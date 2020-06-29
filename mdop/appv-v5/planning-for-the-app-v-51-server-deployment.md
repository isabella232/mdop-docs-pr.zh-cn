---
title: 计划 App-V 5.1 服务器部署
description: 计划 App-V 5.1 服务器部署
author: dansimp
ms.assetid: eedd97c9-bee0-4749-9d1e-ab9528fba398
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 31e3a116eb511356b061e6ccb18c7e25c060a66e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798295"
---
# 计划 App-V 5.1 服务器部署


Microsoft Application Virtualization （App-v） 5.1 server 基础结构包含一组专用功能，这些功能可以基于企业的要求安装在一台或多台服务器计算机上。

## 规划 app-v 5.1 服务器部署


App-v 5.1 服务器包含以下功能：

-   管理服务器-提供 app-v 5.1 基础结构的总体管理功能。

-   管理数据库-方便了 App-v 5.1 管理的数据库 predeployments。

-   发布服务器-提供虚拟应用程序的托管和流功能。

-   报表服务器-提供 app-v 5.1 reporting services。

-   报告数据库-为 App-v 5.1 报告简化数据库 predeployments。

以下列表显示了安装 app-v 5.1 服务器基础结构的推荐方法：

-   安装 app-v 5.1 服务器。 有关详细信息，请参阅[如何部署 app-v 5.1 服务器](how-to-deploy-the-app-v-51-server.md)。

-   在单独的计算机上安装数据库、报告和管理功能。 有关详细信息，请参阅[如何从管理和报告服务在单独的计算机上安装管理和报告数据库](how-to-install-the-management-and-reporting-databases-on-separate-computers-from-the-management-and-reporting-services51.md)。

-   使用电子软件分发（ESD）。 有关详细信息，请参阅[如何使用电子软件分发部署 app-v 5.1 程序包](how-to-deploy-app-v-51-packages-using-electronic-software-distribution.md)。

-   在一台计算机上安装所有服务器功能。

## <a href="" id="---------app-v-5-1-server-interaction"></a> App-v 5.1 服务器交互


本部分包含有关各种 App-v 5.1 服务器角色如何相互交互的信息。

App-v 5.1 管理服务器包含程序包的存储库及其分配的配置。 对于注册到管理服务器的发布服务器，在从运行 App-v 5.1 客户端的计算机接收发布刷新请求时，将向发布服务器提供相关联的元数据。 由单个管理服务器管理的 app-v 5.1 发布服务器可以提供不同的客户端，并且可以具有不同的网站名称和端口绑定。 此外，由同一管理服务器管理的所有发布服务器都是彼此的副本。

**注意** 管理服务器不执行任何负载平衡。 关联的元数据只会传递到发布服务器，以便在处理客户端请求时使用。

 

## 与服务器相关的协议和外部功能


下面显示了有关 App-v 5.1 服务器使用的服务器相关协议的信息。 该表还包括每种服务器类型的报告机制。

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">服务器类型</th>
<th align="left">协议</th>
<th align="left">需要外部功能</th>
<th align="left">报告</th>
<th align="left"></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>IIS 服务器</p></td>
<td align="left"><p>HTTP</p>
<p>HTTPS</p></td>
<td align="left"><p>此服务器协议组合需要一种机制来同步管理服务器和流式处理服务器之间的内容。 使用 HTTP 或 HTTPS 时，请使用 IIS 服务器和防火墙保护服务器对 Internet 的暴露。</p></td>
<td align="left"><p>内置</p></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"><p>文件</p></td>
<td align="left"><p>SMB</p></td>
<td align="left"><p>此服务器协议组合需要支持才能同步管理服务器和流服务器之间的内容。 使用具有文件共享或流功能的客户端计算机。</p></td>
<td align="left"><p>内置</p></td>
<td align="left"></td>
</tr>
</tbody>
</table>

 






## 相关主题


[计划部署 App-V](planning-to-deploy-app-v51.md)

[部署 App-V 5.1 Server](deploying-the-app-v-51-server.md)

 

 





