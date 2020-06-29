---
title: 基于 Application Virtualization Server 的方案概述
description: 基于 Application Virtualization Server 的方案概述
author: dansimp
ms.assetid: 2d91392b-5085-4a5d-94f2-15eed1ed2928
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7b3ac3f10a5b7c7705e6d72c122d52be801a6d50
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803099"
---
# <span data-ttu-id="49efb-103">基于 Application Virtualization Server 的方案概述</span><span class="sxs-lookup"><span data-stu-id="49efb-103">Application Virtualization Server-Based Scenario Overview</span></span>


<span data-ttu-id="49efb-104">如果您计划对您的 Microsoft Application Virtualization 环境使用基于服务器的部署方案，请务必了解*应用程序虚拟化管理服务器*和*应用程序虚拟化流服务器*之间的差异。</span><span class="sxs-lookup"><span data-stu-id="49efb-104">If you plan to use a server-based deployment scenario for your Microsoft Application Virtualization environment, it is important to understand the differences between the *Application Virtualization Management Server* and the *Application Virtualization Streaming Server*.</span></span> <span data-ttu-id="49efb-105">本主题介绍了这些差异，还提供了有关程序包传递方法、传输协议和外部组件的信息，在你继续部署时，你需要考虑这些信息。</span><span class="sxs-lookup"><span data-stu-id="49efb-105">This topic describes those differences and also provides information about package delivery methods, transmission protocols, and external components that you will need to consider as you proceed with your deployment.</span></span>

## <span data-ttu-id="49efb-106">应用程序虚拟化管理服务器</span><span class="sxs-lookup"><span data-stu-id="49efb-106">Application Virtualization Management Server</span></span>


<span data-ttu-id="49efb-107">应用程序虚拟化管理服务器同时执行发布功能和流函数。</span><span class="sxs-lookup"><span data-stu-id="49efb-107">The Application Virtualization Management Server performs both the publishing function and the streaming function.</span></span> <span data-ttu-id="49efb-108">服务器将应用程序图标、快捷方式和文件类型关联发布到已授权用户的 app-v 客户端。</span><span class="sxs-lookup"><span data-stu-id="49efb-108">The server publishes application icons, shortcuts, and file type associations to the App-V clients for authorized users.</span></span> <span data-ttu-id="49efb-109">当接收到应用程序的用户请求时，将使用 RTSP 或 RTSPS 协议将数据按需传输到授权用户。</span><span class="sxs-lookup"><span data-stu-id="49efb-109">When user requests for applications are received the server streams that data on-demand to authorized users using RTSP or RTSPS protocols.</span></span> <span data-ttu-id="49efb-110">在使用此服务器的大多数配置中，一个或多个管理服务器共享一个用于配置和程序包信息的通用数据存储。</span><span class="sxs-lookup"><span data-stu-id="49efb-110">In most configurations using this server, one or more Management Servers share a common data store for configuration and package information.</span></span>

<span data-ttu-id="49efb-111">应用程序虚拟化管理服务器使用 Active Directory 组管理用户授权。</span><span class="sxs-lookup"><span data-stu-id="49efb-111">The Application Virtualization Management Servers use Active Directory groups to manage user authorization.</span></span> <span data-ttu-id="49efb-112">除了 Active Directory 域服务，这些服务器还安装了 SQL Server 来管理数据库和数据存储。</span><span class="sxs-lookup"><span data-stu-id="49efb-112">In addition to Active Directory Domain Services, these servers have SQL Server installed to manage the database and data store.</span></span> <span data-ttu-id="49efb-113">管理服务器通过应用程序虚拟化管理控制台进行控制，该控制台是 Microsoft 管理控制台的一个管理单元。</span><span class="sxs-lookup"><span data-stu-id="49efb-113">The Management Server is controlled through the Application Virtualization Management Console, a snap-in to the Microsoft Management Console.</span></span>

<span data-ttu-id="49efb-114">由于应用程序虚拟化管理服务器将应用程序流式流式处理应用程序，因此这些服务器非常适合具有可靠、高带宽 Lan 的系统配置。</span><span class="sxs-lookup"><span data-stu-id="49efb-114">Because the Application Virtualization Management Servers stream applications to end-users on demand, these servers are ideally suited for system configurations that have reliable, high-bandwidth LANs.</span></span>

## <span data-ttu-id="49efb-115">应用程序虚拟化流服务器</span><span class="sxs-lookup"><span data-stu-id="49efb-115">Application Virtualization Streaming Server</span></span>


<span data-ttu-id="49efb-116">应用程序虚拟化流服务器提供管理服务器提供的相同流和程序包升级功能，但没有其 Active Directory 或 SQL Server 要求。</span><span class="sxs-lookup"><span data-stu-id="49efb-116">The Application Virtualization Streaming Server delivers the same streaming and package upgrade capabilities provided by the Management Server, but without its Active Directory or SQL Server requirements.</span></span> <span data-ttu-id="49efb-117">但是，流服务器没有发布服务，也没有授权或计量功能。</span><span class="sxs-lookup"><span data-stu-id="49efb-117">However, the Streaming Server does not have a publishing service, nor does it have licensing or metering capabilities.</span></span> <span data-ttu-id="49efb-118">单独的 App-v 管理服务器的发布服务与 App-v 流式处理服务器结合使用。</span><span class="sxs-lookup"><span data-stu-id="49efb-118">The publishing service of a separate App-V Management Server is used in conjunction with the App-V Streaming Server.</span></span> <span data-ttu-id="49efb-119">应用程序-V 流服务器解决了希望在多个位置使用应用程序虚拟化和经典服务器配置的流功能的企业需求，但可能没有基础结构来支持每个位置中的 app-v 管理服务器。</span><span class="sxs-lookup"><span data-stu-id="49efb-119">The App-V Streaming Server addresses the needs of businesses that want to use Application Virtualization in multiple locations with the streaming capabilities of the classic server configuration but might not have the infrastructure to support App-V Management Servers in every location.</span></span>

<span data-ttu-id="49efb-120">应用程序虚拟化流服务器还可以在具有现有电子软件分发系统（ESD）的环境中使用。</span><span class="sxs-lookup"><span data-stu-id="49efb-120">The Application Virtualization Streaming Server can also be used in environments with an existing electronic software distribution system (ESD).</span></span> <span data-ttu-id="49efb-121">使用 ESD 管理流式处理应用程序。</span><span class="sxs-lookup"><span data-stu-id="49efb-121">You use the ESD to manage streaming applications.</span></span> <span data-ttu-id="49efb-122">与应用程序虚拟化管理服务器不同，流服务器不使用 SQL 或管理控制台。</span><span class="sxs-lookup"><span data-stu-id="49efb-122">Unlike the Application Virtualization Management Server, the Streaming Server does not use SQL or a management console.</span></span> <span data-ttu-id="49efb-123">这些服务器使用访问控制列表（Acl）授予用户授权。</span><span class="sxs-lookup"><span data-stu-id="49efb-123">These servers use access control lists (ACLs) to grant user authorization.</span></span>

## <span data-ttu-id="49efb-124">程序包传递方法</span><span class="sxs-lookup"><span data-stu-id="49efb-124">Package Delivery Methods</span></span>


<span data-ttu-id="49efb-125">如果你计划将应用程序虚拟化服务器用作发布传递方法，你需要确定你的方案所采用的以下哪种包传递方法：</span><span class="sxs-lookup"><span data-stu-id="49efb-125">If you plan to use an Application Virtualization Server as the publishing delivery method, you need to determine which of the following package delivery methods your scenario employs:</span></span>

-   *<span data-ttu-id="49efb-126">动态包送达</span><span class="sxs-lookup"><span data-stu-id="49efb-126">Dynamic package delivery</span></span>*

-   *<span data-ttu-id="49efb-127">从文件包传递中加载</span><span class="sxs-lookup"><span data-stu-id="49efb-127">Load from file package delivery</span></span>*

### <span data-ttu-id="49efb-128">动态包送达</span><span class="sxs-lookup"><span data-stu-id="49efb-128">Dynamic Package Delivery</span></span>

<span data-ttu-id="49efb-129">在动态程序包传递过程中，服务器（应用程序虚拟化管理服务器、应用程序虚拟化流服务器或 IIS 服务器）通过按需部署向最终用户提供虚拟化应用程序。</span><span class="sxs-lookup"><span data-stu-id="49efb-129">During dynamic package delivery, the server (Application Virtualization Management Server, Application Virtualization Streaming Server, or IIS server) delivers the virtualized applications to the end users through on-demand deployment.</span></span> <span data-ttu-id="49efb-130">只有当用户首次尝试启动应用程序时，服务器才会将虚拟化的应用程序和程序包传递给客户端计算机（按需）。</span><span class="sxs-lookup"><span data-stu-id="49efb-130">The server delivers the virtualized applications and packages to a client computer only when a user first attempts to launch an application (on demand).</span></span> <span data-ttu-id="49efb-131">服务器仅流式处理启动应用程序所需的块（主要功能块）。</span><span class="sxs-lookup"><span data-stu-id="49efb-131">The server streams only the blocks needed to start the application (primary feature block).</span></span> <span data-ttu-id="49efb-132">将主功能块交付给客户端后，应用程序运行;客户端不会收到完整的应用程序（增量部署），除非客户需要访问主功能块中未包含的应用程序部分。</span><span class="sxs-lookup"><span data-stu-id="49efb-132">After the primary feature block is delivered to the client, the application runs; the client does not receive the complete application (incremental deployment) unless the client needs access to a part of the application that is not included in the primary feature block.</span></span> <span data-ttu-id="49efb-133">发生这种情况时，客户端将执行顺序外请求，并将辅助功能块流传送到客户端。</span><span class="sxs-lookup"><span data-stu-id="49efb-133">When this occurs, the client performs an out-of-sequence request and the secondary feature block is streamed to the client.</span></span> <span data-ttu-id="49efb-134">动态程序包交付允许快速应用程序启动。</span><span class="sxs-lookup"><span data-stu-id="49efb-134">Dynamic package delivery allows for rapid application launch.</span></span>

### <span data-ttu-id="49efb-135">从文件包传递中加载</span><span class="sxs-lookup"><span data-stu-id="49efb-135">Load from File Package Delivery</span></span>

<span data-ttu-id="49efb-136">对于从文件包传递进行的加载，服务器会在用户启动应用程序之前将整个虚拟化应用程序包传递到客户端计算机。</span><span class="sxs-lookup"><span data-stu-id="49efb-136">For load from file package delivery, the server delivers the entire virtualized application package to a client computer before the user launches the application.</span></span> <span data-ttu-id="49efb-137">在此方案中，虚拟化的应用程序以完整的程序包形式传递，而不是通过动态传递模型使用的动态、增量方法。</span><span class="sxs-lookup"><span data-stu-id="49efb-137">In this scenario, virtualized applications are delivered as a full package, rather than through the dynamic, incremental method used by the dynamic delivery model.</span></span>

<span data-ttu-id="49efb-138">**注意** 对于每个交付方法，初始虚拟应用程序交付过程和虚拟应用程序更新过程相同;已更新的虚拟应用程序包替换原始应用程序包。</span><span class="sxs-lookup"><span data-stu-id="49efb-138">**Note** For each delivery method, the initial virtual application delivery process and the virtual application update process are the same; the updated virtual application package replaces the original application package.</span></span>

 

<span data-ttu-id="49efb-139">下表比较了每个程序包传递方法的优点和缺点。</span><span class="sxs-lookup"><span data-stu-id="49efb-139">The following table compares the advantages and disadvantages of each package delivery method.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="49efb-140">方法</span><span class="sxs-lookup"><span data-stu-id="49efb-140">Method</span></span></th>
<th align="left"><span data-ttu-id="49efb-141">优点</span><span class="sxs-lookup"><span data-stu-id="49efb-141">Advantages</span></span></th>
<th align="left"><span data-ttu-id="49efb-142">缺点</span><span class="sxs-lookup"><span data-stu-id="49efb-142">Disadvantages</span></span></th>
<th align="left"><span data-ttu-id="49efb-143">备注</span><span class="sxs-lookup"><span data-stu-id="49efb-143">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="49efb-144">动态包送达</span><span class="sxs-lookup"><span data-stu-id="49efb-144">Dynamic package delivery</span></span></p></td>
<td align="left"><p><span data-ttu-id="49efb-145">应用程序按需交付和更新。</span><span class="sxs-lookup"><span data-stu-id="49efb-145">Applications are delivered and updated on demand.</span></span></p>
<p><span data-ttu-id="49efb-146">应用程序以增量方式进行传递和更新，以优化启动时间。</span><span class="sxs-lookup"><span data-stu-id="49efb-146">Applications are delivered and updated incrementally to optimize launch time.</span></span></p>
<p><span data-ttu-id="49efb-147">更新将自动传递到客户端桌面。</span><span class="sxs-lookup"><span data-stu-id="49efb-147">Updates are delivered automatically to the client desktop.</span></span></p></td>
<td align="left"><p><span data-ttu-id="49efb-148">由于服务器要求，企业拓扑中的占用量更大。</span><span class="sxs-lookup"><span data-stu-id="49efb-148">Larger footprint in enterprise topology because of server requirements.</span></span></p>
<p><span data-ttu-id="49efb-149">应用程序流应位于 LAN 上;通过 WAN 或在服务器与客户端之间使用不可靠或间歇性连接的部署方案可能无法使用。</span><span class="sxs-lookup"><span data-stu-id="49efb-149">Application streaming should be over a LAN; deployment scenarios over a WAN or that use an unreliable or intermittent connection between the server and client might be unusable.</span></span></p></td>
<td align="left"><p><span data-ttu-id="49efb-150">需要流式处理基础结构。</span><span class="sxs-lookup"><span data-stu-id="49efb-150">Requires a streaming infrastructure.</span></span></p>
<p><span data-ttu-id="49efb-151">用于将应用程序虚拟化桌面客户端软件部署到最终用户计算机的 Windows 安装程序。</span><span class="sxs-lookup"><span data-stu-id="49efb-151">Windows Installer used to deploy Application Virtualization Desktop Client software to end-user computers.</span></span></p>
<p><span data-ttu-id="49efb-152">大型企业应将应用程序虚拟化流服务器用作分发点。</span><span class="sxs-lookup"><span data-stu-id="49efb-152">Large enterprises should use Application Virtualization Streaming Servers as distribution points.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="49efb-153">从文件包传递中加载</span><span class="sxs-lookup"><span data-stu-id="49efb-153">Load from file package delivery</span></span></p></td>
<td align="left"><p><span data-ttu-id="49efb-154">与典型的企业管理做法保持一致。</span><span class="sxs-lookup"><span data-stu-id="49efb-154">Consistent with typical enterprise management practices.</span></span></p>
<p><span data-ttu-id="49efb-155">支持独立的配置方案。</span><span class="sxs-lookup"><span data-stu-id="49efb-155">Supports stand-alone configuration scenario.</span></span></p>
<p><span data-ttu-id="49efb-156">提供对微型办事处问题的解决方案。</span><span class="sxs-lookup"><span data-stu-id="49efb-156">Provides solution to micro–branch office problem.</span></span></p></td>
<td align="left"><p><span data-ttu-id="49efb-157">应用程序交付和更新不可能按需进行。</span><span class="sxs-lookup"><span data-stu-id="49efb-157">Application delivery and update is not possible on-demand.</span></span></p>
<p><span data-ttu-id="49efb-158">应用程序交付和更新不是增量操作;它会增加相对于动态传递的资源消耗。</span><span class="sxs-lookup"><span data-stu-id="49efb-158">Application delivery and update is not incremental; it increases resource consumption relative to dynamic delivery.</span></span></p></td>
<td align="left"><p><span data-ttu-id="49efb-159">IT 组织通常负责管理应用程序许可证、用户授权和身份验证。</span><span class="sxs-lookup"><span data-stu-id="49efb-159">The IT organization is often responsible for managing application licenses, user authorization, and authentication.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="49efb-160">与服务器相关的协议和外部组件</span><span class="sxs-lookup"><span data-stu-id="49efb-160">Server-Related Protocols and External Components</span></span>


<span data-ttu-id="49efb-161">下表列出了可在基于应用程序虚拟化的方案中使用的服务器类型及其相应的传输协议和支持特定服务器配置所需的外部组件。</span><span class="sxs-lookup"><span data-stu-id="49efb-161">The following table lists the server types that can be used in an Application Virtualization Server-based scenarios, along with their corresponding transmission protocols and the external components needed to support the specific server configuration.</span></span> <span data-ttu-id="49efb-162">该表还包括每种服务器类型的报告机制和活动的升级机制。</span><span class="sxs-lookup"><span data-stu-id="49efb-162">The table also includes the reporting mechanism and the active upgrade mechanism for each server type.</span></span> <span data-ttu-id="49efb-163">由于这些方案都使用应用程序虚拟化管理服务器，因此你可以使用内置于系统的内部报表功能。</span><span class="sxs-lookup"><span data-stu-id="49efb-163">Because these scenarios all use the Application Virtualization Management Server, you can use the internal reporting functionality that is built into the system.</span></span> <span data-ttu-id="49efb-164">如果你使用应用程序虚拟化管理或应用程序虚拟流服务器向客户端发送程序包，则当用户登录到客户端时，服务器上的程序包会自动升级;如果使用 IIS 服务器或文件将程序包传递给客户端，则必须手动升级客户端上的程序包。</span><span class="sxs-lookup"><span data-stu-id="49efb-164">If you use an Application Virtualization Management or an Application Virtualization Streaming Server to deliver packages to the client, packages on the server are automatically upgraded when a user logs into the client; if you use IIS servers or a file to deliver the packages to the client, the packages on the client must be upgraded manually.</span></span>

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="49efb-165">服务器类型</span><span class="sxs-lookup"><span data-stu-id="49efb-165">Server Type</span></span></th>
<th align="left"><span data-ttu-id="49efb-166">协议</span><span class="sxs-lookup"><span data-stu-id="49efb-166">Protocols</span></span></th>
<th align="left"><span data-ttu-id="49efb-167">需要外部组件</span><span class="sxs-lookup"><span data-stu-id="49efb-167">External Components Needed</span></span></th>
<th align="left"><span data-ttu-id="49efb-168">报告</span><span class="sxs-lookup"><span data-stu-id="49efb-168">Reporting</span></span></th>
<th align="left"><span data-ttu-id="49efb-169">活动升级</span><span class="sxs-lookup"><span data-stu-id="49efb-169">Active Upgrade</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="49efb-170">应用程序虚拟化管理服务器</span><span class="sxs-lookup"><span data-stu-id="49efb-170">Application Virtualization Management Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="49efb-171">RTSP</span><span class="sxs-lookup"><span data-stu-id="49efb-171">RTSP</span></span></p>
<p><span data-ttu-id="49efb-172">RTSPS</span><span class="sxs-lookup"><span data-stu-id="49efb-172">RTSPS</span></span></p></td>
<td align="left"><p><span data-ttu-id="49efb-173">使用 HTTPS 时，请使用 IIS 服务器下载 .ICO 和 OSD 文件和防火墙，以防止服务器暴露给 Internet。</span><span class="sxs-lookup"><span data-stu-id="49efb-173">When using HTTPS, use an IIS server to download ICO and OSD files and a firewall to protect the server from exposure to the Internet.</span></span></p></td>
<td align="left"><p><span data-ttu-id="49efb-174">内置</span><span class="sxs-lookup"><span data-stu-id="49efb-174">Internal</span></span></p></td>
<td align="left"><p><span data-ttu-id="49efb-175">支持</span><span class="sxs-lookup"><span data-stu-id="49efb-175">Supported</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="49efb-176">应用程序虚拟化流服务器</span><span class="sxs-lookup"><span data-stu-id="49efb-176">Application Virtualization Streaming Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="49efb-177">RTSP</span><span class="sxs-lookup"><span data-stu-id="49efb-177">RTSP</span></span></p>
<p><span data-ttu-id="49efb-178">RTSPS</span><span class="sxs-lookup"><span data-stu-id="49efb-178">RTSPS</span></span></p></td>
<td align="left"><p><span data-ttu-id="49efb-179">使用一种机制来同步管理服务器和流服务器之间的内容。</span><span class="sxs-lookup"><span data-stu-id="49efb-179">Use a mechanism to synchronize the content between the Management Server and the Streaming Server.</span></span> <span data-ttu-id="49efb-180">使用 HTTPS 时，请使用 IIS 服务器下载 .ICO 和 OSD 文件，并使用防火墙保护服务器对 Internet 的暴露。</span><span class="sxs-lookup"><span data-stu-id="49efb-180">When using HTTPS, use an IIS server to download ICO and OSD files and use a firewall to protect the server from exposure to the Internet.</span></span></p></td>
<td align="left"><p><span data-ttu-id="49efb-181">内置</span><span class="sxs-lookup"><span data-stu-id="49efb-181">Internal</span></span></p></td>
<td align="left"><p><span data-ttu-id="49efb-182">支持</span><span class="sxs-lookup"><span data-stu-id="49efb-182">Supported</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="49efb-183">IIS 服务器</span><span class="sxs-lookup"><span data-stu-id="49efb-183">IIS server</span></span></p></td>
<td align="left"><p><span data-ttu-id="49efb-184">HTTP</span><span class="sxs-lookup"><span data-stu-id="49efb-184">HTTP</span></span></p>
<p><span data-ttu-id="49efb-185">HTTPS</span><span class="sxs-lookup"><span data-stu-id="49efb-185">HTTPS</span></span></p></td>
<td align="left"><p><span data-ttu-id="49efb-186">使用一种机制来同步管理服务器和流服务器之间的内容。</span><span class="sxs-lookup"><span data-stu-id="49efb-186">Use a mechanism to synchronize the content between the Management Server and the Streaming Server.</span></span> <span data-ttu-id="49efb-187">使用 HTTP 或 HTTPS 时，请使用 IIS 服务器下载 .ICO 和 OSD 文件和防火墙，以防止服务器暴露给 Internet。</span><span class="sxs-lookup"><span data-stu-id="49efb-187">When using HTTP or HTTPS, use an IIS server to download ICO and OSD files and a firewall to protect the server from exposure to the Internet.</span></span></p></td>
<td align="left"><p><span data-ttu-id="49efb-188">内置</span><span class="sxs-lookup"><span data-stu-id="49efb-188">Internal</span></span></p></td>
<td align="left"><p><span data-ttu-id="49efb-189">不支持</span><span class="sxs-lookup"><span data-stu-id="49efb-189">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="49efb-190">文件</span><span class="sxs-lookup"><span data-stu-id="49efb-190">File</span></span></p></td>
<td align="left"><p><span data-ttu-id="49efb-191">SMB</span><span class="sxs-lookup"><span data-stu-id="49efb-191">SMB</span></span></p></td>
<td align="left"><p><span data-ttu-id="49efb-192">你需要一种方法来同步管理服务器和流服务器之间的内容。</span><span class="sxs-lookup"><span data-stu-id="49efb-192">You need a way to synchronize the content between the Management Server and the Streaming Server.</span></span> <span data-ttu-id="49efb-193">您需要具有文件共享或流功能的客户端计算机。</span><span class="sxs-lookup"><span data-stu-id="49efb-193">You need a client computer with file sharing or streaming capability.</span></span></p></td>
<td align="left"><p><span data-ttu-id="49efb-194">内置</span><span class="sxs-lookup"><span data-stu-id="49efb-194">Internal</span></span></p></td>
<td align="left"><p><span data-ttu-id="49efb-195">不支持</span><span class="sxs-lookup"><span data-stu-id="49efb-195">Not Supported</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="49efb-196">相关主题</span><span class="sxs-lookup"><span data-stu-id="49efb-196">Related topics</span></span>


[<span data-ttu-id="49efb-197">基于电子软件分发的方案</span><span class="sxs-lookup"><span data-stu-id="49efb-197">Electronic Software Distribution-Based Scenario</span></span>](electronic-software-distribution-based-scenario.md)

[<span data-ttu-id="49efb-198">如何为基于服务器的部署配置服务器</span><span class="sxs-lookup"><span data-stu-id="49efb-198">How to Configure Servers for Server-Based Deployment</span></span>](how-to-configure-servers-for-server-based-deployment.md)

[<span data-ttu-id="49efb-199">如何安装服务器和系统组件</span><span class="sxs-lookup"><span data-stu-id="49efb-199">How to Install the Servers and System Components</span></span>](how-to-install-the-servers-and-system-components.md)

 

 





