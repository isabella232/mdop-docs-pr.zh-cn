---
title: 如何为特定用户将 App-V 4.6 程序包中的扩展点迁移到 App-V 5.0
description: 如何为特定用户将 App-V 4.6 程序包中的扩展点迁移到 App-V 5.0
ms.assetid: dad25992-3c75-4b7d-b4c6-c2edf43baaea
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/21/2016
ms.openlocfilehash: a17d9dad11092a4c8356983b70bea3c18da1be04
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798405"
---
# <span data-ttu-id="14365-103">如何为特定用户将 App-V 4.6 程序包中的扩展点迁移到 App-V 5.0</span><span class="sxs-lookup"><span data-stu-id="14365-103">How to Migrate Extension Points From an App-V 4.6 Package to App-V 5.0 for a Specific User</span></span>

<span data-ttu-id="14365-104">*注意：*\* App-V 4.6 已退出主流支持。</span><span class="sxs-lookup"><span data-stu-id="14365-104">*Note:*\* App-V 4.6 has exited Mainstream support.</span></span>

<span data-ttu-id="14365-105">使用以下过程迁移使用 "用户配置" 文件的 App-v 创建的程序包。</span><span class="sxs-lookup"><span data-stu-id="14365-105">Use the following procedure to migrate packages created with App-V using the user configuration file.</span></span>

**<span data-ttu-id="14365-106">转换程序包</span><span class="sxs-lookup"><span data-stu-id="14365-106">To convert a package</span></span>**

1. <span data-ttu-id="14365-107">找到要转换的程序包的用户配置文件。</span><span class="sxs-lookup"><span data-stu-id="14365-107">Locate the user configuration file for the package you want to convert.</span></span> <span data-ttu-id="14365-108">若要设置策略，请在**userConfiguration**部分中执行以下更新： \*\*ManagingAuthority TakeoverExtensionPointsFrom46 = "true" PACKAGENAME = &lt; 程序包 ID &gt; \*\*。</span><span class="sxs-lookup"><span data-stu-id="14365-108">To set the policy, perform the following updates in the **userConfiguration** section: **ManagingAuthority TakeoverExtensionPointsFrom46="true" PackageName=&lt;Package ID&gt;**.</span></span>

   <span data-ttu-id="14365-109">以下是用户配置文件的示例：</span><span class="sxs-lookup"><span data-stu-id="14365-109">The following is an example of a user configuration file:</span></span>

   <span data-ttu-id="14365-110">&lt;？ xml 版本 = "1.0"？&gt;</span><span class="sxs-lookup"><span data-stu-id="14365-110">&lt;?xml version="1.0" ?&gt;</span></span>

   <span data-ttu-id="14365-111">&lt;UserConfiguration PackageId = &lt; 程序包 ID &gt; DisplayName = &lt; 程序包的名称&gt;</span><span class="sxs-lookup"><span data-stu-id="14365-111">&lt;UserConfiguration PackageId=&lt;Package ID&gt; DisplayName=&lt;Name of the Package&gt;</span></span>

   <span data-ttu-id="14365-112">xmlns = " <https://schemas.microsoft.com/appv/2010/userconfiguration"&gt> ; &lt;ManagingAuthority TakeoverExtensionPointsFrom46 = "true"</span><span class="sxs-lookup"><span data-stu-id="14365-112">xmlns="<https://schemas.microsoft.com/appv/2010/userconfiguration"&gt>; &lt;ManagingAuthority TakeoverExtensionPointsFrom46="true"</span></span>

   <span data-ttu-id="14365-113">PackageName = &lt; 程序包 ID&gt;</span><span class="sxs-lookup"><span data-stu-id="14365-113">PackageName=&lt;Package ID&gt;</span></span>

   <span data-ttu-id="14365-114">&lt;/UserConfiguration&gt;</span><span class="sxs-lookup"><span data-stu-id="14365-114">&lt;/UserConfiguration&gt;</span></span>

2. <span data-ttu-id="14365-115">若要添加 App-v 5.0 程序包，请在提升的 PowerShell 命令提示符中键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="14365-115">To add the App-V 5.0 package type the following in an elevated PowerShell command prompt:</span></span>

   <span data-ttu-id="14365-116">PS &gt; **$Pkg = AppvClientPackage-** &lt; 程序包位置路径路径&gt;</span><span class="sxs-lookup"><span data-stu-id="14365-116">PS&gt;**$pkg= Add-AppvClientPackage –Path** &lt;Path to package location&gt;</span></span>

   <span data-ttu-id="14365-117">PS &gt; **发布-AppVClientPackage $pkg DynamicUserConfiguration** &lt; 用户配置文件的路径&gt;</span><span class="sxs-lookup"><span data-stu-id="14365-117">PS&gt;**Publish-AppVClientPackage $pkg -DynamicUserConfiguration** &lt;Path to the user configuration file&gt;</span></span>

3. <span data-ttu-id="14365-118">现在使用 FTAs 或快捷方式打开应用程序。</span><span class="sxs-lookup"><span data-stu-id="14365-118">Open the application using FTAs or shortcuts now.</span></span> <span data-ttu-id="14365-119">应用程序应使用 App-v 5.0 打开。</span><span class="sxs-lookup"><span data-stu-id="14365-119">The application should open using App-V 5.0.</span></span>

   <span data-ttu-id="14365-120">将向用户发布 app-v SP2 程序包和已转换的 App-v 5.0 程序包，但应用程序的 FTAs 和快捷方式已由 app-v 5.0 程序包承担。</span><span class="sxs-lookup"><span data-stu-id="14365-120">The App-V SP2 package and the converted App-V 5.0 package are published to the user, but the FTAs and shortcuts for the applications have been assumed by the App-V 5.0 package.</span></span>

   <span data-ttu-id="14365-121">已**获得有关 app-v 的建议**？</span><span class="sxs-lookup"><span data-stu-id="14365-121">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="14365-122">在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="14365-122">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="14365-123">遇到了 app-v 问题？</span><span class="sxs-lookup"><span data-stu-id="14365-123">Got an App-V issue?</span></span>** <span data-ttu-id="14365-124">使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="14365-124">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="14365-125">相关主题</span><span class="sxs-lookup"><span data-stu-id="14365-125">Related topics</span></span>


[<span data-ttu-id="14365-126">App-V 5.0 的操作</span><span class="sxs-lookup"><span data-stu-id="14365-126">Operations for App-V 5.0</span></span>](operations-for-app-v-50.md)

 

 





