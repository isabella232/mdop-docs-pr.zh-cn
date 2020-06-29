---
title: 请求创建新的受控 GPO
description: 请求创建新的受控 GPO
author: dansimp
ms.assetid: 4194c2f3-8116-4a35-be1a-81c84072daec
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4f9d7dd8a604bf2d2e3638142c070fed8b6d44e2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802572"
---
# <span data-ttu-id="2d7e0-103">请求创建新的受控 GPO</span><span class="sxs-lookup"><span data-stu-id="2d7e0-103">Request the Creation of a New Controlled GPO</span></span>


<span data-ttu-id="2d7e0-104">除非你是审批者或 AGPM 管理员（完全控制），否则你必须请求创建新的组策略对象（GPO）。</span><span class="sxs-lookup"><span data-stu-id="2d7e0-104">Unless you are an Approver or an AGPM Administrator (Full Control), you must request the creation of a new Group Policy Object (GPO).</span></span>

<span data-ttu-id="2d7e0-105">需要高级组策略管理（AGPM）中具有编辑者或审阅者角色或必需权限的用户帐户才能完成此过程。</span><span class="sxs-lookup"><span data-stu-id="2d7e0-105">A user account with the Editor or Reviewer role or necessary permissions in Advanced Group Policy Management (AGPM) is required to complete this procedure.</span></span> <span data-ttu-id="2d7e0-106">查看本主题中 "其他注意事项" 中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="2d7e0-106">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="2d7e0-107">使用通过 AGPM 管理的更改控制创建新 GPO</span><span class="sxs-lookup"><span data-stu-id="2d7e0-107">To create a new GPO with change control managed through AGPM</span></span>**

1.  <span data-ttu-id="2d7e0-108">在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。</span><span class="sxs-lookup"><span data-stu-id="2d7e0-108">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="2d7e0-109">右键单击 "**更改控件**"，然后单击 "**新建受控制的 GPO**"。</span><span class="sxs-lookup"><span data-stu-id="2d7e0-109">Right-click **Change Control**, and then click **New Controlled GPO**.</span></span>

3.  <span data-ttu-id="2d7e0-110">除非你有创建 Gpo 的特殊权限，否则你必须提交创建请求。</span><span class="sxs-lookup"><span data-stu-id="2d7e0-110">Unless you have special permission to create GPOs, you must submit a request for creation.</span></span> <span data-ttu-id="2d7e0-111">在 "**新建受控 GPO** " 对话框中：</span><span class="sxs-lookup"><span data-stu-id="2d7e0-111">In the **New Controlled GPO** dialog box:</span></span>

    1.  <span data-ttu-id="2d7e0-112">若要接收请求的副本，请在 "**抄送**" 字段中输入您的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="2d7e0-112">To receive a copy of the request, enter your e-mail address in the **Cc** field.</span></span>

    2.  <span data-ttu-id="2d7e0-113">键入新 GPO 的名称。</span><span class="sxs-lookup"><span data-stu-id="2d7e0-113">Type a name for the new GPO.</span></span>

    3.  <span data-ttu-id="2d7e0-114">可选：键入新 GPO 的注释。</span><span class="sxs-lookup"><span data-stu-id="2d7e0-114">Optional: Type a comment for the new GPO.</span></span>

    4.  <span data-ttu-id="2d7e0-115">若要在批准后立即将新 GPO 部署到生产环境，请单击 "**创建 live**"。</span><span class="sxs-lookup"><span data-stu-id="2d7e0-115">To deploy the new GPO to the production environment immediately upon approval, click **Create live**.</span></span> <span data-ttu-id="2d7e0-116">若要将新的 GPO 脱机创建而不在批准后立即进行部署，请单击 "**脱机创建**"。</span><span class="sxs-lookup"><span data-stu-id="2d7e0-116">To create the new GPO offline without immediately deploying it upon approval, click **Create offline**.</span></span>

    5.  <span data-ttu-id="2d7e0-117">选择要用作新 GPO 的起始点的 GPO 模板。</span><span class="sxs-lookup"><span data-stu-id="2d7e0-117">Select the GPO template to use as a starting point for the new GPO.</span></span>

    6.  <span data-ttu-id="2d7e0-118">单击**提交**。</span><span class="sxs-lookup"><span data-stu-id="2d7e0-118">Click **Submit**.</span></span>

4.  <span data-ttu-id="2d7e0-119">当**进度**窗口指示整个进度完成时，单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="2d7e0-119">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="2d7e0-120">新的 GPO 将显示在 "**挂起**" 选项卡上的 gpo 列表中。当审批者批准你的请求后，GPO 将移到 "已**控制**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="2d7e0-120">The new GPO is displayed in the list of GPOs on the **Pending** tab. When an Approver has approved your request, the GPO will be moved to the **Controlled** tab.</span></span>

### <span data-ttu-id="2d7e0-121">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="2d7e0-121">Additional considerations</span></span>

-   <span data-ttu-id="2d7e0-122">默认情况下，你必须是编辑者或审阅者才能执行此过程。</span><span class="sxs-lookup"><span data-stu-id="2d7e0-122">By default, you must be an Editor or a Reviewer to perform this procedure.</span></span> <span data-ttu-id="2d7e0-123">具体而言，您必须具有域的 "**列表内容**" 权限。</span><span class="sxs-lookup"><span data-stu-id="2d7e0-123">Specifically, you must have **List Contents** permission for the domain.</span></span>

-   <span data-ttu-id="2d7e0-124">若要撤消已批准的请求，请单击 "**挂起**" 选项卡。右键单击该 GPO，然后单击 "**撤消**"。</span><span class="sxs-lookup"><span data-stu-id="2d7e0-124">To withdraw your request before it has been approved, click the **Pending** tab. Right-click the GPO, then click **Withdraw**.</span></span> <span data-ttu-id="2d7e0-125">GPO 将被破坏。</span><span class="sxs-lookup"><span data-stu-id="2d7e0-125">The GPO will be destroyed.</span></span>

### <span data-ttu-id="2d7e0-126">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="2d7e0-126">Additional references</span></span>

-   [<span data-ttu-id="2d7e0-127">创建、控制或导入 GPO</span><span class="sxs-lookup"><span data-stu-id="2d7e0-127">Creating, Controlling, or Importing a GPO</span></span>](creating-controlling-or-importing-a-gpo-agpm30ops.md)

 

 





