---
title: 记录和跟踪设置
description: 记录和跟踪设置
author: dansimp
ms.assetid: db6b43c7-fdde-4d11-b5ab-a81346e56940
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: bef0f8367647aad688c2aec7586ecdaae2e22143
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802676"
---
# 记录和跟踪设置


通过高级组策略管理（AGPM）的管理模板设置，你可以为已应用了组策略对象（GPO）的 AGPM 服务器和客户集中配置日志记录和跟踪选项。

在组策略管理控制台（GPMC）中编辑 GPO 时，"**组策略对象编辑器**" 中的 "计算机 Configuration\\Administrative Templates\\Windows Components\\AGPM 下将提供以下设置。 如果此路径不可见，请右键单击 "**管理模板**"，然后添加 "agpm" 或 "agpm .adm" 模板。

**跟踪文件位置**：

-   客户端：%LocalAppData%\\Microsoft\\AGPM\\agpm.log

-   服务器：%CommonAppData%\\Microsoft\\AGPM\\agpmserv.log

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
<td align="left"><p><strong>AGPM 日志记录</strong></p></td>
<td align="left"><p>如果已启用，此设置将配置跟踪是否处于打开状态以及详细级别。 此设置会影响 AGPM 的客户端和服务器组件。</p>
<p>如果已禁用或未配置，此设置将不起作用。</p></td>
</tr>
</tbody>
</table>

 

### 其他参考资料

-   [管理模板设置](administrative-template-settings.md)

 

 





