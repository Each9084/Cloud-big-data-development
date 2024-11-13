## Module 7: Storage

**Module overview**

**Topics**
•Amazon Elastic Block Store (Amazon EBS) 亚马逊弹性块存储
•Amazon Simple Storage Service (Amazon S3) 亚马逊简单存储服务
•Amazon Elastic File System (Amazon EFS) 亚马逊弹性文件系统
•Amazon Simple Storage Service Glacier 亚马逊简单存储服务冰川

云存储通常比传统的本地存储系统更可靠、更可扩展、更安全。云存储是云计算的重要组成部分，因为它保存着应用程序使用的信息。大数据分析、数据仓库、物联网 (IoT)、数据库以及备份和归档应用程序都依赖于某种形式的数据存储架构。

本模块讨论以下主题：
•Amazon Elastic Block Store (Amazon EBS)
•Amazon Simple Storage Service (Amazon S3)
•Amazon Elastic File System (Amazon EFS)
•Amazon Simple Storage Service Glacier

**Module objectives**

![屏幕截图 2024-11-13 183008](../Cloud big data development/asset/image/屏幕截图 2024-11-13 183008.jpg)



存储是另一个 AWS 核心服务类别。存储的一些大类包括：实例存储（临时存储）、Amazon EBS、Amazon EFS、Amazon S3 和 Amazon S3 Glacier。
•实例存储或临时存储是添加到 Amazon EC2 实例的临时存储。
•Amazon EBS 是持久的可安装存储，可以作为设备安装到 Amazon EC2 实例。Amazon EBS 只能安装到同一可用区内的 Amazon EC2 实例。一次只能安装一个 Amazon EC2 实例。
•Amazon EFS 是一个共享文件系统，多个 Amazon EC2 实例可以同时安装。
•Amazon S3 是持久存储，其中每个文件都成为一个对象，可通过统一资源定位器 (URL) 访问；可以从任何地方访问它。
•Amazon S3 Glacier 用于冷存储不经常访问的数据（例如，当您出于存档或合规性原因需要长期数据存储时）



### Section 1: Amazon Elastic Block Store (Amazon EBS)

**Amazon EBS** 提供持久性块存储卷，供 Amazon EC2 实例使用。持久性存储是任何在设备断电后仍保留数据的数据存储设备。它有时也称为非易失性存储。

每个 Amazon EBS 卷都会在其可用区内自动复制，以保护您免受组件故障的影响。它专为高可用性和耐用性而设计。

Amazon EBS 卷提供运行工作负载所需的一致和低延迟性能。使用 Amazon EBS，您可以在几分钟内增加或减少使用量，同时只需为您配置的内容支付低廉的费用

![屏幕截图 2024-11-13 183359](../Cloud big data development\asset\image\屏幕截图 2024-11-13 183359.jpg)

如果您想要更改 1 GB 文件中的一个字符，会发生什么情况？使用块存储，您只需更改包含该字符的块。使用对象存储，则必须更新整个文件。某些存储类型之间的一个关键区别是它们提供块级存储还是对象级存储。这种差异对存储解决方案的吞吐量、延迟和成本有重大影响。块存储解决方案通常速度更快且占用的带宽更少，但它们的成本可能高于对象级存储。



**Amazon EBS**

Amazon EBS 可让您创建单独的存储卷并将其附加到 Amazon EC2 实例：
•Amazon EBS 提供块级存储。
•卷在其可用区域内自动复制。
•它可以通过快照自动备份到 Amazon S3。
•用途包括 –•Amazon Elastic Compute Cloud (Amazon EC2) 实例的引导卷和存储
•使用文件系统的数据存储•数据库主机•企业应用程序

Amazon EBS 可让您创建单独的存储卷并将其附加到 Amazon EC2 实例。Amazon EBS 提供块级存储，其中其卷在其可用区内自动复制。Amazon EBS 旨在为您的 Amazon EC2 实例提供持久、可拆卸的块级存储（类似于外部硬盘）。

由于它们直接附加到实例，因此它们可以在数据存储位置和实例上可能使用数据的位置之间提供低延迟。因此，它们可用于使用 Amazon EC2 实例运行数据库。Amazon EBS 卷作为实例备份到 Amazon 系统映像（或 AMI）的一部分包含在内。AMI 存储在 Amazon S3 中，以后可以重复使用以创建新的 Amazon EC2 实例。

Amazon EBS 卷的备份(A backup of an Amazon EBS volume)称为快照(snapshot)。第一个快照称为基线快照(baseline snapshot)。基线之后的任何其他快照仅捕获与上一个快照不同的内容

Amazon EBS 卷的用途包括：
•Boot volumes and storage for Amazon EC2 instances |Amazon EC2 实例的启动卷和存储
•Data storage with a file system 文件系统的数据存储
•Database hosts 数据库主机
•Enterprise applications 企业应用程序

![屏幕截图 2024-11-13 184000](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-13 184000.jpg)

将正确的技术与您的工作负载相匹配是降低存储成本的最佳实践。预配置 IOPS SSD 支持的 Amazon EBS 卷可以为您提供最高的性能。但是，如果您的应用程序不需要或不会使用如此高的性能，通用 SSD 通常就足够了。只有 SSD 可以用作 EC2 实例的启动卷。低成本选项可能是除启动卷之外的额外存储或用例的解决方案。

![屏幕截图 2024-11-13 184034](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-13 184034.jpg)

![translated_image_zh-CN](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\translated_image_zh-CN.png)

如前所述，Amazon EBS 卷是一种耐用的块级存储设备，您可以将其连接到单个 EC2 实例。您可以将 Amazon EBS 卷用作需要频繁更新的数据的主存储，例如实例的系统驱动器或数据库应用程序的存储。您还可以将它们用于执行连续磁盘扫描的吞吐量密集型应用程序。Amazon EBS 卷的持久性与 EC2 实例的运行寿命无关。

EBS 的使用案例因所使用的存储类型以及您使用的是通用 IOPS 还是预配置 IOPS 而异

![屏幕截图 2024-11-13 184224](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-13 184224.jpg)

为了提供更高级别的数据持久性，Amazon EBS 允许您创建卷的时间点快照，并且您可以随时从快照重新创建新卷。您还可以共享快照，甚至将快照复制到不同的 AWS 区域，以获得更强大的灾难恢复 (DR) 保护。例如，您可以加密快照并将其从美国弗吉尼亚州共享到日本东京。

您还可以免费获得加密的 Amazon EBS 卷，因此在 EC2 实例和 AWS 数据中心内的 EBS 卷之间移动的数据在传输过程中是加密的。

随着公司的发展，存储在 Amazon EBS 卷上的数据量也可能会增加。Amazon EBS 卷可以增加容量并更改为不同类型，因此您可以从硬盘驱动器 (HDD) 更改为固态驱动器 (SSD)，或从 50 GB 卷增加到 16 TB 卷。例如，您可以动态执行此调整大小操作，而无需停止实例。



当您开始估算 Amazon EBS 的成本时，您必须考虑以下几点：
1.**Volumes** – 所有 Amazon EBS 卷类型的卷存储均按您每月配置的 GB 量收费，直到您释放存储为止。
2.**IOPS – I/O** 包含在通用 SSD 卷的价格中。但是，对于 Amazon EBS 磁性卷，I/O 按您对卷发出的请求数量收费。对于预配置 IOPS SSD 卷，您还需要按您配置的 IOPS 量（乘以您当月配置的天数百分比）付费。

3.**Snapshots 快照** – Amazon EBS 可让您将数据快照备份到 Amazon S3 以实现持久恢复。如果您选择 Amazon EBS 快照，则增加的费用按存储数据每 GB 月计算。
4.**Data transfer 数据传输** – 复制 Amazon EBS 快照时，您需要为跨区域传输的数据付费。复制快照后，将对目标区域的存储收取标准 Amazon EBS 快照费用。

Amazon EBS 提供块级存储卷，供 Amazon EC2 实例使用。Amazon EBS 卷是独立于实例生命周期的实例外存储。它们类似于云中的虚拟磁盘。Amazon EBS 提供三种卷类型：通用 SSD、预配置 IOPS SSD 和磁性卷。

三种卷类型的性能特征和成本各不相同，因此您可以根据应用程序的需求选择合适的存储性能和价格.

其他好处包括在同一可用区域进行复制、简单透明的加密、弹性卷以及使用快照进行备份。



### Section 2: Amazon Simple Storage Service (Amazon S3)

Amazon S3 是对象级存储，这意味着如果您要更改文件的一部分，则必须进行更改，然后重新上传整个修改后的文件。Amazon S3 将数据作为对象存储在称为存储桶的资源中。您现在将了解有关 Amazon S3 的更多信息。

Amazon S3 是一种托管云存储解决方案，旨在无缝扩展并提供 11 个 9 的持久性。您可以在存储桶中存储几乎任意数量的对象，并且可以在存储桶中写入、读取和删除对象。存储桶名称是通用的，并且在 Amazon S3 中所有现有的存储桶名称中必须是唯一的。对象的大小最多可达 5 TB。默认情况下，Amazon S3 中的数据冗余存储在多个设施和每个设施中的多个设备上.

您在 Amazon S3 中存储的数据不与任何特定服务器相关联，并且您无需亲自管理任何基础设施。您可以将任意数量的对象放入 Amazon S3。Amazon S3 可容纳数万亿个对象，并且每秒的请求数经常达到数百万。

对象可以是几乎任何数据文件，例如图像、视频或服务器日志。由于 Amazon S3 支持高达几 TB 大小的对象，因此您甚至可以将数据库快照存储为对象。Amazon S3 还通过超文本传输协议 (HTTP) 或安全 HTTP (HTTPS) 通过互联网提供对数据的低延迟访问，因此您可以随时随地检索数据。您还可以通过虚拟私有云 (VPC) 终端节点私下访问 Amazon S3。您可以使用 AWS Identity and Access Management (IAM) 策略、Amazon S3 存储桶策略甚至每个对象的访问控制列表来精细控制谁可以访问您的数据。

默认情况下，您的任何数据都不会公开共享。您还可以加密传输中的数据，并选择对对象启用服务器端加密。您可以通过基于 Web 的 AWS 管理控制台访问 Amazon S3；通过 API 和 SDK 以编程方式访问；或者使用第三方解决方案（使用 API 或 SDK）。

Amazon S3 包含事件通知，可让您设置发生某些事件时的自动通知，例如将对象上传到存储桶或从特定存储桶中删除对象时。这些通知可以发送给您，也可以用于触发其他流程，例如 AWS Lambda 函数。

通过存储类分析，您可以分析存储访问模式并将正确的数据转换到正确的存储类。Amazon S3 Analytics 功能会自动识别最佳生命周期策略，以将不常访问的存储转换为 Amazon S3 Standard –Infrequent Access (Amazon S3 Standard-IA)。您可以配置存储类分析策略来监控整个存储桶、前缀或对象标签。

当观察到不频繁访问模式时，您可以根据结果轻松创建新的生命周期年龄策略。存储类分析还在 AWS 管理控制台中提供存储使用情况的每日可视化。您可以将它们导出到 Amazon S3 存储桶，使用您选择的商业智能 (BI) 工具（例如 Amazon QuickSight）进行分析。

#### Amazon S3 

![屏幕截图 2024-11-13 204046](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-13 204046.jpg)



Amazon S3 提供一系列针对不同用例设计的对象级存储类别。这些类别包括：

- **Amazon S3 Standard** –Amazon S3 Standard 专为频繁访问的数据提供高耐用性、可用性和高性能对象存储而设计。由于 Amazon S3 标准提供低延迟和高吞吐量，因此适用于各种使用案例，包括云应用程序、动态网站、内容分发、移动和游戏应用程序以及大数据分析。
- **Amazon S3 Intelligent-Tiering** – Amazon S3 智能分层存储类旨在通过自动将数据移动到最具成本效益的访问层来优化成本，而不会影响性能或运营开销。只需为每个对象支付少量的每月监控和自动化费用，Amazon S3 便会监控 Amazon S3 智能分层中对象的访问模式，并将连续 30 天未访问的对象移动到不频繁访问层。如果访问了不频繁访问层中的对象，则会自动将其移回频繁访问层。使用 Amazon S3 智能分层存储类时无需支付检索费用，在访问层之间移动对象时也无需支付额外费用。它非常适合访问模式未知或不可预测的长期数据
- **Amazon S3  Standard-Infrequent Access (Amazon S3 Standard-IA)** –Amazon S3 标准 - IA 存储类用于访问频率较低但需要快速访问的数据。Amazon S3 标准 - IA 旨在提供 Amazon S3 标准的高耐用性、高吞吐量和低延迟，同时具有较低的每 GB 存储价格和每 GB 检索费用。低成本和高性能的结合使 Amazon S3 标准 - IA 非常适合长期存储和备份，以及作为灾难恢复文件的数据存储。
- **Amazon S3 One Zone-Infrequent Access (Amazon S3 One Zone-IA)** - Amazon S3 单区-IA 适用于访问频率较低但需要快速访问的数据。与其他将数据存储在至少三个可用区的 Amazon S3 存储类别不同，Amazon S3 单区-IA 将数据存储在单个可用区中，并且成本低于 Amazon S3 标准-IA。Amazon S3 单区-IA 非常适合那些希望以较低成本存储不经常访问的数据但不需要 Amazon S3 标准或 Amazon S3 标准-IA 的可用性和弹性的客户。它是存储本地数据或可轻松重新创建的数据的辅助备份副本的不错选择。您还可以将其用作使用 Amazon S3 跨区域复制从另一个 AWS 区域复制的数据的经济高效的存储
- **Amazon S3 Glacier** –Amazon S3 Glacier 是一种安全、耐用且低成本的数据存档存储类。您可以可靠地存储任何数量的数据，其成本与本地解决方案相当，甚至更低。为了保持低成本并满足各种需求，Amazon S3 Glacier 提供了三种检索选项，时间范围从几分钟到几小时不等。您可以将对象直接上传到 Amazon S3 Glacier，或使用 Amazon S3 生命周期策略在任何 Amazon S3 活动数据存储类（Amazon S3 Standard、Amazon S3 Intelligent-Tiering、Amazon S3 Standard-IA 和 Amazon S3 One Zone-IA）和 Amazon S3 Glacier 之间传输数据。
- **Amazon S3 Glacier Deep Archive** –Amazon S3 Glacier Deep Archive 是 Amazon S3 中成本最低的存储类。它支持对一年可能访问一两次的数据进行长期保留和数字保存。它专为客户而设计，尤其是金融服务、医疗保健和公共部门等监管严格的行业中的客户，这些客户需要保留数据集 7-10 年（或更长时间）以满足监管合规性要求。Amazon S3 Glacier Deep Archive 还可用于备份和灾难恢复用例。它是一种经济高效且易于管理的磁带系统替代方案，无论这些磁带系统是本地库还是异地服务。Amazon S3 Glacier Deep Archive 是对 Amazon S3 Glacier 的补充，它还旨在提供 11 9 s 的耐用性。存储在 Amazon S3 Glacier Deep Archive 中的所有对象都会在至少三个地理分散的可用区中复制和存储，并且这些对象可以在 12 小时内恢复

#### Amazon S3 bucket URLs (two styles)

![屏幕截图 2024-11-13 204546](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-13 204546.jpg)



要有效使用 Amazon S3，您必须了解一些简单的概念。首先，Amazon S3 将数据存储在存储桶内。存储桶本质上是一组文件的前缀，并且必须在全球范围内的整个 Amazon S3 中具有唯一的名称。存储桶是对象的逻辑容器。您的账户中可以有一个或多个存储桶。您可以控制每个存储桶的访问权限 - 谁可以创建、删除和列出存储桶中的对象。您还可以查看存储桶及其对象的访问日志，并选择 Amazon S3 存储存储桶及其内容的地理区域。

要上传数据（例如照片、视频或文档），请在 AWS 区域中创建一个存储桶，然后将几乎任意数量的对象上传到该存储桶。

在示例中，Amazon S3 用于在东京区域创建存储桶，该存储桶在 AWS 中正式由其区域代码标识：ap-northeast-1

存储桶的 URL 结构与示例类似。您可以使用两种不同的 URL 样式来引用存储桶。

Amazon S3 将文件称为对象。只要您有存储桶，就可以在其中存储几乎任意数量的对象。对象由数据和描述该文件的任何元数据（包括 URL）组成。要在 Amazon S3 中存储对象，请将要存储的文件上传到存储桶。

上传文件时，您可以设置数据和任何元数据的权限。

在此示例中，对象 Preview2.mp4 存储在存储桶内。该文件的 URL 末尾包含对象名称。

![屏幕截图 2024-11-13 204829](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-13 204829.jpg)

当您在 Amazon S3 中创建存储桶时，它会与特定的 AWS 区域相关联。当您将数据存储在存储桶中时，它会冗余地存储在所选区域内的多个 AWS 设施中。

Amazon S3 旨在持久存储您的数据，即使两个 AWS 设施同时发生数据丢失。

![屏幕截图 2024-11-13 204916](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-13 204916.jpg)

随着数据的增长，Amazon S3 会自动管理存储桶背后的存储。您可以立即开始使用，并且您的数据存储将随着应用程序需求的增长而增长。

Amazon S3 还可以扩展以处理大量请求。您无需预置存储或吞吐量，只需按实际使用量付费。