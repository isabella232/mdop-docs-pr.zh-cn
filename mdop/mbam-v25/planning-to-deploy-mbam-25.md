---
title: 规划部署 MBAM 2.5
description: 规划部署 MBAM 2.5
author: dansimp
ms.assetid: 1343b80c-d87a-42e7-b912-e84ba997d7e3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2e955b426b00539aa2a4ef0b7c3a6650b05633a5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804019"
---
# <span data-ttu-id="8023a-103">规划部署 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="8023a-103">Planning to Deploy MBAM 2.5</span></span>


<span data-ttu-id="8023a-104">在创建用于 Microsoft BitLocker 管理和监视的部署计划（MBAM）之前，应考虑许多不同的部署配置和先决条件。</span><span class="sxs-lookup"><span data-stu-id="8023a-104">You should consider a number of different deployment configurations and prerequisites before you create your deployment plan for Microsoft BitLocker Administration and Monitoring (MBAM).</span></span> <span data-ttu-id="8023a-105">本部分包含的信息可帮助你收集必要的信息，以制定最符合你的业务要求的部署计划。</span><span class="sxs-lookup"><span data-stu-id="8023a-105">This section includes information that can help you gather the necessary information to formulate a deployment plan that best meets your business requirements.</span></span>

## <span data-ttu-id="8023a-106">查看 MBAM 2.5 支持的配置</span><span class="sxs-lookup"><span data-stu-id="8023a-106">Review the MBAM 2.5 supported configurations</span></span>


<span data-ttu-id="8023a-107">在为 MBAM 服务器和客户端功能部署准备了计算环境后，请确保查看支持的配置，以确认要安装的计算机 MBAM 满足最低硬件和操作系统要求。</span><span class="sxs-lookup"><span data-stu-id="8023a-107">After preparing your computing environment for the MBAM Server and Client feature deployment, make sure that you review the Supported Configurations to confirm that the computers on which you are installing MBAM meet the minimum hardware and operating system requirements.</span></span> <span data-ttu-id="8023a-108">有关 MBAM 部署先决条件的详细信息，请参阅[MBAM 2.5 部署先决条件](mbam-25-deployment-prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="8023a-108">For more information about MBAM deployment prerequisites, see [MBAM 2.5 Deployment Prerequisites](mbam-25-deployment-prerequisites.md).</span></span>

[<span data-ttu-id="8023a-109">MBAM 2.5 支持的配置</span><span class="sxs-lookup"><span data-stu-id="8023a-109">MBAM 2.5 Supported Configurations</span></span>](mbam-25-supported-configurations.md)

## <span data-ttu-id="8023a-110">规划 MBAM 2.5 服务器和客户端部署</span><span class="sxs-lookup"><span data-stu-id="8023a-110">Plan for MBAM 2.5 Server and Client deployment</span></span>


<span data-ttu-id="8023a-111">MBAM 服务器基础结构取决于可在一台或多台服务器计算机上配置的一组服务器功能，具体取决于企业的要求。</span><span class="sxs-lookup"><span data-stu-id="8023a-111">The MBAM Server infrastructure depends on a set of server features that can be configured on one or more server computers, based on the requirements of the enterprise.</span></span> <span data-ttu-id="8023a-112">可以在多台服务器上的分布式配置中配置这些功能。</span><span class="sxs-lookup"><span data-stu-id="8023a-112">These features can be configured in a distributed configuration across multiple servers.</span></span>

<span data-ttu-id="8023a-113">**注意** 对于实验室环境，建议在单个服务器上安装 MBAM。</span><span class="sxs-lookup"><span data-stu-id="8023a-113">**Note** An MBAM installation on a single server is recommended only for lab environments.</span></span>

 

<span data-ttu-id="8023a-114">MBAM 客户端使管理员能够在企业中的计算机上实施和监视 BitLocker 驱动器加密。</span><span class="sxs-lookup"><span data-stu-id="8023a-114">The MBAM Client enables administrators to enforce and monitor BitLocker drive encryption on computers in the enterprise.</span></span> <span data-ttu-id="8023a-115">通过企业软件交付系统部署客户端，或在客户端计算机上安装客户端计算机作为初始映像过程的一部分，可将 BitLocker 客户端集成到组织中。</span><span class="sxs-lookup"><span data-stu-id="8023a-115">The BitLocker client can be integrated into an organization by deploying the client through an enterprise software delivery system or by installing the Client on client computers as part of the initial imaging process.</span></span>

<span data-ttu-id="8023a-116">通过 MBAM，您可以在最终用户接收计算机之前或使用组策略之后对组织中的计算机进行加密。</span><span class="sxs-lookup"><span data-stu-id="8023a-116">With MBAM, you can encrypt a computer in your organization either before the end user receives the computer, or afterwards by using Group Policy.</span></span>

[<span data-ttu-id="8023a-117">规划 MBAM 2.5 服务器部署</span><span class="sxs-lookup"><span data-stu-id="8023a-117">Planning for MBAM 2.5 Server Deployment</span></span>](planning-for-mbam-25-server-deployment.md)

[<span data-ttu-id="8023a-118">规划 MBAM 2.5 客户端部署</span><span class="sxs-lookup"><span data-stu-id="8023a-118">Planning for MBAM 2.5 Client Deployment</span></span>](planning-for-mbam-25-client-deployment.md)

## <a href="" id="other-resources-for-mbam-planning-"></a><span data-ttu-id="8023a-119">MBAM 规划的其他资源</span><span class="sxs-lookup"><span data-stu-id="8023a-119">Other resources for MBAM planning</span></span>


[<span data-ttu-id="8023a-120">规划 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="8023a-120">Planning for MBAM 2.5</span></span>](planning-for-mbam-25.md)

## <span data-ttu-id="8023a-121">已获得 MBAM 的建议？</span><span class="sxs-lookup"><span data-stu-id="8023a-121">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="8023a-122">在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="8023a-122">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="8023a-123">对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="8023a-123">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>

 

 





