---
title: 如何为特定计算机上的所有用户将 App-V 5.0 程序包中的扩展点还原到 App-V 4.6 程序包
description: 如何为特定计算机上的所有用户将 App-V 5.0 程序包中的扩展点还原到 App-V 4.6 程序包
ms.assetid: 2a43ca1b-6847-4dd1-ade2-336ac4ac6af0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/21/2016
ms.openlocfilehash: 62542e5cd0b9dcb55f6e8f3db4d4f43c011a2839
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798368"
---
# <span data-ttu-id="d3ff6-103">如何为特定计算机上的所有用户将 App-V 5.0 程序包中的扩展点还原到 App-V 4.6 程序包</span><span class="sxs-lookup"><span data-stu-id="d3ff6-103">How to Revert Extension Points from an App-V 5.0 Package to an App-V 4.6 Package For All Users on a Specific Computer</span></span>

<span data-ttu-id="d3ff6-104">*注意：*\* App-V 4.6 已退出主流支持。</span><span class="sxs-lookup"><span data-stu-id="d3ff6-104">*Note:*\* App-V 4.6 has exited Mainstream support.</span></span> <span data-ttu-id="d3ff6-105">以下示例假设已安装了 App-v 4.6 SP3 客户端。</span><span class="sxs-lookup"><span data-stu-id="d3ff6-105">The following assumes that the App-V 4.6 SP3 client is already installed.</span></span>

<span data-ttu-id="d3ff6-106">使用以下过程，使用部署配置文件将应用程序 V 5.0 程序包中的扩展点还原到 app-v 4.6 文件格式。</span><span class="sxs-lookup"><span data-stu-id="d3ff6-106">Use the following procedure to revert extension points from an App-V 5.0 package to the App-V 4.6 file format using the deployment configuration file.</span></span>

**<span data-ttu-id="d3ff6-107">还原程序包</span><span class="sxs-lookup"><span data-stu-id="d3ff6-107">To revert a package</span></span>**

1.  <span data-ttu-id="d3ff6-108">确保将 app-v 4.6 程序包发布给用户，但 FTAs 和快捷方式已由 app-v 5.0 程序包（使用以下迁移方法）使用，[如何将应用程序 v 4.6 程序包中的扩展点迁移到特定计算机上所有用户的已转换的 app-v 5.0 程序包](how-to-migrate-extension-points-from-an-app-v-46-package-to-a-converted-app-v-50-package-for-all-users-on-a-specific-computer.md)。</span><span class="sxs-lookup"><span data-stu-id="d3ff6-108">Ensure that App-V 4.6 package is published to the users but the FTAs and shortcuts have been assumed by App-V 5.0 package using the following migration method, [How to Migrate Extension Points From an App-V 4.6 Package to a Converted App-V 5.0 Package for All Users on a Specific Computer](how-to-migrate-extension-points-from-an-app-v-46-package-to-a-converted-app-v-50-package-for-all-users-on-a-specific-computer.md).</span></span>

    <span data-ttu-id="d3ff6-109">在已转换程序包的部署配置文件的 " **userConfiguration** " 部分中，若要设置策略，请对**userConfiguration**部分进行以下更新： \*\*ManagingAuthority TakeoverExtensionPointsFrom46 = "FALSE" PackageName = &lt; 程序包 ID &gt; \*\*</span><span class="sxs-lookup"><span data-stu-id="d3ff6-109">In the **userConfiguration** section of the deployment configuration file for the converted package, to set the policy, make the following update to the **userConfiguration** section: **ManagingAuthority TakeoverExtensionPointsFrom46="false" PackageName=&lt;Package ID&gt;**</span></span>

2.  <span data-ttu-id="d3ff6-110">从提升的命令提示符处，键入：</span><span class="sxs-lookup"><span data-stu-id="d3ff6-110">From an elevated command prompt, type:</span></span>

    <span data-ttu-id="d3ff6-111">PS &gt; **Set-AppvClientPackage $Pkg-DynamicDeploymentConfiguration** &lt; 到部署配置文件的路径&gt;</span><span class="sxs-lookup"><span data-stu-id="d3ff6-111">PS&gt;**Set-AppvClientPackage $pkg –DynamicDeploymentConfiguration** &lt;path to deployment configuration file&gt;</span></span>

    <span data-ttu-id="d3ff6-112">PS &gt; **发布-AppVClientPackage $Pkg-DynamicUserConfigurationType useDeploymentConfiguration**</span><span class="sxs-lookup"><span data-stu-id="d3ff6-112">PS&gt;**Publish-AppVClientPackage $pkg –DynamicUserConfigurationType useDeploymentConfiguration**</span></span>

3.  <span data-ttu-id="d3ff6-113">执行发布刷新，或等待适用于 app-v 4.6 SP2 程序包的下一次计划发布刷新。</span><span class="sxs-lookup"><span data-stu-id="d3ff6-113">Perform a publishing refresh, or wait for the next scheduled publishing refresh for the App-V 4.6 SP2 package.</span></span>

    <span data-ttu-id="d3ff6-114">使用 FTAs 或快捷方式打开应用程序。</span><span class="sxs-lookup"><span data-stu-id="d3ff6-114">Open the application using FTAs or shortcuts.</span></span> <span data-ttu-id="d3ff6-115">应用程序现在应使用 App-v 4.6 打开。</span><span class="sxs-lookup"><span data-stu-id="d3ff6-115">The Application should now open using App-V 4.6.</span></span>

    **<span data-ttu-id="d3ff6-116">注意</span><span class="sxs-lookup"><span data-stu-id="d3ff6-116">Note</span></span>**  
    <span data-ttu-id="d3ff6-117">如果您不再需要 app-v 5.0 程序包，则可以取消发布 app-v 5.0 程序包，扩展点将自动还原为 App-v 4.6。</span><span class="sxs-lookup"><span data-stu-id="d3ff6-117">If you do not need the App-V 5.0 package anymore, you can unpublish the App-V 5.0 package and the extension points will automatically revert to App-V 4.6.</span></span>



~~~
**Got a suggestion for App-V**? Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization). **Got an App-V issue?** Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).
~~~

## <span data-ttu-id="d3ff6-118">相关主题</span><span class="sxs-lookup"><span data-stu-id="d3ff6-118">Related topics</span></span>


[<span data-ttu-id="d3ff6-119">App-V 5.0 的操作</span><span class="sxs-lookup"><span data-stu-id="d3ff6-119">Operations for App-V 5.0</span></span>](operations-for-app-v-50.md)









