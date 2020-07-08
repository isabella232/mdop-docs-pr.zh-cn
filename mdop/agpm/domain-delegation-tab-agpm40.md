---
title: “域委派”选项卡
description: “域委派”选项卡
author: dansimp
ms.assetid: 5be5841e-92fb-4af6-aa68-0ae50f8d5141
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c5f3b5c3b7d8799b383ab48870fcccad0b0c3f73
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801896"
---
# “域委派”选项卡


"**更改控制**" 窗格上的 "**域委派**" 选项卡提供了组策略管理员的列表，这些管理员对存档具有域级别的访问权限，并指明每个组的角色。 此外，此选项卡允许 AGPM 管理员（完全控制）为编辑者、审批者、审阅者和其他 AGPM 管理员配置域级别的权限。 "**域委派**" 选项卡上有两个部分：配置电子邮件通知和域级别的高级组策略管理（AGPM）的基于角色的委派。

## 电子邮件通知配置


此选项卡的 "电子邮件通知" 部分标识当 AGPM 中的操作处于挂起状态时，将收到通知的审批者。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">设置</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>发件人电子邮件地址</strong></p></td>
<td align="left"><p>将通知发送到审批者的 AGPM 别名。 在具有多个域的环境中，这可以是整个环境中的相同别名，也可以是每个域的不同别名。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>收件人电子邮件地址</strong></p></td>
<td align="left"><p>要向其发送通知的审批者的电子邮件地址的逗号分隔列表</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>SMTP 服务器</strong></p></td>
<td align="left"><p>电子邮件服务器的名称，例如 mail.contoso.com</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>用户名</strong></p></td>
<td align="left"><p>对 SMTP 服务器具有访问权限的用户</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>密码</strong></p></td>
<td align="left"><p>SMTP 服务器身份验证的用户密码</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>确认密码</strong></p></td>
<td align="left"><p>确认用户密码</p></td>
</tr>
</tbody>
</table>

 

## 域级基于角色的委派


将显示此选项卡的 "基于角色的委派" 部分，并允许 AGPM 管理员为域上的每个组和用户委派对存档的访问权限，从而允许、拒绝和继承的权限。 AGPM 管理员可以使用标准 AGPM 角色（编辑、审批者、审阅者和 AGPM 管理员）或每个组策略管理员的自定义权限组合来配置域范围权限。

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
<td align="left"><p>将新条目添加到安全描述符中。 Active Directory 中的任何用户或组都可以添加为组策略管理员。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>删除</strong></p></td>
<td align="left"><p>从访问控制列表中删除所选组策略管理员。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>属性</strong></p></td>
<td align="left"><p>显示所选组策略管理员的属性。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>高级</strong></p></td>
<td align="left"><p>打开 " <strong> 访问控制列表编辑器" </strong> 。</p></td>
</tr>
</tbody>
</table>

 

### 其他注意事项

-   有关与特定任务相关的角色和权限的信息，请参阅[执行 AGPM 管理员任务](performing-agpm-administrator-tasks-agpm40.md)、[执行编辑任务](performing-editor-tasks-agpm40.md)、[执行审批者任务](performing-approver-tasks-agpm40.md)和[执行审阅者任务](performing-reviewer-tasks-agpm40.md)中的任务。

### 其他参考资料

-   [用户界面：高级组策略管理](user-interface-advanced-group-policy-management-agpm40.md)

-   [执行 AGPM 管理员任务](performing-agpm-administrator-tasks-agpm40.md)

 

 





