---
title: 计划 MBAM 2.0 客户端部署
description: 计划 MBAM 2.0 客户端部署
author: dansimp
ms.assetid: 3a92cf29-092f-4cad-bdfa-d5f6aafe554b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c3a7383188d4064247d8e493c8e6125fc24a1d2b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798091"
---
# <span data-ttu-id="6ecb3-103">计划 MBAM 2.0 客户端部署</span><span class="sxs-lookup"><span data-stu-id="6ecb3-103">Planning for MBAM 2.0 Client Deployment</span></span>


<span data-ttu-id="6ecb3-104">根据你部署 Microsoft BitLocker 管理和监视（MBAM）客户端的时间，你可以在你的组织中的计算机上启用 BitLocker 驱动器加密，方法是在最终用户收到计算机之前或之后。</span><span class="sxs-lookup"><span data-stu-id="6ecb3-104">Depending on when you deploy the Microsoft BitLocker Administration and Monitoring (MBAM) Client, you can enable BitLocker drive encryption on a computer in your organization either before the end user receives the computer or afterwards.</span></span> <span data-ttu-id="6ecb3-105">对于 MBAM 独立版和 Configuration Manager 拓扑，你必须为 MBAM 配置组策略设置。</span><span class="sxs-lookup"><span data-stu-id="6ecb3-105">For both the MBAM Stand-alone and the Configuration Manager topologies, you have to configure Group Policy settings for MBAM.</span></span>

<span data-ttu-id="6ecb3-106">如果你使用的是 MBAM 独立拓扑，建议您使用企业软件部署系统将 MBAM 客户端软件部署到最终用户计算机。</span><span class="sxs-lookup"><span data-stu-id="6ecb3-106">If you are using the MBAM Stand-alone topology, it is recommended that you use an enterprise software deployment system to deploy the MBAM Client software to end-user computers.</span></span>

<span data-ttu-id="6ecb3-107">如果使用 Configuration Manager 拓扑部署 MBAM，则可以使用 Configuration Manager 将 MBAM 客户端软件部署到最终用户计算机。</span><span class="sxs-lookup"><span data-stu-id="6ecb3-107">If you deploy MBAM with the Configuration Manager topology, you can use Configuration Manager to deploy the MBAM Client software to end-user computers.</span></span> <span data-ttu-id="6ecb3-108">在配置管理器中，MBAM 安装将创建 MBAM 可管理的计算机的集合。</span><span class="sxs-lookup"><span data-stu-id="6ecb3-108">In Configuration Manager, the MBAM installation creates a collection of computers that MBAM can manage.</span></span> <span data-ttu-id="6ecb3-109">此集合包括的工作站和设备没有受信任的平台模块（TPM），但运行的是 Windows 8。</span><span class="sxs-lookup"><span data-stu-id="6ecb3-109">This collection includes workstations and devices that do not have a Trusted Platform Module (TPM), but that are running Windows 8.</span></span>

<span data-ttu-id="6ecb3-110">**注意** 如果你使用的是 Configuration Manager 2007，则不支持 MBAM 的集成 Configuration Manager 安装的 Windows To Go。</span><span class="sxs-lookup"><span data-stu-id="6ecb3-110">**Note** Windows To Go is not supported for integrated Configuration Manager installations of MBAM if you are using Configuration Manager 2007.</span></span>

 

## <span data-ttu-id="6ecb3-111">部署 MBAM 客户端以在将计算机分发给最终用户后启用 BitLocker 加密</span><span class="sxs-lookup"><span data-stu-id="6ecb3-111">Deploying the MBAM Client to Enable BitLocker Encryption After Computer Distribution to End Users</span></span>


<span data-ttu-id="6ecb3-112">配置组策略后，你可以使用企业软件部署系统产品（如 Microsoft System Center Configuration Manager 或 Active Directory 域服务（AD DS））将 MBAM 客户端安装的 Windows Installer 文件部署到目标计算机。</span><span class="sxs-lookup"><span data-stu-id="6ecb3-112">After you configure Group Policy, you can use an enterprise software deployment system product like Microsoft System Center Configuration Manager or Active Directory Domain Services (AD DS) to deploy the Windows Installer files of the MBAM Client installation to target computers.</span></span> <span data-ttu-id="6ecb3-113">若要部署 MBAM 客户端，你可以使用32位或64位 MbamClientSetup.exe 文件或 MBAMClient.msi 文件，这些文件与 MBAM 软件一起提供。</span><span class="sxs-lookup"><span data-stu-id="6ecb3-113">To deploy the MBAM Client, you can use either the 32-bit or 64-bit MbamClientSetup.exe files or MBAMClient.msi files, which are provided with the MBAM software.</span></span>

<span data-ttu-id="6ecb3-114">在将计算机分配给客户端计算机之后部署 MBAM 客户端时，系统会提示最终用户对其计算机进行加密。</span><span class="sxs-lookup"><span data-stu-id="6ecb3-114">When you deploy the MBAM Client after you distribute computers to client computers, end users are prompted to encrypt their computer.</span></span> <span data-ttu-id="6ecb3-115">这使 MBAM 能够收集包含 PIN 和密码的数据，然后开始加密过程。</span><span class="sxs-lookup"><span data-stu-id="6ecb3-115">This enables MBAM to collect the data, which includes the PIN and password, and then to begin the encryption process.</span></span>

<span data-ttu-id="6ecb3-116">**注意** 在此方法中，如果尚未激活该芯片，则会提示拥有 TPM 芯片的计算机的用户激活并初始化 TPM 芯片。</span><span class="sxs-lookup"><span data-stu-id="6ecb3-116">**Note** In this approach, users who have computers with a TPM chip are prompted to activate and initialize the TPM chip if the chip has not been previously activated.</span></span>

 

## <span data-ttu-id="6ecb3-117">在将计算机分发给最终用户之前使用 MBAM 客户端启用 BitLocker 加密</span><span class="sxs-lookup"><span data-stu-id="6ecb3-117">Using the MBAM Client to Enable BitLocker Encryption Before Computer Distribution to End Users</span></span>


<span data-ttu-id="6ecb3-118">在同时接收和配置计算机的组织中，以及计算机具有兼容的 TPM 芯片的地方，你可以在向每台计算机上安装任何用户数据之前，安装 MBAM 客户端来管理该计算机上的 BitLocker 加密。</span><span class="sxs-lookup"><span data-stu-id="6ecb3-118">In organizations where computers are received and configured centrally, and where computers have a compliant TPM chip, you can install the MBAM Client to manage BitLocker encryption on each computer before any user data is written to it.</span></span> <span data-ttu-id="6ecb3-119">此过程的优点是，每台计算机都将与 BitLocker 加密兼容。</span><span class="sxs-lookup"><span data-stu-id="6ecb3-119">The benefit of this process is that every computer will then be BitLocker encryption-compliant.</span></span> <span data-ttu-id="6ecb3-120">此方法不依赖于用户操作，因为管理员已加密计算机。</span><span class="sxs-lookup"><span data-stu-id="6ecb3-120">This method does not rely on user action because the administrator has already encrypted the computer.</span></span> <span data-ttu-id="6ecb3-121">此方案的一个关键假设是，组织的策略在将计算机交付给用户之前安装企业的 Windows 映像。</span><span class="sxs-lookup"><span data-stu-id="6ecb3-121">A key assumption for this scenario is that the policy of the organization installs a corporate Windows image before the computer is delivered to the user.</span></span>

<span data-ttu-id="6ecb3-122">如果你的组织希望使用 TPM 芯片加密计算机，管理员将添加 TPM 保护程序以加密计算机的操作系统卷。</span><span class="sxs-lookup"><span data-stu-id="6ecb3-122">If your organization wants to use the TPM chip to encrypt computers, the administrator adds the TPM protector to encrypt the operating system volume of the computer.</span></span> <span data-ttu-id="6ecb3-123">如果你的组织希望使用 TPM 芯片和 PIN 保护器，则管理员使用 TPM 保护程序对操作系统卷进行加密，然后用户首次登录时选择 PIN。</span><span class="sxs-lookup"><span data-stu-id="6ecb3-123">If your organization wants to use the TPM chip and a PIN protector, the administrator encrypts the operating system volume with the TPM protector, and then users select a PIN when they log on for the first time.</span></span> <span data-ttu-id="6ecb3-124">如果您的组织决定仅使用引脚保护器，则管理员不必先加密卷。</span><span class="sxs-lookup"><span data-stu-id="6ecb3-124">If your organization decides to use only the PIN protector, the administrator does not have to encrypt the volume first.</span></span> <span data-ttu-id="6ecb3-125">当用户登录时，Microsoft BitLocker 管理和监视会提示他们提供 PIN 或 PIN 和密码，以便在以后的计算机重启时使用。</span><span class="sxs-lookup"><span data-stu-id="6ecb3-125">When users log on, Microsoft BitLocker Administration and Monitoring prompts them to provide a PIN, or a PIN and password to be used on later computer restarts.</span></span>

<span data-ttu-id="6ecb3-126">**注意** TPM 保护程序选项要求管理员在将计算机交付给用户之前接受激活和初始化 TPM 的 BIOS 提示。</span><span class="sxs-lookup"><span data-stu-id="6ecb3-126">**Note** The TPM protector option requires the administrator to accept the BIOS prompt to activate and initialize the TPM before the computer is delivered to the user.</span></span>

 

## <span data-ttu-id="6ecb3-127">相关主题</span><span class="sxs-lookup"><span data-stu-id="6ecb3-127">Related topics</span></span>


[<span data-ttu-id="6ecb3-128">计划部署 MBAM 2.0</span><span class="sxs-lookup"><span data-stu-id="6ecb3-128">Planning to Deploy MBAM 2.0</span></span>](planning-to-deploy-mbam-20-mbam-2.md)

[<span data-ttu-id="6ecb3-129">部署 MBAM 2.0 客户端</span><span class="sxs-lookup"><span data-stu-id="6ecb3-129">Deploying the MBAM 2.0 Client</span></span>](deploying-the-mbam-20-client-mbam-2.md)

 

 





