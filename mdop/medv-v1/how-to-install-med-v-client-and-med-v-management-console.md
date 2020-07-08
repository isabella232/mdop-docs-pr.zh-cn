---
title: 如何安装 MED-V 客户端和 MED-V 管理控制台
description: 如何安装 MED-V 客户端和 MED-V 管理控制台
author: dansimp
ms.assetid: 8a5f3010-3a50-487e-99d8-e352e5cb51c6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 24a486cc7cf5534171f80b08dc93742e03cd4a0d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804077"
---
# 如何安装 MED-V 客户端和 MED-V 管理控制台


客户端 .msi 程序包中包含以下 MED-V 组件：

-   MED-V 客户端-必须安装在客户端计算机上才能运行 MED-V 工作区的 MED-V 软件。

-   MED-V 管理控制台-管理员可用于创建和维护图像、MED-V 工作区和策略的管理工具。

MED-V 管理控制台和 MED-V 客户端都是从 MED-V 客户端安装的。 但是，不使用 MED-V 管理控制台即可独立安装 MED-V 客户端，方法是清除安装期间的 "**安装 Med-v 管理应用程序**" 复选框。

**注意**  
MED-V 客户端和 MED-V 管理控制台只能安装在基于 Windows 7、Windows Vista 和 Windows XP 的计算机上。 不能在服务器产品上安装它们。



**注意**  
不要使用 Windows **runas**命令安装 med-v 客户端。



**安装 MED-V 客户端**

1.  以具有本地计算机上的本地管理员权限的用户身份登录。

2.  运行 MED-V .msi 程序包。

    MED-V 程序包称为 " *MED-V\_x.msi*"，其中*x*是版本号。

    例如， *MED-V\_1.0.65.msi*。

3.  出现**InstallShield 向导 "欢迎**" 屏幕时，单击 "**下一步**"。

4.  在 "**许可协议**" 屏幕上，阅读许可协议，单击 **"我接受许可协议中的条款**"，然后单击 "**下一步**"。

    显示 "**目标文件夹**" 屏幕，显示默认安装文件夹。

    默认安装文件夹是安装操作系统的目录。

    -   若要更改应安装 MED-V 的文件夹，请单击 "**更改**"，然后通过浏览找到现有文件夹。

5.  单击“下一步”****。

6.  在 " **Med-v 设置**" 屏幕上，配置 med-v 安装，如下所示：

    -   选中 "**安装 med-v 管理应用程序**" 复选框以在安装中包含管理组件。

        **注意**  
        企业桌面虚拟化管理员应安装 MED-V 管理应用程序。 配置桌面映像和 MED-V 工作区需要此应用程序。



~~~
-   Select the **Load MED-V when Windows starts** check box to start MED-V automatically on startup.

-   Select the **Add a MED-V shortcut to my desktop** check box to create a MED-V shortcut on your desktop.

-   In the **Server address** field, type the server address.

-   In the **Server port** field, type the server's port.

-   Select the **Server requires encrypted connections (https)** check box to work with https.

-   The default virtual machine images folder is displayed. The default installation folder is *%systemdrive%\\MED-V Images\\*. To change the folder where MED-V should be installed, click **Change**, and browse to an existing folder.
~~~

7. 单击“下一步”****。

8. 在 "已**准备好安装程序**" 屏幕上，单击 "**安装**"。

   开始安装 MED-V 客户端。 这可能需要几分钟的时间，屏幕可能不会显示文本。 在安装过程中，将显示多个进度屏幕。 如果出现一条消息，请按照提供的说明进行操作。

   成功安装后，将显示 " **InstallShield 向导已完成**" 屏幕。

9. 单击 "**完成**" 关闭向导。

## 相关主题


[支持的配置](supported-configurationsmedv-orientation.md)

[安装和升级清单](installation-and-upgrade-checklists.md)









