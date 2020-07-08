---
title: 压缩 MED-V 虚拟硬盘
description: 压缩 MED-V 虚拟硬盘
author: dansimp
ms.assetid: 5e6122d1-9847-4b33-adab-594919eec3c5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f71aefb1e4e901078b4d0a421065b7bd5acdf0ee
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803336"
---
# 压缩 MED-V 虚拟硬盘


尽管它是可选的，但你可以在配置 Windows 虚拟 PC 映像之前压缩虚拟硬盘（VHD）以回收空磁盘空间并减小 VHD 的大小。

**重要提示** 在继续操作之前，请创建 Windows XP 映像的备份副本。

 

**准备虚拟硬盘**

1.  打开 Windows XP 映像。

    单击 "**开始**"，单击 "**所有程序**"，单击 " **windows 虚拟 Pc**"，单击 " **Windows 虚拟 pc**"，然后双击 windows XP 映像。

2.  清除 DLL 缓存。

    1.  在虚拟机中的命令提示符处，键入**sfc/cachesize = 1**。

    2.  重新启动虚拟机。

    3.  在虚拟机中的命令提示符处，键入 " **sfc/purgecache**"。

3.  删除不必要的文件，例如 uninstallers、临时文件、日志文件、页面文件、共享文件夹等。

4.  关闭系统还原。 您也可以在 Sysprep.inf 文件中指定此步骤。

    1.  在 "**控制面板**" 中，双击 "**系统**"，然后选择 "**系统还原**" 选项卡。

    2.  选择 "**关闭系统还原**"，然后单击 **"确定"**。

5.  设置最大事件日志大小并清除所有事件。

    1.  打开 "事件查看器"。

        单击 "**开始**"，单击 "**控制面板**"，双击 "**管理工具**"，然后双击 "**事件查看器**"。

    2.  右键单击 "**应用程序**"，然后单击 "**属性**"。

    3.  在 "**日志大小**" 区域中，将**日志大小的最大值**设置为512kb，然后选择 "**根据需要覆盖事件**"。

    4.  单击 "**清除日志**"。 在出现的 "**事件查看器**" 对话框中，单击 "**否**"。

    5.  在 "**属性**" 窗口中，单击 **"确定"**。

    6.  对于**安全**和**系统**日志，请重复步骤 a 到 e。

6.  运行 "磁盘清理" 工具。

    依次单击 "**开始**"、"**所有程序**"、"**附件**"、"**系统工具**"，然后单击 "**磁盘清理**"。

7.  根据需要为你的应用程序配置你的页面文件。

    1.  在 "**控制面板**" 中，双击 "**系统**"，然后选择 "**高级**" 选项卡。

    2.  在 "**性能**" 区域中，单击 "**设置**"。

    3.  在 "**虚拟内存**" 区域中，单击 "**更改**"。

    4.  配置页面文件设置。

8.  关闭 Windows XP 映像。

**对虚拟硬盘进行碎片整理和预压缩**

1.  在运行 Windows 7 的主机上的 **"控制面板**" 中，单击 "**管理工具**"，双击 "**计算机管理**"，然后单击 "**磁盘管理**"。

2.  通过使用磁盘管理控制台，附加（装载）虚拟硬盘，然后对磁盘进行碎片整理。

3.  通过使用 ISO 提取工具，提取位于 \\Program Files\\Windows 虚拟 PC\\Integration 组件文件夹中的 precompact。

4.  使用 precompact.exe 程序压缩 Windows XP 虚拟硬盘。

5.  通过使用 "磁盘管理" 控制台，分离虚拟硬盘。

**压缩虚拟硬盘**

1.  打开 Windows 虚拟电脑。

    单击 "**开始**"，单击 "**所有程序**"，单击 " **windows 虚拟 pc**"，然后单击 " **windows 虚拟 pc**"。

2.  右键单击您的 Windows XP 映像，然后选择 "**设置**"。

3.  单击与你的 Windows XP 映像对应的**硬盘**，然后单击 "**修改**"。

4.  单击 "**压缩虚拟硬盘**"。

5.  单击 "**压缩**"，然后单击 **"确定"**。

创建压缩的虚拟硬盘的备份副本。

## 相关主题


[为 MED-V 配置 Windows Virtual PC 映像](configuring-a-windows-virtual-pc-image-for-med-v.md)

[MED-V 的技术参考](technical-reference-for-med-v.md)

 

 





