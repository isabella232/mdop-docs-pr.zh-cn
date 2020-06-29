---
title: App-V 5.0 SP3 先决条件
description: App-V 5.0 SP3 先决条件
author: dansimp
ms.assetid: fa8d5578-3a53-4e8a-95c7-e7a5f6e4a31c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d8e8318a71d2d3631b0ad47e3c3db3c569488790
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798636"
---
# <span data-ttu-id="dd307-103">App-V 5.0 SP3 先决条件</span><span class="sxs-lookup"><span data-stu-id="dd307-103">App-V 5.0 SP3 Prerequisites</span></span>


<span data-ttu-id="dd307-104">在安装 Microsoft Application Virtualization （App-v） 5.0 SP3 之前，请确保已安装以下所有必需的必备软件。</span><span class="sxs-lookup"><span data-stu-id="dd307-104">Before installing Microsoft Application Virtualization (App-V) 5.0 SP3, ensure that you have installed all of the following required prerequisite software.</span></span>

<span data-ttu-id="dd307-105">有关支持的操作系统和 app-v Server、Sequencer 和客户端的硬件要求的列表，请参阅[app-v 5.0 SP3 支持的配置](app-v-50-sp3-supported-configurations.md)。</span><span class="sxs-lookup"><span data-stu-id="dd307-105">For a list of supported operating systems and hardware requirements for the App-V Server, Sequencer, and Client, see [App-V 5.0 SP3 Supported Configurations](app-v-50-sp3-supported-configurations.md).</span></span>

## <span data-ttu-id="dd307-106">在每个操作系统上预安装的软件的摘要</span><span class="sxs-lookup"><span data-stu-id="dd307-106">Summary of software preinstalled on each operating system</span></span>


<span data-ttu-id="dd307-107">下表显示了已针对不同操作系统安装的软件。</span><span class="sxs-lookup"><span data-stu-id="dd307-107">The following table indicates the software that is already installed for different operating systems.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="dd307-108">操作系统</span><span class="sxs-lookup"><span data-stu-id="dd307-108">Operating system</span></span></th>
<th align="left"><span data-ttu-id="dd307-109">先决条件说明</span><span class="sxs-lookup"><span data-stu-id="dd307-109">Prerequisite description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dd307-110">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="dd307-110">Windows 8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="dd307-111">已安装所有必备软件。</span><span class="sxs-lookup"><span data-stu-id="dd307-111">All of the prerequisite software is already installed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="dd307-112">Windows 8</span><span class="sxs-lookup"><span data-stu-id="dd307-112">Windows 8</span></span></p>
<p><span data-ttu-id="dd307-113">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="dd307-113">Windows Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="dd307-114">已安装以下必备软件：</span><span class="sxs-lookup"><span data-stu-id="dd307-114">The following prerequisite software is already installed:</span></span></p>
<ul>
<li><p><span data-ttu-id="dd307-115">Microsoft .NET Framework 4。5</span><span class="sxs-lookup"><span data-stu-id="dd307-115">Microsoft .NET Framework 4.5</span></span></p></li>
<li><p><span data-ttu-id="dd307-116">Windows PowerShell 3。0</span><span class="sxs-lookup"><span data-stu-id="dd307-116">Windows PowerShell 3.0</span></span></p>
<div class="alert">
<strong><span data-ttu-id="dd307-117">注意</span><span class="sxs-lookup"><span data-stu-id="dd307-117">Note</span></span></strong><br/><p><span data-ttu-id="dd307-118">安装 PowerShell 3.0 需要重新启动。</span><span class="sxs-lookup"><span data-stu-id="dd307-118">Installing PowerShell 3.0 requires a restart.</span></span></p>
</div>
<div>

</div></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dd307-119">Windows 7</span><span class="sxs-lookup"><span data-stu-id="dd307-119">Windows 7</span></span></p></td>
<td align="left"><p><span data-ttu-id="dd307-120">尚未安装必备软件。</span><span class="sxs-lookup"><span data-stu-id="dd307-120">The prerequisite software is not already installed.</span></span> <span data-ttu-id="dd307-121">必须先安装它，然后才能安装 App-v。</span><span class="sxs-lookup"><span data-stu-id="dd307-121">You must install it before you can install App-V.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="dd307-122">App-v 服务器必备软件</span><span class="sxs-lookup"><span data-stu-id="dd307-122">App-V Server prerequisite software</span></span>


<span data-ttu-id="dd307-123">为 App-v 5.0 SP3 服务器组件安装所需的必备软件。</span><span class="sxs-lookup"><span data-stu-id="dd307-123">Install the required prerequisite software for the App-V 5.0 SP3 Server components.</span></span>

### <span data-ttu-id="dd307-124">开始之前需要了解的内容</span><span class="sxs-lookup"><span data-stu-id="dd307-124">What to know before you start</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dd307-125">用于安装 app-v 服务器的帐户</span><span class="sxs-lookup"><span data-stu-id="dd307-125">Account for installing the App-V Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="dd307-126">用于安装 app-v Server 组件的帐户必须具有：</span><span class="sxs-lookup"><span data-stu-id="dd307-126">The account that you use to install the App-V Server components must have:</span></span></p>
<ul>
<li><p><span data-ttu-id="dd307-127">要在其上安装组件的计算机上的管理员权限。</span><span class="sxs-lookup"><span data-stu-id="dd307-127">Administrative rights on the computer on which you are installing the components.</span></span></p></li>
<li><p><span data-ttu-id="dd307-128">查询 Active Directory 域服务的功能。</span><span class="sxs-lookup"><span data-stu-id="dd307-128">The ability to query Active Directory Domain Services.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="dd307-129">端口和防火墙</span><span class="sxs-lookup"><span data-stu-id="dd307-129">Port and firewall</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="dd307-130">指定将托管每个组件的端口。</span><span class="sxs-lookup"><span data-stu-id="dd307-130">Specify a port where each component will be hosted.</span></span></p></li>
<li><p><span data-ttu-id="dd307-131">添加关联的防火墙规则以允许传入请求到指定的端口。</span><span class="sxs-lookup"><span data-stu-id="dd307-131">Add the associated firewall rules to allow incoming requests to the specified ports.</span></span></p></li>
</ul>
<p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dd307-132">Web 分布式创作和版本控制（WebDAV）</span><span class="sxs-lookup"><span data-stu-id="dd307-132">Web Distributed Authoring and Versioning (WebDAV)</span></span></p></td>
<td align="left"><p><span data-ttu-id="dd307-133">自动为管理服务禁用 WebDAV。</span><span class="sxs-lookup"><span data-stu-id="dd307-133">WebDAV is automatically disabled for the Management Service.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="dd307-134">支持的部署方案</span><span class="sxs-lookup"><span data-stu-id="dd307-134">Supported deployment scenarios</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="dd307-135">一个独立部署，其中所有组件都部署在同一台服务器上。</span><span class="sxs-lookup"><span data-stu-id="dd307-135">A stand-alone deployment, where all components are deployed on the same server.</span></span></p></li>
<li><p><span data-ttu-id="dd307-136">分布式部署。</span><span class="sxs-lookup"><span data-stu-id="dd307-136">A distributed deployment.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dd307-137">不支持的部署方案</span><span class="sxs-lookup"><span data-stu-id="dd307-137">Unsupported deployment scenarios</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="dd307-138">在运行 app-v 的任何以前版本或组件的计算机上安装 app-v 服务器。</span><span class="sxs-lookup"><span data-stu-id="dd307-138">Installing the App-V Server on a computer that runs any previous version or component of App-V.</span></span></p></li>
<li><p><span data-ttu-id="dd307-139">在运行服务器核心或域控制器的计算机上安装 app-v 服务器组件。</span><span class="sxs-lookup"><span data-stu-id="dd307-139">Installing the App-V server components on a computer that runs server core or domain controller.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="dd307-140">管理服务器必备软件</span><span class="sxs-lookup"><span data-stu-id="dd307-140">Management server prerequisite software</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="dd307-141">先决条件和必需设置</span><span class="sxs-lookup"><span data-stu-id="dd307-141">Prerequisites and required settings</span></span></th>
<th align="left"><span data-ttu-id="dd307-142">详细信息</span><span class="sxs-lookup"><span data-stu-id="dd307-142">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dd307-143">SQL Server 支持的版本</span><span class="sxs-lookup"><span data-stu-id="dd307-143">Supported version of SQL Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="dd307-144">有关支持的版本，请参阅 <a href="app-v-50-sp3-supported-configurations.md" data-raw-source="[App-V 5.0 SP3 Supported Configurations](app-v-50-sp3-supported-configurations.md)"> App-V 5.0 SP3 支持 </a> 的配置。</span><span class="sxs-lookup"><span data-stu-id="dd307-144">For supported versions, see <a href="app-v-50-sp3-supported-configurations.md" data-raw-source="[App-V 5.0 SP3 Supported Configurations](app-v-50-sp3-supported-configurations.md)">App-V 5.0 SP3 Supported Configurations</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="https://www.microsoft.com//download/details.aspx?id=40773" data-raw-source="[Microsoft .NET Framework 4.5.1 (Web Installer)](https://www.microsoft.com//download/details.aspx?id=40773)"><span data-ttu-id="dd307-145">Microsoft .NET Framework 4.5.1 （Web 安装程序）</span><span class="sxs-lookup"><span data-stu-id="dd307-145">Microsoft .NET Framework 4.5.1 (Web Installer)</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="https://www.microsoft.com/download/details.aspx?id=34595" data-raw-source="[Windows PowerShell 3.0](https://www.microsoft.com/download/details.aspx?id=34595)"><span data-ttu-id="dd307-146">Windows PowerShell 3。0</span><span class="sxs-lookup"><span data-stu-id="dd307-146">Windows PowerShell 3.0</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="dd307-147">安装 PowerShell 3.0 需要重新启动。</span><span class="sxs-lookup"><span data-stu-id="dd307-147">Installing PowerShell 3.0 requires a restart.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="dd307-148">下载并安装 <a href="https://support.microsoft.com/kb/2533623" data-raw-source="[KB2533623](https://support.microsoft.com/kb/2533623)"> KB2533623</span><span class="sxs-lookup"><span data-stu-id="dd307-148">Download and install <a href="https://support.microsoft.com/kb/2533623" data-raw-source="[KB2533623](https://support.microsoft.com/kb/2533623)">KB2533623</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="dd307-149">仅适用于 Windows 7。</span><span class="sxs-lookup"><span data-stu-id="dd307-149">Applies to Windows 7 only.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="https://www.microsoft.com/download/details.aspx?id=40784" data-raw-source="[Visual C++ Redistributable Packages for Visual Studio 2013](https://www.microsoft.com/download/details.aspx?id=40784)"><span data-ttu-id="dd307-150">Visual Studio 2013 的 visual c + + 可再发行程序包</span><span class="sxs-lookup"><span data-stu-id="dd307-150">Visual C++ Redistributable Packages for Visual Studio 2013</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="dd307-151">64位 ASP.NET 注册</span><span class="sxs-lookup"><span data-stu-id="dd307-151">64-bit ASP.NET registration</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dd307-152">Windows Server Web 服务器角色</span><span class="sxs-lookup"><span data-stu-id="dd307-152">Windows Server Web Server Role</span></span></p></td>
<td align="left"><p><span data-ttu-id="dd307-153">此角色必须添加到管理服务器支持的服务器操作系统。</span><span class="sxs-lookup"><span data-stu-id="dd307-153">This role must be added to a server operating system that is supported for the Management server.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="dd307-154">Web 服务器（IIS）管理工具</span><span class="sxs-lookup"><span data-stu-id="dd307-154">Web Server (IIS) Management Tools</span></span></p></td>
<td align="left"><p><span data-ttu-id="dd307-155">单击 " <strong> IIS 管理脚本和工具" </strong> 。</span><span class="sxs-lookup"><span data-stu-id="dd307-155">Click <strong>IIS Management Scripts and Tools</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dd307-156">Web 服务器角色服务</span><span class="sxs-lookup"><span data-stu-id="dd307-156">Web Server Role Services</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="dd307-157">常见的 HTTP 功能：</span><span class="sxs-lookup"><span data-stu-id="dd307-157">Common HTTP Features:</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="dd307-158">静态内容</span><span class="sxs-lookup"><span data-stu-id="dd307-158">Static Content</span></span></p></li>
<li><p><span data-ttu-id="dd307-159">默认文档</span><span class="sxs-lookup"><span data-stu-id="dd307-159">Default Document</span></span></p></li>
</ul>
<p><strong><span data-ttu-id="dd307-160">应用程序开发：</span><span class="sxs-lookup"><span data-stu-id="dd307-160">Application Development:</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="dd307-161">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="dd307-161">ASP.NET</span></span></p></li>
<li><p><span data-ttu-id="dd307-162">.NET 扩展性</span><span class="sxs-lookup"><span data-stu-id="dd307-162">.NET Extensibility</span></span></p></li>
<li><p><span data-ttu-id="dd307-163">ISAPI 扩展</span><span class="sxs-lookup"><span data-stu-id="dd307-163">ISAPI Extensions</span></span></p></li>
<li><p><span data-ttu-id="dd307-164">ISAPI 筛选器</span><span class="sxs-lookup"><span data-stu-id="dd307-164">ISAPI Filters</span></span></p></li>
</ul>
<p><strong><span data-ttu-id="dd307-165">安全</span><span class="sxs-lookup"><span data-stu-id="dd307-165">Security:</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="dd307-166">Windows 身份验证</span><span class="sxs-lookup"><span data-stu-id="dd307-166">Windows Authentication</span></span></p></li>
<li><p><span data-ttu-id="dd307-167">请求筛选</span><span class="sxs-lookup"><span data-stu-id="dd307-167">Request Filtering</span></span></p></li>
</ul>
<p><strong><span data-ttu-id="dd307-168">管理工具：</span><span class="sxs-lookup"><span data-stu-id="dd307-168">Management Tools:</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="dd307-169">IIS 管理控制台</span><span class="sxs-lookup"><span data-stu-id="dd307-169">IIS Management Console</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="dd307-170">默认安装位置</span><span class="sxs-lookup"><span data-stu-id="dd307-170">Default installation location</span></span></p></td>
<td align="left"><p><span data-ttu-id="dd307-171">%PROGRAMFILES%\Microsoft 应用程序虚拟化服务器</span><span class="sxs-lookup"><span data-stu-id="dd307-171">%PROGRAMFILES%\Microsoft Application Virtualization Server</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dd307-172">管理数据库的位置</span><span class="sxs-lookup"><span data-stu-id="dd307-172">Location of the Management database</span></span></p></td>
<td align="left"><p><span data-ttu-id="dd307-173">SQL Server 数据库名称、SQL Server 数据库实例名称和数据库名称。</span><span class="sxs-lookup"><span data-stu-id="dd307-173">SQL Server database name, SQL Server database instance name, and database name.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="dd307-174">管理控制台和管理数据库权限</span><span class="sxs-lookup"><span data-stu-id="dd307-174">Management console and Management database permissions</span></span></p></td>
<td align="left"><p><span data-ttu-id="dd307-175">部署完成后可以访问管理控制台和数据库的用户或组。</span><span class="sxs-lookup"><span data-stu-id="dd307-175">A user or group that can access the Management console and database after the deployment is complete.</span></span> <span data-ttu-id="dd307-176">只有这些用户或组才能访问管理控制台和数据库，除非使用管理控制台添加其他管理员。</span><span class="sxs-lookup"><span data-stu-id="dd307-176">Only these users or groups will have access to the Management console and database unless additional administrators are added by using the Management console.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dd307-177">管理服务网站名称</span><span class="sxs-lookup"><span data-stu-id="dd307-177">Management service website name</span></span></p></td>
<td align="left"><p><span data-ttu-id="dd307-178">管理控制台网站的名称。</span><span class="sxs-lookup"><span data-stu-id="dd307-178">Name for the Management console website.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="dd307-179">管理服务端口绑定</span><span class="sxs-lookup"><span data-stu-id="dd307-179">Management service port binding</span></span></p></td>
<td align="left"><p><span data-ttu-id="dd307-180">管理服务的唯一端口号。</span><span class="sxs-lookup"><span data-stu-id="dd307-180">Unique port number for the Management service.</span></span> <span data-ttu-id="dd307-181">此端口不能由计算机上的另一个进程使用。</span><span class="sxs-lookup"><span data-stu-id="dd307-181">This port cannot be used by another process on the computer.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dd307-182">Microsoft Silverlight 5</span><span class="sxs-lookup"><span data-stu-id="dd307-182">Microsoft Silverlight 5</span></span></p></td>
<td align="left"><p><span data-ttu-id="dd307-183">只有安装了 Silverlight，管理控制台才可用。</span><span class="sxs-lookup"><span data-stu-id="dd307-183">The Management console is available only if Silverlight is installed.</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="dd307-184">管理服务器数据库必备软件</span><span class="sxs-lookup"><span data-stu-id="dd307-184">Management server database prerequisite software</span></span>

<span data-ttu-id="dd307-185">只有在使用 App-v 5.0 SP3 管理服务器时，才需要管理数据库。</span><span class="sxs-lookup"><span data-stu-id="dd307-185">The Management database is required only if you are using the App-V 5.0 SP3 Management server.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="dd307-186">先决条件和必需设置</span><span class="sxs-lookup"><span data-stu-id="dd307-186">Prerequisites and required settings</span></span></th>
<th align="left"><span data-ttu-id="dd307-187">详细信息</span><span class="sxs-lookup"><span data-stu-id="dd307-187">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><a href="https://www.microsoft.com//download/details.aspx?id=40773" data-raw-source="[Microsoft .NET Framework 4.5.1 (Web Installer)](https://www.microsoft.com//download/details.aspx?id=40773)"><span data-ttu-id="dd307-188">Microsoft .NET Framework 4.5.1 （Web 安装程序）</span><span class="sxs-lookup"><span data-stu-id="dd307-188">Microsoft .NET Framework 4.5.1 (Web Installer)</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="https://www.microsoft.com/download/details.aspx?id=40784" data-raw-source="[Visual C++ Redistributable Packages for Visual Studio 2013](https://www.microsoft.com/download/details.aspx?id=40784)"><span data-ttu-id="dd307-189">Visual Studio 2013 的 visual c + + 可再发行程序包</span><span class="sxs-lookup"><span data-stu-id="dd307-189">Visual C++ Redistributable Packages for Visual Studio 2013</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dd307-190">默认安装位置</span><span class="sxs-lookup"><span data-stu-id="dd307-190">Default installation location</span></span></p></td>
<td align="left"><p><span data-ttu-id="dd307-191">%PROGRAMFILES%\Microsoft 应用程序虚拟化服务器</span><span class="sxs-lookup"><span data-stu-id="dd307-191">%PROGRAMFILES%\Microsoft Application Virtualization Server</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="dd307-192">自定义 SQL Server 实例名称（如果适用）</span><span class="sxs-lookup"><span data-stu-id="dd307-192">Custom SQL Server instance name (if applicable)</span></span></p></td>
<td align="left"><p><span data-ttu-id="dd307-193">要使用的格式： <strong> INSTANCENAME</span><span class="sxs-lookup"><span data-stu-id="dd307-193">Format to use: <strong>INSTANCENAME</span></span></strong></p>
<p><span data-ttu-id="dd307-194">此格式基于安装位于本地计算机上的假设。</span><span class="sxs-lookup"><span data-stu-id="dd307-194">This format is based on the assumption that the installation is on the local computer.</span></span></p>
<p><span data-ttu-id="dd307-195">如果指定 SVR\INSTANCE 格式的名称 <strong> </strong> ，安装将失败。</span><span class="sxs-lookup"><span data-stu-id="dd307-195">If you specify the name with the format <strong>SVR\INSTANCE</strong>, the installation will fail.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dd307-196">自定义数据库名称（如果适用）</span><span class="sxs-lookup"><span data-stu-id="dd307-196">Custom database name (if applicable)</span></span></p></td>
<td align="left"><p><span data-ttu-id="dd307-197">唯一的数据库名称。</span><span class="sxs-lookup"><span data-stu-id="dd307-197">Unique database name.</span></span></p>
<p><span data-ttu-id="dd307-198">默认： AppVManagement</span><span class="sxs-lookup"><span data-stu-id="dd307-198">Default: AppVManagement</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="dd307-199">管理服务器位置</span><span class="sxs-lookup"><span data-stu-id="dd307-199">Management server location</span></span></p></td>
<td align="left"><p><span data-ttu-id="dd307-200">部署管理服务器的计算机帐户。</span><span class="sxs-lookup"><span data-stu-id="dd307-200">Machine account on which the Management server is deployed.</span></span></p>
<p><span data-ttu-id="dd307-201">要使用的格式： Domain\MachineAccount</span><span class="sxs-lookup"><span data-stu-id="dd307-201">Format to use: Domain\MachineAccount</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dd307-202">管理服务器安装管理员</span><span class="sxs-lookup"><span data-stu-id="dd307-202">Management server installation administrator</span></span></p></td>
<td align="left"><p><span data-ttu-id="dd307-203">用于安装管理服务器的帐户。</span><span class="sxs-lookup"><span data-stu-id="dd307-203">Account used to install the Management server.</span></span></p>
<p><span data-ttu-id="dd307-204">要使用的格式： Domain\AdministratorLoginName</span><span class="sxs-lookup"><span data-stu-id="dd307-204">Format to use: Domain\AdministratorLoginName</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="dd307-205">Microsoft SQL Server 服务代理</span><span class="sxs-lookup"><span data-stu-id="dd307-205">Microsoft SQL Server Service Agent</span></span></p></td>
<td align="left"><p><span data-ttu-id="dd307-206">配置管理数据库计算机，以便自动重新启动 Microsoft SQL Server 代理服务。</span><span class="sxs-lookup"><span data-stu-id="dd307-206">Configure the Management database computer so that the Microsoft SQL Server Agent service is restarted automatically.</span></span> <span data-ttu-id="dd307-207">有关说明，请参阅 <a href="https://technet.microsoft.com/magazine/gg313742.aspx" data-raw-source="[Configure SQL Server Agent to Restart Services Automatically](https://technet.microsoft.com/magazine/gg313742.aspx)"> 将 SQL Server 代理配置为自动重新启动服务 </a> 。</span><span class="sxs-lookup"><span data-stu-id="dd307-207">For instructions, see <a href="https://technet.microsoft.com/magazine/gg313742.aspx" data-raw-source="[Configure SQL Server Agent to Restart Services Automatically](https://technet.microsoft.com/magazine/gg313742.aspx)">Configure SQL Server Agent to Restart Services Automatically</a>.</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="dd307-208">发布服务器必备软件</span><span class="sxs-lookup"><span data-stu-id="dd307-208">Publishing server prerequisite software</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="dd307-209">先决条件和必需设置</span><span class="sxs-lookup"><span data-stu-id="dd307-209">Prerequisites and required settings</span></span></th>
<th align="left"><span data-ttu-id="dd307-210">详细信息</span><span class="sxs-lookup"><span data-stu-id="dd307-210">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><a href="https://www.microsoft.com//download/details.aspx?id=40773" data-raw-source="[Microsoft .NET Framework 4.5.1 (Web Installer)](https://www.microsoft.com//download/details.aspx?id=40773)"><span data-ttu-id="dd307-211">Microsoft .NET Framework 4.5.1 （Web 安装程序）</span><span class="sxs-lookup"><span data-stu-id="dd307-211">Microsoft .NET Framework 4.5.1 (Web Installer)</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="https://www.microsoft.com/download/details.aspx?id=40784" data-raw-source="[Visual C++ Redistributable Packages for Visual Studio 2013](https://www.microsoft.com/download/details.aspx?id=40784)"><span data-ttu-id="dd307-212">Visual Studio 2013 的 visual c + + 可再发行程序包</span><span class="sxs-lookup"><span data-stu-id="dd307-212">Visual C++ Redistributable Packages for Visual Studio 2013</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dd307-213">64位 ASP.NET 注册</span><span class="sxs-lookup"><span data-stu-id="dd307-213">64-bit ASP.NET registration</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="dd307-214">Windows Server Web 服务器角色</span><span class="sxs-lookup"><span data-stu-id="dd307-214">Windows Server Web Server Role</span></span></p></td>
<td align="left"><p><span data-ttu-id="dd307-215">此角色必须添加到管理服务器支持的服务器操作系统。</span><span class="sxs-lookup"><span data-stu-id="dd307-215">This role must be added to a server operating system that is supported for the Management server.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dd307-216">Web 服务器（IIS）管理工具</span><span class="sxs-lookup"><span data-stu-id="dd307-216">Web Server (IIS) Management Tools</span></span></p></td>
<td align="left"><p><span data-ttu-id="dd307-217">单击 " <strong> IIS 管理脚本和工具" </strong> 。</span><span class="sxs-lookup"><span data-stu-id="dd307-217">Click <strong>IIS Management Scripts and Tools</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="dd307-218">Web 服务器角色服务</span><span class="sxs-lookup"><span data-stu-id="dd307-218">Web Server Role Services</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="dd307-219">常见的 HTTP 功能：</span><span class="sxs-lookup"><span data-stu-id="dd307-219">Common HTTP Features:</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="dd307-220">静态内容</span><span class="sxs-lookup"><span data-stu-id="dd307-220">Static Content</span></span></p></li>
<li><p><span data-ttu-id="dd307-221">默认文档</span><span class="sxs-lookup"><span data-stu-id="dd307-221">Default Document</span></span></p></li>
</ul>
<p><strong><span data-ttu-id="dd307-222">应用程序开发：</span><span class="sxs-lookup"><span data-stu-id="dd307-222">Application Development:</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="dd307-223">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="dd307-223">ASP.NET</span></span></p></li>
<li><p><span data-ttu-id="dd307-224">.NET 扩展性</span><span class="sxs-lookup"><span data-stu-id="dd307-224">.NET Extensibility</span></span></p></li>
<li><p><span data-ttu-id="dd307-225">ISAPI 扩展</span><span class="sxs-lookup"><span data-stu-id="dd307-225">ISAPI Extensions</span></span></p></li>
<li><p><span data-ttu-id="dd307-226">ISAPI 筛选器</span><span class="sxs-lookup"><span data-stu-id="dd307-226">ISAPI Filters</span></span></p></li>
</ul>
<p><strong><span data-ttu-id="dd307-227">安全</span><span class="sxs-lookup"><span data-stu-id="dd307-227">Security:</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="dd307-228">Windows 身份验证</span><span class="sxs-lookup"><span data-stu-id="dd307-228">Windows Authentication</span></span></p></li>
<li><p><span data-ttu-id="dd307-229">请求筛选</span><span class="sxs-lookup"><span data-stu-id="dd307-229">Request Filtering</span></span></p></li>
</ul>
<p><strong><span data-ttu-id="dd307-230">管理工具：</span><span class="sxs-lookup"><span data-stu-id="dd307-230">Management Tools:</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="dd307-231">IIS 管理控制台</span><span class="sxs-lookup"><span data-stu-id="dd307-231">IIS Management Console</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dd307-232">默认安装位置</span><span class="sxs-lookup"><span data-stu-id="dd307-232">Default installation location</span></span></p></td>
<td align="left"><p><span data-ttu-id="dd307-233">%PROGRAMFILES%\Microsoft 应用程序虚拟化服务器</span><span class="sxs-lookup"><span data-stu-id="dd307-233">%PROGRAMFILES%\Microsoft Application Virtualization Server</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="dd307-234">管理服务 URL</span><span class="sxs-lookup"><span data-stu-id="dd307-234">Management service URL</span></span></p></td>
<td align="left"><p><span data-ttu-id="dd307-235">App-v 管理服务的 URL。</span><span class="sxs-lookup"><span data-stu-id="dd307-235">URL of the App-V Management service.</span></span> <span data-ttu-id="dd307-236">这是发布服务器与之通信的端口。</span><span class="sxs-lookup"><span data-stu-id="dd307-236">This is the port with which the Publishing server communicates.</span></span></p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="dd307-237">安装体系结构</span><span class="sxs-lookup"><span data-stu-id="dd307-237">Installation architecture</span></span></th>
<th align="left"><span data-ttu-id="dd307-238">要用于 URL 的格式</span><span class="sxs-lookup"><span data-stu-id="dd307-238">Format to use for the URL</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dd307-239">管理服务器和发布服务器安装在同一台服务器上</span><span class="sxs-lookup"><span data-stu-id="dd307-239">Management server and Publishing server are installed on the same server</span></span></p></td>
<td align="left"><p><a href="http://localhost:12345" data-raw-source="http://localhost:12345">http://localhost:12345</a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="dd307-240">管理服务器和发布服务器安装在不同的服务器上</span><span class="sxs-lookup"><span data-stu-id="dd307-240">Management server and Publishing server are installed on different servers</span></span></p></td>
<td align="left"><p><a href="http://MyAppvServer.MyDomain.com" data-raw-source="http://MyAppvServer.MyDomain.com">http://MyAppvServer.MyDomain.com</a></p></td>
</tr>
</tbody>
</table>
<p> </p>
<p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dd307-241">发布服务网站名称</span><span class="sxs-lookup"><span data-stu-id="dd307-241">Publishing service website name</span></span></p></td>
<td align="left"><p><span data-ttu-id="dd307-242">发布网站的名称。</span><span class="sxs-lookup"><span data-stu-id="dd307-242">Name for the Publishing website.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="dd307-243">发布服务端口绑定</span><span class="sxs-lookup"><span data-stu-id="dd307-243">Publishing service port binding</span></span></p></td>
<td align="left"><p><span data-ttu-id="dd307-244">发布服务的唯一端口号。</span><span class="sxs-lookup"><span data-stu-id="dd307-244">Unique port number for the Publishing service.</span></span> <span data-ttu-id="dd307-245">此端口不能由计算机上的另一个进程使用。</span><span class="sxs-lookup"><span data-stu-id="dd307-245">This port cannot be used by another process on the computer.</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="dd307-246">报告服务器必备软件</span><span class="sxs-lookup"><span data-stu-id="dd307-246">Reporting server prerequisite software</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="dd307-247">先决条件和必需设置</span><span class="sxs-lookup"><span data-stu-id="dd307-247">Prerequisites and required settings</span></span></th>
<th align="left"><span data-ttu-id="dd307-248">详细信息</span><span class="sxs-lookup"><span data-stu-id="dd307-248">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dd307-249">SQL Server 支持的版本</span><span class="sxs-lookup"><span data-stu-id="dd307-249">Supported version of SQL Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="dd307-250">有关支持的版本，请参阅 <a href="app-v-50-sp3-supported-configurations.md" data-raw-source="[App-V 5.0 SP3 Supported Configurations](app-v-50-sp3-supported-configurations.md)"> App-V 5.0 SP3 支持 </a> 的配置。</span><span class="sxs-lookup"><span data-stu-id="dd307-250">For supported versions, see <a href="app-v-50-sp3-supported-configurations.md" data-raw-source="[App-V 5.0 SP3 Supported Configurations](app-v-50-sp3-supported-configurations.md)">App-V 5.0 SP3 Supported Configurations</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="https://www.microsoft.com//download/details.aspx?id=40773" data-raw-source="[Microsoft .NET Framework 4.5.1 (Web Installer)](https://www.microsoft.com//download/details.aspx?id=40773)"><span data-ttu-id="dd307-251">Microsoft .NET Framework 4.5.1 （Web 安装程序）</span><span class="sxs-lookup"><span data-stu-id="dd307-251">Microsoft .NET Framework 4.5.1 (Web Installer)</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="https://www.microsoft.com/download/details.aspx?id=40784" data-raw-source="[Visual C++ Redistributable Packages for Visual Studio 2013](https://www.microsoft.com/download/details.aspx?id=40784)"><span data-ttu-id="dd307-252">Visual Studio 2013 的 visual c + + 可再发行程序包</span><span class="sxs-lookup"><span data-stu-id="dd307-252">Visual C++ Redistributable Packages for Visual Studio 2013</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="dd307-253">64位 ASP.NET 注册</span><span class="sxs-lookup"><span data-stu-id="dd307-253">64-bit ASP.NET registration</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dd307-254">Windows Server Web 服务器角色</span><span class="sxs-lookup"><span data-stu-id="dd307-254">Windows Server Web Server Role</span></span></p></td>
<td align="left"><p><span data-ttu-id="dd307-255">此角色必须添加到管理服务器支持的服务器操作系统。</span><span class="sxs-lookup"><span data-stu-id="dd307-255">This role must be added to a server operating system that is supported for the Management server.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="dd307-256">Web 服务器（IIS）管理工具</span><span class="sxs-lookup"><span data-stu-id="dd307-256">Web Server (IIS) Management Tools</span></span></p></td>
<td align="left"><p><span data-ttu-id="dd307-257">单击 " <strong> IIS 管理脚本和工具" </strong> 。</span><span class="sxs-lookup"><span data-stu-id="dd307-257">Click <strong>IIS Management Scripts and Tools</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dd307-258">Web 服务器角色服务</span><span class="sxs-lookup"><span data-stu-id="dd307-258">Web Server Role Services</span></span></p></td>
<td align="left"><p><span data-ttu-id="dd307-259">若要降低将不受欢迎或恶意数据发送到报告服务器的风险，应限制每个公司安全策略对报告 Web 服务的访问权限。</span><span class="sxs-lookup"><span data-stu-id="dd307-259">To reduce the risk of unwanted or malicious data being sent to the Reporting server, you should restrict access to the Reporting Web Service per your corporate security policy.</span></span></p>
<p><strong><span data-ttu-id="dd307-260">常见的 HTTP 功能：</span><span class="sxs-lookup"><span data-stu-id="dd307-260">Common HTTP Features:</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="dd307-261">静态内容</span><span class="sxs-lookup"><span data-stu-id="dd307-261">Static Content</span></span></p></li>
<li><p><span data-ttu-id="dd307-262">默认文档</span><span class="sxs-lookup"><span data-stu-id="dd307-262">Default Document</span></span></p></li>
</ul>
<p><strong><span data-ttu-id="dd307-263">应用程序开发：</span><span class="sxs-lookup"><span data-stu-id="dd307-263">Application Development:</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="dd307-264">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="dd307-264">ASP.NET</span></span></p></li>
<li><p><span data-ttu-id="dd307-265">.NET 扩展性</span><span class="sxs-lookup"><span data-stu-id="dd307-265">.NET Extensibility</span></span></p></li>
<li><p><span data-ttu-id="dd307-266">ISAPI 扩展</span><span class="sxs-lookup"><span data-stu-id="dd307-266">ISAPI Extensions</span></span></p></li>
<li><p><span data-ttu-id="dd307-267">ISAPI 筛选器</span><span class="sxs-lookup"><span data-stu-id="dd307-267">ISAPI Filters</span></span></p></li>
</ul>
<p><strong><span data-ttu-id="dd307-268">安全</span><span class="sxs-lookup"><span data-stu-id="dd307-268">Security:</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="dd307-269">Windows 身份验证</span><span class="sxs-lookup"><span data-stu-id="dd307-269">Windows Authentication</span></span></p></li>
<li><p><span data-ttu-id="dd307-270">请求筛选</span><span class="sxs-lookup"><span data-stu-id="dd307-270">Request Filtering</span></span></p></li>
</ul>
<p><strong><span data-ttu-id="dd307-271">管理工具：</span><span class="sxs-lookup"><span data-stu-id="dd307-271">Management Tools:</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="dd307-272">IIS 管理控制台</span><span class="sxs-lookup"><span data-stu-id="dd307-272">IIS Management Console</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="dd307-273">默认安装位置</span><span class="sxs-lookup"><span data-stu-id="dd307-273">Default installation location</span></span></p></td>
<td align="left"><p><span data-ttu-id="dd307-274">%PROGRAMFILES%\Microsoft 应用程序虚拟化服务器</span><span class="sxs-lookup"><span data-stu-id="dd307-274">%PROGRAMFILES%\Microsoft Application Virtualization Server</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dd307-275">报告服务网站名称</span><span class="sxs-lookup"><span data-stu-id="dd307-275">Reporting service website name</span></span></p></td>
<td align="left"><p><span data-ttu-id="dd307-276">报告网站的名称。</span><span class="sxs-lookup"><span data-stu-id="dd307-276">Name for the Reporting website.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="dd307-277">报告服务端口绑定</span><span class="sxs-lookup"><span data-stu-id="dd307-277">Reporting service port binding</span></span></p></td>
<td align="left"><p><span data-ttu-id="dd307-278">报告服务的唯一端口号。</span><span class="sxs-lookup"><span data-stu-id="dd307-278">Unique port number for the Reporting service.</span></span> <span data-ttu-id="dd307-279">此端口不能由计算机上的另一个进程使用。</span><span class="sxs-lookup"><span data-stu-id="dd307-279">This port cannot be used by another process on the computer.</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="dd307-280">报告数据库必备软件</span><span class="sxs-lookup"><span data-stu-id="dd307-280">Reporting database prerequisite software</span></span>

<span data-ttu-id="dd307-281">只有在使用 App-v 5.0 SP3 报告服务器时，才需要报告数据库。</span><span class="sxs-lookup"><span data-stu-id="dd307-281">The Reporting database is required only if you are using the App-V 5.0 SP3 Reporting server.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="dd307-282">先决条件和必需设置</span><span class="sxs-lookup"><span data-stu-id="dd307-282">Prerequisites and required settings</span></span></th>
<th align="left"><span data-ttu-id="dd307-283">详细信息</span><span class="sxs-lookup"><span data-stu-id="dd307-283">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><a href="https://www.microsoft.com//download/details.aspx?id=40773" data-raw-source="[Microsoft .NET Framework 4.5.1 (Web Installer)](https://www.microsoft.com//download/details.aspx?id=40773)"><span data-ttu-id="dd307-284">Microsoft .NET Framework 4.5.1 （Web 安装程序）</span><span class="sxs-lookup"><span data-stu-id="dd307-284">Microsoft .NET Framework 4.5.1 (Web Installer)</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="https://www.microsoft.com/download/details.aspx?id=40784" data-raw-source="[Visual C++ Redistributable Packages for Visual Studio 2013](https://www.microsoft.com/download/details.aspx?id=40784)"><span data-ttu-id="dd307-285">Visual Studio 2013 的 visual c + + 可再发行程序包</span><span class="sxs-lookup"><span data-stu-id="dd307-285">Visual C++ Redistributable Packages for Visual Studio 2013</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dd307-286">默认安装位置</span><span class="sxs-lookup"><span data-stu-id="dd307-286">Default installation location</span></span></p></td>
<td align="left"><p><span data-ttu-id="dd307-287">%PROGRAMFILES%\Microsoft 应用程序虚拟化服务器</span><span class="sxs-lookup"><span data-stu-id="dd307-287">%PROGRAMFILES%\Microsoft Application Virtualization Server</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="dd307-288">自定义 SQL Server 实例名称（如果适用）</span><span class="sxs-lookup"><span data-stu-id="dd307-288">Custom SQL Server instance name (if applicable)</span></span></p></td>
<td align="left"><p><span data-ttu-id="dd307-289">要使用的格式： <strong> INSTANCENAME</span><span class="sxs-lookup"><span data-stu-id="dd307-289">Format to use: <strong>INSTANCENAME</span></span></strong></p>
<p><span data-ttu-id="dd307-290">此格式基于安装位于本地计算机上的假设。</span><span class="sxs-lookup"><span data-stu-id="dd307-290">This format is based on the assumption that the installation is on the local computer.</span></span></p>
<p><span data-ttu-id="dd307-291">如果指定 SVR\INSTANCE 格式的名称 <strong> </strong> ，安装将失败。</span><span class="sxs-lookup"><span data-stu-id="dd307-291">If you specify the name with the format <strong>SVR\INSTANCE</strong>, the installation will fail.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dd307-292">自定义数据库名称（如果适用）</span><span class="sxs-lookup"><span data-stu-id="dd307-292">Custom database name (if applicable)</span></span></p></td>
<td align="left"><p><span data-ttu-id="dd307-293">唯一的数据库名称。</span><span class="sxs-lookup"><span data-stu-id="dd307-293">Unique database name.</span></span></p>
<p><span data-ttu-id="dd307-294">默认： AppVReporting</span><span class="sxs-lookup"><span data-stu-id="dd307-294">Default: AppVReporting</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="dd307-295">报表服务器位置</span><span class="sxs-lookup"><span data-stu-id="dd307-295">Reporting server location</span></span></p></td>
<td align="left"><p><span data-ttu-id="dd307-296">要在其上部署报告服务器的计算机帐户。</span><span class="sxs-lookup"><span data-stu-id="dd307-296">Machine account on which the Reporting server is deployed.</span></span></p>
<p><span data-ttu-id="dd307-297">要使用的格式： Domain\MachineAccount</span><span class="sxs-lookup"><span data-stu-id="dd307-297">Format to use: Domain\MachineAccount</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dd307-298">报表服务器安装管理员</span><span class="sxs-lookup"><span data-stu-id="dd307-298">Reporting server installation administrator</span></span></p></td>
<td align="left"><p><span data-ttu-id="dd307-299">用于安装报表服务器的帐户。</span><span class="sxs-lookup"><span data-stu-id="dd307-299">Account used to install the Reporting server.</span></span></p>
<p><span data-ttu-id="dd307-300">要使用的格式： Domain\AdministratorLoginName</span><span class="sxs-lookup"><span data-stu-id="dd307-300">Format to use: Domain\AdministratorLoginName</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="dd307-301">Microsoft SQL Server 服务和 Microsoft SQL Server 服务代理</span><span class="sxs-lookup"><span data-stu-id="dd307-301">Microsoft SQL Server Service and Microsoft SQL Server Service Agent</span></span></p></td>
<td align="left"><p><span data-ttu-id="dd307-302">将这些服务配置为与有权访问查询 AD DS 的用户帐户相关联。</span><span class="sxs-lookup"><span data-stu-id="dd307-302">Configure these services to be associated with user accounts that have access to query AD DS.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="dd307-303">App-v 客户端必备软件</span><span class="sxs-lookup"><span data-stu-id="dd307-303">App-V client prerequisite software</span></span>


<span data-ttu-id="dd307-304">为 App-v 客户端安装以下必备软件。</span><span class="sxs-lookup"><span data-stu-id="dd307-304">Install the following prerequisite software for the App-V client.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="dd307-305">必备</span><span class="sxs-lookup"><span data-stu-id="dd307-305">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="dd307-306">详细信息</span><span class="sxs-lookup"><span data-stu-id="dd307-306">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><a href="https://www.microsoft.com//download/details.aspx?id=40773" data-raw-source="[Microsoft .NET Framework 4.5.1 (Web Installer)](https://www.microsoft.com//download/details.aspx?id=40773)"><span data-ttu-id="dd307-307">Microsoft .NET Framework 4.5.1 （Web 安装程序）</span><span class="sxs-lookup"><span data-stu-id="dd307-307">Microsoft .NET Framework 4.5.1 (Web Installer)</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="https://www.microsoft.com/download/details.aspx?id=34595" data-raw-source="[Windows PowerShell 3.0](https://www.microsoft.com/download/details.aspx?id=34595)"><span data-ttu-id="dd307-308">Windows PowerShell 3。0</span><span class="sxs-lookup"><span data-stu-id="dd307-308">Windows PowerShell 3.0</span></span></a></p>
<p></p></td>
<td align="left"><p><span data-ttu-id="dd307-309">安装 PowerShell 3.0 需要重新启动。</span><span class="sxs-lookup"><span data-stu-id="dd307-309">Installing PowerShell 3.0 requires a restart.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="https://support.microsoft.com/kb/2533623" data-raw-source="[KB2533623](https://support.microsoft.com/kb/2533623)"><span data-ttu-id="dd307-310">KB2533623</span><span class="sxs-lookup"><span data-stu-id="dd307-310">KB2533623</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="dd307-311">仅适用于 Windows 7：下载并安装 KB。</span><span class="sxs-lookup"><span data-stu-id="dd307-311">Applies to Windows 7 only: Download and install the KB.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="https://www.microsoft.com/download/details.aspx?id=40784" data-raw-source="[Visual C++ Redistributable Packages for Visual Studio 2013](https://www.microsoft.com/download/details.aspx?id=40784)"><span data-ttu-id="dd307-312">Visual Studio 2013 的 visual c + + 可再发行程序包</span><span class="sxs-lookup"><span data-stu-id="dd307-312">Visual C++ Redistributable Packages for Visual Studio 2013</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="dd307-313">远程桌面服务客户端必备软件</span><span class="sxs-lookup"><span data-stu-id="dd307-313">Remote Desktop Services client prerequisite software</span></span>


<span data-ttu-id="dd307-314">为 App-v 远程桌面服务客户端安装以下必备软件。</span><span class="sxs-lookup"><span data-stu-id="dd307-314">Install the following prerequisite software for the App-V Remote Desktop Services client.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="dd307-315">必备</span><span class="sxs-lookup"><span data-stu-id="dd307-315">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="dd307-316">详细信息</span><span class="sxs-lookup"><span data-stu-id="dd307-316">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><a href="https://www.microsoft.com//download/details.aspx?id=40773" data-raw-source="[Microsoft .NET Framework 4.5.1 (Web Installer)](https://www.microsoft.com//download/details.aspx?id=40773)"><span data-ttu-id="dd307-317">Microsoft .NET Framework 4.5.1 （Web 安装程序）</span><span class="sxs-lookup"><span data-stu-id="dd307-317">Microsoft .NET Framework 4.5.1 (Web Installer)</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="https://www.microsoft.com/download/details.aspx?id=34595" data-raw-source="[Windows PowerShell 3.0](https://www.microsoft.com/download/details.aspx?id=34595)"><span data-ttu-id="dd307-318">Windows PowerShell 3。0</span><span class="sxs-lookup"><span data-stu-id="dd307-318">Windows PowerShell 3.0</span></span></a></p>
<p></p></td>
<td align="left"><p><span data-ttu-id="dd307-319">安装 PowerShell 3.0 需要重新启动。</span><span class="sxs-lookup"><span data-stu-id="dd307-319">Installing PowerShell 3.0 requires a restart.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="https://support.microsoft.com/kb/2533623" data-raw-source="[KB2533623](https://support.microsoft.com/kb/2533623)"><span data-ttu-id="dd307-320">KB2533623</span><span class="sxs-lookup"><span data-stu-id="dd307-320">KB2533623</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="dd307-321">仅适用于 Windows 7：下载并安装 KB。</span><span class="sxs-lookup"><span data-stu-id="dd307-321">Applies to Windows 7 only: Download and install the KB.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="https://www.microsoft.com/download/details.aspx?id=40784" data-raw-source="[Visual C++ Redistributable Packages for Visual Studio 2013](https://www.microsoft.com/download/details.aspx?id=40784)"><span data-ttu-id="dd307-322">Visual Studio 2013 的 visual c + + 可再发行程序包</span><span class="sxs-lookup"><span data-stu-id="dd307-322">Visual C++ Redistributable Packages for Visual Studio 2013</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="dd307-323">Sequencer 必备软件</span><span class="sxs-lookup"><span data-stu-id="dd307-323">Sequencer prerequisite software</span></span>


**<span data-ttu-id="dd307-324">安装先决条件之前应了解的事项：</span><span class="sxs-lookup"><span data-stu-id="dd307-324">What to know before installing the prerequisites:</span></span>**

-   <span data-ttu-id="dd307-325">最佳做法：运行 Sequencer 的计算机应具有与将运行虚拟应用程序的计算机相同的硬件和软件配置。</span><span class="sxs-lookup"><span data-stu-id="dd307-325">Best practice: The computer that runs the Sequencer should have the same hardware and software configurations as the computers that will run the virtual applications.</span></span>

-   <span data-ttu-id="dd307-326">排序过程占用大量资源，因此请确保运行排序器的计算机具有大量内存、快速处理器和快速硬盘。</span><span class="sxs-lookup"><span data-stu-id="dd307-326">The sequencing process is resource intensive, so make sure that the computer that runs the Sequencer has plenty of memory, a fast processor, and a fast hard drive.</span></span> <span data-ttu-id="dd307-327">本地安装的应用程序的系统要求不能超过 Sequencer 的系统要求。</span><span class="sxs-lookup"><span data-stu-id="dd307-327">The system requirements of locally installed applications cannot exceed those of the Sequencer.</span></span> <span data-ttu-id="dd307-328">有关详细信息，请参阅[App-V 5.0 支持的配置](app-v-50-supported-configurations.md)。</span><span class="sxs-lookup"><span data-stu-id="dd307-328">For more information, see [App-V 5.0 Supported Configurations](app-v-50-supported-configurations.md).</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="dd307-329">必备</span><span class="sxs-lookup"><span data-stu-id="dd307-329">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="dd307-330">详细信息</span><span class="sxs-lookup"><span data-stu-id="dd307-330">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><a href="https://www.microsoft.com//download/details.aspx?id=40773" data-raw-source="[Microsoft .NET Framework 4.5.1 (Web Installer)](https://www.microsoft.com//download/details.aspx?id=40773)"><span data-ttu-id="dd307-331">Microsoft .NET Framework 4.5.1 （Web 安装程序）</span><span class="sxs-lookup"><span data-stu-id="dd307-331">Microsoft .NET Framework 4.5.1 (Web Installer)</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="https://www.microsoft.com/download/details.aspx?id=34595" data-raw-source="[Windows PowerShell 3.0](https://www.microsoft.com/download/details.aspx?id=34595)"><span data-ttu-id="dd307-332">Windows PowerShell 3。0</span><span class="sxs-lookup"><span data-stu-id="dd307-332">Windows PowerShell 3.0</span></span></a></p>
<p></p></td>
<td align="left"><p><span data-ttu-id="dd307-333">安装 PowerShell 3.0 需要重新启动。</span><span class="sxs-lookup"><span data-stu-id="dd307-333">Installing PowerShell 3.0 requires a restart.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="https://support.microsoft.com/kb/2533623" data-raw-source="[KB2533623](https://support.microsoft.com/kb/2533623)"><span data-ttu-id="dd307-334">KB2533623</span><span class="sxs-lookup"><span data-stu-id="dd307-334">KB2533623</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="dd307-335">仅适用于 Windows 7：下载并安装 KB。</span><span class="sxs-lookup"><span data-stu-id="dd307-335">Applies to Windows 7 only: Download and install the KB.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="https://www.microsoft.com/download/details.aspx?id=40784" data-raw-source="[Visual C++ Redistributable Packages for Visual Studio 2013](https://www.microsoft.com/download/details.aspx?id=40784)"><span data-ttu-id="dd307-336">Visual Studio 2013 的 visual c + + 可再发行程序包</span><span class="sxs-lookup"><span data-stu-id="dd307-336">Visual C++ Redistributable Packages for Visual Studio 2013</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>








## <span data-ttu-id="dd307-337">相关主题</span><span class="sxs-lookup"><span data-stu-id="dd307-337">Related topics</span></span>


[<span data-ttu-id="dd307-338">计划 App-V 5.0</span><span class="sxs-lookup"><span data-stu-id="dd307-338">Planning for App-V 5.0</span></span>](planning-for-app-v-50-rc.md)

[<span data-ttu-id="dd307-339">App-V 5.0 SP3 支持的配置</span><span class="sxs-lookup"><span data-stu-id="dd307-339">App-V 5.0 SP3 Supported Configurations</span></span>](app-v-50-sp3-supported-configurations.md)









