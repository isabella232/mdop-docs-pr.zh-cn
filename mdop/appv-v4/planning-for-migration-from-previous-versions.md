---
title: 规划从之前的版本进行迁移
description: 规划从之前的版本进行迁移
author: dansimp
ms.assetid: 62967bf1-542f-41b0-838f-c62f3430ac73
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 9b239e09da06270b30b401151cf12e817e2cf8d4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798869"
---
# 规划从之前的版本进行迁移


在尝试升级到 Microsoft Application Virtualization 4.5 或更高版本之前，必须将4.1 之前的任何版本升级到版本4.1。 你应该首先计划升级客户端，然后升级服务器组件。 已升级到4.5 的客户端将继续处理尚未升级的 Application Virtualization 服务器。 升级到4.5 的服务器不支持早期版本的客户端。 有关升级系统组件的详细信息，请参阅[应用程序虚拟化部署和升级注意事项](application-virtualization-deployment-and-upgrade-considerations.md)。

为了帮助确保迁移成功，应按照以下顺序升级应用程序虚拟化系统组件：

1.  **Microsoft Application Virtualization 客户端。** 有关分步升级说明，请参阅[如何升级应用程序虚拟化客户端](how-to-upgrade-the-application-virtualization-client.md)。

2.  **Microsoft Application Virtualization 服务器和数据库。** 有关分步升级说明，请参阅[如何升级服务器和系统组件](how-to-upgrade-the-servers-and-system-components.md)。

    **注意** 如果您有多个服务器共享访问应用程序虚拟化数据库，则所有这些服务器都必须在数据库升级时联机。 你应遵循数据库升级的正常业务做法，但强烈建议你先在测试服务器上使用数据库的备份副本测试数据库升级。 然后，你应该选择其中一个服务器进行首次升级，这将升级数据库架构。 成功升级生产数据库后，您可以升级其他服务器。

     

3.  **Microsoft Application Virtualization 管理 Web 服务。** 此步骤仅适用于管理 Web 服务位于单独服务器上的情况，这将要求你在单独的服务器上运行服务器安装程序以升级 Web 服务。 否则，以前的服务器升级步骤将自动升级管理 Web 服务。

4.  **Microsoft Application Virtualization 管理控制台。** 此步骤仅适用于管理控制台位于单独计算机上的情况，这需要你在单独的计算机上运行服务器安装程序才能升级该控制台。 否则，以前的服务器升级步骤将升级管理控制台。

5.  **Microsoft Application Virtualization Sequencer。** 有关分步说明，请参阅[如何安装 Application Virtualization Sequencer](how-to-install-the-application-virtualization-sequencer.md)。 在版本4.2 中排序的任何虚拟应用程序包无需重新排序，即可与版本4.5 配合使用。 但是，如果你想要应用默认的访问控制列表（Acl）或生成 Windows Installer 文件，应考虑将虚拟程序包升级为 Microsoft Application Virtualization 4.5 格式。 这是一个简单的过程，只要求使用4.5 排序器打开和保存现有虚拟应用程序包。 可通过使用应用程序虚拟化 Sequencer 命令行界面自动执行此操作。

## <a href="" id="app-v-4-6-client-package-support-"></a>App-v 4.6 客户端软件包支持


你可以将在早期版本的 app-v 中创建的程序包部署到 App-v 4.6 客户端。 但是，你必须修改关联的 **.osd**文件，以便它包括相应的操作系统和芯片体系结构信息。 使用以下值。

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

 

若要运行新创建的32位程序包，必须在运行32位操作系统的计算机上对应用程序进行排序，安装了 app-v 4.6 Sequencer。 对应用程序进行排序后，在 Sequencer 控制台中，选择 "**部署**" 选项卡，然后根据需要指定相应的操作系统和芯片体系结构。

**重要提示** 在运行64位操作系统的计算机上排序的应用程序必须部署到运行64位操作系统的计算机上。 使用 app-v 4.6 Sequencer 创建的新32位程序包将不会在运行 App-v 4.5 客户端的计算机上运行。

 

若要在 App-V 4.6 客户端上运行新的64位程序包，必须在运行 App-v 4.6 Sequencer 和运行64位操作系统的计算机上对应用程序进行排序。 对应用程序进行排序后，在 Sequencer 控制台中，选择 "**部署**" 选项卡，然后根据需要指定相应的操作系统和芯片体系结构。

下表列出了哪些客户端版本将运行使用各种版本的 Sequencer 创建的程序包。

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
<th align="left"></th>
<th align="left">使用 app-v 4.2 Sequencer 进行排序</th>
<th align="left">使用 app-v 4.5 Sequencer 进行排序</th>
<th align="left">使用32位 App-v 4.6 Sequencer 进行排序</th>
<th align="left">使用64位 App-v 4.6 Sequencer 进行排序</th>
<th align="left">使用32位 App-v 4.6 SP1 排序器进行排序</th>
<th align="left">使用64位 App-v 4.6 SP1 排序器进行排序</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>4.2 客户端</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>否</p></td>
<td align="left"><p>否</p></td>
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
<td align="left"><p>否</p></td>
<td align="left"><p>否</p></td>
</tr>
<tr class="odd">
<td align="left"><p>4.6 客户端（32位）</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>不可用</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>否</p></td>
</tr>
<tr class="even">
<td align="left"><p>4.6 客户端（64位）</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
</tr>
<tr class="odd">
<td align="left"><p>4.6 SP1 客户端</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>不可用</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>否</p></td>
</tr>
<tr class="even">
<td align="left"><p>4.6 SP1 客户端（64位）</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
</tr>
</tbody>
</table>

 

¹适用于应用-v 4.5 客户端的所有版本，包括 App-v 4.5、app-v 4.5 CU1 和 App-v 4.5 SP1。

## 其他迁移注意事项


App-v 4.5 排序器的功能之一是将 Windows Installer 文件（.msi）创建为虚拟应用程序包与电子软件分发（ESD）系统（如 Microsoft 终结点配置管理器）的互操作性的控制点。 使用 .msi 工具创建的以前的 Windows 安装程序文件，这些文件已安装在应用程序虚拟化的应用程序虚拟化（随后升级到4.5 的客户端）上，但它们不能安装在4.5 客户端上。 但是，除非在4.5 排序器中升级，否则无法删除或升级它们。 需要在4.5 排序器中打开原始的4.5 虚拟应用程序包，然后将其另存为 Windows Installer 文件。

**注意** 如果应用程序 V 4.2 客户端已升级到4.5，则可以使用脚本作为解决方法来在4.5 客户端上保留4.2 程序包，并允许对其进行管理。 此脚本必须将两个文件（msvcp71.dll 和 msvcr71.dll）复制到 App-v 安装文件夹，并在注册表项 \ [HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\] 下设置以下注册表项值：

"ClientVersion" = "4.2.1.20"

"GlobalDataDirectory" = "C:\\\\Documents 和 Settings\\\\All Users\\\\Documents\\\\" （全局可写位置）

 

当你尝试在 App-v 4.6 客户端上运行时，由 app-v 4.5 Sequencer 生成的 Windows Installer 文件将显示错误消息 "此程序包需要 Microsoft Application Virtualization 客户端4.5 或更高版本"。 使用 app-v 4.5 SP1 Sequencer 或 App-v 4.6 排序器打开旧程序包，并为程序包生成新的 .msi。

当服务器升级到4.5 时，创建和保存的任何4.2 报告将被覆盖。 如果需要保留这些报表，则必须保存位于服务器的 SoftGrid 管理控制台文件夹中的 SftMMC 文件的备份副本，然后使用该副本替换升级期间安装的新 SftMMC。

有关从早期版本升级的其他信息，请参阅[升级到 Microsoft Application Virtualization 4.5 常见问题](https://go.microsoft.com/fwlink/?LinkId=120358)（ https://go.microsoft.com/fwlink/?LinkId=120358) 。

## 相关主题


[规划 Application Virtualization System 部署](planning-for-application-virtualization-system-deployment.md)

 

 





