---
title: MBAM 2.0 入门
description: MBAM 2.0 入门
author: dansimp
ms.assetid: 29f5c9af-5bbf-4d37-aa0f-0716046904af
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 7c683e3d8718da24ebd2164328bda0dab0123037
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803810"
---
# <span data-ttu-id="e3454-103">MBAM 2.0 入门</span><span class="sxs-lookup"><span data-stu-id="e3454-103">Getting Started with MBAM 2.0</span></span>


<span data-ttu-id="e3454-104">在部署 Microsoft BitLockerAdministration 和监视（MBAM）2.0 之前需要进行全面规划，或使用其功能。</span><span class="sxs-lookup"><span data-stu-id="e3454-104">Microsoft BitLockerAdministration and Monitoring(MBAM)2.0 requires thorough planning before you deploy it or use its features.</span></span> <span data-ttu-id="e3454-105">由于此产品会影响组织中的每台计算机，因此，如果不仔细规划部署，则可能会中断整个网络。</span><span class="sxs-lookup"><span data-stu-id="e3454-105">Because this product can affect every computer in your organization, you might disrupt your entire network if you do not plan your deployment carefully.</span></span> <span data-ttu-id="e3454-106">但是，如果你仔细规划部署并对其进行管理以满足你的业务需求，BitLockerAdministration 和监视2.0 可帮助降低你的管理开销和总拥有成本。</span><span class="sxs-lookup"><span data-stu-id="e3454-106">However, if you plan your deployment carefully and manage it so that it meets your business requirements, BitLockerAdministration and Monitoring2.0 can help reduce your administrative overhead and total cost of ownership.</span></span>

<span data-ttu-id="e3454-107">如果您不熟悉本产品，我们建议您仔细阅读文档。</span><span class="sxs-lookup"><span data-stu-id="e3454-107">If you are new to this product, we recommend that you read the documentation carefully.</span></span> <span data-ttu-id="e3454-108">若要获取 MBAM 软件，请参阅[如何获取 MDOP？](https://go.microsoft.com/fwlink/p/?LinkId=322049)。</span><span class="sxs-lookup"><span data-stu-id="e3454-108">To get the MBAM software, see [How Do I Get MDOP?](https://go.microsoft.com/fwlink/p/?LinkId=322049).</span></span> <span data-ttu-id="e3454-109">在将 MBAM 部署到生产环境之前，我们还建议你在测试环境中验证你的部署计划。</span><span class="sxs-lookup"><span data-stu-id="e3454-109">Before you deploy MBAM to a production environment, we also recommend that you validate your deployment plan in a test environment.</span></span> <span data-ttu-id="e3454-110">你还可以考虑获取有关相关技术的类。</span><span class="sxs-lookup"><span data-stu-id="e3454-110">You might also consider taking a class about relevant technologies.</span></span> <span data-ttu-id="e3454-111">有关 Microsoft 培训商机的详细信息，请参阅 Microsoft 培训概述 <https://go.microsoft.com/fwlink/p/?LinkId=80347> 。</span><span class="sxs-lookup"><span data-stu-id="e3454-111">For more information about Microsoft training opportunities, see the Microsoft Training Overview at <https://go.microsoft.com/fwlink/p/?LinkId=80347>.</span></span>

<span data-ttu-id="e3454-112">MBAM 2.0 管理员指南的此部分包含有关 MBAM 2.0 的高级信息，以便在开始规划部署之前提供对产品的基本了解。</span><span class="sxs-lookup"><span data-stu-id="e3454-112">This section of the MBAM2.0 Administrator’s Guide includes high-level information about MBAM2.0 to provide a basic understanding of the product before you begin to plan deployment.</span></span> <span data-ttu-id="e3454-113">有关使用 Configuration Manager 集成拓扑部署 MBAM 的特定信息，请参阅将[MBAM 与 Configuration manager 结合使用](using-mbam-with-configuration-manager.md)。</span><span class="sxs-lookup"><span data-stu-id="e3454-113">For specific information about deploying MBAM with the Configuration Manager integrated topology, see [Using MBAM with Configuration Manager](using-mbam-with-configuration-manager.md).</span></span> <span data-ttu-id="e3454-114">您可以在 "Microsoft BitLocker 管理和监视（MBAM）文档资源下载" 页面上找到其他 MBAM 文档 <https://go.microsoft.com/fwlink/p/?LinkId=258391> 。</span><span class="sxs-lookup"><span data-stu-id="e3454-114">You can find additional MBAM documentation on the Microsoft BitLocker Administration and Monitoring (MBAM) Documentation Resources Download Page at <https://go.microsoft.com/fwlink/p/?LinkId=258391>.</span></span>

## <span data-ttu-id="e3454-115">MBAM 2.0 入门</span><span class="sxs-lookup"><span data-stu-id="e3454-115">Getting Started with MBAM2.0</span></span>


-   [<span data-ttu-id="e3454-116">关于 MBAM 2.0</span><span class="sxs-lookup"><span data-stu-id="e3454-116">About MBAM 2.0</span></span>](about-mbam-20-mbam-2.md)

    <span data-ttu-id="e3454-117">提供 MBAM 2.0 的高级概述，并介绍如何在组织中使用它。</span><span class="sxs-lookup"><span data-stu-id="e3454-117">Provides a high-level overview of MBAM2.0 and describes how it can be used in your organization.</span></span>

-   [<span data-ttu-id="e3454-118">评估 MBAM 2.0</span><span class="sxs-lookup"><span data-stu-id="e3454-118">Evaluating MBAM 2.0</span></span>](evaluating-mbam-20-mbam-2.md)

    <span data-ttu-id="e3454-119">提供有关如何更好地评估 MBAM 2.0 以在组织中使用的信息。</span><span class="sxs-lookup"><span data-stu-id="e3454-119">Provides information about how you can best evaluate MBAM2.0 for use in your organization.</span></span>

-   [<span data-ttu-id="e3454-120">MBAM 2.0 的高级别体系结构</span><span class="sxs-lookup"><span data-stu-id="e3454-120">High-Level Architecture for MBAM 2.0</span></span>](high-level-architecture-for-mbam-20-mbam-2.md)

    <span data-ttu-id="e3454-121">介绍生产环境的 MBAM 2.0 功能和推荐的体系结构。</span><span class="sxs-lookup"><span data-stu-id="e3454-121">Describes the MBAM2.0 features and the recommended architecture for a production environment.</span></span>

-   [<span data-ttu-id="e3454-122">MBAM 2.0 的辅助功能</span><span class="sxs-lookup"><span data-stu-id="e3454-122">Accessibility for MBAM 2.0</span></span>](accessibility-for-mbam-20-mbam-2.md)

    <span data-ttu-id="e3454-123">介绍了可用于 MBAM 2.0 的键盘快捷方式。</span><span class="sxs-lookup"><span data-stu-id="e3454-123">Describes the keyboard shortcuts that are available for MBAM2.0.</span></span>

## <a href="" id="other-resources-for-this-product-"></a><span data-ttu-id="e3454-124">此产品的其他资源</span><span class="sxs-lookup"><span data-stu-id="e3454-124">Other Resources for this Product</span></span>


[<span data-ttu-id="e3454-125">Microsoft BitLocker 管理和监视2管理员指南</span><span class="sxs-lookup"><span data-stu-id="e3454-125">Microsoft BitLocker Administration and Monitoring 2 Administrator's Guide</span></span>](index.md)

[<span data-ttu-id="e3454-126">计划 MBAM 2.0</span><span class="sxs-lookup"><span data-stu-id="e3454-126">Planning for MBAM 2.0</span></span>](planning-for-mbam-20-mbam-2.md)

[<span data-ttu-id="e3454-127">部署 MBAM 2.0</span><span class="sxs-lookup"><span data-stu-id="e3454-127">Deploying MBAM 2.0</span></span>](deploying-mbam-20-mbam-2.md)

[<span data-ttu-id="e3454-128">MBAM 2.0 的操作</span><span class="sxs-lookup"><span data-stu-id="e3454-128">Operations for MBAM 2.0</span></span>](operations-for-mbam-20-mbam-2.md)

[<span data-ttu-id="e3454-129">MBAM 2.0 疑难解答</span><span class="sxs-lookup"><span data-stu-id="e3454-129">Troubleshooting MBAM 2.0</span></span>](troubleshooting-mbam-20-mbam-2.md)

 

 





