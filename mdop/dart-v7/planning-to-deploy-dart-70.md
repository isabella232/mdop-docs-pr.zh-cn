---
title: 计划部署 DaRT 7.0
description: 计划部署 DaRT 7.0
author: dansimp
ms.assetid: 05e97cdb-a8c2-46e4-9c75-a7d12fe26fe8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 09725e994a95f4f93ae655402e7577e137e33f18
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802944"
---
# 计划部署 DaRT 7.0


在创建部署计划之前，必须考虑许多不同的部署配置和先决条件。 本部分包含的信息可帮助您收集可用于制定最符合业务要求的部署计划所必需的信息。

规划 Microsoft 诊断和恢复工具集（DaRT）7安装时，请考虑以下事项：

-   安装 DaRT 时，可以在 IT 管理员计算机上安装所有功能，您将执行与运行 DaRT 相关联的所有任务。 或者，你可以仅安装在 IT 管理员计算机上创建恢复映像的 DaRT 功能。 然后，在帮助台代理计算机上安装用于运行 DaRT 的功能，例如**Dart 远程连接查看器**和**故障分析器**。

-   若要能够远程运行 DaRT，请确保帮助台代理计算机和你可能在远程进行故障排除的所有计算机位于同一网络上。

-   在将 DaRT 部署到生产之前，你可以先构建一个实验室环境进行测试。 测试实验室至少应包括两台计算机，一台充当 IT 管理员/支持台代理计算机，另一台充当最终用户计算机。 或者，如果你想要将 IT 管理员的责任与帮助台代理的人员分开，可以在你的实验室中使用三台计算机。

## 查看受支持的配置


你应该查看 Microsoft 诊断和恢复工具集（DaRT）7支持的配置信息，以确认你选择用于客户端或功能安装的计算机是否满足最低硬件和操作系统要求。

[DaRT 7.0 支持的配置](dart-70-supported-configurations-dart-7.md)

## 计划创建 DaRT 恢复映像


创建 DaRT 恢复映像时，必须确定要在映像中包含的工具。 做出决策时，请记住最终用户可能偶尔有权访问各种 DaRT 工具。 创建恢复映像时，你还将指定是否要包括其他驱动程序或文件。 确定要包括在 DaRT 恢复映像中的任何其他驱动程序或文件的位置。

你应该了解有关创建 DaRT 恢复映像的先决条件和其他额外计划建议。

[计划创建 DaRT 7.0 恢复映像](planning-to-create-the-dart-70-recovery-image.md)

## 计划保存和部署 DaRT 恢复映像


可以使用多种方法来保存和部署 DaRT 恢复映像。 确定你将使用的方法时，请考虑每个方法的优缺点。 此外，请考虑你希望如何在企业中使用 DaRT。

**注意** 您可能希望在您的组织中使用多个方法。 例如，在大多数情况下，你可以从远程分区启动到 DaRT，并且在最终用户计算机无法连接到网络时有可用的 USB 闪存驱动器。

 

[计划如何保存和部署 DaRT 7.0 恢复映像](planning-how-to-save-and-deploy-the-dart-70-recovery-image.md)

## 用于规划部署 DaRT 的其他资源


[计划 DaRT 7.0](planning-for-dart-70-new-ia.md)

 

 





