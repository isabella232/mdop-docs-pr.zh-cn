---
title: DaRT 8.0 发行说明
description: DaRT 8.0 发行说明
author: dansimp
ms.assetid: e8b373c8-7aa5-4930-a8f9-743d26145dad
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 894708585ff4006c37085e71f365690b8424d43e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803638"
---
# DaRT 8.0 发行说明


**若要搜索这些发行说明，请按 CTRL + F。**

在安装 Microsoft 诊断和恢复工具集（DaRT）8.0 之前，请仔细阅读这些发行说明。

这些发行说明包含成功安装 DaRT 8.0 所需的信息。 发行说明还包含产品文档中不可用的信息。 如果这些发行说明和其他 DaRT 文档之间存在差异，则应将最新更改视为权威。 这些发行说明取代了本产品附带的内容。

若要获取 DaRT 软件，请参阅[如何获取 MDOP](https://go.microsoft.com/fwlink/?LinkId=322049)。

## 关于产品文档


有关 DaRT 文档的详细信息，请参阅 Microsoft TechNet 上的[DaRT 主页](https://go.microsoft.com/fwlink/?LinkID=252096)。

若要获取 DaRT 文档的可下载副本，请参阅 <https://go.microsoft.com/fwlink/?LinkID=267420> Microsoft 下载中心。

## 提供反馈


我们对 DaRT 8.0 的反馈感兴趣。 您可以向发送反馈 <mdopdocs@microsoft.com> 。

**注意** 此电子邮件地址不是支持频道，但你的反馈将帮助我们为我们的文档和产品发布计划未来的更改。

 

有关 MDOP 和其他学习资源的最新信息，请参阅[Mdop 信息体验](https://go.microsoft.com/fwlink/p/?LinkId=236032)页面。

有关新更新或提供反馈的详细信息，请在[Facebook](https://go.microsoft.com/fwlink/p/?LinkId=242445)或[Twitter](https://go.microsoft.com/fwlink/p/?LinkId=242447)上关注我们。

## DaRT 8.0 的已知问题


### 运行 Locksmith 或注册表编辑器时系统还原失败

如果您运行的是 Locksmith、注册表编辑器和其他工具，系统还原将失败。

**解决方法：** 关闭并重新启动 DaRT，然后启动 "系统还原"。

### 启动并关闭 Locksmith 或计算机管理后，无法运行 SFC 扫描

如果你开始然后关闭 Locksmith 或计算机管理工具，系统文件检查器将无法运行。

**解决方法：** 关闭并重新启动 DaRT，然后启动 SFC。

### <a href="" id="-------------dart-installer-does-not-fail-when-adk-has-not-been-installed"></a> 尚未安装 ADK 时，DaRT 安装程序不会失败

如果使用命令行执行 MSI 安装 DaRT 8.0，但尚未安装 ADK，则 DaRT 安装应该会失败。 目前，DaRT 8.0 安装程序安装了除 DaRT 8.0 恢复映像之外的所有组件。

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


[关于 DaRT 8.0](about-dart-80-dart-8.md)

 

 





