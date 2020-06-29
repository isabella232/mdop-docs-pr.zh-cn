---
title: 部署 UE-V 1.0
description: 部署 UE-V 1.0
author: dansimp
ms.assetid: 519598bb-8c81-4af7-bee7-357696bff880
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 1a1c515f9be950d8ca7b0a199344d34f7852073d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804110"
---
# 部署 UE-V 1.0


Microsoft 用户体验虚拟化（UE-V）有许多不同的部署配置支持。 本部分包含常规信息和分步过程，可帮助你成功执行必须在部署的不同阶段完成的任务。

## UE-V 的部署信息


UE-V 部署要求网络共享上的设置存储位置和在同步设置的每台计算机上安装的 UE-V agent。 UE-V 组策略模板可用于管理 UE-V 设置。 以下主题介绍了如何部署这些功能。

[为 UE-V 1.0 部署设置存储位置](deploying-the-settings-storage-location-for-ue-v-10.md)

所有 UE-V 部署都需要一个设置存储位置，其中包含同步设置值的设置包位于该位置。

[部署 UE-V 代理](deploying-the-ue-v-agent.md)

若要使用 UE-V 同步设置，计算机必须安装并运行 UE-V Agent。

[安装 UE-V 组策略 ADMX 模板](installing-the-ue-v-group-policy-admx-templates.md)

在部署 UE-V Agent 和标准 UE-V 配置之前，可以使用组策略预配置 UE-V 设置。

## 自定义模板部署的部署信息


如果你计划为除 UE-V 中包含的 Microsoft 应用程序之外的应用程序（如业务线应用程序）创建自定义设置位置模板，则可以部署设置模板目录，并且必须安装 UE-V 生成器才能创建这些模板。 有关详细信息，请参阅[规划用于 ue-v 1.0 的自定义模板部署](planning-for-custom-template-deployment-for-ue-v-10.md)。

[安装 UE-V 生成器](installing-the-ue-v-generator.md)

使用 UE-V 生成器创建、编辑和验证自定义设置位置模板，这些模板有助于同步除默认应用程序之外的应用程序的设置。

[为 UE-V 1.0 部署设置模板目录](deploying-the-settings-template-catalog-for-ue-v-10.md)

如果需要部署自定义设置位置模板以支持除 UE-V Agent 中默认应用程序之外的应用程序，必须配置设置模板目录来存储它们。

[为 UE-V 1.0 部署 UE-V 设置位置模板](deploying-ue-v-settings-location-templates-for-ue-v-10.md)

如果你需要在 UE-V Agent 中同步除默认应用程序之外的应用程序，则可以将通过 UE-V 发生器创建的自定义设置位置模板分发到 UE-V 设置模板目录。

**注意** 部署自定义模板需要设置模板目录。 默认 Microsoft 应用程序模板与 UE-V Agent 一起部署。

 

## 本产品的主题


[Microsoft 用户体验虚拟化 (UE-V) 1.0](index.md)

[用户体验虚拟化 1.0 入门](getting-started-with-user-experience-virtualization-10.md)

[规划 UE-V 1.0](planning-for-ue-v-10.md)

[UE-V 1.0 的操作](operations-for-ue-v-10.md)

[UE-V 1.0 故障排除](troubleshooting-ue-v-10.md)

 

 





