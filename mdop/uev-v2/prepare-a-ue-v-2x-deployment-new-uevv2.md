---
title: 准备 UE-V 2. x 部署
description: 准备 UE-V 2. x 部署
author: dansimp
ms.assetid: c429fd06-13ff-48c5-b9c9-fa1ec01ab800
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 04/19/2017
ms.openlocfilehash: e6b2de407990536e1a08532632dcea19ea0d0ee9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803965"
---
# 准备 UE-V 2. x 部署


在将 Microsoft 用户体验虚拟化（UE-V）2.0 或2.1 部署到企业中用户访问的设备之间进行设置的解决方案之前，需要执行一些计划和准备。 本主题将帮助你确定要执行的部署类型以及你可以提前执行的准备，以便你的部署成功。

首先，让我们看一下部署 UE-V 需要执行的任务：

-   规划 UE-V 部署

    在部署任何内容之前，最好的第一步是执行一些计划，以便你可以确定要部署的 UE-V 功能。 因此，如果您离开此页面，请确保您返回并阅读下面的规划信息。

-   [为 UE-V 2.x 部署所需功能](deploy-required-features-for-ue-v-2x-new-uevv2.md)

    每个 UE-V 部署都需要这些活动：

    -   [定义设置存储位置](https://technet.microsoft.com/library/dn458891.aspx#ssl)

    -   [确定如何部署 UE-V Agent 和管理 UE-V 配置](https://technet.microsoft.com/library/dn458891.aspx#config)

    -   在需要同步设置的每台用户计算机上[安装 Ue-v Agent](https://technet.microsoft.com/library/dn458891.aspx#agent)

-   或者，你可以[为自定义应用程序部署 ue-v 2。](deploy-ue-v-2x-for-custom-applications-new-uevv2.md)

    规划将帮助你确定是否希望 UE-V 支持自定义应用程序（第三方或业务线）的设置同步，这需要这些 UE-V 功能：

    -   [安装 UEV 生成器](https://technet.microsoft.com/library/dn458942.aspx#uevgen)，以便可以创建、编辑和验证同步自定义应用程序设置所需的自定义设置位置模板

    -   使用 UE-V 生成器[创建自定义设置位置模板](https://technet.microsoft.com/library/dn458942.aspx#createcustomtemplates)

    -   部署用于存储自定义设置位置模板的[ue-v 设置模板目录](https://technet.microsoft.com/library/dn458942.aspx#deploycatalogue)

此工作流图提供对 UE-V 部署的高级理解，以及决定如何在企业中部署 UE-V 的决策。

![deploymentworkflow](images/deploymentworkflow.png)

**规划 ue-v 部署：** 首先，你需要执行一些计划，以便你可以确定要部署的 UE-V 组件。 规划 UE-V 部署涉及以下事项：

-   [确定是否同步自定义应用程序的设置](#deciding)

    这确定你是否将在部署期间安装 UE-V 生成器，这使你可以创建自定义设置位置模板。 它涉及以下内容：

    查看[在 ue-v 部署中自动同步的设置](#autosyncsettings)。

    [确定是否需要为其他应用程序同步设置](#determinesettingssync)。

-   查看部署 UE-V （如高可用性和容量规划）[的其他注意事项](#considerations)。

-   [确认系统必备和支持的 UE-V 配置](#prereqs)

## <a href="" id="deciding"></a>确定是否同步自定义应用程序的设置


在 UE-V 部署中，许多设置将自动同步。 但是，你也可以自定义 UE-V 以同步其他应用程序的设置，如业务线和第三方应用。

确定是否希望 UE-V 同步自定义应用程序的设置可能是规划 UE-V 部署的最重要部分。 本部分中的主题将帮助您做出该决策。

### <a href="" id="autosyncsettings"></a>在 UE-V 部署中自动同步的设置

本节提供有关默认情况下在 UE-V 中同步的设置的信息，包括：

默认情况下同步其设置的桌面应用程序

默认同步的 Windows 桌面设置

Windows 应用设置同步的支持语句

请参阅[Microsoft Office 的用户体验虚拟化（ue-v）设置模板](https://www.microsoft.com/download/details.aspx?id=46367)，下载由 ue-v 同步的特定 Microsoft office 2013、microsoft office 2010 和 microsoft office 2007 设置的完整列表。

### UE-V 2.1 和 UE-V 2.1 SP1 中默认同步的桌面应用程序

当安装 UE-V 2.1 或 2.1 SP1 代理时，它将注册一个默认设置位置模板组，用于捕获这些常见 Microsoft 应用程序的设置值。

**提示**  
**Microsoft office 2007 设置同步**-在 ue-v 2.1 和 2.1 SP1 中，默认情况下不再为 Office 2007 应用程序包括设置位置模板。 但是，你仍然可以使用 UE-V 2.0 或更早版本的 Office 2007 模板，并可以从[ue-v 模板库](https://go.microsoft.com/fwlink/p/?LinkID=246589)中获取模板。



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
<td align="left"><p>Microsoft Office 2010 应用程序</p>
<p>（ <a href="https://www.microsoft.com/download/details.aspx?id=46367" data-raw-source="[Download a list of all settings synced](https://www.microsoft.com/download/details.aspx?id=46367)"> 下载已同步的所有设置的列表 </a> ）</p></td>
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
<p>Microsoft OneNote 2010</p>
<p>Microsoft SharePoint Designer 2010</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Office 2013 应用程序</p>
<p>（ <a href="https://www.microsoft.com/download/details.aspx?id=46367" data-raw-source="[Download a list of all settings synced](https://www.microsoft.com/download/details.aspx?id=46367)"> 下载已同步的所有设置的列表 </a> ）</p></td>
<td align="left"><p>Microsoft Word 2013</p>
<p>Microsoft Excel 2013</p>
<p>Microsoft Outlook 2013</p>
<p>Microsoft Access 2013</p>
<p>Microsoft Project 2013</p>
<p>Microsoft PowerPoint 2013</p>
<p>Microsoft Publisher 2013</p>
<p>Microsoft Visio 2013</p>
<p>Microsoft InfoPath 2013</p>
<p>Microsoft Lync 2013</p>
<p>Microsoft OneNote 2013</p>
<p>Microsoft SharePoint Designer 2013</p>
<p>Microsoft Office 2013 上传中心</p>
<p>Microsoft OneDrive for Business 2013</p>
<p>UE-V 2.1 和 2.1 SP1 Microsoft Office 2013 设置位置模板包括改进的 Outlook 签名支持。 我们已为新的、答复和转发的电子邮件添加了默认签名设置的同步。</p>
<div class="alert">
<strong>注意</strong><br/><p>必须为用户要同步其 Outlook 签名的任何设备创建 Outlook 配置文件。 如果尚未创建配置文件，则用户可以创建一个配置文件，然后在该设备上重新启动 Outlook 以启用签名同步。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p>浏览器选项： Internet Explorer 8、Internet Explorer 9、Internet Explorer 10 和 Internet Explorer 11</p></td>
<td align="left"><p>"收藏夹"、"主页"、"选项卡" 和 "工具栏"。</p>
<div class="alert">
<strong>注意</strong><br/><p>UE-V 不会漫游 Internet Explorer cookie 的设置。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p>Windows 附件</p></td>
<td align="left"><p>Microsoft 计算器、记事本和写字板。</p></td>
</tr>
</tbody>
</table>



**注意**  
UE-V 2.1 SP1 不会在 Windows 10 中的 Microsoft 计算器和以前操作系统中的 Microsoft 计算器之间同步设置。



### UE-V 2.0 中默认同步的桌面应用程序

安装 UE-V 2.0 代理时，它将注册一个默认的设置位置模板组，用于捕获这些常见 Microsoft 应用程序的设置值。

**提示**  
**Microsoft office 2013 设置同步**-在 Ue-v 2.0 中，默认情况下不包括 Office 2013 应用程序的设置位置模板，但可从[ue-v 模板库](https://go.microsoft.com/fwlink/p/?LinkID=246589)中下载。 将[office 2013 与 ue-v 2.0 同步](synchronizing-office-2013-with-ue-v-20-both-uevv2.md)提供有关支持的模板的详细信息，这些模板可同步 Office 2013 设置。



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
<td align="left"><p>Microsoft Office 2007 应用程序</p>
<p>（ <a href="https://www.microsoft.com/download/details.aspx?id=46367" data-raw-source="[Download a list of all settings synced](https://www.microsoft.com/download/details.aspx?id=46367)"> 下载已同步的所有设置的列表 </a> ）</p></td>
<td align="left"><p>Microsoft Access 2007</p>
<p>Microsoft Communicator 2007</p>
<p>Microsoft Excel 2007</p>
<p>Microsoft InfoPath 2007</p>
<p>Microsoft OneNote 2007</p>
<p>Microsoft Outlook 2007</p>
<p>Microsoft PowerPoint 2007</p>
<p>Microsoft Project 2007</p>
<p>Microsoft Publisher 2007</p>
<p>Microsoft SharePoint Designer 2007</p>
<p>Microsoft Visio 2007</p>
<p>Microsoft Word 2007</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Office 2010 应用程序</p>
<p>（ <a href="https://www.microsoft.com/download/details.aspx?id=46367" data-raw-source="[Download a list of all settings synced](https://www.microsoft.com/download/details.aspx?id=46367)"> 下载已同步的所有设置的列表 </a> ）</p></td>
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
<p>Microsoft OneNote 2010</p>
<p>Microsoft SharePoint Designer 2010</p></td>
</tr>
<tr class="odd">
<td align="left"><p>浏览器选项： Internet Explorer 8、Internet Explorer 9 和 Internet Explorer 10</p></td>
<td align="left"><p>"收藏夹"、"主页"、"选项卡" 和 "工具栏"。</p>
<div class="alert">
<strong>注意</strong><br/><p>UE-V 不会漫游 Internet Explorer cookie 的设置。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p>Windows 附件</p></td>
<td align="left"><p>Microsoft 计算器、记事本和写字板。</p></td>
</tr>
</tbody>
</table>



### <a href="" id="autosyncsettings2"></a>默认同步的 Windows 设置

UE-V 包括用于捕获这些 Windows 设置的设置值的设置位置模板。

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
<th align="left">Windows 设置</th>
<th align="left">描述</th>
<th align="left">适用于</th>
<th align="left">导出</th>
<th align="left">默认状态</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>桌面背景</p></td>
<td align="left"><p>当前处于活动状态的桌面背景或墙纸。</p></td>
<td align="left"><p>登录、解锁、远程连接、计划任务事件。</p></td>
<td align="left"><p>注销、锁定、远程断开连接、用户 <strong> </strong> 在 "公司设置中心" 中单击 "立即同步" 或 "计划任务间隔"</p></td>
<td align="left"><p>启用</p></td>
</tr>
<tr class="even">
<td align="left"><p>轻松使用</p></td>
<td align="left"><p>辅助功能和输入设置、Microsoft 放大镜、讲述人和屏幕键盘。</p></td>
<td align="left"><p>仅登录。</p></td>
<td align="left"><p>注销，用户 <strong> </strong> 在 "公司设置中心" 中单击 "立即同步" 或 "计划任务间隔"</p></td>
<td align="left"><p>启用</p></td>
</tr>
<tr class="odd">
<td align="left"><p>桌面设置</p></td>
<td align="left"><p>"开始" 菜单和任务栏设置、文件夹选项、默认桌面图标、附加时钟以及区域和语言设置。</p></td>
<td align="left"><p>仅登录。</p></td>
<td align="left"><p><strong> </strong> 在公司设置中心或计划任务中注销、用户单击 "立即同步"</p></td>
<td align="left"><p>启用</p></td>
</tr>
</tbody>
</table>



**注意**  
从 Windows 8 开始，UE-V 不会漫游与 "开始" 屏幕相关的设置，例如 "项目" 和 "位置"。 此外，UE-V 不支持同步已固定的任务栏项目或 Windows 文件快捷方式。



**重要提示**  
UE-V 2.1 SP1 在 Windows 10 设备之间漫游任务栏设置。 但是，UE-V 不会在运行以前操作系统的 Windows 10 设备和设备之间同步任务栏设置。



<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">设置组</th>
<th align="left">类型</th>
<th align="left">捕获</th>
<th align="left">“应用”</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>应用程序设置</strong></p></td>
<td align="left"><p>Windows 应用</p></td>
<td align="left"><p>关闭应用</p>
<p>Windows 应用设置更改事件</p></td>
<td align="left"><p>启动时启动 UE-V 应用监视器</p>
<p>打开应用</p>
<p>Windows 应用设置更改事件</p>
<p>设置包的到达</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p>桌面应用程序</p></td>
<td align="left"><p>应用程序关闭</p></td>
<td align="left"><p>应用程序打开和关闭</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>桌面设置</strong></p></td>
<td align="left"><p>桌面背景</p></td>
<td align="left"><p>锁定或注销</p></td>
<td align="left"><p>登录、解锁、远程连接、新软件包到达通知、用户单击 <strong> </strong> 公司设置中心的 "立即同步" 或 "计划任务运行"。</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p>轻松访问（通用-辅助功能、讲述人、放大镜、屏幕键盘）</p></td>
<td align="left"><p>锁定或注销</p></td>
<td align="left"><p>Logon</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p>轻松访问（Shell-音频、辅助功能、键盘和鼠标）</p></td>
<td align="left"><p>锁定或注销</p></td>
<td align="left"><p>登录、解锁、远程连接、新程序包到达通知、用户 <strong> </strong> 在 "公司设置中心" 中单击 "同步" 或 "计划任务运行"</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p>桌面设置</p></td>
<td align="left"><p>锁定或注销</p></td>
<td align="left"><p>Logon</p></td>
</tr>
</tbody>
</table>



### UE-V-支持 Windows 应用

对于 Windows 应用，应用开发人员将指定同步的设置。 你可以指定启用哪些 Windows 应用进行设置同步。

若要在 Windows PowerShell 命令提示符下显示可将计算机上的设置与计算机的程序包系列名称、启用状态和已启用源同步的 Windows 应用的列表，请输入： `Get-UevAppxPackage`

**注意**  
在 Windows 8 中，如果域用户将他们的登录凭据链接到其 Microsoft 帐户，UE-V 不会同步 Windows 应用设置。 此链接会将设置同步到 Microsoft OneDrive，从而使 UE-V 可以禁用 Windows 应用设置同步。



### UE-V-支持漫游打印机

UE-V 2.1 SP1 允许网络打印机在设备之间漫游，以便用户登录到网络上的任何设备时可以访问其网络打印机。 这包括将其设置为默认打印机的漫游打印机。

UE-V 中的打印机漫游需要以下其中一种方案：

-   打印服务器在漫游到新设备时可以下载所需的驱动程序。

-   漫游网络打印机的驱动程序已在需要访问该网络打印机的任何设备上预安装。

-   可以从 Windows Update 获取打印机驱动程序。

**注意**  
UE-V 打印机漫游**功能不会漫游打印机**设置或首选项，例如双面打印。



### <a href="" id="determinesettingssync"></a>确定是否需要同步其他应用程序的设置

在你查看了在 UE-V 部署中自动同步的设置后，你希望确定是否将同步其他应用程序的设置，因为这决定了如何在整个企业中部署 UE-V。

作为管理员，当你考虑要包含在 UE-V 解决方案中的桌面应用程序时，请考虑哪些设置可以由用户自定义，以及应用程序存储其设置的方式和位置。 并非所有桌面应用程序都具有可自定义或经常由用户自定义的设置。 此外，并非所有桌面应用程序设置都可以在多台计算机或环境中安全地同步。

通常，你可以同步满足以下条件的设置：

-   存储在用户易于访问的位置的设置。 例如，不要同步 HKEY 中存储的设置或注册表的 \ _CURRENT \ _USER （HKCU）部分之外的设置。

-   不特定于特定计算机的设置。 例如，排除网络或硬件配置。

-   可以在计算机之间同步的设置，而不会损坏数据。 例如，不要使用存储在数据库文件中的设置。

### <a href="" id="checklistsettingssync"></a>评估自定义应用程序的清单

如果你确定需要同步其他应用程序的设置，你可以使用此清单来帮助确定你将包括哪些应用程序。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>此应用程序是否包含用户可自定义的设置？</p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>用户对这些设置的同步是否重要？</p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>这些用户设置是否已由应用程序管理或设置策略解决方案管理？ UE-V 在登录、解锁或远程连接事件时，在应用程序启动和 Windows 设置中应用应用程序设置。 如果你将 UE-V 与其他设置共享解决方案配合使用，则用户可能会在同步设置中遇到不一致的情况。</p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>应用程序设置是否特定于计算机？ 与硬件或特定计算机配置相关联的应用程序首选项和自定义不会在多个会话之间持续同步，并且可能导致应用程序体验较差。</p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>应用程序将设置存储在程序文件目录中还是位于 <strong> 用户 </strong> [用户名] &lt; 强 &gt; AppData </strong> &lt; 强 &gt; LocalLow </strong> 目录中的文件目录？ 存储在其中任一位置的应用程序数据通常不应与用户同步，因为此数据特定于计算机，或者由于数据太大而无法同步。</p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>应用程序是否在包含不应同步的其他应用程序数据的文件中存储任何设置？ UE-V 将文件作为单个单元进行同步。 如果设置存储在包含应用程序数据而不是设置的文件中，则同步这些附加数据可能会导致应用程序体验较差。</p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>包含这些设置的文件有多大？ 设置同步的性能可能会受到大型文件的影响。 包括大型文件可能会影响设置同步的性能。</p></td>
</tr>
</tbody>
</table>



## <a href="" id="considerations"></a>准备 UE-V 部署时的其他注意事项


在准备部署 UE-V 时，还应考虑以下事项：

-   [管理凭据同步](#creds)

-   [Windows 应用设置同步](#appxsettings)

-   [自定义 UE-V 设置位置模板](#custom)

-   [无意间的用户设置配置](#prevent)

-   [性能和容量](#capacity)

-   [高可用性](#high)

-   [计算机时钟同步](#clocksync)

### <a href="" id="creds"></a>在 UE-V 2.1 和 UE-V 2.1 SP1 中管理凭据同步

许多企业应用程序（包括 Microsoft Outlook 和 Lync）在登录时提示用户输入其域凭据。 用户可以选择将其凭据保存到磁盘，以防止每次打开这些应用程序时都必须输入它们。 启用漫游凭据同步使用户可以在一台计算机上保存其凭据，避免在其环境中使用的每台计算机上重新输入它们。 用户可将某些域凭据与 UE-V 2.1 和 2.1 SP1 同步。

**重要提示**  
默认情况下，凭据同步处于禁用状态。 你必须在部署期间显式启用凭据同步以实现此功能。



UE-V 2.1 和 2.1 SP1 可以同步企业凭据，但不要漫游仅供在本地计算机上使用的凭据。

凭据是同步设置，这意味着在 UE-V 同步后首次登录到你的配置文件时，这些凭据会应用到你的配置文件。

凭据同步由其自己的设置位置模板管理，默认情况下该模板处于禁用状态。 你可以通过用于其他模板的相同方法启用或禁用此模板。 此功能的模板标识符为 RoamingCredentialSettings。

**重要提示**  
如果你在你的环境中使用 Active Directory 凭据漫游，我们建议你不要启用 UE-V 凭据漫游模板。



使用以下方法之一启用凭据同步：

-   公司设置中心

-   PowerShell

-   组策略

**注意**  
凭据在同步期间加密。



[公司设置中心](https://technet.microsoft.com/library/dn458903.aspx)**：** 选中 "Windows 设置" 下的 "漫游凭据设置" 复选框以启用凭据同步。 取消选中该框以禁用它。 只有当您的帐户未配置为使用 Microsoft 帐户同步设置时，此复选框才会出现在 "公司设置中心" 中。

[Powershell](https://technet.microsoft.com/library/dn458937.aspx)**：** 此 PowerShell cmdlet 支持凭据同步：

``` syntax
Enable-UevTemplate RoamingCredentialSettings
```

此 PowerShell cmdlet 禁用凭据同步：

``` syntax
Disable-UevTemplate RoamingCredentialSettings
```

[组策略](https://technet.microsoft.com/library/dn458893.aspx)**：** 必须[部署最新的 MDOP ADMX 模板](https://go.microsoft.com/fwlink/p/?LinkId=393944)，才能通过组策略启用凭据同步。 通过 Windows 设置管理凭据同步。 若要使用组策略管理此功能，请启用 "同步 Windows 设置" 策略。

1.  打开组策略编辑器并导航到 "**用户配置"-"管理模板-Windows 组件-Microsoft 用户体验虚拟化**"。

2.  双击 "**同步 Windows 设置**"。

3.  如果启用此策略，则可以通过选中 "**漫游凭据**" 复选框，或通过取消选中 "禁用凭据同步" 来启用凭据同步。

4.  单击“确定”****。

### 由 UE-V 同步的凭据位置

应用程序保存到以下位置的凭据文件是同步的：

-   %UserProfile%\\AppData\\Roaming\\Microsoft\\Credentials\\

-   %UserProfile%\\AppData\\Roaming\\Microsoft\\Crypto\\

-   %UserProfile%\\AppData\\Roaming\\Microsoft\\Protect\\

-   %UserProfile%\\AppData\\Roaming\\Microsoft\\SystemCertificates\\

保存到其他位置的凭据不会通过 UE-V 同步。

### <a href="" id="appxsettings"></a>Windows 应用设置同步

UE-V 通过三种方式管理 Windows 应用设置同步：

-   **同步 Windows 应用：** 允许或拒绝任何 Windows 应用同步

-   **Windows 应用列表：** 同步 Windows 应用列表

-   未**列出的默认同步行为：** 确定不在 Windows 应用列表中的 Windows 应用的同步行为。

有关详细信息，请参阅[Windows 应用列表](https://technet.microsoft.com/library/dn458925.aspx#win8applist)。

### <a href="" id="custom"></a>自定义 UE-V 设置位置模板

如果你要部署 UE-V 以同步自定义应用程序的设置，你将使用 UE-V 生成器为这些桌面应用程序创建自定义设置位置模板。 在测试环境中创建和测试自定义设置位置模板后，可以将设置位置模板部署到企业中的计算机。

自定义设置位置模板必须使用现有部署基础结构（如企业软件分发（ESD）方法，如 System Center Configuration Manager）或通过配置 UE-V 设置模板目录进行部署。 必须使用 UE-V WMI 或 Windows PowerShell 注册使用 Configuration Manager 或组策略部署的模板。

有关自定义设置位置模板的详细信息，请参阅[为自定义应用程序部署 ue-v 2。](deploy-ue-v-2x-for-custom-applications-new-uevv2.md) 有关将 UE-V 与 Configuration Manager 配合使用的详细信息，请参阅[使用 System Center Configuration Manager 2012 配置 ue-v 2。](configuring-ue-v-2x-with-system-center-configuration-manager-2012-both-uevv2.md)

### <a href="" id="prevent"></a>防止无意间的用户设置配置

UE-V 从设置存储位置下载新的用户设置信息，并在这些实例中将这些设置应用于本地计算机：

-   每次启动具有注册的 UE-V 模板的应用程序时。

-   当用户登录到计算机时。

-   用户解锁计算机时。

-   连接到安装了 UE-V 的远程桌面计算机时。

-   当运行同步控制器应用程序计划任务时。

如果 UE-V 已安装在计算机 A 和计算机 B 上，而你希望应用程序的设置位于计算机 A 上，则计算机 A 应首先打开并关闭该应用程序。 如果首先在计算机 B 上打开和关闭应用程序，则计算机 A 上的应用程序设置将配置为计算机 B 上的应用程序设置。每个应用程序基础上的设置在计算机之间同步。 随着时间的推移，在计算机上打开和关闭首选设置时，设置会保持一致。

此方案也适用于 Windows 设置。 如果计算机 B 上的 Windows 设置应该与计算机 A 上的 Windows 设置相同，则用户应该先登录，然后再注销计算机 A。

如果用户所需的用户设置按错误的顺序应用，则可以通过针对覆盖了这些设置的计算机上的特定应用程序或 Windows 配置执行还原操作来恢复它们。 有关详细信息，请参阅[在 ue-v 2 中管理管理备份和还原](manage-administrative-backup-and-restore-in-ue-v-2x-new-topic-for-21.md)。

### <a href="" id="capacity"></a>性能和容量规划

通过标准磁盘容量和网络运行状况监视，指定你对 UE-V 的要求。

UE-V 使用服务器消息块（SMB）共享存储设置程序包。 设置包的大小根据每个应用程序的设置信息而有所不同。 虽然大多数设置程序包较小，但同步可能较大的文件（如桌面映像）可能会导致性能较差，尤其是在速度较慢的网络上。

若要减少网络延迟问题，请在用户计算机所在的同一本地网络上创建设置存储位置。 我们建议每个用户 20 MB 的磁盘空间用于设置存储位置。

默认情况下，UE-V 同步将在2秒后超时，以防止由于大型设置包而产生过多的延迟。 你可以使用[组策略对象](https://technet.microsoft.com/library/dn458893.aspx)配置 Powerschool = SyncProvider 设置。

### <a href="" id="high"></a>UE-V 的高可用性

UE-V 设置存储位置和设置模板目录支持将用户数据存储在任何可写的共享上。 为确保高可用性，请遵循以下条件：

-   使用 NTFS 文件系统设置存储卷的格式。

-   共享可以使用分布式文件系统（DFS），但有一些限制。
特别是，支持分布式文件系统复制（使用或不使用分布式文件系统命名空间（DFS-N）的单个目标配置。
同样，DFS-N 仅支持单个目标配置。
有关详细信息，请参阅[microsoft 有关复制的用户配置文件数据的支持声明](https://go.microsoft.com/fwlink/p/?LinkId=313991)，以及[有关适用于 DFS 和 dfs 部署方案的 microsoft 支持策略的信息](https://support.microsoft.com/kb/2533009)。

    此外，由于 SYSVOL 使用 DFS 进行复制，因此无法将 SYSVOL 用于 UE-V 数据文件复制。

-   配置在[部署 ue-v 2. x 的设置存储位置](https://technet.microsoft.com/library/dn458891.aspx#ssl)中指定的共享权限和 NTFS 访问控制列表（acl）。

-   将文件服务器群集与 UE-V Agent 配合使用，可在通信失败时提供对用户状态数据副本的访问权限。

-   你可以将设置存储路径数据（用户数据）和设置模板目录模板存储在群集共享、DFS-N 共享或两者上。

### <a href="" id="clocksync"></a>同步 UE-V 设置同步的计算机时钟

运行 UE-V Agent 的计算机必须使用时间服务器保持一致的设置体验。 UE-V 使用时间戳确定设置是否必须从设置存储位置同步。 如果计算机时钟不准确，则较旧的设置可能会覆盖较新的设置，或者新设置可能不会保存到设置存储位置。

## <a href="" id="prereqs"></a>确认系统必备和支持的 UE-V 配置


在继续操作之前，请确保你的环境包括运行 UE-V 的这些要求。

<table style="width:100%;">
<colgroup>
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong>操作系统</strong></th>
<th align="left"><strong>版本</strong></th>
<th align="left"><strong>Service pack</strong></th>
<th align="left"><strong>系统体系结构</strong></th>
<th align="left"><strong>Windows PowerShell</strong></th>
<th align="left"><strong>Microsoft .NET Framework</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows 7</p></td>
<td align="left"><p>旗舰版、企业版或专业版</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>32 位或 64 位</p></td>
<td align="left"><p>Windows PowerShell 3.0 或更高版本</p></td>
<td align="left"><p>用于 UE-V 2.1 的 .NET Framework 4.5 或更高版本。</p>
<p>用于 UE-V 2.0 的 .NET Framework 4 或更高版本。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server 2008 R2</p></td>
<td align="left"><p>标准版、企业版、数据中心版或 Web 服务器</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>64 位</p></td>
<td align="left"><p>Windows PowerShell 3.0 或更高版本</p></td>
<td align="left"><p>用于 UE-V 2.1 的 .NET Framework 4.5 或更高版本。</p>
<p>用于 UE-V 2.0 的 .NET Framework 4 或更高版本。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows 8 和 Windows 8。1</p></td>
<td align="left"><p>企业版或专业版</p></td>
<td align="left"><p>无</p></td>
<td align="left"><p>32 位或 64 位</p></td>
<td align="left"><p>Windows PowerShell 3.0 或更高版本</p></td>
<td align="left"><p>.NET Framework 4.5 或更高版本</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows 10 预1607版本</p>
<div class="alert">
<strong>注意</strong><br/><p>仅 UE-V 2.1 SP1 支持 Windows 10 的预1607版本</p>
</div>
<div>

</div></td>
<td align="left"><p>企业版或专业版</p></td>
<td align="left"><p>无</p></td>
<td align="left"><p>32 位或 64 位</p></td>
<td align="left"><p>Windows PowerShell 3.0 或更高版本</p></td>
<td align="left"><p>.NET Framework 4.6</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server 2012 和 Windows Server 2012 R2</p></td>
<td align="left"><p>标准版或数据中心</p></td>
<td align="left"><p>无</p></td>
<td align="left"><p>64 位</p></td>
<td align="left"><p>Windows PowerShell 3.0 或更高版本</p></td>
<td align="left"><p>.NET Framework 4.5 或更高版本</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server 2016</p></td>
<td align="left"><p>标准版或数据中心</p></td>
<td align="left"><p>无</p></td>
<td align="left"><p>64 位</p></td>
<td align="left"><p>Windows PowerShell 3.0 或更高版本</p></td>
<td align="left"><p>.NET Framework 4.6 或更高版本</p></td>
</tr>
</tbody>
</table>



同样 .。。

-   **MDOP 许可证：** 此技术是 Microsoft 桌面优化包（MDOP）的一部分。 企业客户可以通过 Microsoft 软件保障获得 MDOP。 有关 Microsoft 软件保证和获取 MDOP 的详细信息，请参阅如何获取 MDOP （ https://go.microsoft.com/fwlink/p/?LinkId=322049) 。

-   要安装的任何计算机的**管理凭据**

**注意**  

-   从 WIndows 10 版本1607开始，UE-V 已包含在[windows 10 For 企业](https://www.microsoft.com/WindowsForBusiness/windows-for-enterprise)中，不再属于 Microsoft 桌面优化包。

-   UE-V Agent 的 UE-V Windows PowerShell 功能需要安装 .NET Framework 4 或更高版本以及 Windows PowerShell 3.0 或更高版本才能启用。 [在此处](https://go.microsoft.com/fwlink/?LinkId=309609)下载 Windows PowerShell 3.0。

-   在运行 Windows 7 或 Windows Server 2008 R2 操作系统的计算机上安装 .NET Framework 4 或 .NET Framework 4.5。 Windows 8、Windows 8.1 和 Windows Server 2012 操作系统附带了 .NET Framework 4.5。 Windows 10 操作系统附带了 .NET Framework 4.6。
-   UE-V 不支持强制配置文件的 "删除漫游缓存" 策略，不应使用。



不存在特定于 UE-V 的特殊随机访问内存（RAM）要求。

### 通过同步提供程序同步设置

同步提供程序是用户的默认设置，用于将本地缓存与这些实例中的设置存储位置同步：

-   登录/注销

-   锁定/解锁

-   远程桌面连接/断开连接

-   应用程序打开/关闭

计划任务每隔30分钟或通过某些应用程序的特定触发事件来管理此设置的同步。 有关详细信息，请参阅[更改 ue-v 2. x 计划任务的频率](changing-the-frequency-of-ue-v-2x-scheduled-tasks-both-uevv2.md)。

UE-V Agent 会同步不始终连接到企业网络（远程计算机和笔记本电脑）的计算机的用户设置，以及始终连接到网络（运行 Windows Server 和托管虚拟桌面界面（VDI）会话的计算机）的计算机的用户设置。

**对始终可用的连接的计算机进行同步：** 在始终连接到网络的计算机上使用 UE-V 时，必须使用*powerschool = None*参数配置 ue-v Agent 以同步设置，该参数将设置存储服务器视为标准网络共享。 在此配置中，可以配置 UE-V Agent 以通知应用程序设置的导入是否已延迟。

通过以下方法之一启用此配置：

-   在 UE-V 安装期间，在命令提示符处或在批处理文件中，设置 AgentSetup.exe 参数*powerschool = None*。 [部署 ue-v 2. x agent](https://technet.microsoft.com/library/dn458891.aspx#agent)可提供更多信息。

-   在 UE-V 安装之后，使用 System Center 2012 配置管理器中的设置管理功能或 MDOP ADMX 模板推送*powerschool = None*配置。

-   使用 Windows PowerShell 或 Windows Management Instrumentation （WMI）设置*powerschool = None*配置。

    **注意**  
    最后两种方法对虚拟桌面基础结构（VDI）环境不起作用。



必须重新启动计算机才能使设置开始同步。

**注意**  
如果设置*powerschool = None*，则任何设置更改都将直接保存到服务器。 如果找不到指向设置存储路径的网络连接，则设置更改将缓存在设备上，并且将在下次运行同步提供程序时进行同步。 如果未找到设置存储路径，并且在注销时从池中的 VDI 环境中删除了用户配置文件，则会丢失设置更改，并且用户必须在计算机重新连接到设置存储路径时重新应用更改。



**外部同步引擎的同步：***Powerschool = External*参数指定如果 ue-v 设置写入到用户计算机上的本地文件夹，则可以使用任何外部同步引擎（如 OneDrive for Business、工作文件夹、Sharepoint 或 Dropbox）将这些设置应用于用户访问的不同计算机。

**对共享的 VDI 会话的支持：** UE-V 2.1 和 2.1 SP1 提供对在最终用户之间共享的 VDI 会话的支持。 你可以注册和配置特殊的 VDI 模板，从而确保 UE-V 将其所有功能完整地保留为非永久性 VDI 会话。

**注意**  
如果您不为非永久性 VDI 会话启用 VDI 模式，则某些功能不起作用，如[备份/还原和上一次正常工作（LKG）](https://technet.microsoft.com/library/dn878331.aspx)。



VDI 模板由 UE-V 2.1 和 2.1 SP1 提供，并且在安装后，通常在此处可用 C:\\program files Files\\Microsoft 用户体验 Virtualization\\Templates\\VdiState.xml

### UE-V 发电机支持的先决条件

在用于创建自定义设置位置模板的计算机上安装 UE-V 发生器。 此计算机应该能够运行其设置已同步的应用程序。 您必须是运行 UE-V 发生器软件的计算机上 "管理员" 组的成员。

UE-V 生成器必须安装在使用 NTFS 文件系统的计算机上。 UE-V 发生器软件需要 .NET Framework 4。 有关详细信息，请参阅[为自定义应用程序部署 ue-v 2。](deploy-ue-v-2x-for-custom-applications-new-uevv2.md)

## 此产品的其他资源


-   [Microsoft 用户体验虚拟化（UE-V） 2. x](index.md)

-   [UE-V 2.x 入门](get-started-with-ue-v-2x-new-uevv2.md)

-   [管理 UE-V 2. x](administering-ue-v-2x-new-uevv2.md)

-   [解决 UE-V 2. x](troubleshooting-ue-v-2x-both-uevv2.md)

-   [UE-V 2.x 的技术参考](technical-reference-for-ue-v-2x-both-uevv2.md)














