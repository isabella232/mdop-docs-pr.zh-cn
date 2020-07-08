---
title: Application Virtualization System 组件概述
description: Application Virtualization System 组件概述
author: dansimp
ms.assetid: 75d88ef7-44d8-4fa7-b7f5-9153f37e570d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: cab0065b9966094da687cce2f5e94069922189fc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798894"
---
# Application Virtualization System 组件概述


下表介绍了 Microsoft Application Virtualization 管理系统的主要组件。 有关部署这些系统组件的详细信息，请参阅[基于应用程序虚拟服务器的方案](application-virtualization-server-based-scenario.md)。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">组件</th>
<th align="left">函数</th>
<th align="left">其他信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Microsoft Application Virtualization 管理服务器</p></td>
<td align="left"><p>负责流式处理程序包内容并将快捷方式和文件类型关联发布到应用程序虚拟化客户端的组件。</p></td>
<td align="left"><p>应用程序虚拟化管理服务器支持活动升级、许可证管理和可用于报告的数据库。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>内容 </strong> 文件夹</p></td>
<td align="left"><p>用于流式处理的应用程序虚拟化程序包的位置。</p></td>
<td align="left"><p>此文件夹可以位于应用程序虚拟化管理服务器上的共享位置。 该文件夹也可以位于存储区域网络（SAN）上。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Microsoft Application Virtualization 管理控制台</p></td>
<td align="left"><p>用于 Microsoft Application Virtualization 服务器管理的 MMC 3.0 管理实用工具。</p></td>
<td align="left"><p>此组件可以安装在 Microsoft Application Virtualization 服务器上，也可以位于具有 MMC 3.0 和的单独工作站上。已安装 NET 2.0。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Application Virtualization 管理 Web 服务</p></td>
<td align="left"><p>负责将任何读/写请求与应用程序虚拟化数据存储进行通信的组件。</p></td>
<td align="left"><p>此组件可以安装在 Microsoft Application Virtualization 服务器上，也可以安装在安装了 IIS 的单独计算机上。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Microsoft Application Virtualization 数据存储</p></td>
<td align="left"><p>存储在 SQL 数据库中的组件，负责存储与应用程序虚拟化基础结构相关的所有信息。</p></td>
<td align="left"><p>此信息包括所有应用程序记录、应用程序分配以及哪些组负责管理应用程序虚拟化环境。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Application Virtualization 流服务器</p></td>
<td align="left"><p>负责托管应用程序虚拟化程序包的组件，用于向分支机构中的客户端进行流处理，其中，返回到应用程序虚拟化管理服务器的链接被视为 WAN。</p></td>
<td align="left"><p>此服务器仅包含流功能，并且既不提供应用程序虚拟化管理控制台，也不提供应用程序虚拟化管理 Web 服务。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Microsoft Application Virtualization Sequencer</p></td>
<td align="left"><p>用于监视和捕获应用程序安装以创建虚拟应用程序包的组件。</p></td>
<td align="left"><p>输出包含应用程序的图标、包含程序包定义信息的 OSD 文件、程序包清单文件和包含应用程序内容文件的 SFT 文件。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Application Virtualization 客户端</p></td>
<td align="left"><p>在应用程序虚拟化桌面客户端或应用程序虚拟化客户端上安装的组件（以前称为 "终端服务"），并为虚拟化的应用程序提供虚拟环境。</p></td>
<td align="left"><p>Microsoft Application Virtualization 客户端将程序包流管理到缓存、发布刷新、传输以及与应用程序虚拟化服务器的所有交互。</p></td>
</tr>
</tbody>
</table>

 

## 相关主题


[基于 Application Virtualization Server 的方案](application-virtualization-server-based-scenario.md)

[在基于 Application Virtualization Server 的实现中计划流式处理解决方案](planning-your-streaming-solution-in-an-application-virtualization-server-based-implementation.md)

[使用 Application Virtualization Management Server 发布虚拟应用程序](publishing-virtual-applications-using-application-virtualization-management-servers.md)

 

 





