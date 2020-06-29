---
title: Application Virtualization Sequencer 硬件和软件要求
description: Application Virtualization Sequencer 硬件和软件要求
author: dansimp
ms.assetid: c88a1b5b-23e1-4460-afa9-a5f37e32eb05
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d68afe4d4a3f6f301d38f2e86139d94319583467
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802291"
---
# <span data-ttu-id="93084-103">Application Virtualization Sequencer 硬件和软件要求</span><span class="sxs-lookup"><span data-stu-id="93084-103">Application Virtualization Sequencer Hardware and Software Requirements</span></span>


<span data-ttu-id="93084-104">本主题介绍运行 Microsoft Application Virtualization （app-v） Sequencer 的计算机的最低建议硬件和软件要求。</span><span class="sxs-lookup"><span data-stu-id="93084-104">This topic describes the minimum recommended hardware and software requirements for the computer running the Microsoft Application Virtualization (App-V) Sequencer.</span></span>

<span data-ttu-id="93084-105">**重要提示** 你必须使用具有管理员权限的帐户运行 app-v sequencer （**SFTSequencer.exe**），因为 sequencer 对本地系统所做的更改。</span><span class="sxs-lookup"><span data-stu-id="93084-105">**Important** You must run the App-V sequencer (**SFTSequencer.exe**) using an account that has administrator privileges because of the changes the sequencer makes to the local system.</span></span> <span data-ttu-id="93084-106">这些更改可以包括将文件写入**C:\\program files files**目录、进行注册表更改、启动和停止服务、更新文件的安全描述符以及更改权限。</span><span class="sxs-lookup"><span data-stu-id="93084-106">These changes can include writing files to the **C:\\Program Files** directory, making registry changes, starting and stopping services, updating security descriptors for files, and changing permissions.</span></span>

 

<span data-ttu-id="93084-107">在安装 Sequencer 之前以及对每个应用程序进行排序后，必须将干净的操作系统映像还原到顺序计算机。</span><span class="sxs-lookup"><span data-stu-id="93084-107">Before you install the Sequencer and after you sequence each application, you must restore a clean operating system image to the sequencing computer.</span></span> <span data-ttu-id="93084-108">你可以使用以下方法之一来还原运行 Sequencer 的计算机：</span><span class="sxs-lookup"><span data-stu-id="93084-108">You can use one of the following methods to restore the computer running the Sequencer:</span></span>

-   <span data-ttu-id="93084-109">重新格式化硬盘并重新安装操作系统。</span><span class="sxs-lookup"><span data-stu-id="93084-109">Reformat the hard drive and reinstall the operating system.</span></span>

-   <span data-ttu-id="93084-110">使用另一个磁盘映像软件还原运行 Sequencer 映像的计算机上的硬盘。</span><span class="sxs-lookup"><span data-stu-id="93084-110">Restore the hard drive on the computer running the Sequencer image by using another disk-imaging software.</span></span>

-   <span data-ttu-id="93084-111">还原虚拟操作系统映像，例如 Microsoft 虚拟 PC 映像。</span><span class="sxs-lookup"><span data-stu-id="93084-111">Revert a virtual operating system image such as a Microsoft Virtual PC image.</span></span> <span data-ttu-id="93084-112">使用虚拟机可轻松地以最少的管理方式重用干净的顺序环境。</span><span class="sxs-lookup"><span data-stu-id="93084-112">Using a virtual machine allows for clean sequencing environments to be easily reused with minimal administration.</span></span>

<span data-ttu-id="93084-113">下表列出了运行 App-v 排序器的推荐硬件要求。</span><span class="sxs-lookup"><span data-stu-id="93084-113">The following list outlines the recommended hardware requirements for running the App-V Sequencer.</span></span>

<span data-ttu-id="93084-114">首先列出了 Microsoft Application Virtualization （app-v） 4.6 SP2 的要求，后跟前面的 App-v 4.6 SP2 版本的要求。</span><span class="sxs-lookup"><span data-stu-id="93084-114">The requirements are listed first for Microsoft Application Virtualization (App-V)4.6 SP2, followed by the requirements for versions that preceded App-V4.6SP2.</span></span>

### <a href="" id="hardware-requirements-"></a><span data-ttu-id="93084-115">硬件要求</span><span class="sxs-lookup"><span data-stu-id="93084-115">Hardware Requirements</span></span>

-   <span data-ttu-id="93084-116">处理器-英特尔奔腾 III、1 GHz （32位或64位）。</span><span class="sxs-lookup"><span data-stu-id="93084-116">Processor—Intel Pentium III, 1 GHz (32-bit or 64-bit).</span></span> <span data-ttu-id="93084-117">排序过程是一个单线程进程，不会利用双处理器。</span><span class="sxs-lookup"><span data-stu-id="93084-117">The sequencing process is a single-threaded process and does not take advantage of dual processors.</span></span>

-   <span data-ttu-id="93084-118">内存-1GB 或更高，建议使用2GB。</span><span class="sxs-lookup"><span data-stu-id="93084-118">Memory—1GB or above, 2GB recommended.</span></span>

-   <span data-ttu-id="93084-119">硬盘-40 千兆字节（GB）硬盘空间，至少有 15 GB 的可用硬盘空间。</span><span class="sxs-lookup"><span data-stu-id="93084-119">Hard disk—40 gigabyte (GB) hard disk space with a minimum of 15 GB available hard disk space.</span></span> <span data-ttu-id="93084-120">我们建议您至少拥有所需的应用程序所需的磁盘空间的三倍。</span><span class="sxs-lookup"><span data-stu-id="93084-120">We recommend that you have at least three times the hard disk space that the application you are sequencing requires.</span></span>

    <span data-ttu-id="93084-121">**注意** 排序需要大量的磁盘使用。</span><span class="sxs-lookup"><span data-stu-id="93084-121">**Note** Sequencing requires heavy disk usage.</span></span> <span data-ttu-id="93084-122">快速磁盘速度会减少排序时间。</span><span class="sxs-lookup"><span data-stu-id="93084-122">A fast disk speed can decrease the sequencing time.</span></span>

     

### <span data-ttu-id="93084-123">App-v 4.6 SP2 的软件要求</span><span class="sxs-lookup"><span data-stu-id="93084-123">Software Requirements for App-V 4.6 SP2</span></span>

<span data-ttu-id="93084-124">下表列出了运行 app-v 4.6 SP2 Sequencer 的受支持的操作系统。</span><span class="sxs-lookup"><span data-stu-id="93084-124">The following list outlines the supported operating systems for running the App-V 4.6 SP2 Sequencer.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="93084-125">操作系统</span><span class="sxs-lookup"><span data-stu-id="93084-125">Operating System</span></span></th>
<th align="left"><span data-ttu-id="93084-126">版本</span><span class="sxs-lookup"><span data-stu-id="93084-126">Edition</span></span></th>
<th align="left"><span data-ttu-id="93084-127">Service Pack</span><span class="sxs-lookup"><span data-stu-id="93084-127">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="93084-128">系统体系结构</span><span class="sxs-lookup"><span data-stu-id="93084-128">System Architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="93084-129">WindowsXP</span><span class="sxs-lookup"><span data-stu-id="93084-129">WindowsXP</span></span></p></td>
<td align="left"><p><span data-ttu-id="93084-130">专业版</span><span class="sxs-lookup"><span data-stu-id="93084-130">Professional</span></span></p></td>
<td align="left"><p><span data-ttu-id="93084-131">又</span><span class="sxs-lookup"><span data-stu-id="93084-131">SP3</span></span></p></td>
<td align="left"><p><span data-ttu-id="93084-132">x86</span><span class="sxs-lookup"><span data-stu-id="93084-132">x86</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="93084-133">Windows Vista</span><span class="sxs-lookup"><span data-stu-id="93084-133">Windows Vista</span></span></p></td>
<td align="left"><p><span data-ttu-id="93084-134">企业版、企业版或旗舰版</span><span class="sxs-lookup"><span data-stu-id="93084-134">Business, Enterprise, or Ultimate</span></span></p></td>
<td align="left"><p><span data-ttu-id="93084-135">SP2</span><span class="sxs-lookup"><span data-stu-id="93084-135">SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="93084-136">x86</span><span class="sxs-lookup"><span data-stu-id="93084-136">x86</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="93084-137">Windows7</span><span class="sxs-lookup"><span data-stu-id="93084-137">Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="93084-138">专业版、企业版或旗舰版</span><span class="sxs-lookup"><span data-stu-id="93084-138">Professional, Enterprise, or Ultimate</span></span></p></td>
<td align="left"><p><span data-ttu-id="93084-139">无服务包或 SP1</span><span class="sxs-lookup"><span data-stu-id="93084-139">No service pack or SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="93084-140">x86 和 x64</span><span class="sxs-lookup"><span data-stu-id="93084-140">x86 and x64</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="93084-141">Windows 8</span><span class="sxs-lookup"><span data-stu-id="93084-141">Windows 8</span></span></p></td>
<td align="left"><p><span data-ttu-id="93084-142">专业版或企业版</span><span class="sxs-lookup"><span data-stu-id="93084-142">Pro or Enterprise Edition</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="93084-143">x86 和 x64</span><span class="sxs-lookup"><span data-stu-id="93084-143">x86 and x64</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="93084-144">**注意** 应用程序虚拟化（app-v） 4.6 SP2 Sequencer 支持这些操作系统的32位和64位版本。</span><span class="sxs-lookup"><span data-stu-id="93084-144">**Note** The Application Virtualization (App-V) 4.6 SP2 Sequencer supports 32-bit and 64-bit versions of these operating systems.</span></span>

 

<span data-ttu-id="93084-145">你应该将运行 Sequencer 的计算机配置为在目标计算机上安装的相同应用程序。</span><span class="sxs-lookup"><span data-stu-id="93084-145">You should configure computers running the Sequencer with the same applications that are installed on targeted computers.</span></span>

### <span data-ttu-id="93084-146">在 App-v 4.6 SP2 之前的版本的软件要求</span><span class="sxs-lookup"><span data-stu-id="93084-146">Software Requirements for Versions that Precede App-V 4.6 SP2</span></span>

<span data-ttu-id="93084-147">下表概述了针对应用 V 4.6 SP2 之前的版本运行 Sequencer 的受支持操作系统。</span><span class="sxs-lookup"><span data-stu-id="93084-147">The following list outlines the supported operating systems for running the Sequencer for versions that precede App-V 4.6 SP2.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="93084-148">操作系统</span><span class="sxs-lookup"><span data-stu-id="93084-148">Operating System</span></span></th>
<th align="left"><span data-ttu-id="93084-149">版本</span><span class="sxs-lookup"><span data-stu-id="93084-149">Edition</span></span></th>
<th align="left"><span data-ttu-id="93084-150">Service Pack</span><span class="sxs-lookup"><span data-stu-id="93084-150">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="93084-151">系统体系结构</span><span class="sxs-lookup"><span data-stu-id="93084-151">System Architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="93084-152">WindowsXP</span><span class="sxs-lookup"><span data-stu-id="93084-152">WindowsXP</span></span></p></td>
<td align="left"><p><span data-ttu-id="93084-153">专业版</span><span class="sxs-lookup"><span data-stu-id="93084-153">Professional</span></span></p></td>
<td align="left"><p><span data-ttu-id="93084-154">SP2 或 SP3</span><span class="sxs-lookup"><span data-stu-id="93084-154">SP2 or SP3</span></span></p></td>
<td align="left"><p><span data-ttu-id="93084-155">x86</span><span class="sxs-lookup"><span data-stu-id="93084-155">x86</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="93084-156">Windows Vista</span><span class="sxs-lookup"><span data-stu-id="93084-156">Windows Vista</span></span></p></td>
<td align="left"><p><span data-ttu-id="93084-157">企业版、企业版或旗舰版</span><span class="sxs-lookup"><span data-stu-id="93084-157">Business, Enterprise, or Ultimate</span></span></p></td>
<td align="left"><p><span data-ttu-id="93084-158">无服务包、SP1 或 SP2</span><span class="sxs-lookup"><span data-stu-id="93084-158">No service pack, SP1, or SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="93084-159">x86</span><span class="sxs-lookup"><span data-stu-id="93084-159">x86</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="93084-160">Windows7 ¹</span><span class="sxs-lookup"><span data-stu-id="93084-160">Windows7¹</span></span></p></td>
<td align="left"><p><span data-ttu-id="93084-161">专业版、企业版或旗舰版</span><span class="sxs-lookup"><span data-stu-id="93084-161">Professional, Enterprise, or Ultimate</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="93084-162">x86</span><span class="sxs-lookup"><span data-stu-id="93084-162">x86</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="93084-163">¹支持仅限 SP1 或 SP2 的 app-v 4.5 和 app-v 4。6</span><span class="sxs-lookup"><span data-stu-id="93084-163">¹Supported for App-V 4.5 with SP1 or SP2, and App-V 4.6 only</span></span>

<span data-ttu-id="93084-164">**注意** 应用程序虚拟化（app-v） 4.6 Sequencer 支持这些操作系统的32位和64位版本。</span><span class="sxs-lookup"><span data-stu-id="93084-164">**Note** The Application Virtualization (App-V) 4.6 Sequencer supports 32-bit and 64-bit versions of these operating systems.</span></span>

 

<span data-ttu-id="93084-165">你应该将运行 Sequencer 的计算机配置为在目标计算机上安装的相同应用程序。</span><span class="sxs-lookup"><span data-stu-id="93084-165">You should configure computers running the Sequencer with the same applications that are installed on targeted computers.</span></span>

### <span data-ttu-id="93084-166">适用于 App-v 4.6 SP2 的远程桌面服务的软件要求</span><span class="sxs-lookup"><span data-stu-id="93084-166">Software Requirements for Remote Desktop Services for App-V 4.6 SP2</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="93084-167">操作系统</span><span class="sxs-lookup"><span data-stu-id="93084-167">Operating System</span></span></th>
<th align="left"><span data-ttu-id="93084-168">版本</span><span class="sxs-lookup"><span data-stu-id="93084-168">Edition</span></span></th>
<th align="left"><span data-ttu-id="93084-169">Service Pack</span><span class="sxs-lookup"><span data-stu-id="93084-169">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="93084-170">系统体系结构</span><span class="sxs-lookup"><span data-stu-id="93084-170">System Architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="93084-171">Windows Server2003 R2</span><span class="sxs-lookup"><span data-stu-id="93084-171">Windows Server2003 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="93084-172">标准版、企业版或数据中心版</span><span class="sxs-lookup"><span data-stu-id="93084-172">Standard Edition, Enterprise Edition, or Datacenter Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="93084-173">SP2</span><span class="sxs-lookup"><span data-stu-id="93084-173">SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="93084-174">x86</span><span class="sxs-lookup"><span data-stu-id="93084-174">x86</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="93084-175">Windows Server2008</span><span class="sxs-lookup"><span data-stu-id="93084-175">Windows Server2008</span></span></p></td>
<td align="left"><p><span data-ttu-id="93084-176">标准版、企业版或数据中心版</span><span class="sxs-lookup"><span data-stu-id="93084-176">Standard, Enterprise, or Datacenter Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="93084-177">SP2</span><span class="sxs-lookup"><span data-stu-id="93084-177">SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="93084-178">x86</span><span class="sxs-lookup"><span data-stu-id="93084-178">x86</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="93084-179">Windows Server2008 R2</span><span class="sxs-lookup"><span data-stu-id="93084-179">Windows Server2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="93084-180">标准版、企业版或数据中心版</span><span class="sxs-lookup"><span data-stu-id="93084-180">Standard, Enterprise, or Datacenter Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="93084-181">无服务包或 SP1</span><span class="sxs-lookup"><span data-stu-id="93084-181">No service pack or SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="93084-182">x64</span><span class="sxs-lookup"><span data-stu-id="93084-182">x64</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="93084-183">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="93084-183">Windows Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="93084-184">标准版、企业版或数据中心版</span><span class="sxs-lookup"><span data-stu-id="93084-184">Standard, Enterprise, or Datacenter Edition</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="93084-185">x86 或 x64</span><span class="sxs-lookup"><span data-stu-id="93084-185">x86 or x64</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="93084-186">**注意** 应用程序虚拟化（app-v）4.6 适用于远程桌面服务的 SP2 支持这些操作系统的32位和64位版本。</span><span class="sxs-lookup"><span data-stu-id="93084-186">**Note** Application Virtualization (App-V) 4.6 SP2 for Remote Desktop Services supports 32-bit and 64-bit versions of these operating systems.</span></span>

 

### <span data-ttu-id="93084-187">适用于应用 V 4.6 SP2 之前的版本的远程桌面服务的软件要求</span><span class="sxs-lookup"><span data-stu-id="93084-187">Software Requirements for Remote Desktop Services for Versions that Precede App-V 4.6 SP2</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="93084-188">操作系统</span><span class="sxs-lookup"><span data-stu-id="93084-188">Operating System</span></span></th>
<th align="left"><span data-ttu-id="93084-189">版本</span><span class="sxs-lookup"><span data-stu-id="93084-189">Edition</span></span></th>
<th align="left"><span data-ttu-id="93084-190">Service Pack</span><span class="sxs-lookup"><span data-stu-id="93084-190">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="93084-191">系统体系结构</span><span class="sxs-lookup"><span data-stu-id="93084-191">System Architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="93084-192">Windows Server2003</span><span class="sxs-lookup"><span data-stu-id="93084-192">Windows Server2003</span></span></p></td>
<td align="left"><p><span data-ttu-id="93084-193">标准版、企业版或数据中心版</span><span class="sxs-lookup"><span data-stu-id="93084-193">Standard Edition, Enterprise Edition, or Datacenter Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="93084-194">SP1 或 SP2</span><span class="sxs-lookup"><span data-stu-id="93084-194">SP1 or SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="93084-195">x86</span><span class="sxs-lookup"><span data-stu-id="93084-195">x86</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="93084-196">Windows Server2003 R2</span><span class="sxs-lookup"><span data-stu-id="93084-196">Windows Server2003 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="93084-197">标准版、企业版或数据中心版</span><span class="sxs-lookup"><span data-stu-id="93084-197">Standard Edition, Enterprise Edition, or Datacenter Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="93084-198">无服务包或 SP2</span><span class="sxs-lookup"><span data-stu-id="93084-198">No service pack or SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="93084-199">x86</span><span class="sxs-lookup"><span data-stu-id="93084-199">x86</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="93084-200">Windows Server2008</span><span class="sxs-lookup"><span data-stu-id="93084-200">Windows Server2008</span></span></p></td>
<td align="left"><p><span data-ttu-id="93084-201">标准版、企业版或数据中心版</span><span class="sxs-lookup"><span data-stu-id="93084-201">Standard, Enterprise, or Datacenter Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="93084-202">SP1 或 SP2</span><span class="sxs-lookup"><span data-stu-id="93084-202">SP1 or SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="93084-203">x86</span><span class="sxs-lookup"><span data-stu-id="93084-203">x86</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="93084-204">Windows Server2008 R2</span><span class="sxs-lookup"><span data-stu-id="93084-204">Windows Server2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="93084-205">标准版、企业版或数据中心版</span><span class="sxs-lookup"><span data-stu-id="93084-205">Standard, Enterprise, or Datacenter Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="93084-206">无服务包或 SP1</span><span class="sxs-lookup"><span data-stu-id="93084-206">No service pack or SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="93084-207">x64</span><span class="sxs-lookup"><span data-stu-id="93084-207">x64</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="93084-208">**注意** 应用程序虚拟化（app-v）4.6 适用于远程桌面服务的 SP2 支持这些操作系统的32位和64位版本。</span><span class="sxs-lookup"><span data-stu-id="93084-208">**Note** Application Virtualization (App-V) 4.6 SP2 for Remote Desktop Services supports 32-bit and 64-bit versions of these operating systems.</span></span>

 

## <span data-ttu-id="93084-209">相关主题</span><span class="sxs-lookup"><span data-stu-id="93084-209">Related topics</span></span>


[<span data-ttu-id="93084-210">Application Virtualization Client 硬件和软件要求</span><span class="sxs-lookup"><span data-stu-id="93084-210">Application Virtualization Client Hardware and Software Requirements</span></span>](application-virtualization-client-hardware-and-software-requirements.md)

[<span data-ttu-id="93084-211">Application Virtualization System 要求</span><span class="sxs-lookup"><span data-stu-id="93084-211">Application Virtualization System Requirements</span></span>](application-virtualization-system-requirements.md)

[<span data-ttu-id="93084-212">如何安装 Application Virtualization Sequencer</span><span class="sxs-lookup"><span data-stu-id="93084-212">How to Install the Application Virtualization Sequencer</span></span>](how-to-install-the-application-virtualization-sequencer.md)

[<span data-ttu-id="93084-213">如何升级 Application Virtualization Sequencer</span><span class="sxs-lookup"><span data-stu-id="93084-213">How to Upgrade the Application Virtualization Sequencer</span></span>](how-to-upgrade-the-application-virtualization-sequencer.md)

 

 





