---
title: 如何使用管理控制台发布程序包
description: 如何使用管理控制台发布程序包
author: dansimp
ms.assetid: 7c6930fc-5c89-4519-a901-512dae155fd2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 832dd95edbb0f4cd6b6ae242a81859141ebcb279
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798382"
---
# <span data-ttu-id="93f86-103">如何使用管理控制台发布程序包</span><span class="sxs-lookup"><span data-stu-id="93f86-103">How to Publish a Package by Using the Management Console</span></span>


<span data-ttu-id="93f86-104">使用以下过程发布 App-v 5.0 程序包。</span><span class="sxs-lookup"><span data-stu-id="93f86-104">Use the following procedure to publish an App-V 5.0 package.</span></span> <span data-ttu-id="93f86-105">发布程序包后，运行 App-V 5.0 客户端的计算机可以访问并运行该程序包中的应用程序。</span><span class="sxs-lookup"><span data-stu-id="93f86-105">Once you publish a package, computers that are running the App-V 5.0 client can access and run the applications in that package.</span></span>

<span data-ttu-id="93f86-106">**注意** 只有在 App-v 5.0 SP3 中才支持仅允许管理员发布或取消发布程序包（如下所述）的功能。</span><span class="sxs-lookup"><span data-stu-id="93f86-106">**Note** The ability to enable only administrators to publish or unpublish packages (described below) is supported starting in App-V 5.0 SP3.</span></span>

 

**<span data-ttu-id="93f86-107">发布 app-v 5.0 程序包</span><span class="sxs-lookup"><span data-stu-id="93f86-107">To publish an App-V 5.0 package</span></span>**

1.  <span data-ttu-id="93f86-108">在 App-v 5.0 管理控制台中。</span><span class="sxs-lookup"><span data-stu-id="93f86-108">In the App-V 5.0 Management console.</span></span> <span data-ttu-id="93f86-109">右键单击要发布的程序包的名称，然后选择 "**发布**"。</span><span class="sxs-lookup"><span data-stu-id="93f86-109">right-click the name of the package to be published, and select **Publish**.</span></span>

2.  <span data-ttu-id="93f86-110">查看 "**状态**" 列以验证程序包是否已发布，现已推出。</span><span class="sxs-lookup"><span data-stu-id="93f86-110">Review the **Status** column to verify that the package has been published and is now available.</span></span> <span data-ttu-id="93f86-111">如果程序包可用，将显示 "**已发布**状态"。</span><span class="sxs-lookup"><span data-stu-id="93f86-111">If the package is available, the status **published** is displayed.</span></span>

    <span data-ttu-id="93f86-112">如果程序包未成功发布，将显示**未发布**的状态，以及解释程序包不可用的原因的错误文本。</span><span class="sxs-lookup"><span data-stu-id="93f86-112">If the package is not published successfully, the status **unpublished** is displayed, along with error text that explains why the package is not available.</span></span>

**<span data-ttu-id="93f86-113">仅允许管理员发布或取消发布程序包</span><span class="sxs-lookup"><span data-stu-id="93f86-113">To enable only administrators to publish or unpublish packages</span></span>**

1.  <span data-ttu-id="93f86-114">导航到以下组策略对象节点：</span><span class="sxs-lookup"><span data-stu-id="93f86-114">Navigate to the following Group Policy Object node:</span></span>

    <span data-ttu-id="93f86-115">**计算机配置 &gt;策略 &gt; 管理模板 &gt; 系统 &gt; 应用程序-V &gt; 发布**。</span><span class="sxs-lookup"><span data-stu-id="93f86-115">**Computer Configuration &gt; Policies &gt; Administrative Templates &gt; System &gt; App-V &gt; Publishing**.</span></span>

2.  <span data-ttu-id="93f86-116">启用 "**要求发布为管理员**组" 策略设置。</span><span class="sxs-lookup"><span data-stu-id="93f86-116">Enable the **Require publish as administrator** Group Policy setting.</span></span>

    <span data-ttu-id="93f86-117">若要另外使用 PowerShell 设置此项，请参阅[如何使用 Powershell 管理独立计算机上运行的 V 5.0 程序包](how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md#bkmk-admins-pub-pkgs)。</span><span class="sxs-lookup"><span data-stu-id="93f86-117">To alternatively use PowerShell to set this item, see [How to Manage App-V 5.0 Packages Running on a Stand-Alone Computer by Using PowerShell](how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md#bkmk-admins-pub-pkgs).</span></span>

    <span data-ttu-id="93f86-118">已**获得有关 app-v 的建议**？</span><span class="sxs-lookup"><span data-stu-id="93f86-118">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="93f86-119">在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="93f86-119">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="93f86-120">遇到了 app-v 问题？</span><span class="sxs-lookup"><span data-stu-id="93f86-120">Got an App-V issue?</span></span>** <span data-ttu-id="93f86-121">使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="93f86-121">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="93f86-122">相关主题</span><span class="sxs-lookup"><span data-stu-id="93f86-122">Related topics</span></span>


[<span data-ttu-id="93f86-123">App-V 5.0 的操作</span><span class="sxs-lookup"><span data-stu-id="93f86-123">Operations for App-V 5.0</span></span>](operations-for-app-v-50.md)

[<span data-ttu-id="93f86-124">如何使用管理控制台配置对程序包的访问权限</span><span class="sxs-lookup"><span data-stu-id="93f86-124">How to Configure Access to Packages by Using the Management Console</span></span>](how-to-configure-access-to-packages-by-using-the-management-console-50.md)

 

 





