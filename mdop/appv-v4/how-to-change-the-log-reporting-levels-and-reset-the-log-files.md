---
title: 如何更改日志报告级别和重置日志文件
description: 如何更改日志报告级别和重置日志文件
author: dansimp
ms.assetid: 9561d6fb-b35c-491b-a355-000064583194
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7307dee0030d9c03a8107d9d0ceef2086a94df07
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801660"
---
# 如何更改日志报告级别和重置日志文件


你可以使用以下过程在应用程序虚拟化管理控制台中更改**应用程序虚拟化**节点中的日志报告级别。 当日志文件达到最大大小（默认值为 256 MB）时，将在下次写入日志时会强制重置。 重置导致创建新的日志文件，并且旧文件被重命名为备份。

**更改日志报告级别**

1.  右键单击 "**应用程序虚拟化**" 节点，然后从弹出菜单中选择 "**属性**"。

2.  在 "**属性**" 对话框中的 "**常规**" 选项卡上，从 "**日志级别**" 下拉列表中选择所需的日志级别。

    **注意** 如果选择 "**详细**" 作为日志记录级别，日志文件将很快变得很快。 这可能会阻止客户端性能，因此最佳做法是仅使用此日志级别来诊断特定问题。

     

3.  在 "**属性**" 对话框中的 "**常规**" 选项卡上，从 "**系统日志级别**" 下拉列表中选择所需的日志级别。

    **注意** "**系统日志级别**" 设置控制发送到系统事件日志的消息级别。 记录的消息与记录到客户端事件日志的消息相同，但它们存储在其他位置。

     

4.  单击 **"确定" 或 "** **应用**" 更改设置。

**重置日志文件**

1.  右键单击 "**应用程序虚拟化**" 节点，然后从弹出菜单中选择 "**属性**"。

2.  在 "**属性**" 对话框中的 "**常规**" 选项卡上，单击 "**重置日志**" 以备份当前日志文件，并立即启动新的日志文件。 备份日志文件存储在同一文件夹中。

3.  单击 **"确定" 或 "** **应用**" 更改设置。

## 相关主题


[如何在 Application Virtualization Client Management Console 中配置客户端](how-to-configure-the-client-in-the-application-virtualization-client-management-console.md)

[Application Virtualization Client 中的用户访问权限](user-access-permissions-in-application-virtualization-client.md)

 

 





