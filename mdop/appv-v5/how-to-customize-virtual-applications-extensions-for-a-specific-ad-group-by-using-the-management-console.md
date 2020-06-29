---
title: 如何使用管理控制台为特定 AD 组自定义虚拟应用程序扩展
description: 如何使用管理控制台为特定 AD 组自定义虚拟应用程序扩展
author: dansimp
ms.assetid: 4f249ee3-cc2d-4b1e-afe5-d1cbf9cabd88
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 57ce4b82cc552e0a4adc2272f849111d8da0be71
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798499"
---
# <span data-ttu-id="e3420-103">如何使用管理控制台为特定 AD 组自定义虚拟应用程序扩展</span><span class="sxs-lookup"><span data-stu-id="e3420-103">How to Customize Virtual Applications Extensions for a Specific AD Group by Using the Management Console</span></span>


<span data-ttu-id="e3420-104">使用以下过程自定义 Active Directory （AD）组的虚拟应用程序扩展。</span><span class="sxs-lookup"><span data-stu-id="e3420-104">Use the following procedure to customize the virtual application extensions for an Active Directory (AD) group.</span></span>

**<span data-ttu-id="e3420-105">自定义 AD 组的虚拟应用程序扩展</span><span class="sxs-lookup"><span data-stu-id="e3420-105">To customize virtual applications extensions for an AD group</span></span>**

1.  <span data-ttu-id="e3420-106">若要查看要配置的程序包，请打开 App-v 5.0 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="e3420-106">To view the package that you want to configure, open the App-V 5.0 Management Console.</span></span> <span data-ttu-id="e3420-107">若要查看分配给给定用户组的配置，请选择该程序包，然后右键单击该程序包名称，然后选择 "**编辑 active directory 访问**"。</span><span class="sxs-lookup"><span data-stu-id="e3420-107">To view the configuration that is assigned to a given user group, select the package, and right-click the package name and select **Edit active directory access**.</span></span> <span data-ttu-id="e3420-108">或者，选择程序包，然后单击 "**广告访问**" 窗格中的 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="e3420-108">Alternatively, select the package and click **EDIT** in the **AD ACCESS** pane.</span></span>

2.  <span data-ttu-id="e3420-109">若要自定义广告组，您可以从**具有 Access 的广告实体**列表中找到该组。</span><span class="sxs-lookup"><span data-stu-id="e3420-109">To customize an AD group, you can find the group from the list of **AD Entities with Access**.</span></span> <span data-ttu-id="e3420-110">然后，使用 "**分配的配置**" 窗格中的下拉框，选择 "**自定义**"，然后单击 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="e3420-110">Then, using the drop-down box in the **Assigned Configuration** pane, select **Custom**, and then click **EDIT**.</span></span>

3.  <span data-ttu-id="e3420-111">若要禁用给定应用程序的所有扩展，请清除 "**启用**"。</span><span class="sxs-lookup"><span data-stu-id="e3420-111">To disable all extensions for a given application, clear **ENABLE**.</span></span>

    <span data-ttu-id="e3420-112">若要为所选应用程序添加新的快捷方式，请右键单击 "**快捷方式**" 窗格中的应用程序，然后选择 "**添加新快捷方式**"。</span><span class="sxs-lookup"><span data-stu-id="e3420-112">To add a new shortcut for the selected application, right-click the application in the **SHORTCUTS** pane, and select **Add new shortcut**.</span></span> <span data-ttu-id="e3420-113">若要删除快捷方式，请右键单击 "**快捷方式**" 窗格中的应用程序，然后选择 "**删除快捷方式**"。</span><span class="sxs-lookup"><span data-stu-id="e3420-113">To remove a shortcut, right-click the application in the **SHORTCUTS** pane, and select **Remove Shortcut**.</span></span> <span data-ttu-id="e3420-114">若要编辑现有快捷方式，请右键单击该应用程序，然后选择 "**编辑快捷方式**"。</span><span class="sxs-lookup"><span data-stu-id="e3420-114">To edit an existing shortcut, right-click the application, and select **Edit Shortcut**.</span></span>

4.  <span data-ttu-id="e3420-115">若要查看任何其他应用程序扩展，请单击 "**高级**"，然后单击 "**导出配置**"。</span><span class="sxs-lookup"><span data-stu-id="e3420-115">To view any other application extensions, click **Advanced**, and click **Export Configuration**.</span></span> <span data-ttu-id="e3420-116">键入文件名，然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="e3420-116">Type in a filename and click **Save**.</span></span> <span data-ttu-id="e3420-117">你可以使用配置文件查看与程序包关联的所有应用程序扩展。</span><span class="sxs-lookup"><span data-stu-id="e3420-117">You can view all application extensions that are associated with the package using the configuration file.</span></span>

5.  <span data-ttu-id="e3420-118">若要编辑其他应用程序扩展，请修改配置文件，然后单击 "**导入并覆盖此配置**"。</span><span class="sxs-lookup"><span data-stu-id="e3420-118">To edit additional application extensions, modify the configuration file and click **Import and Overwrite this Configuration**.</span></span> <span data-ttu-id="e3420-119">选择修改后的文件，然后单击 "**打开**"。</span><span class="sxs-lookup"><span data-stu-id="e3420-119">Select the modified file and click **Open**.</span></span> <span data-ttu-id="e3420-120">在对话框中，单击 "**覆盖**" 以完成该过程。</span><span class="sxs-lookup"><span data-stu-id="e3420-120">In the dialog, click **Overwrite** to complete the process.</span></span>

    <span data-ttu-id="e3420-121">已**获得有关 app-v 的建议**？</span><span class="sxs-lookup"><span data-stu-id="e3420-121">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="e3420-122">在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="e3420-122">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="e3420-123">遇到了 app-v 问题？</span><span class="sxs-lookup"><span data-stu-id="e3420-123">Got an App-V issue?</span></span>** <span data-ttu-id="e3420-124">使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="e3420-124">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="e3420-125">相关主题</span><span class="sxs-lookup"><span data-stu-id="e3420-125">Related topics</span></span>


[<span data-ttu-id="e3420-126">App-V 5.0 的操作</span><span class="sxs-lookup"><span data-stu-id="e3420-126">Operations for App-V 5.0</span></span>](operations-for-app-v-50.md)

 

 





