---
title: 配置 MBAM 2.5 服务器功能
description: 配置 MBAM 2.5 服务器功能
author: dansimp
ms.assetid: 894d1080-5f13-48f7-8fde-82f8d440a4ed
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e6ba2fc49086acf698f61b9997505c8fa884c0eb
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803292"
---
# 配置 MBAM 2.5 服务器功能


在[安装 MBAM 2.5 服务器软件](installing-the-mbam-25-server-software.md)后，请使用此信息作为配置 Microsoft BitLocker 管理和监视（MBAM）2.5 服务器功能的起始位置。 可使用两种方法配置 MBAM：

-   MBAM Server 配置向导

-   Windows PowerShell cmdlet

## 在开始配置 MBAM 服务器功能之前


在开始配置 MBAM 服务器功能之前，请查看并完成以下步骤：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">步骤</th>
<th align="left">获取说明的位置</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>查看建议的 MBAM 体系结构。</p></td>
<td align="left"><p><a href="high-level-architecture-for-mbam-25.md" data-raw-source="[High-Level Architecture for MBAM 2.5](high-level-architecture-for-mbam-25.md)">MBAM 2.5 的高级别体系结构</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>查看 MBAM 支持的配置。</p></td>
<td align="left"><p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)">MBAM 2.5 支持的配置</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>在每台服务器上完成所需的先决条件。</p></td>
<td align="left"><ul>
<li><p><a href="mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md" data-raw-source="[MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)">独立和 Configuration Manager 集成拓扑的 MBAM 2.5 服务器先决条件</a></p></li>
<li><p><a href="mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md" data-raw-source="[MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology](mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md)">仅适用于 Configuration Manager 集成拓扑的 MBAM 2.5 服务器先决条件</a></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>在将在其中配置 MBAM 服务器功能的每台服务器上安装 MBAM 服务器软件。</p></td>
<td align="left"><p><a href="installing-the-mbam-25-server-software.md" data-raw-source="[Installing the MBAM 2.5 Server Software](installing-the-mbam-25-server-software.md)">安装 MBAM 2.5 服务器软件</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>查看使用 Windows PowerShell 配置 MBAM 服务器功能的先决条件（如果你使用此方法配置 MBAM Server 功能）。</p></td>
<td align="left"><p><a href="configuring-mbam-25-server-features-by-using-windows-powershell.md" data-raw-source="[Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md)">使用 Windows PowerShell 配置 MBAM 2.5 服务器功能</a></p></td>
</tr>
</tbody>
</table>

 

## 配置 MBAM Server 功能的步骤


下表中的每一行描述了您将在单独的服务器上配置的功能，这些功能将根据[MBAM 2.5 的推荐高级别体系结构](high-level-architecture-for-mbam-25.md)进行配置。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">要安装的功能</th>
<th align="left">获取说明的位置</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>配置数据库。</p></td>
<td align="left"><p><a href="how-to-configure-the-mbam-25-databases.md" data-raw-source="[How to Configure the MBAM 2.5 Databases](how-to-configure-the-mbam-25-databases.md)">如何配置 MBAM 2.5 数据库</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>配置报告。</p></td>
<td align="left"><p><a href="how-to-configure-the-mbam-25-reports.md" data-raw-source="[How to Configure the MBAM 2.5 Reports](how-to-configure-the-mbam-25-reports.md)">如何配置 MBAM 2.5 报告</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>配置 web 应用程序。</p></td>
<td align="left"><p><a href="how-to-configure-the-mbam-25-web-applications.md" data-raw-source="[How to Configure the MBAM 2.5 Web Applications](how-to-configure-the-mbam-25-web-applications.md)">如何配置 MBAM 2.5 Web 应用程序</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>配置 System Center Configuration Manager 集成（如果适用）。</p></td>
<td align="left"><p><a href="how-to-configure-the-mbam-25-system-center-configuration-manager-integration.md" data-raw-source="[How to Configure the MBAM 2.5 System Center Configuration Manager Integration](how-to-configure-the-mbam-25-system-center-configuration-manager-integration.md)">如何配置 MBAM 2.5 System Center Configuration Manager 集成</a></p></td>
</tr>
</tbody>
</table>

 

有关 MBAM 服务器功能配置的事件的列表，请参阅[服务器事件日志](server-event-logs.md)。



## 相关主题


配置 MBAM 2.5 服务器功能
 

 
## 已获得 MBAM 的建议？
- 在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。 
- 对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。




