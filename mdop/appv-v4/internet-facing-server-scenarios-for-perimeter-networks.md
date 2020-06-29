---
title: 适用于外围网络的面向 Internet 的服务器方案
description: 适用于外围网络的面向 Internet 的服务器方案
author: dansimp
ms.assetid: 8a4da6e6-82c7-49e5-b9b1-1666cba02f65
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: fcb04e651341fa107c358eaabbd7992d7ea155ec
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798940"
---
# <span data-ttu-id="8f0b7-103">适用于外围网络的面向 Internet 的服务器方案</span><span class="sxs-lookup"><span data-stu-id="8f0b7-103">Internet-Facing Server Scenarios for Perimeter Networks</span></span>


<span data-ttu-id="8f0b7-104">App-v 4.5 支持面向 Internet 的服务器方案，在这种情况下，未连接到企业网络或从网络断开连接的用户仍可使用 app-v。</span><span class="sxs-lookup"><span data-stu-id="8f0b7-104">App-V4.5 supports Internet-facing server scenarios, in which users who are not connected to the corporate network or who disconnect from the network can still use App-V.</span></span> <span data-ttu-id="8f0b7-105">如下图所示，仅支持在 Internet （RTSPS 和 HTTPS）上使用安全协议。</span><span class="sxs-lookup"><span data-stu-id="8f0b7-105">As shown in the following illustration, only the use of secure protocols on the Internet (RTSPS and HTTPS) is supported.</span></span>

![app-v 防火墙定位图](images/appvfirewalls.gif)

<span data-ttu-id="8f0b7-107">你可以使用 ISA 服务器设置面向 Internet 的解决方案，其中 App-v 基础结构位于内部网络上的以下几个方面：</span><span class="sxs-lookup"><span data-stu-id="8f0b7-107">You can set up an Internet-facing solution, using an ISA Server, where the App-V infrastructure is on the internal network in the following ways:</span></span>

-   <span data-ttu-id="8f0b7-108">为托管 .ICO 和 OSD 文件的 IIS 服务器创建 Web 发布规则，也可以为流的程序包（可选）位于内部网络上。</span><span class="sxs-lookup"><span data-stu-id="8f0b7-108">Create a Web Publishing rule for the IIS server that is hosting the ICO and OSD files—and optionally, the packages for streaming—located on the internal network.</span></span> <span data-ttu-id="8f0b7-109">提供了详细步骤 <https://go.microsoft.com/fwlink/?LinkId=151982> 。</span><span class="sxs-lookup"><span data-stu-id="8f0b7-109">Detailed steps are provided at <https://go.microsoft.com/fwlink/?LinkId=151982>.</span></span>

-   <span data-ttu-id="8f0b7-110">为 App-v Web 管理服务器（RTSPS）创建服务器发布规则。</span><span class="sxs-lookup"><span data-stu-id="8f0b7-110">Create a Server Publishing rule for the App-V Web Management Server (RTSPS).</span></span> <span data-ttu-id="8f0b7-111">提供了详细步骤 [https://go.microsoft.com/fwlink/?LinkId=151983&](https://go.microsoft.com/fwlink/?LinkId=151983) 。</span><span class="sxs-lookup"><span data-stu-id="8f0b7-111">Detailed steps are provided at [https://go.microsoft.com/fwlink/?LinkId=151983&](https://go.microsoft.com/fwlink/?LinkId=151983).</span></span>

<span data-ttu-id="8f0b7-112">如下图所示，如果基础结构已在客户端和 ISA 服务器之间或 ISA 服务器与内部网络之间实现了其他防火墙，则必须创建 RTSPS （TCP 322）和 HTTPS （TCP 443）防火墙规则来支持流量流。</span><span class="sxs-lookup"><span data-stu-id="8f0b7-112">As shown in the following illustration, if the infrastructure has implemented other firewalls between the client and the ISA Server or between the ISA Server and the internal network, both RTSPS (TCP 322) and HTTPS (TCP 443) firewall rules must be created to support the flow of traffic.</span></span> <span data-ttu-id="8f0b7-113">此外，如果在 ISA 服务器和内部网络之间实现了防火墙，则必须允许域成员的默认流量通过防火墙（DNS、LDAP、Kerberos、SMB/CIFS）进行隧道。</span><span class="sxs-lookup"><span data-stu-id="8f0b7-113">Also, if firewalls have been implemented between the ISA Server and the internal network, the default traffic required for domain members must be permitted to tunnel through the firewall (DNS, LDAP, Kerberos, SMB/CIFS).</span></span>

![应用程序-v 外围网络防火墙图](images/appvperimeternetworkfirewall.gif)

<span data-ttu-id="8f0b7-115">由于防火墙解决方案因环境而异，本主题中提供的指南介绍了在外围网络中配置面向 Internet 的 App-v 环境所需的流量。</span><span class="sxs-lookup"><span data-stu-id="8f0b7-115">Because the firewall solutions vary from environment to environment, the guidance provided in this topic describes the traffic that would be required to configure an Internet-facing App-V environment in the perimeter network.</span></span> <span data-ttu-id="8f0b7-116">此信息还包括推荐的内部网络服务器。</span><span class="sxs-lookup"><span data-stu-id="8f0b7-116">This information also includes the recommended internal network servers.</span></span>

<span data-ttu-id="8f0b7-117">将以下服务器放在外围网络中：</span><span class="sxs-lookup"><span data-stu-id="8f0b7-117">Place the following servers in the perimeter network:</span></span>

-   <span data-ttu-id="8f0b7-118">App-v 管理服务器</span><span class="sxs-lookup"><span data-stu-id="8f0b7-118">App-V Management Server</span></span>

-   <span data-ttu-id="8f0b7-119">用于发布和流式处理的 IIS 服务器</span><span class="sxs-lookup"><span data-stu-id="8f0b7-119">IIS server for publishing and streaming</span></span>

<span data-ttu-id="8f0b7-120">**注意** 最佳做法是将管理服务器和 IIS 服务器放在单独的计算机上。</span><span class="sxs-lookup"><span data-stu-id="8f0b7-120">**Note** It is a best practice to place the Management Server and IIS server on separate computers.</span></span>

 

<span data-ttu-id="8f0b7-121">将以下服务器放入内部网络：</span><span class="sxs-lookup"><span data-stu-id="8f0b7-121">Place the following servers in the internal network:</span></span>

-   <span data-ttu-id="8f0b7-122">内容服务器</span><span class="sxs-lookup"><span data-stu-id="8f0b7-122">Content server</span></span>

-   <span data-ttu-id="8f0b7-123">数据存储（SQL Server）</span><span class="sxs-lookup"><span data-stu-id="8f0b7-123">Data store (SQL Server)</span></span>

-   <span data-ttu-id="8f0b7-124">Active Directory 域控制器</span><span class="sxs-lookup"><span data-stu-id="8f0b7-124">Active Directory Domain Controller</span></span>

## <span data-ttu-id="8f0b7-125">流量要求</span><span class="sxs-lookup"><span data-stu-id="8f0b7-125">Traffic Requirements</span></span>


<span data-ttu-id="8f0b7-126">下表列出了从 Internet 和外围网络以及从外围网络到内部网络的通信的流量要求。</span><span class="sxs-lookup"><span data-stu-id="8f0b7-126">The following tables list the traffic requirements for communication from the Internet and the perimeter network and from the perimeter network to the internal network.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="8f0b7-127">从 Internet 到外围网络的流量要求</span><span class="sxs-lookup"><span data-stu-id="8f0b7-127">Traffic Requirements from Internet to Perimeter Network</span></span></th>
<th align="left"><span data-ttu-id="8f0b7-128">详细信息</span><span class="sxs-lookup"><span data-stu-id="8f0b7-128">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8f0b7-129">RTSPS （发布刷新和流式处理程序包）</span><span class="sxs-lookup"><span data-stu-id="8f0b7-129">RTSPS (publishing refresh and streaming packages)</span></span></p></td>
<td align="left"><p><span data-ttu-id="8f0b7-130">默认情况下为 TCP 322;可以在 App-v 管理服务器中更改此项。</span><span class="sxs-lookup"><span data-stu-id="8f0b7-130">TCP 322 by default; this can be changed in App-V Management Server.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8f0b7-131">HTTPS （发布 .ICO 和 OSD 文件和流式处理程序包）</span><span class="sxs-lookup"><span data-stu-id="8f0b7-131">HTTPS (publishing ICO and OSD files and streaming packages)</span></span></p></td>
<td align="left"><p><span data-ttu-id="8f0b7-132">默认情况下为 TCP 443;可在 IIS 配置中更改此设置。</span><span class="sxs-lookup"><span data-stu-id="8f0b7-132">TCP 443 by default; this can be changed in the IIS configuration.</span></span></p></td>
</tr>
</tbody>
</table>

 

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="8f0b7-133">从外围网络到内部网络的流量要求</span><span class="sxs-lookup"><span data-stu-id="8f0b7-133">Traffic Requirements from Perimeter Network to Internal Network</span></span></th>
<th align="left"><span data-ttu-id="8f0b7-134">详细信息</span><span class="sxs-lookup"><span data-stu-id="8f0b7-134">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8f0b7-135">SQL Server</span><span class="sxs-lookup"><span data-stu-id="8f0b7-135">SQL Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="8f0b7-136">TCP 1433 是默认设置，但可以在 SQL Server 中进行配置。</span><span class="sxs-lookup"><span data-stu-id="8f0b7-136">TCP 1433 is the default but can be configured in SQL Server.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8f0b7-137">SMB/CIFS</span><span class="sxs-lookup"><span data-stu-id="8f0b7-137">SMB/CIFS</span></span></p></td>
<td align="left"><p><span data-ttu-id="8f0b7-138">如果内容目录来自管理服务器或 IIS 服务器的远程位置（推荐）。</span><span class="sxs-lookup"><span data-stu-id="8f0b7-138">If the content directory is located remotely from the Management Server(s) or IIS server (recommended).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8f0b7-139">Kerberos</span><span class="sxs-lookup"><span data-stu-id="8f0b7-139">Kerberos</span></span></p></td>
<td align="left"><p><span data-ttu-id="8f0b7-140">TCP 和 UDP 88</span><span class="sxs-lookup"><span data-stu-id="8f0b7-140">TCP and UDP 88</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8f0b7-141">适用</span><span class="sxs-lookup"><span data-stu-id="8f0b7-141">LDAP</span></span></p></td>
<td align="left"><p><span data-ttu-id="8f0b7-142">TCP 和 UDP 389</span><span class="sxs-lookup"><span data-stu-id="8f0b7-142">TCP and UDP 389</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8f0b7-143">DNS</span><span class="sxs-lookup"><span data-stu-id="8f0b7-143">DNS</span></span></p></td>
<td align="left"><p><span data-ttu-id="8f0b7-144">对于内部资源的名称解析（可在外围网络服务器上使用主机的文件时消除）</span><span class="sxs-lookup"><span data-stu-id="8f0b7-144">For name resolution of internal resources (can be eliminated with the use of host’s file on perimeter network servers)</span></span></p></td>
</tr>
</tbody>
</table>

 

 

 





