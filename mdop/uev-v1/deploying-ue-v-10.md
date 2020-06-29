---
title: 部署 UE-V 1.0
description: 部署 UE-V 1.0
author: dansimp
ms.assetid: 519598bb-8c81-4af7-bee7-357696bff880
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 1a1c515f9be950d8ca7b0a199344d34f7852073d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804110"
---
# <span data-ttu-id="b1add-103">部署 UE-V 1.0</span><span class="sxs-lookup"><span data-stu-id="b1add-103">Deploying UE-V 1.0</span></span>


<span data-ttu-id="b1add-104">Microsoft 用户体验虚拟化（UE-V）有许多不同的部署配置支持。</span><span class="sxs-lookup"><span data-stu-id="b1add-104">There are a number of different deployment configurations that Microsoft User Experience Virtualization (UE-V) supports.</span></span> <span data-ttu-id="b1add-105">本部分包含常规信息和分步过程，可帮助你成功执行必须在部署的不同阶段完成的任务。</span><span class="sxs-lookup"><span data-stu-id="b1add-105">This section includes general information and step-by-step procedures to help you successfully perform the tasks that you must complete at different stages of your deployment.</span></span>

## <span data-ttu-id="b1add-106">UE-V 的部署信息</span><span class="sxs-lookup"><span data-stu-id="b1add-106">Deployment information for UE-V</span></span>


<span data-ttu-id="b1add-107">UE-V 部署要求网络共享上的设置存储位置和在同步设置的每台计算机上安装的 UE-V agent。</span><span class="sxs-lookup"><span data-stu-id="b1add-107">A UE-V deployment requires a settings storage location on a network share and a UE-V agent installed on every computer that synchronizes settings.</span></span> <span data-ttu-id="b1add-108">UE-V 组策略模板可用于管理 UE-V 设置。</span><span class="sxs-lookup"><span data-stu-id="b1add-108">The UE-V Group Policy templates can be used to manage UE-V settings.</span></span> <span data-ttu-id="b1add-109">以下主题介绍了如何部署这些功能。</span><span class="sxs-lookup"><span data-stu-id="b1add-109">The following topics describe how to deploy these features.</span></span>

[<span data-ttu-id="b1add-110">为 UE-V 1.0 部署设置存储位置</span><span class="sxs-lookup"><span data-stu-id="b1add-110">Deploying the Settings Storage Location for UE-V 1.0</span></span>](deploying-the-settings-storage-location-for-ue-v-10.md)

<span data-ttu-id="b1add-111">所有 UE-V 部署都需要一个设置存储位置，其中包含同步设置值的设置包位于该位置。</span><span class="sxs-lookup"><span data-stu-id="b1add-111">All UE-V deployments require a settings storage location where the settings packages that contain the synchronized setting values are located.</span></span>

[<span data-ttu-id="b1add-112">部署 UE-V 代理</span><span class="sxs-lookup"><span data-stu-id="b1add-112">Deploying the UE-V Agent</span></span>](deploying-the-ue-v-agent.md)

<span data-ttu-id="b1add-113">若要使用 UE-V 同步设置，计算机必须安装并运行 UE-V Agent。</span><span class="sxs-lookup"><span data-stu-id="b1add-113">To synchronize settings by using UE-V, a computer must have the UE-V Agent installed and running.</span></span>

[<span data-ttu-id="b1add-114">安装 UE-V 组策略 ADMX 模板</span><span class="sxs-lookup"><span data-stu-id="b1add-114">Installing the UE-V Group Policy ADMX Templates</span></span>](installing-the-ue-v-group-policy-admx-templates.md)

<span data-ttu-id="b1add-115">在部署 UE-V Agent 和标准 UE-V 配置之前，可以使用组策略预配置 UE-V 设置。</span><span class="sxs-lookup"><span data-stu-id="b1add-115">You can use Group Policy to preconfigure UE-V settings before you deploy the UE-V Agent as well as standard UE-V configuration.</span></span>

## <span data-ttu-id="b1add-116">自定义模板部署的部署信息</span><span class="sxs-lookup"><span data-stu-id="b1add-116">Deployment information for custom template deployment</span></span>


<span data-ttu-id="b1add-117">如果你计划为除 UE-V 中包含的 Microsoft 应用程序之外的应用程序（如业务线应用程序）创建自定义设置位置模板，则可以部署设置模板目录，并且必须安装 UE-V 生成器才能创建这些模板。</span><span class="sxs-lookup"><span data-stu-id="b1add-117">If you plan to create custom settings location templates for applications other than the Microsoft applications that are included in UE-V, such as line-of-business applications, then you can deploy a settings template catalog and you must install the UE-V Generator to create those templates.</span></span> <span data-ttu-id="b1add-118">有关详细信息，请参阅[规划用于 ue-v 1.0 的自定义模板部署](planning-for-custom-template-deployment-for-ue-v-10.md)。</span><span class="sxs-lookup"><span data-stu-id="b1add-118">For more information, see [Planning for Custom Template Deployment for UE-V 1.0](planning-for-custom-template-deployment-for-ue-v-10.md).</span></span>

[<span data-ttu-id="b1add-119">安装 UE-V 生成器</span><span class="sxs-lookup"><span data-stu-id="b1add-119">Installing the UE-V Generator</span></span>](installing-the-ue-v-generator.md)

<span data-ttu-id="b1add-120">使用 UE-V 生成器创建、编辑和验证自定义设置位置模板，这些模板有助于同步除默认应用程序之外的应用程序的设置。</span><span class="sxs-lookup"><span data-stu-id="b1add-120">Use the UE-V Generator to create, edit, and validate custom settings location templates that help synchronize settings of applications other than the default applications.</span></span>

[<span data-ttu-id="b1add-121">为 UE-V 1.0 部署设置模板目录</span><span class="sxs-lookup"><span data-stu-id="b1add-121">Deploying the Settings Template Catalog for UE-V 1.0</span></span>](deploying-the-settings-template-catalog-for-ue-v-10.md)

<span data-ttu-id="b1add-122">如果需要部署自定义设置位置模板以支持除 UE-V Agent 中默认应用程序之外的应用程序，必须配置设置模板目录来存储它们。</span><span class="sxs-lookup"><span data-stu-id="b1add-122">If you need to deploy custom settings location templates to support applications other than the default applications in the UE-V Agent, you must configure a settings template catalog to store them.</span></span>

[<span data-ttu-id="b1add-123">为 UE-V 1.0 部署 UE-V 设置位置模板</span><span class="sxs-lookup"><span data-stu-id="b1add-123">Deploying UE-V Settings Location Templates for UE-V 1.0</span></span>](deploying-ue-v-settings-location-templates-for-ue-v-10.md)

<span data-ttu-id="b1add-124">如果你需要在 UE-V Agent 中同步除默认应用程序之外的应用程序，则可以将通过 UE-V 发生器创建的自定义设置位置模板分发到 UE-V 设置模板目录。</span><span class="sxs-lookup"><span data-stu-id="b1add-124">If you need to synchronize applications other than the default applications in the UE-V Agent, the custom setting location templates that are created with UE-V Generator can be distributed to the UE-V settings template catalog.</span></span>

<span data-ttu-id="b1add-125">**注意** 部署自定义模板需要设置模板目录。</span><span class="sxs-lookup"><span data-stu-id="b1add-125">**Note** Deploying custom templates requires a settings template catalog.</span></span> <span data-ttu-id="b1add-126">默认 Microsoft 应用程序模板与 UE-V Agent 一起部署。</span><span class="sxs-lookup"><span data-stu-id="b1add-126">The default Microsoft application templates are deployed with the UE-V Agent.</span></span>

 

## <span data-ttu-id="b1add-127">本产品的主题</span><span class="sxs-lookup"><span data-stu-id="b1add-127">Topics for this product</span></span>


[<span data-ttu-id="b1add-128">Microsoft 用户体验虚拟化 (UE-V) 1.0</span><span class="sxs-lookup"><span data-stu-id="b1add-128">Microsoft User Experience Virtualization (UE-V) 1.0</span></span>](index.md)

[<span data-ttu-id="b1add-129">用户体验虚拟化 1.0 入门</span><span class="sxs-lookup"><span data-stu-id="b1add-129">Getting Started With User Experience Virtualization 1.0</span></span>](getting-started-with-user-experience-virtualization-10.md)

[<span data-ttu-id="b1add-130">规划 UE-V 1.0</span><span class="sxs-lookup"><span data-stu-id="b1add-130">Planning for UE-V 1.0</span></span>](planning-for-ue-v-10.md)

[<span data-ttu-id="b1add-131">UE-V 1.0 的操作</span><span class="sxs-lookup"><span data-stu-id="b1add-131">Operations for UE-V 1.0</span></span>](operations-for-ue-v-10.md)

[<span data-ttu-id="b1add-132">UE-V 1.0 故障排除</span><span class="sxs-lookup"><span data-stu-id="b1add-132">Troubleshooting UE-V 1.0</span></span>](troubleshooting-ue-v-10.md)

 

 





