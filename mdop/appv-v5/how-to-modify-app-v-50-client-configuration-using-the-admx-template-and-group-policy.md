---
title: 如何使用 ADMX 模板和组策略修改 App-V 5.0 Client 配置
description: 如何使用 ADMX 模板和组策略修改 App-V 5.0 Client 配置
author: dansimp
ms.assetid: 79d03a2b-2586-4ca7-bbaa-bdeb0a694279
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: cd257691bf223baa5e2919d83fdbf53d34f271ac
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798396"
---
# 如何使用 ADMX 模板和组策略修改 App-V 5.0 Client 配置


使用 "app-v 5.0 ADMX" 模板，使用 ADMX 模板和组策略配置 app-v 5.0 客户端设置。

**使用组策略修改 App-v 5.0 客户端配置**

1.  若要修改 app-v 5.0 客户端配置，请找到适用于 app-v 5.0 的**ADMXTemplate**文件。

    **注意** 使用以下链接下载 app-v 5.0 **ADMX 模板**： <https://go.microsoft.com/fwlink/p/?LinkId=393941> 。

     

2.  在管理组策略的计算机（通常为域控制器）上，将模板**admx**文件复制到以下目录： ** &lt; 安装驱动器 &gt; \\ Windows \\ PolicyDefinitions**。

    接下来，在同一台计算机上，将**adml**文件复制到以下目录： ** &lt; InstallationDrive &gt; \\ Windows \\ PolicyDefinitions \ en-us**。

3.  将文件复制到 "组策略管理控制台" 之后，若要修改与应用-v 5.0 客户端关联的策略，请浏览到 "**计算机配置**  /  **策略**"  /  **管理模板**  /  **系统**  /  **app-v**。

    已**获得有关 app-v 的建议**？ 在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。 **遇到了 app-v 问题？** 使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相关主题


[部署 App-V 5.0](deploying-app-v-50.md)

[关于 Client 配置设置](about-client-configuration-settings.md)

 

 





