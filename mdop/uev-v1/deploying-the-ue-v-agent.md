---
title: 部署 UE-V 代理
description: 部署 UE-V 代理
author: dansimp
ms.assetid: ec1c16c4-4be0-41ff-93bc-3e2b1afb5832
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 19f3b798ad7d3a43b0a274a25dd97b651435de51
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804117"
---
# <span data-ttu-id="eb684-103">部署 UE-V 代理</span><span class="sxs-lookup"><span data-stu-id="eb684-103">Deploying the UE-V Agent</span></span>


<span data-ttu-id="eb684-104">Microsoft 用户体验虚拟化（UE-V） agent 必须在使用 UE-V 的每台计算机上运行，以便漫游应用程序和 Windows 设置。</span><span class="sxs-lookup"><span data-stu-id="eb684-104">The Microsoft User Experience Virtualization (UE-V) agent must run on each computer that uses UE-V to roam application and Windows settings.</span></span> <span data-ttu-id="eb684-105">AgentSetup.exe 在32位和64位操作系统上安装 UE-V agent 的单个安装程序文件。</span><span class="sxs-lookup"><span data-stu-id="eb684-105">A single installer file, AgentSetup.exe, installs the UE-V agent on both 32-bit and 64-bit operating systems.</span></span> <span data-ttu-id="eb684-106">UE-V Agent 的命令行参数如下所示：</span><span class="sxs-lookup"><span data-stu-id="eb684-106">The command-line parameters of the UE-V Agent are the following:</span></span>

**<span data-ttu-id="eb684-107">AgentSetup.exe 命令行参数</span><span class="sxs-lookup"><span data-stu-id="eb684-107">AgentSetup.exe command-line parameters</span></span>**

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong><span data-ttu-id="eb684-108">命令行参数</span><span class="sxs-lookup"><span data-stu-id="eb684-108">Command-line parameter</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="eb684-109">定义</span><span class="sxs-lookup"><span data-stu-id="eb684-109">Definition</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="eb684-110">注释</span><span class="sxs-lookup"><span data-stu-id="eb684-110">Notes</span></span></strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="eb684-111">/help 或/h 或/？</span><span class="sxs-lookup"><span data-stu-id="eb684-111">/help or /h or /?</span></span></p></td>
<td align="left"><p><span data-ttu-id="eb684-112">显示 "AgentSetup.exe 用法" 对话框。</span><span class="sxs-lookup"><span data-stu-id="eb684-112">Displays the AgentSetup.exe usage dialog.</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="eb684-113">SettingsStoragePath</span><span class="sxs-lookup"><span data-stu-id="eb684-113">SettingsStoragePath</span></span></p></td>
<td align="left"><p><span data-ttu-id="eb684-114">指示用于定义存储设置的位置的通用命名约定（UNC）路径。</span><span class="sxs-lookup"><span data-stu-id="eb684-114">Indicates the Universal Naming Convention (UNC) path that defines where settings are stored.</span></span></p></td>
<td align="left"><p><span data-ttu-id="eb684-115">已接受% 用户名% 或% computername% 环境变量。</span><span class="sxs-lookup"><span data-stu-id="eb684-115">%username% or %computername% environment variables are accepted.</span></span> <span data-ttu-id="eb684-116">脚本可能需要转义变量。</span><span class="sxs-lookup"><span data-stu-id="eb684-116">Scripting may require escaped variables.</span></span></p>
<p><strong><span data-ttu-id="eb684-117">默认 </strong> ： &lt; 无 &gt; （Active Directory 用户 home）</span><span class="sxs-lookup"><span data-stu-id="eb684-117">Default</strong>: &lt;none&gt; (Active Directory user home)</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="eb684-118">SettingsTemplateCatalogPath</span><span class="sxs-lookup"><span data-stu-id="eb684-118">SettingsTemplateCatalogPath</span></span></p></td>
<td align="left"><p><span data-ttu-id="eb684-119">指示用于定义为新设置位置模板检查的位置的通用命名约定（UNC）路径。</span><span class="sxs-lookup"><span data-stu-id="eb684-119">Indicates the Universal Naming Convention (UNC) path that defines the location that was checked for new settings location templates.</span></span></p></td>
<td align="left"><p><span data-ttu-id="eb684-120">仅对于自定义设置位置模板是必需的</span><span class="sxs-lookup"><span data-stu-id="eb684-120">Only required for custom settings location templates</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="eb684-121">RegisterMSTemplates</span><span class="sxs-lookup"><span data-stu-id="eb684-121">RegisterMSTemplates</span></span></p></td>
<td align="left"><p><span data-ttu-id="eb684-122">指定是否应在安装期间注册默认 Microsoft 模板。</span><span class="sxs-lookup"><span data-stu-id="eb684-122">Specifies whether the default Microsoft templates should be registered during installation.</span></span></p></td>
<td align="left"><p><span data-ttu-id="eb684-123">True |;</span><span class="sxs-lookup"><span data-stu-id="eb684-123">True | False</span></span></p>
<p><strong><span data-ttu-id="eb684-124">默认值 </strong> ： True</span><span class="sxs-lookup"><span data-stu-id="eb684-124">Default</strong>: True</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="eb684-125">Powerschool</span><span class="sxs-lookup"><span data-stu-id="eb684-125">SyncMethod</span></span></p></td>
<td align="left"><p><span data-ttu-id="eb684-126">指定应使用的同步方法。</span><span class="sxs-lookup"><span data-stu-id="eb684-126">Specifies which synchronization method should be used.</span></span></p></td>
<td align="left"><p><span data-ttu-id="eb684-127">OfflineFiles |尚</span><span class="sxs-lookup"><span data-stu-id="eb684-127">OfflineFiles | None</span></span></p>
<p><strong><span data-ttu-id="eb684-128">默认 </strong> ： OfflineFiles</span><span class="sxs-lookup"><span data-stu-id="eb684-128">Default</strong>: OfflineFiles</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="eb684-129">SyncTimeoutInMilliseconds</span><span class="sxs-lookup"><span data-stu-id="eb684-129">SyncTimeoutInMilliseconds</span></span></p></td>
<td align="left"><p><span data-ttu-id="eb684-130">指定从设置存储位置检索用户设置时，计算机在超时之前等待的毫秒数。</span><span class="sxs-lookup"><span data-stu-id="eb684-130">Specifies the number of milliseconds that the computer waits before timeout when it retrieves user settings from the settings storage location.</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="eb684-131">默认 </strong> ：2000毫秒</span><span class="sxs-lookup"><span data-stu-id="eb684-131">Default</strong>: 2000 milliseconds</span></span></p>
<p><span data-ttu-id="eb684-132">（等待2秒钟）</span><span class="sxs-lookup"><span data-stu-id="eb684-132">(wait up to 2 seconds)</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="eb684-133">SyncEnabled</span><span class="sxs-lookup"><span data-stu-id="eb684-133">SyncEnabled</span></span></p></td>
<td align="left"><p><span data-ttu-id="eb684-134">指定是启用还是禁用 UE-V 同步。</span><span class="sxs-lookup"><span data-stu-id="eb684-134">Specifies whether UE-V synchronization is enabled or disabled.</span></span></p></td>
<td align="left"><p><span data-ttu-id="eb684-135">True |;</span><span class="sxs-lookup"><span data-stu-id="eb684-135">True | False</span></span></p>
<p><strong><span data-ttu-id="eb684-136">默认值 </strong> ： True</span><span class="sxs-lookup"><span data-stu-id="eb684-136">Default</strong>: True</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="eb684-137">MaxPackageSizeInBytes</span><span class="sxs-lookup"><span data-stu-id="eb684-137">MaxPackageSizeInBytes</span></span></p></td>
<td align="left"><p><span data-ttu-id="eb684-138">指定当 UE-V agent 报告文件超过阈值时的设置程序包文件大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="eb684-138">Specifies a settings package file size in bytes when the UE-V agent reports that files exceed the threshold.</span></span></p></td>
<td align="left"><p><span data-ttu-id="eb684-139">&lt;size&gt;</span><span class="sxs-lookup"><span data-stu-id="eb684-139">&lt;size&gt;</span></span></p>
<p><strong><span data-ttu-id="eb684-140">默认值 </strong> ：无（无警告阈值）</span><span class="sxs-lookup"><span data-stu-id="eb684-140">Default</strong>: none (no warning threshold)</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="eb684-141">CEIPEnabled</span><span class="sxs-lookup"><span data-stu-id="eb684-141">CEIPEnabled</span></span></p></td>
<td align="left"><p><span data-ttu-id="eb684-142">指定参与客户体验改善计划的设置。</span><span class="sxs-lookup"><span data-stu-id="eb684-142">Specifies the setting for participation in the Customer Experience Improvement program.</span></span> <span data-ttu-id="eb684-143">如果设置为 true，则将安装程序信息上载到 "Microsoft 客户体验改善计划" 网站。</span><span class="sxs-lookup"><span data-stu-id="eb684-143">If set to true, then installer information is uploaded to the Microsoft Customer Experience Improvement Program site.</span></span> <span data-ttu-id="eb684-144">如果设置为 false，则不会上载任何信息。</span><span class="sxs-lookup"><span data-stu-id="eb684-144">If set to false, then no information is uploaded.</span></span></p></td>
<td align="left"><p><span data-ttu-id="eb684-145">True |;</span><span class="sxs-lookup"><span data-stu-id="eb684-145">True | False</span></span></p>
<p><strong><span data-ttu-id="eb684-146">默认值 </strong> ： False</span><span class="sxs-lookup"><span data-stu-id="eb684-146">Default</strong>: False</span></span></p>
<p><strong><span data-ttu-id="eb684-147">在 Windows 7 上 </strong> ： True</span><span class="sxs-lookup"><span data-stu-id="eb684-147">On Windows 7</strong>: True</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="eb684-148">在安装期间，SettingsStoragePath 命令行参数指定设置值的设置存储位置。</span><span class="sxs-lookup"><span data-stu-id="eb684-148">During installation, the SettingsStoragePath command-line parameter specifies the settings storage location for the settings values.</span></span> <span data-ttu-id="eb684-149">可以在部署 UE-V Agent 之前定义设置存储位置。</span><span class="sxs-lookup"><span data-stu-id="eb684-149">A settings storage location can be defined before deploying the UE-V Agent.</span></span> <span data-ttu-id="eb684-150">如果未定义任何设置存储位置，则 UE-V 使用 Active Directory 用户主目录作为设置存储位置。</span><span class="sxs-lookup"><span data-stu-id="eb684-150">If no settings storage location is defined, then UE-V uses the Active Directory user Home Directory as the settings storage location.</span></span> <span data-ttu-id="eb684-151">在设置过程中指定 SettingsStoragePath 配置并使用% username% 作为值的一部分时，这将在用户登录的所有计算机或会话上漫游相同的用户设置体验。</span><span class="sxs-lookup"><span data-stu-id="eb684-151">When you specify the SettingsStoragePath configuration during setup and use the %username% as part of the value, this will roam the same user settings experience on all computers or sessions that a user logs into.</span></span> <span data-ttu-id="eb684-152">如果将%username%\\%computername% 变量指定为 SettingsStoragePath 值的一部分，这将保留每台计算机的设置体验。</span><span class="sxs-lookup"><span data-stu-id="eb684-152">If you specify the %username%\\%computername% variables as part of the SettingsStoragePath value, this will preserve the settings experience for each computer.</span></span>

<span data-ttu-id="eb684-153">除了组合的32位和64位安装程序之外，还为 UE-V agent 安装提供了特定于体系结构的 Windows Installer （.msi）文件。</span><span class="sxs-lookup"><span data-stu-id="eb684-153">Architecture-specific Windows Installer (.msi) files are provided for the UE-V agent installation in addition to the combined 32-bit and 64-bit installer.</span></span> <span data-ttu-id="eb684-154">AgentSetupx86.msi 或 AgentSetupx64.msi 安装文件小于 AgentSetup.exe 文件，因此可能会简化代理部署。</span><span class="sxs-lookup"><span data-stu-id="eb684-154">The AgentSetupx86.msi or AgentSetupx64.msi install files are smaller than the AgentSetup.exe file and might streamline the agent deployments.</span></span> <span data-ttu-id="eb684-155">Windows Installer （.msi）安装支持 AgentSetup.exe 安装程序的命令行参数。</span><span class="sxs-lookup"><span data-stu-id="eb684-155">The command-line parameters for the AgentSetup.exe installer are supported for the Windows Installer (.msi) installation.</span></span>

<span data-ttu-id="eb684-156">**注意** 在 UE-V agent 安装或卸载期间，你可以使用 AgentSetup.exe 文件或 AgentSetup xxx &lt; &gt; 文件，但不能同时使用这两者。</span><span class="sxs-lookup"><span data-stu-id="eb684-156">**Note** During UE-V agent installation or uninstallation you can either use the AgentSetup.exe file or the AgentSetup&lt;arch&gt;.msi file, but not both.</span></span> <span data-ttu-id="eb684-157">必须使用同一文件卸载 UE-V Agent，因为它是用于安装 UE-V Agent 的。</span><span class="sxs-lookup"><span data-stu-id="eb684-157">The same file must be used to uninstall the UE-V Agent as it was used to install the UE-V Agent.</span></span>

 

<span data-ttu-id="eb684-158">请确保在安装 UE-V agent 时使用正确的变量格式。</span><span class="sxs-lookup"><span data-stu-id="eb684-158">Be sure to use the correct variable format when you install the UE-V agent.</span></span> <span data-ttu-id="eb684-159">下表提供了使用 AgentSetup.exe 或 Windows Installer （.msi）安装文件的部署选项的示例。</span><span class="sxs-lookup"><span data-stu-id="eb684-159">The following table provides examples of deployment options for using the AgentSetup.exe or the Windows Installer (.msi) installation files.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong><span data-ttu-id="eb684-160">部署类型</span><span class="sxs-lookup"><span data-stu-id="eb684-160">Deployment type</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="eb684-161">部署说明</span><span class="sxs-lookup"><span data-stu-id="eb684-161">Deployment description</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="eb684-162">示例</span><span class="sxs-lookup"><span data-stu-id="eb684-162">Example</span></span></strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="eb684-163">命令提示符</span><span class="sxs-lookup"><span data-stu-id="eb684-163">Command prompt</span></span></p></td>
<td align="left"><p><span data-ttu-id="eb684-164">从命令提示符安装 UE-V agent 时，请使用% ^ username% 变量格式。</span><span class="sxs-lookup"><span data-stu-id="eb684-164">When you install the UE-V agent from a command prompt, use the %^username% variable format.</span></span> <span data-ttu-id="eb684-165">如果由于设置存储路径中的空格而需要引号，请使用批处理脚本文件进行部署。</span><span class="sxs-lookup"><span data-stu-id="eb684-165">If quotation marks are needed because of spaces in the settings storage path, use a batch script file for deployment.</span></span></p>
<p></p></td>
<td align="left"><p><code>AgentSetup.exe /quiet /norestart /log &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare%^username%</code></p>
<p></p>
<p><code>msiexec.exe /i &quot;&lt;path to msi file&gt;&quot; /quiet /norestart /l<em>v &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare%^username%</code></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="eb684-166">批处理脚本</span><span class="sxs-lookup"><span data-stu-id="eb684-166">Batch script</span></span></p></td>
<td align="left"><p><span data-ttu-id="eb684-167">从批处理脚本文件安装 UE-V Agent 时，请使用%% 用户名%% 变量格式。</span><span class="sxs-lookup"><span data-stu-id="eb684-167">When you install the UE-V Agent from a batch script file, use the %%username%% variable format.</span></span> <span data-ttu-id="eb684-168">如果使用此安装方法，则必须使用%% 字符转义变量。</span><span class="sxs-lookup"><span data-stu-id="eb684-168">If you use this install method, you must escape the variable with the %% characters.</span></span> <span data-ttu-id="eb684-169">如果没有此字符，脚本将在安装时（而不是在运行时）扩展用户名变量，从而导致 UE-V 对所有用户使用单个设置存储位置。</span><span class="sxs-lookup"><span data-stu-id="eb684-169">Without this character, the script expands the username variable at install time, rather than at run time, causing UE-V to use a single settings storage location for all users.</span></span></p></td>
<td align="left"><p><code>AgentSetup.exe /quiet /norestart /log &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=&quot;\server\settingsshare%%username%%&quot;</code></p>
<p></p>
<p><code>msiexec.exe /i &quot;&lt;path to msi file&gt;&quot; /quiet /norestart /l</em>v &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=&quot;\server\settingsshare%%username%%&quot;</code></p>
<p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="eb684-170">PowerShell</span><span class="sxs-lookup"><span data-stu-id="eb684-170">PowerShell</span></span></p></td>
<td align="left"><p><span data-ttu-id="eb684-171">从 PowerShell 提示或 PowerShell 脚本安装 UE-V agent 时，请使用% username% 变量格式。</span><span class="sxs-lookup"><span data-stu-id="eb684-171">When you install the UE-V agent from a PowerShell prompt or PowerShell script, use the %username% variable format.</span></span></p></td>
<td align="left"><p><code>&amp; AgentSetup.exe /quiet /norestart /log &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare%username%</code></p>
<p></p>
<p><code>&amp; msiexec.exe /i &quot;&lt;path to msi file&gt;&quot; /quiet /norestart /l<em>v &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare%username%</code></p>
<p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="eb684-172">电子软件分发，如 Configuration Manager 软件部署的部署）</span><span class="sxs-lookup"><span data-stu-id="eb684-172">Electronic software distribution, such as deployment of Configuration Manager Software Deployment)</span></span></p></td>
<td align="left"><p><span data-ttu-id="eb684-173">当使用配置管理器安装 UE-V Agent 时，请使用 ^% 用户名 ^% 变量格式。</span><span class="sxs-lookup"><span data-stu-id="eb684-173">When you install the UE-V Agent with Configuration Manager, use the ^%username^% variable format.</span></span></p></td>
<td align="left"><p><code>AgentSetup.exe /quiet /norestart /log &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare^%username^%</code></p>
<p></p>
<p><code>msiexec.exe /i &quot;&lt;path to msi file&gt;&quot; /quiet /norestart /l</em>v &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare^%username^%</code></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="eb684-174">**注意** 安装 U-EV 代理需要管理员权限，并且计算机需要重启才能运行 UE-V Agent。</span><span class="sxs-lookup"><span data-stu-id="eb684-174">**Note** The installation of the U-EV Agent requires Administrator rights and the computer will require a restart before the UE-V agent can run.</span></span>

 

## <span data-ttu-id="eb684-175">来自网络共享的 UE-V Agent 部署方法</span><span class="sxs-lookup"><span data-stu-id="eb684-175">UE-V Agent deployment methods from a network share</span></span>


<span data-ttu-id="eb684-176">你可以使用以下方法来部署 UE-V agent：</span><span class="sxs-lookup"><span data-stu-id="eb684-176">You can use the following methods to deploy the UE-V agent:</span></span>

-   <span data-ttu-id="eb684-177">可安装 Windows Installer （.msi）文件的电子软件分发（ESD）解决方案。</span><span class="sxs-lookup"><span data-stu-id="eb684-177">An electronic software distribution (ESD) solution that can install a Windows Installer (.msi) file.</span></span>

-   <span data-ttu-id="eb684-178">一个安装脚本，它引用在一个共享位置集中存储的 Windows Installer （.msi）文件。</span><span class="sxs-lookup"><span data-stu-id="eb684-178">An installation script that references the Windows Installer (.msi) file that is stored centrally on a share.</span></span>

-   <span data-ttu-id="eb684-179">在计算机上手动运行安装程序。</span><span class="sxs-lookup"><span data-stu-id="eb684-179">Manually running the installation program on the computer.</span></span>

<span data-ttu-id="eb684-180">若要从网络共享部署 UE-V agent，请使用以下步骤：</span><span class="sxs-lookup"><span data-stu-id="eb684-180">To deploy the UE-V agent from a network share, use the following steps:</span></span>

**<span data-ttu-id="eb684-181">从网络共享安装和配置 UE-V Agent</span><span class="sxs-lookup"><span data-stu-id="eb684-181">To install and configure the UE-V Agent from a network share</span></span>**

1.  <span data-ttu-id="eb684-182">在用户具有 "读取" 权限的网络共享上暂存 UE-V agent 安装文件（AgentSetup.exe）。</span><span class="sxs-lookup"><span data-stu-id="eb684-182">Stage the UE-V agent installation file (AgentSetup.exe) on a network share to which users have “read” permission.</span></span>

2.  <span data-ttu-id="eb684-183">将脚本部署到安装 UE-V agent 的用户计算机。</span><span class="sxs-lookup"><span data-stu-id="eb684-183">Deploy a script to user computers that installs the UE-V agent.</span></span> <span data-ttu-id="eb684-184">脚本应指定设置存储位置。</span><span class="sxs-lookup"><span data-stu-id="eb684-184">The script should specify the settings storage location.</span></span>

**<span data-ttu-id="eb684-185">更新 UE-V Agent</span><span class="sxs-lookup"><span data-stu-id="eb684-185">Update the UE-V Agent</span></span>**

<span data-ttu-id="eb684-186">UE-V agent 软件的更新将通过 Microsoft Update 提供。</span><span class="sxs-lookup"><span data-stu-id="eb684-186">Updates for the UE-V agent software will be provided through Microsoft Update.</span></span> <span data-ttu-id="eb684-187">在 UE-V agent 升级过程中，可能会更新常见 Microsoft 应用程序和 Windows 设置的默认设置位置模板组。</span><span class="sxs-lookup"><span data-stu-id="eb684-187">During a UE-V agent upgrade, the default group of settings location templates for common Microsoft applications and Windows settings may be updated.</span></span> <span data-ttu-id="eb684-188">可以使用企业软件分发（ESD）基础结构部署 UE-V agent 更新。</span><span class="sxs-lookup"><span data-stu-id="eb684-188">UE-V agent updates can be deployed by using Enterprise Software Distribution (ESD) infrastructure.</span></span>

## <span data-ttu-id="eb684-189">相关主题</span><span class="sxs-lookup"><span data-stu-id="eb684-189">Related topics</span></span>


[<span data-ttu-id="eb684-190">部署 UE-V 1.0</span><span class="sxs-lookup"><span data-stu-id="eb684-190">Deploying UE-V 1.0</span></span>](deploying-ue-v-10.md)

[<span data-ttu-id="eb684-191">UE-V 1.0 支持的配置</span><span class="sxs-lookup"><span data-stu-id="eb684-191">Supported Configurations for UE-V 1.0</span></span>](supported-configurations-for-ue-v-10.md)

[<span data-ttu-id="eb684-192">为 UE-V 1.0 部署设置存储位置</span><span class="sxs-lookup"><span data-stu-id="eb684-192">Deploying the Settings Storage Location for UE-V 1.0</span></span>](deploying-the-settings-storage-location-for-ue-v-10.md)

[<span data-ttu-id="eb684-193">安装 UE-V 生成器</span><span class="sxs-lookup"><span data-stu-id="eb684-193">Installing the UE-V Generator</span></span>](installing-the-ue-v-generator.md)

<span data-ttu-id="eb684-194">部署用户体验虚拟化代理</span><span class="sxs-lookup"><span data-stu-id="eb684-194">Deploy the User Experience Virtualization Agent</span></span>
 

 





