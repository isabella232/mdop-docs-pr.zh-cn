---
title: 查看和配置 MED-V 日志
description: 查看和配置 MED-V 日志
author: dansimp
ms.assetid: a15537ce-981d-4f55-9c3c-e7fbf94b8fe5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7984cec072827136db9ea52a535c0ea44c6bc2c3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803426"
---
# 查看和配置 MED-V 日志


当您解决 MED-V 问题和问题时，您可能会发现访问 MED-V 事件日志有帮助或有必要。 你可以使用 MED-V 管理工具包打开主计算机和来宾虚拟机的事件查看器。 你还可以使用 MED-V 管理工具包设置 MED-V 事件日志报告 MED-V 事件的日志记录级别。

有关如何打开 MED-V 管理工具包的信息，请参阅[使用管理工具包对 Med-v 进行故障排除](troubleshooting-med-v-by-using-the-administration-toolkit.md)。

## 查看 MED-V 事件日志


在 " **Med-v 管理工具包**" 窗口中，单击 "**主机事件**" 以打开主机的事件查看器。 或者，单击 "**来宾事件**" 以打开来宾虚拟机的事件查看器。

"事件查看器" 打开并显示相应的事件日志，可用于对部署或管理 MED-V 时可能遇到的问题进行故障排除。 默认情况下，仅显示错误和警告。 有关特定事件 Id 和消息的详细信息，请参阅[Med-v 事件日志消息](med-v-event-log-messages.md)。

**注意** 最终用户在具有管理权限的情况中，只能将事件日志文件保存在来宾中。

 

### 在主计算机中手动打开事件查看器

1.  单击 "**开始**"，单击 "**控制面板**"，然后单击 "**管理工具**"。

2.  双击 "**事件查看器**"，然后单击 "**应用程序和服务日志**"。

3.  双击 " **MEDV**"。

## 配置 MED-V 事件日志


你可以通过选择 MED-V 管理工具包上的相应选项按钮来指定 MED-V 事件日志记录级别。 你可以决定事件日志是否仅包括错误、错误和警告，或者错误、警告和提示消息。 为主计算机和来宾虚拟机设置指定的事件日志记录级别。

你还可以通过编辑 EventLogLevel 注册表值来指定事件日志记录级别。 有关详细信息，请参阅[管理 Med-v 工作区配置设置](managing-med-v-workspace-configuration-settings.md)。

**注意** 在 " **Med-v 管理工具包**" 窗口中指定的级别适用于未来的 med-v 事件日志记录。 如果将级别设置为捕获所有错误、警告和信息性消息，则会删除事件日志更快地填充和较旧的事件。

 

## 相关主题


[重启和重置 MED-V 工作区](restarting-and-resetting-a-med-v-workspace.md)

[查看 MED-V 工作区配置](viewing-med-v-workspace-configurations.md)

 

 





