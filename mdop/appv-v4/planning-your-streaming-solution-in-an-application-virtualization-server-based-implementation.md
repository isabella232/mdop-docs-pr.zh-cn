---
title: 在基于 Application Virtualization Server 的实现中计划流式处理解决方案
description: 在基于 Application Virtualization Server 的实现中计划流式处理解决方案
author: dansimp
ms.assetid: 3a57306e-5c54-4fde-8593-fe3b788f18d3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0d315f554eb99fc5c05c231630eaa41d4f505535
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798857"
---
# 在基于 Application Virtualization Server 的实现中计划流式处理解决方案


如果您想要将应用程序虚拟化流服务器与基于应用程序虚拟化管理服务器的实现配合使用，您可以从多个备选方案中进行选择，从而充分利用任何基础结构已存在的优势。 例如，如果您已在现场分支办事处拥有服务器，则可以将应用程序虚拟化 \\CONTENT 共享在这些服务器上，然后将客户端配置为使用该内容共享作为其应用程序内容源。 如果您选择仅使用应用程序虚拟化管理服务器（例如，您只有一个 office），则客户端可以流式传输该服务器中的内容。

支持的选项包括使用文件服务器、IIS 服务器或应用程序虚拟化流服务器。 您也可以在现有文件服务器或 IIS 服务器上安装应用程序虚拟化流服务器。 下表汇总了这些不同选项的特征。

**注意** 活动升级功能支持将应用程序的新版本添加到应用程序 V 管理服务器或流服务器，而不会影响当前运行该应用程序的用户。 App-v 客户端将在用户下次启动应用程序时从 App-v 管理服务器或流服务器自动接收最新版本的应用程序。 此功能需要使用 RTSP （S）协议。

 

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
<th align="left">服务器类型</th>
<th align="left">协议</th>
<th align="left">优点</th>
<th align="left">缺点</th>
<th align="left">Links</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>文件服务器</p></td>
<td align="left"><p>SMB</p></td>
<td align="left"><ul>
<li><p>通过 \CONTENT 共享配置现有文件服务器的简单的低成本解决方案</p></li>
</ul></td>
<td align="left"><ul>
<li><p>无活动升级</p></li>
</ul></td>
<td align="left"><p><a href="how-to-configure-the-file-server.md" data-raw-source="[How to Configure the File Server](how-to-configure-the-file-server.md)">如何配置文件服务器</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>IIS 服务器</p></td>
<td align="left"><p>HTTP/HTTPS</p></td>
<td align="left"><ul>
<li><p>支持使用 HTTPS 协议增强的安全性</p></li>
<li><p>支持通过 Internet 对远程计算机进行流处理</p></li>
<li><p>防火墙中只能打开一个端口</p></li>
<li><p>伸缩</p></li>
<li><p>熟悉的协议</p></li>
</ul></td>
<td align="left"><ul>
<li><p>需要管理 IIS</p></li>
<li><p>无活动升级</p></li>
</ul></td>
<td align="left"><p><a href="how-to-configure-the-server-for-iis.md" data-raw-source="[How to Configure the Server for IIS](how-to-configure-the-server-for-iis.md)">如何为 IIS 配置服务器</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>应用程序虚拟化流服务器</p></td>
<td align="left"><p>RTSP/RTSPS</p></td>
<td align="left"><ul>
<li><p>活动升级</p></li>
<li><p>支持使用 RTSPS 协议增强的安全性</p></li>
<li><p>防火墙中只能打开一个端口</p></li>
</ul></td>
<td align="left"><ul>
<li><p>双重基础结构</p></li>
<li><p>服务器管理要求</p></li>
</ul></td>
<td align="left"><p><a href="how-to-configure-the-application-virtualization-streaming-servers.md" data-raw-source="[How to Configure the Application Virtualization Streaming Servers](how-to-configure-the-application-virtualization-streaming-servers.md)">如何配置 Application Virtualization Streaming Server</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>应用程序虚拟化管理服务器</p></td>
<td align="left"><p>RTSP/RTSPS</p></td>
<td align="left"><ul>
<li><p>活动升级</p></li>
<li><p>支持使用 RTSPS 协议增强的安全性</p></li>
<li><p>防火墙中只能打开一个端口</p></li>
</ul></td>
<td align="left"><ul>
<li><p>双重基础结构</p></li>
<li><p>服务器管理要求</p></li>
</ul></td>
<td align="left"><p><a href="how-to-configure-the-application-virtualization-management-servers.md" data-raw-source="[How to Configure the Application Virtualization Management Servers](how-to-configure-the-application-virtualization-management-servers.md)">如何配置 Application Virtualization Management Server</a></p></td>
</tr>
</tbody>
</table>

 

## 相关主题


[基于 Application Virtualization Server 的方案](application-virtualization-server-based-scenario.md)

[Application Virtualization System 组件概述](overview-of-the-application-virtualization-system-components.md)

[使用 Application Virtualization Management Server 发布虚拟应用程序](publishing-virtual-applications-using-application-virtualization-management-servers.md)

 

 





