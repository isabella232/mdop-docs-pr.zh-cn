---
title: 将 Office 2013 与 UE-V 2.0 同步
description: 将 Office 2013 与 UE-V 2.0 同步
author: dansimp
ms.assetid: c46feb6d-28a8-4799-888d-053531dc5842
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: c9b079d3f21e6ced689fa2101f5321fa9b1406c8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804058"
---
# 将 Office 2013 与 UE-V 2.0 同步


Microsoft 用户体验虚拟化（UE-V）2.0 支持使用 UE-V 模板库中提供的模板同步 Microsoft Office 2013 应用程序设置。 UE-V 2 和 App-v 5.0 SP2 支持 Office 2013 专业增强版在 Office 2013 的虚拟化实例（任何支持 UE-V 的设备或虚拟化桌面）上的体验同样有效。

若要激活 Office 2013 的 UE-V 应用程序设置支持，可以从[Microsoft 用户体验虚拟化（ue-v）2模板库](https://go.microsoft.com/fwlink/p/?LinkId=246589)下载官方 ue-v Office 2013 模板。 此资源提供 Microsoft 创作的 UE-V 设置位置模板以及社区开发的设置位置模板。

## UE-V 中的 Microsoft Office 支持


UE-V 1.0 和 UE-V 2 包括 Microsoft Office 2010 的设置位置模板。 这些模板作为 UE-V Agent 安装过程的一部分进行分发和注册。 这些模板有助于在设备之间同步用户的 Office 体验。 Office 2013 的 UE-V 模板为 Office 2010 的模板提供了非常类似的设置体验。 在这些设置中不包含通过 Office 365 体验漫游的 Microsoft Office 2013 设置。 有关 Office 365 特定设置的列表，请参阅[office 2013 的用户和漫游设置概述](https://go.microsoft.com/fwlink/p/?LinkId=391220)。

## 同步的 Office 2013 设置


下表包含 UE-V 中的 Office 2013 支持的详细信息：

### Microsoft Office 支持的 UE-V 模板

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Office 2013 模板（UE-V 2.0，可在 UE-V 库上使用）：</th>
<th align="left">Office 2010 模板（UE-V 1.0 &amp; 1.0 SP1）：</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>MicrosoftOffice2013Win32.xml</p>
<p>MicrosoftOffice2013Win64.xml</p>
<p>MicrosoftLync2013Win32.xml</p>
<p>MicrosoftLync2013Win64.xml</p></td>
<td align="left"><p>MicrosoftOffice2010Win32.xml</p>
<p>MicrosoftOffice2010Win64.xml</p>
<p>MicrosoftLync2010.xml</p>
<p></p></td>
</tr>
</tbody>
</table>

 

### 由 UE-V 模板支持的 Microsoft Office 应用程序

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p>Microsoft Access 2013</p>
<p>Microsoft Lync 2013</p>
<p>Microsoft Excel 2013</p>
<p>Microsoft InfoPath 2013</p>
<p>Microsoft OneNote 2013</p>
<p>Microsoft Outlook 2013</p>
<p>Microsoft PowerPoint 2013</p>
<p>Microsoft Project 2013</p>
<p>Microsoft Publisher 2013</p>
<p>Microsoft SharePoint Designer 2013</p>
<p>Microsoft Visio 2013</p>
<p>Microsoft Word 2013</p>
<p>Microsoft Office 上载管理器</p></td>
<td align="left"><p>Microsoft Access 2010</p>
<p>Microsoft Lync 2010</p>
<p>Microsoft Excel 2010</p>
<p>Microsoft InfoPath 2010</p>
<p>Microsoft OneNote 2010</p>
<p>Microsoft Outlook 2010</p>
<p>Microsoft PowerPoint 2010</p>
<p>Microsoft Project 2010</p>
<p>Microsoft Publisher 2010</p>
<p>Microsoft SharePoint Designer 2010</p>
<p>Microsoft Visio 2010</p>
<p>Microsoft Word 2010</p>
<p></p></td>
</tr>
</tbody>
</table>

 

## 部署 Office 2013 模板


你可以通过以下方法部署 UE-V 设置位置模板：

-   **通过 PowerShell 注册模板**。 如果你使用 Windows PowerShell 来管理计算机，请运行以下 Windows PowerShell 命令以管理员身份打开以注册此设置位置模板：

    ``` syntax
    Register-UevTemplate -Path <Path_to_Template>
    ```

    有关使用 UE-V 和 Windows PowerShell 的详细信息，请参阅[使用 Windows PowerShell 和 WMI 管理 ue-v 2. x 设置位置模板](managing-ue-v-2x-settings-location-templates-using-windows-powershell-and-wmi-both-uevv2.md)。

-   **通过模板目录路径注册模板**。 如果使用设置模板目录路径来管理用户计算机上的模板，请将 Office 2013 模板复制到 UE-V Agent 中定义的文件夹中。 下次模板自动更新（ApplySettingsCatalog.exe）计划任务运行时，将在设备上注册设置位置模板。 有关详细信息，请参阅为[ue-v 2 部署设置模板目录](https://technet.microsoft.com/library/dn458942.aspx#deploycatalogue)。

-   **通过 Configuration Manager 注册模板**。 如果你使用 Configuration Manager 管理 UE-V 设置存储模板，请重新创建模板基线 CAB，然后将其导入配置管理器，然后将基线部署到你的客户端。 有关详细信息，请参阅[适用于 Microsoft 用户体验虚拟化2的 System Center 2012 配置包](https://go.microsoft.com/fwlink/?LinkId=317263)的文档中提供的指南。






 

 





