---
title: 基于 Application Virtualization Server 的方案概述
description: 基于 Application Virtualization Server 的方案概述
author: dansimp
ms.assetid: 2d91392b-5085-4a5d-94f2-15eed1ed2928
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7b3ac3f10a5b7c7705e6d72c122d52be801a6d50
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803099"
---
# 基于 Application Virtualization Server 的方案概述


如果您计划对您的 Microsoft Application Virtualization 环境使用基于服务器的部署方案，请务必了解*应用程序虚拟化管理服务器*和*应用程序虚拟化流服务器*之间的差异。 本主题介绍了这些差异，还提供了有关程序包传递方法、传输协议和外部组件的信息，在你继续部署时，你需要考虑这些信息。

## 应用程序虚拟化管理服务器


应用程序虚拟化管理服务器同时执行发布功能和流函数。 服务器将应用程序图标、快捷方式和文件类型关联发布到已授权用户的 app-v 客户端。 当接收到应用程序的用户请求时，将使用 RTSP 或 RTSPS 协议将数据按需传输到授权用户。 在使用此服务器的大多数配置中，一个或多个管理服务器共享一个用于配置和程序包信息的通用数据存储。

应用程序虚拟化管理服务器使用 Active Directory 组管理用户授权。 除了 Active Directory 域服务，这些服务器还安装了 SQL Server 来管理数据库和数据存储。 管理服务器通过应用程序虚拟化管理控制台进行控制，该控制台是 Microsoft 管理控制台的一个管理单元。

由于应用程序虚拟化管理服务器将应用程序流式流式处理应用程序，因此这些服务器非常适合具有可靠、高带宽 Lan 的系统配置。

## 应用程序虚拟化流服务器


应用程序虚拟化流服务器提供管理服务器提供的相同流和程序包升级功能，但没有其 Active Directory 或 SQL Server 要求。 但是，流服务器没有发布服务，也没有授权或计量功能。 单独的 App-v 管理服务器的发布服务与 App-v 流式处理服务器结合使用。 应用程序-V 流服务器解决了希望在多个位置使用应用程序虚拟化和经典服务器配置的流功能的企业需求，但可能没有基础结构来支持每个位置中的 app-v 管理服务器。

应用程序虚拟化流服务器还可以在具有现有电子软件分发系统（ESD）的环境中使用。 使用 ESD 管理流式处理应用程序。 与应用程序虚拟化管理服务器不同，流服务器不使用 SQL 或管理控制台。 这些服务器使用访问控制列表（Acl）授予用户授权。

## 程序包传递方法


如果你计划将应用程序虚拟化服务器用作发布传递方法，你需要确定你的方案所采用的以下哪种包传递方法：

-   *动态包送达*

-   *从文件包传递中加载*

### 动态包送达

在动态程序包传递过程中，服务器（应用程序虚拟化管理服务器、应用程序虚拟化流服务器或 IIS 服务器）通过按需部署向最终用户提供虚拟化应用程序。 只有当用户首次尝试启动应用程序时，服务器才会将虚拟化的应用程序和程序包传递给客户端计算机（按需）。 服务器仅流式处理启动应用程序所需的块（主要功能块）。 将主功能块交付给客户端后，应用程序运行;客户端不会收到完整的应用程序（增量部署），除非客户需要访问主功能块中未包含的应用程序部分。 发生这种情况时，客户端将执行顺序外请求，并将辅助功能块流传送到客户端。 动态程序包交付允许快速应用程序启动。

### 从文件包传递中加载

对于从文件包传递进行的加载，服务器会在用户启动应用程序之前将整个虚拟化应用程序包传递到客户端计算机。 在此方案中，虚拟化的应用程序以完整的程序包形式传递，而不是通过动态传递模型使用的动态、增量方法。

**注意** 对于每个交付方法，初始虚拟应用程序交付过程和虚拟应用程序更新过程相同;已更新的虚拟应用程序包替换原始应用程序包。

 

下表比较了每个程序包传递方法的优点和缺点。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">方法</th>
<th align="left">优点</th>
<th align="left">缺点</th>
<th align="left">备注</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>动态包送达</p></td>
<td align="left"><p>应用程序按需交付和更新。</p>
<p>应用程序以增量方式进行传递和更新，以优化启动时间。</p>
<p>更新将自动传递到客户端桌面。</p></td>
<td align="left"><p>由于服务器要求，企业拓扑中的占用量更大。</p>
<p>应用程序流应位于 LAN 上;通过 WAN 或在服务器与客户端之间使用不可靠或间歇性连接的部署方案可能无法使用。</p></td>
<td align="left"><p>需要流式处理基础结构。</p>
<p>用于将应用程序虚拟化桌面客户端软件部署到最终用户计算机的 Windows 安装程序。</p>
<p>大型企业应将应用程序虚拟化流服务器用作分发点。</p></td>
</tr>
<tr class="even">
<td align="left"><p>从文件包传递中加载</p></td>
<td align="left"><p>与典型的企业管理做法保持一致。</p>
<p>支持独立的配置方案。</p>
<p>提供对微型办事处问题的解决方案。</p></td>
<td align="left"><p>应用程序交付和更新不可能按需进行。</p>
<p>应用程序交付和更新不是增量操作;它会增加相对于动态传递的资源消耗。</p></td>
<td align="left"><p>IT 组织通常负责管理应用程序许可证、用户授权和身份验证。</p></td>
</tr>
</tbody>
</table>

 

## 与服务器相关的协议和外部组件


下表列出了可在基于应用程序虚拟化的方案中使用的服务器类型及其相应的传输协议和支持特定服务器配置所需的外部组件。 该表还包括每种服务器类型的报告机制和活动的升级机制。 由于这些方案都使用应用程序虚拟化管理服务器，因此你可以使用内置于系统的内部报表功能。 如果你使用应用程序虚拟化管理或应用程序虚拟流服务器向客户端发送程序包，则当用户登录到客户端时，服务器上的程序包会自动升级;如果使用 IIS 服务器或文件将程序包传递给客户端，则必须手动升级客户端上的程序包。

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
<th align="left">需要外部组件</th>
<th align="left">报告</th>
<th align="left">活动升级</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>应用程序虚拟化管理服务器</p></td>
<td align="left"><p>RTSP</p>
<p>RTSPS</p></td>
<td align="left"><p>使用 HTTPS 时，请使用 IIS 服务器下载 .ICO 和 OSD 文件和防火墙，以防止服务器暴露给 Internet。</p></td>
<td align="left"><p>内置</p></td>
<td align="left"><p>支持</p></td>
</tr>
<tr class="even">
<td align="left"><p>应用程序虚拟化流服务器</p></td>
<td align="left"><p>RTSP</p>
<p>RTSPS</p></td>
<td align="left"><p>使用一种机制来同步管理服务器和流服务器之间的内容。 使用 HTTPS 时，请使用 IIS 服务器下载 .ICO 和 OSD 文件，并使用防火墙保护服务器对 Internet 的暴露。</p></td>
<td align="left"><p>内置</p></td>
<td align="left"><p>支持</p></td>
</tr>
<tr class="odd">
<td align="left"><p>IIS 服务器</p></td>
<td align="left"><p>HTTP</p>
<p>HTTPS</p></td>
<td align="left"><p>使用一种机制来同步管理服务器和流服务器之间的内容。 使用 HTTP 或 HTTPS 时，请使用 IIS 服务器下载 .ICO 和 OSD 文件和防火墙，以防止服务器暴露给 Internet。</p></td>
<td align="left"><p>内置</p></td>
<td align="left"><p>不支持</p></td>
</tr>
<tr class="even">
<td align="left"><p>文件</p></td>
<td align="left"><p>SMB</p></td>
<td align="left"><p>你需要一种方法来同步管理服务器和流服务器之间的内容。 您需要具有文件共享或流功能的客户端计算机。</p></td>
<td align="left"><p>内置</p></td>
<td align="left"><p>不支持</p></td>
</tr>
</tbody>
</table>

 

## 相关主题


[基于电子软件分发的方案](electronic-software-distribution-based-scenario.md)

[如何为基于服务器的部署配置服务器](how-to-configure-servers-for-server-based-deployment.md)

[如何安装服务器和系统组件](how-to-install-the-servers-and-system-components.md)

 

 





