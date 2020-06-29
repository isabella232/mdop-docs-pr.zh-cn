---
title: 用户体验虚拟化 1.0 入门
description: 用户体验虚拟化 1.0 入门
author: dansimp
ms.assetid: 74a068dc-4f87-4cb4-b114-8ca2a37149f7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 010cefc42c8f2d65ac7f815eff51ec2df42df4d0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804104"
---
# <span data-ttu-id="418e7-103">用户体验虚拟化 1.0 入门</span><span class="sxs-lookup"><span data-stu-id="418e7-103">Getting Started With User Experience Virtualization 1.0</span></span>


<span data-ttu-id="418e7-104">Microsoft 用户体验虚拟化（UE-V）为用户捕获和集中应用程序设置和 Windows 操作系统设置。</span><span class="sxs-lookup"><span data-stu-id="418e7-104">Microsoft User Experience Virtualization (UE-V) captures and centralizes application settings and Windows operating system settings for the user.</span></span> <span data-ttu-id="418e7-105">然后，这些设置将应用于用户访问的不同计算机，包括桌面计算机、便携式计算机和虚拟桌面基础结构（VDI）会话。</span><span class="sxs-lookup"><span data-stu-id="418e7-105">These settings are then applied to the different computers that are accessed by the user, including desktop computers, laptop computers, and virtual desktop infrastructure (VDI) sessions.</span></span>

<span data-ttu-id="418e7-106">UE-V 提供适用于常见 Microsoft 应用程序和 Windows 设置的设置同步。</span><span class="sxs-lookup"><span data-stu-id="418e7-106">UE-V offers settings synchronization for common Microsoft applications and Windows settings.</span></span> <span data-ttu-id="418e7-107">它还可随时将用户设置提供给用户在整个企业中工作的任何地方。</span><span class="sxs-lookup"><span data-stu-id="418e7-107">It also delivers user settings at any time to wherever users work throughout the enterprise.</span></span> <span data-ttu-id="418e7-108">UE-V 允许管理员指定应用程序设置和 Windows 设置漫游。</span><span class="sxs-lookup"><span data-stu-id="418e7-108">UE-V allows administrators to specify which application settings and Windows settings roam.</span></span> <span data-ttu-id="418e7-109">UE-V 可帮助管理员为企业中使用的第三方或业务线应用程序创建自定义设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="418e7-109">UE-V helps administrators to create custom settings location templates for third-party or line-of-business applications that are used in the enterprise.</span></span>

<span data-ttu-id="418e7-110">用户体验虚拟化提供了增强的用户状态虚拟化体验。</span><span class="sxs-lookup"><span data-stu-id="418e7-110">User Experience Virtualization delivers an enhanced user state virtualization experience.</span></span> <span data-ttu-id="418e7-111">在以下情况下，它提供对用户设置的一致性个性化：</span><span class="sxs-lookup"><span data-stu-id="418e7-111">It provides consistent personalization of the user’s settings in the following scenarios:</span></span>

-   <span data-ttu-id="418e7-112">计算机之间的漫游用户应用程序和 Windows 设置。</span><span class="sxs-lookup"><span data-stu-id="418e7-112">Roaming user application and Windows settings between computers.</span></span>

-   <span data-ttu-id="418e7-113">通过使用不同方法部署的应用程序的实例之间的漫游用户设置：</span><span class="sxs-lookup"><span data-stu-id="418e7-113">Roaming user settings between the instances of an application that are deployed by using different methods:</span></span>

    -   <span data-ttu-id="418e7-114">安装的应用程序</span><span class="sxs-lookup"><span data-stu-id="418e7-114">Installed applications</span></span>

    -   <span data-ttu-id="418e7-115">应用程序虚拟化（App-v）已排序的应用程序</span><span class="sxs-lookup"><span data-stu-id="418e7-115">Application Virtualization (App-V) sequenced applications</span></span>

    -   <span data-ttu-id="418e7-116">RemoteApp （远程桌面虚拟化）应用程序</span><span class="sxs-lookup"><span data-stu-id="418e7-116">RemoteApp (Remote Desktop Virtualization) applications</span></span>

-   <span data-ttu-id="418e7-117">在更换、硬件升级或重置映像后恢复计算机的设置。</span><span class="sxs-lookup"><span data-stu-id="418e7-117">Recovering settings for a computer after replacement, hardware upgrade, or reimage.</span></span>

<span data-ttu-id="418e7-118">此产品要求在部署之前进行全面规划或使用其功能。</span><span class="sxs-lookup"><span data-stu-id="418e7-118">This product requires thorough planning before you deploy it or use its features.</span></span> <span data-ttu-id="418e7-119">由于此产品会影响组织中的每台计算机，因此，如果不仔细规划部署，则可能会中断整个网络。</span><span class="sxs-lookup"><span data-stu-id="418e7-119">Because this product can affect every computer in your organization, you might disrupt your entire network if you do not plan your deployment carefully.</span></span> <span data-ttu-id="418e7-120">但是，如果你仔细规划部署并对其进行管理以满足你的业务需求，此产品可以帮助降低你的管理开销和总拥有成本。</span><span class="sxs-lookup"><span data-stu-id="418e7-120">However, if you plan your deployment carefully and manage it so that it meets your business needs, this product can help reduce your administrative overhead and total cost of ownership.</span></span>

<span data-ttu-id="418e7-121">如果您不熟悉本产品，我们建议您仔细阅读文档。</span><span class="sxs-lookup"><span data-stu-id="418e7-121">If you are new to this product, we recommend that you read the documentation carefully.</span></span> <span data-ttu-id="418e7-122">在将产品部署到生产环境之前，我们还建议你在测试网络环境中验证你的部署计划。</span><span class="sxs-lookup"><span data-stu-id="418e7-122">Before you deploy the product to a production environment, we also recommend that you validate your deployment plan in a test network environment.</span></span> <span data-ttu-id="418e7-123">你还可以考虑获取有关相关技术的类。</span><span class="sxs-lookup"><span data-stu-id="418e7-123">You might also consider taking a class about relevant technologies.</span></span> <span data-ttu-id="418e7-124">有关 Microsoft 培训商机的详细信息，请参阅 Microsoft 培训概述 <https://go.microsoft.com/fwlink/p/?LinkId=80347> 。</span><span class="sxs-lookup"><span data-stu-id="418e7-124">For more information about Microsoft training opportunities, see the Microsoft Training Overview at <https://go.microsoft.com/fwlink/p/?LinkId=80347>.</span></span>

<span data-ttu-id="418e7-125">**注意** 此管理员指南的可下载版本不可用。</span><span class="sxs-lookup"><span data-stu-id="418e7-125">**Note** A downloadable version of this administrator’s guide is not available.</span></span> <span data-ttu-id="418e7-126">但是，你可以了解 TechNet 库的特殊模式，这种模式允许你选择文章、将它们分组在一个集合中，或将其打印到文件中 <https://go.microsoft.com/fwlink/?LinkId=272497> （ https://go.microsoft.com/fwlink/?LinkId=272497) 。</span><span class="sxs-lookup"><span data-stu-id="418e7-126">However, you can learn about a special mode of the TechNet Library that allows you to select articles, group them in a collection, and print them or export them to a file at <https://go.microsoft.com/fwlink/?LinkId=272497> (https://go.microsoft.com/fwlink/?LinkId=272497).</span></span>

 

## <span data-ttu-id="418e7-127">Microsoft 用户体验虚拟化主题入门</span><span class="sxs-lookup"><span data-stu-id="418e7-127">Getting started with Microsoft User Experience Virtualization topics</span></span>


-   [<span data-ttu-id="418e7-128">关于用户体验虚拟化 1.0</span><span class="sxs-lookup"><span data-stu-id="418e7-128">About User Experience Virtualization 1.0</span></span>](about-user-experience-virtualization-10.md)

    <span data-ttu-id="418e7-129">介绍用户体验虚拟化的功能和功能。</span><span class="sxs-lookup"><span data-stu-id="418e7-129">Describes the functionality and features of User Experience Virtualization.</span></span>

-   [<span data-ttu-id="418e7-130">UE-V 1.0 的高级别体系结构</span><span class="sxs-lookup"><span data-stu-id="418e7-130">High-Level Architecture for UE-V 1.0</span></span>](high-level-architecture-for-ue-v-10.md)

    <span data-ttu-id="418e7-131">介绍用户体验虚拟化的功能。</span><span class="sxs-lookup"><span data-stu-id="418e7-131">Explains the features of User Experience Virtualization.</span></span>

-   [<span data-ttu-id="418e7-132">Microsoft 用户体验虚拟化 (UE-V) 1.0 发行说明</span><span class="sxs-lookup"><span data-stu-id="418e7-132">Microsoft User Experience Virtualization (UE-V) 1.0 Release Notes</span></span>](microsoft-user-experience-virtualization--ue-v--10-release-notes.md)

    <span data-ttu-id="418e7-133">介绍 UE-V 的已知问题。</span><span class="sxs-lookup"><span data-stu-id="418e7-133">Describes the known issues for UE-V.</span></span>

-   [<span data-ttu-id="418e7-134">UE-V 的辅助功能</span><span class="sxs-lookup"><span data-stu-id="418e7-134">Accessibility for UE-V</span></span>](accessibility-for-ue-v.md)

    <span data-ttu-id="418e7-135">介绍了 UE-V 的键盘快捷方式和辅助功能信息。</span><span class="sxs-lookup"><span data-stu-id="418e7-135">Describes the keyboard shortcuts and accessibility information for UE-V.</span></span>

## <span data-ttu-id="418e7-136">此产品的其他资源</span><span class="sxs-lookup"><span data-stu-id="418e7-136">Other resources for this product</span></span>


-   [<span data-ttu-id="418e7-137">Microsoft 用户体验虚拟化 (UE-V) 1.0</span><span class="sxs-lookup"><span data-stu-id="418e7-137">Microsoft User Experience Virtualization (UE-V) 1.0</span></span>](index.md)

-   [<span data-ttu-id="418e7-138">规划 UE-V 1.0</span><span class="sxs-lookup"><span data-stu-id="418e7-138">Planning for UE-V 1.0</span></span>](planning-for-ue-v-10.md)

-   [<span data-ttu-id="418e7-139">部署 UE-V 1.0</span><span class="sxs-lookup"><span data-stu-id="418e7-139">Deploying UE-V 1.0</span></span>](deploying-ue-v-10.md)

-   [<span data-ttu-id="418e7-140">UE-V 1.0 的操作</span><span class="sxs-lookup"><span data-stu-id="418e7-140">Operations for UE-V 1.0</span></span>](operations-for-ue-v-10.md)

-   [<span data-ttu-id="418e7-141">UE-V 1.0 故障排除</span><span class="sxs-lookup"><span data-stu-id="418e7-141">Troubleshooting UE-V 1.0</span></span>](troubleshooting-ue-v-10.md)

 

 





