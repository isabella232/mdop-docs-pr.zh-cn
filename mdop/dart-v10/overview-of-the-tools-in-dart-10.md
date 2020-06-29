---
title: DaRT 10 中的工具概述
description: DaRT 10 中的工具概述
author: dansimp
ms.assetid: 752467dd-b646-4335-82ce-9090d4651f65
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8bef2b92e998bebffae526d4288c76be081fe0a9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803279"
---
# <span data-ttu-id="61938-103">DaRT 10 中的工具概述</span><span class="sxs-lookup"><span data-stu-id="61938-103">Overview of the Tools in DaRT 10</span></span>


<span data-ttu-id="61938-104">从 Microsoft 诊断和恢复工具集（DaRT）10中的 "**诊断和恢复工具集**" 窗口中，你可以启动在创建 DaRT 10 恢复映像时包含的任何单个工具。</span><span class="sxs-lookup"><span data-stu-id="61938-104">From the **Diagnostics and Recovery Toolset** window in Microsoft Diagnostics and Recovery Toolset (DaRT) 10, you can start any of the individual tools that you include when you create the DaRT 10 recovery image.</span></span> <span data-ttu-id="61938-105">有关如何访问 "**诊断和恢复工具集**" 窗口的信息，请参阅[如何使用 DaRT 恢复映像恢复本地计算机](how-to-recover-local-computers-by-using-the-dart-recovery-image-dart-10.md)。</span><span class="sxs-lookup"><span data-stu-id="61938-105">For information about how to access the **Diagnostics and Recovery Toolset** window, see [How to Recover Local Computers by Using the DaRT Recovery Image](how-to-recover-local-computers-by-using-the-dart-recovery-image-dart-10.md).</span></span>

<span data-ttu-id="61938-106">如果可用，则可以使用 "**诊断和恢复工具集**" 窗口上的 "**解决方案向导**" 选择最适合你的特定问题的工具，具体取决于向导提供的简短面试。</span><span class="sxs-lookup"><span data-stu-id="61938-106">If it is available, you can use the **Solution Wizard** on the **Diagnostics and Recovery Toolset** window to select the tool that best addresses your particular issue, based on a brief interview that the wizard provides.</span></span>

## <span data-ttu-id="61938-107">探索 DaRT 工具</span><span class="sxs-lookup"><span data-stu-id="61938-107">Exploring the DaRT tools</span></span>


<span data-ttu-id="61938-108">以下是 DaRT 10 工具的说明。</span><span class="sxs-lookup"><span data-stu-id="61938-108">A description of the DaRT 10 tools follows.</span></span>

### <span data-ttu-id="61938-109">计算机管理</span><span class="sxs-lookup"><span data-stu-id="61938-109">Computer Management</span></span>

<span data-ttu-id="61938-110">"**计算机管理**" 是 Windows 管理工具的集合，可帮助你对问题计算机进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="61938-110">**Computer Management** is a collection of Windows administrative tools that help you troubleshoot a problem computer.</span></span> <span data-ttu-id="61938-111">你可以使用 DaRT 中的**计算机管理**工具查看系统信息和事件日志、管理磁盘、列出 autoruns 以及管理服务和驱动程序。</span><span class="sxs-lookup"><span data-stu-id="61938-111">You can use the **Computer Management** tools in DaRT to view system information and event logs, manage disks, list autoruns, and manage services and drivers.</span></span> <span data-ttu-id="61938-112">"**计算机管理**" 控制台已自定义，可帮助你诊断和修复可能阻止 Windows 操作系统启动的问题。</span><span class="sxs-lookup"><span data-stu-id="61938-112">The **Computer Management** console is customized to help you diagnose and repair problems that might be preventing the Windows operating system from starting.</span></span>

<span data-ttu-id="61938-113">**注意** 不支持将动态磁盘恢复为 DaRT。</span><span class="sxs-lookup"><span data-stu-id="61938-113">**Note** The recovery of dynamic disks with DaRT is not supported.</span></span>

 

### <span data-ttu-id="61938-114">崩溃分析器</span><span class="sxs-lookup"><span data-stu-id="61938-114">Crash Analyzer</span></span>

<span data-ttu-id="61938-115">通过分析正在修复的 Windows 操作系统上的内存转储文件，使用**崩溃分析器向导**快速确定计算机故障的原因。</span><span class="sxs-lookup"><span data-stu-id="61938-115">Use the **Crash Analyzer Wizard** to quickly determine the cause of a computer failure by analyzing the memory dump file on the Windows operating system that you are repairing.</span></span> <span data-ttu-id="61938-116">**故障分析器**检查导致计算机失败的驱动程序的内存转储文件。</span><span class="sxs-lookup"><span data-stu-id="61938-116">**Crash Analyzer** examines the memory dump file for the driver that caused a computer to fail.</span></span> <span data-ttu-id="61938-117">然后，您可以使用 "**计算机管理**" 工具中的 "**服务和驱动程序**" 节点禁用有问题的设备驱动程序。</span><span class="sxs-lookup"><span data-stu-id="61938-117">You can then disable the problem device driver by using the **Services and Drivers** node in the **Computer Management** tool.</span></span>

<span data-ttu-id="61938-118">"**崩溃分析器" 向导**需要用于你正在修复的操作系统的 Windows 调试工具和符号文件。</span><span class="sxs-lookup"><span data-stu-id="61938-118">The **Crash Analyzer Wizard** requires the Debugging Tools for Windows and symbol files for the operating system that you are repairing.</span></span> <span data-ttu-id="61938-119">你可以在创建 DaRT 恢复映像时包括这两个要求。</span><span class="sxs-lookup"><span data-stu-id="61938-119">You can include both requirements when you create the DaRT recovery image.</span></span> <span data-ttu-id="61938-120">如果它们未包括在恢复映像中，并且你无法在你正在修复的计算机上访问它们，则可以将内存转储文件复制到另一台计算机并使用独立版本的**崩溃分析**程序来诊断问题。</span><span class="sxs-lookup"><span data-stu-id="61938-120">If they are not included on the recovery image and you do not have access to them on the computer that you are repairing, you can copy the memory dump file to another computer and use the stand-alone version of **Crash Analyzer** to diagnose the problem.</span></span>

<span data-ttu-id="61938-121">即使您计划重新映像计算机，运行**崩溃分析器**也是一个好主意。</span><span class="sxs-lookup"><span data-stu-id="61938-121">Running **Crash Analyzer** is a good idea even if you plan to reimage the computer.</span></span> <span data-ttu-id="61938-122">该映像可能存在导致你的环境中出现问题的缺陷驱动程序。</span><span class="sxs-lookup"><span data-stu-id="61938-122">The image could have a defective driver that is causing problems in your environment.</span></span> <span data-ttu-id="61938-123">通过运行**崩溃分析器**，你可以识别问题驱动程序并提高映像稳定性。</span><span class="sxs-lookup"><span data-stu-id="61938-123">By running **Crash Analyzer**, you can identify problem drivers and improve the image stability.</span></span>

<span data-ttu-id="61938-124">有关**崩溃分析器**的详细信息，请参阅[诊断故障分析器的系统故障](diagnosing-system-failures-with-crash-analyzer-dart-10.md)。</span><span class="sxs-lookup"><span data-stu-id="61938-124">For more information about **Crash Analyzer**, see [Diagnosing System Failures with Crash Analyzer](diagnosing-system-failures-with-crash-analyzer-dart-10.md).</span></span>

### <span data-ttu-id="61938-125">磁盘指挥</span><span class="sxs-lookup"><span data-stu-id="61938-125">Disk Commander</span></span>

<span data-ttu-id="61938-126">**磁盘控制程序**允许你使用下列恢复过程之一恢复和修复磁盘分区或卷：</span><span class="sxs-lookup"><span data-stu-id="61938-126">**Disk Commander** lets you recover and repair disk partitions or volumes by using one of the following recovery processes:</span></span>

-   <span data-ttu-id="61938-127">还原主启动记录（MBR）</span><span class="sxs-lookup"><span data-stu-id="61938-127">Restore the master boot record (MBR)</span></span>

-   <span data-ttu-id="61938-128">恢复一个或多个丢失的卷</span><span class="sxs-lookup"><span data-stu-id="61938-128">Recover one or more lost volumes</span></span>

-   <span data-ttu-id="61938-129">从**磁盘控制程序**备份中还原分区表</span><span class="sxs-lookup"><span data-stu-id="61938-129">Restore partition tables from **Disk Commander** backup</span></span>

-   <span data-ttu-id="61938-130">将分区表保存到**磁盘控制程序**备份</span><span class="sxs-lookup"><span data-stu-id="61938-130">Save partition tables to **Disk Commander** backup</span></span>

<span data-ttu-id="61938-131">**警告** 我们建议您在使用 "**磁盘指挥**" 修复磁盘之前备份磁盘。</span><span class="sxs-lookup"><span data-stu-id="61938-131">**Warning** We recommend that you back up a disk before you use **Disk Commander** to repair it.</span></span> <span data-ttu-id="61938-132">通过使用**磁盘指挥**，你可能会损坏卷并使其不可访问。</span><span class="sxs-lookup"><span data-stu-id="61938-132">By using **Disk Commander**, you can potentially damage volumes and make them inaccessible.</span></span> <span data-ttu-id="61938-133">此外，对一个卷的更改可能会影响其他卷，因为磁盘上的卷共享分区表。</span><span class="sxs-lookup"><span data-stu-id="61938-133">Additionally, changes to one volume can affect other volumes because volumes on a disk share a partition table.</span></span>

 

<span data-ttu-id="61938-134">**注意** 不支持将动态磁盘恢复为 DaRT。</span><span class="sxs-lookup"><span data-stu-id="61938-134">**Note** The recovery of dynamic disks with DaRT is not supported.</span></span>

 

### <span data-ttu-id="61938-135">磁盘擦除</span><span class="sxs-lookup"><span data-stu-id="61938-135">Disk Wipe</span></span>

<span data-ttu-id="61938-136">你可以使用 "**磁盘擦除**" 功能删除磁盘或卷上的所有数据，甚至是在重新格式化硬盘驱动器后留下的数据。</span><span class="sxs-lookup"><span data-stu-id="61938-136">You can use **Disk Wipe** to delete all data from a disk or volume, even the data that is left behind after you reformat a hard disk drive.</span></span> <span data-ttu-id="61938-137">利用 "**磁盘擦除**" 功能，您可以从单遍覆盖或4遍覆盖（满足当前美国国防部标准）进行选择。</span><span class="sxs-lookup"><span data-stu-id="61938-137">**Disk Wipe** lets you select from either a single-pass overwrite or a four-pass overwrite, which meets current U.S. Department of Defense standards.</span></span>

<span data-ttu-id="61938-138">**警告** 擦除磁盘或卷后，将无法恢复数据。</span><span class="sxs-lookup"><span data-stu-id="61938-138">**Warning** After wiping a disk or volume, you cannot recover the data.</span></span> <span data-ttu-id="61938-139">先验证卷的大小和标签，然后再将其清除。</span><span class="sxs-lookup"><span data-stu-id="61938-139">Verify the size and label of a volume before erasing it.</span></span>

 

### <span data-ttu-id="61938-140">浏览</span><span class="sxs-lookup"><span data-stu-id="61938-140">Explorer</span></span>

<span data-ttu-id="61938-141">利用 "**资源管理器**" 工具，你可以浏览计算机的文件系统和网络共享，以便你可以在尝试修复或重新映像计算机之前删除用户存储在本地驱动器上的重要数据。</span><span class="sxs-lookup"><span data-stu-id="61938-141">The **Explorer** tool lets you browse the computer’s file system and network shares so that you can remove important data that the user stored on the local drive before you try to repair or reimage the computer.</span></span> <span data-ttu-id="61938-142">由于你可以将驱动器号映射到网络共享，因此你可以轻松地将文件从计算机复制并移动到网络以进行保管或从网络复制到计算机以还原它们。</span><span class="sxs-lookup"><span data-stu-id="61938-142">And because you can map drive letters to network shares, you can easily copy and move files from the computer to the network for safekeeping or from the network to the computer to restore them.</span></span>

### <span data-ttu-id="61938-143">文件还原</span><span class="sxs-lookup"><span data-stu-id="61938-143">File Restore</span></span>

<span data-ttu-id="61938-144">通过**文件还原**，你可以尝试还原意外删除或太大的文件，使其无法放入回收站。</span><span class="sxs-lookup"><span data-stu-id="61938-144">**File Restore** lets you try to restore files that were accidentally deleted or that were too big to fit in the Recycle Bin.</span></span> <span data-ttu-id="61938-145">**文件还原**不仅限于常规磁盘卷，还可以在丢失的卷上或在由 BitLocker 加密的卷上查找和还原文件。</span><span class="sxs-lookup"><span data-stu-id="61938-145">**File Restore** is not limited to regular disk volumes, but can find and restore files on lost volumes or on volumes that are encrypted by BitLocker.</span></span>

<span data-ttu-id="61938-146">**注意** 不支持将动态磁盘恢复为 DaRT。</span><span class="sxs-lookup"><span data-stu-id="61938-146">**Note** The recovery of dynamic disks with DaRT is not supported.</span></span>

 

### <span data-ttu-id="61938-147">文件搜索</span><span class="sxs-lookup"><span data-stu-id="61938-147">File Search</span></span>

<span data-ttu-id="61938-148">在对计算机进行映像前，从本地硬盘恢复文件非常重要，尤其是当用户可能未在其他位置备份或存储文件时。</span><span class="sxs-lookup"><span data-stu-id="61938-148">Before reimaging a computer, recovering files from the local hard disk is important, especially when the user might not have backed up or stored the files elsewhere.</span></span>

<span data-ttu-id="61938-149">**搜索**工具会打开一个**文件搜索**窗口，当你不知道文件路径或在所有本地硬盘上搜索常规类型的文件时，可以使用该窗口查找文档。</span><span class="sxs-lookup"><span data-stu-id="61938-149">The **Search** tool opens a **File Search** window that you can use to find documents when you do not know the file path or to search for general kinds of files across all local hard disks.</span></span> <span data-ttu-id="61938-150">你可以在特定路径中搜索特定的文件名模式。</span><span class="sxs-lookup"><span data-stu-id="61938-150">You can search for specific file-name patterns in specific paths.</span></span> <span data-ttu-id="61938-151">您还可以将结果限制为日期范围或大小范围。</span><span class="sxs-lookup"><span data-stu-id="61938-151">You can also limit results to a date range or size range.</span></span>

### <span data-ttu-id="61938-152">修补程序卸载</span><span class="sxs-lookup"><span data-stu-id="61938-152">Hotfix Uninstall</span></span>

<span data-ttu-id="61938-153">**修复程序卸载向导**允许您从正在修复的计算机上的 Windows 操作系统中删除修补程序或服务包。</span><span class="sxs-lookup"><span data-stu-id="61938-153">The **Hotfix Uninstall Wizard** lets you remove hotfixes or service packs from the Windows operating system on the computer that you are repairing.</span></span> <span data-ttu-id="61938-154">当怀疑修补程序或 service pack 阻止操作系统启动时，请使用此工具。</span><span class="sxs-lookup"><span data-stu-id="61938-154">Use this tool when a hotfix or service pack is suspected in preventing the operating system from starting.</span></span>

<span data-ttu-id="61938-155">我们建议你一次仅卸载一个修补程序，即使该工具允许你卸载多个修补程序。</span><span class="sxs-lookup"><span data-stu-id="61938-155">We recommend that you uninstall only one hotfix at a time, even though the tool lets you uninstall more than one.</span></span>

<span data-ttu-id="61938-156">**重要提示** 卸载修补程序后安装或更新的程序可能无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="61938-156">**Important** Programs that were installed or updated after a hotfix was installed might not work correctly after you uninstall a hotfix.</span></span>

 

### <span data-ttu-id="61938-157">Locksmith</span><span class="sxs-lookup"><span data-stu-id="61938-157">Locksmith</span></span>

<span data-ttu-id="61938-158">在**Locksmith 向导**中，你可以设置或更改你正在分析或修复的 Windows 操作系统上的任何本地帐户的密码。</span><span class="sxs-lookup"><span data-stu-id="61938-158">The **Locksmith Wizard** lets you set or change the password for any local account on the Windows operating system that you are analyzing or repairing.</span></span> <span data-ttu-id="61938-159">您无需知道当前密码。</span><span class="sxs-lookup"><span data-stu-id="61938-159">You do not have to know the current password.</span></span> <span data-ttu-id="61938-160">但是，你设置的密码必须符合由本地组策略对象定义的任何要求。</span><span class="sxs-lookup"><span data-stu-id="61938-160">However, the password that you set must comply with any requirements that are defined by a local Group Policy Object.</span></span> <span data-ttu-id="61938-161">这包括密码长度和复杂性。</span><span class="sxs-lookup"><span data-stu-id="61938-161">This includes password length and complexity.</span></span>

<span data-ttu-id="61938-162">当本地帐户（如本地管理员帐户）的密码未知时，可以使用**Locksmith** 。</span><span class="sxs-lookup"><span data-stu-id="61938-162">You can use **Locksmith** when the password for a local account, such as the local Administrator account, is unknown.</span></span> <span data-ttu-id="61938-163">不能使用**Locksmith**设置域帐户的密码。</span><span class="sxs-lookup"><span data-stu-id="61938-163">You cannot use **Locksmith** to set passwords for domain accounts.</span></span>

### <span data-ttu-id="61938-164">注册表编辑器</span><span class="sxs-lookup"><span data-stu-id="61938-164">Registry Editor</span></span>

<span data-ttu-id="61938-165">可以使用**注册表编辑器**访问和更改正在分析或修复的 Windows 操作系统的注册表。</span><span class="sxs-lookup"><span data-stu-id="61938-165">You can use **Registry Editor** to access and change the registry of the Windows operating system that you are analyzing or repairing.</span></span> <span data-ttu-id="61938-166">这包括添加、删除和编辑注册表项和值，以及导入注册表（.reg）文件。</span><span class="sxs-lookup"><span data-stu-id="61938-166">This includes adding, removing, and editing keys and values, and importing registry (.reg) files.</span></span>

<span data-ttu-id="61938-167">**警告** 如果使用**注册表编辑器**错误地更改注册表，可能会出现严重问题。</span><span class="sxs-lookup"><span data-stu-id="61938-167">**Warning** Serious problems can occur if you change the registry incorrectly by using **Registry Editor**.</span></span> <span data-ttu-id="61938-168">可能需要重新安装操作系统才能解决这些问题。</span><span class="sxs-lookup"><span data-stu-id="61938-168">These problems might require you to reinstall the operating system.</span></span> <span data-ttu-id="61938-169">在对注册表进行更改之前，应备份计算机上的任何重要数据。</span><span class="sxs-lookup"><span data-stu-id="61938-169">Before you make changes to the registry, you should back up any valued data on the computer.</span></span> <span data-ttu-id="61938-170">更改注册表的风险由您自己承担。</span><span class="sxs-lookup"><span data-stu-id="61938-170">Change the registry at your own risk.</span></span>

 

### <span data-ttu-id="61938-171">SFC 扫描</span><span class="sxs-lookup"><span data-stu-id="61938-171">SFC Scan</span></span>

<span data-ttu-id="61938-172">**SFC 扫描**工具将启动**系统文件修复向导**，并允许你修复阻止已安装的 Windows 操作系统启动的系统文件。</span><span class="sxs-lookup"><span data-stu-id="61938-172">The **SFC Scan** tool starts the **System File Repair Wizard** and lets you repair system files that are preventing the installed Windows operating system from starting.</span></span> <span data-ttu-id="61938-173">"**系统文件修复" 向导**可以自动修复损坏或丢失的系统文件，也可以在执行任何修复之前提示您。</span><span class="sxs-lookup"><span data-stu-id="61938-173">The **System File Repair Wizard** can automatically repair system files that are corrupted or missing, or it can prompt you before it performs any repairs.</span></span>

### <span data-ttu-id="61938-174">解决方案向导</span><span class="sxs-lookup"><span data-stu-id="61938-174">Solution Wizard</span></span>

<span data-ttu-id="61938-175">**解决方案向导**将提供一系列问题，然后根据你的回答建议适用情况的最佳工具。</span><span class="sxs-lookup"><span data-stu-id="61938-175">The **Solution Wizard** presents a series of questions and then recommends the best tool for the situation, based on your answers.</span></span> <span data-ttu-id="61938-176">此向导可帮助你确定在不熟悉 DaRT 中的工具时要使用的工具。</span><span class="sxs-lookup"><span data-stu-id="61938-176">This wizard helps you determine which tool to use when you are not familiar with the tools in DaRT.</span></span>

### <span data-ttu-id="61938-177">TCP/IP 配置</span><span class="sxs-lookup"><span data-stu-id="61938-177">TCP/IP Config</span></span>

<span data-ttu-id="61938-178">当您将有问题的计算机启动到 DaRT 时，它将设置为从动态主机配置协议（DHCP）自动获取其 TCP/IP 配置（IP 地址和 DNS 服务器）。</span><span class="sxs-lookup"><span data-stu-id="61938-178">When you boot a problem computer into DaRT, it is set to automatically obtain its TCP/IP configuration (IP address and DNS server) from Dynamic Host Configuration Protocol (DHCP).</span></span> <span data-ttu-id="61938-179">如果 DHCP 不可用，则可以使用**Tcp/ip 配置**工具手动配置 tcp/ip。</span><span class="sxs-lookup"><span data-stu-id="61938-179">If DHCP is unavailable, you can manually configure TCP/IP by using the **TCP/IP Config** tool.</span></span> <span data-ttu-id="61938-180">首先选择一个网络适配器，然后为该适配器配置 IP 地址和 DNS 服务器。</span><span class="sxs-lookup"><span data-stu-id="61938-180">You first select a network adapter, and then configure the IP address and DNS server for that adapter.</span></span>

## <span data-ttu-id="61938-181">相关主题</span><span class="sxs-lookup"><span data-stu-id="61938-181">Related topics</span></span>


[<span data-ttu-id="61938-182">DaRT 10 入门</span><span class="sxs-lookup"><span data-stu-id="61938-182">Getting Started with DaRT 10</span></span>](getting-started-with-dart-10.md)

 

 





