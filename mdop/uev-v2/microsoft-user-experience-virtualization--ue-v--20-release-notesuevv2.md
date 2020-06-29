---
title: Microsoft 用户体验虚拟化 (UE-V) 2.0 发行说明
description: Microsoft 用户体验虚拟化 (UE-V) 2.0 发行说明
author: dansimp
ms.assetid: 5ef66cd1-ba2b-4383-9f45-e7cde41f1ba1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: ad3deffa5cd567a70711e5447197e630f04ea254
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803737"
---
# <span data-ttu-id="aa372-103">Microsoft 用户体验虚拟化 (UE-V) 2.0 发行说明</span><span class="sxs-lookup"><span data-stu-id="aa372-103">Microsoft User Experience Virtualization (UE-V) 2.0 Release Notes</span></span>


<span data-ttu-id="aa372-104">若要搜索 Microsoft 用户体验虚拟化（UE-V）2.0 发行说明，请按 Ctrl + F。</span><span class="sxs-lookup"><span data-stu-id="aa372-104">To search Microsoft User Experience Virtualization (UE-V) 2.0 release notes, press Ctrl+F.</span></span>

<span data-ttu-id="aa372-105">在安装 UE-V 之前，应仔细阅读这些发行说明。</span><span class="sxs-lookup"><span data-stu-id="aa372-105">You should read these release notes thoroughly before you install UE-V.</span></span> <span data-ttu-id="aa372-106">发行说明包含成功安装用户体验虚拟化所需的信息，并包含产品文档中不可用的其他信息。</span><span class="sxs-lookup"><span data-stu-id="aa372-106">The release notes contain information that is required to successfully install User Experience Virtualization, and contain additional information that is not available in the product documentation.</span></span> <span data-ttu-id="aa372-107">如果这些发行说明和其他 UE-V 文档之间存在差异，则应将最新更改视为权威。</span><span class="sxs-lookup"><span data-stu-id="aa372-107">If there are differences between these release notes and other UE-V documentation, the latest change should be considered authoritative.</span></span> <span data-ttu-id="aa372-108">这些发行说明取代了本产品附带的内容。</span><span class="sxs-lookup"><span data-stu-id="aa372-108">These release notes supersede the content that is included with this product.</span></span>

## <span data-ttu-id="aa372-109">提供反馈</span><span class="sxs-lookup"><span data-stu-id="aa372-109">Providing feedback</span></span>


<span data-ttu-id="aa372-110">通过向我们提供反馈和评论，告诉我们您对 MDOP 文档的看法。</span><span class="sxs-lookup"><span data-stu-id="aa372-110">Tell us what you think about our documentation for MDOP by giving us your feedback and comments.</span></span> <span data-ttu-id="aa372-111">将文档反馈发送到[mdopdocs@microsoft.com](mailto:mdopdocs@microsoft.com?subject=UE-V%20Documentation)。</span><span class="sxs-lookup"><span data-stu-id="aa372-111">Send your documentation feedback to [mdopdocs@microsoft.com](mailto:mdopdocs@microsoft.com?subject=UE-V%20Documentation).</span></span>

## <span data-ttu-id="aa372-112">UE-V 已知问题</span><span class="sxs-lookup"><span data-stu-id="aa372-112">UE-V known issues</span></span>


<span data-ttu-id="aa372-113">本部分包含适用于用户体验虚拟化的发行说明。</span><span class="sxs-lookup"><span data-stu-id="aa372-113">This section contains release notes for User Experience Virtualization.</span></span>

### <span data-ttu-id="aa372-114">注册表设置不在同一台计算机上的 app-v 和本机应用程序之间同步</span><span class="sxs-lookup"><span data-stu-id="aa372-114">Registry settings do not synchronize between App-V and native applications on the same computer</span></span>

<span data-ttu-id="aa372-115">当计算机具有通过应用程序虚拟化（app-v）和本地使用 Windows Installer （.msi）文件安装的应用程序时，基于注册表的设置不会在技术之间同步。</span><span class="sxs-lookup"><span data-stu-id="aa372-115">When a computer has an application that is installed through both Application Virtualization (App-V) and a locally with a Windows Installer (.msi) file, the registry-based settings do not synchronize between the technologies.</span></span>

<span data-ttu-id="aa372-116">**解决方法：** 若要解决此问题，请通过选择两种技术之一来运行应用程序，但不能同时选择二者。</span><span class="sxs-lookup"><span data-stu-id="aa372-116">**WORKAROUND:** To resolve this problem, run the application by selecting one of the two technologies, but not both.</span></span>

### <a href="" id="settings-do-not-synchronization-when-network-share-is-outside-user-s-domain"></a><span data-ttu-id="aa372-117">当网络共享位于用户域之外时，设置不同步</span><span class="sxs-lookup"><span data-stu-id="aa372-117">Settings do not synchronization when network share is outside user’s domain</span></span>

<span data-ttu-id="aa372-118">当 Windows®8尝试运行操作系统设置同步时，同步失败，并出现以下错误消息：**提升：： filesystem：：存在：：错误的用户名或密码**。</span><span class="sxs-lookup"><span data-stu-id="aa372-118">When Windows® 8 attempts operating system settings synchronization, the synchronization fails with the following error message: **boost::filesystem::exists::Incorrect user name or password**.</span></span> <span data-ttu-id="aa372-119">此错误可指示网络共享位于用户域或与该域有信任关系的域之外。</span><span class="sxs-lookup"><span data-stu-id="aa372-119">This error can indicate that the network share is outside the user’s domain or a domain with a trust relationship to that domain.</span></span> <span data-ttu-id="aa372-120">若要检查操作日志事件，请打开**事件查看器**并导航到**应用程序和服务记录**  /  **Microsoft**  /  **用户体验虚拟化**  /  **日志记录**  /  **操作**。</span><span class="sxs-lookup"><span data-stu-id="aa372-120">To check for operational log events, open the **Event Viewer** and navigate to **Applications and Services Logs** / **Microsoft** / **User Experience Virtualization** / **Logging** / **Operational**.</span></span> <span data-ttu-id="aa372-121">用于 UE-V 设置的网络共享的存储位置应位于与用户或用户域的受信任域相同的 Active Directory 域中。</span><span class="sxs-lookup"><span data-stu-id="aa372-121">Network shares that are used for UE-V settings storage locations should reside in the same Active Directory domain as the user or a trusted domain of the user’s domain.</span></span>

<span data-ttu-id="aa372-122">**解决方法：** 使用与用户相同的 Active Directory 域中的网络共享。</span><span class="sxs-lookup"><span data-stu-id="aa372-122">**WORKAROUND:** Use network shares from the same Active Directory domain as the user.</span></span>

### <span data-ttu-id="aa372-123">安装了 Office 2010 和 Office 2013 时不可预测的结果</span><span class="sxs-lookup"><span data-stu-id="aa372-123">Unpredictable results with both Office 2010 and Office 2013 installed</span></span>

<span data-ttu-id="aa372-124">如果用户安装了 Office 2010 和 Office 2013，则两个版本的 Office 之间的任何常见设置都通过 UE-V 漫游。</span><span class="sxs-lookup"><span data-stu-id="aa372-124">When a user has both Office 2010 and Office 2013 installed, any common settings between the two versions of Office are roamed by UE-V.</span></span> <span data-ttu-id="aa372-125">这可能会导致 Office 2010 程序包大小相当大或导致与2013的不可预知的冲突，尤其是在使用 Office 365 时。</span><span class="sxs-lookup"><span data-stu-id="aa372-125">This could cause the Office 2010 package size to be quite large or result in unpredictable conflicts with 2013, particularly if Office 365 is used.</span></span>

<span data-ttu-id="aa372-126">**解决方法：** 仅安装一个版本的 Office，或限制由 UE-V 同步的设置。</span><span class="sxs-lookup"><span data-stu-id="aa372-126">**WORKAROUND:** Install only one version of Office or limit which settings are synchronized by UE-V.</span></span>

### <span data-ttu-id="aa372-127">卸载并重新安装 Windows 8 应用会将设置还原为初始状态</span><span class="sxs-lookup"><span data-stu-id="aa372-127">Uninstall and re-install of Windows 8 app reverts settings to initial state</span></span>

<span data-ttu-id="aa372-128">使用 UE-V 设置同步处理 Windows 8 应用时，如果用户卸载应用，然后重新安装该应用，则应用的设置将还原为其默认值。</span><span class="sxs-lookup"><span data-stu-id="aa372-128">While using UE-V settings synchronization for a Windows 8 app, if the user uninstalls the app and then reinstalls the app, the app’s settings revert to their default values.</span></span><span data-ttu-id="aa372-129">发生这种情况是因为卸载删除了应用设置的本地（缓存）副本，但不会删除本地 UE-V 设置程序包。</span><span class="sxs-lookup"><span data-stu-id="aa372-129"> This happens because the uninstall removes the local (cached) copy of the app’s settings but does not remove the local UE-V settings package.</span></span><span data-ttu-id="aa372-130">当应用重新安装并启动时，UE-V 收集重置为应用默认设置的应用设置，然后将默认设置上载到中央存储位置。</span><span class="sxs-lookup"><span data-stu-id="aa372-130"> When the app is reinstalled and launched, UE-V gather the app settings that were reset to the app defaults and then uploads the default settings to the central storage location.</span></span><span data-ttu-id="aa372-131">然后，运行应用的其他计算机将下载默认设置。</span><span class="sxs-lookup"><span data-stu-id="aa372-131"> Other computers running the app then download the default settings.</span></span><span data-ttu-id="aa372-132">此行为与桌面应用程序的行为相同。</span><span class="sxs-lookup"><span data-stu-id="aa372-132"> This behavior is identical to the behavior of desktop applications.</span></span>

<span data-ttu-id="aa372-133">**解决方法：** 尚.</span><span class="sxs-lookup"><span data-stu-id="aa372-133">**WORKAROUND:** None.</span></span>

### <span data-ttu-id="aa372-134">Outlook 2010 的电子邮件签名漫游</span><span class="sxs-lookup"><span data-stu-id="aa372-134">Email signature roaming for Outlook 2010</span></span>

<span data-ttu-id="aa372-135">UE-V 将在设备之间漫游 Outlook 2010 签名文件。</span><span class="sxs-lookup"><span data-stu-id="aa372-135">UE-V will roam the Outlook 2010 signature files between devices.</span></span> <span data-ttu-id="aa372-136">但是，不会同步新邮件和答复或转发的默认签名选项。</span><span class="sxs-lookup"><span data-stu-id="aa372-136">However, the default signature options for new messages and replies or forwards are not synchronized.</span></span> <span data-ttu-id="aa372-137">这两个设置存储在 Outlook 配置文件中，而 UE-V 不会漫游。</span><span class="sxs-lookup"><span data-stu-id="aa372-137">These two settings are stored in the Outlook profile, which UE-V does not roam.</span></span>

<span data-ttu-id="aa372-138">**解决方法：** 尚.</span><span class="sxs-lookup"><span data-stu-id="aa372-138">**WORKAROUND:** None.</span></span>

### <span data-ttu-id="aa372-139">UE-V 不支持32位和64位版本的 Microsoft Office 之间的漫游设置</span><span class="sxs-lookup"><span data-stu-id="aa372-139">UE-V does not support roaming settings between 32-bit and 64-bit versions of Microsoft Office</span></span>

<span data-ttu-id="aa372-140">我们建议你安装适用于新式计算机的64位版本的 Microsoft Office。</span><span class="sxs-lookup"><span data-stu-id="aa372-140">We recommend that you install the 64-bit version of Microsoft Office for modern computers.</span></span> <span data-ttu-id="aa372-141">若要确定所需的版本，请[单击此处](https://support.office.com/article/choose-between-the-64-bit-or-32-bit-version-of-office-2dee7807-8f95-4d0c-b5fe-6c6f49b8d261?ui=en-US&rs=en-US&ad=US#32or64Bit=Newer_Versions)。</span><span class="sxs-lookup"><span data-stu-id="aa372-141">To determine which version you need, [click here](https://support.office.com/article/choose-between-the-64-bit-or-32-bit-version-of-office-2dee7807-8f95-4d0c-b5fe-6c6f49b8d261?ui=en-US&rs=en-US&ad=US#32or64Bit=Newer_Versions).</span></span> <span data-ttu-id="aa372-142">UE-V 支持 Office 的相同体系结构版本之间的漫游设置。</span><span class="sxs-lookup"><span data-stu-id="aa372-142">UE-V supports roaming settings between identical architecture versions of Office.</span></span> <span data-ttu-id="aa372-143">例如，32位 Office 设置将在所有32位 Office 实例之间漫游。</span><span class="sxs-lookup"><span data-stu-id="aa372-143">For example, 32-bit Office settings will roam between all 32-bit Office instances.</span></span> <span data-ttu-id="aa372-144">UE-V 不支持32位和64位版本的 Office 之间的漫游设置。</span><span class="sxs-lookup"><span data-stu-id="aa372-144">UE-V does not support roaming settings between 32-bit and 64-bit versions of Office.</span></span>

<span data-ttu-id="aa372-145">**解决方法：** 尚</span><span class="sxs-lookup"><span data-stu-id="aa372-145">**WORKAROUND:** None</span></span>

### <a href="" id="msi-s-are-not-localized"></a><span data-ttu-id="aa372-146">MSI 未本地化</span><span class="sxs-lookup"><span data-stu-id="aa372-146">MSI’s are not localized</span></span>

<span data-ttu-id="aa372-147">UE-V 2.0 包括用于 UE-V Agent 和 UE-V 发生器的本地化安装程序。</span><span class="sxs-lookup"><span data-stu-id="aa372-147">UE-V 2.0 includes a localized setup program for both the UE-V Agent and UE-V generator.</span></span> <span data-ttu-id="aa372-148">这些 MSI 文件仍然可用，但用户界面已最小化，并且 MSI 仅以英语显示。</span><span class="sxs-lookup"><span data-stu-id="aa372-148">These MSI files are still available but the user interface is minimized and the MSI’s only display in English.</span></span> <span data-ttu-id="aa372-149">尽管文件是英语，安装程序也会在安装期间安装所有支持的语言。</span><span class="sxs-lookup"><span data-stu-id="aa372-149">Despite the file being in English, the setup program installs all supported languages during the installation.</span></span>

<span data-ttu-id="aa372-150">**解决方法：** 尚</span><span class="sxs-lookup"><span data-stu-id="aa372-150">**WORKAROUND:** None</span></span>

### <span data-ttu-id="aa372-151">与 Internet Explorer 9 收藏夹相关联的 Favicons 不漫游</span><span class="sxs-lookup"><span data-stu-id="aa372-151">Favicons that are associated with Internet Explorer 9 favorites do not roam</span></span>

<span data-ttu-id="aa372-152">与 Internet Explorer 9 常用联系人相关联的 favicons 不是由用户体验虚拟化漫游的，并且在新计算机上首次显示收藏时不会显示。</span><span class="sxs-lookup"><span data-stu-id="aa372-152">The favicons that are associated with Internet Explorer 9 favorites are not roamed by User Experience Virtualization and do not appear when the favorites first appear on a new computer.</span></span>

<span data-ttu-id="aa372-153">**解决方法：** 在 Internet Explorer 9 浏览器中使用并缓存书签后，Favicons 将显示相关联的常用联系人。</span><span class="sxs-lookup"><span data-stu-id="aa372-153">**WORKAROUND:** Favicons will appear with their associated favorites once the bookmark is used and cached in the Internet Explorer 9 browser.</span></span>

### <span data-ttu-id="aa372-154">文件设置路径存储在注册表中</span><span class="sxs-lookup"><span data-stu-id="aa372-154">File settings paths are stored in registry</span></span>

<span data-ttu-id="aa372-155">某些应用程序设置将其配置和设置文件的路径存储为注册表中的值。</span><span class="sxs-lookup"><span data-stu-id="aa372-155">Some application settings store the paths of their configuration and settings files as values in the registry.</span></span> <span data-ttu-id="aa372-156">当设置在计算机之间漫游时，必须同步在注册表中作为路径引用的文件。</span><span class="sxs-lookup"><span data-stu-id="aa372-156">The files that are referenced as paths in the registry must be synchronized when settings are roamed between computers.</span></span>

<span data-ttu-id="aa372-157">**解决方法：** 使用 "文件夹重定向" 或其他技术确保作为文件设置路径引用的所有文件都存在并放置在 "设置" 漫游的所有计算机上的相同位置。</span><span class="sxs-lookup"><span data-stu-id="aa372-157">**WORKAROUND:** Use folder redirection or some other technology to ensure that any files that are referenced as file settings paths are present and placed in the same location on all computers where settings roam.</span></span>

### <span data-ttu-id="aa372-158">较长设置存储路径可能会导致错误</span><span class="sxs-lookup"><span data-stu-id="aa372-158">Long Settings Storage Paths could cause an error</span></span>

<span data-ttu-id="aa372-159">使设置存储路径尽可能简短。</span><span class="sxs-lookup"><span data-stu-id="aa372-159">Keep settings storage paths as short as possible.</span></span> <span data-ttu-id="aa372-160">长路径可能会阻止分辨率或同步。</span><span class="sxs-lookup"><span data-stu-id="aa372-160">Long paths could prevent resolution or synchronization.</span></span> <span data-ttu-id="aa372-161">UE-V 使用设置存储路径作为存储设置的计算路径的一部分。</span><span class="sxs-lookup"><span data-stu-id="aa372-161">UE-V uses the Settings storage path as part of the calculated path to store settings.</span></span> <span data-ttu-id="aa372-162">该路径按以下方式计算：设置存储路径 + "settingspackages" + 程序包目录（模板 ID） + 软件包名称（模板 id） + pkgx。</span><span class="sxs-lookup"><span data-stu-id="aa372-162">That path is calculated in the following way: settings storage path + “settingspackages” + package dir (template ID) + package name (template ID) + .pkgx.</span></span> <span data-ttu-id="aa372-163">如果该计算路径超过260个字符，则软件包存储将失败，并在 UE-V 操作事件日志中生成以下错误消息：</span><span class="sxs-lookup"><span data-stu-id="aa372-163">If that calculated path exceeds 260 characters, package storage will fail and generate the following error message in the UE-V operational event log:</span></span>

`[boost::filesystem::copy_file: The system cannot find the path specified]`

<span data-ttu-id="aa372-164">若要检查操作日志事件，请打开事件查看器并导航到 "应用程序和服务日志/Microsoft/用户体验虚拟化/登录/运行"。</span><span class="sxs-lookup"><span data-stu-id="aa372-164">To check the operational log events, open the Event Viewer and navigate to Applications and Services Logs / Microsoft / User Experience Virtualization / Logging / Operational.</span></span>

<span data-ttu-id="aa372-165">**解决方法：** 尚.</span><span class="sxs-lookup"><span data-stu-id="aa372-165">**WORKAROUND:** None.</span></span>

### <span data-ttu-id="aa372-166">某些操作系统设置仅在类似操作系统版本之间漫游</span><span class="sxs-lookup"><span data-stu-id="aa372-166">Some operating system settings only roam between like operating system versions</span></span>

<span data-ttu-id="aa372-167">针对讲述人的操作系统设置和特定于区域设置的货币字符（即语言和区域设置）将仅在 Windows 的操作系统版本上漫游。</span><span class="sxs-lookup"><span data-stu-id="aa372-167">Operating system settings for Narrator and currency characters specific to the locale (i.e. language and regional settings) will only roam across like operating system versions of Windows.</span></span> <span data-ttu-id="aa372-168">例如，货币字符将不会在 Windows 7 和 Windows 8 之间漫游。</span><span class="sxs-lookup"><span data-stu-id="aa372-168">For example, currency characters will not roam between Windows 7 and Windows 8.</span></span>

<span data-ttu-id="aa372-169">**解决方法：** 尚</span><span class="sxs-lookup"><span data-stu-id="aa372-169">**WORKAROUND:** None</span></span>

### <span data-ttu-id="aa372-170">当应用在意外关闭后重新启动时，Windows 8 应用不会同步设置</span><span class="sxs-lookup"><span data-stu-id="aa372-170">Windows 8 apps do not sync settings when the app restarts after closing unexpectedly</span></span>

<span data-ttu-id="aa372-171">如果 Windows 8 应用在启动后意外关闭，则当应用程序重新启动时，应用程序的设置可能不会同步。</span><span class="sxs-lookup"><span data-stu-id="aa372-171">If a Windows 8 app closes unexpectedly soon after startup, settings for the application may not be synchronized when the application is restarted.</span></span>

<span data-ttu-id="aa372-172">**解决方法：** 关闭 Windows 8 应用，关闭并重新启动 UevAppMonitor.exe 应用程序（可使用 TaskManager），然后重新启动 Windows 8 应用。</span><span class="sxs-lookup"><span data-stu-id="aa372-172">**WORKAROUND:** Close the Windows 8 app, close and restart the UevAppMonitor.exe application (can use TaskManager), and then restart the Windows 8 app.</span></span>

### <a href="" id="ue-v-1-agent-generates-errors-when-running-ue-v-2-templates-"></a><span data-ttu-id="aa372-173">UE-V 1 代理在运行 UE-V 2 模板时生成错误</span><span class="sxs-lookup"><span data-stu-id="aa372-173">UE-V 1 agent generates errors when running UE-V 2 templates</span></span>

<span data-ttu-id="aa372-174">如果将 UE-V 2 设置位置模板分配给使用 UE-V 1 代理安装的计算机，则某些设置无法在计算机之间同步，并且代理会在事件日志中报告错误。</span><span class="sxs-lookup"><span data-stu-id="aa372-174">If a UE-V 2 settings location template is distributed to a computer installed with a UE-V 1 agent, some settings fail to synchronize between computers and the agent reports errors in the event log.</span></span>

<span data-ttu-id="aa372-175">**解决方法：** 从 UE-V 1 迁移到 UE-V 2 时，如果计算机运行的是早期版本的代理，则可以创建单独的 UE-V 2.0 目录以支持 UE-V 2.0 代理和模板。</span><span class="sxs-lookup"><span data-stu-id="aa372-175">**WORKAROUND:** When migrating from UE-V 1 to UE-V 2 and it is likely you’ll have computers running the previous version of the agent, create a separate UE-V 2.0 catalog to support the UE-V 2.0 Agent and templates.</span></span>

## <span data-ttu-id="aa372-176">UE-V 2.0 的修补程序和知识文库文章</span><span class="sxs-lookup"><span data-stu-id="aa372-176">Hotfixes and Knowledge Base articles for UE-V 2.0</span></span>


<span data-ttu-id="aa372-177">本部分包含用于 UE-V 2.0 的修补程序和知识库文章。</span><span class="sxs-lookup"><span data-stu-id="aa372-177">This section contains hotfixes and KB articles for UE-V 2.0.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong><span data-ttu-id="aa372-178">知识库文章</span><span class="sxs-lookup"><span data-stu-id="aa372-178">KB Article</span></span></strong></th>
<th align="left"><span data-ttu-id="aa372-179">Title</span><span class="sxs-lookup"><span data-stu-id="aa372-179">Title</span></span></th>
<th align="left"><strong><span data-ttu-id="aa372-180">链接</span><span class="sxs-lookup"><span data-stu-id="aa372-180">Link</span></span></strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="aa372-181">2927019</span><span class="sxs-lookup"><span data-stu-id="aa372-181">2927019</span></span></p></td>
<td align="left"><p><span data-ttu-id="aa372-182">Microsoft 用户体验虚拟化2.0 的修补程序包1</span><span class="sxs-lookup"><span data-stu-id="aa372-182">Hotfix Package 1 for Microsoft User Experience Virtualization 2.0</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2927019" data-raw-source="[support.microsoft.com/kb/2927019](https://support.microsoft.com/kb/2927019)"><span data-ttu-id="aa372-183">support.microsoft.com/kb/2927019</span><span class="sxs-lookup"><span data-stu-id="aa372-183">support.microsoft.com/kb/2927019</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="aa372-184">2903501</span><span class="sxs-lookup"><span data-stu-id="aa372-184">2903501</span></span></p></td>
<td align="left"><p><span data-ttu-id="aa372-185">UE-V：用户体验虚拟化（UE-V）与用户配置文件的兼容性</span><span class="sxs-lookup"><span data-stu-id="aa372-185">UE-V: User Experience Virtualization (UE-V) compatibility with user profiles</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2903501/EN-US" data-raw-source="[support.microsoft.com/kb/2903501/EN-US](https://support.microsoft.com/kb/2903501/EN-US)"><span data-ttu-id="aa372-186">support.microsoft.com/kb/2903501/EN-US</span><span class="sxs-lookup"><span data-stu-id="aa372-186">support.microsoft.com/kb/2903501/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="aa372-187">2770042</span><span class="sxs-lookup"><span data-stu-id="aa372-187">2770042</span></span></p></td>
<td align="left"><p><span data-ttu-id="aa372-188">UE-V 注册表设置</span><span class="sxs-lookup"><span data-stu-id="aa372-188">UE-V Registry Settings</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2770042/EN-US" data-raw-source="[support.microsoft.com/kb/2770042/EN-US](https://support.microsoft.com/kb/2770042/EN-US)"><span data-ttu-id="aa372-189">support.microsoft.com/kb/2770042/EN-US</span><span class="sxs-lookup"><span data-stu-id="aa372-189">support.microsoft.com/kb/2770042/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="aa372-190">2847017</span><span class="sxs-lookup"><span data-stu-id="aa372-190">2847017</span></span></p></td>
<td align="left"><p><span data-ttu-id="aa372-191">由 Internet Explorer 复制的 UE-V 设置</span><span class="sxs-lookup"><span data-stu-id="aa372-191">UE-V settings replicated by Internet Explorer</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2847017/EN-US" data-raw-source="[support.microsoft.com/kb/2847017/EN-US](https://support.microsoft.com/kb/2847017/EN-US)"><span data-ttu-id="aa372-192">support.microsoft.com/kb/2847017/EN-US</span><span class="sxs-lookup"><span data-stu-id="aa372-192">support.microsoft.com/kb/2847017/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="aa372-193">2930271</span><span class="sxs-lookup"><span data-stu-id="aa372-193">2930271</span></span></p></td>
<td align="left"><p><span data-ttu-id="aa372-194">了解 Microsoft UE-V 中的漫游 Outlook 签名的限制</span><span class="sxs-lookup"><span data-stu-id="aa372-194">Understanding the limitations of roaming Outlook signatures in Microsoft UE-V</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2930271/EN-US" data-raw-source="[support.microsoft.com/kb/2930271/EN-US](https://support.microsoft.com/kb/2930271/EN-US)"><span data-ttu-id="aa372-195">support.microsoft.com/kb/2930271/EN-US</span><span class="sxs-lookup"><span data-stu-id="aa372-195">support.microsoft.com/kb/2930271/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="aa372-196">2769631</span><span class="sxs-lookup"><span data-stu-id="aa372-196">2769631</span></span></p></td>
<td align="left"><p><span data-ttu-id="aa372-197">如何修复损坏的 UE-V 安装</span><span class="sxs-lookup"><span data-stu-id="aa372-197">How to repair a corrupted UE-V install</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2769631/EN-US" data-raw-source="[support.microsoft.com/kb/2769631/EN-US](https://support.microsoft.com/kb/2769631/EN-US)"><span data-ttu-id="aa372-198">support.microsoft.com/kb/2769631/EN-US</span><span class="sxs-lookup"><span data-stu-id="aa372-198">support.microsoft.com/kb/2769631/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="aa372-199">2850989</span><span class="sxs-lookup"><span data-stu-id="aa372-199">2850989</span></span></p></td>
<td align="left"><p><span data-ttu-id="aa372-200">不支持通过 Microsoft UE-V 迁移 MAPI 配置文件</span><span class="sxs-lookup"><span data-stu-id="aa372-200">Migrating MAPI profiles with Microsoft UE-V is not supported</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2850989/EN-US" data-raw-source="[support.microsoft.com/kb/2850989/EN-US](https://support.microsoft.com/kb/2850989/EN-US)"><span data-ttu-id="aa372-201">support.microsoft.com/kb/2850989/EN-US</span><span class="sxs-lookup"><span data-stu-id="aa372-201">support.microsoft.com/kb/2850989/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="aa372-202">2769586</span><span class="sxs-lookup"><span data-stu-id="aa372-202">2769586</span></span></p></td>
<td align="left"><p><span data-ttu-id="aa372-203">UE-V 漫游空文件夹和注册表项</span><span class="sxs-lookup"><span data-stu-id="aa372-203">UE-V roams empty folders and registry keys</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2769586/EN-US" data-raw-source="[support.microsoft.com/kb/2769586/EN-US](https://support.microsoft.com/kb/2769586/EN-US)"><span data-ttu-id="aa372-204">support.microsoft.com/kb/2769586/EN-US</span><span class="sxs-lookup"><span data-stu-id="aa372-204">support.microsoft.com/kb/2769586/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="aa372-205">2782997</span><span class="sxs-lookup"><span data-stu-id="aa372-205">2782997</span></span></p></td>
<td align="left"><p><span data-ttu-id="aa372-206">如何在 Microsoft 用户体验虚拟化（UE-V）中启用调试日志记录</span><span class="sxs-lookup"><span data-stu-id="aa372-206">How To Enable Debug Logging in Microsoft User Experience Virtualization (UE-V)</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2782997/EN-US" data-raw-source="[support.microsoft.com/kb/2782997/EN-US](https://support.microsoft.com/kb/2782997/EN-US)"><span data-ttu-id="aa372-207">support.microsoft.com/kb/2782997/EN-US</span><span class="sxs-lookup"><span data-stu-id="aa372-207">support.microsoft.com/kb/2782997/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="aa372-208">2769570</span><span class="sxs-lookup"><span data-stu-id="aa372-208">2769570</span></span></p></td>
<td align="left"><p><span data-ttu-id="aa372-209">UE-V 不会在 RDS 或 VDI 会话上更新主题</span><span class="sxs-lookup"><span data-stu-id="aa372-209">UE-V does not update the theme on RDS or VDI sessions</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2769570/EN-US" data-raw-source="[support.microsoft.com/kb/2769570/EN-US](https://support.microsoft.com/kb/2769570/EN-US)"><span data-ttu-id="aa372-210">support.microsoft.com/kb/2769570/EN-US</span><span class="sxs-lookup"><span data-stu-id="aa372-210">support.microsoft.com/kb/2769570/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="aa372-211">2901856</span><span class="sxs-lookup"><span data-stu-id="aa372-211">2901856</span></span></p></td>
<td align="left"><p><span data-ttu-id="aa372-212">在支持 UE-V 的计算机上强制重启后，应用程序设置不同步</span><span class="sxs-lookup"><span data-stu-id="aa372-212">Application settings do not sync after you force a restart on a UE-V-enabled computer</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2901856/EN-US" data-raw-source="[support.microsoft.com/kb/2901856/EN-US](https://support.microsoft.com/kb/2901856/EN-US)"><span data-ttu-id="aa372-213">support.microsoft.com/kb/2901856/EN-US</span><span class="sxs-lookup"><span data-stu-id="aa372-213">support.microsoft.com/kb/2901856/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="aa372-214">2850582</span><span class="sxs-lookup"><span data-stu-id="aa372-214">2850582</span></span></p></td>
<td align="left"><p><span data-ttu-id="aa372-215">如何将 Microsoft 用户体验虚拟化与 App-v 应用程序配合使用</span><span class="sxs-lookup"><span data-stu-id="aa372-215">How To Use Microsoft User Experience Virtualization With App-V Applications</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2850582/EN-US" data-raw-source="[support.microsoft.com/kb/2850582/EN-US](https://support.microsoft.com/kb/2850582/EN-US)"><span data-ttu-id="aa372-216">support.microsoft.com/kb/2850582/EN-US</span><span class="sxs-lookup"><span data-stu-id="aa372-216">support.microsoft.com/kb/2850582/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="aa372-217">3041879</span><span class="sxs-lookup"><span data-stu-id="aa372-217">3041879</span></span></p></td>
<td align="left"><p><span data-ttu-id="aa372-218">Microsoft 用户体验虚拟化的当前文件版本</span><span class="sxs-lookup"><span data-stu-id="aa372-218">Current file versions for Microsoft User Experience Virtualization</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/3041879/EN-US" data-raw-source="[support.microsoft.com/kb/3041879/EN-US](https://support.microsoft.com/kb/3041879/EN-US)"><span data-ttu-id="aa372-219">support.microsoft.com/kb/3041879/EN-US</span><span class="sxs-lookup"><span data-stu-id="aa372-219">support.microsoft.com/kb/3041879/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="aa372-220">2843592</span><span class="sxs-lookup"><span data-stu-id="aa372-220">2843592</span></span></p></td>
<td align="left"><p><span data-ttu-id="aa372-221">有关用户体验虚拟化和高可用性的信息</span><span class="sxs-lookup"><span data-stu-id="aa372-221">Information on User Experience Virtualization and High Availability</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2843592/EN-US" data-raw-source="[support.microsoft.com/kb/2843592/EN-US](https://support.microsoft.com/kb/2843592/EN-US)"><span data-ttu-id="aa372-222">support.microsoft.com/kb/2843592/EN-US</span><span class="sxs-lookup"><span data-stu-id="aa372-222">support.microsoft.com/kb/2843592/EN-US</span></span></a></p></td>
</tr>
</tbody>
</table>

 

 

 





