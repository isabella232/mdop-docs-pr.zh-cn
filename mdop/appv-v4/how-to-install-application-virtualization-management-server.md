---
title: 如何安装 Application Virtualization Management Server
description: 如何安装 Application Virtualization Management Server
author: dansimp
ms.assetid: 8184be79-8c27-4328-a3c1-183791b5556c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: dfd06ee1d2448990d5a740f3d59b0e5e4b45be4d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801387"
---
# 如何安装 Application Virtualization Management Server


应用程序虚拟化管理服务器将其应用程序发布到客户端。 在负载平衡环境（这是一种典型的大型部署）中，服务器组中的所有服务器应流出相同的应用程序。 如果应用程序虚拟化管理服务器要发布不同的应用程序，请将服务器分配给不同的服务器组。 在这种情况下，你还可能需要增加服务器组的容量。

如果已使用具有本地管理员权限的登录帐户在网络上指定目标计算机，则可以使用以下过程来安装应用程序虚拟化管理服务器并将其分配到相应的服务器组。

**注意**  
安装向导可以创建一个服务器组记录（如果不存在），以及此组中应用程序虚拟化管理服务器成员身份的记录。



完成安装过程后，重新启动服务器。

**安装应用程序虚拟化管理服务器**

1.  验证和（如有必要）卸载已安装在目标计算机上的应用程序虚拟化管理服务器的以前版本。

2.  若要打开**Microsoft Application Virtualization 管理服务器安装**向导，请导航到网络上应用程序虚拟化系统**setup.exe**程序的位置，或者从网络运行此程序，或者将其目录复制到目标计算机，然后双击**Setup.exe**文件。

3.  在 "**欢迎**" 页面上，单击 "**下一步**"。

4.  在 "**许可协议**" 页面上，阅读许可协议，若要接受许可协议，请选择 **"我接受许可条款和条件"**。 单击“下一步”****。

5.  在 "**注册信息**" 页面上，必须输入用户名和**组织**名称。 单击“下一步”****。

6.  在 "**安装类型**" 页面上，选择 "**自定义**"。 单击“下一步”****。 在 "**自定义设置**" 页面上，取消选择 "**应用程序虚拟化服务器**除外"**下**的所有应用程序虚拟化系统组件，然后单击 "

    **注意**  
    如果计算机上已安装某个组件，则在 "**自定义设置**" 窗口中取消选中该组件时，将自动卸载该组件。



7.  在 "**配置数据库**" 页面上，从可用服务器列表中选择一个数据库服务器，或通过选择 "**使用以下主机名**" 并指定**服务器名称**和**端口号**数据来添加服务器。 单击“下一步”****。

    **注意**  
    应用程序虚拟化管理服务器不支持区分大小写的 SQL。



~~~
If a database is available, click the radio button, select the database from the list, and then click **Next**. Setup will upgrade it to this newer version. If the name does not appear in the list, enter the name in the space provided.

**Note**  
When naming a server, do not use the backslash character (/) in the server name.

If you need to install a database, see [How to Install a Database](how-to-install-a-database.md). If you would like to create a new database for this version, select **Create a new database** and specify the name that will be assigned to the new database. You can also specify a new location for the database by selecting the check box and entering the path.
~~~



8. 在 "**连接安全模式**" 页面上，从下拉列表中选择所需的证书。 单击“下一步”****。

   **注意**  
   "**安全连接模式**" 设置要求服务器从公钥基础结构中为其预配服务器证书。 如果服务器上未安装服务器证书，则此选项不可用且无法选中。 您必须授予网络服务帐户对正在使用的证书的读取访问权限。



9. 在 " **TCP 端口配置**" 页面上，要使用默认端口（554），请选择 "**使用默认端口（554）**"。 若要指定自定义端口，请选择 "**使用自定义端口**" 并指定将使用的端口号。 单击“下一步”****。

   **注意**  
   在不安全的环境中安装服务器时，可以使用默认端口（554），也可以定义自定义端口。



10. 在 "**管理员组**" 页面上，在 "**组名称**" 中指定授权管理此服务器的安全组的名称。 单击“下一步”****。 确认指定的组，然后单击 "**下一步**"。

11. 在 "**默认提供程序组**" 页面上，指定默认提供程序组的名称，然后单击 "**下一步**"。

12. 在 "**内容路径**" 页面上，指定将保存 SFT 文件的目标计算机上的位置，然后单击 "**下一步**"。

   **注意**  
   如果管理服务器的 HTTP 或 RTSP 端口已分配，系统将提示你选择新端口。 选择所需的端口，然后单击 "**下一步**"。



13. 在 "已**准备好安装程序**" 页面上，若要安装应用程序虚拟化管理服务器，请单击 "**安装**"。

   **注意**  
   如果在尝试完成此步骤时显示错误25120，则需要启用 IIS**管理脚本和工具**。 若要启用此 Windows 功能，请打开 "**程序和功能**" 控制面板，选择 **"打开或关闭 Windows 功能**"，然后导航到 " **Internet 信息服务"。**

   在 " **Web 管理工具**" 下，启用**IIS 管理脚本和工具**。



14. 在**安装向导完成**的屏幕上，若要关闭向导，请单击 "**完成**"。

   **重要提示**  
   安装可能需要几分钟才能完成。 状态消息将在 Windows 桌面通知区域上方闪烁，指示安装成功。

   出现提示时，不需要重新启动计算机。 但是，为了优化系统性能，建议重新启动。



## 相关主题


[如何安装服务器和系统组件](how-to-install-the-servers-and-system-components.md)









