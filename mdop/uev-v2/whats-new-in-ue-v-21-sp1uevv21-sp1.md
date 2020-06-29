---
title: UE-V 2.1 SP1 中的新增功能
description: UE-V 2.1 SP1 中的新增功能
author: dansimp
ms.assetid: 9a40c737-ad9a-4ec1-b42b-31bfabe0f170
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 1f4b6210d95795c352a7ef1402b0353c6f52774b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804166"
---
# UE-V 2.1 SP1 中的新增功能


用户体验虚拟化 2.1 SP1 提供与 UE-V 2.1 相比的这些新功能和功能。 [Microsoft 用户体验虚拟化（ue-v） 2.1 Sp1 发行说明](microsoft-user-experience-virtualization--ue-v--21-sp1-release-notes.md)提供有关 UE-V 2.1 SP1 版本的详细信息。

## Windows 10 支持


UE-V 2.1 SP1 除了支持早期版本的 UE-V 支持的同一软件外，还添加了对 Windows 10 的支持。

### 与 Microsoft Azure 的兼容性

Windows 10 允许企业用户将 Windows 应用设置和 Windows 操作系统设置同步到 Azure，而不是 OneDrive。 你可以将 Windows 10 企业版同步功能与 UE-V 配合使用，仅限本地域的计算机。 若要启用 Windows 10 与 UE-V 之间的共存，必须在每个客户端或组策略上使用任何 PowerShell 禁用以下 UE-V 模板。

在 "组策略" 中的 "Microsoft 用户体验虚拟化" 节点下，配置以下策略设置：

-   启用 "不同步 Windows 应用"

-   禁用 "同步 Windows 设置"

### Windows 10 支持的设置同步行为已更改

UE-V 2.1 SP1 在 Windows 10 设备之间漫游任务栏设置。 但是，UE-V 不会在运行以前操作系统的 Windows 10 设备和设备之间同步任务栏设置。

此外，UE-V 2.1 SP1 不会同步 Windows 10 中的 Microsoft 计算器与以前操作系统中的 Microsoft 计算器之间的设置。

## 为漫游网络打印机添加的支持


UE-V 2.1 SP1 允许网络打印机在设备之间漫游，以便用户登录到网络上的任何设备时可以访问其网络打印机。 这包括将其设置为默认打印机的漫游打印机。

UE-V 中的打印机漫游需要以下其中一种方案：

-   打印服务器在漫游到新设备时可以下载所需的驱动程序。

-   漫游网络打印机的驱动程序已在需要访问该网络打印机的任何设备上预安装。

-   可以从 Windows Update 获取打印机驱动程序。

**注意** UE-V 打印机漫游**功能不会漫游打印机**设置或首选项，例如双面打印。

 

## Office 2013 设置位置模板


UE-V 2.1 和 2.1 SP1 包括 Microsoft Office 2013 设置位置模板以及改进的 Outlook 签名支持。 我们已为新的、答复和转发的电子邮件添加了默认签名设置的同步。 客户无需再选择默认签名设置。

**注意** 必须为用户要同步其 Outlook 签名的任何设备创建 Outlook 配置文件。 如果尚未创建配置文件，则用户可以创建一个配置文件，然后在该设备上重新启动 Outlook 以启用签名同步。

 

以前的 UE-V 包括 Microsoft Office 2010 设置位置模板，这些位置模板是通过 UE-V Agent 自动分发和注册的。 UE-V 2.1 与 Office 365 配合使用，确定 office 2013 设置是否由 Office 365 漫游。 如果设置由 Office 365 漫游，则他们不会通过 UE-V 进行漫游。 [Office 2013 的用户和漫游设置概述](https://go.microsoft.com/fwlink/p/?LinkID=391220)提供详细信息。

若要使用 UE-V 2.1 启用设置同步，请执行下列操作之一：

-   使用组策略禁用 Office 365 同步

-   不启用 Office 2013 安装期间的 Office 365 同步体验

UE-V 2.1 随附[Office 2013 和 office 2010 模板](https://technet.microsoft.com/library/dn458932.aspx#autosyncsettings)。 此版本将删除 Office 2007 模板。 用户仍然可以使用 UE-V 2.0 或更早版本的 Office 2007 模板，并且仍然可以从位于[此处](https://go.microsoft.com/fwlink/p/?LinkID=246589)的 ue-v 模板库中获取模板。






## 相关主题


[UE-V 2.x 入门](get-started-with-ue-v-2x-new-uevv2.md)

[准备 UE-V 2. x 部署](prepare-a-ue-v-2x-deployment-new-uevv2.md)

[Microsoft 用户体验虚拟化 (UE-V) 2.1 SP1 发行说明](microsoft-user-experience-virtualization--ue-v--21-sp1-release-notes.md)

 

 





