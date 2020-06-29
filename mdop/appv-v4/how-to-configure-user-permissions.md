---
title: 如何配置用户权限
description: 如何配置用户权限
author: dansimp
ms.assetid: 54e69f46-b028-4ad1-9b80-f06ef5c8f559
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 3c2581a9f9dddcbc63682d356c777a24222dd62f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801535"
---
# 如何配置用户权限


你可以通过编辑**权限**注册表项（HKEY \ _LOCAL \ _MACHINE \\software\\microsoft\\softgrid\\4.5\\client\\permissions）下的键值，为没有管理权限的用户启用和禁用某些操作。 此密钥主要用于帮助防止用户犯错误，而不是为了提供任何特殊安全性，因为具有管理权限的用户可以编辑这些键值中的任何一个值。 以下过程是有关如何更改键值的示例。 有关应用程序虚拟化（app-v）客户端注册表项和值的详细信息，请参阅 <https://go.microsoft.com/fwlink/?LinkId=121528> 。

**更改用户权限**

1.  若要使用户可以选择在脱机模式下运行客户端，请将以下键值设置为1：

    HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Permissions\\ToggleOfflineMode

2.  若要使用户能够通过用户界面查看所有应用程序，请将以下项值设置为1。 将该值设置为0（零）允许用户仅查看可用的应用程序。

    HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Permissions\\ViewAllApplications

## 相关主题


[如何使用命令行配置 App-V Client 注册表设置](how-to-configure-the-app-v-client-registry-settings-by-using-the-command-line.md)

[Application Virtualization Client 中的用户访问权限](user-access-permissions-in-application-virtualization-client.md)

 

 





