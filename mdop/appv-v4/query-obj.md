---
title: QUERY OBJ
description: QUERY OBJ
author: dansimp
ms.assetid: 55abf0d1-c779-4172-8357-552ab010933b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 328e9feb96c70080531cbbc666d8ff1b86045ba5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798831"
---
# QUERY OBJ


返回由 tab 分隔的当前应用程序、程序包、文件类型关联或发布服务器的列表。

`SFTMIME QUERY OBJ:{APP|PACKAGE|TYPE|SERVER} [/SHORT] [/GLOBAL]                 [/LOG log-pathname | /CONSOLE ]`

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
<td align="left"><p>应用</p></td>
<td align="left"><p>返回应用程序的列表。</p></td>
</tr>
<tr class="even">
<td align="left"><p>程序包</p></td>
<td align="left"><p>返回程序包列表。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>类型</p></td>
<td align="left"><p>返回文件类型关联的列表。</p></td>
</tr>
<tr class="even">
<td align="left"><p>服务</p></td>
<td align="left"><p>返回发布服务器的列表。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/SHORT</p></td>
<td align="left"><p>如果不显示每个属性的完整属性，则返回应用程序名称、程序包、关联或服务器名称的列表。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/GLOBAL</p></td>
<td align="left"><p>对于应用程序，返回所有已知的应用程序，而不是当前用户有权访问的应用程序。 对于程序包，返回所有已知程序包，而不是当前用户有权访问的程序包。 对于关联，仅返回适用于所有用户（而不是特定于用户的用户）的关联。 对服务器无效。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/LOG</p></td>
<td align="left"><p>如果指定，输出将记录到指定的路径名称。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/CONSOLE</p></td>
<td align="left"><p>如果指定，将在活动控制台窗口中显示输出（默认）。</p></td>
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

 

**注意** 在版本4.6 中，已将新列添加到 SFTMIME 查询 OBJ： APP \ [/GLOBAL\] 的输出。 输出的最后一列是指示是否发布应用程序的数字值。

已发布 = 1 表示应用程序由发布服务器刷新所发布，通过使用 Windows Installer 文件（）安装应用程序。MSI），或者通过运行 SFTMIME 添加程序包，使用程序包清单配置程序包或发布程序包命令。

已发布 = 0 表示应用程序尚未发布，或者由于执行清除操作或运行 SFTMIME 取消发布命令而不再发布该应用程序。

如果你使用/GLOBAL 参数，则发布状态将为1，适用于全局发布的应用程序，而对于在用户上下文中发布的应用程序，则为0。 如果没有/GLOBAL 参数，将为运行该命令的用户上下文中发布的应用程序返回1的已发布状态，并为全局发布的应用程序返回0的状态。

 

SFTMIME 查询 OBJ 命令可用于查询上面显示的所有对象（应用程序、程序包、文件类型关联和服务器）的相关信息。若要显示如何在正常操作任务中使用 SFTMIME 查询 OBJ 命令，下面的示例演示了要为特定程序包设置 OVERRIDEURL 参数值时应遵循的过程，以指定程序包内容的新路径。 

1.  若要查找要配置的程序包，请运行以下命令：

    `SFTMIME QUERY OBJ:PACKAGE`

    此命令将在输出的第一列中以 GUID 的形式返回每个发现的程序包名称，例如 {AF78ABE1-57D4-4297-89DE-C308684AEDD6}。

2.  若要设置 OVERRIDEURL 参数值，请使用 "SFTMIME[配置包](configure-package.md)" 命令。 例如，若要将此程序包的 OVERRIDEURL 值设置为*\\\\server\\share\\mypackage.sft*值，请使用 SFTMIME 的 "配置程序包" 命令，并从步骤1中 SFTMIME 查询 OBJ 命令的输出中为它提供所选的程序包 GUID，后跟 OVERRIDEURL 参数及其新值，如下所示：

    `SFTMIME CONFIGURE PACKAGE:"{AF78ABE1-57D4-4297-89DE-C308684AEDD6}" /OVERRIDEURL "\\\\server\\share\\mypackage.sft "`

对于版本 4.6 SP2，已添加以下选项。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p>/NO-UPDATE-FTA-SHORTCUT</p></td>
<td align="left"><p>指示/NO-UPDATE-FTA-SHORTCUT 标志的当前状态。</p></td>
</tr>
</tbody>
</table>

 

## 相关主题


[SFTMIME 命令引用](sftmime--command-reference.md)

 

 





