---
title: 如何使用 PowerShell 创建包加速器
description: 如何使用 PowerShell 创建包加速器
author: dansimp
ms.assetid: 0cb98394-4477-4193-8c5f-1c1773c7263a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 347572343cff058a7494574035464d66c4d61be4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798506"
---
# 如何使用 PowerShell 创建包加速器


App-v 5.1 程序包加速器自动序列大型、复杂的应用程序。 此外，当你应用 app-v 5.1 程序包加速器时，并非始终需要手动安装应用程序来创建虚拟化程序包。

**创建包加速器**

1.  安装 app-v 5.1 sequencer。 有关安装 sequencer 的详细信息，请参阅[如何安装 sequencer](how-to-install-the-sequencer-51beta-gb18030.md)。

2.  若要打开 PowerShell 控制台，请单击 "**开始**"，然后键入**powershell**。 右键单击**Windows PowerShell**，然后选择**以管理员身份运行**。 使用**AppvPackageAccelerator** cmdlet。

3.  若要创建程序包加速器，请确保你有用于创建加速器的 appv 包、安装媒体或安装文件，以及选择要使用的加速器使用者的自述文件。 要使用程序包加速器 cmdlet，需要以下参数：

    -   **InstalledFilesPath** -指定应用程序安装路径。

    -   **安装**程序-指定应用程序安装程序媒体的路径

    -   **InputPackagePath** –指定 appv 包的路径

    -   **Path** -指定程序包的输出目录。

    以下示例显示了如何创建带有 appv 包和安装媒体的程序包加速器：

    **AppvPackageAccelerator- &lt; &gt; &lt; 输出路径的安装程序可执行文件的 &gt; 路径 &lt; 目录的 appv 文件安装程序路径的 InputPackagePath 路径&gt;**

    以下列表中显示了可与**AppvPackageAccelerator** cmdlet 一起使用的其他可选参数：

    -   **AcceleratorDescriptionFile** -指定用户创建的程序包加速器说明的路径。 程序包加速器说明是将使用程序包加速器创建的程序包打包的 **.txt**或 **.rtf**说明文件。

    已**获得有关 app-v 的建议**？ 在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。 **遇到了 app-v 问题？** 使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相关主题


[使用 PowerShell 管理 App-V 5.1](administering-app-v-51-by-using-powershell.md)

 

 





