---
title: App-V 5.0 先决条件
description: App-V 5.0 先决条件
author: dansimp
ms.assetid: 9756b571-c785-4ce6-a95c-d4e134e89429
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 176c9729d8c909325c6d6694e024938d9ce9df53
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798639"
---
# App-V 5.0 先决条件

开始使用 Microsoft Application Virtualization （App-v）5.0 安装程序之前，应确保已满足安装该产品的先决条件。 本主题包含的信息可帮助你成功计划在部署 app-v 5.0 功能之前准备你的计算环境。

> [!Important]
> **本文中的先决条件仅适用于 app-v 5.0**。 有关适用于 app-v 5.0 Service Pack 的其他先决条件，请参阅以下网页：

-   [App-V 5.0 SP1 中的新增功能](whats-new-in-app-v-50-sp1.md)

-   [关于 App-V 5.0 SP2](about-app-v-50-sp2.md)

-   [App-V 5.0 SP3 先决条件](app-v-50-sp3-prerequisites.md)

下表列出了与特定操作系统有关的先决条件信息。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">操作系统</th>
<th align="left">先决条件说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>正在运行的计算机：</p>
<ul>
<li><p>Windows 8</p></li>
<li><p>Windows Server 2012</p></li>
</ul></td>
<td align="left"><p>已安装以下先决条件：</p>
<ul>
<li><p>Microsoft .NET Framework 4.5-不需要 Microsoft .NET Framework 4</p></li>
<li><p>Windows PowerShell 3。0</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>正在运行的计算机：</p>
<ul>
<li><p>Windows 7</p></li>
<li><p>Windows Server 2008</p></li>
</ul></td>
<td align="left"><p>您可能想要下载以下 KB：</p>
<p><a href="https://support.microsoft.com/kb/2533623" data-raw-source="[Microsoft Security Advisory: Insecure library loading could allow remote code execution](https://support.microsoft.com/kb/2533623)">Microsoft 安全通报：不安全的库加载可能允许远程代码执行</a></p>
<p>请务必检查已取代的后续 KBs，并注意某些 KBs 可能需要你卸载以前的更新。</p></td>
</tr>
</tbody>
</table>

## App-v 5.0 的安装先决条件

> [!Note]  
> 已为运行 Windows 8 的计算机安装了以下先决条件。

每个 app-v 5.0 功能都具有特定的先决条件，必须先满足这些先决条件，然后才能成功安装 app-v 5.0 功能。

### App-v 5.0 客户端的先决条件

下表列出了 app-v 5.0 客户端的安装先决条件：

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
<td align="left"><p><strong>软件要求</strong></p></td>
<td align="left"><ul>
<li><p><a href="https://www.microsoft.com/download/details.aspx?id=17718" data-raw-source="[Microsoft .NET Framework 4 (Full Package)](https://www.microsoft.com/download/details.aspx?id=17718)">Microsoft .NET Framework 4 （完整程序包）</p></li>
<li><p><a href="https://www.microsoft.com/download/details.aspx?id=34595" data-raw-source="[Windows PowerShell 3.0](https://www.microsoft.com/download/details.aspx?id=34595)">Windows PowerShell 3。0</a></p>
<p></p>
<div class="alert">
<strong>注意</strong><br/><p>安装 PowerShell 3.0 需要重新启动。</p>
</div>
<div>

</div></li>
<li><p>下载并安装 <a href="https://support.microsoft.com/kb/2533623" data-raw-source="[KB2533623](https://support.microsoft.com/kb/2533623)"> KB2533623</a></p>
<p></p>
<div class="alert">
<strong>重要提示</strong><br/><p>你可以下载并安装以前的知识库文章。 但是，它可能已替换为更新的版本。</p>
</div>
<div>

</div></li>
<li><p>客户端安装程序（.exe）将检测是否需要安装以下必备组件，它将相应地执行此操作：</p>
<p></p>
<ul>
<li><p><a href="https://www.microsoft.com/download/details.aspx?id=40784" data-raw-source="[Visual C++ Redistributable Packages for Visual Studio 2013](https://www.microsoft.com/download/details.aspx?id=40784)">Visual Studio 2013 的 visual c + + 可再发行程序包</a></p>
<p>只有安装了应用程序虚拟化 5.0 SP2 或更高版本的修补程序包4时，才需要此先决条件。</p>
<p></p></li>
<li><p><a href="https://www.microsoft.com/download/details.aspx?id=26999" data-raw-source="[The Microsoft Visual C++ 2010 Redistributable](https://www.microsoft.com/download/details.aspx?id=26999)">Microsoft Visual c + + 2010 可再发行组件</a></p>
<p></p></li>
<li><p><a href="https://www.microsoft.com/download/details.aspx?id=5638" data-raw-source="[Microsoft Visual C++ 2005 SP1 Redistributable Package (x86)](https://www.microsoft.com/download/details.aspx?id=5638)">Microsoft Visual c + + 2005 SP1 可再发行程序包（x86）</a></p></li>
</ul></li>
</ul></td>
</tr>
</tbody>
</table>

### App-v 5.0 远程桌面服务客户端的先决条件

> [!Note]  
> 已为运行 Windows Server 2012 的计算机安装以下先决条件。

下表列出了 app-v 5.0 远程桌面服务客户端的安装先决条件：

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
<td align="left"><p><strong>软件要求</strong></p></td>
<td align="left"><ul>
<li><p><a href="https://www.microsoft.com/download/details.aspx?id=17718" data-raw-source="[Microsoft.NET Framework 4 (Full Package)](https://www.microsoft.com/download/details.aspx?id=17718)">Microsoft.NET Framework 4 （完整程序包）</a></p></li>
<li><p><a href="https://www.microsoft.com/download/details.aspx?id=34595" data-raw-source="[Windows PowerShell 3.0](https://www.microsoft.com/download/details.aspx?id=34595)">Windows PowerShell 3。0</a></p>
<p></p>
<div class="alert">
<strong>注意</strong><br/><p>安装 PowerShell 3.0 需要重新启动。</p>
</div>
<div>

</div></li>
<li><p>下载并安装 <a href="https://go.microsoft.com/fwlink/?LinkId=286102" data-raw-source="[KB2533623](https://go.microsoft.com/fwlink/?LinkId=286102 )"> KB2533623</a></p>
<p></p>
<div class="alert">
<strong>重要提示</strong><br/><p>你可以下载并安装以前的知识库文章。 但是，它可能已替换为更新的版本。</p>
</div>
<div>

</div></li>
<li><p>客户端（.exe）安装程序将检测是否需要安装以下系统必备组件，它将相应地执行此操作：</p>
<p></p>
<ul>
<li><p><a href="https://www.microsoft.com/download/details.aspx?id=40784" data-raw-source="[Visual C++ Redistributable Packages for Visual Studio 2013](https://www.microsoft.com/download/details.aspx?id=40784)">Visual Studio 2013 的 visual c + + 可再发行程序包</a></p>
<p>只有在安装了应用程序虚拟化 5.0 SP2 或更高版本的修补程序包4时，才需要此先决条件。</p>
<p></p></li>
<li><p><a href="https://www.microsoft.com/download/details.aspx?id=26999" data-raw-source="[The Microsoft Visual C++ 2010 Redistributable](https://www.microsoft.com/download/details.aspx?id=26999)">Microsoft Visual c + + 2010 可再发行组件</a></p>
<p></p></li>
<li><p><a href="https://www.microsoft.com/download/details.aspx?id=5638" data-raw-source="[Microsoft Visual C++ 2005 SP1 Redistributable Package (x86)](https://www.microsoft.com/download/details.aspx?id=5638)">Microsoft Visual c + + 2005 SP1 可再发行程序包（x86）</a></p></li>
</ul></li>
</ul></td>
</tr>
</tbody>
</table>

### App-v 5.0 Sequencer 的先决条件

> [!Note]
> 已为运行 Windows 8 和 Windows Server 2012 的计算机安装了以下先决条件。

下表列出了 app-v 5.0 Sequencer 的安装先决条件。 如果可能，运行 Sequencer 的计算机应具有与将运行虚拟应用程序的计算机相同的硬件和软件配置。

> [!Note]  
> 如果本地安装的应用程序的系统要求超过了 Sequencer 的要求，则必须满足该应用程序的要求。 此外，由于排序过程会占用大量系统资源，因此我们建议运行排序器的计算机具有大量内存、快速处理器和快速硬盘。 有关详细信息，请参阅[应用 V 5.0 支持的配置](app-v-50-supported-configurations.md)。

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
<td align="left"><p><strong>软件要求</strong></p></td>
<td align="left"><ul>
<li><p><a href="https://www.microsoft.com/download/details.aspx?id=40784" data-raw-source="[Visual C++ Redistributable Packages for Visual Studio 2013](https://www.microsoft.com/download/details.aspx?id=40784)">Visual Studio 2013 的 visual c + + 可再发行程序包</a></p>
<p>只有当你已安装应用程序虚拟化 5.0 SP2 的修补程序包4时，才需要此先决条件。</p>
<p></p></li>
<li><p><a href="https://www.microsoft.com/download/details.aspx?id=17718" data-raw-source="[Microsoft .NET Framework 4 (Full Package)](https://www.microsoft.com/download/details.aspx?id=17718)">Microsoft .NET Framework 4 （完整程序包）</a></p>
<p></p></li>
<li><p><a href="https://www.microsoft.com/download/details.aspx?id=34595" data-raw-source="[Windows PowerShell 3.0](https://www.microsoft.com/download/details.aspx?id=34595)">Windows PowerShell 3。0</a></p>
<p></p></li>
<li><p>下载并安装 <a href="https://support.microsoft.com/kb/2533623" data-raw-source="[KB2533623](https://support.microsoft.com/kb/2533623)"> KB2533623</a></p>
<p></p></li>
<li><p>对于运行 Microsoft Windows Server 2008 R2 SP1 的计算机，请下载并安装 <a href="https://go.microsoft.com/fwlink/?LinkId=286102" data-raw-source="[KB2533623](https://go.microsoft.com/fwlink/?LinkId=286102 )"> KB2533623</a></p>
<p></p>
<div class="alert">
<strong>重要提示</strong><br/><p>你可以下载并安装以前的其中一个知识库文章。 但是，它们可能已替换为更新的版本。</p>
</div>
<div>

</div></li>
</ul></td>
</tr>
</tbody>
</table>

### App-v 5.0 服务器的先决条件

> [!Note]
> 已为运行 Windows Server 2012 的计算机安装以下先决条件：

-   Microsoft .NET Framework 4.5。 这将消除 Microsoft .NET Framework 4 的要求。

-   Windows PowerShell 3。0

-   下载并安装[KB2533623](https://support.microsoft.com/kb/2533623) （https://support.microsoft.com/kb/2533623)

    > [!Important]
    > 您仍然可以下载安装以前的 KB。 但是，它可能已替换为更新的版本。

下表列出了 app-v 5.0 服务器的安装先决条件。 用于安装服务器组件的帐户必须具有要在其上安装的计算机的管理权限。 此帐户还必须能够查询 Active Directory 目录服务。 在安装和配置 App-v 5.0 服务器之前，必须指定将托管每个组件的端口。 你还必须添加关联的防火墙规则，以便允许将请求传入到指定的端口。

> [!Note]
> 自动为管理服务禁用 Web 分布式创作和版本控制（WebDAV）。

App-v 5.0 服务器支持独立部署，其中所有组件都部署在同一台服务器上，以及分布式部署。 根据用于部署 app-v 5.0 服务器的拓扑，你需要用于每个组件的数据会略微更改。

> [!Important]
> 不支持在运行任何以前版本或 app-v 组件的计算机上安装 app-v 5.0 服务器。 此外，也不支持在运行服务器 Core 或域控制器的计算机上安装服务器组件。

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
<td align="left"><p><strong>管理服务器</strong></p></td>
<td align="left"><ul>
<li><p><a href="https://www.microsoft.com/download/details.aspx?id=17718" data-raw-source="[Microsoft .NET Framework 4 (Full Package)](https://www.microsoft.com/download/details.aspx?id=17718)">Microsoft .NET Framework 4 （完整程序包）</a></p></li>
<li><p><a href="https://www.microsoft.com/download/details.aspx?id=34595" data-raw-source="[Windows PowerShell 3.0](https://www.microsoft.com/download/details.aspx?id=34595)">Windows PowerShell 3。0</a></p>
<div class="alert">
<strong>注意</strong><br/><p>安装 PowerShell 3.0 需要重新启动。</p>
</div>
<div>

</div></li>
<li><p>启用 IIS 角色且具有以下功能的 Windows Web 服务器： <strong> 常见 HTTP 功能 </strong> （静态内容和默认文档）、 <strong> 应用程序开发 </strong> （ASP.NET、.Net 扩展性、Isapi 扩展和 ISAPI 筛选器）、 <strong> 安全 </strong> （Windows 身份验证、请求筛选）、 <strong> 管理工具 </strong> （IIS 管理控制台）。</p></li>
<li><p>下载并安装 <a href="https://support.microsoft.com/kb/2533623" data-raw-source="[KB2533623](https://support.microsoft.com/kb/2533623)"> KB2533623</a></p>
<p></p>
<div class="alert">
<strong>重要提示</strong><br/><p>您仍然可以下载安装以前的 KB。 但是，它可能已替换为更新的版本。</p>
</div>
<div>

</div></li>
<li><p><a href="https://www.microsoft.com/download/details.aspx?id=13523" data-raw-source="[Microsoft Visual C++ 2010 SP1 Redistributable Package (x64)](https://www.microsoft.com/download/details.aspx?id=13523)">Microsoft Visual c + + 2010 SP1 可再发行程序包（x64）</a></p></li>
<li><p><a href="https://go.microsoft.com/fwlink/?LinkId=267110" data-raw-source="[Microsoft Visual C++ 2010 SP1 Redistributable Package (x86)](https://go.microsoft.com/fwlink/?LinkId=267110)">Microsoft Visual c + + 2010 SP1 可再发行程序包（x86）</a></p></li>
<li><p>64位 ASP.NET 注册</p></li>
</ul>
<p>App-v 5.0 服务器组件是依赖的，但它们具有不同的要求和必须部署的安装选项。 使用以下信息准备环境以运行 app-v 5.0 管理服务器。</p>
<ul>
<li><p>安装位置-默认情况下，此组件将安装到： <strong> %PROGRAMFILES%\Microsoft Application Virtualization 服务器 </strong> 。</p></li>
<li><p>App-v 5.0 管理数据库的位置-SQL Server 名称、SQL 实例名称、数据库名称。</p></li>
<li><p>App-v 5.0 管理控制台的访问权限-这是在部署结束时应授予其访问管理控制台的访问权限的用户或组。 部署后，只有这些用户才可以访问管理控制台，直到通过管理控制台添加其他管理员。</p>
<div class="alert">
<strong>注意</strong><br/><p>不支持安全组和单个用户。 必须指定 AD DS 组。</p>
</div>
<div>

</div></li>
<li><p>App-v 5.0 管理服务网站名称–指定网站的名称或使用默认名称。</p></li>
<li><p>App-v 5.0 管理服务端口绑定-这应该是计算机上的其他网站未使用的唯一端口号。</p></li>
<li><p>支持 Microsoft Silverlight-必须先安装 Microsoft Silverlight，然后才能使用管理控制台。 尽管这不是部署的必要条件，但服务器必须能够支持 Microsoft Silverlight。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><strong>管理数据库</strong></p></td>
<td align="left"><p></p>
<div class="alert">
<strong>注意</strong><br/><p>只有在使用 App-v 5.0 管理服务器时才需要使用该数据库。</p>
</div>
<div>

</div>
<ul>
<li><p><a href="https://www.microsoft.com/download/details.aspx?id=17718" data-raw-source="[Microsoft .NET Framework 4 (Full Package)](https://www.microsoft.com/download/details.aspx?id=17718)">Microsoft .NET Framework 4 （完整程序包）</a></p></li>
<li><p><a href="https://go.microsoft.com/fwlink/?LinkId=267110" data-raw-source="[Microsoft Visual C++ 2010 SP1 Redistributable Package (x86)](https://go.microsoft.com/fwlink/?LinkId=267110)">Microsoft Visual c + + 2010 SP1 可再发行程序包（x86）</a></p></li>
</ul>
<p>App-v 5.0 服务器组件是依赖的，但它们具有不同的要求和必须部署的安装选项。 使用以下信息准备环境以运行 app-v 5.0 管理数据库。</p>
<ul>
<li><p>安装位置-默认情况下，此组件将安装到 <strong> %PROGRAMFILES%\Microsoft Application Virtualization 服务器 </strong> 。</p></li>
<li><p>自定义 SQL Server 实例名称（如果适用）-格式应为 <strong> INSTANCENAME </strong> ，因为安装假定它位于本地计算机上。 如果指定名称的格式如下所示，则 <strong> SVR\INSTANCE </strong> 将失败。</p></li>
<li><p>自定义 App-v 5.0 数据库名称（如果适用）-必须指定唯一的数据库名称。 管理数据库的默认值为 <strong> AppVManagement </strong> 。</p></li>
<li><p>App-v 5.0 管理服务器位置-指定部署管理服务器的计算机帐户。 应按以下格式指定 <strong> Domain\MachineAccount </strong> 。</p></li>
<li><p>App-v 5.0 管理服务器安装管理员-指定将用于安装 App-v 5.0 管理服务器的帐户。 应使用以下格式： <strong> Domain\AdministratorLoginName </strong> 。</p></li>
<li><p>Microsoft SQL Server 服务代理-配置运行 App-v 5.0 管理数据库的计算机，以便自动重新启动 Microsoft SQL Server 代理服务。 有关详细信息，请参阅 <a href="https://go.microsoft.com/fwlink/?LinkId=273725" data-raw-source="[Configure SQL Server Agent to Restart Services Automatically](https://go.microsoft.com/fwlink/?LinkId=273725)"> 将 SQL Server 代理配置为自动重启服务</a></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>报表服务器</strong></p></td>
<td align="left"><ul>
<li><p><a href="https://www.microsoft.com/download/details.aspx?id=17718" data-raw-source="[Microsoft .NET Framework 4 (Full Package)](https://www.microsoft.com/download/details.aspx?id=17718)">Microsoft .NET Framework 4 （完整程序包）</a></p></li>
<li><p><a href="https://go.microsoft.com/fwlink/?LinkId=267110" data-raw-source="[Microsoft Visual C++ 2010 SP1 Redistributable Package (x86)](https://go.microsoft.com/fwlink/?LinkId=267110)">Microsoft Visual c + + 2010 SP1 可再发行程序包（x86）</a></p></li>
<li><div class="alert">
<strong>注意</strong><br/><p>若要帮助降低向报表服务器发送不受欢迎或恶意数据的风险，应根据公司安全策略限制对报告 Web 服务的访问。</p>
</div>
<div>

</div>
<p>具有以下功能的具有 IIS 角色的 Windows Web 服务器： <strong> 常见 HTTP 功能 </strong> （静态内容和默认文档）、 <strong> 应用程序开发 </strong> （ASP.NET、.Net 扩展性、Isapi 扩展和 ISAPI 筛选器）、 <strong> 安全 </strong> （windows 身份验证、请求筛选）、 <strong> 安全 </strong> （windows 身份验证、请求筛选）、 <strong> 管理工具 </strong> （IIS 管理控制台）</p></li>
<li><p>64位 ASP.NET 注册</p></li>
<li><p>安装位置-默认情况下，此组件安装到 <strong> %PROGRAMFILES%\Microsoft Application Virtualization 服务器 </strong> 。</p></li>
<li><p>App-v 5.0 reporting services 网站名称-指定将使用的网站的名称或默认名称。</p></li>
<li><p>App-v 5.0 reporting service 端口绑定-这应该是计算机上运行的另一个网站尚未使用的唯一端口号。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><strong>报告数据库</strong></p></td>
<td align="left"><p></p>
<div class="alert">
<strong>注意</strong><br/><p>只有在使用 App-v 5.0 报告服务器时才需要使用该数据库。</p>
</div>
<div>

</div>
<ul>
<li><p><a href="https://www.microsoft.com/download/details.aspx?id=17718" data-raw-source="[Microsoft .NET Framework 4 (Full Package)](https://www.microsoft.com/download/details.aspx?id=17718)">Microsoft .NET Framework 4 （完整程序包）</a></p></li>
<li><p><a href="https://go.microsoft.com/fwlink/?LinkId=267110" data-raw-source="[Microsoft Visual C++ 2010 SP1 Redistributable Package (x86)](https://go.microsoft.com/fwlink/?LinkId=267110)">Microsoft Visual c + + 2010 SP1 可再发行程序包（x86）</a></p></li>
</ul>
<p>App-v 5.0 服务器组件是依赖的，但它们具有不同的要求和必须部署的安装选项。 使用以下信息准备环境以运行 app-v 5.0 报告数据库。</p>
<ul>
<li><p>安装位置-默认情况下，此组件将安装到 <strong> %PROGRAMFILES%\Microsoft Application Virtualization 服务器 </strong> 。</p></li>
<li><p>自定义 SQL Server 实例名称（如果适用）-格式应为 <strong> INSTANCENAME </strong> ，因为安装假定它位于本地计算机上。 如果指定名称的格式如下所示，则 <strong> SVR\INSTANCE </strong> 将失败。</p></li>
<li><p>自定义 App-v 5.0 数据库名称（如果适用）-必须指定唯一的数据库名称。 报告数据库的默认值为 <strong> AppVReporting </strong> 。</p></li>
<li><p>App-v 5.0 报告服务器位置-指定要在其上部署报告服务器的计算机帐户。 应按以下格式指定 <strong> Domain\MachineAccount </strong> 。</p></li>
<li><p>App-v 5.0 reporting server 安装管理员-指定将用于安装 app-v 5.0 报告服务器的帐户。 应使用以下格式： <strong> Domain\AdministratorLoginName </strong> 。</p></li>
<li><p>Microsoft SQL Server 服务和 Microsoft SQL Server 代理服务-这些服务必须与有权访问查询广告的用户帐户相关联。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>发布服务器</strong></p></td>
<td align="left"><ul>
<li><p><a href="https://www.microsoft.com/download/details.aspx?id=17718" data-raw-source="[Microsoft .NET Framework 4 (Full Package)](https://www.microsoft.com/download/details.aspx?id=17718)">Microsoft .NET Framework 4 （完整程序包）</a></p></li>
<li><p><a href="https://go.microsoft.com/fwlink/?LinkId=267110" data-raw-source="[Microsoft Visual C++ 2010 SP1 Redistributable Package (x86)](https://go.microsoft.com/fwlink/?LinkId=267110)">Microsoft Visual c + + 2010 SP1 可再发行程序包（x86）</a></p></li>
<li><p>具有以下功能的具有 IIS 角色的 Windows Web 服务器： <strong> 常见 HTTP 功能 </strong> （静态内容和默认文档）、 <strong> 应用程序开发 </strong> （ASP.NET、.Net 扩展性、Isapi 扩展和 ISAPI 筛选器）、 <strong> 安全 </strong> （windows 身份验证、请求筛选）、 <strong> 安全 </strong> （windows 身份验证、请求筛选）、 <strong> 管理工具 </strong> （IIS 管理控制台）</p></li>
<li><p>64位 ASP.NET 注册</p></li>
</ul>
<p>App-v 5.0 服务器组件是依赖的，但它们具有不同的要求和必须部署的安装选项。 使用以下信息准备环境以运行 app-v 5.0 发布服务器。</p>
<ul>
<li><p>安装位置-默认情况下，此组件安装到 <strong> %PROGRAMFILES%\Microsoft Application Virtualization 服务器 </strong> 。</p></li>
<li><p>App-v 5.0 管理服务 URL-指定 App-v 5.0 管理服务的 URL。 这是发布服务器与之通信的端口，应使用以下格式指定： <strong><a href="http://localhost:12345" data-raw-source="http://localhost:12345"> http://localhost:12345 </a></strong> 。</p></li>
<li><p>App-v 5.0 发布服务网站名称-指定将使用的网站的名称或默认名称。</p></li>
<li><p>App-v 5.0 发布服务端口绑定-这应该是计算机上运行的另一个网站尚未使用的唯一端口号。</p></li>
</ul></td>
</tr>
</tbody>
</table>

## 相关主题

[计划部署 App-V](planning-to-deploy-app-v.md)

[App-V 5.0 支持的配置](app-v-50-supported-configurations.md)
