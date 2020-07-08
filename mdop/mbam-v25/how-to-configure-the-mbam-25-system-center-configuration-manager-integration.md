---
title: 如何配置 MBAM 2.5 System Center Configuration Manager 集成
description: 如何配置 MBAM 2.5 System Center Configuration Manager 集成
author: dansimp
ms.assetid: 2b8a4c13-1dad-41e8-89ac-6889c5f7e051
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7c6fb0a0b06399baf1dc6493a40d17e76a51741f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798047"
---
# 如何配置 MBAM 2.5 System Center Configuration Manager 集成


本主题介绍如何配置 Microsoft BitLocker 管理和监视（MBAM）以使用 System Center Configuration Manager 集成拓扑，该拓扑将 MBAM 与 Configuration Manager 集成。

这些说明介绍了如何使用以下内容配置 Configuration Manager 集成：

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
<td align="left"><p><a href="high-level-architecture-of-mbam-25-with-configuration-manager-integration-topology.md" data-raw-source="[High-Level Architecture of MBAM 2.5 with Configuration Manager Integration Topology](high-level-architecture-of-mbam-25-with-configuration-manager-integration-topology.md)">采用 Configuration Manager 集成拓扑的 MBAM 2.5 的高级别体系结构</a></p></td>
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
<td align="left"><p>在将在其中配置 MBAM 服务器功能的每台服务器上安装 MBAM 服务器软件。</p>
<div class="alert">
<strong>注意</strong><br/><p>对于此拓扑，你必须在要安装 MBAM Server 软件的计算机上安装 Configuration Manager 控制台。</p>
</div>
<div>

</div></td>
<td align="left"><p><a href="installing-the-mbam-25-server-software.md" data-raw-source="[Installing the MBAM 2.5 Server Software](installing-the-mbam-25-server-software.md)">安装 MBAM 2.5 服务器软件</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>查看 Windows PowerShell 先决条件（仅适用于使用 Windows PowerShell cmdlet 配置 MBAM 的情况）。</p></td>
<td align="left"><p><a href="configuring-mbam-25-server-features-by-using-windows-powershell.md" data-raw-source="[Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md)">使用 Windows PowerShell 配置 MBAM 2.5 服务器功能</a></p></td>
</tr>
</tbody>
</table>



**使用 Windows PowerShell 配置 Configuration Manager 集成**

1.  在开始配置之前，请参阅[使用 Windows Powershell 配置 MBAM 2.5 服务器功能](configuring-mbam-25-server-features-by-using-windows-powershell.md)，以查看使用 windows powershell 的先决条件。

2.  使用**Enable-MbamCMIntegration** Windows PowerShell Cmdlet 配置报告。 若要获取有关此 cmdlet 的信息，请键入**Get-help Enable-MbamCMIntegration**。

**使用向导配置 System Center Configuration Manager 集成**

1.  在要配置 System Center Configuration Manager 集成功能的服务器上，启动 "MBAM Server 配置向导"。 可以从 "**开始**" 菜单中选择 " **MBAM 服务器配置**" 以打开该向导。

2.  单击 "**添加新功能**"，选择 " **System Center Configuration Manager 集成**"，然后单击 "**下一步**"。

    向导检查是否满足 Configuration Manager 集成的所有先决条件。

3.  如果先决条件检查成功，请单击 "**下一步**" 以继续。 否则，请解决任何缺少的先决条件，然后**再次单击 "检查必备项**"。

4.  使用以下说明在向导中输入字段值：

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
    <td align="left"><p><strong>SQL Server Reporting Services 服务器</strong></p></td>
    <td align="left"><p>具有报告服务点角色的服务器的完全限定的域名（FQDN）。 这是要将 MBAM Configuration Manager 报表部署到的服务器。</p>
    <p>如果不指定服务器，配置管理器报告将部署到本地服务器。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><strong>SQL Server Reporting Services 实例</strong></p></td>
    <td align="left"><p>部署配置管理器报告的 SQL Server Reporting Services （SSRS）实例的名称。</p>
    <p>如果不指定实例，配置管理器报告将部署到默认的 SSRS 实例名称。 如果服务器安装了 System Center 2012 配置管理器，则输入的值将被忽略。</p></td>
    </tr>
    </tbody>
    </table>



5.  在 "**摘要**" 页面上，查看将添加的功能。

    **注意**  
    若要创建刚刚创建的条目的 Windows PowerShell 脚本，请单击 "**导出 PowerShell 脚本**" 并保存脚本。



6.  单击 "**添加**" 将 Configuration Manager 集成功能添加到服务器，然后单击 "**关闭**"。



## 相关主题


[配置 MBAM 2.5 服务器功能](configuring-the-mbam-25-server-features.md)

[验证 MBAM 2.5 服务器功能配置](validating-the-mbam-25-server-feature-configuration.md)


## 已获得 MBAM 的建议？
- 在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。 
- 对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。






