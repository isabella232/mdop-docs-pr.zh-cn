---
title: 计划 App-V 5.1 服务器部署
description: 计划 App-V 5.1 服务器部署
author: dansimp
ms.assetid: eedd97c9-bee0-4749-9d1e-ab9528fba398
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 31e3a116eb511356b061e6ccb18c7e25c060a66e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798295"
---
# <span data-ttu-id="5934d-103">计划 App-V 5.1 服务器部署</span><span class="sxs-lookup"><span data-stu-id="5934d-103">Planning for the App-V 5.1 Server Deployment</span></span>


<span data-ttu-id="5934d-104">Microsoft Application Virtualization （App-v） 5.1 server 基础结构包含一组专用功能，这些功能可以基于企业的要求安装在一台或多台服务器计算机上。</span><span class="sxs-lookup"><span data-stu-id="5934d-104">The Microsoft Application Virtualization (App-V) 5.1 server infrastructure consists of a set of specialized features that can be installed on one or more server computers, based on the requirements of the enterprise.</span></span>

## <span data-ttu-id="5934d-105">规划 app-v 5.1 服务器部署</span><span class="sxs-lookup"><span data-stu-id="5934d-105">Planning for App-V 5.1 Server Deployment</span></span>


<span data-ttu-id="5934d-106">App-v 5.1 服务器包含以下功能：</span><span class="sxs-lookup"><span data-stu-id="5934d-106">The App-V 5.1 server consists of the following features:</span></span>

-   <span data-ttu-id="5934d-107">管理服务器-提供 app-v 5.1 基础结构的总体管理功能。</span><span class="sxs-lookup"><span data-stu-id="5934d-107">Management Server – provides overall management functionality for the App-V 5.1 infrastructure.</span></span>

-   <span data-ttu-id="5934d-108">管理数据库-方便了 App-v 5.1 管理的数据库 predeployments。</span><span class="sxs-lookup"><span data-stu-id="5934d-108">Management Database – facilitates database predeployments for App-V 5.1 management.</span></span>

-   <span data-ttu-id="5934d-109">发布服务器-提供虚拟应用程序的托管和流功能。</span><span class="sxs-lookup"><span data-stu-id="5934d-109">Publishing Server – provides hosting and streaming functionality for virtual applications.</span></span>

-   <span data-ttu-id="5934d-110">报表服务器-提供 app-v 5.1 reporting services。</span><span class="sxs-lookup"><span data-stu-id="5934d-110">Reporting Server – provides App-V 5.1 reporting services.</span></span>

-   <span data-ttu-id="5934d-111">报告数据库-为 App-v 5.1 报告简化数据库 predeployments。</span><span class="sxs-lookup"><span data-stu-id="5934d-111">Reporting Database – facilitates database predeployments for App-V 5.1 reporting.</span></span>

<span data-ttu-id="5934d-112">以下列表显示了安装 app-v 5.1 服务器基础结构的推荐方法：</span><span class="sxs-lookup"><span data-stu-id="5934d-112">The following list displays the recommended methods for installing the App-V 5.1 server infrastructure:</span></span>

-   <span data-ttu-id="5934d-113">安装 app-v 5.1 服务器。</span><span class="sxs-lookup"><span data-stu-id="5934d-113">Install the App-V 5.1 server.</span></span> <span data-ttu-id="5934d-114">有关详细信息，请参阅[如何部署 app-v 5.1 服务器](how-to-deploy-the-app-v-51-server.md)。</span><span class="sxs-lookup"><span data-stu-id="5934d-114">For more information, see [How to Deploy the App-V 5.1 Server](how-to-deploy-the-app-v-51-server.md).</span></span>

-   <span data-ttu-id="5934d-115">在单独的计算机上安装数据库、报告和管理功能。</span><span class="sxs-lookup"><span data-stu-id="5934d-115">Install the database, reporting, and management features on separate computers.</span></span> <span data-ttu-id="5934d-116">有关详细信息，请参阅[如何从管理和报告服务在单独的计算机上安装管理和报告数据库](how-to-install-the-management-and-reporting-databases-on-separate-computers-from-the-management-and-reporting-services51.md)。</span><span class="sxs-lookup"><span data-stu-id="5934d-116">For more information, see [How to Install the Management and Reporting Databases on Separate Computers from the Management and Reporting Services](how-to-install-the-management-and-reporting-databases-on-separate-computers-from-the-management-and-reporting-services51.md).</span></span>

-   <span data-ttu-id="5934d-117">使用电子软件分发（ESD）。</span><span class="sxs-lookup"><span data-stu-id="5934d-117">Use Electronic Software Distribution (ESD).</span></span> <span data-ttu-id="5934d-118">有关详细信息，请参阅[如何使用电子软件分发部署 app-v 5.1 程序包](how-to-deploy-app-v-51-packages-using-electronic-software-distribution.md)。</span><span class="sxs-lookup"><span data-stu-id="5934d-118">For more information, see [How to deploy App-V 5.1 Packages Using Electronic Software Distribution](how-to-deploy-app-v-51-packages-using-electronic-software-distribution.md).</span></span>

-   <span data-ttu-id="5934d-119">在一台计算机上安装所有服务器功能。</span><span class="sxs-lookup"><span data-stu-id="5934d-119">Install all server features on a single computer.</span></span>

## <a href="" id="---------app-v-5-1-server-interaction"></a> <span data-ttu-id="5934d-120">App-v 5.1 服务器交互</span><span class="sxs-lookup"><span data-stu-id="5934d-120">App-V 5.1 Server Interaction</span></span>


<span data-ttu-id="5934d-121">本部分包含有关各种 App-v 5.1 服务器角色如何相互交互的信息。</span><span class="sxs-lookup"><span data-stu-id="5934d-121">This section contains information about how the various App-V 5.1 server roles interact with each other.</span></span>

<span data-ttu-id="5934d-122">App-v 5.1 管理服务器包含程序包的存储库及其分配的配置。</span><span class="sxs-lookup"><span data-stu-id="5934d-122">The App-V 5.1 Management Server contains the repository of packages and their assigned configurations.</span></span> <span data-ttu-id="5934d-123">对于注册到管理服务器的发布服务器，在从运行 App-v 5.1 客户端的计算机接收发布刷新请求时，将向发布服务器提供相关联的元数据。</span><span class="sxs-lookup"><span data-stu-id="5934d-123">For Publishing Servers that are registered with the Management Server, the associated metadata is provided to the Publishing servers for use when publishing refresh requests are received from computers running the App-V 5.1 Client.</span></span> <span data-ttu-id="5934d-124">由单个管理服务器管理的 app-v 5.1 发布服务器可以提供不同的客户端，并且可以具有不同的网站名称和端口绑定。</span><span class="sxs-lookup"><span data-stu-id="5934d-124">App-V 5.1 publishing servers managed by a single management server can be serving different clients and can have different website names and port bindings.</span></span> <span data-ttu-id="5934d-125">此外，由同一管理服务器管理的所有发布服务器都是彼此的副本。</span><span class="sxs-lookup"><span data-stu-id="5934d-125">Additionally, all Publishing Servers managed by the same Management Server are replicas of each other.</span></span>

<span data-ttu-id="5934d-126">**注意** 管理服务器不执行任何负载平衡。</span><span class="sxs-lookup"><span data-stu-id="5934d-126">**Note** The Management Server does not perform any load balancing.</span></span> <span data-ttu-id="5934d-127">关联的元数据只会传递到发布服务器，以便在处理客户端请求时使用。</span><span class="sxs-lookup"><span data-stu-id="5934d-127">The associated metadata is simply passed to the publishing server for use when processing client requests.</span></span>

 

## <span data-ttu-id="5934d-128">与服务器相关的协议和外部功能</span><span class="sxs-lookup"><span data-stu-id="5934d-128">Server-Related Protocols and External Features</span></span>


<span data-ttu-id="5934d-129">下面显示了有关 App-v 5.1 服务器使用的服务器相关协议的信息。</span><span class="sxs-lookup"><span data-stu-id="5934d-129">The following displays information about server-related protocols used by the App-V 5.1 servers.</span></span> <span data-ttu-id="5934d-130">该表还包括每种服务器类型的报告机制。</span><span class="sxs-lookup"><span data-stu-id="5934d-130">The table also includes the reporting mechanism for each server type.</span></span>

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
<th align="left"><span data-ttu-id="5934d-131">服务器类型</span><span class="sxs-lookup"><span data-stu-id="5934d-131">Server Type</span></span></th>
<th align="left"><span data-ttu-id="5934d-132">协议</span><span class="sxs-lookup"><span data-stu-id="5934d-132">Protocols</span></span></th>
<th align="left"><span data-ttu-id="5934d-133">需要外部功能</span><span class="sxs-lookup"><span data-stu-id="5934d-133">External Features Needed</span></span></th>
<th align="left"><span data-ttu-id="5934d-134">报告</span><span class="sxs-lookup"><span data-stu-id="5934d-134">Reporting</span></span></th>
<th align="left"></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5934d-135">IIS 服务器</span><span class="sxs-lookup"><span data-stu-id="5934d-135">IIS server</span></span></p></td>
<td align="left"><p><span data-ttu-id="5934d-136">HTTP</span><span class="sxs-lookup"><span data-stu-id="5934d-136">HTTP</span></span></p>
<p><span data-ttu-id="5934d-137">HTTPS</span><span class="sxs-lookup"><span data-stu-id="5934d-137">HTTPS</span></span></p></td>
<td align="left"><p><span data-ttu-id="5934d-138">此服务器协议组合需要一种机制来同步管理服务器和流式处理服务器之间的内容。</span><span class="sxs-lookup"><span data-stu-id="5934d-138">This server-protocol combination requires a mechanism to synchronize the content between the Management Server and the Streaming Server.</span></span> <span data-ttu-id="5934d-139">使用 HTTP 或 HTTPS 时，请使用 IIS 服务器和防火墙保护服务器对 Internet 的暴露。</span><span class="sxs-lookup"><span data-stu-id="5934d-139">When using HTTP or HTTPS, use an IIS server and a firewall to protect the server from exposure to the Internet.</span></span></p></td>
<td align="left"><p><span data-ttu-id="5934d-140">内置</span><span class="sxs-lookup"><span data-stu-id="5934d-140">Internal</span></span></p></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="5934d-141">文件</span><span class="sxs-lookup"><span data-stu-id="5934d-141">File</span></span></p></td>
<td align="left"><p><span data-ttu-id="5934d-142">SMB</span><span class="sxs-lookup"><span data-stu-id="5934d-142">SMB</span></span></p></td>
<td align="left"><p><span data-ttu-id="5934d-143">此服务器协议组合需要支持才能同步管理服务器和流服务器之间的内容。</span><span class="sxs-lookup"><span data-stu-id="5934d-143">This server-protocol combination requires support to synchronize the content between the Management Server and the Streaming Server.</span></span> <span data-ttu-id="5934d-144">使用具有文件共享或流功能的客户端计算机。</span><span class="sxs-lookup"><span data-stu-id="5934d-144">Use a client computer with file sharing or streaming capability.</span></span></p></td>
<td align="left"><p><span data-ttu-id="5934d-145">内置</span><span class="sxs-lookup"><span data-stu-id="5934d-145">Internal</span></span></p></td>
<td align="left"></td>
</tr>
</tbody>
</table>

 






## <span data-ttu-id="5934d-146">相关主题</span><span class="sxs-lookup"><span data-stu-id="5934d-146">Related topics</span></span>


[<span data-ttu-id="5934d-147">计划部署 App-V</span><span class="sxs-lookup"><span data-stu-id="5934d-147">Planning to Deploy App-V</span></span>](planning-to-deploy-app-v51.md)

[<span data-ttu-id="5934d-148">部署 App-V 5.1 Server</span><span class="sxs-lookup"><span data-stu-id="5934d-148">Deploying the App-V 5.1 Server</span></span>](deploying-the-app-v-51-server.md)

 

 





