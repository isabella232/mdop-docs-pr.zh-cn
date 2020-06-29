---
title: 如何使用自助服务门户重获计算机访问权限
description: 如何使用自助服务门户重获计算机访问权限
author: dansimp
ms.assetid: bcf095de-0237-4bb0-b450-da8fb6d6f3d0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4abcffcf35e09bd5e24f4715a38dca74518ba29e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803896"
---
# <span data-ttu-id="a18dc-103">如何使用自助服务门户重获计算机访问权限</span><span class="sxs-lookup"><span data-stu-id="a18dc-103">How to Use the Self-Service Portal to Regain Access to a Computer</span></span>


<span data-ttu-id="a18dc-104">如果最终用户因忘记了密码或 PIN 而被 BitLocker 锁定了 Windows，或者他们更改了操作系统文件或者更改了 BIOS 或受信任的平台模块（TPM），他们可以使用自助服务门户重新获取对 Windows 的访问权限，而无需向其支持人员寻求帮助。</span><span class="sxs-lookup"><span data-stu-id="a18dc-104">If end users get locked out of Windows by BitLocker because they forgot their password or PIN, or because they changed operating system files or changed the BIOS or the Trusted Platform Module (TPM), they can use the Self-Service Portal to regain access to Windows without having to ask their Help Desk for assistance.</span></span>

<span data-ttu-id="a18dc-105">**注意** 如果 IT 管理员配置了 IIS 会话状态超时，则会在超时前60秒显示一条消息。</span><span class="sxs-lookup"><span data-stu-id="a18dc-105">**Note** If the IT administrator configured an IIS Session State time-out, a message is displayed 60 seconds prior to the time-out.</span></span>

 

<span data-ttu-id="a18dc-106">**注意** 这些说明针对最终用户的观点进行编写。</span><span class="sxs-lookup"><span data-stu-id="a18dc-106">**Note** These instructions are written for and from the perspective of end users.</span></span>

 

**<span data-ttu-id="a18dc-107">使用自助服务门户重新获取对计算机的访问权限</span><span class="sxs-lookup"><span data-stu-id="a18dc-107">To use the Self-Service Portal to regain access to a computer</span></span>**

1.  <span data-ttu-id="a18dc-108">在 "**恢复**密钥 ID" 字段中，输入计算机的 BitLocker 恢复屏幕上显示的至少8个32位的 bitlocker 密钥 ID。</span><span class="sxs-lookup"><span data-stu-id="a18dc-108">In the **Recovery KeyId** field, enter a minimum of eight of the 32-digit BitLocker Key ID that is displayed on the BitLocker recovery screen of your computer.</span></span>

    <span data-ttu-id="a18dc-109">**注意** 如果前八个数字与多个键匹配，则会显示一条消息，要求你输入恢复密钥 ID 的所有32位。</span><span class="sxs-lookup"><span data-stu-id="a18dc-109">**Note** If the first eight digits match multiple keys, a message displays that requires you to enter all 32 digits of the recovery key ID.</span></span>

     

2.  <span data-ttu-id="a18dc-110">在 "**原因**" 字段中，为你的恢复密钥请求选择一个原因。</span><span class="sxs-lookup"><span data-stu-id="a18dc-110">In the **Reason** field, select a reason for your request for the recovery key.</span></span>

3.  <span data-ttu-id="a18dc-111">单击 "**获取键**"。</span><span class="sxs-lookup"><span data-stu-id="a18dc-111">Click **Get Key**.</span></span> <span data-ttu-id="a18dc-112">你的 BitLocker 恢复密钥显示在 "BitLocker 恢复密钥" 字段中。</span><span class="sxs-lookup"><span data-stu-id="a18dc-112">Your BitLocker recovery key is displayed in the “Your BitLocker Recovery Key” field.</span></span>

4.  <span data-ttu-id="a18dc-113">在计算机上的 BitLocker 恢复屏幕中输入48位代码，以重新获取对计算机的访问权限。</span><span class="sxs-lookup"><span data-stu-id="a18dc-113">Enter the 48-digit code into the BitLocker recovery screen on your computer to regain access to the computer.</span></span>

## <span data-ttu-id="a18dc-114">相关主题</span><span class="sxs-lookup"><span data-stu-id="a18dc-114">Related topics</span></span>


[<span data-ttu-id="a18dc-115">使用 MBAM 执行 BitLocker 管理</span><span class="sxs-lookup"><span data-stu-id="a18dc-115">Performing BitLocker Management with MBAM</span></span>](performing-bitlocker-management-with-mbam-mbam-2.md)

 

 





