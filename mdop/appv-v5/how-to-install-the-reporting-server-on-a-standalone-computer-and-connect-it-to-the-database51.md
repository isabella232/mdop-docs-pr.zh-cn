---
title: 如何在独立计算机上安装报告服务器并将其连接到数据库
description: 如何在独立计算机上安装报告服务器并将其连接到数据库
author: dansimp
ms.assetid: 11f07750-4045-4c8d-a583-7d70c9e9aa7b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 67866714ff6ae60097d9b368fd0eaf361b08eec6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798429"
---
# 如何在独立计算机上安装报告服务器并将其连接到数据库

使用以下过程在独立计算机上安装报告服务器，并将其连接到数据库。

**重要提示**在执行以下过程之前，应阅读并了解[有关 app-v 5.1 的报告](about-app-v-51-reporting.md)。

## 在独立计算机上安装报表服务器并将其连接到数据库

1. 将 app-v 5.1 服务器安装文件复制到要在其上安装它的计算机上。 若要启动 app-v 5.1 服务器安装，请右键单击并以管理员身份运行**appv\_server\_setup.exe** 。 单击**安装**。

2. 在 "**入门**" 页面上，查看并接受许可条款，然后单击 "**下一步**"。

3. 在 "**使用 Microsoft 更新" 帮助保持计算机的安全和最新**页面上，若要启用 Microsoft 更新，请选择 "**当我检查更新时使用 Microsoft 更新" （推荐）。** 若要禁用 Microsoft 更新，请选择 "**我不想使用 Microsoft 更新**"。 单击“下一步”****。

4. 在 "**功能选择**" 页面上，选中 "**报表服务器**" 复选框，然后单击 "**下一步**"

5. 在 "**安装位置**" 页面上，接受默认位置，然后单击 "**下一步**"。

6. 在 "**配置现有报告数据库**" 页面上，选择 "**使用远程 SQL server**"，然后键入运行 Microsoft SQL server 的计算机的名称，例如**SqlServerMachine**。

    > [!NOTE]
    > 如果 Microsoft SQL Server 部署在同一台服务器上，请选择 "**使用本地 SQL server**"。

    对于 SQL Server 实例，请选择 "**使用默认实例"**。 如果你使用的是自定义 Microsoft SQL Server 实例，则必须选择 "**使用自定义实例**"，然后键入实例的名称。

    指定此报表服务器将使用的**SQL Server 数据库名称**，例如**AppvReporting**。

7. 在 "**配置报表服务器配置**" 页面上。

   - 指定要用于报告服务的网站名称。 如果您没有自定义名称，则保留默认值不变。

   - 对于**端口绑定**，请指定将由 app-v 5.1 使用的唯一端口号（例如**55555**）。 你还应确保指定的端口未被其他网站使用。

8. 单击**安装**。

**遇到了 app-v 问题？** 使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相关主题

[关于 App-V 5.1 报告](about-app-v-51-reporting.md)

[部署 App-V 5.1](deploying-app-v-51.md)

[如何使用 PowerShell 在 App-V 5.1 Client 上启用报告](how-to-enable-reporting-on-the-app-v-51-client-by-using-powershell.md)
