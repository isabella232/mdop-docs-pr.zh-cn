---
title: 采用独立拓扑的 MBAM 2.5 的高级别体系结构
description: 采用独立拓扑的 MBAM 2.5 的高级别体系结构
author: dansimp
ms.assetid: 35f8c5f6-8be3-443d-baf0-56d68b08f3bc
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 75e878e24b4675f2f2f574791d0f06ecadd0196d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803992"
---
# <span data-ttu-id="da3a3-103">采用独立拓扑的 MBAM 2.5 的高级别体系结构</span><span class="sxs-lookup"><span data-stu-id="da3a3-103">High-Level Architecture of MBAM 2.5 with Stand-alone Topology</span></span>


<span data-ttu-id="da3a3-104">本主题介绍使用配置管理器独立拓扑部署 Microsoft BitLocker 管理和监视（MBAM）的推荐体系结构。</span><span class="sxs-lookup"><span data-stu-id="da3a3-104">This topic describes the recommended architecture for deploying Microsoft BitLocker Administration and Monitoring (MBAM) with the Configuration Manager Stand-alone topology.</span></span> <span data-ttu-id="da3a3-105">在此拓扑中，MBAM 作为独立的产品进行部署。</span><span class="sxs-lookup"><span data-stu-id="da3a3-105">In this topology, MBAM is deployed as a stand-alone product.</span></span> <span data-ttu-id="da3a3-106">也可以通过 Configuration Manager 集成拓扑（它将 MBAM 与 Configuration Manager 集成）部署 MBAM。</span><span class="sxs-lookup"><span data-stu-id="da3a3-106">You can alternatively deploy MBAM with the Configuration Manager Integration topology, which integrates MBAM with Configuration Manager.</span></span> <span data-ttu-id="da3a3-107">有关详细信息，请参阅[具有 Configuration Manager 集成拓扑的 MBAM 2.5 的高级别体系结构](high-level-architecture-of-mbam-25-with-configuration-manager-integration-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="da3a3-107">For more information, see [High-Level Architecture of MBAM 2.5 with Configuration Manager Integration Topology](high-level-architecture-of-mbam-25-with-configuration-manager-integration-topology.md).</span></span>

<span data-ttu-id="da3a3-108">有关本主题中所述软件的受支持版本的列表，请参阅[MBAM 2.5 支持的配置](mbam-25-supported-configurations.md)。</span><span class="sxs-lookup"><span data-stu-id="da3a3-108">For a list of the supported versions of the software mentioned in this topic, see [MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md).</span></span>

<span data-ttu-id="da3a3-109">**注意** 我们建议你仅在测试环境中使用单服务器体系结构。</span><span class="sxs-lookup"><span data-stu-id="da3a3-109">**Note** We recommend you use a single-server architecture in test environments only.</span></span>

 

## <span data-ttu-id="da3a3-110">推荐的服务器数和受支持的客户端数</span><span class="sxs-lookup"><span data-stu-id="da3a3-110">Recommended number of servers and supported number of clients</span></span>


<span data-ttu-id="da3a3-111">生产环境中推荐的服务器数和受支持的客户端数量如下所示：</span><span class="sxs-lookup"><span data-stu-id="da3a3-111">The recommended number of servers and supported number of clients in a production environment is as follows:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="da3a3-112">生产环境中的推荐体系结构</span><span class="sxs-lookup"><span data-stu-id="da3a3-112">Recommended architecture in a production environment</span></span></th>
<th align="left"><span data-ttu-id="da3a3-113">详细信息</span><span class="sxs-lookup"><span data-stu-id="da3a3-113">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="da3a3-114">服务器和其他计算机的数量</span><span class="sxs-lookup"><span data-stu-id="da3a3-114">Number of servers and other computers</span></span></p></td>
<td align="left"><p><span data-ttu-id="da3a3-115">两台服务器</span><span class="sxs-lookup"><span data-stu-id="da3a3-115">Two servers</span></span></p>
<p><span data-ttu-id="da3a3-116">一个工作站</span><span class="sxs-lookup"><span data-stu-id="da3a3-116">One workstation</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="da3a3-117">支持的客户端计算机数</span><span class="sxs-lookup"><span data-stu-id="da3a3-117">Number of client computers supported</span></span></p></td>
<td align="left"><p><span data-ttu-id="da3a3-118">500,000</span><span class="sxs-lookup"><span data-stu-id="da3a3-118">500,000</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="da3a3-119">使用独立拓扑的推荐 MBAM 高级别体系结构</span><span class="sxs-lookup"><span data-stu-id="da3a3-119">Recommended MBAM high-level architecture with the Stand-alone topology</span></span>


<span data-ttu-id="da3a3-120">下图和表介绍了推荐的高级别双服务器体系结构，MBAM 使用独立拓扑。</span><span class="sxs-lookup"><span data-stu-id="da3a3-120">The following diagram and table describe the recommended high-level, two-server architecture for MBAM with the Stand-alone topology.</span></span> <span data-ttu-id="da3a3-121">MBAM 多林部署需要单向或双向信任。</span><span class="sxs-lookup"><span data-stu-id="da3a3-121">MBAM multi-forest deployments require a one-way or two-way trust.</span></span> <span data-ttu-id="da3a3-122">单向信任要求服务器域信任客户端域。</span><span class="sxs-lookup"><span data-stu-id="da3a3-122">One-way trusts require that the server domain trusts the client domain.</span></span>

![mbam2](images/mbam2-5-2servers.png)

<span data-ttu-id="da3a3-124">要在此服务器上配置的服务器功能说明数据库服务器</span><span class="sxs-lookup"><span data-stu-id="da3a3-124">Server Features to configure on this server Description Database server</span></span>

<span data-ttu-id="da3a3-125">合规性和审核数据库</span><span class="sxs-lookup"><span data-stu-id="da3a3-125">Compliance and Audit Database</span></span>

<span data-ttu-id="da3a3-126">此功能在运行 Windows Server 和支持的 SQL Server 实例的服务器上配置。</span><span class="sxs-lookup"><span data-stu-id="da3a3-126">This feature is configured on a server running Windows Server and supported SQL Server instance.</span></span>

<span data-ttu-id="da3a3-127">**合规性和审核数据库**存储合规性数据，这些数据主要用于 SQL Server Reporting Services 主机的报表。</span><span class="sxs-lookup"><span data-stu-id="da3a3-127">The **Compliance and Audit Database** stores compliance data, which is used primarily for reports that SQL Server Reporting Services hosts.</span></span>

<span data-ttu-id="da3a3-128">恢复数据库</span><span class="sxs-lookup"><span data-stu-id="da3a3-128">Recovery Database</span></span>

<span data-ttu-id="da3a3-129">此功能在运行 Windows Server 和支持的 SQL Server 实例的服务器上配置。</span><span class="sxs-lookup"><span data-stu-id="da3a3-129">This feature is configured on a server running Windows Server and supported SQL Server instance.</span></span>

<span data-ttu-id="da3a3-130">**恢复数据库**存储从 MBAM 客户端计算机收集的恢复数据。</span><span class="sxs-lookup"><span data-stu-id="da3a3-130">The **Recovery Database** stores recovery data that is collected from MBAM client computers.</span></span>

<span data-ttu-id="da3a3-131">报告</span><span class="sxs-lookup"><span data-stu-id="da3a3-131">Reports</span></span>

<span data-ttu-id="da3a3-132">此功能在运行 Windows Server 和支持的 SQL Server 实例的服务器上配置。</span><span class="sxs-lookup"><span data-stu-id="da3a3-132">This feature is configured on a server running Windows Server and supported SQL Server instance.</span></span>

<span data-ttu-id="da3a3-133">**报告**提供有关您的企业中的客户端计算机的恢复审核和合规性状态数据。</span><span class="sxs-lookup"><span data-stu-id="da3a3-133">The **Reports** provide recovery audit and compliance status data about the client computers in your enterprise.</span></span> <span data-ttu-id="da3a3-134">你可以从 "管理" 和 "监视" 网站或直接从 SQL Server Reporting Services 访问报表。</span><span class="sxs-lookup"><span data-stu-id="da3a3-134">You can access the reports from the Administration and Monitoring Website or directly from SQL Server Reporting Services.</span></span>

<span data-ttu-id="da3a3-135">管理和监视服务器</span><span class="sxs-lookup"><span data-stu-id="da3a3-135">Administration and Monitoring Server</span></span>

<span data-ttu-id="da3a3-136">管理和监视网站</span><span class="sxs-lookup"><span data-stu-id="da3a3-136">Administration and Monitoring Website</span></span>

<span data-ttu-id="da3a3-137">此功能在运行 Windows Server 的计算机上配置。</span><span class="sxs-lookup"><span data-stu-id="da3a3-137">This feature is configured on a computer running Windows Server.</span></span>

<span data-ttu-id="da3a3-138">**管理和监视网站**用于：</span><span class="sxs-lookup"><span data-stu-id="da3a3-138">The **Administration and Monitoring Website** is used to:</span></span>

-   <span data-ttu-id="da3a3-139">当用户被锁定时，帮助最终用户重新获得对其计算机的访问权限。（此网站区域通常称为 "帮助桌面"。）</span><span class="sxs-lookup"><span data-stu-id="da3a3-139">Help end users regain access to their computers when they are locked out. (This area of the Website is commonly called the Help Desk.)</span></span>

-   <span data-ttu-id="da3a3-140">查看显示客户端计算机合规性状态和恢复活动的报告。</span><span class="sxs-lookup"><span data-stu-id="da3a3-140">View reports that show compliance status and recovery activity for client computers.</span></span>

<span data-ttu-id="da3a3-141">自助服务门户</span><span class="sxs-lookup"><span data-stu-id="da3a3-141">Self-Service Portal</span></span>

<span data-ttu-id="da3a3-142">此功能在运行 Windows Server 的计算机上配置。</span><span class="sxs-lookup"><span data-stu-id="da3a3-142">This feature is configured on a computer running Windows Server.</span></span>

<span data-ttu-id="da3a3-143">**自助服务门户**是一种网站，使客户端计算机上的最终用户能够独立登录到网站以获取恢复密钥（如果他们丢失或忘记其 BitLocker 密码）。</span><span class="sxs-lookup"><span data-stu-id="da3a3-143">The **Self-Service Portal** is a website that enables end users on client computers to independently log on to a website to get a recovery key if they lose or forget their BitLocker password.</span></span>

<span data-ttu-id="da3a3-144">监视此网站的 web 服务</span><span class="sxs-lookup"><span data-stu-id="da3a3-144">Monitoring web services for this website</span></span>

<span data-ttu-id="da3a3-145">此功能在运行 Windows Server 的计算机上配置。</span><span class="sxs-lookup"><span data-stu-id="da3a3-145">This feature is configured on a computer running Windows Server.</span></span>

<span data-ttu-id="da3a3-146">**监视 web 服务**由 MBAM 客户端和网站用于与数据库通信。</span><span class="sxs-lookup"><span data-stu-id="da3a3-146">The **monitoring web services** are used by the MBAM Client and the websites to communicate to the database.</span></span>

<span data-ttu-id="da3a3-147">**重要提示** 由于 MBAM 网站直接与恢复数据库通信，因此在 Microsoft BitLocker 管理和监视（MBAM） 2.5 SP1 中不再提供监视 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="da3a3-147">**Important** The Monitoring Web Service is no longer available in Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 SP1 since the MBAM websites communicate directly with the Recovery Database.</span></span>

 

<span data-ttu-id="da3a3-148">管理工作站</span><span class="sxs-lookup"><span data-stu-id="da3a3-148">Management workstation</span></span>

<span data-ttu-id="da3a3-149">MBAM 组策略模板</span><span class="sxs-lookup"><span data-stu-id="da3a3-149">MBAM Group Policy Templates</span></span>

-   <span data-ttu-id="da3a3-150">MBAM 组策略模板是定义 MBAM 的实现设置的组策略设置，使你能够管理 BitLocker 驱动器加密。</span><span class="sxs-lookup"><span data-stu-id="da3a3-150">The MBAM Group Policy Templates are Group Policy settings that define implementation settings for MBAM, which enable you to manage BitLocker Drive Encryption.</span></span>

-   <span data-ttu-id="da3a3-151">在运行 MBAM 之前，你必须从[如何获取 MDOP 组策略（admx）模板](https://go.microsoft.com/fwlink/p/?LinkId=393941)中下载组策略模板，并将其复制到运行受支持的 Windows Server 或 Windows 操作系统的服务器或工作站。</span><span class="sxs-lookup"><span data-stu-id="da3a3-151">Before you run MBAM, you must download the Group Policy Templates from [How to Get MDOP Group Policy (.admx) Templates](https://go.microsoft.com/fwlink/p/?LinkId=393941) and copy them to a server or workstation that is running a supported Windows Server or Windows operating system.</span></span>

-   <span data-ttu-id="da3a3-152">工作站不必是专用计算机。</span><span class="sxs-lookup"><span data-stu-id="da3a3-152">The workstation does not have to be a dedicated computer.</span></span>

<span data-ttu-id="da3a3-153">MBAM 客户端和 Configuration Manager 客户端计算机</span><span class="sxs-lookup"><span data-stu-id="da3a3-153">MBAM Client and Configuration Manager client computer</span></span>

<span data-ttu-id="da3a3-154">MBAM 客户端软件</span><span class="sxs-lookup"><span data-stu-id="da3a3-154">MBAM Client software</span></span>

<span data-ttu-id="da3a3-155">MBAM 客户端：</span><span class="sxs-lookup"><span data-stu-id="da3a3-155">The MBAM Client:</span></span>

-   <span data-ttu-id="da3a3-156">使用组策略对象对企业中的客户端计算机强制执行 BitLocker 驱动器加密。</span><span class="sxs-lookup"><span data-stu-id="da3a3-156">Uses Group Policy Objects to enforce BitLocker Drive Encryption on client computers in the enterprise.</span></span>

-   <span data-ttu-id="da3a3-157">收集三种数据驱动器类型的 Bitlocker 恢复密钥：操作系统驱动器、固定数据驱动器和可移动（USB）数据驱动器。</span><span class="sxs-lookup"><span data-stu-id="da3a3-157">Collects the Bitlocker recovery key for three data drive types: operating system drives, fixed data drives, and removable (USB) data drives.</span></span>

-   <span data-ttu-id="da3a3-158">收集有关客户端计算机的恢复信息和计算机信息。</span><span class="sxs-lookup"><span data-stu-id="da3a3-158">Collects recovery information and computer information about the client computers.</span></span>



## <span data-ttu-id="da3a3-159">相关主题</span><span class="sxs-lookup"><span data-stu-id="da3a3-159">Related topics</span></span>


[<span data-ttu-id="da3a3-160">MBAM 2.5 入门</span><span class="sxs-lookup"><span data-stu-id="da3a3-160">Getting Started with MBAM 2.5</span></span>](getting-started-with-mbam-25.md)

[<span data-ttu-id="da3a3-161">采用 Configuration Manager 集成拓扑的 MBAM 2.5 的高级别体系结构</span><span class="sxs-lookup"><span data-stu-id="da3a3-161">High-Level Architecture of MBAM 2.5 with Configuration Manager Integration Topology</span></span>](high-level-architecture-of-mbam-25-with-configuration-manager-integration-topology.md)

[<span data-ttu-id="da3a3-162">图示 MBAM 2.5 部署的功能</span><span class="sxs-lookup"><span data-stu-id="da3a3-162">Illustrated Features of an MBAM 2.5 Deployment</span></span>](illustrated-features-of-an-mbam-25-deployment.md)

 

## <span data-ttu-id="da3a3-163">已获得 MBAM 的建议？</span><span class="sxs-lookup"><span data-stu-id="da3a3-163">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="da3a3-164">在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="da3a3-164">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="da3a3-165">对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="da3a3-165">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





