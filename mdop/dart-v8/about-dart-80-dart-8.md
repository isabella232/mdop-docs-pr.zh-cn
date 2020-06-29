---
title: 关于 DaRT 8.0
description: 关于 DaRT 8.0
author: dansimp
ms.assetid: ce91efd6-7d78-44cb-bb8f-1f43f768ebaa
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: e70816425dc4775b11596b91d7b5c0045830c6ad
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802937"
---
# <span data-ttu-id="9569b-103">关于 DaRT 8.0</span><span class="sxs-lookup"><span data-stu-id="9569b-103">About DaRT 8.0</span></span>


<span data-ttu-id="9569b-104">Microsoft 诊断和恢复工具集（DaRT）8.0 帮助你诊断和修复基于 Windows 的计算机。</span><span class="sxs-lookup"><span data-stu-id="9569b-104">Microsoft Diagnostics and Recovery Toolset (DaRT) 8.0 helps you troubleshoot and repair Windows-based computers.</span></span> <span data-ttu-id="9569b-105">这包括无法启动的计算机。</span><span class="sxs-lookup"><span data-stu-id="9569b-105">This includes those computers that cannot be started.</span></span> <span data-ttu-id="9569b-106">DaRT 8.0 是一组功能强大的工具，用于扩展 Windows 恢复环境（WinRE）。</span><span class="sxs-lookup"><span data-stu-id="9569b-106">DaRT 8.0 is a powerful set of tools that extend the Windows Recovery Environment (WinRE).</span></span> <span data-ttu-id="9569b-107">通过使用 DaRT，你可以分析问题以确定其原因，例如检查计算机的事件日志或系统注册表。</span><span class="sxs-lookup"><span data-stu-id="9569b-107">By using DaRT, you can analyze an issue to determine its cause, for example, by inspecting the computer’s event log or system registry.</span></span> <span data-ttu-id="9569b-108">DaRT 支持恢复包含分区（例如，主分区和逻辑驱动器）的基本硬盘，并支持卷恢复。</span><span class="sxs-lookup"><span data-stu-id="9569b-108">DaRT supports the recovery of basic hard disks that contain partitions, for example, primary partitions and logical drives, and supports the recovery of volumes.</span></span>

<span data-ttu-id="9569b-109">**注意** DaRT 不支持动态磁盘的恢复。</span><span class="sxs-lookup"><span data-stu-id="9569b-109">**Note** DaRT does not support the recovery of dynamic disks.</span></span>

 

<span data-ttu-id="9569b-110">DaRT 还提供工具来帮助您在确定原因后立即修复问题。</span><span class="sxs-lookup"><span data-stu-id="9569b-110">DaRT also provides tools to help you fix a problem as soon as you determine the cause.</span></span> <span data-ttu-id="9569b-111">例如，你可以使用 DaRT 中的工具禁用错误的设备驱动程序、删除修补程序、还原已删除的文件和扫描计算机，即使你无法或不应启动已安装的 Windows 操作系统也是如此。</span><span class="sxs-lookup"><span data-stu-id="9569b-111">For example, you can use the tools in DaRT to disable a faulty device driver, remove hotfixes, restore deleted files, and scan the computer for malware even when you cannot or should not start the installed Windows operating system.</span></span>

<span data-ttu-id="9569b-112">DaRT 可帮助你快速恢复运行32位或64位版本的 Windows 8 的计算机，通常比重新映像计算机所花费的时间更少。</span><span class="sxs-lookup"><span data-stu-id="9569b-112">DaRT can help you quickly recover computers that are running either 32-bit or 64-bit versions of Windows 8, typically in less time than it would take to reimage the computer.</span></span>

<span data-ttu-id="9569b-113">DaRT 中的功能允许你创建恢复映像。</span><span class="sxs-lookup"><span data-stu-id="9569b-113">Functionality in DaRT lets you create a recovery image.</span></span> <span data-ttu-id="9569b-114">恢复映像将启动 Windows 恢复环境（Windows RE），从该环境中，你可以启动**诊断和恢复工具集**窗口并访问 DaRT 工具。</span><span class="sxs-lookup"><span data-stu-id="9569b-114">The recovery image starts Windows Recovery Environment (Windows RE), from which you can start the **Diagnostics and Recovery Toolset** window and access the DaRT tools.</span></span>

<span data-ttu-id="9569b-115">使用**Dart 恢复映像向导**创建 DaRT 恢复映像。</span><span class="sxs-lookup"><span data-stu-id="9569b-115">Use the **DaRT Recovery Image Wizard** to create the DaRT recovery image.</span></span> <span data-ttu-id="9569b-116">默认情况下，向导创建国际标准化组织（ISO）图像文件和 Windows 映像格式（WIM）文件，并允许你将映像刻录到 CD、DVD 或 USB。</span><span class="sxs-lookup"><span data-stu-id="9569b-116">By default, the wizard creates an International Organization for Standardization (ISO) image file and a Windows Imaging Format (WIM) file and let you burn the image to a CD, DVD, or USB.</span></span> <span data-ttu-id="9569b-117">你可以在最终用户的计算机本地部署映像，也可以从本地硬盘上的远程网络分区或恢复分区部署该映像。</span><span class="sxs-lookup"><span data-stu-id="9569b-117">You can deploy the image locally at end user’s computers, or you can deploy it from a remote network partition or a recovery partition on the local hard drive.</span></span>

## <a href="" id="what-s-new-in-dart-8-0"></a><span data-ttu-id="9569b-118">DaRT 8.0 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="9569b-118">What’s new in DaRT 8.0</span></span>


<span data-ttu-id="9569b-119">DaRT 8.0 可帮助你快速恢复运行32位或64位版本的 Windows 8 的计算机，通常比重新映像计算机所用的时间更少。</span><span class="sxs-lookup"><span data-stu-id="9569b-119">DaRT 8.0 can help you quickly recover computers that are running either 32-bit or 64-bit versions of Windows 8, typically in less time than it would take to reimage the computer.</span></span> <span data-ttu-id="9569b-120">DaRT 8.0 具有以下新增功能。</span><span class="sxs-lookup"><span data-stu-id="9569b-120">DaRT 8.0 has the following new features.</span></span>

### <span data-ttu-id="9569b-121">使用 Windows 8 或 Windows Server 2012 创建 DaRT 映像</span><span class="sxs-lookup"><span data-stu-id="9569b-121">Create DaRT images by using Windows 8 or Windows Server 2012</span></span>

<span data-ttu-id="9569b-122">DaRT 8.0 使你能够使用 Windows®8或 Windows Server®2012创建 DaRT 映像。</span><span class="sxs-lookup"><span data-stu-id="9569b-122">DaRT 8.0 enables you to create DaRT images using either Windows® 8 or Windows Server® 2012.</span></span> <span data-ttu-id="9569b-123">对于早于 Windows 8 和 Windows Server 2012 的 Windows 版本，客户应继续使用早期版本的 DaRT。</span><span class="sxs-lookup"><span data-stu-id="9569b-123">For versions of Windows earlier than Windows 8 and Windows Server 2012, customers should continue to use earlier versions of DaRT.</span></span>

### <span data-ttu-id="9569b-124">从一台计算机生成32和64位图像</span><span class="sxs-lookup"><span data-stu-id="9569b-124">Generate both 32- and 64-bit images from one computer</span></span>

<span data-ttu-id="9569b-125">DaRT 8.0 使你可以从运行 DaRT 的单个计算机生成32位和64位图像，无论该计算机是32还是64位计算机。</span><span class="sxs-lookup"><span data-stu-id="9569b-125">DaRT 8.0 enables you to generate both 32-bit and 64-bit images from a single computer that is running DaRT, regardless of whether the computer is a 32-bit or 64-bit computer.</span></span> <span data-ttu-id="9569b-126">在 DaRT7 中，创建的映像与运行 DaRT 的计算机必须具有相同的、比上的相同。</span><span class="sxs-lookup"><span data-stu-id="9569b-126">In DaRT7, the image that was created had to be the same, bit-wise, as the computer that was running DaRT.</span></span>

### <span data-ttu-id="9569b-127">创建一个支持具有 BIOS 或 UEFI 接口的计算机的映像</span><span class="sxs-lookup"><span data-stu-id="9569b-127">Create one image that supports computers that have either a BIOS or UEFI interface</span></span>

<span data-ttu-id="9569b-128">DaRT 8.0 对统一可扩展固件接口（UEFI）和 BIOS 接口的支持使你能够仅创建一个可与具有任何接口的计算机配合使用的映像。</span><span class="sxs-lookup"><span data-stu-id="9569b-128">DaRT 8.0’s support for both the Unified Extensible Firmware Interface (UEFI) and BIOS interfaces enables you to create just one image that works with computers that have either interface.</span></span>

### <span data-ttu-id="9569b-129">使用 GUID 分区表（GPT）进行分区</span><span class="sxs-lookup"><span data-stu-id="9569b-129">Use a GUID partition table (GPT) for partitioning</span></span>

<span data-ttu-id="9569b-130">DaRT 8.0 工具现在支持 Windows 8 GPT 磁盘，这提供了一种比较旧的主引导记录（MBR）分区方案更灵活的磁盘分区。</span><span class="sxs-lookup"><span data-stu-id="9569b-130">DaRT 8.0 tools now support Windows 8 GPT disks, which provide a more flexible mechanism for partitioning disks than the older master boot record (MBR) partitioning scheme.</span></span> <span data-ttu-id="9569b-131">DaRT 8.0 工具继续支持 MBR 分区。</span><span class="sxs-lookup"><span data-stu-id="9569b-131">DaRT 8.0 tools continue to support MBR partitioning.</span></span>

### <span data-ttu-id="9569b-132">在本地硬盘上安装 Windows 8 和 Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="9569b-132">Install Windows 8 and Windows Server 2012 on the local hard disk</span></span>

<span data-ttu-id="9569b-133">只有当 Windows 8 和 Windows Server 2012 安装在本地硬盘上时，才能使用 DaRT 8.0 工具。</span><span class="sxs-lookup"><span data-stu-id="9569b-133">DaRT 8.0 tools can be used only when Windows 8 and Windows Server 2012 are installed on the local hard disk.</span></span> <span data-ttu-id="9569b-134">目前，不支持 Windows To Go。</span><span class="sxs-lookup"><span data-stu-id="9569b-134">Currently, there is no support for Windows To Go.</span></span>

### <a href="" id="-------------dart-8-0-release-notes"></a> <span data-ttu-id="9569b-135">DaRT 8.0 发行说明</span><span class="sxs-lookup"><span data-stu-id="9569b-135">DaRT 8.0 release notes</span></span>

<span data-ttu-id="9569b-136">有关详细信息，以及未在文档中执行的最新消息，请参阅[DaRT 8.0 的发行说明](release-notes-for-dart-80--dart-8.md)。</span><span class="sxs-lookup"><span data-stu-id="9569b-136">For more information, and for late-breaking news that did not make it into the documentation, see the [Release Notes for DaRT 8.0](release-notes-for-dart-80--dart-8.md).</span></span>

## <span data-ttu-id="9569b-137">如何获取 DaRT 8。0</span><span class="sxs-lookup"><span data-stu-id="9569b-137">How to Get DaRT 8.0</span></span>


<span data-ttu-id="9569b-138">此技术是 Microsoft 桌面优化包（MDOP）的一部分。</span><span class="sxs-lookup"><span data-stu-id="9569b-138">This technology is a part of the Microsoft Desktop Optimization Pack (MDOP).</span></span> <span data-ttu-id="9569b-139">MDOP 是 Microsoft 软件保障的一部分。</span><span class="sxs-lookup"><span data-stu-id="9569b-139">MDOP is part of Microsoft Software Assurance.</span></span> <span data-ttu-id="9569b-140">有关 Microsoft 软件保证和获取 MDOP 的详细信息，请参阅[如何获取 mdop](https://go.microsoft.com/fwlink/?LinkId=322049) （ https://go.microsoft.com/fwlink/?LinkId=322049) 。</span><span class="sxs-lookup"><span data-stu-id="9569b-140">For more information about Microsoft Software Assurance and acquiring MDOP, see [How Do I Get MDOP](https://go.microsoft.com/fwlink/?LinkId=322049) (https://go.microsoft.com/fwlink/?LinkId=322049).</span></span>

## <span data-ttu-id="9569b-141">相关主题</span><span class="sxs-lookup"><span data-stu-id="9569b-141">Related topics</span></span>


[<span data-ttu-id="9569b-142">DaRT 8.0 入门</span><span class="sxs-lookup"><span data-stu-id="9569b-142">Getting Started with DaRT 8.0</span></span>](getting-started-with-dart-80-dart-8.md)

[<span data-ttu-id="9569b-143">DaRT 8.0 发行说明</span><span class="sxs-lookup"><span data-stu-id="9569b-143">Release Notes for DaRT 8.0</span></span>](release-notes-for-dart-80--dart-8.md)

 

 





