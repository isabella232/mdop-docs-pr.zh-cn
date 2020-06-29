---
title: Application Virtualization System 组件概述
description: Application Virtualization System 组件概述
author: dansimp
ms.assetid: 75d88ef7-44d8-4fa7-b7f5-9153f37e570d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: cab0065b9966094da687cce2f5e94069922189fc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798894"
---
# <span data-ttu-id="e6390-103">Application Virtualization System 组件概述</span><span class="sxs-lookup"><span data-stu-id="e6390-103">Overview of the Application Virtualization System Components</span></span>


<span data-ttu-id="e6390-104">下表介绍了 Microsoft Application Virtualization 管理系统的主要组件。</span><span class="sxs-lookup"><span data-stu-id="e6390-104">The following table describes the primary components of the Microsoft Application Virtualization Management System.</span></span> <span data-ttu-id="e6390-105">有关部署这些系统组件的详细信息，请参阅[基于应用程序虚拟服务器的方案](application-virtualization-server-based-scenario.md)。</span><span class="sxs-lookup"><span data-stu-id="e6390-105">For more information about deploying these system components, see [Application Virtualization Server-Based Scenario](application-virtualization-server-based-scenario.md).</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e6390-106">组件</span><span class="sxs-lookup"><span data-stu-id="e6390-106">Component</span></span></th>
<th align="left"><span data-ttu-id="e6390-107">函数</span><span class="sxs-lookup"><span data-stu-id="e6390-107">Function</span></span></th>
<th align="left"><span data-ttu-id="e6390-108">其他信息</span><span class="sxs-lookup"><span data-stu-id="e6390-108">Additional Information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e6390-109">Microsoft Application Virtualization 管理服务器</span><span class="sxs-lookup"><span data-stu-id="e6390-109">Microsoft Application Virtualization Management Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="e6390-110">负责流式处理程序包内容并将快捷方式和文件类型关联发布到应用程序虚拟化客户端的组件。</span><span class="sxs-lookup"><span data-stu-id="e6390-110">The component responsible for streaming the package content and publishing the shortcuts and file type associations to the Application Virtualization Client.</span></span></p></td>
<td align="left"><p><span data-ttu-id="e6390-111">应用程序虚拟化管理服务器支持活动升级、许可证管理和可用于报告的数据库。</span><span class="sxs-lookup"><span data-stu-id="e6390-111">The Application Virtualization Management Server supports active upgrade, License Management, and a database that can be used for reporting.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="e6390-112">内容 </strong> 文件夹</span><span class="sxs-lookup"><span data-stu-id="e6390-112">Content</strong> folder</span></span></p></td>
<td align="left"><p><span data-ttu-id="e6390-113">用于流式处理的应用程序虚拟化程序包的位置。</span><span class="sxs-lookup"><span data-stu-id="e6390-113">The location of the Application Virtualization packages for streaming.</span></span></p></td>
<td align="left"><p><span data-ttu-id="e6390-114">此文件夹可以位于应用程序虚拟化管理服务器上的共享位置。</span><span class="sxs-lookup"><span data-stu-id="e6390-114">This folder can be located on a share on or off the Application Virtualization Management Server.</span></span> <span data-ttu-id="e6390-115">该文件夹也可以位于存储区域网络（SAN）上。</span><span class="sxs-lookup"><span data-stu-id="e6390-115">The folder can also be located on a Storage Area Network (SAN).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e6390-116">Microsoft Application Virtualization 管理控制台</span><span class="sxs-lookup"><span data-stu-id="e6390-116">Microsoft Application Virtualization Management Console</span></span></p></td>
<td align="left"><p><span data-ttu-id="e6390-117">用于 Microsoft Application Virtualization 服务器管理的 MMC 3.0 管理实用工具。</span><span class="sxs-lookup"><span data-stu-id="e6390-117">An MMC 3.0 snap-in management utility for Microsoft Application Virtualization Server administration.</span></span></p></td>
<td align="left"><p><span data-ttu-id="e6390-118">此组件可以安装在 Microsoft Application Virtualization 服务器上，也可以位于具有 MMC 3.0 和的单独工作站上。已安装 NET 2.0。</span><span class="sxs-lookup"><span data-stu-id="e6390-118">This component can be installed on the Microsoft Application Virtualization server or located on a separate workstation that has MMC3.0 and .NET2.0 installed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e6390-119">Microsoft Application Virtualization 管理 Web 服务</span><span class="sxs-lookup"><span data-stu-id="e6390-119">Microsoft Application Virtualization Management Web Service</span></span></p></td>
<td align="left"><p><span data-ttu-id="e6390-120">负责将任何读/写请求与应用程序虚拟化数据存储进行通信的组件。</span><span class="sxs-lookup"><span data-stu-id="e6390-120">The component responsible for communicating any read/write requests to the Application Virtualization data store.</span></span></p></td>
<td align="left"><p><span data-ttu-id="e6390-121">此组件可以安装在 Microsoft Application Virtualization 服务器上，也可以安装在安装了 IIS 的单独计算机上。</span><span class="sxs-lookup"><span data-stu-id="e6390-121">This component can installed on the Microsoft Application Virtualization Server or on a separate computer with IIS installed.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e6390-122">Microsoft Application Virtualization 数据存储</span><span class="sxs-lookup"><span data-stu-id="e6390-122">Microsoft Application Virtualization Data Store</span></span></p></td>
<td align="left"><p><span data-ttu-id="e6390-123">存储在 SQL 数据库中的组件，负责存储与应用程序虚拟化基础结构相关的所有信息。</span><span class="sxs-lookup"><span data-stu-id="e6390-123">The component stored in the SQL database and responsible for storing all information related to the Application Virtualization infrastructure.</span></span></p></td>
<td align="left"><p><span data-ttu-id="e6390-124">此信息包括所有应用程序记录、应用程序分配以及哪些组负责管理应用程序虚拟化环境。</span><span class="sxs-lookup"><span data-stu-id="e6390-124">This information includes all application records, application assignments, and which groups have responsibility for managing the Application Virtualization environment.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e6390-125">Microsoft Application Virtualization 流服务器</span><span class="sxs-lookup"><span data-stu-id="e6390-125">Microsoft Application Virtualization Streaming Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="e6390-126">负责托管应用程序虚拟化程序包的组件，用于向分支机构中的客户端进行流处理，其中，返回到应用程序虚拟化管理服务器的链接被视为 WAN。</span><span class="sxs-lookup"><span data-stu-id="e6390-126">The component responsible for hosting the Application Virtualization packages for streaming to clients in a branch office, where the link back to the Application Virtualization Management Server is considered a WAN.</span></span></p></td>
<td align="left"><p><span data-ttu-id="e6390-127">此服务器仅包含流功能，并且既不提供应用程序虚拟化管理控制台，也不提供应用程序虚拟化管理 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="e6390-127">This server contains streaming functionality only and provides neither the Application Virtualization Management Console nor the Application Virtualization Management Web Service.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e6390-128">Microsoft Application Virtualization Sequencer</span><span class="sxs-lookup"><span data-stu-id="e6390-128">Microsoft Application Virtualization Sequencer</span></span></p></td>
<td align="left"><p><span data-ttu-id="e6390-129">用于监视和捕获应用程序安装以创建虚拟应用程序包的组件。</span><span class="sxs-lookup"><span data-stu-id="e6390-129">The component used to monitor and capture the installation of applications to create virtual application packages.</span></span></p></td>
<td align="left"><p><span data-ttu-id="e6390-130">输出包含应用程序的图标、包含程序包定义信息的 OSD 文件、程序包清单文件和包含应用程序内容文件的 SFT 文件。</span><span class="sxs-lookup"><span data-stu-id="e6390-130">Output consists of the application’s icons, an OSD file containing package definition information, a package manifest file, and the SFT file containing the application program’s content files.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e6390-131">Microsoft Application Virtualization 客户端</span><span class="sxs-lookup"><span data-stu-id="e6390-131">Microsoft Application Virtualization Client</span></span></p></td>
<td align="left"><p><span data-ttu-id="e6390-132">在应用程序虚拟化桌面客户端或应用程序虚拟化客户端上安装的组件（以前称为 "终端服务"），并为虚拟化的应用程序提供虚拟环境。</span><span class="sxs-lookup"><span data-stu-id="e6390-132">The component installed on the Application Virtualization Desktop Client or on the Application Virtualization Client for Remote Desktop Services (formerly Terminal Services) and that provides the virtual environment for the virtualized applications.</span></span></p></td>
<td align="left"><p><span data-ttu-id="e6390-133">Microsoft Application Virtualization 客户端将程序包流管理到缓存、发布刷新、传输以及与应用程序虚拟化服务器的所有交互。</span><span class="sxs-lookup"><span data-stu-id="e6390-133">The Microsoft Application Virtualization Client manages the package streaming into cache, publishing refresh, transport, and all interaction with the Application Virtualization Servers.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="e6390-134">相关主题</span><span class="sxs-lookup"><span data-stu-id="e6390-134">Related topics</span></span>


[<span data-ttu-id="e6390-135">基于 Application Virtualization Server 的方案</span><span class="sxs-lookup"><span data-stu-id="e6390-135">Application Virtualization Server-Based Scenario</span></span>](application-virtualization-server-based-scenario.md)

[<span data-ttu-id="e6390-136">在基于 Application Virtualization Server 的实现中计划流式处理解决方案</span><span class="sxs-lookup"><span data-stu-id="e6390-136">Planning Your Streaming Solution in an Application Virtualization Server-Based Implementation</span></span>](planning-your-streaming-solution-in-an-application-virtualization-server-based-implementation.md)

[<span data-ttu-id="e6390-137">使用 Application Virtualization Management Server 发布虚拟应用程序</span><span class="sxs-lookup"><span data-stu-id="e6390-137">Publishing Virtual Applications Using Application Virtualization Management Servers</span></span>](publishing-virtual-applications-using-application-virtualization-management-servers.md)

 

 





