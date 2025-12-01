**Task B** — **Design and Implement Auto-scaling** 的任务要求我们为 **WordFreq 应用程序** 实现 **自动扩展**（Auto-scaling）功能。这个任务的目标是确保当工作负载增加时，自动增加更多的工作实例（worker instances），并且当工作负载降低时，自动减少不必要的实例，以便高效地处理文件处理任务。



Task B – Design and Implement Auto-scaling Review the architecture of the existing application. Each job process takes a random time to complete between 10-20 seconds (artificially induced, but DO NOT modify the application source code!). To be able to process multiple uploaded files, we need to add scaling to the application.

This should initially function as follows: • When a given maximum performance metric threshold is exceeded, an identical worker instance is launched and begins to also process messages on the queues. • When a given minimum performance metric threshold is exceeded, the most recently launched worker instance is removed (terminated). • There must always be at least one worker instance available to process messages when the application architecture is 'live'. • You don’t want to add more instances every 2 minutes. Using the knowledge gained from the Cloud Foundations course, architect, please implement autoscaling functionality for the WordFreq application and demonstrate how you configure the autoscaling policy. Note that this will not be exactly the same as Lab 6 in Module 10, which is for a web application. You will not need a load balancer, and you will need to identify a different CloudWatch performance metric to use for the ‘scale out’ and ‘scale in’ rules. The 'Average CPU Utilization' metric used in Lab 6 is not necessarily the best choice for this application.





![image-20241201124742522](C:\Users\EACH\AppData\Roaming\Typora\typora-user-images\image-20241201124742522.png)



### **Task B的关键需求：**

1. **自动扩展和缩减规则：**
   - 当 **CPU利用率** 或 **队列长度** 等性能指标超过设定的阈值时，自动增加一个新的工作实例。
   - 当 **CPU利用率** 或 **队列长度** 降低到某个最小阈值时，自动删除最近启动的工作实例。
   - 保证至少有一个工作实例始终在运行，处理队列中的任务。
2. **自定义性能指标：**
   - 与 **Lab 6** 中使用的 `Average CPU Utilization` 不同，在这里我们需要选择一个适合的性能指标来触发 **扩展（scale out）** 和 **收缩（scale in）**。
3. **不使用负载均衡器**：由于这是一个非Web应用程序，**WordFreq应用程序** 处理的是异步任务队列，所以我们不需要设置负载均衡器。
4. **不每两分钟扩展**：我们需要一个灵活的触发机制，而不是固定的时间间隔。

### **实施自动扩展功能：**

在实现自动扩展时，我看了一下得使用 **Amazon EC2 Auto Scaling** 和 **Amazon CloudWatch** 来监控和调整实例的数量。



### **步骤 1：定义自动扩展组**

1. **创建启动模板（Launch Template）**：
   - 自动扩展组需要一个启动模板（Launch Template），用于定义实例的启动配置，例如实例类型、AMI、密钥对等。
   - 在 AWS 控制台中创建一个启动模板，配置好 EC2 实例的所有启动细节，例如：
     - **AMI**：选择与咱们自己应用程序兼容的 Ubuntu 版本（例如 Ubuntu 22.04）。
     - **实例类型**：选择合适的实例类型（例如 `t2.micro` 或 `t3.small`）。
     - **安全组**：选择允许 SSH 访问和其他必要端口的安全组。
2. **创建自动扩展组**：
   - 使用创建的启动模板，在 **EC2 Auto Scaling** 中创建一个自动扩展组。
   - 配置 **最小实例数** 为 1（保证至少有一个工作实例）。
   - 配置 **最大实例数** 为合理的值（例如 10 个实例，视负载而定）。
   - 设置 **期望实例数**（Desired Capacity）为 1（初始化时启动 1 个实例）。

------

### **步骤 2：选择并创建性能指标**

为了确保自动扩展机制能有效地工作，这里的话需要选择合适的性能指标，通常考虑 **SQS队列长度** 或 **EC2 CPU 使用率**。因为这是一个异步文件处理应用，CPU 使用率可能不是最理想的选择，**SQS 队列的消息数量** 更能反映任务积压的情况。

1. 创建自定义 CloudWatch 指标：

   - 这部分的话可以监控 **SQS 队列的消息数量** 来决定是否需要扩展或收缩实例数量。
   - 使用 **CloudWatch 监控 SQS 队列的消息数**，为扩展和收缩设置触发条件。
   - 例如，当队列中的消息数超过某个阈值（比如 1000 瞎编的指标），可以触发 **scale out** 规则。

------

### **步骤 3：配置自动扩展规则**

根据需求配置 **scale out**（扩展）和 **scale in**（收缩）规则。

1. **扩展规则（Scale Out）**：
   - **目标**：当 **SQS 队列中的消息数量** 超过设定的阈值时，启动一个新的 EC2 实例来处理更多的任务。
   - **阈值**：假设设置阈值为 1000 条消息，当队列中的消息数量超过 1000 时，触发扩展。
   - **扩展动作**：增加一个实例。
   - **冷却时间**：设置冷却时间为 300 秒（5 分钟），防止短时间内频繁扩展。
2. **收缩规则（Scale In）**：
   - **目标**：当 **SQS 队列中的消息数量** 降低到设定的最小阈值时，终止最近启动的 EC2 实例。
   - **阈值**：假设设置阈值为 100 条消息，当队列中的消息数量低于 100 时，触发收缩。
   - **收缩动作**：减少一个实例。
   - **冷却时间**：设置冷却时间为 300 秒（5 分钟），防止过于频繁地收缩实例。

------

### **步骤 4：配置 CloudWatch 警报**

为了使 **Auto Scaling** 机制响应 **SQS 队列的消息数量**，需要配置 **CloudWatch 警报**，监控队列的大小并触发自动扩展。

1. **创建 CloudWatch 警报**：
   - 监控 **SQS 队列的消息数**，当消息数超过设定阈值（如 1000）时，触发 **扩展**。
   - 创建另一个警报，当消息数低于设定的最小阈值（如 100）时，触发 **收缩**。
2. **配置警报**：
   - 创建 **扩展警报** 和 **收缩警报**，并将这些警报与相应的 **Auto Scaling 组** 关联起来。

------

### **步骤 5：测试自动扩展功能**

1. **模拟负载增加**：
   - 可以通过上传多个文件到 **S3 上传存储桶**，或者手动向 **SQS 队列** 添加消息，模拟负载增加。
   - 监控 **CloudWatch**，检查是否会根据消息数量触发自动扩展规则。
2. **模拟负载减少**：
   - 可以通过减少 **SQS 队列中的消息**，或者暂停上传文件，模拟负载减少。
   - 监控是否触发自动收缩规则，减少工作实例的数量。

