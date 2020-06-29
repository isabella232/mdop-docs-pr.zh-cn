---
title: 挂起的 GPO 命令
description: 挂起的 GPO 命令
author: dansimp
ms.assetid: 3868dda0-8a41-4bba-9b0c-9f656f9a3cd5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: dde41ea33305290174eab6e34c382aec4ce8b18d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803175"
---
# 挂起的 GPO 命令


"**挂起**" 选项卡：

-   显示组策略对象（Gpo）的列表，其中包含 GPO 管理操作的挂起请求（如创建、控制、部署或删除）。

-   提供快捷菜单，其中包含用于响应挂起的请求和显示 Gpo 的历史记录和报告的命令。

-   显示具有访问选定 GPO 的权限的组和用户的列表。

右键单击此选项卡上的 "**组策略对象**" 列表，将显示快捷菜单，包括以下任何适用选项。

## 控件和历史记录


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
<td align="left"><p><strong>历史记录</strong></p></td>
<td align="left"><p>打开一个窗口，列出存档中保存的选定 GPO 的所有版本。 从历史记录中，你可以获取 GPO 中的设置报告、比较 GPO 的两个版本、将 GPO 与模板进行比较或回退到 GPO 的早期版本。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>提取</strong></p></td>
<td align="left"><p>撤消请求以在请求被批准之前创建、控制或删除所选 GPO。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>批准</strong></p></td>
<td align="left"><p>完成来自编辑器的挂起请求以创建、控制或删除所选 GPO。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>&</strong></p></td>
<td align="left"><p>拒绝来自编辑器的挂起请求以创建、控制或删除所选 GPO。</p></td>
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
<td align="left"><p>生成基于 HTML 或基于 XML 的报表，显示所选 GPO 中的设置，或显示从组织单位到 Gpo 最近控制、导入或签入时的选定 Gpo 的链接。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>不同之处</strong></p></td>
<td align="left"><p>生成用于比较两个选定 Gpo 或所选 GPO 和模板内的设置的基于 HTML 或基于 XML 的报表。</p></td>
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
<td align="left"><p>更新组策略管理控制台（GPMC）的显示以合并任何更改。 在刷新显示之前，某些更改不可见。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>帮助</strong></p></td>
<td align="left"><p>显示 AGPM 的帮助。</p></td>
</tr>
</tbody>
</table>

 

### 其他参考资料

-   [“内容”选项卡](contents-tab-agpm30ops.md)

-   [执行审批者任务](performing-approver-tasks-agpm30ops.md)

-   [执行审阅者任务](performing-reviewer-tasks-agpm30ops.md)

 

 





