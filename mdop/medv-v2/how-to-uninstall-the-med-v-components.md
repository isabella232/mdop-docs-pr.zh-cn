---
title: 如何卸载 MED-V 组件
description: 如何卸载 MED-V 组件
author: dansimp
ms.assetid: c121dd27-6b2f-4d41-a21a-c6e8608c5c41
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 514ec8227b858b34289ca2330f7cfb038bc4f00e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798193"
---
# 如何卸载 MED-V 组件


在某些情况下，你可能需要从你的企业卸载 Microsoft 企业桌面虚拟化（MED-V）2.0 组件的全部或部分。 例如，你已解决所有应用程序操作系统兼容性问题，或者你希望在你的企业中部署不同的 MED-V 工作区。

通常，你可以通过使用基于 Windows 的安装程序配置电子软件分发（ESD）系统以卸载 MED-V 组件。 或者，您也可以手动卸载所有或部分 MED-V 组件。

**重要提示** 必须先卸载任何已安装的 MED-V 主机代理，然后才能卸载 MED-V 主机代理。

 

使用以下过程从您的企业版卸载 MED-V 组件。

**使用电子软件分发系统卸载 MED-V**

1.  使用 ESD 系统分发一个脚本，该脚本为要卸载的每个 MED-V 工作区调用 uninstall.exe 的可执行程序。 文件位于 C:\\ProgramData\\Microsoft\\Medv\\Workspace。 你可以设置一个标志以自动运行卸载可执行程序，以便最终用户不知道卸载。

2.  创建一个程序包，以便将 MED-V 主机代理安装文件分发到卸载了 MED-V 工作区的每台计算机。 将程序包配置为在静默模式下运行卸载。

ESD 客户端识别新程序包何时可用，并开始根据定义和要求卸载程序包。

**手动卸载 MED-V 工作区**

1.  在主计算机上，单击 "**开始**"，单击 "**控制面板**"，然后单击 "**程序和功能**"。

2.  在 "**程序和功能**" 窗口中，选择要删除的 med-v 工作区，然后单击 "**卸载**"。 （MED-V 工作区名为 "MED-V-V 工作区- &lt;*工作区 \ _name* &gt; "）。 将 &lt; 打开 "*工作区 \ _name* &gt; **安装向导**"。

3.  在**设置向导**中，单击 "**下一步**"，然后单击 "**删除**"。

4.  如果你愿意，请选中复选框以删除主 VHD 磁盘和由 MED-V 创建的差异磁盘。 这不是必需的，但在卸载完成后将释放磁盘空间。

5.  单击 "**删除**"。

    **注意** 如果 MED-V 当前正在运行，则会出现一个对话框，提示您是否要将其关闭。 单击 **"是"** 以继续卸载。 单击 "**否**" 取消卸载。

     

或者，也可以通过运行 `uninstall.exe` 文件（通常位于 C:\\ProgramData\\Microsoft\\Medv\\Workspace. 上）来删除 med-v 工作区。

**手动卸载 MED-V 主机代理**

1.  在 Windows 7 主机计算机上，单击 "**开始**"，单击 "**控制面板**"，然后单击 "**程序和功能**"。

2.  在 "**程序和功能**" 窗口中，选择 " **med-v Host Agent**"，然后单击 "**卸载**"。

    Windows Installer 将删除 MED-V 主机代理。

    **注意** 如果您在卸载 MED-V 工作区之前尝试卸载 MED-V 主机代理，则会出现一个对话框，指明必须首先卸载 MED-V 工作区。 单击**确定**继续。

     

**手动卸载 MED-V 工作区包装程序**

1.  在主计算机上，单击 "**开始**"，单击 "**控制面板**"，然后单击 "**程序和功能**"。

2.  在 "**程序和功能**" 窗口中，选择 " **Med-v-V 工作区包装**程序"，然后单击 "**卸载**"。

    Windows 安装程序删除了 MED-V 工作区包装程序。

    **注意** 你可以随时卸载 MED-V 工作区包装程序，而不会影响任何已部署的 MED-V 工作区。

     

## 相关主题


[部署 MED-V 组件](deploy-the-med-v-components.md)

 

 





