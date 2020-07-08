---
title: 断开连接操作模式
description: 断开连接操作模式
author: dansimp
ms.assetid: 3f9849ea-ba53-4c68-85d3-87a4218f59c6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6e9534b93f23b17e5258ef5e2d548eb93213f2f8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803005"
---
# 断开连接操作模式


已连接的操作模式设置（通过右键单击**应用程序虚拟化**节点，选择 "**属性**"，然后单击 "**连接**" 选项卡），启用远程桌面服务（以前称为终端服务）的应用程序虚拟化桌面客户端或客户端，以运行客户端无法连接到应用程序虚拟化管理服务器时存储在客户端的文件系统缓存中的应用程序。

连接到服务器失败的原因包括服务器故障、网络中断或断开网络连接。 如果发生任何故障，客户端将自动切换到断开连接的操作。 断开连接后，如果客户端需要服务器的其他数据才能继续运行应用程序，或者如果断开连接的操作超时时间已到，客户端将尝试重新连接到服务器。 如果此连接尝试失败，应用程序将关闭。

默认情况下，已启用断开连接的操作，超时设置为90天。 将超时值指定为你希望限制断开连接操作模式的天数，你可以输入1到999之间的值。

## 相关主题


[如何禁用或修改断开连接操作模式设置](how-to-disable-or-modify-disconnected-operation-mode-settings.md)

 

 





