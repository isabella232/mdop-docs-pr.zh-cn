---
title: 如何配置 Application Virtualization Management Server
description: 如何配置 Application Virtualization Management Server
author: dansimp
ms.assetid: a9f96148-bf2d-486f-98c2-23409bfb0935
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d6d54dd213efb8d5cbff5d0e730e6dc08c8d19b1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801579"
---
# 如何配置 Application Virtualization Management Server


必须先配置应用程序虚拟化管理服务器，然后才能将虚拟化的应用程序流式传输到应用程序虚拟化桌面客户端或客户端以用于远程桌面服务（以前称为终端服务）。 配置服务器时，将设置用于加载和存储 SFT 文件的*内容目录*。 SFT 文件包含虚拟化的应用程序（或应用程序）。

**重要提示** 应用程序虚拟化服务器使用 RTSP 或 RTSPS 协议将 SFT 文件流式传输到桌面客户端和远程桌面服务客户端。 .ICO （图标）文件和 OSD （开放软件描述符）文件可以配置为从其他文件或 HTTP 服务器流。

 

**配置应用程序虚拟化管理服务器**

1.  完成以下过程：

    [如何安装 Application Virtualization Management Server](how-to-install-application-virtualization-management-server.md)

    **注意** 在安装过程中，在 "**内容路径**" 屏幕上指定 \\Content 目录的位置。

     

2.  导航到为 \\Content 目录指定的位置，如有必要，请创建目录。

3.  创建内容目录时，将此目录配置为标准文件共享。

## 相关主题


[基于 Application Virtualization Server 的方案](application-virtualization-server-based-scenario.md)

[Application Virtualization System 要求](application-virtualization-system-requirements.md)

[基于电子软件分发的方案](electronic-software-distribution-based-scenario.md)

[如何为基于服务器的部署配置服务器](how-to-configure-servers-for-server-based-deployment.md)

 

 





