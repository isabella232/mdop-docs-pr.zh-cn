---
title: 如何更改部署属性
description: 如何更改部署属性
author: dansimp
ms.assetid: 0a214a7a-cc83-4d04-89f9-5727153be918
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: dfb42962d41159479db61da9c3beb3771ef35502
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801667"
---
# 如何更改部署属性


你可以使用以下过程更改你要对其进行排序的应用程序的 "**部署**" 选项卡信息，包括应用程序虚拟化服务器 URL、虚拟化应用程序所需的操作系统以及要安装的虚拟应用程序的输出选项。

**更改服务器 URL**

1.  从下拉列表框中选择 "流协议"。

2.  输入虚拟应用程序服务器或服务器组负载平衡器的主机名。 您可以使用实际的主机名或 IP 地址。

3.  指定虚拟应用程序服务器或负载平衡器将在其上侦听针对流应用的应用程序虚拟化桌面客户端请求的端口号。

4.  指定存储软件包的虚拟应用程序服务器上的相对路径。

**更改应用程序操作系统要求**

1.  若要添加所需操作系统，请在 "**可用**" 列表中选择它，然后单击指向**所选**操作系统列表控件的箭头按钮。

2.  若要删除操作系统，请在**所选**列表控件中选择它，然后单击指向**可用**操作系统列表控件的箭头按钮。

**更改应用程序输出选项**

1.  从 "**压缩算法**" 下拉列表中，选择要在流式处理应用程序时使用的压缩方法。

2.  选中 "**强制执行安全描述符**" 复选框，以确保打包应用程序的安全描述符在部署时生效。

3.  选择 "**生成差异文件**" 以从以前的已排序版本生成应用程序的差异文件。

4.  选择 "**生成 Microsoft Windows Installer （MSI）程序包**" 以创建一个安装程序包。

## 相关主题


[关于“部署”选项卡](about-the-deployment-tab.md)

[Sequencer 控制台](sequencer-console.md)

 

 





