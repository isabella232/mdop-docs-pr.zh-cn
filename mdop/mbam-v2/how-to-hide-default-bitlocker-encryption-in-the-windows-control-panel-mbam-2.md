---
title: 如何在 Windows 控制面板中隐藏默认的 BitLocker 加密
description: 如何在 Windows 控制面板中隐藏默认的 BitLocker 加密
author: dansimp
ms.assetid: 6674aa51-2b5d-4e4a-8b43-2cc18d008285
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: eda8fafbd7b3ebf414520354eba6def2e97f6237
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803497"
---
# 如何在 Windows 控制面板中隐藏默认的 BitLocker 加密


Microsoft BitLocker 管理和监视（MBAM）提供用于 Microsoft BitLocker 管理和监视客户端计算机（称为 BitLocker 加密选项）的自定义控制面板。 此自定义控制面板可以替代默认的 Windows BitLocker 控制面板，该控制面板称为 "BitLocker 驱动器加密"。 "自定义控制面板" 位于 "系统和安全" 下的 "控制面板" 下，使用户能够管理其 PIN 和密码以及解锁驱动器，以及隐藏允许管理员解密驱动器或暂停或恢复 BitLocker 驱动器加密的界面。

**在 Windows "控制面板" 中隐藏默认的 BitLocker 驱动器加密**

1.  在组策略管理控制台（GPMC）、高级组策略管理（AGPM）或 BitLocker 组策略计算机上的本地组策略编辑器中，浏览到 "**用户配置**"。

2.  接下来，单击 "**策略**"，选择 "**管理模板**"，然后单击 "**控制面板"**。

3.  双击 "**详细信息**" 窗格中的 "**隐藏指定的控制面板项目**"，然后选择 "**已启用**"。

4.  单击 "**显示**"，单击 "**添加**"，然后键入 " **BitLockerDriveEncryption**"。 此策略将从 Windows 控制面板中隐藏默认的 Windows BitLocker 管理工具，在 "控制面板" 中，允许用户在 "系统和安全" 下打开更新的 MBAM BitLocker 加密选项工具。

## 相关主题


[部署 MBAM 2.0 组策略对象](deploying-mbam-20-group-policy-objects-mbam-2.md)

 

 





