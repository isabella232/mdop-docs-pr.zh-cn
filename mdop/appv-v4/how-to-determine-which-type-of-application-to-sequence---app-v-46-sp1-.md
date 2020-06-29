---
title: 如何确定要序列化的应用程序类型（App-v 4.6 SP1）
description: 如何确定要序列化的应用程序类型（App-v 4.6 SP1）
author: dansimp
ms.assetid: 936abee2-98f1-45fb-9f0d-786e1d7464b1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 001f6afa36ca28eb1b8e0cc2ccc161cef4194d24
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801436"
---
# 如何确定要序列化的应用程序类型（App-v 4.6 SP1）


你可以使用 Microsoft Application Virtualization （App-v） Sequencer 对三种基本类型的应用程序进行排序。

## 确定序列的应用程序类型


使用下表确定应序列化的应用程序类型，并获取有关如何对应用程序进行排序的详细信息。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">应用程序类型</th>
<th align="left">描述</th>
<th align="left">详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Standard</p></td>
<td align="left"><p>选择此选项可创建包含应用程序或应用程序套件的程序包。 对于你打算序列化的大多数应用程序，你应选择此选项。</p></td>
<td align="left"><p><a href="how-to-sequence-a-new-standard-application--app-v-46-sp1-.md" data-raw-source="[How to Sequence a New Standard Application (App-V 4.6 SP1)](how-to-sequence-a-new-standard-application--app-v-46-sp1-.md)">如何对新的标准应用程序进行排序 (App-V 4.6 SP1)</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>加载项或插件</p></td>
<td align="left"><p>选择此选项可创建扩展标准应用程序（例如 Microsoft Excel 插件）的功能的程序包。 此外，你可以对本机安装的应用程序使用插件，或者对使用动态套件合成链接的其他程序包使用插件。 有关动态套件合成的详细信息，请参阅 <a href="https://go.microsoft.com/fwlink/?LinkId=203804" data-raw-source="[How To Use Dynamic Suite Composition](https://go.microsoft.com/fwlink/?LinkId=203804)"> 如何使用动态套件合成 </a> （ <a href="https://go.microsoft.com/fwlink/?LinkId=203804" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=203804"> https://go.microsoft.com/fwlink/?LinkId=203804 </a> ）。</p></td>
<td align="left"><p><a href="how-to-sequence-a-new-add-on-or-plug-in-application--app-v-46-sp1-.md" data-raw-source="[How to Sequence a New Add-on or Plug-in Application (App-V 4.6 SP1)](how-to-sequence-a-new-add-on-or-plug-in-application--app-v-46-sp1-.md)">如何对新的加载项或插件应用程序进行排序 (App-V 4.6 SP1)</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>中间件</p></td>
<td align="left"><p>选择此选项可创建标准应用程序（例如 Microsoft .NET Framework）所需的程序包。 中间件程序包用于通过使用动态套件合成链接到其他程序包。 有关动态套件合成的详细信息，请参阅 <a href="https://go.microsoft.com/fwlink/?LinkId=203804" data-raw-source="[How To Use Dynamic Suite Composition](https://go.microsoft.com/fwlink/?LinkId=203804)"> 如何使用动态套件合成 </a> （ <a href="https://go.microsoft.com/fwlink/?LinkId=203804" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=203804"> https://go.microsoft.com/fwlink/?LinkId=203804 </a> ）。</p></td>
<td align="left"><p><a href="how-to-sequence-a-new-middleware-application--app-v-46-sp1-.md" data-raw-source="[How to Sequence a New Middleware Application (App-V 4.6 SP1)](how-to-sequence-a-new-middleware-application--app-v-46-sp1-.md)">如何对新的中间件应用程序进行排序 (App-V 4.6 SP1)</a></p></td>
</tr>
</tbody>
</table>

 

## 相关主题


[Application Virtualization Sequencer 的任务 (App-V 4.6 SP1)](tasks-for-the-application-virtualization-sequencer--app-v-46-sp1-.md)

 

 





