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
# 规划 UE-V 配置方法


Microsoft 用户体验虚拟化（UE-V）配置确定设置在整个企业中的同步方式。 本主题介绍如何创建 UE-V 配置，以帮助你制定最符合你的业务需求的配置计划。

## UE-V 的配置方法


你可以在代理安装之前、期间或之后配置 UE-V，具体取决于你使用的配置方法。

**组策略：** 现有组策略基础结构可用于在 ue-v agent 部署之前或之后配置 ue-v。 UE-V ADMX 模板支持通用 UE-V Agent 配置选项的集中管理，其中包括用于配置 UE-V 同步的设置。 使用组策略的网络环境可以预配置 UE-V，以便部署代理。

[使用组策略对象配置 UE-V](configuring-ue-v-with-group-policy-objects.md)

[安装 UE-V 组策略 ADMX 模板](installing-the-ue-v-group-policy-admx-templates.md)

**命令行或批处理脚本安装：** 与 ue-v Agent 的部署一起使用的参数允许配置许多 ue-v 设置。 电子软件分发系统（如 System Center Configuration Manager）使用这些参数在部署和安装 UE-V Agent 软件时配置其客户端。 有关安装参数和示例安装脚本的列表，请参阅[部署 Ue-v Agent](deploying-the-ue-v-agent.md)。

**PowerShell 和 wmi：** 在安装 ue-v Agent 后，使用 POWERSHELL 或 wmi 的脚本化命令可用于修改配置。 有关 PowerShell 和 WMI 命令的列表，请参阅[使用 powershell 和 Wmi 管理 ue-v 1.0 代理和程序包](managing-the-ue-v-10-agent-and-packages-with-powershell-and-wmi.md)。

**编辑注册表设置：** UE-V 设置存储在注册表中，并且可以通过可修改注册表设置的任何工具（如 RegEdit）进行修改。

**注意** 注册表修改可能导致数据丢失或计算机变得不响应。 我们建议你使用其他配置方法。

 

### UE-V 配置设置

以下是 UE-V 配置设置的示例：

-   **设置存储路径：** 指定用于存储 ue-v 设置的文件共享位置。

-   **设置模板目录路径：** 指定通用命名约定（UNC）路径，该路径定义为新设置位置模板选中的位置。

-   **注册 Microsoft 模板：** 指定在安装期间是否注册默认 Microsoft 模板。

-   **同步方法：** 指定是否将 Windows 脱机文件功能用于脱机支持。

-   **同步超时：** 指定从设置存储位置检索用户设置时，计算机在超时之前等待的毫秒数。

-   **启用同步：** 指定是启用还是禁用 ue-v 设置同步。

-   **程序包最大大小：** 指定 ue-v Agent 报告警告的设置包文件阈值大小（以字节为单位）。

## 相关主题


[规划 UE-V 1.0](planning-for-ue-v-10.md)

[规划 UE-V 配置](planning-for-ue-v-configuration.md)

 

 





