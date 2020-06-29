---
title: 如何创建 App-V 项目模板 (App-V 4.6 SP1)
description: 如何创建 App-V 项目模板 (App-V 4.6 SP1)
author: dansimp
ms.assetid: 7e87fba2-b72a-4bc9-92b8-220e25aae99a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4e264d5c41b663bc9c450dc642e2b26297ee7ea1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801500"
---
# 如何创建 App-V 项目模板 (App-V 4.6 SP1)


你可以使用 App-v 项目模板来保存与现有虚拟应用程序包关联的常用设置。 然后，在你的环境中创建新的虚拟应用程序包时，可以应用这些设置，这有助于简化创建虚拟应用程序包的过程。

**注意** 仅当创建新的虚拟应用程序包时，才能应用 V 项目模板。 不支持将项目模板应用于现有虚拟应用程序包。

 

有关应用-V 项目模板的详细信息，请参阅[如何应用 App-v 项目模板（app-v 4.6 SP1）](how-to-apply-an-app-v-project-template--app-v-46-sp1-.md)。

App-v 项目模板与 App-v 应用程序加速器不同，因为 app-v 应用程序加速器属于特定于应用程序，而 app-v 项目模板可应用于多个应用程序。 此外，使用包加速器创建虚拟应用程序包时，不能使用项目模板。

使用 App-v 项目模板保存以下常规设置：

-   **高级监视选项**。 支持在监视期间、变基 **.dll**期间运行 Microsoft 更新。

-   **程序包部署设置**。 包含**协议**、**主机名**、**端口**、**路径**、**操作系统**、**强制执行安全描述符**、**创建 MSI**、**压缩程序包**。

-   **常规选项**。 允许**生成 Microsoft Windows Installer （MSI）** 程序包、**允许虚拟化事件**、**允许虚拟化服务**、**将程序包版本附加到文件名**。

-   **排除项目**。 包含 "排除" 模式列表。

**创建项目模板**

1.  若要启动 app-v 排序器，请在运行 app-v 排序器的计算机上，单击 "**启动**  /  **所有程序**  /  **microsoft application virtualization**  /  **microsoft application virtualization Sequencer**"。

2.  如果虚拟应用程序包当前已在 App-v Sequencer 中打开，请跳到此过程的步骤3。 若要打开包含要用 app-v 项目模板保存的设置的现有虚拟应用程序包，请单击 "**文件**  /  **打开**"，然后单击 "**编辑****包**"。 在 "**选择程序包**" 页面上，单击 "**浏览**" 并找到要打开的虚拟应用程序包。 单击**编辑**。

3.  在 app-v Sequencer 控制台中，单击 "**文件**  /  **另存为模板**"。 查看将与新模板一起保存的设置后，单击 **"确定"**。 指定将与新的 App-v 项目模板关联的名称。 单击 **“保存”**。

    新的 App-v 项目模板保存在此过程的步骤3中指定的目录中。

## 相关主题


[Application Virtualization Sequencer 的任务 (App-V 4.6 SP1)](tasks-for-the-application-virtualization-sequencer--app-v-46-sp1-.md)

[如何应用 App-V 项目模板 (App-V 4.6 SP1)](how-to-apply-an-app-v-project-template--app-v-46-sp1-.md)

 

 





