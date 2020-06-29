---
title: 如何加载 PowerShell Cmdlet 和获取 Cmdlet 帮助
description: 如何加载 PowerShell Cmdlet 和获取 Cmdlet 帮助
author: dansimp
ms.assetid: 0624495b-943e-485b-9e54-b50e4ee6591c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/02/2016
ms.openlocfilehash: 7692d3e36aabc4f3142f664e94d9d71b2cfc1bd3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798425"
---
# 如何加载 PowerShell Cmdlet 和获取 Cmdlet 帮助


本主题包含的内容：

-   [使用 PowerShell cmdlet 的要求](#bkmk-reqs-using-posh)

-   [加载 PowerShell cmdlet](#bkmk-load-cmdlets)

-   [获取有关 PowerShell cmdlet 的帮助](#bkmk-get-cmdlet-help)

-   [显示 PowerShell cmdlet 的帮助](#bkmk-display-help-cmdlet)

## <a href="" id="bkmk-reqs-using-posh"></a>使用 PowerShell cmdlet 的要求


查看有关使用 app-v PowerShell cmdlet 的以下要求：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">要求</th>
<th align="left">详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>仅当用户通过使用以下方法之一授予访问权限时，用户才可以运行 app-v 服务器 cmdlet：</p></td>
<td align="left"><ul>
<li><p><strong>部署和配置 App-v 服务器时 </strong> ：</p>
<p>指定具有管理 App-v 环境的权限的 Active Directory 组或单个用户。 请参阅 <a href="how-to-deploy-the-app-v-50-server-50sp3.md" data-raw-source="[How to Deploy the App-V 5.0 Server](how-to-deploy-the-app-v-50-server-50sp3.md)"> 如何部署 app-v 5.0 服务器 </a> 。</p></li>
<li><p><strong>在部署 app-v 服务器之后 </strong> ：</p>
<p>使用 app-v 管理控制台添加其他 Active Directory 组或用户。 请参阅 <a href="how-to-add-or-remove-an-administrator-by-using-the-management-console.md" data-raw-source="[How to Add or Remove an Administrator by Using the Management Console](how-to-add-or-remove-an-administrator-by-using-the-management-console.md)"> 如何使用管理控制台添加或删除管理员 </a> 。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>需要提升的命令提示符的 cmdlet</p></td>
<td align="left"><ul>
<li><p>Add-AppvClientPackage</p></li>
<li><p>Remove-AppvClientPackage</p></li>
<li><p>Set-AppvClientConfiguration</p></li>
<li><p>Add-AppvClientConnectionGroup</p></li>
<li><p>Remove-AppvClientConnectionGroup</p></li>
<li><p>Add-AppvPublishingServer</p></li>
<li><p>Remove-AppvPublishingServer</p></li>
<li><p>Send-AppvClientReport</p></li>
<li><p>Set-AppvClientMode</p></li>
<li><p>Set-AppvClientPackage</p></li>
<li><p>Set-AppvPublishingServer</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>最终用户可以运行的 cmdlet，除非将其配置为需要提升的命令提示符</p></td>
<td align="left"><ul>
<li><p>发布-AppvClientPackage</p></li>
<li><p>取消发布-AppvClientPackage</p></li>
</ul>
<p>若要将这些 cmdlet 配置为需要提升的命令提示符，请使用以下方法之一：</p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">方法</th>
<th align="left">更多资源</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong> </strong> 通过 <strong> -RequirePublishAsAdmin 参数运行 AppvClientConfiguration cmdlet </strong> 。</p></td>
<td align="left"><ul>
<li><p><a href="how-to-manage-connection-groups-on-a-stand-alone-computer-by-using-powershell.md#bkmk-admin-only-posh-topic-cg" data-raw-source="[How to Manage Connection Groups on a Stand-alone Computer by Using PowerShell](how-to-manage-connection-groups-on-a-stand-alone-computer-by-using-powershell.md#bkmk-admin-only-posh-topic-cg)">如何使用 PowerShell 管理独立计算机上的连接组</a></p></li>
<li><p><a href="how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md" data-raw-source="[How to Manage App-V 5.0 Packages Running on a Stand-Alone Computer by Using PowerShell](how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md)">如何使用 PowerShell 管理在独立计算机上运行的 App-V 5.0 程序包</a></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>对 App-v 客户端启用 "要求发布为管理员" 组策略设置。</p></td>
<td align="left"><p><a href="how-to-publish-a-package-by-using-the-management-console-50.md" data-raw-source="[How to Publish a Package by Using the Management Console](how-to-publish-a-package-by-using-the-management-console-50.md)">如何使用管理控制台发布程序包</a> </p></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-load-cmdlets"></a>加载 PowerShell cmdlet
要加载 PowerShell cmdlet 模块，请执行以下操作：

1.  打开 Windows PowerShell 或 Windows PowerShell 集成脚本环境（ISE）。

2.  键入以下命令之一，为所需的模块加载 cmdlet：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">App-v 组件</th>
<th align="left">要键入的命令</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>App-v 服务器</p></td>
<td align="left"><p>导入-模块 AppvServer</p></td>
</tr>
<tr class="even">
<td align="left"><p>App-v 排序器</p></td>
<td align="left"><p>导入-模块 AppvSequencer</p></td>
</tr>
<tr class="odd">
<td align="left"><p>App-v 客户端</p></td>
<td align="left"><p>导入-模块 AppvClient</p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-get-cmdlet-help"></a>获取有关 PowerShell cmdlet 的帮助
从 app-v 5.0 SP3 开始，cmdlet 帮助有两种格式：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">格式</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>作为可下载的模块</p></td>
<td align="left"><p>下载 cmdlet 模块后下载最新帮助：</p>
<ol>
<li><p>打开 Windows PowerShell 或 Windows PowerShell 集成脚本环境（ISE）。</p></li>
<li><p>键入以下命令之一，为所需的模块加载 cmdlet：</p></li>
</ol>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">App-v 组件</th>
<th align="left">要键入的命令</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>App-v 服务器</p></td>
<td align="left"><p>Update-Help-Module AppvServer</p></td>
</tr>
<tr class="even">
<td align="left"><p>App-v 排序器</p></td>
<td align="left"><p>Update-Help-Module AppvSequencer</p></td>
</tr>
<tr class="odd">
<td align="left"><p>App-v 客户端</p></td>
<td align="left"><p>Update-Help-Module AppvClient</p></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
<tr class="even">
<td align="left"><p>在 TechNet 上作为网页</p></td>
<td align="left"><p>在 <a href="https://technet.microsoft.com/library/dn520245.aspx" data-raw-source="[Microsoft Desktop Optimization Pack Automation with Windows PowerShell](https://technet.microsoft.com/library/dn520245.aspx)"> Windows PowerShell 的 Microsoft 桌面优化包自动化下，查看 app-v 节点 </a> 。</p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-display-help-cmdlet"></a>显示 PowerShell cmdlet 的帮助
若要显示特定 PowerShell cmdlet 的帮助，请执行以下操作：

1.  打开 Windows PowerShell 或 Windows PowerShell 集成脚本环境（ISE）。

2.  输入**get-help** &lt; *cmdlet* &gt; ，例如， **get-help AppvClientPackage**。

已**获得有关 app-v 的建议**？ 在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。 遇到**了 app-v 问题**？ 使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

 

 





