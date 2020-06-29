---
title: MBAM 1.0 部署先决条件
description: MBAM 1.0 部署先决条件
author: dansimp
ms.assetid: bd9e1010-7d25-43e7-8dc6-b521226a659d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6ed14343d37a859364bcabbe6ca72c041502a23c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803213"
---
# <span data-ttu-id="0e30b-103">MBAM 1.0 部署先决条件</span><span class="sxs-lookup"><span data-stu-id="0e30b-103">MBAM 1.0 Deployment Prerequisites</span></span>


<span data-ttu-id="0e30b-104">在开始 Microsoft BitLocker 管理和监视（MBAM）安装之前，请确保满足安装该产品所必需的先决条件。</span><span class="sxs-lookup"><span data-stu-id="0e30b-104">Before you begin the Microsoft BitLocker Administration and Monitoring (MBAM) Setup, make sure that you meet the necessary prerequisites to install the product.</span></span> <span data-ttu-id="0e30b-105">本部分包含的信息可帮助你在部署 MBAM 客户端和服务器功能之前成功准备你的计算环境。</span><span class="sxs-lookup"><span data-stu-id="0e30b-105">This section contains information to help you successfully prepare your computing environment before you deploy the MBAM Clients and Server features.</span></span>

## <span data-ttu-id="0e30b-106">MBAM 服务器功能的安装先决条件</span><span class="sxs-lookup"><span data-stu-id="0e30b-106">Installation prerequisites for MBAM Server features</span></span>


<span data-ttu-id="0e30b-107">每个 MBAM 服务器功能都具有特定的先决条件，必须先满足这些先决条件，然后才能成功安装它们。</span><span class="sxs-lookup"><span data-stu-id="0e30b-107">Each of the MBAM server features has specific prerequisites that must be met before they can be successfully installed.</span></span> <span data-ttu-id="0e30b-108">MBAM 安装程序将验证在安装开始之前是否满足所有先决条件。</span><span class="sxs-lookup"><span data-stu-id="0e30b-108">MBAM Setup verifies if all prerequisites are met before the installation starts.</span></span>

### <span data-ttu-id="0e30b-109">管理和监视服务器的安装先决条件</span><span class="sxs-lookup"><span data-stu-id="0e30b-109">Installation prerequisites for Administration and Monitoring Server</span></span>

<span data-ttu-id="0e30b-110">下表包含 MBAM 管理和监视服务器的安装先决条件：</span><span class="sxs-lookup"><span data-stu-id="0e30b-110">The following table contains the installation prerequisites for the MBAM Administration and Monitoring Server:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="0e30b-111">必备</span><span class="sxs-lookup"><span data-stu-id="0e30b-111">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="0e30b-112">详细信息</span><span class="sxs-lookup"><span data-stu-id="0e30b-112">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="0e30b-113">Windows ServerWeb 服务器角色</span><span class="sxs-lookup"><span data-stu-id="0e30b-113">Windows ServerWeb Server Role</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="0e30b-114">此角色必须添加到 mbam 管理和监视服务器功能支持的服务器操作系统。</span><span class="sxs-lookup"><span data-stu-id="0e30b-114">This role must be added to a server operating system supported for the mbam Administration and Monitoring Server feature.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="0e30b-115">Web 服务器（IIS）管理工具</span><span class="sxs-lookup"><span data-stu-id="0e30b-115">Web Server (IIS) Management Tools</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="0e30b-116">IIS 管理脚本和工具</span><span class="sxs-lookup"><span data-stu-id="0e30b-116">IIS Management Scripts and Tools</span></span></strong></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="0e30b-117">Web 服务器角色服务</span><span class="sxs-lookup"><span data-stu-id="0e30b-117">Web Server Role Services</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="0e30b-118">常见的 HTTP 功能：</span><span class="sxs-lookup"><span data-stu-id="0e30b-118">Common HTTP Features:</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="0e30b-119">静态内容</span><span class="sxs-lookup"><span data-stu-id="0e30b-119">Static Content</span></span></p></li>
<li><p><span data-ttu-id="0e30b-120">默认文档</span><span class="sxs-lookup"><span data-stu-id="0e30b-120">Default Document</span></span></p></li>
</ul>
<p><strong><span data-ttu-id="0e30b-121">应用程序开发：</span><span class="sxs-lookup"><span data-stu-id="0e30b-121">Application Development:</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="0e30b-122">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="0e30b-122">ASP.NET</span></span></p></li>
<li><p><span data-ttu-id="0e30b-123">.NET 扩展性</span><span class="sxs-lookup"><span data-stu-id="0e30b-123">.NET Extensibility</span></span></p></li>
<li><p><span data-ttu-id="0e30b-124">ISAPI 扩展</span><span class="sxs-lookup"><span data-stu-id="0e30b-124">ISAPI Extensions</span></span></p></li>
<li><p><span data-ttu-id="0e30b-125">ISAPI 筛选器</span><span class="sxs-lookup"><span data-stu-id="0e30b-125">ISAPI Filters</span></span></p></li>
</ul>
<p><strong><span data-ttu-id="0e30b-126">安全</span><span class="sxs-lookup"><span data-stu-id="0e30b-126">Security:</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="0e30b-127">Windows 身份验证</span><span class="sxs-lookup"><span data-stu-id="0e30b-127">Windows Authentication</span></span></p></li>
<li><p><span data-ttu-id="0e30b-128">请求筛选</span><span class="sxs-lookup"><span data-stu-id="0e30b-128">Request Filtering</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="0e30b-129">Windows Server 功能</span><span class="sxs-lookup"><span data-stu-id="0e30b-129">Windows Server Features</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="0e30b-130">Microsoft .NET Framework 3.5.1 功能：</span><span class="sxs-lookup"><span data-stu-id="0e30b-130">Microsoft .NET Framework 3.5.1 features:</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="0e30b-131">.NET Framework 3.5。1</span><span class="sxs-lookup"><span data-stu-id="0e30b-131">.NET Framework 3.5.1</span></span></p></li>
<li><p><span data-ttu-id="0e30b-132">WCF 激活</span><span class="sxs-lookup"><span data-stu-id="0e30b-132">WCF Activation</span></span></p>
<ul>
<li><p><span data-ttu-id="0e30b-133">HTTP 激活</span><span class="sxs-lookup"><span data-stu-id="0e30b-133">HTTP Activation</span></span></p></li>
<li><p><span data-ttu-id="0e30b-134">非 HTTP 激活</span><span class="sxs-lookup"><span data-stu-id="0e30b-134">Non-HTTP Activation</span></span></p></li>
</ul></li>
</ul>
<p><strong><span data-ttu-id="0e30b-135">Windows Process Activation Service</span><span class="sxs-lookup"><span data-stu-id="0e30b-135">Windows Process Activation Service</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="0e30b-136">流程模型</span><span class="sxs-lookup"><span data-stu-id="0e30b-136">Process Model</span></span></p></li>
<li><p><span data-ttu-id="0e30b-137">.NET 环境</span><span class="sxs-lookup"><span data-stu-id="0e30b-137">.NET Environment</span></span></p></li>
<li><p><span data-ttu-id="0e30b-138">配置 Api</span><span class="sxs-lookup"><span data-stu-id="0e30b-138">Configuration APIs</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="0e30b-139">**注意** 有关受支持的操作系统的列表，请参阅[MBAM 1.0 支持的配置](mbam-10-supported-configurations.md)。</span><span class="sxs-lookup"><span data-stu-id="0e30b-139">**Note** For a list of supported operating systems, see [MBAM 1.0 Supported Configurations](mbam-10-supported-configurations.md).</span></span>

 

### <span data-ttu-id="0e30b-140">合规性和审核报告的安装先决条件</span><span class="sxs-lookup"><span data-stu-id="0e30b-140">Installation prerequisites for the Compliance and Audit Reports</span></span>

<span data-ttu-id="0e30b-141">必须在支持的 SQLServer 版本上安装合规性和审核报告。</span><span class="sxs-lookup"><span data-stu-id="0e30b-141">The Compliance and Audit Reports must be installed on a supported version of SQLServer.</span></span> <span data-ttu-id="0e30b-142">此功能的安装先决条件包括 SQL Server Reporting Services （SSRS）。</span><span class="sxs-lookup"><span data-stu-id="0e30b-142">Installation prerequisites for this feature include SQL Server Reporting Services (SSRS).</span></span>

<span data-ttu-id="0e30b-143">在 MBAM 服务器安装期间，必须安装并运行 SSRS。</span><span class="sxs-lookup"><span data-stu-id="0e30b-143">SSRS must be installed and running during MBAM server installation.</span></span> <span data-ttu-id="0e30b-144">SSRS 还应在 "本机" 模式下配置，而不是在 "未配置" 或 "SharePoint" 模式下进行配置。</span><span class="sxs-lookup"><span data-stu-id="0e30b-144">SSRS should also be configured in “native” mode, not in the “unconfigured” or “SharePoint” mode.</span></span>

<span data-ttu-id="0e30b-145">**注意** 有关受支持的操作系统和 SQLServer 版本的列表，请参阅[MBAM 1.0 支持的配置](mbam-10-supported-configurations.md)。</span><span class="sxs-lookup"><span data-stu-id="0e30b-145">**Note** For a list of supported operating systems and SQLServer versions, see [MBAM 1.0 Supported Configurations](mbam-10-supported-configurations.md).</span></span>

 

### <span data-ttu-id="0e30b-146">恢复和硬件数据库的安装先决条件</span><span class="sxs-lookup"><span data-stu-id="0e30b-146">Installation prerequisites for the Recovery and Hardware Database</span></span>

<span data-ttu-id="0e30b-147">恢复和硬件数据库必须安装在支持的 SQLServer 版本上。</span><span class="sxs-lookup"><span data-stu-id="0e30b-147">The Recovery and Hardware Database must be installed on a supported version of SQLServer.</span></span>

<span data-ttu-id="0e30b-148">SQL Server 必须在 MBAM 服务器安装期间安装并运行数据库引擎服务。</span><span class="sxs-lookup"><span data-stu-id="0e30b-148">SQL Server must have Database Engine Services installed and running during the MBAM server installation.</span></span> <span data-ttu-id="0e30b-149">必须启用透明数据加密（TDE）功能。</span><span class="sxs-lookup"><span data-stu-id="0e30b-149">The Transparent Data Encryption (TDE) feature must be enabled.</span></span>

<span data-ttu-id="0e30b-150">**注意** 有关受支持的操作系统和 SQLServer 版本的列表，请参阅[MBAM 1.0 支持的配置](mbam-10-supported-configurations.md)。</span><span class="sxs-lookup"><span data-stu-id="0e30b-150">**Note** For a list of supported operating systems and SQLServer versions, see [MBAM 1.0 Supported Configurations](mbam-10-supported-configurations.md).</span></span>

 

<span data-ttu-id="0e30b-151">TDE SQLServer 功能执行实时输入/输出（i/o）加密以及数据和日志文件的解密。</span><span class="sxs-lookup"><span data-stu-id="0e30b-151">The TDE SQLServer feature performs real-time input/output (I/O) encryption and decryption of the data and log files.</span></span> <span data-ttu-id="0e30b-152">TDE 保护 "静止" 数据，其中包括数据和日志文件。</span><span class="sxs-lookup"><span data-stu-id="0e30b-152">TDE protects data that is "at rest,” which include the data and the log files.</span></span> <span data-ttu-id="0e30b-153">它使您能够遵守各种行业中建立的许多法律、法规和指南。</span><span class="sxs-lookup"><span data-stu-id="0e30b-153">It provides the ability to comply with many laws, regulations, and guidelines that are established in various industries.</span></span>

<span data-ttu-id="0e30b-154">**注意** 由于 TDE 执行数据库信息的实时解密，因此，当你登录时所用的帐户在你查看恢复密钥信息 SQL 表时具有数据库的权限时，将显示恢复密钥信息。</span><span class="sxs-lookup"><span data-stu-id="0e30b-154">**Note** Because TDE performs real-time decryption of database information, the recovery key information will be visible if the account under which you are logged in has permissions to the database when you view the recovery key information SQL tables.</span></span>

 

### <span data-ttu-id="0e30b-155">符合性和审核数据库的安装先决条件</span><span class="sxs-lookup"><span data-stu-id="0e30b-155">Installation prerequisites for the Compliance and Audit Database</span></span>

<span data-ttu-id="0e30b-156">合规性和审核数据库必须安装在支持的 SQLServer 版本上。</span><span class="sxs-lookup"><span data-stu-id="0e30b-156">The Compliance and Audit Database must be installed on a supported version of SQLServer.</span></span>

<span data-ttu-id="0e30b-157">在 MBAM 服务器安装期间，SQL Server 必须安装并运行数据库引擎服务。</span><span class="sxs-lookup"><span data-stu-id="0e30b-157">SQL Server must have Database Engine Services installed and running during MBAM server installation.</span></span>

<span data-ttu-id="0e30b-158">**注意** 有关受支持的操作系统和 SQLServer 版本的列表，请参阅[MBAM 1.0 支持的配置](mbam-10-supported-configurations.md)。</span><span class="sxs-lookup"><span data-stu-id="0e30b-158">**Note** For a list of supported operating systems and SQLServer versions, see [MBAM 1.0 Supported Configurations](mbam-10-supported-configurations.md).</span></span>

 

## <span data-ttu-id="0e30b-159">MBAM 客户端的安装先决条件</span><span class="sxs-lookup"><span data-stu-id="0e30b-159">Installation prerequisites for MBAM Clients</span></span>


<span data-ttu-id="0e30b-160">开始 MBAM 客户端安装之前必须满足的必需先决条件如下所示：</span><span class="sxs-lookup"><span data-stu-id="0e30b-160">The necessary prerequisites that you must meet before you begin the MBAM Client installation are the following:</span></span>

-   <span data-ttu-id="0e30b-161">受信任的平台模块（TPM） v 1.2 功能</span><span class="sxs-lookup"><span data-stu-id="0e30b-161">Trusted Platform Module (TPM) v1.2 capability</span></span>

-   <span data-ttu-id="0e30b-162">TPM 芯片必须在 BIOS 中打开，并且必须从操作系统 resettable。</span><span class="sxs-lookup"><span data-stu-id="0e30b-162">The TPM chip must be turned on in the BIOS and it must be resettable from the operating system.</span></span> <span data-ttu-id="0e30b-163">有关详细信息，请参阅 BIOS 文档。</span><span class="sxs-lookup"><span data-stu-id="0e30b-163">For more information, see the BIOS documentation.</span></span>

<span data-ttu-id="0e30b-164">**警告** 确保键盘、鼠标和视频直接连接到计算机，而不是键盘、视频、鼠标（KVM）开关。</span><span class="sxs-lookup"><span data-stu-id="0e30b-164">**Warning** Ensure that the keyboard, mouse, and video are directly connected to the computer, instead of to a keyboard, video, mouse (KVM) switch.</span></span> <span data-ttu-id="0e30b-165">KVM 切换器可能会干扰计算机检测硬件实际存在的能力。</span><span class="sxs-lookup"><span data-stu-id="0e30b-165">A KVM switch can interfere with the ability of the computer to detect the physical presence of hardware.</span></span>

 

## <span data-ttu-id="0e30b-166">相关主题</span><span class="sxs-lookup"><span data-stu-id="0e30b-166">Related topics</span></span>


[<span data-ttu-id="0e30b-167">计划部署 MBAM 1.0</span><span class="sxs-lookup"><span data-stu-id="0e30b-167">Planning to Deploy MBAM 1.0</span></span>](planning-to-deploy-mbam-10.md)

[<span data-ttu-id="0e30b-168">MBAM 1.0 支持的配置</span><span class="sxs-lookup"><span data-stu-id="0e30b-168">MBAM 1.0 Supported Configurations</span></span>](mbam-10-supported-configurations.md)

 

 





