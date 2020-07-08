---
title: PUBLISH PACKAGE
description: PUBLISH PACKAGE
author: dansimp
ms.assetid: a33e72dd-194f-4283-8e99-4584ab13de53
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 00b63389986f495d9405939245a50575bae453f9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798846"
---
# PUBLISH PACKAGE


发布整个程序包的内容。

`SFTMIME PUBLISH PACKAGE:package-name /MANIFEST manifest-path [/GLOBAL]                 [/LOG log-pathname | /CONSOLE | /GUI]`

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

 

**重要提示** 该包必须已添加到应用程序虚拟化客户端，并且需要清单文件。

若要使用**全局**参数，必须以本地管理员身份运行 "发布包" 命令;否则，仅需要**ManageTypes**和**PublishShortcut**权限。

不带**全局**参数的发布授予用户对程序包中应用程序的访问权限，并将清单中列出的文件类型和快捷方式发布到用户的配置文件中。

通过**全局**参数进行发布将清单中列出的文件类型和快捷方式添加到 "所有用户" 配置文件。

如果在呼叫和使用**全局**参数时程序包不是全局程序包，则会将该程序包设置为全局，并向所有用户提供。

 

## 相关主题


[SFTMIME 命令引用](sftmime--command-reference.md)

 

 





