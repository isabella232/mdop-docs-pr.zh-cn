---
title: 如何手动安装 MED-V 主机代理
description: 如何手动安装 MED-V 主机代理
author: dansimp
ms.assetid: 4becc90b-6481-4e1f-a4d3-aec74c8821ec
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8a7fb44b23a390cf394af2331152955afc2d8eba
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798160"
---
# 如何手动安装 MED-V 主机代理


Microsoft 企业桌面虚拟化（MED-V）2.0 解决方案有两个独立但相关的组件： "MED-V 主机代理" 和 "来宾代理"。 主机代理驻留在主机（运行 Windows 7 的用户计算机）上，并提供信道以与 MED-V 来宾（在主机计算机上运行的 MED-V 虚拟机）通信。 它还提供某些与 MED-V 相关的功能，例如应用程序发布。

通常情况下，使用贵公司的预配软件的首选方法部署和安装 MED-V 主机代理。 但是，在你的企业内部署 MED-V 之前，你可能希望在本地安装主机代理以进行测试。 本部分提供了手动安装 MED-V 主机代理的分步说明。

**注意** MED-V 来宾代理将在首次设置时自动安装。

 

**重要提示** 在安装 MED-V 主机代理之前关闭 Internet Explorer，否则可能会在 URL 重定向中出现冲突。 您也可以通过在分发期间指定计算机重启来执行此操作。

 

**安装 MED-V 主机代理**

1.  找到你在软件下载中收到的 MED-V 安装文件。

2.  双击 "MED-V \ _HostAgent \ _Setup 安装文件"。

    **Microsoft 企业桌面虚拟化（med-v） Host Agent 安装**向导随即打开。 单击**下一步**以继续。

3.  接受 Microsoft 软件许可条款，然后单击 "**下一步**"。

4.  选择用于安装 MED-V 主机代理的目标文件夹。 单击“下一步”****。

5.  若要开始安装 Host Agent，请单击 "**安装**"。

6.  安装成功完成后，单击 "**完成**" 关闭向导。

    若要验证主机代理的安装是否成功，请依次单击 "**开始**"、"**所有程序**"、" **Microsoft 企业桌面虚拟化**"，然后单击 " **med-v 主机代理**"。

**注意** 在安装 MED-V 工作区之前，MED-V 主机代理可以启动并运行，但不提供任何功能。

 

## 相关主题


[如何通过电子软件分发系统部署 MED-V 组件](how-to-deploy-the-med-v-components-through-an-electronic-software-distribution-system.md)

[如何安装 MED-V 工作区包装程序](how-to-install-the-med-v-workspace-packager.md)

[如何卸载 MED-V 组件](how-to-uninstall-the-med-v-components.md)

 

 





