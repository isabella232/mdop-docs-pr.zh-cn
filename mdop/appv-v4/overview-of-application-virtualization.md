---
title: Application Virtualization 概述
description: Application Virtualization 概述
author: dansimp
ms.assetid: 80545ef4-cf4c-420c-88d6-48e9f226051f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2f3719a817137edfd76b1b972e966c685581c58e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798896"
---
# Application Virtualization 概述


Microsoft Application Virtualization （App-v）可使应用程序可用于最终用户计算机，而无需直接在这些计算机上安装应用程序。 这可通过一个称为*应用程序顺序的*进程来实现，这使每个应用程序都可以在客户端计算机上其自己的自包含虚拟环境中运行。 序列化的应用程序相互隔离。 这消除了应用程序冲突，但应用程序仍可以与客户端计算机交互。

App-v 客户端是允许最终用户在将应用程序发布到计算机之后与这些应用程序交互的功能。 客户端管理虚拟化应用程序在每台计算机上运行的虚拟环境。 在计算机上安装了客户端后，必须通过称为 "*发布*" 的进程将应用程序提供给计算机，这使最终用户能够运行虚拟应用程序。 发布过程会将虚拟应用程序图标和快捷方式复制到计算机（通常位于 Windows 桌面或 "**开始**" 菜单上），并且还会将程序包定义和文件类型关联信息复制到计算机。 发布还使应用程序包内容可供最终用户的计算机使用。

虚拟应用程序包内容可以复制到一个或多个应用程序虚拟服务器上，以便可以按需将其传输到客户端并在本地缓存。 文件服务器和 Web 服务器也可以用作流服务器，或者可以将内容直接复制到最终用户的计算机上，例如，如果你使用的是电子软件分发系统（如 Microsoft 终结点配置管理器）。 在多服务器实现中，在所有流式处理服务器上维护程序包内容并使其保持最新状态需要全面的程序包管理解决方案。 根据组织的规模，可能需要为全球各地的最终用户提供许多虚拟应用程序。 管理程序包以确保所有用户在需要访问这些程序包时都可以使用相应的应用程序，因此这是一个重要的要求。

## Microsoft Application Virtualization 系统功能


下表介绍了 Microsoft Application Virtualization 管理系统的主要功能。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">功能</th>
<th align="left">函数</th>
<th align="left">其他信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Microsoft Application Virtualization 管理服务器</p></td>
<td align="left"><p>负责对程序包内容进行流式处理，并将快捷方式和文件类型关联发布到应用程序虚拟化客户端。</p></td>
<td align="left"><p>应用程序虚拟化管理服务器支持活动升级、许可证管理和可用于报告的数据库。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>内容 </strong> 文件夹</p></td>
<td align="left"><p>指示用于流式处理的应用程序虚拟化程序包的位置。</p></td>
<td align="left"><p>此文件夹可以位于应用程序虚拟化管理服务器上的共享位置。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Microsoft Application Virtualization 管理控制台</p></td>
<td align="left"><p>此控制台是用于 Microsoft Application Virtualization 服务器管理的 MMC 3.0 管理单元管理工具。</p></td>
<td align="left"><p>此工具可以安装在 Microsoft Application Virtualization 服务器上，也可以位于具有 Microsoft 管理控制台（MMC）3.0 和 Microsoft 的单独工作站上。已安装 NETFramework 2.0。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Application Virtualization 管理 Web 服务</p></td>
<td align="left"><p>负责将任何读取和写入请求传递到应用程序虚拟化数据存储。</p></td>
<td align="left"><p>管理 Web 服务可以安装在 Microsoft Application Virtualization 管理服务器上，也可以安装在安装了 Microsoft Internet information Services （IIS）的单独计算机上。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Microsoft Application Virtualization 数据存储</p></td>
<td align="left"><p>App-v SQL Server 数据库，负责存储与应用程序虚拟化基础结构相关的所有信息。</p></td>
<td align="left"><p>此信息包括所有应用程序记录、应用程序分配以及哪些组负责管理应用程序虚拟化环境。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Application Virtualization 流服务器</p></td>
<td align="left"><p>负责托管应用程序虚拟化程序包，用于向分支机构中的客户端进行流处理，其中返回到应用程序虚拟化管理服务器的链接被视为广域网络（WAN）连接。</p></td>
<td align="left"><p>此服务器仅包含流功能，并且既不提供应用程序虚拟化管理控制台，也不提供应用程序虚拟化管理 Web 服务。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Microsoft Application Virtualization Sequencer</p></td>
<td align="left"><p>Sequencer 用于监视和捕获应用程序的安装以创建虚拟应用程序包。</p></td>
<td align="left"><p>输出包含应用程序的图标、包含程序包定义信息的 .osd 文件、程序包清单文件和包含应用程序内容文件的 sft 文件。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Application Virtualization 客户端</p></td>
<td align="left"><p>应用程序虚拟化桌面客户端和适用于远程桌面服务的应用程序虚拟化客户端为虚拟化应用程序提供和管理虚拟环境。</p></td>
<td align="left"><p>Microsoft Application Virtualization 客户端将程序包流管理到缓存、发布刷新、传输以及与应用程序虚拟化服务器的所有交互。</p></td>
</tr>
</tbody>
</table>

 

 

 





