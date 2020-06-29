---
title: DaRT 10 支持的配置
description: DaRT 10 支持的配置
author: dansimp
ms.assetid: a07d6562-1fa9-499f-829c-9cc487ede0b7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 414b9d5cb7bf78dcfeda3fafc1c476e367709446
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798220"
---
# <span data-ttu-id="bae30-103">DaRT 10 支持的配置</span><span class="sxs-lookup"><span data-stu-id="bae30-103">DaRT 10 Supported Configurations</span></span>


<span data-ttu-id="bae30-104">本主题指定在你的环境中安装和运行 Microsoft 诊断和恢复工具集（DaRT）10所需的必备软件和支持的配置要求。</span><span class="sxs-lookup"><span data-stu-id="bae30-104">This topic specifies the prerequisite software and supported configurations requirements that are necessary to install and run Microsoft Diagnostics and Recovery Toolset (DaRT) 10 in your environment.</span></span> <span data-ttu-id="bae30-105">将指定运行 DaRT 10 所需的操作系统要求和系统要求。</span><span class="sxs-lookup"><span data-stu-id="bae30-105">Both the operating system requirements and the system requirements that are required to run DaRT 10 are specified.</span></span> <span data-ttu-id="bae30-106">有关创建 DaRT 恢复映像时需要考虑的先决条件的信息，请参阅[规划以创建 dart 10 恢复映像](planning-to-create-the-dart-10-recovery-image.md)。</span><span class="sxs-lookup"><span data-stu-id="bae30-106">For information about prerequisites that you need to consider to create the DaRT recovery image, see [Planning to Create the DaRT 10 Recovery Image](planning-to-create-the-dart-10-recovery-image.md).</span></span>

<span data-ttu-id="bae30-107">有关适用于更高版本的受支持的配置，请参阅适用版本的文档。</span><span class="sxs-lookup"><span data-stu-id="bae30-107">For supported configurations that apply to later releases, see the documentation for the applicable release.</span></span>

<span data-ttu-id="bae30-108">你可以通过两种方式之一安装 DaRT。</span><span class="sxs-lookup"><span data-stu-id="bae30-108">You can install DaRT in one of two ways.</span></span> <span data-ttu-id="bae30-109">你可以在 IT 管理员计算机上安装所有功能，你将执行与运行 DaRT 相关联的所有任务。</span><span class="sxs-lookup"><span data-stu-id="bae30-109">You can install all functionality on an IT administrator computer, where you will perform all the tasks associated with running DaRT.</span></span> <span data-ttu-id="bae30-110">或者，你也可以在管理员计算机上安装创建恢复映像的 DaRT 功能，然后在技术支持计算机上安装用于运行 DaRT （即 DaRT 远程连接查看器）的功能。</span><span class="sxs-lookup"><span data-stu-id="bae30-110">Alternatively, you can install, on the administrator computer, only the DaRT functionality that creates the recovery image, and then install the functionality used to run DaRT (that is, the DaRT Remote Connection Viewer) on a help desk computer.</span></span>

## <span data-ttu-id="bae30-111">DaRT 10 必备软件</span><span class="sxs-lookup"><span data-stu-id="bae30-111">DaRT 10 prerequisite software</span></span>


<span data-ttu-id="bae30-112">在安装 DaRT 之前，请确保满足以下先决条件。</span><span class="sxs-lookup"><span data-stu-id="bae30-112">Make sure that the following prerequisites are met before you install DaRT.</span></span>

### <span data-ttu-id="bae30-113">管理员计算机先决条件</span><span class="sxs-lookup"><span data-stu-id="bae30-113">Administrator computer prerequisites</span></span>

<span data-ttu-id="bae30-114">下表列出了安装 DaRT 10 和所有 DaRT 工具时管理员计算机的安装先决条件。</span><span class="sxs-lookup"><span data-stu-id="bae30-114">The following table lists the installation prerequisites for the administrator computer when you are installing DaRT 10 and all of the DaRT tools.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="bae30-115">必备</span><span class="sxs-lookup"><span data-stu-id="bae30-115">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="bae30-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="bae30-116">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="bae30-117">Windows 评估和开发工具包（ADK）</span><span class="sxs-lookup"><span data-stu-id="bae30-117">Windows Assessment and Development Kit (ADK)</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="bae30-118">对于 DaRT 恢复映像向导是必需的。</span><span class="sxs-lookup"><span data-stu-id="bae30-118">Required for the DaRT Recovery Image wizard.</span></span> <span data-ttu-id="bae30-119">包含部署工具，这些工具用于自定义、部署和服务 Windows 映像，并且包含 Windows 预安装环境（Windows PE）。</span><span class="sxs-lookup"><span data-stu-id="bae30-119">Contains the Deployment Tools, which are used to customize, deploy, and service Windows images, and contains the Windows Preinstallation Environment (Windows PE).</span></span> <span data-ttu-id="bae30-120">如果仅安装远程连接查看器和/或崩溃分析器，则不需要 ADK。</span><span class="sxs-lookup"><span data-stu-id="bae30-120">The ADK is not required if you are installing only the Remote Connection Viewer and/or Crash Analyzer.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="bae30-121">Windows 开发工具包或软件开发工具包（可选）</span><span class="sxs-lookup"><span data-stu-id="bae30-121">Windows Development Kit OR Software Development Kit (optional)</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="bae30-122">崩溃分析器需要 windows 驱动程序工具包中的 Windows 10 调试工具来分析内存转储文件。</span><span class="sxs-lookup"><span data-stu-id="bae30-122">Crash Analyzer requires the Windows 10 Debugging Tools from the Windows Driver Kit to analyze memory dump files.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="bae30-123">Windows 10 64 位或32位 ISO 镜像</span><span class="sxs-lookup"><span data-stu-id="bae30-123">Windows 10 64-bit or 32-bit ISO image</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="bae30-124">DaRT 需要 windows 10 介质中的 Windows 恢复环境（Windows RE）映像。</span><span class="sxs-lookup"><span data-stu-id="bae30-124">DaRT requires the Windows Recovery Environment (Windows RE) image from the Windows 10 media.</span></span> <span data-ttu-id="bae30-125">下载32位或64位版本的 Windows 10，具体取决于要创建的 DaRT 恢复映像的类型。</span><span class="sxs-lookup"><span data-stu-id="bae30-125">Download the 32-bit or 64-bit version of Windows 10, depending on the type of DaRT recovery image you want to create.</span></span> <span data-ttu-id="bae30-126">如果你在你的环境中支持这两种系统类型，请下载 Windows 10 的两个版本。</span><span class="sxs-lookup"><span data-stu-id="bae30-126">If you support both system types in your environment, download both versions of Windows 10.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="bae30-127">技术支持计算机必备条件</span><span class="sxs-lookup"><span data-stu-id="bae30-127">Help desk computer prerequisites</span></span>

<span data-ttu-id="bae30-128">下表列出了运行 DaRT 10 远程连接查看器时帮助台计算机的安装先决条件。</span><span class="sxs-lookup"><span data-stu-id="bae30-128">The following table lists the installation prerequisites for the help desk computer when you are running the DaRT 10 Remote Connection Viewer.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="bae30-129">必备</span><span class="sxs-lookup"><span data-stu-id="bae30-129">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="bae30-130">详细信息</span><span class="sxs-lookup"><span data-stu-id="bae30-130">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="bae30-131">DaRT 10 远程连接查看器</span><span class="sxs-lookup"><span data-stu-id="bae30-131">DaRT 10 Remote Connection Viewer</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="bae30-132">必须在 Windows 10 操作系统上安装。</span><span class="sxs-lookup"><span data-stu-id="bae30-132">Must be installed on a Windows 10 operating system.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="bae30-133">Windows 调试工具</span><span class="sxs-lookup"><span data-stu-id="bae30-133">Debugging Tools for Windows</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="bae30-134">仅在安装崩溃分析工具时需要</span><span class="sxs-lookup"><span data-stu-id="bae30-134">Required only if you are installing the Crash Analyzer tool</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="bae30-135">最终用户计算机先决条件</span><span class="sxs-lookup"><span data-stu-id="bae30-135">End-user computer prerequisites</span></span>

<span data-ttu-id="bae30-136">除了 Windows 10 操作系统之外，不存在必须安装在最终用户计算机上的必备软件。</span><span class="sxs-lookup"><span data-stu-id="bae30-136">There is no prerequisite software that must be installed on end-user computers, other than the Windows 10 operating system.</span></span>

## <a href="" id="---------dart-10-operating-system-requirements"></a> <span data-ttu-id="bae30-137">DaRT 10 操作系统要求</span><span class="sxs-lookup"><span data-stu-id="bae30-137">DaRT 10 operating system requirements</span></span>


### <span data-ttu-id="bae30-138">管理员计算机系统要求</span><span class="sxs-lookup"><span data-stu-id="bae30-138">Administrator computer system requirements</span></span>

<span data-ttu-id="bae30-139">下表列出了 DaRT 10 管理员计算机安装支持的操作系统。</span><span class="sxs-lookup"><span data-stu-id="bae30-139">The following table lists the operating systems that are supported for the DaRT 10 administrator computer installation.</span></span>

<span data-ttu-id="bae30-140">**注意** 请确保为要在管理员计算机上安装的任何其他工具分配足够的空间。</span><span class="sxs-lookup"><span data-stu-id="bae30-140">**Note** Make sure that you allocate enough space for any additional tools that you want to install on the administrator computer.</span></span>

 

<span data-ttu-id="bae30-141">**注意** Microsoft 提供对当前服务包的支持，在某些情况下，还提供了之前的服务包。</span><span class="sxs-lookup"><span data-stu-id="bae30-141">**Note** Microsoft provides support for the current service pack and, in some cases, the immediately preceding service pack.</span></span> <span data-ttu-id="bae30-142">若要查找产品的支持时间表，请参阅[支持生命周期的服务包](https://go.microsoft.com/fwlink/p/?LinkId=31975)。</span><span class="sxs-lookup"><span data-stu-id="bae30-142">To find the support timelines for your product, see the [Lifecycle Supported Service Packs](https://go.microsoft.com/fwlink/p/?LinkId=31975).</span></span> <span data-ttu-id="bae30-143">有关 Microsoft 支持生命周期策略的其他信息，请参阅[Microsoft 支持生命周期支持策略常见问题解答](https://go.microsoft.com/fwlink/p/?LinkId=31976)。</span><span class="sxs-lookup"><span data-stu-id="bae30-143">For additional information about Microsoft Support Lifecycle Policy, see [Microsoft Support Lifecycle Support Policy FAQ](https://go.microsoft.com/fwlink/p/?LinkId=31976).</span></span>

 

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
<th align="left"><span data-ttu-id="bae30-144">操作系统</span><span class="sxs-lookup"><span data-stu-id="bae30-144">Operating System</span></span></th>
<th align="left"><span data-ttu-id="bae30-145">版本</span><span class="sxs-lookup"><span data-stu-id="bae30-145">Edition</span></span></th>
<th align="left"><span data-ttu-id="bae30-146">Service Pack</span><span class="sxs-lookup"><span data-stu-id="bae30-146">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="bae30-147">系统体系结构</span><span class="sxs-lookup"><span data-stu-id="bae30-147">System Architecture</span></span></th>
<th align="left"><span data-ttu-id="bae30-148">操作系统要求</span><span class="sxs-lookup"><span data-stu-id="bae30-148">Operating System Requirements</span></span></th>
<th align="left"><span data-ttu-id="bae30-149">运行 DaRT 的内存要求</span><span class="sxs-lookup"><span data-stu-id="bae30-149">RAM Requirement for Running DaRT</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bae30-150">Windows 10</span><span class="sxs-lookup"><span data-stu-id="bae30-150">Windows10</span></span></p></td>
<td align="left"><p><span data-ttu-id="bae30-151">所有版本</span><span class="sxs-lookup"><span data-stu-id="bae30-151">All editions</span></span></p></td>
<td align="left"><p><span data-ttu-id="bae30-152">不适用</span><span class="sxs-lookup"><span data-stu-id="bae30-152">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="bae30-153">64 位</span><span class="sxs-lookup"><span data-stu-id="bae30-153">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="bae30-154">2 GB</span><span class="sxs-lookup"><span data-stu-id="bae30-154">2 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="bae30-155">2.5 GB</span><span class="sxs-lookup"><span data-stu-id="bae30-155">2.5 GB</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bae30-156">Windows 10</span><span class="sxs-lookup"><span data-stu-id="bae30-156">Windows10</span></span></p></td>
<td align="left"><p><span data-ttu-id="bae30-157">所有版本</span><span class="sxs-lookup"><span data-stu-id="bae30-157">All editions</span></span></p></td>
<td align="left"><p><span data-ttu-id="bae30-158">不适用</span><span class="sxs-lookup"><span data-stu-id="bae30-158">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="bae30-159">32 位</span><span class="sxs-lookup"><span data-stu-id="bae30-159">32-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="bae30-160">1 GB</span><span class="sxs-lookup"><span data-stu-id="bae30-160">1 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="bae30-161">1.5 GB</span><span class="sxs-lookup"><span data-stu-id="bae30-161">1.5 GB</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="-------------dart-help-desk-computer-system-requirements"></a> <span data-ttu-id="bae30-162">DaRT 技术支持计算机系统要求</span><span class="sxs-lookup"><span data-stu-id="bae30-162">DaRT help desk computer system requirements</span></span>

<span data-ttu-id="bae30-163">如果你允许帮助台远程对计算机进行故障排除，则必须在技术支持计算机上安装远程连接查看器。</span><span class="sxs-lookup"><span data-stu-id="bae30-163">If you allow a help desk to remotely troubleshoot computers, you must have the Remote Connection Viewer installed on the help desk computer.</span></span> <span data-ttu-id="bae30-164">你可以选择在技术支持计算机上安装崩溃分析器工具。</span><span class="sxs-lookup"><span data-stu-id="bae30-164">You can optionally install the Crash Analyzer tool on the help desk computer.</span></span>

<span data-ttu-id="bae30-165">DaRT 10 使技术支持人员能够使用 DaRT 7.0、DaRT 8.0、DaRt 8.1 或 DaRT 10 远程连接查看器连接到 DaRT 10 计算机。</span><span class="sxs-lookup"><span data-stu-id="bae30-165">DaRT 10 enables a help desk worker to connect to a DaRT 10 computer by using either the DaRT 7.0, DaRT 8.0, DaRt 8.1, or DaRT 10 Remote Connection Viewer.</span></span> <span data-ttu-id="bae30-166">DaRT 7.0、DaRT 8.0 和 DaRt 8.1、远程连接查看器分别需要 Windows 7、Windows 8 或 Windows 8.1 操作系统，而 DaRT 10 远程连接查看器需要 Windows 10。</span><span class="sxs-lookup"><span data-stu-id="bae30-166">The DaRT 7.0, DaRT 8.0 and DaRt 8.1, Remote Connection Viewers require Windows 7, Windows 8, or Windows 8.1 operating systems respectively, while the DaRT 10 Remote Connection Viewer requires Windows 10.</span></span> <span data-ttu-id="bae30-167">DaRT 10 远程连接查看器和所有其他 DaRT 10 工具只能安装在运行 Windows 10 的计算机上。</span><span class="sxs-lookup"><span data-stu-id="bae30-167">The DaRT 10 Remote Connection Viewer and all other DaRT 10 tools can be installed only on a computer running Windows 10.</span></span>

<span data-ttu-id="bae30-168">下表列出了 DaRT 技术支持计算机安装支持的操作系统。</span><span class="sxs-lookup"><span data-stu-id="bae30-168">The following table lists the operating systems that are supported for the DaRT help desk computer installation.</span></span>

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
<th align="left"><span data-ttu-id="bae30-169">操作系统</span><span class="sxs-lookup"><span data-stu-id="bae30-169">Operating System</span></span></th>
<th align="left"><span data-ttu-id="bae30-170">版本</span><span class="sxs-lookup"><span data-stu-id="bae30-170">Edition</span></span></th>
<th align="left"><span data-ttu-id="bae30-171">Service Pack</span><span class="sxs-lookup"><span data-stu-id="bae30-171">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="bae30-172">系统体系结构</span><span class="sxs-lookup"><span data-stu-id="bae30-172">System Architecture</span></span></th>
<th align="left"><span data-ttu-id="bae30-173">操作系统要求</span><span class="sxs-lookup"><span data-stu-id="bae30-173">Operating System Requirements</span></span></th>
<th align="left"><span data-ttu-id="bae30-174">运行 DaRT 的内存要求</span><span class="sxs-lookup"><span data-stu-id="bae30-174">RAM Requirements for Running DaRT</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bae30-175">Windows 10</span><span class="sxs-lookup"><span data-stu-id="bae30-175">Windows10</span></span></p></td>
<td align="left"><p><span data-ttu-id="bae30-176">所有版本</span><span class="sxs-lookup"><span data-stu-id="bae30-176">All editions</span></span></p></td>
<td align="left"><p><span data-ttu-id="bae30-177">不适用</span><span class="sxs-lookup"><span data-stu-id="bae30-177">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="bae30-178">64 位</span><span class="sxs-lookup"><span data-stu-id="bae30-178">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="bae30-179">2 GB</span><span class="sxs-lookup"><span data-stu-id="bae30-179">2 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="bae30-180">2.5 GB</span><span class="sxs-lookup"><span data-stu-id="bae30-180">2.5 GB</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bae30-181">Windows10 （仅限远程连接查看器10.0）</span><span class="sxs-lookup"><span data-stu-id="bae30-181">Windows10 (with Remote Connection Viewer 10.0 only)</span></span></p></td>
<td align="left"><p><span data-ttu-id="bae30-182">所有版本</span><span class="sxs-lookup"><span data-stu-id="bae30-182">All editions</span></span></p></td>
<td align="left"><p><span data-ttu-id="bae30-183">不适用</span><span class="sxs-lookup"><span data-stu-id="bae30-183">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="bae30-184">32 位</span><span class="sxs-lookup"><span data-stu-id="bae30-184">32-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="bae30-185">1 GB</span><span class="sxs-lookup"><span data-stu-id="bae30-185">1 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="bae30-186">1.5 GB</span><span class="sxs-lookup"><span data-stu-id="bae30-186">1.5 GB</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bae30-187">Windows8</span><span class="sxs-lookup"><span data-stu-id="bae30-187">Windows8</span></span></p></td>
<td align="left"><p><span data-ttu-id="bae30-188">所有版本</span><span class="sxs-lookup"><span data-stu-id="bae30-188">All editions</span></span></p></td>
<td align="left"><p><span data-ttu-id="bae30-189">不适用</span><span class="sxs-lookup"><span data-stu-id="bae30-189">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="bae30-190">64 位</span><span class="sxs-lookup"><span data-stu-id="bae30-190">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="bae30-191">2 GB</span><span class="sxs-lookup"><span data-stu-id="bae30-191">2 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="bae30-192">2.5 GB</span><span class="sxs-lookup"><span data-stu-id="bae30-192">2.5 GB</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bae30-193">Windows8 （仅限远程连接查看器8.0）</span><span class="sxs-lookup"><span data-stu-id="bae30-193">Windows8 (with Remote Connection Viewer 8.0 only)</span></span></p></td>
<td align="left"><p><span data-ttu-id="bae30-194">所有版本</span><span class="sxs-lookup"><span data-stu-id="bae30-194">All editions</span></span></p></td>
<td align="left"><p><span data-ttu-id="bae30-195">不适用</span><span class="sxs-lookup"><span data-stu-id="bae30-195">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="bae30-196">32 位</span><span class="sxs-lookup"><span data-stu-id="bae30-196">32-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="bae30-197">1 GB</span><span class="sxs-lookup"><span data-stu-id="bae30-197">1 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="bae30-198">1.5 GB</span><span class="sxs-lookup"><span data-stu-id="bae30-198">1.5 GB</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bae30-199">Windows 7 （仅限远程连接查看器7.0）</span><span class="sxs-lookup"><span data-stu-id="bae30-199">Windows 7 (with Remote Connection Viewer 7.0 only)</span></span></p></td>
<td align="left"><p><span data-ttu-id="bae30-200">所有版本</span><span class="sxs-lookup"><span data-stu-id="bae30-200">All editions</span></span></p></td>
<td align="left"><p><span data-ttu-id="bae30-201">SP1、SP2</span><span class="sxs-lookup"><span data-stu-id="bae30-201">SP1, SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="bae30-202">64位或32位</span><span class="sxs-lookup"><span data-stu-id="bae30-202">64-bit or 32-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="bae30-203">1 GB</span><span class="sxs-lookup"><span data-stu-id="bae30-203">1 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="bae30-204">不适用</span><span class="sxs-lookup"><span data-stu-id="bae30-204">N/A</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bae30-205">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="bae30-205">Windows Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="bae30-206">标准、企业、数据中心</span><span class="sxs-lookup"><span data-stu-id="bae30-206">Standard, Enterprise, Data Center</span></span></p></td>
<td align="left"><p><span data-ttu-id="bae30-207">不适用</span><span class="sxs-lookup"><span data-stu-id="bae30-207">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="bae30-208">64 位</span><span class="sxs-lookup"><span data-stu-id="bae30-208">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="bae30-209">2 GB</span><span class="sxs-lookup"><span data-stu-id="bae30-209">2 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="bae30-210">1.0 GB</span><span class="sxs-lookup"><span data-stu-id="bae30-210">1.0 GB</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bae30-211">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="bae30-211">Windows Server 2012 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="bae30-212">标准、企业、数据中心</span><span class="sxs-lookup"><span data-stu-id="bae30-212">Standard, Enterprise, Data Center</span></span></p></td>
<td align="left"><p><span data-ttu-id="bae30-213">不适用</span><span class="sxs-lookup"><span data-stu-id="bae30-213">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="bae30-214">64 位</span><span class="sxs-lookup"><span data-stu-id="bae30-214">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="bae30-215">2 GB</span><span class="sxs-lookup"><span data-stu-id="bae30-215">2 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="bae30-216">1.0 GB</span><span class="sxs-lookup"><span data-stu-id="bae30-216">1.0 GB</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="bae30-217">DaRT 对于最终用户计算机还具有以下最低硬件要求：</span><span class="sxs-lookup"><span data-stu-id="bae30-217">DaRT also has the following minimum hardware requirements for the end-user computer:</span></span>

<span data-ttu-id="bae30-218">CD 或 DVD 驱动器或 USB 端口-仅当你使用 CD、DVD 或 USB 在企业中部署 DaRT 时才需要。</span><span class="sxs-lookup"><span data-stu-id="bae30-218">A CD or DVD drive or a USB port - required only if you are deploying DaRT in your enterprise by using a CD, DVD, or USB.</span></span>

<span data-ttu-id="bae30-219">从 CD 或 DVD、USB 闪存驱动器或从远程或恢复分区启动计算机的 BIOS 支持。</span><span class="sxs-lookup"><span data-stu-id="bae30-219">BIOS support for starting the computer from a CD or DVD, a USB flash drive, or from a remote or recovery partition.</span></span>

### <a href="" id="-------------dart-10-end-user-computer-system-requirements"></a> <span data-ttu-id="bae30-220">DaRT 10 最终用户计算机系统要求</span><span class="sxs-lookup"><span data-stu-id="bae30-220">DaRT 10 end-user computer system requirements</span></span>

<span data-ttu-id="bae30-221">DaRT 10 中的 "诊断和恢复工具集" 窗口要求最终用户计算机使用下列操作系统之一以及可用于 DaRT 的指定系统内存量：</span><span class="sxs-lookup"><span data-stu-id="bae30-221">The Diagnostics and Recovery Toolset window in DaRT 10 requires that the end-user computer use one of the following operating systems together with the specified amount of system memory available for DaRT:</span></span>

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
<th align="left"><span data-ttu-id="bae30-222">操作系统</span><span class="sxs-lookup"><span data-stu-id="bae30-222">Operating System</span></span></th>
<th align="left"><span data-ttu-id="bae30-223">版本</span><span class="sxs-lookup"><span data-stu-id="bae30-223">Edition</span></span></th>
<th align="left"><span data-ttu-id="bae30-224">Service Pack</span><span class="sxs-lookup"><span data-stu-id="bae30-224">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="bae30-225">系统体系结构</span><span class="sxs-lookup"><span data-stu-id="bae30-225">System Architecture</span></span></th>
<th align="left"><span data-ttu-id="bae30-226">操作系统要求</span><span class="sxs-lookup"><span data-stu-id="bae30-226">Operating System Requirements</span></span></th>
<th align="left"><span data-ttu-id="bae30-227">RAM 要求</span><span class="sxs-lookup"><span data-stu-id="bae30-227">RAM Requirements</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bae30-228">Windows 10</span><span class="sxs-lookup"><span data-stu-id="bae30-228">Windows10</span></span></p></td>
<td align="left"><p><span data-ttu-id="bae30-229">所有版本</span><span class="sxs-lookup"><span data-stu-id="bae30-229">All editions</span></span></p></td>
<td align="left"><p><span data-ttu-id="bae30-230">不适用</span><span class="sxs-lookup"><span data-stu-id="bae30-230">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="bae30-231">64 位</span><span class="sxs-lookup"><span data-stu-id="bae30-231">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="bae30-232">2 GB</span><span class="sxs-lookup"><span data-stu-id="bae30-232">2 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="bae30-233">2.5 GB</span><span class="sxs-lookup"><span data-stu-id="bae30-233">2.5 GB</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bae30-234">Windows 10</span><span class="sxs-lookup"><span data-stu-id="bae30-234">Windows10</span></span></p></td>
<td align="left"><p><span data-ttu-id="bae30-235">所有版本</span><span class="sxs-lookup"><span data-stu-id="bae30-235">All editions</span></span></p></td>
<td align="left"><p><span data-ttu-id="bae30-236">不适用</span><span class="sxs-lookup"><span data-stu-id="bae30-236">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="bae30-237">32 位</span><span class="sxs-lookup"><span data-stu-id="bae30-237">32-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="bae30-238">1 GB</span><span class="sxs-lookup"><span data-stu-id="bae30-238">1 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="bae30-239">1.5 GB</span><span class="sxs-lookup"><span data-stu-id="bae30-239">1.5 GB</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="bae30-240">相关主题</span><span class="sxs-lookup"><span data-stu-id="bae30-240">Related topics</span></span>


[<span data-ttu-id="bae30-241">计划部署 DaRT 10</span><span class="sxs-lookup"><span data-stu-id="bae30-241">Planning to Deploy DaRT 10</span></span>](planning-to-deploy-dart-10.md)

 

 





