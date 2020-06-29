---
title: 关于 DaRT 8.1
description: 关于 DaRT 8.1
author: dansimp
ms.assetid: dcaddc57-0111-4a9d-8be9-f5ada0eefa7d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 29c7522b4f5a5da3b451b23f2fd200db44bb9481
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802933"
---
# <span data-ttu-id="83a40-103">关于 DaRT 8.1</span><span class="sxs-lookup"><span data-stu-id="83a40-103">About DaRT 8.1</span></span>


<span data-ttu-id="83a40-104">Microsoft 诊断和恢复工具集（DaRT）8.1 提供了以下增强功能，本主题对此进行了介绍。</span><span class="sxs-lookup"><span data-stu-id="83a40-104">Microsoft Diagnostics and Recovery Toolset (DaRT) 8.1 provides the following enhancements, which are described in this topic.</span></span>

## <a href="" id="what-s-new"></a><span data-ttu-id="83a40-105">新增内容</span><span class="sxs-lookup"><span data-stu-id="83a40-105">What’s new</span></span>


-   **<span data-ttu-id="83a40-106">对 WIMBoot 的支持</span><span class="sxs-lookup"><span data-stu-id="83a40-106">Support for WIMBoot</span></span>**

    <span data-ttu-id="83a40-107">如果满足以下条件，则诊断和恢复工具集8.1 支持 Windows 映像文件启动（WIMBoot）环境：</span><span class="sxs-lookup"><span data-stu-id="83a40-107">Diagnostics and Recovery Toolset 8.1 supports the Windows image file boot (WIMBoot) environment if these conditions are met:</span></span>

    -   <span data-ttu-id="83a40-108">WIMBoot 基于 Windows 8.1 更新1或更高版本。</span><span class="sxs-lookup"><span data-stu-id="83a40-108">WIMBoot is based on Windows 8.1 Update 1 or later.</span></span>

    -   <span data-ttu-id="83a40-109">DaRT 8.1 映像构建在 Windows 8.1 更新1或更高版本上。</span><span class="sxs-lookup"><span data-stu-id="83a40-109">The DaRT 8.1 image is built on Windows 8.1 Update 1 or later.</span></span>

    <span data-ttu-id="83a40-110">有关 WIMBoot 的详细信息，请参阅[Windows 映像文件启动（WIMBoot）概述](https://go.microsoft.com/fwlink/?LinkId=517536)。</span><span class="sxs-lookup"><span data-stu-id="83a40-110">For more information about WIMBoot, see [Windows Image File Boot (WIMBoot) Overview](https://go.microsoft.com/fwlink/?LinkId=517536).</span></span>

-   **<span data-ttu-id="83a40-111">Windows Server 2012 R2 和 Windows 8.1 的支持</span><span class="sxs-lookup"><span data-stu-id="83a40-111">Support for Windows Server 2012 R2 and Windows 8.1</span></span>**

    <span data-ttu-id="83a40-112">你可以使用 Windows Server 2012 R2 或 Windows 8.1 创建 DaRT 映像。</span><span class="sxs-lookup"><span data-stu-id="83a40-112">You can create DaRT images by using Windows Server 2012 R2 or Windows 8.1.</span></span>

    **<span data-ttu-id="83a40-113">注意</span><span class="sxs-lookup"><span data-stu-id="83a40-113">Note</span></span>**  
    <span data-ttu-id="83a40-114">对于 Windows Server 和 Windows 操作系统的早期版本，请继续使用早期版本的 DaRT。</span><span class="sxs-lookup"><span data-stu-id="83a40-114">For earlier versions of the Windows Server and Windows operating systems, continue to use the earlier versions of DaRT.</span></span>



-   **<span data-ttu-id="83a40-115">客户反馈</span><span class="sxs-lookup"><span data-stu-id="83a40-115">Customer feedback</span></span>**

    <span data-ttu-id="83a40-116">DaRT 8.1 包括解决自 DaRT 8.0 SP1 发布以来发现的问题的更新。</span><span class="sxs-lookup"><span data-stu-id="83a40-116">DaRT 8.1 includes updates that address issues found since the DaRT 8.0 SP1 release.</span></span>

-   **<span data-ttu-id="83a40-117">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="83a40-117">Windows Defender</span></span>**

    <span data-ttu-id="83a40-118">Windows 8.1 中的 windows Defender 包括改进的保护。</span><span class="sxs-lookup"><span data-stu-id="83a40-118">Windows Defender in Windows 8.1 includes improved protection.</span></span> <span data-ttu-id="83a40-119">这些更改不会影响你将 DaRT 与 Windows Defender 配合使用的方式。</span><span class="sxs-lookup"><span data-stu-id="83a40-119">The changes do not impact how you use DaRT with Windows Defender.</span></span>

## <span data-ttu-id="83a40-120">要求</span><span class="sxs-lookup"><span data-stu-id="83a40-120">Requirements</span></span>


-   **<span data-ttu-id="83a40-121">Windows 评估和开发工具包8。1</span><span class="sxs-lookup"><span data-stu-id="83a40-121">Windows Assessment and Development Kit 8.1</span></span>**

    <span data-ttu-id="83a40-122">Windows 评估和开发工具包（ADK）8.1 是 DaRT 恢复映像向导必需的先决条件。</span><span class="sxs-lookup"><span data-stu-id="83a40-122">Windows Assessment and Development Kit (ADK) 8.1 is a required prerequisite for the DaRT Recovery Image Wizard.</span></span> <span data-ttu-id="83a40-123">Windows ADK 8.1 包含用于自定义、部署和服务 Windows 映像的部署工具。</span><span class="sxs-lookup"><span data-stu-id="83a40-123">Windows ADK 8.1 contains deployment tools that are used to customize, deploy, and service Windows images.</span></span> <span data-ttu-id="83a40-124">它还包含 Windows 预安装环境（Windows PE）。</span><span class="sxs-lookup"><span data-stu-id="83a40-124">It also contains the Windows Preinstallation Environment (Windows PE).</span></span>

    **<span data-ttu-id="83a40-125">注意</span><span class="sxs-lookup"><span data-stu-id="83a40-125">Note</span></span>**  
    <span data-ttu-id="83a40-126">如果仅安装远程连接查看器或故障分析器，则不需要 Windows ADK 8.1。</span><span class="sxs-lookup"><span data-stu-id="83a40-126">Windows ADK 8.1 is not required if you are installing only Remote Connection Viewer or Crash Analyzer.</span></span>



~~~
To download Windows ADK 8.1, see [Windows Assessment and Deployment Kit (Windows ADK) for Windows 8.1](https://www.microsoft.com/download/details.aspx?id=39982) in the Microsoft Download Center.
~~~

-   **<span data-ttu-id="83a40-127">Microsoft .NET Framework 4.5。1</span><span class="sxs-lookup"><span data-stu-id="83a40-127">Microsoft .NET Framework 4.5.1</span></span>**

    <span data-ttu-id="83a40-128">DaRT 8.1 需要安装 .NET Framework 4.5.1。</span><span class="sxs-lookup"><span data-stu-id="83a40-128">DaRT 8.1 requires that .NET Framework 4.5.1 is installed.</span></span> <span data-ttu-id="83a40-129">若要下载，请参阅 Microsoft 下载中心中的[Microsoft.NET Framework 4.5.1](https://go.microsoft.com/fwlink/?LinkId=329038) 。</span><span class="sxs-lookup"><span data-stu-id="83a40-129">To download, see [Microsoft.NET Framework 4.5.1](https://go.microsoft.com/fwlink/?LinkId=329038) in the Microsoft Download Center.</span></span>

-   **<span data-ttu-id="83a40-130">Windows 8.1 调试工具</span><span class="sxs-lookup"><span data-stu-id="83a40-130">Windows 8.1 Debugging Tools</span></span>**

    <span data-ttu-id="83a40-131">若要使用 DaRT 8.1 中的崩溃分析器工具，需要使用适用于 Windows 8.1 的软件开发工具包的调试工具。</span><span class="sxs-lookup"><span data-stu-id="83a40-131">To use the Crash Analyzer tool in DaRT 8.1, you need the required debugging tools, which are available in the Software Development Kit for Windows 8.1.</span></span>

    <span data-ttu-id="83a40-132">若要下载，请参阅 Microsoft 下载中心中的 windows[软件开发工具包（SDK）（适用于 windows 8.1）](https://msdn.microsoft.com/library/windows/desktop/bg162891.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="83a40-132">To download, see [Windows Software Development Kit (SDK) for Windows 8.1](https://msdn.microsoft.com/library/windows/desktop/bg162891.aspx) in the Microsoft Download Center.</span></span>

## <span data-ttu-id="83a40-133">语言可用性</span><span class="sxs-lookup"><span data-stu-id="83a40-133">Language availability</span></span>


<span data-ttu-id="83a40-134">DaRT 8.1 提供以下语言版本：</span><span class="sxs-lookup"><span data-stu-id="83a40-134">DaRT 8.1 is available in the following languages:</span></span>

-   <span data-ttu-id="83a40-135">英语（美国） en-us</span><span class="sxs-lookup"><span data-stu-id="83a40-135">English (United States) en-US</span></span>

-   <span data-ttu-id="83a40-136">法语（法国） fr-fr</span><span class="sxs-lookup"><span data-stu-id="83a40-136">French (France) fr-FR</span></span>

-   <span data-ttu-id="83a40-137">意大利语（意大利） it</span><span class="sxs-lookup"><span data-stu-id="83a40-137">Italian (Italy) it-IT</span></span>

-   <span data-ttu-id="83a40-138">德语（德国） de</span><span class="sxs-lookup"><span data-stu-id="83a40-138">German (Germany) de-DE</span></span>

-   <span data-ttu-id="83a40-139">西班牙语、国际排序（西班牙） es</span><span class="sxs-lookup"><span data-stu-id="83a40-139">Spanish, International Sort (Spain) es-ES</span></span>

-   <span data-ttu-id="83a40-140">朝鲜语（韩国） ko-KR</span><span class="sxs-lookup"><span data-stu-id="83a40-140">Korean (Korea) ko-KR</span></span>

-   <span data-ttu-id="83a40-141">日语（日本） ja-jp</span><span class="sxs-lookup"><span data-stu-id="83a40-141">Japanese (Japan) ja-JP</span></span>

-   <span data-ttu-id="83a40-142">葡萄牙语（巴西） pt-BR</span><span class="sxs-lookup"><span data-stu-id="83a40-142">Portuguese (Brazil) pt-BR</span></span>

-   <span data-ttu-id="83a40-143">俄语（俄罗斯） ru-RU</span><span class="sxs-lookup"><span data-stu-id="83a40-143">Russian (Russia) ru-RU</span></span>

-   <span data-ttu-id="83a40-144">繁体中文 zh-cn&platform-幼圆</span><span class="sxs-lookup"><span data-stu-id="83a40-144">Chinese Traditional zh-TW</span></span>

-   <span data-ttu-id="83a40-145">中文简体 zh-cn&platform-CN</span><span class="sxs-lookup"><span data-stu-id="83a40-145">Chinese Simplified zh-CN</span></span>

## <span data-ttu-id="83a40-146">如何获取 MDOP 技术</span><span class="sxs-lookup"><span data-stu-id="83a40-146">How to Get MDOP Technologies</span></span>


<span data-ttu-id="83a40-147">DaRT 8.1 是 Microsoft 桌面优化包（MDOP）的一部分。</span><span class="sxs-lookup"><span data-stu-id="83a40-147">DaRT 8.1 is a part of the Microsoft Desktop Optimization Pack (MDOP).</span></span> <span data-ttu-id="83a40-148">MDOP 是 Microsoft 软件保障的一部分。</span><span class="sxs-lookup"><span data-stu-id="83a40-148">MDOP is part of Microsoft Software Assurance.</span></span> <span data-ttu-id="83a40-149">有关 Microsoft 软件保证和获取 MDOP 的详细信息，请参阅[如何获取 mdop](https://go.microsoft.com/fwlink/?LinkId=322049) （ https://go.microsoft.com/fwlink/?LinkId=322049) 。</span><span class="sxs-lookup"><span data-stu-id="83a40-149">For more information about Microsoft Software Assurance and acquiring MDOP, see [How Do I Get MDOP](https://go.microsoft.com/fwlink/?LinkId=322049) (https://go.microsoft.com/fwlink/?LinkId=322049).</span></span>

## <span data-ttu-id="83a40-150">相关主题</span><span class="sxs-lookup"><span data-stu-id="83a40-150">Related topics</span></span>


[<span data-ttu-id="83a40-151">DaRT 8.1 发行说明</span><span class="sxs-lookup"><span data-stu-id="83a40-151">Release Notes for DaRT 8.1</span></span>](release-notes-for-dart-81.md)









