---
title: 使用 MBAM 执行 BitLocker 管理
description: 使用 MBAM 执行 BitLocker 管理
author: dansimp
ms.assetid: 9bfc6c67-f12c-4daa-8f08-5884fb47443c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d261ec4fa789cd331209afe1c2f1858d627209a3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803980"
---
# <span data-ttu-id="2fb93-103">使用 MBAM 执行 BitLocker 管理</span><span class="sxs-lookup"><span data-stu-id="2fb93-103">Performing BitLocker Management with MBAM</span></span>


<span data-ttu-id="2fb93-104">在规划并部署 Microsoft BitLocker 管理和监视（MBAM）之后，你可以配置和使用它来管理企业 BitLocker 加密。</span><span class="sxs-lookup"><span data-stu-id="2fb93-104">After planning and then deploying Microsoft BitLocker Administration and Monitoring (MBAM), you can configure and use it to manage enterprise BitLocker encryption.</span></span> <span data-ttu-id="2fb93-105">本部分中的信息介绍了通过使用 Microsoft BitLocker 管理和监视来完成的安装后的每天 BitLocker 加密管理任务。</span><span class="sxs-lookup"><span data-stu-id="2fb93-105">The information in this section describes post-installation day-to-day BitLocker encryption management tasks that are accomplished by using Microsoft BitLocker Administration and Monitoring.</span></span>

## <span data-ttu-id="2fb93-106">使用 MBAM 重置 TPM 锁定</span><span class="sxs-lookup"><span data-stu-id="2fb93-106">Reset a TPM Lockout by Using MBAM</span></span>


<span data-ttu-id="2fb93-107">受信任的平台模块（TPM）是一种微芯片，旨在提供基本的与安全相关的功能，主要涉及加密密钥。</span><span class="sxs-lookup"><span data-stu-id="2fb93-107">A Trusted Platform Module (TPM) is a microchip that is designed to provide basic security-related functions, primarily involving encryption keys.</span></span> <span data-ttu-id="2fb93-108">TPM 通常安装在计算机或笔记本电脑的主板上，并通过使用硬件总线与系统的其余部分进行通信。</span><span class="sxs-lookup"><span data-stu-id="2fb93-108">The TPM is usually installed on the motherboard of a computer or laptop, and communicates with the rest of the system by using a hardware bus.</span></span> <span data-ttu-id="2fb93-109">合并 TPM 的计算机能够创建加密密钥并对其进行加密，以便仅可由 TPM 解密。</span><span class="sxs-lookup"><span data-stu-id="2fb93-109">Computers that incorporate a TPM have the ability to create cryptographic keys and encrypt them so that they can be decrypted only by the TPM.</span></span>

<span data-ttu-id="2fb93-110">如果用户输入错误 PIN 的次数过多，可能会发生 TPM 锁定。</span><span class="sxs-lookup"><span data-stu-id="2fb93-110">A TPM lockout can occur if a user enters the incorrect PIN too many times.</span></span> <span data-ttu-id="2fb93-111">用户在 TPM 锁定之前可以输入不正确的 PIN 的次数因制造商而异。</span><span class="sxs-lookup"><span data-stu-id="2fb93-111">The number of times that a user can enter an incorrect PIN before the TPM locks varies from manufacturer to manufacturer.</span></span> <span data-ttu-id="2fb93-112">你可以使用 MBAM 访问 "管理和监视" 网站中的集中式密钥恢复数据系统，在此情况下，你可以在提供计算机 ID 和关联的用户标识符时检索 TPM 所有者密码文件。</span><span class="sxs-lookup"><span data-stu-id="2fb93-112">You can use MBAM to access the centralized Key Recovery data system in the Administration and Monitoring website, where you can retrieve a TPM owner password file when you supply a computer ID and associated user identifier.</span></span>

[<span data-ttu-id="2fb93-113">如何重置 TPM 锁定</span><span class="sxs-lookup"><span data-stu-id="2fb93-113">How to Reset a TPM Lockout</span></span>](how-to-reset-a-tpm-lockout-mbam-2.md)

## <span data-ttu-id="2fb93-114">通过 MBAM 恢复驱动器</span><span class="sxs-lookup"><span data-stu-id="2fb93-114">Recover Drives with MBAM</span></span>


<span data-ttu-id="2fb93-115">当处理数据加密时（尤其是在企业环境中），请考虑在硬件故障、人员更改或可能会丢失加密密钥的其他情况下如何恢复数据。</span><span class="sxs-lookup"><span data-stu-id="2fb93-115">When you are dealing with the encryption of data, especially in an enterprise environment, consider how that data can be recovered in the event of a hardware failure, changes in personnel, or other situations in which encryption keys can be lost.</span></span>

<span data-ttu-id="2fb93-116">MBAM 的加密驱动器恢复功能确保可以捕获和存储数据，并且在 BitLocker 转到恢复模式时，可以使用所需的工具访问受 BitLocker 保护的卷，或者将其移动或损坏。</span><span class="sxs-lookup"><span data-stu-id="2fb93-116">The encrypted drive recovery features of MBAM ensure that data can be captured and stored and that the required tools are available to access a BitLocker-protected volume when BitLocker goes into recovery mode, is moved, or becomes corrupted.</span></span>

[<span data-ttu-id="2fb93-117">如何在恢复模式下恢复驱动器</span><span class="sxs-lookup"><span data-stu-id="2fb93-117">How to Recover a Drive in Recovery Mode</span></span>](how-to-recover-a-drive-in-recovery-mode-mbam-2.md)

[<span data-ttu-id="2fb93-118">如何恢复已移动的驱动器</span><span class="sxs-lookup"><span data-stu-id="2fb93-118">How to Recover a Moved Drive</span></span>](how-to-recover-a-moved-drive-mbam-2.md)

[<span data-ttu-id="2fb93-119">如何恢复已损坏的驱动器</span><span class="sxs-lookup"><span data-stu-id="2fb93-119">How to Recover a Corrupted Drive</span></span>](how-to-recover-a-corrupted-drive-mbam-2.md)

## <span data-ttu-id="2fb93-120">使用 MBAM 确定丢失的计算机的 BitLocker 加密状态</span><span class="sxs-lookup"><span data-stu-id="2fb93-120">Determine BitLocker Encryption State of Lost Computers by Using MBAM</span></span>


<span data-ttu-id="2fb93-121">使用 MBAM，你可以确定丢失或被盗的计算机的上次已知 BitLocker 加密状态。</span><span class="sxs-lookup"><span data-stu-id="2fb93-121">Using MBAM, you can determine the last known BitLocker encryption status of computers that were lost or stolen.</span></span>

[<span data-ttu-id="2fb93-122">如何确定丢失计算机的 BitLocker 加密状态</span><span class="sxs-lookup"><span data-stu-id="2fb93-122">How to Determine BitLocker Encryption State of Lost Computers</span></span>](how-to-determine-bitlocker-encryption-state-of-lost-computers-mbam-2.md)

## <span data-ttu-id="2fb93-123">使用自助服务门户重新获取对计算机的访问权限</span><span class="sxs-lookup"><span data-stu-id="2fb93-123">Use the Self-Service Portal to Regain Access to a Computer</span></span>


<span data-ttu-id="2fb93-124">如果最终用户通过 BitLocker 从 Windows 中被锁定，则他们可以使用本部分中的说明获取 BitLocker 恢复密钥，以重新获得其计算机的访问权限。</span><span class="sxs-lookup"><span data-stu-id="2fb93-124">If end users get locked out of Windows by BitLocker, they can use the instructions in this section to get a BitLocker recovery key to regain access to their computer.</span></span>

[<span data-ttu-id="2fb93-125">如何使用自助服务门户重获计算机访问权限</span><span class="sxs-lookup"><span data-stu-id="2fb93-125">How to Use the Self-Service Portal to Regain Access to a Computer</span></span>](how-to-use-the-self-service-portal-to-regain-access-to-a-computer.md)

## <span data-ttu-id="2fb93-126">用于通过 MBAM 执行 BitLocker 管理的其他资源</span><span class="sxs-lookup"><span data-stu-id="2fb93-126">Other Resources for Performing BitLocker Management with MBAM</span></span>


[<span data-ttu-id="2fb93-127">MBAM 2.0 的操作</span><span class="sxs-lookup"><span data-stu-id="2fb93-127">Operations for MBAM 2.0</span></span>](operations-for-mbam-20-mbam-2.md)

 

 





