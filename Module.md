## Module 1: Cloud Concepts Overview

本模块涉及以下主题：

- 云计算简介
- 云计算的优势
- 亚马逊网络服务 (AWS) 简介
- AWS 云采用框架 (AWS CAF)最后，您将被要求完成知识测试，该测试将用于测试您对本模块所涵盖的关键概念的理解。



完成本模块后，您应该能够：

- 定义不同类型的云计算
- 描述云计算的六个优势
- 识别主要的 AWS 服务类别和核心服务
- 查看 AWS 云采用框架 (AWS CAF)



### Section 1: Introduction to cloud computing

Cloud computing 是通过互联网按需提供计算能力、数据库、存储、应用程序和其他 IT 资源，采用按使用量付费的定价方式。这些资源在位于世界各地不同位置的大型数据中心的服务器计算机上运行。当您使用 AWS 等云服务提供商时，该服务提供商拥有您正在使用的计算机。这些资源可以像构建块一样一起使用，以构建有助于实现业务目标和满足技术要求的解决方案。



![屏幕截图 2024-11-16 201013](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-16 201013.jpg)

在传统的计算模型中，基础设施被视为硬件。硬件解决方案是物理的，这意味着它们需要空间、人员、物理安全、规划和资本支出。

除了大量的前期投资外，传统计算的另一个令人望而却步的方面是漫长的硬件采购周期，其中包括获取、配置和维护内部基础设施。

对于硬件解决方案，您必须询问是否有足够的资源容量或足够的存储空间来满足您的需求，并且您可以通过猜测理论上的最大峰值来配置容量。如果您没有达到预计的最大峰值，那么您将为闲置的昂贵资源付费。如果超出预计的最大峰值，那么您就没有足够的容量来满足您的需求。如果您的需求发生变化，那么您必须花费实施新解决方案所需的时间、精力和金钱。

例如，如果你想要配置一个新网站，你需要购买硬件，将其安装到机架上，然后将其放在数据中心，然后管理它或让其他人来管理它。这种方法既昂贵又耗时。

![屏幕截图 2024-11-16 201124](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-16 201124.jpg)

相比之下，云计算使您可以将基础架构视为软件。软件解决方案非常灵活。您可以选择最符合您需求的云服务，按需配置和终止这些资源，并按使用量付费。您可以以自动化方式弹性地扩展和缩减资源。使用云计算模型，您可以将资源视为临时和可抛弃的。云计算提供的灵活性使企业能够快速实施新解决方案，并且前期成本较低。

与硬件解决方案相比，软件解决方案可以更快、更轻松地进行更改，并且更具成本效益。

云计算帮助开发人员和 IT 部门避免采购、维护和容量规划等无差别的工作，从而使他们能够专注于最重要的事情。

随着云计算的普及，出现了多种不同的服务模型和部署策略，以满足不同用户的特定需求。每种类型的云服务模型和部署策略都为您提供不同级别的控制、灵活性和管理。了解这些云服务模型和部署策略之间的差异可以帮助您确定哪组服务适合您的需求。

![屏幕截图 2024-11-16 201241](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-16 201241.jpg)



云服务模式主要有三种。每种模式代表云计算堆栈的不同部分，并为您提供不同级别的 IT 资源控制：

- **Infrastructure as a service 基础设施即服务 (IaaS)**：此类别中的服务是云 IT 的基本构建块，通常为您提供对网络功能、计算机（虚拟或专用硬件）和数据存储空间的访问。IaaS 为您提供对 IT 资源的最高级别的灵活性和管理控制。它与当今许多 IT 部门和开发人员熟悉的现有 IT 资源最为相似。
- **Platform as a service 平台即服务 (PaaS)**：此类别中的服务减少了您管理底层基础设施（通常是硬件和操作系统）的需要，使您能够专注于应用程序的部署和管理。
- **Software as a service 软件即服务 (SaaS)**：此类别的服务为您提供由服务提供商运行和管理的完整产品。在大多数情况下，软件即服务是指最终用户应用程序。使用 SaaS 产品，您不必考虑如何维护服务或如何管理底层基础设施。您只需考虑计划如何使用该特定软件。SaaS 应用程序的一个常见示例是基于 Web 的电子邮件，您可以在其中发送和接收电子邮件，而无需管理电子邮件产品的功能添加或维护运行电子邮件程序的服务器和操作系统。



![屏幕截图 2024-11-16 201440](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-16 201440.jpg)

云计算部署模型主要有三种，它们代表了您的应用程序可以部署到的云环境：

- **Cloud**：基于云的应用程序完全部署在云中，应用程序的所有部分都在云中运行。云中的应用程序要么是在云中创建的，要么是从现有基础设施迁移而来，以利用云计算的优势（请参阅 https://aws.amazon.com/what-is-cloud-computing/）。基于云的应用程序可以构建在低级基础设施上，也可以使用更高级别的服务，这些服务可以从核心基础设施的管理、架构和扩展要求中抽象出来。
- **Hybrid**：混合部署是一种将基于云的资源与不在云中的现有资源之间的基础架构和应用程序连接起来的方法。最常见的混合部署方法是在云和现有的本地基础架构之间进行。此模型使组织能够将其基础架构扩展并扩展到云中，同时将云资源连接到内部系统。
- **On-premises**：使用虚拟化和资源管理工具在本地部署资源有时被称为私有云。虽然本地部署无法提供云计算的许多优势，但有时人们会寻求它来提供专用资源。在大多数情况下，这种部署模型与传统 IT 基础设施相同，但它也可能使用应用程序管理和虚拟化技术来提高资源利用率。

![屏幕截图 2024-11-16 202151](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-16 202151.jpg)

AWS 与传统的本地 IT 领域有许多相似之处：

- AWS security groups、 network access control lists（network ACL）和 AWS Identity and Access Management (IAM) 类似于防火墙、访问控制列表 (ACL) 和管理员。
- Elastic Load Balancing 和 Amazon Virtual Private Cloud (Amazon VPC) 类似于路由器、网络管道和交换机。
- Amazon Machine Images (AMI) 和 Amazon Elastic Compute Cloud (Amazon EC2) 实例类似于本地服务器。
- Amazon Elastic Block Store (Amazon EBS)、Amazon Elastic File System (Amazon EFS)、Amazon Simple Storage Service (Amazon S3) 和 Amazon Relational Database Service (Amazon RDS) 类似于Direct attached storage (DAS)、storage area networks (SAN)、network attached storage (NAS) 和 relational database management service (RDBMS)。

借助 AWS 服务和功能，您几乎可以完成使用传统数据中心想要完成的所有工作。



**Section 1 key takeaways**

Some key takeaways from this section of the module include:

- 云计算是通过互联网按需交付 IT 资源，采用即用即付定价。
- 云计算使您可以将基础设施视为（并使用）软件。
- 有三种云服务模型：IaaS、PaaS 和 SaaS。
- 有三种云部署模型：云、混合和本地或私有云。
- 有许多 AWS 服务模拟传统的本地 IT 空间





### **Section 2: Advantages of cloud computing**

为什么这么多公司对迁移到云感兴趣？本节介绍云计算的六个优势。

**Advantage #1—Trade capital expense for variable expense 用可变费用取代资本支出**:
资本支出 (Capital expenses 亦称capex) 是公司用于购买、升级和维护实物资产（如房地产、工业建筑或设备）的资金。您还记得传统计算模型中的数据中心示例吗？您需要将硬件架起来并堆叠起来，然后管理所有硬件。无论您是否使用数据中心，您都必须支付所有费用。

相比之下，*variable expense* (可变费用)是承担费用的人可以轻松改变或避免的费用。您不必在知道如何使用数据中心和服务器之前就对其进行大量投资，而是只需在消耗资源时付费，并且只为消耗的量付费。因此，您可以节省技术成本。它还使您能够在几分钟内（而不是几周或几天）适应新的应用程序，并根据需要提供尽可能多的空间。维护工作减少了，因此您可以将更多精力放在业务的核心目标上。

![屏幕截图 2024-11-16 202740](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-16 202740.jpg)



**Advantage #2—Benefit from massive economies of scale (受益于大规模经济):** 

通过使用云计算，您可以实现比自己更低的可变成本。由于数十万客户的使用情况都汇总在云中，AWS 等提供商可以实现更高的规模经济，从而降低即用即付价格。

![屏幕截图 2024-11-16 202953](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-16 202953.jpg)

**Advantage #3—Stop guessing capacity ():** 

无需猜测您的基础设施容量需求。在部署应用程序之前做出容量决策时，您通常要么拥有昂贵的闲置资源，要么处理有限的容量。使用云计算，这些问题就消失了。您可以根据需要访问尽可能多的资源，并根据需要进行扩展和缩减，只需几分钟即可通知。

![屏幕截图 2024-11-16 203039](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-16 203039.jpg)

**Advantage #4—Increase speed and agility 提高速度和敏捷性:** 

在云计算环境中，只需单击一下即可获得新的 IT 资源，这意味着您可以将向开发人员提供这些资源所需的时间从几周缩短到几分钟。结果是组织的敏捷性显著提高，因为实验和开发所需的成本和时间显著降低.

![屏幕截图 2024-11-16 203143](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-16 203143.jpg)

**Advantage #5—Stop spending money on running and maintaining data centers(不再花钱运行和维护数据中心):** 

专注于使您的业务与众不同的项目，而不是专注于基础设施。云计算使您能够专注于自己的客户，而不是繁重的服务器架设、堆叠和供电工作。

![屏幕截图 2024-11-16 203230](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-16 203230.jpg)

**Advantage #6—Go global in minutes (优势 6 — 数分钟内实现全球化)：**

只需单击几下，您就可以在全球多个 AWS 区域部署您的应用程序。这样，您就可以以最低的成本为您的客户提供更低的延迟和更好的体验。

**Section 2 key takeaways**

本模块此部分的关键内容包括云计算的六大优势：

- 用可变费用取代资本费用
- 大规模经济
- 停止猜测容量
- 提高速度和灵活性
- 停止花钱运行和维护数据中心
- 几分钟内走向全球



### Section 3: Introduction to Amazon Web Services (AWS)

![屏幕截图 2024-11-16 203415](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-16 203415.jpg)

一般而言，Web 服务是任何可通过互联网或私有（内部网）网络访问的软件。Web 服务使用标准化格式（例如可扩展标记语言 (XML) 或 JavaScript 对象表示法 (JSON)）来请求和响应应用程序编程接口 (API) 交互。它不依赖于任何一种操作系统或编程语言。它通过接口定义文件进行自我描述，并且可被发现。

![屏幕截图 2024-11-16 203452](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-16 203452.jpg)

Amazon Web Services (AWS) 是一个安全的云平台，提供一系列全球云产品。由于这些产品是通过互联网交付的，因此您可以按需访问项目可能需要的计算、存储、网络、数据库和其他 IT 资源以及管理这些资源的工具。您可以立即配置和启动 AWS 资源。这些资源只需几分钟即可供您使用。

AWS 提供灵活性。您的 AWS 环境可以根据需求重新配置和更新，自动扩大或缩小以满足使用模式并优化支出，或者暂时或永久关闭。AWS 服务的计费将成为运营费用，而不是资本支出。

AWS 服务旨在协同工作，以支持几乎任何类型的应用程序或工作负载。您可以将这些服务视为构建块，快速组装它们以构建复杂、可扩展的解决方案，然后根据需求的变化进行调整。

![屏幕截图 2024-11-16 203548](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-16 203548.jpg)



AWS 服务分为不同的类别，每个类别包含一个或多个服务。您可以从这些不同的类别中选择所需的服务来构建解决方案。

![屏幕截图 2024-11-16 203614](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-16 203614.jpg)

例如，假设您正在构建一个数据库应用程序。您的客户可能会将数据发送到您的 Amazon Elastic Compute Cloud (Amazon EC2) 实例，这是计算类别中的一项服务。这些 EC2 服务器以一分钟为增量对数据进行批处理，并将每个客户的对象添加到您选择使用的 AWS 存储服务 Amazon Simple Storage Service (Amazon S3)。然后，您可以使用非关系数据库（如 Amazon DynamoDB）为您的应用程序提供支持，例如，构建索引，以便您可以找到在特定时间段内收集的给定客户的所有对象。您可能决定在 Amazon Virtual Private Cloud (Amazon VPC) 中运行这些服务，这是网络类别中的一项服务。

这个简单示例的目的是说明您可以从不同的类别中选择 Web 服务，并将它们一起使用来构建解决方案（在本例中为数据库应用程序）。当然，您构建的解决方案可能非常复杂。

![屏幕截图 2024-11-16 203936](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-16 203936.jpg)

您选择使用哪种服务取决于您的业务目标和技术要求。在您刚刚查看的示例中，该解决方案使用 Amazon EC2 作为计算服务。但是，这只是 AWS 提供的众多计算服务之一。以下是您可能选择用于以下示例用例的一些其他 AWS 计算产品：

- Amazon EC2 (https://aws.amazon.com/ec2/)：您希望完全控制您的 AWS 计算资源。
- AWS Lambda (https://aws.amazon.com/lambda/)：您希望运行代码而不是管理或配置服务器。
- AWS Elastic Beanstalk (https://aws.amazon.com/elasticbeanstalk/)：您需要一项为您部署、管理和扩展 Web 应用程序的服务。
- Amazon Lightsail (https://aws.amazon.com/lightsail/)：您需要一个用于简单 Web 应用程序的轻量级云平台。
- AWS Batch (https://aws.amazon.com/batch/)：您需要运行数十万个批处理工作负载。
- AWS Outposts (https://aws.amazon.com/outposts/)：您希望在本地数据中心运行 AWS 基础设施。
- Amazon Elastic Container Service (Amazon ECS) (https://aws.amazon.com/ecs/)
- Amazon Elastic Kubernetes Service (Amazon EKS) (https://aws.amazon.com/eks/)
- AWS Fargate(https://aws.amazon.com/fargate/)：您想要实现容器或微服务架构。
- VMware Cloud on AWS (https://aws.amazon.com/vmware/)：您有一个想要迁移到 AWS 的本地服务器虚拟化平台。

![屏幕截图 2024-11-16 210409](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-16 210409.jpg)

当您开始使用云时，AWS 服务的种类可能令人望而生畏。本课程重点介绍以下服务类别中的一些较常见的服务：计算、存储、数据库、网络和内容交付、安全、身份和合规性、管理和治理以及 AWS 成本管理。

图例：

- Amazon Elastic Block Store (Amazon EBS)
- Amazon Elastic Compute Cloud (Amazon EC2)
- Amazon Elastic Container Registry (Amazon ECR)•Amazon Elastic Container Service (Amazon ECS)
- Amazon Elastic File System (Amazon EFS)•Amazon Elastic Kubernetes Service (Amazon EKS)
- Amazon Relational Database Service (Amazon RDS)
- Amazon Simple Storage Service (Amazon S3)
- Amazon Virtual Private Cloud (Amazon VPC)
- AWS Identity and Access Management (IAM)
- AWS Key Management Service (AWS KMS)



您可能想知道如何访问 AWS 提供的广泛服务。有三种方法可以在 AWS 云上创建和管理资源：

- **AWS Management Console(AWS 管理控制台)**：控制台为 AWS 提供的大多数功能提供了丰富的图形界面。（注意：有时，新功能在首次启动时可能不会在控制台中包含其所有功能。）
- **AWS Command Line Interface AWS 命令行界面 (AWS CLI)**：AWS CLI 提供了一套实用程序，可以从 Linux、macOS 或 Microsoft Windows 中的命令脚本启动。
- **Software development kits  软件开发工具包 (SDK)**：AWS 提供了允许使用各种流行编程语言访问 AWS 的软件包。这让您可以轻松地在现有应用程序中使用 AWS，并且还使您能够创建完全通过代码部署和监控复杂系统的应用程序。

所有这三个选项均建立在作为 AWS 基础的通用 REST 类 API 上。

**Section 3 key takeaways**

本模块此部分的关键要点包括：

- AWS 是一个安全的云平台，提供一系列旨在协同工作的全球云产品（称为服务）。
- AWS 服务有很多类别，每个类别都有许多服务可供选择。
- 根据您的业务目标和技术要求选择服务。
- 有三种方法可以与 AWS 服务交互。



### Section 4: Moving to the AWS Cloud –The AWS Cloud Adoption Framework (AWS CAF)

正如您在本模块中到目前为止所学到的，云计算比传统模式具有许多优势。但是，对于大多数组织而言，云采用并非一蹴而就。技术是一回事，但组织也由人员和流程组成，这三个要素必须协调一致才能成功采用云。云计算在技术获取、使用和管理方式方面带来了重大转变。它还改变了组织预算和支付技术服务的方式。云采用要求在整个组织内讨论和考虑根本性变革。它还要求所有组织部门（IT 内部和外部）的利益相关者支持这些新变化。在最后一节中，您将了解 AWS CAF，它旨在帮助组织设计和走上成功采用云的快速之路。

![屏幕截图 2024-11-16 210811](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-16 210811.jpg)

每个组织的云采用历程都是独一无二的。但是，任何组织要想成功地将其 IT 产品组合迁移到云中，必须将三个要素（即人员、流程和技术）保持一致。组织中的业务和技术领导者必须了解组织的当前状态、目标状态以及实现目标状态所需的过渡，以便他们能够为员工设定目标并创建流程。

AWS 云采用框架 (AWS CAF) 提供指导和最佳实践，帮助组织识别技能和流程方面的差距。它还可以帮助组织在整个组织和整个 IT 生命周期内构建全面的云计算方法，以加速成功的云采用。

在最高级别，AWS CAF 将指导分为六个重点领域，称为视角。视角涵盖人员、流程和技术。每个视角由一组功能组成，涵盖由功能相关的利益相关者拥有或管理的不同职责。

每个视角内的功能可用于确定组织需要关注的领域。通过确定差距，可以创建规范的工作流来支持成功的云之旅。

![屏幕截图 2024-11-16 210906](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-16 210906.jpg)

一般来说，业务、人员和治理视角侧重于业务能力，而平台、安全和运营视角则侧重于技术能力。

![屏幕截图 2024-11-16 210935](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-16 210935.jpg)

从业务角度来看，利益相关者（例如业务经理、财务经理、预算所有者和战略利益相关者）可以使用 AWS CAF 为云采用创建强有力的业务案例，并确定云采用计划的优先级。利益相关者应确保组织的业务战略和目标与其 IT 战略和目标保持一致。

![屏幕截图 2024-11-16 211018](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-16 211018.jpg)

从治理角度来看，利益相关者（例如首席信息官或 CIO、项目经理、企业架构师、业务分析师和投资组合经理）可以使用 AWS CAF 来专注于将 IT 战略和目标与业务战略和目标保持一致所需的技能和流程。这种关注有助于组织最大限度地提高其 IT 投资的业务价值并最大限度地降低业务风险。

![屏幕截图 2024-11-16 211056](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-16 211056.jpg)

平台视角的利益相关者（例如首席技术官或 CTO、IT 经理和解决方案架构师）使用各种架构维度和模型来理解和传达 IT 系统的性质及其关系。他们必须能够详细描述目标状态环境的架构。AWS CAF 包括在云上实施新解决方案以及将本地工作负载迁移到云的原则和模式。

安全视角的利益相关者（例如首席信息安全官或 CISO、IT 安全经理和 IT 安全分析师）必须确保组织满足可见性、可审计性、控制力和敏捷性的安全目标。安全视角的利益相关者可以使用 AWS CAF 来构建满足组织需求的安全控制的选择和实施。

从运营角度来看的利益相关者（例如，IT 运营经理和 IT 支持经理）定义如何开展日常、季度和年度业务。从运营角度来看的利益相关者与业务运营保持一致并为其提供支持。AWS CAF 可帮助这些利益相关者定义当前的运营程序。它还帮助他们确定实施成功云采用所需的流程变更和培训

**Section 4 key takeaways**

本模块此部分的关键要点包括：

- 对于大多数组织而言，云采用并非瞬间完成，需要整个组织制定深思熟虑的策略和协调。
- AWS CAF 旨在帮助组织为其云采用之旅制定高效且有效的计划。
- AWS CAF 将指导分为六个重点领域（称为观点）。
- 观点由主要利益相关者负责的一系列业务或技术能力组成。



总之，在本模块中，您学习了如何：

- 定义不同类型的云计算
- 描述云计算的六个优势
- 识别主要的 AWS 服务类别和核心服务
- 查看 AWS 云采用框架



## Module 2: Cloud Economics and Billing

本模块将讨论以下主题：

- 定价基础知识
- 总拥有成本
- AWS 组织
- AWS 账单和成本管理
- 技术支持

该模块还包括一个由讲师指导的演示，向您展示如何与计费仪表板进行交互。该模块还包括一项活动，要求您使用 AWS 定价计算器估算公司的成本。最后，您将被要求完成知识测试，该测试将用于测试您对本模块中涵盖的关键概念的理解。



完成本模块后，您应该能够：

- 解释 AWS 定价理念
- 识别基本定价特征
- 指出总拥有成本的要素
- 讨论 AWS 定价计算器的结果
- 确定如何设置简化计费和账户可见性的组织结构以查看成本数据。
- 识别 AWS 计费仪表板中的功能•描述如何使用 AWS 账单、AWS 成本资源管理器、AWS 预算以及 AWS 成本和使用情况报告
- 识别各种 AWS 技术支持计划和功能



### Section 1: Fundamentals of pricing

![屏幕截图 2024-11-16 214810](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-16 214810.jpg)

AWS 的成本主要由三个因素决定：**compute计算**、**storage**存储和**outbound data transfer出站数据传输**。这些特性略有不同，具体取决于您选择的 AWS 产品和定价模型。

在大多数情况下，入站数据传输或同一 AWS 区域内其他 AWS 服务之间的数据传输均免费。但也有一些例外，因此在开始使用 AWS 服务之前，请务必验证数据传输费率。

出站数据传输在服务间进行汇总，然后按出站数据传输费率收费。此费用在月结单上显示为*AWS Data Transfer Out.*

![屏幕截图 2024-11-16 215026](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-16 215026.jpg)

这一理念是 AWS 定价的基础。虽然 AWS 提供的服务数量和类型急剧增加，但我们的定价理念始终未变。每个月末，您按实际使用量付费。您可以随时开始或停止使用产品。无需签订长期合同。

AWS 提供一系列云计算服务。对于每项服务，您支付的费用都与您实际需要的资源量相符。这种实用型定价模式包括：

- Pay for what you use 按使用量付费
- Pay less when you reserve 预留时付费更少
- Pay less when you use more 使用量越多付费更少
- Pay even less as AWS grows 随着 AWS 的增长，付费更少

![屏幕截图 2024-11-16 215148](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-16 215148.jpg)

除非您以建设数据中心为生，否则您可能已经花费了太多的时间和金钱来建设它们。使用 AWS，您只需为您使用的服务付费，无需支付大笔前期费用。您可以降低可变成本，因此您不再需要投入宝贵的资源来建设昂贵的基础设施，包括购买服务器、软件许可证或租赁设施。

只需按实际使用量付费，即可快速适应不断变化的业务需求，并将重点放在创新和发明上。所有 AWS 服务均可按需使用，无需长期合同，也没有复杂的许可依赖关系。



![屏幕截图 2024-11-16 215256](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-16 215256.jpg)

对于某些服务（例如 AmazonElastic Compute Cloud (Amazon EC2) 和 Amazon Relational Database Service (Amazon RDS)），您可以投资预留容量。使用预留实例，您可以节省高达 75% 的等效按需容量。预留实例有三种选择：

- All Upfront Reserved Instance 全额预付预留实例 (or AURI)
- Partial Upfront Reserved Instance 部分预付预留实例(or PURI)
- No Upfront Payments Reserved Instance 无预付款预留实例(or NURI)

当您购买预留实例时，预付款越多，折扣越大。为了最大限度地节省开支，您可以全额预付并获得最大折扣。部分预付预留实例提供的折扣较低，但可以让您选择减少预付款。最后，您可以选择不预付任何费用并获得较小的折扣，这使您能够释放资金用于其他项目。

通过使用预留容量，您的组织可以最大限度地降低风险，更有预见性地管理预算，并遵守需要长期承诺的政策。

![屏幕截图 2024-11-16 215513](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-16 215513.jpg)

使用 AWS，您可以获得基于数量的折扣，并随着使用量的增加实现重大节省。对于 Amazon Simple StorageService (Amazon S3) 等服务，定价是分级的，这意味着您使用越多，每 GB 支付的费用就越少。此外，数据传输始终是免费的。多种存储服务可根据您的需求提供更低的存储成本。因此，随着 AWS 使用需求的增加，您将受益于规模经济，从而能够提高采用率并控制成本。

随着组织的发展，AWS 还为您提供了获取可帮助您满足业务需求的服务的选项。例如，AWS 存储服务产品组合提供了一些选项，可帮助您根据访问数据的频率和检索数据所需的性能来降低价格。为了优化您的节省，您可以选择正确的存储解决方案组合，帮助您降低成本，同时保持性能、安全性和耐用性



![屏幕截图 2024-11-16 215551](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-16 215551.jpg)

AWS 始终致力于降低数据中心硬件成本、提高运营效率、降低电力消耗并降低整体业务成本。

这些优化以及 AWS 不断增长的规模经济将为您带来更低的价格。自 2006 年以来，AWS 已降价 75 次（截至 2019 年 9 月）。

AWS 增长的另一个好处是，未来性能更佳的资源可以取代当前的资源，且无需支付额外费用。



![屏幕截图 2024-11-16 215637](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-16 215637.jpg)



AWS 意识到每个客户的需求都不同。如果 AWS 定价模型都不适合您的项目，您可以为具有独特要求的大批量项目提供自定义定价。

![屏幕截图 2024-11-16 215705](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-16 215705.jpg)

为了帮助新的 AWS 客户开始使用云，AWS 为新客户提供了长达 1 年的免费使用套餐（AWS 免费套餐）。AWS 免费套餐适用于某些服务和选项。如果您是新的 AWS 客户，您可以免费运行 Amazon Elastic Compute Cloud (Amazon EC2) T2 微型实例一年，同时还可以使用 Amazon S3、Amazon Elastic Block Store (Amazon EBS)、Elastic Load Balancing、AWS 数据传输和其他 AWS 服务的免费使用套餐。

![屏幕截图 2024-11-16 215735](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-16 215735.jpg)



AWS 还提供各种不收取额外费用的服务。

- **Amazon Virtual Private Cloud (Amazon VPC)** 使您能够配置 AWS 云的逻辑隔离部分，您可以在其中定义的虚拟网络中启动 AWS 资源。
- **AWS Identity and Access Management (IAM)** 控制您的用户对 AWS 服务和资源的访问。
- **Consolidated Billing (合并账单)** 是 AWS Organizations 中的一项账单功能，用于合并多个 AWS 账户或多个 Amazon Internet Services Private Limited (AISPL) 账户的付款*。合并账单提供：
  - One bill for multiple accounts.
  - 能够轻松追踪每个帐户的费用。
  - 通过合并使用获得批量定价折扣，可以降低费用。
  - 您可以使用合并账单整合所有账户，并获得分级优惠。
- **AWS Elastic Beanstalk** 是一种更简单的方法，可让您在 AWS 云中快速部署和管理应用程序。
- **AWS CloudFormation** 为开发人员和系统管理员提供了一种简单的方法来创建相关 AWS 资源集合并以有序且可预测的方式配置它们。
- **Automatic Scaling**会根据您定义的条件自动添加或删除资源。您使用的资源会在需求高峰期间无缝增加以保持性能，并在需求低迷期间自动减少以最大限度地降低成本。
- **AWS OpsWorks** 是一项应用程序管理服务，可以轻松部署和操作各种形状和大小的应用程序。

虽然这些服务是免费的，但与这些服务一起使用的其他 AWS 服务可能会产生费用。例如，当您自动扩展其他 EC2 实例时，这些实例将产生费用。

**Key takeaways**

总而言之，虽然 AWS 提供的服务数量和类型急剧增加，但我们的定价理念并未改变。每个月末，您只需按实际使用量付费，并且可以随时开始或停止使用产品。无需签订长期合同。

估算成本的最佳方法是检查每项 AWS 服务的基本特性，估算每项特性的使用量，然后将使用量与 AWS 网站上公布的价格进行对比。服务定价策略让您可以灵活地选择每个项目所需的服务，并只为您使用的服务付费。

有几种免费的 AWS 服务，包括：

- Amazon VPC
- Elastic Beanstalk
- AWS CloudFormation
- IAM
- Automatic scaling services
- AWS OpsWorks
- Consolidated Billing

虽然这些服务本身是免费的，但它们提供的资源可能不是免费的。在大多数情况下，入站数据传输或同一 AWS 区域内其他 AWS 服务之间的数据传输均免费。但也有一些例外，因此在开始使用 AWS 服务之前，请务必验证数据传输费率。出站数据传输费用是分级的。

### Section 2: Total Cost of Ownership

![屏幕截图 2024-11-16 215735](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-16 215735.jpg)

许多企业都会问到选择本地部署还是云端部署的问题。这两个选项的区别在于部署方式。

本地基础设施安装在公司自己的计算机和服务器上。传统基础设施涉及多项固定成本，也称为资本支出。资本支出包括设施、硬件、许可证和维护人员。扩大规模可能既昂贵又耗时。缩小规模不会降低固定成本。

云基础设施是从服务提供商处购买的，服务提供商负责构建和维护设施、硬件和维护人员。

客户只需为使用的内容付费。扩大或缩小规模很简单。成本很容易估算，因为它们取决于服务的使用情况。

很难将本地 IT 交付模型与 AWS 云进行比较。

两者不同，因为它们使用不同的概念和术语。使用本地 IT 涉及基于资本支出、长期规划周期和多个组件的讨论，这些组件需要随着时间的推移购买、构建、管理和刷新资源。

使用 AWS 云涉及关于灵活性、敏捷性和基于消费的成本的讨论。

那么，您如何确定最佳选择？

![屏幕截图 2024-11-16 221352](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-16 221352.jpg)

您可以通过将本地解决方案与云解决方案进行比较来确定最佳选项。Total Cost of Ownership 总拥有成本 (TCO) 是一种财务估算，旨在帮助买家和所有者确定产品或系统的直接和间接成本。TCO 包括服务成本以及拥有该服务相关的所有成本。

您可能希望比较在本地或托管设施中为特定工作负载运行整个基础架构环境的成本与在基于云的基础架构上运行相同工作负载的成本。进行此比较是为了制定预算或为最佳部署解决方案的业务决策构建业务案例。

![屏幕截图 2024-11-16 221452](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-16 221452.jpg)与数据中心管理相关的一些成本包括：

- **Server** 服务器硬件和软件成本，以及安置设备的设施成本。
- **Storage** 存储硬件、管理和设施成本。
- **Network** 网络硬件、管理和设施成本。
-  **IT labor** 以及管理整个解决方案所需的 IT 劳动力成本。

当您将本地解决方案与云解决方案进行比较时，准确评估这两种方案的真实成本非常重要。使用云，大多数成本都是预付的，并且很容易计算。例如，云提供商根据不同的使用指标（例如 RAM、存储和带宽等）提供透明的定价。定价通常按单位时间固定。

客户可以确定价格，然后能够根据几种不同的使用情况估算轻松计算成本。

将此过程与内部部署技术进行比较。虽然有时很难确定，但内部成本的计算必须考虑所有因素：

- Direct costs :运行服务器所产生的直接成本 - 例如电力、占地面积、存储以及管理这些资源的 IT 运营。
- Indirect costs 运行服务器的间接成本，如网络和存储基础设施。

此图是概念性的，并不包括所有成本项目。例如，根据您正在实施的解决方案，软件成本可能包括数据库、管理和中间层成本。设施成本可能包括升级、维护、建筑安全、税费等。IT 劳动力成本可能包括安全管理和应用程序管理成本。此图包含一个简略列表，以展示数据中心维护所涉及的成本类型。

![屏幕截图 2024-11-16 221736](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-16 221736.jpg)

以下是成本比较示例。此示例显示了 3 年内本地解决方案和云解决方案的成本比较。为了进行此比较，构建了两个类似的环境来代表本地和 AWS 环境。不包括与本地解决方案相关的其他直接和间接成本。本地解决方案的组件包括：

- 1 个虚拟机，配备 4 个 CPU、16 GB RAM 和 Linux 操作系统
- 平均利用率为 100%
- 通过 RAM 进行优化



类似 AWS 环境的组件包括：

- 1 个 m4.xlarge 实例，配备 4 个 CPU、16 GB RAM
- 实例类型为 3 年期部分预付预留实例

本地部署 3 年总成本为 167,422 美元。AWS 云 3 年总成本为 7,509 美元，比本地部署解决方案节省了 96%。因此，云基础设施 3 年总节省额将达到 159,913 美元。此比较有助于企业清楚地了解替代方案之间的差异。

成本有什么不同？请记住，本地解决方案是可预测的。无论是否使用容量，它都会继续产生成本。

相比之下，AWS 解决方案在需要时投入使用，在资源不再使用时退役，从而降低总体成本。

可访问性：图表比较了本地部署和 AWS 的三年总拥有成本。本地部署成本为 167,422 美元，AWS 成本为 7,509 美元。可访问性描述结束。

![屏幕截图 2024-11-16 221912](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-16 221912.jpg)

AWS 提供 AWS 定价计算器，帮助您估算每月 AWS 账单。您可以使用此工具探索 AWS 服务并估算 AWS 上用例的成本。您可以在构建解决方案之前对其进行建模，探索估算背后的价格点和计算，并找到满足您需求的可用实例类型和合同条款。这使您能够就使用 AWS 做出明智的决策。您可以规划 AWS 成本和使用情况，或为设置一组新实例和服务定价。

AWS 定价计算器可帮助您：

- 估算 AWS 服务的每月成本
- 确定降低成本的机会
- 在构建解决方案之前对其进行建模
- 探索估算背后的价格点和计算
- 查找满足您需求的可用实例类型和合同条款

AWS 定价计算器可让您命名估算并创建和命名服务组。组是您添加服务以组织和构建估算的容器。您可以按成本中心、部门、产品架构等组织您的组和服务。

![屏幕截图 2024-11-16 222004](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-16 222004.jpg)

AWS 定价计算器估算分为：

- 前 12 个月的总额 – 您当前组以及当前组内的所有服务和组的总估算。它结合了预付款和月度估算。
- 您的预付款总额 – 在您设置 AWS 堆栈时，预计您需要预付多少费用。
- 您的月度总额 – 在您运行 AWS 堆栈时，预计您每月需要花费多少费用。

在组中，您可以查看每项服务的预计成本。如果您想要为构建 AWS 设置的不同方式定价，则可以为设置的每种变体使用不同的组，并比较不同设置的估算值。

![屏幕截图 2024-11-16 222122](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-16 222122.jpg)

硬性优势包括减少计算、存储、网络和安全方面的支出。它们还包括减少硬件和软件购买；减少运营成本、备份和灾难恢复；以及减少运营人员。

**Cloud Total Cost of Ownership 云总拥有成本**定义了采用该技术后将花费多少钱，或者运行该解决方案的成本。通常，TCO 分析会查看现有的本地基础架构，并将其与云中未来基础架构状态的成本进行比较。虽然这种差异可能很容易计算，但它可能只能提供迁移到云的总体财务影响的狭隘视角。

**return on investment 投资回报率 (ROI)** 分析可用于确定在考虑支出和储蓄时产生的价值。该分析首先确定直接和可见的成本降低和效率提高方面的硬性利益。

接下来，**soft savings 确定软性节约**。软性节约是难以准确量化的价值点，但它们可能比硬性节约更有价值。了解硬性和软性优势对于理解云的全部价值非常重要。软性优势包括：

- 重用服务和应用程序，使您能够使用相同的云服务定义（和重新定义）解决方案
- 提高开发人员的工作效率

- 提高客户满意度 
- 敏捷的业务流程，可以快速响应新出现的机会 
- 扩大全球影响力



### Section 3: AWS Organizations

AWS Organizations 是一项免费的账户管理服务，可让您将多个 AWS 账户整合到您创建并集中管理的组织中。AWS Organizations 包括整合的账单和账户管理功能，可帮助您更好地满足业务的预算、安全性和合规性需求。AWS Organizations 的主要优势包括：

-  集中管理跨多个 AWS 账户的访问策略。
- 控制对 AWS 服务的访问。
- 自动创建和管理 AWS 账户。
-  跨多个 AWS 账户整合账单。



![屏幕截图 2024-11-18 133539](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 133539.jpg)

这里有一些术语可以帮助您了解 AWS 组织的结构。

该图显示了一个基本组织或根，它由七个账户组成，这些账户被组织成四个**organizational units 组织单位 (OU)**。OU 是根内账户的容器。OU 还可以包含其他 OU。此结构使您能够创建一个层次结构，该层次结构看起来像一棵倒置的树，根位于顶部。分支由子 OU 组成，它们向下移动，直到它们以账户结尾，这些账户就像树的叶子一样。

当您将策略附加到层次结构中的一个节点时，它会向下流动并影响所有分支和叶子。此示例组织有几项策略附加到某些 OU 或直接附加到账户。

一个 OU 只能有一个父级，目前每个账户只能是一个 OU 的成员。账户是包含您的 AWS 资源的标准 AWS 账户。您可以将策略附加到账户，以仅对该账户应用控制。

![屏幕截图 2024-11-18 133832](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 133832.jpg)

AWS Organizations 可让您：

- 创建**service control policies 服务控制策略 (SCP)**，以集中控制跨多个 AWS 账户的 AWS 服务
- 创建**groups of accounts 账户组**，然后将策略附加到组，以确保在各个账户中应用正确的策略。
- 通过使用**application programming interfaces 应用程序编程接口 (API)** 自动创建和管理新的 AWS 账户，简化账户管理。
- 通过为组织中的所有 AWS 账户设置**consolidated billing 单一付款方式**，简化计费流程。通过整合账单，您可以查看所有账户产生的费用的综合视图，并可以利用汇总使用量的定价优势。整合账单提供了一个集中位置来管理所有 AWS 账户的账单，并能够从批量折扣中获益。

![屏幕截图 2024-11-18 134202](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 134202.jpg)

AWS Organizations 不会取代将 **AWS Identity and Access Management (IAM)** 策略与 AWS 账户内的用户、组和角色关联起来。

使用 IAM 策略，您可以允许或拒绝对 AWS 服务（例如 Amazon S3）、单个 AWS 资源（例如特定 S3 存储桶）或单个 API 操作（例如 s3:CreateBucket）的访问。IAM 策略只能应用于 IAM 用户、组或角色，并且永远无法限制 AWS 账户根用户。

相比之下，使用组织，您可以使用 **service control policies 服务控制策略 (SCP)** 允许或拒绝单个 AWS 账户或 OU 中的账户组访问特定 AWS 服务。附加 SCP 中的指定操作会影响账户的所有 IAM 用户、组和角色，包括 AWS 账户根用户。

![屏幕截图 2024-11-18 134822](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 134822.jpg)

请记住，此过程假设您可以访问两个现有的 AWS 账户，并且可以以管理员身份登录每个账户。

查看以下步骤以设置 AWS Organizations：

- 步骤 1 是创建您的组织，将您当前的 AWS 账户作为主账户。您还可以邀请一个 AWS 账户加入您的组织，并创建另一个账户作为成员账户。
- 步骤 2 是在您的新组织中创建两个组织单位，并将成员账户放在这些 OU 中。
- 步骤 3 是创建服务控制策略，这些策略使您能够限制可以委托给成员账户中的用户和角色的操作。服务控制策略是一种组织控制策略。
- 步骤 4 是测试您组织的策略。以每个角色（例如 OU1 或 OU2）的用户身份登录，并查看服务控制策略如何影响账户访问。或者，您可以使用 IAM 策略模拟器来测试和排除 IAM 和基于资源的策略的故障，这些策略附加到您的 AWS 账户中的 IAM 用户、组或角色。

![屏幕截图 2024-11-18 134936](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 134936.jpg)

您可以在 AWS Organizations 中创建的名称受到限制，其中包括账户、OU、根和策略的名称。

名称必须由 Unicode 字符组成，且长度不得超过 250 个字符。

AWS Organizations 对于实体有几个最大值和最小值。

对于可访问性：AWS Organizations 限制列表，包括名称、账户数量（各不相同）、根数量（1）、OU 数量（1,000）、策略数量（1,000）、控制策略文档的最大大小（5,120 字节）、BU 的最大嵌套（根下有 5 级 BU）、每天发送的邀请数（20）、同时创建的成员账户数（5）以及可以附加策略的实体数（无限制）。可访问性描述结束。

![屏幕截图 2024-11-18 135047](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 135047.jpg)

AWS Organizations 可以通过不同的界面进行管理。

AWS **Management Console**管理控制台是一个基于浏览器的界面，可用于管理您的组织和 AWS 资源。您可以使用控制台在组织中执行任何任务。

AWS 命令行界面 (AWS CLI) 工具可让您在系统的命令行中发出命令来执行 AWS Organizations 任务和 AWS 任务。此方法比使用控制台更快捷、更方便。

您还可以使用 AWS 软件开发工具包 (SDK) 来处理诸如对请求进行加密签名、管理错误以及自动重试请求等任务。AWS SDK 包含适用于各种编程语言和平台的库和示例代码，例如 Java、Python、Ruby、.NET、iOS 和 Android。

AWS Organizations HTTPS 查询 API 为您提供对 AWS Organizations 和 AWS 的编程访问。您可以使用该 API 直接向服务发出 HTTPS 请求。使用 HTTPS API 时，您必须包含代码以使用您的凭证对请求进行数字签名。



### Section 4: AWS Billing and Cost Management

**AWS Billing and Cost Management** 账单和成本管理是您用来支付 AWS 账单、监控使用情况和预算成本的服务。账单和成本管理使您能够预测并更好地了解未来的成本和使用情况，以便提前规划。

您可以设置自定义时间段，并确定是否要按月度或每日粒度查看数据。

借助筛选和分组功能，您可以使用各种可用维度进一步分析数据。AWS Cost and Usage Report Tool** 成本和使用情况报告工具可让您了解成本和使用情况数据趋势以及您如何使用 AWS 实施，从而确定优化机会。

AWS Billing and Cost Management console 账单和成本管理控制台包含 Cost Explorer 页面，可用于以图表形式查看您的 AWS 成本数据。

使用 Cost Explorer，您可以直观地了解和管理一段时间内的 AWS 成本和使用情况。

Cost Explorer 包含一份默认报告，该报告直观地显示了您最耗费的 AWS 服务的成本和使用情况。每月运行成本报告为您提供了过去 3 个月所有成本的概览。它还提供下个月的预测数字以及相应的置信区间。

Cost Explorer 是一款免费工具，可让您：

- 查看成本图表。
- 查看过去 13 个月的成本数据。•预测未来 3 个月可能花费的金额。
- 发现您在一段时间内在 AWS 资源上花费的模式并确定成本问题区域。
- 确定您使用最多的服务
- 查看指标，例如哪些可用区拥有最多流量或哪个链接的 AWS 账户使用最多。



![屏幕截图 2024-11-18 140127](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 140127.jpg)

**AWS Budgets** 使用 Cost Explorer 提供的成本可视化功能向您显示预算状态并提供估计成本的预测。

您还可以使用 AWS 预算创建通知，以便在超出当月预算或预估成本超出预算时发出通知。您可以按月、季度或年度跟踪预算，并自定义开始和结束日期。预算警报可以通过电子邮件或 **Amazon Simple Notification Service (Amazon SNS)** 发送。

可访问性：AWS 账单预算面板显示预算名称、当前和未来成本和使用情况，以及当前和预测预算的标题。可访问性描述结束。

![屏幕截图 2024-11-18 140236](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 140236.jpg)

**AWS Cost and Usage Report** 成本和使用情况报告是访问有关 AWS 成本和使用情况的综合信息的单一位置。此工具以每小时或每日明细项目的形式列出账户（及其用户）使用的每个服务类别的使用情况，以及您为税务分配目的激活的任何税费。

您可以选择让 AWS 将账单报告发布到 S3 存储桶。这些报告可以每天更新一次。



## Module 3: AWS Global Infrastructure Overview

本模块将讨论以下主题：

- AWS 全球基础设施
- AWS 服务和服务类别概述

该模块包括由教育工作者主导的演示，重点介绍 AWS 全球基础设施的细节。该模块还包括一个动手实践活动，您将在其中探索 AWS 管理控制台。

完成本模块后，您应该能够：

- 识别 AWS 区域、可用区和边缘位置之间的差异
- 识别 AWS 服务和服务类别

### Section 1: AWS Global Infrastructure

![屏幕截图 2024-11-18 141912](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 141912.jpg)



AWS 云基础设施围绕区域构建。AWS 在全球拥有 22 个区域。AWS 区域是具有一个或多个可用区的物理地理位置。可用区又由一个或多个数据中心组成。

为了实现容错和稳定性，区域之间是相互隔离的。一个区域中的资源不会自动复制到其他区域。当您将数据存储在特定区域时，该数据不会复制到该区域之外。

如果您的业务需求需要，您有责任跨区域复制数据。

2019 年 3 月 20 日之前推出的 AWS 区域默认处于启用状态。2019 年 3 月 20 日之后推出的区域（例如亚太地区（香港）和中东（巴林））默认处于禁用状态。您必须先启用这些区域，然后才能使用它们。您可以使用 AWS 管理控制台启用或禁用区域。

部分区域有访问限制。Amazon AWS（中国）账户仅提供对北京和宁夏区域的访问。要了解有关中国 AWS 的更多信息，请参阅：https://www.amazonaws.cn/en/about-aws/china/。独立的 AWS GovCloud（美国）区域旨在允许美国政府机构和客户通过满足其特定的监管和合规性要求将敏感工作负载迁移到云中。

可访问性：来自 Infrastructure.aws 网站的快照，显示伦敦市中心的图片，包括塔桥和碎片大厦。它指出伦敦地区有三个可用区。可访问性描述结束。

![屏幕截图 2024-11-18 142200](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 142200.jpg)



在选择存储数据和使用 AWS 服务的最佳区域时，您应该考虑一些因素。

一个重要的考虑因素是数据管理和法律要求。当地法律可能要求将某些信息保留在地理边界内。这些法律可能会限制您可以提供内容或服务的地区。例如，考虑欧盟 (EU) 数据保护指令。

在其他条件相同的情况下，通常最好在尽可能靠近用户和访问它们的系统的区域运行应用程序并将数据存储起来。这将有助于您减少延迟。CloudPing 是一个可用于测试您所在位置与所有 AWS 区域之间的延迟的网站。要了解有关 CloudPing 的更多信息，请参阅：http://www.cloudping.info/请记住，并非所有服务都可在所有区域使用。要了解更多信息，请参阅：https://aws.amazon.com/about-aws/global-infrastructure/regional-product-services/?p=tgi&loc=4。最后，运行服务的成本会有所不同，这取决于您选择的区域。例如，截至撰写本文时，在美国东部（俄亥俄）区域运行按需 t3.medium 大小的 Amazon Elastic Compute Cloud (Amazon EC2) Linux 实例的成本为每小时 0.0416 美元，但在亚太地区（东京）区域运行相同实例的成本为每小时 0.0544 美元。

![屏幕截图 2024-11-18 142308](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 142308.jpg)

每个 AWS 区域都有多个隔离位置，称为**可用区Availability Zones**。

每个可用区都能够运行比单个数据中心更高可用性、容错性和可扩展性的应用程序和数据库。每个可用区可以包含多个数据中心（通常为三个），在全面扩展时，它们可以包含数十万台服务器。它们是 AWS 全球基础设施的完全隔离分区。可用区拥有自己的电力基础设施，并且它们与其他可用区在物理上相隔数公里 — — 尽管所有可用区之间的距离都在 100 公里以内。

所有可用区均通过高带宽、低延迟网络通过完全冗余的专用光纤互连，从而在可用区之间提供高吞吐量。该网络在可用区之间实现同步复制。

可用区有助于构建高可用性应用程序。当应用程序跨可用区进行分区时，公司可以更好地隔离并免受雷电、龙卷风、地震等问题的影响。

您负责选择系统所在的可用区。系统可以跨多个可用区。AWS 建议跨可用区进行复制以实现弹性。您应设计系统以在发生灾难时承受可用区的临时或长期故障。

![屏幕截图 2024-11-18 142442](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 142442.jpg)

AWS 基础设施的基础是数据中心。客户不会指定数据中心来部署资源。相反，可用区域是客户可以进行的最精细的规范级别。但是，数据中心是实际数据所在的位置。亚马逊运营着最先进的高可用性数据中心。虽然很少见，但可能会发生影响同一位置实例可用性的故障。如果您将所有实例托管在受此类故障影响的单个位置，则您的所有实例都将不可用。

数据中心的安全设计考虑了以下几个因素：

每个位置都经过仔细评估，以减轻环境风险。

- 数据中心采用冗余设计，可预测和容忍故障，同时保持服务水平。
- 为确保可用性，关键系统组件在多个可用区中备份。
- 为确保容量，AWS 持续监控服务使用情况，以部署基础设施来支持可用性承诺和要求。
- 数据中心位置不公开，所有访问均受到限制。
- 发生故障时，自动化流程会将数据流量移出受影响区域。

AWS 使用来自**multiple original device manufacturers**多家原始设备制造商 (ODM) 的**custom network equipment**定制网络设备。ODM 根据第二家公司的规格设计和制造产品。然后，第二家公司重新包装产品以供销售。

![屏幕截图 2024-11-18 142713](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 142713.jpg)

**Amazon CloudFront** 是一种**content delivery network** 内容分发网络 (CDN)，用于将内容分发给最终用户以减少延迟。**Amazon Route 53** 是一种域名系统 (DNS) 服务。发送到其中任一服务的请求将自动路由到最近的边缘位置**edge location**，以降低延迟。

AWS **Points of Presence**  接入点遍布全球大部分主要城市。通过持续测量互联网连接、性能和计算以找到路由请求的最佳方式，接入点可提供更好的近乎实时的用户体验。许多 AWS 服务都使用它们，包括 Amazon CloudFront、Amazon Route 53、AWS Shield 和 AWS Web 应用程序防火墙 (AWS WAF) 服务。

Amazon CloudFront 默认使用 **Regional edge caches 区域边缘缓存**。当您的内容访问频率不够高而无法保留在边缘站点时，将使用区域边缘缓存。区域边缘缓存吸收这些内容，并提供必须从源服务器获取这些内容的替代方案。	

![屏幕截图 2024-11-18 143914](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 143914.jpg)



现在您已经充分了解了组成 AWS 全球基础设施的主要组件，让我们来考虑一下该基础设施提供的优势。

AWS 全球基础设施具有多项宝贵功能：

- 首先，它具有弹性和可扩展性。这意味着资源可以根据容量需求的增加或减少进行动态调整。它还可以快速调整以适应增长。
- 其次，该基础设施具有容错能力，这意味着它具有内置组件冗余，即使某个组件发生故障，它仍可继续运行。
- 最后，它几乎不需要人工干预，同时提供高可用性和最短的停机时间。



**Key takeaways**

本模块此部分的一些关键要点包括：

- AWS 全球基础设施由区域和可用区组成。
- 您对区域的选择通常基于合规性要求或为了减少延迟。
- 每个可用区在物理上都与其他可用区分开，并具有冗余电源、网络和连接。
- 边缘位置和区域边缘缓存通过将内容缓存到更靠近用户的位置来提高性能。



### Section 2: AWS services and service category overview

简介第 2 部分：AWS 服务和服务类别概述。AWS 提供一系列全球云产品，可用作常见云架构的构建块。

下面介绍这些云产品的组织方式。

![屏幕截图 2024-11-18 144106](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 144106.jpg)



如前所述，AWS 全球基础设施可分为三个要素：区域、可用区和接入点（包括边缘位置）。该基础设施为一系列广泛的服务（如网络、存储、计算服务和数据库）提供了平台，这些服务以按需实用程序的形式提供，可在几秒钟内使用，并采用按使用量付费的定价方式。

对于可访问性：营销图显示底部的基础设施，包括区域、可用区和边缘位置。下一个级别标记为基础服务，包括计算、网络和存储的图形。该级别已突出显示。下一个级别是平台服务，包括数据库、分析、应用服务、部署和管理以及移动服务。顶层标记为应用程序，包括虚拟桌面以及协作和共享。可访问性描述结束。

![屏幕截图 2024-11-18 144200](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 144200.jpg)

AWS 提供广泛的基于云的服务。有 23 种不同的产品或服务类别，每个类别包含一项或多项服务。本课程不会尝试向您介绍每项服务。相反，本课程的重点是使用最广泛且为 AWS 云提供最佳介绍的服务。本课程还重点介绍 AWS Certified Cloud Practitioner 考试中更有可能涉及的服务。

本课程将讨论的类别在幻灯片上突出显示：计算、成本管理、数据库、管理和治理、网络和内容交付、安全、身份和合规性以及存储。

要了解有关 AWS 产品的更多信息，请参阅 https://aws.amazon.com/products/ 上的云产品。所有 AWS 产品都按此处显示的服务类别进行组织。例如，如果您单击计算，您将看到 Amazon Elastic Compute Cloud (Amazon EC2) 位列列表首位。计算类别还列出了许多其他产品和服务。

如果您单击 Amazon EC2，它将带您进入 Amazon EC2 页面。每个产品页面都提供了产品的详细描述并列出了它的一些优点。

探索不同的服务组，了解其中的类别和服务。现在您知道如何查找有关不同服务的信息，本模块将讨论突出显示的服务类别。**接下来的七张幻灯片列出了本课程将讨论的上述每个类别中的各项服务。**

![屏幕截图 2024-11-18 144327](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 144327.jpg)

AWS 存储服务包括此处列出的服务以及许多其他服务。

**Amazon Simple Storage Service (Amazon S3)** 是一种对象存储服务，可提供可扩展性、数据可用性、安全性和性能。使用它来存储和保护网站、移动应用程序、备份和恢复、存档、企业应用程序、物联网 (IoT) 设备和大数据分析的任意数量的数据。

**Amazon Elastic Block Store (Amazon EBS)** 是一种高性能数据块存储，专为与 Amazon EC2 配合使用而设计，适用于吞吐量和事务密集型工作负载。它可用于各种工作负载，例如关系数据库和非关系数据库、企业应用程序、容器化应用程序、大数据分析引擎、文件系统和媒体工作流。

**Amazon Elastic File System (Amazon EFS)** 提供可扩展、完全托管的弹性网络文件系统 (NFS) 文件系统，可与 AWS 云服务和本地资源配合使用。它可按需扩展到 PB 级，并随着您添加和删除文件而自动增加和缩小。它减少了配置和管理容量以适应增长的需求。

**Amazon Simple Storage Service Glacier** 是一种安全、耐用且成本极低的 Amazon S3 云存储类，用于数据存档和长期备份。它旨在提供 11 个 9 的耐用性，并提供全面的安全性和合规性功能，以满足严格的监管要求。

![屏幕截图 2024-11-18 144500](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 144500.jpg)

AWS 计算服务包括此处列出的服务以及许多其他服务。

**Amazon Elastic Compute Cloud (Amazon EC2)** 作为云中的虚拟机提供可调整大小的计算容量。

**Amazon EC2 Auto Scaling** 使您能够根据定义的条件自动添加或删除 EC2 实例。

**Amazon Elastic Container Service (Amazon ECS)** 是一种高度可扩展、高性能的容器编排服务，支持 Docker 容器。

**Amazon Elastic Container Registry (Amazon ECR)** 是一个完全托管的 Docker 容器注册表，可让开发人员轻松存储、管理和部署 Docker 容器映像。

**AWS Elastic Beanstalk** 是一种在熟悉的服务器（例如 Apache 和 Microsoft Internet Information Services (IIS)）上部署和扩展 Web 应用程序和服务的服务。

**AWS Lambda** 让您无需预置或管理服务器即可运行代码。您只需为您使用的计算时间付费。当您的代码未运行时，则不收取任何费用。

**Amazon Elastic Kubernetes Service (Amazon EKS)** 让您能够轻松部署、管理和扩展在 AWS 上使用 Kubernetes 的容器化应用程序。

**AWS Fargate** 是 Amazon ECS 的计算引擎，允许您运行容器而无需管理服务器或集群。

![屏幕截图 2024-11-18 145657](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 145657.jpg)

AWS 数据库服务包括此处列出的服务以及许多其他服务。

**Amazon Relational Database Service (Amazon RDS)** 让您能够轻松地在云中设置、操作和扩展关系数据库。它提供可调整大小的容量，同时自动执行耗时的管理任务，例如硬件配置、数据库设置、修补和备份。

**Amazon Aurora** 是与 MySQL 和 PostgreSQL 兼容的关系数据库。它比标准 MySQL 数据库快五倍，比标准 PostgreSQL 数据库快三倍。

**Amazon Redshift** 可让您针对本地存储在 Amazon Redshift 中的 PB 级数据以及直接针对存储在 Amazon S3 中的 EB 级数据运行分析查询。它在任何规模下都能提供快速的性能。

**Amazon DynamoDB** 是一个键值和文档数据库，可以在任何规模下提供个位数毫秒的性能，具有内置安全性、备份和恢复以及内存缓存功能。

![屏幕截图 2024-11-18 145841](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 145841.jpg)



AWS 网络和内容交付服务包括此处列出的服务以及许多其他服务。

**Amazon Virtual Private Cloud (Amazon VPC)** 使您能够配置 AWS 云的逻辑隔离部分。

**Elastic Load Balancing** 自动在多个目标（例如 Amazon EC2 实例、容器、IP 地址和 Lambda 函数）之间分配传入的应用程序流量。

**Amazon CloudFront** 是一种快速内容分发网络 (CDN) 服务，可以安全地向全球客户分发数据、视频、应用程序和应用程序编程接口 (API)，具有低延迟和高传输速度。

**AWS Transit Gateway** 是一项服务，可让客户将其 Amazon Virtual Private Clouds (VPC) 及其本地网络连接到单个网关。

**Amazon Route 53** 是一种可扩展的云域名系统 (DNS) Web 服务，旨在为您提供一种可靠的方式将最终用户路由到互联网应用程序。它将名称（如 www.example.com）转换为计算机用于相互连接的数字 IP 地址（如 192.0.2.1）。

**AWS Direct Connect** 提供了一种从您的数据中心或办公室到 AWS 建立专用私有网络连接的方法，可以降低网络成本并提高带宽吞吐量。

**AWS VPN** 提供从您的网络或设备到 AWS 全球网络的安全专用隧道。

![屏幕截图 2024-11-18 150043](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 150043.jpg)

AWS 安全、身份和合规性服务包括此处列出的服务以及许多其他服务。

**AWS Identity and Access Management (IAM)** 使您能够安全地管理对 AWS 服务和资源的访问。通过使用 IAM，您可以创建和管理 AWS 用户和组。您可以使用 IAM 权限允许和拒绝用户和组对 AWS 资源的访问。

**AWS Organizations** 允许您限制您的账户中允许的服务和操作。

**Amazon Cognito** 可让您向 Web 和移动应用程序添加用户注册、登录和访问控制。

**AWS Artifact** 提供对 AWS 安全性和合规性报告以及选择在线协议的按需访问。

**AWS Key Management Service (AWS KMS)** 可让您创建和管理密钥。您可以使用 AWS KMS 控制各种 AWS 服务和应用程序中加密的使用。

**AWS Shield** 是一种托管的分布式拒绝服务 (DDoS) 防护服务，可保护在 AWS 上运行的应用程序。

![屏幕截图 2024-11-18 150220](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 150220.jpg)

AWS 成本管理服务包括此处列出的服务以及其他服务。

**AWS Cost and Usage Report**包含最全面的 AWS 成本和使用情况数据，包括有关 AWS 服务、定价和预留的其他元数据。

**AWS Budgets**可让您设置自定义预算，当您的成本或使用量超出（或预计超出）预算金额时，系统会向您发出警报。

**AWS Cost Explorer** 具有易于使用的界面，可让您直观地了解和管理您的 AWS 成本和随时间变化的使用情况。

![屏幕截图 2024-11-18 150349](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 150349.jpg)

AWS 管理和治理服务包括此处列出的服务及其他服务。

**AWS Management Console**提供了基于 Web 的用户界面，用于访问您的 AWS 账户。

**AWS Config** 提供可帮助您跟踪资源清单和变化的服务。

**Amazon CloudWatch** 可让您监控资源和应用程序。

**AWS Auto Scaling** 提供可让您扩展多种资源以满足需求的功能。

**AWS Command Line Interface**提供了统一的工具来管理 AWS 服务。

**AWS Trusted Advisor** 可帮助您优化性能和安全性。

**AWS Well-Architected Tool** 可帮助您审查和改进工作负载。

**AWS CloudTrail** 可跟踪用户活动和 API 使用情况。





**Module summary**    

总之，在本模块中，您学习了如何：

- 识别 AWS 区域、可用区和边缘位置之间的差异
- 识别 AWS 服务和服务类别





## Module 4: AWS Cloud Security

安全性是 Amazon WebServices (AWS) 的首要任务。AWS 提供可扩展的云计算环境，旨在实现高可用性和可靠性，同时提供可让您运行各种应用程序的工具。帮助保护系统和数据的机密性、完整性和可用性对 AWS 至关重要，维护客户的信任和信心也是如此。本模块介绍了 AWS 的安全方法，其中包括 AWS 环境中的控制措施以及客户可以用来实现其安全目标的一些 AWS 产品和功能。

本模块将讨论以下主题：

- AWS 共享责任模型
- AWS 身份和访问管理 (IAM)
- 保护新 AWS 账户
- 保护账户
- 保护 AWS 上的数据
- 努力确保合规性
- 其他安全服务和资源

第一部分包括由教育工作者主导的有关 AWS 共享责任模型的活动。

第二部分包括录制的 IAM 演示，同一部分的末尾包括一个动手实验室，可让您练习使用 AWS 管理控制台配置 IAM。

完成本模块后，您应该能够：

-  识别共享责任模型
- 确定客户和 AWS 的责任
- 识别 IAM 用户、组和角色
- 描述 IAM 中的不同类型的安全凭证• 确定保护新 AWS 账户的步骤
-  探索 IAM 用户和组
-  识别如何保护 AWS 数据
-  识别 AWS 合规性计划



### Section 1: AWS shared responsibility model

![屏幕截图 2024-11-18 191055](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 191055.jpg)

安全性和合规性是 AWS 和客户共同承担的责任。这种共同责任模式旨在帮助减轻客户的运营负担。同时，为了提供灵活性和客户控制，以便在 AWS 上部署客户解决方案，客户仍需负责整体安全性的某些方面。谁负责通常称为“云的”安全性与“云中的”安全性的区别。

AWS 运营、管理和控制从软件虚拟化层到 AWS 服务运行设施的物理安全的各个组件。AWS 负责保护运行 AWS 云中提供的所有服务的基础设施。该基础设施由运行 AWS 云服务的硬件、软件、网络和设施组成。

客户负责静态数据和传输中数据的加密。客户还应确保网络配置安全，并安全管理安全凭证和登录。此外，客户还负责配置安全组和在其启动的计算实例上运行的操作系统（包括更新和安全补丁）。

![屏幕截图 2024-11-18 191158](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 191158.jpg)

AWS 负责云的安全。但这意味着什么呢？

在 AWS 共享责任模型下，AWS 运营、管理和控制从裸机主机操作系统和虚拟机管理程序虚拟化层到服务运行设施的物理安全等组件。这意味着 AWS 负责保护运行 AWS 云中提供的所有服务的全球基础设施。全球基础设施包括 AWS 区域、可用区和边缘位置

AWS 负责托管您的资源的物理基础设施，包括：

- **Physical security of data centers 数据中心的物理安全**，具有受控的、基于需求的访问权限；位于不起眼的设施中，配备全天候保安；双因素身份验证；访问记录和审查；视频监控；以及磁盘消磁和销毁。
- **Hardware infrastructure 硬件基础设施**，例如 AWS 所依赖的服务器、存储设备和其他设备。
- **Software infrastructure 软件基础设施**，托管操作系统、服务应用程序和虚拟化软件。
- **Network infrastructure 网络基础设施**，例如路由器、交换机、负载均衡器、防火墙和电缆。AWS 还会持续监控外部边界的网络，保护接入点，并提供具有入侵检测功能的冗余基础设施。

保护这一基础设施是 AWS 的首要任务。虽然您无法访问 AWS 数据中心或办公室来亲眼见证这种保护，但亚马逊提供了多份来自第三方审计师的报告，这些审计师已验证我们遵守了各种计算机安全标准和法规

![屏幕截图 2024-11-18 191339](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 191339.jpg)

虽然云基础设施由 AWS 保护和维护，但客户仍需对他们放入云中的所有内容的安全负责。

客户负责使用 AWS 服务实施的内容以及连接到 AWS 的应用程序。您必须采取的安全步骤取决于您使用的服务和系统的复杂性。

客户的责任包括选择和保护任何实例操作系统、保护在 AWS 资源上启动的应用程序、安全组配置、防火墙配置、网络配置和安全账户管理。

当客户使用 AWS 服务时，他们可以完全控制其内容。客户负责管理关键内容安全要求，包括：

- 他们选择在 AWS 上存储哪些内容
- 内容使用哪些 AWS 服务
- 内容存储在哪个国家/地区
- 内容的格式和结构以及是否经过屏蔽、匿名化或加密
- 谁有权访问内容以及如何授予、管理和撤销这些访问权限

客户可以控制他们选择实施的安全措施来保护他们自己的数据、环境、应用程序、IAM 配置和操作系统。

![屏幕截图 2024-11-18 191457](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 191457.jpg)



**基础设施即服务 (IaaS)** 是指为云 IT 提供基本构建块的服务，通常包括访问配置网络、计算机（虚拟或专用硬件）和数据存储空间。可以归类为 IaaS 的云服务为客户提供**最高级别的灵活性**和对 IT 资源的管理控制。IaaS 服务与当今许多 IT 部门熟悉的现有本地计算资源最为相似。

AWS 服务（例如 **Amazon EC2**）可归类为 IaaS，因此要求客户执行所有必要的安全配置和管理任务。部署 EC2 实例的客户负责管理客户操作系统（包括更新和安全补丁）、实例上安装的任何应用程序软件以及 AWS 提供的安全组的配置。

**平台即服务 (PaaS)** 是指客户无需管理底层基础设施（硬件、操作系统等）的服务。PaaS 服务使客户能够完全专注于部署和管理应用程序。客户无需担心资源采购、容量规划、软件维护或修补。

**AWS Lambda** 和 **Amazon RDS** 等 AWS 服务可以归类为 **PaaS**，因为 **AWS** **运营基础设施层、操作系统和平台**。客户只需访问终端即可存储和检索数据。使用 PaaS 服务，客户负责管理其数据、分类其资产并应用适当的权限。但是，这些服务更像是托管服务，AWS 处理大部分安全需求。对于这些服务，AWS 处理基本的安全任务，例如操作系统和数据库修补、防火墙配置和灾难恢复。

![屏幕截图 2024-11-18 191736](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 191736.jpg)

**软件即服务 (SaaS)** 是指提供集中托管软件的服务，这些软件通常可通过 Web 浏览器、移动应用或应用程序编程接口 (API) 访问。SaaS 产品的许可模式通常是订阅或按使用量付费。使用 SaaS 产品，客户无需管理支持该服务的基础设施。鉴于 **AWS Trusted Advisor**、**AWS Shield** 和 **Amazon Chime** 等 AWS 服务的特点，它们可以归类为 SaaS 产品。

**AWS Trusted Advisor** 是一款在线工具，可分析您的 AWS 环境并提供实时指导和建议，帮助您按照 AWS 最佳实践配置资源。Trusted Advisor 服务是 AWS Support 计划的一部分。部分 Trusted Advisor 功能可供所有账户免费使用，但商业支持和企业支持客户可以访问全套 Trusted Advisor 检查和建议。

**AWS Shield** 是一种托管的分布式拒绝服务 (DDoS) 防护服务，可保护在 AWS 上运行的应用程序。它提供始终在线的检测和自动内联缓解措施，可最大限度地减少应用程序停机时间和延迟，因此无需联系 AWS Support 即可享受 DDoS 防护。AWS Shield Advanced 可供所有客户使用。但是，要联系 DDoS 响应团队，客户必须拥有 AWS Support 的企业支持或商业支持。

**Amazon Chime** 是一种通信服务，可让您使用单个应用程序在组织内部和外部进行会议、聊天和拨打商务电话。它是一种即用即付的通信服务，无需预付费用、承诺或长期合同。

在这个由教师主导的活动中，您将看到两个场景。对于每个场景，您将被问到几个问题，关于谁的责任（AWS 或客户）来确保相关物品的安全。教师将带领全班讨论每个问题，并逐一揭晓正确答案。

![屏幕截图 2024-11-18 191918](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 191918.jpg)

考虑客户使用此处显示的 AWS 服务和资源的情况。谁负责维护安全？AWS 还是客户？

![屏幕截图 2024-11-18 192007](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 192007.jpg)

客户使用 Amazon Simple Storage Service(AmazonS3) 来存储数据。客户使用 Amazon Virtual Private Cloud (Amazon VPC) 配置了一个虚拟私有云 (VPC)。他们创建的 EC2 实例和 Oracle 数据库实例都在 VPC 中运行。

在此示例中，客户必须管理在 EC2 实例上运行的客户操作系统 (OS)。随着时间的推移，客户操作系统将需要升级并应用安全补丁。此外，客户在 Amazon EC2 实例上安装的任何应用软件或实用程序也必须维护。客户负责配置应用于 Amazon EC2 实例的 AWS 防火墙（或安全组）。客户还负责指定 Amazon EC2 实例运行的网络条件的 VPC 配置。这些任务与 IT 人员执行的安全任务相同，无论他们的服务器位于何处。

本例中的 Oracle 实例在 AWS 或客户责任方面提供了一个有趣的案例研究。如果数据库在 EC2 实例上运行，则应用 Oracle 软件升级和补丁是客户的责任。但是，如果数据库作为 Amazon RDS 实例运行，则应用 Oracle 软件升级和补丁是 AWS 的责任。由于 Amazon RDS 是一种托管数据库产品，因此耗时的数据库管理任务（包括配置、备份、软件修补、监控和硬件扩展）由 AWS 处理。要了解更多信息，请参阅 https://docs.aws.amazon.com/whitepapers/latest/oracle-database-aws-best-practices/oracle-database-aws-best-practices.html 上的“在 AWS 上运行 Oracle 数据库的最佳实践”了解详情。

![屏幕截图 2024-11-18 192128](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 192128.jpg)

现在，考虑这个额外的案例，其中客户使用此处显示的 AWS 服务和资源。谁负责维护安全？AWS 还是客户？

![屏幕截图 2024-11-18 192219](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 192219.jpg)

客户使用 Amazon S3 存储数据。客户使用 Amazon VPC 配置了虚拟私有云 (VPC)，并在 VPC 中的 EC2 实例上运行 Web 服务器。客户将 Internet 网关配置为 VPC 的一部分，以便可以使用 AWS 管理控制台或 AWS 命令行界面 (AWS CLI) 访问 Web 服务器。当客户使用 AWS CLI 时，连接需要使用安全 Shell (SSH) 密钥。

**Section 1 key takeaways**

本模块此部分的一些关键要点包括：

- AWS 和客户共同承担安全责任
  - AWS 负责 security **of** the cloud
  - 客户负责security **in** the cloud
- **AWS 负责保护运行 AWS 云服务的基础设施**（包括硬件、软件、网络和设施）
- 对于归类为基础设施即服务 (IaaS) 的服务，**客户负责执行必要的安全配置和管理任务**
  - 例如，客户操作系统更新和安全补丁、防火墙、安全组配置





### Section 2: AWS Identity and Access Management (IAM)

![屏幕截图 2024-11-18 192545](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 192545.jpg)

**AWS Identity and Access Management (IAM)** 允许您控制对 AWS 云中的计算、存储、数据库和应用程序服务的访问。IAM 可用于处理身份验证以及指定和执行授权策略，以便您可以指定哪些用户可以访问哪些服务。

IAM 是一种工具，可集中管理对 AWS 账户中资源的启动、配置、管理和终止的访问权限。它提供对资源访问权限的精细控制，包括能够精确指定用户有权对每项服务进行哪些 **API** 调用。无论您使用 AWS 管理控制台、AWS CLI 还是 AWS 软件开发工具包 (SDK)，对 AWS 服务的每次调用都是一次 API 调用。

使用 IAM，您可以管理哪些资源可供谁访问以及如何访问这些资源。您可以向不同的人授予不同资源的不同权限。例如，您可以允许某些用户完全访问 Amazon EC2、Amazon S3、Amazon DynamoDB、Amazon Redshift 和其他 AWS 服务。但是，对于其他用户，您可能只允许其对几个 S3 存储桶进行只读访问。同样，您可以向其他用户授予仅管理特定 EC2 实例的权限。您还可以允许一些用户仅访问账户账单信息，而不允许访问其他任何内容。

IAM 是您的 AWS 账户的一项功能，无需额外付费。

![屏幕截图 2024-11-18 192707](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 192707.jpg)

要了解如何使用 IAM 保护您的 AWS 账户，了解四个 IAM 组件各自的作用和功能非常重要。

**IAM user**是在 AWS 账户中定义的人员或应用程序，必须对 AWS 产品进行 API 调用。每个用户在 AWS 账户中都必须具有唯一的名称（名称中不能有空格），并且必须拥有一组不与其他用户共享的安全凭证。这些凭证不同于 AWS 账户根用户安全凭证。每个用户只能在一个 AWS 账户中定义。

**IAM group**是 IAM 用户的集合。您可以使用 IAM 组来简化为多个用户指定和管理权限的过程。

**IAM policy**是定义权限的文档，用于确定用户可以在 AWS 账户中执行哪些操作。策略通常授予对特定资源的访问权限，并指定用户可以对这些资源执行哪些操作。策略还可以明确拒绝访问。

**IAM role**是用于授予对 AWS 账户中特定 AWS 资源的临时访问权限的工具。

![屏幕截图 2024-11-18 192957](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 192957.jpg)

**Authentication**是一个基本的计算机安全概念：用户或系统必须首先证明自己的身份。想象一下，当您去机场并希望通过机场安检以便赶上航班时，您如何验证自己的身份。在这种情况下，您必须向安检人员出示某种形式的身份证明，以证明您是谁，然后才能进入禁区。类似的概念适用于获取对云中 AWS 资源的访问权限。

定义 IAM 用户时，您可以选择允许用户使用哪种类型的访问权限来访问 AWS 资源。您可以为用户分配两种不同类型的访问权限：编程访问权限和 AWS 管理控制台访问权限。您可以仅分配编程访问权限、仅分配控制台访问权限，也可以分配两种类型的访问权限。

如果您授予**programmatic access**权限，则 IAM 用户在使用 AWS CLI、AWS SDK 或其他开发工具进行 AWS API 调用时，将需要提供访问**access key ID** 和**secret access key**。

如果您授予 **AWS Management Console access**权限，则 IAM 用户将需要填写浏览器登录窗口中显示的字段。系统将提示用户提供 12 位账户 ID 或相应的账户别名。用户还必须输入其 IAM 用户名和密码。如果为用户启用了**multi-factor authentication** (MFA)，系统还将提示他们输入身份验证代码。



![屏幕截图 2024-11-18 193231](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 193231.jpg)

可以使用 AWS 管理控制台、AWS CLI 或通过 SDK 和 API 访问 AWS 服务和资源。为了提高安全性，我们建议启用 MFA。

使用 MFA，用户和系统除了提供常规登录凭证之外，还必须提供 **MFA token**，然后才能访问 AWS 服务和资源。

生成 MFA 身份验证令牌的选项包括**virtual MFA-compliant applications**（例如 Google Authenticator 或 Authy 2-Factor Authentication）、**U2F security key devices**和**hardware MFA devices**。

![屏幕截图 2024-11-18 193429](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 193429.jpg)



**Authorization**是确定应授予用户、服务或应用程序哪些权限的过程。用户通过身份验证后，必须获得授权才能访问 AWS 服务。

默认情况下，IAM 用户无权访问 AWS 账户中的任何资源或数据。相反，您必须通过创建策略（JavaScript 对象表示法 (JSON) 格式的文档）明确向用户、组或角色授予权限。策略列出了允许或拒绝访问 AWS 账户中资源的权限。

![image-20241118193522017](C:\Users\EACH\AppData\Roaming\Typora\typora-user-images\image-20241118193522017.png)

要将权限分配给用户、组或角色，您必须创建 IAM 策略（或在账户中找到现有策略）。没有默认权限。默认情况下，除非明确允许，否则账户中的所有操作都会被拒绝（隐式拒绝）。任何您未明确允许的操作都会被拒绝。任何您明确拒绝的操作都会被拒绝。

**principle of least privilege 最小权限原则**是计算机安全中的一个重要概念。它提倡您根据用户的需求，仅向用户授予所需的最小用户权限。创建 IAM 策略时，最佳做法是遵循授予最小权限的安全建议。确定用户需要能够执行的操作，然后为他们制定策略，使用户仅执行这些任务。从一组最小权限开始，并根据需要授予其他权限。这样做比从太宽泛的权限开始，然后尝试锁定授予的权限更安全。

请注意，IAM 服务配置的范围是全球性的。这些设置不是在 AWS 区域级别定义的。IAM 设置适用于所有 AWS 区域

![image-20241118193807305](C:\Users\EACH\AppData\Roaming\Typora\typora-user-images\image-20241118193807305.png)

IAM 策略是授予实体的权限的正式声明。策略可以附加到任何 IAM 实体。实体包括用户、组、角色或资源。例如，您可以将策略附加到 AWS 资源，该策略将阻止所有不是来自已批准的 Internet 协议 (IP) 地址范围的请求。策略指定允许哪些操作、允许对哪些资源执行操作以及当用户请求访问资源时会产生什么效果。

评估策略的顺序对评估结果没有影响。所有策略都会被评估，结果始终是允许或拒绝请求。当发生冲突时，将应用限制性最强的策略。

IAM 策略有两种类型。**Identity-based policies**是您可以附加到主体（或身份）（例如 IAM 用户、角色或组）的权限策略。这些策略控制身份可以执行哪些操作、对哪些资源执行哪些操作以及在什么条件下执行。基于身份的策略可以进一步分类为：

- **Managed policies** – 基于身份的独立策略，可将其附加到 AWS 账户中的多个用户、组和角色
- **Inline policies **– 您创建和管理的策略，直接嵌入到单个用户组或角色中。

**Resource-based policies** 是附加到资源（例如 S3 存储桶）的 JSON 策略文档。这些策略控制指定主体可以对该资源执行哪些操作以及在什么条件下执行。

![屏幕截图 2024-11-18 194145](F:\Github_Workspace\Self_Study\Study-Supervision-Plan\asset\image\24.11.18.1)

如前所述，IAM 策略文档是用 JSON 编写的。

示例 IAM 策略仅授予用户对以下资源的访问权限：

- DynamoDB 表，其名称由 table-name 表示。
- AWS 账户的 S3 存储桶，其名称由 bucket-name 表示，以及其中包含的所有对象。

IAM 策略还包含显式拒绝 ("Effect":"Deny") 元素。**NotResource** 元素有助于确保用户无法使用除策略中指定的操作和资源之外的任何其他 DynamoDB 或 S3 操作或资源 — 即使已在另一个策略中授予权限。显式拒绝语句优先于允许语句。

![屏幕截图 2024-11-18 194238](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 194238.jpg)

基于身份的策略附加到用户、组或角色，而基于资源的策略附加到资源，例如 S3 存储桶。这些策略指定谁可以访问资源以及他们可以对资源执行哪些操作。

基于资源的策略仅以**inline内联**方式定义，这意味着您在资源本身上定义策略，而不是创建附加的单独 IAM 策略文档。例如，要在 S3 存储桶上创建 S3 存储桶策略（一种基于资源的策略），请导航到存储桶，单击**Permissions权限**选项卡，单击**Bucket Policy存储桶**策略按钮，然后在那里定义 JSON 格式的策略文档。Amazon S3 访问控制列表 (ACL) 是基于资源的策略的另一个示例。

该图显示了授予用户 MaryMajor 访问名为 photos 的 S3 存储桶中对象的两种不同方式。在左侧，您会看到一个基于身份的策略示例。授予对 S3 存储桶访问权限的 IAM 策略已附加到 MaryMajor 用户。在右侧，您会看到一个基于资源的策略示例。photosbucket 的 S3 存储桶策略指定允许用户 MaryMajor 列出和读取存储桶中的对象。

请注意，您可以在存储桶策略中定义拒绝语句，以限制特定 IAM 用户的访问，即使用户在单独的基于身份的策略中获得访问权限。显式拒绝语句始终优先于任何允许语句。

IAM 策略使您能够微调授予 IAM 用户、组和角色的权限。

当 IAM 确定是否允许某项权限时，IAM 首先检查是否存在任何适用的**explicit denial policy显式拒绝策略**。如果不存在显式拒绝，则检查是否存在任何适用的**explicit allow policy显式允许策略**。如果既不存在显式拒绝也不存在显式允许策略，则 IAM 将恢复默认设置，即拒绝访问。此过程称为**implicit deny隐式拒绝**。仅当请求的操作未被显式拒绝且被显式允许时，用户才被允许执行该操作。

当您制定 IAM 策略时，很难确定是否将授予 IAM 实体对资源的访问权限。https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_testing-policies.html 上的 IAM 策略模拟器是用于测试和排除 IAM 策略故障的有用工具。

![屏幕截图 2024-11-18 194538](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 194538.jpg)

 

**IAM group组**是 IAM 用户的集合。IAM 组提供了一种为用户集合指定权限的便捷方式，可以更轻松地管理这些用户的权限。

例如，您可以创建一个名为 Developers 的 IAM 组，并将一个或多个 IAM 策略附加到 Developers 组，以授予开发人员通常需要的 AWS 资源访问权限。您随后添加到 Developer 组的任何用户都将自动拥有分配给该组的权限。在这种情况下，您无需将一个或多个 IAM 策略直接附加到用户。如果新用户加入您的组织并应被授予开发人员权限，您只需将该用户添加到 Developers 组即可。同样，如果某人在您的组织中换了工作，您无需编辑该用户的权限，只需将该用户从组中删除即可

IAM 组的重要特征：

- 一个组可以包含多个用户，一个用户可以属于多个组。
- 组不能嵌套。一个组只能包含用户，一个组不能包含其他组。
- 没有默认组会自动包含 AWS 账户中的所有用户。如果您想要一个包含所有账户用户的组，则需要创建该组并将每个新用户添加到其中。

**IAM role**是您可以在账户中创建具有特定权限的 IAM 身份。IAM 角色类似于 IAM 用户，因为它也是您可以附加权限策略的 AWS 身份，并且这些权限决定了该身份在 AWS 中可以做什么和不能做什么。但是，角色并非唯一地与一个人相关联，而是由任何需要它的人担任。此外，角色没有与之关联的标准长期凭证（例如密码或访问密钥）。相反，当您担任角色时，该角色会为您的角色会话提供临时安全凭证。

您可以使用角色将访问权限委托给通**常无权访问您的 AWS 资源的用户、应用程序或服务**。例如，您可能希望授予 AWS 账户中的用户访问他们通常没有的资源的权限，或授予一个 AWS 账户中的用户访问另一个账户中的资源的权限。或者，您可能希望允许移动应用程序使用 AWS 资源，但您不想在应用程序中嵌入 AWS 密钥（密钥可能难以轮换，并且用户可能会提取密钥并滥用它们）。此外，有时您可能希望向已拥有在 AWS 之外定义的身份（例如在您的公司目录中）的用户授予 AWS 访问权限。或者，您可能希望向第三方授予对您账户的访问权限，以便他们可以对您的资源进行审计。

对于所有这些示例用例，IAM 角色都是实施云部署的重要组成部分。

![屏幕截图 2024-11-18 194816](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 194816.jpg)

在图中，开发人员在 EC2 实例上运行应用程序，该应用程序需要访问名为照片的 S3 存储桶。管理员创建 IAM 角色并将该角色附加到 EC2 实例。该角色包括授予对指定 S3 存储桶的只读访问权限的权限策略。它还包括允许 EC2 实例承担角色并检索临时凭证的信任策略。当应用程序在实例上运行时，它可以使用角色的临时凭证访问照片存储桶。管理员无需授予应用程序开发人员访问照片存储桶的权限，开发人员也无需共享或管理凭证。

**Section 2 key takeaways**

本模块此部分的一些关键要点包括：

- **IAM policies**使用 JavaScript 对象表示法 (JSON) 构建并定义权限。
  - AM 策略可以附加到任何 **IAM entity**。
  - 实体包括 IAM 用户、IAM 组和 IAM 角色。
- **IAM user**为个人、应用程序或服务提供了一种向 AWS 进行身份验证的方法。
- **IAM group**是一种将相同策略附加到多个用户的简单方法。
- **IAM role**可以附加权限策略，并且可用于将临时访问权限委托给用户或应用程序。



### Section 3: Securing a new AWS account

![屏幕截图 2024-11-18 195252](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 195252.jpg)

首次创建 AWS 账户时，您首先要拥有一个可以完全访问账户中所有 AWS 服务和资源的单点登录身份。此身份称为 AWS 账户**root user**，可以使用创建账户时使用的电子邮件地址和密码登录 AWS 管理控制台来访问此身份。AWS 账户根用户拥有（并保留）对账户中所有资源的**完全**访问权限。因此，AWS 强烈建议您不要使用账户根用户凭证与账户进行日常交互。

相反，AWS 建议您使用 IAM 创建其他用户并按照最小权限原则为这些用户分配权限。例如，如果您需要管理员级权限，则可以创建一个 IAM 用户，授予该用户完全访问权限，然后使用这些凭证与账户进行交互。稍后，如果您需要撤销或修改您的权限，则可以删除或修改与该 IAM 用户关联的任何策略。

此外，如果您有多个用户需要访问该账户，您可以为每个用户创建唯一的凭证，并定义哪个用户有权访问哪些资源。例如，您可以创建对 AWS 账户中的资源具有只读访问权限的 IAM 用户，并将这些凭证分发给需要读取访问权限的用户。您应避免与多个用户共享相同的凭证。

虽然不应使用账户根用户执行常规任务，但有些任务只能通过以账户根用户身份登录才能完成。这些任务的完整列表在需要根用户凭证的任务 AWS 文档页面中详细说明，网址为 https://docs.aws.amazon.com/general/latest/gr/root-vs-iam.html#aws_tasks-that-require-root。

![屏幕截图 2024-11-18 195432](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 195432.jpg)

要停止使用账户根用户，请执行以下步骤：

1.登录账户根用户后，为自己创建一个启用 AWS 管理控制台访问权限的 IAM 用户（但不要向该用户附加任何权限）。如果需要，请保存 IAM 用户访问密钥。

2.接下来，创建一个 IAM 组，为其命名（例如 FullAccess），并将 IAM 策略附加到该组，以授予对您将使用的至少一些服务的完全访问权限。接下来，将 IAM 用户添加到该组。

3.禁用并删除您的账户根用户访问密钥（如果存在）。

4.为所有用户启用密码策略。从 IAM 控制面板页面复制 **IAM users sign-in link**。然后，以账户根用户身份注销。

5.浏览到您复制的 IAM 用户登录链接，然后使用您的新 IAM 用户凭证登录账户。

6.将您的账户根用户凭证存储在安全的地方。

另一个建议的保护新 AWS 账户安全的步骤是要求账户根用户登录和所有其他 IAM 用户登录进行多重身份验证 (MFA)。

您还可以使用 MFA 来控制编程访问。有关详细信息，请参阅配置受 MFA 保护的 API 访问，网址为 https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_mfa_configure-api-require.html。您有几种选项可用于检索启用 MFA 后登录所需的 MFA 令牌。选项包括虚拟 MFA 兼容应用程序（例如 Google Authenticator 和 AuthyAuthenticator）、U2F 安全密钥设备和提供密钥卡或显示卡的硬件 MFA 选项。

AWS CloudTrail 是一项服务，可记录您账户中所有资源的 API 请求。通过这种方式，它可对您的账户进行操作审计。

默认情况下，所有 AWS 账户在创建账户时都会启用 AWS CloudTrail，它会记录过去 90 天的账户管理事件活动。您可以查看和下载过去 90 天的账户活动，以创建、修改和删除 CloudTrail 支持的服务的操作，而无需手动创建另一个跟踪。有关受支持服务的更多信息，请访问 https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-aws-service-specific-topics.html。

要启用过去 90 天以外的 CloudTrail 日志保留，并在发生指定事件时启用警报，请创建一个新跟踪（幻灯片中以高级别描述）。有关如何在 AWS CloudTrail 中创建跟踪的详细分步说明，请参阅 AWS 文档中的创建跟踪，网址为 https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-create-a-trail-using-the-console-first-time.html。

为保护新 AWS 账户，建议采取的另一个步骤是启用账单报告，例如 AWS 成本和使用情况报告。账单报告提供有关您对 AWS 资源的使用情况以及该使用情况的估计成本的信息。AWS 将报告发送到您指定的 Amazon S3 存储桶，并且 AWS 每天至少更新一次报告。

AWS 成本和使用情况报告跟踪 AWS 账户中的使用情况并提供按小时或按天估算的费用。

有关如何创建 AWS 成本和使用情况报告的详细信息，请参阅 AWS 文档：https://docs.aws.amazon.com/cur/latest/userguide/cur-create.html。

**Section 3 key takeaways**

本模块此部分的关键要点均与保护 AWS 账户的最佳实践有关。这些最佳实践建议包括：

- 使用多因素身份验证 (MFA) 保护登录。
- 删除账户根用户访问密钥。
- 创建单个 IAM 用户并根据最小特权原则授予权限。
- 使用组为 IAM 用户分配权限。
- 配置强密码策略。
- 使用角色而不是共享凭证进行委派。•使用 AWS CloudTrail 监控账户活动。



### Section 4: Securing accounts

![屏幕截图 2024-11-18 195751](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 195751.jpg)

**AWS Organizations** 是一项账户管理服务，可让您将多个 AWS 账户整合到您创建并集中管理的组织中。这里重点介绍 AWS Organizations 提供的安全功能。

一个有用的安全功能是，您可以**group accounts into organizational units** **(OU)**，并将不同的访问策略附加到每个 OU。例如，如果您的账户只应被允许访问符合某些监管要求的 AWS 服务，则可以将这些账户放入一个 OU。然后，您可以定义一个策略来阻止 OU 访问不符合这些监管要求的服务，然后将该策略附加到 OU。

另一个安全功能是 **AWS Organizations integrates with and supports IAM**。AWS Organizations 通过让您控制账户或账户组中的用户和角色可以执行的操作，将该控制扩展到账户级别。生成的权限是 AWS Organizations 策略设置允许的内容与 IAM 在该用户或角色的账户中明确授予的权限的逻辑交集。用户只能访问 AWS Organizations 策略和 IAM 策略**都**允许的内容。

最后，AWS Organizations **provides service control policies (SCP)**，使您能够指定组织中成员账户可以拥有的最大权限。在 SCP 中，您可以限制每个成员账户中的用户和角色可以访问哪些 AWS 服务、资源和单个操作。**这些限制甚至会覆盖成员账户的管理员**。当 AWS Organizations 阻止对服务、资源或 API 操作的访问时，该账户中的用户或角色无法访问它，即使成员账户的管理员明确授予此类权限。



![屏幕截图 2024-11-18 200030](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 200030.jpg)

以下是对 AWS Organizations 的服**Service control policies (SCP)** 功能的详细信息。

SCP 可集中控制组织中所有账户的**最大可用权限**，使您能够确保您的账户符合组织的访问控制准则。SCP 仅在启用了所有功能（包括整合账单）的组织中可用。有关启用功能的更多信息，请参阅 https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_org_support-all-features.html。

如果您的组织仅启用了整合账单功能，则 SCP 不可用。有关启用 SCP 的说明，请参阅 https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_policies.html#enable_policies_on_root 上的启用和禁用根上的策略类型。

**SCP 类似于 IAM 权限策略**，它们使用几乎相同的语法。但是，SCP 从不授予权限。相反，SCP 是 JSON 策略，用于指定组织或 OU 的最大权限。将 SCP 附加到组织根或组织单位 (OU) 可为组织根或 OU 中的账户可以执行的操作定义保护措施。但是，它不能替代每个账户内管理良好的 IAM 配置。您仍必须将 IAM 策略附加到组织账户中的用户和角色，以实际向他们授予权限。有关 IAM 策略的更多信息，请参阅 https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html。

![屏幕截图 2024-11-18 200241](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 200241.jpg)

**AWS Key Management Service (AWS KMS)** 是一项服务，可让您创建和管理加密密钥，并控制各种 AWS 服务和应用程序中加密的使用。AWS KMS 是一项安全且有弹性的服务，它使用根据**Federal Information ProcessingStandards (FIPS) 140-2** 验证的硬件安全模块 (HSM)（或正在验证中）来保护您的密钥。AWS KMS 还与 AWS CloudTrail 集成，为您提供所有密钥使用情况的日志，以帮助满足您的监管和合规性需求。

**Customer master keys (CMKs)** 用于控制对加密和解密数据的数据加密密钥的访问。您可以随时创建新密钥，并管理谁有权访问这些密钥以及谁可以使用它们。您还可以将密钥从您自己的密钥管理基础设施导入 AWS KMS。

AWS KMS 与大多数 AWS 服务集成，这意味着您可以使用 AWS KMS CMK 来控制存储在这些服务中的数据的加密。要了解更多信息，请参阅 AWS Key Management Service 功能：https://aws.amazon.com/kms/features/。

![屏幕截图 2024-11-18 200410](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 200410.jpg)

Amazon Cognito 提供解决方案来控制从应用程序访问 AWS 资源。您可以定义角色并将用户映射到不同的角色，以便您的应用程序只能访问每个用户授权的资源。

Amazon Cognito 使用常见的身份管理标准，例如**Security Assertion Markup Language (SAML) 2.0**。SAML 是与应用程序和服务提供商交换身份和安全信息的开放标准。支持 SAML 的应用程序和服务提供商允许您使用公司目录凭证（例如 Microsoft Active Directory 中的用户名和密码）登录。借助 SAML，您可以使用单点登录 (SSO) 使用一组凭证登录所有启用 SAML 的应用程序。

Amazon Cognito 可帮助您满足多项安全性与合规性要求，包括医疗保健公司和商家等受到严格监管的组织的要求。Amazon Cognito 符合美国《健康保险流通与责任法案》（HIPAA）的使用要求，有关 HIPAA 的更多信息，请访问 https://aws.amazon.com/compliance/hipaa-compliance/。它还可用于符合以下标准的工作负载：支付卡行业数据安全标准 (PCI DSS)，有关 PCI DSS 的更多信息，请访问 https://aws.amazon.com/compliance/pci-dss-level-1-faqs/；美国注册会计师协会 (AICPA) 服务组织控制 (SOC)，有关 SOC 的更多信息，请访问 https://aws.amazon.com/compliance/soc-faqs/；国际标准化组织 (ISO) 和国际电工委员会 (IEC) 标准。有关 ISO/IEC 27001 的更多信息，请访问 https://aws.amazon.com/compliance/iso-27001-faqs/；有关 ISO/IEC 27017 的更多信息，请访问 https://aws.amazon.com/compliance/iso-27017-faqs/；有关 ISO/IEC 27018 的更多信息，请访问 https://aws.amazon.com/compliance/iso-27018-faqs/；有关 ISO 9001 的更多信息，请访问 https://aws.amazon.com/compliance/iso-9001-faqs/。

![屏幕截图 2024-11-18 200520](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 200520.jpg)

**AWS Shield** 是一种托管的分布式拒绝服务 (DDoS) 防护服务，可保护在 AWS 上运行的应用程序。它提供始终在线的检测和自动内联缓解措施，可最大限度地减少应用程序停机时间和延迟，因此无需联系 AWS Support 即可享受 DDoS 防护。

AWS Shield 可帮助保护您的网站免受所有类型的 DDoS 攻击，包括基础设施层攻击（如用户数据报协议或 UDP 洪水）、状态耗尽攻击（如 TCP SYN 洪水）和应用程序层攻击（如 HTTP GET 或 POST 洪水）。有关示例，请参阅 AWS WAF 开发人员指南，网址为 https://docs.aws.amazon.com/waf/latest/developerguide/waf-chapter.html。

**AWS Shield Standard** 会自动为所有 AWS 客户启用，无需额外付费。

**AWS Shield Advanced** 是一项可选的付费服务。 AWS Shield Advanced 为在 Amazon EC2、Elastic Load Balancing、Amazon CloudFront、AWS Global Accelerator 和 Amazon Route 53 上运行的应用程序提供针对更复杂、更大规模攻击的额外保护。 AWS Shield Advanced 可供所有客户使用。但是，要联系 DDoS 响应团队，客户需要获得 AWS Support 的企业支持或业务支持。

### Section 5: Securing data on AWS

![屏幕截图 2024-11-18 200653](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 200653.jpg)

当您的目标是保护数字数据时，**Data encryption**是必不可少的工具。数据加密将可读数据编码，使任何无法访问可用于解码的密钥的人都无法读取数据。因此，即使攻击者获得了您的数据的访问权限，他们也无法理解它。

**Data at rest 静态数据**是指物理存储在磁盘或磁带上的数据。

您可以在 AWS 上创建加密文件系统，以便使用开放标准高级加密标准 (AES)-256 加密算法对所有数据和元数据进行静态加密。使用 AWS KMS 时，加密和解密将自动且透明地处理，因此您无需修改应用程序。如果您的组织受公司或监管政策的约束，需要对静态数据和元数据进行加密，AWS 建议在存储数据的所有服务上启用加密。您可以加密存储在 AWS KMS 支持的任何服务中的数据。请参阅 AWS 服务如何使用 AWS KMS，获取受支持服务的列表，网址为 https://docs.aws.amazon.com/kms/latest/developerguide/service-integration.html。

![屏幕截图 2024-11-18 200811](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 200811.jpg)

**Data in transit 传输中的数据**是指在网络上移动的数据。传输中的数据加密是通过使用传输层安全性 (TLS) 1.2 和开放标准 AES-256 密码来实现的。TLS 以前称为安全套接字层 (SSL)。

**AWS Certificate Manager AWS 证书管理器**是一项服务，可让您预置、管理和部署 SSL 或 TLS 证书，以用于 AWS 服务和内部连接的资源。SSL 或 TLS 证书用于保护网络通信并建立互联网上网站的身份以及私有网络上的资源。使用 AWS 证书管理器，您可以请求证书，然后将其部署在 AWS 资源（例如负载均衡器或 CloudFront 分发）上。AWS 证书管理器还处理证书续订。

通过 HTTP 运行的 Web 流量并不安全。但是，通过**Secure 安全 HTTP (HTTPS)** 运行的流量使用 TLS 或 SSL 进行加密。由于通信的双向加密，HTTPS 流量可防止窃听和中间人攻击。

第二个示例展示了如何使用 AWS Storage Gateway，这是一种混合云存储服务，可提供对 AWS 云存储的本地访问。在此示例中，存储网关通过互联网连接到 Amazon S3，并且该连接会对传输中的数据进行加密。

![屏幕截图 2024-11-18 201005](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 201005.jpg)

默认情况下，所有 Amazon S3 存储桶都是私有的，只有明确授予访问权限的用户才能访问。管理和控制对 Amazon S3 数据的访问至关重要。AWS 提供了许多工具和选项来控制对 S3 存储桶或对象的访问，包括：

- 使用 **Amazon S3 Block Public Access** 阻止公共访问。这些设置会覆盖任何其他策略或对象权限。为所有您不希望公开访问的存储桶启用阻止公共访问。此功能提供了一种避免意外暴露 Amazon S3 数据的简单方法。
- 编写 **IAM policies**，指定可以访问特定存储桶和对象的用户或角色。此方法已在本模块前面详细讨论过。
- 编写**bucket policies**，定义对特定存储桶或对象的访问权限。此选项通常在用户或系统无法使用 IAM 进行身份验证时使用。存储桶策略可以配置为授予跨 AWS 账户的访问权限或授予对 Amazon S3 数据的公开或匿名访问权限。如果使用存储桶策略，则应仔细编写并进行全面测试。您可以在存储桶策略中指定拒绝语句来限制访问。即使用户拥有附加到用户的基于身份的策略中授予的权限，访问也会受到限制。
- 在您的存储桶和对象上设置**access control lists (ACLs)** 。ACL 不太常用（ACL 早于 IAM）。如果您确实使用 ACL，请不要设置过于开放或宽松的访问权限
- **AWS Trusted Advisor** 提供了存储桶权限检查功能，该功能是一种有用的工具，可用于发现您账户中的任何存储桶是否具有授予全局访问权限的权限。



### Section6: Working to ensure compliance

![屏幕截图 2024-11-18 201251](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 201251.jpg)

AWS 与外部认证机构和独立审计师合作，为客户提供有关 AWS 建立和运营的政策、流程和控制的信息。

作为您可以使用 AWS 服务实现合规性目标的认证示例，请考虑 ISO/IEC 27001:2013 认证。它指定了建立、实施、维护和持续改进信息安全管理系统的要求。此认证的基础是制定和实施严格的安全计划，其中包括制定和实施信息安全管理系统。信息安全管理系统定义了 AWS 如何以整体、全面的方式永久管理安全性。



**Module summary**   

总之，在本模块中，您学习了如何：

- 识别共享责任模型• 确定客户和 AWS 的责任
- 识别 IAM 用户、组和角色
-  描述 IAM 中的不同类型的安全凭证
-  确定保护新 AWS 账户的步骤
-  探索 IAM 用户和组
-  了解如何保护 AWS 数据
-  识别 AWS 合规性计划



## Module 5: Networking and Content Delivery

本模块讨论以下主题：

- 网络基础知识
- Amazon Virtual Private Cloud (Amazon VPC)
- VPC 网络
- VPC 安全
- Amazon Route 53
- Amazon CloudFront

本模块包含一些活动，要求您标记网络图并设计基本的 VPC 架构。

您将观看录制的演示，以了解如何使用 VPC 向导创建具有公有子网和私有子网的 VPC。



完成本模块后，您应该能够：

- 认识网络基础知识
- 使用 Amazon VPC 描述云中的虚拟网络
- 标记网络图
- 设计基本的 VPC 架构
- 指出构建 VPC 的步骤•识别安全组
- 创建自己的 VPC 并向其中添加其他组件以生成自定义网络
- 识别 Amazon Route 53 的基础知识
- 认识 Amazon CloudFront 的优势



### Section 1: Networking basics

在本节中，您将回顾一些基本的网络概念，这些概念为您理解 AWS 网络服务 Amazon Virtual Private Cloud (Amazon VPC) 提供了必要的基础。

计算机网络是连接在一起以共享资源的两台或多台客户端计算机。网络可以逻辑地划分为子网。联网需要网络设备（如路由器或交换机）将所有客户端连接在一起并实现它们之间的通信。

![屏幕截图 2024-11-18 203028](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 203028.jpg)

网络中的每个客户端计算机都有一个唯一的 Internet 协议 (IP) 地址来标识它。IP 地址是十进制格式的数字标签。计算机将该十进制数转换为二进制格式。

在此示例中，IP 地址为 192.0.2.0。IP 地址的四个以点 (.) 分隔的数字中的每一个都代表八进制数字格式的 8 位。这意味着四个数字中的每一个都可以是 0 到 255 之间的任何数字。IP 地址的四个数字的总和为二进制格式的 32 位。

| IPv4 和 IPv6 地址   |                                         |
| ------------------- | --------------------------------------- |
| IPv4（32 位）地址:  | 192.0.2.0                               |
| IPv6（128 位）地址: | 2600:1f18:22ba:8c00:ba86:a05e:a5ba:00FF |

32 位 IP 地址称为 IPv4 地址。还有 128 位的 IPv6 地址。

IPv6 地址可以容纳更多用户设备。

IPv6 地址由八组四个字母和数字组成，这些字母和数字以冒号 (:) 分隔。在此示例中，IPv6 地址为 2600:1f18:22ba:8c00:ba86:a05e:a5ba:00FF。IPv6 地址的八个以冒号分隔的组中的每一个都代表十六进制数字格式的 16 位。这意味着八个组中的每一个都可以是从 0 到 FFFF 的任意值。IPv6 地址的八个组的总和为二进制格式的 128 位。

![屏幕截图 2024-11-18 203248](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 203248.jpg)

描述网络的常用方法是无类别域间路由 (CIDR)。CIDR 地址的表示方法如下：

- IP 地址（即网络的第一个地址）
- 接下来是斜杠字符 (/)
- 最后是一个数字，表示必须为网络标识符固定或分配多少位路由前缀

不固定的位允许改变。CIDR 是一种表达一组彼此连续的 IP 地址的方式。

在此示例中，CIDR 地址为 192.0.2.0/24。最后一个数字（24）表示前 24 位必须是固定的。最后 8 位是灵活的，这意味着网络可以使用 28 个（或 256 个）IP 地址，范围从 192.0.2.0 到 192.0.2.255。第四个十进制数字允许从 0 变为 255。

如果 CIDR 为 192.0.2.0/16，最后一个数字 (16) 表示前 16 位必须是固定的。后 16 位是灵活的，这意味着网络有 216 个（或 65,536 个）IP 地址可用，范围从 192.0.0.0 到 192.0.255.255。第三和第四个十进制数字可以分别从 0 变为 255。

有两种特殊情况：

- 固定 IP 地址，其中每一位都是固定的，代表单个 IP 地址（例如，192.0.2.0/32）。当您想要设置防火墙规则并授予特定主机访问权限时，这种类型的地址很有用。
- 互联网中每个比特都是灵活的，表示为 0.0.0.0/0

![屏幕截图 2024-11-18 203413](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 203413.jpg)

Open Systems Interconnection 开放系统互连 (OSI) 模型是一种概念模型，用于解释数据如何在网络上传输。它由七层组成，并显示了在每一层发送数据时使用的通用协议和地址。例如，集线器和交换机在第 2 层（数据链路层）工作。路由器在第 3 层（网络层）工作。OSI 模型还可用于了解虚拟私有云 (VPC) 中的通信方式，您将在下一节中了解这一点。



### Section 2: Amazon VPC

本地网络的许多概念都适用于基于云的网络，但设置网络的大部分复杂性已被抽象化，同时又不牺牲控制、安全性和可用性。在本节中，您将了解 Amazon VPC 以及 VPC 的基本组件。

![屏幕截图 2024-11-18 203542](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 203542.jpg)

Amazon Virtual Private Cloud (Amazon VPC) 是一种服务，可让您预置 AWS 云中逻辑隔离的部分（称为虚拟私有云或 VPC），您可以在其中启动 AWS 资源。

Amazon VPC 让您可以控制虚拟网络资源，包括选择自己的 IP 地址范围、创建子网以及配置路由表和网络网关。您可以在 VPC 中使用 IPv4 和 IPv6 来安全访问资源和应用程序。

您还可以自定义 VPC 的网络配置。例如，您可以为可以访问公共互联网的 Web 服务器创建一个公共子网。您可以将后端系统（例如数据库或应用程序服务器）放置在没有公共互联网访问权限的私有子网中。

最后，您可以使用多层安全性，包括安全组和网络访问控制列表 (networkACL)，以帮助控制对每个子网中 Amazon Elastic Compute Cloud (Amazon EC2) 实例的访问。

![屏幕截图 2024-11-18 203638](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 203638.jpg)

Amazon VPC 可让您配置虚拟私有云 (VPC)。VPC 是逻辑上与 AWS 云中的其他虚拟网络隔离的虚拟网络。VPC 专用于您的账户。VPC 属于单个 AWS 区域，可以跨越多个可用区。创建 VPC 后，您可以将其划分为一个或多个子网。子网是 VPC 中的 IP 地址范围。子网属于单个可用区。

您可以在不同的可用区中创建子网以实现高可用性。子网通常分为公共子网和私有子网。公共子网可以直接访问互联网，但私有子网则不能。

![屏幕截图 2024-11-18 203723](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 203723.jpg)

IP 地址使 VPC 中的资源能够通过互联网相互通信并与资源通信。创建 VPC 时，会为其分配一个 IPv4 CIDR 块（一系列私有 IPv4 地址）。创建 VPC 后，您无法更改地址范围，因此务必谨慎选择。IPv4 CIDR 块可能大到 /16（即 216，即 65,536 个地址），也可能小到 /28（即 24，即 16 个地址）。

您可以选择将 IPv6 CIDR 块与您的 VPC 和子网关联，并将该块中的 IPv6 地址分配给 VPC 中的资源。IPv6 CIDR 块具有不同的块大小限制。

子网的 CIDR 块可以与 VPC 的 CIDR 块相同。在这种情况下，VPC 和子网的大小相同（VPC 中的单个子网）。此外，子网的 CIDR 块可以是 VPC 的 CIDR 块的子集。此结构允许定义多个子网。如果您在 VPC 中创建多个子网，则子网的 CIDR 块不能重叠。您不能在同一个 VPC 中有重复的 IP 地址。

![屏幕截图 2024-11-18 203939](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 203939.jpg)

当您创建子网时，它需要自己的 CIDR 块。对于您指定的每个 CIDR 块，AWS 会在该块内保留五个 IP 地址，这些地址不可用。AWS 保留这些 IP 地址用于：

- 网络地址
- VPC 本地路由器（内部通信）
- 域名系统 (DNS) 解
- 未来使用
- 网络广播地址

例如，假设您创建一个 IPv4 CIDR 块为 10.0.0.0/24 的子网（总共有 256 个 IP 地址）。该子网有 256 个 IP 地址，但只有 251 个可用，因为有 5 个被保留。

![屏幕截图 2024-11-18 204025](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 204025.jpg)

当您创建 VPC 时，该 VPC 中的每个实例都会自动获得一个私有 IP 地址。您还可以通过修改子网的自动分配公有 IP 地址属性，在创建实例时请求分配一个公有 IP 地址。

弹性 IP 地址是专为动态云计算而设计的静态公共 IPv4 地址。您可以将弹性 IP 地址与您账户中任何 VPC 的任何实例或网络接口关联。使用弹性 IP 地址，您可以通过快速将地址重新映射到 VPC 中的另一个实例来掩盖实例故障。将弹性 IP 地址与网络接口关联比将其直接与实例关联具有优势。您只需一步即可将网络接口的所有属性从一个实例移动到另一个实例。

使用弹性 IP 地址时可能会产生额外费用，因此当不再需要它们时释放它们非常重要。

![屏幕截图 2024-11-18 204133](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 204133.jpg)



弹性网络接口是一种虚拟网络接口，您可以将其附加到 VPC 中的实例或从中分离。当网络接口重新附加到另一个实例时，其属性将随之改变。当您将网络接口从一个实例移动到另一个实例时，网络流量将重定向到新实例。

VPC 中的每个实例都有一个默认网络接口（主网络接口），该接口分配有 VPC IPv4 地址范围内的私有 IPv4 地址。您无法将主网络接口与实例分离。您可以创建附加网络接口并将其附加到 VPC 中的任何实例。您可以附加的网络接口数量因实例类型而异。

![屏幕截图 2024-11-18 204217](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 204217.jpg)

路由表包含一组规则（称为路由），用于引导来自子网的网络流量。每个路由都指定一个目的地和一个目标。目的地是您希望子网中的流量流向的目标 CIDR 块。目标是发送目标流量的目标。默认情况下，您创建的每个路由表都包含用于 VPC 中通信的本地路由。您可以通过添加路由来自定义路由表。您无法删除用于内部通信的本地路由条目。

您的 VPC 中的每个子网都必须与一个路由表关联。主路由表是自动分配给您的 VPC 的路由表。它控制所有未明确与任何其他路由表关联的子网的路由。一个子网一次只能与一个路由表关联，但您可以将多个子网与同一个路由表关联。

**Section 2 key takeaways**

本模块此部分的一些关键要点包括：

- VPC 是 AWS 云的逻辑隔离部分。
- VPC 属于一个区域并需要一个 CIDR 块。
- VPC 细分为子网。
- 子网属于一个可用区并需要一个 CIDR 块。
- 路由表控制子网的流量。
- 路由表具有内置本地路由。
- 您向表中添加其他路由
- 无法删除本地路由。



### Section 3: VPC networking

![屏幕截图 2024-11-18 204502](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 204502.jpg)

**internet gateway 互联网网关**是一种可扩展、冗余且高度可用的 VPC 组件，可实现 VPC 中的实例与互联网之间的通信。互联网网关有两个用途：在 VPC 路由表中为可路由互联网的流量提供目标，并为分配了公有 IPv4 地址的实例执行网络地址转换。

要使子网公开，您需要将互联网网关连接到您的 VPC，并向路由表添加路由，以通过互联网网关将非本地流量发送到互联网 (0.0.0.0/0)。

![屏幕截图 2024-11-18 204630](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 204630.jpg)

**network address translation 网络地址转换 (NAT)** 网关允许私有子网中的实例连接到互联网或其他 AWS 服务，但阻止互联网与这些实例建立连接。

要创建 NAT 网关，您必须指定 NAT 网关应驻留在的公有子网。您还必须在创建 NAT 网关时指定要与该网关关联的弹性 IP 地址。创建 NAT 网关后，您必须更新与一个或多个私有子网关联的路由表，以将 Internet 绑定流量指向 NAT 网关。这样，私有子网中的实例就可以与 Internet 通信。

您还可以使用 VPC 中公有子网中的 NAT 实例来代替 NAT 网关。但是，NAT 网关是一种托管 NAT 服务，可提供更好的可用性、更高的带宽和更少的管理工作。对于常见用例，AWS 建议您使用 NAT 网关而不是 NAT 实例。

![屏幕截图 2024-11-18 204755](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 204755.jpg)

**VPC sharing**使客户能够与 AWS Organizations 中同一组织内的其他 AWS 账户共享子网。VPC 共享使多个 AWS 账户能够将其应用程序资源（例如 Amazon EC2 实例、Amazon Relational Database Service (Amazon RDS) 数据库、Amazon Redshift 集群和 AWS Lambda 函数）创建到共享的、集中管理的 VPC 中。在此模型中，拥有 VPC 的账户（所有者）与 AWS Organizations 中属于同一组织的其他账户（参与者）共享一个或多个子网。共享子网后，参与者可以在与其共享的子网中查看、创建、修改和删除其应用程序资源。参与者无法查看、修改或删除属于其他参与者或 VPC 所有者的资源。

VPC 共享具有多种优势：

- 职责分离 – 集中控制的 VPC 结构、路由、IP 地址分配
- 所有权 – 应用程序所有者继续拥有资源、账户和安全
- 安全组 – VPC 共享参与者可以引用彼此的安全组 ID
- 效率 – 子网密度更高，有效使用 VPN 和 AWS Direct Connect
- 没有硬性限制 – 可以避免硬性限制 — 例如，通过简化的网络架构，每个 AWS Direct Connect 连接有 50 个虚拟接口
- 优化成本 – 可以通过重用 NAT 网关、VPC 接口终端节点和可用区内流量来优化成本

VPC 共享可让您解耦账户和网络。您可以拥有更少、更大、集中管理的 VPC。高度互连的应用程序会自动受益于这种方法。

![屏幕截图 2024-11-18 205020](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 205020.jpg)

**VPC peering connection**是两个 VPC 之间的网络连接，可让您私下路由它们之间的流量。任一 VPC 中的实例都可以相互通信，就像它们位于同一网络中一样。您可以在自己的 VPC 之间、与另一个 AWS 账户中的 VPC 或与不同 AWS 区域中的 VPC 之间创建 VPC 对等连接。

设置对等连接时，您可以在路由表中创建规则，以允许 VPC 通过对等资源相互通信。例如，假设您有两个 VPC。在 VPC A 的路由表中，您将目的地设置为 VPC B 的 IP 地址，将目标设置为对等资源 ID。在 VPC B 的路由表中，您将目的地设置为 VPC A 的 IP 地址，将目标设置为对等资源 ID。

VPC 对等连接有一些限制：

- IP 地址范围不能重叠。
- 不支持传递对等连接。例如，假设您有三个 VPC：A、B 和 C。VPC A 连接到 VPC B，VPC A 连接到 VPC C。但是，VPC B 未隐式连接到 VPC C。要将 VPC B 连接到 VPC C，您必须明确建立该连接。
- 在相同的两个 VPC 之间只能有一个对等连接资源。

![屏幕截图 2024-11-18 205252](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 205252.jpg)

默认情况下，您在 VPC 中启动的实例无法与远程网络通信。要将您的 VPC 连接到远程网络（即创建虚拟专用网络或 VPN 连接），您需要：

1.创建一个新的虚拟网关设备（称为虚拟专用网络 (VPN) 网关）并将其连接到您的 VPC。

2.定义 VPN 设备或客户网关的配置。客户网关不是设备，而是一种 AWS 资源，可向 AWS 提供有关您的 VPN 设备的信息。

3.创建自定义路由表以将企业数据中心绑定的流量指向 VPN 网关。您还必须更新安全组规则。（您将在下一节中了解安全组。）

4.建立 AWS 站点到站点 VPN（站点到站点 VPN）连接以将两个系统链接在一起。

5.配置路由以通过连接传递流量。

![屏幕截图 2024-11-18 205333](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 205333.jpg)

网络通信面临的挑战之一是网络性能。如果您的数据中心距离 AWS 区域较远，则性能可能会受到负面影响。对于这种情况，AWS 提供 AWS Direct Connect，简称 DX。AWS Direct Connect 使您能够在您的网络和其中一个 DX 位置之间建立专用的私有网络连接。此私有连接可以降低您的网络成本、增加带宽吞吐量并提供比基于互联网的连接更一致的网络体验。DX 使用开放标准 802.1q 虚拟局域网 (VLAN)。

![屏幕截图 2024-11-18 205426](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 205426.jpg)

VPC **endpoint**是一种虚拟设备，可让您私下将您的 VPC 连接到受支持的 AWS 服务和由 AWS PrivateLink 提供支持的 VPC 终端节点服务。连接到这些服务不需要互联网网关、NAT 设备、VPN 连接或 AWS Direct Connect 连接。您的 VPC 中的实例不需要公共 IP 地址即可与服务中的资源进行通信。您的 VPC 与其他服务之间的流量不会离开 Amazon 网络。

有两种类型的 VPC 终端节点：

- 接口 VPC 终端节点（接口终端节点）使您能够连接到由 AWS PrivateLink 支持的服务。这些服务包括一些 AWS 服务、由其他 AWS 客户和 AWS 合作伙伴网络 (APN) 合作伙伴在其自己的 VPC 中托管的服务（称为终端节点服务）以及受支持的 AWS Marketplace APN 合作伙伴服务。服务的所有者是服务提供商，而您（作为创建接口终端节点的委托人）是服务使用者。您需要为创建和使用服务的接口终端节点付费。适用小时使用费率和数据处理费率。请参阅 AWS 文档以获取受支持的接口终端节点列表以及有关此处显示的示例的更多信息，网址为 https://docs.aws.amazon.com/vpc/latest/privatelink/create-interface-endpoint.html。
- 网关终端节点：使用网关终端节点无需额外付费。适用数据传输和资源使用的标准费用。

![屏幕截图 2024-11-18 205614](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 205614.jpg)

您可以通过多种方式配置 VPC，并利用众多连接选项和网关。这些选项和网关包括 AWS Direct Connect（通过 DX 网关）、NAT 网关、互联网网关、VPC 对等连接等。AWS 客户拥有数百个 VPC，分布在 AWS 账户和区域中，为多个业务线、团队、项目等提供服务，这种情况并不罕见。当客户开始在其 VPC 之间建立连接时，事情会变得更加复杂。所有连接选项都是严格点对点的，因此 VPC 到 VPC 连接的数量可以快速增长。随着 AWS 上运行的工作负载数量的增长，您必须能够跨多个账户和 VPC 扩展网络以跟上增长的步伐。

虽然您可以使用 VPC 对等连接来连接多对 VPC，但如果无法集中管理连接策略，则管理多个 VPC 之间的点对点连接在运营上成本高昂且困难重重。对于本地连接，您必须将 VPN 连接到每个单独的 VPC。当 VPC 数量增加到数百个时，此解决方案的构建可能非常耗时且难以管理。

要解决此问题，您可以使用 AWS Transit Gateway 简化网络模型。使用 AWS Transit Gateway，您只需创建和管理从中央网关到网络中的每个 VPC、本地数据中心或远程办公室的单个连接。Transit Gateway 充当枢纽，控制流量在所有连接的网络（如辐条 spokes）之间的路由方式。这种枢纽辐射模型显著简化了管理并降低了运营成本，因为每个网络只需连接到 Transit Gateway，而不必连接到其他每个网络。任何新的 VPC 都连接到 Transit Gateway，然后自动可供连接到 Transit Gateway 的其他每个网络使用。这种轻松的连接性使您能够更轻松地随着业务的增长扩展网络。

![屏幕截图 2024-11-18 205814](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-18 205814.jpg)

通过标记此网络图，看看您是否可以识别出您学到的不同 VPC 网络组件。

![屏幕截图 2024-11-19 090341](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-19 090341.jpg)

**Section 3 key takeaways**

本模块此部分的一些关键要点包括：

- 有几种 VPC 网络选项，其中包括：
  - 互联网网关：将您的 VPC 连接到互联网
  - NAT 网关：使私有子网中的实例能够连接到互联网
  - VPC 终端节点：将您的 VPC 连接到受支持的 AWS 服务
  - VPC peering对等：将您的 VPC 连接到其他 VPC
  - VPC sharing共享：允许多个 AWS 账户将其应用程序资源创建到共享的、集中管理的 Amazon VPC 中
  - AWS Site to Site 站点到站点 VPN：将您的 VPC 连接到远程网络
  - AWS Direct Connect：使用专用网络连接将您的 VPC 连接到远程网络
  - AWS Transit Gateway：VPC 对等的星型连接替代方案



### Section 4: VPC security

您可以通过多种方式在 VPC 架构中构建安全性，以便完全控制传入和传出流量。在本节中，您将了解可用于保护 VPC 的两个 Amazon VPC 防火墙选项：security groups and network access control lists 安全组和网络访问控制列表（network 网络 ACL）。

![屏幕截图 2024-11-19 090659](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-19 090659.jpg)



安全组充当实例的虚拟防火墙，控制入站和出站流量。安全组在实例级别而不是子网级别起作用。因此，VPC 中子网中的每个实例都可以分配给一组不同的安全组。

从最基本的层面上讲，安全组是一种过滤实例流量的方式。

![屏幕截图 2024-11-19 090751](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-19 090751.jpg)

安全组具有控制入站和出站流量的规则。当您创建安全组时，它没有入站规则。因此，除非您向安全组添加入站规则，否则不允许来自其他主机到您的实例的入站流量。默认情况下，安全组包含允许所有出站流量的出站规则。您可以删除该规则并添加仅允许特定出站流量的出站规则。如果您的安全组没有出站规则，则不允许来自您的实例的出站流量。

安全组是有状态的，这意味着即使在处理请求后，状态信息也会保留。因此，如果您从实例发送请求，则无论入站安全组规则如何，该请求的响应流量都可以流入。无论出站规则如何，允许的入站流量的响应都可以流出。

![屏幕截图 2024-11-19 091047](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-19 091047.jpg)

创建自定义安全组时，您可以指定允许规则，但不能指定拒绝规则。在决定允许流量之前，会评估所有规则。

![屏幕截图 2024-11-19 091117](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-19 091117.jpg)

网络访问控制列表 (网络 ACL) 是 Amazon VPC 的可选安全层。它充当防火墙，用于控制进出一个或多个子网的流量。要为 VPC 添加另一层安全保护，您可以设置具有与安全组类似的规则的网络 ACL。

您的 VPC 中的每个子网都必须与网络 ACL 关联。如果您未明确将子网与网络 ACL 关联，则子网将自动与默认网络 ACL 关联。您可以将一个网络 ACL 与多个子网关联；但是，一个子网一次只能与一个网络 ACL 关联。当您将网络 ACL 与子网关联时，先前的关联将被删除。

![屏幕截图 2024-11-19 091215](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-19 091215.jpg)

网络 ACL 具有单独的入站和出站规则，每个规则都可以允许或拒绝流量。您的 VPC 自动附带可修改的默认网络 ACL。默认情况下，它允许所有入站和出站 IPv4 流量以及（如果适用）IPv6 流量。下表显示了默认网络 ACL。

网络 ACL 是无状态的，这意味着在处理请求后不会维护有关请求的任何信息。

![屏幕截图 2024-11-19 091249](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-19 091249.jpg)

您可以创建自定义网络 ACL 并将其与子网关联。默认情况下，每个自定义网络 ACL 都会拒绝所有入站和出站流量，直到您添加规则。

网络 ACL 包含按顺序评估的编号规则列表，从编号最低的规则开始。目的是确定是否允许流量进出与网络 ACL 关联的任何子网。规则可以使用的最大编号是 32,766。AWS 建议您以增量（例如，以 10 或 100 为增量）创建规则，以便您稍后可以在需要的地方插入新规则。

![屏幕截图 2024-11-19 091430](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-19 091430.jpg)

以下是安全组和网络 ACL 之间的差异总结：

- 安全组作用于实例级别，而网络 ACL 作用于子网级别。
- 安全组仅支持允许规则，而网络 ACL 同时支持允许和拒绝规则。
- 安全组是有状态的，而网络 ACL 是无状态的。
- 对于安全组，在决定允许流量之前会评估所有规则。对于网络 ACL，在决定允许流量之前会按数字顺序评估规则

![屏幕截图 2024-11-19 091519](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-19 091519.jpg)

现在轮到你了！在这种情况下，你是一家小企业主，你的网站托管在 AmazonElastic Compute Cloud (Amazon EC2) 实例上。你的客户数据存储在后端数据库中，你想将这些数据存储为私密数据。

看看您是否可以设计一个满足以下要求的 VPC：

- 您的 Web 服务器和数据库服务器必须位于不同的子网中。
- 您的网络的第一个地址必须是 10.0.0.0。每个子网必须有 256 个 IPv4 地址。
- 您的客户必须始终能够访问您的 Web 服务器。
- 您的数据库服务器必须能够访问互联网以进行补丁更新。
- 您的架构必须具有高可用性并使用至少一个自定义防火墙层。

**Section 4 key takeaways**

本模块此部分的重点是：

- 在您的 VPC 架构中构建安全性。
- 安全组和网络 ACL 是您可以用来保护您的 VPC 的防火墙选项。





### Section 5: Amazon Route 53

![屏幕截图 2024-11-19 091930](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-19 091930.jpg)

Amazon Route 53 是一种高度可用且可扩展的云域名系统 (DNS) Web 服务。它旨在为开发人员和企业提供一种可靠且经济高效的方式，将用户路由到互联网应用程序，方法是将名称（如 www.example.com）转换为计算机用于相互连接的数字 IP 地址（如 192.0.2.1）。此外，Amazon Route 53 完全符合 IPv6 标准。有关域名系统的更多信息，请访问 https://aws.amazon.com/route53/what-is-dns/。

Amazon Route 53 可有效地将用户请求连接到 AWS 中运行的基础设施（例如 Amazon EC2 实例、Elastic Load Balancing 负载均衡器或 Amazon S3 存储桶），也可用于将用户路由到 AWS 之外的基础设施。

您可以使用 Amazon Route 53 配置 DNS 运行状况检查，以便将流量路由到健康的终端节点或独立监控应用程序及其终端节点的运行状况。

Amazon Route 53 流量流可帮助您通过多种路由类型在全球范围内管理流量，这些路由类型可与 DNS 故障转移相结合，以实现各种低延迟、容错架构。您可以使用 Amazon Route 53 流量流的简单可视化编辑器来管理如何将用户路由到应用程序的终端节点 — 无论是在单个 AWS 区域还是分布在全球各地。

Amazon Route 53 还提供域名注册 - 您可以购买和管理域名（如 example.com），Amazon Route 53 将自动为您的域配置 DNS 设置。

![屏幕截图 2024-11-19 092128](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-19 092128.jpg)

192.0.2.0这是用户发起 DNS 请求时 Amazon Route 53 遵循的基本模式。DNS 解析器会在 Route 53 中检查您的域，获取 IP 地址并将其返回给用户。

![屏幕截图 2024-11-19 092201](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-19 092201.jpg)

Amazon Route 53 支持多种类型的路由策略，这些策略决定了 Amazon Route 53 如何响应查询：

- Simple routing 简单路由（round robin 循环）– 用于为您的域执行给定功能的单个资源（例如为 example.com 网站提供内容的 Web 服务器）。
- Weighted round  robin routing 加权循环路由 – 用于按您指定的比例将流量路由到多个资源。使您能够为资源记录集分配权重，以指定提供不同响应的频率。您可能希望使用此功能进行 A/B 测试，即将一小部分流量发送到您进行了软件更改的服务器。例如，假设您有两个与一个 DNS 名称关联的记录集：一个权重为 3，另一个权重为 1。在这种情况下，75% 的时间，Amazon Route 53 将返回权重为 3 的记录集，25% 的时间，Amazon Route 53 将返回权重为 1 的记录集。权重可以是 0 到 255 之间的任意数字。
- Latency routing 延迟路由 (LBR) – 当您在多个 AWS 区域中拥有资源并且想要将流量路由到提供最佳延迟的区域时使用。延迟路由的工作原理是根据运行应用程序的不同 AWS 区域的实际性能测量，将您的客户路由到提供最快体验的 AWS 终端节点（例如，Amazon EC2 实例、弹性 IP 地址或负载均衡器）。
- Geolocation routing 地理位置路由 – 当您想要根据用户的位置路由流量时使用。使用地理位置路由时，您可以本地化您的内容并以用户的语言呈现部分或全部网站。您还可以使用地理位置路由将内容分发限制在您拥有分发权的位置。另一个可能的用途是以可预测、易于管理的方式在端点之间平衡负载，以便每个用户位置都一致地路由到同一个端点。
- Geoproximity routing 地理邻近度路由 – 当您想要根据资源位置路由流量，并可选择将流量从一个位置的资源转移到另一个位置的资源时使用。
- Failover routing 故障转移路由（DNS  failover故障转移） – 当您想要配置主动-被动故障转移时使用。Amazon Route 53 可以帮助检测您网站的中断并将您的用户重定向到您的应用程序正常运行的其他位置。启用此功能后，Amazon Route 53 运行状况检查代理将监控您应用程序的每个位置或终端节点以确定其可用性。您可以利用此功能来提高面向客户的应用程序的可用性。
- Multivalue answer routing 多值答案路由 – 当您希望 Route53 使用随机选择的最多八个健康记录来响应 DNS 查询时使用。您可以将 Amazon Route53 配置为在响应 DNS 查询时返回多个值（例如 Web 服务器的 IP 地址）。您可以为几乎任何记录指定多个值，但多值答案路由还使您能够检查每个资源的运行状况，以便 Route53 仅返回健康资源的值。它不能替代负载均衡器，但返回多个可检查健康状态的 IP 地址的能力是使用 DNS 来提高可用性和负载平衡的一种方法。

![屏幕截图 2024-11-19 092517](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-19 092517.jpg)

多区域部署是 Amazon Route 53 的一个示例用例。使用 Amazon Route 53，用户会自动定向到距离用户最近的 Elastic Load Balancing 负载均衡器。

Route 53 多区域部署的优势包括：

- 基于延迟的区域路由
- 负载平衡路由到可用区





![屏幕截图 2024-11-19 092628](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-19 092628.jpg)

Amazon Route 53 可让您通过以下方式提高在 AWS 上运行的应用程序的可用性：

- 为您自己的应用程序配置备份和故障转移方案。
- 在 AWS 上启用高可用性多区域架构。
- 创建运行状况检查以监控 Web 应用程序、Web 服务器和其他资源的运行状况和性能。您创建的每个运行状况检查都可以监控以下任一内容：指定资源（例如 Web 服务器）的运行状况；其他运行状况检查的状态；以及 Amazon CloudWatch 警报的状态。

![屏幕截图 2024-11-19 092708](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-19 092708.jpg)

此图显示了 DNSfailover 在多层 Web 应用程序的典型架构中的工作方式。Route 53 将流量传递到负载均衡器，然后负载均衡器将流量分发到一组 EC2 实例。

您可以使用 Route 53 执行以下任务以确保高可用性：

1. 使用故障转移路由的路由策略为规范名称记录 (CNAME) www 创建两个 DNS 记录。第一个记录是主路由策略，它指向您的 Web 应用程序的负载均衡器。第二个记录是辅助路由策略，它指向您的静态 Amazon S3 网站。
2. 使用 Route 53 运行状况检查来确保主路由正在运行。如果是，则所有流量默认流向您的 Web 应用程序堆栈。如果 Web 服务器发生故障（或停止响应）或数据库实例发生故障，则会触发到静态备份站点的故障转移。



**Section 5 key takeaways**

本模块此部分的一些关键要点包括：

- Amazon Route 53 是一种高度可用且可扩展的云 DNS Web 服务，可将域名转换为数字 IP 地址。
- Amazon Route 53 支持多种类型的路由策略。
- 多区域部署可提高您的应用程序在全球范围内的性能。
- 您可以使用 Amazon Route 53 故障转移来提高应用程序的可用性。



### Section 6: Amazon CloudFront

联网的目的是在连接的资源之间共享信息。到目前为止，在本模块中，您了解了使用 Amazon VPC 的 VPC 联网。您了解了将您的 VPC 连接到互联网、远程网络、其他 VPC 和 AWS 服务的不同选项。

内容交付也通过网络进行 — 例如，当您从您最喜欢的流媒体服务流式传输电影时。在最后一节中，您将了解 Amazon CloudFront，它是一种 content delivery network 内容交付网络 (CDN) 服务。

![屏幕截图 2024-11-19 093109](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-19 093109.jpg)

正如本模块前面您学习 AWS Direct Connect 时所解释的那样，网络通信的挑战之一是网络性能。当您浏览网站或流式传输视频时，您的请求将通过许多不同的网络路由以到达源服务器。源服务器（或源）存储对象（网页、图像和媒体文件）的原始、最终版本。网络跳数和请求必须传输的距离会显著影响网站的性能和响应能力。此外，不同地理位置的网络延迟也不同。出于这些原因，内容分发网络可能是解决方案。

![屏幕截图 2024-11-19 093351](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-19 093351.jpg)

内容分发网络 (CDN) 是一个全球分布的缓存服务器系统。CDN 缓存托管在应用程序源服务器上的常见请求文件（静态内容，例如超文本标记语言或 HTML、层叠样式表或 CSS、JavaScript 和图像文件）的副本。CDN 从缓存边缘或接入点提供所请求内容的本地副本，从而以最快的速度向请求者提供内容

CDN 还交付请求者独有且不可缓存的动态内容。使用 CDN 交付动态内容可提高应用程序性能和扩展性。CDN 建立并维护更靠近请求者的安全连接。如果 CDN 与源站位于同一网络上，则路由回源站以检索动态内容的速度会加快。此外，表单数据、图像和文本等内容可以被提取并发送回源站，从而利用 PoP 的低延迟连接和代理行为。

![屏幕截图 2024-11-19 093433](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-19 093433.jpg)

Amazon CloudFront 是一种快速 CDN 服务，可以安全地向全球客户提供数据、视频、应用程序和应用程序编程接口 (API)，具有低延迟和高传输速度。它还提供了开发人员友好的环境。Amazon CloudFront 通过全球边缘站点网络和区域边缘缓存向用户提供文件。Amazon CloudFront 与传统的内容交付解决方案不同，因为它使您能够快速获得高性能内容交付的好处，而无需协商合同、高价格或最低费用。与其他 AWS 服务一样，Amazon CloudFront 是一种自助服务产品，采用按需付费定价。

![屏幕截图 2024-11-19 093501](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-19 093501.jpg)

AmazonCloudFront 通过全球数据中心网络（称为边缘站点）提供内容。当用户请求您使用 CloudFront 提供的内容时，用户将被路由到提供最低延迟（或时间延迟）的边缘站点，以便以最佳性能提供内容。CloudFront 边缘站点旨在快速向您的查看者提供热门内容。

随着对象变得不那么受欢迎，各个边缘站点可能会删除这些对象，为更受欢迎的内容腾出空间。对于不太受欢迎的内容，CloudFront 具有区域边缘缓存。区域边缘缓存是全球部署且靠近您的查看者的 CloudFront 站点。它们位于您的原始服务器和直接向查看者提供内容的全球边缘站点之间。区域边缘缓存的缓存比单个边缘站点更大，因此对象在区域边缘缓存中保留的时间更长。您的更多内容会更靠近您的查看者，从而减少 CloudFront 返回原始服务器的需要并提高查看者的整体性能。

Amazon CloudFront 具有以下优势：

- 快速且全球化 – Amazon CloudFront 具有大规模扩展和全球分布。为了以低延迟向最终用户提供内容，Amazon CloudFront 使用由边缘站点和区域缓存组成的全球网络。
- 边缘安全性 – Amazon CloudFront 提供网络级和应用程序级保护。您的流量和应用程序可通过各种内置保护（如 AWS Shield Standard）获益，无需支付额外费用。您还可以使用可配置功能（如 AWS 证书管理器 (ACM)）创建和管理自定义安全套接字层 (SSL) 证书，无需支付额外费用。
- 高度可编程 – Amazon CloudFront 功能可根据特定应用程序要求进行自定义。它与 Lambda@Edge 集成，因此您可以在全球 AWS 站点运行自定义代码，从而使您能够将复杂的应用程序逻辑移近用户以提高响应能力。CDN 还支持与其他工具和 DevOps 自动化接口集成。它提供持续集成和持续交付 (CI/CD) 环境。
- 与 AWS 深度集成 – Amazon CloudFront 与 AWS 集成，其物理位置直接连接到 AWS 全球基础设施和其他 AWS 服务。您可以使用 API 或 AWS 管理控制台以编程方式配置 CDN 中的所有功能。
- 经济高效 – Amazon CloudFront 之所以经济高效，是因为它没有最低承诺，只按实际使用量收费。与自托管相比，Amazon CloudFront 避免了在互联网上的多个站点运营缓存服务器网络的费用和复杂性。它消除了过度配置容量以应对潜在的流量高峰的需要。Amazon CloudFront 还使用了一些技术，例如将边缘位置对同一文件的同时查看请求合并为对原始服务器的单个请求。结果就是减少了原始服务器上的负载，减少了扩展原始基础设施的需求，从而进一步节省了成本。如果您使用 AWS 原始服务器（例如 Amazon Simple Storage Service (Amazon S3) 或 Elastic Load Balancing），则只需支付存储费用，而无需支付在这些服务和 CloudFront 之间传输的任何数据的费用。

![屏幕截图 2024-11-19 093648](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-19 093648.jpg)

Amazon CloudFront 费用基于四个方面的服务实际使用情况：

- 数据传出 – 您需要为从 Amazon CloudFront 边缘站点传出到互联网或您的源（AWS 源和其他源服务器）的数据量付费（以 GB 为单位）。数据传输使用量按特定地理区域单独计算，然后根据每个区域的定价套餐计算费用。如果您使用其他 AWS 服务作为文件的源，则您需要为使用这些服务单独付费，包括存储和计算小时数。
- HTTP(S) 请求 – 您需要为内容向 Amazon CloudFront 发出的 HTTP(S) 请求数量付费。
- 失效请求 – 您需要为失效请求中的每个路径付费。失效请求中列出的路径表示要从 CloudFront 缓存中失效的对象的 URL（如果路径包含通配符，则为多个 URL）。您每月可以从 Amazon CloudFront 请求最多 1,000 条路径，无需支付额外费用。超过前 1,000 条路径后，您需要按失效请求中列出的每条路径付费。
- 专用 IP 自定义安全套接字层 (SSL) – 您每月需要为与使用专用 IP 版本自定义 SSL 证书支持的一个或多个 CloudFront 分发相关联的每个自定义 SSL 证书支付 600 美元。此月费按小时按比例计算。例如，如果您的自定义 SSL 证书在 6 月份仅与至少一个 CloudFront 分发相关联 24 小时（即 1 天），则您在 6 月份使用自定义 SSL 证书功能的总费用为（1 天/30 天）* 600 美元 = 20 美元。

**Section 6 key takeaways**

本模块此部分的一些关键要点包括：

- CDN 是一个全球分布的缓存服务器系统，可以加速内容交付。
- Amazon CloudFront 是一种快速 CDN 服务，可以通过全球基础设施安全地交付数据、视频、应用程序和 API，具有低延迟和高传输速度。
- Amazon CloudFront 提供许多好处，包括：
  - 快速且全球化
  - 边缘安全
  - 高度可编程
  - 与 AWS 深度集成
  - 经济高效

**Module summary**  

总之，在本模块中，您学习了如何：

- 认识网络基础知识
-  使用 Amazon VPC 描述云中的虚拟网络
-  标记网络图• 设计基本 VPC 架构
-  指示构建 VPC 的步骤
-  识别安全组
-  创建自己的 VPC 并向其中添加其他组件以生成自定义网络
-  识别 Amazon Route 53 的基础知识
-  认识 Amazon CloudFront 的优势



## Module 6: Compute

本模块将讨论以下主题：

- 计算服务概述
- Amazon EC2
- Amazon EC2 成本优化
- 容器服务
- AWS Lambda 简介
- AWS Elastic Beanstalk 简介

完成本模块后，您应该能够：

- 概述云中不同的 AWS 计算服务
- 演示为什么要使用 Amazon Elastic Compute Cloud (Amazon EC2)
- 识别 EC2 控制台中的功能
- 执行 EC2 中的基本功能以构建虚拟计算环
- 识别 EC2 成本优化元素
- 演示何时使用 AWS Elastic Beanstalk
- 演示何时使用 AWS Lambda
- 识别如何在托管服务器集群中运行容器化应用程序



### Section 1: Compute services overview

![屏幕截图 2024-11-19 095322](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-19 095322.jpg)

Amazon Web Services (AWS) 提供多种计算服务。以下是每种计算服务提供的服务的简要概述：

- Amazon Elastic Compute Cloud (Amazon EC2) 提供可调整大小的虚拟机。
- Amazon EC2 Auto Scaling 通过允许您定义自动启动或终止 EC2 实例的条件来支持应用程序可用性。
- Amazon Elastic Container Registry (Amazon ECR) 用于存储和检索 Docker 映像。
- Amazon Elastic Container Service (Amazon ECS) 是一种支持 Docker 的容器编排服务。
- VMware Cloud on AWS 使您能够配置混合云而无需自定义硬件。
- AWS Elastic Beanstalk 提供了一种运行和管理 Web 应用程序的简单方法。
- AWS Lambda 是一种无服务器计算解决方案。您只需为使用的计算时间付费。
- Amazon Elastic Kubernetes Service (Amazon EKS) 使您能够在 AWS 上运行托管的 Kubernetes。
- Amazon Lightsail 提供一种易于使用的服务，用于构建应用程序或网站。
- AWS Batch 提供一种工具，用于运行任何规模的批处理作业。
- AWS Fargate 提供一种运行容器的方法，从而减少了您管理服务器或集群的需要。
- AWS Outposts 提供一种在本地数据中心运行选定 AWS 服务的方法。
- AWS Serverless Application Repository 提供一种发现、部署和发布无服务器应用程序的方法。

![屏幕截图 2024-11-19 095529](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-19 095529.jpg)

您可以将每个 AWS 计算服务视为属于四大类别之一：提供基础设施即服务 (IaaS) 的虚拟机 (VM)、无服务器、基于容器的和平台即服务 (PaaS)。

**Amazon EC2** 提供虚拟机，您可以将其视为基础设施即服务 (IaaS)。IaaS 服务提供灵活性，并将许多服务器管理责任留给您。您可以选择操作系统，还可以选择要启动的服务器的大小和资源功能。对于有使用本地计算经验的 IT 专业人员来说，虚拟机是一个熟悉的概念。Amazon EC2 是首批 AWS 服务之一，它仍然是最受欢迎的服务之一。

**AWS Lambda** 是一个零管理计算平台。AWS Lambda 使您无需配置或管理服务器即可运行代码。您只需为使用的计算时间付费。这种无服务器技术概念对于许多 IT 专业人士来说相对较新。然而，它正变得越来越流行，因为它支持云原生架构，与全天候运行服务器以支持相同工作负载相比，它能够以更低的成本实现大规模可扩展性。

基于容器的服务（包括 **Amazon Elastic Container Service**、**Amazon Elastic Kubernetes Service**、**AWS Fargate** 和 **Amazon Elastic Container Registry**）可让您在单个操作系统 (OS) 上运行多个工作负载。容器比虚拟机启动速度更快，因此响应速度更快。基于容器的解决方案越来越受欢迎。

最后，**AWS Elastic Beanstalk** 提供平台即服务 (PaaS)。它通过提供您需要的所有应用程序服务，帮助您快速部署创建的应用程序。AWS 管理操作系统、应用程序服务器和其他基础设施组件，以便您可以专注于开发应用程序代码。

AWS 提供多种计算服务，因为不同的用例受益于不同的计算环境。您使用的最佳计算服务将取决于您的用例。

通常，您使用的计算架构由遗留代码决定。但是，这并不意味着您无法改进架构以利用经过验证的云原生设计。

最佳实践包括：

- 评估可用的计算选项
- 了解可用的计算配置选项
- 收集与计算机相关的指标
- 利用资源的可用弹性
- 根据指标重新评估计算需求





### Section 2: Amazon EC2

![屏幕截图 2024-11-19 100058](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-19 100058.jpg)

**Running servers on premises**是一项昂贵的任务。必须采购硬件，并且采购可能基于项目计划，而不是服务器的实际使用情况。数据中心的建设、人员配备和维护成本高昂。组织还需要永久配置足够的硬件来处理流量高峰和峰值工作负载。在构建传统的本地部署后，服务器容量可能会在服务器运行的大部分时间内处于闲置状态，这是一种浪费。

Amazon Elastic Compute Cloud (Amazon EC2) 提供虚拟机，您可以在其中托管在传统本地服务器上运行的相同类型的应用程序。它在云中提供安全、可调整大小的计算容量。EC2 实例可以支持各种工作负载。EC2 实例的常见用途包括但不限于：

- 应用程序服务器

- Web 服务器
- 数据库服务器
- 游戏服务器
- 邮件服务器
- 媒体服务器
- 目录服务器
- 文件服务器
- 计算服务器
- 代理服务器

![屏幕截图 2024-11-19 100220](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-19 100220.jpg)

Amazon EC2 中的 EC2 代表弹性计算云：

- 弹性是指您可以轻松增加或减少运行的服务器数量以自动支持应用程序，还可以增加或减少现有服务器的大小。
- 计算是指大多数用户首先运行服务器的原因，即托管正在运行的应用程序或处理数据 - 这些操作需要计算资源，包括处理能力 (CPU) 和内存 (RAM)。
- 云是指您运行的 EC2 实例托管在云中。

Amazon EC2 在云中提供虚拟机，并让您完全管理实例上运行的 Windows 或 Linux 操作系统。支持大多数服务器操作系统，包括：Windows 2008、2012、2016 和 2019、Red Hat、SuSE、Ubuntu 和 Amazon Linux。

在虚拟机上运行的操作系统通常称为客户操作系统，以区别于主机操作系统。主机操作系统直接安装在托管一台或多台虚拟机的任何服务器硬件上。

使用 Amazon EC2，您可以在几分钟内将任意数量、任意大小的实例启动到全球任何可用区。实例从 Amazon 系统映像 (AMI) 启动，这些映像实际上是虚拟机模板。本模块后面将更详细地讨论 AMI。

您可以使用安全组控制往返实例的流量。此外，由于服务器在 AWS 云中运行，您可以构建使用多种 AWS 服务的解决方案。

![屏幕截图 2024-11-19 100345](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-19 100345.jpg)

首次启动 Amazon EC2 实例时，您可能会使用 AWS 管理控制台启动实例向导。您将有机会在本模块的实验中体验使用启动向导。

启动实例向导可让您轻松启动实例。例如，如果您选择接受所有默认设置，则可以跳过向导提供的大部分步骤，只需单击六次即可启动 EC2 实例。本节末尾的演示中显示了此过程的一个示例。

但是，对于大多数部署，您将需要修改默认设置，以便以符合您特定需求的方式部署启动的服务器。

下一组幻灯片将向您介绍启动实例时必须做出的基本选择。幻灯片涵盖了做出这些选择时需要了解的基本概念。这些概念的描述旨在帮助您了解可用的选项以及您将做出的决定的影响。

![屏幕截图 2024-11-19 100458](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-19 100458.jpg)

**Amazon Machine Image (AMI)** 提供启动 EC2 实例所需的信息。启动实例时必须指定源 AMI。您可以使用不同的 AMI 来启动不同类型的实例。例如，您可以选择一个 AMI 来启动将成为 Web 服务器的实例，并选择另一个 AMI 来部署将托管应用程序服务器的实例。您还可以从单个 AMI 启动多个实例。

AMI 包括以下组件：

- 实例根卷的模板。根卷通常包含操作系统 (OS) 以及安装在该操作系统中的所有内容（应用程序、库等）。Amazon EC2 将模板复制到新 EC2 实例的根卷，然后启动该实例。
- **Launch permissions 启动权限**，控制哪些 AWS 账户可以使用 AMI。
- **block device mapping 块设备映射**，指定启动实例时要附加到实例的卷（如果有）。

您可以选择多种 AMI：

- **Quick Start 快速入门** – AWS 提供许多预构建的 AMI 来启动您的实例。这些 AMI 包括许多 Linux 和 Windows 选项。
- **My AMIs 我的 AMI** – 这些 AMI 是您创建的 AMI。
- **AWS Marketplace** – AWS Marketplace 提供列出数千种软件解决方案的数字目录。这些 AMI 可以提供特定的使用案例来帮助您快速入门。
- **Community AMI社区 AMI** – 这些 AMI 由世界各地的人们创建。这些 AMI 未经 AWS 检查，因此使用它们需要您自担风险。社区 AMI 可以为各种问题提供许多不同的解决方案，但请谨慎使用。避免在任何生产或企业环境中使用它们。

![屏幕截图 2024-11-19 100720](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-19 100720.jpg)

AMI 是从 EC2 实例创建的。您可以导入虚拟机，使其成为 EC2 实例，然后将 EC2 实例另存为 AMI。然后，您可以从该 AMI 启动 EC2 实例。或者，您可以从现有 AMI（例如 AWS 提供的快速入门 AMI）开始，并从中创建 EC2 实例。

无论您选择哪个选项（步骤 1），您都将获得图中所示的未修改实例。然后，您可以从该实例创建一个黄金实例（即，使用所需的特定操作系统和应用程序设置配置的虚拟机）（步骤 2），然后将其捕获为新的 AMI（步骤 3）。当您创建 AMI 时，Amazon EC2 会停止该实例，创建其根卷的快照，最后将该快照注册为 AMI。

注册 AMI 后，可以使用该 AMI 在同一 AWS 区域中启动新实例。现在可以将新 AMI 视为新的启动 AMI。您可能还想将 AMI 复制到其他区域（步骤 4），以便也可以在这些位置启动 EC2 实例。

![屏幕截图 2024-11-19 101318](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-19 101318.jpg)

Amazon EC2 提供多种实例类型，这些实例类型经过优化，可满足不同使用案例的需求。实例类型包括各种 CPU、内存、存储和网络容量组合。不同的实例类型让您可以灵活地为应用程序选择合适的资源组合。每种实例类型都包含一种或多种实例大小，让您能够根据目标工作负载的要求扩展资源。

实例类型类别包括通用型、计算优化型、内存优化型、存储优化型和加速计算型实例。每个实例类型类别都提供多种实例类型可供选择。

![屏幕截图 2024-11-19 101353](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-19 101353.jpg)

当您查看 EC2 实例类型时，您会看到其名称由几个部分组成。例如，考虑 T 类型。

T 是姓氏，后面跟着一个数字。这里，这个数字是 3。

该数字是该类型的代数。因此，t3 实例是 T 系列的第三代。一般而言，更高代数的实例类型功能更强大，性价比更高。

名称的下一部分是实例的大小部分。比较大小时，查看大小类别的系数部分很重要。

例如，t3.2xlarge 的 vCPU 和内存是 t3.xlarge 的两倍。反过来，t3.xlarge 的 vCPU 和内存也是 t3.large 的两倍。

还要注意的是，网络带宽也与 Amazon EC2 实例的大小有关。如果您要运行对网络要求很高的作业，则可能需要增加实例规格以满足您的需求。

![屏幕截图 2024-11-19 101801](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-19 101801.jpg)

实例类型有多种变化，包括：CPU 类型、CPU 或核心数、存储类型、存储量、内存量和网络性能。该图表提供了不同实例类别的概览，以及哪些实例类型系列和代数适合每种类别类型。更详细地考虑一些实例类型：

- **T3** 实例提供可突发性能的通用实例，可提供基准级别的 CPU 性能，并能够超出基准水平。此类实例的使用案例包括网站和 Web 应用程序、开发环境、构建服务器、代码存储库、微服务、测试和暂存环境以及业务线应用程序。
- **C5** 实例针对计算密集型工作负载进行了优化，以低廉的单位计算成本提供经济高效的高性能。用例包括科学建模、批处理、广告投放、高度可扩展的多人游戏和视频编码。
- **R5**实例针对内存密集型应用程序进行了优化。用例包括高性能数据库、数据挖掘和分析、内存数据库、分布式Web级内存缓存、实时处理非结构化大数据的应用程序、Apache Hadoop或Apache Spark集群以及其他企业应用程序。

![屏幕截图 2024-11-19 101915](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-19 101915.jpg)

除了考虑工作负载的 CPU、RAM 和存储需求之外，考虑网络带宽要求也很重要。

每种实例类型都提供记录在案的网络性能级别。例如，a1.medium 实例将提供高达 10 Gbps 的速度，而 p3dn.24xlarge 实例则提供高达 100 Gbps 的速度。选择符合您要求的实例类型。

当您启动多个新的 EC2 实例时，Amazon EC2 会尝试放置这些实例，以便默认情况下它们分散在底层硬件上。这样做是为了最大限度地减少相关故障。但是，如果您想指定特定的放置标准，则可以使用放置组来影响一组相互依赖的实例的放置，以满足您的工作负载需求。例如，您可以指定三个实例都应部署在同一个可用区中，以确保实例之间的网络延迟更低、网络吞吐量更高。有关详细信息，请参阅 https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/placement-groups.html 上的放置组文档。

![屏幕截图 2024-11-19 102030](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-19 102030.jpg)

选择 AMI 和实例类型后，您必须指定将部署 EC2 实例的网络位置。在启动启动实例向导之前，必须选择**Region 区域**。在选择**Launch Instance 启动实例**之前，请验证您是否位于 Amazon EC2 控制台的正确区域页面中。

当您在**默认 VPC** 中启动实例时，AWS 会默认为其分配一个**公有 IP 地址**。当您在**nondefault VPC** 中启动实例时，子网有一个属性，该属性决定在该子网中启动的实例是否从公有 IPv4 地址池中接收公有 IP 地址。默认情况下，AWS 不会为在非默认子网中启动的实例分配公有 IP 地址。您可以通过修改子网的公有 IP 寻址属性，或在启动期间启用或禁用公有 IP 寻址功能（这将覆盖子网的公有 IP 寻址属性）来控制实例是否接收公有 IP 地址。

![屏幕截图 2024-11-19 102228](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-19 102228.jpg)

通常使用 EC2 实例来运行必须对其他 AWS 服务进行安全 API 调用的应用程序。为了支持这些用例，AWS 允许您将 AWS 身份和访问管理 (IAM) 角色附加到 EC2 实例。如果没有此功能，您可能会倾向于将 AWS 凭证放在 EC2 实例上，以便在该实例上运行的应用程序使用。但是，您永远不应将 AWS 凭证存储在 EC2 实例上。这非常不安全。相反，将 IAM 角色附加到 EC2 实例。然后，IAM 角色授予在 EC2 实例上运行的应用程序发出应用程序编程接口 (API) 请求的权限。

**Instance profile 实例配置文件**是 IAM 角色的容器。如果您使用 AWS 管理控制台为 Amazon EC2 创建角色，控制台会自动创建实例配置文件并赋予其与角色相同的名称。当您随后使用 Amazon EC2 控制台启动具有 IAM 角色的实例时，您可以选择与该实例关联的角色。在控制台中，显示的列表实际上是实例配置文件名称的列表。

**在示例中 In the example**，您会看到 IAM 角色用于向在 EC2 实例上运行的应用程序授予权限。该应用程序必须访问 Amazon S3 中的存储桶。

您可以在启动实例时附加 IAM 角色，但也可以向已运行的 EC2 实例附加角色。定义可由 EC2 实例使用的角色时，可以定义哪些账户或 AWS 服务可以担任该角色。还可以定义应用程序在担任该角色后可以使用哪些 API 操作和资源。如果您更改角色，则更改将传播到附加了该角色的所有实例。

![屏幕截图 2024-11-19 102457](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-19 102457.jpg)

创建 EC2 实例时，您可以选择将用户数据传递给实例。用户数据可以在实例启动时自动完成安装和配置。例如，用户数据脚本可能会修补和更新实例的操作系统、获取和安装软件许可证密钥或安装其他软件。

在示例用户数据脚本中，您会看到一个简单的三行 LinuxBash shell 脚本。第一行表示该脚本应由 Bash shell 运行。第二行调用 Yellowdog Updater, Modified (YUM) 实用程序，该实用程序通常用于许多 Linux 发行版（例如 Amazon Linux、CentOS 和 Red Hat Linux）以从在线存储库检索软件并进行安装。在示例的第二行中，该命令告诉 YUM 将所有已安装的软件包更新为其配置为访问的软件存储库已知的最新版本。脚本的第三行表示应安装 Wget 实用程序。Wget 是一种用于从 Web 下载文件的常用实用程序。

对于 Windows 实例，用户数据脚本应采用与命令提示符窗口（批处理命令）或 Windows PowerShell 兼容的格式编写。有关详细信息，请参阅 https://docs.aws.amazon.com/AWSEC2/latest/WindowsGuide/ec2-windows-user-data.html 上的 Windows 用户数据脚本文档。

创建 EC2 实例后，用户数据脚本将在启动过程的最后阶段以 root 权限运行。在 Linux 实例上，它由 cloud-initservice 运行。在 Windows 实例上，它由 EC2Configor EC2Launchutility 运行。默认情况下，用户数据仅在实例首次启动时运行。但是，如果您希望用户数据脚本在每次启动实例时运行，则可以创建多用途 Internet 邮件扩展 (MIME) 多部分文件用户数据脚本（此过程并不常见）。更多信息请参阅 https://aws.amazon.com/premiumsupport/knowledge-center/execute-user-data-ec2/

![屏幕截图 2024-11-19 102550](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-19 102550.jpg)

启动 EC2 实例时，您可以配置存储选项。例如，您可以配置安装客户操作系统的根卷的大小。您还可以在启动实例时附加其他存储卷。某些 AMI 还配置为默认启动多个存储卷，以提供与根卷分开的存储。

对于实例将拥有的每个卷，您可以指定磁盘的大小、卷类型以及实例终止时是否保留存储。您还可以指定是否应使用加密。

![屏幕截图 2024-11-19 102622](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-19 102622.jpg)

**Amazon Elastic Block Store (Amazon EBS)** 是一种易于使用、高性能的持久块存储服务，旨在与 Amazon EC2 配合使用，用于处理吞吐量和事务密集型工作负载。使用 Amazon EBS，您可以从四种不同的卷类型中进行选择，以平衡最佳价格和性能。您可以更改卷类型或增加卷大小，而不会中断关键应用程序，因此您可以在需要时获得经济高效的存储。

**Amazon EC2 Instance Storage** 为您的实例提供短暂或临时的块级存储。此存储位于物理连接到主机的磁盘上。当您必须临时存储频繁更改的信息（例如缓冲区、缓存、临时数据和其他临时内容）时，实例存储非常有用。您还可以将实例存储用于在一组实例（例如负载平衡的 Web 服务器池）中复制的数据。如果实例因用户错误或故障而停止，则实例存储上的数据将被删除。

**Amazon Elastic File System (Amazon EFS)** 提供简单、可扩展、完全托管的弹性网络文件系统 (NFS) 文件系统，可与 AWS 云服务和本地资源配合使用。它旨在按需扩展到 PB 级，而不会中断应用程序。它会随着您添加和删除文件而自动增大和缩小，从而减少了配置和管理容量以适应增长的需要。

**Amazon Simple Storage Service (Amazon S3)** 是一种对象存储服务，可提供可扩展性、数据可用性、安全性和性能。您可以存储和保护任意数量的数据，以满足各种使用案例的需求，例如网站、移动应用程序、备份和还原、存档、企业应用程序、物联网 (IoT) 设备和大数据分析。

![屏幕截图 2024-11-19 102752](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-19 102752.jpg)

在这里，您可以看到两个如何为 EC2 实例配置存储选项的示例。

实例 1 示例显示，根卷（包含操作系统和其他数据）存储在 Amazon EBS 上。此实例还具有两个附加卷。一个卷是 500 GB 的 Amazon EBS 存储卷，另一个卷是实例存储卷。如果停止此实例然后重新启动，则操作系统将继续存在，并且存储在 20 GB 的 Amazon EBS 卷或 500 GB 的 Amazon EBS 卷上的任何数据都将保持不变。但是，存储在临时卷 1 上的任何数据都将永久丢失。实例存储非常适合临时存储频繁更改的信息，例如缓冲区、缓存、临时数据和其他临时内容。

实例 2 示例显示根卷位于实例存储（临时卷 2）上。具有实例存储根卷的实例无法通过 Amazon EC2 API 调用停止。它只能被终止。但是，它可以从实例的操作系统内部停止（例如，通过发出关闭命令） - 或者它可以因操作系统或磁盘故障而停止 - 这会导致实例终止。如果实例被终止，存储在临时卷 2 上的所有数据都将丢失，包括操作系统。您将无法再次启动实例。因此，不要依赖实例存储来存储有价值的长期数据。相反，使用更持久的数据存储，例如 Amazon EBS、Amazon EFS 或 Amazon S3。

如果实例重新启动（有意或无意），实例存储根卷上的数据将会保留下来。

![屏幕截图 2024-11-19 102842](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-19 102842.jpg)



标签是您分配给 AWS 资源的标签。每个标签由一个键和一个可选值组成，两者都是您定义的。标签使您能够以不同的方式对 AWS 资源（例如 EC2 实例）进行分类。例如，您可以按用途、所有者或环境标记实例。

标记是将元数据附加到 EC2 实例的方法。

标签键和标签值区分大小写。例如，EC2 实例常用的标签是名为 Name 的标签键和描述实例的标签值，例如 My Web Server。默认情况下，Name 标签显示在 Amazon EC2 控制台实例页面中。但是，如果您创建名为 name（n 小写）的键，它将不会出现在实例列表的 Name 列中（尽管它仍会显示在 Tags 选项卡中的实例详细信息面板中）。

制定标记策略是一种最佳实践。使用一组一致的标签键可以让您更轻松地管理资源。您还可以根据添加的标签搜索和筛选资源。有关更多信息，请参阅 https://d1.awsstatic.com/whitepapers/aws-tagging-best-practices.pdf。

![屏幕截图 2024-11-19 102929](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-19 102929.jpg)

**security group 安全组**充当虚拟防火墙，控制一个或多个实例的网络流量。启动实例时，您可以指定一个或多个安全组；否则，将使用默认安全组。

您可以向每个安全组添加**rules 规则**。规则允许流量进入或来自其关联实例。您可以随时修改安全组的规则，新规则将自动应用于与该安全组关联的所有实例。当 AWS 决定是否允许流量到达实例时，将评估与该实例关联的所有安全组的所有规则。在虚拟私有云 (VPC) 中启动实例时，您必须创建新的安全组或使用该 VPC 中已存在的安全组。启动实例后，您可以更改其安全组。

**define a rule 定义规则时**，您可以指定允许的网络通信源（入站规则）或目标（出站规则）。源可以是 IP 地址、IP 地址范围、另一个安全组、网关 VPC 终端节点或任何位置（这意味着将允许所有源）。默认情况下，安全组包含允许所有出站流量的出站规则。您可以删除规则并添加仅允许特定出站流量的出站规则。如果您的安全组没有出站规则，则不允许来自您的实例的任何出站流量。

在**示例规则中**，如果请求的来源是 My IP，则规则允许通过传输控制协议 (TCP) 端口 22 进行安全 Shell (SSH) 流量。My IP IP 地址是通过确定您定义规则时当前连接到 AWS 云的 IP 地址来计算的。

**Network access control lists 网络访问控制列表（网络 ACL）**也可以用作防火墙来保护 VPC 中的子网。

**For accessibility 对于可访问性**：EC2 控制台屏幕的屏幕截图，您可以在其中定义安全组规则。它显示了类型为 SSH、协议为 TCP、端口范围为 22、来源为 My IP 的规则，以及显示示例 My IP 地址的 CIDR 块。可访问性描述结束。

![屏幕截图 2024-11-19 103138](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-19 103138.jpg)

在您指定启动 EC2 实例所需的所有配置，并自定义任何可选的 EC2 启动向导配置设置后，系统会向您显示“检查实例启动”窗口。如果您随后选择“启动”，系统会显示一个对话框，要求您选择现有密钥对、在没有密钥对的情况下继续操作或创建新密钥对，然后您才能选择“启动实例”并创建 EC2 实例。

Amazon EC2 使用公钥加密技术来加密和解密登录信息。该技术使用公钥来加密一段数据，然后接收者使用私钥来解密数据。公钥和私钥称为密钥对。公钥加密技术使您可以使用私钥而不是密码来安全地访问您的实例。

启动实例时，您需要指定密钥对。您可以指定现有密钥对，也可以指定启动时创建的新密钥对。如果您创建了新密钥对，请下载并保存在安全位置。这是您保存私钥文件的唯一机会。

要连接到 Windows 实例，请使用私钥获取管理员密码，然后使用远程桌面协议 (RDP) 登录到 EC2 实例的 Windows 桌面。要从 Windows 计算机建立到 Amazon EC2 实例的 SSH 连接，您可以使用 PuTTY 等工具，该工具需要相同的私钥。

使用 Linux 实例时，在启动时，公钥内容将放置在实例上。在 within~/.ssh/authorized_keys 中创建一个条目。要登录到您的 Linux 实例（例如，通过使用 SSH），您必须在建立连接时提供私钥。

![屏幕截图 2024-11-19 103242](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-19 103242.jpg)



选择**Launch Instances**并选择**View Instances**后，您将看到一个与示例类似的屏幕。

您在启动期间指定的许多设置在**Description**描述面板中可见。

有关可用实例的信息包括 IP 地址和 DNS 地址信息、实例类型、分配给该实例的唯一实例 ID、用于启动实例的 AMI 的 AMI ID、VPC ID、子网 ID 等。

其中许多详细信息都提供了超链接，您可以选择这些超链接来了解有关您启动的 EC2 实例相关的资源的更多信息。

![屏幕截图 2024-11-19 103508](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-19 103508.jpg)

您还可以使用 AWS 命令行界面 (AWS CLI) 或某个 AWS 软件开发工具包 (SDK) 以编程方式启动 EC2 实例。

在示例 AWS CLI 命令中，您会看到一个命令，它指定启动实例所需的最少信息。该命令包含以下信息：•aws – 指定调用 aws 命令行实用程序。

- ec2 – 指定调用 ec2 服务命令。
- run-instances – 是正在调用的子命令。





该命令的其余部分指定了几个参数，包括：

- image-id – 此参数后面跟着 AMI ID。所有 AMI 都有唯一的 AMI ID。
- count – 您可以指定多个。
- Instance-type – 您可以指定实例类型以创建（例如）c3.large 实例
- key-name – 在示例中，假设 MyKeyPair 已经存在。
- security-groups - 在此示例中，假设 MySecurityGroup 已经存在。
- region -AMI 存在于 AWS 区域中，因此您必须指定 AWS CLI 将在其中找到 AMI 并启动 EC2 实例的区域。



如果满足以下条件，则命令应该能够成功创建 EC2 实例：

- 命令格式正确
- 命令所需的资源已经存在
- 您拥有足够的权限来运行该命令
- 您的 AWS 账户拥有足够的容量如果命令成功执行，API 会使用实例 ID 和其他相关数据来响应命令，以供您的应用程序在后续 API 请求中使用。



![屏幕截图 2024-11-19 104114](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-19 104114.jpg)

在这里，您可以看到实例的生命周期。箭头表示您可以采取的操作，方框表示实例在该操作之后将进入的状态。实例可以处于以下状态之一：

待处理 – 首次从 AMI 启动实例或启动已停止的实例时，实例启动并部署到主机后将进入待处理状态。启动时指定的实例类型决定了实例的主机硬件。

- **Pending** 待处理– 首次从 AMI 启动实例或启动已停止的实例时，实例在启动并部署到主机后进入待处理状态。启动时指定的实例类型决定了实例的主机硬件。
- **Running** 正在运行 – 实例完全启动并准备就绪后，将退出待处理状态并进入运行状态。您可以通过 Internet 连接到正在运行的实例。
- **Rebooting** 正在重启 –AWS 建议您使用 Amazon EC2 控制台、AWS CLI 或 AWS SDKs 重启实例，而不是从客户操作系统 (OS) 中调用重启。重启的实例将保留在同一物理主机上，维护相同的公共 DNS 名称和公共 IP 地址，并且如果它具有实例存储卷，它将保留这些卷上的数据。
- **Shutting down** 正在关闭 – 此状态是运行和终止之间的中间状态。
- **Terminated** 已终止 – 终止的实例在虚拟机被删除之前仍会在 Amazon EC2 控制台中可见一段时间。但是，您无法连接或恢复已终止的实例。 
- **Stopping** 正在停止 – 可以停止由 Amazon EBS 支持的实例。它们在达到完全停止状态之前会进入停止状态。
- **Stopped** 已停止 – 已停止的实例不会产生与正在运行的实例相同的成本。启动已停止的实例会将其重新置于待处理状态，从而将实例移动到新的主机。

![屏幕截图 2024-11-19 104437](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-19 104437.jpg)

公有 IP 地址是可从 Internet 访问的 IPv4 地址。每个接收公有 IP 地址的实例也会被赋予一个外部 DNS 主机名。例如，如果分配给实例的公有 IP 地址是 203.0.113.25，则外部 DNS 主机名可能是 ec2-203-0-113-25.compute-1.amazonaws.com。

如果您指定应将公有 IP 地址分配给您的实例，则该地址将从 AWS 公有 IPv4 地址池中分配。公有 IP 地址与您的 AWS 账户无关。当公有 IP 地址与您的实例解除关联时，它将被释放回公有 IPv4 地址池，并且您将无法指定是否要重复使用它。当实例停止或终止时，AWS 会释放您的实例的公有 IP 地址。当您停止的实例重新启动时，它将收到一个新的公有 IP 地址。

如果您需要持久的公共 IP 地址，则可能需要将弹性 IP 地址与实例关联。要关联弹性 IP 地址，您必须先在实例所在的区域中分配新的弹性 IP 地址。分配弹性 IP 地址后，您可以将弹性 IP 地址与 EC2 实例关联。

默认情况下，每个区域的所有 AWS 账户都限制为五 (5) 个弹性 IP 地址，因为公共 (IPv4) 互联网地址是一种稀缺的公共资源。不过，这是一个软限制，您可以请求增加限制（可能会获得批准）。

![屏幕截图 2024-11-19 104748](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-19 104748.jpg)

实例元数据是有关您的实例的数据。您可以在连接到实例时查看它。要在浏览器中访问它，请转到以下 URL：http://169.254.169.254/latest/meta-data/。也可以通过编程方式读取数据，例如从具有 cURL 实用程序的终端窗口读取。在终端窗口中，运行 curl http://169.254.169.254/latest/meta-data/ 以检索它。IP 地址 169.254.169.254 是链接本地地址，并且仅在实例中有效。

 实例元数据提供了有关正在运行的实例的大部分信息，这些信息与您在 AWS 管理控制台中找到的信息相同。例如，您可以发现公有 IP 地址、私有 IP 地址、公有主机名、实例 ID、安全组、区域、可用区等。

实例启动时指定的任何用户数据也可以通过以下 URL 访问：http://169.254.169.254/latest/user-data。

EC2 实例元数据可用于配置或管理正在运行的实例。例如，您可以编写一个配置脚本来访问元数据信息并使用它来配置应用程序或操作系统设置。

![屏幕截图 2024-11-19 104834](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-19 104834.jpg)

您可以使用 Amazon CloudWatch 监控您的实例，它可以收集来自 Amazon EC2 的原始数据并将其处理为可读的近乎实时的指标。这些统计数据会记录 15 个月，因此您可以访问历史信息并更好地了解您的 Web 应用程序或服务的运行情况

默认情况下，Amazon EC2 提供基本监控，即以 5 分钟为周期向 CloudWatch 发送指标数据。要以 1 分钟为周期将实例的指标数据发送到 CloudWatch，您可以启用实例的详细监控。有关更多信息，请参阅 https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-cloudwatch-new.html 上的“为您的实例启用或禁用详细监控”。

Amazon EC2 控制台根据来自 Amazon CloudWatch 的原始数据显示一系列图表。根据您的需要，您可能更愿意从 Amazon CloudWatch 获取实例数据，而不是通过控制台中的图表。默认情况下，Amazon CloudWatch 不提供 EC2 实例的 RAM 指标，但如果您希望 CloudWatch 收集该数据，您可以配置该选项。



**Section 2 key takeaways**

本模块此部分的一些关键要点包括：

- Amazon EC2 使您能够在云中运行 Windows 和 Linux 虚拟机。
- 您从 AMI 模板将 EC2 实例启动到您账户中的 VPC 中。
- 您可以从许多实例类型中进行选择。每种实例类型都提供不同的 CPU、RAM、存储和网络功能组合。
- 您可以配置安全组来控制对实例的访问（指定允许的端口和源）。
- 用户数据使您能够指定在实例首次启动时运行的脚本。
- 只能停止由 Amazon EBS 支持的实例。•您可以使用 Amazon CloudWatch 捕获和查看 EC2 实例上的指标。

![屏幕截图 2024-11-19 105155](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-19 105155.jpg)

请注意，Amazon RDS 实例的每小时成本高于类似大小的 EC2 实例。考虑成本时，不要忘记包括人工成本。例如，请记住，标准单可用区 Amazon RDS 部署（示例价格参考的基础）提供自动备份。使用 Amazon RDS，如果数据库实例组件发生故障并且需要用户启动的恢复操作，您将拥有一个可以使用的可恢复备份。如果您在 Amazon EC2 上运行数据库，则可以为 Microsoft SQL Server 配置同样强大的备份程序。但是，构建解决方案需要时间、知识和技术技能。您还需要在遇到需要它的情况之前预先配置解决方案。出于这些原因，当您全面考虑部署需求时，您可能会发现使用 Amazon RDS 比使用 Amazon EC2 更便宜。但是，如果您拥有熟练的数据库管理员，并且您有非常具体的部署要求，希望您能够完全控制部署的各个方面，那么您可以使用 Amazon EC2。在这种情况下，您可能会发现 Amazon EC2 是更具成本效益的解决方案。



### Section 3: Amazon EC2 cost optimization

![屏幕截图 2024-11-19 105310](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-19 105310.jpg)

当您想要运行 EC2 实例时，Amazon 提供不同的定价模型供您选择。

- **Per second billing 按秒计费**仅适用于运行 Amazon Linux 或 Ubuntu 的按需实例、预留实例和竞价实例。
- **On Demand 按需实例**符合 AWS 免费套餐 (https://aws.amazon.com/free/) 的条件。它们具有最低的前期成本和最大的灵活性。无需前期承诺或长期合同。对于具有短期、尖峰或不可预测的工作负载的应用程序来说，这是一个不错的选择。
- **Dedicated Hosts 专用主机**是具有实例容量的物理服务器，专供您使用。它们使您能够使用现有的每套接字、每核心或每虚拟机软件许可证，例如 Microsoft Windows 或 Microsoft SQL Server。
- **Dedicated Instances 专用实例**是在专用于单个客户的硬件上的虚拟私有云 (VPC) 中运行的实例。它们在主机硬件级别与属于其他 AWS 账户的实例物理隔离。 
- **Reserved Instance 预留实例**使您能够以较低的每小时运行成本预留 1 年或 3 年的计算容量。只要您拥有预留实例，折扣使用价格就是固定的。如果您预计会持续大量使用，与按需实例相比，它们可以为您节省大量成本。
- **Scheduled Reserved Instances 预定预留实例**使您能够购买按天、周或月重复的容量预留，期限为 1 年，持续时间为指定时间。即使您不使用实例，您也需要为实例的预定时间付费。
- **Spot Instances 竞价型实例**使您能够竞标未使用的 EC2 实例，从而降低您的成本。竞价型实例的每小时价格会根据供求情况而波动。只要您的出价超过当前市场价格，您的竞价型实例就会运行

![屏幕截图 2024-11-19 105501](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-19 105501.jpg)

每种 Amazon EC2 定价模型都提供不同的优势。

**On Demand Instances 按需实例**提供最大的灵活性，无需长期合同且费率低廉。

**Spot Instances 竞价型实例**以大幅折扣的价格提供大规模服务。

**Reserved Instances 预留实例**是一个不错的选择,如果您有可预测或稳定状态的计算需求的话（例如，您知道希望在几个月或几年内大部分时间或所有时间运行的实例）。

如果您对要在 Amazon EC2 上运行的软件有许可限制，或者您有特定的合规性或监管要求而无法使用其他部署选项，则**Dedicated Hosts 专用主机**是一个不错的选择。



![屏幕截图 2024-11-19 105647](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-19 105647.jpg)

以下是各种定价选项的一些用例回顾。

**On-Demand Instance 按需实例**定价适用于工作负载高峰期，或者您只需要在短时间内测试或运行应用程序（例如，在应用程序开发或测试期间）。

有时，您的工作负载是不可预测的，按需实例是这些情况下的不错选择。如果您的应用程序可以容忍中断并发出 2 分钟的警告通知，则 **Spot Instances**是不错的选择。默认情况下，实例会被终止，但您可以将其配置为停止或休眠。常见用例包括容错应用程序，例如 Web 服务器、API 后端和大数据处理。不断将数据保存到持久性存储（如 Amazon S3）的工作负载也是不错的选择。

当您拥有具有可预测使用模式的长期工作负载时，**Reserved Instances 预留实例**是一个不错的选择，例如您知道需要在未来数月内以一致的方式运行的服务器。

当您拥有现有的每个插槽、每个核心或每个虚拟机的软件许可证时，或者当您必须满足特定的企业合规性和监管要求时，**Dedicated Hosts 专用主机**是一个不错的选择。

![屏幕截图 2024-11-19 105849](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-19 105849.jpg)

要优化成本，您必须考虑四个一致、强大的驱动因素：

- 合适规模 – 选择合适的实例类型平衡。注意何时可以缩小服务器规模或关闭服务器，同时仍能满足您的性能要求。
- 提高弹性 – 通过实施弹性部署（例如使用自动扩展来处理峰值负载的部署），设计您的部署以减少闲置的服务器容量。
- 最佳定价模型 – 识别可用的定价选项。分析您的使用模式，以便您可以使用合适的定价选项组合运行 EC2 实例。
- 优化存储选择 – 分析部署的存储要求。尽可能减少未使用的存储开销，如果存储选项仍能满足您的存储性能要求，则选择较便宜的存储选项。

![屏幕截图 2024-11-19 105932](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-19 105932.jpg)

首先，考虑合理调整规模。AWS 提供大约 60 种实例类型和大小。广泛的选择使客户能够选择最适合其工作负载的实例。从技术角度和成本角度来看，很难知道从哪里开始以及哪种实例选择将被证明是最好的。合理调整规模是审查已部署资源并寻找可能缩小规模的机会的过程。

**To right size** 正确确定大小：

- **Select** 选择最便宜的实例，同时仍能满足您的性能要求。
- **Review** 检查 CPU、RAM、存储和网络利用率，以确定可以缩小大小的实例。您可能希望在测试环境中配置各种实例类型和大小，然后在这些不同的测试部署上测试您的应用程序，以确定哪些实例提供最佳性能成本比。要正确确定大小，请使用负载测试等技术来发挥您的优势。
- **Use** 使用 Amazon CloudWatch 指标并设置自定义指标。指标表示发布到 CloudWatch 的一组按时间顺序排列的值（例如，特定 EC2 实例的 CPU 使用率）。数据点可以来自您为其收集数据的任何应用程序或业务活动。

![屏幕截图 2024-11-19 110043](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-19 110043.jpg)

**elasticity 弹性**的一种形式是在需要时创建、启动或使用 EC2 实例，但在不使用时关闭它们。弹性是云的核心原则之一，但客户通常需要经历一个学习过程才能将弹性付诸实践，从而节省成本。

对于大型客户来说，采用弹性的最简单方法是寻找适合停止或休眠的资源，例如非生产环境、开发工作负载或测试工作负载。例如，如果您在单个时区内运行开发或测试工作负载，则可以轻松地在工作时间之外关闭这些实例，从而将运行时成本降低约 65%。这个概念类似于为什么门旁边有一个电灯开关，以及为什么大多数办公室鼓励员工每晚离开办公室时关灯。

对于生产工作负载，配置更精确、更细粒度的自动扩展策略可以帮助您利用水平扩展来满足峰值容量需求，而不必一直为峰值容量付费。

根据经验法则，您应该将 20% 到 30% 的 Amazon EC2 实例作为按需实例或 Spot 实例运行，并且还应该积极寻找最大化弹性的方法。

![屏幕截图 2024-11-19 110143](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-19 110143.jpg)

AWS 为 Amazon EC2 提供了多种定价模型，以帮助客户节省资金。本模块前面详细讨论了可用的模型。客户可以组合多种购买类型，以根据其当前和预测的容量需求优化定价。

我们还鼓励客户考虑他们的应用程序架构。例如，您的应用程序提供的功能是否需要在 EC2 虚拟机上运行？也许通过使用 AWS Lambda 服务，您可以显著降低成本。

本模块后面将讨论 AWS Lambda。

![屏幕截图 2024-11-19 110231](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-19 110231.jpg)



客户还可以降低存储成本。启动 EC2 实例时，不同的实例类型提供不同的存储选项。最佳做法是尝试降低成本，同时保持存储性能和可用性。

实现此目的的一种方法是**resizing EBS volumes 调整 EBS 卷的大小**。例如，如果您最初为 EC2 实例配置了一个 500 GB 的卷，而该实例最多只需要 20 GB 的存储空间，则可以减小卷的大小并节省成本。

还有各种**EBS volume types EBS 卷类型**。选择最便宜但仍然满足您的性能要求的类型。例如，Amazon EBS 吞吐量优化 HDD (st1) 存储的成本通常只有默认通用 SSD (gp2) 存储选项的一半。如果 st1 驱动器可以满足您的工作负载需求，请充分利用成本节省。

客户经常使用**EBS snapshots EBS 快照**来创建数据备份。但是，有些客户忘记删除不再需要的快照。删除这些不需要的快照以节省成本。

最后，尝试确定**appropriate destination for specific types of data 特定类型数据最合适的目的地**。您的应用程序是否需要将其使用的数据驻留在 Amazon EBS 上？如果应用程序改用 Amazon S3 进行存储，其运行效果是否一样好？配置数据生命周期策略还可以降低成本。例如，您可以自动将较旧的、不常访问的数据迁移到更便宜的存储位置，例如 Amazon Simple Storage Service Glacier。

![屏幕截图 2024-11-19 110454](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-19 110454.jpg)

如果操作正确，成本优化并不是客户一次性完成的过程。相反，通过定期测量和分析您的系统，您可以不断改进和调整成本。

**Tagging 标记**有助于提供有关哪些资源由谁使用以及用于什么目的的信息。您可以在账单和成本管理控制台中激活成本分配标签，AWS 可以生成成本分配报告，其中使用情况和成本按您的活动标签分组。应用代表业务类别（例如成本中心、应用程序名称或所有者）的标签来组织跨多项服务的成本

**Encourage teams to architect for cost 鼓励团队根据成本进行架构**。AWS Cost Explorer 是一款免费工具，可用于查看成本图表。您可以使用 Cost Explorer 查看一段时间内您在 AWS 资源上花费的模式，确定需要进一步调查的领域，并查看可用于了解成本的趋势。

使用 AWS 服务（例如 **AWS Trusted Advisor**），它提供实时指导，帮助您配置遵循 AWS 最佳实践的资源。

当将成本优化的责任分配给个人或团队时，成本优化工作通常会更成功。

**Section 3 key takeaways**

本模块此部分的一些关键要点如下：

- **Amazon EC2 pricing models** Amazon EC2 定价模型包括按需实例、预留实例、竞价实例、专用实例和专用主机。仅使用 Amazon Linux 和 Ubuntu 的按需实例、预留实例和竞价实例可按秒计费。

- **Spot Instances** 竞价实例可通过 2 分钟通知中断。但是，与按需实例相比，它们可以节省大量成本。

- 成本优化的四大支柱是–

  - Right size 合适的规模
  - Increase elasticit 增加弹性
  - Optimal pricing model 最佳定价模型
  - Optimize storage choices 优化存储选择

  

### Section 4: Container services

![屏幕截图 2024-11-19 110826](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-19 110826.jpg)

**Containers 容器**是一种**operating system virtualization**操作系统虚拟化方法，可让您在资源隔离的进程中运行应用程序及其依赖项。通过使用容器，您可以轻松地将应用程序的代码、配置和依赖项打包成易于使用的构建块，从而提供环境一致性、运营效率、开发人员生产力和版本控制。

容器比虚拟机小，不包含整个操作系统。相反，容器共享虚拟化操作系统并作为资源隔离的进程运行，从而确保快速、可靠和一致的部署。容器包含软件运行所需的一切，例如库、系统工具、代码和运行时。

容器提供**environmental consistency 环境一致性**，因为应用程序的代码、配置和依赖项被打包到单个对象中。

在空间方面，容器镜像通常比虚拟机小一个数量级。启动容器只需数百毫秒。因此，通过使用容器，您可以使用快速、便携且与基础设施无关的环境。

无论部署环境如何，容器都可以帮助确保应用程序快速、可靠且一致地部署。容器还可以让您更精细地控制资源，从而提高基础设施的效率。

![屏幕截图 2024-11-19 111001](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-19 111001.jpg)

**Docker** 是一个将软件（如应用程序）打包到容器中的软件平台。

Docker 安装在将托管容器的每台服务器上，它提供了可用于构建、启动或停止容器的简单命令。

通过使用 Docker，您可以快速部署和扩展应用程序到任何环境中。

当您想要执行以下操作时，Docker 是最佳解决方案：

- 标准化环境
- 减少语言堆栈和版本之间的冲突
- 使用容器作为服务
- 使用标准化代码部署运行微服务
- 要求数据处理的可移植性

![屏幕截图 2024-11-19 111125](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-19 111125.jpg)

很多初次接触容器概念的人认为容器与虚拟机完全一样。然而，两者的区别在于细节。一个显著的区别是虚拟机直接在虚拟机管理程序上运行，而容器可以在任何 Linux 操作系统上运行，前提是它们具有适当的内核功能支持并且存在 Docker 守护程序。这使得容器非常易于移植。您的笔记本电脑、VM、EC2 实例和裸机服务器都是可以运行容器的潜在主机。

**图表右侧有一个基于虚拟机 (VM) 的部署**。三个 EC2 实例中的每一个都直接在 AWS 全球基础设施提供的虚拟机管理程序上运行。每个 EC2 实例都运行一个虚拟机。在此基于 VM 的部署中，三个应用程序中的每一个都在自己的 VM 上运行，从而提供进程隔离。

**图左侧为基于容器的部署**。只有一个 EC2 实例运行虚拟机。Docker 引擎安装在 EC2 实例的 Linux 客户操作系统上，并且有三个容器。在此基于容器的部署中，每个应用程序都在其自己的容器中运行（这提供了进程隔离），但所有容器都在单个 EC2 实例上运行。在容器中运行的进程直接与 Linux 客户操作系统中的内核通信，并且基本上不知道它们的容器孤岛。Docker 引擎用于管理容器在 Linux 客户操作系统上的运行方式，并且它还在整个容器生命周期中提供必要的管理功能。

在实际的基于容器的部署中，大型 EC2 实例可以运行数百个容器。

![屏幕截图 2024-11-19 111303](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-19 111303.jpg)



鉴于您现在对容器的了解，您可能会认为您可以启动一个或多个 Amazon EC2 实例，在每个实例上安装 Docker，然后自己管理和运行这些 Amazon EC2 实例上的 Docker 容器。虽然这是一种选择，但 AWS 提供了一项名为 Amazon Elastic Container Service (Amazon ECS) 的服务来简化容器管理。

**Amazon Elastic Container Service (Amazon ECS)** 是一种高度可扩展、高性能的容器管理服务，支持 Docker 容器。Amazon ECS 使您能够在托管的 Amazon EC2 实例集群上轻松运行应用程序。

基本 Amazon ECS 功能包括：

- 在几秒钟内**启动**数万个 Docker 容器
- **监控**容器部署
- **管理**运行容器的集群的状态
- 使用内置**调度**程序或第三方调度程序（例如 Apache Mesos 或 Blox）调度容器

Amazon ECS 集群还可以使用 Spot 实例和预留实例。

![屏幕截图 2024-11-19 111439](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-19 111439.jpg)



要准备在 Amazon ECS 上运行您的应用程序，您需要创建一个**task definition** 任务定义，这是一个文本文件，用于描述构成您的应用程序的一个或多个容器（最多十个）。您可以将其视为应用程序的蓝图。任务定义指定应用程序的参数，例如要使用哪些容器、应为您的应用程序打开哪些端口以及应将哪些数据卷与任务中的容器一起使用。

**task 任务**是集群内任务定义的实例化。您可以指定集群上运行的任务数量。**Amazon ECS task scheduler**程序负责将任务放置在集群内。任务将在 1 到 10 个容器中运行，具体取决于您定义的任务定义。

当 Amazon ECS 运行组成任务的容器时，它会将它们放置在 **ECS cluster** 上。集群（当您选择 EC2 启动类型时）由一组 EC2 实例组成，每个实例都运行一个 **Amazon ECS container agent**。

Amazon ECS 提供多种调度策略，可根据您的资源需求（例如 CPU 或 RAM）和可用性要求将容器放置在您的集群中。

![屏幕截图 2024-11-19 111630](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-19 111630.jpg)

创建 Amazon ECS 集群时，您有三个选项：

- 仅**Networking Only** 网络集群（由 AWS Fargate 提供支持）
- **EC2 Linux + Networking** 
- An **EC2 Windows** + **Networking cluster**

如果您选择两种 **EC2 launch type** 选项之一，系统将提示您选择集群 EC2 实例是作为按需实例还是 Spot 实例运行。此外，您还需要指定组成集群的 EC2 实例的许多详细信息 — 启动独立 EC2 实例时必须指定这些详细信息。通过这种方式，EC2 启动类型可以更精细地控制运行容器应用程序的基础设施，因为您管理组成集群的 EC2 实例。Amazon ECS 会跟踪集群中的所有 CPU、内存和其他资源。Amazon ECS 还会根据您指定的资源需求为您的容器找到最佳服务器

如果您选择仅联网的 **Fargate  launch type**，则运行容器的集群将由 AWS 管理。使用此选项，您只需将应用程序打包到容器中，指定 CPU 和内存要求，定义网络和 IAM 策略，然后启动应用程序。您无需预置、配置或扩展集群。它消除了选择服务器类型、决定何时扩展集群或优化集群打包的需要。Fargate 选项使您能够专注于设计和构建应用程序。

![屏幕截图 2024-11-19 111832](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-19 111832.jpg)

**Kubernetes** 是用于容器编排的开源软件。Kubernetes 可以与许多容器化技术配合使用，包括 Docker。由于它是一个流行的开源项目，因此大量开发人员和公司构建了扩展、集成和插件，以保持软件的相关性，并经常添加新的和热门的功能。

Kubernetes 可让您大规模部署和管理**containerized applications 容器化应用程序**。借助 Kubernetes，您可以在本地数据中心和云中使用相同的工具集运行任何类型的容器化应用程序。Kubernetes 管理计算实例（称为节点）**cluster 集群**。它在集群上运行容器，这些容器基于可用的计算资源位置和每个容器的资源需求。容器以称为 **pods** 的逻辑分组运行。您可以将一个或多个容器作为一个 pod 一起运行和扩展。每个 pod 都有一个 IP 地址和一个域名系统 (DNS) 名称，Kubernetes 使用这些名称将您的服务相互连接并连接外部流量。

Kubernetes 的一个主要优势是，您可以使用它在任何地方运行容器化应用程序，而无需更改操作工具。例如，可以使用相同的操作工具将应用程序从本地开发机器移动到云中的生产部署。

![屏幕截图 2024-11-19 112323](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-19 112323.jpg)

您可能认为可以启动一个或多个 Amazon EC2 实例，在每个实例上安装 Docker，在集群上安装 Kubernetes，然后自行管理和运行 Kubernetes。虽然这是一种选择，但 AWS 提供了一项名为 Amazon Elastic Kubernetes Service (Amazon EKS) 的服务，可简化 Kubernetes 集群的管理。

**Amazon Elastic Kubernetes Service (Amazon EKS)** 是一项托管的 Kubernetes 服务，让您可以轻松地在 AWS 上运行 Kubernetes，而无需安装、操作和维护您自己的 Kubernetes 控制平面。它经过认证，符合 Kubernetes 标准，因此在上游 Kubernetes 上运行的现有应用程序与 Amazon EKS 兼容。

Amazon EKS 自动管理负责启动和停止容器、在虚拟机上调度容器、存储集群数据和其他任务的集群节点的可用性和可扩展性。它会自动检测并替换每个集群的运行状况不佳的控制平面节点。您可以利用 AWS 云的性能、规模、可靠性和可用性，其中包括 AWS 网络和安全服务，例如用于负载分配的应用程序负载均衡器、用于基于角色的访问控制的 IAM 以及用于 Pod 网络的 VPC。

您可能想知道为什么亚马逊同时提供 Amazon ECS 和 Amazon EKS，因为它们都能够编排 Docker 容器。这两项服务存在的原因是为了为客户提供灵活的选择。您可以决定哪种选择最符合您的需求。

![屏幕截图 2024-11-19 112414](C:\Users\EACH\Desktop\Large-Scale Data Engineering 2024\Cloud big data development\asset\image\屏幕截图 2024-11-19 112414.jpg)

**Amazon Elastic Container Registry (Amazon ECR)** 是一个完全托管的 Docker 容器注册表，可让开发人员轻松存储、管理和部署 Docker 容器映像。它与 **integrated with Amazon ECS** Amazon ECS 集成，因此您可以存储、运行和管理在 Amazon ECS 上运行的应用程序的容器映像。在任务定义中指定 Amazon ECR 存储库，Amazon ECS 将为您的应用程序检索适当的映像。

Amazon ECR 支持 Docker Registry HTTP API 版本 2，这让您可以使用 Docker CLI 命令或您首选的 Docker 工具与 Amazon ECR 进行交互。因此，您可以维护现有的开发工作流程并从任何 Docker 环境访问 Amazon ECR — 无论是在云中、本地还是本地计算机上。

您可以通过 HTTPS 将容器映像传输到 Amazon ECS 或从 Amazon ECS 传输容器映像。您的映像还会使用 Amazon S3 服务器端加密自动进行静态加密。

**Section 4 key takeaways**

本节的一些关键要点包括：

- 容器可以容纳应用程序运行所需的一切。
- Docker 是一个将软件打包到容器中的软件平台。
- 单个应用程序可以跨多个容器。
- Amazon Elastic Container Service (Amazon ECS) 协调 Docker 容器的运行。
- Kubernetes 是用于容器编排的开源软件。
- Amazon Elastic Kubernetes Service (Amazon EKS) 使您能够在 AWS 上运行 Kubernetes
- Amazon Elastic Container Registry (Amazon ECR) 使您能够存储、管理和部署 Docker 容器。



### Section 5: Introduction to AWS Lambda





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







# Course Assessment

**1.Which IT requirement would lead an architect to choose an infrastructure as a service (laaS) cloud service model?**

A.A company wants to run a managed instance for the marketplace.
B.A company wants to maintain the highest level of flexibility over its IT resources.
C.A company wants to maintain control of its applications but avoid maintaining servers and operating systems.
D.A company wants to use a web-based email solution.



**2.Which statement describes the business perspective of the AWS Cloud AdoptionFramework?**

A.Stakeholders can evaluate organizational structures and roles, new skill and process requirements, and identify gaps.
B.Stakeholders can focus on the skills and processes that are needed to align ITstrategy and goals with business strategy and goals.
C.Stakeholders can create a strong business case for cloud adoption and prioritizecloud adoption initiatives.
D.Stakeholders can use architectural dimensions and models to understand andcommunicate the nature of IT systems and their relationships.



**3.Which statement accurately describes how customers can use AWS Support?**

A.Customers must choose one of three support plans: Basic Support, Business Support, and Enterprise Support.
B.Customers can get AWS Support for both experimental non-production accounts and for business-critical production accounts.
C.Customers should contact their Support Concierge to provide quick and efficient technical support.
D.Customers are assigned a Technical Account Manager (TAM) for all AWS Supportd plans.



**4.Which factors are considered in calculating the total cost of ownership (TCO) for the AWS Cloud? (Select TWO.)**

A.The number of users that need to be migrated to the cloud
B.The amount of storage that needs to be migrated to the cloud
C.The number of servers that need to be migrated to the cloud
D.The number of groups that need to be migrated to the cloud
E.The number of roles that need to be migrated to the cloud



**5.Which statement about AWS Regions is true?**

A.Using a Region as close as possible to users can reduce latency.
B.All available Regions are enabled by default in an AWS account.
C.All AWS accounts can access all AWS Regions.
D.Data stored in an AWS Region isn't subject to geographical compliance requirements.



**6.Which statements about responsibility are accurate based on the AWS shared responsibility model? (Select TWO.)**

A.AWS is responsible for deciding what data to encrypt in customers' Amazon S3 buckets.
B.AWS is responsible for the physical security of data centers.
C.Customers are responsible for managing their user data.
D.AWS is responsible for the configuration of security groups.
E.Customers are responsible for the installation, maintenance, and decommissioning of the hardware that they use in the AWS data center.



**7.A company must produce reports of any changes to its Amazon EC2 instance settings. Which AWS service should they use?**

A.Amazon Cloud
B.WatchAWS Artifact
C.AWS Config
D.AWS CloudTrail



**8.A network administrator wants to run their ecommerce web application on a virtual private cloud (VPC). Which step is part of setting up the VPC? (Select TWO.)**

A.Create the main route table.
B.Delete the local route in the route table.
C.Attach the VPC to a security group.
D.Specify the range of IP addresses for the VPC.
E.Create private and public subnets.



**9.Which configuration represents a valid use of security groups in a virtual private cloud (VPC)?**

A.Set a deny rule that prevents outbound traffic from an Amazon EC2 instance in a VPC.
B.Set a deny rule that prevents access to the subnet from the public internet.
C.Limit inbound access to the private subnet of the VPC.
D.Limit outbound traffic from an Amazon EC2 instance in the VPC to a specific database server.



**10.A company needs to run a short script each time a new item is added to an Amazon S3 bucket. Which compute option meets the need with the least amount of resource provisioning? Container Service (Amazon ECS).**

A.Set up the script to run in a container, and deploy the container on Amazon Elastic
B.Create an AWS Lambda function to run the script whenever a new item is added tothe bucket.
C.Write a batch job to run the script on all new items overnight when there's lesscompetition for resources. Run the batch job on Spot Instances.
D.Set up a small Amazon EC2 instance that runs code to check for new uploads to thebucket and runs the script.



**11.A company has a set of big data processing jobs in Amazon Simple Queue Service (Amazon SQS) that need a lot of compute. Which Amazon EC2 instancing pricing model would meet the need at the lowest possible cost?**

A.Spot Instance
B.On-Demand Instance
C.Reserved Instance
D.Scheduled Reserved Instance



**12.Which statement about Amazon Elastic Block Store (Amazon EBS) is true?**

A.Amazon EBS volumes persist independently from the Amazon EC2 instances that they're attached to.
B.Amazon EBS volumes aren't recommended for storage that requires frequent updating.
C.Amazon EBS volumes can't be resized.
D.Amazon EBS volumes are automatically replicated across multiple Availability Zones.



**13.A company needs to store long-lived data. They need the data to be available immediately, but access patterns are unpredictable. Which Amazon S3 storage class would be most cost-effective?**

A.Amazon S3 Glacier
B.Amazon S3 One Zone-Infrequent Access
C.Amazon S3 Standard
D.Amazon S3 Intelligent-Tiering



**14.Which scenario describes a good use case for Amazon S3 Standard storage?**

A.Sharing an NFS file system
B.Hosting website images
C.Running a relational database
D.Act as an EC2 instance store.



**15.Which option is a company's responsibility when running Amazon RDS?**

A.Database software patching
B.Application optimization
C.Operating system patching
D.Operating system installation



**16.Which scenario is a good fit for Amazon Redshift?**

A.A company needs a data warehouse to support analytics applications.
B.A company needs to store large volumes of mixed media image and video files.
C.A company needs a database for managing unstructured data.
D.A company needs a relational database for a line-of-business transactional database.



**17.Which statement reflects a design principle of the Security pillar of the AWS WellArchitected Framework?**

A.Decentralize permissions management.
B.Ensure that staff are actively monitoring potential risks manually.
C.Apply security at all layers of an architecture.
D.Don't deploy a solution to production until you're certain that there are no security risks.



**18.For which type of use case is it usually OK to have 2 nines of availability (99%)?**

A.Internet of Things (loT) applications
B.ATM transactions
C.Batch processing
D.Online commerce



**19.A company has an application running on two Amazon EC2 instances. They want to reduce idle EC2 capacity. The application load is difficult to forecast, and they want to keep the CPU utilization close to 40 percent on all instances. Which type of Amazon EC2 Auto Scaling should they configure?**

A.Dynamic scaling
B.Scheduled scaling
C.Predictive scaling
D.Manual scaling



**20.Which statement accurately describes how Amazon EC2 Auto Scaling is used?**

A.Amazon EC2 Auto Scaling is useful for dynamic, unpredictable workloads but doesn't add much value for predictable workloads.
B.Amazon EC2 Auto scaling is useful for predictable workloads.
C.The size of an Amazon EC2 Auto Scaling group will scale up and down automatically based on its configuration and the number of instances can't be manually adjusted.
D.Amazon EC2 Auto scaling allows an application to automatically add resources, but it can't automatically scale them back down.

1.B
2.NOT A
3.B
4.B C 
5.A
6.B C
7.C
8.D E
9.D
10.B
11.A
12.A
13.D
14.B
15.NOT A
16.A
17.C
18.B
19.A
20.NOT A
