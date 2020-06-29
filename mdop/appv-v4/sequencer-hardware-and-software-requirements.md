---
title: Sequencer 硬件和软件要求
description: Sequencer 硬件和软件要求
author: dansimp
ms.assetid: 36084e12-831d-452f-a4a4-45f07f9ce471
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0d4e12a5803a3c9033513424826b49bc0bca5885
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798790"
---
# <span data-ttu-id="362a5-103">Sequencer 硬件和软件要求</span><span class="sxs-lookup"><span data-stu-id="362a5-103">Sequencer Hardware and Software Requirements</span></span>


<span data-ttu-id="362a5-104">本主题介绍运行 Microsoft Application Virtualization （app-v） Sequencer 的计算机的最低建议硬件和软件要求。</span><span class="sxs-lookup"><span data-stu-id="362a5-104">This topic describes the minimum recommended hardware and software requirements for the computer running the Microsoft Application Virtualization (App-V) Sequencer.</span></span>

<span data-ttu-id="362a5-105">在安装 Sequencer 之前以及对每个应用程序进行排序后，必须将干净的操作系统映像还原到顺序计算机。</span><span class="sxs-lookup"><span data-stu-id="362a5-105">Before you install the Sequencer and after you sequence each application, you must restore a clean operating system image to the sequencing computer.</span></span> <span data-ttu-id="362a5-106">你可以使用以下方法之一来还原运行 Sequencer 的计算机：</span><span class="sxs-lookup"><span data-stu-id="362a5-106">You can use one of the following methods to restore the computer running the Sequencer:</span></span>

-   <span data-ttu-id="362a5-107">重新格式化硬盘并重新安装操作系统。</span><span class="sxs-lookup"><span data-stu-id="362a5-107">Reformat the hard drive and reinstall the operating system.</span></span>

-   <span data-ttu-id="362a5-108">使用另一个磁盘映像软件还原运行 Sequencer 映像的计算机上的硬盘。</span><span class="sxs-lookup"><span data-stu-id="362a5-108">Restore the hard drive on the computer running the Sequencer image by using another disk-imaging software.</span></span>

<span data-ttu-id="362a5-109">下表列出了运行 App-v 排序器的推荐硬件要求。</span><span class="sxs-lookup"><span data-stu-id="362a5-109">The following list outlines the recommended hardware requirements for running the App-V Sequencer.</span></span>

### <a href="" id="hardware-requirements-"></a><span data-ttu-id="362a5-110">硬件要求</span><span class="sxs-lookup"><span data-stu-id="362a5-110">Hardware Requirements</span></span>

-   <span data-ttu-id="362a5-111">处理器-英特尔奔腾 III、1 GHz （32位或64位）。</span><span class="sxs-lookup"><span data-stu-id="362a5-111">Processor—Intel Pentium III, 1 GHz (32-bit or 64-bit).</span></span> <span data-ttu-id="362a5-112">排序过程是一个单线程进程，不会利用双处理器。</span><span class="sxs-lookup"><span data-stu-id="362a5-112">The sequencing process is a single-threaded process and does not take advantage of dual processors.</span></span>

-   <span data-ttu-id="362a5-113">内存-1GB 或更高版本，建议使用 2 GB。</span><span class="sxs-lookup"><span data-stu-id="362a5-113">Memory—1GB or above, 2 GB recommended.</span></span>

-   <span data-ttu-id="362a5-114">硬盘-40 千兆字节（GB）硬盘空间，至少有 15 GB 的可用硬盘空间。</span><span class="sxs-lookup"><span data-stu-id="362a5-114">Hard Disk—40 gigabyte (GB) hard disk space with a minimum of 15 GB available hard disk space.</span></span> <span data-ttu-id="362a5-115">我们建议您至少拥有所需的应用程序所需的磁盘空间的三倍。</span><span class="sxs-lookup"><span data-stu-id="362a5-115">We recommend that you have at least three times the hard disk space that the application you are sequencing requires.</span></span>

    <span data-ttu-id="362a5-116">**注意** 排序需要大量的磁盘使用。</span><span class="sxs-lookup"><span data-stu-id="362a5-116">**Note** Sequencing requires heavy disk usage.</span></span> <span data-ttu-id="362a5-117">快速磁盘速度会减少排序时间。</span><span class="sxs-lookup"><span data-stu-id="362a5-117">A fast disk speed can decrease the sequencing time.</span></span>

     

### <span data-ttu-id="362a5-118">软件要求</span><span class="sxs-lookup"><span data-stu-id="362a5-118">Software Requirements</span></span>

<span data-ttu-id="362a5-119">下表列出了运行 Sequencer 所支持的操作系统。</span><span class="sxs-lookup"><span data-stu-id="362a5-119">The following list outlines the supported operating systems for running the Sequencer.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="362a5-120">操作系统</span><span class="sxs-lookup"><span data-stu-id="362a5-120">Operating System</span></span></th>
<th align="left"><span data-ttu-id="362a5-121">版本</span><span class="sxs-lookup"><span data-stu-id="362a5-121">Edition</span></span></th>
<th align="left"><span data-ttu-id="362a5-122">Service Pack</span><span class="sxs-lookup"><span data-stu-id="362a5-122">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="362a5-123">系统体系结构</span><span class="sxs-lookup"><span data-stu-id="362a5-123">System Architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="362a5-124">WindowsXP</span><span class="sxs-lookup"><span data-stu-id="362a5-124">WindowsXP</span></span></p></td>
<td align="left"><p><span data-ttu-id="362a5-125">专业版</span><span class="sxs-lookup"><span data-stu-id="362a5-125">Professional</span></span></p></td>
<td align="left"><p><span data-ttu-id="362a5-126">SP2 或 SP3</span><span class="sxs-lookup"><span data-stu-id="362a5-126">SP2 or SP3</span></span></p></td>
<td align="left"><p><span data-ttu-id="362a5-127">x86</span><span class="sxs-lookup"><span data-stu-id="362a5-127">x86</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="362a5-128">Windows Vista</span><span class="sxs-lookup"><span data-stu-id="362a5-128">Windows Vista</span></span></p></td>
<td align="left"><p><span data-ttu-id="362a5-129">企业版、企业版或旗舰版</span><span class="sxs-lookup"><span data-stu-id="362a5-129">Business, Enterprise, or Ultimate</span></span></p></td>
<td align="left"><p><span data-ttu-id="362a5-130">无服务包、SP1 或 SP2</span><span class="sxs-lookup"><span data-stu-id="362a5-130">No service pack, SP1, or SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="362a5-131">x86</span><span class="sxs-lookup"><span data-stu-id="362a5-131">x86</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="362a5-132">Windows7 ¹</span><span class="sxs-lookup"><span data-stu-id="362a5-132">Windows7¹</span></span></p></td>
<td align="left"><p><span data-ttu-id="362a5-133">专业版、企业版或旗舰版</span><span class="sxs-lookup"><span data-stu-id="362a5-133">Professional, Enterprise, or Ultimate</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="362a5-134">x86</span><span class="sxs-lookup"><span data-stu-id="362a5-134">x86</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="362a5-135">¹支持仅限 SP1 或 SP2 的 app-v 4.5 和 app-v 4。6</span><span class="sxs-lookup"><span data-stu-id="362a5-135">¹Supported for App-V 4.5 with SP1 or SP2, and App-V 4.6 only</span></span>

<span data-ttu-id="362a5-136">**注意** 应用程序虚拟化（app-v） 4.6 Sequencer 支持这些操作系统的32位和64位版本。</span><span class="sxs-lookup"><span data-stu-id="362a5-136">**Note** The Application Virtualization (App-V) 4.6 Sequencer supports 32-bit and 64-bit versions of these operating systems.</span></span>

 

<span data-ttu-id="362a5-137">你应该将运行 Sequencer 的计算机配置为在目标计算机上安装的相同应用程序。</span><span class="sxs-lookup"><span data-stu-id="362a5-137">You should configure computers running the Sequencer with the same applications that are installed on target computers.</span></span>

### <span data-ttu-id="362a5-138">远程桌面服务的软件要求</span><span class="sxs-lookup"><span data-stu-id="362a5-138">Software Requirements for Remote Desktop Services</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="362a5-139">操作系统</span><span class="sxs-lookup"><span data-stu-id="362a5-139">Operating System</span></span></th>
<th align="left"><span data-ttu-id="362a5-140">版本</span><span class="sxs-lookup"><span data-stu-id="362a5-140">Edition</span></span></th>
<th align="left"><span data-ttu-id="362a5-141">Service Pack</span><span class="sxs-lookup"><span data-stu-id="362a5-141">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="362a5-142">系统体系结构</span><span class="sxs-lookup"><span data-stu-id="362a5-142">System Architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="362a5-143">Windows Server2003</span><span class="sxs-lookup"><span data-stu-id="362a5-143">Windows Server2003</span></span></p></td>
<td align="left"><p><span data-ttu-id="362a5-144">标准版、企业版或数据中心版</span><span class="sxs-lookup"><span data-stu-id="362a5-144">Standard Edition, Enterprise Edition, or Datacenter Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="362a5-145">SP1 或 SP2</span><span class="sxs-lookup"><span data-stu-id="362a5-145">SP1 or SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="362a5-146">x86</span><span class="sxs-lookup"><span data-stu-id="362a5-146">x86</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="362a5-147">Windows Server2003 R2</span><span class="sxs-lookup"><span data-stu-id="362a5-147">Windows Server2003 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="362a5-148">标准版、企业版或数据中心版</span><span class="sxs-lookup"><span data-stu-id="362a5-148">Standard Edition, Enterprise Edition, or Datacenter Edition</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="362a5-149">x86</span><span class="sxs-lookup"><span data-stu-id="362a5-149">x86</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="362a5-150">Windows Server2008</span><span class="sxs-lookup"><span data-stu-id="362a5-150">Windows Server2008</span></span></p></td>
<td align="left"><p><span data-ttu-id="362a5-151">标准版、企业版或数据中心</span><span class="sxs-lookup"><span data-stu-id="362a5-151">Standard, Enterprise, or Datacenter</span></span></p></td>
<td align="left"><p><span data-ttu-id="362a5-152">SP1 或 SP2</span><span class="sxs-lookup"><span data-stu-id="362a5-152">SP1 or SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="362a5-153">x86</span><span class="sxs-lookup"><span data-stu-id="362a5-153">x86</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="362a5-154">**注意** 适用于远程桌面服务的应用程序虚拟化（app-v）4.6 支持这些操作系统的32位和64位版本。</span><span class="sxs-lookup"><span data-stu-id="362a5-154">**Note** Application Virtualization (App-V) 4.6 for Remote Desktop Services supports 32-bit and 64-bit versions of these operating systems.</span></span>

 

## <span data-ttu-id="362a5-155">相关主题</span><span class="sxs-lookup"><span data-stu-id="362a5-155">Related topics</span></span>


[<span data-ttu-id="362a5-156">Application Virtualization Sequencer 概述</span><span class="sxs-lookup"><span data-stu-id="362a5-156">Application Virtualization Sequencer Overview</span></span>](application-virtualization-sequencer-overview.md)

 

 





