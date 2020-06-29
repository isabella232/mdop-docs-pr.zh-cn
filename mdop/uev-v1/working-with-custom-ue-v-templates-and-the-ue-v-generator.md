---
title: 使用自定义 UE-V 模板和 UE-V 生成器
description: 使用自定义 UE-V 模板和 UE-V 生成器
author: dansimp
ms.assetid: 7bb2583a-b032-4800-9bf9-eb33528e1d0d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: db5387254842bfdcf3898089bc12a8e929e3813a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803476"
---
# 使用自定义 UE-V 模板和 UE-V 生成器


为了在用户计算机之间漫游应用程序，Microsoft 用户体验虚拟化（UE-V）使用*设置位置模板*。 某些设置位置模板包含在用户体验虚拟化中。 你还可以通过 UE-V 生成器创建、编辑或验证自定义设置位置模板。

UE-V 生成器监视应用程序以发现和捕获应用程序存储其设置的位置。 正在监视的应用程序必须是传统应用程序。 UE-V 生成器无法为以下应用程序类型创建设置位置模板：

-   虚拟化应用程序

-   通过终端服务提供的应用程序

-   Java 应用程序

-   Windows 8 应用程序

## 使用 UE-V 生成器创建 UE-V 设置位置模板


如何使用 UE-V 生成器创建设置位置模板。

[使用 UE-V 生成器创建 UE-V 设置位置模板](create-ue-v-settings-location-templates-with-the-ue-v-generator.md)

## 使用 UE-V 生成器编辑 UE-V 设置位置模板


如何使用 UE-V 生成器编辑设置位置模板。

[使用 UE-V 生成器编辑 UE-V 设置位置模板](edit-ue-v-settings-location-templates-with-the-ue-v-generator.md)

## 使用 UE-V 生成器验证 UE-V 设置位置模板


如何使用 UE-V 生成器验证在 UE-V 生成器外部修改的设置位置模板。

[使用 UE-V 生成器验证 UE-V 设置位置模板](validate-ue-v-settings-location-templates-with-ue-v-generator.md)

## <a href="" id="bkmk-standardnonstandardsettingslocations"></a>标准和非标准设置位置


UE-V 生成器可帮助你识别应用程序在何处查找应用程序用于存储设置信息的设置文件和注册表设置。 你可以使用 UE-V 生成器作为发现过程的一部分打开应用程序，以捕获标准位置中的设置。 标准位置包括以下内容：

-   **注册表设置**- **HKEY \ _CURRENT \ _USER**下的注册表位置

-   **应用程序设置文件**-存储在 \\**用户**\\ [用户名 \] \\ **AppData**  \\  **漫游**中的文件

UE-V 发电机排除了通常存储应用软件文件的位置不会在用户计算机或环境之间很好地漫游。 UE-V 生成器将排除这些位置。 排除的位置如下所示：

-   HKEY \ _CURRENT 已登录用户无法向其写入值的 _USER 注册表项和文件

-   HKEY \ _CURRENT \ _USER 与 Windows 操作系统的核心功能相关联的注册表项和文件

-   位于 HKEY _LOCAL \ _MACHINE 配置单元中的所有注册表项（需要管理员权限，并且可能需要 UAC 协议才能设置）

-   位于 "程序文件" 目录中的文件（需要管理员权限，并且可能需要 UAC 协议才能设置）

-   位于用户 \\ [用户名 \] \\ AppData \\ LocalLow 中的文件

-   位于% systemroot% 中的 Windows 操作系统文件（需要管理员权限，并且可能需要 UAC 协议才能设置）

如果需要在这些位置存储的注册表项和文件才能漫游应用程序设置，则可以在模板创建过程中手动将排除的位置添加到设置位置模板。

## 此产品的其他资源


[UE-V 1.0 的操作](operations-for-ue-v-10.md)

[管理 UE-V 1.0](administering-ue-v-10.md)

 

 





