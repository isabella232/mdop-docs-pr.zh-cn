---
title: 执行编辑者任务
description: 执行编辑者任务
author: dansimp
ms.assetid: 81976a01-2a95-4256-b703-9fb3c884ef34
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b8e23bb91d8762d19eed9ae817967ba5a57505a9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802604"
---
# <span data-ttu-id="caf23-103">执行编辑者任务</span><span class="sxs-lookup"><span data-stu-id="caf23-103">Performing Editor Tasks</span></span>


<span data-ttu-id="caf23-104">在高级组策略管理（AGPM）中，编辑器是由 AGPM 管理员（完全控制）授权的人员，用于更改组策略对象（Gpo）和创建 GPO 模板。</span><span class="sxs-lookup"><span data-stu-id="caf23-104">In Advanced Group Policy Management (AGPM), an Editor is a person authorized by an AGPM Administrator (Full Control) to change Group Policy Objects (GPOs) and create GPO templates.</span></span> <span data-ttu-id="caf23-105">此外，编辑器还可请求创建、删除或还原 GPO。</span><span class="sxs-lookup"><span data-stu-id="caf23-105">Additionally, an Editor can request that a GPO be created, deleted, or restored.</span></span> <span data-ttu-id="caf23-106">审批者必须批准该请求才能实施。</span><span class="sxs-lookup"><span data-stu-id="caf23-106">An Approver must approve the request for it to be implemented.</span></span> <span data-ttu-id="caf23-107">编辑者可以将 GPO 导出到文件，以便可以将其复制到另一个林中的域，并导入从其他域复制的 GPO。</span><span class="sxs-lookup"><span data-stu-id="caf23-107">An Editor can export a GPO to a file so that it can be copied to a domain in another forest, and import a GPO that was copied from another domain.</span></span>

<span data-ttu-id="caf23-108">**重要提示** 请确保你连接到 Gpo 的中心存档。</span><span class="sxs-lookup"><span data-stu-id="caf23-108">**Important** Make sure that you are connecting to the central archive for GPOs.</span></span> <span data-ttu-id="caf23-109">有关详细信息，请参阅[配置 AGPM 服务器连接](configure-an-agpm-server-connection-agpm40.md)。</span><span class="sxs-lookup"><span data-stu-id="caf23-109">For more information, see [Configure an AGPM Server Connection](configure-an-agpm-server-connection-agpm40.md).</span></span>

 

-   [<span data-ttu-id="caf23-110">创建或控制 GPO</span><span class="sxs-lookup"><span data-stu-id="caf23-110">Creating or Controlling a GPO</span></span>](creating-or-controlling-a-gpo-agpm40-ed.md)

-   [<span data-ttu-id="caf23-111">编辑 GPO</span><span class="sxs-lookup"><span data-stu-id="caf23-111">Editing a GPO</span></span>](editing-a-gpo-agpm40.md)

-   [<span data-ttu-id="caf23-112">使用测试环境</span><span class="sxs-lookup"><span data-stu-id="caf23-112">Using a Test Environment</span></span>](using-a-test-environment.md)

-   [<span data-ttu-id="caf23-113">请求部署 GPO</span><span class="sxs-lookup"><span data-stu-id="caf23-113">Request Deployment of a GPO</span></span>](request-deployment-of-a-gpo-agpm40.md)

-   [<span data-ttu-id="caf23-114">创建模板和设置默认模板</span><span class="sxs-lookup"><span data-stu-id="caf23-114">Creating a Template and Setting a Default Template</span></span>](creating-a-template-and-setting-a-default-template-agpm40.md)

-   [<span data-ttu-id="caf23-115">删除或还原 GPO</span><span class="sxs-lookup"><span data-stu-id="caf23-115">Deleting or Restoring a GPO</span></span>](deleting-or-restoring-a-gpo-agpm40.md)

<span data-ttu-id="caf23-116">**注意** 由于编辑器角色包括审阅者角色的权限，因此编辑人员还可以查看设置和比较 Gpo。</span><span class="sxs-lookup"><span data-stu-id="caf23-116">**Note** Because the Editor role includes the permissions for the Reviewer role, an Editor can also review settings and compare GPOs.</span></span> <span data-ttu-id="caf23-117">有关详细信息，请参阅[执行审阅者任务](performing-reviewer-tasks-agpm40.md)。</span><span class="sxs-lookup"><span data-stu-id="caf23-117">See [Performing Reviewer Tasks](performing-reviewer-tasks-agpm40.md) for more information.</span></span>

 

### <span data-ttu-id="caf23-118">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="caf23-118">Additional considerations</span></span>

<span data-ttu-id="caf23-119">默认情况下，为编辑器角色提供以下权限：</span><span class="sxs-lookup"><span data-stu-id="caf23-119">By default, the following permissions are provided for the Editor role:</span></span>

-   <span data-ttu-id="caf23-120">列表内容</span><span class="sxs-lookup"><span data-stu-id="caf23-120">List Contents</span></span>

-   <span data-ttu-id="caf23-121">读取设置</span><span class="sxs-lookup"><span data-stu-id="caf23-121">Read Settings</span></span>

-   <span data-ttu-id="caf23-122">编辑设置</span><span class="sxs-lookup"><span data-stu-id="caf23-122">Edit Settings</span></span>

-   <span data-ttu-id="caf23-123">导出 GPO</span><span class="sxs-lookup"><span data-stu-id="caf23-123">Export GPO</span></span>

-   <span data-ttu-id="caf23-124">导入 GPO</span><span class="sxs-lookup"><span data-stu-id="caf23-124">Import GPO</span></span>

-   <span data-ttu-id="caf23-125">创建模板</span><span class="sxs-lookup"><span data-stu-id="caf23-125">Create Template</span></span>

 

 





