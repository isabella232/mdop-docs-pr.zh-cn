---
title: DaRT 8.0 支持的配置
description: DaRT 8.0 支持的配置
author: dansimp
ms.assetid: 95d68e5c-d202-4f4a-adef-d2098328172e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 02c891555992652bf2a9b2b674ab8377536ef9d6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803466"
---
# <span data-ttu-id="fd85a-103">DaRT 8.0 支持的配置</span><span class="sxs-lookup"><span data-stu-id="fd85a-103">DaRT 8.0 Supported Configurations</span></span>


<span data-ttu-id="fd85a-104">本主题指定在你的环境中安装和运行 Microsoft 诊断和恢复工具集（DaRT）8.0 所需的必备软件和支持的配置要求。</span><span class="sxs-lookup"><span data-stu-id="fd85a-104">This topic specifies the prerequisite software and supported configurations requirements that are necessary to install and run Microsoft Diagnostics and Recovery Toolset (DaRT) 8.0 in your environment.</span></span> <span data-ttu-id="fd85a-105">将指定运行 DaRT 8.0 所需的操作系统要求和系统要求。</span><span class="sxs-lookup"><span data-stu-id="fd85a-105">Both the operating system requirements and the system requirements that are required to run DaRT 8.0 are specified.</span></span> <span data-ttu-id="fd85a-106">有关创建 DaRT 恢复映像时需要考虑的先决条件的信息，请参阅[规划以创建 dart 8.0 恢复映像](planning-to-create-the-dart-80-recovery-image-dart-8.md)。</span><span class="sxs-lookup"><span data-stu-id="fd85a-106">For information about prerequisites that you need to consider to create the DaRT recovery image, see [Planning to Create the DaRT 8.0 Recovery Image](planning-to-create-the-dart-80-recovery-image-dart-8.md).</span></span>

<span data-ttu-id="fd85a-107">有关适用于更高版本的受支持的配置，请参阅适用版本的文档。</span><span class="sxs-lookup"><span data-stu-id="fd85a-107">For supported configurations that apply to later releases, see the documentation for the applicable release.</span></span>

<span data-ttu-id="fd85a-108">你可以通过两种方式之一安装 DaRT。</span><span class="sxs-lookup"><span data-stu-id="fd85a-108">You can install DaRT in one of two ways.</span></span> <span data-ttu-id="fd85a-109">你可以在 IT 管理员计算机上安装所有功能，你将执行与运行 DaRT 相关联的所有任务。</span><span class="sxs-lookup"><span data-stu-id="fd85a-109">You can install all functionality on an IT administrator computer, where you will perform all the tasks associated with running DaRT.</span></span> <span data-ttu-id="fd85a-110">或者，你也可以在管理员计算机上安装创建恢复映像的 DaRT 功能，然后在技术支持计算机上安装用于运行 DaRT （即 DaRT 远程连接查看器）的功能。</span><span class="sxs-lookup"><span data-stu-id="fd85a-110">Alternatively, you can install, on the administrator computer, only the DaRT functionality that creates the recovery image, and then install the functionality used to run DaRT (that is, the DaRT Remote Connection Viewer) on a help desk computer.</span></span>

## <a href="" id="---------dart-8-0-prerequisite-software"></a> <span data-ttu-id="fd85a-111">DaRT 8.0 必备软件</span><span class="sxs-lookup"><span data-stu-id="fd85a-111">DaRT 8.0 prerequisite software</span></span>


<span data-ttu-id="fd85a-112">在安装 DaRT 之前，请确保满足以下先决条件。</span><span class="sxs-lookup"><span data-stu-id="fd85a-112">Make sure that the following prerequisites are met before you install DaRT.</span></span>

### <span data-ttu-id="fd85a-113">管理员计算机先决条件</span><span class="sxs-lookup"><span data-stu-id="fd85a-113">Administrator computer prerequisites</span></span>

<span data-ttu-id="fd85a-114">下表列出了安装 DaRT 8.0 和所有 DaRT 工具时管理员计算机的安装先决条件。</span><span class="sxs-lookup"><span data-stu-id="fd85a-114">The following table lists the installation prerequisites for the administrator computer when you are installing DaRT 8.0 and all of the DaRT tools.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="fd85a-115">必备</span><span class="sxs-lookup"><span data-stu-id="fd85a-115">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="fd85a-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="fd85a-116">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="fd85a-117">Windows 评估和开发工具包（ADK）</span><span class="sxs-lookup"><span data-stu-id="fd85a-117">Windows Assessment and Development Kit (ADK)</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="fd85a-118">对于 DaRT 恢复映像向导是必需的。</span><span class="sxs-lookup"><span data-stu-id="fd85a-118">Required for the DaRT Recovery Image wizard.</span></span> <span data-ttu-id="fd85a-119">包含部署工具，这些工具用于自定义、部署和服务 Windows 映像，并且包含 Windows 预安装环境（Windows PE）。</span><span class="sxs-lookup"><span data-stu-id="fd85a-119">Contains the Deployment Tools, which are used to customize, deploy, and service Windows images, and contains the Windows Preinstallation Environment (Windows PE).</span></span> <span data-ttu-id="fd85a-120">如果仅安装远程连接查看器和/或崩溃分析器，则不需要 ADK。</span><span class="sxs-lookup"><span data-stu-id="fd85a-120">The ADK is not required if you are installing only the Remote Connection Viewer and/or Crash Analyzer.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="fd85a-121">.NET Framework 4。5</span><span class="sxs-lookup"><span data-stu-id="fd85a-121">.NET Framework 4.5</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="fd85a-122">DaRT 恢复映像向导所需。</span><span class="sxs-lookup"><span data-stu-id="fd85a-122">Required by the DaRT Recovery Image wizard.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="fd85a-123">Windows 开发工具包或软件开发工具包（可选）</span><span class="sxs-lookup"><span data-stu-id="fd85a-123">Windows Development Kit OR Software Development Kit (optional)</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="fd85a-124">崩溃分析器需要 Windows 驱动程序工具包中的 Windows 8 调试工具来分析内存转储文件。</span><span class="sxs-lookup"><span data-stu-id="fd85a-124">Crash Analyzer requires the Windows 8 Debugging Tools from the Windows Driver Kit to analyze memory dump files.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="fd85a-125">Windows 8 64 位 ISO 镜像</span><span class="sxs-lookup"><span data-stu-id="fd85a-125">Windows 8 64-bit ISO image</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="fd85a-126">DaRT 需要 windows 8 媒体中的 Windows 恢复环境（Windows RE）映像。</span><span class="sxs-lookup"><span data-stu-id="fd85a-126">DaRT requires the Windows Recovery Environment (Windows RE) image from the Windows 8 media.</span></span> <span data-ttu-id="fd85a-127">下载32位或64位版本的 Windows 8，具体取决于你要创建的 DaRT 恢复映像的类型。</span><span class="sxs-lookup"><span data-stu-id="fd85a-127">Download the 32-bit or 64-bit version of Windows 8, depending on the type of DaRT recovery image you want to create.</span></span> <span data-ttu-id="fd85a-128">如果你在你的环境中支持这两种系统类型，请下载 Windows 8 的两个版本。</span><span class="sxs-lookup"><span data-stu-id="fd85a-128">If you support both system types in your environment, download both versions of Windows 8.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="fd85a-129">技术支持计算机必备条件</span><span class="sxs-lookup"><span data-stu-id="fd85a-129">Help desk computer prerequisites</span></span>

<span data-ttu-id="fd85a-130">下表列出了运行 DaRT 8.0 远程连接查看器时帮助台计算机的安装先决条件。</span><span class="sxs-lookup"><span data-stu-id="fd85a-130">The following table lists the installation prerequisites for the help desk computer when you are running the DaRT 8.0 Remote Connection Viewer.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="fd85a-131">必备</span><span class="sxs-lookup"><span data-stu-id="fd85a-131">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="fd85a-132">详细信息</span><span class="sxs-lookup"><span data-stu-id="fd85a-132">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="fd85a-133">DaRT 8.0 远程连接查看器</span><span class="sxs-lookup"><span data-stu-id="fd85a-133">DaRT 8.0 Remote Connection Viewer</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="fd85a-134">必须安装在 Windows 8 操作系统上。</span><span class="sxs-lookup"><span data-stu-id="fd85a-134">Must be installed on a Windows 8 operating system.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="fd85a-135">NET Framework 4。5</span><span class="sxs-lookup"><span data-stu-id="fd85a-135">NET Framework 4.5</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="fd85a-136">DaRT 恢复映像向导所需</span><span class="sxs-lookup"><span data-stu-id="fd85a-136">Required by the DaRT Recovery Image wizard</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="fd85a-137">Windows 调试工具</span><span class="sxs-lookup"><span data-stu-id="fd85a-137">Debugging Tools for Windows</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="fd85a-138">仅在安装崩溃分析工具时需要</span><span class="sxs-lookup"><span data-stu-id="fd85a-138">Required only if you are installing the Crash Analyzer tool</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="fd85a-139">最终用户计算机先决条件</span><span class="sxs-lookup"><span data-stu-id="fd85a-139">End-user computer prerequisites</span></span>

<span data-ttu-id="fd85a-140">除了 Windows 8 操作系统之外，没有必须安装在最终用户计算机上的必备软件。</span><span class="sxs-lookup"><span data-stu-id="fd85a-140">There is no prerequisite software that must be installed on end-user computers, other than the Windows 8 operating system.</span></span>

## <a href="" id="---------dart-operating-system-requirements"></a> <span data-ttu-id="fd85a-141">DaRT 操作系统要求</span><span class="sxs-lookup"><span data-stu-id="fd85a-141">DaRT operating system requirements</span></span>


### <span data-ttu-id="fd85a-142">管理员计算机系统要求</span><span class="sxs-lookup"><span data-stu-id="fd85a-142">Administrator computer system requirements</span></span>

<span data-ttu-id="fd85a-143">下表列出了 DaRT 管理员计算机安装支持的操作系统。</span><span class="sxs-lookup"><span data-stu-id="fd85a-143">The following table lists the operating systems that are supported for the DaRT administrator computer installation.</span></span>

<span data-ttu-id="fd85a-144">**注意** 请确保为要在管理员计算机上安装的任何其他工具分配足够的空间。</span><span class="sxs-lookup"><span data-stu-id="fd85a-144">**Note** Make sure that you allocate enough space for any additional tools that you want to install on the administrator computer.</span></span>

 

<span data-ttu-id="fd85a-145">**注意** Microsoft 提供对当前服务包的支持，在某些情况下，还提供了之前的服务包。</span><span class="sxs-lookup"><span data-stu-id="fd85a-145">**Note** Microsoft provides support for the current service pack and, in some cases, the immediately preceding service pack.</span></span> <span data-ttu-id="fd85a-146">若要查找产品的支持时间表，请参阅[支持生命周期的服务包](https://go.microsoft.com/fwlink/p/?LinkId=31975)。</span><span class="sxs-lookup"><span data-stu-id="fd85a-146">To find the support timelines for your product, see the [Lifecycle Supported Service Packs](https://go.microsoft.com/fwlink/p/?LinkId=31975).</span></span> <span data-ttu-id="fd85a-147">有关 Microsoft 支持生命周期策略的其他信息，请参阅[Microsoft 支持生命周期支持策略常见问题解答](https://go.microsoft.com/fwlink/p/?LinkId=31976)。</span><span class="sxs-lookup"><span data-stu-id="fd85a-147">For additional information about Microsoft Support Lifecycle Policy, see [Microsoft Support Lifecycle Support Policy FAQ](https://go.microsoft.com/fwlink/p/?LinkId=31976).</span></span>

 

<table style="width:100%;">
<colgroup>
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="fd85a-148">操作系统</span><span class="sxs-lookup"><span data-stu-id="fd85a-148">Operating System</span></span></th>
<th align="left"><span data-ttu-id="fd85a-149">版本</span><span class="sxs-lookup"><span data-stu-id="fd85a-149">Edition</span></span></th>
<th align="left"><span data-ttu-id="fd85a-150">Service Pack</span><span class="sxs-lookup"><span data-stu-id="fd85a-150">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="fd85a-151">系统体系结构</span><span class="sxs-lookup"><span data-stu-id="fd85a-151">System Architecture</span></span></th>
<th align="left"><span data-ttu-id="fd85a-152">操作系统要求</span><span class="sxs-lookup"><span data-stu-id="fd85a-152">Operating System Requirements</span></span></th>
<th align="left"><span data-ttu-id="fd85a-153">运行 DaRT 的内存要求</span><span class="sxs-lookup"><span data-stu-id="fd85a-153">RAM Requirement for Running DaRT</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="fd85a-154">Windows8</span><span class="sxs-lookup"><span data-stu-id="fd85a-154">Windows8</span></span></p></td>
<td align="left"><p><span data-ttu-id="fd85a-155">所有版本</span><span class="sxs-lookup"><span data-stu-id="fd85a-155">All editions</span></span></p></td>
<td align="left"><p><span data-ttu-id="fd85a-156">不适用</span><span class="sxs-lookup"><span data-stu-id="fd85a-156">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="fd85a-157">64 位</span><span class="sxs-lookup"><span data-stu-id="fd85a-157">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="fd85a-158">2 GB</span><span class="sxs-lookup"><span data-stu-id="fd85a-158">2 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="fd85a-159">2.5 GB</span><span class="sxs-lookup"><span data-stu-id="fd85a-159">2.5 GB</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="fd85a-160">Windows8</span><span class="sxs-lookup"><span data-stu-id="fd85a-160">Windows8</span></span></p></td>
<td align="left"><p><span data-ttu-id="fd85a-161">所有版本</span><span class="sxs-lookup"><span data-stu-id="fd85a-161">All editions</span></span></p></td>
<td align="left"><p><span data-ttu-id="fd85a-162">不适用</span><span class="sxs-lookup"><span data-stu-id="fd85a-162">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="fd85a-163">32 位</span><span class="sxs-lookup"><span data-stu-id="fd85a-163">32-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="fd85a-164">1 GB</span><span class="sxs-lookup"><span data-stu-id="fd85a-164">1 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="fd85a-165">1.5 GB</span><span class="sxs-lookup"><span data-stu-id="fd85a-165">1.5 GB</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="fd85a-166">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="fd85a-166">Windows Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="fd85a-167">标准、企业、数据中心</span><span class="sxs-lookup"><span data-stu-id="fd85a-167">Standard, Enterprise, Data Center</span></span></p></td>
<td align="left"><p><span data-ttu-id="fd85a-168">不适用</span><span class="sxs-lookup"><span data-stu-id="fd85a-168">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="fd85a-169">64 位</span><span class="sxs-lookup"><span data-stu-id="fd85a-169">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="fd85a-170">512 MB</span><span class="sxs-lookup"><span data-stu-id="fd85a-170">512 MB</span></span></p></td>
<td align="left"><p><span data-ttu-id="fd85a-171">1. 0 GB</span><span class="sxs-lookup"><span data-stu-id="fd85a-171">1 .0 GB</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="-------------dart-help-desk-computer-system-requirements"></a> <span data-ttu-id="fd85a-172">DaRT 技术支持计算机系统要求</span><span class="sxs-lookup"><span data-stu-id="fd85a-172">DaRT help desk computer system requirements</span></span>

<span data-ttu-id="fd85a-173">如果你允许帮助台远程对计算机进行故障排除，则必须在技术支持计算机上安装远程连接查看器。</span><span class="sxs-lookup"><span data-stu-id="fd85a-173">If you allow a help desk to remotely troubleshoot computers, you must have the Remote Connection Viewer installed on the help desk computer.</span></span> <span data-ttu-id="fd85a-174">你可以选择在技术支持计算机上安装崩溃分析器工具。</span><span class="sxs-lookup"><span data-stu-id="fd85a-174">You can optionally install the Crash Analyzer tool on the help desk computer.</span></span>

<span data-ttu-id="fd85a-175">DaRT 8.0 使技术支持人员能够使用 DaRT 7.0 或 DaRT 8.0 远程连接查看器连接到 DaRT 8.0 计算机。</span><span class="sxs-lookup"><span data-stu-id="fd85a-175">DaRT 8.0 enables a help desk worker to connect to a DaRT 8.0 computer by using either the DaRT 7.0 or DaRT 8.0 Remote Connection Viewer.</span></span> <span data-ttu-id="fd85a-176">DaRT 7.0 远程连接查看器需要 Windows 7 操作系统，而 DaRT 8.0 远程连接查看器需要 Windows 8。</span><span class="sxs-lookup"><span data-stu-id="fd85a-176">The DaRT 7.0 Remote Connection Viewer requires a Windows 7 operating system, while the DaRT 8.0 Remote Connection Viewer requires Windows 8.</span></span> <span data-ttu-id="fd85a-177">DaRT 8.0 远程连接查看器和所有其他 DaRT 8.0 工具只能安装在运行 Windows 8 的计算机上。</span><span class="sxs-lookup"><span data-stu-id="fd85a-177">The DaRT 8.0 Remote Connection Viewer and all other DaRT 8.0 tools can be installed only on a computer running Windows 8.</span></span>

<span data-ttu-id="fd85a-178">下表列出了 DaRT 技术支持计算机安装支持的操作系统。</span><span class="sxs-lookup"><span data-stu-id="fd85a-178">The following table lists the operating systems that are supported for the DaRT help desk computer installation.</span></span>

<table style="width:100%;">
<colgroup>
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="fd85a-179">操作系统</span><span class="sxs-lookup"><span data-stu-id="fd85a-179">Operating System</span></span></th>
<th align="left"><span data-ttu-id="fd85a-180">版本</span><span class="sxs-lookup"><span data-stu-id="fd85a-180">Edition</span></span></th>
<th align="left"><span data-ttu-id="fd85a-181">Service Pack</span><span class="sxs-lookup"><span data-stu-id="fd85a-181">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="fd85a-182">系统体系结构</span><span class="sxs-lookup"><span data-stu-id="fd85a-182">System Architecture</span></span></th>
<th align="left"><span data-ttu-id="fd85a-183">操作系统要求</span><span class="sxs-lookup"><span data-stu-id="fd85a-183">Operating System Requirements</span></span></th>
<th align="left"><span data-ttu-id="fd85a-184">运行 DaRT 的内存要求</span><span class="sxs-lookup"><span data-stu-id="fd85a-184">RAM Requirements for Running DaRT</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="fd85a-185">Windows8</span><span class="sxs-lookup"><span data-stu-id="fd85a-185">Windows8</span></span></p></td>
<td align="left"><p><span data-ttu-id="fd85a-186">所有版本</span><span class="sxs-lookup"><span data-stu-id="fd85a-186">All editions</span></span></p></td>
<td align="left"><p><span data-ttu-id="fd85a-187">不适用</span><span class="sxs-lookup"><span data-stu-id="fd85a-187">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="fd85a-188">64 位</span><span class="sxs-lookup"><span data-stu-id="fd85a-188">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="fd85a-189">2 GB</span><span class="sxs-lookup"><span data-stu-id="fd85a-189">2 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="fd85a-190">2.5 GB</span><span class="sxs-lookup"><span data-stu-id="fd85a-190">2.5 GB</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="fd85a-191">Windows8 （仅限远程连接查看器8.0）</span><span class="sxs-lookup"><span data-stu-id="fd85a-191">Windows8 (with Remote Connection Viewer 8.0 only)</span></span></p></td>
<td align="left"><p><span data-ttu-id="fd85a-192">所有版本</span><span class="sxs-lookup"><span data-stu-id="fd85a-192">All editions</span></span></p></td>
<td align="left"><p><span data-ttu-id="fd85a-193">不适用</span><span class="sxs-lookup"><span data-stu-id="fd85a-193">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="fd85a-194">32 位</span><span class="sxs-lookup"><span data-stu-id="fd85a-194">32-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="fd85a-195">1 GB</span><span class="sxs-lookup"><span data-stu-id="fd85a-195">1 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="fd85a-196">1.5 GB</span><span class="sxs-lookup"><span data-stu-id="fd85a-196">1.5 GB</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="fd85a-197">Windows 7 （仅限远程连接查看器7.0）</span><span class="sxs-lookup"><span data-stu-id="fd85a-197">Windows 7 (with Remote Connection Viewer 7.0 only)</span></span></p></td>
<td align="left"><p><span data-ttu-id="fd85a-198">所有版本</span><span class="sxs-lookup"><span data-stu-id="fd85a-198">All editions</span></span></p></td>
<td align="left"><p><span data-ttu-id="fd85a-199">SP1、SP2</span><span class="sxs-lookup"><span data-stu-id="fd85a-199">SP1, SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="fd85a-200">64位或32位</span><span class="sxs-lookup"><span data-stu-id="fd85a-200">64-bit or 32-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="fd85a-201">1 GB</span><span class="sxs-lookup"><span data-stu-id="fd85a-201">1 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="fd85a-202">不适用</span><span class="sxs-lookup"><span data-stu-id="fd85a-202">N/A</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="fd85a-203">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="fd85a-203">Windows Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="fd85a-204">标准、企业、数据中心</span><span class="sxs-lookup"><span data-stu-id="fd85a-204">Standard, Enterprise, Data Center</span></span></p></td>
<td align="left"><p><span data-ttu-id="fd85a-205">不适用</span><span class="sxs-lookup"><span data-stu-id="fd85a-205">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="fd85a-206">64 位</span><span class="sxs-lookup"><span data-stu-id="fd85a-206">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="fd85a-207">51</span><span class="sxs-lookup"><span data-stu-id="fd85a-207">51</span></span></p></td>
<td align="left"><p><span data-ttu-id="fd85a-208">1.0 GB</span><span class="sxs-lookup"><span data-stu-id="fd85a-208">1.0 GB</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="fd85a-209">DaRT 对于最终用户计算机还具有以下最低硬件要求：</span><span class="sxs-lookup"><span data-stu-id="fd85a-209">DaRT also has the following minimum hardware requirements for the end-user computer:</span></span>

<span data-ttu-id="fd85a-210">CD 或 DVD 驱动器或 USB 端口-仅当你使用 CD、DVD 或 USB 在企业中部署 DaRT 时才需要。</span><span class="sxs-lookup"><span data-stu-id="fd85a-210">A CD or DVD drive or a USB port - required only if you are deploying DaRT in your enterprise by using a CD, DVD, or USB.</span></span>

<span data-ttu-id="fd85a-211">从 CD 或 DVD、USB 闪存驱动器或从远程或恢复分区启动计算机的 BIOS 支持。</span><span class="sxs-lookup"><span data-stu-id="fd85a-211">BIOS support for starting the computer from a CD or DVD, a USB flash drive, or from a remote or recovery partition.</span></span>

### <a href="" id="-------------dart-end-user-computer-system-requirements"></a> <span data-ttu-id="fd85a-212">DaRT 最终用户计算机系统要求</span><span class="sxs-lookup"><span data-stu-id="fd85a-212">DaRT end-user computer system requirements</span></span>

<span data-ttu-id="fd85a-213">DaRT 中的 "诊断和恢复工具集" 窗口要求最终用户计算机使用下列操作系统之一以及可用于 DaRT 的指定系统内存量：</span><span class="sxs-lookup"><span data-stu-id="fd85a-213">The Diagnostics and Recovery Toolset window in DaRT requires that the end-user computer use one of the following operating systems together with the specified amount of system memory available for DaRT:</span></span>

<table style="width:100%;">
<colgroup>
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="fd85a-214">操作系统</span><span class="sxs-lookup"><span data-stu-id="fd85a-214">Operating System</span></span></th>
<th align="left"><span data-ttu-id="fd85a-215">版本</span><span class="sxs-lookup"><span data-stu-id="fd85a-215">Edition</span></span></th>
<th align="left"><span data-ttu-id="fd85a-216">Service Pack</span><span class="sxs-lookup"><span data-stu-id="fd85a-216">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="fd85a-217">系统体系结构</span><span class="sxs-lookup"><span data-stu-id="fd85a-217">System Architecture</span></span></th>
<th align="left"><span data-ttu-id="fd85a-218">操作系统要求</span><span class="sxs-lookup"><span data-stu-id="fd85a-218">Operating System Requirements</span></span></th>
<th align="left"><span data-ttu-id="fd85a-219">RAM 要求</span><span class="sxs-lookup"><span data-stu-id="fd85a-219">RAM Requirements</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="fd85a-220">Windows8</span><span class="sxs-lookup"><span data-stu-id="fd85a-220">Windows8</span></span></p></td>
<td align="left"><p><span data-ttu-id="fd85a-221">所有版本</span><span class="sxs-lookup"><span data-stu-id="fd85a-221">All editions</span></span></p></td>
<td align="left"><p><span data-ttu-id="fd85a-222">不适用</span><span class="sxs-lookup"><span data-stu-id="fd85a-222">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="fd85a-223">64 位</span><span class="sxs-lookup"><span data-stu-id="fd85a-223">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="fd85a-224">2 GB</span><span class="sxs-lookup"><span data-stu-id="fd85a-224">2 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="fd85a-225">2.5 GB</span><span class="sxs-lookup"><span data-stu-id="fd85a-225">2.5 GB</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="fd85a-226">Windows8</span><span class="sxs-lookup"><span data-stu-id="fd85a-226">Windows8</span></span></p></td>
<td align="left"><p><span data-ttu-id="fd85a-227">所有版本</span><span class="sxs-lookup"><span data-stu-id="fd85a-227">All editions</span></span></p></td>
<td align="left"><p><span data-ttu-id="fd85a-228">不适用</span><span class="sxs-lookup"><span data-stu-id="fd85a-228">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="fd85a-229">32 位</span><span class="sxs-lookup"><span data-stu-id="fd85a-229">32-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="fd85a-230">1 GB</span><span class="sxs-lookup"><span data-stu-id="fd85a-230">1 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="fd85a-231">1.5 GB</span><span class="sxs-lookup"><span data-stu-id="fd85a-231">1.5 GB</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="fd85a-232">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="fd85a-232">Windows Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="fd85a-233">标准、企业、数据中心</span><span class="sxs-lookup"><span data-stu-id="fd85a-233">Standard, Enterprise, Data Center</span></span></p></td>
<td align="left"><p><span data-ttu-id="fd85a-234">不适用</span><span class="sxs-lookup"><span data-stu-id="fd85a-234">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="fd85a-235">64 位</span><span class="sxs-lookup"><span data-stu-id="fd85a-235">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="fd85a-236">512 MB</span><span class="sxs-lookup"><span data-stu-id="fd85a-236">512 MB</span></span></p></td>
<td align="left"><p><span data-ttu-id="fd85a-237">1.0 GB</span><span class="sxs-lookup"><span data-stu-id="fd85a-237">1.0 GB</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="fd85a-238">相关主题</span><span class="sxs-lookup"><span data-stu-id="fd85a-238">Related topics</span></span>


[<span data-ttu-id="fd85a-239">计划部署 DaRT 8.0</span><span class="sxs-lookup"><span data-stu-id="fd85a-239">Planning to Deploy DaRT 8.0</span></span>](planning-to-deploy-dart-80-dart-8.md)

 

 





