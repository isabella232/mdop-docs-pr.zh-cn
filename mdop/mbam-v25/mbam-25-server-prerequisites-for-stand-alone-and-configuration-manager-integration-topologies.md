---
title: 独立和 Configuration Manager 集成拓扑的 MBAM 2.5 服务器先决条件
description: 独立和 Configuration Manager 集成拓扑的 MBAM 2.5 服务器先决条件
author: dansimp
ms.assetid: 76a6047a-5c6e-42ff-af09-a6f382a69537
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: c9af551b1d867f61912bbf3b759574a840b0645c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803880"
---
# 独立和 Configuration Manager 集成拓扑的 MBAM 2.5 服务器先决条件


在开始 Microsoft BitLocker 管理和监视（MBAM）安装之前，必须完成本主题中列出的先决条件。 这些先决条件适用于 MBAM 独立拓扑和 System Center Configuration Manager 集成拓扑。

如果你使用 System Center Configuration Manager 部署 MBAM，则必须完成其他先决条件，这些先决条件将在[仅适用于 Configuration Manager 集成拓扑的 MBAM 2.5 服务器必备项](mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md)中列出。

有关 MBAM 支持的硬件和操作系统的列表，请参阅[MBAM 2.5 支持的配置](mbam-25-supported-configurations.md)。

**重要提示**  
如果在没有 MBAM 的情况下使用 BitLocker，则必须解密驱动器，然后使用清除 TPM。 如果客户端电脑已加密，并且 TPM 所有者密码已创建，MBAM 不能取得 TPM 的所有权。



## 必需的 MBAM 角色和帐户


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">必备</th>
<th align="left">详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>在 Active Directory 域服务（AD DS）中创建的组</p></td>
<td align="left"><p>有关 <a href="planning-for-mbam-25-groups-and-accounts.md" data-raw-source="[Planning for MBAM 2.5 Groups and Accounts](planning-for-mbam-25-groups-and-accounts.md)"> 这些组和帐户的说明，请参阅规划 MBAM 2.5 组和帐户 </a> 。</p></td>
</tr>
</tbody>
</table>



## 恢复数据库的先决条件


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">必备</th>
<th align="left">详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>SQL Server 支持的版本</p></td>
<td align="left"><p>安装包含 SQL_Latin1_General_CP1_CI_AS 排序规则的 Microsoft SQL Server。</p>
<p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)"> </a> 有关支持的版本，请参阅 MBAM 2.5 支持的配置。</p></td>
</tr>
<tr class="even">
<td align="left"><p>所需的 SQL Server 权限</p></td>
<td align="left"><p>所需权限：</p>
<ul>
<li><p>SQL Server 实例登录服务器角色：</p>
<ul>
<li><p>dbcreator</p></li>
<li><p>processadmin</p></li>
</ul></li>
<li><p>SQL Server Reporting Services 实例权限：</p>
<ul>
<li><p>创建文件夹</p></li>
<li><p>发布报表</p></li>
</ul></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>可选-安装 SQL Server 中可用的透明数据加密（TDE）功能</p></td>
<td align="left"><p>TDE SQL Server 功能对数据和日志文件执行实时 i/o 加密和解密，这有助于你遵守适用于各种行业的法律、法规和指南。</p>
<div class="alert">
<strong>注意</strong><br/><p>TDE 执行数据库信息的实时解密。 这意味着，如果你在 SQL Server 数据库中查看恢复密钥信息，并且在具有数据库权限的帐户上登录，则恢复密钥信息将可见。 若要了解有关 TDE 的详细信息，请参阅 <a href="mbam-25-security-considerations.md" data-raw-source="[MBAM 2.5 Security Considerations](mbam-25-security-considerations.md)"> MBAM 2.5 安全注意事项 </a> 。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p>SQL Server 数据库引擎服务</p></td>
<td align="left"><p>必须在 MBAM 服务器安装期间安装并运行 SQL Server 数据库引擎服务。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows PowerShell 3.0 或更高版本</p></td>
<td align="left"><p>如果使用 Windows PowerShell 配置来自远程计算机的数据库，则无需在恢复数据库服务器上安装 windows PowerShell。</p></td>
</tr>
</tbody>
</table>



## 合规性和审核数据库的先决条件


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">必备</th>
<th align="left">详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>SQL Server 支持的版本</p></td>
<td align="left"><p>安装包含 SQL_Latin1_General_CP1_CI_AS 排序规则的 SQL Server。</p>
<p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)"> </a> 有关支持的版本，请参阅 MBAM 2.5 支持的配置。</p></td>
</tr>
<tr class="even">
<td align="left"><p>所需的 SQL Server 权限</p></td>
<td align="left"><p>所需权限：</p>
<ul>
<li><p>SQL Server 实例登录服务器角色：</p>
<ul>
<li><p>dbcreator</p></li>
<li><p>processadmin</p></li>
</ul></li>
<li><p>SQL Server Reporting Services 实例权限：</p>
<ul>
<li><p>创建文件夹</p></li>
<li><p>发布报表</p></li>
</ul></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>可选-在 SQL Server 中安装透明数据加密（TDE）功能</p></td>
<td align="left"><p>TDE SQL Server 功能对数据和日志文件执行实时 i/o 加密和解密，这有助于你遵守适用于各种行业的法律、法规和指南。</p>
<p>TDE 执行数据库信息的实时解密。 这意味着，如果你在 SQL Server 数据库中查看恢复密钥信息，并且在具有数据库权限的帐户上登录，则恢复密钥信息将可见。 若要了解有关 TDE 的详细信息，请参阅 <a href="mbam-25-security-considerations.md" data-raw-source="[MBAM 2.5 Security Considerations](mbam-25-security-considerations.md)"> MBAM 2.5 安全注意事项 </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>SQL Server 数据库引擎服务</p></td>
<td align="left"><p>必须在 MBAM 服务器安装期间安装并运行 SQL Server 数据库引擎服务。 但是，SQL Server 可以远程运行;它不必在要安装 MBAM Server 软件的同一服务器上。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows PowerShell 3.0 或更高版本</p></td>
<td align="left"><p>如果使用 Windows PowerShell 配置来自远程计算机的数据库，则无需在合规性和审核数据库服务器上安装 Windows PowerShell。</p></td>
</tr>
</tbody>
</table>



## 报表的先决条件


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">必备</th>
<th align="left">详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>SQL Server 支持的版本</p></td>
<td align="left"><p>安装包含 SQL_Latin1_General_CP1_CI_AS 排序规则的 SQL Server。</p>
<p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)"> </a> 有关支持的版本，请参阅 MBAM 2.5 支持的配置。</p></td>
</tr>
<tr class="even">
<td align="left"><p>SQL Server Reporting Services （SSRS）</p></td>
<td align="left"><p>在 MBAM 服务器安装期间，必须安装并运行 SSRS。</p>
<p>在 &quot; 纯 &quot; 模式下配置 SSRS，而不是在未配置或 &quot; SharePoint &quot; 模式下配置 SSRS。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>SSRS 实例权限-仅当在配置了报表的服务器所在服务器上安装数据库时，才需要配置报表。</p></td>
<td align="left"><p>所需实例权限：</p>
<ul>
<li><p>创建文件夹</p></li>
<li><p>发布报表</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>Windows PowerShell 3.0 或更高版本</p></td>
<td align="left"><p>如果使用 Windows PowerShell 配置来自远程计算机的数据库，则无需在此数据库服务器上安装 windows PowerShell。</p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-prereqsams"></a>管理和监视服务器的先决条件


下表列出了 MBAM 管理和监视服务器的安装先决条件。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">必备</th>
<th align="left">详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows Server Web 服务器角色</p></td>
<td align="left"><p>此角色必须添加到 "管理和监视服务器" 功能支持的服务器操作系统。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Web 服务器（IIS）管理工具</p></td>
<td align="left"><p>单击 " <strong> IIS 管理脚本和工具" </strong> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>SSL 证书</strong></p></td>
<td align="left"><p>可选。 若要保护客户端计算机和 web 服务之间的通信，你必须获取并安装受信任的安全机构签名的证书。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Web 服务器角色服务</p></td>
<td align="left"><p><strong>常见的 HTTP 功能：</strong></p>
<ul>
<li><p>静态内容</p></li>
<li><p>默认文档</p></li>
</ul>
<p><strong>应用程序开发：</strong></p>
<ul>
<li><p>ASP.NET</p></li>
<li><p>.NET 扩展性</p></li>
<li><p>ISAPI 扩展</p></li>
<li><p>ISAPI 筛选器</p></li>
</ul>
<p><strong>安全</strong></p>
<ul>
<li><p>Windows 身份验证</p></li>
<li><p>请求筛选</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server 功能</p></td>
<td align="left"><p><strong>.NET Framework 4.5 功能：</strong></p>
<ul>
<li><p><strong>.NET Framework 4.5 或4。6</strong></p>
<ul>
<li><p><strong></strong> - 已为这些版本的 windows server 安装了 windows server 2016 .net Framework 4.6，但必须启用它。</p></li>  
<li><p><strong>Windows server 2012 或 Windows Server 2012 R2 </strong> - .net Framework 4.5 已针对这些版本的 windows server 安装，但必须启用它。</p></li>
<li><p><strong>Windows server 2008 R2 </strong> - .net framework 4.5 不包含在 windows Server 2008 R2 中，因此必须 <a href="https://go.microsoft.com/fwlink/?LinkId=392318" data-raw-source="[download Microsoft .NET Framework 4.5](https://go.microsoft.com/fwlink/?LinkId=392318)"> 下载 Microsoft .net Framework 4.5 </a> 并单独安装。</p>
<div class="alert">
<strong>注意</strong><br/><p>如果你要从 MBAM 2.0 或 MBAM 2.0 SP1 升级，并且需要安装 .NET Framework 4.5，请参阅 <a href="release-notes-for-mbam-25.md" data-raw-source="[Release Notes for MBAM 2.5](release-notes-for-mbam-25.md)"> MBAM 2.5 的发行说明， </a> 以使网站工作。</p>
</div>
<div>

</div></li>
</ul></li>
<li><p><strong>WCF 激活</strong></p>
<ul>
<li><p>HTTP 激活</p></li>
<li><p>非 HTTP 激活（仅适用于 Windows Server 2008、2012和 2012 R2）</p>
<p></p></li>
</ul></li>
<li><p><strong>TCP 激活</strong></p></li>
</ul>
<p><strong>Windows 进程激活服务：</strong></p>
<ul>
<li><p>流程模型</p></li>
<li><p>.NET Framework 环境</p></li>
<li><p>配置 Api</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>ASP.NET MVC 4。0</p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=392271" data-raw-source="[ASP.NET MVC 4 download](https://go.microsoft.com/fwlink/?LinkId=392271)">ASP.NET MVC 4 下载</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>服务主体名称（SPN）</p></td>
<td align="left"><p>Web 应用程序要求在用于 web 应用程序池的域帐户下的虚拟主机名称中使用 SPN。</p>
<p>如果你的管理权限允许你在 Active Directory 域服务中创建 Spn，MBAM 会为你创建 SPN。 <a href="https://technet.microsoft.com/library/cc731241.aspx" data-raw-source="[Setspn](https://technet.microsoft.com/library/cc731241.aspx)"> </a> 有关创建 spn 所需的权限的信息，请参阅 Setspn。</p>
<p>如果你没有创建 Spn 的管理员权限，则必须使用以下命令让你的组织中的 Active Directory 管理员为你创建 SPN。</p>
<pre class="syntax" space="preserve"><code>Setspn -s http/mbamvirtual contoso\mbamapppooluser
Setspn -s http/mbamvirtual.contoso.com contoso\mbamapppooluser</code></pre>
<p>在该代码示例中，虚拟主机名为 mbamvirtual.contoso.com，用于 web 应用程序池的域帐户为 contoso\mbamapppooluser。</p>
<div class="alert">
<strong>注意</strong><br/><p>如果要设置负载平衡，请在所有服务器上使用相同的应用程序池帐户。</p>
</div>
<div>

</div>
<p>有关为完全限定的、NetBIOS 和自定义主机名注册 Spn 的详细信息，请参阅 <a href="planning-how-to-secure-the-mbam-websites.md" data-raw-source="[Planning How to Secure the MBAM Websites](planning-how-to-secure-the-mbam-websites.md)"> 规划如何保护 MBAM 网站的安全 </a> 。</p></td>
</tr>
</tbody>
</table>



## 自助服务门户的先决条件


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">必备</th>
<th align="left">详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows Server 支持的版本</p></td>
<td align="left"><p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)"> </a> 有关支持的版本，请参阅 MBAM 2.5 支持的配置。</p></td>
</tr>
<tr class="even">
<td align="left"><p>ASP.NET MVC 4。0</p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=392271" data-raw-source="[ASP.NET MVC 4 download](https://go.microsoft.com/fwlink/?LinkId=392271)">ASP.NET MVC 4 下载</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>Web 服务 IIS 管理工具</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>服务主体名称（SPN）</p></td>
<td align="left"><p>Web 应用程序要求在用于 web 应用程序池的域帐户下的虚拟主机名称中使用 SPN。</p>
<p>如果你的管理权限允许你在 Active Directory 域服务中创建 Spn，MBAM 会为你创建 SPN。 <a href="https://technet.microsoft.com/library/cc731241.aspx" data-raw-source="[Setspn](https://technet.microsoft.com/library/cc731241.aspx)"> </a> 有关创建 spn 所需的权限的信息，请参阅 Setspn。</p>
<p>如果您没有创建 Spn 的管理员权限，则必须让组织中的 Active Directory 管理员使用以下命令为您创建 SPN。</p>
<pre class="syntax" space="preserve"><code>Setspn -s http/mbamvirtual contoso\mbamapppooluser
Setspn -s http/mbamvirtual.contoso.com contoso\mbamapppooluser</code></pre>
<p>在该代码示例中，虚拟主机名为 mbamvirtual.contoso.com，用于 web 应用程序池的域帐户为 contoso\mbamapppooluser。</p>
<div class="alert">
<strong>注意</strong><br/><p>如果要设置负载平衡，请在所有服务器上使用相同的应用程序池帐户。</p>
</div>
<div>

</div>
<p>有关为完全限定的、NetBIOS 和自定义主机名注册 Spn 的详细信息，请参阅 <a href="planning-how-to-secure-the-mbam-websites.md" data-raw-source="[Planning How to Secure the MBAM Websites](planning-how-to-secure-the-mbam-websites.md)"> 规划如何保护 MBAM 网站的安全 </a> 。</p></td>
</tr>
</tbody>
</table>



## 管理工作站的先决条件


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">必备</th>
<th align="left">详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>在安装 MBAM 客户端之前，请从 <a href="https://go.microsoft.com/fwlink/p/?LinkId=393941" data-raw-source="[How to Get MDOP Group Policy (.admx) Templates](https://go.microsoft.com/fwlink/p/?LinkId=393941)"> 如何获取 MDOP 组策略（admx）模板中下载 MBAM 组策略模板 </a> ，并使用你希望在你的企业中实现的用于 BitLocker 驱动器加密的设置配置这些模板。</p></td>
<td align="left"><p>在安装 MBAM 客户端之前，请执行以下操作：</p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">要执行的操作</th>
<th align="left">获取说明的位置</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>复制 MBAM 组策略模板</p></td>
<td align="left"><p><a href="copying-the-mbam-25-group-policy-templates.md" data-raw-source="[Copying the MBAM 2.5 Group Policy Templates](copying-the-mbam-25-group-policy-templates.md)">复制 MBAM 2.5 组策略模板</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>编辑组策略设置</p></td>
<td align="left"><p><a href="editing-the-mbam-25-group-policy-settings.md" data-raw-source="[Editing the MBAM 2.5 Group Policy Settings](editing-the-mbam-25-group-policy-settings.md)">编辑 MBAM 2.5 组策略设置</a></p></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
</tbody>
</table>





## 相关主题


[为 MBAM 2.5 准备你的环境](preparing-your-environment-for-mbam-25.md)

[规划部署 MBAM 2.5](planning-to-deploy-mbam-25.md)

[MBAM 2.5 支持的配置](mbam-25-supported-configurations.md)




## 已获得 MBAM 的建议？
- 在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。
- 对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。




