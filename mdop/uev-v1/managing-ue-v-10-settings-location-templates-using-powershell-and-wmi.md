---
title: 使用 PowerShell 和 WMI 管理 UE-V 1.0 设置位置模板
description: 使用 PowerShell 和 WMI 管理 UE-V 1.0 设置位置模板
author: dansimp
ms.assetid: 4b911c78-a5e9-4199-bfeb-72ab764d47c1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d8dab0997cdfaf7c96862fcce4bc012c3edfe0c0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798059"
---
# <span data-ttu-id="e813a-103">使用 PowerShell 和 WMI 管理 UE-V 1.0 设置位置模板</span><span class="sxs-lookup"><span data-stu-id="e813a-103">Managing UE-V 1.0 Settings Location Templates Using PowerShell and WMI</span></span>


<span data-ttu-id="e813a-104">Microsoft 用户体验虚拟化（UE-V）使用设置位置模板（XML 文件），这些模板定义用户体验虚拟化捕获和应用的设置。</span><span class="sxs-lookup"><span data-stu-id="e813a-104">Microsoft User Experience Virtualization (UE-V) uses settings location templates (XML files) that define the settings captured and applied by User Experience Virtualization.</span></span> <span data-ttu-id="e813a-105">UE-V 包含一组标准设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="e813a-105">UE-V includes a set of standard settings location templates.</span></span> <span data-ttu-id="e813a-106">它还包括支持创建自定义设置位置模板的 UE-V 生成器工具。</span><span class="sxs-lookup"><span data-stu-id="e813a-106">It also includes the UE-V Generator tool that enables you to create custom settings location templates.</span></span> <span data-ttu-id="e813a-107">创建和部署设置位置模板后，您可以使用 PowerShell 或 WMI 管理这些模板。</span><span class="sxs-lookup"><span data-stu-id="e813a-107">After you create and deploy settings location templates you can manage those templates using PowerShell or WMI.</span></span>

## <span data-ttu-id="e813a-108">通过 WMI 和 PowerShell 管理设置位置模板</span><span class="sxs-lookup"><span data-stu-id="e813a-108">Manage settings location templates with WMI and PowerShell</span></span>


<span data-ttu-id="e813a-109">UE-V 的 WMI 和 PowerShell 功能包括启用、禁用、注册、更新和注销设置位置模板的功能。</span><span class="sxs-lookup"><span data-stu-id="e813a-109">The WMI and PowerShell features of UE-V include the ability to enable, disable, register, update, and unregister settings location templates.</span></span> <span data-ttu-id="e813a-110">通过使用这些功能，你可以使用 UE-V agent 自动执行注册、更新或注销模板的过程。</span><span class="sxs-lookup"><span data-stu-id="e813a-110">By using these features, you can automate the process of registering, updating, or unregistering templates with the UE-V agent.</span></span> <span data-ttu-id="e813a-111">你还可以使用 WMI 和 PowerShell 命令手动注册模板。</span><span class="sxs-lookup"><span data-stu-id="e813a-111">You can also manually register templates using WMI and PowerShell commands.</span></span> <span data-ttu-id="e813a-112">通过将这些功能与电子软件分发解决方案、组策略或其他自动部署方法（如脚本）结合使用，你可以进一步自动化该过程。</span><span class="sxs-lookup"><span data-stu-id="e813a-112">By using these features in conjunction with an electronic software distribution solution, Group Policy, or another automated deployment method such as a script, you can further automate that process.</span></span>

<span data-ttu-id="e813a-113">必须具有管理员权限才能更新、注册或注销设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="e813a-113">You must have administrator permissions to update, register, or unregister a settings location template.</span></span> <span data-ttu-id="e813a-114">启用或禁用模板不需要管理员权限。</span><span class="sxs-lookup"><span data-stu-id="e813a-114">Administrator permissions are not required to enable or disable templates.</span></span>

**<span data-ttu-id="e813a-115">通过 PowerShell 管理设置位置模板</span><span class="sxs-lookup"><span data-stu-id="e813a-115">To manage settings location templates with PowerShell</span></span>**

1.  <span data-ttu-id="e813a-116">使用具有管理员权限的帐户打开 Windows PowerShell 窗口。</span><span class="sxs-lookup"><span data-stu-id="e813a-116">Use an account with administrator rights to open a Windows PowerShell window.</span></span> <span data-ttu-id="e813a-117">若要导入**MICROSOFT Ue-v PowerShell**模块，请在 PowerShell 命令提示符处键入以下命令。</span><span class="sxs-lookup"><span data-stu-id="e813a-117">To import the **Microsoft UE-V PowerShell** module, type the following command at the PowerShell command prompt.</span></span>

    ``` syntax
    Import-module UEV
    ```

2.  <span data-ttu-id="e813a-118">使用以下 PowerShell cmdlet 注册和管理 UE-V 设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="e813a-118">Use the following PowerShell cmdlets to register and manage the UE-V settings location templates.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><strong><span data-ttu-id="e813a-119">PowerShell 命令</span><span class="sxs-lookup"><span data-stu-id="e813a-119">PowerShell command</span></span></strong></th>
    <th align="left"><strong><span data-ttu-id="e813a-120">描述</span><span class="sxs-lookup"><span data-stu-id="e813a-120">Description</span></span></strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="e813a-121">UevTemplate</span><span class="sxs-lookup"><span data-stu-id="e813a-121">Get-UevTemplate</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e813a-122">列出计算机上注册的所有设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="e813a-122">Lists all the settings location templates registered on the computer.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="e813a-123">注册-UevTemplate</span><span class="sxs-lookup"><span data-stu-id="e813a-123">Register-UevTemplate</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e813a-124">使用 UE-V 注册设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="e813a-124">Registers a settings location template with UE-V.</span></span> <span data-ttu-id="e813a-125">注册模板后，UE-V 将在已注册模板的计算机之间同步模板中定义的设置。</span><span class="sxs-lookup"><span data-stu-id="e813a-125">Once a template is registered, UE-V will synchronize the settings that are defined in the template between computers that have the template registered.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="e813a-126">注销-UevTemplate</span><span class="sxs-lookup"><span data-stu-id="e813a-126">Unregister-UevTemplate</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e813a-127">使用 UE-V 注销设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="e813a-127">Unregisters a settings location template with UE-V.</span></span> <span data-ttu-id="e813a-128">模板注销后，UE-V 将不再同步在计算机之间的模板中定义的设置。</span><span class="sxs-lookup"><span data-stu-id="e813a-128">As soon as a template is unregistered, UE-V will no longer synchronize the settings that are defined in the template between computers.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="e813a-129">Update-UevTemplate</span><span class="sxs-lookup"><span data-stu-id="e813a-129">Update-UevTemplate</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e813a-130">使用最新版本的模板更新设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="e813a-130">Updates a settings location template with a more recent version of the template.</span></span> <span data-ttu-id="e813a-131">新模板的版本应晚于现有模板的版本。</span><span class="sxs-lookup"><span data-stu-id="e813a-131">The new template should have a version that is later than the existing one.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="e813a-132">Disable-UevTemplate</span><span class="sxs-lookup"><span data-stu-id="e813a-132">Disable-UevTemplate</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e813a-133">对计算机的当前用户禁用设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="e813a-133">Disables a settings location template for the current user of the computer.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="e813a-134">Enable-UevTemplate</span><span class="sxs-lookup"><span data-stu-id="e813a-134">Enable-UevTemplate</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e813a-135">为计算机的当前用户启用设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="e813a-135">Enables a settings location template for the current user of the computer.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="e813a-136">Test-UevTemplate</span><span class="sxs-lookup"><span data-stu-id="e813a-136">Test-UevTemplate</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e813a-137">确定给定设置位置模板是否符合其 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="e813a-137">Determines whether a given settings location template complies with its XML schema.</span></span></p></td>
    </tr>
    </tbody>
    </table>

     

<span data-ttu-id="e813a-138">UE-V PowerShell 功能允许你管理在你的企业中部署的一组设置模板。</span><span class="sxs-lookup"><span data-stu-id="e813a-138">The UE-V PowerShell features allow you to manage a group of settings templates deployed in your enterprise.</span></span> <span data-ttu-id="e813a-139">若要使用 PowerShell 管理一组模板，请执行下列操作。</span><span class="sxs-lookup"><span data-stu-id="e813a-139">To manage a group of templates using PowerShell, do the following.</span></span>

**<span data-ttu-id="e813a-140">使用 PowerShell 管理一组设置位置模板</span><span class="sxs-lookup"><span data-stu-id="e813a-140">To manage a group of settings location templates with PowerShell</span></span>**

1.  <span data-ttu-id="e813a-141">修改或更新所需的设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="e813a-141">Modify or update the desired settings location templates.</span></span>

2.  <span data-ttu-id="e813a-142">将所需的设置位置模板部署到本地计算机可访问的文件夹。</span><span class="sxs-lookup"><span data-stu-id="e813a-142">Deploy the desired settings location templates to a folder accessible to the local computer.</span></span>

3.  <span data-ttu-id="e813a-143">在本地计算机上，打开具有管理员权限的 Windows PowerShell 窗口。</span><span class="sxs-lookup"><span data-stu-id="e813a-143">On the local computer, open a Windows PowerShell window with administrator rights.</span></span>

4.  <span data-ttu-id="e813a-144">通过键入以下命令导入 Microsoft UE-V PowerShell 模块。</span><span class="sxs-lookup"><span data-stu-id="e813a-144">Import the Microsoft UE-V PowerShell module, by typing the following command.</span></span>

    ``` syntax
    Import-module UEV
    ```

5.  <span data-ttu-id="e813a-145">通过键入以下命令注销以前注册的所有版本的模板。</span><span class="sxs-lookup"><span data-stu-id="e813a-145">Unregister all the previously registered versions of the templates by typing the following command.</span></span>

    ``` syntax
    Get-UevTemplate | Unregister-UevTemplate
    ```

    <span data-ttu-id="e813a-146">这将注销计算机上的所有活动模板。</span><span class="sxs-lookup"><span data-stu-id="e813a-146">This will unregister all active templates on the computer.</span></span>

6.  <span data-ttu-id="e813a-147">通过键入以下命令注册已更新的模板。</span><span class="sxs-lookup"><span data-stu-id="e813a-147">Register the updated templates by typing the following command.</span></span>

    ``` syntax
    Register-UevTemplate <path to template folder>\*.xml
    ```

    <span data-ttu-id="e813a-148">这将注册位于指定模板文件夹中的所有设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="e813a-148">This will register all of the settings location templates located in the specified template folder.</span></span>

<span data-ttu-id="e813a-149">用户体验虚拟化提供以下 WMI 命令集。</span><span class="sxs-lookup"><span data-stu-id="e813a-149">User Experience Virtualization provides the following set of WMI commands.</span></span> <span data-ttu-id="e813a-150">管理员可以使用这些接口从 Windows PowerShell 中管理设置位置模板，并自动执行模板管理任务。</span><span class="sxs-lookup"><span data-stu-id="e813a-150">Administrators can use these interfaces to manage settings location templates from Windows PowerShell and automate template administrative tasks.</span></span>

**<span data-ttu-id="e813a-151">通过 WMI 管理设置位置模板</span><span class="sxs-lookup"><span data-stu-id="e813a-151">To manage settings location templates with WMI</span></span>**

1.  <span data-ttu-id="e813a-152">使用具有管理员权限的帐户打开 Windows PowerShell 窗口。</span><span class="sxs-lookup"><span data-stu-id="e813a-152">Use an account with administrator rights to open a Windows PowerShell window.</span></span>

2.  <span data-ttu-id="e813a-153">使用以下 WMI 命令注册和管理 UE-V 设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="e813a-153">Use the following WMI commands to register and manage the UE-V settings location templates.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p><strong><span data-ttu-id="e813a-154">PowerShell 命令</span><span class="sxs-lookup"><span data-stu-id="e813a-154">PowerShell command</span></span></strong></p></td>
    <td align="left"><p><strong><span data-ttu-id="e813a-155">描述</span><span class="sxs-lookup"><span data-stu-id="e813a-155">Description</span></span></strong></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="e813a-156">WmiObject-命名空间 root\Microsoft\UEV SettingsLocationTemplate |选择-Object TemplateId、TemplateName、TemplateVersion、Enabled |格式表-自动调整</span><span class="sxs-lookup"><span data-stu-id="e813a-156">Get-WmiObject -Namespace root\Microsoft\UEV SettingsLocationTemplate | Select-Object TemplateId,TemplateName, TemplateVersion,Enabled | Format-Table -Autosize</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e813a-157">列出为计算机注册的所有设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="e813a-157">Lists all the settings location templates registered for the computer.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="e813a-158">WmiMethod-命名空间 root\Microsoft\UEV 类 SettingsLocationTemplate 名称 Register-ArgumentList &lt; 模板路径&gt;</span><span class="sxs-lookup"><span data-stu-id="e813a-158">Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class SettingsLocationTemplate -Name Register -ArgumentList &lt;template path &gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e813a-159">使用 UE-V 注册设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="e813a-159">Registers a settings location template with UE-V.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="e813a-160">WmiMethod-命名空间 root\Microsoft\UEV 类 SettingsLocationTemplate-Name UnregisterByTemplateId-ArgumentList &lt; 模板 ID&gt;</span><span class="sxs-lookup"><span data-stu-id="e813a-160">Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class SettingsLocationTemplate -Name UnregisterByTemplateId -ArgumentList &lt;template ID&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e813a-161">使用 UE-V 注销设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="e813a-161">Unregisters a settings location template with UE-V.</span></span> <span data-ttu-id="e813a-162">模板注销后，UE-V 将不再同步在计算机之间的模板中定义的设置。</span><span class="sxs-lookup"><span data-stu-id="e813a-162">As soon as a template is unregistered, UE-V will no longer synchronize the settings that are defined in the template between computers.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="e813a-163">WmiMethod-命名空间 root\Microsoft\UEV 类 SettingsLocationTemplate-Name EnableByTemplateId-ArgumentList &lt; 模板 ID&gt;</span><span class="sxs-lookup"><span data-stu-id="e813a-163">Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class SettingsLocationTemplate -Name EnableByTemplateId -ArgumentList &lt;template ID&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e813a-164">使用 UE-V 启用设置位置模板</span><span class="sxs-lookup"><span data-stu-id="e813a-164">Enables a settings location template with UE-V</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="e813a-165">WmiMethod-命名空间 root\Microsoft\UEV 类 SettingsLocationTemplate-Name DisableByTemplateId-ArgumentList &lt; 模板 ID&gt;</span><span class="sxs-lookup"><span data-stu-id="e813a-165">Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class SettingsLocationTemplate -Name DisableByTemplateId -ArgumentList &lt;template ID&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e813a-166">使用 UE-V 禁用设置位置模板</span><span class="sxs-lookup"><span data-stu-id="e813a-166">Disables a settings location template with UE-V</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="e813a-167">WmiMethod-命名空间 root\Microsoft\UEV 类 SettingsLocationTemplate-Name Update-ArgumentList &lt; 模板路径&gt;</span><span class="sxs-lookup"><span data-stu-id="e813a-167">Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class SettingsLocationTemplate -Name Update -ArgumentList &lt;template path&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e813a-168">使用 UE-V 更新设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="e813a-168">Updates a settings location template with UE-V.</span></span> <span data-ttu-id="e813a-169">新模板的版本应高于现有模板的版本。</span><span class="sxs-lookup"><span data-stu-id="e813a-169">The new template should have a version that is higher than the existing one.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="e813a-170">WmiMethod-命名空间 root\Microsoft\UEV 类 SettingsLocationTemplate-Name Validate ArgumentList &lt; 模板路径&gt;</span><span class="sxs-lookup"><span data-stu-id="e813a-170">Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class SettingsLocationTemplate -Name Validate -ArgumentList &lt;template path&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e813a-171">确定给定设置位置模板是否符合其 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="e813a-171">Determines whether a given settings location template complies with its XML schema.</span></span></p></td>
    </tr>
    </tbody>
    </table>

     

**<span data-ttu-id="e813a-172">如何通过 PowerShell 部署 UE-V agent</span><span class="sxs-lookup"><span data-stu-id="e813a-172">How to deploy the UE-V agent with PowerShell</span></span>**

1.  <span data-ttu-id="e813a-173">在易于访问的网络共享中暂存 UE-V 安装程序文件。</span><span class="sxs-lookup"><span data-stu-id="e813a-173">Stage the UE-V installer file in an accessible network share.</span></span>

    <span data-ttu-id="e813a-174">**注意** 使用 AgentSetup.exe 部署32位和64位的 UE-V Agent 版本。</span><span class="sxs-lookup"><span data-stu-id="e813a-174">**Note** Use AgentSetup.exe to deploy both 32-bit and 64-bit versions of the UE-V Agent.</span></span> <span data-ttu-id="e813a-175">Windows Installer 文件版本、AgentSetupx86.msi 和 AgentSetupx64.msi 适用于每个体系结构。</span><span class="sxs-lookup"><span data-stu-id="e813a-175">Windows Installer Files versions, AgentSetupx86.msi and AgentSetupx64.msi, are available for each architecture.</span></span> <span data-ttu-id="e813a-176">若要在以后使用安装文件卸载 UE-V Agent，必须使用相同的文件类型。</span><span class="sxs-lookup"><span data-stu-id="e813a-176">To uninstall the UE-V Agent at a later time using the installation file, you must use the same file type.</span></span>

     

2.  <span data-ttu-id="e813a-177">使用以下 PowerShell 命令之一安装代理。</span><span class="sxs-lookup"><span data-stu-id="e813a-177">Use one of the following PowerShell commands to install the agent.</span></span>

    `& AgentSetup.exe /quiet /norestart /log "%temp%\UE-VAgentInstaller.log" SettingsStoragePath=\\server\settingsshare\%username%`

    `& msiexec.exe /i "<path to msi file>" /quiet /norestart /l*v "%temp%\UE-VAgentInstaller.log" SettingsStoragePath=\\server\settingsshare\%username%`

## <span data-ttu-id="e813a-178">相关主题</span><span class="sxs-lookup"><span data-stu-id="e813a-178">Related topics</span></span>


[<span data-ttu-id="e813a-179">使用 PowerShell 和 WMI 管理 UE-V 1.0 代理和程序包</span><span class="sxs-lookup"><span data-stu-id="e813a-179">Managing the UE-V 1.0 Agent and Packages with PowerShell and WMI</span></span>](managing-the-ue-v-10-agent-and-packages-with-powershell-and-wmi.md)

[<span data-ttu-id="e813a-180">管理 UE-V 1.0</span><span class="sxs-lookup"><span data-stu-id="e813a-180">Administering UE-V 1.0</span></span>](administering-ue-v-10.md)

[<span data-ttu-id="e813a-181">UE-V 1.0 的操作</span><span class="sxs-lookup"><span data-stu-id="e813a-181">Operations for UE-V 1.0</span></span>](operations-for-ue-v-10.md)

 

 





