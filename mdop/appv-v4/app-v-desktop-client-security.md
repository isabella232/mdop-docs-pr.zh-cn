---
title: App-V Desktop Client 安全性
description: App-V Desktop Client 安全性
author: dansimp
ms.assetid: 216b9c16-7bb4-4f94-b9d8-810501285008
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 26add6f855780113613cf1591c41722643954477
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803144"
---
# App-V Desktop Client 安全性


App-v 桌面客户端提供了许多在产品的早期版本中不可用的安全增强功能。 默认情况下，这些更改通过客户端设置的配置提供更高的安全级别。

**注意** 在计算机上安装 app-v 桌面客户端时，该软件默认为最安全的设置。 但是，升级时，客户端的以前设置将保持不变。

 

默认情况下，仅使用允许非管理用户执行发布刷新和流应用程序所需的权限配置 app-v 桌面客户端。 App-v 桌面客户端中提供的其他安全增强功能包括以下内容：

-   默认情况下，仅当发布刷新过程才允许 OSD 缓存更新。

-   `sftlog.txt`只有具有客户端本地管理访问权限的帐户才能访问日志文件（）。

-   日志文件现在具有最大大小。

-   日志文件通过 "存档设置" 进行管理。

-   系统事件日志记录现已执行。

## 权限


安装桌面客户端后，可以通过 MMC 配置其他安全设置，也可以使用 Microsoft 提供的注册表或 ADM 模板配置单个客户端上的其他安全设置。 App-v 桌面客户端具有权限，你可以将其设置为限制非管理用户访问桌面客户端的所有功能。 有关权限的完整列表，请参阅应用程序-V 客户端帮助文件或 App-v 操作指南。

**重要提示** 请仔细考虑更改访问权限的后果，尤其是在多个用户共享的系统上（如终端服务器）。

 

**注意** 如果环境中的用户具有其计算机的本地管理员权限，则将忽略权限。

 

### ADM 模板

Microsoft Application Virtualization （App-v）引入了可用于通过组策略配置最常见的客户端设置的 ADM 模板。 通过此模板，管理员可以通过集中管理模型实施和更改许多客户端设置。 ADM 模板中的一些可用设置是安全设置。

**重要提示** 使用 ADM 模板时，请记住，设置是组策略首选项设置，而不是完全托管的组策略。

 

有关 ADM 模板的完整说明、特定设置以及在你的环境中成功部署客户端的指南，请参阅中的 App-v ADM 模板白皮书 [https://go.microsoft.com/fwlink/LinkId=122063](https://go.microsoft.com/fwlink/?LinkId=122063) 。

## 删除 OSD 文件类型关联


如果你的组织不要求用户直接从 OSD 文件打开应用程序，则可以通过删除客户端上的文件类型关联来增强安全性。 删除 `HKEY_CURRENT_USERS` 用于 OSD 和 `Softgird.osd.file` 使用注册表编辑器的键。 你可以将此过程放入登录脚本或安装后脚本以自动执行这些更改。

 

 





