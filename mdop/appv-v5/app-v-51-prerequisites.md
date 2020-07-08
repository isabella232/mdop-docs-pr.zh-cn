---
title: App-V 5.1 先决条件
description: App-V 5.1 先决条件
author: dansimp
ms.assetid: 1bfa03c1-a4ae-45ec-8a2b-b10c2b94bfb0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 24a74d8f8d7148cdb6c32bcafa87f479d24305af
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798621"
---
# App-V 5.1 先决条件


在安装 Microsoft Application Virtualization （App-v）5.1 之前，请确保已安装以下所有必需的必备软件。

有关支持的操作系统和 app-v Server、Sequencer 和客户端的硬件要求的列表，请参阅[App v 5.1 支持的配置](app-v-51-supported-configurations.md)。

## 在每个操作系统上预安装的软件的摘要


下表显示了已针对不同操作系统安装的软件。

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
<td align="left"><p>Windows 10</p></td>
<td align="left"><p>已安装所有必备软件。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows 8.1</p></td>
<td align="left"><p>已安装所有必备软件。</p>
<div class="alert">
<strong>注意</strong><br/><p>如果你运行的是 Windows 8，请在使用 app-v 5.1 之前升级到 Windows 8.1。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server 2012</p></td>
<td align="left"><p>已安装以下必备软件：</p>
<ul>
<li><p>Microsoft .NET Framework 4。5</p></li>
<li><p>Windows PowerShell 3。0</p>
<div class="alert">
<strong>注意</strong><br/><p>安装 PowerShell 3.0 需要重新启动。</p>
</div>
<div>

</div></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>Windows 7</p></td>
<td align="left"><p>尚未安装必备软件。 必须先安装它，然后才能安装 App-v。</p></td>
</tr>
</tbody>
</table>



## App-v 服务器必备软件


为 App-v 5.1 服务器组件安装所需的必备软件。

### 开始之前需要了解的内容

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p>用于安装 app-v 服务器的帐户</p></td>
<td align="left"><p>用于安装 app-v Server 组件的帐户必须具有：</p>
<ul>
<li><p>要在其上安装组件的计算机上的管理员权限。</p></li>
<li><p>查询 Active Directory 域服务的功能。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>端口和防火墙</p></td>
<td align="left"><ul>
<li><p>指定将托管每个组件的端口。</p></li>
<li><p>添加关联的防火墙规则以允许传入请求到指定的端口。</p></li>
</ul>
<p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>Web 分布式创作和版本控制（WebDAV）</p></td>
<td align="left"><p>自动为管理服务禁用 WebDAV。</p></td>
</tr>
<tr class="even">
<td align="left"><p>支持的部署方案</p></td>
<td align="left"><ul>
<li><p>一个独立部署，其中所有组件都部署在同一台服务器上。</p></li>
<li><p>分布式部署。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>不支持的部署方案</p></td>
<td align="left"><ul>
<li><p>在同一台服务器上安装多个 App-v Server 版本的并行实例。</p></li>
<li><p>在运行服务器核心或域控制器的计算机上安装 app-v 服务器组件。</p></li>
</ul></td>
</tr>
</tbody>
</table>



### 管理服务器必备软件

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">先决条件和必需设置</th>
<th align="left">详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>SQL Server 支持的版本</p></td>
<td align="left"><p>有关支持的版本，请参阅 <a href="app-v-51-supported-configurations.md" data-raw-source="[App-V 5.1 Supported Configurations](app-v-51-supported-configurations.md)"> App-V 5.1 支持的配置 </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="https://www.microsoft.com//download/details.aspx?id=40773" data-raw-source="[Microsoft .NET Framework 4.5.1 (Web Installer)](https://www.microsoft.com//download/details.aspx?id=40773)">Microsoft .NET Framework 4.5.1 （Web 安装程序）</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="https://www.microsoft.com/download/details.aspx?id=34595" data-raw-source="[Windows PowerShell 3.0](https://www.microsoft.com/download/details.aspx?id=34595)">Windows PowerShell 3。0</a></p></td>
<td align="left"><p>安装 PowerShell 3.0 需要重新启动。</p></td>
</tr>
<tr class="even">
<td align="left"><p>下载并安装 <a href="https://support.microsoft.com/kb/2533623" data-raw-source="[KB2533623](https://support.microsoft.com/kb/2533623)"> KB2533623</a></p></td>
<td align="left"><p>仅适用于 Windows 7。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="https://www.microsoft.com/download/details.aspx?id=40784" data-raw-source="[Visual C++ Redistributable Packages for Visual Studio 2013](https://www.microsoft.com/download/details.aspx?id=40784)">Visual Studio 2013 的 visual c + + 可再发行程序包</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>64位 ASP.NET 注册</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server Web 服务器角色</p></td>
<td align="left"><p>此角色必须添加到管理服务器支持的服务器操作系统。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Web 服务器（IIS）管理工具</p></td>
<td align="left"><p>单击 " <strong> IIS 管理脚本和工具" </strong> 。</p></td>
</tr>
<tr class="odd">
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
</ul>
<p><strong>管理工具：</strong></p>
<ul>
<li><p>IIS 管理控制台</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>默认安装位置</p></td>
<td align="left"><p>%PROGRAMFILES%\Microsoft 应用程序虚拟化服务器</p></td>
</tr>
<tr class="odd">
<td align="left"><p>管理数据库的位置</p></td>
<td align="left"><p>SQL Server 数据库名称、SQL Server 数据库实例名称和数据库名称。</p></td>
</tr>
<tr class="even">
<td align="left"><p>管理控制台和管理数据库权限</p></td>
<td align="left"><p>部署完成后可以访问管理控制台和数据库的用户或组。 只有这些用户或组才能访问管理控制台和数据库，除非使用管理控制台添加其他管理员。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>管理服务网站名称</p></td>
<td align="left"><p>管理控制台网站的名称。</p></td>
</tr>
<tr class="even">
<td align="left"><p>管理服务端口绑定</p></td>
<td align="left"><p>管理服务的唯一端口号。 此端口不能由计算机上的另一个进程使用。</p></td>
</tr>
</tbody>
</table>



**重要提示**  
必须在打开 Web 管理控制台的浏览器上启用 JavaScript。



### 管理服务器数据库必备软件

只有在使用 app-v 5.1 管理服务器时，才需要管理数据库。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">先决条件和必需设置</th>
<th align="left">详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><a href="https://www.microsoft.com//download/details.aspx?id=40773" data-raw-source="[Microsoft .NET Framework 4.5.1 (Web Installer)](https://www.microsoft.com//download/details.aspx?id=40773)">Microsoft .NET Framework 4.5.1 （Web 安装程序）</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="https://www.microsoft.com/download/details.aspx?id=40784" data-raw-source="[Visual C++ Redistributable Packages for Visual Studio 2013](https://www.microsoft.com/download/details.aspx?id=40784)">Visual Studio 2013 的 visual c + + 可再发行程序包</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>默认安装位置</p></td>
<td align="left"><p>%PROGRAMFILES%\Microsoft 应用程序虚拟化服务器</p></td>
</tr>
<tr class="even">
<td align="left"><p>自定义 SQL Server 实例名称（如果适用）</p></td>
<td align="left"><p>要使用的格式： <strong> INSTANCENAME</strong></p>
<p>此格式基于安装位于本地计算机上的假设。</p>
<p>如果指定 SVR\INSTANCE 格式的名称 <strong> </strong> ，安装将失败。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>自定义数据库名称（如果适用）</p></td>
<td align="left"><p>唯一的数据库名称。</p>
<p>默认： AppVManagement</p></td>
</tr>
<tr class="even">
<td align="left"><p>管理服务器位置</p></td>
<td align="left"><p>部署管理服务器的计算机帐户。</p>
<p>要使用的格式： Domain\MachineAccount</p></td>
</tr>
<tr class="odd">
<td align="left"><p>管理服务器安装管理员</p></td>
<td align="left"><p>用于安装管理服务器的帐户。</p>
<p>要使用的格式： Domain\AdministratorLoginName</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft SQL Server 服务代理</p></td>
<td align="left"><p>配置管理数据库计算机，以便自动重新启动 Microsoft SQL Server 代理服务。 有关说明，请参阅 <a href="https://technet.microsoft.com/magazine/gg313742.aspx" data-raw-source="[Configure SQL Server Agent to Restart Services Automatically](https://technet.microsoft.com/magazine/gg313742.aspx)"> 将 SQL Server 代理配置为自动重新启动服务 </a> 。</p></td>
</tr>
</tbody>
</table>



### 发布服务器必备软件

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">先决条件和必需设置</th>
<th align="left">详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><a href="https://www.microsoft.com//download/details.aspx?id=40773" data-raw-source="[Microsoft .NET Framework 4.5.1 (Web Installer)](https://www.microsoft.com//download/details.aspx?id=40773)">Microsoft .NET Framework 4.5.1 （Web 安装程序）</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="https://www.microsoft.com/download/details.aspx?id=40784" data-raw-source="[Visual C++ Redistributable Packages for Visual Studio 2013](https://www.microsoft.com/download/details.aspx?id=40784)">Visual Studio 2013 的 visual c + + 可再发行程序包</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>64位 ASP.NET 注册</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server Web 服务器角色</p></td>
<td align="left"><p>此角色必须添加到管理服务器支持的服务器操作系统。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Web 服务器（IIS）管理工具</p></td>
<td align="left"><p>单击 " <strong> IIS 管理脚本和工具" </strong> 。</p></td>
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
</ul>
<p><strong>管理工具：</strong></p>
<ul>
<li><p>IIS 管理控制台</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>默认安装位置</p></td>
<td align="left"><p>%PROGRAMFILES%\Microsoft 应用程序虚拟化服务器</p></td>
</tr>
<tr class="even">
<td align="left"><p>管理服务 URL</p></td>
<td align="left"><p>App-v 管理服务的 URL。 这是发布服务器与之通信的端口。</p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">安装体系结构</th>
<th align="left">要用于 URL 的格式</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>管理服务器和发布服务器安装在同一台服务器上</p></td>
<td align="left"><p><a href="http://localhost:12345" data-raw-source="http://localhost:12345">http://localhost:12345</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>管理服务器和发布服务器安装在不同的服务器上</p></td>
<td align="left"><p><a href="http://MyAppvServer.MyDomain.com" data-raw-source="http://MyAppvServer.MyDomain.com">http://MyAppvServer.MyDomain.com</a></p></td>
</tr>
</tbody>
</table>
<p> </p>
<p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>发布服务网站名称</p></td>
<td align="left"><p>发布网站的名称。</p></td>
</tr>
<tr class="even">
<td align="left"><p>发布服务端口绑定</p></td>
<td align="left"><p>发布服务的唯一端口号。 此端口不能由计算机上的另一个进程使用。</p></td>
</tr>
</tbody>
</table>



### 报告服务器必备软件

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">先决条件和必需设置</th>
<th align="left">详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>SQL Server 支持的版本</p></td>
<td align="left"><p>有关支持的版本，请参阅 <a href="app-v-51-supported-configurations.md" data-raw-source="[App-V 5.1 Supported Configurations](app-v-51-supported-configurations.md)"> App-V 5.1 支持的配置 </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="https://www.microsoft.com//download/details.aspx?id=40773" data-raw-source="[Microsoft .NET Framework 4.5.1 (Web Installer)](https://www.microsoft.com//download/details.aspx?id=40773)">Microsoft .NET Framework 4.5.1 （Web 安装程序）</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="https://www.microsoft.com/download/details.aspx?id=40784" data-raw-source="[Visual C++ Redistributable Packages for Visual Studio 2013](https://www.microsoft.com/download/details.aspx?id=40784)">Visual Studio 2013 的 visual c + + 可再发行程序包</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>64位 ASP.NET 注册</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server Web 服务器角色</p></td>
<td align="left"><p>此角色必须添加到管理服务器支持的服务器操作系统。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Web 服务器（IIS）管理工具</p></td>
<td align="left"><p>单击 " <strong> IIS 管理脚本和工具" </strong> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Web 服务器角色服务</p></td>
<td align="left"><p>若要降低将不受欢迎或恶意数据发送到报告服务器的风险，应限制每个公司安全策略对报告 Web 服务的访问权限。</p>
<p><strong>常见的 HTTP 功能：</strong></p>
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
</ul>
<p><strong>管理工具：</strong></p>
<ul>
<li><p>IIS 管理控制台</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>默认安装位置</p></td>
<td align="left"><p>%PROGRAMFILES%\Microsoft 应用程序虚拟化服务器</p></td>
</tr>
<tr class="odd">
<td align="left"><p>报告服务网站名称</p></td>
<td align="left"><p>报告网站的名称。</p></td>
</tr>
<tr class="even">
<td align="left"><p>报告服务端口绑定</p></td>
<td align="left"><p>报告服务的唯一端口号。 此端口不能由计算机上的另一个进程使用。</p></td>
</tr>
</tbody>
</table>



### 报告数据库必备软件

只有在使用 App-v 5.1 报告服务器时，才需要报告数据库。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">先决条件和必需设置</th>
<th align="left">详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><a href="https://www.microsoft.com//download/details.aspx?id=40773" data-raw-source="[Microsoft .NET Framework 4.5.1 (Web Installer)](https://www.microsoft.com//download/details.aspx?id=40773)">Microsoft .NET Framework 4.5.1 （Web 安装程序）</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="https://www.microsoft.com/download/details.aspx?id=40784" data-raw-source="[Visual C++ Redistributable Packages for Visual Studio 2013](https://www.microsoft.com/download/details.aspx?id=40784)">Visual Studio 2013 的 visual c + + 可再发行程序包</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>默认安装位置</p></td>
<td align="left"><p>%PROGRAMFILES%\Microsoft 应用程序虚拟化服务器</p></td>
</tr>
<tr class="even">
<td align="left"><p>自定义 SQL Server 实例名称（如果适用）</p></td>
<td align="left"><p>要使用的格式： <strong> INSTANCENAME</strong></p>
<p>此格式基于安装位于本地计算机上的假设。</p>
<p>如果指定 SVR\INSTANCE 格式的名称 <strong> </strong> ，安装将失败。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>自定义数据库名称（如果适用）</p></td>
<td align="left"><p>唯一的数据库名称。</p>
<p>默认： AppVReporting</p></td>
</tr>
<tr class="even">
<td align="left"><p>报表服务器位置</p></td>
<td align="left"><p>要在其上部署报告服务器的计算机帐户。</p>
<p>要使用的格式： Domain\MachineAccount</p></td>
</tr>
<tr class="odd">
<td align="left"><p>报表服务器安装管理员</p></td>
<td align="left"><p>用于安装报表服务器的帐户。</p>
<p>要使用的格式： Domain\AdministratorLoginName</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft SQL Server 服务和 Microsoft SQL Server 服务代理</p></td>
<td align="left"><p>将这些服务配置为与有权访问查询 AD DS 的用户帐户相关联。</p></td>
</tr>
</tbody>
</table>



## App-v 客户端必备软件


为 App-v 客户端安装以下必备软件。

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
<td align="left"><p><a href="https://www.microsoft.com//download/details.aspx?id=40773" data-raw-source="[Microsoft .NET Framework 4.5.1 (Web Installer)](https://www.microsoft.com//download/details.aspx?id=40773)">Microsoft .NET Framework 4.5.1 （Web 安装程序）</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="https://www.microsoft.com/download/details.aspx?id=34595" data-raw-source="[Windows PowerShell 3.0](https://www.microsoft.com/download/details.aspx?id=34595)">Windows PowerShell 3。0</a></p>
<p></p></td>
<td align="left"><p>安装 PowerShell 3.0 需要重新启动。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="https://support.microsoft.com/kb/2533623" data-raw-source="[KB2533623](https://support.microsoft.com/kb/2533623)">KB2533623</a></p></td>
<td align="left"><p>仅适用于 Windows 7：下载并安装 KB。</p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="https://www.microsoft.com/download/details.aspx?id=40784" data-raw-source="[Visual C++ Redistributable Packages for Visual Studio 2013](https://www.microsoft.com/download/details.aspx?id=40784)">Visual Studio 2013 的 visual c + + 可再发行程序包</a></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>



## 远程桌面服务客户端必备软件


为 App-v 远程桌面服务客户端安装以下必备软件。

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
<td align="left"><p><a href="https://www.microsoft.com//download/details.aspx?id=40773" data-raw-source="[Microsoft .NET Framework 4.5.1 (Web Installer)](https://www.microsoft.com//download/details.aspx?id=40773)">Microsoft .NET Framework 4.5.1 （Web 安装程序）</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="https://www.microsoft.com/download/details.aspx?id=34595" data-raw-source="[Windows PowerShell 3.0](https://www.microsoft.com/download/details.aspx?id=34595)">Windows PowerShell 3。0</a></p>
<p></p></td>
<td align="left"><p>安装 PowerShell 3.0 需要重新启动。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="https://support.microsoft.com/kb/2533623" data-raw-source="[KB2533623](https://support.microsoft.com/kb/2533623)">KB2533623</a></p></td>
<td align="left"><p>仅适用于 Windows 7：下载并安装 KB。</p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="https://www.microsoft.com/download/details.aspx?id=40784" data-raw-source="[Visual C++ Redistributable Packages for Visual Studio 2013](https://www.microsoft.com/download/details.aspx?id=40784)">Visual Studio 2013 的 visual c + + 可再发行程序包</a></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>



## Sequencer 必备软件


**安装先决条件之前应了解的事项：**

-   最佳做法：运行 Sequencer 的计算机应具有与将运行虚拟应用程序的计算机相同的硬件和软件配置。

-   排序过程占用大量资源，因此请确保运行排序器的计算机具有大量内存、快速处理器和快速硬盘。 本地安装的应用程序的系统要求不能超过 Sequencer 的系统要求。 有关详细信息，请参阅[App-V 5.1 支持的配置](app-v-51-supported-configurations.md)。

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
<td align="left"><p><a href="https://www.microsoft.com//download/details.aspx?id=40773" data-raw-source="[Microsoft .NET Framework 4.5.1 (Web Installer)](https://www.microsoft.com//download/details.aspx?id=40773)">Microsoft .NET Framework 4.5.1 （Web 安装程序）</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="https://www.microsoft.com/download/details.aspx?id=34595" data-raw-source="[Windows PowerShell 3.0](https://www.microsoft.com/download/details.aspx?id=34595)">Windows PowerShell 3。0</a></p>
<p></p></td>
<td align="left"><p>安装 PowerShell 3.0 需要重新启动。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="https://support.microsoft.com/kb/2533623" data-raw-source="[KB2533623](https://support.microsoft.com/kb/2533623)">KB2533623</a></p></td>
<td align="left"><p>仅适用于 Windows 7：下载并安装 KB。</p></td>
</tr>
</tbody>
</table>








## 相关主题


[规划 App-V 5.1](planning-for-app-v-51.md)

[App-V 5.1 支持的配置](app-v-51-supported-configurations.md)









