---
title: 管理 MBAM 2.0 功能
description: 管理 MBAM 2.0 功能
author: dansimp
ms.assetid: 065e0704-069e-4372-9b86-0b57dd7638dd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 35bb855e185ad8e3fa6880853938074cf6185a0d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803382"
---
# 管理 MBAM 2.0 功能


完成所有必要的规划，然后部署 Microsoft BitLocker 管理和监视（MBAM）后，你可以配置并使用它来管理整个企业的 BitLocker 加密本部分中的信息介绍安装后的日常 Microsoft BitLocker 管理和监视功能操作任务。

## 管理 MBAM 管理员角色


完成所有服务器功能的 MBAM 设置后，必须授予管理员用户对这些功能的访问权限。 最佳做法是将管理或使用 MBAM 服务器功能的管理员分配给 Active Directory 域服务安全组，然后应将这些组添加到相应的 MBAM 管理本地组。

[如何管理 MBAM 管理员角色](how-to-manage-mbam-administrator-roles-mbam-2.md)

## 管理 BitLocker 加密免除


MBAM 允许你向不需要或不希望其驱动器加密的特定用户授予加密免除。 当公司拥有不需要加密的计算机（例如在开发或测试中使用的计算机或不支持 BitLocker 的较旧计算机）时，通常使用计算机豁免。 在某些情况下，当地法律可能还要求某些计算机未加密。

[如何管理用户 BitLocker 加密免除](how-to-manage-user-bitlocker-encryption-exemptions-mbam-2.md)

## 使用 "控制面板" 管理 MBAM 客户端 BitLocker 加密选项


MBAM 提供一个名为 BitLocker 加密选项的自定义控制面板，该面板将显示在 "**系统和安全**" 下方。 MBAM 控制面板可用于解锁加密的固定和可移动驱动器，还可管理 PIN 或密码。

**注意** 此自定义控制面板不替代默认 Windows BitLocker 控制面板。

 

[如何使用控制面板管理 MBAM 客户端 BitLocker 加密选项](how-to-manage-mbam-client-bitlocker-encryption-options-by-using-the-control-panel-mbam-2.md)

## 用于管理 MBAM 功能的其他资源


[MBAM 2.0 的操作](operations-for-mbam-20-mbam-2.md)

 

 





