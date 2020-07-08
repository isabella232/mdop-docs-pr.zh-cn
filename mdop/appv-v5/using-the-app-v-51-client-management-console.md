---
title: 使用 App-V 5.1 Client Management Console
description: 使用 App-V 5.1 Client Management Console
author: dansimp
ms.assetid: be6d4e35-5701-4f9a-ba8a-bede12662cf1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 63dd75395cdfef1aebae30b364f77465ba8a9882
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798250"
---
# 使用 App-V 5.1 Client Management Console


本主题提供有关如何配置和管理 Microsoft Application Virtualization （App-v）5.1 客户端的信息。

## 修改 App-v 5.1 客户端配置


App-v 5.1 客户端具有相关设置，可配置这些设置以确定客户端在你的环境中的运行方式。 可以在运行客户端的计算机上管理这些设置，也可以使用 PowerShell 或组策略管理这些设置。 有关如何使用 PowerShell 或组策略配置修改客户端的详细信息，请参阅[如何使用 Powershell 修改客户端配置](how-to-modify-client-configuration-by-using-powershell51.md)。

## <a href="" id="the-app-v-5-1-client-management-console-"></a>App-v 5.1 客户端管理控制台


你可以获取有关 App-v 5.1 客户端的信息，或使用 App-v 5.1 客户端管理控制台执行特定任务。 可以在客户端管理控制台中执行的许多任务也可以使用 PowerShell 执行。 下表中还显示了每个操作的关联 PowerShell cmdlet。 有关如何使用 PowerShell 的详细信息，请参阅[使用 Powershell 管理 app-v 5.1](administering-app-v-51-by-using-powershell.md)。

客户端管理控制台包含以下所述的主选项卡。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">选项卡</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>概述</p></td>
<td align="left"><p>" <strong> 概述 </strong> " 选项卡包含以下元素：</p>
<ul>
<li><p>更新-使用 " <strong> 更新" </strong> 磁贴刷新虚拟化的应用程序或接收新的虚拟化程序包。</p>
<p><strong>上次刷新 </strong> 显示虚拟化程序包的当前版本。</p></li>
<li><p>下载所有虚拟应用程序-使用 " <strong> 下载 </strong> " 图块下载所有预配到当前用户的程序包。</p>
<p>（关联的 PowerShell cmdlet： <strong>Mount-AppvClientPackage </strong> ）</p>
<p></p></li>
<li><p>脱机工作–使用此磁贴禁止所有自动和手动虚拟应用程序更新。</p>
<p>（关联的 PowerShell cmdlet： <strong>Set-AppvPublishServer-UserRefreshEnabled-GlobalRefreshEnabled </strong> ）</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>虚拟应用</p></td>
<td align="left"><p>" <strong> 虚拟应用 </strong> " 选项卡显示已发布给用户的所有程序包。 您也可以单击特定程序包，并查看属于该程序包的所有应用程序。 这将显示有关当前正在使用的程序包的信息以及每个程序包已下载到计算机的数量。 你还可以启动和停止程序包下载。 此外，您可以修复用户状态。 修复操作将删除与程序包相关联的所有用户数据。</p>
<p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>应用连接组</p></td>
<td align="left"><p>" <strong> 应用连接组" </strong> 选项卡显示当前用户可用的所有连接组。 单击特定的连接组以查看属于所选组的所有程序包。 这将显示有关已在使用的连接组的信息以及已下载到计算机的连接组内容的数量。 此外，你可以启动和停止连接组下载。 你可以使用此部分启动修复。 修复操作将删除所有与连接组相关联的用户状态。</p>
<p>（关联的 PowerShell cmdlet：下载- <strong>装载-AppvClientConnectionGroup </strong> 。 修复- <strong> AppvClientConnectionGroup </strong> 。）</p>
<p></p></td>
</tr>
</tbody>
</table>

 

[如何访问 Client Management Console](how-to-access-the-client-management-console51.md)

[如何将 Client 配置为从发布服务器接收程序包和连接组更新](how-to-configure-the-client-to-receive-package-and-connection-groups-updates-from-the-publishing-server-51.md)






## 相关主题


[App-V 5.1 的操作](operations-for-app-v-51.md)

 

 





