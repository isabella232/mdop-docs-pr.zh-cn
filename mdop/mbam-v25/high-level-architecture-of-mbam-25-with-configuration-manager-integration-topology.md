---
title: 采用 Configuration Manager 集成拓扑的 MBAM 2.5 的高级别体系结构
description: 采用 Configuration Manager 集成拓扑的 MBAM 2.5 的高级别体系结构
author: dansimp
ms.assetid: 075bafa1-792b-4c24-9d8e-5d3153e2112c
ms.reviewer: ''
manager: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/23/2018
ms.author: dansimp
ms.openlocfilehash: 75af2e22981d76568916c36acadbbb25648b1f1d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803833"
---
# <span data-ttu-id="49b2d-103">具有 Configuration Manager 集成拓扑的 MBAM 2.5 的高级别体系结构</span><span class="sxs-lookup"><span data-stu-id="49b2d-103">High-level architecture of MBAM 2.5 with Configuration Manager Integration topology</span></span>

<span data-ttu-id="49b2d-104">本主题介绍了使用 Configuration Manager 集成拓扑部署 Microsoft BitLocker 管理和监视（MBAM）的推荐体系结构。</span><span class="sxs-lookup"><span data-stu-id="49b2d-104">This topic describes the recommended architecture for deploying Microsoft BitLocker Administration and Monitoring (MBAM) with the Configuration Manager Integration topology.</span></span> <span data-ttu-id="49b2d-105">此拓扑将 MBAM 与 System Center Configuration Manager 集成。</span><span class="sxs-lookup"><span data-stu-id="49b2d-105">This topology integrates MBAM with System Center Configuration Manager.</span></span> <span data-ttu-id="49b2d-106">若要使用独立拓扑部署 MBAM，请参阅[使用独立拓扑的 MBAM 2.5 的高级别体系结构](high-level-architecture-of-mbam-25-with-stand-alone-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="49b2d-106">To deploy MBAM with the Stand-alone topology, see [High-Level Architecture of MBAM 2.5 with Stand-alone Topology](high-level-architecture-of-mbam-25-with-stand-alone-topology.md).</span></span>

<span data-ttu-id="49b2d-107">有关本主题中所述软件的受支持版本的列表，请参阅[MBAM 2.5 支持的配置](mbam-25-supported-configurations.md)。</span><span class="sxs-lookup"><span data-stu-id="49b2d-107">For a list of the supported versions of the software mentioned in this topic, see [MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md).</span></span>

<span data-ttu-id="49b2d-108">**重要提示** 使用 Configuration Manager 2007 时，Configuration Manager 集成拓扑安装不支持 Windows To Go。</span><span class="sxs-lookup"><span data-stu-id="49b2d-108">**Important** Windows To Go is not supported for the Configuration Manager Integration topology installation when you are using Configuration Manager 2007.</span></span>

 

## <span data-ttu-id="49b2d-109">推荐的服务器数和受支持的客户端数</span><span class="sxs-lookup"><span data-stu-id="49b2d-109">Recommended number of servers and supported number of clients</span></span>


<span data-ttu-id="49b2d-110">生产环境中推荐的服务器数和受支持的客户端数量如下所示：</span><span class="sxs-lookup"><span data-stu-id="49b2d-110">The recommended number of servers and supported number of clients in a production environment is as follows:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="49b2d-111">推荐的体系结构</span><span class="sxs-lookup"><span data-stu-id="49b2d-111">Recommended architecture</span></span></th>
<th align="left"><span data-ttu-id="49b2d-112">详细信息</span><span class="sxs-lookup"><span data-stu-id="49b2d-112">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="49b2d-113">服务器和其他计算机的数量</span><span class="sxs-lookup"><span data-stu-id="49b2d-113">Number of servers and other computers</span></span></p></td>
<td align="left"><p><span data-ttu-id="49b2d-114">三台服务器</span><span class="sxs-lookup"><span data-stu-id="49b2d-114">Three servers</span></span></p>
<p><span data-ttu-id="49b2d-115">一个工作站</span><span class="sxs-lookup"><span data-stu-id="49b2d-115">One workstation</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="49b2d-116">支持的客户端计算机数</span><span class="sxs-lookup"><span data-stu-id="49b2d-116">Number of client computers supported</span></span></p></td>
<td align="left"><p><span data-ttu-id="49b2d-117">500,000</span><span class="sxs-lookup"><span data-stu-id="49b2d-117">500,000</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="49b2d-118">Configuration Manager 集成和独立拓扑之间的差异</span><span class="sxs-lookup"><span data-stu-id="49b2d-118">Differences between Configuration Manager Integration and stand-alone topologies</span></span>


<span data-ttu-id="49b2d-119">拓扑的主要区别如下：</span><span class="sxs-lookup"><span data-stu-id="49b2d-119">The main differences between the topologies are:</span></span>

-   <span data-ttu-id="49b2d-120">将从 MBAM 中删除合规性和报告功能，并从配置管理器访问。</span><span class="sxs-lookup"><span data-stu-id="49b2d-120">The compliance and reporting features are removed from MBAM and are accessed from Configuration Manager.</span></span>

-   <span data-ttu-id="49b2d-121">从 Configuration Manager 管理控制台查看报表，除了恢复审核报告之外，还可从 MBAM 管理和监视网站继续查看。</span><span class="sxs-lookup"><span data-stu-id="49b2d-121">Reports are viewed from the Configuration Manager Management Console, with the exception of the Recovery Audit Report, which you continue to view from the MBAM Administration and Monitoring Website.</span></span>

## <span data-ttu-id="49b2d-122">使用 Configuration Manager 集成拓扑推荐的 MBAM 高级别体系结构</span><span class="sxs-lookup"><span data-stu-id="49b2d-122">Recommended MBAM high-level architecture with the Configuration Manager Integration topology</span></span>


<span data-ttu-id="49b2d-123">下图和表介绍了 MBAM 与 Configuration Manager 集成拓扑的推荐高级别体系结构。</span><span class="sxs-lookup"><span data-stu-id="49b2d-123">The following diagram and table describe the recommended high-level architecture for MBAM with the Configuration Manager Integration topology.</span></span> <span data-ttu-id="49b2d-124">MBAM 多林部署需要单向或双向信任。</span><span class="sxs-lookup"><span data-stu-id="49b2d-124">MBAM multi-forest deployments require a one-way or two-way trust.</span></span> <span data-ttu-id="49b2d-125">单向信任要求服务器域信任客户端域。</span><span class="sxs-lookup"><span data-stu-id="49b2d-125">One-way trusts require that the server domain trusts the client domain.</span></span>

![mbam2\-5](images/mbam2-5-cmserver.png)

### <span data-ttu-id="49b2d-127">数据库服务器</span><span class="sxs-lookup"><span data-stu-id="49b2d-127">Database server</span></span>

#### <span data-ttu-id="49b2d-128">恢复数据库</span><span class="sxs-lookup"><span data-stu-id="49b2d-128">Recovery database</span></span>

<span data-ttu-id="49b2d-129">此功能在运行 Windows Server 和支持的 SQL Server 实例的计算机上配置。</span><span class="sxs-lookup"><span data-stu-id="49b2d-129">This feature is configured on a computer running Windows Server and supported SQL Server instance.</span></span>

<span data-ttu-id="49b2d-130">**恢复数据库**存储从 MBAM 客户端计算机收集的恢复数据。</span><span class="sxs-lookup"><span data-stu-id="49b2d-130">The **Recovery Database** stores recovery data that is collected from MBAM Client computers.</span></span>

#### <span data-ttu-id="49b2d-131">审核数据库</span><span class="sxs-lookup"><span data-stu-id="49b2d-131">Audit database</span></span>

<span data-ttu-id="49b2d-132">此功能在运行 Windows Server 和支持的 SQL Server 实例的计算机上配置。</span><span class="sxs-lookup"><span data-stu-id="49b2d-132">This feature is configured on a computer running Windows Server and supported SQL Server instance.</span></span>

<span data-ttu-id="49b2d-133">**审核数据库**存储从已访问恢复数据的客户端计算机收集的审核活动数据。</span><span class="sxs-lookup"><span data-stu-id="49b2d-133">The **Audit Database** stores audit activity data that is collected from client computers that have accessed recovery data.</span></span>

#### <span data-ttu-id="49b2d-134">报告</span><span class="sxs-lookup"><span data-stu-id="49b2d-134">Reports</span></span>

<span data-ttu-id="49b2d-135">此功能在运行 Windows Server 和支持的 SQL Server 实例的计算机上配置。</span><span class="sxs-lookup"><span data-stu-id="49b2d-135">This feature is configured on a computer running Windows Server and supported SQL Server instance.</span></span>

<span data-ttu-id="49b2d-136">**报告**为企业中的客户端计算机提供恢复审核数据。</span><span class="sxs-lookup"><span data-stu-id="49b2d-136">The **Reports** provide recovery audit data for the client computers in your enterprise.</span></span> <span data-ttu-id="49b2d-137">你可以从 Configuration Manager 控制台或直接从 SQL Server Reporting Services 查看报表。</span><span class="sxs-lookup"><span data-stu-id="49b2d-137">You can view reports from the Configuration Manager console or directly from SQL Server Reporting Services.</span></span>

### <span data-ttu-id="49b2d-138">Configuration Manager 主站点服务器</span><span class="sxs-lookup"><span data-stu-id="49b2d-138">Configuration Manager primary site server</span></span>

<span data-ttu-id="49b2d-139">System Center Configuration Manager 集成功能</span><span class="sxs-lookup"><span data-stu-id="49b2d-139">System Center Configuration Manager Integration feature</span></span>

-   <span data-ttu-id="49b2d-140">此功能在 Configuration Manager 主站点服务器（配置管理器基础结构中的顶层服务器）上配置。</span><span class="sxs-lookup"><span data-stu-id="49b2d-140">This feature is configured on the Configuration Manager Primary Site Server, which is the top-tier server in your Configuration Manager infrastructure.</span></span>

-   <span data-ttu-id="49b2d-141">**Configuration Manager 服务器**从客户端计算机收集硬件清单信息，并用于报告客户端计算机的 BitLocker 合规性。</span><span class="sxs-lookup"><span data-stu-id="49b2d-141">The **Configuration Manager Server** collects the hardware inventory information from client computers and is used to report BitLocker compliance of client computers.</span></span>

-   <span data-ttu-id="49b2d-142">当运行 Microsoft BitLocker 管理和监视设置向导安装服务器软件时，配置管理器主站点服务器上配置了 MBAM 支持的计算机集合、配置基线和报告。</span><span class="sxs-lookup"><span data-stu-id="49b2d-142">When you run the Microsoft BitLocker Administration and Monitoring Setup wizard to install the server software, the MBAM Supported Computers collection, configuration baseline, and reports are configured on the Configuration Manager Primary Site Server.</span></span>

-   <span data-ttu-id="49b2d-143">**Configuration Manager 控制台**必须安装在安装了 MBAM Server 软件的同一计算机上。</span><span class="sxs-lookup"><span data-stu-id="49b2d-143">The **Configuration Manager console** must be installed on the same computer on which you install the MBAM Server software.</span></span>

### <span data-ttu-id="49b2d-144">管理和监视服务器</span><span class="sxs-lookup"><span data-stu-id="49b2d-144">Administration and monitoring server</span></span>

#### <span data-ttu-id="49b2d-145">管理和监视网站</span><span class="sxs-lookup"><span data-stu-id="49b2d-145">Administration and monitoring website</span></span>

<span data-ttu-id="49b2d-146">此功能在运行 Windows Server 的计算机上配置。</span><span class="sxs-lookup"><span data-stu-id="49b2d-146">This feature is configured on a computer running Windows Server.</span></span>

<span data-ttu-id="49b2d-147">**管理和监视网站**用于：</span><span class="sxs-lookup"><span data-stu-id="49b2d-147">The **Administration and monitoring website** is used to:</span></span>

-   <span data-ttu-id="49b2d-148">当用户被锁定时，帮助最终用户重新获得对其计算机的访问权限。（此网站区域通常称为 "帮助桌面"。）</span><span class="sxs-lookup"><span data-stu-id="49b2d-148">Help end users regain access to their computers when they are locked out. (This area of the Website is commonly called the Help Desk.)</span></span>

-   <span data-ttu-id="49b2d-149">查看恢复审核报告，该报告显示客户端计算机的恢复活动。</span><span class="sxs-lookup"><span data-stu-id="49b2d-149">View the Recovery Audit Report, which shows recovery activity for client computers.</span></span> <span data-ttu-id="49b2d-150">从 Configuration Manager 控制台查看其他报告。</span><span class="sxs-lookup"><span data-stu-id="49b2d-150">Other reports are viewed from the Configuration Manager console.</span></span>

#### <span data-ttu-id="49b2d-151">自助服务门户</span><span class="sxs-lookup"><span data-stu-id="49b2d-151">Self-service portal</span></span>

<span data-ttu-id="49b2d-152">此功能在运行 Windows Server 的计算机上配置。</span><span class="sxs-lookup"><span data-stu-id="49b2d-152">This feature is configured on a computer running Windows Server.</span></span>

<span data-ttu-id="49b2d-153">**自助服务门户**是一种网站，使客户端计算机上的最终用户能够独立登录到网站以获取恢复密钥（如果他们丢失或忘记其 BitLocker 密码）。</span><span class="sxs-lookup"><span data-stu-id="49b2d-153">The **Self-Service Portal** is a website that enables end users on client computers to independently log on to a website to get a recovery key if they lose or forget their BitLocker password.</span></span>

#### <span data-ttu-id="49b2d-154">监视此网站的 web 服务</span><span class="sxs-lookup"><span data-stu-id="49b2d-154">Monitoring web services for this website</span></span>

<span data-ttu-id="49b2d-155">此功能安装在运行 Windows Server 的计算机上。</span><span class="sxs-lookup"><span data-stu-id="49b2d-155">This feature is installed on a computer running Windows Server.</span></span>

<span data-ttu-id="49b2d-156">**监视 web 服务**由 MBAM 客户端和网站用于与数据库通信。</span><span class="sxs-lookup"><span data-stu-id="49b2d-156">The **monitoring web services** are used by the MBAM Client and the websites to communicate to the database.</span></span>

**<span data-ttu-id="49b2d-157">重要提示</span><span class="sxs-lookup"><span data-stu-id="49b2d-157">Important</span></span>**<br><span data-ttu-id="49b2d-158">由于 MBAM 网站直接与恢复数据库通信，因此在 Microsoft BitLocker 管理和监视（MBAM） 2.5 SP1 中不再提供监视 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="49b2d-158">The Monitoring Web Service is no longer available in Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 SP1 since the MBAM websites communicate directly with the Recovery Database.</span></span> 

 

### <span data-ttu-id="49b2d-159">管理工作站</span><span class="sxs-lookup"><span data-stu-id="49b2d-159">Management workstation</span></span>

#### <span data-ttu-id="49b2d-160">MBAM 组策略模板</span><span class="sxs-lookup"><span data-stu-id="49b2d-160">MBAM group policy templates</span></span>

-   <span data-ttu-id="49b2d-161">**MBAM 组策略模板**是定义 MBAM 的实现设置的组策略设置，使你能够管理 BitLocker 驱动器加密。</span><span class="sxs-lookup"><span data-stu-id="49b2d-161">The **MBAM Group Policy Templates** are Group Policy settings that define implementation settings for MBAM, which enable you to manage BitLocker drive encryption.</span></span>

-   <span data-ttu-id="49b2d-162">在运行 MBAM 之前，你必须从[如何获取 MDOP 组策略（admx）模板](https://go.microsoft.com/fwlink/p/?LinkId=393941)中下载组策略模板，并将其复制到运行受支持的 Windows Server 或 Windows 操作系统的服务器或工作站。</span><span class="sxs-lookup"><span data-stu-id="49b2d-162">Before you run MBAM, you must download the Group Policy Templates from [How to Get MDOP Group Policy (.admx) Templates](https://go.microsoft.com/fwlink/p/?LinkId=393941) and copy them to a server or workstation that is running a supported Windows Server or Windows operating system.</span></span>

    **<span data-ttu-id="49b2d-163">注意</span><span class="sxs-lookup"><span data-stu-id="49b2d-163">NOTE</span></span>**<br><span data-ttu-id="49b2d-164">工作站不必是专用计算机。</span><span class="sxs-lookup"><span data-stu-id="49b2d-164">The workstation does not have to be a dedicated computer.</span></span>

     

### <span data-ttu-id="49b2d-165">MBAM 客户端和 Configuration Manager 客户端计算机</span><span class="sxs-lookup"><span data-stu-id="49b2d-165">MBAM Client and Configuration Manager Client computer</span></span>

#### <span data-ttu-id="49b2d-166">MBAM 客户端软件</span><span class="sxs-lookup"><span data-stu-id="49b2d-166">MBAM Client software</span></span>

<span data-ttu-id="49b2d-167">**MBAM 客户端**：</span><span class="sxs-lookup"><span data-stu-id="49b2d-167">The **MBAM Client**:</span></span>

-   <span data-ttu-id="49b2d-168">使用组策略对象对企业中的客户端计算机强制执行 BitLocker 驱动器加密。</span><span class="sxs-lookup"><span data-stu-id="49b2d-168">Uses Group Policy Objects to enforce BitLocker drive encryption on client computers in the enterprise.</span></span>

-   <span data-ttu-id="49b2d-169">收集三种数据驱动器类型的 BitLocker 恢复密钥：操作系统驱动器、固定数据驱动器和可移动（USB）数据驱动器。</span><span class="sxs-lookup"><span data-stu-id="49b2d-169">Collects the BitLocker recovery key for three data drive types: operating system drives, fixed data drives, and removable (USB) data drives.</span></span>

-   <span data-ttu-id="49b2d-170">收集有关客户端计算机的恢复信息和计算机信息。</span><span class="sxs-lookup"><span data-stu-id="49b2d-170">Collects recovery information and computer information about the client computers.</span></span>

#### <span data-ttu-id="49b2d-171">Configuration Manager 客户端</span><span class="sxs-lookup"><span data-stu-id="49b2d-171">Configuration Manager Client</span></span>

<span data-ttu-id="49b2d-172">**Configuration Manager 客户端**使 configuration manager 能够收集有关客户端计算机的硬件兼容性数据和报告合规性信息。</span><span class="sxs-lookup"><span data-stu-id="49b2d-172">The **Configuration Manager Client** enables Configuration Manager to collect hardware compatibility data about the client computers and report compliance information.</span></span>

 

## <span data-ttu-id="49b2d-173">支持的 Configuration Manager 版本的 MBAM 部署中的差异</span><span class="sxs-lookup"><span data-stu-id="49b2d-173">Differences in MBAM deployment for supported Configuration Manager versions</span></span>


<span data-ttu-id="49b2d-174">使用 Configuration Manager 集成拓扑部署 MBAM 时，可以在主站点服务器上安装 MBAM。</span><span class="sxs-lookup"><span data-stu-id="49b2d-174">When you deploy MBAM with the Configuration Manager Integration topology, you can install MBAM on a primary site server.</span></span> <span data-ttu-id="49b2d-175">但是，对于 System Center2012 Configuration Manager 和配置 Manager2007，MBAM 安装的运行方式有所不同。</span><span class="sxs-lookup"><span data-stu-id="49b2d-175">However, the MBAM installation works differently for System Center2012 Configuration Manager and Configuration Manager2007.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="49b2d-176">Configuration Manager 版本</span><span class="sxs-lookup"><span data-stu-id="49b2d-176">Configuration Manager version</span></span></th>
<th align="left"><span data-ttu-id="49b2d-177">描述</span><span class="sxs-lookup"><span data-stu-id="49b2d-177">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="49b2d-178">System Center2012 R2 配置管理器</span><span class="sxs-lookup"><span data-stu-id="49b2d-178">System Center2012 R2 Configuration Manager</span></span></p>
<p><span data-ttu-id="49b2d-179">System Center2012 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="49b2d-179">System Center2012 Configuration Manager</span></span></p></td>
<td align="left"><p><span data-ttu-id="49b2d-180">如果在主站点服务器或中央管理服务器上安装 MBAM，MBAM 将执行该站点服务器上的所有安装操作。</span><span class="sxs-lookup"><span data-stu-id="49b2d-180">If you install MBAM on a primary site server or on a central administration server, MBAM performs all of the installation actions on that site server.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="49b2d-181">配置 Manager2007 R2</span><span class="sxs-lookup"><span data-stu-id="49b2d-181">Configuration Manager2007 R2</span></span></p>
<p><span data-ttu-id="49b2d-182">配置 Manager2007</span><span class="sxs-lookup"><span data-stu-id="49b2d-182">Configuration Manager2007</span></span></p></td>
<td align="left"><p><span data-ttu-id="49b2d-183">如果在具有中央站点父服务器的大型 Configuration Manager 层次结构的一部分的主站点服务器上安装 MBAM，MBAM 将标识中心网站父服务器并执行该父服务器上的所有安装操作。</span><span class="sxs-lookup"><span data-stu-id="49b2d-183">If you install MBAM on a primary site server that is part of a larger Configuration Manager hierarchy with a central site parent server, MBAM identifies the central site parent server and performs all of the installation actions on that parent server.</span></span> <span data-ttu-id="49b2d-184">安装包括检查先决条件以及安装 Configuration Manager 对象和报告。</span><span class="sxs-lookup"><span data-stu-id="49b2d-184">The installation includes checking prerequisites and installing the Configuration Manager objects and reports.</span></span></p>
<p><span data-ttu-id="49b2d-185">例如，如果在作为中心站点父服务器的子站点的主站点服务器上安装 MBAM，则 MBAM 将在父服务器上安装所有 Configuration Manager 对象和报告。</span><span class="sxs-lookup"><span data-stu-id="49b2d-185">For example, if you install MBAM on a primary site server that is a child of a central site parent server, MBAM installs all of the Configuration Manager objects and reports on the parent server.</span></span> <span data-ttu-id="49b2d-186">如果在父服务器上安装 MBAM，MBAM 将在该父服务器上执行所有安装操作。</span><span class="sxs-lookup"><span data-stu-id="49b2d-186">If you install MBAM on the parent server, MBAM performs all of the installation actions on that parent server.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="49b2d-187">MBAM 如何与 Configuration Manager 配合使用</span><span class="sxs-lookup"><span data-stu-id="49b2d-187">How MBAM works with Configuration Manager</span></span>


<span data-ttu-id="49b2d-188">与 Configuration Manager 的 MBAM 集成基于安装下表中所述项目的配置包。</span><span class="sxs-lookup"><span data-stu-id="49b2d-188">The integration of MBAM with Configuration Manager is based on a configuration pack that installs the items described in the following table.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="49b2d-189">安装到 Configuration Manager 的项目</span><span class="sxs-lookup"><span data-stu-id="49b2d-189">Items installed into Configuration Manager</span></span></th>
<th align="left"><span data-ttu-id="49b2d-190">描述</span><span class="sxs-lookup"><span data-stu-id="49b2d-190">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="49b2d-191">配置数据</span><span class="sxs-lookup"><span data-stu-id="49b2d-191">Configuration data</span></span></p></td>
<td align="left"><p><span data-ttu-id="49b2d-192">配置数据将安装名为 "BitLocker 保护" 的配置基线，其中包含两个配置项目：</span><span class="sxs-lookup"><span data-stu-id="49b2d-192">The configuration data installs a configuration baseline, called “BitLocker Protection,” which contains two configuration items:</span></span></p>
<ul>
<li><p><span data-ttu-id="49b2d-193">BitLocker 操作系统驱动器保护</span><span class="sxs-lookup"><span data-stu-id="49b2d-193">BitLocker Operating System Drive Protection</span></span></p></li>
<li><p><span data-ttu-id="49b2d-194">BitLocker 固定数据驱动器保护</span><span class="sxs-lookup"><span data-stu-id="49b2d-194">BitLocker Fixed Data Drives Protection</span></span></p></li>
</ul>
<p><span data-ttu-id="49b2d-195">配置基线将部署到 "MBAM 支持的计算机" 集合，该集合也是在安装 MBAM 时创建的。</span><span class="sxs-lookup"><span data-stu-id="49b2d-195">The configuration baseline is deployed to the MBAM Supported Computers collection, which is also created when MBAM is installed.</span></span></p>
<p><span data-ttu-id="49b2d-196">这两个配置项目提供评估客户端计算机合规性状态的基础。</span><span class="sxs-lookup"><span data-stu-id="49b2d-196">The two configuration items provide the basis for evaluating the compliance status of the client computers.</span></span> <span data-ttu-id="49b2d-197">在 Configuration Manager 中捕获、存储和评估此信息。</span><span class="sxs-lookup"><span data-stu-id="49b2d-197">This information is captured, stored, and evaluated in Configuration Manager.</span></span></p>
<p><span data-ttu-id="49b2d-198">配置项目基于操作系统驱动器和固定数据驱动器的合规性要求。</span><span class="sxs-lookup"><span data-stu-id="49b2d-198">The configuration items are based on the compliance requirements for operating system drives and fixed data drives.</span></span> <span data-ttu-id="49b2d-199">收集已部署计算机所需的详细信息，以便可以评估这些驱动器类型的合规性。</span><span class="sxs-lookup"><span data-stu-id="49b2d-199">The required details for the deployed computers are collected so that the compliance for those drive types can be evaluated.</span></span></p>
<p><span data-ttu-id="49b2d-200">默认情况下，配置基线会评估合规性状态 every12 小时，并将合规性数据发送到 Configuration Manager。</span><span class="sxs-lookup"><span data-stu-id="49b2d-200">By default, the configuration baseline evaluates the compliance status every12 hours and sends the compliance data to Configuration Manager.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="49b2d-201">MBAM 支持的计算机集合</span><span class="sxs-lookup"><span data-stu-id="49b2d-201">MBAM Supported Computers collection</span></span></p></td>
<td align="left"><p><span data-ttu-id="49b2d-202">MBAM 将创建一个名为 MBAM 支持的计算机的集合。</span><span class="sxs-lookup"><span data-stu-id="49b2d-202">MBAM creates a collection that is called MBAM Supported Computers.</span></span> <span data-ttu-id="49b2d-203">配置基线针对此集合中的客户端计算机。</span><span class="sxs-lookup"><span data-stu-id="49b2d-203">The configuration baseline is targeted to client computers that are in this collection.</span></span></p>
<p><span data-ttu-id="49b2d-204">这是一个动态集合。</span><span class="sxs-lookup"><span data-stu-id="49b2d-204">This is a dynamic collection.</span></span> <span data-ttu-id="49b2d-205">默认情况下，它根据以下三个条件运行 every12 小时并评估成员身份：</span><span class="sxs-lookup"><span data-stu-id="49b2d-205">By default, it runs every12 hours and evaluates membership, based on three criteria:</span></span></p>
<ul>
<li><p><span data-ttu-id="49b2d-206">计算机是受支持的 Windows 操作系统版本。</span><span class="sxs-lookup"><span data-stu-id="49b2d-206">The computer is a supported version of the Windows operating system.</span></span></p></li>
<li><p><span data-ttu-id="49b2d-207">计算机是物理计算机。</span><span class="sxs-lookup"><span data-stu-id="49b2d-207">The computer is a physical computer.</span></span> <span data-ttu-id="49b2d-208">不支持虚拟机。</span><span class="sxs-lookup"><span data-stu-id="49b2d-208">Virtual machines are not supported.</span></span></p></li>
<li><p><span data-ttu-id="49b2d-209">计算机具有可用的受信任的平台模块（TPM）。</span><span class="sxs-lookup"><span data-stu-id="49b2d-209">The computer has a Trusted Platform Module (TPM) that is available.</span></span> <span data-ttu-id="49b2d-210">Windows7 需要有兼容版本的 TPM 1.2 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="49b2d-210">A compatible version of TPM1.2 or later is required for Windows7.</span></span> <span data-ttu-id="49b2d-211">Windows10、Windows 8.1、Windows8 和 Windows To Go 不需要 TPM。</span><span class="sxs-lookup"><span data-stu-id="49b2d-211">Windows10, Windows8.1, Windows8, and Windows To Go do not require a TPM.</span></span></p></li>
</ul>
<p><span data-ttu-id="49b2d-212">将为所有计算机计算集合，并创建兼容计算机的子集，这将为 MBAM 集成提供合规性评估和报告的基础。</span><span class="sxs-lookup"><span data-stu-id="49b2d-212">The collection is evaluated against all computers and a subset of compatible computers is created, which provides the basis for compliance evaluation and reporting for the MBAM integration.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="49b2d-213">报告</span><span class="sxs-lookup"><span data-stu-id="49b2d-213">Reports</span></span></p></td>
<td align="left"><p><span data-ttu-id="49b2d-214">通过 Configuration Manager 集成拓扑配置 MBAM 时，你可以在 "配置管理器" 中查看除 "恢复审核" 报表之外的所有报表，后者是你继续在 MBAM 管理和监视网站中查看的。</span><span class="sxs-lookup"><span data-stu-id="49b2d-214">When you configure MBAM with the Configuration Manager Integration topology, you view all reports in Configuration Manager, except the Recovery Audit Report, the latter of which you continue to view in the MBAM Administration and Monitoring Website.</span></span> <span data-ttu-id="49b2d-215">配置管理器中可用的报表有：</span><span class="sxs-lookup"><span data-stu-id="49b2d-215">The reports available in Configuration Manager are:</span></span></p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="49b2d-216">报告</span><span class="sxs-lookup"><span data-stu-id="49b2d-216">Report</span></span></th>
<th align="left"><span data-ttu-id="49b2d-217">描述</span><span class="sxs-lookup"><span data-stu-id="49b2d-217">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="49b2d-218">BitLocker 企业合规性仪表板</span><span class="sxs-lookup"><span data-stu-id="49b2d-218">BitLocker Enterprise Compliance Dashboard</span></span></p></td>
<td align="left"><p><span data-ttu-id="49b2d-219">向 IT 管理员提供单个报告中的三个信息视图：合规性状态分发、不合规性-错误分发以及合规性状态按驱动器类型分发。</span><span class="sxs-lookup"><span data-stu-id="49b2d-219">Gives IT administrators three views of information in a single report: Compliance Status Distribution, Non Compliant – Errors Distribution, and Compliance Status Distribution By Drive Type.</span></span> <span data-ttu-id="49b2d-220">报表上的向下钻取选项让 IT 管理员可以单击浏览数据并查看与选定状态匹配的计算机列表。</span><span class="sxs-lookup"><span data-stu-id="49b2d-220">Drill-down options on the report let IT administrators click through the data and view a list of computers that match the selected state.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="49b2d-221">BitLocker 企业合规性详细信息</span><span class="sxs-lookup"><span data-stu-id="49b2d-221">BitLocker Enterprise Compliance Details</span></span></p></td>
<td align="left"><p><span data-ttu-id="49b2d-222">允许 IT 管理员查看有关企业的 BitLocker 加密合规性状态的信息，包括每台计算机的合规性状态。</span><span class="sxs-lookup"><span data-stu-id="49b2d-222">Lets IT administrators view information about the BitLocker encryption compliance status of the enterprise and includes the compliance status for each computer.</span></span> <span data-ttu-id="49b2d-223">报表上的向下钻取选项让 IT 管理员可以单击浏览数据并查看与选定状态匹配的计算机列表。</span><span class="sxs-lookup"><span data-stu-id="49b2d-223">Drill-down options on the report let IT administrators click through the data and view a list of computers that match the selected state.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="49b2d-224">BitLocker 计算机合规性</span><span class="sxs-lookup"><span data-stu-id="49b2d-224">BitLocker Computer Compliance</span></span></p></td>
<td align="left"><p><span data-ttu-id="49b2d-225">允许 IT 管理员查看单个计算机并确定报告其状态为 "合规" 或 "不合规" 的原因。</span><span class="sxs-lookup"><span data-stu-id="49b2d-225">Lets IT administrators view an individual computer and determine why it was reported with a status of compliant or not compliant.</span></span> <span data-ttu-id="49b2d-226">该报告还显示操作系统驱动器和固定数据驱动器的加密状态。</span><span class="sxs-lookup"><span data-stu-id="49b2d-226">The report also displays the encryption state of the operating system drives and fixed data drives.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="49b2d-227">BitLocker 企业合规性摘要</span><span class="sxs-lookup"><span data-stu-id="49b2d-227">BitLocker Enterprise Compliance Summary</span></span></p></td>
<td align="left"><p><span data-ttu-id="49b2d-228">允许 IT 管理员查看企业中 MBAM 策略合规性的状态。</span><span class="sxs-lookup"><span data-stu-id="49b2d-228">Lets IT administrators view the status of MBAM policy compliance in the enterprise.</span></span> <span data-ttu-id="49b2d-229">评估每台计算机的省/市/自治区，并且报告将显示企业中所有计算机针对策略的合规性摘要。</span><span class="sxs-lookup"><span data-stu-id="49b2d-229">Each computer’s state is evaluated, and the report shows a summary of the compliance of all computers in the enterprise against the policy.</span></span> <span data-ttu-id="49b2d-230">报表上的向下钻取选项让 IT 管理员可以单击浏览数据并查看与选定状态匹配的计算机列表。</span><span class="sxs-lookup"><span data-stu-id="49b2d-230">Drill-down options on the report let IT administrators click through the data and view a list of computers that match the selected state.</span></span></p></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
</tbody>
</table>

 


## <span data-ttu-id="49b2d-231">相关主题</span><span class="sxs-lookup"><span data-stu-id="49b2d-231">Related topics</span></span>


[<span data-ttu-id="49b2d-232">MBAM 2.5 入门</span><span class="sxs-lookup"><span data-stu-id="49b2d-232">Getting Started with MBAM 2.5</span></span>](getting-started-with-mbam-25.md)

[<span data-ttu-id="49b2d-233">采用独立拓扑的 MBAM 2.5 的高级别体系结构</span><span class="sxs-lookup"><span data-stu-id="49b2d-233">High-Level Architecture of MBAM 2.5 with Stand-alone Topology</span></span>](high-level-architecture-of-mbam-25-with-stand-alone-topology.md)

[<span data-ttu-id="49b2d-234">图示 MBAM 2.5 部署的功能</span><span class="sxs-lookup"><span data-stu-id="49b2d-234">Illustrated Features of an MBAM 2.5 Deployment</span></span>](illustrated-features-of-an-mbam-25-deployment.md)

 

 
## <span data-ttu-id="49b2d-235">已获得 MBAM 的建议？</span><span class="sxs-lookup"><span data-stu-id="49b2d-235">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="49b2d-236">在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="49b2d-236">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="49b2d-237">对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="49b2d-237">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>




