---
title: DaRT 8.0 SP1 发行说明
description: DaRT 8.0 SP1 发行说明
author: dansimp
ms.assetid: fa7512d8-fb00-4c27-8f65-c15f3a8ff1cc
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: a4c49d12fed07f507d2db4d56969d8e7b0559c64
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803635"
---
# DaRT 8.0 SP1 发行说明


**若要搜索这些发行说明，请按 CTRL + F。**

在安装 Microsoft 诊断和恢复工具集（DaRT） 8.0 Service Pack 1 （SP1）之前，请仔细阅读这些发行说明。

这些发行说明包含成功安装诊断和恢复工具集 8.0 SP1 所需的信息。 发行说明还包含产品文档中不可用的信息。 如果这些发行说明和其他 DaRT 文档之间存在差异，则应将最新更改视为权威。 这些发行说明取代了本产品附带的内容。

## 关于产品文档


有关 DaRT 文档的详细信息，请参阅 Microsoft TechNet 上的[DaRT 主页](https://go.microsoft.com/fwlink/?LinkID=252096)。

## DaRT 8.0 SP1 的已知问题


### 运行 Locksmith 或注册表编辑器时系统还原失败

如果您运行的是 Locksmith、注册表编辑器和其他工具，系统还原将失败。

**解决方法：** 关闭并重新启动 DaRT，然后启动 "系统还原"。

### 启动并关闭 Locksmith 或计算机管理后，无法运行 SFC 扫描

如果你开始然后关闭 Locksmith 或计算机管理工具，系统文件检查器将无法运行。

**解决方法：** 关闭并重新启动 DaRT，然后启动 SFC。

### <a href="" id="-------------dart-installer-does-not-fail-when-adk-has-not-been-installed"></a> 尚未安装 ADK 时，DaRT 安装程序不会失败

如果使用命令行运行 MSI 来安装 DaRT 8.0 SP1，但尚未安装 ADK，则 DaRT 安装应该会失败。 目前，DaRT 8.0 SP1 安装程序安装了除 DaRT 恢复映像之外的所有组件。

**解决方法：** 尚.

### 在 Locksmith、RegEdit、崩溃分析和计算机管理启动后，无法启动 Defender

如果你已启动 Locksmith、RegEdit、崩溃分析程序和计算机管理，则不会启动 Defender。

**解决方法：** 关闭并重新启动 DaRT，然后启动 Defender。

### 在启动时，Defender 可能会很慢

有时，Defender 需要几分钟才能启动。 进度栏指示当前加载状态。

**解决方法：** 尚.

## 发行说明版权信息


Microsoft、Active Directory、ActiveX、Bing、Excel、Silverlight、SQLServer、Windows、MicrosoftIntune 和 WindowsPowerShell 是 Microsoft 公司组的商标。 所有其他商标的所有权属于其各自所有者。



## 相关主题


[关于 DaRT 8.0 SP1](about-dart-80-sp1.md)

 

 





