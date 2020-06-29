---
title: DaRT 8.0 中的工具概述
description: DaRT 8.0 中的工具概述
author: dansimp
ms.assetid: 1766c82e-c099-47d4-b186-4689b026a7e0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 10/03/2016
ms.openlocfilehash: a058f6018888f446782aa8f3a18ee89570840c2a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803604"
---
# <span data-ttu-id="36f8c-103">DaRT 8.0 中的工具概述</span><span class="sxs-lookup"><span data-stu-id="36f8c-103">Overview of the Tools in DaRT 8.0</span></span>


<span data-ttu-id="36f8c-104">从 Microsoft 诊断和恢复工具集（DaRT）8.0 中的 "**诊断和恢复工具集**" 窗口中，你可以启动在创建 DaRT 8.0 恢复映像时包含的任何单个工具。</span><span class="sxs-lookup"><span data-stu-id="36f8c-104">From the **Diagnostics and Recovery Toolset** window in Microsoft Diagnostics and Recovery Toolset (DaRT) 8.0, you can start any of the individual tools that you include when you create the DaRT 8.0 recovery image.</span></span> <span data-ttu-id="36f8c-105">有关如何访问 "**诊断和恢复工具集**" 窗口的信息，请参阅[如何使用 DaRT 恢复映像恢复本地计算机](how-to-recover-local-computers-by-using-the-dart-recovery-image-dart-8.md)。</span><span class="sxs-lookup"><span data-stu-id="36f8c-105">For information about how to access the **Diagnostics and Recovery Toolset** window, see [How to Recover Local Computers by Using the DaRT Recovery Image](how-to-recover-local-computers-by-using-the-dart-recovery-image-dart-8.md).</span></span>

<span data-ttu-id="36f8c-106">如果可用，则可以使用 "**诊断和恢复工具集**" 窗口上的 "**解决方案向导**" 选择最适合你的特定问题的工具，具体取决于向导提供的简短面试。</span><span class="sxs-lookup"><span data-stu-id="36f8c-106">If it is available, you can use the **Solution Wizard** on the **Diagnostics and Recovery Toolset** window to select the tool that best addresses your particular issue, based on a brief interview that the wizard provides.</span></span>

## <span data-ttu-id="36f8c-107">探索 DaRT 工具</span><span class="sxs-lookup"><span data-stu-id="36f8c-107">Exploring the DaRT tools</span></span>


<span data-ttu-id="36f8c-108">以下是 DaRT 8.0 工具的说明。</span><span class="sxs-lookup"><span data-stu-id="36f8c-108">A description of the DaRT 8.0 tools follows.</span></span>

### <span data-ttu-id="36f8c-109">计算机管理</span><span class="sxs-lookup"><span data-stu-id="36f8c-109">Computer Management</span></span>

<span data-ttu-id="36f8c-110">"**计算机管理**" 是 Windows 管理工具的集合，可帮助你对问题计算机进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="36f8c-110">**Computer Management** is a collection of Windows administrative tools that help you troubleshoot a problem computer.</span></span> <span data-ttu-id="36f8c-111">你可以使用 DaRT 中的**计算机管理**工具查看系统信息和事件日志、管理磁盘、列出 autoruns 以及管理服务和驱动程序。</span><span class="sxs-lookup"><span data-stu-id="36f8c-111">You can use the **Computer Management** tools in DaRT to view system information and event logs, manage disks, list autoruns, and manage services and drivers.</span></span> <span data-ttu-id="36f8c-112">"**计算机管理**" 控制台已自定义，可帮助你诊断和修复可能阻止 Windows 操作系统启动的问题。</span><span class="sxs-lookup"><span data-stu-id="36f8c-112">The **Computer Management** console is customized to help you diagnose and repair problems that might be preventing the Windows operating system from starting.</span></span>

<span data-ttu-id="36f8c-113">**注意** 不支持将动态磁盘恢复为 DaRT。</span><span class="sxs-lookup"><span data-stu-id="36f8c-113">**Note** The recovery of dynamic disks with DaRT is not supported.</span></span>

 

### <span data-ttu-id="36f8c-114">崩溃分析器</span><span class="sxs-lookup"><span data-stu-id="36f8c-114">Crash Analyzer</span></span>

<span data-ttu-id="36f8c-115">通过分析正在修复的 Windows 操作系统上的内存转储文件，使用**崩溃分析器向导**快速确定计算机故障的原因。</span><span class="sxs-lookup"><span data-stu-id="36f8c-115">Use the **Crash Analyzer Wizard** to quickly determine the cause of a computer failure by analyzing the memory dump file on the Windows operating system that you are repairing.</span></span> <span data-ttu-id="36f8c-116">**故障分析器**检查导致计算机失败的驱动程序的内存转储文件。</span><span class="sxs-lookup"><span data-stu-id="36f8c-116">**Crash Analyzer** examines the memory dump file for the driver that caused a computer to fail.</span></span> <span data-ttu-id="36f8c-117">然后，您可以使用 "**计算机管理**" 工具中的 "**服务和驱动程序**" 节点禁用有问题的设备驱动程序。</span><span class="sxs-lookup"><span data-stu-id="36f8c-117">You can then disable the problem device driver by using the **Services and Drivers** node in the **Computer Management** tool.</span></span>

<span data-ttu-id="36f8c-118">"**崩溃分析器" 向导**需要用于你正在修复的操作系统的 Windows 调试工具和符号文件。</span><span class="sxs-lookup"><span data-stu-id="36f8c-118">The **Crash Analyzer Wizard** requires the Debugging Tools for Windows and symbol files for the operating system that you are repairing.</span></span> <span data-ttu-id="36f8c-119">你可以在创建 DaRT 恢复映像时包括这两个要求。</span><span class="sxs-lookup"><span data-stu-id="36f8c-119">You can include both requirements when you create the DaRT recovery image.</span></span> <span data-ttu-id="36f8c-120">如果它们未包括在恢复映像中，并且你无法在你正在修复的计算机上访问它们，则可以将内存转储文件复制到另一台计算机并使用独立版本的**崩溃分析**程序来诊断问题。</span><span class="sxs-lookup"><span data-stu-id="36f8c-120">If they are not included on the recovery image and you do not have access to them on the computer that you are repairing, you can copy the memory dump file to another computer and use the stand-alone version of **Crash Analyzer** to diagnose the problem.</span></span>

<span data-ttu-id="36f8c-121">即使您计划重新映像计算机，运行**崩溃分析器**也是一个好主意。</span><span class="sxs-lookup"><span data-stu-id="36f8c-121">Running **Crash Analyzer** is a good idea even if you plan to reimage the computer.</span></span> <span data-ttu-id="36f8c-122">该映像可能存在导致你的环境中出现问题的缺陷驱动程序。</span><span class="sxs-lookup"><span data-stu-id="36f8c-122">The image could have a defective driver that is causing problems in your environment.</span></span> <span data-ttu-id="36f8c-123">通过运行**崩溃分析器**，你可以识别问题驱动程序并提高映像稳定性。</span><span class="sxs-lookup"><span data-stu-id="36f8c-123">By running **Crash Analyzer**, you can identify problem drivers and improve the image stability.</span></span>

<span data-ttu-id="36f8c-124">有关**崩溃分析器**的详细信息，请参阅[诊断故障分析器的系统故障](diagnosing-system-failures-with-crash-analyzer--dart-8.md)。</span><span class="sxs-lookup"><span data-stu-id="36f8c-124">For more information about **Crash Analyzer**, see [Diagnosing System Failures with Crash Analyzer](diagnosing-system-failures-with-crash-analyzer--dart-8.md).</span></span>

### <span data-ttu-id="36f8c-125">Defender</span><span class="sxs-lookup"><span data-stu-id="36f8c-125">Defender</span></span>

<span data-ttu-id="36f8c-126">**重要提示** 部署了 DaRT Defender 的环境应改为使用 Microsoft Defender Offline （WDO）保护映像进行恶意软件检测。</span><span class="sxs-lookup"><span data-stu-id="36f8c-126">**Important** Environments with the DaRT Defender deployed should instead use the Microsoft Defender Offline (WDO) protection image for malware detection.</span></span> <span data-ttu-id="36f8c-127">由于 Defender 工具集成到了 DaRT，因此所有受支持的 DaRT 版本部署都无法将这些反恶意软件更新应用到其 DaRT 映像。</span><span class="sxs-lookup"><span data-stu-id="36f8c-127">Because of how the Defender tool integrates into DaRT, all supported DaRT version deployments cannot apply these anti-malware updates to their DaRT images.</span></span> <span data-ttu-id="36f8c-128">有关详细信息，请参阅[Microsoft 诊断和恢复工具集（DaRT）用户应使用 Microsoft Defender Offline （WDO）进行恶意软件检测-->](use-windows-defender-offline-wdo-for-malware-protection-not-dart.md)。</span><span class="sxs-lookup"><span data-stu-id="36f8c-128">For more information, see  [Microsoft Diagnostics and Recovery Toolset (DaRT) users should use Microsoft Defender Offline (WDO) for malware detection-->](use-windows-defender-offline-wdo-for-malware-protection-not-dart.md).</span></span>

 

<span data-ttu-id="36f8c-129">**Defender**可帮助检测恶意软件和不需要的软件，并向你发出安全风险警告。</span><span class="sxs-lookup"><span data-stu-id="36f8c-129">**Defender** can help detect malware and unwanted software and warn you of security risks.</span></span> <span data-ttu-id="36f8c-130">即使安装的 Windows 操作系统未运行时，你也可以使用此工具扫描计算机并删除恶意软件。</span><span class="sxs-lookup"><span data-stu-id="36f8c-130">You can use this tool to scan a computer for and remove malware even when the installed Windows operating system is not running.</span></span> <span data-ttu-id="36f8c-131">当**Defender**检测到恶意或不需要的软件时，它会提示你为每个项目删除、隔离或允许。</span><span class="sxs-lookup"><span data-stu-id="36f8c-131">When **Defender** detects malicious or unwanted software, it prompts you to remove, quarantine, or allow for each item.</span></span>

<span data-ttu-id="36f8c-132">使用 rootkit 的恶意软件可以从正在运行的操作系统屏蔽自身。</span><span class="sxs-lookup"><span data-stu-id="36f8c-132">Malware that uses rootkits can mask itself from the running operating system.</span></span> <span data-ttu-id="36f8c-133">如果计算机中存在受 rootkit 支持的病毒或间谍软件，则大多数实时扫描和删除工具将无法再查看或删除。</span><span class="sxs-lookup"><span data-stu-id="36f8c-133">If a rootkit-enabled virus or spyware is in a computer, most real-time scanning and removal tools can no longer see it or remove it.</span></span> <span data-ttu-id="36f8c-134">由于你将有问题的计算机引导到 DaRT，并且安装的操作系统处于离线状态，因此你可以检测 rootkit，而无需将其自身屏蔽。</span><span class="sxs-lookup"><span data-stu-id="36f8c-134">Because you boot the problem computer into DaRT and the installed operating system is offline, you can detect the rootkit without it being able to mask itself.</span></span>

### <span data-ttu-id="36f8c-135">磁盘指挥</span><span class="sxs-lookup"><span data-stu-id="36f8c-135">Disk Commander</span></span>

<span data-ttu-id="36f8c-136">**磁盘控制程序**允许你使用下列恢复过程之一恢复和修复磁盘分区或卷：</span><span class="sxs-lookup"><span data-stu-id="36f8c-136">**Disk Commander** lets you recover and repair disk partitions or volumes by using one of the following recovery processes:</span></span>

-   <span data-ttu-id="36f8c-137">还原主启动记录（MBR）</span><span class="sxs-lookup"><span data-stu-id="36f8c-137">Restore the master boot record (MBR)</span></span>

-   <span data-ttu-id="36f8c-138">恢复一个或多个丢失的卷</span><span class="sxs-lookup"><span data-stu-id="36f8c-138">Recover one or more lost volumes</span></span>

-   <span data-ttu-id="36f8c-139">从**磁盘控制程序**备份中还原分区表</span><span class="sxs-lookup"><span data-stu-id="36f8c-139">Restore partition tables from **Disk Commander** backup</span></span>

-   <span data-ttu-id="36f8c-140">将分区表保存到**磁盘控制程序**备份</span><span class="sxs-lookup"><span data-stu-id="36f8c-140">Save partition tables to **Disk Commander** backup</span></span>

<span data-ttu-id="36f8c-141">**警告** 我们建议您在使用 "**磁盘指挥**" 修复磁盘之前备份磁盘。</span><span class="sxs-lookup"><span data-stu-id="36f8c-141">**Warning** We recommend that you back up a disk before you use **Disk Commander** to repair it.</span></span> <span data-ttu-id="36f8c-142">通过使用**磁盘指挥**，你可能会损坏卷并使其不可访问。</span><span class="sxs-lookup"><span data-stu-id="36f8c-142">By using **Disk Commander**, you can potentially damage volumes and make them inaccessible.</span></span> <span data-ttu-id="36f8c-143">此外，对一个卷的更改可能会影响其他卷，因为磁盘上的卷共享分区表。</span><span class="sxs-lookup"><span data-stu-id="36f8c-143">Additionally, changes to one volume can affect other volumes because volumes on a disk share a partition table.</span></span>

 

<span data-ttu-id="36f8c-144">**注意** 不支持将动态磁盘恢复为 DaRT。</span><span class="sxs-lookup"><span data-stu-id="36f8c-144">**Note** The recovery of dynamic disks with DaRT is not supported.</span></span>

 

### <span data-ttu-id="36f8c-145">磁盘擦除</span><span class="sxs-lookup"><span data-stu-id="36f8c-145">Disk Wipe</span></span>

<span data-ttu-id="36f8c-146">你可以使用 "**磁盘擦除**" 功能删除磁盘或卷上的所有数据，甚至是在重新格式化硬盘驱动器后留下的数据。</span><span class="sxs-lookup"><span data-stu-id="36f8c-146">You can use **Disk Wipe** to delete all data from a disk or volume, even the data that is left behind after you reformat a hard disk drive.</span></span> <span data-ttu-id="36f8c-147">利用 "**磁盘擦除**" 功能，您可以从单遍覆盖或4遍覆盖（满足当前美国国防部标准）进行选择。</span><span class="sxs-lookup"><span data-stu-id="36f8c-147">**Disk Wipe** lets you select from either a single-pass overwrite or a four-pass overwrite, which meets current U.S. Department of Defense standards.</span></span>

<span data-ttu-id="36f8c-148">**警告** 擦除磁盘或卷后，将无法恢复数据。</span><span class="sxs-lookup"><span data-stu-id="36f8c-148">**Warning** After wiping a disk or volume, you cannot recover the data.</span></span> <span data-ttu-id="36f8c-149">先验证卷的大小和标签，然后再将其清除。</span><span class="sxs-lookup"><span data-stu-id="36f8c-149">Verify the size and label of a volume before erasing it.</span></span>

 

### <span data-ttu-id="36f8c-150">浏览</span><span class="sxs-lookup"><span data-stu-id="36f8c-150">Explorer</span></span>

<span data-ttu-id="36f8c-151">利用 "**资源管理器**" 工具，你可以浏览计算机的文件系统和网络共享，以便你可以在尝试修复或重新映像计算机之前删除用户存储在本地驱动器上的重要数据。</span><span class="sxs-lookup"><span data-stu-id="36f8c-151">The **Explorer** tool lets you browse the computer’s file system and network shares so that you can remove important data that the user stored on the local drive before you try to repair or reimage the computer.</span></span> <span data-ttu-id="36f8c-152">由于你可以将驱动器号映射到网络共享，因此你可以轻松地将文件从计算机复制并移动到网络以进行保管或从网络复制到计算机以还原它们。</span><span class="sxs-lookup"><span data-stu-id="36f8c-152">And because you can map drive letters to network shares, you can easily copy and move files from the computer to the network for safekeeping or from the network to the computer to restore them.</span></span>

### <span data-ttu-id="36f8c-153">文件还原</span><span class="sxs-lookup"><span data-stu-id="36f8c-153">File Restore</span></span>

<span data-ttu-id="36f8c-154">通过**文件还原**，你可以尝试还原意外删除或太大的文件，使其无法放入回收站。</span><span class="sxs-lookup"><span data-stu-id="36f8c-154">**File Restore** lets you try to restore files that were accidentally deleted or that were too big to fit in the Recycle Bin.</span></span> <span data-ttu-id="36f8c-155">**文件还原**不仅限于常规磁盘卷，还可以在丢失的卷上或在由 BitLocker 加密的卷上查找和还原文件。</span><span class="sxs-lookup"><span data-stu-id="36f8c-155">**File Restore** is not limited to regular disk volumes, but can find and restore files on lost volumes or on volumes that are encrypted by BitLocker.</span></span>

<span data-ttu-id="36f8c-156">**注意** 不支持将动态磁盘恢复为 DaRT。</span><span class="sxs-lookup"><span data-stu-id="36f8c-156">**Note** The recovery of dynamic disks with DaRT is not supported.</span></span>

 

### <span data-ttu-id="36f8c-157">文件搜索</span><span class="sxs-lookup"><span data-stu-id="36f8c-157">File Search</span></span>

<span data-ttu-id="36f8c-158">在对计算机进行映像前，从本地硬盘恢复文件非常重要，尤其是当用户可能未在其他位置备份或存储文件时。</span><span class="sxs-lookup"><span data-stu-id="36f8c-158">Before reimaging a computer, recovering files from the local hard disk is important, especially when the user might not have backed up or stored the files elsewhere.</span></span>

<span data-ttu-id="36f8c-159">**搜索**工具会打开一个**文件搜索**窗口，当你不知道文件路径或在所有本地硬盘上搜索常规类型的文件时，可以使用该窗口查找文档。</span><span class="sxs-lookup"><span data-stu-id="36f8c-159">The **Search** tool opens a **File Search** window that you can use to find documents when you do not know the file path or to search for general kinds of files across all local hard disks.</span></span> <span data-ttu-id="36f8c-160">你可以在特定路径中搜索特定的文件名模式。</span><span class="sxs-lookup"><span data-stu-id="36f8c-160">You can search for specific file-name patterns in specific paths.</span></span> <span data-ttu-id="36f8c-161">您还可以将结果限制为日期范围或大小范围。</span><span class="sxs-lookup"><span data-stu-id="36f8c-161">You can also limit results to a date range or size range.</span></span>

### <span data-ttu-id="36f8c-162">修补程序卸载</span><span class="sxs-lookup"><span data-stu-id="36f8c-162">Hotfix Uninstall</span></span>

<span data-ttu-id="36f8c-163">**修复程序卸载向导**允许您从正在修复的计算机上的 Windows 操作系统中删除修补程序或服务包。</span><span class="sxs-lookup"><span data-stu-id="36f8c-163">The **Hotfix Uninstall Wizard** lets you remove hotfixes or service packs from the Windows operating system on the computer that you are repairing.</span></span> <span data-ttu-id="36f8c-164">当怀疑修补程序或 service pack 阻止操作系统启动时，请使用此工具。</span><span class="sxs-lookup"><span data-stu-id="36f8c-164">Use this tool when a hotfix or service pack is suspected in preventing the operating system from starting.</span></span>

<span data-ttu-id="36f8c-165">我们建议你一次仅卸载一个修补程序，即使该工具允许你卸载多个修补程序。</span><span class="sxs-lookup"><span data-stu-id="36f8c-165">We recommend that you uninstall only one hotfix at a time, even though the tool lets you uninstall more than one.</span></span>

<span data-ttu-id="36f8c-166">**重要提示** 卸载修补程序后安装或更新的程序可能无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="36f8c-166">**Important** Programs that were installed or updated after a hotfix was installed might not work correctly after you uninstall a hotfix.</span></span>

 

### <span data-ttu-id="36f8c-167">Locksmith</span><span class="sxs-lookup"><span data-stu-id="36f8c-167">Locksmith</span></span>

<span data-ttu-id="36f8c-168">在**Locksmith 向导**中，你可以设置或更改你正在分析或修复的 Windows 操作系统上的任何本地帐户的密码。</span><span class="sxs-lookup"><span data-stu-id="36f8c-168">The **Locksmith Wizard** lets you set or change the password for any local account on the Windows operating system that you are analyzing or repairing.</span></span> <span data-ttu-id="36f8c-169">您无需知道当前密码。</span><span class="sxs-lookup"><span data-stu-id="36f8c-169">You do not have to know the current password.</span></span> <span data-ttu-id="36f8c-170">但是，你设置的密码必须符合由本地组策略对象定义的任何要求。</span><span class="sxs-lookup"><span data-stu-id="36f8c-170">However, the password that you set must comply with any requirements that are defined by a local Group Policy Object.</span></span> <span data-ttu-id="36f8c-171">这包括密码长度和复杂性。</span><span class="sxs-lookup"><span data-stu-id="36f8c-171">This includes password length and complexity.</span></span>

<span data-ttu-id="36f8c-172">当本地帐户（如本地管理员帐户）的密码未知时，可以使用**Locksmith** 。</span><span class="sxs-lookup"><span data-stu-id="36f8c-172">You can use **Locksmith** when the password for a local account, such as the local Administrator account, is unknown.</span></span> <span data-ttu-id="36f8c-173">不能使用**Locksmith**设置域帐户的密码。</span><span class="sxs-lookup"><span data-stu-id="36f8c-173">You cannot use **Locksmith** to set passwords for domain accounts.</span></span>

### <span data-ttu-id="36f8c-174">注册表编辑器</span><span class="sxs-lookup"><span data-stu-id="36f8c-174">Registry Editor</span></span>

<span data-ttu-id="36f8c-175">可以使用**注册表编辑器**访问和更改正在分析或修复的 Windows 操作系统的注册表。</span><span class="sxs-lookup"><span data-stu-id="36f8c-175">You can use **Registry Editor** to access and change the registry of the Windows operating system that you are analyzing or repairing.</span></span> <span data-ttu-id="36f8c-176">这包括添加、删除和编辑注册表项和值，以及导入注册表（.reg）文件。</span><span class="sxs-lookup"><span data-stu-id="36f8c-176">This includes adding, removing, and editing keys and values, and importing registry (.reg) files.</span></span>

<span data-ttu-id="36f8c-177">**警告** 如果使用**注册表编辑器**错误地更改注册表，可能会出现严重问题。</span><span class="sxs-lookup"><span data-stu-id="36f8c-177">**Warning** Serious problems can occur if you change the registry incorrectly by using **Registry Editor**.</span></span> <span data-ttu-id="36f8c-178">可能需要重新安装操作系统才能解决这些问题。</span><span class="sxs-lookup"><span data-stu-id="36f8c-178">These problems might require you to reinstall the operating system.</span></span> <span data-ttu-id="36f8c-179">在对注册表进行更改之前，应备份计算机上的任何重要数据。</span><span class="sxs-lookup"><span data-stu-id="36f8c-179">Before you make changes to the registry, you should back up any valued data on the computer.</span></span> <span data-ttu-id="36f8c-180">更改注册表的风险由您自己承担。</span><span class="sxs-lookup"><span data-stu-id="36f8c-180">Change the registry at your own risk.</span></span>

 

### <span data-ttu-id="36f8c-181">SFC 扫描</span><span class="sxs-lookup"><span data-stu-id="36f8c-181">SFC Scan</span></span>

<span data-ttu-id="36f8c-182">**SFC 扫描**工具将启动**系统文件修复向导**，并允许你修复阻止已安装的 Windows 操作系统启动的系统文件。</span><span class="sxs-lookup"><span data-stu-id="36f8c-182">The **SFC Scan** tool starts the **System File Repair Wizard** and lets you repair system files that are preventing the installed Windows operating system from starting.</span></span> <span data-ttu-id="36f8c-183">"**系统文件修复" 向导**可以自动修复损坏或丢失的系统文件，也可以在执行任何修复之前提示您。</span><span class="sxs-lookup"><span data-stu-id="36f8c-183">The **System File Repair Wizard** can automatically repair system files that are corrupted or missing, or it can prompt you before it performs any repairs.</span></span>

### <span data-ttu-id="36f8c-184">解决方案向导</span><span class="sxs-lookup"><span data-stu-id="36f8c-184">Solution Wizard</span></span>

<span data-ttu-id="36f8c-185">**解决方案向导**将提供一系列问题，然后根据你的回答建议适用情况的最佳工具。</span><span class="sxs-lookup"><span data-stu-id="36f8c-185">The **Solution Wizard** presents a series of questions and then recommends the best tool for the situation, based on your answers.</span></span> <span data-ttu-id="36f8c-186">此向导可帮助你确定在不熟悉 DaRT 中的工具时要使用的工具。</span><span class="sxs-lookup"><span data-stu-id="36f8c-186">This wizard helps you determine which tool to use when you are not familiar with the tools in DaRT.</span></span>

### <span data-ttu-id="36f8c-187">TCP/IP 配置</span><span class="sxs-lookup"><span data-stu-id="36f8c-187">TCP/IP Config</span></span>

<span data-ttu-id="36f8c-188">当您将有问题的计算机启动到 DaRT 时，它将设置为从动态主机配置协议（DHCP）自动获取其 TCP/IP 配置（IP 地址和 DNS 服务器）。</span><span class="sxs-lookup"><span data-stu-id="36f8c-188">When you boot a problem computer into DaRT, it is set to automatically obtain its TCP/IP configuration (IP address and DNS server) from Dynamic Host Configuration Protocol (DHCP).</span></span> <span data-ttu-id="36f8c-189">如果 DHCP 不可用，则可以使用**Tcp/ip 配置**工具手动配置 tcp/ip。</span><span class="sxs-lookup"><span data-stu-id="36f8c-189">If DHCP is unavailable, you can manually configure TCP/IP by using the **TCP/IP Config** tool.</span></span> <span data-ttu-id="36f8c-190">首先选择一个网络适配器，然后为该适配器配置 IP 地址和 DNS 服务器。</span><span class="sxs-lookup"><span data-stu-id="36f8c-190">You first select a network adapter, and then configure the IP address and DNS server for that adapter.</span></span>

## <span data-ttu-id="36f8c-191">相关主题</span><span class="sxs-lookup"><span data-stu-id="36f8c-191">Related topics</span></span>


[<span data-ttu-id="36f8c-192">DaRT 8.0 入门</span><span class="sxs-lookup"><span data-stu-id="36f8c-192">Getting Started with DaRT 8.0</span></span>](getting-started-with-dart-80-dart-8.md)

 

 





