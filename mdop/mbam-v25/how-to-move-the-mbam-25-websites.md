---
title: 如何移动 MBAM 2.5 网站
description: 如何移动 MBAM 2.5 网站
author: dansimp
ms.assetid: 71af9a54-c27b-408f-9d75-37c0d02e730e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fa5bd8156810b3dccc1588b4dfd4cadd96fd22fb
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803830"
---
# <span data-ttu-id="71611-103">如何移动 MBAM 2.5 网站</span><span class="sxs-lookup"><span data-stu-id="71611-103">How to Move the MBAM 2.5 Websites</span></span>


<span data-ttu-id="71611-104">使用以下过程将以下 MBAM 网站从一台计算机移动到另一台计算机，也就是说，将以下功能从服务器 A 移动到服务器 B：</span><span class="sxs-lookup"><span data-stu-id="71611-104">Use these procedures to move the following MBAM websites from one computer to another, that is, to move the following features from Server A to Server B:</span></span>

-   <span data-ttu-id="71611-105">管理和监视网站</span><span class="sxs-lookup"><span data-stu-id="71611-105">Administration and Monitoring Website</span></span>

-   <span data-ttu-id="71611-106">自助服务门户</span><span class="sxs-lookup"><span data-stu-id="71611-106">Self-Service Portal</span></span>

<span data-ttu-id="71611-107">**重要提示** 在配置这两个网站期间，你必须提供与你当前使用的连接字符串、报表 URL、组帐户和 web 服务应用程序池域帐户相同的连接字符串。</span><span class="sxs-lookup"><span data-stu-id="71611-107">**Important** During the configuration of both websites, you must provide the same connection string, Reports URL, group accounts, and web service application pool domain account as the ones that you are currently using.</span></span> <span data-ttu-id="71611-108">如果不使用相同的值，则无法访问某些服务器。</span><span class="sxs-lookup"><span data-stu-id="71611-108">If you don’t use the same values, you cannot access some of the servers.</span></span> <span data-ttu-id="71611-109">若要获取当前值，请使用**MbamWebApplication** Windows PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="71611-109">To get the current values, use the **Get-MbamWebApplication** Windows PowerShell cmdlet.</span></span>

 

**<span data-ttu-id="71611-110">将管理和监视网站移动到另一台服务器</span><span class="sxs-lookup"><span data-stu-id="71611-110">To move the Administration and Monitoring Website to another server</span></span>**

1.  <span data-ttu-id="71611-111">在服务器 B 上，安装 MBAM 2.5 服务器软件。</span><span class="sxs-lookup"><span data-stu-id="71611-111">On Server B, install the MBAM 2.5 Server software.</span></span> <span data-ttu-id="71611-112">有关说明，请参阅[安装 MBAM 2.5 Server 软件](installing-the-mbam-25-server-software.md)。</span><span class="sxs-lookup"><span data-stu-id="71611-112">For instructions, see [Installing the MBAM 2.5 Server Software](installing-the-mbam-25-server-software.md).</span></span>

2.  <span data-ttu-id="71611-113">在服务器 B 上，启动 "MBAM 服务器配置向导"，单击 "**添加新功能**"，然后仅选择 "**管理和监视网站**" 功能。</span><span class="sxs-lookup"><span data-stu-id="71611-113">On Server B, start the MBAM Server Configuration wizard, click **Add New Features**, and then select only the **Administration and Monitoring Website** feature.</span></span>

    <span data-ttu-id="71611-114">或者，你可以使用**Enable-MbamWebApplication** Windows PowerShell cmdlet 来配置管理和监视网站。</span><span class="sxs-lookup"><span data-stu-id="71611-114">Alternatively, you can use the **Enable-MbamWebApplication** Windows PowerShell cmdlet to configure the Administration and Monitoring Website.</span></span>

    <span data-ttu-id="71611-115">有关如何配置管理和监视网站的说明，请参阅[如何配置 MBAM 2.5 Web 应用程序](how-to-configure-the-mbam-25-web-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="71611-115">For instructions on how to configure the Administration and Monitoring Website, see [How to Configure the MBAM 2.5 Web Applications](how-to-configure-the-mbam-25-web-applications.md).</span></span>

**<span data-ttu-id="71611-116">将自助服务门户移动到另一台服务器</span><span class="sxs-lookup"><span data-stu-id="71611-116">To move the Self-Service Portal to another server</span></span>**

1.  <span data-ttu-id="71611-117">在服务器 B 上，安装 MBAM 2.5 服务器软件。</span><span class="sxs-lookup"><span data-stu-id="71611-117">On Server B, install the MBAM 2.5 Server software.</span></span> <span data-ttu-id="71611-118">有关说明，请参阅[安装 MBAM 2.5 Server 软件](installing-the-mbam-25-server-software.md)。</span><span class="sxs-lookup"><span data-stu-id="71611-118">For instructions, see [Installing the MBAM 2.5 Server Software](installing-the-mbam-25-server-software.md).</span></span>

2.  <span data-ttu-id="71611-119">在服务器 B 上，启动 "MBAM 服务器配置向导"，单击 "**添加新功能**"，然后仅选择 "**自助服务门户**" 功能。</span><span class="sxs-lookup"><span data-stu-id="71611-119">On Server B, start the MBAM Server Configuration wizard, click **Add New Features**, and then select only the **Self-Service Portal** feature.</span></span>

    <span data-ttu-id="71611-120">或者，你可以使用**Enable-MbamWebApplication** Windows PowerShell Cmdlet 配置自助服务门户。</span><span class="sxs-lookup"><span data-stu-id="71611-120">Alternatively, you can use the **Enable-MbamWebApplication** Windows PowerShell cmdlet to configure the Self-Service Portal.</span></span>

    <span data-ttu-id="71611-121">有关如何配置管理和监视网站的说明，请参阅[如何配置 MBAM 2.5 Web 应用程序](how-to-configure-the-mbam-25-web-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="71611-121">For instructions on how to configure the Administration and Monitoring Website, see [How to Configure the MBAM 2.5 Web Applications](how-to-configure-the-mbam-25-web-applications.md).</span></span>

3.  <span data-ttu-id="71611-122">如果你的组织中的客户端计算机无法访问 Microsoft 内容传递网络，你还必须移动 JavaScript 文件。</span><span class="sxs-lookup"><span data-stu-id="71611-122">If the client computers in your organization do not have access to the Microsoft Content Delivery Network, you also have to move the JavaScript files.</span></span> <span data-ttu-id="71611-123">有关详细信息，请参阅[如何在客户端计算机无法访问 Microsoft 内容传递网络时配置自助服务门户](how-to-configure-the-self-service-portal-when-client-computers-cannot-access-the-microsoft-content-delivery-network.md)。</span><span class="sxs-lookup"><span data-stu-id="71611-123">See [How to Configure the Self-Service Portal When Client Computers Cannot Access the Microsoft Content Delivery Network](how-to-configure-the-self-service-portal-when-client-computers-cannot-access-the-microsoft-content-delivery-network.md) for more information.</span></span>

4.  <span data-ttu-id="71611-124">为你的组织自定义自助服务门户。</span><span class="sxs-lookup"><span data-stu-id="71611-124">Customize the Self-Service Portal for your organization.</span></span> <span data-ttu-id="71611-125">使用[自定义组织的自助服务门户](customizing-the-self-service-portal-for-your-organization.md)中的说明查看当前自定义设置，并在服务器 B 上的自助服务器门户上配置自定义设置。</span><span class="sxs-lookup"><span data-stu-id="71611-125">Use the instructions in [Customizing the Self-Service Portal for Your Organization](customizing-the-self-service-portal-for-your-organization.md) to review your current customizations and to configure custom settings on the Self-Server Portal on Server B.</span></span>



## <span data-ttu-id="71611-126">相关主题</span><span class="sxs-lookup"><span data-stu-id="71611-126">Related topics</span></span>


[<span data-ttu-id="71611-127">如何配置 MBAM 2.5 Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="71611-127">How to Configure the MBAM 2.5 Web Applications</span></span>](how-to-configure-the-mbam-25-web-applications.md)

[<span data-ttu-id="71611-128">使用 Windows PowerShell 配置 MBAM 2.5 服务器功能</span><span class="sxs-lookup"><span data-stu-id="71611-128">Configuring MBAM 2.5 Server Features by Using Windows PowerShell</span></span>](configuring-mbam-25-server-features-by-using-windows-powershell.md)

[<span data-ttu-id="71611-129">将 MBAM 2.5 功能移动到另一个服务器上</span><span class="sxs-lookup"><span data-stu-id="71611-129">Moving MBAM 2.5 Features to Another Server</span></span>](moving-mbam-25-features-to-another-server.md)

 

## <span data-ttu-id="71611-130">已获得 MBAM 的建议？</span><span class="sxs-lookup"><span data-stu-id="71611-130">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="71611-131">在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="71611-131">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="71611-132">对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="71611-132">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





