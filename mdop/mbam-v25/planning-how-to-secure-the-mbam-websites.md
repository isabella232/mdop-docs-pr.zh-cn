---
title: 规划如何保护 MBAM 网站
description: 规划如何保护 MBAM 网站
author: dansimp
ms.assetid: aea1d137-62cf-4da4-9989-541e0b5ad8d8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 223c9397ad7933e11051c289c3dbcab63940fbc5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803685"
---
# 规划如何保护 MBAM 网站


本主题介绍以下用于保护 Microsoft BitLocker 管理和监视（MBAM）2.5 管理和监控网站和自助服务门户的方法：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">方法</th>
<th align="left">必需还是可选的？</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>使用证书保护 MBAM 网站</p></td>
<td align="left"><p>可选，但强烈建议</p></td>
</tr>
<tr class="even">
<td align="left"><p>注册应用程序池帐户的服务主体名称（SPN）</p></td>
<td align="left"><p>必需</p></td>
</tr>
</tbody>
</table>



有关如何保护 MBAM 部署的详细信息，请参阅[MBAM 2.5 安全注意事项](mbam-25-security-considerations.md)。

## 使用证书保护 MBAM 网站


我们建议你使用证书来保护以下各内容之间的通信：

-   MBAM 客户端和 web 服务

-   浏览器和管理和监控网站以及自助服务门户网站

有关请求和安装证书的信息，请参阅[配置 Internet 服务器证书](https://technet.microsoft.com/library/cc731977.aspx)。

**注意**  
只有在使用 Windows PowerShell 时，才能在不同服务器上配置网站和 web 服务。 如果使用 MBAM 服务器配置向导配置网站，则必须在同一台服务器上配置网站和 web 服务。



为了保护 web 服务和数据库之间的通信，我们还建议你在 SQL Server 中强制执行加密。 有关保护 SQL Server 的所有连接（包括 web 服务和 SQL Server 之间的通信）的详细信息，请参阅[MBAM 2.5 安全注意事项](mbam-25-security-considerations.md#bkmk-secure-databases)。

## 注册应用程序池帐户的 Spn


若要使 MBAM 服务器能够对来自管理和监视网站和自助服务门户的通信进行身份验证，你必须在用于 web 应用程序池的域帐户下注册主机名的服务主体名称（SPN）。

本主题包含有关如何为以下类型的主机名称注册 Spn 的说明：

-   完全限定的域名

-   NetBIOS 名称

-   虚拟名称

### 在为初始 MBAM 安装创建 Spn 之前

开始创建 Spn 之前，请查看下表中的信息。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">任务或项目</th>
<th align="left">详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>在 Active Directory 域服务（AD DS）中创建服务帐户。</p></td>
<td align="left"><p>服务帐户是在 AD DS 中创建的用于为 MBAM 网站提供安全性的用户帐户。 MBAM 网站在应用程序池下运行，其标识是服务帐户的名称。 然后，在应用程序池帐户中注册 Spn。</p>
<div class="alert">
<strong>注意</strong><br/><p>你必须对所有 web 服务器使用相同的应用程序池帐户。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p>验证 IIS IUSRS 组帐户或应用程序池帐户是否已被授予必要的权限。</p></td>
<td align="left"><p>若要检查此内容，请执行以下步骤：</p>
<ol>
<li><p>打开 " <strong> 本地安全策略编辑器" </strong> ，然后展开 " <strong> 本地策略" </strong> 节点。</p></li>
<li><p>选择 " <strong> 用户权限分配" </strong> 节点，然后双击 " <strong> 身份验证后模拟客户端" 和 "在 </strong> <strong> </strong> 右窗格中作为批处理作业组策略设置登录"。</p></li>
</ol></td>
</tr>
<tr class="odd">
<td align="left"><p>如果您使用域管理帐户配置 MBAM 网站，MBAM 将为您创建 Spn。</p></td>
<td align="left"><p>如果你使用域管理帐户配置 MBAM 网站，请按照本主题中的步骤为你使用的主机名类型手动注册 Spn。</p></td>
</tr>
</tbody>
</table>



### 使用完全限定的域主机名时注册 Spn

如果在配置 MBAM 时使用完全限定的域名主机名，则只需注册一个 SPN，如以下示例所示。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">需要执行的操作</th>
<th align="left">示例和详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>为完全限定的域名注册 SPN。</p></td>
<td align="left"><p><code>Setspn -s http/mybitlockerrecovery.contoso.com contoso\mbamapppooluser</code></p>
<p>完全限定的主机名为 <strong> mybitlockerrecovery.contoso.com </strong> ，而用于 web 应用程序池的域帐户为 <strong> contoso\mbamapppooluser </strong> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>为你为应用程序池帐户注册的 SPN 配置受限委派。</p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=394335" data-raw-source="[Configuring Constrained Delegation](https://go.microsoft.com/fwlink/?LinkId=394335)">配置受限委派</a></p>
<p>此要求仅适用于 MBAM 2.5;MBAM 2.5 SP1 中不需要此功能。</p></td>
</tr>
</tbody>
</table>



### 使用 NetBIOS 主机名注册 Spn

如果在配置 MBAM 时使用 NetBIOS 主机名，请为 NetBIOS 名称注册一个 SPN，为完全限定的域名注册另一个 SPN，如以下示例中所示。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">需要执行的操作</th>
<th align="left">示例和详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>为 NetBIOS 主机名注册 SPN。</p></td>
<td align="left"><p><code>Setspn -s http/nbname01 contoso\mbamapppooluser</code></p>
<p>NetBIOS 主机名为 <strong> nbname01 </strong> ，用于 web 应用程序池的域帐户为 <strong> contoso\mbamapppooluser </strong> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>为完全限定的域名注册 SPN。</p></td>
<td align="left"><p><code>Setspn –s http/nbname01.corp.contoso.com contoso\mbamapppooluser</code></p>
<p>完全限定的域名是 <strong> nbname01.contoso.com </strong> ，而用于 web 应用程序池的域帐户是 <strong> contoso\mbamapppooluser </strong> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>针对为应用程序池帐户注册的 Spn 配置受约束的委派。</p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=394335" data-raw-source="[Configuring Constrained Delegation](https://go.microsoft.com/fwlink/?LinkId=394335)">配置受限委派</a></p>
<p>此要求仅适用于 MBAM 2.5;MBAM 2.5 SP1 中不需要此功能。</p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-regvirtualspn"></a>使用虚拟主机名时注册 Spn

如果将 MBAM 配置为具有完全限定域名的虚拟主机名，请仅为虚拟主机名注册一个 SPN。 如果你配置的虚拟主机名不是完全限定的域名，则必须创建第二个 SPN 来指定完全限定的域名，如以下示例中所述。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">需要执行的操作</th>
<th align="left">示例和详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>如果你的虚拟主机名是完全限定的域名，如本示例中所示，仅注册一个 SPN。</p></td>
<td align="left"><p><code>Setspn -s http/mbamvirtual.contoso.com contoso\mbamapppooluser</code></p>
<p>在此示例中，虚拟主机名为 <strong> mbamvirtual.contoso.com </strong> ，而用于 web 应用程序池的域帐户为 <strong> contoso\mbamapppooluser </strong> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>如果你的虚拟主机名不是完全限定的域名，请注册此额外的 SPN。</p></td>
<td align="left"><p><code>Setspn -s http/mbamvirtual contoso\mbamapppooluser</code></p>
<p>在此示例中，虚拟主机名为 <strong> mbamvirtual </strong> ，而用于 web 应用程序池的域帐户为 <strong> contoso\mbamapppooluser </strong> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>如果你的虚拟主机名不是完全限定的域名，请注册此额外的 SPN。</p></td>
<td align="left"><p><code>Setspn -s http/mbamvirtual.contoso.com contoso\mbamapppooluser</code></p>
<p>在此示例中，虚拟主机名为 <strong> mbamvirtual.contoso.com </strong> ，而用于 web 应用程序池的域帐户为 <strong> contoso\mbamapppooluser </strong> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>在 "域名服务器（DNS）" 服务器上，为自定义主机名创建一个 "A 记录"，并将其指向 web 服务器或负载平衡器。</p></td>
<td align="left"><p>请参阅 <a href="https://go.microsoft.com/fwlink/?LinkId=394337" data-raw-source="[Configure DNS Host Records](https://go.microsoft.com/fwlink/?LinkId=394337)"> 配置 Dns 主机记录中的 "配置 Dns 主机 A 记录" 部分 </a> 。</p>
<p>我们建议您使用记录，而不是 CNAMES。 如果使用 CNAMES 指向域地址，还必须在应用程序池帐户中注册 web 服务器名称的 Spn。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>针对为应用程序池帐户注册的 Spn 配置受约束的委派。</p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=394335" data-raw-source="[Configuring Constrained Delegation](https://go.microsoft.com/fwlink/?LinkId=394335)">配置受限委派</a></p>
<p>此要求仅适用于 MBAM 2.5;MBAM 2.5 SP1 中不需要此功能。</p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-registerspn"></a>从早期版本的 MBAM 升级时注册 SPN

仅当需要执行以下操作时才完成本部分中的步骤：

-   从早期版本的 MBAM 升级。

-   在负载平衡或分布式配置中运行 MBAM 2.5 中的网站，并且当前在未进行负载平衡的配置中运行。

如果你已在计算机帐户（而不是应用程序池帐户）中注册了 Spn，MBAM 将使用现有的 Spn，并且你无法在负载平衡或分布式配置中配置网站。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">需要执行的操作</th>
<th align="left">示例和详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>在 Active Directory 域服务（AD DS）中创建应用程序池帐户。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>删除当前已安装的网站和 web 服务。</p></td>
<td align="left"><p><a href="removing-mbam-server-features-or-software.md" data-raw-source="[Removing MBAM Server Features or Software](removing-mbam-server-features-or-software.md)">删除 MBAM 服务器功能或软件</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>从计算机帐户中删除 Spn。</p></td>
<td align="left"><p><code>Setspn –d http/mbamwebserver mbamwebserver</code></p>
<p><code>Setspn –d http/mbamwebserver.contoso.com mbamwebserver</code></p></td>
</tr>
<tr class="even">
<td align="left"><p>在应用程序池帐户中注册 Spn。</p></td>
<td align="left"><p><a href="#bkmk-regvirtualspn" data-raw-source="[Registering SPNs when you use a virtual host name](#bkmk-regvirtualspn)">使用虚拟主机名时，请按照注册 spn 的步骤进行操作 </a> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>重新配置 web 应用程序和 web 服务。</p></td>
<td align="left"><p><a href="how-to-configure-the-mbam-25-web-applications.md" data-raw-source="[How to Configure the MBAM 2.5 Web Applications](how-to-configure-the-mbam-25-web-applications.md)">如何配置 MBAM 2.5 Web 应用程序</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>根据用于配置的方法，执行下列操作之一：</p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">方法</th>
<th align="left">详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>MBAM Server 配置向导</strong></p></td>
<td align="left"><p>在 " <strong> Web 服务应用程序池域帐户" 字段中输入应用程序池帐户 </strong> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p><code>Enable-MbamWebApplication</code> Windows PowerShell cmdlet</p></td>
<td align="left"><p>在参数中输入帐户 <code>WebServiceApplicationPoolCredential</code> 。</p></td>
</tr>
</tbody>
</table>
<p> </p></td>
<td align="left"><div class="alert">
<strong>重要提示</strong><br/><p>输入的主机名必须与要为其创建 Spn 的虚拟主机名同名。 此外，在您的 web 场中，主机名和应用程序池凭据在您要配置的每台服务器上必须是相同的。</p>
</div>
<div>

</div>
<p>当 MBAM 配置 web 应用程序时，它将尝试为你注册 Spn，但只有当你在其上安装 MBAM 的服务器上有域管理员权限时，才可以执行此操作。 如果你不具有这些权限，则可以完成配置，但你必须在配置 MBAM 之前或之后设置 Spn。</p></td>
</tr>
</tbody>
</table>

## 所需的请求筛选设置

 应用程序按预期操作时需要 "允许未列出的文件扩展名"。  可通过导航到 "Microsoft BitLocker 管理和监视"-> 请求筛选-> "编辑" 功能设置找到此项。


## 相关主题


[为 MBAM 2.5 准备你的环境](preparing-your-environment-for-mbam-25.md)

[MBAM 2.5 部署先决条件](mbam-25-deployment-prerequisites.md)





## 已获得 MBAM 的建议？
- 在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。
- 对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。



