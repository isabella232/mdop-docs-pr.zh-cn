---
title: 部署 MBAM 2.0
description: 部署 MBAM 2.0
author: dansimp
ms.assetid: 4b0eaf10-81b4-427e-9d43-eb833de935a3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ba4423de5306e1ca204ef3b9fd31424bb8f2630f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803375"
---
# <span data-ttu-id="87e72-103">部署 MBAM 2.0</span><span class="sxs-lookup"><span data-stu-id="87e72-103">Deploying MBAM 2.0</span></span>


<span data-ttu-id="87e72-104">Microsoft BitLocker 管理和监视（MBAM）支持多种不同的部署配置。</span><span class="sxs-lookup"><span data-stu-id="87e72-104">Microsoft BitLocker Administration and Monitoring (MBAM) supports a number of different deployment configurations.</span></span> <span data-ttu-id="87e72-105">本部分包含有关如何部署 MBAM 和分步过程的信息，这些信息可帮助你成功执行必须在部署的不同阶段完成的任务。</span><span class="sxs-lookup"><span data-stu-id="87e72-105">This section includes information that you should consider about the deployment of MBAM and step-by-step procedures to help you successfully perform the tasks that you must complete at different stages of your deployment.</span></span>

<span data-ttu-id="87e72-106">你可以在独立拓扑中部署 MBAM，也可以使用与 Microsoft System Center Configuration Manager 2007 或 MicrosoftSystemCenter2012 ConfigurationManager 集成 MBAM 的拓扑。</span><span class="sxs-lookup"><span data-stu-id="87e72-106">You can deploy MBAM either in a Stand-alone topology, or with a topology that integrates MBAM with Microsoft System Center Configuration Manager 2007 or MicrosoftSystemCenter2012 ConfigurationManager.</span></span> <span data-ttu-id="87e72-107">有关使用 Configuration Manager 集成拓扑安装 MBAM 的信息，请参阅将[MBAM 与 Configuration manager 结合使用](using-mbam-with-configuration-manager.md)。</span><span class="sxs-lookup"><span data-stu-id="87e72-107">For information about installing MBAM with the Configuration Manager integrated topology, see [Using MBAM with Configuration Manager](using-mbam-with-configuration-manager.md).</span></span>

## <span data-ttu-id="87e72-108">部署信息</span><span class="sxs-lookup"><span data-stu-id="87e72-108">Deployment Information</span></span>


-   [<span data-ttu-id="87e72-109">部署 MBAM 2.0 服务器基础结构</span><span class="sxs-lookup"><span data-stu-id="87e72-109">Deploying the MBAM 2.0 Server Infrastructure</span></span>](deploying-the-mbam-20-server-infrastructure-mbam-2.md)

    <span data-ttu-id="87e72-110">本节介绍不同的 MBAM 部署拓扑选项以及如何使用 MBAM 设置部署 MBAM 服务器功能。</span><span class="sxs-lookup"><span data-stu-id="87e72-110">This section describes the different MBAM deployment topology options and how to use MBAM Setup to deploy MBAM Server features.</span></span>

-   [<span data-ttu-id="87e72-111">部署 MBAM 2.0 组策略对象</span><span class="sxs-lookup"><span data-stu-id="87e72-111">Deploying MBAM 2.0 Group Policy Objects</span></span>](deploying-mbam-20-group-policy-objects-mbam-2.md)

    <span data-ttu-id="87e72-112">本部分介绍如何创建和部署在整个企业中管理 MBAM 客户端和 BitLocker 加密策略所需的 MBAM 组策略对象。</span><span class="sxs-lookup"><span data-stu-id="87e72-112">This section describes how to create and deploy MBAM Group Policy Objects that are required for managing MBAM Clients and BitLocker encryption policies throughout the enterprise.</span></span>

-   [<span data-ttu-id="87e72-113">部署 MBAM 2.0 客户端</span><span class="sxs-lookup"><span data-stu-id="87e72-113">Deploying the MBAM 2.0 Client</span></span>](deploying-the-mbam-20-client-mbam-2.md)

    <span data-ttu-id="87e72-114">本部分介绍如何使用 MBAM 客户端安装程序文件来部署 MBAM 客户端软件。</span><span class="sxs-lookup"><span data-stu-id="87e72-114">This section describes how to use the MBAM Client Installer files to deploy the MBAM Client software.</span></span>

-   [<span data-ttu-id="87e72-115">MBAM 2.0 部署清单</span><span class="sxs-lookup"><span data-stu-id="87e72-115">MBAM 2.0 Deployment Checklist</span></span>](mbam-20-deployment-checklist-mbam-2.md)

    <span data-ttu-id="87e72-116">本部分提供了可用于协助 MBAM Server 功能和 MBAM 客户端部署的部署清单。</span><span class="sxs-lookup"><span data-stu-id="87e72-116">This section provides a deployment checklist that can be used to assist in MBAM Server feature and MBAM Client deployment.</span></span>

-   [<span data-ttu-id="87e72-117">从以前版本的 MBAM 升级</span><span class="sxs-lookup"><span data-stu-id="87e72-117">Upgrading from Previous Versions of MBAM</span></span>](upgrading-from-previous-versions-of-mbam.md)

    <span data-ttu-id="87e72-118">本部分提供了从以前的版本升级 MBAM 的说明。</span><span class="sxs-lookup"><span data-stu-id="87e72-118">This section provides instructions for upgrading MBAM from previous versions.</span></span>

## <span data-ttu-id="87e72-119">用于部署 MBAM 的其他资源</span><span class="sxs-lookup"><span data-stu-id="87e72-119">Other Resources for Deploying MBAM</span></span>


[<span data-ttu-id="87e72-120">Microsoft BitLocker 管理和监视2管理员指南</span><span class="sxs-lookup"><span data-stu-id="87e72-120">Microsoft BitLocker Administration and Monitoring 2 Administrator's Guide</span></span>](index.md)

[<span data-ttu-id="87e72-121">MBAM 2.0 入门</span><span class="sxs-lookup"><span data-stu-id="87e72-121">Getting Started with MBAM 2.0</span></span>](getting-started-with-mbam-20-mbam-2.md)

[<span data-ttu-id="87e72-122">计划 MBAM 2.0</span><span class="sxs-lookup"><span data-stu-id="87e72-122">Planning for MBAM 2.0</span></span>](planning-for-mbam-20-mbam-2.md)

[<span data-ttu-id="87e72-123">MBAM 2.0 的操作</span><span class="sxs-lookup"><span data-stu-id="87e72-123">Operations for MBAM 2.0</span></span>](operations-for-mbam-20-mbam-2.md)

[<span data-ttu-id="87e72-124">MBAM 2.0 疑难解答</span><span class="sxs-lookup"><span data-stu-id="87e72-124">Troubleshooting MBAM 2.0</span></span>](troubleshooting-mbam-20-mbam-2.md)

 

 





