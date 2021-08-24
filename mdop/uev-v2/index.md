---
title: Microsoft 用户体验虚拟化 (UE-V) 2.x
description: Microsoft 用户体验虚拟化 (UE-V) 2.x
author: dansimp
ms.assetid: b860fed0-b846-415d-bdd6-ba60231a64be
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 04/19/2017
ms.openlocfilehash: 79748e04ae1a59afdc8f9dae3c5dc77c50e3c253
ms.sourcegitcommit: 3e0500abde44d6a09c7ac8e3caf5e25929b490a4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2021
ms.locfileid: "11910537"
---
# <a name="microsoft-user-experience-virtualization-ue-v-2x"></a>Microsoft 用户体验虚拟化 (UE-V) 2.x

>[!NOTE]
>本文档适用于 MDOP UE-V Microsoft 桌面优化包中包含的 (版本) 。 有关最新版本的 UE-V包含在 Windows 10 企业版 中，请参阅入门[UE-V。](https://docs.microsoft.com/windows/configuration/ue-v/uev-getting-started)


通过实现 2.0 或 2.1 Windows捕获和集中用户的应用程序设置Microsoft 用户体验虚拟化 (UE-V) 操作系统设置。 然后，将这些设置应用于用户在你的企业中访问的设备，如台式计算机、笔记本电脑或虚拟桌面基础结构 (VDI) 会话。

**通过UE-V，你可以...**

-   指定同步哪些应用程序和桌面设置

-   在整个企业中随时随地提供用户工作所需的设置

-   为第三方或业务线应用程序创建自定义模板

-   在硬件更换或升级之后，或在将虚拟机重置为初始状态后恢复设置

## <a name="components-of-ue-v-2x"></a>UE-V 2.x 的组件


此图显示了部署的组件UE-V组件如何协同工作以同步设置。

![uev2 体系结构图。](images/uev2archdiagram.gif)

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">组件</th>
<th align="left">函数</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>UE-V代理</strong></p></td>
<td align="left"><p>安装在需要同步设置的每台计算机上，UE-V代理会监视注册的应用程序和操作系统中是否有设置更改，然后在计算机之间 <strong> </strong> 同步这些设置。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>设置包</strong></p></td>
<td align="left"><p>应用程序设置Windows设置存储在由 UE-V 代理创建的设置 <strong> </strong> 包中。 生成、本地存储设置包，并将其复制到设置存储位置。</p>
<ul>
<li><p>桌面应用程序的 <strong> 设置 </strong> 值在用户关闭应用程序时存储。</p></li>
<li><p>用户Windows、计算机锁定或用户与计算机远程断开连接时，将存储这些设置 <strong> </strong> 的值。</p></li>
</ul>
<p>同步提供程序确定何时从程序包中读取应用程序或操作系统设置 <strong> </strong> 同步。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>设置存储位置</strong></p></td>
<td align="left"><p>这是用户可以访问的标准网络共享。 代理UE-V验证位置并创建一个隐藏的系统文件夹，用于存储和检索用户设置。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>设置位置模板</strong></p></td>
<td align="left"><p>UE-V XML 文件作为设置位置模板来监视和同步桌面应用程序设置Windows用户计算机之间的桌面设置。 默认情况下，某些设置位置模板包含在 UE-V 中。 您还可以通过管理自定义应用程序的设置同步来创建、编辑或验证自定义 <a href="#customapps" data-raw-source="[managing settings synchronization for custom applications](#customapps)"> 设置位置模板 </a> 。</p>
<div class="alert">
<strong>注意</strong><br/><p>设置应用不需要任何位置Windows模板。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Windows应用列表</strong></p></td>
<td align="left"><p>设置动态Windows应用的应用。 应用开发人员指定每个应用的同步设置。 UE-V使用Windows列表确定哪些应用程序启用了设置同步。 默认情况下，此列表包括大多数Windows应用。</p>
<p>你可以按照此处显示的过程在Windows应用程序列表中添加或删除 <a href="https://technet.microsoft.com/library/dn458925.aspx" data-raw-source="[here](https://technet.microsoft.com/library/dn458925.aspx)"> 应用程序 </a> 。</p></td>
</tr>
</tbody>
</table>



### <a name="managing-settings-synchronization-for-custom-applications"></a><a href="" id="customapps"></a>管理设置应用程序的同步

使用这些UE-V组件来创建和管理第三方或业务线应用程序的自定义模板。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>UE-V生成器</strong></p></td>
<td align="left"><p>使用 <strong> UE-V生成器 </strong> 创建自定义设置位置模板，然后你可以将其分发给用户计算机。 此外UE-V生成器还允许您编辑现有模板或验证使用另一个 XML 编辑器创建的模板。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>设置模板目录</strong></p></td>
<td align="left"><p>设置模板目录是存储自定义设置位置UE-V SMB (SMB) 共享上的文件夹 <strong> </strong> 路径。 代理UE-V检查此位置，检索新的或更新的模板，并更新其同步行为。</p>
<p>如果您仅使用默认设置UE-V模板，则不需要设置模板目录。 有关设置部署目录详细信息，请参阅配置UE-V <a href="https://technet.microsoft.com/library/dn458942.aspx#deploycatalogue" data-raw-source="[Configure a UE-V settings template catalog](https://technet.microsoft.com/library/dn458942.aspx#deploycatalogue)"> 设置模板目录 </a> 。</p></td>
</tr>
</tbody>
</table>



![ue-v 生成器进程。](images/ue-vgeneratorprocess.gif)

## <a name="settings-synchronized-by-default"></a>设置默认同步


UE-V同步这些应用程序的设置。 有关完整列表和更多详细信息，请参阅设置[部署中自动同步UE-V的信息](https://technet.microsoft.com/library/dn458932.aspx#autosyncsettings)。

Microsoft Office 2.1 SP1 和 2.1 (UE-V 2013 应用程序) 

Microsoft Office 2.1 SP1、2.1 和 2.0 (UE-V 2010 应用程序) 

Microsoft Office 2007 应用程序 (UE-V 2.0) 

Internet Explorer 8、9 和 10

Internet Explorer 2.1 SP1 和 2.1 UE-V 11

许多Windows应用程序，例如 Xbox

许多Windows桌面应用程序，例如记事本

许多Windows设置，例如桌面背景或墙纸

**注意**  
还可以自定义[自定义UE-V](https://technet.microsoft.com/library/dn458942.aspx)同步默认同步的应用程序的设置。



## <a name="compare-ue-v-to-other-microsoft-products"></a>比较UE-V Microsoft 产品


使用此表可以比较UE-V Windows 7 中的同步配置文件、同步 Windows 8 中的配置文件设置 Microsoft 帐户的同步电脑设置功能。

<table style="width:100%;">
<colgroup>
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">功能</th>
<th align="left">使用 Windows 7 同步配置文件</th>
<th align="left">使用数据库同步Windows 8</th>
<th align="left">使用数据同步Windows 10</th>
<th align="left">Microsoft 帐户</th>
<th align="left">UE-V 2.0</th>
<th align="left">UE-V 2.1 和 2.1 SP1</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>在多个计算机之间同步设置</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
</tr>
<tr class="even">
<td align="left"><p>在物理应用和虚拟应用之间同步设置</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
</tr>
<tr class="odd">
<td align="left"><p>同步Windows应用设置</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
</tr>
<tr class="even">
<td align="left"><p>通过 WMI 管理</p></td>
<td align="left"><p></p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p></p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
</tr>
<tr class="odd">
<td align="left"><p>定期同步设置更改</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
</tr>
<tr class="even">
<td align="left"><p>最低安装配置</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
</tr>
<tr class="odd">
<td align="left"><p>在未加入域的计算机上受支持</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>●</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>支持主计算机 Active Directory 属性</p></td>
<td align="left"><p></p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>在虚拟桌面基础结构与 VDI (/Remote Desktop Services) RDS (和丰富) 之间同步设置</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
</tr>
<tr class="even">
<td align="left"><p>无限制设置存储空间</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p></p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
</tr>
<tr class="odd">
<td align="left"><p>选择要同步的应用设置</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
</tr>
<tr class="even">
<td align="left"><p>IT 服务备份/还原Pro</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>部分</p></td>
<td align="left"><p>●</p></td>
</tr>
</tbody>
</table>



## <a name="ue-v-2x-release-notes"></a>UE-V2.x 发行说明


有关详细信息，以及未纳入文档的后期新闻，请参阅

-   [Microsoft 用户体验虚拟化 (UE-V) 2.1 SP1 发行说明](microsoft-user-experience-virtualization--ue-v--21-sp1-release-notes.md)

-   [Microsoft 用户体验虚拟化 (UE-V) 2.1 发行说明](microsoft-user-experience-virtualization--ue-v--21-release-notesuevv21.md)

-   [Microsoft 用户体验虚拟化 (UE-V) 2.0 发行说明](microsoft-user-experience-virtualization--ue-v--20-release-notesuevv2.md)

## <a name="other-resources-for-this-product"></a>该产品的其他资源


-   [UE-V 2.x 入门](get-started-with-ue-v-2x-new-uevv2.md)

-   [准备 UE-V 2.x 部署](prepare-a-ue-v-2x-deployment-new-uevv2.md)

-   [管理 UE-V 2.x](administering-ue-v-2x-new-uevv2.md)

-   [2.x UE-V疑难解答](troubleshooting-ue-v-2x-both-uevv2.md)

-   [UE-V 2.x 的技术参考](technical-reference-for-ue-v-2x-both-uevv2.md)

### <a name="more-information"></a>更多信息

<a href="" id="mdop-techcenter-page"></a>[MDOP TechCenter 页面](https://go.microsoft.com/fwlink/p/?LinkId=225286) 了解最新的 MDOP 信息和资源。

<a href="" id="mdop-information-experience"></a>[MDOP 信息体验](https://go.microsoft.com/fwlink/p/?LinkId=236032) 查找 MDOP 技术的文档、视频和其他资源。 您还可以向我们 [发送反馈，](mailto:MDOPDocs@microsoft.com) 或在 Facebook 或 [Twitter](https://go.microsoft.com/fwlink/p/?LinkId=242445) 上关注我们以了解 [更新](https://go.microsoft.com/fwlink/p/?LinkId=242447)。














