---
title: 评估 MBAM 1.0
description: 评估 MBAM 1.0
author: dansimp
ms.assetid: a1e2b674-eda9-4e1c-9b4c-e748470c71f2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: f09b06af52f5738fd50bfe727987b760d98552d9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803731"
---
# 评估 MBAM 1.0


在将 Microsoft BitLocker 管理和监视（MBAM）部署到生产环境之前，应在实验室环境中对其进行评估。 你可以使用本主题中的信息在单个服务器实验室环境中设置 MBAM，以便仅用于评估目的。

虽然实际部署步骤与在[单个服务器上安装和配置 MBAM](how-to-install-and-configure-mbam-on-a-single-server-mbam-1.md)的方案非常相似，但本主题包含可让你在最少的时间内设置 MBAM 评估环境的其他信息。

## 设置实验室环境


即使在实验室环境中设置要评估的 MBAM 的非生产实例，仍应验证是否满足部署先决条件以及硬件和软件要求。 有关详细信息，请参阅[MBAM 1.0 部署先决条件](mbam-10-deployment-prerequisites.md)和[MBAM 1.0 支持的配置](mbam-10-supported-configurations.md)。 在开始 MBAM 评估部署之前，还应查看[准备 MBAM 1.0 的环境](preparing-your-environment-for-mbam-10.md)。

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
<td align="left"><p><a href="getting-started-with-mbam-10.md" data-raw-source="[Getting Started with MBAM 1.0](getting-started-with-mbam-10.md)">MBAM 1.0 入门</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p></p>
<p>为 MBAM 安装准备你的计算环境。 若要执行此操作，必须在将托管 MBAM 数据库的 SQL Server 实例上启用透明数据加密（TDE）。 若要在你的实验室环境中启用 TDE，你可以创建一个 .sql 文件，以便针对托管在 MBAM 将使用的 SQL Server 实例上的 master 数据库运行。</p>
<div class="alert">
<strong>注意</strong><br/><p>你可以使用以下示例为你的实验室环境创建 .sql 文件，以便在将托管 MBAM 数据库的 SQL Server 实例上快速启用 TDE。 这些 SQL Server 命令将使用本地签名的 SQL Server 证书启用 TDE。 确保将 TDE 证书及其关联的加密密钥备份到 C:\Backup 的示例本地备份路径 <em> </em> 。 恢复数据库或将证书和密钥移动到具有 TDE 加密的另一台服务器时，需要 TDE 证书和密钥。</p>
</div>
<div>

</div>
<pre class="syntax" space="preserve"><code>USE master;
GO
CREATE MASTER KEY ENCRYPTION BY PASSWORD = &#39;P@55w0rd&#39;;
GO
CREATE CERTIFICATE tdeCert WITH SUBJECT = &#39;TDE Certificate&#39;;
GO
BACKUP CERTIFICATE tdeCert TO FILE = &#39;C:\Backup\TDECertificate.cer&#39;
   WITH PRIVATE KEY (
         FILE = &#39;C:\Backup\TDECertificateKey.pvk&#39;,
         ENCRYPTION BY PASSWORD = &#39;P@55w0rd&#39;);
GO</code></pre></td>
<td align="left"><p><a href="mbam-10-deployment-prerequisites.md" data-raw-source="[MBAM 1.0 Deployment Prerequisites](mbam-10-deployment-prerequisites.md)">MBAM 1.0 部署先决条件</a></p>
<p><a href="https://go.microsoft.com/fwlink/?LinkId=269703" data-raw-source="[Database Encryption in SQL Server 2008 Enterprise Edition](https://go.microsoft.com/fwlink/?LinkId=269703)">SQL Server 2008 企业版中的数据库加密</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>规划和配置 MBAM 组策略要求。</p></td>
<td align="left"><p><a href="planning-for-mbam-10-group-policy-requirements.md" data-raw-source="[Planning for MBAM 1.0 Group Policy Requirements](planning-for-mbam-10-group-policy-requirements.md)">计划 MBAM 1.0 组策略要求</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>规划和创建必要的 Active Directory 域服务安全组，并针对 MBAM 本地安全组成员身份要求进行规划。</p></td>
<td align="left"><p><a href="planning-for-mbam-10-administrator-roles.md" data-raw-source="[Planning for MBAM 1.0 Administrator Roles](planning-for-mbam-10-administrator-roles.md)">计划 MBAM 1.0 管理员角色</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>规划 MBAM Server 功能部署。</p></td>
<td align="left"><p><a href="planning-for-mbam-10-server-deployment.md" data-raw-source="[Planning for MBAM 1.0 Server Deployment](planning-for-mbam-10-server-deployment.md)">计划 MBAM 1.0 服务器部署</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>规划 MBAM 客户端部署。</p></td>
<td align="left"><p><a href="planning-for-mbam-10-client-deployment.md" data-raw-source="[Planning for MBAM 1.0 Client Deployment](planning-for-mbam-10-client-deployment.md)">计划 MBAM 1.0 客户端部署</a></p></td>
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
<td align="left"><p><a href="mbam-10-supported-configurations.md" data-raw-source="[MBAM 1.0 Supported Configurations](mbam-10-supported-configurations.md)">MBAM 1.0 支持的配置</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>运行 MBAM 安装程序以在单个服务器上部署 MBAM 服务器功能，以供评估之用。</p></td>
<td align="left"><p><a href="how-to-install-and-configure-mbam-on-a-single-server-mbam-1.md" data-raw-source="[How to Install and Configure MBAM on a Single Server](how-to-install-and-configure-mbam-on-a-single-server-mbam-1.md)">如何在单个服务器上安装和配置 MBAM</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>将在计划阶段创建的 Active Directory 域服务安全组添加到新的 MBAM 服务器上的相应本地 MBAM 服务器功能本地组。</p></td>
<td align="left"><p><a href="planning-for-mbam-10-administrator-roles.md" data-raw-source="[Planning for MBAM 1.0 Administrator Roles](planning-for-mbam-10-administrator-roles.md)">规划 MBAM 1.0 管理员角色 </a> 以及 <a href="how-to-manage-mbam-administrator-roles-mbam-1.md" data-raw-source="[How to Manage MBAM Administrator Roles](how-to-manage-mbam-administrator-roles-mbam-1.md)"> 如何管理 MBAM 管理员角色</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>创建和部署所需的 MBAM 组策略对象。</p></td>
<td align="left"><p><a href="deploying-mbam-10-group-policy-objects.md" data-raw-source="[Deploying MBAM 1.0 Group Policy Objects](deploying-mbam-10-group-policy-objects.md)">部署 MBAM 1.0 组策略对象</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>部署 MBAM 客户端软件。</p></td>
<td align="left"><p><a href="deploying-the-mbam-10-client.md" data-raw-source="[Deploying the MBAM 1.0 Client](deploying-the-mbam-10-client.md)">部署 MBAM 1.0 客户端</a></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>



## 为 MBAM 评估配置实验室计算机


你可以使用注册表编辑器更改 MBAM 客户端状态报告上的频率设置。 但是，这些修改只应用于测试目的。

**警告**  
本主题介绍如何使用注册表编辑器更改 Windows 注册表。 如果不正确地更改 Windows 注册表，则可能会导致严重问题，可能需要重新安装 Windows。 在更改注册表之前，应创建注册表文件（.dat 和 .dat）的备份副本。 Microsoft 无法保证更改注册表时可能出现的问题可以解决。 更改注册表的风险由您自己承担。



### <a href="" id="modify-the-frequency-settings-on-mbam-client-status-reporting-"></a>在 MBAM 客户端状态报告上修改频率设置

当设置为使用组策略时，MBAM 客户端唤醒和状态报告频率的最小值为90分钟。 你可以通过将 Windows 注册表编辑为更低的值来更改 MBAM 客户端计算机上的这些频率，这将有助于加速测试。 若要修改 MBAM 客户端状态报告上的频率设置，请使用注册表编辑器导航到**HKLM\\Software\\Policies\\FVE\\MDOPBitLockerManagement**，将**ClientWakeupFrequency**和**StatusReportingFrequency**的值更改为**1** ，作为最小客户端支持的值，然后重新启动 BitLocker 管理客户端服务。 进行此更改时，MBAM 客户将每分钟报告一次。 只有在注册表中手动执行此操作时，才能将值设置为 "低"。

### <a href="" id="modify-the-startup-delay-on-mbam-client-service-"></a>修改 MBAM 客户端服务上的启动延迟

除了 MBAM 客户端唤醒和状态报告频率之外，在客户端计算机上启动 MBAM 客户端代理服务时，随机延迟最多为90分钟。 如果不希望随机延迟，请在 " **HKLM\\Software\\Microsoft\\MBAM**" 下创建**NoStartupDelay**的**DWORD**值，将其值设置为**1**，然后重新启动 BitLocker 管理客户端服务。

## 相关主题


[MBAM 1.0 入门](getting-started-with-mbam-10.md)









