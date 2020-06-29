---
title: 执行 AGPM 管理员任务
description: 执行 AGPM 管理员任务
author: dansimp
ms.assetid: bc746f39-bdc9-4e2a-bc48-c3c7905de098
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 609b5b8b27fe24ff93e86bea7113929b1e04984d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803164"
---
# <span data-ttu-id="6c36a-103">执行 AGPM 管理员任务</span><span class="sxs-lookup"><span data-stu-id="6c36a-103">Performing AGPM Administrator Tasks</span></span>


<span data-ttu-id="6c36a-104">高级组策略管理（AGPM）允许 AGPM 管理员（完全控制）配置域范围的选项以及将权限委派给审批者、编辑者、审阅者和 AGPM 管理员。</span><span class="sxs-lookup"><span data-stu-id="6c36a-104">Advanced Group Policy Management (AGPM) lets an AGPM Administrator (Full Control) configure domain-wide options and delegate permissions to Approvers, Editors, Reviewers, and AGPM Administrators.</span></span> <span data-ttu-id="6c36a-105">默认情况下，AGPM 管理员是拥有 "完全控制" 权限的人员（所有 AGPM 权限），以及因此可以执行与任何角色相关联的任务。</span><span class="sxs-lookup"><span data-stu-id="6c36a-105">By default, an AGPM Administrator is someone who has Full Control— all AGPM permissions—and who therefore can perform tasks associated with any role.</span></span>

<span data-ttu-id="6c36a-106">在多个用户开发组策略对象（Gpo）的环境中，你可以选择让所有组策略管理员执行相同的任务并具有相同级别的访问权限。</span><span class="sxs-lookup"><span data-stu-id="6c36a-106">In an environment in which multiple people develop Group Policy Objects (GPOs), you can choose to let all Group Policy administrators perform the same tasks and have the same level of access.</span></span> <span data-ttu-id="6c36a-107">或者，你可以选择让 AGPM 管理员委派权限来编辑可更改 Gpo 的权限，以及将 Gpo 部署到生产环境的审批者的权限。</span><span class="sxs-lookup"><span data-stu-id="6c36a-107">Or, you can choose to let AGPM Administrators delegate permissions to Editors who can change GPOs and to Approvers who deploy GPOs to the production environment.</span></span> <span data-ttu-id="6c36a-108">AGPM 管理员可以配置权限以满足组织的需求。</span><span class="sxs-lookup"><span data-stu-id="6c36a-108">AGPM Administrators can configure permissions to meet the needs of your organization.</span></span>

-   <span data-ttu-id="6c36a-109">[配置高级组策略管理](configuring-advanced-group-policy-management-agpm40.md)：配置 AGPM 服务器连接和电子邮件通知、委派对生产环境中的 gpo 的访问权限，以及配置日志记录和跟踪以进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="6c36a-109">[Configuring Advanced Group Policy Management](configuring-advanced-group-policy-management-agpm40.md): Configure the AGPM Server Connection and e-mail notification, delegate access to GPOs in the production environment, and configure logging and tracing for troubleshooting.</span></span>

-   <span data-ttu-id="6c36a-110">[管理存档](managing-the-archive-agpm40.md)：委派对存档中的 gpo 的访问、限制存储的每个 gpo 的版本数、从另一个域导入 gpo 以及备份和还原存档。</span><span class="sxs-lookup"><span data-stu-id="6c36a-110">[Managing the Archive](managing-the-archive-agpm40.md): Delegate access to GPOs in the archive, limit the number of versions of each GPO stored, import a GPO from another domain, and back up and restore the archive.</span></span>

-   <span data-ttu-id="6c36a-111">[管理 Agpm 服务](managing-the-agpm-service-agpm40.md)：停止和启动 AGPM 服务，或者更改已存档路径、Agpm 服务帐户或 agpm 服务侦听的端口。</span><span class="sxs-lookup"><span data-stu-id="6c36a-111">[Managing the AGPM Service](managing-the-agpm-service-agpm40.md): Stop and start the AGPM Service or change the archive path, the AGPM Service Account, or the port on which the AGPM Service listens.</span></span>

-   <span data-ttu-id="6c36a-112">[移动 Agpm 服务器和存档](move-the-agpm-server-and-the-archive-agpm40.md)：将 agpm 服务、存档或两者移动到其他服务器。</span><span class="sxs-lookup"><span data-stu-id="6c36a-112">[Move the AGPM Server and the Archive](move-the-agpm-server-and-the-archive-agpm40.md): Move the AGPM Service, the archive, or both to a different server.</span></span>

<span data-ttu-id="6c36a-113">**注意** 由于 AGPM 管理员角色包括所有其他角色的权限，因此 AGPM 管理员可以执行通常与任何其他角色相关联的任务。</span><span class="sxs-lookup"><span data-stu-id="6c36a-113">**Note** Because the AGPM Administrator role includes the permissions for all other roles, an AGPM Administrator can perform the tasks usually associated with any other role.</span></span>

<span data-ttu-id="6c36a-114">[执行审批者任务](performing-approver-tasks-agpm40.md)，例如创建、部署或删除 gpo</span><span class="sxs-lookup"><span data-stu-id="6c36a-114">[Performing Approver Tasks](performing-approver-tasks-agpm40.md), such as creating, deploying, or deleting GPOs</span></span>

<span data-ttu-id="6c36a-115">执行编辑、重命名、标记或导入 Gpo、创建模板或设置默认模板的[编辑器任务](performing-editor-tasks-agpm40.md)</span><span class="sxs-lookup"><span data-stu-id="6c36a-115">[Performing Editor Tasks](performing-editor-tasks-agpm40.md), such as editing, renaming, labeling, or importing GPOs, creating templates, or setting a default template</span></span>

<span data-ttu-id="6c36a-116">[执行审阅者任务](performing-reviewer-tasks-agpm40.md)，例如审阅设置和比较 gpo</span><span class="sxs-lookup"><span data-stu-id="6c36a-116">[Performing Reviewer Tasks](performing-reviewer-tasks-agpm40.md), such as reviewing settings and comparing GPOs</span></span>

 

### <span data-ttu-id="6c36a-117">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="6c36a-117">Additional considerations</span></span>

<span data-ttu-id="6c36a-118">默认情况下，AGPM 管理员角色具有 "完全控制" （所有 AGPM 权限）：</span><span class="sxs-lookup"><span data-stu-id="6c36a-118">By default, the AGPM Administrator role has Full Control—all AGPM permissions:</span></span>

-   <span data-ttu-id="6c36a-119">列表内容</span><span class="sxs-lookup"><span data-stu-id="6c36a-119">List Contents</span></span>

-   <span data-ttu-id="6c36a-120">读取设置</span><span class="sxs-lookup"><span data-stu-id="6c36a-120">Read Settings</span></span>

-   <span data-ttu-id="6c36a-121">编辑设置</span><span class="sxs-lookup"><span data-stu-id="6c36a-121">Edit Settings</span></span>

-   <span data-ttu-id="6c36a-122">创建 GPO</span><span class="sxs-lookup"><span data-stu-id="6c36a-122">Create GPO</span></span>

-   <span data-ttu-id="6c36a-123">部署 GPO</span><span class="sxs-lookup"><span data-stu-id="6c36a-123">Deploy GPO</span></span>

-   <span data-ttu-id="6c36a-124">删除 GPO</span><span class="sxs-lookup"><span data-stu-id="6c36a-124">Delete GPO</span></span>

-   <span data-ttu-id="6c36a-125">导出 GPO</span><span class="sxs-lookup"><span data-stu-id="6c36a-125">Export GPO</span></span>

-   <span data-ttu-id="6c36a-126">导入 GPO</span><span class="sxs-lookup"><span data-stu-id="6c36a-126">Import GPO</span></span>

-   <span data-ttu-id="6c36a-127">创建模板</span><span class="sxs-lookup"><span data-stu-id="6c36a-127">Create Template</span></span>

-   <span data-ttu-id="6c36a-128">修改选项</span><span class="sxs-lookup"><span data-stu-id="6c36a-128">Modify Options</span></span>

-   <span data-ttu-id="6c36a-129">修改安全性</span><span class="sxs-lookup"><span data-stu-id="6c36a-129">Modify Security</span></span>

<span data-ttu-id="6c36a-130">"**修改选项**" 和 "**修改安全**权限" 对于 AGPM 管理员的角色是唯一的。</span><span class="sxs-lookup"><span data-stu-id="6c36a-130">The **Modify Options** and **Modify Security** permissions are unique to the role of AGPM Administrator.</span></span>

 

 





