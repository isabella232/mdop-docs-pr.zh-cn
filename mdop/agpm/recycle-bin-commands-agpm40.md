---
title: 回收站命令
description: 回收站命令
author: dansimp
ms.assetid: 347a101f-0ba0-4afc-bd59-752cc06bb904
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b05a5c25a59be751a062086f77daa009d7cb32f3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801859"
---
# <span data-ttu-id="201cc-103">回收站命令</span><span class="sxs-lookup"><span data-stu-id="201cc-103">Recycle Bin Commands</span></span>


<span data-ttu-id="201cc-104">"**回收站**" 选项卡：</span><span class="sxs-lookup"><span data-stu-id="201cc-104">The **Recycle Bin** tab:</span></span>

-   <span data-ttu-id="201cc-105">显示已从存档中删除的组策略对象（Gpo）的列表。</span><span class="sxs-lookup"><span data-stu-id="201cc-105">Displays a list of Group Policy Objects (GPOs) that have been deleted from the archive.</span></span>

-   <span data-ttu-id="201cc-106">提供快捷菜单，其中包含用于管理 Gpo 和显示 Gpo 报告的命令。</span><span class="sxs-lookup"><span data-stu-id="201cc-106">Provides a shortcut menu with commands for managing GPOs and for displaying reports for GPOs.</span></span>

-   <span data-ttu-id="201cc-107">显示具有访问选定 GPO 的权限的组和用户的列表。</span><span class="sxs-lookup"><span data-stu-id="201cc-107">Displays a list of the groups and users who have permission to access a selected GPO.</span></span>

<span data-ttu-id="201cc-108">右键单击此选项卡上的 "**组策略对象**" 列表将显示快捷菜单，包括以下任何适用选项：</span><span class="sxs-lookup"><span data-stu-id="201cc-108">Right-clicking the **Group Policy Objects** list on this tab displays a shortcut menu, including whichever of the following options are applicable:</span></span>

## <span data-ttu-id="201cc-109">报告</span><span class="sxs-lookup"><span data-stu-id="201cc-109">Reports</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="201cc-110">命令</span><span class="sxs-lookup"><span data-stu-id="201cc-110">Command</span></span></th>
<th align="left"><span data-ttu-id="201cc-111">作用</span><span class="sxs-lookup"><span data-stu-id="201cc-111">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="201cc-112">设置</span><span class="sxs-lookup"><span data-stu-id="201cc-112">Settings</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="201cc-113">生成基于 HTML 或基于 XML 的报表，显示所选 GPO 中的设置，或显示从组织单位到 Gpo 最近控制、导入或签入时的选定 Gpo 的链接。</span><span class="sxs-lookup"><span data-stu-id="201cc-113">Generate an HTML-based or XML-based report displaying the settings within the selected GPO or display links to the selected GPOs from organizational units as of when the GPOs were most recently controlled, imported, or checked in.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="201cc-114">不同之处</span><span class="sxs-lookup"><span data-stu-id="201cc-114">Differences</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="201cc-115">生成用于比较两个选定 Gpo 或所选 GPO 和模板内的设置的基于 HTML 或基于 XML 的报表。</span><span class="sxs-lookup"><span data-stu-id="201cc-115">Generate an HTML-based or XML-based report comparing the settings within two selected GPOs or within the selected GPO and a template.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="201cc-116">版本管理</span><span class="sxs-lookup"><span data-stu-id="201cc-116">Version management</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="201cc-117">命令</span><span class="sxs-lookup"><span data-stu-id="201cc-117">Command</span></span></th>
<th align="left"><span data-ttu-id="201cc-118">作用</span><span class="sxs-lookup"><span data-stu-id="201cc-118">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="201cc-119">取消</span><span class="sxs-lookup"><span data-stu-id="201cc-119">Destroy</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="201cc-120">从回收站中删除所选 GPO <strong> </strong> ，以便无法再还原它。</span><span class="sxs-lookup"><span data-stu-id="201cc-120">Remove the selected GPO from the <strong>Recycle Bin</strong>, so it can no longer be restored.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="201cc-121">存储</span><span class="sxs-lookup"><span data-stu-id="201cc-121">Restore</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="201cc-122">将所选 GPO 从 " <strong> 回收站" 移动 </strong> 到 " <strong> 受控 </strong> " 选项卡。这不会将 GPO 还原到生产环境。</span><span class="sxs-lookup"><span data-stu-id="201cc-122">Move the selected GPO from the <strong>Recycle Bin</strong> to the <strong>Controlled</strong> tab. This does not restore the GPO to the production environment.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="201cc-123">杂项</span><span class="sxs-lookup"><span data-stu-id="201cc-123">Miscellaneous</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="201cc-124">命令</span><span class="sxs-lookup"><span data-stu-id="201cc-124">Command</span></span></th>
<th align="left"><span data-ttu-id="201cc-125">作用</span><span class="sxs-lookup"><span data-stu-id="201cc-125">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="201cc-126">刷新</span><span class="sxs-lookup"><span data-stu-id="201cc-126">Refresh</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="201cc-127">更新组策略管理控制台（GPMC）的显示以合并任何更改。</span><span class="sxs-lookup"><span data-stu-id="201cc-127">Update the display of the Group Policy Management Console (GPMC) to incorporate any changes.</span></span> <span data-ttu-id="201cc-128">在刷新显示之前，某些更改不可见。</span><span class="sxs-lookup"><span data-stu-id="201cc-128">Some changes are not visible until the display is refreshed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="201cc-129">帮助</span><span class="sxs-lookup"><span data-stu-id="201cc-129">Help</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="201cc-130">显示高级组策略管理（AGPM）的帮助。</span><span class="sxs-lookup"><span data-stu-id="201cc-130">Display help for Advanced Group Policy Management (AGPM).</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="201cc-131">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="201cc-131">Additional references</span></span>

-   [<span data-ttu-id="201cc-132">“内容”选项卡</span><span class="sxs-lookup"><span data-stu-id="201cc-132">Contents Tab</span></span>](contents-tab-agpm40.md)

-   [<span data-ttu-id="201cc-133">执行审批者任务</span><span class="sxs-lookup"><span data-stu-id="201cc-133">Performing Approver Tasks</span></span>](performing-approver-tasks-agpm40.md)

-   [<span data-ttu-id="201cc-134">执行审阅者任务</span><span class="sxs-lookup"><span data-stu-id="201cc-134">Performing Reviewer Tasks</span></span>](performing-reviewer-tasks-agpm40.md)

 

 





