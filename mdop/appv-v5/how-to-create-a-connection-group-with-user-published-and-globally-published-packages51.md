---
title: 如何创建与用户发布和全局发布的程序包的连接组
description: 如何创建与用户发布和全局发布的程序包的连接组
author: dansimp
ms.assetid: 851b8742-0283-4aa6-b3a3-f7f6289824c3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/01/2016
ms.openlocfilehash: 230e687360920c05a214624750eba54dc84b5731
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798527"
---
# 如何创建与用户发布和全局发布的程序包的连接组


你可以使用以下两种方法之一创建包含用户发布和全局发布的程序包的用户具有标题的连接组：

-   [如何使用 PowerShell cmdlet 创建用户有资格的连接组](#bkmk-posh-userentitled-cg)

-   [如何使用 App-v 服务器创建用户有资格的连接组](#bkmk-appvserver-userentitled-cg)

**开始之前应了解的事项：**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">不受支持的方案和潜在问题</th>
<th align="left">结果</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>您不能在具有标题的连接组中包含用户发布的程序包。</p></td>
<td align="left"><p>连接组将失败。</p></td>
</tr>
<tr class="even">
<td align="left"><p>如果你在全局范围内发布程序包，然后创建用户发布的连接组（你已将该程序包设置为非可选），仍可以运行 <strong> 取消发布-AppvClientPackage &lt; 包 &gt; -全局 </strong> 来取消发布程序包，即使该程序包正在另一连接组中使用也是如此。</p></td>
<td align="left"><p>如果任何其他连接组正在使用该程序包，则该程序包将在这些连接组中失败。</p>
<p>为了避免无意间取消发布在其他连接组中使用的非可选程序包，我们建议你跟踪已使用非可选程序包的连接组。</p></td>
</tr>
</tbody>
</table>

<a href="" id="bkmk-posh-userentitled-cg"></a>**如何使用 PowerShell cmdlet 创建用户有资格的连接组**

1.  使用以下命令添加和发布程序包：

    **Add-AppvClientPackage Package1 \ _AppV \ _file \ _Path**

    **Add-AppvClientPackage Package2 \ _AppV \ _file \ _Path**

    **AppvClientPackage-PackageId ID-Global _Version _ID Package1**

    **Publish-AppvClientPackage-PackageId Package2 \ _ID-VersionIdPackage2 \ _ID**

2.  创建连接组 XML 文件。 有关详细信息，请参阅[关于连接组文件](about-the-connection-group-file51.md)。

3.  使用以下命令添加和发布连接组：

    **AppvClientConnectionGroup 连接 \ _Group \ _XML \ _file \ _Path**

    **Enable-AppvClientConnectionGroup-GroupId cg \ _Group \ _ID-VersionId CG \ _Version \ _ID**

<a href="" id="bkmk-appvserver-userentitled-cg"></a>**如何使用 App-v 服务器创建用户有资格的连接组**

1.  打开 app-v 5.1 管理控制台。

2.  按照[如何发布程序包的说明，使用管理控制台](how-to-publish-a-package-by-using-the-management-console-51.md)全局发布程序包和向用户发布程序包。

3.  按照[如何创建连接组](how-to-create-a-connection-group51.md)以创建连接组的说明进行操作，并添加用户发布和全局发布的程序包。

    已**获得有关 app-v 的建议**？ 在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。 **遇到了 app-v 问题？** 使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相关主题


[管理连接组](managing-connection-groups51.md)

[如何使用连接组中的可选程序包](how-to-use-optional-packages-in-connection-groups51.md)

 

 





