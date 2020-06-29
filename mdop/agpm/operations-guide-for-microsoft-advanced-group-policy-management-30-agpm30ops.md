---
title: Microsoft 高级组策略管理 3.0 操作指南
description: Microsoft 高级组策略管理 3.0 操作指南
author: dansimp
ms.assetid: aaefe6d1-a9e5-43eb-b4d8-85880798cb8b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4958609444a62560060a565fb8626bcc9680fd9e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803182"
---
# <span data-ttu-id="5f3a3-103">Microsoft 高级组策略管理 3.0 操作指南</span><span class="sxs-lookup"><span data-stu-id="5f3a3-103">Operations Guide for Microsoft Advanced Group Policy Management 3.0</span></span>


<span data-ttu-id="5f3a3-104">你可以使用 Microsoft 高级组策略管理（AGPM）扩展组策略管理控制台（GPMC）的功能，从而提供组策略对象（Gpo）的全面更改控制和增强管理。</span><span class="sxs-lookup"><span data-stu-id="5f3a3-104">You can use Microsoft Advanced Group Policy Management (AGPM) to extend the capabilities of the Group Policy Management Console (GPMC), providing comprehensive change control and enhanced management for Group Policy Objects (GPOs).</span></span>

<span data-ttu-id="5f3a3-105">通过 AGPM，你可以：</span><span class="sxs-lookup"><span data-stu-id="5f3a3-105">With AGPM you can:</span></span>

-   <span data-ttu-id="5f3a3-106">对 Gpo 执行脱机编辑，以便可以在部署到生产环境之前创建和测试它们。</span><span class="sxs-lookup"><span data-stu-id="5f3a3-106">Perform offline editing of GPOs, so you can create and test them before deploying to a production environment.</span></span>

-   <span data-ttu-id="5f3a3-107">将 GPO 的多个版本保留在一个中央存档中，以便你可以在出现问题时回滚。</span><span class="sxs-lookup"><span data-stu-id="5f3a3-107">Retain multiple versions of a GPO in a central archive, so you can roll back if a problem occurs.</span></span>

-   <span data-ttu-id="5f3a3-108">通过使用基于角色的委派分担在多个人员之间编辑、审批和查看 Gpo 的责任。</span><span class="sxs-lookup"><span data-stu-id="5f3a3-108">Share the responsibility for editing, approving, and reviewing GPOs among multiple people using role-based delegation.</span></span>

-   <span data-ttu-id="5f3a3-109">通过使用 Gpo 的签入/签出功能，消除多个组策略管理员相互覆盖各自的工作的危险。</span><span class="sxs-lookup"><span data-stu-id="5f3a3-109">Eliminate the danger of multiple Group Policy administrators overwriting each other's work by using a check-in/check-out capability for GPOs.</span></span>

-   <span data-ttu-id="5f3a3-110">分析对 GPO 所做的更改，将其与另一个 GPO 进行比较，或使用差异报告将同一 GPO 的另一个版本进行比较。</span><span class="sxs-lookup"><span data-stu-id="5f3a3-110">Analyze changes to a GPO, comparing it to another GPO or another version of the same GPO using difference reporting.</span></span>

-   <span data-ttu-id="5f3a3-111">通过使用 GPO 模板（存储要用作新 Gpo 起点的标准设置）简化新 Gpo 的创建。</span><span class="sxs-lookup"><span data-stu-id="5f3a3-111">Simplify the creation of new GPOs by using GPO templates, storing standard settings to use as starting points for new GPOs.</span></span>

<span data-ttu-id="5f3a3-112">AGPM 将在 GPMC 中显示的每个域下添加**更改控制**文件夹，以及在 gpmc 中显示的每个 GPO 和组策略链接的 "**历史记录**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="5f3a3-112">AGPM adds a **Change Control** folder under each domain displayed in the GPMC, as well as a **History** tab for each GPO and Group Policy link displayed in the GPMC.</span></span>

-   [<span data-ttu-id="5f3a3-113">高级组策略管理概述</span><span class="sxs-lookup"><span data-stu-id="5f3a3-113">Overview of Advanced Group Policy Management</span></span>](overview-of-advanced-group-policy-management-agpm30ops.md)

-   [<span data-ttu-id="5f3a3-114">版本控制最佳做法</span><span class="sxs-lookup"><span data-stu-id="5f3a3-114">Best Practices for Version Control</span></span>](best-practices-for-version-control.md)

-   [<span data-ttu-id="5f3a3-115">清单：管理 AGPM 服务器和存档</span><span class="sxs-lookup"><span data-stu-id="5f3a3-115">Checklist: Administer the AGPM Server and Archive</span></span>](checklist-administer-the-agpm-server-and-archive.md)

-   [<span data-ttu-id="5f3a3-116">清单：创建、编辑和部署 GPO</span><span class="sxs-lookup"><span data-stu-id="5f3a3-116">Checklist: Create, Edit, and Deploy a GPO</span></span>](checklist-create-edit-and-deploy-a-gpo-agpm30ops.md)

-   [<span data-ttu-id="5f3a3-117">执行 AGPM 管理员任务</span><span class="sxs-lookup"><span data-stu-id="5f3a3-117">Performing AGPM Administrator Tasks</span></span>](performing-agpm-administrator-tasks-agpm30ops.md)

-   [<span data-ttu-id="5f3a3-118">执行编辑者任务</span><span class="sxs-lookup"><span data-stu-id="5f3a3-118">Performing Editor Tasks</span></span>](performing-editor-tasks-agpm30ops.md)

-   [<span data-ttu-id="5f3a3-119">执行审批者任务</span><span class="sxs-lookup"><span data-stu-id="5f3a3-119">Performing Approver Tasks</span></span>](performing-approver-tasks-agpm30ops.md)

-   [<span data-ttu-id="5f3a3-120">执行审阅者任务</span><span class="sxs-lookup"><span data-stu-id="5f3a3-120">Performing Reviewer Tasks</span></span>](performing-reviewer-tasks-agpm30ops.md)

-   [<span data-ttu-id="5f3a3-121">高级组策略管理疑难解答</span><span class="sxs-lookup"><span data-stu-id="5f3a3-121">Troubleshooting Advanced Group Policy Management</span></span>](troubleshooting-advanced-group-policy-management-agpm30ops.md)

-   [<span data-ttu-id="5f3a3-122">用户界面：高级组策略管理</span><span class="sxs-lookup"><span data-stu-id="5f3a3-122">User Interface: Advanced Group Policy Management</span></span>](user-interface-advanced-group-policy-management-agpm30ops.md)

 

 





