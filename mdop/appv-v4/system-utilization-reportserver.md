---
title: 系统使用率报告
description: 系统使用率报告
author: dansimp
ms.assetid: 4d490d15-2d1f-4f2c-99bb-0685447c0672
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fe7ff547d969c63ace234104c3e6b7146da2c113
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798734"
---
# 系统使用率报告


使用 "系统使用率" 报表来绘制每日总系统使用率。 你可以使用此报表确定你的应用程序虚拟化系统上的负载。

此报告跟踪在指定服务器或服务器组的报告期间的时间段内的使用情况。

"系统使用率" 报表还将图形为以下系统用法：

-   按周的某一天的使用情况

-   按天的小时使用

"系统使用率" 报表还包括特定用户的总系统使用率和总会话计数的摘要。

创建报表时，指定报表运行时用于收集数据的参数。

报表不会自动运行;必须显式运行它们才能生成输出数据。 运行此报告所需的时间长度由数据存储中收集的数据量决定。

运行报表并在应用程序虚拟化服务器管理控制台中显示输出后，您可以将报表导出为以下格式：

-   Adobe Acrobat （PDF）

-   Microsoft Office Excel

**注意** 从客户端报告的 app-v 服务器名称必须是默认服务器组的一部分，才能使 "系统使用率" 报表显示数据。 例如，如果你将多台服务器与网络负载平衡器（NLB）配合使用，则必须将 NLB 群集名称添加到默认服务器组。

 

## 相关主题


[如何创建报告](how-to-create-a-reportserver.md)

[如何删除报告](how-to-delete-a-reportserver.md)

[如何导出报告](how-to-export-a-reportserver.md)

[如何打印报告](how-to-print-a-reportserver.md)

[如何运行报告](how-to-run-a-reportserver.md)

 

 





