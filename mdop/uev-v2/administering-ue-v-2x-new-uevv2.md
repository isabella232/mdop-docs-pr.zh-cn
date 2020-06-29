---
title: 管理 UE-V 2. x
description: 管理 UE-V 2. x
author: dansimp
ms.assetid: 996e4797-8383-4627-b714-24a84c907798
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2674f6ace80672c1e89bb4f9c765b56f260c3bc0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803815"
---
# <span data-ttu-id="54017-103">管理 UE-V 2. x</span><span class="sxs-lookup"><span data-stu-id="54017-103">Administering UE-V 2.x</span></span>


<span data-ttu-id="54017-104">部署 Microsoft 用户体验虚拟化（UE-V）2.0、2.1 或 2.1 SP1 后，必须能够执行各种持续的管理任务，例如管理 UE-V Agent 的配置和恢复丢失的设置。</span><span class="sxs-lookup"><span data-stu-id="54017-104">After you have deployed Microsoft User Experience Virtualization (UE-V) 2.0, 2.1, or 2.1 SP1, you must be able to perform various ongoing administrative tasks, such as managing the configuration of the UE-V Agent and recovering lost settings.</span></span> <span data-ttu-id="54017-105">以下部分介绍了这些安装后任务。</span><span class="sxs-lookup"><span data-stu-id="54017-105">These post-installation tasks are described in the following sections.</span></span>

## <span data-ttu-id="54017-106">管理 UE-V 2. x 配置</span><span class="sxs-lookup"><span data-stu-id="54017-106">Managing UE-V 2.x configurations</span></span>


<span data-ttu-id="54017-107">在 UE-V 生命周期的过程中，你必须管理 UE-V Agent 的配置，还必须管理资源的存储位置，例如设置程序包文件。</span><span class="sxs-lookup"><span data-stu-id="54017-107">In the course of the UE-V lifecycle, you have to manage the configuration of the UE-V Agent and also manage storage locations for resources such as settings package files.</span></span>

[<span data-ttu-id="54017-108">管理 UE-V 2.x 的配置</span><span class="sxs-lookup"><span data-stu-id="54017-108">Manage Configurations for UE-V 2.x</span></span>](manage-configurations-for-ue-v-2x-new-uevv2.md)

## <span data-ttu-id="54017-109">使用自定义 UE-V 模板和 UE-V 2. x 生成器</span><span class="sxs-lookup"><span data-stu-id="54017-109">Working with custom UE-V templates and the UE-V 2.x Generator</span></span>


<span data-ttu-id="54017-110">本主题提供有关如何使用 UE-V 发生器和管理自定义设置位置模板的说明。</span><span class="sxs-lookup"><span data-stu-id="54017-110">This topic provides instructions for how to use the UE-V Generator and manage custom settings location templates.</span></span>

[<span data-ttu-id="54017-111">使用自定义 UE-V x 模板和 UE-V 2 版生成器</span><span class="sxs-lookup"><span data-stu-id="54017-111">Working with Custom UE-V 2.x Templates and the UE-V 2.x Generator</span></span>](working-with-custom-ue-v-2x-templates-and-the-ue-v-2x-generator-new-uevv2.md)

## <span data-ttu-id="54017-112">备份和还原与 UE-V 2 同步的应用程序和 Windows 设置</span><span class="sxs-lookup"><span data-stu-id="54017-112">Backup and restore application and Windows settings that are synchronized with UE-V 2.x</span></span>


<span data-ttu-id="54017-113">UE-V 的 windows 管理规范（WMI）和 Windows PowerShell 功能提供了还原设置程序包的功能。</span><span class="sxs-lookup"><span data-stu-id="54017-113">Windows Management Instrumentation (WMI) and Windows PowerShell features of UE-V provide the ability to restore settings packages.</span></span> <span data-ttu-id="54017-114">通过使用 WMI 和 Windows PowerShell 命令，你可以将应用程序和 Windows 设置还原到其原始状态，并在用户采用新设备时还原其他设置。</span><span class="sxs-lookup"><span data-stu-id="54017-114">By using WMI and Windows PowerShell commands, you can restore application and Windows settings to their original state and restore additional settings when a user adopts a new device.</span></span>

[<span data-ttu-id="54017-115">在 UE-V 2. x 中管理管理备份和还原</span><span class="sxs-lookup"><span data-stu-id="54017-115">Manage Administrative Backup and Restore in UE-V 2.x</span></span>](manage-administrative-backup-and-restore-in-ue-v-2x-new-topic-for-21.md)

## <span data-ttu-id="54017-116">更改 UE-V 2 x 计划任务的频率</span><span class="sxs-lookup"><span data-stu-id="54017-116">Changing the frequency of UE-V 2.x scheduled tasks</span></span>


<span data-ttu-id="54017-117">你可以配置计划任务，以便在 UE-V 检查新的或更新的设置，或设置模板目录中更新的自定义设置位置模板时进行管理。</span><span class="sxs-lookup"><span data-stu-id="54017-117">You can configure the scheduled tasks that manage when UE-V checks for new or updated settings or for updated custom settings location templates in the settings template catalog.</span></span>

[<span data-ttu-id="54017-118">更改 UE-V 2 x 计划任务的频率</span><span class="sxs-lookup"><span data-stu-id="54017-118">Changing the Frequency of UE-V 2.x Scheduled Tasks</span></span>](changing-the-frequency-of-ue-v-2x-scheduled-tasks-both-uevv2.md)

## <span data-ttu-id="54017-119">迁移 UE-V 2 x-blade 设置程序包</span><span class="sxs-lookup"><span data-stu-id="54017-119">Migrating UE-V 2.x settings packages</span></span>


<span data-ttu-id="54017-120">当用户设置包迁移到新服务器或用于备份时，您可以重新定位用户设置包。</span><span class="sxs-lookup"><span data-stu-id="54017-120">You can relocate the user settings packages either when they migrate to a new server or for backup purposes.</span></span>

[<span data-ttu-id="54017-121">迁移 UE-V 2 x-blade 设置程序包</span><span class="sxs-lookup"><span data-stu-id="54017-121">Migrating UE-V 2.x Settings Packages</span></span>](migrating-ue-v-2x-settings-packages-both-uevv2.md)

## <span data-ttu-id="54017-122">在应用程序虚拟化应用程序中使用 UE-V 2. x</span><span class="sxs-lookup"><span data-stu-id="54017-122">Using UE-V 2.x with Application Virtualization applications</span></span>


<span data-ttu-id="54017-123">你可以将 UE-V 与 Microsoft Application Virtualization （App-v）配合使用，以在多台计算机上共享虚拟应用程序和安装的应用程序之间的设置。</span><span class="sxs-lookup"><span data-stu-id="54017-123">You can use UE-V with Microsoft Application Virtualization (App-V) to share settings between virtual applications and installed applications across multiple computers.</span></span>

[<span data-ttu-id="54017-124">在应用程序虚拟化应用程序中使用 UE-V 2. x</span><span class="sxs-lookup"><span data-stu-id="54017-124">Using UE-V 2.x with Application Virtualization Applications</span></span>](using-ue-v-2x-with-application-virtualization-applications-both-uevv2.md)

## <span data-ttu-id="54017-125">此产品的其他资源</span><span class="sxs-lookup"><span data-stu-id="54017-125">Other resources for this product</span></span>


-   [<span data-ttu-id="54017-126">Microsoft 用户体验虚拟化（UE-V） 2. x</span><span class="sxs-lookup"><span data-stu-id="54017-126">Microsoft User Experience Virtualization (UE-V) 2.x</span></span>](index.md)

-   [<span data-ttu-id="54017-127">UE-V 2.x 入门</span><span class="sxs-lookup"><span data-stu-id="54017-127">Get Started with UE-V 2.x</span></span>](get-started-with-ue-v-2x-new-uevv2.md)

-   [<span data-ttu-id="54017-128">准备 UE-V 2. x 部署</span><span class="sxs-lookup"><span data-stu-id="54017-128">Prepare a UE-V 2.x Deployment</span></span>](prepare-a-ue-v-2x-deployment-new-uevv2.md)

-   [<span data-ttu-id="54017-129">解决 UE-V 2. x</span><span class="sxs-lookup"><span data-stu-id="54017-129">Troubleshooting UE-V 2.x</span></span>](troubleshooting-ue-v-2x-both-uevv2.md)

-   [<span data-ttu-id="54017-130">UE-V 2.x 的技术参考</span><span class="sxs-lookup"><span data-stu-id="54017-130">Technical Reference for UE-V 2.x</span></span>](technical-reference-for-ue-v-2x-both-uevv2.md)






 

 





