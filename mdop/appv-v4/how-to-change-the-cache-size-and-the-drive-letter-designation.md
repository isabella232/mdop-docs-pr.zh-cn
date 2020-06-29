---
title: 如何更改缓存大小和驱动器号指定
description: 如何更改缓存大小和驱动器号指定
author: dansimp
ms.assetid: e7d7b635-079e-41aa-a5e6-655f33b4e317
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: cf972f114845064ecf3027cf52d1a038dc6a5118
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801656"
---
# 如何更改缓存大小和驱动器号指定


你可以直接从应用程序虚拟化客户端管理控制台中的**应用程序虚拟化**节点更改缓存大小和驱动器号标识。

**注意**  
设置缓存大小后，它不能变得更小。



**更改缓存大小**

1.  右键单击 "**应用程序虚拟化**" 节点，然后从弹出菜单中选择 "**属性**"。

2.  选择 "**属性**" 对话框上的 "**文件系统**" 选项卡。 在 "**客户端缓存配置设置**" 部分中，单击下列单选按钮之一，选择如何管理缓存空间：

    **重要提示**  
    如果你选择 "**使用空闲磁盘空间阈值**" 设置，则你输入的值会将缓存大小设置为总磁盘大小减去你输入的可用磁盘空间阈值。 如果你随后希望使用 "**使用最大缓存大小**" 设置还原，则必须指定比现有缓存大小更大的数字。 否则，将显示 "新大小必须大于现有缓存大小" 的错误。



~~~
-   **Use maximum cache size**

    Enter a numeric value from 100 to 1,048,576 (1 TB) in the **Maximum size (MB)** field to specify the maximum size of the cache. The value shown in **Reserved Cache Size** indicates the amount of cache in use.

-   **Use free disk space threshold**

    Enter a numeric value to specify the amount of free disk space, in MB, that the cache must leave available on the disk. This allows the cache to grow until the amount of free disk space reaches this limit. The value shown in **Free disk space remaining** indicates how much disk space is unused.
~~~

3. 单击 **"确定" 或 "** **应用**" 更改设置。

**更改驱动器号指定**

1.  右键单击 "**应用程序虚拟化**" 节点，然后从弹出菜单中选择 "**属性**"。

2.  在 "**属性**" 对话框中的 "**文件系统**" 选项卡上的 "**要使用的驱动器**" 字段中，从可用的驱动器号下拉列表中选择所需的驱动器号。 重新启动计算机后，此设置才有效。

3.  单击 **"确定" 或 "** **应用**" 更改设置。

## 相关主题


[如何在 Application Virtualization Client Management Console 中配置客户端](how-to-configure-the-client-in-the-application-virtualization-client-management-console.md)









