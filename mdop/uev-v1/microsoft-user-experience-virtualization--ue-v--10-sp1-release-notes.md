---
title: Microsoft 用户体验虚拟化 (UE-V) 1.0 SP1 发行说明
description: Microsoft 用户体验虚拟化 (UE-V) 1.0 SP1 发行说明
author: dansimp
ms.assetid: 447fae0c-fe87-4d1c-b616-6f92fbdaf6d5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 8584999d9fdbdfccc3e9b2b1486cb97635475747
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798057"
---
# Microsoft 用户体验虚拟化 (UE-V) 1.0 SP1 发行说明


若要搜索 Microsoft 用户体验虚拟化（UE-V） 1.0 Service Pack 1 发行说明，请按 Ctrl + F。

在安装 UE-V 之前，应仔细阅读这些发行说明。 发行说明包含成功安装用户体验虚拟化所需的信息，并包含产品文档中不可用的其他信息。 如果这些发行说明和其他 UE-V 文档之间存在差异，则应将最新更改视为权威。 这些发行说明取代了本产品附带的内容。

## UE-V 已知问题


本部分包含适用于用户体验虚拟化 1.0 SP1 的发行说明。

### 注册表设置无法在同一台计算机上的 App-v 和本机应用程序之间同步

当计算机具有通过应用程序虚拟化（app-v）应用程序和随 Windows Installer （.msi 文件）安装的本机安装应用程序提供的应用程序时，基于注册表的设置不会在技术之间同步。

解决方法：若要解决此问题，请通过选择两种技术之一来运行应用程序，但不能同时选择二者。

### <a href="" id="windows-8-setting-synchronization-fails-when-network-share-is-outside-user-s-domain"></a>当网络共享位于用户域之外时，Windows 8 设置同步失败

当 Windows®8尝试运行操作系统设置同步时，synchrnization 失败，并出现以下错误消息：**提升：： filesystem：：存在：：错误的用户名或密码**。 此错误可能表示网络共享位于用户域之外。 若要检查操作日志事件，请打开**事件查看器**并导航到**应用程序和服务记录**  /  **Microsoft**  /  **用户体验虚拟化**  /  **日志记录**  /  **操作**。 用于 UE-V 设置的网络共享的存储位置应位于与用户相同的 Active Directory 域中。

解决方法：使用与用户相同的 Active Directory 域中的网络共享。 .

### Outlook 2010 的电子邮件签名漫游

UE-V 将在设备之间漫游 Outlook 2010 签名文件。 但是，新邮件和答复/转发的默认签名选项不是漫游。 这两个设置存储在 Outlook 配置文件中，而 UE-V 不会漫游。

解决方法：无。

### 在慢速链接模式下运行时，同步设置不会按预期的间隔同步

在 "正常情况下，设置存储位置" 应在快速链接网络连接上可用。 在慢速链接模式下，同步只会定期发生。 默认情况下，慢速链接模式同步计划将设置为每360分钟。

解决方法：若要在慢速链接模式下更改计算机的后台同步的频率，可以为**脱机文件**配置后台同步策略的组策略。

### 特殊字符不同步

某些字符（如货币符号）不在运行 UE-V agent 的 Windows 7 和 Windows 8 计算机之间同步。

解决方法：无。

### UE-V 不支持32位和64位版本的 Microsoft Office 之间的漫游设置

我们建议你为32位和64位操作系统安装32位版本的 Microsoft Office。 若要选择所需的 Microsoft Office 版本，请单击 "此处" （ [http://office.microsoft.com/word-help/choose-the-32-bit-or-64-bit-version-of-microsoft-office-HA010369476.aspx](https://go.microsoft.com/fwlink/?LinkID=247623) ）。 UE-V 支持 Office 的相同体系结构版本之间的漫游设置。 例如，32位 Office 设置将在所有32位 Office 实例之间漫游。 UE-V 不支持32位和64位版本的 Office 之间的漫游设置。

解决方法：无

### <a href="" id="msi-s-are-not-localized"></a>MSI 未本地化

UE-V 1.0 SP1 包括用于 UE-V Agent 和 UE-V 发生器的本地化设置程序。 这些 MSI 文件仍然可用，但用户界面已最小化，并且 MSI 仅以英语显示。 尽管文件是英语，安装程序也会在安装期间安装所有支持的语言。

解决方法：无

### 具有设置存储位置的共享上的其他文件夹在慢速连接模式下不可用

设置存储共享不应位于用于其他必须始终可用的文件夹的网络共享上。 当托管设置存储位置的网络共享进入慢速连接模式时，唯一可用的文件夹是 "设置存储位置" 文件夹。 共享上的其他文件夹在慢速连接模式下不可用。

解决方法：无

### 与 Internet Explorer 9 收藏夹相关联的 Favicons 不漫游

与 Internet Explorer 9 常用联系人相关联的 favicons 不是由用户体验虚拟化漫游的，并且在新计算机上首次显示收藏时不会显示。

解决方法：在 Internet Explorer 9 浏览器中使用并缓存书签后，Favicons 将显示相关联的常用联系人。

### 文件设置路径存储在注册表中

某些应用程序设置将其配置和设置文件的路径存储为注册表中的值。 当设置在计算机之间漫游时，必须同步在注册表中作为路径引用的文件。

解决方法：使用 "文件夹重定向" 或其他技术确保作为文件设置路径引用的所有文件都存在并放置在 "设置" 漫游的所有计算机上的相同位置。

### 较长设置存储路径可能会导致错误

使设置存储路径尽可能简短。 长路径可能会阻止分辨率或同步。 UE-V 使用设置存储路径作为存储设置的计算路径的一部分。 该路径按以下方式计算：设置存储路径 + "settingspackages" + 程序包目录（模板 ID） + 软件包名称（模板 ID）。 如果该计算路径超过260个字符，则软件包存储将失败，并在 UE-V 操作事件日志中生成以下错误消息：

`[boost::filesystem::copy_file: The system cannot find the path specified]`

若要检查操作日志事件，请打开事件查看器并导航到 "应用程序和服务日志/Microsoft/用户体验虚拟化/登录/运行"。

解决方法：无。

### UE-V agent 在注销或登录时延迟

如果在 "脱机文件" 确定较慢的链接已到位之前发生登录或注销，则可能会延迟注销或登录。 "脱机文件" 功能可能需要长达三分钟才能检测当前的网络状态。 如果在脱机文件确定计算机连接到慢速链接之前发生登录或关机，则 UE-V 设置程序包将发送到服务器而不是本地缓存。

解决方法：无。

### 尝试在 Windows 8 上漫游操作系统设置时出现设置冲突

在 Windows 8 上，如果已启用 Microsoft 帐户同步以及操作系统设置的 UE-V，则应用的设置可能不一致。

解决方法：执行下列操作之一：

-   如果你使用 UE-V 漫游操作系统设置，则禁用 Microsoft 帐户同步

-   禁用操作系统设置的 UE-V

### 某些操作系统设置仅在类似操作系统版本之间漫游

面向讲述人的操作系统设置和特定于区域设置的货币字符将仅在 Windows 的操作系统版本上漫游。 例如，货币字符将仅从 Windows 7 漫游到 Windows 7。

解决方法：无

 

 





