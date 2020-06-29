---
title: Microsoft 高级组策略管理 4.0 操作指南
description: Microsoft 高级组策略管理 4.0 操作指南
author: dansimp
ms.assetid: 0bafeba3-20a9-4360-be5d-03f786df11ee
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b51956c319f1b0a77e4a4bdf71090be4f322236e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802635"
---
# <span data-ttu-id="a637f-103">Microsoft 高级组策略管理 4.0 操作指南</span><span class="sxs-lookup"><span data-stu-id="a637f-103">Operations Guide for Microsoft Advanced Group Policy Management 4.0</span></span>


<span data-ttu-id="a637f-104">你可以使用 Microsoft 高级组策略管理（AGPM）扩展组策略管理控制台（GPMC）的功能。</span><span class="sxs-lookup"><span data-stu-id="a637f-104">You can use Microsoft Advanced Group Policy Management (AGPM) to extend the capabilities of the Group Policy Management Console (GPMC).</span></span> <span data-ttu-id="a637f-105">AGPM 提供全面的更改控制和改进的组策略对象（Gpo）管理。</span><span class="sxs-lookup"><span data-stu-id="a637f-105">AGPM provides comprehensive change control and improved management of Group Policy Objects (GPOs).</span></span>

<span data-ttu-id="a637f-106">使用 AGPM，您可以执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="a637f-106">Using AGPM, you can do these tasks:</span></span>

-   <span data-ttu-id="a637f-107">对 Gpo 执行脱机编辑，以便你可以在将其部署到生产环境之前创建和测试它们。</span><span class="sxs-lookup"><span data-stu-id="a637f-107">Perform offline editing of GPOs so that you can create and test them before you deploy them to a production environment.</span></span>

-   <span data-ttu-id="a637f-108">在中央存档中维护 GPO 的多个版本，以便你可以在出现问题时回滚。</span><span class="sxs-lookup"><span data-stu-id="a637f-108">Maintain multiple versions of a GPO in a central archive so that you can roll back if a problem occurs.</span></span>

-   <span data-ttu-id="a637f-109">通过使用基于角色的委派，分享在多个人员之间编辑、批准和查看 Gpo 的责任。</span><span class="sxs-lookup"><span data-stu-id="a637f-109">Share the responsibility for editing, approving, and reviewing GPOs among multiple people by using role-based delegation.</span></span>

-   <span data-ttu-id="a637f-110">消除了多个组策略管理员使用 Gpo 的签入和签出功能覆盖另一个组策略的危险。</span><span class="sxs-lookup"><span data-stu-id="a637f-110">Eliminate the danger of multiple Group Policy administrators overwriting one another's work by using the check-in and check-out capability for GPOs.</span></span>

-   <span data-ttu-id="a637f-111">通过使用差异报告分析对 GPO 所做的更改，将其与另一个 GPO 或同一 GPO 的另一个版本进行比较。</span><span class="sxs-lookup"><span data-stu-id="a637f-111">Analyze changes to a GPO, comparing it to another GPO or another version of the same GPO by using difference reporting.</span></span>

-   <span data-ttu-id="a637f-112">通过使用 GPO 模板来简化创建新 Gpo 的操作，存储常见策略设置和首选项设置以用作新 Gpo 的起始点。</span><span class="sxs-lookup"><span data-stu-id="a637f-112">Simplify creating new GPOs by using GPO templates, storing common policy settings and preference settings to use as starting points for new GPOs.</span></span>

-   <span data-ttu-id="a637f-113">委派对生产环境的访问权限。</span><span class="sxs-lookup"><span data-stu-id="a637f-113">Delegate access to the production environment.</span></span>

-   <span data-ttu-id="a637f-114">搜索具有特定属性的 Gpo 并筛选显示的 Gpo 列表。</span><span class="sxs-lookup"><span data-stu-id="a637f-114">Search for GPOs with specific attributes and filter the list of GPOs displayed.</span></span>

-   <span data-ttu-id="a637f-115">将 GPO 导出到文件，以便可以将其从测试林中的域复制到生产林中的域。</span><span class="sxs-lookup"><span data-stu-id="a637f-115">Export a GPO to a file so that you can copy it from a domain in a test forest to a domain in a production forest.</span></span>

<span data-ttu-id="a637f-116">除了在 GPMC 中显示的每个 GPO 和组策略链接的 "**历史记录**" 选项卡之外，AGPM 还会在 gpmc 中显示的每个域下添加 "**更改控制**" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="a637f-116">AGPM adds a **Change Control** folder under each domain displayed in the GPMC, in addition to a **History** tab for each GPO and Group Policy link displayed in the GPMC.</span></span>

-   [<span data-ttu-id="a637f-117">高级组策略管理概述</span><span class="sxs-lookup"><span data-stu-id="a637f-117">Overview of Advanced Group Policy Management</span></span>](overview-of-advanced-group-policy-management-agpm40.md)

-   [<span data-ttu-id="a637f-118">版本控制最佳做法</span><span class="sxs-lookup"><span data-stu-id="a637f-118">Best Practices for Version Control</span></span>](best-practices-for-version-control-agpm40.md)

-   [<span data-ttu-id="a637f-119">清单：管理 AGPM 服务器和存档</span><span class="sxs-lookup"><span data-stu-id="a637f-119">Checklist: Administer the AGPM Server and Archive</span></span>](checklist-administer-the-agpm-server-and-archive-agpm40.md)

-   [<span data-ttu-id="a637f-120">清单：创建、编辑和部署 GPO</span><span class="sxs-lookup"><span data-stu-id="a637f-120">Checklist: Create, Edit, and Deploy a GPO</span></span>](checklist-create-edit-and-deploy-a-gpo-agpm40.md)

-   [<span data-ttu-id="a637f-121">搜索和筛选 GPO 列表</span><span class="sxs-lookup"><span data-stu-id="a637f-121">Search and Filter the List of GPOs</span></span>](search-and-filter-the-list-of-gpos.md)

-   [<span data-ttu-id="a637f-122">执行 AGPM 管理员任务</span><span class="sxs-lookup"><span data-stu-id="a637f-122">Performing AGPM Administrator Tasks</span></span>](performing-agpm-administrator-tasks-agpm40.md)

-   [<span data-ttu-id="a637f-123">执行编辑者任务</span><span class="sxs-lookup"><span data-stu-id="a637f-123">Performing Editor Tasks</span></span>](performing-editor-tasks-agpm40.md)

-   [<span data-ttu-id="a637f-124">执行审批者任务</span><span class="sxs-lookup"><span data-stu-id="a637f-124">Performing Approver Tasks</span></span>](performing-approver-tasks-agpm40.md)

-   [<span data-ttu-id="a637f-125">执行审阅者任务</span><span class="sxs-lookup"><span data-stu-id="a637f-125">Performing Reviewer Tasks</span></span>](performing-reviewer-tasks-agpm40.md)

-   [<span data-ttu-id="a637f-126">AGPM 疑难解答</span><span class="sxs-lookup"><span data-stu-id="a637f-126">Troubleshooting AGPM</span></span>](troubleshooting-agpm-agpm40.md)

-   [<span data-ttu-id="a637f-127">用户界面：高级组策略管理</span><span class="sxs-lookup"><span data-stu-id="a637f-127">User Interface: Advanced Group Policy Management</span></span>](user-interface-advanced-group-policy-management-agpm40.md)

 

 





