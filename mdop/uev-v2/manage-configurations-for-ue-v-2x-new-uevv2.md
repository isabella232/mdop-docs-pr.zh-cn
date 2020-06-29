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
# 管理 UE-V 2.x 的配置


在 Microsoft 用户体验虚拟化（UE-V）2.0、2.1 或 2.1 SP1 生命周期的过程中，你必须管理 UE-V Agent 的配置，并管理资源的存储位置（如设置程序包文件）。 您可能需要执行其他任务，例如，配置公司设置中心以定义用户与 UE-V 交互的方式。 以下主题提供管理这些 UE-V 资源的指南。

## 使用组策略对象配置 UE-V 2。


你可以使用组策略对象修改定义如何在计算机上 UE-V 同步设置的设置。

[通过组策略对象配置 UE-V 2. x](configuring-ue-v-2x-with-group-policy-objects-both-uevv2.md)

## 通过 System Center Configuration Manager 2012 配置 UE-V 2


你可以使用 SystemCenter2012 ConfigurationManager 管理 UE-V Agent，方法是使用 UE-V 2 配置包。

[通过 System Center Configuration Manager 2012 配置 UE-V 2](configuring-ue-v-2x-with-system-center-configuration-manager-2012-both-uevv2.md)

## 通过 PowerShell 和 WMI 管理 UE-V 2. x


UE-V 提供 Windows PowerShell cmdlet，可帮助管理员执行各种 UE-V 任务。

[管理具有 Windows PowerShell 和 WMI 的 UE-V 2。](administering-ue-v-2x-with-windows-powershell-and-wmi-both-uevv2.md)

## 配置 UE-V 2. x 的公司设置中心


你可以配置通过使用 UE-V Agent 安装的公司设置中心来定义用户与 UE-V 的交互方式。

[配置 UE-V 2. x 的公司设置中心](configuring-the-company-settings-center-for-ue-v-2x-both-uevv2.md)

## UE-V 2 的配置设置示例


下面是 UE-V 配置设置的一些示例：

-   **设置存储路径：** 指定存储 UE-V 设置的文件共享位置。

-   **设置模板目录路径：** 指定用于定义为新设置位置模板检查的位置的通用命名约定（UNC）路径。

-   **注册 Microsoft 模板：** 指定是否应在安装期间注册默认 Microsoft 模板。

-   **同步方法：** 指定 UE-V 是使用同步提供程序还是 "none"。 "SyncProvider" 支持从网络断开连接的计算机。 当计算机始终连接到网络时，将应用 "无"。 有关同步方法的详细信息，请参阅[ue-v 2. x 的同步方法](sync-methods-for-ue-v-2x-both-uevv2.md)。

-   **同步超时：** 指定在从设置存储位置检索用户设置时，计算机超时之前等待的毫秒数。

-   **启用同步：** 指定是启用还是禁用 UE-V 设置同步。

-   **最大程序包大小：** 指定 UE-V Agent 报告警告的设置包文件阈值大小（以字节为单位）。

-   **不要同步 Windows 应用设置：** 指定 UE-V 不应同步 Windows 应用。

-   **启用/禁用首次使用通知：** 指定当 ue-v Agent 首次在用户的计算机上运行时，UE-V 是否显示一个对话框。

-   **启用/禁用托盘图标：** 指定是否在通知区域中显示 "UE-V" 以及与之关联的任何通知。 图标提供指向公司设置中心的链接。

-   **自定义联系人 IT 超链接：** 在 "公司设置中心" 中定义 "**联系人 IT** " 超链接的路径、文本和说明。






## 相关主题


[管理 UE-V 2. x](administering-ue-v-2x-new-uevv2.md)

[为 UE-V 2.x 部署所需功能](deploy-required-features-for-ue-v-2x-new-uevv2.md)

[部署自定义应用程序的 UE-V 2。](deploy-ue-v-2x-for-custom-applications-new-uevv2.md)

 

 





