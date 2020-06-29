---
title: 查看 GPO 链接
description: 查看 GPO 链接
author: dansimp
ms.assetid: 5ae95afc-2b89-45cf-916c-efe2d43b2211
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6532a669c6841c2342514c0911f74bc0b1fbc86d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801784"
---
# <span data-ttu-id="79e1c-103">查看 GPO 链接</span><span class="sxs-lookup"><span data-stu-id="79e1c-103">Review GPO Links</span></span>


<span data-ttu-id="79e1c-104">你可以显示一个图表，显示你选择的组策略对象（GPO）或 Gpo 链接到组织单位的位置。</span><span class="sxs-lookup"><span data-stu-id="79e1c-104">You can display a diagram showing where a Group Policy Object (GPO) or GPOs that you select are linked to organizational units.</span></span> <span data-ttu-id="79e1c-105">每次控制、导入或签入 GPO 时，GPO 链接图都会更新。</span><span class="sxs-lookup"><span data-stu-id="79e1c-105">GPO link diagrams are updated each time the GPO is controlled, imported, or checked in.</span></span>

<span data-ttu-id="79e1c-106">需要具有 "审阅者"、"编辑"、"审批者" 或 "AGPM 管理员（完全控制）" 角色或 "高级组策略管理" （AGPM）中的必要权限才能完成此过程的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="79e1c-106">A user account with the Reviewer, Editor, Approver, or AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management (AGPM)is required to complete this procedure.</span></span> <span data-ttu-id="79e1c-107">查看本主题中 "其他注意事项" 中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="79e1c-107">Review the details in "Additional considerations" in this topic.</span></span>

## <span data-ttu-id="79e1c-108">查看 GPO 链接</span><span class="sxs-lookup"><span data-stu-id="79e1c-108">Reviewing GPO links</span></span>


-   [<span data-ttu-id="79e1c-109">对于一个或多个 Gpo</span><span class="sxs-lookup"><span data-stu-id="79e1c-109">For one or more GPOs</span></span>](#bkmk-gpos)

-   [<span data-ttu-id="79e1c-110">对于一个或多个 GPO 版本</span><span class="sxs-lookup"><span data-stu-id="79e1c-110">For one or more versions of a GPO</span></span>](#bkmk-gpo-versions)

### <a href="" id="bkmk-gpos"></a>

**<span data-ttu-id="79e1c-111">显示一个或多个 Gpo 的 GPO 链接</span><span class="sxs-lookup"><span data-stu-id="79e1c-111">To display GPO links for one or more GPOs</span></span>**

1.  <span data-ttu-id="79e1c-112">在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。</span><span class="sxs-lookup"><span data-stu-id="79e1c-112">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="79e1c-113">在 "详细信息" 窗格中的 "**目录**" 选项卡上，单击 "**受控**"、"**挂起**" 或 "**回收站**" 选项卡以显示 gpo。</span><span class="sxs-lookup"><span data-stu-id="79e1c-113">On the **Contents** tab in the details pane, click the **Controlled**, **Pending**, or **Recycle Bin** tab to display GPOs.</span></span>

3.  <span data-ttu-id="79e1c-114">选择要为其显示链接的一个或多个 Gpo，右键单击所选 GPO，单击 "**设置**"，然后单击 " **GPO 链接**" 以显示包含指向所选 gpo 的链接的域和组织单位的图表。</span><span class="sxs-lookup"><span data-stu-id="79e1c-114">Select one or more GPOs for which to display links, right-click a selected GPO, click **Settings**, and then click **GPO Links** to display a diagram of domains and organizational units with links to the selected GPO(s).</span></span>

### <a href="" id="bkmk-gpo-versions"></a>

**<span data-ttu-id="79e1c-115">显示 GPO 的一个或多个版本的 GPO 链接</span><span class="sxs-lookup"><span data-stu-id="79e1c-115">To display GPO links for one or more versions of a GPO</span></span>**

1.  <span data-ttu-id="79e1c-116">在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。</span><span class="sxs-lookup"><span data-stu-id="79e1c-116">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="79e1c-117">在 "详细信息" 窗格中的 "**目录**" 选项卡上，单击 "**受控**" 或 "**回收站**" 选项卡以显示 gpo。</span><span class="sxs-lookup"><span data-stu-id="79e1c-117">On the **Contents** tab in the details pane, click the **Controlled** or **Recycle Bin** tab to display GPOs.</span></span>

3.  <span data-ttu-id="79e1c-118">双击该 GPO 以显示其历史记录。</span><span class="sxs-lookup"><span data-stu-id="79e1c-118">Double-click the GPO to display its history.</span></span>

4.  <span data-ttu-id="79e1c-119">右键单击要查看其设置的 GPO 版本，单击 "**设置**"，然后单击 " **HTML 报表**" 或 " **XML 报表**" 以显示 GPO 设置的摘要。</span><span class="sxs-lookup"><span data-stu-id="79e1c-119">Right-click the GPO version for which to review the settings, click **Settings**, and then click **HTML Report** or **XML Report** to display a summary of the GPO's settings.</span></span>

### <span data-ttu-id="79e1c-120">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="79e1c-120">Additional considerations</span></span>

-   <span data-ttu-id="79e1c-121">默认情况下，你必须是审阅者、编辑者、审批者或 AGPM 管理员（完全控制）才能执行此过程。</span><span class="sxs-lookup"><span data-stu-id="79e1c-121">By default, you must be a Reviewer, an Editor, an Approver, or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="79e1c-122">具体而言，您必须具有该 GPO 的 "**列表内容**" 和 "**读取设置**" 权限。</span><span class="sxs-lookup"><span data-stu-id="79e1c-122">Specifically, you must have **List Contents** and **Read Settings** permissions for the GPO.</span></span> <span data-ttu-id="79e1c-123">此外，若要显示 Gpo 的列表，您必须拥有该域的 "**列表内容**" 权限。</span><span class="sxs-lookup"><span data-stu-id="79e1c-123">Also, to display the list of GPOs, you must have **List Contents** permission for the domain.</span></span>

### <span data-ttu-id="79e1c-124">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="79e1c-124">Additional references</span></span>

-   [<span data-ttu-id="79e1c-125">执行审阅者任务</span><span class="sxs-lookup"><span data-stu-id="79e1c-125">Performing Reviewer Tasks</span></span>](performing-reviewer-tasks-agpm30ops.md)

 

 





