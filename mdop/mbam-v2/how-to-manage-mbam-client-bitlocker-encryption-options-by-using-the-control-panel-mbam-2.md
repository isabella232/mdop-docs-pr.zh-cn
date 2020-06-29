---
title: 如何使用控制面板管理 MBAM 客户端 BitLocker 加密选项
description: 如何使用控制面板管理 MBAM 客户端 BitLocker 加密选项
author: dansimp
ms.assetid: e2ff153e-5770-4a12-b79d-cda998b8a8ab
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a42901ac9d8a1a3527712f4cf342b5c0ca9ffdfd
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803702"
---
# 如何使用控制面板管理 MBAM 客户端 BitLocker 加密选项


安装 Microsoft BitLocker 管理和监视客户端时，"系统和安全" 下的 "Microsoft BitLocker 管理和监视" （MBAM）控制面板应用程序（称为 BitLocker 加密选项）将在 "**系统和安全**" 下可用。 此 "自定义 MBAM" 控制面板是一个附加控制面板。 它不会替换默认的 Windows BitLocker "控制面板"。 MBAM 控制面板可用于解锁加密的固定和可移动驱动器，还可管理 PIN 或密码。 有关启用 MBAM 控制面板的详细信息，请参阅[如何在 Windows "控制面板" 中隐藏默认的 BitLocker 加密](how-to-hide-default-bitlocker-encryption-in-the-windows-control-panel-mbam-2.md)。

**使用 "MBAM 客户端" 控制面板**

1.  若要打开 BitLocker 加密选项，请单击 "**开始**"，然后选择 **"控制面板"**。 当 **"控制面板"** 打开时，选择 "**系统和安全**"。

2.  双击 " **BitLocker 加密选项**" 以打开 "自定义 MBAM" 控制面板。 除了用于管理 PIN 或密码的选项之外，您还可以查看计算机上所有硬盘驱动器及其加密状态的列表。

    如果已部署用户和计算机免除策略，则可以使用计算机上的硬盘驱动器列表来验证加密状态、解锁驱动器或请求 BitLocker 保护的豁免。

    "BitLocker 加密选项" 控制面板还允许非管理员用户管理其 PIN 或密码。 通过选择 "**管理 PIN**"，系统会提示用户输入当前 pin 和新 pin （除了确认新 pin）。 选择 "**更新 pin** " 会将 pin 重置为用户选择的新密码。

    要管理您的密码，请选择 "**解锁驱动器**"，然后输入您的当前密码。 解锁驱动器后，选择 "**重置密码**" 以更改当前密码。

## 相关主题


[管理 MBAM 2.0 功能](administering-mbam-20-features-mbam-2.md)

 

 





