---
title: 如何安装和配置 MED-V 服务器组件
description: 如何安装和配置 MED-V 服务器组件
author: dansimp
ms.assetid: 2d3c5b15-df2c-4ab6-bf78-f47ef8ae7418
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 4fb0cc5c9ffe76e987e316d0285f172dd0b76578
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804076"
---
# 如何安装和配置 MED-V 服务器组件


本部分介绍如何[安装](#bkmk-howtoinstallthemedvserver)和[配置](#bkmk-howtoconfigurethemedvserver)med-v 服务器。

## <a href="" id="bkmk-howtoinstallthemedvserver"></a>如何安装 MED-V 服务器


**安装 MED-V 服务器**

1.  安装 MED-V 服务器 .msi 程序包。

    "MED-V 服务器 .msi" 程序包称为 " *MED-V\_Server\_x.msi*"，其中 x 是版本号。

    例如， *MED-V\_Server\_1.0.65.msi*。

2.  出现**InstallShield 向导 "欢迎**" 屏幕时，单击 "**下一步**"。

3.  在 "**许可协议**" 屏幕上，阅读许可协议，单击 **"我接受许可协议中的条款**"，然后单击 "**下一步**"。

    显示 "**目标文件夹**" 屏幕，显示默认安装文件夹。

    默认安装文件夹为 *%Systemdrive%\\Program Files\\Microsoft Enterprise Desktop Virtualization\\*。

    -   若要更改应安装 MED-V 的文件夹，请单击 "**更改**"，然后浏览到现有文件夹。

4.  单击“下一步”****。

5.  在 "已**准备好安装程序**" 屏幕上，单击 "**安装**"。

    开始安装 MED-V 服务器。 这可能需要几分钟的时间，屏幕可能不会显示文本。 在安装过程中，将显示多个进度屏幕。 如果出现一条消息，请按照提供的说明进行操作。

6.  当 " **InstallShield 向导完成**" 屏幕出现时，单击 "**完成**" 以完成该向导。

**注意**  
如果要通过 Microsoft 远程桌面安装 MED-V 服务器，请使用以下语法： **mstsc/admin**。确保你的 RDP 会话定向到控制台。



## <a href="" id="bkmk-howtoconfigurethemedvserver"></a>如何配置 MED-V 服务器


可以配置以下服务器设置：

-   [连接](#bkmk-configuringconnections)

-   [Images](#bkmk-configuringimages)

-   [权限](#bkmk-configuringpermissions)

-   [报告](#bkmk-configuringreports)

### <a href="" id="bkmk-configuringconnections"></a>配置连接

**配置连接**

1.  在 Windows "开始" 菜单上，选择 "**所有程序" &gt; med-v &gt; Med-v-v 服务器配置管理器**。

    **注意**  
    注意：如果在服务器安装期间选中了 "**启动 Med-v Server 配置管理器**" 复选框，则 med-v 服务器配置管理器将在服务器安装完成后自动启动。



~~~
The MED-V Server Configuration Manager appears.
~~~

2. 在 "**连接**" 选项卡上，配置以下客户端连接设置：

   -   **启用未加密的连接（http），使用端口**—选中此复选框可使用指定的端口启用未加密的连接。 在 "端口" 框中，输入要接受未加密的连接（http）的服务器端口。

   -   **启用加密连接（https），使用端口**-选中此复选框可使用指定的端口启用加密连接。 在 "端口" 框中，输入要接受加密连接的服务器端口（https）。

       Https 是可选配置，可以进行设置以确保 MED-V 服务器和 MED-V 客户端之间的安全事务。 若要配置 https，必须执行以下过程：

       -   在服务器上配置证书。

       -   将服务器证书与使用 netsh 指定的端口相关联。 有关信息，请参阅以下内容：

           -   [超文本传输协议（HTTP）的 Netsh 命令](https://go.microsoft.com/fwlink/?LinkId=183314)

           -   [如何：使用 SSL 证书配置端口](https://go.microsoft.com/fwlink/?LinkID=183315)

           -   [如何：使用 SSL 证书配置端口](https://msdn.microsoft.com/library/ms733791.aspx)

3. 单击“确定”****。

### <a href="" id="bkmk-configuringimages"></a>配置图像

**配置图像**

1.  单击 "**图像**" 选项卡。

2.  配置以下映像管理设置：

    -   虚拟机**目录**-虚拟机目录（存储图像的目录）。 此字段包含可从 MED-V 服务器访问的图像分发服务器上的图像目录的 UNC 路径。

    -   **VM URL**-存储图像的服务器的位置。

3.  单击“确定”****。

### <a href="" id="bkmk-configuringpermissions"></a>配置权限

**配置权限**

1.  单击 "**权限**" 选项卡。

2.  提供了可供登录的所有用户的列表。 若要对用户应用 "读取" 和 "写入" 权限，请选中用户旁边的复选框。 若要对用户应用只读权限，请清除该复选框。

3.  若要添加域用户或组，请单击 "**添加**"。

    将显示 "**输入用户或组名称**" 对话框。

    1.  通过执行下列操作之一选择 "域用户" 或 "组"：

        -   在 "**输入用户或组名称**" 字段中，键入域中存在的用户或组，或者在计算机上作为本地用户或组存在。 然后单击 "**检查姓名**" 以将其解析为完整的现有名称。

        -   单击 "**查找**" 以打开 "标准**选择用户或组**" 对话框。 然后选择 "域用户" 或 "组"。

    2.  单击“确定”****。

4.  若要删除域用户或组，请选择用户或组，然后单击 "**删除**"。

5.  单击“确定”****。

### <a href="" id="bkmk-configuringreports"></a>配置报表

**配置报表**

1.  单击 "**报表**" 选项卡。

2.  若要支持报表，请选择 "**启用报表**"。

3.  在 "**连接字符串**" 框中，输入 MSSQL 数据库的连接字符串。

    -   当 SQL Server 安装在远程服务器上时，请使用以下连接字符串：

        `Data Source=<ServerName>;Initial Catalog=<DBName>;uid=sa;pwd=<Password>;`

        **注意**  
        注意：若要连接到 SQL Express，请使用： `Data Source=<ServerName>\sqlexpress.`



4.  若要创建数据库，请单击 "**创建数据库**"。

5.  若要测试连接，请单击 "**测试连接**"。

6.  要配置数据库清除选项，请单击 "**清除选项**"。

    将显示 "**清除数据库选项**" 对话框。

    1.  选择以下选项之一：

        -   **清除早于**该时间的数据-清除早于指定天数的所有数据;在 "数字" 框中，输入天数。

        -   **清除数据库中的所有数据**-清除数据库中的所有现有数据。

        -   **删除数据库**-删除数据库。

    2.  单击 **"确定"** 以应用更改并关闭对话框。

7.  单击 **"确定"** 保存所做的更改，或单击 "**取消**" 关闭对话框而不保存所做的更改。

8.  如果出现提示，请重新启动 MED-V 服务器服务以将更改应用到网络设置。

## 相关主题


[支持的配置](supported-configurationsmedv-orientation.md)

[设计 MED-V 服务器基础结构](design-the-med-v-server-infrastructure.md)









