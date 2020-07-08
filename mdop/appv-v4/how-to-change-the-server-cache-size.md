---
title: 如何更改服务器缓存大小
description: 如何更改服务器缓存大小
author: dansimp
ms.assetid: 24e63744-21c3-458e-b137-9592f4fe785c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 92e56a8a28f7a00d71805b497f9e404cca65919d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801652"
---
# 如何更改服务器缓存大小


你可以使用以下过程直接从应用程序虚拟化服务器管理控制台更改任何服务器的缓存大小。

**注意** 虽然你可以更改缓存大小，除非你的配置明确要求你更改大小，否则建议将缓存大小保留设置为默认值。

 

**更改服务器缓存大小**

1.  单击左窗格中的 "**服务器组**" 节点以展开服务器组列表。

2.  在 "**结果**" 窗格中，双击所需的服务器组以显示组中的服务器列表。

3.  在 "**结果**" 窗格中，右键单击所需服务器，然后选择 "**属性**"。

4.  选择 "**高级**" 选项卡。

5.  在服务器缓存的 "**最大内存分配**" 字段中输入一个值，然后在 "**警告内存分配**" 字段中输入阈值警告级别的值。

6.  在 "**最大块大小**" 字段中输入值。 此数字必须大于或等于将从服务器流出的最大程序包的最大块大小。

7.  单击**确定**。

## 相关主题


[如何更改服务器端口](how-to-change-the-server-port.md)

[如何在 Server Management Console 中管理服务器](how-to-manage-servers-in-the-server-management-console.md)

 

 





