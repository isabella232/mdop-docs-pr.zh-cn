---
title: MED-V 2.0 的端到端操作方案
description: MED-V 2.0 的端到端操作方案
author: dansimp
ms.assetid: 1d87f5f3-9fc5-4731-8bd1-c155714f34ee
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 90a7c2135ad27040ed87dac980b67321eb771574
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803914"
---
# MED-V 2.0 的端到端操作方案


Microsoft 企业桌面虚拟化（MED-V）2.0 的此示例方案可帮助你通过端到端使用多个方案来部署和管理 MED-V。 你可以将此示例方案视为一个案例研究，可帮助在上下文中放置单个方案和过程。

本部分提供了创建、部署和管理 MED-V 工作区的基本信息和指导，作为你企业中的端到端解决方案。

## MED-V 操作分步方案


你在 MED-V 操作方案中遵循的分步过程包括以下内容：

-   [创建用于 med-v 的 Windows 虚拟 Pc 映像](creating-a-windows-virtual-pc-image-for-med-v.md#bkmk-creatingavirtualmachinebyusingmicrosoftvirtualpc)查看如何为 med-v 创建和配置 WINDOWS 虚拟 pc 映像。 在你可以向用户提供 MED-V 工作区之前，必须先准备一个虚拟硬盘（VHD），用于为 MED-V 构建 MED-V 工作区安装程序包。

-   [创建用于 med-v 的 Windows 虚拟 Pc 映像](creating-a-windows-virtual-pc-image-for-med-v.md#bkmk-installingwindowsxpontovpc)查看如何在 WINDOWS 虚拟 pc 映像上安装 WINDOWS XP SP3 操作系统。 在构建 MED-V 工作区之前，MED-V 要求在 Windows 虚拟 PC 映像上安装 Windows XP SP3。

-   [创建用于 med-v 的 Windows 虚拟 Pc 映像](creating-a-windows-virtual-pc-image-for-med-v.md#bkmk-installingnet)查看如何将 .net FRAMEWORK 3.5 SP1 和更新 KB959209 手动安装到你准备用于 Med-v 的 WINDOWS 虚拟 pc 映像中。 MED-V 需要 .NET Framework 3.5 SP1 和更新[KB959209](https://go.microsoft.com/fwlink/?LinkId=204950) （ https://go.microsoft.com/fwlink/?LinkId=204950) 解决几个已知的应用程序兼容性问题。

-   [创建用于 med-v 的 Windows 虚拟 PC 映像](creating-a-windows-virtual-pc-image-for-med-v.md#bkmk-applypatchestovpc)查看如何使用最新的软件更新以及运行 med-v 所需的其他修补程序（重要）更新 windows XP 映像。

-   [创建用于 med-v 的 Windows 虚拟 PC 映像](creating-a-windows-virtual-pc-image-for-med-v.md#bkmk-installintegration)查看如何在 Windows XP 映像中安装集成组件程序包。 这些功能提供了改进虚拟环境和物理计算机之间的交互的功能。

-   [在 Windows 虚拟 PC 映像上安装应用程序](installing-applications-on-a-windows-virtual-pc-image.md)查看如何在 windows XP 映像上安装某些类型的软件，这些软件在你运行 med-v （如电子软件分发系统和防病毒软件）时非常有用。

-   [为 Med-v 配置 Windows 虚拟 PC 映像](configuring-a-windows-virtual-pc-image-for-med-v.md)介绍如何使用 Sysprep 来配置映像，以确保它可以与 med-v 配合使用。 然后，使用准备好的 MED-V 图像创建 MED-V 工作区程序包。

-   [创建 Med-v 工作区程序包](create-a-med-v-workspace-package.md)查看如何构建在整个企业中部署的 med-v 工作区程序包。 部署 MED-V 工作区程序包以在最终用户计算机上安装 MED-V 工作区。 MED-V 工作区是最终用户与由 MED-V 提供的虚拟机交互的 Windows XP 桌面环境。

-   [测试 Med-v 工作区程序包](testing-the-med-v-workspace-package.md)介绍如何创建可在其中测试 med-v 工作区程序包功能的测试环境，例如首次设置设置和应用程序发布。 在完成对 MED-V 工作区程序包的测试并验证它是否按预期运行后，您可以在整个企业中部署它。

-   [部署 Med-v 工作区程序包](deploying-the-med-v-workspace-package.md)讨论如何使用电子软件分发系统或在 Windows 7 映像中部署 med-v 工作区。 或者，如果你愿意，此部分还会向你介绍如何手动部署 MED-V 工作区。

-   [监视 Med-v 工作区](monitor-med-v-workspaces.md)查看如何监视 med-v 工作区的部署，以确定首次设置是否成功完成。 监视首次设置是否成功是很重要的，因为在首次安装成功完成之前，MED-V 未处于可用状态。 此部分还介绍了如何设置你的环境，以检测可能影响 MED-V 的网络更改。

-   [管理 Med-v 工作区应用程序](manage-med-v-workspace-applications.md)查看如何在已部署的 med-v 工作区上安装和删除或发布和取消发布应用程序。 本部分还介绍了如何在 MED-V 工作区中手动更新软件以及如何管理自动更新。 MED-V 工作区是包含单独操作系统的虚拟机，该操作系统的自动软件更新过程必须与企业中的物理计算机完全一样。

-   [管理 MED-V URL 重定向](manage-med-v-url-redirection.md)查看如何在已部署的 med-v 工作区中添加和删除 web 地址重定向设置。 你可以通过注册表或通过重建 MED-V 工作区来添加或删除 URL 重定向信息。 你还可以使用 MED-V 工作区包装程序上的向导管理 web 地址重定向。

-   [管理 Med-v 工作区设置](manage-med-v-workspace-settings.md)查看如何使用 Med-v 工作区包装程序查看和编辑 med-v 配置设置。 此部分列出了所有可配置的 MED-V 注册表项，包括每个的类型、默认和说明。 本节还包括有关如何管理 MED-V 工作区中的打印机的信息。 在 MED-V 2.0 中，打印机重定向使用户在 MED-V 虚拟机和主机之间具有一致的打印体验。

## 相关主题


[MED-V 的操作](operations-for-med-v.md)

[MED-V 2.0 的端到端规划方案](end-to-end-planning-scenario-for-med-v-20.md)

[MED-V 2.0 的端到端部署方案](end-to-end-deployment-scenario-for-med-v-20.md)

 

 





