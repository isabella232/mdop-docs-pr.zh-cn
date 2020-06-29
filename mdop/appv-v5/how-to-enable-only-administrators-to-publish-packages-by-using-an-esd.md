---
title: 如何使用 ESD 来仅允许管理员发布程序包
description: 如何使用 ESD 来仅允许管理员发布程序包
author: dansimp
ms.assetid: 03367b26-83d5-4299-ad52-b9177b9cf9a8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 341e86ca806c5acc736c78cf8072aab6fb4286df
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798463"
---
# 如何使用 ESD 来仅允许管理员发布程序包


从 app-v 5.0 SP3 开始，你可以配置 App-v 客户端，以便只有管理员（而非最终用户）可以发布或取消发布程序包。 在早期版本的 App-v 中，你不能阻止最终用户执行这些任务。

**仅允许管理员发布或取消发布程序包**

1.  导航到以下组策略对象节点：

    **计算机配置 &gt;策略 &gt; 管理模板 &gt; 系统 &gt; 应用程序-V &gt; 发布**。

2.  启用 "**要求发布为管理员**组" 策略设置。

    若要另外使用 PowerShell 设置此项，请参阅[如何使用 Powershell 管理独立计算机上运行的 V 5.0 程序包](how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md#bkmk-admins-pub-pkgs)。

    已**获得有关 app-v 的建议**？ 在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。 **遇到了 app-v 问题？** 使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

 

 





