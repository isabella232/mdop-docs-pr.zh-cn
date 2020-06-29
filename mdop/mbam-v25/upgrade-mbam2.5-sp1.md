---
title: 从 MBAM 2.5 升级到 MBAM 2.5 SP1 服务发布更新
author: dansimp
ms.author: ksharma
manager: miaposto
audience: ITPro
ms.topic: article
ms.prod: w10
ms.localizationpriority: Normal
ms.openlocfilehash: 372822e1ec049871c62af9f429290b88bbfac949
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798128"
---
# <span data-ttu-id="61d32-102">从 MBAM 2.5 升级到 MBAM 2.5 SP1 服务发布更新</span><span class="sxs-lookup"><span data-stu-id="61d32-102">Upgrade from MBAM 2.5 to MBAM 2.5 SP1 Servicing Release Update</span></span>

<span data-ttu-id="61d32-103">本文提供了升级 Microsoft BitLocker 管理和监视（MBAM）2.5 到 MBAM 2.5 Service Pack 1 （SP1）和[Microsoft 桌面优化包（MDOP）在独立配置中可能2019服务更新](https://support.microsoft.com/help/4505175/may-2019-servicing-release-for-microsoft-desktop-optimization-pack)的分步说明。</span><span class="sxs-lookup"><span data-stu-id="61d32-103">This article provides step-by-step instructions to upgrade Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 to MBAM 2.5 Service Pack 1 (SP1) together with the [Microsoft Desktop Optimization Pack (MDOP) May 2019 servicing update](https://support.microsoft.com/help/4505175/may-2019-servicing-release-for-microsoft-desktop-optimization-pack) in a standalone configuration.</span></span>

<span data-ttu-id="61d32-104">在本指南中，我们将使用两个服务器的配置。</span><span class="sxs-lookup"><span data-stu-id="61d32-104">In this guide, we will use a two-server configuration.</span></span> <span data-ttu-id="61d32-105">一台服务器将是运行 Microsoft SQL Server 2016 的数据库服务器。</span><span class="sxs-lookup"><span data-stu-id="61d32-105">One server will be a database server that's running Microsoft SQL Server 2016.</span></span> <span data-ttu-id="61d32-106">此服务器将托管 MBAM 数据库和报告。</span><span class="sxs-lookup"><span data-stu-id="61d32-106">This server will host the MBAM databases and reports.</span></span> <span data-ttu-id="61d32-107">另一台服务器将是 Windows Server 2012 R2 web 服务器。</span><span class="sxs-lookup"><span data-stu-id="61d32-107">The other server will be a Windows Server 2012 R2 web server.</span></span> <span data-ttu-id="61d32-108">此服务器将托管 "管理和监视" 和 "自助服务门户"。</span><span class="sxs-lookup"><span data-stu-id="61d32-108">This server will host "Administration and Monitoring" and "Self-Service Portal."</span></span>

## <span data-ttu-id="61d32-109">准备升级 MBAM 2.5 SP1</span><span class="sxs-lookup"><span data-stu-id="61d32-109">Prepare to upgrade MBAM 2.5 SP1</span></span>

### <span data-ttu-id="61d32-110">了解你的环境中的 MBAM 服务器</span><span class="sxs-lookup"><span data-stu-id="61d32-110">Know the MBAM servers in your environment</span></span>

1. <span data-ttu-id="61d32-111">SQL Server 数据库引擎：托管 MBAM 数据库的服务器。</span><span class="sxs-lookup"><span data-stu-id="61d32-111">SQL Server Database Engine: Server that hosts the MBAM databases.</span></span>
2. <span data-ttu-id="61d32-112">SQL Server Reporting Services：托管 MBAM 报表的服务器。</span><span class="sxs-lookup"><span data-stu-id="61d32-112">SQL Server Reporting Services: Server that hosts the MBAM reports.</span></span>
3. <span data-ttu-id="61d32-113">Internet information Services （IIS） web 服务器：托管 MBAM Web 应用程序和 MBAM 服务的服务器。</span><span class="sxs-lookup"><span data-stu-id="61d32-113">Internet Information Services (IIS) web servers: Server that hosts MBAM Web Applications and MBAM services.</span></span>
4. <span data-ttu-id="61d32-114">可选Microsoft System Center Configuration Manager 主站点服务器：在此服务器上运行 MBAM 配置应用程序，以将 MBAM 报告与 Configuration Manager 集成。</span><span class="sxs-lookup"><span data-stu-id="61d32-114">(Optional) Microsoft System Center Configuration Manager primary site server: The MBAM configuration application is run on this server to integrate MBAM reports with Configuration Manager.</span></span> <span data-ttu-id="61d32-115">然后，这些报表将与 Configuration Manager SQL Server Reporting Services （SSRS）实例上的现有配置管理器报告合并。</span><span class="sxs-lookup"><span data-stu-id="61d32-115">These reports are then merged with existing Configuration Manager reports on the Configuration Manager SQL Server Reporting Services (SSRS) instance.</span></span>

### <span data-ttu-id="61d32-116">标识服务帐户、组、服务器名称和报表 URL</span><span class="sxs-lookup"><span data-stu-id="61d32-116">Identify service accounts, groups, server name, and reports URL</span></span>

1. <span data-ttu-id="61d32-117">标识 IIS web 服务器用于在 MBAM 数据库中读取和写入数据的 MBAM 应用程序池服务帐户。</span><span class="sxs-lookup"><span data-stu-id="61d32-117">Identify the MBAM application pool service account that's used by IIS web servers to read and write data to MBAM databases.</span></span>
2. <span data-ttu-id="61d32-118">标识在 MBAM web 功能配置和 "报表" web 服务 URL 期间使用的组。</span><span class="sxs-lookup"><span data-stu-id="61d32-118">Identify the groups that are used during the MBAM web features configuration and the reports web service URL.</span></span>
3. <span data-ttu-id="61d32-119">标识 SQL Server 名称和实例名称。</span><span class="sxs-lookup"><span data-stu-id="61d32-119">Identify the SQL Server name and instance name.</span></span> <span data-ttu-id="61d32-120">观看此视频以了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="61d32-120">Watch this video to learn more.</span></span>

    > [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE3ANP1]

4. <span data-ttu-id="61d32-121">确定用于从合规性和审核数据库中读取合规性数据的 SQL Server Reporting Services 帐户。</span><span class="sxs-lookup"><span data-stu-id="61d32-121">Identify the SQL Server Reporting Services Account that's used for reading compliance data from the Compliance and Audit database.</span></span> <span data-ttu-id="61d32-122">观看此视频以了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="61d32-122">Watch this video to learn more.</span></span>

    > [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE3ALdZ]

## <span data-ttu-id="61d32-123">将 MBAM 基础结构升级到可用的最新版本</span><span class="sxs-lookup"><span data-stu-id="61d32-123">Upgrade the MBAM infrastructure to the latest version available</span></span>

<span data-ttu-id="61d32-124">MBAM 服务器基础结构的安装或升级始终按下面列出的顺序执行：</span><span class="sxs-lookup"><span data-stu-id="61d32-124">MBAM Server infrastructure installation or upgrade is always performed in the order listed below:</span></span>

- <span data-ttu-id="61d32-125">SQL Server 数据库引擎：数据库</span><span class="sxs-lookup"><span data-stu-id="61d32-125">SQL Server Database Engine: Databases</span></span>
- <span data-ttu-id="61d32-126">SQL Server Reporting Services：报表</span><span class="sxs-lookup"><span data-stu-id="61d32-126">SQL Server Reporting Services: Reports</span></span>
- <span data-ttu-id="61d32-127">Web 服务器： Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="61d32-127">Web Server: Web Applications</span></span>
- <span data-ttu-id="61d32-128">SCCM 服务器： if 适用的 SCCM 集成报表</span><span class="sxs-lookup"><span data-stu-id="61d32-128">SCCM Server: SCCM Integrated Reports if applicable</span></span>
- <span data-ttu-id="61d32-129">客户端： MBAM 代理或客户端更新</span><span class="sxs-lookup"><span data-stu-id="61d32-129">Clients: MBAM Agent or Client Update</span></span>
- <span data-ttu-id="61d32-130">组策略模板：使用新模板更新现有组策略，并启用现有 MBAM 组策略上的新设置</span><span class="sxs-lookup"><span data-stu-id="61d32-130">Group Policy Templates: Update the existing Group Policy with new templates and enable new settings on existing MBAM Group Policy</span></span>

> [!NOTE]
> <span data-ttu-id="61d32-131">我们建议你先创建 MBAM 数据库的完整数据库备份，然后再运行升级。</span><span class="sxs-lookup"><span data-stu-id="61d32-131">We recommend that you create a full database backup of the MBAM databases before you run the upgrades.</span></span>

### <span data-ttu-id="61d32-132">升级 MBAM SQL Server</span><span class="sxs-lookup"><span data-stu-id="61d32-132">Upgrade the MBAM SQL Server</span></span>

<span data-ttu-id="61d32-133">观看此视频，了解如何升级 MBAM SQL Server：</span><span class="sxs-lookup"><span data-stu-id="61d32-133">Watch this video to learn how to upgrade the MBAM SQL Server:</span></span>

   > [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE3ALew]

### <span data-ttu-id="61d32-134">升级 MBAM Web 服务器</span><span class="sxs-lookup"><span data-stu-id="61d32-134">Upgrade the MBAM Web Server</span></span>

<span data-ttu-id="61d32-135">观看此视频，了解如何升级 MBAM Web 服务器：</span><span class="sxs-lookup"><span data-stu-id="61d32-135">Watch this video to learn how to upgrade the MBAM Web Server:</span></span>

   > [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE3ALex]

## <span data-ttu-id="61d32-136">详细信息</span><span class="sxs-lookup"><span data-stu-id="61d32-136">More information</span></span>

<span data-ttu-id="61d32-137">有关 MBAM 2.5 SP1 中已知问题的详细信息，请参阅[MBAM 2.5 SP1 的发行说明](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/release-notes-for-mbam-25-sp1)。</span><span class="sxs-lookup"><span data-stu-id="61d32-137">For more information about known issues in MBAM 2.5 SP1, see [Release Notes for MBAM 2.5 SP1](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/release-notes-for-mbam-25-sp1).</span></span>
