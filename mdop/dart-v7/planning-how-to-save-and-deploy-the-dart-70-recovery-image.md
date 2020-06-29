---
title: 计划如何保存和部署 DaRT 7.0 恢复映像
description: 计划如何保存和部署 DaRT 7.0 恢复映像
author: dansimp
ms.assetid: d96e9363-6186-4fc3-9b83-ba15ed9694a5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c292633949865d4b3f5053700f4219db3f1cf465
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803240"
---
# 计划如何保存和部署 DaRT 7.0 恢复映像


如果你计划保存和部署 Microsoft 诊断和恢复工具集（DaRT）7恢复映像，请使用本部分中的信息。

## 规划如何保存和部署 DaRT 恢复映像


你可以使用以下方法保存和部署 DaRT 恢复映像。 确定你将使用的方法时，请考虑每个方法的优缺点。 此外，请考虑你希望如何在企业中使用 DaRT。

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
<td align="left"><p>从 CD 或 DVD</p></td>
<td align="left"><p>支持主启动记录（MBR）损坏且无法访问硬盘的方案。 还支持没有网络连接的情况。</p>
<p>较早版本的 DaRT 的用户最熟悉此功能，并且可以直接从 <strong> DaRT 恢复映像向导刻录 CD 或 DVD </strong> 。</p></td>
<td align="left"><p>要求有权访问 CD 或 DVD 的人在最终用户计算机上物理地启动到 DaRT。</p></td>
</tr>
<tr class="even">
<td align="left"><p>从 u 盘（UFD）</p></td>
<td align="left"><p>提供与从 CD 或 DVD 启动同样的优势，并且还提供对没有 CD 或 DVD 驱动器的计算机的支持。</p></td>
<td align="left"><p>需要先设置 UFD 的格式，然后才能使用它启动到 DaRT。 还要求有权访问 UFD 的人在物理位置位于最终用户计算机上，以便启动到 DaRT。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>从远程（网络）分区</p></td>
<td align="left"><p>允许你在不需要 CD、DVD 或 UFD 的情况下启动到 DaRT。 还允许轻松升级 DaRT，因为只有一个文件位置需要更新。</p></td>
<td align="left"><p>如果最终用户计算机未连接到网络，则不起作用。</p>
<p>对最终用户广泛可用，并且在创建恢复映像时可能需要其他安全注意事项。</p></td>
</tr>
<tr class="even">
<td align="left"><p>从恢复分区</p></td>
<td align="left"><p>让你可以启动到 DaRT，无需安装 CD、DVD 或 UFD，包括没有网络连接的实例。</p>
<p>此外，还可以通过使用自动化分发工具（如 Microsoft 终结点配置管理器）来实现和管理作为标准 Windows 映像过程的一部分。</p></td>
<td align="left"><p>更新 DaRT 时，需要更新企业中的所有计算机，而不是只更新一个分区（在网络上）或设备（CD、DVD 或 UFD）。</p></td>
</tr>
</tbody>
</table>

 

## 相关主题


[计划部署 DaRT 7.0](planning-to-deploy-dart-70.md)

 

 





