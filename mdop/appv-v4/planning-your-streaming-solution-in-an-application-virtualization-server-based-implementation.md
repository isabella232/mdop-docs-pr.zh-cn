---
title: 在基于 Application Virtualization Server 的实现中计划流式处理解决方案
description: 在基于 Application Virtualization Server 的实现中计划流式处理解决方案
author: dansimp
ms.assetid: 3a57306e-5c54-4fde-8593-fe3b788f18d3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0d315f554eb99fc5c05c231630eaa41d4f505535
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798857"
---
# <span data-ttu-id="dac34-103">在基于 Application Virtualization Server 的实现中计划流式处理解决方案</span><span class="sxs-lookup"><span data-stu-id="dac34-103">Planning Your Streaming Solution in an Application Virtualization Server-Based Implementation</span></span>


<span data-ttu-id="dac34-104">如果您想要将应用程序虚拟化流服务器与基于应用程序虚拟化管理服务器的实现配合使用，您可以从多个备选方案中进行选择，从而充分利用任何基础结构已存在的优势。</span><span class="sxs-lookup"><span data-stu-id="dac34-104">If you want to use Application Virtualization Streaming Servers in conjunction with your Application Virtualization Management Server-based implementation, you can choose from several alternatives, taking advantage of whatever infrastructure is already in place.</span></span> <span data-ttu-id="dac34-105">例如，如果您已在现场分支办事处拥有服务器，则可以将应用程序虚拟化 \\CONTENT 共享在这些服务器上，然后将客户端配置为使用该内容共享作为其应用程序内容源。</span><span class="sxs-lookup"><span data-stu-id="dac34-105">For example, if you already have servers in your field branch offices, you can place the Application Virtualization \\CONTENT share on those servers and then configure the clients to use that content share as their application content source.</span></span> <span data-ttu-id="dac34-106">如果您选择仅使用应用程序虚拟化管理服务器（例如，您只有一个 office），则客户端可以流式传输该服务器中的内容。</span><span class="sxs-lookup"><span data-stu-id="dac34-106">If you choose to use only Application Virtualization Management Servers—for example, because you have only a single office—the clients can stream content from that server.</span></span>

<span data-ttu-id="dac34-107">支持的选项包括使用文件服务器、IIS 服务器或应用程序虚拟化流服务器。</span><span class="sxs-lookup"><span data-stu-id="dac34-107">The supported options include using a file server, an IIS server, or an Application Virtualization Streaming Server.</span></span> <span data-ttu-id="dac34-108">您也可以在现有文件服务器或 IIS 服务器上安装应用程序虚拟化流服务器。</span><span class="sxs-lookup"><span data-stu-id="dac34-108">You could also install the Application Virtualization Streaming Server on an existing file server or IIS server.</span></span> <span data-ttu-id="dac34-109">下表汇总了这些不同选项的特征。</span><span class="sxs-lookup"><span data-stu-id="dac34-109">The characteristics of these different options are summarized in the following table.</span></span>

<span data-ttu-id="dac34-110">**注意** 活动升级功能支持将应用程序的新版本添加到应用程序 V 管理服务器或流服务器，而不会影响当前运行该应用程序的用户。</span><span class="sxs-lookup"><span data-stu-id="dac34-110">**Note** The active upgrade feature enables a new version of an application to be added to an App-V Management Server or Streaming Server without affecting users currently running the application.</span></span> <span data-ttu-id="dac34-111">App-v 客户端将在用户下次启动应用程序时从 App-v 管理服务器或流服务器自动接收最新版本的应用程序。</span><span class="sxs-lookup"><span data-stu-id="dac34-111">The App-V clients will automatically receive the latest version of the application from the App-V Management Server or Streaming Server the next time the user starts the application.</span></span> <span data-ttu-id="dac34-112">此功能需要使用 RTSP （S）协议。</span><span class="sxs-lookup"><span data-stu-id="dac34-112">Use of the RTSP(S) protocol is required for this feature.</span></span>

 

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
<th align="left"><span data-ttu-id="dac34-113">服务器类型</span><span class="sxs-lookup"><span data-stu-id="dac34-113">Server Type</span></span></th>
<th align="left"><span data-ttu-id="dac34-114">协议</span><span class="sxs-lookup"><span data-stu-id="dac34-114">Protocol</span></span></th>
<th align="left"><span data-ttu-id="dac34-115">优点</span><span class="sxs-lookup"><span data-stu-id="dac34-115">Advantages</span></span></th>
<th align="left"><span data-ttu-id="dac34-116">缺点</span><span class="sxs-lookup"><span data-stu-id="dac34-116">Disadvantages</span></span></th>
<th align="left"><span data-ttu-id="dac34-117">Links</span><span class="sxs-lookup"><span data-stu-id="dac34-117">Links</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dac34-118">文件服务器</span><span class="sxs-lookup"><span data-stu-id="dac34-118">File server</span></span></p></td>
<td align="left"><p><span data-ttu-id="dac34-119">SMB</span><span class="sxs-lookup"><span data-stu-id="dac34-119">SMB</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="dac34-120">通过 \CONTENT 共享配置现有文件服务器的简单的低成本解决方案</span><span class="sxs-lookup"><span data-stu-id="dac34-120">Simple low-cost solution to configure existing file server with \CONTENT share</span></span></p></li>
</ul></td>
<td align="left"><ul>
<li><p><span data-ttu-id="dac34-121">无活动升级</span><span class="sxs-lookup"><span data-stu-id="dac34-121">No active upgrade</span></span></p></li>
</ul></td>
<td align="left"><p><a href="how-to-configure-the-file-server.md" data-raw-source="[How to Configure the File Server](how-to-configure-the-file-server.md)"><span data-ttu-id="dac34-122">如何配置文件服务器</span><span class="sxs-lookup"><span data-stu-id="dac34-122">How to Configure the File Server</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="dac34-123">IIS 服务器</span><span class="sxs-lookup"><span data-stu-id="dac34-123">IIS server</span></span></p></td>
<td align="left"><p><span data-ttu-id="dac34-124">HTTP/HTTPS</span><span class="sxs-lookup"><span data-stu-id="dac34-124">HTTP/ HTTPS</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="dac34-125">支持使用 HTTPS 协议增强的安全性</span><span class="sxs-lookup"><span data-stu-id="dac34-125">Supports enhanced security using HTTPS protocol</span></span></p></li>
<li><p><span data-ttu-id="dac34-126">支持通过 Internet 对远程计算机进行流处理</span><span class="sxs-lookup"><span data-stu-id="dac34-126">Supports streaming to remote computers across the Internet</span></span></p></li>
<li><p><span data-ttu-id="dac34-127">防火墙中只能打开一个端口</span><span class="sxs-lookup"><span data-stu-id="dac34-127">Only one port in firewall to open</span></span></p></li>
<li><p><span data-ttu-id="dac34-128">伸缩</span><span class="sxs-lookup"><span data-stu-id="dac34-128">Scalable</span></span></p></li>
<li><p><span data-ttu-id="dac34-129">熟悉的协议</span><span class="sxs-lookup"><span data-stu-id="dac34-129">Familiar protocol</span></span></p></li>
</ul></td>
<td align="left"><ul>
<li><p><span data-ttu-id="dac34-130">需要管理 IIS</span><span class="sxs-lookup"><span data-stu-id="dac34-130">Need to manage IIS</span></span></p></li>
<li><p><span data-ttu-id="dac34-131">无活动升级</span><span class="sxs-lookup"><span data-stu-id="dac34-131">No active upgrade</span></span></p></li>
</ul></td>
<td align="left"><p><a href="how-to-configure-the-server-for-iis.md" data-raw-source="[How to Configure the Server for IIS](how-to-configure-the-server-for-iis.md)"><span data-ttu-id="dac34-132">如何为 IIS 配置服务器</span><span class="sxs-lookup"><span data-stu-id="dac34-132">How to Configure the Server for IIS</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dac34-133">应用程序虚拟化流服务器</span><span class="sxs-lookup"><span data-stu-id="dac34-133">Application Virtualization Streaming Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="dac34-134">RTSP/RTSPS</span><span class="sxs-lookup"><span data-stu-id="dac34-134">RTSP/ RTSPS</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="dac34-135">活动升级</span><span class="sxs-lookup"><span data-stu-id="dac34-135">Active upgrade</span></span></p></li>
<li><p><span data-ttu-id="dac34-136">支持使用 RTSPS 协议增强的安全性</span><span class="sxs-lookup"><span data-stu-id="dac34-136">Supports enhanced security using RTSPS protocol</span></span></p></li>
<li><p><span data-ttu-id="dac34-137">防火墙中只能打开一个端口</span><span class="sxs-lookup"><span data-stu-id="dac34-137">Only one port in firewall to open</span></span></p></li>
</ul></td>
<td align="left"><ul>
<li><p><span data-ttu-id="dac34-138">双重基础结构</span><span class="sxs-lookup"><span data-stu-id="dac34-138">Dual infrastructure</span></span></p></li>
<li><p><span data-ttu-id="dac34-139">服务器管理要求</span><span class="sxs-lookup"><span data-stu-id="dac34-139">Server administration requirement</span></span></p></li>
</ul></td>
<td align="left"><p><a href="how-to-configure-the-application-virtualization-streaming-servers.md" data-raw-source="[How to Configure the Application Virtualization Streaming Servers](how-to-configure-the-application-virtualization-streaming-servers.md)"><span data-ttu-id="dac34-140">如何配置 Application Virtualization Streaming Server</span><span class="sxs-lookup"><span data-stu-id="dac34-140">How to Configure the Application Virtualization Streaming Servers</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="dac34-141">应用程序虚拟化管理服务器</span><span class="sxs-lookup"><span data-stu-id="dac34-141">Application Virtualization Management Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="dac34-142">RTSP/RTSPS</span><span class="sxs-lookup"><span data-stu-id="dac34-142">RTSP/ RTSPS</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="dac34-143">活动升级</span><span class="sxs-lookup"><span data-stu-id="dac34-143">Active upgrade</span></span></p></li>
<li><p><span data-ttu-id="dac34-144">支持使用 RTSPS 协议增强的安全性</span><span class="sxs-lookup"><span data-stu-id="dac34-144">Supports enhanced security using RTSPS protocol</span></span></p></li>
<li><p><span data-ttu-id="dac34-145">防火墙中只能打开一个端口</span><span class="sxs-lookup"><span data-stu-id="dac34-145">Only one port in firewall to open</span></span></p></li>
</ul></td>
<td align="left"><ul>
<li><p><span data-ttu-id="dac34-146">双重基础结构</span><span class="sxs-lookup"><span data-stu-id="dac34-146">Dual infrastructure</span></span></p></li>
<li><p><span data-ttu-id="dac34-147">服务器管理要求</span><span class="sxs-lookup"><span data-stu-id="dac34-147">Server administration requirement</span></span></p></li>
</ul></td>
<td align="left"><p><a href="how-to-configure-the-application-virtualization-management-servers.md" data-raw-source="[How to Configure the Application Virtualization Management Servers](how-to-configure-the-application-virtualization-management-servers.md)"><span data-ttu-id="dac34-148">如何配置 Application Virtualization Management Server</span><span class="sxs-lookup"><span data-stu-id="dac34-148">How to Configure the Application Virtualization Management Servers</span></span></a></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="dac34-149">相关主题</span><span class="sxs-lookup"><span data-stu-id="dac34-149">Related topics</span></span>


[<span data-ttu-id="dac34-150">基于 Application Virtualization Server 的方案</span><span class="sxs-lookup"><span data-stu-id="dac34-150">Application Virtualization Server-Based Scenario</span></span>](application-virtualization-server-based-scenario.md)

[<span data-ttu-id="dac34-151">Application Virtualization System 组件概述</span><span class="sxs-lookup"><span data-stu-id="dac34-151">Overview of the Application Virtualization System Components</span></span>](overview-of-the-application-virtualization-system-components.md)

[<span data-ttu-id="dac34-152">使用 Application Virtualization Management Server 发布虚拟应用程序</span><span class="sxs-lookup"><span data-stu-id="dac34-152">Publishing Virtual Applications Using Application Virtualization Management Servers</span></span>](publishing-virtual-applications-using-application-virtualization-management-servers.md)

 

 





