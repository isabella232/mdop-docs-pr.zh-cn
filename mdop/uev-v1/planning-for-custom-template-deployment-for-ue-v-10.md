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
# 规划 UE-V 1.0 的自定义模板部署


Microsoft 用户体验虚拟化（UE-V）使用设置位置模板（XML 文件），这些模板定义由 UE-V 捕获和应用的设置。 你可以使用 UE-V 生成器创建自定义设置位置模板，以便用户可以漫游除默认 UE-V 模板中包含的应用程序之外的应用程序的设置。 在测试自定义模板以确保应用程序设置在测试环境中正确漫游后，你可以将这些设置位置模板部署到企业中的计算机。

你可以使用现有部署基础结构（如企业软件分发（ESD））和组策略首选项部署自定义设置位置模板，或者配置 UE-V 设置模板目录。 使用 ESD 或组策略部署的模板必须使用 UE-V WMI 或 PowerShell 注册。

## 设置模板目录


用户体验虚拟化设置模板目录是 UE-V 计算机上的文件夹路径或用于存储所有自定义设置位置模板的服务器消息块（SMB）网络共享。 UE-V agent 从该位置检索新的或更新的模板。 UE-V agent 每天检查此位置一次，并根据此文件夹中的模板更新其同步行为。 自上次检查文件夹后，在此文件夹中添加或更新的模板由 UE-V agent 注册。 从该文件夹中删除的 UE-V agent deregisters 模板。 默认情况下，在 3:30 A.M. 每天注册和注销模板一次。 任务计划程序的本地时间。 有关 UE-V 任务的详细信息，请参阅[更改 Ue-v 计划任务的频率](changing-the-frequency-of-ue-v-scheduled-tasks.md)。

你可以使用安装命令行选项、组策略、WMI 或 PowerShell 配置设置模板目录路径。 存储在设置模板目录路径上的模板由计划任务自动注册和注销。 您可以根据需要自定义此计划任务。

## 替换默认的 Microsoft 模板


UE-V agent 将为常见的 Microsoft 应用程序和 Windows 设置安装默认设置位置模板组。 如果您的企业需要这些模板的自定义版本，则可以将 UE-V agent 配置为使用设置模板目录，然后应替换默认的 Microsoft 模板。

在 UE-V agent 安装过程中，命令行参数 `RegisterMSTemplates` 可用于禁用默认 Microsoft 模板的注册过程。 有关如何设置 UE-V 参数的详细信息，请参阅[规划 Ue-v 配置方法](planning-for-ue-v-configuration-methods.md)。

使用组策略配置设置模板目录路径时，可以选择替换默认的 Microsoft 模板。 如果将策略设置配置为替换默认的 Microsoft 模板，则将从计算机中删除由 UE-V agent 安装的所有默认 Microsoft 模板，并且只会使用位于设置模板目录中的模板。 UE-V Agent 配置设置 `RegisterMSTemplates` 必须设置为 true 才能替代默认的 Microsoft 模板。

**注意** 如果在启用此策略设置后禁用此策略设置，则 UE-V agent 将不会还原默认的 Microsoft 模板。

 

如果设置模板目录中存在使用与默认 Microsoft 模板相同 ID 的自定义模板，并且未将 UE-V agent 配置为替换默认的 Microsoft 模板，则将忽略目录中的 Microsoft 模板。

你还可以使用 UE-V PowerShell 功能替换默认模板。 若要将默认的 Microsoft 模板替换为 PowerShell，请注销所有默认的 Microsoft 模板，然后注册自定义模板。

**注意** 即使为应用程序部署了新设置模板，旧的设置程序包仍保留在设置存储位置。 这些程序包不会由代理读取，但它们都不会自动删除。

 

## 相关主题


[规划 UE-V 1.0](planning-for-ue-v-10.md)

[规划要使用 UE-V 1.0 同步的应用程序](planning-which-applications-to-synchronize-with-ue-v-10.md)

[规划 UE-V 配置方法](planning-for-ue-v-configuration-methods.md)

规划自定义模板部署
 

 





