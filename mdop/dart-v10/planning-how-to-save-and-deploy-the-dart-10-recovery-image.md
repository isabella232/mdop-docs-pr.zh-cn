---
title: 计划如何保存和部署 DaRT 10 恢复映像
description: 计划如何保存和部署 DaRT 10 恢复映像
author: dansimp
ms.assetid: 9a3e5413-2621-49ce-8bd2-992616691703
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: bbaa8c4160970de90561f5ff8cedcefd08ca1dd7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803278"
---
# 计划如何保存和部署 DaRT 10 恢复映像


你可以使用以下方法保存和部署 Microsoft 诊断和恢复工具集（DaRT）10恢复映像。 确定你将使用的方法时，请考虑每个方法的优缺点。 你还应考虑你的基础结构和支持人员。 如果你有一个小型基础结构，你可能希望使用可移动媒体部署 DaRT 10，因为如果将其安装到本地硬盘，恢复映像将始终可用。

如果你的组织使用 Active Directory 域服务（AD DS），你可能希望使用 Windows DS 将恢复映像部署为网络服务。 任何连接的计算机都可以使用恢复图像。 你可以从 Windows DS 部署多个映像，并在一个位置维护它们。

**注意** 您可能希望在您的组织中使用多个方法。 例如，在大多数情况下，你可以从远程分区启动到 DaRT，并且在最终用户计算机无法连接到网络时有可用的 USB 闪存驱动器。

 

下表显示了在组织中使用 DaRT 的每种方法的一些优点和缺点。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">启动到 DaRT 的方法</th>
<th align="left">优点</th>
<th align="left">缺点</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>可移动媒体</strong></p>
<p>恢复映像将写入 CD、DVD 或 USB 驱动器，以使支持人员能够将恢复工具与不稳定的计算机配合使用。</p></td>
<td align="left"><p>支持主启动记录（MBR）损坏的情况，并且您无法访问硬盘并支持没有网络连接的情况。</p>
<p>使你能够创建具有不同工具的多个恢复映像，以提供不同级别的支持。</p>
<p>提供用于将恢复映像刻录到可移动媒体的内置工具。</p></td>
<td align="left"><p>要求支持人员实际位于最终用户计算机上，以便启动到 DaRT。</p>
<p>需要时间和维护，才能为32位和64位计算机创建具有不同配置的多个媒体。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>从远程（网络）分区</strong></p>
<p>恢复映像位于网络启动服务器（如 Windows 部署服务（Windows DS））上，使用户或支持人员可以按需将其流式传输到计算机。</p></td>
<td align="left"><p>适用于有权访问网络启动服务器的所有计算机。</p>
<p>恢复映像托管在一个中央服务器上，该服务器启用集中更新。</p>
<p>集中式技术支持人员可以通过使用远程连接来提供修复。</p>
<p>客户端上没有本地存储要求。</p>
<p>可以创建具有不同工具的多个恢复映像以用于特定的支持级别。</p></td>
<td align="left"><p>需要保护 Windows DS 基础结构，以确保常规用户只能启动 DaRT 恢复映像，而不能启动完整的操作系统成像进程。</p>
<p></p>
<p></p>
<p>要求最终用户计算机在运行时连接到网络。</p>
<p>要求通过网络进入恢复映像。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>从本地硬盘上的恢复分区</strong></p>
<p>恢复映像可以手动安装在本地硬盘上，也可以通过使用电子软件分发系统（如 System Center Configuration Manager）进行安装。</p></td>
<td align="left"><p>恢复映像始终可用，因为它是在计算机上预暂存的。</p>
<p>集中的技术支持人员可通过使用远程连接提供支持。</p>
<p>恢复映像是集中管理和部署的。</p>
<p>已消除受 Windows BitLocker 驱动器加密保护的计算机上的其他恢复密钥请求。</p></td>
<td align="left"><p>需要本地存储。</p>
<p>建议使用专用的未加密分区来放置恢复映像，以降低启动分区出现故障的风险。</p>
<p>更新 DaRT 时，必须更新企业中的所有计算机，而不是只更新一个分区（在网络上）或可移动设备。</p>
<p>如果在启用 BitLocker 后部署恢复映像，则需要其他注意事项。</p></td>
</tr>
</tbody>
</table>

 

## 相关主题


[计划部署 DaRT 10](planning-to-deploy-dart-10.md)

 

 





