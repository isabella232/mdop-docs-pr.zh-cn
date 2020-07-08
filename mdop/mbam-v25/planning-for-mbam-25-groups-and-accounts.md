---
title: 规划 MBAM 2.5 组和帐户
description: 规划 MBAM 2.5 组和帐户
author: dansimp
ms.assetid: 73bb9fe5-5900-4b6f-b271-ade62991fca1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 11/02/2016
ms.openlocfilehash: 3431c3602685a4f96cb4c1333700107ba9c38b96
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803841"
---
# 规划 MBAM 2.5 组和帐户


本主题列出了必须在 Active Directory 域服务（AD DS）中创建的角色和帐户，以便为 Microsoft BitLocker 管理和监视（MBAM）数据库、报表和 web 应用程序提供安全和访问权限。 对于每个角色和帐户，提供了 MBAM Server 配置向导中的相应字段。 有关与这些帐户对应的 Windows PowerShell cmdlet 和参数的列表，请参阅[使用 Windows PowerShell 配置 MBAM 2.5 服务器功能](configuring-mbam-25-server-features-by-using-windows-powershell.md#bkmk-reqd-posh-accts)。

**注意**  
MBAM 不支持使用托管服务帐户。



## 数据库帐户


为合规性和审核数据库以及恢复数据库创建以下帐户。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">帐户名称和用途</th>
<th align="left">帐户类型</th>
<th align="left">与此帐户对应的 MBAM 服务器配置向导字段</th>
<th align="left">与此帐户对应的 "MBAM 服务器配置向导" 字段的说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>合规性和审核数据库和恢复数据库对报表的读/写用户或组</p></td>
<td align="left"><p>用户或组</p></td>
<td align="left"><p>读/写访问域用户或组</p></td>
<td align="left"><p>对合规性和审核数据库和恢复数据库具有读/写访问权限的域用户或组，使 web 应用程序能够访问这些数据库中的数据和报告。</p>
<p>如果在此字段中输入用户名，它必须与 <strong> </strong> " <strong> 配置 web 应用程序" 页面上的 "web 服务应用程序池域帐户" 字段中的值相同 </strong> 。</p>
<p>如果在此字段中输入组名称，则 " <strong> 配置 Web 应用程序" 页面上的 "Web 服务应用程序池域帐户" 字段中的值 </strong> <strong> </strong> 必须是您在此字段中输入的组的成员。</p></td>
</tr>
<tr class="even">
<td align="left"><p>对报表的合规性和审核数据库只读用户或组</p></td>
<td align="left"><p>用户或组</p></td>
<td align="left"><p>只读访问域用户或组</p></td>
<td align="left"><p>将对合规性和审核数据库具有只读访问权限的用户或组的名称，以使报表能够访问此数据库中的合规性和审核数据。</p>
<p>如果在此字段中输入用户名，则该用户名必须与你在 <strong> </strong> "配置报告" 页面上的 "合规性和审核数据库域帐户" 字段中指定的用户相同 <strong> </strong> 。</p>
<p>如果在此字段中输入组名称，则在 <strong> "配置报告" 页面上的 "合规性和审核数据库域帐户" 字段中指定的值 </strong> <strong> </strong> 必须是您在此字段中指定的组的成员。</p></td>
</tr>
</tbody>
</table>



## 报告帐户


为 "报表" 功能创建以下帐户。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">帐户名称/用途</th>
<th align="left">帐户类型</th>
<th align="left">与此帐户对应的 MBAM 服务器配置向导字段</th>
<th align="left">与此帐户对应的 "MBAM 服务器配置向导" 字段的说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>报告只读域访问组</p></td>
<td align="left"><p>组</p></td>
<td align="left"><p>报告角色域组</p></td>
<td align="left"><p>指定对管理和监视网站中的报表具有只读访问权限的域用户组。 你指定的组必须是在启用 web 应用时为 "报表只读访问" 组参数指定的相同组。</p></td>
</tr>
<tr class="even">
<td align="left"><p>合规性和审核数据库域用户帐户</p></td>
<td align="left"><p>用户</p></td>
<td align="left"><p>合规性和审核数据库域帐户</p></td>
<td align="left"><p>本地 SQL Server Reporting Services 实例用于访问合规性和审核数据库的域用户帐户和密码。 此帐户需要 <strong> 以批处理权限登录 </strong> 到 SQL Server Reporting Services 服务器。</p>
<p>如果您在 <strong> "配置数据库" 页面上的 "只读访问域用户" 或 "组" 字段中输入的值 </strong> <strong> </strong> 是用户名，则必须在此字段中输入相同的值。</p>
<p>如果您在 <strong> "配置数据库" 页面上的 "只读访问域用户" 或 "组" 字段中输入的值 </strong> <strong> </strong> 是组名称，则您在此字段中输入的值必须是该组的成员。</p>
<p>将此帐户的密码配置为永不过期。 用户帐户应该能够访问 MBAM Reports Users 组中可用的所有数据。</p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-helpdesk-roles"></a>管理和监控网站（帮助台）帐户


为 "管理和监视" 网站创建以下帐户。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">帐户名称/用途</th>
<th align="left">帐户类型</th>
<th align="left">与此帐户对应的 MBAM 服务器配置向导字段</th>
<th align="left">与此帐户对应的 "MBAM 服务器配置向导" 字段的说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Web 服务应用程序池域帐户</p></td>
<td align="left"><p>用户</p></td>
<td align="left"><p>Web 服务应用程序池域帐户</p></td>
<td align="left"><p>要由 web 应用程序的应用程序池使用的域用户帐户。</p>
<p>如果在 <strong> "配置数据库" 页面上的 "读/写访问域" 用户或组字段中输入用户名 </strong> <strong> </strong> ，则必须在此字段中输入相同的值。</p>
<p>如果在 <strong> "配置数据库" 页面上的 "读/写访问域" 用户或组字段中输入组名称 </strong> <strong> </strong> ，则在此字段中输入的值必须是该组的成员。</p>
<p>如果不指定凭据，将使用为以前启用的任何 web 应用程序指定的凭据。 所有 web 应用程序都必须使用相同的应用程序池凭据。 如果为不同的 web 应用程序指定不同的凭据，将使用最近指定的值。</p>
<div class="alert">
<strong>重要提示</strong><br/><p>为了提高安全性，请将凭据中指定的帐户设置为具有受限的用户权限。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p>MBAM 高级帮助台用户访问组</p></td>
<td align="left"><p>组</p></td>
<td align="left"><p>MBAM 高级帮助台用户</p></td>
<td align="left"><p>其成员有权访问管理和监视网站的所有恢复区域的域用户组。 具有此角色的用户必须在帮助最终用户恢复其驱动器时仅输入恢复密钥，而不是最终用户的域和用户名。 如果用户是 MBAM 支持人员组和 MBAM 高级帮助台用户组的成员，则 MBAM 高级帮助台用户组权限将替代 MBAM 帮助台组权限。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MBAM 帮助台用户访问组</p></td>
<td align="left"><p>组</p></td>
<td align="left"><p>MBAM 帮助台用户</p></td>
<td align="left"><p>其成员有权访问 MBAM 管理和监视网站的 "管理 TPM 和驱动器恢复" 区域的域用户组。 具有此角色的人员必须填写所有字段，包括最终用户的域和帐户名称，同时使用任一选项。</p>
<p>如果用户是 MBAM 支持人员组和 MBAM 高级帮助台用户组的成员，则 MBAM 高级帮助台用户组权限将替代 MBAM 帮助台组权限。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MBAM 报表用户访问组</p></td>
<td align="left"><p>组</p></td>
<td align="left"><p>MBAM 报表用户</p></td>
<td align="left"><p>其成员对管理和监视网站的 "报告" 区域中的报表具有只读访问权限的域用户组。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MBAM 数据迁移用户组</p></td>
<td align="left"><p>组</p></td>
<td align="left"><p>MBAM 数据迁移用户</p></td>
<td align="left"><p>可选域用户组，其成员具有使用 MBAM 服务器上运行的 MBAM 恢复和硬件服务将数据写入 MBAM 的权限。 此帐户通常与 Write-Mbam * cmdlet 一起使用，用于将恢复和 TPM 数据从 Active Directory 写入 MBAM 数据库。</p>
<p>有关详细信息，请参阅 <a href="mbam-25-security-considerations.md" data-raw-source="[MBAM 2.5 Security Considerations](mbam-25-security-considerations.md)"> MBAM 2.5 安全注意事项 </a> 。</p></td>
</tr>
</tbody>
</table>




## 相关主题


[为 MBAM 2.5 准备你的环境](preparing-your-environment-for-mbam-25.md)

[MBAM 2.5 部署先决条件](mbam-25-deployment-prerequisites.md)



## 已获得 MBAM 的建议？
- 在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。 
- 对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。 





