---
title: 评估 UE-V 1.0 的业务线应用程序清单
description: 评估 UE-V 1.0 的业务线应用程序清单
author: dansimp
ms.assetid: 3bfaab30-59f7-4099-abb1-d248ce0086b8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 133bc5d195763b7281fd8d152e153231ac4c4d47
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803972"
---
# 评估 UE-V 1.0 的业务线应用程序清单


若要评估在 UE-V 部署中应包括哪些业务线应用程序，请考虑以下事项：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>此应用程序是否包含用户可自定义的设置？</p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>用户是否对这些设置进行漫游非常重要？</p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>这些用户设置是否已由应用程序管理或设置策略解决方案管理？ UE-V 在登录、解锁或远程连接事件时，在应用程序启动和 Windows 设置中应用应用程序设置。 如果你将 UE-V 与其他设置策略解决方案配合使用，则用户在漫游设置中可能会遇到不一致的情况。</p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>应用程序设置是否特定于计算机？ 与硬件或特定计算机配置相关联的应用程序首选项和自定义不会在多个会话之间持续漫游，并且可能导致应用程序体验较差。</p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>应用程序将设置存储在 "程序文件" 目录中还是位于 " <strong> 用户 </strong> 名称" \ <strong> AppData </strong>  \  <strong> LocalLow </strong> 目录中的文件目录？ 存储在其中任一位置的应用程序数据通常不应与用户漫游，因为此数据特定于计算机，或者由于数据太大而无法进行漫游。</p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>应用程序是否在包含不应漫游的其他应用程序数据的文件中存储任何设置？ UE-V 将文件作为单个单元进行同步。 如果设置存储在包含应用程序数据而不是设置的文件中，则同步这些附加数据可能会导致应用程序体验较差。</p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>包含这些设置的文件有多大？ 设置同步的性能可能会受到大型文件的影响。 包括大型文件会影响设置同步的性能。</p></td>
</tr>
</tbody>
</table>

 

## 相关主题


[规划 UE-V 配置方法](planning-for-ue-v-configuration-methods.md)

[规划 UE-V 1.0](planning-for-ue-v-10.md)

 

 





