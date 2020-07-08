---
title: 命令行错误
description: 命令行错误
author: dansimp
ms.assetid: eea62568-4e90-4877-9cc7-e27ef5c05068
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ab29a77dc15a8c7bd3590b918a7ca8c1ca6e8c0d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802204"
---
# 命令行错误


使用以下错误列表来确定命令行顺序不正常工作的原因。 您也可以通过查看 sequencer 日志文件来查看这些错误。

**注意** 排序时可能会显示多个错误。 此外，显示的错误代码可能是两个错误代码的和。 例如，如果缺少 */InstallPath*和 */Outputfile*参数，Microsoft System Center Application virtualization Sequencer 将返回96（这两个错误代码的和）。

 

<a href="" id="01"></a>01  
存在未指定的错误。

<a href="" id="02"></a>02  
指定的指定安装目录（/INSTALLPACKAGE）无效。

<a href="" id="04"></a>5  
指定的程序包根目录（/INSTALLPATH）无效。

<a href="" id="08"></a>下半年  
指定的 */outputfile*参数无效。

<a href="" id="16"></a>utf-16  
未指定安装目录（/INSTALLPACKAGE）。

<a href="" id="32"></a>32  
未指定程序包 root 目录（/INSTALLPATH）。

<a href="" id="64"></a>64  
未指定 */outputfile*参数。

<a href="" id="128"></a>128  
指定的应用程序虚拟化驱动器无效。

<a href="" id="256"></a>256  
安装程序失败。

<a href="" id="512"></a>512  
对应用程序进行排序失败。

<a href="" id="1024"></a>1024  
评估安装的快捷方式失败。

<a href="" id="2048"></a>2048  
排序后的应用程序包无法保存。

<a href="" id="4096"></a>4096  
指定的程序包名称（/PACKAGENAME）无效。

<a href="" id="8192"></a>8192  
指定的块大小（/BLOCKSIZE <em> ） </em> 无效。

<a href="" id="16384"></a>16384  
指定的压缩类型（/COMPRESSION）无效。

<a href="" id="32768"></a>32768  
指定的项目路径无效。

<a href="" id="65536"></a>65536  
指定的升级参数无效。

<a href="" id="131072"></a>131072  
指定的升级项目参数无效。

<a href="" id="262144"></a>262144  
指定的解码路径参数无效。

<a href="" id="525288"></a>525288  
未指定程序包名称。

## 相关主题


[关于使用 Sequencer 命令行](about-using-the-sequencer-command-line.md)

[命令行参数](command-line-parameters.md)

 

 





