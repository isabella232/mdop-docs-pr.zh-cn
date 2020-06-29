---
title: 如何使用管理控制台添加或升级程序包
description: 如何使用管理控制台添加或升级程序包
author: dansimp
ms.assetid: 4e389d7e-f402-44a7-bc4c-42c2a8440573
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 583ac07168c44c7d0a605b81512ae01a6d979db2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798553"
---
# <span data-ttu-id="e2a7b-103">如何使用管理控制台添加或升级程序包</span><span class="sxs-lookup"><span data-stu-id="e2a7b-103">How to Add or Upgrade Packages by Using the Management Console</span></span>


<span data-ttu-id="e2a7b-104">你可以通过以下过程将程序包添加到 app-v 5.0 管理控制台或将其升级到该管理控制台。</span><span class="sxs-lookup"><span data-stu-id="e2a7b-104">You can the following procedure to add or upgrade a package to the App-V 5.0 Management Console.</span></span> <span data-ttu-id="e2a7b-105">若要升级管理控制台中已存在的程序包，请使用以下步骤，并使用相同的程序包**名称**导入升级后的程序包。</span><span class="sxs-lookup"><span data-stu-id="e2a7b-105">To upgrade a package that already exists in the Management Console, use the following steps and import the upgraded package using the same package **Name**.</span></span>

**<span data-ttu-id="e2a7b-106">将程序包添加到管理控制台</span><span class="sxs-lookup"><span data-stu-id="e2a7b-106">To add a package to the Management Console</span></span>**

1.  <span data-ttu-id="e2a7b-107">在管理控制台显示的导航窗格中单击 "**程序包**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="e2a7b-107">Click the **Packages** tab in the navigation pane of the Management Console display.</span></span>

    <span data-ttu-id="e2a7b-108">该控制台将显示已添加到服务器的程序包列表以及每个程序包的状态信息。</span><span class="sxs-lookup"><span data-stu-id="e2a7b-108">The console displays the list of packages that have been added to the server along with status information about each package.</span></span> <span data-ttu-id="e2a7b-109">选择程序包后，有关程序包的详细信息将显示在 "**程序包**" 窗格中。</span><span class="sxs-lookup"><span data-stu-id="e2a7b-109">When a package is selected, detailed information about the package is displayed in the **PACKAGES** pane.</span></span>

    <span data-ttu-id="e2a7b-110">单击 "**取消分组**" 下拉列表框并指定程序包在控制台中的显示方式。</span><span class="sxs-lookup"><span data-stu-id="e2a7b-110">Click the **Ungrouped** drop-down list box and specify how the packages are to be displayed in the console.</span></span> <span data-ttu-id="e2a7b-111">也可以单击关联的列标题对程序包进行排序。</span><span class="sxs-lookup"><span data-stu-id="e2a7b-111">You can also click the associated column header to sort the packages.</span></span>

2.  <span data-ttu-id="e2a7b-112">若要指定要添加的程序包，请单击 "**添加或升级程序包**"。</span><span class="sxs-lookup"><span data-stu-id="e2a7b-112">To specify the package you want to add, click **Add or Upgrade Packages**.</span></span>

3.  <span data-ttu-id="e2a7b-113">键入要添加的程序包的完整路径。</span><span class="sxs-lookup"><span data-stu-id="e2a7b-113">Type the full path to the package that you want to add.</span></span> <span data-ttu-id="e2a7b-114">使用 UNC 或 HTTP 路径格式，例如**\\\\servername\\sharename\\foldername\\packagename.appv**或，然后 **http://server.1234/file.appv** 单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="e2a7b-114">Use the UNC or HTTP path format, for example **\\\\servername\\sharename\\foldername\\packagename.appv** or **http://server.1234/file.appv**, and then click **Add**.</span></span>

    <span data-ttu-id="e2a7b-115">**重要提示** 必须选择一个具有**appv**文件扩展名的程序包。</span><span class="sxs-lookup"><span data-stu-id="e2a7b-115">**Important** You must select a package with the **.appv** file name extension.</span></span>

     

4.  <span data-ttu-id="e2a7b-116">页面将显示 "\*\*添加 &lt; Packagename &gt; \*\*" 状态消息。</span><span class="sxs-lookup"><span data-stu-id="e2a7b-116">The page displays the status message **Adding &lt;Packagename&gt;**.</span></span> <span data-ttu-id="e2a7b-117">单击 "**导入状态**" 以检查已导入的程序包的状态。</span><span class="sxs-lookup"><span data-stu-id="e2a7b-117">Click **IMPORT STATUS** to check the status of a package that you have imported.</span></span>

    <span data-ttu-id="e2a7b-118">单击 **"确定"** 添加程序包并关闭 "**添加程序包**" 页面。</span><span class="sxs-lookup"><span data-stu-id="e2a7b-118">Click **OK** to add the package and close the **Add Package** page.</span></span> <span data-ttu-id="e2a7b-119">如果在导入过程中出现错误，请单击 "**程序包导入**" 页面上的 "**详细**信息" 以了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="e2a7b-119">If there was an error during the import, click **Detail** on the **Package Import** page for more information.</span></span> <span data-ttu-id="e2a7b-120">新添加的程序包现在在 "**程序包**" 窗格中可用。</span><span class="sxs-lookup"><span data-stu-id="e2a7b-120">The newly added package is now available in the **PACKAGES** pane.</span></span>

5.  <span data-ttu-id="e2a7b-121">单击 "**关闭**" 以关闭 "**添加或升级程序包**" 页面。</span><span class="sxs-lookup"><span data-stu-id="e2a7b-121">Click **Close** to close the **Add or Upgrade Packages** page.</span></span>

    <span data-ttu-id="e2a7b-122">已**获得有关 app-v 的建议**？</span><span class="sxs-lookup"><span data-stu-id="e2a7b-122">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="e2a7b-123">在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="e2a7b-123">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="e2a7b-124">遇到了 app-v 问题？</span><span class="sxs-lookup"><span data-stu-id="e2a7b-124">Got an App-V issue?</span></span>** <span data-ttu-id="e2a7b-125">使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="e2a7b-125">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="e2a7b-126">相关主题</span><span class="sxs-lookup"><span data-stu-id="e2a7b-126">Related topics</span></span>


[<span data-ttu-id="e2a7b-127">App-V 5.0 的操作</span><span class="sxs-lookup"><span data-stu-id="e2a7b-127">Operations for App-V 5.0</span></span>](operations-for-app-v-50.md)

 

 





