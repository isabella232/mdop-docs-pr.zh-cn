---
title: 解决 Application Virtualization Sequencer 问题
description: 解决 Application Virtualization Sequencer 问题
author: dansimp
ms.assetid: 2712094b-a0bc-4643-aced-5415535f3fec
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fa8b84f37217f29ff2c08a2254d7f54ce74348d2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798732"
---
# 解决 Application Virtualization Sequencer 问题


本主题包含可用于帮助解决应用程序虚拟化（app-v） Sequencer 上的一般问题的信息。

## 使用 App-v Sequencer 创建 SFTD 文件会意外地增加版本号


使用命令行生成新的 sft 文件。 若要使用命令行创建 sft 文件，请在命令提示符处输入以下命令：

**&lt;基本 sft 文件名称 &gt; &lt; 差异 mkdiffpkg.exe sft 文件名&gt;**

## <a href="" id="file-name-in-osd-file-is-not-correct-after-package-upgrade-"></a>软件包升级后，OSD 文件中的文件名不正确


打开要升级的程序包时，应将根 Q:\\ 驱动器指定为程序包的输出位置。 不要使用输出位置指定关联的文件名。

## 当向客户端流处理时，Microsoft Word2003 默认安装导致错误


将 Microsoft Word2003 流式传输到客户端时，将返回错误，但 Microsoft Word 将继续运行。

**解决方案**

Resequence 虚拟应用程序包，然后选择 "**完全安装**"。

## 创建依赖程序包时，活动升级不起作用


通过使用 "活动升级" 并添加新的注册表项创建依赖程序包时，它似乎正常运行，但更新的注册表项不可用。

**解决方案**

注册表设置始终与程序包的原始版本一起存储，因此除非修复原始程序包，否则程序包的更新将不会显示为可用。

## 通过使用 "属性" 页面不显示 Microsoft Office2007 文档的详细信息


当您尝试使用 "属性" 页面查看与 Microsoft Office2007 文档相关联的详细信息时，详细信息不可见。

**解决方案**

App-v 不支持这些属性页所需的 shell 扩展。

## 序列16位应用程序时，某些注册表项不会捕获


在 App-v 4.5 中，注册表挂钩已从内核模式移动到用户模式。 如果想要对使用16位安装程序的16位应用程序或应用程序进行排序，必须首先配置 sequencer 计算机，以便该进程在其自己的 Windows NT 虚拟 DOS 计算机（NTVDM）副本中运行。

**解决方案**

在对应用程序进行排序之前，在排序计算机上将以下全局 REGSZ 注册表项值设置为 "yes"：

HKLM\\SYSTEM\\CurrentControlSet\\Control\\WOW\\DefaultSeparateVDM

您必须重新启动计算机才能使此操作生效。

## 相关主题


[Application Virtualization Sequencer](application-virtualization-sequencer.md)

 

 





