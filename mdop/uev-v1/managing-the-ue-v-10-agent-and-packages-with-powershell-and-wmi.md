---
title: 使用 PowerShell 和 WMI 管理 UE-V 1.0 代理和程序包
description: 使用 PowerShell 和 WMI 管理 UE-V 1.0 代理和程序包
author: dansimp
ms.assetid: c8989b01-1769-4e69-82b1-4aadb261d2d5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 79268e3384aaaf08bdd4e9b92d74b039ce96596a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802160"
---
# <span data-ttu-id="04b71-103">使用 PowerShell 和 WMI 管理 UE-V 1.0 代理和程序包</span><span class="sxs-lookup"><span data-stu-id="04b71-103">Managing the UE-V 1.0 Agent and Packages with PowerShell and WMI</span></span>


<span data-ttu-id="04b71-104">你可以使用 WMI 和 PowerShell 来管理 Microsoft 用户体验虚拟化（UE-V） Agent 配置和同步行为。</span><span class="sxs-lookup"><span data-stu-id="04b71-104">You can use WMI and PowerShell to manage Microsoft User Experience Virtualization (UE-V) Agent configuration and synchronization behavior.</span></span>

**<span data-ttu-id="04b71-105">如何通过 PowerShell 部署 UE-V agent</span><span class="sxs-lookup"><span data-stu-id="04b71-105">How to deploy the UE-V agent with PowerShell</span></span>**

1.  <span data-ttu-id="04b71-106">在易于访问的网络共享中暂存 UE-V 安装程序文件。</span><span class="sxs-lookup"><span data-stu-id="04b71-106">Stage the UE-V installer file in an accessible network share.</span></span>

    **<span data-ttu-id="04b71-107">注意</span><span class="sxs-lookup"><span data-stu-id="04b71-107">Note</span></span>**  
    <span data-ttu-id="04b71-108">使用 AgentSetup.exe 部署32位和64位的 UE-V Agent 版本。</span><span class="sxs-lookup"><span data-stu-id="04b71-108">Use AgentSetup.exe to deploy both 32-bit and 64-bit versions of the UE-V Agent.</span></span> <span data-ttu-id="04b71-109">Windows Installer 文件版本、AgentSetupx86.msi 和 AgentSetupx64.msi 适用于每个体系结构。</span><span class="sxs-lookup"><span data-stu-id="04b71-109">Windows Installer Files versions, AgentSetupx86.msi and AgentSetupx64.msi, are available for each architecture.</span></span> <span data-ttu-id="04b71-110">若要在以后使用安装文件卸载 UE-V Agent，必须使用相同的文件类型。</span><span class="sxs-lookup"><span data-stu-id="04b71-110">To uninstall the UE-V Agent at a later time using the installation file, you must use the same file type.</span></span>



2.  <span data-ttu-id="04b71-111">使用以下 PowerShell 命令之一安装代理。</span><span class="sxs-lookup"><span data-stu-id="04b71-111">Use one of the following PowerShell commands to install the agent.</span></span>

    `& AgentSetup.exe /quiet /norestart /log "%temp%\UE-VAgentInstaller.log" SettingsStoragePath=\\server\settingsshare\%username%`

    `& msiexec.exe /i "<path to msi file>" /quiet /norestart /l*v "%temp%\UE-VAgentInstaller.log" SettingsStoragePath=\\server\settingsshare\%username%`

**<span data-ttu-id="04b71-112">如何通过 PowerShell 配置 UE-V Agent</span><span class="sxs-lookup"><span data-stu-id="04b71-112">How to configure the UE-V Agent with PowerShell</span></span>**

1.  <span data-ttu-id="04b71-113">使用具有管理员权限的帐户打开 PowerShell 窗口。</span><span class="sxs-lookup"><span data-stu-id="04b71-113">Use an account with administrator rights to open a PowerShell window.</span></span> <span data-ttu-id="04b71-114">使用以下命令导入 UE-V PowerShell 模块。</span><span class="sxs-lookup"><span data-stu-id="04b71-114">Import the UE-V PowerShell module by using the following command.</span></span>

    ``` syntax
    Import-module UEV
    ```

2.  <span data-ttu-id="04b71-115">使用以下 PowerShell 命令配置代理。</span><span class="sxs-lookup"><span data-stu-id="04b71-115">Use the following PowerShell commands to configure the agent.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p><strong><span data-ttu-id="04b71-116">PowerShell 命令</span><span class="sxs-lookup"><span data-stu-id="04b71-116">PowerShell command</span></span></strong></p></td>
    <td align="left"><p><strong><span data-ttu-id="04b71-117">描述</span><span class="sxs-lookup"><span data-stu-id="04b71-117">Description</span></span></strong></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="04b71-118">UevConfiguration</span><span class="sxs-lookup"><span data-stu-id="04b71-118">Get-UevConfiguration</span></span></p>
    <p></p></td>
    <td align="left"><p><span data-ttu-id="04b71-119">查看有效的 UE-V agent 设置。</span><span class="sxs-lookup"><span data-stu-id="04b71-119">View the effective UE-V agent settings.</span></span> <span data-ttu-id="04b71-120">特定于用户的设置优先于计算机设置。</span><span class="sxs-lookup"><span data-stu-id="04b71-120">User-specific settings have precedence over the computer settings.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="04b71-121">UevConfiguration-CurrentComputerUser</span><span class="sxs-lookup"><span data-stu-id="04b71-121">Get-UevConfiguration - CurrentComputerUser</span></span></p>
    <p></p></td>
    <td align="left"><p><span data-ttu-id="04b71-122">仅查看当前用户的 UE-V agent 设置值。</span><span class="sxs-lookup"><span data-stu-id="04b71-122">View the UE-V agent settings values for the current user only.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="04b71-123">UevConfiguration-计算机</span><span class="sxs-lookup"><span data-stu-id="04b71-123">Get-UevConfiguration -Computer</span></span></p></td>
    <td align="left"><p><span data-ttu-id="04b71-124">查看计算机上所有用户的 UE-V agent 配置设置值。</span><span class="sxs-lookup"><span data-stu-id="04b71-124">View the UE-V agent configuration settings values for all users on the computer.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="04b71-125">UevConfiguration-计算机-SettingsStoragePath &lt; 到 _settings_storage_location 的路径&gt;</span><span class="sxs-lookup"><span data-stu-id="04b71-125">Set-UevConfiguration -Computer -SettingsStoragePath &lt;path to _settings_storage_location&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="04b71-126">定义每台计算机的设置存储位置。</span><span class="sxs-lookup"><span data-stu-id="04b71-126">Define a per-computer settings storage location.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="04b71-127">UevConfiguration-CurrentComputerUser-SettingsStoragePath _settings_storage_location 的 &lt; 路径&gt;</span><span class="sxs-lookup"><span data-stu-id="04b71-127">Set-UevConfiguration -CurrentComputerUser -SettingsStoragePath &lt;path to _settings_storage_location&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="04b71-128">定义每用户设置存储位置。</span><span class="sxs-lookup"><span data-stu-id="04b71-128">Define a per-user settings storage location.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="04b71-129">设置-UevConfiguration-计算机-SyncTimeoutInMilliseconds &lt; 超时（毫秒）&gt;</span><span class="sxs-lookup"><span data-stu-id="04b71-129">Set-UevConfiguration -Computer -SyncTimeoutInMilliseconds &lt;timeout in milliseconds&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="04b71-130">设置同步超时（以毫秒为单位）</span><span class="sxs-lookup"><span data-stu-id="04b71-130">Set the synchronization timeout in milliseconds</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="04b71-131">UevConfiguration-CurrentComputerUser-SyncTimeoutInMilliseconds &lt; 超时（以毫秒为单位）&gt;</span><span class="sxs-lookup"><span data-stu-id="04b71-131">Set-UevConfiguration -CurrentComputerUser -SyncTimeoutInMilliseconds &lt;timeout in milliseconds&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="04b71-132">为当前用户设置同步超时。</span><span class="sxs-lookup"><span data-stu-id="04b71-132">Set the synchronization timeout for the current user.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="04b71-133">UevConfiguration-计算机-MaxPackageSizeInBytes &lt; 大小（以字节为单位）&gt;</span><span class="sxs-lookup"><span data-stu-id="04b71-133">Set-UevConfiguration -Computer -MaxPackageSizeInBytes &lt;size in bytes&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="04b71-134">配置 UE-V agent，以在设置包文件大小达到定义的阈值时进行报告。</span><span class="sxs-lookup"><span data-stu-id="04b71-134">Configure the UE-V agent to report when a settings package file size reaches a defined threshold.</span></span> <span data-ttu-id="04b71-135">设置阈值包大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="04b71-135">Set the threshold package size in bytes.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="04b71-136">UevConfiguration-CurrentComputerUser-MaxPackageSizeInBytes 的 &lt; 字节大小&gt;</span><span class="sxs-lookup"><span data-stu-id="04b71-136">Set-UevConfiguration -CurrentComputerUser -MaxPackageSizeInBytes &lt;size in bytes&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="04b71-137">为当前用户设置程序包大小警告阈值。</span><span class="sxs-lookup"><span data-stu-id="04b71-137">Set the package size warning threshold for the current user.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="04b71-138">UevConfiguration-计算机-SettingsTemplateCatalogPath &lt; 目录的路径&gt;</span><span class="sxs-lookup"><span data-stu-id="04b71-138">Set-UevConfiguration –Computer –SettingsTemplateCatalogPath &lt;path to catalog&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="04b71-139">设置 "设置" 模板的目录路径。</span><span class="sxs-lookup"><span data-stu-id="04b71-139">Set the settings template catalog path.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="04b71-140">UevConfiguration-Powerschool &lt; 同步方法&gt;</span><span class="sxs-lookup"><span data-stu-id="04b71-140">Set-UevConfiguration -Computer -SyncMethod &lt;sync method&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="04b71-141">设置同步方法： OfflineFiles 或 "无"。</span><span class="sxs-lookup"><span data-stu-id="04b71-141">Set the synchronization method: OfflineFiles or None.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="04b71-142">UevConfiguration-CurrentComputerUser-Powerschool &lt; sync 方法&gt;</span><span class="sxs-lookup"><span data-stu-id="04b71-142">Set-UevConfiguration -CurrentComputerUser -SyncMethod &lt;sync method&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="04b71-143">为当前用户设置同步方法： OfflineFiles 或 "无"。</span><span class="sxs-lookup"><span data-stu-id="04b71-143">Set the synchronization method for the current user: OfflineFiles or None.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="04b71-144">UEVConfiguration-计算机-EnableSettingsImportNotify</span><span class="sxs-lookup"><span data-stu-id="04b71-144">Set-UEVConfiguration -Computer –EnableSettingsImportNotify</span></span></p></td>
    <td align="left"><p><span data-ttu-id="04b71-145">启用用户设置导入延迟时出现的通知。</span><span class="sxs-lookup"><span data-stu-id="04b71-145">Enable notification to occur when the import of user settings is delayed.</span></span></p>
    <p><span data-ttu-id="04b71-146">使用– DisableSettingsImportNotify 禁用通知。</span><span class="sxs-lookup"><span data-stu-id="04b71-146">Use –DisableSettingsImportNotify to disable notification.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="04b71-147">Set-UEVConfiguration-CurrentComputerUser-EnableSettingsImportNotify</span><span class="sxs-lookup"><span data-stu-id="04b71-147">Set-UEVConfiguration - CurrentComputerUser -EnableSettingsImportNotify</span></span></p></td>
    <td align="left"><p><span data-ttu-id="04b71-148">当延迟导入用户设置时，对当前用户启用通知。</span><span class="sxs-lookup"><span data-stu-id="04b71-148">Enable notification for the current user when the import of user settings is delayed.</span></span></p>
    <p><span data-ttu-id="04b71-149">使用– DisableSettingsImportNotify 禁用通知。</span><span class="sxs-lookup"><span data-stu-id="04b71-149">Use –DisableSettingsImportNotify to disable notification.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="04b71-150">Set-UEVConfiguration-计算机-SettingsImportNotifyDelayInSeconds</span><span class="sxs-lookup"><span data-stu-id="04b71-150">Set-UEVConfiguration -Computer -SettingsImportNotifyDelayInSeconds</span></span></p></td>
    <td align="left"><p><span data-ttu-id="04b71-151">指定通知用户前的时间（以秒为单位）</span><span class="sxs-lookup"><span data-stu-id="04b71-151">Specify the time in seconds before the user is notified</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="04b71-152">Set-UEVConfiguration-CurrentComputerUser-SettingsImportNotifyDelayInSeconds</span><span class="sxs-lookup"><span data-stu-id="04b71-152">Set-UEVConfiguration - CurrentComputerUser -SettingsImportNotifyDelayInSeconds</span></span></p></td>
    <td align="left"><p><span data-ttu-id="04b71-153">指定在通知当前用户之前的时间（以秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="04b71-153">Specify the time in seconds before notification for the current user.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="04b71-154">UevConfiguration-计算机-DisableSync</span><span class="sxs-lookup"><span data-stu-id="04b71-154">Set-UevConfiguration –Computer –DisableSync</span></span></p></td>
    <td align="left"><p><span data-ttu-id="04b71-155">对计算机上的所有用户禁用 UE-V。</span><span class="sxs-lookup"><span data-stu-id="04b71-155">Disable UE-V for all the users on the computer.</span></span></p>
    <p><span data-ttu-id="04b71-156">使用– EnableSync 启用或重新启用。</span><span class="sxs-lookup"><span data-stu-id="04b71-156">Use –EnableSync to enable or re-enable.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="04b71-157">Set-UevConfiguration-CurrentComputerUser-DisableSync</span><span class="sxs-lookup"><span data-stu-id="04b71-157">Set-UevConfiguration –CurrentComputerUser -DisableSync</span></span></p></td>
    <td align="left"><p><span data-ttu-id="04b71-158">对计算机上的当前用户禁用 UE-V。</span><span class="sxs-lookup"><span data-stu-id="04b71-158">Disable UE-V for the current user on the computer.</span></span></p>
    <p><span data-ttu-id="04b71-159">使用– EnableSync 启用或重新启用。</span><span class="sxs-lookup"><span data-stu-id="04b71-159">Use –EnableSync to enable or re-enable.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="04b71-160">Clear-UevConfiguration-计算机 &lt; 设置名称&gt;</span><span class="sxs-lookup"><span data-stu-id="04b71-160">Clear-UevConfiguration –Computer -&lt;setting name&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="04b71-161">为计算机上的所有用户清除特定设置。</span><span class="sxs-lookup"><span data-stu-id="04b71-161">Clear a specific setting for all users on the computer.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="04b71-162">UevConfiguration-CurrentComputerUser- &lt; 设置名称&gt;</span><span class="sxs-lookup"><span data-stu-id="04b71-162">Clear-UevConfiguration –CurrentComputerUser -&lt;setting name&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="04b71-163">为当前用户清除特定设置。</span><span class="sxs-lookup"><span data-stu-id="04b71-163">Clear a specific setting for the current user only.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="04b71-164">Export-UevConfiguration &lt; 设置迁移文件&gt;</span><span class="sxs-lookup"><span data-stu-id="04b71-164">Export-UevConfiguration &lt;settings migration file&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="04b71-165">将 UE-V 计算机配置导出到设置迁移文件。</span><span class="sxs-lookup"><span data-stu-id="04b71-165">Export the UE-V computer configuration to a settings migration file.</span></span> <span data-ttu-id="04b71-166">文件的扩展名必须是 ". uev"。</span><span class="sxs-lookup"><span data-stu-id="04b71-166">The extension of the file must be “.uev”.</span></span></p>
    <p><span data-ttu-id="04b71-167">导出 cmdlet 导出可通过-计算机参数进行配置的所有 UE-V agent 设置。</span><span class="sxs-lookup"><span data-stu-id="04b71-167">The export cmdlet exports all UE-V agent settings that are configurable with the -computer parameter.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="04b71-168">Import-UevConfiguration &lt; 设置迁移文件&gt;</span><span class="sxs-lookup"><span data-stu-id="04b71-168">Import-UevConfiguration &lt;settings migration file&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="04b71-169">从设置迁移文件（uev 文件）导入 UE-V 计算机配置。</span><span class="sxs-lookup"><span data-stu-id="04b71-169">Import the UE-V computer configuration from a settings migration file (.uev file).</span></span></p></td>
    </tr>
    </tbody>
    </table>



**<span data-ttu-id="04b71-170">如何导出 UE-V 程序包设置并通过 PowerShell 修复 UE-V 模板</span><span class="sxs-lookup"><span data-stu-id="04b71-170">How to export UE-V package settings and repair UE-V templates with PowerShell</span></span>**

1.  <span data-ttu-id="04b71-171">以管理员身份打开 PowerShell 窗口。</span><span class="sxs-lookup"><span data-stu-id="04b71-171">Open a PowerShell window as an Administrator.</span></span> <span data-ttu-id="04b71-172">通过以下命令导入 UE-V PowerShell 模块。</span><span class="sxs-lookup"><span data-stu-id="04b71-172">Import the UE-V PowerShell module with the following command.</span></span>

    ``` syntax
    Import-module UEV
    ```

2.  <span data-ttu-id="04b71-173">使用以下 PowerShell 命令配置代理。</span><span class="sxs-lookup"><span data-stu-id="04b71-173">Use the following PowerShell commands to configure the agent.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p><strong><span data-ttu-id="04b71-174">PowerShell 命令</span><span class="sxs-lookup"><span data-stu-id="04b71-174">PowerShell command</span></span></strong></p></td>
    <td align="left"><p><strong><span data-ttu-id="04b71-175">描述</span><span class="sxs-lookup"><span data-stu-id="04b71-175">Description</span></span></strong></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="04b71-176">Export-UevPackage MicrosoftCalculator6 pkgx</span><span class="sxs-lookup"><span data-stu-id="04b71-176">Export-UevPackage MicrosoftCalculator6.pkgx</span></span></p></td>
    <td align="left"><p><span data-ttu-id="04b71-177">从 Microsoft 计算器包文件中提取设置，并将其转换为 XML 格式的可读格式。</span><span class="sxs-lookup"><span data-stu-id="04b71-177">Extracts the settings from a Microsoft Calculator package file and converts them into a human-readable format in XML.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="04b71-178">修复-UevTemplateIndex</span><span class="sxs-lookup"><span data-stu-id="04b71-178">Repair-UevTemplateIndex</span></span></p></td>
    <td align="left"><p><span data-ttu-id="04b71-179">修复 UE-V 设置位置模板的索引。</span><span class="sxs-lookup"><span data-stu-id="04b71-179">Repairs the index of the UE-V settings location templates.</span></span></p></td>
    </tr>
    </tbody>
    </table>



**<span data-ttu-id="04b71-180">如何将 UE-V Agent 配置为 WMI</span><span class="sxs-lookup"><span data-stu-id="04b71-180">How to configure the UE-V Agent with WMI</span></span>**

1.  <span data-ttu-id="04b71-181">用户体验虚拟化提供以下 WMI 命令集。</span><span class="sxs-lookup"><span data-stu-id="04b71-181">User Experience Virtualization provides the following set of WMI commands.</span></span> <span data-ttu-id="04b71-182">管理员可以使用此接口从命令行配置 UE-V agent 并自动执行典型配置任务。</span><span class="sxs-lookup"><span data-stu-id="04b71-182">Administrators can use this interface to configure the UE-V agent from the command line and automate typical configuration tasks.</span></span>

    <span data-ttu-id="04b71-183">使用具有管理员权限的帐户打开 PowerShell 窗口。</span><span class="sxs-lookup"><span data-stu-id="04b71-183">Use an account with administrator rights to open a PowerShell window.</span></span>

2.  <span data-ttu-id="04b71-184">使用以下 WMI 命令配置代理。</span><span class="sxs-lookup"><span data-stu-id="04b71-184">Use the following WMI commands to configure the agent.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="04b71-185">PowerShell 命令</span><span class="sxs-lookup"><span data-stu-id="04b71-185">PowerShell command</span></span></th>
    <th align="left"><span data-ttu-id="04b71-186">描述</span><span class="sxs-lookup"><span data-stu-id="04b71-186">Description</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="04b71-187">WmiObject-命名空间 root\Microsoft\UEV 配置</span><span class="sxs-lookup"><span data-stu-id="04b71-187">Get-WmiObject -Namespace root\Microsoft\UEV Configuration</span></span></p>
    <p></p></td>
    <td align="left"><p><span data-ttu-id="04b71-188">查看活动的 UE-V agent 设置。</span><span class="sxs-lookup"><span data-stu-id="04b71-188">View the active UE-V agent settings.</span></span> <span data-ttu-id="04b71-189">特定于用户的设置优先于计算机设置。</span><span class="sxs-lookup"><span data-stu-id="04b71-189">User-specific settings have precedence over the computer settings.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="04b71-190">WmiObject-命名空间 root\Microsoft\UEV UserConfiguration</span><span class="sxs-lookup"><span data-stu-id="04b71-190">Get-WmiObject -Namespace root\Microsoft\UEV UserConfiguration</span></span></p></td>
    <td align="left"><p><span data-ttu-id="04b71-191">查看为用户定义的 UE-V agent 配置。</span><span class="sxs-lookup"><span data-stu-id="04b71-191">View the UE-V agent configuration that is defined for user.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="04b71-192">WmiObject-命名空间 root\Microsoft\UEV ComputerConfiguration</span><span class="sxs-lookup"><span data-stu-id="04b71-192">Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</span></span></p></td>
    <td align="left"><p><span data-ttu-id="04b71-193">查看为计算机定义的 UE-V agent 配置。</span><span class="sxs-lookup"><span data-stu-id="04b71-193">View the UE-V agent configuration that is defined for computer.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="04b71-194">$config = WmiObject-命名空间 root\Microsoft\UEV ComputerConfiguration</span><span class="sxs-lookup"><span data-stu-id="04b71-194">$config = Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</span></span></p>
    <p><span data-ttu-id="04b71-195">$config。SettingsStoragePath = &lt; path_to_settings_storage_location&gt;</span><span class="sxs-lookup"><span data-stu-id="04b71-195">$config.SettingsStoragePath = &lt;path_to_settings_storage_location&gt;</span></span></p>
    <p><span data-ttu-id="04b71-196">$config。Put （）</span><span class="sxs-lookup"><span data-stu-id="04b71-196">$config.Put()</span></span></p></td>
    <td align="left"><p><span data-ttu-id="04b71-197">定义每台计算机的设置存储位置。</span><span class="sxs-lookup"><span data-stu-id="04b71-197">Define a per-computer settings storage location.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="04b71-198">$config = WmiObject-命名空间 root\Microsoft\UEV UserConfiguration</span><span class="sxs-lookup"><span data-stu-id="04b71-198">$config = Get-WmiObject -Namespace root\Microsoft\UEV UserConfiguration</span></span></p>
    <p><span data-ttu-id="04b71-199">$config。SettingsStoragePath = &lt; path_to_settings_storage_location&gt;</span><span class="sxs-lookup"><span data-stu-id="04b71-199">$config.SettingsStoragePath = &lt;path_to_settings_storage_location&gt;</span></span></p>
    <p><span data-ttu-id="04b71-200">$config。Put （）</span><span class="sxs-lookup"><span data-stu-id="04b71-200">$config.Put()</span></span></p></td>
    <td align="left"><p><span data-ttu-id="04b71-201">定义每用户设置存储位置。</span><span class="sxs-lookup"><span data-stu-id="04b71-201">Define a per-user settings storage location.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="04b71-202">$config = WmiObject-命名空间 root\Microsoft\UEV ComputerConfiguration</span><span class="sxs-lookup"><span data-stu-id="04b71-202">$config = Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</span></span></p>
    <p><span data-ttu-id="04b71-203">$config。SyncTimeoutInMilliseconds = &lt; timeout_in_milliseconds&gt;</span><span class="sxs-lookup"><span data-stu-id="04b71-203">$config.SyncTimeoutInMilliseconds = &lt;timeout_in_milliseconds&gt;</span></span></p>
    <p><span data-ttu-id="04b71-204">$config。Put （）</span><span class="sxs-lookup"><span data-stu-id="04b71-204">$config.Put()</span></span></p></td>
    <td align="left"><p><span data-ttu-id="04b71-205">设置同步超时（以毫秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="04b71-205">Set the synchronization timeout in milliseconds.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="04b71-206">$config = WmiObject-命名空间 root\Microsoft\UEV ComputerConfiguration</span><span class="sxs-lookup"><span data-stu-id="04b71-206">$config = Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</span></span></p>
    <p><span data-ttu-id="04b71-207">$config。MaxPackageSizeInBytes = &lt; size_in_bytes&gt;</span><span class="sxs-lookup"><span data-stu-id="04b71-207">$config.MaxPackageSizeInBytes = &lt;size_in_bytes&gt;</span></span></p>
    <p><span data-ttu-id="04b71-208">$config。Put （）</span><span class="sxs-lookup"><span data-stu-id="04b71-208">$config.Put()</span></span></p></td>
    <td align="left"><p><span data-ttu-id="04b71-209">配置 UE-V agent，以在设置包文件大小达到定义的阈值时进行报告。</span><span class="sxs-lookup"><span data-stu-id="04b71-209">Configure the UE-V agent to report when a settings package file size reaches a defined threshold.</span></span> <span data-ttu-id="04b71-210">设置阈值程序包文件大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="04b71-210">Set the threshold package file size in bytes.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="04b71-211">$config = WmiObject-命名空间 root\Microsoft\UEV ComputerConfiguration</span><span class="sxs-lookup"><span data-stu-id="04b71-211">$config = Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</span></span></p>
    <p><span data-ttu-id="04b71-212">$config。Powerschool = &lt; sync_method&gt;</span><span class="sxs-lookup"><span data-stu-id="04b71-212">$config.SyncMethod = &lt;sync_method&gt;</span></span></p>
    <p><span data-ttu-id="04b71-213">$config。Put （）</span><span class="sxs-lookup"><span data-stu-id="04b71-213">$config.Put()</span></span></p></td>
    <td align="left"><p><span data-ttu-id="04b71-214">设置同步方法： OfflineFiles 或 "无"。</span><span class="sxs-lookup"><span data-stu-id="04b71-214">Set the synchronization method: OfflineFiles or None.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="04b71-215">$config = WmiObject-命名空间 root\Microsoft\UEV ComputerConfiguration</span><span class="sxs-lookup"><span data-stu-id="04b71-215">$config = Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</span></span></p>
    <p><span data-ttu-id="04b71-216">$config。 &lt;设置名称 &gt;  =  &lt; 设置值&gt;</span><span class="sxs-lookup"><span data-stu-id="04b71-216">$config.&lt;setting name&gt; = &lt;setting value&gt;</span></span></p>
    <p><span data-ttu-id="04b71-217">$config。Put （）</span><span class="sxs-lookup"><span data-stu-id="04b71-217">$config.Put()</span></span></p></td>
    <td align="left"><p><span data-ttu-id="04b71-218">更新特定于每台计算机的设置。</span><span class="sxs-lookup"><span data-stu-id="04b71-218">Update a specific per-computer setting.</span></span> <span data-ttu-id="04b71-219">若要清除该设置，请使用 $null 作为设置值。</span><span class="sxs-lookup"><span data-stu-id="04b71-219">To clear the setting, use $null as the setting value.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="04b71-220">$config = WmiObject-命名空间 root\Microsoft\UEV ComputerConfiguration</span><span class="sxs-lookup"><span data-stu-id="04b71-220">$config = Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</span></span></p>
    <p><span data-ttu-id="04b71-221">$config。 &lt;设置名称 &gt;  =  &lt; 设置值&gt;</span><span class="sxs-lookup"><span data-stu-id="04b71-221">$config.&lt;setting name&gt; = &lt;setting value&gt;</span></span></p>
    <p><span data-ttu-id="04b71-222">$config。Put （）</span><span class="sxs-lookup"><span data-stu-id="04b71-222">$config.Put()</span></span></p></td>
    <td align="left"><p><span data-ttu-id="04b71-223">更新特定的每用户设置。</span><span class="sxs-lookup"><span data-stu-id="04b71-223">Update a specific per-user setting.</span></span> <span data-ttu-id="04b71-224">若要清除该设置，请使用 $null 作为设置值。</span><span class="sxs-lookup"><span data-stu-id="04b71-224">To clear the setting, use $null as the setting value.</span></span></p></td>
    </tr>
    </tbody>
    </table>



~~~
Upon configuration of the UE-V Agent with WMI and PowerShell, the defined configuration is stored in the registry in the following locations:

`\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\UEV\Agent\Configuration`

`\HKEY_CURRENT_USER\SOFTWARE\Microsoft\UEV\Agent\Configuration`
~~~

## <span data-ttu-id="04b71-225">相关主题</span><span class="sxs-lookup"><span data-stu-id="04b71-225">Related topics</span></span>


[<span data-ttu-id="04b71-226">管理 UE-V 1.0</span><span class="sxs-lookup"><span data-stu-id="04b71-226">Administering UE-V 1.0</span></span>](administering-ue-v-10.md)

[<span data-ttu-id="04b71-227">UE-V 1.0 的操作</span><span class="sxs-lookup"><span data-stu-id="04b71-227">Operations for UE-V 1.0</span></span>](operations-for-ue-v-10.md)









