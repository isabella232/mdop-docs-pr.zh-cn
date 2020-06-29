---
title: 部署 MBAM 1.0 服务器基础结构
description: 部署 MBAM 1.0 服务器基础结构
author: dansimp
ms.assetid: 90529379-b70e-4c92-b188-3d7aaf1844af
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: de136db557233a097d95f47ef0a1bba5996798c5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803716"
---
# <span data-ttu-id="9e286-103">部署 MBAM 1.0 服务器基础结构</span><span class="sxs-lookup"><span data-stu-id="9e286-103">Deploying the MBAM 1.0 Server Infrastructure</span></span>


<span data-ttu-id="9e286-104">通过使用一到五台服务器，你可以在不同配置中安装 Microsoft BitLocker 管理和监视（MBAM）服务器功能。</span><span class="sxs-lookup"><span data-stu-id="9e286-104">You can install Microsoft BitLocker Administration and Monitoring (MBAM) Server features in different configurations by using one to five servers.</span></span> <span data-ttu-id="9e286-105">通常，你应该为生产环境使用三到五台服务器的配置，具体取决于你的可伸缩性需求。</span><span class="sxs-lookup"><span data-stu-id="9e286-105">Generally, you should use a configuration of three to five servers for production environments, depending on your scalability needs.</span></span> <span data-ttu-id="9e286-106">有关 MBAM 和推荐部署拓扑的性能可伸缩性的详细信息，请参阅[MBAM 可伸缩性和高可用性指南白皮书](https://go.microsoft.com/fwlink/p/?LinkId=258314)。</span><span class="sxs-lookup"><span data-stu-id="9e286-106">For more information about performance scalability of MBAM and recommended deployment topologies, see the [MBAM Scalability and High-Availability Guide White Paper](https://go.microsoft.com/fwlink/p/?LinkId=258314).</span></span>

## <span data-ttu-id="9e286-107">在单个服务器上部署所有 MBAM 1。0</span><span class="sxs-lookup"><span data-stu-id="9e286-107">Deploy all MBAM 1.0 on a single server</span></span>


<span data-ttu-id="9e286-108">在此配置中，所有 MBAM 功能都安装在一台服务器上。</span><span class="sxs-lookup"><span data-stu-id="9e286-108">In this configuration, all MBAM features are installed on a single server.</span></span> <span data-ttu-id="9e286-109">MBAM server 基础结构的此部署拓扑将最多支持 21000 MBAM 客户端计算机。</span><span class="sxs-lookup"><span data-stu-id="9e286-109">This deployment topology for MBAM server infrastructure will support up to 21,000 MBAM client computers.</span></span>

<span data-ttu-id="9e286-110">**重要提示** 此配置受支持，但我们建议仅用于测试。</span><span class="sxs-lookup"><span data-stu-id="9e286-110">**Important** This configuration is supported, but we recommend it for testing only.</span></span>

 

<span data-ttu-id="9e286-111">本节中的过程介绍了单个服务器上的 MBAM 功能的完整安装。</span><span class="sxs-lookup"><span data-stu-id="9e286-111">The procedures in this section describe the full installation of the MBAM features on a single server.</span></span>

[<span data-ttu-id="9e286-112">如何在单个服务器上安装和配置 MBAM</span><span class="sxs-lookup"><span data-stu-id="9e286-112">How to Install and Configure MBAM on a Single Server</span></span>](how-to-install-and-configure-mbam-on-a-single-server-mbam-1.md)

## <span data-ttu-id="9e286-113">在分布式服务器上部署 MBAM 1。0</span><span class="sxs-lookup"><span data-stu-id="9e286-113">Deploy MBAM 1.0 on distributed servers</span></span>


<span data-ttu-id="9e286-114">MBAM 功能可以采用不同的配置进行安装，具体取决于您的可伸缩性需求。</span><span class="sxs-lookup"><span data-stu-id="9e286-114">MBAM features can be installed in different configurations, depending on your scalability needs.</span></span> <span data-ttu-id="9e286-115">有关如何规划 MBAM server 功能部署的详细信息，请参阅[规划1.0 服务器部署](planning-for-mbam-10-server-deployment.md)。</span><span class="sxs-lookup"><span data-stu-id="9e286-115">For more information about how to plan for MBAM server feature deployment, see [Planning for MBAM 1.0 Server Deployment](planning-for-mbam-10-server-deployment.md).</span></span>

<span data-ttu-id="9e286-116">本节中的过程介绍了分布式服务器上的 MBAM 功能的完整安装。</span><span class="sxs-lookup"><span data-stu-id="9e286-116">The procedures in this section describe the full installation of the MBAM features on distributed servers.</span></span>

### <span data-ttu-id="9e286-117">三台计算机配置</span><span class="sxs-lookup"><span data-stu-id="9e286-117">Three-computer configuration</span></span>

<span data-ttu-id="9e286-118">下图显示了 MBAM 的三计算机部署拓扑。</span><span class="sxs-lookup"><span data-stu-id="9e286-118">The following diagram displays the three-computer deployment topology for MBAM.</span></span> <span data-ttu-id="9e286-119">对于支持最多 55000 MBAM 客户端的生产环境，我们建议采用此拓扑。</span><span class="sxs-lookup"><span data-stu-id="9e286-119">We recommend this topology for production environments that support up to 55,000 MBAM Clients.</span></span>

![mbam 三台计算机部署拓扑](images/mbam-3-server.jpg)

<span data-ttu-id="9e286-121">在此配置中，MBAM 功能安装在以下配置中：</span><span class="sxs-lookup"><span data-stu-id="9e286-121">In this configuration, MBAM features are installed in the following configuration:</span></span>

1.  <span data-ttu-id="9e286-122">在服务器上安装恢复和硬件数据库、合规性和审核数据库以及合规性和审核报告。</span><span class="sxs-lookup"><span data-stu-id="9e286-122">Recovery and Hardware Database, Compliance and Audit Database, and Compliance and Audit Reports are installed on a server.</span></span>

2.  <span data-ttu-id="9e286-123">"管理和监视服务器" 功能安装在服务器上。</span><span class="sxs-lookup"><span data-stu-id="9e286-123">Administration and Monitoring Server feature is installed on a server.</span></span>

3.  <span data-ttu-id="9e286-124">MBAM 组策略模板安装在能够修改组策略对象（GPO）的计算机上。</span><span class="sxs-lookup"><span data-stu-id="9e286-124">MBAM Group Policy template is installed on a computer that is capable of modifying Group Policy Objects (GPO).</span></span>

### <span data-ttu-id="9e286-125">四计算机配置</span><span class="sxs-lookup"><span data-stu-id="9e286-125">Four-computer configuration</span></span>

<span data-ttu-id="9e286-126">下图显示了用于 MBAM 的四计算机部署拓扑。</span><span class="sxs-lookup"><span data-stu-id="9e286-126">The following diagram displays the four-computer deployment topology for MBAM.</span></span> <span data-ttu-id="9e286-127">对于支持最多 110000 MBAM 客户端的生产环境，建议使用此拓扑。</span><span class="sxs-lookup"><span data-stu-id="9e286-127">We recommended this topology for production environments that support up to 110,000 MBAM Clients.</span></span>

![mbam 4 计算机部署拓扑。](images/mbam-4-computer.jpg)

<span data-ttu-id="9e286-129">在此配置中，MBAM 功能安装在以下配置中：</span><span class="sxs-lookup"><span data-stu-id="9e286-129">In this configuration, MBAM features are installed in the following configuration:</span></span>

1.  <span data-ttu-id="9e286-130">在服务器上安装恢复和硬件数据库、合规性和审核数据库以及合规性和审核报告。</span><span class="sxs-lookup"><span data-stu-id="9e286-130">Recovery and Hardware Database, Compliance and Audit Database, and Compliance and Audit Reports are installed on a server.</span></span>

2.  <span data-ttu-id="9e286-131">"管理和监视服务器" 功能安装在网络负载平衡（NLB）服务器群集中配置的服务器上。</span><span class="sxs-lookup"><span data-stu-id="9e286-131">Administration and Monitoring Server feature is installed on a server that is configured in a Network Load Balancing (NLB) Server Cluster.</span></span>

3.  <span data-ttu-id="9e286-132">MBAM 组策略模板安装在能够修改组策略对象的计算机上。</span><span class="sxs-lookup"><span data-stu-id="9e286-132">MBAM Group Policy template is installed on a computer that is capable of modifying the Group Policy Objects.</span></span>

### <span data-ttu-id="9e286-133">五台计算机配置</span><span class="sxs-lookup"><span data-stu-id="9e286-133">Five-computer configuration</span></span>

<span data-ttu-id="9e286-134">下图显示了用于 MBAM 的五台计算机部署拓扑。</span><span class="sxs-lookup"><span data-stu-id="9e286-134">The following diagram displays the five-computer deployment topology for MBAM.</span></span> <span data-ttu-id="9e286-135">对于支持最多 135000 MBAM 客户端的生产环境，我们建议采用此拓扑。</span><span class="sxs-lookup"><span data-stu-id="9e286-135">We recommend this topology for production environments that support up to 135,000 MBAM Clients.</span></span>

![mbam 五台计算机部署拓扑。](images/mbam-5-computer.jpg)

<span data-ttu-id="9e286-137">在此配置中，MBAM 功能安装在以下配置中：</span><span class="sxs-lookup"><span data-stu-id="9e286-137">In this configuration, MBAM features are installed in the following configuration:</span></span>

1.  <span data-ttu-id="9e286-138">恢复和硬件数据库安装在服务器上。</span><span class="sxs-lookup"><span data-stu-id="9e286-138">Recovery and Hardware Database is installed on a server.</span></span>

2.  <span data-ttu-id="9e286-139">在服务器上安装合规性和审核数据库以及合规性和审核报告。</span><span class="sxs-lookup"><span data-stu-id="9e286-139">The Compliance and Audit Database and Compliance and Audit Reports are installed on a server.</span></span>

3.  <span data-ttu-id="9e286-140">"管理和监视服务器" 功能安装在网络负载平衡（NLB）服务器群集中配置的服务器上。</span><span class="sxs-lookup"><span data-stu-id="9e286-140">Administration and Monitoring Server feature is installed on a server that is configured in a Network Load Balancing (NLB) Server Cluster.</span></span>

4.  <span data-ttu-id="9e286-141">MBAM 组策略模板安装在能够修改组策略对象的计算机上。</span><span class="sxs-lookup"><span data-stu-id="9e286-141">MBAM Group Policy template is installed on a computer that is capable of modifying Group Policy Objects.</span></span>

[<span data-ttu-id="9e286-142">如何在分布式服务器上安装和配置 MBAM</span><span class="sxs-lookup"><span data-stu-id="9e286-142">How to Install and Configure MBAM on Distributed Servers</span></span>](how-to-install-and-configure-mbam-on-distributed-servers-mbam-1.md)

[<span data-ttu-id="9e286-143">如何针对 MBAM 配置网络负载均衡</span><span class="sxs-lookup"><span data-stu-id="9e286-143">How to Configure Network Load Balancing for MBAM</span></span>](how-to-configure-network-load-balancing-for-mbam.md)

## <span data-ttu-id="9e286-144">适用于 MBAM 1.0 服务器功能部署的其他资源</span><span class="sxs-lookup"><span data-stu-id="9e286-144">Other resources for MBAM 1.0 Server features deployment</span></span>


[<span data-ttu-id="9e286-145">部署 MBAM 1.0</span><span class="sxs-lookup"><span data-stu-id="9e286-145">Deploying MBAM 1.0</span></span>](deploying-mbam-10.md)

 

 





