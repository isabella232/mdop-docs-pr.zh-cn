---
title: MBAM 2.5 部署清单
description: MBAM 2.5 部署清单
author: dansimp
ms.assetid: 2ba7de17-e3a4-4798-99e0-cd1dc28c5b76
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 11609b3d6d44d62b032e35005e5d967ca6d4e83b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803247"
---
# MBAM 2.5 部署清单


在使用独立拓扑的 Microsoft BitLocker 管理和监视（MBAM）部署期间，你可以使用此清单帮助你。

**注意**  
此清单列出了在部署 Microsoft BitLocker 管理和监视功能时要考虑的推荐步骤和高级列表项。 我们建议您将此清单复制到电子表格程序中，并对其进行自定义以供使用。



<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left">任务</th>
<th align="left">引用</th>
<th align="left">注释</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>查看并完成所有计划步骤，以便为 MBAM 部署准备环境。</p></td>
<td align="left"><p><a href="mbam-25-planning-checklist.md" data-raw-source="[MBAM 2.5 Planning Checklist](mbam-25-planning-checklist.md)">MBAM 2.5 规划清单</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>查看受支持的配置信息，确保 MBAM 支持所选客户端和服务器计算机。</p></td>
<td align="left"><p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)">MBAM 2.5 支持的配置</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>安装 MBAM Server 软件。</p></td>
<td align="left"><p><a href="installing-the-mbam-25-server-software.md" data-raw-source="[Installing the MBAM 2.5 Server Software](installing-the-mbam-25-server-software.md)">安装 MBAM 2.5 服务器软件</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>配置 MBAM 服务器功能：</p>
<ul>
<li><p>合规性和审核数据库和恢复数据库</p></li>
<li><p>报告</p></li>
<li><p>Web 应用程序</p></li>
<li><p>Configuration Manager 集成拓扑（仅在你通过此拓扑运行 MBAM 时才需要）</p></li>
</ul>
<div class="alert">
<strong>注意</strong><br/><p>记下在其上配置每个功能的服务器的名称。 您将在整个配置过程中使用此信息。</p>
</div>
<div>

</div></td>
<td align="left"><p><a href="configuring-the-mbam-25-server-features.md" data-raw-source="[Configuring the MBAM 2.5 Server Features](configuring-the-mbam-25-server-features.md)">配置 MBAM 2.5 服务器功能</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>验证 MBAM 配置。</p></td>
<td align="left"><p><a href="validating-the-mbam-25-server-feature-configuration.md" data-raw-source="[Validating the MBAM 2.5 Server Feature Configuration](validating-the-mbam-25-server-feature-configuration.md)">验证 MBAM 2.5 服务器功能配置</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>复制 MBAM 组策略模板并编辑组策略设置。</p></td>
<td align="left"><p><a href="copying-the-mbam-25-group-policy-templates.md" data-raw-source="[Copying the MBAM 2.5 Group Policy Templates](copying-the-mbam-25-group-policy-templates.md)">复制 MBAM 2.5 组策略模板 </a> 并 <a href="editing-the-mbam-25-group-policy-settings.md" data-raw-source="[Editing the MBAM 2.5 Group Policy Settings](editing-the-mbam-25-group-policy-settings.md)"> 编辑 MBAM 2.5 组策略设置</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>部署 MBAM 客户端软件。</p></td>
<td align="left"><p><a href="deploying-the-mbam-25-client.md" data-raw-source="[Deploying the MBAM 2.5 Client](deploying-the-mbam-25-client.md)">部署 MBAM 2.5 客户端</a></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>




## 相关主题


[部署 MBAM 2.5](deploying-mbam-25.md)




## 已获得 MBAM 的建议？
- 在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。 
- 对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。




