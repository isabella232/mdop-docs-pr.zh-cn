---
title: 执行 AGPM 管理员任务
description: 执行 AGPM 管理员任务
author: dansimp
ms.assetid: 32e694a7-be64-4943-bce2-2a3a15e5341f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0daa8df93a88ed155e9f894011d4dd835761948b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802632"
---
# <span data-ttu-id="e4305-103">执行 AGPM 管理员任务</span><span class="sxs-lookup"><span data-stu-id="e4305-103">Performing AGPM Administrator Tasks</span></span>


<span data-ttu-id="e4305-104">AGPM 管理员（完全控制）配置域范围的选项并将权限委派给审批者、编辑者、审阅者和其他 AGPM 管理员。</span><span class="sxs-lookup"><span data-stu-id="e4305-104">An AGPM Administrator (Full Control) configures domain-wide options and delegates permissions to Approvers, Editors, Reviewers, and other AGPM Administrators.</span></span> <span data-ttu-id="e4305-105">默认情况下，AGPM 管理员是具有 "完全控制" （所有高级组策略管理 \ [AGPM \] 权限）的个人，因此还可以执行与任何角色相关联的任务。</span><span class="sxs-lookup"><span data-stu-id="e4305-105">By default, an AGPM Administrator is an individual with Full Control (all Advanced Group Policy Management \[AGPM\] permissions) and therefore can also perform tasks associated with any role.</span></span>

<span data-ttu-id="e4305-106">在多人在其中开发组策略对象（Gpo）的环境中，可以选择所有高级组策略管理（AGPM）用户是否执行相同的任务以及是否具有相同的访问权限级别，或者 AGPM 管理员是否将权限委派给对 Gpo 以及向生产环境部署 Gpo 的审批者进行的更改。</span><span class="sxs-lookup"><span data-stu-id="e4305-106">In an environment in which multiple people develop Group Policy objects (GPOs), you can choose whether all Advanced Group Policy Management (AGPM) users perform the same tasks and have the same level of access or whether AGPM Administrators delegate permissions to Editors who make changes to GPOs and to Approvers who deploy GPOs to the production environment.</span></span> <span data-ttu-id="e4305-107">AGPM 管理员可以配置权限以满足组织的需求。</span><span class="sxs-lookup"><span data-stu-id="e4305-107">AGPM Administrators can configure permissions to meet the needs of your organization.</span></span>

-   [<span data-ttu-id="e4305-108">配置 AGPM 服务器连接</span><span class="sxs-lookup"><span data-stu-id="e4305-108">Configure the AGPM Server Connection</span></span>](configure-the-agpm-server-connection.md)

-   [<span data-ttu-id="e4305-109">配置电子邮件通知</span><span class="sxs-lookup"><span data-stu-id="e4305-109">Configure E-Mail Notification</span></span>](configure-e-mail-notification.md)

-   [<span data-ttu-id="e4305-110">委派域级访问权限</span><span class="sxs-lookup"><span data-stu-id="e4305-110">Delegate Domain-Level Access</span></span>](delegate-domain-level-access.md)

-   [<span data-ttu-id="e4305-111">委派针对单独 GPO 的访问权限</span><span class="sxs-lookup"><span data-stu-id="e4305-111">Delegate Access to an Individual GPO</span></span>](delegate-access-to-an-individual-gpo.md)

-   [<span data-ttu-id="e4305-112">配置记录和跟踪</span><span class="sxs-lookup"><span data-stu-id="e4305-112">Configure Logging and Tracing</span></span>](configure-logging-and-tracing.md)

-   [<span data-ttu-id="e4305-113">管理 AGPM 服务</span><span class="sxs-lookup"><span data-stu-id="e4305-113">Managing the AGPM Service</span></span>](managing-the-agpm-service.md)

    -   [<span data-ttu-id="e4305-114">启动和停止 AGPM 服务</span><span class="sxs-lookup"><span data-stu-id="e4305-114">Start and Stop the AGPM Service</span></span>](start-and-stop-the-agpm-service.md)

    -   [<span data-ttu-id="e4305-115">修改存档路径</span><span class="sxs-lookup"><span data-stu-id="e4305-115">Modify the Archive Path</span></span>](modify-the-archive-path.md)

    -   [<span data-ttu-id="e4305-116">修改 AGPM 服务帐户</span><span class="sxs-lookup"><span data-stu-id="e4305-116">Modify the AGPM Service Account</span></span>](modify-the-agpm-service-account.md)

    -   [<span data-ttu-id="e4305-117">修改 AGPM 服务侦听的端口</span><span class="sxs-lookup"><span data-stu-id="e4305-117">Modify the Port on Which the AGPM Service Listens</span></span>](modify-the-port-on-which-the-agpm-service-listens.md)

<span data-ttu-id="e4305-118">此外，由于 AGPM 管理员角色包括所有其他角色的权限，AGPM 管理员可以执行通常与任何其他角色相关联的任务。</span><span class="sxs-lookup"><span data-stu-id="e4305-118">Also, because the AGPM Administrator role includes the permissions for all other roles, an AGPM Administrator can perform the tasks normally associated with any other role.</span></span>

-   <span data-ttu-id="e4305-119">[执行审批者任务](performing-approver-tasks.md)，例如创建、部署或删除 gpo</span><span class="sxs-lookup"><span data-stu-id="e4305-119">[Performing Approver Tasks](performing-approver-tasks.md), such as creating, deploying, or deleting GPOs</span></span>

-   <span data-ttu-id="e4305-120">执行编辑、重命名、标记或导入 Gpo、创建模板或设置默认模板的[编辑器任务](performing-editor-tasks.md)</span><span class="sxs-lookup"><span data-stu-id="e4305-120">[Performing Editor Tasks](performing-editor-tasks.md), such as editing, renaming, labeling, or importing GPOs, creating templates, or setting a default template</span></span>

-   <span data-ttu-id="e4305-121">[执行审阅者任务](performing-reviewer-tasks.md)，例如审阅设置和比较 gpo</span><span class="sxs-lookup"><span data-stu-id="e4305-121">[Performing Reviewer Tasks](performing-reviewer-tasks.md), such as reviewing settings and comparing GPOs</span></span>

### <span data-ttu-id="e4305-122">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="e4305-122">Additional considerations</span></span>

<span data-ttu-id="e4305-123">默认情况下，AGPM 管理员角色具有 "完全控制" （所有 AGPM 权限）：</span><span class="sxs-lookup"><span data-stu-id="e4305-123">By default, the AGPM Administrator role has Full Control—all AGPM permissions:</span></span>

-   <span data-ttu-id="e4305-124">列表内容</span><span class="sxs-lookup"><span data-stu-id="e4305-124">List Contents</span></span>

-   <span data-ttu-id="e4305-125">读取设置</span><span class="sxs-lookup"><span data-stu-id="e4305-125">Read Settings</span></span>

-   <span data-ttu-id="e4305-126">编辑设置</span><span class="sxs-lookup"><span data-stu-id="e4305-126">Edit Settings</span></span>

-   <span data-ttu-id="e4305-127">创建 GPO</span><span class="sxs-lookup"><span data-stu-id="e4305-127">Create GPO</span></span>

-   <span data-ttu-id="e4305-128">部署 GPO</span><span class="sxs-lookup"><span data-stu-id="e4305-128">Deploy GPO</span></span>

-   <span data-ttu-id="e4305-129">删除 GPO</span><span class="sxs-lookup"><span data-stu-id="e4305-129">Delete GPO</span></span>

-   <span data-ttu-id="e4305-130">修改选项</span><span class="sxs-lookup"><span data-stu-id="e4305-130">Modify Options</span></span>

-   <span data-ttu-id="e4305-131">修改安全性</span><span class="sxs-lookup"><span data-stu-id="e4305-131">Modify Security</span></span>

-   <span data-ttu-id="e4305-132">创建模板</span><span class="sxs-lookup"><span data-stu-id="e4305-132">Create Template</span></span>

<span data-ttu-id="e4305-133">"**修改选项**" 和 "**修改安全**权限" 对于 AGPM 管理员的角色是唯一的。</span><span class="sxs-lookup"><span data-stu-id="e4305-133">The **Modify Options** and **Modify Security** permissions are unique to the role of AGPM Administrator.</span></span>

 

 





