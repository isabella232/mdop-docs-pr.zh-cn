---
title: 如何配置 MBAM 2.5 数据库
description: 如何配置 MBAM 2.5 数据库
author: dansimp
ms.assetid: 66e1c81b-f785-4398-9175-bb5f112c2a35
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c11cb58d8fd9266bd0322e4cf9aa96256b7fbb6a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804005"
---
# 如何配置 MBAM 2.5 数据库


本主题介绍了如何使用以下内容配置 Microsoft BitLocker 管理和监视（MBAM）2.5 合规性和审核数据库和恢复数据库：

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
<td align="left"><p>在计划配置 MBAM 服务器功能的每台服务器上安装 MBAM Server 软件。</p>
<div class="alert">
<strong>注意</strong><br/><p>你可以使用 Windows PowerShell 或导出的数据层应用程序（DAC）程序包将数据库安装到远程 SQL Server 计算机。 有关 DAC 包的详细信息，请参阅 <a href="https://technet.microsoft.com/library/ee210546.aspx" data-raw-source="[Data-tier Applications](https://technet.microsoft.com/library/ee210546.aspx)"> 数据层应用程序 </a> 。</p>
</div>
<div>

</div></td>
<td align="left"><p><a href="installing-the-mbam-25-server-software.md" data-raw-source="[Installing the MBAM 2.5 Server Software](installing-the-mbam-25-server-software.md)">安装 MBAM 2.5 服务器软件</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>如果计划使用 Windows PowerShell cmdlet 配置 MBAM Server 功能，请查看使用 Windows PowerShell 的先决条件。</p></td>
<td align="left"><p><a href="configuring-mbam-25-server-features-by-using-windows-powershell.md" data-raw-source="[Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md)">使用 Windows PowerShell 配置 MBAM 2.5 服务器功能</a></p></td>
</tr>
</tbody>
</table>



**使用 Windows PowerShell 配置数据库**

1.  在开始配置之前，请参阅[使用 Windows Powershell 配置 MBAM 2.5 服务器功能](configuring-mbam-25-server-features-by-using-windows-powershell.md)，以查看使用 windows powershell 的先决条件。

2.  使用**Enable-MbamDatabase** Windows PowerShell cmdlet 配置数据库。 若要获取有关此 Windows PowerShell cmdlet 的信息，请键入**Get-help Enable-MbamDatabase**。

**使用向导配置合规性和审核数据库**

1. 在要配置数据库的服务器上，启动 " **MBAM 服务器配置**向导"。 可以从 "**开始**" 菜单中选择 " **MBAM 服务器配置**" 以打开该向导。

2. 单击 "**添加新功能**"，选择 "**合规性和审核数据库**和**恢复数据库**"，然后单击 "**下一步**"。 向导将检查数据库的所有先决条件是否已满足。

3. 如果先决条件检查成功，请单击 "**下一步**" 以继续。 否则，请解决任何缺少的先决条件，然后**再次单击 "检查必备项**"。

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
   <td align="left"><p><strong>SQL Server 名称</strong></p></td>
   <td align="left"><p>在其中配置合规性和审核数据库的服务器的名称。</p>
   <div class="alert">
   <strong>注意</strong><br/><p>必须在合规性和审核数据库计算机上添加异常，才能在 Microsoft SQL Server 端口上启用入站流量。 默认端口号为1433。</p>
   </div>
   <div>

   </div></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong>SQL Server 数据库实例</strong></p></td>
   <td align="left"><p>将存储合规性和审核数据的数据库实例的名称。 还必须指定数据库信息的存放位置。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong>数据库名称</strong></p></td>
   <td align="left"><p>将存储合规性数据的数据库的名称。</p>
   <div class="alert">
   <strong>注意</strong><br/><p>如果要从 MBAM 的早期版本升级，则必须使用与以前部署中使用的名称相同的数据库名称。</p>
   </div>
   <div>

   </div></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong>读/写访问域用户或组</strong></p></td>
   <td align="left"><p>对此数据库具有读/写权限的域用户或组，以使 web 应用程序能够访问此数据库中的数据和报表。</p>
   <p>如果在此字段中输入用户，它必须与 <strong> </strong> " <strong> 配置 web 应用程序" 页面上的 "web 服务应用程序池域帐户" 字段中的值相同 </strong> 。</p>
   <p>如果在此字段中输入组，则 " <strong> 配置 Web 应用程序" 页面上的 "Web 服务应用程序池域帐户" 字段中的值 </strong> <strong> </strong> 必须是您在此字段中输入的组的成员。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong>只读访问域用户或组</strong></p></td>
   <td align="left"><p>将对此数据库具有只读权限的用户或组的名称，以使报表能够访问此数据库中的合规性数据。</p>
   <p>如果在此字段中输入用户，则该用户必须与你在 <strong> </strong> "配置报告" 页面上的 "合规性和审核数据库域帐户" 字段中指定的用户相同 <strong> </strong> 。</p>
   <p>如果在此字段中输入一个组，则在 <strong> "配置报告" 页面上的 "合规性和审核数据库域帐户" 字段中指定的值 </strong> <strong> </strong> 必须是您在此字段中指定的组的成员。</p></td>
   </tr>
   </tbody>
   </table>



5. 转到下一节以配置恢复数据库。

**使用向导配置恢复数据库**

1. 使用以下说明，在向导中输入字段值：

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
   <td align="left"><p><strong>SQL Server 名称</strong></p></td>
   <td align="left"><p>要配置恢复数据库的服务器的名称。</p>
   <div class="alert">
   <strong>注意</strong><br/><p>必须在恢复数据库计算机上添加异常，才能在 Microsoft SQL Server 端口上启用入站流量。 默认端口号为1433。</p>
   </div>
   <div>

   </div></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong>SQL Server 数据库实例</strong></p></td>
   <td align="left"><p>将存储恢复数据的数据库实例的名称。 还必须指定数据库信息的存放位置。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong>数据库名称</strong></p></td>
   <td align="left"><p>将存储恢复数据的数据库的名称。</p>
   <div class="alert">
   <strong>注意</strong><br/><p>如果要从 MBAM 的早期版本升级，则必须使用与以前部署中使用的名称相同的数据库名称。</p>
   </div>
   <div>

   </div></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong>读/写访问域用户或组</strong></p></td>
   <td align="left"><p>对此数据库具有读/写权限的域用户或组，以使 web 应用程序能够访问此数据库中的数据和报表。</p>
   <p>如果在此字段中输入用户，它必须与 <strong> </strong> " <strong> 配置 web 应用程序" 页面上的 "web 服务应用程序池域帐户" 字段中的值相同 </strong> 。</p>
   <p>如果在此字段中输入组，则 " <strong> 配置 Web 应用程序" 页面上的 "Web 服务应用程序池域帐户" 字段中的值 </strong> <strong> </strong> 必须是您在此字段中输入的组的成员。</p></td>
   </tr>
   </tbody>
   </table>



2. 完成输入后，单击 "**下一步**"。

   向导将检查数据库的所有先决条件是否已满足。

3. 如果先决条件检查成功，请单击 "**下一步**" 以继续。 否则，请解决任何缺少的先决条件，然后再次单击 "**下一步**"。

4. 在 "**摘要**" 页面上，查看将添加的功能。

   **注意**  
   若要创建刚刚创建的条目的 Windows PowerShell 脚本，请单击 "**导出 PowerShell 脚本**"，然后保存脚本。



5. 单击 "**添加**" 以在服务器上添加 MBAM 数据库，然后单击 "**关闭**"。



## 相关主题


[服务器事件日志](server-event-logs.md)

[配置 MBAM 2.5 服务器功能](configuring-the-mbam-25-server-features.md)

[如何配置 MBAM 2.5 报告](how-to-configure-the-mbam-25-reports.md)

[如何配置 MBAM 2.5 Web 应用程序](how-to-configure-the-mbam-25-web-applications.md)

[验证 MBAM 2.5 服务器功能配置](validating-the-mbam-25-server-feature-configuration.md)



## 已获得 MBAM 的建议？
- 在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。
- 对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。 





