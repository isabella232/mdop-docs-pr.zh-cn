---
title: 如何配置 Application Virtualization Streaming Server
description: 如何配置 Application Virtualization Streaming Server
author: dansimp
ms.assetid: 3e2dde35-9d72-40ba-9fdf-d0338bd4d561
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a0ec5497b010d18bcba60e81e96cbe6334c27fb8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801571"
---
# 如何配置 Application Virtualization Streaming Server


在将虚拟应用程序流式传输到应用程序虚拟化桌面客户端或远程桌面服务客户端（以前称为终端服务）之前，必须配置应用程序虚拟化流服务器。 配置服务器时，将设置用于加载和存储 SFT 文件的*内容目录*。 SFT 文件包含虚拟应用程序（或应用程序）。

**重要提示** 应用程序虚拟化服务器使用 RTSP 或 RTSPS 协议将 SFT 文件流式传输到桌面客户端和远程桌面服务客户端。 .ICO （图标）文件和 OSD （开放软件描述符）文件可以配置为从其他文件或 HTTP 服务器流。

 

**配置应用程序虚拟化流服务器**

1.  完成应用程序虚拟化流服务器的安装过程。 在安装过程中，在 "**内容路径**" 屏幕上指定 \\Content 目录的位置。

2.  导航到你为 \\Content 目录指定的位置，如果需要，请创建目录。

3.  创建内容目录时，将此目录配置为标准文件共享。

4.  将 NTFS 文件系统权限配置为内容目录和内容目录下的程序包文件夹。 应使用 Active Directory 域服务中的安全组定义哪些用户可以访问每个应用程序。

## 相关主题


[基于 Application Virtualization Server 的方案](application-virtualization-server-based-scenario.md)

[基于电子软件分发的方案](electronic-software-distribution-based-scenario.md)

[如何配置 Application Virtualization Management Server](how-to-configure-the-application-virtualization-management-servers.md)

[如何配置文件服务器](how-to-configure-the-file-server.md)

[如何为 IIS 配置服务器](how-to-configure-the-server-for-iis.md)

 

 





