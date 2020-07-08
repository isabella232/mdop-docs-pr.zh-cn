---
title: 如何使用 PowerShell 命令执行 DaRT 任务
description: 如何使用 PowerShell 命令执行 DaRT 任务
author: dansimp
ms.assetid: f5a5c5f9-d667-4c85-9e82-7baf0b2aec6e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fdf167ca81281da4e04dae10e34bad6122ec05aa
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803200"
---
# 如何使用 PowerShell 命令执行 DaRT 任务


Microsoft 诊断和恢复工具集（DaRT）10提供以下列出的一组 Windows PowerShell cmdlet。 管理员可以使用这些 PowerShell cmdlet 从命令提示符而不是从 DaRT 恢复映像向导执行各种 DaRT 10 服务器任务。

## 使用 PowerShell 命令管理 DaRT


使用此处介绍的 PowerShell cmdlet 管理 DaRT。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">名称</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Copy-DartImage</p></td>
<td align="left"><p>将 ISO 刻录到 CD、DVD 或 USB 驱动器。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Export-DartImage</p></td>
<td align="left"><p>允许将包含 DaRT 映像的源 WIM 文件转换为 ISO 文件。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>新-DartConfiguration</p></td>
<td align="left"><p>创建将 DaRT 工具集应用于 Windows 映像所需的 DaRT 配置对象。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Set-DartImage</p></td>
<td align="left"><p>将 DartConfiguration 对象应用于已安装的 Windows 映像。 这包括添加所有文件、配置和程序包依赖关系。</p></td>
</tr>
</tbody>
</table>

 

## 相关主题


[使用 PowerShell 管理 DaRT 10](administering-dart-10-using-powershell.md)

 

 





