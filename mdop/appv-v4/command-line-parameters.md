---
title: 命令行参数
description: 命令行参数
author: dansimp
ms.assetid: d90a0591-f1ce-4cb8-b244-85cc70461922
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 31d6ca1215648e2519e9818817ab5cc779a746d0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802203"
---
# 命令行参数


使用以下应用程序虚拟化 Sequencer 参数对应用程序进行排序，并在命令提示符处升级顺序应用程序包。 在 Microsoft Application Virtualization Sequencer 目录中，输入**SFTSequencer**，然后输入相应的参数。

<a href="" id="-help-or---"></a>*/Help*还是 */？*  
用于显示可用于命令行序列化的参数列表。

<a href="" id="-installpackage-or--i"></a>*/INSTALLPACKAGE*或 */i*  
用于指定要对其进行排序的应用程序或批处理文件。

<a href="" id="-installpath-or--p"></a>*/INSTALLPATH*或 */p*  
用于指定程序包根目录。

<a href="" id="-outputfile-or--o"></a>*/Outputfile*或 */o*  
用于指定将生成的 SPRJ 文件的路径和文件名。

**重要提示** 当打开不打算升级的程序包时， */outputfile*参数不可用。

 

<a href="" id="-fullload-or--f"></a>*/FULLLOAD*或 */f*  
用于指定是否将所有内容放在主功能块中。

<a href="" id="-packagename-or--k"></a>*/Packagename*或 */k*  
用于指定序列化的应用程序的程序包名称。

<a href="" id="-blocksize"></a>*/BLOCKSIZE*  
指定将用于将程序包流式传输到客户端计算机的 SFT 文件块大小。 你可以选择以下值之一：

-   4 KB

-   16 KB

-   32 KB

-   64 KB

指定块大小时，应考虑 SFT 文件的大小。 块大小较小的文件需要花费较长时间才能通过网络传输，但占用带宽较少。 块大小较大的文件使用更多网络带宽。

<a href="" id="-compression"></a>*/COMPRESSION*  
用于指定在将 SFT 文件传输到客户端时对该文件进行压缩的方法。

<a href="" id="-msi-or--m"></a>*/MSI*或 */m*  
用于为序列化的应用程序指定生成 Microsoft Windows Installer 程序包。

<a href="" id="-default"></a>*/DEFAULT*  
指定创建虚拟应用程序包时将使用的默认 SPRJ 文件。 当第一次对应用程序进行排序时，此文件用作 sprj 模板。

<a href="" id="-upgrade"></a>*/UPGRADE*  
指定将升级的 SPRJ 文件的路径和文件名。

<a href="" id="-decodepath"></a>*/DECODEPATH*  
指定排序计算机上安装了与序列化应用程序包相关联的文件的目录。 指定目录时，请使用以下格式之一：

-   /decodepath：问：

-   /decodepath:Q:.

-   /decodepath:"Q:."

-   /decodepath： "Q："

## 相关主题


[关于使用 Sequencer 命令行](about-using-the-sequencer-command-line.md)

[如何使用命令行打开已排序的应用程序](how-to-open-a-sequenced-application-using-the-command-line.md)

[如何使用“打开程序包”命令升级程序包](how-to-upgrade-a-package-using-the-open-package-command.md)

 

 





