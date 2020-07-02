---
title: Microsoft BitLocker 管理和监视2管理员指南
description: Microsoft BitLocker 管理和监视2管理员指南
author: dansimp
ms.assetid: fdb43f62-960a-4811-8802-50efdf04b4af
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 04/19/2017
ms.openlocfilehash: dd6deb6fb91c64ac8609b54114e0dd417497034a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10795426"
---
# <span data-ttu-id="2334f-103">Microsoft BitLocker 管理和监视2管理员指南</span><span class="sxs-lookup"><span data-stu-id="2334f-103">Microsoft BitLocker Administration and Monitoring 2 Administrator's Guide</span></span>

<span data-ttu-id="2334f-104">Microsoft BitLockerAdministration 和 Monitoring （MBAM）2.0 提供简化的管理界面，可用于管理 BitLocker 驱动器加密。</span><span class="sxs-lookup"><span data-stu-id="2334f-104">Microsoft BitLockerAdministration and Monitoring(MBAM)2.0 provides a simplified administrative interface that you can use to manage BitLocker drive encryption.</span></span> <span data-ttu-id="2334f-105">在 BitLockerAdministration 和监视2.0 中，你可以选择适合你的企业的 BitLocker 驱动器加密策略选项，然后使用它们来监视与这些策略的客户端合规性。</span><span class="sxs-lookup"><span data-stu-id="2334f-105">In BitLockerAdministration and Monitoring2.0, you can select BitLocker drive encryption policy options that are appropriate for your enterprise, and then use them to monitor client compliance with those policies.</span></span> <span data-ttu-id="2334f-106">您还可以报告单个计算机和整个企业的加密状态。</span><span class="sxs-lookup"><span data-stu-id="2334f-106">You can also report on the encryption status of an individual computer and on the enterprise as a whole.</span></span> <span data-ttu-id="2334f-107">此外，你可以在用户忘记其 PIN 或密码或其 BIOS 或启动记录更改时访问恢复密钥信息。</span><span class="sxs-lookup"><span data-stu-id="2334f-107">In addition, you can access recovery key information when users forget their PIN or password or when their BIOS or boot record changes.</span></span>

## <span data-ttu-id="2334f-108">空心</span><span class="sxs-lookup"><span data-stu-id="2334f-108">Outline</span></span>

- [<span data-ttu-id="2334f-109">MBAM 2.0 入门</span><span class="sxs-lookup"><span data-stu-id="2334f-109">Getting Started with MBAM 2.0</span></span>](getting-started-with-mbam-20-mbam-2.md)
  - [<span data-ttu-id="2334f-110">关于 MBAM 2.0</span><span class="sxs-lookup"><span data-stu-id="2334f-110">About MBAM 2.0</span></span>](about-mbam-20-mbam-2.md)
  - [<span data-ttu-id="2334f-111">MBAM 2.0 发行说明</span><span class="sxs-lookup"><span data-stu-id="2334f-111">Release Notes for MBAM 2.0</span></span>](release-notes-for-mbam-20-mbam-2.md)
  - [<span data-ttu-id="2334f-112">关于 MBAM 2.0 SP1</span><span class="sxs-lookup"><span data-stu-id="2334f-112">About MBAM 2.0 SP1</span></span>](about-mbam-20-sp1.md)
  - [<span data-ttu-id="2334f-113">MBAM 2.0 SP1 发行说明</span><span class="sxs-lookup"><span data-stu-id="2334f-113">Release Notes for MBAM 2.0 SP1</span></span>](release-notes-for-mbam-20-sp1.md)
  - [<span data-ttu-id="2334f-114">评估 MBAM 2.0</span><span class="sxs-lookup"><span data-stu-id="2334f-114">Evaluating MBAM 2.0</span></span>](evaluating-mbam-20-mbam-2.md)
  - [<span data-ttu-id="2334f-115">MBAM 2.0 的高级别体系结构</span><span class="sxs-lookup"><span data-stu-id="2334f-115">High-Level Architecture for MBAM 2.0</span></span>](high-level-architecture-for-mbam-20-mbam-2.md)
  - [<span data-ttu-id="2334f-116">MBAM 2.0 的辅助功能</span><span class="sxs-lookup"><span data-stu-id="2334f-116">Accessibility for MBAM 2.0</span></span>](accessibility-for-mbam-20-mbam-2.md)
- [<span data-ttu-id="2334f-117">计划 MBAM 2.0</span><span class="sxs-lookup"><span data-stu-id="2334f-117">Planning for MBAM 2.0</span></span>](planning-for-mbam-20-mbam-2.md)
  - [<span data-ttu-id="2334f-118">针对 MBAM 2.0 准备环境</span><span class="sxs-lookup"><span data-stu-id="2334f-118">Preparing your Environment for MBAM 2.0</span></span>](preparing-your-environment-for-mbam-20-mbam-2.md)
  - [<span data-ttu-id="2334f-119">MBAM 2.0 部署先决条件</span><span class="sxs-lookup"><span data-stu-id="2334f-119">MBAM 2.0 Deployment Prerequisites</span></span>](mbam-20-deployment-prerequisites-mbam-2.md)
  - [<span data-ttu-id="2334f-120">计划部署 MBAM 2.0</span><span class="sxs-lookup"><span data-stu-id="2334f-120">Planning to Deploy MBAM 2.0</span></span>](planning-to-deploy-mbam-20-mbam-2.md)
  - [<span data-ttu-id="2334f-121">MBAM 2.0 支持的配置</span><span class="sxs-lookup"><span data-stu-id="2334f-121">MBAM 2.0 Supported Configurations</span></span>](mbam-20-supported-configurations-mbam-2.md)
  - [<span data-ttu-id="2334f-122">MBAM 2.0 计划清单</span><span class="sxs-lookup"><span data-stu-id="2334f-122">MBAM 2.0 Planning Checklist</span></span>](mbam-20-planning-checklist-mbam-2.md)
- [<span data-ttu-id="2334f-123">部署 MBAM 2.0</span><span class="sxs-lookup"><span data-stu-id="2334f-123">Deploying MBAM 2.0</span></span>](deploying-mbam-20-mbam-2.md)
  - [<span data-ttu-id="2334f-124">部署 MBAM 2.0 服务器基础结构</span><span class="sxs-lookup"><span data-stu-id="2334f-124">Deploying the MBAM 2.0 Server Infrastructure</span></span>](deploying-the-mbam-20-server-infrastructure-mbam-2.md)
  - [<span data-ttu-id="2334f-125">部署 MBAM 2.0 组策略对象</span><span class="sxs-lookup"><span data-stu-id="2334f-125">Deploying MBAM 2.0 Group Policy Objects</span></span>](deploying-mbam-20-group-policy-objects-mbam-2.md)
  - [<span data-ttu-id="2334f-126">部署 MBAM 2.0 客户端</span><span class="sxs-lookup"><span data-stu-id="2334f-126">Deploying the MBAM 2.0 Client</span></span>](deploying-the-mbam-20-client-mbam-2.md)
  - [<span data-ttu-id="2334f-127">MBAM 2.0 部署清单</span><span class="sxs-lookup"><span data-stu-id="2334f-127">MBAM 2.0 Deployment Checklist</span></span>](mbam-20-deployment-checklist-mbam-2.md)
  - [<span data-ttu-id="2334f-128">从以前版本的 MBAM 升级</span><span class="sxs-lookup"><span data-stu-id="2334f-128">Upgrading from Previous Versions of MBAM</span></span>](upgrading-from-previous-versions-of-mbam.md)
- [<span data-ttu-id="2334f-129">MBAM 2.0 的操作</span><span class="sxs-lookup"><span data-stu-id="2334f-129">Operations for MBAM 2.0</span></span>](operations-for-mbam-20-mbam-2.md)
  - [<span data-ttu-id="2334f-130">结合使用 MBAM 和 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="2334f-130">Using MBAM with Configuration Manager</span></span>](using-mbam-with-configuration-manager.md)
  - [<span data-ttu-id="2334f-131">管理 MBAM 2.0 功能</span><span class="sxs-lookup"><span data-stu-id="2334f-131">Administering MBAM 2.0 Features</span></span>](administering-mbam-20-features-mbam-2.md)
  - [<span data-ttu-id="2334f-132">使用 MBAM 2.0 监视和报告 BitLocker 符合性</span><span class="sxs-lookup"><span data-stu-id="2334f-132">Monitoring and Reporting BitLocker Compliance with MBAM 2.0</span></span>](monitoring-and-reporting-bitlocker-compliance-with-mbam-20-mbam-2.md)
  - [<span data-ttu-id="2334f-133">使用 MBAM 执行 BitLocker 管理</span><span class="sxs-lookup"><span data-stu-id="2334f-133">Performing BitLocker Management with MBAM</span></span>](performing-bitlocker-management-with-mbam-mbam-2.md)
  - [<span data-ttu-id="2334f-134">维护 MBAM 2.0</span><span class="sxs-lookup"><span data-stu-id="2334f-134">Maintaining MBAM 2.0</span></span>](maintaining-mbam-20-mbam-2.md)
  - [<span data-ttu-id="2334f-135">MBAM 2.0 的安全和隐私</span><span class="sxs-lookup"><span data-stu-id="2334f-135">Security and Privacy for MBAM 2.0</span></span>](security-and-privacy-for-mbam-20-mbam-2.md)
  - [<span data-ttu-id="2334f-136">使用 PowerShell 管理 MBAM 2.0</span><span class="sxs-lookup"><span data-stu-id="2334f-136">Administering MBAM 2.0 Using PowerShell</span></span>](administering-mbam-20-using-powershell-mbam-2.md)
- [<span data-ttu-id="2334f-137">MBAM 2.0 疑难解答</span><span class="sxs-lookup"><span data-stu-id="2334f-137">Troubleshooting MBAM 2.0</span></span>](troubleshooting-mbam-20-mbam-2.md)

## <span data-ttu-id="2334f-138">详细信息</span><span class="sxs-lookup"><span data-stu-id="2334f-138">More Information</span></span>

- [<span data-ttu-id="2334f-139">MDOP 信息体验</span><span class="sxs-lookup"><span data-stu-id="2334f-139">MDOP Information Experience</span></span>](index.md)

  <span data-ttu-id="2334f-140">查找 MDOP 技术的文档、视频和其他资源。</span><span class="sxs-lookup"><span data-stu-id="2334f-140">Find documentation, videos, and other resources for MDOP technologies.</span></span>

 

 





