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
ms.openlocfilehash: 7415cf7a97edc646653df552723667bac8d25fdc
ms.sourcegitcommit: 3e0500abde44d6a09c7ac8e3caf5e25929b490a4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2021
ms.locfileid: "11910687"
---
# <a name="internet-facing-server-scenarios-for-perimeter-networks"></a>适用于外围网络的面向 Internet 的服务器方案


App-V 4.5 支持面向 Internet 的服务器方案，在这种情况下，未连接到企业网络或与网络断开连接的用户仍可以使用 App-V。 如下图所示，仅支持在 Internet 上使用安全协议 (RTSPS 和 HTTPS) 。

![app-v 防火墙定位图。](images/appvfirewalls.gif)

您可以使用 ISA 服务器设置面向 Internet 的解决方案，其中 App-V 基础结构采用以下方式位于内部网络上：

-   为承载 ICO 和 OSD 文件的 IIS 服务器创建 Web 发布规则（可选）位于内部网络上用于流式传输的程序包。 详细步骤在 中提供 <https://go.microsoft.com/fwlink/?LinkId=151982> 。

-   为 App-V Web Management Server 创建服务器发布规则 (RTSPS) 。 详细步骤在 中提供 [https://go.microsoft.com/fwlink/?LinkId=151983&](https://go.microsoft.com/fwlink/?LinkId=151983) 。

如下图所示，如果基础结构在客户端和 ISA 服务器之间或在 ISA 服务器和内部网络之间实施了其他防火墙，则必须创建 RTSPS (TCP 322) 和 HTTPS (TCP 443) 防火墙规则以支持通信流。 此外，如果已在 ISA 服务器和内部网络之间实施防火墙，则必须允许域成员所需的默认流量通过防火墙 (DNS、LDAP、Kerberos、SMB/CIFS) 。

![app-v 外围网络防火墙图。](images/appvperimeternetworkfirewall.gif)

由于防火墙解决方案因环境而异，本主题中提供的指南介绍了在外围网络中配置面向 Internet 的 App-V 环境所需的流量。 此信息还包括推荐的内部网络服务器。

将以下服务器放在外围网络中：

-   App-V 管理服务器

-   用于发布和流式传输的 IIS 服务器

**注意**  
最佳做法是将管理服务器和 IIS 服务器放在单独的计算机上。

 

将以下服务器放在内部网络中：

-   内容服务器

-   数据存储 (SQL Server) 

-   Active Directory 域控制器

## <a name="traffic-requirements"></a>流量要求


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
<td align="left"><p>RTSPS (发布刷新和流式处理) </p></td>
<td align="left"><p>默认情况下，TCP 322;这可以在 App-V 管理服务器中进行更改。</p></td>
</tr>
<tr class="even">
<td align="left"><p>HTTPS (ICO 和 OSD 文件以及流式处理包) </p></td>
<td align="left"><p>默认情况下 TCP 443;可以在 IIS 配置中对此进行更改。</p></td>
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
<td align="left"><p>TCP 1433 是默认设置，但可以在 SQL Server。</p></td>
</tr>
<tr class="even">
<td align="left"><p>SMB/CIFS</p></td>
<td align="left"><p>如果内容目录位于管理服务器或 IIS 服务器 (远程) 则 (IIS) 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Kerberos</p></td>
<td align="left"><p>TCP 和 UDP 88</p></td>
</tr>
<tr class="even">
<td align="left"><p>LDAP</p></td>
<td align="left"><p>TCP 和 UDP 389</p></td>
</tr>
<tr class="odd">
<td align="left"><p>DNS</p></td>
<td align="left"><p>对于内部资源的名称解析 (在外围网络服务器上使用主机文件来) </p></td>
</tr>
</tbody>
</table>

 

 

 





