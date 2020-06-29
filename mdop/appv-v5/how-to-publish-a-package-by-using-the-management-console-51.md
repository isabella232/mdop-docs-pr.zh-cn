---
title: 如何使用管理控制台发布程序包
description: 如何使用管理控制台发布程序包
author: dansimp
ms.assetid: e34d2bcf-15ac-4a75-9dc8-79380b36a25f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b0783a05f658da5e93603e26dc7e9581d26b81f9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798378"
---
# <span data-ttu-id="fd653-103">如何使用管理控制台发布程序包</span><span class="sxs-lookup"><span data-stu-id="fd653-103">How to Publish a Package by Using the Management Console</span></span>


<span data-ttu-id="fd653-104">使用以下过程发布 App-v 5.1 程序包。</span><span class="sxs-lookup"><span data-stu-id="fd653-104">Use the following procedure to publish an App-V 5.1 package.</span></span> <span data-ttu-id="fd653-105">发布程序包后，运行 App-V 5.1 客户端的计算机可以访问并运行该程序包中的应用程序。</span><span class="sxs-lookup"><span data-stu-id="fd653-105">Once you publish a package, computers that are running the App-V 5.1 client can access and run the applications in that package.</span></span>

<span data-ttu-id="fd653-106">**注意** 只有在 App-v 5.0 SP3 中才支持仅允许管理员发布或取消发布程序包（如下所述）的功能。</span><span class="sxs-lookup"><span data-stu-id="fd653-106">**Note** The ability to enable only administrators to publish or unpublish packages (described below) is supported starting in App-V 5.0 SP3.</span></span>

 

**<span data-ttu-id="fd653-107">发布 app-v 5.1 程序包</span><span class="sxs-lookup"><span data-stu-id="fd653-107">To publish an App-V 5.1 package</span></span>**

1.  <span data-ttu-id="fd653-108">在 App-v 5.1 管理控制台中。</span><span class="sxs-lookup"><span data-stu-id="fd653-108">In the App-V 5.1 Management console.</span></span> <span data-ttu-id="fd653-109">单击或右键单击要发布的程序包的名称。</span><span class="sxs-lookup"><span data-stu-id="fd653-109">Click or right-click the name of the package to be published.</span></span> <span data-ttu-id="fd653-110">选择**发布**。</span><span class="sxs-lookup"><span data-stu-id="fd653-110">Select **Publish**.</span></span>

2.  <span data-ttu-id="fd653-111">查看 "**状态**" 列以验证程序包是否已发布，现已推出。</span><span class="sxs-lookup"><span data-stu-id="fd653-111">Review the **Status** column to verify that the package has been published and is now available.</span></span> <span data-ttu-id="fd653-112">如果程序包可用，将显示 "**已发布**状态"。</span><span class="sxs-lookup"><span data-stu-id="fd653-112">If the package is available, the status **published** is displayed.</span></span>

    <span data-ttu-id="fd653-113">如果程序包未成功发布，将显示**未发布**的状态，以及解释程序包不可用的原因的错误文本。</span><span class="sxs-lookup"><span data-stu-id="fd653-113">If the package is not published successfully, the status **unpublished** is displayed, along with error text that explains why the package is not available.</span></span>

**<span data-ttu-id="fd653-114">仅允许管理员发布或取消发布程序包</span><span class="sxs-lookup"><span data-stu-id="fd653-114">To enable only administrators to publish or unpublish packages</span></span>**

1.  <span data-ttu-id="fd653-115">导航到以下组策略对象节点：</span><span class="sxs-lookup"><span data-stu-id="fd653-115">Navigate to the following Group Policy Object node:</span></span>

    <span data-ttu-id="fd653-116">**计算机配置 &gt;策略 &gt; 管理模板 &gt; 系统 &gt; 应用程序-V &gt; 发布**。</span><span class="sxs-lookup"><span data-stu-id="fd653-116">**Computer Configuration &gt; Policies &gt; Administrative Templates &gt; System &gt; App-V &gt; Publishing**.</span></span>

2.  <span data-ttu-id="fd653-117">启用 "**要求发布为管理员**组" 策略设置。</span><span class="sxs-lookup"><span data-stu-id="fd653-117">Enable the **Require publish as administrator** Group Policy setting.</span></span>

    <span data-ttu-id="fd653-118">若要另外使用 PowerShell 设置此项，请参阅[如何使用 Powershell 管理独立计算机上运行的 V 5.1 程序包](how-to-manage-app-v-51-packages-running-on-a-stand-alone-computer-by-using-powershell.md#bkmk-admins-pub-pkgs)。</span><span class="sxs-lookup"><span data-stu-id="fd653-118">To alternatively use PowerShell to set this item, see [How to Manage App-V 5.1 Packages Running on a Stand-Alone Computer by Using PowerShell](how-to-manage-app-v-51-packages-running-on-a-stand-alone-computer-by-using-powershell.md#bkmk-admins-pub-pkgs).</span></span>

    <span data-ttu-id="fd653-119">已**获得有关 app-v 的建议**？</span><span class="sxs-lookup"><span data-stu-id="fd653-119">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="fd653-120">在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="fd653-120">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="fd653-121">遇到了 app-v 问题？</span><span class="sxs-lookup"><span data-stu-id="fd653-121">Got an App-V issue?</span></span>** <span data-ttu-id="fd653-122">使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="fd653-122">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="fd653-123">相关主题</span><span class="sxs-lookup"><span data-stu-id="fd653-123">Related topics</span></span>


[<span data-ttu-id="fd653-124">App-V 5.1 的操作</span><span class="sxs-lookup"><span data-stu-id="fd653-124">Operations for App-V 5.1</span></span>](operations-for-app-v-51.md)

[<span data-ttu-id="fd653-125">如何使用管理控制台配置对程序包的访问权限</span><span class="sxs-lookup"><span data-stu-id="fd653-125">How to Configure Access to Packages by Using the Management Console</span></span>](how-to-configure-access-to-packages-by-using-the-management-console-51.md)

 

 





