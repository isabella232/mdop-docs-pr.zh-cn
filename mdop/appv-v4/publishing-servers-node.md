---
title: “发布服务器”节点
description: “发布服务器”节点
author: dansimp
ms.assetid: b5823c6c-15bc-4e8d-aeeb-acc366ffedd1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8c001e246c63919773d29a2317d5a43937c0813f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798843"
---
# <span data-ttu-id="b8132-103">“发布服务器”节点</span><span class="sxs-lookup"><span data-stu-id="b8132-103">Publishing Servers Node</span></span>


<span data-ttu-id="b8132-104">"**发布服务器**" 节点位于应用程序虚拟化客户端管理控制台的**作用域**窗格中的**应用程序虚拟化**节点下一级。</span><span class="sxs-lookup"><span data-stu-id="b8132-104">The **Publishing Servers** node is one level below the **Application Virtualization** node in the **Scope** pane of the Application Virtualization Client Management Console.</span></span> <span data-ttu-id="b8132-105">选择此节点时，"**结果**" 窗格将显示发布服务器的列表。</span><span class="sxs-lookup"><span data-stu-id="b8132-105">When you select this node, the **Results** pane displays a list of publishing servers.</span></span>

<span data-ttu-id="b8132-106">右键单击 "**发布服务器**" 节点可显示一个弹出菜单，其中包含以下元素。</span><span class="sxs-lookup"><span data-stu-id="b8132-106">Right-click the **Publishing Servers** node to display a pop-up menu that contains the following elements.</span></span>

<a href="" id="new-server"></a>**<span data-ttu-id="b8132-107">新服务器</span><span class="sxs-lookup"><span data-stu-id="b8132-107">New Server</span></span>**  
<span data-ttu-id="b8132-108">此菜单项显示 "新建服务器" 向导。</span><span class="sxs-lookup"><span data-stu-id="b8132-108">This menu item displays the New Server Wizard.</span></span> <span data-ttu-id="b8132-109">此向导包含两个页面：</span><span class="sxs-lookup"><span data-stu-id="b8132-109">This wizard consists of two pages:</span></span>

1.  <span data-ttu-id="b8132-110">输入服务器显示名称和服务器类型：</span><span class="sxs-lookup"><span data-stu-id="b8132-110">Enter a server display name and server type:</span></span>

    -   <span data-ttu-id="b8132-111">**显示名称**-输入要为服务器显示的名称。</span><span class="sxs-lookup"><span data-stu-id="b8132-111">**Display Name**—Enter a name that you want displayed for the server.</span></span> <span data-ttu-id="b8132-112">默认情况下，此字段为空。</span><span class="sxs-lookup"><span data-stu-id="b8132-112">This field is blank by default.</span></span>

    -   <span data-ttu-id="b8132-113">**类型**—从服务器类型的下拉列表中选择服务器类型。</span><span class="sxs-lookup"><span data-stu-id="b8132-113">**Type**—Choose the server type from the drop-down list of server types.</span></span>

2.  <span data-ttu-id="b8132-114">指定服务器的连接设置：</span><span class="sxs-lookup"><span data-stu-id="b8132-114">Specify the connection settings for the server:</span></span>

    -   <span data-ttu-id="b8132-115">**主机名**—输入服务器的名称或 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="b8132-115">**Host Name**—Enter the name or IP address for the server.</span></span>

    -   <span data-ttu-id="b8132-116">**端口**-输入与端口号对应的数值。</span><span class="sxs-lookup"><span data-stu-id="b8132-116">**Port**—Enter a numeric value that corresponds to the port number.</span></span> <span data-ttu-id="b8132-117">如果服务器类型为 "应用程序虚拟化服务器" 和80（如果服务器类型为 "标准 HTTP 服务器"），则默认值为554。</span><span class="sxs-lookup"><span data-stu-id="b8132-117">The default value is 554 if the server type is "Application Virtualization Server" and 80 if the server type is "Standard HTTP Server."</span></span>

    -   <span data-ttu-id="b8132-118">**路径**-当服务器类型为 "Application Virtualization server" 或 "增强的安全应用程序虚拟化服务器" 时，此字段默认为 "/"，并且是只读的。</span><span class="sxs-lookup"><span data-stu-id="b8132-118">**Path**—This field defaults to "/" and is read-only when the server type is "Application Virtualization Server" or “Enhanced Security Application Virtualization Server”.</span></span> <span data-ttu-id="b8132-119">当服务器类型为 "标准 HTTP 服务器" 或 "增强的安全 HTTP 服务器" 时，**路径**字段也是可编辑的。</span><span class="sxs-lookup"><span data-stu-id="b8132-119">When the server type is “Standard HTTP Server” or “Enhanced Security HTTP Server”, the **Path** field is also editable.</span></span>

<a href="" id="new-window-from-here"></a>**<span data-ttu-id="b8132-120">从此处新建窗口</span><span class="sxs-lookup"><span data-stu-id="b8132-120">New Window from Here</span></span>**  
<span data-ttu-id="b8132-121">选择此菜单项以打开新的管理控制台，其中将选定的节点用作根节点。</span><span class="sxs-lookup"><span data-stu-id="b8132-121">Select this menu item to open a new management console with the selected node as the root node.</span></span>

<a href="" id="export-list"></a>**<span data-ttu-id="b8132-122">导出列表</span><span class="sxs-lookup"><span data-stu-id="b8132-122">Export List</span></span>**  
<span data-ttu-id="b8132-123">可以使用此菜单项创建一个以制表符分隔的文本文件，其中包含 "**结果**" 窗格的内容。</span><span class="sxs-lookup"><span data-stu-id="b8132-123">You can use this menu item to create a tab-delimited text file that contains the contents of the **Results** pane.</span></span> <span data-ttu-id="b8132-124">此项显示一个标准的 "**文件保存**" 对话框，您可以在其中指定要创建的文本文件的位置。</span><span class="sxs-lookup"><span data-stu-id="b8132-124">This item displays a standard **File Save** dialog box where you specify the location for the text file you are creating.</span></span>

<a href="" id="view"></a>**<span data-ttu-id="b8132-125">视图</span><span class="sxs-lookup"><span data-stu-id="b8132-125">View</span></span>**  
<span data-ttu-id="b8132-126">此弹出菜单项列表使你能够更改 "**结果**" 窗格的外观和内容。</span><span class="sxs-lookup"><span data-stu-id="b8132-126">This pop-up list of menu items enables you to change the appearance and content of the **Results** pane.</span></span>

<a href="" id="refresh"></a>**<span data-ttu-id="b8132-127">刷新</span><span class="sxs-lookup"><span data-stu-id="b8132-127">Refresh</span></span>**  
<span data-ttu-id="b8132-128">选择此项目以刷新管理控制台。</span><span class="sxs-lookup"><span data-stu-id="b8132-128">Select this item to refresh the management console.</span></span>

<a href="" id="help"></a>**<span data-ttu-id="b8132-129">帮助</span><span class="sxs-lookup"><span data-stu-id="b8132-129">Help</span></span>**  
<span data-ttu-id="b8132-130">此项目显示管理控制台的帮助系统。</span><span class="sxs-lookup"><span data-stu-id="b8132-130">This item displays the help system for the management console.</span></span>

## <span data-ttu-id="b8132-131">相关主题</span><span class="sxs-lookup"><span data-stu-id="b8132-131">Related topics</span></span>


[<span data-ttu-id="b8132-132">“发布服务器结果”窗格</span><span class="sxs-lookup"><span data-stu-id="b8132-132">Publishing Servers Results Pane</span></span>](publishing-servers-results-pane.md)

[<span data-ttu-id="b8132-133">“发布服务器结果”窗格列</span><span class="sxs-lookup"><span data-stu-id="b8132-133">Publishing Servers Results Pane Columns</span></span>](publishing-servers-results-pane-columns.md)

 

 





