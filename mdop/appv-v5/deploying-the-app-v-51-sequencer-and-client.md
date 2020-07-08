---
title: 部署 App-V 5.1 Sequencer 和 Client
description: 部署 App-V 5.1 Sequencer 和 Client
author: dansimp
ms.assetid: 74f32794-4c76-436f-a542-f9e95d89063d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/21/2016
ms.openlocfilehash: 3b78059e5005f563bb99d7e6f4b5fe0af2eae8d5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798578"
---
# 部署 App-V 5.1 Sequencer 和 Client


Microsoft Application Virtualization （App-v） 5.1 Sequencer 和客户端使管理员能够虚拟化和运行虚拟化的应用程序。

## 部署客户端


App-v 5.1 客户端是在目标计算机上运行虚拟化应用程序的组件。 客户端使用户能够与图标交互并双击文件类型，以便他们可以启动虚拟化的应用程序。 客户端还可以从管理服务器获取虚拟应用程序内容。

[如何部署 App-V Client](how-to-deploy-the-app-v-client-51gb18030.md)

[如何卸载 App-V 5.1 Client](how-to-uninstall-the-app-v-51-client.md)

[如何在同一台计算机上部署 app-v 4.6 和 app-v 5.1 客户端](how-to-deploy-the-app-v-46-and-the-app-v--51-client-on-the-same-computer.md)

## 客户端配置设置


App-v 5.1 客户端将其配置存储在注册表中。 如果你了解注册表中的数据的格式，则可以收集有关客户端的一些有用信息。 您也可以通过更改注册表项来配置多个客户端操作。

[关于 Client 配置设置](about-client-configuration-settings51.md)

## 使用 ADMX 模板和组策略配置客户端


你可以使用 Microsoft ADMX 模板来配置 app-v 5.1 客户端和远程桌面服务客户端的客户端设置。 ADMX 模板通过使用现有组策略基础结构管理常见的客户端配置，其中包括 App-v 5.1 客户端配置的设置。

**重要提示** 您可以从 Microsoft 下载中心获取 App-v 5.1 ADMX 模板。

 

下载并安装 ADMX 模板后，请在将用于管理组策略的计算机上执行以下步骤。 这通常是域控制器。

1.  将该**admx**文件保存到以下目录： **Windows \\ PolicyDefinitions**

2.  将**adml**文件保存到以下目录： **Windows \\ PolicyDefinitions \\ &lt; &gt; 语言目录**

完成上述步骤后，您可以使用**组策略管理**控制台管理 app-v 5.1 客户端配置设置。

App-v 5.1 客户端还将其配置存储在注册表中。 如果你了解注册表中数据的格式，则可以收集有关客户端的一些有用信息。 您也可以通过更改注册表项来配置多个客户端操作。

[如何使用 ADMX 模板和组策略修改 App-V 5.1 Client 配置](how-to-modify-app-v-51-client-configuration-using-the-admx-template-and-group-policy.md)

## 使用 "共享内容存储" 模式部署客户端


App-v 5.1 共享内容存储（SCS）模式使 SCS 应用-V 5.1 客户可以运行虚拟化的应用程序，而无需在本地保存任何关联的程序包数据。 所有需要的虚拟化软件包数据均通过网络传输;因此，你应仅在具有快速连接的环境中使用 SCS 模式。 "SCS" 模式支持远程桌面服务（RDS）和标准版本的 App-v 5.1 客户端。

**重要提示** 如果将 app-v 5.1 客户端配置为在 SCS 模式下运行，则从其流入的 app-v 5.1 程序包的位置必须可用，否则虚拟化程序包将失败。 此外，我们不建议将虚拟化应用程序部署到在 SCS 模式下通过 internet 运行 app-v 5.1 客户端的计算机。

 

此外，SCS 不是包含虚拟化程序包的物理位置。 它是一种允许应用-V 5.1 客户端通过网络传输所需的虚拟化包数据的模式。

SCS 模式在以下情况下很有用：

-   虚拟桌面基础结构（VDI）部署

-   远程桌面服务（RDS）部署

若要在你的环境中使用 SCS，必须启用 app-v 5.1 客户端以在 SCS 模式下运行。 应在安装期间指定此设置。 默认情况下，客户端未配置为使用 SCS 模式。 如果计划使用 SCS，则应使用建议的过程安装客户端。 但是，你可以通过在运行 app-v 5.1 客户端的计算机上输入以下 PowerShell 命令来配置现有的应用程序 V 5.1 客户端以在 SCS 模式下运行：

**set-AppvClientConfiguration-SharedContentStoreMode 1**

当管理员在 SCS 模式下运行 App-v 5.1 客户端的计算机上预加载某些虚拟应用程序时，可能会出现这种情况。 可通过将 PowerShell 命令添加、发布和装载程序包来完成此操作。 例如，如果在所有计算机上预加载了程序包，则管理员可以使用 PowerShell 命令添加、发布和装入程序包。 程序包不会通过网络传输，因为它将在本地存储。

[如何针对共享内容存储模式安装 App-V 5.1 Client](how-to-install-the-app-v-51-client-for-shared-content-store-mode.md)

## 部署 Sequencer


Sequencer 是一个工具，用于将标准应用程序转换为虚拟程序包，以便部署到运行 app-v 5.1 客户端的计算机。 排序器可提供简单且可预测的转换过程，对之前的排序工作流进行最少的更改。 此外，排序器允许用户更轻松地配置应用程序以启用虚拟化应用程序的连接。

有关 app-v 5.1 排序器中的更改的列表，请参阅[关于 app-V 5.1](about-app-v-51.md)。

[如何安装 Sequencer](how-to-install-the-sequencer-51beta-gb18030.md)

## <a href="" id="---------app-v-5-1-client-and-sequencer-logs"></a> App-v 5.1 客户端和 Sequencer 日志


在使用 app-v 5.1 时，可以使用 app-v 5.1 Sequencer 日志信息来帮助解决 Sequencer 安装和操作事件。 与排序器相关的日志信息可以通过**事件查看器**进行检查。 下一行显示与 Sequencer 相关的事件的特定路径：

**事件查看器 \\ 应用程序和服务日志 \\ Microsoft \\ App V**。与排序器相关的事件预置了**AppV \ _Sequencer**。 与客户端相关的事件预置到**AppV \ _Client**。

## 用于部署 Sequencer 和客户端的其他资源


[部署 App-V 5.1](deploying-app-v-51.md)

[规划 App-V 5.1](planning-for-app-v-51.md)






 

 





