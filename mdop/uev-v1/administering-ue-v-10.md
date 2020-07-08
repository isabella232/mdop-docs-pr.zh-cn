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
# 管理 UE-V 1.0


部署 Microsoft 用户体验虚拟化（UE-V）后，您必须能够执行各种持续的管理任务。 以下部分介绍了这些安装后任务。

## 管理 UE-V 资源


在 UE-V 生命周期的过程中，你将需要管理 UE-V agent 的配置，还需要管理资源（如设置程序包）的存储位置。 你可能需要执行其他任务，例如，在安装 UE-V 之前将用户的设置还原到其原始状态，以便恢复丢失的设置。 以下主题提供了管理 UE-V 资源的指南。

### 更改 UE-V 计划任务的频率

你可以配置计划任务，以便在 UE-V 检查设置模板目录中的新的、已更新或已删除的自定义设置位置模板时进行管理。

[更改 UE-V 计划任务的频率](changing-the-frequency-of-ue-v-scheduled-tasks.md)

### <a href="" id="sharing-settings-location-templates-with-the-ue-v-template-gallery-"></a>使用 UE-V 模板库共享设置位置模板

UE-V 模板库有利于共享 UE-V 设置位置模板。 库允许你上载你的设置位置模板以与其他人共享，并下载其他人创建的模板。

[使用 UE-V 模板库共享设置位置模板](sharing-settings-location-templates-with-the-ue-v-template-gallery.md)

### 还原与 UE-V 1.0 同步的应用程序和 Windows 设置

UE-V 的 WMI 和 PowerShell 功能提供了还原设置程序包的功能。 WMI 和 PowerShell 命令允许你在启动 UE-V agent 后首次启动应用程序时，将应用程序设置和 Windows 设置还原到计算机上的设置值。

[还原与 UE-V 1.0 同步的应用程序和 Windows 设置](restoring-application-and-windows-settings-synchronized-with-ue-v-10.md)

### 使用组策略对象配置 UE-V

你可以使用组策略修改定义如何在计算机上 UE-V 同步设置的设置。

[使用组策略对象配置 UE-V](configuring-ue-v-with-group-policy-objects.md)

### 使用 PowerShell 和 WMI 管理 UE-V

你可以使用 PowerShell 和 WMI 修改定义如何在计算机上 UE-V 同步设置的设置。

[使用 PowerShell 和 WMI 管理 UE-V 1.0 代理和程序包](managing-the-ue-v-10-agent-and-packages-with-powershell-and-wmi.md)

### 迁移 UE-V 设置包

在迁移到新服务器或用于备份时，您可以重新定位用户设置包。

[迁移 UE-V 设置包](migrating-ue-v-settings-packages.md)

## 此产品的其他资源


[UE-V 1.0 的操作](operations-for-ue-v-10.md)

 

 





