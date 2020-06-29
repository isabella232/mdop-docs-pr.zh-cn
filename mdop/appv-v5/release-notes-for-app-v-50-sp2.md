---
title: App-V 5.0 SP2 发行说明
description: App-V 5.0 SP2 发行说明
author: dansimp
ms.assetid: fe73139d-240c-4ed5-8e59-6ae76ee8e80c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 5e885e67023d0e5c1e36aeb340933c64ae92610e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798268"
---
# App-V 5.0 SP2 发行说明


**若要在这些发行说明中搜索特定问题，请按 CTRL + F。**

安装 App-v 5.0 SP2 之前，请仔细阅读这些发行说明。

这些发行说明包含成功安装 app-v 5.0 SP2 所需的信息。 发行说明还包含产品文档中不可用的信息。 如果这些发行说明和其他 App-v 5.0 文档之间存在差异，则应将最新更改视为权威。 这些发行说明取代了本产品附带的内容。

## 关于产品文档


有关 App-V 5.0 文档的详细信息，请参阅 Microsoft TechNet 上的 app-v 5.0 主页。

## 提供反馈


我们对 app-v 5.0 的反馈感兴趣。 您可以向发送反馈 <mdopdocs@microsoft.com> 。

**注意** 此电子邮件地址不是支持频道，但你的反馈将帮助我们为我们的文档和产品发布计划未来的更改。

 

有关 MDOP 和其他学习资源的最新信息，请参阅[Mdop 信息体验](https://go.microsoft.com/fwlink/p/?LinkId=236032)页面。

有关新更新或提供反馈的详细信息，请在[Facebook](https://go.microsoft.com/fwlink/p/?LinkId=242445)或[Twitter](https://go.microsoft.com/fwlink/p/?LinkId=242447)上关注我们。

## 适用于应用程序虚拟化 5.0 SP2 的修补程序包4的已知问题


### 卸载应用程序虚拟化 5.0 SP2 的修补程序包4后，程序包停止工作

当应用程序虚拟化 5.0 sp2 的修补程序包4已被删除时，应用于应用程序虚拟化 SP2 的修补程序包4时，发布的程序包将停止5.0 工作。

规避

如果存在以下文件夹，则必须将其删除：

**% localappdata%**  \\ **Microsoft**  \\ **AppV**  \\ **客户端**  \\ **VFS**  \\ 已发布的每个程序包的** &lt; 程序包 ID &gt; ** 。

**注意** 您必须具有更高的权限才能删除此文件夹。

 

若要对计算机上的每个用户帐户以及针对应用程序虚拟化 5.0 SP2 安装了修补程序包4后发布的每个程序包 id 使用脚本，请执行以下操作：

`Rd /s /q “%systemdrive%\users\[UserName]\AppData\Local\Microsoft\AppV\Client\VFS\[Package ID]`

-   即使在上一节的目录中删除文件夹后，这些快捷方式仍将保留在用户会话中，这样您就可以单击快捷方式来再次运行该应用程序。 无需重新发布应用程序。

-   对于用户发布的打包和全局发布的程序包（例如 Microsoft Office2013），会出现此问题。 必须删除这两种类型的程序包的文件夹。

-   无需在漫游应用数据（**% appdata%**）中删除 VFS 文件夹。 只有 **% localappdata%** 必须删除。

### Microsoft Office 集成指向错误的文件系统位置

Microsoft Office 集成指向错误的文件系统位置（Groove.exe 错误消息）。

规避

使用以下方法之一：

1.  升级后，删除 "启动" 文件夹中的快捷方式。

2.  使用脚本更改启动文件夹中的快捷方式。

3.  使用部署配置文件指定指向集成根的快捷方式目标。

### <a href="" id="-------------hotfix-package-4-for-application-virtualization-5-0-sp2-installer-can-take-a-long-time"></a> 应用程序虚拟化5.0 的修补程序包 4 SP2 安装程序可能需要花费很长时间

应用程序虚拟化 5.0 SP2 安装程序的修补程序包4可能会花费很长时间，具体取决于在现有程序包缓存中存储的文件数。

在修补程序包4中更新关联的程序包安全描述符应用程序虚拟化 5.0 SP2 安装对安装所需时间有重大影响。 以前，安装安装是持续时间的标准。 但是，它现在取决于在程序包缓存中暂存的文件数。

解决方法：无

### 如果正在使用 JIT 程序包，则卸载应用程序虚拟5.0 化修补程序程序包4的修补程序包将会失败

如果安装了应用程序虚拟化 5.0 SP2 的修补程序包4，然后尝试在使用实时虚拟化（JIT V）时卸载修复程序，则如果满足以下所有条件，则操作将失败：

-   通过使用 Windows Installer 文件（.msi）安装，然后使用 Microsoft 安装程序修补程序文件（.msp）应用更新。

-   您尝试使用 "控制面板" 中的 "添加或删除程序" 项卸载更新。

-   计算机上正在运行支持 JIT 的程序包。

解决方法：完成以下步骤：

1.  打开 Windows PowerShell 并运行以下命令：

    -   **导入-模块 appvclient**

    -   **AppvClientPackage |停止-AppvClientPackage**

2.  使用 "添加或删除程序" 卸载更新。

## 有关 app-v 5.0 SP2 的已知问题


### <a href="" id="bkmk-folderredirection"></a>App-v 客户端文件夹重定向有时无法将文件从% AppData% 移动到% LocalAppData%

当% AppData% 是已为文件夹重定向配置的共享网络文件夹时，最终用户对 AppData （漫游）所做的更改可能会在用户切换计算机时丢失，或者当其本地 AppData 在注销时被清除，然后重新登录。 出现此错误的原因是注册表项（AppDataTime），它指示上次已知上载的操作与本地缓存的 AppData 不同步。

解决方法：当最终用户登录或注销时，手动删除每个相关程序包的以下注册表项：

``` syntax
HKCU\Software\Microsoft\AppV\Client\Packages\<PACKAGE_GUID>\AppDataTime
```

当最终用户在登录后首次启动应用程序包中的应用程序时，App-v 会强制下载压缩% AppData%，即使% LocalAppData% 已经是最新的。

### <a href="" id="-------------app-v-5-0-service-pack-2--app-v-5-0-sp2--does-not-include-a-new-version-of-the-app-v-server"></a> App-v 5.0 Service Pack 2 （App-v 5.0 SP2）不包含新版本的 App-v Server

App-v 5.0 SP2 不包含新版本的 App-v Server。 如果你在你的环境中部署运行 Windows 8.1 的 app-v 5.0 SP2 客户端并计划使用 App-v 基础结构管理客户端，则必须安装[适用于 Microsoft Application Virtualization 5.0 Service Pack 1 的修补程序包 2](https://go.microsoft.com/fwlink/?LinkId=386634)。 (https://go.microsoft.com/fwlink/?LinkId=386634)

如果你正在运行和使用以下任一方法管理 app-v 5.0 SP2 客户端，则不需要客户端更新：

-   独立模式。

-   Configuration Manager。

-   第三方 ESD。

App-v 5.0 SP2 客户端与 Windows 8.1 完全兼容

解决方法：无。

## 发行说明版权信息


Microsoft、Active Directory、ActiveX、Bing、Excel、Silverlight、SQLServer、Windows、MicrosoftIntune 和 WindowsPowerShell 是 Microsoft 公司组的商标。 所有其他商标的所有权属于其各自所有者。








## 相关主题


[关于 App-V 5.0 SP2](about-app-v-50-sp2.md)

 

 





