---
title: DaRT 8.0 发行说明
description: DaRT 8.0 发行说明
author: dansimp
ms.assetid: e8b373c8-7aa5-4930-a8f9-743d26145dad
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 894708585ff4006c37085e71f365690b8424d43e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803638"
---
# <span data-ttu-id="c18ad-103">DaRT 8.0 发行说明</span><span class="sxs-lookup"><span data-stu-id="c18ad-103">Release Notes for DaRT 8.0</span></span>


**<span data-ttu-id="c18ad-104">若要搜索这些发行说明，请按 CTRL + F。</span><span class="sxs-lookup"><span data-stu-id="c18ad-104">To search these release notes, press CTRL+F.</span></span>**

<span data-ttu-id="c18ad-105">在安装 Microsoft 诊断和恢复工具集（DaRT）8.0 之前，请仔细阅读这些发行说明。</span><span class="sxs-lookup"><span data-stu-id="c18ad-105">Read these release notes thoroughly before you install Microsoft Diagnostics and Recovery Toolset (DaRT) 8.0.</span></span>

<span data-ttu-id="c18ad-106">这些发行说明包含成功安装 DaRT 8.0 所需的信息。</span><span class="sxs-lookup"><span data-stu-id="c18ad-106">These release notes contain information that is required to successfully install DaRT 8.0.</span></span> <span data-ttu-id="c18ad-107">发行说明还包含产品文档中不可用的信息。</span><span class="sxs-lookup"><span data-stu-id="c18ad-107">The release notes also contain information that is not available in the product documentation.</span></span> <span data-ttu-id="c18ad-108">如果这些发行说明和其他 DaRT 文档之间存在差异，则应将最新更改视为权威。</span><span class="sxs-lookup"><span data-stu-id="c18ad-108">If there is a difference between these release notes and other DaRT documentation, the latest change should be considered authoritative.</span></span> <span data-ttu-id="c18ad-109">这些发行说明取代了本产品附带的内容。</span><span class="sxs-lookup"><span data-stu-id="c18ad-109">These release notes supersede the content that is included with this product.</span></span>

<span data-ttu-id="c18ad-110">若要获取 DaRT 软件，请参阅[如何获取 MDOP](https://go.microsoft.com/fwlink/?LinkId=322049)。</span><span class="sxs-lookup"><span data-stu-id="c18ad-110">To get the DaRT software, see [How to Get MDOP](https://go.microsoft.com/fwlink/?LinkId=322049).</span></span>

## <span data-ttu-id="c18ad-111">关于产品文档</span><span class="sxs-lookup"><span data-stu-id="c18ad-111">About the product documentation</span></span>


<span data-ttu-id="c18ad-112">有关 DaRT 文档的详细信息，请参阅 Microsoft TechNet 上的[DaRT 主页](https://go.microsoft.com/fwlink/?LinkID=252096)。</span><span class="sxs-lookup"><span data-stu-id="c18ad-112">For information about documentation for DaRT, see the [DaRT home page](https://go.microsoft.com/fwlink/?LinkID=252096) on Microsoft TechNet.</span></span>

<span data-ttu-id="c18ad-113">若要获取 DaRT 文档的可下载副本，请参阅 <https://go.microsoft.com/fwlink/?LinkID=267420> Microsoft 下载中心。</span><span class="sxs-lookup"><span data-stu-id="c18ad-113">To obtain a downloadable copy of DaRT documentation, see <https://go.microsoft.com/fwlink/?LinkID=267420> on the Microsoft Download Center.</span></span>

## <span data-ttu-id="c18ad-114">提供反馈</span><span class="sxs-lookup"><span data-stu-id="c18ad-114">Providing feedback</span></span>


<span data-ttu-id="c18ad-115">我们对 DaRT 8.0 的反馈感兴趣。</span><span class="sxs-lookup"><span data-stu-id="c18ad-115">We are interested in your feedback on DaRT 8.0.</span></span> <span data-ttu-id="c18ad-116">您可以向发送反馈 <mdopdocs@microsoft.com> 。</span><span class="sxs-lookup"><span data-stu-id="c18ad-116">You can send your feedback to <mdopdocs@microsoft.com>.</span></span>

<span data-ttu-id="c18ad-117">**注意** 此电子邮件地址不是支持频道，但你的反馈将帮助我们为我们的文档和产品发布计划未来的更改。</span><span class="sxs-lookup"><span data-stu-id="c18ad-117">**Note** This email address is not a support channel, but your feedback will help us to plan future changes for our documentation and product releases.</span></span>

 

<span data-ttu-id="c18ad-118">有关 MDOP 和其他学习资源的最新信息，请参阅[Mdop 信息体验](https://go.microsoft.com/fwlink/p/?LinkId=236032)页面。</span><span class="sxs-lookup"><span data-stu-id="c18ad-118">For the latest information about MDOP and additional learning resources, see the [MDOP Information Experience](https://go.microsoft.com/fwlink/p/?LinkId=236032) page.</span></span>

<span data-ttu-id="c18ad-119">有关新更新或提供反馈的详细信息，请在[Facebook](https://go.microsoft.com/fwlink/p/?LinkId=242445)或[Twitter](https://go.microsoft.com/fwlink/p/?LinkId=242447)上关注我们。</span><span class="sxs-lookup"><span data-stu-id="c18ad-119">For more information about new updates or to provide feedback, follow us on [Facebook](https://go.microsoft.com/fwlink/p/?LinkId=242445) or [Twitter](https://go.microsoft.com/fwlink/p/?LinkId=242447).</span></span>

## <span data-ttu-id="c18ad-120">DaRT 8.0 的已知问题</span><span class="sxs-lookup"><span data-stu-id="c18ad-120">Known issues with DaRT 8.0</span></span>


### <span data-ttu-id="c18ad-121">运行 Locksmith 或注册表编辑器时系统还原失败</span><span class="sxs-lookup"><span data-stu-id="c18ad-121">System restore fails when you run Locksmith or Registry Editor</span></span>

<span data-ttu-id="c18ad-122">如果您运行的是 Locksmith、注册表编辑器和其他工具，系统还原将失败。</span><span class="sxs-lookup"><span data-stu-id="c18ad-122">If you run Locksmith, Registry Editor, and possibly other tools, System Restore fails.</span></span>

<span data-ttu-id="c18ad-123">**解决方法：** 关闭并重新启动 DaRT，然后启动 "系统还原"。</span><span class="sxs-lookup"><span data-stu-id="c18ad-123">**Workaround:** Close and restart DaRT and then start System Restore.</span></span>

### <span data-ttu-id="c18ad-124">启动并关闭 Locksmith 或计算机管理后，无法运行 SFC 扫描</span><span class="sxs-lookup"><span data-stu-id="c18ad-124">SFC scan fails to run after you launch and close Locksmith or Computer Management</span></span>

<span data-ttu-id="c18ad-125">如果你开始然后关闭 Locksmith 或计算机管理工具，系统文件检查器将无法运行。</span><span class="sxs-lookup"><span data-stu-id="c18ad-125">If you start and then close the Locksmith or Computer Management tools, System File Checker fails to run.</span></span>

<span data-ttu-id="c18ad-126">**解决方法：** 关闭并重新启动 DaRT，然后启动 SFC。</span><span class="sxs-lookup"><span data-stu-id="c18ad-126">**Workaround:** Close and restart DaRT and then start SFC.</span></span>

### <a href="" id="-------------dart-installer-does-not-fail-when-adk-has-not-been-installed"></a> <span data-ttu-id="c18ad-127">尚未安装 ADK 时，DaRT 安装程序不会失败</span><span class="sxs-lookup"><span data-stu-id="c18ad-127">DaRT installer does not fail when ADK has not been installed</span></span>

<span data-ttu-id="c18ad-128">如果使用命令行执行 MSI 安装 DaRT 8.0，但尚未安装 ADK，则 DaRT 安装应该会失败。</span><span class="sxs-lookup"><span data-stu-id="c18ad-128">If you install DaRT 8.0 by using the command line to execute the MSI, and the ADK has not been installed, the DaRT installation should fail.</span></span> <span data-ttu-id="c18ad-129">目前，DaRT 8.0 安装程序安装了除 DaRT 8.0 恢复映像之外的所有组件。</span><span class="sxs-lookup"><span data-stu-id="c18ad-129">Currently, the DaRT 8.0 installer installs all components except the DaRT 8.0 recovery image.</span></span>

<span data-ttu-id="c18ad-130">**解决方法：** 尚.</span><span class="sxs-lookup"><span data-stu-id="c18ad-130">**Workaround:** None.</span></span>

### <span data-ttu-id="c18ad-131">在 Locksmith、RegEdit、崩溃分析和计算机管理启动后，无法启动 Defender</span><span class="sxs-lookup"><span data-stu-id="c18ad-131">Defender cannot be launched after Locksmith, RegEdit, Crash Analyzer, and Computer Management are launched</span></span>

<span data-ttu-id="c18ad-132">如果你已启动 Locksmith、RegEdit、崩溃分析程序和计算机管理，则不会启动 Defender。</span><span class="sxs-lookup"><span data-stu-id="c18ad-132">Defender does not launch if you have already launched Locksmith, RegEdit, Crash Analyzer, and Computer Management.</span></span>

<span data-ttu-id="c18ad-133">**解决方法：** 关闭并重新启动 DaRT，然后启动 Defender。</span><span class="sxs-lookup"><span data-stu-id="c18ad-133">**Workaround:** Close and restart DaRT and then launch Defender.</span></span>

### <span data-ttu-id="c18ad-134">在启动时，Defender 可能会很慢</span><span class="sxs-lookup"><span data-stu-id="c18ad-134">Defender may be slow to launch</span></span>

<span data-ttu-id="c18ad-135">有时，Defender 需要几分钟才能启动。</span><span class="sxs-lookup"><span data-stu-id="c18ad-135">Defender sometimes takes a few minutes to launch.</span></span> <span data-ttu-id="c18ad-136">进度栏指示当前加载状态。</span><span class="sxs-lookup"><span data-stu-id="c18ad-136">The progress bar indicates the current loading status.</span></span>

<span data-ttu-id="c18ad-137">**解决方法：** 尚.</span><span class="sxs-lookup"><span data-stu-id="c18ad-137">**Workaround:** None.</span></span>

## <span data-ttu-id="c18ad-138">发行说明版权信息</span><span class="sxs-lookup"><span data-stu-id="c18ad-138">Release notes copyright information</span></span>


<span data-ttu-id="c18ad-139">Microsoft、Active Directory、ActiveX、Bing、Excel、Silverlight、SQLServer、Windows、MicrosoftIntune 和 WindowsPowerShell 是 Microsoft 公司组的商标。</span><span class="sxs-lookup"><span data-stu-id="c18ad-139">Microsoft, Active Directory, ActiveX, Bing, Excel, Silverlight, SQLServer, Windows, MicrosoftIntune, and WindowsPowerShell are trademarks of the Microsoft group of companies.</span></span> <span data-ttu-id="c18ad-140">所有其他商标的所有权属于其各自所有者。</span><span class="sxs-lookup"><span data-stu-id="c18ad-140">All other trademarks are property of their respective owners.</span></span>



## <span data-ttu-id="c18ad-141">相关主题</span><span class="sxs-lookup"><span data-stu-id="c18ad-141">Related topics</span></span>


[<span data-ttu-id="c18ad-142">关于 DaRT 8.0</span><span class="sxs-lookup"><span data-stu-id="c18ad-142">About DaRT 8.0</span></span>](about-dart-80-dart-8.md)

 

 





