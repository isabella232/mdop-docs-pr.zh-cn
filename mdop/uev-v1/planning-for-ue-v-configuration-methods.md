---
title: 规划 UE-V 配置方法
description: 规划 UE-V 配置方法
author: dansimp
ms.assetid: 57bce7ab-1be5-434b-9ee5-c96026bbe010
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4894644d72392ae984d0de290bf634e137d5b85e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804099"
---
# <span data-ttu-id="93b05-103">规划 UE-V 配置方法</span><span class="sxs-lookup"><span data-stu-id="93b05-103">Planning for UE-V Configuration Methods</span></span>


<span data-ttu-id="93b05-104">Microsoft 用户体验虚拟化（UE-V）配置确定设置在整个企业中的同步方式。</span><span class="sxs-lookup"><span data-stu-id="93b05-104">Microsoft User Experience Virtualization (UE-V) configurations determine how settings are synchronized throughout the enterprise.</span></span> <span data-ttu-id="93b05-105">本主题介绍如何创建 UE-V 配置，以帮助你制定最符合你的业务需求的配置计划。</span><span class="sxs-lookup"><span data-stu-id="93b05-105">This topic describes how UE-V configurations are created to help you formulate a configuration plan that best meets your business requirements.</span></span>

## <span data-ttu-id="93b05-106">UE-V 的配置方法</span><span class="sxs-lookup"><span data-stu-id="93b05-106">Configuration methods for UE-V</span></span>


<span data-ttu-id="93b05-107">你可以在代理安装之前、期间或之后配置 UE-V，具体取决于你使用的配置方法。</span><span class="sxs-lookup"><span data-stu-id="93b05-107">You can configure UE-V before, during, or after agent installation, depending on the configuration method that you use.</span></span>

<span data-ttu-id="93b05-108">**组策略：** 现有组策略基础结构可用于在 ue-v agent 部署之前或之后配置 ue-v。</span><span class="sxs-lookup"><span data-stu-id="93b05-108">**Group Policy:** existing Group Policy infrastructure can be used to configure UE-V before or after UE-V Agent deployment.</span></span> <span data-ttu-id="93b05-109">UE-V ADMX 模板支持通用 UE-V Agent 配置选项的集中管理，其中包括用于配置 UE-V 同步的设置。</span><span class="sxs-lookup"><span data-stu-id="93b05-109">The UE-V ADMX template enables the central management of common UE-V Agent configuration options, and it includes settings to configure UE-V synchronization.</span></span> <span data-ttu-id="93b05-110">使用组策略的网络环境可以预配置 UE-V，以便部署代理。</span><span class="sxs-lookup"><span data-stu-id="93b05-110">Network environments that use Group Policy can preconfigure UE-V in anticipation of agent deployment.</span></span>

[<span data-ttu-id="93b05-111">使用组策略对象配置 UE-V</span><span class="sxs-lookup"><span data-stu-id="93b05-111">Configuring UE-V with Group Policy Objects</span></span>](configuring-ue-v-with-group-policy-objects.md)

[<span data-ttu-id="93b05-112">安装 UE-V 组策略 ADMX 模板</span><span class="sxs-lookup"><span data-stu-id="93b05-112">Installing the UE-V Group Policy ADMX Templates</span></span>](installing-the-ue-v-group-policy-admx-templates.md)

<span data-ttu-id="93b05-113">**命令行或批处理脚本安装：** 与 ue-v Agent 的部署一起使用的参数允许配置许多 ue-v 设置。</span><span class="sxs-lookup"><span data-stu-id="93b05-113">**Command-line or Batch Script Installation:** parameters that are used with the deployment of the UE-V Agent allow the configuration of many UE-V settings.</span></span> <span data-ttu-id="93b05-114">电子软件分发系统（如 System Center Configuration Manager）使用这些参数在部署和安装 UE-V Agent 软件时配置其客户端。</span><span class="sxs-lookup"><span data-stu-id="93b05-114">Electronic software distribution systems, such as System Center Configuration Manager, use these parameters to configure their clients when deploying and installing the UE-V Agent software.</span></span> <span data-ttu-id="93b05-115">有关安装参数和示例安装脚本的列表，请参阅[部署 Ue-v Agent](deploying-the-ue-v-agent.md)。</span><span class="sxs-lookup"><span data-stu-id="93b05-115">For a list of installation parameters and sample installation scripts, see [Deploying the UE-V Agent](deploying-the-ue-v-agent.md).</span></span>

<span data-ttu-id="93b05-116">**PowerShell 和 wmi：** 在安装 ue-v Agent 后，使用 POWERSHELL 或 wmi 的脚本化命令可用于修改配置。</span><span class="sxs-lookup"><span data-stu-id="93b05-116">**PowerShell and WMI:** scripted commands using PowerShell or WMI can be used to modify configurations after the UE-V Agent has been installed.</span></span> <span data-ttu-id="93b05-117">有关 PowerShell 和 WMI 命令的列表，请参阅[使用 powershell 和 Wmi 管理 ue-v 1.0 代理和程序包](managing-the-ue-v-10-agent-and-packages-with-powershell-and-wmi.md)。</span><span class="sxs-lookup"><span data-stu-id="93b05-117">For a list of PowerShell and WMI commands, see [Managing the UE-V 1.0 Agent and Packages with PowerShell and WMI](managing-the-ue-v-10-agent-and-packages-with-powershell-and-wmi.md).</span></span>

<span data-ttu-id="93b05-118">**编辑注册表设置：** UE-V 设置存储在注册表中，并且可以通过可修改注册表设置的任何工具（如 RegEdit）进行修改。</span><span class="sxs-lookup"><span data-stu-id="93b05-118">**Edit Registry Settings:** UE-V settings are stored in the registry and can be modified by using any tool that can modify registry settings, such as RegEdit.</span></span>

<span data-ttu-id="93b05-119">**注意** 注册表修改可能导致数据丢失或计算机变得不响应。</span><span class="sxs-lookup"><span data-stu-id="93b05-119">**Note** Registry modification can result in data loss or the computer becoming unresponsive.</span></span> <span data-ttu-id="93b05-120">我们建议你使用其他配置方法。</span><span class="sxs-lookup"><span data-stu-id="93b05-120">We recommend that you use other configuration methods.</span></span>

 

### <span data-ttu-id="93b05-121">UE-V 配置设置</span><span class="sxs-lookup"><span data-stu-id="93b05-121">UE-V configuration settings</span></span>

<span data-ttu-id="93b05-122">以下是 UE-V 配置设置的示例：</span><span class="sxs-lookup"><span data-stu-id="93b05-122">The following are examples of UE-V configuration settings:</span></span>

-   <span data-ttu-id="93b05-123">**设置存储路径：** 指定用于存储 ue-v 设置的文件共享位置。</span><span class="sxs-lookup"><span data-stu-id="93b05-123">**Setting Storage Path:** specifies the location of the file share that stores the UE-V settings.</span></span>

-   <span data-ttu-id="93b05-124">**设置模板目录路径：** 指定通用命名约定（UNC）路径，该路径定义为新设置位置模板选中的位置。</span><span class="sxs-lookup"><span data-stu-id="93b05-124">**Settings Template Catalog Path:** specifies the Universal Naming Convention (UNC) path that defines the location that was checked for new settings location templates.</span></span>

-   <span data-ttu-id="93b05-125">**注册 Microsoft 模板：** 指定在安装期间是否注册默认 Microsoft 模板。</span><span class="sxs-lookup"><span data-stu-id="93b05-125">**Register Microsoft Templates:** specifies whether the default Microsoft templates should be registered during installation.</span></span>

-   <span data-ttu-id="93b05-126">**同步方法：** 指定是否将 Windows 脱机文件功能用于脱机支持。</span><span class="sxs-lookup"><span data-stu-id="93b05-126">**Synchronization Method:** specifies whether the Windows Offline Files feature is used for offline support.</span></span>

-   <span data-ttu-id="93b05-127">**同步超时：** 指定从设置存储位置检索用户设置时，计算机在超时之前等待的毫秒数。</span><span class="sxs-lookup"><span data-stu-id="93b05-127">**Synchronization Timeout:** specifies the number of milliseconds that the computer waits before timeout when retrieving the user settings from the settings storage location.</span></span>

-   <span data-ttu-id="93b05-128">**启用同步：** 指定是启用还是禁用 ue-v 设置同步。</span><span class="sxs-lookup"><span data-stu-id="93b05-128">**Synchronization Enable:** specifies whether the UE-V settings synchronization is enabled or disabled.</span></span>

-   <span data-ttu-id="93b05-129">**程序包最大大小：** 指定 ue-v Agent 报告警告的设置包文件阈值大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="93b05-129">**Maximum Package Size:** specifies a settings package file threshold size in bytes at which the UE-V Agent reports a warning.</span></span>

## <span data-ttu-id="93b05-130">相关主题</span><span class="sxs-lookup"><span data-stu-id="93b05-130">Related topics</span></span>


[<span data-ttu-id="93b05-131">规划 UE-V 1.0</span><span class="sxs-lookup"><span data-stu-id="93b05-131">Planning for UE-V 1.0</span></span>](planning-for-ue-v-10.md)

[<span data-ttu-id="93b05-132">规划 UE-V 配置</span><span class="sxs-lookup"><span data-stu-id="93b05-132">Planning for UE-V Configuration</span></span>](planning-for-ue-v-configuration.md)

 

 





