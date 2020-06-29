---
title: 使用 PowerShell 管理 App-V
description: 使用 PowerShell 管理 App-V
author: dansimp
ms.assetid: 1ff4686a-1e19-4eff-b648-ada091281094
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0e7f9171e0ac5589d8f1935e715dfdb9c349192d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798651"
---
# 使用 PowerShell 管理 App-V


Microsoft Application Virtualization （App-v）5.0 提供 Windows PowerShell cmdlet，此 cmdlet 可帮助管理员执行各种应用 V 5.0 任务。 以下部分提供了有关将 PowerShell 与 App-v 5.0 结合使用的详细信息。

## 如何使用 PowerShell 管理 app-v 5。0


使用以下 PowerShell 过程执行各种应用程序 V 5.0 任务。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">名称</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><a href="how-to-load-the-powershell-cmdlets-and-get-cmdlet-help-50-sp3.md" data-raw-source="[How to Load the PowerShell Cmdlets and Get Cmdlet Help](how-to-load-the-powershell-cmdlets-and-get-cmdlet-help-50-sp3.md)">如何加载 PowerShell Cmdlet 和获取 Cmdlet 帮助</a></p></td>
<td align="left"><p>介绍如何安装 PowerShell cmdlet 和查找 cmdlet 帮助和示例。</p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md" data-raw-source="[How to Manage App-V 5.0 Packages Running on a Stand-Alone Computer by Using PowerShell](how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md)">如何使用 PowerShell 管理在独立计算机上运行的 App-V 5.0 程序包</a></p></td>
<td align="left"><p>介绍如何使用 PowerShell 管理独立计算机上的客户端程序包生命周期。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="how-to-manage-connection-groups-on-a-stand-alone-computer-by-using-powershell.md" data-raw-source="[How to Manage Connection Groups on a Stand-alone Computer by Using PowerShell](how-to-manage-connection-groups-on-a-stand-alone-computer-by-using-powershell.md)">如何使用 PowerShell 管理独立计算机上的连接组</a></p></td>
<td align="left"><p>介绍如何使用 PowerShell 管理连接组。</p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="how-to-modify-client-configuration-by-using-powershell.md" data-raw-source="[How to Modify Client Configuration by Using PowerShell](how-to-modify-client-configuration-by-using-powershell.md)">如何使用 PowerShell 修改客户端配置</a></p></td>
<td align="left"><p>介绍如何使用 PowerShell 修改客户端。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="how-to-apply-the-user-configuration-file-by-using-powershell.md" data-raw-source="[How to Apply the User Configuration File by Using PowerShell](how-to-apply-the-user-configuration-file-by-using-powershell.md)">如何使用 PowerShell 应用用户配置文件</a></p></td>
<td align="left"><p>介绍如何使用 PowerShell 应用用户配置文件。</p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="how-to-apply-the-deployment-configuration-file-by-using-powershell.md" data-raw-source="[How to Apply the Deployment Configuration File by Using PowerShell](how-to-apply-the-deployment-configuration-file-by-using-powershell.md)">如何使用 PowerShell 应用部署配置文件</a></p></td>
<td align="left"><p>介绍如何使用 PowerShell 应用部署配置文件。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="how-to-sequence-a-package--by-using-powershell-50.md" data-raw-source="[How to Sequence a Package by Using PowerShell](how-to-sequence-a-package--by-using-powershell-50.md)">如何使用 PowerShell 对程序包进行排序</a></p></td>
<td align="left"><p>介绍如何使用 PowerShell 创建新的程序包。</p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="how-to-create-a-package-accelerator-by-using-powershell.md" data-raw-source="[How to Create a Package Accelerator by Using PowerShell](how-to-create-a-package-accelerator-by-using-powershell.md)">如何使用 PowerShell 创建包加速器</a></p></td>
<td align="left"><p>介绍如何使用 PowerShell 创建程序包加速器。 可以使用程序包加速器自动序列大型、复杂的应用程序。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="how-to-enable-reporting-on-the-app-v-50-client-by-using-powershell.md" data-raw-source="[How to Enable Reporting on the App-V 5.0 Client by Using PowerShell](how-to-enable-reporting-on-the-app-v-50-client-by-using-powershell.md)">如何使用 PowerShell 在 App-V 5.0 Client 上启用报告</a></p></td>
<td align="left"><p>介绍如何启用运行 App-v 5.0 的计算机发送报告信息。</p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="how-to-install-the-app-v-databases-and-convert-the-associated-security-identifiers--by-using-powershell.md" data-raw-source="[How to Install the App-V Databases and Convert the Associated Security Identifiers by Using PowerShell](how-to-install-the-app-v-databases-and-convert-the-associated-security-identifiers--by-using-powershell.md)">如何使用 PowerShell 安装 app-v 数据库并转换关联的安全标识符</a></p></td>
<td align="left"><p>介绍如何获取帐户名称数组并将每个帐户名称转换为标准和十六进制格式的相应 SID。</p></td>
</tr>
</tbody>
</table>

 

## PowerShell 错误处理


有关 App-v 5.0 PowerShell 错误处理的信息，请使用下表。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">事件</th>
<th align="left">操作</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>将 RollbackOnError 属性与嵌入式脚本结合使用</p></td>
<td align="left"><p>将 <strong> RollbackOnError </strong> 属性与嵌入式脚本配合使用时，将忽略以下事件的属性：</p>
<ul>
<li><p>删除程序包</p></li>
<li><p>取消发布程序包</p></li>
<li><p>终止虚拟环境</p></li>
<li><p>终止进程</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>程序包名称包含<strong>$</strong></p></td>
<td align="left"><p>如果程序包名称包含字符（ <strong> $ </strong> ），则必须使用单引号（ <strong> ' </strong> ），例如</p>
<p><strong>AppvClientPackage "Contoso $ 应用 appv"</strong></p></td>
</tr>
</tbody>
</table>

 






## 相关主题


[App-V 5.0 的操作](operations-for-app-v-50.md)

 

 





