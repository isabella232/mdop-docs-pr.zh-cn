---
title: 如何安装和配置默认应用程序
description: 如何安装和配置默认应用程序
author: dansimp
ms.assetid: 5c5d5ad1-af40-4f83-8234-39e972f2c29a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 1083de7a8ebf94bce0b41c0d3c3edf350a9aff38
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801388"
---
# 如何安装和配置默认应用程序


默认应用程序作为安装的一部分提供，并在安装期间自动复制到 Microsoft Application Virtualization （app-v）管理服务器。 它用于验证管理服务器是否已正确安装和配置，但必须将其发布到 Microsoft Application Virtualization （App-v）客户端，以便用户可以访问它。

使用以下过程发布默认应用程序并将其流式传输。

**发布默认应用程序**

1.  使用在安装期间指定的 App-v 管理员组成员的帐户登录到 App-v 管理服务器。

2.  在 App-v 管理服务器上，单击 "**开始**"，单击 "**管理工具**"，然后单击 "**应用程序虚拟化管理控制台**"。

3.  在 App-v 管理控制台中，单击 "**操作**"，然后单击 "**连接到应用程序虚拟化系统**"。

4.  在 "**配置连接**" 页面上，清除 "**使用安全连接**" 复选框。

5.  在 " **Web 服务主机名**" 框中，键入 App-v 管理服务器的完全限定的域名（FQDN），然后单击 **"确定"**。

    **注意** 如果在管理服务器上安装了 Web 服务主机名称，还可以使用**localhost** 。

     

6.  在 App-v 管理控制台中，右键单击**服务器**节点，然后单击 "**系统选项**"。

7.  在 "**常规**" 选项卡上的 "**默认内容路径**" 框中，输入安装期间在服务器上创建的内容文件夹的通用命名约定（UNC）路径;例如，\\ &lt; 服务器名 &gt; \\Content，然后单击 **"确定"**。

    **重要提示** 使用服务器名称的 FQDN，以便客户端可以正确解析名称。

     

8.  在 App-v 管理控制台中的 "导航" 窗格中，展开 "**服务器**" 节点，然后单击 "**应用程序**"。

9.  在 "主题" 窗格中，单击 "**默认应用程序**"，然后在 "**操作**" 窗格中单击 "**属性**"。

10. 在 "**属性**" 对话框中的 " **OSD 路径**" 框旁边，单击 "**浏览**"。

11. 在 "**打开**" 对话框中，输入安装期间在服务器上创建的内容文件夹的 UNC 路径;例如，\\ &lt; 服务器名称 &gt; \\Content，然后按 enter。 必须使用实际服务器名称，并且不能在此处使用**localhost** 。

    **重要提示** 确保 " **OSD 路径**" 和 "**图标路径**" 框中的值为 UNC 格式（例如 \\ &lt; 服务器名称 &gt; \\Content\\DefaultApp.ico），并指向在安装服务器时创建的内容文件夹。 请勿使用**localhost**或包含驱动器号（如 c:\\program files Files\\..）的文件路径\\..内容.

     

12. 选择 "DefaultApp" 文件，然后单击 "**打开**"。

13. 重复前面的步骤来配置图标路径。

14. 单击 "**访问权限**" 选项卡，然后确认 App-V 用户组是否有访问应用程序的权限。

15. 单击 "**快捷方式**" 选项卡，然后单击 "**发布到用户桌面**"。 单击“确定”****。

16. 打开 Windows 资源管理器，找到内容目录。

17. 双击 DefaultApp 文件，然后用记事本将其打开。

18. 找到包含**HREF**标记的行，并将其更改为以下代码：

         `CODEBASEHREF=”RTSP://<FQDN of your server>:554/DefaultApp.sft”`

    或者，如果您使用的是 RTSPS：

         `CODEBASEHREF=”RTSPS://<FQDN of your server>:322/DefaultApp.sft”`

19. 关闭 DefaultApp 文件，然后保存所做的更改。

**流式传输默认应用程序**

1.  在安装了 App-v 客户端的计算机上，作为在服务器安装期间指定的应用程序虚拟化用户组成员的用户登录。

2.  在桌面上，将显示**默认的应用程序虚拟化应用程序**快捷方式。 双击快捷方式以启动应用程序。

3.  Windows 通知区域上方显示的状态栏，报告该应用程序正在启动。 如果应用程序启动成功，将显示默认应用程序的标题屏幕。 单击 **"确定"** 关闭该对话框。 您现在已确认 App V 系统正常运行。

## 相关主题


[如何为基于服务器的部署配置服务器](how-to-configure-servers-for-server-based-deployment.md)

 

 





