---
title: 如何使用控制面板管理 MBAM 客户端 BitLocker 加密选项
description: 如何使用控制面板管理 MBAM 客户端 BitLocker 加密选项
author: dansimp
ms.assetid: e2ff153e-5770-4a12-b79d-cda998b8a8ab
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a42901ac9d8a1a3527712f4cf342b5c0ca9ffdfd
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803702"
---
# <span data-ttu-id="0c39a-103">如何使用控制面板管理 MBAM 客户端 BitLocker 加密选项</span><span class="sxs-lookup"><span data-stu-id="0c39a-103">How to Manage MBAM Client BitLocker Encryption Options by Using the Control Panel</span></span>


<span data-ttu-id="0c39a-104">安装 Microsoft BitLocker 管理和监视客户端时，"系统和安全" 下的 "Microsoft BitLocker 管理和监视" （MBAM）控制面板应用程序（称为 BitLocker 加密选项）将在 "**系统和安全**" 下可用。</span><span class="sxs-lookup"><span data-stu-id="0c39a-104">A Microsoft BitLocker Administration and Monitoring (MBAM) control panel application, called BitLocker Encryption Options, will be available under **System and Security** when the Microsoft BitLocker Administration and Monitoring Client is installed.</span></span> <span data-ttu-id="0c39a-105">此 "自定义 MBAM" 控制面板是一个附加控制面板。</span><span class="sxs-lookup"><span data-stu-id="0c39a-105">This custom MBAM control panel is an additional control panel.</span></span> <span data-ttu-id="0c39a-106">它不会替换默认的 Windows BitLocker "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="0c39a-106">It does not replace the default Windows BitLocker control panel.</span></span> <span data-ttu-id="0c39a-107">MBAM 控制面板可用于解锁加密的固定和可移动驱动器，还可管理 PIN 或密码。</span><span class="sxs-lookup"><span data-stu-id="0c39a-107">The MBAM control panel can be used to unlock encrypted fixed and removable drives, and also manage your PIN or password.</span></span> <span data-ttu-id="0c39a-108">有关启用 MBAM 控制面板的详细信息，请参阅[如何在 Windows "控制面板" 中隐藏默认的 BitLocker 加密](how-to-hide-default-bitlocker-encryption-in-the-windows-control-panel-mbam-2.md)。</span><span class="sxs-lookup"><span data-stu-id="0c39a-108">For more information about enabling the MBAM control panel, see [How to Hide Default BitLocker Encryption in the Windows Control Panel](how-to-hide-default-bitlocker-encryption-in-the-windows-control-panel-mbam-2.md).</span></span>

**<span data-ttu-id="0c39a-109">使用 "MBAM 客户端" 控制面板</span><span class="sxs-lookup"><span data-stu-id="0c39a-109">To use the MBAM Client Control Panel</span></span>**

1.  <span data-ttu-id="0c39a-110">若要打开 BitLocker 加密选项，请单击 "**开始**"，然后选择 **"控制面板"**。</span><span class="sxs-lookup"><span data-stu-id="0c39a-110">To open BitLocker Encryption Options, click **Start** and then select **Control Panel**.</span></span> <span data-ttu-id="0c39a-111">当 **"控制面板"** 打开时，选择 "**系统和安全**"。</span><span class="sxs-lookup"><span data-stu-id="0c39a-111">When **Control Panel** opens, select **System and Security**.</span></span>

2.  <span data-ttu-id="0c39a-112">双击 " **BitLocker 加密选项**" 以打开 "自定义 MBAM" 控制面板。</span><span class="sxs-lookup"><span data-stu-id="0c39a-112">Double-click **BitLocker Encryption Options** to open the customized MBAM control panel.</span></span> <span data-ttu-id="0c39a-113">除了用于管理 PIN 或密码的选项之外，您还可以查看计算机上所有硬盘驱动器及其加密状态的列表。</span><span class="sxs-lookup"><span data-stu-id="0c39a-113">You will see a list of all the hard disk drives on the computer and their encryption status, in addition to an option to manage your PIN or passwords.</span></span>

    <span data-ttu-id="0c39a-114">如果已部署用户和计算机免除策略，则可以使用计算机上的硬盘驱动器列表来验证加密状态、解锁驱动器或请求 BitLocker 保护的豁免。</span><span class="sxs-lookup"><span data-stu-id="0c39a-114">The list of hard disk drives on the computer can be used to verify encryption status, unlock a drive, or request an exemption for BitLocker protection if the User and Computer Exemption policies have been deployed.</span></span>

    <span data-ttu-id="0c39a-115">"BitLocker 加密选项" 控制面板还允许非管理员用户管理其 PIN 或密码。</span><span class="sxs-lookup"><span data-stu-id="0c39a-115">The BitLocker Encryption Options control panel also allows for non-administrator users to manage their PIN or passwords.</span></span> <span data-ttu-id="0c39a-116">通过选择 "**管理 PIN**"，系统会提示用户输入当前 pin 和新 pin （除了确认新 pin）。</span><span class="sxs-lookup"><span data-stu-id="0c39a-116">By selecting **Manage PIN**, users are prompted to enter both a current PIN and a new PIN (in addition to confirming the new PIN).</span></span> <span data-ttu-id="0c39a-117">选择 "**更新 pin** " 会将 pin 重置为用户选择的新密码。</span><span class="sxs-lookup"><span data-stu-id="0c39a-117">Selecting **Update PIN** will reset the PIN to the new one that the users selected.</span></span>

    <span data-ttu-id="0c39a-118">要管理您的密码，请选择 "**解锁驱动器**"，然后输入您的当前密码。</span><span class="sxs-lookup"><span data-stu-id="0c39a-118">To manage your password, select **Unlock drive** and enter your current password.</span></span> <span data-ttu-id="0c39a-119">解锁驱动器后，选择 "**重置密码**" 以更改当前密码。</span><span class="sxs-lookup"><span data-stu-id="0c39a-119">As soon as the drive is unlocked, select **Reset Password** to change your current password.</span></span>

## <span data-ttu-id="0c39a-120">相关主题</span><span class="sxs-lookup"><span data-stu-id="0c39a-120">Related topics</span></span>


[<span data-ttu-id="0c39a-121">管理 MBAM 2.0 功能</span><span class="sxs-lookup"><span data-stu-id="0c39a-121">Administering MBAM 2.0 Features</span></span>](administering-mbam-20-features-mbam-2.md)

 

 





