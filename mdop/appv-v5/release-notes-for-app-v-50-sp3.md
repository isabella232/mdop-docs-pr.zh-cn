---
title: App-V 5.0 SP3 发行说明
description: App-V 5.0 SP3 发行说明
author: dansimp
ms.assetid: bc4806e0-2aba-4c7b-9ecc-1b2cc54af1d0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 5b6d5834e4d0c953365f955922403c1a7a2058b1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798267"
---
# App-V 5.0 SP3 发行说明


以下是 Microsoft Application Virtualization （App-v） 5.0 SP3 中的已知问题。

## 在新的 App-v 5.0 SP3 服务器安装之后，无法删除服务器文件


如果卸载 V 5.0 SP1 服务器，然后安装 app-v 5.0 SP3 服务器，安装将失败，并且安装了错误版本的管理服务器。 将显示以下错误：

`[0A5C:06F8][2014-09-12T19:08:00]i102: Detected related bundle: {bee44f0f-05be-48e4-81dd-d34a83600b95}, type: Upgrade, scope: PerMachine, version: 5.0.1218.0, operation: MajorUpgrade``[0A5C:06F8][2014-09-12T19:08:00]i000: AppvUX: A previous version of this product is installed; requesting upgrade.``[0A5C:06F8][2014-09-12T19:08:00]i102: Detected related bundle: {e1ca9d65-0ebf-4fd5-98e5-00d6453967a4}, type: Upgrade, scope: PerMachine, version: 5.0.1224.0, operation: MajorUpgrade``[0A5C:06F8][2014-09-12T19:08:00]i000: AppvUX: A previous version of this product is installed; requesting upgrade.`

出现此问题的原因是，卸载 app-v 5.0 SP1 时未删除服务器文件，因此 App-v 5.0 SP3 安装过程错误地执行升级，而不是全新安装。

**解决方法**：在开始安装 APP-V 5.0 SP3 之前删除以下注册表项：

`HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Windows\CurrentVersion\Uninstall`

## 查询 AD DS 可能导致某些应用程序无法正常工作


通过查询更新的组成员身份的 Active Directory 域服务接收更新的程序包时，如果应用程序依赖于用户的访问令牌，则可能会导致某些应用程序无法正常工作。 此外，频繁的组成员身份查询可能导致域控制器超载。 有关用户访问令牌的详细信息，请参阅[访问令牌](https://msdn.microsoft.com/library/windows/desktop/aa374909.aspx)。

**解决方法**：等待用户注销，然后重新登录，然后再查询已更新的组成员身份。 请勿使用[Microsoft Application Virtualization 5.0 Service Pack 1 的修补程序包 2](https://support.microsoft.com/kb/2897087)中介绍的注册表项来查询已更新的组成员身份。






## 相关主题


[关于 App-V 5.0 SP3](about-app-v-50-sp3.md)

 

 





