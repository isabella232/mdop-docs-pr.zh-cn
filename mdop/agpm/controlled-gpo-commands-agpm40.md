---
title: 受控 GPO 命令
description: 受控 GPO 命令
author: dansimp
ms.assetid: 370d3db9-4efc-4799-983d-e29ba5f32b07
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 65e9d06beb4c36762e845e452bab497a8d3da747
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802888"
---
# <span data-ttu-id="9808e-103">受控 GPO 命令</span><span class="sxs-lookup"><span data-stu-id="9808e-103">Controlled GPO Commands</span></span>


<span data-ttu-id="9808e-104">"**受控**" 选项卡：</span><span class="sxs-lookup"><span data-stu-id="9808e-104">The **Controlled** tab:</span></span>

-   <span data-ttu-id="9808e-105">显示由高级组策略管理（AGPM）管理的组策略对象（Gpo）的列表。</span><span class="sxs-lookup"><span data-stu-id="9808e-105">Displays a list of Group Policy Objects (GPOs) managed by Advanced Group Policy Management (AGPM).</span></span>

-   <span data-ttu-id="9808e-106">提供快捷菜单，其中包含用于管理 Gpo 的命令和用于显示 Gpo 的历史记录和报告的命令。</span><span class="sxs-lookup"><span data-stu-id="9808e-106">Provides a shortcut menu with commands for managing GPOs and for displaying the history and reports for GPOs.</span></span>

-   <span data-ttu-id="9808e-107">显示具有访问选定 GPO 的权限的组和用户的列表。</span><span class="sxs-lookup"><span data-stu-id="9808e-107">Displays a list of the groups and users who have permission to access a selected GPO.</span></span>

<span data-ttu-id="9808e-108">右键单击此选项卡上的 "**组策略对象**" 列表，显示快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="9808e-108">Right-clicking the **Group Policy Objects** list on this tab displays a shortcut menu.</span></span> <span data-ttu-id="9808e-109">此菜单包含以下任何适用选项。</span><span class="sxs-lookup"><span data-stu-id="9808e-109">This menu includes whichever of the following options are applicable.</span></span>

## <span data-ttu-id="9808e-110">控件和历史记录</span><span class="sxs-lookup"><span data-stu-id="9808e-110">Control and history</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="9808e-111">命令</span><span class="sxs-lookup"><span data-stu-id="9808e-111">Command</span></span></th>
<th align="left"><span data-ttu-id="9808e-112">作用</span><span class="sxs-lookup"><span data-stu-id="9808e-112">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="9808e-113">新的受控 GPO</span><span class="sxs-lookup"><span data-stu-id="9808e-113">New Controlled GPO</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="9808e-114">通过 AGPM 管理更改控制来创建新的 GPO，并将其部署到域的生产环境中。</span><span class="sxs-lookup"><span data-stu-id="9808e-114">Create a new GPO with change control managed through AGPM and deploy it to the production environment of the domain.</span></span> <span data-ttu-id="9808e-115">如果你没有创建 GPO 的权限，系统将提示你提交请求。</span><span class="sxs-lookup"><span data-stu-id="9808e-115">If you do not have permission to create a GPO, you are prompted to submit a request.</span></span> <span data-ttu-id="9808e-116">（如果右键单击 <strong> 时未选择任何 GPO，则显示此选项组策略对象 </strong> 列表。）</span><span class="sxs-lookup"><span data-stu-id="9808e-116">(This option is displayed if no GPO is selected when right-clicking in the <strong>Group Policy Objects</strong> list.)</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="9808e-117">历史记录</span><span class="sxs-lookup"><span data-stu-id="9808e-117">History</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="9808e-118">打开一个窗口，列出存档中保存的选定 GPO 的所有版本。</span><span class="sxs-lookup"><span data-stu-id="9808e-118">Open a window listing all versions of the selected GPO saved within the archive.</span></span> <span data-ttu-id="9808e-119">从历史记录中，你可以获取 GPO 中的设置报告、比较 GPO 的两个版本、将 GPO 与模板进行比较或回退到早期版本的 GPO。</span><span class="sxs-lookup"><span data-stu-id="9808e-119">From the history, you can obtain a report of the settings within a GPO, compare two versions of a GPO, compare a GPO to a template, or roll back to an earlier version of a GPO.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="9808e-120">报告</span><span class="sxs-lookup"><span data-stu-id="9808e-120">Reports</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="9808e-121">命令</span><span class="sxs-lookup"><span data-stu-id="9808e-121">Command</span></span></th>
<th align="left"><span data-ttu-id="9808e-122">作用</span><span class="sxs-lookup"><span data-stu-id="9808e-122">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="9808e-123">设置</span><span class="sxs-lookup"><span data-stu-id="9808e-123">Settings</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="9808e-124">生成基于 HTML 或基于 XML 的报表，显示所选 GPO 中的设置，或显示从组织单位到 GPO 最近控制、导入或签入时的选定 GPO 的链接。</span><span class="sxs-lookup"><span data-stu-id="9808e-124">Generate an HTML-based or XML-based report displaying the settings within the selected GPO or display links to the selected GPO(s) from organizational units as of when the GPO(s) was most recently controlled, imported, or checked in.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="9808e-125">不同之处</span><span class="sxs-lookup"><span data-stu-id="9808e-125">Differences</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="9808e-126">生成用于比较两个选定 Gpo 或所选 GPO 和模板内的设置的基于 HTML 或基于 XML 的报表。</span><span class="sxs-lookup"><span data-stu-id="9808e-126">Generate an HTML-based or XML-based report comparing the settings within two selected GPOs or within the selected GPO and a template.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="9808e-127">编辑</span><span class="sxs-lookup"><span data-stu-id="9808e-127">Editing</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="9808e-128">命令</span><span class="sxs-lookup"><span data-stu-id="9808e-128">Command</span></span></th>
<th align="left"><span data-ttu-id="9808e-129">作用</span><span class="sxs-lookup"><span data-stu-id="9808e-129">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="9808e-130">编辑</span><span class="sxs-lookup"><span data-stu-id="9808e-130">Edit</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="9808e-131">打开 <strong> 组策略管理编辑器 </strong> 窗口，更改所选 GPO。</span><span class="sxs-lookup"><span data-stu-id="9808e-131">Open the <strong>Group Policy Management Editor</strong> window to change the selected GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="9808e-132">退房</span><span class="sxs-lookup"><span data-stu-id="9808e-132">Check Out</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="9808e-133">从存档中获取所选 GPO 的副本，以便脱机编辑，并禁止任何其他人编辑 GPO，直到将其签回存档。</span><span class="sxs-lookup"><span data-stu-id="9808e-133">Obtain a copy of the selected GPO from the archive for offline editing and prohibit anyone else from editing the GPO until it is checked back into the archive.</span></span> <span data-ttu-id="9808e-134">签出可由 AGPM 管理员（完全控制）替代。</span><span class="sxs-lookup"><span data-stu-id="9808e-134">Check Out can be overridden by an AGPM Administrator (Full Control).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="9808e-135">登记</span><span class="sxs-lookup"><span data-stu-id="9808e-135">Check In</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="9808e-136">将所选 GPO 的已编辑版本签入存档，以便其他授权的编辑人员可以进行更改，或者审批者可以将 GPO 部署到域的生产环境。</span><span class="sxs-lookup"><span data-stu-id="9808e-136">Check the edited version of the selected GPO into the archive, so other authorized Editors can make changes or an Approver can deploy the GPO to the production environment of the domain.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="9808e-137">撤消签出</span><span class="sxs-lookup"><span data-stu-id="9808e-137">Undo Check Out</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="9808e-138">将已签出的 GPO 返回到存档，不进行任何更改。</span><span class="sxs-lookup"><span data-stu-id="9808e-138">Return a checked out GPO to the archive without any changes.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="9808e-139">版本管理</span><span class="sxs-lookup"><span data-stu-id="9808e-139">Version management</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="9808e-140">命令</span><span class="sxs-lookup"><span data-stu-id="9808e-140">Command</span></span></th>
<th align="left"><span data-ttu-id="9808e-141">作用</span><span class="sxs-lookup"><span data-stu-id="9808e-141">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="9808e-142">从生产导入</span><span class="sxs-lookup"><span data-stu-id="9808e-142">Import from Production</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="9808e-143">对于选定的 GPO，将域的生产环境中的版本复制到存档。</span><span class="sxs-lookup"><span data-stu-id="9808e-143">For the selected GPO, copy the version in the production environment of the domain to the archive.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="9808e-144">从文件导入</span><span class="sxs-lookup"><span data-stu-id="9808e-144">Import from File</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="9808e-145">将所选的已签出 GPO 的策略设置替换为 GPO 备份文件中的 GPO。</span><span class="sxs-lookup"><span data-stu-id="9808e-145">Replace the policy settings of the selected, checked-out GPO with those from a GPO backup file.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="9808e-146">删除</span><span class="sxs-lookup"><span data-stu-id="9808e-146">Delete</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="9808e-147">将所选 GPO 移动到回收站，并指示是否在生产中保留已部署的版本（如果存在），或者删除已部署的版本以及存档中的版本。</span><span class="sxs-lookup"><span data-stu-id="9808e-147">Move the selected GPO to the Recycle Bin and indicate whether to leave the deployed version (if one exists) in production or to delete the deployed version in addition to the version in the archive.</span></span> <span data-ttu-id="9808e-148">如果你没有删除 GPO 的权限，系统将提示你提交请求。</span><span class="sxs-lookup"><span data-stu-id="9808e-148">If you do not have permission to delete a GPO, you are prompted to submit a request.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="9808e-149">部署</span><span class="sxs-lookup"><span data-stu-id="9808e-149">Deploy</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="9808e-150">将已签入存档的选定 GPO 移动到域的生产环境中。</span><span class="sxs-lookup"><span data-stu-id="9808e-150">Move the selected GPO that is checked into the archive to the production environment of the domain.</span></span> <span data-ttu-id="9808e-151">此操作将使其在网络上处于活动状态，并覆盖以前活动版本的 GPO （如果存在）。</span><span class="sxs-lookup"><span data-stu-id="9808e-151">This action makes it active on the network and overwrites the previously active version of the GPO if one existed.</span></span> <span data-ttu-id="9808e-152">如果你没有部署 GPO 的权限，系统将提示你提交请求。</span><span class="sxs-lookup"><span data-stu-id="9808e-152">If you do not have permission to deploy a GPO, you will be prompted to submit a request.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="9808e-153">导出到</span><span class="sxs-lookup"><span data-stu-id="9808e-153">Export to</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="9808e-154">将所选 GPO 保存到备份文件，以便可以将其复制到其他域。</span><span class="sxs-lookup"><span data-stu-id="9808e-154">Save the selected GPO to a backup file so that you can copy it to another domain.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="9808e-155">标签</span><span class="sxs-lookup"><span data-stu-id="9808e-155">Label</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="9808e-156">将所选 GPO 标记为描述性标签（如 " &quot; 已知正常" &quot; ），并使用注释保留记录。</span><span class="sxs-lookup"><span data-stu-id="9808e-156">Mark the selected GPO with a descriptive label (such as &quot;Known good&quot;) and comment for record keeping.</span></span> <span data-ttu-id="9808e-157">标签显示在 " <strong> 状态" </strong> 列中，注释显示在 <strong> </strong> " <strong> 历史记录" 窗口 </strong> 的 "备注" 列中。</span><span class="sxs-lookup"><span data-stu-id="9808e-157">Labels appear in the <strong>State</strong> column and comments in the <strong>Comment</strong> column of the <strong>History</strong> window.</span></span> <span data-ttu-id="9808e-158">它们帮助你识别 GPO 的早期版本，以便你可以在出现问题时回滚。</span><span class="sxs-lookup"><span data-stu-id="9808e-158">They help you identify earlier versions of a GPO so that you can roll back if a problem occurs.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="9808e-159">重命名</span><span class="sxs-lookup"><span data-stu-id="9808e-159">Rename</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="9808e-160">更改所选 GPO 的名称。</span><span class="sxs-lookup"><span data-stu-id="9808e-160">Change the name of the selected GPO.</span></span> <span data-ttu-id="9808e-161">如果 GPO 已部署，则重新部署 GPO 时，将在域的生产环境中更新该名称。</span><span class="sxs-lookup"><span data-stu-id="9808e-161">If the GPO has already been deployed, the name will be updated in the production environment of the domain when the GPO is redeployed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="9808e-162">另存为模板</span><span class="sxs-lookup"><span data-stu-id="9808e-162">Save as Template</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="9808e-163">基于所选 GPO 的设置创建新模板。</span><span class="sxs-lookup"><span data-stu-id="9808e-163">Create a new template based on the settings of the selected GPO.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="9808e-164">杂项</span><span class="sxs-lookup"><span data-stu-id="9808e-164">Miscellaneous</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="9808e-165">命令</span><span class="sxs-lookup"><span data-stu-id="9808e-165">Command</span></span></th>
<th align="left"><span data-ttu-id="9808e-166">作用</span><span class="sxs-lookup"><span data-stu-id="9808e-166">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="9808e-167">刷新</span><span class="sxs-lookup"><span data-stu-id="9808e-167">Refresh</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="9808e-168">更新组策略管理控制台（GPMC）的显示以合并任何更改。</span><span class="sxs-lookup"><span data-stu-id="9808e-168">Update the display of the Group Policy Management Console (GPMC) to incorporate any changes.</span></span> <span data-ttu-id="9808e-169">在刷新显示之前，某些更改不可见。</span><span class="sxs-lookup"><span data-stu-id="9808e-169">Some changes are not visible until the display is refreshed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="9808e-170">帮助</span><span class="sxs-lookup"><span data-stu-id="9808e-170">Help</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="9808e-171">显示 AGPM 的帮助。</span><span class="sxs-lookup"><span data-stu-id="9808e-171">Display help for AGPM.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="9808e-172">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="9808e-172">Additional references</span></span>

-   [<span data-ttu-id="9808e-173">“内容”选项卡</span><span class="sxs-lookup"><span data-stu-id="9808e-173">Contents Tab</span></span>](contents-tab-agpm40.md)

-   [<span data-ttu-id="9808e-174">执行编辑者任务</span><span class="sxs-lookup"><span data-stu-id="9808e-174">Performing Editor Tasks</span></span>](performing-editor-tasks-agpm40.md)

-   [<span data-ttu-id="9808e-175">执行审批者任务</span><span class="sxs-lookup"><span data-stu-id="9808e-175">Performing Approver Tasks</span></span>](performing-approver-tasks-agpm40.md)

-   [<span data-ttu-id="9808e-176">执行审阅者任务</span><span class="sxs-lookup"><span data-stu-id="9808e-176">Performing Reviewer Tasks</span></span>](performing-reviewer-tasks-agpm40.md)

 

 





