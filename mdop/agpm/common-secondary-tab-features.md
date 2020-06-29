---
title: “常用辅助项”选项卡功能
description: “常用辅助项”选项卡功能
author: dansimp
ms.assetid: 44a15c28-944c-49c1-8534-115ce1c362ed
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 546fd4c91e060a5595b6c848015290882de933b6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802076"
---
# <span data-ttu-id="186ec-103">“常用辅助项”选项卡功能</span><span class="sxs-lookup"><span data-stu-id="186ec-103">Common Secondary Tab Features</span></span>


<span data-ttu-id="186ec-104">每个辅助选项卡包含两个部分：**组策略对象**和**组以及用户**。</span><span class="sxs-lookup"><span data-stu-id="186ec-104">Each secondary tab has two sections—**Group Policy objects** and **Groups and Users**.</span></span>

## <span data-ttu-id="186ec-105">组策略对象部分</span><span class="sxs-lookup"><span data-stu-id="186ec-105">Group Policy objects section</span></span>


<span data-ttu-id="186ec-106">**组策略对象**部分显示组策略对象（gpo）的筛选列表，并标识每个 GPO 的以下特征：</span><span class="sxs-lookup"><span data-stu-id="186ec-106">The **Group Policy objects** section displays a filtered list of Group Policy objects (GPOs) and identifies the following characteristics for each GPO:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="186ec-107">GPO 特性</span><span class="sxs-lookup"><span data-stu-id="186ec-107">GPO Characteristic</span></span></th>
<th align="left"><span data-ttu-id="186ec-108">描述</span><span class="sxs-lookup"><span data-stu-id="186ec-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="186ec-109">名称</span><span class="sxs-lookup"><span data-stu-id="186ec-109">Name</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="186ec-110">组策略对象的名称。</span><span class="sxs-lookup"><span data-stu-id="186ec-110">Name of the Group Policy object.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="186ec-111">计算机（Comp）</span><span class="sxs-lookup"><span data-stu-id="186ec-111">Computer (Comp.)</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="186ec-112">GPO 的计算机配置部分的自动生成的版本。</span><span class="sxs-lookup"><span data-stu-id="186ec-112">Automatically generated version of the Computer Configuration portion of the GPO.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="186ec-113">用户</span><span class="sxs-lookup"><span data-stu-id="186ec-113">User</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="186ec-114">GPO 的用户配置部分的自动生成的版本。</span><span class="sxs-lookup"><span data-stu-id="186ec-114">Automatically generated version of the User Configuration portion of the GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="186ec-115">State</span><span class="sxs-lookup"><span data-stu-id="186ec-115">State</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="186ec-116">所选 GPO 的状态：</span><span class="sxs-lookup"><span data-stu-id="186ec-116">The state of the selected GPO:</span></span></p>
<p><img src="images/36f6b687-f5cc-40d1-805f-b191d1fb1ace.gif" alt="Deployed GPO icon" /> <strong><span data-ttu-id="186ec-117">不受控制： </strong> 不由 AGPM 托管。</span><span class="sxs-lookup"><span data-stu-id="186ec-117">Uncontrolled:</strong> Not managed by AGPM.</span></span></p>
<p><img src="images/57b610a5-1c71-4d26-9173-d04abd495fcc.gif" alt="Checked in GPO icon" /> <strong><span data-ttu-id="186ec-118">已签入： </strong> 可供授权编辑人员签出以进行编辑或组策略管理员进行部署。</span><span class="sxs-lookup"><span data-stu-id="186ec-118">Checked In:</strong> Available for authorized Editors to check out for editing or for a Group Policy administrator to deploy.</span></span></p>
<p><img src="images/8e7a7c4e-809a-435a-8b29-30d797936210.gif" alt="Checked out GPO icon" /> <strong><span data-ttu-id="186ec-119">已签出： </strong> 当前正在编辑。</span><span class="sxs-lookup"><span data-stu-id="186ec-119">Checked Out:</strong> Currently being edited.</span></span> <span data-ttu-id="186ec-120">在签出的编辑者或 AGPM 管理员将其签入之前，不能查看其他编辑器。</span><span class="sxs-lookup"><span data-stu-id="186ec-120">Unavailable for other Editors to check out until the Editor who checked it out or an AGPM Administrator checks it in.</span></span></p>
<p><img src="images/0840a6a3-54a6-4528-98a9-7b122243c1a5.gif" alt="Pending GPO icon" /> <strong><span data-ttu-id="186ec-121">挂起：在 </strong> 创建、控制、部署或删除组之前，等待组策略管理员批准。</span><span class="sxs-lookup"><span data-stu-id="186ec-121">Pending:</strong> Awaiting approval from a Group Policy administrator before being created, controlled, deployed, or deleted.</span></span></p>
<p><img src="images/57b610a5-1c71-4d26-9173-d04abd495fcc.gif" alt="Checked in GPO icon" /> <strong><span data-ttu-id="186ec-122">已删除： </strong> 从存档中删除，但仍可以还原。</span><span class="sxs-lookup"><span data-stu-id="186ec-122">Deleted:</strong> Deleted from the archive, but still able to be restored.</span></span></p>
<p><img src="images/9b65829d-253c-4f30-9295-c816a6521ed2.gif" alt="Template icon" /> <strong><span data-ttu-id="186ec-123">模板：在 </strong> 创建新 gpo 时用作起点的 GPO 的静态版本。</span><span class="sxs-lookup"><span data-stu-id="186ec-123">Template:</strong> A static version of a GPO for use as a starting point when creating new GPOs.</span></span></p>
<p><img src="images/cd349b8d-c4d8-45ff-b17f-7db882502c58.gif" alt="Default template icon" /> <strong><span data-ttu-id="186ec-124">模板（默认）： </strong> 默认情况下，此模板是创建新 GPO 时使用的起始点。</span><span class="sxs-lookup"><span data-stu-id="186ec-124">Template (default):</strong> By default, this template is the starting point used when creating a new GPO.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="186ec-125">GPO 状态</span><span class="sxs-lookup"><span data-stu-id="186ec-125">GPO Status</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="186ec-126">计算机配置和用户配置可以单独管理。</span><span class="sxs-lookup"><span data-stu-id="186ec-126">The Computer Configuration and the User Configuration can be managed separately.</span></span> <span data-ttu-id="186ec-127">GPO 状态表示启用了 GPO 的哪些部分。</span><span class="sxs-lookup"><span data-stu-id="186ec-127">The GPO Status indicates which portions of the GPO are enabled.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="186ec-128">WMI 筛选器</span><span class="sxs-lookup"><span data-stu-id="186ec-128">WMI Filter</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="186ec-129">显示应用到此 GPO 的任何 WMI 筛选器。</span><span class="sxs-lookup"><span data-stu-id="186ec-129">Display any WMI filters that are applied to this GPO.</span></span> <span data-ttu-id="186ec-130">WMI 筛选器在 GPMC 的 <strong> </strong> 控制台树中的域的 Wmi 筛选器节点下进行管理。</span><span class="sxs-lookup"><span data-stu-id="186ec-130">WMI filters are managed under the <strong>WMI Filters</strong> node for the domain in the console tree of the GPMC.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="186ec-131">修改日期</span><span class="sxs-lookup"><span data-stu-id="186ec-131">Modified</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="186ec-132">对于受控制的 GPO，在修改或签出后将其签入以进行修改的最新日期。</span><span class="sxs-lookup"><span data-stu-id="186ec-132">For a controlled GPO, the most recent date when it was checked in after being modified or checked out to be modified.</span></span> <span data-ttu-id="186ec-133">对于不受控制的 GPO，为其上次修改的日期。</span><span class="sxs-lookup"><span data-stu-id="186ec-133">For an uncontrolled GPO, the date when it was last modified.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="186ec-134">所有者</span><span class="sxs-lookup"><span data-stu-id="186ec-134">Owner</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="186ec-135">已签入或已部署选定 GPO 的审批者的编辑者。</span><span class="sxs-lookup"><span data-stu-id="186ec-135">The Editor who checked in or the Approver who deployed the selected GPO.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="186ec-136">组和用户部分</span><span class="sxs-lookup"><span data-stu-id="186ec-136">Groups and Users section</span></span>


<span data-ttu-id="186ec-137">选择 GPO 时，"**组和用户**" 部分将显示有权访问该 GPO 的组和用户的列表。</span><span class="sxs-lookup"><span data-stu-id="186ec-137">When a GPO is selected, the **Groups and Users** section displays a list of the groups and users with access to that GPO.</span></span> <span data-ttu-id="186ec-138">为每个组或用户显示允许的权限和继承。</span><span class="sxs-lookup"><span data-stu-id="186ec-138">The allowed permissions and inheritance are displayed for each group or user.</span></span> <span data-ttu-id="186ec-139">AGPM 管理员可以使用标准 AGPM 角色（编辑者、审批者和审阅者）或自定义权限组合配置权限。</span><span class="sxs-lookup"><span data-stu-id="186ec-139">An AGPM Administrator can configure permissions using either standard AGPM roles (Editor, Approver, and Reviewer) or a customized combination of permissions.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="186ec-140">按钮</span><span class="sxs-lookup"><span data-stu-id="186ec-140">Button</span></span></th>
<th align="left"><span data-ttu-id="186ec-141">作用</span><span class="sxs-lookup"><span data-stu-id="186ec-141">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="186ec-142">添加</span><span class="sxs-lookup"><span data-stu-id="186ec-142">Add</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="186ec-143">将新条目添加到安全描述符中。</span><span class="sxs-lookup"><span data-stu-id="186ec-143">Add a new entry to the security descriptor.</span></span> <span data-ttu-id="186ec-144">可以添加 Active Directory 中的任何用户或组。</span><span class="sxs-lookup"><span data-stu-id="186ec-144">Any user or group in Active Directory can be added.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="186ec-145">删除</span><span class="sxs-lookup"><span data-stu-id="186ec-145">Remove</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="186ec-146">从 "访问控制列表" 中删除所选条目。</span><span class="sxs-lookup"><span data-stu-id="186ec-146">Remove the selected entry from the Access Control List.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="186ec-147">属性</span><span class="sxs-lookup"><span data-stu-id="186ec-147">Properties</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="186ec-148">显示所选对象的属性。</span><span class="sxs-lookup"><span data-stu-id="186ec-148">Display the properties for the selected object.</span></span> <span data-ttu-id="186ec-149">"属性" 页面与 <strong> Active Directory 用户和计算机中的对象显示的属性相同 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="186ec-149">The properties page is the same one displayed for an object in <strong>Active Directory Users and Computers</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="186ec-150">高级</span><span class="sxs-lookup"><span data-stu-id="186ec-150">Advanced</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="186ec-151">打开 " <strong> 访问控制列表编辑器" </strong> 。</span><span class="sxs-lookup"><span data-stu-id="186ec-151">Open the <strong>Access Control List Editor</strong>.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="186ec-152">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="186ec-152">Additional considerations</span></span>

-   <span data-ttu-id="186ec-153">有关与特定任务相关的角色和权限的信息，请参阅[执行 AGPM 管理员任务](performing-agpm-administrator-tasks.md)、[执行编辑任务](performing-editor-tasks.md)、[执行审批者任务](performing-approver-tasks.md)和[执行审阅者任务](performing-reviewer-tasks.md)中的任务。</span><span class="sxs-lookup"><span data-stu-id="186ec-153">For information about roles and permissions related to specific tasks, see the tasks under [Performing AGPM Administrator Tasks](performing-agpm-administrator-tasks.md), [Performing Editor Tasks](performing-editor-tasks.md), [Performing Approver Tasks](performing-approver-tasks.md), and [Performing Reviewer Tasks](performing-reviewer-tasks.md).</span></span>

### <span data-ttu-id="186ec-154">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="186ec-154">Additional references</span></span>

-   [<span data-ttu-id="186ec-155">“内容”选项卡</span><span class="sxs-lookup"><span data-stu-id="186ec-155">Contents Tab</span></span>](contents-tab.md)

 

 





