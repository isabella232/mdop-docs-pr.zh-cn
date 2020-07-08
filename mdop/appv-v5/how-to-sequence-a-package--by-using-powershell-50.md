---
title: 如何使用 PowerShell 对程序包进行排序
description: 如何使用 PowerShell 对程序包进行排序
author: dansimp
ms.assetid: b41feed9-d1c5-48a3-940c-9a21d594f4f8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: bbb9641ba75eda4d190892fa2bd0043c92ed9006
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798361"
---
# 如何使用 PowerShell 对程序包进行排序


使用以下过程，使用 PowerShell 创建新的 app-v 5.0 程序包。

**注意** 在使用此过程之前，必须将关联的安装程序文件复制到运行 sequencer 的计算机，并且已阅读并了解[有关应用 V 5.0 排序器和客户端部署规划](planning-for-the-app-v-50-sequencer-and-client-deployment.md)的 sequencer 部分。

 

**使用 PowerShell 创建新的虚拟应用程序**

1.  安装 app-v 5.0 sequencer。 有关安装 sequencer 的详细信息，请参阅[如何安装 sequencer](how-to-install-the-sequencer-beta-gb18030.md)。

2.  若要打开 PowerShell 控制台，请单击 "**开始**"，然后键入**powershell**。 右键单击**Windows PowerShell**，然后选择**以管理员身份运行**。

3.  使用 PowerShell 控制台，键入以下内容： **import-module appvsequencer**。

4.  若要创建程序包，请使用**AppvSequencerPackage** cmdlet。 创建程序包需要以下参数：

    -   **Name** -指定程序包的名称。

    -   **PrimaryVirtualApplicationDirectory** -指定将用于安装应用程序的目录的路径。 此路径必须存在。

    -   **安装**程序-指定关联的应用程序安装程序的路径。

    -   **Path** -指定程序包的输出目录。

    例如：

    **新-AppvSequencerPackage-程序包的名称-程序包的 &lt; &gt; PrimaryVirtualApplicationDirectory &lt; 路径到 &gt; &lt; 安装程序可执行文件的 &gt; OutputPath &lt; 目录的程序包根安装程序路径&gt;**

    等待排序器创建程序包。 使用 PowerShell 创建程序包可能需要一些时间。 如果未成功创建程序包，则会返回错误。

    以下列表显示可与**AppvSequencerPackage** cmdlet 一起使用的其他可选参数：

    -   AcceleratorFilePath –指定要生成程序包的加速器 .cab 文件的路径。

    -   InstalledFilesPath-指定保存应用程序的本地已安装文件的路径。

    -   InstallMediaPath-指定安装媒体的路径

    -   TemplateFilePath-如果要自定义排序过程，请指定模板文件的路径。

    -   FullLoad-指定程序包必须完全下载到运行 App-v 5.0 的计算机，然后才能打开。

    已**获得有关 app-v 的建议**？ 在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。 **遇到了 app-v 问题？** 使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相关主题


[使用 PowerShell 管理 App-V](administering-app-v-by-using-powershell.md)

 

 





