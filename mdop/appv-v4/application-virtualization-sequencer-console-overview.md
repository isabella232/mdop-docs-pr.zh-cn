---
title: Application Virtualization Sequencer 控制台概述
description: Application Virtualization Sequencer 控制台概述
author: dansimp
ms.assetid: 681bb40d-2937-4645-82aa-4a44775232d8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4c2f977fccaaded0309181a1d74c16b749498abb
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803119"
---
# Application Virtualization Sequencer 控制台概述


应用程序虚拟化（App-v） Sequencer 创建应用程序，以便可以在虚拟环境中运行这些应用程序作为虚拟应用程序。 对应用程序进行排序后，它可以从 App-v 服务器运行到使用名为 "流式处理" 的进程为远程桌面服务（以前称为 "终端服务"）运行 app-v 桌面客户端或 App-v 客户端的计算机。 App-v 排序器监视应用程序的安装和设置过程，并记录应用程序在虚拟环境中运行所需的所有信息。 此过程还确定哪些文件和配置适用于所有用户以及用户可以自定义的配置。 虚拟应用程序在目标计算机上运行，并且对在目标计算机上运行的操作系统或在目标计算机上安装的任何应用程序不起作用。

## 应用程序虚拟化 Sequencer 安全注意事项


App-v Sequencer 运行使用本地系统帐户在排序时间内检测到的所有服务，并且不会在服务控制请求上强制执行安全描述符。 如果该服务是使用其他用户帐户安装的，或者安全描述符打算授予不同的用户组特定的服务权限，请仔细考虑是否应虚拟化该服务。 在某些情况下，应在本地安装该服务，以确保保留预期的服务安全。

## 应用程序虚拟化 Sequencer 控制台菜单选项


App-v Sequencer 控制台提供以下菜单项：

-   **文件**-包含帮助创建、打开、修改和保存顺序应用程序的各种命令。

-   **编辑**-包含用于编辑现有虚拟应用程序的各种命令。

-   **视图**-包含用于查看虚拟应用程序属性的各种命令。

-   **工具**-包含用于配置虚拟应用程序的各种工具和诊断。

## Application Virtualization Sequencer 控制台工具栏选项


App-v Sequencer 控制台提供以下工具栏按钮：

-   **新程序包**-单击以创建新的序列化应用程序。

-   **打开**-单击以打开 App-v Sequencer 控制台中的序列化应用程序包。

-   **打开以进行升级**-单击以打开序列化的应用程序以升级或应用更新。

-   **保存**-单击以保存序列化的虚拟应用程序。

-   **排序向导**-单击以打开 "顺序向导"。 如果在 "**工具**选项" 下的 "**常规**" 选项卡上进行任何更改，则应使用此按钮启动顺序向导  /  **Options**。

## 虚拟应用程序选项卡


在 App-v Sequencer 控制台中查看虚拟应用程序时，将显示以下选项卡：

-   **属性**-显示所选虚拟应用程序的相关信息。 你可以更新与虚拟应用程序关联的**程序包名称**和**注释**。

-   **部署**-显示有关目标计算机将如何访问虚拟应用程序的信息。 你可以配置虚拟应用程序交付方法，并且可以配置哪些操作系统必须在目标计算机上运行。 您还可以配置关联的输出选项。 如果你计划让客户从文件访问虚拟应用程序，请在指定 path： **File://server/share/path/.sft**时使用以下格式。 选择 "**强制安全描述符**" 以保留升级期间与程序包相关联的安全，或者在升级期间重置这些权限。

-   **更改历史记录**-显示已对虚拟应用程序进行的更新的相关信息。

-   **文件**-显示与所选虚拟应用程序关联的文件。 你可以使用相应的字段对关联的文件属性进行细微修订。

-   **虚拟注册表**-显示与所选虚拟应用程序关联的虚拟注册表。 您可以通过右键单击相应的条目来添加或删除注册表项。

-   **虚拟文件系统**-显示与所选虚拟应用程序关联的虚拟文件系统。 通过右键单击相应的条目并选择该选项，可以在此选项卡上添加、删除或编辑文件系统条目。

-   **虚拟服务**-显示与所选虚拟应用程序关联的服务。

-   **OSD**—显示与虚拟应用程序相关联的开放式软件描述符（OSD）的相关信息。 你可以通过右键单击相应的条目并选择所需的操作来更新与 OSD 文件相关联的文件。

## 相关主题


[Application Virtualization Sequencer](application-virtualization-sequencer.md)

 

 





