---
title: 在独立配置中部署 MBAM 2.5
description: 介绍如何以独立的配置部署 MBAM 2.5。
author: Deland-Han
ms.reviewer: dcscontentpm
manager: dansimp
ms.author: delhan
ms.sitesec: library
ms.prod: w10
ms.date: 09/16/2019
ms.openlocfilehash: 905eb7a40483a7a7b499d6dced8472331c87b838
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803967"
---
# <span data-ttu-id="94cf4-103">在独立配置中部署 MBAM 2。5</span><span class="sxs-lookup"><span data-stu-id="94cf4-103">Deploying MBAM 2.5 in a standalone configuration</span></span>

<span data-ttu-id="94cf4-104">本文提供了在独立配置中安装 Microsoft BitLocker 管理和监视（MBAM）2.5 的分步说明。</span><span class="sxs-lookup"><span data-stu-id="94cf4-104">This article provides step-by-step instructions for installing Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 in a standalone configuration.</span></span> <span data-ttu-id="94cf4-105">在本指南中，我们将使用两个服务器的配置。</span><span class="sxs-lookup"><span data-stu-id="94cf4-105">In this guide we will use a two-server configuration.</span></span> <span data-ttu-id="94cf4-106">这两个服务器之一将是运行 Microsoft SQL Server 2012 的数据库服务器。</span><span class="sxs-lookup"><span data-stu-id="94cf4-106">One of the two servers will be a database server running Microsoft SQL Server 2012.</span></span> <span data-ttu-id="94cf4-107">此服务器将托管 MBAM 数据库和报告。</span><span class="sxs-lookup"><span data-stu-id="94cf4-107">This server will host the MBAM databases and reports.</span></span> <span data-ttu-id="94cf4-108">其他服务器将是 Windows Server 2012 web 服务器托管的 "管理和监视服务器" 和 "自助服务门户"。</span><span class="sxs-lookup"><span data-stu-id="94cf4-108">The additional server will be a Windows Server 2012 web server hosting "Administration and Monitoring Server" and "Self-Service Portal."</span></span>

## <span data-ttu-id="94cf4-109">安装 MBAM 2.5 server 软件之前的准备步骤</span><span class="sxs-lookup"><span data-stu-id="94cf4-109">Preparation steps before installing MBAM 2.5 server software</span></span>

### <span data-ttu-id="94cf4-110">步骤1：服务器的安装和配置</span><span class="sxs-lookup"><span data-stu-id="94cf4-110">Step 1: Installation and configuration of servers</span></span>

<span data-ttu-id="94cf4-111">在开始配置 MBAM 2.5 之前，我们必须确保两台服务器都按 MBAM 的系统要求进行配置。</span><span class="sxs-lookup"><span data-stu-id="94cf4-111">Before we start configuring MBAM 2.5, we have to make sure that both servers are configured as per MBAM system requirements.</span></span> <span data-ttu-id="94cf4-112">请参阅[MBAM 最低系统要求](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/mbam-25-supported-configurations#-mbam-server-system-requirements)，并选择满足这些要求的配置。</span><span class="sxs-lookup"><span data-stu-id="94cf4-112">See the [MBAM minimum system requirements](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/mbam-25-supported-configurations#-mbam-server-system-requirements), and select a configuration that meets these requirements.</span></span> 

#### <span data-ttu-id="94cf4-113">步骤1.1：部署数据库和报告服务器的先决条件</span><span class="sxs-lookup"><span data-stu-id="94cf4-113">Step 1.1: Deploying prerequisites for database and reporting server</span></span>

1. <span data-ttu-id="94cf4-114">安装和配置运行 Windows Server 2008 R2 （或更高版本）操作系统的服务器。</span><span class="sxs-lookup"><span data-stu-id="94cf4-114">Install and configure a server running Windows Server 2008 R2 (or later) operating system.</span></span>

2. <span data-ttu-id="94cf4-115">安装 Windows PowerShell 3.0。</span><span class="sxs-lookup"><span data-stu-id="94cf4-115">Install Windows PowerShell 3.0.</span></span>

3. <span data-ttu-id="94cf4-116">安装 Microsoft SQL Server 2008 R2 或包含最新服务包的更高版本。</span><span class="sxs-lookup"><span data-stu-id="94cf4-116">Install Microsoft SQL Server 2008 R2 or a later version that includes the latest service pack.</span></span> <span data-ttu-id="94cf4-117">如果你要为 MBAM 安装新的 SQL Server 实例，请确保你安装的 SQL Server 包含 SQL_Latin1_General_CP1_CI_AS 的排序规则。</span><span class="sxs-lookup"><span data-stu-id="94cf4-117">If you are installing a new instance of SQL Server for MBAM, make sure the SQL Server you install includes the SQL_Latin1_General_CP1_CI_AS collation.</span></span> <span data-ttu-id="94cf4-118">必须安装以下 SQL Server 功能：</span><span class="sxs-lookup"><span data-stu-id="94cf4-118">You’ll have to install the following SQL Server features:</span></span>

    * <span data-ttu-id="94cf4-119">数据库引擎</span><span class="sxs-lookup"><span data-stu-id="94cf4-119">Database Engine</span></span>
    * <span data-ttu-id="94cf4-120">Reporting Services</span><span class="sxs-lookup"><span data-stu-id="94cf4-120">Reporting Services</span></span>
    * <span data-ttu-id="94cf4-121">客户端工具连接</span><span class="sxs-lookup"><span data-stu-id="94cf4-121">Client Tools Connectivity</span></span>
    * <span data-ttu-id="94cf4-122">管理工具-完成</span><span class="sxs-lookup"><span data-stu-id="94cf4-122">Management Tools – Complete</span></span>

    > [!Note]
    > <span data-ttu-id="94cf4-123">或者，也可以[在 SQL Server 中安装透明数据加密（TDE）功能](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/mbam-25-security-considerations)。</span><span class="sxs-lookup"><span data-stu-id="94cf4-123">Optionally, you can also install the [Transparent Data Encryption (TDE) feature in SQL Server](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/mbam-25-security-considerations).</span></span>

    <span data-ttu-id="94cf4-124">SQL Server Reporting Services 必须在 "本机" 模式下安装和配置，而不是在未配置或 "SharePoint" 模式下进行配置。</span><span class="sxs-lookup"><span data-stu-id="94cf4-124">SQL Server Reporting Services must be installed and configured in "native" mode and not in unconfigured or "SharePoint" mode.</span></span>

    ![所需的 SQL Server 功能](images/deploying-MBAM-1.png)

4. <span data-ttu-id="94cf4-126">如果你计划对管理和监视网站使用 SSL，请确保先将 SQL Server Reporting Services （SSRS）配置为使用安全套接字层（SSL）协议，然后再配置管理和监视网站。</span><span class="sxs-lookup"><span data-stu-id="94cf4-126">If you plan to use SSL for the Administration and Monitoring website, make sure that you configure SQL Server Reporting Services (SSRS) to use the Secure Sockets Layer (SSL) protocol before you configure the Administration and Monitoring website.</span></span> <span data-ttu-id="94cf4-127">否则，"报表" 功能将使用未加密（HTTP）数据传输，而不是加密（HTTPS）。</span><span class="sxs-lookup"><span data-stu-id="94cf4-127">Otherwise, the Reports feature will use unencrypted (HTTP) data transport instead of encrypted (HTTPS).</span></span>

    <span data-ttu-id="94cf4-128">你可以关注在本机模式报表服务器上[配置 Ssl 连接](https://docs.microsoft.com/sql/reporting-services/security/configure-ssl-connections-on-a-native-mode-report-server?view=sql-server-2017)以在报表服务器上配置 ssl。</span><span class="sxs-lookup"><span data-stu-id="94cf4-128">You can follow [Configure SSL Connections](https://docs.microsoft.com/sql/reporting-services/security/configure-ssl-connections-on-a-native-mode-report-server?view=sql-server-2017) on a Native Mode Report Server to configure SSL on Report Server.</span></span>
    
    > [!Note]
    > <span data-ttu-id="94cf4-129">你可以按照 sql server 各自版本的 SQL Server 安装指南安装 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="94cf4-129">You can follow the SQL Server Installation Guide for your respective version of SQL Server to install SQL Server.</span></span> <span data-ttu-id="94cf4-130">这些链接如下所示：</span><span class="sxs-lookup"><span data-stu-id="94cf4-130">The links are as follows:</span></span>
        > * [<span data-ttu-id="94cf4-131">SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="94cf4-131">SQL Server 2014</span></span>](https://docs.microsoft.com/sql/sql-server/install/planning-a-sql-server-installation?view=sql-server-2014)
        > * [<span data-ttu-id="94cf4-132">SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="94cf4-132">SQL Server 2012</span></span>](https://docs.microsoft.com/previous-versions/sql/sql-server-2012/bb500442(v=sql.110))
        > * [<span data-ttu-id="94cf4-133">SQL Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="94cf4-133">SQL Server 2008 R2</span></span>](https://docs.microsoft.com/previous-versions/sql/sql-server-2012/bb500442(v=sql.110))

5. <span data-ttu-id="94cf4-134">在 SQL Server 的安装后，请确保在 SQL Server 中预配用户帐户，并向将在数据库服务器上配置 MBAM 数据库和报告角色的用户分配以下权限。</span><span class="sxs-lookup"><span data-stu-id="94cf4-134">In the post-installation of SQL Server, make sure that you provision the user account in SQL Server, and assign the following permissions to the user who will configure the MBAM database and reporting roles on the database server.</span></span>

    <span data-ttu-id="94cf4-135">SQL Server 实例的角色：</span><span class="sxs-lookup"><span data-stu-id="94cf4-135">Roles for the instance of SQL Server:</span></span>
        
    * <span data-ttu-id="94cf4-136">dbcreator</span><span class="sxs-lookup"><span data-stu-id="94cf4-136">dbcreator</span></span>
    * <span data-ttu-id="94cf4-137">processadmin</span><span class="sxs-lookup"><span data-stu-id="94cf4-137">processadmin</span></span>

    <span data-ttu-id="94cf4-138">SQL Server Reporting Services 实例的权限：</span><span class="sxs-lookup"><span data-stu-id="94cf4-138">Rights for the instance of SQL Server Reporting Services:</span></span>
    
    * <span data-ttu-id="94cf4-139">创建文件夹</span><span class="sxs-lookup"><span data-stu-id="94cf4-139">Create Folders</span></span>
    * <span data-ttu-id="94cf4-140">发布报表</span><span class="sxs-lookup"><span data-stu-id="94cf4-140">Publish Reports</span></span>

<span data-ttu-id="94cf4-141">您的数据库服务器已准备好配置 MBAM 2.5 角色。</span><span class="sxs-lookup"><span data-stu-id="94cf4-141">Your database server is ready for configuration of MBAM 2.5 roles.</span></span> <span data-ttu-id="94cf4-142">让我们移到下一台服务器。</span><span class="sxs-lookup"><span data-stu-id="94cf4-142">Let’s move to the next server.</span></span>

#### <span data-ttu-id="94cf4-143">步骤1.2：部署管理和监视服务器的先决条件</span><span class="sxs-lookup"><span data-stu-id="94cf4-143">Step 1.2: Deploying prerequisites for administration and monitoring server</span></span>

<span data-ttu-id="94cf4-144">选择满足[MBAM 系统要求文档](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/mbam-25-supported-configurations#-mbam-server-system-requirements)中所述硬件配置的服务器。</span><span class="sxs-lookup"><span data-stu-id="94cf4-144">Choose a server that meets the hardware configuration as explained in the [MBAM system requirements document](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/mbam-25-supported-configurations#-mbam-server-system-requirements).</span></span> <span data-ttu-id="94cf4-145">它必须运行 Windows Server 2008 R2 或更高版本的操作系统以及最新的 service pack 和更新。</span><span class="sxs-lookup"><span data-stu-id="94cf4-145">It must be running Windows Server 2008 R2 or a later operating system together with latest service pack and updates.</span></span> <span data-ttu-id="94cf4-146">在服务器准备就绪后，安装以下角色和功能：</span><span class="sxs-lookup"><span data-stu-id="94cf4-146">After the server is ready, install the following roles and features:</span></span>

##### <span data-ttu-id="94cf4-147">角色</span><span class="sxs-lookup"><span data-stu-id="94cf4-147">Roles</span></span>

* <span data-ttu-id="94cf4-148">Web 服务器（IIS）管理工具（选择 "IIS 管理脚本和工具"。）</span><span class="sxs-lookup"><span data-stu-id="94cf4-148">Web Server (IIS) Management Tools (Select IIS Management Scripts and Tools.)</span></span>

* <span data-ttu-id="94cf4-149">Web 服务器角色服务</span><span class="sxs-lookup"><span data-stu-id="94cf4-149">Web Server Role Services</span></span>

    * <span data-ttu-id="94cf4-150">常用 HTTP 功能</span><span class="sxs-lookup"><span data-stu-id="94cf4-150">Common HTTP features</span></span><br />
      <span data-ttu-id="94cf4-151">静态内容</span><span class="sxs-lookup"><span data-stu-id="94cf4-151">Static Content</span></span><br />
      <span data-ttu-id="94cf4-152">默认文档</span><span class="sxs-lookup"><span data-stu-id="94cf4-152">Default Document</span></span>

    * <span data-ttu-id="94cf4-153">应用程序开发</span><span class="sxs-lookup"><span data-stu-id="94cf4-153">Application development</span></span><br />
      <span data-ttu-id="94cf4-154">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="94cf4-154">ASP.NET</span></span><br />
      <span data-ttu-id="94cf4-155">.NET 扩展性</span><span class="sxs-lookup"><span data-stu-id="94cf4-155">.NET Extensibility</span></span><br />
      <span data-ttu-id="94cf4-156">ISAPI 扩展</span><span class="sxs-lookup"><span data-stu-id="94cf4-156">ISAPI Extensions</span></span><br />
      <span data-ttu-id="94cf4-157">ISAPI 筛选器</span><span class="sxs-lookup"><span data-stu-id="94cf4-157">ISAPI Filters</span></span><br />
      <span data-ttu-id="94cf4-158">安全性</span><span class="sxs-lookup"><span data-stu-id="94cf4-158">Security</span></span><br />
      <span data-ttu-id="94cf4-159">Windows 身份验证</span><span class="sxs-lookup"><span data-stu-id="94cf4-159">Windows Authentication</span></span><br />
      <span data-ttu-id="94cf4-160">请求筛选</span><span class="sxs-lookup"><span data-stu-id="94cf4-160">Request Filtering</span></span>

    * <span data-ttu-id="94cf4-161">Web 服务 IIS 管理工具</span><span class="sxs-lookup"><span data-stu-id="94cf4-161">Web Service IIS Management Tools</span></span>

##### <span data-ttu-id="94cf4-162">功能</span><span class="sxs-lookup"><span data-stu-id="94cf4-162">Feature</span></span>

* <span data-ttu-id="94cf4-163">.NET Framework 4.5 功能</span><span class="sxs-lookup"><span data-stu-id="94cf4-163">.NET Framework 4.5 features</span></span>
  
  * <span data-ttu-id="94cf4-164">Microsoft .NET Framework 4。5</span><span class="sxs-lookup"><span data-stu-id="94cf4-164">Microsoft .NET Framework 4.5</span></span>
  
    <span data-ttu-id="94cf4-165">对于 Windows server 2012 或 Windows Server 2012 R2，已为这些版本的 Windows Server 安装了 .NET Framework 4.5。</span><span class="sxs-lookup"><span data-stu-id="94cf4-165">For Windows Server 2012 or Windows Server 2012 R2, .NET Framework 4.5 is already installed for these versions of Windows Server.</span></span> <span data-ttu-id="94cf4-166">但是，您必须启用它。</span><span class="sxs-lookup"><span data-stu-id="94cf4-166">However, you must enable it.</span></span>
  
    <span data-ttu-id="94cf4-167">对于 Windows server 2008 R2，Windows Server 2008 R2 中不包含 .NET Framework 4.5。</span><span class="sxs-lookup"><span data-stu-id="94cf4-167">For Windows Server 2008 R2, .NET Framework 4.5 is not included with Windows Server 2008 R2.</span></span> <span data-ttu-id="94cf4-168">因此，你必须下载 .NET Framework 4.5 并单独安装它。</span><span class="sxs-lookup"><span data-stu-id="94cf4-168">So, you must download .NET Framework 4.5 and install it separately.</span></span>
  
  * <span data-ttu-id="94cf4-169">WCF 激活</span><span class="sxs-lookup"><span data-stu-id="94cf4-169">WCF Activation</span></span><br />
    <span data-ttu-id="94cf4-170">HTTP 激活</span><span class="sxs-lookup"><span data-stu-id="94cf4-170">HTTP Activation</span></span><br />
    <span data-ttu-id="94cf4-171">非 HTTP 激活</span><span class="sxs-lookup"><span data-stu-id="94cf4-171">Non-HTTP Activation</span></span>
  
  * <span data-ttu-id="94cf4-172">TCP 激活</span><span class="sxs-lookup"><span data-stu-id="94cf4-172">TCP Activation</span></span>
  
  * <span data-ttu-id="94cf4-173">Windows 进程激活服务：</span><span class="sxs-lookup"><span data-stu-id="94cf4-173">Windows Process Activation Service:</span></span><br />
    <span data-ttu-id="94cf4-174">流程模型</span><span class="sxs-lookup"><span data-stu-id="94cf4-174">Process Model</span></span><br />
    <span data-ttu-id="94cf4-175">.NET Framework 环境</span><span class="sxs-lookup"><span data-stu-id="94cf4-175">.NET Framework Environment</span></span><br />
    <span data-ttu-id="94cf4-176">配置 Api</span><span class="sxs-lookup"><span data-stu-id="94cf4-176">Configuration APIs</span></span>

<span data-ttu-id="94cf4-177">若要使用自助服务门户，还应[下载并安装 ASP.NET MVC 4.0](https://go.microsoft.com/fwlink/?linkid=392271)。</span><span class="sxs-lookup"><span data-stu-id="94cf4-177">For the self-service portal to work, you should also [download and install ASP.NET MVC 4.0](https://go.microsoft.com/fwlink/?linkid=392271).</span></span>

<span data-ttu-id="94cf4-178">下一步是在 Active Directory 中创建所需的 MBAM 用户和组。</span><span class="sxs-lookup"><span data-stu-id="94cf4-178">The next step is to create the required MBAM users and groups in Active Directory.</span></span>

### <span data-ttu-id="94cf4-179">步骤2：在 Active Directory 域服务中创建用户和组</span><span class="sxs-lookup"><span data-stu-id="94cf4-179">Step 2: Creating users and groups in Active Directory Domain Services</span></span>
 
<span data-ttu-id="94cf4-180">作为先决条件的一部分，你必须定义在 MBAM 中使用的某些角色和帐户，以便为特定服务器和功能提供安全和访问权限，例如在 SQL Server 实例上运行的数据库和在管理和监视服务器上运行的 web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="94cf4-180">As part of the prerequisites, you must define certain roles and accounts that are used in MBAM to provide security and access rights to specific servers and features, such as the databases that are running on the instance of SQL Server and the web applications that are running on the Administration and Monitoring Server.</span></span>

<span data-ttu-id="94cf4-181">在 Active Directory 中创建以下组和用户。</span><span class="sxs-lookup"><span data-stu-id="94cf4-181">Create the following groups and users in Active Directory.</span></span> <span data-ttu-id="94cf4-182">（您可以为组和用户使用任何名称。）用户不必拥有更多的用户权限。</span><span class="sxs-lookup"><span data-stu-id="94cf4-182">(You can use any name for the groups and users.) Users do not have to have greater user rights.</span></span> <span data-ttu-id="94cf4-183">域用户帐户已足够。</span><span class="sxs-lookup"><span data-stu-id="94cf4-183">A domain user account is sufficient.</span></span> <span data-ttu-id="94cf4-184">在 MBAM 2.5 的配置期间，你必须指定这些组的名称：</span><span class="sxs-lookup"><span data-stu-id="94cf4-184">You’ll have to specify the name of these groups during configuration of MBAM 2.5:</span></span>

* **<span data-ttu-id="94cf4-185">MBAMAppPool</span><span class="sxs-lookup"><span data-stu-id="94cf4-185">MBAMAppPool</span></span>**  

  <span data-ttu-id="94cf4-186">**类型**：域用户</span><span class="sxs-lookup"><span data-stu-id="94cf4-186">**Type**: Domain User</span></span>

  <span data-ttu-id="94cf4-187">**说明**：对合规性和审核数据库和恢复数据库具有读取或写入权限的域用户，使 web 应用程序能够访问这些数据库中的数据和报告。</span><span class="sxs-lookup"><span data-stu-id="94cf4-187">**Description**: Domain user who has Read or Write permission to the Compliance and Audit Database and the Recovery Database to enable the web applications to access the data and reports in these databases.</span></span> <span data-ttu-id="94cf4-188">它还将由 web 应用程序的应用程序池使用。</span><span class="sxs-lookup"><span data-stu-id="94cf4-188">It will also be used by the application pool for the web applications.</span></span>

  <span data-ttu-id="94cf4-189">**帐户角色（在 MBAM 配置期间）**：</span><span class="sxs-lookup"><span data-stu-id="94cf4-189">**Account Roles (During Configuration of MBAM)**:</span></span>

  1. <span data-ttu-id="94cf4-190">Web 服务应用程序池域帐户</span><span class="sxs-lookup"><span data-stu-id="94cf4-190">Web service application pool domain account</span></span>

  2. <span data-ttu-id="94cf4-191">合规性和审核数据库和恢复数据库对报表的读/写用户</span><span class="sxs-lookup"><span data-stu-id="94cf4-191">Compliance and Audit Database and Recovery Database read/write user for reports</span></span>

* **<span data-ttu-id="94cf4-192">MBAMROUser</span><span class="sxs-lookup"><span data-stu-id="94cf4-192">MBAMROUser</span></span>**

  <span data-ttu-id="94cf4-193">**类型**：域用户</span><span class="sxs-lookup"><span data-stu-id="94cf4-193">**Type**: Domain User</span></span>

  <span data-ttu-id="94cf4-194">**说明**：将对合规性和审核数据库具有只读访问权限的域用户，以使报表能够访问此数据库中的合规性和审核数据。</span><span class="sxs-lookup"><span data-stu-id="94cf4-194">**Description**: Domain user who will have Read-Only access to the Compliance and Audit Database to enable the reports to access the compliance and audit data in this database.</span></span> <span data-ttu-id="94cf4-195">它还将是本地 SQL Server Reporting Services 实例用于访问合规性和审核数据库的域用户帐户。</span><span class="sxs-lookup"><span data-stu-id="94cf4-195">It will also be the domain user account that the local SQL Server Reporting Services instance uses to access the Compliance and Audit Database.</span></span>

  <span data-ttu-id="94cf4-196">**帐户角色（在 MBAM 配置期间）**：</span><span class="sxs-lookup"><span data-stu-id="94cf4-196">**Account Roles (During Configuration of MBAM)**:</span></span>

  1. <span data-ttu-id="94cf4-197">针对报表的合规性和审核数据库只读用户</span><span class="sxs-lookup"><span data-stu-id="94cf4-197">Compliance and Audit Database read-only user for reports</span></span>

  2. <span data-ttu-id="94cf4-198">合规性和审核数据库域用户帐户</span><span class="sxs-lookup"><span data-stu-id="94cf4-198">Compliance and Audit Database domain user account</span></span>

* **<span data-ttu-id="94cf4-199">MBAMAdvHelpDsk</span><span class="sxs-lookup"><span data-stu-id="94cf4-199">MBAMAdvHelpDsk</span></span>**

  <span data-ttu-id="94cf4-200">**类型**：域组</span><span class="sxs-lookup"><span data-stu-id="94cf4-200">**Type**: Domain Group</span></span>

  <span data-ttu-id="94cf4-201">**说明**： MBAM 高级帮助台用户访问组：其成员有权访问管理和监视网站的所有区域的域用户组。</span><span class="sxs-lookup"><span data-stu-id="94cf4-201">**Description**: MBAM Advanced Helpdesk Users access group: Domain user group whose members have access to all areas of the Administration and Monitoring Website.</span></span> <span data-ttu-id="94cf4-202">具有此角色的用户在帮助用户恢复其驱动器时，只需输入恢复密钥，而不是用户的域和用户名。</span><span class="sxs-lookup"><span data-stu-id="94cf4-202">Users who have this role have to enter only the recovery key, not the user’s domain and user name, when they are helping users recover their drives.</span></span> <span data-ttu-id="94cf4-203">如果用户是 MBAM 支持人员组和 MBAM 高级帮助台用户组的成员，则 MBAM 高级帮助台用户组权限将替代 MBAM 帮助台组权限。</span><span class="sxs-lookup"><span data-stu-id="94cf4-203">If a user is a member of both the MBAM Helpdesk Users group and the MBAM Advanced Helpdesk Users group, the MBAM Advanced Helpdesk Users group permissions override the MBAM Helpdesk Group permissions.</span></span>

  <span data-ttu-id="94cf4-204">**帐户角色（在 MBAM 配置期间）**： MBAM 高级帮助台用户</span><span class="sxs-lookup"><span data-stu-id="94cf4-204">**Account Roles (During Configuration of MBAM)**: MBAM Advanced Helpdesk Users</span></span>

* **<span data-ttu-id="94cf4-205">MBAMHelpDsk</span><span class="sxs-lookup"><span data-stu-id="94cf4-205">MBAMHelpDsk</span></span>**

  <span data-ttu-id="94cf4-206">**类型**：域组</span><span class="sxs-lookup"><span data-stu-id="94cf4-206">**Type**: Domain Group</span></span>

  <span data-ttu-id="94cf4-207">**说明**： MBAM 帮助台用户访问组：其成员有权访问 MBAM 管理和监视网站的 "管理 TPM" 和 "驱动器恢复" 区域的域用户组。</span><span class="sxs-lookup"><span data-stu-id="94cf4-207">**Description**: MBAM Helpdesk Users access group: Domain user group whose members have access to the Manage TPM and Drive Recovery areas of the MBAM Administration and Monitoring Website.</span></span> <span data-ttu-id="94cf4-208">具有此角色的人员在使用任一选项时都必须填写所有字段。</span><span class="sxs-lookup"><span data-stu-id="94cf4-208">People who have this role must fill in all fields when they use either option.</span></span> <span data-ttu-id="94cf4-209">这包括用户的域和帐户名称。</span><span class="sxs-lookup"><span data-stu-id="94cf4-209">This includes the user’s domain and account name.</span></span>

  <span data-ttu-id="94cf4-210">**帐户角色（在 MBAM 配置期间）**： MBAM 帮助台用户</span><span class="sxs-lookup"><span data-stu-id="94cf4-210">**Account Roles (During Configuration of MBAM)**: MBAM Helpdesk Users</span></span>

* **<span data-ttu-id="94cf4-211">MBAMRUGrp</span><span class="sxs-lookup"><span data-stu-id="94cf4-211">MBAMRUGrp</span></span>**

  <span data-ttu-id="94cf4-212">**类型**：域组</span><span class="sxs-lookup"><span data-stu-id="94cf4-212">**Type**: Domain Group</span></span>

  <span data-ttu-id="94cf4-213">**说明**：其成员对管理和监控网站的 "报告" 区域中的报表具有只读访问权限的域用户组。</span><span class="sxs-lookup"><span data-stu-id="94cf4-213">**Description**: Domain user group whose members have read-only access to the reports in the Reports area of the Administration and Monitoring Website.</span></span>

  <span data-ttu-id="94cf4-214">**帐户角色（在 MBAM 配置期间）**：</span><span class="sxs-lookup"><span data-stu-id="94cf4-214">**Account Roles (During Configuration of MBAM)**:</span></span>

  1. <span data-ttu-id="94cf4-215">报告只读域访问组</span><span class="sxs-lookup"><span data-stu-id="94cf4-215">Reports read-only domain access group</span></span>

  2. <span data-ttu-id="94cf4-216">MBAM 报表用户访问组</span><span class="sxs-lookup"><span data-stu-id="94cf4-216">MBAM Report Users access group</span></span>

### <span data-ttu-id="94cf4-217">步骤3（可选）：在管理和监视服务器上配置并安装 SSL 证书</span><span class="sxs-lookup"><span data-stu-id="94cf4-217">Step 3 (Optional): Configure and install SSL certificate on administration and monitoring server</span></span>

<span data-ttu-id="94cf4-218">尽管它是可选的，但我们强烈建议你使用证书来帮助保护 MBAM 客户端和管理和监视网站以及自助服务门户网站之间的通信。</span><span class="sxs-lookup"><span data-stu-id="94cf4-218">Although it’s optional, we highly recommend that you use a certificate to help secure the communication between the MBAM Client and the Administration and Monitoring Website and the Self-Service Portal websites.</span></span> <span data-ttu-id="94cf4-219">我们不建议使用自签名证书，因为这是显而易见的安全理由。</span><span class="sxs-lookup"><span data-stu-id="94cf4-219">We do not recommend that you use self-signed certificates because of obvious security reasons.</span></span> <span data-ttu-id="94cf4-220">我们建议你使用来自受信任的证书颁发机构的 Web 服务器类型证书。</span><span class="sxs-lookup"><span data-stu-id="94cf4-220">We suggest that you use a Web Server Type Certificate from a trusted Certification Authority.</span></span> <span data-ttu-id="94cf4-221">若要执行此操作，您可以参考[知识库 2754259](https://support.microsoft.com/help/2754259)中的 "使用证书颁发机构批准的证书" 部分。</span><span class="sxs-lookup"><span data-stu-id="94cf4-221">To do this, you can refer the "Using Certificate Approved by Certificate Authority" section from [KB 2754259](https://support.microsoft.com/help/2754259).</span></span>

<span data-ttu-id="94cf4-222">颁发证书后，应将证书添加到管理和监视服务器的个人存储区。</span><span class="sxs-lookup"><span data-stu-id="94cf4-222">After the certificate is issued, you should add the certificate to the personal store of the Administration and Monitoring Server.</span></span> <span data-ttu-id="94cf4-223">若要添加证书，请打开本地计算机上的 "证书" 存储。</span><span class="sxs-lookup"><span data-stu-id="94cf4-223">To add the certificate, open the Certificates store on the local computer.</span></span> <span data-ttu-id="94cf4-224">为此，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="94cf4-224">To do this, follow these steps:</span></span>

1. <span data-ttu-id="94cf4-225">右键选择 "开始"，然后选择 "运行"。</span><span class="sxs-lookup"><span data-stu-id="94cf4-225">Right-select Start, and then select Run.</span></span>

   ![<span data-ttu-id="94cf4-226">选择</span><span class="sxs-lookup"><span data-stu-id="94cf4-226">Select</span></span> ](images/deploying-MBAM-2.png)

2. <span data-ttu-id="94cf4-227">键入 "MMC.EXE" （不带引号），然后选择 **"确定**"。</span><span class="sxs-lookup"><span data-stu-id="94cf4-227">Type "MMC.EXE" (without the quotation marks), and then select **OK**.</span></span>

   !["运行" 框](images/deploying-MBAM-3.png) 

3. <span data-ttu-id="94cf4-229">在打开的新 MMC 中选择 "**文件**"，然后选择 "**添加/删除管理单元**"。</span><span class="sxs-lookup"><span data-stu-id="94cf4-229">Select **File** in the new MMC that you opened, and then select **Add/Remove Snap-in**.</span></span>
   
   ![选择](images/deploying-MBAM-4.png)

4. <span data-ttu-id="94cf4-231">突出显示 "**证书**" 管理单元，然后选择 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="94cf4-231">Highlight the **Certificates** snap-in, and then select **Add**.</span></span>

   !["添加或删除管理单元" 窗口](images/deploying-MBAM-5.png)

5. <span data-ttu-id="94cf4-233">选择 "**计算机帐户**" 选项，然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="94cf4-233">Select the **Computer account** option, and then select **Next**.</span></span>
   
   !["证书" 管理单元窗口](images/deploying-MBAM-6.png)

6. <span data-ttu-id="94cf4-235">在下一个屏幕上选择 "**本地计算机**"，然后选择 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="94cf4-235">Select **Local Computer** on the next screen, and then select **Finish**.</span></span>
   
   ![选择计算机窗口](images/deploying-MBAM-7.png)

7. <span data-ttu-id="94cf4-237">您现在已添加 "证书" 管理单元。</span><span class="sxs-lookup"><span data-stu-id="94cf4-237">You have now added the Certificates snap-in.</span></span> <span data-ttu-id="94cf4-238">这将使你能够使用计算机的证书存储中的任何证书。</span><span class="sxs-lookup"><span data-stu-id="94cf4-238">This will enable you to work with any certificates in your computer's certificate store.</span></span>

   !["添加或删除管理单元" 窗口](images/deploying-MBAM-8.png)

8. <span data-ttu-id="94cf4-240">将 web 服务器证书导入到计算机的证书存储中。</span><span class="sxs-lookup"><span data-stu-id="94cf4-240">Import the web server certificate into your computer's certificate store.</span></span>

   <span data-ttu-id="94cf4-241">既然您有权访问 "证书" 管理单元，则可以将 web 服务器证书导入到计算机的证书存储中。</span><span class="sxs-lookup"><span data-stu-id="94cf4-241">Now that you have access to the Certificates snap-in, you can import the web server certificate into your computer's certificate store.</span></span> <span data-ttu-id="94cf4-242">若要执行此操作，请执行后续步骤。</span><span class="sxs-lookup"><span data-stu-id="94cf4-242">To do this, follow the next steps.</span></span>

9. <span data-ttu-id="94cf4-243">打开 "证书（本地计算机）" 管理单元，然后通过浏览找到 "**个人**"，然后找到 "**证书**"。</span><span class="sxs-lookup"><span data-stu-id="94cf4-243">Open the Certificates (Local Computer) snap-in, and browse to **Personal** and then **Certificates**.</span></span>
   
   !["证书（本地计算机）" 管理单元窗口](images/deploying-MBAM-9.png)

   > [!Note]
   > <span data-ttu-id="94cf4-245">可能未列出 "证书" 管理单元。</span><span class="sxs-lookup"><span data-stu-id="94cf4-245">The Certificates snap-in may not be listed.</span></span> <span data-ttu-id="94cf4-246">如果不是，则没有安装证书。</span><span class="sxs-lookup"><span data-stu-id="94cf4-246">If it is not, no certificates are installed.</span></span>

10. <span data-ttu-id="94cf4-247">右键选择 "**证书**"，选择 "**所有任务**"，然后选择 "**导入**"。</span><span class="sxs-lookup"><span data-stu-id="94cf4-247">Right-select **Certificates**, select **All Tasks**, and then select **Import**.</span></span>

    !["证书（本地计算机）" 管理单元窗口](images/deploying-MBAM-10.png)

11. <span data-ttu-id="94cf4-249">向导启动后，选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="94cf4-249">When the wizard starts, select **Next**.</span></span> <span data-ttu-id="94cf4-250">浏览到你创建的包含服务器证书和私钥的文件，然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="94cf4-250">Browse to the file that you created that contains your server certificate and private key, and then select **Next**.</span></span>

    !["证书导入向导" 窗口](images/deploying-MBAM-11.png)

12. <span data-ttu-id="94cf4-252">如果在创建文件时为其指定了密码，请输入密码。</span><span class="sxs-lookup"><span data-stu-id="94cf4-252">Enter the password if you specified one for the file when you created it.</span></span>

   ![输入密码窗口](images/deploying-MBAM-12.png)

   > [!Note]
   > <span data-ttu-id="94cf4-254">如果希望能够从该计算机再次导出密钥对，请确保选中 "将**密钥标记为可导出**" 选项。</span><span class="sxs-lookup"><span data-stu-id="94cf4-254">Make sure that the **Mark the key as exportable** option is selected if you want to be able to export the key pair again from this computer.</span></span> <span data-ttu-id="94cf4-255">作为添加的安全措施，您可能希望将此选项保留为 "已清除"，以确保没有人可以对您的私钥进行备份。</span><span class="sxs-lookup"><span data-stu-id="94cf4-255">As an added security measure, you may want to leave this option cleared to make sure that no one can make a backup of your private key.</span></span>
 
13. <span data-ttu-id="94cf4-256">选择 "**下一步**"，然后选择要将证书保存到的**证书存储**。</span><span class="sxs-lookup"><span data-stu-id="94cf4-256">Select **Next**, and then select the **Certificate Store** to which you want to save the certificate.</span></span>

    !["证书导入向导" 窗口](images/deploying-MBAM-13.png)

    > [!Note]
    > <span data-ttu-id="94cf4-258">您应选择 "**个人**版"，因为它是 web 服务器证书。</span><span class="sxs-lookup"><span data-stu-id="94cf4-258">You should select **Personal**, because it is a web server certificate.</span></span> <span data-ttu-id="94cf4-259">如果你已在证书层次结构中包含证书，则该证书也将添加到此应用商店。</span><span class="sxs-lookup"><span data-stu-id="94cf4-259">If you included the certificate in the certification hierarchy, it will also be added to this store.</span></span>
 
14. <span data-ttu-id="94cf4-260">选择 "**下一步**"，然后选择 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="94cf4-260">Select **Next**, and then select **Finish**.</span></span>

    !["证书导入向导" 窗口](images/deploying-MBAM-14.png)

<span data-ttu-id="94cf4-262">现在，你将在 "个人证书" 列表中看到 web 服务器的服务器证书。</span><span class="sxs-lookup"><span data-stu-id="94cf4-262">You will now see the server certificate for your web server in the Personal Certificates list.</span></span> <span data-ttu-id="94cf4-263">它将由服务器的公用名称表示。</span><span class="sxs-lookup"><span data-stu-id="94cf4-263">It will be denoted by the common name of the server.</span></span> <span data-ttu-id="94cf4-264">（您可以在证书的主题部分找到它。）</span><span class="sxs-lookup"><span data-stu-id="94cf4-264">(You can find this in the subject section of the certificate.)</span></span>

<span data-ttu-id="94cf4-265">有关进一步参考：</span><span class="sxs-lookup"><span data-stu-id="94cf4-265">For further reference:</span></span>

[<span data-ttu-id="94cf4-266">MBAM 2.5 安全注意事项</span><span class="sxs-lookup"><span data-stu-id="94cf4-266">MBAM 2.5 Security Considerations</span></span>](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/mbam-25-security-considerations)

[<span data-ttu-id="94cf4-267">规划如何保护 MBAM 网站</span><span class="sxs-lookup"><span data-stu-id="94cf4-267">Planning How to Secure the MBAM Websites</span></span>](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/planning-how-to-secure-the-mbam-websites)

<span data-ttu-id="94cf4-268">下一步是为应用程序池帐户注册一个服务主体名称。</span><span class="sxs-lookup"><span data-stu-id="94cf4-268">The next step is to register a service principle name for the application pool account.</span></span>

### <span data-ttu-id="94cf4-269">步骤4：为 MBAM Web 服务器配置 SSL 证书</span><span class="sxs-lookup"><span data-stu-id="94cf4-269">Step 4: Configuring SSL certificate for MBAM Web Server</span></span>

<span data-ttu-id="94cf4-270">如果在客户端和服务器之间使用 SSL 通信，则应确保证书具有增强的密钥用法 Oid （1.3.6.1.5.5.7.3.1）和（1.3.6.1.5.5.7.3.2）。</span><span class="sxs-lookup"><span data-stu-id="94cf4-270">If you are using SSL communication between the client and server, you should make sure that the certificate has Enhanced Key Usage OIDs (1.3.6.1.5.5.7.3.1) and (1.3.6.1.5.5.7.3.2).</span></span> <span data-ttu-id="94cf4-271">也就是说，应确保添加服务器身份验证和客户端身份验证。</span><span class="sxs-lookup"><span data-stu-id="94cf4-271">That is, you should make sure that Server Authentication and Client Authentication are added.</span></span>

<span data-ttu-id="94cf4-272">如果你在尝试浏览服务 Url 时收到证书错误，则表示你使用的是颁发给其他名称的证书，或者你正在使用不正确的 URL 进行浏览。</span><span class="sxs-lookup"><span data-stu-id="94cf4-272">If you receive a certificate error when you try to browse service URLs, you are using a certificate that was issued to a different name, or you are browsing by using an incorrect URL.</span></span>

<span data-ttu-id="94cf4-273">尽管浏览器可能会提示你提供证书错误消息，但你继续操作，MBAM web 服务将不会忽略证书错误，并且将阻止连接。</span><span class="sxs-lookup"><span data-stu-id="94cf4-273">Although the browser may prompt you with a certificate error message but let you continue, the MBAM web service will not ignore certificate errors and will block the connection.</span></span> <span data-ttu-id="94cf4-274">在 MBAM 客户端的 MBAM 管理事件日志中，你将注意到与证书相关的错误。</span><span class="sxs-lookup"><span data-stu-id="94cf4-274">You will notice certificate-related errors in the MBAM client’s MBAM Admin event log.</span></span> <span data-ttu-id="94cf4-275">如果使用别名连接到管理和监视服务器，则应将证书颁发给别名。</span><span class="sxs-lookup"><span data-stu-id="94cf4-275">If you are using an alias to connect to the Administration and Monitoring server, you should issue a certificate to the alias name.</span></span> <span data-ttu-id="94cf4-276">也就是说，证书的使用者名称应为别名，本地服务器的 DNS 名称应添加到证书的 "**主题备用名称**" 字段。</span><span class="sxs-lookup"><span data-stu-id="94cf4-276">That is, the subject name of the certificate should be the alias name, and the local server’s DNS name should be added to the **Subject Alternative Name** field of the certificate.</span></span>

<span data-ttu-id="94cf4-277">示例：</span><span class="sxs-lookup"><span data-stu-id="94cf4-277">Example:</span></span>

<span data-ttu-id="94cf4-278">如果虚拟名称为 "bitlocker.contoso.com"，而 MBAM 管理和监视服务器名称为 "adminserver.contoso.com"，则应将证书颁发给 bitlocker.contoso.com （subject 名称），并且应将 adminserver.contoso.com 添加到证书的 "**主题备用名称**" 字段。</span><span class="sxs-lookup"><span data-stu-id="94cf4-278">If the virtual name is "bitlocker.contoso.com" and the MBAM Administration and Monitoring server name is "adminserver.contoso.com," the certificate should be issued to bitlocker.contoso.com (subject name), and adminserver.contoso.com should be added to **Subject Alternative Name** field of the certificate.</span></span>

<span data-ttu-id="94cf4-279">同样，如果你安装了多个管理和监视服务器以通过负载平衡器平衡负载，则应将 SSL 证书颁发给虚拟名称。</span><span class="sxs-lookup"><span data-stu-id="94cf4-279">Similarly, if you have multiple Administration and Monitoring servers installed to balance the load by using a load balancer, you should issue the SSL certificate to the virtual name.</span></span> <span data-ttu-id="94cf4-280">也就是说，证书的 "主题名称" 字段应具有虚拟名称，并且所有本地服务器的名称都应添加到证书的 "**主题备用名称**" 字段中。</span><span class="sxs-lookup"><span data-stu-id="94cf4-280">That is, the subject name field of the certificate should have the virtual name, and the names of all the local servers should be added in the **Subject Alternative Name** field of the certificate.</span></span>

<span data-ttu-id="94cf4-281">示例：</span><span class="sxs-lookup"><span data-stu-id="94cf4-281">Example:</span></span>

<span data-ttu-id="94cf4-282">如果虚拟名称为 "bitlocker.contoso.com"，并且服务器为 "adminserver1.contoso.com" 和 "adminiserver2.contoso.com"，则应将证书颁发给 bitlocker.contoso.com （subject 名称）和 adminserver1.contoso.com，并且应将 adminiserver2.contoso.com 添加到证书的 "**主题备用名称**" 字段。</span><span class="sxs-lookup"><span data-stu-id="94cf4-282">If the virtual name is "bitlocker.contoso.com" and the servers are "adminserver1.contoso.com" and "adminiserver2.contoso.com," the certificate should be issued to bitlocker.contoso.com (subject name) and adminserver1.contoso.com, and adminiserver2.contoso.com should be added to the **Subject Alternative Name** field of the certificate.</span></span>

<span data-ttu-id="94cf4-283">以下知识库文章中介绍了使用 MBAM 配置 SSL 通信的步骤： [KB 2754259](https://support.microsoft.com/help/2754259)。</span><span class="sxs-lookup"><span data-stu-id="94cf4-283">The steps to configure SSL communication by using MBAM are described in the following Knowledge Base article: [KB 2754259](https://support.microsoft.com/help/2754259).</span></span>

### <span data-ttu-id="94cf4-284">步骤5：注册应用程序池帐户的 SPN 并配置受限委派</span><span class="sxs-lookup"><span data-stu-id="94cf4-284">Step 5: Register SPNS for the application pool account and configure constrained delegation</span></span>

> [!Note]
> <span data-ttu-id="94cf4-285">限制委派仅适用于2.5，对于 2.5 Service Pack 1 和更高版本不是必需的。</span><span class="sxs-lookup"><span data-stu-id="94cf4-285">Constrained delegation is required only for 2.5 and is not required for 2.5 Service Pack 1 and later.</span></span>

<span data-ttu-id="94cf4-286">若要使 MBAM 服务器能够对来自管理和监视网站和自助服务门户的通信进行身份验证，你必须在用于 web 应用程序池的域帐户下注册主机名的服务主体名称（SPN）。</span><span class="sxs-lookup"><span data-stu-id="94cf4-286">To enable the MBAM servers to authenticate communication from the Administration and Monitoring Website and the Self-Service Portal, you must register a Service Principal Name (SPN) for the host name under the domain account that you are using for the web application pool.</span></span> <span data-ttu-id="94cf4-287">以下文章包含注册 Spn 的分步说明：[规划如何保护 MBAM 网站](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/planning-how-to-secure-the-mbam-websites)</span><span class="sxs-lookup"><span data-stu-id="94cf4-287">The following article contains step-by-step instructions to register SPNs: [Planning How to Secure the MBAM Websites](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/planning-how-to-secure-the-mbam-websites)</span></span>

<span data-ttu-id="94cf4-288">配置 SPN 后，应在 SPN 上设置受约束的委派。</span><span class="sxs-lookup"><span data-stu-id="94cf4-288">After you have the SPN configured, you should set up constrained delegation on the SPN.</span></span> <span data-ttu-id="94cf4-289">为此，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="94cf4-289">To do this, follow these steps:</span></span>

1. <span data-ttu-id="94cf4-290">转到 Active Directory，并查找您在前面的步骤中为 MBAM 网站配置的应用池凭据。</span><span class="sxs-lookup"><span data-stu-id="94cf4-290">Go to Active Directory, and find the app pool credentials that you configured for MBAM websites in the previous steps.</span></span>

2. <span data-ttu-id="94cf4-291">右键单击凭据，然后选择 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="94cf4-291">Right-click the credentials, and then select **properties**.</span></span>

3. <span data-ttu-id="94cf4-292">选择 "**委派**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="94cf4-292">Select the **delegation** tab.</span></span>

4. <span data-ttu-id="94cf4-293">选择 Kerberos 身份验证的选项。</span><span class="sxs-lookup"><span data-stu-id="94cf4-293">Select the option for Kerberos authentication.</span></span>

5. <span data-ttu-id="94cf4-294">选择 "**浏览**"，然后再次浏览你的应用池凭据。</span><span class="sxs-lookup"><span data-stu-id="94cf4-294">Select **browse**, and browse again for your app pool credentials.</span></span> <span data-ttu-id="94cf4-295">然后，你应该看到在应用池凭据帐户上设置的所有 Spn。</span><span class="sxs-lookup"><span data-stu-id="94cf4-295">You should then see the all the SPNs that are set up on the app pool creds account.</span></span> <span data-ttu-id="94cf4-296">（SPN 应类似于 "http/bitlocker fqdn .com"）。</span><span class="sxs-lookup"><span data-stu-id="94cf4-296">(The SPN should resemble "http/bitlocker.fqdn.com").</span></span> <span data-ttu-id="94cf4-297">突出显示与在 MBAM 安装期间指定的主机名相同的 SPN。</span><span class="sxs-lookup"><span data-stu-id="94cf4-297">Highlight the SPN that is the same as the host name that you specified during the MBAM installation.</span></span>

6. <span data-ttu-id="94cf4-298">选择“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="94cf4-298">Select **OK**.</span></span>

<span data-ttu-id="94cf4-299">现在，你可以获得先决条件。</span><span class="sxs-lookup"><span data-stu-id="94cf4-299">Now you are good with prerequisites.</span></span> <span data-ttu-id="94cf4-300">在接下来的步骤中，你将在服务器上安装 MBAM 软件并对其进行配置。</span><span class="sxs-lookup"><span data-stu-id="94cf4-300">In the next steps, you will install the MBAM software on the servers and configure it.</span></span>

## <span data-ttu-id="94cf4-301">安装和配置 MBAM 2.5 服务器软件</span><span class="sxs-lookup"><span data-stu-id="94cf4-301">Installing and configuring MBAM 2.5 server software</span></span>

### <span data-ttu-id="94cf4-302">步骤6：安装 MBAM 2.5 server 软件</span><span class="sxs-lookup"><span data-stu-id="94cf4-302">Step 6: Install MBAM 2.5 server software</span></span> 

<span data-ttu-id="94cf4-303">若要在数据库服务器和管理和监视服务器上使用 Microsoft BitLocker 管理和监视设置向导安装 MBAM 服务器软件，请按照以下步骤操作。</span><span class="sxs-lookup"><span data-stu-id="94cf4-303">To install the MBAM Server software by using the Microsoft BitLocker Administration and Monitoring Setup wizard both on Database Server and on Administration and Monitoring Server, follow these steps.</span></span>

1. <span data-ttu-id="94cf4-304">在要在其上安装 MBAM 的服务器上，运行 MBAMserversetup.exe 以启动 Microsoft BitLocker 管理和监视设置向导。</span><span class="sxs-lookup"><span data-stu-id="94cf4-304">On the server on which you want to install MBAM, run MBAMserversetup.exe to start the Microsoft BitLocker Administration and Monitoring Setup wizard.</span></span>

2. <span data-ttu-id="94cf4-305">在 "欢迎" 页面上，选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="94cf4-305">On the Welcome page, select **Next**.</span></span>

3. <span data-ttu-id="94cf4-306">阅读并接受 Microsoft 软件许可协议，然后选择 "**下一步**" 继续安装。</span><span class="sxs-lookup"><span data-stu-id="94cf4-306">Read and accept the Microsoft Software License Agreement, and then select **Next** to continue the installation.</span></span>

4. <span data-ttu-id="94cf4-307">确定在检查更新时是否使用 Microsoft Update，然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="94cf4-307">Decide whether to use Microsoft Update when you check for updates, and then select **Next**.</span></span>

5. <span data-ttu-id="94cf4-308">确定是否参与 "客户体验改善计划"，然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="94cf4-308">Decide whether to participate in the Customer Experience Improvement Program, and then select **Next**.</span></span>

6. <span data-ttu-id="94cf4-309">若要开始安装，请选择 "**安装**"。</span><span class="sxs-lookup"><span data-stu-id="94cf4-309">To start the installation, select **Install**.</span></span>

7. <span data-ttu-id="94cf4-310">若要在 MBAM 服务器软件完成安装后配置服务器功能，请选择 "在**向导关闭后运行 MBAM 服务器配置**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="94cf4-310">To configure the server features after the MBAM Server software finishes installing, select the **Run MBAM Server Configuration after the wizard closes** check box.</span></span> <span data-ttu-id="94cf4-311">或者，你可以稍后通过使用服务器安装在 "**开始**" 菜单上创建的**MBAM 服务器配置**快捷方式来配置 MBAM。</span><span class="sxs-lookup"><span data-stu-id="94cf4-311">Or, you can configure MBAM later by using the **MBAM Server Configuration** shortcut that the server installation creates on your **Start** menu.</span></span>

8. <span data-ttu-id="94cf4-312">选择 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="94cf4-312">Select **Finish**.</span></span>

<span data-ttu-id="94cf4-313">有关详细信息，请参阅[安装 MBAM 2.5 Server 软件](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/installing-the-mbam-25-server-software)。</span><span class="sxs-lookup"><span data-stu-id="94cf4-313">For more information, see [Installing the MBAM 2.5 Server Software](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/installing-the-mbam-25-server-software).</span></span>

### <span data-ttu-id="94cf4-314">步骤7：配置 MBAM 2.5 数据库和报表角色</span><span class="sxs-lookup"><span data-stu-id="94cf4-314">Step 7: Configure MBAM 2.5 database and reports role</span></span>

<span data-ttu-id="94cf4-315">在此步骤中，我们将使用 MBAM 向导配置 MBAM 2.5 数据库和报告组件：</span><span class="sxs-lookup"><span data-stu-id="94cf4-315">In this step, we will configure the MBAM 2.5 databases and reporting component by using the MBAM Wizard:</span></span>

1. <span data-ttu-id="94cf4-316">使用向导配置合规性和审核数据库和恢复数据库：</span><span class="sxs-lookup"><span data-stu-id="94cf4-316">Configure the Compliance and Audit Database and the Recovery Database by using the wizard:</span></span>
   
   1. <span data-ttu-id="94cf4-317">在要配置数据库的服务器上，启动 " **MBAM 服务器配置向导**"。</span><span class="sxs-lookup"><span data-stu-id="94cf4-317">On the server on which you want to configure the databases, start the **MBAM Server Configuration wizard**.</span></span> <span data-ttu-id="94cf4-318">你可以选择 "**开始**" 菜单上的 " **MBAM 服务器配置**" 以打开该向导。</span><span class="sxs-lookup"><span data-stu-id="94cf4-318">You can select **MBAM Server Configuration** on the **Start** menu to open the wizard.</span></span>

   2. <span data-ttu-id="94cf4-319">选择 "**添加新功能**"，选择 "**合规性和审核数据库**"、"**恢复数据库和报告**"，然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="94cf4-319">Select **Add New Features**, select **Compliance and Audit Database**, **Recovery Database and Reports**, and then select **Next**.</span></span> <span data-ttu-id="94cf4-320">向导检查是否满足数据库的所有必备条件。</span><span class="sxs-lookup"><span data-stu-id="94cf4-320">The wizard checks that all prerequisites for the databases are met.</span></span>

   3. <span data-ttu-id="94cf4-321">如果先决条件检查成功，请选择 "**下一步**" 以继续。</span><span class="sxs-lookup"><span data-stu-id="94cf4-321">If the prerequisite check is successful, select **Next** to continue.</span></span> <span data-ttu-id="94cf4-322">否则，请解决任何缺少的先决条件，然后**再次选择 "检查先决条件**"。</span><span class="sxs-lookup"><span data-stu-id="94cf4-322">Otherwise, resolve any missing prerequisites, and then select **Check prerequisites again**.</span></span>
   
   4. <span data-ttu-id="94cf4-323">使用以下说明，在向导中输入字段值：</span><span class="sxs-lookup"><span data-stu-id="94cf4-323">Using the following descriptions, enter the field values in the wizard:</span></span>

2. <span data-ttu-id="94cf4-324">合规性和审核数据库</span><span class="sxs-lookup"><span data-stu-id="94cf4-324">Compliance and audit database</span></span>

   |<span data-ttu-id="94cf4-325">字段</span><span class="sxs-lookup"><span data-stu-id="94cf4-325">Field</span></span>   |<span data-ttu-id="94cf4-326">描述</span><span class="sxs-lookup"><span data-stu-id="94cf4-326">Description</span></span>|
   |-------|-------|
   |<span data-ttu-id="94cf4-327">SQL Server 名称</span><span class="sxs-lookup"><span data-stu-id="94cf4-327">SQL Server name</span></span> |<span data-ttu-id="94cf4-328">在其上配置合规性和审核数据库的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="94cf4-328">Name of the server on which you are configuring the Compliance and Audit Database.</span></span> <br /> <span data-ttu-id="94cf4-329">必须在合规性和审核数据库计算机上添加异常，才能在 SQL Server 端口上启用传入入站流量。</span><span class="sxs-lookup"><span data-stu-id="94cf4-329">You must add an exception on the Compliance and Audit Database computer to enable incoming inbound traffic on the SQL Server port.</span></span> <span data-ttu-id="94cf4-330">默认端口号为1433。</span><span class="sxs-lookup"><span data-stu-id="94cf4-330">The default port number is 1433.</span></span>|
   |<span data-ttu-id="94cf4-331">SQL Server 数据库实例</span><span class="sxs-lookup"><span data-stu-id="94cf4-331">SQL Server database instance</span></span>    |<span data-ttu-id="94cf4-332">将存储合规性和审核数据的数据库实例的名称。</span><span class="sxs-lookup"><span data-stu-id="94cf4-332">Name of the database instance where the compliance and audit data will be stored.</span></span> <span data-ttu-id="94cf4-333">如果您使用的是默认实例，则必须将此字段保留为空。</span><span class="sxs-lookup"><span data-stu-id="94cf4-333">If you are using the default instance, you must leave this field blank.</span></span> <span data-ttu-id="94cf4-334">还必须指定数据库信息的存放位置。</span><span class="sxs-lookup"><span data-stu-id="94cf4-334">You must also specify where the database information will be located.</span></span>|
   |<span data-ttu-id="94cf4-335">数据库名称</span><span class="sxs-lookup"><span data-stu-id="94cf4-335">Database name</span></span>   |<span data-ttu-id="94cf4-336">将存储合规性数据的数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="94cf4-336">Name of the database that will store the compliance data.</span></span> <span data-ttu-id="94cf4-337">你必须记下在此处指定的数据库的名称，因为你需要在后续步骤中提供此信息。</span><span class="sxs-lookup"><span data-stu-id="94cf4-337">You must note the name of the database that you are specifying here because you will have to provide this information in later steps.</span></span>|
   |<span data-ttu-id="94cf4-338">读/写权限域用户或组</span><span class="sxs-lookup"><span data-stu-id="94cf4-338">Read/write permission domain user or group</span></span>  |<span data-ttu-id="94cf4-339">指定在步骤2中配置的 MBAMAppPool 用户的名称。</span><span class="sxs-lookup"><span data-stu-id="94cf4-339">Specify the name of the MBAMAppPool user as configured in step 2.</span></span>|
   |<span data-ttu-id="94cf4-340">只读访问域用户或组</span><span class="sxs-lookup"><span data-stu-id="94cf4-340">Read-only access domain user or group</span></span>   |<span data-ttu-id="94cf4-341">指定在步骤2中配置的 MBAMROUser 用户的名称。</span><span class="sxs-lookup"><span data-stu-id="94cf4-341">Specify the name of the MBAMROUser user as configured in step 2.</span></span>|

3. <span data-ttu-id="94cf4-342">恢复数据库。</span><span class="sxs-lookup"><span data-stu-id="94cf4-342">Recovery database.</span></span>

   |<span data-ttu-id="94cf4-343">字段</span><span class="sxs-lookup"><span data-stu-id="94cf4-343">Field</span></span>   |<span data-ttu-id="94cf4-344">描述</span><span class="sxs-lookup"><span data-stu-id="94cf4-344">Description</span></span>|
   |-----|-----|
   |<span data-ttu-id="94cf4-345">SQL Server 名称</span><span class="sxs-lookup"><span data-stu-id="94cf4-345">SQL Server name</span></span> |<span data-ttu-id="94cf4-346">在其上配置恢复数据库的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="94cf4-346">Name of the server on which you are configuring the Recovery Database.</span></span> <span data-ttu-id="94cf4-347">必须在恢复数据库计算机上添加例外，才能在 SQL Server 端口上启用传入入站流量。</span><span class="sxs-lookup"><span data-stu-id="94cf4-347">You must add an exception on the Recovery Database computer to enable incoming inbound traffic on the SQL Server port.</span></span> <span data-ttu-id="94cf4-348">默认端口号为1433。</span><span class="sxs-lookup"><span data-stu-id="94cf4-348">The default port number is 1433.</span></span>|
   |<span data-ttu-id="94cf4-349">SQL Server 数据库实例</span><span class="sxs-lookup"><span data-stu-id="94cf4-349">SQL Server database instance</span></span>    |<span data-ttu-id="94cf4-350">将存储恢复数据的数据库实例的名称。</span><span class="sxs-lookup"><span data-stu-id="94cf4-350">Name of the database instance where the recovery data will be stored.</span></span> <span data-ttu-id="94cf4-351">如果您使用的是默认实例，则必须将此字段保留为空。</span><span class="sxs-lookup"><span data-stu-id="94cf4-351">If you are using the default instance, you must leave this field blank.</span></span> <span data-ttu-id="94cf4-352">还必须指定数据库信息的存放位置。</span><span class="sxs-lookup"><span data-stu-id="94cf4-352">You must also specify where the database information will be located.</span></span>|
   |<span data-ttu-id="94cf4-353">数据库名称</span><span class="sxs-lookup"><span data-stu-id="94cf4-353">Database name</span></span>   |<span data-ttu-id="94cf4-354">将存储恢复数据的数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="94cf4-354">Name of the database that will store the recovery data.</span></span>|
   |<span data-ttu-id="94cf4-355">读/写权限域用户或组</span><span class="sxs-lookup"><span data-stu-id="94cf4-355">Read/write permission domain user or group</span></span>  |<span data-ttu-id="94cf4-356">对此数据库具有读/写权限的域用户或组，以使 web 应用程序能够访问此数据库中的数据和报表。</span><span class="sxs-lookup"><span data-stu-id="94cf4-356">Domain user or group that has read/write permission to this database to enable the web applications to access the data and reports in this database.</span></span> <br /><span data-ttu-id="94cf4-357">如果在此字段中输入用户，它必须与 "**配置 Web 应用程序**" 页面上的 " **web 服务应用程序池域帐户**" 字段中的值相同。</span><span class="sxs-lookup"><span data-stu-id="94cf4-357">If you enter a user in this field, it must be the same value as the value in the **Web service application pool domain account** field on the **Configure Web Applications** page.</span></span> <br /><span data-ttu-id="94cf4-358">如果在此字段中输入组，则 "**配置 Web 应用程序**" 页面上的 " **Web 服务应用程序池域帐户**" 字段中的值必须是您在此字段中输入的组的成员。</span><span class="sxs-lookup"><span data-stu-id="94cf4-358">If you enter a group in this field, the value in the **Web service application pool domain account** field on the **Configure Web Applications** page must be a member of the group that you enter in this field.</span></span>|
   
   <span data-ttu-id="94cf4-359">完成输入后，选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="94cf4-359">When you finish your entries, select **Next**.</span></span> <span data-ttu-id="94cf4-360">向导检查是否满足数据库的所有必备条件。</span><span class="sxs-lookup"><span data-stu-id="94cf4-360">The wizard checks that all prerequisites for the databases are met.</span></span>
   
   <span data-ttu-id="94cf4-361">如果先决条件检查成功，请选择 "**下一步**" 以继续。</span><span class="sxs-lookup"><span data-stu-id="94cf4-361">If the prerequisite check is successful, select **Next** to continue.</span></span> <span data-ttu-id="94cf4-362">否则，请解决任何缺少的先决条件，然后再次选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="94cf4-362">Otherwise, resolve any missing prerequisites, and then select **Next** again.</span></span>

4. <span data-ttu-id="94cf4-363">报告会.</span><span class="sxs-lookup"><span data-stu-id="94cf4-363">Reports.</span></span>

   |<span data-ttu-id="94cf4-364">字段</span><span class="sxs-lookup"><span data-stu-id="94cf4-364">Field</span></span>   |<span data-ttu-id="94cf4-365">描述</span><span class="sxs-lookup"><span data-stu-id="94cf4-365">Description</span></span>|
   |----|----|
   |<span data-ttu-id="94cf4-366">SQL Server Reporting Services 实例</span><span class="sxs-lookup"><span data-stu-id="94cf4-366">SQL Server Reporting Services instance</span></span>  |<span data-ttu-id="94cf4-367">将配置报告的 SQL Server Reporting Services 的实例。</span><span class="sxs-lookup"><span data-stu-id="94cf4-367">Instance of SQL Server Reporting Services where the reports will be configured.</span></span> <span data-ttu-id="94cf4-368">如果您使用的是默认实例，则必须将此字段保留为空。</span><span class="sxs-lookup"><span data-stu-id="94cf4-368">If you are using the default instance, you must leave this field blank.</span></span>|
   |<span data-ttu-id="94cf4-369">报告角色域组</span><span class="sxs-lookup"><span data-stu-id="94cf4-369">Reporting role domain group</span></span> |<span data-ttu-id="94cf4-370">按照步骤2中所述，指定 MBAMRUGrp 的名称。</span><span class="sxs-lookup"><span data-stu-id="94cf4-370">Specify the name of the MBAMRUGrp as mentioned in step 2.</span></span>|
   |<span data-ttu-id="94cf4-371">SQL Server 名称</span><span class="sxs-lookup"><span data-stu-id="94cf4-371">SQL Server name</span></span> |<span data-ttu-id="94cf4-372">配置合规性和审核数据库的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="94cf4-372">Name of the server on which the Compliance and Audit Database is configured.</span></span>|
   |<span data-ttu-id="94cf4-373">SQL Server 数据库实例</span><span class="sxs-lookup"><span data-stu-id="94cf4-373">SQL Server database instance</span></span>    |<span data-ttu-id="94cf4-374">配置合规性和审核数据的数据库实例的名称。</span><span class="sxs-lookup"><span data-stu-id="94cf4-374">Name of the database instance where the compliance and audit data is configured.</span></span> <span data-ttu-id="94cf4-375">如果您使用的是默认实例，则必须将此字段保留为空。</span><span class="sxs-lookup"><span data-stu-id="94cf4-375">If you are using the default instance, you must leave this field blank.</span></span> <br /><span data-ttu-id="94cf4-376">必须在报表计算机上添加异常，才能在报表服务器的端口上启用传入流量。</span><span class="sxs-lookup"><span data-stu-id="94cf4-376">You must add an exception on the Reports computer to enable incoming traffic on the port of the Reporting Server.</span></span> <span data-ttu-id="94cf4-377">（默认端口为80。）</span><span class="sxs-lookup"><span data-stu-id="94cf4-377">(The default port is 80.)</span></span>|
   |<span data-ttu-id="94cf4-378">数据库名称</span><span class="sxs-lookup"><span data-stu-id="94cf4-378">Database name</span></span>|  <span data-ttu-id="94cf4-379">合规性和审核数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="94cf4-379">Name of the Compliance and Audit Database.</span></span> <span data-ttu-id="94cf4-380">默认情况下，数据库名称为 MBAM 合规性状态。</span><span class="sxs-lookup"><span data-stu-id="94cf4-380">By default, the database name is MBAM Compliance Status.</span></span>|
   |<span data-ttu-id="94cf4-381">合规性和审核数据库域帐户</span><span class="sxs-lookup"><span data-stu-id="94cf4-381">Compliance and Audit Database domain account</span></span>    |<span data-ttu-id="94cf4-382">指定在步骤2中配置的 MBAMROUser 用户的名称。</span><span class="sxs-lookup"><span data-stu-id="94cf4-382">Specify the name of the MBAMROUser user as configured in step 2.</span></span>|
   
   <span data-ttu-id="94cf4-383">完成输入后，选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="94cf4-383">When you finish your entries, select **Next**.</span></span> <span data-ttu-id="94cf4-384">向导将检查是否满足 "报告" 功能的所有先决条件。</span><span class="sxs-lookup"><span data-stu-id="94cf4-384">The wizard checks that all prerequisites for the Reports feature are met.</span></span> <span data-ttu-id="94cf4-385">选择“下一步”以继续。</span><span class="sxs-lookup"><span data-stu-id="94cf4-385">Select Next to continue.</span></span> <span data-ttu-id="94cf4-386">在 "**摘要**" 页面上，查看将添加的功能。</span><span class="sxs-lookup"><span data-stu-id="94cf4-386">On the **Summary** page, review the features that will be added.</span></span>
   
   <span data-ttu-id="94cf4-387">有关详细信息，请参阅以下文章：[如何配置 MBAM 2.5 数据库](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/how-to-configure-the-mbam-25-databases)。</span><span class="sxs-lookup"><span data-stu-id="94cf4-387">For more information, see the following article: [How to Configure the MBAM 2.5 Databases](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/how-to-configure-the-mbam-25-databases).</span></span>

### <span data-ttu-id="94cf4-388">步骤8：配置 MBAM 2.5 Web 应用程序角色</span><span class="sxs-lookup"><span data-stu-id="94cf4-388">Step 8: Configure the MBAM 2.5 Web applications role</span></span>

1. <span data-ttu-id="94cf4-389">在要配置 web 应用程序的服务器上，启动 "MBAM 服务器配置向导"。</span><span class="sxs-lookup"><span data-stu-id="94cf4-389">On the server on which you want to configure the web applications, start the MBAM Server Configuration wizard.</span></span> <span data-ttu-id="94cf4-390">你可以选择 "**开始**" 菜单上的 " **MBAM 服务器配置**" 以打开该向导。</span><span class="sxs-lookup"><span data-stu-id="94cf4-390">You can select **MBAM Server Configuration** on the **Start** menu to open the wizard.</span></span>

2. <span data-ttu-id="94cf4-391">选择 "**添加新功能**"，选择 "**管理和监视网站**和**自助服务门户**"，然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="94cf4-391">Select **Add New Features**, select **Administration and Monitoring Website** and **Self-Service Portal**, and then select **Next**.</span></span> <span data-ttu-id="94cf4-392">向导检查是否满足数据库的所有必备条件。</span><span class="sxs-lookup"><span data-stu-id="94cf4-392">The wizard checks that all prerequisites for the databases are met.</span></span>

3. <span data-ttu-id="94cf4-393">如果先决条件检查成功，请选择 "**下一步**" 以继续。</span><span class="sxs-lookup"><span data-stu-id="94cf4-393">If the prerequisite check is successful, select **Next** to continue.</span></span> <span data-ttu-id="94cf4-394">否则，请解决任何缺少的先决条件，然后**再次选择 "检查先决条件**"。</span><span class="sxs-lookup"><span data-stu-id="94cf4-394">Otherwise, resolve any missing prerequisites, and then select **Check prerequisites again**.</span></span>

4. <span data-ttu-id="94cf4-395">使用以下说明在向导中输入字段值。</span><span class="sxs-lookup"><span data-stu-id="94cf4-395">Use the following descriptions to enter the field values in the wizard.</span></span>

   |<span data-ttu-id="94cf4-396">字段</span><span class="sxs-lookup"><span data-stu-id="94cf4-396">Field</span></span>   |<span data-ttu-id="94cf4-397">描述</span><span class="sxs-lookup"><span data-stu-id="94cf4-397">Description</span></span>|
   |-----|-----|
   |<span data-ttu-id="94cf4-398">安全证书</span><span class="sxs-lookup"><span data-stu-id="94cf4-398">Security certificate</span></span>    |<span data-ttu-id="94cf4-399">在步骤3中选择以前创建的证书，以选择性地加密 web 服务与要在其上配置管理和监视网站的服务器之间的通信。</span><span class="sxs-lookup"><span data-stu-id="94cf4-399">Select a previously created certificate in step 3 to optionally encrypt the communication between the web services and the server on which you are configuring the Administration and Monitoring Website.</span></span> <span data-ttu-id="94cf4-400">如果您选择 "不使用证书"，则您的 web 通信可能不安全。</span><span class="sxs-lookup"><span data-stu-id="94cf4-400">If you select Do not use a certificate, your web communication may not be secure.</span></span>|
   |<span data-ttu-id="94cf4-401">主机名</span><span class="sxs-lookup"><span data-stu-id="94cf4-401">Host name</span></span>   |<span data-ttu-id="94cf4-402">在其上配置管理和监视网站的主机的名称。</span><span class="sxs-lookup"><span data-stu-id="94cf4-402">Name of the host computer on which you are configuring the Administration and Monitoring Website.</span></span> <br /><span data-ttu-id="94cf4-403">它不必是计算机的主机名，它可以是任何内容。</span><span class="sxs-lookup"><span data-stu-id="94cf4-403">It does not have to be the hostname of the machine, it could be anything.</span></span> <span data-ttu-id="94cf4-404">但是，如果主机名与计算机的 netbios 名称不同，则必须创建 A 记录并确保 SPN 使用自定义主机名，而不是 netbios 名称。</span><span class="sxs-lookup"><span data-stu-id="94cf4-404">However, if the hostname is different than the netbios name of the computer, you have to create an A record and make sure the SPN uses the custom hostname, not the netbios name.</span></span> <span data-ttu-id="94cf4-405">这在负载平衡方案中很常见。</span><span class="sxs-lookup"><span data-stu-id="94cf4-405">This is common on load balancing scenarios.</span></span>|
   |<span data-ttu-id="94cf4-406">安装路径</span><span class="sxs-lookup"><span data-stu-id="94cf4-406">Installation path</span></span>   |<span data-ttu-id="94cf4-407">要在其上安装管理和监视网站的路径。</span><span class="sxs-lookup"><span data-stu-id="94cf4-407">Path on which you are installing the Administration and Monitoring Website.</span></span>|
   |<span data-ttu-id="94cf4-408">端口</span><span class="sxs-lookup"><span data-stu-id="94cf4-408">Port</span></span>    |<span data-ttu-id="94cf4-409">用于网站通信的端口号。</span><span class="sxs-lookup"><span data-stu-id="94cf4-409">Port number to use for website communication.</span></span> <br /> <span data-ttu-id="94cf4-410">必须设置防火墙例外以通过指定的端口启用通信。</span><span class="sxs-lookup"><span data-stu-id="94cf4-410">You must set a firewall exception to enable communication through the specified port.</span></span>|
   |<span data-ttu-id="94cf4-411">Web 服务应用程序池域帐户和密码</span><span class="sxs-lookup"><span data-stu-id="94cf4-411">Web service application pool domain account and password</span></span>    |<span data-ttu-id="94cf4-412">根据步骤2中的配置，指定 MBAMAppPool 用户的用户帐户和密码。</span><span class="sxs-lookup"><span data-stu-id="94cf4-412">Specify the user account and password of the MBAMAppPool user as configured in step 2.</span></span> <br /> <span data-ttu-id="94cf4-413">为了提高安全性，请将凭据中指定的帐户设置为具有受限的用户权限。</span><span class="sxs-lookup"><span data-stu-id="94cf4-413">For improved security, set the account that is specified in the credentials to have limited user rights.</span></span> <span data-ttu-id="94cf4-414">此外，将帐户的密码设置为永不过期。</span><span class="sxs-lookup"><span data-stu-id="94cf4-414">Also, set the password of the account to never expire.</span></span>|

5. <span data-ttu-id="94cf4-415">验证内置 IIS_IUSRS 帐户或应用程序池帐户是否已添加到**身份验证后模拟客户端**，以及**作为批处理作业登录**的本地安全设置。</span><span class="sxs-lookup"><span data-stu-id="94cf4-415">Verify that the built-in IIS_IUSRS account or the application pool account was added to the **Impersonate a client after authentication** and the **Log on as a batch job** local security settings.</span></span>

   <span data-ttu-id="94cf4-416">若要检查帐户是否已添加到本地安全设置，请打开 "**本地安全策略编辑器**"，展开 "**本地策略**" 节点，选择 "**用户权限分配**" 节点，然后双击 "在**身份验证后模拟客户端**"，并在右侧窗格中**以批处理作业策略的形式登录**。</span><span class="sxs-lookup"><span data-stu-id="94cf4-416">To check whether the account was added to the local security settings, open the **Local Security Policy editor**, expand the **Local Policies** node, select the **User Rights Assignment** node, and double-select **Impersonate a client after authentication** and **Log on as a batch job** policies in the right-side pane.</span></span>

6. <span data-ttu-id="94cf4-417">使用以下字段说明为合规性和审核数据库配置向导中的连接信息。</span><span class="sxs-lookup"><span data-stu-id="94cf4-417">Use the following field descriptions to configure the connection information in the wizard for the Compliance and Audit Database.</span></span>
   |<span data-ttu-id="94cf4-418">字段</span><span class="sxs-lookup"><span data-stu-id="94cf4-418">Field</span></span>   |<span data-ttu-id="94cf4-419">描述</span><span class="sxs-lookup"><span data-stu-id="94cf4-419">Description</span></span>|
   |------|------|
   |<span data-ttu-id="94cf4-420">SQL Server 名称</span><span class="sxs-lookup"><span data-stu-id="94cf4-420">SQL Server name</span></span> |<span data-ttu-id="94cf4-421">配置合规性和审核数据库的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="94cf4-421">Name of the server on which the Compliance and Audit Database is configured.</span></span>|
   |<span data-ttu-id="94cf4-422">SQL Server 数据库实例</span><span class="sxs-lookup"><span data-stu-id="94cf4-422">SQL Server database instance</span></span>    |<span data-ttu-id="94cf4-423">SQL Server 实例的名称（例如 \<Server Name\> ），以及配置合规性和审核数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="94cf4-423">Name of the instance of SQL Server (for example, \<Server Name\>) and on which the Compliance and Audit Database is configured.</span></span> <span data-ttu-id="94cf4-424">如果您使用的是默认实例，请将其保留为空。</span><span class="sxs-lookup"><span data-stu-id="94cf4-424">Leave this blank if you are using the default instance.</span></span>|
   |<span data-ttu-id="94cf4-425">数据库名称</span><span class="sxs-lookup"><span data-stu-id="94cf4-425">Database name</span></span>   |<span data-ttu-id="94cf4-426">合规性和审核数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="94cf4-426">Name of the Compliance and Audit Database.</span></span> <span data-ttu-id="94cf4-427">默认情况下，它是 "MBAM 合规性状态"。</span><span class="sxs-lookup"><span data-stu-id="94cf4-427">By default, it’s "MBAM Compliance Status".</span></span>|

7. <span data-ttu-id="94cf4-428">使用以下字段说明为恢复数据库配置向导中的连接信息。</span><span class="sxs-lookup"><span data-stu-id="94cf4-428">Use the following field descriptions to configure the connection information in the wizard for the Recovery Database.</span></span>
   |<span data-ttu-id="94cf4-429">字段</span><span class="sxs-lookup"><span data-stu-id="94cf4-429">Field</span></span>   |<span data-ttu-id="94cf4-430">描述</span><span class="sxs-lookup"><span data-stu-id="94cf4-430">Description</span></span>|
   |----|----|
   |<span data-ttu-id="94cf4-431">SQL Server 名称</span><span class="sxs-lookup"><span data-stu-id="94cf4-431">SQL Server name</span></span> |<span data-ttu-id="94cf4-432">在其上配置恢复数据库的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="94cf4-432">Name of the server on which the Recovery Database is configured.</span></span>|
   |<span data-ttu-id="94cf4-433">SQL Server 数据库实例</span><span class="sxs-lookup"><span data-stu-id="94cf4-433">SQL Server database instance</span></span>    |<span data-ttu-id="94cf4-434">在其上配置恢复数据库的 SQL Server 实例的名称（例如 \<Server Name\> ）。</span><span class="sxs-lookup"><span data-stu-id="94cf4-434">Name of the instance of SQL Server (for example, \<Server Name\>) on which the Recovery Database is configured.</span></span> <span data-ttu-id="94cf4-435">如果您使用的是默认实例，请将其保留为空。</span><span class="sxs-lookup"><span data-stu-id="94cf4-435">Leave this blank if you are using the default instance.</span></span>|
   |<span data-ttu-id="94cf4-436">数据库名称</span><span class="sxs-lookup"><span data-stu-id="94cf4-436">Database name</span></span>   |<span data-ttu-id="94cf4-437">恢复数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="94cf4-437">Name of the Recovery Database.</span></span> <span data-ttu-id="94cf4-438">默认情况下，它是 "MBAM 恢复和硬件"。</span><span class="sxs-lookup"><span data-stu-id="94cf4-438">By default, it’s "MBAM Recovery and Hardware".</span></span>|

8. <span data-ttu-id="94cf4-439">使用以下说明在向导中输入字段值以配置管理和监视网站。</span><span class="sxs-lookup"><span data-stu-id="94cf4-439">Use the following descriptions to enter the field values in the wizard to configure the Administration and Monitoring Website.</span></span>
   |<span data-ttu-id="94cf4-440">字段</span><span class="sxs-lookup"><span data-stu-id="94cf4-440">Field</span></span>   |<span data-ttu-id="94cf4-441">描述</span><span class="sxs-lookup"><span data-stu-id="94cf4-441">Description</span></span>|
   |----|----|
   |<span data-ttu-id="94cf4-442">高级帮助台角色域组</span><span class="sxs-lookup"><span data-stu-id="94cf4-442">Advanced Helpdesk role domain group</span></span> |<span data-ttu-id="94cf4-443">指定在步骤2中配置的 MBAMAdvHelpDsk 组的名称。</span><span class="sxs-lookup"><span data-stu-id="94cf4-443">Specify the name of the MBAMAdvHelpDsk Group as configured in step 2.</span></span>|
   |<span data-ttu-id="94cf4-444">帮助台角色域组</span><span class="sxs-lookup"><span data-stu-id="94cf4-444">Helpdesk role domain group</span></span>  |<span data-ttu-id="94cf4-445">指定在步骤2中配置的 MBAMHelpDsk 组的名称。</span><span class="sxs-lookup"><span data-stu-id="94cf4-445">Specify the name of the MBAMHelpDsk Group as configured in step 2.</span></span>|
   |<span data-ttu-id="94cf4-446">使用 System Center Configuration Manager 集成</span><span class="sxs-lookup"><span data-stu-id="94cf4-446">Use System Center Configuration Manager Integration</span></span> |<span data-ttu-id="94cf4-447">选中以清除此复选框。</span><span class="sxs-lookup"><span data-stu-id="94cf4-447">Select to clear this check box.</span></span>     |
   |<span data-ttu-id="94cf4-448">报告角色域组</span><span class="sxs-lookup"><span data-stu-id="94cf4-448">Reporting role domain group</span></span> |<span data-ttu-id="94cf4-449">指定在步骤2中配置的 MBAMRUGrp 组的名称。</span><span class="sxs-lookup"><span data-stu-id="94cf4-449">Specify the name of the MBAMRUGrp Group as configured in step 2.</span></span>    |
   |<span data-ttu-id="94cf4-450">SQL Server Reporting Services URL</span><span class="sxs-lookup"><span data-stu-id="94cf4-450">SQL Server Reporting Services URL</span></span>   |<span data-ttu-id="94cf4-451">为在其上配置了 MBAM 报表的 SSRS 服务器指定 Web 服务 URL。</span><span class="sxs-lookup"><span data-stu-id="94cf4-451">Specify the Web Service URL for the SSRS server on which the MBAM reports are configured.</span></span> <span data-ttu-id="94cf4-452">你可以通过登录到数据库服务器上的 Reporting Services 配置管理器查找此信息。</span><span class="sxs-lookup"><span data-stu-id="94cf4-452">You can find this information by logging in to Reporting Services Configuration Manager on the Database Server.</span></span> <br /> <span data-ttu-id="94cf4-453">完全限定域名的示例：https://MyReportServer.Contoso.com/ReportServer</span><span class="sxs-lookup"><span data-stu-id="94cf4-453">Example of a fully qualified domain name: https://MyReportServer.Contoso.com/ReportServer</span></span> <br /><span data-ttu-id="94cf4-454">自定义主机名示例：https://MyReportServer/ReportServer</span><span class="sxs-lookup"><span data-stu-id="94cf4-454">Example of a custom host name: https://MyReportServer/ReportServer</span></span>|
   |<span data-ttu-id="94cf4-455">虚拟目录</span><span class="sxs-lookup"><span data-stu-id="94cf4-455">Virtual directory</span></span>   |<span data-ttu-id="94cf4-456">管理和监视网站的虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="94cf4-456">Virtual directory of the Administration and Monitoring Website.</span></span> <span data-ttu-id="94cf4-457">此名称对应于服务器上网站的物理目录，并附加到网站的主机名。</span><span class="sxs-lookup"><span data-stu-id="94cf4-457">This name corresponds to the website’s physical directory on the server and is appended to the website’s host name.</span></span> <span data-ttu-id="94cf4-458">例如：</span><span class="sxs-lookup"><span data-stu-id="94cf4-458">For example:</span></span> <br /><span data-ttu-id="94cf4-459">http （s）：// *\<host name\>* ： *\<port\>* /HelpDesk/</span><span class="sxs-lookup"><span data-stu-id="94cf4-459">http(s)://*\<host name\>*:*\<port\>*/HelpDesk/</span></span> <br /><span data-ttu-id="94cf4-460">如果不指定虚拟目录，将使用值帮助台。</span><span class="sxs-lookup"><span data-stu-id="94cf4-460">If you do not specify a virtual directory, the value HelpDesk will be used.</span></span>     |

9. <span data-ttu-id="94cf4-461">使用以下说明在向导中输入字段值以配置自助服务门户。</span><span class="sxs-lookup"><span data-stu-id="94cf4-461">Use the following description to enter the field values in the wizard to configure the Self-Service Portal.</span></span>

   |<span data-ttu-id="94cf4-462">字段</span><span class="sxs-lookup"><span data-stu-id="94cf4-462">Field</span></span>   |<span data-ttu-id="94cf4-463">描述</span><span class="sxs-lookup"><span data-stu-id="94cf4-463">Description</span></span>|
   |----|----|
   |<span data-ttu-id="94cf4-464">虚拟目录</span><span class="sxs-lookup"><span data-stu-id="94cf4-464">Virtual directory</span></span>   |<span data-ttu-id="94cf4-465">Web 应用程序的虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="94cf4-465">Virtual directory of the web application.</span></span> <span data-ttu-id="94cf4-466">此名称对应于服务器上网站的物理目录，并附加到网站的主机名。</span><span class="sxs-lookup"><span data-stu-id="94cf4-466">This name corresponds to the website’s physical directory on the server and is appended to the website’s host name.</span></span> <span data-ttu-id="94cf4-467">例如：</span><span class="sxs-lookup"><span data-stu-id="94cf4-467">For example:</span></span><br /><span data-ttu-id="94cf4-468">http （s）：// *\<host name\>* ： *\<port\>* /SelfService/</span><span class="sxs-lookup"><span data-stu-id="94cf4-468">http(s)://*\<host name\>*:*\<port\>*/SelfService/</span></span><br /> <span data-ttu-id="94cf4-469">如果不指定虚拟目录，将使用值 "SelfService"。</span><span class="sxs-lookup"><span data-stu-id="94cf4-469">If you do not specify a virtual directory, the value "SelfService" will be used.</span></span>|

10. <span data-ttu-id="94cf4-470">完成输入后，选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="94cf4-470">When you finish your entries, select **Next**.</span></span> <span data-ttu-id="94cf4-471">向导检查是否满足 web 应用程序的所有先决条件。</span><span class="sxs-lookup"><span data-stu-id="94cf4-471">The wizard checks that all prerequisites for the web applications are met.</span></span>

11. <span data-ttu-id="94cf4-472">选择 "**下一步**" 继续。</span><span class="sxs-lookup"><span data-stu-id="94cf4-472">Select **Next** to continue.</span></span>

12. <span data-ttu-id="94cf4-473">在 "**摘要**" 页面上，查看将添加的功能。</span><span class="sxs-lookup"><span data-stu-id="94cf4-473">On the **Summary** page, review the features that will be added.</span></span>

13. <span data-ttu-id="94cf4-474">选择 "**添加**" 以将 web 应用程序添加到服务器，然后选择 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="94cf4-474">Select **Add** to add the web applications to the server, and then select **Close**.</span></span>

## <span data-ttu-id="94cf4-475">在安装 MBAM 2.5 server 软件后自定义和验证步骤</span><span class="sxs-lookup"><span data-stu-id="94cf4-475">Customizing and validating steps after installing MBAM 2.5 server software</span></span>

### <span data-ttu-id="94cf4-476">步骤9：为你的组织自定义自服务器门户</span><span class="sxs-lookup"><span data-stu-id="94cf4-476">Step 9: Customizing the self-server portal for your organization</span></span>

<span data-ttu-id="94cf4-477">若要通过添加自定义声明文本、公司名称、指向详细信息的指针自定义自助服务门户，请参阅[自定义组织的自助服务门户](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/customizing-the-self-service-portal-for-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="94cf4-477">To customize the Self-Service Portal by adding custom notice text, your company name, pointers to more information, and so on, see [Customizing the Self-Service Portal for Your Organization](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/customizing-the-self-service-portal-for-your-organization).</span></span>
 
### <span data-ttu-id="94cf4-478">步骤10：在客户端计算机无法访问 CDN 时配置自助服务门户</span><span class="sxs-lookup"><span data-stu-id="94cf4-478">Step 10: Configure the self-server portal if client computers cannot access the CDN</span></span> 

<span data-ttu-id="94cf4-479">确定客户端计算机是否有权访问 Microsoft AJAX 内容交付网络（CDN）。</span><span class="sxs-lookup"><span data-stu-id="94cf4-479">Determine whether your client computers have access to the Microsoft AJAX Content Delivery Network (CDN).</span></span> <span data-ttu-id="94cf4-480">CDN 为自助服务门户提供对某些 JavaScript 文件所需的访问权限。</span><span class="sxs-lookup"><span data-stu-id="94cf4-480">The CDN gives the Self-Service Portal the access it requires to certain JavaScript files.</span></span> <span data-ttu-id="94cf4-481">如果在客户端计算机无法访问 CDN 时未配置自助服务门户，则仅显示公司名称和登录用户所使用的帐户。</span><span class="sxs-lookup"><span data-stu-id="94cf4-481">If you don’t configure the Self-Service Portal when client computers cannot access the CDN, only the company name and the account under which the user signed in will be displayed.</span></span> <span data-ttu-id="94cf4-482">将不会显示任何错误消息。</span><span class="sxs-lookup"><span data-stu-id="94cf4-482">No error message will be shown.</span></span>

<span data-ttu-id="94cf4-483">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="94cf4-483">Do one of the following:</span></span>

* <span data-ttu-id="94cf4-484">如果你的客户端计算机有权访问 CDN，请执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="94cf4-484">If your client computers have access to the CDN, do nothing.</span></span> <span data-ttu-id="94cf4-485">您的自助服务门户配置已完成。</span><span class="sxs-lookup"><span data-stu-id="94cf4-485">Your Self-Service Portal configuration is complete.</span></span>

* <span data-ttu-id="94cf4-486">如果客户端计算机不具有 CDN 的访问权限，请按照在[客户端计算机无法访问 Microsoft 内容传递网络时如何配置自助服务门户](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/how-to-configure-the-self-service-portal-when-client-computers-cannot-access-the-microsoft-content-delivery-network)中的步骤进行操作。</span><span class="sxs-lookup"><span data-stu-id="94cf4-486">If your client computers do not have access to the CDN, follow the steps in [How to Configure the Self-Service Portal When Client Computers Cannot Access the Microsoft Content Delivery Network](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/how-to-configure-the-self-service-portal-when-client-computers-cannot-access-the-microsoft-content-delivery-network).</span></span>

### <span data-ttu-id="94cf4-487">步骤11：验证 MBAM 2.5 服务器功能配置</span><span class="sxs-lookup"><span data-stu-id="94cf4-487">Step 11: Validate the MBAM 2.5 server feature configuration</span></span> 

<span data-ttu-id="94cf4-488">若要验证 MBAM 服务器部署以使用独立拓扑，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="94cf4-488">To validate your MBAM Server deployment to use the standalone topology, follow these steps.</span></span>

1. <span data-ttu-id="94cf4-489">在部署了 MBAM 功能的每台服务器上，选择 **"控制面板**  >  **程序**" 程序  >  **和功能**。</span><span class="sxs-lookup"><span data-stu-id="94cf4-489">On each server on which an MBAM feature is deployed, select **Control Panel** > **Programs** > **Programs and Features**.</span></span> <span data-ttu-id="94cf4-490">验证 "**程序和功能**" 列表中是否显示 " **Microsoft BitLocker 管理和监视**"。</span><span class="sxs-lookup"><span data-stu-id="94cf4-490">Verify that **Microsoft BitLocker Administration and Monitoring** appears in the **Programs and Features** list.</span></span>
   > [!Note]
   > <span data-ttu-id="94cf4-491">若要执行验证，你必须使用在每台服务器上具有本地计算机管理凭据的域帐户。</span><span class="sxs-lookup"><span data-stu-id="94cf4-491">To perform the validation, you must use a domain account that has local computer administrative credentials on each server.</span></span>

2. <span data-ttu-id="94cf4-492">在配置了恢复数据库的服务器上，打开 SQL Server Management Studio，并验证是否配置了**MBAM 恢复和硬件**数据库。</span><span class="sxs-lookup"><span data-stu-id="94cf4-492">On the server on which the Recovery Database is configured, open SQL Server Management Studio, and verify that the **MBAM Recovery and Hardware** database is configured.</span></span>

3. <span data-ttu-id="94cf4-493">在配置合规性和审核数据库的服务器 om 上，打开 SQL Server Management Studio，并验证是否配置了 MBAM 合规性状态数据库。</span><span class="sxs-lookup"><span data-stu-id="94cf4-493">On the server om which the Compliance and Audit Database is configured, open SQL Server Management Studio, and verify that the MBAM Compliance Status Database is configured.</span></span>

4. <span data-ttu-id="94cf4-494">在配置了 "报表" 功能的 "服务器 onm" 上，使用 "管理凭据" 打开 web 浏览器，然后浏览到 SQL Server Reporting Services 网站的主页。</span><span class="sxs-lookup"><span data-stu-id="94cf4-494">On the server onm which the Reports feature is configured, open a web browser by using administrative credentials, and browse to the homepage of the SQL Server Reporting Services site.</span></span>
   
   <span data-ttu-id="94cf4-495">SQL Server Reporting Services 网站实例的默认主页位置如下所示： http （s）：// *\<MBAM Reports Server Name\>* ： *\<port\>* /Reports.aspx</span><span class="sxs-lookup"><span data-stu-id="94cf4-495">The default homepage location of a SQL Server Reporting Services site instance is as follows: http(s)://*\<MBAM Reports Server Name\>*:*\<port\>*/Reports.aspx</span></span>
   
   <span data-ttu-id="94cf4-496">若要查找实际 URL，请使用 Reporting Services 配置管理器工具，然后选择在安装过程中指定的实例。</span><span class="sxs-lookup"><span data-stu-id="94cf4-496">To find the actual URL, use the Reporting Services Configuration Manager tool, and select the instances that you specified during setup.</span></span>
   
5. <span data-ttu-id="94cf4-497">验证名为 Microsoft BitLocker 管理和监视的报表文件夹是否包含名为 MaltaDataSource 的数据源。</span><span class="sxs-lookup"><span data-stu-id="94cf4-497">Verify that a reports folder that is named Microsoft BitLocker Administration and Monitoring contains a data source that is named MaltaDataSource.</span></span> <span data-ttu-id="94cf4-498">此数据源包含具有表示语言区域设置的名称的文件夹（例如，en-us）。</span><span class="sxs-lookup"><span data-stu-id="94cf4-498">This data source contains folders that have names that represent language locales (for example, en-us).</span></span> <span data-ttu-id="94cf4-499">报表位于 "语言" 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="94cf4-499">The reports are in the language folders.</span></span>

   > [!Note]
   > <span data-ttu-id="94cf4-500">如果 SQL Server Reporting Services （SSRS）配置为命名实例，则 URL 应类似于以下内容： http （s）：// \<MBAM Reports Server Name\> ： \<port\> /Reports_</span><span class="sxs-lookup"><span data-stu-id="94cf4-500">If SQL Server Reporting Services (SSRS) was configured as a named instance, the URL should resemble the following: http(s)://\<MBAM Reports Server Name\>:\<port\>/Reports_</span></span>\<SSRS Instance Name\>
   >
   > <span data-ttu-id="94cf4-501">如果未将 SSRS 配置为使用安全套接字层（SSL），则在安装 MBAM 服务器时，报表的 URL 将设置为 "HTTP"，而不是 "HTTPS"。</span><span class="sxs-lookup"><span data-stu-id="94cf4-501">If SSRS was not configured to use Secure Socket Layer (SSL), the URL for the reports will be set to "HTTP" instead of "HTTPS" when you install the MBAM server.</span></span> <span data-ttu-id="94cf4-502">如果您转到 "管理和监视" 网站（也称为 "帮助台"）并选择报表，则会收到以下消息： "仅显示安全内容"。</span><span class="sxs-lookup"><span data-stu-id="94cf4-502">If you then go to the Administration and Monitoring Website (also known as Helpdesk) and select a report, you receive the following message: "Only Secure Content is Displayed."</span></span> <span data-ttu-id="94cf4-503">若要显示报表，请选择 "**显示所有内容**"。</span><span class="sxs-lookup"><span data-stu-id="94cf4-503">To show the report, select **Show All Content**.</span></span>

6. <span data-ttu-id="94cf4-504">在配置了 "管理和监视网站" 功能的服务器上，运行 "服务器管理器"，浏览到 "**角色**"，然后选择 " **Web 服务器（iis）**  >  **Internet 信息服务（iis）** 管理器"。</span><span class="sxs-lookup"><span data-stu-id="94cf4-504">On the server on which the Administration and Monitoring Website feature is configured, run Server Manager, browse to **Roles**, and then select **Web Server (IIS)** > **Internet Information Services (IIS)** Manager.</span></span>

7. <span data-ttu-id="94cf4-505">在 "**连接**" 中，浏览到 "网站"， \<computer name\> 然后选择 "**网站**  >  **Microsoft BitLocker 管理和监视**"。</span><span class="sxs-lookup"><span data-stu-id="94cf4-505">In **Connections**, browse to \<computer name\> and then select **Sites** > **Microsoft BitLocker Administration and Monitoring**.</span></span> <span data-ttu-id="94cf4-506">验证是否列出以下内容：</span><span class="sxs-lookup"><span data-stu-id="94cf4-506">Verify that the following are listed:</span></span>

   * <span data-ttu-id="94cf4-507">MBAMAdministrationService</span><span class="sxs-lookup"><span data-stu-id="94cf4-507">MBAMAdministrationService</span></span>
   * <span data-ttu-id="94cf4-508">MBAMComplianceStatusService</span><span class="sxs-lookup"><span data-stu-id="94cf4-508">MBAMComplianceStatusService</span></span>
   * <span data-ttu-id="94cf4-509">MBAMRecoveryAndHardwareService</span><span class="sxs-lookup"><span data-stu-id="94cf4-509">MBAMRecoveryAndHardwareService</span></span>

8. <span data-ttu-id="94cf4-510">在配置了管理和监视网站和自助服务门户的服务器上，通过使用管理凭据打开 web 浏览器。</span><span class="sxs-lookup"><span data-stu-id="94cf4-510">On the server on which the Administration and Monitoring Website and Self-Service Portal are configured, open a web browser by using administrative credentials.</span></span>

9. <span data-ttu-id="94cf4-511">浏览到以下网站，验证它们是否成功加载：</span><span class="sxs-lookup"><span data-stu-id="94cf4-511">Browse to the following websites to verify that they load successfully:</span></span>
   * <span data-ttu-id="94cf4-512">https （s）：// \<MBAM Administration Server Name\> ： \<port\> /HelpDesk/（确认导航和报告的每个链接）</span><span class="sxs-lookup"><span data-stu-id="94cf4-512">https(s)://\<MBAM Administration Server Name\>:\<port\>/HelpDesk/ (confirm each link for navigation and reports)</span></span>
   * <span data-ttu-id="94cf4-513">http （s）：// \<MBAM Administration Server Name\> ： \<port\> /SelfService/</span><span class="sxs-lookup"><span data-stu-id="94cf4-513">http(s)://\<MBAM Administration Server Name\>:\<port\>/SelfService/</span></span>

   > [!Note]
   > <span data-ttu-id="94cf4-514">假设您在没有网络加密的情况下在默认端口上配置了服务器功能。</span><span class="sxs-lookup"><span data-stu-id="94cf4-514">It is assumed that you configured the server features on the default port without network encryption.</span></span> <span data-ttu-id="94cf4-515">如果你在其他端口或虚拟目录上配置了服务器功能，请将 Url 更改为包含相应的端口。</span><span class="sxs-lookup"><span data-stu-id="94cf4-515">If you configured the server features on a different port or virtual directory, change the URLs to include the appropriate port.</span></span> <span data-ttu-id="94cf4-516">例如： http （s）：// \<host name\> ： \<port\> /HelpDesk/http： \<host name\> //： \<port\> / \<virtualdirectory\> /如果服务器功能配置为使用网络加密，请将 http://更改为 https://。</span><span class="sxs-lookup"><span data-stu-id="94cf4-516">For example: http(s)://\<host name\>:\<port\>/HelpDesk/ http(s)://\<host name\>:\<port\>/\<virtualdirectory\>/ If the server features were configured to use network encryption, change http:// to https://.</span></span>
   
10. <span data-ttu-id="94cf4-517">浏览到以下 web 服务以验证它们是否已成功加载。</span><span class="sxs-lookup"><span data-stu-id="94cf4-517">Browse to the following web services to verify that they load successfully.</span></span> <span data-ttu-id="94cf4-518">将打开一个页面，指示该服务正在运行。</span><span class="sxs-lookup"><span data-stu-id="94cf4-518">A page opens to indicate that the service is running.</span></span> <span data-ttu-id="94cf4-519">但是，该页面不显示元数据。</span><span class="sxs-lookup"><span data-stu-id="94cf4-519">However, the page displays no metadata.</span></span>

    * <span data-ttu-id="94cf4-520">http （s）：// \<MBAM Administration Server Name> ： \<port> /MBAMAdministrationService/AdministrationService.svc</span><span class="sxs-lookup"><span data-stu-id="94cf4-520">http(s)://\<MBAM Administration Server Name>:\<port>/MBAMAdministrationService/AdministrationService.svc</span></span>
    * <span data-ttu-id="94cf4-521">http （s）：// \<MBAM Administration Server Name> ： \<port> /MBAMUserSupportService/UserSupportService.svc</span><span class="sxs-lookup"><span data-stu-id="94cf4-521">http(s)://\<MBAM Administration Server Name>:\<port>/MBAMUserSupportService/UserSupportService.svc</span></span>
    * <span data-ttu-id="94cf4-522">http （s）：// \<MBAM Administration Server Name> ： \<port> /MBAMComplianceStatusService/StatusReportingService.svc</span><span class="sxs-lookup"><span data-stu-id="94cf4-522">http(s)://\<MBAM Administration Server Name>:\<port>/MBAMComplianceStatusService/StatusReportingService.svc</span></span>
    * <span data-ttu-id="94cf4-523">http （s）：// \<MBAM Administration Server Name> ： \<port> /MBAMRecoveryAndHardwareService/CoreService.svc</span><span class="sxs-lookup"><span data-stu-id="94cf4-523">http(s)://\<MBAM Administration Server Name>:\<port>/MBAMRecoveryAndHardwareService/CoreService.svc</span></span>

### <span data-ttu-id="94cf4-524">步骤12：配置 MBAM 组策略模板</span><span class="sxs-lookup"><span data-stu-id="94cf4-524">Step 12: Configure the MBAM Group policy templates</span></span>

<span data-ttu-id="94cf4-525">若要部署 MBAM，你必须设置用于定义 BitLocker 驱动器加密的 MBAM 实现设置的组策略设置。</span><span class="sxs-lookup"><span data-stu-id="94cf4-525">To deploy MBAM, you have to set Group Policy settings that define MBAM implementation settings for BitLocker Drive Encryption.</span></span> <span data-ttu-id="94cf4-526">若要完成此任务，必须将 MBAM 组策略模板复制到可以运行组策略管理控制台（GPMC）或高级组策略管理（AGPM）的服务器或工作站，然后编辑设置。</span><span class="sxs-lookup"><span data-stu-id="94cf4-526">To complete this task, you must copy the MBAM Group Policy templates to a server or workstation that can run Group Policy Management Console (GPMC) or Advanced Group Policy Management (AGPM), and then edit the settings.</span></span>

> [!Important]
> <span data-ttu-id="94cf4-527">不要更改 " **BitLocker 驱动器加密**" 节点中的组策略设置，否则 MBAM 将无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="94cf4-527">Do not change the Group Policy settings in the **BitLocker Drive Encryption** node or MBAM will not work correctly.</span></span> <span data-ttu-id="94cf4-528">在**MDOP MBAM （BitLocker Management）** 节点中配置组策略设置时，MBAM 会自动为你配置**BitLocker 驱动器加密**设置。</span><span class="sxs-lookup"><span data-stu-id="94cf4-528">When you configure the Group Policy settings in the **MDOP MBAM (BitLocker Management)** node, MBAM automatically configures the **BitLocker Drive Encryption** settings for you.</span></span>
 
#### <span data-ttu-id="94cf4-529">复制 MBAM 2.5 组策略模板</span><span class="sxs-lookup"><span data-stu-id="94cf4-529">Copying the MBAM 2.5 Group Policy templates</span></span>

<span data-ttu-id="94cf4-530">在安装 MBAM 客户端之前，必须将 MBAM 特定的组策略对象（Gpo）复制到管理工作站。</span><span class="sxs-lookup"><span data-stu-id="94cf4-530">Before you install the MBAM Client, you must copy MBAM-specific Group Policy Objects (GPOs) to the management workstation.</span></span> <span data-ttu-id="94cf4-531">这些 Gpo 定义了适用于 BitLocker 的 MBAM 实现设置。</span><span class="sxs-lookup"><span data-stu-id="94cf4-531">These GPOs define MBAM implementation settings for BitLocker.</span></span> <span data-ttu-id="94cf4-532">你可以将组策略模板复制到属于受支持的基于 Windows 的服务器或客户端计算机的任何服务器或工作站，并且可以运行组策略管理控制台（GPMC）或高级组策略管理（AGPM）。</span><span class="sxs-lookup"><span data-stu-id="94cf4-532">You can copy the Group Policy templates to any server or workstation that is a supported Windows-based server or client computer and that can run the Group Policy Management Console (GPMC) or Advanced Group Policy Management (AGPM).</span></span>

<span data-ttu-id="94cf4-533">有关详细信息，请参阅[复制 MBAM 2.5 组策略模板](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/copying-the-mbam-25-group-policy-templates)。</span><span class="sxs-lookup"><span data-stu-id="94cf4-533">For more information, see [Copying the MBAM 2.5 Group Policy Templates](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/copying-the-mbam-25-group-policy-templates).</span></span>
 
#### <span data-ttu-id="94cf4-534">编辑 MBAM 2.5 GPO 设置</span><span class="sxs-lookup"><span data-stu-id="94cf4-534">Editing MBAM 2.5 GPO settings</span></span>

<span data-ttu-id="94cf4-535">创建必要的 Gpo 后，必须将 MBAM 组策略设置部署到你的组织的客户端计算机。</span><span class="sxs-lookup"><span data-stu-id="94cf4-535">After you create the necessary GPOs, you must deploy the MBAM Group Policy settings to your organization’s client computers.</span></span> <span data-ttu-id="94cf4-536">若要查看和创建 Gpo，必须安装组策略管理控制台（GPMC）或高级组策略管理（AGPM）。</span><span class="sxs-lookup"><span data-stu-id="94cf4-536">To view and create GPOs, you must have Group Policy Management Console (GPMC) or Advanced Group Policy Management (AGPM) installed.</span></span>

<span data-ttu-id="94cf4-537">有关详细信息，请参阅[编辑 MBAM 2.5 组策略设置](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/editing-the-mbam-25-group-policy-settings)和[规划 MBAM 2.5 组策略要求](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/planning-for-mbam-25-group-policy-requirements)。</span><span class="sxs-lookup"><span data-stu-id="94cf4-537">For more information, see [Editing the MBAM 2.5 Group Policy Settings](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/editing-the-mbam-25-group-policy-settings) and [Planning for MBAM 2.5 Group Policy Requirements](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/planning-for-mbam-25-group-policy-requirements).</span></span>
 
### <span data-ttu-id="94cf4-538">步骤13：部署 MBAM 2.5 客户端</span><span class="sxs-lookup"><span data-stu-id="94cf4-538">Step 13: Deploying the MBAM 2.5 Client</span></span>

<span data-ttu-id="94cf4-539">根据你部署 Microsoft BitLocker 管理和监视客户端软件的时间，你可以在用户接收计算机之前或者通过配置组策略并使用企业软件部署系统部署 MBAM 客户端软件，在你的组织中的计算机上启用 BitLocker。</span><span class="sxs-lookup"><span data-stu-id="94cf4-539">Depending on when you deploy the Microsoft BitLocker Administration and Monitoring Client software, you can enable BitLocker on a computer in your organization either before the user receives the computer or afterward by configuring Group Policy and deploying the MBAM Client software by using an enterprise software deployment system.</span></span>
 
#### <span data-ttu-id="94cf4-540">将 MBAM 客户端部署到台式计算机或便携式计算机</span><span class="sxs-lookup"><span data-stu-id="94cf4-540">Deploy the MBAM Client to desktop or portable computers</span></span>

<span data-ttu-id="94cf4-541">配置组策略设置后，你可以使用企业软件部署系统产品（如 Microsoft System Center 2012 Configuration Manager 或 Active Directory 域服务（AD DS））将 MBAM 客户端安装 Windows Installer 文件部署到目标计算机。</span><span class="sxs-lookup"><span data-stu-id="94cf4-541">After you configure Group Policy settings, you can use an enterprise software deployment system product such as Microsoft System Center 2012 Configuration Manager or Active Directory Domain Services (AD DS) to deploy the MBAM client installation Windows Installer files to target computers.</span></span> <span data-ttu-id="94cf4-542">你可以使用32位或64位 MbamClientSetup.exe 文件或32位或64位 MBAMClient.msi 文件。</span><span class="sxs-lookup"><span data-stu-id="94cf4-542">You can use either the 32-bit or 64-bit MbamClientSetup.exe files or the 32-bit or 64-bit MBAMClient.msi files.</span></span> <span data-ttu-id="94cf4-543">这些软件与 MBAM 客户端软件一起提供。</span><span class="sxs-lookup"><span data-stu-id="94cf4-543">These are provided together with the MBAM Client software.</span></span>

<span data-ttu-id="94cf4-544">有关详细信息，请参阅[如何将 MBAM 客户端部署到台式计算机或膝上型计算机](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/how-to-deploy-the-mbam-client-to-desktop-or-laptop-computers-mbam-25)。</span><span class="sxs-lookup"><span data-stu-id="94cf4-544">For more information, see [How to Deploy the MBAM Client to Desktop or Laptop Computers](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/how-to-deploy-the-mbam-client-to-desktop-or-laptop-computers-mbam-25).</span></span>
 
#### <span data-ttu-id="94cf4-545">将 MBAM 客户端部署为 Windows 部署的一部分</span><span class="sxs-lookup"><span data-stu-id="94cf4-545">Deploy the MBAM Client as part of a Windows deployment</span></span>

<span data-ttu-id="94cf4-546">在要集中接收和配置计算机的组织中，可以安装 MBAM 客户端以在每台计算机上管理 BitLocker 驱动器加密，然后再向其中写入任何用户数据。</span><span class="sxs-lookup"><span data-stu-id="94cf4-546">In organizations in which computers are received and configured centrally, you can install the MBAM Client to manage BitLocker Drive Encryption on each computer before any user data is written to it.</span></span> <span data-ttu-id="94cf4-547">此过程的好处是，每台计算机都与 BitLocker 兼容。</span><span class="sxs-lookup"><span data-stu-id="94cf4-547">The benefit of this process is that every computer is then BitLocker-compliant.</span></span> <span data-ttu-id="94cf4-548">此方法不依赖于用户操作，因为管理员已加密计算机。</span><span class="sxs-lookup"><span data-stu-id="94cf4-548">This method does not rely on user action because the administrator has already encrypted the computer.</span></span> <span data-ttu-id="94cf4-549">此方案的一个关键假设是组织的策略是在计算机交付给用户之前安装企业 Windows 映像。</span><span class="sxs-lookup"><span data-stu-id="94cf4-549">A key assumption for this scenario is that the policy of the organization is to install a corporate Windows image before the computer is delivered to the user.</span></span> <span data-ttu-id="94cf4-550">如果将组策略设置配置为需要 PIN 码，则会在用户收到策略后提示用户设置 PIN。</span><span class="sxs-lookup"><span data-stu-id="94cf4-550">If the Group Policy settings are configured to require a PIN, users are prompted to set a PIN after they receive the policy.</span></span>

<span data-ttu-id="94cf4-551">有关详细信息，请参阅[如何在 Windows 部署中部署 MBAM 客户端](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/how-to-enable-bitlocker-by-using-mbam-as-part-of-a-windows-deploymentmbam-25)。</span><span class="sxs-lookup"><span data-stu-id="94cf4-551">For more information, see [How to Deploy the MBAM Client as Part of a Windows Deployment](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/how-to-enable-bitlocker-by-using-mbam-as-part-of-a-windows-deploymentmbam-25).</span></span>
 
#### <span data-ttu-id="94cf4-552">如何使用命令行部署 MBAM 客户端</span><span class="sxs-lookup"><span data-stu-id="94cf4-552">How to deploy the MBAM Client by using a command line</span></span>

<span data-ttu-id="94cf4-553">有关详细信息，请参阅[如何使用命令行部署 MBAM 客户端](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/how-to-deploy-the-mbam-client-by-using-a-command-line)。</span><span class="sxs-lookup"><span data-stu-id="94cf4-553">For more information see [How to Deploy the MBAM Client by Using a Command Line](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/how-to-deploy-the-mbam-client-by-using-a-command-line).</span></span>

#### <span data-ttu-id="94cf4-554">客户端部署后</span><span class="sxs-lookup"><span data-stu-id="94cf4-554">Post-deployment of clients</span></span>

<span data-ttu-id="94cf4-555">现在，你已完成部署活动，你应该查看以下日志并确定客户是否已成功报告到 MBAM 数据库。</span><span class="sxs-lookup"><span data-stu-id="94cf4-555">Now that you have finished the deployment activity, you should review the following logs and determine whether the clients are reporting successfully to the MBAM database.</span></span>

## <span data-ttu-id="94cf4-556">常见问题</span><span class="sxs-lookup"><span data-stu-id="94cf4-556">FAQ</span></span>

### <span data-ttu-id="94cf4-557">如何创建负载平衡 IIS 服务器</span><span class="sxs-lookup"><span data-stu-id="94cf4-557">How to create a Load balanced IIS servers</span></span>

* <span data-ttu-id="94cf4-558">SPN 必须仅注册为友好名称（例如： bitlocker.corp.net），并且不能注册到单独的 IIS 服务器。</span><span class="sxs-lookup"><span data-stu-id="94cf4-558">SPN must be registered only to the friendly name (for example: bitlocker.corp.net), and must not be registered to individual IIS servers.</span></span>

* <span data-ttu-id="94cf4-559">如果使用了证书，则证书必须将 FQDN 和 NetBIOS 名称输入到 "负载平衡" 组中所有 IIS 服务器的 "**主题备用名称**" 字段中，也必须具有友好名称（例如： bitlocker.corp.net）。</span><span class="sxs-lookup"><span data-stu-id="94cf4-559">If a certificate is used, the certificate must have both FQDN and NetBIOS names entered into the **Subject Alternative Name** field for all IIS servers in the load balance group and also as the Friendly Name (for example: bitlocker.corp.net).</span></span> <span data-ttu-id="94cf4-560">否则，当你浏览负载平衡地址时，该证书将报告为浏览器不受信任。</span><span class="sxs-lookup"><span data-stu-id="94cf4-560">Otherwise, the certificate will be reported as not trusted by the browser when you browse load-balanced addresses.</span></span>

<span data-ttu-id="94cf4-561">有关详细信息，请参阅[IIS 网络负载平衡](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/planning-for-mbam-25-high-availability#a-href-idbkmk-load-balanceaiis-network-load-balancing)和[注册应用程序池帐户的 spn](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/planning-how-to-secure-the-mbam-websites#registering-spns-for-the-application-pool-account)。</span><span class="sxs-lookup"><span data-stu-id="94cf4-561">For more information, see [IIS Network Load Balancing](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/planning-for-mbam-25-high-availability#a-href-idbkmk-load-balanceaiis-network-load-balancing) and [Registering SPNs for the application pool account](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/planning-how-to-secure-the-mbam-websites#registering-spns-for-the-application-pool-account).</span></span>

### <span data-ttu-id="94cf4-562">如何配置证书</span><span class="sxs-lookup"><span data-stu-id="94cf4-562">How to configure a certificate</span></span>

* <span data-ttu-id="94cf4-563">您必须拥有两个证书。</span><span class="sxs-lookup"><span data-stu-id="94cf4-563">You’ll have to have two certificates.</span></span> <span data-ttu-id="94cf4-564">一个证书用于 SQL server，另一个证书用于 IIS。</span><span class="sxs-lookup"><span data-stu-id="94cf4-564">One certificate is used for SQL server, and the other is used for IIS.</span></span> <span data-ttu-id="94cf4-565">必须先安装它们，然后才能开始 MBAM 安装。</span><span class="sxs-lookup"><span data-stu-id="94cf4-565">They must be installed before starting MBAM installation.</span></span>

* <span data-ttu-id="94cf4-566">我们建议你使用安装程序将证书添加到 IIS 配置，而不是手动编辑 web.config 文件。</span><span class="sxs-lookup"><span data-stu-id="94cf4-566">We recommend that you use the installer to add the certificate to the IIS configuration instead of manually editing the web.config file.</span></span>

* <span data-ttu-id="94cf4-567">如果证书上的 "颁发给" 字段与服务器名称不匹配，则 MBAM 配置器将不接受该证书。</span><span class="sxs-lookup"><span data-stu-id="94cf4-567">The certificate will not be accepted by the MBAM Configurator if the “Issued To” field on the certificate does not match the name of the server.</span></span> <span data-ttu-id="94cf4-568">在这种情况下，从 IIS 控制台临时创建自签名证书，然后在配置器中使用它。</span><span class="sxs-lookup"><span data-stu-id="94cf4-568">In this case, temporarily create a self-signed certificate from the IIS Console, and use it in the Configurator.</span></span> <span data-ttu-id="94cf4-569">这将使 nsure 为 SSL 和 HTTPS 安装 Web 应用。</span><span class="sxs-lookup"><span data-stu-id="94cf4-569">This will make nsure that the Web Apps are installed for SSL and HTTPS.</span></span> <span data-ttu-id="94cf4-570">之后，你可以将证书从 MBAM 网站的 IIS 绑定更改为一个证书。</span><span class="sxs-lookup"><span data-stu-id="94cf4-570">After that, you can change the certificate to one from IIS bindings for the MBAM Website.</span></span>

### <span data-ttu-id="94cf4-571">安装的 SQL 权限要求</span><span class="sxs-lookup"><span data-stu-id="94cf4-571">The SQL permissions requirement for installation</span></span>

<span data-ttu-id="94cf4-572">为 MBAM 应用程序池创建一个帐户，并仅为其授予 SecurityAdmin、Public 和 DBCreator 权限。</span><span class="sxs-lookup"><span data-stu-id="94cf4-572">Create an account for MBAM App Pool, and give it only SecurityAdmin, Public, and DBCreator permissions.</span></span>

<span data-ttu-id="94cf4-573">有关详细信息，请参阅[MBAM 数据库配置-最低权限](https://blogs.technet.microsoft.com/dubaisec/2016/02/02/mbam-database-configuration-minimum-permissions/)。</span><span class="sxs-lookup"><span data-stu-id="94cf4-573">See [MBAM Database configuration – minimum permissions](https://blogs.technet.microsoft.com/dubaisec/2016/02/02/mbam-database-configuration-minimum-permissions/) for more information.</span></span>

> [!Note]
> * <span data-ttu-id="94cf4-574">在某些情况下，初始安装和升级操作需要更多的权限。</span><span class="sxs-lookup"><span data-stu-id="94cf4-574">In some situations, more permissions are required for the initial installation and upgrade operations.</span></span>
> * <span data-ttu-id="94cf4-575">使用具有临时 SA 的帐户进行安装。</span><span class="sxs-lookup"><span data-stu-id="94cf4-575">Use an account that has temporary SA for the installation.</span></span>
> * <span data-ttu-id="94cf4-576">不要在没有足够权限来更改 SQL Server 的用户帐户上下文中启动配置器，因为这将导致安装错误。</span><span class="sxs-lookup"><span data-stu-id="94cf4-576">Do not start the Configurator in the context of a user account (Run As) that does not have enough permissions to make changes to SQL Server because this will cause installation errors.</span></span>
> * <span data-ttu-id="94cf4-577">您必须使用在 SQL Server 上拥有权限的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="94cf4-577">You must be logged on by using an account that has permissions on SQL Server.</span></span> <span data-ttu-id="94cf4-578">通过远程运行 MBAM 配置器，仅可创建或更新 SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="94cf4-578">Only SQL Server databases can be created or updated by running MBAM Configurator remotely.</span></span> <span data-ttu-id="94cf4-579">对于 SSRS 服务器，必须在本地安装 MBAM 并运行配置器以安装或更新 MBAM SSRS 报表。</span><span class="sxs-lookup"><span data-stu-id="94cf4-579">For SSRS server, you must install MBAM and run Configurator locally to install or update the MBAM SSRS reports.</span></span>

### <span data-ttu-id="94cf4-580">SPN 注册所需的权限</span><span class="sxs-lookup"><span data-stu-id="94cf4-580">The permission required for SPN Registration</span></span>

<span data-ttu-id="94cf4-581">用于 IIS portal 安装的帐户必须具有写 ServicePrincipalName 并写入验证的 SPN 权限。</span><span class="sxs-lookup"><span data-stu-id="94cf4-581">An account that's used for IIS portal installation must have Write ServicePrincipalName and Write Validated SPN permissions.</span></span> <span data-ttu-id="94cf4-582">如果没有这些权限，安装将返回一条警告消息，指出它无法注册 SPN。</span><span class="sxs-lookup"><span data-stu-id="94cf4-582">Without these permissions, the installation will return a warning message that states that it cannot register the SPN.</span></span>

> [!Note]
> <span data-ttu-id="94cf4-583">此时将收到此警告消息两次。</span><span class="sxs-lookup"><span data-stu-id="94cf4-583">You will this receive this warning message twice.</span></span> <span data-ttu-id="94cf4-584">这并不意味着 SPN 必须已注册两个对象。</span><span class="sxs-lookup"><span data-stu-id="94cf4-584">This does not mean that the SPN must have two objects registered to it.</span></span>

<span data-ttu-id="94cf4-585">有关详细信息，请参阅[MBAM 安装失败，并显示 "注册 SPN 延期" 错误消息](https://support.microsoft.com/help/2754138/)。</span><span class="sxs-lookup"><span data-stu-id="94cf4-585">For more information, see [MBAM Setup fails with “Register SPN Deferred” error message](https://support.microsoft.com/help/2754138/).</span></span>

### <span data-ttu-id="94cf4-586">是否必须将 ADMX 模板更新到最新版本？</span><span class="sxs-lookup"><span data-stu-id="94cf4-586">Did I have to update the ADMX templates to the latest version?</span></span>

<span data-ttu-id="94cf4-587">将 ADMX 模板更新到其最新版本之后，你将在 GPO 的 MBAM 根节点中看到多个 OS 选项。</span><span class="sxs-lookup"><span data-stu-id="94cf4-587">You'll see multiple OS options in the MBAM root node for GPO after you update the ADMX templates to their latest versions.</span></span> <span data-ttu-id="94cf4-588">例如，Windows 7、Windows 8.1 和 Windows 10 版本1511及更高版本。</span><span class="sxs-lookup"><span data-stu-id="94cf4-588">For example, Windows 7, Windows 8.1, and Windows 10, version 1511 and later versions.</span></span>

<span data-ttu-id="94cf4-589">有关如何更新 ADMX 模板的详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="94cf4-589">For more information about how to update the ADMX templates, see the following articles:</span></span>
* [<span data-ttu-id="94cf4-590">如何下载和部署 MDOP 组策略 (.admx) 模板</span><span class="sxs-lookup"><span data-stu-id="94cf4-590">How to Download and Deploy MDOP Group Policy (.admx) Templates</span></span>](https://docs.microsoft.com/microsoft-desktop-optimization-pack/solutions/how-to-download-and-deploy-mdop-group-policy--admx--templates)
* [<span data-ttu-id="94cf4-591">规划 MBAM 2.5 组策略要求</span><span class="sxs-lookup"><span data-stu-id="94cf4-591">Planning for MBAM 2.5 Group Policy Requirements</span></span>](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/planning-for-mbam-25-group-policy-requirements)
* [<span data-ttu-id="94cf4-592">Microsoft 桌面优化包组策略管理模板</span><span class="sxs-lookup"><span data-stu-id="94cf4-592">Microsoft Desktop Optimization Pack Group Policy Administrative Templates</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=55531)
