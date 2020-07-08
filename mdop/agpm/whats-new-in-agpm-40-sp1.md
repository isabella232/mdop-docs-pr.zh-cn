---
title: AGPM 4.0 SP1 中的新增功能
description: AGPM 4.0 SP1 中的新增功能
author: dansimp
ms.assetid: c6a3d94a-13c3-44e6-a466-c3011879999e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: eca1ee4a1c2eb943a25246dc31b127eaf72ff5fc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801703"
---
# AGPM 4.0 SP1 中的新增功能


此 "新增功能" 内容介绍 Microsoft 高级组策略管理（AGPM） 4.0 SP1 的增强功能和受支持的配置。 如果此内容和其他 AGPM 文档之间存在差异，此内容应视为权威内容，并且应该取代本产品附带的内容。

## <a href="" id="what-s-new"></a>新增内容


AGPM 4.0 SP1 支持下列增强：

### 新的和更改的客户端扩展

已为 AGPM 添加或更改了组策略客户端扩展（CSEs），以支持 Windows 8 和 Windows Server 2012 中的新组策略。 这些组策略使组策略管理员能够管理和跟踪在两个组策略对象（Gpo）或模板之间更改的 Windows 8 特定组策略设置。 你还可以使用特定于 Windows 8 的设置创建自定义 Gpo，并将 Gpo 配置和保存为模板。 若要查看 CSEs，请使用 AGPM 4.0 SP1 客户端中提供的 "设置" 和 "差异" 报表。

新的和已更改的组策略客户端扩展为：

-   **中心访问策略：** 允许组策略管理员指定组策略服务器（例如，文件服务器）上的中心访问策略。 中心访问策略是由 GPO 项目指定并应用于策略目标的授权策略，用于促进对资源的集中访问和控制。 必须在 Active Directory 中的组策略客户端计算机上配置这些中心访问策略。 组策略将适用的中心访问策略的知识分配给必须强制使用的计算机。

-   **名称解析策略更改：** 允许组策略管理员为 DNS 客户端计算机上的 DNS 安全和 DirectAccess 配置设置。 添加了用于配置常规 DNS 服务器设置和编码设置的新选项卡。

-   **组策略首选项更改：** 添加对 Windows 8 中添加的 Internet Explorer 10 设置的配置和管理的支持。

-   **远程应用程序和桌面连接：** 允许组策略管理员指定用于远程应用程序和桌面连接的默认连接 URL。

-   **Windows To Go 启动选项：** 允许组策略管理员配置当包含 Windows To Go 工作区的 USB 设备已连接时，计算机是否将引导到 Windows To Go。

-   **Windows To Go 休眠选项：** 允许组策略管理员配置当计算机从 Windows To Go 工作区启动时，计算机是否可以使用休眠睡眠状态（S4）。

### 客户反馈和修补程序汇总

AGPM 4.0 SP1 包括自 AGPM 4.0 发布以来发现的解决问题的修补程序汇总。 AGPM 4.0 SP1 包含的最新修复程序，包括 Microsoft 高级组策略管理4.0 修复程序1。

### "设置和差异" 报表显示新的组策略扩展

新的组策略扩展已添加到 "设置" 和 "差异" 报告。

### 安装程序更改和支持

AGPM 4.0 SP1 安装程序的更改和支持如下所示：

-   如果在 Windows 8 或 Windows Server 2012 上安装了 AGPM 4.0 SP1，AGPM 安装程序将验证是否已安装所需的必备软件（组策略管理控制台和 .NET 3.5 Framework）。 如果未安装这些必备组件，则将阻止 AGPM 4.0 SP1 安装。

-   安装 AGPM 4.0 SP1 时，将自动启用 WCF 激活、非 HTTP 激活和 Windows 进程激活服务。

-   在 Windows Vista、Windows 7 和 Windows 8 客户端操作系统上，下载适用于你的操作系统的远程系统管理工具包版本，然后再安装 AGPM 4.0 SP1。

-   支持与旧版支持的操作系统的向后兼容性。

### 无需重新输入配置参数即可升级或更新到 AGPM 4.0 SP1 的功能

您只能从 AGPM 4.0 将 AGPM 客户端或服务器升级到 AGPM 4.0 SP1，而无需提示重新输入配置参数（称为 "智能升级"），如下表所示。 如果要从其他版本的 AGPM 升级到 AGPM 4.0 SP1 （如表中所示），则必须使用 "经典升级"，这要求重新输入配置参数。 由于你的每个版本的 AGPM 都与特定操作系统相关联，因此请参阅[选择要安装的 Agpm 版本](https://go.microsoft.com/fwlink/?LinkId=254350)，并确保在执行升级之前根据需要升级操作系统。

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>可升级的 AGPM 版本</strong></p></td>
<td align="left"><p><strong>2.5</strong></p></td>
<td align="left"><p><strong>3.0</strong></p></td>
<td align="left"><p><strong>4.0</strong></p></td>
<td align="left"><p><strong>4.0 SP1</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p>2.5</p></td>
<td align="left"><p>不适用</p></td>
<td align="left"><p>经典升级</p></td>
<td align="left"><p>经典升级</p></td>
<td align="left"><p>安装被阻止</p></td>
</tr>
<tr class="odd">
<td align="left"><p>3.0</p></td>
<td align="left"><p>不适用</p></td>
<td align="left"><p>不适用</p></td>
<td align="left"><p>经典升级</p></td>
<td align="left"><p>安装被阻止</p></td>
</tr>
<tr class="even">
<td align="left"><p>4.0</p></td>
<td align="left"><p>不适用</p></td>
<td align="left"><p>不适用</p></td>
<td align="left"><p>不适用</p></td>
<td align="left"><p>智能升级</p></td>
</tr>
</tbody>
</table>

 

## 支持的配置


AGPM 支持下表中的配置。 尽管 AGPM 支持混合配置，但强烈建议你在相同操作系统系列上运行 AGPM 客户端和服务器，例如，使用 windows Server 2012、windows 7 和 Windows Server 2008 R2 运行 Windows 8。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>AGPM 4.0 SP1 服务器支持的配置</strong></p></td>
<td align="left"><p><strong>AGPM 4.0 SP1 客户端支持的配置</strong></p></td>
<td align="left"><p><strong>AGPM 4.0 SP1 支持</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows 8 或 Windows Server 2012</p></td>
<td align="left"><p>Windows 8 或 Windows Server 2012</p></td>
<td align="left"><p>支持</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server 2008 R2 或 Windows 7</p></td>
<td align="left"><p>Windows Server 2008 R2 或 Windows 7</p></td>
<td align="left"><p>受支持，但不能编辑仅存在于 Windows 8 中的策略设置或首选项</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server 2008 R2 或 Windows 7 或 windows 8 或 windows Server 2012</p></td>
<td align="left"><p>Windows Server 2008 或 Windows Vista SP1</p></td>
<td align="left"><p>受支持，但不能编辑仅存在于 Windows Server 2008 R2 或 Windows 7 或 Windows 8 中的策略设置或首选项。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server 2008 或 Windows Vista SP1</p></td>
<td align="left"><p>Windows Server 2008 R2 或 Windows 7 或 windows 8 或 windows Server 2012</p></td>
<td align="left"><p>支持</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server 2008 或 Windows Vista SP1</p></td>
<td align="left"><p>Windows Server 2008 或 Windows Vista SP1</p></td>
<td align="left"><p>受支持，但无法报告或编辑仅存在于 Windows Server 2008 R2 或 Windows 7 或 Windows 8 中的策略设置或首选项</p></td>
</tr>
</tbody>
</table>

 

## 安装 AGPM 4.0 SP1 的先决条件


下表介绍了在缺少远程服务器管理工具（RSAT）中的 .NET 3.5 或组策略管理控制台时，AGPM 4.0 SP1 客户端和服务器安装程序的 Windows 8 上的行为。

**AGPM 客户端 4.0 SP1**

**AGPM 服务器 4.0 SP1**

**操作系统**

**.NET**

**RSAT**

**.NET**

**RSAT**

**Windows 8**

如果未启用或安装 .NET 3.5，安装程序将阻止安装。

如果系统上未启用或安装 GPMC，安装程序将阻止安装。

如果未启用或安装 .NET 3.5，安装程序将阻止安装。

如果系统上未启用或安装 GPMC，安装程序将阻止安装。

**Windows Server 2012**

如果未启用或安装 .NET 3.5，安装程序将阻止安装。

如果未启用 GPMC，安装程序将在安装期间启用它。

如果未启用或安装 .NET 3.5，安装程序将阻止安装。

如果未启用 GPMC，安装程序将在安装期间启用它。

 

## 相关主题


[高级组策略管理](index.md)

[Microsoft 高级组策略管理 4.0 SP1 发行说明](release-notes-for-microsoft-advanced-group-policy-management-40-sp1.md)

 

 





