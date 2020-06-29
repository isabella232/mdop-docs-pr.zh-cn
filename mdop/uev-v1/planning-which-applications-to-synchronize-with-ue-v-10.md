---
title: 规划要使用 UE-V 1.0 同步的应用程序
description: 规划要使用 UE-V 1.0 同步的应用程序
author: dansimp
ms.assetid: c718274f-87b4-47f3-8ef7-5e1bd5557a9d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7f2b04942588d0f6efad03d5e0249534cd325c09
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798040"
---
# <span data-ttu-id="b416a-103">规划要使用 UE-V 1.0 同步的应用程序</span><span class="sxs-lookup"><span data-stu-id="b416a-103">Planning Which Applications to Synchronize with UE-V 1.0</span></span>


<span data-ttu-id="b416a-104">Microsoft 用户体验虚拟化（UE-V）使用设置位置模板（XML 文件），这些模板定义由 UE-V 捕获和应用的设置。</span><span class="sxs-lookup"><span data-stu-id="b416a-104">Microsoft User Experience Virtualization (UE-V) uses settings location templates (XML files) that define the settings that are captured and applied by UE-V.</span></span> <span data-ttu-id="b416a-105">UE-V 包含一组预定义的设置位置模板，还允许管理员为企业中使用的第三方或业务线应用程序创建自定义设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="b416a-105">UE-V includes a set of predefined settings location templates and also allows administrators to create custom settings location templates for third-party or line-of-business applications that are used in the enterprise.</span></span>

<span data-ttu-id="b416a-106">作为管理员，当你考虑要包含在 UE-V 解决方案中的应用程序时，请考虑哪些设置可以由用户自定义，以及应用程序存储其设置的方式和位置。</span><span class="sxs-lookup"><span data-stu-id="b416a-106">As an administrator, when you consider which applications to include in your UE-V solution, consider which settings can be customized by users, and how and where the application stores its settings.</span></span> <span data-ttu-id="b416a-107">并非所有应用程序都具有可自定义或经常由用户自定义的设置。</span><span class="sxs-lookup"><span data-stu-id="b416a-107">Not all applications have settings that can be customized or that are routinely customized by users.</span></span> <span data-ttu-id="b416a-108">此外，并非所有应用程序设置都可以在多台计算机或环境中安全地漫游。</span><span class="sxs-lookup"><span data-stu-id="b416a-108">In addition, not all applications settings can safely roam across multiple computers or environments.</span></span> <span data-ttu-id="b416a-109">同步满足以下条件的设置：</span><span class="sxs-lookup"><span data-stu-id="b416a-109">Synchronize settings that meet the following criteria:</span></span>

-   <span data-ttu-id="b416a-110">存储在用户易于访问的位置的设置。</span><span class="sxs-lookup"><span data-stu-id="b416a-110">Settings that are stored in user-accessible locations.</span></span> <span data-ttu-id="b416a-111">例如，不要同步在 system32 或注册表外部 HKCU 部分中存储的设置。</span><span class="sxs-lookup"><span data-stu-id="b416a-111">For example, do not synchronize settings that are stored in system32 or outside HKCU section of the registry.</span></span>

-   <span data-ttu-id="b416a-112">不特定于特定计算机的设置。</span><span class="sxs-lookup"><span data-stu-id="b416a-112">Settings that are not specific to the particular computer.</span></span> <span data-ttu-id="b416a-113">例如，排除网络或硬件配置。</span><span class="sxs-lookup"><span data-stu-id="b416a-113">For example, exclude network or hardware configurations.</span></span>

-   <span data-ttu-id="b416a-114">可以在计算机之间同步的设置，而不会损坏数据。</span><span class="sxs-lookup"><span data-stu-id="b416a-114">Settings that can be synchronized between computers without risk of corrupted data.</span></span> <span data-ttu-id="b416a-115">例如，不要使用存储在数据库文件中的设置。</span><span class="sxs-lookup"><span data-stu-id="b416a-115">For example, do not use settings that are stored in a database file.</span></span>

## <span data-ttu-id="b416a-116">UE-V 中包含的设置位置模板</span><span class="sxs-lookup"><span data-stu-id="b416a-116">Settings location templates that are included in UE-V</span></span>


**<span data-ttu-id="b416a-117">UE-V 应用程序设置位置模板</span><span class="sxs-lookup"><span data-stu-id="b416a-117">UE-V application settings location templates</span></span>**

<span data-ttu-id="b416a-118">UE-V agent 安装软件安装代理并为常见的 Microsoft 应用程序注册一个默认设置位置模板组。</span><span class="sxs-lookup"><span data-stu-id="b416a-118">The UE-V agent installation software installs the agent and registers a default group of settings location templates for common Microsoft applications.</span></span> <span data-ttu-id="b416a-119">这些设置位置模板捕获以下应用程序的设置值：</span><span class="sxs-lookup"><span data-stu-id="b416a-119">These settings location templates capture settings values for the following applications:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong><span data-ttu-id="b416a-120">应用程序类别</span><span class="sxs-lookup"><span data-stu-id="b416a-120">Application category</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="b416a-121">描述</span><span class="sxs-lookup"><span data-stu-id="b416a-121">Description</span></span></strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b416a-122">Microsoft Office 2010 应用程序</span><span class="sxs-lookup"><span data-stu-id="b416a-122">Microsoft Office 2010 applications</span></span></p></td>
<td align="left"><p><span data-ttu-id="b416a-123">Microsoft Word 2010</span><span class="sxs-lookup"><span data-stu-id="b416a-123">Microsoft Word 2010</span></span></p>
<p><span data-ttu-id="b416a-124">Microsoft Excel 2010</span><span class="sxs-lookup"><span data-stu-id="b416a-124">Microsoft Excel 2010</span></span></p>
<p><span data-ttu-id="b416a-125">Microsoft Outlook 2010</span><span class="sxs-lookup"><span data-stu-id="b416a-125">Microsoft Outlook 2010</span></span></p>
<p><span data-ttu-id="b416a-126">Microsoft Access 2010</span><span class="sxs-lookup"><span data-stu-id="b416a-126">Microsoft Access 2010</span></span></p>
<p><span data-ttu-id="b416a-127">Microsoft Project 2010</span><span class="sxs-lookup"><span data-stu-id="b416a-127">Microsoft Project 2010</span></span></p>
<p><span data-ttu-id="b416a-128">Microsoft PowerPoint 2010</span><span class="sxs-lookup"><span data-stu-id="b416a-128">Microsoft PowerPoint 2010</span></span></p>
<p><span data-ttu-id="b416a-129">Microsoft Publisher 2010</span><span class="sxs-lookup"><span data-stu-id="b416a-129">Microsoft Publisher 2010</span></span></p>
<p><span data-ttu-id="b416a-130">Microsoft Visio 2010</span><span class="sxs-lookup"><span data-stu-id="b416a-130">Microsoft Visio 2010</span></span></p>
<p><span data-ttu-id="b416a-131">Microsoft SharePoint Workspace 2010</span><span class="sxs-lookup"><span data-stu-id="b416a-131">Microsoft SharePoint Workspace 2010</span></span></p>
<p><span data-ttu-id="b416a-132">Microsoft InfoPath 2010</span><span class="sxs-lookup"><span data-stu-id="b416a-132">Microsoft InfoPath 2010</span></span></p>
<p><span data-ttu-id="b416a-133">Microsoft Lync 2010</span><span class="sxs-lookup"><span data-stu-id="b416a-133">Microsoft Lync 2010</span></span></p>
<p><span data-ttu-id="b416a-134">Microsoft OneNote 2010</span><span class="sxs-lookup"><span data-stu-id="b416a-134">Microsoft OneNote 2010</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b416a-135">浏览器选项（Internet Explorer 8、Internet Explorer 9 和 Internet Explorer 10）</span><span class="sxs-lookup"><span data-stu-id="b416a-135">Browser options (Internet Explorer 8, Internet Explorer 9, and Internet Explorer 10)</span></span></p></td>
<td align="left"><p><span data-ttu-id="b416a-136">"收藏夹"、"主页"、"选项卡" 和 "工具栏"。</span><span class="sxs-lookup"><span data-stu-id="b416a-136">Favorites, home page, tabs, and toolbars.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b416a-137">Windows 附件</span><span class="sxs-lookup"><span data-stu-id="b416a-137">Windows accessories</span></span></p></td>
<td align="left"><p><span data-ttu-id="b416a-138">计算器、记事本和写字板。</span><span class="sxs-lookup"><span data-stu-id="b416a-138">Calculator, Notepad, WordPad.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="b416a-139">当应用程序启动时，应用程序设置应用于应用程序。</span><span class="sxs-lookup"><span data-stu-id="b416a-139">Application settings are applied to the application when the application is started.</span></span> <span data-ttu-id="b416a-140">当应用程序关闭时，将保存这些文件。</span><span class="sxs-lookup"><span data-stu-id="b416a-140">They are saved when the application closes.</span></span>

**<span data-ttu-id="b416a-141">UE-V Windows 设置位置模板</span><span class="sxs-lookup"><span data-stu-id="b416a-141">UE-V Windows settings location templates</span></span>**

<span data-ttu-id="b416a-142">用户体验虚拟化包括设置位置模板，这些模板可捕获以下 Windows 设置的设置值：</span><span class="sxs-lookup"><span data-stu-id="b416a-142">User Experience Virtualization includes settings location templates that capture settings values for the following Windows settings:</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="b416a-143">Windows 设置</span><span class="sxs-lookup"><span data-stu-id="b416a-143">Windows settings</span></span></th>
<th align="left"><span data-ttu-id="b416a-144">描述</span><span class="sxs-lookup"><span data-stu-id="b416a-144">Description</span></span></th>
<th align="left"><span data-ttu-id="b416a-145">适用于</span><span class="sxs-lookup"><span data-stu-id="b416a-145">Apply on</span></span></th>
<th align="left"><span data-ttu-id="b416a-146">默认状态</span><span class="sxs-lookup"><span data-stu-id="b416a-146">Default state</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b416a-147">桌面背景</span><span class="sxs-lookup"><span data-stu-id="b416a-147">Desktop background</span></span></p></td>
<td align="left"><p><span data-ttu-id="b416a-148">当前处于活动状态的桌面背景。</span><span class="sxs-lookup"><span data-stu-id="b416a-148">Currently active desktop background.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b416a-149">登录、解锁、远程连接。</span><span class="sxs-lookup"><span data-stu-id="b416a-149">Logon, unlock, remote connect.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b416a-150">启用</span><span class="sxs-lookup"><span data-stu-id="b416a-150">Enabled</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b416a-151">轻松使用</span><span class="sxs-lookup"><span data-stu-id="b416a-151">Ease of Access</span></span></p></td>
<td align="left"><p><span data-ttu-id="b416a-152">辅助功能和输入设置、放大镜、讲述人和屏幕键盘。</span><span class="sxs-lookup"><span data-stu-id="b416a-152">Accessibility and input settings, magnifier, Narrator, and on-Screen keyboard.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b416a-153">登录、解锁、远程连接。</span><span class="sxs-lookup"><span data-stu-id="b416a-153">Logon, unlock, remote connect.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b416a-154">禁用</span><span class="sxs-lookup"><span data-stu-id="b416a-154">Disabled</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b416a-155">桌面设置</span><span class="sxs-lookup"><span data-stu-id="b416a-155">Desktop settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="b416a-156">"开始" 菜单和任务栏设置、文件夹选项、默认桌面图标、附加时钟以及区域和语言设置。</span><span class="sxs-lookup"><span data-stu-id="b416a-156">Start menu and Taskbar settings, Folder options, default desktop icons, additional clocks, and region and Language settings.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b416a-157">仅登录。</span><span class="sxs-lookup"><span data-stu-id="b416a-157">Logon only.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b416a-158">禁用</span><span class="sxs-lookup"><span data-stu-id="b416a-158">Disabled</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="b416a-159">当用户登录、计算机解锁或远程连接到另一台计算机时，将应用 Windows 桌面背景和 "轻松访问" 设置。</span><span class="sxs-lookup"><span data-stu-id="b416a-159">The Windows desktop background and Ease of Access settings are applied when the user logs on, when the computer is unlocked, or upon remote connection to another computer.</span></span> <span data-ttu-id="b416a-160">当用户注销、计算机锁定或远程连接断开时，代理会保存这些设置。</span><span class="sxs-lookup"><span data-stu-id="b416a-160">The agent saves these settings when the user logs off, when the computer is locked, or when a remote connection is disconnected.</span></span> <span data-ttu-id="b416a-161">默认情况下，Windows 桌面背景设置是在同一操作系统版本的计算机之间漫游。</span><span class="sxs-lookup"><span data-stu-id="b416a-161">By default, Windows desktop background settings are roamed between computers of the same operating system version.</span></span>

<span data-ttu-id="b416a-162">在登录之前，Windows 桌面和 "轻松访问" 设置将在桌面登录到用户之前应用。</span><span class="sxs-lookup"><span data-stu-id="b416a-162">Windows desktop and Ease of Access settings are applied at logon before the desktop is presented to the user.</span></span> <span data-ttu-id="b416a-163">为优化登录体验，默认情况下，这些设置不是漫游。</span><span class="sxs-lookup"><span data-stu-id="b416a-163">To optimize the logon experience, these settings are not roamed by default.</span></span> <span data-ttu-id="b416a-164">可以使用组策略、PowerShell 和 WMI 启用桌面和轻松访问设置。</span><span class="sxs-lookup"><span data-stu-id="b416a-164">Desktop and Ease of Access settings can be enabled by using Group Policy, PowerShell, and WMI.</span></span>

<span data-ttu-id="b416a-165">UE-V 不支持漫游不同语言的操作系统之间的设置。</span><span class="sxs-lookup"><span data-stu-id="b416a-165">UE-V does not support the roaming of settings between operating systems with different languages.</span></span> <span data-ttu-id="b416a-166">例如，不支持英语和德语之间的同步。</span><span class="sxs-lookup"><span data-stu-id="b416a-166">For example, synchronization between English and German is not supported.</span></span> <span data-ttu-id="b416a-167">UE-V 漫游的所有计算机的语言用户设置必须匹配。</span><span class="sxs-lookup"><span data-stu-id="b416a-167">The language of all computers to which UE-V roams the user settings must match.</span></span>

<span data-ttu-id="b416a-168">**注意** 如果你更改由 Microsoft 提供的设置位置模板，则对于指定的应用程序或 Windows 设置组，用户体验虚拟化可能无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="b416a-168">**Note** If you change the settings location templates that are provided by Microsoft, User Experience Virtualization might not work properly for the designated application or Windows settings group.</span></span>

 

## <a href="" id="prevent-unintentional-user-settings-configuration-"></a><span data-ttu-id="b416a-169">防止无意间的用户设置配置</span><span class="sxs-lookup"><span data-stu-id="b416a-169">Prevent unintentional user Settings configuration</span></span>


<span data-ttu-id="b416a-170">用户体验虚拟化检查新用户设置信息，并从设置存储位置下载相应信息。</span><span class="sxs-lookup"><span data-stu-id="b416a-170">User Experience Virtualization checks for new user settings information, and downloads that information accordingly from a settings storage location.</span></span> <span data-ttu-id="b416a-171">然后，在以下情况下，它会将设置应用于本地计算机：</span><span class="sxs-lookup"><span data-stu-id="b416a-171">Then, it applies the settings to the local computer in the following cases:</span></span>

-   <span data-ttu-id="b416a-172">每次启动具有注册的 UE-V 模板的应用程序时。</span><span class="sxs-lookup"><span data-stu-id="b416a-172">Every time an application is launched that has a registered UE-V template.</span></span>

-   <span data-ttu-id="b416a-173">当用户登录到其计算机时。</span><span class="sxs-lookup"><span data-stu-id="b416a-173">When a user logs on to their computer.</span></span>

-   <span data-ttu-id="b416a-174">用户解锁计算机时。</span><span class="sxs-lookup"><span data-stu-id="b416a-174">When a user unlocks their computer.</span></span>

-   <span data-ttu-id="b416a-175">连接到安装了 UE-V 的远程桌面计算机时。</span><span class="sxs-lookup"><span data-stu-id="b416a-175">When a connection is made to a remote desktop computer that has UE-V installed.</span></span>

<span data-ttu-id="b416a-176">如果 UE-V 安装在计算机 A 和计算机 B 上，并且应用程序的所需设置位于计算机 A 上，则计算机 A 必须首先打开并关闭该应用程序。</span><span class="sxs-lookup"><span data-stu-id="b416a-176">If UE-V is installed on computer A and computer B, and the desired settings for the application are on computer A, then computer A must open and close the application first.</span></span> <span data-ttu-id="b416a-177">如果首先在计算机 B 上打开和关闭应用程序，则计算机 A 上的应用程序设置将配置为与计算机 B 上的应用程序设置相同。</span><span class="sxs-lookup"><span data-stu-id="b416a-177">If an application is opened and closed on computer B first, then the application settings on computer A will be configured to be the same as the application settings on computer B.</span></span>

<span data-ttu-id="b416a-178">此方案也适用于 Windows 设置。</span><span class="sxs-lookup"><span data-stu-id="b416a-178">This scenario also applies to Windows settings.</span></span> <span data-ttu-id="b416a-179">如果计算机 B 上的 Windows 设置应该与计算机 A 上的 Windows 设置相同，则用户应首先登录和注销计算机 A。</span><span class="sxs-lookup"><span data-stu-id="b416a-179">If the Windows settings on computer B should be the same as the Windows settings on computer A, then the user should logon and logoff computer A first.</span></span>

<span data-ttu-id="b416a-180">如果所需的用户设置按错误的顺序应用，则可以通过针对覆盖了这些设置的计算机上的特定应用程序或 Windows 配置执行还原操作来恢复它们。</span><span class="sxs-lookup"><span data-stu-id="b416a-180">If the desired user settings are applied in the wrong order, they can be recovered by performing a restore operation for the specific application or Windows configuration on the computer on which the settings were overwritten.</span></span> <span data-ttu-id="b416a-181">有关详细信息，请参阅[还原与 ue-v 1.0 同步的应用程序和 Windows 设置](restoring-application-and-windows-settings-synchronized-with-ue-v-10.md)。</span><span class="sxs-lookup"><span data-stu-id="b416a-181">For more information, see [Restoring Application and Windows Settings Synchronized with UE-V 1.0](restoring-application-and-windows-settings-synchronized-with-ue-v-10.md).</span></span>

## <span data-ttu-id="b416a-182">自定义 UE-V 设置位置模板</span><span class="sxs-lookup"><span data-stu-id="b416a-182">Custom UE-V settings location templates</span></span>


<span data-ttu-id="b416a-183">可以使用 UE-V 生成器创建自定义设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="b416a-183">You can create custom settings location templates by using the UE-V Generator.</span></span> <span data-ttu-id="b416a-184">在测试环境中创建和测试自定义设置位置模板后，可以将设置位置模板部署到企业中的计算机。</span><span class="sxs-lookup"><span data-stu-id="b416a-184">After you create and test a custom settings location template in a test environment, you can deploy the settings location templates to computers in the enterprise.</span></span> <span data-ttu-id="b416a-185">自定义设置位置模板必须使用现有部署基础结构（如企业软件分发（ESD）方法）和首选项进行部署，或者配置 UE-V 设置模板目录。</span><span class="sxs-lookup"><span data-stu-id="b416a-185">Custom settings location templates must be deployed with an existing deployment infrastructure, such as enterprise software distribution (ESD) method, with preferences, or by configuring an UE-V settings template catalog.</span></span> <span data-ttu-id="b416a-186">必须使用 UE-V WMI 或 PowerShell 注册使用 ESD 或组策略部署的模板。</span><span class="sxs-lookup"><span data-stu-id="b416a-186">Templates that are deployed with ESD or Group Policy must be registered by using UE-V WMI or PowerShell.</span></span> <span data-ttu-id="b416a-187">有关自定义设置位置模板的详细信息，请参阅[规划 ue-v 1.0 的自定义模板部署](planning-for-custom-template-deployment-for-ue-v-10.md)。</span><span class="sxs-lookup"><span data-stu-id="b416a-187">For more information about custom settings location templates, see [Planning for Custom Template Deployment for UE-V 1.0](planning-for-custom-template-deployment-for-ue-v-10.md).</span></span>

<span data-ttu-id="b416a-188">有关是否应同步业务线应用程序的指导，请参阅[评估 ue-v 1.0 的业务线应用程序的清单](checklist-for-evaluating-line-of-business-applications-for-ue-v-10.md)。</span><span class="sxs-lookup"><span data-stu-id="b416a-188">For guidance on whether a line-of-business application should be synchronized, see [Checklist for Evaluating Line-of-Business Applications for UE-V 1.0](checklist-for-evaluating-line-of-business-applications-for-ue-v-10.md).</span></span>

## <span data-ttu-id="b416a-189">相关主题</span><span class="sxs-lookup"><span data-stu-id="b416a-189">Related topics</span></span>


[<span data-ttu-id="b416a-190">规划 UE-V 1.0</span><span class="sxs-lookup"><span data-stu-id="b416a-190">Planning for UE-V 1.0</span></span>](planning-for-ue-v-10.md)

[<span data-ttu-id="b416a-191">规划 UE-V 1.0 的自定义模板部署</span><span class="sxs-lookup"><span data-stu-id="b416a-191">Planning for Custom Template Deployment for UE-V 1.0</span></span>](planning-for-custom-template-deployment-for-ue-v-10.md)

[<span data-ttu-id="b416a-192">部署 UE-V 1.0</span><span class="sxs-lookup"><span data-stu-id="b416a-192">Deploying UE-V 1.0</span></span>](deploying-ue-v-10.md)

 

 





