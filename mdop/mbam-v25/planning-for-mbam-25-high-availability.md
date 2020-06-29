---
title: 规划 MBAM 2.5 高可用性
description: 规划 MBAM 2.5 高可用性
author: dansimp
ms.assetid: 1e29b30c-33f1-4a52-9442-8c1391f0049c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 20c304f669cfe9e1484be47dea1b9fcc917aea2c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804069"
---
# 规划 MBAM 2.5 高可用性


Microsoft BitLocker 管理和监视（MBAM）可通过使用以下各节中介绍的一种或多种技术来保持高可用性：

-   [SQL Server AlwaysOn 可用性组](#bkmk-alwayson)

-   [Microsoft SQL Server 群集](#bkmk-sql-clustering)

-   [IIS 网络负载平衡](#bkmk-load-balance)

-   [SQL Server 中的数据库镜像](#bkmk-db-mirroring)

-   [使用卷影复制服务（VSS）备份 MBAM 数据库](#bkmk-vss)

使用以下部分中的信息帮助你了解在高可用性配置中部署 MBAM 的选项。

## <a href="" id="bkmk-alwayson"></a>SQL Server AlwaysOn 可用性组的支持


MBAM 使你能够为 Microsoft SQL Server 中的数据库配置和管理可用性组。 MBAM 的可用性组支持故障转移环境，其中合规性和审核数据库和恢复数据库一起进行故障转移，而不是单独进行故障转移。

可用性组支持一组读/写主数据库和一个到四个对应的辅助数据库集。 或者，可以将辅助数据库提供给只读权限、某些备份操作，或者同时提供两者。

有关如何设置可用性组的信息，请参阅[AlwaysOn 可用性组](https://go.microsoft.com/fwlink/?LinkId=393277)。

## <a href="" id="bkmk-sql-clustering"></a>Microsoft SQL Server 群集


你可以在运行 SQL Server 群集的计算机上运行 MBAM 2.5 合规性和审核数据库和恢复数据库。

## <a href="" id="bkmk-load-balance"></a>IIS 网络负载平衡


你可以使用网络负载平衡为运行管理和监视网站（也称为帮助桌面）、自助服务门户和 web 服务（通过 Internet 信息服务（IIS）部署的计算机）配置高可用环境。

### 必备条件

在配置负载平衡之前，请确保满足以下先决条件：

-   负载平衡器必须可用。 你可以使用 Microsoft 或其他公司的负载平衡器。 有关 Microsoft 负载平衡器技术的详细信息，请参阅[使用 IIS 服务器构建 Web 场](https://go.microsoft.com/fwlink/?LinkId=393326)。

-   至少两台服务器运行 IIS，并且满足支持其 web 功能的所有 MBAM 先决条件，包括 ASP.NET MVC 4。

-   MBAM 数据库和报表在服务器上运行。

### <a href="" id="-------------mbam-specific-changes-that-are-required-to-enable-load-balancing"></a> 启用负载平衡所需的 MBAM 特定更改

完成以下任务：

1.  在用于 web 应用程序池的域帐户下注册虚拟主机名的服务主体名称（SPN）。 例如，如果虚拟主机名为 mbamvirtual.contoso.com，并且用于 web 应用程序池的域帐户为 contoso\\mbamapppooluser，则以下命令将相应地注册 SPN。

    `Setspn -s http//mbamvirtual contoso\mbamapppooluser`

    `Setspn -s http//mbamvirtual.contoso.com contoso\mbamapppooluser`

2.  配置以下 MBAM web 功能：

    -   在将托管 MBAM web 功能的每台服务器上，对应用程序池管理凭据使用相同的域帐户。

    -   指定与负载平衡群集的虚拟主机名（DNS 名称）相匹配的主机名。 例如，当你在名为 "NLB1" 的服务器上安装 MBAM 的虚拟主机名为**mbamvirtual.contoso.com**时，请确保你在 Windows PowerShell cmdlet 中指定的主机名**mbamvirtual.contoso.com**。

3.  如果使用负载平衡器配置 web 场中的网站，则必须将网站配置为使用同一计算机密钥。

    有关详细信息，请参阅 MachineKey 元素中的以下各节[（ASP.NET 设置架构）](https://msdn.microsoft.com/library/vstudio/w8h3skw9.aspx)：

    -   计算机密钥解释

    -   Web 场部署注意事项

    有关如何自动生成密钥的说明，请参阅[生成计算机密钥（IIS 7）](https://technet.microsoft.com/library/cc772287.aspx)。

有关负载平衡的信息同样适用于 Windows Server 2012 或 Windows Server2008R2 中的 IIS 网络负载平衡（NLB）群集。 Windows Server 2012 中的 IIS 网络负载平衡功能通常与 Windows Server2008R2 中的功能相同。 但是，某些任务的详细信息在 Windows Server 2012 中是不同的。 有关执行任务的新方法的信息，请参阅[Windows server 2012 R2 预览版和 Windows server 2012 中的常见管理任务和导航](https://go.microsoft.com/fwlink/?LinkId=316371)。

## <a href="" id="bkmk-db-mirroring"></a>SQL Server 中的数据库镜像


MBAM 支持使用 SQL Server 镜像，在这种情况下，将使用每个数据库的两个 SQL Server 实例对合规性和审核数据库和恢复数据库进行镜像。 在实现镜像之前，请注意，镜像会慢慢地引发，如本主题前面所述的可用性组所述。

若要为 MBAM 实现镜像，必须使用**Enable-MbamWebApplication** Windows PowerShell cmdlet 为镜像数据库配置指定相应的连接字符串。 有关 MBAM 2.5 Windows PowerShell cmdlet 的详细信息，请参阅[使用 Windows PowerShell 配置 MBAM 2.5 服务器功能](configuring-mbam-25-server-features-by-using-windows-powershell.md)。

### 使用 Windows PowerShell 实现 SQL Server 镜像的示例

以下示例显示了如何使用 Windows PowerShell cmdlet 实现 SQL Server 镜像。

**示例 1**

``` syntax
Enable-MbamWebApplication -AdministrationPortal -ComplianceAndAuditDBConnectionString 'Integrated Security=SSPI;Data Source=MyDatabaseServer;Failover Partner=myMirrorServerAddress;Initial Catalog="MBAM Compliance Status";' -RecoveryDBConnectionString 'Integrated Security=SSPI;Data Source=MyDatabaseServer;Failover Partner=myMirrorServerAddress;Initial Catalog="MBAM Recovery and Hardware";' -AdvancedHelpdeskAccessGroup “MyDomain\AdvancedUserGroup” -HelpdeskAccessGroup “MyDomain\StandardUserGroup” -ReportsReadOnlyAccessGroup "MyDomain\ReportUserGroup" -ReportUrl "https://MyReportServer/ReportServer" -Port 443 -WebServiceApplicationPoolCredential (Get-Credential) -Certificate (dir cert:\LocalMachine\My\E2A7EA5533890D6567E40DFC46F53B3D31D6B689)
```

**示例 2**

``` syntax
Enable-MbamWebApplication -SelfServicePortal -ComplianceAndAuditDBConnectionString 'Integrated Security=SSPI;Data Source=MyDatabaseServer; Failover Partner=myMirrorServerAddress;Initial Catalog="MBAM Compliance Status";' -RecoveryDBConnectionString 'Integrated Security=SSPI;Data Source=MyDatabaseServer;I Failover Partner=myMirrorServerAddress;Initial Catalog="MBAM Recovery and Hardware";' -Port 443 -WebServiceApplicationPoolCredential (Get-Credential) -Certificate (dir cert:\LocalMachine\My\E2A7EA5533890D6567E40DFC46F53B3D31D6B689)
```

### 有关 SQL Server 镜像的详细信息

以下链接提供了有关配置 SQL Server 镜像的详细信息：

-   [如何：准备镜像数据库以进行镜像（Transact-sql）](https://go.microsoft.com/fwlink/?LinkId=316375)

-   [使用 Windows 身份验证建立数据库镜像会话（SQL Server Management Studio）](https://go.microsoft.com/fwlink/?LinkId=316377)

## <a href="" id="bkmk-vss"></a>使用卷影复制服务（VSS）备份 MBAM 数据库


MBAM 提供了一个卷影复制服务（VSS）编写器，名为 Microsoft BitLocker 管理和管理编写器。 此 VSS 书写器便于备份合规性和审核数据库以及恢复数据库。

VSS 编写器在启用 MBAM web 应用程序的每台服务器上注册。 MBAM VSS 编写器依赖于 SQL Server VSS 书写器，该书写器已注册为 Microsoft SQL Server 安装的一部分。 使用 VSS 编写器执行备份的任何备份技术均可发现 MBAM VSS 书写器。



## 相关主题


[规划部署 MBAM 2.5](planning-to-deploy-mbam-25.md)

 

 
## 已获得 MBAM 的建议？
- 在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。
- 对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。




