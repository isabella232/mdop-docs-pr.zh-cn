---
title: 准备 UE-V 2.x 部署
description: 准备 UE-V 2.x 部署
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
ms.openlocfilehash: 3e4d4b69975deda473372345733d8e8593a4775d
ms.sourcegitcommit: 3e0500abde44d6a09c7ac8e3caf5e25929b490a4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2021
ms.locfileid: "11910527"
---
# <a name="prepare-a-ue-v-2x-deployment"></a>准备 UE-V 2.x 部署


部署 Microsoft 用户体验虚拟化 (UE-V) 2.0 或 2.1 作为在企业中用户访问的设备之间同步设置的解决方案之前，需要做一些规划和准备。 本主题帮助您确定要执行哪种类型的部署，以及您可以事先进行哪些准备，以便部署成功。

首先，我们来看看将执行的任务，以部署UE-V：

-   规划UE-V部署

    在部署任何内容之前，良好的第一步是进行一些规划，以便确定UE-V部署哪些功能。 因此，如果你离开此页面，请确保返回并阅读下面的规划信息。

-   [为 UE-V 2.x 部署所需功能](deploy-required-features-for-ue-v-2x-new-uevv2.md)

    每个UE-V部署都需要以下活动：

    -   [定义设置存储位置](https://technet.microsoft.com/library/dn458891.aspx#ssl)

    -   [确定如何部署 UE-V 代理和管理UE-V配置](https://technet.microsoft.com/library/dn458891.aspx#config)

    -   [在UE-V](https://technet.microsoft.com/library/dn458891.aspx#agent)同步设置的每个用户计算机上安装该代理

-   （可选）您可以部署[UE-V 2.x for Custom Applications](deploy-ue-v-2x-for-custom-applications-new-uevv2.md)

    规划将帮助您确定是希望 UE-V支持自定义应用程序（第三方 (或业务线) ）的设置同步，这需要以下UE-V功能：

    -   [安装 UEV 生成器](https://technet.microsoft.com/library/dn458942.aspx#uevgen) ，以便你可以创建、编辑和验证同步自定义应用程序设置所需的自定义设置位置模板

    -   [使用生成器创建自定义](https://technet.microsoft.com/library/dn458942.aspx#createcustomtemplates)设置位置UE-V模板

    -   [部署UE-V](https://technet.microsoft.com/library/dn458942.aspx#deploycatalogue)自定义设置位置模板的自定义设置模板目录

此工作流图提供了对部署UE-V的高级别了解，以及确定如何在企业中UE-V部署策略。

![deploymentworkflow。](images/deploymentworkflow.png)

**规划UE-V部署：** 首先，需要做一些规划，以便确定要UE-V部署哪些组件。 规划UE-V涉及以下方面：

-   [决定是否同步自定义应用程序的设置](#deciding)

    这将确定是否在部署过程中安装UE-V生成器，从而允许你创建自定义设置位置模板。 它涉及以下内容：

    查看[在部署部署中自动UE-V的设置](#autosyncsettings)。

    [确定是否需要为其他应用程序同步设置](#determinesettingssync)。

-   查看[部署应用程序的其他UE-V，](#considerations)例如高可用性和容量规划。

-   [确认系统必备组件和支持的配置UE-V](#prereqs)

## <a name="decide-whether-to-synchronize-settings-for-custom-applications"></a><a href="" id="deciding"></a>决定是否为自定义设置同步自定义应用程序


在UE-V部署中，许多设置会自动同步。 但你还可以自定义UE-V同步其他应用程序（如业务线应用和第三方应用）的设置。

决定是否要UE-V自定义应用程序的设置可能是规划自定义应用程序部署UE-V部分。 本节中的主题将帮助您做出该决定。

### <a name="settings-that-are-automatically-synchronized-in-a-ue-v-deployment"></a><a href="" id="autosyncsettings"></a>设置部署中自动同步UE-V组

本节提供有关默认情况下在 UE-V 中同步的设置的信息，包括：

设置默认同步的桌面应用程序

Windows同步的桌面设置

支持应用设置Windows声明

请参阅 Microsoft Office 的用户体验虚拟化[ (UE-V) ](https://www.microsoft.com/download/details.aspx?id=46367)设置模板，下载由 UE-V 同步的特定 Microsoft Office 2013、Microsoft Office 2010 和 Microsoft Office 2007 设置的完整列表。

### <a name="desktop-applications-synchronized-by-default-in-ue-v-21-and-ue-v-21-sp1"></a>默认情况下，桌面应用程序在 UE-V 2.1 和 UE-V 2.1 SP1 中同步

在安装 UE-V 2.1 或 2.1 SP1 代理时，它会注册一组默认的设置位置模板，用于捕获这些常见 Microsoft 应用程序的设置值。

**提示**  
**Microsoft Office 2007**设置 同步 – 在 UE-V 2.1 和 2.1 SP1 中，Office 2007 应用程序默认情况下不再包含设置位置模板。 但是，您仍可以使用 Office 2.0 UE-V 2007 模板，并且可以从 UE-V[模板库获取模板](https://go.microsoft.com/fwlink/p/?LinkID=246589)。



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
<p> (<a href="https://www.microsoft.com/download/details.aspx?id=46367" data-raw-source="[Download a list of all settings synced](https://www.microsoft.com/download/details.aspx?id=46367)"> 下载同步的所有设置 </a>) </p></td>
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
<p> (<a href="https://www.microsoft.com/download/details.aspx?id=46367" data-raw-source="[Download a list of all settings synced](https://www.microsoft.com/download/details.aspx?id=46367)"> 下载同步的所有设置 </a>) </p></td>
<td align="left"><p>Microsoft Word 2013</p>
<p>Microsoft Excel 2013</p>
<p>Microsoft Outlook 2013</p>
<p>Microsoft Access 2013</p>
<p>Microsoft Project 2013 年</p>
<p>Microsoft PowerPoint 2013</p>
<p>Microsoft Publisher 2013</p>
<p>Microsoft Visio 2013</p>
<p>Microsoft InfoPath 2013</p>
<p>Microsoft Lync 2013</p>
<p>Microsoft OneNote 2013</p>
<p>Microsoft SharePoint Designer 2013</p>
<p>Microsoft Office 2013 Upload Center</p>
<p>Microsoft OneDrive for Business 2013</p>
<p>2013 UE-V 2.1 和 2.1 SP1 Microsoft Office模板包括改进的 Outlook 签名支持。 我们添加了新电子邮件、回复电子邮件和转发电子邮件的默认签名设置的同步。</p>
<div class="alert">
<strong>注意</strong><br/><p>必须为Outlook同步其签名的任何设备创建一个Outlook配置文件。 如果尚未创建配置文件，用户可以创建一个配置文件，然后在Outlook重新启动配置文件以启用签名同步。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p>浏览器选项：Internet Explorer 8、Internet Explorer 9、Internet Explorer 10 和 Internet Explorer 11</p></td>
<td align="left"><p>收藏夹、主页、选项卡和工具栏。</p>
<div class="alert">
<strong>注意</strong><br/><p>UE-V Cookie 的漫游Internet Explorer设置。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p>Windows附件</p></td>
<td align="left"><p>Microsoft 计算器、记事本、WordPad。</p></td>
</tr>
</tbody>
</table>



**注意**  
UE-V 2.1 SP1 不会同步Microsoft 计算器操作系统中的Windows 10和Microsoft 计算器设置。



### <a name="desktop-applications-synchronized-by-default-in-ue-v-20"></a>默认情况下，桌面应用程序在 UE-V 2.0 中同步

在安装 UE-V 2.0 代理时，它会注册一组默认设置位置模板，用于捕获这些常见 Microsoft 应用程序的设置值。

**提示**  
**Microsoft Office 2013**设置 同步 – 在 UE-V 2.0 中，Office 2013 应用程序默认情况下不包含设置位置模板，但可从[UE-V](https://go.microsoft.com/fwlink/p/?LinkID=246589)模板库下载。 [将 Office 2013 与 UE-V 2.0](synchronizing-office-2013-with-ue-v-20-both-uevv2.md)同步提供了有关同步 Office 2013 设置的支持模板的详细信息。



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
<p> (<a href="https://www.microsoft.com/download/details.aspx?id=46367" data-raw-source="[Download a list of all settings synced](https://www.microsoft.com/download/details.aspx?id=46367)"> 下载同步的所有设置 </a>) </p></td>
<td align="left"><p>Microsoft Access 2007</p>
<p>Microsoft Communicator 2007</p>
<p>Microsoft Excel 2007</p>
<p>Microsoft InfoPath 2007</p>
<p>Microsoft OneNote 2007</p>
<p>Microsoft Outlook 2007</p>
<p>Microsoft PowerPoint 2007</p>
<p>Microsoft Project 2007</p>
<p>Microsoft Publisher 2007 年</p>
<p>Microsoft SharePoint Designer 2007</p>
<p>Microsoft Visio 2007</p>
<p>Microsoft Word 2007</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Office 2010 应用程序</p>
<p> (<a href="https://www.microsoft.com/download/details.aspx?id=46367" data-raw-source="[Download a list of all settings synced](https://www.microsoft.com/download/details.aspx?id=46367)"> 下载同步的所有设置 </a>) </p></td>
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
<td align="left"><p>浏览器选项：Internet Explorer 8、Internet Explorer 9 和 Internet Explorer 10</p></td>
<td align="left"><p>收藏夹、主页、选项卡和工具栏。</p>
<div class="alert">
<strong>注意</strong><br/><p>UE-V Cookie 的漫游Internet Explorer设置。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p>Windows附件</p></td>
<td align="left"><p>Microsoft 计算器、记事本、WordPad。</p></td>
</tr>
</tbody>
</table>



### <a name="windows-settings-synchronized-by-default"></a><a href="" id="autosyncsettings2"></a>Windows同步的设置

UE-V包括用于捕获这些设置的设置值的设置Windows模板。

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
<th align="left">应用于</th>
<th align="left">导出</th>
<th align="left">默认状态</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>桌面背景</p></td>
<td align="left"><p>当前处于活动状态的桌面背景或墙纸。</p></td>
<td align="left"><p>登录、解锁、远程连接、计划任务事件。</p></td>
<td align="left"><p>注销、锁定、远程断开连接、用户单击公司中心中的"立即同步 <strong> </strong> 设置或计划的任务间隔</p></td>
<td align="left"><p>启用</p></td>
</tr>
<tr class="even">
<td align="left"><p>轻松使用</p></td>
<td align="left"><p>辅助功能和输入设置、Microsoft 放大镜、讲述人以及屏幕键盘。</p></td>
<td align="left"><p>仅登录。</p></td>
<td align="left"><p>注销、用户单击"在公司 <strong> </strong> 中心设置立即同步"或计划的任务间隔</p></td>
<td align="left"><p>启用</p></td>
</tr>
<tr class="odd">
<td align="left"><p>桌面设置</p></td>
<td align="left"><p>"开始"菜单和任务栏设置、文件夹选项、默认桌面图标、其他时钟以及"地区"和"语言"设置。</p></td>
<td align="left"><p>仅登录。</p></td>
<td align="left"><p>注销、用户单击"在公司 <strong> </strong> 中心设置立即同步"或计划任务</p></td>
<td align="left"><p>启用</p></td>
</tr>
</tbody>
</table>



**注意**  
从 Windows 8 开始，UE-V不会漫游与"开始"屏幕相关的设置，如项目和位置。 此外，UE-V固定任务栏项目或文件快捷方式Windows同步。



**重要提示**  
UE-V 2.1 SP1 在设备之间漫游Windows 10设置。 但是，UE-V在运行以前操作系统Windows 10设备之间同步任务栏设置。



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
<th align="left">类别</th>
<th align="left">捕获</th>
<th align="left">“应用”</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>应用程序设置</strong></p></td>
<td align="left"><p>Windows 应用</p></td>
<td align="left"><p>关闭应用</p>
<p>Windows应用设置更改事件</p></td>
<td align="left"><p>启动时UE-V应用监视器</p>
<p>打开应用</p>
<p>Windows应用设置更改事件</p>
<p>设置包到达</p></td>
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
<td align="left"><p>登录、解锁、远程连接、新程序包到达通知、用户单击公司中心中的"立即同步设置 <strong> </strong> 或计划任务运行。</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p>轻松使用 (- 辅助功能、讲述人、放大镜、屏幕键盘) </p></td>
<td align="left"><p>锁定或注销</p></td>
<td align="left"><p>登录</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p>轻松使用命令行 (- 音频、辅助功能、键盘、鼠标) </p></td>
<td align="left"><p>锁定或注销</p></td>
<td align="left"><p>登录、解锁、远程连接、新程序包到达通知、用户单击公司中心中的"立即同步设置 <strong> </strong> 或计划任务运行</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p>桌面设置</p></td>
<td align="left"><p>锁定或注销</p></td>
<td align="left"><p>登录</p></td>
</tr>
</tbody>
</table>



### <a name="ue-v-support-for-windows-apps"></a>UE-V应用Windows支持

对于Windows，应用开发人员指定同步的设置。 你可以指定为Windows启用哪些应用。

若要显示可在计算机上Windows程序包系列名称、已启用状态和已启用源同步设置的应用列表，请在命令提示符下Windows PowerShell输入： `Get-UevAppxPackage`

**注意**  
截至Windows 8，UE-V如果用户将其登录凭据链接到其 Microsoft 帐户，Windows应用设置同步。 此链接将设置同步到Microsoft OneDrive，UE-V，这将禁用Windows应用的同步。



### <a name="ue-v-support-for-roaming-printers"></a>UE-V支持漫游打印机

UE-V 2.1 SP1 允许网络打印机在设备之间漫游，以便用户登录到网络的任何设备时可以访问其网络打印机。 这包括漫游设置为默认值的打印机。

打印机在UE-V漫游需要以下方案之一：

-   打印服务器可以在漫游到新设备时下载所需的驱动程序。

-   漫游网络打印机的驱动程序预安装在需要访问该网络打印机的任何设备上。

-   打印机驱动程序可以从更新Windows获取。

**注意**  
打印机UE-V功能不会漫游打印机设置或首选项，**** 例如双面打印。



### <a name="determine-whether-you-need-settings-synchronized-for-other-applications"></a><a href="" id="determinesettingssync"></a>确定是否需要为其他应用程序同步设置

查看在 UE-V 部署中自动同步的设置后，您需要决定是否同步其他应用程序的设置，因为这将确定如何在整个企业中UE-V应用程序。

作为管理员，在考虑要包括在 UE-V 解决方案中的桌面应用程序时，请考虑用户可自定义哪些设置，以及应用程序存储其设置的方法和位置。 并非所有桌面应用程序都有可自定义或由用户例行自定义的设置。 此外，并非所有桌面应用程序设置都可以跨多台计算机或环境安全地同步。

通常，您可以同步满足以下条件的设置：

-   设置用户可访问的位置存储的库。 例如，不要同步存储在 System32 或注册表的 HKEY\_CURRENT\_USER (HKCU) 外部的设置。

-   设置特定计算机的特定计算机。 例如，排除网络或硬件配置。

-   设置，可以在计算机之间同步，而不会存在数据损坏的风险。 例如，请勿使用存储在数据库文件中的设置。

### <a name="checklist-for-evaluating-custom-applications"></a><a href="" id="checklistsettingssync"></a>用于评估自定义应用程序的清单

如果决定需要为其他应用程序同步设置，可以使用此检查表帮助确定要包括的应用程序。

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
<td align="left"><p>此应用程序是否包含用户可以自定义的设置？</p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>这些设置同步对于用户是否很重要？</p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>这些用户设置是否已由应用程序管理或设置策略解决方案管理？ UE-V应用程序启动时应用应用程序设置，Windows登录、解锁或远程连接事件时应用应用程序设置。 如果将 UE-V其他设置共享解决方案，则用户可能会遇到不同同步设置不一致的情况。</p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>应用程序设置是否特定于计算机？ 与硬件或特定计算机配置关联的应用程序首选项和自定义项不会跨会话一致同步，并且可能导致应用程序体验不佳。</p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>应用程序是否将设置存储在 Program Files 目录或位于 <strong> 用户 </strong> [用户名] 强 &lt; &gt; AppData 强 </strong> &lt; LocalLow 目录中 &gt; </strong> 的文件目录中？ 存储在其中任一位置的应用程序数据通常不应与用户同步，因为此数据特定于计算机，或者数据太大，无法同步。</p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>应用程序是否将任何设置存储在包含不应同步的其他应用程序数据的文件中？ UE-V将文件作为一个单元进行同步。 如果设置存储在包含应用程序数据（而非设置）的文件中，则同步此其他数据可能会导致应用程序体验不佳。</p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>包含设置的文件大小如何？ 设置同步的性能可能会受大型文件的影响。 包括大文件可能会影响设置同步的性能。</p></td>
</tr>
</tbody>
</table>



## <a name="other-considerations-when-preparing-a-ue-v-deployment"></a><a href="" id="considerations"></a>准备部署部署时的其他UE-V注意事项


在准备部署以下项目时，还应考虑UE-V：

-   [管理凭据同步](#creds)

-   [Windows应用设置同步](#appxsettings)

-   [自定义UE-V设置位置模板](#custom)

-   [意外的用户设置配置](#prevent)

-   [性能和容量](#capacity)

-   [高可用性](#high)

-   [计算机时钟同步](#clocksync)

### <a name="managing-credentials-synchronization-in-ue-v-21-and-ue-v-21-sp1"></a><a href="" id="creds"></a>在 UE-V 2.1 和 UE-V 2.1 SP1 中管理凭据同步

许多企业应用程序（包括 Microsoft Outlook Lync）会提示用户在登录时输入其域凭据。 用户可以选择将其凭据保存至磁盘，以防止每次打开这些应用程序时必须输入凭据。 启用漫游凭据同步允许用户在一台计算机中保存其凭据，并避免在环境中使用的每台计算机重新输入凭据。 用户可以将某些域凭据与 UE-V 2.1 和 2.1 SP1 同步。

**重要提示**  
默认情况下，凭据同步处于禁用状态。 您必须在部署期间显式启用凭据同步才能实现此功能。



UE-V 2.1 和 2.1 SP1 可以同步企业凭据，但不要漫游仅用于本地计算机的凭据。

凭据是同步设置，这意味着它们在您首次登录计算机时应用于UE-V同步。

凭据同步由它自己的设置位置模板管理，默认情况下禁用该模板。 可以通过用于其他模板的相同方法启用或禁用此模板。 此功能的模板标识符为 RoamingCredentialSettings。

**重要提示**  
如果你在环境中使用 Active Directory 凭据漫游，建议不要启用 UE-V凭据漫游模板。



使用以下方法之一启用凭据同步：

-   公司设置中心

-   PowerShell

-   组策略

**注意**  
凭据在同步过程中加密。



[Company 设置 Center：](https://technet.microsoft.com/library/dn458903.aspx)**** Check the Roaming Credential 设置 check box under Windows 设置 to enable credential synchronization. 取消选中该框以禁用它。 如果你的帐户未配置为使用 Microsoft 帐户设置同步设置，则此复选框仅在公司中心中显示。

[PowerShell：](https://technet.microsoft.com/library/dn458937.aspx)**** 此 PowerShell cmdlet 启用凭据同步：

``` syntax
Enable-UevTemplate RoamingCredentialSettings
```

此 PowerShell cmdlet 禁用凭据同步：

``` syntax
Disable-UevTemplate RoamingCredentialSettings
```

[组策略](https://technet.microsoft.com/library/dn458893.aspx)**：** 必须 [部署最新的 MDOP ADMX 模板](https://go.microsoft.com/fwlink/p/?LinkId=393944) 才能通过组策略启用凭据同步。 凭据同步使用自定义设置Windows管理。 若要使用组策略管理此功能，请启用"同步Windows设置"策略。

1.  打开组策略编辑器并导航到用户配置 – 管理模板 **– Windows组件 – Microsoft 用户体验虚拟化**。

2.  双击同步同步Windows**设置。**

3.  如果启用此策略，则可以通过选中"漫游凭据"复选框来启用**** 凭据同步，或者通过取消选中它来禁用凭据同步。

4.  单击“确定”****。

### <a name="credential-locations-synchronized-by-ue-v"></a>由用户同步的凭据UE-V

同步应用程序保存到以下位置的凭据文件：

-   %UserProfile%\\AppData\\Roaming\\Microsoft\\Credentials\\

-   %UserProfile%\\AppData\\Roaming\\Microsoft\\Crypto\\

-   %UserProfile%\\AppData\\Roaming\\Microsoft\\Protect\\

-   %UserProfile%\\AppData\\Roaming\\Microsoft\\SystemCertificates\\

保存到其他位置的凭据不会由UE-V。

### <a name="windows-app-settings-synchronization"></a><a href="" id="appxsettings"></a>Windows应用设置同步

UE-V三Windows管理应用设置同步：

-   **同步Windows应用：** 允许或拒绝任何Windows同步

-   **Windows应用列表：** 同步应用Windows列表

-   **未列出的默认同步行为：** 确定不在Windows应用列表中的Windows同步行为。

有关详细信息，请参阅应用Windows[列表](https://technet.microsoft.com/library/dn458925.aspx#win8applist)。

### <a name="custom-ue-v-settings-location-templates"></a><a href="" id="custom"></a>自定义UE-V设置位置模板

如果要部署UE-V同步自定义应用程序的设置，将使用 UE-V 生成器为这些桌面应用程序创建自定义设置位置模板。 在测试环境中创建和测试自定义设置位置模板后，可以将设置位置模板部署到企业中的计算机。

自定义设置位置模板必须使用现有部署基础结构进行部署，如企业软件分发 (ESD) 方法（如 System Center Configuration Manager）和首选项，或者通过配置 UE-V 设置模板目录。 使用 Configuration Manager 或组策略部署的模板必须使用 WMI 或 UE-V 注册Windows PowerShell。

有关自定义设置位置模板的信息，请参阅 Deploy [UE-V 2.x for Custom Applications](deploy-ue-v-2x-for-custom-applications-new-uevv2.md)。 有关使用 Configuration Manager UE-V，请参阅[Configuring UE-V 2.x with System Center Configuration Manager 2012。](configuring-ue-v-2x-with-system-center-configuration-manager-2012-both-uevv2.md)

### <a name="prevent-unintentional-user-settings-configuration"></a><a href="" id="prevent"></a>防止意外的用户设置配置

UE-V从设置存储位置下载新的用户设置信息，并应用这些设置到以下实例中的本地计算机：

-   每次启动具有已注册模板的应用程序时UE-V模板。

-   用户登录到计算机时。

-   当用户解锁计算机时。

-   连接到已安装远程桌面计算机的UE-V。

-   运行同步控制器应用程序计划任务时。

如果UE-V在计算机 A 和计算机 B 上安装，并且希望应用程序的设置位于计算机 A 上，则计算机 A 应先打开并关闭应用程序。 如果应用程序首先在计算机 B 上打开和关闭，则计算机 A 上的应用程序设置将配置为计算机 B 上的应用程序设置。设置基于每个应用程序在计算机之间同步。 随着时间的推移，在计算机之间使用首选设置打开和关闭时，这些设置将变得一致。

此方案还适用于Windows设置。 如果Windows B 上的设置应该与计算机 A 上的 Windows 设置相同，则用户应先登录并注销计算机 A。

如果用户希望的用户设置按错误的顺序应用，则可以通过对特定应用程序或覆盖设置的计算机的 Windows 配置执行还原操作来恢复这些设置。 有关详细信息，请参阅 Manage [Administrative Backup and Restore in UE-V 2.x](manage-administrative-backup-and-restore-in-ue-v-2x-new-topic-for-21.md)。

### <a name="performance-and-capacity-planning"></a><a href="" id="capacity"></a>性能和容量规划

指定对具有UE-V磁盘容量和网络运行状况监控的数据的要求。

UE-V使用 SMB 服务器 (块) 共享来存储设置包。 设置包的大小因每个应用程序的设置信息而异。 虽然大多数设置包很小，但潜在大文件（如桌面映像）的同步可能会导致性能不佳，尤其是在网络较慢时。

若要减少网络延迟问题，在用户计算机所在的同一本地网络上创建设置存储位置。 建议每个用户为设置存储位置提供 20 MB 的磁盘空间。

默认情况下，UE-V同步在 2 秒后出现，以防止由于设置包较大而出现过多的延迟。 可以使用组策略对象来配置 SyncMethod=SyncProvider [设置](https://technet.microsoft.com/library/dn458893.aspx)。

### <a name="high-availability-for-ue-v"></a><a href="" id="high"></a>高可用性UE-V

设置UE-V位置和设置模板目录支持在任何可写共享上存储用户数据。 若要确保高可用性，请遵循以下条件：

-   使用 NTFS 文件系统格式化存储卷。

-   共享可以使用分布式文件系统 (DFS) 但存在限制。
具体来说，支持具有 (DFS-N) 分布式文件系统命名空间的分布式文件系统复制 (DFS-R) 单个目标配置。
同样，DFS-N 仅支持单个目标配置。
有关详细信息，请参阅 [Microsoft](https://go.microsoft.com/fwlink/p/?LinkId=313991) 有关复制用户配置文件数据的支持声明和有关 [DFS-R 和 DFS-N](https://support.microsoft.com/kb/2533009)部署方案的 Microsoft 支持策略的信息。

    此外，由于 SYSVOL 使用 DFS-R 进行复制，因此 SYSVOL 不能用于UE-V复制。

-   配置共享权限和 NTFS 访问控制列表 (ACL) 如部署 设置 存储[Location for UE-V 2.x](https://technet.microsoft.com/library/dn458891.aspx#ssl)中指定。

-   使用文件服务器群集和 UE-V 代理，在通信失败时提供对用户状态数据副本的访问权限。

-   你可以将设置存储路径数据存储 (群集共享) 、DFS-N 共享或两者上的用户数据以及设置模板目录模板模板。

### <a name="synchronize-computer-clocks-for-ue-v-settings-synchronization"></a><a href="" id="clocksync"></a>同步计算机时钟以UE-V设置同步

运行 UE-V 代理的计算机必须使用时间服务器来维护一致的设置体验。 UE-V使用时间戳确定是否必须从设置存储位置同步设置。 如果计算机时钟不准确，较旧的设置可能会覆盖较新的设置，或者新设置可能无法保存到设置存储位置。

## <a name="confirm-prerequisites-and-supported-configurations-for-ue-v"></a><a href="" id="prereqs"></a>确认系统必备组件和支持的配置UE-V


在继续之前，请确保你的环境包含运行 UE-V。

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
<th align="left"><strong>Service Pack</strong></th>
<th align="left"><strong>系统体系结构</strong></th>
<th align="left"><strong>Windows PowerShell</strong></th>
<th align="left"><strong>Microsoft .NET Framework</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows 7</p></td>
<td align="left"><p>Ultimate、Enterprise 或 Professional Edition</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>32 位或 64 位</p></td>
<td align="left"><p>Windows PowerShell 3.0 或更高版本</p></td>
<td align="left"><p>.NET Framework 2.1 UE-V 4.5 或更高版本。</p>
<p>.NET Framework 2.0 UE-V 4 或更高版本。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server 2008 R2</p></td>
<td align="left"><p>Standard、Enterprise、Datacenter 或 Web Server</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>64 位</p></td>
<td align="left"><p>Windows PowerShell 3.0 或更高版本</p></td>
<td align="left"><p>.NET Framework 2.1 UE-V 4.5 或更高版本。</p>
<p>.NET Framework 2.0 UE-V 4 或更高版本。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows 8 和 Windows 8.1</p></td>
<td align="left"><p>Enterprise 或 Pro</p></td>
<td align="left"><p>无</p></td>
<td align="left"><p>32 位或 64 位</p></td>
<td align="left"><p>Windows PowerShell 3.0 或更高版本</p></td>
<td align="left"><p>.NET Framework 4.5 或更高版本</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows 10，1607 以前版本</p>
<div class="alert">
<strong>注意</strong><br/><p>只有 UE-V 2.1 SP1 Windows 10 1607 之前的版本</p>
</div>
<div>

</div></td>
<td align="left"><p>Enterprise 或 Pro</p></td>
<td align="left"><p>无</p></td>
<td align="left"><p>32 位或 64 位</p></td>
<td align="left"><p>Windows PowerShell 3.0 或更高版本</p></td>
<td align="left"><p>.NET Framework 4.6</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server 2012 和 Windows Server 2012 R2</p></td>
<td align="left"><p>Standard 或 Datacenter</p></td>
<td align="left"><p>无</p></td>
<td align="left"><p>64 位</p></td>
<td align="left"><p>Windows PowerShell 3.0 或更高版本</p></td>
<td align="left"><p>.NET Framework 4.5 或更高版本</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server 2016</p></td>
<td align="left"><p>Standard 或 Datacenter</p></td>
<td align="left"><p>无</p></td>
<td align="left"><p>64 位</p></td>
<td align="left"><p>Windows PowerShell 3.0 或更高版本</p></td>
<td align="left"><p>.NET Framework 4.6 或更高版本</p></td>
</tr>
</tbody>
</table>



此外...

-   **MDOP 许可证：** 此技术是 Microsoft 桌面优化包和 MDOP (的一) 。 Enterprise客户可以通过使用 Microsoft 软件保障 获取 MDOP。 有关获取和获取 MDOP Microsoft 软件保障，请参阅如何获取 MDOP https://go.microsoft.com/fwlink/p/?LinkId=322049) (。

-   **要** 安装的任何计算机的管理凭据

**注意**  

-   从 WIndows 10 版本 1607 开始，UE-V [Windows 10 for Enterprise](https://www.microsoft.com/WindowsForBusiness/windows-for-enterprise)中不再包含 Microsoft 桌面优化包。

-   UE-V Windows PowerShell代理的 UE-V 功能要求.NET Framework 4 或更高版本Windows PowerShell 3.0 或更高版本。 在此处Windows PowerShell 3.0。 [](https://go.microsoft.com/fwlink/?LinkId=309609)

-   在.NET Framework .NET Framework 7 或 Windows Server 2008 R2 操作系统的计算机上安装 Windows 4 或 Windows 4.5。 Windows 8、Windows 8.1 和 Windows Server 2012 操作系统都安装了 .NET Framework 4.5。 The Windows 10 operating system with .NET Framework 4.6 installed.
-   强制配置文件的"删除漫游缓存"策略不受 UE-V且不应使用。



RAM 内存没有特殊的随机 (内存) 特定于UE-V。

### <a name="synchronization-of-settings-through-the-sync-provider"></a>通过设置同步提供程序进行同步

同步提供程序是用户的默认设置，用于将本地缓存与以下实例中的设置存储位置同步：

-   登录/注销

-   锁定/解锁

-   远程桌面连接/断开连接

-   应用程序打开/关闭

计划任务每 30 分钟管理一次设置同步，或者通过某些应用程序的特定触发事件管理同步。 有关详细信息，请参阅 Changing [the Frequency of UE-V 2.x Scheduled Tasks](changing-the-frequency-of-ue-v-2x-scheduled-tasks-both-uevv2.md)。

UE-V 代理同步并非始终连接到企业网络 (远程计算机和笔记本电脑) 的计算机的用户设置，以及始终连接到运行 Windows Server 并托管虚拟桌面接口 (VDI) 会话) 的网络 (计算机的用户设置。

**对于具有始终可用的连接的计算机同步：** 在始终连接到网络的计算机上使用 UE-V 时，必须使用*SyncMethod=None*参数将 UE-V 代理配置为同步设置，该参数将设置存储服务器视为标准网络共享。 在此配置中，UE-V代理配置为通知应用程序设置的导入是否延迟。

通过以下方法之一启用此配置：

-   在UE-V安装过程中，在命令提示符或批处理文件中，AgentSetup.exe*参数 SyncMethod = None*。 [部署 UE-V 2.x 代理](https://technet.microsoft.com/library/dn458891.aspx#agent)提供了详细信息。

-   安装 UE-V后，使用 System Center 2012 Configuration Manager 中的 设置 Management 功能或 MDOP ADMX 模板推送*SyncMethod = None*配置。

-   使用 Windows PowerShell 或 Windows Management Instrumentation (WMI) *设置 SyncMethod = None*配置。

    **注意**  
    这两种方法不能用于 VDI 环境中 (虚拟) 基础结构。



必须在开始同步设置之前重新启动计算机。

**注意**  
如果将 *SyncMethod 设置为 None，* 则任何设置更改都直接保存到服务器。 如果找不到与设置存储路径的网络连接，则设置更改将缓存在设备上，并同步同步提供程序下次运行时。 如果找不到设置存储路径，并且注销时用户配置文件从池 VDI 环境中删除，则设置更改将丢失，并且用户必须在计算机重新连接到设置存储路径时重新应用更改。



**外部同步引擎的同步：***SyncMethod=External*参数指定如果 UE-V 设置写入用户计算机上的本地文件夹，则任何外部同步引擎 (如 OneDrive for Business、工作文件夹、Sharepoint 或 Dropbox) 均可用于将这些设置应用到用户访问的不同计算机。

**对共享 VDI 会话的支持：UE-V** 2.1 和 2.1 SP1 支持最终用户共享的 VDI 会话。 你可以注册和配置特殊的 VDI 模板，这可确保UE-V非永久性 VDI 会话保持其所有功能不变。

**注意**  
如果未为非永久性 VDI 会话启用 VDI 模式，某些功能将不起作用，例如备份/还原和上次已知良好[ (LKG) 。 ](https://technet.microsoft.com/library/dn878331.aspx)



VDI 模板随 UE-V 2.1 和 2.1 SP1 一起提供，通常在安装后在此处提供：C：\\Program Files\\Microsoft User Experience Virtualization\\Templates\\VdiState.xml

### <a name="prerequisites-for-ue-v-generator-support"></a>生成器支持UE-V的先决条件

在UE-V自定义设置位置模板的计算机上安装该生成器。 此计算机应该能够运行其设置已同步的应用程序。 你必须是运行 管理员组 生成器软件的计算机上UE-V的成员。

必须将UE-V生成器安装在使用 NTFS 文件系统的计算机上。 the UE-V Generator software requires .NET Framework 4. 有关详细信息，请参阅部署自定义[UE-V 2.x。](deploy-ue-v-2x-for-custom-applications-new-uevv2.md)

## <a name="other-resources-for-this-product"></a>该产品的其他资源


-   [Microsoft 用户体验虚拟化 (UE-V) 2.x](index.md)

-   [UE-V 2.x 入门](get-started-with-ue-v-2x-new-uevv2.md)

-   [管理 UE-V 2.x](administering-ue-v-2x-new-uevv2.md)

-   [2.x UE-V疑难解答](troubleshooting-ue-v-2x-both-uevv2.md)

-   [UE-V 2.x 的技术参考](technical-reference-for-ue-v-2x-both-uevv2.md)














