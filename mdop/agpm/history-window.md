---
title: “历史记录”窗口
description: “历史记录”窗口
author: dansimp
ms.assetid: f11f9ad9-bffe-4c56-8c46-fe9c0a8e55c1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 02b4336409f33d6c1f2868bceb22cb95120f2198
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802756"
---
# <span data-ttu-id="1ec5b-103">“历史记录”窗口</span><span class="sxs-lookup"><span data-stu-id="1ec5b-103">History Window</span></span>


<span data-ttu-id="1ec5b-104">通过双击 GPO 或右键单击 GPO，然后单击 "**历史记录**"，可以显示组策略对象（GPO）的历史记录。</span><span class="sxs-lookup"><span data-stu-id="1ec5b-104">The history of a Group Policy object (GPO) can be displayed by double-clicking a GPO or by right-clicking a GPO and then clicking **History**.</span></span> <span data-ttu-id="1ec5b-105">它还显示在**组策略管理控制台**（GPMC）中，作为每个 GPO 的选项卡。</span><span class="sxs-lookup"><span data-stu-id="1ec5b-105">It is also displayed in the **Group Policy Management Console** (GPMC) as a tab for each GPO.</span></span>

<span data-ttu-id="1ec5b-106">历史记录提供在存档中保存的选定 GPO 的所有版本的列表。</span><span class="sxs-lookup"><span data-stu-id="1ec5b-106">The history provides a list of all versions of the selected GPO saved within the archive.</span></span> <span data-ttu-id="1ec5b-107">在 "**历史记录**" 窗口中，你可以获取 gpo 中的设置的报表、比较 gpo 的多个版本或回退到 gpo 的早期版本。</span><span class="sxs-lookup"><span data-stu-id="1ec5b-107">From the **History** window, you can obtain a report of the settings within a GPO, compare multiple versions of a GPO, or roll back to a previous version of a GPO.</span></span>

## <span data-ttu-id="1ec5b-108">在 "历史记录" 窗口中筛选事件</span><span class="sxs-lookup"><span data-stu-id="1ec5b-108">Filtering events in the History window</span></span>


<span data-ttu-id="1ec5b-109">"**历史记录**" 窗口中的选项卡将筛选显示的事件。</span><span class="sxs-lookup"><span data-stu-id="1ec5b-109">The tabs within the **History** window filter the events displayed.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="1ec5b-110">Tabs</span><span class="sxs-lookup"><span data-stu-id="1ec5b-110">Tabs</span></span></th>
<th align="left"><span data-ttu-id="1ec5b-111">筛选</span><span class="sxs-lookup"><span data-stu-id="1ec5b-111">Filtering</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="1ec5b-112">全部显示</span><span class="sxs-lookup"><span data-stu-id="1ec5b-112">Show All</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="1ec5b-113">显示 GPO 的所有版本。</span><span class="sxs-lookup"><span data-stu-id="1ec5b-113">Display all versions of the GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="1ec5b-114">已签入</span><span class="sxs-lookup"><span data-stu-id="1ec5b-114">Checked In</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="1ec5b-115">仅显示 GPO 的已签入版本。</span><span class="sxs-lookup"><span data-stu-id="1ec5b-115">Display only checked-in versions of the GPO.</span></span> <span data-ttu-id="1ec5b-116">此列表中省略了已部署的版本。</span><span class="sxs-lookup"><span data-stu-id="1ec5b-116">The deployed version is omitted from this list.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="1ec5b-117">仅限标签</span><span class="sxs-lookup"><span data-stu-id="1ec5b-117">Labels Only</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="1ec5b-118">仅显示与其相关联的标签的 Gpo。</span><span class="sxs-lookup"><span data-stu-id="1ec5b-118">Display only GPOs that have labels associated with them.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="1ec5b-119">事件信息</span><span class="sxs-lookup"><span data-stu-id="1ec5b-119">Event information</span></span>


<span data-ttu-id="1ec5b-120">为所选 GPO 的历史记录中的每个事件提供了信息。</span><span class="sxs-lookup"><span data-stu-id="1ec5b-120">Information is provided for each event in the history of the selected GPO.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="1ec5b-121">GPO 特性</span><span class="sxs-lookup"><span data-stu-id="1ec5b-121">GPO Characteristic</span></span></th>
<th align="left"><span data-ttu-id="1ec5b-122">描述</span><span class="sxs-lookup"><span data-stu-id="1ec5b-122">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="1ec5b-123">计算机</span><span class="sxs-lookup"><span data-stu-id="1ec5b-123">Computer</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="1ec5b-124">GPO 的计算机配置部分的自动生成的版本。</span><span class="sxs-lookup"><span data-stu-id="1ec5b-124">Automatically generated version of the Computer Configuration portion of the GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="1ec5b-125">用户</span><span class="sxs-lookup"><span data-stu-id="1ec5b-125">User</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="1ec5b-126">GPO 的用户配置部分的自动生成的版本。</span><span class="sxs-lookup"><span data-stu-id="1ec5b-126">Automatically generated version of the User Configuration portion of the GPO.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="1ec5b-127">时间</span><span class="sxs-lookup"><span data-stu-id="1ec5b-127">Time</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="1ec5b-128">在执行 "状态" 字段中的操作时，GPO 版本的时间戳。</span><span class="sxs-lookup"><span data-stu-id="1ec5b-128">Timestamp of the version of the GPO when the action in the status field was performed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="1ec5b-129">State</span><span class="sxs-lookup"><span data-stu-id="1ec5b-129">State</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="1ec5b-130">GPO 的选定版本的状态：</span><span class="sxs-lookup"><span data-stu-id="1ec5b-130">The state of the selected version of the GPO:</span></span></p>
<p><img src="images/36f6b687-f5cc-40d1-805f-b191d1fb1ace.gif" alt="Deployed GPO icon" /> <strong><span data-ttu-id="1ec5b-131">已部署 </strong> ：此版本的 GPO 当前处于生产环境中。</span><span class="sxs-lookup"><span data-stu-id="1ec5b-131">Deployed</strong>: This version of the GPO is currently live in the production environment.</span></span></p>
<p><img src="images/57b610a5-1c71-4d26-9173-d04abd495fcc.gif" alt="Checked in GPO icon" /> <strong><span data-ttu-id="1ec5b-132">已签入 </strong> ：此版本的 GPO 可供授权编辑人员签出以进行编辑或组策略管理员进行部署。</span><span class="sxs-lookup"><span data-stu-id="1ec5b-132">Checked In</strong>: This version of the GPO is available for authorized Editors to check out for editing or for a Group Policy administrator to deploy.</span></span></p>
<p><img src="images/8e7a7c4e-809a-435a-8b29-30d797936210.gif" alt="Checked out GPO icon" /> <strong><span data-ttu-id="1ec5b-133">已签出 </strong> ：该 GPO 的当前版本当前由一个编辑器签出，并且不适用于其他编辑器。</span><span class="sxs-lookup"><span data-stu-id="1ec5b-133">Checked Out</strong>: This version of the GPO is currently checked out by an Editor and is unavailable for other Editors.</span></span> <span data-ttu-id="1ec5b-134">（签出状态不会记录在 <strong>历史记录 </strong> ，除了指示 GPO 当前是否已签出。）</span><span class="sxs-lookup"><span data-stu-id="1ec5b-134">(The checked out state is not recorded in the <strong>History</strong> except to indicate if a GPO is currently checked out.)</span></span></p>
<p><img src="images/327623bd-0842-4372-be1f-bdc4b8c3481c.gif" alt="Created GPO icon" /> <strong><span data-ttu-id="1ec5b-135">已创建 </strong> ：标识最初创建 GPO 的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="1ec5b-135">Created</strong>: Identifies the date and time of the initial creation of the GPO.</span></span></p>
<p><img src="images/8356fcdc-1279-425b-ab14-a23bcfe391da.gif" alt="Labeled GPO icon" /> <strong><span data-ttu-id="1ec5b-136">标记 </strong> ：标识 GPO 的标记版本。</span><span class="sxs-lookup"><span data-stu-id="1ec5b-136">Labeled</strong>: Identifies a labeled version of the GPO.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="1ec5b-137">GPO 状态</span><span class="sxs-lookup"><span data-stu-id="1ec5b-137">GPO Status</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="1ec5b-138">计算机配置和用户配置可以彼此分开管理。</span><span class="sxs-lookup"><span data-stu-id="1ec5b-138">The Computer Configuration and the User Configuration can be managed separately from each other.</span></span> <span data-ttu-id="1ec5b-139">此状态显示启用了 GPO 的哪些部分。</span><span class="sxs-lookup"><span data-stu-id="1ec5b-139">This status shows which portions of the GPO are enabled.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="1ec5b-140">所有者</span><span class="sxs-lookup"><span data-stu-id="1ec5b-140">Owner</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="1ec5b-141">已签入或已部署 GPO 的人员。</span><span class="sxs-lookup"><span data-stu-id="1ec5b-141">The person who checked in or deployed the GPO.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="1ec5b-142">评论</span><span class="sxs-lookup"><span data-stu-id="1ec5b-142">Comment</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="1ec5b-143">修改此版本时 GPO 所有者输入的评论。</span><span class="sxs-lookup"><span data-stu-id="1ec5b-143">A comment entered by the owner of a GPO at the time that this version was modified.</span></span> <span data-ttu-id="1ec5b-144">在需要回滚到以前版本的情况下，用于识别版本的详细信息。</span><span class="sxs-lookup"><span data-stu-id="1ec5b-144">Useful for identifying the specifics of the version in case of the need to roll back to a previous version.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="1ec5b-145">报告</span><span class="sxs-lookup"><span data-stu-id="1ec5b-145">Reports</span></span>


<span data-ttu-id="1ec5b-146">根据是否选择了单个 GPO 版本或多个 GPO 版本，"**设置**" 和 "**差异**" 按钮将显示有关 GPO 设置的报告。</span><span class="sxs-lookup"><span data-stu-id="1ec5b-146">Depending on whether a single GPO version or multiple GPO versions are selected, the **Settings** and **Differences** buttons display reports on GPO settings.</span></span> <span data-ttu-id="1ec5b-147">右键单击 "GPO 版本" 提供了用于显示基于 XML 的报表的选项。</span><span class="sxs-lookup"><span data-stu-id="1ec5b-147">Right-clicking GPO versions provides the option to display XML-based reports as well.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="1ec5b-148">按钮</span><span class="sxs-lookup"><span data-stu-id="1ec5b-148">Button</span></span></th>
<th align="left"><span data-ttu-id="1ec5b-149">作用</span><span class="sxs-lookup"><span data-stu-id="1ec5b-149">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="1ec5b-150">设置</span><span class="sxs-lookup"><span data-stu-id="1ec5b-150">Settings</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="1ec5b-151">生成基于 HTML 的报表，显示所选版本的 GPO 中的设置。</span><span class="sxs-lookup"><span data-stu-id="1ec5b-151">Generate an HTML-based report displaying the settings within the selected version of the GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="1ec5b-152">不同之处</span><span class="sxs-lookup"><span data-stu-id="1ec5b-152">Differences</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="1ec5b-153">生成用于比较 GPO 的多个选定版本内的设置的基于 HTML 的报表。</span><span class="sxs-lookup"><span data-stu-id="1ec5b-153">Generate an HTML-based report comparing the settings within multiple selected versions of the GPO.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="1ec5b-154">差异报告的关键</span><span class="sxs-lookup"><span data-stu-id="1ec5b-154">Key to difference reports</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="1ec5b-155">符号</span><span class="sxs-lookup"><span data-stu-id="1ec5b-155">Symbol</span></span></th>
<th align="left"><span data-ttu-id="1ec5b-156">含义</span><span class="sxs-lookup"><span data-stu-id="1ec5b-156">Meaning</span></span></th>
<th align="left"><span data-ttu-id="1ec5b-157">颜色</span><span class="sxs-lookup"><span data-stu-id="1ec5b-157">Color</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1ec5b-158">无</span><span class="sxs-lookup"><span data-stu-id="1ec5b-158">None</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ec5b-159">具有两个 Gpo 中的相同设置的项目存在</span><span class="sxs-lookup"><span data-stu-id="1ec5b-159">Item exists with identical settings in both GPOs</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ec5b-160">级别不同</span><span class="sxs-lookup"><span data-stu-id="1ec5b-160">Varies with level</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="1ec5b-161">[#]</span><span class="sxs-lookup"><span data-stu-id="1ec5b-161">[#]</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="1ec5b-162">项目存在于两个 Gpo 中，但具有更改后的设置</span><span class="sxs-lookup"><span data-stu-id="1ec5b-162">Item exists in both GPOs, but with changed settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ec5b-163">淡蓝</span><span class="sxs-lookup"><span data-stu-id="1ec5b-163">Blue</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="1ec5b-164">[-]</span><span class="sxs-lookup"><span data-stu-id="1ec5b-164">[-]</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="1ec5b-165">项目仅存在于第一个 GPO 中</span><span class="sxs-lookup"><span data-stu-id="1ec5b-165">Item exists only in the first GPO</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ec5b-166">红色</span><span class="sxs-lookup"><span data-stu-id="1ec5b-166">Red</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="1ec5b-167">[+]</span><span class="sxs-lookup"><span data-stu-id="1ec5b-167">[+]</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="1ec5b-168">项目仅存在于第二个 GPO 中</span><span class="sxs-lookup"><span data-stu-id="1ec5b-168">Item exists only in the second GPO</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ec5b-169">绿色</span><span class="sxs-lookup"><span data-stu-id="1ec5b-169">Green</span></span></p></td>
</tr>
</tbody>
</table>

 

-   <span data-ttu-id="1ec5b-170">对于具有已更改设置的项目，已更改的设置将在项目展开时标识。</span><span class="sxs-lookup"><span data-stu-id="1ec5b-170">For items with changed settings, the changed settings are identified when the item is expanded.</span></span> <span data-ttu-id="1ec5b-171">每个 GPO 中属性的值的显示顺序与在报表中显示 Gpo 的顺序相同。</span><span class="sxs-lookup"><span data-stu-id="1ec5b-171">The value for the attribute in each GPO is displayed in the same order that the GPOs are displayed in the report.</span></span>

-   <span data-ttu-id="1ec5b-172">对设置所做的一些更改可能会导致将某项报告为两个不同的项目（仅在第一个 GPO 中显示，另一个仅在第二个 GPO 中出现），而不是更改的一个项目。</span><span class="sxs-lookup"><span data-stu-id="1ec5b-172">Some changes to settings may cause an item to be reported as two different items (one present only in the first GPO, one present only in the second), rather than as one item that has changed.</span></span>

### <span data-ttu-id="1ec5b-173">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="1ec5b-173">Additional references</span></span>

-   [<span data-ttu-id="1ec5b-174">“内容”选项卡</span><span class="sxs-lookup"><span data-stu-id="1ec5b-174">Contents Tab</span></span>](contents-tab.md)

 

 





