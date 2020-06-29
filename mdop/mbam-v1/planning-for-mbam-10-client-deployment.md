---
title: 计划 MBAM 1.0 客户端部署
description: 计划 MBAM 1.0 客户端部署
author: dansimp
ms.assetid: 3af2e7f3-134b-4ab9-9847-b07474ca6ac3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d58d6420febd2da9ee9cd4074fc8b5870285b0b4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803856"
---
# <span data-ttu-id="4d1d3-103">计划 MBAM 1.0 客户端部署</span><span class="sxs-lookup"><span data-stu-id="4d1d3-103">Planning for MBAM 1.0 Client Deployment</span></span>


<span data-ttu-id="4d1d3-104">根据你部署 Microsoft BitLocker 管理和监视（MBAM）客户端的时间，你可以在你的组织中的计算机上启用 BitLocker 加密，在最终用户收到计算机之前或之后。</span><span class="sxs-lookup"><span data-stu-id="4d1d3-104">Depending on when you deploy the Microsoft BitLocker Administration and Monitoring (MBAM) Client, you can enable BitLocker encryption on a computer in your organization either before the end user receives the computer or afterwards.</span></span> <span data-ttu-id="4d1d3-105">若要在最终用户收到计算机后启用 BitLocker 加密，请配置组策略。</span><span class="sxs-lookup"><span data-stu-id="4d1d3-105">To enable BitLocker encryption after the end user receives the computer, configure Group Policy.</span></span> <span data-ttu-id="4d1d3-106">若要在最终用户接收计算机之前启用 BitLocker 加密，请使用企业软件部署系统部署 MBAM 客户端软件。</span><span class="sxs-lookup"><span data-stu-id="4d1d3-106">To enable BitLocker encryption before the end user receives the computer, deploy the MBAM Client software by using an enterprise software deployment system.</span></span>

<span data-ttu-id="4d1d3-107">您可以在您的组织中使用一种或两种方法。</span><span class="sxs-lookup"><span data-stu-id="4d1d3-107">You can use one or both methods in your organization.</span></span> <span data-ttu-id="4d1d3-108">如果使用这两种方法，则可以改进合规性、报告和密钥恢复支持。</span><span class="sxs-lookup"><span data-stu-id="4d1d3-108">If you use both methods, you can improve compliance, reporting, and key recovery support.</span></span>

<span data-ttu-id="4d1d3-109">**注意** 若要查看 MBAM 客户端系统要求，请参阅[MBAM 1.0 支持的配置](mbam-10-supported-configurations.md)。</span><span class="sxs-lookup"><span data-stu-id="4d1d3-109">**Note** To review the MBAM Client system requirements, see [MBAM 1.0 Supported Configurations](mbam-10-supported-configurations.md).</span></span>

 

## <span data-ttu-id="4d1d3-110">部署 MBAM 客户端以在将计算机分发给最终用户后启用 BitLocker 加密</span><span class="sxs-lookup"><span data-stu-id="4d1d3-110">Deploying the MBAM Client to enable BitLocker encryption after computer distribution to end users</span></span>


<span data-ttu-id="4d1d3-111">配置组策略后，您可以使用企业软件部署系统产品（如 Microsoft System Center Configuration Manager 2012 或 Active Directory 域服务）将 MBAM 客户端安装 Windows 安装程序文件部署到目标计算机。</span><span class="sxs-lookup"><span data-stu-id="4d1d3-111">After you configure the Group Policy, you can use an enterprise software deployment system product, such as Microsoft System Center Configuration Manager 2012 or Active Directory Domain Services, to deploy the MBAM Client installation Windows Installer files to the target computers.</span></span> <span data-ttu-id="4d1d3-112">两个 MBAM 客户端安装 Windows Installer 文件 MBAMClient-64bit.msi 和 MBAMClient-32bit.msi，这些文件随 MBAM 软件一起提供。</span><span class="sxs-lookup"><span data-stu-id="4d1d3-112">The two MBAM Client installation Windows Installer files are MBAMClient-64bit.msi and MBAMClient-32bit.msi, which are provided with the MBAM software.</span></span> <span data-ttu-id="4d1d3-113">有关如何部署 MBAM 组策略对象的详细信息，请参阅[部署 MBAM 1.0 组策略对象](deploying-mbam-10-group-policy-objects.md)。</span><span class="sxs-lookup"><span data-stu-id="4d1d3-113">For more information about how to deploy MBAM Group Policy Objects, see [Deploying MBAM 1.0 Group Policy Objects](deploying-mbam-10-group-policy-objects.md).</span></span>

<span data-ttu-id="4d1d3-114">部署 MBAM 客户端时，在将计算机分发给最终用户后，系统会提示最终用户加密其计算机。</span><span class="sxs-lookup"><span data-stu-id="4d1d3-114">When you deploy the MBAM Client, after you distribute the computers to end users, the end users are prompted to encrypt their computers.</span></span> <span data-ttu-id="4d1d3-115">这允许 MBAM 收集数据，以包括 PIN 和密码，然后开始加密过程。</span><span class="sxs-lookup"><span data-stu-id="4d1d3-115">This lets MBAM collect the data, to include the PIN and password, and then begin the encryption process.</span></span>

<span data-ttu-id="4d1d3-116">**注意** 在此方法中，系统会提示用户激活并初始化受信任的平台模块（TPM）芯片（如果之前尚未激活）。</span><span class="sxs-lookup"><span data-stu-id="4d1d3-116">**Note** In this approach, users are prompted to activate and initialize the Trusted Platform Module (TPM) chip, if it has not been previously activated.</span></span>

 

## <span data-ttu-id="4d1d3-117">在将计算机分发给最终用户之前使用 MBAM 客户端启用 BitLocker 加密</span><span class="sxs-lookup"><span data-stu-id="4d1d3-117">Using the MBAM Client to enable BitLocker encryption before computer distribution to end users</span></span>


<span data-ttu-id="4d1d3-118">在计算机被集中接收和配置的组织中，你可以安装 MBAM 客户端以在每台计算机上管理 BitLocker 加密，然后再向其写入任何用户数据。</span><span class="sxs-lookup"><span data-stu-id="4d1d3-118">In organizations where computers are received and configured centrally, you can install the MBAM Client to manage BitLocker encryption on each computer before any user data is written on it.</span></span> <span data-ttu-id="4d1d3-119">此过程的好处是，每台计算机都将符合 BitLocker 加密的要求。</span><span class="sxs-lookup"><span data-stu-id="4d1d3-119">The benefit of this process is that every computer will then be compliant with the BitLocker encryption.</span></span> <span data-ttu-id="4d1d3-120">此方法不依赖于用户操作，因为管理员已加密计算机。</span><span class="sxs-lookup"><span data-stu-id="4d1d3-120">This method does not rely on user action because the administrator has already encrypted the computer.</span></span> <span data-ttu-id="4d1d3-121">此方案的一个关键假设是，组织的策略在将计算机交付给用户之前安装企业的 Windows 映像。</span><span class="sxs-lookup"><span data-stu-id="4d1d3-121">A key assumption for this scenario is that the policy of the organization installs a corporate Windows image before the computer is delivered to the user.</span></span>

<span data-ttu-id="4d1d3-122">如果你的组织希望使用（TPM）对计算机进行加密，管理员必须使用 TPM 保护程序加密计算机的操作系统卷。</span><span class="sxs-lookup"><span data-stu-id="4d1d3-122">If your organization wants to use (TPM) to encrypt computers, the administrator must encrypt the operating system volume of the computer with TPM protector.</span></span> <span data-ttu-id="4d1d3-123">如果你的组织想要使用 TPM 芯片和 PIN 保护器，管理员必须使用 TPM 保护程序加密系统卷，然后用户在首次登录时选择 PIN 码。</span><span class="sxs-lookup"><span data-stu-id="4d1d3-123">If your organization wants to use the TPM chip and a PIN protector, the administrator must encrypt the system volume with the TPM protector, and then the users select a PIN the first time they log on.</span></span> <span data-ttu-id="4d1d3-124">如果您的组织决定仅使用引脚保护器，则管理员不必先加密卷。</span><span class="sxs-lookup"><span data-stu-id="4d1d3-124">If your organization decides to use only the PIN protector, the administrator does not have to encrypt the volume first.</span></span> <span data-ttu-id="4d1d3-125">当用户在其计算机上登录时，MBAM 会提示他们提供 PIN 或 PIN 以及用户在稍后重新启动计算机时将使用的密码。</span><span class="sxs-lookup"><span data-stu-id="4d1d3-125">When users log on their computers, MBAM prompts them to provide a PIN or a PIN and a password that they will use when they restart their computer later.</span></span>

<span data-ttu-id="4d1d3-126">**注意** TPM 保护程序选项要求管理员在将计算机交付给用户之前接受激活和初始化 TPM 的 BIOS 提示。</span><span class="sxs-lookup"><span data-stu-id="4d1d3-126">**Note** The TPM protector option requires for the administrator to accept the BIOS prompt to activate and initialize the TPM before delivering the computer to the user.</span></span>

 

## <span data-ttu-id="4d1d3-127">相关主题</span><span class="sxs-lookup"><span data-stu-id="4d1d3-127">Related topics</span></span>


[<span data-ttu-id="4d1d3-128">计划部署 MBAM 1.0</span><span class="sxs-lookup"><span data-stu-id="4d1d3-128">Planning to Deploy MBAM 1.0</span></span>](planning-to-deploy-mbam-10.md)

[<span data-ttu-id="4d1d3-129">部署 MBAM 1.0 客户端</span><span class="sxs-lookup"><span data-stu-id="4d1d3-129">Deploying the MBAM 1.0 Client</span></span>](deploying-the-mbam-10-client.md)

 

 





