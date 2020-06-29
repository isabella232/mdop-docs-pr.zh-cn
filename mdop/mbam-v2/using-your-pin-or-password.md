---
title: 使用 PIN 或密码
description: 使用 PIN 或密码
author: dansimp
ms.assetid: 7fe2aef4-d3e0-49c8-877d-7fee13dc5b7b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b8c4b894b8f3e14d2a5cfb39e744fa43874c6753
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803439"
---
# <span data-ttu-id="adb61-103">使用 PIN 或密码</span><span class="sxs-lookup"><span data-stu-id="adb61-103">Using Your PIN or Password</span></span>


<span data-ttu-id="adb61-104">BitLocker 通过要求使用个人识别码（PIN）或密码解锁计算机上存储的信息来帮助保护计算机的安全。</span><span class="sxs-lookup"><span data-stu-id="adb61-104">BitLocker helps secure your computer by requiring a personal identification number (PIN) or password to unlock the information that is stored on your computer.</span></span> <span data-ttu-id="adb61-105">PIN 或密码要求由你的组织设置，并取决于要加密的驱动器类型。</span><span class="sxs-lookup"><span data-stu-id="adb61-105">The PIN or password requirements are set by your organization and depend on the kind of drive being encrypted.</span></span> <span data-ttu-id="adb61-106">在未输入 PIN 或密码的情况下，无法查看加密驱动器上的数据。</span><span class="sxs-lookup"><span data-stu-id="adb61-106">Data on the encrypted drives cannot be viewed without entering the PIN or password.</span></span> <span data-ttu-id="adb61-107">如果你的计算机硬件包含启用的受信任平台模块（TPM），则 TPM 芯片会在你的计算机上启动 Windows 之前提示你输入 PIN。</span><span class="sxs-lookup"><span data-stu-id="adb61-107">If your computer hardware includes an enabled Trusted Platform Module (TPM), the TPM chip prompts you for your PIN before Windows starts on your computer.</span></span>

## <span data-ttu-id="adb61-108">关于您的 BitLocker PIN 和密码</span><span class="sxs-lookup"><span data-stu-id="adb61-108">About Your BitLocker PIN and Passwords</span></span>


<span data-ttu-id="adb61-109">您的公司指定 PIN 或密码所需的复杂程度。</span><span class="sxs-lookup"><span data-stu-id="adb61-109">Your company specifies the complexity required for your PIN or password.</span></span> <span data-ttu-id="adb61-110">在 BitLocker 设置过程中，将介绍这些对 PIN 或密码的要求。</span><span class="sxs-lookup"><span data-stu-id="adb61-110">These requirements for your PIN or password are explained during the BitLocker setup process.</span></span>

<span data-ttu-id="adb61-111">密码用于解锁计算机上不包含操作系统的驱动器。</span><span class="sxs-lookup"><span data-stu-id="adb61-111">The password is used to unlock drives on your computer that do not contain the operating system.</span></span> <span data-ttu-id="adb61-112">在启动期间请求 PIN 后，BitLocker 将询问你的密码。</span><span class="sxs-lookup"><span data-stu-id="adb61-112">BitLocker will ask for your password after the PIN is requested during startup.</span></span> <span data-ttu-id="adb61-113">计算机上的每个受 BitLocker 保护的硬盘都有自己的唯一密码。</span><span class="sxs-lookup"><span data-stu-id="adb61-113">Each BitLocker protected hard disk on your computer has its own unique password.</span></span> <span data-ttu-id="adb61-114">无法解锁受 BitLocker 保护的驱动器，直到你提供密码。</span><span class="sxs-lookup"><span data-stu-id="adb61-114">You cannot unlock a BitLocker protected drive until you provide your password.</span></span>

<span data-ttu-id="adb61-115">**注意** 您的技术支持人员可能会将驱动器设置为自动解锁。</span><span class="sxs-lookup"><span data-stu-id="adb61-115">**Note** Your Help Desk may set drives to unlock automatically.</span></span> <span data-ttu-id="adb61-116">这样便无需提供 PIN 或密码即可查看驱动器上的信息。</span><span class="sxs-lookup"><span data-stu-id="adb61-116">This eliminates the need to provide a PIN or password to view the information on the drives.</span></span>

 

## <span data-ttu-id="adb61-117">如果忘记了 PIN 或密码，请解锁你的计算机</span><span class="sxs-lookup"><span data-stu-id="adb61-117">Unlocking Your Computer if You Forget Your PIN or Password</span></span>


<span data-ttu-id="adb61-118">如果您忘记了 PIN 或密码，您的技术支持人员可以帮助您解锁受 BitLocker 保护的驱动器。</span><span class="sxs-lookup"><span data-stu-id="adb61-118">If you forget your PIN or password, your Help Desk can help you unlock BitLocker protected drives.</span></span> <span data-ttu-id="adb61-119">若要解除锁定使用 BitLocker 保护的驱动器，请与您的技术支持人员联系（如果需要帮助）。</span><span class="sxs-lookup"><span data-stu-id="adb61-119">To unlock a drive protected with BitLocker, contact your Help Desk if you need help.</span></span>

**<span data-ttu-id="adb61-120">如果忘记了 PIN 或密码，如何解锁你的计算机</span><span class="sxs-lookup"><span data-stu-id="adb61-120">How to unlock your computer if you forget your PIN or password</span></span>**

1.  <span data-ttu-id="adb61-121">当您与技术支持人员联系时，您需要向他们提供以下信息：</span><span class="sxs-lookup"><span data-stu-id="adb61-121">When you contact your Help Desk, you will need to provide them with the following information:</span></span>

    -   <span data-ttu-id="adb61-122">您的用户名</span><span class="sxs-lookup"><span data-stu-id="adb61-122">Your user name</span></span>

    -   <span data-ttu-id="adb61-123">您的域</span><span class="sxs-lookup"><span data-stu-id="adb61-123">Your domain</span></span>

    -   <span data-ttu-id="adb61-124">恢复密钥 ID 的前八位数字。</span><span class="sxs-lookup"><span data-stu-id="adb61-124">The first eight digits of your recovery key ID.</span></span> <span data-ttu-id="adb61-125">这是32位的代码，如果你忘记 PIN 或密码，将显示 BitLocker。</span><span class="sxs-lookup"><span data-stu-id="adb61-125">This is a 32-digit code that BitLocker will display if you forget your PIN or password.</span></span>

        -   <span data-ttu-id="adb61-126">如果您忘记了 PIN，则必须输入恢复密钥 ID 的前八位数字，它将显示在 BitLocker 恢复控制台中。</span><span class="sxs-lookup"><span data-stu-id="adb61-126">If you forget your PIN, you will have to enter the first eight digits of the recovery key ID, which will appear in the BitLocker Recovery console.</span></span> <span data-ttu-id="adb61-127">BitLocker 恢复控制台是 Windows 内置屏幕，如果不输入正确的 PIN 码，将显示该屏幕。</span><span class="sxs-lookup"><span data-stu-id="adb61-127">The BitLocker Recovery console is a pre-Windows screen that will be displayed if you do not enter the correct PIN.</span></span>

        -   <span data-ttu-id="adb61-128">如果您忘记了密码，请在 "BitLocker 加密选项" 控制面板应用程序中查找恢复密钥 ID。</span><span class="sxs-lookup"><span data-stu-id="adb61-128">If you forget your password, look for the recovery key ID in the BitLocker Encryption Options Control Panel application.</span></span> <span data-ttu-id="adb61-129">选择 "**解锁驱动器**"，然后单击 "**我不记得我的密码**"。</span><span class="sxs-lookup"><span data-stu-id="adb61-129">Select **Unlock Drive** and then click **I cannot remember my password**.</span></span> <span data-ttu-id="adb61-130">然后，BitLocker "加密选项" 应用程序将显示您提供给帮助台的恢复密钥 ID。</span><span class="sxs-lookup"><span data-stu-id="adb61-130">The BitLocker Encryption Options application will then display a recovery key ID that you provide to Help Desk.</span></span>

2.  <span data-ttu-id="adb61-131">技术支持人员收到必要的信息后，将通过手机或通过电子邮件向你提供恢复密钥。</span><span class="sxs-lookup"><span data-stu-id="adb61-131">Once your Help Desk receives the necessary information, it will provide you with a recovery key over the phone or through e-mail.</span></span>

    -   <span data-ttu-id="adb61-132">如果忘记了 PIN，请在 BitLocker 恢复控制台中输入恢复密钥以解锁你的计算机。</span><span class="sxs-lookup"><span data-stu-id="adb61-132">If you forgot your PIN, enter the recovery key in the BitLocker Recovery console to unlock your computer.</span></span>

    -   <span data-ttu-id="adb61-133">如果您忘记了密码，请在 "BitLocker 加密选项" 控制面板应用程序中输入恢复密钥，在您之前找到恢复密钥 ID 的同一位置。</span><span class="sxs-lookup"><span data-stu-id="adb61-133">If you forgot your password, enter the recovery key in the BitLocker Encryption Options Control Panel application, in the same location where you found the recovery key ID earlier.</span></span> <span data-ttu-id="adb61-134">这将解锁受保护的硬盘。</span><span class="sxs-lookup"><span data-stu-id="adb61-134">This will unlock the protected hard drive.</span></span>

## <span data-ttu-id="adb61-135">更改 PIN 或密码</span><span class="sxs-lookup"><span data-stu-id="adb61-135">Changing your PIN or Password</span></span>


<span data-ttu-id="adb61-136">必须先解锁驱动器，然后才能更改受 BitLocker 保护的驱动器上的密码。</span><span class="sxs-lookup"><span data-stu-id="adb61-136">Before you can change the password on a BitLocker protected drive, you must unlock the drive.</span></span> <span data-ttu-id="adb61-137">如果驱动器未解锁，请选择 "**解锁驱动器**"，然后输入您的当前密码。</span><span class="sxs-lookup"><span data-stu-id="adb61-137">If the drive is not unlocked, select **Unlock Drive**, and then enter your current password.</span></span> <span data-ttu-id="adb61-138">解锁驱动器后，您可以选择 "**管理密码**" 以更改当前密码。</span><span class="sxs-lookup"><span data-stu-id="adb61-138">As soon as the drive is unlocked, you can select **Manage your Password** to change your current password.</span></span>

**<span data-ttu-id="adb61-139">如何更改 PIN 或密码</span><span class="sxs-lookup"><span data-stu-id="adb61-139">How to Change your PIN or password</span></span>**

1.  <span data-ttu-id="adb61-140">单击 "**开始**"，然后选择 **"控制面板"**。</span><span class="sxs-lookup"><span data-stu-id="adb61-140">Click **Start**, and then select **Control Panel**.</span></span> <span data-ttu-id="adb61-141">将在新窗口中打开 "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="adb61-141">Control Panel opens in a new window.</span></span>

2.  <span data-ttu-id="adb61-142">选择 "**系统和安全**"，然后选择 " **BitLocker 加密选项**"。</span><span class="sxs-lookup"><span data-stu-id="adb61-142">Select **System and Security**, and then select **BitLocker Encryption Options**.</span></span>

    -   <span data-ttu-id="adb61-143">若要更改 PIN，请选择 "**管理你的 pin**"。</span><span class="sxs-lookup"><span data-stu-id="adb61-143">To change your PIN, select **Manage Your PIN**.</span></span> <span data-ttu-id="adb61-144">在两个字段中键入新的 PIN 码，然后选择 "**重置 PIN**"。</span><span class="sxs-lookup"><span data-stu-id="adb61-144">Type your new PIN into both fields and select **Reset PIN**.</span></span>

    -   <span data-ttu-id="adb61-145">若要更改密码，请选择 "**管理密码**"。</span><span class="sxs-lookup"><span data-stu-id="adb61-145">To change your password, select **Manage Your Password**.</span></span> <span data-ttu-id="adb61-146">在两个字段中输入新密码，然后选择 "**重置密码**"。</span><span class="sxs-lookup"><span data-stu-id="adb61-146">Enter your new password into both fields and select **Reset Password**.</span></span>

 

 





