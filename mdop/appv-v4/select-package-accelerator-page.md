---
title: “选择包加速器”页
description: “选择包加速器”页
author: dansimp
ms.assetid: 865c2702-4dfd-41ae-8cfc-3514d5f41f76
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a5723f8244563539c27a3fa915c1a680905e61e9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798802"
---
# “选择包加速器”页


使用 "**选择包加速器**" 页面选择将用于创建新虚拟应用程序包的程序包加速器。 必须将程序包加速器复制到运行 App-v Sequencer 的计算机上的文件夹中。 有关详细信息，请参阅[关于 app-v 程序包加速器（app-v 4.6 SP1）](about-app-v-package-accelerators--app-v-46-sp1-.md)。

仅从您信任的发布者运行程序包加速器。 程序包加速器通常包含数字签名。 数字签名是一种电子安全标记，可帮助指示软件的发布者，以及在转换最初签名后程序包是否已被篡改。 如果你使用的转换已由 publisher 进行了数字签名，并且发布者已使用证书颁发机构验证了其身份，则可以更有把握地确保该转换来自特定的发布者且未被更改。

如果以下任何条件成立，则 App-v 排序器将通知你：

-   所选转换尚未进行数字签名。

-   所选转换已由尚未使用证书颁发机构验证其身份的发布者进行签名。

-   所选转换在经过数字签名和释放后已被更改。

如果在使用包加速器时显示这些消息中的任何消息，请访问程序包加速器 publisher 的网站，获取经过数字签名的转换版本。

此页面包含以下元素：

<a href="" id="browse"></a>**浏览**  
单击 "**浏览**" 以指定将用于创建虚拟应用程序包的程序包加速器。 保存在运行 Sequencer 的计算机上本地指定的包加速器。

## 相关主题


[Sequencer 向导 - 包加速器 (AppV 4.6 SP1)](sequencer-wizard---package-accelerator--appv-46-sp1-.md)

 

 





