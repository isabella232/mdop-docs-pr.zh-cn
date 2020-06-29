---
title: DaRT 8.0 支持的配置
description: DaRT 8.0 支持的配置
author: dansimp
ms.assetid: 95d68e5c-d202-4f4a-adef-d2098328172e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 02c891555992652bf2a9b2b674ab8377536ef9d6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803466"
---
# DaRT 8.0 支持的配置


本主题指定在你的环境中安装和运行 Microsoft 诊断和恢复工具集（DaRT）8.0 所需的必备软件和支持的配置要求。 将指定运行 DaRT 8.0 所需的操作系统要求和系统要求。 有关创建 DaRT 恢复映像时需要考虑的先决条件的信息，请参阅[规划以创建 dart 8.0 恢复映像](planning-to-create-the-dart-80-recovery-image-dart-8.md)。

有关适用于更高版本的受支持的配置，请参阅适用版本的文档。

你可以通过两种方式之一安装 DaRT。 你可以在 IT 管理员计算机上安装所有功能，你将执行与运行 DaRT 相关联的所有任务。 或者，你也可以在管理员计算机上安装创建恢复映像的 DaRT 功能，然后在技术支持计算机上安装用于运行 DaRT （即 DaRT 远程连接查看器）的功能。

## <a href="" id="---------dart-8-0-prerequisite-software"></a> DaRT 8.0 必备软件


在安装 DaRT 之前，请确保满足以下先决条件。

### 管理员计算机先决条件

下表列出了安装 DaRT 8.0 和所有 DaRT 工具时管理员计算机的安装先决条件。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">必备</th>
<th align="left">详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>Windows 评估和开发工具包（ADK）</strong></p></td>
<td align="left"><p>对于 DaRT 恢复映像向导是必需的。 包含部署工具，这些工具用于自定义、部署和服务 Windows 映像，并且包含 Windows 预安装环境（Windows PE）。 如果仅安装远程连接查看器和/或崩溃分析器，则不需要 ADK。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>.NET Framework 4。5</strong></p></td>
<td align="left"><p>DaRT 恢复映像向导所需。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Windows 开发工具包或软件开发工具包（可选）</strong></p></td>
<td align="left"><p>崩溃分析器需要 Windows 驱动程序工具包中的 Windows 8 调试工具来分析内存转储文件。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>Windows 8 64 位 ISO 镜像</strong></p></td>
<td align="left"><p>DaRT 需要 windows 8 媒体中的 Windows 恢复环境（Windows RE）映像。 下载32位或64位版本的 Windows 8，具体取决于你要创建的 DaRT 恢复映像的类型。 如果你在你的环境中支持这两种系统类型，请下载 Windows 8 的两个版本。</p></td>
</tr>
</tbody>
</table>

 

### 技术支持计算机必备条件

下表列出了运行 DaRT 8.0 远程连接查看器时帮助台计算机的安装先决条件。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">必备</th>
<th align="left">详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>DaRT 8.0 远程连接查看器</strong></p></td>
<td align="left"><p>必须安装在 Windows 8 操作系统上。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>NET Framework 4。5</strong></p></td>
<td align="left"><p>DaRT 恢复映像向导所需</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Windows 调试工具</strong></p></td>
<td align="left"><p>仅在安装崩溃分析工具时需要</p></td>
</tr>
</tbody>
</table>

 

### 最终用户计算机先决条件

除了 Windows 8 操作系统之外，没有必须安装在最终用户计算机上的必备软件。

## <a href="" id="---------dart-operating-system-requirements"></a> DaRT 操作系统要求


### 管理员计算机系统要求

下表列出了 DaRT 管理员计算机安装支持的操作系统。

**注意** 请确保为要在管理员计算机上安装的任何其他工具分配足够的空间。

 

**注意** Microsoft 提供对当前服务包的支持，在某些情况下，还提供了之前的服务包。 若要查找产品的支持时间表，请参阅[支持生命周期的服务包](https://go.microsoft.com/fwlink/p/?LinkId=31975)。 有关 Microsoft 支持生命周期策略的其他信息，请参阅[Microsoft 支持生命周期支持策略常见问题解答](https://go.microsoft.com/fwlink/p/?LinkId=31976)。

 

<table style="width:100%;">
<colgroup>
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">操作系统</th>
<th align="left">版本</th>
<th align="left">Service Pack</th>
<th align="left">系统体系结构</th>
<th align="left">操作系统要求</th>
<th align="left">运行 DaRT 的内存要求</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows8</p></td>
<td align="left"><p>所有版本</p></td>
<td align="left"><p>不适用</p></td>
<td align="left"><p>64 位</p></td>
<td align="left"><p>2 GB</p></td>
<td align="left"><p>2.5 GB</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows8</p></td>
<td align="left"><p>所有版本</p></td>
<td align="left"><p>不适用</p></td>
<td align="left"><p>32 位</p></td>
<td align="left"><p>1 GB</p></td>
<td align="left"><p>1.5 GB</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server 2012</p></td>
<td align="left"><p>标准、企业、数据中心</p></td>
<td align="left"><p>不适用</p></td>
<td align="left"><p>64 位</p></td>
<td align="left"><p>512 MB</p></td>
<td align="left"><p>1. 0 GB</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="-------------dart-help-desk-computer-system-requirements"></a> DaRT 技术支持计算机系统要求

如果你允许帮助台远程对计算机进行故障排除，则必须在技术支持计算机上安装远程连接查看器。 你可以选择在技术支持计算机上安装崩溃分析器工具。

DaRT 8.0 使技术支持人员能够使用 DaRT 7.0 或 DaRT 8.0 远程连接查看器连接到 DaRT 8.0 计算机。 DaRT 7.0 远程连接查看器需要 Windows 7 操作系统，而 DaRT 8.0 远程连接查看器需要 Windows 8。 DaRT 8.0 远程连接查看器和所有其他 DaRT 8.0 工具只能安装在运行 Windows 8 的计算机上。

下表列出了 DaRT 技术支持计算机安装支持的操作系统。

<table style="width:100%;">
<colgroup>
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">操作系统</th>
<th align="left">版本</th>
<th align="left">Service Pack</th>
<th align="left">系统体系结构</th>
<th align="left">操作系统要求</th>
<th align="left">运行 DaRT 的内存要求</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows8</p></td>
<td align="left"><p>所有版本</p></td>
<td align="left"><p>不适用</p></td>
<td align="left"><p>64 位</p></td>
<td align="left"><p>2 GB</p></td>
<td align="left"><p>2.5 GB</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows8 （仅限远程连接查看器8.0）</p></td>
<td align="left"><p>所有版本</p></td>
<td align="left"><p>不适用</p></td>
<td align="left"><p>32 位</p></td>
<td align="left"><p>1 GB</p></td>
<td align="left"><p>1.5 GB</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows 7 （仅限远程连接查看器7.0）</p></td>
<td align="left"><p>所有版本</p></td>
<td align="left"><p>SP1、SP2</p></td>
<td align="left"><p>64位或32位</p></td>
<td align="left"><p>1 GB</p></td>
<td align="left"><p>不适用</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server 2012</p></td>
<td align="left"><p>标准、企业、数据中心</p></td>
<td align="left"><p>不适用</p></td>
<td align="left"><p>64 位</p></td>
<td align="left"><p>51</p></td>
<td align="left"><p>1.0 GB</p></td>
</tr>
</tbody>
</table>

 

DaRT 对于最终用户计算机还具有以下最低硬件要求：

CD 或 DVD 驱动器或 USB 端口-仅当你使用 CD、DVD 或 USB 在企业中部署 DaRT 时才需要。

从 CD 或 DVD、USB 闪存驱动器或从远程或恢复分区启动计算机的 BIOS 支持。

### <a href="" id="-------------dart-end-user-computer-system-requirements"></a> DaRT 最终用户计算机系统要求

DaRT 中的 "诊断和恢复工具集" 窗口要求最终用户计算机使用下列操作系统之一以及可用于 DaRT 的指定系统内存量：

<table style="width:100%;">
<colgroup>
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">操作系统</th>
<th align="left">版本</th>
<th align="left">Service Pack</th>
<th align="left">系统体系结构</th>
<th align="left">操作系统要求</th>
<th align="left">RAM 要求</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows8</p></td>
<td align="left"><p>所有版本</p></td>
<td align="left"><p>不适用</p></td>
<td align="left"><p>64 位</p></td>
<td align="left"><p>2 GB</p></td>
<td align="left"><p>2.5 GB</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows8</p></td>
<td align="left"><p>所有版本</p></td>
<td align="left"><p>不适用</p></td>
<td align="left"><p>32 位</p></td>
<td align="left"><p>1 GB</p></td>
<td align="left"><p>1.5 GB</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server 2012</p></td>
<td align="left"><p>标准、企业、数据中心</p></td>
<td align="left"><p>不适用</p></td>
<td align="left"><p>64 位</p></td>
<td align="left"><p>512 MB</p></td>
<td align="left"><p>1.0 GB</p></td>
</tr>
</tbody>
</table>

 

## 相关主题


[计划部署 DaRT 8.0](planning-to-deploy-dart-80-dart-8.md)

 

 





