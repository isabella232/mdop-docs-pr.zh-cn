---
title: Microsoft 用户体验虚拟化 (UE-V) 1.0 SP1 发行说明
description: Microsoft 用户体验虚拟化 (UE-V) 1.0 SP1 发行说明
author: dansimp
ms.assetid: 447fae0c-fe87-4d1c-b616-6f92fbdaf6d5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 8584999d9fdbdfccc3e9b2b1486cb97635475747
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798057"
---
# <span data-ttu-id="53547-103">Microsoft 用户体验虚拟化 (UE-V) 1.0 SP1 发行说明</span><span class="sxs-lookup"><span data-stu-id="53547-103">Microsoft User Experience Virtualization (UE-V) 1.0 SP1 Release Notes</span></span>


<span data-ttu-id="53547-104">若要搜索 Microsoft 用户体验虚拟化（UE-V） 1.0 Service Pack 1 发行说明，请按 Ctrl + F。</span><span class="sxs-lookup"><span data-stu-id="53547-104">To search Microsoft User Experience Virtualization (UE-V) 1.0 Service Pack 1 release notes, press Ctrl+F.</span></span>

<span data-ttu-id="53547-105">在安装 UE-V 之前，应仔细阅读这些发行说明。</span><span class="sxs-lookup"><span data-stu-id="53547-105">You should read these release notes thoroughly before you install UE-V.</span></span> <span data-ttu-id="53547-106">发行说明包含成功安装用户体验虚拟化所需的信息，并包含产品文档中不可用的其他信息。</span><span class="sxs-lookup"><span data-stu-id="53547-106">The release notes contain information that is required to successfully install User Experience Virtualization, and contain additional information that is not available in the product documentation.</span></span> <span data-ttu-id="53547-107">如果这些发行说明和其他 UE-V 文档之间存在差异，则应将最新更改视为权威。</span><span class="sxs-lookup"><span data-stu-id="53547-107">If there are differences between these release notes and other UE-V documentation, the latest change should be considered authoritative.</span></span> <span data-ttu-id="53547-108">这些发行说明取代了本产品附带的内容。</span><span class="sxs-lookup"><span data-stu-id="53547-108">These release notes supersede the content that is included with this product.</span></span>

## <span data-ttu-id="53547-109">UE-V 已知问题</span><span class="sxs-lookup"><span data-stu-id="53547-109">UE-V known issues</span></span>


<span data-ttu-id="53547-110">本部分包含适用于用户体验虚拟化 1.0 SP1 的发行说明。</span><span class="sxs-lookup"><span data-stu-id="53547-110">This section contains release notes for User Experience Virtualization 1.0 SP1.</span></span>

### <span data-ttu-id="53547-111">注册表设置无法在同一台计算机上的 App-v 和本机应用程序之间同步</span><span class="sxs-lookup"><span data-stu-id="53547-111">Registry settings fail to synchronize between App-V and native applications on the same computer</span></span>

<span data-ttu-id="53547-112">当计算机具有通过应用程序虚拟化（app-v）应用程序和随 Windows Installer （.msi 文件）安装的本机安装应用程序提供的应用程序时，基于注册表的设置不会在技术之间同步。</span><span class="sxs-lookup"><span data-stu-id="53547-112">When a computer has an application that is available through both the Application Virtualization (App-V) application and a native installation application installed with a Windows Installer (.msi file), the registry-based settings do not synchronize between the technologies.</span></span>

<span data-ttu-id="53547-113">解决方法：若要解决此问题，请通过选择两种技术之一来运行应用程序，但不能同时选择二者。</span><span class="sxs-lookup"><span data-stu-id="53547-113">WORKAROUND: To resolve this problem, run the application by selecting one of the two technologies, but not both.</span></span>

### <a href="" id="windows-8-setting-synchronization-fails-when-network-share-is-outside-user-s-domain"></a><span data-ttu-id="53547-114">当网络共享位于用户域之外时，Windows 8 设置同步失败</span><span class="sxs-lookup"><span data-stu-id="53547-114">Windows 8 setting synchronization fails when network share is outside user’s domain</span></span>

<span data-ttu-id="53547-115">当 Windows®8尝试运行操作系统设置同步时，synchrnization 失败，并出现以下错误消息：**提升：： filesystem：：存在：：错误的用户名或密码**。</span><span class="sxs-lookup"><span data-stu-id="53547-115">When Windows® 8 attempts operating system settings synchronization, the synchrnization fails with the following error message: **boost::filesystem::exists::Incorrect user name or password**.</span></span> <span data-ttu-id="53547-116">此错误可能表示网络共享位于用户域之外。</span><span class="sxs-lookup"><span data-stu-id="53547-116">This error can indicate that the network share is outside the user’s domain.</span></span> <span data-ttu-id="53547-117">若要检查操作日志事件，请打开**事件查看器**并导航到**应用程序和服务记录**  /  **Microsoft**  /  **用户体验虚拟化**  /  **日志记录**  /  **操作**。</span><span class="sxs-lookup"><span data-stu-id="53547-117">To check for operational log events, open the **Event Viewer** and navigate to **Applications and Services Logs** / **Microsoft** / **User Experience Virtualization** / **Logging** / **Operational**.</span></span> <span data-ttu-id="53547-118">用于 UE-V 设置的网络共享的存储位置应位于与用户相同的 Active Directory 域中。</span><span class="sxs-lookup"><span data-stu-id="53547-118">Network shares that are used for UE-V settings storage locations should reside in the same Active Directory domain as the user.</span></span>

<span data-ttu-id="53547-119">解决方法：使用与用户相同的 Active Directory 域中的网络共享。</span><span class="sxs-lookup"><span data-stu-id="53547-119">WORKAROUND: Use network shares from the same Active Directory domain as the user.</span></span> <span data-ttu-id="53547-120">.</span><span class="sxs-lookup"><span data-stu-id="53547-120">.</span></span>

### <span data-ttu-id="53547-121">Outlook 2010 的电子邮件签名漫游</span><span class="sxs-lookup"><span data-stu-id="53547-121">Email signature roaming for Outlook 2010</span></span>

<span data-ttu-id="53547-122">UE-V 将在设备之间漫游 Outlook 2010 签名文件。</span><span class="sxs-lookup"><span data-stu-id="53547-122">UE-V will roam the Outlook 2010 signature files between devices.</span></span> <span data-ttu-id="53547-123">但是，新邮件和答复/转发的默认签名选项不是漫游。</span><span class="sxs-lookup"><span data-stu-id="53547-123">However, the default signature options for new messages and replies/forwards are not roamed.</span></span> <span data-ttu-id="53547-124">这两个设置存储在 Outlook 配置文件中，而 UE-V 不会漫游。</span><span class="sxs-lookup"><span data-stu-id="53547-124">These two settings are stored in the Outlook profile, which UE-V does not roam.</span></span>

<span data-ttu-id="53547-125">解决方法：无。</span><span class="sxs-lookup"><span data-stu-id="53547-125">WORKAROUND: None.</span></span>

### <span data-ttu-id="53547-126">在慢速链接模式下运行时，同步设置不会按预期的间隔同步</span><span class="sxs-lookup"><span data-stu-id="53547-126">Synchronization settings do not synchronize on expected interval when running in slow-link mode</span></span>

<span data-ttu-id="53547-127">在 "正常情况下，设置存储位置" 应在快速链接网络连接上可用。</span><span class="sxs-lookup"><span data-stu-id="53547-127">Under normal conditions, settings storage locations should be available over a fast link network connection.</span></span> <span data-ttu-id="53547-128">在慢速链接模式下，同步只会定期发生。</span><span class="sxs-lookup"><span data-stu-id="53547-128">In slow-link mode, synchronization will only occur on a periodic basis.</span></span> <span data-ttu-id="53547-129">默认情况下，慢速链接模式同步计划将设置为每360分钟。</span><span class="sxs-lookup"><span data-stu-id="53547-129">By default, the slow-link mode synchronization schedule is set to every 360 minutes.</span></span>

<span data-ttu-id="53547-130">解决方法：若要在慢速链接模式下更改计算机的后台同步的频率，可以为**脱机文件**配置后台同步策略的组策略。</span><span class="sxs-lookup"><span data-stu-id="53547-130">WORKAROUND: To change the frequency of the background synchronization for computers in slow-link mode, you can configure the Group Policy for Background Sync policy for **Offline files**.</span></span>

### <span data-ttu-id="53547-131">特殊字符不同步</span><span class="sxs-lookup"><span data-stu-id="53547-131">Special characters do not synchronize</span></span>

<span data-ttu-id="53547-132">某些字符（如货币符号）不在运行 UE-V agent 的 Windows 7 和 Windows 8 计算机之间同步。</span><span class="sxs-lookup"><span data-stu-id="53547-132">Certain characters, such as currency symbols, do not synchronize between Windows 7 and Windows 8 computers that run the UE-V agent.</span></span>

<span data-ttu-id="53547-133">解决方法：无。</span><span class="sxs-lookup"><span data-stu-id="53547-133">WORKAROUND: None.</span></span>

### <span data-ttu-id="53547-134">UE-V 不支持32位和64位版本的 Microsoft Office 之间的漫游设置</span><span class="sxs-lookup"><span data-stu-id="53547-134">UE-V does not support roaming settings between 32-bit and 64-bit versions of Microsoft Office</span></span>

<span data-ttu-id="53547-135">我们建议你为32位和64位操作系统安装32位版本的 Microsoft Office。</span><span class="sxs-lookup"><span data-stu-id="53547-135">We recommend that you install the 32-bit version of Microsoft Office for both 32-bit and 64-bit operating systems.</span></span> <span data-ttu-id="53547-136">若要选择所需的 Microsoft Office 版本，请单击 "此处" （ [http://office.microsoft.com/word-help/choose-the-32-bit-or-64-bit-version-of-microsoft-office-HA010369476.aspx](https://go.microsoft.com/fwlink/?LinkID=247623) ）。</span><span class="sxs-lookup"><span data-stu-id="53547-136">To choose the Microsoft Office version that you need, click here ([http://office.microsoft.com/word-help/choose-the-32-bit-or-64-bit-version-of-microsoft-office-HA010369476.aspx](https://go.microsoft.com/fwlink/?LinkID=247623)).</span></span> <span data-ttu-id="53547-137">UE-V 支持 Office 的相同体系结构版本之间的漫游设置。</span><span class="sxs-lookup"><span data-stu-id="53547-137">UE-V supports roaming settings between identical architecture versions of Office.</span></span> <span data-ttu-id="53547-138">例如，32位 Office 设置将在所有32位 Office 实例之间漫游。</span><span class="sxs-lookup"><span data-stu-id="53547-138">For example, 32-bit Office settings will roam between all 32-bit Office instances.</span></span> <span data-ttu-id="53547-139">UE-V 不支持32位和64位版本的 Office 之间的漫游设置。</span><span class="sxs-lookup"><span data-stu-id="53547-139">UE-V does not support roaming settings between 32-bit and 64-bit versions of Office.</span></span>

<span data-ttu-id="53547-140">解决方法：无</span><span class="sxs-lookup"><span data-stu-id="53547-140">WORKAROUND: None</span></span>

### <a href="" id="msi-s-are-not-localized"></a><span data-ttu-id="53547-141">MSI 未本地化</span><span class="sxs-lookup"><span data-stu-id="53547-141">MSI’s are not localized</span></span>

<span data-ttu-id="53547-142">UE-V 1.0 SP1 包括用于 UE-V Agent 和 UE-V 发生器的本地化设置程序。</span><span class="sxs-lookup"><span data-stu-id="53547-142">UE-V 1.0 SP1 includes a localized setup program for both the UE-V Agent and UE-V generator.</span></span> <span data-ttu-id="53547-143">这些 MSI 文件仍然可用，但用户界面已最小化，并且 MSI 仅以英语显示。</span><span class="sxs-lookup"><span data-stu-id="53547-143">These MSI files are still available but the user interface is minimized and the MSI’s only display in English.</span></span> <span data-ttu-id="53547-144">尽管文件是英语，安装程序也会在安装期间安装所有支持的语言。</span><span class="sxs-lookup"><span data-stu-id="53547-144">Despite the file being in English, the setup program installs all supported languages during the installation.</span></span>

<span data-ttu-id="53547-145">解决方法：无</span><span class="sxs-lookup"><span data-stu-id="53547-145">WORKAROUND: None</span></span>

### <span data-ttu-id="53547-146">具有设置存储位置的共享上的其他文件夹在慢速连接模式下不可用</span><span class="sxs-lookup"><span data-stu-id="53547-146">Other folders on the share with the setting storage location are unavailable in slow-connection mode</span></span>

<span data-ttu-id="53547-147">设置存储共享不应位于用于其他必须始终可用的文件夹的网络共享上。</span><span class="sxs-lookup"><span data-stu-id="53547-147">Settings store shares should not be located on a network share that is used for other folders that must always be available.</span></span> <span data-ttu-id="53547-148">当托管设置存储位置的网络共享进入慢速连接模式时，唯一可用的文件夹是 "设置存储位置" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="53547-148">When the network share that hosts the setting storage location goes into slow-connection mode, the only available folder is the settings storage location folder.</span></span> <span data-ttu-id="53547-149">共享上的其他文件夹在慢速连接模式下不可用。</span><span class="sxs-lookup"><span data-stu-id="53547-149">Other folders on the Share are not available in slow-connection mode.</span></span>

<span data-ttu-id="53547-150">解决方法：无</span><span class="sxs-lookup"><span data-stu-id="53547-150">Workaround: None</span></span>

### <span data-ttu-id="53547-151">与 Internet Explorer 9 收藏夹相关联的 Favicons 不漫游</span><span class="sxs-lookup"><span data-stu-id="53547-151">Favicons that are associated with Internet Explorer 9 favorites do not roam</span></span>

<span data-ttu-id="53547-152">与 Internet Explorer 9 常用联系人相关联的 favicons 不是由用户体验虚拟化漫游的，并且在新计算机上首次显示收藏时不会显示。</span><span class="sxs-lookup"><span data-stu-id="53547-152">The favicons that are associated with Internet Explorer 9 favorites are not roamed by User Experience Virtualization and do not appear when the favorites first appear on a new computer.</span></span>

<span data-ttu-id="53547-153">解决方法：在 Internet Explorer 9 浏览器中使用并缓存书签后，Favicons 将显示相关联的常用联系人。</span><span class="sxs-lookup"><span data-stu-id="53547-153">WORKAROUND: Favicons will appear with their associated favorites once the bookmark is used and cached in the Internet Explorer 9 browser.</span></span>

### <span data-ttu-id="53547-154">文件设置路径存储在注册表中</span><span class="sxs-lookup"><span data-stu-id="53547-154">File settings paths are stored in registry</span></span>

<span data-ttu-id="53547-155">某些应用程序设置将其配置和设置文件的路径存储为注册表中的值。</span><span class="sxs-lookup"><span data-stu-id="53547-155">Some application settings store the paths of their configuration and settings files as values in the registry.</span></span> <span data-ttu-id="53547-156">当设置在计算机之间漫游时，必须同步在注册表中作为路径引用的文件。</span><span class="sxs-lookup"><span data-stu-id="53547-156">The files that are referenced as paths in the registry must be synchronized when settings are roamed between computers.</span></span>

<span data-ttu-id="53547-157">解决方法：使用 "文件夹重定向" 或其他技术确保作为文件设置路径引用的所有文件都存在并放置在 "设置" 漫游的所有计算机上的相同位置。</span><span class="sxs-lookup"><span data-stu-id="53547-157">WORKAROUND: Use folder redirection or some other technology to ensure that any files that are referenced as file settings paths are present and placed in the same location on all computers where settings roam.</span></span>

### <span data-ttu-id="53547-158">较长设置存储路径可能会导致错误</span><span class="sxs-lookup"><span data-stu-id="53547-158">Long Settings Storage Paths could cause an error</span></span>

<span data-ttu-id="53547-159">使设置存储路径尽可能简短。</span><span class="sxs-lookup"><span data-stu-id="53547-159">Keep settings storage paths as short as possible.</span></span> <span data-ttu-id="53547-160">长路径可能会阻止分辨率或同步。</span><span class="sxs-lookup"><span data-stu-id="53547-160">Long paths could prevent resolution or synchronization.</span></span> <span data-ttu-id="53547-161">UE-V 使用设置存储路径作为存储设置的计算路径的一部分。</span><span class="sxs-lookup"><span data-stu-id="53547-161">UE-V uses the Settings storage path as part of the calculated path to store settings.</span></span> <span data-ttu-id="53547-162">该路径按以下方式计算：设置存储路径 + "settingspackages" + 程序包目录（模板 ID） + 软件包名称（模板 ID）。</span><span class="sxs-lookup"><span data-stu-id="53547-162">That path is calculated in the following way: settings storage path + “settingspackages” + package dir (template ID) + package name (template ID).</span></span> <span data-ttu-id="53547-163">如果该计算路径超过260个字符，则软件包存储将失败，并在 UE-V 操作事件日志中生成以下错误消息：</span><span class="sxs-lookup"><span data-stu-id="53547-163">If that calculated path exceeds 260 characters, package storage will fail and generate the following error message in the UE-V operational event log:</span></span>

`[boost::filesystem::copy_file: The system cannot find the path specified]`

<span data-ttu-id="53547-164">若要检查操作日志事件，请打开事件查看器并导航到 "应用程序和服务日志/Microsoft/用户体验虚拟化/登录/运行"。</span><span class="sxs-lookup"><span data-stu-id="53547-164">To check the operational log events, open the Event Viewer and navigate to Applications and Services Logs / Microsoft / User Experience Virtualization / Logging / Operational.</span></span>

<span data-ttu-id="53547-165">解决方法：无。</span><span class="sxs-lookup"><span data-stu-id="53547-165">WORKAROUND: None.</span></span>

### <span data-ttu-id="53547-166">UE-V agent 在注销或登录时延迟</span><span class="sxs-lookup"><span data-stu-id="53547-166">UE-V agent delays upon logout or login</span></span>

<span data-ttu-id="53547-167">如果在 "脱机文件" 确定较慢的链接已到位之前发生登录或注销，则可能会延迟注销或登录。</span><span class="sxs-lookup"><span data-stu-id="53547-167">If a logon or logout occurs before Offline Files has determined that a slow link is in place, logout or login might be delayed.</span></span> <span data-ttu-id="53547-168">"脱机文件" 功能可能需要长达三分钟才能检测当前的网络状态。</span><span class="sxs-lookup"><span data-stu-id="53547-168">The Offline Files feature may take up to three minutes to detect the current network state.</span></span> <span data-ttu-id="53547-169">如果在脱机文件确定计算机连接到慢速链接之前发生登录或关机，则 UE-V 设置程序包将发送到服务器而不是本地缓存。</span><span class="sxs-lookup"><span data-stu-id="53547-169">If the logon or shutdown occurs before Offline Files has determined that the computer is connected to a slow link, the UE-V settings package will be sent to the server instead of the local cache.</span></span>

<span data-ttu-id="53547-170">解决方法：无。</span><span class="sxs-lookup"><span data-stu-id="53547-170">WORKAROUND: None.</span></span>

### <span data-ttu-id="53547-171">尝试在 Windows 8 上漫游操作系统设置时出现设置冲突</span><span class="sxs-lookup"><span data-stu-id="53547-171">Settings conflict when trying to roam operating system settings on Windows 8</span></span>

<span data-ttu-id="53547-172">在 Windows 8 上，如果已启用 Microsoft 帐户同步以及操作系统设置的 UE-V，则应用的设置可能不一致。</span><span class="sxs-lookup"><span data-stu-id="53547-172">On Windows 8 if Microsoft Account Sync is enabled along with UE-V for operating system settings, the settings that are applied may be inconsistent.</span></span>

<span data-ttu-id="53547-173">解决方法：执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="53547-173">WORKAROUND: Do one of the following:</span></span>

-   <span data-ttu-id="53547-174">如果你使用 UE-V 漫游操作系统设置，则禁用 Microsoft 帐户同步</span><span class="sxs-lookup"><span data-stu-id="53547-174">Disable Microsoft Account Sync if you are using UE-V to roam operating system settings</span></span>

-   <span data-ttu-id="53547-175">禁用操作系统设置的 UE-V</span><span class="sxs-lookup"><span data-stu-id="53547-175">Disable UE-V for operating system settings</span></span>

### <span data-ttu-id="53547-176">某些操作系统设置仅在类似操作系统版本之间漫游</span><span class="sxs-lookup"><span data-stu-id="53547-176">Some operating system settings only roam between like operating system versions</span></span>

<span data-ttu-id="53547-177">面向讲述人的操作系统设置和特定于区域设置的货币字符将仅在 Windows 的操作系统版本上漫游。</span><span class="sxs-lookup"><span data-stu-id="53547-177">Operating system settings for Narrator and currency characters specific to the locale will only roam across like operating system versions of Windows.</span></span> <span data-ttu-id="53547-178">例如，货币字符将仅从 Windows 7 漫游到 Windows 7。</span><span class="sxs-lookup"><span data-stu-id="53547-178">For example currency characters will only roam from Windows 7 to Windows 7.</span></span>

<span data-ttu-id="53547-179">解决方法：无</span><span class="sxs-lookup"><span data-stu-id="53547-179">WORKAROUND: None</span></span>

 

 





