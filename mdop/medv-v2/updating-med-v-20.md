---
title: 更新 MED-V 2.0
description: 更新 MED-V 2.0
author: dansimp
ms.assetid: beea2f54-42d7-4a17-98e0-d243a8562265
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 62e8987ec511783422b8dd336dd4f3be2008c9b2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803427"
---
# 更新 MED-V 2.0


通过为 Microsoft 企业版桌面虚拟化（MED-V）2.0 应用相应的安全更新来帮助保护您的系统。

## 更新 MED-V


你可以由最终用户以交互方式或通过使用电子软件分发系统以静默方式更新 MED-V。 安装 MED-V 主机代理升级 MED-V 主机代理，并根据需要更新 MED-V 工作区。 MED-V 主机代理和来宾代理保持同步。如果在更新 MED-V 主机代理的同时从 MED-V 工作区运行应用程序，则需要重启主机才能完成更新。 如果没有正在运行的应用程序，则会自动重新启动 MED-V，并且升级完成后不重新启动主机计算机。

如果您使用电子软件分发系统更新 MED-V，则可以控制重启行为。 若要执行此操作，请在安装 MED-V\_HostAgent\_Setup.exe 时通过在命令提示符处键入**REBOOT = "ReallySuppress"** 来取消重新启动。 然后，配置电子软件分发系统以捕获3010返回代码（该代码表明需要重启），并执行设置重启行为。

## 相关主题


[MED-V 的技术参考](technical-reference-for-med-v.md)

 

 





