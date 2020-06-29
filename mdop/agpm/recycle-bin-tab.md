---
title: “回收站”选项卡
description: “回收站”选项卡
author: dansimp
ms.assetid: 9ce62e98-c03e-4a75-90e0-51be83c6d2db
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7c4a4f8fc6f72045e81515b88788b040b3764d84
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802603"
---
# <span data-ttu-id="92f05-103">“回收站”选项卡</span><span class="sxs-lookup"><span data-stu-id="92f05-103">Recycle Bin Tab</span></span>


<span data-ttu-id="92f05-104">"**回收站**" 选项卡：</span><span class="sxs-lookup"><span data-stu-id="92f05-104">The **Recycle Bin** tab:</span></span>

-   <span data-ttu-id="92f05-105">显示已从存档中删除的组策略对象（Gpo）的列表。</span><span class="sxs-lookup"><span data-stu-id="92f05-105">Displays a list of Group Policy objects (GPOs) that have been deleted from the archive.</span></span>

-   <span data-ttu-id="92f05-106">提供快捷菜单，其中包含用于管理 Gpo 和显示 Gpo 报告的命令。</span><span class="sxs-lookup"><span data-stu-id="92f05-106">Provides a shortcut menu with commands for managing GPOs and for displaying reports for GPOs.</span></span>

-   <span data-ttu-id="92f05-107">显示具有访问选定 GPO 的权限的组和用户的列表。</span><span class="sxs-lookup"><span data-stu-id="92f05-107">Displays a list of the groups and users who have permission to access a selected GPO.</span></span>

<span data-ttu-id="92f05-108">右键单击此选项卡上的 "**组策略对象**" 列表将显示快捷菜单，包括以下任何适用选项：</span><span class="sxs-lookup"><span data-stu-id="92f05-108">Right-clicking the **Group Policy Objects** list on this tab displays a shortcut menu, including whichever of the following options are applicable:</span></span>

## <span data-ttu-id="92f05-109">报告</span><span class="sxs-lookup"><span data-stu-id="92f05-109">Reports</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="92f05-110">命令</span><span class="sxs-lookup"><span data-stu-id="92f05-110">Command</span></span></th>
<th align="left"><span data-ttu-id="92f05-111">作用</span><span class="sxs-lookup"><span data-stu-id="92f05-111">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="92f05-112">设置</span><span class="sxs-lookup"><span data-stu-id="92f05-112">Settings</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="92f05-113">生成基于 HTML 或基于 XML 的报表，显示所选 GPO 中的设置，或显示从组织单位到 Gpo 最近控制、导入或签入时的选定 Gpo 的链接。</span><span class="sxs-lookup"><span data-stu-id="92f05-113">Generate an HTML-based or XML-based report displaying the settings within the selected GPO or display links to the selected GPOs from organizational units as of when the GPOs were most recently controlled, imported, or checked in.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="92f05-114">不同之处</span><span class="sxs-lookup"><span data-stu-id="92f05-114">Differences</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="92f05-115">生成用于比较两个选定 Gpo 或所选 GPO 和模板内的设置的基于 HTML 或基于 XML 的报表。</span><span class="sxs-lookup"><span data-stu-id="92f05-115">Generate an HTML-based or XML-based report comparing the settings within two selected GPOs or within the selected GPO and a template.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="92f05-116">版本管理</span><span class="sxs-lookup"><span data-stu-id="92f05-116">Version management</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="92f05-117">命令</span><span class="sxs-lookup"><span data-stu-id="92f05-117">Command</span></span></th>
<th align="left"><span data-ttu-id="92f05-118">作用</span><span class="sxs-lookup"><span data-stu-id="92f05-118">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="92f05-119">取消</span><span class="sxs-lookup"><span data-stu-id="92f05-119">Destroy</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="92f05-120">从回收站中删除所选 GPO <strong> </strong> ，以便无法再还原它。</span><span class="sxs-lookup"><span data-stu-id="92f05-120">Remove the selected GPO from the <strong>Recycle Bin</strong>, so it can no longer be restored.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="92f05-121">存储</span><span class="sxs-lookup"><span data-stu-id="92f05-121">Restore</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="92f05-122">将所选 GPO 从 " <strong> 回收站" 移动 </strong> 到 " <strong> 受控 </strong> " 选项卡。这不会将 GPO 还原到生产环境。</span><span class="sxs-lookup"><span data-stu-id="92f05-122">Move the selected GPO from the <strong>Recycle Bin</strong> to the <strong>Controlled</strong> tab. This does not restore the GPO to the production environment.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="92f05-123">杂项</span><span class="sxs-lookup"><span data-stu-id="92f05-123">Miscellaneous</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="92f05-124">命令</span><span class="sxs-lookup"><span data-stu-id="92f05-124">Command</span></span></th>
<th align="left"><span data-ttu-id="92f05-125">作用</span><span class="sxs-lookup"><span data-stu-id="92f05-125">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="92f05-126">刷新</span><span class="sxs-lookup"><span data-stu-id="92f05-126">Refresh</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="92f05-127">更新组策略管理控制台的显示以合并所做的任何更改。</span><span class="sxs-lookup"><span data-stu-id="92f05-127">Update the display of the Group Policy Management Console to incorporate any changes.</span></span> <span data-ttu-id="92f05-128">在刷新显示之前，某些更改不可见。</span><span class="sxs-lookup"><span data-stu-id="92f05-128">Some changes are not visible until the display is refreshed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="92f05-129">帮助</span><span class="sxs-lookup"><span data-stu-id="92f05-129">Help</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="92f05-130">显示 AGPM 的帮助。</span><span class="sxs-lookup"><span data-stu-id="92f05-130">Display help for AGPM.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="92f05-131">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="92f05-131">Additional references</span></span>

-   [<span data-ttu-id="92f05-132">“内容”选项卡</span><span class="sxs-lookup"><span data-stu-id="92f05-132">Contents Tab</span></span>](contents-tab.md)

-   [<span data-ttu-id="92f05-133">执行审批者任务</span><span class="sxs-lookup"><span data-stu-id="92f05-133">Performing Approver Tasks</span></span>](performing-approver-tasks.md)

-   [<span data-ttu-id="92f05-134">执行审阅者任务</span><span class="sxs-lookup"><span data-stu-id="92f05-134">Performing Reviewer Tasks</span></span>](performing-reviewer-tasks.md)

 

 





