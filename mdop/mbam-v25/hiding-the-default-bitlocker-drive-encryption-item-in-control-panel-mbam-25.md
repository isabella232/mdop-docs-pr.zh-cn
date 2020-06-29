---
title: 在控制面板中隐藏默认的“BitLocker 驱动器加密”项目
description: 在控制面板中隐藏默认的“BitLocker 驱动器加密”项目
author: dansimp
ms.assetid: 6e2a9a02-a809-43a1-80a3-1b03c7192c89
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: af395928ca8934bfea4eeb848bbd4ee377987293
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803300"
---
# <span data-ttu-id="ea5f2-103">在控制面板中隐藏默认的“BitLocker 驱动器加密”项目</span><span class="sxs-lookup"><span data-stu-id="ea5f2-103">Hiding the Default BitLocker Drive Encryption Item in Control Panel</span></span>


<span data-ttu-id="ea5f2-104">本主题介绍了如何隐藏 " **BitLocker 驱动器加密**控制面板" 项目，该项目在 "控制面板" 中默认显示为 Windows 操作系统的一部分。</span><span class="sxs-lookup"><span data-stu-id="ea5f2-104">This topic describes how to hide the **BitLocker Drive Encryption** Control Panel item, which appears by default on Control Panel as part of the Windows operating system.</span></span>

<span data-ttu-id="ea5f2-105">**注意** Microsoft BitLocker 管理和监视（MBAM）将创建一个名为**BitLocker 加密选项**的其他自定义控制面板项，这使最终用户能够管理其 PIN 和密码、为驱动器启用 BitLocker 以及检查加密。</span><span class="sxs-lookup"><span data-stu-id="ea5f2-105">**Note** Microsoft BitLocker Administration and Monitoring (MBAM) creates an additional, custom Control Panel item, called **BitLocker Encryption Options**, which enables end users to manage their PIN and password, turn on BitLocker for a drive, and check encryption.</span></span>

 

<span data-ttu-id="ea5f2-106">请参阅[了解 "控制面板" 中的 Bitlocker 加密选项和 Bitlocker 驱动器加密项目](understanding-the-bitlocker-encryption-options-and-bitlocker-drive-encryption-items-in-control-panel.md)，了解：</span><span class="sxs-lookup"><span data-stu-id="ea5f2-106">See [Understanding the BitLocker Encryption Options and BitLocker Drive Encryption Items in Control Panel](understanding-the-bitlocker-encryption-options-and-bitlocker-drive-encryption-items-in-control-panel.md) to read about:</span></span>

-   <span data-ttu-id="ea5f2-107">"MBAM" 和 "默认控制面板" 项目之间的差异</span><span class="sxs-lookup"><span data-stu-id="ea5f2-107">Differences between the MBAM and the default Control Panel items</span></span>

-   <span data-ttu-id="ea5f2-108">**管理**在 Windows 资源管理器中右键单击驱动器时出现的 BitLocker 快捷菜单</span><span class="sxs-lookup"><span data-stu-id="ea5f2-108">**Manage BitLocker** shortcut menu that appears when you right-click a drive in Windows Explorer</span></span>

<span data-ttu-id="ea5f2-109">**重要提示** 不要更改 " **BitLocker 驱动器加密**" 节点中的组策略设置。</span><span class="sxs-lookup"><span data-stu-id="ea5f2-109">**Important** Do not change the Group Policy settings in the **BitLocker Drive Encryption** node.</span></span> <span data-ttu-id="ea5f2-110">如果您这样做，MBAM 将无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="ea5f2-110">If you do, MBAM will not work correctly.</span></span> <span data-ttu-id="ea5f2-111">在**MDOP MBAM （BitLocker Management）** 节点中配置组策略设置时，MBAM 会自动为你配置**BitLocker 驱动器加密**设置。</span><span class="sxs-lookup"><span data-stu-id="ea5f2-111">When you configure the Group Policy settings in the **MDOP MBAM (BitLocker Management)** node, MBAM automatically configures the **BitLocker Drive Encryption** settings for you.</span></span>

 

**<span data-ttu-id="ea5f2-112">隐藏 "控制面板" 中的默认 BitLocker 驱动器加密项目</span><span class="sxs-lookup"><span data-stu-id="ea5f2-112">To hide the default BitLocker Drive Encryption item in Control Panel</span></span>**

1.  <span data-ttu-id="ea5f2-113">在组策略管理控制台（GPMC）或高级组策略管理中，浏览到 "**用户配置** &gt; **策略** &gt; "**管理模板** &gt; **控制面板**。</span><span class="sxs-lookup"><span data-stu-id="ea5f2-113">In the Group Policy Management Console (GPMC) or in Advanced Group Policy Management, browse to **User configuration** &gt; **Policies** &gt; **Administrative Templates** &gt; **Control Panel**.</span></span>

2.  <span data-ttu-id="ea5f2-114">在 "**详细信息**" 窗格中，双击 "**隐藏指定的控制面板项目**"，然后单击 "**已启用**"。</span><span class="sxs-lookup"><span data-stu-id="ea5f2-114">In the **Details** pane, double-click **Hide specified Control Panel items**, and then click **Enabled**.</span></span>

3.  <span data-ttu-id="ea5f2-115">单击 "**显示**"，单击 "**添加**"，然后键入 " **BitLockerDriveEncryption**"。</span><span class="sxs-lookup"><span data-stu-id="ea5f2-115">Click **Show**, click **Add**, and then type **Microsoft.BitLockerDriveEncryption**.</span></span>



## <span data-ttu-id="ea5f2-116">相关主题</span><span class="sxs-lookup"><span data-stu-id="ea5f2-116">Related topics</span></span>


[<span data-ttu-id="ea5f2-117">了解控制面板中的“BitLocker 加密选项”和“BitLocker 驱动器加密”项</span><span class="sxs-lookup"><span data-stu-id="ea5f2-117">Understanding the BitLocker Encryption Options and BitLocker Drive Encryption Items in Control Panel</span></span>](understanding-the-bitlocker-encryption-options-and-bitlocker-drive-encryption-items-in-control-panel.md)

[<span data-ttu-id="ea5f2-118">部署 MBAM 2.5 组策略对象</span><span class="sxs-lookup"><span data-stu-id="ea5f2-118">Deploying MBAM 2.5 Group Policy Objects</span></span>](deploying-mbam-25-group-policy-objects.md)

 

## <span data-ttu-id="ea5f2-119">已获得 MBAM 的建议？</span><span class="sxs-lookup"><span data-stu-id="ea5f2-119">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="ea5f2-120">在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="ea5f2-120">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="ea5f2-121">对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="ea5f2-121">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





