---
title: 计划部署 MBAM 2.0
description: 计划部署 MBAM 2.0
author: dansimp
ms.assetid: 2dc05fcd-aed9-4315-aeaf-92aaa9e0e955
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c7f065e52655212261dfe8b6b3f081f697142473
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803807"
---
# <span data-ttu-id="0efbe-103">计划部署 MBAM 2.0</span><span class="sxs-lookup"><span data-stu-id="0efbe-103">Planning to Deploy MBAM 2.0</span></span>


<span data-ttu-id="0efbe-104">在创建用于 Microsoft BitLocker 管理和监视的部署计划（MBAM）之前，应考虑许多不同的部署配置和先决条件。</span><span class="sxs-lookup"><span data-stu-id="0efbe-104">You should consider a number of different deployment configurations and prerequisites before you create your deployment plan for Microsoft BitLocker Administration and Monitoring (MBAM).</span></span> <span data-ttu-id="0efbe-105">本部分包含的信息可帮助你收集必要的信息，以制定最符合你的业务要求的部署计划。</span><span class="sxs-lookup"><span data-stu-id="0efbe-105">This section includes information that can help you gather the necessary information to formulate a deployment plan that best meets your business requirements.</span></span> <span data-ttu-id="0efbe-106">如果你正在通过 Configuration Manager 拓扑安装 MBAM，请参阅[计划通过 Configuration Manager 部署 MBAM](planning-to-deploy-mbam-with-configuration-manager-2.md)以获取其他计划信息。</span><span class="sxs-lookup"><span data-stu-id="0efbe-106">If you are installing MBAM with the Configuration Manager topology, see [Planning to Deploy MBAM with Configuration Manager](planning-to-deploy-mbam-with-configuration-manager-2.md) for additional planning information.</span></span>

## <span data-ttu-id="0efbe-107">查看 MBAM 2.0 支持的配置</span><span class="sxs-lookup"><span data-stu-id="0efbe-107">Review the MBAM 2.0 Supported Configurations</span></span>


<span data-ttu-id="0efbe-108">在为 MBAM 服务器和客户端功能安装准备了计算环境后，请确保查看支持的配置，以确认要安装的计算机 MBAM 满足最低硬件和操作系统要求。</span><span class="sxs-lookup"><span data-stu-id="0efbe-108">After preparing your computing environment for the MBAM Server and Client feature installation, make sure that you review the Supported Configurations to confirm that the computers on which you are installing MBAM meet the minimum hardware and operating system requirements.</span></span> <span data-ttu-id="0efbe-109">有关 MBAM 部署先决条件的详细信息，请参阅[MBAM 2.0 部署先决条件](mbam-20-deployment-prerequisites-mbam-2.md)。</span><span class="sxs-lookup"><span data-stu-id="0efbe-109">For more information about MBAM deployment prerequisites, see [MBAM 2.0 Deployment Prerequisites](mbam-20-deployment-prerequisites-mbam-2.md).</span></span>

[<span data-ttu-id="0efbe-110">MBAM 2.0 支持的配置</span><span class="sxs-lookup"><span data-stu-id="0efbe-110">MBAM 2.0 Supported Configurations</span></span>](mbam-20-supported-configurations-mbam-2.md)

## <span data-ttu-id="0efbe-111">规划 MBAM 2.0 服务器和客户端部署</span><span class="sxs-lookup"><span data-stu-id="0efbe-111">Plan for MBAM 2.0 Server and Client Deployment</span></span>


<span data-ttu-id="0efbe-112">MBAM 服务器基础结构依赖于一组可在一台或多台服务器计算机上安装的服务器功能，具体取决于企业的要求。</span><span class="sxs-lookup"><span data-stu-id="0efbe-112">The MBAM Server infrastructure depends on a set of server features that can be installed on one or more server computers, based on the requirements of the enterprise.</span></span> <span data-ttu-id="0efbe-113">这些功能可通过多台服务器的分布式配置进行安装。</span><span class="sxs-lookup"><span data-stu-id="0efbe-113">These features can be installed in a distributed configuration across multiple servers.</span></span>

<span data-ttu-id="0efbe-114">**注意** 对于实验室环境，建议在单个服务器上安装 MBAM。</span><span class="sxs-lookup"><span data-stu-id="0efbe-114">**Note** An MBAM installation on a single server is recommended only for lab environments.</span></span>

 

<span data-ttu-id="0efbe-115">MBAM 客户端使管理员能够在企业中的计算机上实施和监视 BitLocker 驱动器加密。</span><span class="sxs-lookup"><span data-stu-id="0efbe-115">The MBAM Client enables administrators to enforce and monitor BitLocker drive encryption on computers in the enterprise.</span></span> <span data-ttu-id="0efbe-116">通过企业软件交付系统部署客户端，或者在客户端计算机上安装客户端代理作为初始映像过程的一部分，可将 BitLocker 客户端集成到组织中。</span><span class="sxs-lookup"><span data-stu-id="0efbe-116">The BitLocker client can be integrated into an organization by deploying the client through an enterprise software delivery system or by installing the client agent on client computers as part of the initial imaging process.</span></span>

<span data-ttu-id="0efbe-117">通过 MBAM，您可以在最终用户接收计算机之前或使用组策略之后对组织中的计算机进行加密。</span><span class="sxs-lookup"><span data-stu-id="0efbe-117">With MBAM, you can encrypt a computer in your organization either before the end user receives the computer, or afterwards by using Group Policy.</span></span>

[<span data-ttu-id="0efbe-118">计划 MBAM 2.0 服务器部署</span><span class="sxs-lookup"><span data-stu-id="0efbe-118">Planning for MBAM 2.0 Server Deployment</span></span>](planning-for-mbam-20-server-deployment-mbam-2.md)

[<span data-ttu-id="0efbe-119">计划 MBAM 2.0 客户端部署</span><span class="sxs-lookup"><span data-stu-id="0efbe-119">Planning for MBAM 2.0 Client Deployment</span></span>](planning-for-mbam-20-client-deployment-mbam-2.md)

## <a href="" id="other-resources-for-mbam-planning-"></a><span data-ttu-id="0efbe-120">MBAM 规划的其他资源</span><span class="sxs-lookup"><span data-stu-id="0efbe-120">Other Resources for MBAM Planning</span></span>


[<span data-ttu-id="0efbe-121">计划 MBAM 2.0</span><span class="sxs-lookup"><span data-stu-id="0efbe-121">Planning for MBAM 2.0</span></span>](planning-for-mbam-20-mbam-2.md)

 

 





