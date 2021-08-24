---
title: 采用独立拓扑的 MBAM 2.5 的高级别体系结构
description: 采用独立拓扑的 MBAM 2.5 的高级别体系结构
author: dansimp
ms.assetid: 35f8c5f6-8be3-443d-baf0-56d68b08f3bc
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 9ec9b1e4391fde3083564f34b5f89d1c5bd174f7
ms.sourcegitcommit: 3e0500abde44d6a09c7ac8e3caf5e25929b490a4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2021
ms.locfileid: "11910667"
---
# <a name="high-level-architecture-of-mbam-25-with-stand-alone-topology"></a>采用独立拓扑的 MBAM 2.5 的高级别体系结构


本主题介绍使用 Configuration Manager 独立拓扑部署 Microsoft BitLocker 管理和 (MBAM) 的建议体系结构。 在此拓扑中，MBAM 部署为独立产品。 或者，可以使用 Configuration Manager 集成拓扑部署 MBAM，该拓扑将 MBAM 与 Configuration Manager 集成。 有关详细信息，请参阅使用 Configuration Manager 集成拓扑的 [MBAM 2.5 高级体系结构](high-level-architecture-of-mbam-25-with-configuration-manager-integration-topology.md)。

有关本主题中提到的软件受支持版本的列表，请参阅[MBAM 2.5 Supported Configurations。](mbam-25-supported-configurations.md)

**注意**  
建议仅在测试环境中使用单服务器体系结构。

 

## <a name="recommended-number-of-servers-and-supported-number-of-clients"></a>建议的服务器数量和支持的客户端数量


在生产环境中建议的服务器数量和支持的客户端数量如下所示：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">生产环境中建议的体系结构</th>
<th align="left">详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>服务器和其他计算机的数量</p></td>
<td align="left"><p>两台服务器</p>
<p>一个工作站</p></td>
</tr>
<tr class="even">
<td align="left"><p>支持的客户端计算机数量</p></td>
<td align="left"><p>500,000</p></td>
</tr>
</tbody>
</table>

 

## <a name="recommended-mbam-high-level-architecture-with-the-stand-alone-topology"></a>建议采用独立拓扑的 MBAM 高级体系结构


下图和表介绍了针对具有独立拓扑的 MBAM 的建议高级双服务器体系结构。 MBAM 多林部署需要单向或双向信任。 单向信任要求服务器域信任客户端域。

![mbam2。](images/mbam2-5-2servers.png)

要在此服务器上配置的服务器功能 说明数据库服务器

合规性和审核数据库

此功能在运行 Windows Server 且受支持SQL Server服务器上配置。

合规性**和审核数据库**存储合规性数据，这些数据主要用于托管SQL Server Reporting Services报告。

恢复数据库

此功能在运行 Windows Server 且受支持SQL Server服务器上配置。

恢复 **数据库** 存储从 MBAM 客户端计算机收集的恢复数据。

报告

此功能在运行 Windows Server 且受支持SQL Server服务器上配置。

报告 **提供有关** 企业中客户端计算机的恢复审核和合规性状态数据。 可以从管理和监控网站访问报告，也可以直接从网站SQL Server Reporting Services。

管理和监控服务器

管理和监控网站

此功能在运行 Windows Server 的计算机上配置。

管理和 **监控网站** 用于：

-   帮助最终用户在被锁定时重新获得对计算机的访问权限。 (网站的此区域通常称为 Help Desk.) 

-   查看显示客户端计算机的合规性状态和恢复活动的报告。

Self-Service门户

此功能在运行 Windows Server 的计算机上配置。

自助式 **门户** 是一个网站，使客户端计算机上的最终用户能够在丢失或忘记 BitLocker 密码时独立登录到网站，获取恢复密钥。

监视此网站的 Web 服务

此功能在运行 Windows Server 的计算机上配置。

**MBAM**客户端和网站使用监视 Web 服务与数据库通信。

**重要提示**  
Microsoft BitLocker 管理和监视 (MBAM) 2.5 SP1 中不再提供监控 Web 服务，因为 MBAM 网站直接与恢复数据库通信。

 

管理工作站

MBAM 组策略模板

-   MBAM 组策略模板是定义 MBAM 实现设置的组策略设置，可让你管理 BitLocker 驱动器加密。

-   在运行 MBAM 之前，必须下载如何获取 MDOP 组策略[ (.admx) ](https://go.microsoft.com/fwlink/p/?LinkId=393941)模板中的组策略模板，并复制到运行受支持的 Windows Server 或 Windows 操作系统的服务器或工作站。

-   工作站不需要是专用计算机。

MBAM 客户端和 Configuration Manager 客户端计算机

MBAM 客户端软件

MBAM 客户端：

-   使用组策略对象在企业中的客户端计算机上强制执行 BitLocker 驱动器加密。

-   收集三种数据驱动器类型的 Bitlocker 恢复密钥：操作系统驱动器、固定数据驱动器和可移动 (USB) 数据驱动器。

-   收集有关客户端计算机的恢复信息和计算机信息。



## <a name="related-topics"></a>相关主题


[MBAM 2.5 入门](getting-started-with-mbam-25.md)

[采用 Configuration Manager 集成拓扑的 MBAM 2.5 的高级别体系结构](high-level-architecture-of-mbam-25-with-configuration-manager-integration-topology.md)

[图示 MBAM 2.5 部署的功能](illustrated-features-of-an-mbam-25-deployment.md)

 

## <a name="got-a-suggestion-for-mbam"></a>有关于 MBAM 的建议吗？
- 在此处添加建议或对建议 [投票](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)。 
- 对于 MBAM 问题，请使用 [MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。 





