---
title: 关于 Application Virtualization 程序包
description: 关于 Application Virtualization 程序包
author: dansimp
ms.assetid: 69bd35c1-7af3-43db-931b-3074780aa926
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: cfe6df90881ea4179fa8cd224609ca6d28ff5f61
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802475"
---
# 关于 Application Virtualization 程序包


在应用程序虚拟化中，*程序包*是排序过程的输出。 第一次在服务器上部署应用程序时，以及使用新版本升级应用程序时，可以使用程序包。 程序包使你能够控制你的应用程序虚拟化管理服务器上的虚拟应用程序版本。 单个程序包可以包含一个或多个应用程序。 每个应用程序包都包含一组自包含的单元文件。

## 管理程序包


在 Sequencer 创建一个或多个应用程序的程序包作为其进程的一部分后，你可以将 Sequencer 生成的文件复制到应用程序虚拟化管理服务器，并使它们可用于流处理。

可用包显示在应用程序虚拟化管理控制台左窗格中的**程序包**容器下方。 导入带有 Sequencer 项目（SPRJ）文件或开放软件描述符（OSD）文件的应用程序时，将在**程序包**容器中显示相关条目。 在应用程序虚拟化服务器管理控制台中，你可以部署、升级或删除程序包和版本。

每个虚拟应用程序都有一个关联的程序包。 此程序包包含以下文件：

-   SFT ——将应用程序流式处理到客户端的文件。

-   OSD-开放软件描述符文件包含查找和启动应用程序所需的信息。

-   .ICO-图标文件，直观地表示用户界面和快捷方式中的应用程序。

-   SPRJ-Sequencer 项目文件。

导入 SPRJ 文件时，默认情况下，所有已排序的应用程序均可供部署，但应用程序不会启用流式处理。 你可以选择在程序包中传输所有或部分应用程序。 例如，如果已排序并导入 Microsoft Office，则可以选择不部署某些应用程序，例如 "保存我的设置" 向导。 在这种情况下，右键单击要部署的每个应用程序，选择 "**属性**"，并确保已清除 "**启用**" 框（空白）。 只有选中了 "**已启用**" 框的应用程序才会流入客户端计算机。

在 resequence 程序包并生成用于流处理的新 SFT 文件后，您可以通过应用程序虚拟化服务器管理控制台快速轻松地升级旧程序包。

需要使用 "**程序包**" 节点的唯一操作方案是在为程序包引入新版本（SFT 文件）时。 无论何时导入应用程序、为应用程序分配访问权限和许可证等，应用程序虚拟化系统都会在程序包级别跟踪此信息。 这意味着，当你授权用户使用应用程序时，你将授予用户运行同一程序包中的任何应用程序的权限。

### 程序包版本

程序包版本由特定的 SFT 文件表示。 升级程序包（应用对应用程序的更新或将应用程序添加到程序包）时，将生成新的 SFT 文件。 每次创建新的 SFT 文件时，都将创建一个新的程序包版本。

通过应用程序虚拟化服务器管理控制台导入应用程序时，如果现有程序包和程序包版本尚不存在，则该软件会自动创建该程序包和程序包版本。

## 相关主题


[关于 Application Virtualization 应用程序](about-application-virtualization-applications.md)

[关于 Application Virtualization Server Management Console](about-the-application-virtualization-server-management-console.md)

[如何在 Server Management Console 中管理程序包](how-to-manage-packages-in-the-server-management-console.md)

 

 





