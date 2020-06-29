---
title: 如何创建和使用项目模板
description: 如何创建和使用项目模板
author: dansimp
ms.assetid: 2063f0b3-47a1-4090-bf99-0f26b107331c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e7640b9dc1e7baec194315400ee5672dfa83f394
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798501"
---
# <span data-ttu-id="86233-103">如何创建和使用项目模板</span><span class="sxs-lookup"><span data-stu-id="86233-103">How to Create and Use a Project Template</span></span>


<span data-ttu-id="86233-104">你可以使用 app-v 5.0 项目模板来保存与现有虚拟应用程序包关联的常用设置。</span><span class="sxs-lookup"><span data-stu-id="86233-104">You can use an App-V 5.0 project template to save commonly applied settings associated with an existing virtual application package.</span></span> <span data-ttu-id="86233-105">然后，在你的环境中创建新的虚拟应用程序包时，可以应用这些设置。</span><span class="sxs-lookup"><span data-stu-id="86233-105">These settings can then be applied when you create new virtual application packages in your environment.</span></span> <span data-ttu-id="86233-106">使用项目模板可以简化创建虚拟应用程序包的过程。</span><span class="sxs-lookup"><span data-stu-id="86233-106">Using a project template can streamline the process of creating virtual application packages.</span></span>

<span data-ttu-id="86233-107">**注意** 你可以和经常在程序包升级期间应用 app-v 5.0 项目模板。</span><span class="sxs-lookup"><span data-stu-id="86233-107">**Note** You can, and often should apply an App-V 5.0 project template during a package upgrade.</span></span> <span data-ttu-id="86233-108">例如，如果使用自定义排除列表对应用程序进行了序列化，建议在升级序列化应用程序时创建和保存关联模板以供将来使用。</span><span class="sxs-lookup"><span data-stu-id="86233-108">For example, if you sequenced an application with a custom exclusion list, it is recommended that an associated template is created and saved for later use while upgrading the sequenced application.</span></span>

<span data-ttu-id="86233-109">App-v 5.0 项目模板与 App-v 5.0 应用程序加速器不同，因为 App-v 5.0 应用程序加速器是特定于应用程序的，而 app-v 5.0 项目模板可应用于多个应用程序。</span><span class="sxs-lookup"><span data-stu-id="86233-109">App-V 5.0 project templates differ from App-V 5.0 Application Accelerators because App-V 5.0 Application Accelerators are application-specific, and App-V 5.0 project templates can be applied to multiple applications.</span></span>

<span data-ttu-id="86233-110">使用以下过程创建和应用新模板。</span><span class="sxs-lookup"><span data-stu-id="86233-110">Use the following procedures to create and apply a new template.</span></span>

**<span data-ttu-id="86233-111">创建项目模板</span><span class="sxs-lookup"><span data-stu-id="86233-111">To create a project template</span></span>**

1.  <span data-ttu-id="86233-112">若要启动 app-v 5.0 排序器，请在运行 sequencer 的计算机上，单击 "**启动**  /  **所有程序**  /  **microsoft application virtualization**  /  **microsoft application virtualization sequencer**"。</span><span class="sxs-lookup"><span data-stu-id="86233-112">To start the App-V 5.0 sequencer, on the computer that is running the sequencer, click **Start** / **All Programs** / **Microsoft Application Virtualization** / **Microsoft Application Virtualization Sequencer**.</span></span>

<span data-ttu-id="86233-113">**注意** 如果虚拟应用程序包当前已在 app-v 5.0 Sequencer 控制台中打开，请跳到此过程的步骤3。</span><span class="sxs-lookup"><span data-stu-id="86233-113">**Note** If the virtual application package is currently open in the App-V 5.0 Sequencer console, skip to step 3 of this procedure.</span></span>

2. <span data-ttu-id="86233-114">若要打开现有虚拟应用程序包，其中包含要与 app-v 5.0 项目模板一起保存的设置，请单击 "**文件**  /  **打开**"，然后单击 "**编辑包**"。</span><span class="sxs-lookup"><span data-stu-id="86233-114">To open the existing virtual application package that contains the settings you want to save with the App-V 5.0 project template, click **File** / **Open**, and then click **Edit Package**.</span></span> <span data-ttu-id="86233-115">在 "**选择程序包**" 页面上，单击 "**浏览**" 并找到要打开的虚拟应用程序包。</span><span class="sxs-lookup"><span data-stu-id="86233-115">On the **Select Package** page, click **Browse** and locate the virtual application package that you want to open.</span></span> <span data-ttu-id="86233-116">单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="86233-116">Click **Edit**.</span></span>

3. <span data-ttu-id="86233-117">在 app-v 5.0 Sequencer 控制台中，若要保存模板文件，请单击 "**文件**  /  **另存为模板**"。</span><span class="sxs-lookup"><span data-stu-id="86233-117">In the App-V 5.0 Sequencer console, to save the template file, click **File** / **Save As Template**.</span></span> <span data-ttu-id="86233-118">查看将与新模板一起保存的设置后，单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="86233-118">After you have reviewed the settings that will be saved with the new template, click **OK**.</span></span> <span data-ttu-id="86233-119">指定将与新的 App-v 5.0 项目模板关联的名称。</span><span class="sxs-lookup"><span data-stu-id="86233-119">Specify a name that will be associated with the new App-V 5.0 project template.</span></span> <span data-ttu-id="86233-120">单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="86233-120">Click Save.</span></span>
   <span data-ttu-id="86233-121">新的 App-v 5.0 项目模板保存在此过程的步骤3中指定的目录中。</span><span class="sxs-lookup"><span data-stu-id="86233-121">The new App-V 5.0 project template is saved in the directory specified in step 3 of this procedure.</span></span>

**<span data-ttu-id="86233-122">应用项目模板</span><span class="sxs-lookup"><span data-stu-id="86233-122">To apply a project template</span></span>**

<span data-ttu-id="86233-123">**重要提示** 不支持与程序包加速器一起使用项目模板创建虚拟应用程序包。</span><span class="sxs-lookup"><span data-stu-id="86233-123">**Important** Creating a virtual application package using a project template in conjunction with a Package Accelerator is not supported.</span></span>

1.  <span data-ttu-id="86233-124">若要启动 app-v 5.0 排序器，请在运行 sequencer 的计算机上，单击 "**启动**  /  **所有程序**  /  **microsoft application virtualization**  /  **microsoft application virtualization sequencer**"。</span><span class="sxs-lookup"><span data-stu-id="86233-124">To start the App-V 5.0 sequencer, on the computer that is running the sequencer, click **Start** / **All Programs** / **Microsoft Application Virtualization** / **Microsoft Application Virtualization Sequencer**.</span></span>

2.  <span data-ttu-id="86233-125">若要使用 app-v 5.0 项目模板创建或升级新的虚拟应用程序包，请单击 " **File**  /  **从模板新建**文件"。</span><span class="sxs-lookup"><span data-stu-id="86233-125">To create or upgrade a new virtual application package by using an App-V 5.0 project template, click **File** / **New From Template**.</span></span>

3.  <span data-ttu-id="86233-126">若要选择要使用的项目模板，请浏览到保存项目模板的目录，选择项目模板，然后单击 "**打开**"。</span><span class="sxs-lookup"><span data-stu-id="86233-126">To select the project template that you want to use, browse to the directory where the project template is saved, select the project template, and then click **Open**.</span></span>

    <span data-ttu-id="86233-127">创建新的虚拟应用程序包。</span><span class="sxs-lookup"><span data-stu-id="86233-127">Create the new virtual application package.</span></span> <span data-ttu-id="86233-128">与指定模板一起保存的设置将应用于您创建的新虚拟应用程序包。</span><span class="sxs-lookup"><span data-stu-id="86233-128">The settings saved with the specified template will be applied to the new virtual application package that you are creating.</span></span>

    <span data-ttu-id="86233-129">已**获得有关 app-v 的建议**？</span><span class="sxs-lookup"><span data-stu-id="86233-129">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="86233-130">在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="86233-130">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="86233-131">遇到了 app-v 问题？</span><span class="sxs-lookup"><span data-stu-id="86233-131">Got an App-V issue?</span></span>** <span data-ttu-id="86233-132">使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="86233-132">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="86233-133">相关主题</span><span class="sxs-lookup"><span data-stu-id="86233-133">Related topics</span></span>


[<span data-ttu-id="86233-134">App-V 5.0 的操作</span><span class="sxs-lookup"><span data-stu-id="86233-134">Operations for App-V 5.0</span></span>](operations-for-app-v-50.md)









