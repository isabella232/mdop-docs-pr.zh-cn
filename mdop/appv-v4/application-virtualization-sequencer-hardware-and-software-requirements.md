---
title: Application Virtualization Sequencer 硬件和软件要求
description: Application Virtualization Sequencer 硬件和软件要求
author: dansimp
ms.assetid: c88a1b5b-23e1-4460-afa9-a5f37e32eb05
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d68afe4d4a3f6f301d38f2e86139d94319583467
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802291"
---
# Application Virtualization Sequencer 硬件和软件要求


本主题介绍运行 Microsoft Application Virtualization （app-v） Sequencer 的计算机的最低建议硬件和软件要求。

**重要提示** 你必须使用具有管理员权限的帐户运行 app-v sequencer （**SFTSequencer.exe**），因为 sequencer 对本地系统所做的更改。 这些更改可以包括将文件写入**C:\\program files files**目录、进行注册表更改、启动和停止服务、更新文件的安全描述符以及更改权限。

 

在安装 Sequencer 之前以及对每个应用程序进行排序后，必须将干净的操作系统映像还原到顺序计算机。 你可以使用以下方法之一来还原运行 Sequencer 的计算机：

-   重新格式化硬盘并重新安装操作系统。

-   使用另一个磁盘映像软件还原运行 Sequencer 映像的计算机上的硬盘。

-   还原虚拟操作系统映像，例如 Microsoft 虚拟 PC 映像。 使用虚拟机可轻松地以最少的管理方式重用干净的顺序环境。

下表列出了运行 App-v 排序器的推荐硬件要求。

首先列出了 Microsoft Application Virtualization （app-v） 4.6 SP2 的要求，后跟前面的 App-v 4.6 SP2 版本的要求。

### <a href="" id="hardware-requirements-"></a>硬件要求

-   处理器-英特尔奔腾 III、1 GHz （32位或64位）。 排序过程是一个单线程进程，不会利用双处理器。

-   内存-1GB 或更高，建议使用2GB。

-   硬盘-40 千兆字节（GB）硬盘空间，至少有 15 GB 的可用硬盘空间。 我们建议您至少拥有所需的应用程序所需的磁盘空间的三倍。

    **注意** 排序需要大量的磁盘使用。 快速磁盘速度会减少排序时间。

     

### App-v 4.6 SP2 的软件要求

下表列出了运行 app-v 4.6 SP2 Sequencer 的受支持的操作系统。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">操作系统</th>
<th align="left">版本</th>
<th align="left">Service Pack</th>
<th align="left">系统体系结构</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>WindowsXP</p></td>
<td align="left"><p>专业版</p></td>
<td align="left"><p>又</p></td>
<td align="left"><p>x86</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Vista</p></td>
<td align="left"><p>企业版、企业版或旗舰版</p></td>
<td align="left"><p>SP2</p></td>
<td align="left"><p>x86</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows7</p></td>
<td align="left"><p>专业版、企业版或旗舰版</p></td>
<td align="left"><p>无服务包或 SP1</p></td>
<td align="left"><p>x86 和 x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows 8</p></td>
<td align="left"><p>专业版或企业版</p></td>
<td align="left"><p></p></td>
<td align="left"><p>x86 和 x64</p></td>
</tr>
</tbody>
</table>

 

**注意** 应用程序虚拟化（app-v） 4.6 SP2 Sequencer 支持这些操作系统的32位和64位版本。

 

你应该将运行 Sequencer 的计算机配置为在目标计算机上安装的相同应用程序。

### 在 App-v 4.6 SP2 之前的版本的软件要求

下表概述了针对应用 V 4.6 SP2 之前的版本运行 Sequencer 的受支持操作系统。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">操作系统</th>
<th align="left">版本</th>
<th align="left">Service Pack</th>
<th align="left">系统体系结构</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>WindowsXP</p></td>
<td align="left"><p>专业版</p></td>
<td align="left"><p>SP2 或 SP3</p></td>
<td align="left"><p>x86</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Vista</p></td>
<td align="left"><p>企业版、企业版或旗舰版</p></td>
<td align="left"><p>无服务包、SP1 或 SP2</p></td>
<td align="left"><p>x86</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows7 ¹</p></td>
<td align="left"><p>专业版、企业版或旗舰版</p></td>
<td align="left"><p></p></td>
<td align="left"><p>x86</p></td>
</tr>
</tbody>
</table>

 

¹支持仅限 SP1 或 SP2 的 app-v 4.5 和 app-v 4。6

**注意** 应用程序虚拟化（app-v） 4.6 Sequencer 支持这些操作系统的32位和64位版本。

 

你应该将运行 Sequencer 的计算机配置为在目标计算机上安装的相同应用程序。

### 适用于 App-v 4.6 SP2 的远程桌面服务的软件要求

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">操作系统</th>
<th align="left">版本</th>
<th align="left">Service Pack</th>
<th align="left">系统体系结构</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows Server2003 R2</p></td>
<td align="left"><p>标准版、企业版或数据中心版</p></td>
<td align="left"><p>SP2</p></td>
<td align="left"><p>x86</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2008</p></td>
<td align="left"><p>标准版、企业版或数据中心版</p></td>
<td align="left"><p>SP2</p></td>
<td align="left"><p>x86</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2008 R2</p></td>
<td align="left"><p>标准版、企业版或数据中心版</p></td>
<td align="left"><p>无服务包或 SP1</p></td>
<td align="left"><p>x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server 2012</p></td>
<td align="left"><p>标准版、企业版或数据中心版</p></td>
<td align="left"><p></p></td>
<td align="left"><p>x86 或 x64</p></td>
</tr>
</tbody>
</table>

 

**注意** 应用程序虚拟化（app-v）4.6 适用于远程桌面服务的 SP2 支持这些操作系统的32位和64位版本。

 

### 适用于应用 V 4.6 SP2 之前的版本的远程桌面服务的软件要求

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">操作系统</th>
<th align="left">版本</th>
<th align="left">Service Pack</th>
<th align="left">系统体系结构</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows Server2003</p></td>
<td align="left"><p>标准版、企业版或数据中心版</p></td>
<td align="left"><p>SP1 或 SP2</p></td>
<td align="left"><p>x86</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2003 R2</p></td>
<td align="left"><p>标准版、企业版或数据中心版</p></td>
<td align="left"><p>无服务包或 SP2</p></td>
<td align="left"><p>x86</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2008</p></td>
<td align="left"><p>标准版、企业版或数据中心版</p></td>
<td align="left"><p>SP1 或 SP2</p></td>
<td align="left"><p>x86</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2008 R2</p></td>
<td align="left"><p>标准版、企业版或数据中心版</p></td>
<td align="left"><p>无服务包或 SP1</p></td>
<td align="left"><p>x64</p></td>
</tr>
</tbody>
</table>

 

**注意** 应用程序虚拟化（app-v）4.6 适用于远程桌面服务的 SP2 支持这些操作系统的32位和64位版本。

 

## 相关主题


[Application Virtualization Client 硬件和软件要求](application-virtualization-client-hardware-and-software-requirements.md)

[Application Virtualization System 要求](application-virtualization-system-requirements.md)

[如何安装 Application Virtualization Sequencer](how-to-install-the-application-virtualization-sequencer.md)

[如何升级 Application Virtualization Sequencer](how-to-upgrade-the-application-virtualization-sequencer.md)

 

 





