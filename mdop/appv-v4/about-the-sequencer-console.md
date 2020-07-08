---
title: 关于 Sequencer 控制台
description: 关于 Sequencer 控制台
author: dansimp
ms.assetid: 36ecba89-a0f5-4d4d-981c-7f581aa43695
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 21d1c668e9d6cbd51dd852cf40799d5df072bb00
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802404"
---
# 关于 Sequencer 控制台


开始使用 Microsoft Application Virtualization （App-v） sequencer 之前，你应该熟悉有关 App-v sequencer 控制台的以下信息。 以下部分介绍了在 Sequencer 控制台中可用的工具。

## 应用程序虚拟化 Sequencer 控制台菜单选项


App-v Sequencer 控制台提供以下菜单项：

-   **File** -包含帮助创建、打开、修改和保存顺序应用程序的各种命令。

-   **Edit** -包含用于编辑现有虚拟应用程序的各种命令。

-   **视图**-包含用于查看虚拟应用程序属性的各种命令。

-   **工具**-包含用于配置虚拟应用程序的各种工具和诊断。

## <a href="" id="application-virtualization-sequencer-console-toolbar-options-"></a>Application Virtualization Sequencer 控制台工具栏选项


App-v Sequencer 控制台提供以下工具栏按钮：

-   **新建程序包**-单击以创建新的序列化应用程序。

-   在 App-v Sequencer 控制台中**打开**并单击以打开序列化应用程序包。

-   **打开以进行升级**-单击以打开序列化的应用程序以升级或应用更新。

-   单击 "**保存**" 以保存序列化的虚拟应用程序。

-   **排序向导**-单击以打开 "顺序向导"。 如果在 "**工具**选项" 下的 "**常规**" 选项卡上进行任何更改，则应使用此按钮启动顺序向导  /  **Options**。

## 虚拟应用程序选项卡


在 App-v Sequencer 控制台中查看虚拟应用程序时，将显示以下选项卡：

-   **属性**-显示有关所选虚拟应用程序的信息。 你可以更新与虚拟应用程序关联的程序包名称和注释。

-   **部署**-显示有关目标计算机将如何访问虚拟应用程序的信息。 你可以配置虚拟应用程序交付方法，并且可以配置哪些操作系统必须在目标计算机上运行。 您还可以配置关联的输出选项。 如果你计划让客户从文件访问虚拟应用程序，请在指定 path： **File://server/share/path/.sft**时使用以下格式。 选择 "**强制安全描述符**" 以保留升级期间与程序包相关联的安全，或者在升级期间重置这些权限。

-   **更改历史记录**-显示已对虚拟应用程序进行的更新的相关信息。

-   **文件**-显示与所选虚拟应用程序关联的文件。 你可以使用相应的字段对关联的文件属性进行细微修订。

-   **虚拟注册表**-显示与所选虚拟应用程序关联的虚拟注册表。 您可以通过右键单击相应的条目来添加或删除注册表项。

-   **虚拟文件系统**-显示与所选虚拟应用程序关联的虚拟文件系统。 通过右键单击相应的条目并选择该选项，可以在此选项卡上添加、删除或编辑文件系统条目。

-   **虚拟服务**-显示与所选虚拟应用程序相关联的服务。

-   **OSD** -显示与虚拟应用程序相关联的开放式软件描述符（OSD）的相关信息。 你可以通过右键单击相应的条目并选择所需的操作来更新与 OSD 文件相关联的文件。

## 相关主题


[Application Virtualization Sequencer 概述](application-virtualization-sequencer-overview.md)

 

 





