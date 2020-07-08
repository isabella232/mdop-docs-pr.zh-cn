---
title: 计划从以前版本的 App-V 迁移
description: 计划从以前版本的 App-V 迁移
author: dansimp
ms.assetid: 4a058047-9674-41bc-8050-c58c97a80a9b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/21/2016
ms.openlocfilehash: d7f2496b355aee6a598fee44c84e7e8c0f755c4f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798303"
---
# 计划从以前版本的 App-V 迁移


使用以下信息可计划从早期版本的 App-v 迁移到 Microsoft Application Virtualization （App-v）5.1。

## 迁移要求


开始任何升级之前，请查看以下要求：

-   如果从早于 App-v 4.6 SP2 的版本升级，请先升级到版本 App-v 4.6 SP3，然后再升级到 app-v 5.1 或更高版本。 在此方案中，首先升级 App-v 客户端，然后升级服务器组件。
**注意：** App-v 4.6 已退出主流支持。

-   App-v 5.1 仅支持使用 App-v 5.0 或 App-v 5.1 创建的程序包，或者仅支持已转换为**appv**格式的程序包。

-   如果你要从 App-v 5.0 SP1 升级 app-v 服务器，请参阅[关于 app-v 5.1](about-app-v-51.md#bkmk-migrate-to-51)了解相关说明。

## 与 app-v 4.6 同时运行 app-v 5.1 客户端


可以在具有 App-v 4.6 SP3 客户端的同一计算机上同时运行 app-v 5.1 客户端。

运行共存的 App-v 客户端时，可以：

-   当同时运行两个客户端时，将 app-v 4.6 SP3 程序包转换为 App-v 5.1 格式并发布这两个程序包。

-   为已转换的程序包定义迁移策略，从而允许已转换的 App-v 5.1 程序包假设来自 App-v 4.6 程序包的文件类型关联和快捷方式。

### 支持的共存方案

下表显示了受支持的应用程序-V 共存方案。 我们建议你在运行共存的客户端时，安装给定发布的最新可用更新。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">App-v 4.6 客户端类型</th>
<th align="left">App-v 5.1 客户端类型</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>App-v 4.6 SP3</p></td>
<td align="left"><p>App-V 5.1</p></td>
</tr>
<tr class="even">
<td align="left"><p>App-v 4.6 SP3 RDS</p></td>
<td align="left"><p>App-v 5.1 RDS</p></td>
</tr>
</tbody>
</table>

 

### 运行共存客户端的要求

若要运行共存的客户端，您必须：

-   在安装 app-v 5.1 客户端之前安装 app-v 4.6 客户端。

-   启用 "**启用迁移模式**" 组策略设置，该设置位于**app-v** &gt; **客户端共存**节点中。 若要部署 admx 模板，请参阅[如何下载和部署 MDOP 组策略（admx）模板](https://technet.microsoft.com/library/dn659707.aspx)。

**注意** 如果你有共存的 app-v 5.1 和4.6 安装，则 app-v 5.1 程序包可以并排与 App-v 4.6 程序包并行运行。 但是，app-v 5.1 程序包无法与同一虚拟环境中的 app-v 4.6 程序包交互。

 

### 客户端下载和文档

下表提供了指向 App-v 4.6 客户端下载以及有关这些版本的 TechNet 文档的链接。 下载内容包括 App-v "常规" 和 RDS 客户端。 有关 App-v 客户端的 TechNet 文档适用于两个客户端，除非另行说明。

<table>
<colgroup>
<col width="33%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">App-v 版本</th>
<th align="left">链接到 TechNet 文档</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>App-v 4.6 SP3</p></td>
<td align="left"><p><a href="https://technet.microsoft.com/library/dn511019.aspx" data-raw-source="[About Microsoft Application Virtualization 4.6 SP3](https://technet.microsoft.com/library/dn511019.aspx)">关于 Microsoft Application Virtualization 4.6 SP3</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>App-v 4.6 SP3</p></td>
<td align="left"><p><a href="about-app-v-51.md" data-raw-source="[About Microsoft Application Virtualization 5.1](about-app-v-51.md)">关于 Microsoft Application Virtualization 5。1</a></p></td>
</tr>
</tbody>
</table>

 

有关如何配置 App-v 5.1 客户端共存的详细信息，请参阅：

-   [如何在同一台计算机上部署 app-v 4.6 和 app-v 5.1 客户端](how-to-deploy-the-app-v-46-and-the-app-v--51-client-on-the-same-computer.md)

-   [App-v 5.0 共存和迁移](https://technet.microsoft.com/windows/jj835811.aspx)

## <a href="" id="converting--previous-version--packages-using-the-package-converter-"></a>使用软件包转换器转换 "早期版本" 程序包


将使用应用程序 4.6 SP2 或更早版本创建的程序包迁移到 app-v 5.1 之前，请查看以下要求：

-   必须将程序包转换为**appv**文件格式。

-   程序包转换器仅支持使用 App-v 4.5 和更高版本创建的程序包的直接转换。 若要在使用早期版本创建的程序包上使用程序包转换器，必须使用 sequencer 的 app-v 或更高版本升级程序包，然后你可以执行程序包转换。

有关使用程序包转换器转换程序包的详细信息，请参阅[如何转换在早期版本的 app-v 中创建的程序包](how-to-convert-a-package-created-in-a-previous-version-of-app-v51.md)。 转换文件后，可将其部署到运行 app-v 5.1 客户端的目标计算机。






## 相关主题


[计划部署 App-V](planning-to-deploy-app-v51.md)

 

 





