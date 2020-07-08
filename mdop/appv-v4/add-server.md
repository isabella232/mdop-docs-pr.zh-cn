---
title: ADD SERVER
description: ADD SERVER
author: dansimp
ms.assetid: 4be2ac2e-a410-4711-9f84-f305393c8fa7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e15a5943b40e14b2f9031bf8b3ddffa693e32dea
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802396"
---
# ADD SERVER


添加发布服务器。

`SFTMIME ADD SERVER:server-name /HOST hostname /TYPE {HTTP|RTSP}                 /PATH path [/PORT port] [/REFRESH {ON|OFF}] [/SECURE]                 [/LOG log-pathname | /CONSOLE | /GUI]`

<table>
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
<td align="left"><p>服务器： &lt; 服务器名称&gt;</p></td>
<td align="left"><p>发布服务器的显示名称。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/HOST &lt; 主机名&gt;</p></td>
<td align="left"><p>发布服务器的主机名或 IP 地址。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/TYPE {HTTP |RTSP</p></td>
<td align="left"><p>指示发布服务器是 Web 服务器（ &quot; HTTP &quot; ）还是应用程序虚拟化服务器（ &quot; RTSP &quot; ）。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/PORT &lt; 端口&gt;</p></td>
<td align="left"><p>发布服务器侦听的端口。 对于使用增强安全性的 HTTP 服务器443，对于使用554增强安全性的 HTTP 服务器，80的默认值为; 对于使用增强安全性的服务器，则默认为322。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/PATH &lt; 路径&gt;</p></td>
<td align="left"><p>发布请求中使用的 URL 的路径部分。 如果 TYPE 参数设置为 RTSP，则路径是可选的，并且默认为 &quot; / &quot; 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/REFRESH</p></td>
<td align="left"><p>如果设置为 "开"，则在用户登录时将刷新发布信息。 默认值为 "开"。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/SECURE</p></td>
<td align="left"><p>如果存在，则表示应建立与发布服务器的增强安全性的连接。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/LOG</p></td>
<td align="left"><p>如果指定，输出将记录到指定的路径名称。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/CONSOLE</p></td>
<td align="left"><p>如果指定，将在活动控制台窗口中显示输出（默认）。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/GUI</p></td>
<td align="left"><p>如果指定，将在 Windows 对话框中显示输出。</p></td>
</tr>
</tbody>
</table>

 

对于版本4.6，已添加以下选项。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p>/LOGU</p></td>
<td align="left"><p>如果指定，将以 UNICODE 格式将输出记录到指定的路径名称。</p></td>
</tr>
</tbody>
</table>

 

## 相关主题


[SFTMIME 命令引用](sftmime--command-reference.md)

 

 





