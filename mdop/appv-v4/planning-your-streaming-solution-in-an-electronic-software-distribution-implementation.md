---
title: 在电子软件分发实现中计划流式处理解决方案
description: 在电子软件分发实现中计划流式处理解决方案
author: dansimp
ms.assetid: bc18772a-f169-486f-adb1-7af1a31845aa
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c49d6fc0b5f8f5dee347ead3bb899ce9b0387024
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798855"
---
# <span data-ttu-id="099f3-103">在电子软件分发实现中计划流式处理解决方案</span><span class="sxs-lookup"><span data-stu-id="099f3-103">Planning Your Streaming Solution in an Electronic Software Distribution Implementation</span></span>


<span data-ttu-id="099f3-104">如果您决定将流式处理服务器与 ESD 系统结合使用以使应用程序内容可供您的最终用户计算机使用，则可以从多个备选方案中进行选择，利用任何基础结构已到位。</span><span class="sxs-lookup"><span data-stu-id="099f3-104">If you decide to use streaming servers in conjunction with your ESD system to make application content available to your end user computers, you can choose from several alternatives, taking advantage of whatever infrastructure is already in place.</span></span> <span data-ttu-id="099f3-105">例如，如果 ESD 系统在您的现场分支机构的服务器上有软件分发共享，则可以将应用程序虚拟化 \\CONTENT 共享在这些服务器上，然后将客户端配置为使用该内容共享作为其应用程序内容源。</span><span class="sxs-lookup"><span data-stu-id="099f3-105">For example, if your ESD system has software distribution shares on servers in your field branch offices, you can place the Application Virtualization \\CONTENT share on those servers and then configure the clients to use that content share as their application content source.</span></span> <span data-ttu-id="099f3-106">支持的选项包括使用文件服务器或 IIS 服务器。</span><span class="sxs-lookup"><span data-stu-id="099f3-106">The supported options include using a file server or an IIS server.</span></span> <span data-ttu-id="099f3-107">您也可以在现有文件服务器或 IIS 服务器上安装应用程序虚拟化流服务器。</span><span class="sxs-lookup"><span data-stu-id="099f3-107">You could also install the Application Virtualization Streaming Server on an existing file server or IIS server.</span></span>

<span data-ttu-id="099f3-108">应用程序虚拟化流服务器为应用程序虚拟化中的活动升级功能提供支持。</span><span class="sxs-lookup"><span data-stu-id="099f3-108">The Application Virtualization Streaming Server provides support for the active upgrade feature in Application Virtualization.</span></span> <span data-ttu-id="099f3-109">活动升级功能支持将应用程序的新版本添加到应用程序 V 管理服务器或流服务器，而不会影响当前运行该应用程序的用户。</span><span class="sxs-lookup"><span data-stu-id="099f3-109">The active upgrade feature enables a new version of an application to be added to an App-V Management Server or Streaming Server without affecting users currently running the application.</span></span> <span data-ttu-id="099f3-110">App-v 客户端将在用户下次启动应用程序时从 App-v 管理服务器或流服务器自动接收最新版本的应用程序。</span><span class="sxs-lookup"><span data-stu-id="099f3-110">The App-V clients will automatically receive the latest version of the application from the App-V Management Server or Streaming Server the next time the user starts the application.</span></span> <span data-ttu-id="099f3-111">此功能需要使用 RTSP （S）协议。</span><span class="sxs-lookup"><span data-stu-id="099f3-111">Use of the RTSP(S) protocol is required for this feature.</span></span> <span data-ttu-id="099f3-112">如果你选择不使用应用程序虚拟化流服务器，你将需要使用 ESD 系统显式管理应用程序包升级。</span><span class="sxs-lookup"><span data-stu-id="099f3-112">If you choose not to use the Application Virtualization Streaming Server, you will need to explicitly manage application package upgrades by using the ESD system.</span></span>

<span data-ttu-id="099f3-113">**注意** 对应用程序的访问受 Active Directory 域服务中的安全组的控制，因此你需要为每个虚拟应用程序设置安全组的过程，并为管理每个组中添加的用户制定一个过程。</span><span class="sxs-lookup"><span data-stu-id="099f3-113">**Note** Access to the applications is controlled by means of Security Groups in Active Directory Domain Services, so you will need to plan a process for setting up a security group for each virtual application and for managing which users are added to each group.</span></span> <span data-ttu-id="099f3-114">应用程序虚拟化系统管理员将每个流式服务器配置为使用这些 Active Directory 组，方法是将 Acl 应用于内容共享下的应用程序目录，从而控制对程序包的访问，具体取决于 Active Directory 组成员身份。</span><span class="sxs-lookup"><span data-stu-id="099f3-114">The Application Virtualization system administrator configures each streaming server to use these Active Directory groups by applying ACLs to the application directories under the CONTENT share, which controls access to the packages based on Active Directory group membership.</span></span>

 

<span data-ttu-id="099f3-115">下表汇总了可用的流选项的特征。</span><span class="sxs-lookup"><span data-stu-id="099f3-115">The characteristics of the available streaming options are summarized in the following table.</span></span>

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
<th align="left"><span data-ttu-id="099f3-116">服务器类型</span><span class="sxs-lookup"><span data-stu-id="099f3-116">Server Type</span></span></th>
<th align="left"><span data-ttu-id="099f3-117">协议</span><span class="sxs-lookup"><span data-stu-id="099f3-117">Protocol</span></span></th>
<th align="left"><span data-ttu-id="099f3-118">优点</span><span class="sxs-lookup"><span data-stu-id="099f3-118">Advantages</span></span></th>
<th align="left"><span data-ttu-id="099f3-119">缺点</span><span class="sxs-lookup"><span data-stu-id="099f3-119">Disadvantages</span></span></th>
<th align="left"><span data-ttu-id="099f3-120">Links</span><span class="sxs-lookup"><span data-stu-id="099f3-120">Links</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="099f3-121">文件服务器</span><span class="sxs-lookup"><span data-stu-id="099f3-121">File server</span></span></p></td>
<td align="left"><p><span data-ttu-id="099f3-122">SMB</span><span class="sxs-lookup"><span data-stu-id="099f3-122">SMB</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="099f3-123">通过 \CONTENT 共享配置现有文件服务器的简单的低成本解决方案</span><span class="sxs-lookup"><span data-stu-id="099f3-123">Simple low-cost solution to configure existing file server with \CONTENT share</span></span></p></li>
</ul></td>
<td align="left"><ul>
<li><p><span data-ttu-id="099f3-124">无活动升级</span><span class="sxs-lookup"><span data-stu-id="099f3-124">No active upgrade</span></span></p></li>
</ul></td>
<td align="left"><p><a href="how-to-configure-the-file-server.md" data-raw-source="[How to Configure the File Server](how-to-configure-the-file-server.md)"><span data-ttu-id="099f3-125">如何配置文件服务器</span><span class="sxs-lookup"><span data-stu-id="099f3-125">How to Configure the File Server</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="099f3-126">IIS 服务器</span><span class="sxs-lookup"><span data-stu-id="099f3-126">IIS server</span></span></p></td>
<td align="left"><p><span data-ttu-id="099f3-127">HTTP/HTTPS</span><span class="sxs-lookup"><span data-stu-id="099f3-127">HTTP/ HTTPS</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="099f3-128">支持使用 HTTPS 协议增强的安全性</span><span class="sxs-lookup"><span data-stu-id="099f3-128">Supports enhanced security using HTTPS protocol</span></span></p></li>
<li><p><span data-ttu-id="099f3-129">支持通过 Internet 对远程计算机进行流处理</span><span class="sxs-lookup"><span data-stu-id="099f3-129">Supports streaming to remote computers across the Internet</span></span></p></li>
<li><p><span data-ttu-id="099f3-130">防火墙中只能打开一个端口</span><span class="sxs-lookup"><span data-stu-id="099f3-130">Only one port in firewall to open</span></span></p></li>
<li><p><span data-ttu-id="099f3-131">伸缩</span><span class="sxs-lookup"><span data-stu-id="099f3-131">Scalable</span></span></p></li>
<li><p><span data-ttu-id="099f3-132">熟悉的协议</span><span class="sxs-lookup"><span data-stu-id="099f3-132">Familiar protocol</span></span></p></li>
</ul></td>
<td align="left"><ul>
<li><p><span data-ttu-id="099f3-133">需要管理 IIS</span><span class="sxs-lookup"><span data-stu-id="099f3-133">Need to manage IIS</span></span></p></li>
<li><p><span data-ttu-id="099f3-134">无活动升级</span><span class="sxs-lookup"><span data-stu-id="099f3-134">No active upgrade</span></span></p></li>
</ul></td>
<td align="left"><p><a href="how-to-configure-the-server-for-iis.md" data-raw-source="[How to Configure the Server for IIS](how-to-configure-the-server-for-iis.md)"><span data-ttu-id="099f3-135">如何为 IIS 配置服务器</span><span class="sxs-lookup"><span data-stu-id="099f3-135">How to Configure the Server for IIS</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="099f3-136">应用程序虚拟化流服务器</span><span class="sxs-lookup"><span data-stu-id="099f3-136">Application Virtualization Streaming Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="099f3-137">RTSP/RTSPS</span><span class="sxs-lookup"><span data-stu-id="099f3-137">RTSP/ RTSPS</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="099f3-138">活动升级</span><span class="sxs-lookup"><span data-stu-id="099f3-138">Active upgrade</span></span></p></li>
<li><p><span data-ttu-id="099f3-139">支持使用 RTSPS 协议增强的安全性</span><span class="sxs-lookup"><span data-stu-id="099f3-139">Supports enhanced security using RTSPS protocol</span></span></p></li>
<li><p><span data-ttu-id="099f3-140">防火墙中只能打开一个端口</span><span class="sxs-lookup"><span data-stu-id="099f3-140">Only one port in firewall to open</span></span></p></li>
</ul></td>
<td align="left"><ul>
<li><p><span data-ttu-id="099f3-141">双重基础结构</span><span class="sxs-lookup"><span data-stu-id="099f3-141">Dual infrastructure</span></span></p></li>
<li><p><span data-ttu-id="099f3-142">服务器管理要求</span><span class="sxs-lookup"><span data-stu-id="099f3-142">Server administration requirement</span></span></p></li>
</ul></td>
<td align="left"><p><a href="how-to-configure-the-application-virtualization-management-servers.md" data-raw-source="[How to Configure the Application Virtualization Management Servers](how-to-configure-the-application-virtualization-management-servers.md)"><span data-ttu-id="099f3-143">如何配置 Application Virtualization Management Server</span><span class="sxs-lookup"><span data-stu-id="099f3-143">How to Configure the Application Virtualization Management Servers</span></span></a></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="099f3-144">相关主题</span><span class="sxs-lookup"><span data-stu-id="099f3-144">Related topics</span></span>


[<span data-ttu-id="099f3-145">如何为基于 ESD 的部署配置服务器</span><span class="sxs-lookup"><span data-stu-id="099f3-145">How to Configure Servers for ESD-Based Deployment</span></span>](how-to-configure-servers-for-esd-based-deployment.md)

[<span data-ttu-id="099f3-146">安全和保护概述</span><span class="sxs-lookup"><span data-stu-id="099f3-146">Security and Protection Overview</span></span>](security-and-protection-overview.md)

[<span data-ttu-id="099f3-147">使用电子软件分发发布虚拟应用程序</span><span class="sxs-lookup"><span data-stu-id="099f3-147">Publishing Virtual Applications Using Electronic Software Distribution</span></span>](publishing-virtual-applications-using-electronic-software-distribution.md)

 

 





