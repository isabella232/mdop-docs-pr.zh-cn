---
title: “模板”选项卡
description: “模板”选项卡
author: dansimp
ms.assetid: 5676e9f9-eb52-49e1-a55d-15c1059af368
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d7469ee72eb23903ddec66152f8cc5d59861dfc9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802511"
---
# <span data-ttu-id="5b91b-103">“模板”选项卡</span><span class="sxs-lookup"><span data-stu-id="5b91b-103">Templates Tab</span></span>


<span data-ttu-id="5b91b-104">"**模板**" 选项卡：</span><span class="sxs-lookup"><span data-stu-id="5b91b-104">The **Templates** tab:</span></span>

-   <span data-ttu-id="5b91b-105">显示可用于创建新组策略对象（Gpo）的可用模板列表。</span><span class="sxs-lookup"><span data-stu-id="5b91b-105">Displays a list of available templates that you can use to create new Group Policy objects (GPOs).</span></span>

-   <span data-ttu-id="5b91b-106">提供快捷菜单，其中包含基于所选模板创建 GPO、管理模板和显示模板报表的命令。</span><span class="sxs-lookup"><span data-stu-id="5b91b-106">Provides a shortcut menu with commands for creating a GPO based on a selected template, managing templates, and displaying reports for templates.</span></span>

-   <span data-ttu-id="5b91b-107">显示有权限访问所选模板的组和用户的列表。</span><span class="sxs-lookup"><span data-stu-id="5b91b-107">Displays a list of the groups and users who have permission to access a selected template.</span></span>

<span data-ttu-id="5b91b-108">由于模板不能更改，因此模板没有历史记录。</span><span class="sxs-lookup"><span data-stu-id="5b91b-108">Because a template cannot be altered, templates have no history.</span></span> <span data-ttu-id="5b91b-109">但是，与任何 GPO 版本一样，模板的设置可以与设置报告一起显示，也可以与具有差异报告的另一个 GPO 进行比较。</span><span class="sxs-lookup"><span data-stu-id="5b91b-109">However, like any GPO version, the settings of a template can be displayed with a settings report or compared to another GPO with a difference report.</span></span>

<span data-ttu-id="5b91b-110">**注意** 模板是 GPO 的不可编辑的静态版本，用作创建新的可编辑 Gpo 的起始点。</span><span class="sxs-lookup"><span data-stu-id="5b91b-110">**Note** A template is an uneditable, static version of a GPO for use as a starting point for creating new, editable GPOs.</span></span>

 

<span data-ttu-id="5b91b-111">右键单击此选项卡上的 "**组策略对象**" 列表，将显示快捷菜单，包括以下任何适用选项。</span><span class="sxs-lookup"><span data-stu-id="5b91b-111">Right-clicking the **Group Policy Objects** list on this tab displays a shortcut menu, including whichever of the following options are applicable.</span></span>

## <span data-ttu-id="5b91b-112">控件</span><span class="sxs-lookup"><span data-stu-id="5b91b-112">Control</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="5b91b-113">命令</span><span class="sxs-lookup"><span data-stu-id="5b91b-113">Command</span></span></th>
<th align="left"><span data-ttu-id="5b91b-114">作用</span><span class="sxs-lookup"><span data-stu-id="5b91b-114">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="5b91b-115">新的受控 GPO</span><span class="sxs-lookup"><span data-stu-id="5b91b-115">New Controlled GPO</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="5b91b-116">基于所选模板创建新的 GPO。</span><span class="sxs-lookup"><span data-stu-id="5b91b-116">Create a new GPO based on the selected template.</span></span> <span data-ttu-id="5b91b-117">提供了用于将新 GPO 部署到生产环境的选项。</span><span class="sxs-lookup"><span data-stu-id="5b91b-117">The option to deploy the new GPO to the production environment is provided.</span></span> <span data-ttu-id="5b91b-118">如果你没有创建 GPO 的权限，系统将提示你提交请求。</span><span class="sxs-lookup"><span data-stu-id="5b91b-118">If you do not have permission to create a GPO, you will be prompted to submit a request.</span></span> <span data-ttu-id="5b91b-119">（如果右键单击 <strong> 时未选择任何 GPO，则显示此选项组策略对象 </strong> 列表。）</span><span class="sxs-lookup"><span data-stu-id="5b91b-119">(This option is displayed if no GPO is selected when right-clicking in the <strong>Group Policy Objects</strong> list.)</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="5b91b-120">报告</span><span class="sxs-lookup"><span data-stu-id="5b91b-120">Reports</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="5b91b-121">命令</span><span class="sxs-lookup"><span data-stu-id="5b91b-121">Command</span></span></th>
<th align="left"><span data-ttu-id="5b91b-122">作用</span><span class="sxs-lookup"><span data-stu-id="5b91b-122">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="5b91b-123">设置</span><span class="sxs-lookup"><span data-stu-id="5b91b-123">Settings</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="5b91b-124">生成用于显示选定 GPO 中的设置的基于 HTML 的报表或基于 XML 的报表。</span><span class="sxs-lookup"><span data-stu-id="5b91b-124">Generate an HTML-based or XML-based report displaying the settings within the selected GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="5b91b-125">不同之处</span><span class="sxs-lookup"><span data-stu-id="5b91b-125">Differences</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="5b91b-126">生成用于比较两个选定 GPO 模板中的设置的基于 HTML 或基于 XML 的报表。</span><span class="sxs-lookup"><span data-stu-id="5b91b-126">Generate an HTML-based or XML-based report comparing the settings within two selected GPO templates.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="5b91b-127">模板管理</span><span class="sxs-lookup"><span data-stu-id="5b91b-127">Template management</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="5b91b-128">命令</span><span class="sxs-lookup"><span data-stu-id="5b91b-128">Command</span></span></th>
<th align="left"><span data-ttu-id="5b91b-129">作用</span><span class="sxs-lookup"><span data-stu-id="5b91b-129">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="5b91b-130">设置为默认值</span><span class="sxs-lookup"><span data-stu-id="5b91b-130">Set as Default</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="5b91b-131">将所选模板设置为默认值，以便在创建新 GPO 时自动使用。</span><span class="sxs-lookup"><span data-stu-id="5b91b-131">Set the selected template as the default to be used automatically when creating a new GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="5b91b-132">删除</span><span class="sxs-lookup"><span data-stu-id="5b91b-132">Delete</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="5b91b-133">将所选模板移到 <strong> 回收站 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="5b91b-133">Move the selected template to the <strong>Recycle Bin</strong>.</span></span> <span data-ttu-id="5b91b-134">如果你没有删除 GPO 的权限，系统将提示你提交请求。</span><span class="sxs-lookup"><span data-stu-id="5b91b-134">If you do not have permission to delete a GPO, you will be prompted to submit a request.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="5b91b-135">重命名</span><span class="sxs-lookup"><span data-stu-id="5b91b-135">Rename</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="5b91b-136">更改所选模板的名称。</span><span class="sxs-lookup"><span data-stu-id="5b91b-136">Change the name of the selected template.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="5b91b-137">杂项</span><span class="sxs-lookup"><span data-stu-id="5b91b-137">Miscellaneous</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="5b91b-138">命令</span><span class="sxs-lookup"><span data-stu-id="5b91b-138">Command</span></span></th>
<th align="left"><span data-ttu-id="5b91b-139">作用</span><span class="sxs-lookup"><span data-stu-id="5b91b-139">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="5b91b-140">刷新</span><span class="sxs-lookup"><span data-stu-id="5b91b-140">Refresh</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="5b91b-141">更新组策略管理控制台的显示以合并所做的任何更改。</span><span class="sxs-lookup"><span data-stu-id="5b91b-141">Update the display of the Group Policy Management Console to incorporate any changes.</span></span> <span data-ttu-id="5b91b-142">在刷新显示之前，某些更改不可见。</span><span class="sxs-lookup"><span data-stu-id="5b91b-142">Some changes are not visible until the display is refreshed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="5b91b-143">帮助</span><span class="sxs-lookup"><span data-stu-id="5b91b-143">Help</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="5b91b-144">显示高级组策略管理（AGPM）的帮助。</span><span class="sxs-lookup"><span data-stu-id="5b91b-144">Display help for Advanced Group Policy Management (AGPM).</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="5b91b-145">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="5b91b-145">Additional references</span></span>

-   [<span data-ttu-id="5b91b-146">“内容”选项卡</span><span class="sxs-lookup"><span data-stu-id="5b91b-146">Contents Tab</span></span>](contents-tab.md)

-   [<span data-ttu-id="5b91b-147">执行编辑者任务</span><span class="sxs-lookup"><span data-stu-id="5b91b-147">Performing Editor Tasks</span></span>](performing-editor-tasks.md)

-   [<span data-ttu-id="5b91b-148">执行审阅者任务</span><span class="sxs-lookup"><span data-stu-id="5b91b-148">Performing Reviewer Tasks</span></span>](performing-reviewer-tasks.md)

 

 





