---
title: PUBLISH APP
description: PUBLISH APP
author: dansimp
ms.assetid: f25f06a8-ca23-435b-a0c2-16a5f39b6b97
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b2ccb19255786ee47a8356feef14be1c4d9b4fb2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798847"
---
# PUBLISH APP


将应用程序快捷方式发布到用户的 "开始" 菜单、"桌面" 或其他指定位置。

`SFTMIME PUBLISH APP:application                 {/DESKTOP | /START | /TARGET target-path} [/ICON icon-pathname]                 [/DISPLAY display-name] [/ARGS command-args...]                 [/LOG log-pathname | /CONSOLE | /GUI]`

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
<td align="left"><p>应用程序： &lt; 应用程序&gt;</p></td>
<td align="left"><p>应用程序的名称和版本（可选）。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/DESKTOP</p></td>
<td align="left"><p>发布用户桌面的快捷方式。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/START</p></td>
<td align="left"><p>发布 "开始" 菜单的 "程序" 文件夹中的 "应用程序虚拟化应用程序" 文件夹的快捷方式。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/TARGET &lt; 目标路径&gt;</p></td>
<td align="left"><p>应在其中发布快捷方式的绝对路径。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/ICON &lt; 图标-pathname&gt;</p></td>
<td align="left"><p>图标文件的路径或 URL。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/DISPLAY &lt; 显示名称&gt;</p></td>
<td align="left"><p>快捷方式的显示名称。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/ARGS &lt; 命令-参数&gt;</p></td>
<td align="left"><p>要传递到应用程序的参数。</p></td>
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

 

 





