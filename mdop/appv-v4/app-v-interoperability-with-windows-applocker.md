---
title: App-V 与 Windows AppLocker 的互操作性
description: App-V 与 Windows AppLocker 的互操作性
author: dansimp
ms.assetid: 9a488034-607d-411c-b495-ff184c726f49
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 6f67bb87c0a4474acee3c4982b65c930e86c4917
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803143"
---
# App-V 与 Windows AppLocker 的互操作性


Microsoft Application Virtualization （app-v）客户端的版本 4.5 SP1 支持 Windows 7 的 AppLocker 功能。 AppLocker 功能使 IT 管理员能够指定限制哪些应用程序在计算机上运行。 本文档介绍如何将 AppLocker 规则配置为使用 App-v 虚拟环境和虚拟化应用程序。

**注意** 在为虚拟应用程序配置 Windows AppLocker 规则之前，必须首先启用 Windows AppLocker。 有关启用 Windows AppLocker 的详细信息， [Windows applocker](https://go.microsoft.com/fwlink/?LinkId=156732) （ https://go.microsoft.com/fwlink/?LinkId=156732) 。

 

## 为虚拟应用程序配置 Windows AppLocker 规则


本地管理员可以创建 Windows AppLocker 规则，这些规则限制程序可执行文件（.exe 文件）、Windows Installer 文件（.msi 和 .msp 文件）以及脚本（.ps、.bat、.cmd 和 .js 文件）的运行。 管理员通过使用安装了 App-v 客户端的引用计算机并将所有相关虚拟应用程序流入到客户端缓存来执行此操作。 管理员然后使用参考计算机上的本地安全策略 Microsoft 管理控制台（MMC）管理单元的 Windows AppLocker 部分创建规则。

当您浏览以找到要为其创建规则的目录路径或特定文件时，您可以使用隐藏共享的路径访问 app-v 驱动器。 例如，你可以浏览到 \\\\localhost\\Q $，其中 app-v 驱动器是 drive Q。但是，若要创建规则，必须编辑路径以删除对 \\\\localhost\\Q $ 的引用并改用 Q:\\。 必须在引用计算机上启动每个应用程序才能访问应用程序的文件，并且需要具有管理权限才能浏览 \\\\localhost\\Q $。

 

 





