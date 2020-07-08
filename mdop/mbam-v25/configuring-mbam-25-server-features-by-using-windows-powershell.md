---
title: 使用 Windows PowerShell 配置 MBAM 2.5 服务器功能
description: 使用 Windows PowerShell 配置 MBAM 2.5 服务器功能
author: dansimp
ms.assetid: 826429fd-29bb-44be-b47e-5f5c7d20dd1d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: f350a9eb96a20f50644cfdc1965b7f72741a2c29
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803248"
---
# 使用 Windows PowerShell 配置 MBAM 2.5 服务器功能


在安装 MBAM 2.5 服务器软件后，您可以使用 Windows PowerShell cmdlet 或 "MBAM 服务器配置向导" 配置 MBAM 2.5 服务器功能。 本主题介绍如何使用 Windows PowerShell cmdlet 配置 MBAM 2.5。 若要改为使用该向导，请参阅[配置 MBAM 2.5 服务器功能](configuring-the-mbam-25-server-features.md)。

## 本主题内容


本主题包括有关使用 Windows PowerShell 配置 MBAM 的以下信息：

-   [如何加载 MBAM 2.5 的 Windows PowerShell 帮助](#bkmk-load-posh-help)

-   [如何获取有关 MBAM Windows PowerShell cmdlet 的帮助](#bkmk-help-specific-cmdlet)

-   [只能在 Windows PowerShell 中执行但不能通过 MBAM Server 配置向导执行的配置](#bkmk-config-only-posh)

-   [使用 Windows PowerShell 配置 MBAM Server 功能的先决条件和要求](#bkmk-prereqs-posh-mbamsvr)

-   [在远程计算机上使用 Windows PowerShell 配置 MBAM](#bkmk-remote-config)

-   [必需帐户和相应的 Windows PowerShell cmdlet 参数](#bkmk-reqd-posh-accts)

有关用于管理 MBAM 的**MbamBitLockerRecoveryKey**和**MbamTPMOwnerPassword** Windows PowerShell cmdlet 的信息，请参阅[使用 Windows PowerShell 管理 MBAM 2.5](using-windows-powershell-to-administer-mbam-25.md)。

## <a href="" id="bkmk-load-posh-help"></a>如何加载 MBAM 2.5 的 Windows PowerShell 帮助


有关 TechNet 上的 Windows PowerShell cmdlet 的列表，请参阅[使用 Windows PowerShell 的 Microsoft 桌面优化包自动化](https://go.microsoft.com/fwlink/?LinkId=392816)。

**在安装 MBAM 服务器软件后加载适用于 Windows PowerShell cmdlet 的 MBAM 2.5 帮助**

1.  打开 Windows PowerShell 或 Windows PowerShell 集成脚本环境（ISE）。

2.  类型**更新-帮助-MBAM**。

## <a href="" id="bkmk-help-specific-cmdlet"></a>如何获取有关 MBAM Windows PowerShell cmdlet 的帮助


适用于 MBAM 的 Windows PowerShell 帮助有以下格式：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Windows PowerShell 帮助格式</th>
<th align="left">详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>在 Windows PowerShell 命令提示符处，键入 <strong> get-help </strong> &lt; <em> cmdlet</em>&gt;</p></td>
<td align="left"><p>若要上载最新的 Windows PowerShell cmdlet，请按照上一节中关于如何加载 MBAM 的 Windows PowerShell 帮助中的说明进行操作。</p></td>
</tr>
<tr class="even">
<td align="left"><p>在 TechNet 上作为网页</p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=393498" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=393498">https://go.microsoft.com/fwlink/?LinkId=393498</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>在下载中心中作为单词表文件</p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=393497" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=393497">https://go.microsoft.com/fwlink/?LinkId=393497</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>在下载中心中作为 .pdf 文件</p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=393499" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=393499">https://go.microsoft.com/fwlink/?LinkId=393499</a></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-config-only-posh"></a>只能在 Windows PowerShell 中执行但不能通过 MBAM Server 配置向导执行的配置


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">只能使用 Windows PowerShell 执行的配置</th>
<th align="left">详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>从 web 应用程序在单独的计算机上安装 web 服务。</p></td>
<td align="left"><p>使用该向导，必须在同一台计算机上安装 web 服务和 web 应用程序。</p></td>
</tr>
<tr class="even">
<td align="left"><p>在单独的报告服务点上启用报告，而不安装所有配置管理器对象。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>从 Configuration Manager 中删除所有对象。</p></td>
<td align="left"><p>删除对象依次删除配置管理器中的所有合规性数据。</p></td>
</tr>
<tr class="even">
<td align="left"><p>为数据库输入自定义连接字符串。</p></td>
<td align="left"><p>示例：若要将 web 应用程序配置为使用镜像，必须使用 <strong> Enable-MbamWebApplication </strong> cmdlet 指定连接字符串中的相应故障转移合作伙伴语法。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>即使先决条件检查失败，也跳过验证和配置功能。</p></td>
<td align="left"></td>
</tr>
</tbody>
</table>

 

**注意** 不能使用 Windows PowerShell cmdlet 或 MBAM 服务器配置向导禁用 MBAM 数据库。 为了防止意外删除合规性和审核数据，数据库管理员必须手动删除数据库。

 

## <a href="" id="bkmk-prereqs-posh-mbamsvr"></a>使用 Windows PowerShell 配置 MBAM Server 功能的先决条件和要求


开始配置之前，请完成以下先决条件。

**与客户相关的先决条件**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">必备</th>
<th align="left">详细信息或其他信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>创建所需帐户。</p></td>
<td align="left"><p>请参阅 <strong> 本主题后面部分的所需帐户和相应的 Windows PowerShell cmdlet 参数 </strong> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>作为参数传递到 Windows PowerShell cmdlet 的用户帐户和组必须是域中的有效帐户。</p></td>
<td align="left"><p>您不能使用本地帐户。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>以低级格式指定帐户。</p></td>
<td align="left"><p>示例：</p>
<p>domainNetBiosName\userdomainNetBiosName\group</p></td>
</tr>
</tbody>
</table>

 

**权限相关的先决条件**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">必备</th>
<th align="left">详细信息或其他信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>您必须是要在其中配置 MBAM 功能的本地计算机上的管理员。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>使用提升的 Windows PowerShell 命令提示符运行所有 Windows PowerShell cmdlet。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>仅限 Enable-MbamDatabase </strong> cmdlet：</p>
<p>您必须对 &quot; &quot; 目标 Microsoft SQL Server 数据库的实例具有 "创建任何数据库权限"。</p>
<p>此用户帐户必须是本地管理员组或备份操作员组的一部分，才能注册 MBAM 卷影复制服务（VSS）编写器。</p></td>
<td align="left"><p>默认情况下，数据库管理员或系统管理员具有所需的 &quot; 创建任何数据库 &quot; 权限。</p>
<p></p>
<p>有关 VSS 书写器的详细信息，请参阅 <a href="https://go.microsoft.com/fwlink/?LinkId=392814" data-raw-source="[Volume Shadow Copy Service](https://go.microsoft.com/fwlink/?LinkId=392814)"> 卷影复制服务 </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>仅适用于 <strong> System Center Configuration Manager 集成 </strong> 功能：</p>
<p>启用此功能的用户必须在 Configuration Manager 中具有以下权限：</p></td>
<td align="left"><table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Configuration Manager 中的权限类型</th>
<th align="left">所需权限</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Configuration Manager 网站权限：</p></td>
<td align="left"><p>- 已阅读</p></td>
</tr>
<tr class="even">
<td align="left"><p>Configuration Manager 收集权限：</p></td>
<td align="left"><p>- 创建-删除-已读-修改-部署配置项目</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Configuration Manager 配置项目权限：</p></td>
<td align="left"><p>- 创建-删除-已读</p></td>
</tr>
</tbody>
</table>
<p> </p>
<p></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-remote-config"></a>在远程计算机上使用 Windows PowerShell 配置 MBAM


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>何时使用此功能</strong></p></td>
<td align="left"><p>当您想要在远程计算机上配置 MBAM 2.5 服务器功能时。 Windows PowerShell cmdlet 在一台计算机上运行，并且你正在配置不同的远程计算机上的功能。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>必须执行的操作</strong></p></td>
<td align="left"><p>若要使用 Windows PowerShell 在远程计算机上配置 MBAM 2.5 服务器功能，您必须：</p>
<ul>
<li><p>确保已在远程计算机上安装了 MBAM 2.5 服务器软件。</p></li>
<li><p>使用凭据安全支持提供程序（CredSSP）协议打开 Windows PowerShell 会话。</p></li>
<li><p>启用 Windows 远程管理（WinRM）。 如果你无法启用 WinRM 并正确配置它， <strong> </strong> 此表中所述的新 PSSession cmdlet 将显示错误并介绍如何解决该问题。 有关 WinRM 的详细信息，请参阅 <a href="https://go.microsoft.com/fwlink/?LinkId=393064" data-raw-source="[Using Windows Remote Management](https://go.microsoft.com/fwlink/?LinkId=393064)"> 使用 Windows 远程管理 </a> 。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>为什么必须执行此操作</strong></p></td>
<td align="left"><p>此协议支持使用用户的管理凭据连接到 Active Directory 域服务的 Windows PowerShell cmdlet。 如果在不使用此协议的情况下启动 Windows PowerShell 会话，则可能会收到验证错误。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>如何使用 CredSSP 协议启动 Windows PowerShell 会话</strong></p></td>
<td align="left"><p>在 Windows PowerShell 提示符处键入以下代码：</p>
<p><code>$s = New-PSSession -ComputerName xxx -Authentication Credssp -Credential xxx</code></p>
<p>下面的代码显示了一个示例。</p>
<p><code>$session = New-PSSession -ComputerName &lt;MBAM_server_name&gt; -Authentication Credssp -Credential (Get-Credential)</code></p>
<p><code>Enter-PSSession $session</code></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-reqd-posh-accts"></a>必需帐户和相应的 Windows PowerShell cmdlet 参数


下表介绍了配置 MBAM 2.5 服务器功能所需的帐户。 它还会列出你必须在配置期间为其指定帐户的相应 Windows PowerShell cmdlet 和参数。

Cmdlet 参数类型（用户或组）描述 Enable-MBAMDatabase

AccessAccount

用户或组

指定对此数据库具有读/写权限的域用户或组，以使 web 应用程序能够访问此数据库中的数据和报表。 如果值为域用户，则运行**Enable MbamWebApplication** cmdlet 时使用的**WebServiceApplicationPoolCredential**参数必须使用相同的用户帐户。 如果值为 "域用户" 组，则**WebServiceApplicationPoolCredential**参数使用的域帐户必须是该组的成员。

ReportAccount

用户或组

指定对此数据库具有只读权限的域用户组，以便提供 MBAM 报表对合规性和审核数据的访问。 如果值为域用户，则**Enable-MbamReport** Cmdlet 的**ComplianceAndAuditDBCredential**参数必须使用相同的用户帐户。 如果值为 "域用户" 组，则**ComplianceAndAuditDBCredential**参数使用的域帐户必须是该组的成员。

Enable-MbamReport

ComplianceAndAuditDBCredential

用户

指定本地 SSRS 实例用于连接到 MBAM 合规性和审核数据库的管理凭据。 管理凭据中的域用户必须与用于**ReportAccount**参数的用户帐户相同，该帐户在运行**Enable-MbamDatabase** cmdlet 时使用。 如果域用户组与**ReportAccount**参数一起使用，则此帐户应为该组的成员。

**重要提示** 管理凭据中指定的帐户应具有受限的用户权限，以提高安全性。 此外，帐户的密码应设置为 "未过期"。

 

ReportsReadOnlyAccessGroup

组

指定对报告具有读取权限的域用户组。 指定的组必须与**Enable-MbamWebApplication** cmdlet 中的**ReportsReadOnlyAccessGroup**参数一起使用的组相同。

Enable-MBAMWebApplication

AdvancedHelpdeskAccessGroup

组

指定有权访问除 "报告" 区域之外的 "管理和监视" 网站的所有区域的 "域用户" 组。

HelpdeskAccessGroup

组

指定有权访问管理和监视网站的 "**管理 TPM** " 和 "**驱动器恢复**" 区域的 "域用户" 组。

ReportsReadOnlyAccessGroup

组

指定对管理和监视网站的 "**报告**" 区域具有读取权限的 "域用户" 组。 指定的组必须与**Enable-MbamReport** cmdlet 中的**ReportsReadOnlyAccessGroup**参数一起使用的组相同。

WebServiceApplicationPoolCredential

用户

指定要由 MBAM web 应用程序的应用程序池使用的域用户。 它必须是在**Enable-MbamDatabase** Cmdlet 的**AccessAccount**参数中指定的相同域用户帐户。 如果在运行**Enable MbamDatabase** Cmdlet 时**AccessAccount**参数使用域用户组，则此处指定的域用户必须是该组的成员。 如果不指定管理凭据，将使用由以前启用的任何 web 应用程序指定的管理凭据。 所有 web 应用程序都使用相同的应用程序池标识。 如果多次指定，则使用最新指定的值。

**重要提示** 为了提高安全性，请将管理凭据中指定的帐户设置为受限的用户权限。 此外，将帐户的密码设置为永不过期。 确保已将内置 IIS \ _IUSRS 帐户或用于**WebServiceApplicationPoolCredential**参数的帐户添加到 "身份验证本地安全设置**后模拟客户端**" 设置。

若要查看本地安全设置，请打开 "**本地安全策略编辑器**"，展开 "**本地策略**" 节点，选择 "**用户权限分配**" 节点，然后双击 "**身份验证后模拟客户端**"，然后双击 "详细信息" 窗格中的 "**批处理作业**组策略设置"。

 

 




## 相关主题


[配置 MBAM 2.5 服务器功能](configuring-the-mbam-25-server-features.md)

[验证 MBAM 2.5 服务器功能配置](validating-the-mbam-25-server-feature-configuration.md)

[使用 Windows PowerShell 管理 MBAM 2.5](using-windows-powershell-to-administer-mbam-25.md)

 
## 已获得 MBAM 的建议？
- 在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。 
- 对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。
 





