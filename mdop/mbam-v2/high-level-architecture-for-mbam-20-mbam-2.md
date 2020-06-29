---
title: MBAM 2.0 的高级别体系结构
description: MBAM 2.0 的高级别体系结构
author: dansimp
ms.assetid: 7f73dd3a-0b1f-4af6-a2f0-d0c5bc5d183a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ddc061a1aec5141548c2d2141be38f8501d2244d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803621"
---
# <span data-ttu-id="12a17-103">MBAM 2.0 的高级别体系结构</span><span class="sxs-lookup"><span data-stu-id="12a17-103">High-Level Architecture for MBAM 2.0</span></span>


<span data-ttu-id="12a17-104">Microsoft BitLocker 管理和监视（MBAM）是一种客户端/服务器解决方案，可帮助你简化 BitLocker 预配和部署、改进 BitLocker 的合规性和报告，并减少支持费用。</span><span class="sxs-lookup"><span data-stu-id="12a17-104">Microsoft BitLocker Administration and Monitoring (MBAM) is a client/server solution that can help you simplify BitLocker provisioning and deployment, improve compliance and reporting on BitLocker, and reduce support costs.</span></span> <span data-ttu-id="12a17-105">Microsoft BitLocker 管理和监视包括本主题中所述的功能。</span><span class="sxs-lookup"><span data-stu-id="12a17-105">Microsoft BitLocker Administration and Monitoring includes the features that are described in this topic.</span></span>

<span data-ttu-id="12a17-106">Microsoft BitLocker 管理和监视可在独立拓扑中部署，或在与 Microsoft System Center Configuration Manager 2007 或 MicrosoftSystemCenter2012 ConfigurationManager 集成的拓扑中部署。</span><span class="sxs-lookup"><span data-stu-id="12a17-106">Microsoft BitLocker Administration and Monitoring can be deployed in the Stand-alone topology, or in a topology that is integrated with Microsoft System Center Configuration Manager 2007 or MicrosoftSystemCenter2012 ConfigurationManager.</span></span> <span data-ttu-id="12a17-107">本主题介绍独立拓扑的体系结构。</span><span class="sxs-lookup"><span data-stu-id="12a17-107">This topic describes the architecture for the Stand-alone topology.</span></span> <span data-ttu-id="12a17-108">有关在集成配置管理器拓扑中部署的信息，请参阅将[MBAM 与 Configuration Manager 结合使用](using-mbam-with-configuration-manager.md)。</span><span class="sxs-lookup"><span data-stu-id="12a17-108">For information about deploying in the integrated Configuration Manager topology, see [Using MBAM with Configuration Manager](using-mbam-with-configuration-manager.md).</span></span>

<span data-ttu-id="12a17-109">下图显示了生产环境的 MBAM 推荐体系结构，它由两台服务器和一个管理工作站组成。</span><span class="sxs-lookup"><span data-stu-id="12a17-109">The following diagram shows the MBAM recommended architecture for a production environment, which consists of two servers and a management workstation.</span></span> <span data-ttu-id="12a17-110">此体系结构支持最多 200000 MBAM 客户端。</span><span class="sxs-lookup"><span data-stu-id="12a17-110">This architecture supports up to 200,000 MBAM clients.</span></span> <span data-ttu-id="12a17-111">体系结构映像中的服务器功能和数据库将在下一节中介绍，并且在建议您安装它们的计算机或服务器下列出。</span><span class="sxs-lookup"><span data-stu-id="12a17-111">The server features and databases in the architecture image are described in the following section and are listed under the computer or server where we recommend that you install them.</span></span>

<span data-ttu-id="12a17-112">**注意** 单服务器体系结构应仅在测试环境中使用。</span><span class="sxs-lookup"><span data-stu-id="12a17-112">**Note** A single-server architecture should be used only in test environments.</span></span>

 

![mbam 2 2-服务器部署拓扑](images/mbam2-3-servers.gif)

## <span data-ttu-id="12a17-114">管理和监视服务器</span><span class="sxs-lookup"><span data-stu-id="12a17-114">Administration and Monitoring Server</span></span>


<span data-ttu-id="12a17-115">此服务器上安装了以下功能：</span><span class="sxs-lookup"><span data-stu-id="12a17-115">The following features are installed on this server:</span></span>

-   <span data-ttu-id="12a17-116">**管理和监视服务器**。</span><span class="sxs-lookup"><span data-stu-id="12a17-116">**Administration and Monitoring Server**.</span></span> <span data-ttu-id="12a17-117">"管理和监视服务器" 功能安装在 Windows 服务器上，包括 "管理和监视" 网站，其中包括报表和 "技术支持" 门户以及 "监视 web 服务"。</span><span class="sxs-lookup"><span data-stu-id="12a17-117">The Administration and Monitoring Server feature is installed on a Windows server and consists of the Administration and Monitoring website, which includes the reports and the Help Desk Portal, and the monitoring web services.</span></span>

-   <span data-ttu-id="12a17-118">**自助服务门户**。</span><span class="sxs-lookup"><span data-stu-id="12a17-118">**Self-Service Portal**.</span></span> <span data-ttu-id="12a17-119">自助服务门户已安装在 Windows 服务器上。</span><span class="sxs-lookup"><span data-stu-id="12a17-119">The Self-Service Portal is installed on a Windows server.</span></span> <span data-ttu-id="12a17-120">自助服务门户使客户端计算机上的最终用户能够独立登录到网站，在那里，他们可以获取恢复密钥以恢复已锁定的 BitLocker 卷。</span><span class="sxs-lookup"><span data-stu-id="12a17-120">The Self-Service Portal enables end users on client computers to independently log on to a website, where they can obtain a recovery key to recover a locked BitLocker volume.</span></span>

## <span data-ttu-id="12a17-121">数据库服务器</span><span class="sxs-lookup"><span data-stu-id="12a17-121">Database Server</span></span>


<span data-ttu-id="12a17-122">此服务器上安装了以下功能：</span><span class="sxs-lookup"><span data-stu-id="12a17-122">The following features are installed on this server:</span></span>

-   <span data-ttu-id="12a17-123">**恢复数据库**。</span><span class="sxs-lookup"><span data-stu-id="12a17-123">**Recovery Database**.</span></span> <span data-ttu-id="12a17-124">恢复数据库安装在 Windows server 和受支持的 Microsoft SQLServer 实例中。</span><span class="sxs-lookup"><span data-stu-id="12a17-124">The Recovery Database is installed on a Windows server and a supported instance of Microsoft SQLServer.</span></span> <span data-ttu-id="12a17-125">此数据库存储从 MBAM 客户端计算机收集的恢复数据。</span><span class="sxs-lookup"><span data-stu-id="12a17-125">This database stores recovery data that is collected from MBAM client computers.</span></span>

-   <span data-ttu-id="12a17-126">**合规性和审核数据库**。</span><span class="sxs-lookup"><span data-stu-id="12a17-126">**Compliance and Audit Database**.</span></span> <span data-ttu-id="12a17-127">合规性和审核数据库安装在 Windows server 和支持的 SQLServer 实例上。</span><span class="sxs-lookup"><span data-stu-id="12a17-127">The Compliance and Audit Database is installed on a Windows server and a supported instance of SQLServer.</span></span> <span data-ttu-id="12a17-128">此数据库存储 MBAM 客户端计算机的合规性数据。</span><span class="sxs-lookup"><span data-stu-id="12a17-128">This database stores compliance data for MBAM client computers.</span></span> <span data-ttu-id="12a17-129">此数据主要用于 SQL Server Reporting Services （SSRS）主机的报表。</span><span class="sxs-lookup"><span data-stu-id="12a17-129">This data is used primarily for reports that SQL Server Reporting Services (SSRS) hosts.</span></span>

-   <span data-ttu-id="12a17-130">**合规性和审核报告**。</span><span class="sxs-lookup"><span data-stu-id="12a17-130">**Compliance and Audit Reports**.</span></span> <span data-ttu-id="12a17-131">合规性和审核报告安装在 Windows server 和支持 SQL Server Reporting Services （SSRS）功能的 SQLServer 实例中。</span><span class="sxs-lookup"><span data-stu-id="12a17-131">The Compliance and Audit Reports are installed on a Windows server and a supported instance of SQLServer that has the SQL Server Reporting Services (SSRS) feature installed.</span></span> <span data-ttu-id="12a17-132">这些报表提供可从 "管理" 和 "监视" 网站或直接从 SSRS 服务器访问的 MBAM 报表。</span><span class="sxs-lookup"><span data-stu-id="12a17-132">These reports provide MBAM reports that you can access from the Administration and Monitoring website or directly from the SSRS server.</span></span>

## <span data-ttu-id="12a17-133">管理工作站</span><span class="sxs-lookup"><span data-stu-id="12a17-133">Management Workstation</span></span>


<span data-ttu-id="12a17-134">以下功能安装在管理工作站上，后者可以是 Windows 服务器或客户端计算机。</span><span class="sxs-lookup"><span data-stu-id="12a17-134">The following feature is installed on the Management workstation, which can be a Windows server or a client computer.</span></span>

-   <span data-ttu-id="12a17-135">**策略模板**。</span><span class="sxs-lookup"><span data-stu-id="12a17-135">**Policy Template**.</span></span> <span data-ttu-id="12a17-136">策略模板由定义用于 BitLocker 驱动器加密的 MBAM 实现设置的组策略设置组成。</span><span class="sxs-lookup"><span data-stu-id="12a17-136">The Policy Template consists of Group Policy settings that define MBAM implementation settings for BitLocker drive encryption.</span></span> <span data-ttu-id="12a17-137">你可以在任何服务器或工作站上安装策略模板，但它通常安装在管理工作站上，后者是受支持的 Windows server 或客户端计算机。</span><span class="sxs-lookup"><span data-stu-id="12a17-137">You can install the Policy template on any server or workstation, but it is commonly installed on a management workstation, which is a supported Windows server or client computer.</span></span> <span data-ttu-id="12a17-138">工作站不必是专用计算机。</span><span class="sxs-lookup"><span data-stu-id="12a17-138">The workstation does not have to be a dedicated computer.</span></span>

## <a href="" id="---------mbam-client"></a> <span data-ttu-id="12a17-139">MBAM 客户端</span><span class="sxs-lookup"><span data-stu-id="12a17-139">MBAM Client</span></span>


<span data-ttu-id="12a17-140">MBAM 客户端安装在 Windows 计算机上，具有以下特征：</span><span class="sxs-lookup"><span data-stu-id="12a17-140">The MBAM Client is installed on a Windows computer and has the following characteristics:</span></span>

-   <span data-ttu-id="12a17-141">使用组策略强制对企业中的客户端计算机进行 BitLocker 驱动器加密。</span><span class="sxs-lookup"><span data-stu-id="12a17-141">Uses Group Policy to enforce the BitLocker drive encryption of client computers in the enterprise.</span></span>

-   <span data-ttu-id="12a17-142">收集三个 BitLocker 数据驱动器类型的恢复密钥：操作系统驱动器、固定数据驱动器和可移动数据（USB）驱动器。</span><span class="sxs-lookup"><span data-stu-id="12a17-142">Collects the recovery key for the three BitLocker data drive types: operating system drives, fixed data drives, and removable data (USB) drives.</span></span>

-   <span data-ttu-id="12a17-143">收集计算机的合规性数据并将数据传递到报告系统。</span><span class="sxs-lookup"><span data-stu-id="12a17-143">Collects compliance data for the computer and passes the data to the reporting system.</span></span>

## <span data-ttu-id="12a17-144">相关主题</span><span class="sxs-lookup"><span data-stu-id="12a17-144">Related topics</span></span>


[<span data-ttu-id="12a17-145">MBAM 2.0 入门</span><span class="sxs-lookup"><span data-stu-id="12a17-145">Getting Started with MBAM 2.0</span></span>](getting-started-with-mbam-20-mbam-2.md)

 

 





