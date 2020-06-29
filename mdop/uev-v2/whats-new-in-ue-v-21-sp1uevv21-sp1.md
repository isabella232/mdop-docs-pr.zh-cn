---
title: UE-V 2.1 SP1 中的新增功能
description: UE-V 2.1 SP1 中的新增功能
author: dansimp
ms.assetid: 9a40c737-ad9a-4ec1-b42b-31bfabe0f170
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 1f4b6210d95795c352a7ef1402b0353c6f52774b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804166"
---
# <span data-ttu-id="8efff-103">UE-V 2.1 SP1 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="8efff-103">What's New in UE-V 2.1 SP1</span></span>


<span data-ttu-id="8efff-104">用户体验虚拟化 2.1 SP1 提供与 UE-V 2.1 相比的这些新功能和功能。</span><span class="sxs-lookup"><span data-stu-id="8efff-104">User Experience Virtualization 2.1 SP1 provides these new features and functionality compared to UE-V 2.1.</span></span> <span data-ttu-id="8efff-105">[Microsoft 用户体验虚拟化（ue-v） 2.1 Sp1 发行说明](microsoft-user-experience-virtualization--ue-v--21-sp1-release-notes.md)提供有关 UE-V 2.1 SP1 版本的详细信息。</span><span class="sxs-lookup"><span data-stu-id="8efff-105">The [Microsoft User Experience Virtualization (UE-V) 2.1 SP1 Release Notes](microsoft-user-experience-virtualization--ue-v--21-sp1-release-notes.md) provide more information about the UE-V 2.1 SP1 release.</span></span>

## <span data-ttu-id="8efff-106">Windows 10 支持</span><span class="sxs-lookup"><span data-stu-id="8efff-106">Support for Windows 10</span></span>


<span data-ttu-id="8efff-107">UE-V 2.1 SP1 除了支持早期版本的 UE-V 支持的同一软件外，还添加了对 Windows 10 的支持。</span><span class="sxs-lookup"><span data-stu-id="8efff-107">UE-V 2.1 SP1 adds support for Windows 10, in addition to the same software that is supported in earlier versions of UE-V.</span></span>

### <span data-ttu-id="8efff-108">与 Microsoft Azure 的兼容性</span><span class="sxs-lookup"><span data-stu-id="8efff-108">Compatibility with Microsoft Azure</span></span>

<span data-ttu-id="8efff-109">Windows 10 允许企业用户将 Windows 应用设置和 Windows 操作系统设置同步到 Azure，而不是 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="8efff-109">Windows 10 lets enterprise users synchronize Windows app settings and Windows operating system settings to Azure instead of to OneDrive.</span></span> <span data-ttu-id="8efff-110">你可以将 Windows 10 企业版同步功能与 UE-V 配合使用，仅限本地域的计算机。</span><span class="sxs-lookup"><span data-stu-id="8efff-110">You can use the Windows 10 enterprise sync functionality together with UE-V for on-premises domain-joined computers only.</span></span> <span data-ttu-id="8efff-111">若要启用 Windows 10 与 UE-V 之间的共存，必须在每个客户端或组策略上使用任何 PowerShell 禁用以下 UE-V 模板。</span><span class="sxs-lookup"><span data-stu-id="8efff-111">To enable coexistence between Windows 10 and UE-V, you must disable the following UE-V templates using either PowerShell on each client or Group Policy.</span></span>

<span data-ttu-id="8efff-112">在 "组策略" 中的 "Microsoft 用户体验虚拟化" 节点下，配置以下策略设置：</span><span class="sxs-lookup"><span data-stu-id="8efff-112">In Group Policy, under the Microsoft User Experience Virtualization node, configure these policy settings:</span></span>

-   <span data-ttu-id="8efff-113">启用 "不同步 Windows 应用"</span><span class="sxs-lookup"><span data-stu-id="8efff-113">Enable “Do Not Synchronize Windows Apps”</span></span>

-   <span data-ttu-id="8efff-114">禁用 "同步 Windows 设置"</span><span class="sxs-lookup"><span data-stu-id="8efff-114">Disable “Sync Windows Settings”</span></span>

### <span data-ttu-id="8efff-115">Windows 10 支持的设置同步行为已更改</span><span class="sxs-lookup"><span data-stu-id="8efff-115">Settings Synchronization Behavior Changed for Windows 10 Support</span></span>

<span data-ttu-id="8efff-116">UE-V 2.1 SP1 在 Windows 10 设备之间漫游任务栏设置。</span><span class="sxs-lookup"><span data-stu-id="8efff-116">UE-V 2.1 SP1 roams taskbar settings between Windows 10 devices.</span></span> <span data-ttu-id="8efff-117">但是，UE-V 不会在运行以前操作系统的 Windows 10 设备和设备之间同步任务栏设置。</span><span class="sxs-lookup"><span data-stu-id="8efff-117">However, UE-V does not synchronize taskbar settings between Windows 10 devices and devices running previous operating systems.</span></span>

<span data-ttu-id="8efff-118">此外，UE-V 2.1 SP1 不会同步 Windows 10 中的 Microsoft 计算器与以前操作系统中的 Microsoft 计算器之间的设置。</span><span class="sxs-lookup"><span data-stu-id="8efff-118">In addition, UE-V 2.1 SP1 does not synchronize settings between the Microsoft Calculator in Windows 10 and the Microsoft Calculator in previous operating systems.</span></span>

## <span data-ttu-id="8efff-119">为漫游网络打印机添加的支持</span><span class="sxs-lookup"><span data-stu-id="8efff-119">Support Added for Roaming Network Printers</span></span>


<span data-ttu-id="8efff-120">UE-V 2.1 SP1 允许网络打印机在设备之间漫游，以便用户登录到网络上的任何设备时可以访问其网络打印机。</span><span class="sxs-lookup"><span data-stu-id="8efff-120">UE-V 2.1 SP1 lets network printers roam between devices so that a user has access to their network printers when logged on to any device on the network.</span></span> <span data-ttu-id="8efff-121">这包括将其设置为默认打印机的漫游打印机。</span><span class="sxs-lookup"><span data-stu-id="8efff-121">This includes roaming the printer that they set as the default.</span></span>

<span data-ttu-id="8efff-122">UE-V 中的打印机漫游需要以下其中一种方案：</span><span class="sxs-lookup"><span data-stu-id="8efff-122">Printer roaming in UE-V requires one of these scenarios:</span></span>

-   <span data-ttu-id="8efff-123">打印服务器在漫游到新设备时可以下载所需的驱动程序。</span><span class="sxs-lookup"><span data-stu-id="8efff-123">The print server can download the required driver when it roams to a new device.</span></span>

-   <span data-ttu-id="8efff-124">漫游网络打印机的驱动程序已在需要访问该网络打印机的任何设备上预安装。</span><span class="sxs-lookup"><span data-stu-id="8efff-124">The driver for the roaming network printer is pre-installed on any device that needs to access that network printer.</span></span>

-   <span data-ttu-id="8efff-125">可以从 Windows Update 获取打印机驱动程序。</span><span class="sxs-lookup"><span data-stu-id="8efff-125">The printer driver can be obtained from Windows Update.</span></span>

<span data-ttu-id="8efff-126">**注意** UE-V 打印机漫游**功能不会漫游打印机**设置或首选项，例如双面打印。</span><span class="sxs-lookup"><span data-stu-id="8efff-126">**Note** The UE-V printer roaming feature does **not** roam printer settings or preferences, such as printing double-sided.</span></span>

 

## <span data-ttu-id="8efff-127">Office 2013 设置位置模板</span><span class="sxs-lookup"><span data-stu-id="8efff-127">Office 2013 Settings Location Template</span></span>


<span data-ttu-id="8efff-128">UE-V 2.1 和 2.1 SP1 包括 Microsoft Office 2013 设置位置模板以及改进的 Outlook 签名支持。</span><span class="sxs-lookup"><span data-stu-id="8efff-128">UE-V 2.1 and 2.1 SP1 include the Microsoft Office 2013 settings location template with improved Outlook signature support.</span></span> <span data-ttu-id="8efff-129">我们已为新的、答复和转发的电子邮件添加了默认签名设置的同步。</span><span class="sxs-lookup"><span data-stu-id="8efff-129">We’ve added synchronization of default signature settings for new, reply, and forwarded emails.</span></span> <span data-ttu-id="8efff-130">客户无需再选择默认签名设置。</span><span class="sxs-lookup"><span data-stu-id="8efff-130">Customers no longer have to choose the default signature settings.</span></span>

<span data-ttu-id="8efff-131">**注意** 必须为用户要同步其 Outlook 签名的任何设备创建 Outlook 配置文件。</span><span class="sxs-lookup"><span data-stu-id="8efff-131">**Note** An Outlook profile must be created for any device on which a user wants to sync their Outlook signature.</span></span> <span data-ttu-id="8efff-132">如果尚未创建配置文件，则用户可以创建一个配置文件，然后在该设备上重新启动 Outlook 以启用签名同步。</span><span class="sxs-lookup"><span data-stu-id="8efff-132">If the profile is not already created, the user can create one and then restart Outlook on that device to enable signature synchronization.</span></span>

 

<span data-ttu-id="8efff-133">以前的 UE-V 包括 Microsoft Office 2010 设置位置模板，这些位置模板是通过 UE-V Agent 自动分发和注册的。</span><span class="sxs-lookup"><span data-stu-id="8efff-133">Previously UE-V included Microsoft Office 2010 settings location templates that were automatically distributed and registered with the UE-V Agent.</span></span> <span data-ttu-id="8efff-134">UE-V 2.1 与 Office 365 配合使用，确定 office 2013 设置是否由 Office 365 漫游。</span><span class="sxs-lookup"><span data-stu-id="8efff-134">UE-V 2.1 works with Office 365 to determine whether Office 2013 settings are roamed by Office 365.</span></span> <span data-ttu-id="8efff-135">如果设置由 Office 365 漫游，则他们不会通过 UE-V 进行漫游。</span><span class="sxs-lookup"><span data-stu-id="8efff-135">If settings are roamed by Office 365 they are not roamed by UE-V.</span></span> <span data-ttu-id="8efff-136">[Office 2013 的用户和漫游设置概述](https://go.microsoft.com/fwlink/p/?LinkID=391220)提供详细信息。</span><span class="sxs-lookup"><span data-stu-id="8efff-136">[Overview of user and roaming settings for Office 2013](https://go.microsoft.com/fwlink/p/?LinkID=391220) provides more information.</span></span>

<span data-ttu-id="8efff-137">若要使用 UE-V 2.1 启用设置同步，请执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="8efff-137">To enable settings synchronization using UE-V 2.1, do one of the following:</span></span>

-   <span data-ttu-id="8efff-138">使用组策略禁用 Office 365 同步</span><span class="sxs-lookup"><span data-stu-id="8efff-138">Use Group Policy to disable Office 365 synchronization</span></span>

-   <span data-ttu-id="8efff-139">不启用 Office 2013 安装期间的 Office 365 同步体验</span><span class="sxs-lookup"><span data-stu-id="8efff-139">Do not enable the Office 365 synchronization experience during Office 2013 installation</span></span>

<span data-ttu-id="8efff-140">UE-V 2.1 随附[Office 2013 和 office 2010 模板](https://technet.microsoft.com/library/dn458932.aspx#autosyncsettings)。</span><span class="sxs-lookup"><span data-stu-id="8efff-140">UE-V 2.1 ships [Office 2013 and Office 2010 templates](https://technet.microsoft.com/library/dn458932.aspx#autosyncsettings).</span></span> <span data-ttu-id="8efff-141">此版本将删除 Office 2007 模板。</span><span class="sxs-lookup"><span data-stu-id="8efff-141">This release removes the Office 2007 templates.</span></span> <span data-ttu-id="8efff-142">用户仍然可以使用 UE-V 2.0 或更早版本的 Office 2007 模板，并且仍然可以从位于[此处](https://go.microsoft.com/fwlink/p/?LinkID=246589)的 ue-v 模板库中获取模板。</span><span class="sxs-lookup"><span data-stu-id="8efff-142">Users can still use Office 2007 templates from UE-V 2.0 or earlier and can still get the templates from the UE-V template gallery located [here](https://go.microsoft.com/fwlink/p/?LinkID=246589).</span></span>






## <span data-ttu-id="8efff-143">相关主题</span><span class="sxs-lookup"><span data-stu-id="8efff-143">Related topics</span></span>


[<span data-ttu-id="8efff-144">UE-V 2.x 入门</span><span class="sxs-lookup"><span data-stu-id="8efff-144">Get Started with UE-V 2.x</span></span>](get-started-with-ue-v-2x-new-uevv2.md)

[<span data-ttu-id="8efff-145">准备 UE-V 2. x 部署</span><span class="sxs-lookup"><span data-stu-id="8efff-145">Prepare a UE-V 2.x Deployment</span></span>](prepare-a-ue-v-2x-deployment-new-uevv2.md)

[<span data-ttu-id="8efff-146">Microsoft 用户体验虚拟化 (UE-V) 2.1 SP1 发行说明</span><span class="sxs-lookup"><span data-stu-id="8efff-146">Microsoft User Experience Virtualization (UE-V) 2.1 SP1 Release Notes</span></span>](microsoft-user-experience-virtualization--ue-v--21-sp1-release-notes.md)

 

 





