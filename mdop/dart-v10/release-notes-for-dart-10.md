---
title: DaRT 10 发行说明
description: DaRT 10 发行说明
author: dansimp
ms.assetid: eb996980-f9c4-42cb-bde9-6b3d4b82b58c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 12ae5865538155f3c9ecf8b5f23b0d9e23232833
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803271"
---
# <span data-ttu-id="1f211-103">DaRT 10 发行说明</span><span class="sxs-lookup"><span data-stu-id="1f211-103">Release Notes for DaRT 10</span></span>


**<span data-ttu-id="1f211-104">若要搜索这些发行说明，请按 CTRL + F。</span><span class="sxs-lookup"><span data-stu-id="1f211-104">To search these release notes, press CTRL+F.</span></span>**

<span data-ttu-id="1f211-105">在安装 Microsoft 诊断和恢复工具集（DaRT）10之前，请仔细阅读这些发行说明。</span><span class="sxs-lookup"><span data-stu-id="1f211-105">Read these release notes thoroughly before you install Microsoft Diagnostics and Recovery Toolset (DaRT) 10.</span></span>

<span data-ttu-id="1f211-106">这些发行说明包含成功安装诊断和恢复工具集10所需的信息。</span><span class="sxs-lookup"><span data-stu-id="1f211-106">These release notes contain information that is required to successfully install Diagnostics and Recovery Toolset 10.</span></span> <span data-ttu-id="1f211-107">发行说明还包含产品文档中不可用的信息。</span><span class="sxs-lookup"><span data-stu-id="1f211-107">The release notes also contain information that is not available in the product documentation.</span></span> <span data-ttu-id="1f211-108">如果这些发行说明和其他 DaRT 文档之间存在差异，则应将最新更改视为权威。</span><span class="sxs-lookup"><span data-stu-id="1f211-108">If there is a difference between these release notes and other DaRT documentation, the latest change should be considered authoritative.</span></span> <span data-ttu-id="1f211-109">这些发行说明取代了本产品附带的内容。</span><span class="sxs-lookup"><span data-stu-id="1f211-109">These release notes supersede the content that is included with this product.</span></span>

## <span data-ttu-id="1f211-110">DaRT 10 的已知问题</span><span class="sxs-lookup"><span data-stu-id="1f211-110">Known issues with DaRT 10</span></span>


### <span data-ttu-id="1f211-111">Disk 指挥无法在 Windows 10 的物理分区中修复损坏的主启动记录</span><span class="sxs-lookup"><span data-stu-id="1f211-111">Disk Commander is unable to repair a corrupt master boot record in a physical partition in Windows 10</span></span>

<span data-ttu-id="1f211-112">在 Windows 10 中，"还原主启动记录（MBR）或磁盘中 GUID 分区表（GPT）的头" 选项无法修复物理分区中损坏的主启动记录，因此无法启动客户端计算机。</span><span class="sxs-lookup"><span data-stu-id="1f211-112">In Windows 10, the “Restore the Master Boot Record (MBR) or the header of the GUID Partition Table (GPT)” option in Disk Commander is unable to repair a corrupt master boot record in a physical partition, and therefore is unable to boot the client computer.</span></span>

<span data-ttu-id="1f211-113">**解决方法：** 启动 "**启动修复**"，单击 "**疑难解答**"，单击 "**高级选项**"，然后单击 "**开始修复**"。</span><span class="sxs-lookup"><span data-stu-id="1f211-113">**Workaround:** Start **Startup Repair**, click **Troubleshoot**, click **Advanced options**, and then click **Start repair**.</span></span>

### <span data-ttu-id="1f211-114">针对同一个驱动器的多个磁盘擦除实例会导致除最后一个实例之外的所有实例报告故障</span><span class="sxs-lookup"><span data-stu-id="1f211-114">Multiple instances of Disk Wipe that target the same drive cause all instances except the last one to report a failure</span></span>

<span data-ttu-id="1f211-115">如果你启动磁盘擦除的多个实例，然后尝试使用两个单独的磁盘擦除实例来擦除相同的驱动器，则除最后一个磁盘之外的所有实例都将报告无法擦除驱动器。</span><span class="sxs-lookup"><span data-stu-id="1f211-115">If you start multiple instances of Disk Wipe, and then try to wipe the same drive by using two separate Disk Wipe instances, all instances except the last one report a failure to wipe the drive.</span></span>

<span data-ttu-id="1f211-116">**解决方法：** 尚.</span><span class="sxs-lookup"><span data-stu-id="1f211-116">**Workaround:** None.</span></span>

### <span data-ttu-id="1f211-117">磁盘擦除可能无法清除具有闪存的固态驱动器上的所有数据</span><span class="sxs-lookup"><span data-stu-id="1f211-117">Disk Wipe may not clear all data on solid-state drives that have flash memory</span></span>

<span data-ttu-id="1f211-118">如果使用 "磁盘擦除" 清除具有闪存的固态驱动器（SSD）上的数据，则所有数据都可能不会被清除。</span><span class="sxs-lookup"><span data-stu-id="1f211-118">If you use Disk Wipe to clear data on a solid-state drive (SSD) that has flash memory, all of the data may not be erased.</span></span> <span data-ttu-id="1f211-119">出现此问题的原因是 SSD 固件在执行磁盘擦除时控制写入的物理位置。</span><span class="sxs-lookup"><span data-stu-id="1f211-119">This issue occurs because the SSD firmware controls the physical location of writes while Disk Wipe is running.</span></span>

<span data-ttu-id="1f211-120">**解决方法：** 尚.</span><span class="sxs-lookup"><span data-stu-id="1f211-120">**Workaround:** None.</span></span>

### <span data-ttu-id="1f211-121">运行 Locksmith 向导或注册表编辑器时系统还原失败</span><span class="sxs-lookup"><span data-stu-id="1f211-121">System restore fails when you run Locksmith Wizard or Registry Editor</span></span>

<span data-ttu-id="1f211-122">如果您运行的是 Locksmith 向导、注册表编辑器和可能的其他工具，系统还原将失败。</span><span class="sxs-lookup"><span data-stu-id="1f211-122">If you run Locksmith Wizard, Registry Editor, and possibly other tools, System Restore fails.</span></span>

<span data-ttu-id="1f211-123">**解决方法：** 关闭并重新启动 DaRT，然后启动 "系统还原"。</span><span class="sxs-lookup"><span data-stu-id="1f211-123">**Workaround:** Close and restart DaRT, and then start System Restore.</span></span>

### <span data-ttu-id="1f211-124">启动和关闭 Locksmith 向导或计算机管理后，系统文件检查器（SFC）扫描无法运行</span><span class="sxs-lookup"><span data-stu-id="1f211-124">System File Checker (SFC) Scan fails to run after you start and close Locksmith Wizard or Computer Management</span></span>

<span data-ttu-id="1f211-125">如果在 "计算机管理" 中启动然后关闭 Locksmith 向导或工具，系统文件检查器将无法运行。</span><span class="sxs-lookup"><span data-stu-id="1f211-125">If you start and then close Locksmith Wizard or tools in Computer Management, System File Checker fails to run.</span></span>

<span data-ttu-id="1f211-126">**解决方法：** 关闭并重新启动 DaRT，然后启动系统文件检查器。</span><span class="sxs-lookup"><span data-stu-id="1f211-126">**Workaround:** Close and restart DaRT, and then start System File Checker.</span></span>

### <a href="" id="-------------dart-installer-does-not-fail-when-the-windows-assessment-and-deployment-kit-is-not-installed"></a> <span data-ttu-id="1f211-127">当未安装 Windows 评估和部署工具包时，DaRT 安装程序不会失败</span><span class="sxs-lookup"><span data-stu-id="1f211-127">DaRT installer does not fail when the Windows Assessment and Deployment Kit is not installed</span></span>

<span data-ttu-id="1f211-128">如果你通过使用命令行运行 Windows Installer （.msi），并且尚未安装 Windows 评估和部署工具包（WindowsADK）来安装 DaRT 10，则 DaRT 安装应该会失败。</span><span class="sxs-lookup"><span data-stu-id="1f211-128">If you install DaRT 10 by using the command line to run the Windows Installer (.msi), and the Windows Assessment and Deployment Kit (WindowsADK) has not been installed, the DaRT installation should fail.</span></span> <span data-ttu-id="1f211-129">目前，DaRT 10 安装程序安装了除 DaRT 恢复映像之外的所有组件。</span><span class="sxs-lookup"><span data-stu-id="1f211-129">Currently, the DaRT 10 installer installs all components except the DaRT recovery image.</span></span>

<span data-ttu-id="1f211-130">**解决方法：** 尚.</span><span class="sxs-lookup"><span data-stu-id="1f211-130">**Workaround:** None.</span></span>

## <span data-ttu-id="1f211-131">相关主题</span><span class="sxs-lookup"><span data-stu-id="1f211-131">Related topics</span></span>


[<span data-ttu-id="1f211-132">关于 DaRT 10</span><span class="sxs-lookup"><span data-stu-id="1f211-132">About DaRT 10</span></span>](about-dart-10.md)

 

 





