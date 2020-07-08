---
title: UNPUBLISH PACKAGE
description: UNPUBLISH PACKAGE
author: dansimp
ms.assetid: 1651427c-72a5-4701-bb57-71e14a7a3803
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7704fb3ed03be4864a837767d9e890d28b63f175
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798710"
---
# UNPUBLISH PACKAGE


允许删除整个程序包的快捷方式和文件类型。

`SFTMIME UNPUBLISH PACKAGE:package-name [/CLEAR] [/GLOBAL]                 [/LOG log-pathname | /CONSOLE | /GUI]`

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
<td align="left"><p>程序包的名称。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/CLEAR</p></td>
<td align="left"><p>如果存在，用户设置也将被删除。 （有关详细信息，请参阅本主题后面的重要说明。）</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/GLOBAL</p></td>
<td align="left"><p>如果存在，将取消发布此计算机上所有用户的程序包。</p></td>
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

 

**重要提示** 必须已将程序包添加到应用程序虚拟化客户端，然后才能运行 "**取消发布程序包**" 命令。

若要使用**全局**，**取消发布程序包**必须以本地管理员身份运行;否则，仅需要**ClearApp**权限。

将**取消发布程序包**与**全局**结合使用将删除程序包的所有全局文件类型和快捷方式。 "**清除**" 不适用。

使用**取消发布程序包**（不带**全局**）将删除程序包的用户快捷方式和文件类型，如果已设置 "**清除**"，则还会删除用户设置并停止用户上下文中的后台加载。

**取消发布程序包**适用于使用与**添加**、**编辑**和**发布程序包**的源 ID 相同的程序包名称或 GUID 的应用程序。

**取消发布程序包**始终清除所有用户设置、快捷方式和文件类型，而不管/CLEAR 开关的使用。

 

## 相关主题


[SFTMIME 命令引用](sftmime--command-reference.md)

 

 





