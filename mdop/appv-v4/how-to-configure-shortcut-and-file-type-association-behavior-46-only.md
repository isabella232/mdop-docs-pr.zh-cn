---
title: 如何配置快捷方式和文件类型关联行为
description: 如何配置快捷方式和文件类型关联行为
author: dansimp
ms.assetid: d6fd1728-4de6-4066-b36b-d4837d593d40
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 84e3e0cdd43cfc26cf56f1b5ac72560b1c702ae6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801607"
---
# 如何配置快捷方式和文件类型关联行为


快捷方式和文件类型关联（FTA）发布策略由发布 XML 文件定义和控制，发布 XML 文件在发布刷新操作期间由发布服务器发送给客户端。 当客户端收到此信息时，它将添加有关应用程序（如图标和 FTAs）的任何新发布的数据。 然后，它会删除任何过时的发布数据。

在 App-v 版本4.6 中，定义了两个注册表项值以使管理员能够控制此行为。 默认情况下，使用客户端控制台在本地创建的快捷方式现在保留。

## 如何更改快捷方式和 FTA 行为


已为客户端配置注册表项、"FileTypePolicy" 和 "ShortcutPolicy" 定义了两个新的 DWORD 注册表值。 默认情况下不显示这些 DWORD 注册表值，但可以手动添加它们。 配置注册表项位于 HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\\ [Wow6432Node\\\] Microsoft\\SoftGrid\\4.5\\Client\\Configuration。

下表中定义了四个策略值，它们均适用于两个注册表项值。 以下列表显示了注册表设置的数值，以及应用于发布刷新操作上的文件类型或快捷方式的行为。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p>名称</p></td>
<td align="left"><p>类型</p></td>
<td align="left"><p>数据（示例）</p></td>
<td align="left"><p>描述</p></td>
</tr>
<tr class="even">
<td align="left"><p>FileTypePolicy</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>默认值 = 0x2 （App-v 4.6）</p></td>
<td align="left"><p>（0x0）-"ClientOnly"-删除同一发布信息源中的所有现有项目，并仅保留本地添加的项目</p>
<p>（0x1）-"ServerOnly"-从同一发布信息源和任何本地添加的项目中删除任何过时项目，并添加新项目</p>
<p>（0x2）-"ClientAndServer"-从同一发布信息源中删除任何过时的项目、将添加的项目保留在本地，并添加新项目（如果不存在，则默认为 app-v 4.6）</p>
<p>（0x3）-"NoChange"-不对文件类型或快捷方式进行任何更改</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ShortcutPolicy</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>默认值 = 0x2</p></td>
<td align="left"><p>（0x0）-"ClientOnly"-删除同一发布信息源中的所有现有项目，并仅保留本地添加的项目</p>
<p>（0x1）-"ServerOnly"-删除同一发布信息源和本地添加的任何项目中的任何过时项目，并添加新项目</p>
<p>（0x2）-"ClientAndServer"-从同一发布信息源中删除任何过时项目，将项目添加到本地并添加新项目（如果不存在，则为默认值）</p>
<p>（0x3）-"NoChange"-不对文件类型或快捷方式进行任何更改</p></td>
</tr>
</tbody>
</table>

 

**注意** 文本值指发布 XML 文件中的 XML 属性的值。如果已实现自定义 HTTP 发布解决方案，则可以手动设置这些值。

 

 

 





