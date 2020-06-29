---
title: 帮助最终用户管理 BitLocker
description: 帮助最终用户管理 BitLocker
author: dansimp
ms.assetid: 47776fb3-2d94-4970-b687-c35ec3dd6c64
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 26ef2bc33a75ff7773b75807ab0e10e5aa67b109
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803636"
---
# <span data-ttu-id="6c895-103">帮助最终用户管理 BitLocker</span><span class="sxs-lookup"><span data-stu-id="6c895-103">Helping End Users Manage BitLocker</span></span>


<span data-ttu-id="6c895-104">丢失或被盗计算机上的内容容易受到未经授权的访问，这可能会给人员和公司带来安全风险。</span><span class="sxs-lookup"><span data-stu-id="6c895-104">Content on a lost or stolen computer is vulnerable to unauthorized access, which can present a security risk to both people and companies.</span></span> <span data-ttu-id="6c895-105">Microsoft BitLocker 管理和监视（MBAM）使用 BitLocker 通过锁定您的计算机帮助防止恶意用户的敏感数据，从而帮助防止未经授权的访问。</span><span class="sxs-lookup"><span data-stu-id="6c895-105">Microsoft BitLocker Administration and Monitoring (MBAM) uses BitLocker to help prevent unauthorized access by locking your computer to help protect sensitive data from malicious users.</span></span>

## <span data-ttu-id="6c895-106">什么是 BitLocker？</span><span class="sxs-lookup"><span data-stu-id="6c895-106">What is BitLocker?</span></span>


<span data-ttu-id="6c895-107">通过加密驱动器，BitLocker 驱动器加密可以为操作系统驱动器、数据驱动器和可移动驱动器（如 USB 拇指驱动器）提供保护。</span><span class="sxs-lookup"><span data-stu-id="6c895-107">BitLocker Drive Encryption can provide protection for operating system drives, data drives, and removable drives (such as a USB thumb drive) by encrypting the drives.</span></span> <span data-ttu-id="6c895-108">根据 BitLocker 的配置方式，用户可能必须提供密钥（密码或 PIN）才能解锁存储在加密驱动器上的信息。</span><span class="sxs-lookup"><span data-stu-id="6c895-108">Depending on how BitLocker is configured, users may have to provide a key (a password or PIN) to unlock the information that is stored on the encrypted drives.</span></span>

<span data-ttu-id="6c895-109">将新文件添加到使用 BitLocker 加密的驱动器时，BitLocker 会自动对其进行加密。</span><span class="sxs-lookup"><span data-stu-id="6c895-109">When you add new files to a drive that is encrypted with BitLocker, BitLocker encrypts them automatically.</span></span> <span data-ttu-id="6c895-110">文件仅在存储在加密驱动器中时保持加密。</span><span class="sxs-lookup"><span data-stu-id="6c895-110">Files remain encrypted only while they are stored in the encrypted drive.</span></span> <span data-ttu-id="6c895-111">将解密复制到其他驱动器或计算机的文件。</span><span class="sxs-lookup"><span data-stu-id="6c895-111">Files that are copied to another drive or computer are decrypted.</span></span> <span data-ttu-id="6c895-112">如果您与其他用户（如通过网络）共享文件，则这些文件会在存储在加密驱动器上时进行加密，但授权用户可以正常访问这些文件。</span><span class="sxs-lookup"><span data-stu-id="6c895-112">If you share files with other users, such as through a network, these files are encrypted while stored on the encrypted drive, but they can be accessed normally by authorized users.</span></span>

<span data-ttu-id="6c895-113">如果您加密操作系统驱动器，BitLocker 会在启动期间检查计算机是否存在可能表示安全风险的任何条件（例如，对 BIOS 的更改或对任何启动文件的更改）。</span><span class="sxs-lookup"><span data-stu-id="6c895-113">If you encrypt the operating system drive, BitLocker checks the computer during startup for any conditions that could represent a security risk (for example, a change to the BIOS or changes to any startup files).</span></span> <span data-ttu-id="6c895-114">如果检测到潜在的安全风险，BitLocker 将锁定操作系统驱动器，并且需要使用特殊的 BitLocker 恢复密钥解锁。</span><span class="sxs-lookup"><span data-stu-id="6c895-114">If a potential security risk is detected, BitLocker will lock the operating system drive and require a special BitLocker recovery key to unlock it.</span></span> <span data-ttu-id="6c895-115">请确保在首次打开 BitLocker 时创建此恢复密钥。</span><span class="sxs-lookup"><span data-stu-id="6c895-115">Make sure that you create this recovery key when you turn on BitLocker for the first time.</span></span> <span data-ttu-id="6c895-116">否则，您可能会永久失去对文件的访问权限。</span><span class="sxs-lookup"><span data-stu-id="6c895-116">Otherwise, you could permanently lose access to your files.</span></span>

<span data-ttu-id="6c895-117">如果加密数据驱动器（固定或可移动），则可以使用密码或智能卡解锁加密的驱动器，或者将驱动器设置为当您登录到计算机时自动解锁。</span><span class="sxs-lookup"><span data-stu-id="6c895-117">If you encrypt data drives (fixed or removable), you can unlock an encrypted drive with a password or a smart card, or set the drive to automatically unlock when you log on to the computer.</span></span>

<span data-ttu-id="6c895-118">除了密码和 Pin，BitLocker 还可以使用在许多较新的计算机中提供的受信任的平台模块（TPM）芯片。</span><span class="sxs-lookup"><span data-stu-id="6c895-118">In addition to passwords and PINs, BitLocker can use the Trusted Platform Module (TPM) chip that is provided in many newer computers.</span></span> <span data-ttu-id="6c895-119">TPM 芯片用于确保你的计算机未被篡改，然后 BitLocker 将无法解锁操作系统驱动器。</span><span class="sxs-lookup"><span data-stu-id="6c895-119">The TPM chip is used to ensure that your computer has not been tampered with before BitLocker will unlock the operating system drive.</span></span> <span data-ttu-id="6c895-120">在加密过程中，你可能需要启用 TPM 芯片。</span><span class="sxs-lookup"><span data-stu-id="6c895-120">During the encryption process, you may have to enable the TPM chip.</span></span> <span data-ttu-id="6c895-121">当您启动计算机时，BitLocker 会向该驱动器中的密钥请求 TPM，并将其解除锁定。</span><span class="sxs-lookup"><span data-stu-id="6c895-121">When you start your computer, BitLocker asks the TPM for the keys to the drive and unlocks it.</span></span> <span data-ttu-id="6c895-122">若要启用 TPM 芯片，必须重新启动计算机，然后在 BIOS 中更改计算机软件的 Windows 之前的设置。</span><span class="sxs-lookup"><span data-stu-id="6c895-122">To enable the TPM chip, you will have to restart your computer and then change a setting in the BIOS, a pre-Windows layer of your computer software.</span></span> <span data-ttu-id="6c895-123">有关 TPM 的详细信息，请参阅[关于计算机 TPM 芯片](about-the-computer-tpm-chip.md)。</span><span class="sxs-lookup"><span data-stu-id="6c895-123">For more information about the TPM, see [About the Computer TPM Chip](about-the-computer-tpm-chip.md).</span></span>

<span data-ttu-id="6c895-124">一旦你的计算机受 BitLocker 保护，你可能需要在计算机每次从休眠唤醒或启动时输入 PIN 或密码。</span><span class="sxs-lookup"><span data-stu-id="6c895-124">Once your computer is protected by BitLocker, you may have to enter a PIN or password every time that the computer wakes from hibernation or starts.</span></span> <span data-ttu-id="6c895-125">您的公司或组织的帮助台可帮助您忘记 PIN 或密码。</span><span class="sxs-lookup"><span data-stu-id="6c895-125">The Help Desk for your company or organization can help if you ever forget your PIN or password.</span></span>

<span data-ttu-id="6c895-126">你可以通过解密驱动器来临时关闭 BitLocker，方法是暂停或永久关闭。</span><span class="sxs-lookup"><span data-stu-id="6c895-126">You can turn off BitLocker, either temporarily, by suspending it, or permanently, by decrypting the drive.</span></span>

<span data-ttu-id="6c895-127">**注意** 由于 BitLocker 会对整个驱动器进行加密，而不仅仅是对单个文件进行加密，因此在驱动器之间移动敏感数据时要小心。</span><span class="sxs-lookup"><span data-stu-id="6c895-127">**Note** Because BitLocker encrypts the whole drive and not just the individual files themselves, be careful when you move sensitive data between drives.</span></span> <span data-ttu-id="6c895-128">如果将文件从受 BitLocker 保护的驱动器移动到非加密驱动器，该文件将不再加密。</span><span class="sxs-lookup"><span data-stu-id="6c895-128">If you move a file from a BitLocker-protected drive to a nonencrypted drive, the file will no longer be encrypted.</span></span>

 

## <span data-ttu-id="6c895-129">关于 BitLocker 加密选项应用程序</span><span class="sxs-lookup"><span data-stu-id="6c895-129">About the BitLocker Encryption Options Application</span></span>


<span data-ttu-id="6c895-130">若要在计算机上解锁硬盘驱动器以及管理 PIN 和密码，请按照此处所述的步骤，使用 Windows 控制面板中的 BitLocker 加密选项应用程序。</span><span class="sxs-lookup"><span data-stu-id="6c895-130">To unlock hard disk drives on your computer and to manage your PIN and passwords, use the BitLocker Encryption Options application in the Windows Control Panel by following the procedure outlined here.</span></span> <span data-ttu-id="6c895-131">你可以输入密码来解锁受保护的驱动器，并且可以使用此应用程序检查附加的驱动器的 BitLocker 状态。</span><span class="sxs-lookup"><span data-stu-id="6c895-131">You can enter passwords to unlock protected drives and can check the BitLocker status of attached drives by using this application.</span></span>

**<span data-ttu-id="6c895-132">打开 "BitLocker 加密选项" 应用程序</span><span class="sxs-lookup"><span data-stu-id="6c895-132">To open the BitLocker Encryption Options application</span></span>**

1.  <span data-ttu-id="6c895-133">单击 "**开始**"，然后选择 **"控制面板"**。</span><span class="sxs-lookup"><span data-stu-id="6c895-133">Click **Start**, and select **Control Panel**.</span></span> <span data-ttu-id="6c895-134">将在新窗口中打开 "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="6c895-134">The Control Panel opens in a new window.</span></span>

2.  <span data-ttu-id="6c895-135">在 "控制面板" 中，选择 **"\*\*\*\*系统和安全**"。</span><span class="sxs-lookup"><span data-stu-id="6c895-135">In **Control Panel**, select **System and Security**.</span></span>

3.  <span data-ttu-id="6c895-136">选择 " **Bitlocker 加密选项**" 以打开 "Bitlocker 加密选项" 应用程序。</span><span class="sxs-lookup"><span data-stu-id="6c895-136">Select **BitLocker Encryption Options** to open the BitLocker Encryption Options application.</span></span>

    <span data-ttu-id="6c895-137">有关可用选项的说明，请参阅以下部分。</span><span class="sxs-lookup"><span data-stu-id="6c895-137">For a description of the available options, see the following section.</span></span>

## <span data-ttu-id="6c895-138">BitLocker 加密选项应用程序上的选项</span><span class="sxs-lookup"><span data-stu-id="6c895-138">Options on the BitLocker Encryption Options Application</span></span>


<span data-ttu-id="6c895-139">使用 "控制面板" 上的 "BitLocker 加密选项" 应用程序，你可以管理你的 PIN 和密码，BitLocker 使用此功能保护你的计算机。</span><span class="sxs-lookup"><span data-stu-id="6c895-139">The BitLocker Encryption Options application on Control Panel lets you manage your PIN and passwords, which BitLocker uses to protect your computer.</span></span>

**<span data-ttu-id="6c895-140">BitLocker 驱动器加密-固定磁盘驱动器：</span><span class="sxs-lookup"><span data-stu-id="6c895-140">BitLocker Drive Encryption – Fixed Disk Drives:</span></span>**

<span data-ttu-id="6c895-141">在此部分中，你可以查看有关连接到计算机的硬盘和当前 BitLocker 加密状态的信息。</span><span class="sxs-lookup"><span data-stu-id="6c895-141">In this section, you can view information about hard disk drives connected to your computer and their current BitLocker Encryption status.</span></span>

-   <span data-ttu-id="6c895-142">**管理您的 PIN** -更改 BitLocker 使用的引脚以解锁操作系统驱动器。</span><span class="sxs-lookup"><span data-stu-id="6c895-142">**Manage your PIN** - changes the PIN used by BitLocker to unlock your operating system drive.</span></span>

-   <span data-ttu-id="6c895-143">**管理密码**-更改 BitLocker 用于解锁其他内部驱动器的密码。</span><span class="sxs-lookup"><span data-stu-id="6c895-143">**Manage your password** - changes the password that is used by BitLocker to unlock your other internal drives.</span></span>

**<span data-ttu-id="6c895-144">BitLocker 驱动器加密-外部驱动器：</span><span class="sxs-lookup"><span data-stu-id="6c895-144">BitLocker Drive Encryption - External Drives:</span></span>**

<span data-ttu-id="6c895-145">在此部分中，你可以查看连接到计算机的外部驱动器（如 USB 拇指驱动器）的信息，以及其当前的 BitLocker 加密状态。</span><span class="sxs-lookup"><span data-stu-id="6c895-145">In this section, you can view information about external drives (such as a USB thumb drive) connected to your computer, and their current BitLocker encryption status.</span></span>

-   <span data-ttu-id="6c895-146">**管理密码**-更改 BitLocker 用于解锁其他内部驱动器的密码。</span><span class="sxs-lookup"><span data-stu-id="6c895-146">**Manage your password** - changes the password that is used by BitLocker to unlock your other internal drives.</span></span>

**<span data-ttu-id="6c895-147">先进</span><span class="sxs-lookup"><span data-stu-id="6c895-147">Advanced:</span></span>**

-   <span data-ttu-id="6c895-148">**TPM 管理**-在单独的窗口中打开 TPM 管理工具。</span><span class="sxs-lookup"><span data-stu-id="6c895-148">**TPM Administration** - opens the TPM Administration tool in a separate window.</span></span> <span data-ttu-id="6c895-149">在这里，你可以配置常见的 TPM 任务和获取有关 TPM 芯片组的信息。</span><span class="sxs-lookup"><span data-stu-id="6c895-149">From here you can configure common TPM tasks and obtain information about the TPM chipset.</span></span> <span data-ttu-id="6c895-150">您必须具有计算机的管理员权限才能访问此工具。</span><span class="sxs-lookup"><span data-stu-id="6c895-150">You must have administrative permissions on your computer to access this tool.</span></span>

-   <span data-ttu-id="6c895-151">**磁盘管理**-打开 "磁盘管理" 工具。</span><span class="sxs-lookup"><span data-stu-id="6c895-151">**Disk Management** -open the Disk Management tool.</span></span> <span data-ttu-id="6c895-152">从这里，你可以查看连接到计算机的所有硬盘的信息，并配置分区和驱动器选项。</span><span class="sxs-lookup"><span data-stu-id="6c895-152">From here you can view the information for all hard drives connected to the computer and configure partitions and drive options.</span></span> <span data-ttu-id="6c895-153">您必须具有计算机的管理员权限才能访问此工具。</span><span class="sxs-lookup"><span data-stu-id="6c895-153">You must have administrative rights on your computer to access this tool.</span></span>

 

 





