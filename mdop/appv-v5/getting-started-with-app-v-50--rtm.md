---
title: App-V 5.0 入门
description: App-V 5.0 入门
author: dansimp
ms.assetid: 3e16eafb-ce95-4d06-b214-fe0f4b1b495f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: a7979c81b7b57107f824b96d9fef8049a00c5b08
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798574"
---
# App-V 5.0 入门


App-v 5.0 使管理员可以在需要的基础上实时部署、更新和支持应用程序作为服务。 单个应用程序从本地安装的产品转换为集中管理的服务，并在需要时随时可用，无需预配置计算机或更改操作系统设置。

App-v 包含以下元素：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">元素</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>App-v 管理服务器</p></td>
<td align="left"><ul>
<li><p>提供用于管理 App-v 基础结构的中心位置，该位置将为应用端桌面客户端和远程桌面服务（以前称为终端服务）客户端提供虚拟应用程序。</p></li>
<li><p>对其数据存储使用 Microsoft SQL Server®，其中一个或多个 App-v 管理服务器可以共享单个 SQL Server 数据存储。</p></li>
<li><p>对请求进行身份验证，并提供安全、计量、监视和数据收集。 服务器使用 Active Directory 和支持工具管理用户和应用程序。</p></li>
<li><p>具有基于 Silverlight®的管理网站，使你能够从任意计算机配置 App-v 基础结构。 你可以添加和删除应用程序、操作快捷方式、为用户和组分配访问权限以及创建连接组。</p></li>
<li><p>启用 app-v Web 管理控制台和 SQL Server 数据存储之间的通信。 这些组件可以安装在一台服务器计算机上，也可以安装在一台或多台单独的计算机上，具体取决于所需的系统体系结构。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>App-v 发布服务器</p></td>
<td align="left"><ul>
<li><p>为特定用户提供具有标题的应用程序的 app-v 客户端</p></li>
<li><p>托管用于流式处理的虚拟应用程序包。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>App-v 桌面客户端</p></td>
<td align="left"><ul>
<li><p>检索虚拟应用程序</p></li>
<li><p>在客户端上发布应用程序</p></li>
<li><p>在 Windows 终结点上的运行时自动设置和管理虚拟环境。</p></li>
<li><p>在每个用户&#39;s 配置文件中存储特定于用户的虚拟应用程序设置，如注册表和文件更改。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>App-v 远程桌面服务（RDS）客户端</p></td>
<td align="left"><p>使远程桌面会话主机服务器能够使用 app-v 桌面客户端的功能来实现共享桌面会话。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>App-v 排序器</p></td>
<td align="left"><ul>
<li><p>是一个基于向导的工具，可用于将传统应用程序转换为虚拟应用程序。</p></li>
<li><p>生成应用程序 "程序包"，其中包括：</p>
<ol>
<li><p>顺序应用程序（APPV）文件</p></li>
<li><p>可部署到为独立操作配置的客户端的 Windows Installer 文件（MSI）</p></li>
<li><p>包含 Report.XML、PackageName_DeploymentConfig.XML 和 PackageName_UserConfig.XML 的多个 XML 文件。 UserConfig 和 DeploymentConfig XML 文件用于配置对程序包的默认行为的自定义更改。</p></li>
</ol></li>
</ul></td>
</tr>
</tbody>
</table>

 

有关这些元素的详细信息，请参阅[app-v 5.0 的高级别体系结构](high-level-architecture-for-app-v-50.md)。

如果您不熟悉本产品，我们建议您仔细阅读文档。 在将其部署到生产环境之前，我们还建议你在测试网络环境中验证你的部署计划。 你还可以考虑获取有关相关技术的类。 有关 Microsoft 培训商机的详细信息，请参阅 Microsoft 培训概述 <https://go.microsoft.com/fwlink/p/?LinkId=80347> 。

**注意** 此管理员指南的可下载版本不可用。 但是，你可以了解 TechNet 库的特殊模式，这种模式允许你选择文章、将它们分组在一个集合中，或将其打印到文件中 <https://go.microsoft.com/fwlink/?LinkId=272491> （ https://go.microsoft.com/fwlink/?LinkId=272491) 。

 

本应用程序-V 5.0 管理员指南的此部分包含有关 App-v 5.0 的高级信息，可让你在开始部署计划之前对产品有基本的了解。

## App-v 5.0 入门


-   [关于 App-V 5.0](about-app-v-50.md)

    提供 App-v 5.0 的高级概述以及它在您的组织中的使用方式。

-   [关于 App-V 5.0 SP1](about-app-v-50-sp1.md)

    提供 app-v 5.0 SP1 的高级概述以及它在您的组织中的使用方式。

-   [关于 App-V 5.0 SP2](about-app-v-50-sp2.md)

    提供 app-v 5.0 SP2 的高级概述，以及如何在组织中使用它。

-   [关于 App-V 5.0 SP3](about-app-v-50-sp3.md)

    提供 app-v 5.0 SP2 的高级概述，以及如何在组织中使用它。

-   [评估 App-V 5.0](evaluating-app-v-50.md)

    提供有关如何在组织中使用 V 5.0 的最佳评估方式的信息。

-   [App-V 5.0 的高级别体系结构](high-level-architecture-for-app-v-50.md)

    提供有关 App-v 5.0 功能以及它们如何协同工作的说明。

-   [App-V 5.0 的辅助功能](accessibility-for-app-v-50.md)

    提供有关使残障人士更易于访问本产品及其相应文档的功能和服务的信息。

## <a href="" id="other-resources-for-this-product-"></a>此产品的其他资源


-   [Microsoft Application Virtualization 5.0 管理员指南](microsoft-application-virtualization-50-administrators-guide.md)

-   [计划 App-V 5.0](planning-for-app-v-50-rc.md)

-   [部署 App-V 5.0](deploying-app-v-50.md)

-   [App-V 5.0 的操作](operations-for-app-v-50.md)

-   [App-V 5.0 疑难解答](troubleshooting-app-v-50.md)






 

 





