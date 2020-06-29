---
title: 如何恢复已移动的驱动器
description: 如何恢复已移动的驱动器
author: dansimp
ms.assetid: 0d38ce7e-bc64-473e-ae85-99b7099ca758
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 11/01/2016
ms.openlocfilehash: 9e7e03846e0a94902b699377043237c651939a07
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803349"
---
# <span data-ttu-id="bd8ef-103">如何恢复已移动的驱动器</span><span class="sxs-lookup"><span data-stu-id="bd8ef-103">How to Recover a Moved Drive</span></span>
<span data-ttu-id="bd8ef-104">本主题介绍了如何使用管理和监视网站（也称为帮助桌面）恢复在由 Microsoft BitLocker 管理和监视（MBAM）加密之后移动的操作系统驱动器。</span><span class="sxs-lookup"><span data-stu-id="bd8ef-104">This topic explains how to use the Administration and Monitoring Website (also referred to as the Help Desk) to recover an operating system drive that was moved after being encrypted by Microsoft BitLocker Administration and Monitoring (MBAM).</span></span> <span data-ttu-id="bd8ef-105">移动驱动器后，由于受信任的平台模块（TPM）芯片已更改，因此它不再接受以前计算机中使用的 PIN。</span><span class="sxs-lookup"><span data-stu-id="bd8ef-105">When a drive is moved, it no longer accepts the PIN that was used in the previous computer because the Trusted Platform Module (TPM) chip has changed.</span></span> <span data-ttu-id="bd8ef-106">若要恢复移动的驱动器，您必须获取恢复密钥 ID 才能检索恢复密码。</span><span class="sxs-lookup"><span data-stu-id="bd8ef-106">To recover the moved drive, you must obtain the recovery key ID to retrieve the recovery password.</span></span>

<span data-ttu-id="bd8ef-107">若要恢复移动的驱动器，必须使用管理和监视网站的**驱动器恢复**区域。</span><span class="sxs-lookup"><span data-stu-id="bd8ef-107">To recover a moved drive, you must use the **Drive Recovery** area of the Administration and Monitoring Website.</span></span> <span data-ttu-id="bd8ef-108">要访问**驱动器恢复**区域，你必须被分配 MBAM 帮助台用户角色或 MBAM 高级帮助台用户角色。</span><span class="sxs-lookup"><span data-stu-id="bd8ef-108">To access the **Drive Recovery** area, you must be assigned the MBAM Helpdesk Users role or the MBAM Advanced Helpdesk Users role.</span></span> <span data-ttu-id="bd8ef-109">有关这些角色的详细信息，请参阅[规划 MBAM 2.5 组和帐户](planning-for-mbam-25-groups-and-accounts.md#bkmk-helpdesk-roles)。</span><span class="sxs-lookup"><span data-stu-id="bd8ef-109">For more information about these roles, see [Planning for MBAM 2.5 Groups and Accounts](planning-for-mbam-25-groups-and-accounts.md#bkmk-helpdesk-roles).</span></span>

**<span data-ttu-id="bd8ef-110">恢复移动的驱动器</span><span class="sxs-lookup"><span data-stu-id="bd8ef-110">To recover a moved drive</span></span>**
1.  <span data-ttu-id="bd8ef-111">在包含已移动的驱动器的计算机上，在 Windows 恢复环境（WinRE）模式下启动计算机，或使用 Microsoft 诊断和恢复工具集（DaRT）启动计算机。</span><span class="sxs-lookup"><span data-stu-id="bd8ef-111">On the computer that contains the moved drive, start the computer in Windows Recovery Environment (WinRE) mode, or start the computer by using the Microsoft Diagnostic and Recovery Toolset (DaRT).</span></span>

2.  <span data-ttu-id="bd8ef-112">使用 WinRE 或 DaRT 启动计算机后，MBAM 会将移动的操作系统驱动器视为固定数据驱动器。</span><span class="sxs-lookup"><span data-stu-id="bd8ef-112">After the computer has been started with WinRE or DaRT, MBAM will treat the moved operating system drive as a fixed data drive.</span></span> <span data-ttu-id="bd8ef-113">MBAM 将显示驱动器的恢复密码 ID 并要求输入恢复密码。</span><span class="sxs-lookup"><span data-stu-id="bd8ef-113">MBAM will then display the drive’s recovery password ID and ask for the recovery password.</span></span>

    <span data-ttu-id="bd8ef-114">**注意** 在某些情况下，你可能可以在启动过程中单击 "**我忘记了 PIN** "，然后输入恢复模式以显示恢复密钥 ID。</span><span class="sxs-lookup"><span data-stu-id="bd8ef-114">**Note** In some cases, you may be able to click **I forgot the PIN** during the startup process, and then enter the recovery mode to display the recovery key ID.</span></span>

     

3.  <span data-ttu-id="bd8ef-115">使用恢复密钥 ID 检索恢复密码并通过管理和监视网站解锁驱动器。</span><span class="sxs-lookup"><span data-stu-id="bd8ef-115">Use the recovery key ID to retrieve the recovery password and unlock the drive from the Administration and Monitoring Website.</span></span> <span data-ttu-id="bd8ef-116">有关说明，请参阅[如何在恢复模式下恢复驱动器](how-to-recover-a-drive-in-recovery-mode-mbam-25.md)。</span><span class="sxs-lookup"><span data-stu-id="bd8ef-116">For instructions, see [How to Recover a Drive in Recovery Mode](how-to-recover-a-drive-in-recovery-mode-mbam-25.md).</span></span>

    <span data-ttu-id="bd8ef-117">如果移动的驱动器配置为使用原始计算机上的 TPM 芯片，请完成以下附加步骤。</span><span class="sxs-lookup"><span data-stu-id="bd8ef-117">If the moved drive was configured to use a TPM chip on the original computer, complete the following additional steps.</span></span> <span data-ttu-id="bd8ef-118">否则，恢复过程已完成。</span><span class="sxs-lookup"><span data-stu-id="bd8ef-118">Otherwise, the recovery process is complete.</span></span>

4.  <span data-ttu-id="bd8ef-119">解锁驱动器并完成启动过程后，在 WinRE 模式下打开命令提示符并使用该 `manage-bde` 命令对驱动器进行解密。</span><span class="sxs-lookup"><span data-stu-id="bd8ef-119">After unlocking the drive and completing the start process, open a command prompt in WinRE mode and use the `manage-bde` command to decrypt the drive.</span></span> <span data-ttu-id="bd8ef-120">使用此工具是删除 TPM 以及没有原始 TPM 芯片的引脚保护器的唯一方法。</span><span class="sxs-lookup"><span data-stu-id="bd8ef-120">Using this tool is the only way to remove the TPM plus the PIN protector without the original TPM chip.</span></span> <span data-ttu-id="bd8ef-121">有关该命令的信息 `manage-bde` ，请参阅[manage-bde](https://go.microsoft.com/fwlink/?LinkId=393567)。</span><span class="sxs-lookup"><span data-stu-id="bd8ef-121">For information about the `manage-bde` command, see [Manage-bde](https://go.microsoft.com/fwlink/?LinkId=393567).</span></span>

5.  <span data-ttu-id="bd8ef-122">删除完成后，正常启动计算机。</span><span class="sxs-lookup"><span data-stu-id="bd8ef-122">When the removal is completed, start the computer normally.</span></span> <span data-ttu-id="bd8ef-123">MBAM 代理现在将强制实施该策略，使用新计算机的 TPM 和 PIN 加密驱动器。</span><span class="sxs-lookup"><span data-stu-id="bd8ef-123">The MBAM agent will now enforce the policy to encrypt the drive with the new computer’s TPM plus the PIN.</span></span>



## <span data-ttu-id="bd8ef-124">相关主题</span><span class="sxs-lookup"><span data-stu-id="bd8ef-124">Related topics</span></span>


[<span data-ttu-id="bd8ef-125">使用 MBAM 2.5 执行 BitLocker 管理</span><span class="sxs-lookup"><span data-stu-id="bd8ef-125">Performing BitLocker Management with MBAM 2.5</span></span>](performing-bitlocker-management-with-mbam-25.md)

 

## <span data-ttu-id="bd8ef-126">已获得 MBAM 的建议？</span><span class="sxs-lookup"><span data-stu-id="bd8ef-126">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="bd8ef-127">在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="bd8ef-127">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="bd8ef-128">对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="bd8ef-128">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





