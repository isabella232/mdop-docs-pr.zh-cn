---
title: 如何在 Windows 控制面板中隐藏默认的 BitLocker 加密
description: 如何在 Windows 控制面板中隐藏默认的 BitLocker 加密
author: dansimp
ms.assetid: c8503743-220c-497c-9785-e2feeca484d6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 67a61763e556f8c3b93825220dbbd61a14b7d6f4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803582"
---
# <span data-ttu-id="2734d-103">如何在 Windows 控制面板中隐藏默认的 BitLocker 加密</span><span class="sxs-lookup"><span data-stu-id="2734d-103">How to Hide Default BitLocker Encryption in The Windows Control Panel</span></span>


<span data-ttu-id="2734d-104">Microsoft BitLocker 管理和监视（MBAM）为名为 "BitLocker 加密选项" 的 MBAM 客户端计算机提供自定义控制面板。</span><span class="sxs-lookup"><span data-stu-id="2734d-104">Microsoft BitLocker Administration and Monitoring (MBAM) offers a customized control panel for MBAM client computers that is named called BitLocker Encryption Options.</span></span> <span data-ttu-id="2734d-105">此自定义控制面板可以替换名为 "BitLocker 驱动器加密" 的默认 Windows BitLocker 控制面板。</span><span class="sxs-lookup"><span data-stu-id="2734d-105">This customized control panel can replace the default Windows BitLocker control panel that is named BitLocker Drive Encryption.</span></span> <span data-ttu-id="2734d-106">在 Windows "控制面板" 的 "系统和安全" 下的 "BitLocker 加密选项" 控制面板使用户能够管理其 PIN 和密码、解锁驱动器以及隐藏允许管理员解密驱动器或暂停或恢复 BitLocker 加密的界面。</span><span class="sxs-lookup"><span data-stu-id="2734d-106">The BitLocker Encryption Options control panel, located under System and Security in the Windows control panel, enables users to manage their PIN and passwords, unlock drives, and hides the interface that allows administrators to decrypt a drive or to suspend or resume BitLocker encryption.</span></span>

**<span data-ttu-id="2734d-107">在 Windows "控制面板" 中隐藏默认的 BitLocker 加密</span><span class="sxs-lookup"><span data-stu-id="2734d-107">To hide default BitLocker Encryption in the Windows Control Panel</span></span>**

1.  <span data-ttu-id="2734d-108">通过使用组策略管理控制台（GPMC）、高级组策略管理（AGPM）或 BitLocker 组策略计算机上的本地组策略编辑器，浏览到**用户配置**。</span><span class="sxs-lookup"><span data-stu-id="2734d-108">Browse to **User configuration** by using the Group Policy Management Console (GPMC), the Advanced Group Policy Management (AGPM), or the Local Group Policy Editor on the BitLocker Group Policies computer.</span></span>

2.  <span data-ttu-id="2734d-109">单击 "**策略**"，选择 "**管理模板**"，然后单击 "**控制面板"**。</span><span class="sxs-lookup"><span data-stu-id="2734d-109">Click **Policies**, select **Administrative Templates**, and then click **Control Panel**.</span></span>

3.  <span data-ttu-id="2734d-110">在 "**详细信息**" 窗格中，双击 "**隐藏指定的控制面板项目**"，然后选择 "**已启用**"。</span><span class="sxs-lookup"><span data-stu-id="2734d-110">In the **Details** pane, double-click **Hide specified Control Panel items**, and then select **Enabled**.</span></span>

4.  <span data-ttu-id="2734d-111">单击 "**显示**"，**单击 "添加 ...**"，然后键入 BitLockerDriveEncryption。</span><span class="sxs-lookup"><span data-stu-id="2734d-111">Click **Show**, **click Add…**, and then type Microsoft.BitLockerDriveEncryption.</span></span> <span data-ttu-id="2734d-112">此策略将从 Windows "控制面板" 中隐藏默认的 Windows BitLocker 管理工具，并允许用户从 Windows 控制面板打开更新的 MBAM BitLocker 加密选项工具。</span><span class="sxs-lookup"><span data-stu-id="2734d-112">This policy hides the default Windows BitLocker Management tool from the Windows Control Panel and allows the user to open the updated MBAM BitLocker Encryption Options tool from the Windows Control Panel.</span></span>

## <span data-ttu-id="2734d-113">相关主题</span><span class="sxs-lookup"><span data-stu-id="2734d-113">Related topics</span></span>


[<span data-ttu-id="2734d-114">部署 MBAM 1.0 组策略对象</span><span class="sxs-lookup"><span data-stu-id="2734d-114">Deploying MBAM 1.0 Group Policy Objects</span></span>](deploying-mbam-10-group-policy-objects.md)

 

 





