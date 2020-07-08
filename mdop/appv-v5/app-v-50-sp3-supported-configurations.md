---
title: App-V 5.0 SP3 支持的配置
description: App-V 5.0 SP3 支持的配置
author: dansimp
ms.assetid: 08ced79a-0ed3-43c3-82e7-de01c1f33e81
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: b5a8858c703add3dc84c7eed4f62aa97e60ec9b0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798634"
---
# App-V 5.0 SP3 支持的配置


本主题指定在你的环境中安装和运行 Microsoft Application Virtualization （App-v） 5.0 SP3 的要求。

## App-v Server 系统要求


本部分列出了所有 app-v 服务器组件的操作系统和硬件要求。

### 不支持的 app-v 5.0 SP3 服务器方案

App-v 5.0 SP3 服务器不支持以下方案：

-   部署到运行 Microsoft Windows Server Core 的计算机。

-   部署到运行早期版本的 App-v 5.0 SP3 Server 组件的计算机。 你可以仅使用 app-v 4.5 轻型流服务器（LWS）服务器来安装 app-v 5.0 SP3。 不支持使用 app-v 4.5 应用程序虚拟管理服务（HWS）服务器并行部署 app-v。

-   部署到运行 Microsoft SQL Server Express edition 的计算机。

-   管理服务器数据库或报告数据库的远程部署。 必须直接在运行 Microsoft SQL Server 的计算机上运行安装程序。

-   部署到域控制器。

-   短路径。 如果您计划使用短路径，则必须创建新卷。

### 管理服务器操作系统要求

下表列出了 app-v 5.0 SP3 管理服务器安装支持的操作系统。

**注意** Microsoft 提供对当前服务包的支持，在某些情况下，还提供了之前的服务包。 若要查找产品的支持时间表，请参阅[支持生命周期的服务包](https://go.microsoft.com/fwlink/p/?LinkId=31975)。 有关详细信息，请参阅[Microsoft 支持生命周期支持策略常见问题](https://go.microsoft.com/fwlink/p/?LinkId=31976)。

 

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">操作系统</th>
<th align="left">Service Pack</th>
<th align="left">系统体系结构</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Microsoft Windows Server 2012 R2</p></td>
<td align="left"><p></p></td>
<td align="left"><p>64 位</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Windows Server 2012</p></td>
<td align="left"><p></p></td>
<td align="left"><p>64 位</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Microsoft Windows Server 2008 R2</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>64 位</p></td>
</tr>
</tbody>
</table>

 

**重要提示** 不支持将管理服务器角色部署到启用了远程桌面共享（RDS）的计算机。

 

### <a href="" id="management-server-hardware-requirements-"></a>管理服务器硬件要求

-   处理器-1.4 GHz 或更快的64位（x64）处理器

-   RAM-1 GB RAM （64位）

-   磁盘空间-200 MB 可用硬盘空间，不包括内容目录

### 管理服务器数据库要求

下表列出了 app-v 5.0 SP3 管理数据库安装支持的 SQL Server 版本。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">SQL Server 版本</th>
<th align="left">Service pack</th>
<th align="left">系统体系结构</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Microsoft SQL Server 2014</p></td>
<td align="left"><p></p></td>
<td align="left"><p>32 位或 64 位</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft SQL Server 2012</p></td>
<td align="left"><p>SP2</p></td>
<td align="left"><p>32 位或 64 位</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Microsoft SQL Server 2008 R2</p></td>
<td align="left"><p>又</p></td>
<td align="left"><p>32 位或 64 位</p></td>
</tr>
</tbody>
</table>

 

### 发布服务器操作系统要求

下表列出了 app-v 5.0 SP3 发布服务器安装支持的操作系统。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">操作系统</th>
<th align="left">Service Pack</th>
<th align="left">系统体系结构</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Microsoft Windows Server 2012 R2</p></td>
<td align="left"><p></p></td>
<td align="left"><p>64 位</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Windows Server 2012</p></td>
<td align="left"><p></p></td>
<td align="left"><p>64 位</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Microsoft Windows Server 2008 R2</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>64 位</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="publishing-server-hardware-requirements-"></a>发布服务器硬件要求

App-v 除了在 Windows Server 之外还添加了其他要求。

-   处理器-1.4 GHz 或更快的64位（x64）处理器

-   RAM-2 GB RAM （64位）

-   磁盘空间-200 MB 可用硬盘空间，不包括内容目录

### 报表服务器操作系统要求

下表列出了 app-v 5.0 SP3 报告服务器安装支持的操作系统。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">操作系统</th>
<th align="left">Service Pack</th>
<th align="left">系统体系结构</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Microsoft Windows Server 2012 R2</p></td>
<td align="left"><p></p></td>
<td align="left"><p>64 位</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Windows Server 2012</p></td>
<td align="left"><p></p></td>
<td align="left"><p>64 位</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Microsoft Windows Server 2008 R2</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>64 位</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="reporting-server-hardware-requirements-"></a>报告服务器硬件要求

App-v 除了在 Windows Server 之外还添加了其他要求。

-   处理器-1.4 GHz 或更快的64位（x64）处理器

-   RAM-2 GB RAM （64位）

-   磁盘空间-200 MB 可用硬盘空间

### 报表服务器数据库要求

下表列出了 app-v 5.0 SP3 报告数据库安装支持的 SQL Server 版本。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">SQL Server 版本</th>
<th align="left">Service pack</th>
<th align="left">系统体系结构</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Microsoft SQL Server 2014</p></td>
<td align="left"><p></p></td>
<td align="left"><p>32 位或 64 位</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft SQL Server 2012</p></td>
<td align="left"><p>SP2</p></td>
<td align="left"><p>32 位或 64 位</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Microsoft SQL Server 2008 R2</p></td>
<td align="left"><p>又</p></td>
<td align="left"><p>32 位或 64 位</p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-client-supp-cfgs"></a>App-v 客户端系统要求


下表列出了 app-v 5.0 SP3 客户端安装支持的操作系统。

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
<td align="left"><p>Microsoft Windows 8。1</p></td>
<td align="left"><p></p></td>
<td align="left"><p>32 位或 64 位</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Windows8</p></td>
<td align="left"><p></p></td>
<td align="left"><p>32 位或 64 位</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows7</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>32 位或 64 位</p></td>
</tr>
</tbody>
</table>

 

以下 App-v 客户端安装方案不受支持，但所述除外：

-   运行 Windows Server 的计算机

-   运行 App-v 4.6 SP1 或更早版本的计算机

-   只有启用了 RDS 的服务器才支持 app-v 5.0 SP3 远程桌面服务客户端

### <a href="" id="app-v-client-hardware-requirements-"></a>App-v 客户端硬件要求

以下列表显示了 app-v 5.0 SP3 客户端安装所支持的硬件配置。

-   处理器-1.4 GHz 或更快的32位（x86）或64位（x64）处理器

-   RAM-1 GB （32位）或 2 GB （64位）

-   磁盘-100 MB 用于安装，不包括虚拟化应用程序使用的磁盘空间。

## 远程桌面服务客户端系统要求


下表列出了 App-v 5.0 SP3 远程桌面服务（RDS）客户端安装支持的操作系统。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">操作系统</th>
<th align="left">Service Pack</th>
<th align="left">系统体系结构</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Microsoft Windows Server 2012 R2</p></td>
<td align="left"><p></p></td>
<td align="left"><p>64 位</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Windows Server 2012</p></td>
<td align="left"><p></p></td>
<td align="left"><p>64 位</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Microsoft Windows Server 2008 R2</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>64 位</p></td>
</tr>
</tbody>
</table>

 

### 远程桌面服务客户端硬件要求

App-v 除了在 Windows Server 之外还添加了其他要求。

-   处理器-1.4 GHz 或更快的64位（x64）处理器

-   RAM-2 GB RAM （64位）

-   磁盘空间-200 MB 可用硬盘空间

## Sequencer 系统要求


下表列出了 app-v 5.0 SP3 Sequencer 安装支持的操作系统。

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
<td align="left"><p>Microsoft Windows Server2012 R2</p></td>
<td align="left"></td>
<td align="left"><p>64 位</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Windows Server2012</p></td>
<td align="left"><p></p></td>
<td align="left"><p>64 位</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Microsoft Windows Server2008 R2</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>64 位</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Windows 8。1</p></td>
<td align="left"><p></p></td>
<td align="left"><p>32 位和 64 位 ：</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Microsoft Windows8</p></td>
<td align="left"><p></p></td>
<td align="left"><p>32 位和 64 位 ：</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Windows7</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>32 位和 64 位 ：</p></td>
</tr>
</tbody>
</table>

 

### Sequencer 硬件要求

有关硬件要求，请参阅 Windows 或 Windows Server 文档。 App-v 不增加任何其他硬件要求。

## <a href="" id="bkmk-supp-ver-sccm"></a>System Center Configuration Manager 支持的版本


App-v 客户端支持以下版本的 System Center Configuration Manager：

-   MicrosoftSystemCenter2012 ConfigurationManager

-   System Center 2012 R2 Configuration Manager

-   System Center 2012 R2 Configuration Manager SP1

有关 Configuration Manager 如何与 app-v 集成的详细信息，请参阅[规划与 Configuration Manager 的 App-v 集成](https://technet.microsoft.com/library/jj822982.aspx)。






## 相关主题


[计划部署 App-V](planning-to-deploy-app-v.md)

[App-V 5.0 SP3 先决条件](app-v-50-sp3-prerequisites.md)

 

 





