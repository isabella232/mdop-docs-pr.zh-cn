---
title: 管理 UE-V 1.0
description: 管理 UE-V 1.0
author: dansimp
ms.assetid: c399ae8d-c839-4f84-9bfc-adacd8f89f34
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ce4dcafd1949dcedd195569dabb7540ce55a2f1a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803220"
---
# <span data-ttu-id="6f6f3-103">管理 UE-V 1.0</span><span class="sxs-lookup"><span data-stu-id="6f6f3-103">Administering UE-V 1.0</span></span>


<span data-ttu-id="6f6f3-104">部署 Microsoft 用户体验虚拟化（UE-V）后，您必须能够执行各种持续的管理任务。</span><span class="sxs-lookup"><span data-stu-id="6f6f3-104">After you have deployed Microsoft User Experience Virtualization (UE-V), you must be able to perform various ongoing administrative tasks.</span></span> <span data-ttu-id="6f6f3-105">以下部分介绍了这些安装后任务。</span><span class="sxs-lookup"><span data-stu-id="6f6f3-105">These post-installation tasks are described in the following sections.</span></span>

## <span data-ttu-id="6f6f3-106">管理 UE-V 资源</span><span class="sxs-lookup"><span data-stu-id="6f6f3-106">Managing UE-V resources</span></span>


<span data-ttu-id="6f6f3-107">在 UE-V 生命周期的过程中，你将需要管理 UE-V agent 的配置，还需要管理资源（如设置程序包）的存储位置。</span><span class="sxs-lookup"><span data-stu-id="6f6f3-107">In the course of the UE-V lifecycle, you will need to manage the configuration of the UE-V agent and also manage storage locations for resources such as settings packages.</span></span> <span data-ttu-id="6f6f3-108">你可能需要执行其他任务，例如，在安装 UE-V 之前将用户的设置还原到其原始状态，以便恢复丢失的设置。</span><span class="sxs-lookup"><span data-stu-id="6f6f3-108">You might need to perform other tasks such as to restore a user’s settings to their original state from before UE-V was installed in order to recover lost settings.</span></span> <span data-ttu-id="6f6f3-109">以下主题提供了管理 UE-V 资源的指南。</span><span class="sxs-lookup"><span data-stu-id="6f6f3-109">The following topics provide guidance for managing UE-V resources.</span></span>

### <span data-ttu-id="6f6f3-110">更改 UE-V 计划任务的频率</span><span class="sxs-lookup"><span data-stu-id="6f6f3-110">Changing the Frequency of UE-V Scheduled Tasks</span></span>

<span data-ttu-id="6f6f3-111">你可以配置计划任务，以便在 UE-V 检查设置模板目录中的新的、已更新或已删除的自定义设置位置模板时进行管理。</span><span class="sxs-lookup"><span data-stu-id="6f6f3-111">You can configure the scheduled tasks that manage when UE-V checks for new, updated, or removed custom settings location templates in the settings template catalog.</span></span>

[<span data-ttu-id="6f6f3-112">更改 UE-V 计划任务的频率</span><span class="sxs-lookup"><span data-stu-id="6f6f3-112">Changing the Frequency of UE-V Scheduled Tasks</span></span>](changing-the-frequency-of-ue-v-scheduled-tasks.md)

### <a href="" id="sharing-settings-location-templates-with-the-ue-v-template-gallery-"></a><span data-ttu-id="6f6f3-113">使用 UE-V 模板库共享设置位置模板</span><span class="sxs-lookup"><span data-stu-id="6f6f3-113">Sharing Settings Location Templates with the UE-V Template Gallery</span></span>

<span data-ttu-id="6f6f3-114">UE-V 模板库有利于共享 UE-V 设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="6f6f3-114">The UE-V template gallery facilitates the sharing of UE-V settings location templates.</span></span> <span data-ttu-id="6f6f3-115">库允许你上载你的设置位置模板以与其他人共享，并下载其他人创建的模板。</span><span class="sxs-lookup"><span data-stu-id="6f6f3-115">The gallery enables you to upload your settings location templates to share with other people and to download templates that other people have created.</span></span>

[<span data-ttu-id="6f6f3-116">使用 UE-V 模板库共享设置位置模板</span><span class="sxs-lookup"><span data-stu-id="6f6f3-116">Sharing Settings Location Templates with the UE-V Template Gallery</span></span>](sharing-settings-location-templates-with-the-ue-v-template-gallery.md)

### <span data-ttu-id="6f6f3-117">还原与 UE-V 1.0 同步的应用程序和 Windows 设置</span><span class="sxs-lookup"><span data-stu-id="6f6f3-117">Restoring application and Windows settings synchronized with UE-V 1.0</span></span>

<span data-ttu-id="6f6f3-118">UE-V 的 WMI 和 PowerShell 功能提供了还原设置程序包的功能。</span><span class="sxs-lookup"><span data-stu-id="6f6f3-118">WMI and PowerShell features of UE-V provide the ability to restore settings packages.</span></span> <span data-ttu-id="6f6f3-119">WMI 和 PowerShell 命令允许你在启动 UE-V agent 后首次启动应用程序时，将应用程序设置和 Windows 设置还原到计算机上的设置值。</span><span class="sxs-lookup"><span data-stu-id="6f6f3-119">WMI and PowerShell commands allow you to restore application settings and Windows settings to the settings values that were on the computer the first time the application was started after the UE-V agent was launched.</span></span>

[<span data-ttu-id="6f6f3-120">还原与 UE-V 1.0 同步的应用程序和 Windows 设置</span><span class="sxs-lookup"><span data-stu-id="6f6f3-120">Restoring Application and Windows Settings Synchronized with UE-V 1.0</span></span>](restoring-application-and-windows-settings-synchronized-with-ue-v-10.md)

### <span data-ttu-id="6f6f3-121">使用组策略对象配置 UE-V</span><span class="sxs-lookup"><span data-stu-id="6f6f3-121">Configuring UE-V with Group Policy Objects</span></span>

<span data-ttu-id="6f6f3-122">你可以使用组策略修改定义如何在计算机上 UE-V 同步设置的设置。</span><span class="sxs-lookup"><span data-stu-id="6f6f3-122">You can use Group Policy to modify the settings that define how UE-V synchronizes settings on computers.</span></span>

[<span data-ttu-id="6f6f3-123">使用组策略对象配置 UE-V</span><span class="sxs-lookup"><span data-stu-id="6f6f3-123">Configuring UE-V with Group Policy Objects</span></span>](configuring-ue-v-with-group-policy-objects.md)

### <span data-ttu-id="6f6f3-124">使用 PowerShell 和 WMI 管理 UE-V</span><span class="sxs-lookup"><span data-stu-id="6f6f3-124">Administering UE-V with PowerShell and WMI</span></span>

<span data-ttu-id="6f6f3-125">你可以使用 PowerShell 和 WMI 修改定义如何在计算机上 UE-V 同步设置的设置。</span><span class="sxs-lookup"><span data-stu-id="6f6f3-125">You can use PowerShell and WMI to modify the settings that define how UE-V synchronizes settings on computers.</span></span>

[<span data-ttu-id="6f6f3-126">使用 PowerShell 和 WMI 管理 UE-V 1.0 代理和程序包</span><span class="sxs-lookup"><span data-stu-id="6f6f3-126">Managing the UE-V 1.0 Agent and Packages with PowerShell and WMI</span></span>](managing-the-ue-v-10-agent-and-packages-with-powershell-and-wmi.md)

### <span data-ttu-id="6f6f3-127">迁移 UE-V 设置包</span><span class="sxs-lookup"><span data-stu-id="6f6f3-127">Migrating UE-V Settings Packages</span></span>

<span data-ttu-id="6f6f3-128">在迁移到新服务器或用于备份时，您可以重新定位用户设置包。</span><span class="sxs-lookup"><span data-stu-id="6f6f3-128">You can relocate the user settings packages either when migrating to a new server or for backup purposes.</span></span>

[<span data-ttu-id="6f6f3-129">迁移 UE-V 设置包</span><span class="sxs-lookup"><span data-stu-id="6f6f3-129">Migrating UE-V Settings Packages</span></span>](migrating-ue-v-settings-packages.md)

## <span data-ttu-id="6f6f3-130">此产品的其他资源</span><span class="sxs-lookup"><span data-stu-id="6f6f3-130">Other resources for this product</span></span>


[<span data-ttu-id="6f6f3-131">UE-V 1.0 的操作</span><span class="sxs-lookup"><span data-stu-id="6f6f3-131">Operations for UE-V 1.0</span></span>](operations-for-ue-v-10.md)

 

 





