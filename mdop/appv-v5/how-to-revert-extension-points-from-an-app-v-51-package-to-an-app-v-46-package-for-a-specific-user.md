---
title: 如何为特定用户将 App-V 5.1 程序包中的扩展点还原到 App-V 4.6 程序包
description: 如何为特定用户将 App-V 5.1 程序包中的扩展点还原到 App-V 4.6 程序包
author: dansimp
ms.assetid: bd53c5d6-7fd2-4816-b03b-d59da0a35819
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/21/2016
ms.openlocfilehash: a69d6fb5b180161f39aa89e03b52227f32ce4879
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798369"
---
# <span data-ttu-id="564ee-103">如何为特定用户将 App-V 5.1 程序包中的扩展点还原到 App-V 4.6 程序包</span><span class="sxs-lookup"><span data-stu-id="564ee-103">How to Revert Extension Points From an App-V 5.1 Package to an App-V 4.6 Package for a Specific User</span></span>


<span data-ttu-id="564ee-104">使用以下过程，使用用户配置文件将 app-v 5.1 程序包还原到 App-v 文件格式。</span><span class="sxs-lookup"><span data-stu-id="564ee-104">Use the following procedure to revert an App-V 5.1 package to the App-V file format using the user configuration file.</span></span>

**<span data-ttu-id="564ee-105">还原程序包</span><span class="sxs-lookup"><span data-stu-id="564ee-105">To revert a package</span></span>**

1.  <span data-ttu-id="564ee-106">确保将 app-v 4.6 程序包发布到用户，但 FTAs 和快捷方式已由 app-v 5.1 程序包（使用以下迁移方法）使用，[如何将应用程序 v 4.6 程序包中的扩展点迁移到特定用户](how-to-migrate-extension-points-from-an-app-v-46-package-to-app-v-51-for-a-specific-user.md)的 app-v 5.1。</span><span class="sxs-lookup"><span data-stu-id="564ee-106">Ensure that App-V 4.6 package is published to the users but the FTAs and shortcuts have been assumed by App-V 5.1 package using the following migration method, [How to Migrate Extension Points From an App-V 4.6 Package to App-V 5.1 for a Specific User](how-to-migrate-extension-points-from-an-app-v-46-package-to-app-v-51-for-a-specific-user.md).</span></span>

    <span data-ttu-id="564ee-107">在已转换程序包的部署配置文件的 " **userConfiguration** " 部分中，若要设置策略，请对**userConfiguration**部分进行以下更新： \*\*ManagingAuthority TakeoverExtensionPointsFrom46 = "FALSE" PackageName = &lt; 程序包 ID &gt; \*\*</span><span class="sxs-lookup"><span data-stu-id="564ee-107">In the **userConfiguration** section of the deployment configuration file for the converted package, to set the policy, make the following update to the **userConfiguration** section: **ManagingAuthority TakeoverExtensionPointsFrom46="false" PackageName=&lt;Package ID&gt;**</span></span>

2.  <span data-ttu-id="564ee-108">从提升的命令提示符处，键入：</span><span class="sxs-lookup"><span data-stu-id="564ee-108">From an elevated command prompt, type:</span></span>

    <span data-ttu-id="564ee-109">PS &gt; **发布-AppVClientPackage $Pkg-DynamicUserConfigurationPath** &lt; 用户配置文件的路径&gt;</span><span class="sxs-lookup"><span data-stu-id="564ee-109">PS&gt;**Publish-AppVClientPackage $pkg –DynamicUserConfigurationPath** &lt;path to user configuration file&gt;</span></span>

3.  <span data-ttu-id="564ee-110">执行发布刷新，或等待应用的下一次计划发布刷新-V 4.6。</span><span class="sxs-lookup"><span data-stu-id="564ee-110">Perform a publishing refresh, or wait for the next scheduled publishing refresh for the App-V 4.6.</span></span> <span data-ttu-id="564ee-111">使用 FTAs 或快捷方式打开应用程序。</span><span class="sxs-lookup"><span data-stu-id="564ee-111">Open the application using FTAs or shortcuts.</span></span> <span data-ttu-id="564ee-112">应用程序现在应使用 App-v 4.6 打开。</span><span class="sxs-lookup"><span data-stu-id="564ee-112">The Application should now open using App-V 4.6.</span></span>

    **<span data-ttu-id="564ee-113">注意</span><span class="sxs-lookup"><span data-stu-id="564ee-113">Note</span></span>**  
    <span data-ttu-id="564ee-114">如果您不再需要 app-v 5.1 程序包，则可以取消发布 app-v 5.1 程序包，扩展点将自动还原为 App-v 4.6。</span><span class="sxs-lookup"><span data-stu-id="564ee-114">If you do not need the App-V 5.1 package anymore, you can unpublish the App-V 5.1 package and the extension points will automatically revert to App-V 4.6.</span></span>



~~~
**Got a suggestion for App-V**? Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization). **Got an App-V issue?** Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).
~~~

## <span data-ttu-id="564ee-115">相关主题</span><span class="sxs-lookup"><span data-stu-id="564ee-115">Related topics</span></span>


[<span data-ttu-id="564ee-116">App-V 5.1 的操作</span><span class="sxs-lookup"><span data-stu-id="564ee-116">Operations for App-V 5.1</span></span>](operations-for-app-v-51.md)









