---
title: Application Virtualization Client 中的用户访问权限
description: Application Virtualization Client 中的用户访问权限
author: dansimp
ms.assetid: 7459374c-810c-45e3-b205-fdd1f8514f80
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 1083faffb48aa58a0ee0c81b58fae307e53548b8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798707"
---
# Application Virtualization Client 中的用户访问权限


在 "**属性**" 对话框的 "**权限**" 选项卡上，右键单击应用程序虚拟化客户端管理控制台中的 "**应用程序虚拟化**" 节点可访问该选项卡，管理员可以授予用户使用各种客户端功能的权限。

**注意** 在更改用户权限之前，请确保任何权限更改均与组织授予用户权限的指南一致。

 

下表列出并介绍了可授予用户的权限。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">权限名称</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>添加应用程序</p></td>
<td align="left"><p>通过使用 sfttray.exe、sftmime.exe 或 MMC 将新的 OSD 文件传递到客户端来注册新的应用程序。</p></td>
</tr>
<tr class="even">
<td align="left"><p>更改文件系统缓存大小</p></td>
<td align="left"><p>增加文件系统缓存的大小。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>更改文件系统驱动器</p></td>
<td align="left"><p>为文件系统选择不同的首选驱动器号。</p></td>
</tr>
<tr class="even">
<td align="left"><p>更改日志设置</p></td>
<td align="left"><p>更改客户端日志文件的日志级别或日志路径。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>更改 OSD 文件</p></td>
<td align="left"><p>修改已注册应用程序的 OSD 文件并将其传递到客户端。 这不会影响发布刷新。</p></td>
</tr>
<tr class="even">
<td align="left"><p>清除应用程序设置</p></td>
<td align="left"><p>删除当前用户的文件类型、快捷方式和任何配置。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>删除应用程序</p></td>
<td align="left"><p>从文件系统中删除对应用程序的所有引用以及计算机上所有用户的 OSD 缓存。</p></td>
</tr>
<tr class="even">
<td align="left"><p>将应用程序导入到缓存中</p></td>
<td align="left"><p>将应用程序数据从指定的 SFT 文件直接加载到文件系统缓存中。 这将影响所有用户。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>将应用程序加载到缓存中</p></td>
<td align="left"><p>从已配置的源开始对应用程序的 SFT 文件的加载，例如 App-v 流式处理服务器。 这将为计算机上的所有用户加载应用程序。</p></td>
</tr>
<tr class="even">
<td align="left"><p>在缓存中锁定和取消锁定应用程序</p></td>
<td align="left"><p>阻止或允许从文件系统缓存中卸载应用程序。 这会影响计算机上的所有用户。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>管理文件类型关联</p></td>
<td align="left"><p>仅添加、修改或删除当前用户的文件类型关联。</p></td>
</tr>
<tr class="even">
<td align="left"><p>管理发布刷新设置</p></td>
<td align="left"><p>更改用于控制计算机上所有用户的发布刷新计时的设置。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>管理发布服务器</p></td>
<td align="left"><p>为计算机上的所有用户添加、修改或删除发布服务器。 此权限隐式包含管理发布刷新设置的权限。</p></td>
</tr>
<tr class="even">
<td align="left"><p>发布快捷方式</p></td>
<td align="left"><p>创建新的注册应用程序快捷方式。 用户还必须具有在本地文件系统中创建文件的权限。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>修复应用程序</p></td>
<td align="left"><p>删除当前用户的特定于应用程序的配置，而不删除快捷方式或文件类型关联。</p></td>
</tr>
<tr class="even">
<td align="left"><p>启动发布刷新</p></td>
<td align="left"><p>为当前用户启动计划外的发布刷新。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>切换脱机模式</p></td>
<td align="left"><p>为所有用户将整个客户端从联机模式更改为脱机模式。</p></td>
</tr>
<tr class="even">
<td align="left"><p>从缓存卸载应用程序</p></td>
<td align="left"><p>为所有用户清除文件系统缓存中的应用程序数据，而不删除特定于用户的设置、快捷方式或文件类型关联。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>查看所有应用程序</p></td>
<td align="left"><p>允许用户查看计算机上注册的所有用户的虚拟应用程序。</p></td>
</tr>
</tbody>
</table>

 

## 相关主题


[如何更改用户访问权限](how-to-change-user-access-permissions.md)

 

 





