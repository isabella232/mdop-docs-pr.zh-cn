---
title: Microsoft 用户体验虚拟化 (UE-V) 2.1 SP1 发行说明
description: Microsoft 用户体验虚拟化 (UE-V) 2.1 SP1 发行说明
author: dansimp
ms.assetid: 561988c4-cc5c-4e15-970b-16e942c8f2ef
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 03/30/2017
ms.openlocfilehash: 974914421c61c829b5a32e336bddf8ea1addf514
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803787"
---
# <span data-ttu-id="2eb56-103">Microsoft 用户体验虚拟化 (UE-V) 2.1 SP1 发行说明</span><span class="sxs-lookup"><span data-stu-id="2eb56-103">Microsoft User Experience Virtualization (UE-V) 2.1 SP1 Release Notes</span></span>


<span data-ttu-id="2eb56-104">若要搜索 Microsoft 用户体验虚拟化 2.1 SP1 发行说明，请按 Ctrl + F。</span><span class="sxs-lookup"><span data-stu-id="2eb56-104">To search Microsoft User Experience Virtualization 2.1 SP1 release notes, press Ctrl+F.</span></span>

<span data-ttu-id="2eb56-105">在安装 UE-V 之前，应仔细阅读这些发行说明。</span><span class="sxs-lookup"><span data-stu-id="2eb56-105">You should read these release notes thoroughly before you install UE-V.</span></span> <span data-ttu-id="2eb56-106">发行说明包含成功安装用户体验虚拟化所需的信息，并包含产品文档中不可用的其他信息。</span><span class="sxs-lookup"><span data-stu-id="2eb56-106">The release notes contain information that is required to successfully install User Experience Virtualization, and contain additional information that is not available in the product documentation.</span></span> <span data-ttu-id="2eb56-107">如果这些发行说明和其他 UE-V 文档之间存在差异，则应将最新更改视为权威。</span><span class="sxs-lookup"><span data-stu-id="2eb56-107">If there are differences between these release notes and other UE-V documentation, the latest change should be considered authoritative.</span></span> <span data-ttu-id="2eb56-108">这些发行说明取代了本产品附带的内容。</span><span class="sxs-lookup"><span data-stu-id="2eb56-108">These release notes supersede the content that is included with this product.</span></span>

## <span data-ttu-id="2eb56-109">提供反馈</span><span class="sxs-lookup"><span data-stu-id="2eb56-109">Providing feedback</span></span>


<span data-ttu-id="2eb56-110">通过向我们提供反馈和评论，告诉我们您对 MDOP 文档的看法。</span><span class="sxs-lookup"><span data-stu-id="2eb56-110">Tell us what you think about our documentation for MDOP by giving us your feedback and comments.</span></span> <span data-ttu-id="2eb56-111">将文档反馈发送到[mdopdocs@microsoft.com](mailto:mdopdocs@microsoft.com?subject=UE-V%20Documentation)。</span><span class="sxs-lookup"><span data-stu-id="2eb56-111">Send your documentation feedback to [mdopdocs@microsoft.com](mailto:mdopdocs@microsoft.com?subject=UE-V%20Documentation).</span></span>

## <span data-ttu-id="2eb56-112">UE-V 已知问题</span><span class="sxs-lookup"><span data-stu-id="2eb56-112">UE-V known issues</span></span>


<span data-ttu-id="2eb56-113">本部分包含适用于用户体验虚拟化 2.1 SP1 的发行说明。</span><span class="sxs-lookup"><span data-stu-id="2eb56-113">This section contains release notes for User Experience Virtualization 2.1 SP1.</span></span>

### <span data-ttu-id="2eb56-114">用于 Skype 的 UE-V 设置位置模板导致 Skype 崩溃</span><span class="sxs-lookup"><span data-stu-id="2eb56-114">UE-V settings location templates for Skype cause Skype to crash</span></span>

<span data-ttu-id="2eb56-115">当用户为 Skype 桌面应用程序生成有效的设置位置模板时，将注册该模板，然后启动 Skype 桌面应用程序，Skype 崩溃。</span><span class="sxs-lookup"><span data-stu-id="2eb56-115">When a user generates a valid settings location template for the Skype desktop application, registers it, and then launches the Skype desktop application, Skype crashes.</span></span> <span data-ttu-id="2eb56-116">在应用程序事件日志中记录了一个访问 \ _VIOLATION。</span><span class="sxs-lookup"><span data-stu-id="2eb56-116">An ACCESS\_VIOLATION is recorded in the Application Event Log.</span></span>

<span data-ttu-id="2eb56-117">解决方法：删除或注销 Skype 模板以允许 Skype 再次工作。</span><span class="sxs-lookup"><span data-stu-id="2eb56-117">WORKAROUND: Remove or unregister the Skype template to allow Skype to work again.</span></span>

### <span data-ttu-id="2eb56-118">用于无提示安装 UE-V 的现有脚本可能失败</span><span class="sxs-lookup"><span data-stu-id="2eb56-118">Existing scripts for silent installations of UE-V may fail</span></span>

<span data-ttu-id="2eb56-119">在安装 UE-V 2.1 SP1 时，对 UE-V 安装程序所做的两个更改可能会导致运行早期版本的 UE-V 的无声安装脚本失败。</span><span class="sxs-lookup"><span data-stu-id="2eb56-119">Two changes made to the UE-V installer can cause silent installation scripts that worked for previous versions of UE-V to fail when installing UE-V 2.1 SP1.</span></span> <span data-ttu-id="2eb56-120">第一项是用户必须接受许可条款并同意或拒绝参与客户体验改善计划（CEIP）的新要求，即使在缄默安装期间也是如此。</span><span class="sxs-lookup"><span data-stu-id="2eb56-120">The first is a new requirement that users must accept the license terms and agree to or decline participation in the Customer Experience Improvement Program (CEIP), even during a silent installation.</span></span> <span data-ttu-id="2eb56-121">使用/q 参数已不再足以指明接受许可证条款和协议以参与 CEIP。</span><span class="sxs-lookup"><span data-stu-id="2eb56-121">Using the /q parameter is no longer sufficient to indicate acceptance of the license terms and agreement to participate in CEIP.</span></span>

<span data-ttu-id="2eb56-122">第二，安装程序现在在安装 UE-V Agent 后强制重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="2eb56-122">Second, the installer now forces a computer restart after installing the UE-V Agent.</span></span> <span data-ttu-id="2eb56-123">这可能会导致安装脚本在不需要重新启动时失败（例如，它首先安装 UE-V Agent，然后立即安装生成器）。</span><span class="sxs-lookup"><span data-stu-id="2eb56-123">This can cause an install script to fail if it is not expecting the restart (for example, it installs the UE-V Agent first and then immediately installs the generator).</span></span>

<span data-ttu-id="2eb56-124">解决方法： UE-V 安装程序（.msi）具有两个支持静默安装的新命令行参数。</span><span class="sxs-lookup"><span data-stu-id="2eb56-124">WORKAROUND: The UE-V installer (.msi) has two new command-line parameters that support silent installations.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="2eb56-125">参数</span><span class="sxs-lookup"><span data-stu-id="2eb56-125">Parameter</span></span></th>
<th align="left"><span data-ttu-id="2eb56-126">描述</span><span class="sxs-lookup"><span data-stu-id="2eb56-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="2eb56-127">/ACCEPTLICENSETERMS = True</span><span class="sxs-lookup"><span data-stu-id="2eb56-127">/ACCEPTLICENSETERMS=True</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="2eb56-128">将此参数设置为 <strong> True </strong> 以无提示安装 ue-v。</span><span class="sxs-lookup"><span data-stu-id="2eb56-128">Set this parameter to <strong>True</strong> to install UE-V silently.</span></span> <span data-ttu-id="2eb56-129">添加此参数意味着用户接受在此处找到的 UE-V 许可条款（默认情况下）：%ProgramFiles%\Microsoft 用户体验 Virtualization\Agent</span><span class="sxs-lookup"><span data-stu-id="2eb56-129">Adding this parameter implies that the user accepts the UE-V license terms, which are found (by default) here: %ProgramFiles%\Microsoft User Experience Virtualization\Agent</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="2eb56-130">/NORESTART</span><span class="sxs-lookup"><span data-stu-id="2eb56-130">/NORESTART</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="2eb56-131">此参数可防止安装 UE-V agent 后强制重启。</span><span class="sxs-lookup"><span data-stu-id="2eb56-131">This parameter prevents the mandatory restart after the UE-V agent is installed.</span></span> <span data-ttu-id="2eb56-132">3010的返回代码表示在使用 UE-V 之前需要重启。</span><span class="sxs-lookup"><span data-stu-id="2eb56-132">A return code of 3010 indicates that a restart is required prior to using UE-V.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="2eb56-133">注册表设置不在同一台计算机上的 app-v 和本机应用程序之间同步</span><span class="sxs-lookup"><span data-stu-id="2eb56-133">Registry settings do not synchronize between App-V and native applications on the same computer</span></span>

<span data-ttu-id="2eb56-134">当计算机具有通过应用程序虚拟化（app-v）安装的应用程序并使用 Windows Installer （.msi）文件本地安装的应用程序时，基于注册表的设置不会在技术之间同步。</span><span class="sxs-lookup"><span data-stu-id="2eb56-134">When a computer has an application that is installed through both Application Virtualization (App-V) and locally with a Windows Installer (.msi) file, the registry-based settings do not synchronize between the technologies.</span></span>

<span data-ttu-id="2eb56-135">解决方法：若要解决此问题，请通过选择两种技术之一来运行应用程序，但不能同时选择二者。</span><span class="sxs-lookup"><span data-stu-id="2eb56-135">WORKAROUND: To resolve this problem, run the application by selecting one of the two technologies, but not both.</span></span>

### <span data-ttu-id="2eb56-136">安装了 Office 2010 和 Office 2013 时不可预测的结果</span><span class="sxs-lookup"><span data-stu-id="2eb56-136">Unpredictable results with both Office 2010 and Office 2013 installed</span></span>

<span data-ttu-id="2eb56-137">如果用户安装了 Office 2010 和 Office 2013，则两个版本的 Office 之间的任何常见设置都通过 UE-V 漫游。</span><span class="sxs-lookup"><span data-stu-id="2eb56-137">When a user has both Office 2010 and Office 2013 installed, any common settings between the two versions of Office are roamed by UE-V.</span></span> <span data-ttu-id="2eb56-138">这可能会导致 Office 2010 程序包大小相当大或导致与2013的不可预知的冲突，尤其是在使用 Office 365 时。</span><span class="sxs-lookup"><span data-stu-id="2eb56-138">This could cause the Office 2010 package size to be quite large or result in unpredictable conflicts with 2013, particularly if Office 365 is used.</span></span>

<span data-ttu-id="2eb56-139">解决方法：仅安装一个版本的 Office 或限制由 UE-V 同步的设置。</span><span class="sxs-lookup"><span data-stu-id="2eb56-139">WORKAROUND: Install only one version of Office or limit which settings are synchronized by UE-V.</span></span>

### <span data-ttu-id="2eb56-140">卸载并重新安装 Windows 8 应用会将设置还原为初始状态</span><span class="sxs-lookup"><span data-stu-id="2eb56-140">Uninstall and re-install of Windows 8 app reverts settings to initial state</span></span>

<span data-ttu-id="2eb56-141">使用 UE-V 设置同步处理 Windows 8 应用时，如果用户卸载应用，然后重新安装该应用，则应用的设置将还原为其默认值。</span><span class="sxs-lookup"><span data-stu-id="2eb56-141">While using UE-V settings synchronization for a Windows 8 app, if the user uninstalls the app and then reinstalls the app, the app’s settings revert to their default values.</span></span><span data-ttu-id="2eb56-142">发生这种情况是因为卸载删除了应用设置的本地（缓存）副本，但不会删除本地 UE-V 设置程序包。</span><span class="sxs-lookup"><span data-stu-id="2eb56-142"> This happens because the uninstall removes the local (cached) copy of the app’s settings but does not remove the local UE-V settings package.</span></span><span data-ttu-id="2eb56-143">当应用重新安装并启动时，UE-V 收集重置为应用默认设置的应用设置，然后将默认设置上载到中央存储位置。</span><span class="sxs-lookup"><span data-stu-id="2eb56-143"> When the app is reinstalled and launched, UE-V gather the app settings that were reset to the app defaults and then uploads the default settings to the central storage location.</span></span><span data-ttu-id="2eb56-144">然后，运行应用的其他计算机将下载默认设置。</span><span class="sxs-lookup"><span data-stu-id="2eb56-144"> Other computers running the app then download the default settings.</span></span><span data-ttu-id="2eb56-145">此行为与桌面应用程序的行为相同。</span><span class="sxs-lookup"><span data-stu-id="2eb56-145"> This behavior is identical to the behavior of desktop applications.</span></span>

<span data-ttu-id="2eb56-146">解决方法：无。</span><span class="sxs-lookup"><span data-stu-id="2eb56-146">WORKAROUND: None.</span></span>

### <span data-ttu-id="2eb56-147">UE-V 不支持32位和64位版本的 Microsoft Office 之间的漫游设置</span><span class="sxs-lookup"><span data-stu-id="2eb56-147">UE-V does not support roaming settings between 32-bit and 64-bit versions of Microsoft Office</span></span>

<span data-ttu-id="2eb56-148">我们建议你为32位和64位操作系统安装32位版本的 Microsoft Office。</span><span class="sxs-lookup"><span data-stu-id="2eb56-148">We recommend that you install the 32-bit version of Microsoft Office for both 32-bit and 64-bit operating systems.</span></span> <span data-ttu-id="2eb56-149">若要选择所需的 Microsoft Office 版本，请单击此处。</span><span class="sxs-lookup"><span data-stu-id="2eb56-149">To choose the Microsoft Office version that you need, click here.</span></span> <span data-ttu-id="2eb56-150">([http://office.microsoft.com/word-help/choose-the-32-bit-or-64-bit-version-of-microsoft-office-HA010369476.aspx](https://go.microsoft.com/fwlink/?LinkID=247623)).</span><span class="sxs-lookup"><span data-stu-id="2eb56-150">([http://office.microsoft.com/word-help/choose-the-32-bit-or-64-bit-version-of-microsoft-office-HA010369476.aspx](https://go.microsoft.com/fwlink/?LinkID=247623)).</span></span> <span data-ttu-id="2eb56-151">UE-V 支持 Office 的相同体系结构版本之间的漫游设置。</span><span class="sxs-lookup"><span data-stu-id="2eb56-151">UE-V supports roaming settings between identical architecture versions of Office.</span></span> <span data-ttu-id="2eb56-152">例如，32位 Office 设置将在所有32位 Office 实例之间漫游。</span><span class="sxs-lookup"><span data-stu-id="2eb56-152">For example, 32-bit Office settings will roam between all 32-bit Office instances.</span></span> <span data-ttu-id="2eb56-153">UE-V 不支持32位和64位版本的 Office 之间的漫游设置。</span><span class="sxs-lookup"><span data-stu-id="2eb56-153">UE-V does not support roaming settings between 32-bit and 64-bit versions of Office.</span></span>

<span data-ttu-id="2eb56-154">解决方法：无</span><span class="sxs-lookup"><span data-stu-id="2eb56-154">WORKAROUND: None</span></span>

### <a href="" id="msi-s-are-not-localized"></a><span data-ttu-id="2eb56-155">MSI 未本地化</span><span class="sxs-lookup"><span data-stu-id="2eb56-155">MSI’s are not localized</span></span>

<span data-ttu-id="2eb56-156">UE-V 包括用于 UE-V Agent 和 UE-V 发生器的本地化设置程序。</span><span class="sxs-lookup"><span data-stu-id="2eb56-156">UE-V includes a localized setup program for both the UE-V Agent and UE-V generator.</span></span> <span data-ttu-id="2eb56-157">这些 MSI 文件仍然可用，但用户界面已最小化，并且 MSI 仅以英语显示。</span><span class="sxs-lookup"><span data-stu-id="2eb56-157">These MSI files are still available but the user interface is minimized and the MSI’s only display in English.</span></span> <span data-ttu-id="2eb56-158">尽管文件是英语，安装程序也会在安装期间安装所有支持的语言。</span><span class="sxs-lookup"><span data-stu-id="2eb56-158">Despite the file being in English, the setup program installs all supported languages during the installation.</span></span>

<span data-ttu-id="2eb56-159">解决方法：无</span><span class="sxs-lookup"><span data-stu-id="2eb56-159">WORKAROUND: None</span></span>

### <span data-ttu-id="2eb56-160">与 Internet Explorer 9 收藏夹相关联的 Favicons 不漫游</span><span class="sxs-lookup"><span data-stu-id="2eb56-160">Favicons that are associated with Internet Explorer 9 favorites do not roam</span></span>

<span data-ttu-id="2eb56-161">与 Internet Explorer 9 常用联系人相关联的 favicons 不是由用户体验虚拟化漫游的，并且在新计算机上首次显示收藏时不会显示。</span><span class="sxs-lookup"><span data-stu-id="2eb56-161">The favicons that are associated with Internet Explorer 9 favorites are not roamed by User Experience Virtualization and do not appear when the favorites first appear on a new computer.</span></span>

<span data-ttu-id="2eb56-162">解决方法：在 Internet Explorer 9 浏览器中使用并缓存书签后，Favicons 将显示相关联的常用联系人。</span><span class="sxs-lookup"><span data-stu-id="2eb56-162">WORKAROUND: Favicons will appear with their associated favorites once the bookmark is used and cached in the Internet Explorer 9 browser.</span></span>

### <span data-ttu-id="2eb56-163">文件设置路径存储在注册表中</span><span class="sxs-lookup"><span data-stu-id="2eb56-163">File settings paths are stored in registry</span></span>

<span data-ttu-id="2eb56-164">某些应用程序设置将其配置和设置文件的路径存储为注册表中的值。</span><span class="sxs-lookup"><span data-stu-id="2eb56-164">Some application settings store the paths of their configuration and settings files as values in the registry.</span></span> <span data-ttu-id="2eb56-165">当设置在计算机之间漫游时，必须同步在注册表中作为路径引用的文件。</span><span class="sxs-lookup"><span data-stu-id="2eb56-165">The files that are referenced as paths in the registry must be synchronized when settings are roamed between computers.</span></span>

<span data-ttu-id="2eb56-166">解决方法：使用 "文件夹重定向" 或其他技术确保作为文件设置路径引用的所有文件都存在并放置在 "设置" 漫游的所有计算机上的相同位置。</span><span class="sxs-lookup"><span data-stu-id="2eb56-166">WORKAROUND: Use folder redirection or some other technology to ensure that any files that are referenced as file settings paths are present and placed in the same location on all computers where settings roam.</span></span>

### <span data-ttu-id="2eb56-167">较长设置存储路径可能会导致错误</span><span class="sxs-lookup"><span data-stu-id="2eb56-167">Long Settings Storage Paths could cause an error</span></span>

<span data-ttu-id="2eb56-168">使设置存储路径尽可能简短。</span><span class="sxs-lookup"><span data-stu-id="2eb56-168">Keep settings storage paths as short as possible.</span></span> <span data-ttu-id="2eb56-169">长路径可能会阻止分辨率或同步。</span><span class="sxs-lookup"><span data-stu-id="2eb56-169">Long paths could prevent resolution or synchronization.</span></span> <span data-ttu-id="2eb56-170">UE-V 使用设置存储路径作为存储设置的计算路径的一部分。</span><span class="sxs-lookup"><span data-stu-id="2eb56-170">UE-V uses the Settings storage path as part of the calculated path to store settings.</span></span> <span data-ttu-id="2eb56-171">该路径按以下方式计算：设置存储路径 + "settingspackages" + 程序包目录（模板 ID） + 软件包名称（模板 id） + pkgx。</span><span class="sxs-lookup"><span data-stu-id="2eb56-171">That path is calculated in the following way: settings storage path + “settingspackages” + package dir (template ID) + package name (template ID) + .pkgx.</span></span> <span data-ttu-id="2eb56-172">如果该计算路径超过260个字符，则软件包存储将失败，并在 UE-V 操作事件日志中生成以下错误消息：</span><span class="sxs-lookup"><span data-stu-id="2eb56-172">If that calculated path exceeds 260 characters, package storage will fail and generate the following error message in the UE-V operational event log:</span></span>

`[boost::filesystem::copy_file: The system cannot find the path specified]`

<span data-ttu-id="2eb56-173">若要检查操作日志事件，请打开事件查看器并导航到 "应用程序和服务日志/Microsoft/用户体验虚拟化/登录/运行"。</span><span class="sxs-lookup"><span data-stu-id="2eb56-173">To check the operational log events, open the Event Viewer and navigate to Applications and Services Logs / Microsoft / User Experience Virtualization / Logging / Operational.</span></span>

<span data-ttu-id="2eb56-174">解决方法：无。</span><span class="sxs-lookup"><span data-stu-id="2eb56-174">WORKAROUND: None.</span></span>

### <span data-ttu-id="2eb56-175">某些操作系统设置仅在类似操作系统版本之间漫游</span><span class="sxs-lookup"><span data-stu-id="2eb56-175">Some operating system settings only roam between like operating system versions</span></span>

<span data-ttu-id="2eb56-176">针对讲述人的操作系统设置和特定于区域设置的货币字符（即语言和区域设置）将仅在 Windows 的操作系统版本上漫游。</span><span class="sxs-lookup"><span data-stu-id="2eb56-176">Operating system settings for Narrator and currency characters specific to the locale (i.e. language and regional settings) will only roam across like operating system versions of Windows.</span></span> <span data-ttu-id="2eb56-177">例如，货币字符将不会在 Windows 7 和 Windows 8 之间漫游。</span><span class="sxs-lookup"><span data-stu-id="2eb56-177">For example, currency characters will not roam between Windows 7 and Windows 8.</span></span>

<span data-ttu-id="2eb56-178">解决方法：无</span><span class="sxs-lookup"><span data-stu-id="2eb56-178">WORKAROUND: None</span></span>

### <a href="" id="ue-v-1-agent-generates-errors-when-running-ue-v-2-templates-"></a><span data-ttu-id="2eb56-179">UE-V 1 代理在运行 UE-V 2 模板时生成错误</span><span class="sxs-lookup"><span data-stu-id="2eb56-179">UE-V 1 agent generates errors when running UE-V 2 templates</span></span>

<span data-ttu-id="2eb56-180">如果将 UE-V 2 设置位置模板分配给使用 UE-V 1 代理安装的计算机，则某些设置无法在计算机之间同步，并且代理会在事件日志中报告错误。</span><span class="sxs-lookup"><span data-stu-id="2eb56-180">If a UE-V 2 settings location template is distributed to a computer installed with a UE-V 1 agent, some settings fail to synchronize between computers and the agent reports errors in the event log.</span></span>

<span data-ttu-id="2eb56-181">解决方法：从 UE-V 1 迁移到 UE-V 2 时，如果计算机运行的是早期版本的代理，则可以创建一个单独的 UE-V 2 目录，以支持 UE-V 2 和 templates 代理和模板。</span><span class="sxs-lookup"><span data-stu-id="2eb56-181">WORKAROUND: When migrating from UE-V 1 to UE-V 2 and it is likely you’ll have computers running the previous version of the agent, create a separate UE-V 2.x catalog to support the UE-V 2.x Agent and templates.</span></span>

### <span data-ttu-id="2eb56-182">UE-V 注销延迟</span><span class="sxs-lookup"><span data-stu-id="2eb56-182">UE-V logoff delay</span></span>

<span data-ttu-id="2eb56-183">有时，在注销时，UE-V 需要花费很长时间来同步设置。</span><span class="sxs-lookup"><span data-stu-id="2eb56-183">Occasionally on logoff, UE-V takes a long time to sync settings.</span></span> <span data-ttu-id="2eb56-184">通常，这是由高延迟网络或 Distrubuted 文件系统（DFS）使用不当引起的。</span><span class="sxs-lookup"><span data-stu-id="2eb56-184">Typically, this is due to a high latency network or incorrect use of Distrubuted File System (DFS).</span></span>
<span data-ttu-id="2eb56-185">有关 DFS 支持，请参阅[Microsoft 的有关复制的用户配置文件数据的支持声明](https://support.microsoft.com/kb/2533009)，了解进一步的详细信息。</span><span class="sxs-lookup"><span data-stu-id="2eb56-185">For DFS support, see [Microsoft’s Support Statement Around Replicated User Profile Data](https://support.microsoft.com/kb/2533009) for further details.</span></span>

<span data-ttu-id="2eb56-186">解决方法：从 HF03 开始，引入了新的注册表项以下注册表项提供了一种机制，可通过该机制来指定最大的注销延迟 \\Software\\Microsoft\\UEV\\Agent\\Configuration\\LogOffWaitInterval</span><span class="sxs-lookup"><span data-stu-id="2eb56-186">WORKAROUND: Starting with HF03, a new registry key has been introduced The following registry key provides a mechanism by which the maximum logoff delay can be specified \\Software\\Microsoft\\UEV\\Agent\\Configuration\\LogOffWaitInterval</span></span>

<span data-ttu-id="2eb56-187">有关进一步的详细信息，请参阅[ue-v 注册表设置](https://support.microsoft.com/kb/2770042)</span><span class="sxs-lookup"><span data-stu-id="2eb56-187">See [UE-V registry settings](https://support.microsoft.com/kb/2770042) for further details</span></span>

## <span data-ttu-id="2eb56-188">用于 UE-V 2.1 SP1 的修补程序和知识文库文章</span><span class="sxs-lookup"><span data-stu-id="2eb56-188">Hotfixes and Knowledge Base articles for UE-V 2.1 SP1</span></span>


<span data-ttu-id="2eb56-189">本部分包含用于 UE-V 2.1 SP1 的修补程序和知识库文章。</span><span class="sxs-lookup"><span data-stu-id="2eb56-189">This section contains hotfixes and KB articles for UE-V 2.1 SP1.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong><span data-ttu-id="2eb56-190">知识库文章</span><span class="sxs-lookup"><span data-stu-id="2eb56-190">KB Article</span></span></strong></th>
<th align="left"><span data-ttu-id="2eb56-191">Title</span><span class="sxs-lookup"><span data-stu-id="2eb56-191">Title</span></span></th>
<th align="left"><strong><span data-ttu-id="2eb56-192">链接</span><span class="sxs-lookup"><span data-stu-id="2eb56-192">Link</span></span></strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2eb56-193">3018608</span><span class="sxs-lookup"><span data-stu-id="2eb56-193">3018608</span></span></p></td>
<td align="left"><p><span data-ttu-id="2eb56-194">UE-V 2.1-当 UE-V WMI 类缺失时 TemplateConsole.exe 崩溃</span><span class="sxs-lookup"><span data-stu-id="2eb56-194">UE-V 2.1 - TemplateConsole.exe crashes when UE-V WMI classes are missing</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/3018608/EN-US" data-raw-source="[support.microsoft.com/kb/3018608/EN-US](https://support.microsoft.com/kb/3018608/EN-US)"><span data-ttu-id="2eb56-195">support.microsoft.com/kb/3018608/EN-US</span><span class="sxs-lookup"><span data-stu-id="2eb56-195">support.microsoft.com/kb/3018608/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2eb56-196">2903501</span><span class="sxs-lookup"><span data-stu-id="2eb56-196">2903501</span></span></p></td>
<td align="left"><p><span data-ttu-id="2eb56-197">UE-V：用户体验虚拟化（UE-V）与用户配置文件的兼容性</span><span class="sxs-lookup"><span data-stu-id="2eb56-197">UE-V: User Experience Virtualization (UE-V) compatibility with user profiles</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2903501/EN-US" data-raw-source="[support.microsoft.com/kb/2903501/EN-US](https://support.microsoft.com/kb/2903501/EN-US)"><span data-ttu-id="2eb56-198">support.microsoft.com/kb/2903501/EN-US</span><span class="sxs-lookup"><span data-stu-id="2eb56-198">support.microsoft.com/kb/2903501/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2eb56-199">2770042</span><span class="sxs-lookup"><span data-stu-id="2eb56-199">2770042</span></span></p></td>
<td align="left"><p><span data-ttu-id="2eb56-200">UE-V 注册表设置</span><span class="sxs-lookup"><span data-stu-id="2eb56-200">UE-V Registry Settings</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2770042/EN-US" data-raw-source="[support.microsoft.com/kb/2770042/EN-US](https://support.microsoft.com/kb/2770042/EN-US)"><span data-ttu-id="2eb56-201">support.microsoft.com/kb/2770042/EN-US</span><span class="sxs-lookup"><span data-stu-id="2eb56-201">support.microsoft.com/kb/2770042/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2eb56-202">2847017</span><span class="sxs-lookup"><span data-stu-id="2eb56-202">2847017</span></span></p></td>
<td align="left"><p><span data-ttu-id="2eb56-203">由 Internet Explorer 复制的 UE-V 设置</span><span class="sxs-lookup"><span data-stu-id="2eb56-203">UE-V settings replicated by Internet Explorer</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2847017/EN-US" data-raw-source="[support.microsoft.com/kb/2847017/EN-US](https://support.microsoft.com/kb/2847017/EN-US)"><span data-ttu-id="2eb56-204">support.microsoft.com/kb/2847017/EN-US</span><span class="sxs-lookup"><span data-stu-id="2eb56-204">support.microsoft.com/kb/2847017/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2eb56-205">2769631</span><span class="sxs-lookup"><span data-stu-id="2eb56-205">2769631</span></span></p></td>
<td align="left"><p><span data-ttu-id="2eb56-206">如何修复损坏的 UE-V 安装</span><span class="sxs-lookup"><span data-stu-id="2eb56-206">How to repair a corrupted UE-V install</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2769631/EN-US" data-raw-source="[support.microsoft.com/kb/2769631/EN-US](https://support.microsoft.com/kb/2769631/EN-US)"><span data-ttu-id="2eb56-207">support.microsoft.com/kb/2769631/EN-US</span><span class="sxs-lookup"><span data-stu-id="2eb56-207">support.microsoft.com/kb/2769631/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2eb56-208">2850989</span><span class="sxs-lookup"><span data-stu-id="2eb56-208">2850989</span></span></p></td>
<td align="left"><p><span data-ttu-id="2eb56-209">不支持通过 Microsoft UE-V 迁移 MAPI 配置文件</span><span class="sxs-lookup"><span data-stu-id="2eb56-209">Migrating MAPI profiles with Microsoft UE-V is not supported</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2850989/EN-US" data-raw-source="[support.microsoft.com/kb/2850989/EN-US](https://support.microsoft.com/kb/2850989/EN-US)"><span data-ttu-id="2eb56-210">support.microsoft.com/kb/2850989/EN-US</span><span class="sxs-lookup"><span data-stu-id="2eb56-210">support.microsoft.com/kb/2850989/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2eb56-211">2769586</span><span class="sxs-lookup"><span data-stu-id="2eb56-211">2769586</span></span></p></td>
<td align="left"><p><span data-ttu-id="2eb56-212">UE-V 漫游空文件夹和注册表项</span><span class="sxs-lookup"><span data-stu-id="2eb56-212">UE-V roams empty folders and registry keys</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2769586/EN-US" data-raw-source="[support.microsoft.com/kb/2769586/EN-US](https://support.microsoft.com/kb/2769586/EN-US)"><span data-ttu-id="2eb56-213">support.microsoft.com/kb/2769586/EN-US</span><span class="sxs-lookup"><span data-stu-id="2eb56-213">support.microsoft.com/kb/2769586/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2eb56-214">2782997</span><span class="sxs-lookup"><span data-stu-id="2eb56-214">2782997</span></span></p></td>
<td align="left"><p><span data-ttu-id="2eb56-215">如何在 Microsoft 用户体验虚拟化（UE-V）中启用调试日志记录</span><span class="sxs-lookup"><span data-stu-id="2eb56-215">How To Enable Debug Logging in Microsoft User Experience Virtualization (UE-V)</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2782997/EN-US" data-raw-source="[support.microsoft.com/kb/2782997/EN-US](https://support.microsoft.com/kb/2782997/EN-US)"><span data-ttu-id="2eb56-216">support.microsoft.com/kb/2782997/EN-US</span><span class="sxs-lookup"><span data-stu-id="2eb56-216">support.microsoft.com/kb/2782997/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2eb56-217">2769570</span><span class="sxs-lookup"><span data-stu-id="2eb56-217">2769570</span></span></p></td>
<td align="left"><p><span data-ttu-id="2eb56-218">UE-V 不会在 RDS 或 VDI 会话上更新主题</span><span class="sxs-lookup"><span data-stu-id="2eb56-218">UE-V does not update the theme on RDS or VDI sessions</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2769570/EN-US" data-raw-source="[support.microsoft.com/kb/2769570/EN-US](https://support.microsoft.com/kb/2769570/EN-US)"><span data-ttu-id="2eb56-219">support.microsoft.com/kb/2769570/EN-US</span><span class="sxs-lookup"><span data-stu-id="2eb56-219">support.microsoft.com/kb/2769570/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2eb56-220">2850582</span><span class="sxs-lookup"><span data-stu-id="2eb56-220">2850582</span></span></p></td>
<td align="left"><p><span data-ttu-id="2eb56-221">如何将 Microsoft 用户体验虚拟化与 App-v 应用程序配合使用</span><span class="sxs-lookup"><span data-stu-id="2eb56-221">How To Use Microsoft User Experience Virtualization With App-V Applications</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2850582/EN-US" data-raw-source="[support.microsoft.com/kb/2850582/EN-US](https://support.microsoft.com/kb/2850582/EN-US)"><span data-ttu-id="2eb56-222">support.microsoft.com/kb/2850582/EN-US</span><span class="sxs-lookup"><span data-stu-id="2eb56-222">support.microsoft.com/kb/2850582/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2eb56-223">3041879</span><span class="sxs-lookup"><span data-stu-id="2eb56-223">3041879</span></span></p></td>
<td align="left"><p><span data-ttu-id="2eb56-224">Microsoft 用户体验虚拟化的当前文件版本</span><span class="sxs-lookup"><span data-stu-id="2eb56-224">Current file versions for Microsoft User Experience Virtualization</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/3041879/EN-US" data-raw-source="[support.microsoft.com/kb/3041879/EN-US](https://support.microsoft.com/kb/3041879/EN-US)"><span data-ttu-id="2eb56-225">support.microsoft.com/kb/3041879/EN-US</span><span class="sxs-lookup"><span data-stu-id="2eb56-225">support.microsoft.com/kb/3041879/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2eb56-226">2843592</span><span class="sxs-lookup"><span data-stu-id="2eb56-226">2843592</span></span></p></td>
<td align="left"><p><span data-ttu-id="2eb56-227">有关用户体验虚拟化和高可用性的信息</span><span class="sxs-lookup"><span data-stu-id="2eb56-227">Information on User Experience Virtualization and High Availability</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2843592/EN-US" data-raw-source="[support.microsoft.com/kb/2843592/EN-US](https://support.microsoft.com/kb/2843592/EN-US)"><span data-ttu-id="2eb56-228">support.microsoft.com/kb/2843592/EN-US</span><span class="sxs-lookup"><span data-stu-id="2eb56-228">support.microsoft.com/kb/2843592/EN-US</span></span></a></p></td>
</tr>
</tbody>
</table>

 






 

 





