---
title: 如何在客户端计算机无法访问 Microsoft 内容交付网络时配置自助服务门户
description: 如何在客户端计算机无法访问 Microsoft 内容交付网络时配置自助服务门户
author: dansimp
ms.assetid: 90ee76db-9876-41b5-994a-118556d5ed3b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: ffce3dd023cb6ff9bd5cdb13ea789b348661de24
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803579"
---
# <span data-ttu-id="e6102-103">如何在客户端计算机无法访问 Microsoft 内容交付网络时配置自助服务门户</span><span class="sxs-lookup"><span data-stu-id="e6102-103">How to Configure the Self-Service Portal When Client Computers Cannot Access the Microsoft Content Delivery Network</span></span>


<span data-ttu-id="e6102-104">如果组织中的客户端计算机无法访问 Microsoft Ajax 内容交付网络（CDN），请按照以下说明操作。</span><span class="sxs-lookup"><span data-stu-id="e6102-104">Follow these instructions if the client computers in your organization do not have access to the Microsoft Ajax Content Delivery Network (CDN).</span></span>

**<span data-ttu-id="e6102-105">为什么需要配置：</span><span class="sxs-lookup"><span data-stu-id="e6102-105">Why you need to configure this:</span></span>**

<span data-ttu-id="e6102-106">客户端计算机需要访问 CDN，这将为自助服务门户提供对某些 JavaScript 文件所需的访问权限。</span><span class="sxs-lookup"><span data-stu-id="e6102-106">Your client computers need access to the CDN, which gives the Self-Service Portal the required access to certain JavaScript files.</span></span> <span data-ttu-id="e6102-107">如果在客户端计算机无法访问 CDN 时未配置自助服务门户，则仅显示公司名称和最终用户登录时所用的帐户。</span><span class="sxs-lookup"><span data-stu-id="e6102-107">If you don’t configure the Self-Service Portal when client computers cannot access CDN, only the company name and the account under which the end user logs in will be displayed.</span></span> <span data-ttu-id="e6102-108">将不会显示任何错误消息。</span><span class="sxs-lookup"><span data-stu-id="e6102-108">No error message will be shown.</span></span>

<span data-ttu-id="e6102-109">**注意** 在 MBAM 2.5 SP1 中，这些 JavaScript 文件包含在产品中，你无需按照本部分中的说明将 SSP 配置为支持无法访问 internet 的客户端。</span><span class="sxs-lookup"><span data-stu-id="e6102-109">**Note** In MBAM 2.5 SP1, the JavaScript files are included in the product, and you do not need to follow the instructions in this section to configure the SSP to support clients that cannot access the internet.</span></span>

 

**<span data-ttu-id="e6102-110">如何在客户端计算机无法访问 CDN 时配置自助服务门户</span><span class="sxs-lookup"><span data-stu-id="e6102-110">How to configure the Self-Service Portal when client computers cannot access the CDN</span></span>**

1. <span data-ttu-id="e6102-111">从 CDN 下载以下 JavaScript 文件：</span><span class="sxs-lookup"><span data-stu-id="e6102-111">Download the following JavaScript files from the CDN:</span></span>

   -   [<span data-ttu-id="e6102-112">jQuery-1.10.2.min.js</span><span class="sxs-lookup"><span data-stu-id="e6102-112">jQuery-1.10.2.min.js</span></span>](https://go.microsoft.com/fwlink/?LinkID=390515)

   -   [<span data-ttu-id="e6102-113">jQuery.validate.min.js</span><span class="sxs-lookup"><span data-stu-id="e6102-113">jQuery.validate.min.js</span></span>](https://go.microsoft.com/fwlink/?LinkID=390516)

   -   [<span data-ttu-id="e6102-114">jQuery.validate.unobtrusive.min.js</span><span class="sxs-lookup"><span data-stu-id="e6102-114">jQuery.validate.unobtrusive.min.js</span></span>](https://go.microsoft.com/fwlink/?LinkID=390517)

2. <span data-ttu-id="e6102-115">将 JavaScript 文件复制到自助服务门户的 "**脚本**" 目录中。</span><span class="sxs-lookup"><span data-stu-id="e6102-115">Copy the JavaScript files to the **Scripts** directory of the Self-Service Portal.</span></span> <span data-ttu-id="e6102-116">此目录位于 <em> &lt; MBAM 自助服务安装目录 &gt; \\ </em> 自助服务 Website\\Scripts。</span><span class="sxs-lookup"><span data-stu-id="e6102-116">This directory is located in <em>&lt;MBAM Self-Service Install Directory&gt;\\</em>Self Service Website\\Scripts.</span></span>

3. <span data-ttu-id="e6102-117">打开 Internet Information Services （IIS）管理器。</span><span class="sxs-lookup"><span data-stu-id="e6102-117">Open Internet Information Services (IIS) Manager.</span></span>

4. <span data-ttu-id="e6102-118">展开 "**网站** &gt; **Microsoft BitLocker 管理和监视**"，然后突出显示**SelfService**。</span><span class="sxs-lookup"><span data-stu-id="e6102-118">Expand **Sites** &gt; **Microsoft BitLocker Administration and Monitoring**, and highlight **SelfService**.</span></span>

   **<span data-ttu-id="e6102-119">注意</span><span class="sxs-lookup"><span data-stu-id="e6102-119">Note</span></span>**  
   <span data-ttu-id="e6102-120">*SelfService*是默认的虚拟目录名称。</span><span class="sxs-lookup"><span data-stu-id="e6102-120">*SelfService* is the default virtual directory name.</span></span> <span data-ttu-id="e6102-121">如果在配置期间为此目录选择了其他名称，请记住使用您选择的名称替换这些说明中的*SelfService* 。</span><span class="sxs-lookup"><span data-stu-id="e6102-121">If you chose a different name for this directory during the configuration, remember to replace *SelfService* in these instructions with the name you chose.</span></span>

     

5. <span data-ttu-id="e6102-122">在中间窗格中，双击 "**应用程序设置**"。</span><span class="sxs-lookup"><span data-stu-id="e6102-122">In the middle pane, double-click **Application Settings**.</span></span>

6. <span data-ttu-id="e6102-123">对于下表中的每个项目，通过 &lt; *virtual directory* &gt; 使用/SelfService/（或在配置期间选择的任何名称），编辑应用程序设置以引用新位置。</span><span class="sxs-lookup"><span data-stu-id="e6102-123">For each item in the following list, edit the application settings to reference the new location by replacing /&lt;*virtual directory*&gt;/ with /SelfService/ (or whatever name you chose during configuration).</span></span> <span data-ttu-id="e6102-124">例如，虚拟目录路径将类似于/selfservice/Scripts/jQuery-1.10.2.min.js。</span><span class="sxs-lookup"><span data-stu-id="e6102-124">For example, the virtual directory path will be similar to /selfservice/Scripts/ jQuery-1.10.2.min.js.</span></span>

   -   <span data-ttu-id="e6102-125">jQueryPath：/ &lt; *virtual directory* &gt; /Scripts/jQuery-1.10.2.min.js</span><span class="sxs-lookup"><span data-stu-id="e6102-125">jQueryPath: /&lt;*virtual directory*&gt;/Scripts/jQuery-1.10.2.min.js</span></span>

   -   <span data-ttu-id="e6102-126">jQueryValidatePath：/ &lt; *virtual directory* &gt; /Scripts/jQuery.validate.min.js</span><span class="sxs-lookup"><span data-stu-id="e6102-126">jQueryValidatePath: /&lt;*virtual directory*&gt;/Scripts/jQuery.validate.min.js</span></span>

   -   <span data-ttu-id="e6102-127">jQueryValidateUnobtrusivePath：/ &lt; *virtual directory* &gt; /Scripts/jQuery.validate.unobtrusive.min.js</span><span class="sxs-lookup"><span data-stu-id="e6102-127">jQueryValidateUnobtrusivePath: /&lt;*virtual directory*&gt;/Scripts/jQuery.validate.unobtrusive.min.js</span></span>



## <span data-ttu-id="e6102-128">相关主题</span><span class="sxs-lookup"><span data-stu-id="e6102-128">Related topics</span></span>


[<span data-ttu-id="e6102-129">如何配置 MBAM 2.5 Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="e6102-129">How to Configure the MBAM 2.5 Web Applications</span></span>](how-to-configure-the-mbam-25-web-applications.md)

 

## <span data-ttu-id="e6102-130">已获得 MBAM 的建议？</span><span class="sxs-lookup"><span data-stu-id="e6102-130">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="e6102-131">在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="e6102-131">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="e6102-132">对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="e6102-132">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





