---
title: Windows Virtual PC 应用程序排除列表
description: Windows Virtual PC 应用程序排除列表
author: dansimp
ms.assetid: 7715f198-f5ed-421e-8740-0cec2ca4ece3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 04/28/2017
ms.openlocfilehash: 190049ce99865ef237d8d26e14a8279def7da521
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803419"
---
# Windows Virtual PC 应用程序排除列表


在某些情况下，你可能不希望将 MED-V 工作区中安装的应用程序发布到主计算机的 "**开始**" 菜单。 你可以按照有关[如何在 Med-v 工作区中发布和取消发布应用程序](how-to-publish-and-unpublish-an-application-on-the-med-v-workspace.md)的说明，取消发布这些应用程序。 但是，如果程序自动更新，也可能会自动重新发布它。 这使你必须再次取消发布该应用程序。

Windows 虚拟 PC 包含一个称为 "排除列表" 的功能，可用于指定不希望发布到主机 "**开始**" 菜单的某些已安装应用程序。 "排除列表" 位于 HKLM\\Software\\Microsoft\\Windows NT\\CurrentVersion\\Virtual Machine\\VPCVAppExcludeList 项的来宾注册表中，列出未发布到主机 "**开始**" 菜单的应用程序。 你可以将 "排除列表" 视为永久取消发布指定的应用程序，因为列出的应用程序的任何自动更新将不会导致自动重新发布。

## 使用 Windows 虚拟 PC 中的排除列表管理应用程序


****

1.  以全屏打开 MED-V 工作区。

    有关使用 MED-V 管理工具包以全屏模式打开 MED-V 工作区的信息，请参阅[查看 Med-v 工作区配置](viewing-med-v-workspace-configurations.md#bkmk-fullscreen)。 或者，您可以通过单击 "**开始**"，单击 "**所有程序**"，单击 " **windows 虚拟 Pc**"，单击 " **windows 虚拟**pc"，然后双击 "med-v" 工作区，以在全屏方式手动打开它。

2.  在 MED-V 工作区 Windows 虚拟 PC 窗口中，打开注册表编辑器。

    单击 "**开始**"，单击 "**运行**"，然后键入 regedit。 然后单击 **"确定"**。

3.  在注册表编辑器中，找到 HKLM\\Software\\Microsoft\\Windows NT\\CurrentVersion\\Virtual Machine\\VPCVAppExcludeList 注册表项。

4.  为不希望发布到主机计算机 "**开始**" 菜单的已安装应用程序创建新的注册表值。 例如，如果要取消发布自动发布的程序 Microsoft Silverlight，请按照下列步骤操作：

    1.  突出显示 VPCVAppExcludeList 注册表项，单击 "**编辑**"，单击 "**新建**"，然后单击 "**字符串值**"。

    2.  输入新注册表值的名称。 例如，对于 Microsoft Silverlight，你可以输入 sllauncher.exe。

    3.  双击新的注册表值，然后输入值数据。

        "值数据" 是要取消发布的命令的完整路径。 你可以通过右键单击不希望发布的应用程序的 "**开始**" 菜单上的快捷方式，然后单击 "**属性**" 来查找完整路径。 完整路径在 "**目标**" 下的 "**快捷方式**" 选项卡中列出。

        例如，对于程序 Microsoft Silverlight，完整路径可能是 "C:\\program files Files\\Microsoft Silverlight\\4.0.50917.0\\Silverlight.Configuration.exe"。

        **重要提示** 如果适用，在将完整路径输入到 "值数据" 字段中时，请删除完整路径中的引号。

         

5.  关闭注册表编辑器，然后重新启动 MED-V 工作区虚拟机。

    应用程序仍安装在 MED-V 工作区中，但现在从主机 "**开始**" 菜单中被删除。

还可以通过从 VPCVAppExcludeList 键中删除相应的值来将排除的应用程序发布到主机 "**开始**" 菜单。 例如，若要重新发布 Microsoft Silverlight，请右键单击注册表值 sllauncher.exe 然后选择 "**删除**"。

## 相关主题


[MED-V 的技术参考](technical-reference-for-med-v.md)

[如何在 MED-V 工作区上发布和取消发布应用程序](how-to-publish-and-unpublish-an-application-on-the-med-v-workspace.md)

 

 





