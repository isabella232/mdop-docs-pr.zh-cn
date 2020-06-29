---
title: 入门 - 结合使用 MBAM 和 Configuration Manager
description: 入门 - 结合使用 MBAM 和 Configuration Manager
author: dansimp
ms.assetid: b0a1d3cc-0b01-4b69-a2cd-fd09fb3beda4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 654de38918102a41395efe37dc593ce8f49113e4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803714"
---
# <span data-ttu-id="2e4bf-103">入门 - 结合使用 MBAM 和 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="2e4bf-103">Getting Started - Using MBAM with Configuration Manager</span></span>


<span data-ttu-id="2e4bf-104">安装 Microsoft BitLocker 管理和监视（MBAM）时，你可以选择将 MBAM 与 Configuration Manager 2007 或 SystemCenter2012 ConfigurationManager 集成的拓扑。</span><span class="sxs-lookup"><span data-stu-id="2e4bf-104">When you install Microsoft BitLocker Administration and Monitoring (MBAM), you can choose a topology that integrates MBAM with Configuration Manager 2007 or SystemCenter2012 ConfigurationManager.</span></span> <span data-ttu-id="2e4bf-105">有关 MBAM 支持的 Configuration Manager 的受支持版本的列表，请参阅[计划使用 Configuration Manager 部署 MBAM](planning-to-deploy-mbam-with-configuration-manager-2.md)。</span><span class="sxs-lookup"><span data-stu-id="2e4bf-105">For a list of the supported versions of Configuration Manager that MBAM supports, see [Planning to Deploy MBAM with Configuration Manager](planning-to-deploy-mbam-with-configuration-manager-2.md).</span></span> <span data-ttu-id="2e4bf-106">在集成拓扑中，将从 MBAM 中删除硬件合规性和报告功能，并从配置管理器访问。</span><span class="sxs-lookup"><span data-stu-id="2e4bf-106">In the integrated topology, the hardware compliance and reporting features are removed from MBAM and are accessed from Configuration Manager.</span></span>

<span data-ttu-id="2e4bf-107">**重要提示** 将 MBAM 的集成拓扑安装到 Configuration Manager 2007 时，不支持 Windows To Go。</span><span class="sxs-lookup"><span data-stu-id="2e4bf-107">**Important** Windows To Go is not supported when you install the integrated topology of MBAM with Configuration Manager 2007.</span></span>

 

## <span data-ttu-id="2e4bf-108">结合使用 MBAM 和 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="2e4bf-108">Using MBAM with Configuration Manager</span></span>


<span data-ttu-id="2e4bf-109">MBAM 的集成基于将以下三项安装到 Configuration Manager 2007 或 SystemCenter2012 ConfigurationManager 的新配置包，这些内容将在以下部分中详细介绍：</span><span class="sxs-lookup"><span data-stu-id="2e4bf-109">The integration of MBAM is based on a new Configuration Pack that installs the following three items into Configuration Manager 2007 or SystemCenter2012 ConfigurationManager, which are described in detail in the following sections:</span></span>

<span data-ttu-id="2e4bf-110">包含配置项目和配置基线的配置数据</span><span class="sxs-lookup"><span data-stu-id="2e4bf-110">Configuration data that consists of configuration items and a configuration baseline</span></span>

<span data-ttu-id="2e4bf-111">集合</span><span class="sxs-lookup"><span data-stu-id="2e4bf-111">Collection</span></span>

<span data-ttu-id="2e4bf-112">报告</span><span class="sxs-lookup"><span data-stu-id="2e4bf-112">Reports</span></span>

### <span data-ttu-id="2e4bf-113">配置数据</span><span class="sxs-lookup"><span data-stu-id="2e4bf-113">Configuration Data</span></span>

<span data-ttu-id="2e4bf-114">配置数据将安装名为 "BitLocker 保护" 的配置基线，其中包含两个配置项目： "BitLocker 操作系统驱动器保护" 和 "BitLocker 固定数据驱动器保护"。</span><span class="sxs-lookup"><span data-stu-id="2e4bf-114">The configuration data installs a configuration baseline, called “BitLocker Protection,” which contains two configuration items: “BitLocker Operating System Drive Protection” and “BitLocker Fixed Data Drives Protection.”</span></span> <span data-ttu-id="2e4bf-115">配置基线将部署到集合，该集合也会在安装 MBAM 时创建。</span><span class="sxs-lookup"><span data-stu-id="2e4bf-115">The configuration baseline is deployed to the collection, which is also created when MBAM is installed.</span></span> <span data-ttu-id="2e4bf-116">这两个配置项目提供评估客户端计算机合规性状态的基础。</span><span class="sxs-lookup"><span data-stu-id="2e4bf-116">The two configuration items provide the basis for evaluating the compliance status of the client computers.</span></span> <span data-ttu-id="2e4bf-117">在 Configuration Manager 中捕获、存储和评估此信息。</span><span class="sxs-lookup"><span data-stu-id="2e4bf-117">This information is captured, stored, and evaluated in Configuration Manager.</span></span> <span data-ttu-id="2e4bf-118">配置项目基于操作系统驱动器（OSDs）和固定数据驱动器（FDDs）的符合性要求。</span><span class="sxs-lookup"><span data-stu-id="2e4bf-118">The configuration items are based on the compliance requirements for operating system drives (OSDs) and Fixed Data Drives (FDDs).</span></span> <span data-ttu-id="2e4bf-119">收集已部署计算机所需的详细信息，以便可以评估这些驱动器类型的合规性。</span><span class="sxs-lookup"><span data-stu-id="2e4bf-119">The required details for the deployed computers are collected so that the compliance for those drive types can be evaluated.</span></span> <span data-ttu-id="2e4bf-120">默认情况下，配置基线每隔12小时评估合规性状态，并将合规性数据发送到配置管理器。</span><span class="sxs-lookup"><span data-stu-id="2e4bf-120">By default, the configuration baseline evaluates the compliance status every 12 hours and sends the compliance data to Configuration Manager.</span></span>

### <span data-ttu-id="2e4bf-121">集合</span><span class="sxs-lookup"><span data-stu-id="2e4bf-121">Collection</span></span>

<span data-ttu-id="2e4bf-122">MBAM 将创建一个名为 MBAM 支持的计算机的集合。</span><span class="sxs-lookup"><span data-stu-id="2e4bf-122">MBAM creates a collection that is called MBAM Supported Computers.</span></span> <span data-ttu-id="2e4bf-123">配置基线针对此集合中的客户端计算机。</span><span class="sxs-lookup"><span data-stu-id="2e4bf-123">The configuration baseline is targeted to client computers that are in this collection.</span></span> <span data-ttu-id="2e4bf-124">这是一个动态集合，默认情况下，每12小时运行一次，并评估成员资格。</span><span class="sxs-lookup"><span data-stu-id="2e4bf-124">This is a dynamic collection that, by default, runs every 12 hours and evaluates membership.</span></span> <span data-ttu-id="2e4bf-125">成员身份基于三个条件：</span><span class="sxs-lookup"><span data-stu-id="2e4bf-125">Membership is based on three criteria:</span></span>

-   <span data-ttu-id="2e4bf-126">它是受支持的 Windows 操作系统版本。</span><span class="sxs-lookup"><span data-stu-id="2e4bf-126">It is a supported version of the Windows operating system.</span></span> <span data-ttu-id="2e4bf-127">目前，MBAM 在 windows 8 企业版上运行时，仅支持 Windows 7 企业版和 Windows 7 旗舰版、Windows 8 企业版和 Windows To Go。</span><span class="sxs-lookup"><span data-stu-id="2e4bf-127">Currently, MBAM supports only Windows 7 Enterprise and Windows 7 Ultimate, Windows 8 Enterprise, and Windows To Go, when Windows To Go is running on Windows 8 Enterprise.</span></span>

-   <span data-ttu-id="2e4bf-128">它是一台物理计算机。</span><span class="sxs-lookup"><span data-stu-id="2e4bf-128">It is a physical computer.</span></span> <span data-ttu-id="2e4bf-129">不支持虚拟机。</span><span class="sxs-lookup"><span data-stu-id="2e4bf-129">Virtual machines are not supported.</span></span>

-   <span data-ttu-id="2e4bf-130">受信任的平台模块（TPM）可用。</span><span class="sxs-lookup"><span data-stu-id="2e4bf-130">Trusted Platform Module (TPM) is available.</span></span> <span data-ttu-id="2e4bf-131">Windows 7 需要使用兼容版本的 TPM 1.2 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="2e4bf-131">A compatible version of TPM 1.2 or later is required for Windows 7.</span></span> <span data-ttu-id="2e4bf-132">Windows 8 和 Windows To Go 不需要 TPM。</span><span class="sxs-lookup"><span data-stu-id="2e4bf-132">Windows 8 and Windows To Go do not require a TPM.</span></span>

<span data-ttu-id="2e4bf-133">该集合针对所有计算机进行评估，并创建兼容计算机的子集，这些计算机为 MBAM 集成提供了合规性评估和报告的基础。</span><span class="sxs-lookup"><span data-stu-id="2e4bf-133">The collection is evaluated against all computers and creates the subset of compatible computers that provides the basis for compliance evaluation and reporting for the MBAM integration.</span></span>

### <span data-ttu-id="2e4bf-134">报告</span><span class="sxs-lookup"><span data-stu-id="2e4bf-134">Reports</span></span>

<span data-ttu-id="2e4bf-135">你可以使用四个报表来查看合规性。</span><span class="sxs-lookup"><span data-stu-id="2e4bf-135">There are four reports that you can use to view compliance.</span></span> <span data-ttu-id="2e4bf-136">它们是：</span><span class="sxs-lookup"><span data-stu-id="2e4bf-136">They are:</span></span>

-   <span data-ttu-id="2e4bf-137">**BitLocker 企业合规性仪表板**-为 IT 管理员提供单个报告上的三种不同的信息视图：合规性状态分发、不合规性-错误分发以及合规性状态按驱动器类型分发。</span><span class="sxs-lookup"><span data-stu-id="2e4bf-137">**BitLocker Enterprise Compliance Dashboard** – gives IT administrators three different views of information on a single report: Compliance Status Distribution, Non Compliant – Errors Distribution, and Compliance Status Distribution By Drive Type.</span></span> <span data-ttu-id="2e4bf-138">报表上的向下钻取选项让 IT 管理员可以单击浏览数据并查看与所选状态相匹配的计算机列表。</span><span class="sxs-lookup"><span data-stu-id="2e4bf-138">Drill-down options on the report let IT administrators click through the data and view a list of computers that match the state that you select.</span></span>

-   <span data-ttu-id="2e4bf-139">**BitLocker 企业合规性详细信息**-允许 IT 管理员查看有关企业的 BitLocker 加密合规性状态的信息，包括每台计算机的合规性状态。</span><span class="sxs-lookup"><span data-stu-id="2e4bf-139">**BitLocker Enterprise Compliance Details** – lets IT administrators view information about the BitLocker encryption compliance status of the enterprise and includes the compliance status for each computer.</span></span> <span data-ttu-id="2e4bf-140">报表上的向下钻取选项让 IT 管理员可以单击浏览数据并查看与所选状态相匹配的计算机列表。</span><span class="sxs-lookup"><span data-stu-id="2e4bf-140">Drill-down options on the report let IT administrators click through the data and view a list of computers that match the state that you select.</span></span>

-   <span data-ttu-id="2e4bf-141">**BitLocker 计算机合规性**-允许 IT 管理员查看单个计算机，并确定报告其给定状态符合或不合规的原因。</span><span class="sxs-lookup"><span data-stu-id="2e4bf-141">**BitLocker Computer Compliance** – lets IT administrators view an individual computer and determine why it was reported with a given status of compliant or not compliant.</span></span> <span data-ttu-id="2e4bf-142">该报告还显示操作系统驱动器（OSD）和固定数据驱动器（FDDs）的加密状态。</span><span class="sxs-lookup"><span data-stu-id="2e4bf-142">The report also displays the encryption state of the operating system drives (OSD) and fixed data drives (FDDs).</span></span>

-   <span data-ttu-id="2e4bf-143">**BitLocker 企业合规性摘要**-允许 IT 管理员通过 MBAM 策略查看企业合规性的状态。</span><span class="sxs-lookup"><span data-stu-id="2e4bf-143">**BitLocker Enterprise Compliance Summary** – lets IT administrators view the status of the compliance of the enterprise with MBAM policy.</span></span> <span data-ttu-id="2e4bf-144">评估每台计算机的省/市/自治区，并且报告将显示企业中所有计算机针对策略的合规性摘要。</span><span class="sxs-lookup"><span data-stu-id="2e4bf-144">Each computer’s state is evaluated, and the report shows a summary of the compliance of all computers in the enterprise against the policy.</span></span> <span data-ttu-id="2e4bf-145">报表上的向下钻取选项让 IT 管理员可以单击浏览数据并查看与所选状态相匹配的计算机列表。</span><span class="sxs-lookup"><span data-stu-id="2e4bf-145">Drill-down options on the report let IT administrators click through the data and view a list of computers that match the state that you select.</span></span>

## <span data-ttu-id="2e4bf-146">具有 Configuration Manager 的 MBAM 的高级别体系结构</span><span class="sxs-lookup"><span data-stu-id="2e4bf-146">High-Level Architecture of MBAM with Configuration Manager</span></span>


<span data-ttu-id="2e4bf-147">下图显示了具有配置管理器拓扑的 MBAM 体系结构。</span><span class="sxs-lookup"><span data-stu-id="2e4bf-147">The following image shows the MBAM architecture with the Configuration Manager topology.</span></span> <span data-ttu-id="2e4bf-148">此配置在生产环境中最多支持 200000 MBAM 客户端。</span><span class="sxs-lookup"><span data-stu-id="2e4bf-148">This configuration supports up to 200,000 MBAM clients in a production environment.</span></span>

![具有 configuration manager 的 mbam 体系结构](images/mbam2-cmserver.gif)

<span data-ttu-id="2e4bf-150">以下是对此体系结构的服务器、数据库和功能的描述。</span><span class="sxs-lookup"><span data-stu-id="2e4bf-150">A description of the servers, databases, and features of this architecture follows.</span></span> <span data-ttu-id="2e4bf-151">体系结构图像中的服务器功能和数据库在建议您安装它们的计算机或服务器下列出。</span><span class="sxs-lookup"><span data-stu-id="2e4bf-151">The server features and databases in the architecture image are listed under the computer or server where we recommend that you install them.</span></span>

-   <span data-ttu-id="2e4bf-152">**数据库服务器**-**恢复数据库**、**审核数据库**和**审核报告**安装在 Windows 服务器上并支持 SQLServer 实例。</span><span class="sxs-lookup"><span data-stu-id="2e4bf-152">**Database Server** – The **Recovery Database**, **Audit Database**, and **Audit Reports** are installed on a Windows server and supported SQLServer instance.</span></span> <span data-ttu-id="2e4bf-153">恢复数据库存储从 MBAM 客户端计算机收集的恢复数据。</span><span class="sxs-lookup"><span data-stu-id="2e4bf-153">The Recovery database stores recovery data that is collected from MBAM client computers.</span></span> <span data-ttu-id="2e4bf-154">审核数据库存储从已访问恢复数据的客户端计算机收集的审核活动数据。</span><span class="sxs-lookup"><span data-stu-id="2e4bf-154">The Audit Database stores audit activity data that is collected from client computers that have accessed recovery data.</span></span> <span data-ttu-id="2e4bf-155">审核报告提供有关您的企业中客户端计算机的合规性状态的数据。</span><span class="sxs-lookup"><span data-stu-id="2e4bf-155">The Audit Reports provide data about the compliance status of client computers in your enterprise.</span></span>

-   <span data-ttu-id="2e4bf-156">**Configuration Manager 主站点服务器**-配置管理器服务器包含具有 System Center Configuration Manager 集成拓扑的 MBAM 服务器安装（必须在 Configuration Manager 主站点服务器上安装）。</span><span class="sxs-lookup"><span data-stu-id="2e4bf-156">**Configuration Manager Primary Site Server** – The Configuration Manager Server contains of the MBAM server installation with the System Center Configuration Manager Integration topology, which must be installed on a Configuration Manager primary site server.</span></span> <span data-ttu-id="2e4bf-157">Configuration Manager 服务器从客户端计算机收集硬件清单信息，并用于报告客户端计算机的 BitLocker 合规性。</span><span class="sxs-lookup"><span data-stu-id="2e4bf-157">The Configuration Manager Server collects the hardware inventory information from client computers and is used to report BitLocker compliance of client computers.</span></span> <span data-ttu-id="2e4bf-158">运行 MBAM 安装服务器安装时，将在 Configuration Manager 主站点服务器上安装一个集合和配置数据。</span><span class="sxs-lookup"><span data-stu-id="2e4bf-158">When you run the MBAM Setup server installation, a collection and the configuration data are installed on the Configuration Manager Primary Site Server.</span></span>

-   <span data-ttu-id="2e4bf-159">**管理和监视服务器**-**管理和监视服务器**安装在 Windows 服务器上，包括管理和监视网站以及监视 web 服务。</span><span class="sxs-lookup"><span data-stu-id="2e4bf-159">**Administration and Monitoring Server** - The **Administration and Monitoring Server** is installed on a Windows server and consists of the Administration and Monitoring website and the monitoring web services.</span></span> <span data-ttu-id="2e4bf-160">管理和监视网站用于审核活动和访问恢复数据（例如，BitLocker 恢复密钥）。</span><span class="sxs-lookup"><span data-stu-id="2e4bf-160">The Administration and Monitoring website is used to audit activity and to access recovery data (for example, BitLocker recovery keys).</span></span> <span data-ttu-id="2e4bf-161">**自助服务门户**也安装在管理和监视服务器上。</span><span class="sxs-lookup"><span data-stu-id="2e4bf-161">The **Self-Service Portal** is also installed on the Administration and Monitoring Server.</span></span> <span data-ttu-id="2e4bf-162">门户使客户端计算机上的最终用户能够独立登录到网站，以便在丢失或忘记其 BitLocker 密码时获取恢复密钥。</span><span class="sxs-lookup"><span data-stu-id="2e4bf-162">The Portal enables end users on client computers to independently log onto a website to get a recovery key if they lose or forget their BitLocker password.</span></span> <span data-ttu-id="2e4bf-163">审核报告还安装在管理和监视服务器上。</span><span class="sxs-lookup"><span data-stu-id="2e4bf-163">The Audit reports are also installed on the Administration and Monitoring Server.</span></span>

-   <span data-ttu-id="2e4bf-164">**管理工作站**-**策略模板**包含定义用于 BITLOCKER 驱动器加密的 MBAM 实现设置的组策略对象。</span><span class="sxs-lookup"><span data-stu-id="2e4bf-164">**Management Workstation** - The **Policy Template** consists of Group Policy Objects that define MBAM implementation settings for BitLocker drive encryption.</span></span> <span data-ttu-id="2e4bf-165">你可以在任何服务器或工作站上安装策略模板，但它通常安装在受支持的 Windows server 或客户端计算机的管理工作站上。</span><span class="sxs-lookup"><span data-stu-id="2e4bf-165">You can install the Policy template on any server or workstation, but it is commonly installed on a management workstation that is a supported Windows server or client computer.</span></span> <span data-ttu-id="2e4bf-166">工作站不必是专用计算机。</span><span class="sxs-lookup"><span data-stu-id="2e4bf-166">The workstation does not have to be a dedicated computer.</span></span>

-   <span data-ttu-id="2e4bf-167">**MBAM 客户端**和**Configuration Manager 客户端**计算机</span><span class="sxs-lookup"><span data-stu-id="2e4bf-167">**MBAM Client** and **Configuration Manager Client** computer</span></span>

    -   <span data-ttu-id="2e4bf-168">**MBAM 客户端**执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="2e4bf-168">The **MBAM Client** performs the following tasks:</span></span>

        -   <span data-ttu-id="2e4bf-169">使用组策略对象对企业中的客户端计算机强制执行 BitLocker 加密。</span><span class="sxs-lookup"><span data-stu-id="2e4bf-169">Uses Group Policy Objects to enforce the BitLocker encryption of client computers in the enterprise.</span></span>

        -   <span data-ttu-id="2e4bf-170">收集三个 BitLocker 数据驱动器类型的恢复密钥：操作系统驱动器、固定数据驱动器和可移动数据（USB）驱动器。</span><span class="sxs-lookup"><span data-stu-id="2e4bf-170">Collects the recovery key for the three BitLocker data drive types: operating system drives, fixed data drives, and removable data (USB) drives.</span></span>

        -   <span data-ttu-id="2e4bf-171">收集有关客户端计算机的恢复信息和计算机信息。</span><span class="sxs-lookup"><span data-stu-id="2e4bf-171">Collects recovery information and computer information about the client computers.</span></span>

    -   <span data-ttu-id="2e4bf-172">**Configuration Manager 客户端**-配置管理器客户端使 configuration manager 能够收集有关客户端计算机的硬件兼容性数据，并使 configuration manager 能够报告合规性信息。</span><span class="sxs-lookup"><span data-stu-id="2e4bf-172">**Configuration Manager Client** – The Configuration Manager client enables Configuration Manager to collect hardware compatibility data about the client computers, and enables Configuration Manager to report compliance information.</span></span>

## <span data-ttu-id="2e4bf-173">相关主题</span><span class="sxs-lookup"><span data-stu-id="2e4bf-173">Related topics</span></span>


[<span data-ttu-id="2e4bf-174">结合使用 MBAM 和 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="2e4bf-174">Using MBAM with Configuration Manager</span></span>](using-mbam-with-configuration-manager.md)

 

 





