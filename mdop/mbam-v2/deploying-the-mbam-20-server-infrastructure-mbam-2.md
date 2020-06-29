---
title: 部署 MBAM 2.0 服务器基础结构
description: 部署 MBAM 2.0 服务器基础结构
author: dansimp
ms.assetid: 52e68d94-e2b4-4b06-ae55-f900ea6cc59f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 22a69fe8f6853c02a818bb026b36771cd09632f0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803632"
---
# <span data-ttu-id="272fb-103">部署 MBAM 2.0 服务器基础结构</span><span class="sxs-lookup"><span data-stu-id="272fb-103">Deploying the MBAM 2.0 Server Infrastructure</span></span>


<span data-ttu-id="272fb-104">适用于独立拓扑的 Microsoft BitLocker 管理和监视（MBAM）服务器功能可以在生产环境中的两个或多个服务器上以不同的配置进行安装。</span><span class="sxs-lookup"><span data-stu-id="272fb-104">Microsoft BitLocker Administration and Monitoring (MBAM) Server features for the Stand-alone topology can be installed in different configurations on two or more servers in a production environment.</span></span> <span data-ttu-id="272fb-105">对于生产环境，建议的配置是两台服务器，具体取决于你的可伸缩性要求。</span><span class="sxs-lookup"><span data-stu-id="272fb-105">The recommended configuration is two servers for a production environment, depending on your scalability requirements.</span></span> <span data-ttu-id="272fb-106">仅在测试环境中使用单个服务器进行 MBAM 安装。</span><span class="sxs-lookup"><span data-stu-id="272fb-106">Use a single server for an MBAM installation only in test environments.</span></span> <span data-ttu-id="272fb-107">有关规划 MBAM Server 功能部署的详细信息，请参阅[规划2.0 服务器部署](planning-for-mbam-20-server-deployment-mbam-2.md)。</span><span class="sxs-lookup"><span data-stu-id="272fb-107">For more information about planning for the MBAM Server feature deployment, see [Planning for MBAM 2.0 Server Deployment](planning-for-mbam-20-server-deployment-mbam-2.md).</span></span>

<span data-ttu-id="272fb-108">下图显示了如何配置建议的两服务器 MBAM 部署的示例。</span><span class="sxs-lookup"><span data-stu-id="272fb-108">The following diagram shows an example of how you can configure the recommended two-server MBAM deployment.</span></span> <span data-ttu-id="272fb-109">此配置在生产环境中最多支持 200000 MBAM 客户端。</span><span class="sxs-lookup"><span data-stu-id="272fb-109">This configuration supports up to 200,000 MBAM clients in a production environment.</span></span> <span data-ttu-id="272fb-110">体系结构映像中的服务器功能和数据库将在下一节中介绍，并且在建议您安装它们的计算机或服务器下列出。</span><span class="sxs-lookup"><span data-stu-id="272fb-110">The server features and databases in the architecture image are described in the following section and are listed under the computer or server where we recommend that you install them.</span></span>

![mbam 2 2-服务器部署拓扑](images/mbam2-3-servers.gif)

## <span data-ttu-id="272fb-112">管理和监视服务器</span><span class="sxs-lookup"><span data-stu-id="272fb-112">Administration and Monitoring Server</span></span>


<span data-ttu-id="272fb-113">此服务器上安装了以下功能：</span><span class="sxs-lookup"><span data-stu-id="272fb-113">The following features are installed on this server:</span></span>

-   <span data-ttu-id="272fb-114">**管理和监视服务器**。</span><span class="sxs-lookup"><span data-stu-id="272fb-114">**Administration and Monitoring Server**.</span></span> <span data-ttu-id="272fb-115">"管理和监视服务器" 功能安装在 Windows 服务器上，由技术支持网站和监视 web 服务组成。</span><span class="sxs-lookup"><span data-stu-id="272fb-115">The Administration and Monitoring Server feature is installed on a Windows server and consists of the Help Desk website and the monitoring web services.</span></span>

-   <span data-ttu-id="272fb-116">**自助服务门户**。</span><span class="sxs-lookup"><span data-stu-id="272fb-116">**Self-Service Portal**.</span></span> <span data-ttu-id="272fb-117">自助服务门户已安装在 Windows 服务器上。</span><span class="sxs-lookup"><span data-stu-id="272fb-117">The Self-Service Portal is installed on a Windows server.</span></span> <span data-ttu-id="272fb-118">自助服务门户使客户端计算机上的最终用户能够独立登录到网站，在那里，他们可以获取恢复密钥以恢复已锁定的 BitLocker 卷。</span><span class="sxs-lookup"><span data-stu-id="272fb-118">The Self-Service Portal enables end users on client computers to independently log on to a website, where they can obtain a recovery key to recover a locked BitLocker volume.</span></span>

## <span data-ttu-id="272fb-119">数据库服务器</span><span class="sxs-lookup"><span data-stu-id="272fb-119">Database Server</span></span>


<span data-ttu-id="272fb-120">此服务器上安装了以下功能：</span><span class="sxs-lookup"><span data-stu-id="272fb-120">The following features are installed on this server:</span></span>

-   <span data-ttu-id="272fb-121">**恢复数据库**。</span><span class="sxs-lookup"><span data-stu-id="272fb-121">**Recovery Database**.</span></span> <span data-ttu-id="272fb-122">恢复数据库安装在 Windows server 和受支持的 Microsoft SQLServer 实例中。</span><span class="sxs-lookup"><span data-stu-id="272fb-122">The Recovery Database is installed on a Windows server and a supported instance of Microsoft SQLServer.</span></span> <span data-ttu-id="272fb-123">此数据库存储从 MBAM 客户端计算机收集的恢复数据。</span><span class="sxs-lookup"><span data-stu-id="272fb-123">This database stores recovery data that is collected from MBAM client computers.</span></span>

-   <span data-ttu-id="272fb-124">**合规性和审核数据库**。</span><span class="sxs-lookup"><span data-stu-id="272fb-124">**Compliance and Audit Database**.</span></span> <span data-ttu-id="272fb-125">合规性和审核数据库安装在 Windows server 和支持的 SQLServer 实例上。</span><span class="sxs-lookup"><span data-stu-id="272fb-125">The Compliance and Audit Database is installed on a Windows server and a supported instance of SQLServer.</span></span> <span data-ttu-id="272fb-126">此数据库存储 MBAM 客户端计算机的合规性数据。</span><span class="sxs-lookup"><span data-stu-id="272fb-126">This database stores compliance data for MBAM client computers.</span></span> <span data-ttu-id="272fb-127">此数据主要用于 SQL Server Reporting Services （SSRS）主机的报表。</span><span class="sxs-lookup"><span data-stu-id="272fb-127">This data is used primarily for reports that SQL Server Reporting Services (SSRS) hosts.</span></span>

-   <span data-ttu-id="272fb-128">**合规性和审核报告**。</span><span class="sxs-lookup"><span data-stu-id="272fb-128">**Compliance and Audit Reports**.</span></span> <span data-ttu-id="272fb-129">合规性和审核报告安装在 Windows server 和支持 SQL Server Reporting Services （SSRS）功能的 SQLServer 实例中。</span><span class="sxs-lookup"><span data-stu-id="272fb-129">The Compliance and Audit Reports are installed on a Windows server and a supported instance of SQLServer that has the SQL Server Reporting Services (SSRS) feature installed.</span></span> <span data-ttu-id="272fb-130">这些报表提供可从技术支持网站或直接从 SSRS 服务器访问的 MBAM 报表。</span><span class="sxs-lookup"><span data-stu-id="272fb-130">These reports provide MBAM reports that you can access from the Help Desk website or directly from the SSRS server.</span></span>

## <span data-ttu-id="272fb-131">管理工作站</span><span class="sxs-lookup"><span data-stu-id="272fb-131">Management Workstation</span></span>


<span data-ttu-id="272fb-132">以下功能安装在管理工作站上，后者可以是 Windows 服务器或客户端计算机。</span><span class="sxs-lookup"><span data-stu-id="272fb-132">The following feature is installed on the Management Workstation, which can be a Windows server or a client computer.</span></span>

-   <span data-ttu-id="272fb-133">**策略模板**。</span><span class="sxs-lookup"><span data-stu-id="272fb-133">**Policy Template**.</span></span> <span data-ttu-id="272fb-134">策略模板包含定义用于 BitLocker 驱动器加密的 MBAM 实现设置的组策略。</span><span class="sxs-lookup"><span data-stu-id="272fb-134">The Policy Template consists of Group Policies that define MBAM implementation settings for BitLocker drive encryption.</span></span> <span data-ttu-id="272fb-135">你可以在任何服务器或工作站上安装策略模板，但它通常安装在管理工作站上，后者是受支持的 Windows server 或客户端计算机。</span><span class="sxs-lookup"><span data-stu-id="272fb-135">You can install the Policy template on any server or workstation, but it is commonly installed on a management workstation, which is a supported Windows server or client computer.</span></span> <span data-ttu-id="272fb-136">工作站不必是专用计算机。</span><span class="sxs-lookup"><span data-stu-id="272fb-136">The workstation does not have to be a dedicated computer.</span></span>

## <a href="" id="---------mbam-client"></a> <span data-ttu-id="272fb-137">MBAM 客户端</span><span class="sxs-lookup"><span data-stu-id="272fb-137">MBAM Client</span></span>


<span data-ttu-id="272fb-138">MBAM 客户端安装在 Windows 计算机上，具有以下特征：</span><span class="sxs-lookup"><span data-stu-id="272fb-138">The MBAM Client is installed on a Windows computer and has the following characteristics:</span></span>

-   <span data-ttu-id="272fb-139">使用组策略强制对企业中的客户端计算机进行 BitLocker 驱动器加密。</span><span class="sxs-lookup"><span data-stu-id="272fb-139">Uses Group Policy to enforce the BitLocker drive encryption of client computers in the enterprise.</span></span>

-   <span data-ttu-id="272fb-140">收集三个 BitLocker 数据驱动器类型的恢复密钥：操作系统驱动器、固定数据驱动器和可移动数据（USB）驱动器。</span><span class="sxs-lookup"><span data-stu-id="272fb-140">Collects the recovery key for the three BitLocker data drive types: operating system drives, fixed data drives, and removable data (USB) drives.</span></span>

-   <span data-ttu-id="272fb-141">收集计算机的合规性数据并将数据传递到报告系统。</span><span class="sxs-lookup"><span data-stu-id="272fb-141">Collects compliance data for the computer and passes the data to the reporting system.</span></span>

## <span data-ttu-id="272fb-142">用于部署 MBAM 2.0 服务器功能的其他资源</span><span class="sxs-lookup"><span data-stu-id="272fb-142">Other Resources for Deploying MBAM 2.0 Server Features</span></span>


[<span data-ttu-id="272fb-143">部署 MBAM 2.0</span><span class="sxs-lookup"><span data-stu-id="272fb-143">Deploying MBAM 2.0</span></span>](deploying-mbam-20-mbam-2.md)

 

 





