---
title: 识别各 GPO、GPO 版本或模板之间的差异
description: 识别各 GPO、GPO 版本或模板之间的差异
author: dansimp
ms.assetid: 3f03c368-162b-450f-be6c-2807c3e8d741
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: bf5a7c71b431c787dcb2b16fe9a19f7ff9b06046
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802747"
---
# <span data-ttu-id="44368-103">识别各 GPO、GPO 版本或模板之间的差异</span><span class="sxs-lookup"><span data-stu-id="44368-103">Identify Differences Between GPOs, GPO Versions, or Templates</span></span>


<span data-ttu-id="44368-104">你可以生成基于 HTML 或基于 XML 的差异报表，以分析组策略对象（Gpo）、模板或 GPO 不同版本之间的差异。</span><span class="sxs-lookup"><span data-stu-id="44368-104">You can generate HTML-based or XML-based difference reports to analyze the differences between Group Policy Objects (GPOs), templates, or different versions of a GPO.</span></span>

<span data-ttu-id="44368-105">需要具有 "审阅者"、"编辑"、"审批者" 或 "AGPM 管理员（完全控制）" 角色或 "高级组策略管理" （AGPM）中的必要权限才能完成此过程的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="44368-105">A user account with the Reviewer, Editor, Approver, or AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management (AGPM)is required to complete this procedure.</span></span> <span data-ttu-id="44368-106">查看本主题中 "其他注意事项" 中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="44368-106">Review the details in "Additional considerations" in this topic.</span></span>

## <span data-ttu-id="44368-107">确定 Gpo、GPO 版本或模板之间的差异</span><span class="sxs-lookup"><span data-stu-id="44368-107">Identifying differences between GPOs, GPO versions, or templates</span></span>


-   [<span data-ttu-id="44368-108">在两个 Gpo 或模板之间</span><span class="sxs-lookup"><span data-stu-id="44368-108">Between two GPOs or templates</span></span>](#bkmk-two-gpos)

-   [<span data-ttu-id="44368-109">在 GPO 和模板之间</span><span class="sxs-lookup"><span data-stu-id="44368-109">Between a GPO and a template</span></span>](#bkmk-gpo-and-template)

-   [<span data-ttu-id="44368-110">一个 GPO 的两个版本之间</span><span class="sxs-lookup"><span data-stu-id="44368-110">Between two versions of one GPO</span></span>](#bkmk-two-versions)

-   [<span data-ttu-id="44368-111">GPO 版本和模板之间</span><span class="sxs-lookup"><span data-stu-id="44368-111">Between a GPO version and a template</span></span>](#bkmk-gpo-version-and-template)

## <a href="" id="bkmk-two-gpos"></a>


**<span data-ttu-id="44368-112">确定两个 Gpo 或模板之间的差异</span><span class="sxs-lookup"><span data-stu-id="44368-112">To identify differences between two GPOs or templates</span></span>**

1.  <span data-ttu-id="44368-113">在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。</span><span class="sxs-lookup"><span data-stu-id="44368-113">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="44368-114">在 "详细信息" 窗格中的 "**目录**" 选项卡上，单击选项卡以显示 gpo （如果比较两个模板，则是模板）。</span><span class="sxs-lookup"><span data-stu-id="44368-114">On the **Contents** tab in the details pane, click a tab to display GPOs (or templates, if comparing two templates).</span></span>

3.  <span data-ttu-id="44368-115">选择两个 Gpo 或模板。</span><span class="sxs-lookup"><span data-stu-id="44368-115">Select the two GPOs or templates.</span></span>

4.  <span data-ttu-id="44368-116">右键单击其中一个 Gpo 或模板，单击 "**差异**"，然后单击 " **HTML 报表**" 或 " **XML 报表**" 以显示汇总 gpo 或模板设置的差异报表。</span><span class="sxs-lookup"><span data-stu-id="44368-116">Right-click one of the GPOs or templates, click **Differences**, and then click **HTML Report** or **XML Report** to display a difference report summarizing the settings of the GPOs or templates.</span></span>

### <a href="" id="bkmk-gpo-and-template"></a>

**<span data-ttu-id="44368-117">确定 GPO 和模板之间的差异</span><span class="sxs-lookup"><span data-stu-id="44368-117">To identify differences between a GPO and a template</span></span>**

1.  <span data-ttu-id="44368-118">在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。</span><span class="sxs-lookup"><span data-stu-id="44368-118">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="44368-119">在 "详细信息" 窗格中的 "**目录**" 选项卡上，单击选项卡以显示 gpo （如果比较两个模板，则是模板）。</span><span class="sxs-lookup"><span data-stu-id="44368-119">On the **Contents** tab in the details pane, click a tab to display GPOs (or templates, if comparing two templates).</span></span>

3.  <span data-ttu-id="44368-120">右键单击该 GPO，单击 "**差异**"，然后单击 "**模板**"。</span><span class="sxs-lookup"><span data-stu-id="44368-120">Right-click the GPO, click **Differences**, and then click **Template**.</span></span>

4.  <span data-ttu-id="44368-121">选择模板和报告类型，然后单击 **"确定"** 以显示对 GPO 和模板设置进行汇总的差异报告。</span><span class="sxs-lookup"><span data-stu-id="44368-121">Select the template and type of report, and then click **OK** to display a difference report summarizing the settings of the GPO and template.</span></span>

### <a href="" id="bkmk-two-versions"></a>

**<span data-ttu-id="44368-122">确定一个 GPO 的两个版本之间的差异</span><span class="sxs-lookup"><span data-stu-id="44368-122">To identify differences between two versions of one GPO</span></span>**

1.  <span data-ttu-id="44368-123">在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。</span><span class="sxs-lookup"><span data-stu-id="44368-123">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="44368-124">在 "详细信息" 窗格中的 "**目录**" 选项卡上，单击选项卡以显示 gpo （如果比较两个模板，则是模板）。</span><span class="sxs-lookup"><span data-stu-id="44368-124">On the **Contents** tab in the details pane, click a tab to display GPOs (or templates, if comparing two templates).</span></span>

3.  <span data-ttu-id="44368-125">双击该 GPO 以显示其历史记录，然后突出显示要比较的版本。</span><span class="sxs-lookup"><span data-stu-id="44368-125">Double-click the GPO to display its history, and then highlight the versions to be compared.</span></span>

4.  <span data-ttu-id="44368-126">右键单击其中一个版本，单击 "**差异**"，然后单击 " **HTML 报表**" 或 " **XML 报表**" 以显示汇总 gpo 设置的差异报表。</span><span class="sxs-lookup"><span data-stu-id="44368-126">Right-click one of the versions, click **Differences**, and then click **HTML Report** or **XML Report** to display a difference report summarizing the settings of the GPOs.</span></span>

### <a href="" id="bkmk-gpo-version-and-template"></a>

**<span data-ttu-id="44368-127">确定 GPO 版本和模板之间的差异</span><span class="sxs-lookup"><span data-stu-id="44368-127">To identify differences between a GPO version and a template</span></span>**

1.  <span data-ttu-id="44368-128">在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。</span><span class="sxs-lookup"><span data-stu-id="44368-128">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="44368-129">在 "详细信息" 窗格中的 "**目录**" 选项卡上，单击选项卡以显示 gpo （如果比较两个模板，则是模板）。</span><span class="sxs-lookup"><span data-stu-id="44368-129">On the **Contents** tab in the details pane, click a tab to display GPOs (or templates, if comparing two templates).</span></span>

3.  <span data-ttu-id="44368-130">双击该 GPO 以显示其历史记录。</span><span class="sxs-lookup"><span data-stu-id="44368-130">Double-click the GPO to display its history.</span></span>

4.  <span data-ttu-id="44368-131">右键单击感兴趣的 GPO 版本，单击 "**差异**"，然后单击 "**模板**"。</span><span class="sxs-lookup"><span data-stu-id="44368-131">Right-click the GPO version of interest, click **Differences**, and then click **Template**.</span></span>

5.  <span data-ttu-id="44368-132">选择模板和报告类型，然后单击 **"确定"** 以显示对 GPO 版本和模板设置进行汇总的差异报告。</span><span class="sxs-lookup"><span data-stu-id="44368-132">Select the template and type of report, and then click **OK** to display a difference report summarizing the settings of the GPO version and template.</span></span>

## <span data-ttu-id="44368-133">差异报告的关键</span><span class="sxs-lookup"><span data-stu-id="44368-133">Key to difference reports</span></span>


<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="44368-134">符号</span><span class="sxs-lookup"><span data-stu-id="44368-134">Symbol</span></span></th>
<th align="left"><span data-ttu-id="44368-135">含义</span><span class="sxs-lookup"><span data-stu-id="44368-135">Meaning</span></span></th>
<th align="left"><span data-ttu-id="44368-136">颜色</span><span class="sxs-lookup"><span data-stu-id="44368-136">Color</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="44368-137">无</span><span class="sxs-lookup"><span data-stu-id="44368-137">None</span></span></p></td>
<td align="left"><p><span data-ttu-id="44368-138">具有两个 Gpo 中的相同设置的项目存在</span><span class="sxs-lookup"><span data-stu-id="44368-138">Item exists with identical settings in both GPOs</span></span></p></td>
<td align="left"><p><span data-ttu-id="44368-139">级别不同</span><span class="sxs-lookup"><span data-stu-id="44368-139">Varies with level</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="44368-140">[#]</span><span class="sxs-lookup"><span data-stu-id="44368-140">[#]</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="44368-141">项目存在于两个 Gpo 中，但具有更改后的设置</span><span class="sxs-lookup"><span data-stu-id="44368-141">Item exists in both GPOs, but with changed settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="44368-142">淡蓝</span><span class="sxs-lookup"><span data-stu-id="44368-142">Blue</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="44368-143">[-]</span><span class="sxs-lookup"><span data-stu-id="44368-143">[-]</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="44368-144">项目仅存在于第一个 GPO 中</span><span class="sxs-lookup"><span data-stu-id="44368-144">Item exists only in the first GPO</span></span></p></td>
<td align="left"><p><span data-ttu-id="44368-145">红色</span><span class="sxs-lookup"><span data-stu-id="44368-145">Red</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="44368-146">[+]</span><span class="sxs-lookup"><span data-stu-id="44368-146">[+]</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="44368-147">项目仅存在于第二个 GPO 中</span><span class="sxs-lookup"><span data-stu-id="44368-147">Item exists only in the second GPO</span></span></p></td>
<td align="left"><p><span data-ttu-id="44368-148">绿色</span><span class="sxs-lookup"><span data-stu-id="44368-148">Green</span></span></p></td>
</tr>
</tbody>
</table>

 

-   <span data-ttu-id="44368-149">对于具有已更改设置的项目，已更改的设置将在项目展开时标识。</span><span class="sxs-lookup"><span data-stu-id="44368-149">For items with changed settings, the changed settings are identified when the item is expanded.</span></span> <span data-ttu-id="44368-150">每个 GPO 中属性的值的显示顺序与在报表中显示 Gpo 的顺序相同。</span><span class="sxs-lookup"><span data-stu-id="44368-150">The value for the attribute in each GPO is displayed in the same order that the GPOs are displayed in the report.</span></span>

-   <span data-ttu-id="44368-151">对设置所做的一些更改可能会导致将某项报告为两个不同的项目（仅在第一个 GPO 中出现，一个仅在第二个 GPO 中出现），而不是一个已更改的项目。</span><span class="sxs-lookup"><span data-stu-id="44368-151">Some changes to settings may cause an item to be reported as two different items (one present only in the first GPO, one present only in the second) rather than as one item that has changed.</span></span>

### <span data-ttu-id="44368-152">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="44368-152">Additional considerations</span></span>

-   <span data-ttu-id="44368-153">默认情况下，你必须是审阅者、编辑者、审批者或 AGPM 管理员（完全控制）才能执行此过程。</span><span class="sxs-lookup"><span data-stu-id="44368-153">By default, you must be a Reviewer, an Editor, an Approver, or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="44368-154">具体而言，您必须具有该 GPO 的 "**列表内容**" 和 "**读取设置**" 权限。</span><span class="sxs-lookup"><span data-stu-id="44368-154">Specifically, you must have **List Contents** and **Read Settings** permissions for the GPO.</span></span> <span data-ttu-id="44368-155">此外，若要显示 Gpo 的列表，您必须拥有该域的 "**列表内容**" 权限。</span><span class="sxs-lookup"><span data-stu-id="44368-155">Also, to display the list of GPOs, you must have **List Contents** permission for the domain.</span></span>

### <span data-ttu-id="44368-156">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="44368-156">Additional references</span></span>

-   [<span data-ttu-id="44368-157">执行审阅者任务</span><span class="sxs-lookup"><span data-stu-id="44368-157">Performing Reviewer Tasks</span></span>](performing-reviewer-tasks-agpm40.md)

 

 





