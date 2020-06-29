---
title: 执行 AGPM 管理员任务
description: 执行 AGPM 管理员任务
author: dansimp
ms.assetid: 9678b0f4-70a5-411e-a896-afa4dc9ea6c4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 26b412e5b22e46af938d127751fdca1da722a8c6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803165"
---
# <span data-ttu-id="7ec18-103">执行 AGPM 管理员任务</span><span class="sxs-lookup"><span data-stu-id="7ec18-103">Performing AGPM Administrator Tasks</span></span>


<span data-ttu-id="7ec18-104">在高级组策略管理（AGPM）中，AGPM 管理员（完全控制）配置域范围的选项以及将权限委派给审批者、编辑者、审阅者和其他 AGPM 管理员。</span><span class="sxs-lookup"><span data-stu-id="7ec18-104">In Advanced Group Policy Management (AGPM), an AGPM Administrator (Full Control) configures domain-wide options and delegates permissions to Approvers, Editors, Reviewers, and other AGPM Administrators.</span></span> <span data-ttu-id="7ec18-105">默认情况下，AGPM 管理员是拥有 "完全控制" 权限的个人（所有 AGPM 权限），以及因此可以执行与任何角色相关联的任务。</span><span class="sxs-lookup"><span data-stu-id="7ec18-105">By default, an AGPM Administrator is an individual with Full Control—all AGPM permissions—and who therefore can perform tasks associated with any role.</span></span>

<span data-ttu-id="7ec18-106">在多个用户开发组策略对象（Gpo）的环境中，你可以选择所有 AGPM 用户是否执行相同的任务以及是否具有相同的访问权限级别，或者 AGPM 管理员是否将权限委派给编辑 Gpo 和向生产环境部署 Gpo 的审批者。</span><span class="sxs-lookup"><span data-stu-id="7ec18-106">In an environment in which multiple people develop Group Policy Objects (GPOs), you can choose whether all AGPM users perform the same tasks and have the same level of access or whether AGPM Administrators delegate permissions to Editors who make changes to GPOs and to Approvers who deploy GPOs to the production environment.</span></span> <span data-ttu-id="7ec18-107">AGPM 管理员可以配置权限以满足组织的需求。</span><span class="sxs-lookup"><span data-stu-id="7ec18-107">AGPM Administrators can configure permissions to meet the needs of your organization.</span></span>

-   <span data-ttu-id="7ec18-108">[配置高级组策略管理](configuring-advanced-group-policy-management.md)：配置 AGPM 服务器连接和电子邮件通知、委派对生产环境中的 gpo 的访问权限，以及配置日志记录和跟踪以进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="7ec18-108">[Configuring Advanced Group Policy Management](configuring-advanced-group-policy-management.md): Configure the AGPM Server Connection and e-mail notification, delegate access to GPOs in the production environment, and configure logging and tracing for troubleshooting.</span></span>

-   <span data-ttu-id="7ec18-109">[管理存档](managing-the-archive.md)：委派对存档中的 gpo 的访问，并限制存储的每个 GPO 的版本数。</span><span class="sxs-lookup"><span data-stu-id="7ec18-109">[Managing the Archive](managing-the-archive.md): Delegate access to GPOs in the archive and limit the number of versions of each GPO stored.</span></span>

-   <span data-ttu-id="7ec18-110">[管理 Agpm 服务](managing-the-agpm-service-agpm30ops.md)：停止和启动 AGPM 服务，或者更改已存档路径、Agpm 服务帐户或 agpm 服务侦听的端口。</span><span class="sxs-lookup"><span data-stu-id="7ec18-110">[Managing the AGPM Service](managing-the-agpm-service-agpm30ops.md): Stop and start the AGPM Service or change the archive path, the AGPM Service Account, or the port on which the AGPM Service listens.</span></span>

-   <span data-ttu-id="7ec18-111">[移动 Agpm 服务器和存档](move-the-agpm-server-and-the-archive.md)：将 agpm 服务、存档或两者移动到其他服务器。</span><span class="sxs-lookup"><span data-stu-id="7ec18-111">[Move the AGPM Server and the Archive](move-the-agpm-server-and-the-archive.md): Move the AGPM Service, the archive, or both to a different server.</span></span>

<span data-ttu-id="7ec18-112">此外，由于 AGPM 管理员角色包括所有其他角色的权限，AGPM 管理员可以执行通常与任何其他角色相关联的任务。</span><span class="sxs-lookup"><span data-stu-id="7ec18-112">Also, because the AGPM Administrator role includes the permissions for all other roles, an AGPM Administrator can perform the tasks normally associated with any other role.</span></span>

-   <span data-ttu-id="7ec18-113">[执行审批者任务](performing-approver-tasks-agpm30ops.md)，例如创建、部署或删除 gpo</span><span class="sxs-lookup"><span data-stu-id="7ec18-113">[Performing Approver Tasks](performing-approver-tasks-agpm30ops.md), such as creating, deploying, or deleting GPOs</span></span>

-   <span data-ttu-id="7ec18-114">执行编辑、重命名、标记或导入 Gpo、创建模板或设置默认模板的[编辑器任务](performing-editor-tasks-agpm30ops.md)</span><span class="sxs-lookup"><span data-stu-id="7ec18-114">[Performing Editor Tasks](performing-editor-tasks-agpm30ops.md), such as editing, renaming, labeling, or importing GPOs, creating templates, or setting a default template</span></span>

-   <span data-ttu-id="7ec18-115">[执行审阅者任务](performing-reviewer-tasks-agpm30ops.md)，例如审阅设置和比较 gpo</span><span class="sxs-lookup"><span data-stu-id="7ec18-115">[Performing Reviewer Tasks](performing-reviewer-tasks-agpm30ops.md), such as reviewing settings and comparing GPOs</span></span>

### <span data-ttu-id="7ec18-116">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="7ec18-116">Additional considerations</span></span>

<span data-ttu-id="7ec18-117">默认情况下，AGPM 管理员角色具有 "完全控制" （所有 AGPM 权限）：</span><span class="sxs-lookup"><span data-stu-id="7ec18-117">By default, the AGPM Administrator role has Full Control—all AGPM permissions:</span></span>

-   <span data-ttu-id="7ec18-118">列表内容</span><span class="sxs-lookup"><span data-stu-id="7ec18-118">List Contents</span></span>

-   <span data-ttu-id="7ec18-119">读取设置</span><span class="sxs-lookup"><span data-stu-id="7ec18-119">Read Settings</span></span>

-   <span data-ttu-id="7ec18-120">编辑设置</span><span class="sxs-lookup"><span data-stu-id="7ec18-120">Edit Settings</span></span>

-   <span data-ttu-id="7ec18-121">创建 GPO</span><span class="sxs-lookup"><span data-stu-id="7ec18-121">Create GPO</span></span>

-   <span data-ttu-id="7ec18-122">部署 GPO</span><span class="sxs-lookup"><span data-stu-id="7ec18-122">Deploy GPO</span></span>

-   <span data-ttu-id="7ec18-123">删除 GPO</span><span class="sxs-lookup"><span data-stu-id="7ec18-123">Delete GPO</span></span>

-   <span data-ttu-id="7ec18-124">修改选项</span><span class="sxs-lookup"><span data-stu-id="7ec18-124">Modify Options</span></span>

-   <span data-ttu-id="7ec18-125">修改安全性</span><span class="sxs-lookup"><span data-stu-id="7ec18-125">Modify Security</span></span>

-   <span data-ttu-id="7ec18-126">创建模板</span><span class="sxs-lookup"><span data-stu-id="7ec18-126">Create Template</span></span>

<span data-ttu-id="7ec18-127">"**修改选项**" 和 "**修改安全**权限" 对于 AGPM 管理员的角色是唯一的。</span><span class="sxs-lookup"><span data-stu-id="7ec18-127">The **Modify Options** and **Modify Security** permissions are unique to the role of AGPM Administrator.</span></span>

 

 





