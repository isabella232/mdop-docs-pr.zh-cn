---
title: 如何配置 MBAM 2.5 Web 应用程序
description: 如何配置 MBAM 2.5 Web 应用程序
author: dansimp
ms.assetid: 909bf2d3-028c-4ac1-9247-171532a1eeae
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0336d24f51167a00c8565ccd081f4bc5dfb2c4cd
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803580"
---
# 如何配置 MBAM 2.5 Web 应用程序


本主题介绍了如何使用以下方法之一为 MBAM 2.5 配置 Microsoft BitLocker 管理和监视（MBAM） 2.5 web 应用程序以获取推荐的[高级别体系结构](high-level-architecture-for-mbam-25.md)：

-   Windows PowerShell cmdlet

-   MBAM Server 配置向导

Web 应用程序包含以下网站及其相应的 web 服务：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Website</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>管理和监视网站</p></td>
<td align="left"><p>网站，其中指定用户可以查看报表，并帮助最终用户在忘记 PIN 或密码时恢复其计算机</p></td>
</tr>
<tr class="even">
<td align="left"><p>自助服务门户</p></td>
<td align="left"><p>最终用户可以访问的网站，如果他们忘记了 PIN 或密码，可以独立地重新获得其计算机的访问权限</p></td>
</tr>
</tbody>
</table>



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
<td align="left"><p>在每台服务器上完成所需的先决条件。</p>
<div class="alert">
<strong>注意</strong><br/><p>在配置管理和监视网站之前，请确保将 SQL ServerReporting Services （SSRS）配置为使用安全套接字层（SSL）。 否则，"报表" 功能将使用 HTTP 而不是 HTTPS。</p>
</div>
<div>

</div></td>
<td align="left"><ul>
<li><p><a href="mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md" data-raw-source="[MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)">独立和 Configuration Manager 集成拓扑的 MBAM 2.5 服务器先决条件</a></p></li>
<li><p><a href="mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md" data-raw-source="[MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology](mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md)">仅适用于 Configuration Manager 集成拓扑 </a> （如果适用）的 MBAM 2.5 服务器必备条件</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>注册网站的应用程序池帐户的服务主体名称（Spn）。 只有在 Active Directory 域服务（AD DS）中没有管理域权限的情况下，才需要执行此步骤。 如果你在 AD DS 中拥有这些权限，MBAM 将为你创建 Spn。</p></td>
<td align="left"><p><a href="planning-how-to-secure-the-mbam-websites.md#bkmk-regvirtualspn" data-raw-source="[Planning How to Secure the MBAM Websites](planning-how-to-secure-the-mbam-websites.md#bkmk-regvirtualspn)">规划如何保护 MBAM 网站</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>在将在其中配置 MBAM 服务器功能的每台服务器上安装 MBAM 服务器软件。</p>
<div class="alert">
<strong>注意</strong><br/><p>如果你计划在一台服务器上安装网站，并在另一台服务器上安装 web 服务，你将只能通过使用 <strong> Enable-MbamWebApplication </strong> Windows PowerShell cmdlet 来配置它们。 MBAM Server 配置向导不支持在单独的服务器上配置这些项目。</p>
</div>
<div>

</div></td>
<td align="left"><p><a href="installing-the-mbam-25-server-software.md" data-raw-source="[Installing the MBAM 2.5 Server Software](installing-the-mbam-25-server-software.md)">安装 MBAM 2.5 服务器软件</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>如果计划使用 cmdlet 配置 MBAM Server 功能，请查看使用 Windows PowerShell 的先决条件。</p></td>
<td align="left"><p><a href="configuring-mbam-25-server-features-by-using-windows-powershell.md" data-raw-source="[Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md)">使用 Windows PowerShell 配置 MBAM 2.5 服务器功能</a></p></td>
</tr>
</tbody>
</table>



**使用 Windows PowerShell 配置 web 应用程序**

1.  在开始配置之前，请参阅[使用 Windows Powershell 配置 MBAM 2.5 服务器功能](configuring-mbam-25-server-features-by-using-windows-powershell.md)，以查看使用 windows powershell 的先决条件。

2.  使用**MbamWebApplication** cmdlet 配置使用 Windows PowerShell 的 web 应用程序。 若要获取有关此 cmdlet 的信息，请键入**Get-help Enable-MbamWebApplication**。

**使用向导配置所有 web 应用程序的设置**

1. 在要配置 web 应用程序的服务器上，启动 "MBAM 服务器配置向导"。 可以从 "**开始**" 菜单中选择 " **MBAM 服务器配置**" 以打开该向导。

2. 单击 "**添加新功能**"，选择 "**管理和监视网站**和**自助服务门户**"，然后单击 "**下一步**"。 向导检查是否满足 web 应用程序的所有先决条件。

3. 如果先决条件检查成功，请单击 "**下一步**" 以继续。 否则，请解决任何缺少的先决条件，然后**再次单击 "检查必备项**"。

4. 使用以下说明在向导中输入字段值。

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><strong>字段</strong></th>
   <th align="left">描述</th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong>安全证书</strong></p></td>
   <td align="left"><p>选择以前创建的证书，以选择性地加密 web 服务与正在配置网站的服务器之间的通信。 如果您选择 <strong> "不使用证书 </strong> "，则您的 web 通信可能不安全。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong>主机名</strong></p></td>
   <td align="left"><p>要在其中配置网站的主机的名称。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong>安装路径</strong></p></td>
   <td align="left"><p>要在其中安装网站的路径。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong>端口</strong></p></td>
   <td align="left"><p>用于网站和服务通信的端口号。</p>
   <div class="alert">
   <strong>注意</strong><br/><p>必须设置防火墙例外以通过指定的端口启用通信。</p>
   </div>
   <div>

   </div></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong>Web 服务应用程序池域帐户和密码</strong></p></td>
   <td align="left"><p>Web 服务应用程序池的域用户帐户和密码。</p>
   <p>如果在 <strong> "配置数据库" 页面上的 "读/写访问域" 用户或组字段中输入用户名 </strong> <strong> </strong> ，则必须在此字段中输入相同的值。</p>
   <p>如果在 <strong> "配置数据库" 页面上的 "读/写访问域" 用户或组字段中输入组名称 </strong> <strong> </strong> ，则在此字段中输入的值必须是该组的成员。</p>
   <p>如果不指定凭据，将使用为以前启用的任何 web 应用程序指定的凭据。 所有 web 应用程序都必须使用相同的应用程序池凭据。 如果为不同的 web 应用程序指定不同的凭据，将使用最近指定的值。</p>
   <div class="alert">
   <strong>重要提示</strong><br/><p>为了提高安全性，请将凭据中指定的帐户设置为具有受限的用户权限。 此外，将帐户的密码设置为永不过期。</p>
   </div>
   <div>

   </div></td>
   </tr>
   </tbody>
   </table>



5. 验证内置 IIS \ _IUSRS 帐户或应用程序池帐户是否已添加到**身份验证后模拟客户端**，以及**作为批处理作业**的本地安全设置登录。

   若要检查是否已将其添加到本地安全设置，请打开 "**本地安全策略编辑器**"，展开 "**本地策略**" 节点，单击 "**用户权限分配**" 节点，然后双击 "在**身份验证后模拟客户端**" 和 "在右窗格中**作为批处理作业登录**" 策略。

**使用向导配置数据库的连接信息**

1.  使用以下字段说明为合规性和审核数据库配置向导中的连接信息。

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
    <td align="left"><p>配置合规性和审核数据库的服务器的名称。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><strong>SQL Server 数据库实例</strong></p></td>
    <td align="left"><p>配置合规性和审核数据库的 SQL Server 实例名称。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><strong>数据库名称</strong></p></td>
    <td align="left"><p>合规性和审核数据库的名称。</p></td>
    </tr>
    </tbody>
    </table>



2.  使用以下字段说明为恢复数据库配置向导中的连接信息。

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
    <td align="left"><p>配置恢复数据库的服务器的名称。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><strong>SQL Server 数据库实例</strong></p></td>
    <td align="left"><p>在其中配置了恢复数据库的 SQL Server 实例名称。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><strong>数据库名称</strong></p></td>
    <td align="left"><p>恢复数据库的名称。</p></td>
    </tr>
    </tbody>
    </table>



**使用向导配置 web 应用程序**

1. 使用以下说明在向导中输入字段值以配置管理和监视网站。

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
   <td align="left"><p><strong>高级帮助台角色域组</strong></p></td>
   <td align="left"><p>其成员有权访问管理和监视网站的所有区域（"报表" 区域除外）的域用户组。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong>帮助台角色域组</strong></p></td>
   <td align="left"><p>其成员有权访问 <strong> </strong> 管理和监视网站的 "管理 TPM" 和 " <strong> 驱动器恢复" 区域的域用户组 </strong> 。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong>使用 System Center Configuration Manager 集成</strong></p></td>
   <td align="left"><p>如果你正在通过 Configuration Manager 集成拓扑配置 MBAM，请选中此复选框。 选中此复选框将使除 "恢复审核报告" 之外的所有报告显示在 Configuration Manager 中，而不是在 "管理和监视" 网站中显示。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong>报告角色域组</strong></p></td>
   <td align="left"><p>其成员对管理和监视网站的 "报告" 区域具有只读访问权限的域用户组。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong>SQL Server Reporting Services URL</strong></p></td>
   <td align="left"><p>配置了 MBAM 报表的 SSRS 服务器的 URL。</p>
   <p>报表 Url 的示例：</p>
   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left">主机名的类型</th>
   <th align="left">示例</th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p>具有完全限定的域名的示例</p></td>
   <td align="left"><p><a href="https://MyReportServer.Contoso.com/ReportServer" data-raw-source="https://MyReportServer.Contoso.com/ReportServer">https://MyReportServer.Contoso.com/ReportServer</a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>带有自定义主机名的示例</p></td>
   <td align="left"><p><a href="https://MyReportServer/ReportServer" data-raw-source="https://MyReportServer/ReportServer">https://MyReportServer/ReportServer</a></p></td>
   </tr>
   </tbody>
   </table>
   <p> </p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong>虚拟目录</strong></p></td>
   <td align="left"><p>管理和监视网站的虚拟目录。 此名称对应于服务器上网站的物理目录，并附加到网站的主机名称，例如：</p>
   <p>http （s）：// &lt; <em> 主机名 </em> &gt; ： &lt; <em> 端口 </em> &gt; /HelpDesk/</p>
   <p>如果不指定虚拟目录， <strong> 将使用值帮助台 </strong> 。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong>数据迁移角色域组 </strong> （可选）</p></td>
   <td align="left"><p>其成员有权使用 Write Mbam * 信息 Cmdlet 来通过此终结点写入恢复信息的域用户组。</p></td>
   </tr>
   </tbody>
   </table>



2. 使用以下说明在向导中输入字段值以配置自助服务门户。

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
   <td align="left"><p><strong>虚拟目录</strong></p></td>
   <td align="left"><p>Web 应用程序的虚拟目录。 此名称对应于服务器上网站的物理目录，并附加到网站的主机名称，例如：</p>
   <p>http （s）：// &lt; <em> 主机名 </em> &gt; ： &lt; <em> 端口 </em> &gt; /SelfService/</p>
   <p>如果不指定虚拟目录， <strong> </strong> 将使用值 SelfService。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>公司名称</p></td>
   <td align="left"><p>为自助服务门户指定公司名称，例如：</p>
   <p>Contoso IT</p>
   <p>此公司名称由所有自助门户用户查看。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>帮助台 URL 文本</p></td>
   <td align="left"><p>指定将用户定向到组织的帮助台网站的文本语句，例如：</p>
   <p>联系支持人员或 IT 部门</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>帮助台 URL</p></td>
   <td align="left"><p>指定组织的帮助程序网站的 URL，例如：</p>
   <p>http （s）：// &lt; <em> companyHelpdeskURL</em>&gt;/</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>通知文本文件</p></td>
   <td align="left"><p>选择包含要在自助服务门户登录页面上向用户显示的通知的文件。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>不向用户显示通知文本</p></td>
   <td align="left"><p>选中此复选框以指定不向用户显示声明文本。</p></td>
   </tr>
   </tbody>
   </table>



3. 完成输入后，单击 "**下一步**"。

   向导检查是否满足 web 应用程序的所有先决条件。

4. 单击**下一步**以继续。

5. 在 "**摘要**" 页面上，查看将添加的功能。

   **注意**  
   若要为您所创建的条目创建 Windows PowerShell 脚本，请单击 "**导出 PowerShell 脚本**" 并保存脚本。



6. 单击 "**添加**" 以将 web 应用程序添加到服务器，然后单击 "**关闭**"。

   若要通过添加自定义声明文本、公司名称、指向详细信息的指针自定义自助服务门户，请参阅[自定义组织的自助服务门户](customizing-the-self-service-portal-for-your-organization.md)。

**如果客户端计算机无法访问 CDN，则配置自助服务门户**

1.  确定你是否正在运行 Microsoft BitLocker 管理和监视（MBAM） 2.5 SP1。 如果是，则不执行任何操作。 您的自助服务门户配置已完成。

    **注意**  
    Microsoft BitLocker 管理和监视（MBAM） 2.5 SP1 在安装程序中安装 JavaScript 文件，因此无需连接到 Microsoft Ajax 内容传递网络即可配置自助服务门户。 只有在 SP1 之前使用版本的 Microsoft BitLocker 管理和监视（MBAM）2.5 时，才需要执行以下步骤。



2.  确定客户端计算机是否有权访问 Microsoft Ajax 内容交付网络（CDN）。

    CDN 为自助服务门户提供对某些 JavaScript 文件所需的访问权限。 如果在客户端计算机无法访问 CDN 时未配置自助服务门户，则仅显示公司名称和用于登录的最终用户帐户。 将不会显示任何错误消息。

3.  执行下列操作之一：

    -   如果你的客户端计算机有权访问 CDN，请执行任何操作。 您的自助服务门户配置已完成。

    -   如果客户端计算机不具有 CDN 的访问权限，请完成在[客户端计算机无法访问 Microsoft 内容传递网络时如何配置自助服务门户](how-to-configure-the-self-service-portal-when-client-computers-cannot-access-the-microsoft-content-delivery-network.md)的步骤。


## 相关主题


[服务器事件日志](server-event-logs.md)

[配置 MBAM 2.5 服务器功能](configuring-the-mbam-25-server-features.md)

[如何在客户端计算机无法访问 Microsoft 内容交付网络时配置自助服务门户](how-to-configure-the-self-service-portal-when-client-computers-cannot-access-the-microsoft-content-delivery-network.md)

[为组织自定义自助服务门户](customizing-the-self-service-portal-for-your-organization.md)

[验证 MBAM 2.5 服务器功能配置](validating-the-mbam-25-server-feature-configuration.md)



## 已获得 MBAM 的建议？
- 在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。 
- 对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。 





