---
title: 使用 App-V 部署 Microsoft Office 2010
description: 使用 App-V 部署 Microsoft Office 2010
author: dansimp
ms.assetid: ae0b0459-c0d6-4946-b62d-ff153f52d1fb
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 90454373e9a1c894eba8cbf1b8642656b986bc94
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798592"
---
# 使用 App-V 部署 Microsoft Office 2010


你可以使用以下方法之一为 Microsoft Application Virtualization （app-v）5.1 创建 Office 2010 程序包：

-   应用程序虚拟化（App-v） Sequencer

-   应用程序虚拟化（App-v）程序包加速器

## Office 2010 的 app-v 支持


下表显示了应用程序-V 版本、Office 程序包的创建方法、支持的许可以及 Office 2010 支持的部署。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">支持的项目</th>
<th align="left">支持级别</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>支持的应用-V 版本</p></td>
<td align="left"><ul>
<li><p>4.6</p></li>
<li><p>5.0</p></li>
<li><p>5.1</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>程序包创建</p></td>
<td align="left"><ul>
<li><p>引出</p></li>
<li><p>程序包加速器</p></li>
<li><p>Office 部署工具包</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>支持的许可</p></td>
<td align="left"><p>批量许可</p></td>
</tr>
<tr class="even">
<td align="left"><p>支持的部署</p></td>
<td align="left"><ul>
<li><p>桌面</p></li>
<li><p>个人 VDI</p></li>
<li><p>RDS</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

## 使用 sequencer 创建 Office 2010 App-V 5。1


对 Office 2010 进行排序是在 App-v 5.1 上创建 Office 2010 程序包的主要方法之一。 Microsoft 已通过知识文库文章提供了详细的食谱。 若要在 App-V 5.1 上创建 Office 2010 程序包，请参阅以下链接获取详细说明：

[如何在 Microsoft Application Virtualization 5.0 中对 Microsoft Office 2010 进行排序](https://go.microsoft.com/fwlink/p/?LinkId=330676)

## 使用包加速器创建 Office 2010 App-v 5.1 程序包


Office 2010 App-V 5.1 程序包可以通过程序包加速器创建。 Microsoft 提供了用于在 Windows 10、Windows 8 和 Windows 7 上创建 Office 2010 的程序包加速器。 若要使用程序包加速器在 App-v 上创建 Office 2010 程序包，请参阅以下页面以访问相应的程序包加速器：

-   [适用于 Office Professional Plus 2010 的 app-v 5.0 程序包加速器-Windows 8](https://go.microsoft.com/fwlink/p/?LinkId=330677)

-   [适用于 Office Professional Plus 2010 的 app-v 5.0 程序包加速器– Windows 7](https://go.microsoft.com/fwlink/p/?LinkId=330678)

有关如何使用 App-v 程序包加速器创建虚拟应用程序包的详细说明，请参阅[如何使用 App-v 包加速器创建虚拟应用程序包](how-to-create-a-virtual-application-package-using-an-app-v-package-accelerator51.md)。

## 部署 app-v 5.1 的 Microsoft Office 程序包


你可以使用以下任何应用程序 V 部署方法部署 Office 2010 程序包：

-   System Center Configuration Manager

-   App-v 服务器

-   通过 PowerShell 命令独立运行

## Office App-V 程序包管理和自定义


通过已知的程序包管理机制，可以像管理任何其他 App-v 5.1 程序包一样管理 Office 2010 程序包。 例如，不需要特殊说明来添加、发布、取消发布或删除 Office 程序包。

## Microsoft Office 与 Windows 集成


下表提供了 Office 2010 受支持的集成点的完整列表。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">扩展点</th>
<th align="left">描述</th>
<th align="left">Office 2010</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>适用于 Firefox 和 Chrome 的 Lync 会议加入插件</p></td>
<td align="left"><p>用户可以从 Firefox 和 Chrome 加入 Lync 会议</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>已发送到 OneNote 打印驱动程序</p></td>
<td align="left"><p>用户可以打印到 OneNote</p></td>
<td align="left"><p>是</p></td>
</tr>
<tr class="odd">
<td align="left"><p>OneNote 链接笔记</p></td>
<td align="left"><p>OneNote 链接笔记</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>发送到 OneNote Internet Explorer 加载项</p></td>
<td align="left"><p>用户可以从 IE 发送到 OneNote</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>Lync 和 Outlook 的防火墙例外</p></td>
<td align="left"><p>Lync 和 Outlook 的防火墙例外</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>MAPI 客户端</p></td>
<td align="left"><p>本机应用和外接程序可以通过 MAPI 与虚拟 Outlook 进行交互</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>适用于 Firefox 的 SharePoint 插件</p></td>
<td align="left"><p>用户可以使用 Firefox 中的 SharePoint 功能</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>"邮件控制面板" 小程序</p></td>
<td align="left"><p>用户在 Outlook 中获取 "邮件" 控制面板小程序</p></td>
<td align="left"><p>是</p></td>
</tr>
<tr class="odd">
<td align="left"><p>主互操作程序集</p></td>
<td align="left"><p>支持托管加载项</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>Office 文档缓存处理程序</p></td>
<td align="left"><p>允许 Office 应用程序的文档缓存</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>Outlook 协议搜索处理程序</p></td>
<td align="left"><p>用户可以在 outlook 中搜索</p></td>
<td align="left"><p>是</p></td>
</tr>
<tr class="even">
<td align="left"><p>活动 X 控件：</p></td>
<td align="left"><p>有关 ActiveX 控件的详细信息，请参阅 <a href="https://go.microsoft.com/fwlink/p/?LinkId=331361" data-raw-source="[ActiveX Control API Reference](https://go.microsoft.com/fwlink/p/?LinkId=331361)"> Activex 控件 API 参考 </a> 。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   Groove。 SiteClient</p></td>
<td align="left"><p>活动 X 控件</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>   PortalConnect.PersonalSite</p></td>
<td align="left"><p>活动 X 控件</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   OpenDocuments</p></td>
<td align="left"><p>活动 X 控件</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>   ExportDatabase</p></td>
<td align="left"><p>活动 X 控件</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   SpreadSheetLauncher</p></td>
<td align="left"><p>活动 X 控件</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>   StssyncHander</p></td>
<td align="left"><p>活动 X 控件</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   DragUploadCtl</p></td>
<td align="left"><p>活动 X 控件</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>   DragDownloadCtl</p></td>
<td align="left"><p>活动 X 控件</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   Sharpoint.OpenXMLDocuments</p></td>
<td align="left"><p>活动 X 控件</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>   ClipboardCtl</p></td>
<td align="left"><p>活动 X 控件</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   WinProj</p></td>
<td align="left"><p>活动 X 控件</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>   NameCtrl</p></td>
<td align="left"><p>活动 X 控件</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   STSUPld.CopyCtl</p></td>
<td align="left"><p>活动 X 控件</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>   CommunicatorMeetingJoinAx.JoinManager</p></td>
<td align="left"><p>活动 X 控件</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   LISTNET.Listnet</p></td>
<td align="left"><p>活动 X 控件</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>   OneDrive Pro 浏览器帮助程序</p></td>
<td align="left"><p>活动 X 控件]</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>OneDrive Pro 图标覆盖</p></td>
<td align="left"><p>当用户查看文件夹 OneDrive Pro 文件夹时，Windows 资源管理器 shell 图标重叠</p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>

 

## 其他资源


**Office 2013 App-v 程序包其他资源**

[将 Microsoft Office 部署为顺序式 App-v 程序包所支持的方案](https://go.microsoft.com/fwlink/p/?LinkId=330680)

**Office 2010 应用程序-V 程序包**

[Microsoft Application Virtualization 5.0 的 microsoft Office 2010 排序包](https://go.microsoft.com/fwlink/p/?LinkId=330681)

[创建或使用 app-v 5.0 Office 2010 程序包时的已知问题](https://go.microsoft.com/fwlink/p/?LinkId=330682)

[如何在 Microsoft Application Virtualization 5.0 中对 Microsoft Office 2010 进行排序](https://go.microsoft.com/fwlink/p/?LinkId=330676)

**连接组**

[在 Microsoft App 中部署连接组-V v5](https://go.microsoft.com/fwlink/p/?LinkId=330683)

[管理连接组](managing-connection-groups51.md)

**动态配置**

[关于 App-V 5.1 动态配置](about-app-v-51-dynamic-configuration.md)






 

 





