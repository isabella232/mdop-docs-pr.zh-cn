---
title: 使用电子软件分发发布虚拟应用程序
description: 使用电子软件分发发布虚拟应用程序
author: dansimp
ms.assetid: 295fbc1d-ed1c-43b4-aeee-0df384d4e630
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a0354fc1226aa78d947dd764a0ab6157b563a321
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798832"
---
# 使用电子软件分发发布虚拟应用程序


电子软件分发（ESD）系统旨在通过慢速或快速网络连接高效地将软件移动到许多不同的计算机。 通过使用 ESD 系统的应用程序虚拟化，你可以使用以下方法之一来分发你的虚拟应用程序包：

-   将您的 ESD 系统配置为使用应用程序虚拟化排序器生成的程序包的 Windows 安装程序版本将程序包直接分发到每台客户端计算机。 Windows Installer 文件包含图标、程序包定义信息和内容，当你使用 Windows Installer 时，它会将图标发布到 Windows 桌面和 "开始" 菜单，并将程序包内容加载到应用程序虚拟化客户端缓存中。 用户无需任何进一步的设置要求即可立即开始使用应用程序。 将程序包升级到较新版本是通过使用 Windows Installer 卸载 package.msi 文件，然后再安装新版本完成的。

-   将软件包内容放在通过具有良好带宽的网络连接（如 LAN）通过网络连接随时可供客户端计算机使用的软件分发点或应用程序虚拟流服务器。 例如，你可以使用每个分支机构中的现有 ESD 系统分发点计算机。 使用命令行参数定义客户端将流式处理虚拟应用程序包的流源，ESD 系统会将程序包的 Windows 安装程序版本部署到每个客户端。 ESD 系统还可以用于将包含程序包内容的 SFT 文件复制到所有流式服务器上的文件共享。 将程序包升级到较新版本是通过使用 Windows Installer 卸载 package.msi 文件，然后安装新版本完成的。

-   作为在上述模式下使用自包含的 Windows Installer 文件部署程序包的替代方法，你可以通过使用应用程序虚拟化命令行语言 SFTMIME 来更详细地控制部署。 这提供了许多命令来控制程序包管理的所有方面。 虽然 SFTMIME 非常强大，但它也非常复杂，因此管理员应计划以脚本形式创建所有命令，并在生产环境使用之前在测试环境中对其进行全面测试。 有关可用的 SFTMIME 命令的详细信息，请参阅[SFTMIME 命令参考](sftmime--command-reference.md)。

## 相关主题


[基于电子软件分发的方案](electronic-software-distribution-based-scenario.md)

[规划 Application Virtualization System 部署](planning-for-application-virtualization-system-deployment.md)

[在电子软件分发实现中计划流式处理解决方案](planning-your-streaming-solution-in-an-electronic-software-distribution-implementation.md)

[SFTMIME 命令引用](sftmime--command-reference.md)

 

 





