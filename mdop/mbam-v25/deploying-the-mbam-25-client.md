---
title: 部署 MBAM 2.5 客户端
description: 部署 MBAM 2.5 客户端
author: dansimp
ms.assetid: 0a96a0ee-f280-49d9-a244-88f4147fe9fd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 375af8966c8e66a58baec5065d065891187899fc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803936"
---
# <span data-ttu-id="aaf3e-103">部署 MBAM 2.5 客户端</span><span class="sxs-lookup"><span data-stu-id="aaf3e-103">Deploying the MBAM 2.5 Client</span></span>


<span data-ttu-id="aaf3e-104">Microsoft BitLocker 管理和监视（MBAM）客户端软件使管理员能够在企业中的计算机上实施和监视 BitLocker 驱动器加密。</span><span class="sxs-lookup"><span data-stu-id="aaf3e-104">The Microsoft BitLocker Administration and Monitoring (MBAM) Client software enables administrators to enforce and monitor BitLocker Drive Encryption on computers in the enterprise.</span></span> <span data-ttu-id="aaf3e-105">通过电子软件分发系统（如 Active Directory 域服务）部署客户端，或者通过直接加密客户端计算机作为初始映像过程的一部分，可将 BitLocker 客户端集成到组织中。</span><span class="sxs-lookup"><span data-stu-id="aaf3e-105">The BitLocker client can be integrated into an organization by deploying the client through an electronic software distribution system, such as Active Directory Domain Services, or by directly encrypting the client computers as part of the initial imaging process.</span></span>

<span data-ttu-id="aaf3e-106">根据部署 Microsoft BitLocker 管理和监视客户端软件的时间，你可以在最终用户接收计算机之前或通过配置组策略并使用企业软件部署系统部署 MBAM 客户端软件，在组织中的计算机上启用 BitLocker 驱动器加密。</span><span class="sxs-lookup"><span data-stu-id="aaf3e-106">Depending on when you deploy the Microsoft BitLocker Administration and Monitoring Client software, you can enable BitLocker Drive Encryption on a computer in your organization either before the end user receives the computer or afterwards by configuring Group Policy and deploying the MBAM Client software by using an enterprise software deployment system.</span></span>

## <span data-ttu-id="aaf3e-107">将 MBAM 客户端部署到台式计算机或膝上型计算机</span><span class="sxs-lookup"><span data-stu-id="aaf3e-107">Deploy the MBAM Client to desktop or laptop computers</span></span>


<span data-ttu-id="aaf3e-108">配置组策略设置后，你可以使用企业软件部署系统产品（如 MicrosoftSystemCenter2012 ConfigurationManager 或 Active Directory 域服务）将 MBAM 客户端安装 Windows Installer 文件部署到目标计算机。</span><span class="sxs-lookup"><span data-stu-id="aaf3e-108">After configuring Group Policy settings, you can use an enterprise software deployment system product like MicrosoftSystemCenter2012 ConfigurationManager or Active Directory Domain Services to deploy the MBAM Client installation Windows Installer files to target computers.</span></span> <span data-ttu-id="aaf3e-109">你可以使用32位或64位 MbamClientSetup.exe 文件或32位或64位 MBAMClient.msi 文件，这些文件随 MBAM 客户端软件一起提供。</span><span class="sxs-lookup"><span data-stu-id="aaf3e-109">You can use either the 32-bit or 64-bit MbamClientSetup.exe files or the 32-bit or 64-bit MBAMClient.msi files, which are provided with the MBAM Client software.</span></span> <span data-ttu-id="aaf3e-110">有关部署 MBAM 组策略设置的详细信息，请参阅[部署 MBAM 2.5 组策略对象](deploying-mbam-25-group-policy-objects.md)。</span><span class="sxs-lookup"><span data-stu-id="aaf3e-110">For more information about deploying MBAM Group Policy settings, see [Deploying MBAM 2.5 Group Policy Objects](deploying-mbam-25-group-policy-objects.md).</span></span>

<span data-ttu-id="aaf3e-111">**注意** 从 MBAM 2.5 SP1 开始，MBAM 产品不再附带单独的 MSI。</span><span class="sxs-lookup"><span data-stu-id="aaf3e-111">**Note** Beginning in MBAM 2.5 SP1, a separate MSI is no longer included with the MBAM product.</span></span> <span data-ttu-id="aaf3e-112">但是，你可以从产品附带的可执行文件（.exe）中提取 MSI。</span><span class="sxs-lookup"><span data-stu-id="aaf3e-112">However, you can extract the MSI from the executable file (.exe) that is included with the product.</span></span>

 

[<span data-ttu-id="aaf3e-113">如何将 MBAM 客户端部署到台式机或笔记本电脑</span><span class="sxs-lookup"><span data-stu-id="aaf3e-113">How to Deploy the MBAM Client to Desktop or Laptop Computers</span></span>](how-to-deploy-the-mbam-client-to-desktop-or-laptop-computers-mbam-25.md)

## <span data-ttu-id="aaf3e-114">将 MBAM 客户端部署为 Windows 部署的一部分</span><span class="sxs-lookup"><span data-stu-id="aaf3e-114">Deploy the MBAM Client as part of a Windows deployment</span></span>


<span data-ttu-id="aaf3e-115">在计算机被集中接收和配置的组织中，你可以安装 MBAM 客户端以在每台计算机上管理 BitLocker 驱动器加密，然后再向其写入任何用户数据。</span><span class="sxs-lookup"><span data-stu-id="aaf3e-115">In organizations where computers are received and configured centrally, you can install the MBAM Client to manage BitLocker Drive Encryption on each computer before any user data is written to it.</span></span> <span data-ttu-id="aaf3e-116">此过程的好处是，每台计算机都与 BitLocker 驱动器加密兼容。</span><span class="sxs-lookup"><span data-stu-id="aaf3e-116">The benefit of this process is that every computer is then BitLocker Drive Encryption-compliant.</span></span> <span data-ttu-id="aaf3e-117">此方法不依赖于用户操作，因为管理员已加密计算机。</span><span class="sxs-lookup"><span data-stu-id="aaf3e-117">This method does not rely on user action because the administrator has already encrypted the computer.</span></span> <span data-ttu-id="aaf3e-118">此方案的一个关键假设是，组织的策略在将计算机交付给用户之前安装企业的 Windows 映像。</span><span class="sxs-lookup"><span data-stu-id="aaf3e-118">A key assumption for this scenario is that the policy of the organization installs a corporate Windows image before the computer is delivered to the user.</span></span> <span data-ttu-id="aaf3e-119">如果已将组策略设置配置为需要 PIN 码，则会在用户收到策略后提示用户设置 PIN。</span><span class="sxs-lookup"><span data-stu-id="aaf3e-119">If the Group Policy settings has been configured to require a PIN, users are prompted to set a PIN after they receive the policy.</span></span>

[<span data-ttu-id="aaf3e-120">如何通过使用 MBAM 将 BitLocker 作为 Windows 部署的一部分来启用</span><span class="sxs-lookup"><span data-stu-id="aaf3e-120">How to Enable BitLocker by Using MBAM as Part of a Windows Deployment</span></span>](how-to-enable-bitlocker-by-using-mbam-as-part-of-a-windows-deploymentmbam-25.md)

## <span data-ttu-id="aaf3e-121">如何使用命令行部署 MBAM 客户端</span><span class="sxs-lookup"><span data-stu-id="aaf3e-121">How to deploy the MBAM Client by using a command line</span></span>


<span data-ttu-id="aaf3e-122">本部分介绍如何使用命令行安装 MBAM 客户端。</span><span class="sxs-lookup"><span data-stu-id="aaf3e-122">This section explains how to install the MBAM Client by using a command line.</span></span>

[<span data-ttu-id="aaf3e-123">如何使用命令行部署 MBAM 客户端</span><span class="sxs-lookup"><span data-stu-id="aaf3e-123">How to Deploy the MBAM Client by Using a Command Line</span></span>](how-to-deploy-the-mbam-client-by-using-a-command-line.md)

## <span data-ttu-id="aaf3e-124">用于部署 MBAM 客户端的其他资源</span><span class="sxs-lookup"><span data-stu-id="aaf3e-124">Other resources for deploying the MBAM Client</span></span>


[<span data-ttu-id="aaf3e-125">部署 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="aaf3e-125">Deploying MBAM 2.5</span></span>](deploying-mbam-25.md)



## <span data-ttu-id="aaf3e-126">相关主题</span><span class="sxs-lookup"><span data-stu-id="aaf3e-126">Related topics</span></span>


[<span data-ttu-id="aaf3e-127">部署 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="aaf3e-127">Deploying MBAM 2.5</span></span>](deploying-mbam-25.md)

[<span data-ttu-id="aaf3e-128">规划 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="aaf3e-128">Planning for MBAM 2.5</span></span>](planning-for-mbam-25.md)

 
## <span data-ttu-id="aaf3e-129">已获得 MBAM 的建议？</span><span class="sxs-lookup"><span data-stu-id="aaf3e-129">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="aaf3e-130">在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="aaf3e-130">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="aaf3e-131">对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="aaf3e-131">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>
 





