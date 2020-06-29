---
title: 高级组策略管理概述
description: 高级组策略管理概述
author: dansimp
ms.assetid: 3a8d1e58-12b9-42bd-898f-6d57514dfbb9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: feb43972c78ed12501e372800c1f5ec19609477a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803179"
---
# <span data-ttu-id="34702-103">高级组策略管理概述</span><span class="sxs-lookup"><span data-stu-id="34702-103">Overview of Advanced Group Policy Management</span></span>


<span data-ttu-id="34702-104">你可以使用高级组策略管理（AGPM）扩展组策略管理控制台（GPMC）的功能，以便为组策略对象（Gpo）提供全面的更改控制和改进的管理。</span><span class="sxs-lookup"><span data-stu-id="34702-104">You can use Advanced Group Policy Management (AGPM) to extend the capabilities of the Group Policy Management Console (GPMC) to provide comprehensive change control and improved management for Group Policy Objects (GPOs).</span></span>

## <span data-ttu-id="34702-105">带有更改控制的组策略对象开发</span><span class="sxs-lookup"><span data-stu-id="34702-105">Group Policy object development with change control</span></span>


<span data-ttu-id="34702-106">使用 AGPM，你可以将每个 GPO 的副本存储在一个中央存档中，以便组策略管理员可以在不立即影响 GPO 的已部署版本的情况下查看和更改它。</span><span class="sxs-lookup"><span data-stu-id="34702-106">With AGPM, you can store a copy of each GPO in a central archive so that Group Policy administrators can view and change it offline without immediately affecting the deployed version of the GPO.</span></span> <span data-ttu-id="34702-107">此外，AGPM 将在存档中存储每个受控制 GPO 版本的副本，以便你可以在需要时回滚到早期版本。</span><span class="sxs-lookup"><span data-stu-id="34702-107">Additionally, AGPM stores a copy of each version of each controlled GPO in the archive so that you can roll back to an earlier version if necessary.</span></span>

<span data-ttu-id="34702-108">"签入" 和 "签出" 一词的使用方式与在库中（或提供用于编程开发的更改控制、版本控制或源代码管理）的应用程序中一样。</span><span class="sxs-lookup"><span data-stu-id="34702-108">The terms "check in" and "check out" are used just as in a library (or in applications that provide change control, version control, or source control for programming development).</span></span> <span data-ttu-id="34702-109">若要使用库中的书籍，请将其从库中签出。</span><span class="sxs-lookup"><span data-stu-id="34702-109">To use a book that is in a library, you check it out from the library.</span></span> <span data-ttu-id="34702-110">签出后，其他人都无法使用它。完成本书后，请将其签回库，以便其他人可以使用它。</span><span class="sxs-lookup"><span data-stu-id="34702-110">No one else can use it while you have it checked out. When you are finished with the book, you check it back into the library, so others can use it.</span></span>

<span data-ttu-id="34702-111">使用 AGPM 开发 Gpo 时：</span><span class="sxs-lookup"><span data-stu-id="34702-111">When you develop GPOs by using AGPM:</span></span>

1.  <span data-ttu-id="34702-112">创建新的受控 GPO 或控制以前不受管理的 GPO。</span><span class="sxs-lookup"><span data-stu-id="34702-112">Create a new controlled GPO or control a previously uncontrolled GPO.</span></span>

2.  <span data-ttu-id="34702-113">签出 GPO，以便你和你可以更改它。</span><span class="sxs-lookup"><span data-stu-id="34702-113">Check out the GPO, so that you and only you can change it.</span></span>

3.  <span data-ttu-id="34702-114">编辑 GPO。</span><span class="sxs-lookup"><span data-stu-id="34702-114">Edit the GPO.</span></span>

4.  <span data-ttu-id="34702-115">签入编辑后的 GPO，以便其他人可以对其进行更改，也可以将其部署。</span><span class="sxs-lookup"><span data-stu-id="34702-115">Check in the edited GPO, so that others can change it, or so that it can be deployed.</span></span>

5.  <span data-ttu-id="34702-116">查看更改。</span><span class="sxs-lookup"><span data-stu-id="34702-116">Review the changes.</span></span>

6.  <span data-ttu-id="34702-117">将 GPO 部署到生产环境。</span><span class="sxs-lookup"><span data-stu-id="34702-117">Deploy the GPO to the production environment.</span></span>

## <span data-ttu-id="34702-118">基于角色的委派</span><span class="sxs-lookup"><span data-stu-id="34702-118">Role-based delegation</span></span>


<span data-ttu-id="34702-119">AGPM 提供了全面、易于使用的基于角色的委派，可用于管理对存档中的 Gpo 的访问。</span><span class="sxs-lookup"><span data-stu-id="34702-119">AGPM provides comprehensive, easy-to-use role-based delegation for managing access to GPOs in the archive.</span></span> <span data-ttu-id="34702-120">域级权限使 AGPM 管理员可以在不提供对其他域的访问权限的情况下提供对单个域的访问权限。</span><span class="sxs-lookup"><span data-stu-id="34702-120">Domain-level permissions enable AGPM Administrators to provide access to individual domains without providing access to other domains.</span></span> <span data-ttu-id="34702-121">基于 GPO 的委派使 AGPM 管理员能够提供对特定 Gpo 的访问权限，而无需提供域范围的访问权限。</span><span class="sxs-lookup"><span data-stu-id="34702-121">GPO-based delegation enables AGPM Administrators to provide access to specific GPOs without providing domain-wide access.</span></span>

<span data-ttu-id="34702-122">在 AGPM 内，有一些专门定义的角色： AGPM 管理员（完全控制）、审批者、编辑者和审阅者。</span><span class="sxs-lookup"><span data-stu-id="34702-122">Within AGPM, there are specifically defined roles: AGPM Administrator (Full Control), Approver, Editor, and Reviewer.</span></span> <span data-ttu-id="34702-123">AGPM 管理员角色包括所有其他角色的权限。</span><span class="sxs-lookup"><span data-stu-id="34702-123">The AGPM Administrator role includes the permissions for all other roles.</span></span> <span data-ttu-id="34702-124">默认情况下，只有审批者有能力将 Gpo 部署到生产环境，通过较少经验丰富的编辑器保护环境不受错误。</span><span class="sxs-lookup"><span data-stu-id="34702-124">By default, only Approvers have the power to deploy GPOs to the production environment, protecting the environment from mistakes by less experienced Editors.</span></span> <span data-ttu-id="34702-125">此外，默认情况下，所有角色都包含审阅者角色，因此能够在报表中查看 GPO 设置。</span><span class="sxs-lookup"><span data-stu-id="34702-125">Also by default, all roles include the Reviewer role and therefore the ability to view GPO settings in reports.</span></span> <span data-ttu-id="34702-126">但是，AGPM 为 AGPM 管理员提供了自定义 GPO 访问的灵活性，以满足组织的需求。</span><span class="sxs-lookup"><span data-stu-id="34702-126">However, AGPM provides an AGPM Administrator with the flexibility to customize GPO access to fit the needs of your organization.</span></span>

## <span data-ttu-id="34702-127">多组策略管理员环境中的委派</span><span class="sxs-lookup"><span data-stu-id="34702-127">Delegation in a multiple Group Policy administrator environment</span></span>


<span data-ttu-id="34702-128">在多个用户更改 Gpo 的环境中，AGPM 管理员将权限作为组或个人委派给编辑者、审批者和审阅者。</span><span class="sxs-lookup"><span data-stu-id="34702-128">In an environment where multiple people change GPOs, an AGPM Administrator delegates permission to Editors, Approvers, and Reviewers, either as groups or as individuals.</span></span> <span data-ttu-id="34702-129">有关编辑器和审批者的典型 GPO 开发过程，请参阅[清单：创建、编辑和部署 GPO](checklist-create-edit-and-deploy-a-gpo-agpm30ops.md)。</span><span class="sxs-lookup"><span data-stu-id="34702-129">For a typical GPO development process for an Editor and an Approver, see [Checklist: Create, Edit, and Deploy a GPO](checklist-create-edit-and-deploy-a-gpo-agpm30ops.md).</span></span>

### <span data-ttu-id="34702-130">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="34702-130">Additional references</span></span>

-   [<span data-ttu-id="34702-131">Microsoft 高级组策略管理 3.0 操作指南</span><span class="sxs-lookup"><span data-stu-id="34702-131">Operations Guide for Microsoft Advanced Group Policy Management 3.0</span></span>](operations-guide-for-microsoft-advanced-group-policy-management-30-agpm30ops.md)

 

 





