---
title: “历史记录”窗口
description: “历史记录”窗口
author: dansimp
ms.assetid: 5bea62e7-d267-40b2-a66d-fb1be7373a1c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 81f19e3834e945a45238856e23f6ee4a86407c4a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802759"
---
# <span data-ttu-id="3f62a-103">“历史记录”窗口</span><span class="sxs-lookup"><span data-stu-id="3f62a-103">History Window</span></span>


<span data-ttu-id="3f62a-104">通过双击 GPO 或右键单击 GPO，然后单击 "**历史记录**"，可以显示组策略对象（GPO）的历史记录。</span><span class="sxs-lookup"><span data-stu-id="3f62a-104">The history of a Group Policy Object (GPO) can be displayed by double-clicking a GPO or by right-clicking a GPO and then clicking **History**.</span></span> <span data-ttu-id="3f62a-105">它还显示在组策略管理控制台（GPMC）中，作为每个 GPO 的选项卡。</span><span class="sxs-lookup"><span data-stu-id="3f62a-105">It is also displayed in the Group Policy Management Console (GPMC) as a tab for each GPO.</span></span>

<span data-ttu-id="3f62a-106">历史记录在所选 GPO 的生命周期内提供事件记录。</span><span class="sxs-lookup"><span data-stu-id="3f62a-106">The history provides a record of events in the lifetime of the selected GPO.</span></span> <span data-ttu-id="3f62a-107">在 "**历史记录**" 窗口中，你可以获取 gpo 版本中的设置的报告，比较 gpo 的多个版本，或者回滚到 gpo 的早期版本。</span><span class="sxs-lookup"><span data-stu-id="3f62a-107">From the **History** window, you can obtain a report of the settings in a version of the GPO, compare multiple versions of a GPO, or roll back to an earlier version of a GPO.</span></span>

## <span data-ttu-id="3f62a-108">在 "历史记录" 窗口中筛选事件</span><span class="sxs-lookup"><span data-stu-id="3f62a-108">Filtering events in the History window</span></span>


<span data-ttu-id="3f62a-109">"**历史记录**" 窗口中的选项卡将筛选 GPO 历史记录中的状态。</span><span class="sxs-lookup"><span data-stu-id="3f62a-109">The tabs within the **History** window filter the states in the history of the GPO.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="3f62a-110">Tabs</span><span class="sxs-lookup"><span data-stu-id="3f62a-110">Tabs</span></span></th>
<th align="left"><span data-ttu-id="3f62a-111">筛选</span><span class="sxs-lookup"><span data-stu-id="3f62a-111">Filtering</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="3f62a-112">所有状态</span><span class="sxs-lookup"><span data-stu-id="3f62a-112">All States</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="3f62a-113">显示 GPO 历史记录中的所有状态。</span><span class="sxs-lookup"><span data-stu-id="3f62a-113">Display all states in the history of the GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="3f62a-114">唯一版本</span><span class="sxs-lookup"><span data-stu-id="3f62a-114">Unique Versions</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="3f62a-115">仅显示已签入存档的 GPO 的唯一版本。</span><span class="sxs-lookup"><span data-stu-id="3f62a-115">Display only unique versions of the GPO checked into the archive.</span></span> <span data-ttu-id="3f62a-116">此列表中省略了部署到生产环境的版本、指向唯一版本的快捷方式和信息状态。</span><span class="sxs-lookup"><span data-stu-id="3f62a-116">The version deployed to the production environment, shortcuts to unique versions, and informational states are omitted from this list.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="3f62a-117">事件信息</span><span class="sxs-lookup"><span data-stu-id="3f62a-117">Event information</span></span>


<span data-ttu-id="3f62a-118">为 GPO 历史记录中的每个状态提供了信息。</span><span class="sxs-lookup"><span data-stu-id="3f62a-118">Information is provided for each state in the history of the GPO.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="3f62a-119">GPO 属性</span><span class="sxs-lookup"><span data-stu-id="3f62a-119">GPO attribute</span></span></th>
<th align="left"><span data-ttu-id="3f62a-120">描述</span><span class="sxs-lookup"><span data-stu-id="3f62a-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="3f62a-121">更改日期</span><span class="sxs-lookup"><span data-stu-id="3f62a-121">Change Date</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="3f62a-122">在 "状态" 列中执行操作的时间戳 <strong> </strong> 。</span><span class="sxs-lookup"><span data-stu-id="3f62a-122">Time stamp of when the action in the <strong>State</strong> column was performed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="3f62a-123">State</span><span class="sxs-lookup"><span data-stu-id="3f62a-123">State</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="3f62a-124">GPO 历史记录中的状态。</span><span class="sxs-lookup"><span data-stu-id="3f62a-124">A state in the history of the GPO.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="3f62a-125">更改者</span><span class="sxs-lookup"><span data-stu-id="3f62a-125">Changed By</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="3f62a-126">已签入或已部署 GPO 的人员。</span><span class="sxs-lookup"><span data-stu-id="3f62a-126">The person who checked in or deployed the GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="3f62a-127">评论</span><span class="sxs-lookup"><span data-stu-id="3f62a-127">Comment</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="3f62a-128">在此版本发生更改时由签入或部署 GPO 的人员输入的注释，用于识别版本的细节，以防需要回滚到早期版本。</span><span class="sxs-lookup"><span data-stu-id="3f62a-128">A comment entered by the person who checked in or deployed a GPO at the time that this version was changed, useful for identifying the specifics of the version in case of the need to roll back to an earlier version.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="3f62a-129">已</span><span class="sxs-lookup"><span data-stu-id="3f62a-129">Deletable</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="3f62a-130">如果存档中保留的每个 GPO 的唯一版本数受到限制，是否可以删除此 GPO 版本。</span><span class="sxs-lookup"><span data-stu-id="3f62a-130">Whether this version of the GPO can be deleted if the number of unique versions of each GPO retained in the archive is limited.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="3f62a-131">注意</span><span class="sxs-lookup"><span data-stu-id="3f62a-131">Note</span></span></strong><br/><p><span data-ttu-id="3f62a-132">你可以通过右键单击 GPO，然后单击 "不 <strong> 允许删除" </strong> 或 " <strong> 允许删除" 来更改 gpo 的版本是否可以删除 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="3f62a-132">You can change whether a version of a GPO can be deleted by right-clicking the GPO and then clicking <strong>Do Not Allow Deletion</strong> or <strong>Allow Deletion</strong>.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="3f62a-133">计算机版本</span><span class="sxs-lookup"><span data-stu-id="3f62a-133">Computer Version</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="3f62a-134">GPO 的 "计算机配置" 部分的自动生成的版本。</span><span class="sxs-lookup"><span data-stu-id="3f62a-134">Automatically generated version of the Computer Configuration part of the GPO.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="3f62a-135">用户版本</span><span class="sxs-lookup"><span data-stu-id="3f62a-135">User Version</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="3f62a-136">GPO 的用户配置部分的自动生成的版本。</span><span class="sxs-lookup"><span data-stu-id="3f62a-136">Automatically generated version of the User Configuration part of the GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="3f62a-137">GPO 状态</span><span class="sxs-lookup"><span data-stu-id="3f62a-137">GPO Status</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="3f62a-138">计算机配置和用户配置可以彼此分开管理。</span><span class="sxs-lookup"><span data-stu-id="3f62a-138">The Computer Configuration and the User Configuration can be managed separately from each other.</span></span> <span data-ttu-id="3f62a-139">此状态显示启用了 GPO 的哪些部分。</span><span class="sxs-lookup"><span data-stu-id="3f62a-139">This status shows which portions of the GPO are enabled.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="3f62a-140">源 GPO 信息</span><span class="sxs-lookup"><span data-stu-id="3f62a-140">Source GPO Information</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="3f62a-141">对于从另一个目录林中导入的 GPO，原始 GPO 名称、域和用户以及与上次更改相关联的日期。</span><span class="sxs-lookup"><span data-stu-id="3f62a-141">For a GPO that has been imported from another forest, the original GPO name, domain, and user and date associated with the last change.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="3f62a-142">报告</span><span class="sxs-lookup"><span data-stu-id="3f62a-142">Reports</span></span>


<span data-ttu-id="3f62a-143">"**设置**和**差异**" 按钮显示有关所选 gpo 版本或版本的 gpo 设置的报告。</span><span class="sxs-lookup"><span data-stu-id="3f62a-143">The **Settings** and **Differences** buttons display reports about GPO settings for the GPO version or versions selected.</span></span> <span data-ttu-id="3f62a-144">此外，右键单击 GPO 版本或版本可提供用于显示基于 XML 的报表的选项。</span><span class="sxs-lookup"><span data-stu-id="3f62a-144">Also, right-clicking a GPO version or versions provides the option to display XML-based reports.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="3f62a-145">按钮</span><span class="sxs-lookup"><span data-stu-id="3f62a-145">Button</span></span></th>
<th align="left"><span data-ttu-id="3f62a-146">作用</span><span class="sxs-lookup"><span data-stu-id="3f62a-146">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="3f62a-147">设置</span><span class="sxs-lookup"><span data-stu-id="3f62a-147">Settings</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="3f62a-148">生成基于 HTML 的报表，显示所选版本的 GPO 中的设置。</span><span class="sxs-lookup"><span data-stu-id="3f62a-148">Generate an HTML-based report displaying the settings within the selected version of the GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="3f62a-149">不同之处</span><span class="sxs-lookup"><span data-stu-id="3f62a-149">Differences</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="3f62a-150">生成用于比较 GPO 的多个选定版本内的设置的基于 HTML 的报表。</span><span class="sxs-lookup"><span data-stu-id="3f62a-150">Generate an HTML-based report comparing the settings within multiple selected versions of the GPO.</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="3f62a-151">差异报告的关键</span><span class="sxs-lookup"><span data-stu-id="3f62a-151">Key to difference reports</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="3f62a-152">符号</span><span class="sxs-lookup"><span data-stu-id="3f62a-152">Symbol</span></span></th>
<th align="left"><span data-ttu-id="3f62a-153">含义</span><span class="sxs-lookup"><span data-stu-id="3f62a-153">Meaning</span></span></th>
<th align="left"><span data-ttu-id="3f62a-154">颜色</span><span class="sxs-lookup"><span data-stu-id="3f62a-154">Color</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3f62a-155">无</span><span class="sxs-lookup"><span data-stu-id="3f62a-155">None</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f62a-156">具有两个 Gpo 中的相同设置的项目存在</span><span class="sxs-lookup"><span data-stu-id="3f62a-156">Item exists with identical settings in both GPOs</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f62a-157">级别不同</span><span class="sxs-lookup"><span data-stu-id="3f62a-157">Varies with level</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="3f62a-158">[#]</span><span class="sxs-lookup"><span data-stu-id="3f62a-158">[#]</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="3f62a-159">项目存在于两个 Gpo 中，但具有更改后的设置</span><span class="sxs-lookup"><span data-stu-id="3f62a-159">Item exists in both GPOs, but with changed settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f62a-160">淡蓝</span><span class="sxs-lookup"><span data-stu-id="3f62a-160">Blue</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="3f62a-161">[-]</span><span class="sxs-lookup"><span data-stu-id="3f62a-161">[-]</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="3f62a-162">项目仅存在于第一个 GPO 中</span><span class="sxs-lookup"><span data-stu-id="3f62a-162">Item exists only in the first GPO</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f62a-163">红色</span><span class="sxs-lookup"><span data-stu-id="3f62a-163">Red</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="3f62a-164">[+]</span><span class="sxs-lookup"><span data-stu-id="3f62a-164">[+]</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="3f62a-165">项目仅存在于第二个 GPO 中</span><span class="sxs-lookup"><span data-stu-id="3f62a-165">Item exists only in the second GPO</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f62a-166">绿色</span><span class="sxs-lookup"><span data-stu-id="3f62a-166">Green</span></span></p></td>
</tr>
</tbody>
</table>



-   <span data-ttu-id="3f62a-167">对于具有已更改设置的项目，已更改的设置将在项目展开时标识。</span><span class="sxs-lookup"><span data-stu-id="3f62a-167">For items with changed settings, the changed settings are identified when the item is expanded.</span></span> <span data-ttu-id="3f62a-168">每个 GPO 中属性的值的显示顺序与在报表中显示 Gpo 的顺序相同。</span><span class="sxs-lookup"><span data-stu-id="3f62a-168">The value for the attribute in each GPO is displayed in the same order that the GPOs are displayed in the report.</span></span>

-   <span data-ttu-id="3f62a-169">对设置所做的一些更改可能会导致将某项报告为两个项目（仅在第一个 GPO 中显示，另一个仅在第二个 GPO 中出现），而不是更改的一个项目。</span><span class="sxs-lookup"><span data-stu-id="3f62a-169">Some changes to settings may cause an item to be reported as two items (one present only in the first GPO, one present only in the second), instead of one item that has changed.</span></span>

### <span data-ttu-id="3f62a-170">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="3f62a-170">Additional references</span></span>

-   [<span data-ttu-id="3f62a-171">“内容”选项卡</span><span class="sxs-lookup"><span data-stu-id="3f62a-171">Contents Tab</span></span>](contents-tab-agpm40.md)









