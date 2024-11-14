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

