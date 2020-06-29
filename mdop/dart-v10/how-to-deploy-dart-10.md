---
title: 如何部署 DaRT 10
description: 如何部署 DaRT 10
author: dansimp
ms.assetid: 13e8ba20-21c3-4870-94ed-6d3106d69f21
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 9e78f55e238cce16798525915487e4b753d92e6c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798204"
---
# <span data-ttu-id="8118a-103">如何部署 DaRT 10</span><span class="sxs-lookup"><span data-stu-id="8118a-103">How to Deploy DaRT 10</span></span>


<span data-ttu-id="8118a-104">以下说明介绍了如何在你的环境中部署 Microsoft Diagnostics 和恢复工具集（DaRT）10。</span><span class="sxs-lookup"><span data-stu-id="8118a-104">The following instructions explain how to deploy Microsoft Diagnostics and Recovery Toolset (DaRT) 10 in your environment.</span></span> <span data-ttu-id="8118a-105">若要获取 DaRT 软件，请参阅[如何获取 MDOP](https://go.microsoft.com/fwlink/?LinkId=322049)。</span><span class="sxs-lookup"><span data-stu-id="8118a-105">To get the DaRT software, see [How to Get MDOP](https://go.microsoft.com/fwlink/?LinkId=322049).</span></span> <span data-ttu-id="8118a-106">假定你在一台管理员计算机上安装所有功能。</span><span class="sxs-lookup"><span data-stu-id="8118a-106">It is assumed that you are installing all functionality on one administrator computer.</span></span> <span data-ttu-id="8118a-107">如果需要在多台计算机上部署或卸载 DaRT 10，例如使用电子软件分发系统，则使用命令行安装选项可能更容易。</span><span class="sxs-lookup"><span data-stu-id="8118a-107">If you need to deploy or uninstall DaRT 10 on multiple computers, using an electronic software distribution system, for example, it might be easier to use command line installation options.</span></span> <span data-ttu-id="8118a-108">本部分提供了可用命令行选项的说明和示例。</span><span class="sxs-lookup"><span data-stu-id="8118a-108">Descriptions and examples of the available command line options are provided in this section.</span></span>

<span data-ttu-id="8118a-109">**重要提示** 在安装 DaRT 之前，请参阅[DaRT 10 支持的配置](dart-10-supported-configurations.md)，以确保已安装所有必备软件，并且计算机满足最低系统要求。</span><span class="sxs-lookup"><span data-stu-id="8118a-109">**Important** Before you install DaRT, see [DaRT 10 Supported Configurations](dart-10-supported-configurations.md) to ensure that you have installed all of the prerequisite software and that the computer meets the minimum system requirements.</span></span> <span data-ttu-id="8118a-110">在其上安装 DaRT 的计算机必须运行 Windows 10。</span><span class="sxs-lookup"><span data-stu-id="8118a-110">The computer onto which you install DaRT must be running Windows 10.</span></span>

 

<span data-ttu-id="8118a-111">你可以使用以下两种不同的配置之一安装 DaRT：</span><span class="sxs-lookup"><span data-stu-id="8118a-111">You can install DaRT using one of two different configurations:</span></span>

-   <span data-ttu-id="8118a-112">在管理员计算机上安装 DaRT 和所有 DaRT 工具。</span><span class="sxs-lookup"><span data-stu-id="8118a-112">Install DaRT and all of the DaRT tools on the administrator computer.</span></span>

-   <span data-ttu-id="8118a-113">仅在管理员计算机上安装创建 DaRT 恢复映像所需的工具，然后在技术支持计算机上安装**远程连接查看器**和**故障分析器**（可选）。</span><span class="sxs-lookup"><span data-stu-id="8118a-113">Install on the administrator computer only the tools that you need to create the DaRT recovery image, and then install the **Remote Connection Viewer** and, optionally, **Crash Analyzer** on a help desk computer.</span></span>

<span data-ttu-id="8118a-114">DaRT 安装文件在32位和64位版本中均可用。</span><span class="sxs-lookup"><span data-stu-id="8118a-114">The DaRT installation file is available in both 32-bit and 64-bit versions.</span></span> <span data-ttu-id="8118a-115">安装与运行 DaRT 恢复映像向导的计算机的体系结构相匹配的版本，而不是要创建的恢复映像的计算机体系结构。</span><span class="sxs-lookup"><span data-stu-id="8118a-115">Install the version that matches the architecture of the computer on which you are running the DaRT Recovery Image wizard, not the computer architecture of the recovery image that you are creating.</span></span>

<span data-ttu-id="8118a-116">你可以使用 DaRT 安装文件的任一版本创建32位或64位计算机的恢复映像，但不能为32位和64位计算机创建一个恢复映像。</span><span class="sxs-lookup"><span data-stu-id="8118a-116">You can use either version of the DaRT installation file to create a recovery image for either 32-bit or 64-bit computers, but you cannot create one recovery image for both 32-bit and 64-bit computers.</span></span>

**<span data-ttu-id="8118a-117">在管理员计算机上安装 DaRT 和所有 DaRT 工具</span><span class="sxs-lookup"><span data-stu-id="8118a-117">To install DaRT and all DaRT tools on an administrator computer</span></span>**

1.  <span data-ttu-id="8118a-118">下载32位或64位版本的 DaRT 10 安装程序文件。</span><span class="sxs-lookup"><span data-stu-id="8118a-118">Download the 32-bit or 64-bit version of the DaRT 10 installer file.</span></span> <span data-ttu-id="8118a-119">选择与要安装 DaRT 的计算机相匹配的体系结构，并运行 DaRT 恢复映像向导。</span><span class="sxs-lookup"><span data-stu-id="8118a-119">Choose the architecture that matches the computer on which you are installing DaRT and running the DaRT Recovery Image wizard.</span></span>

2.  <span data-ttu-id="8118a-120">在下载了 DaRT 10 的文件夹中，运行与你的系统要求对应的**MSDaRT.msi**安装文件。</span><span class="sxs-lookup"><span data-stu-id="8118a-120">From the folder into which you downloaded DaRT 10, run the **MSDaRT.msi** installation file that corresponds to your system requirements.</span></span>

3.  <span data-ttu-id="8118a-121">在 "**欢迎使用 Microsoft DaRT 10 安装向导**" 页面上，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="8118a-121">On the **Welcome to the Microsoft DaRT 10 Setup Wizard** page, click **Next**.</span></span>

4.  <span data-ttu-id="8118a-122">接受 Microsoft 软件许可条款，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="8118a-122">Accept the Microsoft Software License Terms, and then click **Next**.</span></span>

5.  <span data-ttu-id="8118a-123">在 " **Microsoft 更新**" 页面上，选择 "**当我检查更新时使用 Microsoft 更新**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="8118a-123">On the **Microsoft Update** page, select **Use Microsoft Update when I check for updates**, and then click **Next**.</span></span>

6.  <span data-ttu-id="8118a-124">在 "**选择安装文件夹**" 页面上，选择一个文件夹，或单击 "**下一步**" 以在默认安装位置安装 DaRT。</span><span class="sxs-lookup"><span data-stu-id="8118a-124">On the **Select Installation Folder** page, select a folder, or click **Next** to install DaRT in the default installation location.</span></span>

7.  <span data-ttu-id="8118a-125">在 "**安装选项**" 页面上，选择要安装的 dart 功能，或单击 "**下一步**" 以安装 dart 和所有功能。</span><span class="sxs-lookup"><span data-stu-id="8118a-125">On the **Setup Options** page, select the DaRT features that you want to install, or click **Next** to install DaRT with all of the features.</span></span>

8.  <span data-ttu-id="8118a-126">若要开始安装，请单击 "**安装**"。</span><span class="sxs-lookup"><span data-stu-id="8118a-126">To start the installation, click **Install**.</span></span>

9.  <span data-ttu-id="8118a-127">安装成功完成后，单击 "**完成**" 退出向导。</span><span class="sxs-lookup"><span data-stu-id="8118a-127">After the installation has completed successfully, click **Finish** to exit the wizard.</span></span>

## <span data-ttu-id="8118a-128">使用命令提示符在管理员计算机上安装 DaRT 和所有 DaRT 工具</span><span class="sxs-lookup"><span data-stu-id="8118a-128">To install DaRT and all DaRT tools on an administrator computer by using a command prompt</span></span>


<span data-ttu-id="8118a-129">安装或卸载 DaRT 时，可以选择在命令提示符处运行安装文件。</span><span class="sxs-lookup"><span data-stu-id="8118a-129">When you install or uninstall DaRT, you have the option of running the installation files at the command prompt.</span></span> <span data-ttu-id="8118a-130">本部分介绍了在命令提示符处安装或卸载 DaRT 时可以指定的不同选项的一些示例。</span><span class="sxs-lookup"><span data-stu-id="8118a-130">This section describes some examples of different options that you can specify when you install or uninstall DaRT at the command prompt.</span></span>

<span data-ttu-id="8118a-131">以下示例显示了如何安装所有 DaRT 功能。</span><span class="sxs-lookup"><span data-stu-id="8118a-131">The following example shows how to install all DaRT functionality.</span></span>

``` syntax
msiexec /i MSDaRT.msi ADDLOCAL=CommonFiles, DaRTRecoveryImage,CrashAnalyzer,RemoteViewer 
```

<span data-ttu-id="8118a-132">以下示例显示了如何仅安装 DaRT 恢复映像向导。</span><span class="sxs-lookup"><span data-stu-id="8118a-132">The following example shows how to install only the DaRT Recovery Image wizard.</span></span>

``` syntax
msiexec /i MSDaRT.msi ADDLOCAL=CommonFiles, ,DaRTRecoveryImage
```

<span data-ttu-id="8118a-133">以下示例显示了如何仅安装崩溃分析器和 DaRT 远程连接查看器。</span><span class="sxs-lookup"><span data-stu-id="8118a-133">The following example shows how to install only the Crash Analyzer and the DaRT Remote Connection Viewer.</span></span>

``` syntax
msiexec /i MSDaRT.msi ADDLOCAL=CommonFiles,CrashAnalyzer,RemoteViewer 
```

<span data-ttu-id="8118a-134">以下示例为 Windows Installer 创建安装日志。</span><span class="sxs-lookup"><span data-stu-id="8118a-134">The following example creates a setup log for the Windows Installer.</span></span> <span data-ttu-id="8118a-135">这对于调试非常有用。</span><span class="sxs-lookup"><span data-stu-id="8118a-135">This is valuable for debugging.</span></span>

``` syntax
msiexec.exe /i MSDaRT.msi /l*v log.txt 
```

<span data-ttu-id="8118a-136">**注意** 你可以添加/qn 或/qb 以执行静默式安装。</span><span class="sxs-lookup"><span data-stu-id="8118a-136">**Note** You can add /qn or /qb to perform a silent installation.</span></span>

 

**<span data-ttu-id="8118a-137">验证 DaRT 安装</span><span class="sxs-lookup"><span data-stu-id="8118a-137">To validate the DaRT installation</span></span>**

1.  <span data-ttu-id="8118a-138">单击 "**开始**"，然后选择 "**诊断和恢复工具集**"。</span><span class="sxs-lookup"><span data-stu-id="8118a-138">Click **Start**, and select **Diagnostics and Recovery Toolset**.</span></span>

    <span data-ttu-id="8118a-139">将打开 "**诊断和恢复工具集**" 窗口。</span><span class="sxs-lookup"><span data-stu-id="8118a-139">The **Diagnostics and Recovery Toolset** window opens.</span></span>

2.  <span data-ttu-id="8118a-140">检查您选择安装的所有 DaRT 工具是否已成功安装。</span><span class="sxs-lookup"><span data-stu-id="8118a-140">Check that all of the DaRT tools that you selected for installation were successfully installed.</span></span>

## <span data-ttu-id="8118a-141">相关主题</span><span class="sxs-lookup"><span data-stu-id="8118a-141">Related topics</span></span>


[<span data-ttu-id="8118a-142">将 DaRT 10 部署到管理员计算机</span><span class="sxs-lookup"><span data-stu-id="8118a-142">Deploying DaRT 10 to Administrator Computers</span></span>](deploying-dart-10-to-administrator-computers.md)

 

 





