---
title: “内容”选项卡功能
description: “内容”选项卡功能
author: dansimp
ms.assetid: 725f025a-c30a-4d07-add1-4e0ed9a1a5fd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f64aad16a3335d78641812121692f6d5f6436ee1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802004"
---
# “内容”选项卡功能


"**目录**" 选项卡中的每个辅助选项卡都包含两个部分：**组策略对象**和**组和用户**。

## 组策略对象部分


**组策略对象**部分显示组策略对象（gpo）的筛选列表，并标识每个 GPO 的以下属性：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">GPO 属性</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>名称</strong></p></td>
<td align="left"><p>GPO 的名称。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>State</strong></p></td>
<td align="left"><p>所选 GPO 的状态</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>更改者</strong></p></td>
<td align="left"><p>已签入或已部署选定 GPO 的审批者的编辑者。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>更改日期</strong></p></td>
<td align="left"><p>对于受控 GPO，在修改或签出后将其签入的最新日期。 对于不受控制的 GPO，为其上次修改的日期。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>评论</strong></p></td>
<td align="left"><p>在修改时由签入或部署 GPO 的人员输入的注释。 在需要回滚到以前版本的情况下，用于识别版本的详细信息。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>计算机版本</strong></p></td>
<td align="left"><p>GPO 的计算机配置部分的自动生成的版本。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>用户版本</strong></p></td>
<td align="left"><p>GPO 的用户配置部分的自动生成的版本。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>GPO 状态</strong></p></td>
<td align="left"><p>计算机配置和用户配置可以单独管理。 GPO 状态表示启用了 GPO 的哪些部分。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>WMI 筛选器</strong></p></td>
<td align="left"><p>显示应用到此 GPO 的任何 WMI 筛选器。 WMI 筛选器在 GPMC 的 <strong> </strong> 控制台树中的域的 Wmi 筛选器文件夹下进行管理。</p></td>
</tr>
</tbody>
</table>

 

## 组和用户部分


选择 GPO 时，"**组和用户**" 部分将显示有权访问该 GPO 的组和用户的列表。 为每个组或用户显示允许的权限和继承。 AGPM 管理员可以使用标准 AGPM 角色（编辑、审批者、审阅者和 AGPM 管理员）或自定义权限组合配置权限。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">按钮</th>
<th align="left">作用</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>添加</strong></p></td>
<td align="left"><p>将新条目添加到安全描述符中。 可以添加 Active Directory 中的任何用户或组。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>删除</strong></p></td>
<td align="left"><p>从 "访问控制列表" 中删除所选条目。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>属性</strong></p></td>
<td align="left"><p>显示所选对象的属性。 "属性" 页面与 <strong> Active Directory 用户和计算机中的对象显示的属性相同 </strong> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>高级</strong></p></td>
<td align="left"><p>打开 " <strong> 访问控制列表编辑器" </strong> 。</p></td>
</tr>
</tbody>
</table>

 

### 其他注意事项

-   有关与特定任务相关的角色和权限的信息，请参阅[执行 AGPM 管理员任务](performing-agpm-administrator-tasks-agpm30ops.md)、[执行编辑任务](performing-editor-tasks-agpm30ops.md)、[执行审批者任务](performing-approver-tasks-agpm30ops.md)和[执行审阅者任务](performing-reviewer-tasks-agpm30ops.md)中的任务。

### 其他参考资料

-   [“内容”选项卡](contents-tab-agpm30ops.md)

 

 





