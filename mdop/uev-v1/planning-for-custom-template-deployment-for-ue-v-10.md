---
title: 规划 UE-V 1.0 的自定义模板部署
description: 规划 UE-V 1.0 的自定义模板部署
author: dansimp
ms.assetid: be76fc9a-31ca-4290-af11-7640dcb87d50
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 5d17f058bff452f88003ab4488daa7afa846f688
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802919"
---
# <span data-ttu-id="8d621-103">规划 UE-V 1.0 的自定义模板部署</span><span class="sxs-lookup"><span data-stu-id="8d621-103">Planning for Custom Template Deployment for UE-V 1.0</span></span>


<span data-ttu-id="8d621-104">Microsoft 用户体验虚拟化（UE-V）使用设置位置模板（XML 文件），这些模板定义由 UE-V 捕获和应用的设置。</span><span class="sxs-lookup"><span data-stu-id="8d621-104">Microsoft User Experience Virtualization (UE-V) uses settings location templates (XML files) that define the settings that are captured and applied by UE-V.</span></span> <span data-ttu-id="8d621-105">你可以使用 UE-V 生成器创建自定义设置位置模板，以便用户可以漫游除默认 UE-V 模板中包含的应用程序之外的应用程序的设置。</span><span class="sxs-lookup"><span data-stu-id="8d621-105">You can use the UE-V Generator to create custom settings location templates that let users roam the settings of applications other than those that are included in the default UE-V templates.</span></span> <span data-ttu-id="8d621-106">在测试自定义模板以确保应用程序设置在测试环境中正确漫游后，你可以将这些设置位置模板部署到企业中的计算机。</span><span class="sxs-lookup"><span data-stu-id="8d621-106">After you test the custom template to ensure that the application settings roam correctly in a test environment, you can deploy these settings location templates to computers in the enterprise.</span></span>

<span data-ttu-id="8d621-107">你可以使用现有部署基础结构（如企业软件分发（ESD））和组策略首选项部署自定义设置位置模板，或者配置 UE-V 设置模板目录。</span><span class="sxs-lookup"><span data-stu-id="8d621-107">You can deploy your custom settings location templates with an existing deployment infrastructure, such as Enterprise Software Distribution (ESD), with Group Policy preferences, or by configuring a UE-V settings template catalog.</span></span> <span data-ttu-id="8d621-108">使用 ESD 或组策略部署的模板必须使用 UE-V WMI 或 PowerShell 注册。</span><span class="sxs-lookup"><span data-stu-id="8d621-108">Templates that are deployed by using ESD or Group Policy must be registered with UE-V WMI or PowerShell.</span></span>

## <span data-ttu-id="8d621-109">设置模板目录</span><span class="sxs-lookup"><span data-stu-id="8d621-109">Settings template catalog</span></span>


<span data-ttu-id="8d621-110">用户体验虚拟化设置模板目录是 UE-V 计算机上的文件夹路径或用于存储所有自定义设置位置模板的服务器消息块（SMB）网络共享。</span><span class="sxs-lookup"><span data-stu-id="8d621-110">The User Experience Virtualization settings template catalog is a folder path on UE-V computers or a Server Message Block (SMB) network share that stores all the custom settings location templates.</span></span> <span data-ttu-id="8d621-111">UE-V agent 从该位置检索新的或更新的模板。</span><span class="sxs-lookup"><span data-stu-id="8d621-111">The UE-V agent retrieves new or updated templates from this location.</span></span> <span data-ttu-id="8d621-112">UE-V agent 每天检查此位置一次，并根据此文件夹中的模板更新其同步行为。</span><span class="sxs-lookup"><span data-stu-id="8d621-112">The UE-V agent checks this location once each day and updates its synchronization behavior based on the templates in this folder.</span></span> <span data-ttu-id="8d621-113">自上次检查文件夹后，在此文件夹中添加或更新的模板由 UE-V agent 注册。</span><span class="sxs-lookup"><span data-stu-id="8d621-113">Templates that were added or updated in this folder since the last time that the folder was checked are registered by the UE-V agent.</span></span> <span data-ttu-id="8d621-114">从该文件夹中删除的 UE-V agent deregisters 模板。</span><span class="sxs-lookup"><span data-stu-id="8d621-114">The UE-V agent deregisters templates that are removed from this folder.</span></span> <span data-ttu-id="8d621-115">默认情况下，在 3:30 A.M. 每天注册和注销模板一次。</span><span class="sxs-lookup"><span data-stu-id="8d621-115">By default, templates are registered and unregistered one time per day at 3:30 A.M.</span></span> <span data-ttu-id="8d621-116">任务计划程序的本地时间。</span><span class="sxs-lookup"><span data-stu-id="8d621-116">local time by the task scheduler.</span></span> <span data-ttu-id="8d621-117">有关 UE-V 任务的详细信息，请参阅[更改 Ue-v 计划任务的频率](changing-the-frequency-of-ue-v-scheduled-tasks.md)。</span><span class="sxs-lookup"><span data-stu-id="8d621-117">For more information about the UE-V tasks, see [Changing the Frequency of UE-V Scheduled Tasks](changing-the-frequency-of-ue-v-scheduled-tasks.md).</span></span>

<span data-ttu-id="8d621-118">你可以使用安装命令行选项、组策略、WMI 或 PowerShell 配置设置模板目录路径。</span><span class="sxs-lookup"><span data-stu-id="8d621-118">You can configure the settings template catalog path by using the install command-line options, Group Policy, WMI, or PowerShell.</span></span> <span data-ttu-id="8d621-119">存储在设置模板目录路径上的模板由计划任务自动注册和注销。</span><span class="sxs-lookup"><span data-stu-id="8d621-119">Templates that are stored at the settings template catalog path are automatically registered and unregistered by a scheduled task.</span></span> <span data-ttu-id="8d621-120">您可以根据需要自定义此计划任务。</span><span class="sxs-lookup"><span data-stu-id="8d621-120">You can customize this scheduled task as needed.</span></span>

## <span data-ttu-id="8d621-121">替换默认的 Microsoft 模板</span><span class="sxs-lookup"><span data-stu-id="8d621-121">Replace the default Microsoft templates</span></span>


<span data-ttu-id="8d621-122">UE-V agent 将为常见的 Microsoft 应用程序和 Windows 设置安装默认设置位置模板组。</span><span class="sxs-lookup"><span data-stu-id="8d621-122">The UE-V agent installs a default group of settings location templates for common Microsoft applications and Windows settings.</span></span> <span data-ttu-id="8d621-123">如果您的企业需要这些模板的自定义版本，则可以将 UE-V agent 配置为使用设置模板目录，然后应替换默认的 Microsoft 模板。</span><span class="sxs-lookup"><span data-stu-id="8d621-123">If your enterprise needs customized versions of these templates, the UE-V agent can be configured to use a settings template catalog and you should then replace the default Microsoft templates.</span></span>

<span data-ttu-id="8d621-124">在 UE-V agent 安装过程中，命令行参数 `RegisterMSTemplates` 可用于禁用默认 Microsoft 模板的注册过程。</span><span class="sxs-lookup"><span data-stu-id="8d621-124">During the installation of the UE-V agent, the command-line parameter, `RegisterMSTemplates`, can be used to disable the registration of the default Microsoft templates.</span></span> <span data-ttu-id="8d621-125">有关如何设置 UE-V 参数的详细信息，请参阅[规划 Ue-v 配置方法](planning-for-ue-v-configuration-methods.md)。</span><span class="sxs-lookup"><span data-stu-id="8d621-125">For more information about how to set the UE-V parameters, see [Planning for UE-V Configuration Methods](planning-for-ue-v-configuration-methods.md).</span></span>

<span data-ttu-id="8d621-126">使用组策略配置设置模板目录路径时，可以选择替换默认的 Microsoft 模板。</span><span class="sxs-lookup"><span data-stu-id="8d621-126">When you use Group Policy to configure the settings template catalog path, you can choose to replace the default Microsoft templates.</span></span> <span data-ttu-id="8d621-127">如果将策略设置配置为替换默认的 Microsoft 模板，则将从计算机中删除由 UE-V agent 安装的所有默认 Microsoft 模板，并且只会使用位于设置模板目录中的模板。</span><span class="sxs-lookup"><span data-stu-id="8d621-127">If you configure the policy settings to replace the default Microsoft templates, all of the default Microsoft templates that are installed by the UE-V agent will be deleted from the computer, and only the templates that are located in the settings template catalog will be used.</span></span> <span data-ttu-id="8d621-128">UE-V Agent 配置设置 `RegisterMSTemplates` 必须设置为 true 才能替代默认的 Microsoft 模板。</span><span class="sxs-lookup"><span data-stu-id="8d621-128">The UE-V Agent configuration setting `RegisterMSTemplates` must be set to true in order to override the default Microsoft template.</span></span>

<span data-ttu-id="8d621-129">**注意** 如果在启用此策略设置后禁用此策略设置，则 UE-V agent 将不会还原默认的 Microsoft 模板。</span><span class="sxs-lookup"><span data-stu-id="8d621-129">**Note** If you disable this policy setting after it has been enabled, the UE-V agent will not restore the default Microsoft templates.</span></span>

 

<span data-ttu-id="8d621-130">如果设置模板目录中存在使用与默认 Microsoft 模板相同 ID 的自定义模板，并且未将 UE-V agent 配置为替换默认的 Microsoft 模板，则将忽略目录中的 Microsoft 模板。</span><span class="sxs-lookup"><span data-stu-id="8d621-130">If there are customized templates in the settings template catalog that use the same ID as the default Microsoft templates, and the UE-V agent is not configured to replace the default Microsoft templates, the Microsoft templates in the catalog will be ignored.</span></span>

<span data-ttu-id="8d621-131">你还可以使用 UE-V PowerShell 功能替换默认模板。</span><span class="sxs-lookup"><span data-stu-id="8d621-131">You can also replace the default templates by using the UE-V PowerShell features.</span></span> <span data-ttu-id="8d621-132">若要将默认的 Microsoft 模板替换为 PowerShell，请注销所有默认的 Microsoft 模板，然后注册自定义模板。</span><span class="sxs-lookup"><span data-stu-id="8d621-132">To replace the default Microsoft Template with PowerShell, unregister all of the default Microsoft templates, and then register the customized templates.</span></span>

<span data-ttu-id="8d621-133">**注意** 即使为应用程序部署了新设置模板，旧的设置程序包仍保留在设置存储位置。</span><span class="sxs-lookup"><span data-stu-id="8d621-133">**Note** Old settings packages remain in the settings storage location even if new settings templates are deployed for an application.</span></span> <span data-ttu-id="8d621-134">这些程序包不会由代理读取，但它们都不会自动删除。</span><span class="sxs-lookup"><span data-stu-id="8d621-134">These packages are not read by the agent, but neither are they automatically deleted.</span></span>

 

## <span data-ttu-id="8d621-135">相关主题</span><span class="sxs-lookup"><span data-stu-id="8d621-135">Related topics</span></span>


[<span data-ttu-id="8d621-136">规划 UE-V 1.0</span><span class="sxs-lookup"><span data-stu-id="8d621-136">Planning for UE-V 1.0</span></span>](planning-for-ue-v-10.md)

[<span data-ttu-id="8d621-137">规划要使用 UE-V 1.0 同步的应用程序</span><span class="sxs-lookup"><span data-stu-id="8d621-137">Planning Which Applications to Synchronize with UE-V 1.0</span></span>](planning-which-applications-to-synchronize-with-ue-v-10.md)

[<span data-ttu-id="8d621-138">规划 UE-V 配置方法</span><span class="sxs-lookup"><span data-stu-id="8d621-138">Planning for UE-V Configuration Methods</span></span>](planning-for-ue-v-configuration-methods.md)

<span data-ttu-id="8d621-139">规划自定义模板部署</span><span class="sxs-lookup"><span data-stu-id="8d621-139">Planning for Custom Template Deployment</span></span>
 

 





