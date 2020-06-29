---
title: 如何使用命令行安装 MBAM 服务器
description: 如何使用命令行安装 MBAM 服务器
author: dansimp
ms.assetid: 6ffc6d41-a793-42c2-b997-95ba47550648
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a689a2df77300300073b2731281004feac87305f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803809"
---
# <span data-ttu-id="0081a-103">如何使用命令行安装 MBAM 服务器</span><span class="sxs-lookup"><span data-stu-id="0081a-103">How to Use a Command Line to Install the MBAM Server</span></span>


<span data-ttu-id="0081a-104">你可以使用命令行使用独立或配置管理器拓扑安装 MBAM 服务器。</span><span class="sxs-lookup"><span data-stu-id="0081a-104">You can use a command line to install the MBAM Server with either the Stand-alone or Configuration Manager topology.</span></span> <span data-ttu-id="0081a-105">下面的命令行示例用于在单个服务器上部署 MBAM，这是一个仅应在测试环境中使用的体系结构。</span><span class="sxs-lookup"><span data-stu-id="0081a-105">The following command line example is for deploying MBAM on a single server, which is an architecture that should be used only in a test environment.</span></span> <span data-ttu-id="0081a-106">将 MBAM 部署到生产环境（应具有多台服务器）时，你需要相应地更改命令行。</span><span class="sxs-lookup"><span data-stu-id="0081a-106">You will need to change the command line accordingly when you deploy MBAM to a production environment, which should have multiple servers.</span></span>

## <span data-ttu-id="0081a-107">使用独立拓扑部署 MBAM 2.0 服务器的命令行</span><span class="sxs-lookup"><span data-stu-id="0081a-107">Command Line for Deploying the MBAM2.0 Server with the Stand-alone Topology</span></span>


<span data-ttu-id="0081a-108">你可以使用与以下内容类似的命令行来安装具有独立拓扑的 MBAM 服务器。</span><span class="sxs-lookup"><span data-stu-id="0081a-108">You can use a command line that is similar to the following to install the MBAM Server with the Stand-alone topology.</span></span>

``` syntax
MbamSetup.exe /qb /l*v MaltaServerInstall.log TOPOLOGY=0 I_ACCEPT_ENDUSER_LICENSE_AGREEMENT=1 ADDLOCAL=KeyDatabase,ReportsDatabase,Reports,AdministrationMonitoringServer,SelfServiceServer,PolicyTemplate,REPORTS_USERACCOUNT=[UserDomain]\[UserName1] REPORTS_USERACCOUNTPW=[UserPwd1] COMPLIDB_SQLINSTANCE=%computername% RECOVERYANDHWDB_SQLINSTANCE=%computername% SRS_INSTANCENAME=%computername% ADMINANDMON_WEBSITE_PORT=83 WEBSITE_PORT=83
```

<span data-ttu-id="0081a-109">下表介绍了用于使用独立拓扑部署 MBAM 服务器的命令行参数。</span><span class="sxs-lookup"><span data-stu-id="0081a-109">The following table describes the command line parameters for deploying the MBAM Server with the Stand-alone topology.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="0081a-110">参数</span><span class="sxs-lookup"><span data-stu-id="0081a-110">Parameter</span></span></th>
<th align="left"><span data-ttu-id="0081a-111">参数值</span><span class="sxs-lookup"><span data-stu-id="0081a-111">Parameter Value</span></span></th>
<th align="left"><span data-ttu-id="0081a-112">描述</span><span class="sxs-lookup"><span data-stu-id="0081a-112">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0081a-113">拓扑</span><span class="sxs-lookup"><span data-stu-id="0081a-113">TOPOLOGY</span></span></p></td>
<td align="left"><p><span data-ttu-id="0081a-114">0</span><span class="sxs-lookup"><span data-stu-id="0081a-114">0</span></span></p></td>
<td align="left"><p><span data-ttu-id="0081a-115">0-独立拓扑</span><span class="sxs-lookup"><span data-stu-id="0081a-115">0 – Stand-alone topology</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0081a-116">I_ACCEPT_ENDUSER_LICENSE_AGREEMENT</span><span class="sxs-lookup"><span data-stu-id="0081a-116">I_ACCEPT_ENDUSER_LICENSE_AGREEMENT</span></span></p></td>
<td align="left"><p><span data-ttu-id="0081a-117">01</span><span class="sxs-lookup"><span data-stu-id="0081a-117">01</span></span></p></td>
<td align="left"><p><span data-ttu-id="0081a-118">0–不接受许可证 agreement1 –接受许可协议</span><span class="sxs-lookup"><span data-stu-id="0081a-118">0 – do not accept the license agreement1 – accept the license agreement</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0081a-119">ADDLOCAL</span><span class="sxs-lookup"><span data-stu-id="0081a-119">ADDLOCAL</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="0081a-120">要在服务器上安装的功能</span><span class="sxs-lookup"><span data-stu-id="0081a-120">Features to be installed on the Server</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="0081a-121">KeyDatabase</span><span class="sxs-lookup"><span data-stu-id="0081a-121">KeyDatabase</span></span></p></td>
<td align="left"><p><span data-ttu-id="0081a-122">恢复数据库</span><span class="sxs-lookup"><span data-stu-id="0081a-122">Recovery Database</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="0081a-123">ReportsDatabase</span><span class="sxs-lookup"><span data-stu-id="0081a-123">ReportsDatabase</span></span></p></td>
<td align="left"><p><span data-ttu-id="0081a-124">合规性和审核报告数据库</span><span class="sxs-lookup"><span data-stu-id="0081a-124">Compliance and Audit Reports Database</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="0081a-125">报告</span><span class="sxs-lookup"><span data-stu-id="0081a-125">Reports</span></span></p></td>
<td align="left"><p><span data-ttu-id="0081a-126">合规性和审核报告</span><span class="sxs-lookup"><span data-stu-id="0081a-126">Compliance and Audit Reports</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="0081a-127">AdministrationMonitoringServer</span><span class="sxs-lookup"><span data-stu-id="0081a-127">AdministrationMonitoringServer</span></span></p></td>
<td align="left"><p><span data-ttu-id="0081a-128">管理和监视网站</span><span class="sxs-lookup"><span data-stu-id="0081a-128">Administration and Monitoring website</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="0081a-129">SelfServiceServer</span><span class="sxs-lookup"><span data-stu-id="0081a-129">SelfServiceServer</span></span></p></td>
<td align="left"><p><span data-ttu-id="0081a-130">自助服务门户</span><span class="sxs-lookup"><span data-stu-id="0081a-130">Self-Service Portal</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="0081a-131">PolicyTemplate</span><span class="sxs-lookup"><span data-stu-id="0081a-131">PolicyTemplate</span></span></p></td>
<td align="left"><p><span data-ttu-id="0081a-132">MBAM 组策略模板</span><span class="sxs-lookup"><span data-stu-id="0081a-132">MBAM Group Policy template</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0081a-133">REPORTS_USERACCOUNT</span><span class="sxs-lookup"><span data-stu-id="0081a-133">REPORTS_USERACCOUNT</span></span></p></td>
<td align="left"><p><span data-ttu-id="0081a-134">[UserDomain][UserName1]</span><span class="sxs-lookup"><span data-stu-id="0081a-134">[UserDomain][UserName1]</span></span></p></td>
<td align="left"><p><span data-ttu-id="0081a-135">将访问合规性和审核数据库的 Reporting Services 服务帐户的域和用户帐户</span><span class="sxs-lookup"><span data-stu-id="0081a-135">Domain and user account of the Reporting Services service account that will access the Compliance and Audit database</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0081a-136">REPORTS_USERACCOUNTPW</span><span class="sxs-lookup"><span data-stu-id="0081a-136">REPORTS_USERACCOUNTPW</span></span></p></td>
<td align="left"><p><span data-ttu-id="0081a-137">[UserPwd1]</span><span class="sxs-lookup"><span data-stu-id="0081a-137">[UserPwd1]</span></span></p></td>
<td align="left"><p><span data-ttu-id="0081a-138">将访问合规性和审核数据库的 Reporting Services 服务帐户的密码</span><span class="sxs-lookup"><span data-stu-id="0081a-138">Password of the Reporting Services service account that will access the Compliance and Audit database</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0081a-139">COMPLIDB_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="0081a-139">COMPLIDB_SQLINSTANCE</span></span></p></td>
<td align="left"><p><span data-ttu-id="0081a-140">名</span><span class="sxs-lookup"><span data-stu-id="0081a-140">%computername%</span></span></p></td>
<td align="left"><p><span data-ttu-id="0081a-141">合规性和审核数据库的 SQL Server 实例名称–将 <strong> % computername% 替换 </strong> 为计算机名称</span><span class="sxs-lookup"><span data-stu-id="0081a-141">SQL Server instance name for the Compliance and Audit Database – replace <strong>%computername%</strong> with the computer name</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0081a-142">RECOVERYANDHWDB_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="0081a-142">RECOVERYANDHWDB_SQLINSTANCE</span></span></p></td>
<td align="left"><p><span data-ttu-id="0081a-143">名</span><span class="sxs-lookup"><span data-stu-id="0081a-143">%computername%</span></span></p></td>
<td align="left"><p><span data-ttu-id="0081a-144">恢复数据库的 SQL Server 实例名称–将 <strong> % computername% 替换 </strong> 为计算机名称</span><span class="sxs-lookup"><span data-stu-id="0081a-144">SQL Server instance name for the Recovery Database – replace <strong>%computername%</strong> with the computer name</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0081a-145">SRS_INSTANCENAME</span><span class="sxs-lookup"><span data-stu-id="0081a-145">SRS_INSTANCENAME</span></span></p></td>
<td align="left"><p><span data-ttu-id="0081a-146">名</span><span class="sxs-lookup"><span data-stu-id="0081a-146">%computername%</span></span></p></td>
<td align="left"><p><span data-ttu-id="0081a-147">将安装合规性和审核报告的 SQL Server Reporting Server 实例–将 <strong> % computername% 替换 </strong> 为计算机名称</span><span class="sxs-lookup"><span data-stu-id="0081a-147">SQL Server Reporting Server instance where the Compliance and Audit reports will be installed – replace <strong>%computername%</strong> with the computer name</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0081a-148">ADMINANDMON_WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="0081a-148">ADMINANDMON_WEBSITE_PORT</span></span></p></td>
<td align="left"><p><span data-ttu-id="0081a-149">83</span><span class="sxs-lookup"><span data-stu-id="0081a-149">83</span></span></p></td>
<td align="left"><p><span data-ttu-id="0081a-150">管理和监视网站的端口;"83" 只是一个示例</span><span class="sxs-lookup"><span data-stu-id="0081a-150">Port for the Administration and Monitoring website; “83” is only an example</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0081a-151">WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="0081a-151">WEBSITE_PORT</span></span></p></td>
<td align="left"><p><span data-ttu-id="0081a-152">83</span><span class="sxs-lookup"><span data-stu-id="0081a-152">83</span></span></p></td>
<td align="left"><p><span data-ttu-id="0081a-153">自助服务门户网站的端口;"83" 只是一个示例</span><span class="sxs-lookup"><span data-stu-id="0081a-153">Port for the Self-Service Portal website; “83” is only an example</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="0081a-154">用于通过 Configuration Manager 拓扑部署 MBAM 2.0 服务器的命令行</span><span class="sxs-lookup"><span data-stu-id="0081a-154">Command Line for Deploying the MBAM2.0 Server with the Configuration Manager Topology</span></span>


<span data-ttu-id="0081a-155">你可以使用与以下内容类似的命令行来使用 Configuration Manager 拓扑安装 MBAM 服务器。</span><span class="sxs-lookup"><span data-stu-id="0081a-155">You can use a command line that is similar to the following to install the MBAM Server with the Configuration Manager topology.</span></span>

``` syntax
MbamSetup.exe /qn /l*v MaltaServerInstall.log I_ACCEPT_ENDUSER_LICENSE_AGREEMENT=1 TOPOLOGY=1 COMPLIDB_SQLINSTANCE=%computername% RECOVERYANDHWDB_SQLINSTANCE=%computername% SRS_INSTANCENAME=%computername% REPORTS_USERACCOUNT=[UserDomain]\[UserName] REPORTS_USERACCOUNTPW=[UserPwd] ADMINANDMON_WEBSITE_PORT=83 WEBSITE_PORT=83
```

<span data-ttu-id="0081a-156">下表介绍了用于通过 Configuration Manager 拓扑安装 MBAM 2.0 服务器的命令行参数。</span><span class="sxs-lookup"><span data-stu-id="0081a-156">The following table describes the command line parameters for installing the MBAM2.0 Server with the Configuration Manager topology.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="0081a-157">参数</span><span class="sxs-lookup"><span data-stu-id="0081a-157">Parameter</span></span></th>
<th align="left"><span data-ttu-id="0081a-158">参数值</span><span class="sxs-lookup"><span data-stu-id="0081a-158">Parameter Value</span></span></th>
<th align="left"><span data-ttu-id="0081a-159">描述</span><span class="sxs-lookup"><span data-stu-id="0081a-159">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0081a-160">拓扑</span><span class="sxs-lookup"><span data-stu-id="0081a-160">TOPOLOGY</span></span></p></td>
<td align="left"><p><span data-ttu-id="0081a-161">raid-1</span><span class="sxs-lookup"><span data-stu-id="0081a-161">1</span></span></p></td>
<td align="left"><p><span data-ttu-id="0081a-162">1-配置管理器拓扑</span><span class="sxs-lookup"><span data-stu-id="0081a-162">1 – Configuration Manager topology</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0081a-163">I_ACCEPT_ENDUSER_LICENSE_AGREEMENT</span><span class="sxs-lookup"><span data-stu-id="0081a-163">I_ACCEPT_ENDUSER_LICENSE_AGREEMENT</span></span></p></td>
<td align="left"><p><span data-ttu-id="0081a-164">01</span><span class="sxs-lookup"><span data-stu-id="0081a-164">01</span></span></p></td>
<td align="left"><p><span data-ttu-id="0081a-165">0–不接受许可证 agreement1 –接受许可协议</span><span class="sxs-lookup"><span data-stu-id="0081a-165">0 – do not accept the license agreement1 – accept the license agreement</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0081a-166">COMPLIDB_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="0081a-166">COMPLIDB_SQLINSTANCE</span></span></p></td>
<td align="left"><p><span data-ttu-id="0081a-167">名</span><span class="sxs-lookup"><span data-stu-id="0081a-167">%computername%</span></span></p></td>
<td align="left"><p><span data-ttu-id="0081a-168">审核数据库的 SQL Server 实例名称–将 <strong> % computername% 替换 </strong> 为计算机名称</span><span class="sxs-lookup"><span data-stu-id="0081a-168">SQL Server instance name for the Audit Database – replace <strong>%computername%</strong> with the computer name</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0081a-169">RECOVERYANDHWDB_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="0081a-169">RECOVERYANDHWDB_SQLINSTANCE</span></span></p></td>
<td align="left"><p><span data-ttu-id="0081a-170">名</span><span class="sxs-lookup"><span data-stu-id="0081a-170">%computername%</span></span></p></td>
<td align="left"><p><span data-ttu-id="0081a-171">恢复数据库的 SQL Server 实例名称-将 <strong> % computername% 替换为 </strong> 计算机名称</span><span class="sxs-lookup"><span data-stu-id="0081a-171">SQL Server instance name for the Recovery Database - replace <strong>%computername%</strong> with the computer name</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0081a-172">SRS_INSTANCENAME</span><span class="sxs-lookup"><span data-stu-id="0081a-172">SRS_INSTANCENAME</span></span></p></td>
<td align="left"><p><span data-ttu-id="0081a-173">名</span><span class="sxs-lookup"><span data-stu-id="0081a-173">%computername%</span></span></p></td>
<td align="left"><p><span data-ttu-id="0081a-174">将安装审核报告的 SQL Server Reporting Server 实例–将% computername% 替换为计算机名称</span><span class="sxs-lookup"><span data-stu-id="0081a-174">SQL Server Reporting Server instance where the Audit reports will be installed – replace %computername% with the computer name</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0081a-175">REPORTS_USERACCOUNT</span><span class="sxs-lookup"><span data-stu-id="0081a-175">REPORTS_USERACCOUNT</span></span></p></td>
<td align="left"><p><span data-ttu-id="0081a-176">[UserDomain][UserName1]</span><span class="sxs-lookup"><span data-stu-id="0081a-176">[UserDomain][UserName1]</span></span></p></td>
<td align="left"><p><span data-ttu-id="0081a-177">将访问合规性和审核数据库的 Reporting Services 服务帐户的域和用户帐户</span><span class="sxs-lookup"><span data-stu-id="0081a-177">Domain and user account of the Reporting Services service account that will access the Compliance and Audit database</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0081a-178">REPORTS_USERACCOUNTPW</span><span class="sxs-lookup"><span data-stu-id="0081a-178">REPORTS_USERACCOUNTPW</span></span></p></td>
<td align="left"><p><span data-ttu-id="0081a-179">[UserPwd1]</span><span class="sxs-lookup"><span data-stu-id="0081a-179">[UserPwd1]</span></span></p></td>
<td align="left"><p><span data-ttu-id="0081a-180">将访问合规性和审核数据库的 Reporting Services 服务帐户的密码</span><span class="sxs-lookup"><span data-stu-id="0081a-180">Password of the Reporting Services service account that will access the Compliance and Audit database</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0081a-181">ADMINANDMON_WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="0081a-181">ADMINANDMON_WEBSITE_PORT</span></span></p></td>
<td align="left"><p><span data-ttu-id="0081a-182">83</span><span class="sxs-lookup"><span data-stu-id="0081a-182">83</span></span></p></td>
<td align="left"><p><span data-ttu-id="0081a-183">管理和监视网站的端口;"83" 只是一个示例</span><span class="sxs-lookup"><span data-stu-id="0081a-183">Port for the Administration and Monitoring website; “83” is only an example</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0081a-184">WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="0081a-184">WEBSITE_PORT</span></span></p></td>
<td align="left"><p><span data-ttu-id="0081a-185">83</span><span class="sxs-lookup"><span data-stu-id="0081a-185">83</span></span></p></td>
<td align="left"><p><span data-ttu-id="0081a-186">自助服务门户网站的端口;"83" 只是一个示例</span><span class="sxs-lookup"><span data-stu-id="0081a-186">Port for the Self-Service Portal website; “83” is only an example</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="0081a-187">相关主题</span><span class="sxs-lookup"><span data-stu-id="0081a-187">Related topics</span></span>


[<span data-ttu-id="0081a-188">部署 MBAM 2.0 服务器基础结构</span><span class="sxs-lookup"><span data-stu-id="0081a-188">Deploying the MBAM 2.0 Server Infrastructure</span></span>](deploying-the-mbam-20-server-infrastructure-mbam-2.md)

 

 





