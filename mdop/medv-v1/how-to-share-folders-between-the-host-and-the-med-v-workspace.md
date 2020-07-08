---
title: 如何在主机和 MED-V 工作区之间共享文件夹
description: 如何在主机和 MED-V 工作区之间共享文件夹
author: dansimp
ms.assetid: 3cb295f2-c07e-4ee6-aa3c-ce4c8c45c191
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 87f315c9894cd38834413d2549e652a36c5cc16d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803831"
---
# 如何在主机和 MED-V 工作区之间共享文件夹


你可以在主机和 MED-V 工作区之间共享文件夹。 共享文件夹可以存储在以下文件夹中：

-   网络上的外部计算机

-   主计算机

以下过程演示了如何在主机和 MED-V 工作区之间共享文件夹。

**共享位于网络上的文件夹**

1.  在完整桌面模式下配置 MED-V。

2.  在 MED-V 管理的 "网络" 选项卡上，单击 "**使用不同于主机的 IP 地址（桥）**"。

3.  在主机计算机上执行以下操作：

    1.  在 "控制面板" 中，单击 "**查看网络状态和任务**"，然后将 "**网络发现**" 设置为 **"打开"**。

    2.  在 "开始" 菜单上，右键单击 "**计算机**"，然后单击 "**映射网络驱动器**"。

    3.  在 "**映射网络驱动器**" 对话框的 "**驱动器**" 字段中，选择一个驱动器。

        **注意** 确保两台计算机上未使用相同的驱动器号。

         

    4.  单击**浏览**。

    5.  在 "**浏览文件夹**" 对话框中，通过浏览找到共享驱动器，然后单击 **"确定"**。

    6.  单击**完成**。

4.  在 MED-V 工作区中重复步骤3。 指向与主机上相同的驱动器。

**共享位于主机上的文件夹**

1.  将文件夹配置为具有相应权限的共享文件夹。

2.  从 MED-V 工作区，转到 **"网上邻居**" 并找到共享文件夹。

3.  在 MED-V 工作区中，找到共享文件夹。

**注意** 确保主机和 MED-V 工作区计算机位于同一个域或工作组中。

 

 

 





