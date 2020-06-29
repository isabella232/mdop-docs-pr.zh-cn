---
title: MBAM 2.5 规划清单
description: MBAM 2.5 规划清单
author: dansimp
ms.assetid: ffe11eb8-44db-4886-8300-6dffec8bcfa4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 505f2890d67f36056ab5bb87df2a894473cd3306
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803989"
---
# <span data-ttu-id="9cd62-103">MBAM 2.5 规划清单</span><span class="sxs-lookup"><span data-stu-id="9cd62-103">MBAM 2.5 Planning Checklist</span></span>


<span data-ttu-id="9cd62-104">你可以使用以下清单帮助你准备用于 Microsoft BitLocker 管理和监视（MBAM）部署的计算环境。</span><span class="sxs-lookup"><span data-stu-id="9cd62-104">You can use the following checklists to help you prepare your computing environment for the Microsoft BitLocker Administration and Monitoring (MBAM) deployment.</span></span> <span data-ttu-id="9cd62-105">清单在规划部署时提供要考虑的项目的高级列表。</span><span class="sxs-lookup"><span data-stu-id="9cd62-105">The checklists provide a high-level list of items to consider when planning the deployment.</span></span> <span data-ttu-id="9cd62-106">独立拓扑和配置管理器集成拓扑有单独的清单。</span><span class="sxs-lookup"><span data-stu-id="9cd62-106">There are separate checklists for the Stand-alone topology and the Configuration Manager Integration topology.</span></span> <span data-ttu-id="9cd62-107">您可能希望将所需清单复制到电子表格中，并对其进行自定义以供使用。</span><span class="sxs-lookup"><span data-stu-id="9cd62-107">You might want to copy the desired checklist into a spreadsheet and customize it for your use.</span></span>

**<span data-ttu-id="9cd62-108">MBAM 部署规划清单</span><span class="sxs-lookup"><span data-stu-id="9cd62-108">Planning checklist for an MBAM deployment</span></span>**

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left"><span data-ttu-id="9cd62-109">任务</span><span class="sxs-lookup"><span data-stu-id="9cd62-109">Task</span></span></th>
<th align="left"><span data-ttu-id="9cd62-110">引用</span><span class="sxs-lookup"><span data-stu-id="9cd62-110">References</span></span></th>
<th align="left"><span data-ttu-id="9cd62-111">注释</span><span class="sxs-lookup"><span data-stu-id="9cd62-111">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="9cd62-112">&quot; &quot; 开始部署规划之前，查看入门信息以了解产品。</span><span class="sxs-lookup"><span data-stu-id="9cd62-112">Review the &quot;Getting started&quot; information to understand the product before you start deployment planning.</span></span></p></td>
<td align="left"><p><a href="getting-started-with-mbam-25.md" data-raw-source="[Getting Started with MBAM 2.5](getting-started-with-mbam-25.md)"><span data-ttu-id="9cd62-113">MBAM 2.5 入门</span><span class="sxs-lookup"><span data-stu-id="9cd62-113">Getting Started with MBAM 2.5</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="9cd62-114">查看 MBAM 部署的推荐高级别体系结构。</span><span class="sxs-lookup"><span data-stu-id="9cd62-114">Review the recommended high-level architecture for an MBAM deployment.</span></span> <span data-ttu-id="9cd62-115">您可能还希望查看 MBAM 部署的单个部件（数据库、网站、报表）的插图和说明。</span><span class="sxs-lookup"><span data-stu-id="9cd62-115">You might also want to review an illustration and description of the individual parts (databases, websites, Reports) of an MBAM deployment.</span></span></p></td>
<td align="left"><p><a href="high-level-architecture-for-mbam-25.md" data-raw-source="[High-Level Architecture for MBAM 2.5](high-level-architecture-for-mbam-25.md)"><span data-ttu-id="9cd62-116">MBAM 2.5 的高级别体系结构</span><span class="sxs-lookup"><span data-stu-id="9cd62-116">High-Level Architecture for MBAM 2.5</span></span></a></p>
<p><a href="illustrated-features-of-an-mbam-25-deployment.md" data-raw-source="[Illustrated Features of an MBAM 2.5 Deployment](illustrated-features-of-an-mbam-25-deployment.md)"><span data-ttu-id="9cd62-117">图示 MBAM 2.5 部署的功能</span><span class="sxs-lookup"><span data-stu-id="9cd62-117">Illustrated Features of an MBAM 2.5 Deployment</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="9cd62-118">查看并完成 MBAM 独立和 Configuration Manager 集成拓扑的先决条件。</span><span class="sxs-lookup"><span data-stu-id="9cd62-118">Review and complete the prerequisites for the MBAM Stand-alone and Configuration Manager Integration topologies.</span></span></p></td>
<td align="left"><p><a href="mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md" data-raw-source="[MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)"><span data-ttu-id="9cd62-119">独立和 Configuration Manager 集成拓扑的 MBAM 2.5 服务器先决条件</span><span class="sxs-lookup"><span data-stu-id="9cd62-119">MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="9cd62-120">如果你计划使用 Configuration Manager 集成拓扑，请完成仅适用于此拓扑的其他先决条件。</span><span class="sxs-lookup"><span data-stu-id="9cd62-120">If you plan to use the Configuration Manager Integration topology, complete the additional prerequisites that apply only to this topology.</span></span></p></td>
<td align="left"><p><a href="mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md" data-raw-source="[MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology](mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md)"><span data-ttu-id="9cd62-121">仅适用于 Configuration Manager 集成拓扑的 MBAM 2.5 服务器先决条件</span><span class="sxs-lookup"><span data-stu-id="9cd62-121">MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="9cd62-122">查看并满足 MBAM 客户端的 MBAM 2.5 先决条件。</span><span class="sxs-lookup"><span data-stu-id="9cd62-122">Review and meet the MBAM 2.5 prerequisites for the MBAM Client.</span></span></p></td>
<td align="left"><p><a href="prerequisites-for-mbam-25-clients.md" data-raw-source="[Prerequisites for MBAM 2.5 Clients](prerequisites-for-mbam-25-clients.md)"><span data-ttu-id="9cd62-123">MBAM 2.5 客户端的先决条件</span><span class="sxs-lookup"><span data-stu-id="9cd62-123">Prerequisites for MBAM 2.5 Clients</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="9cd62-124">规划和配置 MBAM 组策略要求。</span><span class="sxs-lookup"><span data-stu-id="9cd62-124">Plan for and configure MBAM Group Policy requirements.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-25-group-policy-requirements.md" data-raw-source="[Planning for MBAM 2.5 Group Policy Requirements](planning-for-mbam-25-group-policy-requirements.md)"><span data-ttu-id="9cd62-125">规划 MBAM 2.5 组策略要求</span><span class="sxs-lookup"><span data-stu-id="9cd62-125">Planning for MBAM 2.5 Group Policy Requirements</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="9cd62-126">规划和创建必要的 ActiveDirectoryDomainServices 安全组。</span><span class="sxs-lookup"><span data-stu-id="9cd62-126">Plan for and create the necessary ActiveDirectoryDomainServices security groups.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-25-groups-and-accounts.md" data-raw-source="[Planning for MBAM 2.5 Groups and Accounts](planning-for-mbam-25-groups-and-accounts.md)"><span data-ttu-id="9cd62-127">规划 MBAM 2.5 组和帐户</span><span class="sxs-lookup"><span data-stu-id="9cd62-127">Planning for MBAM 2.5 Groups and Accounts</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="9cd62-128">规划如何保护 MBAM 网站的安全。</span><span class="sxs-lookup"><span data-stu-id="9cd62-128">Plan how you will secure the MBAM websites.</span></span></p></td>
<td align="left"><p><a href="planning-how-to-secure-the-mbam-websites.md" data-raw-source="[Planning How to Secure the MBAM Websites](planning-how-to-secure-the-mbam-websites.md)"><span data-ttu-id="9cd62-129">规划如何保护 MBAM 网站</span><span class="sxs-lookup"><span data-stu-id="9cd62-129">Planning How to Secure the MBAM Websites</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="9cd62-130">查看 MBAM 支持的配置，确保硬件满足安装系统要求。</span><span class="sxs-lookup"><span data-stu-id="9cd62-130">Review the MBAM Supported Configurations to ensure that your hardware meets the installation system requirements.</span></span></p></td>
<td align="left"><p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)"><span data-ttu-id="9cd62-131">MBAM 2.5 支持的配置</span><span class="sxs-lookup"><span data-stu-id="9cd62-131">MBAM 2.5 Supported Configurations</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="9cd62-132">查看部署 MBAM 服务器功能的注意事项。</span><span class="sxs-lookup"><span data-stu-id="9cd62-132">Review the considerations for deploying the MBAM Server features.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-25-server-deployment.md" data-raw-source="[Planning for MBAM 2.5 Server Deployment](planning-for-mbam-25-server-deployment.md)"><span data-ttu-id="9cd62-133">规划 MBAM 2.5 服务器部署</span><span class="sxs-lookup"><span data-stu-id="9cd62-133">Planning for MBAM 2.5 Server Deployment</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="9cd62-134">查看部署 MBAM 客户端的注意事项。</span><span class="sxs-lookup"><span data-stu-id="9cd62-134">Review the considerations for deploying the MBAM Client.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-25-client-deployment.md" data-raw-source="[Planning for MBAM 2.5 Client Deployment](planning-for-mbam-25-client-deployment.md)"><span data-ttu-id="9cd62-135">规划 MBAM 2.5 客户端部署</span><span class="sxs-lookup"><span data-stu-id="9cd62-135">Planning for MBAM 2.5 Client Deployment</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="9cd62-136">查看在高可用性配置中部署 MBAM 的要求和步骤。</span><span class="sxs-lookup"><span data-stu-id="9cd62-136">Review the requirements and steps to deploy MBAM in a highly available configuration.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-25-high-availability.md" data-raw-source="[Planning for MBAM 2.5 High Availability](planning-for-mbam-25-high-availability.md)"><span data-ttu-id="9cd62-137">规划 MBAM 2.5 高可用性</span><span class="sxs-lookup"><span data-stu-id="9cd62-137">Planning for MBAM 2.5 High Availability</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="9cd62-138">查看与受信任的平台模块、日志文件和透明数据加密相关的 MBAM 安全注意事项。</span><span class="sxs-lookup"><span data-stu-id="9cd62-138">Review the MBAM security considerations that pertain to the Trusted Platform Module, log files, and transparent data encryption.</span></span></p></td>
<td align="left"><p><a href="mbam-25-security-considerations.md" data-raw-source="[MBAM 2.5 Security Considerations](mbam-25-security-considerations.md)"><span data-ttu-id="9cd62-139">MBAM 2.5 安全注意事项</span><span class="sxs-lookup"><span data-stu-id="9cd62-139">MBAM 2.5 Security Considerations</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="9cd62-140">（可选）查看在测试环境中评估 MBAM 的步骤。</span><span class="sxs-lookup"><span data-stu-id="9cd62-140">Optionally, review the steps to evaluate MBAM in a test environment.</span></span></p></td>
<td align="left"><p><a href="evaluating-mbam-25-in-a-test-environment.md" data-raw-source="[Evaluating MBAM 2.5 in a Test Environment](evaluating-mbam-25-in-a-test-environment.md)"><span data-ttu-id="9cd62-141">在测试环境中评估 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="9cd62-141">Evaluating MBAM 2.5 in a Test Environment</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>

 


## <span data-ttu-id="9cd62-142">相关主题</span><span class="sxs-lookup"><span data-stu-id="9cd62-142">Related topics</span></span>


[<span data-ttu-id="9cd62-143">规划 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="9cd62-143">Planning for MBAM 2.5</span></span>](planning-for-mbam-25.md)

 

 
## <span data-ttu-id="9cd62-144">已获得 MBAM 的建议？</span><span class="sxs-lookup"><span data-stu-id="9cd62-144">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="9cd62-145">在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="9cd62-145">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="9cd62-146">对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="9cd62-146">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>




