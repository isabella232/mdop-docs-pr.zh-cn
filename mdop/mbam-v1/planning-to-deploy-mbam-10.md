---
title: 计划部署 MBAM 1.0
description: 计划部署 MBAM 1.0
author: dansimp
ms.assetid: 30ad4304-45c6-427d-8e33-ebe8053c7871
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c2ff25e705717db5086150ed08a5640335bbacb8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803318"
---
# <span data-ttu-id="38e61-103">计划部署 MBAM 1.0</span><span class="sxs-lookup"><span data-stu-id="38e61-103">Planning to Deploy MBAM 1.0</span></span>


<span data-ttu-id="38e61-104">在创建 Microsoft BitLocker 管理和监视（MBAM）1.0 部署计划之前，应考虑许多不同的部署配置和先决条件。</span><span class="sxs-lookup"><span data-stu-id="38e61-104">You should consider a number of different deployment configurations and prerequisites before you create your Microsoft BitLocker Administration and Monitoring (MBAM) 1.0 deployment plan.</span></span> <span data-ttu-id="38e61-105">本部分包含的信息可帮助您收集可用于制定最符合业务要求的部署计划所必需的信息。</span><span class="sxs-lookup"><span data-stu-id="38e61-105">This section includes information that can help you gather the information that you must have to formulate a deployment plan that best meets your business requirements.</span></span>

## <span data-ttu-id="38e61-106">查看 MBAM 1.0 支持的配置</span><span class="sxs-lookup"><span data-stu-id="38e61-106">Review the MBAM 1.0 supported configurations</span></span>


<span data-ttu-id="38e61-107">为 MBAM 客户端和服务器功能安装准备了计算环境后，请确保查看 MBAM 支持的配置信息，以确认安装 MBAM 的计算机满足最低硬件和操作系统要求。</span><span class="sxs-lookup"><span data-stu-id="38e61-107">After you prepare your computing environment for the MBAM Client and Server feature installation, make sure that you review the Supported Configurations information for MBAM to confirm that the computers on which you install MBAM meet the minimum hardware and operating system requirements.</span></span> <span data-ttu-id="38e61-108">有关 MBAM 部署先决条件的详细信息，请参阅[MBAM 1.0 部署先决条件](mbam-10-deployment-prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="38e61-108">For more information about MBAM deployment prerequisites, see [MBAM 1.0 Deployment Prerequisites](mbam-10-deployment-prerequisites.md).</span></span>

[<span data-ttu-id="38e61-109">MBAM 1.0 支持的配置</span><span class="sxs-lookup"><span data-stu-id="38e61-109">MBAM 1.0 Supported Configurations</span></span>](mbam-10-supported-configurations.md)

## <span data-ttu-id="38e61-110">规划 MBAM 1.0 服务器和客户端部署</span><span class="sxs-lookup"><span data-stu-id="38e61-110">Plan for MBAM 1.0 Server and Client deployment</span></span>


<span data-ttu-id="38e61-111">MBAM 服务器基础结构依赖于一组可在一台或多台服务器计算机上安装的服务器功能，具体取决于企业的要求。</span><span class="sxs-lookup"><span data-stu-id="38e61-111">The MBAM server infrastructure depends on a set of server features that can be installed on one or more server computers, based on the requirements of the enterprise.</span></span> <span data-ttu-id="38e61-112">这些功能可以安装在一台服务器上，也可以分布在多台服务器上。</span><span class="sxs-lookup"><span data-stu-id="38e61-112">These features can be installed on a single server or distributed across multiple servers.</span></span>

<span data-ttu-id="38e61-113">MBAM 客户端使管理员能够在企业中的计算机上实施和监视 BitLocker 驱动器加密。</span><span class="sxs-lookup"><span data-stu-id="38e61-113">The MBAM Client enables administrators to enforce and monitor the BitLocker drive encryption on computers in the enterprise.</span></span> <span data-ttu-id="38e61-114">通过诸如 Active Directory 域服务之类的工具部署客户端，或者在初始映像过程中直接加密客户端计算机，可将 BitLocker 客户端集成到组织中。</span><span class="sxs-lookup"><span data-stu-id="38e61-114">The BitLocker client can be integrated into an organization by deploying the client through tools like Active Directory Domain Services or by directly encrypting the client computers as part of the initial imaging process.</span></span>

<span data-ttu-id="38e61-115">通过 MBAM，你可以在最终用户接收计算机之前或使用组策略之后，在你的组织中加密计算机。</span><span class="sxs-lookup"><span data-stu-id="38e61-115">With MBAM, you can encrypt a computer in your organization either before the end user receives the computer or afterwards, by using Group Policy.</span></span> <span data-ttu-id="38e61-116">您可以在您的组织中使用一种或两种方法。</span><span class="sxs-lookup"><span data-stu-id="38e61-116">You can use one or both methods in your organization.</span></span> <span data-ttu-id="38e61-117">如果你选择使用这两种方法，则可以改进合规性、报告和密钥恢复支持。</span><span class="sxs-lookup"><span data-stu-id="38e61-117">If you choose to use both methods, you can improve compliance, reporting, and key recovery support.</span></span>

[<span data-ttu-id="38e61-118">计划 MBAM 1.0 服务器部署</span><span class="sxs-lookup"><span data-stu-id="38e61-118">Planning for MBAM 1.0 Server Deployment</span></span>](planning-for-mbam-10-server-deployment.md)

[<span data-ttu-id="38e61-119">计划 MBAM 1.0 客户端部署</span><span class="sxs-lookup"><span data-stu-id="38e61-119">Planning for MBAM 1.0 Client Deployment</span></span>](planning-for-mbam-10-client-deployment.md)

## <a href="" id="other-resources-for-mbam-planning-"></a><span data-ttu-id="38e61-120">MBAM 规划的其他资源</span><span class="sxs-lookup"><span data-stu-id="38e61-120">Other resources for MBAM planning</span></span>


-   [<span data-ttu-id="38e61-121">计划 MBAM 1.0</span><span class="sxs-lookup"><span data-stu-id="38e61-121">Planning for MBAM 1.0</span></span>](planning-for-mbam-10.md)

 

 





