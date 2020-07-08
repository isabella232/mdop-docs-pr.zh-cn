---
title: 计划使用 Configuration Manager 部署 MBAM
description: 计划使用 Configuration Manager 部署 MBAM
author: dansimp
ms.assetid: fb768306-48c2-40b4-ac4e-c279db987391
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: e8588ce03c86a8a5138d591327e5f95503dce5ad
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803806"
---
# 计划使用 Configuration Manager 部署 MBAM


若要使用 Configuration Manager 拓扑部署 MBAM，建议使用支持200000客户端的三服务器体系结构。 使用单独的服务器运行配置管理器，并在两台服务器上安装基本的管理和监视功能，如入门中的体系结构图所示[-将 MBAM 与 Configuration Manager 配合使用](getting-started---using-mbam-with-configuration-manager.md)。

**重要提示**  
将 MBAM 的集成拓扑安装到 Configuration Manager 2007 时，不支持 Windows To Go。



## 通过 Configuration Manager 安装 MBAM 的部署先决条件


在使用 Configuration Manager 安装 MBAM 之前，请确保满足以下先决条件：

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
<td align="left"><p>确保 Configuration Manager 服务器是 Configuration Manager 系统中的主站点。</p></td>
<td align="left"><p>不适用</p></td>
</tr>
<tr class="even">
<td align="left"><p>在 Configuration Manager 服务器上启用硬件清单客户端代理。</p></td>
<td align="left"><p>有关 Configuration Manager 2007 的详细说明，请参阅 <a href="https://go.microsoft.com/fwlink/?LinkId=301656" data-raw-source="[How to Configure Hardware Inventory for a Site](https://go.microsoft.com/fwlink/?LinkId=301656)"> 如何为网站配置硬件清单 </a> 。</p>
<p>对于 System Center 2012 配置管理器，请参阅 <a href="https://go.microsoft.com/fwlink/?LinkId=301685" data-raw-source="[How to Configure Hardware Inventory in Configuration Manager](https://go.microsoft.com/fwlink/?LinkId=301685)"> 如何在 Configuration manager 中配置硬件清单 </a> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>根据你使用的 Configuration Manager 版本启用所需的配置管理（DCM）代理或合规性设置。</p></td>
<td align="left"><p>对于 Configuration Manager 2007，请启用 "查看 <a href="https://go.microsoft.com/fwlink/?LinkId=301686" data-raw-source="[Desired Configuration Management Client Agent Properties](https://go.microsoft.com/fwlink/?LinkId=301686)"> 所需的配置管理客户端代理" 属性 </a> 。</p>
<p>对于 System Center 2012 配置管理器，请参阅配置 <a href="https://go.microsoft.com/fwlink/?LinkId=301687" data-raw-source="[Configuring Compliance Settings in Configuration Manager](https://go.microsoft.com/fwlink/?LinkId=301687)"> 管理器中的配置合规性设置 </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>在配置管理器中定义 reporting services 点。 对于 SQL Reporting Services 是必需的。</p></td>
<td align="left"><p>有关 Configuration Manager 2007 的详细说明，请参阅 <a href="https://go.microsoft.com/fwlink/?LinkId=301688" data-raw-source="[How to Create a Reporting Services Point for SQL Reporting Services](https://go.microsoft.com/fwlink/?LinkId=301688)"> 如何为 SQL Reporting Services 创建 Reporting Services 点 </a> 。</p>
<p>对于 System Center 2012 配置管理器，请参阅 <a href="https://go.microsoft.com/fwlink/?LinkId=301689" data-raw-source="[Prerequisites for Reporting in Configuration Manager](https://go.microsoft.com/fwlink/?LinkId=301689)"> 配置管理器中的报告先决条件 </a> 。</p></td>
</tr>
</tbody>
</table>



## <a href="" id="---------configuration-manager-supported-versions"></a> Configuration Manager 支持的版本


MBAM 支持以下版本的 Configuration Manager：

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">支持的版本</th>
<th align="left">Service pack</th>
<th align="left">系统体系结构</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Microsoft System Center Configuration Manager 2007 R2</p></td>
<td align="left"><p>SP1 或更高版本</p></td>
<td align="left"><p>64 位</p>
<div class="alert">
<strong>注意</strong><br/><p>虽然 Configuration Manager 2007 是32位，但必须在64位操作系统上安装它和 SQL Server 才能匹配64位 MBAM 软件。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft System Center 2012 Configuration Manager</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>64 位</p></td>
</tr>
</tbody>
</table>



有关 Configuration Manager 服务器支持的配置的列表，请参阅适用于你正在使用的 Configuration Manager 版本的相应网页。 MBAM 配置管理器服务器没有其他系统要求。

## <a href="" id="---------mbam-and-sql-server-system-requirements"></a> MBAM 和 SQL Server 系统要求


MBAM 服务器和配置管理器拓扑的 SQL Server 支持的配置和系统要求与独立拓扑的支持配置和系统要求相同。 有关独立系统要求，请参阅[MBAM 2.0 支持的配置](mbam-20-supported-configurations-mbam-2.md)。 有关 Configuration Manager 拓扑的 MBAM 服务器和 SQL Server 处理器、RAM 和磁盘空间要求，请参阅以下部分。

## MBAM 服务器处理器、RAM 和磁盘空间要求 MBAM


下表列出了使用 Configuration Manager 集成拓扑时 MBAM 服务器的服务器处理器、RAM 和磁盘空间要求。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">硬件组件</th>
<th align="left">最低要求</th>
<th align="left">建议的要求</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>处理者</p></td>
<td align="left"><p>2.33 GHz</p></td>
<td align="left"><p>2.33 GHz 或更高版本</p></td>
</tr>
<tr class="even">
<td align="left"><p>RAM</p></td>
<td align="left"><p>4 GB</p></td>
<td align="left"><p>8 GB</p></td>
</tr>
<tr class="odd">
<td align="left"><p>可用磁盘空间</p></td>
<td align="left"><p>1 GB</p></td>
<td align="left"><p>2 GB</p></td>
</tr>
</tbody>
</table>



## SQL Server 处理器、RAM 和磁盘空间要求


下表列出了使用 Configuration Manager 集成拓扑时 SQL Server 计算机的服务器处理器、RAM 和磁盘空间要求。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">硬件组件</th>
<th align="left">最低要求</th>
<th align="left">建议的要求</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>处理者</p></td>
<td align="left"><p>2.33 GHz</p></td>
<td align="left"><p>2.33 GHz 或更高版本</p></td>
</tr>
<tr class="even">
<td align="left"><p>RAM</p></td>
<td align="left"><p>4 GB</p></td>
<td align="left"><p>8 GB</p></td>
</tr>
<tr class="odd">
<td align="left"><p>可用磁盘空间</p></td>
<td align="left"><p>5 GB</p></td>
<td align="left"><p>5 GB 或以上</p></td>
</tr>
</tbody>
</table>



## 安装 MBAM 服务器所需的权限


若要使用 Configuration Manager 安装 MBAM，你必须在配置管理器中拥有具有下表中列出的最低权限的安全角色的管理用户。 该表还显示了您必须拥有的权限，但不限于基本的计算机管理员权限，以便安装 MBAM 服务器。

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
<td align="left"><p>SQL 实例登录服务器角色：-dbcreator-processadmin</p></td>
<td align="left"><p>- 恢复数据库-审核数据库</p></td>
</tr>
<tr class="even">
<td align="left"><p>SQL Server Reporting Services 实例权限：-创建文件夹-发布报表</p></td>
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



## 配置管理器拓扑的 MBAM 功能的部署顺序


在 Configuration Manager 服务器上部署 MBAM 时，必须按照以下顺序完成部署任务：

1.  在 Configuration Manager 服务器上编辑配置 mof 文件。

2.  创建或编辑 sms \ _def. mof 文件配置管理器服务器。

3.  在 Configuration Manager 服务器上安装 MBAM。

4.  在数据库服务器上安装恢复数据库和审核数据库。

5.  在 "管理和监视" 服务器上安装 MBAM 功能。

## 有关通过 Configuration Manager 安装 MBAM 的规划清单


此清单列出了在规划使用 Configuration Manager 进行 Microsoft BitLocker 管理和监视部署时需要考虑的推荐步骤和高级别的项目列表。 建议将此清单复制到电子表格程序中，然后对其进行自定义以供使用。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left">任务</th>
<th align="left">引用</th>
<th align="left">注释</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>查看入门信息，介绍 Configuration Manager 如何与 MBAM 配合工作，并显示推荐的高级别体系结构。</p></td>
<td align="left"><p><a href="getting-started---using-mbam-with-configuration-manager.md" data-raw-source="[Getting Started - Using MBAM with Configuration Manager](getting-started---using-mbam-with-configuration-manager.md)">入门 - 结合使用 MBAM 和 Configuration Manager</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>查看规划信息，其中介绍了每个功能的部署先决条件、支持的配置、所需权限和部署顺序。</p></td>
<td align="left"><p>计划使用 Configuration Manager 部署 MBAM</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>规划和配置 MBAM 组策略要求。</p></td>
<td align="left"><p><a href="planning-for-mbam-20-group-policy-requirements-mbam-2.md" data-raw-source="[Planning for MBAM 2.0 Group Policy Requirements](planning-for-mbam-20-group-policy-requirements-mbam-2.md)">计划 MBAM 2.0 组策略要求</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>规划和创建必要的 Active Directory 域服务安全组，并针对 MBAM 本地安全组成员身份要求进行规划。</p></td>
<td align="left"><p><a href="planning-for-mbam-20-administrator-roles-mbam-2.md" data-raw-source="[Planning for MBAM 2.0 Administrator Roles](planning-for-mbam-20-administrator-roles-mbam-2.md)">计划 MBAM 2.0 管理员角色</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>规划部署 MBAM 客户端部署。</p></td>
<td align="left"><p><a href="planning-for-mbam-20-client-deployment-mbam-2.md" data-raw-source="[Planning for MBAM 2.0 Client Deployment](planning-for-mbam-20-client-deployment-mbam-2.md)">计划 MBAM 2.0 客户端部署</a></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>



## 相关主题


[结合使用 MBAM 和 Configuration Manager](using-mbam-with-configuration-manager.md)









