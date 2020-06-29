---
title: 规划 MBAM 2.5 服务器部署
description: 规划 MBAM 2.5 服务器部署
author: dansimp
ms.assetid: 88774c89-31c8-4eb8-a845-a00bbec8c870
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d2ecb510fab821118ce210577f9ffb83c39be050
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803923"
---
# <span data-ttu-id="4e968-103">规划 MBAM 2.5 服务器部署</span><span class="sxs-lookup"><span data-stu-id="4e968-103">Planning for MBAM 2.5 Server Deployment</span></span>


<span data-ttu-id="4e968-104">本主题列出了为 MBAM 独立版和 Configuration Manager 拓扑部署的功能，并列出了部署这些拓扑所需的顺序。</span><span class="sxs-lookup"><span data-stu-id="4e968-104">This topic lists the features that you deploy for the MBAM Stand-alone and Configuration Manager topologies and lists the order in which you need to deploy them.</span></span> <span data-ttu-id="4e968-105">每个拓扑都有一个建议的配置。</span><span class="sxs-lookup"><span data-stu-id="4e968-105">There is a recommended configuration for each topology.</span></span> <span data-ttu-id="4e968-106">但是，你可以在不同的配置和多台服务器上配置 MBAM 服务器数据库和功能，具体取决于你的可伸缩性要求。</span><span class="sxs-lookup"><span data-stu-id="4e968-106">However, you can configure MBAM server databases and features in different configurations and across multiple servers, depending on your scalability requirements.</span></span>

## <span data-ttu-id="4e968-107">两种拓扑的重要规划注意事项</span><span class="sxs-lookup"><span data-stu-id="4e968-107">Important planning considerations for both topologies</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4e968-108">注意事项</span><span class="sxs-lookup"><span data-stu-id="4e968-108">Considerations</span></span></th>
<th align="left"><span data-ttu-id="4e968-109">详细信息或用途</span><span class="sxs-lookup"><span data-stu-id="4e968-109">Details or purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4e968-110">开始部署之前，请先查看以下内容：</span><span class="sxs-lookup"><span data-stu-id="4e968-110">Review the following before you start the deployment:</span></span></p>
<ul>
<li><p><a href="mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md" data-raw-source="[MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)"><span data-ttu-id="4e968-111">独立和 Configuration Manager 集成拓扑的 MBAM 2.5 服务器先决条件</span><span class="sxs-lookup"><span data-stu-id="4e968-111">MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies</span></span></a></p></li>
<li><p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)"><span data-ttu-id="4e968-112">MBAM 2.5 支持的配置</span><span class="sxs-lookup"><span data-stu-id="4e968-112">MBAM 2.5 Supported Configurations</span></span></a></p></li>
</ul></td>
<td align="left"><p><span data-ttu-id="4e968-113">每个 MBAM 功能都具有特定的先决条件，在开始 MBAM 安装之前必须满足这些先决条件。</span><span class="sxs-lookup"><span data-stu-id="4e968-113">Each MBAM feature has specific prerequisites that must be met before you start the MBAM installation.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4e968-114">MBAM 中的 BitLocker 恢复密钥在一次使用后过期。</span><span class="sxs-lookup"><span data-stu-id="4e968-114">BitLocker recovery keys in MBAM expire after a single use.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4e968-115">一次使用意味着已通过管理和监视网站（也称为帮助桌面）、自助服务门户或使用 <strong> MbamBitLockerRecoveryKey </strong> Windows PowerShell cmdlet 检索恢复密钥。</span><span class="sxs-lookup"><span data-stu-id="4e968-115">A single use means that the recovery key has been retrieved through the Administration and Monitoring Website (also known as Help Desk), Self-Service Portal, or by using the Get-<strong>MbamBitLockerRecoveryKey</strong> Windows PowerShell cmdlet.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4e968-116">跟踪配置每个功能的计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="4e968-116">Keep track of the names of the computers on which you configure each feature.</span></span> <span data-ttu-id="4e968-117">您将在整个配置过程中使用此信息。</span><span class="sxs-lookup"><span data-stu-id="4e968-117">You will use this information throughout the configuration process.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4e968-118">您可能希望使用 <a href="mbam-25-deployment-checklist.md" data-raw-source="[MBAM 2.5 Deployment Checklist](mbam-25-deployment-checklist.md)"> MBAM 2.5 部署清单 </a> 来实现此目的。</span><span class="sxs-lookup"><span data-stu-id="4e968-118">You may want to use the <a href="mbam-25-deployment-checklist.md" data-raw-source="[MBAM 2.5 Deployment Checklist](mbam-25-deployment-checklist.md)">MBAM 2.5 Deployment Checklist</a> for this purpose.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4e968-119">仅配置 MDOP MBAM （BitLocker Management）节点中的组策略设置。</span><span class="sxs-lookup"><span data-stu-id="4e968-119">Configure only the Group Policy settings in the MDOP MBAM (BitLocker Management) node.</span></span> <span data-ttu-id="4e968-120">不要更改 "BitLocker 驱动器加密" 节点中的组策略设置。</span><span class="sxs-lookup"><span data-stu-id="4e968-120">Do not change the Group Policy settings in the BitLocker Drive Encryption node.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4e968-121">如果更改了 BitLocker 驱动器加密节点中的组策略设置，MBAM 将不起作用。</span><span class="sxs-lookup"><span data-stu-id="4e968-121">If you change the Group Policy settings in the BitLocker Drive Encryption node, MBAM will not work.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="planning-for-mbam-server-deployment---stand-alone-topology"></a><span data-ttu-id="4e968-122">规划 MBAM Server 部署-独立拓扑</span><span class="sxs-lookup"><span data-stu-id="4e968-122">Planning for MBAM Server deployment – Stand-alone topology</span></span>


<span data-ttu-id="4e968-123">对于独立拓扑，建议对生产环境使用双服务器配置，尽管可以使用3到4台服务器的配置。</span><span class="sxs-lookup"><span data-stu-id="4e968-123">For the Stand-alone topology, a two-server configuration is recommended for production environments, although configurations of three to four servers can be used.</span></span>

<span data-ttu-id="4e968-124">MBAM 独立拓扑的服务器基础结构包含以下功能，这些功能必须按所列顺序进行配置：</span><span class="sxs-lookup"><span data-stu-id="4e968-124">The Server infrastructure for the MBAM Stand-alone topology contains the following features, which must be configured in the order listed:</span></span>

1.  <span data-ttu-id="4e968-125">数据库（合规性和审核数据库和恢复数据库）</span><span class="sxs-lookup"><span data-stu-id="4e968-125">Databases (Compliance and Audit Database and Recovery Database)</span></span>

2.  <span data-ttu-id="4e968-126">报告</span><span class="sxs-lookup"><span data-stu-id="4e968-126">Reports</span></span>

3.  <span data-ttu-id="4e968-127">Web 应用程序（及其相应的 web 服务）</span><span class="sxs-lookup"><span data-stu-id="4e968-127">Web applications (and their corresponding web services)</span></span>

    -   <span data-ttu-id="4e968-128">管理和监视网站</span><span class="sxs-lookup"><span data-stu-id="4e968-128">Administration and Monitoring Website</span></span>

    -   <span data-ttu-id="4e968-129">自助服务门户</span><span class="sxs-lookup"><span data-stu-id="4e968-129">Self-Service Portal</span></span>

<span data-ttu-id="4e968-130">有关这些功能的说明，请参阅[具有独立拓扑的 MBAM 2.5 的高级别体系结构](high-level-architecture-of-mbam-25-with-stand-alone-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="4e968-130">For a description of these features, see [High-Level Architecture of MBAM 2.5 with Stand-alone Topology](high-level-architecture-of-mbam-25-with-stand-alone-topology.md).</span></span>

## <a href="" id="planning-for-mbam-server-deployment---configuration-manager-topology"></a><span data-ttu-id="4e968-131">规划 MBAM Server 部署-配置管理器拓扑</span><span class="sxs-lookup"><span data-stu-id="4e968-131">Planning for MBAM Server deployment – Configuration Manager topology</span></span>


<span data-ttu-id="4e968-132">对于 Configuration Manager 集成拓扑，虽然可以使用其他服务器的配置，但对于生产环境，建议使用三服务器配置。</span><span class="sxs-lookup"><span data-stu-id="4e968-132">For the Configuration Manager Integration topology, a three-server configuration is recommended for production environments, although configurations of additional servers can be used.</span></span>

<span data-ttu-id="4e968-133">MBAM Configuration Manager 拓扑的服务器基础结构包含以下功能，这些功能必须按所列顺序进行配置或执行：</span><span class="sxs-lookup"><span data-stu-id="4e968-133">The Server infrastructure for the MBAM Configuration Manager topology contains the following features, which must be configured or performed in the order listed:</span></span>

1.  <span data-ttu-id="4e968-134">数据库（合规性和审核数据库和恢复数据库）</span><span class="sxs-lookup"><span data-stu-id="4e968-134">Databases (Compliance and Audit Database and Recovery Database)</span></span>

2.  <span data-ttu-id="4e968-135">报告</span><span class="sxs-lookup"><span data-stu-id="4e968-135">Reports</span></span>

3.  <span data-ttu-id="4e968-136">Web 应用程序（及其相应的 web 服务）</span><span class="sxs-lookup"><span data-stu-id="4e968-136">Web applications (and their corresponding web services)</span></span>

    -   <span data-ttu-id="4e968-137">管理和监视网站</span><span class="sxs-lookup"><span data-stu-id="4e968-137">Administration and Monitoring Website</span></span>

    -   <span data-ttu-id="4e968-138">自助服务门户</span><span class="sxs-lookup"><span data-stu-id="4e968-138">Self-Service Portal</span></span>

4.  <span data-ttu-id="4e968-139">System Center Configuration Manager 集成</span><span class="sxs-lookup"><span data-stu-id="4e968-139">System Center Configuration Manager Integration</span></span>

<span data-ttu-id="4e968-140">有关这些功能的说明，请参阅[具有 Configuration Manager 集成拓扑的 MBAM 2.5 的高级别体系结构](high-level-architecture-of-mbam-25-with-configuration-manager-integration-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="4e968-140">For a description of these features, see [High-Level Architecture of MBAM 2.5 with Configuration Manager Integration Topology](high-level-architecture-of-mbam-25-with-configuration-manager-integration-topology.md).</span></span>



## <span data-ttu-id="4e968-141">相关主题</span><span class="sxs-lookup"><span data-stu-id="4e968-141">Related topics</span></span>


[<span data-ttu-id="4e968-142">规划部署 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="4e968-142">Planning to Deploy MBAM 2.5</span></span>](planning-to-deploy-mbam-25.md)

[<span data-ttu-id="4e968-143">部署 MBAM 2.5 服务器基础结构</span><span class="sxs-lookup"><span data-stu-id="4e968-143">Deploying the MBAM 2.5 Server Infrastructure</span></span>](deploying-the-mbam-25-server-infrastructure.md)

 

## <span data-ttu-id="4e968-144">已获得 MBAM 的建议？</span><span class="sxs-lookup"><span data-stu-id="4e968-144">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="4e968-145">在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="4e968-145">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="4e968-146">对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="4e968-146">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





