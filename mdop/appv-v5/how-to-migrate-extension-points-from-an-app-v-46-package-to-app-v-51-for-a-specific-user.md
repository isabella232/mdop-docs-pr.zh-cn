---
title: 如何为特定用户将 App-V 4.6 程序包中的扩展点迁移到 App-V 5.1
description: 如何为特定用户将 App-V 4.6 程序包中的扩展点迁移到 App-V 5.1
author: dansimp
ms.assetid: 19da3776-5ebe-41e1-9890-12b84ef3c1c7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/21/2016
ms.openlocfilehash: e2166b0f280153ad62709b21bb3477d0c4277fcd
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798403"
---
# <span data-ttu-id="d84e4-103">如何为特定用户将 App-V 4.6 程序包中的扩展点迁移到 App-V 5.1</span><span class="sxs-lookup"><span data-stu-id="d84e4-103">How to Migrate Extension Points From an App-V 4.6 Package to App-V 5.1 for a Specific User</span></span>


<span data-ttu-id="d84e4-104">使用以下过程迁移使用 "用户配置" 文件的 App-v 创建的程序包。</span><span class="sxs-lookup"><span data-stu-id="d84e4-104">Use the following procedure to migrate packages created with App-V using the user configuration file.</span></span>

<span data-ttu-id="d84e4-105">**注意** 此过程假定你运行的是最新版本的 App-v 4.6。</span><span class="sxs-lookup"><span data-stu-id="d84e4-105">**Note** This procedure assumes that you are running the latest version of App-V 4.6.</span></span>

**<span data-ttu-id="d84e4-106">转换程序包</span><span class="sxs-lookup"><span data-stu-id="d84e4-106">To convert a package</span></span>**

1. <span data-ttu-id="d84e4-107">找到要转换的程序包的用户配置文件。</span><span class="sxs-lookup"><span data-stu-id="d84e4-107">Locate the user configuration file for the package you want to convert.</span></span> <span data-ttu-id="d84e4-108">若要设置策略，请在**userConfiguration**部分中执行以下更新： \*\*ManagingAuthority TakeoverExtensionPointsFrom46 = "true" PACKAGENAME = &lt; 程序包 ID &gt; \*\*。</span><span class="sxs-lookup"><span data-stu-id="d84e4-108">To set the policy, perform the following updates in the **userConfiguration** section: **ManagingAuthority TakeoverExtensionPointsFrom46="true" PackageName=&lt;Package ID&gt;**.</span></span>

   <span data-ttu-id="d84e4-109">以下是用户配置文件的示例：</span><span class="sxs-lookup"><span data-stu-id="d84e4-109">The following is an example of a user configuration file:</span></span>

   <span data-ttu-id="d84e4-110">&lt;？ xml 版本 = "1.0"？&gt;</span><span class="sxs-lookup"><span data-stu-id="d84e4-110">&lt;?xml version="1.0" ?&gt;</span></span>

   <span data-ttu-id="d84e4-111">&lt;UserConfiguration PackageId = &lt; 程序包 ID &gt; DisplayName = &lt; 程序包的名称&gt;</span><span class="sxs-lookup"><span data-stu-id="d84e4-111">&lt;UserConfiguration PackageId=&lt;Package ID&gt; DisplayName=&lt;Name of the Package&gt;</span></span>

   <span data-ttu-id="d84e4-112">xmlns = " <https://schemas.microsoft.com/appv/2010/userconfiguration"&gt> ; &lt;ManagingAuthority TakeoverExtensionPointsFrom46 = "true"</span><span class="sxs-lookup"><span data-stu-id="d84e4-112">xmlns="<https://schemas.microsoft.com/appv/2010/userconfiguration"&gt>; &lt;ManagingAuthority TakeoverExtensionPointsFrom46="true"</span></span>

   <span data-ttu-id="d84e4-113">PackageName = &lt; 程序包 ID&gt;</span><span class="sxs-lookup"><span data-stu-id="d84e4-113">PackageName=&lt;Package ID&gt;</span></span>

   <span data-ttu-id="d84e4-114">&lt;/UserConfiguration&gt;</span><span class="sxs-lookup"><span data-stu-id="d84e4-114">&lt;/UserConfiguration&gt;</span></span>

2. <span data-ttu-id="d84e4-115">若要添加 App-v 5.1 程序包，请在提升的 PowerShell 命令提示符窗口中键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="d84e4-115">To add the App-V 5.1 package, type the following in an elevated PowerShell command prompt window:</span></span>

   <span data-ttu-id="d84e4-116">PS &gt; **$Pkg = AppvClientPackage-** &lt; 程序包位置路径路径&gt;</span><span class="sxs-lookup"><span data-stu-id="d84e4-116">PS&gt;**$pkg= Add-AppvClientPackage –Path** &lt;Path to package location&gt;</span></span>

   <span data-ttu-id="d84e4-117">PS &gt; **发布-AppVClientPackage $pkg DynamicUserConfiguration** &lt; 用户配置文件的路径&gt;</span><span class="sxs-lookup"><span data-stu-id="d84e4-117">PS&gt;**Publish-AppVClientPackage $pkg -DynamicUserConfiguration** &lt;Path to the user configuration file&gt;</span></span>

3. <span data-ttu-id="d84e4-118">现在使用 FTAs 或快捷方式打开应用程序。</span><span class="sxs-lookup"><span data-stu-id="d84e4-118">Open the application using FTAs or shortcuts now.</span></span> <span data-ttu-id="d84e4-119">应用程序应使用 App-v 5.1 打开。</span><span class="sxs-lookup"><span data-stu-id="d84e4-119">The application should open using App-V 5.1.</span></span>

   <span data-ttu-id="d84e4-120">App-v 4.6 程序包和转换后的 App-v 5.1 程序包将发布给用户，但应用程序的 FTAs 和快捷方式已由 app-v 5.1 程序包承担。</span><span class="sxs-lookup"><span data-stu-id="d84e4-120">The App-V 4.6 package and the converted App-V 5.1 package are published to the user, but the FTAs and shortcuts for the applications have been assumed by the App-V 5.1 package.</span></span>

   <span data-ttu-id="d84e4-121">已**获得有关 app-v 的建议**？</span><span class="sxs-lookup"><span data-stu-id="d84e4-121">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="d84e4-122">在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="d84e4-122">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="d84e4-123">遇到了 app-v 问题？</span><span class="sxs-lookup"><span data-stu-id="d84e4-123">Got an App-V issue?</span></span>** <span data-ttu-id="d84e4-124">使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="d84e4-124">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="d84e4-125">相关主题</span><span class="sxs-lookup"><span data-stu-id="d84e4-125">Related topics</span></span>


[<span data-ttu-id="d84e4-126">App-V 5.1 的操作</span><span class="sxs-lookup"><span data-stu-id="d84e4-126">Operations for App-V 5.1</span></span>](operations-for-app-v-51.md)

[<span data-ttu-id="d84e4-127">如何为特定用户将 App-V 5.1 程序包中的扩展点还原到 App-V 4.6 程序包</span><span class="sxs-lookup"><span data-stu-id="d84e4-127">How to Revert Extension Points From an App-V 5.1 Package to an App-V 4.6 Package for a Specific User</span></span>](how-to-revert-extension-points-from-an-app-v-51-package-to-an-app-v-46-package-for-a-specific-user.md)

 

 





