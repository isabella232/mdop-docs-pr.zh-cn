---
title: 规划 Application Virtualization Client 部署
description: 规划 Application Virtualization Client 部署
author: dansimp
ms.assetid: a352f80f-f0f9-4fbf-ac10-24c510b2d6be
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6c9fc4f29020af83a8606827015947e78761f4d7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798874"
---
# 规划 Application Virtualization Client 部署


确定如何将虚拟应用程序包发布和部署到最终用户计算机后，应规划应用程序虚拟化客户端软件的部署。

应用程序虚拟化客户端是实际运行虚拟应用程序的组件。 应用程序虚拟化客户端使用户能够与图标交互，并双击文件类型以启动虚拟应用程序。 它还处理流服务器中的应用程序内容的流式处理，并在启动应用程序之前对其进行缓存。 应用程序内容结构化，以便启动应用程序和处理初始用户交互所需的所有内容首先被流式传输到最终用户计算机。 有两种不同类型的应用程序虚拟化客户端软件：用于远程桌面服务（以前称为终端服务）的应用程序虚拟化客户端，用于远程桌面会话主机（RDSession 主机）服务器系统上的应用程序虚拟化桌面客户端，以及用于所有其他计算机的应用程序虚拟化桌面客户端。

应用程序虚拟化客户端应在安装时通过应用程序虚拟化管理控制台或通过安装程序命令行（包括以下几个重要设置）进行配置：

-   所有应用程序的图标的位置。

-   包含程序包定义信息的 OSD 文件的位置。

-   应用程序内容源。

-   检索前面的项目时要使用的通信协议。

-   要使用的缓存大小和缓存大小管理方法。

若要在使用电子软件分发（ESD）解决方案时加速应用程序虚拟化客户端软件的部署，必须提前仔细定义前面的设置。 如果你的计算机位于不同的办事处，并且需要将其客户端配置为使用不同的源位置，这一点尤其重要。

**注意**  
-   在选择发布方法时，无论使用的是 Windows Installer 还是 SFTMIME，图标位置和 OSD 文件值都是要考虑的重要因素。 应用程序内容源的设置由你选择的流式处理方法定义。

-   若要确保缓存为所有可能部署的程序包分配了足够的空间，请在配置客户端时使用 "**使用可用磁盘空间阈值**" 设置，以便缓存可以根据需要增长。 或者，提前确定应用 V 缓存所需的磁盘空间量，并在安装时设置相应的缓存大小。 有关缓存空间管理功能的详细信息，请参阅如何使用 Microsoft Application Virtualization （App-v）操作指南中**的缓存空间管理功能**。

-   在发布和 HTTP （S）流操作过程中，App-v 4.5 SP1 客户端使用在用户计算机上的 Internet Explorer 中配置的代理服务器设置。

有关配置客户端安装参数的详细信息，请参阅[应用程序虚拟化客户端安装程序命令行参数](application-virtualization-client-installer-command-line-parameters.md)。

 

最后，你需要确定如何为桌面客户端部署应用程序虚拟化桌面客户端软件。 虽然可以在每台计算机上手动部署应用程序虚拟化桌面客户端，但大多数组织都需要通过某些自动化过程来执行此操作。 中等或大型组织可能会有 ESD 系统正在运行，这将是部署客户端的理想方法。 如果不存在 ESD 系统，则可以使用你的标准方法在组织中安装软件。 选项包括组策略或各种脚本技术。 根据你拥有的办事处的数量和大小，此部署过程可能会很复杂，因此你需要采用结构化的方法来确保所有计算机获得安装了正确配置的客户端，这一点非常重要。

## 相关主题


[规划 Application Virtualization System 部署](planning-for-application-virtualization-system-deployment.md)

[如何使用命令行安装客户端](how-to-install-the-client-by-using-the-command-line-new.md)

[如何在客户端上发布虚拟应用程序](how-to-publish-a-virtual-application-on-the-client.md)

[如何升级 Application Virtualization Client](how-to-upgrade-the-application-virtualization-client.md)

[如何卸载 App-V Client](how-to-uninstall-the-app-v-client.md)

 

 





