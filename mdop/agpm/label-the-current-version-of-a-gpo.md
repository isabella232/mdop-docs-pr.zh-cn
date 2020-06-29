---
title: 标记当前版本的 GPO
description: 标记当前版本的 GPO
author: dansimp
ms.assetid: 5e4e50f8-e4a8-4bda-aac4-1569d5fbd6a7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a34232dfd1f7a755dd81cdecbe3d5d1957f01294
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802692"
---
# <span data-ttu-id="1f6bc-103">标记当前版本的 GPO</span><span class="sxs-lookup"><span data-stu-id="1f6bc-103">Label the Current Version of a GPO</span></span>


<span data-ttu-id="1f6bc-104">你可以标记组策略对象（GPO）的当前版本，以便在其历史记录中轻松识别。</span><span class="sxs-lookup"><span data-stu-id="1f6bc-104">You can label the current version of a Group Policy object (GPO) for easy identification in its history.</span></span> <span data-ttu-id="1f6bc-105">你可以使用标签来标识在出现问题时可以回退的已知正常版本。</span><span class="sxs-lookup"><span data-stu-id="1f6bc-105">You can use a label to identify a known good version to which you could roll back if a problem occurs.</span></span> <span data-ttu-id="1f6bc-106">此外，在一次为多个具有相同标签的 Gpo 添加标识时，你可以将应回滚到同一点的相关 Gpo 标记为在稍后需要回滚。</span><span class="sxs-lookup"><span data-stu-id="1f6bc-106">Also, by labeling multiple GPOs with the same label at one time, you can mark related GPOs that should be rolled back to the same point if rollback should later be necessary.</span></span>

<span data-ttu-id="1f6bc-107">必须具有编辑者、审批者或 AGPM 管理员（完全控制）角色的用户帐户或高级组策略管理中的必需权限才能完成此过程。</span><span class="sxs-lookup"><span data-stu-id="1f6bc-107">A user account with the Editor, Approver, or AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management is required to complete this procedure.</span></span> <span data-ttu-id="1f6bc-108">查看本主题中 "其他注意事项" 中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="1f6bc-108">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="1f6bc-109">在其历史记录中标记 Gpo 的当前版本</span><span class="sxs-lookup"><span data-stu-id="1f6bc-109">To label the current version of GPOs in their histories</span></span>**

1.  <span data-ttu-id="1f6bc-110">在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。</span><span class="sxs-lookup"><span data-stu-id="1f6bc-110">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="1f6bc-111">在 "**目录**" 选项卡上，单击 "**受控**" 选项卡以显示受控 gpo。</span><span class="sxs-lookup"><span data-stu-id="1f6bc-111">On the **Contents** tab, click the **Controlled** tab to display the controlled GPOs.</span></span>

3.  <span data-ttu-id="1f6bc-112">单击要为其标记当前版本的 GPO。</span><span class="sxs-lookup"><span data-stu-id="1f6bc-112">Click a GPO for which to label the current version.</span></span> <span data-ttu-id="1f6bc-113">若要选择多个 Gpo，请按 SHIFT 并单击一组连续 Gpo 中的最后一个 GPO，或者按 CTRL 并单击各个 Gpo。</span><span class="sxs-lookup"><span data-stu-id="1f6bc-113">To select multiple GPOs, press SHIFT and click the last GPO in a contiguous group of GPOs, or press CTRL and click individual GPOs.</span></span> <span data-ttu-id="1f6bc-114">右键单击所选的 GPO，然后单击 "**标签**"。</span><span class="sxs-lookup"><span data-stu-id="1f6bc-114">Right-click a selected GPO, and then click **Label**.</span></span>

4.  <span data-ttu-id="1f6bc-115">键入要在选定的每个 GPO 的历史记录中显示的标签和注释，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="1f6bc-115">Type a label and a comment to be displayed in the history of each GPO selected, and then click **OK**.</span></span>

5.  <span data-ttu-id="1f6bc-116">当**进度**窗口指示整个进度完成时，单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="1f6bc-116">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span>

### <span data-ttu-id="1f6bc-117">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="1f6bc-117">Additional considerations</span></span>

-   <span data-ttu-id="1f6bc-118">默认情况下，你必须是编辑者、审批者或 AGPM 管理员（完全控制）才能执行此过程。</span><span class="sxs-lookup"><span data-stu-id="1f6bc-118">By default, you must be an Editor, an Approver, or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="1f6bc-119">具体而言，您必须具有**列表内容**并**编辑设置**或为 gpo**部署 gpo**权限。</span><span class="sxs-lookup"><span data-stu-id="1f6bc-119">Specifically, you must have **List Contents** and either **Edit Settings** or **Deploy GPO** permissions for the GPO.</span></span>

### <span data-ttu-id="1f6bc-120">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="1f6bc-120">Additional references</span></span>

-   [<span data-ttu-id="1f6bc-121">编辑 GPO</span><span class="sxs-lookup"><span data-stu-id="1f6bc-121">Editing a GPO</span></span>](editing-a-gpo.md)

 

 





