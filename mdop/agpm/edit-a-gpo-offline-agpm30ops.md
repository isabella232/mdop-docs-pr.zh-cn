---
title: 脱机编辑 GPO
description: 脱机编辑 GPO
author: dansimp
ms.assetid: 51677d8a-6209-41b5-82ed-4f3be817abc0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 74b6ae9fdf11456a9a45cb5504ed97a9bc6aecb4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801891"
---
# <span data-ttu-id="c5c13-103">脱机编辑 GPO</span><span class="sxs-lookup"><span data-stu-id="c5c13-103">Edit a GPO Offline</span></span>


<span data-ttu-id="c5c13-104">若要对受控制的组策略对象（GPO）进行更改，必须首先从存档中签出 GPO 的副本。</span><span class="sxs-lookup"><span data-stu-id="c5c13-104">To make changes to a controlled Group Policy Object (GPO), you must first check out a copy of the GPO from the archive.</span></span> <span data-ttu-id="c5c13-105">任何其他人都将无法修改 GPO，直到再次签入该 GPO，以防多个组策略管理员的冲突更改被引入。</span><span class="sxs-lookup"><span data-stu-id="c5c13-105">No one else will be able to modify the GPO until it is checked in again, preventing the introduction of conflicting changes by multiple Group Policy administrators.</span></span> <span data-ttu-id="c5c13-106">修改完 GPO 后，将其签入存档，以便可以对其进行检查并将其部署到生产环境。</span><span class="sxs-lookup"><span data-stu-id="c5c13-106">When you have finished modifying the GPO, you check it into the archive so that it can be reviewed and deployed to the production environment.</span></span>

<span data-ttu-id="c5c13-107">具有编辑器或 AGPM 管理员（完全控制）角色的用户帐户、创建 GPO 的审批者的用户帐户，或者需要高级组策略管理（AGPM）中具有必要权限的用户帐户才能完成此过程。</span><span class="sxs-lookup"><span data-stu-id="c5c13-107">A user account with the Editor or AGPM Administrator (Full Control) role, the user account of the Approver who created the GPO, or a user account with the necessary permissions in Advanced Group Policy Management (AGPM) is required to complete this procedure.</span></span> <span data-ttu-id="c5c13-108">查看本主题中 "其他注意事项" 中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="c5c13-108">Review the details in "Additional considerations" in this topic.</span></span>

## <span data-ttu-id="c5c13-109">脱机编辑 GPO</span><span class="sxs-lookup"><span data-stu-id="c5c13-109">Editing a GPO offline</span></span>


<span data-ttu-id="c5c13-110">若要编辑 GPO，请从存档中签出 GPO，脱机编辑 GPO，然后将 GPO 检查到存档中，以便可以查看和部署该 GPO （或由其他编辑器修改）。</span><span class="sxs-lookup"><span data-stu-id="c5c13-110">To edit a GPO, you check out the GPO from the archive, edit the GPO offline, and then check the GPO into the archive so that it can be reviewed and deployed (or modified by other Editors).</span></span>

-   [<span data-ttu-id="c5c13-111">从存档中签出 GPO 进行编辑</span><span class="sxs-lookup"><span data-stu-id="c5c13-111">Check out a GPO from the archive for editing</span></span>](#bkmk-checkout)

-   [<span data-ttu-id="c5c13-112">脱机编辑 GPO</span><span class="sxs-lookup"><span data-stu-id="c5c13-112">Edit a GPO offline</span></span>](#bkmk-edit)

-   [<span data-ttu-id="c5c13-113">将 GPO 签入存档</span><span class="sxs-lookup"><span data-stu-id="c5c13-113">Check a GPO into the archive</span></span>](#bkmk-checkin)

### <a href="" id="bkmk-checkout"></a>

**<span data-ttu-id="c5c13-114">从存档中签出 GPO 以进行编辑</span><span class="sxs-lookup"><span data-stu-id="c5c13-114">To check out a GPO from the archive for editing</span></span>**

1.  <span data-ttu-id="c5c13-115">在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。</span><span class="sxs-lookup"><span data-stu-id="c5c13-115">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="c5c13-116">在 "**目录**" 选项卡上，单击 "**受控**" 选项卡以显示受控 gpo。</span><span class="sxs-lookup"><span data-stu-id="c5c13-116">On the **Contents** tab, click the **Controlled** tab to display the controlled GPOs.</span></span>

3.  <span data-ttu-id="c5c13-117">右键单击要编辑的 GPO，然后单击 "**签出**"。</span><span class="sxs-lookup"><span data-stu-id="c5c13-117">Right-click the GPO to be edited, and then click **Check Out**.</span></span>

4.  <span data-ttu-id="c5c13-118">键入要在已签出的 GPO 的历史记录中显示的注释，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="c5c13-118">Type a comment to be displayed in the History of the GPO while it is checked out, and then click **OK**.</span></span>

5.  <span data-ttu-id="c5c13-119">当**进度**窗口指示整个进度完成时，单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="c5c13-119">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="c5c13-120">在 "**受控**" 选项卡上，GPO 的状态现在标识为 "**已签出**"。</span><span class="sxs-lookup"><span data-stu-id="c5c13-120">On the **Controlled** tab, the state of the GPO is now identified as **Checked Out**.</span></span>

### <a href="" id="bkmk-edit"></a>

**<span data-ttu-id="c5c13-121">脱机编辑 GPO</span><span class="sxs-lookup"><span data-stu-id="c5c13-121">To edit a GPO offline</span></span>**

1.  <span data-ttu-id="c5c13-122">在 "**受控**" 选项卡上，右键单击要编辑的 GPO，然后单击 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="c5c13-122">On the **Controlled** tab, right-click the GPO to be edited, and then click **Edit**.</span></span>

2.  <span data-ttu-id="c5c13-123">在 "**组策略管理编辑器**" 窗口中，对 GPO 的脱机副本进行更改。</span><span class="sxs-lookup"><span data-stu-id="c5c13-123">In the **Group Policy Management Editor** window, make changes to an offline copy of the GPO.</span></span>

    <span data-ttu-id="c5c13-124">**注意** 若要禁用所有计算机配置设置或所有用户配置设置，请在 "**组策略管理编辑器**" 窗口中右键单击该 GPO，然后单击 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="c5c13-124">**Note** To disable all Computer Configuration settings or all User Configuration settings, right-click the GPO in the **Group Policy Management Editor** window and click **Properties**.</span></span> <span data-ttu-id="c5c13-125">根据需要，选择 "**禁用计算机配置设置**" 或 "**禁用用户配置设置**"。</span><span class="sxs-lookup"><span data-stu-id="c5c13-125">Select **Disable Computer Configuration settings** or **Disable User Configuration settings** as appropriate.</span></span>

     

3.  <span data-ttu-id="c5c13-126">完成对 GPO 的修改后，请关闭 "**组策略管理编辑器**" 窗口。</span><span class="sxs-lookup"><span data-stu-id="c5c13-126">When you have finished modifying the GPO, close the **Group Policy Management Editor** window.</span></span>

### <a href="" id="bkmk-checkin"></a>

**<span data-ttu-id="c5c13-127">将 GPO 签入存档</span><span class="sxs-lookup"><span data-stu-id="c5c13-127">To check a GPO into the archive</span></span>**

1.  <span data-ttu-id="c5c13-128">在 "**受控**" 选项卡上：</span><span class="sxs-lookup"><span data-stu-id="c5c13-128">On the **Controlled** tab:</span></span>

    -   <span data-ttu-id="c5c13-129">如果你未对 GPO 进行任何更改，请右键单击该 GPO，然后单击 "**撤消签出**"，然后单击 **"是"** 进行确认。</span><span class="sxs-lookup"><span data-stu-id="c5c13-129">If you have made no changes to the GPO, right-click the GPO and click **Undo Check Out**, and then click **Yes** to confirm.</span></span>

    -   <span data-ttu-id="c5c13-130">如果你已对 GPO 进行了更改，请右键单击该 GPO，然后单击 "**签入**"。</span><span class="sxs-lookup"><span data-stu-id="c5c13-130">If you have made changes to the GPO, right-click the GPO and click **Check In**.</span></span>

2.  <span data-ttu-id="c5c13-131">键入要显示在 GPO 审核跟踪中的注释，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="c5c13-131">Type a comment to be displayed in the audit trail of the GPO, and then click **OK**.</span></span>

3.  <span data-ttu-id="c5c13-132">当**进度**窗口指示整个进度完成时，单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="c5c13-132">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="c5c13-133">在 "**受控**" 选项卡上，将 GPO 的状态标识为 **"已签入**"。</span><span class="sxs-lookup"><span data-stu-id="c5c13-133">On the **Controlled** tab, the state of the GPO is identified as **Checked In**.</span></span>

### <span data-ttu-id="c5c13-134">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="c5c13-134">Additional considerations</span></span>

-   <span data-ttu-id="c5c13-135">若要签出和编辑 GPO，默认情况下，你必须是创建或控制 GPO、编辑器或 AGPM 管理员（完全控制）的审批者。</span><span class="sxs-lookup"><span data-stu-id="c5c13-135">To check out and edit a GPO, by default you must be the Approver who created or controlled the GPO, an Editor, or an AGPM Administrator (Full Control).</span></span> <span data-ttu-id="c5c13-136">具体而言，您必须具有该 GPO 的 "**列表内容**" 和 "**编辑设置**" 权限。</span><span class="sxs-lookup"><span data-stu-id="c5c13-136">Specifically, you must have **List Contents** and **Edit Settings** permissions for the GPO.</span></span> <span data-ttu-id="c5c13-137">此外，若要编辑 GPO，您必须是已签出 GPO 的个人。</span><span class="sxs-lookup"><span data-stu-id="c5c13-137">Additionally, to edit the GPO you must be the individual who has checked out the GPO.</span></span>

-   <span data-ttu-id="c5c13-138">若要签入 GPO，默认情况下，您必须是编辑者、审批者或 AGPM 管理员（"完全控制"）。</span><span class="sxs-lookup"><span data-stu-id="c5c13-138">To check in a GPO, by default, you must be an Editor, an Approver, or an AGPM Administrator (Full Control).</span></span> <span data-ttu-id="c5c13-139">具体而言，您必须具有**列表内容**并**编辑设置**或为 gpo**部署 gpo**权限。</span><span class="sxs-lookup"><span data-stu-id="c5c13-139">Specifically, you must have **List Contents** and either **Edit Settings** or **Deploy GPO** permissions for the GPO.</span></span> <span data-ttu-id="c5c13-140">如果您不是审批者或 AGPM 管理员（或具有 "**部署 GPO**权限" 的其他组策略管理员），则您必须是已签出 GPO 的编辑器。</span><span class="sxs-lookup"><span data-stu-id="c5c13-140">If you are not an Approver or AGPM Administrator (or other Group Policy administrator with **Deploy GPO** permission), you must be the Editor who has checked out the GPO.</span></span>

-   <span data-ttu-id="c5c13-141">编辑 GPO 时，其他 GPO 中的程序包的任何组策略软件安装升级都应引用部署的 GPO，而不是已签出的副本。</span><span class="sxs-lookup"><span data-stu-id="c5c13-141">When editing a GPO, any Group Policy Software Installation upgrade of a package in another GPO should reference the deployed GPO, and not the checked-out copy.</span></span>

### <span data-ttu-id="c5c13-142">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="c5c13-142">Additional references</span></span>

-   [<span data-ttu-id="c5c13-143">编辑 GPO</span><span class="sxs-lookup"><span data-stu-id="c5c13-143">Editing a GPO</span></span>](editing-a-gpo-agpm30ops.md)

-   <span data-ttu-id="c5c13-144">查看 GPO</span><span class="sxs-lookup"><span data-stu-id="c5c13-144">Reviewing a GPO</span></span>

    -   [<span data-ttu-id="c5c13-145">查看 GPO 设置</span><span class="sxs-lookup"><span data-stu-id="c5c13-145">Review GPO Settings</span></span>](review-gpo-settings-agpm30ops.md)

    -   [<span data-ttu-id="c5c13-146">查看 GPO 链接</span><span class="sxs-lookup"><span data-stu-id="c5c13-146">Review GPO Links</span></span>](review-gpo-links-agpm30ops.md)

    -   [<span data-ttu-id="c5c13-147">识别各 GPO、GPO 版本或模板之间的差异</span><span class="sxs-lookup"><span data-stu-id="c5c13-147">Identify Differences Between GPOs, GPO Versions, or Templates</span></span>](identify-differences-between-gpos-gpo-versions-or-templates-agpm30ops.md)

-   <span data-ttu-id="c5c13-148">部署 GPO</span><span class="sxs-lookup"><span data-stu-id="c5c13-148">Deploying a GPO</span></span>

    -   [<span data-ttu-id="c5c13-149">请求部署 GPO</span><span class="sxs-lookup"><span data-stu-id="c5c13-149">Request Deployment of a GPO</span></span>](request-deployment-of-a-gpo-agpm30ops.md)

    -   [<span data-ttu-id="c5c13-150">部署 GPO</span><span class="sxs-lookup"><span data-stu-id="c5c13-150">Deploy a GPO</span></span>](deploy-a-gpo-agpm30ops.md)

 

 





