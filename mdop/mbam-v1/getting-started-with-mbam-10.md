---
title: MBAM 1.0 入门
description: MBAM 1.0 入门
author: dansimp
ms.assetid: 4fab4e4a-d25e-4661-b235-2b45bf5ac3e4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: e0bbbcabfb25cfc8b24cbb4cbc3d344d4e7f209b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803735"
---
# <span data-ttu-id="a2569-103">MBAM 1.0 入门</span><span class="sxs-lookup"><span data-stu-id="a2569-103">Getting Started with MBAM 1.0</span></span>

> <span data-ttu-id="a2569-104">**重要提示**1.0 年9月14日的 MBAM 将于2021结束。</span><span class="sxs-lookup"><span data-stu-id="a2569-104">**IMPORTANT** MBAM 1.0 will reach end of support on September 14, 2021.</span></span> 
> <span data-ttu-id="a2569-105">有关详细信息，请参阅我们的[生命周期页面](https://support.microsoft.com/lifecycle/search?alpha=Microsoft%20BitLocker%20Administration%20and%20Monitoring%201.0)。</span><span class="sxs-lookup"><span data-stu-id="a2569-105">See our [lifecycle page](https://support.microsoft.com/lifecycle/search?alpha=Microsoft%20BitLocker%20Administration%20and%20Monitoring%201.0) for more information.</span></span> <span data-ttu-id="a2569-106">我们建议[迁移到 MBAM 2.5](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/upgrading-to-mbam-25-or-mbam-25-sp1-from-previous-versions)或其他受支持的 MBAM 版本，或将 BitLocker 管理迁移到[Microsoft 终结点管理器](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)。</span><span class="sxs-lookup"><span data-stu-id="a2569-106">We recommend [migrating to MBAM 2.5](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/upgrading-to-mbam-25-or-mbam-25-sp1-from-previous-versions) or another supported version of MBAM, or migrating your BitLocker management to [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager).</span></span>


<span data-ttu-id="a2569-107">Microsoft BitLocker 管理和监视（MBAM）需要全面规划才能部署它或使用其功能。</span><span class="sxs-lookup"><span data-stu-id="a2569-107">Microsoft BitLocker Administration and Monitoring (MBAM) requires thorough planning before you deploy it or use its features.</span></span> <span data-ttu-id="a2569-108">由于此产品会影响组织中的每台计算机，因此，如果不仔细规划部署，则可能会中断整个网络。</span><span class="sxs-lookup"><span data-stu-id="a2569-108">Because this product can affect every computer in your organization, you might disrupt your entire network if you do not plan your deployment carefully.</span></span> <span data-ttu-id="a2569-109">但是，如果你仔细规划部署并对其进行管理以满足你的业务需求，MBAM 可以帮助降低你的管理开销和总拥有成本。</span><span class="sxs-lookup"><span data-stu-id="a2569-109">However, if you plan your deployment carefully and manage it so that it meets your business needs, MBAM can help reduce your administrative overhead and total cost of ownership.</span></span>

<span data-ttu-id="a2569-110">如果您不熟悉本产品，我们建议您仔细阅读文档。</span><span class="sxs-lookup"><span data-stu-id="a2569-110">If you are new to this product, we recommend that you read the documentation thoroughly.</span></span> <span data-ttu-id="a2569-111">在将其部署到生产环境之前，我们还建议你在测试网络环境中验证你的部署计划。</span><span class="sxs-lookup"><span data-stu-id="a2569-111">Before you deploy it to a production environment, we also recommend that you validate your deployment plan in a test network environment.</span></span> <span data-ttu-id="a2569-112">你还可以考虑获取有关相关技术的类。</span><span class="sxs-lookup"><span data-stu-id="a2569-112">You might also consider taking a class about relevant technologies.</span></span> <span data-ttu-id="a2569-113">有关 Microsoft 培训商机的详细信息，请参阅 Microsoft 培训概述 <https://go.microsoft.com/fwlink/p/?LinkId=80347> 。</span><span class="sxs-lookup"><span data-stu-id="a2569-113">For more information about Microsoft training opportunities, see the Microsoft Training Overview at <https://go.microsoft.com/fwlink/p/?LinkId=80347>.</span></span>

<span data-ttu-id="a2569-114">**注意** 您可以在以下位置找到本文档和 MBAM 评估指南的可下载版本 <https://go.microsoft.com/fwlink/p/?LinkId=225356> 。</span><span class="sxs-lookup"><span data-stu-id="a2569-114">**Note** You can find a downloadable version of this documentation and the MBAM Evaluation Guide at <https://go.microsoft.com/fwlink/p/?LinkId=225356>.</span></span>

 

<span data-ttu-id="a2569-115">本《 MBAM 管理员指南》本部分包含有关 MBAM 的高级信息，在开始部署规划之前，向您提供对产品的基本了解。</span><span class="sxs-lookup"><span data-stu-id="a2569-115">This section of the MBAM Administrator’s Guide includes high-level information about MBAM to provide you with a basic understanding of the product before you begin the deployment planning.</span></span> <span data-ttu-id="a2569-116">其他 MBAM 文档可在 MBAM 文档资源下载页面上找到 <https://go.microsoft.com/fwlink/p/?LinkId=258391> 。</span><span class="sxs-lookup"><span data-stu-id="a2569-116">Additional MBAM documentation can be found on the MBAM Documentation Resources Download page at <https://go.microsoft.com/fwlink/p/?LinkId=258391>.</span></span>

## <span data-ttu-id="a2569-117">MBAM 1.0 入门</span><span class="sxs-lookup"><span data-stu-id="a2569-117">Getting started with MBAM 1.0</span></span>


-   [<span data-ttu-id="a2569-118">关于 MBAM 1.0</span><span class="sxs-lookup"><span data-stu-id="a2569-118">About MBAM 1.0</span></span>](about-mbam-10.md)

    <span data-ttu-id="a2569-119">提供 MBAM 的高级概述以及如何在组织中使用它。</span><span class="sxs-lookup"><span data-stu-id="a2569-119">Provides a high-level overview of MBAM and how it can be used in your organization.</span></span>

-   [<span data-ttu-id="a2569-120">评估 MBAM 1.0</span><span class="sxs-lookup"><span data-stu-id="a2569-120">Evaluating MBAM 1.0</span></span>](evaluating-mbam-10.md)

    <span data-ttu-id="a2569-121">提供有关如何在组织中使用的最佳评估 MBAM 的信息。</span><span class="sxs-lookup"><span data-stu-id="a2569-121">Provides information about how you can best evaluate MBAM for use in your organization.</span></span>

-   [<span data-ttu-id="a2569-122">MBAM 1.0 的高级别体系结构</span><span class="sxs-lookup"><span data-stu-id="a2569-122">High Level Architecture for MBAM 1.0</span></span>](high-level-architecture-for-mbam-10.md)

    <span data-ttu-id="a2569-123">提供 MBAM 功能的说明以及它们如何协同工作。</span><span class="sxs-lookup"><span data-stu-id="a2569-123">Provides a description of the MBAM features and how they work together.</span></span>

-   [<span data-ttu-id="a2569-124">MBAM 1.0 的辅助功能</span><span class="sxs-lookup"><span data-stu-id="a2569-124">Accessibility for MBAM 1.0</span></span>](accessibility-for-mbam-10.md)

    <span data-ttu-id="a2569-125">提供有关使残障人士更易于访问本产品及其相应文档的功能和服务的信息。</span><span class="sxs-lookup"><span data-stu-id="a2569-125">Provides information about features and services that make this product and its corresponding documentation more accessible for people with disabilities.</span></span>

## <a href="" id="other-resources-for-this-product-"></a><span data-ttu-id="a2569-126">此产品的其他资源</span><span class="sxs-lookup"><span data-stu-id="a2569-126">Other resources for this product</span></span>


-   [<span data-ttu-id="a2569-127">Microsoft BitLocker 管理和监视1管理员指南</span><span class="sxs-lookup"><span data-stu-id="a2569-127">Microsoft BitLocker Administration and Monitoring 1 Administrator's Guide</span></span>](index.md)

-   [<span data-ttu-id="a2569-128">计划 MBAM 1.0</span><span class="sxs-lookup"><span data-stu-id="a2569-128">Planning for MBAM 1.0</span></span>](planning-for-mbam-10.md)

-   [<span data-ttu-id="a2569-129">部署 MBAM 1.0</span><span class="sxs-lookup"><span data-stu-id="a2569-129">Deploying MBAM 1.0</span></span>](deploying-mbam-10.md)

-   [<span data-ttu-id="a2569-130">MBAM 1.0 的操作</span><span class="sxs-lookup"><span data-stu-id="a2569-130">Operations for MBAM 1.0</span></span>](operations-for-mbam-10.md)

-   [<span data-ttu-id="a2569-131">MBAM 1.0 疑难解答</span><span class="sxs-lookup"><span data-stu-id="a2569-131">Troubleshooting MBAM 1.0</span></span>](troubleshooting-mbam-10.md)

 

 





