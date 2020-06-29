---
title: 计划将 App-V 与 Office 结合使用
description: 计划将 App-V 与 Office 结合使用
author: dansimp
ms.assetid: c4371869-4bfc-4d13-9198-ef19f99fc192
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: ff523c8f8827e295c8fb9a2d9fd0e02d5b019aa8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798292"
---
# 计划将 App-V 与 Office 结合使用


使用以下信息规划如何使用 App-v 部署 Office。 本文包括：

-   [语言包的 app-v 支持](#bkmk-lang-pack)

-   [Microsoft Office 支持的版本](#bkmk-office-vers-supp-appv)

-   [规划将 App-v 与早期版本的 Office 配合使用](#bkmk-plan-coexisting)

-   [Office 在部署时如何与 Windows 集成使用 app-v 部署 Office](#bkmk-office-integration-win)

## <a href="" id="bkmk-lang-pack"></a>语言包的 app-v 支持


你可以使用 app-v 5.0 Sequencer 为语言包、语言界面包、校对工具和屏幕提示语言创建插件包。 然后，你可以在连接组中包含插件程序包，以及使用 Office 部署工具包创建的 Office 2013 程序包。 Office 应用程序和插件语言包在同一连接组中无缝交互，就像在连接组中组合在一起的任何其他程序包一样。

**注意** Microsoft Visio 和 Microsoft Project 不提供对泰语语言包的支持。

 

## <a href="" id="bkmk-office-vers-supp-appv"></a>Microsoft Office 支持的版本


下表列出了 App-v 支持的 Microsoft Office 版本、Office 程序包的创建方法、支持的许可以及支持的部署。

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">支持的 Office 版本</th>
<th align="left">支持的应用-V 版本</th>
<th align="left">程序包创建</th>
<th align="left">支持的许可</th>
<th align="left">支持的部署</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>适用于企业的 Microsoft 365 应用</p>
<p>还支持：</p>
<ul>
<li><p>Visio Pro for Office 365</p></li>
<li><p>Project Pro for Office 365</p></li>
</ul></td>
<td align="left"><ul>
<li><p>App-v 5。0</p></li>
<li><p>App-v 5.0 SP1</p></li>
<li><p>App-v 5.0 SP2</p></li>
</ul></td>
<td align="left"><p>Office 部署工具</p></td>
<td align="left"><p>订阅</p></td>
<td align="left"><ul>
<li><p>桌面</p></li>
<li><p>个人 VDI</p></li>
<li><p>汇集了 VDI</p></li>
<li><p>RDS</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>Office 专业增强版2013</p>
<p>还支持：</p>
<ul>
<li><p>Visio Professional 2013</p></li>
<li><p>Project Professional 2013</p></li>
</ul></td>
<td align="left"><ul>
<li><p>App-v 5。0</p></li>
<li><p>App-v 5.0 SP1</p></li>
<li><p>App-v 5.0 SP2</p></li>
</ul></td>
<td align="left"><p>Office 部署工具</p></td>
<td align="left"><p>批量许可</p></td>
<td align="left"><ul>
<li><p>桌面</p></li>
<li><p>个人 VDI</p></li>
<li><p>汇集了 VDI</p></li>
<li><p>RDS</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-plan-coexisting"></a>规划将 App-v 与早期版本的 Office 配合使用


你可以使用 "Microsoft Office 共存" 在同一台计算机上并排安装多个版本的 Microsoft Office。 你可以通过使用基于 Windows Installer （MSi）版本的 Office、即点即用和 App-v 5.0 SP2 的所有主要版本的 office 共存和安装方法来实现 Office 共存。 但是，Microsoft 不建议使用 Office 共存。

Microsoft 建议的最佳做法是完全避免 Office 共存，以防止兼容性问题。 但是，当你迁移到较新版本的 Office 时，偶尔会出现不能立即解决的问题，因此你可以临时实现共存，以便更快地迁移到最新的产品版本。 永远不建议在短期内使用 Office 共存，并且你的组织应制定一个计划，以便在将来立即完全过渡。

### 实现 Office 共存之前

在实现 Office 共存之前，请查看以下 Office 文档。 选择对应于你计划为其实施共存的最新版本的 Office 的文章。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Office 版本</th>
<th align="left">链接到指南</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Office 2013</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2784668" data-raw-source="[Information about how to use Office 2013 suites and programs (MSI deployment) on a computer that is running another version of Office](https://support.microsoft.com/kb/2784668)">有关如何在运行其他版本的 Office 的计算机上使用 Office 2013 套件和程序（MSI 部署）的信息</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>Office 2010</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2121447" data-raw-source="[Information about how to use Office 2010 suites and programs on a computer that is running another version of Office](https://support.microsoft.com/kb/2121447)">有关如何在运行其他版本的 Office 的计算机上使用 Office 2010 套件和程序的信息</a></p></td>
</tr>
</tbody>
</table>

 

Office 文档提供了有关基于 Windows Installer （MSi）的共存和 Office 的即点即用安装的详细指南。 有关共存的此 App-v 主题补充了 Office 指南，其信息更特定于 App-v 部署。

### 受支持的 Office 共存方案

下表总结了受支持的共存方案。 根据你开始的版本和部署方法以及你要迁移到的版本和部署方法对它们进行组织。 请确保在将所有共存解决方案部署到生产用户之前对其进行全面测试。

**注意** Microsoft 不支持在启用远程桌面会话主机角色服务的 Windows Server 环境中使用多个版本的 Office。 若要运行 Office 共存方案，必须禁用此角色服务。

 

### Windows 集成 & 的 Office 共存

基于 Windows 安装程序和单击到运行的 Office 安装方法与基础 Windows 操作系统的某些点集成。 使用共存时，两个 Office 版本之间的常见操作系统集成可能会发生冲突，从而导致兼容性和用户体验问题。 通过 App-v，你可以对某些版本的 Office 进行排序以排除集成，从而将其与操作系统隔离。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left">在此模式下，app-v 可以对此版本的 Office 进行排序</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Office 2007</p></td>
<td align="left"><p>始终不集成。 App-v 不会提供与虚拟化版本的 Office 2007 的任何操作系统集成。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Office 2010</p></td>
<td align="left"><p>集成模式和非集成模式。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Office 2013</p></td>
<td align="left"><p>始终集成。 无法禁用 Windows 操作系统集成。</p></td>
</tr>
</tbody>
</table>

 

Microsoft 建议你仅通过一个集成的 Office 实例部署 Office 共存。 例如，如果你使用 App-v 部署 Office 2010 和 Office 2013，则应在非集成模式下序列化 Office 2010。 有关在非集成（独立）模式下排列 Office 的详细信息，请参阅[如何在 Microsoft Application Virtualization 5.0 中对 Microsoft Office 2010](https://support.microsoft.com/kb/2830069)进行排序。

### Office 共存方案的已知限制

以下部分介绍了使用 App-v 实现与 Office 的共存时可能遇到的一些问题。

### 基于 Windows Installer/单击到运行和 App-v Office 共存方案的常见限制

在同一台计算机上安装以下版本的 Office 时，可能会出现以下限制：

-   使用基于 Windows Installer 的版本的 Office 2010

-   使用 App-v 的 Office 2013

通过将 app-v 与基于 Windows Installer 的 Office 2010 的早期版本结合使用来发布 Office 2013 后，可能还会导致 Windows 安装程序启动。 这是因为基于 Windows 安装程序或单击到运行版本的 Office 2010 试图自动注册到计算机。

若要绕过本机 Word 2010 的自动注册操作，请按照下列步骤操作：

1.  退出 Word 2010。

2.  通过执行下列操作来启动注册表编辑器：

    -   在 Windows 7 中：单击 "**开始**"，在 "开始搜索" 框中键入**regedit** ，然后按 enter。

    -   在 Windows 8 中，键入**regedit**按 "开始" 页面上的 enter，然后按 enter。

    如果系统提示您输入管理员密码或进行确认，请键入密码，或单击 "**继续**"。

3.  找到并选择下面的注册表子项：

    ``` syntax
    HKEY_CURRENT_USER\Software\Microsoft\Office\14.0\Word\Options
    ```

4.  在 "**编辑**" 菜单上，单击 "**新建**"，然后单击 " **DWORD 值**"。

5.  键入**NoReReg**，然后按 Enter。

6.  右键单击 " **NoReReg** "，然后单击 "**修改**"。

7.  在 " **Valuedata** " 框中，键入**1**，然后单击 **"确定"**。

8.  在 "文件" 菜单上，单击 "**退出**" 以关闭注册表编辑器。

## <a href="" id="bkmk-office-integration-win"></a>使用 App-v 部署 Office 时 Office 与 Windows 的集成方式


当您使用 App-v 部署 Office 2013 时，Office 将与操作系统完全集成，这将向最终用户提供与 Office 在不使用 App-v 部署时的功能和功能相同的功能和功能。

Office 2013 App-v 程序包支持 Windows 操作系统的以下集成点：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">扩展点</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>适用于 Firefox 和 Chrome 的 Lync 会议加入插件</p></td>
<td align="left"><p>用户可以从 Firefox 和 Chrome 加入 Lync 会议</p></td>
</tr>
<tr class="even">
<td align="left"><p>已发送到 OneNote 打印驱动程序</p></td>
<td align="left"><p>用户可以打印到 OneNote</p></td>
</tr>
<tr class="odd">
<td align="left"><p>OneNote 链接笔记</p></td>
<td align="left"><p>OneNote 链接笔记</p></td>
</tr>
<tr class="even">
<td align="left"><p>发送到 OneNote Internet Explorer 加载项</p></td>
<td align="left"><p>用户可以从 IE 发送到 OneNote</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Lync 和 Outlook 的防火墙例外</p></td>
<td align="left"><p>Lync 和 Outlook 的防火墙例外</p></td>
</tr>
<tr class="even">
<td align="left"><p>MAPI 客户端</p></td>
<td align="left"><p>本机应用和外接程序可以通过 MAPI 与虚拟 Outlook 进行交互</p></td>
</tr>
<tr class="odd">
<td align="left"><p>用于 Firefox 的 SharePoint 插件</p></td>
<td align="left"><p>用户可以使用 Firefox 中的 SharePoint 功能</p></td>
</tr>
<tr class="even">
<td align="left"><p>"邮件控制面板" 小程序</p></td>
<td align="left"><p>用户在 Outlook 中获取 "邮件" 控制面板小程序</p></td>
</tr>
<tr class="odd">
<td align="left"><p>主互操作程序集</p></td>
<td align="left"><p>支持托管加载项</p></td>
</tr>
<tr class="even">
<td align="left"><p>Office 文档缓存处理程序</p></td>
<td align="left"><p>允许 Office 应用程序的文档缓存</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Outlook 协议搜索处理程序</p></td>
<td align="left"><p>用户可以在 outlook 中搜索</p></td>
</tr>
<tr class="even">
<td align="left"><p>活动 X 控件：</p></td>
<td align="left"><p>有关 ActiveX 控件的详细信息，请参阅 <a href="https://go.microsoft.com/fwlink/p/?LinkId=331361" data-raw-source="[ActiveX Control API Reference](https://go.microsoft.com/fwlink/p/?LinkId=331361)"> Activex 控件 API 参考 </a> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>   Groove。 SiteClient</p></td>
<td align="left"><p>活动 X 控件</p></td>
</tr>
<tr class="even">
<td align="left"><p>   PortalConnect.PersonalSite</p></td>
<td align="left"><p>活动 X 控件</p></td>
</tr>
<tr class="odd">
<td align="left"><p>   OpenDocuments</p></td>
<td align="left"><p>活动 X 控件</p></td>
</tr>
<tr class="even">
<td align="left"><p>   ExportDatabase</p></td>
<td align="left"><p>活动 X 控件</p></td>
</tr>
<tr class="odd">
<td align="left"><p>   SpreadSheetLauncher</p></td>
<td align="left"><p>活动 X 控件</p></td>
</tr>
<tr class="even">
<td align="left"><p>   StssyncHander</p></td>
<td align="left"><p>活动 X 控件</p></td>
</tr>
<tr class="odd">
<td align="left"><p>   DragUploadCtl</p></td>
<td align="left"><p>活动 X 控件</p></td>
</tr>
<tr class="even">
<td align="left"><p>   DragDownloadCtl</p></td>
<td align="left"><p>活动 X 控件</p></td>
</tr>
<tr class="odd">
<td align="left"><p>   OpenXMLDocuments</p></td>
<td align="left"><p>活动 X 控件</p></td>
</tr>
<tr class="even">
<td align="left"><p>   ClipboardCtl</p></td>
<td align="left"><p>活动 X 控件</p></td>
</tr>
<tr class="odd">
<td align="left"><p>   WinProj</p></td>
<td align="left"><p>活动 X 控件</p></td>
</tr>
<tr class="even">
<td align="left"><p>   NameCtrl</p></td>
<td align="left"><p>活动 X 控件</p></td>
</tr>
<tr class="odd">
<td align="left"><p>   STSUPld.CopyCtl</p></td>
<td align="left"><p>活动 X 控件</p></td>
</tr>
<tr class="even">
<td align="left"><p>   CommunicatorMeetingJoinAx.JoinManager</p></td>
<td align="left"><p>活动 X 控件</p></td>
</tr>
<tr class="odd">
<td align="left"><p>   LISTNET.Listnet</p></td>
<td align="left"><p>活动 X 控件</p></td>
</tr>
<tr class="even">
<td align="left"><p>   OneDrive Pro 浏览器帮助程序</p></td>
<td align="left"><p>活动 X 控件]</p></td>
</tr>
<tr class="odd">
<td align="left"><p>OneDrive Pro 图标覆盖</p></td>
<td align="left"><p>当用户查看文件夹 OneDrive Pro 文件夹时，Windows 资源管理器 shell 图标重叠</p></td>
</tr>
<tr class="even">
<td align="left"><p>Shell 扩展</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>指向</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows 搜索</p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>

 






 

 





