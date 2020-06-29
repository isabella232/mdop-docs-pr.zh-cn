---
title: 配置环境先决条件
description: 配置环境先决条件
author: dansimp
ms.assetid: 7379e8e5-1cb2-4b8e-8acc-5c04e26f8c91
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 8d6fc3b81f6dafbe709dd904b9fba6124d2f6b6a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803970"
---
# 配置环境先决条件


在部署和运行 Microsoft 企业版桌面虚拟化（MED-V）2.0 之前，必须确保你的环境满足以下最低先决条件。

**Windows 7**

MED-V 主机代理和 MED-V 工作区包装程序仅在 Windows 7 或更高版本中受支持。

**Windows XP SP3**

MED-V 来宾代理仅在 Windows XP SP3 中受支持。

**.NET Framework 3.5 SP1**

MED-V 主机和来宾代理以及 MED-V 工作区包装程序需要 Microsoft .NET Framework 3.5 SP1。

**重要提示** 你还必须安装更新[KB959209](https://go.microsoft.com/fwlink/?LinkId=204950) （ https://go.microsoft.com/fwlink/?LinkId=204950) ，它解决了几个已知的应用程序兼容性问题。

 

**注意** 你必须手动将 .NET Framework 3.5 SP1 和更新 KB959209 安装到你准备用于 MED-V 的 Windows 虚拟 PC 映像中。 但是，在主机上安装 Windows 7 时，默认情况下会包含 Microsoft .NET Framework 3.5 SP1 和更新。

 

**Active Directory 基础结构**

组策略提供对 Active Directory 环境中的操作系统、应用程序和用户设置的集中管理和配置。

## 相关主题


[配置安装先决条件](configure-installation-prerequisites.md)

[高级别体系结构](high-level-architecturemedv2.md)

[MED-V 2.0 支持的配置](med-v-20-supported-configurations.md)

 

 





