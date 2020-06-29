---
title: ADD PACKAGE
description: ADD PACKAGE
author: dansimp
ms.assetid: aa83928d-a234-4395-831e-2a7ef786ff53
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 925349ce5bdf041b6a8768b5413692966e1cfc1e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803160"
---
# ADD PACKAGE


添加程序包记录。 如果程序包已存在，此命令将更新现有程序包的配置。

`SFTMIME ADD PACKAGE:package-name /MANIFEST manifest-path                 [/OVERRIDEURL url [/AUTOLOADONREFRESH] [/AUTOLOADONLOGIN]                 [/AUTOLOADONLAUNCH] [/AUTOLOADTARGET {NONE|ALL|PREVUSED}]                 [/GLOBAL] [/LOG log-pathname | /CONSOLE | /GUI]`

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
<td align="left"><p>程序包： &lt; 软件包-name&gt;</p></td>
<td align="left"><p>程序包的用户可见名称和用户友好名称。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/MANIFEST &lt; 清单-path&gt;</p></td>
<td align="left"><p>列出程序包中包含的应用程序及其所有发布信息的清单文件的路径。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/OVERRIDEURL &lt; URL&gt;</p></td>
<td align="left"><p>程序包的 SFT 文件的位置。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/AUTOLOADONREFRESH</p></td>
<td align="left"><p>在发布刷新后执行后台加载。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/AUTOLOADONLOGIN</p></td>
<td align="left"><p>在用户登录时执行后台加载。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/AUTOLOADONLAUNCH</p></td>
<td align="left"><p>在用户从程序包启动应用程序后执行后台加载。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/AUTOLOADTARGET 目标</p></td>
<td align="left"><p>指示程序包中将 autoloaded 的应用程序。</p></td>
</tr>
<tr class="even">
<td align="left"><p>尚</p></td>
<td align="left"><p>尽管存在任何/AUTOLOADONxxx 标志，也不会执行任何 autoloading。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>所有</p></td>
<td align="left"><p>如果启用了 autoload 触发器，则程序包中的所有应用程序都将加载到缓存中，无论它们以前是否已启动。</p></td>
</tr>
<tr class="even">
<td align="left"><p>PREVUSED</p></td>
<td align="left"><p>如果启用了 autoload 触发器，则在此程序包中的任何应用程序之前已由用户启动时，将加载该程序包。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/GLOBAL</p></td>
<td align="left"><p>如果存在，则此计算机上的所有用户都可以使用该程序包。</p></td>
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

 

 





