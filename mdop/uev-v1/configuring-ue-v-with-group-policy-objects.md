---
title: 使用组策略对象配置 UE-V
description: 使用组策略对象配置 UE-V
author: dansimp
ms.assetid: 5c9be706-a05f-4397-9a38-e6b73ebff1e5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7e479e6bef1a2b38cf822ffca19ed4220b0c59fe
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804020"
---
# <span data-ttu-id="d2f09-103">使用组策略对象配置 UE-V</span><span class="sxs-lookup"><span data-stu-id="d2f09-103">Configuring UE-V with Group Policy Objects</span></span>


<span data-ttu-id="d2f09-104">某些 Microsoft 用户体验虚拟化（UE-V）组策略设置可为计算机定义，而其他用户可以为用户定义。</span><span class="sxs-lookup"><span data-stu-id="d2f09-104">Some Microsoft User Experience Virtualization (UE-V) Group Policy settings can be defined for computers and others can be defined for users.</span></span> <span data-ttu-id="d2f09-105">可以为计算机或用户定义 UE-V agent 配置策略设置。</span><span class="sxs-lookup"><span data-stu-id="d2f09-105">UE-V agent configuration policy settings can be defined for computers or users.</span></span> <span data-ttu-id="d2f09-106">有关如何安装 UE-V 组策略 ADMX 文件的信息，请参阅[安装 Ue-v 组策略 Admx 模板](installing-the-ue-v-group-policy-admx-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="d2f09-106">For information about how to install UE-V Group Policy ADMX files, see [Installing the UE-V Group Policy ADMX Templates](installing-the-ue-v-group-policy-admx-templates.md).</span></span>

<span data-ttu-id="d2f09-107">可为 UE-V 配置以下策略设置：</span><span class="sxs-lookup"><span data-stu-id="d2f09-107">The following policy settings can be configured for UE-V:</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="d2f09-108">策略设置名称</span><span class="sxs-lookup"><span data-stu-id="d2f09-108">Policy setting name</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="d2f09-109">目标</span><span class="sxs-lookup"><span data-stu-id="d2f09-109">Target</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="d2f09-110">策略设置说明</span><span class="sxs-lookup"><span data-stu-id="d2f09-110">Policy setting description</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="d2f09-111">配置选项</span><span class="sxs-lookup"><span data-stu-id="d2f09-111">Configuration options</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d2f09-112">使用用户体验虚拟化（UE-V）</span><span class="sxs-lookup"><span data-stu-id="d2f09-112">Use User Experience Virtualization (UE-V)</span></span></p></td>
<td align="left"><p><span data-ttu-id="d2f09-113">计算机和用户</span><span class="sxs-lookup"><span data-stu-id="d2f09-113">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="d2f09-114">通过此策略设置，你可以启用或禁用用户体验虚拟化（UE-V）。</span><span class="sxs-lookup"><span data-stu-id="d2f09-114">This policy setting allows you to enable or disable User Experience Virtualization (UE-V).</span></span></p></td>
<td align="left"><p><span data-ttu-id="d2f09-115">启用或禁用此策略设置。</span><span class="sxs-lookup"><span data-stu-id="d2f09-115">Enable or disable this policy setting.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d2f09-116">设置存储路径</span><span class="sxs-lookup"><span data-stu-id="d2f09-116">Settings storage path</span></span></p></td>
<td align="left"><p><span data-ttu-id="d2f09-117">计算机和用户</span><span class="sxs-lookup"><span data-stu-id="d2f09-117">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="d2f09-118">此策略设置配置将存储用户设置的位置。</span><span class="sxs-lookup"><span data-stu-id="d2f09-118">This policy setting configures where the user settings will be stored.</span></span></p></td>
<td align="left"><p><span data-ttu-id="d2f09-119">提供通用命名约定（UNC）路径和变量（如 \Server\SettingsShare%username%.）</span><span class="sxs-lookup"><span data-stu-id="d2f09-119">Provide a Universal Naming Convention (UNC) path and variables such as \Server\SettingsShare%username%.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d2f09-120">设置模板目录路径</span><span class="sxs-lookup"><span data-stu-id="d2f09-120">Settings template catalog path</span></span></p></td>
<td align="left"><p><span data-ttu-id="d2f09-121">仅限计算机</span><span class="sxs-lookup"><span data-stu-id="d2f09-121">Computers Only</span></span></p></td>
<td align="left"><p><span data-ttu-id="d2f09-122">此策略设置配置自定义设置位置模板的存储位置。</span><span class="sxs-lookup"><span data-stu-id="d2f09-122">This policy setting configures where custom settings location templates are stored.</span></span> <span data-ttu-id="d2f09-123">此策略设置还配置目录是否将用于替换随 UE-V agent 一起安装的默认 Microsoft 模板。</span><span class="sxs-lookup"><span data-stu-id="d2f09-123">This policy setting also configures whether the catalog will be used to replace the default Microsoft templates that are installed with the UE-V agent.</span></span></p></td>
<td align="left"><p><span data-ttu-id="d2f09-124">在计算机上提供通用命名约定（UNC）路径，如 \Server\TemplateShare 或文件夹位置。</span><span class="sxs-lookup"><span data-stu-id="d2f09-124">Provide a Universal Naming Convention (UNC) path such as \Server\TemplateShare or a folder location on the computer.</span></span></p>
<p></p>
<p><span data-ttu-id="d2f09-125">选中复选框以替换默认的 Microsoft 模板。</span><span class="sxs-lookup"><span data-stu-id="d2f09-125">Select the check box to replace the default Microsoft templates.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d2f09-126">不使用脱机文件</span><span class="sxs-lookup"><span data-stu-id="d2f09-126">Do not use Offline Files</span></span></p></td>
<td align="left"><p><span data-ttu-id="d2f09-127">计算机和用户</span><span class="sxs-lookup"><span data-stu-id="d2f09-127">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="d2f09-128">通过此策略设置，你可以配置 UE-V 是否将使用 Windows 脱机文件功能。</span><span class="sxs-lookup"><span data-stu-id="d2f09-128">This policy setting allows you to configure whether UE-V will use the Windows Offline Files feature.</span></span> <span data-ttu-id="d2f09-129">此策略设置还允许你启用在用户设置的导入延迟时出现的通知。</span><span class="sxs-lookup"><span data-stu-id="d2f09-129">This policy setting also allows you to enable notification to occur when the import of user settings is delayed.</span></span></p></td>
<td align="left"><p><span data-ttu-id="d2f09-130">若要将 UE-V Agent 配置为不使用脱机文件，请启用此设置。</span><span class="sxs-lookup"><span data-stu-id="d2f09-130">To configure the UE-V Agent to not use offline files, enable this setting.</span></span></p>
<p></p>
<p><span data-ttu-id="d2f09-131">指定在设置导入延迟时是否应提供通知。</span><span class="sxs-lookup"><span data-stu-id="d2f09-131">Specify if notifications should be given when settings import is delayed.</span></span></p>
<p></p>
<p><span data-ttu-id="d2f09-132">指定在通知出现之前等待的时间长度（以秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="d2f09-132">Specify the length of time in seconds to wait before the notification appears.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d2f09-133">同步超时</span><span class="sxs-lookup"><span data-stu-id="d2f09-133">Synchronization timeout</span></span></p></td>
<td align="left"><p><span data-ttu-id="d2f09-134">计算机和用户</span><span class="sxs-lookup"><span data-stu-id="d2f09-134">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="d2f09-135">此策略设置配置从远程设置位置检索用户设置时，计算机超时之前等待的毫秒数。</span><span class="sxs-lookup"><span data-stu-id="d2f09-135">This policy setting configures the number of milliseconds that the computer waits before a timeout when retrieving user settings from the remote settings location.</span></span> <span data-ttu-id="d2f09-136">如果 "远程存储" 位置不可用，则应用程序启动将延迟此毫秒。</span><span class="sxs-lookup"><span data-stu-id="d2f09-136">If the remote storage location is unavailable, the application launch is delayed by this many milliseconds.</span></span></p></td>
<td align="left"><p><span data-ttu-id="d2f09-137">指定首选同步超时值（以毫秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="d2f09-137">Specify the preferred synchronization timeout in milliseconds.</span></span> <span data-ttu-id="d2f09-138">2000毫秒的默认值。</span><span class="sxs-lookup"><span data-stu-id="d2f09-138">The default value of 2000 milliseconds.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d2f09-139">程序包大小警告阈值</span><span class="sxs-lookup"><span data-stu-id="d2f09-139">Package size warning threshold</span></span></p></td>
<td align="left"><p><span data-ttu-id="d2f09-140">计算机和用户</span><span class="sxs-lookup"><span data-stu-id="d2f09-140">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="d2f09-141">通过此策略设置，你可以配置 UE-V agent，以便在设置包文件大小达到定义的阈值时进行报告。</span><span class="sxs-lookup"><span data-stu-id="d2f09-141">This policy setting allows you to configure the UE-V agent to report when a settings package file size reaches a defined threshold.</span></span></p></td>
<td align="left"><p><span data-ttu-id="d2f09-142">指定设置包大小的首选阈值（以 kb 为单位）。</span><span class="sxs-lookup"><span data-stu-id="d2f09-142">Specified the preferred threshold for settings package sizes in kilobytes.</span></span></p>
<p><span data-ttu-id="d2f09-143">默认情况下，UE-V agent 没有程序包文件大小阈值。</span><span class="sxs-lookup"><span data-stu-id="d2f09-143">By default, the UE-V agent does not have a package file size threshold.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d2f09-144">漫游应用程序设置</span><span class="sxs-lookup"><span data-stu-id="d2f09-144">Roaming Application settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="d2f09-145">仅限用户</span><span class="sxs-lookup"><span data-stu-id="d2f09-145">Users Only</span></span></p></td>
<td align="left"><p><span data-ttu-id="d2f09-146">此策略设置配置应用程序的用户设置的漫游。</span><span class="sxs-lookup"><span data-stu-id="d2f09-146">This policy setting configures the roaming of user settings of applications.</span></span></p></td>
<td align="left"><p><span data-ttu-id="d2f09-147">选择将在计算机之间漫游的 Windows 设置。</span><span class="sxs-lookup"><span data-stu-id="d2f09-147">Select which Windows settings will roam between computers.</span></span></p>
<p><span data-ttu-id="d2f09-148">默认情况下，由 UE-V 提供的具有设置模板的应用程序的用户设置是在计算机之间漫游。</span><span class="sxs-lookup"><span data-stu-id="d2f09-148">By default, the user settings of applications with settings template provided by UE-V are roamed between computers.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d2f09-149">漫游 Windows 设置</span><span class="sxs-lookup"><span data-stu-id="d2f09-149">Roaming Windows settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="d2f09-150">仅限用户</span><span class="sxs-lookup"><span data-stu-id="d2f09-150">Users Only</span></span></p></td>
<td align="left"><p><span data-ttu-id="d2f09-151">此策略设置配置 Windows 设置的漫游。</span><span class="sxs-lookup"><span data-stu-id="d2f09-151">This policy setting configures the roaming of Windows settings.</span></span></p></td>
<td align="left"><p><span data-ttu-id="d2f09-152">选择将在计算机之间漫游的应用程序。</span><span class="sxs-lookup"><span data-stu-id="d2f09-152">Select which applications will roam between computers.</span></span></p>
<p><span data-ttu-id="d2f09-153">默认情况下，Windows 主题是在同一操作系统版本的计算机之间漫游。</span><span class="sxs-lookup"><span data-stu-id="d2f09-153">By default, Windows themes are roamed between computers of the same operating system version.</span></span> <span data-ttu-id="d2f09-154">Windows 桌面设置和 "轻松访问" 设置不在漫游。</span><span class="sxs-lookup"><span data-stu-id="d2f09-154">Windows desktop settings and Ease of Access settings are not roamed.</span></span></p></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="d2f09-155">配置以计算机为目标的策略</span><span class="sxs-lookup"><span data-stu-id="d2f09-155">To configure computer-targeted policies</span></span>**

1.  <span data-ttu-id="d2f09-156">在管理 UE-V 计算机的组策略的域控制器计算机上使用组策略管理控制台（GPMC）或高级组策略管理（AGPM）。</span><span class="sxs-lookup"><span data-stu-id="d2f09-156">Use the Group Policy Management Console (GPMC) or the Advanced Group Policy Management (AGPM) on the domain controller computer that manages Group Policy for UE-V computers.</span></span> <span data-ttu-id="d2f09-157">导航到 "**计算机配置**"，选择 "**策略**"，选择 "**管理模板**"，单击 " **Windows 组件**"，然后选择 " **Microsoft 用户体验虚拟化**"。</span><span class="sxs-lookup"><span data-stu-id="d2f09-157">Navigate to **Computer configuration**, select **Policies**, select **Administrative Templates**, click **Windows Components**, and then select **Microsoft User Experience Virtualization**.</span></span>

2.  <span data-ttu-id="d2f09-158">选择要编辑的策略设置。</span><span class="sxs-lookup"><span data-stu-id="d2f09-158">Select the policy setting to be edited.</span></span>

**<span data-ttu-id="d2f09-159">配置用户设定的策略</span><span class="sxs-lookup"><span data-stu-id="d2f09-159">To configure user-targeted policies</span></span>**

1.  <span data-ttu-id="d2f09-160">在管理 UE-V 的组策略的域控制器计算机上的 Microsoft 桌面优化包（MDOP）中使用组策略管理控制台（GPMC）或高级组策略管理（AGPM）工具。</span><span class="sxs-lookup"><span data-stu-id="d2f09-160">Use the Group Policy Management Console (GPMC) or the Advanced Group Policy Management (AGPM) tool in Microsoft Desktop Optimization Pack (MDOP) on the domain controller computer that manages Group Policy for UE-V.</span></span> <span data-ttu-id="d2f09-161">导航到 "**用户配置**"，选择 "**策略**"，选择 "**管理模板**"，单击 " **Windows 组件**"，然后选择 " **Microsoft 用户体验虚拟化**"。</span><span class="sxs-lookup"><span data-stu-id="d2f09-161">Navigate to **User configuration**, select **Policies**, select **Administrative Templates**, click **Windows Components**, and then select **Microsoft User Experience Virtualization**.</span></span>

2.  <span data-ttu-id="d2f09-162">选择已编辑的策略设置。</span><span class="sxs-lookup"><span data-stu-id="d2f09-162">Select the policy setting edited.</span></span>

<span data-ttu-id="d2f09-163">UE-V agent 使用以下优先级顺序确定同步。</span><span class="sxs-lookup"><span data-stu-id="d2f09-163">The UE-V agent uses the following order of precedence to determine synchronization.</span></span>

**<span data-ttu-id="d2f09-164">UE-V 设置的优先级顺序</span><span class="sxs-lookup"><span data-stu-id="d2f09-164">Order of precedence for UE-V settings</span></span>**

1.  <span data-ttu-id="d2f09-165">由组策略管理的由用户设定的设置-这些配置设置由 "组策略" 下的 "组策略" 存储在注册表项中 `HKEY_CURRENT_USER\Software\Policies\Microsoft\Uev\Agent\Configuration` 。</span><span class="sxs-lookup"><span data-stu-id="d2f09-165">User-targeted settings managed by Group Policy - These configuration settings are stored in the registry key by Group Policy under `HKEY_CURRENT_USER\Software\Policies\Microsoft\Uev\Agent\Configuration`.</span></span>

2.  <span data-ttu-id="d2f09-166">由组策略管理的由计算机设定的设置-这些配置设置由 "组策略" 下的 "组策略" 存储在注册表项中 `HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Uev\Agent\Configuration` 。</span><span class="sxs-lookup"><span data-stu-id="d2f09-166">Computer-targeted settings managed by Group Policy - These configuration settings are stored in the registry key by Group Policy under `HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Uev\Agent\Configuration`.</span></span>

3.  <span data-ttu-id="d2f09-167">当前用户使用 PowerShell 或 WMI 定义的配置设置-这些配置设置由 UE-V agent 在此注册表位置下存储： `HKEY_CURRENT_USER\Software\Microsoft\Uev\Agent\Configuration` 。</span><span class="sxs-lookup"><span data-stu-id="d2f09-167">Configuration settings defined by the current user using PowerShell or WMI - These configuration settings are stored by the UE-V agent under this registry location: `HKEY_CURRENT_USER\Software\Microsoft\Uev\Agent\Configuration`.</span></span>

4.  <span data-ttu-id="d2f09-168">使用 PowerShell 或 WMI 为计算机定义的配置设置。</span><span class="sxs-lookup"><span data-stu-id="d2f09-168">Configuration settings defined for the computer using PowerShell or WMI.</span></span> <span data-ttu-id="d2f09-169">这些配置设置由 UE-V agent 存储在 `HKEY_LOCAL_MACHINE \Software\Microsoft\Uev\Agent\Configuration` 。</span><span class="sxs-lookup"><span data-stu-id="d2f09-169">These configuration settings are stored by the UE-V agent under the `HKEY_LOCAL_MACHINE \Software\Microsoft\Uev\Agent\Configuration`.</span></span>

## <span data-ttu-id="d2f09-170">相关主题</span><span class="sxs-lookup"><span data-stu-id="d2f09-170">Related topics</span></span>


[<span data-ttu-id="d2f09-171">管理 UE-V 1.0</span><span class="sxs-lookup"><span data-stu-id="d2f09-171">Administering UE-V 1.0</span></span>](administering-ue-v-10.md)

[<span data-ttu-id="d2f09-172">UE-V 1.0 的操作</span><span class="sxs-lookup"><span data-stu-id="d2f09-172">Operations for UE-V 1.0</span></span>](operations-for-ue-v-10.md)

 

 





