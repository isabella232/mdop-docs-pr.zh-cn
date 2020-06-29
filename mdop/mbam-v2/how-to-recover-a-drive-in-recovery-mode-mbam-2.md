---
title: 如何在恢复模式下恢复驱动器
description: 如何在恢复模式下恢复驱动器
author: dansimp
ms.assetid: 8b792bc8-b671-4345-9d37-0208db3e5b03
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7d5ce509599d0eb800a71360e3be9d0fa3b33f4f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803692"
---
# <span data-ttu-id="7083b-103">如何在恢复模式下恢复驱动器</span><span class="sxs-lookup"><span data-stu-id="7083b-103">How to Recover a Drive in Recovery Mode</span></span>


<span data-ttu-id="7083b-104">Microsoft BitLocker 管理和监视（MBAM）的加密驱动器恢复功能可确保在 BitLocker 进入恢复模式时访问受 BitLocker 保护的卷所需的数据和可用工具的捕获和存储。</span><span class="sxs-lookup"><span data-stu-id="7083b-104">The encrypted drive recovery features of Microsoft BitLocker Administration and Monitoring (MBAM) ensure the capture and storage of data and availability of tools required to access a BitLocker-protected volume when BitLocker goes into recovery mode.</span></span> <span data-ttu-id="7083b-105">当丢失或忘记 PIN 或密码，或者当受信任模块平台（TPM）芯片检测到计算机的 BIOS 或启动文件更改时，受 BitLocker 保护的卷将进入恢复模式。</span><span class="sxs-lookup"><span data-stu-id="7083b-105">A BitLocker-protected volume goes into recovery mode when a PIN or password is lost or forgotten, or when the Trusted Module Platform (TPM) chip detects changes to the BIOS or startup files of a computer.</span></span>

<span data-ttu-id="7083b-106">使用此过程访问集中的密钥恢复数据系统，如果提供了恢复密码 ID 和关联的用户标识符，该系统可以提供恢复密码。</span><span class="sxs-lookup"><span data-stu-id="7083b-106">Use this procedure to access the centralized key recovery data system, which can provide a recovery password if a recovery password ID and associated user identifier are supplied.</span></span>

**<span data-ttu-id="7083b-107">重要提示</span><span class="sxs-lookup"><span data-stu-id="7083b-107">Important</span></span>**  
<span data-ttu-id="7083b-108">Microsoft BitLocker 管理和监视使用在使用时过期的单一使用恢复密钥。</span><span class="sxs-lookup"><span data-stu-id="7083b-108">Microsoft BitLocker Administration and Monitoring uses single-use recovery keys that expire upon use.</span></span> <span data-ttu-id="7083b-109">恢复密码的单个用途将自动应用于操作系统驱动器和固定驱动器。</span><span class="sxs-lookup"><span data-stu-id="7083b-109">The single use of a recovery password is automatically applied to operating system drives and fixed drives.</span></span> <span data-ttu-id="7083b-110">在可移动驱动器上，当删除驱动器，然后在已激活组策略设置以管理可移动驱动器的计算机上重新插入和解除锁定时，将应用该驱动器。</span><span class="sxs-lookup"><span data-stu-id="7083b-110">On removable drives, it is applied when the drive is removed and then re-inserted and unlocked on a computer that has Group Policy settings activated to manage removable drives.</span></span>



**<span data-ttu-id="7083b-111">在恢复模式下恢复驱动器</span><span class="sxs-lookup"><span data-stu-id="7083b-111">To recover a drive in recovery mode</span></span>**

1.  <span data-ttu-id="7083b-112">打开 web 浏览器并导航到 "管理和监视" 网站。</span><span class="sxs-lookup"><span data-stu-id="7083b-112">Open a web browser and navigate to the Administration and Monitoring website.</span></span>

2.  <span data-ttu-id="7083b-113">在导航窗格中，单击 "**驱动器恢复**"。</span><span class="sxs-lookup"><span data-stu-id="7083b-113">In the navigation pane, click **Drive Recovery**.</span></span> <span data-ttu-id="7083b-114">"恢复对加密驱动器的访问" 网页随即打开。</span><span class="sxs-lookup"><span data-stu-id="7083b-114">The “Recover access to an encrypted drive” webpage opens.</span></span>

3.  <span data-ttu-id="7083b-115">输入用户的 Windows 登录域和用户名以查看恢复信息，以及恢复密钥 ID 的前八位数字，以接收可能匹配的恢复密钥的列表或整个恢复密钥 ID 以接收准确的恢复密钥。</span><span class="sxs-lookup"><span data-stu-id="7083b-115">Enter the Windows Logon domain and user name of the user to view recovery information and the first eight digits of the recovery key ID to receive a list of possible matching recovery keys or the entire recovery key ID to receive the exact recovery key.</span></span>

4.  <span data-ttu-id="7083b-116">从 "**驱动器解锁的原因**" 列表中选择一个预定义选项，然后单击 "**提交**"。</span><span class="sxs-lookup"><span data-stu-id="7083b-116">Select one of the predefined options from the **Reason for Drive Unlock** list, and then click **Submit**.</span></span>

    **<span data-ttu-id="7083b-117">注意</span><span class="sxs-lookup"><span data-stu-id="7083b-117">Note</span></span>**  
    <span data-ttu-id="7083b-118">如果你是 MBAM 高级帮助台用户，则不需要用户域和用户 ID 条目。</span><span class="sxs-lookup"><span data-stu-id="7083b-118">If you are an MBAM Advanced Helpdesk user, the user domain and user ID entries are not required.</span></span>



~~~
MBAM returns the following:

-   An error message if no matching recovery password is found

-   Multiple possible matches if the user has multiple matching recovery passwords

-   The recovery password and recovery package for the submitted user

    **Note**  
    If you are recovering a damaged drive, the recovery package option provides BitLocker with critical information that it needs to recover the drive.



After the recovery password and recovery package are retrieved, the recovery password is displayed.
~~~

5. <span data-ttu-id="7083b-119">若要复制密码，请单击 "**复制密钥**"，然后将恢复密码粘贴到电子邮件中。</span><span class="sxs-lookup"><span data-stu-id="7083b-119">To copy the password, click **Copy Key**, and then paste the recovery password into an email message.</span></span> <span data-ttu-id="7083b-120">或者，单击 "**保存**" 以将恢复密码保存到文件。</span><span class="sxs-lookup"><span data-stu-id="7083b-120">Alternatively, click **Save** to save the recovery password to a file.</span></span>

   <span data-ttu-id="7083b-121">当用户在系统中键入恢复密码或使用恢复包时，驱动器将解锁。</span><span class="sxs-lookup"><span data-stu-id="7083b-121">When the user types the recovery password into the system or uses the recovery package, the drive is unlocked.</span></span>

## <span data-ttu-id="7083b-122">相关主题</span><span class="sxs-lookup"><span data-stu-id="7083b-122">Related topics</span></span>


[<span data-ttu-id="7083b-123">使用 MBAM 执行 BitLocker 管理</span><span class="sxs-lookup"><span data-stu-id="7083b-123">Performing BitLocker Management with MBAM</span></span>](performing-bitlocker-management-with-mbam-mbam-2.md)









