---
title: 模板命令
description: 模板命令
author: dansimp
ms.assetid: 243a9b18-bf3f-44fa-94d7-5c793f7322da
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2c540bf87462f501a4db5596faca43ef66ee8558
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801756"
---
# <span data-ttu-id="19b9c-103">模板命令</span><span class="sxs-lookup"><span data-stu-id="19b9c-103">Template Commands</span></span>


<span data-ttu-id="19b9c-104">"**模板**" 选项卡：</span><span class="sxs-lookup"><span data-stu-id="19b9c-104">The **Templates** tab:</span></span>

-   <span data-ttu-id="19b9c-105">显示可用于创建新组策略对象（Gpo）的可用模板列表。</span><span class="sxs-lookup"><span data-stu-id="19b9c-105">Displays a list of available templates that you can use to create new Group Policy Objects (GPOs).</span></span>

-   <span data-ttu-id="19b9c-106">提供快捷菜单，其中包含基于所选模板创建 GPO、管理模板和显示模板报表的命令。</span><span class="sxs-lookup"><span data-stu-id="19b9c-106">Provides a shortcut menu with commands for creating a GPO based on a selected template, managing templates, and displaying reports for templates.</span></span>

-   <span data-ttu-id="19b9c-107">显示有权限访问所选模板的组和用户的列表。</span><span class="sxs-lookup"><span data-stu-id="19b9c-107">Displays a list of the groups and users who have permission to access a selected template.</span></span>

<span data-ttu-id="19b9c-108">由于模板不能更改，因此模板没有历史记录。</span><span class="sxs-lookup"><span data-stu-id="19b9c-108">Because a template cannot be altered, templates have no history.</span></span> <span data-ttu-id="19b9c-109">但是，与任何 GPO 版本一样，模板的设置可以与设置报告一起显示，也可以与具有差异报告的另一个 GPO 进行比较。</span><span class="sxs-lookup"><span data-stu-id="19b9c-109">However, like any GPO version, the settings of a template can be displayed with a settings report or compared to another GPO with a difference report.</span></span>

<span data-ttu-id="19b9c-110">**注意** 模板是 GPO 的不可编辑的静态版本，用作创建新的可编辑 Gpo 的起始点。</span><span class="sxs-lookup"><span data-stu-id="19b9c-110">**Note** A template is an uneditable, static version of a GPO for use as a starting point for creating new, editable GPOs.</span></span>

 

<span data-ttu-id="19b9c-111">右键单击此选项卡上的 "**组策略对象**" 列表，将显示快捷菜单，包括以下任何适用选项。</span><span class="sxs-lookup"><span data-stu-id="19b9c-111">Right-clicking the **Group Policy Objects** list on this tab displays a shortcut menu, including whichever of the following options are applicable.</span></span>

## <span data-ttu-id="19b9c-112">控件</span><span class="sxs-lookup"><span data-stu-id="19b9c-112">Control</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="19b9c-113">命令</span><span class="sxs-lookup"><span data-stu-id="19b9c-113">Command</span></span></th>
<th align="left"><span data-ttu-id="19b9c-114">作用</span><span class="sxs-lookup"><span data-stu-id="19b9c-114">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="19b9c-115">新的受控 GPO</span><span class="sxs-lookup"><span data-stu-id="19b9c-115">New Controlled GPO</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="19b9c-116">基于所选模板创建新的 GPO。</span><span class="sxs-lookup"><span data-stu-id="19b9c-116">Create a new GPO based on the selected template.</span></span> <span data-ttu-id="19b9c-117">提供了用于将新 GPO 部署到域的生产环境的选项。</span><span class="sxs-lookup"><span data-stu-id="19b9c-117">The option to deploy the new GPO to the production environment of the domain is provided.</span></span> <span data-ttu-id="19b9c-118">如果你没有创建 GPO 的权限，系统将提示你提交请求。</span><span class="sxs-lookup"><span data-stu-id="19b9c-118">If you do not have permission to create a GPO, you will be prompted to submit a request.</span></span> <span data-ttu-id="19b9c-119">（如果右键单击 <strong> 时未选择任何 GPO，则显示此选项组策略对象 </strong> 列表。）</span><span class="sxs-lookup"><span data-stu-id="19b9c-119">(This option is displayed if no GPO is selected when right-clicking in the <strong>Group Policy Objects</strong> list.)</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="19b9c-120">报告</span><span class="sxs-lookup"><span data-stu-id="19b9c-120">Reports</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="19b9c-121">命令</span><span class="sxs-lookup"><span data-stu-id="19b9c-121">Command</span></span></th>
<th align="left"><span data-ttu-id="19b9c-122">作用</span><span class="sxs-lookup"><span data-stu-id="19b9c-122">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="19b9c-123">设置</span><span class="sxs-lookup"><span data-stu-id="19b9c-123">Settings</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="19b9c-124">生成用于显示选定 GPO 中的设置的基于 HTML 的报表或基于 XML 的报表。</span><span class="sxs-lookup"><span data-stu-id="19b9c-124">Generate an HTML-based or XML-based report displaying the settings within the selected GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="19b9c-125">不同之处</span><span class="sxs-lookup"><span data-stu-id="19b9c-125">Differences</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="19b9c-126">生成用于比较两个选定 GPO 模板中的设置的基于 HTML 或基于 XML 的报表。</span><span class="sxs-lookup"><span data-stu-id="19b9c-126">Generate an HTML-based or XML-based report comparing the settings within two selected GPO templates.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="19b9c-127">模板管理</span><span class="sxs-lookup"><span data-stu-id="19b9c-127">Template management</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="19b9c-128">命令</span><span class="sxs-lookup"><span data-stu-id="19b9c-128">Command</span></span></th>
<th align="left"><span data-ttu-id="19b9c-129">作用</span><span class="sxs-lookup"><span data-stu-id="19b9c-129">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="19b9c-130">设置为默认值</span><span class="sxs-lookup"><span data-stu-id="19b9c-130">Set as Default</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="19b9c-131">将所选模板设置为默认值，以便在创建新 GPO 时自动使用。</span><span class="sxs-lookup"><span data-stu-id="19b9c-131">Set the selected template as the default to be used automatically when creating a new GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="19b9c-132">删除</span><span class="sxs-lookup"><span data-stu-id="19b9c-132">Delete</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="19b9c-133">将所选模板移到 <strong> 回收站 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="19b9c-133">Move the selected template to the <strong>Recycle Bin</strong>.</span></span> <span data-ttu-id="19b9c-134">如果你没有删除 GPO 的权限，系统将提示你提交请求。</span><span class="sxs-lookup"><span data-stu-id="19b9c-134">If you do not have permission to delete a GPO, you will be prompted to submit a request.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="19b9c-135">重命名</span><span class="sxs-lookup"><span data-stu-id="19b9c-135">Rename</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="19b9c-136">更改所选模板的名称。</span><span class="sxs-lookup"><span data-stu-id="19b9c-136">Change the name of the selected template.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="19b9c-137">杂项</span><span class="sxs-lookup"><span data-stu-id="19b9c-137">Miscellaneous</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="19b9c-138">命令</span><span class="sxs-lookup"><span data-stu-id="19b9c-138">Command</span></span></th>
<th align="left"><span data-ttu-id="19b9c-139">作用</span><span class="sxs-lookup"><span data-stu-id="19b9c-139">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="19b9c-140">刷新</span><span class="sxs-lookup"><span data-stu-id="19b9c-140">Refresh</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="19b9c-141">更新组策略管理控制台的显示以合并所做的任何更改。</span><span class="sxs-lookup"><span data-stu-id="19b9c-141">Update the display of the Group Policy Management Console to incorporate any changes.</span></span> <span data-ttu-id="19b9c-142">在刷新显示之前，某些更改不可见。</span><span class="sxs-lookup"><span data-stu-id="19b9c-142">Some changes are not visible until the display is refreshed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="19b9c-143">帮助</span><span class="sxs-lookup"><span data-stu-id="19b9c-143">Help</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="19b9c-144">显示高级组策略管理（AGPM）的帮助。</span><span class="sxs-lookup"><span data-stu-id="19b9c-144">Display help for Advanced Group Policy Management (AGPM).</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="19b9c-145">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="19b9c-145">Additional references</span></span>

-   [<span data-ttu-id="19b9c-146">“内容”选项卡</span><span class="sxs-lookup"><span data-stu-id="19b9c-146">Contents Tab</span></span>](contents-tab-agpm40.md)

-   [<span data-ttu-id="19b9c-147">执行编辑者任务</span><span class="sxs-lookup"><span data-stu-id="19b9c-147">Performing Editor Tasks</span></span>](performing-editor-tasks-agpm40.md)

-   [<span data-ttu-id="19b9c-148">执行审阅者任务</span><span class="sxs-lookup"><span data-stu-id="19b9c-148">Performing Reviewer Tasks</span></span>](performing-reviewer-tasks-agpm40.md)

 

 





