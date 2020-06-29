---
title: 请求删除 GPO
description: 请求删除 GPO
author: dansimp
ms.assetid: 576ece5c-dc6d-4b5e-8628-01c15ae2c9a8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 87368d9f132d1ef7dc6a70fffa0611d33a23aa78
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801819"
---
# <span data-ttu-id="f8fba-103">请求删除 GPO</span><span class="sxs-lookup"><span data-stu-id="f8fba-103">Request Deletion of a GPO</span></span>


<span data-ttu-id="f8fba-104">除非你是审批者或 AGPM 管理员（完全控制），否则你必须请求删除组策略对象（GPO）。</span><span class="sxs-lookup"><span data-stu-id="f8fba-104">Unless you are an Approver or an AGPM Administrator (Full Control), you must request the deletion of a Group Policy Object (GPO).</span></span>

<span data-ttu-id="f8fba-105">需要高级组策略管理（AGPM）中具有编辑器角色或必需权限的用户帐户才能完成此过程。</span><span class="sxs-lookup"><span data-stu-id="f8fba-105">A user account with the Editor role or necessary permissions in Advanced Group Policy Management (AGPM) is required to complete this procedure.</span></span> <span data-ttu-id="f8fba-106">查看本主题中 "其他注意事项" 中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f8fba-106">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="f8fba-107">请求删除受控 GPO</span><span class="sxs-lookup"><span data-stu-id="f8fba-107">To request the deletion of a controlled GPO</span></span>**

1.  <span data-ttu-id="f8fba-108">在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。</span><span class="sxs-lookup"><span data-stu-id="f8fba-108">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="f8fba-109">在 "**目录**" 选项卡上，单击 "**受控**" 选项卡以显示受控 gpo。</span><span class="sxs-lookup"><span data-stu-id="f8fba-109">On the **Contents** tab, click the **Controlled** tab to display the controlled GPOs.</span></span>

3.  <span data-ttu-id="f8fba-110">右键单击要删除的 GPO，然后单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="f8fba-110">Right-click the GPO you want to delete, and then click **Delete**.</span></span>

    -   <span data-ttu-id="f8fba-111">若要从存档中删除 GPO，同时在生产环境中保持 GPO 的部署版本，请单击 "**仅从存档中删除 gpo**"。</span><span class="sxs-lookup"><span data-stu-id="f8fba-111">To delete the GPO from the archive while leaving the deployed version of the GPO untouched in the production environment, click **Delete GPO from archive only**.</span></span>

    -   <span data-ttu-id="f8fba-112">若要从存档和生产环境中删除 GPO，请单击 "**从存档和生产中删除 gpo**"。</span><span class="sxs-lookup"><span data-stu-id="f8fba-112">To delete the GPO from both the archive and production environment, click **Delete GPO from archive and production**.</span></span>

4.  <span data-ttu-id="f8fba-113">除非你有删除 Gpo 的特殊权限，否则你必须提交删除已部署 GPO 的请求。</span><span class="sxs-lookup"><span data-stu-id="f8fba-113">Unless you have special permission to delete GPOs, you must submit a request for deletion of the deployed GPO.</span></span> <span data-ttu-id="f8fba-114">若要接收请求的副本，请在 "**抄送**" 字段中键入您的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="f8fba-114">To receive a copy of the request, type your e-mail address in the **Cc** field.</span></span> <span data-ttu-id="f8fba-115">键入要显示在 GPO 审核跟踪中的注释，然后单击 "**提交**"。</span><span class="sxs-lookup"><span data-stu-id="f8fba-115">Type a comment to be displayed in the audit trail for the GPO, and then click **Submit**.</span></span>

5.  <span data-ttu-id="f8fba-116">当**进度**窗口指示整个进度完成时，单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="f8fba-116">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="f8fba-117">GPO 将显示在 "**挂起**" 选项卡上的 gpo 列表中。当审批者批准你的请求后，GPO 将从 "**挂起**" 选项卡移动到 "**回收站**" 选项卡，可在该选项卡上还原或销毁。</span><span class="sxs-lookup"><span data-stu-id="f8fba-117">The GPO is displayed on the list of GPOs on the **Pending** tab. When an Approver has approved your request, the GPO will be moved from the **Pending** tab to the **Recycle Bin** tab, where it can be restored or destroyed.</span></span>

### <span data-ttu-id="f8fba-118">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="f8fba-118">Additional considerations</span></span>

-   <span data-ttu-id="f8fba-119">默认情况下，你必须是编辑器才能执行此过程。</span><span class="sxs-lookup"><span data-stu-id="f8fba-119">By default, you must be an Editor to perform this procedure.</span></span> <span data-ttu-id="f8fba-120">具体而言，您必须具有该 GPO 的 "**列表内容**" 和 "**编辑设置**" 权限。</span><span class="sxs-lookup"><span data-stu-id="f8fba-120">Specifically, you must have **List Contents** and **Edit Settings** permissions for the GPO.</span></span>

-   <span data-ttu-id="f8fba-121">若要撤消已批准的请求，请单击 "**挂起**" 选项卡。右键单击该 GPO，然后单击 "**撤消**"。</span><span class="sxs-lookup"><span data-stu-id="f8fba-121">To withdraw your request before it has been approved, click the **Pending** tab. Right-click the GPO, and then click **Withdraw**.</span></span> <span data-ttu-id="f8fba-122">GPO 将返回到 "**受控**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="f8fba-122">The GPO will be returned to the **Controlled** tab.</span></span>

-   <span data-ttu-id="f8fba-123">若要从生产环境中删除不受管理的 GPO 而不先对其进行控制，请在**组策略管理控制台**中单击 "**林**"，单击 "**域**"，单击 " \*\* &lt; MyDomain &gt; **"，然后单击 "**组策略对象\*\*"。</span><span class="sxs-lookup"><span data-stu-id="f8fba-123">To delete an uncontrolled GPO from the production environment without first controlling it, in the **Group Policy Management Console**, click **Forest**, click **Domains**, click **&lt;MyDomain&gt;**, and then click **Group Policy Objects**.</span></span> <span data-ttu-id="f8fba-124">右键单击不受控制的 GPO，然后单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="f8fba-124">Right-click the uncontrolled GPO, and then click **Delete**.</span></span>

### <span data-ttu-id="f8fba-125">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="f8fba-125">Additional references</span></span>

-   [<span data-ttu-id="f8fba-126">执行编辑者任务</span><span class="sxs-lookup"><span data-stu-id="f8fba-126">Performing Editor Tasks</span></span>](performing-editor-tasks-agpm30ops.md)

 

 





