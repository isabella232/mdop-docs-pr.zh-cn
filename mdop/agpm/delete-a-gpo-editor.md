---
title: 删除 GPO
description: 删除 GPO
author: dansimp
ms.assetid: 66be3dde-653e-4c25-8cb7-00e7090c8d31
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6c27ddf87a12ed6010c481d93bfc85bb531f3d4f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802831"
---
# <span data-ttu-id="e9b29-103">删除 GPO</span><span class="sxs-lookup"><span data-stu-id="e9b29-103">Delete a GPO</span></span>


<span data-ttu-id="e9b29-104">作为编辑器，你可能无权完成删除组策略对象（GPO）的权限，但你有必要权限来开始该进程并向审批者提交你的请求。</span><span class="sxs-lookup"><span data-stu-id="e9b29-104">As an Editor, you may not have permission to complete the deletion of a Group Policy object (GPO), but you do have the permission necessary to begin the process and submit your request to an Approver.</span></span>

<span data-ttu-id="e9b29-105">要完成此过程，需要在高级组策略管理中具有编辑者角色或必需权限的用户帐户才能完成此过程。</span><span class="sxs-lookup"><span data-stu-id="e9b29-105">A user account with the Editor role or necessary permissions in Advanced Group Policy Management is required to complete this procedure.</span></span> <span data-ttu-id="e9b29-106">查看本主题中 "其他注意事项" 中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="e9b29-106">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="e9b29-107">请求删除受控 GPO</span><span class="sxs-lookup"><span data-stu-id="e9b29-107">To request the deletion of a controlled GPO</span></span>**

1.  <span data-ttu-id="e9b29-108">在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。</span><span class="sxs-lookup"><span data-stu-id="e9b29-108">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="e9b29-109">在 "**目录**" 选项卡上，单击 "**受控**" 选项卡以显示受控 gpo。</span><span class="sxs-lookup"><span data-stu-id="e9b29-109">On the **Contents** tab, click the **Controlled** tab to display the controlled GPOs.</span></span>

3.  <span data-ttu-id="e9b29-110">右键单击要删除的 GPO，然后单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="e9b29-110">Right-click the GPO to delete, and then click **Delete**.</span></span>

    -   <span data-ttu-id="e9b29-111">若要从存档中删除 GPO，同时在生产环境中保持 GPO 的部署版本，请单击 "**仅从存档中删除 gpo" （uncontrol）**。</span><span class="sxs-lookup"><span data-stu-id="e9b29-111">To delete the GPO from the archive while leaving the deployed version of the GPO untouched in the production environment, click **Delete GPO from archive only (uncontrol)**.</span></span>

    -   <span data-ttu-id="e9b29-112">若要从存档和生产环境中删除 GPO，请单击 "**从存档和生产中删除 gpo**"。</span><span class="sxs-lookup"><span data-stu-id="e9b29-112">To delete the GPO from both the archive and production environment, click **Delete GPO from archive and production**.</span></span>

        <span data-ttu-id="e9b29-113">除非你有删除 Gpo 的特殊权限，否则你必须提交删除已部署 GPO 的请求。</span><span class="sxs-lookup"><span data-stu-id="e9b29-113">Unless you have special permission to delete GPOs, you must submit a request for deletion of the deployed GPO.</span></span> <span data-ttu-id="e9b29-114">若要接收请求的副本，请在 "**抄送**" 字段中键入您的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="e9b29-114">To receive a copy of the request, type your e-mail address in the **Cc** field.</span></span> <span data-ttu-id="e9b29-115">键入要显示在 GPO 审核跟踪中的注释，然后单击 "**提交**"。</span><span class="sxs-lookup"><span data-stu-id="e9b29-115">Type a comment to be displayed in the audit trail for the GPO, and then click **Submit**.</span></span>

4.  <span data-ttu-id="e9b29-116">当**进度**窗口指示整个进度完成时，单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="e9b29-116">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="e9b29-117">GPO 将显示在 "**挂起**" 选项卡上的 gpo 列表中。当审批者批准你的请求后，GPO 将从 "**挂起**" 选项卡移动到 "**回收站**" 选项卡，可在该选项卡上还原或销毁。</span><span class="sxs-lookup"><span data-stu-id="e9b29-117">The GPO is displayed on the list of GPOs on the **Pending** tab. When an Approver has approved your request, the GPO will be moved from the **Pending** tab to the **Recycle Bin** tab, where it can be restored or destroyed.</span></span>

### <span data-ttu-id="e9b29-118">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="e9b29-118">Additional considerations</span></span>

-   <span data-ttu-id="e9b29-119">默认情况下，你必须是用于请求删除已部署 GPO 的编辑器。</span><span class="sxs-lookup"><span data-stu-id="e9b29-119">By default, you must be an Editor to request the deletion of a deployed GPO.</span></span> <span data-ttu-id="e9b29-120">具体而言，您必须具有该 GPO 的 "**列表内容**" 和 "**编辑设置**" 权限。</span><span class="sxs-lookup"><span data-stu-id="e9b29-120">Specifically, you must have **List Contents** and **Edit Settings** permissions for the GPO.</span></span>

-   <span data-ttu-id="e9b29-121">默认情况下，你必须是编辑者、审批者或 AGPM 管理员（完全控制）才能从存档中删除 GPO。</span><span class="sxs-lookup"><span data-stu-id="e9b29-121">By default, you must be an Editor, an Approver, or an AGPM Administrator (Full Control) to delete a GPO from the archive.</span></span> <span data-ttu-id="e9b29-122">具体而言，您必须具有**列表内容**并**编辑设置**或**删除**gpo 的 gpo 权限。</span><span class="sxs-lookup"><span data-stu-id="e9b29-122">Specifically, you must have **List Contents** and either **Edit Settings** or **Delete GPO** permissions for the GPO.</span></span>

-   <span data-ttu-id="e9b29-123">若要撤消已批准的请求，请单击 "**挂起**" 选项卡。右键单击该 GPO，然后单击 "**撤消**"。</span><span class="sxs-lookup"><span data-stu-id="e9b29-123">To withdraw your request before it has been approved, click the **Pending** tab. Right-click the GPO, and then click **Withdraw**.</span></span> <span data-ttu-id="e9b29-124">GPO 将返回到 "**受控**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="e9b29-124">The GPO will be returned to the **Controlled** tab.</span></span>

-   <span data-ttu-id="e9b29-125">若要从生产环境中删除不受管理的 GPO 而不先对其进行控制，请在**组策略管理控制台**中单击 "**林**"，单击 "**域**"，单击 " \*\* &lt; MyDomain &gt; **"，然后单击 "**组策略对象\*\*"。</span><span class="sxs-lookup"><span data-stu-id="e9b29-125">To delete an uncontrolled GPO from the production environment without first controlling it, in the **Group Policy Management Console**, click **Forest**, click **Domains**, click **&lt;MyDomain&gt;**, and then click **Group Policy Objects**.</span></span> <span data-ttu-id="e9b29-126">右键单击不受控制的 GPO，然后单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="e9b29-126">Right-click the uncontrolled GPO, and then click **Delete**.</span></span>

### <span data-ttu-id="e9b29-127">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="e9b29-127">Additional references</span></span>

-   [<span data-ttu-id="e9b29-128">执行编辑者任务</span><span class="sxs-lookup"><span data-stu-id="e9b29-128">Performing Editor Tasks</span></span>](performing-editor-tasks.md)

 

 





