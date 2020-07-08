---
title: Microsoft 用户体验虚拟化（UE-V） 2. x
description: Microsoft 用户体验虚拟化（UE-V） 2. x
author: dansimp
ms.assetid: b860fed0-b846-415d-bdd6-ba60231a64be
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 04/19/2017
ms.openlocfilehash: 573b8bb2027e5c7f117a8254005a43c656f047a9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10795567"
---
# Microsoft 用户体验虚拟化（UE-V） 2. x

>[!NOTE]
>本文档是 Microsoft 桌面优化包（MDOP）中包含的 ue-v 版本的 ue-v。 有关 Windows 10 企业版中包含的最新 UE-V 版本的信息，请参阅[从 Ue-v 开始](https://docs.microsoft.com/windows/configuration/ue-v/uev-getting-started)。


通过实现 Microsoft 用户体验虚拟化（UE-V）2.0 或2.1 来捕获和集中你的用户的应用程序设置和 Windows 操作系统设置。 然后，将这些设置应用于您的企业中的用户访问的设备，如台式计算机、笔记本电脑或虚拟桌面基础结构（VDI）会话。

**通过 UE-V，您可以 .。。**

-   指定要同步的应用程序和桌面设置

-   在整个企业中随时随地提供用户工作所需的设置

-   为第三方或业务线应用程序创建自定义模板

-   在硬件更换或升级后或将虚拟机重置为其初始状态之后恢复设置

## UE-V 2 的组件


此图显示了部署的 UE-V 组件如何协同工作以同步设置。

![uev2 体系结构图表](images/uev2archdiagram.gif)

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
<td align="left"><p><strong>UE-V Agent</strong></p></td>
<td align="left"><p>在需要同步设置的每台计算机上安装时， <strong> Ue-v Agent 将 </strong> 监视已注册的应用程序和操作系统以了解任何设置更改，然后在计算机之间同步这些设置。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>设置程序包</strong></p></td>
<td align="left"><p>应用程序设置和 Windows 设置存储在 <strong> </strong> 由 ue-v Agent 创建的设置包中。 生成、本地存储设置包，并将其复制到设置存储位置。</p>
<ul>
<li><p><strong> </strong> 当用户关闭应用程序时，将存储桌面应用程序的设置值。</p></li>
<li><p>在 <strong> </strong> 用户注销、计算机锁定或用户从计算机远程断开连接时，将存储 Windows 设置的值。</p></li>
</ul>
<p>同步提供程序确定何时从设置程序包中读取应用程序或操作系统设置 <strong> 并进行 </strong> 同步。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>设置存储位置</strong></p></td>
<td align="left"><p>这是您的用户可以访问的标准网络共享。 UE-V Agent 验证位置并创建一个隐藏的系统文件夹，用于存储和检索用户设置。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>设置位置模板</strong></p></td>
<td align="left"><p>UE-V 将 XML 文件用作设置位置模板，用于监视和同步用户计算机之间的桌面应用程序设置和 Windows 桌面设置。 默认情况下，UE-V 中包含某些设置位置模板。 您也可以通过 <a href="#customapps" data-raw-source="[managing settings synchronization for custom applications](#customapps)"> 管理自定义应用程序的设置同步来创建、编辑或验证自定义设置位置模板 </a> 。</p>
<div class="alert">
<strong>注意</strong><br/><p>Windows 应用不需要设置位置模板。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Windows 应用列表</strong></p></td>
<td align="left"><p>已捕获和动态应用 Windows 应用的设置。 应用开发人员指定为每个应用同步的设置。 UE-V 使用应用的托管列表确定启用了设置同步的 Windows 应用。 默认情况下，此列表包含大多数 Windows 应用。</p>
<p>你可以按照此处所示的过程在 Windows 应用列表中添加或删除应用程序 <a href="https://technet.microsoft.com/library/dn458925.aspx" data-raw-source="[here](https://technet.microsoft.com/library/dn458925.aspx)"> </a> 。</p></td>
</tr>
</tbody>
</table>



### <a href="" id="customapps"></a>管理自定义应用程序的设置同步

使用这些 UE-V 组件创建和管理第三方或业务线应用程序的自定义模板。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>UE-V 发电机</strong></p></td>
<td align="left"><p>使用 <strong> Ue-v 生成器 </strong> 创建自定义设置位置模板，然后您可以将这些模板分发给用户计算机。 UE-V 生成器还允许你编辑现有模板或验证使用另一个 XML 编辑器创建的模板。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>设置模板目录</strong></p></td>
<td align="left"><p><strong>设置模板目录 </strong> 是 ue-v 计算机上的文件夹路径或存储自定义设置位置模板的服务器消息块（SMB）网络共享。 UE-V Agent 每天检查此位置，检索新的或更新的模板，并更新其同步行为。</p>
<p>如果仅使用 UE-V 默认设置位置模板，则不需要设置模板目录。 有关设置部署目录的详细信息，请参阅 <a href="https://technet.microsoft.com/library/dn458942.aspx#deploycatalogue" data-raw-source="[Configure a UE-V settings template catalog](https://technet.microsoft.com/library/dn458942.aspx#deploycatalogue)"> 配置 ue-v 设置模板目录 </a> 。</p></td>
</tr>
</tbody>
</table>



![ue-v 发电机进程](images/ue-vgeneratorprocess.gif)

## 默认同步的设置


Ue-v 默认情况下，ue-v 同步这些应用程序的设置。 有关完整列表和更多详细信息，请参阅[在 ue-v 部署中自动同步的设置](https://technet.microsoft.com/library/dn458932.aspx#autosyncsettings)。

Microsoft Office 2013 应用程序（UE-V 2.1 SP1 和2.1）

Microsoft Office 2010 应用程序（UE-V 2.1 SP1、2.1 和2.0）

Microsoft Office 2007 应用程序（仅限 UE-V 2.0）

Internet Explorer 8、9和10

UE-V 2.1 SP1 和2.1 中的 Internet Explorer 11

许多 Windows 应用程序（如 Xbox）

许多 Windows 桌面应用程序（如记事本）

许多 Windows 设置，如桌面背景或墙纸

**注意**  
你还可以[自定义 ue-v，以便同步](https://technet.microsoft.com/library/dn458942.aspx)除默认情况下同步的应用程序的设置。



## 将 UE-V 与其他 Microsoft 产品进行比较


使用此表比较 UE-V 以在 Windows 7 中同步配置文件、在 Windows 8 中同步配置文件，以及 Microsoft 帐户的同步电脑设置功能。

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
<th align="left">使用 Windows 8 同步配置文件</th>
<th align="left">使用 Windows 10 同步配置文件</th>
<th align="left">Microsoft 帐户</th>
<th align="left">UE-V 2。0</th>
<th align="left">UE-V 2.1 和 2.1 SP1</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>同步多台计算机之间的设置</p></td>
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
<td align="left"><p>同步 Windows 应用设置</p></td>
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
<td align="left"><p>设置的最低配置</p></td>
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
<td align="left"><p>同步虚拟桌面基础结构（VDI）/Remote 桌面服务（RDS）和丰富桌面之间的设置</p></td>
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
<td align="left"><p>要同步的应用设置的选择</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
</tr>
<tr class="even">
<td align="left"><p>IT 专业人员的备份/恢复</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>部分</p></td>
<td align="left"><p>●</p></td>
</tr>
</tbody>
</table>



## UE-V 2. x 发行说明


有关详细信息，以及未使其进入文档的最新消息，请参阅

-   [Microsoft 用户体验虚拟化 (UE-V) 2.1 SP1 发行说明](microsoft-user-experience-virtualization--ue-v--21-sp1-release-notes.md)

-   [Microsoft 用户体验虚拟化 (UE-V) 2.1 发行说明](microsoft-user-experience-virtualization--ue-v--21-release-notesuevv21.md)

-   [Microsoft 用户体验虚拟化 (UE-V) 2.0 发行说明](microsoft-user-experience-virtualization--ue-v--20-release-notesuevv2.md)

## 此产品的其他资源


-   [UE-V 2.x 入门](get-started-with-ue-v-2x-new-uevv2.md)

-   [准备 UE-V 2. x 部署](prepare-a-ue-v-2x-deployment-new-uevv2.md)

-   [管理 UE-V 2. x](administering-ue-v-2x-new-uevv2.md)

-   [解决 UE-V 2. x](troubleshooting-ue-v-2x-both-uevv2.md)

-   [UE-V 2.x 的技术参考](technical-reference-for-ue-v-2x-both-uevv2.md)

### 详细信息

<a href="" id="mdop-techcenter-page"></a>[MDOP 技术中心页](https://go.microsoft.com/fwlink/p/?LinkId=225286)了解最新的 MDOP 信息和资源。

<a href="" id="mdop-information-experience"></a>[MDOP 信息体验](https://go.microsoft.com/fwlink/p/?LinkId=236032)查找 MDOP 技术的文档、视频和其他资源。 您还可以在[Facebook](https://go.microsoft.com/fwlink/p/?LinkId=242445)或[Twitter](https://go.microsoft.com/fwlink/p/?LinkId=242447)上关注我们，[向我们发送反馈](mailto:MDOPDocs@microsoft.com)或了解更新。














