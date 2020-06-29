---
title: 如何为断开连接操作模式配置客户端
description: 如何为断开连接操作模式配置客户端
author: dansimp
ms.assetid: 3b48464a-b8b4-494b-93e3-9a6d9bd74652
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 1c917d87996a26b330551deb04b1828c31fd3c73
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801568"
---
# 如何为断开连接操作模式配置客户端


已断开连接模式启用应用程序虚拟化（app-v）桌面客户端或应用程序虚拟化（以前称为终端服务）客户端，以便在客户端无法连接到 app-v 管理服务器时运行存储在客户端的文件系统缓存中的应用程序。

**重要提示** 在大型组织中，多个远程桌面会话主机（以前称为终端服务器）服务器（以前称为终端服务器）在服务器场中链接以支持许多用户，使用单个 App-v 管理服务器支持服务器场可表示单个故障点。 若要提供高可用性来支持 RDSession 主机场，请考虑将两个或更多个 App-v 管理服务器链接到使用同一数据库。

 

**启用断开连接的操作模式**

-   将以下注册表项的值设置为1，以启用断开连接的操作模式：

    HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Network\\AllowDisconnectedOperation

**设置断开连接操作模式使用的时间限制**

1.  将以下注册表项值设置为1：

    HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Network\\LimitDisconnectedOperation

2.  将以下注册表项值设置为要限制断开连接操作模式的分钟数。 值的有效范围为1–999999。 默认值为90天或129600分钟。

    HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Network\\DOTimeoutMinutes

**为断开连接操作模式配置远程桌面服务客户端**

1.  将以下注册表项值设置为1，以启用断开连接的操作模式：

    HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Network\\AllowDisconnectedOperation

2.  将以下注册表项值设置为0（零），以允许无限制地使用已断开的操作模式：

    HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Network\\LimitDisconnectedOperation

3.  确保将所有程序包预加载到缓存中，以提高性能。

## 相关主题


[断开连接操作模式](disconnected-operation-mode.md)

[如何使用命令行配置 App-V Client 注册表设置](how-to-configure-the-app-v-client-registry-settings-by-using-the-command-line.md)

 

 





