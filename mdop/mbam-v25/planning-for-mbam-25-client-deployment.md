---
title: 规划 MBAM 2.5 客户端部署
description: 规划 MBAM 2.5 客户端部署
author: dansimp
ms.assetid: 23c89976-af24-4753-9412-ce0ea42d1964
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ff03b58da0985b2f57308c99a9bc15f4a0554623
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803879"
---
# <span data-ttu-id="4e527-103">规划 MBAM 2.5 客户端部署</span><span class="sxs-lookup"><span data-stu-id="4e527-103">Planning for MBAM 2.5 Client Deployment</span></span>


<span data-ttu-id="4e527-104">根据你部署 Microsoft BitLocker 管理和监视（MBAM）客户端软件的时间，你可以在最终用户收到计算机之前或之后在组织中的计算机上启用 BitLocker 驱动器加密。</span><span class="sxs-lookup"><span data-stu-id="4e527-104">Depending on when you deploy the Microsoft BitLocker Administration and Monitoring (MBAM) Client software, you can enable BitLocker Drive Encryption on a computer in your organization either before the end user receives the computer or afterwards.</span></span> <span data-ttu-id="4e527-105">对于 MBAM 单机版和 System Center Configuration Manager 集成拓扑，你必须为 MBAM 配置组策略设置。</span><span class="sxs-lookup"><span data-stu-id="4e527-105">For both the MBAM Stand-alone and the System Center Configuration Manager Integration topologies, you have to configure Group Policy settings for MBAM.</span></span>

<span data-ttu-id="4e527-106">如果你使用的是 MBAM 独立拓扑，我们建议你使用企业软件部署系统将 MBAM 客户端软件部署到最终用户计算机。</span><span class="sxs-lookup"><span data-stu-id="4e527-106">If you are using the MBAM Stand-alone topology, we recommend that you use an enterprise software deployment system to deploy the MBAM Client software to end-user computers.</span></span>

<span data-ttu-id="4e527-107">如果使用 Configuration Manager 集成拓扑部署 MBAM，则可以使用 Configuration Manager 将 MBAM 客户端软件部署到最终用户计算机。</span><span class="sxs-lookup"><span data-stu-id="4e527-107">If you deploy MBAM with the Configuration Manager Integration topology, you can use Configuration Manager to deploy the MBAM Client software to end-user computers.</span></span> <span data-ttu-id="4e527-108">在配置管理器中，MBAM 安装将创建 MBAM 可管理的计算机的集合。</span><span class="sxs-lookup"><span data-stu-id="4e527-108">In Configuration Manager, the MBAM installation creates a collection of computers that MBAM can manage.</span></span> <span data-ttu-id="4e527-109">此集合包括的工作站和设备没有受信任的平台模块（TPM），但运行的是 Windows 8、Windows 8.1 或 Windows 10。</span><span class="sxs-lookup"><span data-stu-id="4e527-109">This collection includes workstations and devices that do not have a Trusted Platform Module (TPM), but that are running Windows 8, Windows 8.1, or Windows 10.</span></span>

<span data-ttu-id="4e527-110">**注意** 使用 Configuration Manager 2007 时，Configuration Manager 集成拓扑安装不支持 Windows To Go。</span><span class="sxs-lookup"><span data-stu-id="4e527-110">**Note** Windows To Go is not supported for the Configuration Manager Integration topology installation when you are using Configuration Manager 2007.</span></span>

 

## <span data-ttu-id="4e527-111">部署 MBAM 客户端以在将计算机分发给最终用户之后启用 BitLocker 驱动器加密</span><span class="sxs-lookup"><span data-stu-id="4e527-111">Deploying the MBAM Client to enable BitLocker Drive Encryption after computer distribution to end users</span></span>


<span data-ttu-id="4e527-112">配置组策略后，你可以使用企业软件部署系统产品（如 Microsoft System Center Configuration Manager 或 Active Directory 域服务（AD DS））将 MBAM 客户端安装的 Windows Installer 文件部署到目标计算机。</span><span class="sxs-lookup"><span data-stu-id="4e527-112">After you configure Group Policy, you can use an enterprise software deployment system product like Microsoft System Center Configuration Manager or Active Directory Domain Services (AD DS) to deploy the Windows Installer files of the MBAM Client installation to target computers.</span></span> <span data-ttu-id="4e527-113">若要部署 MBAM 客户端，你可以使用32位或64位 MbamClientSetup.exe 文件或 MBAMClient.msi 文件，这些文件或 MBAM 客户端软件附带的文件。</span><span class="sxs-lookup"><span data-stu-id="4e527-113">To deploy the MBAM Client, you can use either the 32-bit or 64-bit MbamClientSetup.exe files or MBAMClient.msi files, which are provided with the MBAM Client software.</span></span>

<span data-ttu-id="4e527-114">**注意** 从 MBAM 2.5 SP1 开始，MBAM 产品不再附带单独的 MSI。</span><span class="sxs-lookup"><span data-stu-id="4e527-114">**Note** Beginning in MBAM 2.5 SP1, a separate MSI is no longer included with the MBAM product.</span></span> <span data-ttu-id="4e527-115">但是，你可以从产品附带的可执行文件（.exe）中提取 MSI。</span><span class="sxs-lookup"><span data-stu-id="4e527-115">However, you can extract the MSI from the executable file (.exe) that is included with the product.</span></span>

 

<span data-ttu-id="4e527-116">在将计算机分配给客户端计算机之后部署 MBAM 客户端时，系统会提示最终用户对其计算机进行加密。</span><span class="sxs-lookup"><span data-stu-id="4e527-116">When you deploy the MBAM Client after you distribute computers to client computers, end users are prompted to encrypt their computer.</span></span> <span data-ttu-id="4e527-117">此操作使 MBAM 能够收集数据，其中包括 PIN 和密码（如果策略要求），然后开始加密过程。</span><span class="sxs-lookup"><span data-stu-id="4e527-117">This action enables MBAM to collect the data, which includes the PIN and password (if required by policy), and then to begin the encryption process.</span></span>

<span data-ttu-id="4e527-118">**注意** 在此方法中，如果尚未激活该芯片，则系统将提示拥有 TPM 芯片的计算机的最终用户激活并初始化 TPM 芯片。</span><span class="sxs-lookup"><span data-stu-id="4e527-118">**Note** In this approach, end users who have computers with a TPM chip are prompted to activate and initialize the TPM chip if the chip has not been previously activated.</span></span>

 

## <span data-ttu-id="4e527-119">在计算机分发给最终用户之前使用 MBAM 客户端启用 BitLocker 驱动器加密</span><span class="sxs-lookup"><span data-stu-id="4e527-119">Using the MBAM Client to enable BitLocker Drive Encryption before computer distribution to end users</span></span>


<span data-ttu-id="4e527-120">在同时接收和配置计算机的组织中，以及计算机具有兼容的 TPM 芯片的地方，你可以在向每台计算机上使用 MBAM 客户端管理 BitLocker 驱动器加密，然后再向其写入任何用户数据。</span><span class="sxs-lookup"><span data-stu-id="4e527-120">In organizations where computers are received and configured centrally, and where computers have a compliant TPM chip, you can use the MBAM Client to manage BitLocker Drive Encryption on each computer before any user data is written to it.</span></span> <span data-ttu-id="4e527-121">此过程的好处是，每台计算机都合规。</span><span class="sxs-lookup"><span data-stu-id="4e527-121">The benefit of this process is that every computer is then compliant.</span></span> <span data-ttu-id="4e527-122">此方法不依赖于最终用户操作，因为管理员已加密计算机。</span><span class="sxs-lookup"><span data-stu-id="4e527-122">This method does not rely on end-user action because the administrator has already encrypted the computer.</span></span> <span data-ttu-id="4e527-123">此方案的一个关键假设是，在将计算机交付给最终用户之前，组织的策略会安装企业的 Windows 映像。</span><span class="sxs-lookup"><span data-stu-id="4e527-123">A key assumption for this scenario is that the policy of the organization installs a corporate Windows image before the computer is delivered to the end user.</span></span>

<span data-ttu-id="4e527-124">如果你的组织希望使用 TPM 芯片加密计算机，管理员将添加 TPM 保护程序以加密计算机的操作系统卷。</span><span class="sxs-lookup"><span data-stu-id="4e527-124">If your organization wants to use the TPM chip to encrypt computers, the administrator adds the TPM protector to encrypt the operating system volume of the computer.</span></span> <span data-ttu-id="4e527-125">如果你的组织希望使用 TPM 芯片和 PIN 保护器，则管理员使用 TPM 保护程序对操作系统卷进行加密，然后最终用户首次登录时选择 PIN。</span><span class="sxs-lookup"><span data-stu-id="4e527-125">If your organization wants to use the TPM chip and a PIN protector, the administrator encrypts the operating system volume with the TPM protector, and then end users select a PIN when they log on for the first time.</span></span> <span data-ttu-id="4e527-126">如果您的组织决定仅使用引脚保护器，则管理员不必先加密卷。</span><span class="sxs-lookup"><span data-stu-id="4e527-126">If your organization decides to use only the PIN protector, the administrator does not have to encrypt the volume first.</span></span> <span data-ttu-id="4e527-127">当最终用户登录时，Microsoft BitLocker 管理和监视会提示他们提供 PIN 或 PIN 和密码，以便在以后的计算机重启时使用。</span><span class="sxs-lookup"><span data-stu-id="4e527-127">When end users log on, Microsoft BitLocker Administration and Monitoring prompts them to provide a PIN, or a PIN and password to be used on later computer restarts.</span></span>

<span data-ttu-id="4e527-128">**注意** TPM 保护程序选项要求管理员在将计算机交付给最终用户之前接受激活和初始化 TPM 的 BIOS 提示。</span><span class="sxs-lookup"><span data-stu-id="4e527-128">**Note** The TPM protector option requires the administrator to accept the BIOS prompt to activate and initialize the TPM before the computer is delivered to the end user.</span></span>

 

## <span data-ttu-id="4e527-129">MBAM 客户端对加密硬驱的支持</span><span class="sxs-lookup"><span data-stu-id="4e527-129">MBAM Client support for Encrypted Hard Drives</span></span>


<span data-ttu-id="4e527-130">MBAM 支持在满足 Opal 的 TCG 规范要求和 IEEE 1667 标准的加密硬盘上支持 BitLocker。</span><span class="sxs-lookup"><span data-stu-id="4e527-130">MBAM supports BitLocker on Encrypted Hard Drives that meet TCG specification requirements for Opal as well as IEEE 1667 standards.</span></span> <span data-ttu-id="4e527-131">在这些设备上启用 BitLocker 时，它将在已加密的驱动器上生成密钥并执行管理功能。</span><span class="sxs-lookup"><span data-stu-id="4e527-131">When BitLocker is enabled on these devices, it will generate keys and perform management functions on the encrypted drive.</span></span> <span data-ttu-id="4e527-132">有关详细信息，请参阅[加密的硬驱](https://technet.microsoft.com/library/hh831627.aspx)。</span><span class="sxs-lookup"><span data-stu-id="4e527-132">See [Encrypted Hard Drive](https://technet.microsoft.com/library/hh831627.aspx) for more information.</span></span>


## <span data-ttu-id="4e527-133">相关主题</span><span class="sxs-lookup"><span data-stu-id="4e527-133">Related topics</span></span>


[<span data-ttu-id="4e527-134">规划部署 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="4e527-134">Planning to Deploy MBAM 2.5</span></span>](planning-to-deploy-mbam-25.md)

[<span data-ttu-id="4e527-135">部署 MBAM 2.5 客户端</span><span class="sxs-lookup"><span data-stu-id="4e527-135">Deploying the MBAM 2.5 Client</span></span>](deploying-the-mbam-25-client.md)

 

 
## <span data-ttu-id="4e527-136">已获得 MBAM 的建议？</span><span class="sxs-lookup"><span data-stu-id="4e527-136">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="4e527-137">在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="4e527-137">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="4e527-138">对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="4e527-138">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>




