---
title: App-V 4.6 SP1 发行说明
description: App-V 4.6 SP1 发行说明
author: dansimp
ms.assetid: aeb6784a-864a-4f4e-976b-40c34dcfd8d6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 7081aaf4a04d52bf288d7a76b4a488e2b200c3d6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802376"
---
# App-V 4.6 SP1 发行说明


若要搜索这些发行说明，请按 CTRL + F。

**重要提示** 在安装 Microsoft Application Virtualization （app-v）管理系统之前，请仔细阅读这些发行说明。 这些发行说明包含的信息可帮助你成功安装应用程序虚拟化（app-v） 4.6 SP1。 本文档包含产品文档中不可用的信息。 如果这些发行说明和其他 App-v 文档之间存在差异，则应将最新更改视为权威。

 

## 防范安全漏洞和病毒


若要帮助防范安全漏洞和病毒，请务必为正在安装的任何新软件安装最新的可用安全更新。 有关详细信息，请参阅[Microsoft 安全网站](https://go.microsoft.com/fwlink/?LinkId=3482)（ https://go.microsoft.com/fwlink/?LinkId=3482) 。

## 应用程序虚拟化 4.6 SP1 的已知问题


本部分提供有关 Microsoft Application Virtualization （app-v） 4.6 SP1 问题的最新信息。 这些问题不会显示在产品文档中，在某些情况下，可能会矛盾现有产品文档。 如果可能，这些问题将在以后的版本中解决。

### 如果从 SPRT 的路径不以正斜杠（/）结尾，则该路径将丢失

当项目模板中的 HREF 中的路径不以正斜杠（）结尾时 **/** ，生成的 HREF 不包含该路径。 当用户手动处理**sprt**文件时，会发生这种情况。 如果使用 sequencer，它总是在路径后添加斜杠（ **/** ）。

解决方法确保 HREF 具有结尾的正斜杠（ **/** ）。

### 用户文件夹名称与程序包名称不对应

包含用户和 installer.pkg 文件的文件夹不再包含程序包名称。 以前，App-v 客户端用于将程序包根文件夹8.3 短名称用作文件夹名称的一部分。 这使你可以轻松地识别它。 使用 app-v 4.6 SP1 排序器时，程序包根文件夹8.3 短名称现在是随机字符串。 这使得很难在运行 App-v client 的计算机上标识包含程序包的**installer.pkg**文件的文件夹。

解决方法使用下列方法之一更轻松地识别这些包文件夹：

1.  使用排序器创建程序包时，请为主应用程序文件夹指定8.3 命名约定遵循的文件夹名称。 然后，此名称将用作用户文件夹名称的一部分，就像 App-v 4.6 中的情况一样。

2.  Sprj 文件现在包含一个标记，该标记显示用作用户文件夹名称的开头的字符串。 你可以使用**PACKAGEROOTFOLDER**元素的**SHORTNAME**元素来确定名称。

### 在超过64个处理器的计算机上运行 app-v 4.6 SP1

在安装了超过64个处理器的计算机上运行 app-v 4.6 SP1 时，App-v 客户端将失败。

解决方法无。 不支持此配置。 您必须运行 SP1on 个处理器小于64的 app-v 4.6。

### 未在使用 Microsoft Update 的所有区域设置中提供 Application Virtualization 4.6 SP1 更新

使用 Microsoft Update 时，对于以下语言区域设置，app-v 4.6 SP1 的更新不可用：

-   哈萨克语

-   印地语

-   塞尔维亚语-西里尔文

解决方法如果您使用的是 Microsoft Windows Server 更新服务（WSUS），请使用英文版更新或从 Microsoft Update 目录下载更新。

### 展开父程序包后，你无法使用并排组件序列化插件

当使用工具展开父包时， **Tools**  /  在 app-v Sequencer 控制台中将 "**包扩展到本地系统**" 并将插件序列化到 "并行" 组件，则会返回安装错误。 例如：

-   **HRESULT 0x80073712**

当 sequencer 将并行组件写入注册表但不清除以下注册表项的值时，会导致此情况：

HKEY \ _LOCAL \ _MACHINE \\COMPONENTS\\StoreDirty

解决方法在运行 sequencer 的计算机上展开父程序包后，必须删除以下注册表项的值：

HKEY \ _LOCAL \ _MACHINE \\COMPONENTS\\StoreDirty

删除值后，将插件序列化。

### 发行说明版权信息

本文档 "按现状" 提供。 本文档中表示的信息和视图（如 URL 和其他 Internet 网站参考）可能会更改，恕不另行通知。 使用本文档的风险由你自己承担。

此处描述的一些示例仅供说明，并且是虚构的。 不打算或应该推断出真正的关联或连接。

本文档未向你提供针对任何 Microsoft 产品的任何知识产权的任何法律权限。 可以复制本文档并将其用于进行内部参考。 你可以出于内部参考目的修改此文档。



Microsoft、Active Directory、ActiveSync、ActiveX、Excel、SQL Server、Windows、Windows PowerShell、Windows Server 和 Windows Vista 是 Microsoft 组公司的商标。

所有其他商标的所有权属于其各自所有者。

 

 





