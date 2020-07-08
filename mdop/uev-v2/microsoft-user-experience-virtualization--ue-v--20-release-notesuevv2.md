---
title: Microsoft 用户体验虚拟化 (UE-V) 2.0 发行说明
description: Microsoft 用户体验虚拟化 (UE-V) 2.0 发行说明
author: dansimp
ms.assetid: 5ef66cd1-ba2b-4383-9f45-e7cde41f1ba1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: ad3deffa5cd567a70711e5447197e630f04ea254
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803737"
---
# Microsoft 用户体验虚拟化 (UE-V) 2.0 发行说明


若要搜索 Microsoft 用户体验虚拟化（UE-V）2.0 发行说明，请按 Ctrl + F。

在安装 UE-V 之前，应仔细阅读这些发行说明。 发行说明包含成功安装用户体验虚拟化所需的信息，并包含产品文档中不可用的其他信息。 如果这些发行说明和其他 UE-V 文档之间存在差异，则应将最新更改视为权威。 这些发行说明取代了本产品附带的内容。

## 提供反馈


通过向我们提供反馈和评论，告诉我们您对 MDOP 文档的看法。 将文档反馈发送到[mdopdocs@microsoft.com](mailto:mdopdocs@microsoft.com?subject=UE-V%20Documentation)。

## UE-V 已知问题


本部分包含适用于用户体验虚拟化的发行说明。

### 注册表设置不在同一台计算机上的 app-v 和本机应用程序之间同步

当计算机具有通过应用程序虚拟化（app-v）和本地使用 Windows Installer （.msi）文件安装的应用程序时，基于注册表的设置不会在技术之间同步。

**解决方法：** 若要解决此问题，请通过选择两种技术之一来运行应用程序，但不能同时选择二者。

### <a href="" id="settings-do-not-synchronization-when-network-share-is-outside-user-s-domain"></a>当网络共享位于用户域之外时，设置不同步

当 Windows®8尝试运行操作系统设置同步时，同步失败，并出现以下错误消息：**提升：： filesystem：：存在：：错误的用户名或密码**。 此错误可指示网络共享位于用户域或与该域有信任关系的域之外。 若要检查操作日志事件，请打开**事件查看器**并导航到**应用程序和服务记录**  /  **Microsoft**  /  **用户体验虚拟化**  /  **日志记录**  /  **操作**。 用于 UE-V 设置的网络共享的存储位置应位于与用户或用户域的受信任域相同的 Active Directory 域中。

**解决方法：** 使用与用户相同的 Active Directory 域中的网络共享。

### 安装了 Office 2010 和 Office 2013 时不可预测的结果

如果用户安装了 Office 2010 和 Office 2013，则两个版本的 Office 之间的任何常见设置都通过 UE-V 漫游。 这可能会导致 Office 2010 程序包大小相当大或导致与2013的不可预知的冲突，尤其是在使用 Office 365 时。

**解决方法：** 仅安装一个版本的 Office，或限制由 UE-V 同步的设置。

### 卸载并重新安装 Windows 8 应用会将设置还原为初始状态

使用 UE-V 设置同步处理 Windows 8 应用时，如果用户卸载应用，然后重新安装该应用，则应用的设置将还原为其默认值。发生这种情况是因为卸载删除了应用设置的本地（缓存）副本，但不会删除本地 UE-V 设置程序包。当应用重新安装并启动时，UE-V 收集重置为应用默认设置的应用设置，然后将默认设置上载到中央存储位置。然后，运行应用的其他计算机将下载默认设置。此行为与桌面应用程序的行为相同。

**解决方法：** 尚.

### Outlook 2010 的电子邮件签名漫游

UE-V 将在设备之间漫游 Outlook 2010 签名文件。 但是，不会同步新邮件和答复或转发的默认签名选项。 这两个设置存储在 Outlook 配置文件中，而 UE-V 不会漫游。

**解决方法：** 尚.

### UE-V 不支持32位和64位版本的 Microsoft Office 之间的漫游设置

我们建议你安装适用于新式计算机的64位版本的 Microsoft Office。 若要确定所需的版本，请[单击此处](https://support.office.com/article/choose-between-the-64-bit-or-32-bit-version-of-office-2dee7807-8f95-4d0c-b5fe-6c6f49b8d261?ui=en-US&rs=en-US&ad=US#32or64Bit=Newer_Versions)。 UE-V 支持 Office 的相同体系结构版本之间的漫游设置。 例如，32位 Office 设置将在所有32位 Office 实例之间漫游。 UE-V 不支持32位和64位版本的 Office 之间的漫游设置。

**解决方法：** 尚

### <a href="" id="msi-s-are-not-localized"></a>MSI 未本地化

UE-V 2.0 包括用于 UE-V Agent 和 UE-V 发生器的本地化安装程序。 这些 MSI 文件仍然可用，但用户界面已最小化，并且 MSI 仅以英语显示。 尽管文件是英语，安装程序也会在安装期间安装所有支持的语言。

**解决方法：** 尚

### 与 Internet Explorer 9 收藏夹相关联的 Favicons 不漫游

与 Internet Explorer 9 常用联系人相关联的 favicons 不是由用户体验虚拟化漫游的，并且在新计算机上首次显示收藏时不会显示。

**解决方法：** 在 Internet Explorer 9 浏览器中使用并缓存书签后，Favicons 将显示相关联的常用联系人。

### 文件设置路径存储在注册表中

某些应用程序设置将其配置和设置文件的路径存储为注册表中的值。 当设置在计算机之间漫游时，必须同步在注册表中作为路径引用的文件。

**解决方法：** 使用 "文件夹重定向" 或其他技术确保作为文件设置路径引用的所有文件都存在并放置在 "设置" 漫游的所有计算机上的相同位置。

### 较长设置存储路径可能会导致错误

使设置存储路径尽可能简短。 长路径可能会阻止分辨率或同步。 UE-V 使用设置存储路径作为存储设置的计算路径的一部分。 该路径按以下方式计算：设置存储路径 + "settingspackages" + 程序包目录（模板 ID） + 软件包名称（模板 id） + pkgx。 如果该计算路径超过260个字符，则软件包存储将失败，并在 UE-V 操作事件日志中生成以下错误消息：

`[boost::filesystem::copy_file: The system cannot find the path specified]`

若要检查操作日志事件，请打开事件查看器并导航到 "应用程序和服务日志/Microsoft/用户体验虚拟化/登录/运行"。

**解决方法：** 尚.

### 某些操作系统设置仅在类似操作系统版本之间漫游

针对讲述人的操作系统设置和特定于区域设置的货币字符（即语言和区域设置）将仅在 Windows 的操作系统版本上漫游。 例如，货币字符将不会在 Windows 7 和 Windows 8 之间漫游。

**解决方法：** 尚

### 当应用在意外关闭后重新启动时，Windows 8 应用不会同步设置

如果 Windows 8 应用在启动后意外关闭，则当应用程序重新启动时，应用程序的设置可能不会同步。

**解决方法：** 关闭 Windows 8 应用，关闭并重新启动 UevAppMonitor.exe 应用程序（可使用 TaskManager），然后重新启动 Windows 8 应用。

### <a href="" id="ue-v-1-agent-generates-errors-when-running-ue-v-2-templates-"></a>UE-V 1 代理在运行 UE-V 2 模板时生成错误

如果将 UE-V 2 设置位置模板分配给使用 UE-V 1 代理安装的计算机，则某些设置无法在计算机之间同步，并且代理会在事件日志中报告错误。

**解决方法：** 从 UE-V 1 迁移到 UE-V 2 时，如果计算机运行的是早期版本的代理，则可以创建单独的 UE-V 2.0 目录以支持 UE-V 2.0 代理和模板。

## UE-V 2.0 的修补程序和知识文库文章


本部分包含用于 UE-V 2.0 的修补程序和知识库文章。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong>知识库文章</strong></th>
<th align="left">Title</th>
<th align="left"><strong>链接</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>2927019</p></td>
<td align="left"><p>Microsoft 用户体验虚拟化2.0 的修补程序包1</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2927019" data-raw-source="[support.microsoft.com/kb/2927019](https://support.microsoft.com/kb/2927019)">support.microsoft.com/kb/2927019</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2903501</p></td>
<td align="left"><p>UE-V：用户体验虚拟化（UE-V）与用户配置文件的兼容性</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2903501/EN-US" data-raw-source="[support.microsoft.com/kb/2903501/EN-US](https://support.microsoft.com/kb/2903501/EN-US)">support.microsoft.com/kb/2903501/EN-US</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>2770042</p></td>
<td align="left"><p>UE-V 注册表设置</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2770042/EN-US" data-raw-source="[support.microsoft.com/kb/2770042/EN-US](https://support.microsoft.com/kb/2770042/EN-US)">support.microsoft.com/kb/2770042/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2847017</p></td>
<td align="left"><p>由 Internet Explorer 复制的 UE-V 设置</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2847017/EN-US" data-raw-source="[support.microsoft.com/kb/2847017/EN-US](https://support.microsoft.com/kb/2847017/EN-US)">support.microsoft.com/kb/2847017/EN-US</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>2930271</p></td>
<td align="left"><p>了解 Microsoft UE-V 中的漫游 Outlook 签名的限制</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2930271/EN-US" data-raw-source="[support.microsoft.com/kb/2930271/EN-US](https://support.microsoft.com/kb/2930271/EN-US)">support.microsoft.com/kb/2930271/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2769631</p></td>
<td align="left"><p>如何修复损坏的 UE-V 安装</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2769631/EN-US" data-raw-source="[support.microsoft.com/kb/2769631/EN-US](https://support.microsoft.com/kb/2769631/EN-US)">support.microsoft.com/kb/2769631/EN-US</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>2850989</p></td>
<td align="left"><p>不支持通过 Microsoft UE-V 迁移 MAPI 配置文件</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2850989/EN-US" data-raw-source="[support.microsoft.com/kb/2850989/EN-US](https://support.microsoft.com/kb/2850989/EN-US)">support.microsoft.com/kb/2850989/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2769586</p></td>
<td align="left"><p>UE-V 漫游空文件夹和注册表项</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2769586/EN-US" data-raw-source="[support.microsoft.com/kb/2769586/EN-US](https://support.microsoft.com/kb/2769586/EN-US)">support.microsoft.com/kb/2769586/EN-US</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>2782997</p></td>
<td align="left"><p>如何在 Microsoft 用户体验虚拟化（UE-V）中启用调试日志记录</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2782997/EN-US" data-raw-source="[support.microsoft.com/kb/2782997/EN-US](https://support.microsoft.com/kb/2782997/EN-US)">support.microsoft.com/kb/2782997/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2769570</p></td>
<td align="left"><p>UE-V 不会在 RDS 或 VDI 会话上更新主题</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2769570/EN-US" data-raw-source="[support.microsoft.com/kb/2769570/EN-US](https://support.microsoft.com/kb/2769570/EN-US)">support.microsoft.com/kb/2769570/EN-US</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>2901856</p></td>
<td align="left"><p>在支持 UE-V 的计算机上强制重启后，应用程序设置不同步</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2901856/EN-US" data-raw-source="[support.microsoft.com/kb/2901856/EN-US](https://support.microsoft.com/kb/2901856/EN-US)">support.microsoft.com/kb/2901856/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2850582</p></td>
<td align="left"><p>如何将 Microsoft 用户体验虚拟化与 App-v 应用程序配合使用</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2850582/EN-US" data-raw-source="[support.microsoft.com/kb/2850582/EN-US](https://support.microsoft.com/kb/2850582/EN-US)">support.microsoft.com/kb/2850582/EN-US</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>3041879</p></td>
<td align="left"><p>Microsoft 用户体验虚拟化的当前文件版本</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/3041879/EN-US" data-raw-source="[support.microsoft.com/kb/3041879/EN-US](https://support.microsoft.com/kb/3041879/EN-US)">support.microsoft.com/kb/3041879/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2843592</p></td>
<td align="left"><p>有关用户体验虚拟化和高可用性的信息</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2843592/EN-US" data-raw-source="[support.microsoft.com/kb/2843592/EN-US](https://support.microsoft.com/kb/2843592/EN-US)">support.microsoft.com/kb/2843592/EN-US</a></p></td>
</tr>
</tbody>
</table>

 

 

 





