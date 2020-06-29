---
title: 搜索和筛选 GPO 列表
description: 搜索和筛选 GPO 列表
author: dansimp
ms.assetid: 1bc58a38-033c-4aed-9eb4-c239827f5501
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 5646a51a37a4ca9195fb9ef858e8c5920ca7738a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802547"
---
# <span data-ttu-id="3a8b1-103">搜索和筛选 GPO 列表</span><span class="sxs-lookup"><span data-stu-id="3a8b1-103">Search and Filter the List of GPOs</span></span>


<span data-ttu-id="3a8b1-104">在高级组策略管理（AGPM）中，您可以搜索组策略对象（Gpo）的列表及其属性以筛选所显示的 Gpo 列表。</span><span class="sxs-lookup"><span data-stu-id="3a8b1-104">In Advanced Group Policy Management (AGPM), you can search the list of Group Policy Objects (GPOs) and their attributes to filter the list of GPOs displayed.</span></span> <span data-ttu-id="3a8b1-105">例如，您可以搜索具有特定名称、状态或注释的 Gpo。</span><span class="sxs-lookup"><span data-stu-id="3a8b1-105">For example, you can search for GPOs with a particular name, state, or comment.</span></span> <span data-ttu-id="3a8b1-106">你还可以搜索特定组策略管理员或特定日期上次更改的 Gpo。</span><span class="sxs-lookup"><span data-stu-id="3a8b1-106">You can also search for GPOs that were last changed by a particular Group Policy administrator or on a particular date.</span></span>

## <span data-ttu-id="3a8b1-107">执行复杂的搜索</span><span class="sxs-lookup"><span data-stu-id="3a8b1-107">Performing a complex search</span></span>


<span data-ttu-id="3a8b1-108">你可以使用 format *GPO 属性1：搜索字符串 1 GPO 属性2：搜索字符串 2 .。。所有列搜索字符串*。</span><span class="sxs-lookup"><span data-stu-id="3a8b1-108">You can perform a complex search by using the format *GPO attribute 1: search string 1 GPO attribute 2: search string 2…all-column search strings*.</span></span> <span data-ttu-id="3a8b1-109">搜索不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="3a8b1-109">The search is not case-sensitive.</span></span>

-   <span data-ttu-id="3a8b1-110">**GPO 属性：** 在除**计算机版本**或**用户版本**之外的 AGPM 中的 gpo 列表中的任何列标题。</span><span class="sxs-lookup"><span data-stu-id="3a8b1-110">**GPO attribute:** Any column heading in the list of GPOs in AGPM other than **Computer Version** or **User Version**.</span></span> <span data-ttu-id="3a8b1-111">GPO 属性包括 GPO 名称、状态、最近更改了 GPO 的用户、最新更改 gpo 的日期和时间、注释、GPO 状态和应用到 GPO 的 WMI 筛选器。</span><span class="sxs-lookup"><span data-stu-id="3a8b1-111">GPO attributes include the GPO name, state, user who most recently changed the GPO, date and time when the GPO was most recently changed, comment, GPO status, and WMI filter applied to the GPO.</span></span>

-   <span data-ttu-id="3a8b1-112">**搜索字符串：** 要在指定列中搜索的文本。</span><span class="sxs-lookup"><span data-stu-id="3a8b1-112">**Search string:** Text for which to search in the specified column.</span></span> <span data-ttu-id="3a8b1-113">如果字符串包含空格，则必须用引号将字符串引起来。</span><span class="sxs-lookup"><span data-stu-id="3a8b1-113">If a string includes spaces, you must enclose the string with quotation marks.</span></span>

-   <span data-ttu-id="3a8b1-114">**所有列搜索字符串：** 要在除**计算机版本**和**用户版本**之外的 AGPM 的 gpo 列表中的所有列中搜索的文本。</span><span class="sxs-lookup"><span data-stu-id="3a8b1-114">**All-column search strings:** Text for which to search in all columns in the list of GPOs in AGPM other than **Computer Version** and **User Version**.</span></span> <span data-ttu-id="3a8b1-115">可以包含以空格分隔的多个字符串。</span><span class="sxs-lookup"><span data-stu-id="3a8b1-115">You can include multiple strings separated by spaces.</span></span> <span data-ttu-id="3a8b1-116">如果字符串包含空格，则必须用引号将字符串引起来。</span><span class="sxs-lookup"><span data-stu-id="3a8b1-116">If a string includes spaces, you must enclose the string with quotation marks.</span></span>

<span data-ttu-id="3a8b1-117">每个 GPO 属性和搜索字符串对以及每个全列搜索字符串都使用逻辑 AND 运算组合。</span><span class="sxs-lookup"><span data-stu-id="3a8b1-117">Each GPO attribute and search string pair and each all-column search string are combined by using a logical AND operation.</span></span> <span data-ttu-id="3a8b1-118">结果是所有 Gpo 的列表，其中每个指定的属性都包含指定的搜索字符串，并且所有所有列的搜索字符串都显示在至少一个列中。</span><span class="sxs-lookup"><span data-stu-id="3a8b1-118">The result is a list of all GPOs for which each specified attribute includes the specified search string and for which any all-column search strings appear in at least one column.</span></span> <span data-ttu-id="3a8b1-119">搜索将返回字符串的任何部分匹配项，以便你可以输入 GPO 名称或用户名的一部分，并查看其名称中包含该文本的所有 Gpo 的列表。</span><span class="sxs-lookup"><span data-stu-id="3a8b1-119">The search returns any partial matches for strings so that you can enter part of a GPO name or user name and view a list of all GPOs that include that text in their name.</span></span>

<span data-ttu-id="3a8b1-120">下面是搜索的示例：</span><span class="sxs-lookup"><span data-stu-id="3a8b1-120">The following are examples of searches:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="3a8b1-121">搜索结果说明</span><span class="sxs-lookup"><span data-stu-id="3a8b1-121">Description of search result</span></span></th>
<th align="left"><span data-ttu-id="3a8b1-122">搜索查询</span><span class="sxs-lookup"><span data-stu-id="3a8b1-122">Search query</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3a8b1-123">名称中包含文本安全性和北美的所有 Gpo <strong> </strong> <strong> </strong> 。</span><span class="sxs-lookup"><span data-stu-id="3a8b1-123">All GPOs with names that include the text <strong>security</strong> and <strong>North America</strong>.</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="3a8b1-124">名称： </strong><strong> 安全 </strong><strong> 名称： </strong> 北美 &quot; <strong></strong>&quot;</span><span class="sxs-lookup"><span data-stu-id="3a8b1-124">name:</strong><strong>security</strong><strong>name:</strong>&quot;<strong>North America</strong>&quot;</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3a8b1-125">所有已签出的 Gpo。</span><span class="sxs-lookup"><span data-stu-id="3a8b1-125">All checked out GPOs.</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="3a8b1-126">状态： </strong> &quot; <strong> 已签出</strong>&quot;</span><span class="sxs-lookup"><span data-stu-id="3a8b1-126">state:</strong>&quot;<strong>checked out</strong>&quot;</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3a8b1-127">所有最近由用户（名为管理员）更改的 Gpo <strong> </strong> 和上个月内最近更改的 gpo。</span><span class="sxs-lookup"><span data-stu-id="3a8b1-127">All GPOs most recently changed by the user named <strong>Administrator</strong> and most recently changed within the previous month.</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="3a8b1-128">更改者： </strong><strong> 管理员 </strong><strong> 更改日期： </strong><strong> lastmonth</span><span class="sxs-lookup"><span data-stu-id="3a8b1-128">changed by:</strong><strong>Administrator</strong><strong>change date:</strong><strong>lastmonth</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3a8b1-129">在 <strong> 最新注释中包含 word 防火墙的所有 gpo </strong> 以及 word <strong> 安全性 </strong> 出现在任何列中的所有 gpo。</span><span class="sxs-lookup"><span data-stu-id="3a8b1-129">All GPOs in which the word <strong>firewall</strong> is included in the most recent comment and in which the word <strong>security</strong> appears in any column.</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="3a8b1-130">注释： </strong><strong> 防火墙 </strong><strong> 安全性</span><span class="sxs-lookup"><span data-stu-id="3a8b1-130">comment:</strong><strong>firewall</strong><strong>security</span></span></strong></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3a8b1-131">所有设置状态为 "已禁用" 的所有 Gpo <strong> </strong> 。</span><span class="sxs-lookup"><span data-stu-id="3a8b1-131">All GPOs that have a status of <strong>All Settings Disabled</strong>.</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="3a8b1-132">gpo 状态： </strong><strong> 全部</span><span class="sxs-lookup"><span data-stu-id="3a8b1-132">gpo status:</strong><strong>all</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3a8b1-133">应用了名为 <strong> "我的 Wmi 筛选器" </strong> 且状态为 "已 <strong> 禁用用户配置设置" 的 wmi 筛选器的所有 gpo </strong> 。</span><span class="sxs-lookup"><span data-stu-id="3a8b1-133">All GPOs that have a WMI filter named <strong>My WMI Filter</strong> applied and that have a status of <strong>User Configuration Settings Disabled</strong>.</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="3a8b1-134">wmi 筛选器： </strong> &quot; <strong> 我的 wmi 筛选器 </strong> &quot; <strong> gpo 状态： </strong><strong> 用户</span><span class="sxs-lookup"><span data-stu-id="3a8b1-134">wmi filter:</strong>&quot;<strong>My WMI Filter</strong>&quot;<strong>gpo status:</strong><strong>user</span></span></strong></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="3a8b1-135">指定日期</span><span class="sxs-lookup"><span data-stu-id="3a8b1-135">Specifying dates</span></span>


<span data-ttu-id="3a8b1-136">你可以在特定时间通过使用在 Windows 中搜索时可用的相同特殊条件来搜索在特定日期、特定时间或一段时间内更改的 Gpo。</span><span class="sxs-lookup"><span data-stu-id="3a8b1-136">You can search for GPOs changed on a specific date, at a specific time, or during a span of time by using the same special terms available when you search in Windows.</span></span> <span data-ttu-id="3a8b1-137">如果输入特定日期或时间，则必须使用 "**更改日期**" 列中使用的格式。</span><span class="sxs-lookup"><span data-stu-id="3a8b1-137">If entering a specific date or time, you must use the format that is used in the **Change Date** column.</span></span> <span data-ttu-id="3a8b1-138">以下是 "**更改日期**" 列的搜索示例：</span><span class="sxs-lookup"><span data-stu-id="3a8b1-138">The following are examples of searches of the **Change Date** column:</span></span>

-   <span data-ttu-id="3a8b1-139">**更改日期：\*\*\*\*10/10/2009**</span><span class="sxs-lookup"><span data-stu-id="3a8b1-139">**change date:\*\*\*\*10/10/2009**</span></span>

-   <span data-ttu-id="3a8b1-140">**更改日期：\*\*\*\*10/10/2009 9:00:00 AM**</span><span class="sxs-lookup"><span data-stu-id="3a8b1-140">**change date:\*\*\*\*10/10/2009 9:00:00 AM**</span></span>

-   <span data-ttu-id="3a8b1-141">**更改日期：\*\*\*\*thisweek**</span><span class="sxs-lookup"><span data-stu-id="3a8b1-141">**change date:\*\*\*\*thisweek**</span></span>

<span data-ttu-id="3a8b1-142">当您搜索 "**更改日期**" 列时，可以使用以下特殊术语（它们不区分大小写）：</span><span class="sxs-lookup"><span data-stu-id="3a8b1-142">You can use the following special terms, which are not case-sensitive, when you search the **Change Date** column:</span></span>

-   **<span data-ttu-id="3a8b1-143">今天</span><span class="sxs-lookup"><span data-stu-id="3a8b1-143">Today</span></span>**

-   **<span data-ttu-id="3a8b1-144">昨天</span><span class="sxs-lookup"><span data-stu-id="3a8b1-144">Yesterday</span></span>**

-   **<span data-ttu-id="3a8b1-145">ThisWeek</span><span class="sxs-lookup"><span data-stu-id="3a8b1-145">ThisWeek</span></span>**

-   **<span data-ttu-id="3a8b1-146">LastWeek</span><span class="sxs-lookup"><span data-stu-id="3a8b1-146">LastWeek</span></span>**

-   **<span data-ttu-id="3a8b1-147">ThisMonth</span><span class="sxs-lookup"><span data-stu-id="3a8b1-147">ThisMonth</span></span>**

-   **<span data-ttu-id="3a8b1-148">LastMonth</span><span class="sxs-lookup"><span data-stu-id="3a8b1-148">LastMonth</span></span>**

-   **<span data-ttu-id="3a8b1-149">TwoMonths</span><span class="sxs-lookup"><span data-stu-id="3a8b1-149">TwoMonths</span></span>**

-   **<span data-ttu-id="3a8b1-150">ThreeMonths</span><span class="sxs-lookup"><span data-stu-id="3a8b1-150">ThreeMonths</span></span>**

-   **<span data-ttu-id="3a8b1-151">ThisYear</span><span class="sxs-lookup"><span data-stu-id="3a8b1-151">ThisYear</span></span>**

-   **<span data-ttu-id="3a8b1-152">LastYear</span><span class="sxs-lookup"><span data-stu-id="3a8b1-152">LastYear</span></span>**

### <span data-ttu-id="3a8b1-153">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="3a8b1-153">Additional considerations</span></span>

-   <span data-ttu-id="3a8b1-154">默认情况下，你必须是审阅者、编辑者、审批者或 AGPM 管理员（完全控制）才能执行此过程。</span><span class="sxs-lookup"><span data-stu-id="3a8b1-154">By default, you must be a Reviewer, an Editor, an Approver, or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="3a8b1-155">具体而言，您必须具有域的 "**列表内容**" 权限。</span><span class="sxs-lookup"><span data-stu-id="3a8b1-155">Specifically, you must have **List Contents** permission for the domain.</span></span>

-   <span data-ttu-id="3a8b1-156">有关 GPO 属性的详细信息，请参阅[目录选项卡功能](contents-tab-features-agpm40.md)。</span><span class="sxs-lookup"><span data-stu-id="3a8b1-156">For more information about GPO attributes, see [Contents Tab Features](contents-tab-features-agpm40.md).</span></span>

### <span data-ttu-id="3a8b1-157">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="3a8b1-157">Additional references</span></span>

-   [<span data-ttu-id="3a8b1-158">高级组策略管理 4.0</span><span class="sxs-lookup"><span data-stu-id="3a8b1-158">Advanced Group Policy Management 4.0</span></span>](advanced-group-policy-management-40.md)

 

 





