---
title: UE-V 2.1 中的新增功能
description: UE-V 2.1 中的新增功能
author: dansimp
ms.assetid: 7f385183-7d97-4602-b19a-baa710334ade
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 7816fc8309a29347048172b2104750140c483587
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803933"
---
# UE-V 2.1 中的新增功能


用户体验虚拟化2.1 提供了与 UE-V 2.0 相比的这些新功能和功能。 [Microsoft 用户体验虚拟化（ue-v）2.1 发行说明](microsoft-user-experience-virtualization--ue-v--21-release-notesuevv21.md)提供了有关 ue-v 2.1 版本的详细信息。

## Office 2013 设置位置模板


UE-V 2.1 包括 Microsoft Office 2013 设置位置模板，改进了 Outlook 签名支持。 在 UE-V 2.1 中，签名数据在用户设备之间同步。 我们已为新的、答复和转发的电子邮件添加了默认签名设置的同步。 客户无需再选择默认签名设置。

**注意** 必须为用户要同步其 Outlook 签名的任何设备创建 Outlook 配置文件。 如果尚未创建配置文件，则用户可以创建一个配置文件，然后在该设备上重新启动 Outlook 以启用签名同步。

 

以前的 UE-V 包括 Microsoft Office 2010 设置位置模板，这些位置模板是通过 UE-V Agent 自动分发和注册的。 UE-V 2.1 与 Office 365 配合使用，确定 office 2013 设置是否由 Office 365 漫游。 如果设置由 Office 365 漫游，则他们不会通过 UE-V 进行漫游。 [Office 2013 的用户和漫游设置概述](https://go.microsoft.com/fwlink/p/?LinkID=391220)提供详细信息。

若要使用 UE-V 2.1 启用设置同步，请执行下列操作之一：

-   使用组策略禁用 Office 365 同步

-   不启用 Office 2013 安装期间的 Office 365 同步体验

UE-V 2.1 随附[Office 2013 和 office 2010 模板](https://technet.microsoft.com/library/dn458932.aspx#autosyncsettings)。 此版本将删除 Office 2007 模板。 用户仍然可以使用 UE-V 2.0 或更早版本的 Office 2007 模板，并且仍然可以从位于[此处](https://go.microsoft.com/fwlink/p/?LinkID=246589)的 ue-v 模板库中获取模板。

## 修复分布式文件系统命名空间用户


UE-V 通过添加名为 SyncProviderPingEnabled 的 UE-V 配置改进了分布式文件系统命名空间（DFSN）支持。 使用 PowerShell 或 WMI 禁用此配置允许用户禁用 UE-V ping。 在使用 DFSN 服务器时，UE-V ping 会导致错误，因为这些服务器不响应 ping 操作。 非响应可防止 UE-V 进行同步设置。 禁用 UE-V ping 允许 UE-V 同步正常工作。

若要禁用 UE-V ping，请使用此 PowerShell cmdlet：

``` syntax
Set-UevConfiguration -DisableSyncProviderPing
```

## 凭据同步


UE-V 2.1 使客户能够同步存储在 Windows 凭据管理器中的凭据和证书。 默认情况下，此组件处于禁用状态。 启用此组件可使用户保持其域凭据和证书同步。用户可以在设备上一次登录，这些凭据将在其所有支持 UE-V 的设备上漫游。 [通过 ue-v 2.1 管理凭据](https://technet.microsoft.com/library/dn458932.aspx#creds)可提供更多信息。

**注意** 在 Windows 8 及更高版本中，凭据管理器包含 web 凭据。 这些凭据不会在用户的设备之间同步。

 

## UE-V 和 Microsoft 帐户同步


UE-V 检测 "带有 OneDrive 的同步设置" （也称为 Microsoft 帐户同步）是否已启用。 如果 Microsoft 帐户未配置为同步设置，则 UE-V 会同步设备之间的 Windows 应用、AppX 程序包和 Windows 桌面设置。 这使用户可以访问其应用商店应用、音乐、图片和其他 Microsoft 帐户启用的应用程序，而无需在企业防火墙外同步。 UE-V 检查组策略是否将停止将设置与 OneDrive 同步，或者如果用户在此计算机上禁用了用户控件中的 **"同步您的设置**"。

## 支持 Powerschool 外部


名为**External**的新[powerschool 配置](https://technet.microsoft.com/library/dn554321.aspx)指定如果 ue-v 设置写入到用户计算机上的本地文件夹，则可以使用任何外部同步引擎（如 OneDrive For business、工作文件夹、Sharepoint 或 Dropbox）将这些设置应用于用户访问的不同计算机。

## 对 VDI 模式的增强支持


UE-V 2.1 包括对在最终用户之间共享的[VDI 会话的支持](https://technet.microsoft.com/library/dn458932.aspx#vdi)。 作为管理员，你可以注册和配置特殊的 VDI 模板，从而确保 UE-V 将其所有功能完整地保留给非持久的 VDI 会话。

**注意** 如果不为非永久性 VDI 会话启用 VDI 模式，则某些功能不起作用，例如备份/还原和 LKG。

 

## 管理员备份和还原


通过使用 UevTemplateProfile PowerShell cmdlet 将设置位置模板放在 "**备份**" 或 "**漫游" （默认）** 配置文件中，你可以在用户采用新设备时还原其他设置。 除了用户设置外，此功能还允许将计算机设置与新计算机同步。 为该设备备份分配给备份配置文件的模板，并基于每台设备进行配置。 [在 ue-v 2 中管理管理备份和还原。 x](manage-administrative-backup-and-restore-in-ue-v-2x-new-topic-for-21.md)提供详细信息。

## 其他 Windows 设置的同步


UE-V 现在将同步触摸键盘个性化设置、拼写词典，并启用应用切换 "最近的应用" 和 "屏幕边缘" 设置，以便在 Windows 8 和 Windows 8.1 设备之间进行同步。






## 相关主题


[UE-V 2.x 入门](get-started-with-ue-v-2x-new-uevv2.md)

[准备 UE-V 2. x 部署](prepare-a-ue-v-2x-deployment-new-uevv2.md)

[Microsoft 用户体验虚拟化 (UE-V) 2.1 发行说明](microsoft-user-experience-virtualization--ue-v--21-release-notesuevv21.md)

 

 





