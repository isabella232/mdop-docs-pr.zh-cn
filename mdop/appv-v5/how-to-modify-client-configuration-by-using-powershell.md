---
title: 如何使用 PowerShell 修改客户端配置
description: 如何使用 PowerShell 修改客户端配置
author: dansimp
ms.assetid: 53ccb2cf-ef81-4310-a853-efcb395f006e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b5d3173944abfe2c2b3d30aa9654dae81f204a32
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798393"
---
# 如何使用 PowerShell 修改客户端配置


使用以下过程配置 App-v 5.0 客户端配置。

**使用 PowerShell 修改 App-v 5.0 客户端配置**

1.  若要使用 PowerShell 配置客户端设置，请使用**AppvClientConfiguration** cmdlet。

2.  若要修改客户端配置，请打开 PowerShell 命令提示符，并使用任何必需的参数运行以下 cmdlet **Set AppvClientConfiguration** 。 例如：

    `$config = Get-AppvClientConfiguration`

    `Set-AppvClientConfiguration $config`

    `Set-AppvClientConfiguration –AutoLoad 2`

    已**获得有关 app-v 的建议**？ 在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。 **遇到了 app-v 问题？** 使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相关主题


[App-V 5.0 的操作](operations-for-app-v-50.md)

 

 





