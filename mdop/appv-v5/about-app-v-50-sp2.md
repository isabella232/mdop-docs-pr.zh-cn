---
title: 关于 App-V 5.0 SP2
description: 关于 App-V 5.0 SP2
author: dansimp
ms.assetid: 16ca8452-cef2-464e-b4b5-c10d4630fa6a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 9a476f3bf273717b5a85a4244c5796f893b0c617
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798681"
---
# 关于 App-V 5.0 SP2


App-v 5.0 SP2 提供改进的集成平台、更灵活的虚拟化和针对虚拟化应用程序的强大管理。 有关详细信息，请参阅[App-V 5.0 概述](https://go.microsoft.com/fwlink/p/?LinkId=325265)（ https://go.microsoft.com/fwlink/?LinkId=325265) 。

## 标准 App V 5.0 SP2 功能中的更改


以下各节包含有关 App-v 5.0 SP2 的标准功能更改的信息。

### <a href="" id="bkmk-sp2-supported-cfg"></a>Windows Server 2012 R2 和 Windows 8.1 的支持

App-v 5.0 包括对 Windows Server 2012 R2 和 Windows 8.1 的支持

### <a href="" id="-------------app-v-5-0-sp2-now-supports-folder-redirection-for-the-user-s-roaming-appdata-directory"></a> App-v 5.0 SP2 现在支持用户的漫游 AppData 目录的文件夹重定向

App-v 5.0 SP2 支持漫游 AppData （% AppData%）文件夹重定向。 有关详细信息，请参阅[规划使用 app-v 的文件夹重定向](planning-to-use-folder-redirection-with-app-v.md)。

### <a href="" id="bkmk-pkg-upgr-pendg-tasks"></a>程序包升级改进和挂起的任务

在 App-v 5.0 SP2 中，当发布了更新版本的程序包或连接组时，不再提示关闭正在运行的虚拟应用程序。 如果尝试执行相关任务时程序包或连接组正在使用，则会显示一条消息，指示该对象正在使用，并且稍后将尝试该操作。

将根据以下规则执行已置入挂起状态的任务：

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

 

当任务置于挂起状态时，App-v 客户端还会为挂起任务生成注册表项，如下所示：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">基于用户或基于全球的任务</th>
<th align="left">注册表项的生成位置</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>基于用户的任务</p></td>
<td align="left"><p>KEY_CURRENT_USER \Software\Microsoft\AppV\Client\PendingTasks</p></td>
</tr>
<tr class="even">
<td align="left"><p>基于全球的任务</p></td>
<td align="left"><p>HKEY_LOCAL_MACHINE \Software\Microsoft\AppV\Client\PendingTasks</p></td>
</tr>
</tbody>
</table>

 

### 使用 App-v 5.0 虚拟化 Microsoft Office 2013 和 Microsoft Office 2010

有关 App-v 5.0 支持的 Microsoft Office 方案的详细信息，请使用以下链接。

[虚拟化适用于 Application Virtualization (App-V) 5.0 的 Microsoft Office 2013](../solutions/virtualizing-microsoft-office-2013-for-application-virtualization--app-v--50-solutions.md)

**注意** 本文档重点介绍如何创建 Microsoft Office 2013 App-v 5.0 程序包。 但是，它还提供了有关 Microsoft Office 2010 的应用程序与 app-v 5.0 相关的信息。

 

### <a href="" id="-------------app-v-5-0-client-management-user-interface-application"></a> App-v 5.0 客户端管理用户界面应用程序

在早期版本的 App-v 5.0 中，客户端管理用户界面（UI）随 App-v 5.0 客户端安装提供。 有了 app-v 5.0 SP2，这就不再是这样。 管理员现在可以选择将 app-v 5.0 客户端 UI 部署为虚拟应用程序（使用所有受支持的应用程序 V 部署配置）或安装的应用程序。

有关详细信息，请参阅[Microsoft Application Virtualization 5.0 客户端 UI 应用程序](https://go.microsoft.com/fwlink/p/?LinkId=386345)（ https://go.microsoft.com/fwlink/?LinkId=386345) 。

### 并行（SxS）程序集自动打包和部署

App-v 5.0 SP2 现在会自动检测运行 App-v 5.0 SP2 客户端的计算机上的并行（SxS）程序集和部署。 SxS 程序集主要由 VC + + 运行时依赖项或 MSXML 组成。 在早期版本的 App-v 中，具有 VC 运行时依赖项的虚拟应用程序需要在运行 App-v 5.0 SP2 客户端的计算机上本地运行这些依赖关系。

现在支持以下功能：

-   App-v 5.0 sequencer 会自动捕获程序包中的 SxS 程序集，而不管是否已在运行 sequencer 的计算机上安装了 VC 运行时。

-   App-v 5.0 客户端会根据需要在发布时将所需的 SxS 程序集自动安装到运行客户端的计算机。

-   App-v 5.0 sequencer 使用 sequencer 报告机制报告 VC 运行时依赖关系。

-   现在，App-v 5.0 sequencer 允许你在运行 sequencer 的计算机上已提供依赖项的情况中排除 VC 运行时依赖关系。

### 发布刷新改进

App-v 5.0 支持添加了多个功能，以提高为特定用户刷新一组应用程序的总体体验。

以下列表显示了发布刷新增强功能：

以下列表包含有关如何启用新的发布刷新改进的详细信息。

-   **EnablePublishingRefreshUI** -为运行 App-v 5.0 客户端的计算机启用发布刷新进度栏。

-   **HideUI** -在手动同步期间隐藏发布刷新进度栏。

### 新的客户端配置设置

以下新的客户端配置设置可用于 App-v 5.0 SP2：

**EnableDynamicVirtualization** -支持要虚拟化并与虚拟应用程序一起运行的支持的 Shell 扩展、浏览器帮助程序对象和 Active X 控件。

有关详细信息，请参阅[关于客户端配置设置](about-client-configuration-settings.md)。

### <a href="" id="-------------app-v-5-0-shell-extensions"></a> App-v 5.0 外壳扩展

现在，app-v 5.0 SP2 支持外壳扩展。

有关详细信息，请参阅[创建和管理 app-v 5.0 虚拟化应用程序](creating-and-managing-app-v-50-virtualized-applications.md)的 APP-V **5.0 sp2 shell 扩展支持**部分。

## <a href="" id="---------app-v-5-0-documentation-updates"></a> App-v 5.0 文档更新


App-v 5.0 SP2 提供以下方案的更新文档：

-   [从以前版本迁移](migrating-from-a-previous-version-app-v-50.md)

-   [关于 App-V 5.0](about-app-v-50.md)

-   [关于应用-V 5.0 报告](about-app-v-50-reporting.md)（常见问题部分）

## 如何获取 MDOP 技术


App-v 5.0 是 Microsoft 桌面优化包（MDOP）的一部分。 MDOP 是 Microsoft 软件保障的一部分。 有关 Microsoft 软件保证和获取 MDOP 的详细信息，请参阅[如何获取 mdop](https://go.microsoft.com/fwlink/?LinkId=322049) （ https://go.microsoft.com/fwlink/?LinkId=322049) 。






## 相关主题


[App-V 5.0 SP2 发行说明](release-notes-for-app-v-50-sp2.md)

 

 





