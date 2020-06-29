---
title: 如何安装 Sequencer （App-v 4.6 SP1）
description: 如何安装 Sequencer （App-v 4.6 SP1）
author: dansimp
ms.assetid: fe8eb876-28fb-46ae-b592-da055107e639
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 611564e861d65dcd357c58732fb60dab21c05abe
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801351"
---
# 如何安装 Sequencer （App-v 4.6 SP1）


Microsoft Application Virtualization （App-v） Sequencer 监视和记录应用程序的安装和设置过程，以便可以将应用程序作为虚拟应用程序运行。 应在仅安装操作系统的计算机上安装 app-v 排序器。 或者，你可以在虚拟环境（如虚拟计算机）上运行的计算机上安装 Sequencer。 此方法非常有用，因为它更易于维护可使用最少的额外配置的干净的顺序环境。

你必须在用于对应用程序进行序列化的计算机上拥有管理凭据，并且计算机不得运行任何版本的 App-v 客户端。 使用 App-v Sequencer 创建虚拟应用程序需要多个操作，因此在满足或超过[应用虚拟化 Sequencer 硬件和软件要求](application-virtualization-sequencer-hardware-and-software-requirements.md)的计算机上安装 Sequencer 非常重要。

**注意**  
在安全模式下运行 app-v sequencer 不受支持。



**安装 Microsoft Application Virtualization Sequencer**

1.  将 Microsoft Application Virtualization Sequencer 安装文件复制到要在其上安装的计算机。

2.  若要启动 Microsoft Application Virtualization Sequencer 安装向导，请双击 " **Setup.exe**"。 如果在安装之前未检测到**Microsoft Visual c + + SP1 可再发行程序包（x86）** ，请单击 "**安装**" 以安装所需的先决条件。

3.  若要继续安装，请在 "**欢迎**" 页面上单击 "**下一步**"。

4.  在 "**许可协议**" 页面上，要接受许可协议的条款，请单击 **"我接受许可协议中的条款**"，然后单击 "**下一步**"。

5.  在 "**目标文件夹**" 页面上，要接受默认安装文件夹，请单击 "**下一步**"。 若要指定其他目标文件夹，请单击 "**更改**"，然后指定将用于安装的安装文件夹。 单击“下一步”****。

6.  在 "**虚拟驱动器**" 页面上，要将应用程序虚拟化默认驱动器**Q:\\** （默认）配置为运行所有序列化应用程序的驱动器，请单击 "**下一步**"。 如果要指定不同的驱动器号，请使用列表并选择要使用的驱动器号，方法是选择相应的驱动器号，然后单击 "**下一步**"。

    **重要提示**  
    通过此步骤指定的 Application Virtualization 驱动器号是虚拟应用程序将从目标计算机上运行的驱动器号。 指定的驱动器号必须可用，并且当前未在运行 App-v client 的计算机上使用。 如果指定的驱动器已在使用，则虚拟应用程序将在目标计算机上失败。



7.  在 "已**准备好安装程序**" 页面上，若要开始安装，请单击 "**安装**"。

8.  在 " **InstallShield 向导已完成**" 页面上，若要关闭安装向导并打开 app-v 排序器，请单击 "**完成**"。 若要在不打开 Sequencer 的情况下关闭安装向导，请清除 "**启动程序**"，然后单击 "**完成**"。

    **注意**  
    如果在运行虚拟环境的计算机（例如虚拟机）上安装了 app-v Sequencer，现在必须拍摄快照。 对应用程序进行排序后，你可以还原到此映像，以便对下一个应用程序进行排序。



~~~
When you uninstall the Sequencer, the following registry keys are not removed from the computer that the Sequencer was installed on. Additionally, you must restart the computer after you have uninstalled the Sequencer so that all associated drivers can be stopped and the operation can be completed.

-   **HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid**

-   **HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid\\4.5**

-   **HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid\\4.5\\SystemGuard**

-   **HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid\\4.5\\SystemGuard\\SecKey**
~~~

## 相关主题


[配置 Application Virtualization Sequencer (App-V 4.6 SP1)](configuring-the-application-virtualization-sequencer--app-v-46-sp1-.md)









