---
title: MBAM 1.0 的高级别体系结构
description: MBAM 1.0 的高级别体系结构
author: dansimp
ms.assetid: b1349196-88ed-4d6c-8a1d-998f18127b6b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: de3529fdb565859fcc212d1a9a614ac4ef4b183e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803728"
---
# <span data-ttu-id="9c0af-103">MBAM 1.0 的高级别体系结构</span><span class="sxs-lookup"><span data-stu-id="9c0af-103">High Level Architecture for MBAM 1.0</span></span>


<span data-ttu-id="9c0af-104">Microsoft BitLocker 管理和监视（MBAM）是一种客户端/服务器数据加密解决方案，可帮助你简化 BitLocker 预配和部署、改进 BitLocker 合规性和报告，并减少支持费用。</span><span class="sxs-lookup"><span data-stu-id="9c0af-104">Microsoft BitLocker Administration and Monitoring (MBAM) is a client/server data encryption solution that can help you simplify BitLocker provisioning and deployment, improve BitLocker compliance and reporting, and reduce support costs.</span></span> <span data-ttu-id="9c0af-105">MBAM 包括本主题中所述的功能。</span><span class="sxs-lookup"><span data-stu-id="9c0af-105">MBAM includes the features that are described in this topic.</span></span>

<span data-ttu-id="9c0af-106">此外，还提供了一种视频，提供 MBAM 体系结构和 MBAM 设置的概述。</span><span class="sxs-lookup"><span data-stu-id="9c0af-106">Additionally, there is a video that provides an overview of the MBAM architecture and MBAM Setup.</span></span> <span data-ttu-id="9c0af-107">有关详细信息，请参阅[MBAM 部署和体系结构概述](https://go.microsoft.com/fwlink/p/?LinkId=258392)。</span><span class="sxs-lookup"><span data-stu-id="9c0af-107">For more information, see [MBAM Deployment and Architecture Overview](https://go.microsoft.com/fwlink/p/?LinkId=258392).</span></span>

## <span data-ttu-id="9c0af-108">体系结构概述</span><span class="sxs-lookup"><span data-stu-id="9c0af-108">Architecture Overview</span></span>


<span data-ttu-id="9c0af-109">下图显示了 MBAM 体系结构。</span><span class="sxs-lookup"><span data-stu-id="9c0af-109">The following diagram displays the MBAM architecture.</span></span> <span data-ttu-id="9c0af-110">将显示单服务器 MBAM 部署拓扑，介绍 MBAM 功能。</span><span class="sxs-lookup"><span data-stu-id="9c0af-110">The single-server MBAM deployment topology is shown to introduce the MBAM features.</span></span> <span data-ttu-id="9c0af-111">但是，建议仅针对实验室环境使用此 MBAM 部署拓扑。</span><span class="sxs-lookup"><span data-stu-id="9c0af-111">However, this MBAM deployment topology is recommended only for lab environments.</span></span>

<span data-ttu-id="9c0af-112">**注意** 对于生产部署，建议至少使用三台计算机 MBAM 部署拓扑。</span><span class="sxs-lookup"><span data-stu-id="9c0af-112">**Note** At least a three-computer MBAM deployment topology is recommended for a production deployment.</span></span> <span data-ttu-id="9c0af-113">有关 MBAM 部署拓扑的详细信息，请参阅[部署 MBAM 1.0 服务器基础结构](deploying-the-mbam-10-server-infrastructure.md)。</span><span class="sxs-lookup"><span data-stu-id="9c0af-113">For more information about MBAM deployment topologies, see [Deploying the MBAM 1.0 Server Infrastructure](deploying-the-mbam-10-server-infrastructure.md).</span></span>

 

![mbam 单服务器部署拓扑](images/mbam-1-server.jpg)

1.  <span data-ttu-id="9c0af-115">**管理和监视服务器**。</span><span class="sxs-lookup"><span data-stu-id="9c0af-115">**Administration and Monitoring Server**.</span></span> <span data-ttu-id="9c0af-116">MBAM 管理和监视服务器安装在 Windows 服务器上，并托管 MBAM 管理和管理网站以及监视 web 服务。</span><span class="sxs-lookup"><span data-stu-id="9c0af-116">The MBAM Administration and Monitoring Server is installed on a Windows server and hosts the MBAM Administration and Management website and the monitoring web services.</span></span> <span data-ttu-id="9c0af-117">MBAM 管理和管理网站用于确定企业合规性状态、审核活动、管理硬件功能和访问恢复数据，如 BitLocker 恢复密钥。</span><span class="sxs-lookup"><span data-stu-id="9c0af-117">The MBAM Administration and Management website is used to determine enterprise compliance status, to audit activity, to manage hardware capability, and to access recovery data, such as the BitLocker recovery keys.</span></span> <span data-ttu-id="9c0af-118">管理和监视服务器连接到以下数据库和服务：</span><span class="sxs-lookup"><span data-stu-id="9c0af-118">The Administration and Monitoring Server connects to the following databases and services:</span></span>

    -   <span data-ttu-id="9c0af-119">恢复和硬件数据库。</span><span class="sxs-lookup"><span data-stu-id="9c0af-119">Recovery and Hardware Database.</span></span> <span data-ttu-id="9c0af-120">恢复和硬件数据库安装在基于 Windows 的服务器上，并且支持 SQLServer 实例。</span><span class="sxs-lookup"><span data-stu-id="9c0af-120">The Recovery and Hardware database is installed on a Windows-based server and supported SQLServer instance.</span></span> <span data-ttu-id="9c0af-121">此数据库存储从 MBAM 客户端计算机收集的恢复数据和硬件信息。</span><span class="sxs-lookup"><span data-stu-id="9c0af-121">This database stores recovery data and hardware information that is collected from MBAM client computers.</span></span>

    -   <span data-ttu-id="9c0af-122">合规性和审核数据库。</span><span class="sxs-lookup"><span data-stu-id="9c0af-122">Compliance and Audit Database.</span></span> <span data-ttu-id="9c0af-123">合规性和审核数据库安装在 Windows server 上并支持 SQLServer 实例。</span><span class="sxs-lookup"><span data-stu-id="9c0af-123">The Compliance and Audit Database is installed on a Windows server and supported SQLServer instance.</span></span> <span data-ttu-id="9c0af-124">此数据库存储 MBAM 客户端计算机的合规性数据。</span><span class="sxs-lookup"><span data-stu-id="9c0af-124">This database stores compliance data for MBAM client computers.</span></span> <span data-ttu-id="9c0af-125">此数据主要用于由 SQL Server Reporting Services （SSRS）托管的报表。</span><span class="sxs-lookup"><span data-stu-id="9c0af-125">This data is used primarily for reports that are hosted by SQL Server Reporting Services (SSRS).</span></span>

    -   <span data-ttu-id="9c0af-126">合规性和审核报告。</span><span class="sxs-lookup"><span data-stu-id="9c0af-126">Compliance and Audit Reports.</span></span> <span data-ttu-id="9c0af-127">合规性和审核报告安装在基于 Windows 的服务器上，并且支持安装了 SSRS 功能的 SQLServer 实例。</span><span class="sxs-lookup"><span data-stu-id="9c0af-127">The Compliance and Audit Reports are installed on a Windows-based server and supported SQLServer instance that has the SSRS feature installed.</span></span> <span data-ttu-id="9c0af-128">这些报表提供 Microsoft BitLocker 管理和监视报告。</span><span class="sxs-lookup"><span data-stu-id="9c0af-128">These reports provide Microsoft BitLocker Administration and Monitoring reports.</span></span> <span data-ttu-id="9c0af-129">可以从 MBAM 管理和管理网站或直接从 SSRS 服务器访问这些报告。</span><span class="sxs-lookup"><span data-stu-id="9c0af-129">These reports can be accessed from the MBAM Administration and Management website or directly from the SSRS Server.</span></span>

2.  <span data-ttu-id="9c0af-130">**MBAM 客户端**。</span><span class="sxs-lookup"><span data-stu-id="9c0af-130">**MBAM Client**.</span></span> <span data-ttu-id="9c0af-131">Microsoft BitLocker 管理和监视客户端执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="9c0af-131">The Microsoft BitLocker Administration and Monitoring Client performs the following tasks:</span></span>

    -   <span data-ttu-id="9c0af-132">使用组策略强制对企业中的客户端计算机进行 BitLocker 加密。</span><span class="sxs-lookup"><span data-stu-id="9c0af-132">Uses Group Policy to enforce the BitLocker encryption of client computers in the enterprise.</span></span>

    -   <span data-ttu-id="9c0af-133">收集三个 BitLocker 数据驱动器类型的恢复密钥：操作系统驱动器、固定数据驱动器和可移动数据（USB）驱动器。</span><span class="sxs-lookup"><span data-stu-id="9c0af-133">Collects the recovery key for the three BitLocker data drive types: operating system drives, fixed data drives, and removable data (USB) drives.</span></span>

    -   <span data-ttu-id="9c0af-134">收集有关客户端计算机的恢复信息和硬件信息。</span><span class="sxs-lookup"><span data-stu-id="9c0af-134">Collects recovery information and hardware information about the client computers.</span></span>

    -   <span data-ttu-id="9c0af-135">收集计算机的合规性数据并将数据传递到报告系统。</span><span class="sxs-lookup"><span data-stu-id="9c0af-135">Collects compliance data for the computer and passes the data to the reporting system.</span></span>

3.  <span data-ttu-id="9c0af-136">**策略模板**。</span><span class="sxs-lookup"><span data-stu-id="9c0af-136">**Policy Template**.</span></span> <span data-ttu-id="9c0af-137">MBAM 组策略模板安装在受支持的基于 Windows 的服务器或客户端计算机上。</span><span class="sxs-lookup"><span data-stu-id="9c0af-137">The MBAM Group Policy template is installed on a supported Windows-based server or client computer.</span></span> <span data-ttu-id="9c0af-138">此模板用于指定用于 BitLocker 驱动器加密的 MBAM 实现设置。</span><span class="sxs-lookup"><span data-stu-id="9c0af-138">This template is used to specify the MBAM implementation settings for BitLocker drive encryption.</span></span>

## <span data-ttu-id="9c0af-139">相关主题</span><span class="sxs-lookup"><span data-stu-id="9c0af-139">Related topics</span></span>


[<span data-ttu-id="9c0af-140">MBAM 1.0 入门</span><span class="sxs-lookup"><span data-stu-id="9c0af-140">Getting Started with MBAM 1.0</span></span>](getting-started-with-mbam-10.md)

 

 





