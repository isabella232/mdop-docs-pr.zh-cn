---
title: 规划客户端安全
description: 规划客户端安全
author: dansimp
ms.assetid: 4840a60f-4c91-489c-ad0b-6671882abf9b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: e0038f7cbc8592d6c7fcdfa485111da88c17791d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798870"
---
# 规划客户端安全


App-v 客户端提供了在产品的早期版本中不存在的多个安全增强功能。 这些更改提供了在安装后和客户端设置的后续配置中改进的安全性。 本主题介绍了其中一些增强功能，并标识了在规划过程中应考虑的一些重要的安全相关配置设置。 请务必记住，虚拟应用程序仍可执行，因此你必须确保这些资产不会被未经授权的人员篡改。 出于此原因，开放软件描述符（OSD）文件缓存受保护，如本主题后面部分所述，我们强烈建议你使用 RTSPS、HTTPS 和 IPsec 来保护发布和流式处理。

## App-v 客户端安全性


默认情况下，在安装时，app-v 客户端配置有允许用户执行发布刷新和启动应用程序所需的最低权限。 App-v 客户端中提供的其他安全增强功能包括以下内容：

-   默认情况下，OSD 文件缓存只能由管理员和通过使用发布刷新过程进行更新。

-   日志文件（sftlog.txt）只能通过对客户端具有本地管理访问权限的帐户进行访问。

-   日志文件现在具有最大大小。

### 文件类型关联

默认情况下，客户端的安装将注册 OSD 文件的文件类型关联（FTAs），从而使用户可以直接从 OSD 文件而不是已发布的快捷方式启动应用程序。 如果具有本地管理员权限的用户收到包含恶意代码的 OSD 文件（来自电子邮件或从网站下载），用户可以打开 OSD 文件并启动该应用程序，即使该客户已设置为限制 "**添加应用程序**" 权限。 你可以为 OSD 注销 FTAs 以减少此风险。 此外，请考虑在电子邮件系统和防火墙上阻止此扩展。 有关将 Outlook 配置为阻止扩展的详细信息，请参阅 <https://go.microsoft.com/fwlink/?LinkId=133278> 。

**安全说明：**

从应用程序第4.6 版开始，在新安装客户端期间，将不再为 OSD 文件创建文件类型关联，但在从 App-v 客户端版本4.2 或4.5 升级期间将保留现有设置。 如果出于任何原因需要创建文件类型关联，则可以创建以下注册表项并设置其值，如下所示：

    Create HKEY\_CLASSES\_ROOT\\.osd with a default value of SoftGrid.osd.File

    Under HKEY\_LOCAL\_MACHINE\\software\\classes\\Softgrid.osd.file, create a string value named AppUserModelID with a data value of Microsoft.AppV.Client.Tray

### 授权

在安装期间，你可以使用**RequireAuthorizationIfCached**参数将客户端配置为在用户尝试启动应用程序时要求从服务器授权。 应仔细考虑如何设置此参数。 如果 App-v server 因任何原因而不可用，应用程序将使用此参数的最新存储状态来控制用户对应用程序的访问权限。 如果用户在 App-v 服务器不可用之前未成功启动应用程序，则它们将无法启动应用程序，直到它们能够与服务器通信并接收授权。 但是，如果你设置参数以使客户端不需要授权，并且如果服务器不可用，则所有以前缓存的应用程序都可以启动，无论是否已授权。 此外，如果用户有权通过权限将客户端更改为工作脱机模式，或者如果用户是本地管理员，则用户可以打开所有缓存的程序包，就像应用 V 基础结构不可用一样。

### 防病毒扫描

在 App-v 客户端计算机上运行的防病毒软件可以在虚拟环境中检测和报告感染病毒的文件。 但是，它不能对文件进行杀毒。 如果在虚拟环境中检测到病毒，则防病毒软件将在缓存中执行已配置的隔离或修复操作，而不是实际程序包中的操作。 使用 sftfs 文件的例外配置防病毒软件。 此文件是将程序包存储在 App-v 客户端的缓存文件。

**安全说明：**

如果在生产环境中部署的应用程序或程序包中检测到病毒，请使用无病毒版本替换该应用程序或程序包。

## 客户端和服务器之间的通信


发布刷新和程序包流也是与客户端服务器通信相关的安全注意事项的区域。

### 发布刷新

当客户端与服务器通信以执行发布刷新时，它将使用已登录用户的凭据请求有关应用程序包的信息。 你应该确保应用 V 客户端和 App-v 管理服务器之间发生的通信安全，以确保在传输过程中不会篡改任何发布信息。 这是通过使用增强的安全选项完成的，该选项将使用 RTSPS/HTTPS。 客户端与要存储 .ICO 和 OSD 文件的位置之间的通信应使用适用于 SMB/CIFS 共享的 IPsec 和 IIS 服务器的 HTTPS。

**注意** 如果使用 IIS 发布 .ICO 和 OSD 文件，请为 OSD = TXT 配置 MIME 类型;否则，IIS 将拒绝向客户端提供 .ICO 和 OSD 文件。

 

### 程序包流

当用户首次启动应用程序时，或者如果在客户端上设置了自动加载参数，则会将应用程序包从服务器传输到客户端缓存。 此流程支持 RTSP/RTSPS、HTTP/HTTPS 和 SMB/CIFS 协议。 除非已在客户端上配置了**ApplicationSourceRoot**或**OverrideURL**设置，否则 OSD 文件将控制使用哪些协议。 你应该将通信配置为通过 RTSPS、HTTPS 或 IPsec for SMB/CIFS 进行通信，以获得更高的安全级别。 有关选择要使用的通信方法的详细信息，请参阅《 App-V 规划和部署指南》 <https://go.microsoft.com/fwlink/?LinkId=122063> 。

**注意** 如果使用 IIS 发布程序包（SFT 文件），请为 SFT = Binary 配置 MIME 类型;否则，IIS 将拒绝向客户提供 SFT 文件。

 

### 漫游配置文件和文件夹重定向

App-v 系统在 usrvol \ _sftfs \ _v1 installer.pkg 文件中存储对程序包的特定于用户的更改。 此文件位于用户配置文件的 "应用程序数据" 文件夹中。 由于配置文件或重定向的应用程序数据文件夹在客户端和服务器之间传输，因此请使用 IPsec 保护通信。

## 面向 Internet 的客户端的注意事项


对于面向 Internet 的客户端，请务必考虑客户端是否已加入域或是否未加入域。

### 加入域的客户端

默认情况下，App-v 客户端使用 Active Directory 域服务在 intranet 上进行身份验证和授权所颁发的 Kerberos 票证。 默认情况下，这些 Kerberos 票证的有效期为10小时。 只要票证有效，客户端就会使用此票证访问 app-v 服务器，即使计算机无法连接到域控制器来刷新票证也是如此。 如果 Kerberos 票证已过期，则 App-v 客户端将还原为 NTLM 身份验证，并使用用户的缓存凭据。

### 非域加入客户端

如果用户是基于 home 的用户，并且计算机未加入到公司域，则 App-v 仍可支持应用程序的提供。 若要对用户进行身份验证和授权以执行发布刷新并启动应用程序，请在客户端计算机上配置用户帐户以存储具有对 app-v 环境的访问权限的用户名和密码，并为应用程序提供相应的权限。

## 相关主题


[规划安全和保护](planning-for-security-and-protection.md)

 

 





