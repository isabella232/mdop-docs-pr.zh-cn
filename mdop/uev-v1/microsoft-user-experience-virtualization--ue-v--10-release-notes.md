---
title: Microsoft 用户体验虚拟化 (UE-V) 1.0 发行说明
description: Microsoft 用户体验虚拟化 (UE-V) 1.0 发行说明
author: dansimp
ms.assetid: 920f3fae-e9b5-4b94-beda-32c19d31e94b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 9f9942eef7ea84cf7010a0c0173427827a512216
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798058"
---
# <span data-ttu-id="7701d-103">Microsoft 用户体验虚拟化 (UE-V) 1.0 发行说明</span><span class="sxs-lookup"><span data-stu-id="7701d-103">Microsoft User Experience Virtualization (UE-V) 1.0 Release Notes</span></span>


<span data-ttu-id="7701d-104">若要搜索 Microsoft 用户体验虚拟化（UE-V）发行说明，请按 Ctrl + F。</span><span class="sxs-lookup"><span data-stu-id="7701d-104">To search Microsoft User Experience Virtualization (UE-V) release notes, press Ctrl+F.</span></span>

<span data-ttu-id="7701d-105">在安装 UE-V 之前，应仔细阅读这些发行说明。</span><span class="sxs-lookup"><span data-stu-id="7701d-105">You should read these release notes thoroughly before you install UE-V.</span></span> <span data-ttu-id="7701d-106">发行说明包含成功安装用户体验虚拟化所需的信息，并包含产品文档中不可用的其他信息。</span><span class="sxs-lookup"><span data-stu-id="7701d-106">The release notes contain information that is required to successfully install User Experience Virtualization, and contain additional information that is not available in the product documentation.</span></span> <span data-ttu-id="7701d-107">如果这些发行说明和其他 UE-V 文档之间存在差异，则应将最新更改视为权威。</span><span class="sxs-lookup"><span data-stu-id="7701d-107">If there are differences between these release notes and other UE-V documentation, the latest change should be considered authoritative.</span></span> <span data-ttu-id="7701d-108">这些发行说明取代了本产品附带的内容。</span><span class="sxs-lookup"><span data-stu-id="7701d-108">These release notes supersede the content that is included with this product.</span></span>

## <span data-ttu-id="7701d-109">提供反馈</span><span class="sxs-lookup"><span data-stu-id="7701d-109">Providing feedback</span></span>


<span data-ttu-id="7701d-110">通过向我们提供反馈和评论，告诉我们您对 MDOP 文档的看法。</span><span class="sxs-lookup"><span data-stu-id="7701d-110">Tell us what you think about our documentation for MDOP by giving us your feedback and comments.</span></span> <span data-ttu-id="7701d-111">将文档反馈发送到[mdopdocs@microsoft.com](mailto:mdopdocs@microsoft.com?subject=UE-V%20Documentation)。</span><span class="sxs-lookup"><span data-stu-id="7701d-111">Send your documentation feedback to [mdopdocs@microsoft.com](mailto:mdopdocs@microsoft.com?subject=UE-V%20Documentation).</span></span>

## <span data-ttu-id="7701d-112">UE-V 已知问题</span><span class="sxs-lookup"><span data-stu-id="7701d-112">UE-V known issues</span></span>


<span data-ttu-id="7701d-113">本部分包含适用于用户体验虚拟化的发行说明。</span><span class="sxs-lookup"><span data-stu-id="7701d-113">This section contains release notes for User Experience Virtualization.</span></span>

### <span data-ttu-id="7701d-114">注册表设置无法在同一台计算机上的 App-v 和本机应用程序之间同步</span><span class="sxs-lookup"><span data-stu-id="7701d-114">Registry settings fail to synchronize between App-V and native applications on the same computer</span></span>

<span data-ttu-id="7701d-115">当计算机具有通过应用程序虚拟化（app-v）应用程序和本机安装应用程序（使用 .msi 文件安装）提供的应用程序时，基于注册表的设置不会在技术之间同步。</span><span class="sxs-lookup"><span data-stu-id="7701d-115">When a computer has an application that is available through both the Application Virtualization (App-V) application and a native installation application (installed with an .msi file), the registry-based settings do not synchronize between the technologies.</span></span>

<span data-ttu-id="7701d-116">解决方法：若要解决此问题，请通过选择两种技术之一来运行应用程序，但不能同时选择二者。</span><span class="sxs-lookup"><span data-stu-id="7701d-116">WORKAROUND: To resolve this problem, run the application by selecting one of the two technologies, but not both.</span></span>

### <span data-ttu-id="7701d-117">Windows 8 设置同步失败，出现错误： "增强：： filesystem：： exists：：不正确的用户名或密码"</span><span class="sxs-lookup"><span data-stu-id="7701d-117">Windows 8 setting synchronization fails with error: "boost::filesystem::exists::Incorrect user name or password"</span></span>

<span data-ttu-id="7701d-118">Windows®8操作系统设置同步失败，并出现以下错误消息：**提升：： filesystem：：存在：：不正确的用户名或密码**。</span><span class="sxs-lookup"><span data-stu-id="7701d-118">The Windows® 8 operating system settings synchronization fails with the following error message: **boost::filesystem::exists::Incorrect user name or password**.</span></span> <span data-ttu-id="7701d-119">若要检查操作日志事件，请打开**事件查看器**并导航到**应用程序和服务记录**  /  **Microsoft**  /  **用户体验虚拟化**  /  **日志记录**  /  **操作**。</span><span class="sxs-lookup"><span data-stu-id="7701d-119">To check for operational log events, open the **Event Viewer** and navigate to **Applications and Services Logs** / **Microsoft** / **User Experience Virtualization** / **Logging** / **Operational**.</span></span> <span data-ttu-id="7701d-120">用于 UE-V 设置的网络共享的存储位置应位于与用户相同的 Active Directory 域中。</span><span class="sxs-lookup"><span data-stu-id="7701d-120">Network shares that are used for UE-V settings storage locations should reside in the same Active Directory domain as the user.</span></span> <span data-ttu-id="7701d-121">否则，可能会出现以下错误： "用户名或密码不正确"。</span><span class="sxs-lookup"><span data-stu-id="7701d-121">Otherwise, the following error might occur: "Incorrect user name or password".</span></span>

<span data-ttu-id="7701d-122">解决方法：使用与用户相同的 Active Directory 域中的网络共享。</span><span class="sxs-lookup"><span data-stu-id="7701d-122">WORKAROUND: Use network shares from the same Active Directory domain as the user.</span></span> <span data-ttu-id="7701d-123">.</span><span class="sxs-lookup"><span data-stu-id="7701d-123">.</span></span>

### <span data-ttu-id="7701d-124">Outlook 2010 的电子邮件签名漫游</span><span class="sxs-lookup"><span data-stu-id="7701d-124">Email signature roaming for Outlook 2010</span></span>

<span data-ttu-id="7701d-125">UE-V 将在设备之间漫游 Outlook 2010 签名文件。</span><span class="sxs-lookup"><span data-stu-id="7701d-125">UE-V will roam the Outlook 2010 signature files between devices.</span></span> <span data-ttu-id="7701d-126">但是，新邮件和答复/转发的默认签名选项不是。</span><span class="sxs-lookup"><span data-stu-id="7701d-126">However, the default signature options for new messages and replies/forwards are not.</span></span><span data-ttu-id="7701d-127">这两个设置存储在 Outlook 配置文件中，Vdoes 不漫游。</span><span class="sxs-lookup"><span data-stu-id="7701d-127"> These two settings are stored in the Outlook profile, which UE-Vdoes not roam.</span></span>

<span data-ttu-id="7701d-128">解决方法：无。</span><span class="sxs-lookup"><span data-stu-id="7701d-128">WORKAROUND: None.</span></span>

### <span data-ttu-id="7701d-129">在慢速链接模式下运行时，同步设置不会按预期的间隔同步</span><span class="sxs-lookup"><span data-stu-id="7701d-129">Synchronization settings do not synchronize on expected interval when running in slow-link mode</span></span>

<span data-ttu-id="7701d-130">在 "正常情况下，设置存储位置" 应在快速链接网络连接上可用。</span><span class="sxs-lookup"><span data-stu-id="7701d-130">Under normal conditions, settings storage locations should be available over a fast link network connection.</span></span> <span data-ttu-id="7701d-131">在慢速链接模式下，同步只会定期发生。</span><span class="sxs-lookup"><span data-stu-id="7701d-131">In slow-link mode, synchronization will only occur on a periodic basis.</span></span> <span data-ttu-id="7701d-132">默认情况下，慢速链接模式同步计划将设置为每360分钟。</span><span class="sxs-lookup"><span data-stu-id="7701d-132">By default, the slow-link mode synchronization schedule is set to every 360 minutes.</span></span>

<span data-ttu-id="7701d-133">解决方法：若要在慢速链接模式下更改计算机的后台同步的频率，可以为**脱机文件**配置后台同步策略的组策略。</span><span class="sxs-lookup"><span data-stu-id="7701d-133">WORKAROUND: To change the frequency of the background synchronization for computers in slow-link mode, you can configure the Group Policy for Background Sync policy for **Offline files**.</span></span>

### <span data-ttu-id="7701d-134">特殊字符不同步</span><span class="sxs-lookup"><span data-stu-id="7701d-134">Special characters do not synchronize</span></span>

<span data-ttu-id="7701d-135">某些字符（如货币符号）不在运行 UE-V agent 的 Windows 7 和 Windows 8 计算机之间同步。</span><span class="sxs-lookup"><span data-stu-id="7701d-135">Certain characters, such as currency symbols, do not synchronize between Windows 7 and Windows 8 computers that run the UE-V agent.</span></span>

<span data-ttu-id="7701d-136">解决方法：无。</span><span class="sxs-lookup"><span data-stu-id="7701d-136">WORKAROUND: None.</span></span>

### <span data-ttu-id="7701d-137">UE-V 不支持32位和64位版本的 Microsoft Office 之间的漫游设置</span><span class="sxs-lookup"><span data-stu-id="7701d-137">UE-V does not support roaming settings between 32-bit and 64-bit versions of Microsoft Office</span></span>

<span data-ttu-id="7701d-138">我们建议你为32位和64位操作系统安装32位版本的 Microsoft Office。</span><span class="sxs-lookup"><span data-stu-id="7701d-138">We recommend that you install the 32-bit version of Microsoft Office for both 32-bit and 64-bit operating systems.</span></span> <span data-ttu-id="7701d-139">若要选择所需的 Microsoft Office 版本，请单击此处。</span><span class="sxs-lookup"><span data-stu-id="7701d-139">To choose the Microsoft Office version that you need, click here.</span></span> <span data-ttu-id="7701d-140">([http://office.microsoft.com/word-help/choose-the-32-bit-or-64-bit-version-of-microsoft-office-HA010369476.aspx](https://go.microsoft.com/fwlink/?LinkID=247623)).</span><span class="sxs-lookup"><span data-stu-id="7701d-140">([http://office.microsoft.com/word-help/choose-the-32-bit-or-64-bit-version-of-microsoft-office-HA010369476.aspx](https://go.microsoft.com/fwlink/?LinkID=247623)).</span></span> <span data-ttu-id="7701d-141">UE-V 支持 Office 的相同体系结构版本之间的漫游设置。</span><span class="sxs-lookup"><span data-stu-id="7701d-141">UE-V supports roaming settings between identical architecture versions of Office.</span></span> <span data-ttu-id="7701d-142">例如，32位 Office 设置将在所有32位 Office 实例之间漫游。</span><span class="sxs-lookup"><span data-stu-id="7701d-142">For example, 32-bit Office settings will roam between all 32-bit Office instances.</span></span> <span data-ttu-id="7701d-143">UE-V 不支持32位和64位版本的 Office 之间的漫游设置。</span><span class="sxs-lookup"><span data-stu-id="7701d-143">UE-V does not support roaming settings between 32-bit and 64-bit versions of Office.</span></span>

<span data-ttu-id="7701d-144">解决方法：无</span><span class="sxs-lookup"><span data-stu-id="7701d-144">WORKAROUND: None</span></span>

### <span data-ttu-id="7701d-145">具有设置存储位置的共享上的其他文件夹在慢速连接模式下不可用</span><span class="sxs-lookup"><span data-stu-id="7701d-145">Other folders on the share with the setting storage location are unavailable in slow-connection mode</span></span>

<span data-ttu-id="7701d-146">设置存储共享不应位于用于其他必须始终可用的文件夹的网络共享上。</span><span class="sxs-lookup"><span data-stu-id="7701d-146">Settings store shares should not be located on a network share that is used for other folders that must always be available.</span></span> <span data-ttu-id="7701d-147">当托管设置存储位置的网络共享进入慢速连接模式时，唯一可用的文件夹是 "设置存储位置" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="7701d-147">When the network share that hosts the setting storage location goes into slow-connection mode, the only available folder is the settings storage location folder.</span></span> <span data-ttu-id="7701d-148">共享上的其他文件夹在慢速连接模式下不可用。</span><span class="sxs-lookup"><span data-stu-id="7701d-148">Other folders on the Share are not available in slow-connection mode.</span></span>

<span data-ttu-id="7701d-149">解决方法：无</span><span class="sxs-lookup"><span data-stu-id="7701d-149">Workaround: None</span></span>

### <span data-ttu-id="7701d-150">与 Internet Explorer 9 收藏夹相关联的 Favicons 不漫游</span><span class="sxs-lookup"><span data-stu-id="7701d-150">Favicons that are associated with Internet Explorer 9 favorites do not roam</span></span>

<span data-ttu-id="7701d-151">与 Internet Explorer 9 常用联系人相关联的 favicons 不是由用户体验虚拟化漫游的，并且在新计算机上首次显示收藏时不会显示。</span><span class="sxs-lookup"><span data-stu-id="7701d-151">The favicons that are associated with Internet Explorer 9 favorites are not roamed by User Experience Virtualization and do not appear when the favorites first appear on a new computer.</span></span>

<span data-ttu-id="7701d-152">解决方法：在 Internet Explorer 9 浏览器中使用并缓存书签后，Favicons 将显示相关联的常用联系人。</span><span class="sxs-lookup"><span data-stu-id="7701d-152">WORKAROUND: Favicons will appear with their associated favorites once the bookmark is used and cached in the Internet Explorer 9 browser.</span></span>

### <span data-ttu-id="7701d-153">文件设置路径存储在注册表中</span><span class="sxs-lookup"><span data-stu-id="7701d-153">File settings paths are stored in registry</span></span>

<span data-ttu-id="7701d-154">某些应用程序设置将其配置和设置文件的路径存储为注册表中的值。</span><span class="sxs-lookup"><span data-stu-id="7701d-154">Some application settings store the paths of their configuration and settings files as values in the registry.</span></span> <span data-ttu-id="7701d-155">当设置在计算机之间漫游时，必须同步在注册表中作为路径引用的文件。</span><span class="sxs-lookup"><span data-stu-id="7701d-155">The files that are referenced as paths in the registry must be synchronized when settings are roamed between computers.</span></span>

<span data-ttu-id="7701d-156">解决方法：使用 "文件夹重定向" 或其他技术确保作为文件设置路径引用的所有文件都存在并放置在 "设置" 漫游的所有计算机上的相同位置。</span><span class="sxs-lookup"><span data-stu-id="7701d-156">WORKAROUND: Use folder redirection or some other technology to ensure that any files that are referenced as file settings paths are present and placed in the same location on all computers where settings roam.</span></span>

### <span data-ttu-id="7701d-157">不支持长度超过260个字符的路径</span><span class="sxs-lookup"><span data-stu-id="7701d-157">Paths longer than 260 characters are not supported</span></span>

<span data-ttu-id="7701d-158">不支持超过260个字符的设置存储路径。</span><span class="sxs-lookup"><span data-stu-id="7701d-158">Settings storage paths that are longer than 260 characters are not supported.</span></span> <span data-ttu-id="7701d-159">将 UE-V 设置程序包复制到设置超过260个字符的存储路径将失败，并且在 UE-V 操作事件日志中生成以下异常消息： **\ [增强：： filesystem：：复制 \ _file：系统找不到指定的路径 \]**。</span><span class="sxs-lookup"><span data-stu-id="7701d-159">Copying the UE-V settings packages to settings storage paths that are longer than 260 characters will fail and generate the following exception message in the UE-V operational event log: **\[boost::filesystem::copy\_file: The system cannot find the path specified\]**.</span></span> <span data-ttu-id="7701d-160">若要检查操作日志事件，请打开**事件查看器**并导航到**应用程序和服务记录**  /  **Microsoft**  /  **用户体验虚拟化**  /  **日志记录**  /  **操作**。</span><span class="sxs-lookup"><span data-stu-id="7701d-160">To check for operational log events, open the **Event Viewer** and navigate to **Applications and Services Logs** / **Microsoft** / **User Experience Virtualization** / **Logging** / **Operational**.</span></span>

<span data-ttu-id="7701d-161">当前不支持超过260个字符的文件设置路径。</span><span class="sxs-lookup"><span data-stu-id="7701d-161">File settings paths that are longer than 260 characters are not currently supported.</span></span> <span data-ttu-id="7701d-162">在 UE-V 设置位置模板中引用的文件设置不能位于超过260个字符的目录路径中。</span><span class="sxs-lookup"><span data-stu-id="7701d-162">File settings that are referenced in UE-V settings location templates cannot be located in a directory path that is longer than 260 characters.</span></span>

<span data-ttu-id="7701d-163">解决方法：无。</span><span class="sxs-lookup"><span data-stu-id="7701d-163">WORKAROUND: None.</span></span>

### <span data-ttu-id="7701d-164">UE-V agent 在注销或登录时延迟</span><span class="sxs-lookup"><span data-stu-id="7701d-164">UE-V agent delays upon logout or login</span></span>

<span data-ttu-id="7701d-165">如果在 "脱机文件" 确定较慢的链接已到位之前发生登录或注销，则可能会延迟注销或登录。</span><span class="sxs-lookup"><span data-stu-id="7701d-165">If a logon or logout occurs before Offline Files has determined that a slow link is in place, logout or login might be delayed.</span></span> <span data-ttu-id="7701d-166">"脱机文件" 功能可能需要长达三分钟才能检测当前的网络状态。</span><span class="sxs-lookup"><span data-stu-id="7701d-166">The Offline Files feature may take up to three minutes to detect the current network state.</span></span> <span data-ttu-id="7701d-167">如果在脱机文件确定计算机连接到慢速链接之前发生登录或关机，则 UE-V 设置程序包将发送到服务器而不是本地缓存。</span><span class="sxs-lookup"><span data-stu-id="7701d-167">If the logon or shutdown occurs before Offline Files has determined that the computer is connected to a slow link, the UE-V settings package will be sent to the server instead of the local cache.</span></span>

<span data-ttu-id="7701d-168">解决方法：无。</span><span class="sxs-lookup"><span data-stu-id="7701d-168">WORKAROUND: None.</span></span>

### <span data-ttu-id="7701d-169">尝试在 Windows 8 上漫游操作系统设置时出现设置冲突</span><span class="sxs-lookup"><span data-stu-id="7701d-169">Settings conflict when trying to roam operating system settings on Windows 8</span></span>

<span data-ttu-id="7701d-170">在 Windows 8 上，如果已启用 Microsoft 帐户同步以及操作系统设置的 UE-V，则应用的设置可能不一致。</span><span class="sxs-lookup"><span data-stu-id="7701d-170">On Windows 8 if Microsoft Account Sync is enabled along with UE-V for operating system settings, the settings that are applied may be inconsistent.</span></span>

<span data-ttu-id="7701d-171">解决方法：执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="7701d-171">WORKAROUND: Do one of the following:</span></span>

-   <span data-ttu-id="7701d-172">如果你使用 UE-V 漫游操作系统设置，则禁用 Microsoft 帐户同步</span><span class="sxs-lookup"><span data-stu-id="7701d-172">Disable Microsoft Account Sync if you are using UE-V to roam operating system settings</span></span>

-   <span data-ttu-id="7701d-173">禁用操作系统设置的 UE-V</span><span class="sxs-lookup"><span data-stu-id="7701d-173">Disable UE-V for operating system settings</span></span>

### <span data-ttu-id="7701d-174">某些操作系统设置仅在类似操作系统版本之间漫游</span><span class="sxs-lookup"><span data-stu-id="7701d-174">Some operating system settings only roam between like operating system versions</span></span>

<span data-ttu-id="7701d-175">面向讲述人的操作系统设置和特定于区域设置的货币字符将仅在 Windows 的操作系统版本上漫游。</span><span class="sxs-lookup"><span data-stu-id="7701d-175">Operating system settings for Narrator and currency characters specific to the locale will only roam across like operating system versions of Windows.</span></span> <span data-ttu-id="7701d-176">例如，货币字符将仅从 Windows 7 漫游到 Windows 7。</span><span class="sxs-lookup"><span data-stu-id="7701d-176">For example currency characters will only roam from Windows 7 to Windows 7.</span></span>

<span data-ttu-id="7701d-177">解决方法：无</span><span class="sxs-lookup"><span data-stu-id="7701d-177">WORKAROUND: None</span></span>

### <span data-ttu-id="7701d-178">Internet Explorer 书签不会显示在 Internet Explorer smartbar 中。</span><span class="sxs-lookup"><span data-stu-id="7701d-178">Internet Explorer bookmarks do not appear in the Internet Explorer smartbar</span></span>

<span data-ttu-id="7701d-179">当 Internet Explorer 书签从一台计算机漫游到另一台计算机时，第二台计算机上的索引无法更新，因此当在地址栏中键入内容时，收藏将不会在计算机2上显示为可能的搜索结果。</span><span class="sxs-lookup"><span data-stu-id="7701d-179">When Internet Explorer bookmarks roam from one computer to another computer, the index on the second computer cannot update, so when typing in the address bar, the favorite will not appear as a possible search result on computer 2.</span></span>

<span data-ttu-id="7701d-180">解决方法：无</span><span class="sxs-lookup"><span data-stu-id="7701d-180">WORKAROUND: None</span></span>

 

 





