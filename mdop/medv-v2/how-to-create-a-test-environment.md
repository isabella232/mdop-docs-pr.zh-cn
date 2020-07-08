---
title: 如何创建测试环境
description: 如何创建测试环境
author: dansimp
ms.assetid: a0db2299-16f3-4516-8769-7d55ca4a1e98
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ee2ab131f6003b56cce7a60ffea1cd00b067fae3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804138"
---
# 如何创建测试环境


下面是一些可帮助你创建测试环境的步骤和说明，可用于在整个企业中部署你的 MED-V 工作区程序包之前进行本地测试。 本部分提供了有关如何手动或通过使用电子软件分发系统创建测试环境的指南。

**使用 ESD 创建测试环境**

1.  使用贵公司在整个企业中部署软件的方法将以下必要组件部署到测试计算机。 按以下顺序安装：

    -   **Windows 虚拟电脑**–如果尚未安装。 有关详细信息，请参阅[配置安装先决条件](configure-installation-prerequisites.md)。

    -   **Windows 虚拟 PC 的添加和更新**-如果尚未安装。 有关详细信息，请参阅[配置安装先决条件](configure-installation-prerequisites.md)。

    -   **Med-v Host Agent 安装文件**-安装主机代理（med-v \ _HostAgent \ _Setup 安装文件）。 有关详细信息，请参阅[如何手动安装 Med-v 主机代理](how-to-manually-install-the-med-v-host-agent.md)。

    -   **Med-v 工作区安装程序、VHD 和安装可执行文件**-在**Med-v 工作区包装**程序中创建。 有关详细信息，请参阅[创建 Med-v 工作区程序包](create-a-med-v-workspace-package.md)。

        **重要提示** VHD 和设置可执行程序必须与 MED-V 工作区安装程序位于同一个文件夹中。 然后，通过运行 setup.exe 安装 MED-V 工作区安装程序。

         

2.  在测试计算机上安装所有组件后，运行 MED-V 主机代理首次启动设置。

    单击 "**开始**"，单击 "**所有程序**"，单击 " **Microsoft 企业桌面虚拟化**"，然后单击 " **med-v 主机代理**"。

    **注意** 如果您无法在测试计算机上物理运行 MED-V 主机代理，则首次重新启动计算机时，安装程序将自动启动。

     

首次启动时，可能需要十分钟或更长时间才能完成。

有关在首次运行设置时测试配置设置的信息，请参阅[如何首次验证](how-to-verify-first-time-setup-settings.md)设置。

**手动创建测试环境**

1.  在包含 MED-V 先决条件的本地测试环境（如带有添加和更新的 Windows 虚拟 PC）中安装 MED-V 主机代理。 有关信息，请参阅[如何手动安装 Med-v 主机代理](how-to-manually-install-the-med-v-host-agent.md)。

2.  将 MED-V 工作区文件复制到你的测试环境。 MED-V 工作区文件位于您在**Med-v 工作区包装**程序中指定的目标文件夹中。

    **重要提示** VHD 和设置可执行程序必须与 MED-V 工作区安装程序位于测试环境的同一文件夹中。

     

3.  通过运行 setup.exe 安装 MED-V 工作区。

4.  通过运行 MED-V Host Agent 开始首次设置。

    单击 "**开始**"，单击 "**所有程序**"，单击 " **Microsoft 企业桌面虚拟化**"，然后单击 " **med-v 主机代理**"。

首次设置启动时，可能需要几分钟才能完成，具体取决于指定 VHD 的大小。

现在，你可以为你为 MED-V 工作区指定的配置、应用程序发布和 URL 重定向测试不同的设置。

**注意** 默认情况下，MED-V 会覆盖来宾中的屏幕锁定策略。 但是，这不会造成安全问题，因为主机仍然采用屏幕锁定策略。

 

## 相关主题


[如何验证首次安装设置](how-to-verify-first-time-setup-settings.md)

[如何测试应用程序发布](how-to-test-application-publishing.md)

[如何测试 URL 重定向](how-to-test-url-redirection.md)

 

 





