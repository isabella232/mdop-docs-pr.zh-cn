---
title: 记录和跟踪设置
description: 记录和跟踪设置
author: dansimp
ms.assetid: 858b6fbf-65b4-42fa-95a9-69b04e5734d7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 078bda16b5fcf968d45e0c4890487471105e8c44
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802679"
---
# 记录和跟踪设置


通过高级组策略管理（AGPM）的管理模板设置，你可以为已应用了组策略对象（GPO）的 AGPM 服务器和客户集中配置日志记录和跟踪选项。

编辑 GPO 时，"计算机 Configuration\\Policies\\Administrative Templates\\Windows Components\\AGPM" 下提供以下设置。

**跟踪文件位置**：

-   客户端：%LocalAppData%\\Microsoft\\AGPM\\agpm.log

-   服务器：%ProgramData%\\Microsoft\\AGPM\\agpmserv.log

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">设置</th>
<th align="left">作用</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>AGPM：配置日志记录</strong></p></td>
<td align="left"><p>通过此策略设置，你可以为 AGPM 启用和配置日志记录。 此设置会影响 AGPM 的客户端和服务器组件。</p></td>
</tr>
</tbody>
</table>

 

### 其他参考资料

-   [“管理模板”文件夹](administrative-templates-folder-agpm30ops.md)

 

 





