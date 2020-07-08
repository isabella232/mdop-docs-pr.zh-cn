---
title: MBAM 1.0 部署清单
description: MBAM 1.0 部署清单
author: dansimp
ms.assetid: 7e00be23-36a0-4b0f-8663-3c4f2c71546d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 96725183af2cb4e3d86d3f42973452c598497773
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798070"
---
# MBAM 1.0 部署清单


此清单旨在帮助你部署 Microsoft BitLocker 管理和监视（MBAM）。

**注意**  
此清单列出了推荐的步骤，并提供了在部署 MBAM 功能时要考虑的项目的高级列表。 我们建议你将此清单复制到电子表格程序中，并针对你的特定需求对其进行自定义。



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
<td align="left"><p>完成规划阶段以准备 MBAM 部署的计算环境。</p></td>
<td align="left"><p><a href="mbam-10-planning-checklist.md" data-raw-source="[MBAM 1.0 Planning Checklist](mbam-10-planning-checklist.md)">MBAM 1.0 计划清单</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>查看有关 MBAM 支持的配置的信息，确保所选客户端和服务器计算机支持 MBAM 功能安装。</p></td>
<td align="left"><p><a href="mbam-10-supported-configurations.md" data-raw-source="[MBAM 1.0 Supported Configurations](mbam-10-supported-configurations.md)">MBAM 1.0 支持的配置</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>按以下顺序运行 MBAM 安装程序以部署 MBAM 服务器功能：</p>
<ol>
<li><p>恢复和硬件数据库</p></li>
<li><p>合规性状态数据库</p></li>
<li><p>合规性审核和报告</p></li>
<li><p>管理和监视服务器</p></li>
<li><p>MBAM 组策略模板</p></li>
</ol>
<div class="alert">
<strong>注意</strong><br/><p>跟踪安装每个功能的服务器的名称。 您将在整个安装过程中使用此信息。</p>
</div>
<div>

</div></td>
<td align="left"><p><a href="deploying-the-mbam-10-server-infrastructure.md" data-raw-source="[Deploying the MBAM 1.0 Server Infrastructure](deploying-the-mbam-10-server-infrastructure.md)">部署 MBAM 1.0 服务器基础结构</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>将在计划阶段创建的 Active Directory 域服务安全组添加到相应的服务器上的相应本地 MBAM 服务器功能管理员组。</p></td>
<td align="left"><p><a href="planning-for-mbam-10-administrator-roles.md" data-raw-source="[Planning for MBAM 1.0 Administrator Roles](planning-for-mbam-10-administrator-roles.md)">规划 MBAM 1.0 管理员角色 </a> 以及 <a href="how-to-manage-mbam-administrator-roles-mbam-1.md" data-raw-source="[How to Manage MBAM Administrator Roles](how-to-manage-mbam-administrator-roles-mbam-1.md)"> 如何管理 MBAM 管理员角色</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>创建和部署所需的 MBAM 组策略对象。</p></td>
<td align="left"><p><a href="deploying-mbam-10-group-policy-objects.md" data-raw-source="[Deploying MBAM 1.0 Group Policy Objects](deploying-mbam-10-group-policy-objects.md)">部署 MBAM 1.0 组策略对象</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>部署 MBAM 客户端软件。</p></td>
<td align="left"><p><a href="deploying-the-mbam-10-client.md" data-raw-source="[Deploying the MBAM 1.0 Client](deploying-the-mbam-10-client.md)">部署 MBAM 1.0 客户端</a></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>



## 相关主题


[部署 MBAM 1.0](deploying-mbam-10.md)









