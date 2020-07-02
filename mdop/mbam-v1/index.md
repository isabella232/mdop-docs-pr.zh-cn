---
title: Microsoft BitLocker 管理和监视1管理员指南
description: Microsoft BitLocker 管理和监视1管理员指南
author: dansimp
ms.assetid: 4086e721-db24-4439-bdcd-ac5ef901811f
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 04/19/2017
ms.openlocfilehash: 5336108e12738a21441df8062fbcd8bd98933945
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10795428"
---
# <span data-ttu-id="d48f5-103">Microsoft BitLocker 管理和监视1管理员指南</span><span class="sxs-lookup"><span data-stu-id="d48f5-103">Microsoft BitLocker Administration and Monitoring 1 Administrator's Guide</span></span>

<span data-ttu-id="d48f5-104">Microsoft BitLocker 管理和监视（MBAM）提供简化的管理界面，可用于管理 BitLocker 驱动器加密。</span><span class="sxs-lookup"><span data-stu-id="d48f5-104">Microsoft BitLocker Administration and Monitoring (MBAM) provides a simplified administrative interface that you can use to manage BitLocker drive encryption.</span></span> <span data-ttu-id="d48f5-105">使用 MBAM，你可以选择适合你的企业的 BitLocker 加密策略选项，然后使用它们来监视客户端是否符合这些策略。</span><span class="sxs-lookup"><span data-stu-id="d48f5-105">With MBAM, you can select BitLocker encryption policy options that are appropriate to your enterprise and then use them to monitor client compliance with those policies.</span></span> <span data-ttu-id="d48f5-106">您还可以报告单个计算机和整个企业的加密状态。</span><span class="sxs-lookup"><span data-stu-id="d48f5-106">You can also report on the encryption status of an individual computer and on the entire enterprise.</span></span> <span data-ttu-id="d48f5-107">此外，当用户忘记其 PIN 或密码时，或者当其 BIOS 或启动记录发生更改时，您可以访问恢复密钥信息。</span><span class="sxs-lookup"><span data-stu-id="d48f5-107">In addition, you can access recovery key information when users forget their PIN or password, or when their BIOS or boot record changes.</span></span>

- [<span data-ttu-id="d48f5-108">MBAM 1.0 入门</span><span class="sxs-lookup"><span data-stu-id="d48f5-108">Getting Started with MBAM 1.0</span></span>](getting-started-with-mbam-10.md)  
  - [<span data-ttu-id="d48f5-109">关于 MBAM 1.0</span><span class="sxs-lookup"><span data-stu-id="d48f5-109">About MBAM 1.0</span></span>](about-mbam-10.md)
  - [<span data-ttu-id="d48f5-110">MBAM 1.0 发行说明</span><span class="sxs-lookup"><span data-stu-id="d48f5-110">Release Notes for MBAM 1.0</span></span>](release-notes-for-mbam-10.md)
  - [<span data-ttu-id="d48f5-111">评估 MBAM 1.0</span><span class="sxs-lookup"><span data-stu-id="d48f5-111">Evaluating MBAM 1.0</span></span>](evaluating-mbam-10.md)
  - [<span data-ttu-id="d48f5-112">MBAM 1.0 的高级别体系结构</span><span class="sxs-lookup"><span data-stu-id="d48f5-112">High Level Architecture for MBAM 1.0</span></span>](high-level-architecture-for-mbam-10.md)
  - [<span data-ttu-id="d48f5-113">MBAM 1.0 的辅助功能</span><span class="sxs-lookup"><span data-stu-id="d48f5-113">Accessibility for MBAM 1.0</span></span>](accessibility-for-mbam-10.md)
  - [<span data-ttu-id="d48f5-114">MBAM 1.0 隐私声明</span><span class="sxs-lookup"><span data-stu-id="d48f5-114">Privacy Statement for MBAM 1.0</span></span>](privacy-statement-for-mbam-10.md)
- [<span data-ttu-id="d48f5-115">计划 MBAM 1.0</span><span class="sxs-lookup"><span data-stu-id="d48f5-115">Planning for MBAM 1.0</span></span>](planning-for-mbam-10.md)  
  - [<span data-ttu-id="d48f5-116">针对 MBAM 1.0 准备环境</span><span class="sxs-lookup"><span data-stu-id="d48f5-116">Preparing your Environment for MBAM 1.0</span></span>](preparing-your-environment-for-mbam-10.md)
  - [<span data-ttu-id="d48f5-117">MBAM 1.0 部署先决条件</span><span class="sxs-lookup"><span data-stu-id="d48f5-117">MBAM 1.0 Deployment Prerequisites</span></span>](mbam-10-deployment-prerequisites.md)
  - [<span data-ttu-id="d48f5-118">计划部署 MBAM 1.0</span><span class="sxs-lookup"><span data-stu-id="d48f5-118">Planning to Deploy MBAM 1.0</span></span>](planning-to-deploy-mbam-10.md)
  - [<span data-ttu-id="d48f5-119">MBAM 1.0 支持的配置</span><span class="sxs-lookup"><span data-stu-id="d48f5-119">MBAM 1.0 Supported Configurations</span></span>](mbam-10-supported-configurations.md)
  - [<span data-ttu-id="d48f5-120">MBAM 1.0 计划清单</span><span class="sxs-lookup"><span data-stu-id="d48f5-120">MBAM 1.0 Planning Checklist</span></span>](mbam-10-planning-checklist.md)
- [<span data-ttu-id="d48f5-121">部署 MBAM 1.0</span><span class="sxs-lookup"><span data-stu-id="d48f5-121">Deploying MBAM 1.0</span></span>](deploying-mbam-10.md)  
  - [<span data-ttu-id="d48f5-122">部署 MBAM 1.0 服务器基础结构</span><span class="sxs-lookup"><span data-stu-id="d48f5-122">Deploying the MBAM 1.0 Server Infrastructure</span></span>](deploying-the-mbam-10-server-infrastructure.md)
  - [<span data-ttu-id="d48f5-123">部署 MBAM 1.0 组策略对象</span><span class="sxs-lookup"><span data-stu-id="d48f5-123">Deploying MBAM 1.0 Group Policy Objects</span></span>](deploying-mbam-10-group-policy-objects.md)
  - [<span data-ttu-id="d48f5-124">部署 MBAM 1.0 客户端</span><span class="sxs-lookup"><span data-stu-id="d48f5-124">Deploying the MBAM 1.0 Client</span></span>](deploying-the-mbam-10-client.md)
  - [<span data-ttu-id="d48f5-125">部署 MBAM 1.0 语言版本更新</span><span class="sxs-lookup"><span data-stu-id="d48f5-125">Deploying the MBAM 1.0 Language Release Update</span></span>](deploying-the-mbam-10-language-release-update.md)
  - [<span data-ttu-id="d48f5-126">MBAM 1.0 部署清单</span><span class="sxs-lookup"><span data-stu-id="d48f5-126">MBAM 1.0 Deployment Checklist</span></span>](mbam-10-deployment-checklist.md)
- [<span data-ttu-id="d48f5-127">MBAM 1.0 的操作</span><span class="sxs-lookup"><span data-stu-id="d48f5-127">Operations for MBAM 1.0</span></span>](operations-for-mbam-10.md)  
  - [<span data-ttu-id="d48f5-128">管理 MBAM 1.0 功能</span><span class="sxs-lookup"><span data-stu-id="d48f5-128">Administering MBAM 1.0 Features</span></span>](administering-mbam-10-features.md)
  - [<span data-ttu-id="d48f5-129">使用 MBAM 1.0 监视和报告 BitLocker 符合性</span><span class="sxs-lookup"><span data-stu-id="d48f5-129">Monitoring and Reporting BitLocker Compliance with MBAM 1.0</span></span>](monitoring-and-reporting-bitlocker-compliance-with-mbam-10.md)
  - [<span data-ttu-id="d48f5-130">使用 MBAM 执行 BitLocker 管理</span><span class="sxs-lookup"><span data-stu-id="d48f5-130">Performing BitLocker Management with MBAM</span></span>](performing-bitlocker-management-with-mbam.md)
  - [<span data-ttu-id="d48f5-131">使用 PowerShell 管理 MBAM 1.0</span><span class="sxs-lookup"><span data-stu-id="d48f5-131">Administering MBAM 1.0 by Using PowerShell</span></span>](administering-mbam-10-by-using-powershell.md)
- [<span data-ttu-id="d48f5-132">MBAM 1.0 疑难解答</span><span class="sxs-lookup"><span data-stu-id="d48f5-132">Troubleshooting MBAM 1.0</span></span>](troubleshooting-mbam-10.md)  

## <span data-ttu-id="d48f5-133">详细信息</span><span class="sxs-lookup"><span data-stu-id="d48f5-133">More Information</span></span>
- [<span data-ttu-id="d48f5-134">MDOP 信息体验</span><span class="sxs-lookup"><span data-stu-id="d48f5-134">MDOP Information Experience</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=236032)  
  <span data-ttu-id="d48f5-135">查找 MDOP 技术的文档、视频和其他资源。</span><span class="sxs-lookup"><span data-stu-id="d48f5-135">Find documentation, videos, and other resources for MDOP technologies.</span></span>
