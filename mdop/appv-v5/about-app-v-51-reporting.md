---
title: 关于 App-V 5.1 报告
description: 关于 App-V 5.1 报告
author: dansimp
ms.assetid: 385dca00-7178-4e35-8d86-c58867ebd65c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 827343d538238ca638b57a74ae5d2d74bc6c5968
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798674"
---
# 关于 App-V 5.1 报告

Microsoft Application Virtualization （App-v）5.1 包括一个内置的报告功能，可帮助你收集有关运行 app-v 5.1 客户端的计算机的信息以及有关虚拟应用程序包使用情况的信息。 你可以使用此信息从集中式数据库生成报表。

## <a href="" id="---------app-v-5-1-reporting-overview"></a> App-v 5.1 报告概述

以下列表显示了 app-v 5.1 中用于报告的端到端高级别工作流。

1. App-v 5.1 报告服务器具有下列先决条件：

    - Internet information Services （IIS） web 服务器角色

    - Windows 身份验证角色（在 " **IIS/安全**" 下）

    - 安装和运行 sql Server Reporting Services （SSRS）的 SQL Server

    若要确认 SQL Server Reporting Services 正在运行，请 `http://localhost/Reports` 在 web 浏览器中以管理员身份查看将承载 app-v 5.1 报告的服务器。 将显示 SQL Server Reporting Services 主页。

2. 安装 app-v 5.1 报告服务器和关联的数据库。 有关安装报告服务器的详细信息，请参阅[如何在独立计算机上安装报告服务器并将其连接到数据库](how-to-install-the-reporting-server-on-a-standalone-computer-and-connect-it-to-the-database51.md)。 配置运行 App-v 5.1 客户端的计算机应将数据发送到报告服务器的时间。

3. 如果您未使用电子软件分发系统（如 Configuration Manager 查看报告），则可以在 SQL Server Reporting Services 中定义报表。 从[下载中心](https://go.microsoft.com/fwlink/?LinkId=397255)下载预定义的 SSRS 报告。

    > [!NOTE]
    > 如果你将 Configuration Manager 与 app-v 5.1 结合使用，则大多数报表都是从 Configuration Manager 生成的，而不是从 App-v 5.1 生成的。

4. 使用 as 管理员导入 app-v 5.1 PowerShell 模块后 `Import-Module AppvClient` ，启用 app-v 5.1 客户端。 此示例 PowerShell cmdlet 支持 app-v 5.1 报告：

    ```powershell
    Set-AppvClientConfiguration –reportingserverurl <url>:<port> -reportingenabled 1 – ReportingStartTime <0-23> - ReportingRandomDelay <#min>
    ```

    若要立即发送 app-v 5.1 报告数据，请 `Send-AppvClientReport` 在 app-v 5.1 客户端上运行。

    有关安装启用了报告的 app-v 5.1 客户端的详细信息，请参阅[关于客户端配置设置](about-client-configuration-settings51.md)。 若要使用 Windows PowerShell 管理 app-v 5.1 报告，请参阅[如何使用 PowerShell 启用 app-v 5.1 客户端上的报告](how-to-enable-reporting-on-the-app-v-51-client-by-using-powershell.md)。

5. 在报表服务器从 App-v 5.1 客户端接收数据后，它会将数据发送到报告数据库。 当数据库接收和处理客户端数据时，会将成功的答复发送到报告服务器，然后将通知发送到 App-v 5.1 客户端。

6. 当 App-v 5.1 客户端收到成功通知时，它将清空数据缓存以节省空间。

    > [!NOTE]
    > 默认情况下，在服务器确认数据接收后，缓存将被清除。 你可以手动配置客户端以保存数据缓存。

如果 App-v 5.1 客户端设备未收到来自服务器的成功通知，它会将数据保留在缓存中，并尝试在下一个配置的时间间隔内重新发送数据。 客户端继续收集数据并将其添加到缓存。

### <a href="" id="-------------app-v-5-1-reporting-server-frequently-asked-questions"></a> App-v 5.1 reporting server 常见问题

下表显示了有关 App-v 5.1 报告的常见问题的答案

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">问题</th>
<th align="left">详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>报告信息发送到报告数据库的频率是多少？</p></td>
<td align="left"><p>该频率取决于运行 App-v 5.1 客户端的计算机上配置报告任务的方式。 您必须配置发送报告数据的频率/间隔。 默认情况下，不启用 app-v 5.1 报告。</p></td>
</tr>
<tr class="even">
<td align="left"><p>报表服务器数据库中存储哪些信息？</p></td>
<td align="left"><p>以下列表显示了报告数据库中存储的内容：</p>
<ul>
<li><p>运行 App-v 5.1 客户端的计算机上运行的操作系统：主机名、版本、service pack、type-客户端/服务器、处理器架构。</p></li>
<li><p>App-v 5.1 客户端信息：版本。</p></li>
<li><p>已发布程序包列表： GUID、版本 GUID、名称。</p></li>
<li><p>应用程序使用信息：名称、版本、流式处理服务器、用户（domain\alias）、程序包版本 GUID、启动状态和时间、关闭时间。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>发送到报告服务器的信息量的平均数量是多少？</p></td>
<td align="left"><p>这取决于。 以下列表显示发送到报告服务器的三组数据：</p>
<ol>
<li><p>操作系统和 App-v 5.1 客户端信息。 每次发送此数据时约150字节。</p></li>
<li><p>已发布程序包列表。 30个程序包大约 7 KB。 仅当程序包列表使用较少的发布刷新进行更新时，才会发送此内容;如果没有任何更改，则不会发送此信息。</p></li>
<li><p>虚拟应用程序使用信息-每个事件大约 0.25 KB。 如果两次都在发送信息之前发生，则打开和结束计数为一个事件。 使用计划任务发送时，仅将上次成功上载后的数据发送到服务器。 如果通过 PowerShell cmdlet 手动发送，则会有一个可选参数，用于控制是否需要在下一次（该参数为 DeleteOnSuccess）重新发送数据 <strong> </strong> 。</p>
<p></p>
<p>例如，如果二十个应用程序已打开并已关闭，并且报告信息每天发送，则典型的每天流量应大约为 0.15 KB + 20 x 0.25 KB，或者大约 5KB/user</p></li>
</ol></td>
</tr>
<tr class="even">
<td align="left"><p>是否可以计划报告？</p></td>
<td align="left"><p>是。 除了使用 PowerShell Cmdlet （ <strong> Send-AppvClientReport）手动发送报告外 </strong> ，还可以计划任务，以便它会自动发生。 可通过两种方式安排报告：</p>
<ol>
<li><p>使用 PowerShell cmdlet- <strong> Set-AppvClientConfiguration </strong> 。 例如：</p>
<p>Set-AppvClientConfiguration-ReportingEnabled 1-ReportingServerURL<a href="http://any.com/appv-reporting" data-raw-source="http://any.com/appv-reporting">http://any.com/appv-reporting</a></p>
<p></p>
<p>有关客户端配置设置的完整列表，请参阅 <a href="about-client-configuration-settings51.md" data-raw-source="[About Client Configuration Settings](about-client-configuration-settings51.md)"> 关于客户端配置设置 </a> 和查找以下条目： <strong> ReportingEnabled </strong> 、 <strong> ReportingServerURL </strong> 、 <strong> ReportingDataCacheLimit </strong> 、 <strong> ReportingDataBlockSize </strong> 、 <strong> ReportingStartTime </strong> 、 <strong> ReportingRandomDelay </strong> 、 <strong> ReportingInterval </strong> 。</p>
<p></p></li>
<li><p>使用组策略。 如果使用域控制器进行分发，则设置与前面列出的设置相同。</p>
<div class="alert">
<strong>注意</strong><br/><p>组策略设置替代使用 PowerShell 配置的本地设置。</p>
</div>
<div>
</div></li>
</ol></td>
</tr>
</tbody>
</table>

## <a href="" id="---------app-v-5-1-client-reporting"></a> App-v 5.1 客户端报告

若要使用 app-v 5.1 报告，您必须安装和配置 app-v 5.1 客户端。 安装客户端后，请使用**AppVClientConfiguration** PowerShell Cmdlet 或**ADMX 模板**来配置报告。 报告功能 cmdlet 可通过以下链接提供，并以**报告**开头。 有关客户端配置设置的完整列表，请参阅[关于客户端配置设置](about-client-configuration-settings51.md)。 以下部分提供了使用 PowerShell 的 app-v 5.1 客户端报告配置的示例。

### 使用 PowerShell 配置 App-v 客户端报告

以下示例显示 PowerShell 参数如何配置 app-v 5.1 客户端的报告功能。

> [!NOTE]
> 还可以使用 app-v 5.1 ADMX 模板中的组策略设置配置以下配置任务。 有关使用 ADMX 模板的详细信息，请参阅[如何使用 Admx 模板和组策略修改 app-v 5.1 客户端配置](how-to-modify-app-v-51-client-configuration-using-the-admx-template-and-group-policy.md)。

**若要在运行 app-v 5.1 客户端的计算机上启用报告和启动数据收集，** 请执行以下操作：

```powershell
Set-AppVClientConfiguration –ReportingEnabled 1
```

**若要将客户端配置为自动将数据发送到特定的报表服务器**，请执行以下操作：

```powershell
Set-AppVClientConfiguration –ReportingServerURL http://MyReportingServer:MyPort/ -ReportingStartTime 20 -ReportingInterval 1 -ReportingRandomDelay 30 -ReportingInterval 1 -ReportingRandomDelay 30
```

此示例将客户端配置为自动将报告数据发送到报表服务器 URL **http://MyReportingServer:MyPort/** 。 此外，报告数据将在8:00 和 8:30 PM 之间每天发送，具体取决于为会话生成的随机延迟。

**若要限制客户端上的数据缓存的大小**，请执行以下操作：

```powershell
Set-AppvClientConfiguration –ReportingDataCacheLimit 100
```

将运行 App-v 5.1 客户端的计算机上的报告缓存的最大大小配置为 100 MB。 如果在将数据发送到服务器之前已达到缓存限制，则日志将回滚，并且将根据需要覆盖数据。

**要配置客户端和服务器之间通过网络传输的数据块大小，** 请执行以下操作：

```powershell
Set-AppvClientConfiguration –ReportingDataBlockSize 10240
```

指定客户端发送到 10240 MB 的最大数据块。

### 收集的数据类型

下表显示了可使用 App-v 5.1 报告收集的信息类型。

|客户端信息  |程序包信息  |应用程序使用  |
|---------|---------|---------|
|主机名 |程序包名称|开始时间和结束时间|
|App-v 5.1 客户端版本 |程序包版本|运行状态|
|处理器体系结构 |程序包源|关闭状态|
|操作系统版本|缓存百分比|应用程序名称|
|Service Pack 级别| |应用程序版本|
|操作系统类型| |用户名|
| | |连接组|

客户端以 **.xml**格式收集和保存此数据。 默认情况下，数据缓存处于隐藏状态，需要管理员权限才能打开 XML 文件。

### 将数据发送到服务器

你可以配置运行 App-v 5.1 客户端的计算机以自动将数据发送到指定的报表服务器。 若要指定服务器，请使用具有以下设置的**AppvClientConfiguration** cmdlet：

- ReportingEnabled
- ReportingServerURL
- ReportingStartTime
- ReportingInterval
- ReportingRandomDelay

配置以前的设置后，必须创建计划任务。 计划任务将联系由**ReportingServerURL**设置指定的服务器，并将启动传输。 如果你想要在计划的时间之外手动发送数据，请使用以下 PowerShell cmdlet：

```powershell
Send-AppVClientReport –URL http://MyReportingServer:MyPort/ -DeleteOnSuccess
```

如果以前配置过报表服务器，则可以忽略 **– URL**参数。 或者，如果应将数据发送到备用位置，请指定其他 URL 以替代此数据集的已配置**ReportingServerURL** 。

**-DeleteOnSuccess**参数指示如果传输成功，则清除数据缓存。 如果未指定此选项，则不会清除缓存。

### 手动数据收集

你还可以使用**AppVClientReport** cmdlet 手动收集数据。 此解决方案对现有报告服务器或没有现有报告服务器很有帮助。 以下列表显示有关使用或不使用报表服务器收集数据的信息。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">使用报表服务器</th>
<th align="left">不带报表服务器</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>如果你有现有的 app-v 5.1 报表服务器，请创建自定义计划任务或脚本。 指定客户端将数据以所需的频率发送到指定位置。</p></td>
<td align="left"><p>如果您没有现有的 app-v 5.1 报告服务器，请使用 <strong> – URL </strong> 参数将数据发送到指定的共享。 例如：</p>
<p><code>Send-AppVClientReport –URL \Myshare\MyData\ -DeleteOnSuccess</code></p>
<p>前面的示例将把报告数据发送到 <strong> &lt; &gt; 由 <strong> -URL 参数指示的 \MyShare\MyData/strong 位置 </strong> 。 发送数据后，将清除缓存。</p>
<div class="alert">
<strong>注意</strong><br/><p>如果指定了报告服务器之外的位置，则数据将使用 <strong> .xml 格式发送， </strong> 无需其他处理。</p>
</div>
<div>
</div></td>
</tr>
</tbody>
</table>

### 创建报表

若要使用 App-v 5.1 检索报表信息和创建报表，必须使用下列方法之一：

- Microsoft **Sql Server Reporting services （SSRS）** -microsoft Sql Server reporting services 可通过 Microsoft sql server 使用。 安装 app-v 5.1 报告服务器时，不会安装 SSRS。 必须单独部署它才能生成相关联的报表。

    有关使用[MICROSOFT SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=285596)的详细信息，请使用以下链接。

- **脚本**-你可以通过直接通过脚本对 app-v 5.1 报告数据库生成报表。 例如：

    **存储过程：**

    **spProcessClientReport**计划在午夜或 12:00 AM 运行。

    若要运行 Microsoft SQL Server 计划的存储过程，必须运行 Microsoft SQL Server 代理。 应确保将 Microsoft SQL Server Agent 设置为**AutoStart**。 有关详细信息，请参阅[AUTOSTART Sql Server 代理（Sql Server Management Studio）](https://go.microsoft.com/fwlink/?LinkId=287045)。

    还会在使用 app-v 5.1 数据库脚本时创建存储过程。

你还应确保将报表服务器 web 服务的**最大并发连接**设置为服务器能够管理的值，而不会影响可用性。 **报告 Web 服务**的**最大并发连接**数建议为**10000**。

## 相关主题

[部署 App-V 5.1 Server](deploying-the-app-v-51-server.md)

[如何在独立计算机上安装报告服务器并将其连接到数据库](how-to-install-the-reporting-server-on-a-standalone-computer-and-connect-it-to-the-database51.md)
