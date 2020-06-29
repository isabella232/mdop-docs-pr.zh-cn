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
# <span data-ttu-id="abbc4-103">规划 MBAM 2.5 高可用性</span><span class="sxs-lookup"><span data-stu-id="abbc4-103">Planning for MBAM 2.5 High Availability</span></span>


<span data-ttu-id="abbc4-104">Microsoft BitLocker 管理和监视（MBAM）可通过使用以下各节中介绍的一种或多种技术来保持高可用性：</span><span class="sxs-lookup"><span data-stu-id="abbc4-104">Microsoft BitLocker Administration and Monitoring (MBAM) can maintain high availability through use of one or more of the following technologies, which are described in the following sections:</span></span>

-   [<span data-ttu-id="abbc4-105">SQL Server AlwaysOn 可用性组</span><span class="sxs-lookup"><span data-stu-id="abbc4-105">SQL Server AlwaysOn availability groups</span></span>](#bkmk-alwayson)

-   [<span data-ttu-id="abbc4-106">Microsoft SQL Server 群集</span><span class="sxs-lookup"><span data-stu-id="abbc4-106">Microsoft SQL Server clustering</span></span>](#bkmk-sql-clustering)

-   [<span data-ttu-id="abbc4-107">IIS 网络负载平衡</span><span class="sxs-lookup"><span data-stu-id="abbc4-107">IIS Network Load Balancing</span></span>](#bkmk-load-balance)

-   [<span data-ttu-id="abbc4-108">SQL Server 中的数据库镜像</span><span class="sxs-lookup"><span data-stu-id="abbc4-108">Database mirroring in SQL Server</span></span>](#bkmk-db-mirroring)

-   [<span data-ttu-id="abbc4-109">使用卷影复制服务（VSS）备份 MBAM 数据库</span><span class="sxs-lookup"><span data-stu-id="abbc4-109">Backing up MBAM databases by using the Volume Shadow Copy Service (VSS)</span></span>](#bkmk-vss)

<span data-ttu-id="abbc4-110">使用以下部分中的信息帮助你了解在高可用性配置中部署 MBAM 的选项。</span><span class="sxs-lookup"><span data-stu-id="abbc4-110">Use the information in the following sections to help you understand the options to deploy MBAM in a highly available configuration.</span></span>

## <a href="" id="bkmk-alwayson"></a><span data-ttu-id="abbc4-111">SQL Server AlwaysOn 可用性组的支持</span><span class="sxs-lookup"><span data-stu-id="abbc4-111">Support for SQL Server AlwaysOn availability groups</span></span>


<span data-ttu-id="abbc4-112">MBAM 使你能够为 Microsoft SQL Server 中的数据库配置和管理可用性组。</span><span class="sxs-lookup"><span data-stu-id="abbc4-112">MBAM enables you to configure and manage availability groups for the databases in Microsoft SQL Server.</span></span> <span data-ttu-id="abbc4-113">MBAM 的可用性组支持故障转移环境，其中合规性和审核数据库和恢复数据库一起进行故障转移，而不是单独进行故障转移。</span><span class="sxs-lookup"><span data-stu-id="abbc4-113">An availability group for MBAM supports a failover environment where the Compliance and Audit Database and the Recovery Database fail over together rather than separately.</span></span>

<span data-ttu-id="abbc4-114">可用性组支持一组读/写主数据库和一个到四个对应的辅助数据库集。</span><span class="sxs-lookup"><span data-stu-id="abbc4-114">An availability group supports a set of read/write primary databases and one to four sets of corresponding secondary databases.</span></span> <span data-ttu-id="abbc4-115">或者，可以将辅助数据库提供给只读权限、某些备份操作，或者同时提供两者。</span><span class="sxs-lookup"><span data-stu-id="abbc4-115">Optionally, secondary databases can be made available for read-only permission, some backup operations, or for both.</span></span>

<span data-ttu-id="abbc4-116">有关如何设置可用性组的信息，请参阅[AlwaysOn 可用性组](https://go.microsoft.com/fwlink/?LinkId=393277)。</span><span class="sxs-lookup"><span data-stu-id="abbc4-116">For information about how to set up availability groups, see [AlwaysOn Availability Groups](https://go.microsoft.com/fwlink/?LinkId=393277).</span></span>

## <a href="" id="bkmk-sql-clustering"></a><span data-ttu-id="abbc4-117">Microsoft SQL Server 群集</span><span class="sxs-lookup"><span data-stu-id="abbc4-117">Microsoft SQL Server clustering</span></span>


<span data-ttu-id="abbc4-118">你可以在运行 SQL Server 群集的计算机上运行 MBAM 2.5 合规性和审核数据库和恢复数据库。</span><span class="sxs-lookup"><span data-stu-id="abbc4-118">You can run the MBAM 2.5 Compliance and Audit Database and the Recovery Database on computers that are running SQL Server clusters.</span></span>

## <a href="" id="bkmk-load-balance"></a><span data-ttu-id="abbc4-119">IIS 网络负载平衡</span><span class="sxs-lookup"><span data-stu-id="abbc4-119">IIS Network Load Balancing</span></span>


<span data-ttu-id="abbc4-120">你可以使用网络负载平衡为运行管理和监视网站（也称为帮助桌面）、自助服务门户和 web 服务（通过 Internet 信息服务（IIS）部署的计算机）配置高可用环境。</span><span class="sxs-lookup"><span data-stu-id="abbc4-120">You can use Network Load Balancing to configure a highly available environment for computers that are running the Administration and Monitoring Website (also known as Help Desk), the Self-Service Portal, and the web services, which are deployed through Internet Information Services (IIS).</span></span>

### <span data-ttu-id="abbc4-121">必备条件</span><span class="sxs-lookup"><span data-stu-id="abbc4-121">Prerequisites</span></span>

<span data-ttu-id="abbc4-122">在配置负载平衡之前，请确保满足以下先决条件：</span><span class="sxs-lookup"><span data-stu-id="abbc4-122">Before configuring load balancing, ensure that you have met the following prerequisites:</span></span>

-   <span data-ttu-id="abbc4-123">负载平衡器必须可用。</span><span class="sxs-lookup"><span data-stu-id="abbc4-123">A load balancer must be available.</span></span> <span data-ttu-id="abbc4-124">你可以使用 Microsoft 或其他公司的负载平衡器。</span><span class="sxs-lookup"><span data-stu-id="abbc4-124">You can use load balancers from Microsoft or another company.</span></span> <span data-ttu-id="abbc4-125">有关 Microsoft 负载平衡器技术的详细信息，请参阅[使用 IIS 服务器构建 Web 场](https://go.microsoft.com/fwlink/?LinkId=393326)。</span><span class="sxs-lookup"><span data-stu-id="abbc4-125">For more information about Microsoft load balancer technology, see [Build a Web Farm with IIS Servers](https://go.microsoft.com/fwlink/?LinkId=393326).</span></span>

-   <span data-ttu-id="abbc4-126">至少两台服务器运行 IIS，并且满足支持其 web 功能的所有 MBAM 先决条件，包括 ASP.NET MVC 4。</span><span class="sxs-lookup"><span data-stu-id="abbc4-126">At least two servers are running IIS and have met all of the MBAM prerequisites to support its web features, including ASP.NET MVC 4.</span></span>

-   <span data-ttu-id="abbc4-127">MBAM 数据库和报表在服务器上运行。</span><span class="sxs-lookup"><span data-stu-id="abbc4-127">MBAM databases and reports are running on a server.</span></span>

### <a href="" id="-------------mbam-specific-changes-that-are-required-to-enable-load-balancing"></a> <span data-ttu-id="abbc4-128">启用负载平衡所需的 MBAM 特定更改</span><span class="sxs-lookup"><span data-stu-id="abbc4-128">MBAM-specific changes that are required to enable Load Balancing</span></span>

<span data-ttu-id="abbc4-129">完成以下任务：</span><span class="sxs-lookup"><span data-stu-id="abbc4-129">Complete the following tasks:</span></span>

1.  <span data-ttu-id="abbc4-130">在用于 web 应用程序池的域帐户下注册虚拟主机名的服务主体名称（SPN）。</span><span class="sxs-lookup"><span data-stu-id="abbc4-130">Register a Service Principal Name (SPN) for the virtual host name under the domain account that you are using for the web application pools.</span></span> <span data-ttu-id="abbc4-131">例如，如果虚拟主机名为 mbamvirtual.contoso.com，并且用于 web 应用程序池的域帐户为 contoso\\mbamapppooluser，则以下命令将相应地注册 SPN。</span><span class="sxs-lookup"><span data-stu-id="abbc4-131">For example, if the virtual host name is mbamvirtual.contoso.com, and the domain account used for the web application pools is contoso\\mbamapppooluser, the following command registers the SPN appropriately.</span></span>

    `Setspn -s http//mbamvirtual contoso\mbamapppooluser`

    `Setspn -s http//mbamvirtual.contoso.com contoso\mbamapppooluser`

2.  <span data-ttu-id="abbc4-132">配置以下 MBAM web 功能：</span><span class="sxs-lookup"><span data-stu-id="abbc4-132">Configure the following MBAM web features:</span></span>

    -   <span data-ttu-id="abbc4-133">在将托管 MBAM web 功能的每台服务器上，对应用程序池管理凭据使用相同的域帐户。</span><span class="sxs-lookup"><span data-stu-id="abbc4-133">On each server that will host the MBAM web features, use the same domain account for the application pool administrative credentials.</span></span>

    -   <span data-ttu-id="abbc4-134">指定与负载平衡群集的虚拟主机名（DNS 名称）相匹配的主机名。</span><span class="sxs-lookup"><span data-stu-id="abbc4-134">Specify a host name that matches the virtual host name (DNS name) of the Load Balancing cluster.</span></span> <span data-ttu-id="abbc4-135">例如，当你在名为 "NLB1" 的服务器上安装 MBAM 的虚拟主机名为**mbamvirtual.contoso.com**时，请确保你在 Windows PowerShell cmdlet 中指定的主机名**mbamvirtual.contoso.com**。</span><span class="sxs-lookup"><span data-stu-id="abbc4-135">For example, when you install MBAM on a server called "NLB1" with a virtual host name of **mbamvirtual.contoso.com**, ensure that the host name that you specify in the Windows PowerShell cmdlet is **mbamvirtual.contoso.com**.</span></span>

3.  <span data-ttu-id="abbc4-136">如果使用负载平衡器配置 web 场中的网站，则必须将网站配置为使用同一计算机密钥。</span><span class="sxs-lookup"><span data-stu-id="abbc4-136">If you are configuring the websites in a web farm with a load balancer, you must configure the websites to use the same machine key.</span></span>

    <span data-ttu-id="abbc4-137">有关详细信息，请参阅 MachineKey 元素中的以下各节[（ASP.NET 设置架构）](https://msdn.microsoft.com/library/vstudio/w8h3skw9.aspx)：</span><span class="sxs-lookup"><span data-stu-id="abbc4-137">For more information, see the following sections in [machineKey Element (ASP.NET Settings Schema)](https://msdn.microsoft.com/library/vstudio/w8h3skw9.aspx):</span></span>

    -   <span data-ttu-id="abbc4-138">计算机密钥解释</span><span class="sxs-lookup"><span data-stu-id="abbc4-138">Machine Key Explained</span></span>

    -   <span data-ttu-id="abbc4-139">Web 场部署注意事项</span><span class="sxs-lookup"><span data-stu-id="abbc4-139">Web Farm Deployment Considerations</span></span>

    <span data-ttu-id="abbc4-140">有关如何自动生成密钥的说明，请参阅[生成计算机密钥（IIS 7）](https://technet.microsoft.com/library/cc772287.aspx)。</span><span class="sxs-lookup"><span data-stu-id="abbc4-140">For instructions about how to automatically generate a key, see [Generate a Machine Key (IIS 7)](https://technet.microsoft.com/library/cc772287.aspx).</span></span>

<span data-ttu-id="abbc4-141">有关负载平衡的信息同样适用于 Windows Server 2012 或 Windows Server2008R2 中的 IIS 网络负载平衡（NLB）群集。</span><span class="sxs-lookup"><span data-stu-id="abbc4-141">The information about Load Balancing also applies to IIS Network Load Balancing (NLB) clusters in Windows Server 2012 or Windows Server2008R2.</span></span> <span data-ttu-id="abbc4-142">Windows Server 2012 中的 IIS 网络负载平衡功能通常与 Windows Server2008R2 中的功能相同。</span><span class="sxs-lookup"><span data-stu-id="abbc4-142">The IIS Network Load Balancing functionality in Windows Server 2012 is generally the same as in Windows Server2008R2.</span></span> <span data-ttu-id="abbc4-143">但是，某些任务的详细信息在 Windows Server 2012 中是不同的。</span><span class="sxs-lookup"><span data-stu-id="abbc4-143">However, some task details are different in Windows Server 2012.</span></span> <span data-ttu-id="abbc4-144">有关执行任务的新方法的信息，请参阅[Windows server 2012 R2 预览版和 Windows server 2012 中的常见管理任务和导航](https://go.microsoft.com/fwlink/?LinkId=316371)。</span><span class="sxs-lookup"><span data-stu-id="abbc4-144">For information about new ways to do tasks, see [Common Management Tasks and Navigation in Windows Server 2012 R2 Preview and Windows Server 2012](https://go.microsoft.com/fwlink/?LinkId=316371).</span></span>

## <a href="" id="bkmk-db-mirroring"></a><span data-ttu-id="abbc4-145">SQL Server 中的数据库镜像</span><span class="sxs-lookup"><span data-stu-id="abbc4-145">Database mirroring in SQL Server</span></span>


<span data-ttu-id="abbc4-146">MBAM 支持使用 SQL Server 镜像，在这种情况下，将使用每个数据库的两个 SQL Server 实例对合规性和审核数据库和恢复数据库进行镜像。</span><span class="sxs-lookup"><span data-stu-id="abbc4-146">MBAM supports the use of SQL Server mirroring, where the Compliance and Audit Database and the Recovery Database are mirrored by using two instances of SQL Server for each database.</span></span> <span data-ttu-id="abbc4-147">在实现镜像之前，请注意，镜像会慢慢地引发，如本主题前面所述的可用性组所述。</span><span class="sxs-lookup"><span data-stu-id="abbc4-147">Before implementing mirroring, be aware that mirroring is slowly being phased out, in favor of availability groups, which are discussed earlier in this topic.</span></span>

<span data-ttu-id="abbc4-148">若要为 MBAM 实现镜像，必须使用**Enable-MbamWebApplication** Windows PowerShell cmdlet 为镜像数据库配置指定相应的连接字符串。</span><span class="sxs-lookup"><span data-stu-id="abbc4-148">To implement mirroring for MBAM, you must specify the appropriate connection strings for the mirrored database configuration by using the **Enable-MbamWebApplication** Windows PowerShell cmdlet.</span></span> <span data-ttu-id="abbc4-149">有关 MBAM 2.5 Windows PowerShell cmdlet 的详细信息，请参阅[使用 Windows PowerShell 配置 MBAM 2.5 服务器功能](configuring-mbam-25-server-features-by-using-windows-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="abbc4-149">For more information about the MBAM 2.5 Windows PowerShell cmdlets, see [Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md).</span></span>

### <span data-ttu-id="abbc4-150">使用 Windows PowerShell 实现 SQL Server 镜像的示例</span><span class="sxs-lookup"><span data-stu-id="abbc4-150">Examples of implementing SQL Server mirroring by using Windows PowerShell</span></span>

<span data-ttu-id="abbc4-151">以下示例显示了如何使用 Windows PowerShell cmdlet 实现 SQL Server 镜像。</span><span class="sxs-lookup"><span data-stu-id="abbc4-151">The following examples show how you might implement SQL Server mirroring by using Windows PowerShell cmdlets.</span></span>

**<span data-ttu-id="abbc4-152">示例 1</span><span class="sxs-lookup"><span data-stu-id="abbc4-152">Example 1</span></span>**

``` syntax
Enable-MbamWebApplication -AdministrationPortal -ComplianceAndAuditDBConnectionString 'Integrated Security=SSPI;Data Source=MyDatabaseServer;Failover Partner=myMirrorServerAddress;Initial Catalog="MBAM Compliance Status";' -RecoveryDBConnectionString 'Integrated Security=SSPI;Data Source=MyDatabaseServer;Failover Partner=myMirrorServerAddress;Initial Catalog="MBAM Recovery and Hardware";' -AdvancedHelpdeskAccessGroup “MyDomain\AdvancedUserGroup” -HelpdeskAccessGroup “MyDomain\StandardUserGroup” -ReportsReadOnlyAccessGroup "MyDomain\ReportUserGroup" -ReportUrl "https://MyReportServer/ReportServer" -Port 443 -WebServiceApplicationPoolCredential (Get-Credential) -Certificate (dir cert:\LocalMachine\My\E2A7EA5533890D6567E40DFC46F53B3D31D6B689)
```

**<span data-ttu-id="abbc4-153">示例 2</span><span class="sxs-lookup"><span data-stu-id="abbc4-153">Example 2</span></span>**

``` syntax
Enable-MbamWebApplication -SelfServicePortal -ComplianceAndAuditDBConnectionString 'Integrated Security=SSPI;Data Source=MyDatabaseServer; Failover Partner=myMirrorServerAddress;Initial Catalog="MBAM Compliance Status";' -RecoveryDBConnectionString 'Integrated Security=SSPI;Data Source=MyDatabaseServer;I Failover Partner=myMirrorServerAddress;Initial Catalog="MBAM Recovery and Hardware";' -Port 443 -WebServiceApplicationPoolCredential (Get-Credential) -Certificate (dir cert:\LocalMachine\My\E2A7EA5533890D6567E40DFC46F53B3D31D6B689)
```

### <span data-ttu-id="abbc4-154">有关 SQL Server 镜像的详细信息</span><span class="sxs-lookup"><span data-stu-id="abbc4-154">More information about SQL Server mirroring</span></span>

<span data-ttu-id="abbc4-155">以下链接提供了有关配置 SQL Server 镜像的详细信息：</span><span class="sxs-lookup"><span data-stu-id="abbc4-155">The following links provide more information about configuring SQL Server mirroring:</span></span>

-   [<span data-ttu-id="abbc4-156">如何：准备镜像数据库以进行镜像（Transact-sql）</span><span class="sxs-lookup"><span data-stu-id="abbc4-156">How to: Prepare a Mirror Database for Mirroring (Transact-SQL)</span></span>](https://go.microsoft.com/fwlink/?LinkId=316375)

-   [<span data-ttu-id="abbc4-157">使用 Windows 身份验证建立数据库镜像会话（SQL Server Management Studio）</span><span class="sxs-lookup"><span data-stu-id="abbc4-157">Establish a Database Mirroring Session Using Windows Authentication (SQL Server Management Studio)</span></span>](https://go.microsoft.com/fwlink/?LinkId=316377)

## <a href="" id="bkmk-vss"></a><span data-ttu-id="abbc4-158">使用卷影复制服务（VSS）备份 MBAM 数据库</span><span class="sxs-lookup"><span data-stu-id="abbc4-158">Backing up MBAM databases by using the Volume Shadow Copy Service (VSS)</span></span>


<span data-ttu-id="abbc4-159">MBAM 提供了一个卷影复制服务（VSS）编写器，名为 Microsoft BitLocker 管理和管理编写器。</span><span class="sxs-lookup"><span data-stu-id="abbc4-159">MBAM provides a Volume Shadow Copy Service (VSS) writer, called the Microsoft BitLocker Administration and Management Writer.</span></span> <span data-ttu-id="abbc4-160">此 VSS 书写器便于备份合规性和审核数据库以及恢复数据库。</span><span class="sxs-lookup"><span data-stu-id="abbc4-160">This VSS writer facilitates the backup of the Compliance and Audit Database and the Recovery Database.</span></span>

<span data-ttu-id="abbc4-161">VSS 编写器在启用 MBAM web 应用程序的每台服务器上注册。</span><span class="sxs-lookup"><span data-stu-id="abbc4-161">The VSS writer is registered on every server where you enable an MBAM web application.</span></span> <span data-ttu-id="abbc4-162">MBAM VSS 编写器依赖于 SQL Server VSS 书写器，该书写器已注册为 Microsoft SQL Server 安装的一部分。</span><span class="sxs-lookup"><span data-stu-id="abbc4-162">The MBAM VSS writer depends on the SQL Server VSS Writer, which is registered as part of the Microsoft SQL Server installation.</span></span> <span data-ttu-id="abbc4-163">使用 VSS 编写器执行备份的任何备份技术均可发现 MBAM VSS 书写器。</span><span class="sxs-lookup"><span data-stu-id="abbc4-163">Any backup technology that uses VSS writers to perform backup can discover the MBAM VSS writer.</span></span>



## <span data-ttu-id="abbc4-164">相关主题</span><span class="sxs-lookup"><span data-stu-id="abbc4-164">Related topics</span></span>


[<span data-ttu-id="abbc4-165">规划部署 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="abbc4-165">Planning to Deploy MBAM 2.5</span></span>](planning-to-deploy-mbam-25.md)

 

 
## <span data-ttu-id="abbc4-166">已获得 MBAM 的建议？</span><span class="sxs-lookup"><span data-stu-id="abbc4-166">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="abbc4-167">在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="abbc4-167">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span>
- <span data-ttu-id="abbc4-168">对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="abbc4-168">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>




