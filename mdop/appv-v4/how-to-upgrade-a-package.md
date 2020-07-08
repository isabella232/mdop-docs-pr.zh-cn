---
title: 如何升级程序包
description: 如何升级程序包
author: dansimp
ms.assetid: 831c7556-6f6c-4b3a-aefb-26889094dc1a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0a9b3eca2c996337d79e551784818a421f495316
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801043"
---
# 如何升级程序包


自动升级的过程与在应用程序虚拟化服务器管理控制台中添加程序包版本的过程相同。 当你在现有程序包中 resequence 应用程序时，将执行自动升级。 然后，你可以将此新版本添加到你的服务器以进行流式处理。

使用新版本升级程序包时，可以保留现有版本或将其删除，仅保留最新版本。 你可能希望保留旧版本以实现与旧版文档的兼容性，以便你可以在将新版本提供给所有用户之前对其进行测试。

**自动升级程序包**

1.  将新的 SFT 文件复制到 Application Virtualization 服务器的内容文件夹。

    **注意** 如果 resequencing 未添加已更改开放软件描述符（OSD）、图标（.ICO）或 Sequencer 项目（SPRJ）文件的功能，则无需复制这些功能。 如果您希望所有这些文件都显示相同的日期，则可以包含这些文件。

     

2.  在应用程序虚拟化服务器管理控制台的左窗格中，展开 "**程序包**"。

3.  右键单击要升级的程序包，然后选择 "**添加版本**"。

4.  在 "**添加包版本**" 对话框中，在 "文件" 字段的 "**完整路径**" 中，浏览或键入新应用程序版本的完整路径名称。 这必须是一个 SFT 文件。

5.  单击“下一步”****。

6.  "**摘要**" 对话框显示文件位置，并提示您将文件复制到该位置（如果尚未执行此操作）。 验证信息后，单击 "**完成**"。

    新版本现已完成，准备好流。

## 相关主题


[如何在 Server Management Console 中管理程序包](how-to-manage-packages-in-the-server-management-console.md)

 

 





