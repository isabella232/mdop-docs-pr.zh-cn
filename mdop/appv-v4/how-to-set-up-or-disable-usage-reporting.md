---
title: 如何设置或禁用使用情况报告
description: 如何设置或禁用使用情况报告
author: dansimp
ms.assetid: 8587003a-128d-4b5d-ac70-5b9eddddd3dc
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3f8f6c44d4060581f1ebe435875bc2f105cb93d6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801060"
---
# 如何设置或禁用使用情况报告


你可以使用应用程序虚拟化服务器管理控制台中的以下过程来指定要存储在数据库中的应用程序虚拟化系统使用信息的持续时间（以月为单位）。

**注意** 若要存储使用信息，必须选中 "**提供程序管道**" 选项卡上的 "**日志使用信息**" 复选框。若要显示此选项卡，请右键单击 "**提供程序策略结果**" 窗格中的提供程序策略，然后选择 "**属性**"。

 

**设置使用率报告**

1.  右键单击左窗格中的 "应用程序虚拟化系统" 节点，然后选择 "**系统选项**"。

2.  选择 "**数据库**" 选项卡。

3.  选择 "**保留使用情况（月）** " 或 "**保留所有使用情况**" 单选按钮。

4.  如果您选择以月为单位指定使用持续时间，请输入从1到120的数字（默认值为6个月）。 如果选择 "**保留所有用法**"，数据库将增长，直至达到指定的大小限制。

5.  单击**Apply** "应用 **" 或 "确定"**。

**禁用使用率报告**

1.  单击 "**提供商策略**" 节点。

2.  右键单击 "**提供程序策略**"，然后选择 "**属性**"。

3.  选择 "**提供商管道**" 选项卡。

4.  清除 "**日志使用情况信息**" 复选框。

5.  单击**Apply** "应用 **" 或 "确定"**。

## 相关主题


[如何在 Server Management Console 中自定义 Application Virtualization System](how-to-customize-an-application-virtualization-system-in-the-server-management-console.md)

[如何设置或禁用数据库大小](how-to-set-up-or-disable-database-size.md)

 

 





