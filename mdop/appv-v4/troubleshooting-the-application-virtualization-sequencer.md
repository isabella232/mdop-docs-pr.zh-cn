---
title: Application Virtualization Sequencer 故障排除
description: Application Virtualization Sequencer 故障排除
author: dansimp
ms.assetid: 12ea8367-0b84-44e1-a885-e0539486556b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 60c47b853c74d90afc21e9ca172c0eec2a2c7a0d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798720"
---
# Application Virtualization Sequencer 故障排除


本主题包含可用于帮助解决应用程序虚拟化（app-v） Sequencer 上的一般问题的信息。

## 使用 App-v Sequencer 创建 SFTD 文件会意外地增加版本号


与 SFTD 文件关联的版本号会意外增加。

**解决方案**

使用命令行生成新的 sft 文件。 若要使用命令行创建 sft 文件，请在命令提示符处输入以下命令：

**&lt;基本 sft 文件名称 &gt; &lt; 差异 mkdiffpkg.exe sft 文件名&gt;**

## <a href="" id="file-name-in-osd-file-is-not-correct-after-package-upgrade-"></a>软件包升级后，OSD 文件中的文件名不正确


升级现有程序包后，文件名不正确。

**解决方案**

打开要升级的程序包时，应将根 Q:\\ 驱动器指定为程序包的输出位置。 不要使用输出位置指定关联的文件名。

## 当向客户端流处理时，Microsoft Word2003 默认安装导致错误


将 Microsoft Word2003 流式传输到客户端时，将返回错误，但 Microsoft Word 将继续运行。

**解决方案**

Resequence 虚拟应用程序包，然后选择 "**完全安装**"。

## 创建依赖程序包时程序包升级不起作用


使用程序包升级创建依赖程序包并添加新的注册表项时，它似乎正常运行，但更新的注册表项不可用。

**解决方案**

注册表设置始终与程序包的原始版本一起存储，因此除非修复原始程序包，否则程序包的更新将不会显示为可用。

## 尝试序列时出错。NET 2。0


对需要的程序包进行排序时。NET 2.0 后，您会收到一条错误消息。

**解决方案**

需要的排序包。不支持 NET 2.0。

## 相关主题


[Application Virtualization Sequencer](application-virtualization-sequencer.md)

 

 





