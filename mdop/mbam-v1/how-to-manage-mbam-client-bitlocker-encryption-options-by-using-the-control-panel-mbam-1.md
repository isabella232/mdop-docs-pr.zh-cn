---
title: 如何使用控制面板管理 MBAM 客户端 BitLocker 加密选项
description: 如何使用控制面板管理 MBAM 客户端 BitLocker 加密选项
author: dansimp
ms.assetid: c08077e1-5529-468f-9370-c3b33fc258f3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 271147d0e5581f6ce49fe0b46aa83dae6ae4556b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798175"
---
# 如何使用控制面板管理 MBAM 客户端 BitLocker 加密选项


安装 MBAM 客户端时，"系统和安全" 下的 "Microsoft BitLocker 管理和监视" （MBAM）控制面板应用程序（称为 BitLocker 加密选项）将在 "**系统和安全**" 下可用。 此自定义 MBAM 控制面板取代了默认的 Windows BitLocker "控制面板"。 MBAM 控制面板使你能够解锁加密的驱动器（固定和可移动），还可帮助你管理 PIN 或密码。 有关启用 MBAM 控制面板的详细信息，请参阅[如何在 Windows "控制面板" 中隐藏默认的 BitLocker 加密](how-to-hide-default-bitlocker-encryption-in-the-windows-control-panel.md)。

**注意** 对于 BitLocker 客户端，管理员和操作日志文件位于 "**应用程序和服务日志**"  /  **Microsoft**  /  **Windows**  /  **BitLockerManagement**下的 "事件查看器" 中。

 

**使用 "MBAM 客户端" 控制面板**

1.  若要打开 BitLocker 加密选项，请单击 "**开始**"，然后选择 **"控制面板"**。 当 **"控制面板"** 打开时，选择 "**系统和安全**"。

2.  双击 " **BitLocker 加密选项**" 以打开 "自定义 MBAM" 控制面板。 您将看到计算机上的所有硬盘驱动器及其加密状态的列表。 你还将看到用于管理 PIN 或密码的选项。

3.  如果已部署用户和计算机免除策略，请使用计算机上的硬盘驱动器列表来验证加密状态、解锁驱动器或请求 BitLocker 保护的豁免。

4.  非管理员可以使用 "BitLocker 加密选项" 控制面板管理 Pin 或密码。 用户可以选择 **"管理 PIN"，** 然后输入当前 pin 和新 pin 码。 用户也可以确认其新 PIN 码。 "**更新 PIN** " 功能会将 PIN 重置为用户选择的新 pin。

5.  要管理您的密码，请选择 "**解锁驱动器**"，然后输入您的当前密码。 解锁驱动器后，选择 "**重置密码**" 以更改当前密码。

## 相关主题


[管理 MBAM 1.0 功能](administering-mbam-10-features.md)

 

 





