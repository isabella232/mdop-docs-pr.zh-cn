---
title: MED-V 1.0 支持的配置
description: MED-V 1.0 支持的配置
author: dansimp
ms.assetid: 74643de6-549e-4177-a559-6407e156ed3a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3b8ffdfb6e34fe7888ea5ace0ff7264bd978a548
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798088"
---
# <span data-ttu-id="eae11-103">MED-V 1.0 支持的配置</span><span class="sxs-lookup"><span data-stu-id="eae11-103">MED-V 1.0 Supported Configurations</span></span>


<span data-ttu-id="eae11-104">本主题指定在你的环境中安装和运行 Microsoft 企业桌面虚拟化（MED-V）1.0 所需的要求。</span><span class="sxs-lookup"><span data-stu-id="eae11-104">This topic specifies the requirements necessary to install and run Microsoft Enterprise Desktop Virtualization (MED-V) 1.0 in your environment.</span></span>

## <span data-ttu-id="eae11-105">MED-V 1.0 客户端系统要求</span><span class="sxs-lookup"><span data-stu-id="eae11-105">MED-V 1.0 Client System Requirements</span></span>


### <span data-ttu-id="eae11-106">MED-V 客户端操作系统要求</span><span class="sxs-lookup"><span data-stu-id="eae11-106">MED-V Client Operating System Requirements</span></span>

<span data-ttu-id="eae11-107">下表列出了 MED-V 1.0 客户端安装支持的操作系统。</span><span class="sxs-lookup"><span data-stu-id="eae11-107">The following table lists the operating systems that are supported for MED-V 1.0 client installation.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="eae11-108">操作系统</span><span class="sxs-lookup"><span data-stu-id="eae11-108">Operating System</span></span></th>
<th align="left"><span data-ttu-id="eae11-109">版本</span><span class="sxs-lookup"><span data-stu-id="eae11-109">Edition</span></span></th>
<th align="left"><span data-ttu-id="eae11-110">Service Pack</span><span class="sxs-lookup"><span data-stu-id="eae11-110">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="eae11-111">系统体系结构</span><span class="sxs-lookup"><span data-stu-id="eae11-111">System Architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="eae11-112">Windows XP</span><span class="sxs-lookup"><span data-stu-id="eae11-112">Windows XP</span></span></p></td>
<td align="left"><p><span data-ttu-id="eae11-113">专业版</span><span class="sxs-lookup"><span data-stu-id="eae11-113">Professional Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="eae11-114">SP2 或 SP3</span><span class="sxs-lookup"><span data-stu-id="eae11-114">SP2 or SP3</span></span></p></td>
<td align="left"><p><span data-ttu-id="eae11-115">x86</span><span class="sxs-lookup"><span data-stu-id="eae11-115">x86</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="eae11-116">Windows Vista</span><span class="sxs-lookup"><span data-stu-id="eae11-116">Windows Vista</span></span></p></td>
<td align="left"><p><span data-ttu-id="eae11-117">企业版、企业版或旗舰版</span><span class="sxs-lookup"><span data-stu-id="eae11-117">Business, Enterprise, or Ultimate Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="eae11-118">SP1 或 SP2</span><span class="sxs-lookup"><span data-stu-id="eae11-118">SP1 or SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="eae11-119">x86</span><span class="sxs-lookup"><span data-stu-id="eae11-119">x86</span></span></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="eae11-120">注意</span><span class="sxs-lookup"><span data-stu-id="eae11-120">Note</span></span>**  
<span data-ttu-id="eae11-121">MED-V 客户端不在本机 x64 模式下运行。</span><span class="sxs-lookup"><span data-stu-id="eae11-121">MED-V client does not run in native x64 mode.</span></span> <span data-ttu-id="eae11-122">而 MED-V 在64位计算机上的 Windows 64 位（WOW64）模式下运行。</span><span class="sxs-lookup"><span data-stu-id="eae11-122">Instead, MED-V runs in Windows on Windows 64-bit (WOW64) mode on 64-bit computers.</span></span>



### <a href="" id="med-v-1-0-client-configuration-"></a><span data-ttu-id="eae11-123">MED-V 1.0 客户端配置</span><span class="sxs-lookup"><span data-stu-id="eae11-123">MED-V 1.0 Client Configuration</span></span>

**<span data-ttu-id="eae11-124">.NET Framework 版本</span><span class="sxs-lookup"><span data-stu-id="eae11-124">.NET Framework Version</span></span>**

<span data-ttu-id="eae11-125">以下版本的 Microsoft .NET Framework 支持 MED-V 1.0 客户端安装：</span><span class="sxs-lookup"><span data-stu-id="eae11-125">The following versions of the Microsoft .NET Framework are supported for MED-V 1.0 client installation:</span></span>

-   <span data-ttu-id="eae11-126">.NET Framework 2.0 或 .NET Framework 2.0 SP1</span><span class="sxs-lookup"><span data-stu-id="eae11-126">.NET Framework 2.0 or .NET Framework 2.0 SP1</span></span>

-   <span data-ttu-id="eae11-127">.NET Framework 3.0 或 .NET Framework 3.0 SP1</span><span class="sxs-lookup"><span data-stu-id="eae11-127">.NET Framework 3.0 or .NET Framework 3.0 SP1</span></span>

-   <span data-ttu-id="eae11-128">.NET Framework 3.5 或 .NET Framework 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="eae11-128">.NET Framework 3.5 or .NET Framework 3.5 SP1</span></span>

**<span data-ttu-id="eae11-129">虚拟化引擎</span><span class="sxs-lookup"><span data-stu-id="eae11-129">Virtualization Engine</span></span>**

<span data-ttu-id="eae11-130">对于以下配置中的 MED-V 1.0 客户端安装，支持 microsoft office 知识库文章974918中所述修复程序的 microsoft Virtual PC 2007 SP1：</span><span class="sxs-lookup"><span data-stu-id="eae11-130">Microsoft Virtual PC 2007 SP1 with the hotfix that is described in Microsoft Knowledge Base article 974918 is supported for MED-V 1.0 client installation in the following configurations:</span></span>

-   <span data-ttu-id="eae11-131">静态虚拟硬盘（VHD）文件</span><span class="sxs-lookup"><span data-stu-id="eae11-131">Static Virtual Hard Disk (VHD) file</span></span>

-   <span data-ttu-id="eae11-132">位于同一目录中的多个 VHD 文件</span><span class="sxs-lookup"><span data-stu-id="eae11-132">Multiple VHD files located within the same directory</span></span>

-   <span data-ttu-id="eae11-133">动态 VHD 文件</span><span class="sxs-lookup"><span data-stu-id="eae11-133">Dynamic VHD file</span></span>

**<span data-ttu-id="eae11-134">Internet 浏览器</span><span class="sxs-lookup"><span data-stu-id="eae11-134">Internet Browser</span></span>**

<span data-ttu-id="eae11-135">Windows Internet Explorer 7 和 Windows Internet Explorer 8 支持 MED-V 1.0 客户端安装。</span><span class="sxs-lookup"><span data-stu-id="eae11-135">Windows Internet Explorer 7 and Windows Internet Explorer 8 are supported for MED-V 1.0 client installation.</span></span>

**<span data-ttu-id="eae11-136">Microsoft Hyper-V Server</span><span class="sxs-lookup"><span data-stu-id="eae11-136">Microsoft Hyper-V Server</span></span>**

<span data-ttu-id="eae11-137">在 Microsoft Hyper-v server 环境中不支持 MED-V 客户端。</span><span class="sxs-lookup"><span data-stu-id="eae11-137">The MED-V client is not supported in a Microsoft Hyper-V server environment.</span></span>

## <span data-ttu-id="eae11-138">MED-V 1.0 工作区系统要求</span><span class="sxs-lookup"><span data-stu-id="eae11-138">MED-V 1.0 Workspace System Requirements</span></span>


### <span data-ttu-id="eae11-139">MED-V 工作区操作系统要求</span><span class="sxs-lookup"><span data-stu-id="eae11-139">MED-V Workspace Operating System Requirements</span></span>

<span data-ttu-id="eae11-140">下表列出了 MED-V 1.0 工作区支持的操作系统。</span><span class="sxs-lookup"><span data-stu-id="eae11-140">The following table lists the operating systems supported for MED-V 1.0 workspaces.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="eae11-141">操作系统</span><span class="sxs-lookup"><span data-stu-id="eae11-141">Operating System</span></span></th>
<th align="left"><span data-ttu-id="eae11-142">版本</span><span class="sxs-lookup"><span data-stu-id="eae11-142">Edition</span></span></th>
<th align="left"><span data-ttu-id="eae11-143">Service Pack</span><span class="sxs-lookup"><span data-stu-id="eae11-143">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="eae11-144">系统体系结构</span><span class="sxs-lookup"><span data-stu-id="eae11-144">System Architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="eae11-145">Windows 2000</span><span class="sxs-lookup"><span data-stu-id="eae11-145">Windows 2000</span></span></p></td>
<td align="left"><p><span data-ttu-id="eae11-146">专业版</span><span class="sxs-lookup"><span data-stu-id="eae11-146">Professional</span></span></p></td>
<td align="left"><p><span data-ttu-id="eae11-147">以后</span><span class="sxs-lookup"><span data-stu-id="eae11-147">SP4</span></span></p></td>
<td align="left"><p><span data-ttu-id="eae11-148">X86</span><span class="sxs-lookup"><span data-stu-id="eae11-148">X86</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="eae11-149">Windows XP</span><span class="sxs-lookup"><span data-stu-id="eae11-149">Windows XP</span></span></p></td>
<td align="left"><p><span data-ttu-id="eae11-150">专业版</span><span class="sxs-lookup"><span data-stu-id="eae11-150">Professional Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="eae11-151">SP2 或 SP3</span><span class="sxs-lookup"><span data-stu-id="eae11-151">SP2 or SP3</span></span></p>
<div class="alert">
<strong><span data-ttu-id="eae11-152">注意</span><span class="sxs-lookup"><span data-stu-id="eae11-152">Note</span></span></strong><br/><p><span data-ttu-id="eae11-153">建议使用 SP3，以确保 MED-V 工作区与 MED-V 的未来版本兼容。</span><span class="sxs-lookup"><span data-stu-id="eae11-153">SP3 is recommended to ensure that the MED-V workspace will be compatible with future versions of MED-V.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><span data-ttu-id="eae11-154">x86</span><span class="sxs-lookup"><span data-stu-id="eae11-154">x86</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="med-v-1-0-workspace-configuration-"></a><span data-ttu-id="eae11-155">MED-V 1.0 工作区配置</span><span class="sxs-lookup"><span data-stu-id="eae11-155">MED-V 1.0 Workspace Configuration</span></span>

**<span data-ttu-id="eae11-156">.NET Framework 版本</span><span class="sxs-lookup"><span data-stu-id="eae11-156">.NET Framework Version</span></span>**

<span data-ttu-id="eae11-157">MED-V 需要适用于 MED-V 1.0 工作区安装的以下支持版本的 Microsoft .NET Framework 之一：</span><span class="sxs-lookup"><span data-stu-id="eae11-157">MED-V requires one of the following supported versions of the Microsoft .NET Framework for MED-V 1.0 workspace installation:</span></span>

-   <span data-ttu-id="eae11-158">.NET Framework 2.0 SP1</span><span class="sxs-lookup"><span data-stu-id="eae11-158">.NET Framework 2.0 SP1</span></span>

-   <span data-ttu-id="eae11-159">.NET Framework 3.0 SP1</span><span class="sxs-lookup"><span data-stu-id="eae11-159">.NET Framework 3.0 SP1</span></span>

-   <span data-ttu-id="eae11-160">.NET Framework 3.5 或 .NET Framework 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="eae11-160">.NET Framework 3.5 or .NET Framework 3.5 SP1</span></span>

**<span data-ttu-id="eae11-161">注意</span><span class="sxs-lookup"><span data-stu-id="eae11-161">Note</span></span>**  
<span data-ttu-id="eae11-162">建议使用 .NET Framework 3.5 SP1，以确保 MED-V 工作区与 MED-V 的未来版本兼容。</span><span class="sxs-lookup"><span data-stu-id="eae11-162">.NET Framework 3.5 SP1 is recommended to ensure that the MED-V workspace will be compatible with future versions of MED-V.</span></span>



**<span data-ttu-id="eae11-163">Internet 浏览器</span><span class="sxs-lookup"><span data-stu-id="eae11-163">Internet Browser</span></span>**

<span data-ttu-id="eae11-164">Windows Internet Explorer 6 SP2 和 Windows Internet Explorer 7 支持 MED-V 1.0 工作区安装。</span><span class="sxs-lookup"><span data-stu-id="eae11-164">Windows Internet Explorer 6 SP2 and Windows Internet Explorer 7 are supported for the MED-V 1.0 workspace installation.</span></span>

### <a href="" id="med-v-workspace-images-"></a><span data-ttu-id="eae11-165">MED-V 工作区图像</span><span class="sxs-lookup"><span data-stu-id="eae11-165">MED-V Workspace Images</span></span>

<span data-ttu-id="eae11-166">MED-V 工作区映像必须使用虚拟 PC 2007 SP1 创建。</span><span class="sxs-lookup"><span data-stu-id="eae11-166">MED-V workspace images must be created by using Virtual PC 2007 SP1.</span></span>

## <span data-ttu-id="eae11-167">MED-V 1.0 服务器系统要求</span><span class="sxs-lookup"><span data-stu-id="eae11-167">MED-V 1.0 Server System Requirements</span></span>


### <span data-ttu-id="eae11-168">MED-V 1.0 服务器操作系统要求</span><span class="sxs-lookup"><span data-stu-id="eae11-168">MED-V 1.0 Server Operating System Requirements</span></span>

<span data-ttu-id="eae11-169">下表列出了 MED-V 1.0 服务器安装支持的操作系统。</span><span class="sxs-lookup"><span data-stu-id="eae11-169">The following table lists the operating systems supported for MED-V 1.0 server installations.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="eae11-170">操作系统</span><span class="sxs-lookup"><span data-stu-id="eae11-170">Operating System</span></span></th>
<th align="left"><span data-ttu-id="eae11-171">版本</span><span class="sxs-lookup"><span data-stu-id="eae11-171">Edition</span></span></th>
<th align="left"><span data-ttu-id="eae11-172">Service Pack</span><span class="sxs-lookup"><span data-stu-id="eae11-172">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="eae11-173">系统体系结构</span><span class="sxs-lookup"><span data-stu-id="eae11-173">System Architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="eae11-174">Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="eae11-174">Windows Server 2008</span></span></p></td>
<td align="left"><p><span data-ttu-id="eae11-175">Standard 或 Enterprise</span><span class="sxs-lookup"><span data-stu-id="eae11-175">Standard or Enterprise</span></span></p></td>
<td align="left"><p><span data-ttu-id="eae11-176">无</span><span class="sxs-lookup"><span data-stu-id="eae11-176">None</span></span></p></td>
<td align="left"><p><span data-ttu-id="eae11-177">X86 或 x64</span><span class="sxs-lookup"><span data-stu-id="eae11-177">X86 or x64</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="med-v-1-0-server-configuration-"></a><span data-ttu-id="eae11-178">MED-V 1.0 服务器配置</span><span class="sxs-lookup"><span data-stu-id="eae11-178">MED-V 1.0 Server Configuration</span></span>

**<span data-ttu-id="eae11-179">.NET Framework 版本</span><span class="sxs-lookup"><span data-stu-id="eae11-179">.NET Framework Version</span></span>**

<span data-ttu-id="eae11-180">MED-V 需要适用于 MED-V 1.0 工作区安装的以下支持版本的 Microsoft .NET Framework 之一：</span><span class="sxs-lookup"><span data-stu-id="eae11-180">MED-V requires one of the following supported versions of the Microsoft .NET Framework for MED-V 1.0 workspace installation:</span></span>

-   <span data-ttu-id="eae11-181">.NET Framework 2.0 或 .NET Framework 2.0 SP1</span><span class="sxs-lookup"><span data-stu-id="eae11-181">.NET Framework 2.0 or .NET Framework 2.0 SP1</span></span>

-   <span data-ttu-id="eae11-182">.NET Framework 3.0 或 .NET Framework 3.0 SP1</span><span class="sxs-lookup"><span data-stu-id="eae11-182">.NET Framework 3.0 or .NET Framework 3.0 SP1</span></span>

-   <span data-ttu-id="eae11-183">.NET Framework 3.5 或 .NET Framework 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="eae11-183">.NET Framework 3.5 or .NET Framework 3.5 SP1</span></span>

**<span data-ttu-id="eae11-184">Microsoft SQL Server 版本</span><span class="sxs-lookup"><span data-stu-id="eae11-184">Microsoft SQL Server Version</span></span>**

<span data-ttu-id="eae11-185">从 MED-V 1.0 服务器本地或远程安装 SQL Server 时，MED-V 1.0 支持以下版本的 Microsoft SQL Server：</span><span class="sxs-lookup"><span data-stu-id="eae11-185">The following versions of Microsoft SQL Server are supported for MED-V 1.0 when SQL Server is installed locally or remotely from the MED-V 1.0 Server:</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="eae11-186">SQL Server 版本</span><span class="sxs-lookup"><span data-stu-id="eae11-186">SQL Server Version</span></span></th>
<th align="left"><span data-ttu-id="eae11-187">版本</span><span class="sxs-lookup"><span data-stu-id="eae11-187">Edition</span></span></th>
<th align="left"><span data-ttu-id="eae11-188">Service Pack</span><span class="sxs-lookup"><span data-stu-id="eae11-188">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="eae11-189">系统体系结构</span><span class="sxs-lookup"><span data-stu-id="eae11-189">System Architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="eae11-190">SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="eae11-190">SQL Server 2005</span></span></p></td>
<td align="left"><p><span data-ttu-id="eae11-191">速成版、标准版或企业版</span><span class="sxs-lookup"><span data-stu-id="eae11-191">Express, Standard, or Enterprise Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="eae11-192">SP2</span><span class="sxs-lookup"><span data-stu-id="eae11-192">SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="eae11-193">X86 或 x64</span><span class="sxs-lookup"><span data-stu-id="eae11-193">X86 or x64</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="eae11-194">SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="eae11-194">SQL Server 2008</span></span></p></td>
<td align="left"><p><span data-ttu-id="eae11-195">速成版、标准版或企业版</span><span class="sxs-lookup"><span data-stu-id="eae11-195">Express, Standard, or Enterprise</span></span></p></td>
<td align="left"><p><span data-ttu-id="eae11-196">无</span><span class="sxs-lookup"><span data-stu-id="eae11-196">None</span></span></p></td>
<td align="left"><p><span data-ttu-id="eae11-197">X86 或 x64</span><span class="sxs-lookup"><span data-stu-id="eae11-197">X86 or x64</span></span></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="eae11-198">Microsoft Hyper-V Server</span><span class="sxs-lookup"><span data-stu-id="eae11-198">Microsoft Hyper-V Server</span></span>**

<span data-ttu-id="eae11-199">在 Microsoft Hyper-v server 环境中支持 MED-V 服务器。</span><span class="sxs-lookup"><span data-stu-id="eae11-199">The MED-V server is supported in a Microsoft Hyper-V server environment.</span></span>

## <span data-ttu-id="eae11-200">MED-V 1.0 全球化信息</span><span class="sxs-lookup"><span data-stu-id="eae11-200">MED-V 1.0 Globalization Information</span></span>


<span data-ttu-id="eae11-201">尽管 MED-V 不是用英语以外的语言发布的，但对于 MED-V 1.0 客户端、工作区和服务器安装，支持以下 Windows 操作系统语言版本：</span><span class="sxs-lookup"><span data-stu-id="eae11-201">Although MED-V is not released in languages other than English, the following Windows operating system language versions are supported for the MED-V 1.0 client, workspace, and server installations:</span></span>

-   <span data-ttu-id="eae11-202">英语</span><span class="sxs-lookup"><span data-stu-id="eae11-202">English</span></span>

-   <span data-ttu-id="eae11-203">法语</span><span class="sxs-lookup"><span data-stu-id="eae11-203">French</span></span>

-   <span data-ttu-id="eae11-204">德语</span><span class="sxs-lookup"><span data-stu-id="eae11-204">German</span></span>

-   <span data-ttu-id="eae11-205">意大利语</span><span class="sxs-lookup"><span data-stu-id="eae11-205">Italian</span></span>

-   <span data-ttu-id="eae11-206">西班牙语</span><span class="sxs-lookup"><span data-stu-id="eae11-206">Spanish</span></span>

-   <span data-ttu-id="eae11-207">葡萄牙语（巴西）</span><span class="sxs-lookup"><span data-stu-id="eae11-207">Portuguese (Brazil)</span></span>









