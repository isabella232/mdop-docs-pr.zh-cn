---
title: AGPM 4.0 SP3 中的新增功能
description: AGPM 4.0 SP3 中的新增功能
author: dansimp
ms.assetid: df495d55-9fbf-4f7e-a7af-3905f4f8790e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 09/27/2016
ms.openlocfilehash: a98bda82fab561113522382b4de6539a9dc23d0c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802488"
---
# AGPM 4.0 SP3 中的新增功能


此内容介绍 Microsoft 高级组策略管理（AGPM）4.0 服务 Pack3 （SP3）的增强功能和受支持的配置。 如果此内容和其他 AGPM 文档之间存在差异，请考虑此内容的权威，并假定它取代了其他文档。

## <a href="" id="what-s-new"></a>新增内容


AGPM 4.0 SP3 支持以下功能和功能。

### 对 Windows10 的支持

AGPM 4.0 SP3 添加了对 Windows10 和 Windows Server 2016 操作系统的支持。

### 对 PowerShell 的支持

AGPM 4.0 SP3 添加了对 PowerShell cmdlet 的支持。 有关 AGPM 4.0 SP3 中可用的 cmdlet （包括说明和语法）的列表，请参阅[Microsoft 桌面优化包自动化与 Windows PowerShell](https://docs.microsoft.com/powershell/mdop/get-started?view=win-mdop2-ps)。

### 客户反馈和修补程序汇总

AGPM 4.0 SP3 包括所有修复的汇总，包括 Microsoft 高级组策略管理 4.0 SP2 以及有关自 AGPM 4.0 SP2 以来发现的问题的任何修补程序。

### 无需重新输入配置参数即可升级到 AGPM 4.0 SP3 的功能

你可以将 AGPM 客户端或 AGPM 服务器升级到 AGPM 4.0 SP3，而不提示仅从 AGPM 4.0 和更高版本重新输入配置参数（称为 "智能升级"），如下表所示。 如果要从其他版本的 AGPM 升级到 AGPM 4.0 SP3 （如表中所示），则必须使用 "经典升级"，这需要重新输入配置参数。 由于 AGPM 的每个版本都与特定操作系统相关联，请参阅[选择要安装的 Agpm 版本](https://go.microsoft.com/fwlink/?LinkId=254350)，并确保在升级 AGPM 之前升级操作系统。

**AGPM 4.0 SP3 支持的升级**

<table style="width:100%;">
<colgroup>
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>可升级的 AGPM 版本</strong></p></td>
<td align="left"><p><strong>2.5</strong></p></td>
<td align="left"><p><strong>3.0</strong></p></td>
<td align="left"><p><strong>4.0</strong></p></td>
<td align="left"><p><strong>4.0 SP1</strong></p></td>
<td align="left"><p><strong>4.0 SP2</strong></p></td>
<td align="left"><p><strong>4.0 SP3</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p>2.5</p></td>
<td align="left"><p>不适用</p></td>
<td align="left"><p>经典升级</p></td>
<td align="left"><p>经典升级</p></td>
<td align="left"><p>安装被阻止</p></td>
<td align="left"><p>安装被阻止</p></td>
<td align="left"><p>安装被阻止</p></td>
</tr>
<tr class="odd">
<td align="left"><p>3.0</p></td>
<td align="left"><p>不适用</p></td>
<td align="left"><p>不适用</p></td>
<td align="left"><p>经典升级</p></td>
<td align="left"><p>安装被阻止</p></td>
<td align="left"><p>安装被阻止</p></td>
<td align="left"><p>安装被阻止</p></td>
</tr>
<tr class="even">
<td align="left"><p>4.0</p></td>
<td align="left"><p>不适用</p></td>
<td align="left"><p>不适用</p></td>
<td align="left"><p>不适用</p></td>
<td align="left"><p>智能升级</p></td>
<td align="left"><p>智能升级</p></td>
<td align="left"><p>智能升级</p></td>
</tr>
<tr class="odd">
<td align="left"><p>4.0 SP1</p></td>
<td align="left"><p>不适用</p></td>
<td align="left"><p>不适用</p></td>
<td align="left"><p>不适用</p></td>
<td align="left"><p>不适用</p></td>
<td align="left"><p>智能升级</p></td>
<td align="left"><p>智能升级</p></td>
</tr>
<tr class="even">
<td align="left"><p>4.0 SP2</p></td>
<td align="left"><p>不适用</p></td>
<td align="left"><p>不适用</p></td>
<td align="left"><p>不适用</p></td>
<td align="left"><p>不适用</p></td>
<td align="left"><p>不适用</p></td>
<td align="left"><p>智能升级</p></td>
</tr>
</tbody>
</table>

 

## 支持的配置


AGPM 4.0 SP3 支持下表中的配置。 尽管 AGPM 支持混合配置，但我们强烈建议你在相同的操作系统行上运行 AGPM 客户端和 AGPM 服务器，例如，Windows10 Windows Server 2016、windows 8.1 和 Windows Server 2012 R2 等。

**AGPM 4.0 SP3 支持的操作系统和策略设置**

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
<td align="left"><p>Windows Server 2016 或 Windows 10</p></td>
<td align="left"><p>Windows10</p></td>
<td align="left"><p>支持</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2012 R2 或 Windows 8。1</p></td>
<td align="left"><p>Windows Server2012 R2 或 Windows 8。1</p></td>
<td align="left"><p>支持</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2012 R2、Windows Server 2012 或 Windows 8。1</p></td>
<td align="left"><p>Windows Server 2012</p></td>
<td align="left"><p>受支持，但不能编辑仅存在于 Windows 8.1 中的策略设置或首选项</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2008R2 或 Windows7</p></td>
<td align="left"><p>Windows Server2008R2 或 Windows7</p></td>
<td align="left"><p>受支持，但不能编辑仅存在于 Windows 8.1 中的策略设置或首选项</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server 2012、Windows Server2008R2 或 Windows7</p></td>
<td align="left"><p>Windows Server2008 或 WindowsVista Service Pack 1 （SP1）</p></td>
<td align="left"><p>受支持，但不能编辑仅存在于 Windows Server2012 R2、Windows Server 2012、Windows Server2008R2、Windows 8.1 或 Windows7 中的策略设置或首选项</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2008 或 Windows Vista SP1</p></td>
<td align="left"><p>Windows Server 2012、Windows Server2008R2 或 Windows7</p></td>
<td align="left"><p>不支持</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2008 或 Windows Vista SP1</p></td>
<td align="left"><p>Windows Server2008 或 Windows Vista SP1</p></td>
<td align="left"><p>受支持，但无法报告或编辑仅存在于 Windows Server2012 R2、Windows Server 2012、Windows Server2008R2、Windows 8.1 或 Windows7 中的策略设置或首选项</p></td>
</tr>
</tbody>
</table>

 

## 安装 AGPM 4.0 SP3 的先决条件

下表介绍了当缺少远程服务器管理工具中的 .NET Framework 4.5.1、PowerShell 3.0 或 GPMC 时，AGPM 4.0 SP3 客户端和服务器安装程序的行为。

| AGPM 客户端            |                                                                                                 |                                                                            | AGPM 服务器                                                                     |                                                                                                 |                                                                                 |
|------------------------|-------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------|---------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------|
| 操作系统       | .NET Framework                                                                                  | PowerShell                                                                 | 远程服务器管理工具                                              | .NET Framework                                                                                  | 远程服务器管理工具                                              |
| Windows 10             | 如果未启用或安装 .NET Framework 4.5.1，安装程序将阻止安装。 | 如果未安装 Powershell 3.0，安装程序将阻止安装。 | 如果 GPMC 未启用或未安装，安装程序将阻止安装。 | 如果未启用或安装 .NET Framework 4.5.1，安装程序将阻止安装。 | 如果 GPMC 未启用或未安装，安装程序将阻止安装。 |
| Windows 8.1            | 如果未启用或安装 .NET Framework 4.5.1，安装程序将阻止安装。 | 如果未安装 Powershell 3.0，安装程序将阻止安装。 | 如果 GPMC 未启用或未安装，安装程序将阻止安装。 | 如果未启用或安装 .NET Framework 4.5.1，安装程序将阻止安装。 | 如果 GPMC 未启用或未安装，安装程序将阻止安装。 |
| Windows Server 2012 R2 | 如果未启用或安装 .NET Framework 4.5.1，安装程序将阻止安装。 | 如果未安装 Powershell 3.0，安装程序将阻止安装。 | 如果未启用 GPMC，安装程序将在安装期间启用它。   | 如果未启用或安装 .NET Framework 4.5.1，安装程序将阻止安装。 | 如果未启用 GPMC，安装程序将在安装期间启用它。   |

 

## 如何获取 MDOP 技术


AGPM 4.0 SP3 是 Microsoft 桌面优化包（MDOP）的一部分，自 MDOP 2015 起。 MDOP 是 Microsoft 软件保障的一部分。 有关 Microsoft 软件保证和获取 MDOP 的详细信息，请参阅[如何获取 mdop](https://go.microsoft.com/fwlink/?LinkId=322049) （ https://go.microsoft.com/fwlink/?LinkId=322049) 。

## 相关主题


[高级组策略管理](index.md)

[Microsoft 高级组策略管理 4.0 SP3 发行说明](release-notes-for-microsoft-advanced-group-policy-management-40-sp3.md)

[选择要安装的 AGPM 版本](choosing-which-version-of-agpm-to-install.md)

 

 





