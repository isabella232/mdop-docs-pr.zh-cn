---
title: 如何使用 ESD 来仅允许管理员发布程序包
description: 如何使用 ESD 来仅允许管理员发布程序包
author: dansimp
ms.assetid: 03367b26-83d5-4299-ad52-b9177b9cf9a8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 341e86ca806c5acc736c78cf8072aab6fb4286df
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798463"
---
# <span data-ttu-id="6d73e-103">如何使用 ESD 来仅允许管理员发布程序包</span><span class="sxs-lookup"><span data-stu-id="6d73e-103">How to Enable Only Administrators to Publish Packages by Using an ESD</span></span>


<span data-ttu-id="6d73e-104">从 app-v 5.0 SP3 开始，你可以配置 App-v 客户端，以便只有管理员（而非最终用户）可以发布或取消发布程序包。</span><span class="sxs-lookup"><span data-stu-id="6d73e-104">Starting in App-V 5.0 SP3, you can configure the App-V client so that only administrators (not end users) can publish or unpublish packages.</span></span> <span data-ttu-id="6d73e-105">在早期版本的 App-v 中，你不能阻止最终用户执行这些任务。</span><span class="sxs-lookup"><span data-stu-id="6d73e-105">In earlier versions of App-V, you could not prevent end users from performing these tasks.</span></span>

**<span data-ttu-id="6d73e-106">仅允许管理员发布或取消发布程序包</span><span class="sxs-lookup"><span data-stu-id="6d73e-106">To enable only administrators to publish or unpublish packages</span></span>**

1.  <span data-ttu-id="6d73e-107">导航到以下组策略对象节点：</span><span class="sxs-lookup"><span data-stu-id="6d73e-107">Navigate to the following Group Policy Object node:</span></span>

    <span data-ttu-id="6d73e-108">**计算机配置 &gt;策略 &gt; 管理模板 &gt; 系统 &gt; 应用程序-V &gt; 发布**。</span><span class="sxs-lookup"><span data-stu-id="6d73e-108">**Computer Configuration &gt; Policies &gt; Administrative Templates &gt; System &gt; App-V &gt; Publishing**.</span></span>

2.  <span data-ttu-id="6d73e-109">启用 "**要求发布为管理员**组" 策略设置。</span><span class="sxs-lookup"><span data-stu-id="6d73e-109">Enable the **Require publish as administrator** Group Policy setting.</span></span>

    <span data-ttu-id="6d73e-110">若要另外使用 PowerShell 设置此项，请参阅[如何使用 Powershell 管理独立计算机上运行的 V 5.0 程序包](how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md#bkmk-admins-pub-pkgs)。</span><span class="sxs-lookup"><span data-stu-id="6d73e-110">To alternatively use PowerShell to set this item, see [How to Manage App-V 5.0 Packages Running on a Stand-Alone Computer by Using PowerShell](how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md#bkmk-admins-pub-pkgs).</span></span>

    <span data-ttu-id="6d73e-111">已**获得有关 app-v 的建议**？</span><span class="sxs-lookup"><span data-stu-id="6d73e-111">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="6d73e-112">在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="6d73e-112">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="6d73e-113">遇到了 app-v 问题？</span><span class="sxs-lookup"><span data-stu-id="6d73e-113">Got an App-V issue?</span></span>** <span data-ttu-id="6d73e-114">使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="6d73e-114">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

 

 





