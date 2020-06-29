---
title: “提供程序策略”节点
description: “提供程序策略”节点
author: dansimp
ms.assetid: 89b47076-7732-4128-93cc-8e6d5b671c8e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 221171b22471a4a8614b13023b24dd21fd571dd3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798850"
---
# <span data-ttu-id="50ffd-103">“提供程序策略”节点</span><span class="sxs-lookup"><span data-stu-id="50ffd-103">Provider Policies Node</span></span>


<span data-ttu-id="50ffd-104">"**提供程序策略**" 节点位于应用程序虚拟化服务器管理控制台的 "**范围**" 窗格中 "应用程序虚拟化系统" 节点下的一个级别。</span><span class="sxs-lookup"><span data-stu-id="50ffd-104">The **Provider Policies** node is one level below the Application Virtualization System node in the **Scope** pane in the Application Virtualization Server Management Console.</span></span> <span data-ttu-id="50ffd-105">选择此节点时，"**结果**" 窗格将显示提供商策略的列表。</span><span class="sxs-lookup"><span data-stu-id="50ffd-105">When you select this node, the **Results** pane displays a list of provider policies.</span></span> <span data-ttu-id="50ffd-106">右键单击 "**提供商策略**" 节点以显示包含以下元素的弹出菜单。</span><span class="sxs-lookup"><span data-stu-id="50ffd-106">Right-click the **Provider Policies** node to display a pop-up menu that contains the following elements.</span></span>

<a href="" id="new-provider-policy"></a>**<span data-ttu-id="50ffd-107">新的提供商策略</span><span class="sxs-lookup"><span data-stu-id="50ffd-107">New Provider Policy</span></span>**  
<span data-ttu-id="50ffd-108">显示 "新建提供程序策略" 向导。</span><span class="sxs-lookup"><span data-stu-id="50ffd-108">Displays the New Provider Policy Wizard.</span></span> <span data-ttu-id="50ffd-109">此向导包含以下页面：</span><span class="sxs-lookup"><span data-stu-id="50ffd-109">This wizard consists of the following pages:</span></span>

1.  <span data-ttu-id="50ffd-110">在 "**提供商策略名称**" 字段中输入一个名称。</span><span class="sxs-lookup"><span data-stu-id="50ffd-110">Enter a name in the **Provider Policy Name** field.</span></span> <span data-ttu-id="50ffd-111">如果需要此功能，请选中 "**使用管理控制台管理客户端桌面"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="50ffd-111">Select the **Manage client desktop using the Management Console** check box if you want that capability.</span></span> <span data-ttu-id="50ffd-112">如果需要相关联的功能，请选中以下一个或两个复选框：</span><span class="sxs-lookup"><span data-stu-id="50ffd-112">Select one or both of the following check boxes if you want the associated functionality:</span></span>

    -   **<span data-ttu-id="50ffd-113">用户登录时刷新发布配置</span><span class="sxs-lookup"><span data-stu-id="50ffd-113">Refresh publishing configuration when a user logs in</span></span>**

    -   <span data-ttu-id="50ffd-114">**刷新配置间隔**。</span><span class="sxs-lookup"><span data-stu-id="50ffd-114">**Refresh configuration every**.</span></span> <span data-ttu-id="50ffd-115">选择此选项后，输入一个数字，然后从下拉菜单中选择单位。</span><span class="sxs-lookup"><span data-stu-id="50ffd-115">After selecting this option, enter a number and select the unit from the drop-down menu.</span></span> <span data-ttu-id="50ffd-116">有效条目最少**30 分钟**到最大**999 天**。</span><span class="sxs-lookup"><span data-stu-id="50ffd-116">Valid entries range from a minimum of **30 minutes** to a maximum of **999 days**.</span></span>

2.  <span data-ttu-id="50ffd-117">单击 "**添加**" 或 "**删除**" 添加或删除组分配。</span><span class="sxs-lookup"><span data-stu-id="50ffd-117">Click **Add** or **Remove** to add or remove a group assignment.</span></span> <span data-ttu-id="50ffd-118">使用标准的**Windows "浏览**" 对话框查找用户组。</span><span class="sxs-lookup"><span data-stu-id="50ffd-118">Use the standard **Windows Browse** dialog box to find a user group.</span></span>

3.  <span data-ttu-id="50ffd-119">在 "**提供商管道配置**" 对话框中选择以下复选框之一，启用相关联的功能：</span><span class="sxs-lookup"><span data-stu-id="50ffd-119">Select one of the following check boxes on the **Provider Pipeline Configuration** dialog box to enable the associated feature:</span></span>

    -   <span data-ttu-id="50ffd-120">**身份验证**-从下拉列表中选择身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="50ffd-120">**Authentication**—Select the type of authentication from the drop-down list.</span></span>

    -   **<span data-ttu-id="50ffd-121">强制实施访问权限设置</span><span class="sxs-lookup"><span data-stu-id="50ffd-121">Enforce Access Permission Settings</span></span>**

    -   **<span data-ttu-id="50ffd-122">日志使用信息</span><span class="sxs-lookup"><span data-stu-id="50ffd-122">Log Usage Information</span></span>**

    -   <span data-ttu-id="50ffd-123">**许可**-从下拉列表中选择强制方案。</span><span class="sxs-lookup"><span data-stu-id="50ffd-123">**Licensing**—Select an enforcement scheme from the drop-down list.</span></span>

4.  <span data-ttu-id="50ffd-124">单击 "**完成**" 以添加新的提供商策略。</span><span class="sxs-lookup"><span data-stu-id="50ffd-124">Click **Finish** to add the new provider policy.</span></span>

<a href="" id="view"></a>**<span data-ttu-id="50ffd-125">视图</span><span class="sxs-lookup"><span data-stu-id="50ffd-125">View</span></span>**  
<span data-ttu-id="50ffd-126">更改 "**结果**" 窗格的外观和内容。</span><span class="sxs-lookup"><span data-stu-id="50ffd-126">Changes the appearance and content of the **Results** pane.</span></span>

<a href="" id="new-window-from-here"></a>**<span data-ttu-id="50ffd-127">从此处新建窗口</span><span class="sxs-lookup"><span data-stu-id="50ffd-127">New Window from Here</span></span>**  
<span data-ttu-id="50ffd-128">打开新的管理控制台，其中将选定的节点作为根节点。</span><span class="sxs-lookup"><span data-stu-id="50ffd-128">Opens a new management console with the selected node as the root node.</span></span>

<a href="" id="refresh"></a>**<span data-ttu-id="50ffd-129">刷新</span><span class="sxs-lookup"><span data-stu-id="50ffd-129">Refresh</span></span>**  
<span data-ttu-id="50ffd-130">刷新服务器的视图。</span><span class="sxs-lookup"><span data-stu-id="50ffd-130">Refreshes the view of the server.</span></span>

<a href="" id="export-list"></a>**<span data-ttu-id="50ffd-131">导出列表</span><span class="sxs-lookup"><span data-stu-id="50ffd-131">Export List</span></span>**  
<span data-ttu-id="50ffd-132">创建一个制表符分隔的文本文件，其中包含 "**结果**" 窗格的内容。</span><span class="sxs-lookup"><span data-stu-id="50ffd-132">Creates a tab-delimited text file that contains the contents of the **Results** pane.</span></span> <span data-ttu-id="50ffd-133">此项显示一个标准的 "**文件保存**" 对话框，您可以在其中指定要创建的文本文件的位置。</span><span class="sxs-lookup"><span data-stu-id="50ffd-133">This item displays a standard **File Save** dialog box where you specify the location for the text file you are creating.</span></span>

<a href="" id="help"></a>**<span data-ttu-id="50ffd-134">帮助</span><span class="sxs-lookup"><span data-stu-id="50ffd-134">Help</span></span>**  
<span data-ttu-id="50ffd-135">显示应用程序虚拟化服务器管理控制台的帮助系统。</span><span class="sxs-lookup"><span data-stu-id="50ffd-135">Displays the help system for the Application Virtualization Server Management Console.</span></span>

## <span data-ttu-id="50ffd-136">相关主题</span><span class="sxs-lookup"><span data-stu-id="50ffd-136">Related topics</span></span>


[<span data-ttu-id="50ffd-137">Server Management Console：“提供程序策略”节点</span><span class="sxs-lookup"><span data-stu-id="50ffd-137">Server Management Console: Provider Policies Node</span></span>](server-management-console-provider-policies-node.md)

 

 





