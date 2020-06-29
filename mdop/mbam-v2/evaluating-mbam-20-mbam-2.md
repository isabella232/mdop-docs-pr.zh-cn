---
title: 评估 MBAM 2.0
description: 评估 MBAM 2.0
author: dansimp
ms.assetid: bfc77eec-0fd7-4fec-9c78-6870afa87152
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b7be883f44f5f09a904f619972ae3e7c35261d26
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803628"
---
# 评估 MBAM 2.0


在将 Microsoft BitLocker 管理和监视（MBAM）部署到生产环境之前，应在测试环境中对其进行评估。 本主题中的信息可用于在单服务器测试环境中使用独立拓扑设置 Microsoft BitLocker 管理和监视，仅供评估之用。 对于生产环境，不推荐使用单服务器拓扑。

有关在测试环境中部署 MBAM 的说明，请参阅[如何在单个服务器上安装和配置 MBAM](how-to-install-and-configure-mbam-on-a-single-server-mbam-2.md)。

## 设置测试环境


即使你要在测试环境中设置要评估的 MBAM 的非生产实例，你仍应验证你是否满足先决条件和硬件和软件要求。 开始安装之前，请参阅[MBAM 2.0 部署先决条件](mbam-20-deployment-prerequisites-mbam-2.md)、 [MBAM 2.0 支持的配置](mbam-20-supported-configurations-mbam-2.md)和[为 MBAM 2.0 准备环境](preparing-your-environment-for-mbam-20-mbam-2.md)。

### 规划 MBAM 评估部署

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
<td align="left"><p>查看有关 MBAM 的入门信息，以在开始部署规划之前对产品进行基本的了解。</p></td>
<td align="left"><p><a href="getting-started-with-mbam-20-mbam-2.md" data-raw-source="[Getting Started with MBAM 2.0](getting-started-with-mbam-20-mbam-2.md)">MBAM 2.0 入门</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>规划 MBAM 2.0 部署先决条件并准备你的计算环境。</p></td>
<td align="left"><p><a href="mbam-20-deployment-prerequisites-mbam-2.md" data-raw-source="[MBAM 2.0 Deployment Prerequisites](mbam-20-deployment-prerequisites-mbam-2.md)">MBAM 2.0 部署先决条件</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>规划和配置 MBAM 组策略要求。</p></td>
<td align="left"><p><a href="planning-for-mbam-20-group-policy-requirements-mbam-2.md" data-raw-source="[Planning for MBAM 2.0 Group Policy Requirements](planning-for-mbam-20-group-policy-requirements-mbam-2.md)">计划 MBAM 2.0 组策略要求</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>规划和创建必要的 ActiveDirectoryDomainServices 安全组，并针对 MBAM 本地安全组成员身份要求进行规划。</p></td>
<td align="left"><p><a href="planning-for-mbam-20-administrator-roles-mbam-2.md" data-raw-source="[Planning for MBAM 2.0 Administrator Roles](planning-for-mbam-20-administrator-roles-mbam-2.md)">计划 MBAM 2.0 管理员角色</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>规划部署 MBAM Server 功能部署。</p></td>
<td align="left"><p><a href="planning-for-mbam-20-server-deployment-mbam-2.md" data-raw-source="[Planning for MBAM 2.0 Server Deployment](planning-for-mbam-20-server-deployment-mbam-2.md)">计划 MBAM 2.0 服务器部署</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>规划部署 MBAM 客户端部署。</p></td>
<td align="left"><p><a href="planning-for-mbam-20-client-deployment-mbam-2.md" data-raw-source="[Planning for MBAM 2.0 Client Deployment](planning-for-mbam-20-client-deployment-mbam-2.md)">计划 MBAM 2.0 客户端部署</a></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>

 

### 执行 MBAM 评估部署

完成必要的规划和软件必备安装以准备 MBAM 安装的计算环境后，您可以开始 MBAM 评估部署。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>查看 MBAM 支持的配置信息，确保所选客户端和服务器计算机支持 MBAM 功能安装。</p></td>
<td align="left"><p><a href="mbam-20-supported-configurations-mbam-2.md" data-raw-source="[MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md)">MBAM 2.0 支持的配置</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>运行 MBAM 安装程序以在单个服务器上部署 MBAM 服务器功能，以供评估之用。</p></td>
<td align="left"><p><a href="how-to-install-and-configure-mbam-on-a-single-server-mbam-2.md" data-raw-source="[How to Install and Configure MBAM on a Single Server](how-to-install-and-configure-mbam-on-a-single-server-mbam-2.md)">如何在单个服务器上安装和配置 MBAM</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>将在计划阶段创建的 ActiveDirectoryDomainServices 安全组添加到新 MBAM 服务器上相应的本地 MBAM 服务器功能本地组。</p></td>
<td align="left"><p><a href="planning-for-mbam-20-administrator-roles-mbam-2.md" data-raw-source="[Planning for MBAM 2.0 Administrator Roles](planning-for-mbam-20-administrator-roles-mbam-2.md)">规划 MBAM 2.0 管理员角色 </a> 以及 <a href="how-to-manage-mbam-administrator-roles-mbam-2.md" data-raw-source="[How to Manage MBAM Administrator Roles](how-to-manage-mbam-administrator-roles-mbam-2.md)"> 如何管理 MBAM 管理员角色</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>创建和部署所需的 MBAM 组策略对象。</p></td>
<td align="left"><p><a href="deploying-mbam-20-group-policy-objects-mbam-2.md" data-raw-source="[Deploying MBAM 2.0 Group Policy Objects](deploying-mbam-20-group-policy-objects-mbam-2.md)">部署 MBAM 2.0 组策略对象</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>部署 MBAM 客户端软件。</p></td>
<td align="left"><p><a href="deploying-the-mbam-20-client-mbam-2.md" data-raw-source="[Deploying the MBAM 2.0 Client](deploying-the-mbam-20-client-mbam-2.md)">部署 MBAM 2.0 客户端</a></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>

 

## 为 MBAM 评估配置实验室计算机


本部分包含可用于加速 MBAM 客户端状态报告的信息。 但是，这些修改只应用于测试目的。

**注意** 下一节中的信息介绍了如何修改 Windows 注册表。 注册表编辑器使用不当可能导致严重问题，可能需要重新安装 Windows。 Microsoft 无法保证无法通过错误地使用注册表编辑器来解决所产生的问题。 使用注册表编辑器的风险由您自己承担。

 

### 修改 MBAM 客户端状态报告频率设置

MBAM 客户端唤醒和状态报告频率在使用组策略设置时的最小值为90分钟。 你可以使用 Windows 注册表将这些频率更改为 MBAM 客户端计算机上的较低值，以帮助加速测试。

要修改 MBAM 客户端状态报告频率设置，请执行以下操作：

1.  使用注册表编辑器导航到**HKLM\\Software\\Policies\\Microsoft\\FVE\\MDOPBitLockerManagement**。

2.  将**ClientWakeupFrequency**和**StatusReportingFrequency**的值更改为**1** ，以支持最小客户端支持的值。 此更改导致 MBAM 客户端每分钟报告一次。

3.  重新启动**BitLocker 管理客户端服务**。

**注意** 若要设置这种低的值，必须在注册表中手动设置它们。

 

### 修改 MBAM 客户端服务启动延迟

除了 MBAM 客户端唤醒和状态报告频率之外，在客户端计算机上启动 MBAM 客户端代理服务时，随机延迟最多为90分钟。 如果不希望随机延迟，请在 " **HKLM\\Software\\Microsoft\\MBAM**" 下创建**NoStartupDelay**的**DWORD**值，将其值设置为**1**，然后重新启动**BitLocker 管理客户端服务**。

## 相关主题


[MBAM 2.0 入门](getting-started-with-mbam-20-mbam-2.md)

 

 





