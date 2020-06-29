---
title: 部署 GPO
description: 部署 GPO
author: dansimp
ms.assetid: 3767b722-db43-40f1-a714-bb8e38bcaa10
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 71c08a3b2d4f5af5bc7f1b69f964e9bb707d889c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802807"
---
# <span data-ttu-id="93fb0-103">部署 GPO</span><span class="sxs-lookup"><span data-stu-id="93fb0-103">Deploy a GPO</span></span>


<span data-ttu-id="93fb0-104">审批者可以将新的或已编辑的组策略对象（GPO）部署到生产环境。</span><span class="sxs-lookup"><span data-stu-id="93fb0-104">An Approver can deploy a new or edited Group Policy Object (GPO) to the production environment.</span></span> <span data-ttu-id="93fb0-105">有关重新部署 GPO 的早期版本的信息，请参阅回退[到 gpo 的以前版本](roll-back-to-a-previous-version-of-a-gpo-agpm30ops.md)。</span><span class="sxs-lookup"><span data-stu-id="93fb0-105">For information about redeploying a previous version of a GPO, see [Roll Back to a Previous Version of a GPO](roll-back-to-a-previous-version-of-a-gpo-agpm30ops.md).</span></span>

<span data-ttu-id="93fb0-106">需要具有审批者或 AGPM 管理员（完全控制）角色的用户帐户或高级组策略管理（AGPM）中的必要权限才能完成此过程。</span><span class="sxs-lookup"><span data-stu-id="93fb0-106">A user account with the Approver or AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management (AGPM) is required to complete this procedure.</span></span> <span data-ttu-id="93fb0-107">查看本主题中 "其他注意事项" 中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="93fb0-107">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="93fb0-108">将 GPO 部署到生产环境</span><span class="sxs-lookup"><span data-stu-id="93fb0-108">To deploy a GPO to the production environment</span></span>**

1.  <span data-ttu-id="93fb0-109">在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。</span><span class="sxs-lookup"><span data-stu-id="93fb0-109">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="93fb0-110">在 "**目录**" 选项卡上，单击 "**受控**" 选项卡以显示受控 gpo。</span><span class="sxs-lookup"><span data-stu-id="93fb0-110">On the **Contents** tab, click the **Controlled** tab to display the controlled GPOs.</span></span>

3.  <span data-ttu-id="93fb0-111">右键单击要部署的 GPO，然后单击 "**部署**"。</span><span class="sxs-lookup"><span data-stu-id="93fb0-111">Right-click the GPO to be deployed and then click **Deploy**.</span></span>

4.  <span data-ttu-id="93fb0-112">若要查看指向该 GPO 的链接，请单击 "**高级**"。</span><span class="sxs-lookup"><span data-stu-id="93fb0-112">To review links to the GPO, click **Advanced**.</span></span> <span data-ttu-id="93fb0-113">将鼠标指针暂停在树中的某个项目上以显示详细信息。</span><span class="sxs-lookup"><span data-stu-id="93fb0-113">Pause the mouse pointer on an item in the tree to display details.</span></span>

    -   <span data-ttu-id="93fb0-114">默认情况下，将还原指向该 GPO 的所有链接。</span><span class="sxs-lookup"><span data-stu-id="93fb0-114">By default, all links to the GPO will be restored.</span></span>

    -   <span data-ttu-id="93fb0-115">若要阻止还原某个链接，请清除该链接的复选框。</span><span class="sxs-lookup"><span data-stu-id="93fb0-115">To prevent a link from being restored, clear the check box for that link.</span></span>

    -   <span data-ttu-id="93fb0-116">若要阻止还原所有链接，请清除 "**部署 GPO** " 对话框中的 "**还原链接**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="93fb0-116">To prevent all links from being restored, clear the **Restore Links** check box in the **Deploy GPO** dialog box.</span></span>

5.  <span data-ttu-id="93fb0-117">单击**是**。</span><span class="sxs-lookup"><span data-stu-id="93fb0-117">Click **Yes**.</span></span> <span data-ttu-id="93fb0-118">当**进度**窗口指示整个进度完成时，单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="93fb0-118">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span>

<span data-ttu-id="93fb0-119">**注意** 若要验证是否已部署 GPO 的最新版本，请在 "**受控**" 选项卡上，双击该 GPO 以显示其**历史记录**。</span><span class="sxs-lookup"><span data-stu-id="93fb0-119">**Note** To verify whether the most recent version of a GPO has been deployed, on the **Controlled** tab, double-click the GPO to display its **History**.</span></span> <span data-ttu-id="93fb0-120">在 GPO 的**历史记录**中，"**状态**" 列指示是否已部署 gpo。</span><span class="sxs-lookup"><span data-stu-id="93fb0-120">In the **History** for the GPO, the **State** column indicates whether a GPO has been deployed.</span></span>

 

### <span data-ttu-id="93fb0-121">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="93fb0-121">Additional considerations</span></span>

-   <span data-ttu-id="93fb0-122">默认情况下，你必须是审批者或 AGPM 管理员（完全控制）才能执行此过程。</span><span class="sxs-lookup"><span data-stu-id="93fb0-122">By default, you must be an Approver or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="93fb0-123">具体而言，您必须拥有**列表内容**并为 GPO**部署 gpo**权限。</span><span class="sxs-lookup"><span data-stu-id="93fb0-123">Specifically, you must have **List Contents** and **Deploy GPO** permissions for the GPO.</span></span>

### <span data-ttu-id="93fb0-124">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="93fb0-124">Additional references</span></span>

-   [<span data-ttu-id="93fb0-125">执行审批者任务</span><span class="sxs-lookup"><span data-stu-id="93fb0-125">Performing Approver Tasks</span></span>](performing-approver-tasks-agpm30ops.md)

 

 





