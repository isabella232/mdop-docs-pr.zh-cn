---
title: 如何将 App-V SQL 数据库迁移到其他 SQL Server
description: 如何将 App-V SQL 数据库迁移到其他 SQL Server
author: dansimp
ms.assetid: 353892a1-9327-4489-a19c-4ec7bd1b736f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e3d84b0cb328873db3722ad3eb9af6a2b442fdcf
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801271"
---
# 如何将 App-V SQL 数据库迁移到其他 SQL Server


以下过程详细介绍了如何将 Microsoft Application Virtualization （app-v）管理服务器的 SQL 数据库迁移到其他 SQL 服务器。

**重要提示** 此过程要求停止应用 V 服务器服务，这将阻止最终用户使用其应用程序。

 

**备份 app-v SQL 数据库**

1.  打开 services.msc 程序，并停止使用要迁移的数据库的所有管理服务器上的 App-v 管理服务器服务。

2.  在应用程序 V 数据库所在的计算机上，打开 SQL Server Management Studio。

3.  展开 "**数据库**" 节点并找到 "app-v 数据库" （默认名称为 APPVIRT）。

4.  右键单击数据库并选择 "**任务**"，然后选择 "**备份**"。

5.  验证 "**恢复模型**" 设置为 "**简单**"，"**备份类型**" 设置为 "**完整**"。 如有必要，请更改**备份集**和**目标**设置。

6.  单击 **"确定"** 备份数据库。 备份成功完成后，单击 **"确定"**。

7.  打开 Windows 资源管理器，浏览到包含数据库备份文件的文件夹，例如 APPVIRT。.BAK. 将数据库备份文件复制到运行 SQL Server 的目标计算机。

**将 app-v SQL 数据库还原到目标计算机**

1.  在目标计算机上，打开 SQL Server Management Studio，右键单击 "**数据库**" 节点，然后选择 "**还原数据库**"。

2.  在 "**还原源**" 下，选择 "**从设备**"，然后单击 "**..."。** 按钮。

3.  在 "**指定备份**" 对话框中，确保**备份媒体**已设置为 "**文件**"，然后单击 "**添加**"。

4.  选择从运行 SQL Server 的原始计算机复制的备份文件，然后单击 **"确定"**。

5.  单击 **"确定"** ，然后单击以选择要还原的备份集。

6.  在 "**还原目标**" 下，单击 "**数据库**" 下拉列表，然后选择 "app-v" 数据库名称，例如 APPVIRT。

7.  单击 **"确定"** 启动还原。 还原成功完成后，单击 **"确定"**。

8.  展开 "**安全**" 节点，右键单击 "**登录**"，然后选择 "**新建登录**"。

9.  在 "**登录名**" 字段中，输入 App-v 管理服务器的网络服务帐户详细信息，格式为 DOMAIN\\SERVERNAME $。

10. 在 "**默认数据库**" 下的 "**常规**" 页面上，选择 "app-v" 数据库名称，例如 "APPVIRT"，然后单击 **"确定"**。

11. 在 "**选择页面**" 下，单击以选择 "**用户映射**" 页面。 在 "**用户映射到此登录名**" 下，单击 "**映射**" 列中的复选框以选择 app-v 数据库。

12. 在 **： &lt; &gt; Appvdatabasename 的 "数据库角色成员身份**" 下，单击以选择**SFTEveryone** ，然后单击 **"确定"**。

13. 确保将运行 SQL Server 的新计算机上的 Windows 防火墙配置为允许 App-v 管理服务器访问系统。 在 "**管理工具**" 下，使用**具有高级安全程序的 WINDOWS 防火墙**为 SQL Server 使用的端口创建**入站规则**（默认为端口1433）。

**迁移 app-v SQL Server 代理作业**

1.  在运行 SQL Server 的原始计算机上，在 SQL Server Management Studio 中，展开 " **Sql Server 代理**" 节点，然后展开 "**作业**" 节点。

2.  右键单击以下四个 App-v 作业，然后选择 "**脚本作业" 作为 |创建到 |文件**，并将每个脚本保存到一个文件夹，并为每个脚本提供一个描述性名称。

    -   **Softgrid 数据库（appvdbname）检查使用情况历史记录**

    -   **Softgrid 数据库（appvdbname）关闭孤立会话**

    -   **Softgrid 数据库（appvdbname）强制大小限制**

    -   **Softgrid 数据库（appvdbname）监视器警报/作业状态**

3.  将四个脚本文件（.sql）复制到运行 SQL Server 的目标计算机，并打开 SQL Server Management Studio。

4.  在 Windows 资源管理器中，右键单击每个 .sql 文件，然后单击 "**运行**"。 每个脚本都将在 SQL Server Management Studio 中的查询窗口中打开。 单击每个脚本的 "**执行**" 并验证每个脚本是否已成功完成。

5.  刷新**SQL Server 代理**节点下的 "**作业**" 节点，确认已成功创建四个作业。

**更新 app-v 管理服务器的配置**

1.  在 App-v 管理服务器上，修改以下注册表项：

    -   **SQLServerName**  =  SQLServerName &lt;newservername&gt;

    -   **SQLServerPort**  =  SQLServerPort &lt;newserverport&gt;

    然后重新启动 app-v 服务器服务。

2.  通过浏览找到应用程序 V 管理服务器安装目录下的文件 SftMgmt （默认为 C:\\program files Files\\Microsoft System Center App Virt 管理 Server\\App Virt 管理服务）。 右键单击文件，然后选择 "**打开**"。

3.  在 "**连接**" 选项卡上，输入运行 SQL Server 的目标计算机的名称，然后单击 "**测试连接**"。 测试成功后，单击 **"确定"** ，然后再次单击 **"确定"** 。

4.  对于 4.5 SP2 之前的 app-v 管理服务器版本，必须更新 SQL 日志记录设置。 在 "**服务器组**" 下，右键单击服务器所属的服务器组，然后选择 "**属性**"。

5.  在 "**日志记录**" 选项卡上，单击以选择**SQL 数据库**条目，然后单击 "**编辑**"。

6.  将**DNS 主机名**更改为运行 SQL Server 的新计算机的主机名，然后单击 **"确定"**。 再次单击 **"确定"** 两次，然后重新启动 app-v 服务器服务。

7.  打开 app-v 管理控制台，右键单击 "**应用程序**" 节点，然后选择 "**刷新**"。 应用程序列表应显示为 "以前"。

 

 





