---
title: 管理 UE-V 2.x 的配置
description: 管理 UE-V 2.x 的配置
author: dansimp
ms.assetid: e2332eca-a9cd-4446-8f7c-d17058b03466
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 20d5d2942dbd805a4054a9431b237c821cbb70fe
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804157"
---
# <span data-ttu-id="efef4-103">管理 UE-V 2.x 的配置</span><span class="sxs-lookup"><span data-stu-id="efef4-103">Manage Configurations for UE-V 2.x</span></span>


<span data-ttu-id="efef4-104">在 Microsoft 用户体验虚拟化（UE-V）2.0、2.1 或 2.1 SP1 生命周期的过程中，你必须管理 UE-V Agent 的配置，并管理资源的存储位置（如设置程序包文件）。</span><span class="sxs-lookup"><span data-stu-id="efef4-104">In the course of the Microsoft User Experience Virtualization (UE-V) 2.0, 2.1, or 2.1 SP1 lifecycle, you have to manage the configuration of the UE-V Agent and also manage storage locations for resources such as settings package files.</span></span> <span data-ttu-id="efef4-105">您可能需要执行其他任务，例如，配置公司设置中心以定义用户与 UE-V 交互的方式。</span><span class="sxs-lookup"><span data-stu-id="efef4-105">You might have to perform other tasks, for example, configuring the Company Settings Center to define how users interact with UE-V.</span></span> <span data-ttu-id="efef4-106">以下主题提供管理这些 UE-V 资源的指南。</span><span class="sxs-lookup"><span data-stu-id="efef4-106">The following topics provide guidance for managing these UE-V resources.</span></span>

## <span data-ttu-id="efef4-107">使用组策略对象配置 UE-V 2。</span><span class="sxs-lookup"><span data-stu-id="efef4-107">Configuring UE-V 2.x by using Group Policy Objects</span></span>


<span data-ttu-id="efef4-108">你可以使用组策略对象修改定义如何在计算机上 UE-V 同步设置的设置。</span><span class="sxs-lookup"><span data-stu-id="efef4-108">You can use Group Policy Objects to modify the settings that define how UE-V synchronizes settings on computers.</span></span>

[<span data-ttu-id="efef4-109">通过组策略对象配置 UE-V 2. x</span><span class="sxs-lookup"><span data-stu-id="efef4-109">Configuring UE-V 2.x with Group Policy Objects</span></span>](configuring-ue-v-2x-with-group-policy-objects-both-uevv2.md)

## <span data-ttu-id="efef4-110">通过 System Center Configuration Manager 2012 配置 UE-V 2</span><span class="sxs-lookup"><span data-stu-id="efef4-110">Configuring UE-V 2.x with System Center Configuration Manager 2012</span></span>


<span data-ttu-id="efef4-111">你可以使用 SystemCenter2012 ConfigurationManager 管理 UE-V Agent，方法是使用 UE-V 2 配置包。</span><span class="sxs-lookup"><span data-stu-id="efef4-111">You can use SystemCenter2012 ConfigurationManager to manage the UE-V Agent by using the UE-V 2 Configuration Pack.</span></span>

[<span data-ttu-id="efef4-112">通过 System Center Configuration Manager 2012 配置 UE-V 2</span><span class="sxs-lookup"><span data-stu-id="efef4-112">Configuring UE-V 2.x with System Center Configuration Manager 2012</span></span>](configuring-ue-v-2x-with-system-center-configuration-manager-2012-both-uevv2.md)

## <span data-ttu-id="efef4-113">通过 PowerShell 和 WMI 管理 UE-V 2. x</span><span class="sxs-lookup"><span data-stu-id="efef4-113">Administering UE-V 2.x with PowerShell and WMI</span></span>


<span data-ttu-id="efef4-114">UE-V 提供 Windows PowerShell cmdlet，可帮助管理员执行各种 UE-V 任务。</span><span class="sxs-lookup"><span data-stu-id="efef4-114">UE-V provides Windows PowerShell cmdlets, which can help administrators perform various UE-V tasks.</span></span>

[<span data-ttu-id="efef4-115">管理具有 Windows PowerShell 和 WMI 的 UE-V 2。</span><span class="sxs-lookup"><span data-stu-id="efef4-115">Administering UE-V 2.x with Windows PowerShell and WMI</span></span>](administering-ue-v-2x-with-windows-powershell-and-wmi-both-uevv2.md)

## <span data-ttu-id="efef4-116">配置 UE-V 2. x 的公司设置中心</span><span class="sxs-lookup"><span data-stu-id="efef4-116">Configuring the Company Settings Center for UE-V 2.x</span></span>


<span data-ttu-id="efef4-117">你可以配置通过使用 UE-V Agent 安装的公司设置中心来定义用户与 UE-V 的交互方式。</span><span class="sxs-lookup"><span data-stu-id="efef4-117">You can configure the Company Settings Center that is installed by using the UE-V Agent to define how users interact with UE-V.</span></span>

[<span data-ttu-id="efef4-118">配置 UE-V 2. x 的公司设置中心</span><span class="sxs-lookup"><span data-stu-id="efef4-118">Configuring the Company Settings Center for UE-V 2.x</span></span>](configuring-the-company-settings-center-for-ue-v-2x-both-uevv2.md)

## <span data-ttu-id="efef4-119">UE-V 2 的配置设置示例</span><span class="sxs-lookup"><span data-stu-id="efef4-119">Examples of configuration settings for UE-V 2.x</span></span>


<span data-ttu-id="efef4-120">下面是 UE-V 配置设置的一些示例：</span><span class="sxs-lookup"><span data-stu-id="efef4-120">Here are some examples of UE-V configuration settings:</span></span>

-   <span data-ttu-id="efef4-121">**设置存储路径：** 指定存储 UE-V 设置的文件共享位置。</span><span class="sxs-lookup"><span data-stu-id="efef4-121">**Settings Storage Path:** Specifies the location of the file share that stores the UE-V settings.</span></span>

-   <span data-ttu-id="efef4-122">**设置模板目录路径：** 指定用于定义为新设置位置模板检查的位置的通用命名约定（UNC）路径。</span><span class="sxs-lookup"><span data-stu-id="efef4-122">**Settings Template Catalog Path:** Specifies the Universal Naming Convention (UNC) path that defines the location that was checked for new settings location templates.</span></span>

-   <span data-ttu-id="efef4-123">**注册 Microsoft 模板：** 指定是否应在安装期间注册默认 Microsoft 模板。</span><span class="sxs-lookup"><span data-stu-id="efef4-123">**Register Microsoft Templates:** Specifies whether the default Microsoft templates should be registered during installation.</span></span>

-   <span data-ttu-id="efef4-124">**同步方法：** 指定 UE-V 是使用同步提供程序还是 "none"。</span><span class="sxs-lookup"><span data-stu-id="efef4-124">**Synchronization Method:** Specifies whether UE-V uses the sync provider or "none".</span></span> <span data-ttu-id="efef4-125">"SyncProvider" 支持从网络断开连接的计算机。</span><span class="sxs-lookup"><span data-stu-id="efef4-125">The "SyncProvider" supports computers that are disconnected from the network.</span></span> <span data-ttu-id="efef4-126">当计算机始终连接到网络时，将应用 "无"。</span><span class="sxs-lookup"><span data-stu-id="efef4-126">"None" applies when the computer is always connected to the network.</span></span> <span data-ttu-id="efef4-127">有关同步方法的详细信息，请参阅[ue-v 2. x 的同步方法](sync-methods-for-ue-v-2x-both-uevv2.md)。</span><span class="sxs-lookup"><span data-stu-id="efef4-127">For more information about the Sync Method, see [Sync Methods for UE-V 2.x](sync-methods-for-ue-v-2x-both-uevv2.md).</span></span>

-   <span data-ttu-id="efef4-128">**同步超时：** 指定在从设置存储位置检索用户设置时，计算机超时之前等待的毫秒数。</span><span class="sxs-lookup"><span data-stu-id="efef4-128">**Synchronization Timeout:** Specifies the number of milliseconds that the computer waits before time-out when it retrieves the user settings from the settings storage location.</span></span>

-   <span data-ttu-id="efef4-129">**启用同步：** 指定是启用还是禁用 UE-V 设置同步。</span><span class="sxs-lookup"><span data-stu-id="efef4-129">**Synchronization Enable:** Specifies whether the UE-V settings synchronization is enabled or disabled.</span></span>

-   <span data-ttu-id="efef4-130">**最大程序包大小：** 指定 UE-V Agent 报告警告的设置包文件阈值大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="efef4-130">**Maximum Package Size:** Specifies a settings package file threshold size in bytes at which the UE-V Agent reports a warning.</span></span>

-   <span data-ttu-id="efef4-131">**不要同步 Windows 应用设置：** 指定 UE-V 不应同步 Windows 应用。</span><span class="sxs-lookup"><span data-stu-id="efef4-131">**Don’t Sync Windows App Settings:** Specifies that UE-V should not synchronize Windows apps.</span></span>

-   <span data-ttu-id="efef4-132">**启用/禁用首次使用通知：** 指定当 ue-v Agent 首次在用户的计算机上运行时，UE-V 是否显示一个对话框。</span><span class="sxs-lookup"><span data-stu-id="efef4-132">**Enable/Disable First Use Notification:** Specifies whether UE-V displays a dialog box the first time that the UE-V Agent runs on a user’s computer.</span></span>

-   <span data-ttu-id="efef4-133">**启用/禁用托盘图标：** 指定是否在通知区域中显示 "UE-V" 以及与之关联的任何通知。</span><span class="sxs-lookup"><span data-stu-id="efef4-133">**Enable/Disable Tray Icon:** Specifies whether UE-V displays an icon in the notification area and any notifications associated with it.</span></span> <span data-ttu-id="efef4-134">图标提供指向公司设置中心的链接。</span><span class="sxs-lookup"><span data-stu-id="efef4-134">The icon provides a link to the Company Settings Center.</span></span>

-   <span data-ttu-id="efef4-135">**自定义联系人 IT 超链接：** 在 "公司设置中心" 中定义 "**联系人 IT** " 超链接的路径、文本和说明。</span><span class="sxs-lookup"><span data-stu-id="efef4-135">**Custom Contact IT Hyperlink:** Defines the path, text, and description for the **Contact IT** hyperlink in the Company Settings Center.</span></span>






## <span data-ttu-id="efef4-136">相关主题</span><span class="sxs-lookup"><span data-stu-id="efef4-136">Related topics</span></span>


[<span data-ttu-id="efef4-137">管理 UE-V 2. x</span><span class="sxs-lookup"><span data-stu-id="efef4-137">Administering UE-V 2.x</span></span>](administering-ue-v-2x-new-uevv2.md)

[<span data-ttu-id="efef4-138">为 UE-V 2.x 部署所需功能</span><span class="sxs-lookup"><span data-stu-id="efef4-138">Deploy Required Features for UE-V 2.x</span></span>](deploy-required-features-for-ue-v-2x-new-uevv2.md)

[<span data-ttu-id="efef4-139">部署自定义应用程序的 UE-V 2。</span><span class="sxs-lookup"><span data-stu-id="efef4-139">Deploy UE-V 2.x for Custom Applications</span></span>](deploy-ue-v-2x-for-custom-applications-new-uevv2.md)

 

 





