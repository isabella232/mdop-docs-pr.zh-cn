---
title: App-V 4.6 SP3 发行说明
description: App-V 4.6 SP3 发行说明
author: dansimp
ms.assetid: 206fadeb-59cc-47b4-836f-191ab1c27ff8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: dd0b82c5e12cbe161066a7f4a4e0932cb92cca42
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802359"
---
# App-V 4.6 SP3 发行说明


若要搜索这些发行说明，请按 CTRL + F。

在安装 Microsoft Application Virtualization （app-v）管理系统之前，请仔细阅读这些发行说明。 这些发行说明包含的信息可帮助你成功安装应用程序虚拟化（app-v） 4.6 SP3。 本文档包含产品文档中不可用的信息。 如果这些发行说明和其他 App-v 文档之间存在差异，则应将最新更改视为权威。 这些发行说明取代了本产品附带的内容。

## 防范安全漏洞和病毒


若要帮助防范安全漏洞和病毒，请务必为正在安装的任何新软件安装最新的可用安全更新。 有关详细信息，请参阅[Microsoft 安全网站](https://go.microsoft.com/fwlink/?LinkId=3482)（ https://go.microsoft.com/fwlink/?LinkId=3482) 。

## 应用程序虚拟化 4.6 SP3 的已知问题


本部分提供有关 Microsoft Application Virtualization （app-v） 4.6 SP3 问题的最新信息。 这些问题不会显示在产品文档中，在某些情况下，可能会矛盾现有产品文档。 如果可能，这些问题将在以后的版本中解决。

### 无法在虚拟环境中使用 Microsoft Windows 8.1 上的 Internet Explorer11 打开超链接

在使用 Internet Explorer 11 的 Windows 8.1 上尝试从虚拟环境中打开超链接将失败。 这是因为 Internet Explorer 11 现在附带了默认启用的增强保护模式（EPM），这将导致 App-v 无法访问所需的注册表项、文件和通信端口对象。

解决方法：打开 App-v 程序包之前，在 Internet Explorer11 中禁用 EPM。 这将允许你从虚拟环境中打开 Internet Explorer。

## 相关主题


[关于 Microsoft Application Virtualization 4.6 SP3](about-microsoft-application-virtualization-46-sp3.md)

 

 





