---
title: 如何配置客户端以进行应用程序包检索
description: 如何配置客户端以进行应用程序包检索
author: dansimp
ms.assetid: 891f2739-da7a-46da-b452-b8c0af075525
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f5eeb0b977c6ecd44947d5d1c42d25d47b9e2530
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801572"
---
# 如何配置客户端以进行应用程序包检索


将客户端配置为将应用程序虚拟化（app-v）管理服务器配置为发布服务器时，默认情况下，在下一个发布刷新周期中，客户端从服务器检索用户有权使用的每个程序包的开放软件描述符（OSD）和程序包清单文件。 客户端使用在这些文件中定义的程序包源信息来确定要在何处查找程序包内容、图标和文件类型关联。

如果你希望客户从本地 App-v 流式处理服务器或其他备用源（如 Web 服务器或文件服务器）获取程序包内容（SFT 文件），可以将计算机上的 ApplicationSourceRoot 注册表项值配置为指向另一台服务器上的本地内容共享。 OSD 文件仍定义程序包内容的原始源路径。 但是，客户端使用 ApplicationSourceRoot 设置的值代替在 OSD 文件的内容路径中指定的服务器和共享。 这将重定向客户端以从另一台服务器检索内容。

如果你想要在程序包清单文件或发布服务器发送的路径中替代这些设置，也可以配置 OSDSourceRoot 和 IconSourceRoot 注册表项值。 OSDSourceRoot 指定发布期间应用程序包的 OSD 文件检索的源位置。 IconSourceRoot 指定发布期间应用程序包的图标检索的源位置。

**注意**  
-   IconSourceRoot 和 OSDSourceRoot 设置替代程序包清单文件中的值，因此，如果你尝试使用 Windows Installer （.msi）文件方法部署程序包，则它还将替代该 .msi 文件中包含的程序包清单文件中的值。

-   在发布和 HTTP （S）流操作过程中，App-v 4.5 SP1 客户端使用在用户计算机上的 Internet Explorer 中配置的代理服务器设置。



**配置 ApplicationSourceRoot 注册表项值**

-   使用 UNC 路径或 URL 配置以下注册表项值中的 ApplicationSourceRoot：

    HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\\ApplicationSourceRoot

    通用命名约定（UNC）路径的正确格式为**\\\\computername\\sharefolder\\\ [folder \] \ [\\]**，其中**文件夹**是可选的。 **Computername**可以是完全限定的域名（FQDN）或 IP 地址， **sharefolder**可以是驱动器号。 仅替换 OSD 路径的**\\\\computername\\sharedfolder**或驱动器号部分。

    URL 路径的正确格式为**protocol：/path\： \ [port \] \ [] \ [/\]**，其中**port**和**path**是可选的。 如果未指定**port** ，则使用协议的默认端口。 仅替换了 OSD URL 的**协议：//server：端口**部分。

    **重要提示**  
    ApplicationSourceRoot 定义中不支持环境变量。



~~~
The following table lists examples of acceptable URL and UNC path formats.

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">ApplicationSourceRoot</th>
<th align="left">OSD File HREF Path</th>
<th align="left">Result</th>
<th align="left">Comments</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>rtsps://mainserver:322</p></td>
<td align="left"><p>rtsp://appserver/productivity/office2k3.sft?customer=seq</p></td>
<td align="left"><p>rtsps://mainserver:322/productivity/office2k3.sft?customer=seq</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>rtsps://mainserver:322/prodapps</p></td>
<td align="left"><p>rtsp://appserver/productivity/office2k3.sft?customer=seq</p></td>
<td align="left"><p>rtsps://mainserver:322/prodapps/productivity/office2k3.sft?customer=seq</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>https://mainserver:443/prodapps</p></td>
<td align="left"><p>rtsp://appserver/productivity/office2k3.sft?customer=seq</p></td>
<td align="left"><p>https://mainserver:443/prodapps/productivity/office2k3.sft?customer=seq</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>rtsps://mainserver:322/prodapps</p></td>
<td align="left"><p>rtsp://%SFT_APPVSERVER%:554/productivity/office2k3.sft?customer=seq</p></td>
<td align="left"><p>rtsps://mainserver:322/prodapps/productivity/office2k3.sft?customer=seq</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>rtsps://mainserver:322</p></td>
<td align="left"><p>\\uncserver\share\productivity\office2k3.sft</p></td>
<td align="left"><p>rtsps://mainserver:322/productivity/office2k3.sft</p></td>
<td align="left"><p>‘\’ converted to ‘/’</p></td>
</tr>
<tr class="even">
<td align="left"><p>rtsps://mainserver:322</p></td>
<td align="left"><p>file://\\uncserver\share\productivity\office2k3.sft</p></td>
<td align="left"><p>rtsps://mainserver:322/productivity/office2k3.sft</p></td>
<td align="left"><p>‘\’ converted to ‘/’</p></td>
</tr>
<tr class="odd">
<td align="left"><p>\\uncserver\share</p></td>
<td align="left"><p>rtsp://appserver/productivity/office2k3.sft?customer=seq</p></td>
<td align="left"><p>\\uncserver\share\productivity\office2k3.sft</p></td>
<td align="left"><p>‘/’ converted to ‘\’ and parameter dropped when converting to UNC path</p></td>
</tr>
<tr class="even">
<td align="left"><p>\\uncserver\share\prodapps</p></td>
<td align="left"><p>rtsp://appserver/productivity/office2k3.sft?customer=seq</p></td>
<td align="left"><p>\\uncserver\share\prodapps\productivity\office2k3.sft</p></td>
<td align="left"><p>‘/’ converted to ‘\’ and parameter dropped when converting to UNC path</p></td>
</tr>
<tr class="odd">
<td align="left"><p>M:</p></td>
<td align="left"><p>\\uncserver\share\productivity\office2k3.sft</p></td>
<td align="left"><p>M:\productivity\office2k3.sft</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>M:\prodapps</p></td>
<td align="left"><p>\\uncserver\share\productivity\office2k3.sft</p></td>
<td align="left"><p>M:\prodapps\productivity\office2k3.sft</p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>
~~~



**配置 OSDSourceRoot 值**

-   使用 UNC 路径或 URL 配置以下注册表项值中的 OSDSourceRoot：

    HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\\OSDSourceRoot

    OSDSourceRoot 的可接受格式包括 UNC 路径和 Url，如以下示例中所示：

    **\\\\computername\\sharefolder\\resource**或**\\\\computername\\content**或** &lt; drive &gt; ： \\foldername**

    **http://computername/productivity/** 或**https://computername/productivity/**

**配置 IconSourceRoot 值**

-   使用 UNC 路径或 URL 配置以下注册表项值中的 IconSourceRoot：

    HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\\IconSourceRoot

    IconSourceRoot 的可接受格式包括 UNC 路径和 Url，如以下示例中所示：

    **\\\\computername\\sharefolder\\resource**或**\\\\computername\\content**或** &lt; drive &gt; ： \\foldername**

    **http://computername/productivity/** 或**https://computername/productivity/**

## 相关主题


[如何使用命令行配置 App-V Client 注册表设置](how-to-configure-the-app-v-client-registry-settings-by-using-the-command-line.md)









