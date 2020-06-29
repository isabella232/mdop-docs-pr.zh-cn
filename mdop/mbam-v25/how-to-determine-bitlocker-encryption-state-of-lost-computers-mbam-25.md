---
title: 如何确定丢失计算机的 BitLocker 加密状态
description: 如何确定丢失计算机的 BitLocker 加密状态
author: dansimp
ms.assetid: 4f4bec1b-df3e-40ee-b431-291440268d64
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 95fb843b230804417e375946814a585d1d681634
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803575"
---
# <span data-ttu-id="dcd47-103">如何确定丢失计算机的 BitLocker 加密状态</span><span class="sxs-lookup"><span data-stu-id="dcd47-103">How to Determine BitLocker Encryption State of Lost Computers</span></span>


<span data-ttu-id="dcd47-104">将此过程与管理和监视网站配合使用以确定以下内容：</span><span class="sxs-lookup"><span data-stu-id="dcd47-104">Use this procedure with the Administration and Monitoring Website to determine the following:</span></span>

-   <span data-ttu-id="dcd47-105">已丢失或被盗计算机的上次已知 BitLocker 加密状态</span><span class="sxs-lookup"><span data-stu-id="dcd47-105">The last known BitLocker encryption status of lost or stolen computers</span></span>

-   <span data-ttu-id="dcd47-106">已丢失或被盗计算机上的卷是否已加密</span><span class="sxs-lookup"><span data-stu-id="dcd47-106">Whether the volumes on a lost or stolen computer were encrypted</span></span>

<span data-ttu-id="dcd47-107">若要完成此任务，你需要访问管理和监视网站的 "**报告**" 区域。</span><span class="sxs-lookup"><span data-stu-id="dcd47-107">To complete this task, you need access to the **Reports** area of the Administration and Monitoring Website.</span></span> <span data-ttu-id="dcd47-108">若要获取对此区域的访问权限，您必须分配有 MBAM Report Users 角色。</span><span class="sxs-lookup"><span data-stu-id="dcd47-108">To get access to this area, you must be assigned the MBAM Report Users role.</span></span> <span data-ttu-id="dcd47-109">创建这些角色时，可能会为这些角色指定不同的名称。</span><span class="sxs-lookup"><span data-stu-id="dcd47-109">You may have given these roles different names when you created them.</span></span> <span data-ttu-id="dcd47-110">有关详细信息，请参阅[规划 MBAM 2.5 组和帐户](planning-for-mbam-25-groups-and-accounts.md#bkmk-helpdesk-roles)。</span><span class="sxs-lookup"><span data-stu-id="dcd47-110">For more information, see [Planning for MBAM 2.5 Groups and Accounts](planning-for-mbam-25-groups-and-accounts.md#bkmk-helpdesk-roles).</span></span>

<span data-ttu-id="dcd47-111">**注意** 设备合规性由您的企业已部署的 BitLocker 策略确定。</span><span class="sxs-lookup"><span data-stu-id="dcd47-111">**Note** Device compliance is determined by the BitLocker policies that your enterprise has deployed.</span></span> <span data-ttu-id="dcd47-112">你可能需要先验证已部署的策略，然后再尝试确定设备的 BitLocker 加密状态。</span><span class="sxs-lookup"><span data-stu-id="dcd47-112">You may want to verify your deployed policies before you try to determine the BitLocker encryption state of a device.</span></span>

 

**<span data-ttu-id="dcd47-113">确定丢失的计算机的上次已知 BitLocker 加密状态</span><span class="sxs-lookup"><span data-stu-id="dcd47-113">To determine the last known BitLocker encryption state of lost computers</span></span>**

1.  <span data-ttu-id="dcd47-114">打开 web 浏览器并导航到 "**管理和监视" 网站**。</span><span class="sxs-lookup"><span data-stu-id="dcd47-114">Open a web browser and navigate to the **Administration and Monitoring Website**.</span></span>

2.  <span data-ttu-id="dcd47-115">在左窗格中，选择 "**报表**" 以打开 "报表" 页面。</span><span class="sxs-lookup"><span data-stu-id="dcd47-115">In the left pane, select **Reports** to open the Reports page.</span></span>

3.  <span data-ttu-id="dcd47-116">选择 "**计算机合规性报告**"。</span><span class="sxs-lookup"><span data-stu-id="dcd47-116">Select the **Computer Compliance Report**.</span></span>

4.  <span data-ttu-id="dcd47-117">使用右窗格中的筛选字段缩小搜索结果范围，然后单击 "**搜索**"。</span><span class="sxs-lookup"><span data-stu-id="dcd47-117">Use the filter fields in the right pane to narrow the search results, and then click **Search**.</span></span> <span data-ttu-id="dcd47-118">结果将显示在搜索查询下。</span><span class="sxs-lookup"><span data-stu-id="dcd47-118">Results are shown under your search query.</span></span>

5.  <span data-ttu-id="dcd47-119">采取相应的操作，由策略为丢失设备确定。</span><span class="sxs-lookup"><span data-stu-id="dcd47-119">Take the appropriate action, as determined by your policy for lost devices.</span></span>



## <span data-ttu-id="dcd47-120">相关主题</span><span class="sxs-lookup"><span data-stu-id="dcd47-120">Related topics</span></span>


[<span data-ttu-id="dcd47-121">使用 MBAM 2.5 执行 BitLocker 管理</span><span class="sxs-lookup"><span data-stu-id="dcd47-121">Performing BitLocker Management with MBAM 2.5</span></span>](performing-bitlocker-management-with-mbam-25.md)

 
## <span data-ttu-id="dcd47-122">已获得 MBAM 的建议？</span><span class="sxs-lookup"><span data-stu-id="dcd47-122">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="dcd47-123">在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="dcd47-123">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="dcd47-124">对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="dcd47-124">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>
 





