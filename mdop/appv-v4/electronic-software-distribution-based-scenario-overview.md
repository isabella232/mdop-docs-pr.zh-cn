---
title: 基于电子软件分发的方案概述
description: 基于电子软件分发的方案概述
author: dansimp
ms.assetid: e9e94b8a-6cba-4de8-9b57-73897796b6a0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: cfbdf40f5ac0f61721c05d0da5cd49e910b16154
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803000"
---
# 基于电子软件分发的方案概述


如果您计划使用电子软件分发（ESD）解决方案来部署虚拟应用程序，请务必了解进入和受该决策影响的因素。 本主题介绍使用基于 ESD 的方案的优点，并提供有关发布和打包流方法的信息，在你继续部署时需要考虑这些方法。

**重要提示** 无论使用哪种 ESD 解决方案，您都必须熟悉特定解决方案的要求。 如果您使用的是 Microsoft 终结点配置管理器，请参阅配置管理器文档 <https://go.microsoft.com/fwlink/?LinkId=66999> 。

 

使用现有 ESD 系统可为你提供以下好处：

-   消除了双重管理基础架构

-   降低额外硬件的成本

-   降低其他操作系统和数据库许可证的成本

## 发布方法


使用基于 ESD 的方案时，你可以选择将应用程序发布到客户端：

-   **独立的 Windows Installer。** Windows Installer 文件包含客户端用于配置程序包的清单和 OSD 和 .ICO 文件。 Windows Installer 文件还将 SFT 文件复制到客户端，因为此方案不使用服务器。

-   **带有程序包清单的 Windows 安装程序。** Windows Installer 文件包含客户端用于配置程序包的清单和 OSD 和 .ICO 文件。 SFT 文件存储在服务器上。 命令行参数将客户端定向到 SFT 文件的位置。

-   **SFTMIME 命令。** SFTMIME 命令与清单、OSD、.ICO 和 SFT 文件配合使用，以向客户端添加程序包。 清单文件必须位于客户端计算机上，或者必须可通过 UNC 路径进行访问。 根据客户端配置和命令行选项，OSD、.ICO 和 SFT 文件可以位于客户端计算机上或服务器上。

有关以前发布方法的详细信息，请参阅[确定发布方法](determine-your-publishing-method.md)。

## 程序包流式处理方法


你将需要确定你的应用程序虚拟化系统将用于将虚拟应用程序包（或 SFT 文件）从服务器传输到客户端的方法。 以下流式处理选项可用：

-   **应用程序虚拟化流服务器。** 如果你在配置中使用应用程序虚拟流服务器，则将使用 RTSP 或 RTSPS 协议将 SFT 文件流到该服务器中的客户端。 必须在计算机上安装服务器软件，并且必须通过注册表配置它，但此配置不依赖于诸如 SQL 或 Active Directory 域服务之类的服务。 SFT 文件存储在服务器上由客户端访问的位置。 发布信息可通过任何分发机制分发给客户端。 但是，当配置时，客户端将自动接收程序包升级，并且支持活动升级。

-   **应用程序虚拟化管理服务器。** 如果你在配置中使用应用程序虚拟化管理服务器，则将使用 RTSP 或 RTSPS 协议将 SFT 文件流到该服务器中的客户端。 可通过应用程序虚拟化管理控制台管理此服务器。 此配置使用 SQL 数据库和 Active Directory 服务。 服务器可以将发布信息分发给客户端，因此不需要其他发布机制。

-   **文件服务器。** 如果你在配置中使用文件服务器，则将使用 SMB 协议将 SFT 文件传输到其他客户端计算机。 在此配置中使用的文件服务器通过在文件共享和 SFT 文件上创建访问控制列表（Acl）进行管理。 必须小心，才能将客户端定向到文件服务器上的正确文件。

-   **IIS 服务器。** 如果你在配置中使用 IIS 服务器，则将从该服务器使用 HTTP 或 HTTPS 协议将 SFT 文件传输到客户端。 IIS 服务器易于配置和管理。 必须小心，才能将客户端定向到 IIS 服务器上的正确文件。

有关上述流方法的更多详细信息，请参阅[确定流式处理方法](determine-your-streaming-method.md)。

## 相关主题


[Application Virtualization Client 安装程序命令行参数](application-virtualization-client-installer-command-line-parameters.md)

[基于 Application Virtualization Server 的方案](application-virtualization-server-based-scenario.md)

[确定发布方法](determine-your-publishing-method.md)

[确定流式处理方法](determine-your-streaming-method.md)

[基于电子软件分发的方案](electronic-software-distribution-based-scenario.md)

[SFTMIME 命令引用](sftmime--command-reference.md)

 

 





