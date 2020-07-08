---
title: 管理 MBAM 1.0 功能
description: 管理 MBAM 1.0 功能
author: dansimp
ms.assetid: dd9a9eff-f1ad-4af3-85d9-c19131a4ad22
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a99ac556227c0f113fb20f3aca32d21c204877b0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802925"
---
# 管理 MBAM 1.0 功能


完成所有必需的 Microsoft BitLocker 管理和监视（MBAM）规划和部署后，您可以配置和使用 MBAM 管理企业 BitLocker 加密。 本部分中的信息介绍安装后的日常 MBAM 功能操作任务。

## 管理 MBAM 管理员角色


完成所有服务器功能的 MBAM 设置后，必须授予管理员用户访问这些服务器功能的权限。 最佳做法是管理或使用 MBAM 服务器功能的管理员应分配给 Active Directory 安全组，然后应将这些组添加到相应的 MBAM 管理本地组。

[如何管理 MBAM 管理员角色](how-to-manage-mbam-administrator-roles-mbam-1.md)

## 管理硬件兼容性


MBAM 硬件兼容性功能可帮助你确保仅加密你指定为支持 BitLocker 的计算机硬件。 当此功能处于打开状态时，位 _admmontla 将仅加密标记为兼容的计算机。

**重要提示** 关闭此功能时，将对部署了 MBAM 策略的所有计算机进行加密。

 

如果你部署 "允许硬件兼容性检查" 组策略，MBAM 可以收集客户端计算机的建立和模型的信息。 如果配置此策略，则当在客户端计算机上部署 MBAM 客户端时，MBAM 代理会向 MBAM 服务器报告计算机和模型信息。

[如何管理硬件兼容性](how-to-manage-hardware-compatibility-mbam-1.md)

[如何管理用户 BitLocker 加密免除](how-to-manage-user-bitlocker-encryption-exemptions-mbam-1.md)

## 管理 BitLocker 加密免除


MBAM 可以授予来自 BitLocker 加密的两种形式的免除：计算机豁免和用户豁免。 当公司拥有不需要加密的计算机（例如在开发或测试中使用的计算机或不支持 BitLocker 的较旧计算机）时，通常使用计算机豁免。 在某些情况下，当地法律可能还要求某些计算机未加密。 您也可以选择免除不需要或不希望其驱动器加密的用户。

[如何管理计算机 BitLocker 加密免除](how-to-manage-computer-bitlocker-encryption-exemptions.md)

## 使用 "控制面板" 管理 MBAM 客户端 BitLocker 加密选项


如果通过组策略对象（GPO）启用，则名为 "BitLocker 加密选项" 的自定义 MBAM 控制面板将在 "**系统和安全**" 下可用。 此自定义控制面板替换默认的 Windows BitLocker 控制面板。 MBAM 控制面板使你能够解锁加密的驱动器（固定和可移动），还可帮助你管理 PIN 或密码。

[如何使用控制面板管理 MBAM 客户端 BitLocker 加密选项](how-to-manage-mbam-client-bitlocker-encryption-options-by-using-the-control-panel-mbam-1.md)

## 用于管理 MBAM 功能的其他资源


[MBAM 1.0 的操作](operations-for-mbam-10.md)

 

 





