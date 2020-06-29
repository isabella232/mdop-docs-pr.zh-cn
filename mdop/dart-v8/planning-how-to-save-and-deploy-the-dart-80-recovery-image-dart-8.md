---
title: 计划如何保存和部署 DaRT 8.0 恢复映像
description: 计划如何保存和部署 DaRT 8.0 恢复映像
author: dansimp
ms.assetid: 939fbe17-0e30-4c85-8782-5b84d69442a7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2e5cca90c644eb3edf233564c474d2601d4227fa
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802929"
---
# <span data-ttu-id="add45-103">计划如何保存和部署 DaRT 8.0 恢复映像</span><span class="sxs-lookup"><span data-stu-id="add45-103">Planning How to Save and Deploy the DaRT 8.0 Recovery Image</span></span>


<span data-ttu-id="add45-104">你可以使用以下方法保存和部署 Microsoft 诊断和恢复工具集（DaRT）8.0 恢复映像。</span><span class="sxs-lookup"><span data-stu-id="add45-104">You can save and deploy the Microsoft Diagnostics and Recovery Toolset (DaRT) 8.0 recovery image by using the following methods.</span></span> <span data-ttu-id="add45-105">确定你将使用的方法时，请考虑每个方法的优缺点。</span><span class="sxs-lookup"><span data-stu-id="add45-105">When you are determining the method that you will use, consider the advantages and disadvantages of each.</span></span> <span data-ttu-id="add45-106">你还应考虑你的基础结构和支持人员。</span><span class="sxs-lookup"><span data-stu-id="add45-106">You should also consider your infrastructure and support staff.</span></span> <span data-ttu-id="add45-107">如果您有一个小型基础结构，您可能希望使用可移动媒体部署 DaRT 8.0，因为如果将其安装到本地硬盘，恢复映像将始终可用。</span><span class="sxs-lookup"><span data-stu-id="add45-107">If you have a small infrastructure, you might want to deploy DaRT 8.0 by using removable media, since the recovery image will always be available if you install it to the local hard drive.</span></span>

<span data-ttu-id="add45-108">如果你的组织使用 Active Directory 域服务（AD DS），你可能希望使用 Windows DS 将恢复映像部署为网络服务。</span><span class="sxs-lookup"><span data-stu-id="add45-108">If your organization uses Active Directory Domain Services (AD DS), you may want to deploy recovery images as a network service by using Windows DS.</span></span> <span data-ttu-id="add45-109">任何连接的计算机都可以使用恢复图像。</span><span class="sxs-lookup"><span data-stu-id="add45-109">Recovery images are always available to any connected computer.</span></span> <span data-ttu-id="add45-110">你可以从 Windows DS 部署多个映像，并在一个位置维护它们。</span><span class="sxs-lookup"><span data-stu-id="add45-110">You can deploy multiple images from Windows DS and maintain them all in one place.</span></span>

<span data-ttu-id="add45-111">**注意** 您可能希望在您的组织中使用多个方法。</span><span class="sxs-lookup"><span data-stu-id="add45-111">**Note** You may want to use more than one method in your organization.</span></span> <span data-ttu-id="add45-112">例如，在大多数情况下，你可以从远程分区启动到 DaRT，并且在最终用户计算机无法连接到网络时有可用的 USB 闪存驱动器。</span><span class="sxs-lookup"><span data-stu-id="add45-112">For example, you can boot into DaRT from a remote partition for most situations and have a USB flash drive available in case the end-user computer cannot connect to the network.</span></span>

 

<span data-ttu-id="add45-113">下表显示了在组织中使用 DaRT 的每种方法的一些优点和缺点。</span><span class="sxs-lookup"><span data-stu-id="add45-113">The following table shows some advantages and disadvantages of each method of using DaRT in your organization.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="add45-114">启动到 DaRT 的方法</span><span class="sxs-lookup"><span data-stu-id="add45-114">Method to Boot into DaRT</span></span></th>
<th align="left"><span data-ttu-id="add45-115">优点</span><span class="sxs-lookup"><span data-stu-id="add45-115">Advantages</span></span></th>
<th align="left"><span data-ttu-id="add45-116">缺点</span><span class="sxs-lookup"><span data-stu-id="add45-116">Disadvantages</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="add45-117">可移动媒体</span><span class="sxs-lookup"><span data-stu-id="add45-117">Removable Media</span></span></strong></p>
<p><span data-ttu-id="add45-118">恢复映像将写入 CD、DVD 或 USB 驱动器，以使支持人员能够将恢复工具与不稳定的计算机配合使用。</span><span class="sxs-lookup"><span data-stu-id="add45-118">The recovery image is written to a CD, DVD, or USB drive to enable support staff to take the recovery tools with them to the unstable computer.</span></span></p></td>
<td align="left"><p><span data-ttu-id="add45-119">支持主启动记录（MBR）损坏的情况，并且您无法访问硬盘并支持没有网络连接的情况。</span><span class="sxs-lookup"><span data-stu-id="add45-119">Supports scenarios in which the master boot record (MBR) is corrupted and you cannot access the hard disk and supports cases in which there is no network connection.</span></span></p>
<p><span data-ttu-id="add45-120">使你能够创建具有不同工具的多个恢复映像，以提供不同级别的支持。</span><span class="sxs-lookup"><span data-stu-id="add45-120">Enables you to create multiple recovery images with different tools to provide different levels of support.</span></span></p>
<p><span data-ttu-id="add45-121">提供用于将恢复映像刻录到可移动媒体的内置工具。</span><span class="sxs-lookup"><span data-stu-id="add45-121">Provides a built-in tool for burning recovery images to removable media.</span></span></p></td>
<td align="left"><p><span data-ttu-id="add45-122">要求支持人员实际位于最终用户计算机上，以便启动到 DaRT。</span><span class="sxs-lookup"><span data-stu-id="add45-122">Requires that support staff are physically at the end-user computer to boot into DaRT.</span></span></p>
<p><span data-ttu-id="add45-123">需要时间和维护，才能为32位和64位计算机创建具有不同配置的多个媒体。</span><span class="sxs-lookup"><span data-stu-id="add45-123">Requires time and maintenance to create multiple media with different configurations for 32-bit and 64-bit computers.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="add45-124">从远程（网络）分区</span><span class="sxs-lookup"><span data-stu-id="add45-124">From a remote (network) partition</span></span></strong></p>
<p><span data-ttu-id="add45-125">恢复映像位于网络启动服务器（如 Windows 部署服务（Windows DS））上，使用户或支持人员可以按需将其流式传输到计算机。</span><span class="sxs-lookup"><span data-stu-id="add45-125">The recovery image is hosted on a network boot server like Windows Deployment Services (Windows DS), which allows users or support staff to stream it to computers on demand.</span></span></p></td>
<td align="left"><p><span data-ttu-id="add45-126">适用于有权访问网络启动服务器的所有计算机。</span><span class="sxs-lookup"><span data-stu-id="add45-126">Available to all computers that have access to the network boot server.</span></span></p>
<p><span data-ttu-id="add45-127">恢复映像托管在一个中央服务器上，该服务器启用集中更新。</span><span class="sxs-lookup"><span data-stu-id="add45-127">Recovery images are hosted on a central server, which enables centralized updates.</span></span></p>
<p><span data-ttu-id="add45-128">集中式技术支持人员可以通过使用远程连接来提供修复。</span><span class="sxs-lookup"><span data-stu-id="add45-128">Centralized help desk staff can provide repairs by using remote connectivity.</span></span></p>
<p><span data-ttu-id="add45-129">客户端上没有本地存储要求。</span><span class="sxs-lookup"><span data-stu-id="add45-129">No local storage requirement on the clients.</span></span></p>
<p><span data-ttu-id="add45-130">可以创建具有不同工具的多个恢复映像以用于特定的支持级别。</span><span class="sxs-lookup"><span data-stu-id="add45-130">Ability to create multiple recovery images with different tools for specific support levels.</span></span></p></td>
<td align="left"><p><span data-ttu-id="add45-131">需要保护 Windows DS 基础结构，以确保常规用户只能启动 DaRT 恢复映像，而不能启动完整的操作系统成像进程。</span><span class="sxs-lookup"><span data-stu-id="add45-131">The need to secure Windows DS infrastructure to ensure that regular users can start only the DaRT recovery image and not the full operating system imaging process.</span></span></p>
<p></p>
<p></p>
<p><span data-ttu-id="add45-132">要求最终用户计算机在运行时连接到网络。</span><span class="sxs-lookup"><span data-stu-id="add45-132">Requires that the end-user computer is connected to the network at runtime.</span></span></p>
<p><span data-ttu-id="add45-133">要求通过网络进入恢复映像。</span><span class="sxs-lookup"><span data-stu-id="add45-133">Requires that the recovery image is brought across the network.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="add45-134">从本地硬盘上的恢复分区</span><span class="sxs-lookup"><span data-stu-id="add45-134">From a recovery partition on the local hard drive</span></span></strong></p>
<p><span data-ttu-id="add45-135">恢复映像可以手动安装在本地硬盘上，也可以通过使用电子软件分发系统（如 System Center Configuration Manager）进行安装。</span><span class="sxs-lookup"><span data-stu-id="add45-135">The recovery image is installed on a local hard drive either manually or by using electronic software distribution systems like System Center Configuration Manager.</span></span></p></td>
<td align="left"><p><span data-ttu-id="add45-136">恢复映像始终可用，因为它是在计算机上预暂存的。</span><span class="sxs-lookup"><span data-stu-id="add45-136">The recovery image is always available because it is pre-staged on the computer.</span></span></p>
<p><span data-ttu-id="add45-137">集中的技术支持人员可通过使用远程连接提供支持。</span><span class="sxs-lookup"><span data-stu-id="add45-137">Centralized help desk staff can provide support by using Remote Connection.</span></span></p>
<p><span data-ttu-id="add45-138">恢复映像是集中管理和部署的。</span><span class="sxs-lookup"><span data-stu-id="add45-138">The recovery image is centrally managed and deployed.</span></span></p>
<p><span data-ttu-id="add45-139">已消除受 Windows BitLocker 驱动器加密保护的计算机上的其他恢复密钥请求。</span><span class="sxs-lookup"><span data-stu-id="add45-139">Additional recovery key requests on computers that are protected by Windows BitLocker drive encryption are eliminated.</span></span></p></td>
<td align="left"><p><span data-ttu-id="add45-140">需要本地存储。</span><span class="sxs-lookup"><span data-stu-id="add45-140">Local storage is required.</span></span></p>
<p><span data-ttu-id="add45-141">建议使用专用的未加密分区来放置恢复映像，以降低启动分区出现故障的风险。</span><span class="sxs-lookup"><span data-stu-id="add45-141">A dedicated, unencrypted partition for recovery image placement is recommended to reduce the risk of a failed boot partition.</span></span></p>
<p><span data-ttu-id="add45-142">更新 DaRT 时，必须更新企业中的所有计算机，而不是只更新一个分区（在网络上）或可移动设备。</span><span class="sxs-lookup"><span data-stu-id="add45-142">When updating DaRT, you must update all computers in your enterprise instead of just one partition (on the network) or removable device.</span></span></p>
<p><span data-ttu-id="add45-143">如果在启用 BitLocker 后部署恢复映像，则需要其他注意事项。</span><span class="sxs-lookup"><span data-stu-id="add45-143">Additional consideration is required if you deploy the recovery image after BitLocker has been enabled.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="add45-144">相关主题</span><span class="sxs-lookup"><span data-stu-id="add45-144">Related topics</span></span>


[<span data-ttu-id="add45-145">计划部署 DaRT 8.0</span><span class="sxs-lookup"><span data-stu-id="add45-145">Planning to Deploy DaRT 8.0</span></span>](planning-to-deploy-dart-80-dart-8.md)

 

 





