---
title: 关于计算机 TPM 芯片
description: 关于计算机 TPM 芯片
author: dansimp
ms.assetid: 6f1cf18c-277a-4932-886d-14202ca8d175
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f6df54dc8085c398bacc508fdbbb79a30b0e4204
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803387"
---
# <span data-ttu-id="90dae-103">关于计算机 TPM 芯片</span><span class="sxs-lookup"><span data-stu-id="90dae-103">About the Computer TPM Chip</span></span>


<span data-ttu-id="90dae-104">BitLocker 在与受信任的平台模块（TPM）芯片配合使用时提供附加保护。</span><span class="sxs-lookup"><span data-stu-id="90dae-104">BitLocker provides additional protection when it is used with a Trusted Platform Module (TPM) chip.</span></span> <span data-ttu-id="90dae-105">TPM 芯片是计算机制造商在许多较新计算机上安装的硬件组件。</span><span class="sxs-lookup"><span data-stu-id="90dae-105">The TPM chip is a hardware component that is installed in many newer computers by the computer manufacturers.</span></span> <span data-ttu-id="90dae-106">Microsoft BitLocker 管理和监视（MBAM）除了 TPM 芯片之外，还使用 BitLocker 来帮助对你的数据提供额外保护，并确保你的计算机未被篡改。</span><span class="sxs-lookup"><span data-stu-id="90dae-106">Microsoft BitLocker Administration and Monitoring (MBAM) uses BitLocker, in addition to the TPM chip, to help provide additional protection of your data and to make sure that your computer has not been tampered with.</span></span>

## <span data-ttu-id="90dae-107">如何设置 TPM</span><span class="sxs-lookup"><span data-stu-id="90dae-107">How to Set Up Your TPM</span></span>


<span data-ttu-id="90dae-108">当你在计算机上启动 BitLocker 驱动器加密向导时，如果你的组织已将 BitLocker 配置为使用 TPM 芯片，BitLocker 将检查 TPM 芯片。</span><span class="sxs-lookup"><span data-stu-id="90dae-108">When you start the BitLocker Drive Encryption wizard on your computer, BitLocker checks for a TPM chip if your organization has configured BitLocker to use a TPM chip.</span></span> <span data-ttu-id="90dae-109">如果 BitLocker 找到兼容的 TPM 芯片，系统可能会提示你重启计算机，以使 TPM 芯片可供使用。</span><span class="sxs-lookup"><span data-stu-id="90dae-109">If BitLocker finds a compatible TPM chip, you may be prompted to restart your computer to enable the TPM chip for use.</span></span> <span data-ttu-id="90dae-110">一旦计算机重新启动，请按照说明在 BIOS 中配置 TPM 芯片（BIOS 是计算机软件的 Windows 安装层）。</span><span class="sxs-lookup"><span data-stu-id="90dae-110">As soon as your computer has restarted, follow the instructions to configure the TPM chip in the BIOS (the BIOS is a pre-Windows layer of your computer software).</span></span>

<span data-ttu-id="90dae-111">配置 BitLocker 后，您可以通过打开 Windows "控制面板" 中的 "BitLocker 加密选项" 工具，然后选择 " **TPM 管理**" 来访问有关 TPM 芯片的其他信息。</span><span class="sxs-lookup"><span data-stu-id="90dae-111">After BitLocker is configured, you can access additional information about the TPM chip by opening the BitLocker Encryption Options tool in the Windows Control Panel, and then selecting **TPM Administration**.</span></span>

<span data-ttu-id="90dae-112">**注意** 您必须拥有计算机的管理凭据才能访问此工具。</span><span class="sxs-lookup"><span data-stu-id="90dae-112">**Note** You must have administrative credentials on your computer to access this tool.</span></span>

 

<span data-ttu-id="90dae-113">在 TPM 故障、BIOS 中的更改或某些 Windows 更新中，BitLocker 将锁定你的计算机，并要求你与你的技术支持人员联系以解除锁定。</span><span class="sxs-lookup"><span data-stu-id="90dae-113">In a TPM failure, a change in the BIOS, or certain Windows Updates, BitLocker will lock your computer and require you to contact your Help Desk to unlock it.</span></span> <span data-ttu-id="90dae-114">您必须提供计算机的名称以及计算机的域。</span><span class="sxs-lookup"><span data-stu-id="90dae-114">You have to provide the name of your computer as well as your computer’s domain.</span></span> <span data-ttu-id="90dae-115">技术支持人员可以为你提供密码文件，该文件可用于解锁你的计算机。</span><span class="sxs-lookup"><span data-stu-id="90dae-115">Help Desk can give you a password file that can be used to unlock your computer.</span></span>

## <span data-ttu-id="90dae-116">TPM 问题疑难解答</span><span class="sxs-lookup"><span data-stu-id="90dae-116">Troubleshooting TPM Issues</span></span>


<span data-ttu-id="90dae-117">如果 TPM 故障、在 BIOS 中发生更改或发生某些 Windows 更新，BitLocker 将锁定您的计算机，并要求您与您的技术支持人员联系以解除锁定。</span><span class="sxs-lookup"><span data-stu-id="90dae-117">If a TPM failure, change in the BIOS, or certain Windows Updates occur, BitLocker will lock your computer and require you to contact your Help Desk to unlock it.</span></span> <span data-ttu-id="90dae-118">您必须提供计算机的名称以及计算机的域。</span><span class="sxs-lookup"><span data-stu-id="90dae-118">You have to provide the name of your computer as well as your computer’s domain.</span></span> <span data-ttu-id="90dae-119">技术支持人员可以为您提供一个密码文件，您可以使用该文件解锁您的计算机。</span><span class="sxs-lookup"><span data-stu-id="90dae-119">The Help Desk can give you a password file that you can use to unlock your computer.</span></span>

## <span data-ttu-id="90dae-120">相关主题</span><span class="sxs-lookup"><span data-stu-id="90dae-120">Related topics</span></span>


[<span data-ttu-id="90dae-121">帮助最终用户管理 BitLocker</span><span class="sxs-lookup"><span data-stu-id="90dae-121">Helping End Users Manage BitLocker</span></span>](helping-end-users-manage-bitlocker.md)

[<span data-ttu-id="90dae-122">使用 PIN 或密码</span><span class="sxs-lookup"><span data-stu-id="90dae-122">Using Your PIN or Password</span></span>](using-your-pin-or-password.md)

 

 





