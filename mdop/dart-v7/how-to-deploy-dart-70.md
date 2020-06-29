---
title: 如何部署 DaRT 7.0
description: 如何部署 DaRT 7.0
author: dansimp
ms.assetid: 30522441-40cb-4eca-99b4-dff758f5c647
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c2059b64e5f3ae7af8926bc00e5965598ede4288
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798198"
---
# <span data-ttu-id="58608-103">如何部署 DaRT 7.0</span><span class="sxs-lookup"><span data-stu-id="58608-103">How to Deploy DaRT 7.0</span></span>


<span data-ttu-id="58608-104">本主题提供了在你的环境中部署 Microsoft 诊断和恢复工具集（DaRT）7的说明。</span><span class="sxs-lookup"><span data-stu-id="58608-104">This topic provides instructions to deploy Microsoft Diagnostics and Recovery Toolset (DaRT)7 in your environment.</span></span> <span data-ttu-id="58608-105">本主题中的第一个过程假定你在一台管理员计算机上安装所有功能。</span><span class="sxs-lookup"><span data-stu-id="58608-105">The first procedure in this topic assumes that you are installing all functionality on one administrator computer.</span></span> <span data-ttu-id="58608-106">如果需要在多台计算机上部署或卸载 DaRT （例如，使用电子软件分发系统），则使用命令行安装选项可能更容易。</span><span class="sxs-lookup"><span data-stu-id="58608-106">When you need to deploy or uninstall DaRT on multiple computers, using an electronic software distribution system for example, it might be easier to use command line installation options.</span></span> <span data-ttu-id="58608-107">本主题的第二个过程中定义了这些选项，其中提供了可用命令行选项的示例用法。</span><span class="sxs-lookup"><span data-stu-id="58608-107">Those options are defined in the second procedure in this topic which provides example usage for the available command line options.</span></span>

<span data-ttu-id="58608-108">**重要提示** 在安装 DaRT 之前，请确保计算机满足[DaRT 7.0 支持的配置](dart-70-supported-configurations-dart-7.md)中列出的最低系统要求。</span><span class="sxs-lookup"><span data-stu-id="58608-108">**Important** Before you install DaRT, ensure that the computer meets the minimum system requirements listed in [DaRT 7.0 Supported Configurations](dart-70-supported-configurations-dart-7.md).</span></span>

 

**<span data-ttu-id="58608-109">在管理员计算机上安装 DaRT</span><span class="sxs-lookup"><span data-stu-id="58608-109">To install DaRT on an administrator computer</span></span>**

1.  <span data-ttu-id="58608-110">找到您在软件下载中收到的 DaRT 安装文件。</span><span class="sxs-lookup"><span data-stu-id="58608-110">Locate the DaRT installation files that you received as part of your software download.</span></span>

2.  <span data-ttu-id="58608-111">双击与你的系统要求相对应的 DaRT 安装文件，无论是32位还是64位。</span><span class="sxs-lookup"><span data-stu-id="58608-111">Double-click the DaRT installation file that corresponds to your system requirements, either 32-bit or 64-bit.</span></span> <span data-ttu-id="58608-112">DaRT 安装文件命名为 " **MSDaRT70.msi**"。</span><span class="sxs-lookup"><span data-stu-id="58608-112">The DaRT installation file is named **MSDaRT70.msi**.</span></span>

3.  <span data-ttu-id="58608-113">接受 Microsoft 软件许可条款，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="58608-113">Accept the Microsoft Software License Terms, and then click **Next**.</span></span>

4.  <span data-ttu-id="58608-114">选择用于安装 DaRT 的目标文件夹，选择是应为所有用户安装 DaRT 还是仅为当前用户安装 DaRT，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="58608-114">Select the destination folder for installing DaRT, select whether DaRT should be installed for all users or just the current user, and then click **Next**.</span></span>

5.  <span data-ttu-id="58608-115">选择是**典型**、**自定义**还是**完成**安装，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="58608-115">Select whether the installation should be **Typical**, **Custom**, or **Complete**, and then click **Next**.</span></span>

    -   <span data-ttu-id="58608-116">**典型**安装最常用的工具。</span><span class="sxs-lookup"><span data-stu-id="58608-116">**Typical** installs the tools that are most frequently used.</span></span> <span data-ttu-id="58608-117">对于大多数用户，建议使用此方法。</span><span class="sxs-lookup"><span data-stu-id="58608-117">This method is recommended for most users.</span></span>

    -   <span data-ttu-id="58608-118">"**自定义**" 让你可以选择已安装的工具以及它们的安装位置。</span><span class="sxs-lookup"><span data-stu-id="58608-118">**Custom** lets you select the tools that are installed and where they will be installed.</span></span> <span data-ttu-id="58608-119">建议高级用户使用此功能，尤其是在不同的支持台计算机上安装不同的 DaRT 工具时。</span><span class="sxs-lookup"><span data-stu-id="58608-119">This is recommended for advanced users, especially if you are installing different DaRT tools on different helpdesk computers.</span></span>

    -   <span data-ttu-id="58608-120">**完整**安装所有 DaRT 工具，并且需要最大磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="58608-120">**Complete** installs all DaRT tools and requires the most disk space.</span></span>

    <span data-ttu-id="58608-121">选择了安装方法后，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="58608-121">After you have selected your method of installation, click **Next**.</span></span>

6.  <span data-ttu-id="58608-122">若要开始安装，请单击 "**安装**"。</span><span class="sxs-lookup"><span data-stu-id="58608-122">To start the installation, click **Install**.</span></span>

7.  <span data-ttu-id="58608-123">安装成功完成后，单击 "**完成**" 退出向导。</span><span class="sxs-lookup"><span data-stu-id="58608-123">After the installation is completed successfully, click **Finish** to exit the wizard.</span></span>

**<span data-ttu-id="58608-124">在命令提示符处安装 DaRT</span><span class="sxs-lookup"><span data-stu-id="58608-124">To install DaRT at the command prompt</span></span>**

1.  <span data-ttu-id="58608-125">以下示例显示了如何安装所有 DaRT 功能。</span><span class="sxs-lookup"><span data-stu-id="58608-125">The following example shows how to install all DaRT functionality.</span></span>

    ``` syntax
    msiexec /i MSDaRT70.msi ADDLOCAL=CommonFiles,MSDaRTHelp,DaRTRecoveryImage,CrashAnalyzer,RemoteViewer 
    ```

2.  <span data-ttu-id="58608-126">以下示例显示了如何仅安装**DaRT 恢复映像向导**。</span><span class="sxs-lookup"><span data-stu-id="58608-126">The following example shows how to install only the **DaRT Recovery Image Wizard**.</span></span>

    ``` syntax
    msiexec /i MSDaRT70.msi ADDLOCAL=CommonFiles,MSDaRTHelp,DaRTRecoveryImage
    ```

3.  <span data-ttu-id="58608-127">以下示例显示了如何仅安装崩溃分析器和 DaRT 远程连接查看器。</span><span class="sxs-lookup"><span data-stu-id="58608-127">The following example shows how to install only the Crash Analyzer and the DaRT Remote Connection Viewer.</span></span>

    ``` syntax
    msiexec /i MSDaRT70.msi ADDLOCAL=CommonFiles,MSDaRTHelp,CrashAnalyzer,RemoteViewer 
    ```

4.  <span data-ttu-id="58608-128">以下示例为 Windows Installer 创建安装日志。</span><span class="sxs-lookup"><span data-stu-id="58608-128">The following example creates a setup log for the Windows Installer.</span></span> <span data-ttu-id="58608-129">这对于调试非常有用。</span><span class="sxs-lookup"><span data-stu-id="58608-129">This is valuable for debugging.</span></span>

    ``` syntax
    msiexec.exe /i MSDaRT70.msi /l*v log.txt 
    ```

<span data-ttu-id="58608-130">**注意** 您可以将/qn 或/qb 添加到任何 DaRT 安装命令提示符选项以执行静默式安装。</span><span class="sxs-lookup"><span data-stu-id="58608-130">**Note** You can add /qn or /qb to any of the DaRT installation command prompt options to perform a silent installation.</span></span>

 

## <span data-ttu-id="58608-131">相关主题</span><span class="sxs-lookup"><span data-stu-id="58608-131">Related topics</span></span>


[<span data-ttu-id="58608-132">将 DaRT 7.0 部署到管理员计算机</span><span class="sxs-lookup"><span data-stu-id="58608-132">Deploying DaRT 7.0 to Administrator Computers</span></span>](deploying-dart-70-to-administrator-computers-dart-7.md)

 

 





