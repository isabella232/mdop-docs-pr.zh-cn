---
title: 如何使用管理控制台发布程序包
description: 如何使用管理控制台发布程序包
author: dansimp
ms.assetid: e34d2bcf-15ac-4a75-9dc8-79380b36a25f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b0783a05f658da5e93603e26dc7e9581d26b81f9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798378"
---
# 如何使用管理控制台发布程序包


使用以下过程发布 App-v 5.1 程序包。 发布程序包后，运行 App-V 5.1 客户端的计算机可以访问并运行该程序包中的应用程序。

**注意** 只有在 App-v 5.0 SP3 中才支持仅允许管理员发布或取消发布程序包（如下所述）的功能。

 

**发布 app-v 5.1 程序包**

1.  在 App-v 5.1 管理控制台中。 单击或右键单击要发布的程序包的名称。 选择**发布**。

2.  查看 "**状态**" 列以验证程序包是否已发布，现已推出。 如果程序包可用，将显示 "**已发布**状态"。

    如果程序包未成功发布，将显示**未发布**的状态，以及解释程序包不可用的原因的错误文本。

**仅允许管理员发布或取消发布程序包**

1.  导航到以下组策略对象节点：

    **计算机配置 &gt;策略 &gt; 管理模板 &gt; 系统 &gt; 应用程序-V &gt; 发布**。

2.  启用 "**要求发布为管理员**组" 策略设置。

    若要另外使用 PowerShell 设置此项，请参阅[如何使用 Powershell 管理独立计算机上运行的 V 5.1 程序包](how-to-manage-app-v-51-packages-running-on-a-stand-alone-computer-by-using-powershell.md#bkmk-admins-pub-pkgs)。

    已**获得有关 app-v 的建议**？ 在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。 **遇到了 app-v 问题？** 使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相关主题


[App-V 5.1 的操作](operations-for-app-v-51.md)

[如何使用管理控制台配置对程序包的访问权限](how-to-configure-access-to-packages-by-using-the-management-console-51.md)

 

 





