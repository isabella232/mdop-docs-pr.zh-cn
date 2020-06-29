---
title: 确定发布方法
description: 确定发布方法
author: dansimp
ms.assetid: 1f2d0d39-5d65-457a-b826-4f45b00c8c85
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9a6b19b12c28ab67e3250909cb32ddb8419f399a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803016"
---
# <span data-ttu-id="082fe-103">确定发布方法</span><span class="sxs-lookup"><span data-stu-id="082fe-103">Determine Your Publishing Method</span></span>


<span data-ttu-id="082fe-104">使用应用程序虚拟化 Sequencer 对应用程序进行排序之后，你需要将该应用程序*发布*给你的用户。</span><span class="sxs-lookup"><span data-stu-id="082fe-104">After you sequence an application by using the Application Virtualization Sequencer, you need to *publish* that application to your users.</span></span> <span data-ttu-id="082fe-105">发布应用程序包括将图标、程序包定义信息和内容源位置提供给安装了应用程序虚拟化客户端的每台计算机。</span><span class="sxs-lookup"><span data-stu-id="082fe-105">Publishing the application consists of delivering the icons, package definition information, and content source location to each computer where the Application Virtualization Client has been installed.</span></span> <span data-ttu-id="082fe-106">下表介绍了使用电子软件分发（ESD）系统部署应用程序虚拟化时支持的发布方法。</span><span class="sxs-lookup"><span data-stu-id="082fe-106">The following table describes publishing methods that are supported when you deploy Application Virtualization by using an electronic software distribution (ESD) system.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="082fe-107">方法</span><span class="sxs-lookup"><span data-stu-id="082fe-107">Method</span></span></th>
<th align="left"><span data-ttu-id="082fe-108">优点</span><span class="sxs-lookup"><span data-stu-id="082fe-108">Advantages</span></span></th>
<th align="left"><span data-ttu-id="082fe-109">缺点</span><span class="sxs-lookup"><span data-stu-id="082fe-109">Disadvantages</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="082fe-110">在排序期间生成 Windows Installer 文件，作为独立的解决方案。</span><span class="sxs-lookup"><span data-stu-id="082fe-110">Generate a Windows Installer file during sequencing, as a stand-alone solution.</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="082fe-111">使用非常简单。</span><span class="sxs-lookup"><span data-stu-id="082fe-111">Very simple to use.</span></span></p></li>
<li><p><span data-ttu-id="082fe-112">程序包在每台计算机上本地加载到缓存中。</span><span class="sxs-lookup"><span data-stu-id="082fe-112">Package loaded into cache locally on each computer.</span></span></p></li>
<li><p><span data-ttu-id="082fe-113">向用户显示的图标。</span><span class="sxs-lookup"><span data-stu-id="082fe-113">Icons displayed to user.</span></span></p></li>
<li><p><span data-ttu-id="082fe-114">与传统软件部署类似。</span><span class="sxs-lookup"><span data-stu-id="082fe-114">Similar to traditional software deployment.</span></span></p></li>
<li><p><span data-ttu-id="082fe-115">无需流式服务器。</span><span class="sxs-lookup"><span data-stu-id="082fe-115">No need for streaming servers.</span></span></p></li>
</ul></td>
<td align="left"><ul>
<li><p><span data-ttu-id="082fe-116">在计算机上的程序包内容的位置没有灵活性——在所有计算机上都有相同的位置。</span><span class="sxs-lookup"><span data-stu-id="082fe-116">No flexibility in location of package contents on computers—same location on all computers.</span></span></p></li>
<li><p><span data-ttu-id="082fe-117">必须仅使用 "添加/删除程序" 或 msiexec 删除应用程序。</span><span class="sxs-lookup"><span data-stu-id="082fe-117">Must use only Add/Remove Programs or msiexec to remove applications.</span></span></p></li>
<li><p><span data-ttu-id="082fe-118">删除和替换更新软件包更新所需的新版本。</span><span class="sxs-lookup"><span data-stu-id="082fe-118">Removal and replacement with new version required for package updating.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="082fe-119">在排序期间生成 Windows Installer 文件，使用模式、加载和 OVERRIDEURL 命令行属性和程序包清单。</span><span class="sxs-lookup"><span data-stu-id="082fe-119">Generate a Windows Installer file during sequencing, used with MODE, LOAD, and OVERRIDEURL command-line properties and the package manifest.</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="082fe-120">使用方便，但灵活性更高。</span><span class="sxs-lookup"><span data-stu-id="082fe-120">Simple to use but with added flexibility.</span></span></p></li>
<li><p><span data-ttu-id="082fe-121">向用户显示的图标。</span><span class="sxs-lookup"><span data-stu-id="082fe-121">Icons displayed to user.</span></span></p></li>
<li><p><span data-ttu-id="082fe-122">可将包含应用程序的 SFT 文件置于流源位置，并且客户端配置为使用该位置。</span><span class="sxs-lookup"><span data-stu-id="082fe-122">SFT file containing the applications can be placed on a streaming source location, with clients configured to use that location.</span></span></p></li>
</ul></td>
<td align="left"><ul>
<li><p><span data-ttu-id="082fe-123">灵活性有限-仅可在运行时控制软件包内容的位置。</span><span class="sxs-lookup"><span data-stu-id="082fe-123">Limited flexibility—only the location of the package content can be controlled at run time.</span></span></p></li>
<li><p><span data-ttu-id="082fe-124">必须仅使用 "添加/删除程序" 或 msiexec 删除应用程序。</span><span class="sxs-lookup"><span data-stu-id="082fe-124">Must use only Add/Remove Programs or msiexec to remove the application.</span></span></p></li>
<li><p><span data-ttu-id="082fe-125">删除和替换更新软件包更新所需的新版本，除非使用流式服务器。</span><span class="sxs-lookup"><span data-stu-id="082fe-125">Removal and replacement with new version required for package updating, unless using streaming server.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="082fe-126">运行 SFTMIME 命令。</span><span class="sxs-lookup"><span data-stu-id="082fe-126">Run SFTMIME commands.</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="082fe-127">全面的灵活性-完全控制所有软件包管理功能。</span><span class="sxs-lookup"><span data-stu-id="082fe-127">Complete flexibility—full control of all package management functions.</span></span></p></li>
</ul></td>
<td align="left"><ul>
<li><p><span data-ttu-id="082fe-128">命令必须经过脚本才能与 ESD 系统配合使用。</span><span class="sxs-lookup"><span data-stu-id="082fe-128">Commands must be scripted for use with the ESD system.</span></span></p></li>
<li><p><span data-ttu-id="082fe-129">必须按正确顺序在每台计算机上运行命令。</span><span class="sxs-lookup"><span data-stu-id="082fe-129">Commands must be run on each computer in correct sequence.</span></span></p></li>
<li><p><span data-ttu-id="082fe-130">详细了解命令语言并仔细规划所需。</span><span class="sxs-lookup"><span data-stu-id="082fe-130">Detailed understanding of command language and careful planning required.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="082fe-131">有关使用这些发布方法的详细信息，请参阅[如何在客户端发布虚拟应用程序](how-to-publish-a-virtual-application-on-the-client.md)。</span><span class="sxs-lookup"><span data-stu-id="082fe-131">For more information about using these publishing methods, see [How to Publish a Virtual Application on the Client](how-to-publish-a-virtual-application-on-the-client.md).</span></span>

## <span data-ttu-id="082fe-132">相关主题</span><span class="sxs-lookup"><span data-stu-id="082fe-132">Related topics</span></span>


[<span data-ttu-id="082fe-133">确定流式处理方法</span><span class="sxs-lookup"><span data-stu-id="082fe-133">Determine Your Streaming Method</span></span>](determine-your-streaming-method.md)

[<span data-ttu-id="082fe-134">基于电子软件分发的方案</span><span class="sxs-lookup"><span data-stu-id="082fe-134">Electronic Software Distribution-Based Scenario</span></span>](electronic-software-distribution-based-scenario.md)

[<span data-ttu-id="082fe-135">基于电子软件分发的方案概述</span><span class="sxs-lookup"><span data-stu-id="082fe-135">Electronic Software Distribution-Based Scenario Overview</span></span>](electronic-software-distribution-based-scenario-overview.md)

[<span data-ttu-id="082fe-136">如何在客户端上发布虚拟应用程序</span><span class="sxs-lookup"><span data-stu-id="082fe-136">How to Publish a Virtual Application on the Client</span></span>](how-to-publish-a-virtual-application-on-the-client.md)

[<span data-ttu-id="082fe-137">SFTMIME 命令引用</span><span class="sxs-lookup"><span data-stu-id="082fe-137">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





