---
title: 图示 MBAM 2.5 部署的功能
description: 图示 MBAM 2.5 部署的功能
author: dansimp
ms.assetid: 7b5eff42-af8c-4bd0-a20a-18cc2e779f01
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/15/2018
ms.openlocfilehash: c3b205d4f0b4b18cf8bdbf51982b5a59e5e1b9d5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798035"
---
# <span data-ttu-id="50b1b-103">图示 MBAM 2.5 部署的功能</span><span class="sxs-lookup"><span data-stu-id="50b1b-103">Illustrated Features of an MBAM 2.5 Deployment</span></span>


<span data-ttu-id="50b1b-104">本主题介绍了组成以下拓扑的 Microsoft BitLocker 管理和监视（MBAM）2.5 部署的各个功能：</span><span class="sxs-lookup"><span data-stu-id="50b1b-104">This topic describes the individual features that make up a Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 deployment for the following topologies:</span></span>

-   <span data-ttu-id="50b1b-105">MBAM 独立</span><span class="sxs-lookup"><span data-stu-id="50b1b-105">MBAM Stand-alone</span></span>

-   <span data-ttu-id="50b1b-106">System Center Configuration Manager 集成</span><span class="sxs-lookup"><span data-stu-id="50b1b-106">System Center Configuration Manager Integration</span></span>

**<span data-ttu-id="50b1b-107">重要提示</span><span class="sxs-lookup"><span data-stu-id="50b1b-107">Important</span></span>**  
<span data-ttu-id="50b1b-108">这些功能不表示用于部署 MBAM 的推荐体系结构。</span><span class="sxs-lookup"><span data-stu-id="50b1b-108">These features do not represent the recommended architecture for deploying MBAM.</span></span> <span data-ttu-id="50b1b-109">仅将此信息用作了解组成 MBAM 部署的各个功能的指南。</span><span class="sxs-lookup"><span data-stu-id="50b1b-109">Use this information only as a guide to understand the individual features that make up an MBAM deployment.</span></span> <span data-ttu-id="50b1b-110">请参阅适用于 MBAM 的推荐体系结构的[MBAM 2.5 的高级别体系结构](high-level-architecture-for-mbam-25.md)。</span><span class="sxs-lookup"><span data-stu-id="50b1b-110">See [High-Level Architecture for MBAM 2.5](high-level-architecture-for-mbam-25.md) for the recommended architecture for MBAM.</span></span>



<span data-ttu-id="50b1b-111">有关本主题中所述软件的受支持版本的列表，请参阅[MBAM 2.5 支持的配置](mbam-25-supported-configurations.md)。</span><span class="sxs-lookup"><span data-stu-id="50b1b-111">For a list of the supported versions of the software mentioned in this topic, see [MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md).</span></span>

## <a href="" id="bkmk-standalone"></a> <span data-ttu-id="50b1b-112">MBAM 独立拓扑</span><span class="sxs-lookup"><span data-stu-id="50b1b-112">MBAM Stand-alone topology</span></span>


<span data-ttu-id="50b1b-113">以下图像和表介绍了 MBAM 独立拓扑中的功能。</span><span class="sxs-lookup"><span data-stu-id="50b1b-113">The following image and table explain the features in an MBAM Stand-alone topology.</span></span>

![mbab2\-5](images/mbam2-5-standalonecomponents.png)

|<span data-ttu-id="50b1b-115">功能类型</span><span class="sxs-lookup"><span data-stu-id="50b1b-115">Feature type</span></span>|<span data-ttu-id="50b1b-116">描述</span><span class="sxs-lookup"><span data-stu-id="50b1b-116">Description</span></span>|<span data-ttu-id="50b1b-117">数据库</span><span class="sxs-lookup"><span data-stu-id="50b1b-117">Database</span></span>|
|-|-|-|
|<span data-ttu-id="50b1b-118">恢复数据库</span><span class="sxs-lookup"><span data-stu-id="50b1b-118">Recovery Database</span></span>|<span data-ttu-id="50b1b-119">此数据库存储从 MBAM 客户端计算机收集的恢复数据。</span><span class="sxs-lookup"><span data-stu-id="50b1b-119">This database stores recovery data that is collected from MBAM client computers.</span></span>|<span data-ttu-id="50b1b-120">此功能在运行 Windows Server 和支持的 SQL Server 实例的服务器上配置。</span><span class="sxs-lookup"><span data-stu-id="50b1b-120">This feature is configured on a server running Windows Server and a supported SQL Server instance.</span></span>|
|<span data-ttu-id="50b1b-121">合规性和审核数据库</span><span class="sxs-lookup"><span data-stu-id="50b1b-121">Compliance and Audit Database</span></span>|<span data-ttu-id="50b1b-122">此数据库存储合规性数据，该数据主要用于 SQL Server Reporting Services 主机的报表。</span><span class="sxs-lookup"><span data-stu-id="50b1b-122">This database stores compliance data, which is used primarily for the Reports that SQL Server Reporting Services hosts.</span></span>|<span data-ttu-id="50b1b-123">此功能在运行 Windows Server 和支持的 SQL Server 实例的服务器上配置。</span><span class="sxs-lookup"><span data-stu-id="50b1b-123">This feature is configured on a server running Windows Server and a supported SQL Server instance.</span></span>|
|<span data-ttu-id="50b1b-124">合规性和审核报告</span><span class="sxs-lookup"><span data-stu-id="50b1b-124">Compliance and Audit Reports</span></span>|||
|<span data-ttu-id="50b1b-125">报表 Web 服务</span><span class="sxs-lookup"><span data-stu-id="50b1b-125">Reporting Web Service</span></span>|<span data-ttu-id="50b1b-126">此 web 服务支持管理和监视网站与存储报告数据的 SQL Server 实例之间的通信。</span><span class="sxs-lookup"><span data-stu-id="50b1b-126">This web service enables communication between the Administration and Monitoring Website and the SQL Server instance where reporting data is stored.</span></span>|<span data-ttu-id="50b1b-127">此功能安装在运行 Windows Server 的服务器上。</span><span class="sxs-lookup"><span data-stu-id="50b1b-127">This feature is installed on a server running Windows Server.</span></span>|
|<span data-ttu-id="50b1b-128">报告网站（管理和监视网站）</span><span class="sxs-lookup"><span data-stu-id="50b1b-128">Reporting Website (Administration and Monitoring Website)</span></span>|<span data-ttu-id="50b1b-129">可从 "管理和监视" 网站查看报表。</span><span class="sxs-lookup"><span data-stu-id="50b1b-129">You view Reports from the Administration and Monitoring Website.</span></span> <span data-ttu-id="50b1b-130">报告提供有关您的企业中的客户端计算机的恢复审核和合规性状态数据。</span><span class="sxs-lookup"><span data-stu-id="50b1b-130">The Reports provide recovery audit and compliance status data about the client computers in your enterprise.</span></span>|<span data-ttu-id="50b1b-131">此功能在运行 Windows Server 的服务器上配置。</span><span class="sxs-lookup"><span data-stu-id="50b1b-131">This feature is configured on a server running Windows Server.</span></span>|
|<span data-ttu-id="50b1b-132">SQL Server Reporting Services （SSRS）</span><span class="sxs-lookup"><span data-stu-id="50b1b-132">SQL Server Reporting Services (SSRS)</span></span>|<span data-ttu-id="50b1b-133">在 SSRS 数据库实例中配置报表。</span><span class="sxs-lookup"><span data-stu-id="50b1b-133">Reports are configured in an SSRS database instance.</span></span> <span data-ttu-id="50b1b-134">可以直接从 SSRS 或管理和监视网站查看报表。</span><span class="sxs-lookup"><span data-stu-id="50b1b-134">Reports can be viewed directly from SSRS or from the Administration and Monitoring Website.</span></span>|<span data-ttu-id="50b1b-135">此功能在运行 Windows Server 的服务器上配置，并且在运行 SSRS 的受支持的 SQL Server 实例上配置。</span><span class="sxs-lookup"><span data-stu-id="50b1b-135">This feature is configured on a server running Windows Server and a supported SQL Server instance that is running SSRS.</span></span>|
|<span data-ttu-id="50b1b-136">自助服务服务器</span><span class="sxs-lookup"><span data-stu-id="50b1b-136">Self-Service Server</span></span>|||
|<span data-ttu-id="50b1b-137">自助服务 Web 服务</span><span class="sxs-lookup"><span data-stu-id="50b1b-137">Self-Service Web Service</span></span>|<span data-ttu-id="50b1b-138">此 web 服务由 MBAM 客户端和管理和监控网站和自助服务门户使用，用于与恢复数据库通信。</span><span class="sxs-lookup"><span data-stu-id="50b1b-138">This web service is used by the MBAM Client and the Administration and Monitoring Website and Self-Service Portal to communicate to the Recovery Database.</span></span>|<span data-ttu-id="50b1b-139">此功能安装在运行 Windows Server 的计算机上。</span><span class="sxs-lookup"><span data-stu-id="50b1b-139">This feature is installed on a computer running Windows Server.</span></span>|
|<span data-ttu-id="50b1b-140">自助服务网站（自助服务门户）</span><span class="sxs-lookup"><span data-stu-id="50b1b-140">Self-Service Website (Self-Service Portal)</span></span>|<span data-ttu-id="50b1b-141">此网站使客户端计算机上的最终用户能够独立登录到网站，以便在丢失或忘记其 BitLocker 密码时获取恢复密钥。</span><span class="sxs-lookup"><span data-stu-id="50b1b-141">This website enables end users on client computers to independently sign in to a website to get a recovery key if they lose or forget their BitLocker password.</span></span>|<span data-ttu-id="50b1b-142">此功能在运行 Windows Server 的计算机上配置。</span><span class="sxs-lookup"><span data-stu-id="50b1b-142">This feature is configured on a computer running Windows Server.</span></span>|
|<span data-ttu-id="50b1b-143">管理和监视服务器</span><span class="sxs-lookup"><span data-stu-id="50b1b-143">Administration and Monitoring Server</span></span>|||
|<span data-ttu-id="50b1b-144">管理和监视 Web 服务</span><span class="sxs-lookup"><span data-stu-id="50b1b-144">Administration and Monitoring Web Service</span></span>|<span data-ttu-id="50b1b-145">监视 Web 服务由 MBAM 客户端和网站用于与数据库通信。</span><span class="sxs-lookup"><span data-stu-id="50b1b-145">The Monitoring Web Service is used by the MBAM Client and the websites to communicate to the databases.</span></span>|<span data-ttu-id="50b1b-146">此功能安装在运行 Windows Server 的计算机上。</span><span class="sxs-lookup"><span data-stu-id="50b1b-146">This feature is installed on a computer running Windows Server.</span></span>|

**<span data-ttu-id="50b1b-147">重要提示</span><span class="sxs-lookup"><span data-stu-id="50b1b-147">Important</span></span>**  
<span data-ttu-id="50b1b-148">自助服务 Web 服务在 Microsoft BitLocker 管理和监视（MBAM） 2.5 SP1 中不再可用，其中 MBAM 客户端、管理和监视网站以及自助服务门户直接与恢复数据库进行通信。</span><span class="sxs-lookup"><span data-stu-id="50b1b-148">The Self-Service Web Service is no longer available in Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 SP1, in which the MBAM Client, the Administration and Monitoring Website, and the Self-Service Portal communicate directly with the Recovery Database.</span></span>

**<span data-ttu-id="50b1b-149">重要提示</span><span class="sxs-lookup"><span data-stu-id="50b1b-149">Important</span></span>**  
<span data-ttu-id="50b1b-150">由于 MBAM 客户端和网站直接与恢复数据库通信，因此在 Microsoft BitLocker 管理和监视（MBAM） 2.5 SP1 中不再提供监视 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="50b1b-150">The Monitoring Web Service is no longer available in Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 SP1 since the MBAM Client and the websites communicate directly with the Recovery Database.</span></span>


## <a href="" id="bkmk-cmintegrated"></a><span data-ttu-id="50b1b-151">System Center Configuration Manager 集成拓扑</span><span class="sxs-lookup"><span data-stu-id="50b1b-151">System Center Configuration Manager Integration topology</span></span>

<span data-ttu-id="50b1b-152">以下图像和表介绍了 System Center Configuration Manager 集成拓扑中的功能。</span><span class="sxs-lookup"><span data-stu-id="50b1b-152">The following image and table explain the features in the System Center Configuration Manager Integration topology.</span></span>

![mbam2\-5](images/mbam2-5-cmcomponents.png)

**<span data-ttu-id="50b1b-154">重要提示</span><span class="sxs-lookup"><span data-stu-id="50b1b-154">Important</span></span>**  
<span data-ttu-id="50b1b-155">自助服务 Web 服务在 Microsoft BitLocker 管理和监视（MBAM） 2.5 SP1 中不再可用，其中 MBAM 客户端、管理和监视网站以及自助服务门户直接与恢复数据库进行通信。</span><span class="sxs-lookup"><span data-stu-id="50b1b-155">The Self-Service Web Service is no longer available in Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 SP1, in which the MBAM Client, the Administration and Monitoring Website, and the Self-Service Portal communicate directly with the Recovery Database.</span></span>

**<span data-ttu-id="50b1b-156">警告</span><span class="sxs-lookup"><span data-stu-id="50b1b-156">Warning</span></span>**  
<span data-ttu-id="50b1b-157">由于 MBAM 客户端和网站直接与恢复数据库通信，因此在 Microsoft BitLocker 管理和监视（MBAM） 2.5 SP1 中不再提供监视 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="50b1b-157">The Monitoring Web Service is no longer available in Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 SP1 since the MBAM Client and the websites communicate directly with the Recovery Database.</span></span>


|                        <span data-ttu-id="50b1b-158">功能类型</span><span class="sxs-lookup"><span data-stu-id="50b1b-158">Feature type</span></span>                        |                                                                                                    <span data-ttu-id="50b1b-159">描述</span><span class="sxs-lookup"><span data-stu-id="50b1b-159">Description</span></span>                                                                                                    |
|------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                    <span data-ttu-id="50b1b-160">自助服务服务器</span><span class="sxs-lookup"><span data-stu-id="50b1b-160">Self-Service Server</span></span>                     |                                                                                                                                                                                                                   |
|                  <span data-ttu-id="50b1b-161">自助服务 Web 服务</span><span class="sxs-lookup"><span data-stu-id="50b1b-161">Self-Service Web Service</span></span>                  |                                                 <span data-ttu-id="50b1b-162">此 web 服务由 MBAM 客户端和自助服务门户用于与恢复数据库通信。</span><span class="sxs-lookup"><span data-stu-id="50b1b-162">This web service is used by the MBAM Client and the Self-Service Portal to communicate to the Recovery Database.</span></span>                                                  |
|                    <span data-ttu-id="50b1b-163">自助服务网站</span><span class="sxs-lookup"><span data-stu-id="50b1b-163">Self-Service Website</span></span>                    |                          <span data-ttu-id="50b1b-164">此网站使客户端计算机上的最终用户能够独立登录到网站，以便在丢失或忘记其 BitLocker 密码时获取恢复密钥。</span><span class="sxs-lookup"><span data-stu-id="50b1b-164">This website enables end users on client computers to independently sign in to a website to get a recovery key if they lose or forget their BitLocker password.</span></span>                          |
| <span data-ttu-id="50b1b-165">管理和监视服务器/恢复审核报告</span><span class="sxs-lookup"><span data-stu-id="50b1b-165">Administration and Monitoring Server/Recovery Audit Report</span></span> |                                                                                                                                                                                                                   |
|         <span data-ttu-id="50b1b-166">管理和监视 Web 服务</span><span class="sxs-lookup"><span data-stu-id="50b1b-166">Administration and Monitoring Web Service</span></span>          |                               <span data-ttu-id="50b1b-167">此 web 服务支持管理和监视网站与存储报告数据的 SQL Server 数据库之间的通信。</span><span class="sxs-lookup"><span data-stu-id="50b1b-167">This web service enables communication between the Administration and Monitoring Website and the SQL Server databases where reporting data is stored.</span></span>                               |
|           <span data-ttu-id="50b1b-168">管理和监视网站</span><span class="sxs-lookup"><span data-stu-id="50b1b-168">Administration and Monitoring Website</span></span>            | <span data-ttu-id="50b1b-169">可通过管理和监视网站查看恢复审核报告。</span><span class="sxs-lookup"><span data-stu-id="50b1b-169">The Recovery Audit report is viewed from the Administration and Monitoring Website.</span></span> <span data-ttu-id="50b1b-170">使用 Configuration Manager 控制台查看所有其他报表，或直接从 SQL Server Reporting Services 查看报表。</span><span class="sxs-lookup"><span data-stu-id="50b1b-170">Use the Configuration Manager console to view all other reports, or view reports directly from SQL Server Reporting Services.</span></span> |
|                         <span data-ttu-id="50b1b-171">数据库</span><span class="sxs-lookup"><span data-stu-id="50b1b-171">Databases</span></span>                          |                                                                                                                                                                                                                   |
|                     <span data-ttu-id="50b1b-172">恢复数据库</span><span class="sxs-lookup"><span data-stu-id="50b1b-172">Recovery Database</span></span>                      |                                                                 <span data-ttu-id="50b1b-173">此数据库存储从 MBAM 客户端计算机收集的恢复数据。</span><span class="sxs-lookup"><span data-stu-id="50b1b-173">This database stores recovery data that is collected from MBAM client computers.</span></span>                                                                  |
|                       <span data-ttu-id="50b1b-174">审核数据库</span><span class="sxs-lookup"><span data-stu-id="50b1b-174">Audit Database</span></span>                       |                                                                   <span data-ttu-id="50b1b-175">此数据库存储有关恢复尝试和活动的审核信息。</span><span class="sxs-lookup"><span data-stu-id="50b1b-175">This database stores audit information about recovery attempts and activity.</span></span>                                                                    |
|               <span data-ttu-id="50b1b-176">配置管理器功能</span><span class="sxs-lookup"><span data-stu-id="50b1b-176">Configuration Manager Features</span></span>               |                                                                                                                                                                                                                   |
|          <span data-ttu-id="50b1b-177">Configuration Manager 管理控制台</span><span class="sxs-lookup"><span data-stu-id="50b1b-177">Configuration Manager Management console</span></span>          |                                                                   <span data-ttu-id="50b1b-178">此控制台内置于 Configuration Manager 中，用于查看报表。</span><span class="sxs-lookup"><span data-stu-id="50b1b-178">This console is built into Configuration Manager and is used to view reports.</span></span>                                                                   |
|               <span data-ttu-id="50b1b-179">配置管理器报告</span><span class="sxs-lookup"><span data-stu-id="50b1b-179">Configuration Manager Reports</span></span>                |                                                             <span data-ttu-id="50b1b-180">报表显示企业版客户端计算机的合规性和恢复审核数据。</span><span class="sxs-lookup"><span data-stu-id="50b1b-180">Reports show compliance and recovery audit data for client computers in your enterprise.</span></span>                                                              |
|               <span data-ttu-id="50b1b-181">SQL Server Reporting Services</span><span class="sxs-lookup"><span data-stu-id="50b1b-181">SQL Server Reporting Services</span></span>                |                                                <span data-ttu-id="50b1b-182">SSRS 启用 MBAM 报表。</span><span class="sxs-lookup"><span data-stu-id="50b1b-182">SSRS enables the MBAM Reports.</span></span> <span data-ttu-id="50b1b-183">可以直接从 SSRS 或配置管理器控制台查看报表。</span><span class="sxs-lookup"><span data-stu-id="50b1b-183">Reports can be viewed directly from SSRS or from the Configuration Manager console.</span></span>                                                 |

## <span data-ttu-id="50b1b-184">相关主题</span><span class="sxs-lookup"><span data-stu-id="50b1b-184">Related topics</span></span>

[<span data-ttu-id="50b1b-185">MBAM 2.5 的高级别体系结构</span><span class="sxs-lookup"><span data-stu-id="50b1b-185">High-Level Architecture for MBAM 2.5</span></span>](high-level-architecture-for-mbam-25.md)

[<span data-ttu-id="50b1b-186">MBAM 2.5 入门</span><span class="sxs-lookup"><span data-stu-id="50b1b-186">Getting Started with MBAM 2.5</span></span>](getting-started-with-mbam-25.md)

## <span data-ttu-id="50b1b-187">已获得 MBAM 的建议？</span><span class="sxs-lookup"><span data-stu-id="50b1b-187">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="50b1b-188">在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="50b1b-188">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="50b1b-189">对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="50b1b-189">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>




