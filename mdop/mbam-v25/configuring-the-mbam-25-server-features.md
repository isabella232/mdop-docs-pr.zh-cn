---
title: 配置 MBAM 2.5 服务器功能
description: 配置 MBAM 2.5 服务器功能
author: dansimp
ms.assetid: 894d1080-5f13-48f7-8fde-82f8d440a4ed
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e6ba2fc49086acf698f61b9997505c8fa884c0eb
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803292"
---
# <span data-ttu-id="04ae6-103">配置 MBAM 2.5 服务器功能</span><span class="sxs-lookup"><span data-stu-id="04ae6-103">Configuring the MBAM 2.5 Server Features</span></span>


<span data-ttu-id="04ae6-104">在[安装 MBAM 2.5 服务器软件](installing-the-mbam-25-server-software.md)后，请使用此信息作为配置 Microsoft BitLocker 管理和监视（MBAM）2.5 服务器功能的起始位置。</span><span class="sxs-lookup"><span data-stu-id="04ae6-104">Use this information as a starting place for configuring Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 Server features after [Installing the MBAM 2.5 Server Software](installing-the-mbam-25-server-software.md).</span></span> <span data-ttu-id="04ae6-105">可使用两种方法配置 MBAM：</span><span class="sxs-lookup"><span data-stu-id="04ae6-105">There are two methods you can use to configure MBAM:</span></span>

-   <span data-ttu-id="04ae6-106">MBAM Server 配置向导</span><span class="sxs-lookup"><span data-stu-id="04ae6-106">MBAM Server Configuration wizard</span></span>

-   <span data-ttu-id="04ae6-107">Windows PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="04ae6-107">Windows PowerShell cmdlets</span></span>

## <span data-ttu-id="04ae6-108">在开始配置 MBAM 服务器功能之前</span><span class="sxs-lookup"><span data-stu-id="04ae6-108">Before you start configuring MBAM Server features</span></span>


<span data-ttu-id="04ae6-109">在开始配置 MBAM 服务器功能之前，请查看并完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="04ae6-109">Review and complete the following steps before you start configuring the MBAM Server features:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="04ae6-110">步骤</span><span class="sxs-lookup"><span data-stu-id="04ae6-110">Step</span></span></th>
<th align="left"><span data-ttu-id="04ae6-111">获取说明的位置</span><span class="sxs-lookup"><span data-stu-id="04ae6-111">Where to get instructions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="04ae6-112">查看建议的 MBAM 体系结构。</span><span class="sxs-lookup"><span data-stu-id="04ae6-112">Review the recommended architecture for MBAM.</span></span></p></td>
<td align="left"><p><a href="high-level-architecture-for-mbam-25.md" data-raw-source="[High-Level Architecture for MBAM 2.5](high-level-architecture-for-mbam-25.md)"><span data-ttu-id="04ae6-113">MBAM 2.5 的高级别体系结构</span><span class="sxs-lookup"><span data-stu-id="04ae6-113">High-Level Architecture for MBAM 2.5</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="04ae6-114">查看 MBAM 支持的配置。</span><span class="sxs-lookup"><span data-stu-id="04ae6-114">Review the supported configurations for MBAM.</span></span></p></td>
<td align="left"><p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)"><span data-ttu-id="04ae6-115">MBAM 2.5 支持的配置</span><span class="sxs-lookup"><span data-stu-id="04ae6-115">MBAM 2.5 Supported Configurations</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="04ae6-116">在每台服务器上完成所需的先决条件。</span><span class="sxs-lookup"><span data-stu-id="04ae6-116">Complete the required prerequisites on each server.</span></span></p></td>
<td align="left"><ul>
<li><p><a href="mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md" data-raw-source="[MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)"><span data-ttu-id="04ae6-117">独立和 Configuration Manager 集成拓扑的 MBAM 2.5 服务器先决条件</span><span class="sxs-lookup"><span data-stu-id="04ae6-117">MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies</span></span></a></p></li>
<li><p><a href="mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md" data-raw-source="[MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology](mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md)"><span data-ttu-id="04ae6-118">仅适用于 Configuration Manager 集成拓扑的 MBAM 2.5 服务器先决条件</span><span class="sxs-lookup"><span data-stu-id="04ae6-118">MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology</span></span></a></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="04ae6-119">在将在其中配置 MBAM 服务器功能的每台服务器上安装 MBAM 服务器软件。</span><span class="sxs-lookup"><span data-stu-id="04ae6-119">Install the MBAM Server software on each server where you will configure an MBAM Server feature.</span></span></p></td>
<td align="left"><p><a href="installing-the-mbam-25-server-software.md" data-raw-source="[Installing the MBAM 2.5 Server Software](installing-the-mbam-25-server-software.md)"><span data-ttu-id="04ae6-120">安装 MBAM 2.5 服务器软件</span><span class="sxs-lookup"><span data-stu-id="04ae6-120">Installing the MBAM 2.5 Server Software</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="04ae6-121">查看使用 Windows PowerShell 配置 MBAM 服务器功能的先决条件（如果你使用此方法配置 MBAM Server 功能）。</span><span class="sxs-lookup"><span data-stu-id="04ae6-121">Review the prerequisites for using Windows PowerShell to configure MBAM Server features (if you are using this method to configure MBAM Server features).</span></span></p></td>
<td align="left"><p><a href="configuring-mbam-25-server-features-by-using-windows-powershell.md" data-raw-source="[Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md)"><span data-ttu-id="04ae6-122">使用 Windows PowerShell 配置 MBAM 2.5 服务器功能</span><span class="sxs-lookup"><span data-stu-id="04ae6-122">Configuring MBAM 2.5 Server Features by Using Windows PowerShell</span></span></a></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="04ae6-123">配置 MBAM Server 功能的步骤</span><span class="sxs-lookup"><span data-stu-id="04ae6-123">Steps for configuring MBAM Server features</span></span>


<span data-ttu-id="04ae6-124">下表中的每一行描述了您将在单独的服务器上配置的功能，这些功能将根据[MBAM 2.5 的推荐高级别体系结构](high-level-architecture-for-mbam-25.md)进行配置。</span><span class="sxs-lookup"><span data-stu-id="04ae6-124">Each row in the following table describes the features that you will configure on a separate server, according to the recommended [High-Level Architecture for MBAM 2.5](high-level-architecture-for-mbam-25.md).</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="04ae6-125">要安装的功能</span><span class="sxs-lookup"><span data-stu-id="04ae6-125">Features to install</span></span></th>
<th align="left"><span data-ttu-id="04ae6-126">获取说明的位置</span><span class="sxs-lookup"><span data-stu-id="04ae6-126">Where to get instructions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="04ae6-127">配置数据库。</span><span class="sxs-lookup"><span data-stu-id="04ae6-127">Configure the databases.</span></span></p></td>
<td align="left"><p><a href="how-to-configure-the-mbam-25-databases.md" data-raw-source="[How to Configure the MBAM 2.5 Databases](how-to-configure-the-mbam-25-databases.md)"><span data-ttu-id="04ae6-128">如何配置 MBAM 2.5 数据库</span><span class="sxs-lookup"><span data-stu-id="04ae6-128">How to Configure the MBAM 2.5 Databases</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="04ae6-129">配置报告。</span><span class="sxs-lookup"><span data-stu-id="04ae6-129">Configure the reports.</span></span></p></td>
<td align="left"><p><a href="how-to-configure-the-mbam-25-reports.md" data-raw-source="[How to Configure the MBAM 2.5 Reports](how-to-configure-the-mbam-25-reports.md)"><span data-ttu-id="04ae6-130">如何配置 MBAM 2.5 报告</span><span class="sxs-lookup"><span data-stu-id="04ae6-130">How to Configure the MBAM 2.5 Reports</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="04ae6-131">配置 web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="04ae6-131">Configure the web applications.</span></span></p></td>
<td align="left"><p><a href="how-to-configure-the-mbam-25-web-applications.md" data-raw-source="[How to Configure the MBAM 2.5 Web Applications](how-to-configure-the-mbam-25-web-applications.md)"><span data-ttu-id="04ae6-132">如何配置 MBAM 2.5 Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="04ae6-132">How to Configure the MBAM 2.5 Web Applications</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="04ae6-133">配置 System Center Configuration Manager 集成（如果适用）。</span><span class="sxs-lookup"><span data-stu-id="04ae6-133">Configure the System Center Configuration Manager Integration (if applicable).</span></span></p></td>
<td align="left"><p><a href="how-to-configure-the-mbam-25-system-center-configuration-manager-integration.md" data-raw-source="[How to Configure the MBAM 2.5 System Center Configuration Manager Integration](how-to-configure-the-mbam-25-system-center-configuration-manager-integration.md)"><span data-ttu-id="04ae6-134">如何配置 MBAM 2.5 System Center Configuration Manager 集成</span><span class="sxs-lookup"><span data-stu-id="04ae6-134">How to Configure the MBAM 2.5 System Center Configuration Manager Integration</span></span></a></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="04ae6-135">有关 MBAM 服务器功能配置的事件的列表，请参阅[服务器事件日志](server-event-logs.md)。</span><span class="sxs-lookup"><span data-stu-id="04ae6-135">For a list of events about MBAM Server feature configuration, see [Server Event Logs](server-event-logs.md).</span></span>



## <span data-ttu-id="04ae6-136">相关主题</span><span class="sxs-lookup"><span data-stu-id="04ae6-136">Related topics</span></span>


<span data-ttu-id="04ae6-137">配置 MBAM 2.5 服务器功能</span><span class="sxs-lookup"><span data-stu-id="04ae6-137">Configuring the MBAM 2.5 Server Features</span></span>
 

 
## <span data-ttu-id="04ae6-138">已获得 MBAM 的建议？</span><span class="sxs-lookup"><span data-stu-id="04ae6-138">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="04ae6-139">在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="04ae6-139">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="04ae6-140">对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="04ae6-140">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>




