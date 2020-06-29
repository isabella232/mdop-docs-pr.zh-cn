---
title: 签入 GPO
description: 签入 GPO
author: dansimp
ms.assetid: e428cfff-651f-4903-bf01-d742714d2fa9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6adbcfa1c2b0d79389bc16dd1dde5afc0a4ec4a5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802100"
---
# <span data-ttu-id="cc71b-103">签入 GPO</span><span class="sxs-lookup"><span data-stu-id="cc71b-103">Check In a GPO</span></span>


<span data-ttu-id="cc71b-104">通常情况下，编辑器应签入其修改完成后已编辑过的组策略对象（Gpo）。</span><span class="sxs-lookup"><span data-stu-id="cc71b-104">Ordinarily, Editors should check in Group Policy objects (GPOs) that they have edited when their modifications are complete.</span></span> <span data-ttu-id="cc71b-105">（有关详细信息，请参阅在[脱机状态下编辑 GPO](edit-a-gpo-offline.md)。）但是，如果编辑器不可用，则审批者还可以签入 GPO。</span><span class="sxs-lookup"><span data-stu-id="cc71b-105">(For details, see [Edit a GPO Offline](edit-a-gpo-offline.md).) However, if the Editor is unavailable, an Approver can also check in a GPO.</span></span>

<span data-ttu-id="cc71b-106">必须具有编辑者、审批者或 AGPM 管理员（完全控制）角色的用户帐户或高级组策略管理中的必需权限才能完成此过程。</span><span class="sxs-lookup"><span data-stu-id="cc71b-106">A user account with the Editor, Approver, or AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management is required to complete this procedure.</span></span> <span data-ttu-id="cc71b-107">查看本主题中 "其他注意事项" 中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="cc71b-107">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="cc71b-108">签入由编辑器签出的 GPO</span><span class="sxs-lookup"><span data-stu-id="cc71b-108">To check in a GPO that has been checked out by an Editor</span></span>**

1.  <span data-ttu-id="cc71b-109">在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。</span><span class="sxs-lookup"><span data-stu-id="cc71b-109">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="cc71b-110">在 "详细信息" 窗格中的 "**目录**" 选项卡上，单击 "**受控**" 选项卡以显示受控 gpo。</span><span class="sxs-lookup"><span data-stu-id="cc71b-110">On the **Contents** tab in the details pane, click the **Controlled** tab to display the controlled GPOs.</span></span>

    -   <span data-ttu-id="cc71b-111">若要放弃编辑器所做的任何更改，请右键单击该 GPO，单击 "**撤消签出**"，然后单击 **"是"** 进行确认。</span><span class="sxs-lookup"><span data-stu-id="cc71b-111">To discard any changes made by the Editor, right-click the GPO, click **Undo Check Out**, and then click **Yes** to confirm.</span></span>

    -   <span data-ttu-id="cc71b-112">若要保留编辑器所做的更改，请右键单击该 GPO，然后单击 "**签入**"。</span><span class="sxs-lookup"><span data-stu-id="cc71b-112">To retain changes made by the Editor, right-click the GPO and then click **Check In**.</span></span>

3.  <span data-ttu-id="cc71b-113">键入要显示在 GPO 审核跟踪中的注释，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="cc71b-113">Type a comment to be displayed in the audit trail of the GPO, and then click **OK**.</span></span>

4.  <span data-ttu-id="cc71b-114">当**进度**窗口指示整个进度完成时，单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="cc71b-114">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="cc71b-115">在 "**受控**" 选项卡上，将 GPO 的状态标识为 **"已签入**"。</span><span class="sxs-lookup"><span data-stu-id="cc71b-115">On the **Controlled** tab, the state of the GPO is identified as **Checked In**.</span></span>

### <span data-ttu-id="cc71b-116">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="cc71b-116">Additional considerations</span></span>

-   <span data-ttu-id="cc71b-117">默认情况下，你必须是编辑者、审批者或 AGPM 管理员（完全控制）才能执行此过程。</span><span class="sxs-lookup"><span data-stu-id="cc71b-117">By default, you must be an Editor, an Approver, or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="cc71b-118">具体而言，您必须具有**列表内容**并**编辑设置**或为 gpo**部署 gpo**权限。</span><span class="sxs-lookup"><span data-stu-id="cc71b-118">Specifically, you must have **List Contents** and either **Edit Settings** or **Deploy GPO** permissions for the GPO.</span></span> <span data-ttu-id="cc71b-119">如果您不是审批者或 AGPM 管理员（或具有 "**部署 GPO**权限" 的其他组策略管理员），则您必须是已签出 GPO 的编辑器。</span><span class="sxs-lookup"><span data-stu-id="cc71b-119">If you are not an Approver or AGPM Administrator (or other Group Policy administrator with **Deploy GPO** permission), you must be the Editor who has checked out the GPO.</span></span>

### <span data-ttu-id="cc71b-120">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="cc71b-120">Additional references</span></span>

-   [<span data-ttu-id="cc71b-121">执行审批者任务</span><span class="sxs-lookup"><span data-stu-id="cc71b-121">Performing Approver Tasks</span></span>](performing-approver-tasks.md)

-   [<span data-ttu-id="cc71b-122">脱机编辑 GPO</span><span class="sxs-lookup"><span data-stu-id="cc71b-122">Edit a GPO Offline</span></span>](edit-a-gpo-offline.md)

 

 





