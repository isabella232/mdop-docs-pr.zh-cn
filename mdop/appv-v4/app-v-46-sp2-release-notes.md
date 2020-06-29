---
title: App-V 4.6 SP2 发行说明
description: App-V 4.6 SP2 发行说明
author: dansimp
ms.assetid: abb536f0-e187-4c5b-952a-f837abd10ad2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: cf36a6361e6f49c2b868c6752e1b2eb379cc9a31
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803149"
---
# <span data-ttu-id="8b360-103">App-V 4.6 SP2 发行说明</span><span class="sxs-lookup"><span data-stu-id="8b360-103">App-V 4.6 SP2 Release Notes</span></span>


**<span data-ttu-id="8b360-104">若要搜索这些发行说明，请按 CTRL + F。</span><span class="sxs-lookup"><span data-stu-id="8b360-104">To search these release notes, press CTRL+F.</span></span>**

<span data-ttu-id="8b360-105">安装 Microsoft Application Virtualization （app-v） 4.6 SP2 之前，请仔细阅读这些发行说明。</span><span class="sxs-lookup"><span data-stu-id="8b360-105">Read these release notes thoroughly before you install Microsoft Application Virtualization (App-V)4.6 SP2.</span></span>

<span data-ttu-id="8b360-106">这些发行说明包含成功安装 Application Virtualization 4.6 SP2 所需的信息。</span><span class="sxs-lookup"><span data-stu-id="8b360-106">These release notes contain information that is required to successfully install Application Virtualization 4.6 SP2.</span></span> <span data-ttu-id="8b360-107">发行说明还包含产品文档中不可用的信息。</span><span class="sxs-lookup"><span data-stu-id="8b360-107">The release notes also contain information that is not available in the product documentation.</span></span> <span data-ttu-id="8b360-108">如果这些发行说明和其他 App-v 4.6 文档之间存在差异，则应将最新更改视为权威。</span><span class="sxs-lookup"><span data-stu-id="8b360-108">If there is a difference between these release notes and other App-V4.6SP2 documentation, the latest change should be considered authoritative.</span></span> <span data-ttu-id="8b360-109">这些发行说明取代了本产品附带的内容。</span><span class="sxs-lookup"><span data-stu-id="8b360-109">These release notes supersede the content that is included with this product.</span></span>

## <span data-ttu-id="8b360-110">关于产品文档</span><span class="sxs-lookup"><span data-stu-id="8b360-110">About the Product Documentation</span></span>


<span data-ttu-id="8b360-111">有关 App-v 的文档的详细信息，请参阅 Microsoft TechNet 上的[应用程序虚拟化](https://go.microsoft.com/fwlink/?LinkID=232982)页面。</span><span class="sxs-lookup"><span data-stu-id="8b360-111">For more information about documentation for App-V, see the [Application Virtualization](https://go.microsoft.com/fwlink/?LinkID=232982) page on Microsoft TechNet.</span></span>

## <span data-ttu-id="8b360-112">提供反馈</span><span class="sxs-lookup"><span data-stu-id="8b360-112">Providing feedback</span></span>


<span data-ttu-id="8b360-113">我们对 app-v 4.6 SP2 的反馈感兴趣。</span><span class="sxs-lookup"><span data-stu-id="8b360-113">We are interested in your feedback on App-V4.6SP2.</span></span> <span data-ttu-id="8b360-114">您可以向发送反馈 <mdopdocs@microsoft.com> 。</span><span class="sxs-lookup"><span data-stu-id="8b360-114">You can send your feedback to <mdopdocs@microsoft.com>.</span></span>

<span data-ttu-id="8b360-115">**注意** 此电子邮件地址不是支持频道，但你的反馈将帮助我们为我们的文档和产品发布计划未来的更改。</span><span class="sxs-lookup"><span data-stu-id="8b360-115">**Note** This email address is not a support channel, but your feedback will help us to plan future changes for our documentation and product releases.</span></span>

 

<span data-ttu-id="8b360-116">有关 MDOP 和其他学习资源的最新信息，请参阅[Mdop 信息体验](https://go.microsoft.com/fwlink/p/?LinkId=236032)页面。</span><span class="sxs-lookup"><span data-stu-id="8b360-116">For the latest information about MDOP and additional learning resources, see the [MDOP Information Experience](https://go.microsoft.com/fwlink/p/?LinkId=236032) page.</span></span>

<span data-ttu-id="8b360-117">有关新更新或提供反馈的详细信息，请在[Facebook](https://go.microsoft.com/fwlink/p/?LinkId=242445)或[Twitter](https://go.microsoft.com/fwlink/p/?LinkId=242447)上关注我们。</span><span class="sxs-lookup"><span data-stu-id="8b360-117">For more information about new updates or to provide feedback, follow us on [Facebook](https://go.microsoft.com/fwlink/p/?LinkId=242445) or [Twitter](https://go.microsoft.com/fwlink/p/?LinkId=242447).</span></span>

## <a href="" id="known-issues-with-app-v-4-6-sp2-"></a><span data-ttu-id="8b360-118">有关 App-v 4.6 SP2 的已知问题</span><span class="sxs-lookup"><span data-stu-id="8b360-118">Known Issues with App-V4.6SP2</span></span>


### <span data-ttu-id="8b360-119">序列时，对非系统物理驱动器禁用短文件名支持</span><span class="sxs-lookup"><span data-stu-id="8b360-119">Short file name support is disabled for non-system physical drives when you sequence</span></span>

<span data-ttu-id="8b360-120">当你在 Windows 8 或 Windows Server 2012 上进行排序时，对于非系统物理驱动器，默认情况下将禁用短文件名（8.3）支持。</span><span class="sxs-lookup"><span data-stu-id="8b360-120">When you sequence on Windows 8 or Windows Server 2012, support for short file names (8.3) is disabled by default for non-system physical drives.</span></span>

<span data-ttu-id="8b360-121">在序列站上与主虚拟应用程序目录（例如，"Q:\\appname"）相关联的基础物理驱动器必须提供短文件名（8.3）支持，以便在创建虚拟应用程序包时，应用程序 V 4.6 SP2 Sequencer 生成短文件名。</span><span class="sxs-lookup"><span data-stu-id="8b360-121">The underlying physical drive associated with the primary virtual application directory (for example, “Q:\\appname”) on the sequencing station must provide short file name (8.3) support in order for the App-V4.6SP2 Sequencer to generate short file names when creating virtual application packages.</span></span> <span data-ttu-id="8b360-122">对于 Windows 8 或 Windows Server 2012 上的非系统物理驱动器，默认情况下禁用短文件名（8.3）支持。</span><span class="sxs-lookup"><span data-stu-id="8b360-122">Short file name (8.3) support is disabled by default for non-system physical drives on Windows 8 or Windows Server 2012.</span></span>

<span data-ttu-id="8b360-123">**解决方法：** 在非系统物理驱动器上启用短文件名（8.3）支持。</span><span class="sxs-lookup"><span data-stu-id="8b360-123">**Workaround:** Enable short file name (8.3) support on non-system physical drives.</span></span> <span data-ttu-id="8b360-124">你可以使用以下命令在 Windows 8 或 Windows Server 2012 上启用短文件名支持。</span><span class="sxs-lookup"><span data-stu-id="8b360-124">You can use the following command to enable short file name support on Windows 8 or Windows Server 2012.</span></span>

``` syntax
fsutil 8dot3name set <virtual drive letter>:
```

<span data-ttu-id="8b360-125">例如，如果驱动器号为 "Q："，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="8b360-125">For example, use the following command if the drive letter is “Q:”:</span></span>

``` syntax
fsutil 8dot3name set Q: 0
```

<span data-ttu-id="8b360-126">**注意** 无需在 App-v 客户端上更改此设置，因为 App-v 文件系统在 Windows 8 或 Windows Server 2012 上正确处理短路径。</span><span class="sxs-lookup"><span data-stu-id="8b360-126">**Note** You do not need to change this setting on the App-V client because the App-V file system properly handles short paths on Windows 8 or Windows Server 2012.</span></span>

 

### <a href="" id="-------------app-v-does-not-override-the-default-handler-for-file-type-or-protocol-associations-on-windows-8"></a> <span data-ttu-id="8b360-127">App-v 不会替代 Windows 8 上的文件类型或协议关联的默认处理程序</span><span class="sxs-lookup"><span data-stu-id="8b360-127">App-V does not override the default handler for file type or protocol associations on Windows 8</span></span>

<span data-ttu-id="8b360-128">如果在 Windows 8 上使用 **"控制面板**" 中的 "**默认程序**" 选择默认应用程序，则 app-v 不会覆盖该应用程序的关联文件类型关联。</span><span class="sxs-lookup"><span data-stu-id="8b360-128">If you select a default application by using **Default Programs** in **Control Panel** on Windows 8, App-V will not override the associated file type associations for that application.</span></span>

<span data-ttu-id="8b360-129">**解决方法：** 尚.</span><span class="sxs-lookup"><span data-stu-id="8b360-129">**Workaround:** None.</span></span>

### <span data-ttu-id="8b360-130">Windows 8 上的 mailto 可点击链接的选项不提供虚拟化 Outlook 2010</span><span class="sxs-lookup"><span data-stu-id="8b360-130">Virtualized Outlook 2010 is not offered as an option for mailto clickable links on Windows 8</span></span>

<span data-ttu-id="8b360-131">Mailto 外壳扩展不会在 Windows 8 上提供虚拟化 Outlook 2010。</span><span class="sxs-lookup"><span data-stu-id="8b360-131">The mailto shell extension does not offer virtualized Outlook 2010 on Windows 8.</span></span> <span data-ttu-id="8b360-132">例如，如果您单击来自运行在 Windows 8 上的虚拟化 Outlook 2010 的 mailto：链接，则不会创建新的电子邮件窗口。</span><span class="sxs-lookup"><span data-stu-id="8b360-132">For example, if you click a mailto: link from virtualized Outlook 2010 that is running on Windows 8, a new email window is not created.</span></span> <span data-ttu-id="8b360-133">此选项在 Windows 7 和早期版本的 Windows 操作系统上正常工作。</span><span class="sxs-lookup"><span data-stu-id="8b360-133">This option works correctly on Windows 7 and earlier versions of the Windows operating system.</span></span>

<span data-ttu-id="8b360-134">**解决方法：** 尚.</span><span class="sxs-lookup"><span data-stu-id="8b360-134">**Workaround:** None.</span></span>

### <a href="" id="-------------application-virtualization-4-6-sp2-update-is-not-offered-on-all-locales-that-use-microsoft-update"></a> <span data-ttu-id="8b360-135">在使用 Microsoft Update 的所有区域设置中不提供应用程序虚拟化 4.6 SP2 更新</span><span class="sxs-lookup"><span data-stu-id="8b360-135">Application Virtualization 4.6 SP2 update is not offered on all locales that use Microsoft Update</span></span>

<span data-ttu-id="8b360-136">使用 Microsoft Update 时，适用于以下语言区域设置的 app-v 4.6 SP2 更新不可用：</span><span class="sxs-lookup"><span data-stu-id="8b360-136">When you use Microsoft Update, the update for App-V4.6SP2 is not available for the following language locales:</span></span>

-   <span data-ttu-id="8b360-137">哈萨克语</span><span class="sxs-lookup"><span data-stu-id="8b360-137">Kazakh</span></span>

-   <span data-ttu-id="8b360-138">印地语</span><span class="sxs-lookup"><span data-stu-id="8b360-138">Hindi</span></span>

-   <span data-ttu-id="8b360-139">塞尔维亚语-西里尔文</span><span class="sxs-lookup"><span data-stu-id="8b360-139">Serbian-Cyrillic</span></span>

<span data-ttu-id="8b360-140">**解决方法：** 如果你使用的是 Microsoft Windows Server 更新服务（WSUS），请使用更新的英文版本或从 Microsoft Update 目录下载更新。</span><span class="sxs-lookup"><span data-stu-id="8b360-140">**Workaround:** If you are using Microsoft Windows Server Update Services (WSUS), use the English version of the update or download the update from the Microsoft Update Catalog.</span></span>

## <span data-ttu-id="8b360-141">发行说明版权信息</span><span class="sxs-lookup"><span data-stu-id="8b360-141">Release Notes Copyright Information</span></span>


<span data-ttu-id="8b360-142">Microsoft、Active Directory、ActiveX、Bing、Excel、Silverlight、SQLServer、Windows、MicrosoftIntune 和 WindowsPowerShell 是 Microsoft 公司组的商标。</span><span class="sxs-lookup"><span data-stu-id="8b360-142">Microsoft, Active Directory, ActiveX, Bing, Excel, Silverlight, SQLServer, Windows, MicrosoftIntune, and WindowsPowerShell are trademarks of the Microsoft group of companies.</span></span> <span data-ttu-id="8b360-143">所有其他商标的所有权属于其各自所有者。</span><span class="sxs-lookup"><span data-stu-id="8b360-143">All other trademarks are property of their respective owners.</span></span>



## <span data-ttu-id="8b360-144">相关主题</span><span class="sxs-lookup"><span data-stu-id="8b360-144">Related topics</span></span>


[<span data-ttu-id="8b360-145">关于 Microsoft Application Virtualization 4.6 SP2</span><span class="sxs-lookup"><span data-stu-id="8b360-145">About Microsoft Application Virtualization 4.6 SP2</span></span>](about-microsoft-application-virtualization-46-sp2.md)

 

 





