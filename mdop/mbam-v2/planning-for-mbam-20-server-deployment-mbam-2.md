---
title: 计划 MBAM 2.0 服务器部署
description: 计划 MBAM 2.0 服务器部署
author: dansimp
ms.assetid: b57f1a42-134f-4997-8697-7fbed08e2fc4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 57e6510556522dce029c958172bd89a361e06b83
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798089"
---
# <span data-ttu-id="cae93-103">计划 MBAM 2.0 服务器部署</span><span class="sxs-lookup"><span data-stu-id="cae93-103">Planning for MBAM 2.0 Server Deployment</span></span>


<span data-ttu-id="cae93-104">Microsoft BitLocker 管理和监视（MBAM）服务器基础结构取决于一组服务器功能，这些功能可以基于企业的要求安装在一台或多台服务器计算机上。</span><span class="sxs-lookup"><span data-stu-id="cae93-104">The Microsoft BitLocker Administration and Monitoring (MBAM) server infrastructure depends on a set of server features that can be installed on one or more server computers, based on the requirements of the enterprise.</span></span> <span data-ttu-id="cae93-105">如果你要安装 Microsoft BitLocker 管理并通过 Configuration Manager 拓扑进行监视，请参阅[计划通过 Configuration Manager 部署 MBAM](planning-to-deploy-mbam-with-configuration-manager-2.md)。</span><span class="sxs-lookup"><span data-stu-id="cae93-105">If you are installing Microsoft BitLocker Administration and Monitoring with the Configuration Manager topology, see [Planning to Deploy MBAM with Configuration Manager](planning-to-deploy-mbam-with-configuration-manager-2.md).</span></span>

<span data-ttu-id="cae93-106">**注意** 建议仅针对测试环境对单个服务器上的 Microsoft BitLocker 管理和监视进行安装。</span><span class="sxs-lookup"><span data-stu-id="cae93-106">**Note** Installations of Microsoft BitLocker Administration and Monitoring on a single server are recommended only for test environments.</span></span>

 

## <span data-ttu-id="cae93-107">规划 MBAM Server 部署</span><span class="sxs-lookup"><span data-stu-id="cae93-107">Planning for MBAM Server Deployment</span></span>


<span data-ttu-id="cae93-108">MBAM 服务器部署的基础结构包括以下功能：</span><span class="sxs-lookup"><span data-stu-id="cae93-108">The infrastructure for an MBAM Server deployment includes the following features:</span></span>

-   <span data-ttu-id="cae93-109">恢复数据库</span><span class="sxs-lookup"><span data-stu-id="cae93-109">Recovery Database</span></span>

-   <span data-ttu-id="cae93-110">合规性和审核数据库</span><span class="sxs-lookup"><span data-stu-id="cae93-110">Compliance and Audit Database</span></span>

-   <span data-ttu-id="cae93-111">合规性和审核报告</span><span class="sxs-lookup"><span data-stu-id="cae93-111">Compliance and Audit Reports</span></span>

-   <span data-ttu-id="cae93-112">自助服务门户</span><span class="sxs-lookup"><span data-stu-id="cae93-112">Self-Service Portal</span></span>

-   <span data-ttu-id="cae93-113">管理和监视服务器</span><span class="sxs-lookup"><span data-stu-id="cae93-113">Administration and Monitoring Server</span></span>

-   <span data-ttu-id="cae93-114">MBAM 组策略模板</span><span class="sxs-lookup"><span data-stu-id="cae93-114">MBAM Group Policy Template</span></span>

<span data-ttu-id="cae93-115">MBAM 服务器数据库和功能可以安装在不同的配置中，具体取决于你的可伸缩性要求。</span><span class="sxs-lookup"><span data-stu-id="cae93-115">MBAM Server databases and features can be installed in different configurations, depending on your scalability requirements.</span></span> <span data-ttu-id="cae93-116">所有 MBAM 服务器功能都可以安装在一台服务器上，也可以分布在多台服务器上。</span><span class="sxs-lookup"><span data-stu-id="cae93-116">All MBAM Server features can be installed on a single server or distributed across multiple servers.</span></span> <span data-ttu-id="cae93-117">我们建议你对生产环境使用双服务器配置，尽管还可以使用2到4台服务器的配置，具体取决于你的计算要求。</span><span class="sxs-lookup"><span data-stu-id="cae93-117">We recommend that you use a two-server configuration for production environments, although configurations of two to four servers can also be used, depending on your computing requirements.</span></span>

<span data-ttu-id="cae93-118">每个 MBAM 功能都具有特定的先决条件。</span><span class="sxs-lookup"><span data-stu-id="cae93-118">Each MBAM feature has specific prerequisites.</span></span> <span data-ttu-id="cae93-119">有关服务器功能必备条件和硬件和软件要求的完整列表，请参阅[MBAM 2.0 部署先决条件](mbam-20-deployment-prerequisites-mbam-2.md)和[MBAM 2.0 支持的配置](mbam-20-supported-configurations-mbam-2.md)。</span><span class="sxs-lookup"><span data-stu-id="cae93-119">For a full list of server feature prerequisites and hardware and software requirements, see [MBAM 2.0 Deployment Prerequisites](mbam-20-deployment-prerequisites-mbam-2.md) and [MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md).</span></span>

<span data-ttu-id="cae93-120">除了服务器相关的 MBAM 功能之外，服务器设置应用程序还包含一个 MBAM 组策略模板。</span><span class="sxs-lookup"><span data-stu-id="cae93-120">In addition to the server-related MBAM features, the Server Setup application includes an MBAM Group Policy template.</span></span> <span data-ttu-id="cae93-121">该模板包含您配置用于管理企业中的 BitLocker 驱动器加密的组策略对象（GPO）设置。</span><span class="sxs-lookup"><span data-stu-id="cae93-121">The template contains Group Policy Object (GPO) settings that you configure to manage BitLocker Drive Encryption in the enterprise.</span></span> <span data-ttu-id="cae93-122">你可以在任何可运行组策略管理控制台（GPMC）或高级组策略管理（AGPM）的计算机上安装此模板。</span><span class="sxs-lookup"><span data-stu-id="cae93-122">You can install this template on any computer that can run the Group Policy Management Console (GPMC) or Advanced Group Policy Management (AGPM).</span></span>

<span data-ttu-id="cae93-123">在规划 MBAM 服务器部署时，请考虑 MBAM 中的 BitLocker 恢复密钥仅供一次性使用，之后恢复密钥将过期。</span><span class="sxs-lookup"><span data-stu-id="cae93-123">As you plan the MBAM Server deployment, consider that BitLocker recovery keys in MBAM are intended for single use only, after which recovery keys expire.</span></span> <span data-ttu-id="cae93-124">为了使密钥在使用后过期，必须通过问讯台门户或自助服务门户进行检索。</span><span class="sxs-lookup"><span data-stu-id="cae93-124">In order for the keys to expire after use, they must be retrieved through the Help Desk Portal or the Self-Service Portal.</span></span>

## <span data-ttu-id="cae93-125">MBAM 服务器功能的部署顺序</span><span class="sxs-lookup"><span data-stu-id="cae93-125">Order of Deployment of MBAM Server Features</span></span>


<span data-ttu-id="cae93-126">若要在多台服务器上部署 MBAM 功能，必须按照以下顺序安装这些功能：</span><span class="sxs-lookup"><span data-stu-id="cae93-126">To deploy MBAM features on multiple servers, you have to install the features in the following order:</span></span>

1.  <span data-ttu-id="cae93-127">恢复数据库</span><span class="sxs-lookup"><span data-stu-id="cae93-127">Recovery Database</span></span>

2.  <span data-ttu-id="cae93-128">合规性和审核数据库</span><span class="sxs-lookup"><span data-stu-id="cae93-128">Compliance and Audit Database</span></span>

3.  <span data-ttu-id="cae93-129">合规性审核和报告</span><span class="sxs-lookup"><span data-stu-id="cae93-129">Compliance Audit and Reports</span></span>

4.  <span data-ttu-id="cae93-130">自助服务门户</span><span class="sxs-lookup"><span data-stu-id="cae93-130">Self-Service Portal</span></span>

5.  <span data-ttu-id="cae93-131">管理和监视服务器</span><span class="sxs-lookup"><span data-stu-id="cae93-131">Administration and Monitoring Server</span></span>

6.  <span data-ttu-id="cae93-132">MBAM 组策略模板</span><span class="sxs-lookup"><span data-stu-id="cae93-132">MBAM Group Policy Template</span></span>

<span data-ttu-id="cae93-133">**注意** 跟踪安装每个功能的计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="cae93-133">**Note** Keep track of the names of the computers on which you install each feature.</span></span> <span data-ttu-id="cae93-134">您必须在整个安装过程中使用此信息。</span><span class="sxs-lookup"><span data-stu-id="cae93-134">You have to use this information throughout the installation process.</span></span> <span data-ttu-id="cae93-135">您可以打印和使用部署清单来帮助完成这一工作。</span><span class="sxs-lookup"><span data-stu-id="cae93-135">You can print and use a deployment checklist to assist in this effort.</span></span> <span data-ttu-id="cae93-136">有关 MBAM 部署清单的详细信息，请参阅[MBAM 2.0 部署清单](mbam-20-deployment-checklist-mbam-2.md)。</span><span class="sxs-lookup"><span data-stu-id="cae93-136">For more information about the MBAM Deployment Checklist, see [MBAM 2.0 Deployment Checklist](mbam-20-deployment-checklist-mbam-2.md).</span></span>

 

## <span data-ttu-id="cae93-137">相关主题</span><span class="sxs-lookup"><span data-stu-id="cae93-137">Related topics</span></span>


[<span data-ttu-id="cae93-138">计划部署 MBAM 2.0</span><span class="sxs-lookup"><span data-stu-id="cae93-138">Planning to Deploy MBAM 2.0</span></span>](planning-to-deploy-mbam-20-mbam-2.md)

[<span data-ttu-id="cae93-139">部署 MBAM 2.0 服务器基础结构</span><span class="sxs-lookup"><span data-stu-id="cae93-139">Deploying the MBAM 2.0 Server Infrastructure</span></span>](deploying-the-mbam-20-server-infrastructure-mbam-2.md)

 

 





