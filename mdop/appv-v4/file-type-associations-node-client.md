---
title: “文件类型关联”节点
description: “文件类型关联”节点
author: dansimp
ms.assetid: 48e4d9eb-00bd-4231-a68a-f8597ab683ff
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d94621a1d418f0af29ef9e73b8d430c81a7181c8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802987"
---
# <span data-ttu-id="98963-103">“文件类型关联”节点</span><span class="sxs-lookup"><span data-stu-id="98963-103">File Type Associations Node</span></span>


<span data-ttu-id="98963-104">"**文件类型关联**" 节点是应用程序虚拟化客户端管理控制台的**范围**窗格中 "**应用程序虚拟化**" 节点下方的一个级别。</span><span class="sxs-lookup"><span data-stu-id="98963-104">The **File Type Associations** node is one level below the **Application Virtualization** node in the **Scope** pane of the Application Virtualization Client Management Console.</span></span> <span data-ttu-id="98963-105">选择此节点时，"**结果**" 窗格将显示文件类型关联的列表。</span><span class="sxs-lookup"><span data-stu-id="98963-105">When you select this node, the **Results** pane displays a list of file type associations.</span></span>

<span data-ttu-id="98963-106">右键单击 "**文件类型关联**" 节点以显示包含以下元素的弹出菜单。</span><span class="sxs-lookup"><span data-stu-id="98963-106">Right-click the **File Type Associations** node to display a pop-up menu that contains the following elements.</span></span>

<a href="" id="new-association"></a>**<span data-ttu-id="98963-107">新关联</span><span class="sxs-lookup"><span data-stu-id="98963-107">New Association</span></span>**  
<span data-ttu-id="98963-108">此菜单项显示 "新建关联" 向导。</span><span class="sxs-lookup"><span data-stu-id="98963-108">This menu item displays the New Association Wizard.</span></span> <span data-ttu-id="98963-109">此向导包含两个页面：</span><span class="sxs-lookup"><span data-stu-id="98963-109">This wizard consists of two pages:</span></span>

1.  <span data-ttu-id="98963-110">输入新的或现有的文件扩展名，并将扩展名与文件类型关联：</span><span class="sxs-lookup"><span data-stu-id="98963-110">Enter a new or existing file name extension, and associate the extension with a file type:</span></span>

    -   <span data-ttu-id="98963-111">**扩展名**-输入新的或现有的文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="98963-111">**Extension**—Enter a new or existing file name extension.</span></span> <span data-ttu-id="98963-112">默认情况下，此字段为空。</span><span class="sxs-lookup"><span data-stu-id="98963-112">This field is blank by default.</span></span>

    -   <span data-ttu-id="98963-113">**使用此说明创建新的文件类型**-选择此单选按钮可在活动字段中输入新的文件类型说明。</span><span class="sxs-lookup"><span data-stu-id="98963-113">**Create a new file type with this description**—Select this radio button to enter a new file type description in the active field.</span></span> <span data-ttu-id="98963-114">默认情况下，此按钮处于选中状态，并且活动字段为空。</span><span class="sxs-lookup"><span data-stu-id="98963-114">This button is selected by default, and the active field is blank.</span></span>

    -   <span data-ttu-id="98963-115">**将此文件类型应用于所有用户**-如果希望此关联为所有用户全局，请选中此复选框。</span><span class="sxs-lookup"><span data-stu-id="98963-115">**Apply this file type to all users**—Select this check box when you want this association to be global for all users.</span></span> <span data-ttu-id="98963-116">默认情况下，此框未选中。</span><span class="sxs-lookup"><span data-stu-id="98963-116">By default, this box is not selected.</span></span>

    -   <span data-ttu-id="98963-117">**使用现有文件类型链接此扩展名**-选择此单选按钮可将扩展名与现有文件类型相关联。</span><span class="sxs-lookup"><span data-stu-id="98963-117">**Link this extension with an existing file type**—Select this radio button to associate the extension with an existing file type.</span></span> <span data-ttu-id="98963-118">从下拉列表中选择文件类型。</span><span class="sxs-lookup"><span data-stu-id="98963-118">Choose a file type from the drop-down list.</span></span> <span data-ttu-id="98963-119">选择此选项时，"**下一步**" 将更改为 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="98963-119">When you choose this option, **Next** is changed to **Finish**.</span></span>

2.  <span data-ttu-id="98963-120">选择将打开具有指定扩展名的文件的应用程序：</span><span class="sxs-lookup"><span data-stu-id="98963-120">Select the application that will open files with the specified extension:</span></span>

    -   <span data-ttu-id="98963-121">**使用所选应用程序打开文件**-选择此单选按钮以使用现有应用程序打开文件。</span><span class="sxs-lookup"><span data-stu-id="98963-121">**Open files with the selected application**—Select this radio button to open the file with an existing application.</span></span> <span data-ttu-id="98963-122">从可用应用程序下拉列表中选择应用程序。</span><span class="sxs-lookup"><span data-stu-id="98963-122">Choose an application from the drop-down list of available applications.</span></span>

    -   <span data-ttu-id="98963-123">**使用此 OSD 文件中描述的应用程序打开文件**-选择此单选按钮可指定一个开放软件描述符（OSD）文件，该文件确定用于打开文件的应用程序。</span><span class="sxs-lookup"><span data-stu-id="98963-123">**Open files with the application described in this OSD file**—Select this radio button to specify an Open Software Descriptor (OSD) file that determines the application used to open the file.</span></span> <span data-ttu-id="98963-124">通过浏览选择现有位置，或在此字段中输入路径或 HTTP 格式的 URL。</span><span class="sxs-lookup"><span data-stu-id="98963-124">Browse to select an existing location, or enter a path or HTTP-formatted URL in this field.</span></span>

<a href="" id="new-window-from-here"></a>**<span data-ttu-id="98963-125">从此处新建窗口</span><span class="sxs-lookup"><span data-stu-id="98963-125">New Window from Here</span></span>**  
<span data-ttu-id="98963-126">选择此菜单项以打开新的管理控制台，其中将选定的节点用作根节点。</span><span class="sxs-lookup"><span data-stu-id="98963-126">Select this menu item to open a new management console with the selected node as the root node.</span></span>

<a href="" id="export-list"></a>**<span data-ttu-id="98963-127">导出列表</span><span class="sxs-lookup"><span data-stu-id="98963-127">Export List</span></span>**  
<span data-ttu-id="98963-128">可以使用此菜单项创建一个以制表符分隔的文本文件，其中包含 "**结果**" 窗格的内容。</span><span class="sxs-lookup"><span data-stu-id="98963-128">You can use this menu item to create a tab-delimited text file that contains the contents of the **Results** pane.</span></span> <span data-ttu-id="98963-129">此项显示一个标准的 "**文件保存**" 对话框，您可以在其中指定要创建的文本文件的位置。</span><span class="sxs-lookup"><span data-stu-id="98963-129">This item displays a standard **File Save** dialog box where you specify the location for the text file you are creating.</span></span>

<a href="" id="view"></a>**<span data-ttu-id="98963-130">视图</span><span class="sxs-lookup"><span data-stu-id="98963-130">View</span></span>**  
<span data-ttu-id="98963-131">此弹出菜单项列表使你能够更改 "**结果**" 窗格的外观和内容。</span><span class="sxs-lookup"><span data-stu-id="98963-131">This pop-up list of menu items enables you to change the appearance and content of the **Results** pane.</span></span>

<a href="" id="refresh"></a>**<span data-ttu-id="98963-132">刷新</span><span class="sxs-lookup"><span data-stu-id="98963-132">Refresh</span></span>**  
<span data-ttu-id="98963-133">选择此项目以刷新管理控制台。</span><span class="sxs-lookup"><span data-stu-id="98963-133">Select this item to refresh the management console.</span></span>

<a href="" id="help"></a>**<span data-ttu-id="98963-134">帮助</span><span class="sxs-lookup"><span data-stu-id="98963-134">Help</span></span>**  
<span data-ttu-id="98963-135">通过此菜单项，你可以显示管理控制台的帮助系统。</span><span class="sxs-lookup"><span data-stu-id="98963-135">With this menu item, you can display the help system for the management console.</span></span>

## <span data-ttu-id="98963-136">相关主题</span><span class="sxs-lookup"><span data-stu-id="98963-136">Related topics</span></span>


[<span data-ttu-id="98963-137">“文件类型关联结果”窗格</span><span class="sxs-lookup"><span data-stu-id="98963-137">File Type Association Results Pane</span></span>](file-type-association-results-pane.md)

[<span data-ttu-id="98963-138">“文件类型关联结果”窗格列</span><span class="sxs-lookup"><span data-stu-id="98963-138">File Type Association Results Pane Columns</span></span>](file-type-association-results-pane-columns.md)

 

 





