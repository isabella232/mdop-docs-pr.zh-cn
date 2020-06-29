---
title: DaRT 8.0 SP1 发行说明
description: DaRT 8.0 SP1 发行说明
author: dansimp
ms.assetid: fa7512d8-fb00-4c27-8f65-c15f3a8ff1cc
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: a4c49d12fed07f507d2db4d56969d8e7b0559c64
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803635"
---
# <span data-ttu-id="640a9-103">DaRT 8.0 SP1 发行说明</span><span class="sxs-lookup"><span data-stu-id="640a9-103">Release Notes for DaRT 8.0 SP1</span></span>


**<span data-ttu-id="640a9-104">若要搜索这些发行说明，请按 CTRL + F。</span><span class="sxs-lookup"><span data-stu-id="640a9-104">To search these release notes, press CTRL+F.</span></span>**

<span data-ttu-id="640a9-105">在安装 Microsoft 诊断和恢复工具集（DaRT） 8.0 Service Pack 1 （SP1）之前，请仔细阅读这些发行说明。</span><span class="sxs-lookup"><span data-stu-id="640a9-105">Read these release notes thoroughly before you install Microsoft Diagnostics and Recovery Toolset (DaRT) 8.0 Service Pack 1 (SP1).</span></span>

<span data-ttu-id="640a9-106">这些发行说明包含成功安装诊断和恢复工具集 8.0 SP1 所需的信息。</span><span class="sxs-lookup"><span data-stu-id="640a9-106">These release notes contain information that is required to successfully install Diagnostics and Recovery Toolset 8.0 SP1.</span></span> <span data-ttu-id="640a9-107">发行说明还包含产品文档中不可用的信息。</span><span class="sxs-lookup"><span data-stu-id="640a9-107">The release notes also contain information that is not available in the product documentation.</span></span> <span data-ttu-id="640a9-108">如果这些发行说明和其他 DaRT 文档之间存在差异，则应将最新更改视为权威。</span><span class="sxs-lookup"><span data-stu-id="640a9-108">If there is a difference between these release notes and other DaRT documentation, the latest change should be considered authoritative.</span></span> <span data-ttu-id="640a9-109">这些发行说明取代了本产品附带的内容。</span><span class="sxs-lookup"><span data-stu-id="640a9-109">These release notes supersede the content that is included with this product.</span></span>

## <span data-ttu-id="640a9-110">关于产品文档</span><span class="sxs-lookup"><span data-stu-id="640a9-110">About the product documentation</span></span>


<span data-ttu-id="640a9-111">有关 DaRT 文档的详细信息，请参阅 Microsoft TechNet 上的[DaRT 主页](https://go.microsoft.com/fwlink/?LinkID=252096)。</span><span class="sxs-lookup"><span data-stu-id="640a9-111">For information about documentation for DaRT, see the [DaRT home page](https://go.microsoft.com/fwlink/?LinkID=252096) on Microsoft TechNet.</span></span>

## <span data-ttu-id="640a9-112">DaRT 8.0 SP1 的已知问题</span><span class="sxs-lookup"><span data-stu-id="640a9-112">Known issues with DaRT 8.0 SP1</span></span>


### <span data-ttu-id="640a9-113">运行 Locksmith 或注册表编辑器时系统还原失败</span><span class="sxs-lookup"><span data-stu-id="640a9-113">System restore fails when you run Locksmith or Registry Editor</span></span>

<span data-ttu-id="640a9-114">如果您运行的是 Locksmith、注册表编辑器和其他工具，系统还原将失败。</span><span class="sxs-lookup"><span data-stu-id="640a9-114">If you run Locksmith, Registry Editor, and possibly other tools, System Restore fails.</span></span>

<span data-ttu-id="640a9-115">**解决方法：** 关闭并重新启动 DaRT，然后启动 "系统还原"。</span><span class="sxs-lookup"><span data-stu-id="640a9-115">**Workaround:** Close and restart DaRT and then start System Restore.</span></span>

### <span data-ttu-id="640a9-116">启动并关闭 Locksmith 或计算机管理后，无法运行 SFC 扫描</span><span class="sxs-lookup"><span data-stu-id="640a9-116">SFC scan fails to run after you launch and close Locksmith or Computer Management</span></span>

<span data-ttu-id="640a9-117">如果你开始然后关闭 Locksmith 或计算机管理工具，系统文件检查器将无法运行。</span><span class="sxs-lookup"><span data-stu-id="640a9-117">If you start and then close the Locksmith or Computer Management tools, System File Checker fails to run.</span></span>

<span data-ttu-id="640a9-118">**解决方法：** 关闭并重新启动 DaRT，然后启动 SFC。</span><span class="sxs-lookup"><span data-stu-id="640a9-118">**Workaround:** Close and restart DaRT and then start SFC.</span></span>

### <a href="" id="-------------dart-installer-does-not-fail-when-adk-has-not-been-installed"></a> <span data-ttu-id="640a9-119">尚未安装 ADK 时，DaRT 安装程序不会失败</span><span class="sxs-lookup"><span data-stu-id="640a9-119">DaRT installer does not fail when ADK has not been installed</span></span>

<span data-ttu-id="640a9-120">如果使用命令行运行 MSI 来安装 DaRT 8.0 SP1，但尚未安装 ADK，则 DaRT 安装应该会失败。</span><span class="sxs-lookup"><span data-stu-id="640a9-120">If you install DaRT 8.0 SP1 by using the command line to run the MSI, and the ADK has not been installed, the DaRT installation should fail.</span></span> <span data-ttu-id="640a9-121">目前，DaRT 8.0 SP1 安装程序安装了除 DaRT 恢复映像之外的所有组件。</span><span class="sxs-lookup"><span data-stu-id="640a9-121">Currently, the DaRT 8.0 SP1 installer installs all components except the DaRT recovery image.</span></span>

<span data-ttu-id="640a9-122">**解决方法：** 尚.</span><span class="sxs-lookup"><span data-stu-id="640a9-122">**Workaround:** None.</span></span>

### <span data-ttu-id="640a9-123">在 Locksmith、RegEdit、崩溃分析和计算机管理启动后，无法启动 Defender</span><span class="sxs-lookup"><span data-stu-id="640a9-123">Defender cannot be launched after Locksmith, RegEdit, Crash Analyzer, and Computer Management are launched</span></span>

<span data-ttu-id="640a9-124">如果你已启动 Locksmith、RegEdit、崩溃分析程序和计算机管理，则不会启动 Defender。</span><span class="sxs-lookup"><span data-stu-id="640a9-124">Defender does not launch if you have already launched Locksmith, RegEdit, Crash Analyzer, and Computer Management.</span></span>

<span data-ttu-id="640a9-125">**解决方法：** 关闭并重新启动 DaRT，然后启动 Defender。</span><span class="sxs-lookup"><span data-stu-id="640a9-125">**Workaround:** Close and restart DaRT and then launch Defender.</span></span>

### <span data-ttu-id="640a9-126">在启动时，Defender 可能会很慢</span><span class="sxs-lookup"><span data-stu-id="640a9-126">Defender may be slow to launch</span></span>

<span data-ttu-id="640a9-127">有时，Defender 需要几分钟才能启动。</span><span class="sxs-lookup"><span data-stu-id="640a9-127">Defender sometimes takes a few minutes to launch.</span></span> <span data-ttu-id="640a9-128">进度栏指示当前加载状态。</span><span class="sxs-lookup"><span data-stu-id="640a9-128">The progress bar indicates the current loading status.</span></span>

<span data-ttu-id="640a9-129">**解决方法：** 尚.</span><span class="sxs-lookup"><span data-stu-id="640a9-129">**Workaround:** None.</span></span>

## <span data-ttu-id="640a9-130">发行说明版权信息</span><span class="sxs-lookup"><span data-stu-id="640a9-130">Release notes copyright information</span></span>


<span data-ttu-id="640a9-131">Microsoft、Active Directory、ActiveX、Bing、Excel、Silverlight、SQLServer、Windows、MicrosoftIntune 和 WindowsPowerShell 是 Microsoft 公司组的商标。</span><span class="sxs-lookup"><span data-stu-id="640a9-131">Microsoft, Active Directory, ActiveX, Bing, Excel, Silverlight, SQLServer, Windows, MicrosoftIntune, and WindowsPowerShell are trademarks of the Microsoft group of companies.</span></span> <span data-ttu-id="640a9-132">所有其他商标的所有权属于其各自所有者。</span><span class="sxs-lookup"><span data-stu-id="640a9-132">All other trademarks are property of their respective owners.</span></span>



## <span data-ttu-id="640a9-133">相关主题</span><span class="sxs-lookup"><span data-stu-id="640a9-133">Related topics</span></span>


[<span data-ttu-id="640a9-134">关于 DaRT 8.0 SP1</span><span class="sxs-lookup"><span data-stu-id="640a9-134">About DaRT 8.0 SP1</span></span>](about-dart-80-sp1.md)

 

 





