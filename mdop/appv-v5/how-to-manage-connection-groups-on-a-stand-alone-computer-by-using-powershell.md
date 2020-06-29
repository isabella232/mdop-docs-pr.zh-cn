---
title: 如何使用 PowerShell 管理独立计算机上的连接组
description: 如何使用 PowerShell 管理独立计算机上的连接组
author: dansimp
ms.assetid: b73ae74d-8a6f-4bb3-b1f2-0067c7bd5212
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/01/2016
ms.openlocfilehash: 32dd4f9c5ad1ba4ae9e25246d5ec52a6363ef303
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798417"
---
# 如何使用 PowerShell 管理独立计算机上的连接组


App-v 连接组允许你将所有虚拟应用程序作为单个虚拟环境中定义的程序包集运行。 例如，你可以使用单独的程序包虚拟化应用程序及其插件，但将它们一起运行在单个连接组中。

连接组 XML 文件定义在安装了 App-v 客户端的计算机上运行的连接组。 有关连接组 XML 文件以及如何配置它的信息，请参阅[关于连接组文件](about-the-connection-group-file.md)。

本主题介绍下列过程：

-   [在连接组中添加和发布 app-v 程序包](#bkmk-add-pub-pkgs-in-cg)

-   [在 App-v 客户端上添加和启用连接组](#bkmk-add-enable-cg-on-clt)

-   [为特定用户启用或禁用连接组](#bkmk-enable-cg-for-user-poshtopic)

-   [仅允许管理员启用连接组](#bkmk-admin-only-posh-topic-cg)

<a href="" id="bkmk-add-pub-pkgs-in-cg"></a>**在连接组中添加和发布 app-v 程序包**

1.  若要将 app-v 5.0 程序包添加并发布到运行 App-v 客户端的计算机，请键入以下命令：

    AppvClientPackage – path c:\\tmpstore\\quartfin.appv |发布-AppvClientPackage

2.  对 "连接" 组中的每个程序包重复此过程的**步骤 1** 。

<a href="" id="bkmk-add-enable-cg-on-clt"></a>**在 App-v 客户端上添加和启用连接组**

1.  通过键入以下命令来添加连接组：

    AppvClientConnectionGroup-路径 c:\\tmpstore\\financ.xml

2.  通过键入以下命令启用连接组：

    Enable-AppvClientConnectionGroup-名称 "财务应用程序"

    当成员程序包中的任何虚拟应用程序在目标计算机上运行时，它们将在连接组的虚拟环境内运行，并且将在连接组中的其他程序包内的所有虚拟应用程序中可用。

<a href="" id="bkmk-enable-cg-for-user-poshtopic"></a>**为特定用户启用或禁用连接组**

1.  查看参数说明和要求：

    -   该参数使管理员能够为特定用户启用或禁用连接组。

    -   必须使用 App-v 5.0 SP2 修补程序包5或更高版本才能使用此参数。

    -   你可以从用户或管理员会话运行此 cmdlet。

    -   必须使用管理凭据登录才能使用该参数。

    -   最终用户必须登录。

    -   您必须提供最终用户的安全标识符（SID）。

2.  使用以下 cmdlet，并添加可选的 **-UserSID**参数，其中 **-UserSID**表示最终用户的安全标识符（SID）：

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">Cmdlet</th>
    <th align="left">示例</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>Enable-AppVClientConnectionGroup</p></td>
    <td align="left"><p>Enable-AppVClientConnectionGroup "ConnectionGroupA"-UserSID S-1-2-34-56789012-3456789012-345678901-2345</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>Disable-AppVClientConnectionGroup</p></td>
    <td align="left"><p>Disable-AppVClientConnectionGroup "ConnectionGroupA"-UserSID S-1-2-34-56789012-3456789012-345678901-2345</p></td>
    </tr>
    </tbody>
    </table>

<a href="" id="bkmk-admin-only-posh-topic-cg"></a>**仅允许管理员启用连接组**

1.  查看使用此 cmdlet 的说明和要求：

    -   使用此 cmdlet 和参数将 App-v 客户端配置为仅允许管理员（而非最终用户）启用或禁用连接组。

    -   必须至少使用 app-v 5.0 SP3 才能使用此 cmdlet。

2.  运行以下 cmdlet 和参数：

    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">Cmdlet</th>
    <th align="left">参数和值</th>
    <th align="left">示例</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>Set-AppvClientConfiguration</p></td>
    <td align="left"><p>–RequirePublishAsAdmin</p>
    <ul>
    <li><p>0-假</p></li>
    <li><p>1-True</p></li>
    </ul></td>
    <td align="left"><p>Set-AppvClientConfiguration-RequirePublishAsAdmin1</p></td>
    </tr>
    </tbody>
    </table>

    已**获得有关 app-v 的建议**？ 在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。 **遇到了 app-v 问题？** 使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相关主题


[App-V 5.0 的操作](operations-for-app-v-50.md)

[使用 PowerShell 管理 App-V](administering-app-v-by-using-powershell.md)

 

 





