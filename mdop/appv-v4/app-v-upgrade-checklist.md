---
title: App-V 升级清单
description: App-V 升级清单
author: dansimp
ms.assetid: 64e317d2-d260-4b67-8a49-ba9ac513087a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: ad856ce3067c327f3e604f9269ee384a66a1675a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802336"
---
# App-V 升级清单


在尝试升级到 Microsoft Application Virtualization （App-v）4.5 或更高版本之前，任何早于 app-v 4.1 的版本都必须升级到 App-v 4.1。 你应该首先计划升级客户端，然后升级服务器组件。 已升级到 app-v 4.5 的 app-v 客户端将继续处理尚未升级的 app-v 服务器。 已升级到 app-v 4.5 的服务器不支持早期版本的客户端。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">步骤</th>
<th align="left">参考</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>升级 app-v 客户端。</p></td>
<td align="left"><p><a href="how-to-upgrade-the-application-virtualization-client.md" data-raw-source="[How to Upgrade the Application Virtualization Client](how-to-upgrade-the-application-virtualization-client.md)">如何升级 Application Virtualization Client</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>升级 app-v 服务器和数据库。</p>
<div class="alert">
<strong>重要提示</strong><br/><p>如果你有多个对 App-v 数据库的服务器共享访问权限，则所有这些服务器都必须在数据库升级时联机。 你应遵循数据库升级的常规业务做法，但我们建议你先在测试服务器上使用数据库的备份副本测试数据库升级。 然后，你应该选择其中一个服务器进行首次升级，这将升级数据库架构。 成功升级生产数据库后，您可以在其他服务器上升级 app-v 软件。</p>
</div>
<div>

</div></td>
<td align="left"><p><a href="how-to-upgrade-the-servers-and-system-components.md" data-raw-source="[How to Upgrade the Servers and System Components](how-to-upgrade-the-servers-and-system-components.md)">如何升级服务器和系统组件</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>升级 app-v Management Web 服务。</p>
<p>仅当管理 Web 服务位于单独的服务器上时才适用此步骤，这将要求你在单独的服务器上运行服务器安装程序以升级管理 Web 服务。 否则，以前的服务器升级步骤将自动升级管理 Web 服务。</p></td>
<td align="left"><p><a href="how-to-upgrade-the-servers-and-system-components.md" data-raw-source="[How to Upgrade the Servers and System Components](how-to-upgrade-the-servers-and-system-components.md)">如何升级服务器和系统组件</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>升级 app-v 管理控制台。</p>
<p>此步骤仅适用于管理控制台位于单独计算机上的情况，这需要你在单独的计算机上运行服务器安装程序才能升级该控制台。 否则，以前的服务器升级步骤将升级管理控制台。</p></td>
<td align="left"><p><a href="how-to-upgrade-the-servers-and-system-components.md" data-raw-source="[How to Upgrade the Servers and System Components](how-to-upgrade-the-servers-and-system-components.md)">如何升级服务器和系统组件</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>升级 app-v Sequencer。</p></td>
<td align="left"><p><a href="how-to-upgrade-the-application-virtualization-sequencer.md" data-raw-source="[How to Upgrade the Application Virtualization Sequencer](how-to-upgrade-the-application-virtualization-sequencer.md)">如何升级 Application Virtualization Sequencer</a></p></td>
</tr>
</tbody>
</table>



## 其他升级注意事项


-   不需要再次对版本4.2 中的任何虚拟应用程序包进行排序，即可与版本4.5 一起使用。 但是，如果你希望应用默认的访问控制列表（Acl）或生成 Windows Installer 文件，应考虑将虚拟程序包升级为 Microsoft Application Virtualization 4.5 格式。 这是一个简单的过程，只需要使用 App-v 4.5 Sequencer 打开和保存现有虚拟应用程序包。 这可以通过使用 VSequencer 命令行界面自动执行。 有关详细信息，请参阅[如何使用 App-v Sequencer 创建或升级虚拟应用程序](how-to-create-or-upgrade-virtual-applications-using--the-app-v-sequencer.md)

-   4.5 Sequencer 的功能之一是创建 Windows Installer （.msi）文件的功能，作为虚拟应用程序包与电子软件分发（ESD）系统（如 Microsoft 终结点配置管理器）的互操作性的控制点。 以前升级到 app-v 4.5 的 App-v 4.1 或4.2 客户端上安装的用于应用程序虚拟化的以前升级到 app-v 的应用程序虚拟化的 Windows 安装程序文件将继续正常运行，但它们不能安装在 App-v 4.5 客户端上。 但是，除非在 App-v 4.5 Sequencer 中升级，否则无法删除或升级它们。 早于4.5 的原始 App-v 包必须在 App-v 4.5 Sequencer 中打开，然后另存为 Windows Installer 文件。

    **注意**  
    如果 app-v 4.2 客户端已升级到 App-v 4.5，则可以通过脚本解决方法来保留版本4.5 客户端上的版本4.2 程序包，并允许对其进行管理。 此脚本必须将两个文件（msvcp71.dll 和 msvcr71.dll）复制到 App-v 安装文件夹，并在注册表项下设置以下注册表项值： \ [HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\]：

    "ClientVersion" = "4.2.1.20"

    "GlobalDataDirectory" = "C:\\\\Documents 和 Settings\\\\All Users\\\\Documents\\\\" （全局可写位置）



-   当尝试在 App-v 4.6 客户端上运行时，由 app-v 4.5 Sequencer 生成的 Windows Installer 文件将显示错误消息 "此程序包需要 Microsoft Application Virtualization 客户端4.5 或更高版本"。 使用 app-v 4.5 SP1 Sequencer 或 App-v 4.6 排序器打开旧程序包，并为程序包生成新的 .msi 文件。

-   当服务器升级到版本4.5 时，将覆盖创建和保存的任何版本4.2 报告。 如果必须保留这些报表，则必须保存位于服务器的 SoftGrid 管理控制台文件夹中的 SftMMC 文件的备份副本，然后使用该副本替换升级期间安装的新 SftMMC。

-   有关从早期版本升级的其他信息，请参阅[升级到 Microsoft Application Virtualization 4.5 常见问题](https://go.microsoft.com/fwlink/?LinkId=120358)（ https://go.microsoft.com/fwlink/?LinkId=120358) 。

## <a href="" id="app-v-4-6-client-package-support-"></a>App-v 4.6 客户端软件包支持


你可以将在早期版本的 app-v 中创建的程序包部署到 app-v 4.6 客户端。 但是，你必须修改关联的 .osd 文件，以便它包括相应的操作系统和芯片体系结构信息。 可以使用以下值：

<table>
<colgroup>
<col width="100%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">操作系统值</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>&lt;OS 值 = "Win2003TS"/&gt;</p></td>
</tr>
<tr class="even">
<td align="left"><p>&lt;OS 值 = "Win2003TS64"/&gt;</p></td>
</tr>
<tr class="odd">
<td align="left"><p>&lt;OS 值 = "Win2008TS"/&gt;</p></td>
</tr>
<tr class="even">
<td align="left"><p>&lt;OS 值 = "Win2008TS64"/&gt;</p></td>
</tr>
<tr class="odd">
<td align="left"><p>&lt;OS 值 = "Win2008R2TS64"/&gt;</p></td>
</tr>
<tr class="even">
<td align="left"><p>&lt;OS 值 = "Win7"/&gt;</p></td>
</tr>
<tr class="odd">
<td align="left"><p>&lt;OS 值 = "Win764"/&gt;</p></td>
</tr>
<tr class="even">
<td align="left"><p>&lt;OS 值 = "WinVista"/&gt;</p></td>
</tr>
<tr class="odd">
<td align="left"><p>&lt;OS 值 = "WinVista64"/&gt;</p></td>
</tr>
<tr class="even">
<td align="left"><p>&lt;OS 值 = "WinXP"/&gt;</p></td>
</tr>
<tr class="odd">
<td align="left"><p>&lt;OS 值 = "WinXP64"/&gt;</p></td>
</tr>
</tbody>
</table>



若要运行新创建的32位程序包，必须在运行32位操作系统的计算机上对应用程序进行排序，安装了 App-v 4.6 Sequencer。 对应用程序进行排序后，在 Sequencer 控制台中，单击 "**部署**" 选项卡，然后根据需要指定相应的操作系统和芯片体系结构。

**重要提示**  
在运行64位操作系统的计算机上排序的应用程序必须部署到运行64位操作系统的计算机上。 使用 app-v 4.6 Sequencer 创建的新32位程序包不会在运行 App-v 4.5 客户端的计算机上运行。



若要在 App-V 4.6 客户端上运行新的64位程序包，你必须在运行 App-v 4.6 Sequencer 且运行了64位操作系统的计算机上对应用程序进行排序。 对应用程序进行排序后，在 Sequencer 控制台中，单击 "**部署**" 选项卡，然后根据需要指定相应的操作系统和芯片体系结构。

下表列出了哪些客户端版本将运行使用各种版本的 sequencer 创建的程序包。

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
<th align="left"></th>
<th align="left">使用 app-v 4.2 Sequencer 进行排序</th>
<th align="left">使用 app-v 4.5 Sequencer 进行排序</th>
<th align="left">使用32位 App-v 4.6 Sequencer 进行排序</th>
<th align="left">使用64位 App-v 4.6 Sequencer 进行排序</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>4.2 客户端</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>否</p></td>
<td align="left"><p>否</p></td>
<td align="left"><p>否</p></td>
</tr>
<tr class="even">
<td align="left"><p>4.5 客户端¹</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>否</p></td>
<td align="left"><p>否</p></td>
</tr>
<tr class="odd">
<td align="left"><p>4.6 客户端（32位）</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>否</p></td>
</tr>
<tr class="even">
<td align="left"><p>4.6 客户端（64位）</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
</tr>
</tbody>
</table>



¹适用于应用-v 4.5 客户端的所有版本，包括 App-v 4.5、App-v 4.5 CU1 和 App-v 4.5 SP1。









