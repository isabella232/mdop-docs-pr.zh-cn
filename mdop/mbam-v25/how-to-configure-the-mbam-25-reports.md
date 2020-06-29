---
title: 如何配置 MBAM 2.5 报告
description: 如何配置 MBAM 2.5 报告
author: dansimp
ms.assetid: ec462879-0253-4d9c-83c7-a9bcad479725
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6b372bd6bc38a3729aef43354ecf19b2619b7856
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804004"
---
# 如何配置 MBAM 2.5 报告


本主题介绍了如何使用以下内容配置 Microsoft BitLocker 管理和监视（MBAM）2.5 报告功能：

-   Windows PowerShell cmdlet

-   MBAM Server 配置向导

说明基于[MBAM 2.5 的高级别体系结构](high-level-architecture-for-mbam-25.md)中的推荐体系结构。

**开始配置之前：**

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
<li><p><a href="mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md" data-raw-source="[MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology](mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md)">仅适用于 Configuration Manager 集成拓扑 </a> （如果适用）的 MBAM 2.5 服务器必备条件</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>在计划配置 MBAM 服务器功能的每台服务器上安装 MBAM Server 软件。</p></td>
<td align="left"><p><a href="installing-the-mbam-25-server-software.md" data-raw-source="[Installing the MBAM 2.5 Server Software](installing-the-mbam-25-server-software.md)">安装 MBAM 2.5 服务器软件</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>如果计划使用 Windows PowerShell cmdlet 配置 MBAM Server 功能，请查看使用 Windows PowerShell 的先决条件。</p></td>
<td align="left"><p><a href="configuring-mbam-25-server-features-by-using-windows-powershell.md" data-raw-source="[Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md)">使用 Windows PowerShell 配置 MBAM 2.5 服务器功能</a></p></td>
</tr>
</tbody>
</table>



**使用 Windows PowerShell 配置报表**

1.  在开始配置之前，请参阅[使用 Windows Powershell 配置 MBAM 2.5 服务器功能](configuring-mbam-25-server-features-by-using-windows-powershell.md)，以查看使用 windows powershell 的先决条件。

2.  使用**Enable-MbamReport** Windows PowerShell Cmdlet 配置报告。 若要获取有关此 Windows PowerShell cmdlet 的信息，请键入**Get-help Enable-MbamReport**。

**使用向导配置报表**

1. 在要配置报告的服务器上，启动 " **MBAM 服务器配置**向导"。 可以从 "**开始**" 菜单中选择 " **MBAM 服务器配置**" 以打开该向导。

2. 单击 "**添加新功能**"，选择 "**报表**"，然后单击 "**下一步**"。 向导将检查是否满足报表的所有先决条件。

3. 单击**下一步**以继续。

4. 使用以下说明，在向导中输入字段值：

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left">字段</th>
   <th align="left">描述</th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong>SQL Server Reporting Services 实例</strong></p></td>
   <td align="left"><p>将配置报告的 SQL Server Reporting Services 的实例。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong>报告角色域组</strong></p></td>
   <td align="left"><p>成员具有在管理和监视服务器上访问报表的权限的域用户组的名称。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong>SQL Server 名称</strong></p></td>
   <td align="left"><p>配置合规性和审核数据库的服务器的名称。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong>SQL Server 数据库实例</strong></p></td>
   <td align="left"><p>在 <em> </em> 其中配置合规性和审核数据库的 SQL Server 实例的名称（例如，MSSQLSERVER）。</p>
   <div class="alert">
   <strong>注意</strong><br/><p>必须在报表计算机上添加一个例外，才能在报告服务器的端口上启用入站流量（默认端口为80）。</p>
   </div>
   <div>

   </div></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong>数据库名称</strong></p></td>
   <td align="left"><p>合规性和审核数据库的名称。 默认情况下，数据库名称是 <strong> MBAM 合规性状态 </strong> ，但你可以在配置合规性和审核数据库时更改名称。</p>
   <div class="alert">
   <strong>注意</strong><br/><p>如果要从 MBAM 的早期版本升级，则必须使用与以前部署中使用的名称相同的数据库名称。</p>
   </div>
   <div>

   </div></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong>合规性和审核数据库域帐户</strong></p></td>
   <td align="left"><p>用于访问合规性和审核数据库的域用户帐户和密码。</p>
   <p>如果您在 <strong> "配置数据库" 页面上的 "只读访问域用户" 或 "组" 字段中输入的值 </strong> <strong> </strong> 是用户，则必须在此字段中输入相同的值。</p>
   <p>如果您在 <strong> "配置数据库" 页面上的 "只读访问域用户" 或 "组" 字段中输入的值 </strong> <strong> </strong> 是组，则在此字段中输入的值必须是该组的成员。</p>
   <p>将此帐户的密码配置为永不过期。 用户帐户应该能够访问 MBAM Reports Users 组中可用的所有数据。</p></td>
   </tr>
   </tbody>
   </table>



5. 完成输入后，单击 "**下一步**"。

   该向导将检查是否已满足 "报表" 功能的所有先决条件。

6. 单击**下一步**以继续。

7. 在 "**摘要**" 页面上，查看将添加的功能。

   **注意**  
   若要创建刚刚创建的条目的 Windows PowerShell 脚本，请单击 "**导出 PowerShell 脚本**"，然后保存脚本。



8. 单击 "**添加**" 以在服务器上添加报表，然后单击 "**关闭**"。



## 相关主题


[服务器事件日志](server-event-logs.md)

[配置 MBAM 2.5 服务器功能](configuring-the-mbam-25-server-features.md)

[如何配置 MBAM 2.5 Web 应用程序](how-to-configure-the-mbam-25-web-applications.md)

[验证 MBAM 2.5 服务器功能配置](validating-the-mbam-25-server-feature-configuration.md)


## 已获得 MBAM 的建议？
- 在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。 
- 对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。






