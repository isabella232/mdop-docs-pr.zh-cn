---
title: 在管理控制台中配置应用程序和默认虚拟应用程序扩展
description: 如何使用管理控制台查看和配置应用程序和默认虚拟应用程序扩展
author: dansimp
ms.assetid: 1e1941d3-fb22-4077-8ec6-7a0cb80335d8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 09/26/2019
ms.openlocfilehash: 7c29ba0e40cf1adbc2b2297124cfb245a65a7ffe
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798612"
---
#   <span data-ttu-id="ec85c-103">在管理控制台中配置应用程序和默认虚拟应用程序扩展</span><span class="sxs-lookup"><span data-stu-id="ec85c-103">Configure Applications and Default Virtual Application Extensions in Management Console</span></span>

<span data-ttu-id="ec85c-104">使用以下过程*查看*和*配置*默认程序包扩展。</span><span class="sxs-lookup"><span data-stu-id="ec85c-104">Use the following procedure to *view* and *configure* default package extensions.</span></span>

**<span data-ttu-id="ec85c-105">查看和配置默认虚拟应用程序扩展</span><span class="sxs-lookup"><span data-stu-id="ec85c-105">To view and configure default virtual application extensions</span></span>**

1.  <span data-ttu-id="ec85c-106">若要查看要配置的程序包，请打开 App-v 5.1 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="ec85c-106">To view the package that you want to configure, open the App-V 5.1 Management Console.</span></span> <span data-ttu-id="ec85c-107">选择要配置的程序包，右键单击程序包名称，然后选择 "**编辑默认配置**"。</span><span class="sxs-lookup"><span data-stu-id="ec85c-107">Select the package that you want to configure, right-click the package name and select **edit default configuration**.</span></span>

2.  <span data-ttu-id="ec85c-108">若要查看指定程序包中包含的应用程序，请在 "**默认配置**" 窗格中单击 "**应用程序**"。</span><span class="sxs-lookup"><span data-stu-id="ec85c-108">To view the applications contained in the specified package, in the **Default Configuration** pane, click **Applications**.</span></span> <span data-ttu-id="ec85c-109">若要查看该程序包的快捷方式，请单击 "**快捷方式**"。</span><span class="sxs-lookup"><span data-stu-id="ec85c-109">To view the shortcuts for that package, click **Shortcuts**.</span></span> <span data-ttu-id="ec85c-110">若要查看该程序包的文件类型关联，请单击 "**文件类型**"。</span><span class="sxs-lookup"><span data-stu-id="ec85c-110">To view the file type associations for that package, click **File Types**.</span></span>

3.  <span data-ttu-id="ec85c-111">若要启用应用程序扩展，请选择 "**启用**"。</span><span class="sxs-lookup"><span data-stu-id="ec85c-111">To enable the application extensions, select **ENABLE**.</span></span>

    <span data-ttu-id="ec85c-112">若要启用快捷方式，请选择 "**启用快捷方式**"。</span><span class="sxs-lookup"><span data-stu-id="ec85c-112">To enable shortcuts, select **ENABLE SHORTCUTS**.</span></span> <span data-ttu-id="ec85c-113">若要为所选应用程序添加新的快捷方式，请右键单击 "**快捷方式**" 窗格中的应用程序，然后选择 "**添加新快捷方式**"。</span><span class="sxs-lookup"><span data-stu-id="ec85c-113">To add a new shortcut for the selected application, right-click the application in the **SHORTCUTS** pane and select **Add new shortcut**.</span></span> <span data-ttu-id="ec85c-114">若要删除快捷方式，请右键单击 "**快捷方式**" 窗格中的应用程序，然后选择 "**删除快捷方式**"。</span><span class="sxs-lookup"><span data-stu-id="ec85c-114">To remove a shortcut, right-click the application in the **SHORTCUTS** pane and select **Remove Shortcut**.</span></span> <span data-ttu-id="ec85c-115">若要编辑现有快捷方式，请右键单击该应用程序，然后选择 "**编辑快捷方式**"。</span><span class="sxs-lookup"><span data-stu-id="ec85c-115">To edit an existing shortcut, right-click the application and select **Edit Shortcut**.</span></span>

4.  <span data-ttu-id="ec85c-116">若要查看任何其他应用程序扩展，请单击 "**高级**"，然后单击 "**导出配置**"。</span><span class="sxs-lookup"><span data-stu-id="ec85c-116">To view any other application extensions, click **Advanced** and click **Export Configuration**.</span></span> <span data-ttu-id="ec85c-117">键入文件名，然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="ec85c-117">Type in a filename and click **Save**.</span></span> <span data-ttu-id="ec85c-118">你可以使用配置文件查看与程序包关联的所有应用程序扩展。</span><span class="sxs-lookup"><span data-stu-id="ec85c-118">You can view all application extensions associated with the package using the configuration file.</span></span>

5.  <span data-ttu-id="ec85c-119">若要编辑其他应用程序扩展，请修改配置文件，然后单击 "**导入并覆盖此配置**"。</span><span class="sxs-lookup"><span data-stu-id="ec85c-119">To edit other application extensions, modify the configuration file and click **Import and Overwrite this Configuration**.</span></span> <span data-ttu-id="ec85c-120">选择修改后的文件，然后单击 "**打开**"。</span><span class="sxs-lookup"><span data-stu-id="ec85c-120">Select the modified file and click **Open**.</span></span> <span data-ttu-id="ec85c-121">在对话框中，单击 "**覆盖**" 以完成该过程。</span><span class="sxs-lookup"><span data-stu-id="ec85c-121">In the dialog box, click **Overwrite** to complete the process.</span></span>

><span data-ttu-id="ec85c-122">**注意**如果上载失败且配置文件的大小高于4MB，则需要增加服务器所允许的最大文件大小。</span><span class="sxs-lookup"><span data-stu-id="ec85c-122">**Note** If the upload fails and the size of your configuration file is above 4MB, you will need to increase the maximum file size allowed by the server.</span></span> <span data-ttu-id="ec85c-123">可通过将 maxRequestLength 属性添加为大于配置文件（KB）的值的 httpRuntime 元素添加到的行26上的元素来完成此操作 `C:\Program Files\Microsoft Application Virtualization Server\ManagementService\Web.config` 。</span><span class="sxs-lookup"><span data-stu-id="ec85c-123">This can be done by adding the maxRequestLength attribute with a value greater than the size of your configuration file (in KB) to the httpRuntime element on line 26 of `C:\Program Files\Microsoft Application Virtualization Server\ManagementService\Web.config`.</span></span>  
<span data-ttu-id="ec85c-124">例如，更改 `<httpRuntime targetFramework="4.5"/>` 为 `<httpRuntime targetFramework="4.5" maxRequestLength="8192"/>` 将把最大大小增加到8mb</span><span class="sxs-lookup"><span data-stu-id="ec85c-124">For example, changing `<httpRuntime targetFramework="4.5"/>` to `<httpRuntime targetFramework="4.5" maxRequestLength="8192"/>` will increase the maximum size to 8MB</span></span>


<span data-ttu-id="ec85c-125">已**获得有关 app-v 的建议**？</span><span class="sxs-lookup"><span data-stu-id="ec85c-125">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="ec85c-126">在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="ec85c-126">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="ec85c-127">遇到了 app-v 问题？</span><span class="sxs-lookup"><span data-stu-id="ec85c-127">Got an App-V issue?</span></span>** <span data-ttu-id="ec85c-128">使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="ec85c-128">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="ec85c-129">相关主题</span><span class="sxs-lookup"><span data-stu-id="ec85c-129">Related topics</span></span>


[<span data-ttu-id="ec85c-130">App-V 5.1 的操作</span><span class="sxs-lookup"><span data-stu-id="ec85c-130">Operations for App-V 5.1</span></span>](operations-for-app-v-51.md)

 

 





