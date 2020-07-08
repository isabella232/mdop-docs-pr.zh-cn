---
title: Sequencer 硬件和软件要求
description: Sequencer 硬件和软件要求
author: dansimp
ms.assetid: 36084e12-831d-452f-a4a4-45f07f9ce471
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0d4e12a5803a3c9033513424826b49bc0bca5885
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798790"
---
# Sequencer 硬件和软件要求


本主题介绍运行 Microsoft Application Virtualization （app-v） Sequencer 的计算机的最低建议硬件和软件要求。

在安装 Sequencer 之前以及对每个应用程序进行排序后，必须将干净的操作系统映像还原到顺序计算机。 你可以使用以下方法之一来还原运行 Sequencer 的计算机：

-   重新格式化硬盘并重新安装操作系统。

-   使用另一个磁盘映像软件还原运行 Sequencer 映像的计算机上的硬盘。

下表列出了运行 App-v 排序器的推荐硬件要求。

### <a href="" id="hardware-requirements-"></a>硬件要求

-   处理器-英特尔奔腾 III、1 GHz （32位或64位）。 排序过程是一个单线程进程，不会利用双处理器。

-   内存-1GB 或更高版本，建议使用 2 GB。

-   硬盘-40 千兆字节（GB）硬盘空间，至少有 15 GB 的可用硬盘空间。 我们建议您至少拥有所需的应用程序所需的磁盘空间的三倍。

    **注意** 排序需要大量的磁盘使用。 快速磁盘速度会减少排序时间。

     

### 软件要求

下表列出了运行 Sequencer 所支持的操作系统。

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

### 远程桌面服务的软件要求

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
<td align="left"><p></p></td>
<td align="left"><p>x86</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2008</p></td>
<td align="left"><p>标准版、企业版或数据中心</p></td>
<td align="left"><p>SP1 或 SP2</p></td>
<td align="left"><p>x86</p></td>
</tr>
</tbody>
</table>

 

**注意** 适用于远程桌面服务的应用程序虚拟化（app-v）4.6 支持这些操作系统的32位和64位版本。

 

## 相关主题


[Application Virtualization Sequencer 概述](application-virtualization-sequencer-overview.md)

 

 





