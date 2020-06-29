---
title: 计划如何保存和部署 DaRT 7.0 恢复映像
description: 计划如何保存和部署 DaRT 7.0 恢复映像
author: dansimp
ms.assetid: d96e9363-6186-4fc3-9b83-ba15ed9694a5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c292633949865d4b3f5053700f4219db3f1cf465
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803240"
---
# <span data-ttu-id="2ce89-103">计划如何保存和部署 DaRT 7.0 恢复映像</span><span class="sxs-lookup"><span data-stu-id="2ce89-103">Planning How to Save and Deploy the DaRT 7.0 Recovery Image</span></span>


<span data-ttu-id="2ce89-104">如果你计划保存和部署 Microsoft 诊断和恢复工具集（DaRT）7恢复映像，请使用本部分中的信息。</span><span class="sxs-lookup"><span data-stu-id="2ce89-104">Use the information in this section when you plan for saving and deploying the Microsoft Diagnostics and Recovery Toolset (DaRT)7 recovery image.</span></span>

## <span data-ttu-id="2ce89-105">规划如何保存和部署 DaRT 恢复映像</span><span class="sxs-lookup"><span data-stu-id="2ce89-105">Planning How to Save and Deploy the DaRT Recovery Image</span></span>


<span data-ttu-id="2ce89-106">你可以使用以下方法保存和部署 DaRT 恢复映像。</span><span class="sxs-lookup"><span data-stu-id="2ce89-106">You can save and deploy the DaRT recovery image by using the following methods.</span></span> <span data-ttu-id="2ce89-107">确定你将使用的方法时，请考虑每个方法的优缺点。</span><span class="sxs-lookup"><span data-stu-id="2ce89-107">When you are determining the method that you will use, consider the advantages and disadvantages of each.</span></span> <span data-ttu-id="2ce89-108">此外，请考虑你希望如何在企业中使用 DaRT。</span><span class="sxs-lookup"><span data-stu-id="2ce89-108">Also, consider how you want to use DaRT in your enterprise.</span></span>

<span data-ttu-id="2ce89-109">**注意** 您可能希望在您的组织中使用多个方法。</span><span class="sxs-lookup"><span data-stu-id="2ce89-109">**Note** You might want to use more than one method in your organization.</span></span> <span data-ttu-id="2ce89-110">例如，在大多数情况下，你可以从远程分区启动到 DaRT，并且在最终用户计算机无法连接到网络时有可用的 USB 闪存驱动器。</span><span class="sxs-lookup"><span data-stu-id="2ce89-110">For example, you can boot into DaRT from a remote partition for most situations and have a USB flash drive available in case the end-user computer cannot connect to the network.</span></span>

 

<span data-ttu-id="2ce89-111">下表显示了在组织中使用 DaRT 的每种方法的一些优点和缺点。</span><span class="sxs-lookup"><span data-stu-id="2ce89-111">The following table shows some advantages and disadvantages of each method of using DaRT in your organization.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="2ce89-112">启动到 DaRT 的方法</span><span class="sxs-lookup"><span data-stu-id="2ce89-112">Method to Boot into DaRT</span></span></th>
<th align="left"><span data-ttu-id="2ce89-113">优点</span><span class="sxs-lookup"><span data-stu-id="2ce89-113">Advantages</span></span></th>
<th align="left"><span data-ttu-id="2ce89-114">缺点</span><span class="sxs-lookup"><span data-stu-id="2ce89-114">Disadvantages</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2ce89-115">从 CD 或 DVD</span><span class="sxs-lookup"><span data-stu-id="2ce89-115">From a CD or DVD</span></span></p></td>
<td align="left"><p><span data-ttu-id="2ce89-116">支持主启动记录（MBR）损坏且无法访问硬盘的方案。</span><span class="sxs-lookup"><span data-stu-id="2ce89-116">Supports scenarios in which the master boot record (MBR) is corrupted and you cannot access the hard disk.</span></span> <span data-ttu-id="2ce89-117">还支持没有网络连接的情况。</span><span class="sxs-lookup"><span data-stu-id="2ce89-117">Also supports cases in which there is no network connection.</span></span></p>
<p><span data-ttu-id="2ce89-118">较早版本的 DaRT 的用户最熟悉此功能，并且可以直接从 <strong> DaRT 恢复映像向导刻录 CD 或 DVD </strong> 。</span><span class="sxs-lookup"><span data-stu-id="2ce89-118">This is most familiar to users of earlier versions of DaRT, and a CD or DVD can be burned directly from the <strong>DaRT Recovery Image Wizard</strong>.</span></span></p></td>
<td align="left"><p><span data-ttu-id="2ce89-119">要求有权访问 CD 或 DVD 的人在最终用户计算机上物理地启动到 DaRT。</span><span class="sxs-lookup"><span data-stu-id="2ce89-119">Requires that someone with access to the CD or DVD is physically at the end-user computer to boot into DaRT.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2ce89-120">从 u 盘（UFD）</span><span class="sxs-lookup"><span data-stu-id="2ce89-120">From a USB flash drive (UFD)</span></span></p></td>
<td align="left"><p><span data-ttu-id="2ce89-121">提供与从 CD 或 DVD 启动同样的优势，并且还提供对没有 CD 或 DVD 驱动器的计算机的支持。</span><span class="sxs-lookup"><span data-stu-id="2ce89-121">Provides same advantages as booting from a CD or DVD and also provides support to computers that have no CD or DVD drive.</span></span></p></td>
<td align="left"><p><span data-ttu-id="2ce89-122">需要先设置 UFD 的格式，然后才能使用它启动到 DaRT。</span><span class="sxs-lookup"><span data-stu-id="2ce89-122">Requires you to format the UFD before you can use it to boot into DaRT.</span></span> <span data-ttu-id="2ce89-123">还要求有权访问 UFD 的人在物理位置位于最终用户计算机上，以便启动到 DaRT。</span><span class="sxs-lookup"><span data-stu-id="2ce89-123">Also requires that someone with access to the UFD is physically at the end-user computer to boot into DaRT.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2ce89-124">从远程（网络）分区</span><span class="sxs-lookup"><span data-stu-id="2ce89-124">From a remote (network) partition</span></span></p></td>
<td align="left"><p><span data-ttu-id="2ce89-125">允许你在不需要 CD、DVD 或 UFD 的情况下启动到 DaRT。</span><span class="sxs-lookup"><span data-stu-id="2ce89-125">Lets you boot into DaRT without needing a CD, DVD, or UFD.</span></span> <span data-ttu-id="2ce89-126">还允许轻松升级 DaRT，因为只有一个文件位置需要更新。</span><span class="sxs-lookup"><span data-stu-id="2ce89-126">Also allows for easy upgrades of DaRT because there is only one file location to update.</span></span></p></td>
<td align="left"><p><span data-ttu-id="2ce89-127">如果最终用户计算机未连接到网络，则不起作用。</span><span class="sxs-lookup"><span data-stu-id="2ce89-127">Does not work if the end-user computer is not connected to the network.</span></span></p>
<p><span data-ttu-id="2ce89-128">对最终用户广泛可用，并且在创建恢复映像时可能需要其他安全注意事项。</span><span class="sxs-lookup"><span data-stu-id="2ce89-128">Widely available to end users and might require additional security considerations when you are creating the recovery image.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2ce89-129">从恢复分区</span><span class="sxs-lookup"><span data-stu-id="2ce89-129">From a recovery partition</span></span></p></td>
<td align="left"><p><span data-ttu-id="2ce89-130">让你可以启动到 DaRT，无需安装 CD、DVD 或 UFD，包括没有网络连接的实例。</span><span class="sxs-lookup"><span data-stu-id="2ce89-130">Lets you boot into DaRT without needing a CD, DVD, or UFD that includes instances in which there is no network connectivity.</span></span></p>
<p><span data-ttu-id="2ce89-131">此外，还可以通过使用自动化分发工具（如 Microsoft 终结点配置管理器）来实现和管理作为标准 Windows 映像过程的一部分。</span><span class="sxs-lookup"><span data-stu-id="2ce89-131">Also, can be implemented and managed as part of your standard Windows image process by using automated distribution tools, such as Microsoft Endpoint Configuration Manager.</span></span></p></td>
<td align="left"><p><span data-ttu-id="2ce89-132">更新 DaRT 时，需要更新企业中的所有计算机，而不是只更新一个分区（在网络上）或设备（CD、DVD 或 UFD）。</span><span class="sxs-lookup"><span data-stu-id="2ce89-132">When updating DaRT, requires you to update all computers in your enterprise instead of just one partition (on the network) or device (CD, DVD, or UFD).</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="2ce89-133">相关主题</span><span class="sxs-lookup"><span data-stu-id="2ce89-133">Related topics</span></span>


[<span data-ttu-id="2ce89-134">计划部署 DaRT 7.0</span><span class="sxs-lookup"><span data-stu-id="2ce89-134">Planning to Deploy DaRT 7.0</span></span>](planning-to-deploy-dart-70.md)

 

 





