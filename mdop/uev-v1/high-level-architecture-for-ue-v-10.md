---
title: UE-V 1.0 的高级别体系结构
description: UE-V 1.0 的高级别体系结构
author: dansimp
ms.assetid: d54f9f10-1a4d-4e56-802d-22d51646e1cc
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 76703cf4c7297401e6516830bf194cef741d60ec
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804100"
---
# <span data-ttu-id="a8282-103">UE-V 1.0 的高级别体系结构</span><span class="sxs-lookup"><span data-stu-id="a8282-103">High-Level Architecture for UE-V 1.0</span></span>


<span data-ttu-id="a8282-104">本主题介绍 Microsoft 用户体验虚拟化（UE-V）设置漫游解决方案的高级别体系结构元素。</span><span class="sxs-lookup"><span data-stu-id="a8282-104">This topic describes high-level architectural elements of the Microsoft User Experience Virtualization (UE-V) settings roaming solution.</span></span> <span data-ttu-id="a8282-105">以下元素是标准 UE-V 部署的一部分。</span><span class="sxs-lookup"><span data-stu-id="a8282-105">The following elements are part of a standard UE-V deployment.</span></span>

![ue-v agent 体系结构图](images/ue-vagentarchitecturaldiagram.gif)

<span data-ttu-id="a8282-107">UE-V Agent 将监视应用程序和操作系统进程，因为它们在 UE-V 设置位置模板中标识。</span><span class="sxs-lookup"><span data-stu-id="a8282-107">The UE-V Agent monitors the applications and the operating system processes as they are identified in the UE-V settings location templates.</span></span> <span data-ttu-id="a8282-108">当应用程序或操作系统启动时，将从设置包中读取设置并将其应用于计算机。</span><span class="sxs-lookup"><span data-stu-id="a8282-108">When the application or operating system starts, the settings are read from the settings package and applied to the computer.</span></span> <span data-ttu-id="a8282-109">当应用程序关闭或操作系统锁定或关闭时，设置将保存在设置存储位置的 UE-V settings 程序包中。</span><span class="sxs-lookup"><span data-stu-id="a8282-109">When the application closes or when the operating system is locked or shut down, settings are saved in a UE-V settings package in the settings storage location.</span></span>

## <span data-ttu-id="a8282-110">设置存储位置</span><span class="sxs-lookup"><span data-stu-id="a8282-110">Settings storage location</span></span>


<span data-ttu-id="a8282-111">设置存储位置是用户体验虚拟化代理访问的用于读取和写入设置的文件共享。</span><span class="sxs-lookup"><span data-stu-id="a8282-111">The settings storage location is a file share that the User Experience Virtualization agent accesses to read and write settings.</span></span> <span data-ttu-id="a8282-112">此位置可以是 Active Directory 主目录，也可以是在 UE-V 安装期间定义的。</span><span class="sxs-lookup"><span data-stu-id="a8282-112">This location is either the Active Directory home directory or defined during the UE-V installation.</span></span> <span data-ttu-id="a8282-113">你可以在安装 UE-V agent 的过程中设置位置，也可以稍后通过组策略、WMI 或 PowerShell 设置位置。</span><span class="sxs-lookup"><span data-stu-id="a8282-113">You can set the location during the installation of the UE-V agent, or you can set it later with Group Policy, WMI, or PowerShell.</span></span> <span data-ttu-id="a8282-114">该位置可以是用户可以访问的任何通用文件共享。</span><span class="sxs-lookup"><span data-stu-id="a8282-114">The location can be on any common file share that users can access.</span></span> <span data-ttu-id="a8282-115">如果在安装期间没有设置存储位置，则 UE-V 将使用 Active Directory 中的主目录。</span><span class="sxs-lookup"><span data-stu-id="a8282-115">If no setting storage location is set during installation then UE-V will use the home directory in Active Directory.</span></span> <span data-ttu-id="a8282-116">UE-V agent 将验证位置并创建一个系统文件夹，该文件夹将被存储和访问用户设置的用户隐藏。</span><span class="sxs-lookup"><span data-stu-id="a8282-116">The UE-V agent verifies the location and creates a system folder that is hidden from the user in which to store and access the user settings.</span></span> <span data-ttu-id="a8282-117">有关设置存储的详细信息，请参阅[为 Ue-v 准备环境](preparing-your-environment-for-ue-v.md)。</span><span class="sxs-lookup"><span data-stu-id="a8282-117">For more information about settings storage, see [Preparing Your Environment for UE-V](preparing-your-environment-for-ue-v.md).</span></span>

## <span data-ttu-id="a8282-118">UE-V Agent</span><span class="sxs-lookup"><span data-stu-id="a8282-118">UE-V Agent</span></span>


<span data-ttu-id="a8282-119">UE-V agent 使用由用户体验虚拟化同步的设置在每台计算机上安装。</span><span class="sxs-lookup"><span data-stu-id="a8282-119">The UE-V agent is installed on each computer with settings that are synchronized by User Experience Virtualization.</span></span> <span data-ttu-id="a8282-120">对于对设置所做的任何更改，代理将监视已注册的应用程序和操作系统，并在计算机之间同步这些设置。</span><span class="sxs-lookup"><span data-stu-id="a8282-120">The agent monitors the registered applications and the operating system for any changes to that are made to settings, and it synchronizes those settings between computers.</span></span> <span data-ttu-id="a8282-121">应用程序启动时，设置将从设置存储位置应用到应用程序。</span><span class="sxs-lookup"><span data-stu-id="a8282-121">Settings are applied from the settings storage location to the application when the application is started.</span></span> <span data-ttu-id="a8282-122">然后，在应用程序关闭时，这些设置将保存回设置存储位置。</span><span class="sxs-lookup"><span data-stu-id="a8282-122">The settings are then saved back to the settings storage location when the application closes.</span></span> <span data-ttu-id="a8282-123">当用户登录、计算机处于解锁状态或者当用户使用远程桌面协议（RDP）将远程连接到计算机时，将应用操作系统设置。</span><span class="sxs-lookup"><span data-stu-id="a8282-123">The operating system settings are applied when the user logs on, when the computer is unlocked, or when the user connects remotely to the computer by using remote desktop protocol (RDP).</span></span> <span data-ttu-id="a8282-124">当用户注销、计算机被锁定或远程连接断开时，代理会保存设置。</span><span class="sxs-lookup"><span data-stu-id="a8282-124">The agent saves settings when the user logs off, when the computer is locked, or when a remote connection is disconnected.</span></span> <span data-ttu-id="a8282-125">有关 UE-V Agent 的详细信息，请参阅[为 Ue-v 准备环境](preparing-your-environment-for-ue-v.md)。</span><span class="sxs-lookup"><span data-stu-id="a8282-125">For more information about the UE-V Agent, see [Preparing Your Environment for UE-V](preparing-your-environment-for-ue-v.md).</span></span>

## <a href="" id="bkmk-settingslocationtemplate"></a><span data-ttu-id="a8282-126">设置位置模板</span><span class="sxs-lookup"><span data-stu-id="a8282-126">Settings location templates</span></span>


<span data-ttu-id="a8282-127">设置位置模板是一个 XML 文件，用于定义要由用户体验虚拟化监视的设置位置。</span><span class="sxs-lookup"><span data-stu-id="a8282-127">The settings location template is an XML file that defines the settings locations to be monitored by User Experience Virtualization.</span></span> <span data-ttu-id="a8282-128">在运行 UE-V Agent 的计算机上，仅捕获或应用在这些设置模板中定义的设置位置。</span><span class="sxs-lookup"><span data-stu-id="a8282-128">Only the settings locations defined in these settings templates are captured or applied on computers running the UE-V Agent.</span></span> <span data-ttu-id="a8282-129">设置位置模板不包含设置值，仅包含值存储在计算机上的位置。</span><span class="sxs-lookup"><span data-stu-id="a8282-129">The settings location template does not contain settings values, only the locations where values are stored on the computer.</span></span>

<span data-ttu-id="a8282-130">UE-V 包含一组设置位置模板，用于为某些 Microsoft 应用程序和 Windows 设置指定设置位置。</span><span class="sxs-lookup"><span data-stu-id="a8282-130">UE-V includes a set of settings location templates that specify settings locations for some Microsoft applications and Windows settings.</span></span> <span data-ttu-id="a8282-131">管理员可以使用 UE-V 生成器创建自定义设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="a8282-131">An administrator can create custom settings location templates by using the UE-V Generator.</span></span>

[<span data-ttu-id="a8282-132">规划要使用 UE-V 1.0 同步的应用程序</span><span class="sxs-lookup"><span data-stu-id="a8282-132">Planning Which Applications to Synchronize with UE-V 1.0</span></span>](planning-which-applications-to-synchronize-with-ue-v-10.md)

[<span data-ttu-id="a8282-133">规划 UE-V 1.0 的自定义模板部署</span><span class="sxs-lookup"><span data-stu-id="a8282-133">Planning for Custom Template Deployment for UE-V 1.0</span></span>](planning-for-custom-template-deployment-for-ue-v-10.md)

[<span data-ttu-id="a8282-134">使用自定义 UE-V 模板和 UE-V 生成器</span><span class="sxs-lookup"><span data-stu-id="a8282-134">Working with Custom UE-V Templates and the UE-V Generator</span></span>](working-with-custom-ue-v-templates-and-the-ue-v-generator.md)

## <span data-ttu-id="a8282-135">设置程序包</span><span class="sxs-lookup"><span data-stu-id="a8282-135">Settings packages</span></span>


<span data-ttu-id="a8282-136">应用程序设置和 Windows 设置存储在设置程序包中，由 UE-V Agent 创建。</span><span class="sxs-lookup"><span data-stu-id="a8282-136">Application settings and Windows settings are stored in settings packages, which are created by the UE-V Agent.</span></span> <span data-ttu-id="a8282-137">设置包是在设置位置模板中表示的设置的集合。</span><span class="sxs-lookup"><span data-stu-id="a8282-137">A settings package is a collection of the settings that are represented in the settings location templates.</span></span> <span data-ttu-id="a8282-138">这些设置程序包已生成，本地存储，然后复制到设置存储位置。</span><span class="sxs-lookup"><span data-stu-id="a8282-138">These settings packages are built, locally stored, and then copied to the settings storage location.</span></span> <span data-ttu-id="a8282-139">"上次写入 wins" 确定当单个用户将多台计算机同步到一个存储位置时，将保留哪些设置。</span><span class="sxs-lookup"><span data-stu-id="a8282-139">“Last write wins” determines which settings are preserved when a single user synchronizes the more than one computer to a storage location.</span></span> <span data-ttu-id="a8282-140">在一台计算机上运行的代理将读取和写入设置位置，与在其他计算机上运行的代理无关。</span><span class="sxs-lookup"><span data-stu-id="a8282-140">The agent that runs on one computer reads and writes to the settings location independent of agents that run on other computers.</span></span> <span data-ttu-id="a8282-141">当下一个代理从设置存储位置读取时，将应用最近写入的设置和值。</span><span class="sxs-lookup"><span data-stu-id="a8282-141">The most recently written settings and values are applied when the next agent reads from the settings storage location.</span></span>

![ue-v 发电机进程](images/ue-vgeneratorprocess.gif)

## <span data-ttu-id="a8282-143">设置模板目录</span><span class="sxs-lookup"><span data-stu-id="a8282-143">Settings template catalog</span></span>


<span data-ttu-id="a8282-144">设置模板目录是 UE-V 计算机上的文件夹路径或用于存储所有自定义设置位置模板的服务器消息块（SMB）网络共享。</span><span class="sxs-lookup"><span data-stu-id="a8282-144">The settings template catalog is a folder path on UE-V computers or a Server Message Block (SMB) network share that stores all the custom settings location templates.</span></span> <span data-ttu-id="a8282-145">UE-V agent 从该位置检索新的或更新的模板。</span><span class="sxs-lookup"><span data-stu-id="a8282-145">The UE-V agent retrieves new or updated templates from this location.</span></span> <span data-ttu-id="a8282-146">UE-V agent 每天检查此位置一次，它会根据此文件夹中的模板更新其同步行为。</span><span class="sxs-lookup"><span data-stu-id="a8282-146">The UE-V agent checks this location once each day and it updates its synchronization behavior based on the templates in this folder.</span></span> <span data-ttu-id="a8282-147">自上次检查以来在此文件夹中添加或更新的模板由 UE-V agent 注册。</span><span class="sxs-lookup"><span data-stu-id="a8282-147">The templates that were added or updated in this folder since the last check are registered by the UE-V agent.</span></span> <span data-ttu-id="a8282-148">UE-V agent deregisters 从此文件夹中删除的模板。</span><span class="sxs-lookup"><span data-stu-id="a8282-148">The UE-V agent deregisters the templates that were removed from this folder.</span></span> <span data-ttu-id="a8282-149">任务计划程序每天注册和注销一次模板。</span><span class="sxs-lookup"><span data-stu-id="a8282-149">Templates are registered and unregistered one time per day by the task scheduler.</span></span> <span data-ttu-id="a8282-150">如果只使用 UE-V 附带的默认设置位置模板，则不需要设置模板目录。</span><span class="sxs-lookup"><span data-stu-id="a8282-150">If you will use only the default settings location templates that are included with UE-V, then a settings template catalog is unnecessary.</span></span> <span data-ttu-id="a8282-151">有关设置部署目录的详细信息，请参阅[规划 ue-v 1.0 的自定义模板部署](planning-for-custom-template-deployment-for-ue-v-10.md)。</span><span class="sxs-lookup"><span data-stu-id="a8282-151">For more information about settings deployment catalogs, see [Planning for Custom Template Deployment for UE-V 1.0](planning-for-custom-template-deployment-for-ue-v-10.md).</span></span>

## <span data-ttu-id="a8282-152">用户体验虚拟化生成器</span><span class="sxs-lookup"><span data-stu-id="a8282-152">User Experience Virtualization Generator</span></span>


<span data-ttu-id="a8282-153">用户体验虚拟化生成器使你能够创建自定义设置位置模板，这些模板将存储在企业中使用的应用程序的设置位置以及你希望包括在漫游设置解决方案中的应用程序的设置位置。</span><span class="sxs-lookup"><span data-stu-id="a8282-153">The User Experience Virtualization Generator enables you to create custom settings location templates which will store the settings locations of the applications that are used in the enterprise and that you want to include in the roaming settings solution.</span></span> <span data-ttu-id="a8282-154">UE-V 生成器将寻找发现应用程序的注册表值和设置文件的位置，然后将在设置位置模板 XML 文件中记录这些位置。</span><span class="sxs-lookup"><span data-stu-id="a8282-154">The UE-V Generator will seek to discover the locations of registry values and the settings files for applications and then it will record those locations in a settings location template XML file.</span></span> <span data-ttu-id="a8282-155">然后，你可以将这些设置位置模板分发给用户计算机。</span><span class="sxs-lookup"><span data-stu-id="a8282-155">You can then distribute these settings location templates to the user computers.</span></span> <span data-ttu-id="a8282-156">UE-V 生成器还允许管理员编辑现有模板或验证使用其他 XML 编辑器创建的模板。</span><span class="sxs-lookup"><span data-stu-id="a8282-156">The UE-V Generator also allows an administrator to edit an existing template or validate a template that was created with another XML editor.</span></span>

<span data-ttu-id="a8282-157">UE-V 生成器监视应用程序以发现和记录其设置的存储位置。</span><span class="sxs-lookup"><span data-stu-id="a8282-157">The UE-V Generator monitors an application to discover and record where it stores its settings.</span></span> <span data-ttu-id="a8282-158">若要执行此操作，它会监视应用程序在 HKEY _CURRENT \ _USER 注册表中或在 "**用户**\\ [用户名 \] \ \ **AppData**  \\  **漫游** **AppData**" 下的文件文件夹中读取或写入的位置  \\  **Local**。</span><span class="sxs-lookup"><span data-stu-id="a8282-158">To do this, it monitors where the application reads or writes in the HKEY\_CURRENT\_USER registry or in the file folders under **Users** \\ \[User name\] \\ **AppData** \\ **Roaming and Users** \\ \[User name\] \\ **AppData** \\ **Local**.</span></span>

<span data-ttu-id="a8282-159">发现过程将排除登录用户无法写入值的注册表项和文件。</span><span class="sxs-lookup"><span data-stu-id="a8282-159">The discovery process excludes registry keys and files to which the logged-in user cannot write values.</span></span> <span data-ttu-id="a8282-160">XML 文件中不包含任何内容。</span><span class="sxs-lookup"><span data-stu-id="a8282-160">None of these will be included in the XML file.</span></span> <span data-ttu-id="a8282-161">该发现过程还会排除与 Windows 操作系统的核心功能相关联的注册表项和文件。</span><span class="sxs-lookup"><span data-stu-id="a8282-161">The discovery process also excludes registry keys and files that are associated with the core functionality of the Windows operating system.</span></span>

<span data-ttu-id="a8282-162">有关 UE-V 生成器的详细信息，请参阅[安装 Ue-v 生成器](installing-the-ue-v-generator.md)。</span><span class="sxs-lookup"><span data-stu-id="a8282-162">For more information about the UE-V Generator, see [Installing the UE-V Generator](installing-the-ue-v-generator.md).</span></span>

## <span data-ttu-id="a8282-163">相关主题</span><span class="sxs-lookup"><span data-stu-id="a8282-163">Related topics</span></span>


[<span data-ttu-id="a8282-164">Microsoft 用户体验虚拟化 (UE-V) 1.0</span><span class="sxs-lookup"><span data-stu-id="a8282-164">Microsoft User Experience Virtualization (UE-V) 1.0</span></span>](index.md)

[<span data-ttu-id="a8282-165">用户体验虚拟化 1.0 入门</span><span class="sxs-lookup"><span data-stu-id="a8282-165">Getting Started With User Experience Virtualization 1.0</span></span>](getting-started-with-user-experience-virtualization-10.md)

[<span data-ttu-id="a8282-166">关于用户体验虚拟化 1.0</span><span class="sxs-lookup"><span data-stu-id="a8282-166">About User Experience Virtualization 1.0</span></span>](about-user-experience-virtualization-10.md)

[<span data-ttu-id="a8282-167">使用自定义 UE-V 模板和 UE-V 生成器</span><span class="sxs-lookup"><span data-stu-id="a8282-167">Working with Custom UE-V Templates and the UE-V Generator</span></span>](working-with-custom-ue-v-templates-and-the-ue-v-generator.md)

 

 





