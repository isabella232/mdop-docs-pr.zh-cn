---
title: Configuration Manager 集成功能的先决条件
description: Configuration Manager 集成功能的先决条件
author: dansimp
ms.assetid: b318cbd3-b009-44b8-991b-f7364c1cae88
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: af7abd50f6218810dd6718f091512b48fee32652
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803683"
---
# Configuration Manager 集成功能的先决条件


如果使用 System Center Configuration Manager 集成拓扑部署 MBAM，我们建议使用三个服务器体系结构，如[使用 Configuration Manager 集成拓扑的 MBAM 2.5 的高级别体系结构](high-level-architecture-of-mbam-25-with-configuration-manager-integration-topology.md)中所述。 此体系结构可以支持500000客户端计算机。

**重要提示**  
使用 Configuration Manager 2007 时，Configuration Manager 集成拓扑安装不支持 Windows To Go。



## Configuration Manager 集成功能的常规先决条件


当使用配置管理器安装 MBAM 时，除独立拓扑的先决条件之外还需要以下其他先决条件。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">必备</th>
<th align="left">其他信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Configuration Manager 服务器是 Configuration Manager 系统中的主站点。</p></td>
<td align="left"><p>不适用</p></td>
</tr>
<tr class="even">
<td align="left"><p>硬件清单客户端代理位于 Configuration Manager 服务器上。</p></td>
<td align="left"><p>对于 System Center 2012 配置管理器，请参阅 <a href="https://go.microsoft.com/fwlink/?LinkId=301685" data-raw-source="[How to Configure Hardware Inventory in Configuration Manager](https://go.microsoft.com/fwlink/?LinkId=301685)"> 如何在 Configuration manager 中配置硬件清单 </a> 。</p>
<p>有关 Configuration Manager 2007 的详细说明，请参阅 <a href="https://go.microsoft.com/fwlink/?LinkId=301656" data-raw-source="[How to Configure Hardware Inventory for a Site](https://go.microsoft.com/fwlink/?LinkId=301656)"> 如何为网站配置硬件清单 </a> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>根据你使用的 Configuration Manager 版本，启用以下操作之一：</p>
<ul>
<li><p>合规性设置-（System Center 2012 Configuration Manager）</p></li>
<li><p>所需配置管理（DCM）客户端代理–（Configuration Manager 2007）</p></li>
</ul></td>
<td align="left"><p>对于 System Center 2012 配置管理器，请参阅配置 <a href="https://go.microsoft.com/fwlink/?LinkId=301687" data-raw-source="[Configuring Compliance Settings in Configuration Manager](https://go.microsoft.com/fwlink/?LinkId=301687)"> 管理器中的配置合规性设置 </a> 。</p>
<p>对于 Configuration Manager 2007，请参阅 <a href="https://go.microsoft.com/fwlink/?LinkId=301686" data-raw-source="[Desired Configuration Management Client Agent Properties](https://go.microsoft.com/fwlink/?LinkId=301686)"> 所需的配置管理客户端代理属性 </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>报告服务点在配置管理器中定义。 对于 SQL Server Reporting Services （SSRS）是必需的。</p></td>
<td align="left"><p>对于 System Center 2012 配置管理器，请参阅 <a href="https://go.microsoft.com/fwlink/?LinkId=301689" data-raw-source="[Prerequisites for Reporting in Configuration Manager](https://go.microsoft.com/fwlink/?LinkId=301689)"> 配置管理器中的报告先决条件 </a> 。</p>
<p>有关 Configuration Manager 2007 的详细说明，请参阅 <a href="https://go.microsoft.com/fwlink/?LinkId=301688" data-raw-source="[How to Create a Reporting Services Point for SQL Reporting Services](https://go.microsoft.com/fwlink/?LinkId=301688)"> 如何为 SQL Reporting Services 创建 Reporting Services 点 </a> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Configuration Manager 2007 需要 Microsoft .NET Framework 2。0</p></td>
<td align="left"><p>Configuration Manager 2007 中所需的配置管理（DCM）客户端代理需要 .NET Framework 2.0 来报告合规性。</p>
<div class="alert">
<strong>注意</strong><br/><p>安装 .NET Framework 3.5 会自动安装 .NET Framework 2.0。</p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



## 通过 Configuration Manager 安装 MBAM 所需的权限


若要使用 Configuration Manager 安装 MBAM，你必须在配置管理器中拥有具有下表中列出的最低权限的安全角色的管理用户。 该表还显示了您必须拥有的权限，但不限于基本的计算机管理员权限，以便安装 MBAM 服务器。

**下表中的权限适用于两个版本的 Configuration Manager。**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">权限</th>
<th align="left">MBAM Server 功能</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>SQL Server 实例登录服务器角色：-dbcreator-processadmin</p></td>
<td align="left"><p>- 恢复数据库-审核数据库</p></td>
</tr>
<tr class="even">
<td align="left"><p>SSRS 实例权限：-创建文件夹-发布报表</p></td>
<td align="left"><p>- System Center Configuration Manager 集成</p></td>
</tr>
</tbody>
</table>



**System Center 2012 Configuration Manager**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">权限</th>
<th align="left">Configuration Manager 服务器功能</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Configuration Manager 网站权限：-已读</p></td>
<td align="left"><p>System Center Configuration Manager 集成</p></td>
</tr>
<tr class="even">
<td align="left"><p>配置管理器收集权限：-Create-Delete-Read-Modify-部署配置项目</p></td>
<td align="left"><p>System Center Configuration Manager 集成</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Configuration Manager 配置项目权限：-Create-Delete-Read</p></td>
<td align="left"><p>System Center Configuration Manager 集成</p></td>
</tr>
</tbody>
</table>



**配置管理器 2007**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">权限</th>
<th align="left">Configuration Manager 服务器功能</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Configuration Manager 网站权限：-已读</p></td>
<td align="left"><p>System Center Configuration Manager 集成</p></td>
</tr>
<tr class="even">
<td align="left"><p>Configuration Manager 收集权限：-Create-Delete-ReadResource</p></td>
<td align="left"><p>System Center Configuration Manager 集成</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Configuration Manager 配置项目权限：-创建-删除-已读-分发</p></td>
<td align="left"><p>System Center Configuration Manager 集成</p></td>
</tr>
</tbody>
</table>



## 对 mof 文件所需的更改


若要使客户端计算机能够通过 MBAM Configuration Manager 报表报告 BitLocker 合规性详细信息，你必须编辑 System Center 2012 Configuration Manager 和 Microsoft System Center Configuration Manager 2007 的 Configuration 文件和 Sms \ _def mof 文件。 有关说明，请参阅[仅适用于 Configuration Manager 集成拓扑的 MBAM 2.5 Server 先决条件](mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md)。



## 相关主题


[独立和 Configuration Manager 集成拓扑的 MBAM 2.5 服务器先决条件](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)

[仅适用于 Configuration Manager 集成拓扑的 MBAM 2.5 服务器先决条件](mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md)



## 已获得 MBAM 的建议？
- 在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。 
- 对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。 





