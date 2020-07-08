---
title: 在电子软件分发实现中计划流式处理解决方案
description: 在电子软件分发实现中计划流式处理解决方案
author: dansimp
ms.assetid: bc18772a-f169-486f-adb1-7af1a31845aa
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c49d6fc0b5f8f5dee347ead3bb899ce9b0387024
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798855"
---
# 在电子软件分发实现中计划流式处理解决方案


如果您决定将流式处理服务器与 ESD 系统结合使用以使应用程序内容可供您的最终用户计算机使用，则可以从多个备选方案中进行选择，利用任何基础结构已到位。 例如，如果 ESD 系统在您的现场分支机构的服务器上有软件分发共享，则可以将应用程序虚拟化 \\CONTENT 共享在这些服务器上，然后将客户端配置为使用该内容共享作为其应用程序内容源。 支持的选项包括使用文件服务器或 IIS 服务器。 您也可以在现有文件服务器或 IIS 服务器上安装应用程序虚拟化流服务器。

应用程序虚拟化流服务器为应用程序虚拟化中的活动升级功能提供支持。 活动升级功能支持将应用程序的新版本添加到应用程序 V 管理服务器或流服务器，而不会影响当前运行该应用程序的用户。 App-v 客户端将在用户下次启动应用程序时从 App-v 管理服务器或流服务器自动接收最新版本的应用程序。 此功能需要使用 RTSP （S）协议。 如果你选择不使用应用程序虚拟化流服务器，你将需要使用 ESD 系统显式管理应用程序包升级。

**注意** 对应用程序的访问受 Active Directory 域服务中的安全组的控制，因此你需要为每个虚拟应用程序设置安全组的过程，并为管理每个组中添加的用户制定一个过程。 应用程序虚拟化系统管理员将每个流式服务器配置为使用这些 Active Directory 组，方法是将 Acl 应用于内容共享下的应用程序目录，从而控制对程序包的访问，具体取决于 Active Directory 组成员身份。

 

下表汇总了可用的流选项的特征。

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
<td align="left"><p><a href="how-to-configure-the-application-virtualization-management-servers.md" data-raw-source="[How to Configure the Application Virtualization Management Servers](how-to-configure-the-application-virtualization-management-servers.md)">如何配置 Application Virtualization Management Server</a></p></td>
</tr>
</tbody>
</table>

 

## 相关主题


[如何为基于 ESD 的部署配置服务器](how-to-configure-servers-for-esd-based-deployment.md)

[安全和保护概述](security-and-protection-overview.md)

[使用电子软件分发发布虚拟应用程序](publishing-virtual-applications-using-electronic-software-distribution.md)

 

 





