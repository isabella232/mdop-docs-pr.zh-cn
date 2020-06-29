---
title: “内容”选项卡功能
description: “内容”选项卡功能
author: dansimp
ms.assetid: f1f4849d-bf94-47d5-ad81-0eee33abcaca
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 081cffb7c2871d0e49abd229ec06773726483f2b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801999"
---
# <span data-ttu-id="3adf4-103">“内容”选项卡功能</span><span class="sxs-lookup"><span data-stu-id="3adf4-103">Contents Tab Features</span></span>


<span data-ttu-id="3adf4-104">"**目录**" 选项卡中的每个辅助选项卡都包含两个部分：**组策略对象**和**组和用户**。</span><span class="sxs-lookup"><span data-stu-id="3adf4-104">Each secondary tab within the **Contents** tab has two sections—**Group Policy objects** and **Groups and Users**.</span></span>

## <span data-ttu-id="3adf4-105">组策略对象部分</span><span class="sxs-lookup"><span data-stu-id="3adf4-105">Group Policy objects section</span></span>


<span data-ttu-id="3adf4-106">**组策略对象**部分显示组策略对象（gpo）的筛选列表，并标识每个 GPO 的以下属性。</span><span class="sxs-lookup"><span data-stu-id="3adf4-106">The **Group Policy objects** section displays a filtered list of Group Policy Objects (GPOs) and identifies the following attributes for each GPO.</span></span> <span data-ttu-id="3adf4-107">你可以使用**搜索**框来搜索具有特定属性的 gpo。</span><span class="sxs-lookup"><span data-stu-id="3adf4-107">You can use the **Search** box to search for GPOs with specific attributes.</span></span> <span data-ttu-id="3adf4-108">有关详细信息，请参阅[搜索和筛选 Gpo 列表](search-and-filter-the-list-of-gpos.md)。</span><span class="sxs-lookup"><span data-stu-id="3adf4-108">For more information, see [Search and Filter the List of GPOs](search-and-filter-the-list-of-gpos.md).</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="3adf4-109">GPO 属性</span><span class="sxs-lookup"><span data-stu-id="3adf4-109">GPO attribute</span></span></th>
<th align="left"><span data-ttu-id="3adf4-110">描述</span><span class="sxs-lookup"><span data-stu-id="3adf4-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="3adf4-111">名称</span><span class="sxs-lookup"><span data-stu-id="3adf4-111">Name</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="3adf4-112">GPO 的名称。</span><span class="sxs-lookup"><span data-stu-id="3adf4-112">Name of the GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="3adf4-113">State</span><span class="sxs-lookup"><span data-stu-id="3adf4-113">State</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="3adf4-114">所选 GPO 的状态</span><span class="sxs-lookup"><span data-stu-id="3adf4-114">The state of the selected GPO</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="3adf4-115">更改者</span><span class="sxs-lookup"><span data-stu-id="3adf4-115">Changed By</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="3adf4-116">已签入或已部署选定 GPO 的审批者的编辑者。</span><span class="sxs-lookup"><span data-stu-id="3adf4-116">The Editor who checked in or the Approver who deployed the selected GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="3adf4-117">更改日期</span><span class="sxs-lookup"><span data-stu-id="3adf4-117">Change Date</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="3adf4-118">对于受控 GPO，在修改或签出后将其签入的最新日期。</span><span class="sxs-lookup"><span data-stu-id="3adf4-118">For a controlled GPO, the most recent date it was checked in after being modified or checked out to be modified.</span></span> <span data-ttu-id="3adf4-119">对于不受控制的 GPO，为其上次修改的日期。</span><span class="sxs-lookup"><span data-stu-id="3adf4-119">For an uncontrolled GPO, the date when it was last modified.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="3adf4-120">评论</span><span class="sxs-lookup"><span data-stu-id="3adf4-120">Comment</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="3adf4-121">在修改时由签入或部署 GPO 的人员输入的注释。</span><span class="sxs-lookup"><span data-stu-id="3adf4-121">A comment entered by the person who checked in or deployed a GPO at the time that it was modified.</span></span> <span data-ttu-id="3adf4-122">在需要回滚到较早版本的情况下，用于识别版本的详细信息。</span><span class="sxs-lookup"><span data-stu-id="3adf4-122">Useful for identifying the specifics of the version in case of the need to roll back to an earlier version.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="3adf4-123">计算机版本</span><span class="sxs-lookup"><span data-stu-id="3adf4-123">Computer Version</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="3adf4-124">GPO 的 "计算机配置" 部分的自动生成的版本。</span><span class="sxs-lookup"><span data-stu-id="3adf4-124">Automatically generated version of the Computer Configuration part of the GPO.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="3adf4-125">用户版本</span><span class="sxs-lookup"><span data-stu-id="3adf4-125">User Version</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="3adf4-126">GPO 的用户配置部分的自动生成的版本。</span><span class="sxs-lookup"><span data-stu-id="3adf4-126">Automatically generated version of the User Configuration part of the GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="3adf4-127">GPO 状态</span><span class="sxs-lookup"><span data-stu-id="3adf4-127">GPO Status</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="3adf4-128">计算机配置和用户配置可以单独管理。</span><span class="sxs-lookup"><span data-stu-id="3adf4-128">The Computer Configuration and the User Configuration can be managed separately.</span></span> <span data-ttu-id="3adf4-129">GPO 状态表示启用了 GPO 的哪些部分。</span><span class="sxs-lookup"><span data-stu-id="3adf4-129">The GPO Status indicates which portions of the GPO are enabled.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="3adf4-130">WMI 筛选器</span><span class="sxs-lookup"><span data-stu-id="3adf4-130">WMI Filter</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="3adf4-131">显示应用到此 GPO 的任何 WMI 筛选器。</span><span class="sxs-lookup"><span data-stu-id="3adf4-131">Display any WMI filters that are applied to this GPO.</span></span> <span data-ttu-id="3adf4-132">WMI 筛选器在 GPMC 的 <strong> </strong> 控制台树中的域的 Wmi 筛选器文件夹下进行管理。</span><span class="sxs-lookup"><span data-stu-id="3adf4-132">WMI filters are managed under the <strong>WMI Filters</strong> folder for the domain in the console tree of the GPMC.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="3adf4-133">组和用户部分</span><span class="sxs-lookup"><span data-stu-id="3adf4-133">Groups and Users section</span></span>


<span data-ttu-id="3adf4-134">选择 GPO 时，"**组和用户**" 部分将显示有权访问该 GPO 的组和用户的列表。</span><span class="sxs-lookup"><span data-stu-id="3adf4-134">When a GPO is selected, the **Groups and Users** section displays a list of the groups and users with access to that GPO.</span></span> <span data-ttu-id="3adf4-135">为每个组或用户显示允许的权限和继承。</span><span class="sxs-lookup"><span data-stu-id="3adf4-135">The allowed permissions and inheritance are displayed for each group or user.</span></span> <span data-ttu-id="3adf4-136">AGPM 管理员可以使用标准 AGPM 角色（编辑、审批者、审阅者和 AGPM 管理员）或自定义权限组合配置权限。</span><span class="sxs-lookup"><span data-stu-id="3adf4-136">An AGPM Administrator can configure permissions using either standard AGPM roles (Editor, Approver, Reviewer, and AGPM Administrator) or a customized combination of permissions.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="3adf4-137">按钮</span><span class="sxs-lookup"><span data-stu-id="3adf4-137">Button</span></span></th>
<th align="left"><span data-ttu-id="3adf4-138">作用</span><span class="sxs-lookup"><span data-stu-id="3adf4-138">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="3adf4-139">添加</span><span class="sxs-lookup"><span data-stu-id="3adf4-139">Add</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="3adf4-140">将新条目添加到安全描述符中。</span><span class="sxs-lookup"><span data-stu-id="3adf4-140">Add a new entry to the security descriptor.</span></span> <span data-ttu-id="3adf4-141">可以添加 Active Directory 中的任何用户或组。</span><span class="sxs-lookup"><span data-stu-id="3adf4-141">Any user or group in Active Directory can be added.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="3adf4-142">删除</span><span class="sxs-lookup"><span data-stu-id="3adf4-142">Remove</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="3adf4-143">从 "访问控制列表" 中删除所选条目。</span><span class="sxs-lookup"><span data-stu-id="3adf4-143">Remove the selected entry from the Access Control List.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="3adf4-144">属性</span><span class="sxs-lookup"><span data-stu-id="3adf4-144">Properties</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="3adf4-145">显示所选对象的属性。</span><span class="sxs-lookup"><span data-stu-id="3adf4-145">Display the properties for the selected object.</span></span> <span data-ttu-id="3adf4-146">"属性" 页面与 <strong> Active Directory 用户和计算机中的对象显示的属性相同 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="3adf4-146">The properties page is the same one displayed for an object in <strong>Active Directory Users and Computers</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="3adf4-147">高级</span><span class="sxs-lookup"><span data-stu-id="3adf4-147">Advanced</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="3adf4-148">打开 " <strong> 访问控制列表编辑器" </strong> 。</span><span class="sxs-lookup"><span data-stu-id="3adf4-148">Open the <strong>Access Control List Editor</strong>.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="3adf4-149">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="3adf4-149">Additional considerations</span></span>

-   <span data-ttu-id="3adf4-150">有关与特定任务相关的角色和权限的信息，请参阅[执行 AGPM 管理员任务](performing-agpm-administrator-tasks-agpm40.md)、[执行编辑任务](performing-editor-tasks-agpm40.md)、[执行审批者任务](performing-approver-tasks-agpm40.md)和[执行审阅者任务](performing-reviewer-tasks-agpm40.md)中的任务。</span><span class="sxs-lookup"><span data-stu-id="3adf4-150">For information about roles and permissions related to specific tasks, see the tasks under [Performing AGPM Administrator Tasks](performing-agpm-administrator-tasks-agpm40.md), [Performing Editor Tasks](performing-editor-tasks-agpm40.md), [Performing Approver Tasks](performing-approver-tasks-agpm40.md), and [Performing Reviewer Tasks](performing-reviewer-tasks-agpm40.md).</span></span>

### <span data-ttu-id="3adf4-151">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="3adf4-151">Additional references</span></span>

-   [<span data-ttu-id="3adf4-152">“内容”选项卡</span><span class="sxs-lookup"><span data-stu-id="3adf4-152">Contents Tab</span></span>](contents-tab-agpm40.md)

 

 





