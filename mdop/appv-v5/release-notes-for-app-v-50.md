---
title: App-V 5.0 发行说明
description: App-V 5.0 发行说明
author: dansimp
ms.assetid: 68a6a5a1-4b3c-4c09-b00c-9ca4237695d5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: e49f6072d738b45afe25de24f2ee9a2d09d64a2e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798266"
---
# <span data-ttu-id="45bc5-103">App-V 5.0 发行说明</span><span class="sxs-lookup"><span data-stu-id="45bc5-103">Release Notes for App-V 5.0</span></span>


**<span data-ttu-id="45bc5-104">若要在这些发行说明中搜索特定问题，请按 CTRL + F。</span><span class="sxs-lookup"><span data-stu-id="45bc5-104">To search for a specific issue in these release notes, press CTRL+F.</span></span>**

<span data-ttu-id="45bc5-105">安装 App-v 5.0 之前，请仔细阅读这些发行说明。</span><span class="sxs-lookup"><span data-stu-id="45bc5-105">Read these release notes thoroughly before you install App-V 5.0.</span></span>

<span data-ttu-id="45bc5-106">这些发行说明包含成功安装 app-v 5.0 所需的信息。</span><span class="sxs-lookup"><span data-stu-id="45bc5-106">These release notes contain information that is required to successfully install App-V 5.0.</span></span> <span data-ttu-id="45bc5-107">发行说明还包含产品文档中不可用的信息。</span><span class="sxs-lookup"><span data-stu-id="45bc5-107">The release notes also contain information that is not available in the product documentation.</span></span> <span data-ttu-id="45bc5-108">如果这些发行说明和其他 App-v 5.0 文档之间存在差异，则应将最新更改视为权威。</span><span class="sxs-lookup"><span data-stu-id="45bc5-108">If there is a difference between these release notes and other App-V 5.0 documentation, the latest change should be considered authoritative.</span></span> <span data-ttu-id="45bc5-109">这些发行说明取代了本产品附带的内容。</span><span class="sxs-lookup"><span data-stu-id="45bc5-109">These release notes supersede the content that is included with this product.</span></span>

## <span data-ttu-id="45bc5-110">关于产品文档</span><span class="sxs-lookup"><span data-stu-id="45bc5-110">About the Product Documentation</span></span>


<span data-ttu-id="45bc5-111">有关 App-V 5.0 文档的详细信息，请参阅 Microsoft TechNet 上的 app-v 5.0 主页。</span><span class="sxs-lookup"><span data-stu-id="45bc5-111">For information about App-V 5.0 documentation, see the App-V 5.0 home page on Microsoft TechNet.</span></span>

## <span data-ttu-id="45bc5-112">提供反馈</span><span class="sxs-lookup"><span data-stu-id="45bc5-112">Provide Feedback</span></span>


<span data-ttu-id="45bc5-113">我们对 app-v 5.0 的反馈感兴趣。</span><span class="sxs-lookup"><span data-stu-id="45bc5-113">We are interested in your feedback on App-V 5.0.</span></span> <span data-ttu-id="45bc5-114">您可以向发送反馈 <mdopdocs@microsoft.com> 。</span><span class="sxs-lookup"><span data-stu-id="45bc5-114">You can send your feedback to <mdopdocs@microsoft.com>.</span></span>

<span data-ttu-id="45bc5-115">**注意** 此电子邮件地址不是支持频道，但你的反馈将帮助我们为我们的文档和产品发布计划未来的更改。</span><span class="sxs-lookup"><span data-stu-id="45bc5-115">**Note** This email address is not a support channel, but your feedback will help us to plan for future changes in our documentation and product releases.</span></span>

 

<span data-ttu-id="45bc5-116">有关 MDOP 和其他学习资源的最新信息，请参阅[Mdop 信息体验](https://go.microsoft.com/fwlink/p/?LinkId=236032)页面。</span><span class="sxs-lookup"><span data-stu-id="45bc5-116">For the latest information about MDOP and additional learning resources, see the [MDOP Information Experience](https://go.microsoft.com/fwlink/p/?LinkId=236032) page.</span></span>

<span data-ttu-id="45bc5-117">有关新更新或提供反馈的详细信息，请在[Facebook](https://go.microsoft.com/fwlink/p/?LinkId=242445)或[Twitter](https://go.microsoft.com/fwlink/p/?LinkId=242447)上关注我们。</span><span class="sxs-lookup"><span data-stu-id="45bc5-117">For more information about new updates or to provide feedback, follow us on [Facebook](https://go.microsoft.com/fwlink/p/?LinkId=242445) or [Twitter](https://go.microsoft.com/fwlink/p/?LinkId=242447).</span></span>

## <span data-ttu-id="45bc5-118">有关 App-v 5.0 的已知问题</span><span class="sxs-lookup"><span data-stu-id="45bc5-118">Known Issues with App-V 5.0</span></span>


<span data-ttu-id="45bc5-119">本部分包含有关 app-v 5.0 的已知问题的发行说明。</span><span class="sxs-lookup"><span data-stu-id="45bc5-119">This section contains release notes about the known issues with App-V 5.0.</span></span>

### <span data-ttu-id="45bc5-120">使用服务器 PowerShell cmdlet 时无法终止添加程序包的添加</span><span class="sxs-lookup"><span data-stu-id="45bc5-120">Unable to terminate adding packages when using server PowerShell cmdlets</span></span>

<span data-ttu-id="45bc5-121">使用 PowerShell 添加程序包时，不存在退出添加新程序包的方法。</span><span class="sxs-lookup"><span data-stu-id="45bc5-121">When you add a package using PowerShell, there is no method to exit adding new packages.</span></span>

<span data-ttu-id="45bc5-122">解决方法：要停止添加程序包，请在添加最终程序包后按**enter** 。</span><span class="sxs-lookup"><span data-stu-id="45bc5-122">WORKAROUND: To stop adding packages, press **enter** after you have added the final package.</span></span>

### <a href="" id="-------------app-v-5-0-client-rejects-packages-from-servers-whose-ssl-certificate-has-been-revoked"></a> <span data-ttu-id="45bc5-123">App-v 5.0 客户端拒绝来自其 SSL 证书已被吊销的服务器的程序包</span><span class="sxs-lookup"><span data-stu-id="45bc5-123">App-V 5.0 client rejects packages from servers whose SSL certificate has been revoked</span></span>

<span data-ttu-id="45bc5-124">使用 HTTPS 协议时，App-v 5.0 客户端将默认拒绝来自其 SSL 证书已被吊销的服务器的程序包。</span><span class="sxs-lookup"><span data-stu-id="45bc5-124">When using the HTTPS protocol, the App-V 5.0 client will by default reject packages from servers whose SSL certificate has been revoked.</span></span> <span data-ttu-id="45bc5-125">通过修改**VerifyCertificateRevocationList**设置，可以通过配置关闭此行为。</span><span class="sxs-lookup"><span data-stu-id="45bc5-125">This behavior can be turned off through configuration by modifying the **VerifyCertificateRevocationList** setting.</span></span> <span data-ttu-id="45bc5-126">在重新启动 app-v 5.0 服务之前，应用此设置的新配置将不会生效。</span><span class="sxs-lookup"><span data-stu-id="45bc5-126">Applying new configuration for this setting will not take effect until the App-V 5.0 service is restarted.</span></span>

<span data-ttu-id="45bc5-127">解决方法：重新启动 app-v 5.0 服务。</span><span class="sxs-lookup"><span data-stu-id="45bc5-127">WORKAROUND: Restart the App-V 5.0 service.</span></span>

## <span data-ttu-id="45bc5-128">发行说明版权信息</span><span class="sxs-lookup"><span data-stu-id="45bc5-128">Release Notes Copyright Information</span></span>


<span data-ttu-id="45bc5-129">Microsoft、Active Directory、ActiveX、Bing、Excel、Silverlight、SQLServer、Windows、MicrosoftIntune 和 WindowsPowerShell 是 Microsoft 公司组的商标。</span><span class="sxs-lookup"><span data-stu-id="45bc5-129">Microsoft, Active Directory, ActiveX, Bing, Excel, Silverlight, SQLServer, Windows, MicrosoftIntune, and WindowsPowerShell are trademarks of the Microsoft group of companies.</span></span> <span data-ttu-id="45bc5-130">所有其他商标的所有权属于其各自所有者。</span><span class="sxs-lookup"><span data-stu-id="45bc5-130">All other trademarks are property of their respective owners.</span></span>








## <span data-ttu-id="45bc5-131">相关主题</span><span class="sxs-lookup"><span data-stu-id="45bc5-131">Related topics</span></span>


[<span data-ttu-id="45bc5-132">关于 App-V 5.0</span><span class="sxs-lookup"><span data-stu-id="45bc5-132">About App-V 5.0</span></span>](about-app-v-50.md)

 

 





