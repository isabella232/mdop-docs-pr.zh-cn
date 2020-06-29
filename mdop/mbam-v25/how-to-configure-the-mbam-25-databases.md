---
title: 如何配置 MBAM 2.5 数据库
description: 如何配置 MBAM 2.5 数据库
author: dansimp
ms.assetid: 66e1c81b-f785-4398-9175-bb5f112c2a35
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c11cb58d8fd9266bd0322e4cf9aa96256b7fbb6a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804005"
---
# <span data-ttu-id="c904b-103">如何配置 MBAM 2.5 数据库</span><span class="sxs-lookup"><span data-stu-id="c904b-103">How to Configure the MBAM 2.5 Databases</span></span>


<span data-ttu-id="c904b-104">本主题介绍了如何使用以下内容配置 Microsoft BitLocker 管理和监视（MBAM）2.5 合规性和审核数据库和恢复数据库：</span><span class="sxs-lookup"><span data-stu-id="c904b-104">This topic explains how to configure the Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 Compliance and Audit Database and the Recovery Database by using:</span></span>

-   <span data-ttu-id="c904b-105">Windows PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="c904b-105">A Windows PowerShell cmdlet</span></span>

-   <span data-ttu-id="c904b-106">MBAM Server 配置向导</span><span class="sxs-lookup"><span data-stu-id="c904b-106">The MBAM Server Configuration wizard</span></span>

<span data-ttu-id="c904b-107">说明基于[MBAM 2.5 的高级别体系结构](high-level-architecture-for-mbam-25.md)中的推荐体系结构。</span><span class="sxs-lookup"><span data-stu-id="c904b-107">The instructions are based on the recommended architecture in [High-Level Architecture for MBAM 2.5](high-level-architecture-for-mbam-25.md).</span></span>

**<span data-ttu-id="c904b-108">开始配置之前：</span><span class="sxs-lookup"><span data-stu-id="c904b-108">Before you start the configuration:</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="c904b-109">步骤</span><span class="sxs-lookup"><span data-stu-id="c904b-109">Step</span></span></th>
<th align="left"><span data-ttu-id="c904b-110">获取说明的位置</span><span class="sxs-lookup"><span data-stu-id="c904b-110">Where to get instructions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c904b-111">查看建议的 MBAM 体系结构。</span><span class="sxs-lookup"><span data-stu-id="c904b-111">Review the recommended architecture for MBAM.</span></span></p></td>
<td align="left"><p><a href="high-level-architecture-for-mbam-25.md" data-raw-source="[High-Level Architecture for MBAM 2.5](high-level-architecture-for-mbam-25.md)"><span data-ttu-id="c904b-112">MBAM 2.5 的高级别体系结构</span><span class="sxs-lookup"><span data-stu-id="c904b-112">High-Level Architecture for MBAM 2.5</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c904b-113">查看 MBAM 支持的配置。</span><span class="sxs-lookup"><span data-stu-id="c904b-113">Review the supported configurations for MBAM.</span></span></p></td>
<td align="left"><p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)"><span data-ttu-id="c904b-114">MBAM 2.5 支持的配置</span><span class="sxs-lookup"><span data-stu-id="c904b-114">MBAM 2.5 Supported Configurations</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c904b-115">在每台服务器上完成所需的先决条件。</span><span class="sxs-lookup"><span data-stu-id="c904b-115">Complete the required prerequisites on each server.</span></span></p></td>
<td align="left"><ul>
<li><p><a href="mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md" data-raw-source="[MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)"><span data-ttu-id="c904b-116">独立和 Configuration Manager 集成拓扑的 MBAM 2.5 服务器先决条件</span><span class="sxs-lookup"><span data-stu-id="c904b-116">MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies</span></span></a></p></li>
<li><p><a href="mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md" data-raw-source="[MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology](mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md)"><span data-ttu-id="c904b-117">仅适用于 Configuration Manager 集成拓扑 </a> （如果适用）的 MBAM 2.5 服务器必备条件</span><span class="sxs-lookup"><span data-stu-id="c904b-117">MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology</a> (if applicable)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c904b-118">在计划配置 MBAM 服务器功能的每台服务器上安装 MBAM Server 软件。</span><span class="sxs-lookup"><span data-stu-id="c904b-118">Install the MBAM Server software on each server where you plan to configure an MBAM Server feature.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="c904b-119">注意</span><span class="sxs-lookup"><span data-stu-id="c904b-119">Note</span></span></strong><br/><p><span data-ttu-id="c904b-120">你可以使用 Windows PowerShell 或导出的数据层应用程序（DAC）程序包将数据库安装到远程 SQL Server 计算机。</span><span class="sxs-lookup"><span data-stu-id="c904b-120">You can install the databases to a remote SQL Server computer by using Windows PowerShell or an exported data-tier application (DAC) package.</span></span> <span data-ttu-id="c904b-121">有关 DAC 包的详细信息，请参阅 <a href="https://technet.microsoft.com/library/ee210546.aspx" data-raw-source="[Data-tier Applications](https://technet.microsoft.com/library/ee210546.aspx)"> 数据层应用程序 </a> 。</span><span class="sxs-lookup"><span data-stu-id="c904b-121">For more information about DAC packages, see <a href="https://technet.microsoft.com/library/ee210546.aspx" data-raw-source="[Data-tier Applications](https://technet.microsoft.com/library/ee210546.aspx)">Data-tier Applications</a>.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><a href="installing-the-mbam-25-server-software.md" data-raw-source="[Installing the MBAM 2.5 Server Software](installing-the-mbam-25-server-software.md)"><span data-ttu-id="c904b-122">安装 MBAM 2.5 服务器软件</span><span class="sxs-lookup"><span data-stu-id="c904b-122">Installing the MBAM 2.5 Server Software</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c904b-123">如果计划使用 Windows PowerShell cmdlet 配置 MBAM Server 功能，请查看使用 Windows PowerShell 的先决条件。</span><span class="sxs-lookup"><span data-stu-id="c904b-123">Review the prerequisites for using Windows PowerShell if you plan to use Windows PowerShell cmdlets to configure MBAM Server features.</span></span></p></td>
<td align="left"><p><a href="configuring-mbam-25-server-features-by-using-windows-powershell.md" data-raw-source="[Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md)"><span data-ttu-id="c904b-124">使用 Windows PowerShell 配置 MBAM 2.5 服务器功能</span><span class="sxs-lookup"><span data-stu-id="c904b-124">Configuring MBAM 2.5 Server Features by Using Windows PowerShell</span></span></a></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="c904b-125">使用 Windows PowerShell 配置数据库</span><span class="sxs-lookup"><span data-stu-id="c904b-125">To configure the databases by using Windows PowerShell</span></span>**

1.  <span data-ttu-id="c904b-126">在开始配置之前，请参阅[使用 Windows Powershell 配置 MBAM 2.5 服务器功能](configuring-mbam-25-server-features-by-using-windows-powershell.md)，以查看使用 windows powershell 的先决条件。</span><span class="sxs-lookup"><span data-stu-id="c904b-126">Before you start the configuration, see [Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md) to review the prerequisites for using Windows PowerShell.</span></span>

2.  <span data-ttu-id="c904b-127">使用**Enable-MbamDatabase** Windows PowerShell cmdlet 配置数据库。</span><span class="sxs-lookup"><span data-stu-id="c904b-127">Use the **Enable-MbamDatabase** Windows PowerShell cmdlet to configure the databases.</span></span> <span data-ttu-id="c904b-128">若要获取有关此 Windows PowerShell cmdlet 的信息，请键入**Get-help Enable-MbamDatabase**。</span><span class="sxs-lookup"><span data-stu-id="c904b-128">To get information about this Windows PowerShell cmdlet, type **Get-Help Enable-MbamDatabase**.</span></span>

**<span data-ttu-id="c904b-129">使用向导配置合规性和审核数据库</span><span class="sxs-lookup"><span data-stu-id="c904b-129">To configure the Compliance and Audit Database by using the wizard</span></span>**

1. <span data-ttu-id="c904b-130">在要配置数据库的服务器上，启动 " **MBAM 服务器配置**向导"。</span><span class="sxs-lookup"><span data-stu-id="c904b-130">On the server where you want to configure the databases, start the **MBAM Server Configuration** wizard.</span></span> <span data-ttu-id="c904b-131">可以从 "**开始**" 菜单中选择 " **MBAM 服务器配置**" 以打开该向导。</span><span class="sxs-lookup"><span data-stu-id="c904b-131">You can select **MBAM Server Configuration** from the **Start** menu to open the wizard.</span></span>

2. <span data-ttu-id="c904b-132">单击 "**添加新功能**"，选择 "**合规性和审核数据库**和**恢复数据库**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="c904b-132">Click **Add New Features**, select **Compliance and Audit Database** and **Recovery Database**, and then click **Next**.</span></span> <span data-ttu-id="c904b-133">向导将检查数据库的所有先决条件是否已满足。</span><span class="sxs-lookup"><span data-stu-id="c904b-133">The wizard checks that all prerequisites for the databases have been met.</span></span>

3. <span data-ttu-id="c904b-134">如果先决条件检查成功，请单击 "**下一步**" 以继续。</span><span class="sxs-lookup"><span data-stu-id="c904b-134">If the prerequisite check is successful, click **Next** to continue.</span></span> <span data-ttu-id="c904b-135">否则，请解决任何缺少的先决条件，然后**再次单击 "检查必备项**"。</span><span class="sxs-lookup"><span data-stu-id="c904b-135">Otherwise, resolve any missing prerequisites, and then click **Check prerequisites again**.</span></span>

4. <span data-ttu-id="c904b-136">使用以下说明，在向导中输入字段值：</span><span class="sxs-lookup"><span data-stu-id="c904b-136">Using the following descriptions, enter the field values in the wizard:</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="c904b-137">字段</span><span class="sxs-lookup"><span data-stu-id="c904b-137">Field</span></span></th>
   <th align="left"><span data-ttu-id="c904b-138">描述</span><span class="sxs-lookup"><span data-stu-id="c904b-138">Description</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="c904b-139">SQL Server 名称</span><span class="sxs-lookup"><span data-stu-id="c904b-139">SQL Server name</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="c904b-140">在其中配置合规性和审核数据库的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="c904b-140">Name of the server where you are configuring the Compliance and Audit Database.</span></span></p>
   <div class="alert">
   <strong><span data-ttu-id="c904b-141">注意</span><span class="sxs-lookup"><span data-stu-id="c904b-141">Note</span></span></strong><br/><p><span data-ttu-id="c904b-142">必须在合规性和审核数据库计算机上添加异常，才能在 Microsoft SQL Server 端口上启用入站流量。</span><span class="sxs-lookup"><span data-stu-id="c904b-142">You must add an exception on the Compliance and Audit Database computer to enable inbound traffic on the Microsoft SQL Server port.</span></span> <span data-ttu-id="c904b-143">默认端口号为1433。</span><span class="sxs-lookup"><span data-stu-id="c904b-143">The default port number is 1433.</span></span></p>
   </div>
   <div>

   </div></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="c904b-144">SQL Server 数据库实例</span><span class="sxs-lookup"><span data-stu-id="c904b-144">SQL Server database instance</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="c904b-145">将存储合规性和审核数据的数据库实例的名称。</span><span class="sxs-lookup"><span data-stu-id="c904b-145">Name of the database instance where the compliance and audit data will be stored.</span></span> <span data-ttu-id="c904b-146">还必须指定数据库信息的存放位置。</span><span class="sxs-lookup"><span data-stu-id="c904b-146">You must also specify where the database information will be located.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="c904b-147">数据库名称</span><span class="sxs-lookup"><span data-stu-id="c904b-147">Database name</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="c904b-148">将存储合规性数据的数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="c904b-148">Name of the database that will store the compliance data.</span></span></p>
   <div class="alert">
   <strong><span data-ttu-id="c904b-149">注意</span><span class="sxs-lookup"><span data-stu-id="c904b-149">Note</span></span></strong><br/><p><span data-ttu-id="c904b-150">如果要从 MBAM 的早期版本升级，则必须使用与以前部署中使用的名称相同的数据库名称。</span><span class="sxs-lookup"><span data-stu-id="c904b-150">If you are upgrading from a previous version of MBAM, you must use the same database name as the name that was used in your previous deployment.</span></span></p>
   </div>
   <div>

   </div></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="c904b-151">读/写访问域用户或组</span><span class="sxs-lookup"><span data-stu-id="c904b-151">Read/write access domain user or group</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="c904b-152">对此数据库具有读/写权限的域用户或组，以使 web 应用程序能够访问此数据库中的数据和报表。</span><span class="sxs-lookup"><span data-stu-id="c904b-152">Domain user or group that has read/write permission to this database to enable the web applications to access the data and reports in this database.</span></span></p>
   <p><span data-ttu-id="c904b-153">如果在此字段中输入用户，它必须与 <strong> </strong> " <strong> 配置 web 应用程序" 页面上的 "web 服务应用程序池域帐户" 字段中的值相同 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="c904b-153">If you enter a user in this field, it must be the same value as the value in the <strong>Web service application pool domain account</strong> field on the <strong>Configure Web Applications</strong> page.</span></span></p>
   <p><span data-ttu-id="c904b-154">如果在此字段中输入组，则 " <strong> 配置 Web 应用程序" 页面上的 "Web 服务应用程序池域帐户" 字段中的值 </strong> <strong> </strong> 必须是您在此字段中输入的组的成员。</span><span class="sxs-lookup"><span data-stu-id="c904b-154">If you enter a group in this field, the value in the <strong>Web service application pool domain account</strong> field on the <strong>Configure Web Applications</strong> page must be a member of the group you enter in this field.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="c904b-155">只读访问域用户或组</span><span class="sxs-lookup"><span data-stu-id="c904b-155">Read-only access domain user or group</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="c904b-156">将对此数据库具有只读权限的用户或组的名称，以使报表能够访问此数据库中的合规性数据。</span><span class="sxs-lookup"><span data-stu-id="c904b-156">Name of the user or group that will have read-only permission to this database to enable the reports to access the compliance data in this database.</span></span></p>
   <p><span data-ttu-id="c904b-157">如果在此字段中输入用户，则该用户必须与你在 <strong> </strong> "配置报告" 页面上的 "合规性和审核数据库域帐户" 字段中指定的用户相同 <strong> </strong> 。</span><span class="sxs-lookup"><span data-stu-id="c904b-157">If you enter a user in this field, it must be the same user as the one you specify in the <strong>Compliance and Audit Database domain account</strong> field on the <strong>Configure Reports</strong> page.</span></span></p>
   <p><span data-ttu-id="c904b-158">如果在此字段中输入一个组，则在 <strong> "配置报告" 页面上的 "合规性和审核数据库域帐户" 字段中指定的值 </strong> <strong> </strong> 必须是您在此字段中指定的组的成员。</span><span class="sxs-lookup"><span data-stu-id="c904b-158">If you enter a group in this field, the value that you specify in the <strong>Compliance and Audit Database domain account</strong> field on the <strong>Configure Reports</strong> page must be a member of the group that you specify in this field.</span></span></p></td>
   </tr>
   </tbody>
   </table>



5. <span data-ttu-id="c904b-159">转到下一节以配置恢复数据库。</span><span class="sxs-lookup"><span data-stu-id="c904b-159">Continue to the next section to configure the Recovery Database.</span></span>

**<span data-ttu-id="c904b-160">使用向导配置恢复数据库</span><span class="sxs-lookup"><span data-stu-id="c904b-160">To configure the Recovery Database by using the wizard</span></span>**

1. <span data-ttu-id="c904b-161">使用以下说明，在向导中输入字段值：</span><span class="sxs-lookup"><span data-stu-id="c904b-161">Using the following descriptions, enter the field values in the wizard:</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="c904b-162">字段</span><span class="sxs-lookup"><span data-stu-id="c904b-162">Field</span></span></th>
   <th align="left"><span data-ttu-id="c904b-163">描述</span><span class="sxs-lookup"><span data-stu-id="c904b-163">Description</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="c904b-164">SQL Server 名称</span><span class="sxs-lookup"><span data-stu-id="c904b-164">SQL Server name</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="c904b-165">要配置恢复数据库的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="c904b-165">Name of the server where you are configuring the Recovery Database.</span></span></p>
   <div class="alert">
   <strong><span data-ttu-id="c904b-166">注意</span><span class="sxs-lookup"><span data-stu-id="c904b-166">Note</span></span></strong><br/><p><span data-ttu-id="c904b-167">必须在恢复数据库计算机上添加异常，才能在 Microsoft SQL Server 端口上启用入站流量。</span><span class="sxs-lookup"><span data-stu-id="c904b-167">You must add an exception on the Recovery Database computer to enable inbound traffic on the Microsoft SQL Server port.</span></span> <span data-ttu-id="c904b-168">默认端口号为1433。</span><span class="sxs-lookup"><span data-stu-id="c904b-168">The default port number is 1433.</span></span></p>
   </div>
   <div>

   </div></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="c904b-169">SQL Server 数据库实例</span><span class="sxs-lookup"><span data-stu-id="c904b-169">SQL Server database instance</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="c904b-170">将存储恢复数据的数据库实例的名称。</span><span class="sxs-lookup"><span data-stu-id="c904b-170">Name of the database instance where the recovery data will be stored.</span></span> <span data-ttu-id="c904b-171">还必须指定数据库信息的存放位置。</span><span class="sxs-lookup"><span data-stu-id="c904b-171">You must also specify where the database information will be located.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="c904b-172">数据库名称</span><span class="sxs-lookup"><span data-stu-id="c904b-172">Database name</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="c904b-173">将存储恢复数据的数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="c904b-173">Name of the database that will store the recovery data.</span></span></p>
   <div class="alert">
   <strong><span data-ttu-id="c904b-174">注意</span><span class="sxs-lookup"><span data-stu-id="c904b-174">Note</span></span></strong><br/><p><span data-ttu-id="c904b-175">如果要从 MBAM 的早期版本升级，则必须使用与以前部署中使用的名称相同的数据库名称。</span><span class="sxs-lookup"><span data-stu-id="c904b-175">If you are upgrading from a previous version of MBAM, you must use the same database name as the name that was used in your previous deployment.</span></span></p>
   </div>
   <div>

   </div></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="c904b-176">读/写访问域用户或组</span><span class="sxs-lookup"><span data-stu-id="c904b-176">Read/write access domain user or group</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="c904b-177">对此数据库具有读/写权限的域用户或组，以使 web 应用程序能够访问此数据库中的数据和报表。</span><span class="sxs-lookup"><span data-stu-id="c904b-177">Domain user or group that has read/write permission to this database to enable the web applications to access the data and reports in this database.</span></span></p>
   <p><span data-ttu-id="c904b-178">如果在此字段中输入用户，它必须与 <strong> </strong> " <strong> 配置 web 应用程序" 页面上的 "web 服务应用程序池域帐户" 字段中的值相同 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="c904b-178">If you enter a user in this field, it must be the same value as the value in the <strong>Web service application pool domain account</strong> field on the <strong>Configure Web Applications</strong> page.</span></span></p>
   <p><span data-ttu-id="c904b-179">如果在此字段中输入组，则 " <strong> 配置 Web 应用程序" 页面上的 "Web 服务应用程序池域帐户" 字段中的值 </strong> <strong> </strong> 必须是您在此字段中输入的组的成员。</span><span class="sxs-lookup"><span data-stu-id="c904b-179">If you enter a group in this field, the value in the <strong>Web service application pool domain account</strong> field on the <strong>Configure Web Applications</strong> page must be a member of the group you enter in this field.</span></span></p></td>
   </tr>
   </tbody>
   </table>



2. <span data-ttu-id="c904b-180">完成输入后，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="c904b-180">When you finish your entries, click **Next**.</span></span>

   <span data-ttu-id="c904b-181">向导将检查数据库的所有先决条件是否已满足。</span><span class="sxs-lookup"><span data-stu-id="c904b-181">The wizard checks that all prerequisites for the databases have been met.</span></span>

3. <span data-ttu-id="c904b-182">如果先决条件检查成功，请单击 "**下一步**" 以继续。</span><span class="sxs-lookup"><span data-stu-id="c904b-182">If the prerequisite check is successful, click **Next** to continue.</span></span> <span data-ttu-id="c904b-183">否则，请解决任何缺少的先决条件，然后再次单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="c904b-183">Otherwise, resolve any missing prerequisites, and then click **Next** again.</span></span>

4. <span data-ttu-id="c904b-184">在 "**摘要**" 页面上，查看将添加的功能。</span><span class="sxs-lookup"><span data-stu-id="c904b-184">On the **Summary** page, review the features that will be added.</span></span>

   **<span data-ttu-id="c904b-185">注意</span><span class="sxs-lookup"><span data-stu-id="c904b-185">Note</span></span>**  
   <span data-ttu-id="c904b-186">若要创建刚刚创建的条目的 Windows PowerShell 脚本，请单击 "**导出 PowerShell 脚本**"，然后保存脚本。</span><span class="sxs-lookup"><span data-stu-id="c904b-186">To create a Windows PowerShell script of the entries that you just made, click **Export PowerShell Script**, and then save the script.</span></span>



5. <span data-ttu-id="c904b-187">单击 "**添加**" 以在服务器上添加 MBAM 数据库，然后单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="c904b-187">Click **Add** to add the MBAM databases on the server, and then click **Close**.</span></span>



## <span data-ttu-id="c904b-188">相关主题</span><span class="sxs-lookup"><span data-stu-id="c904b-188">Related topics</span></span>


[<span data-ttu-id="c904b-189">服务器事件日志</span><span class="sxs-lookup"><span data-stu-id="c904b-189">Server Event Logs</span></span>](server-event-logs.md)

[<span data-ttu-id="c904b-190">配置 MBAM 2.5 服务器功能</span><span class="sxs-lookup"><span data-stu-id="c904b-190">Configuring the MBAM 2.5 Server Features</span></span>](configuring-the-mbam-25-server-features.md)

[<span data-ttu-id="c904b-191">如何配置 MBAM 2.5 报告</span><span class="sxs-lookup"><span data-stu-id="c904b-191">How to Configure the MBAM 2.5 Reports</span></span>](how-to-configure-the-mbam-25-reports.md)

[<span data-ttu-id="c904b-192">如何配置 MBAM 2.5 Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="c904b-192">How to Configure the MBAM 2.5 Web Applications</span></span>](how-to-configure-the-mbam-25-web-applications.md)

[<span data-ttu-id="c904b-193">验证 MBAM 2.5 服务器功能配置</span><span class="sxs-lookup"><span data-stu-id="c904b-193">Validating the MBAM 2.5 Server Feature Configuration</span></span>](validating-the-mbam-25-server-feature-configuration.md)



## <span data-ttu-id="c904b-194">已获得 MBAM 的建议？</span><span class="sxs-lookup"><span data-stu-id="c904b-194">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="c904b-195">在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="c904b-195">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span>
- <span data-ttu-id="c904b-196">对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="c904b-196">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





