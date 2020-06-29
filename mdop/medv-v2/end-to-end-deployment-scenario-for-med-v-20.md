---
title: MED-V 2.0 的端到端部署方案
description: MED-V 2.0 的端到端部署方案
author: dansimp
ms.assetid: 91bb5a9a-5fb1-4743-8494-9d4dee2ec222
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6d56e70ad359ebf2d76cf3f30f54f73cd9ca1c66
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803915"
---
# <span data-ttu-id="4633d-103">MED-V 2.0 的端到端部署方案</span><span class="sxs-lookup"><span data-stu-id="4633d-103">End-to-End Deployment Scenario for MED-V 2.0</span></span>


<span data-ttu-id="4633d-104">Microsoft 企业桌面虚拟化（MED-V）2.0 的此示例方案可帮助你通过端到端使用多个方案来部署你的企业中的 MED-V 组件。</span><span class="sxs-lookup"><span data-stu-id="4633d-104">This sample scenario for Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 helps you deploy the MED-V components in your enterprise by using multiple scenarios end-to-end.</span></span> <span data-ttu-id="4633d-105">你可以将此示例方案视为一个案例研究，可帮助在上下文中放置单个方案和过程。</span><span class="sxs-lookup"><span data-stu-id="4633d-105">You can think of this sample scenario as a case study that helps put the individual scenarios and procedures in context.</span></span>

<span data-ttu-id="4633d-106">本部分提供了将 MED-V 组件部署为企业中的端到端解决方案的基本信息和说明。</span><span class="sxs-lookup"><span data-stu-id="4633d-106">This section provides basic information and directions for deploying MED-V components as an end-to-end solution in your enterprise.</span></span>

## <span data-ttu-id="4633d-107">MED-V 部署分步方案</span><span class="sxs-lookup"><span data-stu-id="4633d-107">MED-V Deployment Step-by-step Scenario</span></span>


<span data-ttu-id="4633d-108">分步方案中的主题包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="4633d-108">The topics in this step-by-step scenario include the following:</span></span>

-   <span data-ttu-id="4633d-109">[Med-v 2.0 支持的配置](med-v-20-supported-configurations.md)讨论了在你的环境中安装和运行 Microsoft 企业桌面虚拟化（med-v）2.0 时必须具备的要求。</span><span class="sxs-lookup"><span data-stu-id="4633d-109">[MED-V 2.0 Supported Configurations](med-v-20-supported-configurations.md) discusses the requirements that you must have to install and run Microsoft Enterprise Desktop Virtualization (MED-V) 2.0in your environment.</span></span> <span data-ttu-id="4633d-110">本主题指定操作系统要求、配置要求和 MED-V 工作区要求。</span><span class="sxs-lookup"><span data-stu-id="4633d-110">This topic specifies the operating system requirements, configuration requirements, and MED-V workspace requirements.</span></span> <span data-ttu-id="4633d-111">本主题还包括有关 MED-V 2.0 支持的语言的本地化信息。</span><span class="sxs-lookup"><span data-stu-id="4633d-111">This topic also includes localization information about the languages that MED-V 2.0 supports.</span></span>

-   <span data-ttu-id="4633d-112">[Med-v 2.0 部署概述](med-v-20-deployment-overview.md)介绍了可帮助你在整个企业中安装和部署 med-v 的常规信息和说明。</span><span class="sxs-lookup"><span data-stu-id="4633d-112">[MED-V 2.0 Deployment Overview](med-v-20-deployment-overview.md) discusses general information and instructions to help you install and deploy MED-V throughout your enterprise.</span></span> <span data-ttu-id="4633d-113">MED-V 组件基于客户端，并且通过使用现有的企业基础结构和进程进行提供和管理。</span><span class="sxs-lookup"><span data-stu-id="4633d-113">The MED-V components are client-based and are delivered and managed by using your existing enterprise infrastructure and processes.</span></span> <span data-ttu-id="4633d-114">本主题概述了 MED-V 解决方案，其中包括有关 MED-V 安装文件和你部署的 MED-V 组件的信息。</span><span class="sxs-lookup"><span data-stu-id="4633d-114">This topic provides an overview of the MED-V solution that includes information about the MED-V installation files and the MED-V components that you deploy.</span></span> <span data-ttu-id="4633d-115">本主题还提供 MED-V 安装和部署过程的高级概述。</span><span class="sxs-lookup"><span data-stu-id="4633d-115">This topic also provides a high-level overview of the MED-V installation and deployment process.</span></span>

-   <span data-ttu-id="4633d-116">[为 Med-v 准备部署环境](prepare-the-deployment-environment-for-med-v.md)讨论如何为 med-v 2.0 部署准备环境。</span><span class="sxs-lookup"><span data-stu-id="4633d-116">[Prepare the Deployment Environment for MED-V](prepare-the-deployment-environment-for-med-v.md) discusses how to prepare your environment for a MED-V 2.0 deployment.</span></span> <span data-ttu-id="4633d-117">本部分介绍了 MED-V 环境所需的先决条件，例如 Microsoft Windows 7 和 Active Directory 基础结构，使用组策略来提供操作系统、应用程序和用户设置的集中管理和配置。</span><span class="sxs-lookup"><span data-stu-id="4633d-117">This section describes the prerequisites that are required for the MED-V environment, such as Microsoft Windows 7 and an Active Directory infrastructure in which you use Group Policy to provide centralized management and configuration of operating systems, applications, and users' settings.</span></span> <span data-ttu-id="4633d-118">本部分还介绍了在整个企业中安装和部署 MED-V 2.0 时必须具备的先决条件，如 Windows 虚拟 PC 和所需的 Windows 虚拟 PC 更新。</span><span class="sxs-lookup"><span data-stu-id="4633d-118">This section also describes the prerequisites that you must have for installing and deploying MED-V 2.0 throughout your enterprise, such as Windows Virtual PC and the required Windows Virtual PC update.</span></span>

-   <span data-ttu-id="4633d-119">[部署 Med-v 组件](deploy-the-med-v-components.md)讨论了在整个企业中安装所有必需的安装文件和 med-v 组件的不同方法。</span><span class="sxs-lookup"><span data-stu-id="4633d-119">[Deploy the MED-V Components](deploy-the-med-v-components.md) discusses the different ways you can install all of the necessary installation files and MED-V components throughout your enterprise.</span></span> <span data-ttu-id="4633d-120">若要安装和部署 MED-V，通常请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="4633d-120">To install and deploy MED-V, you typically follow these steps:</span></span>

    1.  <span data-ttu-id="4633d-121">在将用于构建 MED-V 工作区程序包的管理员计算机上安装**Med-v 工作区包装**程序。</span><span class="sxs-lookup"><span data-stu-id="4633d-121">Install the **MED-V Workspace Packager** on the administrator computer that you will use to build the MED-V workspace packages.</span></span> <span data-ttu-id="4633d-122">有关详细信息，请参阅[如何安装 Med-v 工作区包装程序](how-to-install-the-med-v-workspace-packager.md)。</span><span class="sxs-lookup"><span data-stu-id="4633d-122">For more information, see [How to Install the MED-V Workspace Packager](how-to-install-the-med-v-workspace-packager.md).</span></span>

    2.  <span data-ttu-id="4633d-123">创建和测试你的 MED-V 工作区程序包。</span><span class="sxs-lookup"><span data-stu-id="4633d-123">Create and test your MED-V workspace packages.</span></span> <span data-ttu-id="4633d-124">有关详细信息，请参阅[创建 Med-v 工作区程序包](create-a-med-v-workspace-package.md)和[测试 Med-v 工作区程序包](testing-the-med-v-workspace-package.md)。</span><span class="sxs-lookup"><span data-stu-id="4633d-124">For more information, see [Create a MED-V Workspace Package](create-a-med-v-workspace-package.md) and [Testing the MED-V Workspace Package](testing-the-med-v-workspace-package.md).</span></span>

    3.  <span data-ttu-id="4633d-125">使用贵公司的现有部署应用程序的方法，在整个企业中部署 MED-V。</span><span class="sxs-lookup"><span data-stu-id="4633d-125">Deploy MED-V throughout your enterprise by using your company’s existing method for deploying applications.</span></span> <span data-ttu-id="4633d-126">有关详细信息，请参阅[部署 Med-v 工作区程序包](deploying-the-med-v-workspace-package.md)。</span><span class="sxs-lookup"><span data-stu-id="4633d-126">For more information, see [Deploying the MED-V Workspace Package](deploying-the-med-v-workspace-package.md).</span></span>

## <span data-ttu-id="4633d-127">相关主题</span><span class="sxs-lookup"><span data-stu-id="4633d-127">Related topics</span></span>


[<span data-ttu-id="4633d-128">MED-V 的部署</span><span class="sxs-lookup"><span data-stu-id="4633d-128">Deployment of MED-V</span></span>](deployment-of-med-v.md)

[<span data-ttu-id="4633d-129">MED-V 2.0 的端到端规划方案</span><span class="sxs-lookup"><span data-stu-id="4633d-129">End-to-End Planning Scenario for MED-V 2.0</span></span>](end-to-end-planning-scenario-for-med-v-20.md)

[<span data-ttu-id="4633d-130">MED-V 2.0 的端到端操作方案</span><span class="sxs-lookup"><span data-stu-id="4633d-130">End-to-End Operations Scenario for MED-V 2.0</span></span>](end-to-end-operations-scenario-for-med-v-20.md)

 

 





