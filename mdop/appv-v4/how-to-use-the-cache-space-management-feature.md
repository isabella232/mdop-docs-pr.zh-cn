---
title: 如何使用缓存空间管理功能
description: 如何使用缓存空间管理功能
author: dansimp
ms.assetid: 60965660-c015-46a8-88ac-54cbc050fe33
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fcb9cc4bc076e1acf52fb1c03797384c45b82f7b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798965"
---
# 如何使用缓存空间管理功能


文件系统缓存空间管理功能使用最近最少使用的（LRU）算法，并且默认情况下处于启用状态。 如果新程序包所需的空间超过缓存中的可用空间，应用程序虚拟化（app-v）客户端将使用此功能来确定它可以从缓存中删除的现有程序包（如果有），以便为新程序包腾出空间。 如果上次访问日期比在 MinPkgAge 注册表值中指定的值旧，客户端将删除该程序包。 使用文件系统缓存空间管理功能还有助于避免缓存空间不足的问题。

如有必要，将删除多个软件包。 锁定的程序包不会被删除。

**注意** 若要确保缓存为所有可能部署的程序包分配了足够的空间，请在配置客户端时使用 "**使用可用磁盘空间阈值**" 设置，以便缓存可以根据需要增长。 或者，提前确定应用 V 缓存所需的磁盘空间量，并在安装时设置相应的缓存大小。

 

缓存空间管理功能由 UnloadLeastRecentlyUsed 注册表值控制。 值1启用该功能，值0（零）将禁用该功能。

**启用或禁用缓存空间管理功能**

-   将以下注册表值设置为1，以启用 LRU 算法。 将其设置为0（零）以禁用该功能。

    HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\AppFS\\UnloadLeastRecentlyUsed

**控制可以丢弃哪些程序包**

-   若要确定何时可以选择要放弃的程序包，请将以下注册表值设置为等于自上次访问程序包后所需的最少天数。 不会放弃最近使用过的程序包。

    HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\AppFS\\MinPkgAge

    **小心** 此注册表项的最大值为0x00011111。 较大值将阻止缓存空间管理功能的正确操作。

     

## 相关主题


[如何使用命令行配置 App-V Client 注册表设置](how-to-configure-the-app-v-client-registry-settings-by-using-the-command-line.md)

 

 





