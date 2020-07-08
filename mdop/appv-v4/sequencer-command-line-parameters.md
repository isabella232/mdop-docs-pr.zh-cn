---
title: Sequencer 命令行参数
description: Sequencer 命令行参数
author: dansimp
ms.assetid: 28fb875a-c302-4d95-b2e0-8dc0c5dbb0f8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ecfa269de04cf3dcba30cbb4a40f9176f03f6571
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798794"
---
# Sequencer 命令行参数


你可以使用以下应用程序虚拟化（App-v） Sequencer 参数对应用程序进行排序，并使用命令行升级现有虚拟应用程序。 有关使用命令行对应用程序进行排序的详细信息，请参阅[如何使用命令行对新应用程序](how-to-sequence-a-new-application-by-using-the-command-line.md)进行排序。

## Sequencer 命令行参数


<a href="" id="-help-or---"></a>**/HELP 还是/？**  
显示有关可使用命令行序列化应用程序的参数的信息。

<a href="" id="-installpackage-or--i"></a>**/INSTALLPACKAGE 或/I**  
指定将用于安装应用程序的 Windows 安装程序或批处理文件，以便可以对其进行排序。

<a href="" id="-installpath-or--p"></a>**/INSTALLPATH 或/P**  
指定应用程序的程序包根目录。

<a href="" id="-outputfile-or--o"></a>**/OUTPUTFILE 或/O**  
指定将生成的 SPRJ 文件的路径和文件名。

<a href="" id="-fullload-or--f"></a>**/FULLLOAD 或/F**  
指定是否将所有文件包含在主要功能块中。 如果在命令行上指定了 **/FULLLOAD**参数，则所有关联的应用程序数据都将添加到主功能块。 如果未在命令行上指定 **/FULLLOAD**参数，则不会将任何关联的应用程序数据添加到主功能块。

<a href="" id="-packagename-or--k"></a>**/PACKAGENAME 或/K**  
指定将分配给序列化应用程序的程序包名称。

<a href="" id="-blocksize"></a>**/BLOCKSIZE**  
指定将用于将程序包流式传输到客户端计算机的 SFT 文件块大小。 你可以选择以下值之一：

-   4 KB

-   16 KB

-   32 KB

-   64 KB

指定块大小时，应考虑 SFT 文件的大小。 块大小较小的文件需要花费较长时间才能通过网络传输，但占用带宽较少。 块大小较大的文件使用更多网络带宽。

<a href="" id="-compression"></a>**/COMPRESSION**  
指定用于压缩将流入到客户端的 SFT 文件的方法。

<a href="" id="-msi-or--m"></a>**/MSI 或/M**  
指定是否应创建序列化应用程序的 Windows Installer。

<a href="" id="-default"></a>**/DEFAULT**  
指定创建虚拟应用程序包时将使用的默认 SPRJ 文件。 当第一次对应用程序进行排序时，此文件用作 sprj 模板。

<a href="" id="-upgrade"></a>**/UPGRADE**  
指定将升级的 SPRJ 文件的路径和文件名。

<a href="" id="-decodepath"></a>**/DECODEPATH**  
指定排序计算机上安装了与序列化应用程序包相关联的文件的目录。 指定目录时，请使用以下格式之一：

-   /decodepath：问：

-   /decodepath:Q:.

-   /decodepath:"Q:."

-   /decodepath： "Q："

## 相关主题


[Application Virtualization Sequencer](application-virtualization-sequencer.md)

[Sequencer 命令行错误代码](sequencer-command-line-error-codes.md)

 

 





