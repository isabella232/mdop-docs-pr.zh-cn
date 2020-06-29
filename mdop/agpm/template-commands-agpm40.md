---
title: 模板命令
description: 模板命令
author: dansimp
ms.assetid: 243a9b18-bf3f-44fa-94d7-5c793f7322da
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2c540bf87462f501a4db5596faca43ef66ee8558
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801756"
---
# 模板命令


"**模板**" 选项卡：

-   显示可用于创建新组策略对象（Gpo）的可用模板列表。

-   提供快捷菜单，其中包含基于所选模板创建 GPO、管理模板和显示模板报表的命令。

-   显示有权限访问所选模板的组和用户的列表。

由于模板不能更改，因此模板没有历史记录。 但是，与任何 GPO 版本一样，模板的设置可以与设置报告一起显示，也可以与具有差异报告的另一个 GPO 进行比较。

**注意** 模板是 GPO 的不可编辑的静态版本，用作创建新的可编辑 Gpo 的起始点。

 

右键单击此选项卡上的 "**组策略对象**" 列表，将显示快捷菜单，包括以下任何适用选项。

## 控件


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">命令</th>
<th align="left">作用</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>新的受控 GPO</strong></p></td>
<td align="left"><p>基于所选模板创建新的 GPO。 提供了用于将新 GPO 部署到域的生产环境的选项。 如果你没有创建 GPO 的权限，系统将提示你提交请求。 （如果右键单击 <strong> 时未选择任何 GPO，则显示此选项组策略对象 </strong> 列表。）</p></td>
</tr>
</tbody>
</table>

 

## 报告


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">命令</th>
<th align="left">作用</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>设置</strong></p></td>
<td align="left"><p>生成用于显示选定 GPO 中的设置的基于 HTML 的报表或基于 XML 的报表。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>不同之处</strong></p></td>
<td align="left"><p>生成用于比较两个选定 GPO 模板中的设置的基于 HTML 或基于 XML 的报表。</p></td>
</tr>
</tbody>
</table>

 

## 模板管理


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">命令</th>
<th align="left">作用</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>设置为默认值</strong></p></td>
<td align="left"><p>将所选模板设置为默认值，以便在创建新 GPO 时自动使用。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>删除</strong></p></td>
<td align="left"><p>将所选模板移到 <strong> 回收站 </strong> 。 如果你没有删除 GPO 的权限，系统将提示你提交请求。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>重命名</strong></p></td>
<td align="left"><p>更改所选模板的名称。</p></td>
</tr>
</tbody>
</table>

 

## 杂项


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">命令</th>
<th align="left">作用</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>刷新</strong></p></td>
<td align="left"><p>更新组策略管理控制台的显示以合并所做的任何更改。 在刷新显示之前，某些更改不可见。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>帮助</strong></p></td>
<td align="left"><p>显示高级组策略管理（AGPM）的帮助。</p></td>
</tr>
</tbody>
</table>

 

### 其他参考资料

-   [“内容”选项卡](contents-tab-agpm40.md)

-   [执行编辑者任务](performing-editor-tasks-agpm40.md)

-   [执行审阅者任务](performing-reviewer-tasks-agpm40.md)

 

 





