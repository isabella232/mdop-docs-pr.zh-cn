---
title: Microsoft 用户体验虚拟化（UE-V） 2. x
description: Microsoft 用户体验虚拟化（UE-V） 2. x
author: dansimp
ms.assetid: b860fed0-b846-415d-bdd6-ba60231a64be
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 04/19/2017
ms.openlocfilehash: 573b8bb2027e5c7f117a8254005a43c656f047a9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10795567"
---
# <span data-ttu-id="78d38-103">Microsoft 用户体验虚拟化（UE-V） 2. x</span><span class="sxs-lookup"><span data-stu-id="78d38-103">Microsoft User Experience Virtualization (UE-V) 2.x</span></span>

>[!NOTE]
><span data-ttu-id="78d38-104">本文档是 Microsoft 桌面优化包（MDOP）中包含的 ue-v 版本的 ue-v。</span><span class="sxs-lookup"><span data-stu-id="78d38-104">This documentation is a for version of UE-V that was included in the Microsoft Desktop Optimization Pack (MDOP).</span></span> <span data-ttu-id="78d38-105">有关 Windows 10 企业版中包含的最新 UE-V 版本的信息，请参阅[从 Ue-v 开始](https://docs.microsoft.com/windows/configuration/ue-v/uev-getting-started)。</span><span class="sxs-lookup"><span data-stu-id="78d38-105">For information about the latest version of UE-V which is included in Windows 10 Enterprise, see [Get Started with UE-V](https://docs.microsoft.com/windows/configuration/ue-v/uev-getting-started).</span></span>


<span data-ttu-id="78d38-106">通过实现 Microsoft 用户体验虚拟化（UE-V）2.0 或2.1 来捕获和集中你的用户的应用程序设置和 Windows 操作系统设置。</span><span class="sxs-lookup"><span data-stu-id="78d38-106">Capture and centralize your users’ application settings and Windows OS settings by implementing Microsoft User Experience Virtualization (UE-V) 2.0 or 2.1.</span></span> <span data-ttu-id="78d38-107">然后，将这些设置应用于您的企业中的用户访问的设备，如台式计算机、笔记本电脑或虚拟桌面基础结构（VDI）会话。</span><span class="sxs-lookup"><span data-stu-id="78d38-107">Then, apply these settings to the devices users access in your enterprise, like desktop computers, laptops, or virtual desktop infrastructure (VDI) sessions.</span></span>

**<span data-ttu-id="78d38-108">通过 UE-V，您可以 .。。</span><span class="sxs-lookup"><span data-stu-id="78d38-108">With UE-V you can…</span></span>**

-   <span data-ttu-id="78d38-109">指定要同步的应用程序和桌面设置</span><span class="sxs-lookup"><span data-stu-id="78d38-109">Specify which application and desktop settings synchronize</span></span>

-   <span data-ttu-id="78d38-110">在整个企业中随时随地提供用户工作所需的设置</span><span class="sxs-lookup"><span data-stu-id="78d38-110">Deliver the settings anytime and anywhere users work throughout the enterprise</span></span>

-   <span data-ttu-id="78d38-111">为第三方或业务线应用程序创建自定义模板</span><span class="sxs-lookup"><span data-stu-id="78d38-111">Create custom templates for your third-party or line-of-business applications</span></span>

-   <span data-ttu-id="78d38-112">在硬件更换或升级后或将虚拟机重置为其初始状态之后恢复设置</span><span class="sxs-lookup"><span data-stu-id="78d38-112">Recover settings after hardware replacement or upgrade, or after reimaging a virtual machine to its initial state</span></span>

## <span data-ttu-id="78d38-113">UE-V 2 的组件</span><span class="sxs-lookup"><span data-stu-id="78d38-113">Components of UE-V 2.x</span></span>


<span data-ttu-id="78d38-114">此图显示了部署的 UE-V 组件如何协同工作以同步设置。</span><span class="sxs-lookup"><span data-stu-id="78d38-114">This diagram shows how deployed UE-V components work together to synchronize settings.</span></span>

![uev2 体系结构图表](images/uev2archdiagram.gif)

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="78d38-116">组件</span><span class="sxs-lookup"><span data-stu-id="78d38-116">Component</span></span></th>
<th align="left"><span data-ttu-id="78d38-117">函数</span><span class="sxs-lookup"><span data-stu-id="78d38-117">Function</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="78d38-118">UE-V Agent</span><span class="sxs-lookup"><span data-stu-id="78d38-118">UE-V Agent</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="78d38-119">在需要同步设置的每台计算机上安装时， <strong> Ue-v Agent 将 </strong> 监视已注册的应用程序和操作系统以了解任何设置更改，然后在计算机之间同步这些设置。</span><span class="sxs-lookup"><span data-stu-id="78d38-119">Installed on every computer that needs to synchronize settings, the <strong>UE-V Agent</strong> monitors registered applications and the operating system for any settings changes, then synchronizes those settings between computers.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="78d38-120">设置程序包</span><span class="sxs-lookup"><span data-stu-id="78d38-120">Settings packages</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="78d38-121">应用程序设置和 Windows 设置存储在 <strong> </strong> 由 ue-v Agent 创建的设置包中。</span><span class="sxs-lookup"><span data-stu-id="78d38-121">Application settings and Windows settings are stored in <strong>settings packages</strong> created by the UE-V Agent.</span></span> <span data-ttu-id="78d38-122">生成、本地存储设置包，并将其复制到设置存储位置。</span><span class="sxs-lookup"><span data-stu-id="78d38-122">Settings packages are built, locally stored, and copied to the settings storage location.</span></span></p>
<ul>
<li><p><span data-ttu-id="78d38-123"><strong> </strong> 当用户关闭应用程序时，将存储桌面应用程序的设置值。</span><span class="sxs-lookup"><span data-stu-id="78d38-123">The setting values for <strong>desktop applications</strong> are stored when the user closes the application.</span></span></p></li>
<li><p><span data-ttu-id="78d38-124">在 <strong> </strong> 用户注销、计算机锁定或用户从计算机远程断开连接时，将存储 Windows 设置的值。</span><span class="sxs-lookup"><span data-stu-id="78d38-124">Values for <strong>Windows settings</strong> are stored when the user logs off, when the computer is locked, or when the user disconnects remotely from a computer.</span></span></p></li>
</ul>
<p><span data-ttu-id="78d38-125">同步提供程序确定何时从设置程序包中读取应用程序或操作系统设置 <strong> 并进行 </strong> 同步。</span><span class="sxs-lookup"><span data-stu-id="78d38-125">The sync provider determines when the application or operating system settings are read from the <strong>Settings Packages</strong> and synchronized.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="78d38-126">设置存储位置</span><span class="sxs-lookup"><span data-stu-id="78d38-126">Settings storage location</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="78d38-127">这是您的用户可以访问的标准网络共享。</span><span class="sxs-lookup"><span data-stu-id="78d38-127">This is a standard network share that your users can access.</span></span> <span data-ttu-id="78d38-128">UE-V Agent 验证位置并创建一个隐藏的系统文件夹，用于存储和检索用户设置。</span><span class="sxs-lookup"><span data-stu-id="78d38-128">The UE-V Agent verifies the location and creates a hidden system folder in which to store and retrieve user settings.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="78d38-129">设置位置模板</span><span class="sxs-lookup"><span data-stu-id="78d38-129">Settings location templates</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="78d38-130">UE-V 将 XML 文件用作设置位置模板，用于监视和同步用户计算机之间的桌面应用程序设置和 Windows 桌面设置。</span><span class="sxs-lookup"><span data-stu-id="78d38-130">UE-V uses XML files as settings location templates to monitor and synchronize desktop application settings and Windows desktop settings between user computers.</span></span> <span data-ttu-id="78d38-131">默认情况下，UE-V 中包含某些设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="78d38-131">By default, some settings location templates are included in UE-V .</span></span> <span data-ttu-id="78d38-132">您也可以通过 <a href="#customapps" data-raw-source="[managing settings synchronization for custom applications](#customapps)"> 管理自定义应用程序的设置同步来创建、编辑或验证自定义设置位置模板 </a> 。</span><span class="sxs-lookup"><span data-stu-id="78d38-132">You can also create, edit, or validate custom settings location templates by <a href="#customapps" data-raw-source="[managing settings synchronization for custom applications](#customapps)">managing settings synchronization for custom applications</a>.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="78d38-133">注意</span><span class="sxs-lookup"><span data-stu-id="78d38-133">Note</span></span></strong><br/><p><span data-ttu-id="78d38-134">Windows 应用不需要设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="78d38-134">Settings location templates are not required for Windows apps.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="78d38-135">Windows 应用列表</span><span class="sxs-lookup"><span data-stu-id="78d38-135">Windows app list</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="78d38-136">已捕获和动态应用 Windows 应用的设置。</span><span class="sxs-lookup"><span data-stu-id="78d38-136">Settings for Windows apps are captured and applied dynamically.</span></span> <span data-ttu-id="78d38-137">应用开发人员指定为每个应用同步的设置。</span><span class="sxs-lookup"><span data-stu-id="78d38-137">The app developer specifies the settings that are synchronized for each app.</span></span> <span data-ttu-id="78d38-138">UE-V 使用应用的托管列表确定启用了设置同步的 Windows 应用。</span><span class="sxs-lookup"><span data-stu-id="78d38-138">UE-V determines which Windows apps are enabled for settings synchronization using a managed list of apps.</span></span> <span data-ttu-id="78d38-139">默认情况下，此列表包含大多数 Windows 应用。</span><span class="sxs-lookup"><span data-stu-id="78d38-139">By default, this list includes most Windows apps.</span></span></p>
<p><span data-ttu-id="78d38-140">你可以按照此处所示的过程在 Windows 应用列表中添加或删除应用程序 <a href="https://technet.microsoft.com/library/dn458925.aspx" data-raw-source="[here](https://technet.microsoft.com/library/dn458925.aspx)"> </a> 。</span><span class="sxs-lookup"><span data-stu-id="78d38-140">You can add or remove applications in the Windows app list by following the procedures shown <a href="https://technet.microsoft.com/library/dn458925.aspx" data-raw-source="[here](https://technet.microsoft.com/library/dn458925.aspx)">here</a>.</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="customapps"></a><span data-ttu-id="78d38-141">管理自定义应用程序的设置同步</span><span class="sxs-lookup"><span data-stu-id="78d38-141">Managing Settings Synchronization for Custom Applications</span></span>

<span data-ttu-id="78d38-142">使用这些 UE-V 组件创建和管理第三方或业务线应用程序的自定义模板。</span><span class="sxs-lookup"><span data-stu-id="78d38-142">Use these UE-V components to create and manage custom templates for your third-party or line-of-business applications.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="78d38-143">UE-V 发电机</span><span class="sxs-lookup"><span data-stu-id="78d38-143">UE-V Generator</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="78d38-144">使用 <strong> Ue-v 生成器 </strong> 创建自定义设置位置模板，然后您可以将这些模板分发给用户计算机。</span><span class="sxs-lookup"><span data-stu-id="78d38-144">Use the <strong>UE-V Generator</strong> to create custom settings location templates that you can then distribute to user computers.</span></span> <span data-ttu-id="78d38-145">UE-V 生成器还允许你编辑现有模板或验证使用另一个 XML 编辑器创建的模板。</span><span class="sxs-lookup"><span data-stu-id="78d38-145">The UE-V Generator also lets you edit an existing template or validate a template that was created by using another XML editor.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="78d38-146">设置模板目录</span><span class="sxs-lookup"><span data-stu-id="78d38-146">Settings template catalog</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="78d38-147"><strong>设置模板目录 </strong> 是 ue-v 计算机上的文件夹路径或存储自定义设置位置模板的服务器消息块（SMB）网络共享。</span><span class="sxs-lookup"><span data-stu-id="78d38-147">The <strong>settings template catalog</strong> is a folder path on UE-V computers or a Server Message Block (SMB) network share that stores the custom settings location templates.</span></span> <span data-ttu-id="78d38-148">UE-V Agent 每天检查此位置，检索新的或更新的模板，并更新其同步行为。</span><span class="sxs-lookup"><span data-stu-id="78d38-148">The UE-V Agent checks this location once a day, retrieves new or updated templates, and updates its synchronization behavior.</span></span></p>
<p><span data-ttu-id="78d38-149">如果仅使用 UE-V 默认设置位置模板，则不需要设置模板目录。</span><span class="sxs-lookup"><span data-stu-id="78d38-149">If you use only the UE-V default settings location templates, then a settings template catalog is unnecessary.</span></span> <span data-ttu-id="78d38-150">有关设置部署目录的详细信息，请参阅 <a href="https://technet.microsoft.com/library/dn458942.aspx#deploycatalogue" data-raw-source="[Configure a UE-V settings template catalog](https://technet.microsoft.com/library/dn458942.aspx#deploycatalogue)"> 配置 ue-v 设置模板目录 </a> 。</span><span class="sxs-lookup"><span data-stu-id="78d38-150">For more information about settings deployment catalogs, see <a href="https://technet.microsoft.com/library/dn458942.aspx#deploycatalogue" data-raw-source="[Configure a UE-V settings template catalog](https://technet.microsoft.com/library/dn458942.aspx#deploycatalogue)">Configure a UE-V settings template catalog</a>.</span></span></p></td>
</tr>
</tbody>
</table>



![ue-v 发电机进程](images/ue-vgeneratorprocess.gif)

## <span data-ttu-id="78d38-152">默认同步的设置</span><span class="sxs-lookup"><span data-stu-id="78d38-152">Settings Synchronized by Default</span></span>


<span data-ttu-id="78d38-153">Ue-v 默认情况下，ue-v 同步这些应用程序的设置。</span><span class="sxs-lookup"><span data-stu-id="78d38-153">UE-V synchronizes settings for these applications by default.</span></span> <span data-ttu-id="78d38-154">有关完整列表和更多详细信息，请参阅[在 ue-v 部署中自动同步的设置](https://technet.microsoft.com/library/dn458932.aspx#autosyncsettings)。</span><span class="sxs-lookup"><span data-stu-id="78d38-154">For a complete list and more detailed information, see [Settings that are automatically synchronized in a UE-V deployment](https://technet.microsoft.com/library/dn458932.aspx#autosyncsettings).</span></span>

<span data-ttu-id="78d38-155">Microsoft Office 2013 应用程序（UE-V 2.1 SP1 和2.1）</span><span class="sxs-lookup"><span data-stu-id="78d38-155">Microsoft Office 2013 applications (UE-V 2.1 SP1 and 2.1)</span></span>

<span data-ttu-id="78d38-156">Microsoft Office 2010 应用程序（UE-V 2.1 SP1、2.1 和2.0）</span><span class="sxs-lookup"><span data-stu-id="78d38-156">Microsoft Office 2010 applications (UE-V 2.1 SP1, 2.1, and 2.0)</span></span>

<span data-ttu-id="78d38-157">Microsoft Office 2007 应用程序（仅限 UE-V 2.0）</span><span class="sxs-lookup"><span data-stu-id="78d38-157">Microsoft Office 2007 applications (UE-V 2.0 only)</span></span>

<span data-ttu-id="78d38-158">Internet Explorer 8、9和10</span><span class="sxs-lookup"><span data-stu-id="78d38-158">Internet Explorer 8, 9, and 10</span></span>

<span data-ttu-id="78d38-159">UE-V 2.1 SP1 和2.1 中的 Internet Explorer 11</span><span class="sxs-lookup"><span data-stu-id="78d38-159">Internet Explorer 11 in UE-V 2.1 SP1 and 2.1</span></span>

<span data-ttu-id="78d38-160">许多 Windows 应用程序（如 Xbox）</span><span class="sxs-lookup"><span data-stu-id="78d38-160">Many Windows applications, such as Xbox</span></span>

<span data-ttu-id="78d38-161">许多 Windows 桌面应用程序（如记事本）</span><span class="sxs-lookup"><span data-stu-id="78d38-161">Many Windows desktop applications, such as Notepad</span></span>

<span data-ttu-id="78d38-162">许多 Windows 设置，如桌面背景或墙纸</span><span class="sxs-lookup"><span data-stu-id="78d38-162">Many Windows settings, such as desktop background or wallpaper</span></span>

**<span data-ttu-id="78d38-163">注意</span><span class="sxs-lookup"><span data-stu-id="78d38-163">Note</span></span>**  
<span data-ttu-id="78d38-164">你还可以[自定义 ue-v，以便同步](https://technet.microsoft.com/library/dn458942.aspx)除默认情况下同步的应用程序的设置。</span><span class="sxs-lookup"><span data-stu-id="78d38-164">You can also [customize UE-V to synchronize settings](https://technet.microsoft.com/library/dn458942.aspx) for applications other than those synchronized by default.</span></span>



## <span data-ttu-id="78d38-165">将 UE-V 与其他 Microsoft 产品进行比较</span><span class="sxs-lookup"><span data-stu-id="78d38-165">Compare UE-V to other Microsoft products</span></span>


<span data-ttu-id="78d38-166">使用此表比较 UE-V 以在 Windows 7 中同步配置文件、在 Windows 8 中同步配置文件，以及 Microsoft 帐户的同步电脑设置功能。</span><span class="sxs-lookup"><span data-stu-id="78d38-166">Use this table to compare UE-V to Synchronize Profiles in Windows 7, Synchronize Profiles in Windows 8, and the Sync PC Settings feature of Microsoft account.</span></span>

<table style="width:100%;">
<colgroup>
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="78d38-167">功能</span><span class="sxs-lookup"><span data-stu-id="78d38-167">Feature</span></span></th>
<th align="left"><span data-ttu-id="78d38-168">使用 Windows 7 同步配置文件</span><span class="sxs-lookup"><span data-stu-id="78d38-168">Synchronize Profiles using Windows 7</span></span></th>
<th align="left"><span data-ttu-id="78d38-169">使用 Windows 8 同步配置文件</span><span class="sxs-lookup"><span data-stu-id="78d38-169">Synchronize Profiles using Windows 8</span></span></th>
<th align="left"><span data-ttu-id="78d38-170">使用 Windows 10 同步配置文件</span><span class="sxs-lookup"><span data-stu-id="78d38-170">Synchronize Profiles using Windows 10</span></span></th>
<th align="left"><span data-ttu-id="78d38-171">Microsoft 帐户</span><span class="sxs-lookup"><span data-stu-id="78d38-171">Microsoft account</span></span></th>
<th align="left"><span data-ttu-id="78d38-172">UE-V 2。0</span><span class="sxs-lookup"><span data-stu-id="78d38-172">UE-V 2.0</span></span></th>
<th align="left"><span data-ttu-id="78d38-173">UE-V 2.1 和 2.1 SP1</span><span class="sxs-lookup"><span data-stu-id="78d38-173">UE-V 2.1 and 2.1 SP1</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="78d38-174">同步多台计算机之间的设置</span><span class="sxs-lookup"><span data-stu-id="78d38-174">Synchronize settings between multiple computers</span></span></p></td>
<td align="left"><p><span data-ttu-id="78d38-175">●</span><span class="sxs-lookup"><span data-stu-id="78d38-175">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="78d38-176">●</span><span class="sxs-lookup"><span data-stu-id="78d38-176">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="78d38-177">●</span><span class="sxs-lookup"><span data-stu-id="78d38-177">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="78d38-178">●</span><span class="sxs-lookup"><span data-stu-id="78d38-178">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="78d38-179">●</span><span class="sxs-lookup"><span data-stu-id="78d38-179">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="78d38-180">●</span><span class="sxs-lookup"><span data-stu-id="78d38-180">●</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="78d38-181">在物理应用和虚拟应用之间同步设置</span><span class="sxs-lookup"><span data-stu-id="78d38-181">Synchronize settings between physical and virtual apps</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="78d38-182">●</span><span class="sxs-lookup"><span data-stu-id="78d38-182">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="78d38-183">●</span><span class="sxs-lookup"><span data-stu-id="78d38-183">●</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="78d38-184">同步 Windows 应用设置</span><span class="sxs-lookup"><span data-stu-id="78d38-184">Synchronize Windows app settings</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="78d38-185">●</span><span class="sxs-lookup"><span data-stu-id="78d38-185">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="78d38-186">●</span><span class="sxs-lookup"><span data-stu-id="78d38-186">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="78d38-187">●</span><span class="sxs-lookup"><span data-stu-id="78d38-187">●</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="78d38-188">通过 WMI 管理</span><span class="sxs-lookup"><span data-stu-id="78d38-188">Manage via WMI</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="78d38-189">●</span><span class="sxs-lookup"><span data-stu-id="78d38-189">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="78d38-190">●</span><span class="sxs-lookup"><span data-stu-id="78d38-190">●</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="78d38-191">●</span><span class="sxs-lookup"><span data-stu-id="78d38-191">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="78d38-192">●</span><span class="sxs-lookup"><span data-stu-id="78d38-192">●</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="78d38-193">定期同步设置更改</span><span class="sxs-lookup"><span data-stu-id="78d38-193">Synchronize settings changes on a regular basis</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="78d38-194">●</span><span class="sxs-lookup"><span data-stu-id="78d38-194">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="78d38-195">●</span><span class="sxs-lookup"><span data-stu-id="78d38-195">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="78d38-196">●</span><span class="sxs-lookup"><span data-stu-id="78d38-196">●</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="78d38-197">设置的最低配置</span><span class="sxs-lookup"><span data-stu-id="78d38-197">Minimal configuration for Setup</span></span></p></td>
<td align="left"><p><span data-ttu-id="78d38-198">●</span><span class="sxs-lookup"><span data-stu-id="78d38-198">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="78d38-199">●</span><span class="sxs-lookup"><span data-stu-id="78d38-199">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="78d38-200">●</span><span class="sxs-lookup"><span data-stu-id="78d38-200">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="78d38-201">●</span><span class="sxs-lookup"><span data-stu-id="78d38-201">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="78d38-202">●</span><span class="sxs-lookup"><span data-stu-id="78d38-202">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="78d38-203">●</span><span class="sxs-lookup"><span data-stu-id="78d38-203">●</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="78d38-204">在未加入域的计算机上受支持</span><span class="sxs-lookup"><span data-stu-id="78d38-204">Supported on non-domain joined computers</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="78d38-205">●</span><span class="sxs-lookup"><span data-stu-id="78d38-205">●</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="78d38-206">支持主计算机 Active Directory 属性</span><span class="sxs-lookup"><span data-stu-id="78d38-206">Supports Primary Computer Active Directory attribute</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="78d38-207">●</span><span class="sxs-lookup"><span data-stu-id="78d38-207">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="78d38-208">●</span><span class="sxs-lookup"><span data-stu-id="78d38-208">●</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="78d38-209">同步虚拟桌面基础结构（VDI）/Remote 桌面服务（RDS）和丰富桌面之间的设置</span><span class="sxs-lookup"><span data-stu-id="78d38-209">Synchronizes settings between virtual desktop infrastructure (VDI)/Remote Desktop Services (RDS) and rich desktops</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="78d38-210">●</span><span class="sxs-lookup"><span data-stu-id="78d38-210">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="78d38-211">●</span><span class="sxs-lookup"><span data-stu-id="78d38-211">●</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="78d38-212">无限制设置存储空间</span><span class="sxs-lookup"><span data-stu-id="78d38-212">Unlimited setting storage space</span></span></p></td>
<td align="left"><p><span data-ttu-id="78d38-213">●</span><span class="sxs-lookup"><span data-stu-id="78d38-213">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="78d38-214">●</span><span class="sxs-lookup"><span data-stu-id="78d38-214">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="78d38-215">●</span><span class="sxs-lookup"><span data-stu-id="78d38-215">●</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="78d38-216">●</span><span class="sxs-lookup"><span data-stu-id="78d38-216">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="78d38-217">●</span><span class="sxs-lookup"><span data-stu-id="78d38-217">●</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="78d38-218">要同步的应用设置的选择</span><span class="sxs-lookup"><span data-stu-id="78d38-218">Choice in which app settings to synchronize</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="78d38-219">●</span><span class="sxs-lookup"><span data-stu-id="78d38-219">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="78d38-220">●</span><span class="sxs-lookup"><span data-stu-id="78d38-220">●</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="78d38-221">IT 专业人员的备份/恢复</span><span class="sxs-lookup"><span data-stu-id="78d38-221">Backup/Restore for IT Pro</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="78d38-222">●</span><span class="sxs-lookup"><span data-stu-id="78d38-222">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="78d38-223">部分</span><span class="sxs-lookup"><span data-stu-id="78d38-223">Partial</span></span></p></td>
<td align="left"><p><span data-ttu-id="78d38-224">●</span><span class="sxs-lookup"><span data-stu-id="78d38-224">●</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="78d38-225">UE-V 2. x 发行说明</span><span class="sxs-lookup"><span data-stu-id="78d38-225">UE-V 2.x Release Notes</span></span>


<span data-ttu-id="78d38-226">有关详细信息，以及未使其进入文档的最新消息，请参阅</span><span class="sxs-lookup"><span data-stu-id="78d38-226">For more information, and for late-breaking news that did not make it into the documentation, see</span></span>

-   [<span data-ttu-id="78d38-227">Microsoft 用户体验虚拟化 (UE-V) 2.1 SP1 发行说明</span><span class="sxs-lookup"><span data-stu-id="78d38-227">Microsoft User Experience Virtualization (UE-V) 2.1 SP1 Release Notes</span></span>](microsoft-user-experience-virtualization--ue-v--21-sp1-release-notes.md)

-   [<span data-ttu-id="78d38-228">Microsoft 用户体验虚拟化 (UE-V) 2.1 发行说明</span><span class="sxs-lookup"><span data-stu-id="78d38-228">Microsoft User Experience Virtualization (UE-V) 2.1 Release Notes</span></span>](microsoft-user-experience-virtualization--ue-v--21-release-notesuevv21.md)

-   [<span data-ttu-id="78d38-229">Microsoft 用户体验虚拟化 (UE-V) 2.0 发行说明</span><span class="sxs-lookup"><span data-stu-id="78d38-229">Microsoft User Experience Virtualization (UE-V) 2.0 Release Notes</span></span>](microsoft-user-experience-virtualization--ue-v--20-release-notesuevv2.md)

## <span data-ttu-id="78d38-230">此产品的其他资源</span><span class="sxs-lookup"><span data-stu-id="78d38-230">Other resources for this product</span></span>


-   [<span data-ttu-id="78d38-231">UE-V 2.x 入门</span><span class="sxs-lookup"><span data-stu-id="78d38-231">Get Started with UE-V 2.x</span></span>](get-started-with-ue-v-2x-new-uevv2.md)

-   [<span data-ttu-id="78d38-232">准备 UE-V 2. x 部署</span><span class="sxs-lookup"><span data-stu-id="78d38-232">Prepare a UE-V 2.x Deployment</span></span>](prepare-a-ue-v-2x-deployment-new-uevv2.md)

-   [<span data-ttu-id="78d38-233">管理 UE-V 2. x</span><span class="sxs-lookup"><span data-stu-id="78d38-233">Administering UE-V 2.x</span></span>](administering-ue-v-2x-new-uevv2.md)

-   [<span data-ttu-id="78d38-234">解决 UE-V 2. x</span><span class="sxs-lookup"><span data-stu-id="78d38-234">Troubleshooting UE-V 2.x</span></span>](troubleshooting-ue-v-2x-both-uevv2.md)

-   [<span data-ttu-id="78d38-235">UE-V 2.x 的技术参考</span><span class="sxs-lookup"><span data-stu-id="78d38-235">Technical Reference for UE-V 2.x</span></span>](technical-reference-for-ue-v-2x-both-uevv2.md)

### <span data-ttu-id="78d38-236">详细信息</span><span class="sxs-lookup"><span data-stu-id="78d38-236">More information</span></span>

<a href="" id="mdop-techcenter-page"></a><span data-ttu-id="78d38-237">[MDOP 技术中心页](https://go.microsoft.com/fwlink/p/?LinkId=225286)了解最新的 MDOP 信息和资源。</span><span class="sxs-lookup"><span data-stu-id="78d38-237">[MDOP TechCenter Page](https://go.microsoft.com/fwlink/p/?LinkId=225286) Learn about the latest MDOP information and resources.</span></span>

<a href="" id="mdop-information-experience"></a><span data-ttu-id="78d38-238">[MDOP 信息体验](https://go.microsoft.com/fwlink/p/?LinkId=236032)查找 MDOP 技术的文档、视频和其他资源。</span><span class="sxs-lookup"><span data-stu-id="78d38-238">[MDOP Information Experience](https://go.microsoft.com/fwlink/p/?LinkId=236032) Find documentation, videos, and other resources for MDOP technologies.</span></span> <span data-ttu-id="78d38-239">您还可以在[Facebook](https://go.microsoft.com/fwlink/p/?LinkId=242445)或[Twitter](https://go.microsoft.com/fwlink/p/?LinkId=242447)上关注我们，[向我们发送反馈](mailto:MDOPDocs@microsoft.com)或了解更新。</span><span class="sxs-lookup"><span data-stu-id="78d38-239">You can also [send us feedback](mailto:MDOPDocs@microsoft.com) or learn about updates by following us on [Facebook](https://go.microsoft.com/fwlink/p/?LinkId=242445) or [Twitter](https://go.microsoft.com/fwlink/p/?LinkId=242447).</span></span>














