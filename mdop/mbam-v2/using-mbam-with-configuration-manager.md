---
title: 结合使用 MBAM 和 Configuration Manager
description: 结合使用 MBAM 和 Configuration Manager
author: dansimp
ms.assetid: 03868717-4aa7-4897-8166-9a3df5e9519e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9e3c5dd199010ac758ab701b0753d913ea323efd
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803438"
---
# <span data-ttu-id="ab0fe-103">结合使用 MBAM 和 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="ab0fe-103">Using MBAM with Configuration Manager</span></span>


<span data-ttu-id="ab0fe-104">安装 Microsoft BitLocker 管理和监视（MBAM）时，你可以选择通过 System Center Configuration Manager 集成 Microsoft BitLocker 管理和监视的安装。</span><span class="sxs-lookup"><span data-stu-id="ab0fe-104">When you install Microsoft BitLocker Administration and Monitoring (MBAM), you can choose an installation that integrates Microsoft BitLocker Administration and Monitoring with System Center Configuration Manager.</span></span> <span data-ttu-id="ab0fe-105">有关支持的 Configuration Manager 版本的列表，请参阅[计划使用 Configuration Manager 部署 MBAM](planning-to-deploy-mbam-with-configuration-manager-2.md)。</span><span class="sxs-lookup"><span data-stu-id="ab0fe-105">For a list of the supported versions of Configuration Manager, see [Planning to Deploy MBAM with Configuration Manager](planning-to-deploy-mbam-with-configuration-manager-2.md).</span></span>

<span data-ttu-id="ab0fe-106">此集成将 Microsoft BitLocker 管理和监视合规性和报告基础结构移动到 Microsoft System Center Configuration Manager 的本机环境中。</span><span class="sxs-lookup"><span data-stu-id="ab0fe-106">This integration moves the Microsoft BitLocker Administration and Monitoring compliance and reporting infrastructure into the native environment of Microsoft System Center Configuration Manager.</span></span> <span data-ttu-id="ab0fe-107">通过 Configuration Manager 拓扑，IT 管理员可以从 Configuration Manager 管理控制台查看其企业的报告和合规性状态。</span><span class="sxs-lookup"><span data-stu-id="ab0fe-107">With the Configuration Manager topology, IT administrators can view reports and the compliance status of their enterprise from the Configuration Manager Management Console.</span></span>

<span data-ttu-id="ab0fe-108">**重要提示** 将 MBAM 的集成拓扑安装到 Configuration Manager 2007 时，不支持 Windows To Go。</span><span class="sxs-lookup"><span data-stu-id="ab0fe-108">**Important** Windows To Go is not supported when you install the integrated topology of MBAM with Configuration Manager 2007.</span></span>

 

## <a href="" id="getting-started---using-mbam-with-configuration-manager"></a><span data-ttu-id="ab0fe-109">入门–将 MBAM 与 Configuration Manager 配合使用</span><span class="sxs-lookup"><span data-stu-id="ab0fe-109">Getting Started – Using MBAM with Configuration Manager</span></span>


<span data-ttu-id="ab0fe-110">本部分介绍了 MBAM 如何与 Configuration Manager 配合使用，并介绍了使用 Configuration Manager 集成拓扑部署 MBAM 的推荐体系结构。</span><span class="sxs-lookup"><span data-stu-id="ab0fe-110">This section describes how MBAM works with Configuration Manager and explains the recommended architecture for deploying MBAM with the Configuration Manager Integration topology.</span></span>

[<span data-ttu-id="ab0fe-111">入门 - 结合使用 MBAM 和 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="ab0fe-111">Getting Started - Using MBAM with Configuration Manager</span></span>](getting-started---using-mbam-with-configuration-manager.md)

## <span data-ttu-id="ab0fe-112">计划使用 Configuration Manager 部署 MBAM</span><span class="sxs-lookup"><span data-stu-id="ab0fe-112">Planning to Deploy MBAM with Configuration Manager</span></span>


<span data-ttu-id="ab0fe-113">本部分介绍在通过 Configuration Manager 拓扑安装 MBAM 之前需要考虑的安装先决条件、受支持的配置和硬件和软件要求。</span><span class="sxs-lookup"><span data-stu-id="ab0fe-113">This section describes the installation prerequisites, supported configurations, and hardware and software requirements that you need to consider before you install MBAM with the Configuration Manager topology.</span></span>

[<span data-ttu-id="ab0fe-114">计划使用 Configuration Manager 部署 MBAM</span><span class="sxs-lookup"><span data-stu-id="ab0fe-114">Planning to Deploy MBAM with Configuration Manager</span></span>](planning-to-deploy-mbam-with-configuration-manager-2.md)

## <span data-ttu-id="ab0fe-115">使用 Configuration Manager 部署 MBAM</span><span class="sxs-lookup"><span data-stu-id="ab0fe-115">Deploying MBAM with Configuration Manager</span></span>


<span data-ttu-id="ab0fe-116">本部分介绍了如何通过 Configuration Manager 部署 MBAM，以及如何在 "管理和监视服务器" 和 "配置管理器" 服务器上安装和配置 MBAM 的说明。</span><span class="sxs-lookup"><span data-stu-id="ab0fe-116">This section describes how to deploy MBAM with Configuration Manager, and includes instructions for installing and configuring the MBAM on the Administration and Monitoring Server and Configuration Manager Server.</span></span>

[<span data-ttu-id="ab0fe-117">使用 Configuration Manager 部署 MBAM</span><span class="sxs-lookup"><span data-stu-id="ab0fe-117">Deploying MBAM with Configuration Manager</span></span>](deploying-mbam-with-configuration-manager-mbam2.md)

## <span data-ttu-id="ab0fe-118">了解 Configuration Manager 中的 MBAM 报告</span><span class="sxs-lookup"><span data-stu-id="ab0fe-118">Understanding MBAM Reports in Configuration Manager</span></span>


<span data-ttu-id="ab0fe-119">本节介绍你可以从 Configuration Manager 运行的 MBAM 报表，以展示企业中的单个计算机的企业合规性和合规性。</span><span class="sxs-lookup"><span data-stu-id="ab0fe-119">This section describes the MBAM reports that you can run from Configuration Manager to show the compliance of your enterprise and compliance of individual computers in your enterprise.</span></span>

[<span data-ttu-id="ab0fe-120">了解 Configuration Manager 中的 MBAM 报告</span><span class="sxs-lookup"><span data-stu-id="ab0fe-120">Understanding MBAM Reports in Configuration Manager</span></span>](understanding-mbam-reports-in-configuration-manager.md)

## <span data-ttu-id="ab0fe-121">相关主题</span><span class="sxs-lookup"><span data-stu-id="ab0fe-121">Related topics</span></span>


[<span data-ttu-id="ab0fe-122">MBAM 2.0 的操作</span><span class="sxs-lookup"><span data-stu-id="ab0fe-122">Operations for MBAM 2.0</span></span>](operations-for-mbam-20-mbam-2.md)

 

 





