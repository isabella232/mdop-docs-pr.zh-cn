---
title: 计划 MBAM 1.0 服务器部署
description: 计划 MBAM 1.0 服务器部署
author: dansimp
ms.assetid: 3cbef284-3092-4c42-9234-2826b18ddef1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 76ff9c444ce3f9c39161341610fb0cd9a763dc6d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798043"
---
# <span data-ttu-id="046f5-103">计划 MBAM 1.0 服务器部署</span><span class="sxs-lookup"><span data-stu-id="046f5-103">Planning for MBAM 1.0 Server Deployment</span></span>


<span data-ttu-id="046f5-104">Microsoft BitLocker 管理和监视（MBAM）服务器基础结构取决于一组服务器功能，这些功能可以基于企业的要求安装在一台或多台服务器计算机上。</span><span class="sxs-lookup"><span data-stu-id="046f5-104">The Microsoft BitLocker Administration and Monitoring (MBAM) server infrastructure depends on a set of server features that can be installed on one or more server computers, based on the requirements of your enterprise.</span></span>

## <span data-ttu-id="046f5-105">规划 MBAM Server 部署</span><span class="sxs-lookup"><span data-stu-id="046f5-105">Planning for MBAM Server deployment</span></span>


<span data-ttu-id="046f5-106">以下 MBAM 功能表示 MBAM 服务器部署的服务器基础结构：</span><span class="sxs-lookup"><span data-stu-id="046f5-106">The following MBAM features represent the server infrastructure for an MBAM server deployment:</span></span>

-   <span data-ttu-id="046f5-107">恢复和硬件数据库</span><span class="sxs-lookup"><span data-stu-id="046f5-107">Recovery and Hardware Database</span></span>

-   <span data-ttu-id="046f5-108">合规性和审核数据库</span><span class="sxs-lookup"><span data-stu-id="046f5-108">Compliance and Audit Database</span></span>

-   <span data-ttu-id="046f5-109">合规性和审核报告</span><span class="sxs-lookup"><span data-stu-id="046f5-109">Compliance and Audit Reports</span></span>

-   <span data-ttu-id="046f5-110">管理和监视服务器</span><span class="sxs-lookup"><span data-stu-id="046f5-110">Administration and Monitoring Server</span></span>

<span data-ttu-id="046f5-111">MBAM 服务器数据库和功能可以安装在不同的配置中，具体取决于你的可伸缩性需求。</span><span class="sxs-lookup"><span data-stu-id="046f5-111">MBAM server databases and features can be installed in different configurations, depending on your scalability needs.</span></span> <span data-ttu-id="046f5-112">所有 MBAM 服务器功能都可以安装在一台服务器上，也可以分布在多台服务器上。</span><span class="sxs-lookup"><span data-stu-id="046f5-112">All MBAM Server features can be installed on a single server or distributed across multiple servers.</span></span> <span data-ttu-id="046f5-113">通常，我们建议你对生产环境使用三服务器或五台服务器配置，尽管也可以使用两台或四台服务器的配置，具体取决于你的计算需求。</span><span class="sxs-lookup"><span data-stu-id="046f5-113">Generally, we recommend that you use a three-server or five-server configuration for production environments, although configurations of two or four servers can also be used, depending on your computing needs.</span></span>

<span data-ttu-id="046f5-114">**注意** 有关 MBAM 和推荐部署拓扑的性能可伸缩性的详细信息，请参阅 MBAM 可伸缩性和高可用性指南白皮书 <https://go.microsoft.com/fwlink/p/?LinkId=258314> 。</span><span class="sxs-lookup"><span data-stu-id="046f5-114">**Note** For more information about performance scalability of MBAM and recommended deployment topologies, see the MBAM Scalability and High-Availability Guide white paper at <https://go.microsoft.com/fwlink/p/?LinkId=258314>.</span></span>

 

<span data-ttu-id="046f5-115">每个 MBAM 功能都具有特定的先决条件。</span><span class="sxs-lookup"><span data-stu-id="046f5-115">Each MBAM feature has specific prerequisites.</span></span> <span data-ttu-id="046f5-116">有关服务器功能必备条件和硬件和软件要求的完整列表，请参阅[MBAM 1.0 部署先决条件](mbam-10-deployment-prerequisites.md)和[MBAM 1.0 支持的配置](mbam-10-supported-configurations.md)。</span><span class="sxs-lookup"><span data-stu-id="046f5-116">For a full list of server feature prerequisites and hardware and software requirements, see [MBAM 1.0 Deployment Prerequisites](mbam-10-deployment-prerequisites.md) and [MBAM 1.0 Supported Configurations](mbam-10-supported-configurations.md).</span></span>

<span data-ttu-id="046f5-117">除了服务器相关的 MBAM 功能之外，服务器设置应用程序还包含一个 MBAM 组策略模板。</span><span class="sxs-lookup"><span data-stu-id="046f5-117">In addition to the server-related MBAM features, the server Setup application includes an MBAM Group Policy template.</span></span> <span data-ttu-id="046f5-118">此模板可以安装在可运行组策略管理控制台（GPMC）或高级组策略管理（AGPM）的任何计算机上。</span><span class="sxs-lookup"><span data-stu-id="046f5-118">This template can be installed on any computer that is able to run the Group Policy Management Console (GPMC) or Advanced Group Policy Management (AGPM).</span></span>

## <span data-ttu-id="046f5-119">MBAM 服务器功能的部署顺序</span><span class="sxs-lookup"><span data-stu-id="046f5-119">Order of deployment of MBAM Server Features</span></span>


<span data-ttu-id="046f5-120">部署 MBAM 服务器功能时，请按以下顺序安装这些功能：</span><span class="sxs-lookup"><span data-stu-id="046f5-120">When you deploy the MBAM Server features, install the features in the following order:</span></span>

1.  <span data-ttu-id="046f5-121">恢复和硬件数据库</span><span class="sxs-lookup"><span data-stu-id="046f5-121">Recovery and Hardware Database</span></span>

2.  <span data-ttu-id="046f5-122">合规性和审核数据库</span><span class="sxs-lookup"><span data-stu-id="046f5-122">Compliance and Audit Database</span></span>

3.  <span data-ttu-id="046f5-123">合规性审核和报告</span><span class="sxs-lookup"><span data-stu-id="046f5-123">Compliance Audit and Reports</span></span>

4.  <span data-ttu-id="046f5-124">管理和监视服务器</span><span class="sxs-lookup"><span data-stu-id="046f5-124">Administration and Monitoring Server</span></span>

5.  <span data-ttu-id="046f5-125">策略模板</span><span class="sxs-lookup"><span data-stu-id="046f5-125">Policy Template</span></span>

<span data-ttu-id="046f5-126">**注意** 跟踪安装每个功能的计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="046f5-126">**Note** Keep track of the names of the computers on which you install each feature.</span></span> <span data-ttu-id="046f5-127">您将在整个安装过程中使用此信息。</span><span class="sxs-lookup"><span data-stu-id="046f5-127">You will use this information throughout the installation process.</span></span> <span data-ttu-id="046f5-128">你可以打印和使用部署清单来帮助你完成安装过程。</span><span class="sxs-lookup"><span data-stu-id="046f5-128">You can print and use a deployment checklist to assist you in the installation process.</span></span> <span data-ttu-id="046f5-129">有关 MBAM 部署清单的详细信息，请参阅[MBAM 1.0 部署清单](mbam-10-deployment-checklist.md)。</span><span class="sxs-lookup"><span data-stu-id="046f5-129">For more information about the MBAM deployment checklist, see [MBAM 1.0 Deployment Checklist](mbam-10-deployment-checklist.md).</span></span>

 

## <span data-ttu-id="046f5-130">相关主题</span><span class="sxs-lookup"><span data-stu-id="046f5-130">Related topics</span></span>


[<span data-ttu-id="046f5-131">计划部署 MBAM 1.0</span><span class="sxs-lookup"><span data-stu-id="046f5-131">Planning to Deploy MBAM 1.0</span></span>](planning-to-deploy-mbam-10.md)

[<span data-ttu-id="046f5-132">部署 MBAM 1.0 服务器基础结构</span><span class="sxs-lookup"><span data-stu-id="046f5-132">Deploying the MBAM 1.0 Server Infrastructure</span></span>](deploying-the-mbam-10-server-infrastructure.md)

 

 





