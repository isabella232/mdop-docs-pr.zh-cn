---
title: 如何卸载 App-V Client
description: 如何卸载 App-V Client
author: dansimp
ms.assetid: 07591270-9651-4bb5-a5b3-e0fc009bd9e2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: acb3f53b42027ff2c1b84fd2ab2bdde3c52f96de
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801051"
---
# 如何卸载 App-V Client


使用以下过程从计算机中卸载应用程序虚拟化客户端。

**卸载应用程序虚拟化桌面客户端**

1.  在 "控制面板" 中，双击 "**添加或删除程序**" （或者在 Windows Vista 中，单击 "**程序和功能**"，然后双击 " **Microsoft Application Virtualization 桌面客户端**"。

2.  在出现的对话框中，单击 **"是"** 以继续卸载过程。

    **重要提示** 无法取消或中断卸载过程。

     

3.  如果出现一条消息，指出必须关闭 Microsoft Application Virtualization 客户端任务栏应用程序才能继续操作，请右键单击通知区域中的 app-v 图标，然后选择 "**退出**" 以关闭该应用程序。 然后单击 "**重试**" 继续卸载过程。

    **重要提示** 你可能会看到一条消息，指出正在使用一个或多个虚拟应用程序。 在继续之前，请关闭所有打开的应用程序并保存数据。 然后单击 **"确定"** 以继续卸载过程。

     

4.  进度栏显示剩余时间。 完成此步骤后，必须重新启动计算机，才能停止所有关联的驱动程序以完成卸载过程。

    **注意** 卸载过程完成后，以下注册表项仍保留：

    -   HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid

    -   HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid\\4。5

    -   HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid\\4.5\\SystemGuard "客户端" = dword：00000000

    -   HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid\\4.5\\SystemGuard\\SecKey

     

## 相关主题


[如何使用命令行安装客户端](how-to-install-the-client-by-using-the-command-line-new.md)

[如何手动安装 Application Virtualization Client](how-to-manually-install-the-application-virtualization-client.md)

[如何在客户端上发布虚拟应用程序](how-to-publish-a-virtual-application-on-the-client.md)

 

 





