---
title: 为 App-V Server 配置防火墙
description: 为 App-V Server 配置防火墙
author: dansimp
ms.assetid: f779c450-6c6f-46a8-ac66-5e82e0689d55
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 92db727eb060546ab71f2c647f2d89b662be5c64
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803044"
---
# 为 App-V Server 配置防火墙


安装 Microsoft Application Virtualization （app-v）管理服务器或流服务器并将其配置为使用 RTSP 或 RTSPS 协议后，必须为 App-v 程序创建防火墙例外。

## 配置应用程序虚拟化管理服务器的防火墙例外


为**sghwdsptr.exe**和**sghwsvr.exe**创建防火墙例外。 这些程序位于32位操作系统上的 "C:\\program files Files\\Microsoft System Center App Virt 管理 Server\\App Virt 管理 Server\\bin" 文件夹中。 如果您使用的是64位操作系统版本，则该文件夹位于 C:\\program files Files （x86）下 \\Microsoft System Center App Virt Management Server\\App Virt 管理 Server\\bin。

## 配置应用程序虚拟化流服务器的防火墙例外


为**sglwdsptr.exe**和**sglwsvr.exe**创建防火墙例外。 在32位操作系统上 Virt 流 Server\\App Virt 流 Server\\bin 的文件夹 C:\\program files Files\\Microsoft System Center App 中可以找到这些程序。 如果您使用的是64位操作系统版本，则该文件夹位于 C:\\program files Files （x86）下 \\Microsoft System Center App Virt 流 Server\\App Virt 流 Server\\bin。

## 相关主题


[如何为基于服务器的部署配置服务器](how-to-configure-servers-for-server-based-deployment.md)

[如何安装和配置默认应用程序](how-to-install-and-configure-the-default-application.md)

 

 





