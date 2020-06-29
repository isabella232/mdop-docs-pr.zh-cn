---
title: 部署 DaRT 8.0
description: 部署 DaRT 8.0
author: dansimp
ms.assetid: 5a976d4e-3372-4ef6-9095-1b48e99af21b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 7cc847836587abb0eaa22c009c8fd18d0ba0899b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803513"
---
# <span data-ttu-id="30ed1-103">部署 DaRT 8.0</span><span class="sxs-lookup"><span data-stu-id="30ed1-103">Deploying DaRT 8.0</span></span>


<span data-ttu-id="30ed1-104">Microsoft 诊断和恢复工具集（DaRT）8.0 支持多种不同的部署配置。</span><span class="sxs-lookup"><span data-stu-id="30ed1-104">Microsoft Diagnostics and Recovery Toolset (DaRT) 8.0 supports a number of different deployment configurations.</span></span> <span data-ttu-id="30ed1-105">本部分包含有关 DaRT 8.0 和分步过程的部署的信息，这些信息可帮助你成功执行必须在部署的不同阶段完成的任务。</span><span class="sxs-lookup"><span data-stu-id="30ed1-105">This section includes information you should consider about the deployment of DaRT 8.0 and step-by-step procedures to help you successfully perform the tasks that you must complete at different stages of your deployment.</span></span>

## <span data-ttu-id="30ed1-106">部署信息</span><span class="sxs-lookup"><span data-stu-id="30ed1-106">Deployment Information</span></span>


-   [<span data-ttu-id="30ed1-107">将 DaRT 8.0 部署到管理员计算机</span><span class="sxs-lookup"><span data-stu-id="30ed1-107">Deploying DaRT 8.0 to Administrator Computers</span></span>](deploying-dart-80-to-administrator-computers-dart-8.md)

    <span data-ttu-id="30ed1-108">本部分介绍不同的针对你的要求的 DaRT 部署选项，并介绍如何部署它们。</span><span class="sxs-lookup"><span data-stu-id="30ed1-108">This section describes the different DaRT deployment options for your requirements and explains how to deploy them.</span></span>

-   [<span data-ttu-id="30ed1-109">创建 DaRT 8.0 恢复映像</span><span class="sxs-lookup"><span data-stu-id="30ed1-109">Creating the DaRT 8.0 Recovery Image</span></span>](creating-the-dart-80-recovery-image-dart-8.md)

    <span data-ttu-id="30ed1-110">本部分介绍了可用于创建 DaRT 恢复映像的方法，并提供了使用 DaRT 恢复映像向导创建恢复映像的说明。</span><span class="sxs-lookup"><span data-stu-id="30ed1-110">This section describes the methods you can use to create the DaRT recovery image and provides instructions to create the recovery image by using the DaRT Recovery Image wizard.</span></span>

-   [<span data-ttu-id="30ed1-111">部署 DaRT 恢复映像</span><span class="sxs-lookup"><span data-stu-id="30ed1-111">Deploying the DaRT Recovery Image</span></span>](deploying-the-dart-recovery-image-dart-8.md)

    <span data-ttu-id="30ed1-112">本部分提供的信息可帮助你确定针对你的要求的最佳 DaRT 恢复映像部署选项，并提供有关如何部署恢复映像的说明。</span><span class="sxs-lookup"><span data-stu-id="30ed1-112">This section provides information to help you decide on the best DaRT recovery image deployment option for your requirements and provides instructions on how to deploy the recovery image.</span></span>

-   [<span data-ttu-id="30ed1-113">DaRT 8.0 部署清单</span><span class="sxs-lookup"><span data-stu-id="30ed1-113">DaRT 8.0 Deployment Checklist</span></span>](dart-80-deployment-checklist-dart-8.md)

    <span data-ttu-id="30ed1-114">本部分包含可帮助你部署 DaRT 的部署清单。</span><span class="sxs-lookup"><span data-stu-id="30ed1-114">This section contains a deployment checklist that can help you to deploy DaRT.</span></span>

### <span data-ttu-id="30ed1-115">如何获取 DaRT</span><span class="sxs-lookup"><span data-stu-id="30ed1-115">How to get DaRT</span></span>

<span data-ttu-id="30ed1-116">此技术是 Microsoft 桌面优化包（MDOP）的一部分。</span><span class="sxs-lookup"><span data-stu-id="30ed1-116">This technology is a part of the Microsoft Desktop Optimization Pack (MDOP).</span></span> <span data-ttu-id="30ed1-117">企业客户可以通过 Microsoft 软件保障获得 MDOP。</span><span class="sxs-lookup"><span data-stu-id="30ed1-117">Enterprise customers can get MDOP with Microsoft Software Assurance.</span></span> <span data-ttu-id="30ed1-118">有关 Microsoft 软件保证和获取 MDOP 的详细信息，请参阅[如何获取 mdop](https://go.microsoft.com/fwlink/p/?LinkId=322049) （ https://go.microsoft.com/fwlink/p/?LinkId=322049) 。</span><span class="sxs-lookup"><span data-stu-id="30ed1-118">For more information about Microsoft Software Assurance and acquiring MDOP, see [How Do I Get MDOP](https://go.microsoft.com/fwlink/p/?LinkId=322049) (https://go.microsoft.com/fwlink/p/?LinkId=322049).</span></span>

## <span data-ttu-id="30ed1-119">用于部署 DaRT 的其他资源</span><span class="sxs-lookup"><span data-stu-id="30ed1-119">Other Resources for deploying DaRT</span></span>


[<span data-ttu-id="30ed1-120">诊断和恢复工具集8管理员指南</span><span class="sxs-lookup"><span data-stu-id="30ed1-120">Diagnostics and Recovery Toolset 8 Administrator's Guide</span></span>](index.md)

[<span data-ttu-id="30ed1-121">DaRT 8.0 入门</span><span class="sxs-lookup"><span data-stu-id="30ed1-121">Getting Started with DaRT 8.0</span></span>](getting-started-with-dart-80-dart-8.md)

[<span data-ttu-id="30ed1-122">计划 DaRT 8.0</span><span class="sxs-lookup"><span data-stu-id="30ed1-122">Planning for DaRT 8.0</span></span>](planning-for-dart-80-dart-8.md)

[<span data-ttu-id="30ed1-123">DaRT 8.0 的操作</span><span class="sxs-lookup"><span data-stu-id="30ed1-123">Operations for DaRT 8.0</span></span>](operations-for-dart-80-dart-8.md)

[<span data-ttu-id="30ed1-124">DaRT 8.0 疑难解答</span><span class="sxs-lookup"><span data-stu-id="30ed1-124">Troubleshooting DaRT 8.0</span></span>](troubleshooting-dart-80-dart-8.md)

 

 





