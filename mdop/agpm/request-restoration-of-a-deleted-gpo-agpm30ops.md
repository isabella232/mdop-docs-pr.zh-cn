---
title: 请求还原已删除的 GPO
description: 请求还原已删除的 GPO
author: dansimp
ms.assetid: dcc3baea-8af7-4886-a301-98b6ac5819cd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f85620ed7d9afe676caabe4ce0f7da4fd8d5ae13
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802588"
---
# <span data-ttu-id="63c09-103">请求还原已删除的 GPO</span><span class="sxs-lookup"><span data-stu-id="63c09-103">Request Restoration of a Deleted GPO</span></span>


<span data-ttu-id="63c09-104">除非你是审批者或 AGPM 管理员（完全控制），否则你必须请求从回收站还原已删除的组策略对象（GPO），以将其返回到存档。</span><span class="sxs-lookup"><span data-stu-id="63c09-104">Unless you are an Approver or an AGPM Administrator (Full Control), you must request the restoration of a deleted Group Policy Object (GPO) from the Recycle Bin to return it to the archive.</span></span>

<span data-ttu-id="63c09-105">需要高级组策略管理（AGPM）中具有编辑器角色或必需权限的用户帐户才能完成此过程。</span><span class="sxs-lookup"><span data-stu-id="63c09-105">A user account with the Editor role or necessary permissions in Advanced Group Policy Management (AGPM) is required to complete this procedure.</span></span> <span data-ttu-id="63c09-106">查看本主题中 "其他注意事项" 中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="63c09-106">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="63c09-107">请求还原已删除的 GPO</span><span class="sxs-lookup"><span data-stu-id="63c09-107">To request the restoration of a deleted GPO</span></span>**

1.  <span data-ttu-id="63c09-108">在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。</span><span class="sxs-lookup"><span data-stu-id="63c09-108">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="63c09-109">在 "**目录**" 选项卡上，单击 "**回收站**" 选项卡以显示已删除的 gpo。</span><span class="sxs-lookup"><span data-stu-id="63c09-109">On the **Contents** tab, click the **Recycle Bin** tab to display the deleted GPOs.</span></span>

3.  <span data-ttu-id="63c09-110">右键单击要还原的 GPO，然后单击 "**还原**"。</span><span class="sxs-lookup"><span data-stu-id="63c09-110">Right-click the GPO you want to restore, and then click **Restore**.</span></span>

4.  <span data-ttu-id="63c09-111">除非你拥有还原 Gpo 的特殊权限，否则你必须提交已删除 GPO 的还原请求。</span><span class="sxs-lookup"><span data-stu-id="63c09-111">Unless you have special permission to restore GPOs, you must submit a request for restoration of the deleted GPO.</span></span> <span data-ttu-id="63c09-112">若要接收请求的副本，请在 "**抄送**" 字段中键入您的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="63c09-112">To receive a copy of the request, type your e-mail address in the **Cc** field.</span></span> <span data-ttu-id="63c09-113">键入要显示在 GPO 审核跟踪中的注释，然后单击 "**提交**"。</span><span class="sxs-lookup"><span data-stu-id="63c09-113">Type a comment to be displayed in the audit trail for the GPO, and then click **Submit**.</span></span>

5.  <span data-ttu-id="63c09-114">当**进度**窗口指示整个进度完成时，单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="63c09-114">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="63c09-115">该 GPO 将从 "**回收站**" 选项卡中删除，并显示在 "**受控**" 选项卡上。</span><span class="sxs-lookup"><span data-stu-id="63c09-115">The GPO is removed from the **Recycle Bin** tab and is displayed on the **Controlled** tab.</span></span>

<span data-ttu-id="63c09-116">**注意** 如果从生产环境中删除了某个 GPO，则将其还原到存档不会自动将其重新部署到生产环境。</span><span class="sxs-lookup"><span data-stu-id="63c09-116">**Note** If a GPO was deleted from the production environment, restoring it to the archive will not automatically redeploy it to the production environment.</span></span> <span data-ttu-id="63c09-117">若要将 GPO 返回到生产环境，请部署 GPO。</span><span class="sxs-lookup"><span data-stu-id="63c09-117">To return the GPO to the production environment, deploy the GPO.</span></span> <span data-ttu-id="63c09-118">有关信息，请参阅[部署 GPO](deploy-a-gpo-agpm30ops.md)。</span><span class="sxs-lookup"><span data-stu-id="63c09-118">For information, see [Deploy a GPO](deploy-a-gpo-agpm30ops.md).</span></span>

 

### <span data-ttu-id="63c09-119">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="63c09-119">Additional considerations</span></span>

-   <span data-ttu-id="63c09-120">默认情况下，你必须是编辑器才能执行此过程。</span><span class="sxs-lookup"><span data-stu-id="63c09-120">By default, you must be an Editor to perform this procedure.</span></span> <span data-ttu-id="63c09-121">具体而言，您必须具有该 GPO 的 "**列表内容**" 和 "**编辑设置**" 权限。</span><span class="sxs-lookup"><span data-stu-id="63c09-121">Specifically, you must have **List Contents** and **Edit Settings** permission for the GPO.</span></span>

-   <span data-ttu-id="63c09-122">若要撤消已批准的请求，请单击 "**挂起**" 选项卡。右键单击该 GPO，然后单击 "**撤消**"。</span><span class="sxs-lookup"><span data-stu-id="63c09-122">To withdraw your request before it has been approved, click the **Pending** tab. Right-click the GPO, and then click **Withdraw**.</span></span> <span data-ttu-id="63c09-123">GPO 将返回到 "**回收站**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="63c09-123">The GPO will be returned to the **Recycle Bin** tab.</span></span>

### <span data-ttu-id="63c09-124">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="63c09-124">Additional references</span></span>

-   [<span data-ttu-id="63c09-125">删除、还原或销毁 GPO</span><span class="sxs-lookup"><span data-stu-id="63c09-125">Deleting, Restoring, or Destroying a GPO</span></span>](deleting-restoring-or-destroying-a-gpo-agpm30ops.md)

 

 





