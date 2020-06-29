---
title: 关于 DaRT 7.0
description: 关于 DaRT 7.0
author: dansimp
ms.assetid: 217ffafc-6d73-4b80-88d9-71870460d4ab
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: cd647b2f596ce88ce38580f08422ff8f92b35c06
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803335"
---
# <span data-ttu-id="57b5a-103">关于 DaRT 7.0</span><span class="sxs-lookup"><span data-stu-id="57b5a-103">About DaRT 7.0</span></span>


<span data-ttu-id="57b5a-104">Microsoft 诊断和恢复工具集（DaRT）7帮助你诊断和修复基于 Windows 的桌面。</span><span class="sxs-lookup"><span data-stu-id="57b5a-104">Microsoft Diagnostics and Recovery Toolset (DaRT)7 helps you troubleshoot and repair Windows-based desktops.</span></span> <span data-ttu-id="57b5a-105">这包括无法启动的桌面。</span><span class="sxs-lookup"><span data-stu-id="57b5a-105">This includes those desktops that cannot be started.</span></span> <span data-ttu-id="57b5a-106">DaRT 是一组功能强大的工具，用于扩展 Windows 恢复环境（WinRE）。</span><span class="sxs-lookup"><span data-stu-id="57b5a-106">DaRT is a powerful set of tools that extend the Windows Recovery Environment (WinRE).</span></span> <span data-ttu-id="57b5a-107">通过使用 DaRT，你可以分析问题以确定其原因，例如检查计算机的事件日志或系统注册表。</span><span class="sxs-lookup"><span data-stu-id="57b5a-107">By using DaRT, you can analyze an issue to determine its cause, for example, by inspecting the computer’s event log or system registry.</span></span>

<span data-ttu-id="57b5a-108">DaRT 还提供工具来帮助您在确定原因后立即修复问题。</span><span class="sxs-lookup"><span data-stu-id="57b5a-108">DaRT also provides tools to help you fix a problem as soon as you determine the cause.</span></span> <span data-ttu-id="57b5a-109">例如，你可以使用 DaRT 中的工具禁用错误的设备驱动程序、删除修补程序、还原已删除的文件和扫描计算机，即使你无法或不应启动已安装的 Windows 操作系统也是如此。</span><span class="sxs-lookup"><span data-stu-id="57b5a-109">For example, you can use the tools in DaRT to disable a faulty device driver, remove hotfixes, restore deleted files, and scan the computer for malware even when you cannot or should not start the installed Windows operating system.</span></span>

<span data-ttu-id="57b5a-110">DaRT 可帮助你快速恢复运行32位或64位版本的 Windows 7 的计算机，通常比重新映像计算机所花费的时间更少。</span><span class="sxs-lookup"><span data-stu-id="57b5a-110">DaRT can help you quickly recover computers that are running either 32-bit or 64-bit versions of Windows 7, typically in less time than it would take to reimage the computer.</span></span>

## <span data-ttu-id="57b5a-111">关于 DaRT 7 恢复映像</span><span class="sxs-lookup"><span data-stu-id="57b5a-111">About the DaRT 7 Recovery Image</span></span>


<span data-ttu-id="57b5a-112">通过 DaRT 中的功能，你可以创建基于 WinRE 的恢复映像，并将其与 DaRT 提供的一组工具结合使用。</span><span class="sxs-lookup"><span data-stu-id="57b5a-112">Functionality in DaRT lets you create a recovery image that is based on WinRE combined with a set of tools that DaRT provides.</span></span> <span data-ttu-id="57b5a-113">DaRT 恢复映像利用 WinRE，可从中访问 "**诊断和恢复工具集**" 窗口。</span><span class="sxs-lookup"><span data-stu-id="57b5a-113">The DaRT recovery image takes advantage of WinRE, from which you can access the **Diagnostics and Recovery Toolset** window.</span></span>

<span data-ttu-id="57b5a-114">使用**Dart 恢复映像向导**创建 DaRT 恢复映像。</span><span class="sxs-lookup"><span data-stu-id="57b5a-114">Use the **DaRT Recovery Image Wizard** to create the DaRT recovery image.</span></span> <span data-ttu-id="57b5a-115">默认情况下，向导在桌面上创建一个名为 DaRT70 的国际组织标准化（ISO）图像文件，但你可以指定不同的位置和文件名。</span><span class="sxs-lookup"><span data-stu-id="57b5a-115">By default, the wizard creates an International Organization for Standardization (ISO) image file on your desktop that is named DaRT70.iso, although you can specify a different location and file name.</span></span> <span data-ttu-id="57b5a-116">该向导还允许你将图像刻录到 CD 或 DVD。</span><span class="sxs-lookup"><span data-stu-id="57b5a-116">The wizard also lets you burn the image to a CD or DVD.</span></span> <span data-ttu-id="57b5a-117">完成向导后，您可以将恢复映像保存到 USB 闪存驱动器，或将其保存为可用于创建远程分区或恢复分区的格式。</span><span class="sxs-lookup"><span data-stu-id="57b5a-117">After you have finished the wizard, you can save the recovery image to a USB flash drive or save it in a format that you can use to create a remote partition or a recovery partition.</span></span>

<span data-ttu-id="57b5a-118">当你必须使用 DaRT 启动不会启动的最终用户计算机时，你可以按照有关[如何使用 DaRT 恢复映像恢复本地计算机](how-to-recover-local-computers-using-the-dart-recovery-image-dart-7.md)的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="57b5a-118">When you have to use DaRT to startup an end-user computer that will not start, you can follow the instructions at [How to Recover Local Computers Using the DaRT Recovery Image](how-to-recover-local-computers-using-the-dart-recovery-image-dart-7.md).</span></span>

<span data-ttu-id="57b5a-119">有关 DaRT 中的工具的详细信息，请参阅[dart 7.0 中的工具概述](overview-of-the-tools-in-dart-70-new-ia.md)。</span><span class="sxs-lookup"><span data-stu-id="57b5a-119">For detailed information about the tools in DaRT, see [Overview of the Tools in DaRT 7.0](overview-of-the-tools-in-dart-70-new-ia.md).</span></span>

## <a href="" id="what-s-new-in-dart-7"></a><span data-ttu-id="57b5a-120">DaRT 7 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="57b5a-120">What’s New in DaRT 7</span></span>


<span data-ttu-id="57b5a-121">DaRT7 将继续支持以前版本中包含的所有方案，并且除了三个新的部署选项之外，还会添加新的远程连接功能。</span><span class="sxs-lookup"><span data-stu-id="57b5a-121">DaRT7 continues to support all the scenarios included in previous versions and it adds a new Remote Connection feature in addition to three new deployment options.</span></span>

### <span data-ttu-id="57b5a-122">DaRT 7 映像创建</span><span class="sxs-lookup"><span data-stu-id="57b5a-122">DaRT 7 Image Creation</span></span>

<span data-ttu-id="57b5a-123">用于创建 DaRT ISO 映像的向导现在称为**DaRT 恢复映像**，它现在支持启用或禁用新的远程连接功能的选项。</span><span class="sxs-lookup"><span data-stu-id="57b5a-123">The wizard that you use to create DaRT ISO images is now called **DaRT Recovery Image** and it now supports an option to enable or disable the new Remote Connection feature.</span></span> <span data-ttu-id="57b5a-124">远程连接允许帮助台代理从远程位置运行 DaRT 工具。</span><span class="sxs-lookup"><span data-stu-id="57b5a-124">Remote Connection lets a helpdesk agent run the DaRT tools from a remote location.</span></span> <span data-ttu-id="57b5a-125">在以前的版本中，帮助台工程师必须在最终用户计算机上物理显示才能运行 DaRT 工具。</span><span class="sxs-lookup"><span data-stu-id="57b5a-125">In previous releases, the helpdesk agent had to be physically present at the end-user computer to run the DaRT tools.</span></span>

<span data-ttu-id="57b5a-126">该向导还允许你自定义 "远程连接" 功能的欢迎消息（当最终用户运行远程连接工具时显示消息）。</span><span class="sxs-lookup"><span data-stu-id="57b5a-126">The wizard also lets you customize the Welcome message for the Remote Connection feature (the message is shown when end users run the Remote Connection tool).</span></span> <span data-ttu-id="57b5a-127">IT 管理员还可以配置远程连接应使用的端口号。</span><span class="sxs-lookup"><span data-stu-id="57b5a-127">IT Admins can also configure which Port Number should be used by Remote Connection.</span></span>

<span data-ttu-id="57b5a-128">有关**DaRT 恢复映像向导**或远程连接的详细信息，请参阅[创建 DaRT 7.0 恢复映像](creating-the-dart-70-recovery-image-dart-7.md)。</span><span class="sxs-lookup"><span data-stu-id="57b5a-128">For more information about the **DaRT Recovery Image Wizard** or Remote Connection, see [Creating the DaRT 7.0 Recovery Image](creating-the-dart-70-recovery-image-dart-7.md).</span></span>

### <span data-ttu-id="57b5a-129">DaRT 7 ISO 部署</span><span class="sxs-lookup"><span data-stu-id="57b5a-129">DaRT 7 ISO Deployment</span></span>

<span data-ttu-id="57b5a-130">除了刻录到 CD 或 DVD 外，在部署包含 DaRT 恢复映像的 ISO 时，DaRT7 还将添加三个新选项：</span><span class="sxs-lookup"><span data-stu-id="57b5a-130">In addition to burning to a CD or DVD, DaRT7 adds three new options when you deploy the ISO that contains the DaRT recovery image:</span></span>

-   <span data-ttu-id="57b5a-131">USB 闪存驱动器部署</span><span class="sxs-lookup"><span data-stu-id="57b5a-131">USB flash drive deployment</span></span>

-   <span data-ttu-id="57b5a-132">远程分区部署</span><span class="sxs-lookup"><span data-stu-id="57b5a-132">Remote partition deployment</span></span>

-   <span data-ttu-id="57b5a-133">恢复分区部署</span><span class="sxs-lookup"><span data-stu-id="57b5a-133">Recovery partition deployment</span></span>

<span data-ttu-id="57b5a-134">USB 闪存驱动器部署选项允许公司在没有 CD 或 DVD 驱动器可用的计算机上使用 DaRT。</span><span class="sxs-lookup"><span data-stu-id="57b5a-134">The USB flash drive deployment option lets a company use DaRT on computers that do not have CD or DVD drives available.</span></span> <span data-ttu-id="57b5a-135">通过恢复和远程分区选项，最终用户可以轻松访问 DaRT 映像并启用远程连接功能。</span><span class="sxs-lookup"><span data-stu-id="57b5a-135">The recovery and remote partition options let end users have easy access to the DaRT image and to enable the Remote Connection functionality.</span></span>

<span data-ttu-id="57b5a-136">有关如何部署 DaRT 恢复映像的详细信息，请参阅[部署 dart 7.0 恢复映像](deploying-the-dart-70-recovery-image-dart-7.md)。</span><span class="sxs-lookup"><span data-stu-id="57b5a-136">For more information about how to deploy DaRT recovery images, see [Deploying the DaRT 7.0 Recovery Image](deploying-the-dart-70-recovery-image-dart-7.md).</span></span>

## <span data-ttu-id="57b5a-137">相关主题</span><span class="sxs-lookup"><span data-stu-id="57b5a-137">Related topics</span></span>


[<span data-ttu-id="57b5a-138">DaRT 7.0 入门</span><span class="sxs-lookup"><span data-stu-id="57b5a-138">Getting Started with DaRT 7.0</span></span>](getting-started-with-dart-70-new-ia.md)

[<span data-ttu-id="57b5a-139">DaRT 7.0 发行说明</span><span class="sxs-lookup"><span data-stu-id="57b5a-139">Release Notes for DaRT 7.0</span></span>](release-notes-for-dart-70-new-ia.md)

 

 





