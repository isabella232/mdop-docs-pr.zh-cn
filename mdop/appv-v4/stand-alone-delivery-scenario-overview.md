---
title: 独立传递方案概述
description: 独立传递方案概述
author: dansimp
ms.assetid: b109f309-f3c1-43af-996f-2a9b138dd171
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9f29b1c8d1c9ae97f7a21498369647f31f552839
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798745"
---
# 独立传递方案概述


独立交付方案是适用于低带宽连接或无连接的环境的理想应用虚拟化解决方案，它限制了应用程序虚拟化桌面客户端从集中式服务器流出应用程序的能力。 在这些环境中，用户通常使用 Windows Installer 文件远程工作和设备所有者安装应用程序。

你可以使用应用程序虚拟化 Sequencer 创建包含 Windows Installer 文件的序列化应用程序。 这些程序包包括虚拟化应用程序、发布信息以及在客户端系统上安装程序包所需的安装程序例程。 安装程序将虚拟应用程序包添加到 Microsoft Application Virtualization 桌面客户端。 发布信息配置为从本地位置加载应用程序，而不是通过 WAN 流出它们。 用户可以暂时连接到网络以检索 Windows 安装程序文件，也可以从 DVD 运行它们。

独立交付方案为用户提供以下好处：

-   简单的部署操作。

-   在运行时不需要网络和服务器。

-   应用程序预缓存并供所有用户使用。

独立交付方案具有下列限制：

-   内置的自动报告不可用;报表必须通过外部报表工具生成。

-   应用程序必须手动发送到客户端，就像原始的 Windows 安装程序文件一样。

## 相关主题


[如何手动安装 Application Virtualization Client](how-to-manually-install-the-application-virtualization-client.md)

[如何在客户端上发布虚拟应用程序](how-to-publish-a-virtual-application-on-the-client.md)

 

 





