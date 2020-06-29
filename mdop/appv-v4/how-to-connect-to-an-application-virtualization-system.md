---
title: 如何连接到 Application Virtualization System
description: 如何连接到 Application Virtualization System
author: dansimp
ms.assetid: ac38216c-5464-4c0b-a4d3-3949ba6358ac
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 30d60e187e1b7595fd0dce6641fa027a1df68f3d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801527"
---
# 如何连接到 Application Virtualization System


必须先将应用程序虚拟化服务器管理控制台连接到应用程序虚拟化系统，然后才能使用管理控制台管理应用程序、文件类型关联、程序包、应用程序许可证、服务器组、提供程序策略和管理员。 以下过程概述了将控制台连接到应用程序虚拟化系统时必须遵循的步骤。

**连接到应用程序虚拟化系统**

1. 右键单击 "**范围**" 窗格中的 "应用程序虚拟化系统" 节点，然后从弹出菜单中选择 "**连接到应用程序虚拟化系统**"。

   **注意**  
   应用程序虚拟化服务器管理有三个组件：应用程序虚拟化管理控制台、管理 Web 服务和 SQL 数据存储。 如果这些组件分布在不同的物理计算机上，则必须正确配置组件的安全性才能在系统之间进行通信。 有关详细信息，请参阅以下手册和文章：

   [如何将服务器配置为受信任的委派](https://go.microsoft.com/fwlink/?LinkID=166682)（https://go.microsoft.com/fwlink/?LinkID=166682)

   [应用程序虚拟化系统的规划和部署指南](https://go.microsoft.com/fwlink/?LinkID=122063)（https://go.microsoft.com/fwlink/?LinkID=122063)

   [应用程序虚拟化系统的操作指南](https://go.microsoft.com/fwlink/?LinkID=133129)（https://go.microsoft.com/fwlink/?LinkID=133129)

   Microsoft 知识库中的[文章 930472](https://go.microsoft.com/fwlink/?LinkId=114647) （https://go.microsoft.com/fwlink/?LinkId=114647)

   Microsoft 知识库中的[文章 930565](https://go.microsoft.com/fwlink/?LinkId=114648) （https://go.microsoft.com/fwlink/?LinkId=114648)

     

2. 填写 "**连接到应用程序虚拟化系统**" 对话框中的字段：

   1. **Web 服务主机名**—输入要连接到的应用程序虚拟化系统的名称，或输入**localhost**以连接到本地服务器。

   2. **使用安全连接**-如果要使用安全连接连接到服务器，请选中此复选框。

   3. **Port**-输入要用于连接的端口号。 **80**是默认的常规端口号， **443**是安全端口号。

   4. **使用当前 Windows 帐户**-选择此单选按钮以使用当前的 windows 帐户凭据。

   5. **指定 Windows 帐户**-如果你希望以其他用户身份连接到服务器，请选择此单选按钮。

   6. **名称**-使用*DOMAIN\\username*或 username@domain 格式输入新用户的名称 <em> </em> 。

   7. **密码**—输入与新用户对应的密码。

3. 单击**确定**。

## 相关主题


[如何在 Application Virtualization Server Management Console 中执行管理任务](how-to-perform-administrative-tasks-in-the-application-virtualization-server-management-console.md)

 

 





