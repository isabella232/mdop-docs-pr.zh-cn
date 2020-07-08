---
title: HELP
description: HELP
author: dansimp
ms.assetid: 0ddb5f18-0c0a-45ea-b7c7-2d4749e3d35d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 395e6199529ccbe708aa7d1ac6673ea6f9494ae4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802973"
---
# HELP


显示有关可在应用程序虚拟化（app-v）中使用的各种 SFTMIME 命令的信息。

## HELP


`SFTMIME [/? | /HELP [VERB:<verb>]]`

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
<td align="left"><p>/？、/HELP</p></td>
<td align="left"><p>显示使用信息。</p></td>
</tr>
<tr class="even">
<td align="left"><p>谓词</p></td>
<td align="left"><p>要运行的命令，如 "添加"、"刷新"、"帮助" 或 "删除"。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>object</p></td>
<td align="left"><p>该命令的应用方式，如应用： &quot; 默认应用程序。&quot;</p></td>
</tr>
<tr class="even">
<td align="left"><p>实参</p></td>
<td align="left"><p>指定动词和对象的可选参数。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/LOG</p></td>
<td align="left"><p>将输出记录到指定的路径名称。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/CONSOLE</p></td>
<td align="left"><p>在活动控制台窗口中显示输出（默认）。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/GUI</p></td>
<td align="left"><p>显示对话框中的错误（对于查询无效）。</p></td>
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

 

下表中所述的谓词受支持。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p>ADD</p></td>
<td align="left"><p>将新的应用程序、程序包、文件类型关联或发布服务器添加到 App-v 客户端。</p></td>
</tr>
<tr class="even">
<td align="left"><p>对</p></td>
<td align="left"><p>更改应用程序、程序包、文件类型关联或发布服务器的配置。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>DELETE</p></td>
<td align="left"><p>删除应用程序、程序包、文件类型关联或服务器。</p></td>
</tr>
<tr class="even">
<td align="left"><p>载量</p></td>
<td align="left"><p>将程序包加载到文件系统缓存中。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>修复</p></td>
<td align="left"><p>重置应用程序的个人设置。</p></td>
</tr>
<tr class="even">
<td align="left"><p>恢复</p></td>
<td align="left"><p>触发发布服务器刷新。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>发布</p></td>
<td align="left"><p>将应用程序快捷方式发布到用户的 "开始" 菜单、"桌面" 或其他指定位置，或者可用于发布整个程序包的内容。</p></td>
</tr>
<tr class="even">
<td align="left"><p>发布</p></td>
<td align="left"><p>删除整个程序包的快捷方式和文件类型。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>查询</p></td>
<td align="left"><p>获取应用程序、程序包、文件类型关联或发布服务器的当前列表。</p></td>
</tr>
<tr class="even">
<td align="left"><p>消除</p></td>
<td align="left"><p>删除一个或多个应用程序的个人设置和桌面配置。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>卸载</p></td>
<td align="left"><p>从文件系统缓存中卸载程序包。</p></td>
</tr>
<tr class="even">
<td align="left"><p>形</p></td>
<td align="left"><p>锁定在文件系统缓存中指定的应用程序。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>钥匙</p></td>
<td align="left"><p>解除锁定文件系统缓存中指定的应用程序。</p></td>
</tr>
</tbody>
</table>

 

有关上述操作的详细信息，请使用以下命令：

`SFTMIME /HELP VERB:verb`

例如，以下命令将显示 ADD 谓词的信息：

`SFTMIME /HELP VERB:ADD`

## 相关主题


[SFTMIME 命令引用](sftmime--command-reference.md)

 

 





