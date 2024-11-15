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
•使用文件系统的数据存储
•数据库主机
•企业应用程序

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

![屏幕截图 2024-11-13 205334](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-13 205334.jpg)

您可以通过控制台、AWS 命令行界面 (AWS CLI) 或 AWS SDK 访问 Amazon S3。您还可以使用基于 REST 的终端节点直接访问存储桶中的数据。

终端节点支持 HTTP 或 HTTPS 访问。要支持这种基于 URL 的访问，Amazon S3 存储桶名称必须是全局唯一的，并且符合域名服务器 (DNS) 的要求。

此外，对象键应该使用对 URL 安全的字符。

这种存储几乎无限量数据（并且可从任何地方访问这些数据）的灵活性意味着 Amazon S3 适用于各种场景。现在，您将考虑 Amazon S3 的一些使用案例：

- 作为任何应用程序数据的位置，Amazon S3 存储桶提供了一个共享位置，用于存储任何应用程序实例（包括 Amazon EC2 上的应用程序甚至传统服务器）都可以访问的对象。此功能对于用户生成的媒体文件、服务器日志或应用程序必须存储在公共位置的其他文件非常有用。此外，由于可以直接通过互联网获取内容，因此您可以将提供这些内容的任务从应用程序中转移，并让客户端直接从 Amazon S3 本身获取数据。
- 对于静态网络托管，Amazon S3 存储桶可以提供您网站的静态内容，包括 HTML、CSS、JavaScript 和其他文件。
- Amazon S3 的高耐用性使其成为存储数据备份的理想选择。为了获得更高的可用性和灾难恢复能力，Amazon S3 甚至可以配置为支持跨区域复制，以便一个区域中的 Amazon S3 存储桶中的数据可以自动复制到另一个 Amazon S3 区域.

#### Amazon S3 common scenarios

![屏幕截图 2024-11-13 205600](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-13 205600.jpg)

**备份与存储** – 为他人提供数据备份与存储服务

**应用程序托管** – 提供部署、安装和管理 Web 应用程序的服务

**媒体托管**——构建冗余、可扩展且高度可用的基础设施，用于托管视频、照片或音乐的上传和下载

**软件交付** – 托管客户可以下载的软件应用程序



#### Amazon S3 pricing

![屏幕截图 2024-11-13 205740](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-13 205740.jpg)

使用 Amazon S3 时，具体费用取决于区域和所发出的具体请求。您只需按实际使用量付费，包括每月 GB 数、从其他区域转出以及 PUT、COPY、POST、LIST 和 GET 请求。

一般来说，您只需为跨越区域边界的传输付费，这意味着您无需为进入 Amazon S3 的传输付费，也无需为从 Amazon S3 转出到同一区域内的 Amazon CloudFront 边缘站点的传输付费。

当您开始估算 Amazon S3 的成本时，必须考虑以下几点：

**1**.**存储类别类型** –

- **Standard storage**旨在提供 11 个 9 的耐用性和 4 个 9 的可用性。
- **S3 Standard –Infrequent Access (S-IA)** – 不频繁访问 (S-IA) 是 Amazon S3 中的一种存储选项，您可以使用它来降低成本，方法是将不经常访问的数据存储在比 Amazon S3 标准存储略低的冗余级别上。标准 – 不频繁访问旨在提供与 Amazon S3 相同的 11 个 9 的耐用性和给定年份的 3 个 9 的可用性。每个类别的费率都不同。

**2.Amount of storage**  – 存储在 Amazon S3 存储桶中的对象的数量和大小。

**3.Requests** - 考虑请求的数量和类型。GET 请求的费用与其他请求（例如 PUT 和 COPY 请求）的费用不同。

- GET——从 Amazon S3 检索对象。您必须具有 READ 权限才能使用此操作。
- PUT——将对象添加到存储桶。您必须对存储桶具有 WRITE 权限才能向其中添加对象。
- COPY——创建已存储在 Amazon S3 中的对象的副本。COPY 操作与执行 GET 然后执行 PUT 相同。

**4.Data transfer** – 考虑从 Amazon S3 区域传输出的数据量。请记住，传入数据是免费的，但传出数据需要付费。

### Section 3: Amazon Elastic File System (Amazon EFS)

#### Storage

**Amazon Elastic File System (Amazon EFS**) 提供简单、可扩展、弹性的文件存储，可与 AWS 服务和本地资源配合使用。它提供了一个简单的界面，让您能够快速轻松地创建和配置文件系统。

Amazon EFS 可根据需要动态扩展，而不会中断应用程序 — 它会随着您添加和删除文件而自动增大和缩小。它旨在让您的应用程序在需要时获得所需的存储空间。

![屏幕截图 2024-11-13 210528](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-13 210528.jpg)

Amazon EFS 是一项完全托管的服务，可让您轻松在 AWS 云中设置和扩展文件存储。您可以使用 Amazon EFS 构建文件系统，用于大数据和分析、媒体处理工作流、内容管理、Web 服务和主目录。

您可以创建可通过文件系统接口（使用标准操作系统文件 I/O API）供 Amazon EC2 实例访问的文件系统。这些文件系统支持完整的文件系统访问语义，例如强一致性和文件锁定。

Amazon EFS 文件系统可以自动从 GB 扩展到 PB 级数据，而无需预置存储。数千个 Amazon EC2 实例可以同时访问 Amazon EFS 文件系统，Amazon EFS 旨在为每个 Amazon EC2 实例提供一致的性能。Amazon EFS 还具有高耐用性和高可用性。Amazon EFS 不要求最低费用或设置成本，您只需为您使用的存储付费.

![屏幕截图 2024-11-13 210624](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-13 210624.jpg)

Amazon EFS 在云中提供文件存储。借助 Amazon EFS，您可以创建文件系统，将文件系统挂载到 Amazon EC2 实例上，然后从文件系统读取和写入数据。您可以通过 NFS 版本 4.0 和 4.1 (NFSv4) 在 VPC 中挂载 Amazon EFS 文件系统。

您可以从 VPC 中的 Amazon EC2 实例同时访问 Amazon EFS 文件系统，因此超出单个连接的应用程序可以访问文件系统。在同一 AWS 区域内的多个可用区中运行的 Amazon EC2 实例可以访问文件系统，因此许多用户可以访问和共享通用数据源。

在图中，VPC 有三个可用区，每个可用区都有一个在其中创建的挂载目标。我们建议您从同一可用区内的挂载目标访问文件系统。其中一个可用区有两个子网。但是，仅在其中一个子网中创建了挂载目标。



您必须完成五个步骤才能创建和使用您的第一个 Amazon EFS 文件系统、将其挂载到您的 VPC 中的 Amazon EC2 实例上并测试端到端设置：

- 创建 Amazon EC2 资源并启动实例。（您必须先创建密钥对，然后才能启动并连接到 Amazon EC2 实例，除非您已经拥有密钥对。）
- 创建您的 Amazon EFS 文件系统。
- 在适当的子网中，创建挂载目标。
- 接下来，连接到您的 Amazon EC2 实例并挂载 Amazon EFS 文件系统。
- 最后，清理您的资源并保护您的 AWS 账户。



#### Amazon EFS resources

![屏幕截图 2024-11-13 211019](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-13 211019.jpg)

在 Amazon EFS 中，文件系统是主要资源。每个文件系统都具有以下属性：

- ID
- Creation token
- Creation time
- File system size in bytes
- Number of mount targets that are created for the file system
- File system state 

Amazon EFS 还支持其他资源来配置主资源。这些资源包括挂载目标和标签。

挂载目标：要访问文件系统，您必须在 VPC 中创建挂载目标。每个挂载目标都具有以下属性：

- The mount target ID
- The subnet ID for the subnet where it was created
- The file system ID for the file system where it was created
- An IP address where the file system can be mounted
- The mount target state

您可以在 mount 命令中使用 IP 地址或域名系统 (DNS) 名称。

标签：为了帮助您组织文件系统，您可以为您创建的每个文件系统分配自己的元数据。每个标签都是一个键值对。

将挂载目标和标签视为子资源，除非它们与文件系统相关联，否则它们不存在。



您已完成对 Amazon EFS 的介绍，包括主要功能和主要资源。Amazon EFS 在云中提供文件存储，非常适合大数据和分析、媒体处理工作流、内容管理、Web 服务和主目录。

当添加或删除文件时，Amazon EFS 会扩大或缩小规模，并且您只需为正在使用的部分付费。

Amazon EFS 是一项完全托管的服务，可以通过控制台、API 或 AWS CLI 访问。

### Section 4: Amazon S3 Glacier

Amazon S3 Glacier 是一种安全、耐用且成本极低的云存储服务，用于数据存档和长期备份。

#### Amazon S3 Glacier Review

![屏幕截图 2024-11-13 211419](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-13 211419.jpg)

当您使用 Amazon S3 Glacier 存档数据时，您可以以极低的成本存储数据（甚至与 Amazon S3 相比），但您无法在需要时立即检索数据。

存储在 Amazon S3 Glacier 中的数据可能需要几个小时才能检索，这就是它适合存档的原因。

您应该熟悉三个关键的 Amazon S3 Glacier 术语：

- **Archive: **您存储在 Amazon S3 Glacier 中的任何对象（例如照片、视频、文件或文档）。它是 Amazon S3 Glacier 中的基本存储单位。每个档案都有自己唯一的 ID，也可以有描述。
- **Vault(保险库):** 用于存储档案的容器。创建文件库时，请指定文件库名称以及要放置文件库的区域。
- **Vault access policy(保管库访问策略):** 确定哪些人可以访问和哪些人不能访问存储在保管库中的数据，以及用户可以和不能执行哪些操作。可以为每个保管库创建一个保管库访问权限策略来管理该保管库的访问权限。您还可以使用保管库锁定策略来确保保管库无法被更改。每个保管库可以有一个保管库访问策略和一个保管库锁定策略与其关联。

您有三种检索数据的选项，每种选项的访问时间和成本各不相同：

- **Expedited** Retrievals(**加急检索)**通常在 1-5 分钟内完成（费用最高）。
- **Standard** retrievals 通常在 3-5 小时内完成（比加急检索时间短，比批量检索时间长）。
- **Bulk** (批量)检索通常在 5-12 小时内完成（成本最低）。

您可以将这些选项与选择最经济的包裹运输成本进行比较，以满足您的需求

![屏幕截图 2024-11-13 211852](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-13 211852.jpg)

#### Amazon S3 Glacier use cases

![image-20241113211944855](C:\Users\EACH\AppData\Roaming\Typora\typora-user-images\image-20241113211944855.png)

**Media asset archiving**

媒体资产（例如视频和新闻片段）需要持久存储，并且随着时间的推移可能会增长到数 PB。Amazon S3 Glacier 可让您以经济实惠的方式存档旧媒体内容，然后在需要时将其移动到 Amazon S3 进行分发。



**Healthcare information archiving** **(医疗保健信息归档)**

为了满足监管要求，医院系统必须保留数十年的 PB 级患者记录（例如低收入补贴 (LIS) 信息、图片存档和通信系统 (PACS) 数据或电子健康记录 (EHR)。Amazon S3 Glacier 可以帮助您以极低的成本安全地存档患者记录数据。



**Regulatory and compliance archiving (监管与合规性归档)**

许多企业（例如金融服务和医疗保健行业）必须长期保留监管和合规性档案。Amazon S3 Glacier Vault Lock 可以帮助您设置合规性控制，以便您努力实现合规性目标，例如美国证券交易委员会 (SEC) 规则 17a-4(f)。



**Scientific data archiving (科学数据归档)**

研究机构生成、分析和存档大量数据。通过使用 Amazon S3 Glacier，您可以降低硬件和设施管理以及容量规划的复杂性。



**Digital preservation (数字保存)**

图书馆和政府机构必须在数字保存工作中应对数据完整性挑战。与需要费力的数据验证和手动修复的传统系统不同，Amazon S3 Glacier 会定期执行系统性的数据完整性检查，并且能够自动自我修复



#### Using Amazon S3 Glacier

![image-20241113212252409](C:\Users\EACH\AppData\Roaming\Typora\typora-user-images\image-20241113212252409.png)

要在 Amazon S3 Glacier 中存储和访问数据，您可以使用 AWS 管理控制台。但是，控制台中仅提供少数操作（例如创建和删除文件库以及创建和管理存档策略）。

对于几乎所有其他操作和与 Amazon S3 Glacier 的交互，您必须使用 Amazon S3 Glacier REST API、AWS Java 或 .NET SDK 或 AWS CLI。

您还可以使用生命周期策略将数据存档到 Amazon S3 Glacier。接下来，您将了解生命周期策略。



#### Lifecycle policies

![image-20241113212437035](C:\Users\EACH\AppData\Roaming\Typora\typora-user-images\image-20241113212437035.png)

您应该自动执行存储在 Amazon S3 中的数据的生命周期。通过使用生命周期策略，您可以在不同的 Amazon S3 存储类型之间定期循环数据。这种自动化可以降低您的总体成本，因为随着时间的推移，数据的重要性会降低，因此您支付的数据费用也会减少。

除了为每个对象设置生命周期规则之外，您还可以为每个存储桶设置生命周期规则。

考虑一个生命周期策略示例，该策略将数据从 Amazon S3 Standard 移动到 Amazon S3 Standard –Infrequent Access，最后移动到 Amazon S3 Glacier 中，然后删除。假设用户将视频上传到您的应用程序，并且您的应用程序生成该视频的缩略图预览。此视频预览存储到 Amazon S3 Standard，因为用户很可能希望立即访问它。

您的使用数据表明，大多数缩略图预览在 30 天后都无人访问。您的生命周期策略会在 30 天后将这些预览移至 Amazon S3 – 不频繁访问。再过 30 天后，预览不太可能再次被访问。然后预览将移至 Amazon S3 Glacier，并在那里保留 1 年。1 年后，预览将被删除。重要的是，生命周期策略会自动管理所有这些移动。

![屏幕截图 2024-11-13 212543](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-13 212543.jpg)

虽然 Amazon S3 和 Amazon S3 Glacier 都是对象存储解决方案，可让您存储几乎无限量的数据，但它们之间存在一些关键差异。 图表概述了其中一些差异。

- 在决定哪种存储解决方案适合您的需求时，请务必谨慎。这两种服务满足截然不同的存储需求。Amazon S3 专为频繁、低延迟地访问数据而设计，而 Amazon S3 Glacier 专为低成本、长期存储不频繁访问的数据而设计。
- Amazon S3 中的最大项目大小为 5 TB，但 Amazon S3 Glacier 可以存储高达 40 TB 的项目。
- 由于 Amazon S3 可让您更快地访问数据，因此每 GB 的存储成本高于 Amazon S3 Glacier。
- 虽然这两项服务都按请求收费，但 Amazon S3 对 PUT、COPY、POST、LIST、GET 操作收费。相比之下，Amazon S3 Glacier 对 UPLOAD 和检索操作收费。
- 由于 Amazon S3 Glacier 专为不频繁访问数据而设计，因此每次检索请求的成本比 Amazon S3 更高。



#### Server-side encryption

![屏幕截图 2024-11-13 213142](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-13 213142.jpg)

Amazon S3 和 Amazon S3Glacier 之间的另一个重要区别是数据的加密方式。服务器端加密专注于保护静态数据。使用这两种解决方案，您都可以通过 HTTPS 安全地传输数据。默认情况下，存档在 Amazon S3Glacier 中的任何数据都是加密的。使用 Amazon S3，您的应用程序必须启动服务器端加密。您可以通过多种方式在 Amazon S3 中完成服务器端加密：

- 使用 **Amazon S3-managed encryption keys (SSE-S3)** 的服务器端加密采用强大的多因素加密。Amazon S3 使用唯一密钥加密每个对象。作为额外的保护措施，它使用定期轮换的主密钥加密密钥。Amazon S3 服务器端加密使用最强大的分组密码之一 256 位高级加密标准 (AES-256) 来加密您的数据。
- 使用带有**Customer-provided Encryption Keys**  **(SSE-C)** 的服务器端加密，您可以设置自己的加密密钥。您可以将加密密钥作为请求的一部分，Amazon S3 会管理加密（写入磁盘时）和解密（访问对象时）。
- 使用 **AWS Key Management Service (AWS KMS)** 进行服务器端加密是一项服务，它将安全、高度可用的硬件和软件结合起来，提供可扩展到云的密钥管理系统。AWS KMS 使用客户主密钥 (CMK) 来加密您的 Amazon S3 对象。您可以通过 IAM 控制台中的加密密钥部分使用 AWS KMS。您还可以通过 API 访问 AWS KMS，以集中创建加密密钥、定义控制密钥使用方式的策略以及审核密钥使用情况以证明密钥使用正确。您可以使用这些密钥保护 Amazon S3buckets 中的数据。



#### Security with Amazon S3 Glacier

![屏幕截图 2024-11-13 213421](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-13 213421.jpg)

默认情况下，只有您可以访问您的数据。您可以使用 IAM 启用和控制对 Amazon S3 Glacier 中数据的访问。您可以设置指定用户访问权限的 IAM 策略。

- Amazon S3 Glacier 是一种数据存档服务，专为安全性、耐用性和极低成本而设计。
- Amazon S3 Glacier 定价基于区域。
- 其极低成本的设计非常适合长期存档。
- 该服务旨在为对象提供 11  9S 的耐用性。



### Module 7 Knowledge Check

**1.True or False? Amazon Simple Storage Service (Amazon S3) is an object storage suitable for the storage of flat files like Microsoft Word documents, photos, etc.**
   True
   False

**2.Amazon S3 replicates all objects.(Select the best answer)**
1.on multiple volumes within an Availability Zone
2.in multiple Availability Zones within the same Region
3.across multiple Regions for higher durability
4.on multiple S3 buckets

**3.Which of the following can be used as a storage class for an S3 object lifecycle policy? (Choose three)**

A.S3 - Standard Access
B.AWS Storage Gateway
C.S3 - Infrequent Access
D.Simple Storage Service Glacier
E.S3-Reduced Redundancy Storage
F.Amazon Dynamo DB

**4.The name of an S3 bucket must be unique. (Select the best answer)**

A.worldwide across all AWS accounts
B.within a Region
C.across all your AWS accounts
D.within your AWS account



**5.You can use Amazon Elastic File System (Amazon EFS) to: (Select the best answer)**

A.provide simple, scalable, elastic file storage for use only within AWS.
B.implement storage for Amazon EC2 instances that multiple virtual machines can access at      the same time.
C.host a robust CDN to deliver entire web sites with dynamic, static, and streaming content.
D.generate user-specific content.



**6.Amazon Elastic Block Store (Amazon EBS) is recommended when data_ and ___.  (Choose two)**

A.requires object-level storage
B.must be quickly accessible, requiring long-term persistence
C.requires an encryption solution
D.needs to be stored in a different Availability Zone than the one the EC2 instance is in



**7.True or False? By default, all data stored in Amazon S3 is viewable by the public.**

1.True
2.False



**8.Regarding Amazon S3 Glacier, what is a Vault?    (Select the best answer)**

A.The rules that determine who may (or may not) access archives
B.An object (photos, videos, files, or documents)
C.A container for storing archives
D.A policy that identifies who can access content stored in Glacier

**9.True or False? When you create a bucket in Amazon S3, it is associated with a specific AWS Region.**
1.True
2.False



**10.Which of the following are features of Amazon Elastic Block Store (Amazon EBS)?   (Choose two)**

A.Amazon EBS data is automatically backed up to tape.
B.Data on an Amazon EBS volume is lost when the attached instance is stopped.
C.Data stored on Amazon EBS is automatically replicated within an Availability Zone.  
D.Amazon EBS volumes can be encrypted transparently to workloads on the attached instance.

1.TRUE
2.2
3.A C D
4.A
5.B
6.B
7.FALSE
8.C
9.TRUE
10.C D



## Module 8: Databases

商业世界不断变化和发展。通过高效、定期地准确记录、更新和跟踪数据，公司可以利用从数据中获得的洞察力发挥巨大潜力。数据库管理系统是管理这些数据的关键环节。与其他云服务一样，云数据库比传统数据库策略具有显著的成本优势。

在本模块中，您将了解 Amazon Relational Database Service（或 Amazon RDS）、Amazon DynamoDB、Amazon Redshift 和 Amazon Aurora。

This module will address the following topics:

- Amazon Relational Database Service (Amazon RDS)
- Amazon DynamoDB
- Amazon Redshift
- Amazon Aurora



在本模块中，您将了解与数据库解决方案相关的关键概念，包括：

- 了解云中的不同数据库服务。
- 发现非托管和托管数据库解决方案之间的差异。
- 了解结构化查询语言（或 SQL）和 NoSQL 数据库之间的差异。
- 比较替代数据库解决方案的可用性差异。

本模块旨在帮助您了解可用于支持解决方案的数据库资源。您还将查看可用的不同服务功能，以便开始了解不同的选择如何影响解决方案可用性等

完成本模块后，您应该能够：

- 解释 Amazon Relational Database Service (Amazon RDS)
-  识别 Amazon RDS 中的功能
- 解释 Amazon DynamoDB
- 识别 Amazon DynamoDB 中的功能
-  解释 Amazon Redshift• 解释 Amazon Aurora
- 在 RDS 数据库中执行任务，例如启动、配置和交互



### Section 1: Amazon Relational Database Service

#### Amazon Relational Database Service

欢迎阅读 Amazon Web Services (AWS) 上提供的基础数据库服务简介。本模块从 Amazon Relational Database Service (AmazonRDS) 开始。

本节首先回顾与 Amazon RDS 相关的托管服务和非托管服务之间的差异。

![屏幕截图 2024-11-14 090859](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-14 090859.jpg)

AWS 解决方案通常分为两类：非托管或托管。

非托管服务通常按用户指定的离散部分进行配置。您必须管理服务如何响应负载变化、错误和资源不可用的情况。假设您在 Amazon Elastic Compute Cloud (Amazon EC2) 实例上启动 Web 服务器。由于 Amazon EC2 是一种非托管解决方案，因此该 Web 服务器不会扩展以处理增加的流量负载或用健康实例替换不健康的实例，除非您指定它使用扩展解决方案（例如 AWS Automatic Scaling）。使用非托管服务的好处是，您可以更精细地控制解决方案如何处理负载变化、错误和资源不可用的情况。

托管服务需要用户进行配置。例如，您可以创建一个 Amazon Simple Storage Service (Amazon S3) 存储桶，然后为其设置权限。但是，托管服务通常需要较少的配置。假设您有一个静态网站，托管在基于云的存储解决方案（例如 Amazon S3）中。静态网站没有 Web 服务器。但是，由于 Amazon S3 是一种托管解决方案，因此 Amazon S3 会自动内部处理扩展、容错和可用性等功能。

现在，您将了解运行非托管独立关系数据库所面临的挑战。然后，您将了解 Amazon RDS 如何应对这些挑战。

![屏幕截图 2024-11-14 092346](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-14 092346.jpg)

当您运行自己的关系数据库时，您需要负责多项管理任务，例如服务器维护和能源占用、软件、安装和修补以及数据库备份。您还负责确保高可用性、规划可扩展性、数据安全性以及操作系统 (OS) 安装和修补。所有这些任务都需要您待办事项列表中其他项目的资源，并且需要多个领域的专业知识。

![屏幕截图 2024-11-14 092434](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-14 092434.jpg)

Amazon RDS 是一种在云中建立和操作关系数据库的托管服务。

为了解决运行非托管独立关系数据库的挑战，AWS 提供了一种无需任何持续管理即可设置、操作和扩展关系数据库的服务。Amazon RDS 提供经济高效且可调整大小的容量，同时自动执行耗时的管理任务。

Amazon RDS 使您能够专注于应用程序，从而为应用程序提供所需的性能、高可用性、安全性和兼容性。使用 Amazon RDS，您的主要关注点是数据和优化应用程序。

![屏幕截图 2024-11-14 092546](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-14 092546.jpg)

**managed services (托管服务)**这个术语是什么意思？

当您的数据库位于本地时，数据库管理员负责一切。数据库管理任务包括优化应用程序和查询；设置硬件；修补硬件；设置网络和电源；以及管理供暖、通风和空调 (HVAC)。

如果您迁移到在 Amazon Elastic Compute Cloud (Amazon EC2) 实例上运行的数据库，则不再需要管理底层硬件或处理数据中心操作。但是，您仍需负责修补操作系统并处理所有软件和备份操作。

如果您在 Amazon RDS 或 Amazon Aurora 上设置数据库，则可以减少管理责任。通过迁移到云，您可以自动扩展数据库、启用高可用性、管理备份和执行修补。因此，您可以专注于真正最重要的事情——优化您的应用程序。

![屏幕截图 2024-11-14 093039](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-14 093039.jpg)

使用 Amazon RDS，您可以管理应用程序优化。AWS 管理操作系统的安装和修补、数据库软件的安装和修补、自动备份和高可用性。

AWS 还可以扩展资源、管理电力和服务器并执行维护。

将这些操作卸载到托管的 Amazon RDS 服务可减少您的操作工作量和与关系数据库相关的成本。现在您将简要了解该服务以及一些潜在用例。

![屏幕截图 2024-11-14 093132](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-14 093132.jpg)

Amazon RDS 的基本构建块是**Database Instance**。数据库实例是一个独立的数据库环境，可以包含多个用户创建的数据库。可以使用与独立数据库实例相同的工具和应用程序来访问它。数据库实例中的资源由其数据库实例类决定，存储类型由磁盘类型决定。

数据库实例和存储在性能特征和价格上有所不同，因此您可以根据数据库的需求自定义性能和成本。选择创建数据库实例时，必须首先指定要运行的数据库引擎。Amazon RDS 目前支持六种数据库：MySQL、Amazon Aurora、Microsoft SQL Server、PostgreSQL、MariaDB 和 Oracle。

![屏幕截图 2024-11-14 093241](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-14 093241.jpg)

您可以使用 Amazon Virtual Private Cloud (Amazon VPC) 运行实例。使用虚拟私有云 (VPC) 时，您可以控制虚拟网络环境。

您可以选择自己的 IP 地址范围、创建子网以及配置路由和访问控制列表 (ACL)。无论 Amazon RDS 是否在 VPC 中运行，其基本功能都是相同的。通常，数据库实例被隔离在私有子网中，并且仅可由指定的应用程序实例直接访问。VPC 中的子网与单个可用区相关联，因此当您选择子网时，您也在为数据库实例选择可用区（或物理位置）。

![屏幕截图 2024-11-14 093631](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-14 093631.jpg)

Amazon RDS 最强大的功能之一是能够通过多可用区部署配置数据库实例以实现高可用性。配置多可用区部署后，Amazon RDS 会自动在同一 VPC 内的另一个可用区中生成数据库实例的备用副本。播种数据库副本后，事务将同步复制到备用副本。在多可用区部署中运行数据库实例可以增强计划系统维护期间的可用性，并有助于保护数据库免受数据库实例故障和可用区中断的影响。

![屏幕截图 2024-11-14 093941](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-14 093941.jpg)

因此，如果主数据库实例在多可用区部署中发生故障，Amazon RDS 会自动将备用数据库实例联机作为新的主实例。同步复制可最大程度地降低数据丢失的可能性。由于您的应用程序使用 Amazon RDS 域名系统 (DNS) 终端节点按名称引用数据库，因此您无需更改应用程序代码中的任何内容即可使用备用副本进行故障转移。

![屏幕截图 2024-11-14 094034](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-14 094034.jpg)

Amazon RDS 还支持为 MySQL、MariaDB、PostgreSQL 和 Amazon Aurora 创建只读副本。对源数据库实例所做的更新将异步复制到只读副本实例。您可以通过将应用程序的读取查询路由到只读副本来减少源数据库实例上的负载。使用只读副本，您还可以扩展超出单个数据库实例的容量限制，以处理读取密集型数据库工作负载。也可以将只读副本提升为主数据库实例，但由于异步复制，这需要手动操作。

可以在与主数据库不同的区域中创建只读副本。此功能可以帮助满足灾难恢复要求或通过将读取定向到更靠近用户的只读副本来减少延迟。

![屏幕截图 2024-11-14 094235](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-14 094235.jpg)

Amazon RDS 非常适合需要具有高吞吐量、大规模存储可扩展性和高可用性的数据库的 Web 和移动应用程序。由于 Amazon RDS 没有任何许可限制，因此它适合这些应用程序的可变使用模式。对于小型和大型电子商务企业，Amazon RDS 为在线销售和零售提供了灵活、安全且低成本的数据库解决方案。移动和在线游戏需要具有高吞吐量和可用性的数据库平台。Amazon RDS 管理数据库基础设施，因此游戏开发人员无需担心配置、扩展或监控数据库服务器。

![屏幕截图 2024-11-14 094312](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-14 094312.jpg)

当您的应用程序需要以下功能时，请使用 Amazon RDS：

- 复杂事务或复杂查询
- 中高查询或写入速率 – 高达 30,000 IOPS（15,000 次读取 + 15,000 次写入）
- 不超过单个工作节点或分片
- 高耐用性

如果您的应用程序需要以下条件，请勿使用 Amazon RDS：

-  大规模读取/写入速率（例如每秒 150,000 次写入）
-  由于数据量大或吞吐量需求而进行分片
- NoSQL 数据库可以处理的简单 GET 或 PUT 请求和查询
-  或者，关系数据库管理系统 (RDBMS) 自定义

对于不应该使用 Amazon RDS 的情况，请考虑使用 NoSQL 数据库解决方案（例如 DynamoDB）或在 Amazon EC2 实例而不是 Amazon RDS 上运行关系数据库引擎（这将为您提供更多自定义数据库的选项）。

![屏幕截图 2024-11-14 094520](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-14 094520.jpg)

当您开始估算 Amazon RDS 的成本时，您必须考虑服务时间的时钟小时数，这些资源在运行时会产生费用（例如，从启动数据库实例到终止实例的时间）。

还应考虑数据库特性。您选择的数据库的物理容量将影响您的费用。数据库特性因数据库引擎、大小和内存类别而异。

![屏幕截图 2024-11-14 094603](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-14 094603.jpg)

考虑一下数据库购买类型。使用按需实例时，您需要为数据库实例运行的每个小时支付计算容量费用，无需最低承诺。使用预留实例，您可以为想要预留 1 年或 3 年的每个数据库实例支付较低的一次性预付款。

此外，您还必须考虑数据库实例的数量。使用 Amazon RDS，您可以配置多个数据库实例来处理峰值负载。

![屏幕截图 2024-11-14 094650](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-14 094650.jpg)

考虑预配置存储。对于活动数据库实例，备份存储最多可达到预配置数据库存储的 100%，无需额外付费。数据库实例终止后，备份存储按 GB 每月计费。

除了预配置的存储量之外，还要考虑备份存储量，按每 GB、每月计费。

![屏幕截图 2024-11-14 094745](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-14 094745.jpg)

还要考虑对数据库发出的输入和输出请求的数量。

考虑部署类型。您可以将数据库实例部署到单个可用区（类似于独立数据中心）或多个可用区（类似于辅助数据中心，以提高可用性和耐用性）。存储和 I/O 费用会有所不同，具体取决于您部署到的可用区数量。

最后，考虑数据传输。入站数据传输是免费的，出站数据传输费用是分级的。

根据应用程序的需求，可以通过购买预留实例来优化 Amazon RDS 数据库实例的成本。要购买预留实例，您需要为要预留的每个实例支付一笔较低的一次性费用。因此，您将获得该实例每小时使用费的大幅折扣。

![屏幕截图 2024-11-14 100204](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-14 100204.jpg)

本实验旨在向您展示如何使用 AWS 托管数据库实例来解决关系数据库的需求。借助 Amazon RDS，您可以在云中设置、操作和扩展关系数据库。它提供经济高效且可调整大小的容量，同时管理耗时的数据库管理任务，让您可以专注于应用程序和业务。Amazon RDS 提供六种熟悉的数据库引擎供您选择：Amazon Aurora、Oracle、Microsoft SQL Server、PostgreSQL、MySQL 和 MariaDB。

Amazon RDS 多可用区部署为数据库实例提供了增强的可用性和持久性，使其非常适合生产数据库工作负载。当您配置多可用区数据库实例时，Amazon RDS 会自动创建主数据库实例并将数据同步复制到不同可用区中的备用实例。

完成本实验后，您应该能够：

- 启动具有高可用性的 Amazon RDS DB 实例。
- 配置 DB 实例以允许来自 Web 服务器的连接。
- 打开 Web 应用程序并与您的数据库交互。

Amazon RDS 是一种 Web 服务，可让您轻松地在云中设置、操作和扩展关系数据库。它提供经济高效且可调整大小的容量，同时管理耗时的数据库管理任务，以便您可以专注于应用程序和业务。其功能包括它是一项托管服务，并且可以通过控制台、AWS 命令行界面 (AWS CLI) 或应用程序编程接口 (API) 调用进行访问。AmazonRDS 可扩展用于计算和存储，并提供自动冗余和备份。支持的数据库引擎包括 Amazon Aurora、PostgreSQL、MySQL、MariaDB、Oracle 和 Microsoft SQL Server。

Amazon RDS 支持要求严格的数据库应用程序。您可以在两种固态硬盘 (SSD) 支持的存储选项之间进行选择：一种选项针对高性能在线事务处理 (OLTP) 应用程序进行了优化，另一种选项非常适合经济高效的通用用途。

使用 Amazon RDS，您可以扩展数据库的计算和存储资源，而无需停机。Amazon RDS 运行在其他 AWS 服务使用的相同高可靠性基础设施上。它还使您能够运行数据库实例和 Amazon VPC，旨在为您提供控制和安全性。

### Section 2: Amazon DynamoDB

![屏幕截图 2024-11-14 104023](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-14 104023.jpg)

借助 DynamoDB，此模块从关系型数据库过渡到非关系型数据库。下面回顾一下这两类数据库之间的区别：

**Relational Database (RDB)** 使用由表、记录和列组织的结构化数据。RDB 在数据库表之间建立明确定义的关系。RDB 使用结构化查询语言 (SQL)，这是一种标准用户应用程序，可提供用于数据库交互的编程接口。关系数据库可能难以水平扩展或处理半结构化数据，并且可能还需要对规范化数据进行多次连接。

**Anon-relational Database**是指不遵循传统关系型数据库管理系统 (RDBMS) 提供的关系模型的任何数据库。非关系型数据库之所以越来越受欢迎，是因为它们旨在克服关系型数据库在处理可变结构化数据需求方面的局限性。非关系型数据库可以水平扩展，并且可以处理非结构化和半结构化数据。

![image-20241114104155868](C:\Users\EACH\AppData\Roaming\Typora\typora-user-images\image-20241114104155868.png)

DynamoDB 是一种快速而灵活的 NoSQL 数据库服务，适用于所有需要在任何规模下实现一致的个位数毫秒级延迟的应用程序。

作为容错架构的一部分，Amazon 管理此服务的所有底层数据基础设施，并将数据冗余地存储在美国本地区域的多个设施中。使用 DynamoDB，您可以创建表和项目。您可以将项目添加到表中。系统会自动对数据进行分区，并具有表存储以满足工作负载要求。您可以在表中存储的项目数量没有实际限制。例如，一些客户的生产表包含数十亿个项目。

NoSQL 数据库的一个优点是同一张表中的项目可以具有不同的属性。这让您能够随着应用程序的发展灵活地添加属性。您可以将较新格式的项目与较旧格式的项目并排存储在同一张表中，而无需执行架构迁移。

随着您的应用程序越来越受欢迎，并且用户继续与其交互，您的存储可以随着应用程序的需求而增长。 DynamoDB 中的所有数据都存储在固态硬盘 (SSD) 上，其简单的查询语言可实现一致的低延迟查询性能。 除了扩展存储之外，DynamoDB 还使您能够为表预置所需的读取或写入吞吐量。 随着应用程序用户数量的增长，可以通过手动预置扩展 DynamoDB 表以处理增加的读取/写入请求数量。 或者，您可以启用自动扩展，以便 DynamoDB 监控表上的负载并自动增加或减少预置的吞吐量。

一些额外的主要功能包括全局表，使您能够在您选择的 AWS 区域之间自动复制、静态加密和项目生存时间 (TTL)。

![屏幕截图 2024-11-14 104536](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-14 104536.jpg)

DynamoDB 的核心组件是**tables**、**items**和**attributes**。

- 表是数据的集合。
- 项目是一组在所有其他项目中具有唯一可识别性的属性。
- 属性是基本数据元素，不需要进一步细分。

DynamoDB 支持两种不同类型的主键。分区键是一种简单主键，由一个称为排序键的属性组成。分区键和排序键也称为复合主键，由两个属性组成。

![屏幕截图 2024-11-14 104633](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-14 104633.jpg)

随着数据的增长，表数据会根据主键进行分区和索引。

您可以通过两种不同的方式从 DynamoDB 表中检索数据：

- 在第一种方法中，查询操作利用分区来使用主键有效地定位项目。
- 第二种方法是通过扫描，它使您可以通过匹配非关键属性的条件来查找表中的项目。第二种方法使您可以灵活地通过其他属性来查找项目。但是，该操作效率较低，因为 DynamoDB 将扫描表中的所有项目以查找符合您的条件的项目。

![屏幕截图 2024-11-14 104957](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-14 104957.jpg)

为了充分利用查询操作和 DynamoDB，重要的是要考虑用于唯一标识 DynamoDB 表中项目的键。您可以设置一个简单的主键，该主键基于具有均匀分布的数据值的单个属性，例如**Globally Unique Identifier (全局唯一标识符 (GUID))** 或其他随机标识符。

例如，如果您想要为包含产品的表建模，则可以使用一些属性，例如产品 ID。或者，您可以指定复合键，它由分区键和辅助键组成。在此示例中，如果您有一个包含书籍的表，则可以使用作者和标题的组合来唯一标识表项。如果您希望经常按作者查看书籍，则此方法可能很有用，因为您可以使用查询。

对于 **accessibility** **(可访问性)**：两种不同类型的键。单个键表示数据由数据中唯一标识每条记录的项目标识。复合键由分区键和第二个键组成，可用于对数据进行排序。





DynamoDB 专门在 SSD 上运行，并且支持文档和键值存储模型。

DynamoDB 适用于移动、网络、游戏、广告技术和物联网 (IoT) 应用程序。可通过控制台、AWS CLI 和 API 调用访问。

DynamoDB 能够在存储和预置吞吐量方面扩展表，非常适合处理来自 Web、移动和 IoT 应用程序的结构化数据。例如，您可能有大量客户端不断生成数据并每秒发出大量请求。在这种情况下，DynamoDB 的吞吐量扩展可为您的客户端提供一致的性能。DynamoDB 还用于对延迟敏感的应用程序。即使在大型表中，可预测的查询性能也使其适用于可变延迟可能对用户体验或业务目标（例如广告技术游戏）造成重大影响的情况。

DynamoDB 全局表功能减少了在区域之间复制数据和解决更新冲突的工作量。它会自动在您选择的 AWS 区域之间复制您的 DynamoDB 表。全局表可以帮助应用程序保持可用性和高性能，从而实现业务连续性。



### Section 3: Amazon Redshift

Amazon Redshift 是一个快速、完全托管的数据仓库，它让您能够使用标准 SQL 和现有的商业智能 (BI) 工具轻松且经济高效地分析所有数据。下面介绍一下 Amazon Redshift 以及如何将其用于分析应用程序。

![屏幕截图 2024-11-14 105511](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-14 105511.jpg)

分析对于当今的企业来说非常重要，但建立数据仓库既复杂又昂贵。建立数据仓库可能需要数月时间并投入大量资金。

Amazon Redshift 是一个快速、强大、完全托管的数据仓库，其设置、使用和扩展都非常简单且经济高效。它使用复杂的查询优化、高性能本地磁盘上的列式存储和大规模并行数据处理，使您能够针对 PB 级结构化数据运行复杂的分析查询。大多数结果可在几秒钟内返回。

接下来，您将更详细地了解 Amazon Redshift 的主要功能以及一些常见用例。

![屏幕截图 2024-11-14 105624](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-14 105624.jpg)

领导节点管理与客户端程序的通信以及与计算节点的所有通信。它解析并制定计划以执行数据库操作 - 具体来说，是获取复杂查询结果所需的一系列步骤。领导节点编译计划中各个元素的代码，并将代码分配给各个计算节点。计算节点运行编译后的代码并将中间结果发送回领导节点进行最终汇总。

与其他 AWS 服务一样，您只需按实际使用量付费。您只需支付每小时 25 美分的费用即可开始使用，而随着规模的扩大，Amazon Redshift 可以提供每年每 TB 约 1,000 美元的存储和处理费用（采用 3 年期部分预付预留实例定价）。

Amazon Redshift Spectrum 功能使您能够直接在 Amazon S3 中针对 EB 级数据运行查询。

![屏幕截图 2024-11-14 105718](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-14 105718.jpg)

可以轻松自动执行大多数常见的管理任务来管理、监控和扩展您的 Amazon Redshift 集群 - 使您能够专注于您的数据和业务。

可扩展性是 Amazon Redshift 的固有特性。只需在控制台中单击几下，即可根据您的需求变化扩大或缩小集群。

安全性是 AWS 的首要任务。Amazon Redshift 内置了安全性，旨在为静态数据和传输中的数据提供强加密。

![屏幕截图 2024-11-14 105838](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-14 105838.jpg)

最后，Amazon Redshift 与您已经了解和使用的工具兼容。Amazon Redshift 支持标准 SQL。它还提供高性能 Java Database Connectivity (JDBC) 和Open Database Connectivity (ODBC) 连接器，使您可以使用您选择的 SQL 客户端和 BI 工具。

![屏幕截图 2024-11-14 105940](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-14 105940.jpg)

本幻灯片讨论了一些 Amazon Redshift 用例。

许多客户将传统的企业数据仓库迁移到 Amazon Redshift，主要目的是实现敏捷性。客户可以从他们想要的任意规模开始，并对其数据进行实验，而无需依赖 IT 部门的复杂流程来采购和准备软件。

大数据客户有一个共同点：海量数据会将现有系统推向极限。规模较小的客户可能没有资源来采购运行这些系统所需的硬件和专业知识。借助 Amazon Redshift，规模较小的客户可以以相对较低的价格快速设置和使用数据仓库。

作为一项托管服务，Amazon Redshift 可处理许多通常需要数据库管理员执行的部署和持续维护任务。这使客户能够专注于查询和分析其数据。

![屏幕截图 2024-11-14 110207](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-14 110207.jpg)

软件即服务 (SaaS) 客户可以利用 Amazon Redshift 提供的可扩展、易于管理的功能。一些客户使用 Amazon Redshift 为其应用程序提供分析功能。一些用户为每个客户部署一个集群，并使用标记来简化和管理他们的服务级别协议 (SLA) 和计费。Amazon Redshift 可以帮助您降低硬件和软件成本。



**Section 3 key takeaways**

总而言之，Amazon Redshift 是一种快速、完全托管的数据仓库服务。随着业务的增长，您可以通过添加更多节点轻松扩展，而无需停机。Amazon Redshift 会自动将节点添加到您的集群并重新分配数据以实现最佳性能。

AmazonRedshift 旨在持续提供高性能。Amazon Redshift 使用列式存储和大规模并行处理架构。这些功能可在多个节点上并行处理和分发数据和查询。AmazonRedshift 还会自动监控您的集群并备份您的数据，以便您在需要时轻松恢复。加密是内置的 — 您只需启用它即可。



### Section 4: Amazon Aurora

![屏幕截图 2024-11-14 110325](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-14 110325.jpg)

Amazon Aurora 是与 MySQL 和 PostgreSQL 兼容的关系数据库，专为云而构建。它将高端商用数据库的性能和可用性与开源数据库的简单性和成本效益相结合。使用 Amazon Aurora 可以降低数据库成本，同时提高数据库的可靠性和可用性。作为一项完全托管的服务，Aurora 旨在自动执行耗时的任务，例如配置、修补、备份、恢复、故障检测和修复。

![屏幕截图 2024-11-14 110349](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-14 110349.jpg)

本幻灯片介绍了 Amazon Aurora 的一些优势。它具有高可用性，并提供快速的分布式存储子系统。Amazon Aurora 易于设置并使用 SQL 查询。它旨在与 MySQL 和 PostgreSQL 数据库引擎实现直接兼容，因此您几乎无需更改即可使用大多数现有数据库工具。

Amazon Aurora 是一种按使用量付费的服务，这意味着您只需为使用的服务和功能付费。它是一种托管服务，集成了 AWSDatabase Migration Service (AWS DMS) 和 AWS Schema Conversion Tool 等功能。这些功能旨在帮助您将数据集迁移到 Amazon Aurora。

![屏幕截图 2024-11-14 110435](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-14 110435.jpg)

为什么您可能会选择 Amazon Aurora，而不是其他选项（例如 SQL 与 Amazon RDS）？该决定主要涉及 Amazon Aurora 提供的高可用性和弹性设计。

Amazon Aurora 的设计目标是高可用性：它会在多个可用区中存储数据的多个副本，并持续备份到 Amazon S3。AmazonAurora 最多可以使用 15 个只读副本，以降低丢失数据的可能性。此外，如果您的主数据库出现问题，Amazon Aurora 还可以实现即时崩溃恢复。

![屏幕截图 2024-11-14 110524](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-14 110524.jpg)

数据库崩溃后，Amazon Aurora 无需从最后一个数据库检查点重播重做日志。相反，它会在每次读取操作时执行此操作。在大多数情况下，这会将数据库崩溃后的重启时间缩短至 60 秒以内。

使用 Amazon Aurora，缓冲区缓存会移出数据库进程，这样一来，数据库进程在重启时即可立即使用。这样就无需限制访问，直到重新填充缓存以避免断电。



**Section 4 key takeaways**

总而言之，Amazon Aurora 是一种高可用性、高性能且经济高效的托管关系数据库。

Aurora 提供分布式高性能存储子系统。使用 Amazon Aurora 可以降低数据库成本，同时提高数据库的可靠性。

Aurora 还具有高可用性。它具有为云构建的容错和自我修复存储。Aurora 会在多个可用区中复制数据的多个副本，并持续将数据备份到 Amazon S3。

提供多种级别的安全性，包括使用 Amazon VPC 进行网络隔离；使用通过 AWS Key Management Service (AWS KMS) 创建和控制的密钥进行静态加密；以及使用安全套接字层 (SSL) 进行传输中的数据加密。

Amazon Aurora 数据库引擎与现有的 MySQL 和 PostgreSQL 开源数据库兼容，并定期增加对新版本的兼容性。

最后，Amazon Aurora 完全由 Amazon RDS 管理。Aurora 可自动执行数据库管理任务，例如硬件配置、软件修补、设置、配置或备份。



![屏幕截图 2024-11-14 110857](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-14 110857.jpg)

正如您在本模块中看到的，云继续降低存储和计算成本。新一代应用程序已经出现，这对数据库提出了一系列新要求。这些应用程序需要数据库来存储 TB 到 PB 级的新类型数据、以毫秒级延迟提供对数据的访问、每秒处理数百万个请求以及扩展以支持世界各地的数百万用户。为了满足这些要求，您需要专门为满足应用程序的特定需求而构建的关系数据库和非关系数据库。AWS 提供了为您的特定应用程序用例构建的各种数据库。

### Module 8 Knowledge Check

**1.You are designing an ecommerce web application that will scale to hundreds of thousands of concurrent users. Which database technology is best suited to hold the session state in this example?**

A.Amazon Relational Database Service (Amazon RDS)
B.Amazon DynamoDB
C.Amazon Redshift
D.Amazon Simple Storage Service (Amazon S3)



**2.You need to find an item in an Amazon DynamoDB table using an attribute other than the item's primary key. Which of the following operations should you use? (Select the best answer.)**

A.Putltem
B.Scan
C.Query
D.Getltem



**3.In Amazon DynamoDB, what does the query operation enable you to do? (Select the best answer.)**

A.Query a table using the partition key and an optional sort key filter
B.Query any secondary indexes that exist for a table
C.Efficiently retrieve items from a table or secondary index
D.All of the above



**4.Which AWS Cloud service is best suited for analyzing your data by using standard structured query language (SQL) and your existing business intelligence (BI) tools? (Select the best answer.)**

A.Amazon Relational Database Service (Amazon RDS)
B.Amazon Simple Storage Service Glacier
C.Amazon DynamoDB
D.Amazon Redshift



**5.In Amazon DynamoDB, an attribute is.(Select the best answer.)**

A.a fundamental data element
B.a collection of items
C.a collection of attributes



**6.If you are developing an application that requires a database with extremely fast performance, fast scalability, and flexibility in the database schema, which service should you consider?  (Select the best answer.)** 

A.Amazon Relational Database Service (Amazon RDS)
B.Amazon ElastiCache
C.Amazon DynamoDB
D.Amazon Redshift



**7.Which of the following use cases is appropriate for using Amazon Relational Database Service (Amazon RDS)? (Select the best answer.)**

A.Massive read/write rates
B.Simple GET or PUT requests
C.Complex transactions
D.All of the above



**8.A company has an application, which consists of a .NET layer that connects to a MySQL database. They want to move this application on to AWS and use AWS features such as high availability and automated backups. Which of the following would be an ideal database for this use case? (Select the best answer)**

A.Amazon DynamoDB
B.Amazon Aurora
C.Amazon Redshift
D.Amazon RDS



**9.True or false? Amazon RDS automatically patches the database software and backs upyour database, storing the backups for a user-defined retention period and enabling point-in-time recovery.**

True
False



**10.What should you consider when choosing a database type? (Select the best answer.)**
A.Data size
B.Data access period
C.Query frequency
D.Highly available
E.All of the above



**Answer**:

1.B
2.B 
To find an item in a DynamoDB table other than the item's primary key, you would use the scan operation.
3.D
4.D
5.A
6.C
If you are developing an application that requires a database with extremely fast performance, fast scalability, and flexibility in the database schema, consider Amazon DynamoDB.

7.C
8.B
9.TRUE
10.E





## Module 10: Automatic Scaling and Monitoring

本模块将讨论以下主题：

- Elastic Load Balancing
- Amazon CloudWatch
- Amazon EC2 Auto Scaling

该模块还包括两项活动。一项活动将要求您指出 Elastic Load Balancing 用例。另一项活动将要求您识别 Amazon CloudWatch 示例。

该模块还包括一个实践实验室，您将在其中结合使用 Amazon EC2 Auto Scaling、Elastic Load Balancing 和 Amazon CloudWatch 来创建动态可扩展的架构。

最后，您将被要求完成知识测试，以测试您对本模块中涵盖的关键概念的理解。



完成本模块后，您应该能够：
- 指出如何使用 Elastic Load Balancing 在 Amazon Elastic Compute Cloud (Amazon EC2) 实例之间分配流量
- 确定 Amazon CloudWatch 如何让您实时监控 AWS 资源和应用程序
- 解释 Amazon EC2 Auto Scaling 如何根据工作负载变化启动和发布服务器
- 执行扩展和负载平衡任务以改进架构



### Section 1: Elastic Load  Balancing

![屏幕截图 2024-11-14 161956](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-14 161956.jpg)

现代高流量网站必须处理来自用户或客户端的数十万甚至数百万个并发请求，然后以快速可靠的方式返回正确的文本、图像、视频或应用程序数据。通常需要额外的服务器来满足这些高流量

Elastic Load Balancing 是一项 AWS 服务，可在单个可用区或多个可用区中跨多个目标（例如 Amazon Elastic Compute Cloud (Amazon EC2) 实例、容器、互联网协议 (IP) 地址和 Lambda 函数）分配传入的应用程序或网络流量。Elastic Load Balancing 会随着应用程序流量随时间变化而扩展您的负载均衡器。它可以自动扩展到大多数工作负载。

![屏幕截图 2024-11-14 162226](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-14 162226.jpg)

Elastic Load Balancing 有三种类型：

- 应用程序负载均衡器在应用程序级别（开放系统互连，即 OSI，模型第 7 层）运行。它根据请求的内容将流量路由到目标 — Amazon Elastic Compute Cloud (Amazon EC2) 实例、容器、Internet 协议 (IP) 地址和 Lambda 函数。它是超文本传输协议 (HTTP) 和安全 HTTP (HTTPS) 流量的高级负载平衡的理想选择。应用程序负载均衡器提供高级请求路由，旨在交付现代应用程序架构，包括微服务和基于容器的应用程序。应用程序负载均衡器通过确保始终使用最新的安全套接字层/传输层安全性 (SSL/TLS) 密码和协议来简化和提高应用程序的安全性。
- 网络负载均衡器在网络传输层（OSI 模型第 4 层）运行，根据 IP 协议数据将连接路由到目标（EC2 实例、微服务和容器）。它非常适合对传输控制协议 (TCP) 和用户数据报协议 (UDP) 流量进行负载平衡。网络负载均衡器能够每秒处理数百万个请求，同时保持超低延迟。网络负载均衡器经过优化，可处理突发和不稳定的网络流量模式。
- Classic Load Balancer 提供跨多个 EC2 实例的基本负载平衡，并在应用程序级别和网络传输级别运行。Classic Load Balancer 支持使用 HTTP、HTTPS、TCP 和 SSL 的应用程序的负载平衡。Classic Load Balancer 是一种较旧的实现。如果可能，AWS 建议您使用专用的应用程序负载均衡器或网络负载均衡器。

![屏幕截图 2024-11-14 162510](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-14 162510.jpg)

负载均衡器接受来自客户端的传入流量，并将请求路由到一个或多个可用区域中的注册目标（例如 EC2 实例）。

您可以通过指定一个或多个侦听器来配置负载均衡器以接受传入流量。侦听器是一个检查连接请求的过程。它配置了从客户端到负载均衡器的连接的协议和端口号。同样，它配置了从负载均衡器到目标的连接的协议和端口号。

您还可以配置负载均衡器以执行运行状况检查，这些检查用于监控已注册目标的运行状况，以便负载均衡器仅向运行状况良好的实例发送请求。当负载均衡器检测到运行状况不佳的目标时，它会停止将流量路由到该目标。然后，当它检测到目标再次运行正常时，它会恢复将流量路由到该目标。

负载均衡器类型的配置方式存在一个关键差异。使用应用程序负载均衡器和网络负载均衡器，您可以在目标组中注册目标，并将流量路由到目标组。使用传统负载均衡器，您可以向负载均衡器注册实例。

![屏幕截图 2024-11-14 162720](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-14 162720.jpg)

使用负载均衡器的原因有很多：

- 为您的应用程序实现高可用性和更好的容错能力——Elastic Load Balancing 可在多个可用区的健康目标之间平衡流量。如果单个可用区中的一个或多个目标运行不正常，Elastic Load Balancing 会将流量路由到其他可用区中的健康目标。当目标恢复健康状态后，负载平衡将自动恢复到这些目标的流量。
- 自动对容器化应用程序进行负载均衡– 借助对 Elastic Load Balancing 的增强容器支持，您现在可以在同一 EC2 实例上的多个端口之间进行负载均衡。您还可以利用与 Amazon Elastic Container Service (Amazon ECS) 的深度集成，它提供了完全托管的容器产品。您只需向负载均衡器注册服务，Amazon ECS 就会透明地管理 Docker 容器的注册和取消注册。负载均衡器会自动检测端口并动态地重新配置自身。
- 自动扩展您的应用程序 – Elastic Load Balancing 与 Amazon CloudWatch 和 Amazon EC2 Auto Scaling 配合使用，帮助您根据客户需求扩展应用程序。当任何一个 EC2 实例的延迟超过预配置阈值时，Amazon CloudWatch 警报可以触发 EC2 实例队列的自动扩展。然后，Amazon EC2 Auto Scaling 会预置新实例，您的应用程序将准备好满足下一个客户请求。负载均衡器将注册 EC2 实例并根据需要将流量引导至该实例。
- 在您的虚拟私有云 (VPC) 中使用 Elastic Load Balancing – 您可以使用 Elastic Load Balancing 创建 VPC 的公共入口点，或者在 VPC 内的应用程序层之间路由请求流量。您可以将安全组分配给负载均衡器，以控制哪些端口对允许的源列表开放。由于 Elastic Load Balancing 与您的 VPC 配合使用，因此您现有的所有网络访问控制列表 (网络 ACL) 和路由表将继续提供额外的网络控制。在 VPC 中创建负载均衡器时，您可以指定负载均衡器是公共 (默认) 还是内部。如果选择内部，则无需使用互联网网关即可访问负载均衡器，并且负载均衡器的私有 IP 地址将用于负载均衡器的域名系统 (DNS) 记录中。
- 启用混合负载平衡– Elastic Load Balancing 可让您使用同一负载平衡器在 AWS 和本地资源之间进行负载平衡。例如，如果您必须在 AWS 和本地资源之间分配应用程序流量，则可以将所有资源注册到同一目标组，并将目标组与负载平衡器关联。或者，您可以使用基于 DNS 的加权负载平衡在 AWS 和本地资源之间进行，方法是使用两个负载平衡器，其中一个负载平衡器用于 AWS，另一个负载平衡器用于本地资源。您还可以使用混合负载平衡来使单独的应用程序受益，其中一个应用程序位于 VPC 中，另一个应用程序位于本地位置。将 VPC 目标放在一个目标组中，将本地目标放在另一个目标组中，然后使用基于内容的路由将流量路由到每个目标组。
- 通过 HTTP(S) 调用 Lambda 函数 – Elastic Load Balancing 支持调用 Lambda 函数来处理 HTTP(S) 请求。这使用户能够从任何 HTTP 客户端（包括 Web 浏览器）访问无服务器应用程序。您可以将 Lambda 函数注册为目标，并使用 Application Load Balancer 中对基于内容的路由规则的支持将请求路由到不同的 Lambda 函数。您可以将 Application Load Balancer 用作使用服务器和无服务器计算的应用程序的通用 HTTP 终端节点。您可以使用 Lambda 函数构建整个网站，也可以组合 EC2 实例、容器、本地服务器和 Lambda 函数来构建应用程序。

![屏幕截图 2024-11-14 163833](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-14 163833.jpg)

对于此活动，请命名您将在给定场景中使用的负载均衡器。

![屏幕截图 2024-11-14 163901](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-14 163901.jpg)

答案已经揭晓



![屏幕截图 2024-11-14 163932](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-14 163932.jpg)

您可以使用以下功能来监控负载均衡器、分析流量模式以及解决负载均衡器和目标的问题：

- Amazon CloudWatch 指标 – Elastic Load Balancing 将负载均衡器和目标的数据点发布到 Amazon CloudWatch。CloudWatch 允许您以一组有序的时间序列数据（称为指标）的形式检索有关这些数据点的统计数据。您可以使用指标来验证系统是否按预期运行。例如，您可以创建 CloudWatch 警报来监控指定的指标，并在指标超出您认为的可接受范围时启动操作（例如向电子邮件地址发送通知）。
- 访问日志–您可以使用访问日志捕获有关对负载均衡器发出的请求的详细信息，并将其作为日志文件存储在 Amazon Simple Storage Service (Amazon S3) 中。您可以使用这些访问日志来分析流量模式并解决目标或后端应用程序的问题。
- AWS CloudTrail 日志 – 您可以使用 AWS CloudTrail 捕获有关对 Elastic Load Balancing 应用程序编程接口 (API) 进行的调用的详细信息，并将其作为日志文件存储在 Amazon S3 中。您可以使用这些 CloudTrail 日志确定谁进行了调用、进行了哪些调用、调用的时间、调用的源 IP 地址等等。

**Section 1 key takeaways**

本模块此部分的一些关键要点包括：

- Elastic Load Balancing 在一个或多个可用区域内的多个目标（例如 Amazon EC2 实例、容器、IP 地址和 Lambda 函数）之间分配传入的应用程序或网络流量。
- Elastic Load Balancing 支持三种类型的负载均衡器：
  - Application Load Balancer 应用程序负载均衡器
  - Network Load Balancer 网络负载均衡器
  - Classic Load Balancer 传统负载均衡器
- Elastic Load Balancing 提供多种监控工具，用于持续监控和日志记录以供审计和分析。



### Section 2: Amazon CloudWatch

要高效地使用 AWS，您需要了解您的 AWS 资源。

例如，您可能想知道：

-  何时应启动更多 Amazon EC2 实例？
-  应用程序的性能或可用性是否因容量不足而受到影响？
-  您的基础设施实际使用了多少？

您如何获取这些信息？

![屏幕截图 2024-11-14 164413](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-14 164413.jpg)

您可以使用 Amazon CloudWatch 捕获此信息。

Amazon CloudWatch 是一项监控和可观测性服务，专为 DevOps 工程师、开发人员、站点可靠性工程师 (SRE) 和 IT 经理打造。CloudWatch 可实时监控您的 AWS 资源（以及您在 AWS 上运行的应用程序）。您可以使用 CloudWatch 收集和跟踪指标，这些指标是您可以衡量的资源和应用程序的变量。

您可以创建警报来监控账户中的任何 Amazon CloudWatch 指标，并使用警报自动向 Amazon Simple Notification Service (Amazon SNS) 主题发送通知或执行 Amazon EC2 Auto Scaling 或 Amazon EC2 操作。例如，您可以针对 EC2 实例的 CPU 利用率、Elastic Load Balancing 请求延迟、Amazon DynamoDB 表吞吐量、Amazon Simple Queue Service (Amazon SQS) 队列长度甚至 AWS 账单上的费用创建警报。您还可以针对特定于您的自定义应用程序或基础设施的自定义指标创建警报。

您还可以使用 Amazon CloudWatch Events 定义与传入事件（或 AWS 环境中的更改）匹配的规则，并将其路由到目标进行处理。目标可以包括 Amazon EC2 实例、AWS Lambda 函数、Kinesis 流、Amazon ECS 任务、Step Functions 状态机、Amazon SNS 主题、Amazon SQS 队列和内置目标。CloudWatch Events 会在发生操作更改时感知到这些更改。CloudWatch Events 会响应这些操作更改并根据需要采取纠正措施，方法是发送消息以响应环境、激活函数、进行更改和捕获状态信息。

借助 CloudWatch，您可以全面了解资源利用率、应用程序性能和运行状况。无需预付承诺或最低费用；您只需按实际使用量付费。我们会在月底向您收取实际使用量的费用。

![屏幕截图 2024-11-14 164740](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-14 164740.jpg)

您可以创建 CloudWatch 警报来监控单个 CloudWatch 指标或基于 CloudWatch 指标的数学表达式的结果。您可以基于静态阈值、异常检测或指标数学表达式创建 CloudWatch 警报。

当您根据静态阈值创建警报时，您可以选择要监视的 CloudWatch 指标以及该指标的阈值。当指标在指定的评估期内超出阈值时，警报将进入 ALARM 状态。

对于基于静态阈值的警报，您必须指定：

- 命名空间—命名空间包含您想要的 CloudWatch 指标，例如 AWS/EC2。
- 指标—指标是您想要测量的变量，例如 CPU 利用率。
- 统计数据—统计数据可以是平均值、总和、最小值、最大值、样本数、预定义百分位数或自定义百分位数。
- 周期—周期是警报的评估期。评估警报时，每个周期都会聚合为一个数据点。
- 条件 - 指定静态阈值的条件时，您可以指定指标大于、大于或等于、小于或等于或低于阈值的情况，还可以指定阈值。
- 其他配置信息 - 这包括评估期内必须违反多少个数据点才能触发警报，以及 CloudWatch 在评估警报时应如何处理缺失数据。
- 操作 - 您可以选择向 Amazon SNS 主题发送通知，或者执行 Amazon EC2 Auto Scaling 操作或 Amazon EC2 操作。

![屏幕截图 2024-11-14 164850](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-14 164850.jpg)

对于此活动，看看您是否可以确定哪些是正确的 CloudWatch 警报。对于不正确的警报，看看您是否可以确定错误。

![屏幕截图 2024-11-14 164920](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-14 164920.jpg)



**Section 2 key takeaways**

本模块此部分的一些关键要点包括：

- Amazon CloudWatch 可帮助您实时监控您的 AWS 资源以及您在 AWS 上运行的应用程序。
- CloudWatch 可让您 –
  - 收集并跟踪标准和自定义指标。
  - 设置警报以自动向 SNS 主题发送通知，或根据指标或表达式在多个时间段内相对于阈值的值执行 Amazon EC2 Auto Scaling 或 Amazon EC2 操作。
  - 定义与 AWS 环境中的变化相匹配的规则，并将这些事件路由到目标进行处理。

### Section 3: Amazon EC2 Auto Scaling

在 AWS 上运行应用程序时，您需要确保您的架构能够扩展以应对需求变化。在本节中，您将了解如何使用 Amazon EC2 Auto Scaling 自动扩展您的 EC2 实例。

![屏幕截图 2024-11-14 165155](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-14 165155.jpg)

Scaling (扩展)是指增加或减少应用程序的计算容量的能力。要了解扩展为何如此重要，请考虑这个具有不同资源需求的工作负载示例。在此示例中，星期三需要的资源容量最多，而星期日需要的资源容量最少。

一种选择是分配足够多的容量，以便始终满足最高需求（在本例中为周三）。但是，这种情况意味着您运行的资源在一周中的大多数日子都未得到充分利用。使用此选项，您的成本不会得到优化。

另一种选择是分配较少的容量以降低成本。这种情况意味着您在某些日子容量不足。如果您不解决容量问题，您的应用程序可能会表现不佳，甚至可能无法供用户使用。

![屏幕截图 2024-11-14 165256](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-14 165256.jpg)

在云中，由于计算能力是一种程序化资源，因此您可以采用灵活的方法进行扩展。Amazon EC2 Auto Scaling 是一项 AWS 服务，可帮助您维护应用程序可用性，并使您能够根据定义的条件自动添加或删除 EC2 实例。您可以使用 EC2 Auto Scaling 的队列管理功能来维护队列的运行状况和可用性。

Amazon EC2 Auto Scaling 提供了多种方法来调整扩展，以最好地满足您的应用程序需求。您可以手动、按计划、响应不断变化的需求或与 AWS Auto Scaling 结合使用以进行预测性扩展来添加或删除 EC2 实例。动态扩展和预测性扩展可以一起使用以更快地进行扩展。

![屏幕截图 2024-11-14 165334](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-14 165334.jpg)

自动扩展对于可预测的工作负载很有用 - 例如零售公司 Amazon.com 的每周流量。

![屏幕截图 2024-11-14 165403](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-14 165403.jpg)

自动扩展对于动态按需扩展也很有用。亚马逊在 11 月会经历季节性流量高峰（黑色星期五和网络星期一，即 11 月底美国零售商举行大型促销活动的日子）。如果亚马逊提供固定容量来满足最高使用率，则一年中大部分时间 76% 的资源处于闲置状态。容量扩展对于支持不断变化的服务需求是必不可少的。如果不进行扩展，服务器可能会因饱和而崩溃，企业将失去客户信心。

![屏幕截图 2024-11-14 165435](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-14 165435.jpg)

Auto Scaling 组是 Amazon EC2 实例的集合，这些实例被视为逻辑分组，以便自动扩展和管理。Auto Scaling 组的大小取决于您设置为所需容量的实例数。您可以手动或使用自动扩展来调整其大小以满足需求。

有关 Auto Scaling Groups 的更多信息，请参阅 https://docs.aws.amazon.com/autoscaling/ec2/userguide/auto-scaling-groups.html。

您可以指定每个 Auto Scaling 组中的最小实例数，Amazon EC2 Auto Scaling 旨在防止您的组低于此大小。您可以指定每个 Auto Scaling 组中的最大实例数，Amazon EC2 Auto Scaling 旨在防止您的组高于此大小。如果您在创建组时或之后的任何时间指定所需的容量，Amazon EC2 Auto Scaling 旨在调整您的组的大小，使其具有指定的实例数。如果您指定扩展策略，则 Amazon EC2 Auto Scaling 可以根据应用程序需求的增加或减少来启动或终止实例。

例如，此 Auto Scaling 组的最小大小为 1 个实例，所需容量为 2 个实例，最大大小为 4 个实例。您定义的扩展策略会根据您指定的条件在最小和最大实例数范围内调整实例数。



![屏幕截图 2024-11-14 165600](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-14 165600.jpg)

使用 Amazon EC2 Auto Scaling，启动实例称为扩展，终止实例称为缩减。

![屏幕截图 2024-11-14 165632](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-14 165632.jpg)

要启动 EC2 实例，Auto Scaling 组需要使用启动配置，即实例配置模板。您可以将启动配置视为您要扩展的内容。创建启动配置时，您需要指定实例的信息。您指定的信息包括 Amazon 系统映像 (AMI) 的 ID、实例类型、AWS 身份和访问管理 (IAM) 角色、额外存储、一个或多个安全组以及任何 Amazon Elastic Block Store (Amazon EBS) 卷。

有关启动配置的更多信息，请参阅https://docs.aws.amazon.com/autoscaling/ec2/userguide/launch-configurations.html。

您可以定义 Auto Scaling 组的最小和最大实例数以及所需容量。然后，将其启动到 VPC 内的子网中（您可以将其视为要扩展的位置）。Amazon EC2 Auto Scaling 与 Elastic Load Balancing 集成，使您可以将一个或多个负载均衡器附加到现有的 Auto Scaling 组。附加负载均衡器后，它会自动在组中注册实例并在实例之间分配传入流量。

最后，您可以指定扩展事件发生的时间。您有许多扩展选项：

- 始终保持当前实例级别 – 您可以配置 Auto Scaling 组以始终保持指定数量的正在运行的实例。为了保持当前实例级别，Amazon EC2 Auto Scaling 会对 Auto Scaling 组中正在运行的实例执行定期运行状况检查。当 Amazon EC2 Auto Scaling 发现运行状况不佳的实例时，它会终止该实例并启动一个新实例。
- 手动扩展 – 使用手动扩展，您只需指定 Auto Scaling 组的最大、最小或所需容量的变化。有关手动扩展的更多信息，请参阅 https://docs.aws.amazon.com/autoscaling/ec2/userguide/as-manual-scaling.html。
- 计划扩展 – 使用计划扩展，扩展操作将根据日期和时间自动执行。当您确切知道何时增加或减少组中的实例数量时，这对于可预测的工作负载非常有用。例如，假设每周，您的 Web 应用程序的流量在星期三开始增加，在星期四保持高位，并在星期五开始减少。有关计划扩展的更多信息，请参阅 https://docs.aws.amazon.com/autoscaling/ec2/userguide/ec2-auto-scaling-scheduled-scaling.html。您可以根据 Web 应用程序的可预测流量模式规划扩展操作。要实施计划扩展，您需要创建计划操作。
- 扩展资源的更高级方法使您能够定义控制扩展过程的参数。例如，您有一个当前在两个实例上运行的 Web 应用程序，并且您希望 Auto Scaling 组的 CPU 利用率在应用程序负载发生变化时保持接近 50%。当您不知道这些条件何时会发生变化时，此选项对于根据不断变化的条件进行扩展非常有用。动态扩展为您提供了额外的容量来处理流量高峰，而无需维护过多的闲置资源。您可以将 Auto Scaling 组配置为自动扩展以满足此需求。有关动态扩展的更多信息，请访问 https://docs.aws.amazon.com/autoscaling/ec2/userguide/as-scale-based-on-demand.html。扩展策略类型决定了如何执行扩展操作。您可以将 Amazon EC2 Auto Scaling 与 Amazon CloudWatch 结合使用，以触发扩展策略来响应警报。请参阅 https://docs.aws.amazon.com/autoscaling/ec2/userguide/as-scale-based-on-demand.html#as-scaling-types 中的策略类型。
- 预测扩展 - 您可以将 Amazon EC2 Auto Scaling 与 AWS Auto Scaling 结合使用来实现预测扩展，其中您的容量根据预测需求进行扩展。预测扩展使用从您的实际 EC2 使用情况中收集的数据，并且这些数据由从我们自己的观察中提取的数十亿个数据点进一步提供信息。然后，AWS 使用训练有素的机器学习模型来预测您的预期流量（和 EC2 使用情况），包括每日和每周模式。该模型需要至少 1 天的历史数据才能开始进行预测。每 24 小时重新评估一次以创建未来 48 小时的预测。预测过程会生成一个扩展计划，该计划可以驱动一组或多组自动扩展的 EC2 实例。
  https://aws.amazon.com/blogs/aws/new-predictive-scaling-for-ec2-powered-by-machine-learning/

![屏幕截图 2024-11-14 165941](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-14 165941.jpg)

**Implementing Dynamic scaling(实现动态扩展)** 的一个常见配置是创建基于 EC2 实例或负载均衡器性能信息的 CloudWatch 警报。当超出性能阈值时，CloudWatch 警报会触发自动扩展事件，该事件会扩展或缩减 Auto Scaling 组中的 EC2 实例。

要了解其工作原理，请考虑以下示例：

- 您创建一个 Amazon CloudWatch 警报来监控整个 EC2 实例队列的 CPU 利用率，并在队列的平均 CPU 利用率超过 60% 持续 5 分钟时运行自动扩展策略。
- AmazonEC2Auto Scaling 根据您创建的启动配置将新的 EC2 实例实例化到您的 Auto Scaling 组中。
- 添加新实例后，Amazon EC2Auto Scaling 会调用 Elastic Load Balancing 以在该 Auto Scaling 组中注册新的 EC2 实例。
- 然后，Elastic Load Balancing 执行所需的运行状况检查并开始将流量分发到该实例。Elastic Load Balancing 在 EC2 实例之间路由流量并将指标提供给 Amazon CloudWatch。

Amazon CloudWatch、Amazon EC2 Auto Scaling 和 Elastic Load Balancing 单独使用效果很好。但是，它们结合起来会变得更加强大，并可以提高应用程序处理客户需求时的控制力和灵活性。

![屏幕截图 2024-11-14 170552](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-14 170552.jpg)

到目前为止，您了解了如何使用 Amazon EC2 Auto Scaling 扩展 EC2 实例。您还了解到，您可以将 Amazon EC2 Auto Scaling 与 AWS Auto Scaling 结合使用来执行预测性扩展。

AWS Auto Scaling 是一项单独的服务，用于监控您的应用程序。它会自动调整容量，以尽可能低的成本保持稳定、可预测的性能。该服务提供了一个简单而强大的用户界面，使您能够为资源构建扩展计划，包括：

- Amazon EC2 实例和 Spot 队列
- Amazon Elastic Container Service (Amazon ECS) 任务
- Amazon DynamoDB 表和索引
- Amazon Aurora 副本

如果您已经在使用 Amazon EC2 Auto Scaling 动态扩展您的 EC2 实例，那么您现在可以将其与 AWS Auto Scaling 一起使用来扩展其他 AWS 服务的额外资源。



**Section 3 key takeaways**

本模块此部分的一些关键要点包括：

- 扩展使您能够快速响应资源需求的变化。
- Amazon EC2 Auto Scaling 可帮助您维护应用程序可用性，并使您能够根据工作负载自动添加或删除 EC2 实例。
- Auto Scaling 组是 EC2 实例的集合。
- 启动配置是实例配置模板。
- 您可以使用 Amazon EC2 Auto Scaling、Amazon CloudWatch 和 Elastic Load Balancing 实现动态扩展。

AWS Auto Scaling 是一项单独的服务，可监控您的应用程序并自动调整以下资源的容量：

- Amazon EC2 实例和 Spot 队列
- Amazon ECS 任务
- Amazon DynamoDB 表和索引
- Amazon Aurora 副本



**Module summary**    

总之，在本模块中，您学习了如何：

-  指出如何使用 Elastic Load Balancing 在 Amazon Elastic Compute Cloud (Amazon EC2) 实例之间分配流量。
- 确定 Amazon CloudWatch 如何使您能够实时监控 AWS 资源和应用程序
-  解释 Amazon EC2 Auto Scaling 如何启动和发布服务器以响应工作负载变化。
- 执行扩展和负载平衡任务以改进架构。



### Module 8 Knowledge Check

**1.Which of the following AWS tools help your application scale up or down based on demand? (Choose two.)**

A.Availability Zones
B.Amazon EC2 Auto Scaling
C.AWS CloudFormation
D.Elastic Load Balancing
E.AWS Config



**2.Which service would you use to send alerts based on Amazon CloudWatch alarms?d (Select the best answer.)**

A.Amazon Simple Notification Service (Amazon SNS)
B.AWS CloudTrail
C.AWS Trusted Advisor
D.Amazon Route 53



**3.Which of the following are characteristics of Amazon EC2 Auto Scaling? (Choose three.)**

A.Only supports dynamic scaling
B.Responds to changing conditions by adding or terminating instances
C.Delivers push notifications
D.Launches instances from a specified Amazon Machine Image (AMI)
E.Enforces a minimum number of running Amazon EC2 instances



**4.Which of the following must be configured on an Elastic Load Balancing load balancer to expect incoming traffic? (Select the best answer.)**

A.A port
B.A network interface
C.A listener
D.An instance



**5.Which of the following elements are used to create an Amazon EC2 Auto Scaling launch configuration?  (Choose three.)** 

A.Amazon Machine Image (AMI)
B.Load balancer
C.Instance type
D.Virtual private cloud (VPC) and subnets
E.Amazon Elastic Block Store (Amazon EBS) volumes



**6.Which of the following services can help you collect important metrics from Amazon Relational Database Service (Amazon RDS) and Amazon Elastic Compute Cloud (Amazon EC2) instances? (Select the best answer.)**

A.Amazon CloudFront
B.Amazon CloudSearch
C.Amazon CloudWatch
D.AWS CloudTrail
E.Amazon EC2 Auto Scaling



**7.Which of the following are elements of an Auto Scaling group? (Choose three.)**

A.Minimum size
B.Health checks
C.Desired capacity
D.Maximum size



**8.There is an audit at your company and they need to have a log of all access to AWS resources in the account. Which of the following services can assist in providing these details? (Select the best answer.)**

A.Amazon Cloud Watch
B.AWS Cloud Trail
C.Amazon Elastic Compute Cloud (Amazon EC2)
D.Amazon Simple Notification Service (Amazon SNS)



**9.In Elastic Load Balancing, when the load balancer detects an unhealthy target, which of the following are true? (Choose three.)**

A.Stops routing traffic to that target
B.Triggers an alarm
C.Resumes routing traffic when it detects that the target is healthy again
D.Resumes routing traffic when manually restarted
E.Routes traffic to a healthy target



**10.What are the three types of load balancers that Elastic Load Balancing'offers?**

A.Internet Load Balancer
B.Application Load Balancer
C.Network Load Balancer
D.Compute Load Balancer
E.Classic Load Balancer
F.Auto Scaling Load Balancer



1.B D
2.A
3.B D E
4.C 

> You configure the load balancer to accept incoming traffic by specifying one or more listeners.

5.A C E 

> You specify the AMI, instance type, and EBS volumes when you create an Auto Scaling launch configuration.

6.C
7.A C D
8.C
9.A C E

> When the load balancer detects an unhealthy target, it stops routing traffic to that target and sends it to a healthy target. It then resumes routing traffic to that target when it detects that the target is healthy again.

10.B C E

> ELB offers three types of load balancers: Application Load Balancer, Network Load Balancer, and Classic Load Balancer.
