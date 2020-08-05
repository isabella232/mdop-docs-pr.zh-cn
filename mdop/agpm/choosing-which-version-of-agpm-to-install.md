---
title: 选择要安装的 AGPM 版本
description: 选择要安装的 AGPM 版本
author: dansimp
ms.assetid: 31357d2a-bc23-4e15-93f4-0beda8ab7a7b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 04/05/2017
ms.openlocfilehash: f8a69fb323d9f47c5b906ac3abc6ec59376ee6f7
ms.sourcegitcommit: 0a7dee11289780336d9c24ebbf27c5c1ffee441c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/04/2020
ms.locfileid: "10905599"
---
# 选择要安装的 AGPM 版本


MicrosoftAdvanced 组策略管理的每个版本 (AGPM) 支持特定版本的 Windows 操作系统。 我们强烈建议你在同一操作系统行上运行 AGPM 客户端和 AGPM 服务器。 例如，windows 10 适用于 windows Server 2016、windows 8.1 和 Windows Server2012 R2 等。

我们建议你在域中的最新版本的操作系统上安装 AGPM 服务器。 AGPM 使用组策略管理控制台 (GPMC) 备份和还原 Gpo)  (的组策略对象。 由于较新版本的 GPMC 提供的其他策略设置在早期版本中不可用，因此你可以使用最新版本的操作系统管理更多策略设置。

所有版本的 AGPM 都只能管理在同一版本或早期版本的运行 AGPM 的操作系统中引入的策略设置。 例如，如果在 Windows Server 2012 上安装了 AGPM 4.0 SP2，则可以管理 Windows Server 2012 或更早版本中引入的策略设置，但不能管理稍后在 Windows 8.1 或 Windows Server2012 R2 中引入的策略设置。

如果你的 AGPM 服务器上的 GPMC 版本比管理员用于管理组策略的计算机上的版本旧，则 AGPM 服务器将无法存储在较早版本的 GPMC 中不可用的任何策略设置。 有关 Windows 中包含的组策略设置的电子表格，请参阅[适用于 Windows 和 Windows Server 的组策略设置参考](https://go.microsoft.com/fwlink/p/?LinkId=613627)。

## AGPM 4.0 SP3


如果使用运行 Windows 10 的计算机管理 Gpo，则必须使用 AGPM 4.0 SP3。 无法在运行 Windows 10 操作系统的计算机上安装早期版本的 AGPM。

表1列出了可在其上安装 AGPM 4.0 SP3 的操作系统，以及可使用 AGPM 4.0 SP3 管理的策略设置。

**表1： AGPM 4.0 SP3 支持的操作系统和策略设置**

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong>AGPM 服务器支持的配置</strong></th>
<th align="left"><strong>AGPM 客户端支持的配置</strong></th>
<th align="left"><strong>AGPM 支持</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows Server 2019 或 Windows 10</p></td>
<td align="left"><p>Windows Server 2019 或 Windows 10</p></td>
<td align="left"><p>支持</p></td>
</tr>
 <tr class="even">
<td align="left"><p>Windows Server 2019 或 Windows 10</p></td>
<td align="left"><p>Windows Server 2019 或 Windows 10</p></td>
<td align="left"><p>支持</p></td>
</tr>
<tr class="edd">
<td align="left"><p>Windows Server2012 R2</p></td>
<td align="left"><p>Windows 10</p></td>
<td align="left"><p>通过在 KB 4015786 中概述的注意事项提供支持 <a href="https://support.microsoft.com/help/4015786/known-issues-managing-a-windows-10-group-policy-client-in-windows-serv" data-raw-source="[KB 4015786](https://support.microsoft.com/help/4015786/known-issues-managing-a-windows-10-group-policy-client-in-windows-serv)"></a>
</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2012 R2 或 Windows 8。1</p></td>
<td align="left"><p>Windows Server2012 R2 或 Windows 8。1</p></td>
<td align="left"><p>支持</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2012 R2、Windows Server 2012 或 Windows 8。1</p></td>
<td align="left"><p>Windows Server 2012 或 Windows 8。1</p></td>
<td align="left"><p>受支持，但不能编辑仅存在于 Windows 8.1 中的策略设置或首选项</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2008R2 或 Windows7</p></td>
<td align="left"><p>Windows Server2008R2 或 Windows7</p></td>
<td align="left"><p>受支持，但不能编辑仅存在于 Windows 8.1 中的策略设置或首选项</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server 2012、Windows Server2008R2 或 Windows7</p></td>
<td align="left"><p>Windows Server2008 或 WindowsVista Service Pack 1 (SP1) </p></td>
<td align="left"><p>受支持，但不能编辑仅存在于 Windows Server2012 R2、Windows Server 2012、Windows Server2008R2、Windows 8.1 或 Windows7 中的策略设置或首选项</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2008 或 Windows Vista SP1</p></td>
<td align="left"><p>Windows Server 2012、Windows Server2008R2、Windows 8 或 Windows7</p></td>
<td align="left"><p>不支持</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2008 或 Windows Vista SP1</p></td>
<td align="left"><p>Windows Server2008 或 Windows Vista SP1</p></td>
<td align="left"><p>受支持，但无法报告或编辑仅存在于 Windows Server2012 R2、Windows Server 2012、Windows Server2008R2、Windows 8.1 或 Windows7 中的策略设置或首选项</p></td>
</tr>
</tbody>
</table>

 

## AGPM 4.0 SP2


如果你使用运行 Windows Server2012 R2 或 Windows 8.1 的计算机管理 Gpo，则必须使用 AGPM 4.0 SP2。 无法在运行这些操作系统的计算机上安装早期版本的 AGPM。

表1列出了可在其上安装 AGPM 4.0 SP2 的操作系统，以及可使用 AGPM 4.0 SP2 管理的策略设置。

**表2： AGPM 4.0 SP2 支持的操作系统和策略设置**

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong>AGPM 服务器支持的配置</strong></th>
<th align="left"><strong>AGPM 客户端支持的配置</strong></th>
<th align="left"><strong>AGPM 支持</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows Server2012 R2 或 Windows 8。1</p></td>
<td align="left"><p>Windows Server2012 R2 或 Windows 8。1</p></td>
<td align="left"><p>支持</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2012 R2、Windows Server 2012 或 Windows 8。1</p></td>
<td align="left"><p>Windows Server 2012 或 Windows 8。1</p></td>
<td align="left"><p>受支持，但不能编辑仅存在于 Windows 8.1 中的策略设置或首选项</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2008R2 或 Windows7</p></td>
<td align="left"><p>Windows Server2008R2 或 Windows7</p></td>
<td align="left"><p>受支持，但不能编辑仅存在于 Windows 8.1 中的策略设置或首选项</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server 2012、Windows Server2008R2 或 Windows7</p></td>
<td align="left"><p>Windows Server2008 或 WindowsVista Service Pack 1 (SP1) </p></td>
<td align="left"><p>受支持，但不能编辑仅存在于 Windows Server2012 R2、Windows Server 2012、Windows Server2008R2、Windows 8.1 或 Windows7 中的策略设置或首选项</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2008 或 Windows Vista SP1</p></td>
<td align="left"><p>Windows Server 2012、Windows Server2008R2 或 Windows7</p></td>
<td align="left"><p>不支持</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2008 或 Windows Vista SP1</p></td>
<td align="left"><p>Windows Server2008 或 Windows Vista SP1</p></td>
<td align="left"><p>受支持，但无法报告或编辑仅存在于 Windows Server2012 R2、Windows Server 2012、Windows Server2008R2、Windows 8.1 或 Windows7 中的策略设置或首选项</p></td>
</tr>
</tbody>
</table>

 

## AGPM 4.0 SP1


表2列出了可安装 AGPM 4.0 SP1 的操作系统，以及可使用 AGPM 4.0 SP1 管理的策略设置。

**表3： AGPM 4.0 SP1 支持的操作系统和策略设置**

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong>AGPM 服务器支持的配置</strong></th>
<th align="left"><strong>AGPM 客户端支持的配置</strong></th>
<th align="left"><strong>AGPM 支持</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows Server 2012</p></td>
<td align="left"><p>Windows Server 2012</p></td>
<td align="left"><p>支持</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2008R2 或 Windows7</p></td>
<td align="left"><p>Windows Server2008R2 或 Windows7</p></td>
<td align="left"><p>受支持，但不能编辑仅存在于 Windows 8.1 中的策略设置或首选项项目</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server 2012、Windows Server2008R2 或 Windows7</p></td>
<td align="left"><p>Windows Server2008 或 Windows Vista SP1</p></td>
<td align="left"><p>受支持，但不能编辑仅存在于 Windows Server2008R2 或 Windows7 中的策略设置或首选项</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2008 或 Windows Vista SP1</p></td>
<td align="left"><p>Windows Server 2012、Windows Server2008R2 或 Windows7</p></td>
<td align="left"><p>支持</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2008 或 Windows Vista SP1</p></td>
<td align="left"><p>Windows Server2008 或 Windows Vista SP1</p></td>
<td align="left"><p>受支持，但无法报告或编辑仅存在于 Windows Server2008R2 或 Windows7 中的策略设置或首选项</p></td>
</tr>
</tbody>
</table>

 

## AGPM 4。0


表3列出了可安装 AGPM 4.0 的操作系统，以及可使用 AGPM 4.0 管理的策略设置。

**表4： AGPM 4.0 支持的操作系统和策略设置**

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">AGPM 服务器支持的操作系统</th>
<th align="left">AGPM 客户端支持的操作系统</th>
<th align="left">AGPM 支持</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows Server2008R2 或 Windows7</p></td>
<td align="left"><p>Windows Server2008R2 或 Windows7</p></td>
<td align="left"><p>支持</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2008R2 或 Windows7</p></td>
<td align="left"><p>Windows Server2008 或 Windows Vista SP1</p></td>
<td align="left"><p>受支持，但不能编辑仅存在于 Windows Server2008R2 或 Windows7 中的策略设置或首选项</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2008 或 Windows Vista SP1</p></td>
<td align="left"><p>Windows Server2008R2 或 Windows7</p></td>
<td align="left"><p>不支持</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2008 或 Windows Vista SP1</p></td>
<td align="left"><p>Windows Server2008 或 Windows Vista SP1</p></td>
<td align="left"><p>受支持，但无法报告或编辑仅存在于 Windows Server2008R2 或 Windows7 中的策略设置或首选项</p></td>
</tr>
</tbody>
</table>

 

## 在 AGPM 4.0 之前的 AGPM 版本


表4列出了可在其上安装 agpm 4.0 之前的 AGPM 版本的操作系统。 如果未列出操作系统，则无法在该操作系统上安装 AGPM。

**表5：在 AGPM 4.0 之前的 AGPM 版本的受支持的操作系统**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">操作系统</th>
<th align="left">可安装的 AGPM 版本</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows Server2008</p></td>
<td align="left"><p>3.0</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Vista SP1</p></td>
<td align="left"><p>3.0</p></td>
</tr>
<tr class="odd">
<td align="left"><p>WindowsVista 未安装 service pack (32 位) </p></td>
<td align="left"><p>2.5</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2003 (32 位) </p></td>
<td align="left"><p>2.5</p></td>
</tr>
</tbody>
</table>

 

## 如何获取 MDOP 技术


AGPM 4.0 SP2 是 Microsoft 桌面优化包 (MDOP) 的一部分。 MDOP 是 Microsoft 软件保障的一部分。 有关 Microsoft 软件保证和获取 MDOP 的详细信息，请参阅[如何获取 mdop](https://go.microsoft.com/fwlink/?LinkId=322049) (https://go.microsoft.com/fwlink/?LinkId=322049) 。

## 相关主题


[高级组策略管理](index.md)

 

 





