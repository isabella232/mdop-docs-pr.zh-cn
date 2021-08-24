---
title: 采用 Configuration Manager 集成拓扑的 MBAM 2.5 的高级别体系结构
description: 采用 Configuration Manager 集成拓扑的 MBAM 2.5 的高级别体系结构
author: dansimp
ms.assetid: 075bafa1-792b-4c24-9d8e-5d3153e2112c
ms.reviewer: ''
manager: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/23/2018
ms.author: dansimp
ms.openlocfilehash: a0f9349391794100a670e382bb18d0713f4b5b60
ms.sourcegitcommit: 3e0500abde44d6a09c7ac8e3caf5e25929b490a4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2021
ms.locfileid: "11910717"
---
# <a name="high-level-architecture-of-mbam-25-with-configuration-manager-integration-topology"></a>具有 Configuration Manager 集成拓扑的 MBAM 2.5 高级体系结构

本主题介绍使用 Configuration Manager 集成拓扑部署 Microsoft BitLocker 管理和 (MBAM) 的建议体系结构。 此拓扑将 MBAM 与 System Center Configuration Manager。 若要使用独立拓扑部署 MBAM，请参阅使用独立拓扑的 [MBAM 2.5 高级体系结构](high-level-architecture-of-mbam-25-with-stand-alone-topology.md)。

有关本主题中提到的软件受支持版本的列表，请参阅[MBAM 2.5 Supported Configurations。](mbam-25-supported-configurations.md)

**重要提示**  
Windows在使用 Configuration Manager 2007 时，配置管理器集成拓扑安装不支持"转到"。

 

## <a name="recommended-number-of-servers-and-supported-number-of-clients"></a>建议的服务器数量和支持的客户端数量


在生产环境中建议的服务器数量和支持的客户端数量如下所示：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">建议的体系结构</th>
<th align="left">详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>服务器和其他计算机的数量</p></td>
<td align="left"><p>三台服务器</p>
<p>一个工作站</p></td>
</tr>
<tr class="even">
<td align="left"><p>支持的客户端计算机数量</p></td>
<td align="left"><p>500,000</p></td>
</tr>
</tbody>
</table>

 

## <a name="differences-between-configuration-manager-integration-and-stand-alone-topologies"></a>Configuration Manager 集成和独立拓扑之间的差异


拓扑之间的主要区别是：

-   合规性和报告功能已从 MBAM 中删除，并且从 Configuration Manager 访问。

-   报告从 Configuration Manager 管理控制台查看，但恢复审核报告除外，你可以继续从 MBAM 管理和监控网站查看该报告。

## <a name="recommended-mbam-high-level-architecture-with-the-configuration-manager-integration-topology"></a>建议的 MBAM 高级体系结构与 Configuration Manager 集成拓扑


下图和表介绍了使用 Configuration Manager 集成拓扑为 MBAM 建议的高级别体系结构。 MBAM 多林部署需要单向或双向信任。 单向信任要求服务器域信任客户端域。

![mbam2\-5。](images/mbam2-5-cmserver.png)

### <a name="database-server"></a>数据库服务器

#### <a name="recovery-database"></a>恢复数据库

此功能在运行 Windows Server 且受支持SQL Server计算机上配置。

恢复 **数据库** 存储从 MBAM 客户端计算机收集的恢复数据。

#### <a name="audit-database"></a>审核数据库

此功能在运行 Windows Server 且受支持SQL Server计算机上配置。

审核 **数据库** 存储从已访问恢复数据的客户端计算机收集的审核活动数据。

#### <a name="reports"></a>报告

此功能在运行 Windows Server 且受支持SQL Server计算机上配置。

报告 **提供** 企业中客户端计算机的恢复审核数据。 你可以从 Configuration Manager 控制台或直接从配置管理器控制台查看SQL Server Reporting Services。

### <a name="configuration-manager-primary-site-server"></a>Configuration Manager 主站点服务器

System Center Configuration Manager集成功能

-   此功能在 Configuration Manager 主站点服务器上配置，该服务器是 Configuration Manager 基础结构中的顶层服务器。

-   Configuration **Manager Server** 从客户端计算机收集硬件清单信息，并用于报告客户端计算机的 BitLocker 合规性。

-   运行 Microsoft BitLocker 管理和监视安装向导以安装服务器软件时，MBAM 支持的计算机集合、配置基线和报告在 Configuration Manager 主站点服务器上配置。

-   Configuration **Manager 控制台** 必须安装在安装 MBAM 服务器软件的计算机上。

### <a name="administration-and-monitoring-server"></a>管理和监控服务器

#### <a name="administration-and-monitoring-website"></a>管理和监视网站

此功能在运行 Windows Server 的计算机上配置。

管理和 **监控网站** 用于：

-   帮助最终用户在被锁定时重新获得对计算机的访问权限。 (网站的此区域通常称为 Help Desk.) 

-   查看恢复审核报告，其中显示客户端计算机的恢复活动。 其他报告从 Configuration Manager 控制台查看。

#### <a name="self-service-portal"></a>自助服务门户

此功能在运行 Windows Server 的计算机上配置。

自助式 **门户** 是一个网站，使客户端计算机上的最终用户能够在丢失或忘记 BitLocker 密码时独立登录到网站，获取恢复密钥。

#### <a name="monitoring-web-services-for-this-website"></a>监视此网站的 Web 服务

此功能安装在运行 Windows Server 的计算机上。

**MBAM**客户端和网站使用监视 Web 服务与数据库通信。

**重要提示**<br>Microsoft BitLocker 管理和监视 (MBAM) 2.5 SP1 中不再提供监控 Web 服务，因为 MBAM 网站直接与恢复数据库通信。 

 

### <a name="management-workstation"></a>管理工作站

#### <a name="mbam-group-policy-templates"></a>MBAM 组策略模板

-   **MBAM 组策略模板**是定义 MBAM 实现设置的组策略设置，可让你管理 BitLocker 驱动器加密。

-   在运行 MBAM 之前，必须下载如何获取 MDOP 组策略[ (.admx) ](https://go.microsoft.com/fwlink/p/?LinkId=393941)模板中的组策略模板，并复制到运行受支持的 Windows Server 或 Windows 操作系统的服务器或工作站。

    **注意**<br>工作站不需要是专用计算机。

     

### <a name="mbam-client-and-configuration-manager-client-computer"></a>MBAM 客户端和 Configuration Manager 客户端计算机

#### <a name="mbam-client-software"></a>MBAM 客户端软件

**MBAM 客户端**：

-   使用组策略对象在企业中的客户端计算机上强制执行 BitLocker 驱动器加密。

-   收集三种数据驱动器类型的 BitLocker 恢复密钥：操作系统驱动器、固定数据驱动器和可移动 (USB) 数据驱动器。

-   收集有关客户端计算机的恢复信息和计算机信息。

#### <a name="configuration-manager-client"></a>Configuration Manager 客户端

Configuration **Manager 客户端** 使 Configuration Manager 能够收集有关客户端计算机的硬件兼容性数据并报告合规性信息。

 

## <a name="differences-in-mbam-deployment-for-supported-configuration-manager-versions"></a>受支持 Configuration Manager 版本的 MBAM 部署的差异


使用 Configuration Manager 集成拓扑部署 MBAM 时，可以在主站点服务器上安装 MBAM。 但是，对于 System Center 2012 Configuration Manager 和 Configuration Manager 2007，MBAM 安装的工作方式有所不同。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Configuration Manager 版本</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>System Center 2012 R2 Configuration Manager</p>
<p>System Center 2012 Configuration Manager</p></td>
<td align="left"><p>如果在主站点服务器或管理中心服务器上安装 MBAM，MBAM 将执行该站点服务器上的所有安装操作。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Configuration Manager 2007 R2</p>
<p>配置管理器 2007</p></td>
<td align="left"><p>如果在包含中央站点父服务器的较大 Configuration Manager 层次结构的一部分的主站点服务器上安装 MBAM，MBAM 将标识中央站点父服务器，并针对该父服务器执行所有安装操作。 安装包括检查必备组件和安装 Configuration Manager 对象和报告。</p>
<p>例如，如果你在作为中央站点父服务器的子级的主站点服务器上安装 MBAM，MBAM 将安装父服务器上所有 Configuration Manager 对象和报告。 如果在父服务器上安装 MBAM，MBAM 将执行该父服务器上的所有安装操作。</p></td>
</tr>
</tbody>
</table>

 

## <a name="how-mbam-works-with-configuration-manager"></a>MBAM 如何与 Configuration Manager 一起工作


MBAM 与 Configuration Manager 的集成基于安装下表中所述项目的配置包。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">安装到 Configuration Manager 中的项目</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>配置数据</p></td>
<td align="left"><p>配置数据将安装一个称为"BitLocker Protection"的配置基线，其中包含两个配置项：</p>
<ul>
<li><p>BitLocker 操作系统驱动器保护</p></li>
<li><p>BitLocker 固定数据驱动器保护</p></li>
</ul>
<p>配置基线将部署到 MBAM 支持的计算机集合，该集合也是在安装 MBAM 时创建的。</p>
<p>这两个配置项为评估客户端计算机的合规性状态提供了基础。 此信息在 Configuration Manager 中捕获、存储和评估。</p>
<p>配置项基于操作系统驱动器和固定数据驱动器的合规性要求。 收集已部署计算机所需的详细信息，以便评估这些驱动器类型的合规性。</p>
<p>默认情况下，配置基线每 12 小时评估一次合规性状态，并将合规性数据发送到 Configuration Manager。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MBAM 支持的计算机集合</p></td>
<td align="left"><p>MBAM 创建一个称为 MBAM 支持的计算机的集合。 配置基线面向此集合中的客户端计算机。</p>
<p>这是一个动态集合。 默认情况下，它每 12 小时运行一次，并基于以下三个条件评估成员身份：</p>
<ul>
<li><p>计算机是支持的操作系统Windows版本。</p></li>
<li><p>计算机是物理计算机。 不支持虚拟机。</p></li>
<li><p>计算机具有受信任的平台模块 (TPM) 可用。 TPM 1.2 或更高版本的兼容版本是 Windows 7。 Windows 10、Windows 8.1、Windows 8 和 Windows To Go 不需要 TPM。</p></li>
</ul>
<p>集合将针对所有计算机进行评估，并创建兼容计算机的子集，这为 MBAM 集成的合规性评估和报告提供了基础。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>报告</p></td>
<td align="left"><p>使用 Configuration Manager 集成拓扑配置 MBAM 时，你将在 Configuration Manager 中查看所有报告，但恢复审核报告除外，后者将继续在 MBAM 管理和监控网站中查看。 Configuration Manager 中可用的报告包括：</p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">报告</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>BitLocker 企业级合规性仪表板</p></td>
<td align="left"><p>为 IT 管理员提供单个报告中的三个信息视图：合规性状态分布、不兼容 – 错误分布和按驱动器类型表示的合规性状态分发。 通过报告上的向下钻取选项，IT 管理员可单击数据并查看与所选状态匹配的计算机列表。</p></td>
</tr>
<tr class="even">
<td align="left"><p>BitLocker 企业级合规性详细信息</p></td>
<td align="left"><p>允许 IT 管理员查看有关企业的 BitLocker 加密合规性状态的信息，并包括每台计算机的合规性状态。 通过报告上的向下钻取选项，IT 管理员可单击数据并查看与所选状态匹配的计算机列表。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>BitLocker 计算机合规性</p></td>
<td align="left"><p>允许 IT 管理员查看单个计算机并确定报告计算机状态是否符合标准的原因。 该报告还显示操作系统驱动器和固定数据驱动器的加密状态。</p></td>
</tr>
<tr class="even">
<td align="left"><p>BitLocker 企业级合规性摘要</p></td>
<td align="left"><p>允许 IT 管理员查看企业中 MBAM 策略合规性的状态。 将评估每台计算机的状态，并且报告根据策略显示企业中所有计算机的合规性摘要。 通过报告上的向下钻取选项，IT 管理员可单击数据并查看与所选状态匹配的计算机列表。</p></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
</tbody>
</table>

 


## <a name="related-topics"></a>相关主题


[MBAM 2.5 入门](getting-started-with-mbam-25.md)

[采用独立拓扑的 MBAM 2.5 的高级别体系结构](high-level-architecture-of-mbam-25-with-stand-alone-topology.md)

[图示 MBAM 2.5 部署的功能](illustrated-features-of-an-mbam-25-deployment.md)

 

 
## <a name="got-a-suggestion-for-mbam"></a>有关于 MBAM 的建议吗？
- 在此处添加建议或对建议 [投票](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)。 
- 对于 MBAM 问题，请使用 [MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。




