---
title: 如何配置 MBAM 2.5 报告
description: 如何配置 MBAM 2.5 报告
author: dansimp
ms.assetid: ec462879-0253-4d9c-83c7-a9bcad479725
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6b372bd6bc38a3729aef43354ecf19b2619b7856
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804004"
---
# <span data-ttu-id="86d62-103">如何配置 MBAM 2.5 报告</span><span class="sxs-lookup"><span data-stu-id="86d62-103">How to Configure the MBAM 2.5 Reports</span></span>


<span data-ttu-id="86d62-104">本主题介绍了如何使用以下内容配置 Microsoft BitLocker 管理和监视（MBAM）2.5 报告功能：</span><span class="sxs-lookup"><span data-stu-id="86d62-104">This topic explains how to configure the Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 Reports feature by using:</span></span>

-   <span data-ttu-id="86d62-105">Windows PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="86d62-105">A Windows PowerShell cmdlet</span></span>

-   <span data-ttu-id="86d62-106">MBAM Server 配置向导</span><span class="sxs-lookup"><span data-stu-id="86d62-106">The MBAM Server Configuration wizard</span></span>

<span data-ttu-id="86d62-107">说明基于[MBAM 2.5 的高级别体系结构](high-level-architecture-for-mbam-25.md)中的推荐体系结构。</span><span class="sxs-lookup"><span data-stu-id="86d62-107">The instructions are based on the recommended architecture in [High-Level Architecture for MBAM 2.5](high-level-architecture-for-mbam-25.md).</span></span>

**<span data-ttu-id="86d62-108">开始配置之前：</span><span class="sxs-lookup"><span data-stu-id="86d62-108">Before you start the configuration:</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="86d62-109">步骤</span><span class="sxs-lookup"><span data-stu-id="86d62-109">Step</span></span></th>
<th align="left"><span data-ttu-id="86d62-110">获取说明的位置</span><span class="sxs-lookup"><span data-stu-id="86d62-110">Where to get instructions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="86d62-111">查看建议的 MBAM 体系结构。</span><span class="sxs-lookup"><span data-stu-id="86d62-111">Review the recommended architecture for MBAM.</span></span></p></td>
<td align="left"><p><a href="high-level-architecture-for-mbam-25.md" data-raw-source="[High-Level Architecture for MBAM 2.5](high-level-architecture-for-mbam-25.md)"><span data-ttu-id="86d62-112">MBAM 2.5 的高级别体系结构</span><span class="sxs-lookup"><span data-stu-id="86d62-112">High-Level Architecture for MBAM 2.5</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="86d62-113">查看 MBAM 支持的配置。</span><span class="sxs-lookup"><span data-stu-id="86d62-113">Review the supported configurations for MBAM.</span></span></p></td>
<td align="left"><p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)"><span data-ttu-id="86d62-114">MBAM 2.5 支持的配置</span><span class="sxs-lookup"><span data-stu-id="86d62-114">MBAM 2.5 Supported Configurations</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="86d62-115">在每台服务器上完成所需的先决条件。</span><span class="sxs-lookup"><span data-stu-id="86d62-115">Complete the required prerequisites on each server.</span></span></p></td>
<td align="left"><ul>
<li><p><a href="mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md" data-raw-source="[MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)"><span data-ttu-id="86d62-116">独立和 Configuration Manager 集成拓扑的 MBAM 2.5 服务器先决条件</span><span class="sxs-lookup"><span data-stu-id="86d62-116">MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies</span></span></a></p></li>
<li><p><a href="mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md" data-raw-source="[MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology](mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md)"><span data-ttu-id="86d62-117">仅适用于 Configuration Manager 集成拓扑 </a> （如果适用）的 MBAM 2.5 服务器必备条件</span><span class="sxs-lookup"><span data-stu-id="86d62-117">MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology</a> (if applicable)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="86d62-118">在计划配置 MBAM 服务器功能的每台服务器上安装 MBAM Server 软件。</span><span class="sxs-lookup"><span data-stu-id="86d62-118">Install the MBAM Server software on each server where you plan to configure an MBAM Server feature.</span></span></p></td>
<td align="left"><p><a href="installing-the-mbam-25-server-software.md" data-raw-source="[Installing the MBAM 2.5 Server Software](installing-the-mbam-25-server-software.md)"><span data-ttu-id="86d62-119">安装 MBAM 2.5 服务器软件</span><span class="sxs-lookup"><span data-stu-id="86d62-119">Installing the MBAM 2.5 Server Software</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="86d62-120">如果计划使用 Windows PowerShell cmdlet 配置 MBAM Server 功能，请查看使用 Windows PowerShell 的先决条件。</span><span class="sxs-lookup"><span data-stu-id="86d62-120">Review the prerequisites for using Windows PowerShell if you plan to use Windows PowerShell cmdlets to configure MBAM Server features.</span></span></p></td>
<td align="left"><p><a href="configuring-mbam-25-server-features-by-using-windows-powershell.md" data-raw-source="[Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md)"><span data-ttu-id="86d62-121">使用 Windows PowerShell 配置 MBAM 2.5 服务器功能</span><span class="sxs-lookup"><span data-stu-id="86d62-121">Configuring MBAM 2.5 Server Features by Using Windows PowerShell</span></span></a></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="86d62-122">使用 Windows PowerShell 配置报表</span><span class="sxs-lookup"><span data-stu-id="86d62-122">To configure the Reports by using Windows PowerShell</span></span>**

1.  <span data-ttu-id="86d62-123">在开始配置之前，请参阅[使用 Windows Powershell 配置 MBAM 2.5 服务器功能](configuring-mbam-25-server-features-by-using-windows-powershell.md)，以查看使用 windows powershell 的先决条件。</span><span class="sxs-lookup"><span data-stu-id="86d62-123">Before you start the configuration, see [Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md) to review the prerequisites for using Windows PowerShell.</span></span>

2.  <span data-ttu-id="86d62-124">使用**Enable-MbamReport** Windows PowerShell Cmdlet 配置报告。</span><span class="sxs-lookup"><span data-stu-id="86d62-124">Use the **Enable-MbamReport** Windows PowerShell cmdlet to configure the Reports.</span></span> <span data-ttu-id="86d62-125">若要获取有关此 Windows PowerShell cmdlet 的信息，请键入**Get-help Enable-MbamReport**。</span><span class="sxs-lookup"><span data-stu-id="86d62-125">To get information about this Windows PowerShell cmdlet, type **Get-Help Enable-MbamReport**.</span></span>

**<span data-ttu-id="86d62-126">使用向导配置报表</span><span class="sxs-lookup"><span data-stu-id="86d62-126">To configure the Reports by using the wizard</span></span>**

1. <span data-ttu-id="86d62-127">在要配置报告的服务器上，启动 " **MBAM 服务器配置**向导"。</span><span class="sxs-lookup"><span data-stu-id="86d62-127">On the server where you want to configure the Reports, start the **MBAM Server Configuration** wizard.</span></span> <span data-ttu-id="86d62-128">可以从 "**开始**" 菜单中选择 " **MBAM 服务器配置**" 以打开该向导。</span><span class="sxs-lookup"><span data-stu-id="86d62-128">You can select **MBAM Server Configuration** from the **Start** menu to open the wizard.</span></span>

2. <span data-ttu-id="86d62-129">单击 "**添加新功能**"，选择 "**报表**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="86d62-129">Click **Add New Features**, select **Reports**, and then click **Next**.</span></span> <span data-ttu-id="86d62-130">向导将检查是否满足报表的所有先决条件。</span><span class="sxs-lookup"><span data-stu-id="86d62-130">The wizard checks that all prerequisites for the Reports have been met.</span></span>

3. <span data-ttu-id="86d62-131">单击**下一步**以继续。</span><span class="sxs-lookup"><span data-stu-id="86d62-131">Click **Next** to continue.</span></span>

4. <span data-ttu-id="86d62-132">使用以下说明，在向导中输入字段值：</span><span class="sxs-lookup"><span data-stu-id="86d62-132">Using the following descriptions, enter the field values in the wizard:</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="86d62-133">字段</span><span class="sxs-lookup"><span data-stu-id="86d62-133">Field</span></span></th>
   <th align="left"><span data-ttu-id="86d62-134">描述</span><span class="sxs-lookup"><span data-stu-id="86d62-134">Description</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="86d62-135">SQL Server Reporting Services 实例</span><span class="sxs-lookup"><span data-stu-id="86d62-135">SQL Server Reporting Services instance</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="86d62-136">将配置报告的 SQL Server Reporting Services 的实例。</span><span class="sxs-lookup"><span data-stu-id="86d62-136">Instance of SQL Server Reporting Services where the Reports will be configured.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="86d62-137">报告角色域组</span><span class="sxs-lookup"><span data-stu-id="86d62-137">Reporting role domain group</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="86d62-138">成员具有在管理和监视服务器上访问报表的权限的域用户组的名称。</span><span class="sxs-lookup"><span data-stu-id="86d62-138">Name of the domain Users group whose members have rights to access the reports on the Administration and Monitoring Server.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="86d62-139">SQL Server 名称</span><span class="sxs-lookup"><span data-stu-id="86d62-139">SQL Server name</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="86d62-140">配置合规性和审核数据库的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="86d62-140">Name of the server where the Compliance and Audit Database is configured.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="86d62-141">SQL Server 数据库实例</span><span class="sxs-lookup"><span data-stu-id="86d62-141">SQL Server database instance</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="86d62-142">在 <em> </em> 其中配置合规性和审核数据库的 SQL Server 实例的名称（例如，MSSQLSERVER）。</span><span class="sxs-lookup"><span data-stu-id="86d62-142">Name of the instance of SQL Server (for example, <em>MSSQLSERVER</em>) where the Compliance and Audit Database is configured.</span></span></p>
   <div class="alert">
   <strong><span data-ttu-id="86d62-143">注意</span><span class="sxs-lookup"><span data-stu-id="86d62-143">Note</span></span></strong><br/><p><span data-ttu-id="86d62-144">必须在报表计算机上添加一个例外，才能在报告服务器的端口上启用入站流量（默认端口为80）。</span><span class="sxs-lookup"><span data-stu-id="86d62-144">You must add an exception on the Reports computer to enable inbound traffic on the port of the Reporting Server (the default port is 80).</span></span></p>
   </div>
   <div>

   </div></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="86d62-145">数据库名称</span><span class="sxs-lookup"><span data-stu-id="86d62-145">Database name</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="86d62-146">合规性和审核数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="86d62-146">Name of the Compliance and Audit Database.</span></span> <span data-ttu-id="86d62-147">默认情况下，数据库名称是 <strong> MBAM 合规性状态 </strong> ，但你可以在配置合规性和审核数据库时更改名称。</span><span class="sxs-lookup"><span data-stu-id="86d62-147">By default, the database name is <strong>MBAM Compliance Status</strong>, although you can change the name when you configure the Compliance and Audit Database.</span></span></p>
   <div class="alert">
   <strong><span data-ttu-id="86d62-148">注意</span><span class="sxs-lookup"><span data-stu-id="86d62-148">Note</span></span></strong><br/><p><span data-ttu-id="86d62-149">如果要从 MBAM 的早期版本升级，则必须使用与以前部署中使用的名称相同的数据库名称。</span><span class="sxs-lookup"><span data-stu-id="86d62-149">If you are upgrading from a previous version of MBAM, you must use the same database name as the name used in your previous deployment.</span></span></p>
   </div>
   <div>

   </div></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="86d62-150">合规性和审核数据库域帐户</span><span class="sxs-lookup"><span data-stu-id="86d62-150">Compliance and Audit Database domain account</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="86d62-151">用于访问合规性和审核数据库的域用户帐户和密码。</span><span class="sxs-lookup"><span data-stu-id="86d62-151">Domain user account and password to access the Compliance and Audit Database.</span></span></p>
   <p><span data-ttu-id="86d62-152">如果您在 <strong> "配置数据库" 页面上的 "只读访问域用户" 或 "组" 字段中输入的值 </strong> <strong> </strong> 是用户，则必须在此字段中输入相同的值。</span><span class="sxs-lookup"><span data-stu-id="86d62-152">If the value you enter in the <strong>Read-only access domain user or group</strong> field on the <strong>Configure Databases</strong> page is a user, you must enter that same value in this field.</span></span></p>
   <p><span data-ttu-id="86d62-153">如果您在 <strong> "配置数据库" 页面上的 "只读访问域用户" 或 "组" 字段中输入的值 </strong> <strong> </strong> 是组，则在此字段中输入的值必须是该组的成员。</span><span class="sxs-lookup"><span data-stu-id="86d62-153">If the value that you enter in the <strong>Read-only access domain user or group</strong> field on the <strong>Configure Databases</strong> page is a group, the value that you enter in this field must be a member of that group.</span></span></p>
   <p><span data-ttu-id="86d62-154">将此帐户的密码配置为永不过期。</span><span class="sxs-lookup"><span data-stu-id="86d62-154">Configure the password for this account to never expire.</span></span> <span data-ttu-id="86d62-155">用户帐户应该能够访问 MBAM Reports Users 组中可用的所有数据。</span><span class="sxs-lookup"><span data-stu-id="86d62-155">The user account should be able to access all data that is available to the MBAM Reports Users group.</span></span></p></td>
   </tr>
   </tbody>
   </table>



5. <span data-ttu-id="86d62-156">完成输入后，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="86d62-156">When you finish your entries, click **Next**.</span></span>

   <span data-ttu-id="86d62-157">该向导将检查是否已满足 "报表" 功能的所有先决条件。</span><span class="sxs-lookup"><span data-stu-id="86d62-157">The wizard checks that all prerequisites for the Reports feature have been met.</span></span>

6. <span data-ttu-id="86d62-158">单击**下一步**以继续。</span><span class="sxs-lookup"><span data-stu-id="86d62-158">Click **Next** to continue.</span></span>

7. <span data-ttu-id="86d62-159">在 "**摘要**" 页面上，查看将添加的功能。</span><span class="sxs-lookup"><span data-stu-id="86d62-159">On the **Summary** page, review the features that will be added.</span></span>

   **<span data-ttu-id="86d62-160">注意</span><span class="sxs-lookup"><span data-stu-id="86d62-160">Note</span></span>**  
   <span data-ttu-id="86d62-161">若要创建刚刚创建的条目的 Windows PowerShell 脚本，请单击 "**导出 PowerShell 脚本**"，然后保存脚本。</span><span class="sxs-lookup"><span data-stu-id="86d62-161">To create a Windows PowerShell script of the entries that you just made, click **Export PowerShell Script**, and then save the script.</span></span>



8. <span data-ttu-id="86d62-162">单击 "**添加**" 以在服务器上添加报表，然后单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="86d62-162">Click **Add** to add the Reports on the server, and then click **Close**.</span></span>



## <span data-ttu-id="86d62-163">相关主题</span><span class="sxs-lookup"><span data-stu-id="86d62-163">Related topics</span></span>


[<span data-ttu-id="86d62-164">服务器事件日志</span><span class="sxs-lookup"><span data-stu-id="86d62-164">Server Event Logs</span></span>](server-event-logs.md)

[<span data-ttu-id="86d62-165">配置 MBAM 2.5 服务器功能</span><span class="sxs-lookup"><span data-stu-id="86d62-165">Configuring the MBAM 2.5 Server Features</span></span>](configuring-the-mbam-25-server-features.md)

[<span data-ttu-id="86d62-166">如何配置 MBAM 2.5 Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="86d62-166">How to Configure the MBAM 2.5 Web Applications</span></span>](how-to-configure-the-mbam-25-web-applications.md)

[<span data-ttu-id="86d62-167">验证 MBAM 2.5 服务器功能配置</span><span class="sxs-lookup"><span data-stu-id="86d62-167">Validating the MBAM 2.5 Server Feature Configuration</span></span>](validating-the-mbam-25-server-feature-configuration.md)


## <span data-ttu-id="86d62-168">已获得 MBAM 的建议？</span><span class="sxs-lookup"><span data-stu-id="86d62-168">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="86d62-169">在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="86d62-169">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="86d62-170">对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="86d62-170">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>






