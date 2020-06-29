---
title: 如何在恢复模式下恢复驱动器
description: 如何在恢复模式下恢复驱动器
author: dansimp
ms.assetid: 09d27e4b-57fa-47c7-a004-8b876a49f27e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c1151ffe7453eb8d07d2aa6dcb4c41f6b3efe6de
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798174"
---
# <span data-ttu-id="5a28c-103">如何在恢复模式下恢复驱动器</span><span class="sxs-lookup"><span data-stu-id="5a28c-103">How to Recover a Drive in Recovery Mode</span></span>


<span data-ttu-id="5a28c-104">Microsoft BitLocker 管理和监视（MBAM）包括加密的驱动器恢复功能。</span><span class="sxs-lookup"><span data-stu-id="5a28c-104">Microsoft BitLocker Administration and Monitoring (MBAM) includes Encrypted Drive Recovery features.</span></span> <span data-ttu-id="5a28c-105">当 BitLocker 将该卷置于恢复模式时，这些功能可确保捕获和存储访问受 BitLocker 保护的卷所需的工具的数据和可用性。</span><span class="sxs-lookup"><span data-stu-id="5a28c-105">These features ensure the capture and storage of data and availability of tools that are required to access a BitLocker-protected volume when BitLocker puts that volume into recovery mode.</span></span> <span data-ttu-id="5a28c-106">当丢失或忘记 PIN 或密码时，或者当受信任的模块平台（TPM）芯片检测到计算机的 BIOS 或启动文件的更改时，受 BitLocker 保护的卷将进入恢复模式。</span><span class="sxs-lookup"><span data-stu-id="5a28c-106">A BitLocker-protected volume goes into recovery mode when a PIN or password is lost or forgotten, or when the Trusted Module Platform (TPM) chip detects a change to the computer's BIOS or startup files.</span></span>

<span data-ttu-id="5a28c-107">使用此过程访问可在提供恢复密码 ID 和关联的用户标识符时提供恢复密码的集中密钥恢复数据系统。</span><span class="sxs-lookup"><span data-stu-id="5a28c-107">Use this procedure to access the centralized Key Recovery data system that can provide a recovery password when a recovery password ID and associated user identifier are supplied.</span></span>

<span data-ttu-id="5a28c-108">**重要提示** MBAM 生成单一使用恢复密钥。</span><span class="sxs-lookup"><span data-stu-id="5a28c-108">**Important** MBAM generates single-use recovery keys.</span></span> <span data-ttu-id="5a28c-109">在此限制下，只能使用一个恢复密钥一次，然后它将不再有效。</span><span class="sxs-lookup"><span data-stu-id="5a28c-109">Under this limitation, a recovery key can be used only once and then it is no longer valid.</span></span> <span data-ttu-id="5a28c-110">恢复密码的单个用途将自动应用于操作系统驱动器和固定驱动器。</span><span class="sxs-lookup"><span data-stu-id="5a28c-110">The single use of a recovery password is automatically applied to operating system drives and fixed drives.</span></span> <span data-ttu-id="5a28c-111">在可移动驱动器上，当删除驱动器，然后在已激活组策略设置以管理可移动驱动器的计算机上重新插入和解除锁定时，将应用单一使用。</span><span class="sxs-lookup"><span data-stu-id="5a28c-111">On removable drives, the single use is applied when the drive is removed and then re-inserted and unlocked on a computer that has the group policy settings activated to manage removable drives.</span></span>

 

**<span data-ttu-id="5a28c-112">在恢复模式下恢复驱动器</span><span class="sxs-lookup"><span data-stu-id="5a28c-112">To recover a drive in Recovery Mode</span></span>**

1.  <span data-ttu-id="5a28c-113">打开 MBAM 网站。</span><span class="sxs-lookup"><span data-stu-id="5a28c-113">Open the MBAM website.</span></span>

2.  <span data-ttu-id="5a28c-114">在导航窗格中，单击 "**驱动器恢复**"。</span><span class="sxs-lookup"><span data-stu-id="5a28c-114">In the navigation pane, click **Drive Recovery**.</span></span> <span data-ttu-id="5a28c-115">将打开 "**恢复对加密驱动器的访问**" 网页。</span><span class="sxs-lookup"><span data-stu-id="5a28c-115">The **Recover access to an encrypted drive** webpage opens.</span></span>

3.  <span data-ttu-id="5a28c-116">输入用户的 Windows 登录域和用户名以及恢复密钥 ID 的前八位数字，以接收可能匹配的恢复密钥的列表。</span><span class="sxs-lookup"><span data-stu-id="5a28c-116">Enter the user's Windows Logon domain and user name and the first eight digits of the recovery key ID, to receive a list of possible matching recovery keys.</span></span> <span data-ttu-id="5a28c-117">或者，输入整个恢复密钥 ID 以接收准确的恢复密钥。</span><span class="sxs-lookup"><span data-stu-id="5a28c-117">Alternatively, enter the entire recovery key ID to receive the exact recovery key.</span></span> <span data-ttu-id="5a28c-118">在 "**驱动器解锁的原因**" 下拉列表中选择预定义选项之一，然后单击 "**提交**"。</span><span class="sxs-lookup"><span data-stu-id="5a28c-118">Select one of the predefined options in the **Reason for Drive Unlock** drop-down list, and then click **Submit**.</span></span>

    <span data-ttu-id="5a28c-119">**注意** 如果你是 MBAM 高级帮助台用户，则不需要用户域和用户 ID 条目。</span><span class="sxs-lookup"><span data-stu-id="5a28c-119">**Note** If you are an MBAM Advanced Helpdesk User, the user domain and user ID entries are not required.</span></span>

     

4.  <span data-ttu-id="5a28c-120">MBAM 返回以下内容：</span><span class="sxs-lookup"><span data-stu-id="5a28c-120">MBAM returns the following:</span></span>

    1.  <span data-ttu-id="5a28c-121">找不到匹配的恢复密码时出现的错误消息</span><span class="sxs-lookup"><span data-stu-id="5a28c-121">An error message if no matching recovery password is found</span></span>

    2.  <span data-ttu-id="5a28c-122">如果用户具有多个匹配的恢复密码，则可以进行多个可能的匹配</span><span class="sxs-lookup"><span data-stu-id="5a28c-122">Multiple possible matches if the user has multiple matching recovery passwords</span></span>

    3.  <span data-ttu-id="5a28c-123">已提交用户的恢复密码和恢复程序包</span><span class="sxs-lookup"><span data-stu-id="5a28c-123">The recovery password and recovery package for the submitted user</span></span>

        <span data-ttu-id="5a28c-124">**注意** 如果要恢复损坏的驱动器，恢复包选项会提供 BitLocker，其中包含尝试恢复所必需的关键信息。</span><span class="sxs-lookup"><span data-stu-id="5a28c-124">**Note** If you are recovering a damaged drive, the recovery package option provides BitLocker with the critical information necessary to attempt the recovery.</span></span>

         

5.  <span data-ttu-id="5a28c-125">检索恢复密码和恢复程序包后，将显示恢复密码。</span><span class="sxs-lookup"><span data-stu-id="5a28c-125">After the recovery password and recovery package are retrieved, the recovery password is displayed.</span></span> <span data-ttu-id="5a28c-126">若要复制密码，请单击 "**复制密钥**"，然后将恢复密码粘贴到电子邮件或其他文本文件中以进行临时存储。</span><span class="sxs-lookup"><span data-stu-id="5a28c-126">To copy the password, click **Copy Key**, and then paste the recovery password into an email or other text file for temporary storage.</span></span> <span data-ttu-id="5a28c-127">或者，要将恢复密码保存到文件中，请单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="5a28c-127">Or, to save the recovery password to a file, click **Save**.</span></span>

6.  <span data-ttu-id="5a28c-128">当用户在系统中键入恢复密码或使用恢复包时，驱动器将解锁。</span><span class="sxs-lookup"><span data-stu-id="5a28c-128">When the user types the recovery password into the system or uses the recovery package, the drive is unlocked.</span></span>

## <span data-ttu-id="5a28c-129">相关主题</span><span class="sxs-lookup"><span data-stu-id="5a28c-129">Related topics</span></span>


[<span data-ttu-id="5a28c-130">使用 MBAM 执行 BitLocker 管理</span><span class="sxs-lookup"><span data-stu-id="5a28c-130">Performing BitLocker Management with MBAM</span></span>](performing-bitlocker-management-with-mbam.md)

 

 





