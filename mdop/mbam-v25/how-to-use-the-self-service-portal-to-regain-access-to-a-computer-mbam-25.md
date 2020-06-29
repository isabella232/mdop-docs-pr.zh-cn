---
title: 如何使用自助服务门户重获计算机访问权限
description: 如何使用自助服务门户重获计算机访问权限
author: dansimp
ms.assetid: 3c24b13a-d1b1-4763-8ac0-0b2db46267e3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: cde9c71a957a5270d69aa8388455895f1cb2432b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804021"
---
# <span data-ttu-id="4f10d-103">如何使用自助服务门户重获计算机访问权限</span><span class="sxs-lookup"><span data-stu-id="4f10d-103">How to Use the Self-Service Portal to Regain Access to a Computer</span></span>


<span data-ttu-id="4f10d-104">自助服务门户是 IT 管理员将其配置为 Microsoft BitLocker 管理和监视（MBAM）2.5 部署的一部分的网站。</span><span class="sxs-lookup"><span data-stu-id="4f10d-104">The Self-Service Portal is a website that IT administrators configure as part of their Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 deployment.</span></span> <span data-ttu-id="4f10d-105">如果用户被封锁到 Windows，则该网站使最终用户能够独立地重新获取其计算机的访问权限。</span><span class="sxs-lookup"><span data-stu-id="4f10d-105">The website enables end users to independently regain access to their computers if they get locked out of Windows.</span></span> <span data-ttu-id="4f10d-106">自助服务门户不需要技术支持人员的帮助。</span><span class="sxs-lookup"><span data-stu-id="4f10d-106">The Self-Service Portal requires no assistance from Help Desk staff.</span></span>

<span data-ttu-id="4f10d-107">以下说明是从最终用户的角度编写的，但该信息可能有助于 IT 管理员理解。</span><span class="sxs-lookup"><span data-stu-id="4f10d-107">The following instructions are written from the perspective of end users, but the information may be useful for IT administrators to understand.</span></span>

<span data-ttu-id="4f10d-108">**重要提示** 最终用户必须至少有一次登录到计算机（非远程）才能使用自助服务门户恢复其密钥。</span><span class="sxs-lookup"><span data-stu-id="4f10d-108">**Important** An end user must have physically logged on to the computer (not remotely) at least one time successfully to be able to recover their key using the Self-Service Portal.</span></span> <span data-ttu-id="4f10d-109">否则，他们必须使用支持人员门户进行密钥恢复。</span><span class="sxs-lookup"><span data-stu-id="4f10d-109">Otherwise, they must use the Helpdesk Portal for key recovery.</span></span>

 

<span data-ttu-id="4f10d-110">最终用户可能会在以下情况中遇到锁定：</span><span class="sxs-lookup"><span data-stu-id="4f10d-110">End users may experience lockouts if they:</span></span>

-   <span data-ttu-id="4f10d-111">忘记了密码或 PIN 码</span><span class="sxs-lookup"><span data-stu-id="4f10d-111">Forget their password or PIN</span></span>

-   <span data-ttu-id="4f10d-112">更改操作系统文件、BIOS 或受信任的平台模块（TPM）</span><span class="sxs-lookup"><span data-stu-id="4f10d-112">Change operating system files, the BIOS, or the Trusted Platform Module (TPM)</span></span>

<span data-ttu-id="4f10d-113">**注意** 如果 IT 管理员配置了一个 IIS 会话状态超时，则在出现超时前的自助服务门户60秒中会显示一条消息。</span><span class="sxs-lookup"><span data-stu-id="4f10d-113">**Note** If the IT administrator configured an IIS Session State time-out, a message is displayed in the Self-Service Portal 60 seconds prior to the time-out.</span></span>

 

**<span data-ttu-id="4f10d-114">使用自助服务门户重新获取对计算机的访问权限</span><span class="sxs-lookup"><span data-stu-id="4f10d-114">To use the Self-Service Portal to regain access to a computer</span></span>**

1.  <span data-ttu-id="4f10d-115">在 "**恢复**密钥 ID" 字段中，输入计算机的 BitLocker 恢复屏幕上显示的至少8个32位的 bitlocker 密钥 ID。</span><span class="sxs-lookup"><span data-stu-id="4f10d-115">In the **Recovery KeyId** field, enter a minimum of eight of the 32-digit BitLocker Key ID that is displayed on the BitLocker recovery screen of your computer.</span></span> <span data-ttu-id="4f10d-116">如果前八个数字与多个键匹配，则会显示一条消息，要求你输入恢复密钥 ID 的所有32位。</span><span class="sxs-lookup"><span data-stu-id="4f10d-116">If the first eight digits match multiple keys, a message displays that requires you to enter all 32 digits of the recovery key ID.</span></span>

2.  <span data-ttu-id="4f10d-117">在 "**原因**" 字段中，为你的恢复密钥请求选择一个原因。</span><span class="sxs-lookup"><span data-stu-id="4f10d-117">In the **Reason** field, select a reason for your request for the recovery key.</span></span>

3.  <span data-ttu-id="4f10d-118">单击 "**获取键**"。</span><span class="sxs-lookup"><span data-stu-id="4f10d-118">Click **Get Key**.</span></span> <span data-ttu-id="4f10d-119">您的 BitLocker 恢复密钥显示在 " **Bitlocker 恢复密钥**" 字段中。</span><span class="sxs-lookup"><span data-stu-id="4f10d-119">Your BitLocker recovery key is displayed in the **Your BitLocker Recovery Key** field.</span></span>

4.  <span data-ttu-id="4f10d-120">在计算机上的 BitLocker 恢复屏幕中输入48位代码，以重新获取对计算机的访问权限。</span><span class="sxs-lookup"><span data-stu-id="4f10d-120">Enter the 48-digit code into the BitLocker recovery screen on your computer to regain access to the computer.</span></span>



## <span data-ttu-id="4f10d-121">相关主题</span><span class="sxs-lookup"><span data-stu-id="4f10d-121">Related topics</span></span>


[<span data-ttu-id="4f10d-122">使用 MBAM 2.5 执行 BitLocker 管理</span><span class="sxs-lookup"><span data-stu-id="4f10d-122">Performing BitLocker Management with MBAM 2.5</span></span>](performing-bitlocker-management-with-mbam-25.md)

 
## <span data-ttu-id="4f10d-123">已获得 MBAM 的建议？</span><span class="sxs-lookup"><span data-stu-id="4f10d-123">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="4f10d-124">在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="4f10d-124">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="4f10d-125">对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="4f10d-125">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>
 





