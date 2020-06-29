---
title: 部署 MBAM 2.0 客户端
description: 部署 MBAM 2.0 客户端
author: dansimp
ms.assetid: 3dd584fe-2a54-40f0-9bab-13ea74040b01
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fa42c8ab3adc273f0e00ba56a59f487deba89c6f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803370"
---
# <span data-ttu-id="0e77b-103">部署 MBAM 2.0 客户端</span><span class="sxs-lookup"><span data-stu-id="0e77b-103">Deploying the MBAM 2.0 Client</span></span>


<span data-ttu-id="0e77b-104">Microsoft BitLocker 管理和监视（MBAM）客户端使管理员能够在企业中的计算机上实施和监视 BitLocker 驱动器加密。</span><span class="sxs-lookup"><span data-stu-id="0e77b-104">The Microsoft BitLocker Administration and Monitoring (MBAM) Client enables administrators to enforce and monitor BitLocker drive encryption on computers in the enterprise.</span></span> <span data-ttu-id="0e77b-105">通过电子软件分发系统（如 Active Directory 域服务）部署客户端，或者通过直接加密客户端计算机作为初始映像过程的一部分，可将 BitLocker 客户端集成到组织中。</span><span class="sxs-lookup"><span data-stu-id="0e77b-105">The BitLocker client can be integrated into an organization by deploying the client through an electronic software distribution system, such as Active Directory Domain Services, or by directly encrypting the client computers as part of the initial imaging process.</span></span>

<span data-ttu-id="0e77b-106">根据你部署 Microsoft BitLocker 管理和监视客户端的时间，你可以在最终用户接收计算机之前或通过配置组策略并使用企业软件部署系统部署 MBAM 客户端软件，在组织中的计算机上启用 BitLocker 加密。</span><span class="sxs-lookup"><span data-stu-id="0e77b-106">Depending on when you deploy the Microsoft BitLocker Administration and Monitoring Client, you can enable BitLocker encryption on a computer in your organization either before the end user receives the computer or afterwards by configuring Group Policy and deploying the MBAM Client software by using an enterprise software deployment system.</span></span>

## <span data-ttu-id="0e77b-107">将 MBAM 客户端部署到台式计算机或膝上型计算机</span><span class="sxs-lookup"><span data-stu-id="0e77b-107">Deploy the MBAM Client to Desktop or Laptop Computers</span></span>


<span data-ttu-id="0e77b-108">配置组策略后，您可以使用企业软件部署系统产品（如 Microsoft System Center Configuration Manager 2012 或 Active Directory 域服务）将 MBAM 客户端安装 Windows Installer 文件部署到目标计算机。</span><span class="sxs-lookup"><span data-stu-id="0e77b-108">After configuring Group Policy, you can use an enterprise software deployment system product like Microsoft System Center Configuration Manager 2012 or Active Directory Domain Services to deploy the MBAM Client installation Windows Installer files to target computers.</span></span> <span data-ttu-id="0e77b-109">你可以使用32位或64位 MbamClientSetup.exe 文件，或者使用 MBAM 软件附带的32位或64位 MBAMClient.msi 文件来部署客户端。</span><span class="sxs-lookup"><span data-stu-id="0e77b-109">You can deploy the client by using either the 32-bit or 64-bit MbamClientSetup.exe files, or the 32-bit or 64-bit MBAMClient.msi files, which are provided with the MBAM software.</span></span> <span data-ttu-id="0e77b-110">有关部署 MBAM 组策略对象的详细信息，请参阅[部署 MBAM 2.0 组策略对象](deploying-mbam-20-group-policy-objects-mbam-2.md)。</span><span class="sxs-lookup"><span data-stu-id="0e77b-110">For more information about deploying MBAM Group Policy Objects, see [Deploying MBAM 2.0 Group Policy Objects](deploying-mbam-20-group-policy-objects-mbam-2.md).</span></span>

[<span data-ttu-id="0e77b-111">如何将 MBAM 客户端部署到台式机或笔记本电脑</span><span class="sxs-lookup"><span data-stu-id="0e77b-111">How to Deploy the MBAM Client to Desktop or Laptop Computers</span></span>](how-to-deploy-the-mbam-client-to-desktop-or-laptop-computers-mbam-2.md)

## <span data-ttu-id="0e77b-112">将 MBAM 客户端部署为 Windows 部署的一部分</span><span class="sxs-lookup"><span data-stu-id="0e77b-112">Deploy the MBAM Client as Part of a Windows Deployment</span></span>


<span data-ttu-id="0e77b-113">在计算机被集中接收和配置的组织中，你可以安装 MBAM 客户端以在每台计算机上管理 BitLocker 加密，然后再向其写入任何用户数据。</span><span class="sxs-lookup"><span data-stu-id="0e77b-113">In organizations where computers are received and configured centrally, you can install the MBAM Client to manage BitLocker encryption on each computer before any user data is written to it.</span></span> <span data-ttu-id="0e77b-114">此过程的优点是，每台计算机都符合 BitLocker 加密标准。</span><span class="sxs-lookup"><span data-stu-id="0e77b-114">The benefit of this process is that every computer is then BitLocker encryption compliant.</span></span> <span data-ttu-id="0e77b-115">此方法不依赖于用户操作，因为管理员已加密计算机。</span><span class="sxs-lookup"><span data-stu-id="0e77b-115">This method does not rely on user action because the administrator has already encrypted the computer.</span></span> <span data-ttu-id="0e77b-116">此方案的一个关键假设是，组织的策略在将计算机交付给用户之前安装企业的 Windows 映像。</span><span class="sxs-lookup"><span data-stu-id="0e77b-116">A key assumption for this scenario is that the policy of the organization installs a corporate Windows image before the computer is delivered to the user.</span></span> <span data-ttu-id="0e77b-117">如果已将组策略配置为需要 PIN 码，则会在用户收到组策略后提示用户设置 PIN。</span><span class="sxs-lookup"><span data-stu-id="0e77b-117">If the Group Policy has been configured to require a PIN, users are prompted to set a PIN after they receive the Group Policy.</span></span>

[<span data-ttu-id="0e77b-118">如何在 Windows 部署过程中部署 MBAM 客户端</span><span class="sxs-lookup"><span data-stu-id="0e77b-118">How to Deploy the MBAM Client as Part of a Windows Deployment</span></span>](how-to-deploy-the-mbam-client-as-part-of-a-windows-deployment-mbam-2.md)

## <span data-ttu-id="0e77b-119">如何使用命令行安装 MBAM 客户端</span><span class="sxs-lookup"><span data-stu-id="0e77b-119">How to Use a Command Line to Install the MBAM Client</span></span>


<span data-ttu-id="0e77b-120">本部分介绍如何使用命令行安装 MBAM 客户端。</span><span class="sxs-lookup"><span data-stu-id="0e77b-120">This section explains how to install the MBAM Client by using a command line.</span></span>

[<span data-ttu-id="0e77b-121">如何使用命令行安装 MBAM 客户端</span><span class="sxs-lookup"><span data-stu-id="0e77b-121">How to Use a Command Line to Install the MBAM Client</span></span>](how-to-use-a-command-line-to-install-the-mbam-client.md)

## <span data-ttu-id="0e77b-122">用于部署 MBAM 客户端的其他资源</span><span class="sxs-lookup"><span data-stu-id="0e77b-122">Other Resources for Deploying the MBAM Client</span></span>


<span data-ttu-id="0e77b-123">[部署 MBAM 2.0](deploying-mbam-20-mbam-2.md)[MBAM 2.0 客户端部署计划](planning-for-mbam-20-client-deployment-mbam-2.md)</span><span class="sxs-lookup"><span data-stu-id="0e77b-123">[Deploying MBAM 2.0](deploying-mbam-20-mbam-2.md)[Planning for MBAM 2.0 Client Deployment](planning-for-mbam-20-client-deployment-mbam-2.md)</span></span>

 

 





