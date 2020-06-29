---
title: 清单创建、编辑和部署 GPO
description: 清单创建、编辑和部署 GPO
author: dansimp
ms.assetid: 614e2d9a-c18b-4f62-99fd-e17a2ac8559d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c79fefaa65c138372ebee00b769ccc5243142e22
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802087"
---
# 清单：创建、编辑和部署 GPO


在多个用户对组策略对象（Gpo）进行更改的环境中，AGPM 管理员（完全控制）将权限委派给编辑者、审批者和审阅者，或者作为组或个人。 下面是一个针对编辑器和审批者的典型 GPO 开发过程。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">任务</th>
<th align="left">参考</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>编辑器请求创建新的 GPO 或审批者创建新的 GPO。</p></td>
<td align="left"><p><a href="request-the-creation-of-a-new-controlled-gpo.md" data-raw-source="[Request the Creation of a New Controlled GPO](request-the-creation-of-a-new-controlled-gpo.md)">请求创建新的受控 GPO</a></p>
<p><a href="create-a-new-controlled-gpo.md" data-raw-source="[Create a New Controlled GPO](create-a-new-controlled-gpo.md)">创建新的受控 GPO</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>如果某个编辑器请求了该 GPO，审批者将批准该 GPO 的创建。</p></td>
<td align="left"><p><a href="approve-or-reject-a-pending-action.md" data-raw-source="[Approve or Reject a Pending Action](approve-or-reject-a-pending-action.md)">批准或拒绝挂起的操作</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>编辑器从存档中签出 GPO 的副本，因此任何其他人都无法修改该 GPO。 编辑器对 GPO 进行更改，然后将修改后的 GPO 检查到存档中。</p></td>
<td align="left"><p><a href="edit-a-gpo-offline.md" data-raw-source="[Edit a GPO Offline](edit-a-gpo-offline.md)">脱机编辑 GPO</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>编辑器请求将 GPO 部署到生产环境。</p></td>
<td align="left"><p><a href="request-deployment-of-a-gpo.md" data-raw-source="[Request Deployment of a GPO](request-deployment-of-a-gpo.md)">请求部署 GPO</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>审阅者（如审批者或编辑者）分析 GPO。</p></td>
<td align="left"><p><a href="performing-reviewer-tasks.md" data-raw-source="[Performing Reviewer Tasks](performing-reviewer-tasks.md)">执行审阅者任务</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>审批者批准并将 GPO 部署到生产环境或拒绝 GPO。</p></td>
<td align="left"><p><a href="approve-or-reject-a-pending-action.md" data-raw-source="[Approve or Reject a Pending Action](approve-or-reject-a-pending-action.md)">批准或拒绝挂起的操作</a></p></td>
</tr>
</tbody>
</table>

 

 

 





