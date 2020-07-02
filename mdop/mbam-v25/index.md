---
title: Microsoft BitLocker 管理和监控 2.5
description: Microsoft BitLocker 管理和监控 2.5
author: dansimp
ms.assetid: fd81d7de-b166-47e8-b6c7-d984830762b6
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 04/19/2017
ms.openlocfilehash: 2e5243131853207f0ed3cbb6d0cd8fb8e3d56108
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10795412"
---
# <span data-ttu-id="1f328-103">Microsoft BitLocker 管理和监控 2.5</span><span class="sxs-lookup"><span data-stu-id="1f328-103">Microsoft BitLocker Administration and Monitoring 2.5</span></span>

<span data-ttu-id="1f328-104">Microsoft BitLocker 管理和监视（MBAM）2.5 提供了简化的管理界面，可用于管理 BitLocker 驱动器加密。</span><span class="sxs-lookup"><span data-stu-id="1f328-104">Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 provides a simplified administrative interface that you can use to manage BitLocker Drive Encryption.</span></span> <span data-ttu-id="1f328-105">你可以配置 MBAM 组策略模板，这些模板使你能够设置适用于你的企业的 BitLocker 驱动器加密策略选项，然后使用它们来监视与这些策略的客户端合规性。</span><span class="sxs-lookup"><span data-stu-id="1f328-105">You configure MBAM Group Policy Templates that enable you to set BitLocker Drive Encryption policy options that are appropriate for your enterprise, and then use them to monitor client compliance with those policies.</span></span> <span data-ttu-id="1f328-106">您还可以报告单个计算机和整个企业的加密状态。</span><span class="sxs-lookup"><span data-stu-id="1f328-106">You can also report on the encryption status of an individual computer and on the enterprise as a whole.</span></span> <span data-ttu-id="1f328-107">此外，你可以在用户忘记其 PIN 或密码或其 BIOS 或启动记录更改时访问恢复密钥信息。</span><span class="sxs-lookup"><span data-stu-id="1f328-107">In addition, you can access recovery key information when users forget their PIN or password or when their BIOS or boot record changes.</span></span> <span data-ttu-id="1f328-108">有关 MBAM 的更多详细说明，请参阅[关于 MBAM 2.5](about-mbam-25.md)。</span><span class="sxs-lookup"><span data-stu-id="1f328-108">For a more detailed description of MBAM, see [About MBAM 2.5](about-mbam-25.md).</span></span>

<span data-ttu-id="1f328-109">若要获取 MBAM，请参阅[如何获取 MDOP](https://docs.microsoft.com/microsoft-desktop-optimization-pack/index#how-to-get-mdop)。</span><span class="sxs-lookup"><span data-stu-id="1f328-109">To obtain MBAM, see [How Do I Get MDOP](https://docs.microsoft.com/microsoft-desktop-optimization-pack/index#how-to-get-mdop).</span></span>

## <span data-ttu-id="1f328-110">空心</span><span class="sxs-lookup"><span data-stu-id="1f328-110">Outline</span></span>

- <a href="" id="getting-started-with-mbam-2-5"></a>[<span data-ttu-id="1f328-111">MBAM 2.5 入门</span><span class="sxs-lookup"><span data-stu-id="1f328-111">Getting Started with MBAM 2.5</span></span>](getting-started-with-mbam-25.md)
  - [<span data-ttu-id="1f328-112">关于 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="1f328-112">About MBAM 2.5</span></span>](about-mbam-25.md)
  - [<span data-ttu-id="1f328-113">MBAM 2.5 的发行说明</span><span class="sxs-lookup"><span data-stu-id="1f328-113">Release Notes for MBAM 2.5</span></span>](release-notes-for-mbam-25.md)
  - [<span data-ttu-id="1f328-114">关于 MBAM 2.5 SP1</span><span class="sxs-lookup"><span data-stu-id="1f328-114">About MBAM 2.5 SP1</span></span>](about-mbam-25-sp1.md)
  - [<span data-ttu-id="1f328-115">MBAM 2.5 SP1 的发行说明</span><span class="sxs-lookup"><span data-stu-id="1f328-115">Release Notes for MBAM 2.5 SP1</span></span>](release-notes-for-mbam-25-sp1.md)
  - [<span data-ttu-id="1f328-116">在测试环境中评估 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="1f328-116">Evaluating MBAM 2.5 in a Test Environment</span></span>](evaluating-mbam-25-in-a-test-environment.md)
  - [<span data-ttu-id="1f328-117">MBAM 2.5 的高级别体系结构</span><span class="sxs-lookup"><span data-stu-id="1f328-117">High-Level Architecture for MBAM 2.5</span></span>](high-level-architecture-for-mbam-25.md)
  - [<span data-ttu-id="1f328-118">MBAM 2.5 的辅助功能</span><span class="sxs-lookup"><span data-stu-id="1f328-118">Accessibility for MBAM 2.5</span></span>](accessibility-for-mbam-25.md)
- <a href="" id="planning-for-mbam-2-5"></a>[<span data-ttu-id="1f328-119">规划 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="1f328-119">Planning for MBAM 2.5</span></span>](planning-for-mbam-25.md)
  - [<span data-ttu-id="1f328-120">为 MBAM 2.5 准备你的环境</span><span class="sxs-lookup"><span data-stu-id="1f328-120">Preparing your Environment for MBAM 2.5</span></span>](preparing-your-environment-for-mbam-25.md)
  - [<span data-ttu-id="1f328-121">MBAM 2.5 部署先决条件</span><span class="sxs-lookup"><span data-stu-id="1f328-121">MBAM 2.5 Deployment Prerequisites</span></span>](mbam-25-deployment-prerequisites.md)
  - [<span data-ttu-id="1f328-122">规划 MBAM 2.5 组策略要求</span><span class="sxs-lookup"><span data-stu-id="1f328-122">Planning for MBAM 2.5 Group Policy Requirements</span></span>](planning-for-mbam-25-group-policy-requirements.md)
  - [<span data-ttu-id="1f328-123">规划 MBAM 2.5 组和帐户</span><span class="sxs-lookup"><span data-stu-id="1f328-123">Planning for MBAM 2.5 Groups and Accounts</span></span>](planning-for-mbam-25-groups-and-accounts.md)
  - [<span data-ttu-id="1f328-124">规划如何保护 MBAM 网站</span><span class="sxs-lookup"><span data-stu-id="1f328-124">Planning How to Secure the MBAM Websites</span></span>](planning-how-to-secure-the-mbam-websites.md)
  - [<span data-ttu-id="1f328-125">规划部署 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="1f328-125">Planning to Deploy MBAM 2.5</span></span>](planning-to-deploy-mbam-25.md)
  - [<span data-ttu-id="1f328-126">MBAM 2.5 支持的配置</span><span class="sxs-lookup"><span data-stu-id="1f328-126">MBAM 2.5 Supported Configurations</span></span>](mbam-25-supported-configurations.md)
  - [<span data-ttu-id="1f328-127">规划 MBAM 2.5 高可用性</span><span class="sxs-lookup"><span data-stu-id="1f328-127">Planning for MBAM 2.5 High Availability</span></span>](planning-for-mbam-25-high-availability.md)
  - [<span data-ttu-id="1f328-128">MBAM 2.5 安全注意事项</span><span class="sxs-lookup"><span data-stu-id="1f328-128">MBAM 2.5 Security Considerations</span></span>](mbam-25-security-considerations.md)
  - [<span data-ttu-id="1f328-129">MBAM 2.5 规划清单</span><span class="sxs-lookup"><span data-stu-id="1f328-129">MBAM 2.5 Planning Checklist</span></span>](mbam-25-planning-checklist.md)
- <a href="" id="deploying-mbam-2-5"></a>[<span data-ttu-id="1f328-130">部署 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="1f328-130">Deploying MBAM 2.5</span></span>](deploying-mbam-25.md)
  - [<span data-ttu-id="1f328-131">部署 MBAM 2.5 服务器基础结构</span><span class="sxs-lookup"><span data-stu-id="1f328-131">Deploying the MBAM 2.5 Server Infrastructure</span></span>](deploying-the-mbam-25-server-infrastructure.md)
  - [<span data-ttu-id="1f328-132">部署 MBAM 2.5 组策略对象</span><span class="sxs-lookup"><span data-stu-id="1f328-132">Deploying MBAM 2.5 Group Policy Objects</span></span>](deploying-mbam-25-group-policy-objects.md)
  - [<span data-ttu-id="1f328-133">部署 MBAM 2.5 客户端</span><span class="sxs-lookup"><span data-stu-id="1f328-133">Deploying the MBAM 2.5 Client</span></span>](deploying-the-mbam-25-client.md)
  - [<span data-ttu-id="1f328-134">MBAM 2.5 部署清单</span><span class="sxs-lookup"><span data-stu-id="1f328-134">MBAM 2.5 Deployment Checklist</span></span>](mbam-25-deployment-checklist.md)
  - [<span data-ttu-id="1f328-135">从先前版本升级到 MBAM 2.5 或 MBAM 2.5 SP1</span><span class="sxs-lookup"><span data-stu-id="1f328-135">Upgrading to MBAM 2.5 or MBAM 2.5 SP1 from Previous Versions</span></span>](upgrading-to-mbam-25-or-mbam-25-sp1-from-previous-versions.md)
  - [<span data-ttu-id="1f328-136">删除 MBAM 服务器功能或软件</span><span class="sxs-lookup"><span data-stu-id="1f328-136">Removing MBAM Server Features or Software</span></span>](removing-mbam-server-features-or-software.md)
- <a href="" id="operations-for-mbam-2-5"></a>[<span data-ttu-id="1f328-137">MBAM 2.5 的操作</span><span class="sxs-lookup"><span data-stu-id="1f328-137">Operations for MBAM 2.5</span></span>](operations-for-mbam-25.md)
  - [<span data-ttu-id="1f328-138">管理 MBAM 2.5 功能</span><span class="sxs-lookup"><span data-stu-id="1f328-138">Administering MBAM 2.5 Features</span></span>](administering-mbam-25-features.md)
  - [<span data-ttu-id="1f328-139">监视和报告 BitLocker 与 MBAM 2.5 的相容性</span><span class="sxs-lookup"><span data-stu-id="1f328-139">Monitoring and Reporting BitLocker Compliance with MBAM 2.5</span></span>](monitoring-and-reporting-bitlocker-compliance-with-mbam-25.md)
  - [<span data-ttu-id="1f328-140">使用 MBAM 2.5 执行 BitLocker 管理</span><span class="sxs-lookup"><span data-stu-id="1f328-140">Performing BitLocker Management with MBAM 2.5</span></span>](performing-bitlocker-management-with-mbam-25.md)
  - [<span data-ttu-id="1f328-141">维护 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="1f328-141">Maintaining MBAM 2.5</span></span>](maintaining-mbam-25.md)
  - [<span data-ttu-id="1f328-142">使用 Windows PowerShell 管理 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="1f328-142">Using Windows PowerShell to Administer MBAM 2.5</span></span>](using-windows-powershell-to-administer-mbam-25.md)
- <a href="" id="troubleshooting-mbam-2-5"></a>[<span data-ttu-id="1f328-143">MBAM 2.5 故障排除</span><span class="sxs-lookup"><span data-stu-id="1f328-143">Troubleshooting MBAM 2.5</span></span>](troubleshooting-mbam-25.md)
- <a href="" id="technical-reference-for-mbam-2-5"></a>[<span data-ttu-id="1f328-144">MBAM 2.5 的技术参考</span><span class="sxs-lookup"><span data-stu-id="1f328-144">Technical Reference for MBAM 2.5</span></span>](technical-reference-for-mbam-25.md)
  - [<span data-ttu-id="1f328-145">客户端事件日志</span><span class="sxs-lookup"><span data-stu-id="1f328-145">Client Event Logs</span></span>](client-event-logs.md)
  - [<span data-ttu-id="1f328-146">服务器事件日志</span><span class="sxs-lookup"><span data-stu-id="1f328-146">Server Event Logs</span></span>](server-event-logs.md)

## <span data-ttu-id="1f328-147">详细信息</span><span class="sxs-lookup"><span data-stu-id="1f328-147">More Information</span></span>

- [<span data-ttu-id="1f328-148">MDOP 信息体验</span><span class="sxs-lookup"><span data-stu-id="1f328-148">MDOP Information Experience</span></span>](index.md)

  <span data-ttu-id="1f328-149">查找 MDOP 技术的文档、视频和其他资源。</span><span class="sxs-lookup"><span data-stu-id="1f328-149">Find documentation, videos, and other resources for MDOP technologies.</span></span>

- [<span data-ttu-id="1f328-150">MBAM 部署指南</span><span class="sxs-lookup"><span data-stu-id="1f328-150">MBAM Deployment Guide</span></span>](https://www.microsoft.com/download/details.aspx?id=38398)

  <span data-ttu-id="1f328-151">获取有关为 MBAM 选择部署方法的帮助，包括每个方法的分步说明。</span><span class="sxs-lookup"><span data-stu-id="1f328-151">Get help in choosing a deployment method for MBAM, including step-by-step instructions for each method.</span></span>
    
- [<span data-ttu-id="1f328-152">在 MBAM 2.5 SP1 服务器上应用修补程序</span><span class="sxs-lookup"><span data-stu-id="1f328-152">Apply Hotfixes on MBAM 2.5 SP1 Server</span></span>](apply-hotfix-for-mbam-25-sp1.md)

  <span data-ttu-id="1f328-153">如何应用 MBAM 2.5 SP1 Server 修补程序的指南</span><span class="sxs-lookup"><span data-stu-id="1f328-153">Guide of how to apply MBAM 2.5 SP1 Server hotfixes</span></span>
