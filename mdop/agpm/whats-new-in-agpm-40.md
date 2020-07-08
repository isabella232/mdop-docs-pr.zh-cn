---
title: AGPM 4.0 中的新增功能
description: AGPM 4.0 中的新增功能
author: dansimp
ms.assetid: 31775f7f-a59c-4e64-a875-0adc9f5bc835
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 82b4445a7d22fb7c1ef4f42d896f11908a22f2f5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802483"
---
# AGPM 4.0 中的新增功能


Microsoft 高级组策略管理（AGPM）4.0 包含新功能，可让你搜索组策略对象（Gpo）、筛选所显示的 Gpo 列表、将 GPO 导出和导入到其他林，以及在运行 Windows7 和 Windows Server2008R2 的计算机上安装 AGPM。

## 搜索和筛选 Gpo


在 AGPM 4.0 中，你可以在 Gpo 列表中搜索特定属性，以筛选所显示的 Gpo 列表。 例如，您可以搜索具有特定名称、状态或注释的 Gpo。 你还可以搜索特定组策略管理员或特定日期上次更改的 Gpo。

你可以使用 format *GPO 属性1：搜索文本 1 GPO 属性2：搜索文本 2 ...*，其中 gpo 属性是 AGPM 中 gpo 列表中的任意列标题。 例如，若要搜索名称中包含已签入并由用户 Editor03 最后更改的文本 "MyGPO" 的所有 Gpo，请在 "搜索" 框中键入以下内容：**名称： MyGPO 状态：****"** 已**更改者： Editor03**"。 搜索返回部分匹配，以便你可以输入 GPO 名称或用户名的一部分，并查看其名称中包含该文本的所有 Gpo 的列表。

此外，你可以使用在 Windows 中搜索时可用的相同特殊条件搜索在特定日期或日期范围内更改的 Gpo。 例如，**更改日期：****lastmonth**或**更改日期：****thisweek**。

## 将 Gpo 导出并导入到不同的林


使用 AGPM 4.0，您可以将一个目录林中的域的受控 GPO 复制到第二个林中的域。 例如，你可以通过使用 AGPM 将 GPO 从一个林中的域导出到 CAB 文件，将该 CAB 文件复制到一个 USB 驱动器，将 USB 驱动器插入第二个林中的域中的计算机，然后将该 GPO 导入到第二个林中的域中的 AGPM 中。 你可以将 GPO 作为新的受控 GPO 导入，或将其导入以替换已签出的现有 GPO 的设置。

## Windows Server 2008 R2 和 Windows 7 支持


AGPM 4.0 支持 Windows Server2008R2 和 Windows7，但仍支持 Windows Server2008 和 WindowsVista® Service Pack1 （SP1）。 但是，混合环境中存在限制，包括更新的旧操作系统，如下表所示。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">在其上运行 AGPM 服务器4.0 的操作系统</th>
<th align="left">在其上运行 AGPM 客户端4.0 的操作系统</th>
<th align="left">AGPM 4.0 支持的状态</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows Server2008R2 或 Windows7</p></td>
<td align="left"><p>Windows Server2008R2 或 Windows7</p></td>
<td align="left"><p>支持</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2008R2 或 Windows7</p></td>
<td align="left"><p>Windows Server2008 或 Windows Vista SP1</p></td>
<td align="left"><p>受支持，但不能编辑仅存在于 Windows Server2008R2 或 Windows7 中的策略设置或首选项</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2008 或 Windows Vista SP1</p></td>
<td align="left"><p>Windows Server2008R2 或 Windows7</p></td>
<td align="left"><p>不支持</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2008 或 Windows Vista SP1</p></td>
<td align="left"><p>Windows Server2008 或 Windows Vista SP1</p></td>
<td align="left"><p>受支持，但无法报告或编辑仅存在于 Windows Server2008R2 或 Windows7 中的策略设置或首选项</p></td>
</tr>
</tbody>
</table>

 

 

 





