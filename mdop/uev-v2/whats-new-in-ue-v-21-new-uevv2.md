---
title: UE-V 2.1 中的新增功能
description: UE-V 2.1 中的新增功能
author: dansimp
ms.assetid: 7f385183-7d97-4602-b19a-baa710334ade
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 7816fc8309a29347048172b2104750140c483587
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803933"
---
# <span data-ttu-id="8eca9-103">UE-V 2.1 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="8eca9-103">What's New in UE-V 2.1</span></span>


<span data-ttu-id="8eca9-104">用户体验虚拟化2.1 提供了与 UE-V 2.0 相比的这些新功能和功能。</span><span class="sxs-lookup"><span data-stu-id="8eca9-104">User Experience Virtualization 2.1 provides these new features and functionality compared to UE-V 2.0.</span></span> <span data-ttu-id="8eca9-105">[Microsoft 用户体验虚拟化（ue-v）2.1 发行说明](microsoft-user-experience-virtualization--ue-v--21-release-notesuevv21.md)提供了有关 ue-v 2.1 版本的详细信息。</span><span class="sxs-lookup"><span data-stu-id="8eca9-105">The [Microsoft User Experience Virtualization (UE-V) 2.1 Release Notes](microsoft-user-experience-virtualization--ue-v--21-release-notesuevv21.md) provide more information about the UE-V 2.1 release.</span></span>

## <span data-ttu-id="8eca9-106">Office 2013 设置位置模板</span><span class="sxs-lookup"><span data-stu-id="8eca9-106">Office 2013 Settings Location Template</span></span>


<span data-ttu-id="8eca9-107">UE-V 2.1 包括 Microsoft Office 2013 设置位置模板，改进了 Outlook 签名支持。</span><span class="sxs-lookup"><span data-stu-id="8eca9-107">UE-V 2.1 includes the Microsoft Office 2013 settings location template with improved Outlook signature support.</span></span> <span data-ttu-id="8eca9-108">在 UE-V 2.1 中，签名数据在用户设备之间同步。</span><span class="sxs-lookup"><span data-stu-id="8eca9-108">In UE-V 2.1, the signature data synchronizes between user devices.</span></span> <span data-ttu-id="8eca9-109">我们已为新的、答复和转发的电子邮件添加了默认签名设置的同步。</span><span class="sxs-lookup"><span data-stu-id="8eca9-109">We’ve added synchronization of default signature settings for new, reply, and forwarded emails.</span></span> <span data-ttu-id="8eca9-110">客户无需再选择默认签名设置。</span><span class="sxs-lookup"><span data-stu-id="8eca9-110">Customers no longer have to choose the default signature settings.</span></span>

<span data-ttu-id="8eca9-111">**注意** 必须为用户要同步其 Outlook 签名的任何设备创建 Outlook 配置文件。</span><span class="sxs-lookup"><span data-stu-id="8eca9-111">**Note** An Outlook profile must be created for any device on which a user wants to sync their Outlook signature.</span></span> <span data-ttu-id="8eca9-112">如果尚未创建配置文件，则用户可以创建一个配置文件，然后在该设备上重新启动 Outlook 以启用签名同步。</span><span class="sxs-lookup"><span data-stu-id="8eca9-112">If the profile is not already created, the user can create one and then restart Outlook on that device to enable signature synchronization.</span></span>

 

<span data-ttu-id="8eca9-113">以前的 UE-V 包括 Microsoft Office 2010 设置位置模板，这些位置模板是通过 UE-V Agent 自动分发和注册的。</span><span class="sxs-lookup"><span data-stu-id="8eca9-113">Previously UE-V included Microsoft Office 2010 settings location templates that were automatically distributed and registered with the UE-V Agent.</span></span> <span data-ttu-id="8eca9-114">UE-V 2.1 与 Office 365 配合使用，确定 office 2013 设置是否由 Office 365 漫游。</span><span class="sxs-lookup"><span data-stu-id="8eca9-114">UE-V 2.1 works with Office 365 to determine whether Office 2013 settings are roamed by Office 365.</span></span> <span data-ttu-id="8eca9-115">如果设置由 Office 365 漫游，则他们不会通过 UE-V 进行漫游。</span><span class="sxs-lookup"><span data-stu-id="8eca9-115">If settings are roamed by Office 365 they are not roamed by UE-V.</span></span> <span data-ttu-id="8eca9-116">[Office 2013 的用户和漫游设置概述](https://go.microsoft.com/fwlink/p/?LinkID=391220)提供详细信息。</span><span class="sxs-lookup"><span data-stu-id="8eca9-116">[Overview of user and roaming settings for Office 2013](https://go.microsoft.com/fwlink/p/?LinkID=391220) provides more information.</span></span>

<span data-ttu-id="8eca9-117">若要使用 UE-V 2.1 启用设置同步，请执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="8eca9-117">To enable settings synchronization using UE-V 2.1, do one of the following:</span></span>

-   <span data-ttu-id="8eca9-118">使用组策略禁用 Office 365 同步</span><span class="sxs-lookup"><span data-stu-id="8eca9-118">Use Group Policy to disable Office 365 synchronization</span></span>

-   <span data-ttu-id="8eca9-119">不启用 Office 2013 安装期间的 Office 365 同步体验</span><span class="sxs-lookup"><span data-stu-id="8eca9-119">Do not enable the Office 365 synchronization experience during Office 2013 installation</span></span>

<span data-ttu-id="8eca9-120">UE-V 2.1 随附[Office 2013 和 office 2010 模板](https://technet.microsoft.com/library/dn458932.aspx#autosyncsettings)。</span><span class="sxs-lookup"><span data-stu-id="8eca9-120">UE-V 2.1 ships [Office 2013 and Office 2010 templates](https://technet.microsoft.com/library/dn458932.aspx#autosyncsettings).</span></span> <span data-ttu-id="8eca9-121">此版本将删除 Office 2007 模板。</span><span class="sxs-lookup"><span data-stu-id="8eca9-121">This release removes the Office 2007 templates.</span></span> <span data-ttu-id="8eca9-122">用户仍然可以使用 UE-V 2.0 或更早版本的 Office 2007 模板，并且仍然可以从位于[此处](https://go.microsoft.com/fwlink/p/?LinkID=246589)的 ue-v 模板库中获取模板。</span><span class="sxs-lookup"><span data-stu-id="8eca9-122">Users can still use Office 2007 templates from UE-V 2.0 or earlier and can still get the templates from the UE-V template gallery located [here](https://go.microsoft.com/fwlink/p/?LinkID=246589).</span></span>

## <span data-ttu-id="8eca9-123">修复分布式文件系统命名空间用户</span><span class="sxs-lookup"><span data-stu-id="8eca9-123">Fix for Distributed File System Namespace Users</span></span>


<span data-ttu-id="8eca9-124">UE-V 通过添加名为 SyncProviderPingEnabled 的 UE-V 配置改进了分布式文件系统命名空间（DFSN）支持。</span><span class="sxs-lookup"><span data-stu-id="8eca9-124">UE-V has improved Distributed File System Namespace (DFSN) support by adding a UE-V configuration called SyncProviderPingEnabled.</span></span> <span data-ttu-id="8eca9-125">使用 PowerShell 或 WMI 禁用此配置允许用户禁用 UE-V ping。</span><span class="sxs-lookup"><span data-stu-id="8eca9-125">Disabling this configuration using PowerShell or WMI allows users to disable the UE-V ping.</span></span> <span data-ttu-id="8eca9-126">在使用 DFSN 服务器时，UE-V ping 会导致错误，因为这些服务器不响应 ping 操作。</span><span class="sxs-lookup"><span data-stu-id="8eca9-126">The UE-V ping causes an error when using DFSN servers because these servers do not respond to pings.</span></span> <span data-ttu-id="8eca9-127">非响应可防止 UE-V 进行同步设置。</span><span class="sxs-lookup"><span data-stu-id="8eca9-127">The non-response prevents UE-V from synchronizing settings.</span></span> <span data-ttu-id="8eca9-128">禁用 UE-V ping 允许 UE-V 同步正常工作。</span><span class="sxs-lookup"><span data-stu-id="8eca9-128">Disabling the UE-V ping allows UE-V synchronization to work normally.</span></span>

<span data-ttu-id="8eca9-129">若要禁用 UE-V ping，请使用此 PowerShell cmdlet：</span><span class="sxs-lookup"><span data-stu-id="8eca9-129">To disable UE-V ping, use this PowerShell cmdlet:</span></span>

``` syntax
Set-UevConfiguration -DisableSyncProviderPing
```

## <span data-ttu-id="8eca9-130">凭据同步</span><span class="sxs-lookup"><span data-stu-id="8eca9-130">Synchronization for Credentials</span></span>


<span data-ttu-id="8eca9-131">UE-V 2.1 使客户能够同步存储在 Windows 凭据管理器中的凭据和证书。</span><span class="sxs-lookup"><span data-stu-id="8eca9-131">UE-V 2.1 gives customers the ability to synchronize credentials and certificates stored in the Windows Credential Manager.</span></span> <span data-ttu-id="8eca9-132">默认情况下，此组件处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="8eca9-132">This component is disabled by default.</span></span> <span data-ttu-id="8eca9-133">启用此组件可使用户保持其域凭据和证书同步。用户可以在设备上一次登录，这些凭据将在其所有支持 UE-V 的设备上漫游。</span><span class="sxs-lookup"><span data-stu-id="8eca9-133">Enabling this component lets users keep their domain credentials and certificates in sync. Users can sign in one time on a device, and these credentials will roam for that user across all of their UE-V enabled devices.</span></span> <span data-ttu-id="8eca9-134">[通过 ue-v 2.1 管理凭据](https://technet.microsoft.com/library/dn458932.aspx#creds)可提供更多信息。</span><span class="sxs-lookup"><span data-stu-id="8eca9-134">[Manage Credentials with UE-V 2.1](https://technet.microsoft.com/library/dn458932.aspx#creds) provides more information.</span></span>

<span data-ttu-id="8eca9-135">**注意** 在 Windows 8 及更高版本中，凭据管理器包含 web 凭据。</span><span class="sxs-lookup"><span data-stu-id="8eca9-135">**Note** In Windows 8 and later, Credential Manager contains web credentials.</span></span> <span data-ttu-id="8eca9-136">这些凭据不会在用户的设备之间同步。</span><span class="sxs-lookup"><span data-stu-id="8eca9-136">These credentials are not synchronized between users’ devices.</span></span>

 

## <span data-ttu-id="8eca9-137">UE-V 和 Microsoft 帐户同步</span><span class="sxs-lookup"><span data-stu-id="8eca9-137">UE-V and Microsoft Account Synchronization</span></span>


<span data-ttu-id="8eca9-138">UE-V 检测 "带有 OneDrive 的同步设置" （也称为 Microsoft 帐户同步）是否已启用。</span><span class="sxs-lookup"><span data-stu-id="8eca9-138">UE-V detects if “Sync settings with OneDrive”, also known as Microsoft Account synchronization, is on.</span></span> <span data-ttu-id="8eca9-139">如果 Microsoft 帐户未配置为同步设置，则 UE-V 会同步设备之间的 Windows 应用、AppX 程序包和 Windows 桌面设置。</span><span class="sxs-lookup"><span data-stu-id="8eca9-139">If the Microsoft Account is not configured to synchronize settings, UE-V synchronizes Windows apps, AppX packages, and Windows desktop settings between devices.</span></span> <span data-ttu-id="8eca9-140">这使用户可以访问其应用商店应用、音乐、图片和其他 Microsoft 帐户启用的应用程序，而无需在企业防火墙外同步。</span><span class="sxs-lookup"><span data-stu-id="8eca9-140">This lets users access their Store apps, music, pictures and other Microsoft Account-enabled applications without syncing outside of the enterprise firewall.</span></span> <span data-ttu-id="8eca9-141">UE-V 检查组策略是否将停止将设置与 OneDrive 同步，或者如果用户在此计算机上禁用了用户控件中的 **"同步您的设置**"。</span><span class="sxs-lookup"><span data-stu-id="8eca9-141">UE-V checks whether Group Policy will stop synchronizing settings with OneDrive or if the user disables **Sync your settings on this computer** in the user controls.</span></span>

## <span data-ttu-id="8eca9-142">支持 Powerschool 外部</span><span class="sxs-lookup"><span data-stu-id="8eca9-142">Support for the SyncMethod External</span></span>


<span data-ttu-id="8eca9-143">名为**External**的新[powerschool 配置](https://technet.microsoft.com/library/dn554321.aspx)指定如果 ue-v 设置写入到用户计算机上的本地文件夹，则可以使用任何外部同步引擎（如 OneDrive For business、工作文件夹、Sharepoint 或 Dropbox）将这些设置应用于用户访问的不同计算机。</span><span class="sxs-lookup"><span data-stu-id="8eca9-143">A new [SyncMethod configuration](https://technet.microsoft.com/library/dn554321.aspx) called **External** specifies that if UE-V settings are written to a local folder on the user computer, then any external sync engine (such as OneDrive for Business, Work Folders, Sharepoint, or Dropbox) can be used to apply these settings to the different computers that users access.</span></span>

## <span data-ttu-id="8eca9-144">对 VDI 模式的增强支持</span><span class="sxs-lookup"><span data-stu-id="8eca9-144">Enhanced Support for VDI Mode</span></span>


<span data-ttu-id="8eca9-145">UE-V 2.1 包括对在最终用户之间共享的[VDI 会话的支持](https://technet.microsoft.com/library/dn458932.aspx#vdi)。</span><span class="sxs-lookup"><span data-stu-id="8eca9-145">UE-V 2.1 includes [support for VDI sessions](https://technet.microsoft.com/library/dn458932.aspx#vdi) that are shared among end users.</span></span> <span data-ttu-id="8eca9-146">作为管理员，你可以注册和配置特殊的 VDI 模板，从而确保 UE-V 将其所有功能完整地保留给非持久的 VDI 会话。</span><span class="sxs-lookup"><span data-stu-id="8eca9-146">As an administrator, you can register and configure a special VDI template, which ensures that UE-V keeps all of its functionality intact for non-persistent VDI sessions.</span></span>

<span data-ttu-id="8eca9-147">**注意** 如果不为非永久性 VDI 会话启用 VDI 模式，则某些功能不起作用，例如备份/还原和 LKG。</span><span class="sxs-lookup"><span data-stu-id="8eca9-147">**Note** If you do not enable VDI mode for non-persistent VDI sessions, certain features do not work, such as back-up/restore and LKG.</span></span>

 

## <span data-ttu-id="8eca9-148">管理员备份和还原</span><span class="sxs-lookup"><span data-stu-id="8eca9-148">Administrative Backup and Restore</span></span>


<span data-ttu-id="8eca9-149">通过使用 UevTemplateProfile PowerShell cmdlet 将设置位置模板放在 "**备份**" 或 "**漫游" （默认）** 配置文件中，你可以在用户采用新设备时还原其他设置。</span><span class="sxs-lookup"><span data-stu-id="8eca9-149">You can restore additional settings when a user adopts a new device by putting a settings location template in **backup** or **roam (default)** profile using the Set-UevTemplateProfile PowerShell cmdlet.</span></span> <span data-ttu-id="8eca9-150">除了用户设置外，此功能还允许将计算机设置与新计算机同步。</span><span class="sxs-lookup"><span data-stu-id="8eca9-150">This lets computer settings sync to the new computer, in addition to user settings.</span></span> <span data-ttu-id="8eca9-151">为该设备备份分配给备份配置文件的模板，并基于每台设备进行配置。</span><span class="sxs-lookup"><span data-stu-id="8eca9-151">Templates assigned to the backup profile are backed up for that device and configured on a per-device basis.</span></span> <span data-ttu-id="8eca9-152">[在 ue-v 2 中管理管理备份和还原。 x](manage-administrative-backup-and-restore-in-ue-v-2x-new-topic-for-21.md)提供详细信息。</span><span class="sxs-lookup"><span data-stu-id="8eca9-152">[Manage Administrative Backup and Restore in UE-V 2.x](manage-administrative-backup-and-restore-in-ue-v-2x-new-topic-for-21.md) provides more information.</span></span>

## <span data-ttu-id="8eca9-153">其他 Windows 设置的同步</span><span class="sxs-lookup"><span data-stu-id="8eca9-153">Synchronization for Additional Windows Settings</span></span>


<span data-ttu-id="8eca9-154">UE-V 现在将同步触摸键盘个性化设置、拼写词典，并启用应用切换 "最近的应用" 和 "屏幕边缘" 设置，以便在 Windows 8 和 Windows 8.1 设备之间进行同步。</span><span class="sxs-lookup"><span data-stu-id="8eca9-154">UE-V now synchronizes touch keyboard personalization, the spelling dictionary, and enables the App Switching for recent apps and screen edge settings to synchronize between Windows 8 and Windows 8.1 devices.</span></span>






## <span data-ttu-id="8eca9-155">相关主题</span><span class="sxs-lookup"><span data-stu-id="8eca9-155">Related topics</span></span>


[<span data-ttu-id="8eca9-156">UE-V 2.x 入门</span><span class="sxs-lookup"><span data-stu-id="8eca9-156">Get Started with UE-V 2.x</span></span>](get-started-with-ue-v-2x-new-uevv2.md)

[<span data-ttu-id="8eca9-157">准备 UE-V 2. x 部署</span><span class="sxs-lookup"><span data-stu-id="8eca9-157">Prepare a UE-V 2.x Deployment</span></span>](prepare-a-ue-v-2x-deployment-new-uevv2.md)

[<span data-ttu-id="8eca9-158">Microsoft 用户体验虚拟化 (UE-V) 2.1 发行说明</span><span class="sxs-lookup"><span data-stu-id="8eca9-158">Microsoft User Experience Virtualization (UE-V) 2.1 Release Notes</span></span>](microsoft-user-experience-virtualization--ue-v--21-release-notesuevv21.md)

 

 





