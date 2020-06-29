---
title: 如何确定丢失计算机的 BitLocker 加密状态
description: 如何确定丢失计算机的 BitLocker 加密状态
author: dansimp
ms.assetid: dbd23b64-dff3-4913-9acd-affe67b9462e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b9ea4afd6dd08f2040b9e2bd1e1a8998181d1e60
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803603"
---
# <span data-ttu-id="3de1e-103">如何确定丢失计算机的 BitLocker 加密状态</span><span class="sxs-lookup"><span data-stu-id="3de1e-103">How to Determine BitLocker Encryption State of Lost Computers</span></span>


<span data-ttu-id="3de1e-104">你可以使用 Microsoft BitLocker 管理和监视（MBAM）确定丢失或被盗的计算机的上次已知 BitLocker 加密状态。</span><span class="sxs-lookup"><span data-stu-id="3de1e-104">You can use Microsoft BitLocker Administration and Monitoring (MBAM) to determine the last known BitLocker encryption status of computers that were lost or stolen.</span></span> <span data-ttu-id="3de1e-105">以下过程介绍了如何在丢失或被盗时确定计算机上的卷是否已加密。</span><span class="sxs-lookup"><span data-stu-id="3de1e-105">The following procedure explains how to determine whether the volumes on a computer are encrypted if there is a loss or theft.</span></span>

**<span data-ttu-id="3de1e-106">确定丢失的计算机的上次已知 BitLocker 加密状态</span><span class="sxs-lookup"><span data-stu-id="3de1e-106">To determine the last known BitLocker encryption state of lost computers</span></span>**

1.  <span data-ttu-id="3de1e-107">打开 web 浏览器并导航到 "管理和监视" 网站。</span><span class="sxs-lookup"><span data-stu-id="3de1e-107">Open a web browser and navigate to the Administration and Monitoring website.</span></span>

    <span data-ttu-id="3de1e-108">**注意** 注意：管理和监视网站的默认地址是 http://\* &lt; computername &gt; \*。</span><span class="sxs-lookup"><span data-stu-id="3de1e-108">**Note** Note: The default address for the Administration and Monitoring website is http://*&lt;computername&gt;*.</span></span> <span data-ttu-id="3de1e-109">使用完全限定的服务器名称将产生更快的浏览结果。</span><span class="sxs-lookup"><span data-stu-id="3de1e-109">Using the fully qualified server name will yield faster browsing results.</span></span>

     

2.  <span data-ttu-id="3de1e-110">从导航窗格中选择 "**报告**" 节点，然后选择 "**计算机合规性报告**"。</span><span class="sxs-lookup"><span data-stu-id="3de1e-110">Selects the **Report** node from the navigation pane, and select the **Computer Compliance Report**.</span></span>

3.  <span data-ttu-id="3de1e-111">使用右窗格中的筛选字段缩小搜索结果范围，然后单击 "**搜索**"。</span><span class="sxs-lookup"><span data-stu-id="3de1e-111">Use the filter fields in the right pane to narrow the search results, and then click **Search**.</span></span> <span data-ttu-id="3de1e-112">结果将显示在搜索查询下方。</span><span class="sxs-lookup"><span data-stu-id="3de1e-112">Results are shown below your search query.</span></span>

4.  <span data-ttu-id="3de1e-113">采取相应的操作，由策略为丢失设备确定。</span><span class="sxs-lookup"><span data-stu-id="3de1e-113">Take the appropriate action, as determined by your policy for lost devices.</span></span>

    <span data-ttu-id="3de1e-114">**注意** 设备合规性由您的企业已部署的 BitLocker 策略确定。</span><span class="sxs-lookup"><span data-stu-id="3de1e-114">**Note** Device compliance is determined by the BitLocker policies that your enterprise has deployed.</span></span> <span data-ttu-id="3de1e-115">你可能需要先验证已部署的策略，然后再尝试确定设备的 BitLocker 加密状态。</span><span class="sxs-lookup"><span data-stu-id="3de1e-115">You may want to verify your deployed policies before you try to determine the BitLocker encryption state of a device.</span></span>

     

## <span data-ttu-id="3de1e-116">相关主题</span><span class="sxs-lookup"><span data-stu-id="3de1e-116">Related topics</span></span>


[<span data-ttu-id="3de1e-117">使用 MBAM 执行 BitLocker 管理</span><span class="sxs-lookup"><span data-stu-id="3de1e-117">Performing BitLocker Management with MBAM</span></span>](performing-bitlocker-management-with-mbam-mbam-2.md)

 

 





