---
title: “内容”选项卡功能
description: “内容”选项卡功能
author: dansimp
ms.assetid: 725f025a-c30a-4d07-add1-4e0ed9a1a5fd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f64aad16a3335d78641812121692f6d5f6436ee1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802004"
---
# <span data-ttu-id="fea35-103">“内容”选项卡功能</span><span class="sxs-lookup"><span data-stu-id="fea35-103">Contents Tab Features</span></span>


<span data-ttu-id="fea35-104">"**目录**" 选项卡中的每个辅助选项卡都包含两个部分：**组策略对象**和**组和用户**。</span><span class="sxs-lookup"><span data-stu-id="fea35-104">Each secondary tab within the **Contents** tab has two sections—**Group Policy objects** and **Groups and Users**.</span></span>

## <span data-ttu-id="fea35-105">组策略对象部分</span><span class="sxs-lookup"><span data-stu-id="fea35-105">Group Policy objects section</span></span>


<span data-ttu-id="fea35-106">**组策略对象**部分显示组策略对象（gpo）的筛选列表，并标识每个 GPO 的以下属性：</span><span class="sxs-lookup"><span data-stu-id="fea35-106">The **Group Policy objects** section displays a filtered list of Group Policy Objects (GPOs) and identifies the following attributes for each GPO:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="fea35-107">GPO 属性</span><span class="sxs-lookup"><span data-stu-id="fea35-107">GPO attribute</span></span></th>
<th align="left"><span data-ttu-id="fea35-108">描述</span><span class="sxs-lookup"><span data-stu-id="fea35-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="fea35-109">名称</span><span class="sxs-lookup"><span data-stu-id="fea35-109">Name</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="fea35-110">GPO 的名称。</span><span class="sxs-lookup"><span data-stu-id="fea35-110">Name of the GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="fea35-111">State</span><span class="sxs-lookup"><span data-stu-id="fea35-111">State</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="fea35-112">所选 GPO 的状态</span><span class="sxs-lookup"><span data-stu-id="fea35-112">The state of the selected GPO</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="fea35-113">更改者</span><span class="sxs-lookup"><span data-stu-id="fea35-113">Changed By</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="fea35-114">已签入或已部署选定 GPO 的审批者的编辑者。</span><span class="sxs-lookup"><span data-stu-id="fea35-114">The Editor who checked in or the Approver who deployed the selected GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="fea35-115">更改日期</span><span class="sxs-lookup"><span data-stu-id="fea35-115">Change Date</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="fea35-116">对于受控 GPO，在修改或签出后将其签入的最新日期。</span><span class="sxs-lookup"><span data-stu-id="fea35-116">For a controlled GPO, the most recent date it was checked in after being modified or checked out to be modified.</span></span> <span data-ttu-id="fea35-117">对于不受控制的 GPO，为其上次修改的日期。</span><span class="sxs-lookup"><span data-stu-id="fea35-117">For an uncontrolled GPO, the date when it was last modified.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="fea35-118">评论</span><span class="sxs-lookup"><span data-stu-id="fea35-118">Comment</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="fea35-119">在修改时由签入或部署 GPO 的人员输入的注释。</span><span class="sxs-lookup"><span data-stu-id="fea35-119">A comment entered by the person who checked in or deployed a GPO at the time that it was modified.</span></span> <span data-ttu-id="fea35-120">在需要回滚到以前版本的情况下，用于识别版本的详细信息。</span><span class="sxs-lookup"><span data-stu-id="fea35-120">Useful for identifying the specifics of the version in case of the need to roll back to a previous version.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="fea35-121">计算机版本</span><span class="sxs-lookup"><span data-stu-id="fea35-121">Computer Version</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="fea35-122">GPO 的计算机配置部分的自动生成的版本。</span><span class="sxs-lookup"><span data-stu-id="fea35-122">Automatically generated version of the Computer Configuration portion of the GPO.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="fea35-123">用户版本</span><span class="sxs-lookup"><span data-stu-id="fea35-123">User Version</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="fea35-124">GPO 的用户配置部分的自动生成的版本。</span><span class="sxs-lookup"><span data-stu-id="fea35-124">Automatically generated version of the User Configuration portion of the GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="fea35-125">GPO 状态</span><span class="sxs-lookup"><span data-stu-id="fea35-125">GPO Status</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="fea35-126">计算机配置和用户配置可以单独管理。</span><span class="sxs-lookup"><span data-stu-id="fea35-126">The Computer Configuration and the User Configuration can be managed separately.</span></span> <span data-ttu-id="fea35-127">GPO 状态表示启用了 GPO 的哪些部分。</span><span class="sxs-lookup"><span data-stu-id="fea35-127">The GPO Status indicates which portions of the GPO are enabled.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="fea35-128">WMI 筛选器</span><span class="sxs-lookup"><span data-stu-id="fea35-128">WMI Filter</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="fea35-129">显示应用到此 GPO 的任何 WMI 筛选器。</span><span class="sxs-lookup"><span data-stu-id="fea35-129">Display any WMI filters that are applied to this GPO.</span></span> <span data-ttu-id="fea35-130">WMI 筛选器在 GPMC 的 <strong> </strong> 控制台树中的域的 Wmi 筛选器文件夹下进行管理。</span><span class="sxs-lookup"><span data-stu-id="fea35-130">WMI filters are managed under the <strong>WMI Filters</strong> folder for the domain in the console tree of the GPMC.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="fea35-131">组和用户部分</span><span class="sxs-lookup"><span data-stu-id="fea35-131">Groups and Users section</span></span>


<span data-ttu-id="fea35-132">选择 GPO 时，"**组和用户**" 部分将显示有权访问该 GPO 的组和用户的列表。</span><span class="sxs-lookup"><span data-stu-id="fea35-132">When a GPO is selected, the **Groups and Users** section displays a list of the groups and users with access to that GPO.</span></span> <span data-ttu-id="fea35-133">为每个组或用户显示允许的权限和继承。</span><span class="sxs-lookup"><span data-stu-id="fea35-133">The allowed permissions and inheritance are displayed for each group or user.</span></span> <span data-ttu-id="fea35-134">AGPM 管理员可以使用标准 AGPM 角色（编辑、审批者、审阅者和 AGPM 管理员）或自定义权限组合配置权限。</span><span class="sxs-lookup"><span data-stu-id="fea35-134">An AGPM Administrator can configure permissions using either standard AGPM roles (Editor, Approver, Reviewer, and AGPM Administrator) or a customized combination of permissions.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="fea35-135">按钮</span><span class="sxs-lookup"><span data-stu-id="fea35-135">Button</span></span></th>
<th align="left"><span data-ttu-id="fea35-136">作用</span><span class="sxs-lookup"><span data-stu-id="fea35-136">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="fea35-137">添加</span><span class="sxs-lookup"><span data-stu-id="fea35-137">Add</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="fea35-138">将新条目添加到安全描述符中。</span><span class="sxs-lookup"><span data-stu-id="fea35-138">Add a new entry to the security descriptor.</span></span> <span data-ttu-id="fea35-139">可以添加 Active Directory 中的任何用户或组。</span><span class="sxs-lookup"><span data-stu-id="fea35-139">Any user or group in Active Directory can be added.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="fea35-140">删除</span><span class="sxs-lookup"><span data-stu-id="fea35-140">Remove</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="fea35-141">从 "访问控制列表" 中删除所选条目。</span><span class="sxs-lookup"><span data-stu-id="fea35-141">Remove the selected entry from the Access Control List.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="fea35-142">属性</span><span class="sxs-lookup"><span data-stu-id="fea35-142">Properties</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="fea35-143">显示所选对象的属性。</span><span class="sxs-lookup"><span data-stu-id="fea35-143">Display the properties for the selected object.</span></span> <span data-ttu-id="fea35-144">"属性" 页面与 <strong> Active Directory 用户和计算机中的对象显示的属性相同 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="fea35-144">The properties page is the same one displayed for an object in <strong>Active Directory Users and Computers</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="fea35-145">高级</span><span class="sxs-lookup"><span data-stu-id="fea35-145">Advanced</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="fea35-146">打开 " <strong> 访问控制列表编辑器" </strong> 。</span><span class="sxs-lookup"><span data-stu-id="fea35-146">Open the <strong>Access Control List Editor</strong>.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="fea35-147">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="fea35-147">Additional considerations</span></span>

-   <span data-ttu-id="fea35-148">有关与特定任务相关的角色和权限的信息，请参阅[执行 AGPM 管理员任务](performing-agpm-administrator-tasks-agpm30ops.md)、[执行编辑任务](performing-editor-tasks-agpm30ops.md)、[执行审批者任务](performing-approver-tasks-agpm30ops.md)和[执行审阅者任务](performing-reviewer-tasks-agpm30ops.md)中的任务。</span><span class="sxs-lookup"><span data-stu-id="fea35-148">For information about roles and permissions related to specific tasks, see the tasks under [Performing AGPM Administrator Tasks](performing-agpm-administrator-tasks-agpm30ops.md), [Performing Editor Tasks](performing-editor-tasks-agpm30ops.md), [Performing Approver Tasks](performing-approver-tasks-agpm30ops.md), and [Performing Reviewer Tasks](performing-reviewer-tasks-agpm30ops.md).</span></span>

### <span data-ttu-id="fea35-149">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="fea35-149">Additional references</span></span>

-   [<span data-ttu-id="fea35-150">“内容”选项卡</span><span class="sxs-lookup"><span data-stu-id="fea35-150">Contents Tab</span></span>](contents-tab-agpm30ops.md)

 

 





