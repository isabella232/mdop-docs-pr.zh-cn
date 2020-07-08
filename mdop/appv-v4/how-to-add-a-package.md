---
title: 如何添加程序包
description: 如何添加程序包
author: dansimp
ms.assetid: 5407fdbe-e658-44f6-a9b8-a566b81dedce
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c580d7d131017c52e278adda0208ffcb2e86ccf2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802960"
---
# 如何添加程序包


你可以通过以下方式从应用程序虚拟化服务器管理控制台添加程序包：

-   导入应用程序，该应用程序将在进程中自动创建程序包。

-   手动添加程序包。

建议你导入应用程序，而不是手动添加它们。 有关导入应用程序的详细信息，请参阅[如何导入应用程序](how-to-import-an-applicationserver.md)。

**手动添加程序包**

1.  在应用程序虚拟化服务器管理控制台中，右键单击左窗格中的 "**程序包**" 节点，然后选择 "**新建程序包**"。

2.  在 "**新建程序包**" 对话框中，在 "**包名称**" 字段中键入名称。

3.  在 "**文件包文件的完整路径**" 字段中，浏览或键入路径名称。 这必须是一个 SFT 文件。

    **注意** 如果浏览到 SFT 文件，请将本地路径（如 C:\\program files Files\\User\ _Apps \\Virtual\ _App \ _Server \\content）替换为服务器的静态主机名或 IP 地址。 使用变量 *% SFT \ _SOFTGRIDSERVER%* 需要每客户端计算机配置。

    在引用虚拟应用程序服务器的对话框中，必须使用用户可以访问的网络位置，如服务器的静态主机名或 IP 地址。 应用程序的开放式软件描述符（OSD）文件可以将占位符变量 *% SFT \ _SOFTGRIDSERER%* 替换为服务器的静态主机名或 IP 地址。 如果保留了占位符变量，则必须在将访问该服务器的每台客户端计算机上设置此变量。 在 SFT \ _SOFTGRIDSERVER 的每台计算机上设置一个用户或系统变量。 变量值必须是服务器的静态主机名或 IP 地址。 如果设置了变量，请退出客户端会话，注销并重新登录到 Microsoft Windows，然后在运行会话且具有变量集的每台计算机上重新启动会话。

     

4.  单击“下一步”****。

5.  "**摘要**" 对话框显示文件位置，并提示您将文件复制到该位置（如果尚未执行此操作）。 验证信息后，单击 "**完成**"。

    **注意** 如果你在远程服务器上管理应用程序，请在 "下一个" 对话框中，只键入相对于服务器的内容根的文件路径。

     

## 相关主题


[如何导入应用程序](how-to-import-an-applicationserver.md)

[如何在 Server Management Console 中管理程序包](how-to-manage-packages-in-the-server-management-console.md)

 

 





