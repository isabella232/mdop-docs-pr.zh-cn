---
title: 如何配置文件服务器
description: 如何配置文件服务器
author: dansimp
ms.assetid: 0977554c-1741-411b-85e7-7e1cd017542f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8a8971ad5c9f83dec4d0c77a16f1093ef7026b5c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801555"
---
# 如何配置文件服务器


你可以使用以下过程来配置本地计算机，该计算机用作文件共享并将应用程序流式处理到应用程序虚拟化桌面客户端和远程桌面服务（以前称为终端服务）客户端。 当你不希望向现有硬件环境添加其他服务器基础结构时，请使用此方案。

如果你使用应用程序虚拟化管理服务器作为本地办公室中安装的文件共享的分发点，则必须先配置此服务器，然后才能将虚拟应用程序流式传输到用作文件共享的计算机。 配置服务器和文件共享时，您将设置用于加载和存储 SFT 文件的内容目录。 SFT 文件包含虚拟应用程序（或应用程序）。

**重要提示** 要使应用程序能够正确地流处理到应用程序虚拟化桌面客户端和客户端以进行远程桌面服务，从存储虚拟应用程序的服务器上的内容目录中的 SFT 文件流;.ICO （图标）文件和 OSD （开放软件描述符）文件可以配置为从其他服务器流。

 

**配置应用程序虚拟化文件服务器**

1.  完成以下安装过程以配置用作分发点的服务器：

    [如何安装 Application Virtualization Management Server](how-to-install-application-virtualization-management-server.md)

    **注意** 在安装过程中，在 "**内容路径**" 屏幕上指定 \\Content 目录的位置。

     

2.  创建 \\Content 目录，该目录对应于你在用作文件共享的每台计算机上安装服务器时指定的目录。

    **重要提示** 将应用程序虚拟化桌面客户端配置为将应用程序从你用作文件共享的计算机流出，而不是从应用程序虚拟化服务器或 IIS 服务器流出。

     

3.  创建 \\Content 目录时，将此目录配置为标准文件共享。

## 相关主题


[基于 Application Virtualization Server 的方案](application-virtualization-server-based-scenario.md)

[基于电子软件分发的方案](electronic-software-distribution-based-scenario.md)

[如何配置 Application Virtualization Management Server](how-to-configure-the-application-virtualization-management-servers.md)

[如何配置 Application Virtualization Streaming Server](how-to-configure-the-application-virtualization-streaming-servers.md)

[如何为 IIS 配置服务器](how-to-configure-the-server-for-iis.md)

 

 





