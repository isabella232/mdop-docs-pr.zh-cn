---
title: 为 UE-V 1.0 部署 UE-V 设置位置模板
description: 为 UE-V 1.0 部署 UE-V 设置位置模板
author: dansimp
ms.assetid: 7e0cc553-14f7-40fa-828a-281c8d2d1934
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b276fb9d6c0b3749f9818483869dfe98bbc147c7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804105"
---
# 为 UE-V 1.0 部署 UE-V 设置位置模板


Microsoft 用户体验虚拟化（UE-V）使用设置位置模板（XML 文件），这些模板定义用户体验虚拟化捕获和应用的设置。 UE-V 包含一组标准模板以及一个工具，即 UE-V 生成器，该生成器允许你创建自定义设置位置模板。 创建设置位置模板后，应对其进行测试以确保应用程序设置在测试环境中正确漫游。 然后，您可以安全地将设置位置模板部署到企业中的计算机。

可以使用企业软件分发（ESD）、组策略首选项或通过配置 UE-V 设置模板目录来部署设置位置模板。 使用 ESD 或组策略部署的模板必须通过 UE-V WMI 或 PowerShell 注册。 存储在设置模板目录位置的模板由 UE-V agent 自动注册。

## 使用设置模板目录路径部署设置位置模板


可以使用以下方法定义 UE-V 设置位置模板目录路径：组策略、代理安装命令行参数、WMI 或 PowerShell。 定义模板目录路径后，UE-V agent 将从该位置检索新的或更新的模板。 UE-V agent 每天检查此位置一次，并根据在此文件夹中找到的模板更新其同步行为。 自上次检查以来，在此文件夹中添加或更新的模板由 UE-V agent 注册。 UE-V agent 还将注销已从此文件夹中删除的模板。 任务计划程序每天注册和注销一次模板。

**使用设置模板目录路径部署 UE-V 设置位置模板**

1.  导航到定义为设置模板目录的网络共享文件夹。

2.  在设置模板目录中添加、删除或更新设置位置模板，以反映 UE-V 计算机的所需 UE-V agent 模板配置。

3.  计算机上的模板根据对设置模板目录的更改每天更新。

4.  打开提升的命令提示符并导航到 **% program files%\\Microsoft 用户体验虚拟化 \\ agent \ &lt; x86 或 x64 &gt; **，然后运行**ApplySettingsTemplateCatalog.exe**以手动更新运行 ue-v Agent 的计算机上的模板。

## 相关主题


[Microsoft 用户体验虚拟化 (UE-V) 1.0](index.md)

[部署 UE-V 1.0](deploying-ue-v-10.md)

[规划要使用 UE-V 1.0 同步的应用程序](planning-which-applications-to-synchronize-with-ue-v-10.md)

 

 





