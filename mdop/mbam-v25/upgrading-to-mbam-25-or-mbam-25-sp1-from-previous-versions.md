---
title: 从先前版本升级到 MBAM 2.5 或 MBAM 2.5 SP1
description: 从先前版本升级到 MBAM 2.5 或 MBAM 2.5 SP1
author: dansimp
ms.assetid: a9edb4b8-5d5e-42ab-8db6-619db2878e50
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 07a03ebbbfce45f7f69a85000e18ddf1a58e53ad
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798124"
---
# 从先前版本升级到 MBAM 2.5 或 MBAM 2.5 SP1


本主题介绍了从早期版本的 MBAM 升级 Microsoft BitLocker 管理和监视（MBAM）服务器和 MBAM 客户端的过程。

**注意** 你可以从任何以前版本的 MBAM 直接升级到 MBAM 2.5 或 MBAM 2.5 SP1。

 

## 开始升级之前


在开始升级之前查看以下信息。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">开始之前需要了解的内容</th>
<th align="left">详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>如果要在一台服务器上安装 MBAM 网站，并在另一台服务器上安装 web 服务，则必须使用 Windows PowerShell cmdlet 对其进行配置。</p></td>
<td align="left"><p>MBAM Server 配置向导不支持在另一台服务器上配置网站，也不支持在其他服务器上配置 web 服务。</p></td>
</tr>
<tr class="even">
<td align="left"><p>如果你要从 Windows Server2008 R2 中的 MBAM 2.0 或 2.0 SP1 升级到 MBAM 2.5 或 2.5 SP1：</p>
<p>如果在已安装 Internet 信息服务（IIS）之后安装所需的 .NET Framework 4.5 软件，则管理和监视网站和自助服务门户将无法正常工作。</p>
<p>出现此问题的原因是，如果在安装 IIS 后安装了 .NET Framework，ASP.NET 无法正确注册 IIS。</p></td>
<td align="left"><p><strong>要解决此问题，请执行以下操作：</strong></p>
<p><strong>从以下位置运行 aspnet_regiis-i </strong> ：</p>
<p>C:\windows\microsoft.net\Framework\v4.0.30319</p>
<p>有关详细信息，请参阅： <a href="https://go.microsoft.com/fwlink/?LinkId=393272" data-raw-source="[ASP.NET IIS Registration Tool](https://go.microsoft.com/fwlink/?LinkId=393272)"> ASP.NET IIS 注册工具 </a> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>如果以下所有条件均为 true，则在应用程序池帐户上注册 SPN：</p>
<ul>
<li><p>您从 MBAM 的早期版本升级。</p></li>
<li><p>目前，你没有在负载平衡或分布式配置下运行 MBAM 网站，但你希望在升级到 MBAM 2.5 或 2.5 SP1 时执行此操作。</p></li>
</ul></td>
<td align="left"><p>有关说明，请参阅 <a href="planning-how-to-secure-the-mbam-websites.md#bkmk-registerspn" data-raw-source="[Planning How to Secure the MBAM Websites](planning-how-to-secure-the-mbam-websites.md#bkmk-registerspn)"> 规划如何保护 MBAM 网站的安全 </a> 。</p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>我们建议的操作</strong></p></td>
<td align="left"><p>注册应用程序池帐户的服务主体名称（SPN），即使你可能已注册了计算机帐户的 Spn 也是如此。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>我们建议的原因</strong></p></td>
<td align="left"><p>若要在负载平衡或分布式配置中配置网站，必须在应用程序池帐户上注册 SPN。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>如果已在计算机帐户上配置 Spn，会发生什么情况？</strong></p></td>
<td align="left"><p>MBAM 将使用你已注册的 Spn，并且无需配置其他 Spn，但你无法在负载平衡或分布式配置中配置网站。</p></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
</tbody>
</table>

 

## 升级 MBAM Server 基础结构的步骤


使用以下部分中的步骤升级 MBAM 以获取独立拓扑或 System Center Configuration Manager 集成拓扑。

**升级 MBAM 服务器基础结构以获取独立拓扑**

1.  从 "**程序和功能**" 和 "web 服务器" 中卸载以前版本的 MBAM，以确保信息不会从 MBAM 客户端写入 MBAM 基础结构。 有关说明，请参阅[删除 MBAM 服务器功能或软件](removing-mbam-server-features-or-software.md#bkmk-removeserverfeatures)。

2.  备份数据库。

3.  通过使用 "**程序和功能**" （包括通过 Sql Server Reporting SERVICES 托管 MBAM 报表的 sql server），从 SQL Server 中卸载以前版本的 MBAM。 从数据库服务器和 reporting services 中删除任何剩余的 MBAM 服务器临时文件或文件夹。

    **注意** 将不会删除数据库，并且在数据库中维护所有合规性和恢复数据。

     

4.  按照该顺序安装和配置 MBAM 2.5 或 2.5 SP1 数据库、报表和 web 应用程序。 数据库已就地升级。

5.  使用 MBAM 2.5 模板更新组策略对象（Gpo），以利用 MBAM 中的新功能，如强制加密。 如果不将 Gpo 和 MBAM 客户端更新为 MBAM 2.5，则较早版本的 MBAM 客户端将继续向你的当前 Gpo 提供缩减功能的报告。 了解[如何获取 MDOP 组策略（admx）模板](https://www.microsoft.com/download/details.aspx?id=41183)以下载最新的 admx 模板。

    升级 MBAM 服务器基础结构后，现有客户端计算机会继续成功地向 MBAM 2.5 或 2.5 SP1 服务器报告，并继续存储恢复数据。

6.  安装最新的 MBAM 2.5 或 2.5 SP1 客户端。 部署后不需要重新启动客户端计算机。

**升级 System Center Configuration Manager 集成拓扑的 MBAM 基础结构**

1.  从 "**程序和功能**" 和 "web 服务器" 中卸载以前版本的 MBAM，以确保信息不会从 MBAM 客户端写入 MBAM 基础结构。 有关说明，请参阅[删除 MBAM 服务器功能或软件](removing-mbam-server-features-or-software.md#bkmk-removeserverfeatures)。

2.  备份数据库。

3.  通过使用 "**程序和功能**" （包括通过 Sql Server Reporting SERVICES 托管 MBAM 报表的 sql server），从 SQL Server 中卸载以前版本的 MBAM。 从数据库服务器和 reporting services 中删除任何剩余的 MBAM 服务器临时文件或文件夹。

4.  从 Configuration Manager 服务器卸载 MBAM。

    **注意** 数据库和配置管理器对象（基准、MBAM 支持的计算机集合和报告）将不会被删除，并且所有合规性和恢复数据都将保留在数据库中。

     

5.  更新 mof 文件。

6.  按照该顺序安装和配置 MBAM 2.5 或 2.5 SP1 数据库、报表、web 应用程序和 Configuration Manager 集成。 数据库和配置管理器对象已就地升级。

7.  （可选）更新组策略对象（Gpo），如果要在 MBAM 中实现新功能（如强制加密），请编辑设置。 如果不更新 Gpo，MBAM 将继续报告当前 Gpo。 了解[如何获取 MDOP 组策略（admx）模板](https://docs.microsoft.com/microsoft-desktop-optimization-pack/solutions/how-to-download-and-deploy-mdop-group-policy--admx--templates)以下载最新的 admx 模板。

    升级 MBAM 服务器基础结构后，现有客户端计算机会继续成功地向 MBAM 2.5 或 2.5 SP1 服务器报告，并继续存储恢复数据。

8.  安装最新的 MBAM 2.5 或 2.5 SP1 客户端。 部署后不需要重新启动客户端计算机。

## MBAM 客户端的升级支持


MBAM 支持从任何早期版本的 MBAM 客户端升级到 MBAM 2.5 客户端。

**安装 MBAM 客户端的方法：**

-   在安装 MBAM 2.5 服务器基础结构之后，立即或逐步升级运行 MBAM 客户端的计算机。

-   通过电子软件分发系统或通过诸如 Active Directory 域服务或 System Center Configuration Manager 之类的工具安装 MBAM 客户端。



## 相关主题


[部署 MBAM 2.5](deploying-mbam-25.md)

[部署 MBAM 2.5 客户端](deploying-the-mbam-25-client.md)

[配置 MBAM 2.5 服务器功能](configuring-the-mbam-25-server-features.md)

 

## 已获得 MBAM 的建议？
- 在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。
- 对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。 





