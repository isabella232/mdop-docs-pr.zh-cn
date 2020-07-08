---
title: App-V 5.0 支持的配置
description: App-V 5.0 支持的配置
author: dansimp
ms.assetid: 3787ff63-7ce7-45a8-8f01-81b4b6dced34
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 60236743d2a6b418ca7f4705168a7bf064b82156
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798633"
---
# App-V 5.0 支持的配置


本主题指定在你的环境中安装和运行 Microsoft Application Virtualization （app-v）5.0 所需的要求。

**重要提示**  
**本文中受支持的配置仅适用于 app-v 5.0**。 有关适用于 App-v 5.0 Service Pack 的受支持配置，请参阅以下网页：

-   [App-V 5.0 SP1 中的新增功能](whats-new-in-app-v-50-sp1.md)

-   [关于 App-V 5.0 SP2](about-app-v-50-sp2.md)

-   [App-V 5.0 SP3 支持的配置](app-v-50-sp3-supported-configurations.md)



## <a href="" id="---------app-v-5-0-server-system-requirements"></a> App-v 5.0 服务器系统要求


**重要提示**  
App-v 5.0 服务器不支持以下方案：



-   部署到运行 Microsoft Windows Server Core 的计算机。

-   部署到运行早期版本的 App-v 5.0 server 组件的计算机。

    **注意**  
    你可以仅使用 app-v 4.5 轻型流服务器（LWS）服务器并行安装 app-v 5.0。 不支持使用 app-v 4.5 应用程序虚拟化管理服务（HWS）服务器并行部署 app-v 5.0。



-   部署到运行 Microsoft SQL Server Express edition 的计算机。

-   管理服务器数据库或报告数据库的远程部署。 安装程序必须直接在运行 Microsoft SQL 的计算机上运行，才能成功完成数据库安装。

-   部署到域控制器。

-   短路径不受支持。 如果您计划使用短路径，则必须创建新卷。

### 管理服务器操作系统要求

下表列出了 app-v 5.0 管理服务器安装支持的操作系统。

**注意**  
Microsoft 提供对当前服务包的支持，在某些情况下，还提供了之前的服务包。 若要查找产品的支持时间表，请参阅[支持生命周期的服务包](https://go.microsoft.com/fwlink/p/?LinkId=31975)。 有关 Microsoft 支持生命周期策略的其他信息，请参阅[Microsoft 支持生命周期支持策略常见问题解答](https://go.microsoft.com/fwlink/p/?LinkId=31976)。



<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">操作系统</th>
<th align="left">版本</th>
<th align="left">Service pack</th>
<th align="left">系统体系结构</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Microsoft Windows Server 2008 （标准版、企业版、数据中心版或 Web 服务器）</p></td>
<td align="left"><p>R2</p></td>
<td align="left"><p>SP1 及更高版本</p></td>
<td align="left"><p>64 位</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Windows Server 2012 （Standard、Datacenter）</p></td>
<td align="left"><p></p></td>
<td align="left"></td>
<td align="left"><p>64 位</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Microsoft Windows Server 2012 （Standard、Datacenter）</p></td>
<td align="left"><p>R2</p></td>
<td align="left"></td>
<td align="left"><p>64 位</p></td>
</tr>
</tbody>
</table>



**重要提示**  
不支持将管理服务器角色部署到启用了远程桌面共享（RDS）的计算机。



### <a href="" id="management-server-hardware-requirements-"></a>管理服务器硬件要求

-   处理器-1.4 GHz 或更快的64位（x64）处理器

-   RAM-1 GB RAM （64位）

-   磁盘空间-200 MB 可用硬盘空间，不包括内容目录。

### 发布服务器操作系统要求

下表列出了 app-v 5.0 发布服务器安装支持的操作系统。

**注意**  
Microsoft 提供对当前服务包的支持，在某些情况下，还提供了之前的服务包。 若要查找产品的支持时间表，请参阅[支持生命周期的服务包](https://go.microsoft.com/fwlink/p/?LinkId=31975)。 有关 Microsoft 支持生命周期策略的其他信息，请参阅[Microsoft 支持生命周期支持策略常见问题解答](https://go.microsoft.com/fwlink/p/?LinkId=31976)。



<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">操作系统</th>
<th align="left">版本</th>
<th align="left">Service pack</th>
<th align="left">系统体系结构</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Microsoft Windows Server 2008 （标准版、企业版、数据中心版或 Web 服务器）</p></td>
<td align="left"><p>R2</p></td>
<td align="left"><p></p></td>
<td align="left"><p>64 位</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Windows Server 2012 （Standard、Datacenter）</p></td>
<td align="left"><p></p></td>
<td align="left"></td>
<td align="left"><p>64 位</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Microsoft Windows Server 2012 （Standard、Datacenter）</p></td>
<td align="left"><p>R2</p></td>
<td align="left"></td>
<td align="left"><p>64 位</p></td>
</tr>
</tbody>
</table>



### <a href="" id="publishing-server-hardware-requirements-"></a>发布服务器硬件要求

-   处理器-1.4 GHz 或更快。 64位（x64）处理器

-   RAM-2 GB RAM （64位）

-   磁盘空间-200 MB 可用硬盘空间。 不包含内容目录

### 报表服务器操作系统要求

下表列出了 app-v 5.0 reporting server 安装支持的操作系统。

**注意**  
Microsoft 提供对当前服务包的支持，在某些情况下，还提供了之前的服务包。 若要查找产品的支持时间表，请参阅[支持生命周期的服务包](https://go.microsoft.com/fwlink/p/?LinkId=31975)。 有关 Microsoft 支持生命周期策略的其他信息，请参阅[Microsoft 支持生命周期支持策略常见问题解答](https://go.microsoft.com/fwlink/p/?LinkId=31976)。



<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">操作系统</th>
<th align="left">版本</th>
<th align="left">Service Pack</th>
<th align="left">系统体系结构</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Microsoft Windows Server 2008 （标准版、企业版、数据中心版或 Web 服务器）</p></td>
<td align="left"><p>R2</p></td>
<td align="left"><p></p></td>
<td align="left"><p>64 位</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Windows Server 2012 （Standard、Datacenter）</p></td>
<td align="left"><p></p></td>
<td align="left"></td>
<td align="left"><p>64 位</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Microsoft Windows Server 2012 （Standard、Datacenter）</p></td>
<td align="left"><p>R2</p></td>
<td align="left"></td>
<td align="left"><p>64 位</p></td>
</tr>
</tbody>
</table>



### <a href="" id="reporting-server-hardware-requirements-"></a>报告服务器硬件要求

-   处理器-1.4 GHz 或更快。 64位（x64）处理器

-   RAM-2 GB RAM （64位）

-   磁盘空间-200 MB 可用硬盘空间

### <a href="" id="sql-server-database-requirements-"></a>SQL Server 数据库要求

下表列出了 app-v 5.0 数据库和服务器安装支持的 SQL Server 版本。

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">App-v 5.0 服务器类型</th>
<th align="left">SQL Server 版本</th>
<th align="left">版本</th>
<th align="left">Service pack</th>
<th align="left">系统体系结构</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>管理/报告</p></td>
<td align="left"><p>Microsoft SQL Server 2008</p>
<p>（标准版、企业版、数据中心版或开发人员版，具有以下功能： <strong>数据库引擎服务 </strong> 。）</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>32 位或 64 位</p></td>
</tr>
<tr class="even">
<td align="left"><p>管理/报告</p></td>
<td align="left"><p>Microsoft SQL Server 2008 </p>
<p>（标准版、企业版、数据中心版或开发人员版，具有以下功能： <strong>数据库引擎服务 </strong> 。）</p></td>
<td align="left"><p>R2</p></td>
<td align="left"><p>SP2</p></td>
<td align="left"><p>32 位或 64 位</p></td>
</tr>
<tr class="odd">
<td align="left"><p>管理/报告</p></td>
<td align="left"><p>Microsoft SQL Server 2012</p>
<p>（标准版、企业版、数据中心版或开发人员版，具有以下功能： <strong>数据库引擎服务 </strong> 。）</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>32 位或 64 位</p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-client-supp-cfgs"></a> App-v 5.0 客户端系统要求


下表列出了 app-v 5.0 客户端安装支持的操作系统。

**注意**  
Microsoft 提供对当前服务包的支持，在某些情况下，还提供了之前的服务包。 若要查找产品的支持时间表，请参阅[支持生命周期的服务包](https://go.microsoft.com/fwlink/p/?LinkId=31975)。 有关 Microsoft 支持生命周期策略的其他信息，请参阅[Microsoft 支持生命周期支持策略常见问题解答](https://go.microsoft.com/fwlink/p/?LinkId=31976)。



<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">操作系统</th>
<th align="left">Service pack</th>
<th align="left">系统体系结构</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Microsoft Windows 7</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>32 位或 64 位</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Windows 8</p></td>
<td align="left"><p></p></td>
<td align="left"><p>32 位或 64 位</p></td>
</tr>
<tr class="odd">
<td align="left"><div class="alert">
<strong>重要提示</strong><br/><p>Windows 8.1 仅受 App-v 5.0 SP2 支持</p>
</div>
<div>

</div>
<p>Windows 8.1</p></td>
<td align="left"><p></p></td>
<td align="left"><p>32 位或 64 位</p></td>
</tr>
</tbody>
</table>



以下 App-v 客户端安装方案不受支持，但所述除外：

-   运行 Windows Server 的计算机

-   运行 App-v 4.6 SP1 或更早版本的计算机

-   只有支持 RDS 的服务器才支持 app-v 5.0 远程桌面服务客户端

### <a href="" id="client-hardware-requirements-"></a>客户端硬件要求

以下列表显示了 app-v 5.0 客户端安装所支持的硬件配置。

-   处理器-1.4 GHz 或更快的32位（x86）或64位（x64）处理器

-   RAM-1 GB （32位）或 2 GB （64位）

-   磁盘-100 MB 用于安装，不包括虚拟化应用程序使用的磁盘空间。

## <a href="" id="---------app-v-5-0-remote-desktop-client-system-requirements"></a> App-v 5.0 远程桌面客户端系统要求


下表列出了 App-v 5.0 远程桌面客户端安装支持的操作系统。

**注意**  
Microsoft 提供对当前服务包的支持，在某些情况下，还提供了之前的服务包。 若要查找产品的支持时间表，请参阅[支持生命周期的服务包](https://go.microsoft.com/fwlink/p/?LinkId=31975)。 有关 Microsoft 支持生命周期策略的其他信息，请参阅[Microsoft 支持生命周期支持策略常见问题解答](https://go.microsoft.com/fwlink/p/?LinkId=31976)。



操作系统版本 Service pack Microsoft Windows Server 2008

R2

SP1

Microsoft Windows Server 2012

**重要提示**  
Windows Server 2012 R2 仅受 App-v 5.0 SP2 支持



Microsoft Windows Server 2012 （Standard、Datacenter）

R2

64 位



### <a href="" id="remote-desktop-client-hardware-requirements-"></a>远程桌面客户端硬件要求

以下列表显示了 app-v 5.0 客户端安装所支持的硬件配置。

-   处理器-1.4 GHz 或更快的32位（x86）或64位（x64）处理器

-   RAM-1 GB （32位）或 2 GB （64位）

-   磁盘-100 MB 用于安装，不包括虚拟化应用程序使用的磁盘空间。

## <a href="" id="---------app-v-5-0-sequencer-system-requirements"></a> App-v 5.0 Sequencer 系统要求


下表列出了应用 V 5.0 Sequencer 安装支持的操作系统。

**注意**  
Microsoft 提供对当前服务包的支持，在某些情况下，还提供了之前的服务包。 若要查找产品的支持时间表，请参阅[支持生命周期的服务包](https://go.microsoft.com/fwlink/p/?LinkId=31975)。 有关 Microsoft 支持生命周期策略的其他信息，请参阅[Microsoft 支持生命周期支持策略常见问题解答](https://go.microsoft.com/fwlink/p/?LinkId=31976)。



<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">操作系统</th>
<th align="left">版本</th>
<th align="left">Service pack</th>
<th align="left">系统体系结构</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Microsoft Windows 7</p></td>
<td align="left"></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>32 位和 64 位 ：</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Windows 8</p></td>
<td align="left"></td>
<td align="left"><p></p></td>
<td align="left"><p>32 位和 64 位 ：</p></td>
</tr>
<tr class="odd">
<td align="left"><div class="alert">
<strong>重要提示</strong><br/><p>Windows 8.1 仅受 App-v 5.0 SP2 支持</p>
</div>
<div>

</div>
<p>Windows 8.1</p></td>
<td align="left"></td>
<td align="left"><p></p></td>
<td align="left"><p>32 位或 64 位</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Windows Server 2008</p></td>
<td align="left"><p>R2</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>32 位和 64 位 ：</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Microsoft Windows Server 2012</p></td>
<td align="left"></td>
<td align="left"><p></p></td>
<td align="left"><p>32 位和 64 位 ：</p></td>
</tr>
<tr class="even">
<td align="left"><div class="alert">
<strong>重要提示</strong><br/><p>Windows Server 2012 R2 仅受 App-v 5.0 SP2 支持</p>
</div>
<div>

</div>
<p>Microsoft Windows Server 2012</p></td>
<td align="left"><p>R2</p></td>
<td align="left"></td>
<td align="left"><p>64 位</p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-supp-ver-sccm"></a>System Center Configuration Manager 支持的版本


你可以使用 Microsoft System Center 2012 Configuration Manager 或 System Center 2012 R2 配置管理器管理 App-v 虚拟应用程序、报告和其他功能。 下表列出了每个适用版本的 App-v 的受支持的 Configuration Manager 版本。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">支持的 Configuration Manager 版本</th>
<th align="left">App-v 版本</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Microsoft System Center 2012 Configuration Manager</p></td>
<td align="left"><ul>
<li><p>App-v 5。0</p></li>
<li><p>App-v 5.0 SP1</p></li>
<li><p>App-v 5.0 SP2</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>System Center 2012 R2 Configuration Manager</p></td>
<td align="left"><ul>
<li><p>App-v 5。0</p></li>
<li><p>App-v 5.0 SP1</p></li>
<li><p>App-v 5.0 SP2</p></li>
</ul></td>
</tr>
</tbody>
</table>



有关 Configuration Manager 如何与 app-v 集成的详细信息，请参阅[规划与 Configuration Manager 的 App-v 集成](https://technet.microsoft.com/library/jj822982.aspx)。






## 相关主题


[计划部署 App-V](planning-to-deploy-app-v.md)

[App-V 5.0 先决条件](app-v-50-prerequisites.md)









