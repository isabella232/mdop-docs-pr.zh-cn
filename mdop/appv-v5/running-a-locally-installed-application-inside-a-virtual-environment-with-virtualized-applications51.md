---
title: 使用虚拟化应用程序在虚拟环境内部运行本地安装的应用程序
description: 使用虚拟化应用程序在虚拟环境内部运行本地安装的应用程序
author: dansimp
ms.assetid: 71baf193-a9e8-4ffa-aa7f-e0bffed2e4b2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 384a1325b2f363595971f70f25fe0a25cade448d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798260"
---
# 使用虚拟化应用程序在虚拟环境内部运行本地安装的应用程序


你可以在虚拟环境中运行本地安装的应用程序，以及使用 Microsoft Application Virtualization （App-v）虚拟化的应用程序。 在以下情况下，您可能希望执行此操作：

-   希望在客户端计算机本地安装和运行应用程序，但希望虚拟化并运行与该本地应用程序配合使用的特定插件。

-   对 app-v 客户端程序包进行故障排除，并希望在 App-v 虚拟环境中打开本地应用程序。

使用以下任一方法在 App-v 虚拟环境内打开本地应用程序：

-   [RunVirtual 注册表项](#bkmk-runvirtual-regkey)

-   [AppvClientPackage PowerShell cmdlet](#bkmk-get-appvclientpackage-posh)

-   [命令行开关/appvpid： &lt; PID&gt;](#bkmk-cl-switch-appvpid)

-   [命令行挂钩开关/appvve： &lt; GUID&gt;](#bkmk-cl-hook-switch-appvve)

每个方法实质上是同一个任务，但某些方法可能更适合于某些应用程序，具体取决于虚拟化的应用程序是否已在运行。

## <a href="" id="bkmk-runvirtual-regkey"></a>RunVirtual 注册表项


若要将本地安装的应用程序添加到程序包或连接组的虚拟环境，请按照以下部分中的说明将子项添加到注册表编辑器中的 `RunVirtual` 注册表项。

没有可用于管理此注册表项的组策略设置，因此你必须使用 System Center Configuration Manager 或其他电子软件分发（ESD）系统，或者手动编辑注册表。

### <a href="" id="bkmk-"></a>使用 RunVirtual 时支持的发布程序包的方法

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">App-v 版本</th>
<th align="left">支持的发布方法</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>App-v 5.0 SP3 和 App-v 5。1</p></td>
<td align="left"><p>已全局或向用户发布</p></td>
</tr>
<tr class="even">
<td align="left"><p>App-v 5.0 至 App-V 5.0 SP2</p></td>
<td align="left"><p>仅全局发布</p></td>
</tr>
</tbody>
</table>

 

### 创建子项的步骤

1.  使用下表中的信息，使用可执行文件的名称创建新的注册表项，例如**MyApp.exe**。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">程序包发布方法</th>
    <th align="left">在何处创建注册表项</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>全局发布</p></td>
    <td align="left"><p>HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\AppV\Client\RunVirtual</p>
    <p><strong>示例 </strong> ： HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\AppV\Client\RunVirtual\MyApp.exe</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>发布给用户</p></td>
    <td align="left"><p>HKEY_CURRENT_USER \SOFTWARE\Microsoft\AppV\Client\RunVirtual</p>
    <p><strong>示例 </strong> ： HKEY_CURRENT_USER \SOFTWARE\Microsoft\AppV\Client\RunVirtual\MyApp.exe</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>连接组可以包含：</p>
    <ul>
    <li><p>仅在全局或仅向用户发布的程序包</p></li>
    <li><p>全局发布和用户发布的程序包</p></li>
    </ul></td>
    <td align="left"><p>HKEY_LOCAL_MACHINE 或 HKEY_CURRENT_USER 键，但以下所有条件都必须为 true：</p>
    <ul>
    <li><p>如果要在虚拟环境中包含多个程序包，则必须将它们包含在已启用的连接组中。</p></li>
    <li><p>仅为连接组中的其中一个程序包创建一个子项。 例如，如果你有一个在全局上发布的程序包以及发布给用户的另一个程序包，则会为这些程序包之一创建一个子项，但不能同时创建这两个程序包。 虽然只为其中一个程序包创建子项，但连接组中的所有程序包以及本地应用程序都将在虚拟环境中可用。</p></li>
    <li><p>创建子项的键必须与您用于程序包的发布方法相匹配。</p>
    <p>例如，如果你将程序包发布给用户，则必须在下创建该子项 <code>HKEY_CURRENT_USER\SOFTWARE\Microsoft\AppV\Client\RunVirtual</code> 。</p></li>
    </ul></td>
    </tr>
    </tbody>
    </table>

     

2.  将新的注册表子项的值设置为程序包的 PackageId 和 VersionId，并用下划线分隔这些值。

    **语法**： &lt; PackageId &gt; \ _ &lt; VersionId&gt;

    **示例**： 4c909996-afc9-4352-b606-0b74542a09c1 \ _Be463724-Oct1-48f1-8604-c4bd7ca92fa

    上一个示例中的应用程序将生成如下所示的注册表导出文件（.reg 文件）：

    ``` syntax
    Windows Registry Editor Version 5.00 
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\AppV\Client\RunVirtual] 
    @="" 
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\AppV\Client\RunVirtual\MyApp.exe] 
    @="aaaaaaaa-bbbb-cccc-dddd-eeeeeeee_11111111-2222-3333-4444-555555555
    ```

## <a href="" id="bkmk-get-appvclientpackage-posh"></a>AppvClientPackage PowerShell cmdlet


你可以使用**AppVVirtualProcess** cmdlet 检索程序包名称，然后在指定程序包的虚拟环境中启动进程。 此方法允许你在 App-v 包的上下文中启动任何命令，无论该包当前是否正在运行。

使用以下语法示例，并替换** &lt; 程序包 &gt; **的名称：

`$AppVName = Get-AppvClientPackage <Package>`

`Start-AppvVirtualProcess -AppvClientObject $AppVName cmd.exe`

如果不知道程序包的确切名称，则可以使用命令行**AppvClientPackage \ * executable\\** <em> ，其中 **可执行 </em> 文件*是应用程序的名称，例如： Get-AppvClientPackage \ * Word \ *。

## <a href="" id="bkmk-cl-switch-appvpid"></a>命令行开关/appvpid： &lt; PID&gt;


你可以将 **/appvpid： &lt; PID &gt; **开关应用到任何命令，从而使该命令能够在你选择的虚拟进程内运行，方法是指定其进程 ID （PID）。 使用此方法会在与已运行的可执行文件相同的 App-v 环境中启动新的可执行文件。

示例： `cmd.exe /appvpid:8108`

若要查找 app-v 进程的进程 ID （PID），请从提升的命令提示符处运行命令**tasklist.exe** 。

## <a href="" id="bkmk-cl-hook-switch-appvve"></a>命令行挂钩开关/appvve： &lt; GUID&gt;


此开关允许你在 App-v 包的虚拟环境内运行本地命令。 与 **/appvid**开关（虚拟环境必须已运行）不同，此开关使你能够启动虚拟环境。

语法 `cmd.exe /appvve:<PACKAGEGUID_VERSIONGUID>`

示例： `cmd.exe /appvve:aaaaaaaa-bbbb-cccc-dddd-eeeeeeee_11111111-2222-3333-4444-55555555`

若要获取应用程序的程序包 GUID 和版本 GUID，请运行**AppvClientPackage** cmdlet。 将 **/appvve**开关与以下内容连接：

-   冒号

-   所需程序包的程序包 GUID

-   下划线

-   所需程序包的版本 ID

如果不知道程序包的确切名称，请使用命令行**AppvClientPackage \ * executable\\** <em> ，其中 **可执行 </em> 文件*是应用程序的名称，例如： Get-AppvClientPackage \ * Word \ *。

此方法允许你在 App-v 包的上下文中启动任何命令，无论该包当前是否正在运行。






## 相关主题


[App-V 5.1 技术参考](technical-reference-for-app-v-51.md)

 

 





