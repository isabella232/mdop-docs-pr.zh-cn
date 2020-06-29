---
title: 清单创建、编辑和部署 GPO
description: 清单创建、编辑和部署 GPO
author: dansimp
ms.assetid: a7a17706-304a-4455-9ada-52508ec620f1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 35255926ba2384e2942900fc30eae06a30049a15
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802084"
---
# <span data-ttu-id="c0739-103">清单：创建、编辑和部署 GPO</span><span class="sxs-lookup"><span data-stu-id="c0739-103">Checklist: Create, Edit, and Deploy a GPO</span></span>


<span data-ttu-id="c0739-104">在多个用户使用高级组策略管理（AGPM）对组策略对象（Gpo）进行更改的环境中，AGPM 管理员（完全控制）将权限委派给编辑者、审批者和审阅者，或者作为组或个人。</span><span class="sxs-lookup"><span data-stu-id="c0739-104">In an environment where multiple people make changes to Group Policy Objects (GPOs) using Advanced Group Policy Management (AGPM), an AGPM Administrator (Full Control) delegates permission to Editors, Approvers, and Reviewers, either as groups or as individuals.</span></span> <span data-ttu-id="c0739-105">下面是一个针对编辑器和审批者的典型 GPO 开发过程。</span><span class="sxs-lookup"><span data-stu-id="c0739-105">The following is a typical GPO development process for an Editor and an Approver.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="c0739-106">任务</span><span class="sxs-lookup"><span data-stu-id="c0739-106">Task</span></span></th>
<th align="left"><span data-ttu-id="c0739-107">参考</span><span class="sxs-lookup"><span data-stu-id="c0739-107">Reference</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c0739-108">编辑器请求创建新的 GPO 或审批者创建新的 GPO。</span><span class="sxs-lookup"><span data-stu-id="c0739-108">Editor requests the creation of a new GPO or an Approver creates a new GPO.</span></span></p></td>
<td align="left"><p><a href="request-the-creation-of-a-new-controlled-gpo-agpm30ops.md" data-raw-source="[Request the Creation of a New Controlled GPO](request-the-creation-of-a-new-controlled-gpo-agpm30ops.md)"><span data-ttu-id="c0739-109">请求创建新的受控 GPO</span><span class="sxs-lookup"><span data-stu-id="c0739-109">Request the Creation of a New Controlled GPO</span></span></a></p>
<p><a href="create-a-new-controlled-gpo-agpm30ops.md" data-raw-source="[Create a New Controlled GPO](create-a-new-controlled-gpo-agpm30ops.md)"><span data-ttu-id="c0739-110">创建新的受控 GPO</span><span class="sxs-lookup"><span data-stu-id="c0739-110">Create a New Controlled GPO</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c0739-111">如果某个编辑器请求了该 GPO，审批者将批准该 GPO 的创建。</span><span class="sxs-lookup"><span data-stu-id="c0739-111">Approver approves the creation of the GPO if it was requested by an Editor.</span></span></p></td>
<td align="left"><p><a href="approve-or-reject-a-pending-action-agpm30ops.md" data-raw-source="[Approve or Reject a Pending Action](approve-or-reject-a-pending-action-agpm30ops.md)"><span data-ttu-id="c0739-112">批准或拒绝挂起的操作</span><span class="sxs-lookup"><span data-stu-id="c0739-112">Approve or Reject a Pending Action</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c0739-113">编辑器从存档中签出 GPO 的副本，因此任何其他人都无法修改该 GPO。</span><span class="sxs-lookup"><span data-stu-id="c0739-113">Editor checks out a copy of the GPO from the archive, so no one else can modify the GPO.</span></span> <span data-ttu-id="c0739-114">编辑器对 GPO 进行更改，然后将修改后的 GPO 检查到存档中。</span><span class="sxs-lookup"><span data-stu-id="c0739-114">Editor makes changes to the GPO, and then checks the modified GPO into the archive.</span></span></p></td>
<td align="left"><p><a href="edit-a-gpo-offline-agpm30ops.md" data-raw-source="[Edit a GPO Offline](edit-a-gpo-offline-agpm30ops.md)"><span data-ttu-id="c0739-115">脱机编辑 GPO</span><span class="sxs-lookup"><span data-stu-id="c0739-115">Edit a GPO Offline</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c0739-116">编辑器请求将 GPO 部署到生产环境。</span><span class="sxs-lookup"><span data-stu-id="c0739-116">Editor requests deployment of the GPO to the production environment.</span></span></p></td>
<td align="left"><p><a href="request-deployment-of-a-gpo-agpm30ops.md" data-raw-source="[Request Deployment of a GPO](request-deployment-of-a-gpo-agpm30ops.md)"><span data-ttu-id="c0739-117">请求部署 GPO</span><span class="sxs-lookup"><span data-stu-id="c0739-117">Request Deployment of a GPO</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c0739-118">审阅者（如审批者或编辑者）分析 GPO。</span><span class="sxs-lookup"><span data-stu-id="c0739-118">Reviewers, such as Approvers or Editors, analyze the GPO.</span></span></p></td>
<td align="left"><p><a href="performing-reviewer-tasks-agpm30ops.md" data-raw-source="[Performing Reviewer Tasks](performing-reviewer-tasks-agpm30ops.md)"><span data-ttu-id="c0739-119">执行审阅者任务</span><span class="sxs-lookup"><span data-stu-id="c0739-119">Performing Reviewer Tasks</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c0739-120">审批者批准并将 GPO 部署到生产环境或拒绝 GPO。</span><span class="sxs-lookup"><span data-stu-id="c0739-120">Approver approves and deploys the GPO to the production environment or rejects the GPO.</span></span></p></td>
<td align="left"><p><a href="approve-or-reject-a-pending-action-agpm30ops.md" data-raw-source="[Approve or Reject a Pending Action](approve-or-reject-a-pending-action-agpm30ops.md)"><span data-ttu-id="c0739-121">批准或拒绝挂起的操作</span><span class="sxs-lookup"><span data-stu-id="c0739-121">Approve or Reject a Pending Action</span></span></a></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="c0739-122">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="c0739-122">Additional references</span></span>

[<span data-ttu-id="c0739-123">Microsoft 高级组策略管理 3.0 操作指南</span><span class="sxs-lookup"><span data-stu-id="c0739-123">Operations Guide for Microsoft Advanced Group Policy Management 3.0</span></span>](operations-guide-for-microsoft-advanced-group-policy-management-30-agpm30ops.md)

 

 





