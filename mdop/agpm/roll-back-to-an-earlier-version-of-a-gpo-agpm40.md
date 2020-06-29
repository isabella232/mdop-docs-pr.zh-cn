---
title: 回滚到以前版本的 GPO
description: 回滚到以前版本的 GPO
author: dansimp
ms.assetid: 06ce9251-95e0-46d0-99c2-b9a0690e5891
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 1146a8ecaf25796b9ac105ba46ea7f27b06fc8aa
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802551"
---
# <span data-ttu-id="c1c1c-103">回滚到以前版本的 GPO</span><span class="sxs-lookup"><span data-stu-id="c1c1c-103">Roll Back to an Earlier Version of a GPO</span></span>


<span data-ttu-id="c1c1c-104">通过从其历史记录重新部署 GPO 的早期版本，审批者可以回滚对组策略对象（GPO）的更改。</span><span class="sxs-lookup"><span data-stu-id="c1c1c-104">An Approver can roll back changes to a Group Policy Object (GPO) by redeploying an earlier version of the GPO from its history.</span></span> <span data-ttu-id="c1c1c-105">部署早期版本的 GPO 会覆盖当前生产中的 GPO 版本。</span><span class="sxs-lookup"><span data-stu-id="c1c1c-105">Deploying an earlier version of a GPO overwrites the version of the GPO currently in production.</span></span>

<span data-ttu-id="c1c1c-106">需要具有审批者或 AGPM 管理员（完全控制）角色的用户帐户或高级组策略管理（AGPM）中的必要权限才能完成此过程。</span><span class="sxs-lookup"><span data-stu-id="c1c1c-106">A user account with the Approver or AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management (AGPM) is required to complete this procedure.</span></span> <span data-ttu-id="c1c1c-107">查看本主题中 "其他注意事项" 中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="c1c1c-107">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="c1c1c-108">将 GPO 的早期版本部署到域的生产环境</span><span class="sxs-lookup"><span data-stu-id="c1c1c-108">To deploy an earlier version of a GPO to the production environment of the domain</span></span>**

1.  <span data-ttu-id="c1c1c-109">在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。</span><span class="sxs-lookup"><span data-stu-id="c1c1c-109">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="c1c1c-110">在 "**目录**" 选项卡上，单击 "**受控**" 选项卡以显示受控 gpo。</span><span class="sxs-lookup"><span data-stu-id="c1c1c-110">On the **Contents** tab, click the **Controlled** tab to display the controlled GPOs.</span></span>

3.  <span data-ttu-id="c1c1c-111">双击要部署的 GPO 以显示其**历史记录**。</span><span class="sxs-lookup"><span data-stu-id="c1c1c-111">Double-click the GPO to be deployed to display its **History**.</span></span>

4.  <span data-ttu-id="c1c1c-112">右键单击要部署的版本，单击 "**部署**"，然后单击 **"是"**。</span><span class="sxs-lookup"><span data-stu-id="c1c1c-112">Right-click the version to be deployed, click **Deploy**, and then click **Yes**.</span></span>

5.  <span data-ttu-id="c1c1c-113">当**进度**窗口指示整个进度完成时，单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="c1c1c-113">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="c1c1c-114">在 "**历史记录**" 窗口中，单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="c1c1c-114">In the **History** window, click **Close**.</span></span>

<span data-ttu-id="c1c1c-115">**注意** 若要验证已重新部署的版本是否与所需版本相匹配，请检查这两个版本的差异报告。</span><span class="sxs-lookup"><span data-stu-id="c1c1c-115">**Note** To verify that the version that has been redeployed matches the version intended, examine a difference report for the two versions.</span></span> <span data-ttu-id="c1c1c-116">在 GPO 的 "**历史记录**" 窗口中，突出显示两个版本，然后右键单击并选择 "**差异**" 和 " **HTML 报表**" 或 " **XML 报表**"。</span><span class="sxs-lookup"><span data-stu-id="c1c1c-116">In the **History** window for the GPO, highlight the two versions, and then right-click and select **Difference** and either **HTML Report** or **XML Report**.</span></span>

 

### <span data-ttu-id="c1c1c-117">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="c1c1c-117">Additional considerations</span></span>

-   <span data-ttu-id="c1c1c-118">默认情况下，你必须是审批者或 AGPM 管理员（完全控制）才能执行此过程。</span><span class="sxs-lookup"><span data-stu-id="c1c1c-118">By default, you must be an Approver or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="c1c1c-119">具体而言，您必须拥有**列表内容**并为 GPO**部署 gpo**权限。</span><span class="sxs-lookup"><span data-stu-id="c1c1c-119">Specifically, you must have **List Contents** and **Deploy GPO** permissions for the GPO.</span></span>

### <span data-ttu-id="c1c1c-120">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="c1c1c-120">Additional references</span></span>

-   [<span data-ttu-id="c1c1c-121">执行审批者任务</span><span class="sxs-lookup"><span data-stu-id="c1c1c-121">Performing Approver Tasks</span></span>](performing-approver-tasks-agpm40.md)

 

 





