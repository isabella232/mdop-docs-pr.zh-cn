---
title: “常用辅助项”选项卡功能
description: “常用辅助项”选项卡功能
author: dansimp
ms.assetid: 44a15c28-944c-49c1-8534-115ce1c362ed
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 546fd4c91e060a5595b6c848015290882de933b6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802076"
---
# “常用辅助项”选项卡功能


每个辅助选项卡包含两个部分：**组策略对象**和**组以及用户**。

## 组策略对象部分


**组策略对象**部分显示组策略对象（gpo）的筛选列表，并标识每个 GPO 的以下特征：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">GPO 特性</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>名称</strong></p></td>
<td align="left"><p>组策略对象的名称。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>计算机（Comp）</strong></p></td>
<td align="left"><p>GPO 的计算机配置部分的自动生成的版本。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>用户</strong></p></td>
<td align="left"><p>GPO 的用户配置部分的自动生成的版本。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>State</strong></p></td>
<td align="left"><p>所选 GPO 的状态：</p>
<p><img src="images/36f6b687-f5cc-40d1-805f-b191d1fb1ace.gif" alt="Deployed GPO icon" /> <strong>不受控制： </strong> 不由 AGPM 托管。</p>
<p><img src="images/57b610a5-1c71-4d26-9173-d04abd495fcc.gif" alt="Checked in GPO icon" /> <strong>已签入： </strong> 可供授权编辑人员签出以进行编辑或组策略管理员进行部署。</p>
<p><img src="images/8e7a7c4e-809a-435a-8b29-30d797936210.gif" alt="Checked out GPO icon" /> <strong>已签出： </strong> 当前正在编辑。 在签出的编辑者或 AGPM 管理员将其签入之前，不能查看其他编辑器。</p>
<p><img src="images/0840a6a3-54a6-4528-98a9-7b122243c1a5.gif" alt="Pending GPO icon" /> <strong>挂起：在 </strong> 创建、控制、部署或删除组之前，等待组策略管理员批准。</p>
<p><img src="images/57b610a5-1c71-4d26-9173-d04abd495fcc.gif" alt="Checked in GPO icon" /> <strong>已删除： </strong> 从存档中删除，但仍可以还原。</p>
<p><img src="images/9b65829d-253c-4f30-9295-c816a6521ed2.gif" alt="Template icon" /> <strong>模板：在 </strong> 创建新 gpo 时用作起点的 GPO 的静态版本。</p>
<p><img src="images/cd349b8d-c4d8-45ff-b17f-7db882502c58.gif" alt="Default template icon" /> <strong>模板（默认）： </strong> 默认情况下，此模板是创建新 GPO 时使用的起始点。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>GPO 状态</strong></p></td>
<td align="left"><p>计算机配置和用户配置可以单独管理。 GPO 状态表示启用了 GPO 的哪些部分。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>WMI 筛选器</strong></p></td>
<td align="left"><p>显示应用到此 GPO 的任何 WMI 筛选器。 WMI 筛选器在 GPMC 的 <strong> </strong> 控制台树中的域的 Wmi 筛选器节点下进行管理。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>修改日期</strong></p></td>
<td align="left"><p>对于受控制的 GPO，在修改或签出后将其签入以进行修改的最新日期。 对于不受控制的 GPO，为其上次修改的日期。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>所有者</strong></p></td>
<td align="left"><p>已签入或已部署选定 GPO 的审批者的编辑者。</p></td>
</tr>
</tbody>
</table>

 

## 组和用户部分


选择 GPO 时，"**组和用户**" 部分将显示有权访问该 GPO 的组和用户的列表。 为每个组或用户显示允许的权限和继承。 AGPM 管理员可以使用标准 AGPM 角色（编辑者、审批者和审阅者）或自定义权限组合配置权限。

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

-   有关与特定任务相关的角色和权限的信息，请参阅[执行 AGPM 管理员任务](performing-agpm-administrator-tasks.md)、[执行编辑任务](performing-editor-tasks.md)、[执行审批者任务](performing-approver-tasks.md)和[执行审阅者任务](performing-reviewer-tasks.md)中的任务。

### 其他参考资料

-   [“内容”选项卡](contents-tab.md)

 

 





