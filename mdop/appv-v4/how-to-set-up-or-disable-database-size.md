---
title: 如何设置或禁用数据库大小
description: 如何设置或禁用数据库大小
author: dansimp
ms.assetid: 4abaf349-132d-4186-8873-a0e515593b93
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: cbb041920e2680d51b01926f144eba595fe28d05
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801067"
---
# 如何设置或禁用数据库大小


你可以使用应用程序虚拟化服务器管理控制台中的以下过程来指定要存储在数据库中的应用程序虚拟化系统使用的大小（以 MB 为单位）。

当所存储数据的大小达到指定限制的95% （高水位线）时，系统将删除10% 的使用率数据，从而导致85% 的数据。 将删除程序包和应用程序使用情况数据。 当数据库变得足够大并接近高水位线时，将向 SQL Server 日志发送一条警告消息，告知您已达到此限制。 此警告是必需的，因为清理操作可能会影响报表的输出。 它还将帮助你确定是否需要增加最大数据库大小、减少要保留的使用数据的月份数，或关闭日志记录级别。

**注意** 将提供 "**无大小限制**" 和 "**保留所有使用情况**" 选项，以便您可以禁用使用情况报告和数据库清理。 选择这些项目也将清理数据库事务日志。 （所有提交的 Microsoft SQL Server 事务都将从数据库日志中删除。）

 

**设置数据库大小**

1.  右键单击左窗格中的 "应用程序虚拟化系统" 节点，然后选择 "**系统选项**"。

2.  选择 "**数据库**" 选项卡。

3.  选择 "**最大数据库大小（MB）** " 或 "**无大小限制**" 单选按钮。

4.  如果你选择指定数据库大小，最佳做法建议你输入一个介于512和 4096 MB 之间的数字。 默认大小为 1024 MB，如果需要增加数据库大小，则可以输入的最大值为2147483647。 如果选择 "**无大小限制**"，数据库将增长，直到达到磁盘大小限制。

5.  单击**Apply** "应用 **" 或 "确定"**。

**禁用数据库大小限制**

1.  右键单击 "**范围**" 窗格中的 "应用程序虚拟化系统" 节点，然后选择 "**系统选项**"。

2.  选择 "**数据库**" 选项卡。

3.  选择 "**无大小限制**" 并**保留 "所有使用情况**" 单选按钮。

4.  单击**Apply** "应用 **" 或 "确定"**。

## 相关主题


[如何在 Server Management Console 中自定义 Application Virtualization System](how-to-customize-an-application-virtualization-system-in-the-server-management-console.md)

[如何设置或禁用使用情况报告](how-to-set-up-or-disable-usage-reporting.md)

 

 





