---
title: App-V 4.6 SP2 发行说明
description: App-V 4.6 SP2 发行说明
author: dansimp
ms.assetid: abb536f0-e187-4c5b-952a-f837abd10ad2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: cf36a6361e6f49c2b868c6752e1b2eb379cc9a31
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803149"
---
# App-V 4.6 SP2 发行说明


**若要搜索这些发行说明，请按 CTRL + F。**

安装 Microsoft Application Virtualization （app-v） 4.6 SP2 之前，请仔细阅读这些发行说明。

这些发行说明包含成功安装 Application Virtualization 4.6 SP2 所需的信息。 发行说明还包含产品文档中不可用的信息。 如果这些发行说明和其他 App-v 4.6 文档之间存在差异，则应将最新更改视为权威。 这些发行说明取代了本产品附带的内容。

## 关于产品文档


有关 App-v 的文档的详细信息，请参阅 Microsoft TechNet 上的[应用程序虚拟化](https://go.microsoft.com/fwlink/?LinkID=232982)页面。

## 提供反馈


我们对 app-v 4.6 SP2 的反馈感兴趣。 您可以向发送反馈 <mdopdocs@microsoft.com> 。

**注意** 此电子邮件地址不是支持频道，但你的反馈将帮助我们为我们的文档和产品发布计划未来的更改。

 

有关 MDOP 和其他学习资源的最新信息，请参阅[Mdop 信息体验](https://go.microsoft.com/fwlink/p/?LinkId=236032)页面。

有关新更新或提供反馈的详细信息，请在[Facebook](https://go.microsoft.com/fwlink/p/?LinkId=242445)或[Twitter](https://go.microsoft.com/fwlink/p/?LinkId=242447)上关注我们。

## <a href="" id="known-issues-with-app-v-4-6-sp2-"></a>有关 App-v 4.6 SP2 的已知问题


### 序列时，对非系统物理驱动器禁用短文件名支持

当你在 Windows 8 或 Windows Server 2012 上进行排序时，对于非系统物理驱动器，默认情况下将禁用短文件名（8.3）支持。

在序列站上与主虚拟应用程序目录（例如，"Q:\\appname"）相关联的基础物理驱动器必须提供短文件名（8.3）支持，以便在创建虚拟应用程序包时，应用程序 V 4.6 SP2 Sequencer 生成短文件名。 对于 Windows 8 或 Windows Server 2012 上的非系统物理驱动器，默认情况下禁用短文件名（8.3）支持。

**解决方法：** 在非系统物理驱动器上启用短文件名（8.3）支持。 你可以使用以下命令在 Windows 8 或 Windows Server 2012 上启用短文件名支持。

``` syntax
fsutil 8dot3name set <virtual drive letter>:
```

例如，如果驱动器号为 "Q："，请使用以下命令：

``` syntax
fsutil 8dot3name set Q: 0
```

**注意** 无需在 App-v 客户端上更改此设置，因为 App-v 文件系统在 Windows 8 或 Windows Server 2012 上正确处理短路径。

 

### <a href="" id="-------------app-v-does-not-override-the-default-handler-for-file-type-or-protocol-associations-on-windows-8"></a> App-v 不会替代 Windows 8 上的文件类型或协议关联的默认处理程序

如果在 Windows 8 上使用 **"控制面板**" 中的 "**默认程序**" 选择默认应用程序，则 app-v 不会覆盖该应用程序的关联文件类型关联。

**解决方法：** 尚.

### Windows 8 上的 mailto 可点击链接的选项不提供虚拟化 Outlook 2010

Mailto 外壳扩展不会在 Windows 8 上提供虚拟化 Outlook 2010。 例如，如果您单击来自运行在 Windows 8 上的虚拟化 Outlook 2010 的 mailto：链接，则不会创建新的电子邮件窗口。 此选项在 Windows 7 和早期版本的 Windows 操作系统上正常工作。

**解决方法：** 尚.

### <a href="" id="-------------application-virtualization-4-6-sp2-update-is-not-offered-on-all-locales-that-use-microsoft-update"></a> 在使用 Microsoft Update 的所有区域设置中不提供应用程序虚拟化 4.6 SP2 更新

使用 Microsoft Update 时，适用于以下语言区域设置的 app-v 4.6 SP2 更新不可用：

-   哈萨克语

-   印地语

-   塞尔维亚语-西里尔文

**解决方法：** 如果你使用的是 Microsoft Windows Server 更新服务（WSUS），请使用更新的英文版本或从 Microsoft Update 目录下载更新。

## 发行说明版权信息


Microsoft、Active Directory、ActiveX、Bing、Excel、Silverlight、SQLServer、Windows、MicrosoftIntune 和 WindowsPowerShell 是 Microsoft 公司组的商标。 所有其他商标的所有权属于其各自所有者。



## 相关主题


[关于 Microsoft Application Virtualization 4.6 SP2](about-microsoft-application-virtualization-46-sp2.md)

 

 





