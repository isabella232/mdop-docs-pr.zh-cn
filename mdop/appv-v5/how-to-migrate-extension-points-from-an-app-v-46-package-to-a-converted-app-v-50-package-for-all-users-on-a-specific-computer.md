---
title: 如何为特定计算机上的所有用户将 App-V 4.6 程序包中的扩展点迁移到转换后的 App-V 5.0 程序包
description: 如何为特定计算机上的所有用户将 App-V 4.6 程序包中的扩展点迁移到转换后的 App-V 5.0 程序包
ms.assetid: 3ae9996f-71d9-4ca1-9aab-25b599158e55
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/21/2016
ms.openlocfilehash: 3c53104907448edeb894cf4eb9dbb0a24d3229e4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798407"
---
# <span data-ttu-id="15cf4-103">如何为特定计算机上的所有用户将 App-V 4.6 程序包中的扩展点迁移到转换后的 App-V 5.0 程序包</span><span class="sxs-lookup"><span data-stu-id="15cf4-103">How to Migrate Extension Points From an App-V 4.6 Package to a Converted App-V 5.0 Package for All Users on a Specific Computer</span></span>

<span data-ttu-id="15cf4-104">**注意：** App-v 4.6 已退出主流支持。</span><span class="sxs-lookup"><span data-stu-id="15cf4-104">**Note:** App-V 4.6 has exited Mainstream support.</span></span>

<span data-ttu-id="15cf4-105">使用以下过程将扩展点从 App-v 4.6 程序包迁移到使用部署配置文件的 App-v 5.0 程序包。</span><span class="sxs-lookup"><span data-stu-id="15cf4-105">Use the following procedure to migrate extension points from an App-V4.6package to a App-V 5.0 package using the deployment configuration file.</span></span>

<span data-ttu-id="15cf4-106">**注意** 以下过程不需要 app-v 5.0 管理服务器。</span><span class="sxs-lookup"><span data-stu-id="15cf4-106">**Note** The following procedure does not require an App-V 5.0 management server.</span></span>

 

**<span data-ttu-id="15cf4-107">将程序包中的扩展点从 App-v 4.6 包迁移到使用部署配置文件的已转换的 App-v 5.0 程序包</span><span class="sxs-lookup"><span data-stu-id="15cf4-107">To migrate extension points from a package from an App-V4.6 package to a converted App-V 5.0 package using the deployment configuration file</span></span>**

1. <span data-ttu-id="15cf4-108">找到包含要迁移的程序包的部署配置文件的目录。</span><span class="sxs-lookup"><span data-stu-id="15cf4-108">Locate the directory that contains the deployment configuration file for the package you want to migrate.</span></span> <span data-ttu-id="15cf4-109">若要设置策略，请对**userConfiguration**部分进行以下更新：</span><span class="sxs-lookup"><span data-stu-id="15cf4-109">To set the policy, make the following update to the **userConfiguration** section:</span></span>

   **<span data-ttu-id="15cf4-110">ManagingAuthority TakeoverExtensionPointsFrom46 = "true" PackageName = &lt; 程序包 ID&gt;</span><span class="sxs-lookup"><span data-stu-id="15cf4-110">ManagingAuthority TakeoverExtensionPointsFrom46="true" PackageName=&lt;Package ID&gt;</span></span>**

   <span data-ttu-id="15cf4-111">下面是部署配置文件中内容的示例：</span><span class="sxs-lookup"><span data-stu-id="15cf4-111">The following is an example of content from a deployment configuration file:</span></span>

   <span data-ttu-id="15cf4-112">&lt;？ xml 版本 = "1.0"？&gt;</span><span class="sxs-lookup"><span data-stu-id="15cf4-112">&lt;?xml version="1.0" ?&gt;</span></span>

   <span data-ttu-id="15cf4-113">&lt;DeploymentConfiguration</span><span class="sxs-lookup"><span data-stu-id="15cf4-113">&lt;DeploymentConfiguration</span></span>

   <span data-ttu-id="15cf4-114">xmlns = " <https://schemas.microsoft.com/appv/2010/deploymentconfiguration> " PackageId = &lt; Package ID &gt; DisplayName = &lt; 显示名称&gt;</span><span class="sxs-lookup"><span data-stu-id="15cf4-114">xmlns="<https://schemas.microsoft.com/appv/2010/deploymentconfiguration>" PackageId=&lt;Package ID&gt; DisplayName=&lt;Display Name&gt;</span></span>

   <span data-ttu-id="15cf4-115">&lt;MachineConfiguration/&gt;</span><span class="sxs-lookup"><span data-stu-id="15cf4-115">&lt;MachineConfiguration/&gt;</span></span>

   <span data-ttu-id="15cf4-116">&lt;UserConfiguration&gt;</span><span class="sxs-lookup"><span data-stu-id="15cf4-116">&lt;UserConfiguration&gt;</span></span>

   <span data-ttu-id="15cf4-117">&lt;ManagingAuthority TakeoverExtensionPointsFrom46 = "true"</span><span class="sxs-lookup"><span data-stu-id="15cf4-117">&lt;ManagingAuthority TakeoverExtensionPointsFrom46="true"</span></span>

   <span data-ttu-id="15cf4-118">PackageName = &lt; 程序包 ID&gt;</span><span class="sxs-lookup"><span data-stu-id="15cf4-118">PackageName=&lt;Package ID&gt;</span></span>

   <span data-ttu-id="15cf4-119">&lt;/UserConfiguration&gt;</span><span class="sxs-lookup"><span data-stu-id="15cf4-119">&lt;/UserConfiguration&gt;</span></span>

   <span data-ttu-id="15cf4-120">&lt;/DeploymentConfiguration&gt;</span><span class="sxs-lookup"><span data-stu-id="15cf4-120">&lt;/DeploymentConfiguration&gt;</span></span>

2. <span data-ttu-id="15cf4-121">要添加 App-v 5.0 程序包，请在提升的 PowerShell 命令提示符中键入：</span><span class="sxs-lookup"><span data-stu-id="15cf4-121">To add the App-V 5.0 package, in an elevated PowerShell command prompt type:</span></span>

   <span data-ttu-id="15cf4-122">PS &gt; **$pkg = Add-AppvClientPackage** **-** &lt; 程序包位置的路径路径指向 &gt;  - **DynamicDeploymentConfiguration** &lt; 部署配置文件的路径 DynamicDeploymentConfiguration 路径&gt;</span><span class="sxs-lookup"><span data-stu-id="15cf4-122">PS&gt;**$pkg= Add-AppvClientPackage** **–Path** &lt;Path to package location&gt; -**DynamicDeploymentConfiguration** &lt;Path to the deployment configuration file&gt;</span></span>

   <span data-ttu-id="15cf4-123">PS &gt; **发布-AppVClientPackage $pkg**</span><span class="sxs-lookup"><span data-stu-id="15cf4-123">PS&gt;**Publish-AppVClientPackage $pkg**</span></span>

3. <span data-ttu-id="15cf4-124">若要测试迁移，请使用关联的 FTAs 或快捷方式打开虚拟应用程序。</span><span class="sxs-lookup"><span data-stu-id="15cf4-124">To test the migration, open the virtual application using associated FTAs or shortcuts.</span></span> <span data-ttu-id="15cf4-125">应用程序随即打开，其中包含 App-v 5.0。</span><span class="sxs-lookup"><span data-stu-id="15cf4-125">The application opens with App-V 5.0.</span></span> <span data-ttu-id="15cf4-126">同时，app-v 4.6 程序包和转换后的 App-v 5.0 程序包将发布给用户，但应用程序的 FTAs 和快捷方式已由 app-v 5.0 程序包承担。</span><span class="sxs-lookup"><span data-stu-id="15cf4-126">Both, the App-V 4.6 package and the converted App-V 5.0 package are published to the user, but the FTAs and shortcuts for the applications have been assumed by the App-V 5.0 package.</span></span>

   <span data-ttu-id="15cf4-127">已**获得有关 app-v 的建议**？</span><span class="sxs-lookup"><span data-stu-id="15cf4-127">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="15cf4-128">在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="15cf4-128">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="15cf4-129">遇到了 app-v 问题？</span><span class="sxs-lookup"><span data-stu-id="15cf4-129">Got an App-V issue?</span></span>** <span data-ttu-id="15cf4-130">使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="15cf4-130">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="15cf4-131">相关主题</span><span class="sxs-lookup"><span data-stu-id="15cf4-131">Related topics</span></span>


[<span data-ttu-id="15cf4-132">如何为特定计算机上的所有用户将 App-V 5.0 程序包中的扩展点还原到 App-V 4.6 程序包</span><span class="sxs-lookup"><span data-stu-id="15cf4-132">How to Revert Extension Points from an App-V 5.0 Package to an App-V 4.6 Package For All Users on a Specific Computer</span></span>](how-to-revert-extension-points-from-an-app-v-50-package-to-an-app-v-46-package-for-all-users-on-a-specific-computer.md)

[<span data-ttu-id="15cf4-133">App-V 5.0 的操作</span><span class="sxs-lookup"><span data-stu-id="15cf4-133">Operations for App-V 5.0</span></span>](operations-for-app-v-50.md)

 

 





