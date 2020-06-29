---
title: 部署自定义应用程序的 UE-V 2。
description: 部署自定义应用程序的 UE-V 2。
author: dansimp
ms.assetid: f7cb089f-d764-4a93-82b6-926fe0385a23
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 07/19/2016
ms.openlocfilehash: 217f647d948df016c4a6b72736669c2b3305b705
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803561"
---
# <span data-ttu-id="6ed2b-103">部署自定义应用程序的 UE-V 2。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-103">Deploy UE-V 2.x for Custom Applications</span></span>


<span data-ttu-id="6ed2b-104">Microsoft 用户体验虚拟化（UE-V）2.0。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-104">Microsoft User Experience Virtualization (UE-V) 2.0.</span></span> <span data-ttu-id="6ed2b-105">2.1 和 2.1 SP1 使用名为**设置位置模板**的 XML 文件监视和同步用户计算机之间的桌面应用程序设置和 Windows 桌面设置。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-105">2.1, and 2.1 SP1 use XML files called **settings location templates** to monitor and synchronize desktop application settings and Windows desktop settings between user computers.</span></span> <span data-ttu-id="6ed2b-106">默认情况下，某些设置位置模板包含在 UE-V 中。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-106">By default, some settings location templates are included in UE-V.</span></span> <span data-ttu-id="6ed2b-107">但是，如果你希望同步除默认模板中包含的桌面应用程序之外的桌面应用程序的设置，你可以使用 UE-V 生成器创建你自己的自定义设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-107">But if you want to synchronize settings for desktop applications other than those included in the default templates, you can create your own custom settings location templates by using the UE-V Generator.</span></span>

<span data-ttu-id="6ed2b-108">一旦您已阅读[准备 ue-v 2. x 部署](prepare-a-ue-v-2x-deployment-new-uevv2.md)中的规划资料并确定要同步自定义应用程序（第三方、业务线等）的设置，您将按照本主题中的说明部署 ue-v 的功能。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-108">Once you have read through the planning material in [Prepare a UE-V 2.x Deployment](prepare-a-ue-v-2x-deployment-new-uevv2.md) and have decided that you want to synchronize settings for custom applications (third-party, line-of-business, etc.), you will deploy the features of UE-V as described in this topic.</span></span> <span data-ttu-id="6ed2b-109">若要开始，下面是同步自定义应用程序的设置所需的主要步骤：</span><span class="sxs-lookup"><span data-stu-id="6ed2b-109">To start, here are the main steps required to synchronize settings for custom applications:</span></span>

-   [<span data-ttu-id="6ed2b-110">安装 UEV 生成器</span><span class="sxs-lookup"><span data-stu-id="6ed2b-110">Install the UEV Generator</span></span>](#uevgen)

    <span data-ttu-id="6ed2b-111">使用 UEV 生成器创建自定义 XML 设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-111">Use the UEV Generator to create custom XML settings location templates.</span></span>

-   [<span data-ttu-id="6ed2b-112">配置 UE-V 设置模板目录</span><span class="sxs-lookup"><span data-stu-id="6ed2b-112">Configure a UE-V settings template catalog</span></span>](#deploycatalogue)

    <span data-ttu-id="6ed2b-113">你可以定义存储自定义设置位置模板的此路径。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-113">You can define this path where custom settings location templates are stored.</span></span>

-   [<span data-ttu-id="6ed2b-114">创建自定义设置位置模板</span><span class="sxs-lookup"><span data-stu-id="6ed2b-114">Create custom settings location templates</span></span>](#createcustomtemplates)

    <span data-ttu-id="6ed2b-115">这些自定义模板允许用户同步自定义应用程序的设置。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-115">These custom templates let users sync settings for custom applications.</span></span>

-   [<span data-ttu-id="6ed2b-116">部署自定义设置位置模板</span><span class="sxs-lookup"><span data-stu-id="6ed2b-116">Deploy the custom settings location templates</span></span>](#deploycustomtemplates)

    <span data-ttu-id="6ed2b-117">在测试自定义模板以确保正确同步设置后，你可以通过以下方式之一部署这些模板：</span><span class="sxs-lookup"><span data-stu-id="6ed2b-117">After you test the custom template to ensure that settings are synced correctly, you can deploy these templates in one of these ways:</span></span>

    -   <span data-ttu-id="6ed2b-118">通过现有部署基础结构（如 Configuration Manager）</span><span class="sxs-lookup"><span data-stu-id="6ed2b-118">Through your existing deployment infrastructure, such as Configuration Manager</span></span>

    -   <span data-ttu-id="6ed2b-119">使用组策略首选项</span><span class="sxs-lookup"><span data-stu-id="6ed2b-119">By using Group Policy preferences</span></span>

    -   [<span data-ttu-id="6ed2b-120">部署 UE-V 设置模板目录</span><span class="sxs-lookup"><span data-stu-id="6ed2b-120">Deploy a UE-V settings template catalog</span></span>](#deploycatalogue)

    <span data-ttu-id="6ed2b-121">**注意** 使用 ESD 或组策略部署的模板必须使用 UE-V Windows Management Instrumentation （WMI）或 Windows PowerShell 注册。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-121">**Note** Templates that are deployed by using ESD or Group Policy must be registered with UE-V Windows Management Instrumentation (WMI) or Windows PowerShell.</span></span>

     

## <span data-ttu-id="6ed2b-122">准备为自定义应用程序部署 UE-V 2。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-122">Prepare to Deploy UE-V 2.x for Custom Applications</span></span>


<span data-ttu-id="6ed2b-123">开始部署处理自定义应用程序的 UE-V 功能之前，只需查看几个方面。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-123">Before you start deploying the UE-V features that handle custom applications, there are just a couple things to review.</span></span>

### <span data-ttu-id="6ed2b-124">UE-V 生成器</span><span class="sxs-lookup"><span data-stu-id="6ed2b-124">The UE-V Generator</span></span>

<span data-ttu-id="6ed2b-125">UE-V 生成器监视应用程序以发现和捕获应用程序存储其设置的位置。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-125">The UE-V Generator monitors an application to discover and capture the locations where the application stores its settings.</span></span> <span data-ttu-id="6ed2b-126">被监视的应用程序必须是传统的应用程序。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-126">The application that is monitored must be a traditional application.</span></span> <span data-ttu-id="6ed2b-127">使用 UE-V 生成器创建设置位置模板，但无法从这些应用程序类型创建设置位置模板：</span><span class="sxs-lookup"><span data-stu-id="6ed2b-127">You use the UE-V Generator to create settings location templates, but it cannot create a settings location template from these application types:</span></span>

-   <span data-ttu-id="6ed2b-128">虚拟化应用程序</span><span class="sxs-lookup"><span data-stu-id="6ed2b-128">Virtualized applications</span></span>

-   <span data-ttu-id="6ed2b-129">通过终端服务提供的应用程序</span><span class="sxs-lookup"><span data-stu-id="6ed2b-129">Applications that are offered through Terminal Services</span></span>

-   <span data-ttu-id="6ed2b-130">Java 应用程序</span><span class="sxs-lookup"><span data-stu-id="6ed2b-130">Java applications</span></span>

-   <span data-ttu-id="6ed2b-131">Windows 应用</span><span class="sxs-lookup"><span data-stu-id="6ed2b-131">Windows apps</span></span>

<span data-ttu-id="6ed2b-132">**注意** UE-V 设置位置模板不能从虚拟化应用程序或终端服务应用程序创建。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-132">**Note** UE-V settings location templates cannot be created from virtualized applications or Terminal Services applications.</span></span> <span data-ttu-id="6ed2b-133">但是，可将使用模板同步的设置应用于这些应用程序。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-133">However, settings that are synchronized by using the templates can be applied to those applications.</span></span> <span data-ttu-id="6ed2b-134">若要创建支持虚拟桌面基础结构（VDI）和终端服务应用程序的模板，请使用 UE-V 生成器打开应用程序的 Windows Installer （.msi）程序包版本。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-134">To create templates that support Virtual Desktop Infrastructure (VDI) and Terminal Services applications, open a version of the Windows Installer (.msi) package of the application by using the UE-V Generator.</span></span> <span data-ttu-id="6ed2b-135">有关同步虚拟应用程序的设置的详细信息，请参阅[使用 ue-v 2 和应用程序虚拟化应用](using-ue-v-2x-with-application-virtualization-applications-both-uevv2.md)程序。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-135">For more information about synchronizing settings for virtual applications, see [Using UE-V 2.x with Application Virtualization Applications](using-ue-v-2x-with-application-virtualization-applications-both-uevv2.md).</span></span>

 

<span data-ttu-id="6ed2b-136">**排除的位置：** 发现过程排除了通常存储应用软件文件的位置，这些文件不会在用户计算机或计算环境之间同步设置。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-136">**Excluded Locations:** The discovery process excludes locations that commonly store application software files that do not synchronize settings well between user computers or computing environments.</span></span> <span data-ttu-id="6ed2b-137">默认情况下，这些值将被排除：</span><span class="sxs-lookup"><span data-stu-id="6ed2b-137">By default, these are excluded:</span></span>

-   <span data-ttu-id="6ed2b-138">HKEY \ _CURRENT 已登录用户无法向其写入值的 _USER 注册表项和文件</span><span class="sxs-lookup"><span data-stu-id="6ed2b-138">HKEY\_CURRENT\_USER registry keys and files to which the logged-on user cannot write values</span></span>

-   <span data-ttu-id="6ed2b-139">HKEY \ _CURRENT \ _USER 与 Windows 操作系统的核心功能相关联的注册表项和文件</span><span class="sxs-lookup"><span data-stu-id="6ed2b-139">HKEY\_CURRENT\_USER registry keys and files that are associated with the core functionality of the Windows operating system</span></span>

-   <span data-ttu-id="6ed2b-140">位于 HKEY \ _LOCAL \ _MACHINE 配置单元中的所有注册表项</span><span class="sxs-lookup"><span data-stu-id="6ed2b-140">All registry keys that are located in the HKEY\_LOCAL\_MACHINE hive</span></span>

-   <span data-ttu-id="6ed2b-141">位于程序文件目录中的文件</span><span class="sxs-lookup"><span data-stu-id="6ed2b-141">Files that are located in Program Files directories</span></span>

-   <span data-ttu-id="6ed2b-142">位于用户 \\ [User name \] \\ AppData \\ LocalLow 中的文件</span><span class="sxs-lookup"><span data-stu-id="6ed2b-142">Files that are located in Users \\ \[User name\] \\ AppData \\ LocalLow</span></span>

-   <span data-ttu-id="6ed2b-143">位于% Systemroot% 中的 Windows 操作系统文件</span><span class="sxs-lookup"><span data-stu-id="6ed2b-143">Windows operating system files that are located in %Systemroot%</span></span>

<span data-ttu-id="6ed2b-144">如果需要在排除位置存储的注册表项和文件同步应用程序设置，则可以在模板创建过程中手动将位置添加到设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-144">If registry keys and files that are stored in excluded locations are required to synchronize application settings, you can manually add the locations to the settings location template during the template creation process.</span></span>
<span data-ttu-id="6ed2b-145">但是，只有对 HKEY \ _CURRENT \ _USER 配置单元的更改才会同步。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-145">However, only changes to the HKEY\_CURRENT\_USER hive will be sync-ed.</span></span>

### <span data-ttu-id="6ed2b-146">替换默认的 Microsoft 模板</span><span class="sxs-lookup"><span data-stu-id="6ed2b-146">Replace the default Microsoft templates</span></span>

<span data-ttu-id="6ed2b-147">UE-V Agent 将为常见的 Microsoft 应用程序和 Windows 设置安装默认设置位置模板组。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-147">The UE-V Agent installs a default group of settings location templates for common Microsoft applications and Windows settings.</span></span> <span data-ttu-id="6ed2b-148">如果自定义这些模板或创建设置位置模板以同步自定义应用程序的设置，则可以将 UE-V Agent 配置为使用设置模板目录来存储模板。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-148">If you customize these templates, or create settings location templates to synchronize settings for custom applications, the UE-V Agent can be configured to use a settings template catalog to store the templates.</span></span> <span data-ttu-id="6ed2b-149">在这种情况下，你将需要在设置模板目录中包含默认模板以及自定义模板。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-149">In this case, you will need to include the default templates along with the custom templates in the settings template catalog.</span></span>

<span data-ttu-id="6ed2b-150">在[部署 Ue-v Agent](https://technet.microsoft.com/library/dn458891.aspx#agent)时，可以使用命令行参数 `RegisterMSTemplates` 禁用默认 Microsoft 模板的注册。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-150">When you [Deploy a UE-V Agent](https://technet.microsoft.com/library/dn458891.aspx#agent), you can use the command-line parameter `RegisterMSTemplates` to disable the registration of the default Microsoft templates.</span></span>

<span data-ttu-id="6ed2b-151">使用组策略配置设置模板目录路径时，可以选择替换默认的 Microsoft 模板。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-151">When you use Group Policy to configure the settings template catalog path, you can choose to replace the default Microsoft templates.</span></span> <span data-ttu-id="6ed2b-152">如果将策略设置配置为替换默认的 Microsoft 模板，则将删除由 UE-V Agent 安装的所有默认 Microsoft 模板，并且仅使用位于设置模板目录中的模板。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-152">If you configure the policy settings to replace the default Microsoft templates, all of the default Microsoft templates that are installed by the UE-V Agent are deleted and only the templates that are located in the settings template catalog are used.</span></span> <span data-ttu-id="6ed2b-153">UE-V Agent 配置设置参数 `RegisterMSTemplates` 必须设置为*true*才能替代默认的 Microsoft 模板。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-153">The UE-V Agent configuration setting parameter `RegisterMSTemplates` must be set to *true* in order to override the default Microsoft template.</span></span>

<span data-ttu-id="6ed2b-154">**注意** 如果在启用此策略设置后禁用此策略设置，则 UE-V Agent 不会还原默认的 Microsoft 模板。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-154">**Note** If you disable this policy setting after it has been enabled, the UE-V Agent does not restore the default Microsoft templates.</span></span>

 

<span data-ttu-id="6ed2b-155">如果设置模板目录中存在使用与默认 Microsoft 模板相同 ID 的自定义模板，并且未将 UE-V Agent 配置为替换默认的 Microsoft 模板，则忽略 Microsoft 模板。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-155">If there are customized templates in the settings template catalog that use the same ID as the default Microsoft templates, and the UE-V Agent is not configured to replace the default Microsoft templates, the Microsoft templates are ignored.</span></span>

<span data-ttu-id="6ed2b-156">你还可以使用 UE-V Windows PowerShell 功能替换默认模板。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-156">You can also replace the default templates by using the UE-V Windows PowerShell features.</span></span> <span data-ttu-id="6ed2b-157">若要将默认的 Microsoft 模板替换为 Windows PowerShell，请注销所有默认的 Microsoft 模板，然后注册自定义模板。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-157">To replace the default Microsoft template with Windows PowerShell, unregister all of the default Microsoft templates, and then register the customized templates.</span></span>

<span data-ttu-id="6ed2b-158">**注意** 即使为应用程序部署新的设置位置模板，旧的设置程序包仍保留在设置存储位置。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-158">**Note** Old settings packages remain in the settings storage location even if you deploy new settings location templates for an application.</span></span> <span data-ttu-id="6ed2b-159">这些程序包不会由代理读取，但它们都不会自动删除。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-159">These packages are not read by the agent, but neither are they automatically deleted.</span></span>

 

## <a href="" id="uevgen"></a><span data-ttu-id="6ed2b-160">安装 UEV 生成器</span><span class="sxs-lookup"><span data-stu-id="6ed2b-160">Install the UEV 2.x Generator</span></span>


<span data-ttu-id="6ed2b-161">在可用于创建自定义设置位置模板的计算机上安装 Microsoft 用户体验虚拟化（UE-V）2.0 生成器。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-161">Install the Microsoft User Experience Virtualization (UE-V) 2.0 Generator on a computer that you can then use to create a custom settings location template.</span></span> <span data-ttu-id="6ed2b-162">此计算机应为要生成的自定义设置位置模板安装应用程序。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-162">This computer should have the applications installed for which custom settings location templates are to be generated.</span></span>

**<span data-ttu-id="6ed2b-163">安装 UE-V 发生器</span><span class="sxs-lookup"><span data-stu-id="6ed2b-163">To install the UE-V Generator</span></span>**

1.  <span data-ttu-id="6ed2b-164">作为具有本地管理员权限的用户，找到与 UE-V 软件一起提供的 UE-V 发生器安装文件**ToolSetup.exe** 。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-164">As a user with local administrator rights, locate the UE-V Generator installation file **ToolSetup.exe** provided with the UE-V software.</span></span> <span data-ttu-id="6ed2b-165">或者，如果你知道计算机体系结构，则可以运行相应的 Windows Installer （.msi）文件， **ToolsSetupx64.msi**或**ToolsSetupx86.msi**。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-165">Or, if you know the computer architecture, you can run the appropriate Windows Installer (.msi) file, **ToolsSetupx64.msi** or **ToolsSetupx86.msi**.</span></span>

2.  <span data-ttu-id="6ed2b-166">双击安装文件。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-166">Double-click the installation file.</span></span> <span data-ttu-id="6ed2b-167">此时将打开 "用户体验虚拟化生成器设置向导"。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-167">The User Experience Virtualization Generator Setup wizard opens.</span></span> <span data-ttu-id="6ed2b-168">单击**下一步**以继续。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-168">Click **Next** to continue.</span></span>

3.  <span data-ttu-id="6ed2b-169">接受 Microsoft 软件许可条款，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-169">Accept the Microsoft Software License Terms, and then click **Next**.</span></span>

4.  <span data-ttu-id="6ed2b-170">单击 "Microsoft 更新" 和 "客户体验改善计划" 的选项。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-170">Click the options for Microsoft Updates and the Customer Experience Improvement Program.</span></span>

5.  <span data-ttu-id="6ed2b-171">选择要在其中安装 UE-V 发生器的目标文件夹，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-171">Select the destination folder in which to install the UE-V Generator, and then click **Next**.</span></span>

6.  <span data-ttu-id="6ed2b-172">单击 "**安装**" 以开始安装。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-172">Click **Install** to begin the installation.</span></span>

    <span data-ttu-id="6ed2b-173">**注意** 在安装应用程序之前显示**用户帐户控制**提示。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-173">**Note** A prompt for **User Account Control** appears before the application is installed.</span></span> <span data-ttu-id="6ed2b-174">需要具有权限才能安装 UE-V 生成器。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-174">Permission is required to install the UE-V Generator.</span></span>

     

7.  <span data-ttu-id="6ed2b-175">安装完成后，单击 "**完成**" 关闭向导。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-175">Click **Finish** to close the wizard after the installation is finished.</span></span> <span data-ttu-id="6ed2b-176">必须重新启动计算机才能运行 UE-V 发生器。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-176">You must restart your computer before you can run the UE-V Generator.</span></span>

    <span data-ttu-id="6ed2b-177">若要验证安装是否成功，请依次单击 "**开始**"、"**所有程序**"、" **microsoft 用户体验虚拟化**"，然后单击 " **microsoft 用户体验虚拟化生成器**"。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-177">To verify that the installation was successful, click **Start**, click **All Programs**, click **Microsoft User Experience Virtualization**, and then click **Microsoft User Experience Virtualization Generator**.</span></span>

    <span data-ttu-id="6ed2b-178">**注意** UE-V 2 生成器仅可用于为 UE-V 2 代理创建模板。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-178">**Note** The UE-V 2 Generator can only be used to create templates for UE-V 2 Agents.</span></span> <span data-ttu-id="6ed2b-179">在 UE-V 1.0 代理和 UE-V 2 代理的混合部署中，应继续使用 UE-V 1.0 生成器，直到升级了所有 UE-V Agent。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-179">In a mixed deployment of UE-V 1.0 Agents and UE-V 2 Agents, you should continue to use the UE-V 1.0 Generator until you have upgraded all UE-V Agents.</span></span>

     

## <a href="" id="deploycatalogue"></a><span data-ttu-id="6ed2b-180">部署设置模板目录</span><span class="sxs-lookup"><span data-stu-id="6ed2b-180">Deploy a Settings Template Catalog</span></span>


<span data-ttu-id="6ed2b-181">用户体验虚拟化设置模板目录是 UE-V 计算机上的文件夹路径或用于存储所有自定义设置位置模板的服务器消息块（SMB）网络共享。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-181">The User Experience Virtualization settings template catalog is a folder path on UE-V computers or a Server Message Block (SMB) network share that stores all the custom settings location templates.</span></span> <span data-ttu-id="6ed2b-182">UE-V Agent 中的计划任务每日检查此位置一次，并根据此文件夹中的模板更新其同步行为。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-182">A scheduled task in the UE-V Agent checks this location one time each day and updates its synchronization behavior, based on the templates in this folder.</span></span>

<span data-ttu-id="6ed2b-183">UE-V Agent 将在最后一次检查文件夹并注销删除的模板后，注册在此文件夹中添加或更新的模板。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-183">The UE-V Agent registers templates that were added or updated in this folder after the last time that the folder was checked and unregisters templates that are removed.</span></span> <span data-ttu-id="6ed2b-184">默认情况下，在 3:30 A.M. 每天注册和注销模板一次。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-184">By default, templates are registered and unregistered one time per day at 3:30 A.M.</span></span> <span data-ttu-id="6ed2b-185">任务计划程序和系统启动时的本地时间。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-185">local time by the Task Scheduler and at system startup.</span></span> <span data-ttu-id="6ed2b-186">若要自定义此计划任务的频率，请参阅[更改 ue-v 2. x 计划任务的频率](changing-the-frequency-of-ue-v-2x-scheduled-tasks-both-uevv2.md)。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-186">To customize the frequency of this scheduled task, see [Changing the Frequency of UE-V 2.x Scheduled Tasks](changing-the-frequency-of-ue-v-2x-scheduled-tasks-both-uevv2.md).</span></span>

<span data-ttu-id="6ed2b-187">你可以使用安装命令行选项、组策略、WMI 或 Windows PowerShell 配置设置模板目录路径。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-187">You can configure the settings template catalog path by using the installation command-line options, Group Policy, WMI, or Windows PowerShell.</span></span> <span data-ttu-id="6ed2b-188">存储在设置模板目录路径上的模板由计划任务自动注册和注销。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-188">Templates that are stored at the settings template catalog path are automatically registered and unregistered by a scheduled task.</span></span>

**<span data-ttu-id="6ed2b-189">配置用于 UE-V 2 的设置模板目录</span><span class="sxs-lookup"><span data-stu-id="6ed2b-189">To configure the settings template catalog for UE-V 2.x</span></span>**

1.  <span data-ttu-id="6ed2b-190">在存储 UE-V 设置模板目录的计算机上创建一个新文件夹。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-190">Create a new folder on the computer that stores the UE-V settings template catalog.</span></span>

2.  <span data-ttu-id="6ed2b-191">为设置模板目录文件夹设置以下共享级别（SMB）权限。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-191">Set the following share-level (SMB) permissions for the settings template catalog folder.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><strong><span data-ttu-id="6ed2b-192">用户帐户</span><span class="sxs-lookup"><span data-stu-id="6ed2b-192">User account</span></span></strong></th>
    <th align="left"><strong><span data-ttu-id="6ed2b-193">推荐的权限</span><span class="sxs-lookup"><span data-stu-id="6ed2b-193">Recommended permissions</span></span></strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="6ed2b-194">所有人</span><span class="sxs-lookup"><span data-stu-id="6ed2b-194">Everyone</span></span></p></td>
    <td align="left"><p><span data-ttu-id="6ed2b-195">无权限</span><span class="sxs-lookup"><span data-stu-id="6ed2b-195">No Permissions</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="6ed2b-196">域计算机</span><span class="sxs-lookup"><span data-stu-id="6ed2b-196">Domain Computers</span></span></p></td>
    <td align="left"><p><span data-ttu-id="6ed2b-197">读取权限级别</span><span class="sxs-lookup"><span data-stu-id="6ed2b-197">Read Permission Levels</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="6ed2b-198">管理员</span><span class="sxs-lookup"><span data-stu-id="6ed2b-198">Administrators</span></span></p></td>
    <td align="left"><p><span data-ttu-id="6ed2b-199">读/写权限级别</span><span class="sxs-lookup"><span data-stu-id="6ed2b-199">Read/Write Permission Levels</span></span></p></td>
    </tr>
    </tbody>
    </table>

     

3.  <span data-ttu-id="6ed2b-200">为设置模板目录文件夹设置以下 NTFS 文件系统权限。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-200">Set the following NTFS file system permissions for the settings template catalog folder.</span></span>

    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="6ed2b-201">用户帐户</span><span class="sxs-lookup"><span data-stu-id="6ed2b-201">User account</span></span></th>
    <th align="left"><span data-ttu-id="6ed2b-202">推荐的权限</span><span class="sxs-lookup"><span data-stu-id="6ed2b-202">Recommended permissions</span></span></th>
    <th align="left"><span data-ttu-id="6ed2b-203">应用于</span><span class="sxs-lookup"><span data-stu-id="6ed2b-203">Apply to</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="6ed2b-204">创建者/所有者</span><span class="sxs-lookup"><span data-stu-id="6ed2b-204">Creator/Owner</span></span></p></td>
    <td align="left"><p><span data-ttu-id="6ed2b-205">完全控制</span><span class="sxs-lookup"><span data-stu-id="6ed2b-205">Full Control</span></span></p></td>
    <td align="left"><p><span data-ttu-id="6ed2b-206">此文件夹、子文件夹和文件</span><span class="sxs-lookup"><span data-stu-id="6ed2b-206">This Folder, Subfolders and Files</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="6ed2b-207">域计算机</span><span class="sxs-lookup"><span data-stu-id="6ed2b-207">Domain Computers</span></span></p></td>
    <td align="left"><p><span data-ttu-id="6ed2b-208">列出文件夹内容和阅读</span><span class="sxs-lookup"><span data-stu-id="6ed2b-208">List Folder Contents and Read</span></span></p></td>
    <td align="left"><p><span data-ttu-id="6ed2b-209">此文件夹、子文件夹和文件</span><span class="sxs-lookup"><span data-stu-id="6ed2b-209">This Folder, Subfolders and Files</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="6ed2b-210">所有人</span><span class="sxs-lookup"><span data-stu-id="6ed2b-210">Everyone</span></span></p></td>
    <td align="left"><p><span data-ttu-id="6ed2b-211">无权限</span><span class="sxs-lookup"><span data-stu-id="6ed2b-211">No Permissions</span></span></p></td>
    <td align="left"><p><span data-ttu-id="6ed2b-212">无权限</span><span class="sxs-lookup"><span data-stu-id="6ed2b-212">No Permissions</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="6ed2b-213">管理员</span><span class="sxs-lookup"><span data-stu-id="6ed2b-213">Administrators</span></span></p></td>
    <td align="left"><p><span data-ttu-id="6ed2b-214">完全控制</span><span class="sxs-lookup"><span data-stu-id="6ed2b-214">Full Control</span></span></p></td>
    <td align="left"><p><span data-ttu-id="6ed2b-215">此文件夹、子文件夹和文件</span><span class="sxs-lookup"><span data-stu-id="6ed2b-215">This Folder, Subfolders and Files</span></span></p></td>
    </tr>
    </tbody>
    </table>

     

4.  <span data-ttu-id="6ed2b-216">单击 **"确定"** 关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-216">Click **OK** to close the dialog boxes.</span></span>

<span data-ttu-id="6ed2b-217">至少，网络共享必须为 "域计算机" 组授予权限。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-217">At a minimum, the network share must grant permissions for the Domain Computers group.</span></span> <span data-ttu-id="6ed2b-218">此外，将网络共享文件夹的访问权限授予管理已存储模板的管理员。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-218">In addition, grant access permissions for the network share folder to administrators who are to manage the stored templates.</span></span>

## <a href="" id="createcustomtemplates"></a><span data-ttu-id="6ed2b-219">创建自定义设置位置模板</span><span class="sxs-lookup"><span data-stu-id="6ed2b-219">Create Custom Settings Location Templates</span></span>


<span data-ttu-id="6ed2b-220">使用 UE-V 生成器为业务线应用程序或其他自定义应用程序创建设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-220">Use the UE-V Generator to create settings location templates for line-of-business applications or other custom applications.</span></span> <span data-ttu-id="6ed2b-221">创建应用程序的模板后，可以将其部署到计算机，以便为该应用程序同步设置。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-221">After the template for an application is created, you can deploy it to computers so that settings are synchronized for that application.</span></span>

**<span data-ttu-id="6ed2b-222">使用 UE-V 生成器创建 UE-V 设置位置模板</span><span class="sxs-lookup"><span data-stu-id="6ed2b-222">To create a UE-V settings location template with the UE-V Generator</span></span>**

1.  <span data-ttu-id="6ed2b-223">依次单击 "**开始**"、"**所有程序**"、" **microsoft 用户体验虚拟化**"，然后单击 " **microsoft 用户体验虚拟化生成器**"。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-223">Click **Start**, click **All Programs**, click **Microsoft User Experience Virtualization**, and then click **Microsoft User Experience Virtualization Generator**.</span></span>

2.  <span data-ttu-id="6ed2b-224">单击 "**创建设置位置模板**"。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-224">Click **Create a settings location template**.</span></span>

3.  <span data-ttu-id="6ed2b-225">指定应用程序。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-225">Specify the application.</span></span> <span data-ttu-id="6ed2b-226">通过浏览找到要为其创建设置位置模板的应用程序（.exe）或应用程序快捷方式（.lnk）的文件路径。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-226">Browse to the file path of the application (.exe) or the application shortcut (.lnk) for which you want to create a settings location template.</span></span> <span data-ttu-id="6ed2b-227">指定命令行参数（如果有）和工作目录（如果有）。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-227">Specify the command-line arguments, if any, and working directory, if any.</span></span> <span data-ttu-id="6ed2b-228">单击**下一步**以继续。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-228">Click **Next** to continue.</span></span>

    <span data-ttu-id="6ed2b-229">**注意** 在应用程序启动之前，系统将显示 "**用户帐户控制**" 提示。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-229">**Note** Before the application is started, the system displays a prompt for **User Account Control**.</span></span> <span data-ttu-id="6ed2b-230">需要权限来监视应用程序用于存储设置的注册表和文件位置。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-230">Permission is required to monitor the registry and file locations that the application uses to store settings.</span></span>

     

4.  <span data-ttu-id="6ed2b-231">应用程序启动后，关闭该应用程序。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-231">After the application starts, close the application.</span></span> <span data-ttu-id="6ed2b-232">UE-V 生成器记录应用程序存储其设置的位置。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-232">The UE-V Generator records the locations where the application stores its settings.</span></span>

5.  <span data-ttu-id="6ed2b-233">过程完成后，单击 "**下一步**" 以继续。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-233">After the process is completed, click **Next** to continue.</span></span>

6.  <span data-ttu-id="6ed2b-234">查看并选择相应注册表设置位置旁边的复选框，并选择要为此应用程序同步的设置文件位置。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-234">Review and select the check boxes that are next to the appropriate registry settings locations and settings file locations to synchronize for this application.</span></span> <span data-ttu-id="6ed2b-235">该列表包含设置位置的以下两个类别：</span><span class="sxs-lookup"><span data-stu-id="6ed2b-235">The list includes the following two categories for settings locations:</span></span>

    -   <span data-ttu-id="6ed2b-236">**标准**：存储在注册表中的应用程序设置，这些设置存储在 HKEY \ _CURRENT \ _USER 键或在 \\**用户**\\ [用户名 \] \ **AppData**漫游] 下的文件文件夹中  \\  **Roaming**。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-236">**Standard**: Application settings that are stored in the registry under the HKEY\_CURRENT\_USER keys or in the file folders under \\ **Users** \\ \[User name\] \\ **AppData** \\ **Roaming**.</span></span> <span data-ttu-id="6ed2b-237">UE-V 生成器默认包括这些设置。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-237">The UE-V Generator includes these settings by default.</span></span>

    -   <span data-ttu-id="6ed2b-238">**非标准**：在 "设置数据存储" 的最佳做法中指定存储在位置外部的应用程序设置（可选）。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-238">**Nonstandard**: Application settings that are stored outside the locations are specified in the best practices for settings data storage (optional).</span></span> <span data-ttu-id="6ed2b-239">其中包括 " **Users** \\ [用户名 \] \" \ " **AppData**  \\  **本地**的文件和文件夹"。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-239">These include files and folders under **Users** \\ \[User name\] \\ **AppData** \\ **Local**.</span></span> <span data-ttu-id="6ed2b-240">查看这些位置以确定是否将它们包含在 "设置位置" 模板中。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-240">Review these locations to determine whether to include them in the settings location template.</span></span> <span data-ttu-id="6ed2b-241">选中 "位置" 复选框以包括它们。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-241">Select the locations check boxes to include them.</span></span>

    <span data-ttu-id="6ed2b-242">单击**下一步**以继续。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-242">Click **Next** to continue.</span></span>

7.  <span data-ttu-id="6ed2b-243">查看和编辑设置位置模板的任何**属性**、**注册表**位置和**文件**位置。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-243">Review and edit any **Properties**, **Registry** locations, and **Files** locations for the settings location template.</span></span>

    -   <span data-ttu-id="6ed2b-244">在 "**属性**" 选项卡上编辑以下属性：</span><span class="sxs-lookup"><span data-stu-id="6ed2b-244">Edit the following properties on the **Properties** tab:</span></span>

        -   <span data-ttu-id="6ed2b-245">**应用程序名称**：在程序文件属性的描述中写入的应用程序名称。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-245">**Application Name**: The application name that is written in the description of the program files properties.</span></span>

        -   <span data-ttu-id="6ed2b-246">**程序名称**：从程序文件属性中获取的程序的名称。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-246">**Program name**: The name of the program that is taken from the program file properties.</span></span> <span data-ttu-id="6ed2b-247">此名称通常具有 .exe 文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-247">This name usually has the .exe file name extension.</span></span>

        -   <span data-ttu-id="6ed2b-248">**产品版本**：应用程序的 .exe 文件的产品版本号。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-248">**Product version**: The product version number of the .exe file of the application.</span></span> <span data-ttu-id="6ed2b-249">此属性与**文件版本**结合使用，可帮助确定设置位置模板面向的应用程序。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-249">This property, in conjunction with the **File version**, helps determine which applications are targeted by the settings location template.</span></span> <span data-ttu-id="6ed2b-250">此属性接受主版本号。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-250">This property accepts a major version number.</span></span> <span data-ttu-id="6ed2b-251">如果此属性为空，则设置位置模板适用于产品的所有版本。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-251">If this property is empty, the settings location template applies to all versions of the product.</span></span>

        -   <span data-ttu-id="6ed2b-252">**文件版本**：应用程序的 .exe 文件的文件版本号。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-252">**File version**: The file version number of the .exe file of the application.</span></span> <span data-ttu-id="6ed2b-253">此属性与**产品版本**结合使用，可帮助确定设置位置模板面向的应用程序。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-253">This property, in conjunction with the **Product version**, helps determine which applications are targeted by the settings location template.</span></span> <span data-ttu-id="6ed2b-254">此属性接受主版本号。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-254">This property accepts a major version number.</span></span> <span data-ttu-id="6ed2b-255">如果此属性为空，则设置位置模板将应用于该程序的所有版本。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-255">If this property is empty, the settings location template applies to all versions of the program.</span></span>

        -   <span data-ttu-id="6ed2b-256">**模板作者名称**（可选）：设置位置模板作者的名称。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-256">**Template author name** (optional): The name of the settings location template author.</span></span>

        -   <span data-ttu-id="6ed2b-257">**模板作者电子邮件**（可选）：设置位置模板作者的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-257">**Template author email** (optional): The email address of the settings location template author.</span></span>

    -   <span data-ttu-id="6ed2b-258">"**注册表**" 选项卡列出了 "设置位置" 模板中包含的注册表位置的**密钥**和**范围**。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-258">The **Registry** tab lists the **Key** and **Scope** of the registry locations that are included in the settings location template.</span></span> <span data-ttu-id="6ed2b-259">使用 "**任务**" 下拉菜单编辑注册表位置。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-259">Edit the registry locations by using the **Tasks** drop-down menu.</span></span> <span data-ttu-id="6ed2b-260">任务使你能够添加新密钥、编辑现有密钥的名称或作用域、删除密钥以及浏览注册表项所在的注册表。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-260">Tasks enable you to add new keys, edit the name or scope of existing keys, delete keys, and browse the registry where the keys are located.</span></span> <span data-ttu-id="6ed2b-261">使用 "**所有设置**" 范围将所有注册表设置包含在指定的键下。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-261">Use the **All Settings** scope to include all the registry settings under the specified key.</span></span> <span data-ttu-id="6ed2b-262">使用 "**所有设置" 和 "子项**"，将所有注册表设置包含在指定的项、子项和子项设置下。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-262">Use the **All Settings and Subkeys** to include all the registry settings under the specified key, subkeys, and subkey settings.</span></span>

    -   <span data-ttu-id="6ed2b-263">"**文件**" 选项卡列出了 "设置位置" 模板中包含的文件位置的文件路径和文件掩码。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-263">The **Files** tab lists the file path and file mask of the file locations that are included in the settings location template.</span></span> <span data-ttu-id="6ed2b-264">通过使用 "**任务**" 下拉菜单来编辑文件位置。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-264">Edit the file locations by use of the **Tasks** drop-down menu.</span></span> <span data-ttu-id="6ed2b-265">文件位置的任务使你能够添加新文件或文件夹位置、编辑现有文件或文件夹的范围、删除文件或文件夹，以及在 Windows 资源管理器中打开所选位置。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-265">Tasks for file locations enable you to add new files or folder locations, edit the scope of existing files or folders, delete files or folders, and open the selected location in Windows Explorer.</span></span> <span data-ttu-id="6ed2b-266">将文件掩码保留为空，以包括指定文件夹中的所有文件。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-266">Leave the file mask empty to include all files in the specified folder.</span></span>

8.  <span data-ttu-id="6ed2b-267">单击 "**创建**"，然后单击 "**保存**" 以在计算机上保存设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-267">Click **Create**, and then click **Save** to save the settings location template on the computer.</span></span>

9.  <span data-ttu-id="6ed2b-268">单击 "**关闭**" 以关闭 "设置模板" 向导。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-268">Click **Close** to close the Settings Template Wizard.</span></span> <span data-ttu-id="6ed2b-269">退出 UE-V 发生器应用程序。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-269">Exit the UE-V Generator application.</span></span>

    <span data-ttu-id="6ed2b-270">为应用程序创建设置位置模板后，应测试该模板。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-270">After you have created the settings location template for an application, you should test the template.</span></span> <span data-ttu-id="6ed2b-271">在实验室环境中部署模板，然后再将其放入企业中的生产环境中。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-271">Deploy the template in a lab environment before you put it into production in the enterprise.</span></span>

<span data-ttu-id="6ed2b-272">UE-V 详细信息的[应用程序模板参考](https://technet.microsoft.com/library/dn763947.aspx)ue-v 设置位置模板的 XML 结构，并提供编辑这些文件的指南。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-272">[Application Template Schema Reference for UE-V](https://technet.microsoft.com/library/dn763947.aspx) details the XML structure of the UE-V settings location template and provides guidance for editing these files.</span></span>

## <a href="" id="deploycustomtemplates"></a><span data-ttu-id="6ed2b-273">部署自定义设置位置模板</span><span class="sxs-lookup"><span data-stu-id="6ed2b-273">Deploy the Custom Settings Location Templates</span></span>


<span data-ttu-id="6ed2b-274">使用 UE-V 生成器创建设置位置模板后，应对其进行测试以确保正确同步应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-274">After you create a settings location template with the UE-V Generator, you should test it to ensure that the application settings are synchronized correctly.</span></span> <span data-ttu-id="6ed2b-275">然后，您可以安全地将设置位置模板部署到企业中的计算机。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-275">You can then safely deploy the settings location template to computers in the enterprise.</span></span>

<span data-ttu-id="6ed2b-276">可以使用以下任一方法部署设置位置模板：</span><span class="sxs-lookup"><span data-stu-id="6ed2b-276">Settings location templates can be deployed by using one of these methods:</span></span>

-   <span data-ttu-id="6ed2b-277">企业软件分发（ESD）系统，如 System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="6ed2b-277">An enterprise software distribution (ESD) system such as System Center Configuration Manager</span></span>

-   <span data-ttu-id="6ed2b-278">组策略首选项</span><span class="sxs-lookup"><span data-stu-id="6ed2b-278">Group Policy preferences</span></span>

-   <span data-ttu-id="6ed2b-279">UE-V 设置模板目录</span><span class="sxs-lookup"><span data-stu-id="6ed2b-279">A UE-V settings template catalog</span></span>

<span data-ttu-id="6ed2b-280">使用 ESD 系统或组策略对象部署的模板必须通过 UE-V Windows Management Instrumentation （WMI）或 Windows PowerShell 注册。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-280">Templates that are deployed by using an ESD system or Group Policy Objects must be registered through UE-V Windows Management Instrumentation (WMI) or Windows PowerShell.</span></span> <span data-ttu-id="6ed2b-281">存储在设置模板目录位置的模板由 UE-V Agent 自动注册。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-281">Templates that are stored in the settings template catalog location are automatically registered by the UE-V Agent.</span></span>

**<span data-ttu-id="6ed2b-282">使用设置模板目录路径部署 UE-V 设置位置模板</span><span class="sxs-lookup"><span data-stu-id="6ed2b-282">To use the settings template catalog path to deploy UE-V settings location templates</span></span>**

1.  <span data-ttu-id="6ed2b-283">浏览到定义为设置模板目录的网络共享文件夹。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-283">Browse to the network share folder that is defined as the settings template catalog.</span></span>

2.  <span data-ttu-id="6ed2b-284">在设置模板目录中添加、删除或更新设置位置模板，以反映你希望用于 UE-V 计算机的 UE-V Agent 模板配置。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-284">Add, remove, or update settings location templates in the settings template catalog to reflect the UE-V Agent template configuration that you want for UE-V computers.</span></span>

    <span data-ttu-id="6ed2b-285">**注意** 计算机上的模板每天更新。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-285">**Note** Templates on computers are updated daily.</span></span> <span data-ttu-id="6ed2b-286">更新基于对设置模板目录所做的更改。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-286">The update is based on changes to the settings template catalog.</span></span>

     

3.  <span data-ttu-id="6ed2b-287">若要在运行 UE-V Agent 的计算机上手动更新模板，请打开提升的命令提示符，并浏览到 **% 程序 Files%\\Microsoft 用户体验虚拟化 \\ 代理 \ &lt; x86 或 x64 &gt; **，然后运行**ApplySettingsTemplateCatalog.exe**。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-287">To manually update templates on a computer that runs the UE-V Agent, open an elevated command prompt, and browse to **%Program Files%\\Microsoft User Experience Virtualization \\ Agent \\ &lt;x86 or x64 &gt;**, and then run **ApplySettingsTemplateCatalog.exe**.</span></span>

    <span data-ttu-id="6ed2b-288">**注意** 此程序将在计算机启动期间和每天3:30 的中自动运行。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-288">**Note** This program runs automatically during computer startup and daily at 3:30 A. M.</span></span> <span data-ttu-id="6ed2b-289">收集最近添加到目录中的任何新模板。</span><span class="sxs-lookup"><span data-stu-id="6ed2b-289">to gather any new templates that were recently added to the catalog.</span></span>

     






## <span data-ttu-id="6ed2b-290">相关主题</span><span class="sxs-lookup"><span data-stu-id="6ed2b-290">Related topics</span></span>


[<span data-ttu-id="6ed2b-291">准备 UE-V 2. x 部署</span><span class="sxs-lookup"><span data-stu-id="6ed2b-291">Prepare a UE-V 2.x Deployment</span></span>](prepare-a-ue-v-2x-deployment-new-uevv2.md)

[<span data-ttu-id="6ed2b-292">为 UE-V 2.x 部署所需功能</span><span class="sxs-lookup"><span data-stu-id="6ed2b-292">Deploy Required Features for UE-V 2.x</span></span>](deploy-required-features-for-ue-v-2x-new-uevv2.md)

 

 





