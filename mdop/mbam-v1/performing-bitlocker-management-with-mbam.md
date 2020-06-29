---
title: 使用 MBAM 执行 BitLocker 管理
description: 使用 MBAM 执行 BitLocker 管理
author: dansimp
ms.assetid: 2d24390a-87bf-48b3-96a9-3882d6f2a15c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8d0de3711d5b7c3696783a054ee7c7f8220b5356
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803859"
---
# <span data-ttu-id="d813a-103">使用 MBAM 执行 BitLocker 管理</span><span class="sxs-lookup"><span data-stu-id="d813a-103">Performing BitLocker Management with MBAM</span></span>


<span data-ttu-id="d813a-104">部署 Microsoft BitLocker 管理和监视（MBAM）后，你可以配置和使用 MBAM 管理企业 BitLocker 加密。</span><span class="sxs-lookup"><span data-stu-id="d813a-104">After you deploy Microsoft BitLocker Administration and Monitoring (MBAM), you can configure and use MBAM to manage enterprise BitLocker encryption.</span></span> <span data-ttu-id="d813a-105">本节介绍了可通过使用 MBAM 完成的安装后、日常 BitLocker 加密管理任务。</span><span class="sxs-lookup"><span data-stu-id="d813a-105">This section describes post-installation, day-to-day BitLocker encryption management tasks that can be accomplished by using MBAM.</span></span>

## <span data-ttu-id="d813a-106">使用 MBAM 重置 TPM 锁定</span><span class="sxs-lookup"><span data-stu-id="d813a-106">Reset a TPM Lockout with MBAM</span></span>


<span data-ttu-id="d813a-107">受信任的平台模块（TPM）微芯片提供与安全相关的基本功能。</span><span class="sxs-lookup"><span data-stu-id="d813a-107">A Trusted Platform Module (TPM) microchip provides basic security-related functions.</span></span> <span data-ttu-id="d813a-108">这些函数主要通过使用加密密钥来完成。</span><span class="sxs-lookup"><span data-stu-id="d813a-108">These functions are accomplished primarily by the use of encryption keys.</span></span> <span data-ttu-id="d813a-109">TPM 通常安装在计算机或笔记本电脑的主板上，通过使用硬件总线与系统的其余部分进行通信。</span><span class="sxs-lookup"><span data-stu-id="d813a-109">The TPM is typically installed on the motherboard of a computer or laptop and communicates with the rest of the system by using a hardware bus.</span></span> <span data-ttu-id="d813a-110">合并 TPM 的计算机可以创建只能由 TPM 解密的加密密钥。</span><span class="sxs-lookup"><span data-stu-id="d813a-110">Computers that incorporate a TPM can create cryptographic keys that can be decrypted only by the TPM.</span></span> <span data-ttu-id="d813a-111">如果用户输入错误 PIN 的次数过多，可能会发生 TPM 锁定。</span><span class="sxs-lookup"><span data-stu-id="d813a-111">A TPM lockout can occur if a user enters an incorrect PIN too many times.</span></span> <span data-ttu-id="d813a-112">用户在 TPM 锁定之前可以输入不正确的 PIN 的次数因制造商而异。</span><span class="sxs-lookup"><span data-stu-id="d813a-112">The number of times that a user can enter an incorrect PIN before the TPM locks varies from manufacturer to manufacturer.</span></span> <span data-ttu-id="d813a-113">MBAM 管理网站上的密钥恢复数据系统使你能够获取重置 TPM 所有者密码文件。</span><span class="sxs-lookup"><span data-stu-id="d813a-113">The Key Recovery data system on the MBAM administration website enables you to obtain a reset TPM owner password file.</span></span>

[<span data-ttu-id="d813a-114">如何重置 TPM 锁定</span><span class="sxs-lookup"><span data-stu-id="d813a-114">How to Reset a TPM Lockout</span></span>](how-to-reset-a-tpm-lockout-mbam-1.md)

## <span data-ttu-id="d813a-115">通过 MBAM 恢复驱动器</span><span class="sxs-lookup"><span data-stu-id="d813a-115">Recover drives with MBAM</span></span>


<span data-ttu-id="d813a-116">请确保你知道在硬件故障、人员的更改或加密密钥丢失的其他情况下，如何尝试从加密的驱动器恢复数据。</span><span class="sxs-lookup"><span data-stu-id="d813a-116">Make sure that you know how to attempt data recovery from encrypted drives in the event of hardware failure, changes in personnel, or other situations in which encryption keys are lost.</span></span> <span data-ttu-id="d813a-117">MBAM 的加密驱动器恢复功能提供了访问受 BitLocker 保护的卷的数据和可用性所需的工具的捕获和存储，以便在卷进入恢复模式、移动或损坏时访问受 BitLocker 保护的卷。</span><span class="sxs-lookup"><span data-stu-id="d813a-117">The Encrypted Drive Recovery features of MBAM provide the capture and storage of data and availability of tools required to access a BitLocker-protected volume when the volume goes into recovery mode, is moved, or becomes corrupted.</span></span>

[<span data-ttu-id="d813a-118">如何在恢复模式下恢复驱动器</span><span class="sxs-lookup"><span data-stu-id="d813a-118">How to Recover a Drive in Recovery Mode</span></span>](how-to-recover-a-drive-in-recovery-mode-mbam-1.md)

[<span data-ttu-id="d813a-119">如何恢复已移动的驱动器</span><span class="sxs-lookup"><span data-stu-id="d813a-119">How to Recover a Moved Drive</span></span>](how-to-recover-a-moved-drive-mbam-1.md)

[<span data-ttu-id="d813a-120">如何恢复已损坏的驱动器</span><span class="sxs-lookup"><span data-stu-id="d813a-120">How to Recover a Corrupted Drive</span></span>](how-to-recover-a-corrupted-drive-mbam-1.md)

## <span data-ttu-id="d813a-121">使用 MBAM 确定丢失的计算机的 BitLocker 加密状态</span><span class="sxs-lookup"><span data-stu-id="d813a-121">Determine BitLocker Encryption State of lost computers by Using MBAM</span></span>


<span data-ttu-id="d813a-122">使用 MBAM 时，你可以确定丢失或被盗的计算机的上次已知 BitLocker 加密状态。</span><span class="sxs-lookup"><span data-stu-id="d813a-122">When you use MBAM, you can determine the last known BitLocker encryption status of computers that were lost or stolen.</span></span>

[<span data-ttu-id="d813a-123">如何确定丢失计算机的 BitLocker 加密状态</span><span class="sxs-lookup"><span data-stu-id="d813a-123">How to Determine the BitLocker Encryption State of a Lost Computers</span></span>](how-to-determine-the-bitlocker-encryption-state-of-a-lost-computers-mbam-1.md)

## <span data-ttu-id="d813a-124">用于通过 MBAM 执行 BitLocker 管理的其他资源</span><span class="sxs-lookup"><span data-stu-id="d813a-124">Other resources for performing BitLocker Management with MBAM</span></span>


[<span data-ttu-id="d813a-125">MBAM 1.0 的操作</span><span class="sxs-lookup"><span data-stu-id="d813a-125">Operations for MBAM 1.0</span></span>](operations-for-mbam-10.md)

 

 





