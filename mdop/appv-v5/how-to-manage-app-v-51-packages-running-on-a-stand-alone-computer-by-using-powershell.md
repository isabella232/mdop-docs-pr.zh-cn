---
title: 如何使用 PowerShell 管理在独立计算机上运行的 App-V 5.1 程序包
description: 如何使用 PowerShell 管理在独立计算机上运行的 App-V 5.1 程序包
author: dansimp
ms.assetid: c3fd06f6-102f-43d1-a577-d5ced6ac537d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: b454014da4e5f349af913d3fea8ea3837598a039
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798415"
---
# 如何使用 PowerShell 管理在独立计算机上运行的 App-V 5.1 程序包


以下各部分介绍了如何使用 PowerShell 在独立客户端计算机上执行各种管理任务：

-   [返回程序包列表](#bkmk-return-pkgs-standalone-posh)

-   [添加程序包](#bkmk-add-pkgs-standalone-posh)

-   [发布程序包](#bkmk-pub-pkg-standalone-posh)

-   [将程序包发布到特定用户](#bkmk-pub-pkg-a-user-standalone-posh)

-   [添加和发布程序包](#bkmk-add-pub-pkg-standalone-posh)

-   [取消发布现有程序包](#bkmk-unpub-pkg-standalone-posh)

-   [取消发布特定用户的程序包](#bkmk-unpub-pkg-specfc-use)

-   [删除现有程序包](#bkmk-remove-pkg-standalone-posh)

-   [仅允许管理员发布或取消发布程序包](#bkmk-admins-pub-pkgs)

-   [了解挂起程序包（UserPending 和 GlobalPending）](#bkmk-understd-pend-pkgs)

## <a href="" id="bkmk-return-pkgs-standalone-posh"></a>返回程序包列表


使用以下信息返回有权使用特定用户的程序包的列表：

**Cmdlet**： AppvClientPackage

**参数**：-Name-Version-PackageID-VersionID

**示例**： AppvClientPackage-Name "ContosoApplication"-版本2

## <a href="" id="bkmk-add-pkgs-standalone-posh"></a>添加程序包


使用以下信息将程序包添加到计算机。

**重要提示** 此示例仅添加程序包。 它不会将程序包发布给用户或计算机。

 

**Cmdlet**： Add-AppvClientPackage

**示例**： $Contoso = Add-AppvClientPackage \\\\path\\to\\appv\\package.appv

## <a href="" id="bkmk-pub-pkg-standalone-posh"></a>发布程序包


使用以下信息将已添加到特定用户或全局的程序包发布到计算机上的任何用户。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">发布方法</th>
<th align="left">Cmdlet 和示例</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>发布到用户</p></td>
<td align="left"><p><strong>Cmdlet </strong> ： Publish-AppvClientPackage</p>
<p><strong>示例 </strong> ： Publish-AppvClientPackage "ContosoApplication"</p></td>
</tr>
<tr class="even">
<td align="left"><p>全球发布</p></td>
<td align="left"><p><strong>Cmdlet </strong> ： Publish-AppvClientPackage</p>
<p><strong>示例 </strong> ： Publish-AppvClientPackage "ContosoApplication"-Global</p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-pub-pkg-a-user-standalone-posh"></a>将程序包发布到特定用户


**注意** 必须使用 App-v 5.0 SP2 修补程序包5或更高版本才能使用此参数。

 

管理员可以通过使用**AppvClientPackage** cmdlet 指定可选 **– UserSID**参数来将程序包发布到特定用户，其中 **-UserSID**表示最终用户的安全标识符（SID）。

要使用此参数，请执行以下操作：

-   你可以从用户或管理员会话运行此 cmdlet。

-   必须使用管理凭据登录才能使用该参数。

-   最终用户必须登录。

-   您必须提供最终用户的安全标识符（SID）。

**Cmdlet**： Publish-AppvClientPackage

**示例**： Publish-AppvClientPackage "ContosoApplication"-UserSID S-1-2-34-56789012-3456789012-345678901-2345

## <a href="" id="bkmk-add-pub-pkg-standalone-posh"></a>添加和发布程序包


使用以下信息将程序包添加到计算机并将其发布给用户。

**Cmdlet**： Add-AppvClientPackage

**示例**： Add-AppvClientPackage \\\\path\\to\\appv\\package.appv |发布-AppvClientPackage

## <a href="" id="bkmk-unpub-pkg-standalone-posh"></a>取消发布现有程序包


使用以下信息取消发布已获得用户资格但不从计算机中删除程序包的程序包。

**Cmdlet**：取消发布-AppvClientPackage

**示例**：取消发布-AppvClientPackage "ContosoApplication"

## <a href="" id="bkmk-unpub-pkg-specfc-use"></a>取消发布特定用户的程序包


**注意** 必须使用 App-v 5.0 SP2 修补程序包5或更高版本才能使用此参数。

 

管理员可以通过将 optional- **UserSID**参数与**AppvClientPackage** cmdlet 一起使用可选的- **UserSID**表示最终用户的安全标识符（SID）来取消发布特定用户的程序包。

要使用此参数，请执行以下操作：

-   你可以从用户或管理员会话运行此 cmdlet。

-   必须使用管理凭据登录才能使用该参数。

-   最终用户必须登录。

-   您必须提供最终用户的安全标识符（SID）。

**Cmdlet**：取消发布-AppvClientPackage

**示例**：取消发布-AppvClientPackage "ContosoApplication"-UserSID S-1-2-34-56789012-3456789012-345678901-2345

## <a href="" id="bkmk-remove-pkg-standalone-posh"></a>删除现有程序包


使用以下信息从计算机中删除程序包。

**Cmdlet**： Remove-AppvClientPackage

**示例**： Remove-AppvClientPackage "ContosoApplication"

**注意** 对于前面示例的变量，已将 app-v cmdlet 分配给变量，仅供你明确使用;不要求赋值。 大多数 cmdlet 可以合并为中显示的，[以添加和发布程序包](#bkmk-add-pub-pkg-standalone-posh)。 有关详细教程，请参阅[App-V 5.0 客户端 PowerShell 深入](https://go.microsoft.com/fwlink/?LinkId=324466)了解。

 

## <a href="" id="bkmk-admins-pub-pkgs"></a>仅允许管理员发布或取消发布程序包


**注意** 
**从 app-v 5.0 SP3 开始，支持此功能。**

 

使用以下 cmdlet 和参数以仅允许管理员（而非最终用户）发布或取消发布程序包：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>Cmdlet</strong></p></td>
<td align="left"><p>Set-AppvClientConfiguration</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>参数</strong></p></td>
<td align="left"><p>-RequirePublishAsAdmin</p>
<p>参数值：</p>
<ul>
<li><p>0-假</p></li>
<li><p>1-True</p></li>
</ul>
<p><strong>示例： </strong> ： Set-AppvClientConfiguration-RequirePublishAsAdmin1</p></td>
</tr>
</tbody>
</table>

 

若要使用 App-v 管理控制台设置此配置，请参阅[如何使用管理控制台发布程序包](how-to-publish-a-package-by-using-the-management-console-51.md)。

## <a href="" id="bkmk-understd-pend-pkgs"></a>了解挂起程序包（UserPending 和 GlobalPending）


**从 app-v 5.0 SP2 开始**：如果你运行的 PowerShell cmdlet 影响当前正在使用的程序包，你尝试执行的任务将置于挂起状态。 例如，如果你尝试在使用该程序包中的应用程序时发布程序包，然后运行**AppvClientPackage**，则会在 cmdlet 输出中显示挂起状态，如下所示：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Cmdlet 输出项目</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>UserPending</p></td>
<td align="left"><p>指示列出的程序包是否有正在应用于用户的挂起任务：</p>
<ul>
<li><p>True</p></li>
<li><p>False</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>GlobalPending</p></td>
<td align="left"><p>指示列出的程序包是否具有正在全局应用于计算机的挂起任务：</p>
<ul>
<li><p>True</p></li>
<li><p>False</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

根据以下规则，待决任务将在以后运行：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">任务类型</th>
<th align="left">适用规则</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>基于用户的任务，例如将程序包发布给用户</p></td>
<td align="left"><p>将在用户注销后执行挂起的任务，然后重新登录。</p></td>
</tr>
<tr class="even">
<td align="left"><p>基于全球的任务，例如，全局启用连接组</p></td>
<td align="left"><p>当计算机关闭然后重新启动时，将执行挂起的任务。</p></td>
</tr>
</tbody>
</table>

 

有关挂起任务的详细信息，请参阅[关于 App-V 5.0 SP2](about-app-v-50-sp2.md#bkmk-pkg-upgr-pendg-tasks)。

已**获得有关 app-v 的建议**？ 在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。 **遇到了 app-v 问题？** 使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相关主题


[App-V 5.1 的操作](operations-for-app-v-51.md)

[使用 PowerShell 管理 App-V 5.1](administering-app-v-51-by-using-powershell.md)

 

 





