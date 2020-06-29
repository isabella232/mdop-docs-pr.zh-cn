---
title: UE-V 2.x 的同步方法
description: UE-V 2.x 的同步方法
author: dansimp
ms.assetid: af0ae894-dfdc-41d2-927b-c2ab1b355ffe
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a163442e2ab3dbd777aca133b13b0086cdb8ae1a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803396"
---
# UE-V 2.x 的同步方法


Microsoft 用户体验虚拟化（UE-V）2.0、2.1 和 2.1 SP1 代理使你可以将用户的应用程序和 Windows 设置与设置存储位置同步。 *同步方法*配置定义了 ue-v Agent 如何将这些设置上载并下载到设置存储位置。 UE-V 2. x 引入了名为*SyncProvider*的新 powerschool。 有关启动应用程序和 Windows 设置同步的触发器事件的详细信息，请参阅[为 ue-v 2. x 同步触发器事件](sync-trigger-events-for-ue-v-2x-both-uevv2.md)。

## Powerschool 配置


下表说明了对 Powerschool 的更改：从 UE-V v 1.0 到 v 2.0 到 v 2.1 以及每个配置的设置：

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>Powerschool 配置</strong></p></td>
<td align="left"><p><strong>V 1。0</strong></p></td>
<td align="left"><p><strong>V 2。0</strong></p></td>
<td align="left"><p><strong>V 2.1 和 V 2.1 SP1</strong></p></td>
<td align="left"><p><strong>描述</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p>SyncProvider</p></td>
<td align="left"><p>不适用</p></td>
<td align="left"><p>默认值</p></td>
<td align="left"><p>默认值</p></td>
<td align="left"><p>特定应用程序或全局 Windows 桌面设置的设置更改将保存到本地缓存文件夹中。 当发生同步触发事件时，这些更改将与设置存储位置同步。 推送更改会将本地更改保存到设置存储路径。</p>
<p>此默认设置是计算机的黄金标准。 此选项尝试在短时间延迟后同步设置和超时，以确保应用程序或操作系统启动不会在很长一段时间内延迟。</p>
<p>此功能还与 "计划任务-同步控制器" 应用程序相关联。 管理员控制计划任务的频率。 默认情况下，计算机在登录后每隔30分钟同步其设置。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>OfflineFiles</p></td>
<td align="left"><p>默认值</p></td>
<td align="left"><p>已弃用</p></td>
<td align="left"><p>已弃用</p></td>
<td align="left"><p>的行为与 V 2.0 中的 SyncProvider 相同。</p>
<p>如果启用了脱机文件，并且已将文件夹固定，则 UE-V 将取消该文件夹的固定，并将其直接同步到中央 SMB 目录。</p>
<p><strong>注意： </strong> 在 V 1.0 中，如果你想要以企业的断开连接方式使用 ue-v （也就是使用膝上型电脑旅行），则指南是使用脱机文件确保你的设置漫游。我们收到了足够的客户反馈，可打开 "脱机文件" 是不重要的企业阻止程序。 因此，在 UE-V 2 中，我们创建了一个紧密耦合的同步引擎以在本地缓存数据，并将设置同步到中央服务器。 此功能区域不会替换脱机文件或文件夹重定向。</p>
<p>UE-V 2 不能很好地处理脱机文件夹，因此指南不会将设置存储路径设置为已固定的脱机或 CSC 文件夹。</p></td>
</tr>
<tr class="even">
<td align="left"><p>外部</p></td>
<td align="left"><p>不适用</p></td>
<td align="left"><p>不适用</p></td>
<td align="left"><p>支持</p></td>
<td align="left"><p>UE-V 2.1 中的新增功能，此配置方法指定如果 UE-V 设置写入到用户计算机上的本地文件夹，则可以使用任何外部同步引擎（如 OneDrive for Business、工作文件夹、Sharepoint 或 Dropbox）将这些设置应用于用户访问的不同计算机。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>无</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>此配置设置主要用于虚拟桌面基础结构（VDI）和流式处理应用程序体验。 应在数据中心中使用的 Windows Server 框上使用此设置，其中的连接将始终可用。</p>
<p>任何设置更改都将直接保存到服务器。 如果到设置存储路径的网络连接不可用，则设置更改将缓存在设备上，并且将在下次运行同步提供程序时进行同步。 如果未找到设置存储路径，并且在注销时从池中的 VDI 环境中删除了用户配置文件，则这些设置更改将丢失，用户必须重新应用更改，然后计算机才能再次访问设置存储路径。</p>
<p>应用和操作系统将无限期地等待要显示的位置。 如果找不到该位置，这可能会导致应用加载或操作系统登录时间大幅增加。</p></td>
</tr>
</tbody>
</table>

 

你可以通过以下方式配置同步方法：

-   通过命令行参数或在批处理脚本中[部署 Ue-v Agent](https://technet.microsoft.com/library/dn458891.aspx#agent)时

-   通过[组策略](https://technet.microsoft.com/library/dn458893.aspx)设置

-   对于 UE-V 的[System Center 配置包](https://technet.microsoft.com/library/dn458917.aspx)

-   在安装 UE-V Agent 之后，使用[Windows PowerShell 或 Windows Management Instrumentation （WMI）](https://technet.microsoft.com/library/dn458937.aspx)






## 相关主题


[为 UE-V 2.x 部署所需功能](deploy-required-features-for-ue-v-2x-new-uevv2.md#ssl)

[为 UE-V 2.x 部署所需功能](deploy-required-features-for-ue-v-2x-new-uevv2.md#config)

[UE-V 2.x 的技术参考](technical-reference-for-ue-v-2x-both-uevv2.md)

 

 





