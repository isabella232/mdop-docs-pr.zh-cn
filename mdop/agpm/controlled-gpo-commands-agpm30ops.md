---
title: 受控 GPO 命令
description: 受控 GPO 命令
author: dansimp
ms.assetid: 82db4772-154a-4a8d-99cd-2c69e1738698
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8e537751107a2796727e5ed71511649b6bce953a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801992"
---
# <span data-ttu-id="fd836-103">受控 GPO 命令</span><span class="sxs-lookup"><span data-stu-id="fd836-103">Controlled GPO Commands</span></span>


<span data-ttu-id="fd836-104">"**受控**" 选项卡：</span><span class="sxs-lookup"><span data-stu-id="fd836-104">The **Controlled** tab:</span></span>

-   <span data-ttu-id="fd836-105">显示由高级组策略管理（AGPM）管理的组策略对象（Gpo）的列表。</span><span class="sxs-lookup"><span data-stu-id="fd836-105">Displays a list of Group Policy Objects (GPOs) managed by Advanced Group Policy Management (AGPM).</span></span>

-   <span data-ttu-id="fd836-106">提供快捷菜单，其中包含用于管理 Gpo 的命令和用于显示 Gpo 的历史记录和报告的命令。</span><span class="sxs-lookup"><span data-stu-id="fd836-106">Provides a shortcut menu with commands for managing GPOs and for displaying the history and reports for GPOs.</span></span>

-   <span data-ttu-id="fd836-107">显示具有访问选定 GPO 的权限的组和用户的列表。</span><span class="sxs-lookup"><span data-stu-id="fd836-107">Displays a list of the groups and users who have permission to access a selected GPO.</span></span>

<span data-ttu-id="fd836-108">右键单击此选项卡上的 "**组策略对象**" 列表，将显示快捷菜单，包括以下任何适用选项。</span><span class="sxs-lookup"><span data-stu-id="fd836-108">Right-clicking the **Group Policy Objects** list on this tab displays a shortcut menu, including whichever of the following options are applicable.</span></span>

## <span data-ttu-id="fd836-109">控件和历史记录</span><span class="sxs-lookup"><span data-stu-id="fd836-109">Control and history</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="fd836-110">命令</span><span class="sxs-lookup"><span data-stu-id="fd836-110">Command</span></span></th>
<th align="left"><span data-ttu-id="fd836-111">作用</span><span class="sxs-lookup"><span data-stu-id="fd836-111">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="fd836-112">新的受控 GPO</span><span class="sxs-lookup"><span data-stu-id="fd836-112">New Controlled GPO</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="fd836-113">通过 AGPM 管理更改控制来创建新的 GPO 并将其部署到生产环境。</span><span class="sxs-lookup"><span data-stu-id="fd836-113">Create a new GPO with change control managed through AGPM and deploy it to the production environment.</span></span> <span data-ttu-id="fd836-114">如果你没有创建 GPO 的权限，系统将提示你提交请求。</span><span class="sxs-lookup"><span data-stu-id="fd836-114">If you do not have permission to create a GPO, you will be prompted to submit a request.</span></span> <span data-ttu-id="fd836-115">（如果右键单击 <strong> 时未选择任何 GPO，则显示此选项组策略对象 </strong> 列表。）</span><span class="sxs-lookup"><span data-stu-id="fd836-115">(This option is displayed if no GPO is selected when right-clicking in the <strong>Group Policy Objects</strong> list.)</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="fd836-116">历史记录</span><span class="sxs-lookup"><span data-stu-id="fd836-116">History</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="fd836-117">打开一个窗口，列出存档中保存的选定 GPO 的所有版本。</span><span class="sxs-lookup"><span data-stu-id="fd836-117">Open a window listing all versions of the selected GPO saved within the archive.</span></span> <span data-ttu-id="fd836-118">从历史记录中，你可以获取 GPO 中的设置报告、比较 GPO 的两个版本、将 GPO 与模板进行比较或回退到 GPO 的早期版本。</span><span class="sxs-lookup"><span data-stu-id="fd836-118">From the history, you can obtain a report of the settings within a GPO, compare two versions of a GPO, compare a GPO to a template, or roll back to a previous version of a GPO.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="fd836-119">报告</span><span class="sxs-lookup"><span data-stu-id="fd836-119">Reports</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="fd836-120">命令</span><span class="sxs-lookup"><span data-stu-id="fd836-120">Command</span></span></th>
<th align="left"><span data-ttu-id="fd836-121">作用</span><span class="sxs-lookup"><span data-stu-id="fd836-121">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="fd836-122">设置</span><span class="sxs-lookup"><span data-stu-id="fd836-122">Settings</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="fd836-123">生成基于 HTML 或基于 XML 的报表，显示所选 GPO 中的设置，或显示从组织单位到 GPO 最近控制、导入或签入时的选定 GPO 的链接。</span><span class="sxs-lookup"><span data-stu-id="fd836-123">Generate an HTML-based or XML-based report displaying the settings within the selected GPO or display links to the selected GPO(s) from organizational units as of when the GPO(s) was most recently controlled, imported, or checked in.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="fd836-124">不同之处</span><span class="sxs-lookup"><span data-stu-id="fd836-124">Differences</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="fd836-125">生成用于比较两个选定 Gpo 或所选 GPO 和模板内的设置的基于 HTML 或基于 XML 的报表。</span><span class="sxs-lookup"><span data-stu-id="fd836-125">Generate an HTML-based or XML-based report comparing the settings within two selected GPOs or within the selected GPO and a template.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="fd836-126">编辑</span><span class="sxs-lookup"><span data-stu-id="fd836-126">Editing</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="fd836-127">命令</span><span class="sxs-lookup"><span data-stu-id="fd836-127">Command</span></span></th>
<th align="left"><span data-ttu-id="fd836-128">作用</span><span class="sxs-lookup"><span data-stu-id="fd836-128">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="fd836-129">编辑</span><span class="sxs-lookup"><span data-stu-id="fd836-129">Edit</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="fd836-130">打开 <strong> 组策略管理编辑器 </strong> 窗口，对所选 GPO 进行更改。</span><span class="sxs-lookup"><span data-stu-id="fd836-130">Open the <strong>Group Policy Management Editor</strong> window to make changes to the selected GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="fd836-131">退房</span><span class="sxs-lookup"><span data-stu-id="fd836-131">Check Out</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="fd836-132">从存档中获取所选 GPO 的副本，以便脱机编辑，并禁止任何其他人编辑它，直到将其签回存档。</span><span class="sxs-lookup"><span data-stu-id="fd836-132">Obtain a copy of the selected GPO from the archive for offline editing and prohibit anyone else from editing it until it is checked back into the archive.</span></span> <span data-ttu-id="fd836-133">（签出可由 AGPM 管理员替代（"完全控制"）。）</span><span class="sxs-lookup"><span data-stu-id="fd836-133">(Check Out can be overridden by an AGPM Administrator (Full Control).)</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="fd836-134">登记</span><span class="sxs-lookup"><span data-stu-id="fd836-134">Check In</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="fd836-135">将所选 GPO 的已编辑版本签入存档，以便其他授权的编辑人员可以进行更改，或者审批者可以将其部署到生产环境。</span><span class="sxs-lookup"><span data-stu-id="fd836-135">Check the edited version of the selected GPO into the archive, so other authorized Editors can make changes or an Approver can deploy it to the production environment.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="fd836-136">撤消签出</span><span class="sxs-lookup"><span data-stu-id="fd836-136">Undo Check Out</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="fd836-137">将已签出的 GPO 返回到存档，不进行任何更改。</span><span class="sxs-lookup"><span data-stu-id="fd836-137">Return a checked out GPO to the archive without any changes.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="fd836-138">版本管理</span><span class="sxs-lookup"><span data-stu-id="fd836-138">Version management</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="fd836-139">命令</span><span class="sxs-lookup"><span data-stu-id="fd836-139">Command</span></span></th>
<th align="left"><span data-ttu-id="fd836-140">作用</span><span class="sxs-lookup"><span data-stu-id="fd836-140">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="fd836-141">从生产导入</span><span class="sxs-lookup"><span data-stu-id="fd836-141">Import from Production</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="fd836-142">对于选定的 GPO，将生产环境中的版本复制到存档。</span><span class="sxs-lookup"><span data-stu-id="fd836-142">For the selected GPO, copy the version in the production environment to the archive.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="fd836-143">删除</span><span class="sxs-lookup"><span data-stu-id="fd836-143">Delete</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="fd836-144">将所选 GPO 移动到回收站，并指示是否在生产中保留已部署的版本（如果存在），或者删除它以及存档中的版本。</span><span class="sxs-lookup"><span data-stu-id="fd836-144">Move the selected GPO to the Recycle Bin and indicate whether to leave the deployed version (if one exists) in production or to delete it as well as the version in the archive.</span></span> <span data-ttu-id="fd836-145">如果你没有删除 GPO 的权限，系统将提示你提交请求。</span><span class="sxs-lookup"><span data-stu-id="fd836-145">If you do not have permission to delete a GPO, you will be prompted to submit a request.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="fd836-146">部署</span><span class="sxs-lookup"><span data-stu-id="fd836-146">Deploy</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="fd836-147">将已签入存档的选定 GPO 移动到生产环境。</span><span class="sxs-lookup"><span data-stu-id="fd836-147">Move the selected GPO that is checked into the archive to the production environment.</span></span> <span data-ttu-id="fd836-148">此操作将使其在网络上处于活动状态，并覆盖以前活动版本的 GPO （如果存在）。</span><span class="sxs-lookup"><span data-stu-id="fd836-148">This action makes it active on the network and overwrites the previously active version of the GPO if one existed.</span></span> <span data-ttu-id="fd836-149">如果你没有部署 GPO 的权限，系统将提示你提交请求。</span><span class="sxs-lookup"><span data-stu-id="fd836-149">If you do not have permission to deploy a GPO, you will be prompted to submit a request.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="fd836-150">标签</span><span class="sxs-lookup"><span data-stu-id="fd836-150">Label</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="fd836-151">将所选 GPO 标记为描述性标签（如 " &quot; 已知正常" &quot; ），并使用注释保留记录。</span><span class="sxs-lookup"><span data-stu-id="fd836-151">Mark the selected GPO with a descriptive label (such as &quot;Known good&quot;) and comment for record keeping.</span></span> <span data-ttu-id="fd836-152">标签显示在 " <strong> 历史记录" 窗口的 "备注" 列中的 "状态" </strong> 列和注释中 <strong> </strong> <strong> </strong> ，使你能够轻松地识别使用特定标签标识的 GPO 的以前版本，以便你可以在出现问题时回滚。</span><span class="sxs-lookup"><span data-stu-id="fd836-152">Labels appear in the <strong>State</strong> column and comments in the <strong>Comment</strong> column of the <strong>History</strong> window, enabling you to easily identify previous versions of a GPO identified with a particular label, so you can roll back if a problem occurs.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="fd836-153">重命名</span><span class="sxs-lookup"><span data-stu-id="fd836-153">Rename</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="fd836-154">更改所选 GPO 的名称。</span><span class="sxs-lookup"><span data-stu-id="fd836-154">Change the name of the selected GPO.</span></span> <span data-ttu-id="fd836-155">如果 GPO 已部署，则重新部署 GPO 时，将在生产环境中更新该名称。</span><span class="sxs-lookup"><span data-stu-id="fd836-155">If the GPO has already been deployed, the name will be updated in the production environment when the GPO is redeployed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="fd836-156">另存为模板</span><span class="sxs-lookup"><span data-stu-id="fd836-156">Save as Template</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="fd836-157">基于所选 GPO 的设置创建新模板。</span><span class="sxs-lookup"><span data-stu-id="fd836-157">Create a new template based on the settings of the selected GPO.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="fd836-158">杂项</span><span class="sxs-lookup"><span data-stu-id="fd836-158">Miscellaneous</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="fd836-159">命令</span><span class="sxs-lookup"><span data-stu-id="fd836-159">Command</span></span></th>
<th align="left"><span data-ttu-id="fd836-160">作用</span><span class="sxs-lookup"><span data-stu-id="fd836-160">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="fd836-161">刷新</span><span class="sxs-lookup"><span data-stu-id="fd836-161">Refresh</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="fd836-162">更新组策略管理控制台（GPMC）的显示以合并任何更改。</span><span class="sxs-lookup"><span data-stu-id="fd836-162">Update the display of the Group Policy Management Console (GPMC) to incorporate any changes.</span></span> <span data-ttu-id="fd836-163">在刷新显示之前，某些更改不可见。</span><span class="sxs-lookup"><span data-stu-id="fd836-163">Some changes are not visible until the display is refreshed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="fd836-164">帮助</span><span class="sxs-lookup"><span data-stu-id="fd836-164">Help</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="fd836-165">显示 AGPM 的帮助。</span><span class="sxs-lookup"><span data-stu-id="fd836-165">Display help for AGPM.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="fd836-166">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="fd836-166">Additional references</span></span>

-   [<span data-ttu-id="fd836-167">“内容”选项卡</span><span class="sxs-lookup"><span data-stu-id="fd836-167">Contents Tab</span></span>](contents-tab-agpm30ops.md)

-   [<span data-ttu-id="fd836-168">执行编辑者任务</span><span class="sxs-lookup"><span data-stu-id="fd836-168">Performing Editor Tasks</span></span>](performing-editor-tasks-agpm30ops.md)

-   [<span data-ttu-id="fd836-169">执行审批者任务</span><span class="sxs-lookup"><span data-stu-id="fd836-169">Performing Approver Tasks</span></span>](performing-approver-tasks-agpm30ops.md)

-   [<span data-ttu-id="fd836-170">执行审阅者任务</span><span class="sxs-lookup"><span data-stu-id="fd836-170">Performing Reviewer Tasks</span></span>](performing-reviewer-tasks-agpm30ops.md)

 

 





