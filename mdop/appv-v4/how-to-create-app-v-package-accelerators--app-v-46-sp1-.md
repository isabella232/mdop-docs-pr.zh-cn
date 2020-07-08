---
title: 如何创建 App-V 包加速器 (App-V 4.6 SP1)
description: 如何创建 App-V 包加速器 (App-V 4.6 SP1)
author: dansimp
ms.assetid: 585e692e-cebb-48ac-93ab-b2e7eb7ae7ad
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: eb806ccf04fcd5ae7db87c5de21e85217739fcbc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801496"
---
# 如何创建 App-V 包加速器 (App-V 4.6 SP1)


你可以使用 App-v 程序包加速器自动生成新的虚拟应用程序包。 成功创建程序包加速器后，您可以重复使用和共享程序包加速器。 有关软件包加速器的详细信息，请参阅[关于 App-v 程序包加速器（app-v 4.6 SP1）](about-app-v-package-accelerators--app-v-46-sp1-.md)。 创建 App-v 包加速器是一种高级任务。 程序包加速器可以包含密码和特定于用户的信息。 因此，你必须将程序包加速器和关联的安装媒体保存在一个安全位置，并且你应对程序包加速器进行数字签名，以便在应用 V 程序包加速器应用时可以验证发布者。

在某些情况下，若要创建程序包加速器，可能需要在运行 Sequencer 的计算机上本地安装应用程序。 首先尝试使用安装媒体创建程序包加速器，如果有多个缺少的文件，请在运行 Sequencer 的计算机本地安装应用程序，然后创建程序包加速器。

**重要提示**  
开始执行以下过程之前，应执行下列操作：

-   将你必须使用的虚拟应用程序包复制到运行 Sequencer 的计算机本地创建程序包加速器。

-   将与虚拟应用程序包相关联的所有所需安装文件复制到运行 Sequencer 的计算机。



**重要提示**  
免责声明： Microsoft Application Virtualization Sequencer 不向你提供用于创建程序包加速器的软件应用程序的许可证权利。 您必须遵守此类应用程序的所有最终用户许可条款。 您有责任确保软件应用程序的许可条款允许您使用 Application Virtualization Sequencer 创建软件包加速器。



**创建 App-v 包加速器**

1.  若要启动 app-v 排序器，请在运行 app-v 排序器的计算机上，单击 "**启动**  /  **所有程序**  /  **microsoft application virtualization**  /  **microsoft application virtualization Sequencer**"。

2.  若要启动 app-v**创建包加速器**向导，请在 app-v 排序器中单击 "**工具**  /  **创建包加速器**"。

3.  在 "**选择程序包**" 页面上，若要指定要用于创建程序包加速器的现有虚拟应用程序包，请单击 "**浏览**"，然后找到现有虚拟应用程序包（sprj 文件）。

    **提示**  
    将与你计划要使用的虚拟应用程序包关联的文件复制到运行 Sequencer 的计算机。



~~~
Click **Next**.
~~~

4. 在 "**安装文件**" 页面上，若要指定包含用于创建原始虚拟应用程序包的安装文件的文件夹，请单击 "**浏览**"，然后选择包含安装文件的目录。

   **提示**  
   将包含所需安装文件的文件夹复制到运行 Sequencer 的计算机。



~~~
If the application is already installed on the computer running the Sequencer, to specify the installation file, select **Files installed on local system**. To use this option, the application must already be installed in the default installation location.
~~~

5. 在 "**收集信息**" 页面上，查看在此向导的 "**安装文件**" 页面上指定的位置中未找到的文件。 如果显示的文件不是必需的，请选择 "**删除这些文件**"，然后单击 "**下一步**"。 如果需要这些文件，请单击 "**上一步**"，然后将所需的文件复制到 "**安装文件**" 页面上指定的目录中。

   **注意**  
   必须删除 unrequired 文件，或单击 "**上一**步"，然后找到所需的文件以转到此向导的下一页。



6. 在 "**选择文件**" 页面上，仔细查看检测到的文件，并清除应从程序包加速器中删除的任何文件。 仅选择应用程序成功运行所需的文件，然后单击 "**下一步**"。

7. 在 "**验证应用程序**" 页面上，确认显示生成程序包所需的所有安装文件。 当程序包加速器用于创建新程序包时，必须在 "**应用程序**" 窗格中显示所有安装文件才能创建程序包。

   如有必要，要添加其他安装程序文件，请单击 "**添加**"。 若要删除不需要的安装文件，请选择安装程序文件，然后单击 "**删除**"。 若要编辑与安装程序相关联的属性，请单击 "**编辑**"。 当程序包加速器用于创建新的虚拟应用程序包时，将需要在此步骤中指定的安装文件。 确认所显示的信息后，单击 "**下一步**"。

8. 在 "**选择指南**" 页面上，若要指定包含程序包加速器相关信息的文件，请单击 "**浏览**"。 例如，此文件可以包含有关运行 Sequencer 的计算机的配置、目标计算机的应用程序必备信息以及常规注释的信息。 你应提供要成功应用的程序包加速器所需的所有信息。 所选文件必须是 rtf （.rtf）或文本文件（.txt）格式。 单击“下一步”****。

9. 在 "**创建包加速器**" 页面上，若要指定程序包加速器的保存位置，请单击 "**浏览**" 并选择目录。

10. 在**完成**页上，若要关闭 "**创建程序包加速器**" 向导，请单击 "**关闭**"。

   **重要提示**  
   为了帮助确保程序包加速器尽可能安全，并且可以在应用包加速器时验证发布者，你应该始终对程序包加速器进行数字签名。



## 相关主题


配置应用程序虚拟化排序器（App-v 4.6 SP1）[如何应用程序包加速器以创建虚拟应用程序包（app-v 4.6 SP1）](how-to-apply-a-package-accelerator-to-create-a-virtual-application-package---app-v-46-sp1-.md)









