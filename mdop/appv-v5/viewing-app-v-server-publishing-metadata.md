---
title: 查看 App-V 服务器发布元数据
description: 查看 App-V 服务器发布元数据
author: dansimp
ms.assetid: 048dd42a-24d4-4cc4-81f6-7a919aadd9b2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 304aa656de98a0c9d59f0a6166811ead911033ad
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798252"
---
# 查看 App-V 服务器发布元数据


使用此过程可查看发布元数据，这有助于解决与发布相关的问题。 必须使用 App-v 管理服务器才能使用此过程。

本文包含以下信息：

-   [用于查看发布元数据的 app-v 5.0 SP3 要求](#bkmk-50sp3-reqs-pub-meta)

-   [用于查看发布元数据的语法](#bkmk-syntax-view-pub-meta)

-   [客户端操作系统和版本的查询值](#bkmk-values-query-pub-meta)

-   [发布元数据的定义](#bkmk-whatis-pub-metadata)

## <a href="" id="bkmk-50sp3-reqs-pub-meta"></a>用于查看发布元数据的 app-v 5.0 SP3 要求


在 App-v 5.0 SP3 中，当你查询用于元数据的 app-v 发布服务器时，必须在地址中提供以下值：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">值</th>
<th align="left">其他详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>ClientVersion</strong></p></td>
<td align="left"><p>如果省略查询中的 <strong> ClientVersion </strong> 参数，则元数据将排除新的 APP-V 5.0 SP3 功能。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>ClientOS</strong></p></td>
<td align="left"><p>只有在对程序包进行排序时选择特定客户端操作系统时，才必须提供此值。 如果选择 "默认（所有操作系统）"，请不要在查询中指定此值。</p>
<p>如果省略查询中的 <strong> ClientOS </strong> 参数，则只有已排序支持任何操作系统的程序包才会显示在元数据中。</p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-syntax-view-pub-meta"></a>用于查看发布元数据的查询语法


下表提供了语法和查询示例。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">App-v 版本</th>
<th align="left">查询语法</th>
<th align="left">参数说明</th>
<th align="left">示例</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>App-v 5.0 SP3</p></td>
<td align="left"><p><code>http://&lt;PubServer&gt;:&lt;Publishing Port#&gt;/?ClientVersion=&lt;AppvClientVersion&gt;&amp;ClientOS=&lt;OSStringValue&gt;</code></p></td>
<td align="left"><table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">参数</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>&lt;PubServer&gt;</p></td>
<td align="left"><p>App-v 发布服务器的名称。</p></td>
</tr>
<tr class="even">
<td align="left"><p>&lt;发布端口#&gt;</p></td>
<td align="left"><p>指向在配置发布服务器时定义的 app-v 发布服务器的端口。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ClientVersion = &lt; AppvClientVersion&gt;</p></td>
<td align="left"><p>App-v 客户端的版本。 请参考下表，以获取正确的值以供使用。</p></td>
</tr>
<tr class="even">
<td align="left"><p>ClientOS = &lt; OSStringValue&gt;</p></td>
<td align="left"><p>运行 App-v 客户端的计算机的操作系统。 请参考下表，以获取正确的值以供使用。</p></td>
</tr>
</tbody>
</table>
<p> </p>
<p>若要从 App-v 客户端获取发布服务器和端口号（http:// &lt; PubServer &gt; ： &lt; 发布端口 # &gt; ）的名称，请查看 <strong> AppvPublishingServer PowerShell cmdlet 的 URL 配置 </strong> 。</p></td>
<td align="left"><p><code><a href="http://pubsvr01:2718/?clientversion=5.0.10066.0&amp;clientos=WindowsClient_6.2_x64" data-raw-source="http://pubsvr01:2718/?clientversion=5.0.10066.0&amp;amp;clientos=WindowsClient_6.2_x64">http://pubsvr01:2718/?clientversion=5.0.10066.0&amp;clientos=WindowsClient_6.2_x64</a></code></p>
<p>在示例中：</p>
<ul>
<li><p>名为 "pubsvr01" 的 Windows Server 2012 R2 托管发布服务。</p></li>
<li><p>Windows 客户端是 Windows 8.1 64 位。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>App-v 5.0 至 App-V 5.0 SP2</p></td>
<td align="left"><p><code>http://&lt;PubServer&gt;:&lt;Publishing Port#&gt;/ </code></p>
<div class="alert">
<strong>注意</strong><br/><p><strong>ClientVersion </strong> 和 <strong> ClientOS </strong> 仅在 app-v 5.0 SP3 中受支持。</p>
</div>
<div>

</div></td>
<td align="left"><p>请参阅 App-v 5.0 SP3 的信息。</p></td>
<td align="left"><p><code><a href="http://pubsvr01:2718" data-raw-source="http://pubsvr01:2718">http://pubsvr01:2718</a></code></p>
<p>在此示例中，名为 "pubsvr01" 的 Windows Server 2012 R2 托管了管理和发布服务。</p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-values-query-pub-meta"></a>客户端操作系统和版本的查询值


在 "发布元数据" 查询中，输入与你正在使用的客户端操作系统和版本对应的字符串值。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">操作系统</th>
<th align="left">体系结构</th>
<th align="left">操作字符串字符串值</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows 8.1</p></td>
<td align="left"><p>64 位</p></td>
<td align="left"><p>WindowsClient_6。2_x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows 8.1</p></td>
<td align="left"><p>32 位</p></td>
<td align="left"><p>WindowsClient_6。2_x86</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows 8</p></td>
<td align="left"><p>64 位</p></td>
<td align="left"><p>WindowsClient_6。2_x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows 8</p></td>
<td align="left"><p>32 位</p></td>
<td align="left"><p>WindowsClient_6。2_x86</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server 2012 R2</p></td>
<td align="left"><p>64 位</p></td>
<td align="left"><p>WindowsServer_6。2_x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server 2012 R2</p></td>
<td align="left"><p>32 位</p></td>
<td align="left"><p>WindowsServer_6。2_x86</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server 2012</p></td>
<td align="left"><p>64 位</p></td>
<td align="left"><p>WindowsServer_6。2_x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server 2012</p></td>
<td align="left"><p>32 位</p></td>
<td align="left"><p>WindowsServer_6。2_x86</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows 7</p></td>
<td align="left"><p>64 位</p></td>
<td align="left"><p>WindowsClient_6。1_x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows 7</p></td>
<td align="left"><p>32 位</p></td>
<td align="left"><p>WindowsClient_6。1_x86</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server 2008 R2</p></td>
<td align="left"><p>64 位</p></td>
<td align="left"><p>WindowsServer_6。1_x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server 2008 R2</p></td>
<td align="left"><p>32 位</p></td>
<td align="left"><p>WindowsServer_6。1_x86</p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-whatis-pub-metadata"></a>发布元数据的定义


将程序包发布到运行 App-v 客户端的计算机时，将向该计算机发送元数据，指示正在发布哪些程序包和连接组。 App-v 客户端对以下两个单独的请求进行请求：

-   客户端计算机有权享有的程序包和连接组。

-   当前用户有权使用的程序包和连接组。

发布服务器与管理服务器通信，以确定请求者可以使用哪些程序包和连接组。 发布服务器必须注册到管理服务器才能生成元数据。

你可以使用特定用户或计算机上下文中的查询，在 Internet 浏览器中查看每个请求的元数据。






## 相关主题


[App-V 5.0 技术参考](technical-reference-for-app-v-50.md)









