---
title: 如何重置 FileSystem 缓存
description: 如何重置 FileSystem 缓存
author: dansimp
ms.assetid: 7777259d-8c21-4c06-9384-9599b69f9828
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 680634d98f8aac048af605c62029a0ee6b20af03
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801127"
---
# 如何重置 FileSystem 缓存


重置文件系统缓存不是通常需要的操作。 但是，如果你需要完全重置文件系统缓存（可能是出于疑难解答目的），则可以使用以下过程。 执行此操作需要管理员权限。

**重置文件系统缓存**

1.  将以下注册表值设置为0（零）：

    HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\AppFS\\State

2.  重新启动计算机。

## 相关主题


[如何使用命令行配置 App-V Client 注册表设置](how-to-configure-the-app-v-client-registry-settings-by-using-the-command-line.md)

 

 





