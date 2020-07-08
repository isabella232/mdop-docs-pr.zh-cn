---
title: 如何使用 Configuration Manager 安装 MBAM
description: 如何使用 Configuration Manager 安装 MBAM
author: dansimp
ms.assetid: fd0832e4-3b79-4e56-9550-d2f396be6d09
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a556ce961e6a423caecdd0766cf8623383897b58
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803706"
---
# 如何使用 Configuration Manager 安装 MBAM


本节介绍使用配置管理器通过[配置管理器](getting-started---using-mbam-with-configuration-manager.md)将 MBAM 安装到配置管理器的步骤。 步骤分为以下任务：

-   在 Configuration Manager 服务器上安装和配置 MBAM

-   在数据库服务器上安装恢复和审核数据库

-   在 "管理和监视" 服务器上安装 "管理和监视服务器" 功能

开始安装之前，请确保您已编辑或创建了必要的 mof 文件。 有关说明，请参阅[如何创建或编辑 Mof 文件](how-to-create-or-edit-the-mof-files.md)。

**重要提示** 如果你使用的是非默认 SQL Server Reporting Services （SSRS）实例，则必须使用以下命令行来启动 MBAM 设置以指定 SSRS 命名的实例：

`MbamSetup.exe CM_SSRS_INSTANCE_NAME=<NamedInstance>`

 

**在 Configuration Manager 服务器上安装 MBAM**

1.  在 Configuration Manager 服务器上，运行 " **MBAMSetup.exe** " 以启动 MBAM 安装向导。

    **注意** 若要获取安装程序日志文件，必须使用 Msiexec 程序包和 **/l** &lt; location &gt; 选项来安装 Configuration Manager。 将在您指定的位置创建日志文件。

    在安装 Configuration Manager 的用户的计算机上的% temp% 文件夹中创建了其他安装日志文件。

     

2.  在 "**欢迎**" 页面上，选择 "**客户体验改善计划**"，然后单击 "**开始**"。

3.  阅读并接受 Microsoft 软件许可协议，然后单击 "**下一步**" 继续安装。

4.  在 "**拓扑选择**" 页面上，选择 " **System Center Configuration Manager 集成**"，然后单击 "**下一步**"。

5.  在 "**选择要安装的功能**" 页面上，选择 " **System Center Configuration Manager 集成**"。

    **注意** 在 "**检查先决条件**" 页面上，在安装向导检查安装的先决条件并确认没有缺失时，单击 "**下一步**"。 如果检测到缺少先决条件，则必须解决缺少的先决条件，然后再次单击 "**检查必备项"。**

     

6.  指定是否使用 Microsoft 更新来帮助保护您的计算机安全，然后单击 "**下一步**"。 使用 Microsoft 更新不会在 Windows 中启用自动更新。

7.  单击**下一步**以继续。

8.  在 "**安装摘要**" 页面上，查看将安装的功能列表，然后单击 "**安装**" 以开始安装 MBAM 功能。 如果必须查看或更改安装设置，请单击 "**返回**" 以在向导中向后移动，或者单击 "**取消**" 退出安装程序。 安装程序安装 MBAM 功能并通知您安装已完成。

9.  单击 "**完成**" 退出向导。

**在数据库服务器上安装恢复和审核数据库**

1.  在数据库服务器上，运行**MBAMSetup.exe**以启动 MBAM 安装向导。

2.  在 "**欢迎**" 页面上，选择 "**客户体验改善计划**"，然后单击 "**开始**"。

3.  阅读并接受 Microsoft 软件许可协议，然后单击 "**下一步**" 继续安装。

4.  在 "**拓扑选择**" 页面上，选择 " **System Center Configuration Manager 集成**拓扑"，然后单击 "**下一步**"。

5.  从要安装的功能列表中，选择 "**恢复数据库**和**审核数据库**"，然后清除剩余的功能。

    **注意** 安装向导将检查安装的先决条件，并显示缺少的必备条件。 如果满足所有先决条件，安装将继续。 如果检测到缺少先决条件，则必须解决缺少的先决条件，然后再次单击 "**检查必备项**"。 如果此时间满足所有先决条件，安装将继续。

     

6.  在 "**配置恢复数据库**" 页面上，指定将运行 "管理和监视服务器" 功能的计算机的名称。 部署 "管理和监视服务器" 功能后，它将使用其域帐户连接到数据库。

7.  单击**下一步**以继续。

8.  指定要存储恢复数据的 SQL Server 实例名称和数据库的名称。 还必须指定数据库将位于的位置以及日志信息所在的位置。

9.  单击 "**下一步**" 以继续安装 MBAM 设置安装向导。

10. 在 "**配置审核数据库**" 页面上，指定将用于访问报表的数据库的用户帐户。

11. 指定将运行管理和监视服务器以及审核报告的计算机的计算机名称。 部署 "管理和监视" 和 "审核报告" 功能后，将使用其域帐户连接到数据库。

    **注意** 如果在未使用 "审核报告" 功能的情况下安装审核数据库，则必须在审核数据库计算机上添加一个例外，以便在 Microsoft SQL Server 端口上启用入站流量。 默认端口号为1433。

     

12. 指定要存储审核数据的数据库的 SQL Server 实例名称和数据库名称。 你还必须指定数据库和日志信息的位置。

13. 单击 "**安装**" 以开始安装，然后单击 "**完成**" 以完成安装。

**在管理和监视服务器上安装管理和监视服务器功能**

1.  在 "管理和监视" 服务器上，运行 " **MBAMSetup.exe** " 以启动 MBAM 安装向导。

2.  在 "**欢迎**" 页面上，选择 "**客户体验改善计划**"，然后单击 "**开始**"。

3.  阅读并接受 Microsoft 软件许可协议，然后单击 "**下一步**" 继续安装。

4.  在 "**拓扑选择**" 页面上，选择 " **System Center Configuration Manager 集成**拓扑"，然后单击 "**下一步**"。

5.  从要安装的功能列表中，选择 "**管理和监视服务器**和**自助服务门户**"，然后清除 "剩余功能"。

    **注意** 安装向导将检查安装的先决条件，并显示缺少的必备条件。 如果满足所有先决条件，安装将继续。 如果检测到缺少先决条件，则必须解决缺少的先决条件，然后再次单击 "**检查必备项**"。 如果此时间满足所有先决条件，安装将继续。

     

6.  按照[如何在分布式服务器上安装和配置 MBAM](how-to-install-and-configure-mbam-on-distributed-servers-mbam-2.md)的 "**安装自助服务门户**" 部分中的步骤安装自助服务门户。

    **注意** 如果客户端计算机将无法访问 Microsoft 内容交付网络（CDN），这将为自助服务门户提供对某些 JavaScript 文件所需的访问权限，完成了在**最终用户无法访问 Microsoft Content 传递网络部分时配置自助服务门户**中的步骤，[如何在分布式服务器上安装和配置 MBAM](how-to-install-and-configure-mbam-on-distributed-servers-mbam-2.md) ，以将自助服务门户配置为从易于访问的源中引用 JavaScript 文件。

     

7.  按照[如何在分布式服务器上安装和配置 MBAM](how-to-install-and-configure-mbam-on-distributed-servers-mbam-2.md)的 "**安装管理和监视服务器功能**" 部分中的步骤安装管理和监视服务器功能。

8.  单击 "**完成**" 以完成安装。

## 相关主题


[如何使用 Configuration Manager 验证 MBAM 安装](how-to-validate-the-mbam-installation-with-configuration-manager.md)

[使用 Configuration Manager 部署 MBAM](deploying-mbam-with-configuration-manager-mbam2.md)

 

 





