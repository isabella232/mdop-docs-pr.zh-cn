---
title: 清单创建、编辑和部署 GPO
description: 清单创建、编辑和部署 GPO
author: dansimp
ms.assetid: 44631bed-16d2-4b5a-af70-17a73fb5f6af
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7d8bea9109040aa81a20df62356ef1d307d5eac0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802083"
---
# <span data-ttu-id="aef86-103">清单：创建、编辑和部署 GPO</span><span class="sxs-lookup"><span data-stu-id="aef86-103">Checklist: Create, Edit, and Deploy a GPO</span></span>


<span data-ttu-id="aef86-104">在多人通过使用高级组策略管理（AGPM）更改组策略对象（Gpo）的环境中，AGPM 管理员（"完全控制"）将对编辑者、审批者和审阅者的权限委派为组或个人。</span><span class="sxs-lookup"><span data-stu-id="aef86-104">In an environment where multiple people change Group Policy Objects (GPOs) by using Advanced Group Policy Management (AGPM), an AGPM Administrator (Full Control) delegates permission to Editors, Approvers, and Reviewers either as groups or as individuals.</span></span> <span data-ttu-id="aef86-105">下面是一个针对编辑器和审批者的典型 GPO 开发过程。</span><span class="sxs-lookup"><span data-stu-id="aef86-105">The following is a typical GPO development process for an Editor and an Approver.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="aef86-106">任务</span><span class="sxs-lookup"><span data-stu-id="aef86-106">Task</span></span></th>
<th align="left"><span data-ttu-id="aef86-107">参考</span><span class="sxs-lookup"><span data-stu-id="aef86-107">Reference</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="aef86-108">编辑器请求创建新的 GPO 或审批者创建新的 GPO。</span><span class="sxs-lookup"><span data-stu-id="aef86-108">Editor requests that a new GPO be created or an Approver creates a new GPO.</span></span></p></td>
<td align="left"><p><a href="request-the-creation-of-a-new-controlled-gpo-agpm40.md" data-raw-source="[Request the Creation of a New Controlled GPO](request-the-creation-of-a-new-controlled-gpo-agpm40.md)"><span data-ttu-id="aef86-109">请求创建新的受控 GPO</span><span class="sxs-lookup"><span data-stu-id="aef86-109">Request the Creation of a New Controlled GPO</span></span></a></p>
<p><a href="create-a-new-controlled-gpo-agpm40.md" data-raw-source="[Create a New Controlled GPO](create-a-new-controlled-gpo-agpm40.md)"><span data-ttu-id="aef86-110">创建新的受控 GPO</span><span class="sxs-lookup"><span data-stu-id="aef86-110">Create a New Controlled GPO</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="aef86-111">如果某个编辑器请求了该 GPO，审批者将批准该 GPO 的创建。</span><span class="sxs-lookup"><span data-stu-id="aef86-111">Approver approves the creation of the GPO if it was requested by an Editor.</span></span></p></td>
<td align="left"><p><a href="approve-or-reject-a-pending-action-agpm40.md" data-raw-source="[Approve or Reject a Pending Action](approve-or-reject-a-pending-action-agpm40.md)"><span data-ttu-id="aef86-112">批准或拒绝挂起的操作</span><span class="sxs-lookup"><span data-stu-id="aef86-112">Approve or Reject a Pending Action</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="aef86-113">编辑器从存档中签出 GPO 的副本，以便任何人都不能修改该 GPO。</span><span class="sxs-lookup"><span data-stu-id="aef86-113">Editor checks out a copy of the GPO from the archive so that no one else can modify the GPO.</span></span> <span data-ttu-id="aef86-114">编辑器对 GPO 进行更改，然后将修改后的 GPO 检查到存档中。</span><span class="sxs-lookup"><span data-stu-id="aef86-114">Editor makes changes to the GPO, and then checks the modified GPO into the archive.</span></span></p></td>
<td align="left"><p><a href="edit-a-gpo-offline-agpm40.md" data-raw-source="[Edit a GPO Offline](edit-a-gpo-offline-agpm40.md)"><span data-ttu-id="aef86-115">脱机编辑 GPO</span><span class="sxs-lookup"><span data-stu-id="aef86-115">Edit a GPO Offline</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="aef86-116">如果在测试林中开发，编辑器会将 GPO 导出到一个文件，将文件传输到生产林，然后导入该文件。</span><span class="sxs-lookup"><span data-stu-id="aef86-116">If developing in a test forest, Editor exports the GPO to a file, transfers the file to the production forest, and imports the file.</span></span> <span data-ttu-id="aef86-117">此外，编辑器还可将 GPO 链接到包含测试计算机和用户的组织单位。</span><span class="sxs-lookup"><span data-stu-id="aef86-117">Additionally, an Editor can link the GPO to an organizational unit that contains test computers and users.</span></span></p></td>
<td align="left"><p><a href="using-a-test-environment.md" data-raw-source="[Using a Test Environment](using-a-test-environment.md)"><span data-ttu-id="aef86-118">使用测试环境</span><span class="sxs-lookup"><span data-stu-id="aef86-118">Using a Test Environment</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="aef86-119">编辑器请求将 GPO 部署到域的生产环境。</span><span class="sxs-lookup"><span data-stu-id="aef86-119">Editor requests deployment of the GPO to the production environment of the domain.</span></span></p></td>
<td align="left"><p><a href="request-deployment-of-a-gpo-agpm40.md" data-raw-source="[Request Deployment of a GPO](request-deployment-of-a-gpo-agpm40.md)"><span data-ttu-id="aef86-120">请求部署 GPO</span><span class="sxs-lookup"><span data-stu-id="aef86-120">Request Deployment of a GPO</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="aef86-121">审阅者（如审批者或编辑者）分析 GPO。</span><span class="sxs-lookup"><span data-stu-id="aef86-121">Reviewers, such as Approvers or Editors, analyze the GPO.</span></span></p></td>
<td align="left"><p><a href="performing-reviewer-tasks-agpm40.md" data-raw-source="[Performing Reviewer Tasks](performing-reviewer-tasks-agpm40.md)"><span data-ttu-id="aef86-122">执行审阅者任务</span><span class="sxs-lookup"><span data-stu-id="aef86-122">Performing Reviewer Tasks</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="aef86-123">审批者批准并将 GPO 部署到域的生产环境或拒绝 GPO。</span><span class="sxs-lookup"><span data-stu-id="aef86-123">Approver approves and deploys the GPO to the production environment of the domain or rejects the GPO.</span></span></p></td>
<td align="left"><p><a href="approve-or-reject-a-pending-action-agpm40.md" data-raw-source="[Approve or Reject a Pending Action](approve-or-reject-a-pending-action-agpm40.md)"><span data-ttu-id="aef86-124">批准或拒绝挂起的操作</span><span class="sxs-lookup"><span data-stu-id="aef86-124">Approve or Reject a Pending Action</span></span></a></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="aef86-125">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="aef86-125">Additional references</span></span>

[<span data-ttu-id="aef86-126">高级组策略管理 4.0</span><span class="sxs-lookup"><span data-stu-id="aef86-126">Advanced Group Policy Management 4.0</span></span>](advanced-group-policy-management-40.md)

 

 





