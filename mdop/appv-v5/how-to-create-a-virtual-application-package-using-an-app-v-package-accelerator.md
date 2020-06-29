---
title: 如何使用 App-V 包加速器创建虚拟应用程序包
description: 如何使用 App-V 包加速器创建虚拟应用程序包
author: dansimp
ms.assetid: 715e7526-e100-419c-8fc1-75cbfe433835
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 547cb93f334e025243937a97a1f904410fe2d504
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798503"
---
# 如何使用 App-V 包加速器创建虚拟应用程序包


**重要提示**  
App-v 5.0 Sequencer 不会向你用于创建包加速器的软件应用程序授予任何许可证权限。 你必须遵守你使用的应用程序的所有最终用户许可条款。 您有责任确保软件应用程序的许可条款允许您使用 App-v 5.0 Sequencer 创建软件包加速器。



使用以下过程创建带有 App-v 5.0 程序包加速器的虚拟应用程序包。

**注意**  
在开始此过程之前，请将所需的软件包加速器本地复制到运行 app-v 5.0 Sequencer 的计算机。 你还应将程序包所需的所有安装文件复制到运行 Sequencer 的计算机上的本地目录。 这是你必须在此过程的步骤5中指定的目录。



**使用 app-v 5.0 程序包加速器创建虚拟应用程序包**

1.  若要启动 app-v-sequencer，请在运行 app-v 5.0 Sequencer 的计算机上，单击 "**启动**  /  **所有程序**  /  **microsoft application virtualization**  /  **microsoft application virtualization Sequencer**"。

2.  若要启动 "**创建新程序包" 向导**，请单击 "**创建新的虚拟应用程序包**"。 若要创建程序包，请选中 "**使用包加速器创建程序包**" 复选框，然后单击 "**下一步**"。

3.  若要指定将用于创建新虚拟应用程序包的程序包加速器，请单击 "**选择包加速器**" 页面上的 "**浏览**"。 单击“下一步”****。

    **重要提示**  
    如果无法验证程序包加速器的发布者，并且它不包含有效的数字签名，则必须确认你信任程序包加速器的源，然后再单击 "**运行**"。 在 "**安全警告**" 对话框中确认您的选择。



4.  在 "**指南**" 页上，查看 "信息" 窗格中显示的发布指南信息。 此信息是在创建程序包加速器时添加的，它包含有关如何创建和发布程序包的指南。 若要将指南信息导出到文本（.txt）文件，请单击 "**导出**"，指定应保存该文件的位置，然后单击 "**下一步**"。

5.  在 "**选择安装文件**" 页面上，单击 "创建**新文件夹**" 以创建一个本地文件夹，其中包含程序包所需的所有安装文件，并指定应保存文件夹的位置。 还必须指定要分配给文件夹的名称。 然后，您必须将所有所需的安装文件复制到您指定的位置。 如果包含安装文件的文件夹已存在于运行 Sequencer 的计算机上，请单击 "**浏览**" 以选择该文件夹。

    或者，如果已将安装文件复制到此计算机上的目录中，请单击 "**新建文件夹**"，浏览到包含安装文件的文件夹，然后单击 "**下一步**"。

    **注意**  
    你可以指定以下支持的安装文件类型：

    -   Windows Installer 文件（**.msi**）

    -   Cabinet 文件（.cab）

    -   文件扩展名为 .zip 的压缩文件

    -   实际应用程序文件

    不支持以下文件类型： **.msp**和 **.exe**文件。 如果指定 **.exe**文件，则必须手动解压缩安装文件。



~~~
If the package accelerator requires an application to be installed before you apply the Package Accelerator, and if you have already installed the required application, select **I have installed all applications**, and then click **Next** on the **Local Installation** page.
~~~

6. 在 "**程序包名称**" 页面上，指定将与程序包关联的名称。 你指定的名称在 App-v 管理控制台中标识程序包。 单击“下一步”****。

7. 在 "**创建程序包**" 页面上，提供将与程序包相关联的注释。 注释应包含有关正在创建的程序包的标识信息。 若要确认创建程序包的位置，请查看 "**保存位置**" 中显示的信息。 若要压缩程序包，请选择 "**压缩包**"。 如果要跨网络传输包，或者程序包大小超过 4 GB，请选中 "**压缩包**" 复选框。

   若要创建程序包，请单击 "**创建**"。 创建程序包后，单击 "**下一步**"。

8. 在 "**配置软件**" 页面上，若要启用排序器来配置程序包中包含的应用程序，请选择 "**配置软件**"。 在此步骤中，你可以配置必须完成的任何关联任务，以便在目标计算机上运行应用程序。 例如，您可以配置任何相关的许可协议。

   如果选择 "**配置软件**"，则可以使用 Sequencer 作为此步骤的一部分配置以下项：

   -   **加载程序包**。 Sequencer 将加载与该包关联的文件。 解码程序包可能需要几秒钟到一小时。

   -   **运行每个程序**。 （可选）运行程序包中包含的程序。 此步骤有助于完成在目标计算机上部署和运行程序包之前运行应用程序所需的任何相关许可证或配置任务。 若要一次运行所有程序，请选择至少一个程序，然后单击 "**全部运行**"。 若要运行特定程序，请选择要运行的一个或一些程序，然后单击 "**运行所选**"。 完成所需的配置任务，然后关闭应用程序。 运行所有程序可能需要几分钟的时间。 单击“下一步”****。

   -   **保存程序包**。 Sequencer 将保存包。

   -   **主要功能块**。 Sequencer 通过重新生成主功能块来优化流包。

   如果您不想配置应用程序，请单击 "**跳过此步骤**"，转到此过程的步骤9，然后单击 "**下一步**"。

9. 在 "**完成**" 页面上，查看 "**虚拟应用程序包报告**" 窗格中显示的信息后，单击 "**关闭**"。

   程序包现在在 Sequencer 中可用。 若要编辑程序包属性，请单击 "**编辑 \ [包名称 \]**"。 有关如何修改程序包的详细信息，请参阅[如何修改现有虚拟应用程序包](how-to-modify-an-existing-virtual-application-package-beta.md)。

   已**获得有关 app-v 的建议**？ 在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。 **遇到了 app-v 问题？** 使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相关主题


[App-V 5.0 的操作](operations-for-app-v-50.md)









