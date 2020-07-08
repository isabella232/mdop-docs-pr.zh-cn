---
title: Application Virtualization 5.1 性能指南
description: Application Virtualization 5.1 性能指南
author: dansimp
ms.assetid: 5f2643c7-5cf7-4a29-adb7-45bf9f5b0364
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 3382a7958e12cc28b8101a6d5b7384a6975e6e82
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798316"
---
# Application Virtualization 5.1 性能指南


了解如何配置 app-v 5.1 以优化性能、优化虚拟应用包以及使用 RDS 和 VDI 提供更好的用户体验。

实现多个方法可帮助你改进最终用户体验。 但是，你的环境可能不支持所有方法。

阅读本文档之前，请阅读并理解以下信息。

-   [Microsoft Application Virtualization 5.1 管理员指南](microsoft-application-virtualization-51-administrators-guide.md)

-   [App-v 5 SP2 应用程序发布和客户端交互](https://go.microsoft.com/fwlink/?LinkId=395206)

-   [Microsoft Application Virtualization 排序指南](https://go.microsoft.com/fwlink/?LinkId=269953)

**注意**  
本文档中使用的某些术语可能具有不同的含义，具体取决于外部源和上下文。 有关本文档中使用的术语的详细信息，后跟星号 **\\** * 请查看本文档的[Application Virtualization 性能指南术语](#bkmk-terms1)部分。



最后，本文档将向你提供用于配置运行 app-v 5.1 客户端的计算机和用于优化性能的环境的信息。 使用 sequencer 优化虚拟应用程序包的性能，并了解如何使用用户体验虚拟化（UE-V）或其他用户环境管理技术在远程桌面服务（RDS）和非永久性虚拟桌面基础结构（VDI）中提供有关 App-v 5.1 的最佳用户体验。

为了帮助确定哪些信息与你的环境相关，你应查看每个部分的简要概述和适用性清单。

## <a href="" id="---------app-v-5-1-in-stateful--non-persistent-deployments"></a> 状态 \ * 非永久性部署中的 app-v 5。1


本部分提供了有关帮助确保用户在登录后的几秒钟内能够访问所有虚拟应用程序的方法的信息。 这是通过唯一寻址经常运行的 App-v 5.1 发布刷新的唯一方法实现的。 由于你将发现方法的基础，最快的发布刷新是无需实际执行任何操作的方法。 必须满足许多条件和步骤，然后才能提供最佳的用户体验。

有关详细信息，请使用以下部分中的信息：

[使用方案](#bkmk-us)-当你查看这两个方案时，请记住这两种方法的极端。 根据你的使用要求，你可以选择将这些步骤应用到用户和/或虚拟应用程序包的子集。

-   针对性能进行优化-若要提供最佳体验，你可以期望基本映像包含一些 App-v 虚拟应用程序包。 本文将讨论此和其他要求。

-   针对存储进行了优化-如果你关注存储影响，请遵循此方案将帮助解决这些问题。

[准备环境](#bkmk-pe)

-   准备基本映像的步骤-无论是在非持久性 VDI 还是在 RDSH 环境中，只有少数几个步骤都必须在基本映像中完成才能启用此方法。

-   使用 UE-V 2.1 作为应用 V 方法的用户配置文件管理（UPM）解决方案-此方法的基础是 UEM 解决方案保留几个注册表和文件位置的内容的能力。 这些位置构成了用户集成 \ *。 请务必查看 UPM 解决方案的特定要求。

[用户体验指导-通过](#bkmk-uewt)

-   走出–这是分步指导，分步介绍了 app-v 和 UE-V 操作以及用户应具备的预期。

-   结果-这将描述预期的结果。

[对程序包生命周期的影响](#bkmk-plc)

[通过性能优化/优化增强 VDI 体验](#bkmk-evdi)

### <a href="" id="applicability-checklist-"></a>适用性清单

部署环境

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>非永久性 VDI 或 RDSH。</p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>用户体验虚拟化（UE-V）、其他 UPM 解决方案或用户配置文件磁盘（UPD）。</p></td>
</tr>
</tbody>
</table>



预期配置

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>用户体验虚拟化（UE-V）已启用 app-v 用户状态模板或用户配置文件管理（UPM）软件。 非 UE-V UPM 软件必须能够在登录或进程/应用程序启动和注销时触发。</p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>已配置或可以配置 app-v 共享的内容存储（SCS）。</p></td>
</tr>
</tbody>
</table>



IT 管理

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>管理员可能需要定期更新 VM 基本映像以确保最佳性能或管理员可能需要管理不同用户组的多个映像。</p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-us"></a>使用方案

查看这两种方案时，请记住这些方法的极端。 根据你的使用要求，你可以选择将这些步骤应用到用户、虚拟应用程序包或两者的子集。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">已针对性能进行优化</th>
<th align="left">已针对存储优化</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>为了提供最佳的用户体验，此方法利用 UPM 解决方案的功能，并且需要额外的映像管理开销。</p>
<p>下面介绍了状态非持久部署中的许多性能改进。 有关详细信息，请参阅 <strong> </strong> <strong> </strong> <strong> 本文档的 "另请参阅" 部分中 </strong> 的用于优化发布性能的程序包和参考 App-v 排序指南的先后顺序步骤。</p></td>
<td align="left"><p>此处仍适用于上一方案的一般预期。 但是，请记住，VM 映像通常存储在非常昂贵的阵列中;已对该方法稍作改动。 不要预配置基本映像中的用户目标虚拟应用程序包。</p>
<p>本文档的 "用户体验演练" 部分详细介绍了此变更的影响。</p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-pe"></a>准备环境

下表显示为方法准备基本映像和 UE-V 或另一个 UPM 解决方案所需的步骤。

**准备基本映像**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">已针对性能进行优化</th>
<th align="left">已针对存储优化</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p></p>
<ul>
<li><p>安装客户端的 app-v 5.1 客户端版本。</p></li>
<li><p>安装 UE-V 并从 UE-V 模板库下载 app-v 设置模板，请参阅以下步骤。</p></li>
<li><p>为共享内容存储（SCS）模式进行配置。 有关详细信息，请参阅 <a href="how-to-install-the-app-v-51-client-for-shared-content-store-mode.md" data-raw-source="[How to Install the App-V 5.1 Client for Shared Content Store Mode](how-to-install-the-app-v-51-client-for-shared-content-store-mode.md)"> 如何为共享内容存储模式安装 app-v 5.1 客户端 </a> 。</p></li>
<li><p>配置在登录注册表 DWORD 上保留用户集成。</p></li>
<li><p>预配置所有由用户和全局定向的程序包（例如， <strong> Add-AppvClientPackage </strong> 。</p></li>
<li><p>预配置所有用户和全局定向的连接组（例如， <strong> Add-AppvClientConnectionGroup </strong> 。</p></li>
<li><p>预发布所有全局目标程序包。</p>
<p></p>
<p>另</p>
<ul>
<li><p>执行全局发布/刷新。</p></li>
<li><p>执行用户发布/刷新。</p></li>
<li><p>取消发布所有面向用户的程序包。</p></li>
<li><p>删除以下用户虚拟文件系统（VFS）条目。</p></li>
</ul>
<p><code>AppData\Local\Microsoft\AppV\Client\VFS</code></p>
<p><code>AppData\Roaming\Microsoft\AppV\Client\VFS</code></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>安装客户端的 app-v 5.1 客户端版本。</p></li>
<li><p>安装 UE-V 并从 UE-V 模板库下载 app-v 设置模板，请参阅以下步骤。</p></li>
<li><p>为共享内容存储（SCS）模式进行配置。 有关详细信息，请参阅 <a href="how-to-install-the-app-v-51-client-for-shared-content-store-mode.md" data-raw-source="[How to Install the App-V 5.1 Client for Shared Content Store Mode](how-to-install-the-app-v-51-client-for-shared-content-store-mode.md)"> 如何为共享内容存储模式安装 app-v 5.1 客户端 </a> 。</p></li>
<li><p>配置在登录注册表 DWORD 上保留用户集成。</p></li>
<li><p>预配置所有全局定向的程序包（例如， <strong> Add-AppvClientPackage </strong> 。</p></li>
<li><p>预配置所有全局定向的连接组（例如， <strong> Add-AppvClientConnectionGroup </strong> 。</p></li>
<li><p>预发布所有全局目标程序包。</p>
<p></p></li>
</ul></td>
</tr>
</tbody>
</table>



**配置**-对于关键应用程序-V 客户端配置以及更多上下文和操作方法，请查看以下信息：

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">配置设置</th>
<th align="left">这是什么？</th>
<th align="left">我应该如何使用它？</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>共享内容存储（SCS）模式</p>
<ul>
<li><p>可在 PowerShell 中使用 <strong> AppvClientConfiguration </strong> - <strong> SharedContentStoreMode </strong> 或</p></li>
<li><p>在安装 app-v 客户端的过程中。</p></li>
</ul></td>
<td align="left"><p>仅当运行共享内容存储时，才会在硬盘上维护发布数据;其他虚拟应用程序资源将保留在内存（RAM）中。</p>
<p>这有助于保存本地存储并最大限度地减少每秒磁盘 i/o （IOPS）。</p></td>
<td align="left"><p>如果在应用 V 客户端终结点和 SCS 内容服务器（SAN）之间提供低延迟连接，则建议使用此操作。</p></td>
</tr>
<tr class="even">
<td align="left"><p>PreserveUserIntegrationsOnLogin</p>
<ul>
<li><p>在注册表中的 " <strong> HKEY_LOCAL_MACHINE </strong>  \  <strong> 软件 </strong>  \  <strong> Microsoft </strong>  \  <strong> AppV </strong>  \  <strong> 客户端 </strong>  \  <strong> 集成 </strong> " 下进行配置。</p></li>
<li><p>创建 <strong> </strong> 值为1的 DWORD 值 PreserveUserIntegrationsOnLogin <strong> </strong> 。</p></li>
<li><p>重新启动 App-v client 服务或重启运行 App-v 客户端的计算机。</p></li>
</ul></td>
<td align="left"><p>如果尚未预配置（ <strong> Add-AppvClientPackage </strong> ）特定程序包，并且未配置此设置，则 App-v 客户端将解除集成 * 保留的用户集成，然后重新集成 *。</p>
<p>对于满足上述条件的每个程序包，有效地将在发布/刷新期间完成两次工作。</p></td>
<td align="left"><p>如果您不打算预配置基本映像中的每个可用用户程序包，请使用此设置。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MaxConcurrentPublishingRefresh</p>
<ul>
<li><p>在注册表中的 " <strong> HKEY_LOCAL_MACHINE </strong> &lt; 增强的 &gt; 软件 </strong>  \  <strong> Microsoft </strong>  \  <strong> AppV </strong> &lt; 增强 &gt; 的客户端 </strong>  \  <strong> 发布 </strong> " 下进行配置。</p></li>
<li><p><strong> </strong> 用所需的并发发布刷新次数创建 DWORD 值 MaxConcurrentPublishingrefresh。</p></li>
<li><p>App-v 客户端服务和计算机不需要重新启动。</p></li>
</ul></td>
<td align="left"><p>此设置确定可以同时执行发布刷新/同步的用户数。 默认设置为 "无限制"。</p></td>
<td align="left"><p>限制并发发布刷新数可防止过度占用的 CPU 使用率影响计算机性能。 建议在 RDS 环境中使用此限制，在这种情况下，多个用户可以同时登录到同一台计算机并执行发布刷新同步。</p>
<p>如果达到了并发发布刷新阈值，发布新应用程序并使最终用户在登录后可以使用的时间可能会花费不确定的时间。</p></td>
</tr>
</tbody>
</table>



### 为 App-v 方法配置 UE-V 解决方案

我们建议使用 Microsoft 用户体验虚拟化（UE-V）捕获和集中特定用户的应用程序设置和 Windows 操作系统设置。 然后，这些设置将应用于用户访问的不同计算机，包括桌面计算机、便携式计算机和虚拟桌面基础结构（VDI）会话。 UE-V 针对 RDS 和 VDI 方案进行了优化。

有关详细信息，请参阅[用户体验虚拟化2.0 入门](https://technet.microsoft.com/library/dn458926.aspx)

实质上，只需安装 UE-V 客户端，然后从[Microsoft 用户体验虚拟化（ue-v）模板库](https://gallery.technet.microsoft.com/Authored-UE-V-Settings-bb442a33)下载以下 microsoft 创作的 app-v 设置模板。 注册模板。 有关 UE-V 模板的详细信息，请参阅[用于获取和注册模板的 ue-v 特定资源](https://technet.microsoft.com/library/dn458926.aspx)。

**注意**  
在不执行其他配置步骤的情况下，Microsoft 用户环境虚拟化（UE-V）将无法同步目标计算机上的 "开始" 菜单快捷方式（.lnk 文件）。 默认情况下将排除 .lnk 文件类型。

UE-V 仅支持从 "RDS 和 VDI" 方案中的排除列表中删除 .lnk 文件类型，其中每个用户的设备都将具有同一位置安装的同一应用程序集，并且每个 .lnk 文件对所有用户的设备均有效。 例如，UE-V 目前不支持以下2种方案，因为最终结果将是快捷方式将在一个但不是所有设备上有效。

-   如果用户在启用了 .lnk 文件的一台设备上安装了应用程序，并且在另一台设备上安装了与启用了 .lnk 文件的其他安装根目录相同的本机应用程序。

-   如果用户在一台设备上安装了应用程序，但未启用另一台设备上的 .lnk 文件。



**重要提示**  
本主题介绍如何使用注册表编辑器更改 Windows 注册表。 如果不正确地更改 Windows 注册表，则可能会导致严重问题，可能需要重新安装 Windows。 在更改注册表之前，应创建注册表文件（.dat 和 .dat）的备份副本。 Microsoft 无法保证更改注册表时可能出现的问题可以解决。 更改注册表的风险由您自己承担。



使用 Microsoft 注册表编辑器（regedit.exe），导航到**HKEY \ _LOCAL \ _MACHINE**  \\  **软件**  \\  **Microsoft**  \\  **UEV**  \\  **Agent**  \\  **配置**  \\  **ExcludedFileTypes**并从排除的文件类型中删除 **.lnk** 。

**为 App-v 方法配置其他用户配置文件管理（UPM）解决方案**

在有状态的环境中的预期是，UPM 解决方案已实现，并且可以支持跨会话和登录之间的用户数据的持久性。

UPM 解决方案的要求如下所示。

若要启用针对用户的 app-v 5.1 方法的优化登录体验，解决方案必须具备以下功能：

-   将以下用户集成保留为用户配置文件/角色的一部分。

-   在登录（或应用程序启动）上触发用户配置文件同步，这样可以确保在发布/刷新开始之前应用所有用户集成，或者

-   附加和分离用户配置文件磁盘（UPD）或包含用户集成的类似技术。

    **注意**  
    仅当将整个配置文件存储在用户配置文件磁盘上时，才支持使用 UPD。

    将 UPD 与存储在用户配置文件磁盘中的选定文件夹结合使用时，不支持 app-v 程序包。 "写入时副本" 驱动程序不会处理 UPD 选定的文件夹。



-   在会话注销之前捕获对位置（构成用户集成）的更改。

使用 app-v 5.1 添加发布服务器（**AppvPublishingServer**）时，你可以配置同步，例如，在登录期间刷新和/或在指定的刷新间隔后进行刷新。 在这两种情况下，都将创建计划任务。

在早期版本的 App-v 5.1 中，使用将启动用户和全局刷新的 VBScript 配置了两个计划任务。 对于应用程序虚拟化 5.0 SP2，应用程序虚拟化 SP2 的用户在登录时刷新是由**SyncAppvPublishingServer.exe**发起的。 引入此变更是为了提供 UPM 解决方案一个触发器进程。 此过程将延迟发布/refresh 以允许 UPM 解决方案应用用户集成。 发布/刷新完成后，它将退出。

**用户集成**

注册表-HKEY \ _CURRENT \ _USER

-   Path-Software\\Classes

    排除：本地设置、ActivatableClasses、AppX \ *

-   Path-Software\\Microsoft\\AppV

-   Path-Software\\Microsoft\\Windows\\CurrentVersion\\App 路径

**文件位置**

-   Root-"环境变量" APPDATA

    Path-Microsoft\\AppV\\Client\\Catalog

-   Root-"环境变量" APPDATA

    Path-Microsoft\\AppV\\Client\\Integration

-   Root-"环境变量" APPDATA

    Path-Microsoft\\Windows\\Start Menu\\Programs

-   （保持所有桌面快捷方式，虚拟和非虚拟）

    Root-"KnownFolder" {B4BFCC3A-DB2C-424C-B029-7FE99A87C641} FileMask-\ * .lnk

**Microsoft 用户体验虚拟化（UE-V）**

此外，我们建议使用 Microsoft 用户体验虚拟化（UE-V）捕获和集中特定用户的应用程序设置和 Windows 操作系统设置。 然后，这些设置将应用于用户访问的不同计算机，包括桌面计算机、便携式计算机和虚拟桌面基础结构（VDI）会话。

有关详细信息，请参阅[用户体验虚拟化 1.0](https://technet.microsoft.com/library/jj680015.aspx)和[与 Ue-v 模板库共享设置位置模板](https://technet.microsoft.com/library/jj679972.aspx)的入门。

### <a href="" id="bkmk-uewt"></a>用户体验指导-通过

下面是 App-v 和 UPM 操作的分步指导，以及用户应期望的预期效果。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">已针对性能进行优化</th>
<th align="left">已针对存储优化</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>在 VDI/RDSH 环境中实现此方法后，在首次登录时，</p>
<ul>
<li><p>工序将启动用户发布/刷新。 预计如果这是用户第一次发布虚拟应用程序（例如，非永久性），这将占用发布/刷新的常规持续时间。</p></li>
<li><p>工序发布/刷新后，UPM 解决方案捕获用户集成。 预计根据 UPM 解决方案的配置方式，这可能会作为注销过程的一部分出现。 这将产生与保持用户状态相同/类似的开销。</p></li>
</ul>
<p>在后续登录中：</p>
<ul>
<li><p>工序UPM 解决方案在发布/刷新之前将用户集成到系统。</p>
<p>预计桌面或 "开始" 菜单中将显示快捷方式，该快捷方式将立即工作。 发布/刷新完成（即程序包权利更改）时，某些情况可能会消失。</p></li>
<li><p>工序发布/刷新将处理用户包权利中的更改的取消发布和发布操作。 预计如果没有权利更改，publishing1 将在几秒钟内完成。 否则，发布/刷新将相对于虚拟应用程序的数量和复杂性而增加</p></li>
<li><p>工序UPM 解决方案将在注销时再次捕获用户集成。 预计与上一节相同。</p></li>
</ul>
<p>¹发布操作（ <strong> Publish-AppVClientPackage </strong> ）将条目添加到用户目录、将权利映射到用户、标识本地存储以及完成任何集成步骤。</p></td>
<td align="left"><p>在 VDI/RDSH 环境中实现此方法后，在首次登录时，</p>
<ul>
<li><p>工序将启动用户发布/刷新。 预计</p>
<ul>
<li><p>如果这是用户第一次发布虚拟应用程序（例如，非永久性），这将占用发布/刷新的常规持续时间。</p></li>
<li><p>首次登录时，将通过预配置程序包（添加/刷新）影响首次登录和后续登录。</p>
<p></p></li>
</ul></li>
<li><p>工序发布/刷新后，UPM 解决方案捕获用户集成。 预计根据 UPM 解决方案的配置方式，这可能会作为注销过程的一部分出现。 这将产生与保持用户状态相同/类似的开销</p></li>
</ul>
<p>在后续登录中：</p>
<ul>
<li><p>工序UPM 解决方案在发布/刷新之前将用户集成到系统。</p></li>
<li><p>工序添加/刷新必须预配置所有用户目标应用程序。 预计</p>
<ul>
<li><p>这可能会显著增加应用程序可用性的时间（以10秒为单位）。</p></li>
<li><p>这将增加相对于虚拟应用程序的数量和复杂性 * 的发布刷新时间。</p>
<p></p></li>
</ul></li>
<li><p>工序发布/刷新将处理对用户程序包权利所做的更改的取消发布和发布操作。</p></li>
</ul></td>
</tr>
</tbody>
</table>



<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">输出</th>
<th align="left">输出</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p></p>
<ul>
<li><p>由于用户集成已完全保留，因此不会有任何工作，例如，用于完成发布/刷新的集成。 所有虚拟应用程序将在登录后的几秒钟内可用。</p></li>
<li><p>发布/刷新将处理对用户的更改，这些用户为用户授予了影响体验的虚拟应用程序。</p></li>
</ul></td>
<td align="left"><p>由于添加/刷新必须将所有虚拟应用程序重新配置到 VM，因此将扩展每个登录上的发布刷新时间。</p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-plc"></a>对包生命周期的影响

升级程序包是程序包生命周期的一个重要方面。 为帮助保证用户能够访问相应的已升级（已发布）或降级（未发布）的虚拟应用程序包，建议你更新基本映像以反映这些更改。 若要了解查看以下部分的原因，请执行以下操作：

App-v 5.0 SP2 引入了挂起状态的概念。 过去，

-   如果管理员更改了权利或创建了程序包的新版本（已升级），并且在发布/刷新该程序包正在使用的过程中，则分别取消发布或发布操作将失败。

-   现在，如果程序包处于使用中，该操作将处于暂停。 将在服务重启时或在发出另一个发布或取消发布命令时处理未发布和发布挂起的操作。 在后一种情况下，如果虚拟应用程序在其他情况下处于使用中，虚拟应用程序将保持挂起状态。 对于全局发布的程序包，通常需要重启（或服务重启）。

在非持久性环境中，将不可能处理这些暂停的操作。 已暂停的操作（例如任务）在**HKEY \ _CURRENT \ _USER**  \\  **软件**  \\  **Microsoft**  \\  **AppV**  \\  **client**  \\  **PendingTasks**中捕获。 虽然此位置由 UPM 解决方案保留，但如果未在登录之前应用于环境，则不会对其进行处理。

### <a href="" id="bkmk-evdi"></a>通过性能优化优化增强 VDI 体验

以下部分包含有关 Microsoft 文档和下载的信息的列表，这些信息在优化环境以提高性能时可能很有用。

**.NET NGEN 博客和脚本（强烈建议）**

关于 NGEN 技术

-   [如何加快 NGEN 优化](https://blogs.msdn.com/b/dotnet/archive/2013/08/06/wondering-why-mscorsvw-exe-has-high-cpu-usage-you-can-speed-it-up.aspx)

-   [脚本](https://aka.ms/DrainNGenQueue)

**Windows Server 和服务器角色**

的服务器性能优化指南

-   [Microsoft Windows Server 2012 R2](https://msdn.microsoft.com/library/windows/hardware/dn529133.aspx)

-   [Microsoft Windows Server 2012](https://download.microsoft.com/download/0/0/B/00BE76AF-D340-4759-8ECD-C80BC53B6231/performance-tuning-guidelines-windows-server-2012.docx)

-   [Microsoft Windows Server 2008 R2](https://download.microsoft.com/download/6/B/2/6B2EBD3A-302E-4553-AC00-9885BBF31E21/Perf-tun-srv-R2.docx)

**服务器角色**

-   [远程桌面虚拟化主机](https://msdn.microsoft.com/library/windows/hardware/dn567643.aspx)

-   [远程桌面会话主机](https://msdn.microsoft.com/library/windows/hardware/dn567648.aspx)

-   [IIS 相关性： App-v 管理、发布和报告 Web 服务](https://msdn.microsoft.com/library/windows/hardware/dn567678.aspx)

-   [文件服务器（SMB）相关性：如果用于 SCS 模式中的 App-v 内容存储和传递](https://technet.microsoft.com/library/jj134210.aspx)

**Windows 客户端（来宾 OS）性能优化指南**

-   [Microsoft Windows 7](https://download.microsoft.com/download/E/5/7/E5783D68-160B-4366-8387-114FC3E45EB4/Performance Tuning Guidelines for Windows 7 Desktop Virtualization v1.9.docx)

-   [优化脚本：（由 Microsoft 支持人员提供）](https://blogs.technet.com/b/jeff_stokes/archive/2012/10/15/the-microsoft-premier-field-engineer-pfe-view-on-virtual-desktop-vdi-density.aspx)

-   [Microsoft Windows 8](https://download.microsoft.com/download/6/0/1/601D7797-A063-4FA7-A2E5-74519B57C2B4/Windows_8_VDI_Image_Client_Tuning_Guide.pdf)

-   [优化脚本：（由 Microsoft 支持人员提供）](https://blogs.technet.com/b/jeff_stokes/archive/2013/04/09/hot-off-the-presses-get-it-now-the-windows-8-vdi-optimization-script-courtesy-of-pfe.aspx)

## 为发布性能优化程序包的先后顺序步骤


几种应用程序-V 功能有利于新方案或支持新的客户部署方案。 以下功能会影响发布和启动操作的性能。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">步骤</th>
<th align="left">注意事项</th>
<th align="left">权益</th>
<th align="left">取舍</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>无功能块1（FB1，也称为主要的 FB）</p></td>
<td align="left"><p>无 FB1 意味着应用程序将立即启动并流故障（应用程序在启动时需要文件、DLL 且必须在网络上拉下）。如果存在网络限制，FB1 将：</p>
<ul>
<li><p>减少首次启动应用程序时使用的流故障数和网络带宽。</p></li>
<li><p>延迟启动，直到已对整个 FB1 进行流式处理。</p></li>
</ul></td>
<td align="left"><p>流错误减少了启动时间。</p></td>
<td align="left"><p>已配置 FB1 的虚拟应用程序包将需要重新排序。</p></td>
</tr>
</tbody>
</table>



### 删除 FB1

删除 FB1 不需要原始应用程序安装程序。 完成以下步骤后，建议将运行 sequencer 的计算机还原为干净的快照。

**SEQUENCER UI** -创建新的虚拟应用程序包。

1.  完成对自定义流的排序步骤 &gt; 。

2.  在 "流" 步骤中，不要选择 "**通过慢速或不可靠的网络优化程序包以进行部署**"。

3.  如果需要，请转到**目标操作系统**。

**修改现有虚拟应用程序包**

1.  完成对流的排序步骤。

2.  不要选择**通过慢速或不可靠的网络优化程序包以进行部署**。

3.  移动以**创建程序包**。

**PowerShell** -更新现有虚拟应用程序包。

1.  打开提升的 PowerShell 会话。

2.  Import-module **appvsequencer**。

3.  **Update-AppvSequencerPackage**  - **AppvPackageFilePath**

    "C:\\Packages\\MyPackage.appv"-安装程序

    "C:\\PackageInstall\\PackageUpgrade.exe empty.exe"-OutputPath

    "C:\\UpgradedPackages"

    **注意**  
    此 cmdlet 需要可执行文件（.exe）或批处理文件（.bat）。 必须提供空（不执行任何操作）可执行文件或批处理文件。



<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">步骤</th>
<th align="left">注意事项</th>
<th align="left">权益</th>
<th align="left">取舍</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>发布时无 SXS 安装（预安装 SxS 程序集）</p></td>
<td align="left"><p>不需要对虚拟应用程序包进行重新排序。 SxS 程序集可以保留在虚拟应用程序包中。</p></td>
<td align="left"><p>将不会在发布时安装 SxS 程序集依赖项。</p></td>
<td align="left"><p>必须预安装 SxS 程序集依赖项。</p></td>
</tr>
</tbody>
</table>



### 在 sequencer 上创建新的虚拟应用程序包

如果在排序器监视期间，将在应用程序的安装过程中安装 SxS 程序集（如 VC + + 运行时），将自动检测并包含在程序包中的 SxS 程序集。 管理员将收到通知，并且将具有排除 SxS 程序集的选项。

**客户端**：

当发布虚拟应用程序包时，App-v 客户端将检测是否已安装了所需的 SxS 依赖关系。 如果依赖项在计算机上不可用，并且它包含在程序包中，则是传统的 Windows Installer （.**msi**）将启动 SxS 程序集的安装。 如之前所述，只需在运行客户端的计算机上安装依赖项，以确保不会发生 Windows Installer （.msi）安装。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">步骤</th>
<th align="left">注意事项</th>
<th align="left">权益</th>
<th align="left">取舍</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>有选择地使用动态配置文件</p></td>
<td align="left"><p>App-v 5.1 客户端必须分析和处理这些动态配置文件。</p>
<p>关注文件的大小和复杂性（脚本执行、VREG 包含/排除）。</p>
<p>许多虚拟应用程序包可能已经具有特定于用户或计算机的动态配置文件。</p></td>
<td align="left"><p>如果有选择性地使用这些文件或根本不使用，则发布时间将会提高。</p></td>
<td align="left"><p>虚拟应用程序包需要单独配置或通过 App-v 服务器管理控制台进行配置以删除关联的动态配置文件。</p></td>
</tr>
</tbody>
</table>



### 使用 Powershell 禁用动态配置

-   对于已发布的程序包，你可以 `Set-AppVClientPackage –Name Myapp –Path c:\Packages\Apps\MyApp.appv` 使用

    **-DynamicDeploymentConfiguration**参数

-   同样，如果使用添加新的程序包，请不要 `Add-AppVClientPackage –Path c:\Packages\Apps\MyApp.appv` 使用

    **-DynamicDeploymentConfiguration**参数。

有关如何应用动态配置的文档，请参阅：

-   [如何使用 PowerShell 应用用户配置文件](how-to-apply-the-user-configuration-file-by-using-powershell51.md)

-   [如何使用 PowerShell 应用部署配置文件](how-to-apply-the-deployment-configuration-file-by-using-powershell51.md)

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">步骤</th>
<th align="left">注意事项</th>
<th align="left">权益</th>
<th align="left">取舍</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>用于在程序包生命周期期间同步脚本执行的帐户。</p></td>
<td align="left"><p>如果程序包中嵌入了脚本宣传资料，则 Add （Powershell）可能会显著降低。</p>
<p>在虚拟应用程序启动期间（StartVirtualEnvironment、StartProcess）和/或 Add + 发布期间运行脚本将影响在一个或多个这些生命周期操作期间的感知性能。</p></td>
<td align="left"><p>使用异步（非阻止）脚本可确保生命周期操作高效完成。</p></td>
<td align="left"><p>此步骤需要使用嵌入式脚本辅助包（具有相关联的动态配置文件以及同步引用和运行脚本）的所有虚拟应用程序包的工作知识。</p></td>
</tr>
<tr class="even">
<td align="left"><p>从程序包中删除无关的虚拟字体。</p></td>
<td align="left"><p>应用-V 产品团队调查的大多数应用程序都包含少量的字体，通常少于20。</p></td>
<td align="left"><p>虚拟字体影响发布刷新性能。</p></td>
<td align="left"><p>需要在本地启用/安装所需的字体。 有关说明，请参阅安装或卸载字体。</p></td>
</tr>
</tbody>
</table>



### 确定程序包中存在的虚拟字体

-   制作程序包的副本。

-   将程序包 \ _copy 的 appv 重命名为 Package\_copy.zip

-   打开 AppxManifest.xml 并找到下列内容：

    &lt;appv： Extension Category = "AppV"&gt;

    &lt;appv：字体&gt;

    &lt;appv： Font Path = "\ [{Fonts} \] \\private\\CalibriL.ttf" DelayLoad = "true" &gt; &lt; /Appv： Font&gt;

    **注意**  
    如果有字体标记为**DelayLoad**，这些字体不会影响首次启动。



~~~
&lt;/appv:Fonts&gt;
~~~

### 从程序包中排除虚拟字体

使用最适合用户范围的动态配置文件-计算机上所有用户的部署配置，特定用户的用户配置。

-   使用部署或用户配置禁用字体。

字体

--&gt;

&lt;已启用的字体 = "false"/&gt;

&lt;!--

## <a href="" id="bkmk-terms1"></a> App-v 5.1 性能指南术语


在描述与 App-v 5.1 性能优化相关的概念和操作时，将使用以下术语。

-   **复杂性**–指在预配置（**Add-AppvClientPackage**）或集成（**AppvClientPackage**）期间可能会影响性能的一个或多个程序包特征。 一些示例特征是：清单大小、虚拟字体数、文件数。

-   **取消集成**-删除用户集成

-   **重新集成**–应用用户集成。

-   **非持久，共**用-在每次登录时创建运行虚拟环境的计算机。

-   **永久性，个人**-运行每个登录的虚拟环境的计算机都保持不变。

-   **状态**-对于此文档，表示用户集成在会话之间保持，并且用户环境管理技术与非持久性 RDSH 或 VDI 结合使用。

-   **无状态**-表示在会话之间不保持用户状态时的方案。

-   **触发器**-（或本机操作触发器）。 UPM 使用这些类型的触发器启动监视或同步操作。

-   **用户体验**-在 app-v 5.1 的上下文中，用户体验 quantitatively 是以下部分的和：

    -   从用户启动登录到桌面的时间点开始，您可以进行操作。

    -   在使用 App-v 5.1 完整服务器基础结构时，从桌面可以与发布刷新的点开始交互的位置（在 PowerShell 术语中为同步）。 在独立实例中，启动了**Add-AppVClientPackage**和**AppVClientPackage Powershell**命令。

    -   从开始到完成发布刷新。 在独立实例中，这是第一个发布的最后一个虚拟应用程序。

    -   从虚拟应用程序可从快捷方式启动的位置开始。 或者，它从文件类型关联注册的点开始，并且将启动指定的虚拟应用程序。

-   **用户配置文件管理**-用于管理与环境相关联的用户组件的可控和结构化方法。 例如，用户配置文件、首选项和策略管理、应用程序控制和应用程序部署。 你可以使用脚本或第三方解决方案根据需要配置环境。






## 相关主题


[Microsoft Application Virtualization 5.1 管理员指南](microsoft-application-virtualization-51-administrators-guide.md)









