---
title: CONFIGURE PACKAGE
description: CONFIGURE PACKAGE
author: dansimp
ms.assetid: acc7eaa8-6ada-47b9-a655-2ca2537605b9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: dc8b315b68349cc9834316786b0bf15d4ac3c5cd
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802180"
---
# CONFIGURE PACKAGE


允许用户更改程序包的程序包清单文件、程序包源、加载触发器类型或加载目标。

`SFTMIME CONFIGURE PACKAGE:package-name [/MANIFEST manifest-path]                 [/OVERRIDEURL url] [/AUTOLOADNEVER] [/AUTOLOADONREFRESH]                 [/AUTOLOADONLOGIN] [/AUTOLOADONLAUNCH]                 [/AUTOLOADTARGET {NONE|ALL|PREVUSED}]                 [/LOG log-pathname | /CONSOLE | /GUI]                 [/NO-UPDATE-FTA-SHORTCUT {TRUE|FALSE} {/GLOBAL}]`

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
<td align="left"><p>列出程序包中包含的应用程序及其所有发布信息的清单文件的路径或 URL。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/OVERRIDEURL &lt; URL&gt;</p></td>
<td align="left"><p>程序包的 SFT 文件的位置。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/AUTOLOADNEVER</p></td>
<td align="left"><p>程序包的后台加载已关闭。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/AUTOLOADONREFRESH</p></td>
<td align="left"><p>在发布刷新后执行后台加载。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/AUTOLOADONLOGIN</p></td>
<td align="left"><p>在用户登录时执行后台加载。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/AUTOLOADONLAUNCH</p></td>
<td align="left"><p>在用户从程序包启动应用程序后执行后台加载。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/AUTOLOADTARGET &lt; 目标&gt;</p></td>
<td align="left"><p>指示程序包中将 autoloaded 的应用程序。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>尚</p></td>
<td align="left"><p>尽管存在任何/AUTOLOADONxxx 标志，也不会执行任何 autoloading。</p></td>
</tr>
<tr class="even">
<td align="left"><p>所有</p></td>
<td align="left"><p>如果启用了 autoload 触发器，则程序包中的所有应用程序都将加载到缓存中，无论它们是否曾被启动。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>PREVUSED</p></td>
<td align="left"><p>如果启用了 autoload 触发器，则在此程序包中的任何应用程序之前已由用户启动时，将加载该程序包。</p></td>
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

 

对于版本 4.6 SP2，已添加以下选项。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p>[/NO-UPDATE-FTA-SHORTCUT {TRUE |FALSE} {/GLOBAL}]</p></td>
<td align="left"><p>如果设置为 TRUE，则为程序包（每用户）创建注册表值，如果指定了/GLOBAL 标志，则为全局。</p>
<p>如果设置为 FALSE，将删除注册表值并重新安装程序包的文件类型关联（FTA）。</p>
<p>如果未指定，则会发生正常的 FTA 和快捷方式发布行为。 如果在 App-V 4.6 SP2 客户端上执行任何后续的发布刷新操作，则不会更改具有此注册表值设置的程序包的快捷方式和 FTAs，并且不会在系统启动或用户登录时注册快捷方式和 FTAs，除非你重置该标记。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/GLOBAL</p></td>
<td align="left"><p>与/NO-UPDATE-FTA-SHORTCUT 标志配合使用。 如果/GLOBAL 标志存在，则表示将为所有用户创建该程序包的注册表值。 默认情况下，仅为此用户创建注册表值。</p></td>
</tr>
</tbody>
</table>

 

## 相关主题


[SFTMIME 命令引用](sftmime--command-reference.md)

 

 





