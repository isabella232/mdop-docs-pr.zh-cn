---
title: 如何恢复已移动的驱动器
description: 如何恢复已移动的驱动器
author: dansimp
ms.assetid: 697cd78d-962c-411e-901a-2e9220ba6552
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: bd0d43f2eea95fe71225a50e7fa68d4fb1c35485
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803693"
---
# <span data-ttu-id="ee98e-103">如何恢复已移动的驱动器</span><span class="sxs-lookup"><span data-stu-id="ee98e-103">How to Recover a Moved Drive</span></span>


<span data-ttu-id="ee98e-104">当你移动使用 Microsoft BitLocker 管理和监视（MBAM）加密的操作系统驱动器时，由于受信任的平台模块（TPM）芯片发生更改，因此驱动器不会接受以前计算机中使用的 PIN。</span><span class="sxs-lookup"><span data-stu-id="ee98e-104">When you move an operating system drive that is encrypted by using Microsoft BitLocker Administration and Monitoring (MBAM), the drive will not accept the PIN that was used in a previous computer because of the change to the Trusted Platform Module (TPM) chip.</span></span> <span data-ttu-id="ee98e-105">若要使用移动的驱动器，你将需要获取恢复密钥 ID 以检索恢复密码的方法。</span><span class="sxs-lookup"><span data-stu-id="ee98e-105">To use the moved drive, you will need a way to obtain the recovery key ID to retrieve the recovery password.</span></span> <span data-ttu-id="ee98e-106">使用以下过程恢复已移动的驱动器。</span><span class="sxs-lookup"><span data-stu-id="ee98e-106">Use the following procedure to recover a drive that has moved.</span></span>

**<span data-ttu-id="ee98e-107">恢复移动的驱动器</span><span class="sxs-lookup"><span data-stu-id="ee98e-107">To recover a moved drive</span></span>**

1.  <span data-ttu-id="ee98e-108">在包含已移动的驱动器的计算机上，在 Windows 恢复环境（WinRE）模式下启动计算机，或使用 Microsoft 诊断和恢复工具集（DaRT）启动计算机。</span><span class="sxs-lookup"><span data-stu-id="ee98e-108">On the computer that contains the moved drive, start the computer in Windows recovery environment (WinRE) mode, or start the computer by using the Microsoft Diagnostic and Recovery Toolset (DaRT).</span></span>

2.  <span data-ttu-id="ee98e-109">当计算机使用 WinRE 或 DaRT 启动后，Microsoft BitLocker 管理和监视会将移动的操作系统驱动器视为数据驱动器。</span><span class="sxs-lookup"><span data-stu-id="ee98e-109">Once the computer has been started with WinRE or DaRT, Microsoft BitLocker Administration and Monitoring will treat the moved operating system drive as a data drive.</span></span> <span data-ttu-id="ee98e-110">MBAM 将显示驱动器的恢复密码 ID 并要求输入恢复密码。</span><span class="sxs-lookup"><span data-stu-id="ee98e-110">MBAM will then display the drive’s recovery password ID and ask for the recovery password.</span></span>

    <span data-ttu-id="ee98e-111">**注意** 在某些情况下，你可能可以在启动过程中单击 "**我忘记了 PIN** "，然后输入恢复模式以显示恢复密钥 ID。</span><span class="sxs-lookup"><span data-stu-id="ee98e-111">**Note** In some cases, you may be able to click **I forgot the PIN** during the startup process, and then enter the recovery mode to display the recovery key ID.</span></span>

     

3.  <span data-ttu-id="ee98e-112">使用恢复密钥 ID 检索恢复密码并通过管理和监视网站解锁驱动器。</span><span class="sxs-lookup"><span data-stu-id="ee98e-112">Use the recovery key ID to retrieve the recovery password and unlock the drive from the Administration and Monitoring website.</span></span>

4.  <span data-ttu-id="ee98e-113">如果移动的驱动器配置为使用原始计算机上的 TPM 芯片，则必须在解锁驱动器并完成启动过程后执行其他步骤。</span><span class="sxs-lookup"><span data-stu-id="ee98e-113">If the moved drive was configured to use a TPM chip on the original computer, you must take additional steps after unlocking the drive and completing the start process.</span></span> <span data-ttu-id="ee98e-114">在 WinRE 模式中，打开命令提示符，然后使用**manage-bde**工具解密驱动器。</span><span class="sxs-lookup"><span data-stu-id="ee98e-114">In WinRE mode, open a command prompt and use the **manage-bde** tool to decrypt the drive.</span></span> <span data-ttu-id="ee98e-115">使用此工具是删除 TPM 以及不使用原始 TPM 芯片的 PIN 保护器的唯一方法。</span><span class="sxs-lookup"><span data-stu-id="ee98e-115">Using this tool is the only way to remove the TPM plus PIN protector without the original TPM chip.</span></span>

5.  <span data-ttu-id="ee98e-116">删除完成后，正常启动计算机。</span><span class="sxs-lookup"><span data-stu-id="ee98e-116">Once the removal is completed, start the computer normally.</span></span> <span data-ttu-id="ee98e-117">MBAM 代理现在将强制策略使用新计算机的 TPM 和 PIN 加密驱动器。</span><span class="sxs-lookup"><span data-stu-id="ee98e-117">The MBAM agent will now enforce the policy to encrypt the drive with the new computer’s TPM plus PIN.</span></span>

## <span data-ttu-id="ee98e-118">相关主题</span><span class="sxs-lookup"><span data-stu-id="ee98e-118">Related topics</span></span>


[<span data-ttu-id="ee98e-119">使用 MBAM 执行 BitLocker 管理</span><span class="sxs-lookup"><span data-stu-id="ee98e-119">Performing BitLocker Management with MBAM</span></span>](performing-bitlocker-management-with-mbam-mbam-2.md)

 

 





