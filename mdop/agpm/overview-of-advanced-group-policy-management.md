---
title: 高级组策略管理概述
description: 高级组策略管理概述
author: dansimp
ms.assetid: 028de9dd-848b-42bc-a982-65ba5c433772
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 38396de6bd8bdace72d3add1bba09769ae26de32
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803177"
---
# <span data-ttu-id="c4e50-103">高级组策略管理概述</span><span class="sxs-lookup"><span data-stu-id="c4e50-103">Overview of Advanced Group Policy Management</span></span>


<span data-ttu-id="c4e50-104">你可以使用高级组策略管理（AGPM）扩展组策略管理控制台（GPMC）的功能，从而为组策略对象（Gpo）提供全面的更改控制和增强的管理。</span><span class="sxs-lookup"><span data-stu-id="c4e50-104">You can use Advanced Group Policy Management (AGPM) to extend the capabilities of the Group Policy Management Console (GPMC), providing comprehensive change control and enhanced management for Group Policy objects (GPOs).</span></span>

## <span data-ttu-id="c4e50-105">带有更改控制的组策略对象开发</span><span class="sxs-lookup"><span data-stu-id="c4e50-105">Group Policy object development with change control</span></span>


<span data-ttu-id="c4e50-106">利用 AGPM，你可以将每个 GPO 的副本存储在一个中心存档中，以便组策略管理员可以在不立即影响到已部署的 GPO 的版本的情况下查看和修改它。</span><span class="sxs-lookup"><span data-stu-id="c4e50-106">With AGPM, you can store a copy of each GPO in a central archive, so Group Policy administrators can view and modify it offline without immediately impacting the deployed version of the GPO.</span></span> <span data-ttu-id="c4e50-107">此外，AGPM 将在存档中存储每个受控制 GPO 版本的副本，以便你可以在需要时回滚到早期版本。</span><span class="sxs-lookup"><span data-stu-id="c4e50-107">Additionally, AGPM stores a copy of each version of each controlled GPO in the archive so that you can roll back to an earlier version if needed.</span></span>

<span data-ttu-id="c4e50-108">术语 "签入" 和 "签出" 的使用方式与在库中（或提供用于编程开发的更改控制、版本控制或源代码管理的应用程序）大致相同。</span><span class="sxs-lookup"><span data-stu-id="c4e50-108">The terms "check in" and "check out" are used in much the same way as in a library (or in applications that provide change control, version control, or source code control for programming development).</span></span> <span data-ttu-id="c4e50-109">若要使用库中的书籍，请将其从库中签出。</span><span class="sxs-lookup"><span data-stu-id="c4e50-109">To use a book that is in a library, you check it out from the library.</span></span> <span data-ttu-id="c4e50-110">签出后，其他人都无法使用它。完成本书后，请将其签回库，以便其他人可以使用它。</span><span class="sxs-lookup"><span data-stu-id="c4e50-110">No one else can use it while you have it checked out. When you are finished with the book, you check it back into the library, so others can use it.</span></span>

<span data-ttu-id="c4e50-111">使用 AGPM 开发 Gpo 时：</span><span class="sxs-lookup"><span data-stu-id="c4e50-111">When developing GPOs using AGPM:</span></span>

1.  <span data-ttu-id="c4e50-112">创建新的受控 GPO 或控制以前不受管理的 GPO。</span><span class="sxs-lookup"><span data-stu-id="c4e50-112">Create a new controlled GPO or control a previously uncontrolled GPO.</span></span>

2.  <span data-ttu-id="c4e50-113">签出 GPO，以便你和你可以对其进行修改。</span><span class="sxs-lookup"><span data-stu-id="c4e50-113">Check out the GPO, so you and only you can modify it.</span></span>

3.  <span data-ttu-id="c4e50-114">编辑 GPO。</span><span class="sxs-lookup"><span data-stu-id="c4e50-114">Edit the GPO.</span></span>

4.  <span data-ttu-id="c4e50-115">签入编辑后的 GPO，以便其他人可以对其进行修改，或者可对其进行部署。</span><span class="sxs-lookup"><span data-stu-id="c4e50-115">Check in the edited GPO, so others can modify it, or so it can be deployed.</span></span>

5.  <span data-ttu-id="c4e50-116">查看更改。</span><span class="sxs-lookup"><span data-stu-id="c4e50-116">Review the changes.</span></span>

6.  <span data-ttu-id="c4e50-117">将 GPO 部署到生产环境。</span><span class="sxs-lookup"><span data-stu-id="c4e50-117">Deploy the GPO to the production environment.</span></span>

## <span data-ttu-id="c4e50-118">基于角色的委派</span><span class="sxs-lookup"><span data-stu-id="c4e50-118">Role-based delegation</span></span>


<span data-ttu-id="c4e50-119">AGPM 提供了全面、易于使用的基于角色的委派。</span><span class="sxs-lookup"><span data-stu-id="c4e50-119">AGPM provides comprehensive, easy-to-use role-based delegation.</span></span> <span data-ttu-id="c4e50-120">域级权限允许 AGPM 管理员提供对单个域的访问权限，而无需提供对其他域的访问权限。</span><span class="sxs-lookup"><span data-stu-id="c4e50-120">Domain-level permissions allow AGPM Administrators to provide access to individual domains without providing access to other domains.</span></span> <span data-ttu-id="c4e50-121">基于 GPO 的委派使 AGPM 管理员可以仅访问特定 Gpo。</span><span class="sxs-lookup"><span data-stu-id="c4e50-121">GPO-based delegation enables AGPM Administrators to allow access only to specific GPOs.</span></span>

<span data-ttu-id="c4e50-122">在 AGPM 内，有一些专门定义的角色： AGPM 管理员（完全控制）、审批者、编辑者和审阅者。</span><span class="sxs-lookup"><span data-stu-id="c4e50-122">Within AGPM, there are specifically defined roles: AGPM Administrator (Full Control), Approver, Editor, and Reviewer.</span></span> <span data-ttu-id="c4e50-123">AGPM 管理员角色包括所有其他角色的权限。</span><span class="sxs-lookup"><span data-stu-id="c4e50-123">The AGPM Administrator role includes the permissions for all other roles.</span></span> <span data-ttu-id="c4e50-124">默认情况下，仅审批者有能力将 Gpo 部署到生产环境，保护环境不受经验较少的编辑器意外出错。</span><span class="sxs-lookup"><span data-stu-id="c4e50-124">By default, only Approvers have the power to deploy GPOs to the production environment, protecting the environment from inadvertent mistakes by less experienced Editors.</span></span> <span data-ttu-id="c4e50-125">此外，默认情况下，所有角色都包含审阅者角色，因此能够在报表中查看 GPO 设置。</span><span class="sxs-lookup"><span data-stu-id="c4e50-125">Also by default, all roles include the Reviewer role and therefore the ability to view GPO settings in reports.</span></span> <span data-ttu-id="c4e50-126">但是，AGPM 为 AGPM 管理员提供了自定义 GPO 访问的灵活性，以满足组织的需求。</span><span class="sxs-lookup"><span data-stu-id="c4e50-126">However, AGPM provides an AGPM Administrator with the flexibility to customize GPO access to fit the needs of your organization.</span></span>

## <span data-ttu-id="c4e50-127">多组策略管理员环境中的委派</span><span class="sxs-lookup"><span data-stu-id="c4e50-127">Delegation in a multiple Group Policy administrator environment</span></span>


<span data-ttu-id="c4e50-128">在多个用户对 Gpo 进行更改的环境中，AGPM 管理员将权限作为组或个人委派给编辑者、审批者和审阅者。</span><span class="sxs-lookup"><span data-stu-id="c4e50-128">In an environment where multiple people make changes to GPOs, an AGPM Administrator delegates permission to Editors, Approvers, and Reviewers, either as groups or as individuals.</span></span> <span data-ttu-id="c4e50-129">有关编辑器和审批者的典型 GPO 开发过程，请参阅[清单：创建、编辑和部署 GPO](checklist-create-edit-and-deploy-a-gpo.md)。</span><span class="sxs-lookup"><span data-stu-id="c4e50-129">For a typical GPO development process for an Editor and an Approver, see [Checklist: Create, Edit, and Deploy a GPO](checklist-create-edit-and-deploy-a-gpo.md).</span></span>

### <span data-ttu-id="c4e50-130">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="c4e50-130">Additional references</span></span>

-   [<span data-ttu-id="c4e50-131">清单：创建、编辑和部署 GPO</span><span class="sxs-lookup"><span data-stu-id="c4e50-131">Checklist: Create, Edit, and Deploy a GPO</span></span>](checklist-create-edit-and-deploy-a-gpo.md)

-   [<span data-ttu-id="c4e50-132">执行 AGPM 管理员任务</span><span class="sxs-lookup"><span data-stu-id="c4e50-132">Performing AGPM Administrator Tasks</span></span>](performing-agpm-administrator-tasks.md)

-   [<span data-ttu-id="c4e50-133">执行编辑者任务</span><span class="sxs-lookup"><span data-stu-id="c4e50-133">Performing Editor Tasks</span></span>](performing-editor-tasks.md)

-   [<span data-ttu-id="c4e50-134">执行审批者任务</span><span class="sxs-lookup"><span data-stu-id="c4e50-134">Performing Approver Tasks</span></span>](performing-approver-tasks.md)

-   [<span data-ttu-id="c4e50-135">执行审阅者任务</span><span class="sxs-lookup"><span data-stu-id="c4e50-135">Performing Reviewer Tasks</span></span>](performing-reviewer-tasks.md)

-   [<span data-ttu-id="c4e50-136">高级组策略管理疑难解答</span><span class="sxs-lookup"><span data-stu-id="c4e50-136">Troubleshooting Advanced Group Policy Management</span></span>](troubleshooting-advanced-group-policy-management.md)

-   [<span data-ttu-id="c4e50-137">用户界面：高级组策略管理</span><span class="sxs-lookup"><span data-stu-id="c4e50-137">User Interface: Advanced Group Policy Management</span></span>](user-interface-advanced-group-policy-management.md)

 

 





