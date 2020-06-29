---
title: Application Virtualization 5.1 性能指南
description: Application Virtualization 5.1 性能指南
author: dansimp
ms.assetid: 5f2643c7-5cf7-4a29-adb7-45bf9f5b0364
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 3382a7958e12cc28b8101a6d5b7384a6975e6e82
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798316"
---
# <span data-ttu-id="273ab-103">Application Virtualization 5.1 性能指南</span><span class="sxs-lookup"><span data-stu-id="273ab-103">Performance Guidance for Application Virtualization 5.1</span></span>


<span data-ttu-id="273ab-104">了解如何配置 app-v 5.1 以优化性能、优化虚拟应用包以及使用 RDS 和 VDI 提供更好的用户体验。</span><span class="sxs-lookup"><span data-stu-id="273ab-104">Learn how to configure App-V 5.1 for optimal performance, optimize virtual app packages, and provide a better user experience with RDS and VDI.</span></span>

<span data-ttu-id="273ab-105">实现多个方法可帮助你改进最终用户体验。</span><span class="sxs-lookup"><span data-stu-id="273ab-105">Implementing multiple methods can help you improve the end-user experience.</span></span> <span data-ttu-id="273ab-106">但是，你的环境可能不支持所有方法。</span><span class="sxs-lookup"><span data-stu-id="273ab-106">However, your environment may not support all methods.</span></span>

<span data-ttu-id="273ab-107">阅读本文档之前，请阅读并理解以下信息。</span><span class="sxs-lookup"><span data-stu-id="273ab-107">You should read and understand the following information before reading this document.</span></span>

-   [<span data-ttu-id="273ab-108">Microsoft Application Virtualization 5.1 管理员指南</span><span class="sxs-lookup"><span data-stu-id="273ab-108">Microsoft Application Virtualization 5.1 Administrator's Guide</span></span>](microsoft-application-virtualization-51-administrators-guide.md)

-   [<span data-ttu-id="273ab-109">App-v 5 SP2 应用程序发布和客户端交互</span><span class="sxs-lookup"><span data-stu-id="273ab-109">App-V 5 SP2 Application Publishing and Client Interaction</span></span>](https://go.microsoft.com/fwlink/?LinkId=395206)

-   [<span data-ttu-id="273ab-110">Microsoft Application Virtualization 排序指南</span><span class="sxs-lookup"><span data-stu-id="273ab-110">Microsoft Application Virtualization Sequencing Guide</span></span>](https://go.microsoft.com/fwlink/?LinkId=269953)

**<span data-ttu-id="273ab-111">注意</span><span class="sxs-lookup"><span data-stu-id="273ab-111">Note</span></span>**  
<span data-ttu-id="273ab-112">本文档中使用的某些术语可能具有不同的含义，具体取决于外部源和上下文。</span><span class="sxs-lookup"><span data-stu-id="273ab-112">Some terms used in this document may have different meanings depending on external source and context.</span></span> <span data-ttu-id="273ab-113">有关本文档中使用的术语的详细信息，后跟星号 **\\** \* 请查看本文档的[Application Virtualization 性能指南术语](#bkmk-terms1)部分。</span><span class="sxs-lookup"><span data-stu-id="273ab-113">For more information about terms used in this document followed by an asterisk **\\**\* review the [Application Virtualization Performance Guidance Terminology](#bkmk-terms1) section of this document.</span></span>



<span data-ttu-id="273ab-114">最后，本文档将向你提供用于配置运行 app-v 5.1 客户端的计算机和用于优化性能的环境的信息。</span><span class="sxs-lookup"><span data-stu-id="273ab-114">Finally, this document will provide you with the information to configure the computer running App-V 5.1 client and the environment for optimal performance.</span></span> <span data-ttu-id="273ab-115">使用 sequencer 优化虚拟应用程序包的性能，并了解如何使用用户体验虚拟化（UE-V）或其他用户环境管理技术在远程桌面服务（RDS）和非永久性虚拟桌面基础结构（VDI）中提供有关 App-v 5.1 的最佳用户体验。</span><span class="sxs-lookup"><span data-stu-id="273ab-115">Optimize your virtual application packages for performance using the sequencer, and to understand how to use User Experience Virtualization (UE-V) or other user environment management technologies to provide the optimal user experience with App-V 5.1 in both Remote Desktop Services (RDS) and non-persistent virtual desktop infrastructure (VDI).</span></span>

<span data-ttu-id="273ab-116">为了帮助确定哪些信息与你的环境相关，你应查看每个部分的简要概述和适用性清单。</span><span class="sxs-lookup"><span data-stu-id="273ab-116">To help determine what information is relevant to your environment you should review each section’s brief overview and applicability checklist.</span></span>

## <a href="" id="---------app-v-5-1-in-stateful--non-persistent-deployments"></a> <span data-ttu-id="273ab-117">状态 \ \* 非永久性部署中的 app-v 5。1</span><span class="sxs-lookup"><span data-stu-id="273ab-117">App-V 5.1 in stateful\* non-persistent deployments</span></span>


<span data-ttu-id="273ab-118">本部分提供了有关帮助确保用户在登录后的几秒钟内能够访问所有虚拟应用程序的方法的信息。</span><span class="sxs-lookup"><span data-stu-id="273ab-118">This section provides information about an approach that helps ensure a user will have access to all virtual applications within seconds after logging in.</span></span> <span data-ttu-id="273ab-119">这是通过唯一寻址经常运行的 App-v 5.1 发布刷新的唯一方法实现的。</span><span class="sxs-lookup"><span data-stu-id="273ab-119">This is achieved by uniquely addressing the often long-running App-V 5.1 publishing refresh.</span></span> <span data-ttu-id="273ab-120">由于你将发现方法的基础，最快的发布刷新是无需实际执行任何操作的方法。</span><span class="sxs-lookup"><span data-stu-id="273ab-120">As you will discover the basis of the approach, the fastest publishing refresh, is one that doesn’t have to actually do anything.</span></span> <span data-ttu-id="273ab-121">必须满足许多条件和步骤，然后才能提供最佳的用户体验。</span><span class="sxs-lookup"><span data-stu-id="273ab-121">A number of conditions must be met and steps followed to provide the optimal user experience.</span></span>

<span data-ttu-id="273ab-122">有关详细信息，请使用以下部分中的信息：</span><span class="sxs-lookup"><span data-stu-id="273ab-122">Use the information in the following section for more information:</span></span>

<span data-ttu-id="273ab-123">[使用方案](#bkmk-us)-当你查看这两个方案时，请记住这两种方法的极端。</span><span class="sxs-lookup"><span data-stu-id="273ab-123">[Usage Scenarios](#bkmk-us) - As you review the two scenarios, keep in mind that these are the approach extremes.</span></span> <span data-ttu-id="273ab-124">根据你的使用要求，你可以选择将这些步骤应用到用户和/或虚拟应用程序包的子集。</span><span class="sxs-lookup"><span data-stu-id="273ab-124">Based on your usage requirements, you may choose to apply these steps to a subset of users and/or virtual applications packages.</span></span>

-   <span data-ttu-id="273ab-125">针对性能进行优化-若要提供最佳体验，你可以期望基本映像包含一些 App-v 虚拟应用程序包。</span><span class="sxs-lookup"><span data-stu-id="273ab-125">Optimized for Performance – To provide the optimal experience, you can expect the base image to include some of the App-V virtual application package.</span></span> <span data-ttu-id="273ab-126">本文将讨论此和其他要求。</span><span class="sxs-lookup"><span data-stu-id="273ab-126">This and other requirements are discussed.</span></span>

-   <span data-ttu-id="273ab-127">针对存储进行了优化-如果你关注存储影响，请遵循此方案将帮助解决这些问题。</span><span class="sxs-lookup"><span data-stu-id="273ab-127">Optimized for Storage – If you are concerned with the storage impact, following this scenario will help address those concerns.</span></span>

[<span data-ttu-id="273ab-128">准备环境</span><span class="sxs-lookup"><span data-stu-id="273ab-128">Preparing your Environment</span></span>](#bkmk-pe)

-   <span data-ttu-id="273ab-129">准备基本映像的步骤-无论是在非持久性 VDI 还是在 RDSH 环境中，只有少数几个步骤都必须在基本映像中完成才能启用此方法。</span><span class="sxs-lookup"><span data-stu-id="273ab-129">Steps to Prepare the Base Image – Whether in a non-persistent VDI or RDSH environment, only a few steps must be completed in the base image to enable this approach.</span></span>

-   <span data-ttu-id="273ab-130">使用 UE-V 2.1 作为应用 V 方法的用户配置文件管理（UPM）解决方案-此方法的基础是 UEM 解决方案保留几个注册表和文件位置的内容的能力。</span><span class="sxs-lookup"><span data-stu-id="273ab-130">Use UE-V 2.1 as the User Profile Management (UPM) solution for the App-V approach – the cornerstone of this approach is the ability of a UEM solution to persist the contents of just a few registry and file locations.</span></span> <span data-ttu-id="273ab-131">这些位置构成了用户集成 \ \*。</span><span class="sxs-lookup"><span data-stu-id="273ab-131">These locations constitute the user integrations\*.</span></span> <span data-ttu-id="273ab-132">请务必查看 UPM 解决方案的特定要求。</span><span class="sxs-lookup"><span data-stu-id="273ab-132">Be sure to review the specific requirements for the UPM solution.</span></span>

[<span data-ttu-id="273ab-133">用户体验指导-通过</span><span class="sxs-lookup"><span data-stu-id="273ab-133">User Experience Walk-through</span></span>](#bkmk-uewt)

-   <span data-ttu-id="273ab-134">走出–这是分步指导，分步介绍了 app-v 和 UE-V 操作以及用户应具备的预期。</span><span class="sxs-lookup"><span data-stu-id="273ab-134">Walk-through – This is a step-by-step walk-through of the App-V and UE-V operations and the expectations users should have.</span></span>

-   <span data-ttu-id="273ab-135">结果-这将描述预期的结果。</span><span class="sxs-lookup"><span data-stu-id="273ab-135">Outcome – This describes the expected results.</span></span>

[<span data-ttu-id="273ab-136">对程序包生命周期的影响</span><span class="sxs-lookup"><span data-stu-id="273ab-136">Impact to Package Lifecycle</span></span>](#bkmk-plc)

[<span data-ttu-id="273ab-137">通过性能优化/优化增强 VDI 体验</span><span class="sxs-lookup"><span data-stu-id="273ab-137">Enhancing the VDI Experience through Performance Optimization/Tuning</span></span>](#bkmk-evdi)

### <a href="" id="applicability-checklist-"></a><span data-ttu-id="273ab-138">适用性清单</span><span class="sxs-lookup"><span data-stu-id="273ab-138">Applicability Checklist</span></span>

<span data-ttu-id="273ab-139">部署环境</span><span class="sxs-lookup"><span data-stu-id="273ab-139">Deployment Environment</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="273ab-140">非永久性 VDI 或 RDSH。</span><span class="sxs-lookup"><span data-stu-id="273ab-140">Non-Persistent VDI or RDSH.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="273ab-141">用户体验虚拟化（UE-V）、其他 UPM 解决方案或用户配置文件磁盘（UPD）。</span><span class="sxs-lookup"><span data-stu-id="273ab-141">User Experience Virtualization (UE-V), other UPM solutions or User Profile Disks (UPD).</span></span></p></td>
</tr>
</tbody>
</table>



<span data-ttu-id="273ab-142">预期配置</span><span class="sxs-lookup"><span data-stu-id="273ab-142">Expected Configuration</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="273ab-143">用户体验虚拟化（UE-V）已启用 app-v 用户状态模板或用户配置文件管理（UPM）软件。</span><span class="sxs-lookup"><span data-stu-id="273ab-143">User Experience Virtualization (UE-V) with the App-V user state template enabled or User Profile Management (UPM) software.</span></span> <span data-ttu-id="273ab-144">非 UE-V UPM 软件必须能够在登录或进程/应用程序启动和注销时触发。</span><span class="sxs-lookup"><span data-stu-id="273ab-144">Non-UE-V UPM software must be capable of triggering on Login or Process/Application Start and Logoff.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="273ab-145">已配置或可以配置 app-v 共享的内容存储（SCS）。</span><span class="sxs-lookup"><span data-stu-id="273ab-145">App-V Shared Content Store (SCS) is configured or can be configured.</span></span></p></td>
</tr>
</tbody>
</table>



<span data-ttu-id="273ab-146">IT 管理</span><span class="sxs-lookup"><span data-stu-id="273ab-146">IT Administration</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="273ab-147">管理员可能需要定期更新 VM 基本映像以确保最佳性能或管理员可能需要管理不同用户组的多个映像。</span><span class="sxs-lookup"><span data-stu-id="273ab-147">Admin may need to update the VM base image regularly to ensure optimal performance or Admin may need to manage multiple images for different user groups.</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-us"></a><span data-ttu-id="273ab-148">使用方案</span><span class="sxs-lookup"><span data-stu-id="273ab-148">Usage Scenario</span></span>

<span data-ttu-id="273ab-149">查看这两种方案时，请记住这些方法的极端。</span><span class="sxs-lookup"><span data-stu-id="273ab-149">As you review the two scenarios, keep in mind that these approach the extremes.</span></span> <span data-ttu-id="273ab-150">根据你的使用要求，你可以选择将这些步骤应用到用户、虚拟应用程序包或两者的子集。</span><span class="sxs-lookup"><span data-stu-id="273ab-150">Based on your usage requirements, you may choose to apply these steps to a subset of users, virtual application packages, or both.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="273ab-151">已针对性能进行优化</span><span class="sxs-lookup"><span data-stu-id="273ab-151">Optimized for Performance</span></span></th>
<th align="left"><span data-ttu-id="273ab-152">已针对存储优化</span><span class="sxs-lookup"><span data-stu-id="273ab-152">Optimized for Storage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="273ab-153">为了提供最佳的用户体验，此方法利用 UPM 解决方案的功能，并且需要额外的映像管理开销。</span><span class="sxs-lookup"><span data-stu-id="273ab-153">To provide the most optimal user experience, this approach leverages the capabilities of a UPM solution and requires additional image preparation and can incur some additional image management overhead.</span></span></p>
<p><span data-ttu-id="273ab-154">下面介绍了状态非持久部署中的许多性能改进。</span><span class="sxs-lookup"><span data-stu-id="273ab-154">The following describes many performance improvements in stateful non-persistent deployments.</span></span> <span data-ttu-id="273ab-155">有关详细信息，请参阅 <strong> </strong> <strong> </strong> <strong> 本文档的 "另请参阅" 部分中 </strong> 的用于优化发布性能的程序包和参考 App-v 排序指南的先后顺序步骤。</span><span class="sxs-lookup"><span data-stu-id="273ab-155">For more information, see the <strong>Sequencing Steps to Optimize Packages for Publishing Performance</strong> and reference to <strong>App-V Sequencing Guide</strong> in the <strong>See Also section of this document</strong>.</span></span></p></td>
<td align="left"><p><span data-ttu-id="273ab-156">此处仍适用于上一方案的一般预期。</span><span class="sxs-lookup"><span data-stu-id="273ab-156">The general expectations of the previous scenario still apply here.</span></span> <span data-ttu-id="273ab-157">但是，请记住，VM 映像通常存储在非常昂贵的阵列中;已对该方法稍作改动。</span><span class="sxs-lookup"><span data-stu-id="273ab-157">However, keep in mind that VM images are typically stored in very costly arrays; a slight alteration has been made to the approach.</span></span> <span data-ttu-id="273ab-158">不要预配置基本映像中的用户目标虚拟应用程序包。</span><span class="sxs-lookup"><span data-stu-id="273ab-158">Do not pre-configure user-targeted virtual application packages in the base image.</span></span></p>
<p><span data-ttu-id="273ab-159">本文档的 "用户体验演练" 部分详细介绍了此变更的影响。</span><span class="sxs-lookup"><span data-stu-id="273ab-159">The impact of this alteration is detailed in the User Experience Walkthrough section of this document.</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-pe"></a><span data-ttu-id="273ab-160">准备环境</span><span class="sxs-lookup"><span data-stu-id="273ab-160">Preparing your Environment</span></span>

<span data-ttu-id="273ab-161">下表显示为方法准备基本映像和 UE-V 或另一个 UPM 解决方案所需的步骤。</span><span class="sxs-lookup"><span data-stu-id="273ab-161">The following table displays the required steps to prepare the base image and the UE-V or another UPM solution for the approach.</span></span>

**<span data-ttu-id="273ab-162">准备基本映像</span><span class="sxs-lookup"><span data-stu-id="273ab-162">Prepare the Base Image</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="273ab-163">已针对性能进行优化</span><span class="sxs-lookup"><span data-stu-id="273ab-163">Optimized for Performance</span></span></th>
<th align="left"><span data-ttu-id="273ab-164">已针对存储优化</span><span class="sxs-lookup"><span data-stu-id="273ab-164">Optimized for Storage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="273ab-165">安装客户端的 app-v 5.1 客户端版本。</span><span class="sxs-lookup"><span data-stu-id="273ab-165">Install the App-V 5.1 client version of the client.</span></span></p></li>
<li><p><span data-ttu-id="273ab-166">安装 UE-V 并从 UE-V 模板库下载 app-v 设置模板，请参阅以下步骤。</span><span class="sxs-lookup"><span data-stu-id="273ab-166">Install UE-V and download the App-V Settings Template from the UE-V template Gallery, see the following steps.</span></span></p></li>
<li><p><span data-ttu-id="273ab-167">为共享内容存储（SCS）模式进行配置。</span><span class="sxs-lookup"><span data-stu-id="273ab-167">Configure for Shared Content Store (SCS) mode.</span></span> <span data-ttu-id="273ab-168">有关详细信息，请参阅 <a href="how-to-install-the-app-v-51-client-for-shared-content-store-mode.md" data-raw-source="[How to Install the App-V 5.1 Client for Shared Content Store Mode](how-to-install-the-app-v-51-client-for-shared-content-store-mode.md)"> 如何为共享内容存储模式安装 app-v 5.1 客户端 </a> 。</span><span class="sxs-lookup"><span data-stu-id="273ab-168">For more information see <a href="how-to-install-the-app-v-51-client-for-shared-content-store-mode.md" data-raw-source="[How to Install the App-V 5.1 Client for Shared Content Store Mode](how-to-install-the-app-v-51-client-for-shared-content-store-mode.md)">How to Install the App-V 5.1 Client for Shared Content Store Mode</a>.</span></span></p></li>
<li><p><span data-ttu-id="273ab-169">配置在登录注册表 DWORD 上保留用户集成。</span><span class="sxs-lookup"><span data-stu-id="273ab-169">Configure Preserve User Integrations on Login Registry DWORD.</span></span></p></li>
<li><p><span data-ttu-id="273ab-170">预配置所有由用户和全局定向的程序包（例如， <strong> Add-AppvClientPackage </strong> 。</span><span class="sxs-lookup"><span data-stu-id="273ab-170">Pre-configure all user- and global-targeted packages for example, <strong>Add-AppvClientPackage</strong>.</span></span></p></li>
<li><p><span data-ttu-id="273ab-171">预配置所有用户和全局定向的连接组（例如， <strong> Add-AppvClientConnectionGroup </strong> 。</span><span class="sxs-lookup"><span data-stu-id="273ab-171">Pre-configure all user- and global-targeted connection groups for example, <strong>Add-AppvClientConnectionGroup</strong>.</span></span></p></li>
<li><p><span data-ttu-id="273ab-172">预发布所有全局目标程序包。</span><span class="sxs-lookup"><span data-stu-id="273ab-172">Pre-publish all global-targeted packages.</span></span></p>
<p></p>
<p><span data-ttu-id="273ab-173">另</span><span class="sxs-lookup"><span data-stu-id="273ab-173">Alternatively,</span></span></p>
<ul>
<li><p><span data-ttu-id="273ab-174">执行全局发布/刷新。</span><span class="sxs-lookup"><span data-stu-id="273ab-174">Perform a global publishing/refresh.</span></span></p></li>
<li><p><span data-ttu-id="273ab-175">执行用户发布/刷新。</span><span class="sxs-lookup"><span data-stu-id="273ab-175">Perform a user publishing/refresh.</span></span></p></li>
<li><p><span data-ttu-id="273ab-176">取消发布所有面向用户的程序包。</span><span class="sxs-lookup"><span data-stu-id="273ab-176">Un-publish all user-targeted packages.</span></span></p></li>
<li><p><span data-ttu-id="273ab-177">删除以下用户虚拟文件系统（VFS）条目。</span><span class="sxs-lookup"><span data-stu-id="273ab-177">Delete the following user-Virtual File System (VFS) entries.</span></span></p></li>
</ul>
<p><code>AppData\Local\Microsoft\AppV\Client\VFS</code></p>
<p><code>AppData\Roaming\Microsoft\AppV\Client\VFS</code></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="273ab-178">安装客户端的 app-v 5.1 客户端版本。</span><span class="sxs-lookup"><span data-stu-id="273ab-178">Install the App-V 5.1 client version of the client.</span></span></p></li>
<li><p><span data-ttu-id="273ab-179">安装 UE-V 并从 UE-V 模板库下载 app-v 设置模板，请参阅以下步骤。</span><span class="sxs-lookup"><span data-stu-id="273ab-179">Install UE-V and download the App-V Settings Template from the UE-V template Gallery, see the following steps.</span></span></p></li>
<li><p><span data-ttu-id="273ab-180">为共享内容存储（SCS）模式进行配置。</span><span class="sxs-lookup"><span data-stu-id="273ab-180">Configure for Shared Content Store (SCS) mode.</span></span> <span data-ttu-id="273ab-181">有关详细信息，请参阅 <a href="how-to-install-the-app-v-51-client-for-shared-content-store-mode.md" data-raw-source="[How to Install the App-V 5.1 Client for Shared Content Store Mode](how-to-install-the-app-v-51-client-for-shared-content-store-mode.md)"> 如何为共享内容存储模式安装 app-v 5.1 客户端 </a> 。</span><span class="sxs-lookup"><span data-stu-id="273ab-181">For more information see <a href="how-to-install-the-app-v-51-client-for-shared-content-store-mode.md" data-raw-source="[How to Install the App-V 5.1 Client for Shared Content Store Mode](how-to-install-the-app-v-51-client-for-shared-content-store-mode.md)">How to Install the App-V 5.1 Client for Shared Content Store Mode</a>.</span></span></p></li>
<li><p><span data-ttu-id="273ab-182">配置在登录注册表 DWORD 上保留用户集成。</span><span class="sxs-lookup"><span data-stu-id="273ab-182">Configure Preserve User Integrations on Login Registry DWORD.</span></span></p></li>
<li><p><span data-ttu-id="273ab-183">预配置所有全局定向的程序包（例如， <strong> Add-AppvClientPackage </strong> 。</span><span class="sxs-lookup"><span data-stu-id="273ab-183">Pre-configure all global-targeted packages for example, <strong>Add-AppvClientPackage</strong>.</span></span></p></li>
<li><p><span data-ttu-id="273ab-184">预配置所有全局定向的连接组（例如， <strong> Add-AppvClientConnectionGroup </strong> 。</span><span class="sxs-lookup"><span data-stu-id="273ab-184">Pre-configure all global-targeted connection groups for example, <strong>Add-AppvClientConnectionGroup</strong>.</span></span></p></li>
<li><p><span data-ttu-id="273ab-185">预发布所有全局目标程序包。</span><span class="sxs-lookup"><span data-stu-id="273ab-185">Pre-publish all global-targeted packages.</span></span></p>
<p></p></li>
</ul></td>
</tr>
</tbody>
</table>



<span data-ttu-id="273ab-186">**配置**-对于关键应用程序-V 客户端配置以及更多上下文和操作方法，请查看以下信息：</span><span class="sxs-lookup"><span data-stu-id="273ab-186">**Configurations** - For critical App-V Client configurations and for a little more context and how-to, review the following information:</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="273ab-187">配置设置</span><span class="sxs-lookup"><span data-stu-id="273ab-187">Configuration Setting</span></span></th>
<th align="left"><span data-ttu-id="273ab-188">这是什么？</span><span class="sxs-lookup"><span data-stu-id="273ab-188">What does this do?</span></span></th>
<th align="left"><span data-ttu-id="273ab-189">我应该如何使用它？</span><span class="sxs-lookup"><span data-stu-id="273ab-189">How should I use it?</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="273ab-190">共享内容存储（SCS）模式</span><span class="sxs-lookup"><span data-stu-id="273ab-190">Shared Content Store (SCS) Mode</span></span></p>
<ul>
<li><p><span data-ttu-id="273ab-191">可在 PowerShell 中使用 <strong> AppvClientConfiguration </strong> - <strong> SharedContentStoreMode </strong> 或</span><span class="sxs-lookup"><span data-stu-id="273ab-191">Configurable in PowerShell using <strong>Set- AppvClientConfiguration</strong> –<strong>SharedContentStoreMode</strong>, or</span></span></p></li>
<li><p><span data-ttu-id="273ab-192">在安装 app-v 客户端的过程中。</span><span class="sxs-lookup"><span data-stu-id="273ab-192">During installation of the App-V client.</span></span></p></li>
</ul></td>
<td align="left"><p><span data-ttu-id="273ab-193">仅当运行共享内容存储时，才会在硬盘上维护发布数据;其他虚拟应用程序资源将保留在内存（RAM）中。</span><span class="sxs-lookup"><span data-stu-id="273ab-193">When running the shared content store only publishing data is maintained on hard disk; other virtual application assets are maintained in memory (RAM).</span></span></p>
<p><span data-ttu-id="273ab-194">这有助于保存本地存储并最大限度地减少每秒磁盘 i/o （IOPS）。</span><span class="sxs-lookup"><span data-stu-id="273ab-194">This helps to conserve local storage and minimize disk I/O per second (IOPS).</span></span></p></td>
<td align="left"><p><span data-ttu-id="273ab-195">如果在应用 V 客户端终结点和 SCS 内容服务器（SAN）之间提供低延迟连接，则建议使用此操作。</span><span class="sxs-lookup"><span data-stu-id="273ab-195">This is recommended when low-latency connections are available between the App-V Client endpoint and the SCS content server, SAN.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="273ab-196">PreserveUserIntegrationsOnLogin</span><span class="sxs-lookup"><span data-stu-id="273ab-196">PreserveUserIntegrationsOnLogin</span></span></p>
<ul>
<li><p><span data-ttu-id="273ab-197">在注册表中的 " <strong> HKEY_LOCAL_MACHINE </strong>  \  <strong> 软件 </strong>  \  <strong> Microsoft </strong>  \  <strong> AppV </strong>  \  <strong> 客户端 </strong>  \  <strong> 集成 </strong> " 下进行配置。</span><span class="sxs-lookup"><span data-stu-id="273ab-197">Configure in the Registry under <strong>HKEY_LOCAL_MACHINE</strong> \ <strong>Software</strong> \ <strong>Microsoft</strong> \ <strong>AppV</strong> \ <strong>Client</strong> \ <strong>Integration</strong>.</span></span></p></li>
<li><p><span data-ttu-id="273ab-198">创建 <strong> </strong> 值为1的 DWORD 值 PreserveUserIntegrationsOnLogin <strong> </strong> 。</span><span class="sxs-lookup"><span data-stu-id="273ab-198">Create the DWORD value <strong>PreserveUserIntegrationsOnLogin</strong> with a value of <strong>1</strong>.</span></span></p></li>
<li><p><span data-ttu-id="273ab-199">重新启动 App-v client 服务或重启运行 App-v 客户端的计算机。</span><span class="sxs-lookup"><span data-stu-id="273ab-199">Restart the App-V client service or restart the computer running the App-V Client.</span></span></p></li>
</ul></td>
<td align="left"><p><span data-ttu-id="273ab-200">如果尚未预配置（ <strong> Add-AppvClientPackage </strong> ）特定程序包，并且未配置此设置，则 App-v 客户端将解除集成 \* 保留的用户集成，然后重新集成 \*。</span><span class="sxs-lookup"><span data-stu-id="273ab-200">If you have not pre-configured (<strong>Add-AppvClientPackage</strong>) a specific package and this setting is not configured, the App-V Client will de-integrate\* the persisted user integrations, then re-integrate\*.</span></span></p>
<p><span data-ttu-id="273ab-201">对于满足上述条件的每个程序包，有效地将在发布/刷新期间完成两次工作。</span><span class="sxs-lookup"><span data-stu-id="273ab-201">For every package that meets the above conditions, effectively twice the work will be done during publishing/refresh.</span></span></p></td>
<td align="left"><p><span data-ttu-id="273ab-202">如果您不打算预配置基本映像中的每个可用用户程序包，请使用此设置。</span><span class="sxs-lookup"><span data-stu-id="273ab-202">If you don’t plan to pre-configure every available user package in the base image, use this setting.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="273ab-203">MaxConcurrentPublishingRefresh</span><span class="sxs-lookup"><span data-stu-id="273ab-203">MaxConcurrentPublishingRefresh</span></span></p>
<ul>
<li><p><span data-ttu-id="273ab-204">在注册表中的 " <strong> HKEY_LOCAL_MACHINE </strong> &lt; 增强的 &gt; 软件 </strong>  \  <strong> Microsoft </strong>  \  <strong> AppV </strong> &lt; 增强 &gt; 的客户端 </strong>  \  <strong> 发布 </strong> " 下进行配置。</span><span class="sxs-lookup"><span data-stu-id="273ab-204">Configure in the Registry under <strong>HKEY_LOCAL_MACHINE</strong> &lt;strong&gt;Software</strong> \ <strong>Microsoft</strong> \ <strong>AppV</strong> &lt;strong&gt;Client</strong> \ <strong>Publishing</strong>.</span></span></p></li>
<li><p><span data-ttu-id="273ab-205"><strong> </strong> 用所需的并发发布刷新次数创建 DWORD 值 MaxConcurrentPublishingrefresh。</span><span class="sxs-lookup"><span data-stu-id="273ab-205">Create the DWORD value <strong>MaxConcurrentPublishingrefresh</strong> with the desired maximum number of concurrent publishing refreshes.</span></span></p></li>
<li><p><span data-ttu-id="273ab-206">App-v 客户端服务和计算机不需要重新启动。</span><span class="sxs-lookup"><span data-stu-id="273ab-206">The App-V client service and computer do not need to be restarted.</span></span></p></li>
</ul></td>
<td align="left"><p><span data-ttu-id="273ab-207">此设置确定可以同时执行发布刷新/同步的用户数。</span><span class="sxs-lookup"><span data-stu-id="273ab-207">This setting determines the number of users that can perform a publishing refresh/sync at the same time.</span></span> <span data-ttu-id="273ab-208">默认设置为 "无限制"。</span><span class="sxs-lookup"><span data-stu-id="273ab-208">The default setting is no limit.</span></span></p></td>
<td align="left"><p><span data-ttu-id="273ab-209">限制并发发布刷新数可防止过度占用的 CPU 使用率影响计算机性能。</span><span class="sxs-lookup"><span data-stu-id="273ab-209">Limiting the number of concurrent publishing refreshes prevents excessive CPU usage that could impact computer performance.</span></span> <span data-ttu-id="273ab-210">建议在 RDS 环境中使用此限制，在这种情况下，多个用户可以同时登录到同一台计算机并执行发布刷新同步。</span><span class="sxs-lookup"><span data-stu-id="273ab-210">This limit is recommended in an RDS environment, where multiple users can log in to the same computer at the same time and perform a publishing refresh sync.</span></span></p>
<p><span data-ttu-id="273ab-211">如果达到了并发发布刷新阈值，发布新应用程序并使最终用户在登录后可以使用的时间可能会花费不确定的时间。</span><span class="sxs-lookup"><span data-stu-id="273ab-211">If the concurrent publishing refresh threshold is reached, the time required to publish new applications and make them available to end users after they log in could take an indeterminate amount of time.</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="273ab-212">为 App-v 方法配置 UE-V 解决方案</span><span class="sxs-lookup"><span data-stu-id="273ab-212">Configure UE-V solution for App-V Approach</span></span>

<span data-ttu-id="273ab-213">我们建议使用 Microsoft 用户体验虚拟化（UE-V）捕获和集中特定用户的应用程序设置和 Windows 操作系统设置。</span><span class="sxs-lookup"><span data-stu-id="273ab-213">We recommend using Microsoft User Experience Virtualization (UE-V) to capture and centralize application settings and Windows operating system settings for a specific user.</span></span> <span data-ttu-id="273ab-214">然后，这些设置将应用于用户访问的不同计算机，包括桌面计算机、便携式计算机和虚拟桌面基础结构（VDI）会话。</span><span class="sxs-lookup"><span data-stu-id="273ab-214">These settings are then applied to the different computers that are accessed by the user, including desktop computers, laptop computers, and virtual desktop infrastructure (VDI) sessions.</span></span> <span data-ttu-id="273ab-215">UE-V 针对 RDS 和 VDI 方案进行了优化。</span><span class="sxs-lookup"><span data-stu-id="273ab-215">UE-V is optimized for RDS and VDI scenarios.</span></span>

<span data-ttu-id="273ab-216">有关详细信息，请参阅[用户体验虚拟化2.0 入门](https://technet.microsoft.com/library/dn458926.aspx)</span><span class="sxs-lookup"><span data-stu-id="273ab-216">For more information see [Getting Started With User Experience Virtualization 2.0](https://technet.microsoft.com/library/dn458926.aspx)</span></span>

<span data-ttu-id="273ab-217">实质上，只需安装 UE-V 客户端，然后从[Microsoft 用户体验虚拟化（ue-v）模板库](https://gallery.technet.microsoft.com/Authored-UE-V-Settings-bb442a33)下载以下 microsoft 创作的 app-v 设置模板。</span><span class="sxs-lookup"><span data-stu-id="273ab-217">In essence all that is required is to install the UE-V client and download the following Microsoft authored App-V settings template from the [Microsoft User Experience Virtualization (UE-V) template gallery](https://gallery.technet.microsoft.com/Authored-UE-V-Settings-bb442a33).</span></span> <span data-ttu-id="273ab-218">注册模板。</span><span class="sxs-lookup"><span data-stu-id="273ab-218">Register the template.</span></span> <span data-ttu-id="273ab-219">有关 UE-V 模板的详细信息，请参阅[用于获取和注册模板的 ue-v 特定资源](https://technet.microsoft.com/library/dn458926.aspx)。</span><span class="sxs-lookup"><span data-stu-id="273ab-219">For more information around UE-V templates see [The UE-V specific resource for acquiring and registering the template](https://technet.microsoft.com/library/dn458926.aspx).</span></span>

**<span data-ttu-id="273ab-220">注意</span><span class="sxs-lookup"><span data-stu-id="273ab-220">Note</span></span>**  
<span data-ttu-id="273ab-221">在不执行其他配置步骤的情况下，Microsoft 用户环境虚拟化（UE-V）将无法同步目标计算机上的 "开始" 菜单快捷方式（.lnk 文件）。</span><span class="sxs-lookup"><span data-stu-id="273ab-221">Without performing an additional configuration step, the Microsoft User Environment Virtualization (UE-V) will not be able to synchronize the Start menu shortcuts (.lnk files) on the target computer.</span></span> <span data-ttu-id="273ab-222">默认情况下将排除 .lnk 文件类型。</span><span class="sxs-lookup"><span data-stu-id="273ab-222">The .lnk file type is excluded by default.</span></span>

<span data-ttu-id="273ab-223">UE-V 仅支持从 "RDS 和 VDI" 方案中的排除列表中删除 .lnk 文件类型，其中每个用户的设备都将具有同一位置安装的同一应用程序集，并且每个 .lnk 文件对所有用户的设备均有效。</span><span class="sxs-lookup"><span data-stu-id="273ab-223">UE-V will only support removing the .lnk file type from the exclusion list in the RDS and VDI scenarios, where every user’s device will have the same set of applications installed to the same location and every .lnk file is valid for all the users’ devices.</span></span> <span data-ttu-id="273ab-224">例如，UE-V 目前不支持以下2种方案，因为最终结果将是快捷方式将在一个但不是所有设备上有效。</span><span class="sxs-lookup"><span data-stu-id="273ab-224">For example, UE-V would not currently support the following 2 scenarios, because the net result will be that the shortcut will be valid on one but not all devices.</span></span>

-   <span data-ttu-id="273ab-225">如果用户在启用了 .lnk 文件的一台设备上安装了应用程序，并且在另一台设备上安装了与启用了 .lnk 文件的其他安装根目录相同的本机应用程序。</span><span class="sxs-lookup"><span data-stu-id="273ab-225">If a user has an application installed on one device with .lnk files enabled and the same native application installed on another device to a different installation root with .lnk files enabled.</span></span>

-   <span data-ttu-id="273ab-226">如果用户在一台设备上安装了应用程序，但未启用另一台设备上的 .lnk 文件。</span><span class="sxs-lookup"><span data-stu-id="273ab-226">If a user has an application installed on one device but not another with .lnk files enabled.</span></span>



**<span data-ttu-id="273ab-227">重要提示</span><span class="sxs-lookup"><span data-stu-id="273ab-227">Important</span></span>**  
<span data-ttu-id="273ab-228">本主题介绍如何使用注册表编辑器更改 Windows 注册表。</span><span class="sxs-lookup"><span data-stu-id="273ab-228">This topic describes how to change the Windows registry by using Registry Editor.</span></span> <span data-ttu-id="273ab-229">如果不正确地更改 Windows 注册表，则可能会导致严重问题，可能需要重新安装 Windows。</span><span class="sxs-lookup"><span data-stu-id="273ab-229">If you change the Windows registry incorrectly, you can cause serious problems that might require you to reinstall Windows.</span></span> <span data-ttu-id="273ab-230">在更改注册表之前，应创建注册表文件（.dat 和 .dat）的备份副本。</span><span class="sxs-lookup"><span data-stu-id="273ab-230">You should make a backup copy of the registry files (System.dat and User.dat) before you change the registry.</span></span> <span data-ttu-id="273ab-231">Microsoft 无法保证更改注册表时可能出现的问题可以解决。</span><span class="sxs-lookup"><span data-stu-id="273ab-231">Microsoft cannot guarantee that the problems that might occur when you change the registry can be resolved.</span></span> <span data-ttu-id="273ab-232">更改注册表的风险由您自己承担。</span><span class="sxs-lookup"><span data-stu-id="273ab-232">Change the registry at your own risk.</span></span>



<span data-ttu-id="273ab-233">使用 Microsoft 注册表编辑器（regedit.exe），导航到**HKEY \ _LOCAL \ _MACHINE**  \\  **软件**  \\  **Microsoft**  \\  **UEV**  \\  **Agent**  \\  **配置**  \\  **ExcludedFileTypes**并从排除的文件类型中删除 **.lnk** 。</span><span class="sxs-lookup"><span data-stu-id="273ab-233">Using the Microsoft Registry Editor (regedit.exe), navigate to **HKEY\_LOCAL\_MACHINE** \\ **Software** \\ **Microsoft** \\ **UEV** \\ **Agent** \\ **Configuration** \\ **ExcludedFileTypes** and remove **.lnk** from the excluded file types.</span></span>

**<span data-ttu-id="273ab-234">为 App-v 方法配置其他用户配置文件管理（UPM）解决方案</span><span class="sxs-lookup"><span data-stu-id="273ab-234">Configure other User Profile Management (UPM) solution for App-V Approach</span></span>**

<span data-ttu-id="273ab-235">在有状态的环境中的预期是，UPM 解决方案已实现，并且可以支持跨会话和登录之间的用户数据的持久性。</span><span class="sxs-lookup"><span data-stu-id="273ab-235">The expectation in a stateful environment is that a UPM solution is implemented and can support persistence of user data across sessions and between logins.</span></span>

<span data-ttu-id="273ab-236">UPM 解决方案的要求如下所示。</span><span class="sxs-lookup"><span data-stu-id="273ab-236">The requirements for the UPM solution are as follows.</span></span>

<span data-ttu-id="273ab-237">若要启用针对用户的 app-v 5.1 方法的优化登录体验，解决方案必须具备以下功能：</span><span class="sxs-lookup"><span data-stu-id="273ab-237">To enable an optimized login experience, for example the App-V 5.1 approach for the user, the solution must be capable of:</span></span>

-   <span data-ttu-id="273ab-238">将以下用户集成保留为用户配置文件/角色的一部分。</span><span class="sxs-lookup"><span data-stu-id="273ab-238">Persisting the below user integrations as part of the user profile/persona.</span></span>

-   <span data-ttu-id="273ab-239">在登录（或应用程序启动）上触发用户配置文件同步，这样可以确保在发布/刷新开始之前应用所有用户集成，或者</span><span class="sxs-lookup"><span data-stu-id="273ab-239">Triggering a user profile sync on login (or application start), which can guarantee that all user integrations are applied before publishing/refresh begin, or,</span></span>

-   <span data-ttu-id="273ab-240">附加和分离用户配置文件磁盘（UPD）或包含用户集成的类似技术。</span><span class="sxs-lookup"><span data-stu-id="273ab-240">Attaching and detaching a user profile disk (UPD) or similar technology that contains the user integrations.</span></span>

    **<span data-ttu-id="273ab-241">注意</span><span class="sxs-lookup"><span data-stu-id="273ab-241">Note</span></span>**  
    <span data-ttu-id="273ab-242">仅当将整个配置文件存储在用户配置文件磁盘上时，才支持使用 UPD。</span><span class="sxs-lookup"><span data-stu-id="273ab-242">App-V is supported when using UPD only when the entire profile is stored on the user profile disk.</span></span>

    <span data-ttu-id="273ab-243">将 UPD 与存储在用户配置文件磁盘中的选定文件夹结合使用时，不支持 app-v 程序包。</span><span class="sxs-lookup"><span data-stu-id="273ab-243">App-V packages are not supported when using UPD with selected folders stored in the user profile disk.</span></span> <span data-ttu-id="273ab-244">"写入时副本" 驱动程序不会处理 UPD 选定的文件夹。</span><span class="sxs-lookup"><span data-stu-id="273ab-244">The Copy on Write driver does not handle UPD selected folders.</span></span>



-   <span data-ttu-id="273ab-245">在会话注销之前捕获对位置（构成用户集成）的更改。</span><span class="sxs-lookup"><span data-stu-id="273ab-245">Capturing changes to the locations, which constitute the user integrations, prior to session logoff.</span></span>

<span data-ttu-id="273ab-246">使用 app-v 5.1 添加发布服务器（**AppvPublishingServer**）时，你可以配置同步，例如，在登录期间刷新和/或在指定的刷新间隔后进行刷新。</span><span class="sxs-lookup"><span data-stu-id="273ab-246">With App-V 5.1 when you add a publishing server (**Add-AppvPublishingServer**) you can configure synchronization, for example refresh during log on and/or after a specified refresh interval.</span></span> <span data-ttu-id="273ab-247">在这两种情况下，都将创建计划任务。</span><span class="sxs-lookup"><span data-stu-id="273ab-247">In both cases a scheduled task is created.</span></span>

<span data-ttu-id="273ab-248">在早期版本的 App-v 5.1 中，使用将启动用户和全局刷新的 VBScript 配置了两个计划任务。</span><span class="sxs-lookup"><span data-stu-id="273ab-248">In previous versions of App-V 5.1, both scheduled tasks were configured using a VBScript that would initiate the user and global refresh.</span></span> <span data-ttu-id="273ab-249">对于应用程序虚拟化 5.0 SP2，应用程序虚拟化 SP2 的用户在登录时刷新是由**SyncAppvPublishingServer.exe**发起的。</span><span class="sxs-lookup"><span data-stu-id="273ab-249">With Hotfix Package 4 for Application Virtualization 5.0 SP2 the user refresh on log on was initiated by **SyncAppvPublishingServer.exe**.</span></span> <span data-ttu-id="273ab-250">引入此变更是为了提供 UPM 解决方案一个触发器进程。</span><span class="sxs-lookup"><span data-stu-id="273ab-250">This change was introduced to provide UPM solutions a trigger process.</span></span> <span data-ttu-id="273ab-251">此过程将延迟发布/refresh 以允许 UPM 解决方案应用用户集成。</span><span class="sxs-lookup"><span data-stu-id="273ab-251">This process delays the publish /refresh to allow the UPM solution to apply the user integrations.</span></span> <span data-ttu-id="273ab-252">发布/刷新完成后，它将退出。</span><span class="sxs-lookup"><span data-stu-id="273ab-252">It will exit once the publishing/refresh is complete.</span></span>

**<span data-ttu-id="273ab-253">用户集成</span><span class="sxs-lookup"><span data-stu-id="273ab-253">User Integrations</span></span>**

<span data-ttu-id="273ab-254">注册表-HKEY \ _CURRENT \ _USER</span><span class="sxs-lookup"><span data-stu-id="273ab-254">Registry – HKEY\_CURRENT\_USER</span></span>

-   <span data-ttu-id="273ab-255">Path-Software\\Classes</span><span class="sxs-lookup"><span data-stu-id="273ab-255">Path - Software\\Classes</span></span>

    <span data-ttu-id="273ab-256">排除：本地设置、ActivatableClasses、AppX \ \*</span><span class="sxs-lookup"><span data-stu-id="273ab-256">Exclude: Local Settings, ActivatableClasses, AppX\*</span></span>

-   <span data-ttu-id="273ab-257">Path-Software\\Microsoft\\AppV</span><span class="sxs-lookup"><span data-stu-id="273ab-257">Path - Software\\Microsoft\\AppV</span></span>

-   <span data-ttu-id="273ab-258">Path-Software\\Microsoft\\Windows\\CurrentVersion\\App 路径</span><span class="sxs-lookup"><span data-stu-id="273ab-258">Path- Software\\Microsoft\\Windows\\CurrentVersion\\App Paths</span></span>

**<span data-ttu-id="273ab-259">文件位置</span><span class="sxs-lookup"><span data-stu-id="273ab-259">File Locations</span></span>**

-   <span data-ttu-id="273ab-260">Root-"环境变量" APPDATA</span><span class="sxs-lookup"><span data-stu-id="273ab-260">Root – “Environment Variable” APPDATA</span></span>

    <span data-ttu-id="273ab-261">Path-Microsoft\\AppV\\Client\\Catalog</span><span class="sxs-lookup"><span data-stu-id="273ab-261">Path – Microsoft\\AppV\\Client\\Catalog</span></span>

-   <span data-ttu-id="273ab-262">Root-"环境变量" APPDATA</span><span class="sxs-lookup"><span data-stu-id="273ab-262">Root – “Environment Variable” APPDATA</span></span>

    <span data-ttu-id="273ab-263">Path-Microsoft\\AppV\\Client\\Integration</span><span class="sxs-lookup"><span data-stu-id="273ab-263">Path – Microsoft\\AppV\\Client\\Integration</span></span>

-   <span data-ttu-id="273ab-264">Root-"环境变量" APPDATA</span><span class="sxs-lookup"><span data-stu-id="273ab-264">Root – “Environment Variable” APPDATA</span></span>

    <span data-ttu-id="273ab-265">Path-Microsoft\\Windows\\Start Menu\\Programs</span><span class="sxs-lookup"><span data-stu-id="273ab-265">Path - Microsoft\\Windows\\Start Menu\\Programs</span></span>

-   <span data-ttu-id="273ab-266">（保持所有桌面快捷方式，虚拟和非虚拟）</span><span class="sxs-lookup"><span data-stu-id="273ab-266">(To persist all desktop shortcuts, virtual and non-virtual)</span></span>

    <span data-ttu-id="273ab-267">Root-"KnownFolder" {B4BFCC3A-DB2C-424C-B029-7FE99A87C641} FileMask-\ \* .lnk</span><span class="sxs-lookup"><span data-stu-id="273ab-267">Root - “KnownFolder” {B4BFCC3A-DB2C-424C-B029-7FE99A87C641}FileMask - \*.lnk</span></span>

**<span data-ttu-id="273ab-268">Microsoft 用户体验虚拟化（UE-V）</span><span class="sxs-lookup"><span data-stu-id="273ab-268">Microsoft User Experience Virtualization (UE-V)</span></span>**

<span data-ttu-id="273ab-269">此外，我们建议使用 Microsoft 用户体验虚拟化（UE-V）捕获和集中特定用户的应用程序设置和 Windows 操作系统设置。</span><span class="sxs-lookup"><span data-stu-id="273ab-269">Additionally, we recommend using Microsoft User Experience Virtualization (UE-V) to capture and centralize application settings and Windows operating system settings for a specific user.</span></span> <span data-ttu-id="273ab-270">然后，这些设置将应用于用户访问的不同计算机，包括桌面计算机、便携式计算机和虚拟桌面基础结构（VDI）会话。</span><span class="sxs-lookup"><span data-stu-id="273ab-270">These settings are then applied to the different computers that are accessed by the user, including desktop computers, laptop computers, and virtual desktop infrastructure (VDI) sessions.</span></span>

<span data-ttu-id="273ab-271">有关详细信息，请参阅[用户体验虚拟化 1.0](https://technet.microsoft.com/library/jj680015.aspx)和[与 Ue-v 模板库共享设置位置模板](https://technet.microsoft.com/library/jj679972.aspx)的入门。</span><span class="sxs-lookup"><span data-stu-id="273ab-271">For more information see [Getting Started With User Experience Virtualization 1.0](https://technet.microsoft.com/library/jj680015.aspx) and [Sharing Settings Location Templates with the UE-V Template Gallery](https://technet.microsoft.com/library/jj679972.aspx).</span></span>

### <a href="" id="bkmk-uewt"></a><span data-ttu-id="273ab-272">用户体验指导-通过</span><span class="sxs-lookup"><span data-stu-id="273ab-272">User Experience Walk-through</span></span>

<span data-ttu-id="273ab-273">下面是 App-v 和 UPM 操作的分步指导，以及用户应期望的预期效果。</span><span class="sxs-lookup"><span data-stu-id="273ab-273">This following is a step-by-step walk-through of the App-V and UPM operations and the expectations users should expect.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="273ab-274">已针对性能进行优化</span><span class="sxs-lookup"><span data-stu-id="273ab-274">Optimized for Performance</span></span></th>
<th align="left"><span data-ttu-id="273ab-275">已针对存储优化</span><span class="sxs-lookup"><span data-stu-id="273ab-275">Optimized for Storage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="273ab-276">在 VDI/RDSH 环境中实现此方法后，在首次登录时，</span><span class="sxs-lookup"><span data-stu-id="273ab-276">After implementing this approach in the VDI/RDSH environment, on first login,</span></span></p>
<ul>
<li><p><span data-ttu-id="273ab-277">工序将启动用户发布/刷新。</span><span class="sxs-lookup"><span data-stu-id="273ab-277">(Operation) A user-publishing/refresh is initiated.</span></span> <span data-ttu-id="273ab-278">预计如果这是用户第一次发布虚拟应用程序（例如，非永久性），这将占用发布/刷新的常规持续时间。</span><span class="sxs-lookup"><span data-stu-id="273ab-278">(Expectation) If this is the first time a user has published virtual applications (e.g. non-persistent), this will take the usual duration of a publishing/refresh.</span></span></p></li>
<li><p><span data-ttu-id="273ab-279">工序发布/刷新后，UPM 解决方案捕获用户集成。</span><span class="sxs-lookup"><span data-stu-id="273ab-279">(Operation) After the publishing/refresh, the UPM solution captures the user integrations.</span></span> <span data-ttu-id="273ab-280">预计根据 UPM 解决方案的配置方式，这可能会作为注销过程的一部分出现。</span><span class="sxs-lookup"><span data-stu-id="273ab-280">(Expectation) Depending on how the UPM solution is configured, this may occur as part of the logoff process.</span></span> <span data-ttu-id="273ab-281">这将产生与保持用户状态相同/类似的开销。</span><span class="sxs-lookup"><span data-stu-id="273ab-281">This will incur the same/similar overhead as persisting the user state.</span></span></p></li>
</ul>
<p><span data-ttu-id="273ab-282">在后续登录中：</span><span class="sxs-lookup"><span data-stu-id="273ab-282">On subsequent logins:</span></span></p>
<ul>
<li><p><span data-ttu-id="273ab-283">工序UPM 解决方案在发布/刷新之前将用户集成到系统。</span><span class="sxs-lookup"><span data-stu-id="273ab-283">(Operation) UPM solution applies the user integrations to the system prior to publishing/refresh.</span></span></p>
<p><span data-ttu-id="273ab-284">预计桌面或 "开始" 菜单中将显示快捷方式，该快捷方式将立即工作。</span><span class="sxs-lookup"><span data-stu-id="273ab-284">(Expectation) There will be shortcuts present on the desktop, or in the start menu, which work immediately.</span></span> <span data-ttu-id="273ab-285">发布/刷新完成（即程序包权利更改）时，某些情况可能会消失。</span><span class="sxs-lookup"><span data-stu-id="273ab-285">When the publishing/refresh completes (i.e., package entitlements change), some may go away.</span></span></p></li>
<li><p><span data-ttu-id="273ab-286">工序发布/刷新将处理用户包权利中的更改的取消发布和发布操作。</span><span class="sxs-lookup"><span data-stu-id="273ab-286">(Operation) Publishing/refresh will process un-publish and publish operations for changes in user package entitlements.</span></span> <span data-ttu-id="273ab-287">预计如果没有权利更改，publishing1 将在几秒钟内完成。</span><span class="sxs-lookup"><span data-stu-id="273ab-287">(Expectation) If there are no entitlement changes, publishing1 will complete in seconds.</span></span> <span data-ttu-id="273ab-288">否则，发布/刷新将相对于虚拟应用程序的数量和复杂性而增加</span><span class="sxs-lookup"><span data-stu-id="273ab-288">Otherwise, the publishing/refresh will increase relative to the number and complexity\* of virtual applications</span></span></p></li>
<li><p><span data-ttu-id="273ab-289">工序UPM 解决方案将在注销时再次捕获用户集成。</span><span class="sxs-lookup"><span data-stu-id="273ab-289">(Operation) UPM solution will capture user integrations again at logoff.</span></span> <span data-ttu-id="273ab-290">预计与上一节相同。</span><span class="sxs-lookup"><span data-stu-id="273ab-290">(Expectation) Same as previous.</span></span></p></li>
</ul>
<p><span data-ttu-id="273ab-291">¹发布操作（ <strong> Publish-AppVClientPackage </strong> ）将条目添加到用户目录、将权利映射到用户、标识本地存储以及完成任何集成步骤。</span><span class="sxs-lookup"><span data-stu-id="273ab-291">¹ The publishing operation (<strong>Publish-AppVClientPackage</strong>) adds entries to the user catalog, maps entitlement to the user, identifies the local store, and finishes by completing any integration steps.</span></span></p></td>
<td align="left"><p><span data-ttu-id="273ab-292">在 VDI/RDSH 环境中实现此方法后，在首次登录时，</span><span class="sxs-lookup"><span data-stu-id="273ab-292">After implementing this approach in the VDI/RDSH environment, on first login,</span></span></p>
<ul>
<li><p><span data-ttu-id="273ab-293">工序将启动用户发布/刷新。</span><span class="sxs-lookup"><span data-stu-id="273ab-293">(Operation) A user-publishing/refresh is initiated.</span></span> <span data-ttu-id="273ab-294">预计</span><span class="sxs-lookup"><span data-stu-id="273ab-294">(Expectation)</span></span></p>
<ul>
<li><p><span data-ttu-id="273ab-295">如果这是用户第一次发布虚拟应用程序（例如，非永久性），这将占用发布/刷新的常规持续时间。</span><span class="sxs-lookup"><span data-stu-id="273ab-295">If this is the first time a user has published virtual applications (e.g., non-persistent), this will take the usual duration of a publishing/refresh.</span></span></p></li>
<li><p><span data-ttu-id="273ab-296">首次登录时，将通过预配置程序包（添加/刷新）影响首次登录和后续登录。</span><span class="sxs-lookup"><span data-stu-id="273ab-296">First and subsequent logins will be impacted by pre-configuring of packages (add/refresh).</span></span></p>
<p></p></li>
</ul></li>
<li><p><span data-ttu-id="273ab-297">工序发布/刷新后，UPM 解决方案捕获用户集成。</span><span class="sxs-lookup"><span data-stu-id="273ab-297">(Operation) After the publishing/refresh, the UPM solution captures the user integrations.</span></span> <span data-ttu-id="273ab-298">预计根据 UPM 解决方案的配置方式，这可能会作为注销过程的一部分出现。</span><span class="sxs-lookup"><span data-stu-id="273ab-298">(Expectation) Depending on how the UPM solution is configured, this may occur as part of the logoff process.</span></span> <span data-ttu-id="273ab-299">这将产生与保持用户状态相同/类似的开销</span><span class="sxs-lookup"><span data-stu-id="273ab-299">This will incur the same/similar overhead as persisting the user state</span></span></p></li>
</ul>
<p><span data-ttu-id="273ab-300">在后续登录中：</span><span class="sxs-lookup"><span data-stu-id="273ab-300">On subsequent logins:</span></span></p>
<ul>
<li><p><span data-ttu-id="273ab-301">工序UPM 解决方案在发布/刷新之前将用户集成到系统。</span><span class="sxs-lookup"><span data-stu-id="273ab-301">(Operation) UPM solution applies the user integrations to the system prior to publishing/refresh.</span></span></p></li>
<li><p><span data-ttu-id="273ab-302">工序添加/刷新必须预配置所有用户目标应用程序。</span><span class="sxs-lookup"><span data-stu-id="273ab-302">(Operation) Add/refresh must pre-configure all user targeted applications.</span></span> <span data-ttu-id="273ab-303">预计</span><span class="sxs-lookup"><span data-stu-id="273ab-303">(Expectation)</span></span></p>
<ul>
<li><p><span data-ttu-id="273ab-304">这可能会显著增加应用程序可用性的时间（以10秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="273ab-304">This may increase the time to application availability significantly (on the order of 10’s of seconds).</span></span></p></li>
<li><p><span data-ttu-id="273ab-305">这将增加相对于虚拟应用程序的数量和复杂性 \* 的发布刷新时间。</span><span class="sxs-lookup"><span data-stu-id="273ab-305">This will increase the publishing refresh time relative to the number and complexity\* of virtual applications.</span></span></p>
<p></p></li>
</ul></li>
<li><p><span data-ttu-id="273ab-306">工序发布/刷新将处理对用户程序包权利所做的更改的取消发布和发布操作。</span><span class="sxs-lookup"><span data-stu-id="273ab-306">(Operation) Publishing/refresh will process un-publish and publish operations for changes to user package entitlements.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>



<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="273ab-307">输出</span><span class="sxs-lookup"><span data-stu-id="273ab-307">Outcome</span></span></th>
<th align="left"><span data-ttu-id="273ab-308">输出</span><span class="sxs-lookup"><span data-stu-id="273ab-308">Outcome</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="273ab-309">由于用户集成已完全保留，因此不会有任何工作，例如，用于完成发布/刷新的集成。</span><span class="sxs-lookup"><span data-stu-id="273ab-309">Because the user integrations are entirely preserved, there will be no work for example, integration for the publishing/refresh to complete.</span></span> <span data-ttu-id="273ab-310">所有虚拟应用程序将在登录后的几秒钟内可用。</span><span class="sxs-lookup"><span data-stu-id="273ab-310">All virtual applications will be available within seconds of login.</span></span></p></li>
<li><p><span data-ttu-id="273ab-311">发布/刷新将处理对用户的更改，这些用户为用户授予了影响体验的虚拟应用程序。</span><span class="sxs-lookup"><span data-stu-id="273ab-311">The publishing/refresh will process changes to the users entitled virtual applications which impacts the experience.</span></span></p></li>
</ul></td>
<td align="left"><p><span data-ttu-id="273ab-312">由于添加/刷新必须将所有虚拟应用程序重新配置到 VM，因此将扩展每个登录上的发布刷新时间。</span><span class="sxs-lookup"><span data-stu-id="273ab-312">Because the add/refresh must re-configure all the virtual applications to the VM, the publishing refresh time on every login will be extended.</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-plc"></a><span data-ttu-id="273ab-313">对包生命周期的影响</span><span class="sxs-lookup"><span data-stu-id="273ab-313">Impact to Package Life Cycle</span></span>

<span data-ttu-id="273ab-314">升级程序包是程序包生命周期的一个重要方面。</span><span class="sxs-lookup"><span data-stu-id="273ab-314">Upgrading a package is a crucial aspect of the package lifecycle.</span></span> <span data-ttu-id="273ab-315">为帮助保证用户能够访问相应的已升级（已发布）或降级（未发布）的虚拟应用程序包，建议你更新基本映像以反映这些更改。</span><span class="sxs-lookup"><span data-stu-id="273ab-315">To help guarantee users have access to the appropriate upgraded (published) or downgraded (un-published) virtual application packages, it is recommended you update the base image to reflect these changes.</span></span> <span data-ttu-id="273ab-316">若要了解查看以下部分的原因，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="273ab-316">To understand why review the following section:</span></span>

<span data-ttu-id="273ab-317">App-v 5.0 SP2 引入了挂起状态的概念。</span><span class="sxs-lookup"><span data-stu-id="273ab-317">App-V 5.0 SP2 introduced the concept of pending states.</span></span> <span data-ttu-id="273ab-318">过去，</span><span class="sxs-lookup"><span data-stu-id="273ab-318">In the past,</span></span>

-   <span data-ttu-id="273ab-319">如果管理员更改了权利或创建了程序包的新版本（已升级），并且在发布/刷新该程序包正在使用的过程中，则分别取消发布或发布操作将失败。</span><span class="sxs-lookup"><span data-stu-id="273ab-319">If an administrator changed entitlements or created a new version of a package (upgraded) and during a publishing/refresh that package was in-use, the un-publish or publish operation, respectively, would fail.</span></span>

-   <span data-ttu-id="273ab-320">现在，如果程序包处于使用中，该操作将处于暂停。</span><span class="sxs-lookup"><span data-stu-id="273ab-320">Now, if a package is in-use the operation will be pended.</span></span> <span data-ttu-id="273ab-321">将在服务重启时或在发出另一个发布或取消发布命令时处理未发布和发布挂起的操作。</span><span class="sxs-lookup"><span data-stu-id="273ab-321">The un-publish and publish-pend operations will be processed on service restart or if another publish or un-publish command is issued.</span></span> <span data-ttu-id="273ab-322">在后一种情况下，如果虚拟应用程序在其他情况下处于使用中，虚拟应用程序将保持挂起状态。</span><span class="sxs-lookup"><span data-stu-id="273ab-322">In the latter case, if the virtual application is in-use otherwise, the virtual application will remain in a pending state.</span></span> <span data-ttu-id="273ab-323">对于全局发布的程序包，通常需要重启（或服务重启）。</span><span class="sxs-lookup"><span data-stu-id="273ab-323">For globally published packages, a restart (or service restart) often needed.</span></span>

<span data-ttu-id="273ab-324">在非持久性环境中，将不可能处理这些暂停的操作。</span><span class="sxs-lookup"><span data-stu-id="273ab-324">In a non-persistent environment, it is unlikely these pended operations will be processed.</span></span> <span data-ttu-id="273ab-325">已暂停的操作（例如任务）在**HKEY \ _CURRENT \ _USER**  \\  **软件**  \\  **Microsoft**  \\  **AppV**  \\  **client**  \\  **PendingTasks**中捕获。</span><span class="sxs-lookup"><span data-stu-id="273ab-325">The pended operations, for example tasks are captured under **HKEY\_CURRENT\_USER** \\ **Software** \\ **Microsoft** \\ **AppV** \\ **Client** \\ **PendingTasks**.</span></span> <span data-ttu-id="273ab-326">虽然此位置由 UPM 解决方案保留，但如果未在登录之前应用于环境，则不会对其进行处理。</span><span class="sxs-lookup"><span data-stu-id="273ab-326">Although this location is persisted by the UPM solution, if it is not applied to the environment prior to log on, it will not be processed.</span></span>

### <a href="" id="bkmk-evdi"></a><span data-ttu-id="273ab-327">通过性能优化优化增强 VDI 体验</span><span class="sxs-lookup"><span data-stu-id="273ab-327">Enhancing the VDI Experience through Performance Optimization Tuning</span></span>

<span data-ttu-id="273ab-328">以下部分包含有关 Microsoft 文档和下载的信息的列表，这些信息在优化环境以提高性能时可能很有用。</span><span class="sxs-lookup"><span data-stu-id="273ab-328">The following section contains lists with information about Microsoft documentation and downloads that may be useful when optimizing your environment for performance.</span></span>

**<span data-ttu-id="273ab-329">.NET NGEN 博客和脚本（强烈建议）</span><span class="sxs-lookup"><span data-stu-id="273ab-329">.NET NGEN Blog and Script (Highly Recommended)</span></span>**

<span data-ttu-id="273ab-330">关于 NGEN 技术</span><span class="sxs-lookup"><span data-stu-id="273ab-330">About NGEN technology</span></span>

-   [<span data-ttu-id="273ab-331">如何加快 NGEN 优化</span><span class="sxs-lookup"><span data-stu-id="273ab-331">How to speed up NGEN optimization</span></span>](https://blogs.msdn.com/b/dotnet/archive/2013/08/06/wondering-why-mscorsvw-exe-has-high-cpu-usage-you-can-speed-it-up.aspx)

-   [<span data-ttu-id="273ab-332">脚本</span><span class="sxs-lookup"><span data-stu-id="273ab-332">Script</span></span>](https://aka.ms/DrainNGenQueue)

**<span data-ttu-id="273ab-333">Windows Server 和服务器角色</span><span class="sxs-lookup"><span data-stu-id="273ab-333">Windows Server and Server Roles</span></span>**

<span data-ttu-id="273ab-334">的服务器性能优化指南</span><span class="sxs-lookup"><span data-stu-id="273ab-334">Server Performance Tuning Guidelines for</span></span>

-   [<span data-ttu-id="273ab-335">Microsoft Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="273ab-335">Microsoft Windows Server 2012 R2</span></span>](https://msdn.microsoft.com/library/windows/hardware/dn529133.aspx)

-   [<span data-ttu-id="273ab-336">Microsoft Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="273ab-336">Microsoft Windows Server 2012</span></span>](https://download.microsoft.com/download/0/0/B/00BE76AF-D340-4759-8ECD-C80BC53B6231/performance-tuning-guidelines-windows-server-2012.docx)

-   [<span data-ttu-id="273ab-337">Microsoft Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="273ab-337">Microsoft Windows Server 2008 R2</span></span>](https://download.microsoft.com/download/6/B/2/6B2EBD3A-302E-4553-AC00-9885BBF31E21/Perf-tun-srv-R2.docx)

**<span data-ttu-id="273ab-338">服务器角色</span><span class="sxs-lookup"><span data-stu-id="273ab-338">Server Roles</span></span>**

-   [<span data-ttu-id="273ab-339">远程桌面虚拟化主机</span><span class="sxs-lookup"><span data-stu-id="273ab-339">Remote Desktop Virtualization Host</span></span>](https://msdn.microsoft.com/library/windows/hardware/dn567643.aspx)

-   [<span data-ttu-id="273ab-340">远程桌面会话主机</span><span class="sxs-lookup"><span data-stu-id="273ab-340">Remote Desktop Session Host</span></span>](https://msdn.microsoft.com/library/windows/hardware/dn567648.aspx)

-   [<span data-ttu-id="273ab-341">IIS 相关性： App-v 管理、发布和报告 Web 服务</span><span class="sxs-lookup"><span data-stu-id="273ab-341">IIS Relevance: App-V Management, Publishing, Reporting Web Services</span></span>](https://msdn.microsoft.com/library/windows/hardware/dn567678.aspx)

-   [<span data-ttu-id="273ab-342">文件服务器（SMB）相关性：如果用于 SCS 模式中的 App-v 内容存储和传递</span><span class="sxs-lookup"><span data-stu-id="273ab-342">File Server (SMB) Relevance: If used for App-V Content Storage and Delivery in SCS Mode</span></span>](https://technet.microsoft.com/library/jj134210.aspx)

**<span data-ttu-id="273ab-343">Windows 客户端（来宾 OS）性能优化指南</span><span class="sxs-lookup"><span data-stu-id="273ab-343">Windows Client (Guest OS) Performance Tuning Guidance</span></span>**

-   [<span data-ttu-id="273ab-344">Microsoft Windows 7</span><span class="sxs-lookup"><span data-stu-id="273ab-344">Microsoft Windows 7</span></span>](https://download.microsoft.com/download/E/5/7/E5783D68-160B-4366-8387-114FC3E45EB4/Performance Tuning Guidelines for Windows 7 Desktop Virtualization v1.9.docx)

-   [<span data-ttu-id="273ab-345">优化脚本：（由 Microsoft 支持人员提供）</span><span class="sxs-lookup"><span data-stu-id="273ab-345">Optimization Script: (Provided by Microsoft Support)</span></span>](https://blogs.technet.com/b/jeff_stokes/archive/2012/10/15/the-microsoft-premier-field-engineer-pfe-view-on-virtual-desktop-vdi-density.aspx)

-   [<span data-ttu-id="273ab-346">Microsoft Windows 8</span><span class="sxs-lookup"><span data-stu-id="273ab-346">Microsoft Windows 8</span></span>](https://download.microsoft.com/download/6/0/1/601D7797-A063-4FA7-A2E5-74519B57C2B4/Windows_8_VDI_Image_Client_Tuning_Guide.pdf)

-   [<span data-ttu-id="273ab-347">优化脚本：（由 Microsoft 支持人员提供）</span><span class="sxs-lookup"><span data-stu-id="273ab-347">Optimization Script: (Provided by Microsoft Support)</span></span>](https://blogs.technet.com/b/jeff_stokes/archive/2013/04/09/hot-off-the-presses-get-it-now-the-windows-8-vdi-optimization-script-courtesy-of-pfe.aspx)

## <span data-ttu-id="273ab-348">为发布性能优化程序包的先后顺序步骤</span><span class="sxs-lookup"><span data-stu-id="273ab-348">Sequencing Steps to Optimize Packages for Publishing Performance</span></span>


<span data-ttu-id="273ab-349">几种应用程序-V 功能有利于新方案或支持新的客户部署方案。</span><span class="sxs-lookup"><span data-stu-id="273ab-349">Several App-V features facilitate new scenarios or enable new customer deployment scenarios.</span></span> <span data-ttu-id="273ab-350">以下功能会影响发布和启动操作的性能。</span><span class="sxs-lookup"><span data-stu-id="273ab-350">These following features can impact the performance of the publishing and launch operations.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="273ab-351">步骤</span><span class="sxs-lookup"><span data-stu-id="273ab-351">Step</span></span></th>
<th align="left"><span data-ttu-id="273ab-352">注意事项</span><span class="sxs-lookup"><span data-stu-id="273ab-352">Consideration</span></span></th>
<th align="left"><span data-ttu-id="273ab-353">权益</span><span class="sxs-lookup"><span data-stu-id="273ab-353">Benefits</span></span></th>
<th align="left"><span data-ttu-id="273ab-354">取舍</span><span class="sxs-lookup"><span data-stu-id="273ab-354">Tradeoffs</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="273ab-355">无功能块1（FB1，也称为主要的 FB）</span><span class="sxs-lookup"><span data-stu-id="273ab-355">No Feature Block 1 (FB1, also known as Primary FB)</span></span></p></td>
<td align="left"><p><span data-ttu-id="273ab-356">无 FB1 意味着应用程序将立即启动并流故障（应用程序在启动时需要文件、DLL 且必须在网络上拉下）。如果存在网络限制，FB1 将：</span><span class="sxs-lookup"><span data-stu-id="273ab-356">No FB1 means the application will launch immediately and stream fault (application requires file, DLL and must pull down over the network) during launch.If there are network limitations, FB1 will:</span></span></p>
<ul>
<li><p><span data-ttu-id="273ab-357">减少首次启动应用程序时使用的流故障数和网络带宽。</span><span class="sxs-lookup"><span data-stu-id="273ab-357">Reduce the number of stream faults and network bandwidth used when you launch an application for the first time.</span></span></p></li>
<li><p><span data-ttu-id="273ab-358">延迟启动，直到已对整个 FB1 进行流式处理。</span><span class="sxs-lookup"><span data-stu-id="273ab-358">Delay launch until the entire FB1 has been streamed.</span></span></p></li>
</ul></td>
<td align="left"><p><span data-ttu-id="273ab-359">流错误减少了启动时间。</span><span class="sxs-lookup"><span data-stu-id="273ab-359">Stream faulting decreases the launch time.</span></span></p></td>
<td align="left"><p><span data-ttu-id="273ab-360">已配置 FB1 的虚拟应用程序包将需要重新排序。</span><span class="sxs-lookup"><span data-stu-id="273ab-360">Virtual application packages with FB1 configured will need to be re-sequenced.</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="273ab-361">删除 FB1</span><span class="sxs-lookup"><span data-stu-id="273ab-361">Removing FB1</span></span>

<span data-ttu-id="273ab-362">删除 FB1 不需要原始应用程序安装程序。</span><span class="sxs-lookup"><span data-stu-id="273ab-362">Removing FB1 does not require the original application installer.</span></span> <span data-ttu-id="273ab-363">完成以下步骤后，建议将运行 sequencer 的计算机还原为干净的快照。</span><span class="sxs-lookup"><span data-stu-id="273ab-363">After completing the following steps, it is suggested that you revert the computer running the sequencer to a clean snapshot.</span></span>

<span data-ttu-id="273ab-364">**SEQUENCER UI** -创建新的虚拟应用程序包。</span><span class="sxs-lookup"><span data-stu-id="273ab-364">**Sequencer UI** - Create a New Virtual Application Package.</span></span>

1.  <span data-ttu-id="273ab-365">完成对自定义流的排序步骤 &gt; 。</span><span class="sxs-lookup"><span data-stu-id="273ab-365">Complete the sequencing steps up to Customize -&gt; Streaming.</span></span>

2.  <span data-ttu-id="273ab-366">在 "流" 步骤中，不要选择 "**通过慢速或不可靠的网络优化程序包以进行部署**"。</span><span class="sxs-lookup"><span data-stu-id="273ab-366">At the Streaming step, do not select **Optimize the package for deployment over slow or unreliable network**.</span></span>

3.  <span data-ttu-id="273ab-367">如果需要，请转到**目标操作系统**。</span><span class="sxs-lookup"><span data-stu-id="273ab-367">If desired, move on to **Target OS**.</span></span>

**<span data-ttu-id="273ab-368">修改现有虚拟应用程序包</span><span class="sxs-lookup"><span data-stu-id="273ab-368">Modify an Existing Virtual Application Package</span></span>**

1.  <span data-ttu-id="273ab-369">完成对流的排序步骤。</span><span class="sxs-lookup"><span data-stu-id="273ab-369">Complete the sequencing steps up to Streaming.</span></span>

2.  <span data-ttu-id="273ab-370">不要选择**通过慢速或不可靠的网络优化程序包以进行部署**。</span><span class="sxs-lookup"><span data-stu-id="273ab-370">Do not select **Optimize the package for deployment over a slow or unreliable network**.</span></span>

3.  <span data-ttu-id="273ab-371">移动以**创建程序包**。</span><span class="sxs-lookup"><span data-stu-id="273ab-371">Move to **Create Package**.</span></span>

<span data-ttu-id="273ab-372">**PowerShell** -更新现有虚拟应用程序包。</span><span class="sxs-lookup"><span data-stu-id="273ab-372">**PowerShell** - Update an Existing Virtual Application Package.</span></span>

1.  <span data-ttu-id="273ab-373">打开提升的 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="273ab-373">Open an elevated PowerShell session.</span></span>

2.  <span data-ttu-id="273ab-374">Import-module **appvsequencer**。</span><span class="sxs-lookup"><span data-stu-id="273ab-374">Import-module **appvsequencer**.</span></span>

3.  <span data-ttu-id="273ab-375">**Update-AppvSequencerPackage**  - **AppvPackageFilePath**</span><span class="sxs-lookup"><span data-stu-id="273ab-375">**Update-AppvSequencerPackage** - **AppvPackageFilePath**</span></span>

    <span data-ttu-id="273ab-376">"C:\\Packages\\MyPackage.appv"-安装程序</span><span class="sxs-lookup"><span data-stu-id="273ab-376">"C:\\Packages\\MyPackage.appv" -Installer</span></span>

    <span data-ttu-id="273ab-377">"C:\\PackageInstall\\PackageUpgrade.exe empty.exe"-OutputPath</span><span class="sxs-lookup"><span data-stu-id="273ab-377">"C:\\PackageInstall\\PackageUpgrade.exe empty.exe" -OutputPath</span></span>

    <span data-ttu-id="273ab-378">"C:\\UpgradedPackages"</span><span class="sxs-lookup"><span data-stu-id="273ab-378">"C:\\UpgradedPackages"</span></span>

    **<span data-ttu-id="273ab-379">注意</span><span class="sxs-lookup"><span data-stu-id="273ab-379">Note</span></span>**  
    <span data-ttu-id="273ab-380">此 cmdlet 需要可执行文件（.exe）或批处理文件（.bat）。</span><span class="sxs-lookup"><span data-stu-id="273ab-380">This cmdlet requires an executable (.exe) or batch file (.bat).</span></span> <span data-ttu-id="273ab-381">必须提供空（不执行任何操作）可执行文件或批处理文件。</span><span class="sxs-lookup"><span data-stu-id="273ab-381">You must provide an empty (does nothing) executable or batch file.</span></span>



<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="273ab-382">步骤</span><span class="sxs-lookup"><span data-stu-id="273ab-382">Step</span></span></th>
<th align="left"><span data-ttu-id="273ab-383">注意事项</span><span class="sxs-lookup"><span data-stu-id="273ab-383">Considerations</span></span></th>
<th align="left"><span data-ttu-id="273ab-384">权益</span><span class="sxs-lookup"><span data-stu-id="273ab-384">Benefits</span></span></th>
<th align="left"><span data-ttu-id="273ab-385">取舍</span><span class="sxs-lookup"><span data-stu-id="273ab-385">Tradeoffs</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="273ab-386">发布时无 SXS 安装（预安装 SxS 程序集）</span><span class="sxs-lookup"><span data-stu-id="273ab-386">No SXS Install at Publish (Pre-Install SxS assemblies)</span></span></p></td>
<td align="left"><p><span data-ttu-id="273ab-387">不需要对虚拟应用程序包进行重新排序。</span><span class="sxs-lookup"><span data-stu-id="273ab-387">Virtual Application packages do not need to be re-sequenced.</span></span> <span data-ttu-id="273ab-388">SxS 程序集可以保留在虚拟应用程序包中。</span><span class="sxs-lookup"><span data-stu-id="273ab-388">SxS Assemblies can remain in the virtual application package.</span></span></p></td>
<td align="left"><p><span data-ttu-id="273ab-389">将不会在发布时安装 SxS 程序集依赖项。</span><span class="sxs-lookup"><span data-stu-id="273ab-389">The SxS Assembly dependencies will not install at publishing time.</span></span></p></td>
<td align="left"><p><span data-ttu-id="273ab-390">必须预安装 SxS 程序集依赖项。</span><span class="sxs-lookup"><span data-stu-id="273ab-390">SxS Assembly dependencies must be pre-installed.</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="273ab-391">在 sequencer 上创建新的虚拟应用程序包</span><span class="sxs-lookup"><span data-stu-id="273ab-391">Creating a new virtual application package on the sequencer</span></span>

<span data-ttu-id="273ab-392">如果在排序器监视期间，将在应用程序的安装过程中安装 SxS 程序集（如 VC + + 运行时），将自动检测并包含在程序包中的 SxS 程序集。</span><span class="sxs-lookup"><span data-stu-id="273ab-392">If, during sequencer monitoring, an SxS Assembly (such as a VC++ Runtime) is installed as part of an application’s installation, SxS Assembly will be automatically detected and included in the package.</span></span> <span data-ttu-id="273ab-393">管理员将收到通知，并且将具有排除 SxS 程序集的选项。</span><span class="sxs-lookup"><span data-stu-id="273ab-393">The administrator will be notified and will have the option to exclude the SxS Assembly.</span></span>

<span data-ttu-id="273ab-394">**客户端**：</span><span class="sxs-lookup"><span data-stu-id="273ab-394">**Client Side**:</span></span>

<span data-ttu-id="273ab-395">当发布虚拟应用程序包时，App-v 客户端将检测是否已安装了所需的 SxS 依赖关系。</span><span class="sxs-lookup"><span data-stu-id="273ab-395">When publishing a virtual application package, the App-V Client will detect if a required SxS dependency is already installed.</span></span> <span data-ttu-id="273ab-396">如果依赖项在计算机上不可用，并且它包含在程序包中，则是传统的 Windows Installer （.**msi**）将启动 SxS 程序集的安装。</span><span class="sxs-lookup"><span data-stu-id="273ab-396">If the dependency is unavailable on the computer and it is included in the package, a traditional Windows Installer (.**msi**) installation of the SxS assembly will be initiated.</span></span> <span data-ttu-id="273ab-397">如之前所述，只需在运行客户端的计算机上安装依赖项，以确保不会发生 Windows Installer （.msi）安装。</span><span class="sxs-lookup"><span data-stu-id="273ab-397">As previously documented, simply install the dependency on the computer running the client to ensure that the Windows Installer (.msi) installation will not occur.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="273ab-398">步骤</span><span class="sxs-lookup"><span data-stu-id="273ab-398">Step</span></span></th>
<th align="left"><span data-ttu-id="273ab-399">注意事项</span><span class="sxs-lookup"><span data-stu-id="273ab-399">Considerations</span></span></th>
<th align="left"><span data-ttu-id="273ab-400">权益</span><span class="sxs-lookup"><span data-stu-id="273ab-400">Benefits</span></span></th>
<th align="left"><span data-ttu-id="273ab-401">取舍</span><span class="sxs-lookup"><span data-stu-id="273ab-401">Tradeoffs</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="273ab-402">有选择地使用动态配置文件</span><span class="sxs-lookup"><span data-stu-id="273ab-402">Selectively Employ Dynamic Configuration files</span></span></p></td>
<td align="left"><p><span data-ttu-id="273ab-403">App-v 5.1 客户端必须分析和处理这些动态配置文件。</span><span class="sxs-lookup"><span data-stu-id="273ab-403">The App-V 5.1 client must parse and process these Dynamic Configuration files.</span></span></p>
<p><span data-ttu-id="273ab-404">关注文件的大小和复杂性（脚本执行、VREG 包含/排除）。</span><span class="sxs-lookup"><span data-stu-id="273ab-404">Be conscious of size and complexity (script execution, VREG inclusions/exclusions) of the file.</span></span></p>
<p><span data-ttu-id="273ab-405">许多虚拟应用程序包可能已经具有特定于用户或计算机的动态配置文件。</span><span class="sxs-lookup"><span data-stu-id="273ab-405">Numerous virtual application packages may already have User- or computer–specific dynamic configurations files.</span></span></p></td>
<td align="left"><p><span data-ttu-id="273ab-406">如果有选择性地使用这些文件或根本不使用，则发布时间将会提高。</span><span class="sxs-lookup"><span data-stu-id="273ab-406">Publishing times will improve if these files are used selectively or not at all.</span></span></p></td>
<td align="left"><p><span data-ttu-id="273ab-407">虚拟应用程序包需要单独配置或通过 App-v 服务器管理控制台进行配置以删除关联的动态配置文件。</span><span class="sxs-lookup"><span data-stu-id="273ab-407">Virtual application packages would need to be reconfigured individually or via the App-V server management console to remove associated Dynamic Configuration files.</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="273ab-408">使用 Powershell 禁用动态配置</span><span class="sxs-lookup"><span data-stu-id="273ab-408">Disabling a Dynamic Configuration using Powershell</span></span>

-   <span data-ttu-id="273ab-409">对于已发布的程序包，你可以 `Set-AppVClientPackage –Name Myapp –Path c:\Packages\Apps\MyApp.appv` 使用</span><span class="sxs-lookup"><span data-stu-id="273ab-409">For already published packages, you can use `Set-AppVClientPackage –Name Myapp –Path c:\Packages\Apps\MyApp.appv` without</span></span>

    <span data-ttu-id="273ab-410">**-DynamicDeploymentConfiguration**参数</span><span class="sxs-lookup"><span data-stu-id="273ab-410">**-DynamicDeploymentConfiguration** parameter</span></span>

-   <span data-ttu-id="273ab-411">同样，如果使用添加新的程序包，请不要 `Add-AppVClientPackage –Path c:\Packages\Apps\MyApp.appv` 使用</span><span class="sxs-lookup"><span data-stu-id="273ab-411">Similarly, when adding new packages using `Add-AppVClientPackage –Path c:\Packages\Apps\MyApp.appv`, do not use the</span></span>

    <span data-ttu-id="273ab-412">**-DynamicDeploymentConfiguration**参数。</span><span class="sxs-lookup"><span data-stu-id="273ab-412">**-DynamicDeploymentConfiguration** parameter.</span></span>

<span data-ttu-id="273ab-413">有关如何应用动态配置的文档，请参阅：</span><span class="sxs-lookup"><span data-stu-id="273ab-413">For documentation on How to Apply a Dynamic Configuration, see:</span></span>

-   [<span data-ttu-id="273ab-414">如何使用 PowerShell 应用用户配置文件</span><span class="sxs-lookup"><span data-stu-id="273ab-414">How to Apply the User Configuration File by Using PowerShell</span></span>](how-to-apply-the-user-configuration-file-by-using-powershell51.md)

-   [<span data-ttu-id="273ab-415">如何使用 PowerShell 应用部署配置文件</span><span class="sxs-lookup"><span data-stu-id="273ab-415">How to Apply the Deployment Configuration File by Using PowerShell</span></span>](how-to-apply-the-deployment-configuration-file-by-using-powershell51.md)

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="273ab-416">步骤</span><span class="sxs-lookup"><span data-stu-id="273ab-416">Step</span></span></th>
<th align="left"><span data-ttu-id="273ab-417">注意事项</span><span class="sxs-lookup"><span data-stu-id="273ab-417">Considerations</span></span></th>
<th align="left"><span data-ttu-id="273ab-418">权益</span><span class="sxs-lookup"><span data-stu-id="273ab-418">Benefits</span></span></th>
<th align="left"><span data-ttu-id="273ab-419">取舍</span><span class="sxs-lookup"><span data-stu-id="273ab-419">Tradeoffs</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="273ab-420">用于在程序包生命周期期间同步脚本执行的帐户。</span><span class="sxs-lookup"><span data-stu-id="273ab-420">Account for Synchronous Script Execution during Package Lifecycle.</span></span></p></td>
<td align="left"><p><span data-ttu-id="273ab-421">如果程序包中嵌入了脚本宣传资料，则 Add （Powershell）可能会显著降低。</span><span class="sxs-lookup"><span data-stu-id="273ab-421">If script collateral is embedded in the package, Add (Powershell) may be significantly slower.</span></span></p>
<p><span data-ttu-id="273ab-422">在虚拟应用程序启动期间（StartVirtualEnvironment、StartProcess）和/或 Add + 发布期间运行脚本将影响在一个或多个这些生命周期操作期间的感知性能。</span><span class="sxs-lookup"><span data-stu-id="273ab-422">Running of scripts during virtual application launch (StartVirtualEnvironment, StartProcess) and/or Add+Publish will impact the perceived performance during one or more of these lifecycle operations.</span></span></p></td>
<td align="left"><p><span data-ttu-id="273ab-423">使用异步（非阻止）脚本可确保生命周期操作高效完成。</span><span class="sxs-lookup"><span data-stu-id="273ab-423">Use of Asynchronous (Non-Blocking) Scripts will ensure that the lifecycle operations complete efficiently.</span></span></p></td>
<td align="left"><p><span data-ttu-id="273ab-424">此步骤需要使用嵌入式脚本辅助包（具有相关联的动态配置文件以及同步引用和运行脚本）的所有虚拟应用程序包的工作知识。</span><span class="sxs-lookup"><span data-stu-id="273ab-424">This step requires working knowledge of all virtual application packages with embedded script collateral, which have associated dynamic configurations files and which reference and run scripts synchronously.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="273ab-425">从程序包中删除无关的虚拟字体。</span><span class="sxs-lookup"><span data-stu-id="273ab-425">Remove Extraneous Virtual Fonts from Package.</span></span></p></td>
<td align="left"><p><span data-ttu-id="273ab-426">应用-V 产品团队调查的大多数应用程序都包含少量的字体，通常少于20。</span><span class="sxs-lookup"><span data-stu-id="273ab-426">The majority of applications investigated by the App-V product team contained a small number of fonts, typically fewer than 20.</span></span></p></td>
<td align="left"><p><span data-ttu-id="273ab-427">虚拟字体影响发布刷新性能。</span><span class="sxs-lookup"><span data-stu-id="273ab-427">Virtual Fonts impact publishing refresh performance.</span></span></p></td>
<td align="left"><p><span data-ttu-id="273ab-428">需要在本地启用/安装所需的字体。</span><span class="sxs-lookup"><span data-stu-id="273ab-428">Desired fonts will need to be enabled/installed natively.</span></span> <span data-ttu-id="273ab-429">有关说明，请参阅安装或卸载字体。</span><span class="sxs-lookup"><span data-stu-id="273ab-429">For instructions, see Install or uninstall fonts.</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="273ab-430">确定程序包中存在的虚拟字体</span><span class="sxs-lookup"><span data-stu-id="273ab-430">Determining what virtual fonts exist in the package</span></span>

-   <span data-ttu-id="273ab-431">制作程序包的副本。</span><span class="sxs-lookup"><span data-stu-id="273ab-431">Make a copy of the package.</span></span>

-   <span data-ttu-id="273ab-432">将程序包 \ _copy 的 appv 重命名为 Package\_copy.zip</span><span class="sxs-lookup"><span data-stu-id="273ab-432">Rename Package\_copy.appv to Package\_copy.zip</span></span>

-   <span data-ttu-id="273ab-433">打开 AppxManifest.xml 并找到下列内容：</span><span class="sxs-lookup"><span data-stu-id="273ab-433">Open AppxManifest.xml and locate the following:</span></span>

    <span data-ttu-id="273ab-434">&lt;appv： Extension Category = "AppV"&gt;</span><span class="sxs-lookup"><span data-stu-id="273ab-434">&lt;appv:Extension Category="AppV.Fonts"&gt;</span></span>

    <span data-ttu-id="273ab-435">&lt;appv：字体&gt;</span><span class="sxs-lookup"><span data-stu-id="273ab-435">&lt;appv:Fonts&gt;</span></span>

    <span data-ttu-id="273ab-436">&lt;appv： Font Path = "\ [{Fonts} \] \\private\\CalibriL.ttf" DelayLoad = "true" &gt; &lt; /Appv： Font&gt;</span><span class="sxs-lookup"><span data-stu-id="273ab-436">&lt;appv:Font Path="\[{Fonts}\]\\private\\CalibriL.ttf" DelayLoad="true"&gt;&lt;/appv:Font&gt;</span></span>

    **<span data-ttu-id="273ab-437">注意</span><span class="sxs-lookup"><span data-stu-id="273ab-437">Note</span></span>**  
    <span data-ttu-id="273ab-438">如果有字体标记为**DelayLoad**，这些字体不会影响首次启动。</span><span class="sxs-lookup"><span data-stu-id="273ab-438">If there are fonts marked as **DelayLoad**, those will not impact first launch.</span></span>



~~~
&lt;/appv:Fonts&gt;
~~~

### <span data-ttu-id="273ab-439">从程序包中排除虚拟字体</span><span class="sxs-lookup"><span data-stu-id="273ab-439">Excluding virtual fonts from the package</span></span>

<span data-ttu-id="273ab-440">使用最适合用户范围的动态配置文件-计算机上所有用户的部署配置，特定用户的用户配置。</span><span class="sxs-lookup"><span data-stu-id="273ab-440">Use the dynamic configuration file that best suits the user scope – deployment configuration for all users on computer, user configuration for specific user or users.</span></span>

-   <span data-ttu-id="273ab-441">使用部署或用户配置禁用字体。</span><span class="sxs-lookup"><span data-stu-id="273ab-441">Disable fonts with the deployment or user configuration.</span></span>

<span data-ttu-id="273ab-442">字体</span><span class="sxs-lookup"><span data-stu-id="273ab-442">Fonts</span></span>

--&gt;

<span data-ttu-id="273ab-443">&lt;已启用的字体 = "false"/&gt;</span><span class="sxs-lookup"><span data-stu-id="273ab-443">&lt;Fonts Enabled="false" /&gt;</span></span>

<span data-ttu-id="273ab-444">&lt;!--</span><span class="sxs-lookup"><span data-stu-id="273ab-444">&lt;!--</span></span>

## <a href="" id="bkmk-terms1"></a> <span data-ttu-id="273ab-445">App-v 5.1 性能指南术语</span><span class="sxs-lookup"><span data-stu-id="273ab-445">App-V 5.1 Performance Guidance Terminology</span></span>


<span data-ttu-id="273ab-446">在描述与 App-v 5.1 性能优化相关的概念和操作时，将使用以下术语。</span><span class="sxs-lookup"><span data-stu-id="273ab-446">The following terms are used when describing concepts and actions related to App-V 5.1 performance optimization.</span></span>

-   <span data-ttu-id="273ab-447">**复杂性**–指在预配置（**Add-AppvClientPackage**）或集成（**AppvClientPackage**）期间可能会影响性能的一个或多个程序包特征。</span><span class="sxs-lookup"><span data-stu-id="273ab-447">**Complexity** – Refers to the one or more package characteristics that may impact performance during pre-configure (**Add-AppvClientPackage**) or integration (**Publish-AppvClientPackage**).</span></span> <span data-ttu-id="273ab-448">一些示例特征是：清单大小、虚拟字体数、文件数。</span><span class="sxs-lookup"><span data-stu-id="273ab-448">Some example characteristics are: manifest size, number of virtual fonts, number of files.</span></span>

-   <span data-ttu-id="273ab-449">**取消集成**-删除用户集成</span><span class="sxs-lookup"><span data-stu-id="273ab-449">**De-Integrate** – Removes the user integrations</span></span>

-   <span data-ttu-id="273ab-450">**重新集成**–应用用户集成。</span><span class="sxs-lookup"><span data-stu-id="273ab-450">**Re-Integrate** – Applies the user integrations.</span></span>

-   <span data-ttu-id="273ab-451">**非持久，共**用-在每次登录时创建运行虚拟环境的计算机。</span><span class="sxs-lookup"><span data-stu-id="273ab-451">**Non-Persistent, Pooled** – Creates a computer running a virtual environment each time they log in.</span></span>

-   <span data-ttu-id="273ab-452">**永久性，个人**-运行每个登录的虚拟环境的计算机都保持不变。</span><span class="sxs-lookup"><span data-stu-id="273ab-452">**Persistent, Personal** – A computer running a virtual environment that remains the same for every login.</span></span>

-   <span data-ttu-id="273ab-453">**状态**-对于此文档，表示用户集成在会话之间保持，并且用户环境管理技术与非持久性 RDSH 或 VDI 结合使用。</span><span class="sxs-lookup"><span data-stu-id="273ab-453">**Stateful** - For this document, implies that user integrations are persisted between sessions and a user environment management technology is used in conjunction with non-persistent RDSH or VDI.</span></span>

-   <span data-ttu-id="273ab-454">**无状态**-表示在会话之间不保持用户状态时的方案。</span><span class="sxs-lookup"><span data-stu-id="273ab-454">**Stateless** – Represents a scenario when no user state is persisted between sessions.</span></span>

-   <span data-ttu-id="273ab-455">**触发器**-（或本机操作触发器）。</span><span class="sxs-lookup"><span data-stu-id="273ab-455">**Trigger** – (or Native Action Triggers).</span></span> <span data-ttu-id="273ab-456">UPM 使用这些类型的触发器启动监视或同步操作。</span><span class="sxs-lookup"><span data-stu-id="273ab-456">UPM uses these types of triggers to initiate monitoring or synchronization operations.</span></span>

-   <span data-ttu-id="273ab-457">**用户体验**-在 app-v 5.1 的上下文中，用户体验 quantitatively 是以下部分的和：</span><span class="sxs-lookup"><span data-stu-id="273ab-457">**User Experience** - In the context of App-V 5.1, the user experience, quantitatively, is the sum of the following parts:</span></span>

    -   <span data-ttu-id="273ab-458">从用户启动登录到桌面的时间点开始，您可以进行操作。</span><span class="sxs-lookup"><span data-stu-id="273ab-458">From the point that users initiate a log-in to when they are able to manipulate the desktop.</span></span>

    -   <span data-ttu-id="273ab-459">在使用 App-v 5.1 完整服务器基础结构时，从桌面可以与发布刷新的点开始交互的位置（在 PowerShell 术语中为同步）。</span><span class="sxs-lookup"><span data-stu-id="273ab-459">From the point where the desktop can be interacted with to the point a publishing refresh begins (in PowerShell terms, sync) when using the App-V 5.1 full server infrastructure.</span></span> <span data-ttu-id="273ab-460">在独立实例中，启动了**Add-AppVClientPackage**和**AppVClientPackage Powershell**命令。</span><span class="sxs-lookup"><span data-stu-id="273ab-460">In standalone instances, it is when the **Add-AppVClientPackage** and **Publish-AppVClientPackage Powershell** commands are initiated.</span></span>

    -   <span data-ttu-id="273ab-461">从开始到完成发布刷新。</span><span class="sxs-lookup"><span data-stu-id="273ab-461">From start to completion of the publishing refresh.</span></span> <span data-ttu-id="273ab-462">在独立实例中，这是第一个发布的最后一个虚拟应用程序。</span><span class="sxs-lookup"><span data-stu-id="273ab-462">In standalone instances, this is the first to last virtual application published.</span></span>

    -   <span data-ttu-id="273ab-463">从虚拟应用程序可从快捷方式启动的位置开始。</span><span class="sxs-lookup"><span data-stu-id="273ab-463">From the point where the virtual application is available to launch from a shortcut.</span></span> <span data-ttu-id="273ab-464">或者，它从文件类型关联注册的点开始，并且将启动指定的虚拟应用程序。</span><span class="sxs-lookup"><span data-stu-id="273ab-464">Alternatively, it is from the point at which the file type association is registered and will launch a specified virtual application.</span></span>

-   <span data-ttu-id="273ab-465">**用户配置文件管理**-用于管理与环境相关联的用户组件的可控和结构化方法。</span><span class="sxs-lookup"><span data-stu-id="273ab-465">**User Profile Management** – The controlled and structured approach to managing user components associated with the environment.</span></span> <span data-ttu-id="273ab-466">例如，用户配置文件、首选项和策略管理、应用程序控制和应用程序部署。</span><span class="sxs-lookup"><span data-stu-id="273ab-466">For example, user profiles, preference and policy management, application control and application deployment.</span></span> <span data-ttu-id="273ab-467">你可以使用脚本或第三方解决方案根据需要配置环境。</span><span class="sxs-lookup"><span data-stu-id="273ab-467">You can use scripting or third-party solutions configure the environment as needed.</span></span>






## <span data-ttu-id="273ab-468">相关主题</span><span class="sxs-lookup"><span data-stu-id="273ab-468">Related topics</span></span>


[<span data-ttu-id="273ab-469">Microsoft Application Virtualization 5.1 管理员指南</span><span class="sxs-lookup"><span data-stu-id="273ab-469">Microsoft Application Virtualization 5.1 Administrator's Guide</span></span>](microsoft-application-virtualization-51-administrators-guide.md)









