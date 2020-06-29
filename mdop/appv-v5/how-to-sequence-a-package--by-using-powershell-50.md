---
title: 如何使用 PowerShell 对程序包进行排序
description: 如何使用 PowerShell 对程序包进行排序
author: dansimp
ms.assetid: b41feed9-d1c5-48a3-940c-9a21d594f4f8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: bbb9641ba75eda4d190892fa2bd0043c92ed9006
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798361"
---
# <span data-ttu-id="26981-103">如何使用 PowerShell 对程序包进行排序</span><span class="sxs-lookup"><span data-stu-id="26981-103">How to Sequence a Package by Using PowerShell</span></span>


<span data-ttu-id="26981-104">使用以下过程，使用 PowerShell 创建新的 app-v 5.0 程序包。</span><span class="sxs-lookup"><span data-stu-id="26981-104">Use the following procedure to create a new App-V 5.0 package using PowerShell.</span></span>

<span data-ttu-id="26981-105">**注意** 在使用此过程之前，必须将关联的安装程序文件复制到运行 sequencer 的计算机，并且已阅读并了解[有关应用 V 5.0 排序器和客户端部署规划](planning-for-the-app-v-50-sequencer-and-client-deployment.md)的 sequencer 部分。</span><span class="sxs-lookup"><span data-stu-id="26981-105">**Note** Before you use this procedure you must copy the associated installer files to the computer running the sequencer and you have read and understand the sequencer section of [Planning for the App-V 5.0 Sequencer and Client Deployment](planning-for-the-app-v-50-sequencer-and-client-deployment.md).</span></span>

 

**<span data-ttu-id="26981-106">使用 PowerShell 创建新的虚拟应用程序</span><span class="sxs-lookup"><span data-stu-id="26981-106">To create a new virtual application using PowerShell</span></span>**

1.  <span data-ttu-id="26981-107">安装 app-v 5.0 sequencer。</span><span class="sxs-lookup"><span data-stu-id="26981-107">Install the App-V 5.0 sequencer.</span></span> <span data-ttu-id="26981-108">有关安装 sequencer 的详细信息，请参阅[如何安装 sequencer](how-to-install-the-sequencer-beta-gb18030.md)。</span><span class="sxs-lookup"><span data-stu-id="26981-108">For more information about installing the sequencer see [How to Install the Sequencer](how-to-install-the-sequencer-beta-gb18030.md).</span></span>

2.  <span data-ttu-id="26981-109">若要打开 PowerShell 控制台，请单击 "**开始**"，然后键入**powershell**。</span><span class="sxs-lookup"><span data-stu-id="26981-109">To open a PowerShell console click **Start** and type **PowerShell**.</span></span> <span data-ttu-id="26981-110">右键单击**Windows PowerShell**，然后选择**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="26981-110">Right-click **Windows PowerShell** and select **Run as Administrator**.</span></span>

3.  <span data-ttu-id="26981-111">使用 PowerShell 控制台，键入以下内容： **import-module appvsequencer**。</span><span class="sxs-lookup"><span data-stu-id="26981-111">Using the PowerShell console, type the following: **import-module appvsequencer**.</span></span>

4.  <span data-ttu-id="26981-112">若要创建程序包，请使用**AppvSequencerPackage** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="26981-112">To create a package, use the **New-AppvSequencerPackage** cmdlet.</span></span> <span data-ttu-id="26981-113">创建程序包需要以下参数：</span><span class="sxs-lookup"><span data-stu-id="26981-113">The following parameters are required to create a package:</span></span>

    -   <span data-ttu-id="26981-114">**Name** -指定程序包的名称。</span><span class="sxs-lookup"><span data-stu-id="26981-114">**Name** - specifies the name of the package.</span></span>

    -   <span data-ttu-id="26981-115">**PrimaryVirtualApplicationDirectory** -指定将用于安装应用程序的目录的路径。</span><span class="sxs-lookup"><span data-stu-id="26981-115">**PrimaryVirtualApplicationDirectory** - specifies the path to the directory that will be used to install the application.</span></span> <span data-ttu-id="26981-116">此路径必须存在。</span><span class="sxs-lookup"><span data-stu-id="26981-116">This path must exist.</span></span>

    -   <span data-ttu-id="26981-117">**安装**程序-指定关联的应用程序安装程序的路径。</span><span class="sxs-lookup"><span data-stu-id="26981-117">**Installer** - specifies the path to the associated application installer.</span></span>

    -   <span data-ttu-id="26981-118">**Path** -指定程序包的输出目录。</span><span class="sxs-lookup"><span data-stu-id="26981-118">**Path** - specifies the output directory for the package.</span></span>

    <span data-ttu-id="26981-119">例如：</span><span class="sxs-lookup"><span data-stu-id="26981-119">For example:</span></span>

    **<span data-ttu-id="26981-120">新-AppvSequencerPackage-程序包的名称-程序包的 &lt; &gt; PrimaryVirtualApplicationDirectory &lt; 路径到 &gt; &lt; 安装程序可执行文件的 &gt; OutputPath &lt; 目录的程序包根安装程序路径&gt;</span><span class="sxs-lookup"><span data-stu-id="26981-120">New-AppvSequencerPackage –Name &lt;name of Package&gt; -PrimaryVirtualApplicationDirectory &lt;path to the package root&gt; -Installer &lt;path to the installer executable&gt; -OutputPath &lt;directory of the output path&gt;</span></span>**

    <span data-ttu-id="26981-121">等待排序器创建程序包。</span><span class="sxs-lookup"><span data-stu-id="26981-121">Wait for the sequencer to create the package.</span></span> <span data-ttu-id="26981-122">使用 PowerShell 创建程序包可能需要一些时间。</span><span class="sxs-lookup"><span data-stu-id="26981-122">Creating a package using PowerShell can take time.</span></span> <span data-ttu-id="26981-123">如果未成功创建程序包，则会返回错误。</span><span class="sxs-lookup"><span data-stu-id="26981-123">If the package was not created successfully an error will be returned.</span></span>

    <span data-ttu-id="26981-124">以下列表显示可与**AppvSequencerPackage** cmdlet 一起使用的其他可选参数：</span><span class="sxs-lookup"><span data-stu-id="26981-124">The following list displays additional optional parameters that can be used with **New-AppvSequencerPackage** cmdlet:</span></span>

    -   <span data-ttu-id="26981-125">AcceleratorFilePath –指定要生成程序包的加速器 .cab 文件的路径。</span><span class="sxs-lookup"><span data-stu-id="26981-125">AcceleratorFilePath – specifies the path to the accelerator .cab file to generate a package.</span></span>

    -   <span data-ttu-id="26981-126">InstalledFilesPath-指定保存应用程序的本地已安装文件的路径。</span><span class="sxs-lookup"><span data-stu-id="26981-126">InstalledFilesPath - specifies the path to where the local installed files of the application are saved.</span></span>

    -   <span data-ttu-id="26981-127">InstallMediaPath-指定安装媒体的路径</span><span class="sxs-lookup"><span data-stu-id="26981-127">InstallMediaPath - specifies the path to where the installation media is</span></span>

    -   <span data-ttu-id="26981-128">TemplateFilePath-如果要自定义排序过程，请指定模板文件的路径。</span><span class="sxs-lookup"><span data-stu-id="26981-128">TemplateFilePath - specifies the path to a template file if you want to customize the sequencing process.</span></span>

    -   <span data-ttu-id="26981-129">FullLoad-指定程序包必须完全下载到运行 App-v 5.0 的计算机，然后才能打开。</span><span class="sxs-lookup"><span data-stu-id="26981-129">FullLoad - specifies that the package must be fully downloaded to the computer running the App-V 5.0 before it can be opened.</span></span>

    <span data-ttu-id="26981-130">已**获得有关 app-v 的建议**？</span><span class="sxs-lookup"><span data-stu-id="26981-130">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="26981-131">在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="26981-131">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="26981-132">遇到了 app-v 问题？</span><span class="sxs-lookup"><span data-stu-id="26981-132">Got an App-V issue?</span></span>** <span data-ttu-id="26981-133">使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="26981-133">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="26981-134">相关主题</span><span class="sxs-lookup"><span data-stu-id="26981-134">Related topics</span></span>


[<span data-ttu-id="26981-135">使用 PowerShell 管理 App-V</span><span class="sxs-lookup"><span data-stu-id="26981-135">Administering App-V by Using PowerShell</span></span>](administering-app-v-by-using-powershell.md)

 

 





