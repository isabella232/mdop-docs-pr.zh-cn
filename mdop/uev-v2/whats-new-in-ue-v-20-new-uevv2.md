---
title: UE-V 2.0 中的新增功能
description: UE-V 2.0 中的新增功能
author: dansimp
ms.assetid: 5d852beb-f293-4e3a-a33b-c40df59a7515
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a7566bd82432dcf7e4c46e1fa3e66e55d1515b79
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803673"
---
# UE-V 2.0 中的新增功能


Microsoft 用户体验虚拟化（UE-V）2.0 提供了与 UE-V 1.0 相比的这些新功能和功能。 [Microsoft 用户体验虚拟化（ue-v）2.0 发行说明](microsoft-user-experience-virtualization--ue-v--20-release-notesuevv2.md)提供了有关 ue-v 2.0 版本的详细信息。

## 不再需要客户端缓存（CSC）


此版本的 UE-V 引入了**同步提供程序**，这将替代 Windows 脱机文件功能的要求以支持设置的客户端缓存。

虽然 UE-V 仅用于在应用程序打开、关闭或 Windows 锁定或注销时同步设置，或者在登录或注销时同步设置，请参阅同步提供程序 .。。

-   使用 "**触发器事件**" 在带外同步本地应用程序和 Windows 设置

-   使用**计划任务**以你为企业要求选择的任何间隔同步设置存储包（默认情况下，每隔30分钟）

某些条件提供更频繁的同步。

-   当用户单击新的公司设置中心应用程序中的 "**立即同步**" 按钮时，设置将同步。

-   同步提供程序也可以在不等待计划同步任务的情况下为单个应用程序启动。 例如，当应用程序关闭时，任何设置更改都将写入本地缓存，同步提供程序进程将异步运行以将这些新的设置更改移动到设置存储位置。

## Windows 应用同步


Windows 应用的开发人员可以定义要同步的设置（如果有），并且这些设置现在可以通过 UE-V 捕获并同步。

默认情况下，UE-V 同步 Windows 8 和 Windows 8.1 中包含的许多 Windows 应用的设置。 你可以通过 Windows PowerShell、Windows Management Instrumentation （WMI）或组策略修改已同步应用的列表。

**注意** 如果域用户将他们的登录凭据链接到其 Microsoft 帐户，UE-V 不会同步 Windows 应用设置。 此链接会将设置同步到 Microsoft OneDrive，因此 UE-V 仅同步桌面应用程序。

 

## Microsoft 帐户链接


使用 Microsoft 帐户登录或将 Microsoft 帐户链接到域帐户时，通过 OneDrive 的设置同步是 Windows 8 的新增功能。 如果域用户使用 UE-V 并已登录到 Microsoft 帐户，那么 .。。

-   UE-V 仅同步桌面应用程序的设置

-   Microsoft 帐户处理 Windows 应用设置和 Windows 桌面设置

## 公司设置中心


你可以通过名为 "公司设置中心" 的 UE-V 2 中的应用程序向你的用户提供一些设置的控制。 公司设置中心与 UE-V Agent 一起安装，用户可以从 "控制面板"、"**开始**" 菜单或 "**开始**" 屏幕以及从 ue-v 通知区域图标访问它。

公司设置中心显示哪些设置是同步的，并且允许用户查看 UE-V 的同步状态。 如果你允许，用户可以使用公司设置中心来选择要同步的设置。 他们还可以单击 "**立即同步**" 按钮，立即同步所有设置。






## 相关主题


[UE-V 2.x 入门](get-started-with-ue-v-2x-new-uevv2.md)

[准备 UE-V 2. x 部署](prepare-a-ue-v-2x-deployment-new-uevv2.md)

[Microsoft 用户体验虚拟化 (UE-V) 2.0 发行说明](microsoft-user-experience-virtualization--ue-v--20-release-notesuevv2.md)

 

 





