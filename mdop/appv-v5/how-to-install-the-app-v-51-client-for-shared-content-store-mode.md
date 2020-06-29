---
title: 如何针对共享内容存储模式安装 App-V 5.1 Client
description: 如何针对共享内容存储模式安装 App-V 5.1 Client
author: dansimp
ms.assetid: 6f3ecb1b-b5b5-4ae0-8de9-b4ffdfd2c216
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: a7ce8114a44762180bf9bb0240913dca50c55d31
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798449"
---
# 如何针对共享内容存储模式安装 App-V 5.1 Client


使用以下过程安装 Microsoft Application Virtualization （App-v）5.1 客户端，以便它使用 App-v 5.1 共享内容存储（SCS）模式。 应确保安装了要安装到的计算机上已安装所有必需的先决条件。 使用以下链接查看 app-v [5.1 先决条件](app-v-51-prerequisites.md)。

**注意** 在执行此过程之前，如有必要，请卸载 app-v 5.1 客户端的任何现有版本。

 

有关 SCS 模式的详细信息，请参阅[Microsoft app-v 5.0 中的共享内容存储（位于后台）-后台](https://go.microsoft.com/fwlink/?LinkId=316879)（ https://go.microsoft.com/fwlink/?LinkId=316879) 。

**为 SCS 模式安装和配置 app-v 5.1 客户端**

1.  将 app-v 5.1 客户端安装文件复制到将在其上安装的计算机。 打开命令行，并从保存安装文件的目录中，键入以下选项之一，具体取决于你正在安装的客户端版本：

    -   若要安装 RDS 5.1 客户端类型的 RDS 版本，请执行以下操作： **appv\_client\_setup\_rds.exe/SHAREDCONTENTSTOREMODE = 1/q**

    -   若要安装标准版本的 App-v 5.1 客户端类型，请执行以下操作： **appv\_client\_setup.exe/SHAREDCONTENTSTOREMODE = 1/q**

        **重要提示** 必须执行静默式安装，否则安装将失败。

         

2.  完成安装后，你可以将程序包部署到运行客户端的计算机上，所有程序包内容都将跨网络进行传输。

    已**获得有关 app-v 的建议**？ 在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。 **遇到了 app-v 问题？** 使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相关主题


[部署 App-V 5.1 Sequencer 和 Client](deploying-the-app-v-51-sequencer-and-client.md)

 

 





