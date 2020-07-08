---
title: 如何使用命令行安装客户端
description: 如何使用命令行安装客户端
author: dansimp
ms.assetid: ed372403-64ff-48ff-a3cd-a46cad04a4d5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: eca594e1399b4ca4f680f68efffcd011fdc5f042
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801371"
---
# 如何使用命令行安装客户端


本部分中的主题包括使用 setup.exe 或 setup.msi 安装应用程序虚拟化（App-v）桌面客户端或远程桌面服务（以前称为终端服务）的 App-v 客户端的过程。 需要具有管理员权限才能运行任一安装程序。

在安装期间，你可以使用可选的命令行参数对 App-v 客户端应用特定的配置设置。 有关使用参数的详细信息，请参阅[应用程序虚拟化客户端安装程序命令行参数](application-virtualization-client-installer-command-line-parameters.md)。 如果在部署客户端之前已将注册表设置应用到计算机（例如，通过使用组策略），将保留这些设置并应用任何其他命令行参数。 命令行参数值将替换相同设置的任何现有值。

**注意** 当安装与只读缓存（例如使用 VDI 服务器实现）一起使用的 app-v 客户端时，必须将*AUTOLOADTARGET*参数设置为 NONE，以防止客户端尝试在缓存为只读时尝试更新应用程序。

 

有关在安装后设置这些参数值的详细信息，请参阅[如何使用命令行](https://go.microsoft.com/fwlink/?LinkId=169355)（ https://go.microsoft.com/fwlink/?LinkId=169355) 在 Application Virtualization （App-v）操作指南中配置 App-v Client 注册表设置。

**注意** 如果用户计算机上的配置设置取决于客户端安装路径，请注意应用程序虚拟化（app-v）4.5 客户端将其安装文件复制到与以前的版本不同的文件夹中。 默认情况下，App-v 4.5 客户端的全新安装会将其安装文件复制到 \\Program Files\\Microsoft Application Virtualization Client 文件夹。 如果已安装较早版本的客户端，运行 app-v 4.5 客户端安装程序将使用现有安装文件夹执行现有客户端的升级。

 

\ [模板令牌值 \]

**注意** 对于 app-v 和更高版本，在安装 app-v 客户端时，SFTLDR.DLL 将复制到 Windows\\system32 目录。 如果在64位系统上安装了 app-v 客户端，SFTLDR\_WOW64.DLL 将复制到 Windows\\SysWOW64 目录。

 

\ [模板令牌值 \]

## 本部分内容


以下主题介绍如何使用 setup.exe 或 setup.msi 为远程桌面服务（以前称为终端服务）安装应用程序虚拟化（app-v）桌面客户端或 App-v 客户端。

<a href="" id="how-to-install-the-app-v-client-by-using-setup-exe"></a>[如何使用 Setup.exe 安装 App-V Client](how-to-install-the-app-v-client-by-using-setupexe-new.md)  
提供通过使用 setup.exe 程序安装 App-v 客户端的分步过程。

<a href="" id="how-to-install-the-app-v-client-by-using-setup-msi"></a>[如何使用 Setup.msi 安装 App-V Client](how-to-install-the-app-v-client-by-using-setupmsi-new.md)  
提供通过使用 setup.msi 程序安装任何必备软件和 App-v 客户端的分步过程。

## 相关主题


[Application Virtualization Client 安装程序命令行参数](application-virtualization-client-installer-command-line-parameters.md)

[如何手动安装 Application Virtualization Client](how-to-manually-install-the-application-virtualization-client.md)

[如何在客户端上发布虚拟应用程序](how-to-publish-a-virtual-application-on-the-client.md)

[如何卸载 App-V Client](how-to-uninstall-the-app-v-client.md)

 

 





