---
title: 如何在单独的计算机上从管理和报告服务安装管理和报告数据库
description: 如何在单独的计算机上从管理和报告服务安装管理和报告数据库
author: dansimp
ms.assetid: 2a67402e-3119-40ea-a247-24d166af1ced
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2332f674f10a9b60aa1cee814c6eac4ddbe4f5af
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798444"
---
# 如何在单独的计算机上从管理和报告服务安装管理和报告数据库

使用以下过程在不同计算机上安装数据库服务器和管理服务器。 你计划用于安装数据库服务器的计算机必须运行受支持的 Microsoft SQL 版本，否则安装将失败。

> [!NOTE]
> 完成部署后，安装该服务的管理员将需要**MICROSOFT SQL Server 名称**、**实例名称**和**数据库名称**才能连接到这些数据库。

## 在单独的计算机上安装管理数据库和管理服务器

1. 将 app-v 5.1 服务器安装文件复制到要在其上安装它的计算机上。 若要启动 app-v 5.1 服务器安装，请右键单击并以管理员身份运行**appv\_server\_setup.exe** 。 单击**安装**。
1. 在 "**入门**" 页面上，查看并接受许可条款，然后单击 "**下一步**"。
1. 在 "**使用 Microsoft 更新" 帮助保持计算机的安全和最新**页面上，若要启用 Microsoft 更新，请选择 "**当我检查更新时使用 Microsoft 更新" （推荐）。** 若要禁用 Microsoft 更新，请选择 "**我不想使用 Microsoft 更新**"。 单击“下一步”****。
1. 在 "**功能选择**" 页面上，选择要安装的组件，方法是选择 "**管理服务器数据库**" 复选框，然后单击 "**下一步**"。
1. 在 "**安装位置**" 页面上，接受默认位置，然后单击 "**下一步**"。
1. 在 "**新建管理服务器数据库" 页面**上，接受默认选择（如果适用），然后单击 "**下一步**"。

    如果您使用的是自定义 SQL Server 实例，请选择 "**使用自定义实例**"，然后键入实例的名称。
    如果您使用的是自定义数据库名称，请选择 "**自定义配置**"，然后键入数据库名称。

1. 在 "**新建管理服务器数据库**" 页面上，选择 "**使用远程计算机**"，然后使用以下格式键入远程计算机帐户： **Domain\\MachineAccount**。

    > [!NOTE]
    > 如果你计划在同一台计算机上部署管理服务器，必须选择 "**使用此本地计算机**"。

1. 使用以下格式为管理服务器**安装管理员**指定用户名称： **Domain\\AdministratorLoginName**。 单击“下一步”****。
1. 若要开始安装，请单击 "**安装**"。

## 在单独的计算机上安装报表数据库和报表服务器

1. 将 app-v 5.1 服务器安装文件复制到要在其上安装它的计算机上。 若要启动 app-v 5.1 服务器安装，请右键单击并以管理员身份运行**appv\_server\_setup.exe** 。 单击**安装**。
1. 在 "**入门**" 页面上，查看并接受许可条款，然后单击 "**下一步**"。
1. 在 "**使用 Microsoft 更新" 帮助保持计算机的安全和最新**页面上，若要启用 Microsoft 更新，请选择 "**当我检查更新时使用 Microsoft 更新" （推荐）。** 若要禁用 Microsoft 更新，请选择 "**我不想使用 Microsoft 更新**"。 单击“下一步”****。
1. 在 "**功能选择**" 页面上，选择要安装的组件，方法是选中 "**报表服务器数据库**" 复选框，然后单击 "**下一步**"。
1. 在 "**安装位置**" 页面上，接受默认位置，然后单击 "**下一步**"。
1. 在 "**创建新的报表服务器数据库**" 页面上，接受默认选择（如果适用），然后单击 "**下一步**"。

    如果你使用的是自定义 SQL Server 实例，请选择 "**使用自定义实例**"，然后键入实例的名称。
    如果您使用的是自定义数据库名称，请选择 "**自定义配置**"，然后键入数据库名称。

1. 在 "**新建报表服务器数据库**" 页面上，选择 "**使用远程计算机**"，然后使用以下格式键入远程计算机帐户： **Domain\\MachineAccount**。

    > [!NOTE]
    > 如果你计划在同一台计算机上部署报表服务器，必须选择 "**使用此本地计算机**"。

1. 使用以下格式为 reporting server**安装管理员**指定用户名： **Domain\\AdministratorLoginName**。 单击“下一步”****。
1. 若要开始安装，请单击 "**安装**"。

## 使用 App-v 5.1 数据库脚本安装管理和报告数据库

1. 将 app-v 5.1 服务器安装文件复制到要在其上安装它的计算机上。
1. 若要提取 app-v 5.1 数据库脚本，请打开命令提示符并指定保存安装文件的位置，然后运行以下命令：

    **appv\_server\_setup.exe** **/LAYOUT** **/LAYOUTDIR = "InstallationExtractionLocation"**。

1. 提取完成后，若要访问 app-v 5.1 数据库脚本和说明自述文件，请执行以下操作：

    - App-v 5.1 管理数据库脚本和说明自述文件位于以下文件夹中： **InstallationExtractionLocation**  \\  **数据库脚本**  \\  **管理数据库**。
    - App-v 5.1 报告数据库脚本和说明自述文件位于以下文件夹中： **InstallationExtractionLocation**  \\  **数据库脚本**  \\  **报告数据库**。

1. 对于每个数据库，将脚本复制到共享，然后按照自述文件中的说明进行修改。

    > [!NOTE]
    > 有关修改脚本中包含的所需 Sid 的详细信息，请参阅[如何使用 PowerShell 安装 App-v 数据库并转换关联的安全标识符](how-to-install-the-app-v-databases-and-convert-the-associated-security-identifiers--by-using-powershell51.md)。

1. 在运行 Microsoft SQL Server 的计算机上运行脚本。

**遇到了 app-v 问题？** 使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相关主题

[部署 App-V 5.1](deploying-app-v-51.md)
