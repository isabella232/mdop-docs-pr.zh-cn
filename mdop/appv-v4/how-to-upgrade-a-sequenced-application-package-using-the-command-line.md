---
title: 如何使用命令行升级已排序的应用程序包
description: 如何使用命令行升级已排序的应用程序包
author: dansimp
ms.assetid: 682fac46-c71d-4731-831b-81bfd5032764
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: eade2ced43852419176f635918f0a6b7c3444aee
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801036"
---
# 如何使用命令行升级已排序的应用程序包


使用以下过程通过命令行升级虚拟应用程序。 使用命令行升级现有虚拟应用程序包时，将删除该 sft 文件的原始版本。 你应该先备份关联的 sft 文件，然后再使用命令行升级程序包。

**升级虚拟应用程序**

1.  在运行应用程序虚拟化（app-v）排序器的计算机上，若要打开命令提示符，请选择 "**开始**"、"**运行**"，然后键入**cmd**。 单击“确定”****。

2.  在命令提示符处，指定安装 app-v Sequencer 的位置。 例如，在命令提示符处，可以键入以下内容： **cd C:\\program files Files\\Microsoft Application Virtualization Sequencer**。

3.  在命令提示符处，键入以下命令，将引号中的文本替换为值：

    `SFTSequencer /UPGRADE:"pathtosourceSPRJ" /INSTALLPACKAGE:"pathtoUpgradeInstaller" /DECODEPATH:"pathtodecodefolder" /OUTPUTFILE:"pathtodestinationSPRJ"`

    **注意**  
    你可以使用命令行指定其他参数，具体取决于你要升级的应用程序的复杂程度。 有关可用于 App-v Sequencer 的参数的完整列表，请参阅[命令行参数](command-line-parameters.md)。



~~~
Use the value descriptions in the following table to help you determine the actual text you will use in the preceding command.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Value</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><em>pathtosourceSPRJ</em></p></td>
<td align="left"><p>Specifies the directory location of the virtual application to be upgraded.</p></td>
</tr>
<tr class="even">
<td align="left"><p><em>pathtoUpgradeInstaller</em></p></td>
<td align="left"><p>Specifies the Windows Installer or a batch file that will be used to install an upgrade to the application.</p></td>
</tr>
<tr class="odd">
<td align="left"><p><em>pathtodecodefolder</em></p></td>
<td align="left"><p>Specify the directory in which to unpack the SFT file.</p></td>
</tr>
<tr class="even">
<td align="left"><p><em>pathtodestinationSPRJ</em></p></td>
<td align="left"><p>Specifies the path and file name of the SPRJ file that will be created.</p></td>
</tr>
</tbody>
</table>
~~~



4. 按**enter**。

## 相关主题


[如何使用命令行管理虚拟应用程序](how-to-manage-virtual-applications-using-the-command-line.md)









