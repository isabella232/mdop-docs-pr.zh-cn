---
title: 如何在 Windows 控制面板中隐藏默认的 BitLocker 加密
description: 如何在 Windows 控制面板中隐藏默认的 BitLocker 加密
author: dansimp
ms.assetid: 6674aa51-2b5d-4e4a-8b43-2cc18d008285
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: eda8fafbd7b3ebf414520354eba6def2e97f6237
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803497"
---
# <span data-ttu-id="80c2b-103">如何在 Windows 控制面板中隐藏默认的 BitLocker 加密</span><span class="sxs-lookup"><span data-stu-id="80c2b-103">How to Hide Default BitLocker Encryption in the Windows Control Panel</span></span>


<span data-ttu-id="80c2b-104">Microsoft BitLocker 管理和监视（MBAM）提供用于 Microsoft BitLocker 管理和监视客户端计算机（称为 BitLocker 加密选项）的自定义控制面板。</span><span class="sxs-lookup"><span data-stu-id="80c2b-104">Microsoft BitLocker Administration and Monitoring (MBAM) offers a customized control panel for Microsoft BitLocker Administration and Monitoring client computers, called BitLocker Encryption Options.</span></span> <span data-ttu-id="80c2b-105">此自定义控制面板可以替代默认的 Windows BitLocker 控制面板，该控制面板称为 "BitLocker 驱动器加密"。</span><span class="sxs-lookup"><span data-stu-id="80c2b-105">This customized control panel can replace the default Windows BitLocker control panel, which is called BitLocker Drive Encryption.</span></span> <span data-ttu-id="80c2b-106">"自定义控制面板" 位于 "系统和安全" 下的 "控制面板" 下，使用户能够管理其 PIN 和密码以及解锁驱动器，以及隐藏允许管理员解密驱动器或暂停或恢复 BitLocker 驱动器加密的界面。</span><span class="sxs-lookup"><span data-stu-id="80c2b-106">The customized control panel, which is in Control Panel under System and Security, enables users to manage their PIN and passwords and to unlock drives, and hides the interface that enables administrators to decrypt a drive or to suspend or resume BitLocker drive encryption.</span></span>

**<span data-ttu-id="80c2b-107">在 Windows "控制面板" 中隐藏默认的 BitLocker 驱动器加密</span><span class="sxs-lookup"><span data-stu-id="80c2b-107">To hide default BitLocker drive encryption in Windows Control Panel</span></span>**

1.  <span data-ttu-id="80c2b-108">在组策略管理控制台（GPMC）、高级组策略管理（AGPM）或 BitLocker 组策略计算机上的本地组策略编辑器中，浏览到 "**用户配置**"。</span><span class="sxs-lookup"><span data-stu-id="80c2b-108">In the Group Policy Management Console (GPMC), the Advanced Group Policy Management (AGPM), or the Local Group Policy Editor on the BitLocker Group Policies computer, browse to **User configuration**.</span></span>

2.  <span data-ttu-id="80c2b-109">接下来，单击 "**策略**"，选择 "**管理模板**"，然后单击 "**控制面板"**。</span><span class="sxs-lookup"><span data-stu-id="80c2b-109">Next, click **Policies**, select **Administrative Templates**, and then click **Control Panel**.</span></span>

3.  <span data-ttu-id="80c2b-110">双击 "**详细信息**" 窗格中的 "**隐藏指定的控制面板项目**"，然后选择 "**已启用**"。</span><span class="sxs-lookup"><span data-stu-id="80c2b-110">Double-click **Hide specified Control Panel items** in the **Details** pane, and then select **Enabled**.</span></span>

4.  <span data-ttu-id="80c2b-111">单击 "**显示**"，单击 "**添加**"，然后键入 " **BitLockerDriveEncryption**"。</span><span class="sxs-lookup"><span data-stu-id="80c2b-111">Click **Show**, click **Add**, and then type **Microsoft.BitLockerDriveEncryption**.</span></span> <span data-ttu-id="80c2b-112">此策略将从 Windows 控制面板中隐藏默认的 Windows BitLocker 管理工具，在 "控制面板" 中，允许用户在 "系统和安全" 下打开更新的 MBAM BitLocker 加密选项工具。</span><span class="sxs-lookup"><span data-stu-id="80c2b-112">This policy hides the default Windows BitLocker Management tool from the Windows Control Panel and, in Control Panel, lets the user open the updated MBAM BitLocker Encryption Options tool under System and Security.</span></span>

## <span data-ttu-id="80c2b-113">相关主题</span><span class="sxs-lookup"><span data-stu-id="80c2b-113">Related topics</span></span>


[<span data-ttu-id="80c2b-114">部署 MBAM 2.0 组策略对象</span><span class="sxs-lookup"><span data-stu-id="80c2b-114">Deploying MBAM 2.0 Group Policy Objects</span></span>](deploying-mbam-20-group-policy-objects-mbam-2.md)

 

 





