---
title: 如何使用 PowerShell 创建包加速器
description: 如何使用 PowerShell 创建包加速器
author: dansimp
ms.assetid: 0cb98394-4477-4193-8c5f-1c1773c7263a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 347572343cff058a7494574035464d66c4d61be4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798506"
---
# <span data-ttu-id="6f492-103">如何使用 PowerShell 创建包加速器</span><span class="sxs-lookup"><span data-stu-id="6f492-103">How to Create a Package Accelerator by Using PowerShell</span></span>


<span data-ttu-id="6f492-104">App-v 5.1 程序包加速器自动序列大型、复杂的应用程序。</span><span class="sxs-lookup"><span data-stu-id="6f492-104">App-V 5.1 package accelerators automatically sequence large, complex applications.</span></span> <span data-ttu-id="6f492-105">此外，当你应用 app-v 5.1 程序包加速器时，并非始终需要手动安装应用程序来创建虚拟化程序包。</span><span class="sxs-lookup"><span data-stu-id="6f492-105">Additionally, when you apply an App-V 5.1 package accelerator, you are not always required to manually install an application to create the virtualized package.</span></span>

**<span data-ttu-id="6f492-106">创建包加速器</span><span class="sxs-lookup"><span data-stu-id="6f492-106">To create a package accelerator</span></span>**

1.  <span data-ttu-id="6f492-107">安装 app-v 5.1 sequencer。</span><span class="sxs-lookup"><span data-stu-id="6f492-107">Install the App-V 5.1 sequencer.</span></span> <span data-ttu-id="6f492-108">有关安装 sequencer 的详细信息，请参阅[如何安装 sequencer](how-to-install-the-sequencer-51beta-gb18030.md)。</span><span class="sxs-lookup"><span data-stu-id="6f492-108">For more information about installing the sequencer see [How to Install the Sequencer](how-to-install-the-sequencer-51beta-gb18030.md).</span></span>

2.  <span data-ttu-id="6f492-109">若要打开 PowerShell 控制台，请单击 "**开始**"，然后键入**powershell**。</span><span class="sxs-lookup"><span data-stu-id="6f492-109">To open a PowerShell console click **Start** and type **PowerShell**.</span></span> <span data-ttu-id="6f492-110">右键单击**Windows PowerShell**，然后选择**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="6f492-110">Right-click **Windows PowerShell** and select **Run as Administrator**.</span></span> <span data-ttu-id="6f492-111">使用**AppvPackageAccelerator** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6f492-111">Use the **New-AppvPackageAccelerator** cmdlet.</span></span>

3.  <span data-ttu-id="6f492-112">若要创建程序包加速器，请确保你有用于创建加速器的 appv 包、安装媒体或安装文件，以及选择要使用的加速器使用者的自述文件。</span><span class="sxs-lookup"><span data-stu-id="6f492-112">To create a package accelerator, make sure that you have the .appv package to create an accelerator from, the installation media or installation files, and optionally a read me file for consumers of the accelerator to use.</span></span> <span data-ttu-id="6f492-113">要使用程序包加速器 cmdlet，需要以下参数：</span><span class="sxs-lookup"><span data-stu-id="6f492-113">The following parameters are required to use the package accelerator cmdlet:</span></span>

    -   <span data-ttu-id="6f492-114">**InstalledFilesPath** -指定应用程序安装路径。</span><span class="sxs-lookup"><span data-stu-id="6f492-114">**InstalledFilesPath** - specifies the application installation path.</span></span>

    -   <span data-ttu-id="6f492-115">**安装**程序-指定应用程序安装程序媒体的路径</span><span class="sxs-lookup"><span data-stu-id="6f492-115">**Installer** – specifies the path to the application installer media</span></span>

    -   <span data-ttu-id="6f492-116">**InputPackagePath** –指定 appv 包的路径</span><span class="sxs-lookup"><span data-stu-id="6f492-116">**InputPackagePath** – specifies the path to the .appv package</span></span>

    -   <span data-ttu-id="6f492-117">**Path** -指定程序包的输出目录。</span><span class="sxs-lookup"><span data-stu-id="6f492-117">**Path** – specifies the output directory for the package.</span></span>

    <span data-ttu-id="6f492-118">以下示例显示了如何创建带有 appv 包和安装媒体的程序包加速器：</span><span class="sxs-lookup"><span data-stu-id="6f492-118">The following example displays how you can create a package accelerator with an .appv package and the installation media:</span></span>

    **<span data-ttu-id="6f492-119">AppvPackageAccelerator- &lt; &gt; &lt; 输出路径的安装程序可执行文件的 &gt; 路径 &lt; 目录的 appv 文件安装程序路径的 InputPackagePath 路径&gt;</span><span class="sxs-lookup"><span data-stu-id="6f492-119">New-AppvPackageAccelerator -InputPackagePath &lt;path to the .appv file&gt; -Installer &lt;path to the installer executable&gt; -Path &lt;directory of the output path&gt;</span></span>**

    <span data-ttu-id="6f492-120">以下列表中显示了可与**AppvPackageAccelerator** cmdlet 一起使用的其他可选参数：</span><span class="sxs-lookup"><span data-stu-id="6f492-120">Additional optional parameters that can be used with the **New-AppvPackageAccelerator** cmdlet are displayed in the following list:</span></span>

    -   <span data-ttu-id="6f492-121">**AcceleratorDescriptionFile** -指定用户创建的程序包加速器说明的路径。</span><span class="sxs-lookup"><span data-stu-id="6f492-121">**AcceleratorDescriptionFile** - specifies the path to user created package accelerator instructions.</span></span> <span data-ttu-id="6f492-122">程序包加速器说明是将使用程序包加速器创建的程序包打包的 **.txt**或 **.rtf**说明文件。</span><span class="sxs-lookup"><span data-stu-id="6f492-122">The package accelerator instructions are **.txt** or **.rtf** description files that will be packaged with the package created using the package accelerator.</span></span>

    <span data-ttu-id="6f492-123">已**获得有关 app-v 的建议**？</span><span class="sxs-lookup"><span data-stu-id="6f492-123">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="6f492-124">在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="6f492-124">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="6f492-125">遇到了 app-v 问题？</span><span class="sxs-lookup"><span data-stu-id="6f492-125">Got an App-V issue?</span></span>** <span data-ttu-id="6f492-126">使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="6f492-126">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="6f492-127">相关主题</span><span class="sxs-lookup"><span data-stu-id="6f492-127">Related topics</span></span>


[<span data-ttu-id="6f492-128">使用 PowerShell 管理 App-V 5.1</span><span class="sxs-lookup"><span data-stu-id="6f492-128">Administering App-V 5.1 by Using PowerShell</span></span>](administering-app-v-51-by-using-powershell.md)

 

 





