---
title: 通过 System Center Configuration Manager 2012 配置 UE-V 2
description: 通过 System Center Configuration Manager 2012 配置 UE-V 2
author: dansimp
ms.assetid: 9a4e2a74-7646-4a77-b58f-2b4456487295
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/02/2016
ms.openlocfilehash: 2ff9ccc1a17db31471549ece37461558768c3a2b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803562"
---
# <span data-ttu-id="25e8e-103">通过 System Center Configuration Manager 2012 配置 UE-V 2</span><span class="sxs-lookup"><span data-stu-id="25e8e-103">Configuring UE-V 2.x with System Center Configuration Manager 2012</span></span>


<span data-ttu-id="25e8e-104">安装 Microsoft 用户体验虚拟化（UE-V）2.0、2.1 或 2.1 SP1 及其必需功能后，必须配置 UE-V。</span><span class="sxs-lookup"><span data-stu-id="25e8e-104">After you install Microsoft User Experience Virtualization (UE-V) 2.0, 2.1, or 2.1 SP1 and their required features, UE-V must be configured.</span></span> <span data-ttu-id="25e8e-105">UE-V 配置包为管理员使用 System Center Configuration Manager 2012 SP1 或更高版本的合规性设置功能在安装了 UE-V 和配置管理器的网站之间应用一致的配置提供了一种方式。</span><span class="sxs-lookup"><span data-stu-id="25e8e-105">The UE-V Configuration Pack provides a way for administrators to use the Compliance Settings feature of System Center Configuration Manager 2012 SP1 or later to apply consistent configurations across sites where UE-V and Configuration Manager are installed.</span></span>

## <span data-ttu-id="25e8e-106">UE-V 配置包支持的功能</span><span class="sxs-lookup"><span data-stu-id="25e8e-106">UE-V Configuration Pack supported features</span></span>


<span data-ttu-id="25e8e-107">UE-V 配置包包括用于执行以下任务的工具：</span><span class="sxs-lookup"><span data-stu-id="25e8e-107">The UE-V Configuration Pack includes tools to perform the following tasks:</span></span>

-   <span data-ttu-id="25e8e-108">创建或更新 UE-V 设置位置模板分布基线。</span><span class="sxs-lookup"><span data-stu-id="25e8e-108">Create or update UE-V settings location template distribution baselines.</span></span>

    -   <span data-ttu-id="25e8e-109">定义要注册或注销的 UE-V 模板</span><span class="sxs-lookup"><span data-stu-id="25e8e-109">Define UE-V templates to be registered or unregistered</span></span>

    -   <span data-ttu-id="25e8e-110">添加或更新模板时更新 UE-V 模板配置项目和基线</span><span class="sxs-lookup"><span data-stu-id="25e8e-110">Update UE-V template configuration items and baselines as templates are added or updated</span></span>

    -   <span data-ttu-id="25e8e-111">使用标准配置项目补救措施分发和注册 UE-V 模板</span><span class="sxs-lookup"><span data-stu-id="25e8e-111">Distribute and register UE-V templates using standard Configuration Item remediation</span></span>

-   <span data-ttu-id="25e8e-112">创建或更新 UE-V Agent 策略配置项目以设置或清除这些设置。</span><span class="sxs-lookup"><span data-stu-id="25e8e-112">Create or update a UE-V Agent policy configuration item to set or clear these settings.</span></span>

    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="25e8e-113">程序包最大大小</span><span class="sxs-lookup"><span data-stu-id="25e8e-113">Max package size</span></span></p></td>
    <td align="left"><p><span data-ttu-id="25e8e-114">启用/禁用 Windows 应用同步</span><span class="sxs-lookup"><span data-stu-id="25e8e-114">Enable/disable Windows app sync</span></span></p></td>
    <td align="left"><p><span data-ttu-id="25e8e-115">在应用程序启动时等待同步</span><span class="sxs-lookup"><span data-stu-id="25e8e-115">Wait for sync on application start</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="25e8e-116">设置导入延迟</span><span class="sxs-lookup"><span data-stu-id="25e8e-116">Setting import delay</span></span></p></td>
    <td align="left"><p><span data-ttu-id="25e8e-117">同步未列出的 Windows 应用</span><span class="sxs-lookup"><span data-stu-id="25e8e-117">Sync unlisted Windows apps</span></span></p></td>
    <td align="left"><p><span data-ttu-id="25e8e-118">等待登录时同步</span><span class="sxs-lookup"><span data-stu-id="25e8e-118">Wait for sync on logon</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="25e8e-119">设置导入通知</span><span class="sxs-lookup"><span data-stu-id="25e8e-119">Settings import notification</span></span></p></td>
    <td align="left"><p><span data-ttu-id="25e8e-120">IT 联系人 URL</span><span class="sxs-lookup"><span data-stu-id="25e8e-120">IT contact URL</span></span></p></td>
    <td align="left"><p><span data-ttu-id="25e8e-121">等待同步超时</span><span class="sxs-lookup"><span data-stu-id="25e8e-121">Wait for sync timeout</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="25e8e-122">设置存储路径</span><span class="sxs-lookup"><span data-stu-id="25e8e-122">Settings storage path</span></span></p></td>
    <td align="left"><p><span data-ttu-id="25e8e-123">联系说明性文本</span><span class="sxs-lookup"><span data-stu-id="25e8e-123">IT contact descriptive text</span></span></p></td>
    <td align="left"><p><span data-ttu-id="25e8e-124">设置模板目录路径</span><span class="sxs-lookup"><span data-stu-id="25e8e-124">Settings template catalog path</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="25e8e-125">同步启用</span><span class="sxs-lookup"><span data-stu-id="25e8e-125">Sync enablement</span></span></p></td>
    <td align="left"><p><span data-ttu-id="25e8e-126">托盘图标已启用</span><span class="sxs-lookup"><span data-stu-id="25e8e-126">Tray icon enabled</span></span></p></td>
    <td align="left"><p><span data-ttu-id="25e8e-127">开始/停止 UE-V agent 服务</span><span class="sxs-lookup"><span data-stu-id="25e8e-127">Start/Stop UE-V agent service</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="25e8e-128">同步方法</span><span class="sxs-lookup"><span data-stu-id="25e8e-128">Sync method</span></span></p></td>
    <td align="left"><p><span data-ttu-id="25e8e-129">首次使用通知</span><span class="sxs-lookup"><span data-stu-id="25e8e-129">First use notification</span></span></p></td>
    <td align="left"><p><span data-ttu-id="25e8e-130">定义哪些 Windows 应用将漫游设置</span><span class="sxs-lookup"><span data-stu-id="25e8e-130">Define which Windows apps will roam settings</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="25e8e-131">同步超时</span><span class="sxs-lookup"><span data-stu-id="25e8e-131">Sync timeout</span></span></p></td>
    <td align="left"><p></p></td>
    <td align="left"><p></p></td>
    </tr>
    </tbody>
    </table>

     

-   <span data-ttu-id="25e8e-132">通过确认 UE-V 正在运行来验证合规性。</span><span class="sxs-lookup"><span data-stu-id="25e8e-132">Verify compliance by confirming that UE-V is running.</span></span>

## <span data-ttu-id="25e8e-133">生成 UE-V Agent 策略配置项目</span><span class="sxs-lookup"><span data-stu-id="25e8e-133">Generate a UE-V Agent Policy Configuration Item</span></span>


<span data-ttu-id="25e8e-134">所有 UE-V Agent 策略和配置均通过使用 UevAgentPolicyGenerator.exe 工具生成的单个配置项目进行分发。</span><span class="sxs-lookup"><span data-stu-id="25e8e-134">All UE-V Agent policy and configuration is distributed through a single configuration item that is generated using the UevAgentPolicyGenerator.exe tool.</span></span> <span data-ttu-id="25e8e-135">此工具从 XML 配置文件中读取所需的配置，并创建一个 CI，其中包含使计算机遵守合规性所需的发现和更正设置。</span><span class="sxs-lookup"><span data-stu-id="25e8e-135">This tool reads the desired configuration from an XML configuration file and creates a CI containing the discovery and remediation settings needed to bring the machine into compliance.</span></span>

<span data-ttu-id="25e8e-136">UE-V Agent 策略配置项目 CAB 文件是使用 UevTemplateBaselineGenerator.exe 命令行工具创建的，该工具具有以下参数：</span><span class="sxs-lookup"><span data-stu-id="25e8e-136">The UE-V Agent policy configuration item CAB file is created using the UevTemplateBaselineGenerator.exe command line tool, which has these parameters:</span></span>

-   <span data-ttu-id="25e8e-137">网站 &lt; 网站代码&gt;</span><span class="sxs-lookup"><span data-stu-id="25e8e-137">Site &lt;site code&gt;</span></span>

-   <span data-ttu-id="25e8e-138">PolicyName &lt; 名称 &gt; 可选：默认为 "Ue-v Agent Policy" （如果不存在）</span><span class="sxs-lookup"><span data-stu-id="25e8e-138">PolicyName &lt;name&gt; Optional: Defaults to “UE-V Agent Policy” if not present</span></span>

-   <span data-ttu-id="25e8e-139">PolicyDescription &lt; 说明 &gt; 可选：如果不存在，则提供说明</span><span class="sxs-lookup"><span data-stu-id="25e8e-139">PolicyDescription &lt;description&gt; Optional: A description is provided if not present</span></span>

-   <span data-ttu-id="25e8e-140">CabFilePath &lt; 配置项目的完整路径。CAB 文件&gt;</span><span class="sxs-lookup"><span data-stu-id="25e8e-140">CabFilePath &lt;full path to configuration item .CAB file&gt;</span></span>

-   <span data-ttu-id="25e8e-141">ConfigurationFile &lt; 代理配置 XML 文件的完整路径&gt;</span><span class="sxs-lookup"><span data-stu-id="25e8e-141">ConfigurationFile &lt;full path to agent configuration XML file&gt;</span></span>

<span data-ttu-id="25e8e-142">**注意** 可能需要更改 PowerShell 执行策略以允许这些脚本在你的环境中运行。</span><span class="sxs-lookup"><span data-stu-id="25e8e-142">**Note** It might be necessary to change the PowerShell execution policy to allow these scripts to run in your environment.</span></span> <span data-ttu-id="25e8e-143">在 Configuration Manager 控制台中执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="25e8e-143">Perform these steps in the Configuration Manager console:</span></span>

1.  <span data-ttu-id="25e8e-144">选择**管理 &gt; 客户端设置 &gt; 属性**</span><span class="sxs-lookup"><span data-stu-id="25e8e-144">Select **Administration &gt; Client Settings &gt; Properties**</span></span>

2.  <span data-ttu-id="25e8e-145">在 "**用户代理**" 选项卡中，将 " **PowerShell 执行策略**" 设置为 "**绕过**"</span><span class="sxs-lookup"><span data-stu-id="25e8e-145">In the **User Agent** tab, set the **PowerShell Execution Policy** to **Bypass**</span></span>

<a href="" id="create"></a>**<span data-ttu-id="25e8e-146">创建第一个 UE-V 策略配置项目</span><span class="sxs-lookup"><span data-stu-id="25e8e-146">Create the First UE-V Policy Configuration Item</span></span>**

1.  <span data-ttu-id="25e8e-147">将默认设置配置文件从 UE-V Config Pack 安装目录复制到 ConfigMgr 管理员控制台可见的位置：</span><span class="sxs-lookup"><span data-stu-id="25e8e-147">Copy the default settings configuration file from the UE-V Config Pack installation directory to a location visible to your ConfigMgr Admin Console:</span></span>

    ``` syntax
    C:\Program Files (x86)\Microsoft User Experience Virtualization\ConfigPack\AgentConfiguration.xml c:\<target path>
    ```

    <span data-ttu-id="25e8e-148">默认配置文件包含五个部分：</span><span class="sxs-lookup"><span data-stu-id="25e8e-148">The default configuration file contains five sections:</span></span>

    <a href="" id="computer-policy"></a>**<span data-ttu-id="25e8e-149">计算机策略</span><span class="sxs-lookup"><span data-stu-id="25e8e-149">Computer Policy</span></span>**  
    <span data-ttu-id="25e8e-150">所有 UE-V 计算机级设置。</span><span class="sxs-lookup"><span data-stu-id="25e8e-150">All UE-V machine level settings.</span></span> <span data-ttu-id="25e8e-151">DesiredState 属性可以</span><span class="sxs-lookup"><span data-stu-id="25e8e-151">The DesiredState attribute can be</span></span>

    -   <span data-ttu-id="25e8e-152">**设置**为在注册表中分配值</span><span class="sxs-lookup"><span data-stu-id="25e8e-152">**Set** to have the value assigned in the registry</span></span>

    -   <span data-ttu-id="25e8e-153">**清除**以删除设置</span><span class="sxs-lookup"><span data-stu-id="25e8e-153">**Clear** to remove the setting</span></span>

    -   <span data-ttu-id="25e8e-154">**非托管**以使配置项目处于其当前状态</span><span class="sxs-lookup"><span data-stu-id="25e8e-154">**Unmanaged** to have the configuration item left at its current state</span></span>

    <span data-ttu-id="25e8e-155">请勿删除本部分中的行。</span><span class="sxs-lookup"><span data-stu-id="25e8e-155">Do not remove lines from this section.</span></span> <span data-ttu-id="25e8e-156">如果不希望 Configuration Manager 更改当前值或默认值，请改为将 DesiredState 设置为 "非托管"。</span><span class="sxs-lookup"><span data-stu-id="25e8e-156">Instead, set the DesiredState to ‘Unmanaged’ if you do not want Configuration Manager to alter current or default values.</span></span>

    <a href="" id="currentcomputeruserpolicy"></a>**<span data-ttu-id="25e8e-157">CurrentComputerUserPolicy</span><span class="sxs-lookup"><span data-stu-id="25e8e-157">CurrentComputerUserPolicy</span></span>**  
    <span data-ttu-id="25e8e-158">所有 UE-V 用户级别设置。</span><span class="sxs-lookup"><span data-stu-id="25e8e-158">All UE-V user level settings.</span></span> <span data-ttu-id="25e8e-159">这些条目会替代用户的计算机设置。</span><span class="sxs-lookup"><span data-stu-id="25e8e-159">These entries override the machine settings for a user.</span></span> <span data-ttu-id="25e8e-160">DesiredState 属性可以</span><span class="sxs-lookup"><span data-stu-id="25e8e-160">The DesiredState attribute can be</span></span>

    -   <span data-ttu-id="25e8e-161">**设置**为在注册表中分配值</span><span class="sxs-lookup"><span data-stu-id="25e8e-161">**Set** to have the value assigned in the registry</span></span>

    -   <span data-ttu-id="25e8e-162">**清除**以删除设置</span><span class="sxs-lookup"><span data-stu-id="25e8e-162">**Clear** to remove the setting</span></span>

    -   <span data-ttu-id="25e8e-163">**非托管**以使配置项目处于其当前状态</span><span class="sxs-lookup"><span data-stu-id="25e8e-163">**Unmanaged** to have the configuration item left at its current state</span></span>

    <span data-ttu-id="25e8e-164">请勿删除本部分中的行。</span><span class="sxs-lookup"><span data-stu-id="25e8e-164">Do not remove lines from this section.</span></span> <span data-ttu-id="25e8e-165">如果不希望 Configuration Manager 更改当前值或默认值，请改为将 DesiredState 设置为 "非托管"。</span><span class="sxs-lookup"><span data-stu-id="25e8e-165">Instead, set the DesiredState to ‘Unmanaged’ if you do not want Configuration Manager to alter current or default values.</span></span>

    <a href="" id="services"></a>**<span data-ttu-id="25e8e-166">服务</span><span class="sxs-lookup"><span data-stu-id="25e8e-166">Services</span></span>**  
    <span data-ttu-id="25e8e-167">此部分控件服务操作中的条目。</span><span class="sxs-lookup"><span data-stu-id="25e8e-167">Entries in this section control service operation.</span></span> <span data-ttu-id="25e8e-168">默认配置文件包含 UevAgentService 的单个条目。</span><span class="sxs-lookup"><span data-stu-id="25e8e-168">The default configuration file contains a single entry for the UevAgentService.</span></span> <span data-ttu-id="25e8e-169">DesiredState 属性可以设置为 "**正在运行**" 或 "**已停止**"。</span><span class="sxs-lookup"><span data-stu-id="25e8e-169">The DesiredState attribute can be set to **Running** or **Stopped**.</span></span>

    <a href="" id="windows8appscomputerpolicy"></a>**<span data-ttu-id="25e8e-170">Windows8AppsComputerPolicy</span><span class="sxs-lookup"><span data-stu-id="25e8e-170">Windows8AppsComputerPolicy</span></span>**  
    <span data-ttu-id="25e8e-171">所有计算机级 Windows 应用同步设置。</span><span class="sxs-lookup"><span data-stu-id="25e8e-171">All machine level Windows app synchronization settings.</span></span> <span data-ttu-id="25e8e-172">可以为本部分中列出的每个 PackageFamilyName 分配一个 DesiredState</span><span class="sxs-lookup"><span data-stu-id="25e8e-172">Each PackageFamilyName listed in this section can be assigned a DesiredState of</span></span>

    -   <span data-ttu-id="25e8e-173">**已启用**以设置漫游</span><span class="sxs-lookup"><span data-stu-id="25e8e-173">**Enabled** to have settings roam</span></span>

    -   <span data-ttu-id="25e8e-174">**禁用**以防止漫游设置</span><span class="sxs-lookup"><span data-stu-id="25e8e-174">**Disabled** to prevent settings from roaming</span></span>

    -   <span data-ttu-id="25e8e-175">已**清除**以从 ue-v control 中删除条目</span><span class="sxs-lookup"><span data-stu-id="25e8e-175">**Cleared** to have the entry removed from UE-V control</span></span>

    <span data-ttu-id="25e8e-176">可使用 PowerShell cmdlet GetAppxPackage 查看已安装的 Windows 应用列表，从而将其他行添加到此部分。</span><span class="sxs-lookup"><span data-stu-id="25e8e-176">Additional lines can be added to this section based on the list of installed Windows apps that can be viewed using the PowerShell cmdlet GetAppxPackage.</span></span>

    <a href="" id="windows8appscurrentcomputeruserpolicy"></a>**<span data-ttu-id="25e8e-177">Windows8AppsCurrentComputerUserPolicy</span><span class="sxs-lookup"><span data-stu-id="25e8e-177">Windows8AppsCurrentComputerUserPolicy</span></span>**  
    <span data-ttu-id="25e8e-178">与 Windows8AppsComputerPolicy 的设置相同，该设置会替代单个用户的计算机设置。</span><span class="sxs-lookup"><span data-stu-id="25e8e-178">Identical to the Windows8AppsComputerPolicy with settings that override machine settings for an individual user.</span></span>

2.  <span data-ttu-id="25e8e-179">通过更改所需的 "状态" 和 "值" 字段来编辑配置文件。</span><span class="sxs-lookup"><span data-stu-id="25e8e-179">Edit the configuration file by changing the desired state and value fields.</span></span>

3.  <span data-ttu-id="25e8e-180">在运行 ConfigMgr 管理员控制台的计算机上运行此命令：</span><span class="sxs-lookup"><span data-stu-id="25e8e-180">Run this command on a machine running the ConfigMgr Admin Console:</span></span>

    ``` syntax
    C:\Program Files (x86)\Microsoft User Experience Virtualization\ConfigPack\UevAgentPolicyGenerator.exe –Site ABC –CabFilePath "C:\MyCabFiles\UevPolicyItem.cab" –ConfigurationFile "c:\AgentConfiguration.xml"
    ```

4.  <span data-ttu-id="25e8e-181">使用 ConfigMgr 控制台或 PowerShell Import 导入 CAB 文件 CMConfigurationItem</span><span class="sxs-lookup"><span data-stu-id="25e8e-181">Import the CAB file using ConfigMgr console or PowerShell Import-CMConfigurationItem</span></span>

**<span data-ttu-id="25e8e-182">更新 UE-V 策略配置项目</span><span class="sxs-lookup"><span data-stu-id="25e8e-182">Update a UE-V Policy Configuration Item</span></span>**

1.  <span data-ttu-id="25e8e-183">通过更改所需的 "状态" 和 "值" 字段来编辑配置文件。</span><span class="sxs-lookup"><span data-stu-id="25e8e-183">Edit the configuration file by changing the desired state and value fields.</span></span>

2.  <span data-ttu-id="25e8e-184">在[创建第一个 Ue-v 策略配置项](#create)中的步骤3中运行命令。</span><span class="sxs-lookup"><span data-stu-id="25e8e-184">Run the command from Step 3 in [Create the First UE-V Policy Configuration Item](#create).</span></span> <span data-ttu-id="25e8e-185">如果您已通过 PolicyName 参数更改了名称，请确保输入相同的名称。</span><span class="sxs-lookup"><span data-stu-id="25e8e-185">If you changed the name with the PolicyName parameter, make sure you enter the same name.</span></span>

3.  <span data-ttu-id="25e8e-186">重新导入 CAB 文件。</span><span class="sxs-lookup"><span data-stu-id="25e8e-186">Reimport the CAB file.</span></span> <span data-ttu-id="25e8e-187">将更新 ConfigMgr 中的版本。</span><span class="sxs-lookup"><span data-stu-id="25e8e-187">The version in ConfigMgr will be updated.</span></span>

## <span data-ttu-id="25e8e-188">生成 UE-V 模板基线</span><span class="sxs-lookup"><span data-stu-id="25e8e-188">Generate a UE-V Template Baseline</span></span>
<span data-ttu-id="25e8e-189">UE-V 模板是使用包含多个配置项目的基线分发的。</span><span class="sxs-lookup"><span data-stu-id="25e8e-189">UE-V templates are distributed using a baseline containing multiple configuration items.</span></span> <span data-ttu-id="25e8e-190">每个配置项目都包含安装一个 UE-V 模板所需的发现和修正脚本。</span><span class="sxs-lookup"><span data-stu-id="25e8e-190">Each configuration item contains the discovery and remediation scripts needed to install one UE-V template.</span></span> <span data-ttu-id="25e8e-191">实际 UE-V 模板嵌入在用于使用标准配置项目功能分发的更新脚本中。</span><span class="sxs-lookup"><span data-stu-id="25e8e-191">The actual UE-V template is embedded within the remediation script for distribution using standard Configuration Item functionality.</span></span>

<span data-ttu-id="25e8e-192">UE-V 模板基线是使用 UevTemplateBaselineGenerator.exe 命令行工具创建的，该工具具有以下参数：</span><span class="sxs-lookup"><span data-stu-id="25e8e-192">The UE-V template baseline is created using the UevTemplateBaselineGenerator.exe command line tool, which has these parameters:</span></span>

-   <span data-ttu-id="25e8e-193">网站 &lt; 网站代码&gt;</span><span class="sxs-lookup"><span data-stu-id="25e8e-193">Site &lt;site code&gt;</span></span>

-   <span data-ttu-id="25e8e-194">BaselineName &lt; 名称 &gt; （可选：默认为 "Ue-v 模板分布基线" （如果不存在）</span><span class="sxs-lookup"><span data-stu-id="25e8e-194">BaselineName &lt;name&gt; (Optional: defaults to “UE-V Template Distribution Baseline” if not present)</span></span>

-   <span data-ttu-id="25e8e-195">BaselineDescription &lt; 说明 &gt; （可选：如果不存在，则提供说明）</span><span class="sxs-lookup"><span data-stu-id="25e8e-195">BaselineDescription &lt;description&gt; (Optional: a description is provided if not present)</span></span>

-   <span data-ttu-id="25e8e-196">TemplateFolder &lt; ue-v 模板文件夹&gt;</span><span class="sxs-lookup"><span data-stu-id="25e8e-196">TemplateFolder &lt;UE-V template folder&gt;</span></span>

-   <span data-ttu-id="25e8e-197">注册 &lt; 逗号分隔的模板文件列表&gt;</span><span class="sxs-lookup"><span data-stu-id="25e8e-197">Register &lt;comma separated template file list&gt;</span></span>

-   <span data-ttu-id="25e8e-198">注销 &lt; 以逗号分隔的模板列表&gt;</span><span class="sxs-lookup"><span data-stu-id="25e8e-198">Unregister &lt;comma separated template list&gt;</span></span>

-   <span data-ttu-id="25e8e-199">CabFilePath 要 &lt; 生成的基线 CAB 文件的完整路径&gt;</span><span class="sxs-lookup"><span data-stu-id="25e8e-199">CabFilePath &lt;Full path to baseline CAB file to generate&gt;</span></span>

<span data-ttu-id="25e8e-200">结果是一个可以导入到 Configuration Manager 的基线 CAB 文件。</span><span class="sxs-lookup"><span data-stu-id="25e8e-200">The result is a baseline CAB file that is ready for import into Configuration Manager.</span></span> <span data-ttu-id="25e8e-201">如果在将来日期更新或添加模板，则可以使用相同的基线名称重新运行命令。</span><span class="sxs-lookup"><span data-stu-id="25e8e-201">If at a future date, you update or add a template, you can rerun the command using the same baseline name.</span></span> <span data-ttu-id="25e8e-202">在更改后的模板上导入的 CAB 会导致 CI 版本更新。</span><span class="sxs-lookup"><span data-stu-id="25e8e-202">Importing the CAB results in CI version updates on the changed templates.</span></span>

### <a href="" id="create2"></a><span data-ttu-id="25e8e-203">创建第一个 UE-V 模板基线</span><span class="sxs-lookup"><span data-stu-id="25e8e-203">Create the First UE-V Template Baseline</span></span>

1.  <span data-ttu-id="25e8e-204">在运行 ConfigMgr 管理员控制台的计算机可见的稳定文件夹位置中创建一个 "母版" 一组 UE-V 模板。</span><span class="sxs-lookup"><span data-stu-id="25e8e-204">Create a “master” set of UE-V templates in a stable folder location visible to the machine running your ConfigMgr Admin Console.</span></span> <span data-ttu-id="25e8e-205">添加或更新模板后，此文件夹将被拉入以进行分发。</span><span class="sxs-lookup"><span data-stu-id="25e8e-205">As templates are added or updated, this folder is where they are pulled for distribution.</span></span> <span data-ttu-id="25e8e-206">可以从安装了 UE-V 的计算机复制模板的初始列表。</span><span class="sxs-lookup"><span data-stu-id="25e8e-206">The initial list of templates can be copied from a machine with UE-V installed.</span></span> <span data-ttu-id="25e8e-207">默认模板位置是 C:\\program files Files\\Microsoft 用户体验 Virtualization\\Templates。</span><span class="sxs-lookup"><span data-stu-id="25e8e-207">The default template location is C:\\Program Files\\Microsoft User Experience Virtualization\\Templates.</span></span>

2.  <span data-ttu-id="25e8e-208">创建可在其中添加模板生成器命令的 text.bat 文件。</span><span class="sxs-lookup"><span data-stu-id="25e8e-208">Create a text.bat file where you can add the template generator command.</span></span> <span data-ttu-id="25e8e-209">这是可选的，但如果保存命令参数，则会使再生更简单。</span><span class="sxs-lookup"><span data-stu-id="25e8e-209">This is optional, but will make regeneration simpler if you save the command parameters.</span></span>

3.  <span data-ttu-id="25e8e-210">将命令和参数添加到将生成基线的 .bat 文件。</span><span class="sxs-lookup"><span data-stu-id="25e8e-210">Add the command and parameters to the .bat file that will generate the baseline.</span></span> <span data-ttu-id="25e8e-211">下面的示例创建了一个分发记事本和计算器的比较基准：</span><span class="sxs-lookup"><span data-stu-id="25e8e-211">The following example creates a baseline that distributes Notepad and Calculator:</span></span>

    ``` syntax
    C:\Program Files (x86)\Microsoft User Experience Virtualization\ConfigPack\UevTemplateBaselineGenerator.exe –Site "ABC" –TemplateFolder "C:\ProductionUevTemplates" –Register "MicrosoftNotepad.xml, MicrosoftCalculator.xml" –CabFilePath "C:\MyCabFiles\UevTemplateBaseline.cab"
    ```

4.  <span data-ttu-id="25e8e-212">运行 .bat 文件，创建 UevTemplateBaseline.cab 准备导入到配置管理器。</span><span class="sxs-lookup"><span data-stu-id="25e8e-212">Run the .bat file to create UevTemplateBaseline.cab ready for import into Configuration Manager.</span></span>

### <span data-ttu-id="25e8e-213">更新 UE-V 模板基线</span><span class="sxs-lookup"><span data-stu-id="25e8e-213">Update a UE-V Template Baseline</span></span>

<span data-ttu-id="25e8e-214">模板生成器使用模板版本来确定是否应更新模板。</span><span class="sxs-lookup"><span data-stu-id="25e8e-214">The template generator uses the template version to determine if a template should be updated.</span></span> <span data-ttu-id="25e8e-215">如果你进行模板更改并更新版本，则基线生成器会将你的主文件夹中的模板与 ConfigMgr 服务器上 CI 中包含的模板进行比较。</span><span class="sxs-lookup"><span data-stu-id="25e8e-215">If you make a template change and update the version, the baseline generator compares the template in your master folder with the template contained in the CI on the ConfigMgr server.</span></span> <span data-ttu-id="25e8e-216">如果发现差异，则会更新生成的基线和修改后的 CI 版本。</span><span class="sxs-lookup"><span data-stu-id="25e8e-216">If a difference is found, the generated baseline and modified CI versions are updated.</span></span>

<span data-ttu-id="25e8e-217">要分发新的记事本模板，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="25e8e-217">To distribute a new Notepad template, you would perform these steps:</span></span>

1.  <span data-ttu-id="25e8e-218">更新位于模板的版本元素中的模板和模板版本 &lt; &gt; 。</span><span class="sxs-lookup"><span data-stu-id="25e8e-218">Update the template and template version located in the &lt;Version&gt; element of the template.</span></span>

2.  <span data-ttu-id="25e8e-219">将模板复制到您的主模板目录。</span><span class="sxs-lookup"><span data-stu-id="25e8e-219">Copy the template to your master template directory.</span></span>

3.  <span data-ttu-id="25e8e-220">在[创建第一个 Ue-v 模板基线](#create2)的步骤3中创建的 .bat 文件中运行该命令。</span><span class="sxs-lookup"><span data-stu-id="25e8e-220">Run the command in the .bat file that you created in Step 3 in [Create the First UE-V Template Baseline](#create2).</span></span>

4.  <span data-ttu-id="25e8e-221">使用 console 或 PowerShell Import-CMBaseline 将生成的 CAB 文件导入 ConfigMgr。</span><span class="sxs-lookup"><span data-stu-id="25e8e-221">Import the generated CAB file into ConfigMgr using the console or PowerShell Import-CMBaseline.</span></span>

## <span data-ttu-id="25e8e-222">获取 UE-V 配置包</span><span class="sxs-lookup"><span data-stu-id="25e8e-222">Get the UE-V Configuration Pack</span></span>


<span data-ttu-id="25e8e-223">可在[此处](https://go.microsoft.com/fwlink/?LinkId=317263)下载 Configuration MANAGER 2012 SP1 或更高版本的 Ue-v 配置包。</span><span class="sxs-lookup"><span data-stu-id="25e8e-223">The UE-V Configuration Pack for Configuration Manager 2012 SP1 or later can be downloaded [here](https://go.microsoft.com/fwlink/?LinkId=317263).</span></span>






## <span data-ttu-id="25e8e-224">相关主题</span><span class="sxs-lookup"><span data-stu-id="25e8e-224">Related topics</span></span>


[<span data-ttu-id="25e8e-225">管理 UE-V 2.x 的配置</span><span class="sxs-lookup"><span data-stu-id="25e8e-225">Manage Configurations for UE-V 2.x</span></span>](manage-configurations-for-ue-v-2x-new-uevv2.md)

 

 





