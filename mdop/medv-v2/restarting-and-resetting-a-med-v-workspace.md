---
title: 重启和重置 MED-V 工作区
description: 重启和重置 MED-V 工作区
author: dansimp
ms.assetid: a959cdb3-a727-47c7-967e-e58f224e74de
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 48a644c2ed1668f87eb6e1a78521e780e8b783dd
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803765"
---
# 重启和重置 MED-V 工作区


在故障排除期间，有时您可能会发现需要重新启动或重置 MED-V 工作区。 重启 MED-V 工作区与重启物理计算机基本相同。 重置 MED-V 工作区首次重新运行设置并删除虚拟机中存储的所有数据。 由于删除了所有存储的数据，因此通常应仅重置 MED-V 工作区以解决最严重的疑难解答问题，或者将以前工作的 MED-V 工作区还原为工作状态。

有关如何打开 MED-V 管理工具包的信息，请参阅[使用管理工具包对 Med-v 进行故障排除](troubleshooting-med-v-by-using-the-administration-toolkit.md)。

**重新启动 MED-V 工作区**

1.  在 " **Med-v 管理工具包**" 窗口中，单击 "**重启 med-v 工作区**"。 将打开一个对话框窗口，您必须确认是否要重新启动 MED-V 工作区。

2.  单击 "**重新启动**"。

    当 MED-V 工作区重新启动时，任何运行的或重定向的网站已打开的应用程序都将关闭。

**重置 MED-V 工作区**

1.  在 " **Med-v 管理工具包**" 窗口中，单击 "**重置 med-v 工作区**"。 将打开一个对话框窗口，您必须确认是否要重置 MED-V 工作区。

    **警告** 重置 MED-V 工作区会导致首次设置再次运行，从而重新加载原始虚拟硬盘。 自首次运行设置后的 MED-V 工作区中存储的所有数据将被删除。

     

2.  单击**重置**。

    当 MED-V 工作区重置时，任何运行的或重定向的网站都将关闭的已发布应用程序。

## 相关主题


[查看和配置 MED-V 日志](viewing-and-configuring-med-v-logs.md)

[查看 MED-V 工作区配置](viewing-med-v-workspace-configurations.md)

 

 





