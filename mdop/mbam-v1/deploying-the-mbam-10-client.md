---
title: 部署 MBAM 1.0 客户端
description: 部署 MBAM 1.0 客户端
author: dansimp
ms.assetid: f7ca233f-5035-4ff9-ab3a-f2453b4929d1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: dee8c2f4a9b398c9f0797ada35e4c36610c755b1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803261"
---
# <span data-ttu-id="380d3-103">部署 MBAM 1.0 客户端</span><span class="sxs-lookup"><span data-stu-id="380d3-103">Deploying the MBAM 1.0 Client</span></span>


<span data-ttu-id="380d3-104">Microsoft BitLocker 管理和监视（MBAM）客户端使管理员能够在企业中的计算机上实施和监视 BitLocker 驱动器加密。</span><span class="sxs-lookup"><span data-stu-id="380d3-104">The Microsoft BitLocker Administration and Monitoring (MBAM) Client enables administrators to enforce and monitor BitLocker drive encryption on computers in the enterprise.</span></span> <span data-ttu-id="380d3-105">通过诸如 Active Directory 域服务之类的工具部署客户端，或者在初始映像过程中直接加密客户端计算机，可将 BitLocker 客户端集成到组织中。</span><span class="sxs-lookup"><span data-stu-id="380d3-105">The BitLocker client can be integrated into an organization by deploying the client through tools like Active Directory Domain Services or by directly encrypting the client computers as part of the initial imaging process.</span></span>

<span data-ttu-id="380d3-106">根据部署 MBAM 客户端的时间，你可以在你组织中的计算机上或最终用户接收计算机之前或之后启用 BitLocker 加密。</span><span class="sxs-lookup"><span data-stu-id="380d3-106">Depending on when you deploy the MBAM Client, you can enable BitLocker encryption on a computer in your organization either before or after the end user receives the computer.</span></span> <span data-ttu-id="380d3-107">若要控制此计时，请配置组策略并使用企业软件部署系统部署 MBAM 客户端软件。</span><span class="sxs-lookup"><span data-stu-id="380d3-107">To control this timing, you configure Group Policy and deploy the MBAM Client software by using an enterprise software deployment system.</span></span>

<span data-ttu-id="380d3-108">您可以在您的组织中使用其中一个或两个方法。</span><span class="sxs-lookup"><span data-stu-id="380d3-108">You can use either or both of these methods in your organization.</span></span> <span data-ttu-id="380d3-109">如果使用这两种方法，则可以改进合规性、报告和密钥恢复支持。</span><span class="sxs-lookup"><span data-stu-id="380d3-109">If you use both methods, you can improve compliance, reporting, and key recovery support.</span></span>

## <span data-ttu-id="380d3-110">将 MBAM 客户端部署到台式计算机或膝上型计算机</span><span class="sxs-lookup"><span data-stu-id="380d3-110">Deploy the MBAM Client to desktop or laptop computers</span></span>


<span data-ttu-id="380d3-111">配置组策略后，你可以将 MBAM 客户端安装 Windows Installer 文件部署到目标计算机。</span><span class="sxs-lookup"><span data-stu-id="380d3-111">After you have configured Group Policy, you can deploy the MBAM Client installation Windows Installer files to target computers.</span></span> <span data-ttu-id="380d3-112">你可以使用企业软件部署系统产品（如 Microsoft System Center 2012 配置管理器或 Active Directory 域服务）执行此操作。</span><span class="sxs-lookup"><span data-stu-id="380d3-112">You can do this by use of an enterprise software deployment system product like Microsoft System Center 2012 Configuration Manager or Active Directory Domain Services.</span></span> <span data-ttu-id="380d3-113">两个可用的 MBAM 客户端安装 Windows 安装程序文件 MBAMClient-64bit.msi 和 MBAMClient-32bit.msi。</span><span class="sxs-lookup"><span data-stu-id="380d3-113">The two available MBAM Client installation Windows Installer files are MBAMClient-64bit.msi and MBAMClient-32bit.msi.</span></span> <span data-ttu-id="380d3-114">这些文件随 MBAM 软件一起提供。</span><span class="sxs-lookup"><span data-stu-id="380d3-114">These files are provided with the MBAM software.</span></span> <span data-ttu-id="380d3-115">有关如何部署 MBAM 组策略对象的详细信息，请参阅[部署 MBAM 1.0 组策略对象](deploying-mbam-10-group-policy-objects.md)。</span><span class="sxs-lookup"><span data-stu-id="380d3-115">For more information about how to deploy MBAM Group Policy Objects, see [Deploying MBAM 1.0 Group Policy Objects](deploying-mbam-10-group-policy-objects.md).</span></span>

[<span data-ttu-id="380d3-116">如何将 MBAM 客户端部署到台式机或笔记本电脑</span><span class="sxs-lookup"><span data-stu-id="380d3-116">How to Deploy the MBAM Client to Desktop or Laptop Computers</span></span>](how-to-deploy-the-mbam-client-to-desktop-or-laptop-computers-mbam-1.md)

## <span data-ttu-id="380d3-117">将 MBAM 客户端部署为 Windows 部署的一部分</span><span class="sxs-lookup"><span data-stu-id="380d3-117">Deploy the MBAM Client as part of a Windows deployment</span></span>


<span data-ttu-id="380d3-118">在某些组织中，新计算机的接收和配置是集中的。</span><span class="sxs-lookup"><span data-stu-id="380d3-118">In some organizations, new computers are received and configured centrally.</span></span> <span data-ttu-id="380d3-119">这种情况使管理员能够在任何用户数据写入计算机之前安装 MBAM 客户端来管理每台计算机上的 BitLocker 加密。</span><span class="sxs-lookup"><span data-stu-id="380d3-119">This situation enables administrators to install the MBAM Client to manage BitLocker encryption on each computer before any user data is written to the computer.</span></span> <span data-ttu-id="380d3-120">此方法有助于确保计算机被正确加密，因为管理员执行操作时不依赖最终用户操作。</span><span class="sxs-lookup"><span data-stu-id="380d3-120">This approach helps to ensure that computers are properly encrypted because the administrator performs the action without reliance on end-user action.</span></span> <span data-ttu-id="380d3-121">此方案的一个关键假设是，组织的策略在将计算机交付给用户之前安装企业的 Windows 映像。</span><span class="sxs-lookup"><span data-stu-id="380d3-121">A key assumption for this scenario is that the policy of the organization installs a corporate Windows image before the computer is delivered to the user.</span></span>

[<span data-ttu-id="380d3-122">如何在 Windows 部署过程中部署 MBAM 客户端</span><span class="sxs-lookup"><span data-stu-id="380d3-122">How to Deploy the MBAM Client as Part of a Windows Deployment</span></span>](how-to-deploy-the-mbam-client-as-part-of-a-windows-deployment-mbam-1.md)

## <span data-ttu-id="380d3-123">用于部署 MBAM 客户端的其他资源</span><span class="sxs-lookup"><span data-stu-id="380d3-123">Other resources for deploying the MBAM Client</span></span>


[<span data-ttu-id="380d3-124">部署 MBAM 1.0</span><span class="sxs-lookup"><span data-stu-id="380d3-124">Deploying MBAM 1.0</span></span>](deploying-mbam-10.md)

[<span data-ttu-id="380d3-125">计划 MBAM 1.0 客户端部署</span><span class="sxs-lookup"><span data-stu-id="380d3-125">Planning for MBAM 1.0 Client Deployment</span></span>](planning-for-mbam-10-client-deployment.md)

 

 





