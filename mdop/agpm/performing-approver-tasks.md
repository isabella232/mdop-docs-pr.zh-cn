---
title: 执行审批者任务
description: 执行审批者任务
author: dansimp
ms.assetid: 6f6310b3-19c1-47c9-8615-964ddd10ce14
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fc77a1dd9a3d54e637ae4baeb452d327672ed250
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802612"
---
# <span data-ttu-id="12cc8-103">执行审批者任务</span><span class="sxs-lookup"><span data-stu-id="12cc8-103">Performing Approver Tasks</span></span>


<span data-ttu-id="12cc8-104">审批者是由 AGPM 管理员（完全控制）授权的人员，用于创建、部署和删除组策略对象（Gpo），以及批准或拒绝请求（通常来自编辑者）来创建、部署或删除 Gpo。</span><span class="sxs-lookup"><span data-stu-id="12cc8-104">An Approver is a person authorized by an AGPM Administrator (Full Control) to create, deploy, and delete Group Policy objects (GPOs) and to approve or reject requests (typically from Editors) to create, deploy, or delete GPOs.</span></span>

<span data-ttu-id="12cc8-105">**重要提示** 确保你连接到 Gpo 的中心存档。</span><span class="sxs-lookup"><span data-stu-id="12cc8-105">**Important** Ensure that you are connecting to the central archive for GPOs.</span></span> <span data-ttu-id="12cc8-106">有关详细信息，请参阅[配置 AGPM 服务器连接](configure-the-agpm-server-connection-reviewer.md)。</span><span class="sxs-lookup"><span data-stu-id="12cc8-106">For more information, see [Configure the AGPM Server Connection](configure-the-agpm-server-connection-reviewer.md).</span></span>

 

-   [<span data-ttu-id="12cc8-107">批准或拒绝挂起的操作</span><span class="sxs-lookup"><span data-stu-id="12cc8-107">Approve or Reject a Pending Action</span></span>](approve-or-reject-a-pending-action.md)

-   [<span data-ttu-id="12cc8-108">创建、控制或导入 GPO</span><span class="sxs-lookup"><span data-stu-id="12cc8-108">Creating, Controlling, or Importing a GPO</span></span>](creating-controlling-or-importing-a-gpo-approver.md)

-   [<span data-ttu-id="12cc8-109">签入 GPO</span><span class="sxs-lookup"><span data-stu-id="12cc8-109">Check In a GPO</span></span>](check-in-a-gpo-approver.md)

-   [<span data-ttu-id="12cc8-110">部署 GPO</span><span class="sxs-lookup"><span data-stu-id="12cc8-110">Deploy a GPO</span></span>](deploy-a-gpo.md)

-   [<span data-ttu-id="12cc8-111">回滚到以前版本的 GPO</span><span class="sxs-lookup"><span data-stu-id="12cc8-111">Roll Back to a Previous Version of a GPO</span></span>](roll-back-to-a-previous-version-of-a-gpo.md)

-   [<span data-ttu-id="12cc8-112">删除、还原或销毁 GPO</span><span class="sxs-lookup"><span data-stu-id="12cc8-112">Deleting, Restoring, or Destroying a GPO</span></span>](deleting-restoring-or-destroying-a-gpo.md)

<span data-ttu-id="12cc8-113">**注意** 由于审批者角色包括审阅者角色的权限，审批者还可以查看设置和比较 Gpo。</span><span class="sxs-lookup"><span data-stu-id="12cc8-113">**Note** Because the Approver role includes the permissions for the Reviewer role, an Approver can also review settings and compare GPOs.</span></span> <span data-ttu-id="12cc8-114">有关详细信息，请参阅[执行审阅者任务](performing-reviewer-tasks.md)。</span><span class="sxs-lookup"><span data-stu-id="12cc8-114">See [Performing Reviewer Tasks](performing-reviewer-tasks.md) for more information.</span></span>

 

### <span data-ttu-id="12cc8-115">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="12cc8-115">Additional considerations</span></span>

<span data-ttu-id="12cc8-116">默认情况下，为审批者角色提供以下权限：</span><span class="sxs-lookup"><span data-stu-id="12cc8-116">By default, the following permissions are provided for the Approver role:</span></span>

-   <span data-ttu-id="12cc8-117">列表内容</span><span class="sxs-lookup"><span data-stu-id="12cc8-117">List Contents</span></span>

-   <span data-ttu-id="12cc8-118">读取设置</span><span class="sxs-lookup"><span data-stu-id="12cc8-118">Read Settings</span></span>

-   <span data-ttu-id="12cc8-119">创建 GPO</span><span class="sxs-lookup"><span data-stu-id="12cc8-119">Create GPO</span></span>

-   <span data-ttu-id="12cc8-120">部署 GPO</span><span class="sxs-lookup"><span data-stu-id="12cc8-120">Deploy GPO</span></span>

-   <span data-ttu-id="12cc8-121">删除 GPO</span><span class="sxs-lookup"><span data-stu-id="12cc8-121">Delete GPO</span></span>

<span data-ttu-id="12cc8-122">此外，审批者对他创建或控制的 Gpo 拥有完全控制权。</span><span class="sxs-lookup"><span data-stu-id="12cc8-122">Also, an Approver has full control over GPOs that he created or controlled.</span></span>

 

 





