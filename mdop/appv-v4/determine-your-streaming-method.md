---
title: 确定流式处理方法
description: 确定流式处理方法
author: dansimp
ms.assetid: 50d5e0ec-7f48-4cea-8711-5882bd89153b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0acfd345ac55f11476cffe94b3a95b13c5d8f303
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803014"
---
# 确定流式处理方法


用户首次双击已通过发布过程放置在计算机上的图标时，应用程序虚拟化客户端将从流源位置获取虚拟应用程序包内容。

**注意** 
*流*是用于描述从顺序应用程序包获取内容的过程的术语，从主功能块开始，然后根据需要获取其他块。

 

流源位置通常是可由用户计算机访问的服务器;但是，某些电子分发系统（如 Microsoft 终结点配置管理器）可以将 SFT 文件分发到用户的计算机，然后从该计算机的缓存中本地传输虚拟应用程序包。

**注意** 可以在非服务器计算机上设置虚拟包的流源位置。 这在没有服务器的小型分支机构中尤其有用。

 

下表介绍了可用于存储排序应用程序的流式处理源。

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
<td align="left"><p>文件</p></td>
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
<li><p>支持使用 HTTPS 协议增强的安全性。</p></li>
<li><p>支持通过 Internet 对远程计算机进行流处理</p></li>
<li><p>防火墙中只能打开一个端口</p></li>
<li><p>高度可扩展</p></li>
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
<li><p>仅在防火墙中打开一个端口（仅限 RTSPS）</p></li>
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


[基于电子软件分发的方案](electronic-software-distribution-based-scenario.md)

[基于电子软件分发的方案概述](electronic-software-distribution-based-scenario-overview.md)

[确定发布方法](determine-your-publishing-method.md)

 

 





