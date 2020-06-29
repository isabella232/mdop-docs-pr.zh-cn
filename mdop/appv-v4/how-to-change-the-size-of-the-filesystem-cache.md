---
title: 如何更改 FileSystem 缓存的大小
description: 如何更改 FileSystem 缓存的大小
author: dansimp
ms.assetid: 6ed17ba3-293b-4482-b3fa-31e5f606dad6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d63c98d53ccb31e8eb64bc70d3d79b2198c506e2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801643"
---
# 如何更改 FileSystem 缓存的大小


你可以使用命令行更改文件系统缓存的大小。 此操作需要完整地重置缓存，并且它需要管理权限。

**更改文件系统缓存的大小**

1.  将以下注册表值设置为0（零）：

    HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\AppFS\\State

2.  将以下注册表值设置为包含程序包所需的最大缓存大小（以 MB 为单位），例如，8192 MB：

    HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\AppFS\\FileSize

3.  重新启动计算机。

## 相关主题


[如何使用命令行配置 App-V Client 注册表设置](how-to-configure-the-app-v-client-registry-settings-by-using-the-command-line.md)

 

 





