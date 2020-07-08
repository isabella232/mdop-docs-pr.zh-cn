---
title: MBAM 1.0 发行说明
description: MBAM 1.0 发行说明
author: dansimp
ms.assetid: d82fddde-c360-48ef-86a0-d9b5fe066861
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 705fd1b936da1454081dd14a7f075f642fc4a405
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803886"
---
# MBAM 1.0 发行说明


**若要在这些发行说明中搜索特定问题，请按 CTRL + F。**

安装 Microsoft BitLocker 管理和监视（MBAM）之前，请仔细阅读这些发行说明。

这些发行说明包含成功安装 MBAM 所需的信息。 发行说明还包含产品文档中不可用的信息。 如果这些发行说明和其他 MBAM 文档之间存在差异，则应将最新更改视为权威。 这些发行说明取代了本产品附带的内容。

## 关于产品文档


有关 MBAM 文档的信息，请参阅 Microsoft TechNet 上的 MBAM 主页。

若要获取 MBAM 文档的可下载副本，请参阅 <https://go.microsoft.com/fwlink/p/?LinkId=225356> Microsoft 下载中心。

## 提供反馈


我们对 MBAM 的反馈感兴趣。 您可以向发送反馈 <mdopdocs@microsoft.com> 。

**注意** 此电子邮件地址不是支持频道，但你的反馈将帮助我们为我们的文档和产品发布计划未来的更改。

 

有关 MDOP 和其他学习资源的最新信息，请参阅[Mdop 信息体验](https://go.microsoft.com/fwlink/p/?LinkId=236032)页面。

有关新更新或提供反馈的详细信息，请在[Facebook](https://go.microsoft.com/fwlink/p/?LinkId=242445)或[Twitter](https://go.microsoft.com/fwlink/p/?LinkId=242447)上关注我们。

## MBAM 1.0 的已知问题


本部分包含有关 MBAM 设置和安装的已知问题的发行说明。

### <a href="" id="if-you-select-the--use-a-certificate-to-encrypt-the-network-communication--option-during-setup--existing-database-connections-and-dependent-applications-can-stop-functioning-"></a>如果在安装过程中选择 "使用证书加密网络通信" 选项，则现有数据库连接和依赖应用程序可能停止运行

在安装了恢复和硬件数据库或合规性状态数据库功能之后，你可以配置 MBAM 以进行**加密的网络通信**。 如果你选择为加密网络通信配置 MBAM，MBAM 安装程序会将 SQL Server 数据库引擎的实例配置为使用安全套接字层（SSL），以便在适用数据库之间以及管理和监视服务器以及合规性和审核报表服务器功能之间进行通信。

-   如果 SQL Server 数据库引擎的实例尚未配置为使用 SSL，MBAM 安装程序会将其配置为使用 SSL。 这可以防止尝试在 SQL Server 数据库引擎实例上使用非 MBAM 数据库的应用程序与它们的数据库进行通信。

-   如果 SQL Server 数据库引擎的实例已配置为使用 SSL，则将其配置为使用用户在安装过程中选择的证书。 如果此证书与已使用的证书不同，则可以阻止在 SQL Server 数据库引擎实例上使用 SQL Server 数据库的应用程序运行。

**解决方法：** 尚

### 使用本地管理员帐户时，MBAM 安装程序在安装过程中失败

使用本地管理员帐户时，MBAM 安装程序将失败。 日志文件包含以下信息：

``` syntax
Locating group 'MBAM Report Users'
Adding <GUID>' to group 'MBAM Report Users'
Locating group 'MBAM Recovery and Hardware DB Access'
Adding 'S-1-5-20' to group 'MBAM Recovery and Hardware DB Access'
Exception: A new member could not be added to a local group because the member has the wrong account type.
 
  StackTrace:    at System.DirectoryServices.AccountManagement.SAMStoreCtx.UpdateGroupMembership(Principal group, DirectoryEntry de, NetCred credentials, AuthenticationTypes authTypes)
   at System.DirectoryServices.AccountManagement.SDSUtils.ApplyChangesToDirectory(Principal p, StoreCtx storeCtx, GroupMembershipUpdater updateGroupMembership, NetCred credentials, AuthenticationTypes authTypes)
   at System.DirectoryServices.AccountManagement.SAMStoreCtx.Update(Principal p)
   at Microsoft.Windows.Mdop.BitlockerManagement.Setup.Groups.CreateGroupsDeferred(Session session)
  InnerException:Exception: A new member could not be added to a local group because the member has the wrong account type.
 
    InnerException:StackTrace:    at System.DirectoryServices.AccountManagement.UnsafeNativeMethods.IADsGroup.Add(String bstrNewItem)
   at System.DirectoryServices.AccountManagement.SAMStoreCtx.UpdateGroupMembership(Principal group, DirectoryEntry de, NetCred credentials, AuthenticationTypes authTypes)
CustomAction MbamCreateGroupsDeferred returned actual error code 1603 (note this may not be 100% accurate if translation happened inside sandbox)
Action ended 11:41:29: InstallExecute. Return value 3.
```

**解决方法：** 在安装 MBAM 时，在服务器计算机上使用具有管理凭据的域帐户。

### 如果你选择 "不加密网络通信"，MBAM 安装程序会将 SQL Server 数据库引擎的实例重新配置为不使用 SSL

在安装恢复和硬件数据库或合规性状态数据库时，可以通过选择**加密的网络通信**来使用安装程序配置 MBAM。 如果您决定不加密网络通信，MBAM 安装程序将重新配置 SQL Server 数据库引擎的实例，以使其不使用 SSL。

-   如果 SQL Server 数据库引擎的实例已配置为使用 SSL，MBAM 安装程序将在 SQL Server 数据库引擎的实例上禁用 SSL。 这将更改在 SQL Server 数据库引擎实例上使用与 MBAM 数据库无关的数据库的应用之间的通信安全。

**解决方法：** 尚

### 缺少 Internet Information Services （IIS）管理脚本和工具 web 服务器功能的先决条件

MBAM 安装程序依赖于 IIS 管理脚本和工具 web 服务器功能，但不是强制先决条件。 服务器设置允许你在缺少此功能时安装 MBAM。 但是，这将导致备份服务 MBAM VSS 编写器启动然后停止，因为它无法找到 Windows Management Instrumentation （WMI）和 Internet Information Services （IIS）提供程序。 除了事件日志中发生的情况外，此条件没有错误消息。 不带 IIS 管理脚本和工具的 MBAM 安装会导致不为 MBAM 运行备份操作。

**解决方法：** 在启动 MBAM 安装程序之前，请确保已安装 IIS 管理脚本和工具 web 服务器功能。

### <a href="" id="mbam-setup-stops-responding-during-the--installing-selected-features--phase-when-setup-is-configured-to-use-a-certificate"></a>设置配置为使用证书时，在 "安装所选功能" 阶段，MBAM 安装程序停止响应

MBAM 安装程序在安装的 "**安装选定的功能**" 阶段期间停止响应。 在恢复和硬件数据库或合规性状态数据库的安装过程中，选择 "**使用证书加密网络通信"** 选项时，会发生这种情况。 此外，如果 SQL Server 数据库引擎的实例无法访问在安装过程中指定的证书，MBAM 安装程序将停止响应。

**解决方法：** 更新对证书的权限，以便适用于 SQL Server 数据库引擎的适用实例的 Windows 服务可以访问该证书。 你还可以更改 SQL Server 数据库引擎实例的运行帐户，以便数据库引擎使用该证书。 若要确定证书的权限，请在命令提示符处键入以下命令： **certutil-v-存储 MY**

### 安装 SQL Server Reporting Services 时，MBAM 安装程序暂停

在 MBAM 安装期间，如果你选择 SQL Server Reporting Services （SSRS）实例，并且 SSRS 实例的配置不正确，则 MBAM 安装程序在尝试与 SSRS 实例通信时最多可能暂停一分钟。

**解决方法：** 在安装程序尝试联系 SSRS 实例时，请至少等待一分钟，MBAM 设置才能恢复。

### <a href="" id="administration-and-monitoring-server-does-not-run-after-setup-"></a>安装后，管理和监视服务器不运行

当 MBAM 安装成功安装 "管理和监视服务器" 功能后，当你尝试访问 MBAM 管理员网站时，MBAM 会显示错误消息。 出现此问题的原因有以下几种：

-   在 MBAM 安装之后，已删除管理和监视服务器上的一个或多个先决条件。

-   在服务器上安装了一个或多个先决条件，并且在运行 MBAM 安装程序之前已将其删除。

**解决方法：** 查看 MBAM 文档并确认已安装所有 MBAM 先决条件。

### 在安装过程中单击文档链接会导致安装完成后出现应用程序错误

在设置过程中单击文档链接，然后在安装程序成功完成后单击 "**取消**" 或 "**完成**" 以关闭安装程序时，将显示应用程序错误消息。 此问题是由 Windows 任务计划程序中的访问冲突错误导致的。

**解决方法：** 尚. 您可以忽略此错误。

### 失败的 MBAM 安装程序不会删除新数据库

如果 MBAM 设置失败，则安装程序可能不会删除新创建的数据库。 这可能会导致后续安装期间失败。

**解决方法：** 在后续安装期间为数据库实例选择其他名称。

### MBAM 安装程序不识别有效的网络负载平衡群集证书

在 MBAM 管理和监视服务器安装期间，如果选择了 "网络加密" 选项，则不会将群集证书识别为有效证书。 当已安装与数据库通信的证书时，它被识别为有效，但负载平衡群集拒绝通信。

**解决方法：** 确认与证书相关联的证书吊销列表（CRL）是可访问的，或者使用不需要使用 CRL 进行验证的证书。

## 发行说明版权信息


Microsoft、Active Directory、ActiveX、Bing、Excel、Silverlight、SQLServer、Windows、MicrosoftIntune 和 WindowsPowerShell 是 Microsoft 公司组的商标。 所有其他商标的所有权属于其各自所有者。



## 相关主题


[关于 MBAM 1.0](about-mbam-10.md)

 

 





