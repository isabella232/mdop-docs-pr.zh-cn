---
title: 执行审批者任务
description: 执行审批者任务
author: dansimp
ms.assetid: 9f711824-191b-4b4b-a1c6-a3b2116006a4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d8e4a848608a3be1dbb0632f0145b4fc1d1bc631
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802631"
---
# <span data-ttu-id="82940-103">执行审批者任务</span><span class="sxs-lookup"><span data-stu-id="82940-103">Performing Approver Tasks</span></span>


<span data-ttu-id="82940-104">审批者是由 AGPM 管理员（完全控制）授权的人员，用于创建、部署和删除组策略对象（Gpo），以及批准或拒绝请求（通常来自编辑者）来创建、部署或删除 Gpo。</span><span class="sxs-lookup"><span data-stu-id="82940-104">An Approver is a person authorized by an AGPM Administrator (Full Control) to create, deploy, and delete Group Policy Objects (GPOs) and to approve or reject requests (typically from Editors) to create, deploy, or delete GPOs.</span></span>

<span data-ttu-id="82940-105">**重要提示** 请确保你连接到 Gpo 的中心存档。</span><span class="sxs-lookup"><span data-stu-id="82940-105">**Important** Make sure that you are connecting to the central archive for GPOs.</span></span> <span data-ttu-id="82940-106">有关详细信息，请参阅[配置 AGPM 服务器连接](configure-an-agpm-server-connection-reviewer-agpm30ops.md)。</span><span class="sxs-lookup"><span data-stu-id="82940-106">For more information, see [Configure an AGPM Server Connection](configure-an-agpm-server-connection-reviewer-agpm30ops.md).</span></span>

 

-   [<span data-ttu-id="82940-107">批准或拒绝挂起的操作</span><span class="sxs-lookup"><span data-stu-id="82940-107">Approve or Reject a Pending Action</span></span>](approve-or-reject-a-pending-action-agpm30ops.md)

-   [<span data-ttu-id="82940-108">创建、控制或导入 GPO</span><span class="sxs-lookup"><span data-stu-id="82940-108">Creating, Controlling, or Importing a GPO</span></span>](creating-controlling-or-importing-a-gpo-editor-agpm30ops.md)

-   [<span data-ttu-id="82940-109">签入 GPO</span><span class="sxs-lookup"><span data-stu-id="82940-109">Check In a GPO</span></span>](check-in-a-gpo-agpm30ops.md)

-   [<span data-ttu-id="82940-110">部署 GPO</span><span class="sxs-lookup"><span data-stu-id="82940-110">Deploy a GPO</span></span>](deploy-a-gpo-agpm30ops.md)

-   [<span data-ttu-id="82940-111">回滚到以前版本的 GPO</span><span class="sxs-lookup"><span data-stu-id="82940-111">Roll Back to a Previous Version of a GPO</span></span>](roll-back-to-a-previous-version-of-a-gpo-agpm30ops.md)

-   [<span data-ttu-id="82940-112">删除、还原或销毁 GPO</span><span class="sxs-lookup"><span data-stu-id="82940-112">Deleting, Restoring, or Destroying a GPO</span></span>](deleting-restoring-or-destroying-a-gpo-agpm30ops.md)

<span data-ttu-id="82940-113">**注意** 在批准 GPO 之前，审批者应检查它所包含的策略设置。</span><span class="sxs-lookup"><span data-stu-id="82940-113">**Note** Before approving a GPO, an Approver should review the policy settings that it contains.</span></span> <span data-ttu-id="82940-114">审批者角色包括审阅者角色的权限，以便审批者可以查看策略设置和比较 Gpo。</span><span class="sxs-lookup"><span data-stu-id="82940-114">The Approver role includes the permissions for the Reviewer role, so that an Approver can review policy settings and compare GPOs.</span></span> <span data-ttu-id="82940-115">有关详细信息，请参阅[执行审阅者任务](performing-reviewer-tasks-agpm30ops.md)。</span><span class="sxs-lookup"><span data-stu-id="82940-115">See [Performing Reviewer Tasks](performing-reviewer-tasks-agpm30ops.md) for more information.</span></span>

 

### <span data-ttu-id="82940-116">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="82940-116">Additional considerations</span></span>

<span data-ttu-id="82940-117">默认情况下，为审批者角色提供以下权限：</span><span class="sxs-lookup"><span data-stu-id="82940-117">By default, the following permissions are provided for the Approver role:</span></span>

-   <span data-ttu-id="82940-118">列表内容</span><span class="sxs-lookup"><span data-stu-id="82940-118">List Contents</span></span>

-   <span data-ttu-id="82940-119">读取设置</span><span class="sxs-lookup"><span data-stu-id="82940-119">Read Settings</span></span>

-   <span data-ttu-id="82940-120">创建 GPO</span><span class="sxs-lookup"><span data-stu-id="82940-120">Create GPO</span></span>

-   <span data-ttu-id="82940-121">部署 GPO</span><span class="sxs-lookup"><span data-stu-id="82940-121">Deploy GPO</span></span>

-   <span data-ttu-id="82940-122">删除 GPO</span><span class="sxs-lookup"><span data-stu-id="82940-122">Delete GPO</span></span>

<span data-ttu-id="82940-123">此外，审批者对他创建或控制的 Gpo 拥有完全控制权。</span><span class="sxs-lookup"><span data-stu-id="82940-123">Also, an Approver has full control over GPOs that he created or controlled.</span></span>

 

 





