---
title: 高级别体系结构
description: 高级别体系结构
author: dansimp
ms.assetid: a78e12ad-5aa6-40e0-ae8b-51acaf005712
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 00df29c751653645ab4bee9762af57576a40092a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803921"
---
# 高级别体系结构


MED-V 解决方案包含以下元素：

-   **管理员定义的虚拟机**-封装了一个完整的桌面环境，包括操作系统、应用程序以及可选的管理和安全工具。

-   **图像存储库**-通过 "修剪传输技术" 将所有虚拟图像存储在标准 IIS 服务器上，并支持虚拟图像版本管理、客户端验证的图像检索和高效下载（新映像或更新）。

-   **管理服务器**—将映像存储库中的虚拟图像和管理员使用策略关联到 Active Directory®用户或组。 管理服务器还会聚合客户端的事件，并将它们存储在外部数据库（Microsoft SQL Server®）中，用于监视和报告目的。

-   **管理控制台**-使管理员能够控制管理服务器和映像存储库。

-   **最终用户客户端**

    1.  虚拟图像生命周期-身份验证、图像检索、使用策略的实施。

    2.  虚拟机会话管理-启动、停止、锁定虚拟机。

    3.  单一桌面体验-通过标准的桌面 "开始" 菜单并与用户桌面上的其他应用程序集成，在虚拟机中安装的应用程序无缝提供。

客户端和服务器（管理服务器和映像存储库）之间的所有通信都将置于标准的 HTTP 或 HTTPS 通道顶部。

![](images/506f54d0-38fa-446a-8070-17ae26da5355.gif)

 

 





