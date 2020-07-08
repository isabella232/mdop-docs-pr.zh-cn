---
title: 如何在 Windows 7 映像中部署 MED-V 工作区
description: 如何在 Windows 7 映像中部署 MED-V 工作区
author: dansimp
ms.assetid: a83aba4e-8681-4906-9872-f431c0bb15f9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 49dd796d6f6af425b9000b595a0d828c3cb0035a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804137"
---
# 如何在 Windows 7 映像中部署 MED-V 工作区


你可以将所有 MED-V 组件安装到你在整个企业中分发的 Windows 7 映像中，就像使用 Windows 7 的任何全新安装一样。 最终用户通过单击您配置为启动 MED-V 的 "**开始**" 菜单快捷方式来完成 med-v 工作区的安装。 首次启动设置，最终用户按照说明完成配置。

以下部分提供了可帮助你使用 Windows 7 映像在整个企业中部署 MED-V 工作区的信息和说明。

**在 Windows 7 映像中部署 MED-V 工作区**

1.  创建 Windows 7 的标准映像。 有关详细信息，请参阅[构建 Windows 7 的标准映像：分步指南](https://go.microsoft.com/fwlink/?LinkId=204843)（ https://go.microsoft.com/fwlink/?LinkId=204843) 。

2.  在 Windows 7 映像中，安装 Windows 虚拟 PC 和 Windows 虚拟电脑更新。 有关详细信息，请参阅[配置安装先决条件](configure-installation-prerequisites.md)。

3.  使用 MED-V \ _HostAgent \ _Setup 安装文件安装 MED-V 主机代理。 有关详细信息，请参阅[如何手动安装 Med-v 主机代理](how-to-manually-install-the-med-v-host-agent.md)。

    **警告** 在安装 MED-V 主机代理之前，必须关闭 Internet Explorer，否则可能会在 URL 重定向中出现冲突。 您也可以通过在分发期间指定计算机重启来执行此操作。

     

4.  将 MED-V 工作区程序包文件复制到 Windows 7 映像。 MED-V 工作区程序包文件是 MED-V 工作区安装程序、medv 文件和使用**Med-v 工作区包装**程序创建的 setup.exe 文件。

    **重要提示** Medv 和 setup.exe 文件必须与 MED-V 工作区安装程序位于同一文件夹中。 然后，通过运行 setup.exe 安装 MED-V 工作区。

     

5.  在 "**开始**" 菜单上配置快捷方式以打开 med-v 工作区程序包安装。

    创建 setup.exe 文件的 "**开始**" 菜单快捷方式，最终用户可根据需要启动 med-v 安装。

6.  通过使用贵公司的标准映像部署过程，将 Windows 7 映像分发到企业中需要 MED-V 的计算机。

当最终用户必须访问在 MED-V 工作区中发布的应用程序时，他们可以单击 "**开始**" 菜单快捷方式来安装 med-v 工作区。 这将在首次设置时自动启动，并完成 MED-V 的配置。 第一次设置完成后，最终用户可以访问 "**开始**" 菜单上的 med-v 应用程序。

## 相关主题


[MED-V 2.0 部署概述](med-v-20-deployment-overview.md)

[如何通过电子软件分发系统部署 MED-V 工作区](how-to-deploy-a-med-v-workspace-through-an-electronic-software-distribution-system.md)

 

 





