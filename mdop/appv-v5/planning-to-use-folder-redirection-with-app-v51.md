---
title: 计划将文件夹重定向与 App-V 结合使用
description: 计划将文件夹重定向与 App-V 结合使用
author: dansimp
ms.assetid: 6bea9a8f-a915-4d7d-be67-ef1cca1398ed
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 507aef186579da0efdb3af7b6e1088a5e725ad70
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798282"
---
# 计划将文件夹重定向与 App-V 结合使用


Microsoft Application Virtualization （App-v）5.1 支持使用文件夹重定向，这种功能使用户和管理员能够将文件夹的路径重定向到新位置。

本主题包含以下各节：

-   [使用文件夹重定向的要求](#bkmk-folder-redir-reqs)

-   [如何配置用于 App-v 的文件夹重定向](#bkmk-folder-redir-cfg)

-   [文件夹重定向如何与 app-v 配合使用](#bkmk-folder-redir-works)

-   [文件夹重定向概述](#bkmk-folder-redir-overview)

## <a href="" id="bkmk-folder-redir-reqs"></a>使用文件夹重定向的要求和不受支持的方案


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p>要求</p></td>
<td align="left"><p>若要使用% AppData% 文件夹重定向，必须：</p>
<ul>
<li><p>具有具有 AppData 虚拟文件系统（VFS）文件夹的 app-v 包。</p></li>
<li><p>启用文件夹重定向并将用户文件夹重定向到共享文件夹，通常是网络文件夹。</p></li>
<li><p>既能漫游下列两项，也不漫游：</p>
<ul>
<li><p>%Appdata%\Microsoft\AppV\Client\Catalog 下的文件</p></li>
<li><p>HKEY_CURRENT_USER \Software\Microsoft\AppV\Client\Packages 下的注册表设置</p>
<p>有关更多详细信息，请参阅 <a href="application-publishing-and-client-interaction.md#bkmk-clt-inter-roam-reqs" data-raw-source="[Application Publishing and Client Interaction](application-publishing-and-client-interaction.md#bkmk-clt-inter-roam-reqs)"> 应用程序发布和客户端交互 </a> 。</p></li>
</ul></li>
<li><p>确保登录到运行 App-v 5.0 SP2 或更高版本客户端的计算机的每个用户都可以使用以下文件夹：</p>
<ul>
<li><p>% AppData% 配置为所需的网络位置（有或不 <a href="https://technet.microsoft.com/library/cc780552.aspx" data-raw-source="[Offline Files](https://technet.microsoft.com/library/cc780552.aspx)"> 支持脱机文件 </a> ）。</p></li>
<li><p>% LocalAppData% 配置为所需的本地文件夹。</p></li>
</ul></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>不受支持的情形</p></td>
<td align="left"><ul>
<li><p>将% LocalAppData% 配置为网络驱动器。</p></li>
<li><p>为多个用户将 "开始" 菜单重定向到单个文件夹。</p></li>
<li><p>如果漫游 AppData （% AppData%）被重定向到不可用的网络共享，则 App-v 应用程序将无法启动，如下所示：</p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">App-v 版本</th>
<th align="left">方案说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>在 app-v 5.0 中，通过 app-v 5.0 SP2 和修补程序</p></td>
<td align="left"><p>无论是否启用 "脱机文件"，都将出现此错误。</p></td>
</tr>
<tr class="even">
<td align="left"><p>在 App-v 5.0 SP3 和更高版本中</p></td>
<td align="left"><p>如果为脱机文件启用了不可用的网络共享，则 App-v 应用程序将成功启动。</p></td>
</tr>
</tbody>
</table>
<p> </p></li>
</ul></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-folder-redir-cfg"></a>如何配置用于 App-v 的文件夹重定向


文件夹重定向可应用于不同的文件夹，例如 "桌面"、"我的文档"、"我的图片" 等。但是，影响 App-v 应用程序的使用的唯一文件夹是用户的漫游 AppData 文件夹（% AppData%）。 你可以将文件夹重定向应用到任何其他支持的文件夹，而不会影响 App-v。

## <a href="" id="bkmk-folder-redir-works"></a>文件夹重定向如何与 app-v 配合使用


下表介绍了当% AppData% 被重定向到网络时，以及当满足本文前面列出的要求时，文件夹重定向如何工作。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">虚拟环境状态</th>
<th align="left">发生的操作</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>虚拟环境启动时</p></td>
<td align="left"><p>虚拟文件系统（VFS） AppData 文件夹映射到本地 AppData 文件夹（% LocalAppData%）而不是用户的漫游 AppData 文件夹（% AppData%）。</p>
<ul>
<li><p>LocalAppData 包含要使用的程序包的用户漫游 AppData 文件夹的本地缓存。 本地缓存位于以下位置：</p>
<p><code>%LocalAppData%\Microsoft\AppV\Client\VFS\PackageGUID\AppData</code></p></li>
<li><p>用户的漫游 AppData 文件夹中的最新数据将复制到并替换本地缓存中的当前数据。</p></li>
<li><p>虚拟环境运行时，数据将继续保存到本地缓存。 仅提供% LocalAppData% 的数据，并且不会与% AppData% 一起移动或同步，直到最终用户关闭计算机。</p></li>
<li><p>使用用户上下文（而非系统上下文）对 AppData 文件夹的条目进行输入。</p></li>
</ul>
<div class="alert">
<strong>注意</strong><br/><p>App-v 客户端文件夹重定向有时无法将文件从% AppData% 移动到% LocalAppData%。 请参阅 <a href="release-notes-for-app-v-50-sp2.md#bkmk-folderredirection" data-raw-source="[Release Notes for App-V 5.0 SP2](release-notes-for-app-v-50-sp2.md#bkmk-folderredirection)"> 应用-V 5.0 SP2 的发行说明 </a> 。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p>虚拟环境关闭时</p></td>
<td align="left"><p>将 AppData （漫游）中的本地缓存数据压缩并复制到% AppData% 中的 "真正的" 漫游 AppData 文件夹。 时间戳（指示上次已知上载）将同时另存为注册表项，如下所示：</p>
<p><code>HKCU\Software\Microsoft\AppV\Client\Packages&amp;lt;PACKAGE_GUID&gt;\AppDataTime</code></p>
<p>为了提供冗余，App-v 将 "% AppData%" 下的三个最新压缩数据副本保留。</p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-folder-redir-overview"></a>文件夹重定向概述


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p>用途</p></td>
<td align="left"><p>使最终用户能够使用已重定向到另一个文件夹的文件，就像文件仍然存在于本地驱动器上一样。</p></td>
</tr>
<tr class="even">
<td align="left"><p>描述</p></td>
<td align="left"><p>文件夹重定向允许用户和管理员将文件夹的路径重定向到网络位置。 用户可从网络上的任何计算机使用该文件夹中的文档。</p>
<ul>
<li><p>文件夹重定向允许用户和管理员将文件夹的路径重定向到网络位置。 用户可从网络上的任何计算机使用该文件夹中的文档。</p></li>
<li><p>新位置可以是本地计算机上的文件夹，也可以是共享网络上的文件夹。</p></li>
<li><p>"文件夹重定向" 将立即更新文件，而漫游数据通常在用户登录或注销时同步。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>用法示例</p></td>
<td align="left"><p>你可以将 "文档" 文件夹（通常存储在计算机&#39;s 本地硬盘）重定向到网络位置。 用户可以从网络上的任何计算机访问文件夹中的文档。</p></td>
</tr>
<tr class="even">
<td align="left"><p>更多资源</p></td>
<td align="left"><p><a href="https://technet.microsoft.com/library/cc778976.aspx" data-raw-source="[Folder redirection overview](https://technet.microsoft.com/library/cc778976.aspx)">文件夹重定向概述</a></p></td>
</tr>
</tbody>
</table>
















