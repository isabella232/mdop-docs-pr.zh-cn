---
title: 在 UE-V 2. x 中管理管理备份和还原
description: 在 UE-V 2. x 中管理管理备份和还原
author: dansimp
ms.assetid: 2eb5ae75-65e5-4afc-adb6-4e83cf4364ae
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 11c168b54b71731c51417b2b7c4737c85f42035a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804158"
---
# <span data-ttu-id="3e5da-103">在 UE-V 2. x 中管理管理备份和还原</span><span class="sxs-lookup"><span data-stu-id="3e5da-103">Manage Administrative Backup and Restore in UE-V 2.x</span></span>


<span data-ttu-id="3e5da-104">作为 Microsoft 用户体验虚拟化（UE-V）2.0、2.1 或 2.1 SP1 的管理员，你可以将应用程序和 Windows 设置还原到其原始状态。</span><span class="sxs-lookup"><span data-stu-id="3e5da-104">As an administrator of Microsoft User Experience Virtualization (UE-V) 2.0, 2.1, or 2.1 SP1, you can restore application and Windows settings to their original state.</span></span> <span data-ttu-id="3e5da-105">此外，在 UE-V 2.1 中，你还可以在用户采用新设备时还原其他设置。</span><span class="sxs-lookup"><span data-stu-id="3e5da-105">And new in UE-V 2.1, you can also restore additional settings when a user adopts a new device.</span></span>

## <span data-ttu-id="3e5da-106">当用户采用新设备时，在 UE-V 2.1 或 UE-V 2.1 SP1 中还原设置</span><span class="sxs-lookup"><span data-stu-id="3e5da-106">Restore Settings in UE-V 2.1 or UE-V 2.1 SP1 when a User Adopts a New Device</span></span>


<span data-ttu-id="3e5da-107">若要在用户使用新设备时还原设置，可以使用 UevTemplateProfile PowerShell cmdlet 将设置位置模板放置在 "**备份**" 或 "**漫游" （默认）** 配置文件中。</span><span class="sxs-lookup"><span data-stu-id="3e5da-107">To restore settings when a user adopts a new device, you can put a settings location template in **backup** or **roam (default)** profile using the Set-UevTemplateProfile PowerShell cmdlet.</span></span> <span data-ttu-id="3e5da-108">除了用户设置外，此功能还允许将计算机设置与新计算机同步。</span><span class="sxs-lookup"><span data-stu-id="3e5da-108">This lets computer settings sync to the new computer, in addition to user settings.</span></span> <span data-ttu-id="3e5da-109">为该设备备份分配给备份配置文件的模板，并基于每台设备进行配置。</span><span class="sxs-lookup"><span data-stu-id="3e5da-109">Templates assigned to the backup profile are backed up for that device and configured on a per-device basis.</span></span> <span data-ttu-id="3e5da-110">若要备份模板的设置，请在 Windows PowerShell 中使用以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="3e5da-110">To backup settings for a template, use the following cmdlet in Windows PowerShell:</span></span>

``` syntax
Set-UevTemplateProfile -ID <TemplateID> -Profile <backup>
```

-   <span data-ttu-id="3e5da-111">&lt;TemplateID &gt; 是 Ue-v 模板 ID</span><span class="sxs-lookup"><span data-stu-id="3e5da-111">&lt;TemplateID&gt; is the UE-V Template ID</span></span>

-   <span data-ttu-id="3e5da-112">&lt;备份 &gt; 可以是备份或漫游</span><span class="sxs-lookup"><span data-stu-id="3e5da-112">&lt;backup&gt; can either be Backup or Roaming</span></span>

<span data-ttu-id="3e5da-113">当用户的域、用户名和设备名称全部匹配时，当替换用户的设备时，UE-V 会自动还原设置。</span><span class="sxs-lookup"><span data-stu-id="3e5da-113">When replacing a user’s device UE-V automatically restores settings if the user’s domain, username, and device name all match.</span></span> <span data-ttu-id="3e5da-114">将自动在设备上还原所有已同步和任何备份数据。</span><span class="sxs-lookup"><span data-stu-id="3e5da-114">All synchronized and any backup data is restored on the device automatically.</span></span>

<span data-ttu-id="3e5da-115">你还可以使用新的 PowerShell cmdlet UevBackup 还原其他设备中的设置。</span><span class="sxs-lookup"><span data-stu-id="3e5da-115">You can also use the new PowerShell cmdlet, Restore-UevBackup, to restore settings from a different device.</span></span> <span data-ttu-id="3e5da-116">若要克隆新设备的设置程序包，请使用 Windows PowerShell 中的以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="3e5da-116">To clone the settings packages for the new device, use the following cmdlet in Windows PowerShell:</span></span>

``` syntax
Restore-UevBackup –Machine <MachineName>
```

<span data-ttu-id="3e5da-117">其中 &lt; 计算机 &gt; 名是设备的计算机名。</span><span class="sxs-lookup"><span data-stu-id="3e5da-117">where &lt;MachineName&gt; is the computer name of the device.</span></span>

<span data-ttu-id="3e5da-118">包含许多应用程序的模板（如 Office 2013 模板）既可以包含在漫游（默认）还是备份配置文件中。</span><span class="sxs-lookup"><span data-stu-id="3e5da-118">Templates such as the Office 2013 template that include many applications can either all be included in the roamed (default) or backed up profile.</span></span> <span data-ttu-id="3e5da-119">模板套件中的单个应用关注组。</span><span class="sxs-lookup"><span data-stu-id="3e5da-119">Individual apps in a template suite follow the group.</span></span> <span data-ttu-id="3e5da-120">Office 2013 内置模板包括漫游和仅备份设置。</span><span class="sxs-lookup"><span data-stu-id="3e5da-120">Office 2013 in-box templates include both roaming and backup-only settings.</span></span> <span data-ttu-id="3e5da-121">仅备份设置不能包含在漫游配置文件中。</span><span class="sxs-lookup"><span data-stu-id="3e5da-121">Backup-only settings cannot be included in a roaming profile.</span></span>

<span data-ttu-id="3e5da-122">作为 "备份/还原" 功能的一部分，UE-V 将 "**最后一次正确的" （LKG）** 添加到用于回退到设置的选项。</span><span class="sxs-lookup"><span data-stu-id="3e5da-122">As part of the Backup/Restore feature, UE-V added **last known good (LKG)** to the options for rolling back to settings.</span></span> <span data-ttu-id="3e5da-123">在此版本中，你可以返回到原始设置或 LKG 设置。</span><span class="sxs-lookup"><span data-stu-id="3e5da-123">In this release, you can roll back to either the original settings or LKG settings.</span></span> <span data-ttu-id="3e5da-124">LKG 设置允许用户回退到设置的前 UE-V 状态之前的中间和稳定点。</span><span class="sxs-lookup"><span data-stu-id="3e5da-124">The LKG settings let users roll back to an intermediate and stable point ahead of the pre-UE-V state of the settings.</span></span>

### <span data-ttu-id="3e5da-125">如何通过 UE-V 备份/还原模板</span><span class="sxs-lookup"><span data-stu-id="3e5da-125">How to Backup/Restore Templates with UE-V</span></span>

<span data-ttu-id="3e5da-126">以下是 UE-V 的主要备份和还原组件：</span><span class="sxs-lookup"><span data-stu-id="3e5da-126">These are the key backup and restore components of UE-V:</span></span>

-   <span data-ttu-id="3e5da-127">模板配置文件</span><span class="sxs-lookup"><span data-stu-id="3e5da-127">Template profiles</span></span>

-   <span data-ttu-id="3e5da-128">设置存储位置模板内的设置程序包位置</span><span class="sxs-lookup"><span data-stu-id="3e5da-128">Settings packages location within the Settings Storage Location template</span></span>

-   <span data-ttu-id="3e5da-129">备份触发器</span><span class="sxs-lookup"><span data-stu-id="3e5da-129">Backup trigger</span></span>

-   <span data-ttu-id="3e5da-130">如何还原设置</span><span class="sxs-lookup"><span data-stu-id="3e5da-130">How settings are restored</span></span>

**<span data-ttu-id="3e5da-131">模板配置文件</span><span class="sxs-lookup"><span data-stu-id="3e5da-131">Template Profiles</span></span>**

<span data-ttu-id="3e5da-132">在设备上注册模板或通过 PowerShell/WMI 配置实用程序发布注册时，将定义 UE-V 模板配置文件。</span><span class="sxs-lookup"><span data-stu-id="3e5da-132">A UE-V template profile is defined when the template is registered on the device or post registration through the PowerShell/WMI configuration utility.</span></span> <span data-ttu-id="3e5da-133">配置文件类型包括：</span><span class="sxs-lookup"><span data-stu-id="3e5da-133">The profile types include:</span></span>

-   <span data-ttu-id="3e5da-134">漫游（默认）</span><span class="sxs-lookup"><span data-stu-id="3e5da-134">Roaming (default)</span></span>

-   <span data-ttu-id="3e5da-135">备份</span><span class="sxs-lookup"><span data-stu-id="3e5da-135">Backup</span></span>

-   <span data-ttu-id="3e5da-136">BackupOnly</span><span class="sxs-lookup"><span data-stu-id="3e5da-136">BackupOnly</span></span>

<span data-ttu-id="3e5da-137">除非另行指定，否则在注册后，所有模板都将包含在漫游配置文件中。</span><span class="sxs-lookup"><span data-stu-id="3e5da-137">All templates are included in the roaming profile when registered unless otherwise specified.</span></span> <span data-ttu-id="3e5da-138">这些模板将设置同步到启用了相应模板的所有 UE-V 启用的设备。</span><span class="sxs-lookup"><span data-stu-id="3e5da-138">These templates synchronize settings to all UE-V enabled devices with the corresponding template enabled.</span></span>

<span data-ttu-id="3e5da-139">可使用 UevTemplateProfile cmdlet 将模板添加到具有 PowerShell 或 WMI 的备份配置文件。</span><span class="sxs-lookup"><span data-stu-id="3e5da-139">Templates can be added to the Backup Profile with PowerShell or WMI using the Set-UevTemplateProfile cmdlet.</span></span> <span data-ttu-id="3e5da-140">备份配置文件中的模板将这些设置备份到 "特殊设备名称" 目录中的 "设置" 存储位置。</span><span class="sxs-lookup"><span data-stu-id="3e5da-140">Templates in the Backup Profile back up these settings to the Settings Storage Location in a special Device name directory.</span></span> <span data-ttu-id="3e5da-141">指定的设置将备份到此位置。</span><span class="sxs-lookup"><span data-stu-id="3e5da-141">Specified settings are backed up to this location.</span></span>

<span data-ttu-id="3e5da-142">指定 BackupOnly 的模板包括特定于该设备的设置，除非显式还原，否则不应进行同步。</span><span class="sxs-lookup"><span data-stu-id="3e5da-142">Templates designated BackupOnly include settings specific to that device that should not be synchronized unless explicitly restored.</span></span> <span data-ttu-id="3e5da-143">这些设置存储在设置存储位置上的同一特定于设备的设置程序包位置，作为 Backedup 设置。</span><span class="sxs-lookup"><span data-stu-id="3e5da-143">These settings are stored in the same device-specific settings package location on the settings storage location as the Backedup Settings.</span></span> <span data-ttu-id="3e5da-144">这些模板具有嵌入在模板中的特殊标识符，用于指定这些模板应属于此配置文件的一部分。</span><span class="sxs-lookup"><span data-stu-id="3e5da-144">These templates have a special identifier embedded in the template that specifies they should be part of this profile.</span></span>

**<span data-ttu-id="3e5da-145">设置存储位置模板内的设置程序包位置</span><span class="sxs-lookup"><span data-stu-id="3e5da-145">Settings packages location within the Settings Storage Location template</span></span>**

<span data-ttu-id="3e5da-146">漫游配置文件设置存储在设置存储位置。</span><span class="sxs-lookup"><span data-stu-id="3e5da-146">Roaming Profile settings are stored on the settings storage location.</span></span> <span data-ttu-id="3e5da-147">分配给备份或 BackupOnly 配置文件的模板将其设置存储在特殊设备名称目录中的设置存储位置。</span><span class="sxs-lookup"><span data-stu-id="3e5da-147">Templates assigned to the Backup or the BackupOnly profile store their settings to the Settings Storage Location in a special Device name directory.</span></span> <span data-ttu-id="3e5da-148">每台具有这些配置文件中的模板的设备都有其自己的设备名称。</span><span class="sxs-lookup"><span data-stu-id="3e5da-148">Each device with templates in these profiles has its own device name.</span></span> <span data-ttu-id="3e5da-149">UE-V 不会清理这些目录。</span><span class="sxs-lookup"><span data-stu-id="3e5da-149">UE-V does not clean up these directories.</span></span>

**<span data-ttu-id="3e5da-150">备份触发器</span><span class="sxs-lookup"><span data-stu-id="3e5da-150">Backup trigger</span></span>**

<span data-ttu-id="3e5da-151">备份由触发 UE-V 同步的相同事件触发。</span><span class="sxs-lookup"><span data-stu-id="3e5da-151">Backup is triggered by the same events that trigger a UE-V synchronization.</span></span>

**<span data-ttu-id="3e5da-152">如何还原设置</span><span class="sxs-lookup"><span data-stu-id="3e5da-152">How settings are restored</span></span>**

<span data-ttu-id="3e5da-153">还原用户的设备会将当前注册的模板设置从其他设备的备份文件夹和所有同步设置还原到当前计算机。</span><span class="sxs-lookup"><span data-stu-id="3e5da-153">Restoring a user’s device restores the currently registered Template’s settings from another device’s backup folder and all synchronized settings to the current machine.</span></span> <span data-ttu-id="3e5da-154">可通过以下两种方式还原设置：</span><span class="sxs-lookup"><span data-stu-id="3e5da-154">Settings are restored in these two ways:</span></span>

-   **<span data-ttu-id="3e5da-155">自动还原</span><span class="sxs-lookup"><span data-stu-id="3e5da-155">Automatic restore</span></span>**

    <span data-ttu-id="3e5da-156">如果用户的 UE-V 设置存储路径、域和计算机名称与当前用户匹配，则该用户的所有设置都将同步，并且仅应用最新设置。</span><span class="sxs-lookup"><span data-stu-id="3e5da-156">If the user’s UE-V settings storage path, domain, and Computer name match the current user then all of the settings for that user are synchronized, with only the latest settings applied.</span></span> <span data-ttu-id="3e5da-157">如果用户首次登录到新设备并满足这些条件，则设置数据将应用到该设备。</span><span class="sxs-lookup"><span data-stu-id="3e5da-157">If a user logs on to a new device for the first time and these criteria are met, the settings data is applied to that device.</span></span>

    **<span data-ttu-id="3e5da-158">注意</span><span class="sxs-lookup"><span data-stu-id="3e5da-158">Note</span></span>**  
    <span data-ttu-id="3e5da-159">辅助功能和 Windows 桌面设置要求用户重新登录到要应用的 Windows。</span><span class="sxs-lookup"><span data-stu-id="3e5da-159">Accessibility and Windows Desktop settings require the user to re-logon to Windows to be applied.</span></span>



-   **<span data-ttu-id="3e5da-160">手动还原</span><span class="sxs-lookup"><span data-stu-id="3e5da-160">Manual Restore</span></span>**

    <span data-ttu-id="3e5da-161">如果你想要在刷新期间通过还原设备来帮助用户，你可以选择使用 UevBackup cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3e5da-161">If you want to assist users by restoring a device during a refresh, you can choose to use the Restore-UevBackup cmdlet.</span></span> <span data-ttu-id="3e5da-162">此命令会导致从设置存储位置下载用户的设置。</span><span class="sxs-lookup"><span data-stu-id="3e5da-162">This command causes the user’s settings to be downloaded from the Settings Storage Location.</span></span>

## <span data-ttu-id="3e5da-163">将应用程序和 Windows 设置还原为原始状态</span><span class="sxs-lookup"><span data-stu-id="3e5da-163">Restore Application and Windows Settings to Original State</span></span>


<span data-ttu-id="3e5da-164">WMI 和 Windows PowerShell 命令允许你在安装 UE-V Agent 后首次启动应用程序时，将应用程序和 Windows 设置还原到计算机上的设置值。</span><span class="sxs-lookup"><span data-stu-id="3e5da-164">WMI and Windows PowerShell commands let you restore application and Windows settings to the settings values that were on the computer the first time that the application started after the UE-V Agent was installed.</span></span> <span data-ttu-id="3e5da-165">将在每个应用程序或 Windows 设置基础上执行此还原操作。</span><span class="sxs-lookup"><span data-stu-id="3e5da-165">This restoring action is performed on a per-application or Windows settings basis.</span></span> <span data-ttu-id="3e5da-166">下次应用程序运行时，将恢复这些设置，或者当用户登录到操作系统时还原设置。</span><span class="sxs-lookup"><span data-stu-id="3e5da-166">The settings are restored the next time that the application runs, or the settings are restored when the user logs on to the operating system.</span></span>

**<span data-ttu-id="3e5da-167">将应用程序设置和 Windows 设置还原为适用于 UE-V 2 的 Windows PowerShell。 x</span><span class="sxs-lookup"><span data-stu-id="3e5da-167">To restore application settings and Windows settings with Windows PowerShell for UE-V 2.x</span></span>**

1.  <span data-ttu-id="3e5da-168">打开 Windows PowerShell 窗口。</span><span class="sxs-lookup"><span data-stu-id="3e5da-168">Open the Windows PowerShell window.</span></span>

2.  <span data-ttu-id="3e5da-169">输入以下 Windows PowerShell cmdlet 以还原应用程序设置和 Windows 设置。</span><span class="sxs-lookup"><span data-stu-id="3e5da-169">Enter the following Windows PowerShell cmdlet to restore the application settings and Windows settings.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><strong><span data-ttu-id="3e5da-170">Windows PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="3e5da-170">Windows PowerShell cmdlet</span></span></strong></th>
    <th align="left"><strong><span data-ttu-id="3e5da-171">描述</span><span class="sxs-lookup"><span data-stu-id="3e5da-171">Description</span></span></strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><code>Restore-UevUserSetting -&lt;TemplateID&gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="3e5da-172">还原应用程序的用户设置或还原一组 Windows 设置。</span><span class="sxs-lookup"><span data-stu-id="3e5da-172">Restores the user settings for an application or restores a group of Windows settings.</span></span></p></td>
    </tr>
    </tbody>
    </table>



**<span data-ttu-id="3e5da-173">通过 WMI 还原应用程序设置和 Windows 设置</span><span class="sxs-lookup"><span data-stu-id="3e5da-173">To restore application settings and Windows settings with WMI</span></span>**

1.  <span data-ttu-id="3e5da-174">打开 Windows PowerShell 窗口。</span><span class="sxs-lookup"><span data-stu-id="3e5da-174">Open a Windows PowerShell window.</span></span>

2.  <span data-ttu-id="3e5da-175">输入以下 WMI 命令以还原应用程序设置和 Windows 设置。</span><span class="sxs-lookup"><span data-stu-id="3e5da-175">Enter the following WMI command to restore application settings and Windows settings.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><strong><span data-ttu-id="3e5da-176">WMI 命令</span><span class="sxs-lookup"><span data-stu-id="3e5da-176">WMI command</span></span></strong></th>
    <th align="left"><strong><span data-ttu-id="3e5da-177">描述</span><span class="sxs-lookup"><span data-stu-id="3e5da-177">Description</span></span></strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class UserSettings -Name RestoreByTemplateId -ArgumentList &lt;template_ID&gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="3e5da-178">还原应用程序的用户设置或还原一组 Windows 设置。</span><span class="sxs-lookup"><span data-stu-id="3e5da-178">Restores the user settings for an application or restores a group of Windows settings.</span></span></p></td>
    </tr>
    </tbody>
    </table>



~~~
**Note**  
UE-V does not provide a settings rollback for Windows apps.
~~~








## <span data-ttu-id="3e5da-179">相关主题</span><span class="sxs-lookup"><span data-stu-id="3e5da-179">Related topics</span></span>


[<span data-ttu-id="3e5da-180">管理具有 Windows PowerShell 和 WMI 的 UE-V 2。</span><span class="sxs-lookup"><span data-stu-id="3e5da-180">Administering UE-V 2.x with Windows PowerShell and WMI</span></span>](administering-ue-v-2x-with-windows-powershell-and-wmi-both-uevv2.md)

[<span data-ttu-id="3e5da-181">管理 UE-V 2. x</span><span class="sxs-lookup"><span data-stu-id="3e5da-181">Administering UE-V 2.x</span></span>](administering-ue-v-2x-new-uevv2.md)









