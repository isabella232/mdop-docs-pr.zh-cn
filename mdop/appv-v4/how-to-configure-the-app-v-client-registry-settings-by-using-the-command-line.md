---
title: 如何使用命令行配置 App-V Client 注册表设置
description: 如何使用命令行配置 App-V Client 注册表设置
author: dansimp
ms.assetid: 3e3d873f-13d2-402f-97b4-f62d0c399171
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: c424f39c8209ca641f6073838ebcb8726acc9e25
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801600"
---
# 如何使用命令行配置 App-V Client 注册表设置


在使用命令行在安装过程中部署和配置应用程序虚拟化（App-v）客户端之后，可能需要更改一个或多个客户端配置设置。 这可以通过使用以下方法之一编辑相应的注册表项来实现：

-   直接使用注册表编辑器

-   使用 .reg 文件

-   使用脚本语言（如 VBScript 或 Windows PowerShell）

还有一个您可以使用的 ADM 模板。 有关 ADM 模板的详细信息，请参阅 <https://go.microsoft.com/fwlink/?LinkId=121835> 。

**小心** 编辑注册表时使用小心，因为错误可能会使计算机处于无法使用的状态。 请务必遵循与注册表编辑相关的标准业务做法。 在将测试环境中的所有建议的更改部署到生产计算机之前，对它们进行全面测试。

 

## 本部分内容


**重要提示** 在64位计算机上，以下部分中介绍的键和值将在 HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid\\4.5\\Client. 下。

 

<a href="" id="how-to-reset-the-filesystem-cache"></a>[如何重置 FileSystem 缓存](how-to-reset-the-filesystem-cache.md)  
提供重置文件系统缓存所需的信息。

<a href="" id="how-to-change-the-size-of-the-filesystem-cache"></a>[如何更改 FileSystem 缓存的大小](how-to-change-the-size-of-the-filesystem-cache.md)  
介绍如何更改缓存的大小。

<a href="" id="how-to-use-the-cache-space-management-feature"></a>[如何使用缓存空间管理功能](how-to-use-the-cache-space-management-feature.md)  
介绍如何配置缓存空间管理功能。

<a href="" id="how-to-configure-the-client-log-file"></a>[如何配置客户端日志文件](how-to-configure-the-client-log-file.md)  
介绍控制客户端日志文件的各种注册表项值以及如何更改它们。

<a href="" id="how-to-configure-user-permissions"></a>[如何配置用户权限](how-to-configure-user-permissions.md)  
标识控制用户权限的注册表项，并提供有关如何更改某些权限的示例。

<a href="" id="how-to-configure-the-client-for-application-package-retrieval"></a>[如何配置客户端以进行应用程序包检索](how-to-configure-the-client-for-application-package-retrieval.md)  
介绍如何配置客户端以检索不同源中的程序包内容、图标和文件类型关联，并提供了正确路径格式的几个示例。

<a href="" id="how-to-configure-the-client-for-disconnected-operation-mode"></a>[如何为断开连接操作模式配置客户端](how-to-configure-the-client-for-disconnected-operation-mode.md)  
提供有关如何配置与断开连接的操作模式关联的各种设置的信息。

<a href="" id="how-to-configure-shortcut-and-file-type-association-behavior"></a>[如何配置快捷方式和文件类型关联行为](how-to-configure-shortcut-and-file-type-association-behavior-46-only.md)  
介绍用于控制应用程序-V 客户端中的快捷方式和文件类型关联的注册表项值，并提供有关如何配置它们的详细信息。

## 相关主题


[Application Virtualization Client](application-virtualization-client.md)

 

 





