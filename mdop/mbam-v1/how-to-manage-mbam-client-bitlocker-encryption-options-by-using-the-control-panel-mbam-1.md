---
title: 如何使用控制面板管理 MBAM 客户端 BitLocker 加密选项
description: 如何使用控制面板管理 MBAM 客户端 BitLocker 加密选项
author: dansimp
ms.assetid: c08077e1-5529-468f-9370-c3b33fc258f3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 271147d0e5581f6ce49fe0b46aa83dae6ae4556b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798175"
---
# <span data-ttu-id="a32b6-103">如何使用控制面板管理 MBAM 客户端 BitLocker 加密选项</span><span class="sxs-lookup"><span data-stu-id="a32b6-103">How to Manage MBAM Client BitLocker Encryption Options by Using the Control Panel</span></span>


<span data-ttu-id="a32b6-104">安装 MBAM 客户端时，"系统和安全" 下的 "Microsoft BitLocker 管理和监视" （MBAM）控制面板应用程序（称为 BitLocker 加密选项）将在 "**系统和安全**" 下可用。</span><span class="sxs-lookup"><span data-stu-id="a32b6-104">A Microsoft BitLocker Administration and Monitoring (MBAM) control panel application, called BitLocker Encryption Options, will be available under **System and Security** when the MBAM Client is installed.</span></span> <span data-ttu-id="a32b6-105">此自定义 MBAM 控制面板取代了默认的 Windows BitLocker "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="a32b6-105">This customized MBAM control panel replaces the default Windows BitLocker control panel.</span></span> <span data-ttu-id="a32b6-106">MBAM 控制面板使你能够解锁加密的驱动器（固定和可移动），还可帮助你管理 PIN 或密码。</span><span class="sxs-lookup"><span data-stu-id="a32b6-106">The MBAM control panel enables you to unlock encrypted drives (fixed and removable), and also helps you manage your PIN or password.</span></span> <span data-ttu-id="a32b6-107">有关启用 MBAM 控制面板的详细信息，请参阅[如何在 Windows "控制面板" 中隐藏默认的 BitLocker 加密](how-to-hide-default-bitlocker-encryption-in-the-windows-control-panel.md)。</span><span class="sxs-lookup"><span data-stu-id="a32b6-107">For more information about enabling the MBAM control panel, see [How to Hide Default BitLocker Encryption in The Windows Control Panel](how-to-hide-default-bitlocker-encryption-in-the-windows-control-panel.md).</span></span>

<span data-ttu-id="a32b6-108">**注意** 对于 BitLocker 客户端，管理员和操作日志文件位于 "**应用程序和服务日志**"  /  **Microsoft**  /  **Windows**  /  **BitLockerManagement**下的 "事件查看器" 中。</span><span class="sxs-lookup"><span data-stu-id="a32b6-108">**Note** For the BitLocker client, the Admin and Operational log files are located in Event Viewer, under **Application and Services Logs** / **Microsoft** / **Windows** / **BitLockerManagement**.</span></span>

 

**<span data-ttu-id="a32b6-109">使用 "MBAM 客户端" 控制面板</span><span class="sxs-lookup"><span data-stu-id="a32b6-109">To use the MBAM Client Control Panel</span></span>**

1.  <span data-ttu-id="a32b6-110">若要打开 BitLocker 加密选项，请单击 "**开始**"，然后选择 **"控制面板"**。</span><span class="sxs-lookup"><span data-stu-id="a32b6-110">To open BitLocker Encryption Options, click **Start**, and then select **Control Panel**.</span></span> <span data-ttu-id="a32b6-111">当 **"控制面板"** 打开时，选择 "**系统和安全**"。</span><span class="sxs-lookup"><span data-stu-id="a32b6-111">When **Control Panel** opens, select **System and Security**.</span></span>

2.  <span data-ttu-id="a32b6-112">双击 " **BitLocker 加密选项**" 以打开 "自定义 MBAM" 控制面板。</span><span class="sxs-lookup"><span data-stu-id="a32b6-112">Double-click **BitLocker Encryption Options** to open the customized MBAM control panel.</span></span> <span data-ttu-id="a32b6-113">您将看到计算机上的所有硬盘驱动器及其加密状态的列表。</span><span class="sxs-lookup"><span data-stu-id="a32b6-113">You will see a list of all the hard disk drives on the computer and their encryption status.</span></span> <span data-ttu-id="a32b6-114">你还将看到用于管理 PIN 或密码的选项。</span><span class="sxs-lookup"><span data-stu-id="a32b6-114">You will also see an option to manage your PIN or passwords.</span></span>

3.  <span data-ttu-id="a32b6-115">如果已部署用户和计算机免除策略，请使用计算机上的硬盘驱动器列表来验证加密状态、解锁驱动器或请求 BitLocker 保护的豁免。</span><span class="sxs-lookup"><span data-stu-id="a32b6-115">Use the list of hard disk drives on the computer to verify the encryption status, unlock a drive, or request an exemption for BitLocker protection if the User and Computer Exemption policies have been deployed.</span></span>

4.  <span data-ttu-id="a32b6-116">非管理员可以使用 "BitLocker 加密选项" 控制面板管理 Pin 或密码。</span><span class="sxs-lookup"><span data-stu-id="a32b6-116">Non-administrators can use the BitLocker Encryption Options control panel to manage PINs or passwords.</span></span> <span data-ttu-id="a32b6-117">用户可以选择 **"管理 PIN"，** 然后输入当前 pin 和新 pin 码。</span><span class="sxs-lookup"><span data-stu-id="a32b6-117">A user can select **Manage PIN,** and then enter both a current PIN and a new PIN.</span></span> <span data-ttu-id="a32b6-118">用户也可以确认其新 PIN 码。</span><span class="sxs-lookup"><span data-stu-id="a32b6-118">Users can also confirm their new PIN.</span></span> <span data-ttu-id="a32b6-119">"**更新 PIN** " 功能会将 PIN 重置为用户选择的新 pin。</span><span class="sxs-lookup"><span data-stu-id="a32b6-119">The **Update PIN** function will reset the PIN to the new one that the user selects.</span></span>

5.  <span data-ttu-id="a32b6-120">要管理您的密码，请选择 "**解锁驱动器**"，然后输入您的当前密码。</span><span class="sxs-lookup"><span data-stu-id="a32b6-120">To manage your password, select **Unlock drive** and enter your current password.</span></span> <span data-ttu-id="a32b6-121">解锁驱动器后，选择 "**重置密码**" 以更改当前密码。</span><span class="sxs-lookup"><span data-stu-id="a32b6-121">As soon as the drive is unlocked, select **Reset Password** to change your current password.</span></span>

## <span data-ttu-id="a32b6-122">相关主题</span><span class="sxs-lookup"><span data-stu-id="a32b6-122">Related topics</span></span>


[<span data-ttu-id="a32b6-123">管理 MBAM 1.0 功能</span><span class="sxs-lookup"><span data-stu-id="a32b6-123">Administering MBAM 1.0 Features</span></span>](administering-mbam-10-features.md)

 

 





