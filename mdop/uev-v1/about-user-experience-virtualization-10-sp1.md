---
title: 关于用户体验虚拟化 1.0 SP1
description: 关于用户体验虚拟化 1.0 SP1
author: dansimp
ms.assetid: 0212d3fb-e882-476c-9496-9eb52301703d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8a480ac5d4f4083fc15a724b7cc79390b0caef14
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804059"
---
# 关于用户体验虚拟化 1.0 SP1


Microsoft 用户体验虚拟化（UE-V） 1.0 Service Pack 1 将版本从1.0.414 更改为1.0.520。 当 UE-V Agent setup.exe 或 UE-V 发生器 setup.exe 启动时，它将检测是否需要升级，并将升级 UE-V Agent 或发电机。

## 现在支持其他语言


UE-V 1.0 Service Pack 1 提供支持其他语言的 UE-V Agent 和 UE-V 发电机的更新。 运行安装程序时，将安装所有支持的语言。 UE-V 1 SP1 中包含以下语言：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">UE-V Agent</th>
<th align="left">UE-V 发电机</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><ul>
<li><p>简体中文（PRC） zh-cn&platform-CN</p></li>
</ul>
<ul>
<li><p>繁体中文-台湾 zh-cn&platform</p></li>
</ul>
<ul>
<li><p>捷克语（捷克共和国） cs-CZ</p></li>
</ul>
<ul>
<li><p>丹麦语（丹麦） da-深色</p></li>
</ul>
<ul>
<li><p>荷兰语（荷兰） nl-NL</p></li>
</ul>
<ul>
<li><p>芬兰语（芬兰） wlan</p></li>
</ul>
<ul>
<li><p>法语（法国） fr-fr</p></li>
</ul>
<ul>
<li><p>德语（德国） de</p></li>
</ul>
<ul>
<li><p>希腊语（希腊） el-GR</p></li>
</ul>
<ul>
<li><p>匈牙利语（匈牙利） hu-HU</p></li>
</ul>
<ul>
<li><p>意大利语（意大利） it</p></li>
</ul>
<ul>
<li><p>日语（日本） ja-jp</p></li>
</ul>
<ul>
<li><p>朝鲜语（韩国） ko-KR</p></li>
</ul>
<ul>
<li><p>挪威语（挪威博克马尔语） nb</p></li>
</ul>
<ul>
<li><p>波兰语（波兰） pl-PL</p></li>
</ul>
<ul>
<li><p>葡萄牙语（巴西） pt-BR</p></li>
</ul>
<ul>
<li><p>葡萄牙语（葡萄牙） pt</p></li>
</ul>
<ul>
<li><p>俄语（俄罗斯） ru-RU</p></li>
</ul>
<ul>
<li><p>斯洛伐克语（斯洛伐克） sk-SK</p></li>
</ul>
<ul>
<li><p>斯洛文尼亚语（斯洛文尼亚） sl-SL</p></li>
</ul>
<ul>
<li><p>西班牙语、国际排序（西班牙） es</p></li>
</ul>
<ul>
<li><p>瑞典语（瑞典） sv-SE</p></li>
</ul>
<ul>
<li><p>土耳其语（土耳其） tr-TR</p></li>
</ul>
<p></p></td>
<td align="left"><ul>
<li><p>简体中文（PRC） zh-cn&platform-CN</p></li>
</ul>
<ul>
<li><p>繁体中文-台湾 zh-cn&platform</p></li>
</ul>
<ul>
<li><p>法语（法国） fr-fr</p></li>
</ul>
<ul>
<li><p>德语（德国） de</p></li>
</ul>
<ul>
<li><p>意大利语（意大利） it</p></li>
</ul>
<ul>
<li><p>日语（日本） ja-jp</p></li>
</ul>
<ul>
<li><p>朝鲜语（韩国） ko-KR</p></li>
</ul>
<ul>
<li><p>葡萄牙语（巴西） pt-BR</p></li>
</ul>
<ul>
<li><p>俄语（俄罗斯） ru-RU</p></li>
</ul>
<ul>
<li><p>西班牙语、国际排序（西班牙） es</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

**重要提示** 虽然 UE-V Agent 安装程序（AgentSetup.exe）和 UE-V 发生器安装程序（ToolSetup.exe）被翻译为上述语言，但 Windows Installer （.msi）文件仅提供英文版本。

 

## Office 2007 设置位置模板


UE-V Agent 安装软件安装代理并为常见的 Microsoft 应用程序注册一个默认设置位置模板组。 Microsoft Office 2007 现在是这些应用程序的一部分。 有两个 Office 2007 模板： "MicrosoftOffice2007.xml" 和 "MicrosoftCommunicator2007.xml"。 这些设置位置模板将在 Microsoft Office 2007 中捕获以下应用程序的设置：

-   Microsoft Access 2007

-   Microsoft Communicator 2007

-   Microsoft Excel 2007

-   Microsoft InfoPath 2007

-   Microsoft OneNote 2007

-   Microsoft Outlook 2007

-   Microsoft PowerPoint 2007

-   Microsoft Project 2007

-   Microsoft Publisher 2007

-   Microsoft SharePoint Designer 2007

-   Microsoft Visio 2007

-   Microsoft Word 2007

### Office 2010 设置位置模板更新

还对设置位置模板进行了更新。 这些更改包括：

-   添加了对 Microsoft SharePoint Designer 2010 的支持，方法是将新模板添加到 Office 2010 模板（MicrosoftOffice2010Win32.xml 和 MicrosoftOffice2010Win64.xml）

-   小 bug 修复，包括自定义状态栏-Word、Excel 和 PowerPoint

## 用于目录更新的计划任务现在是随机的


模板自动更新任务检查设置模板目录中是否有新的、已更新或已删除的模板。 仅当配置了 SettingsTemplateCatalog 时，此任务才会运行。 模板自动更新任务运行 ApplySettingsCatalog.exe 文件，该文件位于 UE-V Agent 安装目录中，而 UE-V SP1 已更改为一小时内随机更新。

## Citrix EdgeSight 支持


使用 Citrix EdgeSight 在服务器上运行的 UE-V 发现冲突。 UE-V 1.0 SP1 可解决此问题。

## Internet Explorer 收藏夹的索引


当 UE-V 将 Internet Explorer 收藏夹从一台计算机漫游到另一台计算机时，同步计算机上地址栏中的收藏地址的索引现在已更新。 当用户在地址栏中键入内容时，漫游收藏夹现在在同步的计算机上显示为可用的搜索结果。

## 用于 UE-V Agent 和 UE-V 发生器的新 setup.exe 命令行参数


使用 UE-V 1.0 SP1 的发布，UE-V Agent 和 UE-V 发电机的 setup.exe 都已更新，以允许使用以下附加命令行参数：

1.  `CEIPENABLED` -允许安装程序接受 "Microsoft 客户体验改善计划" 中包含的选项。

2.  `INSTALLFOLDER` -允许为代理或生成器设置不同的安装文件夹。

3.  `MUENABLED` -允许安装程序接受 "Microsoft 更新" 程序中包含的选项。

## 设置的新错误代码


当运行 UE-V Agent （AgentSetup.exe）的 UE-V 安装程序时，可以在安装日志 "/loglog.txt中查看以下返回代码 &lt; &gt; 。"

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p>0</p></td>
<td align="left"><p>安装程序已成功完成。</p></td>
</tr>
<tr class="even">
<td align="left"><p>ppls-2</p></td>
<td align="left"><p>尝试卸载时使用的是较旧版本的 UE-V。 若要卸载 UE-V，请使用与用于安装的 ue-v 版本相同的 ue-v。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>三维空间</p></td>
<td align="left"><p>已使用新版本的 UE-V 进行卸载。 若要卸载 UE-V，请使用与用于安装的 ue-v 版本相同的 ue-v。</p></td>
</tr>
<tr class="even">
<td align="left"><p>第</p></td>
<td align="left"><p>安装程序中出现意外错误。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>级</p></td>
<td align="left"><p>UE-V 的完整版本无法安装在试用版（评估）版本的顶部。 请卸载试用版，然后重试。</p></td>
</tr>
<tr class="even">
<td align="left"><p>型</p></td>
<td align="left"><p>安装过程中出现意外错误。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>7</p></td>
<td align="left"><p>在 Windows 7 或 Windows Server2008 R2 计算机上找不到 .NET 3.5 Framework。</p></td>
</tr>
<tr class="even">
<td align="left"><p>个</p></td>
<td align="left"><p>"脱机文件" 功能未启用。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>db-9</p></td>
<td align="left"><p>UE-V 安装程序无法确定是否已安装 UE-V 或安装文件中存在错误。</p></td>
</tr>
</tbody>
</table>

 

 

 





