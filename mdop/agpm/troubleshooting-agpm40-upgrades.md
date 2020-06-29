---
title: AGPM 升级疑难解答
description: AGPM 升级疑难解答
author: dansimp
ms.assetid: 1abbf0c1-fd32-46a8-a3ba-c005f066523d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2089eac51803dca60da51f61ebdb112fbf0bda08
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801740"
---
# <span data-ttu-id="e1ed2-103">AGPM 升级疑难解答</span><span class="sxs-lookup"><span data-stu-id="e1ed2-103">Troubleshooting AGPM Upgrades</span></span>

<span data-ttu-id="e1ed2-104">本部分列出了将高级组策略管理（AGPM）服务器升级到较新版本时可能遇到的常见问题（例如，AGPM 4.0 到 AGPM 4.3）。</span><span class="sxs-lookup"><span data-stu-id="e1ed2-104">This section lists common issues that you may encounter when you upgrade your Advanced Group Policy Management (AGPM) server to a newer version (e.g. AGPM 4.0 to AGPM 4.3).</span></span> <span data-ttu-id="e1ed2-105">若要诊断此处未列出的问题，请查看[疑难解答 AGPM](troubleshooting-agpm-agpm40.md)或 AGPM 管理员（"完全控制"）以使用日志记录和跟踪。</span><span class="sxs-lookup"><span data-stu-id="e1ed2-105">To diagnose issues not listed here, it may be helpful to view the [Troubleshooting AGPM](troubleshooting-agpm-agpm40.md) or for an AGPM Administrator (Full Control) to use logging and tracing.</span></span> <span data-ttu-id="e1ed2-106">有关详细信息，请参阅[配置日志记录和跟踪](configure-logging-and-tracing-agpm40.md)。</span><span class="sxs-lookup"><span data-stu-id="e1ed2-106">For more information, see [Configure Logging and Tracing](configure-logging-and-tracing-agpm40.md).</span></span>

## <span data-ttu-id="e1ed2-107">你遇到了哪些问题？</span><span class="sxs-lookup"><span data-stu-id="e1ed2-107">What problems are you having?</span></span>

-   [<span data-ttu-id="e1ed2-108">无法生成 HTML GPO 差异报告（错误代码80004003）</span><span class="sxs-lookup"><span data-stu-id="e1ed2-108">Failed to generate a HTML GPO difference report (Error code 80004003)</span></span>](#bkmk-error-80004003)

### <a href="" id="bkmk-error-80004003"></a><span data-ttu-id="e1ed2-109">无法生成 HTML GPO 差异报告（错误代码80004003）</span><span class="sxs-lookup"><span data-stu-id="e1ed2-109">Failed to generate a HTML GPO difference report (Error code 80004003)</span></span>

-   <span data-ttu-id="e1ed2-110">**原因**：你已使用不正确的帐户安装了 AGPM 升级包。</span><span class="sxs-lookup"><span data-stu-id="e1ed2-110">**Cause**: You have installed the AGPM upgrade package with an incorrect account.</span></span>

-   <span data-ttu-id="e1ed2-111">**解决方案**：你将需要成为 AGPM 管理员才能解决此问题。</span><span class="sxs-lookup"><span data-stu-id="e1ed2-111">**Solution**: You will need to be an AGPM administrator in order to fix this issue.</span></span>
    
    -   <span data-ttu-id="e1ed2-112">请确保你知道**AGPM 服务帐户**的用户名 & 密码。</span><span class="sxs-lookup"><span data-stu-id="e1ed2-112">Ensure you know the username & password of your **AGPM service account**.</span></span>

    -   <span data-ttu-id="e1ed2-113">作为 AGPM 服务帐户交互式登录到 AGPM 服务器。</span><span class="sxs-lookup"><span data-stu-id="e1ed2-113">Log onto your AGPM server interactively as your AGPM service account.</span></span>
        
        -   <span data-ttu-id="e1ed2-114">这极其重要，因为如果你使用其他帐户，安装将失败。</span><span class="sxs-lookup"><span data-stu-id="e1ed2-114">This is critically important, as the install will fail if you use a different account.</span></span>

    -   <span data-ttu-id="e1ed2-115">关闭 AGPM 服务。</span><span class="sxs-lookup"><span data-stu-id="e1ed2-115">Shutdown the AGPM service.</span></span>
    
    -   <span data-ttu-id="e1ed2-116">安装所需的修补程序。</span><span class="sxs-lookup"><span data-stu-id="e1ed2-116">Install the required hotfix.</span></span>
    
    -   <span data-ttu-id="e1ed2-117">使用 AGPM 客户端连接到 AGPM 以测试差异报告现在是否可正常工作。</span><span class="sxs-lookup"><span data-stu-id="e1ed2-117">Connect to AGPM using an AGPM client to test that your difference reports are now functioning.</span></span>
    
## <span data-ttu-id="e1ed2-118">安装修补程序包1（适用于 Microsoft 高级组策略管理 4.0 SP3）</span><span class="sxs-lookup"><span data-stu-id="e1ed2-118">Install Hotfix Package 1 for Microsoft Advanced Group Policy Management 4.0 SP3</span></span>
    
<span data-ttu-id="e1ed2-119">**此修复程序中修复的问题**： AGPM 无法在控制或管理新组策略对象（gpo）时生成差异报告。</span><span class="sxs-lookup"><span data-stu-id="e1ed2-119">**Issue fixed in this hotfix**: AGPM can't generate difference reports when it controls or manages new Group Policy Objects (GPOs).</span></span>

<span data-ttu-id="e1ed2-120">**如何获取此更新**：安装最新版本的 Microsoft 桌面优化包（[2017 年3月的服务发布](https://www.microsoft.com/download/details.aspx?id=54967)）。</span><span class="sxs-lookup"><span data-stu-id="e1ed2-120">**How to get this update**: Install the latest version of Microsoft Desktop Optimization Pack ([March 2017 Servicing Release](https://www.microsoft.com/download/details.aspx?id=54967)).</span></span> <span data-ttu-id="e1ed2-121">有关详细信息，请参阅[KB 4014009](https://support.microsoft.com/help/4014009/) 。</span><span class="sxs-lookup"><span data-stu-id="e1ed2-121">See [KB 4014009](https://support.microsoft.com/help/4014009/) for more information.</span></span>

<span data-ttu-id="e1ed2-122">更具体地说，您可以选择仅下载第一个文件， `AGPM4.0SP1_Server_X64_KB4014009.exe` 从按下 "下载" 按钮后显示的列表中进行选择。</span><span class="sxs-lookup"><span data-stu-id="e1ed2-122">More specifically, you can choose to download only the first file, `AGPM4.0SP1_Server_X64_KB4014009.exe`, from the list presented after pressing the download button.</span></span>
      
<span data-ttu-id="e1ed2-123">Microsoft 桌面优化包的下载链接（2017年3月的服务发布）可在[此处](https://www.microsoft.com/download/details.aspx?id=54967)找到。</span><span class="sxs-lookup"><span data-stu-id="e1ed2-123">The download link to the Microsoft Desktop Optimization Pack (March 2017 Servicing Release) can be found [here](https://www.microsoft.com/download/details.aspx?id=54967).</span></span>
      
      
## <span data-ttu-id="e1ed2-124">引用链接</span><span class="sxs-lookup"><span data-stu-id="e1ed2-124">Reference link</span></span>
https://support.microsoft.com/help/3127165/hotfix-package-1-for-microsoft-advanced-group-policy-management-4-0-sp
      
