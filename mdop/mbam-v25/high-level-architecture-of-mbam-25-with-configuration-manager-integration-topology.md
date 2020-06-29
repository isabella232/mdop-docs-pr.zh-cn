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
ms.openlocfilehash: 75af2e22981d76568916c36acadbbb25648b1f1d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803833"
---
# 具有 Configuration Manager 集成拓扑的 MBAM 2.5 的高级别体系结构

本主题介绍了使用 Configuration Manager 集成拓扑部署 Microsoft BitLocker 管理和监视（MBAM）的推荐体系结构。 此拓扑将 MBAM 与 System Center Configuration Manager 集成。 若要使用独立拓扑部署 MBAM，请参阅[使用独立拓扑的 MBAM 2.5 的高级别体系结构](high-level-architecture-of-mbam-25-with-stand-alone-topology.md)。

有关本主题中所述软件的受支持版本的列表，请参阅[MBAM 2.5 支持的配置](mbam-25-supported-configurations.md)。

**重要提示** 使用 Configuration Manager 2007 时，Configuration Manager 集成拓扑安装不支持 Windows To Go。

 

## 推荐的服务器数和受支持的客户端数


生产环境中推荐的服务器数和受支持的客户端数量如下所示：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">推荐的体系结构</th>
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
<td align="left"><p>支持的客户端计算机数</p></td>
<td align="left"><p>500,000</p></td>
</tr>
</tbody>
</table>

 

## Configuration Manager 集成和独立拓扑之间的差异


拓扑的主要区别如下：

-   将从 MBAM 中删除合规性和报告功能，并从配置管理器访问。

-   从 Configuration Manager 管理控制台查看报表，除了恢复审核报告之外，还可从 MBAM 管理和监视网站继续查看。

## 使用 Configuration Manager 集成拓扑推荐的 MBAM 高级别体系结构


下图和表介绍了 MBAM 与 Configuration Manager 集成拓扑的推荐高级别体系结构。 MBAM 多林部署需要单向或双向信任。 单向信任要求服务器域信任客户端域。

![mbam2\-5](images/mbam2-5-cmserver.png)

### 数据库服务器

#### 恢复数据库

此功能在运行 Windows Server 和支持的 SQL Server 实例的计算机上配置。

**恢复数据库**存储从 MBAM 客户端计算机收集的恢复数据。

#### 审核数据库

此功能在运行 Windows Server 和支持的 SQL Server 实例的计算机上配置。

**审核数据库**存储从已访问恢复数据的客户端计算机收集的审核活动数据。

#### 报告

此功能在运行 Windows Server 和支持的 SQL Server 实例的计算机上配置。

**报告**为企业中的客户端计算机提供恢复审核数据。 你可以从 Configuration Manager 控制台或直接从 SQL Server Reporting Services 查看报表。

### Configuration Manager 主站点服务器

System Center Configuration Manager 集成功能

-   此功能在 Configuration Manager 主站点服务器（配置管理器基础结构中的顶层服务器）上配置。

-   **Configuration Manager 服务器**从客户端计算机收集硬件清单信息，并用于报告客户端计算机的 BitLocker 合规性。

-   当运行 Microsoft BitLocker 管理和监视设置向导安装服务器软件时，配置管理器主站点服务器上配置了 MBAM 支持的计算机集合、配置基线和报告。

-   **Configuration Manager 控制台**必须安装在安装了 MBAM Server 软件的同一计算机上。

### 管理和监视服务器

#### 管理和监视网站

此功能在运行 Windows Server 的计算机上配置。

**管理和监视网站**用于：

-   当用户被锁定时，帮助最终用户重新获得对其计算机的访问权限。（此网站区域通常称为 "帮助桌面"。）

-   查看恢复审核报告，该报告显示客户端计算机的恢复活动。 从 Configuration Manager 控制台查看其他报告。

#### 自助服务门户

此功能在运行 Windows Server 的计算机上配置。

**自助服务门户**是一种网站，使客户端计算机上的最终用户能够独立登录到网站以获取恢复密钥（如果他们丢失或忘记其 BitLocker 密码）。

#### 监视此网站的 web 服务

此功能安装在运行 Windows Server 的计算机上。

**监视 web 服务**由 MBAM 客户端和网站用于与数据库通信。

**重要提示**<br>由于 MBAM 网站直接与恢复数据库通信，因此在 Microsoft BitLocker 管理和监视（MBAM） 2.5 SP1 中不再提供监视 Web 服务。 

 

### 管理工作站

#### MBAM 组策略模板

-   **MBAM 组策略模板**是定义 MBAM 的实现设置的组策略设置，使你能够管理 BitLocker 驱动器加密。

-   在运行 MBAM 之前，你必须从[如何获取 MDOP 组策略（admx）模板](https://go.microsoft.com/fwlink/p/?LinkId=393941)中下载组策略模板，并将其复制到运行受支持的 Windows Server 或 Windows 操作系统的服务器或工作站。

    **注意**<br>工作站不必是专用计算机。

     

### MBAM 客户端和 Configuration Manager 客户端计算机

#### MBAM 客户端软件

**MBAM 客户端**：

-   使用组策略对象对企业中的客户端计算机强制执行 BitLocker 驱动器加密。

-   收集三种数据驱动器类型的 BitLocker 恢复密钥：操作系统驱动器、固定数据驱动器和可移动（USB）数据驱动器。

-   收集有关客户端计算机的恢复信息和计算机信息。

#### Configuration Manager 客户端

**Configuration Manager 客户端**使 configuration manager 能够收集有关客户端计算机的硬件兼容性数据和报告合规性信息。

 

## 支持的 Configuration Manager 版本的 MBAM 部署中的差异


使用 Configuration Manager 集成拓扑部署 MBAM 时，可以在主站点服务器上安装 MBAM。 但是，对于 System Center2012 Configuration Manager 和配置 Manager2007，MBAM 安装的运行方式有所不同。

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
<td align="left"><p>System Center2012 R2 配置管理器</p>
<p>System Center2012 Configuration Manager</p></td>
<td align="left"><p>如果在主站点服务器或中央管理服务器上安装 MBAM，MBAM 将执行该站点服务器上的所有安装操作。</p></td>
</tr>
<tr class="even">
<td align="left"><p>配置 Manager2007 R2</p>
<p>配置 Manager2007</p></td>
<td align="left"><p>如果在具有中央站点父服务器的大型 Configuration Manager 层次结构的一部分的主站点服务器上安装 MBAM，MBAM 将标识中心网站父服务器并执行该父服务器上的所有安装操作。 安装包括检查先决条件以及安装 Configuration Manager 对象和报告。</p>
<p>例如，如果在作为中心站点父服务器的子站点的主站点服务器上安装 MBAM，则 MBAM 将在父服务器上安装所有 Configuration Manager 对象和报告。 如果在父服务器上安装 MBAM，MBAM 将在该父服务器上执行所有安装操作。</p></td>
</tr>
</tbody>
</table>

 

## MBAM 如何与 Configuration Manager 配合使用


与 Configuration Manager 的 MBAM 集成基于安装下表中所述项目的配置包。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">安装到 Configuration Manager 的项目</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>配置数据</p></td>
<td align="left"><p>配置数据将安装名为 "BitLocker 保护" 的配置基线，其中包含两个配置项目：</p>
<ul>
<li><p>BitLocker 操作系统驱动器保护</p></li>
<li><p>BitLocker 固定数据驱动器保护</p></li>
</ul>
<p>配置基线将部署到 "MBAM 支持的计算机" 集合，该集合也是在安装 MBAM 时创建的。</p>
<p>这两个配置项目提供评估客户端计算机合规性状态的基础。 在 Configuration Manager 中捕获、存储和评估此信息。</p>
<p>配置项目基于操作系统驱动器和固定数据驱动器的合规性要求。 收集已部署计算机所需的详细信息，以便可以评估这些驱动器类型的合规性。</p>
<p>默认情况下，配置基线会评估合规性状态 every12 小时，并将合规性数据发送到 Configuration Manager。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MBAM 支持的计算机集合</p></td>
<td align="left"><p>MBAM 将创建一个名为 MBAM 支持的计算机的集合。 配置基线针对此集合中的客户端计算机。</p>
<p>这是一个动态集合。 默认情况下，它根据以下三个条件运行 every12 小时并评估成员身份：</p>
<ul>
<li><p>计算机是受支持的 Windows 操作系统版本。</p></li>
<li><p>计算机是物理计算机。 不支持虚拟机。</p></li>
<li><p>计算机具有可用的受信任的平台模块（TPM）。 Windows7 需要有兼容版本的 TPM 1.2 或更高版本。 Windows10、Windows 8.1、Windows8 和 Windows To Go 不需要 TPM。</p></li>
</ul>
<p>将为所有计算机计算集合，并创建兼容计算机的子集，这将为 MBAM 集成提供合规性评估和报告的基础。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>报告</p></td>
<td align="left"><p>通过 Configuration Manager 集成拓扑配置 MBAM 时，你可以在 "配置管理器" 中查看除 "恢复审核" 报表之外的所有报表，后者是你继续在 MBAM 管理和监视网站中查看的。 配置管理器中可用的报表有：</p>
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
<td align="left"><p>BitLocker 企业合规性仪表板</p></td>
<td align="left"><p>向 IT 管理员提供单个报告中的三个信息视图：合规性状态分发、不合规性-错误分发以及合规性状态按驱动器类型分发。 报表上的向下钻取选项让 IT 管理员可以单击浏览数据并查看与选定状态匹配的计算机列表。</p></td>
</tr>
<tr class="even">
<td align="left"><p>BitLocker 企业合规性详细信息</p></td>
<td align="left"><p>允许 IT 管理员查看有关企业的 BitLocker 加密合规性状态的信息，包括每台计算机的合规性状态。 报表上的向下钻取选项让 IT 管理员可以单击浏览数据并查看与选定状态匹配的计算机列表。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>BitLocker 计算机合规性</p></td>
<td align="left"><p>允许 IT 管理员查看单个计算机并确定报告其状态为 "合规" 或 "不合规" 的原因。 该报告还显示操作系统驱动器和固定数据驱动器的加密状态。</p></td>
</tr>
<tr class="even">
<td align="left"><p>BitLocker 企业合规性摘要</p></td>
<td align="left"><p>允许 IT 管理员查看企业中 MBAM 策略合规性的状态。 评估每台计算机的省/市/自治区，并且报告将显示企业中所有计算机针对策略的合规性摘要。 报表上的向下钻取选项让 IT 管理员可以单击浏览数据并查看与选定状态匹配的计算机列表。</p></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
</tbody>
</table>

 


## 相关主题


[MBAM 2.5 入门](getting-started-with-mbam-25.md)

[采用独立拓扑的 MBAM 2.5 的高级别体系结构](high-level-architecture-of-mbam-25-with-stand-alone-topology.md)

[图示 MBAM 2.5 部署的功能](illustrated-features-of-an-mbam-25-deployment.md)

 

 
## 已获得 MBAM 的建议？
- 在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。 
- 对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。




