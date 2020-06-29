---
title: 使用 Windows PowerShell 和 WMI 管理 UE-V 2. x 设置位置模板
description: 使用 Windows PowerShell 和 WMI 管理 UE-V 2. x 设置位置模板
author: dansimp
ms.assetid: b5253050-acc3-4274-90d0-1fa4c480331d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 9788ff1a11f1c70e52b75dd2187a198f5472f77f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798156"
---
# <span data-ttu-id="c232c-103">使用 Windows PowerShell 和 WMI 管理 UE-V 2. x 设置位置模板</span><span class="sxs-lookup"><span data-stu-id="c232c-103">Managing UE-V 2.x Settings Location Templates Using Windows PowerShell and WMI</span></span>


<span data-ttu-id="c232c-104">Microsoft 用户体验虚拟化（UE-V）2.0、2.1 和 2.1 SP1 使用 XML 设置位置模板来定义用户体验虚拟化捕获和应用的设置。</span><span class="sxs-lookup"><span data-stu-id="c232c-104">Microsoft User Experience Virtualization (UE-V) 2.0, 2.1, and 2.1 SP1 use XML settings location templates to define the settings that User Experience Virtualization captures and applies.</span></span> <span data-ttu-id="c232c-105">UE-V 包含一组标准设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="c232c-105">UE-V includes a set of standard settings location templates.</span></span> <span data-ttu-id="c232c-106">它还包括支持创建自定义设置位置模板的 UE-V 生成器工具。</span><span class="sxs-lookup"><span data-stu-id="c232c-106">It also includes the UE-V Generator tool that enables you to create custom settings location templates.</span></span> <span data-ttu-id="c232c-107">创建和部署设置位置模板后，可以使用 Windows PowerShell 和 Windows Management Instrumentation （WMI）管理这些模板。</span><span class="sxs-lookup"><span data-stu-id="c232c-107">After you create and deploy settings location templates, you can manage those templates by using Windows PowerShell and the Windows Management Instrumentation (WMI).</span></span> <span data-ttu-id="c232c-108">有关 UE-V PowerShell cmdlet 的完整列表，请参阅[ue-v 2 Cmdlet 参考](https://go.microsoft.com/fwlink/p/?LinkId=393495)（ https://go.microsoft.com/fwlink/p/?LinkId=393495) 。</span><span class="sxs-lookup"><span data-stu-id="c232c-108">For a complete list of UE-V PowerShell cmdlets, see [UE-V 2 Cmdlet Reference](https://go.microsoft.com/fwlink/p/?LinkId=393495) (https://go.microsoft.com/fwlink/p/?LinkId=393495).</span></span>

## <span data-ttu-id="c232c-109">使用 Windows PowerShell 管理 UE-V 2 设置位置模板</span><span class="sxs-lookup"><span data-stu-id="c232c-109">Manage UE-V 2 settings location templates by using Windows PowerShell</span></span>


<span data-ttu-id="c232c-110">UE-V 的 WMI 和 Windows PowerShell 功能包括启用、禁用、注册、更新和注销设置位置模板的功能。</span><span class="sxs-lookup"><span data-stu-id="c232c-110">The WMI and Windows PowerShell features of UE-V include the ability to enable, disable, register, update, and unregister settings location templates.</span></span> <span data-ttu-id="c232c-111">通过使用这些功能，你可以使用 UE-V Agent 自动执行注册、更新或注销模板的过程。</span><span class="sxs-lookup"><span data-stu-id="c232c-111">By using these features, you can automate the process of registering, updating, or unregistering templates with the UE-V Agent.</span></span> <span data-ttu-id="c232c-112">你还可以使用 WMI 和 Windows PowerShell 命令手动注册模板。</span><span class="sxs-lookup"><span data-stu-id="c232c-112">You can also manually register templates by using WMI and Windows PowerShell commands.</span></span> <span data-ttu-id="c232c-113">通过将这些功能与电子软件分发解决方案、组策略或其他自动部署方法（如脚本）结合使用，你可以进一步自动化该过程。</span><span class="sxs-lookup"><span data-stu-id="c232c-113">By using these features in conjunction with an electronic software distribution solution, Group Policy, or another automated deployment method such as a script, you can further automate that process.</span></span>

<span data-ttu-id="c232c-114">必须具有管理员权限才能更新、注册或注销设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="c232c-114">You must have administrator permissions to update, register, or unregister a settings location template.</span></span> <span data-ttu-id="c232c-115">启用、禁用或列出模板不需要管理员权限。</span><span class="sxs-lookup"><span data-stu-id="c232c-115">Administrator permissions are not required to enable, disable, or list templates.</span></span>

***<em><span data-ttu-id="c232c-116">使用 Windows PowerShell 管理设置位置模板</span><span class="sxs-lookup"><span data-stu-id="c232c-116">To manage settings location templates by using Windows PowerShell</span></span>ell</em>***

1.  <span data-ttu-id="c232c-117">使用具有管理员权限的帐户打开 Windows PowerShell 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="c232c-117">Use an account with administrator rights to open a Windows PowerShell command prompt.</span></span>

2.  <span data-ttu-id="c232c-118">使用以下 Windows PowerShell cmdlet 注册和管理 UE-V 设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="c232c-118">Use the following Windows PowerShell cmdlets to register and manage the UE-V settings location templates.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="c232c-119">Windows PowerShell 命令</span><span class="sxs-lookup"><span data-stu-id="c232c-119">Windows PowerShell command</span></span></th>
    <th align="left"><span data-ttu-id="c232c-120">描述</span><span class="sxs-lookup"><span data-stu-id="c232c-120">Description</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><code>Get-UevTemplate</code></p></td>
    <td align="left"><p><span data-ttu-id="c232c-121">列出计算机上注册的所有设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="c232c-121">Lists all the settings location templates that are registered on the computer.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Get-UevTemplate –Application &lt;string&gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="c232c-122">列出计算机上注册的所有设置位置模板，应用程序名称或模板名称包含 &lt; 字符串 &gt; 。</span><span class="sxs-lookup"><span data-stu-id="c232c-122">Lists all the settings location templates that are registered on the computer where the application name or template name contains &lt;string&gt;.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Get-UevTemplate –TemplateID &lt;string&gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="c232c-123">列出计算机上注册的所有设置位置模板，这些模板 ID 包含 &lt; 字符串 &gt; 。</span><span class="sxs-lookup"><span data-stu-id="c232c-123">Lists all the settings location templates that are registered on the computer where the template ID contains &lt;string&gt;.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Get-UevTemplate [-ApplicationOrTemplateID] &lt;string&gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="c232c-124">列出计算机上注册的所有设置位置模板（应用程序或模板名称或模板 ID 包含 &lt; 字符串） &gt; 。</span><span class="sxs-lookup"><span data-stu-id="c232c-124">Lists all the settings location templates that are registered on the computer where the application or template name, or template ID contains &lt;string&gt;.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Get-UevTemplateProgram [-ID] &lt;template ID&gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="c232c-125">获取程序和版本信息的名称，这些信息取决于模板 ID。</span><span class="sxs-lookup"><span data-stu-id="c232c-125">Gets the name of the program and version information, which depend on the template ID.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Get-UevAppXPackage</code></p></td>
    <td align="left"><p><span data-ttu-id="c232c-126">获取 Windows 应用的有效列表。</span><span class="sxs-lookup"><span data-stu-id="c232c-126">Gets the effective list of Windows apps.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Get-UevAppXPackage -Computer</code></p></td>
    <td align="left"><p><span data-ttu-id="c232c-127">获取为计算机配置的 Windows 应用的列表。</span><span class="sxs-lookup"><span data-stu-id="c232c-127">Gets the list of Windows apps that are configured for the computer.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Get-UevAppXPackage -CurrentComputerUser</code></p></td>
    <td align="left"><p><span data-ttu-id="c232c-128">获取为当前用户配置的 Windows 应用的列表。</span><span class="sxs-lookup"><span data-stu-id="c232c-128">Gets the list of Windows apps that are configured for the current user.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Register-UevTemplate [-Path] &lt;template file path&gt;[,&lt;template file path&gt;]</code></p></td>
    <td align="left"><p><span data-ttu-id="c232c-129">通过使用相对路径和/或文件路径中的通配符，使用 UE-V 注册一个或多个设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="c232c-129">Registers one or more settings location template with UE-V by using relative paths and/or wildcard characters in file paths.</span></span> <span data-ttu-id="c232c-130">注册模板后，UE-V 将在已注册模板的计算机之间的模板中定义的设置进行同步。</span><span class="sxs-lookup"><span data-stu-id="c232c-130">After a template is registered, UE-V synchronizes the settings that are defined in the template between computers that have the template registered.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Register-UevTemplate –LiteralPath &lt;template file path&gt;[,&lt;template file path&gt;]</code></p></td>
    <td align="left"><p><span data-ttu-id="c232c-131">使用文本路径将一个或多个设置位置模板注册到 UE-V，其中任何字符都不能解释为通配符。</span><span class="sxs-lookup"><span data-stu-id="c232c-131">Registers one or more settings location template with UE-V by using literal paths, where no characters can be interpreted as wildcard characters.</span></span> <span data-ttu-id="c232c-132">注册模板后，UE-V 将在已注册模板的计算机之间的模板中定义的设置进行同步。</span><span class="sxs-lookup"><span data-stu-id="c232c-132">After a template is registered, UE-V synchronizes the settings that are defined in the template between computers that have the template registered.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Unregister-UevTemplate [-ID] &lt;template ID&gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="c232c-133">使用 UE-V 注销设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="c232c-133">Unregisters a settings location template with UE-V.</span></span> <span data-ttu-id="c232c-134">当模板未注册时，UE-V 不再同步在计算机之间的模板中定义的设置。</span><span class="sxs-lookup"><span data-stu-id="c232c-134">When a template is unregistered, UE-V no longer synchronizes the settings that are defined in the template between computers.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Unregister-UevTemplate -All</code></p></td>
    <td align="left"><p><span data-ttu-id="c232c-135">通过 UE-V 注销所有设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="c232c-135">Unregisters all settings location templates with UE-V.</span></span> <span data-ttu-id="c232c-136">当模板未注册时，UE-V 不再同步在计算机之间的模板中定义的设置。</span><span class="sxs-lookup"><span data-stu-id="c232c-136">When a template is unregistered, UE-V no longer synchronizes the settings that are defined in the template between computers.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Update-UevTemplate [-Path] &lt;template file path&gt;[,&lt;template file path&gt;]</code></p></td>
    <td align="left"><p><span data-ttu-id="c232c-137">使用较新版本的模板更新一个或多个设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="c232c-137">Updates one or more settings location templates with a more recent version of the template.</span></span> <span data-ttu-id="c232c-138">在文件路径中使用相对路径和/或通配符。</span><span class="sxs-lookup"><span data-stu-id="c232c-138">Use relative paths and/or wildcard characters in the file paths.</span></span> <span data-ttu-id="c232c-139">新模板的版本应比现有模板的版本更新。</span><span class="sxs-lookup"><span data-stu-id="c232c-139">The new template should be a newer version than the existing template.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Update-UevTemplate –LiteralPath &lt;template file path&gt;[,&lt;template file path&gt;]</code></p></td>
    <td align="left"><p><span data-ttu-id="c232c-140">使用较新版本的模板更新一个或多个设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="c232c-140">Updates one or more settings location templates with a more recent version of the template.</span></span> <span data-ttu-id="c232c-141">使用指向模板文件的完整路径，其中任何字符均不能解释为通配符。</span><span class="sxs-lookup"><span data-stu-id="c232c-141">Use full paths to template files, where no characters can be interpreted as wildcard characters.</span></span> <span data-ttu-id="c232c-142">新模板的版本应比现有模板的版本更新。</span><span class="sxs-lookup"><span data-stu-id="c232c-142">The new template should be a newer version than the existing template.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Clear-UevAppXPackage –Computer [-PackageFamilyName] &lt;package family name&gt;[,&lt;package family name&gt;]</code></p></td>
    <td align="left"><p><span data-ttu-id="c232c-143">从计算机 Windows 应用列表中删除一个或多个 Windows 应用。</span><span class="sxs-lookup"><span data-stu-id="c232c-143">Removes one or more Windows apps from the computer Windows app list.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Clear-UevAppXPackage -CurrentComputerUser</code></p></td>
    <td align="left"><p><span data-ttu-id="c232c-144">从当前用户的 Windows 应用列表中删除 Windows 应用。</span><span class="sxs-lookup"><span data-stu-id="c232c-144">Removes Windows app from the current user Windows app list.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Clear-UevAppXPackage –Computer -All</code></p></td>
    <td align="left"><p><span data-ttu-id="c232c-145">从计算机的 Windows 应用列表中删除所有 Windows 应用。</span><span class="sxs-lookup"><span data-stu-id="c232c-145">Removes all Windows apps from the computer Windows app list.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Clear-UevAppXPackage [–CurrentComputerUser] [-PackageFamilyName] &lt;package family name&gt;[,&lt;package family name&gt;]</code></p></td>
    <td align="left"><p><span data-ttu-id="c232c-146">从当前用户的 Windows 应用列表中删除一个或多个 Windows 应用。</span><span class="sxs-lookup"><span data-stu-id="c232c-146">Removes one or more Windows apps from the current user Windows app list.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Clear-UevAppXPackage [–CurrentComputerUser] -All</code></p></td>
    <td align="left"><p><span data-ttu-id="c232c-147">从当前用户的 Windows 应用列表中删除所有 Windows 应用。</span><span class="sxs-lookup"><span data-stu-id="c232c-147">Removes all Windows apps from the current user Windows app list.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Disable-UevTemplate [-ID] &lt;template ID&gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="c232c-148">对计算机的当前用户禁用设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="c232c-148">Disables a settings location template for the current user of the computer.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Disable-UevAppXPackage –Computer [-PackageFamilyName] &lt;package family name&gt;[,&lt;package family name&gt;]</code></p></td>
    <td align="left"><p><span data-ttu-id="c232c-149">在计算机 Windows 应用列表中禁用一个或多个 Windows 应用。</span><span class="sxs-lookup"><span data-stu-id="c232c-149">Disables one or more Windows apps in the computer Windows app list.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Disable-UevAppXPackage [–CurrentComputerUser] [-PackageFamilyName] &lt;package family name&gt;[,&lt;package family name&gt;]</code></p></td>
    <td align="left"><p><span data-ttu-id="c232c-150">在当前用户的 Windows 应用列表中禁用一个或多个 Windows 应用。</span><span class="sxs-lookup"><span data-stu-id="c232c-150">Disables one or more Windows apps in the current user Windows app list.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Enable-UevTemplate [-ID] &lt;template ID&gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="c232c-151">为计算机的当前用户启用设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="c232c-151">Enables a settings location template for the current user of the computer.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Enable-UevAppXPackage –Computer [-PackageFamilyName] &lt;package family name&gt;[,&lt;package family name&gt;]</code></p></td>
    <td align="left"><p><span data-ttu-id="c232c-152">在计算机 Windows 应用列表中启用一个或多个 Windows 应用。</span><span class="sxs-lookup"><span data-stu-id="c232c-152">Enables one or more Windows apps in the computer Windows app list.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Enable-UevAppXPackage [–CurrentComputerUser] [-PackageFamilyName] &lt;package family name&gt;[,&lt;package family name&gt;]</code></p></td>
    <td align="left"><p><span data-ttu-id="c232c-153">在当前用户的 Windows 应用列表中启用一个或多个 Windows 应用。</span><span class="sxs-lookup"><span data-stu-id="c232c-153">Enables one or more Windows apps in the current user Windows app list.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Test-UevTemplate [-Path] &lt;template file path&gt;[,&lt;template file path&gt;]</code></p></td>
    <td align="left"><p><span data-ttu-id="c232c-154">确定一个或多个设置位置模板是否符合其 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="c232c-154">Determines whether one or more settings location templates comply with its XML schema.</span></span> <span data-ttu-id="c232c-155">可以使用相对路径和通配符。</span><span class="sxs-lookup"><span data-stu-id="c232c-155">Can use relative paths and wildcard characters.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Test-UevTemplate –LiteralPath &lt;template file path&gt;[,&lt;template file path&gt;]</code></p></td>
    <td align="left"><p><span data-ttu-id="c232c-156">确定一个或多个设置位置模板是否符合其 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="c232c-156">Determines whether one or more settings location templates comply with its XML schema.</span></span> <span data-ttu-id="c232c-157">路径必须是模板文件的完整路径，但不包含通配符字符。</span><span class="sxs-lookup"><span data-stu-id="c232c-157">The path must be a full path to the template file, but does not include wildcard characters.</span></span></p></td>
    </tr>
    </tbody>
    </table>



<span data-ttu-id="c232c-158">借助 UE-V Windows PowerShell 功能，你可以管理企业中部署的一组设置模板。</span><span class="sxs-lookup"><span data-stu-id="c232c-158">The UE-V Windows PowerShell features enable you to manage a group of settings templates that are deployed in your enterprise.</span></span> <span data-ttu-id="c232c-159">使用以下过程，使用 Windows PowerShell 管理一组模板。</span><span class="sxs-lookup"><span data-stu-id="c232c-159">Use the following procedure to manage a group of templates by using Windows PowerShell.</span></span>

**<span data-ttu-id="c232c-160">使用 Windows PowerShell 管理一组设置位置模板</span><span class="sxs-lookup"><span data-stu-id="c232c-160">To manage a group of settings location templates by using Windows PowerShell</span></span>**

1.  <span data-ttu-id="c232c-161">修改或更新所需的设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="c232c-161">Modify or update the desired settings location templates.</span></span>

2.  <span data-ttu-id="c232c-162">如果要修改或更新设置位置模板，请将这些设置位置模板部署到本地计算机可以访问的文件夹。</span><span class="sxs-lookup"><span data-stu-id="c232c-162">If you want to modify or update the settings location templates, deploy those settings location templates to a folder that is accessible to the local computer.</span></span>

3.  <span data-ttu-id="c232c-163">在本地计算机上，打开具有管理员权限的 Windows PowerShell 窗口。</span><span class="sxs-lookup"><span data-stu-id="c232c-163">On the local computer, open a Windows PowerShell window with administrator rights.</span></span>

4.  <span data-ttu-id="c232c-164">通过键入以下命令注销以前注册的所有版本的模板。</span><span class="sxs-lookup"><span data-stu-id="c232c-164">Unregister all the previously registered versions of the templates by typing the following command.</span></span>

    ``` syntax
    Unregister-UevTemplate -All
    ```

    <span data-ttu-id="c232c-165">此命令将注销计算机上的所有活动模板。</span><span class="sxs-lookup"><span data-stu-id="c232c-165">This command unregisters all active templates on the computer.</span></span>

5.  <span data-ttu-id="c232c-166">通过键入以下命令注册已更新的模板。</span><span class="sxs-lookup"><span data-stu-id="c232c-166">Register the updated templates by typing the following command.</span></span>

    ``` syntax
    Register-UevTemplate <path to template folder>\*.xml
    ```

    <span data-ttu-id="c232c-167">此命令将注册位于指定模板文件夹中的所有设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="c232c-167">This command registers all of the settings location templates that are located in the specified template folder.</span></span>

### <a href="" id="win8applist"></a><span data-ttu-id="c232c-168">Windows 应用列表</span><span class="sxs-lookup"><span data-stu-id="c232c-168">Windows app list</span></span>

<span data-ttu-id="c232c-169">通过在 Windows 应用列表中列出 Windows 应用，可以指定是启用还是禁用该应用以进行设置同步。</span><span class="sxs-lookup"><span data-stu-id="c232c-169">By listing a Windows app in the Windows app list, you specify whether that app is enabled or disabled for settings synchronization.</span></span> <span data-ttu-id="c232c-170">应用程序在列表中通过其程序包系列名称进行标识，以及是否应为该应用启用或禁用设置同步。</span><span class="sxs-lookup"><span data-stu-id="c232c-170">Apps are identified in the list by their Package Family name and whether settings synchronization should be enabled or disabled for that app.</span></span> <span data-ttu-id="c232c-171">将这些设置与未列出的默认同步行为设置一起使用时，你可以控制是否同步 Windows 应用。</span><span class="sxs-lookup"><span data-stu-id="c232c-171">When you use these settings along with the Unlisted Default Sync Behavior setting, you can control whether Windows apps are synchronized.</span></span>

<span data-ttu-id="c232c-172">若要显示已安装的 Windows 应用的程序包系列名称，请在 Windows PowerShell 命令提示符处输入：</span><span class="sxs-lookup"><span data-stu-id="c232c-172">To display the Package Family Name of installed Windows apps, at a Windows PowerShell command prompt, enter:</span></span>

``` syntax
Get-AppxPackage | Sort-Object PackageFamilyName | Format-Table PackageFamilyName
```

<span data-ttu-id="c232c-173">若要在 Windows PowerShell 命令提示符下显示可将计算机上的设置与计算机的程序包系列名称、启用状态和已启用源同步的 Windows 应用的列表，请输入：</span><span class="sxs-lookup"><span data-stu-id="c232c-173">To display a list of Windows apps that can synchronize settings on a computer with their package family name, enabled status, and enabled source, at a Windows PowerShell command prompt, enter:</span></span> `Get-UevAppxPackage`

**<span data-ttu-id="c232c-174">UevAppxPackage 属性的定义</span><span class="sxs-lookup"><span data-stu-id="c232c-174">Definitions of Get-UevAppxPackage properties</span></span>**

<a href="" id="displayname"></a>**<span data-ttu-id="c232c-175">DisplayName</span><span class="sxs-lookup"><span data-stu-id="c232c-175">DisplayName</span></span>**  
<span data-ttu-id="c232c-176">在公司设置中心应用程序中向用户显示的名称。</span><span class="sxs-lookup"><span data-stu-id="c232c-176">The name that is displayed to the user in the Company Settings Center application.</span></span> <span data-ttu-id="c232c-177">该 `DisplayName` 属性派生自 `PackageFamilyName` 属性。</span><span class="sxs-lookup"><span data-stu-id="c232c-177">The `DisplayName` property is derived from the `PackageFamilyName` property.</span></span>

<a href="" id="packagefamilyname"></a>**<span data-ttu-id="c232c-178">PackageFamilyName</span><span class="sxs-lookup"><span data-stu-id="c232c-178">PackageFamilyName</span></span>**  
<span data-ttu-id="c232c-179">为当前用户安装的程序包的名称。</span><span class="sxs-lookup"><span data-stu-id="c232c-179">The name of the package that is installed for the current user.</span></span>

<a href="" id="enabled"></a>**<span data-ttu-id="c232c-180">启用</span><span class="sxs-lookup"><span data-stu-id="c232c-180">Enabled</span></span>**  
<span data-ttu-id="c232c-181">定义是否将应用的设置配置为同步。</span><span class="sxs-lookup"><span data-stu-id="c232c-181">Defines whether the settings for the app are configured to synchronize.</span></span>

<a href="" id="enabledsource"></a>**<span data-ttu-id="c232c-182">EnabledSource</span><span class="sxs-lookup"><span data-stu-id="c232c-182">EnabledSource</span></span>**  
<span data-ttu-id="c232c-183">设置启用或禁用应用的配置所在的位置。</span><span class="sxs-lookup"><span data-stu-id="c232c-183">The location where the configuration that enables or disables the app is set.</span></span> <span data-ttu-id="c232c-184">可能的值包括： *NotSet*、 *LocalMachine*、 *LocalUser*、 *PolicyMachine*和*PolicyUser*。</span><span class="sxs-lookup"><span data-stu-id="c232c-184">Possible values are: *NotSet*, *LocalMachine*, *LocalUser*, *PolicyMachine*, and *PolicyUser*.</span></span>

<a href="" id="notset"></a>**<span data-ttu-id="c232c-185">NotSet</span><span class="sxs-lookup"><span data-stu-id="c232c-185">NotSet</span></span>**  
<span data-ttu-id="c232c-186">策略未配置为同步此应用。</span><span class="sxs-lookup"><span data-stu-id="c232c-186">The policy is not configured to synchronize this app.</span></span>

<a href="" id="localmachine"></a>**<span data-ttu-id="c232c-187">Store</span><span class="sxs-lookup"><span data-stu-id="c232c-187">LocalMachine</span></span>**  
<span data-ttu-id="c232c-188">启用状态在注册表的 "本地计算机" 部分中设置。</span><span class="sxs-lookup"><span data-stu-id="c232c-188">The enabled state is set in the local computer section of the registry.</span></span>

<a href="" id="localuser"></a>**<span data-ttu-id="c232c-189">LocalUser</span><span class="sxs-lookup"><span data-stu-id="c232c-189">LocalUser</span></span>**  
<span data-ttu-id="c232c-190">启用状态在注册表的 "当前用户" 部分中设置。</span><span class="sxs-lookup"><span data-stu-id="c232c-190">The enabled state is set in the current user section of the registry.</span></span>

<a href="" id="policymachine"></a>**<span data-ttu-id="c232c-191">PolicyMachine</span><span class="sxs-lookup"><span data-stu-id="c232c-191">PolicyMachine</span></span>**  
<span data-ttu-id="c232c-192">启用状态在注册表的 "本地计算机" 部分的 "策略" 部分中设置。</span><span class="sxs-lookup"><span data-stu-id="c232c-192">The enabled state is set in the policy section of the local computer section of the registry.</span></span>

<span data-ttu-id="c232c-193">若要获取用户配置的 Windows 应用列表，请在 Windows PowerShell 命令提示符处输入：</span><span class="sxs-lookup"><span data-stu-id="c232c-193">To get the user-configured list of Windows apps, at the Windows PowerShell command prompt, enter:</span></span> `Get-UevAppxPackage –CurrentComputerUser`

<span data-ttu-id="c232c-194">若要获取计算机配置的 Windows 应用列表，请在 Windows PowerShell 命令提示符处输入：</span><span class="sxs-lookup"><span data-stu-id="c232c-194">To get the computer-configured list of Windows apps, at the Windows PowerShell command prompt, enter:</span></span> `Get-UevAppxPackage –Computer`

<span data-ttu-id="c232c-195">对于参数、CurrentComputerUser 或计算机，cmdlet 返回在用户或计算机级别配置的 Windows 应用的列表。</span><span class="sxs-lookup"><span data-stu-id="c232c-195">For either parameter, CurrentComputerUser or Computer, the cmdlet returns a list of the Windows apps that are configured at the user or at the computer level.</span></span>

**<span data-ttu-id="c232c-196">属性的定义</span><span class="sxs-lookup"><span data-stu-id="c232c-196">Definitions of properties</span></span>**

<a href="" id="displayname"></a>**<span data-ttu-id="c232c-197">DisplayName</span><span class="sxs-lookup"><span data-stu-id="c232c-197">DisplayName</span></span>**  
<span data-ttu-id="c232c-198">在公司设置中心应用程序中向用户显示的名称。</span><span class="sxs-lookup"><span data-stu-id="c232c-198">The name that is displayed to the user in the Company Settings Center application.</span></span> <span data-ttu-id="c232c-199">该 `DisplayName` 属性派生自 `PackageFamilyName` 属性。</span><span class="sxs-lookup"><span data-stu-id="c232c-199">The `DisplayName` property is derived from the `PackageFamilyName` property.</span></span>

<a href="" id="packagefamilyname"></a>**<span data-ttu-id="c232c-200">PackageFamilyName</span><span class="sxs-lookup"><span data-stu-id="c232c-200">PackageFamilyName</span></span>**  
<span data-ttu-id="c232c-201">为当前用户安装的程序包的名称。</span><span class="sxs-lookup"><span data-stu-id="c232c-201">The name of the package that is installed for the current user.</span></span>

<a href="" id="enabled"></a>**<span data-ttu-id="c232c-202">启用</span><span class="sxs-lookup"><span data-stu-id="c232c-202">Enabled</span></span>**  
<span data-ttu-id="c232c-203">定义是否将应用的设置配置为针对指定的交换机（即**用户**或**计算机**）进行同步。</span><span class="sxs-lookup"><span data-stu-id="c232c-203">Defines whether the settings for the app are configured to synchronize for the specified switch, that is, **user** or **computer**.</span></span>

<a href="" id="installed"></a>**<span data-ttu-id="c232c-204">已安装</span><span class="sxs-lookup"><span data-stu-id="c232c-204">Installed</span></span>**  
<span data-ttu-id="c232c-205">如果应用（即为当前用户安装了 PackageFamilyName）为 True，则为 True。</span><span class="sxs-lookup"><span data-stu-id="c232c-205">True if the app, that is, the PackageFamilyName is installed for the current user.</span></span>

### <span data-ttu-id="c232c-206">使用 WMI 管理 UE-V 2 设置位置模板</span><span class="sxs-lookup"><span data-stu-id="c232c-206">Manage UE-V 2 settings location templates by using WMI</span></span>

<span data-ttu-id="c232c-207">用户体验虚拟化提供以下 WMI 命令集。</span><span class="sxs-lookup"><span data-stu-id="c232c-207">User Experience Virtualization provides the following set of WMI commands.</span></span> <span data-ttu-id="c232c-208">管理员可以使用这些接口从 Windows PowerShell 中管理设置位置模板，并自动执行模板管理任务。</span><span class="sxs-lookup"><span data-stu-id="c232c-208">Administrators can use these interfaces to manage settings location templates from Windows PowerShell and automate template administrative tasks.</span></span>

**<span data-ttu-id="c232c-209">使用 WMI 管理设置位置模板</span><span class="sxs-lookup"><span data-stu-id="c232c-209">To manage settings location templates by using WMI</span></span>**

1.  <span data-ttu-id="c232c-210">使用具有管理员权限的帐户打开 Windows PowerShell 窗口。</span><span class="sxs-lookup"><span data-stu-id="c232c-210">Use an account with administrator rights to open a Windows PowerShell window.</span></span>

2.  <span data-ttu-id="c232c-211">使用以下 WMI 命令注册和管理 UE-V 设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="c232c-211">Use the following WMI commands to register and manage the UE-V settings location templates.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><code>                         Windows PowerShell command</code></th>
    <th align="left"><span data-ttu-id="c232c-212">描述</span><span class="sxs-lookup"><span data-stu-id="c232c-212">Description</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><code>Get-WmiObject -Namespace root\Microsoft\UEV SettingsLocationTemplate | Select-Object TemplateId,TemplateName, TemplateVersion,Enabled | Format-Table -Autosize</code></p></td>
    <td align="left"><p><span data-ttu-id="c232c-213">列出为计算机注册的所有设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="c232c-213">Lists all the settings location templates that are registered for the computer.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Invoke-WmiMethod –Namespace root\Microsoft\UEV –Class SettingsLocationTemplate –Name GetProcessInfoByTemplateId &lt;template Id&gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="c232c-214">获取程序和版本信息的名称，该名称取决于模板名称。</span><span class="sxs-lookup"><span data-stu-id="c232c-214">Gets the name of the program and version information, which depends on the template name.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Get-WmiObject -Namespace root\Microsoft\UEV EffectiveWindows8App</code></p></td>
    <td align="left"><p><span data-ttu-id="c232c-215">获取 Windows 应用的有效列表。</span><span class="sxs-lookup"><span data-stu-id="c232c-215">Gets the effective list of Windows apps.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="c232c-216">WmiObject-命名空间 root\Microsoft\UEV MachineConfiguredWindows8App</span><span class="sxs-lookup"><span data-stu-id="c232c-216">Get-WmiObject -Namespace root\Microsoft\UEV MachineConfiguredWindows8App</span></span></p></td>
    <td align="left"><p><span data-ttu-id="c232c-217">获取为计算机配置的 Windows 应用的列表。</span><span class="sxs-lookup"><span data-stu-id="c232c-217">Gets the list of Windows apps that are configured for the computer.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Get-WmiObject -Namespace root\Microsoft\UEV UserConfiguredWindows8App</code></p></td>
    <td align="left"><p><span data-ttu-id="c232c-218">获取为当前用户配置的 Windows 应用的列表。</span><span class="sxs-lookup"><span data-stu-id="c232c-218">Gets the list of Windows apps that are configured for the current user.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class SettingsLocationTemplate -Name Register -ArgumentList &lt;template path &gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="c232c-219">使用 UE-V 注册设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="c232c-219">Registers a settings location template with UE-V.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class SettingsLocationTemplate -Name UnregisterByTemplateId -ArgumentList &lt;template ID&gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="c232c-220">使用 UE-V 注销设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="c232c-220">Unregisters a settings location template with UE-V.</span></span> <span data-ttu-id="c232c-221">模板注销后，UE-V 不再同步在计算机之间的模板中定义的设置。</span><span class="sxs-lookup"><span data-stu-id="c232c-221">As soon as a template is unregistered, UE-V no longer synchronizes the settings that are defined in the template between computers.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class SettingsLocationTemplate -Name Update -ArgumentList &lt;template path&gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="c232c-222">使用 UE-V 更新设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="c232c-222">Updates a settings location template with UE-V.</span></span> <span data-ttu-id="c232c-223">新模板的版本应比现有模板新。</span><span class="sxs-lookup"><span data-stu-id="c232c-223">The new template should be a newer version than the existing one.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class MachineConfiguredWindows8App -Name RemoveApp -ArgumentList &lt;package family name | package family name&gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="c232c-224">从计算机 Windows 应用列表中删除一个或多个 Windows 应用。</span><span class="sxs-lookup"><span data-stu-id="c232c-224">Removes one or more Windows apps from the computer Windows app list.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class UserConfiguredWindows8App -Name RemoveApp -ArgumentList &lt;package family name | package family name&gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="c232c-225">从当前用户的 Windows 应用列表中删除一个或多个 Windows 应用。</span><span class="sxs-lookup"><span data-stu-id="c232c-225">Removes one or more Windows apps from the current user Windows app list.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class SettingsLocationTemplate -Name DisableByTemplateId -ArgumentList &lt;template ID&gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="c232c-226">通过 UE-V 禁用一个或多个设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="c232c-226">Disables one or more settings location templates with UE-V.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class MachineConfiguredWindows8App -Name DisableApp -ArgumentList &lt;package family name | package family name&gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="c232c-227">在计算机 Windows 应用列表中禁用一个或多个 Windows 应用。</span><span class="sxs-lookup"><span data-stu-id="c232c-227">Disables one or more Windows apps in the computer Windows app list.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class UserConfiguredWindows8App -Name DisableApp -ArgumentList &lt;package family name | package family name&gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="c232c-228">在当前用户的 Windows 应用列表中禁用一个或多个 Windows 应用。</span><span class="sxs-lookup"><span data-stu-id="c232c-228">Disables one or more Windows apps in the current user Windows app list.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class SettingsLocationTemplate -Name EnableByTemplateId -ArgumentList &lt;template ID&gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="c232c-229">使用 UE-V 启用设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="c232c-229">Enables a settings location template with UE-V.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class MachineConfiguredWindows8App -Name EnableApp -ArgumentList &lt;package family name | package family name&gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="c232c-230">在计算机 Windows 应用列表中启用 Windows 应用。</span><span class="sxs-lookup"><span data-stu-id="c232c-230">Enables Windows apps in the computer Windows app list.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class UserConfiguredWindows8App -Name EnableApp -ArgumentList &lt;package family name | package family name&gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="c232c-231">在当前用户的 Windows 应用列表中启用 Windows 应用。</span><span class="sxs-lookup"><span data-stu-id="c232c-231">Enables Windows apps in the current user Windows app list.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class SettingsLocationTemplate -Name Validate -ArgumentList &lt;template path&gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="c232c-232">确定给定设置位置模板是否符合其 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="c232c-232">Determines whether a given settings location template complies with its XML schema.</span></span></p></td>
    </tr>
    </tbody>
    </table>



~~~
**Note**  
Where a list of Package Family Names is called by the WMI command, the list must be in quotes and separated by a pipe symbol, for example, `"<package family name | package family name>"`.
~~~



### <span data-ttu-id="c232c-233">使用 Windows PowerShell 部署 UE-V Agent</span><span class="sxs-lookup"><span data-stu-id="c232c-233">Deploying the UE-V Agent using Windows PowerShell</span></span>

**<span data-ttu-id="c232c-234">如何使用 Windows PowerShell 部署 UE-V Agent</span><span class="sxs-lookup"><span data-stu-id="c232c-234">How to deploy the UE-V Agent by using Windows PowerShell</span></span>**

1.  <span data-ttu-id="c232c-235">在易于访问的网络共享中暂存 UE-V Agent 安装包。</span><span class="sxs-lookup"><span data-stu-id="c232c-235">Stage the UE-V Agent installation package in an accessible network share.</span></span>

    **<span data-ttu-id="c232c-236">注意</span><span class="sxs-lookup"><span data-stu-id="c232c-236">Note</span></span>**  
    <span data-ttu-id="c232c-237">使用 AgentSetup.exe 部署32位和64位的 UE-V Agent 版本。</span><span class="sxs-lookup"><span data-stu-id="c232c-237">Use AgentSetup.exe to deploy both 32-bit and 64-bit versions of the UE-V Agent.</span></span> <span data-ttu-id="c232c-238">Windows Installer 程序包（AgentSetupx86.msi 和 AgentSetupx64.msi）可用于每个体系结构。</span><span class="sxs-lookup"><span data-stu-id="c232c-238">The Windows Installer packages, AgentSetupx86.msi and AgentSetupx64.msi, are available for each architecture.</span></span> <span data-ttu-id="c232c-239">若要在以后使用安装文件卸载 UE-V Agent，必须使用相同的文件类型。</span><span class="sxs-lookup"><span data-stu-id="c232c-239">To uninstall the UE-V Agent at a later time by using the installation file, you must use the same file type.</span></span>



2.  <span data-ttu-id="c232c-240">使用以下 Windows PowerShell 命令之一安装 UE-V Agent。</span><span class="sxs-lookup"><span data-stu-id="c232c-240">Use one of the following Windows PowerShell commands to install the UE-V Agent.</span></span>

    -   `& AgentSetup.exe /quiet /norestart /log "%temp%\UE-VAgentInstaller.log" SettingsStoragePath=\\server\settingsshare\%username%`

    -   `& msiexec.exe /i "<path to msi file>" /quiet /norestart /l*v "%temp%\UE-VAgentInstaller.log" SettingsStoragePath=\\server\settingsshare\%username%`

<span data-ttu-id="c232c-241">已**获得有关 ue-v 的建议**？</span><span class="sxs-lookup"><span data-stu-id="c232c-241">**Got a suggestion for UE-V**?</span></span> <span data-ttu-id="c232c-242">在[此处](http://uev.uservoice.com/forums/280428-microsoft-user-experience-virtualization)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="c232c-242">Add or vote on suggestions [here](http://uev.uservoice.com/forums/280428-microsoft-user-experience-virtualization).</span></span> <span data-ttu-id="c232c-243">是否**遇到了 ue-v 问题**？</span><span class="sxs-lookup"><span data-stu-id="c232c-243">**Got a UE-V issue**?</span></span> <span data-ttu-id="c232c-244">使用[Ue-v TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopuev)。</span><span class="sxs-lookup"><span data-stu-id="c232c-244">Use the [UE-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopuev).</span></span>

## <span data-ttu-id="c232c-245">相关主题</span><span class="sxs-lookup"><span data-stu-id="c232c-245">Related topics</span></span>


[<span data-ttu-id="c232c-246">管理具有 Windows PowerShell 和 WMI 的 UE-V 2。</span><span class="sxs-lookup"><span data-stu-id="c232c-246">Administering UE-V 2.x with Windows PowerShell and WMI</span></span>](administering-ue-v-2x-with-windows-powershell-and-wmi-both-uevv2.md)

[<span data-ttu-id="c232c-247">管理 UE-V 2. x</span><span class="sxs-lookup"><span data-stu-id="c232c-247">Administering UE-V 2.x</span></span>](administering-ue-v-2x-new-uevv2.md)









