---
title: 如何加载文件和程序包
description: 如何加载文件和程序包
author: dansimp
ms.assetid: f86f5bf1-99a4-44d7-ae2f-e6049c482f68
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9427fd8089ec9c22d7d379b15ae94bf421ca2d44
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801336"
---
# 如何加载文件和程序包


你可以使用以下过程在应用程序虚拟化服务器上加载文件和程序包。

**注意** 在安装过程中，你在 "**内容路径**" 页面上指定了 \\Content 目录的位置。 在指向该目录的位置之前，应创建并将其配置为标准文件共享。

 

**加载文件和程序包**

1.  在要将应用程序流式传输到的计算机上，导航到您为 \\Content 目录指定的位置。 如有必要，请创建目录并将其配置为标准文件共享。

2.  将虚拟应用程序和程序包的 SFT 文件移动到 \\Content 目录。 若要使 SFT 文件保持井然有序并避免混淆，请将应用程序和程序包放在专用子文件夹中。

3.  根据你的方案和配置的要求加载应用程序和程序包，考虑以下情况：

    -   如果你的应用程序和程序包存储在应用程序虚拟化（App-v）管理服务器上，请通过管理控制台加载它们。 有关详细信息，请参阅[如何加载或卸载应用程序](how-to-load-or-unload-an-application.md)或[如何从桌面通知区域加载虚拟应用程序](how-to-load-virtual-applications-from-the-desktop-notification-area.md)。

    -   如果你的应用程序存储在 app-v 流服务器、Web 服务器或配置为文件服务器的计算机上，则可以自动加载应用程序。

        **注意** App-v 流处理服务器将自动轮询 \\Content 目录以查找应用程序和程序包，并将此信息放入内存以服务应用程序请求。

        必须正确配置 app-v 客户端，才能从 Web 服务器和文件服务器检索应用程序和程序包。 有关详细信息，请参阅[如何为应用程序包检索配置客户端](how-to-configure-the-client-for-application-package-retrieval.md)。

         

## 相关主题


[Application Virtualization Server](application-virtualization-server.md)

 

 





