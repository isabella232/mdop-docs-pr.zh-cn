---
title: 高级组策略管理概述
description: 高级组策略管理概述
author: dansimp
ms.assetid: 2c12f3b4-8472-4c5b-b7f8-1c98a80d6b47
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 94e47075ae865096f9fe7d327cc7b11cb54217d6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803178"
---
# <span data-ttu-id="06c2b-103">高级组策略管理概述</span><span class="sxs-lookup"><span data-stu-id="06c2b-103">Overview of Advanced Group Policy Management</span></span>


<span data-ttu-id="06c2b-104">你可以使用高级组策略管理（AGPM）扩展组策略管理控制台（GPMC）的功能，以便为组策略对象（Gpo）提供全面的更改控制和改进的管理。</span><span class="sxs-lookup"><span data-stu-id="06c2b-104">You can use Advanced Group Policy Management (AGPM) to extend the capabilities of the Group Policy Management Console (GPMC) to provide comprehensive change control and improved management for Group Policy Objects (GPOs).</span></span>

## <span data-ttu-id="06c2b-105">带有更改控制的组策略对象开发</span><span class="sxs-lookup"><span data-stu-id="06c2b-105">Group Policy object development with change control</span></span>


<span data-ttu-id="06c2b-106">使用 AGPM，你可以将每个 GPO 的副本存储在一个中央存档中，以便组策略管理员可以在不立即影响 GPO 的已部署版本的情况下查看和更改它。</span><span class="sxs-lookup"><span data-stu-id="06c2b-106">With AGPM, you can store a copy of each GPO in a central archive so that Group Policy administrators can view and change it offline without immediately affecting the deployed version of the GPO.</span></span> <span data-ttu-id="06c2b-107">此外，AGPM 将在存档中存储每个受控制 GPO 版本的副本，以便你可以在需要时回滚到早期版本。</span><span class="sxs-lookup"><span data-stu-id="06c2b-107">Additionally, AGPM stores a copy of each version of each controlled GPO in the archive so that you can roll back to an earlier version if necessary.</span></span>

<span data-ttu-id="06c2b-108">"签入" 和 "签出" 一词的使用方式与在库中（或提供用于编程开发的更改控制、版本控制或源代码管理）的应用程序中一样。</span><span class="sxs-lookup"><span data-stu-id="06c2b-108">The terms "check in" and "check out" are used just as in a library (or in applications that provide change control, version control, or source control for programming development).</span></span> <span data-ttu-id="06c2b-109">若要使用库中的书籍，请将其从库中签出。</span><span class="sxs-lookup"><span data-stu-id="06c2b-109">To use a book that is in a library, you check it out from the library.</span></span> <span data-ttu-id="06c2b-110">签出后，其他人都无法使用它。完成本书后，请将其签回库，以便其他人可以使用它。</span><span class="sxs-lookup"><span data-stu-id="06c2b-110">No one else can use it while you have it checked out. When you are finished with the book, you check it back into the library, so others can use it.</span></span>

<span data-ttu-id="06c2b-111">若要使用这些 GPO 控制功能，您将在 "组策略管理编辑器" 中单击 "更改控制" 节点。</span><span class="sxs-lookup"><span data-stu-id="06c2b-111">To use these GPO control features, you will click a Change Control node in the Group Policy Management editor.</span></span> <span data-ttu-id="06c2b-112">仅当安装了 AGPM 客户端时，才会显示 "更改控制" 节点。</span><span class="sxs-lookup"><span data-stu-id="06c2b-112">The Change Control node appears only if you have installed the AGPM Client.</span></span>

<span data-ttu-id="06c2b-113">使用 AGPM 开发 Gpo 时：</span><span class="sxs-lookup"><span data-stu-id="06c2b-113">When you develop GPOs by using AGPM:</span></span>

1.  <span data-ttu-id="06c2b-114">创建新的受控 GPO 或控制以前不受管理的 GPO。</span><span class="sxs-lookup"><span data-stu-id="06c2b-114">Create a new controlled GPO or control a previously uncontrolled GPO.</span></span>

2.  <span data-ttu-id="06c2b-115">签出 GPO，以便你和你可以更改它。</span><span class="sxs-lookup"><span data-stu-id="06c2b-115">Check out the GPO, so that you and only you can change it.</span></span>

3.  <span data-ttu-id="06c2b-116">编辑 GPO。</span><span class="sxs-lookup"><span data-stu-id="06c2b-116">Edit the GPO.</span></span>

4.  <span data-ttu-id="06c2b-117">签入编辑后的 GPO，以便其他人可以对其进行更改，也可以将其部署。</span><span class="sxs-lookup"><span data-stu-id="06c2b-117">Check in the edited GPO, so that others can change it, or so that it can be deployed.</span></span>

5.  <span data-ttu-id="06c2b-118">查看更改。</span><span class="sxs-lookup"><span data-stu-id="06c2b-118">Review the changes.</span></span>

6.  <span data-ttu-id="06c2b-119">将 GPO 部署到生产环境。</span><span class="sxs-lookup"><span data-stu-id="06c2b-119">Deploy the GPO to the production environment.</span></span>

## <span data-ttu-id="06c2b-120">基于角色的委派</span><span class="sxs-lookup"><span data-stu-id="06c2b-120">Role-based delegation</span></span>


<span data-ttu-id="06c2b-121">AGPM 提供了全面、易于使用的基于角色的委派，可用于管理对存档中的 Gpo 的访问。</span><span class="sxs-lookup"><span data-stu-id="06c2b-121">AGPM provides comprehensive, easy-to-use role-based delegation for managing access to GPOs in the archive.</span></span> <span data-ttu-id="06c2b-122">域级权限使 AGPM 管理员可以在不提供对其他域的访问权限的情况下提供对单个域的访问权限。</span><span class="sxs-lookup"><span data-stu-id="06c2b-122">Domain-level permissions enable AGPM Administrators to provide access to individual domains without providing access to other domains.</span></span> <span data-ttu-id="06c2b-123">基于 GPO 的委派使 AGPM 管理员能够提供对特定 Gpo 的访问权限，而无需提供域范围的访问权限。</span><span class="sxs-lookup"><span data-stu-id="06c2b-123">GPO-based delegation enables AGPM Administrators to provide access to specific GPOs without providing domain-wide access.</span></span>

<span data-ttu-id="06c2b-124">在 AGPM 内，有一些专门定义的角色： AGPM 管理员（完全控制）、审批者、编辑者和审阅者。</span><span class="sxs-lookup"><span data-stu-id="06c2b-124">Within AGPM, there are specifically defined roles: AGPM Administrator (Full Control), Approver, Editor, and Reviewer.</span></span> <span data-ttu-id="06c2b-125">AGPM 管理员角色包括所有其他角色的权限。</span><span class="sxs-lookup"><span data-stu-id="06c2b-125">The AGPM Administrator role includes the permissions for all other roles.</span></span> <span data-ttu-id="06c2b-126">默认情况下，只有审批者有能力将 Gpo 部署到域的生产环境，通过较少经验的编辑器保护环境不受错误。</span><span class="sxs-lookup"><span data-stu-id="06c2b-126">By default, only Approvers have the power to deploy GPOs to the production environment of a domain, protecting the environment from mistakes by less experienced Editors.</span></span> <span data-ttu-id="06c2b-127">此外，默认情况下，所有角色都包含审阅者角色，因此能够在报表中查看 GPO 设置。</span><span class="sxs-lookup"><span data-stu-id="06c2b-127">Also by default, all roles include the Reviewer role and therefore the ability to view GPO settings in reports.</span></span> <span data-ttu-id="06c2b-128">但是，AGPM 为 AGPM 管理员提供了自定义 GPO 访问的灵活性，以满足组织的需求。</span><span class="sxs-lookup"><span data-stu-id="06c2b-128">However, AGPM provides an AGPM Administrator with the flexibility to customize GPO access to fit the needs of your organization.</span></span>

## <span data-ttu-id="06c2b-129">多组策略管理员环境中的委派</span><span class="sxs-lookup"><span data-stu-id="06c2b-129">Delegation in a multiple Group Policy administrator environment</span></span>


<span data-ttu-id="06c2b-130">在多个用户更改 Gpo 的环境中，AGPM 管理员将权限作为组或个人委派给编辑者、审批者和审阅者。</span><span class="sxs-lookup"><span data-stu-id="06c2b-130">In an environment where multiple people change GPOs, an AGPM Administrator delegates permission to Editors, Approvers, and Reviewers, either as groups or as individuals.</span></span> <span data-ttu-id="06c2b-131">有关编辑器和审批者的典型 GPO 开发过程，请参阅[清单：创建、编辑和部署 GPO](checklist-create-edit-and-deploy-a-gpo-agpm40.md)。</span><span class="sxs-lookup"><span data-stu-id="06c2b-131">For a typical GPO development process for an Editor and an Approver, see [Checklist: Create, Edit, and Deploy a GPO](checklist-create-edit-and-deploy-a-gpo-agpm40.md).</span></span>

### <span data-ttu-id="06c2b-132">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="06c2b-132">Additional references</span></span>

-   [<span data-ttu-id="06c2b-133">高级组策略管理 4.0</span><span class="sxs-lookup"><span data-stu-id="06c2b-133">Advanced Group Policy Management 4.0</span></span>](advanced-group-policy-management-40.md)

 

 





