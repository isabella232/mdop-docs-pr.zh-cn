---
title: ADD TYPE
description: ADD TYPE
author: dansimp
ms.assetid: 8f1d3978-9977-4851-9f46-fee6aefa3535
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4d2dcfb24a32dc733aa91b5534e0011090ef12b9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803157"
---
# ADD TYPE


添加指定的文件类型关联。

`SFTMIME ADD TYPE:file-extension /APP application [/ICON icon-pathname]                 [/DESCRIPTION type-desc] [/CONTENT-TYPE content-type] [/GLOBAL]                 [/PERCEIVED-TYPE perceived-type] [/PROGID progid]                 [/CONFIRMOPEN {YES|NO}] [/SHOWEXT {YES|NO}]                 [/NEWMENU {YES|NO}]  [/LOG log-pathname | /CONSOLE | /GUI]`

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
<td align="left"><p>类型： &lt; 文件扩展名&gt;</p></td>
<td align="left"><p>将与指定的应用程序相关联的文件扩展名。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/APP &lt; 应用程序&gt;</p></td>
<td align="left"><p>应用程序的名称和版本（可选）。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/ICON &lt; 图标-pathname&gt;</p></td>
<td align="left"><p>图标文件的路径或 URL。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/DESCRIPTION &lt; 类型-desc&gt;</p></td>
<td align="left"><p>文件类型的用户友好名称。 默认为 &quot; 扩展文件。&quot;</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/CONTENT-TYPE &lt; 内容类型&gt;</p></td>
<td align="left"><p>文件的内容类型。 默认为 &quot; application/softricity-extension。&quot;</p></td>
</tr>
<tr class="even">
<td align="left"><p>/GLOBAL</p></td>
<td align="left"><p>如果存在，则此计算机上的所有用户都可以使用该程序包。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/PERCEIVED-TYPE &lt; 感知-类型&gt;</p></td>
<td align="left"><p>文件的假设类型。 默认值为 nothing。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/PROGID &lt; PROGID&gt;</p></td>
<td align="left"><p>文件类型的编程标识符。 默认值为 App Virt 文件。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/CONFIRMOPEN</p></td>
<td align="left"><p>指示是否应询问用户是否要打开或保存此类文件。 默认值为 "是"。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/SHOWEXT</p></td>
<td align="left"><p>指示是否应始终显示文件的扩展名，即使用户已请求隐藏所有扩展名也是如此。 默认值为 "否"。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/NEWMENU</p></td>
<td align="left"><p>指示是否应将某个条目添加到外壳的 " <strong> 新建" </strong> 菜单。 默认值为 "否"。</p></td>
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

 

 





