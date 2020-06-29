---
title: UE-V 2.x 入门
description: UE-V 2.x 入门
author: dansimp
ms.assetid: 526ecbf0-0dee-4f0b-b017-8f8d25357b14
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 02/13/2017
ms.openlocfilehash: d3f01dd67ea9e5f6cfcf5dc3425265deff3f7df1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803338"
---
# <span data-ttu-id="ecf3f-103">UE-V 2.x 入门</span><span class="sxs-lookup"><span data-stu-id="ecf3f-103">Get Started with UE-V 2.x</span></span>


<span data-ttu-id="ecf3f-104">按照本指南中的步骤，在小型测试环境中快速部署 Microsoft 用户体验虚拟化（UE-V）2.0 或2.1。</span><span class="sxs-lookup"><span data-stu-id="ecf3f-104">Follow the steps in this guide to quickly deploy Microsoft User Experience Virtualization (UE-V) 2.0 or 2.1 in a small test environment.</span></span> <span data-ttu-id="ecf3f-105">这可帮助你确定 UE-V 是否是在企业内的多个设备上管理用户设置的合适解决方案。</span><span class="sxs-lookup"><span data-stu-id="ecf3f-105">This helps you determine whether UE-V is the right solution to manage user settings across multiple devices within your enterprise.</span></span>

<span data-ttu-id="ecf3f-106">**注意** 本部分中的信息将在整个文档的其余部分中更详细地重复。</span><span class="sxs-lookup"><span data-stu-id="ecf3f-106">**Note** The information in this section is repeated in greater detail throughout the rest of the documentation.</span></span> <span data-ttu-id="ecf3f-107">因此，如果你已经知道 UE-V 2 是正确的解决方案，而你不需要对其进行评估，则可以直接转到[准备 ue-v 2. x 部署](prepare-a-ue-v-2x-deployment-new-uevv2.md)。</span><span class="sxs-lookup"><span data-stu-id="ecf3f-107">So if you already know that UE-V 2 is the right solution and you don’t need to evaluate it, you can just go right to [Prepare a UE-V 2.x Deployment](prepare-a-ue-v-2x-deployment-new-uevv2.md).</span></span>

 

<span data-ttu-id="ecf3f-108">UE-V 的标准安装将同步默认的 Microsoft Windows 和 Office 设置以及许多 Windows 应用设置。</span><span class="sxs-lookup"><span data-stu-id="ecf3f-108">The standard installation of UE-V synchronizes the default Microsoft Windows and Office settings and many Windows app settings.</span></span> <span data-ttu-id="ecf3f-109">确保你的测试环境包含两个或多个共享网络访问的用户计算机，你将在短期内评估 UE-V。</span><span class="sxs-lookup"><span data-stu-id="ecf3f-109">Make sure your test environment includes two or more user computers that share network access and you’ll be evaluating UE-V in just a short time.</span></span>

-   <span data-ttu-id="ecf3f-110">[步骤1：确认系统必备](#step1)：确保你的环境能够运行 ue-v，包括有关受支持的配置的详细信息。</span><span class="sxs-lookup"><span data-stu-id="ecf3f-110">[Step 1: Confirm Prerequisites](#step1): Make sure your environment is able to run UE-V, including details about supported configurations.</span></span>

-   <span data-ttu-id="ecf3f-111">[步骤2：为 ue-v 2 部署设置存储位置](#step2)：所有 Ue-v 部署都需要一个包含同步设置值的设置程序包的位置。</span><span class="sxs-lookup"><span data-stu-id="ecf3f-111">[Step 2: Deploy the Settings Storage Location for UE-V 2](#step2): All UE-V deployments require a location for settings packages that contain the synchronized setting values.</span></span>

-   <span data-ttu-id="ecf3f-112">[步骤3：部署 ue-v 2 代理](#step3)：若要使用 ue-v 同步设置，设备必须安装并运行 ue-v Agent。</span><span class="sxs-lookup"><span data-stu-id="ecf3f-112">[Step 3: Deploy the UE-V 2 Agent](#step3): To synchronize settings using UE-V, devices must have the UE-V Agent installed and running.</span></span>

-   <span data-ttu-id="ecf3f-113">[步骤4：测试 ue-v 2 评估部署](#step4)：在安装了 ue-v Agent 的两台计算机上运行一些测试，并查看 ue-v 如何工作。</span><span class="sxs-lookup"><span data-stu-id="ecf3f-113">[Step 4: Test Your UE-V 2 Evaluation Deployment](#step4): Run a few tests on two computers that have the UE-V Agent installed and see how UE-V works.</span></span>

<span data-ttu-id="ecf3f-114">就是这样！</span><span class="sxs-lookup"><span data-stu-id="ecf3f-114">That’s it!</span></span> <span data-ttu-id="ecf3f-115">按照这些步骤操作后，你将能够评估 UE-V 如何在你的企业中工作。</span><span class="sxs-lookup"><span data-stu-id="ecf3f-115">Once you follow the steps, you’ll be able to evaluate how UE-V can work in your enterprise.</span></span>

<span data-ttu-id="ecf3f-116">**进一步评估：** 你还可以执行其他步骤来配置一些第三方应用程序和业务线应用程序，以便使用 UE-V 同步其设置，如[部署 ue-v 的自定义应用程序](deploy-ue-v-2x-for-custom-applications-new-uevv2.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="ecf3f-116">**Further evaluation:** You can also perform additional steps to configure some third-party and line-of-business applications to synchronize their settings using UE-V as detailed in [Deploy UE-V 2.x for Custom Applications](deploy-ue-v-2x-for-custom-applications-new-uevv2.md).</span></span>

## <a href="" id="step1"></a><span data-ttu-id="ecf3f-117">步骤1：确认先决条件</span><span class="sxs-lookup"><span data-stu-id="ecf3f-117">Step 1: Confirm Prerequisites</span></span>


<span data-ttu-id="ecf3f-118">在继续操作之前，请确保你的环境包括运行 UE-V 的这些要求。</span><span class="sxs-lookup"><span data-stu-id="ecf3f-118">Before you proceed, make sure your environment includes these requirements for running UE-V.</span></span>

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
<th align="left"><strong><span data-ttu-id="ecf3f-119">操作系统</span><span class="sxs-lookup"><span data-stu-id="ecf3f-119">Operating system</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="ecf3f-120">版本</span><span class="sxs-lookup"><span data-stu-id="ecf3f-120">Edition</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="ecf3f-121">Service pack</span><span class="sxs-lookup"><span data-stu-id="ecf3f-121">Service pack</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="ecf3f-122">系统体系结构</span><span class="sxs-lookup"><span data-stu-id="ecf3f-122">System architecture</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="ecf3f-123">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ecf3f-123">Windows PowerShell</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="ecf3f-124">Microsoft .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ecf3f-124">Microsoft .NET Framework</span></span></strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ecf3f-125">Windows7</span><span class="sxs-lookup"><span data-stu-id="ecf3f-125">Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="ecf3f-126">旗舰版、企业版或专业版</span><span class="sxs-lookup"><span data-stu-id="ecf3f-126">Ultimate, Enterprise, or Professional Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="ecf3f-127">SP1</span><span class="sxs-lookup"><span data-stu-id="ecf3f-127">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="ecf3f-128">32 位或 64 位</span><span class="sxs-lookup"><span data-stu-id="ecf3f-128">32-bit or 64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="ecf3f-129">Windows PowerShell 3.0 或更高版本</span><span class="sxs-lookup"><span data-stu-id="ecf3f-129">Windows PowerShell 3.0 or higher</span></span></p></td>
<td align="left"><p><span data-ttu-id="ecf3f-130">.NET Framework 4 或更高版本</span><span class="sxs-lookup"><span data-stu-id="ecf3f-130">.NET Framework 4 or higher</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ecf3f-131">Windows Server2008R2</span><span class="sxs-lookup"><span data-stu-id="ecf3f-131">Windows Server2008R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="ecf3f-132">标准版、企业版、数据中心版或 Web 服务器</span><span class="sxs-lookup"><span data-stu-id="ecf3f-132">Standard, Enterprise, Datacenter, or Web Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="ecf3f-133">SP1</span><span class="sxs-lookup"><span data-stu-id="ecf3f-133">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="ecf3f-134">64 位</span><span class="sxs-lookup"><span data-stu-id="ecf3f-134">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="ecf3f-135">Windows PowerShell 3.0 或更高版本</span><span class="sxs-lookup"><span data-stu-id="ecf3f-135">Windows PowerShell 3.0 or higher</span></span></p></td>
<td align="left"><p><span data-ttu-id="ecf3f-136">.NET Framework 4 或更高版本</span><span class="sxs-lookup"><span data-stu-id="ecf3f-136">.NET Framework 4 or higher</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ecf3f-137">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="ecf3f-137">Windows 8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="ecf3f-138">企业版或专业版</span><span class="sxs-lookup"><span data-stu-id="ecf3f-138">Enterprise or Pro</span></span></p></td>
<td align="left"><p><span data-ttu-id="ecf3f-139">无</span><span class="sxs-lookup"><span data-stu-id="ecf3f-139">None</span></span></p></td>
<td align="left"><p><span data-ttu-id="ecf3f-140">32 位或 64 位</span><span class="sxs-lookup"><span data-stu-id="ecf3f-140">32-bit or 64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="ecf3f-141">Windows PowerShell 3.0 或更高版本</span><span class="sxs-lookup"><span data-stu-id="ecf3f-141">Windows PowerShell 3.0 or higher</span></span></p></td>
<td align="left"><p><span data-ttu-id="ecf3f-142">.NET Framework 4。5</span><span class="sxs-lookup"><span data-stu-id="ecf3f-142">.NET Framework 4.5</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ecf3f-143">Windows Server 2012 或 Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="ecf3f-143">Windows Server 2012 or Windows Server 2012 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="ecf3f-144">标准版或数据中心</span><span class="sxs-lookup"><span data-stu-id="ecf3f-144">Standard or Datacenter</span></span></p></td>
<td align="left"><p><span data-ttu-id="ecf3f-145">无</span><span class="sxs-lookup"><span data-stu-id="ecf3f-145">None</span></span></p></td>
<td align="left"><p><span data-ttu-id="ecf3f-146">64 位</span><span class="sxs-lookup"><span data-stu-id="ecf3f-146">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="ecf3f-147">Windows PowerShell 3.0 或更高版本</span><span class="sxs-lookup"><span data-stu-id="ecf3f-147">Windows PowerShell 3.0 or higher</span></span></p></td>
<td align="left"><p><span data-ttu-id="ecf3f-148">.NET Framework 4。5</span><span class="sxs-lookup"><span data-stu-id="ecf3f-148">.NET Framework 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ecf3f-149">Windows 10 预 1607 verison</span><span class="sxs-lookup"><span data-stu-id="ecf3f-149">Windows 10, pre-1607 verison</span></span></p></td>
<td align="left"><p><span data-ttu-id="ecf3f-150">企业版或专业版</span><span class="sxs-lookup"><span data-stu-id="ecf3f-150">Enterprise or Pro</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="ecf3f-151">32 位或 64 位</span><span class="sxs-lookup"><span data-stu-id="ecf3f-151">32-bit or 64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="ecf3f-152">Windows PowerShell 3.0 或更高版本</span><span class="sxs-lookup"><span data-stu-id="ecf3f-152">Windows PowerShell 3.0 or higher</span></span></p></td>
<td align="left"><p><span data-ttu-id="ecf3f-153">.NET Framework 4。5</span><span class="sxs-lookup"><span data-stu-id="ecf3f-153">.NET Framework 4.5</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ecf3f-154">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="ecf3f-154">Windows Server 2016</span></span></p></td>
<td align="left"><p><span data-ttu-id="ecf3f-155">标准版或数据中心</span><span class="sxs-lookup"><span data-stu-id="ecf3f-155">Standard or Datacenter</span></span></p></td>
<td align="left"><p><span data-ttu-id="ecf3f-156">无</span><span class="sxs-lookup"><span data-stu-id="ecf3f-156">None</span></span></p></td>
<td align="left"><p><span data-ttu-id="ecf3f-157">64 位</span><span class="sxs-lookup"><span data-stu-id="ecf3f-157">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="ecf3f-158">Windows PowerShell 3.0 或更高版本</span><span class="sxs-lookup"><span data-stu-id="ecf3f-158">Windows PowerShell 3.0 or higher</span></span></p></td>
<td align="left"><p><span data-ttu-id="ecf3f-159">.NET Framework 4。5</span><span class="sxs-lookup"><span data-stu-id="ecf3f-159">.NET Framework 4.5</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ecf3f-160">**注意：** 从 Windows 10 版本1607开始，UE-V 已包含在[windows 10 For 企业](https://www.microsoft.com/WindowsForBusiness/windows-for-enterprise)中，不再属于 Microsoft 桌面优化包</span><span class="sxs-lookup"><span data-stu-id="ecf3f-160">**Note:** Starting with Windows 10, version 1607, UE-V is included with [Windows 10 for Enterprise](https://www.microsoft.com/WindowsForBusiness/windows-for-enterprise) and is no longer part of the Microsoft Desktop Optimization Pack</span></span>

<span data-ttu-id="ecf3f-161">同样 .。。</span><span class="sxs-lookup"><span data-stu-id="ecf3f-161">Also…</span></span>

-   <span data-ttu-id="ecf3f-162">**MDOP 许可证：** 此技术是 Microsoft 桌面优化包（MDOP）的一部分。</span><span class="sxs-lookup"><span data-stu-id="ecf3f-162">**MDOP License:** This technology is a part of the Microsoft Desktop Optimization Pack (MDOP).</span></span> <span data-ttu-id="ecf3f-163">企业客户可以通过 Microsoft 软件保障获得 MDOP。</span><span class="sxs-lookup"><span data-stu-id="ecf3f-163">Enterprise customers can get MDOP with Microsoft Software Assurance.</span></span> <span data-ttu-id="ecf3f-164">有关 Microsoft 软件保证和获取 MDOP 的详细信息，请参阅如何获取 MDOP （ https://go.microsoft.com/fwlink/p/?LinkId=322049) 。</span><span class="sxs-lookup"><span data-stu-id="ecf3f-164">For more information about Microsoft Software Assurance and acquiring MDOP, see How Do I Get MDOP (https://go.microsoft.com/fwlink/p/?LinkId=322049).</span></span>

-   <span data-ttu-id="ecf3f-165">要安装的任何计算机的**管理凭据**</span><span class="sxs-lookup"><span data-stu-id="ecf3f-165">**Administrative Credentials** for any computer on which you’ll be installing</span></span>

## <a href="" id="step2"></a><span data-ttu-id="ecf3f-166">步骤2：为 UE-V 2 部署设置存储位置</span><span class="sxs-lookup"><span data-stu-id="ecf3f-166">Step 2: Deploy the Settings Storage Location for UE-V 2</span></span>


<span data-ttu-id="ecf3f-167">你将需要部署设置存储位置（一个标准网络共享，用户设置存储在设置包文件中）。</span><span class="sxs-lookup"><span data-stu-id="ecf3f-167">You’ll need to deploy a settings storage location, a standard network share where user settings are stored in a settings package file.</span></span> <span data-ttu-id="ecf3f-168">创建设置存储共享时，应限制对需要它的用户的访问。</span><span class="sxs-lookup"><span data-stu-id="ecf3f-168">When you create the settings storage share, you should limit access to users that require it.</span></span> <span data-ttu-id="ecf3f-169">[部署设置存储位置](https://technet.microsoft.com/library/dn458891.aspx#ssl)可提供更详细的信息。</span><span class="sxs-lookup"><span data-stu-id="ecf3f-169">[Deploy a Settings Storage Location](https://technet.microsoft.com/library/dn458891.aspx#ssl) provides more detailed information.</span></span>

**<span data-ttu-id="ecf3f-170">创建网络共享</span><span class="sxs-lookup"><span data-stu-id="ecf3f-170">Create a network share</span></span>**

1.  <span data-ttu-id="ecf3f-171">创建新的安全组并将 UE-V 用户添加到其中。</span><span class="sxs-lookup"><span data-stu-id="ecf3f-171">Create a new security group and add UE-V users to it.</span></span>

2.  <span data-ttu-id="ecf3f-172">在存储 UE-V settings 程序包的集中位置的计算机上创建一个新文件夹，然后向 UE-V 用户授予对该文件夹的组权限。</span><span class="sxs-lookup"><span data-stu-id="ecf3f-172">Create a new folder on the centrally located computer that stores the UE-V settings packages, and then grant the UE-V users access with group permissions to the folder.</span></span> <span data-ttu-id="ecf3f-173">支持 UE-V 的管理员必须具有此共享文件夹的权限。</span><span class="sxs-lookup"><span data-stu-id="ecf3f-173">The administrator who supports UE-V must have permissions to this shared folder.</span></span>

3.  <span data-ttu-id="ecf3f-174">在连接时，请分配 UE-V 用户创建目录的权限。</span><span class="sxs-lookup"><span data-stu-id="ecf3f-174">Assign UE-V users permission to create a directory when they connect.</span></span> <span data-ttu-id="ecf3f-175">向该目录的所有子目录授予完全权限，但阻止对上述任何内容的访问。</span><span class="sxs-lookup"><span data-stu-id="ecf3f-175">Grant full permission to all subdirectories of that directory, but block access to anything above.</span></span>

    1.  <span data-ttu-id="ecf3f-176">为 "设置存储位置" 文件夹设置以下共享级服务器消息块（SMB）权限。</span><span class="sxs-lookup"><span data-stu-id="ecf3f-176">Set the following share-level Server Message Block (SMB) permissions for the settings storage location folder.</span></span>

        <table>
        <colgroup>
        <col width="50%" />
        <col width="50%" />
        </colgroup>
        <thead>
        <tr class="header">
        <th align="left"><strong><span data-ttu-id="ecf3f-177">用户帐户</span><span class="sxs-lookup"><span data-stu-id="ecf3f-177">User account</span></span></strong></th>
        <th align="left"><strong><span data-ttu-id="ecf3f-178">推荐的权限</span><span class="sxs-lookup"><span data-stu-id="ecf3f-178">Recommended permissions</span></span></strong></th>
        </tr>
        </thead>
        <tbody>
        <tr class="odd">
        <td align="left"><p><span data-ttu-id="ecf3f-179">所有人</span><span class="sxs-lookup"><span data-stu-id="ecf3f-179">Everyone</span></span></p></td>
        <td align="left"><p><span data-ttu-id="ecf3f-180">无权限</span><span class="sxs-lookup"><span data-stu-id="ecf3f-180">No permissions</span></span></p></td>
        </tr>
        <tr class="even">
        <td align="left"><p><span data-ttu-id="ecf3f-181">UE-V 用户的安全组</span><span class="sxs-lookup"><span data-stu-id="ecf3f-181">Security group of UE-V users</span></span></p></td>
        <td align="left"><p><span data-ttu-id="ecf3f-182">完全控制</span><span class="sxs-lookup"><span data-stu-id="ecf3f-182">Full control</span></span></p></td>
        </tr>
        </tbody>
        </table>

         

    2.  <span data-ttu-id="ecf3f-183">为 "设置存储位置" 文件夹设置以下 NTFS 文件系统权限。</span><span class="sxs-lookup"><span data-stu-id="ecf3f-183">Set the following NTFS file system permissions for the settings storage location folder.</span></span>

        <table>
        <colgroup>
        <col width="33%" />
        <col width="33%" />
        <col width="33%" />
        </colgroup>
        <thead>
        <tr class="header">
        <th align="left"><strong><span data-ttu-id="ecf3f-184">用户帐户</span><span class="sxs-lookup"><span data-stu-id="ecf3f-184">User account</span></span></strong></th>
        <th align="left"><strong><span data-ttu-id="ecf3f-185">推荐的权限</span><span class="sxs-lookup"><span data-stu-id="ecf3f-185">Recommended permissions</span></span></strong></th>
        <th align="left"><strong><span data-ttu-id="ecf3f-186">文件夹</span><span class="sxs-lookup"><span data-stu-id="ecf3f-186">Folder</span></span></strong></th>
        </tr>
        </thead>
        <tbody>
        <tr class="odd">
        <td align="left"><p><span data-ttu-id="ecf3f-187">创建者/所有者</span><span class="sxs-lookup"><span data-stu-id="ecf3f-187">Creator/owner</span></span></p></td>
        <td align="left"><p><span data-ttu-id="ecf3f-188">完全控制</span><span class="sxs-lookup"><span data-stu-id="ecf3f-188">Full control</span></span></p></td>
        <td align="left"><p><span data-ttu-id="ecf3f-189">仅子文件夹和文件</span><span class="sxs-lookup"><span data-stu-id="ecf3f-189">Subfolders and files only</span></span></p></td>
        </tr>
        <tr class="even">
        <td align="left"><p><span data-ttu-id="ecf3f-190">UE-V 用户的安全组</span><span class="sxs-lookup"><span data-stu-id="ecf3f-190">Security group of UE-V users</span></span></p></td>
        <td align="left"><p><span data-ttu-id="ecf3f-191">列出文件夹/读取数据、创建文件夹/附加数据</span><span class="sxs-lookup"><span data-stu-id="ecf3f-191">List folder/read data, create folders/append data</span></span></p></td>
        <td align="left"><p><span data-ttu-id="ecf3f-192">仅此文件夹</span><span class="sxs-lookup"><span data-stu-id="ecf3f-192">This folder only</span></span></p></td>
        </tr>
        </tbody>
        </table>

         

**<span data-ttu-id="ecf3f-193">安全说明：</span><span class="sxs-lookup"><span data-stu-id="ecf3f-193">Security Note:</span></span>**

<span data-ttu-id="ecf3f-194">如果在运行 Windows Server 操作系统的计算机上创建设置存储共享，请配置 UE-V 以验证本地管理员组或当前用户是否为存储设置包的文件夹的所有者。</span><span class="sxs-lookup"><span data-stu-id="ecf3f-194">If you create the settings storage share on a computer running a Windows Server operating system, configure UE-V to verify that either the local Administrators group or the current user is the owner of the folder where settings packages are stored.</span></span> <span data-ttu-id="ecf3f-195">若要启用此附加安全性，请在 Windows Server 注册表编辑器中指定此设置：</span><span class="sxs-lookup"><span data-stu-id="ecf3f-195">To enable this additional security, specify this setting in the Windows Server Registry Editor:</span></span>

1.  <span data-ttu-id="ecf3f-196">将名为 **"RepositoryOwnerCheckEnabled"** 的**REG \ _DWORD**注册表项添加到**HKEY \ _LOCAL \ _MACHINE \\software\\microsoft\\uev\\agent\\configuration**。</span><span class="sxs-lookup"><span data-stu-id="ecf3f-196">Add a **REG\_DWORD** registry key named **"RepositoryOwnerCheckEnabled"** to **HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\UEV\\Agent\\Configuration**.</span></span>

2.  <span data-ttu-id="ecf3f-197">将注册表项值设置为*1*。</span><span class="sxs-lookup"><span data-stu-id="ecf3f-197">Set the registry key value to *1*.</span></span>

## <a href="" id="step3"></a><span data-ttu-id="ecf3f-198">步骤3：部署 UE-V 2 代理</span><span class="sxs-lookup"><span data-stu-id="ecf3f-198">Step 3: Deploy the UE-V 2 Agent</span></span>


<span data-ttu-id="ecf3f-199">UE-V Agent 会同步用户计算机和设备之间的应用程序和 Windows 设置。</span><span class="sxs-lookup"><span data-stu-id="ecf3f-199">The UE-V Agent synchronizes application and Windows settings between users’ computers and devices.</span></span> <span data-ttu-id="ecf3f-200">对于评估目的，请在属于同一用户的测试环境中的至少两台计算机上安装代理。</span><span class="sxs-lookup"><span data-stu-id="ecf3f-200">For evaluation purposes, install the agent on at least two computers in your test environment that belong to the same user.</span></span>

<span data-ttu-id="ecf3f-201">从命令行运行 AgentSetup.exe 文件以安装 UE-V Agent。</span><span class="sxs-lookup"><span data-stu-id="ecf3f-201">Run the AgentSetup.exe file from the command line to install the UE-V Agent.</span></span> <span data-ttu-id="ecf3f-202">它在32位和64位操作系统上安装。</span><span class="sxs-lookup"><span data-stu-id="ecf3f-202">It installs on both 32-bit and 64-bit operating systems.</span></span>

``` syntax
AgentSetup.exe SettingsStoragePath=\\server\settingsshare\%username%
```

<span data-ttu-id="ecf3f-203">必须将 SettingsStoragePath 命令行参数指定为步骤2中的网络共享。</span><span class="sxs-lookup"><span data-stu-id="ecf3f-203">You must specify the SettingsStoragePath command line parameter as the network share from Step 2.</span></span> <span data-ttu-id="ecf3f-204">[部署 Ue-v Agent](https://technet.microsoft.com/library/dn458891.aspx#agent)提供更详细的信息。</span><span class="sxs-lookup"><span data-stu-id="ecf3f-204">[Deploy a UE-V Agent](https://technet.microsoft.com/library/dn458891.aspx#agent) provides more detailed information.</span></span>

## <a href="" id="step4"></a><span data-ttu-id="ecf3f-205">步骤4：测试 UE-V 2 评估部署</span><span class="sxs-lookup"><span data-stu-id="ecf3f-205">Step 4: Test Your UE-V 2 Evaluation Deployment</span></span>


<span data-ttu-id="ecf3f-206">现在，你可以在 UE-V 评估部署上运行一些测试，以了解 UE-V 的工作方式。</span><span class="sxs-lookup"><span data-stu-id="ecf3f-206">You can now run a few tests on your UE-V evaluation deployment to see how UE-V works.</span></span>

****

1.  <span data-ttu-id="ecf3f-207">在第一台计算机（计算机 A）上，执行以下一项或多项更改：</span><span class="sxs-lookup"><span data-stu-id="ecf3f-207">On the first computer (Computer A), make one or more of these changes:</span></span>

    1.  <span data-ttu-id="ecf3f-208">打开到 Windows 桌面并将任务栏移动到窗口中的其他位置。</span><span class="sxs-lookup"><span data-stu-id="ecf3f-208">Open to Windows Desktop and move the taskbar to a different location in the window.</span></span>

    2.  <span data-ttu-id="ecf3f-209">更改默认字体。</span><span class="sxs-lookup"><span data-stu-id="ecf3f-209">Change the default fonts.</span></span>

    3.  <span data-ttu-id="ecf3f-210">打开 "计算器" 并设置为 "**科学记数**"。</span><span class="sxs-lookup"><span data-stu-id="ecf3f-210">Open Calculator and set to **scientific**.</span></span>

    4.  <span data-ttu-id="ecf3f-211">更改任何 Windows 应用的行为，如[管理 ue-v 2. 使用 Windows PowerShell 和 WMI 的 Ue-v Settings 位置模板](managing-ue-v-2x-settings-location-templates-using-windows-powershell-and-wmi-both-uevv2.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="ecf3f-211">Change the behavior of any Windows app, as detailed in [Managing UE-V 2.x Settings Location Templates Using Windows PowerShell and WMI](managing-ue-v-2x-settings-location-templates-using-windows-powershell-and-wmi-both-uevv2.md).</span></span>

    5.  <span data-ttu-id="ecf3f-212">禁用 Microsoft 帐户设置同步和漫游配置文件。</span><span class="sxs-lookup"><span data-stu-id="ecf3f-212">Disable Microsoft Account settings synchronization and Roaming Profiles.</span></span>

2.  <span data-ttu-id="ecf3f-213">注销计算机 A：当用户锁定、注销、退出应用程序或同步提供程序运行时（默认情况下，每隔30分钟），将在 UE-V 设置程序包中保存设置。</span><span class="sxs-lookup"><span data-stu-id="ecf3f-213">Log off Computer A. Settings are saved in a UE-V settings package when users lock, logoff, exit an application, or when the sync provider runs (every 30 minutes by default).</span></span>

3.  <span data-ttu-id="ecf3f-214">以与计算机 A 相同的用户的身份登录到第二台计算机（计算机 B）。</span><span class="sxs-lookup"><span data-stu-id="ecf3f-214">Log in to the second computer (Computer B) as the same user as Computer A.</span></span>

4.  <span data-ttu-id="ecf3f-215">打开到 Windows 桌面并验证任务栏位置是否与计算机 A 的位置相匹配。验证默认字体是否匹配且计算器是否设置为**科学计数**。</span><span class="sxs-lookup"><span data-stu-id="ecf3f-215">Open to Windows Desktop and verify that the taskbar location matches that of Computer A. Verify that the default fonts match and that Calculator is set to **scientific**.</span></span> <span data-ttu-id="ecf3f-216">同时验证你对任何 Windows 应用所做的更改。</span><span class="sxs-lookup"><span data-stu-id="ecf3f-216">Also verify the change you made to any Windows app.</span></span>

<span data-ttu-id="ecf3f-217">你可以将计算机 B 中的设置更改回原始计算机的设置。</span><span class="sxs-lookup"><span data-stu-id="ecf3f-217">You can change the settings in Computer B back to the original Computer A settings.</span></span> <span data-ttu-id="ecf3f-218">然后从计算机 B 注销并登录到计算机 A 以验证更改。</span><span class="sxs-lookup"><span data-stu-id="ecf3f-218">Then log off Computer B and log in to Computer A to verify the changes.</span></span>

## <span data-ttu-id="ecf3f-219">此产品的其他资源</span><span class="sxs-lookup"><span data-stu-id="ecf3f-219">Other resources for this product</span></span>


-   [<span data-ttu-id="ecf3f-220">Microsoft 用户体验虚拟化（UE-V） 2. x</span><span class="sxs-lookup"><span data-stu-id="ecf3f-220">Microsoft User Experience Virtualization (UE-V) 2.x</span></span>](index.md)

-   [<span data-ttu-id="ecf3f-221">准备 UE-V 2. x 部署</span><span class="sxs-lookup"><span data-stu-id="ecf3f-221">Prepare a UE-V 2.x Deployment</span></span>](prepare-a-ue-v-2x-deployment-new-uevv2.md)

-   [<span data-ttu-id="ecf3f-222">管理 UE-V 2. x</span><span class="sxs-lookup"><span data-stu-id="ecf3f-222">Administering UE-V 2.x</span></span>](administering-ue-v-2x-new-uevv2.md)

-   [<span data-ttu-id="ecf3f-223">解决 UE-V 2. x</span><span class="sxs-lookup"><span data-stu-id="ecf3f-223">Troubleshooting UE-V 2.x</span></span>](troubleshooting-ue-v-2x-both-uevv2.md)

-   [<span data-ttu-id="ecf3f-224">UE-V 2.x 的技术参考</span><span class="sxs-lookup"><span data-stu-id="ecf3f-224">Technical Reference for UE-V 2.x</span></span>](technical-reference-for-ue-v-2x-both-uevv2.md)






 

 





