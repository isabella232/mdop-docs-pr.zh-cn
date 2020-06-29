---
title: 如何使用 PowerShell 在 App-V 5.0 Client 上启用报告
description: 如何使用 PowerShell 在 App-V 5.0 Client 上启用报告
author: dansimp
ms.assetid: a7aaf553-0f83-4cd0-8df8-93a5f1ebe497
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c004b4900a9814a11cb2706659a2edb99de6cc1b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798458"
---
# 如何使用 PowerShell 在 App-V 5.0 Client 上启用报告


使用以下过程为报告配置 App-v 5.0。

**配置运行 app-v 5.0 客户端以进行报告的计算机**

1. 安装 app-v 5.0 客户端。 有关安装客户端的详细信息，请参阅[如何部署 App-v 客户端](how-to-deploy-the-app-v-client-gb18030.md)。

2. 在安装了 app-v 5.0 客户端之后，请使用 AppvClientConfiguration PowerShell 配置适当**的**报告配置设置：

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left">设置</th>
   <th align="left">描述</th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p>ReportingEnabled</p></td>
   <td align="left"><p>使客户端能够将信息返回到报表服务器。 客户端需要此设置才能收集客户端上的报告数据。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>ReportingServerURL</p></td>
   <td align="left"><p>指定报表服务器上保存客户端信息的位置。 例如，http:// &lt; reportingservername &gt; ： &lt; reportingportnumber &gt; 。</p>
   <div class="alert">
   <strong>注意</strong><br/><p>这是在报表服务器安装期间分配的端口号</p>
   </div>
   <div>

   </div></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>报告开始时间</p></td>
   <td align="left"><p>此设置用于计划客户端自动将数据发送到服务器。 此设置将指示报告数据将开始发送的小时数。 它采用24小时格式，并且将采用介于0-23 之间的数字。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>ReportingRandomDelay</p></td>
   <td align="left"><p>指定发送到报告服务器的数据的最大延迟（以分钟为单位）。 当计划任务启动时，客户端会在0和 ReportingRandomDelay 之间生成一个随机延迟，并在发送数据之前等待指定的持续时间。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>ReportingInterval</p></td>
   <td align="left"><p>指定客户端将用于向报告服务器重新发送数据的重试间隔。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>ReportingDataCacheLimit</p></td>
   <td align="left"><p>指定用于存储报告信息的 XML 缓存的最大大小（以兆字节（MB）为单位）。 大小应用于内存中的缓存。 达到限制时，日志文件将翻转。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>ReportingDataBlockSize</p></td>
   <td align="left"><p>指定用于存储报告信息的 XML 缓存的最大大小（以兆字节（MB）为单位）。 大小应用于内存中的缓存。 达到限制时，日志文件将翻转。</p></td>
   </tr>
   </tbody>
   </table>



3. 配置相应的设置后，运行 App-v 5.0 客户端的计算机将自动收集数据并将数据发送回报表服务器。

   此外，管理员还可以使用**send-AppvClientReport** PowerShell cmdlet 以按需方式向后手动发送数据。

   已**获得有关 app-v 的建议**？ 在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。 **遇到了 app-v 问题？** 使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相关主题


[使用 PowerShell 管理 App-V](administering-app-v-by-using-powershell.md)









