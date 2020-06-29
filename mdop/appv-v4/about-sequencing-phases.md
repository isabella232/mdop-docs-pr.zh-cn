---
title: 关于排序阶段
description: 关于排序阶段
author: dansimp
ms.assetid: c1cb7b6c-204c-48f2-848c-4bd5a3d5ecb6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4e3d1504f0af82f3d21806b38bb4640b6f7ebc45
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802443"
---
# 关于排序阶段


排序是通过使用 Microsoft Application Virtualization （App-v） Sequencer 创建序列化应用程序包的过程。 在排序期间，Sequencer 将监视和记录应用程序的所有安装和设置进程，并创建以下文件： .ICO、OSD、SFT 和 SPRJ。 这些文件包含有关应用程序的所有必要信息，并允许该应用程序在虚拟环境中运行。

序列化应用程序和创建虚拟应用程序包的四个阶段是安装、启动、自定义和保存。 下面的列表提供了每个阶段的相关信息：

1.  **安装阶段**-在安装阶段，指定程序包名称和将与程序包关联的可选关联注释。 您也可以在此阶段配置高级监视选项。 高级监视选项包括指定块大小以及在监视期间是否将安装自动更新。 Sequencer 记录创建虚拟应用程序包以及关联的文件和注册表设置所需的所有必要信息和配置。

    **重要提示** 若要查看高级选项，请选择 "**程序包信息**" 页面上的 "**显示高级监视选项**"。

     

2.  **启动阶段**-在启动阶段，你可以指定应配置程序包的任何必需的文件关联和安全描述符。 你应根据需要多次打开应用程序，以确保应用程序功能和稳定性。

3.  **自定义阶段**——在自定义阶段，您可以使用关联的 .osd 文件配置程序包。 你可以指定是否应在虚拟环境内部或外部运行任何关联的脚本、指定应执行的其他操作、指定关联脚本的运行方式（同步或异步），以及指定应在用户上下文下运行的任何其他脚本。

4.  **保存阶段**-在保存阶段，创建虚拟应用程序包所需的所有文件。 创建的文件为 sprj、sft、.osd、.ico、.xml 清单和 Windows installer （.msi）文件。

## 相关主题


[Application Virtualization Sequencer](application-virtualization-sequencer.md)

 

 





