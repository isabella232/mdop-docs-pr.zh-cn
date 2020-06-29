---
title: 规划要使用 UE-V 1.0 同步的应用程序
description: 规划要使用 UE-V 1.0 同步的应用程序
author: dansimp
ms.assetid: c718274f-87b4-47f3-8ef7-5e1bd5557a9d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7f2b04942588d0f6efad03d5e0249534cd325c09
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798040"
---
# 规划要使用 UE-V 1.0 同步的应用程序


Microsoft 用户体验虚拟化（UE-V）使用设置位置模板（XML 文件），这些模板定义由 UE-V 捕获和应用的设置。 UE-V 包含一组预定义的设置位置模板，还允许管理员为企业中使用的第三方或业务线应用程序创建自定义设置位置模板。

作为管理员，当你考虑要包含在 UE-V 解决方案中的应用程序时，请考虑哪些设置可以由用户自定义，以及应用程序存储其设置的方式和位置。 并非所有应用程序都具有可自定义或经常由用户自定义的设置。 此外，并非所有应用程序设置都可以在多台计算机或环境中安全地漫游。 同步满足以下条件的设置：

-   存储在用户易于访问的位置的设置。 例如，不要同步在 system32 或注册表外部 HKCU 部分中存储的设置。

-   不特定于特定计算机的设置。 例如，排除网络或硬件配置。

-   可以在计算机之间同步的设置，而不会损坏数据。 例如，不要使用存储在数据库文件中的设置。

## UE-V 中包含的设置位置模板


**UE-V 应用程序设置位置模板**

UE-V agent 安装软件安装代理并为常见的 Microsoft 应用程序注册一个默认设置位置模板组。 这些设置位置模板捕获以下应用程序的设置值：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong>应用程序类别</strong></th>
<th align="left"><strong>描述</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Microsoft Office 2010 应用程序</p></td>
<td align="left"><p>Microsoft Word 2010</p>
<p>Microsoft Excel 2010</p>
<p>Microsoft Outlook 2010</p>
<p>Microsoft Access 2010</p>
<p>Microsoft Project 2010</p>
<p>Microsoft PowerPoint 2010</p>
<p>Microsoft Publisher 2010</p>
<p>Microsoft Visio 2010</p>
<p>Microsoft SharePoint Workspace 2010</p>
<p>Microsoft InfoPath 2010</p>
<p>Microsoft Lync 2010</p>
<p>Microsoft OneNote 2010</p></td>
</tr>
<tr class="even">
<td align="left"><p>浏览器选项（Internet Explorer 8、Internet Explorer 9 和 Internet Explorer 10）</p></td>
<td align="left"><p>"收藏夹"、"主页"、"选项卡" 和 "工具栏"。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows 附件</p></td>
<td align="left"><p>计算器、记事本和写字板。</p></td>
</tr>
</tbody>
</table>

 

当应用程序启动时，应用程序设置应用于应用程序。 当应用程序关闭时，将保存这些文件。

**UE-V Windows 设置位置模板**

用户体验虚拟化包括设置位置模板，这些模板可捕获以下 Windows 设置的设置值：

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Windows 设置</th>
<th align="left">描述</th>
<th align="left">适用于</th>
<th align="left">默认状态</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>桌面背景</p></td>
<td align="left"><p>当前处于活动状态的桌面背景。</p></td>
<td align="left"><p>登录、解锁、远程连接。</p></td>
<td align="left"><p>启用</p></td>
</tr>
<tr class="even">
<td align="left"><p>轻松使用</p></td>
<td align="left"><p>辅助功能和输入设置、放大镜、讲述人和屏幕键盘。</p></td>
<td align="left"><p>登录、解锁、远程连接。</p></td>
<td align="left"><p>禁用</p></td>
</tr>
<tr class="odd">
<td align="left"><p>桌面设置</p></td>
<td align="left"><p>"开始" 菜单和任务栏设置、文件夹选项、默认桌面图标、附加时钟以及区域和语言设置。</p></td>
<td align="left"><p>仅登录。</p></td>
<td align="left"><p>禁用</p></td>
</tr>
</tbody>
</table>

 

当用户登录、计算机解锁或远程连接到另一台计算机时，将应用 Windows 桌面背景和 "轻松访问" 设置。 当用户注销、计算机锁定或远程连接断开时，代理会保存这些设置。 默认情况下，Windows 桌面背景设置是在同一操作系统版本的计算机之间漫游。

在登录之前，Windows 桌面和 "轻松访问" 设置将在桌面登录到用户之前应用。 为优化登录体验，默认情况下，这些设置不是漫游。 可以使用组策略、PowerShell 和 WMI 启用桌面和轻松访问设置。

UE-V 不支持漫游不同语言的操作系统之间的设置。 例如，不支持英语和德语之间的同步。 UE-V 漫游的所有计算机的语言用户设置必须匹配。

**注意** 如果你更改由 Microsoft 提供的设置位置模板，则对于指定的应用程序或 Windows 设置组，用户体验虚拟化可能无法正常工作。

 

## <a href="" id="prevent-unintentional-user-settings-configuration-"></a>防止无意间的用户设置配置


用户体验虚拟化检查新用户设置信息，并从设置存储位置下载相应信息。 然后，在以下情况下，它会将设置应用于本地计算机：

-   每次启动具有注册的 UE-V 模板的应用程序时。

-   当用户登录到其计算机时。

-   用户解锁计算机时。

-   连接到安装了 UE-V 的远程桌面计算机时。

如果 UE-V 安装在计算机 A 和计算机 B 上，并且应用程序的所需设置位于计算机 A 上，则计算机 A 必须首先打开并关闭该应用程序。 如果首先在计算机 B 上打开和关闭应用程序，则计算机 A 上的应用程序设置将配置为与计算机 B 上的应用程序设置相同。

此方案也适用于 Windows 设置。 如果计算机 B 上的 Windows 设置应该与计算机 A 上的 Windows 设置相同，则用户应首先登录和注销计算机 A。

如果所需的用户设置按错误的顺序应用，则可以通过针对覆盖了这些设置的计算机上的特定应用程序或 Windows 配置执行还原操作来恢复它们。 有关详细信息，请参阅[还原与 ue-v 1.0 同步的应用程序和 Windows 设置](restoring-application-and-windows-settings-synchronized-with-ue-v-10.md)。

## 自定义 UE-V 设置位置模板


可以使用 UE-V 生成器创建自定义设置位置模板。 在测试环境中创建和测试自定义设置位置模板后，可以将设置位置模板部署到企业中的计算机。 自定义设置位置模板必须使用现有部署基础结构（如企业软件分发（ESD）方法）和首选项进行部署，或者配置 UE-V 设置模板目录。 必须使用 UE-V WMI 或 PowerShell 注册使用 ESD 或组策略部署的模板。 有关自定义设置位置模板的详细信息，请参阅[规划 ue-v 1.0 的自定义模板部署](planning-for-custom-template-deployment-for-ue-v-10.md)。

有关是否应同步业务线应用程序的指导，请参阅[评估 ue-v 1.0 的业务线应用程序的清单](checklist-for-evaluating-line-of-business-applications-for-ue-v-10.md)。

## 相关主题


[规划 UE-V 1.0](planning-for-ue-v-10.md)

[规划 UE-V 1.0 的自定义模板部署](planning-for-custom-template-deployment-for-ue-v-10.md)

[部署 UE-V 1.0](deploying-ue-v-10.md)

 

 





