---
title: DaRT 7.0 中的工具概述
description: DaRT 7.0 中的工具概述
author: dansimp
ms.assetid: 67c5991e-cbe6-4ce9-9fe5-f1761369d1fe
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d327e14fd1851f0e0d82e1c3ad692bcf7842a835
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803369"
---
# <span data-ttu-id="81f45-103">DaRT 7.0 中的工具概述</span><span class="sxs-lookup"><span data-stu-id="81f45-103">Overview of the Tools in DaRT 7.0</span></span>


<span data-ttu-id="81f45-104">从 Microsoft 诊断和恢复工具集（DaRT）7中的 "**诊断和恢复工具集**" 窗口中，你可以启动在创建 DaRT 恢复映像时所包含的任何单个工具。</span><span class="sxs-lookup"><span data-stu-id="81f45-104">From the **Diagnostics and Recovery Toolset** window in Microsoft Diagnostics and Recovery Toolset (DaRT)7, you can start any of the individual tools that were included when the DaRT recovery image was created.</span></span> <span data-ttu-id="81f45-105">有关如何访问 "**诊断和恢复工具集**" 窗口的信息，请参阅[如何使用 DaRT 恢复映像恢复本地计算机](how-to-recover-local-computers-using-the-dart-recovery-image-dart-7.md)。</span><span class="sxs-lookup"><span data-stu-id="81f45-105">For information about how to access the **Diagnostics and Recovery Toolset** window, see [How to Recover Local Computers Using the DaRT Recovery Image](how-to-recover-local-computers-using-the-dart-recovery-image-dart-7.md).</span></span>

<span data-ttu-id="81f45-106">如果可用，则可以使用 "**诊断和恢复工具集**" 窗口上的 "**解决方案向导**" 来选择最适合你的特定问题的工具，具体取决于简短的面试。</span><span class="sxs-lookup"><span data-stu-id="81f45-106">If it is available, you can use the **Solution Wizard** on the **Diagnostics and Recovery Toolset** window to select the tool that best addresses your particular issue, based on a brief interview.</span></span>

## <span data-ttu-id="81f45-107">探索 DaRT 工具</span><span class="sxs-lookup"><span data-stu-id="81f45-107">Exploring the DaRT Tools</span></span>


<span data-ttu-id="81f45-108">本部分介绍了 DaRT 中的各种工具。</span><span class="sxs-lookup"><span data-stu-id="81f45-108">This section describes the various tools that are part of DaRT.</span></span>

### <span data-ttu-id="81f45-109">注册表编辑器</span><span class="sxs-lookup"><span data-stu-id="81f45-109">Registry Editor</span></span>

<span data-ttu-id="81f45-110">可以使用**注册表编辑器**访问和更改正在分析或修复的 Windows 操作系统的注册表。</span><span class="sxs-lookup"><span data-stu-id="81f45-110">You can use **Registry Editor** to access and change the registry of the Windows operating system that you are analyzing or repairing.</span></span> <span data-ttu-id="81f45-111">这包括添加、删除和编辑注册表项和值，以及导入注册表（.reg）文件。</span><span class="sxs-lookup"><span data-stu-id="81f45-111">This includes adding, removing, and editing keys and values, and importing registry (.reg) files.</span></span>

<span data-ttu-id="81f45-112">**小心** 本主题介绍如何使用注册表编辑器更改 Windows 注册表。</span><span class="sxs-lookup"><span data-stu-id="81f45-112">**Caution** This topic describes how to change the Windows registry by using Registry Editor.</span></span> <span data-ttu-id="81f45-113">如果不正确地更改 Windows 注册表，则可能会导致严重问题，可能需要重新安装 Windows。</span><span class="sxs-lookup"><span data-stu-id="81f45-113">If you change the Windows registry incorrectly, you can cause serious problems that might require you to reinstall Windows.</span></span> <span data-ttu-id="81f45-114">在更改注册表之前，应创建注册表文件（.dat 和 .dat）的备份副本。</span><span class="sxs-lookup"><span data-stu-id="81f45-114">You should make a backup copy of the registry files (System.dat and User.dat) before you change the registry.</span></span> <span data-ttu-id="81f45-115">Microsoft 无法保证更改注册表时可能出现的问题可以解决。</span><span class="sxs-lookup"><span data-stu-id="81f45-115">Microsoft cannot guarantee that the problems that might occur when you change the registry can be resolved.</span></span> <span data-ttu-id="81f45-116">更改注册表的风险由您自己承担。</span><span class="sxs-lookup"><span data-stu-id="81f45-116">Change the registry at your own risk.</span></span>

 

### <span data-ttu-id="81f45-117">Locksmith</span><span class="sxs-lookup"><span data-stu-id="81f45-117">Locksmith</span></span>

<span data-ttu-id="81f45-118">在**Locksmith 向导**中，你可以设置或更改你正在分析或修复的 Windows 操作系统上的任何本地帐户的密码。</span><span class="sxs-lookup"><span data-stu-id="81f45-118">The **Locksmith Wizard** lets you set or change the password for any local account on the Windows operating system that you are analyzing or repairing.</span></span> <span data-ttu-id="81f45-119">您无需知道当前密码。</span><span class="sxs-lookup"><span data-stu-id="81f45-119">You do not have to know the current password.</span></span> <span data-ttu-id="81f45-120">但是，你设置的密码必须符合由本地组策略对象定义的任何要求。</span><span class="sxs-lookup"><span data-stu-id="81f45-120">However, the password that you set must comply with any requirements that are defined by a local Group Policy object.</span></span> <span data-ttu-id="81f45-121">这包括密码长度和复杂性。</span><span class="sxs-lookup"><span data-stu-id="81f45-121">This includes password length and complexity.</span></span>

<span data-ttu-id="81f45-122">当本地帐户（如本地管理员帐户）的密码未知时，可以使用**Locksmith** 。</span><span class="sxs-lookup"><span data-stu-id="81f45-122">You can use **Locksmith** when the password for a local account, such as the local Administrator account, is unknown.</span></span> <span data-ttu-id="81f45-123">不能使用**Locksmith**设置域帐户的密码。</span><span class="sxs-lookup"><span data-stu-id="81f45-123">You cannot use **Locksmith** to set passwords for domain accounts.</span></span>

### <span data-ttu-id="81f45-124">崩溃分析器</span><span class="sxs-lookup"><span data-stu-id="81f45-124">Crash Analyzer</span></span>

<span data-ttu-id="81f45-125">通过分析正在修复的 Windows 操作系统上的内存转储文件，使用**崩溃分析器向导**快速确定计算机崩溃的原因。</span><span class="sxs-lookup"><span data-stu-id="81f45-125">Use the **Crash Analyzer Wizard** to quickly determine the cause of a computer crash by analyzing the memory dump file on the Windows operating system that you are repairing.</span></span> <span data-ttu-id="81f45-126">**故障分析器**检查导致计算机失败的驱动程序的故障转储文件。</span><span class="sxs-lookup"><span data-stu-id="81f45-126">**Crash Analyzer** examines the crash dump file for the driver that caused a computer to fail.</span></span> <span data-ttu-id="81f45-127">然后，您可以使用 "**计算机管理**" 工具中的 "**服务和驱动程序**" 节点禁用有问题的设备驱动程序。</span><span class="sxs-lookup"><span data-stu-id="81f45-127">Then, you can disable the problem device driver by using the **Services and Drivers** node in the **Computer Management** tool.</span></span>

<span data-ttu-id="81f45-128">"**崩溃分析器" 向导**需要用于你正在修复的操作系统的 Windows 调试工具和符号文件。</span><span class="sxs-lookup"><span data-stu-id="81f45-128">The **Crash Analyzer Wizard** requires the Debugging Tools for Windows and symbol files for the operating system that you are repairing.</span></span> <span data-ttu-id="81f45-129">你可以在创建 DaRT 恢复映像时包括这两个要求。</span><span class="sxs-lookup"><span data-stu-id="81f45-129">You can include both requirements when you create the DaRT recovery image.</span></span> <span data-ttu-id="81f45-130">如果它们未包括在恢复映像中，并且你无法在你正在修复的计算机上访问它们，则可以将内存转储文件复制到另一台计算机并使用独立版本的**崩溃分析**程序来诊断问题。</span><span class="sxs-lookup"><span data-stu-id="81f45-130">If they are not included on the recovery image and you do not have access to them on the computer that you are repairing, you can copy the memory dump file to another computer and use the stand-alone version of **Crash Analyzer** to diagnose the problem.</span></span>

<span data-ttu-id="81f45-131">即使您计划重新映像计算机，运行**崩溃分析器**也是一个好主意。</span><span class="sxs-lookup"><span data-stu-id="81f45-131">Running **Crash Analyzer** is a good idea even if you plan to reimage the computer.</span></span> <span data-ttu-id="81f45-132">该映像可能存在导致你的环境中出现问题的缺陷驱动程序。</span><span class="sxs-lookup"><span data-stu-id="81f45-132">The image could have a defective driver that is causing problems in your environment.</span></span> <span data-ttu-id="81f45-133">通过运行**崩溃分析器**，你可以识别问题驱动程序并提高映像稳定性。</span><span class="sxs-lookup"><span data-stu-id="81f45-133">By running **Crash Analyzer**, you can identify problem drivers and improve the image stability.</span></span>

<span data-ttu-id="81f45-134">有关**崩溃分析器**的详细信息，请参阅[诊断故障分析器的系统故障](diagnosing-system-failures-with-crash-analyzer--dart-7.md)。</span><span class="sxs-lookup"><span data-stu-id="81f45-134">For more information about **Crash Analyzer**, see [Diagnosing System Failures with Crash Analyzer](diagnosing-system-failures-with-crash-analyzer--dart-7.md).</span></span>

### <span data-ttu-id="81f45-135">文件还原</span><span class="sxs-lookup"><span data-stu-id="81f45-135">File Restore</span></span>

<span data-ttu-id="81f45-136">通过**文件还原**，你可以尝试还原意外删除或太大的文件，使其无法放入回收站。</span><span class="sxs-lookup"><span data-stu-id="81f45-136">**File Restore** lets you try to restore files that were accidentally deleted or that were too big to fit in the Recycle Bin.</span></span> <span data-ttu-id="81f45-137">**文件还原**不仅限于常规磁盘卷，还可以在丢失的卷上或在由 BitLocker 加密的卷上查找和还原文件。</span><span class="sxs-lookup"><span data-stu-id="81f45-137">**File Restore** is not limited to regular disk volumes, but can find and restore files on lost volumes or on volumes that are encrypted by BitLocker.</span></span>

### <span data-ttu-id="81f45-138">磁盘指挥</span><span class="sxs-lookup"><span data-stu-id="81f45-138">Disk Commander</span></span>

<span data-ttu-id="81f45-139">**磁盘控制程序**允许你使用下列恢复过程之一恢复和修复磁盘分区或卷：</span><span class="sxs-lookup"><span data-stu-id="81f45-139">**Disk Commander** lets you recover and repair disk partitions or volumes by using one of the following recovery processes:</span></span>

-   <span data-ttu-id="81f45-140">还原主启动记录（MBR）</span><span class="sxs-lookup"><span data-stu-id="81f45-140">Restore the master boot record (MBR)</span></span>

-   <span data-ttu-id="81f45-141">恢复一个或多个丢失的卷</span><span class="sxs-lookup"><span data-stu-id="81f45-141">Recover one or more lost volumes</span></span>

-   <span data-ttu-id="81f45-142">从**磁盘控制程序**备份中还原分区表</span><span class="sxs-lookup"><span data-stu-id="81f45-142">Restore partition tables from **Disk Commander** backup</span></span>

-   <span data-ttu-id="81f45-143">将分区表保存到**磁盘控制程序**备份</span><span class="sxs-lookup"><span data-stu-id="81f45-143">Save partition tables to **Disk Commander** backup</span></span>

<span data-ttu-id="81f45-144">**警告** 我们建议您在使用 "**磁盘指挥**" 修复磁盘之前备份磁盘。</span><span class="sxs-lookup"><span data-stu-id="81f45-144">**Warning** We recommend that you back up a disk before you use **Disk Commander** to repair it.</span></span> <span data-ttu-id="81f45-145">通过使用**磁盘指挥**，你可能会损坏卷并使其不可访问。</span><span class="sxs-lookup"><span data-stu-id="81f45-145">By using **Disk Commander**, you can potentially damage volumes and make them inaccessible.</span></span> <span data-ttu-id="81f45-146">此外，对一个卷的更改可能会影响其他卷，因为磁盘上的卷共享分区表。</span><span class="sxs-lookup"><span data-stu-id="81f45-146">Additionally, changes to one volume can affect other volumes because volumes on a disk share a partition table.</span></span>

 

### <span data-ttu-id="81f45-147">磁盘擦除</span><span class="sxs-lookup"><span data-stu-id="81f45-147">Disk Wipe</span></span>

<span data-ttu-id="81f45-148">你可以使用 "**磁盘擦除**" 功能删除磁盘或卷上的所有数据，甚至是在重新格式化硬盘驱动器后留下的数据。</span><span class="sxs-lookup"><span data-stu-id="81f45-148">You can use **Disk Wipe** to delete all data from a disk or volume, even the data that is left behind after you reformat a hard disk drive.</span></span> <span data-ttu-id="81f45-149">利用 "**磁盘擦除**" 功能，您可以从单遍覆盖或4遍覆盖（满足当前美国国防部标准）进行选择。</span><span class="sxs-lookup"><span data-stu-id="81f45-149">**Disk Wipe** lets you select from either a single-pass overwrite or a four-pass overwrite, which meets current U.S. Department of Defense standards.</span></span>

<span data-ttu-id="81f45-150">**警告** 擦除磁盘或卷后，将无法恢复数据。</span><span class="sxs-lookup"><span data-stu-id="81f45-150">**Warning** After wiping a disk or volume, you cannot recover the data.</span></span> <span data-ttu-id="81f45-151">先验证卷的大小和标签，然后再将其清除。</span><span class="sxs-lookup"><span data-stu-id="81f45-151">Verify the size and label of a volume before erasing it.</span></span>

 

### <span data-ttu-id="81f45-152">计算机管理</span><span class="sxs-lookup"><span data-stu-id="81f45-152">Computer Management</span></span>

<span data-ttu-id="81f45-153">"**计算机管理**" 是 Windows 管理工具的集合，可帮助你对问题计算机进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="81f45-153">**Computer Management** is a collection of Windows administrative tools that help you troubleshoot a problem computer.</span></span> <span data-ttu-id="81f45-154">你可以使用 DaRT 中的**计算机管理**工具查看系统信息和事件日志、管理磁盘、列出 autoruns 以及管理服务和驱动程序。</span><span class="sxs-lookup"><span data-stu-id="81f45-154">You can use the **Computer Management** tools in DaRT to view system information and event logs, manage disks, list autoruns, and manage services and drivers.</span></span> <span data-ttu-id="81f45-155">"**计算机管理**" 控制台已自定义，可帮助你诊断和修复可能阻止 Windows 操作系统启动的问题。</span><span class="sxs-lookup"><span data-stu-id="81f45-155">The **Computer Management** console is customized to help you diagnose and repair problems that might be preventing the Windows operating system from starting.</span></span>

### <span data-ttu-id="81f45-156">浏览</span><span class="sxs-lookup"><span data-stu-id="81f45-156">Explorer</span></span>

<span data-ttu-id="81f45-157">利用 "**资源管理器**" 工具，你可以浏览计算机的文件系统和网络共享，以便你可以在尝试修复或重新映像计算机之前删除用户存储在本地驱动器上的重要数据。</span><span class="sxs-lookup"><span data-stu-id="81f45-157">The **Explorer** tool lets you browse the computer’s file system and network shares so that you can remove important data that the user stored on the local drive before you try to repair or reimage the computer.</span></span> <span data-ttu-id="81f45-158">由于你可以将驱动器号映射到网络共享，因此你可以轻松地将文件从计算机复制并移动到网络以进行保管或从网络复制到计算机以还原它们。</span><span class="sxs-lookup"><span data-stu-id="81f45-158">And because you can map drive letters to network shares, you can easily copy and move files from the computer to the network for safekeeping or from the network to the computer to restore them.</span></span>

### <span data-ttu-id="81f45-159">解决方案向导</span><span class="sxs-lookup"><span data-stu-id="81f45-159">Solution Wizard</span></span>

<span data-ttu-id="81f45-160">**解决方案向导**将提供一系列问题，然后根据你的回答建议适用情况的最佳工具。</span><span class="sxs-lookup"><span data-stu-id="81f45-160">The **Solution Wizard** presents a series of questions and then recommends the best tool for the situation, based on your answers.</span></span> <span data-ttu-id="81f45-161">此向导可帮助你确定在不熟悉 DaRT 中的工具时要使用的工具。</span><span class="sxs-lookup"><span data-stu-id="81f45-161">This wizard helps you determine which tool to use when you are not familiar with the tools in DaRT.</span></span>

### <span data-ttu-id="81f45-162">TCP/IP 配置</span><span class="sxs-lookup"><span data-stu-id="81f45-162">TCP/IP Config</span></span>

<span data-ttu-id="81f45-163">当您将有问题的计算机启动到 DaRT 时，它将设置为从动态主机配置协议（DHCP）自动获取其 TCP/IP 配置（IP 地址和 DNS 服务器）。</span><span class="sxs-lookup"><span data-stu-id="81f45-163">When you boot a problem computer into DaRT, it is set to automatically obtain its TCP/IP configuration (IP address and DNS server) from Dynamic Host Configuration Protocol (DHCP).</span></span> <span data-ttu-id="81f45-164">如果 DHCP 不可用，则可以使用**Tcp/ip 配置**工具手动配置 tcp/ip。</span><span class="sxs-lookup"><span data-stu-id="81f45-164">If DHCP is unavailable, you can manually configure TCP/IP by using the **TCP/IP Config** tool.</span></span> <span data-ttu-id="81f45-165">首先选择一个网络适配器，然后为该适配器配置 IP 地址和 DNS 服务器。</span><span class="sxs-lookup"><span data-stu-id="81f45-165">You first select a network adapter, and then configure the IP address and DNS server for that adapter.</span></span>

### <span data-ttu-id="81f45-166">修补程序卸载</span><span class="sxs-lookup"><span data-stu-id="81f45-166">Hotfix Uninstall</span></span>

<span data-ttu-id="81f45-167">**修复程序卸载向导**允许您从正在修复的计算机上的 Windows 操作系统中删除修补程序或服务包。</span><span class="sxs-lookup"><span data-stu-id="81f45-167">The **Hotfix Uninstall Wizard** lets you remove hotfixes or service packs from the Windows operating system on the computer that you are repairing.</span></span> <span data-ttu-id="81f45-168">当怀疑修补程序或 service pack 阻止操作系统启动时，请使用此工具。</span><span class="sxs-lookup"><span data-stu-id="81f45-168">Use this tool when a hotfix or service pack is suspected in preventing the operating system from starting.</span></span>

<span data-ttu-id="81f45-169">我们建议你一次仅卸载一个修补程序，即使该工具允许你卸载多个修补程序。</span><span class="sxs-lookup"><span data-stu-id="81f45-169">We recommend that you uninstall only one hotfix at a time, even though the tool lets you uninstall more than one.</span></span>

<span data-ttu-id="81f45-170">**重要提示** 卸载修补程序后安装或更新的程序可能无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="81f45-170">**Important** Programs that were installed or updated after a hotfix was installed might not work correctly after you uninstall a hotfix.</span></span>

 

### <span data-ttu-id="81f45-171">SFC 扫描</span><span class="sxs-lookup"><span data-stu-id="81f45-171">SFC Scan</span></span>

<span data-ttu-id="81f45-172">**SFC 扫描**工具将启动**系统文件修复向导**，并允许你修复阻止已安装的 Windows 操作系统启动的系统文件。</span><span class="sxs-lookup"><span data-stu-id="81f45-172">The **SFC Scan** tool starts the **System File Repair Wizard** and lets you repair system files that are preventing the installed Windows operating system from starting.</span></span> <span data-ttu-id="81f45-173">"**系统文件修复" 向导**可以自动修复损坏或丢失的系统文件，也可以在执行任何修复之前提示您。</span><span class="sxs-lookup"><span data-stu-id="81f45-173">The **System File Repair Wizard** can automatically repair system files that are corrupted or missing, or it can prompt you before it performs any repairs.</span></span>

### <span data-ttu-id="81f45-174">搜索</span><span class="sxs-lookup"><span data-stu-id="81f45-174">Search</span></span>

<span data-ttu-id="81f45-175">在对计算机进行映像前，从本地硬盘恢复文件非常重要，尤其是当用户可能未在其他位置备份或存储文件时。</span><span class="sxs-lookup"><span data-stu-id="81f45-175">Before reimaging a computer, recovering files from the local hard disk is important, especially when the user might not have backed up or stored the files elsewhere.</span></span>

<span data-ttu-id="81f45-176">**搜索**工具会打开一个**文件搜索**窗口，当你不知道文件路径或在所有本地硬盘上搜索常规类型的文件时，可以使用该窗口查找文档。</span><span class="sxs-lookup"><span data-stu-id="81f45-176">The **Search** tool opens a **File Search** window that you can use to find documents when you do not know the file path or to search for general kinds of files across all local hard disks.</span></span> <span data-ttu-id="81f45-177">你可以在特定路径中搜索特定的文件名模式。</span><span class="sxs-lookup"><span data-stu-id="81f45-177">You can search for specific file-name patterns in specific paths.</span></span> <span data-ttu-id="81f45-178">您还可以将结果限制为日期范围或大小范围。</span><span class="sxs-lookup"><span data-stu-id="81f45-178">You can also limit results to a date range or size range.</span></span>

### <span data-ttu-id="81f45-179">独立系统 Sweeper</span><span class="sxs-lookup"><span data-stu-id="81f45-179">Standalone System Sweeper</span></span>

<span data-ttu-id="81f45-180">**重要提示** 部署了独立系统 Sweeper 的环境应改为使用 Microsoft Defender Offline （WDO）防护映像进行恶意软件检测。</span><span class="sxs-lookup"><span data-stu-id="81f45-180">**Important** Environments with the Standalone System Sweeper deployed should instead use the Microsoft Defender Offline (WDO) protection image for malware detection.</span></span> <span data-ttu-id="81f45-181">由于独立系统 Sweeper 工具如何集成到 DaRT，因此所有受支持的 DaRT 版本部署都无法将这些反恶意软件更新应用到其 DaRT 映像。</span><span class="sxs-lookup"><span data-stu-id="81f45-181">Because of how the Standalone System Sweeper tool integrates into DaRT, all supported DaRT version deployments cannot apply these anti-malware updates to their DaRT images.</span></span>

 

<span data-ttu-id="81f45-182">**独立的系统 Sweeper**可帮助检测恶意软件和不需要的软件，并向您发出安全风险警告。</span><span class="sxs-lookup"><span data-stu-id="81f45-182">The **Standalone System Sweeper** can help detect malware and unwanted software and warn you of security risks.</span></span> <span data-ttu-id="81f45-183">即使安装的 Windows 操作系统未运行时，你也可以使用此工具扫描计算机并删除恶意软件。</span><span class="sxs-lookup"><span data-stu-id="81f45-183">You can use this tool to scan a computer for and remove malware even when the installed Windows operating system is not running.</span></span> <span data-ttu-id="81f45-184">当**独立系统 Sweeper**检测到恶意或不需要的软件时，它会提示你为每个项目删除、隔离或允许。</span><span class="sxs-lookup"><span data-stu-id="81f45-184">When the **Standalone System Sweeper** detects malicious or unwanted software, it prompts you to remove, quarantine, or allow for each item.</span></span>

<span data-ttu-id="81f45-185">使用 rootkit 的恶意软件可以从正在运行的操作系统屏蔽自身。</span><span class="sxs-lookup"><span data-stu-id="81f45-185">Malware that uses rootkits can mask itself from the running operating system.</span></span> <span data-ttu-id="81f45-186">如果计算机中存在受 rootkit 支持的病毒或间谍软件，则大多数实时扫描和删除工具将无法再查看或删除。</span><span class="sxs-lookup"><span data-stu-id="81f45-186">If a rootkit-enabled virus or spyware is in a computer, most real-time scanning and removal tools can no longer see it or remove it.</span></span> <span data-ttu-id="81f45-187">由于你将有问题的计算机引导到 DaRT，并且安装的操作系统处于离线状态，因此你可以检测 rootkit，而无需将其自身屏蔽。</span><span class="sxs-lookup"><span data-stu-id="81f45-187">Because you boot the problem computer into DaRT and the installed operating system is offline, you can detect the rootkit without it being able to mask itself.</span></span>

### <span data-ttu-id="81f45-188">远程连接</span><span class="sxs-lookup"><span data-stu-id="81f45-188">Remote Connection</span></span>

<span data-ttu-id="81f45-189">DaRT 中的**远程连接**工具可让你在最终用户计算机上远程运行 DaRT 工具。</span><span class="sxs-lookup"><span data-stu-id="81f45-189">The **Remote Connection** tool in DaRT lets you remotely run the DaRT tools on an end-user computer.</span></span> <span data-ttu-id="81f45-190">当最终用户（或由支持最终用户计算机的技术支持人员）提供特定信息后，IT 管理员可以控制最终用户的计算机并远程运行必要的 DaRT 工具。</span><span class="sxs-lookup"><span data-stu-id="81f45-190">After certain specific information is provided by the end user (or by a helpdesk professional working on the end-user computer), the IT administrator can take control of the end user's computer and run the necessary DaRT tools remotely.</span></span>

<span data-ttu-id="81f45-191">**重要提示** 建立远程连接的两台计算机必须是同一网络的一部分。</span><span class="sxs-lookup"><span data-stu-id="81f45-191">**Important** The two computers establishing a remote connection must be part of the same network.</span></span>

 

## <span data-ttu-id="81f45-192">相关主题</span><span class="sxs-lookup"><span data-stu-id="81f45-192">Related topics</span></span>


[<span data-ttu-id="81f45-193">DaRT 7.0 入门</span><span class="sxs-lookup"><span data-stu-id="81f45-193">Getting Started with DaRT 7.0</span></span>](getting-started-with-dart-70-new-ia.md)

 

 





