---
title: 适用于外围网络的面向 Internet 的服务器方案
description: 适用于外围网络的面向 Internet 的服务器方案
author: dansimp
ms.assetid: 8a4da6e6-82c7-49e5-b9b1-1666cba02f65
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: fcb04e651341fa107c358eaabbd7992d7ea155ec
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798940"
---
# 适用于外围网络的面向 Internet 的服务器方案


App-v 4.5 支持面向 Internet 的服务器方案，在这种情况下，未连接到企业网络或从网络断开连接的用户仍可使用 app-v。 如下图所示，仅支持在 Internet （RTSPS 和 HTTPS）上使用安全协议。

![app-v 防火墙定位图](images/appvfirewalls.gif)

你可以使用 ISA 服务器设置面向 Internet 的解决方案，其中 App-v 基础结构位于内部网络上的以下几个方面：

-   为托管 .ICO 和 OSD 文件的 IIS 服务器创建 Web 发布规则，也可以为流的程序包（可选）位于内部网络上。 提供了详细步骤 <https://go.microsoft.com/fwlink/?LinkId=151982> 。

-   为 App-v Web 管理服务器（RTSPS）创建服务器发布规则。 提供了详细步骤 [https://go.microsoft.com/fwlink/?LinkId=151983&](https://go.microsoft.com/fwlink/?LinkId=151983) 。

如下图所示，如果基础结构已在客户端和 ISA 服务器之间或 ISA 服务器与内部网络之间实现了其他防火墙，则必须创建 RTSPS （TCP 322）和 HTTPS （TCP 443）防火墙规则来支持流量流。 此外，如果在 ISA 服务器和内部网络之间实现了防火墙，则必须允许域成员的默认流量通过防火墙（DNS、LDAP、Kerberos、SMB/CIFS）进行隧道。

![应用程序-v 外围网络防火墙图](images/appvperimeternetworkfirewall.gif)

由于防火墙解决方案因环境而异，本主题中提供的指南介绍了在外围网络中配置面向 Internet 的 App-v 环境所需的流量。 此信息还包括推荐的内部网络服务器。

将以下服务器放在外围网络中：

-   App-v 管理服务器

-   用于发布和流式处理的 IIS 服务器

**注意** 最佳做法是将管理服务器和 IIS 服务器放在单独的计算机上。

 

将以下服务器放入内部网络：

-   内容服务器

-   数据存储（SQL Server）

-   Active Directory 域控制器

## 流量要求


下表列出了从 Internet 和外围网络以及从外围网络到内部网络的通信的流量要求。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">从 Internet 到外围网络的流量要求</th>
<th align="left">详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>RTSPS （发布刷新和流式处理程序包）</p></td>
<td align="left"><p>默认情况下为 TCP 322;可以在 App-v 管理服务器中更改此项。</p></td>
</tr>
<tr class="even">
<td align="left"><p>HTTPS （发布 .ICO 和 OSD 文件和流式处理程序包）</p></td>
<td align="left"><p>默认情况下为 TCP 443;可在 IIS 配置中更改此设置。</p></td>
</tr>
</tbody>
</table>

 

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">从外围网络到内部网络的流量要求</th>
<th align="left">详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>SQL Server</p></td>
<td align="left"><p>TCP 1433 是默认设置，但可以在 SQL Server 中进行配置。</p></td>
</tr>
<tr class="even">
<td align="left"><p>SMB/CIFS</p></td>
<td align="left"><p>如果内容目录来自管理服务器或 IIS 服务器的远程位置（推荐）。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Kerberos</p></td>
<td align="left"><p>TCP 和 UDP 88</p></td>
</tr>
<tr class="even">
<td align="left"><p>适用</p></td>
<td align="left"><p>TCP 和 UDP 389</p></td>
</tr>
<tr class="odd">
<td align="left"><p>DNS</p></td>
<td align="left"><p>对于内部资源的名称解析（可在外围网络服务器上使用主机的文件时消除）</p></td>
</tr>
</tbody>
</table>

 

 

 





