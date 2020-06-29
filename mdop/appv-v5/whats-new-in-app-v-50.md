---
title: App-V 5.0 中的新增功能
description: App-V 5.0 中的新增功能
author: dansimp
ms.assetid: 79ff6e02-e926-4803-87d8-248a6b28099d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: dabe264f033bd5c9897f07d931f799a42e6b72e9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798241"
---
# App-V 5.0 中的新增功能


本部分适用于已熟悉 app-v 的用户，想要了解在 app-v 5.0 中更改的内容（如果你还不熟悉 App-v），应首先阅读 " [app-v 5.0 规划](planning-for-app-v-50-rc.md)"。

## 标准功能的更改


以下各节包含有关 App-v 5.0 的标准功能更改的信息。

### 对支持的操作系统的更改

有关详细信息，请参阅[App-V 5.0 支持的配置](app-v-50-supported-configurations.md)。

## 对 sequencer 的更改


以下各节包含有关 app-v 5.0 sequencer 中的更改的信息。

### 对排序器的特定更改

下表显示了有关应用 V 5.0 sequencer 的更改信息

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Sequencer 功能</th>
<th align="left">App-v 5.0 Sequencer 功能</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>重启处理</p></td>
<td align="left"><p>当应用程序提示重新启动时，你应该允许应用程序重新启动运行 sequencer 的计算机。 运行 sequencer 的计算机将重新启动，并且 sequencer 将在监视模式下继续。</p></td>
</tr>
<tr class="even">
<td align="left"><p>指定虚拟应用程序目录</p></td>
<td align="left"><p>虚拟应用程序目录是必需的参数。 为了获得最佳结果，它应与应用程序安装程序的安装目录相匹配。 这将导致更最佳的性能和应用程序兼容性。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>编辑快捷方式/FTAs</p></td>
<td align="left"><p>在 <strong> 排序向导完成后，"快捷方式/FTA" 页面位于 "高级 </strong> 编辑" 页面上。</p></td>
</tr>
<tr class="even">
<td align="left"><p>“更改历史记录”选项卡</p></td>
<td align="left"><p>已删除 app-v 5.0 的 "更改历史记录" 选项卡。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>“OSD”选项卡</p></td>
<td align="left"><p>已删除 app-v 5.0 的 OSD 选项卡。</p></td>
</tr>
<tr class="even">
<td align="left"><p>“虚拟服务”选项卡</p></td>
<td align="left"><p>已删除 app-v 5.0 的 "虚拟服务" 选项卡。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>"文件/虚拟文件系统" 选项卡</p></td>
<td align="left"><p>组合这些选项卡，并允许您修改软件包文件。</p></td>
</tr>
<tr class="even">
<td align="left"><p>“部署”选项卡</p></td>
<td align="left"><p>没有更长的选项可用于在程序包中配置服务器 URL。 你应该立即使用部署配置或管理服务器对此进行配置。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>程序包转换器工具</p></td>
<td align="left"><p>现在，你可以使用 PowerShell 转换在早期版本中创建的程序包。</p></td>
</tr>
<tr class="even">
<td align="left"><p>加载项/中间件</p></td>
<td align="left"><p>在对加载项或中间件应用程序进行排序时，可以展开父包。 加载项和中间件程序包必须使用 App-v 5.0 中的连接组进行连接。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>文件输出</p></td>
<td align="left"><p>以下文件是使用 app-v 5.0、Windows Installer （.msi）、appv、部署配置、用户配置和 Report.XML 创建的。</p></td>
</tr>
<tr class="even">
<td align="left"><p>压缩/安全描述符/MSI 程序包</p></td>
<td align="left"><p>压缩和创建 Windows Installer （.msi）文件对所有程序包都是自动的，不能再替代安全描述符。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>工具/选项</p></td>
<td align="left"><p>"诊断" 窗口已删除，还有其他一些设置。</p></td>
</tr>
<tr class="even">
<td align="left"><p>安装驱动器</p></td>
<td align="left"><p>安装应用程序时，不再需要安装驱动器。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>OOS 流</p></td>
<td align="left"><p>如果未执行任何流优化，则当运行 App-v 5.0 客户端的计算机请求程序包，直到它们启动时，程序包才会出现流错误。</p></td>
</tr>
<tr class="even">
<td align="left"><p>问： &lt; /p&gt;</td>
<td align="left"><p>App-v 5.0 使用本机文件系统，不再需要 Q:。</p></td>
</tr>
</tbody>
</table>

 

## 序列错误检测


App-v 5.0 sequencer 可检测排序期间的常见排序问题。 排序向导结束时的 "**安装报告**" 页面显示根据问题的严重程度，归类为**错误**、**警告**和**信息**的诊断消息。

若要显示有关事件的更多详细信息，请双击要在报表中查看的项目。 将显示排序问题以及有关如何解决这些问题的建议。 创建程序包后，将汇总系统准备报告和安装报告中的信息。 以下列表显示了报告中可用的问题类型：

-   排除的文件。

-   驱动程序信息。

-   COM + 系统差异。

-   并行（SxS）冲突。

-   外壳扩展。

-   有关不支持的服务的信息。

-   DCOM.

## 连接组


以前称为 "**动态套件合成**" 的 app-v 功能现在称为 "app-v 5.0 中的**连接组**"。 有关使用连接组的详细信息，请参阅[管理连接组](managing-connection-groups.md)。

## 许可和测定功能


应用程序和许可功能已在 App-v 5.0 中删除。 环境中的实际许可证位置取决于相关联的许可条款所授予的特定软件标题许可证和使用权利。

## 文件和应用程序缓存


App-v 5.0 没有可用的文件或应用程序缓存。






## 相关主题


[关于 App-V 5.0](about-app-v-50.md)

 

 





