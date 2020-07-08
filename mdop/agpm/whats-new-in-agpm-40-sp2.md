---
title: AGPM 4.0 SP2 中的新增功能
description: AGPM 4.0 SP2 中的新增功能
author: dansimp
ms.assetid: 5c0dcab4-f27d-4153-8b8e-b280b080be51
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 56369207780cf0795f16eda91f249a26270c4b47
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801700"
---
# AGPM 4.0 SP2 中的新增功能


此内容介绍 Microsoft 高级组策略管理（AGPM）4.0 服务 Pack2 （SP2）的增强功能和受支持的配置。 如果此内容和其他 AGPM 文档之间存在差异，请考虑此内容的权威，并假定它取代了其他文档。

## <a href="" id="what-s-new"></a>新增内容


AGPM 4.0 SP2 支持以下特性和功能。

### Windows 8.1 和 Windows Server2012 R2 支持

AGPM 4.0 SP2 添加了对 Windows 8.1 和 Windows Server2012 R2 操作系统的支持。

### 新的和更改的客户端扩展

已为 AGPM 添加或更改了组策略客户端扩展，以支持 Windows 8.1 中的新策略设置。 这些策略设置使组策略管理员能够管理和跟踪 Windows 8.1-在两个组策略对象（Gpo）或模板之间更改的特定策略设置。 若要查看客户端扩展，请使用在 AGPM 客户端中可用的 "设置" 和 "差异" 报表。

新的和已更改的组策略客户端扩展为：

-   **指定工作文件夹设置**。 如果启用此策略设置，IT 管理员可以配置要自动创建的工作文件夹。 "工作文件夹" 功能使最终用户能够将文件从其 Windows 桌面设备同步到其其他设备。 使用此策略设置可在最终用户的设备上创建同步关系，并配置如何识别存储用户工作文件夹的文件服务器。 如果选中 "**自动设置同步**" 复选框，则将在不使用用户输入的情况下创建同步合作关系，并且数据将自动开始与用户的设备同步。 如果未选中 "**自动设置同步**" 复选框，则用户必须提供输入才能启动同步。

-   **为所有用户强制自动设置**。 如果启用此策略设置，IT 管理员可以确定是否在最终用户的设备上自动创建工作文件夹，而无需最终用户输入。 如果启用此策略设置，将根据你配置 "**指定工作文件夹设置**" 策略设置的方式设置同步。 如果将 "**强制自动设置为所有用户**" 策略设置设置为 "**已禁用**" 或 "**未配置**"，则将根据你在 "**指定工作文件夹设置**" 策略设置中设置**自动提供**选项来配置工作文件夹合作关系。

有关工作文件夹功能的详细信息，请参阅[工作文件夹概述](https://go.microsoft.com/fwlink/?LinkId=330444)。

### 客户反馈和修补程序汇总

AGPM 4.0 SP2 包括修复程序的汇总，用于解决自 AGPM 4.0 服务 Pack1 （SP1）发布以来发现的问题。 AGPM 4.0 SP2 包含 Microsoft 高级组策略管理 4.0 SP1 Hotfix1 的最新修补程序，包括 Microsoft 高级组策略管理 4.0 SP1。 有关详细信息，请参阅知识文库文章[2873472](https://go.microsoft.com/fwlink/?LinkId=325400)。

### "设置" 和 "差异" 报告中的新组策略扩展

新的组策略扩展已添加到 "设置" 和 "差异" 报告。

### 安装程序更改和支持

AGPM 4.0 SP2 安装程序的更改和支持包括：

-   如果在 Windows 8 或 Windows Server 2012 操作系统或更高版本的操作系统上安装了 AGPM 4.0 SP2，AGPM 安装程序将验证是否已安装所需的必备软件（组策略管理控制台（GPMC）和 Microsoft .NET Framework 3.5）。 如果未安装此必备软件，则将阻止 AGPM 4.0 SP2 安装。

-   安装 AGPM 服务器时，将自动启用 WCF 激活、非 HTTP 激活和 Windows 进程激活服务。

-   在 WindowsVista 客户端操作系统和更高版本的操作系统上，在安装 AGPM 4.0 SP2 之前，下载适用于您的操作系统的远程系统管理工具的相应版本。

-   AGPM 4.0 SP2 支持与早期支持的操作系统的向后兼容性。

### 无需重新设置配置参数即可升级到 AGPM 4.0 SP2 的功能

你可以将 AGPM 客户端或 AGPM 服务器升级到 AGPM 4.0 SP2，而不提示仅从 AGPM 4.0 开始重新输入配置参数（称为 "智能升级"），如下表所示。 如果要从其他版本的 AGPM 升级到 AGPM 4.0 SP2 （如表中所示），则必须使用 "经典" 升级，这需要重新输入配置参数。 由于 AGPM 的每个版本都与特定操作系统相关联，请参阅[选择要安装的 Agpm 版本](https://go.microsoft.com/fwlink/?LinkId=254350)，并确保在升级 AGPM 之前升级操作系统。

**AGPM 4.0 SP2 支持的升级**

<table style="width:100%;">
<colgroup>
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>可升级的 AGPM 版本</strong></p></td>
<td align="left"><p><strong>2.5</strong></p></td>
<td align="left"><p><strong>3.0</strong></p></td>
<td align="left"><p><strong>4.0</strong></p></td>
<td align="left"><p><strong>4.0 SP1</strong></p></td>
<td align="left"><p><strong>4.0 SP2</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p>2.5</p></td>
<td align="left"><p>不适用</p></td>
<td align="left"><p>经典升级</p></td>
<td align="left"><p>经典升级</p></td>
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
</tr>
<tr class="even">
<td align="left"><p>4.0</p></td>
<td align="left"><p>不适用</p></td>
<td align="left"><p>不适用</p></td>
<td align="left"><p>不适用</p></td>
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
</tr>
</tbody>
</table>

 

## 支持的配置


AGPM 4.0 SP2 支持下表中的配置。 尽管 AGPM 支持混合配置，但我们强烈建议你在相同的操作系统行上运行 AGPM 客户端和 AGPM 服务器，例如，具有 windows Server2012 R2 的 windows 8.1 和 windows Server 2012 的 windows 8 等。

**AGPM 4.0 SP2 支持的操作系统和策略设置**

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
<td align="left"><p>Windows Server2012 R2、Windows Server 2012、Windows 8.1 或 Windows 8</p></td>
<td align="left"><p>Windows Server 2012 或 Windows 8</p></td>
<td align="left"><p>受支持，但不能编辑仅存在于 Windows 8.1 中的策略设置或首选项</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2008R2 或 Windows7</p></td>
<td align="left"><p>Windows Server2008R2 或 Windows7</p></td>
<td align="left"><p>受支持，但不能编辑仅存在于 Windows 8.1 或 Windows 8 中的策略设置或首选项</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server 2012、Windows Server2008R2、Windows 8 或 Windows7</p></td>
<td align="left"><p>Windows Server2008 或 WindowsVista Service Pack 1 （SP1）</p></td>
<td align="left"><p>受支持，但不能编辑仅存在于 Windows Server2012 R2、Windows Server 2012、Windows Server2008R2、Windows 8.1、windows 8 或 Windows7 中的策略设置或首选项</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2008 或 Windows Vista SP1</p></td>
<td align="left"><p>Windows Server 2012、Windows Server2008R2、Windows 8 或 Windows7</p></td>
<td align="left"><p>不支持</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2008 或 Windows Vista SP1</p></td>
<td align="left"><p>Windows Server2008 或 Windows Vista SP1</p></td>
<td align="left"><p>受支持，但不能报告或编辑仅存在于 Windows Server2012 R2、Windows Server 2012、Windows Server2008R2、Windows 8.1、windows 8 或 Windows7 中的策略设置或首选项</p></td>
</tr>
</tbody>
</table>

 

## 安装 AGPM 4.0 SP2 的先决条件


下表介绍了当 .NET Framework 3.5 或远程服务器管理工具中的 GPMC 缺失时 Windows 8.1 上的 AGPM 4.0 SP2 客户端和服务器安装程序的行为。

**AGPM 客户端**

**AGPM 服务器**

**操作系统**

**.NET Framework**

**远程服务器管理工具**

**.NET Framework**

**远程服务器管理工具**

**Windows 8。1**

如果未启用或安装 .NET Framework 3.5，安装程序将阻止安装。

如果 GPMC 未启用或未安装，安装程序将阻止安装。

如果未启用或安装 .NET Framework 3.5，安装程序将阻止安装。

如果 GPMC 未启用或未安装，安装程序将阻止安装。

**Windows Server2012 R2**

如果未启用或安装 .NET Framework 3.5，安装程序将阻止安装。

如果未启用 GPMC，安装程序将在安装期间启用它。

如果未启用或安装 .NET Framework 3.5，安装程序将阻止安装。

如果未启用 GPMC，安装程序将在安装期间启用它。

 

## 如何获取 MDOP 技术


AGPM 4.0 SP2 是 Microsoft 桌面优化包（MDOP）的一部分。 MDOP 是 Microsoft 软件保障的一部分。 有关 Microsoft 软件保证和获取 MDOP 的详细信息，请参阅[如何获取 mdop](https://go.microsoft.com/fwlink/?LinkId=322049) （ https://go.microsoft.com/fwlink/?LinkId=322049) 。

## 相关主题


[高级组策略管理](index.md)

[Microsoft 高级组策略管理 4.0 SP2 发行说明](release-notes-for-microsoft-advanced-group-policy-management-40-sp2.md)

[选择要安装的 AGPM 版本](choosing-which-version-of-agpm-to-install.md)

 

 





