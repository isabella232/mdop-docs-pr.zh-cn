---
title: 定义项目范围
description: 定义项目范围
author: dansimp
ms.assetid: 84637d2a-2e30-417d-b150-dc81f414b3a5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4f33562452327bba9036f56d9f6f96650f00c1f0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803409"
---
# <span data-ttu-id="eb27e-103">定义项目范围</span><span class="sxs-lookup"><span data-stu-id="eb27e-103">Define the Project Scope</span></span>


<span data-ttu-id="eb27e-104">定义项目范围时，请确定以下事项：</span><span class="sxs-lookup"><span data-stu-id="eb27e-104">When defining the project scope, determine the following:</span></span>

1.  <span data-ttu-id="eb27e-105">MED-V 最终用户—最终用户的位置和数量用于确定 MED-V 客户端安装的位置和 med-v 实例的数量，以及 MED-V 图像存储库的数量和位置的位置。</span><span class="sxs-lookup"><span data-stu-id="eb27e-105">The MED-V end users—the location and number of end users are used in determining the location of MED-V client installations and the number of MED-V instances, as well as the number and placement of MED-V image repositories.</span></span>

2.  <span data-ttu-id="eb27e-106">由 MED-V 管理的虚拟机（VM）映像，用于确定分发图像和放置图像存储库的方法。</span><span class="sxs-lookup"><span data-stu-id="eb27e-106">The virtual machine (VM) images to be managed by MED-V—to determine the method of distributing images and placement of image repositories.</span></span>

3.  <span data-ttu-id="eb27e-107">组织的服务级别期望值-确定 MED-V 服务器和数据库以及映像存储库的性能和容错要求。</span><span class="sxs-lookup"><span data-stu-id="eb27e-107">The organization’s service level expectations—to determine the performance and fault-tolerance requirements for the MED-V server and database as well as the image repository.</span></span>

4.  <span data-ttu-id="eb27e-108">与业务部门进行验证-确保有完整地了解计划的基础结构对企业有何影响。</span><span class="sxs-lookup"><span data-stu-id="eb27e-108">Validate with the business—ensure there is a complete understanding of how the planned infrastructure affects the business.</span></span>

## <span data-ttu-id="eb27e-109">定义 MED-V 最终用户</span><span class="sxs-lookup"><span data-stu-id="eb27e-109">Define the MED-V End Users</span></span>


<span data-ttu-id="eb27e-110">首先，确定最终用户所在的位置，以及每个位置中的用户数。</span><span class="sxs-lookup"><span data-stu-id="eb27e-110">First, determine where the end users are located, as well as the number of users in each location.</span></span> <span data-ttu-id="eb27e-111">第二，获取网络基础结构图，显示用户位置和这些位置的可用带宽。</span><span class="sxs-lookup"><span data-stu-id="eb27e-111">Second, obtain a network infrastructure diagram that displays the user locations and the available bandwidth to those locations.</span></span> <span data-ttu-id="eb27e-112">第三，了解用户是否在两个位置之间旅行。</span><span class="sxs-lookup"><span data-stu-id="eb27e-112">Third, find out if users travel between locations.</span></span> <span data-ttu-id="eb27e-113">如果用户旅行，在服务器基础结构和图像存储库的设计中可能需要额外的容量。</span><span class="sxs-lookup"><span data-stu-id="eb27e-113">If users travel, additional capacity may be required in the design of the server infrastructure and image repositories.</span></span>

## <span data-ttu-id="eb27e-114">确定 MED-V 要管理的 MED-V 图像</span><span class="sxs-lookup"><span data-stu-id="eb27e-114">Determine the MED-V Images to Be Managed by MED-V</span></span>


<span data-ttu-id="eb27e-115">定义了 MED-V 最终用户后，确定将由 MED-V 对每个位置中的用户管理哪些 Vm。</span><span class="sxs-lookup"><span data-stu-id="eb27e-115">After the MED-V end users have been defined, determine which VMs will be managed by MED-V for the users in each location.</span></span>

<span data-ttu-id="eb27e-116">如果任何 Vm 存储在一个集中的库中，请确定该库的位置，以便将其评估用作 MED-V 存储库。</span><span class="sxs-lookup"><span data-stu-id="eb27e-116">If any of the VMs are stored in a centralized library, determine the location of the library so that it may be evaluated for use as a MED-V repository.</span></span>

## <a href="" id="determine-the-organization-s-service-level-expectations"></a><span data-ttu-id="eb27e-117">确定组织的服务级别期望值</span><span class="sxs-lookup"><span data-stu-id="eb27e-117">Determine the Organization’s Service Level Expectations</span></span>


<span data-ttu-id="eb27e-118">对于每个 MED-V 工作区，请注意要加载的新映像的可接受时间和要部署的关键更新的时间范围。</span><span class="sxs-lookup"><span data-stu-id="eb27e-118">For each MED-V workspace, note the acceptable time for a new image to load and the timeframe for critical updates to be deployed.</span></span>

<span data-ttu-id="eb27e-119">如果适用，请记录 MED-V 报告的服务级别期望值，以便在服务器基础结构的设计中使用。</span><span class="sxs-lookup"><span data-stu-id="eb27e-119">If applicable, record the service level expectations for MED-V reporting, to be used in the design of the server infrastructure.</span></span>

## <span data-ttu-id="eb27e-120">与业务部门进行验证</span><span class="sxs-lookup"><span data-stu-id="eb27e-120">Validate with the Business</span></span>


<span data-ttu-id="eb27e-121">询问业务利益干系人和应用程序所有者下列问题：</span><span class="sxs-lookup"><span data-stu-id="eb27e-121">Ask business stakeholders and application owners the following questions:</span></span>

-   <span data-ttu-id="eb27e-122">是否有任何现有图像可以合并？</span><span class="sxs-lookup"><span data-stu-id="eb27e-122">Are there any existing images that can be combined?</span></span> <span data-ttu-id="eb27e-123">例如，如果 WindowsXP 上的应用程序是一个 VPC 图像，而 WindowsXP 上的应用程序 B 是另一个 VPC 映像，则可能是单个映像可以同时包含这两个应用程序，从而减少了下载图像所需的存储库空间和带宽。</span><span class="sxs-lookup"><span data-stu-id="eb27e-123">For example, if application A on WindowsXP is one VPC image and application B on WindowsXP is another VPC image, perhaps a single image can contain both applications, thereby reducing repository space and bandwidth required for image download.</span></span>

-   <span data-ttu-id="eb27e-124">如果由 MED-V 在 VM 中传递，则范围内应用程序是否受许可和支持？</span><span class="sxs-lookup"><span data-stu-id="eb27e-124">Are the in-scope applications licensable and supportable if delivered in a VM by MED-V?</span></span> <span data-ttu-id="eb27e-125">通过 MED-V 提供应用程序，与应用程序供应商联系，以确保不会违反许可和支持条款。</span><span class="sxs-lookup"><span data-stu-id="eb27e-125">Check with the application supplier to ensure that licensing and support terms will not be violated by delivering the application through MED-V.</span></span>

 

 





