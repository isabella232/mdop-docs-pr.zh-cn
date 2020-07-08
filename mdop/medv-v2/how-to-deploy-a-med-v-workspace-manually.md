---
title: 如何手动部署 MED-V 工作区
description: 如何手动部署 MED-V 工作区
author: dansimp
ms.assetid: 94bfb209-2230-49b6-bb40-9c6ab088dbf4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3f13d06e2232681f87df7a71b9a3ef3269b4f9ce
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804136"
---
# 如何手动部署 MED-V 工作区


在某些情况下，你可能希望手动部署你的 MED-V 工作区，例如，如果你的公司不使用电子软件分发系统来部署应用程序。

本部分提供了有关如何手动部署 MED-V 工作区的说明。

**手动部署 MED-V 工作区**

1.  将所有必备应用程序和 MED-V 工作区程序包文件复制到共享驱动器或 DVD。 下面列出了所需的应用程序和文件。

    -   **Windows 虚拟 PC**。 有关详细信息，请参阅[配置安装先决条件](configure-installation-prerequisites.md)。

    -   **Windows 虚拟电脑添加和更新**。 有关详细信息，请参阅[配置安装先决条件](configure-installation-prerequisites.md)。

    -   **Med-v Host Agent 安装文件**-安装主机代理（med-v \ _HostAgent \ _Setup 安装文件）。

        **警告**  
        在安装 MED-V 主机代理之前关闭 Internet Explorer，否则可能会在 URL 重定向中出现冲突。 您也可以通过在分发期间指定计算机重启来执行此操作。



~~~
-   **MED-V Workspace Installer, VHD, and Setup Executable** – created with the **MED-V Workspace Packager**. For more information, see [Create a MED-V Workspace Package](create-a-med-v-workspace-package.md).

    **Important**  
    The compressed VHD file (.medv) and the Setup executable program (setup.exe) must be in the same folder as the MED-V workspace installer.
~~~



2. 按列出的顺序安装以下。 最终用户可以手动执行此任务，也可以创建脚本来安装以下内容：

   -   Windows 虚拟电脑和 Windows 虚拟电脑的添加和更新。 需要重新启动计算机。

   -   MED-V 主机代理。

       **注意**  
       如果它正在运行，则必须重新启动 Internet Explorer，然后才能完成安装 MED-V Host Agent。



~~~
-   The MED-V workspace package.

    Install the MED-V workspace by running the setup.exe program that is included in the MED-V workspace package files.
~~~

3. 首次安装完成。

   安装 MED-V 工作区后，您可以选择启动 MED-V。 这将启动 MED-V 主机代理。 你可以在此时启动 MED-V，或者稍后启动 MED-V 主机代理以完成首次设置。

   若要启动 MED-V 主机代理，请依次单击 "**开始**"、"**所有程序**"、" **Microsoft 企业桌面虚拟化**"，然后单击 " **med-v 主机代理**"。

## 相关主题


[如何通过电子软件分发系统部署 MED-V 工作区](how-to-deploy-a-med-v-workspace-through-an-electronic-software-distribution-system.md)

[如何在 Windows 7 映像中部署 MED-V 工作区](how-to-deploy-a-med-v-workspace-in-a-windows-7-image.md)

[部署 MED-V 工作区程序包](deploying-the-med-v-workspace-package.md)









