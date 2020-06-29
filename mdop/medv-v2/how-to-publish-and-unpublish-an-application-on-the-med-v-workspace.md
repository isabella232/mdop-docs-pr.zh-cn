---
title: 如何在 MED-V 工作区上发布和取消发布应用程序
description: 如何在 MED-V 工作区上发布和取消发布应用程序
author: dansimp
ms.assetid: fd5a62e9-0577-44d2-ae17-61c0aef78ce8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: cc8f9579d800aa0e5da0d67e0cd71bcae5e912a0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804065"
---
# 如何在 MED-V 工作区上发布和取消发布应用程序


即使在 MED-V 工作区中安装了应用程序，你也可能还需要先发布应用程序，然后才能向最终用户提供该应用程序。 默认情况下，大多数应用程序在安装时发布，并且创建和启用快捷方式。

在某些情况下，你可能希望在 MED-V 工作区上安装应用程序，而不让最终用户（如病毒扫描软件）使用这些应用程序。 同样，你希望在某些情况下发布安装在以前对最终用户不可用的 MED-V 工作区中安装的应用程序。 例如，如果安装未在 "**开始**" 菜单上自动创建快捷方式，则可能必须发布已安装的应用程序。

**重要提示** 如果发布不支持 UNC 路径的应用程序，我们建议你将应用程序映射到驱动器。

 

你可以通过执行以下任务之一将应用程序发布或取消发布到已部署的 MED-V 工作区：

**发布或取消发布已安装的应用程序**

1.  若要在已部署的 MED-V 工作区上发布应用程序，请将该应用程序的快捷方式复制到虚拟机上的以下文件夹：

    C:\\Documents 和 Settings\\All Users\\Start 菜单

    如有必要，请使用组策略或 ESD 系统部署脚本，该脚本将该应用程序的快捷方式复制到 "所有 Users\\Start" 菜单文件夹。

2.  若要在已部署的 MED-V 工作区上取消发布应用程序，请从虚拟机上的以下文件夹中删除该应用程序的快捷方式：

    C:\\Documents 和 Settings\\All Users\\Start 菜单

    如有必要，请使用组策略或 ESD 系统部署脚本，该脚本从 "所有 Users\\Start" 菜单文件夹中删除该应用程序的快捷方式。

    **注意** 通常，卸载应用程序时，快捷方式会自动从主机 "**开始**" 菜单中删除。 但是，在某些情况下（例如对于为共享计算机的所有用户配置的 MED-V 工作区），可能需要在卸载应用程序后手动删除 "**开始**" 菜单上的快捷方式。 最终用户可以通过右键单击快捷方式并选择 "**删除**" 来执行此操作。

     

若要测试应用程序是否已发布或未发布，请在 MED-V 工作区中验证是否有相应的快捷方式可用。

**注意** Windows XP SP3 中包含的应用程序和位于虚拟机 "开始" 菜单文件夹中的应用程序不会自动发布到主机。 它们由阻止自动发布的注册表设置控制。 有关详细信息，请参阅[Windows 虚拟 PC 应用程序排除列表](windows-virtual-pc-application-exclude-list.md)。

 

**发布 "控制面板" 项目**

1.  在目标是项目名称的虚拟机（如 C:\\WINDOWS\\system32\\appwiz.cpl）上创建快捷方式。

    快捷方式必须在 "%ALLUSERSPROFILE%\\Start Menu\\" 文件夹或其中一个子文件夹中创建或移动到其中一个子文件夹。

    项目将发布到主机 "开始" 菜单文件夹中相应位置的主计算机。

2.  启动主机中项目的快捷方式。

**小心** 创建快捷方式时，请不要指定% SystemRoot% \\control.exe。 此应用程序将不会发布，因为它包含在阻止自动发布的注册表设置中。

 

**MED-V 如何处理自动应用程序发布**

1.  在应用程序发布期间，MED-V 通过尝试匹配存在于来宾中的文件夹层次结构，将来宾虚拟机中的快捷方式复制到主机计算机。 通过执行此操作，MED-V 通过执行以下步骤将来自来宾的快捷方式复制到主机：

    1.  MED-V 尝试在名为与快捷方式所在的来宾中的文件夹相同的主机上的 "开始 Menu\\Programs" 下找到某个文件夹。

    2.  如果没有匹配的文件夹，则 MED-V 会尝试在主机 "开始" 菜单文件夹中查找与快捷方式所在的来宾中的文件夹同名的文件夹。

    3.  如果没有匹配的文件夹，则 MED-V 会将指向主机上默认文件夹的快捷方式复制到 "开始 Menu\\Programs" 文件夹。

2.  应用程序发布过程示例：

    1.  如果将应用程序快捷方式发布到来宾中的 "开始 Menu\\Programs\\AppShortcuts" 文件夹，则 MED-V 将在主机中查找 "开始 Menu\\Programs\\ AppShortcuts" 文件夹，如果找到，则将快捷方式复制到该文件夹。

    2.  如果找不到文件夹，则 MED-V 在主机中查找开始 Menu\\AppShortcuts 文件夹，如果找到，则将快捷方式复制到该文件夹。

    3.  如果找不到文件夹，则 MED-V 会将快捷方式复制到 "开始 Menu\\Programs" 文件夹。

**注意** 在 MED-V 的主机 "开始" 菜单文件夹中，文件夹必须已存在，才能复制快捷方式。 如果文件夹尚不存在，则 MED-V 不会创建该文件夹。

 

## 相关主题


[在 MED-V 工作区上安装和删除应用程序](installing-and-removing-an-application-on-the-med-v-workspace.md)

[管理 MED-V 工作区的软件更新](managing-software-updates-for-med-v-workspaces.md)

[Windows Virtual PC 应用程序排除列表](windows-virtual-pc-application-exclude-list.md)

 

 





