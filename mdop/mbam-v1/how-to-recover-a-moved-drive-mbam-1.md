---
title: 如何恢复已移动的驱动器
description: 如何恢复已移动的驱动器
author: dansimp
ms.assetid: 0c7199d8-9463-4f44-9af3-b70eceeaff1d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e73e0878a3102d56494feb33efa69182029988c2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798168"
---
# <span data-ttu-id="9da6b-103">如何恢复已移动的驱动器</span><span class="sxs-lookup"><span data-stu-id="9da6b-103">How to Recover a Moved Drive</span></span>


<span data-ttu-id="9da6b-104">当您移动以前使用 Microsoft BitLocker 管理和监视（MBAM）加密的操作系统驱动器时，必须解决某些问题。</span><span class="sxs-lookup"><span data-stu-id="9da6b-104">When you move an operating system drive that has been previously encrypted by using Microsoft BitLocker Administration and Monitoring (MBAM), you must resolve certain issues.</span></span> <span data-ttu-id="9da6b-105">将 PIN 连接到新计算机后，驱动器将不会接受以前计算机中使用的启动 PIN。</span><span class="sxs-lookup"><span data-stu-id="9da6b-105">After a PIN is attached to the new computer, the drive will not accept the start-up PIN that was used in previous computer.</span></span> <span data-ttu-id="9da6b-106">由于对受信任的平台模块（TPM）芯片的更改，系统认为该 PIN 无效。</span><span class="sxs-lookup"><span data-stu-id="9da6b-106">The system considers the PIN to be invalid because of the change to the Trusted Platform Module (TPM) chip.</span></span> <span data-ttu-id="9da6b-107">必须获取恢复密钥 ID 才能检索恢复密码，以便使用移动的驱动器。</span><span class="sxs-lookup"><span data-stu-id="9da6b-107">You must obtain a recovery key ID to retrieve the recovery password in order to use the moved drive.</span></span> <span data-ttu-id="9da6b-108">若要执行此操作，请使用以下过程。</span><span class="sxs-lookup"><span data-stu-id="9da6b-108">To do this, use the following procedure.</span></span>

**<span data-ttu-id="9da6b-109">恢复移动的驱动器</span><span class="sxs-lookup"><span data-stu-id="9da6b-109">To recover a moved drive</span></span>**

1.  <span data-ttu-id="9da6b-110">在包含移动的驱动器的计算机上，在 Windows 恢复环境（WinRE）模式下启动，或使用 Microsoft 诊断和恢复工具集（DaRT）启动计算机。</span><span class="sxs-lookup"><span data-stu-id="9da6b-110">On the computer that contains the moved drive, start in Windows Recovery Environment (WinRE) mode, or start the computer by using the Microsoft Diagnostics and Recovery Toolset (DaRT).</span></span>

2.  <span data-ttu-id="9da6b-111">使用 WinRE 或 DaRT 启动计算机后，MBAM 会将移动的操作系统驱动器视为数据驱动器。</span><span class="sxs-lookup"><span data-stu-id="9da6b-111">Once the computer has been started with WinRE or DaRT, MBAM will treat the moved operating system drive as a data drive.</span></span> <span data-ttu-id="9da6b-112">MBAM 将显示驱动器的恢复密码 ID 并要求输入恢复密码。</span><span class="sxs-lookup"><span data-stu-id="9da6b-112">MBAM will then display the drive’s recovery password ID and ask for the recovery password.</span></span>

    <span data-ttu-id="9da6b-113">**注意** 在某些情况下，你可能可以在启动过程中单击 "**我忘记 PIN"** 以进入恢复模式。</span><span class="sxs-lookup"><span data-stu-id="9da6b-113">**Note** In some cases, you might be able to click **I forget the PIN** during the startup process to enter the recovery mode.</span></span> <span data-ttu-id="9da6b-114">这还会显示恢复密钥 ID。</span><span class="sxs-lookup"><span data-stu-id="9da6b-114">This also displays the recovery key ID.</span></span>

     

3.  <span data-ttu-id="9da6b-115">在 MBAM 管理网站上，使用恢复密钥 ID 检索恢复密码并解锁驱动器。</span><span class="sxs-lookup"><span data-stu-id="9da6b-115">On the MBAM administration website, use the recovery key ID to retrieve the recovery password and unlock the drive.</span></span>

4.  <span data-ttu-id="9da6b-116">如果移动的驱动器配置为使用原始计算机上的 TPM 芯片，则必须在解锁驱动器并完成启动过程后执行其他步骤。</span><span class="sxs-lookup"><span data-stu-id="9da6b-116">If the moved drive was configured to use a TPM chip on the original computer, you must take additional steps after you unlock the drive and complete the start process.</span></span> <span data-ttu-id="9da6b-117">在 WinRE 模式中，打开命令提示符，然后使用**manage-bde**工具解密驱动器。</span><span class="sxs-lookup"><span data-stu-id="9da6b-117">In WinRE mode, open a command prompt and use the **manage-bde** tool to decrypt the drive.</span></span> <span data-ttu-id="9da6b-118">使用此工具的唯一方法是删除没有原始 TPM 芯片的 TPM 加针保护。</span><span class="sxs-lookup"><span data-stu-id="9da6b-118">The use of this tool is the only way to remove the TPM-plus-PIN protection without the original TPM chip.</span></span>

5.  <span data-ttu-id="9da6b-119">删除完成后，正常启动系统。</span><span class="sxs-lookup"><span data-stu-id="9da6b-119">After the removal is complete, start the system normally.</span></span> <span data-ttu-id="9da6b-120">MBAM 代理将继续实施策略，以使用新计算机的 TPM 加针加密驱动器。</span><span class="sxs-lookup"><span data-stu-id="9da6b-120">The MBAM agent will proceed to enforce the policy to encrypt the drive with the new computer’s TPM plus PIN.</span></span>

## <span data-ttu-id="9da6b-121">相关主题</span><span class="sxs-lookup"><span data-stu-id="9da6b-121">Related topics</span></span>


[<span data-ttu-id="9da6b-122">使用 MBAM 执行 BitLocker 管理</span><span class="sxs-lookup"><span data-stu-id="9da6b-122">Performing BitLocker Management with MBAM</span></span>](performing-bitlocker-management-with-mbam.md)

 

 





