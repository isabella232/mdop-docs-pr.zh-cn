---
title: “历史记录”窗口
description: “历史记录”窗口
author: dansimp
ms.assetid: 114f50a4-508d-4589-b006-6cd05cffe6b7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 81911b5103c76e267d806fb7cd8acf55811440c9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802760"
---
# <span data-ttu-id="451fa-103">“历史记录”窗口</span><span class="sxs-lookup"><span data-stu-id="451fa-103">History Window</span></span>


<span data-ttu-id="451fa-104">通过双击 GPO 或右键单击 GPO，然后单击 "**历史记录**"，可以显示组策略对象（GPO）的历史记录。</span><span class="sxs-lookup"><span data-stu-id="451fa-104">The history of a Group Policy Object (GPO) can be displayed by double-clicking a GPO or by right-clicking a GPO and then clicking **History**.</span></span> <span data-ttu-id="451fa-105">它还显示在**组策略管理控制台**（GPMC）中，作为每个 GPO 的选项卡。</span><span class="sxs-lookup"><span data-stu-id="451fa-105">It is also displayed in the **Group Policy Management Console** (GPMC) as a tab for each GPO.</span></span>

<span data-ttu-id="451fa-106">历史记录在所选 GPO 的生命周期内提供事件记录。</span><span class="sxs-lookup"><span data-stu-id="451fa-106">The history provides a record of events in the lifetime of the selected GPO.</span></span> <span data-ttu-id="451fa-107">在 "**历史记录**" 窗口中，你可以获取 gpo 版本中的设置的报告，比较 gpo 的多个版本，或者回滚到 gpo 的以前版本。</span><span class="sxs-lookup"><span data-stu-id="451fa-107">From the **History** window, you can obtain a report of the settings within a version of the GPO, compare multiple versions of a GPO, or roll back to a previous version of a GPO.</span></span>

## <span data-ttu-id="451fa-108">在 "历史记录" 窗口中筛选事件</span><span class="sxs-lookup"><span data-stu-id="451fa-108">Filtering events in the History window</span></span>


<span data-ttu-id="451fa-109">"**历史记录**" 窗口中的选项卡将筛选 GPO 历史记录中的状态。</span><span class="sxs-lookup"><span data-stu-id="451fa-109">The tabs within the **History** window filter the states in the history of the GPO.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="451fa-110">Tabs</span><span class="sxs-lookup"><span data-stu-id="451fa-110">Tabs</span></span></th>
<th align="left"><span data-ttu-id="451fa-111">筛选</span><span class="sxs-lookup"><span data-stu-id="451fa-111">Filtering</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="451fa-112">所有状态</span><span class="sxs-lookup"><span data-stu-id="451fa-112">All States</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="451fa-113">显示 GPO 历史记录中的所有状态。</span><span class="sxs-lookup"><span data-stu-id="451fa-113">Display all states in the history of the GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="451fa-114">唯一版本</span><span class="sxs-lookup"><span data-stu-id="451fa-114">Unique Versions</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="451fa-115">仅显示已签入存档的 GPO 的唯一版本。</span><span class="sxs-lookup"><span data-stu-id="451fa-115">Display only unique versions of the GPO checked into the archive.</span></span> <span data-ttu-id="451fa-116">此列表中省略了部署到生产环境的版本、指向唯一版本的快捷方式和信息状态。</span><span class="sxs-lookup"><span data-stu-id="451fa-116">The version deployed to the production environment, shortcuts to unique versions, and informational states are omitted from this list.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="451fa-117">事件信息</span><span class="sxs-lookup"><span data-stu-id="451fa-117">Event information</span></span>


<span data-ttu-id="451fa-118">为 GPO 历史记录中的每个状态提供了信息。</span><span class="sxs-lookup"><span data-stu-id="451fa-118">Information is provided for each state in the history of the GPO.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="451fa-119">GPO 属性</span><span class="sxs-lookup"><span data-stu-id="451fa-119">GPO attribute</span></span></th>
<th align="left"><span data-ttu-id="451fa-120">描述</span><span class="sxs-lookup"><span data-stu-id="451fa-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="451fa-121">更改日期</span><span class="sxs-lookup"><span data-stu-id="451fa-121">Change Date</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="451fa-122">在 "状态" 列中执行操作的时间戳 <strong> </strong> 。</span><span class="sxs-lookup"><span data-stu-id="451fa-122">Time stamp of when the action in the <strong>State</strong> column was performed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="451fa-123">State</span><span class="sxs-lookup"><span data-stu-id="451fa-123">State</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="451fa-124">GPO 历史记录中的状态。</span><span class="sxs-lookup"><span data-stu-id="451fa-124">A state in the history of the GPO.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="451fa-125">更改者</span><span class="sxs-lookup"><span data-stu-id="451fa-125">Changed By</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="451fa-126">已签入或已部署 GPO 的人员。</span><span class="sxs-lookup"><span data-stu-id="451fa-126">The person who checked in or deployed the GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="451fa-127">评论</span><span class="sxs-lookup"><span data-stu-id="451fa-127">Comment</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="451fa-128">在修改此版本时由签入或部署 GPO 的人员输入的注释。</span><span class="sxs-lookup"><span data-stu-id="451fa-128">A comment entered by the person who checked in or deployed a GPO at the time that this version was modified.</span></span> <span data-ttu-id="451fa-129">在需要回滚到以前版本的情况下，用于识别版本的详细信息。</span><span class="sxs-lookup"><span data-stu-id="451fa-129">Useful for identifying the specifics of the version in case of the need to roll back to a previous version.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="451fa-130">已</span><span class="sxs-lookup"><span data-stu-id="451fa-130">Deletable</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="451fa-131">如果存档中保留的每个 GPO 的唯一版本数受到限制，是否可以删除此 GPO 版本。</span><span class="sxs-lookup"><span data-stu-id="451fa-131">Whether this version of the GPO can be deleted if the number of unique versions of each GPO retained in the archive is limited.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="451fa-132">注意</span><span class="sxs-lookup"><span data-stu-id="451fa-132">Note</span></span></strong><br/><p><span data-ttu-id="451fa-133">通过右键单击 GPO 的版本，然后单击 "不允许删除" 或 "允许删除"，可以修改该 GPO 的版本是否可 <strong> </strong> <strong> 删除 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="451fa-133">You can modify whether a version of a GPO is deletable by right-clicking it and then clicking <strong>Do Not Allow Deletion</strong> or <strong>Allow Deletion</strong>.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="451fa-134">计算机版本</span><span class="sxs-lookup"><span data-stu-id="451fa-134">Computer Version</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="451fa-135">GPO 的计算机配置部分的自动生成的版本。</span><span class="sxs-lookup"><span data-stu-id="451fa-135">Automatically generated version of the Computer Configuration portion of the GPO.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="451fa-136">用户版本</span><span class="sxs-lookup"><span data-stu-id="451fa-136">User Version</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="451fa-137">GPO 的用户配置部分的自动生成的版本。</span><span class="sxs-lookup"><span data-stu-id="451fa-137">Automatically generated version of the User Configuration portion of the GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="451fa-138">GPO 状态</span><span class="sxs-lookup"><span data-stu-id="451fa-138">GPO Status</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="451fa-139">计算机配置和用户配置可以彼此分开管理。</span><span class="sxs-lookup"><span data-stu-id="451fa-139">The Computer Configuration and the User Configuration can be managed separately from each other.</span></span> <span data-ttu-id="451fa-140">此状态显示启用了 GPO 的哪些部分。</span><span class="sxs-lookup"><span data-stu-id="451fa-140">This status shows which portions of the GPO are enabled.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="451fa-141">WMI 筛选器</span><span class="sxs-lookup"><span data-stu-id="451fa-141">WMI Filter</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="451fa-142">显示应用到此 GPO 的任何 WMI 筛选器。</span><span class="sxs-lookup"><span data-stu-id="451fa-142">Display any WMI filters that are applied to this GPO.</span></span> <span data-ttu-id="451fa-143">WMI 筛选器在 GPMC 的 <strong> </strong> 控制台树中的域的 Wmi 筛选器文件夹下进行管理。</span><span class="sxs-lookup"><span data-stu-id="451fa-143">WMI filters are managed under the <strong>WMI Filters</strong> folder for the domain in the console tree of the GPMC.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="451fa-144">报告</span><span class="sxs-lookup"><span data-stu-id="451fa-144">Reports</span></span>


<span data-ttu-id="451fa-145">"**设置**和**差异**" 按钮显示有关所选 gpo 版本或版本的 gpo 设置的报告。</span><span class="sxs-lookup"><span data-stu-id="451fa-145">The **Settings** and **Differences** buttons display reports about GPO settings for the GPO version or versions selected.</span></span> <span data-ttu-id="451fa-146">右键单击 "GPO 版本" 提供了用于显示基于 XML 的报表的选项。</span><span class="sxs-lookup"><span data-stu-id="451fa-146">Right-clicking GPO versions provides the option to display XML-based reports as well.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="451fa-147">按钮</span><span class="sxs-lookup"><span data-stu-id="451fa-147">Button</span></span></th>
<th align="left"><span data-ttu-id="451fa-148">作用</span><span class="sxs-lookup"><span data-stu-id="451fa-148">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="451fa-149">设置</span><span class="sxs-lookup"><span data-stu-id="451fa-149">Settings</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="451fa-150">生成基于 HTML 的报表，显示所选版本的 GPO 中的设置。</span><span class="sxs-lookup"><span data-stu-id="451fa-150">Generate an HTML-based report displaying the settings within the selected version of the GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="451fa-151">不同之处</span><span class="sxs-lookup"><span data-stu-id="451fa-151">Differences</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="451fa-152">生成用于比较 GPO 的多个选定版本内的设置的基于 HTML 的报表。</span><span class="sxs-lookup"><span data-stu-id="451fa-152">Generate an HTML-based report comparing the settings within multiple selected versions of the GPO.</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="451fa-153">差异报告的关键</span><span class="sxs-lookup"><span data-stu-id="451fa-153">Key to difference reports</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="451fa-154">符号</span><span class="sxs-lookup"><span data-stu-id="451fa-154">Symbol</span></span></th>
<th align="left"><span data-ttu-id="451fa-155">含义</span><span class="sxs-lookup"><span data-stu-id="451fa-155">Meaning</span></span></th>
<th align="left"><span data-ttu-id="451fa-156">颜色</span><span class="sxs-lookup"><span data-stu-id="451fa-156">Color</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="451fa-157">无</span><span class="sxs-lookup"><span data-stu-id="451fa-157">None</span></span></p></td>
<td align="left"><p><span data-ttu-id="451fa-158">具有两个 Gpo 中的相同设置的项目存在</span><span class="sxs-lookup"><span data-stu-id="451fa-158">Item exists with identical settings in both GPOs</span></span></p></td>
<td align="left"><p><span data-ttu-id="451fa-159">级别不同</span><span class="sxs-lookup"><span data-stu-id="451fa-159">Varies with level</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="451fa-160">[#]</span><span class="sxs-lookup"><span data-stu-id="451fa-160">[#]</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="451fa-161">项目存在于两个 Gpo 中，但具有更改后的设置</span><span class="sxs-lookup"><span data-stu-id="451fa-161">Item exists in both GPOs, but with changed settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="451fa-162">淡蓝</span><span class="sxs-lookup"><span data-stu-id="451fa-162">Blue</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="451fa-163">[-]</span><span class="sxs-lookup"><span data-stu-id="451fa-163">[-]</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="451fa-164">项目仅存在于第一个 GPO 中</span><span class="sxs-lookup"><span data-stu-id="451fa-164">Item exists only in the first GPO</span></span></p></td>
<td align="left"><p><span data-ttu-id="451fa-165">红色</span><span class="sxs-lookup"><span data-stu-id="451fa-165">Red</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="451fa-166">[+]</span><span class="sxs-lookup"><span data-stu-id="451fa-166">[+]</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="451fa-167">项目仅存在于第二个 GPO 中</span><span class="sxs-lookup"><span data-stu-id="451fa-167">Item exists only in the second GPO</span></span></p></td>
<td align="left"><p><span data-ttu-id="451fa-168">绿色</span><span class="sxs-lookup"><span data-stu-id="451fa-168">Green</span></span></p></td>
</tr>
</tbody>
</table>



-   <span data-ttu-id="451fa-169">对于具有已更改设置的项目，已更改的设置将在项目展开时标识。</span><span class="sxs-lookup"><span data-stu-id="451fa-169">For items with changed settings, the changed settings are identified when the item is expanded.</span></span> <span data-ttu-id="451fa-170">每个 GPO 中属性的值的显示顺序与在报表中显示 Gpo 的顺序相同。</span><span class="sxs-lookup"><span data-stu-id="451fa-170">The value for the attribute in each GPO is displayed in the same order that the GPOs are displayed in the report.</span></span>

-   <span data-ttu-id="451fa-171">对设置所做的一些更改可能会导致将某项报告为两个不同的项目（仅在第一个 GPO 中显示，另一个仅在第二个 GPO 中出现），而不是更改的一个项目。</span><span class="sxs-lookup"><span data-stu-id="451fa-171">Some changes to settings may cause an item to be reported as two different items (one present only in the first GPO, one present only in the second), rather than as one item that has changed.</span></span>

### <span data-ttu-id="451fa-172">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="451fa-172">Additional references</span></span>

-   [<span data-ttu-id="451fa-173">“内容”选项卡</span><span class="sxs-lookup"><span data-stu-id="451fa-173">Contents Tab</span></span>](contents-tab-agpm30ops.md)









