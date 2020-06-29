---
title: App-V 5.0 SP2 发行说明
description: App-V 5.0 SP2 发行说明
author: dansimp
ms.assetid: fe73139d-240c-4ed5-8e59-6ae76ee8e80c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 5e885e67023d0e5c1e36aeb340933c64ae92610e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798268"
---
# <span data-ttu-id="c7371-103">App-V 5.0 SP2 发行说明</span><span class="sxs-lookup"><span data-stu-id="c7371-103">Release Notes for App-V 5.0 SP2</span></span>


**<span data-ttu-id="c7371-104">若要在这些发行说明中搜索特定问题，请按 CTRL + F。</span><span class="sxs-lookup"><span data-stu-id="c7371-104">To search for a specific issue in these release notes, press CTRL+F.</span></span>**

<span data-ttu-id="c7371-105">安装 App-v 5.0 SP2 之前，请仔细阅读这些发行说明。</span><span class="sxs-lookup"><span data-stu-id="c7371-105">Read these release notes thoroughly before you install App-V 5.0 SP2.</span></span>

<span data-ttu-id="c7371-106">这些发行说明包含成功安装 app-v 5.0 SP2 所需的信息。</span><span class="sxs-lookup"><span data-stu-id="c7371-106">These release notes contain information that is required to successfully install App-V 5.0 SP2.</span></span> <span data-ttu-id="c7371-107">发行说明还包含产品文档中不可用的信息。</span><span class="sxs-lookup"><span data-stu-id="c7371-107">The release notes also contain information that is not available in the product documentation.</span></span> <span data-ttu-id="c7371-108">如果这些发行说明和其他 App-v 5.0 文档之间存在差异，则应将最新更改视为权威。</span><span class="sxs-lookup"><span data-stu-id="c7371-108">If there are differences between these release notes and other App-V 5.0 documentation, the latest change should be considered authoritative.</span></span> <span data-ttu-id="c7371-109">这些发行说明取代了本产品附带的内容。</span><span class="sxs-lookup"><span data-stu-id="c7371-109">These release notes supersede the content that is included with this product.</span></span>

## <span data-ttu-id="c7371-110">关于产品文档</span><span class="sxs-lookup"><span data-stu-id="c7371-110">About the Product Documentation</span></span>


<span data-ttu-id="c7371-111">有关 App-V 5.0 文档的详细信息，请参阅 Microsoft TechNet 上的 app-v 5.0 主页。</span><span class="sxs-lookup"><span data-stu-id="c7371-111">For information about App-V 5.0 documentation, see the App-V 5.0 home page on Microsoft TechNet.</span></span>

## <span data-ttu-id="c7371-112">提供反馈</span><span class="sxs-lookup"><span data-stu-id="c7371-112">Provide Feedback</span></span>


<span data-ttu-id="c7371-113">我们对 app-v 5.0 的反馈感兴趣。</span><span class="sxs-lookup"><span data-stu-id="c7371-113">We are interested in your feedback on App-V 5.0.</span></span> <span data-ttu-id="c7371-114">您可以向发送反馈 <mdopdocs@microsoft.com> 。</span><span class="sxs-lookup"><span data-stu-id="c7371-114">You can send your feedback to <mdopdocs@microsoft.com>.</span></span>

<span data-ttu-id="c7371-115">**注意** 此电子邮件地址不是支持频道，但你的反馈将帮助我们为我们的文档和产品发布计划未来的更改。</span><span class="sxs-lookup"><span data-stu-id="c7371-115">**Note** This email address is not a support channel, but your feedback will help us to plan for future changes in our documentation and product releases.</span></span>

 

<span data-ttu-id="c7371-116">有关 MDOP 和其他学习资源的最新信息，请参阅[Mdop 信息体验](https://go.microsoft.com/fwlink/p/?LinkId=236032)页面。</span><span class="sxs-lookup"><span data-stu-id="c7371-116">For the latest information about MDOP and additional learning resources, see the [MDOP Information Experience](https://go.microsoft.com/fwlink/p/?LinkId=236032) page.</span></span>

<span data-ttu-id="c7371-117">有关新更新或提供反馈的详细信息，请在[Facebook](https://go.microsoft.com/fwlink/p/?LinkId=242445)或[Twitter](https://go.microsoft.com/fwlink/p/?LinkId=242447)上关注我们。</span><span class="sxs-lookup"><span data-stu-id="c7371-117">For more information about new updates or to provide feedback, follow us on [Facebook](https://go.microsoft.com/fwlink/p/?LinkId=242445) or [Twitter](https://go.microsoft.com/fwlink/p/?LinkId=242447).</span></span>

## <span data-ttu-id="c7371-118">适用于应用程序虚拟化 5.0 SP2 的修补程序包4的已知问题</span><span class="sxs-lookup"><span data-stu-id="c7371-118">Known Issues with Hotfix Package 4 for Application Virtualization 5.0 SP2</span></span>


### <span data-ttu-id="c7371-119">卸载应用程序虚拟化 5.0 SP2 的修补程序包4后，程序包停止工作</span><span class="sxs-lookup"><span data-stu-id="c7371-119">Packages stop working after you uninstall Hotfix Package 4 for Application Virtualization 5.0 SP2</span></span>

<span data-ttu-id="c7371-120">当应用程序虚拟化 5.0 sp2 的修补程序包4已被删除时，应用于应用程序虚拟化 SP2 的修补程序包4时，发布的程序包将停止5.0 工作。</span><span class="sxs-lookup"><span data-stu-id="c7371-120">Packages published when Hotfix Package 4 for Application Virtualization 5.0 SP2 is applied stop working when Hotfix Package 4 for Application Virtualization 5.0 SP2 is removed.</span></span>

<span data-ttu-id="c7371-121">规避</span><span class="sxs-lookup"><span data-stu-id="c7371-121">WORKAROUND:</span></span>

<span data-ttu-id="c7371-122">如果存在以下文件夹，则必须将其删除：</span><span class="sxs-lookup"><span data-stu-id="c7371-122">If the following folder exists, then you must delete it:</span></span>

<span data-ttu-id="c7371-123">**% localappdata%**  \\ **Microsoft**  \\ **AppV**  \\ **客户端**  \\ **VFS**  \\ 已发布的每个程序包的\*\* &lt; 程序包 ID &gt; \*\* 。</span><span class="sxs-lookup"><span data-stu-id="c7371-123">**%localappdata%** \\ **Microsoft** \\ **AppV** \\ **Client** \\ **VFS** \\ **&lt;package ID&gt;** for each package that was published.</span></span>

<span data-ttu-id="c7371-124">**注意** 您必须具有更高的权限才能删除此文件夹。</span><span class="sxs-lookup"><span data-stu-id="c7371-124">**Note** You must have elevated privileges to delete this folder.</span></span>

 

<span data-ttu-id="c7371-125">若要对计算机上的每个用户帐户以及针对应用程序虚拟化 5.0 SP2 安装了修补程序包4后发布的每个程序包 id 使用脚本，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c7371-125">To use a script, for each user account on the computer and for each package id that was published after installing Hotfix Package 4 for Application Virtualization 5.0 SP2:</span></span>

`Rd /s /q “%systemdrive%\users\[UserName]\AppData\Local\Microsoft\AppV\Client\VFS\[Package ID]`

-   <span data-ttu-id="c7371-126">即使在上一节的目录中删除文件夹后，这些快捷方式仍将保留在用户会话中，这样您就可以单击快捷方式来再次运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="c7371-126">The shortcuts will remain with the user sessions even after deleting the folder from the directory in the previous section, so you can click on the shortcut to run the application again.</span></span> <span data-ttu-id="c7371-127">无需重新发布应用程序。</span><span class="sxs-lookup"><span data-stu-id="c7371-127">There is no need to re-publish the application.</span></span>

-   <span data-ttu-id="c7371-128">对于用户发布的打包和全局发布的程序包（例如 Microsoft Office2013），会出现此问题。</span><span class="sxs-lookup"><span data-stu-id="c7371-128">This issue happens for both user published packaged and globally published packages for example, Microsoft Office2013.</span></span> <span data-ttu-id="c7371-129">必须删除这两种类型的程序包的文件夹。</span><span class="sxs-lookup"><span data-stu-id="c7371-129">The folder must be deleted for both types of packages.</span></span>

-   <span data-ttu-id="c7371-130">无需在漫游应用数据（**% appdata%**）中删除 VFS 文件夹。</span><span class="sxs-lookup"><span data-stu-id="c7371-130">You do not need to delete the VFS folder in the Roaming app data (**%appdata%**).</span></span> <span data-ttu-id="c7371-131">只有 **% localappdata%** 必须删除。</span><span class="sxs-lookup"><span data-stu-id="c7371-131">Only the **%localappdata%** must be deleted.</span></span>

### <span data-ttu-id="c7371-132">Microsoft Office 集成指向错误的文件系统位置</span><span class="sxs-lookup"><span data-stu-id="c7371-132">Microsoft Office integration points to wrong file system location</span></span>

<span data-ttu-id="c7371-133">Microsoft Office 集成指向错误的文件系统位置（Groove.exe 错误消息）。</span><span class="sxs-lookup"><span data-stu-id="c7371-133">Microsoft Office integration points to wrong file system location (Groove.exe error message).</span></span>

<span data-ttu-id="c7371-134">规避</span><span class="sxs-lookup"><span data-stu-id="c7371-134">WORKAROUND:</span></span>

<span data-ttu-id="c7371-135">使用以下方法之一：</span><span class="sxs-lookup"><span data-stu-id="c7371-135">Use one of the following methods:</span></span>

1.  <span data-ttu-id="c7371-136">升级后，删除 "启动" 文件夹中的快捷方式。</span><span class="sxs-lookup"><span data-stu-id="c7371-136">Delete the shortcut in the start-up folder after upgrade.</span></span>

2.  <span data-ttu-id="c7371-137">使用脚本更改启动文件夹中的快捷方式。</span><span class="sxs-lookup"><span data-stu-id="c7371-137">Change the shortcut in the start-up folder using a script.</span></span>

3.  <span data-ttu-id="c7371-138">使用部署配置文件指定指向集成根的快捷方式目标。</span><span class="sxs-lookup"><span data-stu-id="c7371-138">Use the deployment configuration file to specify the shortcut target to the integration root.</span></span>

### <a href="" id="-------------hotfix-package-4-for-application-virtualization-5-0-sp2-installer-can-take-a-long-time"></a> <span data-ttu-id="c7371-139">应用程序虚拟化5.0 的修补程序包 4 SP2 安装程序可能需要花费很长时间</span><span class="sxs-lookup"><span data-stu-id="c7371-139">Hotfix Package 4 for Application Virtualization 5.0 SP2 installer can take a long time</span></span>

<span data-ttu-id="c7371-140">应用程序虚拟化 5.0 SP2 安装程序的修补程序包4可能会花费很长时间，具体取决于在现有程序包缓存中存储的文件数。</span><span class="sxs-lookup"><span data-stu-id="c7371-140">The Hotfix Package 4 for Application Virtualization 5.0 SP2 installer can potentially take a long time depending on how many files are stored in the existing package cache.</span></span>

<span data-ttu-id="c7371-141">在修补程序包4中更新关联的程序包安全描述符应用程序虚拟化 5.0 SP2 安装对安装所需时间有重大影响。</span><span class="sxs-lookup"><span data-stu-id="c7371-141">Updating associated package security descriptors during the Hotfix Package 4 for Application Virtualization 5.0 SP2 installation has a significant impact on how long it takes the installation will take.</span></span> <span data-ttu-id="c7371-142">以前，安装安装是持续时间的标准。</span><span class="sxs-lookup"><span data-stu-id="c7371-142">Previously, the installation install was standard in duration.</span></span> <span data-ttu-id="c7371-143">但是，它现在取决于在程序包缓存中暂存的文件数。</span><span class="sxs-lookup"><span data-stu-id="c7371-143">However, it now depends on how many files you have staged in the package cache.</span></span>

<span data-ttu-id="c7371-144">解决方法：无</span><span class="sxs-lookup"><span data-stu-id="c7371-144">WORKAROUND: None</span></span>

### <span data-ttu-id="c7371-145">如果正在使用 JIT 程序包，则卸载应用程序虚拟5.0 化修补程序程序包4的修补程序包将会失败</span><span class="sxs-lookup"><span data-stu-id="c7371-145">Uninstalling Hotfix Package 4 for Application Virtualization 5.0 SP2 fails if JIT-V package is in use</span></span>

<span data-ttu-id="c7371-146">如果安装了应用程序虚拟化 5.0 SP2 的修补程序包4，然后尝试在使用实时虚拟化（JIT V）时卸载修复程序，则如果满足以下所有条件，则操作将失败：</span><span class="sxs-lookup"><span data-stu-id="c7371-146">If you install Hotfix Package 4 for Application Virtualization 5.0 SP2 and then try to uninstall the hotfix when just-in-time virtualization (JIT-V) is being used, the operation will fail if all of the following conditions are true:</span></span>

-   <span data-ttu-id="c7371-147">通过使用 Windows Installer 文件（.msi）安装，然后使用 Microsoft 安装程序修补程序文件（.msp）应用更新。</span><span class="sxs-lookup"><span data-stu-id="c7371-147">You installed by using a Windows Installer file (.msi), and then you apply updates by using a Microsoft Installer Patch File (.msp).</span></span>

-   <span data-ttu-id="c7371-148">您尝试使用 "控制面板" 中的 "添加或删除程序" 项卸载更新。</span><span class="sxs-lookup"><span data-stu-id="c7371-148">You try to uninstall an update by using the Add or Remove Programs item in Control Panel.</span></span>

-   <span data-ttu-id="c7371-149">计算机上正在运行支持 JIT 的程序包。</span><span class="sxs-lookup"><span data-stu-id="c7371-149">A JIT-V-enabled package is running on the computer.</span></span>

<span data-ttu-id="c7371-150">解决方法：完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="c7371-150">WORKAROUND: Complete the following steps:</span></span>

1.  <span data-ttu-id="c7371-151">打开 Windows PowerShell 并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="c7371-151">Open Windows PowerShell and run the following commands:</span></span>

    -   **<span data-ttu-id="c7371-152">导入-模块 appvclient</span><span class="sxs-lookup"><span data-stu-id="c7371-152">Import-module appvclient</span></span>**

    -   **<span data-ttu-id="c7371-153">AppvClientPackage |停止-AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="c7371-153">Get-AppvClientPackage | Stop-AppvClientPackage</span></span>**

2.  <span data-ttu-id="c7371-154">使用 "添加或删除程序" 卸载更新。</span><span class="sxs-lookup"><span data-stu-id="c7371-154">Uninstall the update using Add or Remove Programs.</span></span>

## <span data-ttu-id="c7371-155">有关 app-v 5.0 SP2 的已知问题</span><span class="sxs-lookup"><span data-stu-id="c7371-155">Known Issues with App-V 5.0 SP2</span></span>


### <a href="" id="bkmk-folderredirection"></a><span data-ttu-id="c7371-156">App-v 客户端文件夹重定向有时无法将文件从% AppData% 移动到% LocalAppData%</span><span class="sxs-lookup"><span data-stu-id="c7371-156">App-V client folder redirection sometimes fails to move files from %AppData% to %LocalAppData%</span></span>

<span data-ttu-id="c7371-157">当% AppData% 是已为文件夹重定向配置的共享网络文件夹时，最终用户对 AppData （漫游）所做的更改可能会在用户切换计算机时丢失，或者当其本地 AppData 在注销时被清除，然后重新登录。</span><span class="sxs-lookup"><span data-stu-id="c7371-157">When %AppData% is a shared network folder that you have configured for folder redirection, the changes that end users make to AppData (Roaming) can be lost when they switch computers or when their local AppData is cleared when they log off and then log back on.</span></span> <span data-ttu-id="c7371-158">出现此错误的原因是注册表项（AppDataTime），它指示上次已知上载的操作与本地缓存的 AppData 不同步。</span><span class="sxs-lookup"><span data-stu-id="c7371-158">This error occurs because the registry key (AppDataTime), which indicates the last known upload, gets out of synchronization with the local cached AppData.</span></span>

<span data-ttu-id="c7371-159">解决方法：当最终用户登录或注销时，手动删除每个相关程序包的以下注册表项：</span><span class="sxs-lookup"><span data-stu-id="c7371-159">WORKAROUND: Manually delete the following registry key for each relevant package when an end user logs on or off:</span></span>

``` syntax
HKCU\Software\Microsoft\AppV\Client\Packages\<PACKAGE_GUID>\AppDataTime
```

<span data-ttu-id="c7371-160">当最终用户在登录后首次启动应用程序包中的应用程序时，App-v 会强制下载压缩% AppData%，即使% LocalAppData% 已经是最新的。</span><span class="sxs-lookup"><span data-stu-id="c7371-160">The first time that end users start an application in the package after they log in, App-V forces a download of the zipped %AppData%, even if %LocalAppData% is already up to date.</span></span>

### <a href="" id="-------------app-v-5-0-service-pack-2--app-v-5-0-sp2--does-not-include-a-new-version-of-the-app-v-server"></a> <span data-ttu-id="c7371-161">App-v 5.0 Service Pack 2 （App-v 5.0 SP2）不包含新版本的 App-v Server</span><span class="sxs-lookup"><span data-stu-id="c7371-161">App-V 5.0 Service Pack 2 (App-V 5.0 SP2) does not include a new version of the App-V Server</span></span>

<span data-ttu-id="c7371-162">App-v 5.0 SP2 不包含新版本的 App-v Server。</span><span class="sxs-lookup"><span data-stu-id="c7371-162">App-V 5.0SP2 does not include a new version of the App-V Server.</span></span> <span data-ttu-id="c7371-163">如果你在你的环境中部署运行 Windows 8.1 的 app-v 5.0 SP2 客户端并计划使用 App-v 基础结构管理客户端，则必须安装[适用于 Microsoft Application Virtualization 5.0 Service Pack 1 的修补程序包 2](https://go.microsoft.com/fwlink/?LinkId=386634)。</span><span class="sxs-lookup"><span data-stu-id="c7371-163">If you deploy App-V 5.0 SP2 clients running Windows 8.1 in your environment and plan to manage the clients using the App-V infrastructure, you must install [Hotfix Package 2 for Microsoft Application Virtualization 5.0 Service Pack 1](https://go.microsoft.com/fwlink/?LinkId=386634).</span></span> <span data-ttu-id="c7371-164">(https://go.microsoft.com/fwlink/?LinkId=386634)</span><span class="sxs-lookup"><span data-stu-id="c7371-164">(https://go.microsoft.com/fwlink/?LinkId=386634)</span></span>

<span data-ttu-id="c7371-165">如果你正在运行和使用以下任一方法管理 app-v 5.0 SP2 客户端，则不需要客户端更新：</span><span class="sxs-lookup"><span data-stu-id="c7371-165">If you are running and managing App-V 5.0 SP2 clients using any of the following methods no client update is required:</span></span>

-   <span data-ttu-id="c7371-166">独立模式。</span><span class="sxs-lookup"><span data-stu-id="c7371-166">Standalone mode.</span></span>

-   <span data-ttu-id="c7371-167">Configuration Manager。</span><span class="sxs-lookup"><span data-stu-id="c7371-167">Configuration Manager.</span></span>

-   <span data-ttu-id="c7371-168">第三方 ESD。</span><span class="sxs-lookup"><span data-stu-id="c7371-168">Third party ESD.</span></span>

<span data-ttu-id="c7371-169">App-v 5.0 SP2 客户端与 Windows 8.1 完全兼容</span><span class="sxs-lookup"><span data-stu-id="c7371-169">The App-V 5.0 SP2 client is fully compatible with Windows 8.1</span></span>

<span data-ttu-id="c7371-170">解决方法：无。</span><span class="sxs-lookup"><span data-stu-id="c7371-170">WORKAROUND: None.</span></span>

## <span data-ttu-id="c7371-171">发行说明版权信息</span><span class="sxs-lookup"><span data-stu-id="c7371-171">Release Notes Copyright Information</span></span>


<span data-ttu-id="c7371-172">Microsoft、Active Directory、ActiveX、Bing、Excel、Silverlight、SQLServer、Windows、MicrosoftIntune 和 WindowsPowerShell 是 Microsoft 公司组的商标。</span><span class="sxs-lookup"><span data-stu-id="c7371-172">Microsoft, Active Directory, ActiveX, Bing, Excel, Silverlight, SQLServer, Windows, MicrosoftIntune, and WindowsPowerShell are trademarks of the Microsoft group of companies.</span></span> <span data-ttu-id="c7371-173">所有其他商标的所有权属于其各自所有者。</span><span class="sxs-lookup"><span data-stu-id="c7371-173">All other trademarks are property of their respective owners.</span></span>








## <span data-ttu-id="c7371-174">相关主题</span><span class="sxs-lookup"><span data-stu-id="c7371-174">Related topics</span></span>


[<span data-ttu-id="c7371-175">关于 App-V 5.0 SP2</span><span class="sxs-lookup"><span data-stu-id="c7371-175">About App-V 5.0 SP2</span></span>](about-app-v-50-sp2.md)

 

 





