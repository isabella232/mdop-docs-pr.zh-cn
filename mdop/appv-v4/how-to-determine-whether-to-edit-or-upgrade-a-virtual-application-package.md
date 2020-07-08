---
title: 如何确定是编辑还是升级虚拟应用程序包
description: 如何确定是编辑还是升级虚拟应用程序包
author: dansimp
ms.assetid: 33dd5332-6802-46e0-9748-43fcc8f80aa3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b256a4927231613b6f2e688b5951adf57c9cb89a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801443"
---
# 如何确定是编辑还是升级虚拟应用程序包


使用下表来帮助确定是否可以打开虚拟应用程序包进行编辑，无论是需要创建新版本的程序包，还是使用 App-v 排序器的任一选项可用。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">操作</th>
<th align="left">打开进行编辑</th>
<th align="left">打开以升级</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>查看程序包属性。</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
</tr>
<tr class="even">
<td align="left"><p>查看程序包更改历史记录。</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
</tr>
<tr class="odd">
<td align="left"><p>查看关联的程序包文件。</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
</tr>
<tr class="even">
<td align="left"><p>编辑注册表设置。</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
</tr>
<tr class="odd">
<td align="left"><p>查看其他程序包设置（操作系统文件属性除外）。</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
</tr>
<tr class="even">
<td align="left"><p>创建关联的 Windows Installer （MSI）。</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
</tr>
<tr class="odd">
<td align="left"><p>修改 OSD 文件。</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
</tr>
<tr class="even">
<td align="left"><p>压缩和解压缩程序包。</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
</tr>
<tr class="odd">
<td align="left"><p>添加文件类型关联。</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
</tr>
<tr class="even">
<td align="left"><p>重命名快捷方式。</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
</tr>
<tr class="odd">
<td align="left"><p>设置虚拟化注册表项状态（替代/合并）。</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
</tr>
<tr class="even">
<td align="left"><p>设置虚拟化文件夹状态。</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
</tr>
<tr class="odd">
<td align="left"><p>编辑虚拟文件系统映射。</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
</tr>
<tr class="even">
<td align="left"><p>查看程序包的所有关联操作系统文件属性。</p></td>
<td align="left"><p>否</p></td>
<td align="left"><p>是</p></td>
</tr>
<tr class="odd">
<td align="left"><p>添加其他服务。</p></td>
<td align="left"><p>否</p></td>
<td align="left"><p>是</p></td>
</tr>
<tr class="even">
<td align="left"><p>添加其他文件。</p></td>
<td align="left"><p>否</p></td>
<td align="left"><p>是</p></td>
</tr>
<tr class="odd">
<td align="left"><p>收集和配置关联的安全描述符。</p></td>
<td align="left"><p>否</p></td>
<td align="left"><p>是</p></td>
</tr>
<tr class="even">
<td align="left"><p>应用安全更新或升级到新版本。</p></td>
<td align="left"><p>否</p></td>
<td align="left"><p>是</p></td>
</tr>
<tr class="odd">
<td align="left"><p>添加其他应用程序。</p></td>
<td align="left"><p>否</p></td>
<td align="left"><p>是</p></td>
</tr>
<tr class="even">
<td align="left"><p>应用需要打开应用程序的更新。</p></td>
<td align="left"><p>否</p></td>
<td align="left"><p>是</p></td>
</tr>
<tr class="odd">
<td align="left"><p>应用需要重新启动计算机的更新。</p></td>
<td align="left"><p>否</p></td>
<td align="left"><p>是</p></td>
</tr>
</tbody>
</table>

 

## 相关主题


[如何编辑现有的虚拟应用程序](how-to-edit-an-existing-virtual-application.md)

[如何升级现有的虚拟应用程序](how-to-upgrade-an-existing-virtual-application.md)

 

 





