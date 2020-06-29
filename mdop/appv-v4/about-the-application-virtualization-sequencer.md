---
title: 关于 Application Virtualization Sequencer
description: 关于 Application Virtualization Sequencer
author: dansimp
ms.assetid: bee193ca-58bd-40c9-b41a-310435633895
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 83709bcceabe3312fba34512b47d28a24b4dc52c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802440"
---
# <span data-ttu-id="5745e-103">关于 Application Virtualization Sequencer</span><span class="sxs-lookup"><span data-stu-id="5745e-103">About the Application Virtualization Sequencer</span></span>


<span data-ttu-id="5745e-104">Microsoft Application Virtualization （App-v） Sequencer 监视和记录应用程序的所有安装和设置进程，并创建以下文件： **.ico**、 **OSD**、 **SFT**和**SPRJ**。</span><span class="sxs-lookup"><span data-stu-id="5745e-104">The Microsoft Application Virtualization (App-V) Sequencer monitors and records all installation and setup processes for an application and creates the following files: **ICO**, **OSD**, **SFT**, and **SPRJ**.</span></span> <span data-ttu-id="5745e-105">这些文件包含有关应用程序的所有必要信息，以便应用程序可以在目标计算机上的虚拟环境中运行。</span><span class="sxs-lookup"><span data-stu-id="5745e-105">These files contain all the necessary information about an application so the application can run in a virtual environment on target computers.</span></span> <span data-ttu-id="5745e-106">你可以使用 Microsoft Application Virtualization （App-v） Sequencer 创建虚拟应用程序。</span><span class="sxs-lookup"><span data-stu-id="5745e-106">You can use the Microsoft Application Virtualization (App-V) Sequencer to create virtual applications.</span></span> <span data-ttu-id="5745e-107">对应用程序进行排序后，可以将其流式传输到目标计算机，或者目标计算机可以通过下载虚拟应用程序包的内容并在本地运行应用程序来运行虚拟应用程序。</span><span class="sxs-lookup"><span data-stu-id="5745e-107">After you sequence an application, it can be streamed to target computers, or target computers can run the virtual application by downloading the contents of the virtual application package and running the application locally.</span></span>

<span data-ttu-id="5745e-108">**重要提示** 若要运行虚拟应用程序包，目标计算机必须运行应用的相应版本的 App-v 客户端。</span><span class="sxs-lookup"><span data-stu-id="5745e-108">**Important** To run a virtual application package the target computer must be running the appropriate version of the App-V client.</span></span>

 

<span data-ttu-id="5745e-109">虚拟应用程序包在目标计算机上运行，但不与目标计算机上的基础操作系统交互，因为每个应用程序都在虚拟环境中运行，并且与在目标计算机上安装或运行的其他应用程序隔离。</span><span class="sxs-lookup"><span data-stu-id="5745e-109">Virtual application packages run on target computers without interacting with the underlying operating system on the target computer because each application runs in a virtual environment and is isolated from other applications that are installed or running on the target computer.</span></span> <span data-ttu-id="5745e-110">这种隔离可减少应用程序冲突，并有助于减少所需的应用程序预部署测试量。</span><span class="sxs-lookup"><span data-stu-id="5745e-110">This isolation can reduce application conflicts and can help decrease the required amount of application pre-deployment testing.</span></span>

## <span data-ttu-id="5745e-111">Sequencer 术语</span><span class="sxs-lookup"><span data-stu-id="5745e-111">Sequencer Terminology</span></span>


<a href="" id="application-virtualization-drive"></a><span data-ttu-id="5745e-112">Application Virtualization 驱动器</span><span class="sxs-lookup"><span data-stu-id="5745e-112">Application Virtualization drive</span></span>  
<span data-ttu-id="5745e-113">应用程序虚拟化驱动器是运行顺序应用程序的目标计算机上的默认驱动器（Q:\）。</span><span class="sxs-lookup"><span data-stu-id="5745e-113">The application virtualization drive is the default drive (Q:\) on the target computer from which sequenced applications are run.</span></span>

<a href="" id="ico-file"></a><span data-ttu-id="5745e-114">.ICO 文件</span><span class="sxs-lookup"><span data-stu-id="5745e-114">ICO file</span></span>  
<span data-ttu-id="5745e-115">客户端桌面上的图标文件，用于启动序列化的应用程序。</span><span class="sxs-lookup"><span data-stu-id="5745e-115">The icon file on the client desktop which is used to launch a sequenced application.</span></span>

<a href="" id="installation-directory"></a><span data-ttu-id="5745e-116">安装目录</span><span class="sxs-lookup"><span data-stu-id="5745e-116">Installation directory</span></span>  
<span data-ttu-id="5745e-117">在安装期间，sequencer 用于放置安装文件的目录。</span><span class="sxs-lookup"><span data-stu-id="5745e-117">The directory used by the sequencer to place installation files during setup.</span></span>

<a href="" id="open-software-descriptor--osd--file"></a><span data-ttu-id="5745e-118">开放软件描述符（OSD）文件</span><span class="sxs-lookup"><span data-stu-id="5745e-118">Open Software Descriptor (OSD) file</span></span>  
<span data-ttu-id="5745e-119">基于 XML 的文件，指示 App-v 客户端如何从 App-v 流式处理服务器检索序列化的应用程序，以及如何在虚拟环境中运行序列化的应用程序。</span><span class="sxs-lookup"><span data-stu-id="5745e-119">An XML-based file that instructs the App-V client how to retrieve the sequenced application from the App-V streaming server and how to run the sequenced application in the virtual environment.</span></span>

<a href="" id="package-root-directory"></a><span data-ttu-id="5745e-120">程序包根目录</span><span class="sxs-lookup"><span data-stu-id="5745e-120">Package root directory</span></span>  
<span data-ttu-id="5745e-121">排序计算机上安装序列化应用程序包的文件的目录。</span><span class="sxs-lookup"><span data-stu-id="5745e-121">The directory on the sequencing computer on which files for the sequenced application package are installed.</span></span> <span data-ttu-id="5745e-122">此目录还存在于将对序列化的应用程序进行流式处理的计算机上。</span><span class="sxs-lookup"><span data-stu-id="5745e-122">This directory also exists virtually on the computer to which a sequenced application will be streamed.</span></span>

<a href="" id="sequenced-application"></a><span data-ttu-id="5745e-123">顺序应用程序</span><span class="sxs-lookup"><span data-stu-id="5745e-123">Sequenced application</span></span>  
<span data-ttu-id="5745e-124">由 sequencer 监视的应用程序被分解为主要和辅助功能块，流到运行应用程序 V 客户端 t 的目标计算机，并运行虚拟环境。</span><span class="sxs-lookup"><span data-stu-id="5745e-124">An application that has been monitored by the sequencer, broken up into primary and secondary feature blocks, streamed to a target computer running the App-V client t, and runs a virtual environment.</span></span>

<a href="" id="sequenced-application-package"></a><span data-ttu-id="5745e-125">顺序应用程序包</span><span class="sxs-lookup"><span data-stu-id="5745e-125">Sequenced application package</span></span>  
<span data-ttu-id="5745e-126">构成虚拟应用程序并允许虚拟应用程序运行的文件。</span><span class="sxs-lookup"><span data-stu-id="5745e-126">The files that comprise a virtual application and allow a virtual application to run.</span></span> <span data-ttu-id="5745e-127">这些文件是在排序后创建的， **.osd**具体包括 .osd **、** sprj、 **.sprj**和 **.ico**文件。</span><span class="sxs-lookup"><span data-stu-id="5745e-127">These files are created after sequencing and specifically include **.osd**, **.sft**, **.sprj**, and **.ico** files.</span></span>

<a href="" id="sequencing"></a><span data-ttu-id="5745e-128">引出</span><span class="sxs-lookup"><span data-stu-id="5745e-128">Sequencing</span></span>  
<span data-ttu-id="5745e-129">使用 App-v 排序器创建应用程序包的过程。</span><span class="sxs-lookup"><span data-stu-id="5745e-129">The process of creating an application package using the App-V Sequencer.</span></span> <span data-ttu-id="5745e-130">在此过程中，将监视应用程序、配置其快捷方式，并创建序列化的应用程序包。</span><span class="sxs-lookup"><span data-stu-id="5745e-130">In this process, an application is monitored, its shortcuts are configured, and a sequenced application package is created.</span></span>

<a href="" id="sequencing-computer"></a><span data-ttu-id="5745e-131">计算机排序</span><span class="sxs-lookup"><span data-stu-id="5745e-131">Sequencing computer</span></span>  
<span data-ttu-id="5745e-132">用于对应用程序进行排序的计算机。</span><span class="sxs-lookup"><span data-stu-id="5745e-132">The computer used to sequence an application.</span></span>

<a href="" id="virtual-application"></a><span data-ttu-id="5745e-133">虚拟应用程序</span><span class="sxs-lookup"><span data-stu-id="5745e-133">Virtual application</span></span>  
<span data-ttu-id="5745e-134">由 Sequencer 打包以在自包含虚拟环境中运行的应用程序。</span><span class="sxs-lookup"><span data-stu-id="5745e-134">An application packaged by the Sequencer to run in a self-contained, virtual environment.</span></span> <span data-ttu-id="5745e-135">虚拟环境包含在客户端上运行应用程序所需的信息，而无需本地安装应用程序。</span><span class="sxs-lookup"><span data-stu-id="5745e-135">The virtual environment contains the information necessary to run the application on the client without installing the application locally.</span></span>

<a href="" id="primary-feature-block"></a><span data-ttu-id="5745e-136">主要功能块</span><span class="sxs-lookup"><span data-stu-id="5745e-136">Primary feature block</span></span>  
<span data-ttu-id="5745e-137">在目标计算机上运行应用程序所需的虚拟应用程序包中的最小内容。</span><span class="sxs-lookup"><span data-stu-id="5745e-137">The minimum content in a virtual application package that is necessary for an application to run on a target computer.</span></span> <span data-ttu-id="5745e-138">主功能块中的内容在排序的应用阶段中标识，通常包含最常用的应用程序功能的内容。</span><span class="sxs-lookup"><span data-stu-id="5745e-138">The content in the primary feature block is identified during the application phase of sequencing and typically consists of the content for the most used application features.</span></span>

## <a href="" id="sequencing-applications-"></a><span data-ttu-id="5745e-139">排序应用程序</span><span class="sxs-lookup"><span data-stu-id="5745e-139">Sequencing Applications</span></span>


<span data-ttu-id="5745e-140">有两种方法可以在你的环境中创建和修改虚拟应用程序包。</span><span class="sxs-lookup"><span data-stu-id="5745e-140">There are two methods to create and modify virtual application packages in your environment.</span></span> <span data-ttu-id="5745e-141">第一种方法是使用**排序**向导。</span><span class="sxs-lookup"><span data-stu-id="5745e-141">The first method is by using the **Sequencing** wizard.</span></span> <span data-ttu-id="5745e-142">**排序**向导允许你创建新的或修改现有的虚拟应用程序包。</span><span class="sxs-lookup"><span data-stu-id="5745e-142">The **Sequencing** wizard allows you to create new, or modify existing virtual application packages.</span></span> <span data-ttu-id="5745e-143">有关使用**顺序**向导的详细信息，请参阅[如何对新应用程序进行排序](how-to-sequence-a-new-application.md)。</span><span class="sxs-lookup"><span data-stu-id="5745e-143">For more information about using the **Sequencing** wizard see, [How to Sequence a New Application](how-to-sequence-a-new-application.md).</span></span> <span data-ttu-id="5745e-144">第二种方法是使用命令行。</span><span class="sxs-lookup"><span data-stu-id="5745e-144">The second method is by using the command-line.</span></span> <span data-ttu-id="5745e-145">命令行允许你使用命令提示符创建新的或修改现有的虚拟应用程序包。</span><span class="sxs-lookup"><span data-stu-id="5745e-145">The command-line allows you to create new, or modify existing virtual application packages using the command prompt.</span></span> <span data-ttu-id="5745e-146">有关使用命令行的详细信息，请参阅[如何使用命令行管理虚拟应用程序](how-to-manage-virtual-applications-using-the-command-line.md)。</span><span class="sxs-lookup"><span data-stu-id="5745e-146">For more information about using the command line see, [How to Manage Virtual Applications Using the Command Line](how-to-manage-virtual-applications-using-the-command-line.md).</span></span>

<span data-ttu-id="5745e-147">**排序**向导提供以下用于创建虚拟应用程序包的函数：</span><span class="sxs-lookup"><span data-stu-id="5745e-147">The **Sequencing** wizard provides the following functions for creating virtual application packages:</span></span>

1.  <span data-ttu-id="5745e-148">**程序包配置**：**排序**向导提示提供完成开放软件描述符（OSD）文件所需的程序包配置信息，该文件是启动顺序应用程序包所需的文件。</span><span class="sxs-lookup"><span data-stu-id="5745e-148">**Package Configuration**: The **Sequencing** Wizard prompts for package configuration information necessary to complete the Open Software Descriptor (OSD) file, which is a required file for starting a sequenced application package.</span></span>

2.  <span data-ttu-id="5745e-149">**应用程序安装**：**排序**向导收集有关应用程序的安装和启动配置的信息。</span><span class="sxs-lookup"><span data-stu-id="5745e-149">**Application Installation**: The **Sequencing** Wizard gathers information about an application’s installation and startup configurations.</span></span> <span data-ttu-id="5745e-150">它监视和记录与应用程序关联的安装和启动信息，以创建虚拟应用程序包所需的文件。</span><span class="sxs-lookup"><span data-stu-id="5745e-150">It monitors and records the installation and startup information associated with the application to create the files necessary for a virtual application package.</span></span>

3.  <span data-ttu-id="5745e-151">**应用程序启动**：**排序**向导收集用于编译和排序的代码块的信息，以便在目标计算机上执行序列化应用程序包初始启动所需的代码块。</span><span class="sxs-lookup"><span data-stu-id="5745e-151">**Application Startup**: The **Sequencing** Wizard gathers information for compiling and ordering the blocks of code necessary to perform the initial startup of the sequenced application package on the target computer.</span></span> <span data-ttu-id="5745e-152">代码块的编译称为主功能块。</span><span class="sxs-lookup"><span data-stu-id="5745e-152">The compilation of the code block is referred to as the primary feature block.</span></span>

## <span data-ttu-id="5745e-153">应用程序虚拟化 Sequencer 安全注意事项</span><span class="sxs-lookup"><span data-stu-id="5745e-153">Application Virtualization Sequencer Security Considerations</span></span>


<span data-ttu-id="5745e-154">App-v Sequencer 运行使用本地系统帐户在排序时间内检测到的所有服务，并且不会在服务控制请求上强制执行安全描述符。</span><span class="sxs-lookup"><span data-stu-id="5745e-154">The App-V Sequencer runs all services detected at sequencing time using the Local System account and does not enforce security descriptors on service control requests.</span></span> <span data-ttu-id="5745e-155">如果该服务是使用其他用户帐户安装的，或者安全描述符打算授予不同的用户组特定的服务权限，请仔细考虑是否应虚拟化该服务。</span><span class="sxs-lookup"><span data-stu-id="5745e-155">If the service was installed using a different user account or if the security descriptors are intended to grant different user groups specific service permissions, consider carefully whether the service should be virtualized.</span></span> <span data-ttu-id="5745e-156">在某些情况下，应在本地安装该服务，以确保保留预期的服务安全。</span><span class="sxs-lookup"><span data-stu-id="5745e-156">In some cases, you should install the service locally to ensure that the intended service security is preserved.</span></span>

<span data-ttu-id="5745e-157">**重要提示** 你应该始终将虚拟应用程序包保存到安全位置。</span><span class="sxs-lookup"><span data-stu-id="5745e-157">**Important** You should always save virtual application packages in a secure location.</span></span>

 

## <span data-ttu-id="5745e-158">相关主题</span><span class="sxs-lookup"><span data-stu-id="5745e-158">Related topics</span></span>


[<span data-ttu-id="5745e-159">Application Virtualization Sequencer 概述</span><span class="sxs-lookup"><span data-stu-id="5745e-159">Application Virtualization Sequencer Overview</span></span>](application-virtualization-sequencer-overview.md)

 

 





