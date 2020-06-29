---
title: 如何确定丢失计算机的 BitLocker 加密状态
description: 如何确定丢失计算机的 BitLocker 加密状态
author: dansimp
ms.assetid: 9440890a-9c63-463b-9113-f46071446388
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d9b977b20ecf219830609c3b1f646a29e6678448
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803539"
---
# <span data-ttu-id="debf2-103">如何确定丢失计算机的 BitLocker 加密状态</span><span class="sxs-lookup"><span data-stu-id="debf2-103">How to Determine the BitLocker Encryption State of a Lost Computers</span></span>


<span data-ttu-id="debf2-104">Microsoft BitLocker 管理和监视（MBAM）使你能够确定丢失或被盗计算机的上次已知 BitLocker 加密状态。</span><span class="sxs-lookup"><span data-stu-id="debf2-104">Microsoft BitLocker Administration and Monitoring (MBAM) enables you to determine the last known BitLocker encryption status of computers that are lost or stolen.</span></span> <span data-ttu-id="debf2-105">使用以下过程确定是否已在已不再存在的计算机上加密了这些卷。</span><span class="sxs-lookup"><span data-stu-id="debf2-105">Use the following procedure to determine whether the volumes have been encrypted on computers that are no longer in your possession.</span></span>

**<span data-ttu-id="debf2-106">确定计算机的上次已知 BitLocker 加密状态</span><span class="sxs-lookup"><span data-stu-id="debf2-106">Determine a Computer's Last Known BitLocker Encryption state</span></span>**

1.  <span data-ttu-id="debf2-107">打开 MBAM 网站。</span><span class="sxs-lookup"><span data-stu-id="debf2-107">Open the MBAM website.</span></span>

    <span data-ttu-id="debf2-108">**注意** MBAM 网站的默认地址是 http://\* &lt; computername &gt; \*。</span><span class="sxs-lookup"><span data-stu-id="debf2-108">**Note** The default address for the MBAM website is http://*&lt;computername&gt;*.</span></span> <span data-ttu-id="debf2-109">使用完全限定的服务器名称，以便更快地浏览结果。</span><span class="sxs-lookup"><span data-stu-id="debf2-109">Use the fully qualified server name for faster browsing results.</span></span>

     

2.  <span data-ttu-id="debf2-110">从导航窗格中选择 "**报告**" 节点，然后选择 "**计算机合规性报告**"。</span><span class="sxs-lookup"><span data-stu-id="debf2-110">Select the **Report** node from the navigation pane, and then select the **Computer Compliance Report**.</span></span>

3.  <span data-ttu-id="debf2-111">使用右侧窗格中的筛选字段缩小搜索结果范围，然后单击 "**搜索**"。</span><span class="sxs-lookup"><span data-stu-id="debf2-111">Use the filter fields in the right-side pane to narrow the search results, and then click **Search**.</span></span> <span data-ttu-id="debf2-112">结果将显示在搜索查询下方。</span><span class="sxs-lookup"><span data-stu-id="debf2-112">Results will be shown below your search query.</span></span>

4.  <span data-ttu-id="debf2-113">采取由策略为丢失的设备确定的相应操作。</span><span class="sxs-lookup"><span data-stu-id="debf2-113">Take the appropriate action as determined by your policy for lost devices.</span></span>

    <span data-ttu-id="debf2-114">**注意** 设备合规性由已部署的 BitLocker 策略确定。</span><span class="sxs-lookup"><span data-stu-id="debf2-114">**Note** Device compliance is determined by the deployed BitLocker policies.</span></span> <span data-ttu-id="debf2-115">当你尝试确定设备的 BitLocker 加密状态时，应验证这些已部署的策略。</span><span class="sxs-lookup"><span data-stu-id="debf2-115">You should verify these deployed policies when you are trying to determine the BitLocker encryption state of a device.</span></span>

     

## <span data-ttu-id="debf2-116">相关主题</span><span class="sxs-lookup"><span data-stu-id="debf2-116">Related topics</span></span>


[<span data-ttu-id="debf2-117">使用 MBAM 执行 BitLocker 管理</span><span class="sxs-lookup"><span data-stu-id="debf2-117">Performing BitLocker Management with MBAM</span></span>](performing-bitlocker-management-with-mbam.md)

 

 





