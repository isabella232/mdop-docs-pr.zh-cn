---
title: 如何使用“打开程序包”命令升级程序包
description: 如何使用“打开程序包”命令升级程序包
author: dansimp
ms.assetid: 67c10440-de8a-4547-a34b-f83206d0cc3b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: cca438fe90373e8f934d1d790246544cdf46fa18
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801048"
---
# 如何使用“打开程序包”命令升级程序包


使用 "打开程序包" 命令将更新升级或应用到顺序应用程序包。 使用命令行升级现有虚拟应用程序包时，将删除该 sft 文件的原始版本。 你应该先备份关联的 sft 文件，然后再使用命令行升级程序包。

**使用 "打开包" 命令升级程序包**

1.  若要打开要升级的程序包，请在 "应用程序虚拟化（App-v）" 控制台中选择 "**文件**"，**打开 "升级程序包**"。 在 "**打开**" 对话框中，选择将升级的程序包。

2.  若要启动**顺序**向导，请选择 "**工具**"、"**序列化向导**"。 完成向导应用配置更改，以保存新的顺序应用程序，请选择 "**文件**"，"**保存**"。

3.  若要将版本号追加到程序包名称，请在 Sequencer 控制台中选择 "**工具**"、"**选项**"。 选择 "**将包版本附加到文件名**"。 单击“确定”****。

    **重要提示** 若要成功完成升级，更新程序包版本的文件名是必需的。

     

## 相关主题


[如何使用命令行管理虚拟应用程序](how-to-manage-virtual-applications-using-the-command-line.md)

 

 





