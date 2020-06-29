---
title: App-V 5.0 的高级别体系结构
description: App-V 5.0 的高级别体系结构
author: dansimp
ms.assetid: fdf8b841-918f-4672-b352-0f2b9519581b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0ec105ffcc3213e488615603484b2de6bafce4d3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798575"
---
# <span data-ttu-id="44b7e-103">App-V 5.0 的高级别体系结构</span><span class="sxs-lookup"><span data-stu-id="44b7e-103">High Level Architecture for App-V 5.0</span></span>


<span data-ttu-id="44b7e-104">使用以下信息可帮助你简化 Microsoft Application Virtualization （App-v）5.0 部署。</span><span class="sxs-lookup"><span data-stu-id="44b7e-104">Use the following information to help you simplify you Microsoft Application Virtualization (App-V) 5.0 deployment.</span></span>

## <span data-ttu-id="44b7e-105">体系结构概述</span><span class="sxs-lookup"><span data-stu-id="44b7e-105">Architecture Overview</span></span>


<span data-ttu-id="44b7e-106">典型的 App-v 5.0 实现由以下元素组成。</span><span class="sxs-lookup"><span data-stu-id="44b7e-106">A typical App-V 5.0 implementation consists of the following elements.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="44b7e-107">元素</span><span class="sxs-lookup"><span data-stu-id="44b7e-107">Element</span></span></th>
<th align="left"><span data-ttu-id="44b7e-108">详细信息</span><span class="sxs-lookup"><span data-stu-id="44b7e-108">More information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="44b7e-109">App-v 5.0 管理服务器</span><span class="sxs-lookup"><span data-stu-id="44b7e-109">App-V 5.0 Management Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="44b7e-110">App-v 5.0 管理服务器为 App-v 5.0 基础结构提供了总体管理功能。</span><span class="sxs-lookup"><span data-stu-id="44b7e-110">The App-V 5.0 Management server provides overall management functionality for the App-V 5.0 infrastructure.</span></span> <span data-ttu-id="44b7e-111">此外，你可以在你的环境中安装多个管理服务器实例，这些实例提供以下好处：</span><span class="sxs-lookup"><span data-stu-id="44b7e-111">Additionally, you can install more than one instance of the management server in your environment which provides the following benefits:</span></span></p>
<ul>
<li><p><span data-ttu-id="44b7e-112">容错和高可用性-在两台单独的计算机上安装和配置 App-v 5.0 管理服务器可帮助在其中一个服务器不可用或脱机时出现的情况。</span><span class="sxs-lookup"><span data-stu-id="44b7e-112">Fault Tolerance and High Availability – Installing and configuring the App-V 5.0 Management server on two separate computers can help in situations when one of the servers is unavailable or offline.</span></span></p>
<p><span data-ttu-id="44b7e-113">您还可以通过在多台计算机上安装管理服务器来帮助提高 App-v 5.0 的可用性。</span><span class="sxs-lookup"><span data-stu-id="44b7e-113">You can also help increase App-V 5.0 availability by installing the Management server on multiple computers.</span></span> <span data-ttu-id="44b7e-114">在此方案中，还应考虑使用网络负载平衡器，以便服务器请求平衡。</span><span class="sxs-lookup"><span data-stu-id="44b7e-114">In this scenario, a network load balancer should also be considered so that server requests are balanced.</span></span></p></li>
<li><p><span data-ttu-id="44b7e-115">可伸缩性-你可以根据需要添加其他管理服务器以支持高负载，例如，你可以在负载平衡器后面安装多台服务器。</span><span class="sxs-lookup"><span data-stu-id="44b7e-115">Scalability – You can add additional management servers as necessary to support a high load, for example you can install multiple servers behind a load balancer.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="44b7e-116">App-v 5.0 发布服务器</span><span class="sxs-lookup"><span data-stu-id="44b7e-116">App-V 5.0 Publishing Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="44b7e-117">App-v 5.0 发布服务器提供虚拟应用程序托管和流式处理的功能。</span><span class="sxs-lookup"><span data-stu-id="44b7e-117">The App-V 5.0 publishing server provides functionality for virtual application hosting and streaming.</span></span> <span data-ttu-id="44b7e-118">发布服务器不需要数据库连接，并且支持下列协议：</span><span class="sxs-lookup"><span data-stu-id="44b7e-118">The publishing server does not require a database connection and supports the following protocols:</span></span></p>
<ul>
<li><p><span data-ttu-id="44b7e-119">HTTP 和 HTTPS</span><span class="sxs-lookup"><span data-stu-id="44b7e-119">HTTP, and HTTPS</span></span></p></li>
</ul>
<p><span data-ttu-id="44b7e-120">您还可以通过在多台计算机上安装发布服务器来帮助提高 App-v 5.0 的可用性。</span><span class="sxs-lookup"><span data-stu-id="44b7e-120">You can also help increase App-V 5.0 availability by installing the Publishing server on multiple computers.</span></span> <span data-ttu-id="44b7e-121">还应考虑网络负载平衡器，以便平衡服务器请求。</span><span class="sxs-lookup"><span data-stu-id="44b7e-121">A network load balancer should also be considered so that server requests are balanced.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="44b7e-122">App-v 5.0 报告服务器</span><span class="sxs-lookup"><span data-stu-id="44b7e-122">App-V 5.0 Reporting Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="44b7e-123">App-v 5.0 报告服务器使授权用户能够运行和查看现有的 app-v 5.0 报告和可帮助他们管理 App-v 5.0 基础结构的特定报表。</span><span class="sxs-lookup"><span data-stu-id="44b7e-123">The App-V 5.0 Reporting server enables authorized users to run and view existing App-V 5.0 reports and ad hoc reports that can help them manage the App-V 5.0 infrastructure.</span></span> <span data-ttu-id="44b7e-124">报表服务器需要连接到 app-v 5.0 报告数据库。</span><span class="sxs-lookup"><span data-stu-id="44b7e-124">The Reporting server requires a connection to the App-V 5.0 reporting database.</span></span> <span data-ttu-id="44b7e-125">你还可以通过在多台计算机上安装报表服务器来帮助提高 App-v 5.0 的可用性。</span><span class="sxs-lookup"><span data-stu-id="44b7e-125">You can also help increase App-V 5.0 availability by installing the Reporting server on multiple computers.</span></span> <span data-ttu-id="44b7e-126">还应考虑网络负载平衡器，以便平衡服务器请求。</span><span class="sxs-lookup"><span data-stu-id="44b7e-126">A network load balancer should also be considered so that server requests are balanced.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="44b7e-127">App-v 5.0 客户端</span><span class="sxs-lookup"><span data-stu-id="44b7e-127">App-V 5.0 Client</span></span></p></td>
<td align="left"><p><span data-ttu-id="44b7e-128">App-v 5.0 客户端支持使用 App-v 5.0 创建的程序包在目标计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="44b7e-128">The App-V 5.0 client enables packages created using App-V 5.0 to run on target computers.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="44b7e-129">**注意** 如果您将 app-v 5.0 与电子软件分发（ESD）配合使用，则不需要使用 app-v 5.0 管理服务器，但是您仍然可以利用 App-v 5.0 的报告功能和流功能。</span><span class="sxs-lookup"><span data-stu-id="44b7e-129">**Note** If you are using App-V 5.0 with Electronic Software Distribution (ESD) you are not required to use the App-V 5.0 Management server, however you can still utilize the reporting and streaming functionality of App-V 5.0.</span></span>

 






## <span data-ttu-id="44b7e-130">相关主题</span><span class="sxs-lookup"><span data-stu-id="44b7e-130">Related topics</span></span>


[<span data-ttu-id="44b7e-131">App-V 5.0 入门</span><span class="sxs-lookup"><span data-stu-id="44b7e-131">Getting Started with App-V 5.0</span></span>](getting-started-with-app-v-50--rtm.md)

 

 





