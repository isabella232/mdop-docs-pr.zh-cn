---
title: App-V 5.1 的高级别体系结构
description: App-V 5.1 的高级别体系结构
author: dansimp
ms.assetid: 90406361-55b8-40b7-85c0-449436789d4c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8044c6ae9af4673ec12b47cf3b8fa73a134d9cca
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798566"
---
# App-V 5.1 的高级别体系结构


使用以下信息可帮助你简化 Microsoft Application Virtualization （App-v）5.1 部署。

## 体系结构概述


典型的 App-v 5.1 实现由以下元素组成。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">元素</th>
<th align="left">详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>App-v 5.1 管理服务器</p></td>
<td align="left"><p>App-v 5.1 管理服务器为 App-v 5.1 基础结构提供了总体管理功能。 此外，你可以在你的环境中安装多个管理服务器实例，这些实例提供以下好处：</p>
<ul>
<li><p>容错和高可用性-在两台单独的计算机上安装和配置 App-v 5.1 管理服务器可帮助在其中一个服务器不可用或脱机时出现的情况。</p>
<p>您还可以通过在多台计算机上安装管理服务器来帮助提高 App-v 5.1 的可用性。 在此方案中，还应考虑使用网络负载平衡器，以便服务器请求平衡。</p></li>
<li><p>可伸缩性-你可以根据需要添加其他管理服务器以支持高负载，例如，你可以在负载平衡器后面安装多台服务器。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>App-v 5.1 发布服务器</p></td>
<td align="left"><p>App-v 5.1 发布服务器提供虚拟应用程序托管和流式处理的功能。 发布服务器不需要数据库连接，并且支持下列协议：</p>
<ul>
<li><p>HTTP 和 HTTPS</p></li>
</ul>
<p>您还可以通过在多台计算机上安装发布服务器来帮助提高 App-v 5.1 的可用性。 还应考虑网络负载平衡器，以便平衡服务器请求。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>App-v 5.1 报告服务器</p></td>
<td align="left"><p>App-v 5.1 报告服务器使授权用户能够运行和查看现有的 app-v 5.1 报告和可帮助他们管理 App-v 5.1 基础结构的特定报表。 报表服务器需要连接到 app-v 5.1 报告数据库。 你还可以通过在多台计算机上安装报表服务器来帮助提高 App-v 5.1 的可用性。 还应考虑网络负载平衡器，以便平衡服务器请求。</p></td>
</tr>
<tr class="even">
<td align="left"><p>App-v 5.1 客户端</p></td>
<td align="left"><p>App-v 5.1 客户端支持使用 App-v 5.1 创建的程序包在目标计算机上运行。</p></td>
</tr>
</tbody>
</table>

 

**注意** 如果您将 app-v 5.1 与电子软件分发（ESD）配合使用，则不需要使用 app-v 5.1 管理服务器，但是您仍然可以利用 App-v 5.1 的报告功能和流功能。

 






## 相关主题


[App-V 5.1 入门](getting-started-with-app-v-51.md)

 

 





