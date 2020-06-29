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
ms.openlocfilehash: 75e878e24b4675f2f2f574791d0f06ecadd0196d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803992"
---
# 采用独立拓扑的 MBAM 2.5 的高级别体系结构


本主题介绍使用配置管理器独立拓扑部署 Microsoft BitLocker 管理和监视（MBAM）的推荐体系结构。 在此拓扑中，MBAM 作为独立的产品进行部署。 也可以通过 Configuration Manager 集成拓扑（它将 MBAM 与 Configuration Manager 集成）部署 MBAM。 有关详细信息，请参阅[具有 Configuration Manager 集成拓扑的 MBAM 2.5 的高级别体系结构](high-level-architecture-of-mbam-25-with-configuration-manager-integration-topology.md)。

有关本主题中所述软件的受支持版本的列表，请参阅[MBAM 2.5 支持的配置](mbam-25-supported-configurations.md)。

**注意** 我们建议你仅在测试环境中使用单服务器体系结构。

 

## 推荐的服务器数和受支持的客户端数


生产环境中推荐的服务器数和受支持的客户端数量如下所示：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">生产环境中的推荐体系结构</th>
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
<td align="left"><p>支持的客户端计算机数</p></td>
<td align="left"><p>500,000</p></td>
</tr>
</tbody>
</table>

 

## 使用独立拓扑的推荐 MBAM 高级别体系结构


下图和表介绍了推荐的高级别双服务器体系结构，MBAM 使用独立拓扑。 MBAM 多林部署需要单向或双向信任。 单向信任要求服务器域信任客户端域。

![mbam2](images/mbam2-5-2servers.png)

要在此服务器上配置的服务器功能说明数据库服务器

合规性和审核数据库

此功能在运行 Windows Server 和支持的 SQL Server 实例的服务器上配置。

**合规性和审核数据库**存储合规性数据，这些数据主要用于 SQL Server Reporting Services 主机的报表。

恢复数据库

此功能在运行 Windows Server 和支持的 SQL Server 实例的服务器上配置。

**恢复数据库**存储从 MBAM 客户端计算机收集的恢复数据。

报告

此功能在运行 Windows Server 和支持的 SQL Server 实例的服务器上配置。

**报告**提供有关您的企业中的客户端计算机的恢复审核和合规性状态数据。 你可以从 "管理" 和 "监视" 网站或直接从 SQL Server Reporting Services 访问报表。

管理和监视服务器

管理和监视网站

此功能在运行 Windows Server 的计算机上配置。

**管理和监视网站**用于：

-   当用户被锁定时，帮助最终用户重新获得对其计算机的访问权限。（此网站区域通常称为 "帮助桌面"。）

-   查看显示客户端计算机合规性状态和恢复活动的报告。

自助服务门户

此功能在运行 Windows Server 的计算机上配置。

**自助服务门户**是一种网站，使客户端计算机上的最终用户能够独立登录到网站以获取恢复密钥（如果他们丢失或忘记其 BitLocker 密码）。

监视此网站的 web 服务

此功能在运行 Windows Server 的计算机上配置。

**监视 web 服务**由 MBAM 客户端和网站用于与数据库通信。

**重要提示** 由于 MBAM 网站直接与恢复数据库通信，因此在 Microsoft BitLocker 管理和监视（MBAM） 2.5 SP1 中不再提供监视 Web 服务。

 

管理工作站

MBAM 组策略模板

-   MBAM 组策略模板是定义 MBAM 的实现设置的组策略设置，使你能够管理 BitLocker 驱动器加密。

-   在运行 MBAM 之前，你必须从[如何获取 MDOP 组策略（admx）模板](https://go.microsoft.com/fwlink/p/?LinkId=393941)中下载组策略模板，并将其复制到运行受支持的 Windows Server 或 Windows 操作系统的服务器或工作站。

-   工作站不必是专用计算机。

MBAM 客户端和 Configuration Manager 客户端计算机

MBAM 客户端软件

MBAM 客户端：

-   使用组策略对象对企业中的客户端计算机强制执行 BitLocker 驱动器加密。

-   收集三种数据驱动器类型的 Bitlocker 恢复密钥：操作系统驱动器、固定数据驱动器和可移动（USB）数据驱动器。

-   收集有关客户端计算机的恢复信息和计算机信息。



## 相关主题


[MBAM 2.5 入门](getting-started-with-mbam-25.md)

[采用 Configuration Manager 集成拓扑的 MBAM 2.5 的高级别体系结构](high-level-architecture-of-mbam-25-with-configuration-manager-integration-topology.md)

[图示 MBAM 2.5 部署的功能](illustrated-features-of-an-mbam-25-deployment.md)

 

## 已获得 MBAM 的建议？
- 在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。 
- 对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。 





