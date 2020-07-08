---
title: 如何配置部署包
description: 如何配置部署包
author: dansimp
ms.assetid: 748272a1-6af2-476e-a3f1-87435b8e94b1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: aba5e91a4da92f9e51a5ccc70502658ae724d76f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803870"
---
# 如何配置部署包


打包向导将引导你完成程序包创建，方法是在本地计算机上创建一个文件夹，并将所有所需的安装文件转移到单个文件夹。 然后，可将该文件夹的内容移动到多个可移动媒体驱动器进行分发。

**注意**  
单个程序包不能包含 x86 和 x64 系统的安装文件。



## 如何创建部署包


**创建部署包**

1. 在 "**映像**" 模块中验证你已创建了至少一个本地打包的映像。

2. 在 "**工具**" 菜单上，选择 "**打包向导**"。

3. 在 "**打包向导**" 欢迎页面上，单击 "**下一步**"。

4. 在 "**工作区图像**" 页面上，选中 "**在程序包中包含图像**" 复选框以在程序包中包含图像。

   "**图像**" 字段已启用。

   **注意**  
   不需要在 MED-V 程序包中使用图像;可以创建不带映像的程序包。 在这种情况下，应将图像上载到服务器，以便以后可以通过网络将其下载到客户端，或者将其推送到 "图像预暂存" 文件夹。



5. 单击**图像**列表以查看所有可用图像。 选择要复制到程序包的图像。 单击 "**刷新**" 以刷新可用图像的列表。

6. 单击“下一步”****。

7. 在 " **Med-v 安装设置**" 页面上，通过执行下列操作之一选择 med-v 安装文件：

   -   在 " **med-v 安装文件**" 字段中，键入安装文件所在目录的完整路径。

   -   单击 " **...** " 浏览到安装文件所在的目录。

   **注意**  
   此字段是必需的，并且如果没有有效的文件名，向导将不会继续。



8. 在 "**服务器地址**" 字段中，键入服务器名称或 IP 地址。

9. 在 "**服务器端口**" 字段中，键入服务器端口。

10. 选中 "**使用 https 访问服务器**" 复选框，以要求 https 连接连接到服务器。

11. 执行下列操作之一：

    -   单击 "**默认安装设置**"，然后单击 "**下一步**" 继续并保留默认设置。

    -   单击 "**自定义安装设置**"，然后单击 "**下一步**" 以自定义安装设置。

        1.  在 " **Med-v 安装" 自定义设置**页面上的 "**安装文件夹**" 字段中，键入将在主机计算机上安装 med-v 文件的文件夹的路径。

            **注意**  
            建议在路径（而不是常量）中使用变量，这可能会因计算机而异。

            例如，使用 *%ProgramFiles%\\MED-V*而不是*c:\\MED-V*。



    ~~~
    2.  In the **Virtual machines images folder** field, type the path of the folder where the virtual images files will be installed on the host computer.

        **Note**  
        If you are using image pre-staging, this is the image pre-stage folder where the image is located.



    3.  In the **Minimal required RAM** field, enter the RAM required to install a MED-V package. If the user installing the MED-V package does not have the minimal required RAM, the installation will fail.

    4.  Select the **Install the MED-V management application** check box to include the MED-V management console application in the installation.

    5.  Select the **Create a shortcut to MED-V on the desktop** check box to create a shortcut to MED-V on the host's desktop.

    6.  Select the **Start automatically on computer startup** check box to start MED-V automatically on startup.

    7.  Click **Next**.
    ~~~

12. 在 "**其他安装**" 页面上，选中 "**包括虚拟化软件的安装**" 复选框，以在程序包中包含虚拟 PC 安装。

    "**安装文件**" 字段已启用。 键入虚拟化软件安装文件的完整路径，或单击 " **...** " 以浏览到该目录。

13. 选中 "**包括虚拟 PC QFE 的安装**" 复选框以在程序包中包含虚拟 pc 更新安装。

    "**安装文件**" 字段已启用。 键入虚拟 PC 更新安装文件的完整路径，或单击 " **...** " 以浏览到该目录。

14. 选中 "**包括 microsoft .Net framework 2.0 安装**" 复选框，以在程序包中包含 Microsoft .net framework 2.0 安装。

    "**安装文件**" 字段已启用。 键入 Microsoft .NET Framework 2.0 安装文件的完整路径，或单击 " **...** " 以浏览到该目录。

15. 单击“下一步”****。

16. 在 "**完成**" 页面上，通过执行下列操作之一选择要保存程序包的位置：

    -   在 "**程序包目标**" 字段中，键入应保存程序包的目录的完整路径。

    -   单击 " **...** " 浏览到应保存安装文件的目录。

    **注意**  
    构建程序包可能会占用比实际程序包大小更多的空间。 因此，建议在硬盘上构建程序包。 创建程序包后，可以将其复制到 USB。



17. 在 "**程序包名称**" 字段中，输入程序包的名称。

18. 单击 "**完成**" 以创建程序包。

    创建程序包。 这可能需要几分钟的时间。

    创建程序包后，将显示一条消息，通知您已成功完成。

**注意**  
如果您在本地保存了所有文件，而不是直接在可移动媒体上保存，请确保只将文件夹的内容（而不是文件夹本身）复制到可移动媒体。



**注意**  
可移动媒体必须足够大，以便程序包内容最多只能使用可移动媒体内存的四分之三。



**注意**  
创建程序包时，在生成完成时，可能需要最多两倍的实际包大小。



## 相关主题


[创建 MED-V 映像](creating-a-med-v-image.md)









