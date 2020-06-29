---
title: 如何为 IIS 配置服务器
description: 如何为 IIS 配置服务器
author: dansimp
ms.assetid: 1fcfc583-322f-4a38-90d0-e64bfa9ee3d8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9fe3367698b6f387d4467afdad1b3e17211134d6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801539"
---
# 如何为 IIS 配置服务器


在将虚拟应用程序传输到应用程序虚拟化桌面客户端和远程桌面服务客户端（以前称为终端服务）之前，必须配置 IIS 服务器。 配置服务器时，将设置用于加载和存储 SFT 文件的内容目录。 SFT 文件包含虚拟应用程序（或应用程序）。

**在 IIS 服务器上配置内容目录**

1.  在运行 IIS 的服务器上，找到要用作内容目录的目录，或者创建不存在的目录。 将此目录配置为标准文件共享。

2.  在运行 IIS 的服务器上，打开**Iis 管理器**，然后在默认网站下创建一个与您在服务器上创建的内容目录相对应的虚拟目录。 请确保已选中 "**读取**"。

3.  为新创建的虚拟目录提供别名**内容**。

4.  接受此虚拟目录的所有其他默认设置。

5.  通过使用您之前定义的 Active Directory 域服务中的安全组，在内容目录下配置对内容目录和程序包文件夹的 NTFS 文件系统权限。

**注意** 如果使用 IIS 发布 .ICO 和 OSD 文件，则必须为 OSD = TXT 配置 MIME 类型;否则，IIS 不会将 .ICO 和 OSD 文件提供给客户端。 如果使用 IIS 发布程序包（SFT 文件），则必须为 SFT = Binary 配置 MIME 类型;否则，IIS 不会将 SFT 文件提供给客户端。

 

## 相关主题


[基于 Application Virtualization Server 的方案](application-virtualization-server-based-scenario.md)

[基于电子软件分发的方案](electronic-software-distribution-based-scenario.md)

[如何配置 Application Virtualization Management Server](how-to-configure-the-application-virtualization-management-servers.md)

[如何配置 Application Virtualization Streaming Server](how-to-configure-the-application-virtualization-streaming-servers.md)

[如何配置文件服务器](how-to-configure-the-file-server.md)

 

 





