---
title: 如何安装 MED-V 客户端
description: 如何安装 MED-V 客户端
author: dansimp
ms.assetid: bfac6de7-d96d-4b3e-bd8b-183e051e53c8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b2e4468b15c0c196bf605b1b5d129ab38678ec74
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804119"
---
# 如何安装 MED-V 客户端


在基于部署程序包的方案中，MED-V 客户端安装包含在部署程序包中并直接从程序包安装。

**重要提示**  
使用不包含图像的部署包时，请确保在安装部署包之前将图像上载到 Web 或将其推送到前阶段文件夹。



**安装部署程序包**

1.  执行下列操作之一：

    -   从 Web 下载 MED-V 程序包。

    -   将部署 USB 或 DVD 插入主驱动器。

2.  如果 MED-V 不会自动启动，请双击 MED-VAutoInstaller.exe。

    将出现一个对话框，其中列出了已安装的组件以及当前正在安装的组件。

    **注意**  
    如果主机上存在不受支持的 Microsoft 虚拟 PC 版本，则会显示一条消息，告知你卸载现有版本并再次运行安装程序。



~~~
**Note**  
If an older version of the MED-V client exists, it will prompt you asking whether you want to upgrade.



Depending on the components that have been installed, you might need to reboot. If rebooting is necessary, a message appears notifying you that you must reboot.
~~~

3. 如有必要，请重新启动计算机。

   安装完成后，将启动 MED-V，并显示一条消息，通知您安装已完成。

4. 使用以下用户名和密码登录到 MED-V：

   -   键入允许使用 MED-V 的域用户的密码的域名和用户名，后跟您的密码。

       示例： "domain \ _name \\user\ _name"，"密码"

## 相关主题


[如何配置部署包](how-to-configure-a-deployment-package.md)

[如何将 MED-V 映像上传到服务器](how-to-upload-a-med-v-image-to-the-server.md)

[客户端安装命令行参考](client-installation-command-line-reference.md)









