---
title: 确定流式处理方法
description: 确定流式处理方法
author: dansimp
ms.assetid: 50d5e0ec-7f48-4cea-8711-5882bd89153b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0acfd345ac55f11476cffe94b3a95b13c5d8f303
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803014"
---
# <span data-ttu-id="ce04c-103">确定流式处理方法</span><span class="sxs-lookup"><span data-stu-id="ce04c-103">Determine Your Streaming Method</span></span>


<span data-ttu-id="ce04c-104">用户首次双击已通过发布过程放置在计算机上的图标时，应用程序虚拟化客户端将从流源位置获取虚拟应用程序包内容。</span><span class="sxs-lookup"><span data-stu-id="ce04c-104">The first time that a user double-clicks the icon that has been placed on a computer through the publishing process, the Application Virtualization client will obtain the virtual application package content from a streaming source location.</span></span>

<span data-ttu-id="ce04c-105">**注意** 
*流*是用于描述从顺序应用程序包获取内容的过程的术语，从主功能块开始，然后根据需要获取其他块。</span><span class="sxs-lookup"><span data-stu-id="ce04c-105">**Note**
*Streaming* is the term used to describe the process of obtaining content from a sequenced application package, starting with the primary feature block and then obtaining additional blocks as needed.</span></span>

 

<span data-ttu-id="ce04c-106">流源位置通常是可由用户计算机访问的服务器;但是，某些电子分发系统（如 Microsoft 终结点配置管理器）可以将 SFT 文件分发到用户的计算机，然后从该计算机的缓存中本地传输虚拟应用程序包。</span><span class="sxs-lookup"><span data-stu-id="ce04c-106">The streaming source location is usually a server that is accessible by the user’s computer; however, some electronic distribution systems, such as Microsoft Endpoint Configuration Manager, can distribute the SFT file to the user’s computer and then stream the virtual application package locally from that computer’s cache.</span></span>

<span data-ttu-id="ce04c-107">**注意** 可以在非服务器计算机上设置虚拟包的流源位置。</span><span class="sxs-lookup"><span data-stu-id="ce04c-107">**Note** A streaming source location for virtual packages can be set up on a computer that is not a server.</span></span> <span data-ttu-id="ce04c-108">这在没有服务器的小型分支机构中尤其有用。</span><span class="sxs-lookup"><span data-stu-id="ce04c-108">This is especially useful in a small branch office that has no server.</span></span>

 

<span data-ttu-id="ce04c-109">下表介绍了可用于存储排序应用程序的流式处理源。</span><span class="sxs-lookup"><span data-stu-id="ce04c-109">The streaming sources that can be used to store sequenced applications are described in the following table.</span></span>

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
<th align="left"><span data-ttu-id="ce04c-110">服务器类型</span><span class="sxs-lookup"><span data-stu-id="ce04c-110">Server Type</span></span></th>
<th align="left"><span data-ttu-id="ce04c-111">协议</span><span class="sxs-lookup"><span data-stu-id="ce04c-111">Protocol</span></span></th>
<th align="left"><span data-ttu-id="ce04c-112">优点</span><span class="sxs-lookup"><span data-stu-id="ce04c-112">Advantages</span></span></th>
<th align="left"><span data-ttu-id="ce04c-113">缺点</span><span class="sxs-lookup"><span data-stu-id="ce04c-113">Disadvantages</span></span></th>
<th align="left"><span data-ttu-id="ce04c-114">Links</span><span class="sxs-lookup"><span data-stu-id="ce04c-114">Links</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ce04c-115">文件服务器</span><span class="sxs-lookup"><span data-stu-id="ce04c-115">File server</span></span></p></td>
<td align="left"><p><span data-ttu-id="ce04c-116">文件</span><span class="sxs-lookup"><span data-stu-id="ce04c-116">File</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="ce04c-117">通过 \CONTENT 共享配置现有文件服务器的简单的低成本解决方案</span><span class="sxs-lookup"><span data-stu-id="ce04c-117">Simple low-cost solution to configure existing file server with \CONTENT share</span></span></p></li>
</ul></td>
<td align="left"><ul>
<li><p><span data-ttu-id="ce04c-118">无活动升级</span><span class="sxs-lookup"><span data-stu-id="ce04c-118">No active upgrade</span></span></p></li>
</ul></td>
<td align="left"><p><a href="how-to-configure-the-file-server.md" data-raw-source="[How to Configure the File Server](how-to-configure-the-file-server.md)"><span data-ttu-id="ce04c-119">如何配置文件服务器</span><span class="sxs-lookup"><span data-stu-id="ce04c-119">How to Configure the File Server</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ce04c-120">IIS 服务器</span><span class="sxs-lookup"><span data-stu-id="ce04c-120">IIS server</span></span></p></td>
<td align="left"><p><span data-ttu-id="ce04c-121">HTTP/HTTPS</span><span class="sxs-lookup"><span data-stu-id="ce04c-121">HTTP/ HTTPS</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="ce04c-122">支持使用 HTTPS 协议增强的安全性。</span><span class="sxs-lookup"><span data-stu-id="ce04c-122">Supports enhanced security using HTTPS protocol.</span></span></p></li>
<li><p><span data-ttu-id="ce04c-123">支持通过 Internet 对远程计算机进行流处理</span><span class="sxs-lookup"><span data-stu-id="ce04c-123">Supports streaming to remote computers across the Internet</span></span></p></li>
<li><p><span data-ttu-id="ce04c-124">防火墙中只能打开一个端口</span><span class="sxs-lookup"><span data-stu-id="ce04c-124">Only one port in firewall to open</span></span></p></li>
<li><p><span data-ttu-id="ce04c-125">高度可扩展</span><span class="sxs-lookup"><span data-stu-id="ce04c-125">Highly scalable</span></span></p></li>
<li><p><span data-ttu-id="ce04c-126">熟悉的协议</span><span class="sxs-lookup"><span data-stu-id="ce04c-126">Familiar protocol</span></span></p></li>
</ul></td>
<td align="left"><ul>
<li><p><span data-ttu-id="ce04c-127">需要管理 IIS</span><span class="sxs-lookup"><span data-stu-id="ce04c-127">Need to manage IIS</span></span></p></li>
<li><p><span data-ttu-id="ce04c-128">无活动升级</span><span class="sxs-lookup"><span data-stu-id="ce04c-128">No active upgrade</span></span></p></li>
</ul></td>
<td align="left"><p><a href="how-to-configure-the-server-for-iis.md" data-raw-source="[How to Configure the Server for IIS](how-to-configure-the-server-for-iis.md)"><span data-ttu-id="ce04c-129">如何为 IIS 配置服务器</span><span class="sxs-lookup"><span data-stu-id="ce04c-129">How to Configure the Server for IIS</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ce04c-130">应用程序虚拟化流服务器</span><span class="sxs-lookup"><span data-stu-id="ce04c-130">Application Virtualization Streaming Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="ce04c-131">RTSP/RTSPS</span><span class="sxs-lookup"><span data-stu-id="ce04c-131">RTSP/ RTSPS</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="ce04c-132">活动升级</span><span class="sxs-lookup"><span data-stu-id="ce04c-132">Active upgrade</span></span></p></li>
<li><p><span data-ttu-id="ce04c-133">支持使用 RTSPS 协议增强的安全性</span><span class="sxs-lookup"><span data-stu-id="ce04c-133">Supports enhanced security using RTSPS protocol</span></span></p></li>
<li><p><span data-ttu-id="ce04c-134">仅在防火墙中打开一个端口（仅限 RTSPS）</span><span class="sxs-lookup"><span data-stu-id="ce04c-134">Only one port in firewall to open (RTSPS only)</span></span></p></li>
</ul></td>
<td align="left"><ul>
<li><p><span data-ttu-id="ce04c-135">双重基础结构</span><span class="sxs-lookup"><span data-stu-id="ce04c-135">Dual infrastructure</span></span></p></li>
<li><p><span data-ttu-id="ce04c-136">服务器管理要求</span><span class="sxs-lookup"><span data-stu-id="ce04c-136">Server administration requirement</span></span></p></li>
</ul></td>
<td align="left"><p><a href="how-to-configure-the-application-virtualization-management-servers.md" data-raw-source="[How to Configure the Application Virtualization Management Servers](how-to-configure-the-application-virtualization-management-servers.md)"><span data-ttu-id="ce04c-137">如何配置 Application Virtualization Management Server</span><span class="sxs-lookup"><span data-stu-id="ce04c-137">How to Configure the Application Virtualization Management Servers</span></span></a></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="ce04c-138">相关主题</span><span class="sxs-lookup"><span data-stu-id="ce04c-138">Related topics</span></span>


[<span data-ttu-id="ce04c-139">基于电子软件分发的方案</span><span class="sxs-lookup"><span data-stu-id="ce04c-139">Electronic Software Distribution-Based Scenario</span></span>](electronic-software-distribution-based-scenario.md)

[<span data-ttu-id="ce04c-140">基于电子软件分发的方案概述</span><span class="sxs-lookup"><span data-stu-id="ce04c-140">Electronic Software Distribution-Based Scenario Overview</span></span>](electronic-software-distribution-based-scenario-overview.md)

[<span data-ttu-id="ce04c-141">确定发布方法</span><span class="sxs-lookup"><span data-stu-id="ce04c-141">Determine Your Publishing Method</span></span>](determine-your-publishing-method.md)

 

 





