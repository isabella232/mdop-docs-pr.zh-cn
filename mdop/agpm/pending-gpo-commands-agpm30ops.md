---
title: 挂起的 GPO 命令
description: 挂起的 GPO 命令
author: dansimp
ms.assetid: 3868dda0-8a41-4bba-9b0c-9f656f9a3cd5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: dde41ea33305290174eab6e34c382aec4ce8b18d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803175"
---
# <span data-ttu-id="95aed-103">挂起的 GPO 命令</span><span class="sxs-lookup"><span data-stu-id="95aed-103">Pending GPO Commands</span></span>


<span data-ttu-id="95aed-104">"**挂起**" 选项卡：</span><span class="sxs-lookup"><span data-stu-id="95aed-104">The **Pending** tab:</span></span>

-   <span data-ttu-id="95aed-105">显示组策略对象（Gpo）的列表，其中包含 GPO 管理操作的挂起请求（如创建、控制、部署或删除）。</span><span class="sxs-lookup"><span data-stu-id="95aed-105">Displays a list of Group Policy Objects (GPOs) with pending requests for GPO management actions (such as creation, control, deployment, or deletion).</span></span>

-   <span data-ttu-id="95aed-106">提供快捷菜单，其中包含用于响应挂起的请求和显示 Gpo 的历史记录和报告的命令。</span><span class="sxs-lookup"><span data-stu-id="95aed-106">Provides a shortcut menu with commands for responding to pending requests and for displaying the history and reports for GPOs.</span></span>

-   <span data-ttu-id="95aed-107">显示具有访问选定 GPO 的权限的组和用户的列表。</span><span class="sxs-lookup"><span data-stu-id="95aed-107">Displays a list of the groups and users who have permission to access a selected GPO.</span></span>

<span data-ttu-id="95aed-108">右键单击此选项卡上的 "**组策略对象**" 列表，将显示快捷菜单，包括以下任何适用选项。</span><span class="sxs-lookup"><span data-stu-id="95aed-108">Right-clicking the **Group Policy Objects** list on this tab displays a shortcut menu, including whichever of the following options are applicable.</span></span>

## <span data-ttu-id="95aed-109">控件和历史记录</span><span class="sxs-lookup"><span data-stu-id="95aed-109">Control and history</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="95aed-110">命令</span><span class="sxs-lookup"><span data-stu-id="95aed-110">Command</span></span></th>
<th align="left"><span data-ttu-id="95aed-111">作用</span><span class="sxs-lookup"><span data-stu-id="95aed-111">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="95aed-112">历史记录</span><span class="sxs-lookup"><span data-stu-id="95aed-112">History</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="95aed-113">打开一个窗口，列出存档中保存的选定 GPO 的所有版本。</span><span class="sxs-lookup"><span data-stu-id="95aed-113">Open a window listing all versions of the selected GPO saved within the archive.</span></span> <span data-ttu-id="95aed-114">从历史记录中，你可以获取 GPO 中的设置报告、比较 GPO 的两个版本、将 GPO 与模板进行比较或回退到 GPO 的早期版本。</span><span class="sxs-lookup"><span data-stu-id="95aed-114">From the history, you can obtain a report of the settings within a GPO, compare two versions of a GPO, compare a GPO to a template, or roll back to a previous version of a GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="95aed-115">提取</span><span class="sxs-lookup"><span data-stu-id="95aed-115">Withdraw</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="95aed-116">撤消请求以在请求被批准之前创建、控制或删除所选 GPO。</span><span class="sxs-lookup"><span data-stu-id="95aed-116">Withdraw your pending request to create, control, or delete the selected GPO before the request has been approved.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="95aed-117">批准</span><span class="sxs-lookup"><span data-stu-id="95aed-117">Approve</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="95aed-118">完成来自编辑器的挂起请求以创建、控制或删除所选 GPO。</span><span class="sxs-lookup"><span data-stu-id="95aed-118">Complete a pending request from an Editor to create, control, or delete the selected GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="95aed-119">&</span><span class="sxs-lookup"><span data-stu-id="95aed-119">Reject</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="95aed-120">拒绝来自编辑器的挂起请求以创建、控制或删除所选 GPO。</span><span class="sxs-lookup"><span data-stu-id="95aed-120">Deny a pending request from an Editor to create, control, or delete the selected GPO.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="95aed-121">报告</span><span class="sxs-lookup"><span data-stu-id="95aed-121">Reports</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="95aed-122">命令</span><span class="sxs-lookup"><span data-stu-id="95aed-122">Command</span></span></th>
<th align="left"><span data-ttu-id="95aed-123">作用</span><span class="sxs-lookup"><span data-stu-id="95aed-123">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="95aed-124">设置</span><span class="sxs-lookup"><span data-stu-id="95aed-124">Settings</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="95aed-125">生成基于 HTML 或基于 XML 的报表，显示所选 GPO 中的设置，或显示从组织单位到 Gpo 最近控制、导入或签入时的选定 Gpo 的链接。</span><span class="sxs-lookup"><span data-stu-id="95aed-125">Generate an HTML-based or XML-based report displaying the settings within the selected GPO or display links to the selected GPOs from organizational units as of when the GPOs are most recently controlled, imported, or checked in.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="95aed-126">不同之处</span><span class="sxs-lookup"><span data-stu-id="95aed-126">Differences</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="95aed-127">生成用于比较两个选定 Gpo 或所选 GPO 和模板内的设置的基于 HTML 或基于 XML 的报表。</span><span class="sxs-lookup"><span data-stu-id="95aed-127">Generate an HTML-based or XML-based report comparing the settings within two selected GPOs or within the selected GPO and a template.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="95aed-128">杂项</span><span class="sxs-lookup"><span data-stu-id="95aed-128">Miscellaneous</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="95aed-129">命令</span><span class="sxs-lookup"><span data-stu-id="95aed-129">Command</span></span></th>
<th align="left"><span data-ttu-id="95aed-130">作用</span><span class="sxs-lookup"><span data-stu-id="95aed-130">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="95aed-131">刷新</span><span class="sxs-lookup"><span data-stu-id="95aed-131">Refresh</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="95aed-132">更新组策略管理控制台（GPMC）的显示以合并任何更改。</span><span class="sxs-lookup"><span data-stu-id="95aed-132">Update the display of the Group Policy Management Console (GPMC) to incorporate any changes.</span></span> <span data-ttu-id="95aed-133">在刷新显示之前，某些更改不可见。</span><span class="sxs-lookup"><span data-stu-id="95aed-133">Some changes are not visible until the display is refreshed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="95aed-134">帮助</span><span class="sxs-lookup"><span data-stu-id="95aed-134">Help</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="95aed-135">显示 AGPM 的帮助。</span><span class="sxs-lookup"><span data-stu-id="95aed-135">Display help for AGPM.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="95aed-136">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="95aed-136">Additional references</span></span>

-   [<span data-ttu-id="95aed-137">“内容”选项卡</span><span class="sxs-lookup"><span data-stu-id="95aed-137">Contents Tab</span></span>](contents-tab-agpm30ops.md)

-   [<span data-ttu-id="95aed-138">执行审批者任务</span><span class="sxs-lookup"><span data-stu-id="95aed-138">Performing Approver Tasks</span></span>](performing-approver-tasks-agpm30ops.md)

-   [<span data-ttu-id="95aed-139">执行审阅者任务</span><span class="sxs-lookup"><span data-stu-id="95aed-139">Performing Reviewer Tasks</span></span>](performing-reviewer-tasks-agpm30ops.md)

 

 





