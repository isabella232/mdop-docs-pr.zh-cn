---
title: 如何在分布式服务器上安装和配置 MBAM
description: 如何在分布式服务器上安装和配置 MBAM
author: dansimp
ms.assetid: 67b91e6b-ae2e-4e47-9ef2-6819aba95976
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 841b894430d14604f0fd923703708d7a3f588c07
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803492"
---
# <span data-ttu-id="cd232-103">如何在分布式服务器上安装和配置 MBAM</span><span class="sxs-lookup"><span data-stu-id="cd232-103">How to Install and Configure MBAM on Distributed Servers</span></span>


<span data-ttu-id="cd232-104">本主题中的过程介绍了如何在分布式服务器上的独立拓扑中安装 Microsoft BitLocker 管理和监视（MBAM）2.0。</span><span class="sxs-lookup"><span data-stu-id="cd232-104">The procedures in this topic describe how to install Microsoft BitLocker Administration and Monitoring (MBAM) 2.0 in the Stand-alone topology on distributed servers.</span></span> <span data-ttu-id="cd232-105">若要查看推荐的体系结构的图表以及数据库和功能的说明，请参阅[部署 MBAM 2.0 服务器基础结构](deploying-the-mbam-20-server-infrastructure-mbam-2.md)。</span><span class="sxs-lookup"><span data-stu-id="cd232-105">To see a diagram of the recommended architecture, along with a description of the databases and features, see [Deploying the MBAM 2.0 Server Infrastructure](deploying-the-mbam-20-server-infrastructure-mbam-2.md).</span></span> <span data-ttu-id="cd232-106">若要通过 Configuration Manager 拓扑安装 Microsoft BitLocker 管理和监视，请参阅[通过 Configuration Manager 部署 MBAM](deploying-mbam-with-configuration-manager-mbam2.md)。</span><span class="sxs-lookup"><span data-stu-id="cd232-106">To install Microsoft BitLocker Administration and Monitoring with the Configuration Manager topology, see [Deploying MBAM with Configuration Manager](deploying-mbam-with-configuration-manager-mbam2.md).</span></span>

<span data-ttu-id="cd232-107">每个服务器功能都具有特定的先决条件。</span><span class="sxs-lookup"><span data-stu-id="cd232-107">Each server feature has certain prerequisites.</span></span> <span data-ttu-id="cd232-108">若要验证你是否满足先决条件和硬件和软件要求，请参阅[MBAM 2.0 部署先决条件](mbam-20-deployment-prerequisites-mbam-2.md)和[MBAM 2.0 支持的配置](mbam-20-supported-configurations-mbam-2.md)。</span><span class="sxs-lookup"><span data-stu-id="cd232-108">To verify that you have met the prerequisites and hardware and software requirements, see [MBAM 2.0 Deployment Prerequisites](mbam-20-deployment-prerequisites-mbam-2.md) and [MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md).</span></span> <span data-ttu-id="cd232-109">此外，某些功能需要你在安装过程中提供特定信息才能成功部署该功能。</span><span class="sxs-lookup"><span data-stu-id="cd232-109">In addition, some features require that you provide certain information during the installation process to successfully deploy the feature.</span></span> <span data-ttu-id="cd232-110">在开始 MBAM 部署之前，还应查看[规划 MBAM 2.0 服务器部署](planning-for-mbam-20-server-deployment-mbam-2.md)。</span><span class="sxs-lookup"><span data-stu-id="cd232-110">You should also review [Planning for MBAM 2.0 Server Deployment](planning-for-mbam-20-server-deployment-mbam-2.md) before you start the MBAM deployment.</span></span>

**<span data-ttu-id="cd232-111">注意</span><span class="sxs-lookup"><span data-stu-id="cd232-111">Note</span></span>**  
<span data-ttu-id="cd232-112">若要获取安装程序日志文件，必须使用 Msiexec 程序包和 **/l** &lt; location &gt; 选项来安装 MBAM。</span><span class="sxs-lookup"><span data-stu-id="cd232-112">To obtain the setup log files, you have to use the Msiexec package and the **/L** &lt;location&gt; option to install MBAM.</span></span> <span data-ttu-id="cd232-113">将在您指定的位置创建日志文件。</span><span class="sxs-lookup"><span data-stu-id="cd232-113">Log files are created in the location that you specify.</span></span>

<span data-ttu-id="cd232-114">其他安装日志文件在安装 MBAM 的用户服务器上的% temp% 文件夹中创建。</span><span class="sxs-lookup"><span data-stu-id="cd232-114">Additional setup log files are created in the %temp% folder on the server of the user who is installing MBAM.</span></span>



## <a href="" id="deploying-mbam-server-features-"></a><span data-ttu-id="cd232-115">部署 MBAM 服务器功能</span><span class="sxs-lookup"><span data-stu-id="cd232-115">Deploying MBAM Server Features</span></span>


<span data-ttu-id="cd232-116">以下步骤介绍了如何安装常规 MBAM 功能。</span><span class="sxs-lookup"><span data-stu-id="cd232-116">The following steps describe how to install general MBAM features.</span></span>

**<span data-ttu-id="cd232-117">启动 MBAM 服务器安装向导</span><span class="sxs-lookup"><span data-stu-id="cd232-117">To start the MBAM Server installation wizard</span></span>**

1.  <span data-ttu-id="cd232-118">在要安装 Microsoft BitLocker 管理和监视的服务器上，运行**MBAMSetup.exe**以启动 MBAM 安装向导。</span><span class="sxs-lookup"><span data-stu-id="cd232-118">On the server where you want to install Microsoft BitLocker Administration and Monitoring, run **MBAMSetup.exe** to start the MBAM installation wizard.</span></span>

2.  <span data-ttu-id="cd232-119">在 "**欢迎**" 页面上，选择 "**客户体验改善计划**"，然后单击 "**开始**"。</span><span class="sxs-lookup"><span data-stu-id="cd232-119">On the **Welcome** page, optionally select the **Customer Experience Improvement Program**, and then click **Start**.</span></span>

3.  <span data-ttu-id="cd232-120">阅读并接受 Microsoft 软件许可协议，然后单击 "**下一步**" 继续安装。</span><span class="sxs-lookup"><span data-stu-id="cd232-120">Read and accept the Microsoft Software License Agreement, and then click **Next** to continue the installation.</span></span>

4.  <span data-ttu-id="cd232-121">在 "**拓扑选择**" 页面上，选择**独立**拓扑，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="cd232-121">On the **Topology Selection** page, select the **Stand-alone** topology, and then click **Next**.</span></span>

    **<span data-ttu-id="cd232-122">注意</span><span class="sxs-lookup"><span data-stu-id="cd232-122">Note</span></span>**  
    <span data-ttu-id="cd232-123">如果要通过 Configuration Manager 集成拓扑安装 MBAM，请参阅[通过 Configuration Manager 部署 MBAM](deploying-mbam-with-configuration-manager-mbam2.md)。</span><span class="sxs-lookup"><span data-stu-id="cd232-123">If you want to install MBAM with the Configuration Manager integrated topology, see [Deploying MBAM with Configuration Manager](deploying-mbam-with-configuration-manager-mbam2.md).</span></span>



5.  <span data-ttu-id="cd232-124">选择要安装的功能。</span><span class="sxs-lookup"><span data-stu-id="cd232-124">Select the features that you want to install.</span></span> <span data-ttu-id="cd232-125">默认情况下，将选择所有 MBAM 功能进行安装。</span><span class="sxs-lookup"><span data-stu-id="cd232-125">By default, all MBAM features are selected for installation.</span></span> <span data-ttu-id="cd232-126">清除要在别处安装的功能。</span><span class="sxs-lookup"><span data-stu-id="cd232-126">Clear the features that you want to install elsewhere.</span></span> <span data-ttu-id="cd232-127">将在同一台计算机上安装的功能必须同时安装。</span><span class="sxs-lookup"><span data-stu-id="cd232-127">Features that will be installed on the same computer must be installed together at the same time.</span></span> <span data-ttu-id="cd232-128">必须按以下顺序安装 MBAM 功能：</span><span class="sxs-lookup"><span data-stu-id="cd232-128">You must install MBAM features in the following order:</span></span>

    -   <span data-ttu-id="cd232-129">恢复数据库</span><span class="sxs-lookup"><span data-stu-id="cd232-129">Recovery Database</span></span>

    -   <span data-ttu-id="cd232-130">合规性和审核数据库</span><span class="sxs-lookup"><span data-stu-id="cd232-130">Compliance and Audit Database</span></span>

    -   <span data-ttu-id="cd232-131">合规性和审核报告</span><span class="sxs-lookup"><span data-stu-id="cd232-131">Compliance and Audit Reports</span></span>

    -   <span data-ttu-id="cd232-132">自助服务门户</span><span class="sxs-lookup"><span data-stu-id="cd232-132">Self-Service Portal</span></span>

    -   <span data-ttu-id="cd232-133">管理和监视服务器</span><span class="sxs-lookup"><span data-stu-id="cd232-133">Administration and Monitoring Server</span></span>

    -   <span data-ttu-id="cd232-134">MBAM 组策略模板</span><span class="sxs-lookup"><span data-stu-id="cd232-134">MBAM Group Policy template</span></span>

    **<span data-ttu-id="cd232-135">注意</span><span class="sxs-lookup"><span data-stu-id="cd232-135">Note</span></span>**  
    <span data-ttu-id="cd232-136">安装向导将检查安装的先决条件，并显示缺少的必备条件。</span><span class="sxs-lookup"><span data-stu-id="cd232-136">The installation wizard checks the prerequisites for your installation and displays the prerequisites that are missing.</span></span> <span data-ttu-id="cd232-137">如果满足所有先决条件，安装将继续。</span><span class="sxs-lookup"><span data-stu-id="cd232-137">If all of the prerequisites are met, the installation continues.</span></span> <span data-ttu-id="cd232-138">如果检测到缺少先决条件，则必须解决缺少的先决条件，然后再次单击 "**检查必备项**"。</span><span class="sxs-lookup"><span data-stu-id="cd232-138">If a missing prerequisite is detected, you have to resolve the missing prerequisites, and then click **Check prerequisites again**.</span></span> <span data-ttu-id="cd232-139">如果此时间满足所有先决条件，安装将继续。</span><span class="sxs-lookup"><span data-stu-id="cd232-139">If all prerequisites are met this time, the installation resumes.</span></span>



~~~
The MBAM Setup wizard displays installation pages for the features that you select. The following sections describe the installation procedures for each feature.

**Note**  
For the following instructions, it is assumed that each feature is to be installed on a separate server. If you install multiple features on a single server, you can change or eliminate some steps.
~~~



**<span data-ttu-id="cd232-140">安装恢复数据库</span><span class="sxs-lookup"><span data-stu-id="cd232-140">To install the Recovery Database</span></span>**

1.  <span data-ttu-id="cd232-141">在 "**配置恢复数据库**" 页面上，指定将运行 "管理和监视服务器" 功能的计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="cd232-141">On the **Configure the Recovery database** page, specify the names of the computers that will be running the Administration and Monitoring Server feature.</span></span> <span data-ttu-id="cd232-142">部署 "管理和监视服务器" 功能后，它将使用其域帐户连接到数据库。</span><span class="sxs-lookup"><span data-stu-id="cd232-142">After the Administration and Monitoring Server feature is deployed, it uses its domain account to connect to the database.</span></span>

2.  <span data-ttu-id="cd232-143">单击**下一步**以继续。</span><span class="sxs-lookup"><span data-stu-id="cd232-143">Click **Next** to continue.</span></span>

3.  <span data-ttu-id="cd232-144">指定要存储恢复数据的 SQL Server 实例名称和数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="cd232-144">Specify the SQL Server instance name and the name of the database that will store the recovery data.</span></span> <span data-ttu-id="cd232-145">还必须指定数据库将位于的位置以及日志信息所在的位置。</span><span class="sxs-lookup"><span data-stu-id="cd232-145">You must also specify both where the database will be located and where the log information will be located.</span></span>

4.  <span data-ttu-id="cd232-146">单击 "**下一步**" 继续 MBAM 设置向导。</span><span class="sxs-lookup"><span data-stu-id="cd232-146">Click **Next** to continue with the MBAM Setup wizard.</span></span>

**<span data-ttu-id="cd232-147">安装合规性和审核数据库</span><span class="sxs-lookup"><span data-stu-id="cd232-147">To install the Compliance and Audit Database</span></span>**

1.  <span data-ttu-id="cd232-148">在 "**配置合规性和审核数据库**" 页面上，指定将用于访问报表的数据库的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="cd232-148">On the **Configure the Compliance and Audit Database** page, specify the user account that will be used to access the database for reports.</span></span>

2.  <span data-ttu-id="cd232-149">指定将运行管理和监视服务器以及合规性和审核报告的计算机的计算机名称。</span><span class="sxs-lookup"><span data-stu-id="cd232-149">Specify the computer names of the computers that will be running the Administration and Monitoring Server and the Compliance and Audit Reports.</span></span> <span data-ttu-id="cd232-150">在部署管理和监视以及合规性和审核报告服务器之后，他们将使用其域帐户连接到数据库。</span><span class="sxs-lookup"><span data-stu-id="cd232-150">After the Administration and Monitoring and the Compliance and Audit Reports Server are deployed, they use their domain accounts to connect to the databases.</span></span>

    **<span data-ttu-id="cd232-151">注意</span><span class="sxs-lookup"><span data-stu-id="cd232-151">Note</span></span>**  
    <span data-ttu-id="cd232-152">如果在没有合规性和审核报告功能的情况下安装合规性和审核数据库，则必须在合规性和审核数据库计算机上添加异常，才能在 Microsoft SQL Server 端口上启用入站流量。</span><span class="sxs-lookup"><span data-stu-id="cd232-152">If you are installing the Compliance and Audit Database without the Compliance and Audit Reports feature, you must add an exception on the Compliance and Audit Database computer to enable inbound traffic on the Microsoft SQL Server port.</span></span> <span data-ttu-id="cd232-153">默认端口号为1433。</span><span class="sxs-lookup"><span data-stu-id="cd232-153">The default port number is 1433.</span></span>



3.  <span data-ttu-id="cd232-154">指定 SQL Server 实例名称以及将存储合规性和审核数据的数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="cd232-154">Specify the SQL Server instance name and the name of the database that will store the compliance and audit data.</span></span> <span data-ttu-id="cd232-155">你还必须指定数据库和日志信息的位置。</span><span class="sxs-lookup"><span data-stu-id="cd232-155">You must also specify where the database and log information will be located.</span></span>

4.  <span data-ttu-id="cd232-156">单击 "**下一步**" 以继续 "Microsoft BitLocker 管理和监视设置向导"。</span><span class="sxs-lookup"><span data-stu-id="cd232-156">Click **Next** to continue with the Microsoft BitLocker Administration and Monitoring Setup wizard.</span></span>

**<span data-ttu-id="cd232-157">安装合规性和审核报告</span><span class="sxs-lookup"><span data-stu-id="cd232-157">To install the Compliance and Audit Reports</span></span>**

1.  <span data-ttu-id="cd232-158">在 "**配置合规性和审核报告**" 页面上，指定 &lt; &gt; 安装合规性和审核数据库的远程 SQL Server 实例名称（例如，服务器名）。</span><span class="sxs-lookup"><span data-stu-id="cd232-158">On the **Configure the Compliance and Audit Reports** page, specify the remote SQL Server instance name (for example, &lt;ServerName&gt;) where the Compliance and Audit Database was installed.</span></span>

    **<span data-ttu-id="cd232-159">注意</span><span class="sxs-lookup"><span data-stu-id="cd232-159">Note</span></span>**  
    <span data-ttu-id="cd232-160">如果在没有管理和监视服务器的情况下安装合规性和审核报告，则必须在合规性和审核报告计算机上添加例外，以便在报告服务器端口上启用入站流量（默认端口为80）。</span><span class="sxs-lookup"><span data-stu-id="cd232-160">If you are installing the Compliance and Audit Reports without the Administration and Monitoring Server, you must add an exception on the Compliance and Audit Report computer to enable inbound traffic on the Reporting Server port (the default port is 80).</span></span>



2.  <span data-ttu-id="cd232-161">指定合规性和审核数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="cd232-161">Specify the name of the Compliance and Audit Database.</span></span> <span data-ttu-id="cd232-162">默认情况下，数据库名称是 MBAM 合规性状态，但你可以在安装合规性和审核数据库时更改名称。</span><span class="sxs-lookup"><span data-stu-id="cd232-162">By default, the database name is MBAM Compliance Status, although you can change the name when you install the Compliance and Audit Database.</span></span>

3.  <span data-ttu-id="cd232-163">单击**下一步**以继续。</span><span class="sxs-lookup"><span data-stu-id="cd232-163">Click **Next** to continue.</span></span>

4.  <span data-ttu-id="cd232-164">选择将安装合规性和审核报告的 SQL Server Reporting Services 实例。</span><span class="sxs-lookup"><span data-stu-id="cd232-164">Select the instance of SQL Server Reporting Services where the Compliance and Audit Reports will be installed.</span></span> <span data-ttu-id="cd232-165">提供用于访问合规性和审核数据库的域用户帐户和密码。</span><span class="sxs-lookup"><span data-stu-id="cd232-165">Provide a domain user account and password to access the Compliance and Audit Database.</span></span> <span data-ttu-id="cd232-166">将此帐户的密码配置为永不过期。</span><span class="sxs-lookup"><span data-stu-id="cd232-166">Configure the password for this account to never expire.</span></span> <span data-ttu-id="cd232-167">用户帐户应该能够访问 MBAM Reports Users 组中可用的所有数据。</span><span class="sxs-lookup"><span data-stu-id="cd232-167">The user account should be able to access all data that is available to the MBAM Reports Users group.</span></span>

5.  <span data-ttu-id="cd232-168">单击 "**下一步**" 以继续 "Microsoft BitLocker 管理和监视设置向导"。</span><span class="sxs-lookup"><span data-stu-id="cd232-168">Click **Next** to continue with the Microsoft BitLocker Administration and Monitoring Setup wizard.</span></span>

**<span data-ttu-id="cd232-169">安装自助服务门户</span><span class="sxs-lookup"><span data-stu-id="cd232-169">To install the Self-Service Portal</span></span>**

1.  <span data-ttu-id="cd232-170">在 "**配置自助服务门户**" 页面上，您可以选择加密自助服务门户和管理和监视服务器之间的通信。</span><span class="sxs-lookup"><span data-stu-id="cd232-170">On the **Configure the Self-Service Portal** page, you can optionally encrypt the communication between the Self-Service Portal and the Administration and Monitoring servers.</span></span> <span data-ttu-id="cd232-171">如果你选择加密通信的选项，系统将提示你选择用于加密的证书颁发机构预配的证书。</span><span class="sxs-lookup"><span data-stu-id="cd232-171">If you choose the option to encrypt the communication, you are prompted to select the certification authority-provisioned certificate to use for encryption.</span></span>

2.  <span data-ttu-id="cd232-172">单击**下一步**以继续。</span><span class="sxs-lookup"><span data-stu-id="cd232-172">Click **Next** to continue.</span></span>

3.  <span data-ttu-id="cd232-173">指定安装合规性和审核数据库的 SQL Server 远程实例（例如， \* &lt; 服务器名 &gt; \*）。</span><span class="sxs-lookup"><span data-stu-id="cd232-173">Specify the remote instance of SQL Server (for example, *&lt;ServerName&gt;*) where the Compliance and Audit Database was installed.</span></span>

4.  <span data-ttu-id="cd232-174">指定合规性和审核数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="cd232-174">Specify the name of the Compliance and Audit Database.</span></span> <span data-ttu-id="cd232-175">默认情况下，数据库名称为 MBAM 合规性状态。</span><span class="sxs-lookup"><span data-stu-id="cd232-175">By default, the database name is MBAM Compliance Status.</span></span> <span data-ttu-id="cd232-176">但是，你可以在安装合规性和审核数据库时更改名称。</span><span class="sxs-lookup"><span data-stu-id="cd232-176">However, you can change the name when you install the Compliance and Audit Database.</span></span>

5.  <span data-ttu-id="cd232-177">单击**下一步**以继续。</span><span class="sxs-lookup"><span data-stu-id="cd232-177">Click **Next** to continue.</span></span>

6.  <span data-ttu-id="cd232-178">指定安装了恢复数据库的 SQL Server 远程实例（例如， \* &lt; 服务器名 &gt; \*）。</span><span class="sxs-lookup"><span data-stu-id="cd232-178">Specify the remote instance of SQL Server (for example, *&lt;ServerName&gt;*) where the Recovery Database was installed.</span></span>

7.  <span data-ttu-id="cd232-179">指定恢复数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="cd232-179">Specify the name of the Recovery Database.</span></span> <span data-ttu-id="cd232-180">默认情况下，数据库名称是**MBAM 恢复和硬件**。</span><span class="sxs-lookup"><span data-stu-id="cd232-180">By default, the database name is **MBAM Recovery and Hardware**.</span></span> <span data-ttu-id="cd232-181">但是，你可以在安装恢复数据库功能时更改名称。</span><span class="sxs-lookup"><span data-stu-id="cd232-181">However, you can change the name when you install the Recovery Database feature.</span></span>

8.  <span data-ttu-id="cd232-182">单击**下一步**以继续。</span><span class="sxs-lookup"><span data-stu-id="cd232-182">Click **Next** to continue.</span></span>

9.  <span data-ttu-id="cd232-183">输入**端口号**、**主机名**（可选）和 MBAM 管理和监视服务器的**安装路径**。</span><span class="sxs-lookup"><span data-stu-id="cd232-183">Enter the **Port Number**, the **Host Name** (optional), and the **Installation Path** for the MBAM Administration and Monitoring Server.</span></span>

    **<span data-ttu-id="cd232-184">注意</span><span class="sxs-lookup"><span data-stu-id="cd232-184">Note</span></span>**  
    <span data-ttu-id="cd232-185">你指定的端口号必须是管理和监视服务器上未使用的端口号，除非你指定唯一的主机标题名称。</span><span class="sxs-lookup"><span data-stu-id="cd232-185">The port number that you specify must be an unused port number on the Administration and Monitoring server unless you specify a unique host header name.</span></span> <span data-ttu-id="cd232-186">如果您使用的是 Windows 防火墙，则该端口将自动打开。</span><span class="sxs-lookup"><span data-stu-id="cd232-186">If you are using Windows Firewall, the port will be opened automatically.</span></span>



10. <span data-ttu-id="cd232-187">若要选择性地注册自助服务门户的服务主体名称（SPN），请选择 "**使用 Active Directory 注册此计算机的服务主体名称（spn）" （Windows 身份验证所需）**。</span><span class="sxs-lookup"><span data-stu-id="cd232-187">To optionally register a Service Principal Name (SPN) for the Self-Service Portal, select **Register this machine’s Service Principal Names (SPN) with Active Directory (Required for Windows Authentication)**.</span></span> <span data-ttu-id="cd232-188">如果选中此复选框，MBAM 安装程序将不会尝试注册现有的 Spn，你可以在 MBAM 安装之前或之后手动注册 SPN。</span><span class="sxs-lookup"><span data-stu-id="cd232-188">If you select this check box, MBAM Setup will not try to register the existing SPNs, and you can manually register the SPN before or after the MBAM installation.</span></span> <span data-ttu-id="cd232-189">有关手动注册 SPN 的说明，请参阅[手动 SPN 注册](https://go.microsoft.com/fwlink/?LinkId=286758)。</span><span class="sxs-lookup"><span data-stu-id="cd232-189">For instructions on registering the SPN manually, see [Manual SPN Registration](https://go.microsoft.com/fwlink/?LinkId=286758).</span></span>

11. <span data-ttu-id="cd232-190">单击 "**下一步**" 以继续 "Microsoft BitLocker 管理和监视设置向导"。</span><span class="sxs-lookup"><span data-stu-id="cd232-190">Click **Next** to continue with the Microsoft BitLocker Administration and Monitoring Setup wizard.</span></span>

12. <span data-ttu-id="cd232-191">指定是否使用 Microsoft 更新来帮助保护您的计算机安全，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="cd232-191">Specify whether to use Microsoft Updates to help keep your computer secure, and then click **Next**.</span></span>

13. <span data-ttu-id="cd232-192">在所选的 MBAM 功能信息完成后，即可使用设置向导启动 MBAM 安装。</span><span class="sxs-lookup"><span data-stu-id="cd232-192">When the selected MBAM feature information is completed, you are ready to start the MBAM installation by using the Setup wizard.</span></span> <span data-ttu-id="cd232-193">如果必须查看或更改安装设置，请单击 "**返回**" 以在向导中移动。</span><span class="sxs-lookup"><span data-stu-id="cd232-193">Click **Back** to move through the wizard if you have to review or change your installation settings.</span></span> <span data-ttu-id="cd232-194">单击 "**安装**" 以开始安装。</span><span class="sxs-lookup"><span data-stu-id="cd232-194">Click **Install** to start the installation.</span></span> <span data-ttu-id="cd232-195">单击 "**取消**" 退出向导。</span><span class="sxs-lookup"><span data-stu-id="cd232-195">Click **Cancel** to exit the wizard.</span></span> <span data-ttu-id="cd232-196">安装程序安装你选择的 MBAM 功能并通知你安装已完成。</span><span class="sxs-lookup"><span data-stu-id="cd232-196">Setup installs the MBAM features that you selected and notifies you that the installation is finished.</span></span>

14. <span data-ttu-id="cd232-197">单击 "**完成**" 退出向导。</span><span class="sxs-lookup"><span data-stu-id="cd232-197">Click **Finish** to exit the wizard.</span></span>

    **<span data-ttu-id="cd232-198">注意</span><span class="sxs-lookup"><span data-stu-id="cd232-198">Note</span></span>**  
    <span data-ttu-id="cd232-199">若要在安装自助服务门户之后配置它，请向自助服务门户提供公司名称和其他公司特定的信息，请参阅如何为[自助服务门户](how-to-brand-the-self-service-portal.md)提供有关说明的品牌。</span><span class="sxs-lookup"><span data-stu-id="cd232-199">To configure the Self-Service Portal after you installed it, brand the Self-Service Portal with your company name and other company-specific information, see [How to Brand the Self-Service Portal](how-to-brand-the-self-service-portal.md) for instructions.</span></span>



15. <span data-ttu-id="cd232-200">如果客户端计算机有权访问 Microsoft 内容交付网络（CDN），从而使自助服务门户对某些 JavaScript 文件所需的访问权限，则你已完成自助服务门户安装。</span><span class="sxs-lookup"><span data-stu-id="cd232-200">If the client computers have access to the Microsoft Content Delivery Network (CDN), which gives the Self-Service Portal the required access to certain JavaScript files, you are finished with the Self-Service Portal installation.</span></span> <span data-ttu-id="cd232-201">如果客户端计算机没有 Microsoft CDN 的访问权限，请完成下一节中的步骤，将自助服务门户配置为从易于访问的源中引用 JavaScript 文件。</span><span class="sxs-lookup"><span data-stu-id="cd232-201">If the client computers does not have access to the Microsoft CDN, complete the steps in the next section to configure the Self-Service Portal to reference the JavaScript files from an accessible source.</span></span>

**<span data-ttu-id="cd232-202">在最终用户无法访问 Microsoft Content 传递网络时配置自助服务门户</span><span class="sxs-lookup"><span data-stu-id="cd232-202">To configure the Self-Service Portal when end users cannot access the Microsoft Content Delivery Network</span></span>**

1. <span data-ttu-id="cd232-203">如果客户端计算机有权访问 Microsoft 内容交付网络（CDN），从而使自助服务门户对某些 JavaScript 文件所需的访问权限完成，则自助服务门户安装已完成。</span><span class="sxs-lookup"><span data-stu-id="cd232-203">If the client computers have access to the Microsoft Content Delivery Network (CDN), which gives the Self-Service Portal the required access to certain JavaScript files, the Self-Service Portal installation is completed.</span></span> <span data-ttu-id="cd232-204">如果客户端计算机没有 Microsoft CDN 的访问权限，请完成本部分中的其余步骤，将自助服务门户配置为从可访问的源中引用 JavaScript 文件。</span><span class="sxs-lookup"><span data-stu-id="cd232-204">If the client computers do not have access to the Microsoft CDN, complete the remaining steps in this section to configure the Self-Service Portal to reference the JavaScript files from an accessible source.</span></span>

2. <span data-ttu-id="cd232-205">从 Microsoft CDN 下载四个 JavaScript 文件：</span><span class="sxs-lookup"><span data-stu-id="cd232-205">Download the four JavaScript files from the Microsoft CDN:</span></span>

   -   <span data-ttu-id="cd232-206">jQuery-1.7.2.min.js-[https://go.microsoft.com/p/fwlink/?LinkID=271736](https://go.microsoft.com/fwlink/p/?LinkID=271736)</span><span class="sxs-lookup"><span data-stu-id="cd232-206">jQuery-1.7.2.min.js - [https://go.microsoft.com/p/fwlink/?LinkID=271736](https://go.microsoft.com/fwlink/p/?LinkID=271736)</span></span>

   -   <span data-ttu-id="cd232-207">MicrosoftAjax.js-[https://go.microsoft.com/p/fwlink/?LinkId=272283](https://go.microsoft.com/fwlink/p/?LinkId=272283)</span><span class="sxs-lookup"><span data-stu-id="cd232-207">MicrosoftAjax.js –[https://go.microsoft.com/p/fwlink/?LinkId=272283](https://go.microsoft.com/fwlink/p/?LinkId=272283)</span></span>

   -   <span data-ttu-id="cd232-208">MicrosoftMvcAjax.js-[https://go.microsoft.com/p/fwlink/?LinkId=272284](https://go.microsoft.com/fwlink/p/?LinkId=272284)</span><span class="sxs-lookup"><span data-stu-id="cd232-208">MicrosoftMvcAjax.js - [https://go.microsoft.com/p/fwlink/?LinkId=272284](https://go.microsoft.com/fwlink/p/?LinkId=272284)</span></span>

   -   <span data-ttu-id="cd232-209">MicrosoftMvcValidation.js-</span><span class="sxs-lookup"><span data-stu-id="cd232-209">MicrosoftMvcValidation.js -</span></span> <https://go.microsoft.com/fwlink/p/?LinkId=272285>

3. <span data-ttu-id="cd232-210">将 JavaScript 文件复制到自助服务门户的 "**脚本**" 目录中。</span><span class="sxs-lookup"><span data-stu-id="cd232-210">Copy the JavaScript files to the **Scripts** directory of the Self-Service Portal.</span></span> <span data-ttu-id="cd232-211">此目录位于 <em> &lt; MBAM 自助服务安装目录 &gt; \\ </em> 自助服务 Website\\Scripts。</span><span class="sxs-lookup"><span data-stu-id="cd232-211">This directory is located in <em>&lt;MBAM Self-Service Install Directory&gt;\\</em>Self Service Website\\Scripts.</span></span>

4. <span data-ttu-id="cd232-212">打开**Internet Information Services （IIS）管理器**。</span><span class="sxs-lookup"><span data-stu-id="cd232-212">Open **Internet Information Services (IIS) Manager**.</span></span>

5. <span data-ttu-id="cd232-213">展开 "**网站** &gt; **Microsoft BitLocker 管理和监视**"，然后突出显示**SelfService**。</span><span class="sxs-lookup"><span data-stu-id="cd232-213">Expand **Sites** &gt; **Microsoft BitLocker Administration and Monitoring**, and highlight **SelfService**.</span></span>

   **<span data-ttu-id="cd232-214">注意</span><span class="sxs-lookup"><span data-stu-id="cd232-214">Note</span></span>**  
   <span data-ttu-id="cd232-215">*SelfService*是默认的虚拟目录名称。</span><span class="sxs-lookup"><span data-stu-id="cd232-215">*SelfService* is the default virtual directory name.</span></span> <span data-ttu-id="cd232-216">如果在安装过程中为此目录选择了其他名称，请记住将其余说明中的*SelfService*替换为您选择的名称。</span><span class="sxs-lookup"><span data-stu-id="cd232-216">If you chose a different name for this directory during installation, remember to replace *SelfService* in the rest of these instructions with the name you chose.</span></span>



6. <span data-ttu-id="cd232-217">在中间窗格中，双击 "**应用程序设置**"。</span><span class="sxs-lookup"><span data-stu-id="cd232-217">In the middle pane, double-click **Application Settings**.</span></span>

7. <span data-ttu-id="cd232-218">对于下表中的每一项，通过 &lt; &gt; 使用/SelfService/（或在安装过程中选择的名称）替换虚拟目录来编辑应用程序设置以引用新位置。</span><span class="sxs-lookup"><span data-stu-id="cd232-218">For each item in the following list, edit the application settings to reference the new location by replacing &lt;virtual directory&gt; with /SelfService/ (or the name you chose during installation).</span></span> <span data-ttu-id="cd232-219">例如，虚拟目录路径将类似于/selfservice/scripts/jquery-1.7.2.min.js。</span><span class="sxs-lookup"><span data-stu-id="cd232-219">For example, the virtual directory path will be similar to /selfservice/scripts/jquery-1.7.2.min.js.</span></span>

   -   <span data-ttu-id="cd232-220">jQueryPath：/ &lt; virtual directory &gt; /Scripts/jQuery-1.7.2.min.js</span><span class="sxs-lookup"><span data-stu-id="cd232-220">jQueryPath: /&lt;virtual directory&gt;/Scripts/ jQuery-1.7.2.min.js</span></span>

   -   <span data-ttu-id="cd232-221">MicrosoftAjaxPath：/ &lt; virtual directory &gt; /Scripts/MicrosoftAjax.js</span><span class="sxs-lookup"><span data-stu-id="cd232-221">MicrosoftAjaxPath: /&lt;virtual directory&gt;/Scripts/ MicrosoftAjax.js</span></span>

   -   <span data-ttu-id="cd232-222">MicrosoftMvcAjaxPath：/ &lt; virtual directory &gt; /Scripts/MicrosoftMvcAjax.js</span><span class="sxs-lookup"><span data-stu-id="cd232-222">MicrosoftMvcAjaxPath: /&lt;virtual directory&gt;/Scripts/ MicrosoftMvcAjax.js</span></span>

   -   <span data-ttu-id="cd232-223">MicrosoftMvcValidationPath：/ &lt; virtual directory &gt; /Scripts/MicrosoftMvcValidation.js</span><span class="sxs-lookup"><span data-stu-id="cd232-223">MicrosoftMvcValidationPath: /&lt;virtual directory&gt;/Scripts/ MicrosoftMvcValidation.js</span></span>

**<span data-ttu-id="cd232-224">安装 "管理和监视服务器" 功能</span><span class="sxs-lookup"><span data-stu-id="cd232-224">To install the Administration and Monitoring Server feature</span></span>**

1. <span data-ttu-id="cd232-225">MBAM 可以加密 Web 服务与管理和监视服务器之间的通信。</span><span class="sxs-lookup"><span data-stu-id="cd232-225">MBAM can encrypt the communication between the Web Services and the Administration and Monitoring servers.</span></span> <span data-ttu-id="cd232-226">如果你选择加密通信的选项，系统将提示你选择用于加密的证书颁发机构预配的证书。</span><span class="sxs-lookup"><span data-stu-id="cd232-226">If you choose the option to encrypt the communication, you are prompted to select the certification authority-provisioned certificate to use for encryption.</span></span>

2. <span data-ttu-id="cd232-227">单击**下一步**以继续。</span><span class="sxs-lookup"><span data-stu-id="cd232-227">Click **Next** to continue.</span></span>

3. <span data-ttu-id="cd232-228">指定安装合规性和审核数据库的 SQL Server 远程实例（例如： \* &lt; ServerName &gt; \*）。</span><span class="sxs-lookup"><span data-stu-id="cd232-228">Specify the remote instance of SQL Server (for example: *&lt;ServerName&gt;*) where the Compliance and Audit Database was installed.</span></span>

4. <span data-ttu-id="cd232-229">指定合规性和审核数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="cd232-229">Specify the name of the Compliance and Audit Database.</span></span> <span data-ttu-id="cd232-230">默认情况下，数据库名称为 MBAM 合规性状态。</span><span class="sxs-lookup"><span data-stu-id="cd232-230">By default, the database name is MBAM Compliance Status.</span></span> <span data-ttu-id="cd232-231">但是，你可以在安装合规性和审核数据库时更改名称。</span><span class="sxs-lookup"><span data-stu-id="cd232-231">However, you can change the name when you install the Compliance and Audit Database.</span></span>

5. <span data-ttu-id="cd232-232">单击**下一步**以继续。</span><span class="sxs-lookup"><span data-stu-id="cd232-232">Click **Next** to continue.</span></span>

6. <span data-ttu-id="cd232-233">指定安装了恢复数据库的 SQL Server 远程实例（例如： \* &lt; ServerName &gt; \*）。</span><span class="sxs-lookup"><span data-stu-id="cd232-233">Specify the remote instance of SQL Server (for example: *&lt;ServerName&gt;*) where the Recovery Database was installed.</span></span>

7. <span data-ttu-id="cd232-234">指定恢复数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="cd232-234">Specify the name of the Recovery Database.</span></span> <span data-ttu-id="cd232-235">默认情况下，数据库名称是**MBAM 恢复和硬件**。</span><span class="sxs-lookup"><span data-stu-id="cd232-235">By default, the database name is **MBAM Recovery and Hardware**.</span></span> <span data-ttu-id="cd232-236">但是，你可以在安装恢复数据库功能时更改名称。</span><span class="sxs-lookup"><span data-stu-id="cd232-236">However, you can change the name when you install the Recovery Database feature.</span></span>

8. <span data-ttu-id="cd232-237">单击**下一步**以继续。</span><span class="sxs-lookup"><span data-stu-id="cd232-237">Click **Next** to continue.</span></span>

9. <span data-ttu-id="cd232-238">指定 SQL Server Reporting Services （SRS）网站的 "开始" URL。</span><span class="sxs-lookup"><span data-stu-id="cd232-238">Specify the URL for the “Home” of the SQL Server Reporting Services (SRS) site.</span></span> <span data-ttu-id="cd232-239">SQL Server Reporting Services 网站实例的默认起始位置为：</span><span class="sxs-lookup"><span data-stu-id="cd232-239">The default Home location of a SQL Server Reporting Services site instance is at:</span></span>

   <span data-ttu-id="cd232-240">http:// <em> &lt; NameofMBAMReportsServer &gt; / </em> ReportServer</span><span class="sxs-lookup"><span data-stu-id="cd232-240">http://<em>&lt;NameofMBAMReportsServer&gt;/</em>ReportServer</span></span>

   **<span data-ttu-id="cd232-241">注意</span><span class="sxs-lookup"><span data-stu-id="cd232-241">Note</span></span>**  
   <span data-ttu-id="cd232-242">如果 SQL Server Reporting Services 配置为命名实例，则 URL 类似于以下内容： http://\* &lt; NameofMBAMReportsServer &gt; */ReportServer\_* &lt; SRSInstanceName &gt; \*。</span><span class="sxs-lookup"><span data-stu-id="cd232-242">If SQL Server Reporting Services was configured as a named instance, the URL resembles the following: http://*&lt;NameofMBAMReportsServer&gt;*/ReportServer\_*&lt;SRSInstanceName&gt;*.</span></span>



10. <span data-ttu-id="cd232-243">单击**下一步**以继续。</span><span class="sxs-lookup"><span data-stu-id="cd232-243">Click **Next** to continue.</span></span>

11. <span data-ttu-id="cd232-244">输入**端口号**、**主机名**（可选）和 MBAM 管理和监视服务器的**安装路径**。</span><span class="sxs-lookup"><span data-stu-id="cd232-244">Enter the **Port Number**, the **Host Name** (optional), and the **Installation Path** for the MBAM Administration and Monitoring Server.</span></span>

    **<span data-ttu-id="cd232-245">注意</span><span class="sxs-lookup"><span data-stu-id="cd232-245">Note</span></span>**  
    <span data-ttu-id="cd232-246">你指定的端口号必须是管理和监视服务器上未使用的端口号，除非你指定唯一的主机标题名称。</span><span class="sxs-lookup"><span data-stu-id="cd232-246">The port number that you specify must be an unused port number on the Administration and Monitoring server unless you specify a unique host header name.</span></span> <span data-ttu-id="cd232-247">如果您使用的是 Windows 防火墙，则该端口将自动打开。</span><span class="sxs-lookup"><span data-stu-id="cd232-247">If you are using Windows Firewall, the port will be opened automatically.</span></span>



12. <span data-ttu-id="cd232-248">若要选择性地注册自助服务门户的服务主体名称（SPN），请选择 "**使用 Active Directory 注册此计算机的服务主体名称（spn）" （Windows 身份验证所需）**。</span><span class="sxs-lookup"><span data-stu-id="cd232-248">To optionally register a Service Principal Name (SPN) for the Self-Service Portal, select **Register this machine’s Service Principal Names (SPN) with Active Directory (Required for Windows Authentication)**.</span></span> <span data-ttu-id="cd232-249">如果选中此复选框，MBAM 安装程序将不会尝试注册现有的 Spn，你可以在 MBAM 安装之前或之后手动注册 SPN。</span><span class="sxs-lookup"><span data-stu-id="cd232-249">If you select this check box, MBAM Setup will not try to register the existing SPNs, and you can manually register the SPN before or after the MBAM installation.</span></span> <span data-ttu-id="cd232-250">有关手动注册 SPN 的说明，请参阅[手动 SPN 注册](https://go.microsoft.com/fwlink/?LinkId=286758)。</span><span class="sxs-lookup"><span data-stu-id="cd232-250">For instructions on registering the SPN manually, see [Manual SPN Registration](https://go.microsoft.com/fwlink/?LinkId=286758).</span></span>

13. <span data-ttu-id="cd232-251">单击 "**下一步**" 以继续 "Microsoft BitLocker 管理和监视设置向导"。</span><span class="sxs-lookup"><span data-stu-id="cd232-251">Click **Next** to continue with the Microsoft BitLocker Administration and Monitoring Setup wizard.</span></span>

14. <span data-ttu-id="cd232-252">指定是否使用 Microsoft 更新来帮助保护您的计算机安全，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="cd232-252">Specify whether to use Microsoft Updates to help keep your computer secure, and then click **Next**.</span></span>

15. <span data-ttu-id="cd232-253">在所选的 MBAM 功能信息完成后，即可使用设置向导启动 MBAM 安装。</span><span class="sxs-lookup"><span data-stu-id="cd232-253">When the selected MBAM feature information is completed, you are ready to start the MBAM installation by using the Setup wizard.</span></span> <span data-ttu-id="cd232-254">如果必须查看或更改安装设置，请单击 "**返回**" 以在向导中移动。</span><span class="sxs-lookup"><span data-stu-id="cd232-254">Click **Back** to move through the wizard if you have to review or change your installation settings.</span></span> <span data-ttu-id="cd232-255">单击 "**安装**" 进行安装。</span><span class="sxs-lookup"><span data-stu-id="cd232-255">Click **Install** to being the installation.</span></span> <span data-ttu-id="cd232-256">单击 "**取消**" 退出向导。</span><span class="sxs-lookup"><span data-stu-id="cd232-256">Click **Cancel** to exit the wizard.</span></span> <span data-ttu-id="cd232-257">安装程序安装你选择的 MBAM 功能并通知你安装已完成。</span><span class="sxs-lookup"><span data-stu-id="cd232-257">Setup installs the MBAM features that you selected and notifies you that the installation is finished.</span></span>

16. <span data-ttu-id="cd232-258">单击 "**完成**" 退出向导。</span><span class="sxs-lookup"><span data-stu-id="cd232-258">Click **Finish** to exit the wizard.</span></span>

**<span data-ttu-id="cd232-259">执行安装后配置</span><span class="sxs-lookup"><span data-stu-id="cd232-259">To perform post-installation configuration</span></span>**

1.  <span data-ttu-id="cd232-260">在 "管理和监视" 服务器上，将用户添加到以下本地组，以使其可以访问 MBAM 管理和监视网站上的功能。</span><span class="sxs-lookup"><span data-stu-id="cd232-260">On the Administration and Monitoring Server, add users to the following local groups to give them access to the features on the MBAM Administration and Monitoring website.</span></span>

    -   <span data-ttu-id="cd232-261">**MBAM 帮助台用户**：此本地组的成员可以访问 MBAM 管理和监视网站上的驱动器恢复和管理 TPM 功能。</span><span class="sxs-lookup"><span data-stu-id="cd232-261">**MBAM Helpdesk Users**: Members of this local group can access the Drive Recovery and Manage TPM features on the MBAM Administration and Monitoring website.</span></span> <span data-ttu-id="cd232-262">驱动器恢复和管理 TPM 中的所有字段是支持人员用户的必填字段。</span><span class="sxs-lookup"><span data-stu-id="cd232-262">All fields in Drive Recovery and Manage TPM are required fields for a Helpdesk User.</span></span>

    -   <span data-ttu-id="cd232-263">**MBAM 高级帮助台用户**：此本地组的成员对驱动器恢复具有高级访问权限，并在 MBAM 管理和监视网站上管理 TPM 功能。</span><span class="sxs-lookup"><span data-stu-id="cd232-263">**MBAM Advanced Helpdesk Users**: Members of this local group have advanced access to the Drive Recovery and Manage TPM features on the MBAM Administration and Monitoring website.</span></span> <span data-ttu-id="cd232-264">对于高级帮助台用户，驱动器恢复中仅需要 "密钥 ID" 字段。</span><span class="sxs-lookup"><span data-stu-id="cd232-264">For Advanced Helpdesk Users, only the Key ID field is required in Drive Recovery.</span></span> <span data-ttu-id="cd232-265">在 "**管理 TPM**" 中，仅需要 "**计算机域**字段" 和 "**计算机名称**" 字段。</span><span class="sxs-lookup"><span data-stu-id="cd232-265">In **Manage TPM**, only the **Computer Domain** field and **Computer Name** field are required.</span></span>

2.  <span data-ttu-id="cd232-266">在托管管理和监视服务器以及合规性和审核数据库以及托管合规性和审核报告的服务器上的服务器上，将用户添加到以下本地组，以便他们可以访问 MBAM 管理和监视网站上的 "报告" 功能。</span><span class="sxs-lookup"><span data-stu-id="cd232-266">On the server that hosts Administration and Monitoring Server and the Compliance and Audit Database and on the server that hosts the Compliance and Audit Reports, add users to the following local group to give them access to the Reports feature on the MBAM Administration and Monitoring website.</span></span>

    -   <span data-ttu-id="cd232-267">**MBAM 报表用户**：此本地组的成员可以访问 MBAM 管理和监视网站上的报表。</span><span class="sxs-lookup"><span data-stu-id="cd232-267">**MBAM Report Users**: Members of this local group can access the reports on the MBAM Administration and Monitoring website.</span></span>

    **<span data-ttu-id="cd232-268">注意</span><span class="sxs-lookup"><span data-stu-id="cd232-268">Note</span></span>**  
    <span data-ttu-id="cd232-269">**MBAM 报表**的相同用户或组成员身份必须在所有计算机上维护，这些用户本地组 MBAM 管理和监视服务器功能、合规性和审核数据库以及合规性和审核报告已安装。</span><span class="sxs-lookup"><span data-stu-id="cd232-269">Identical user or group membership of the **MBAM Report Users** local group must be maintained on all computers where the MBAM Administration and Monitoring Server features, Compliance and Audit Database, and the Compliance and Audit Reports are installed.</span></span>



## <span data-ttu-id="cd232-270">验证 MBAM 服务器功能安装</span><span class="sxs-lookup"><span data-stu-id="cd232-270">Validating the MBAM Server Feature Installation</span></span>


<span data-ttu-id="cd232-271">Microsoft BitLocker 管理和监视服务器功能安装完成后，建议你验证安装是否已成功设置 MBAM 的所有必要功能。</span><span class="sxs-lookup"><span data-stu-id="cd232-271">When Microsoft BitLocker Administration and Monitoring Server feature installation is completed, we recommend that you validate that the installation has successfully set up all the necessary features for MBAM.</span></span> <span data-ttu-id="cd232-272">使用以下过程确认 Microsoft BitLocker 管理和监视服务正常运行。</span><span class="sxs-lookup"><span data-stu-id="cd232-272">Use the following procedure to confirm that the Microsoft BitLocker Administration and Monitoring service is functional.</span></span>

**<span data-ttu-id="cd232-273">验证 MBAM 服务器安装</span><span class="sxs-lookup"><span data-stu-id="cd232-273">To validate an MBAM Server installation</span></span>**

1. <span data-ttu-id="cd232-274">在部署 MBAM 功能的每台服务器上，打开 "**控制面板**"，选择 "**程序**"，然后选择 "**程序和功能**"。</span><span class="sxs-lookup"><span data-stu-id="cd232-274">On each server where an MBAM feature is deployed, open **Control Panel**, select **Programs**, and then select **Programs and Features**.</span></span> <span data-ttu-id="cd232-275">验证 "**程序和功能**" 列表中是否显示 " **Microsoft BitLocker 管理和监视**"。</span><span class="sxs-lookup"><span data-stu-id="cd232-275">Verify that **Microsoft BitLocker Administration and Monitoring** appears in the **Programs and Features** list.</span></span>

   **<span data-ttu-id="cd232-276">注意</span><span class="sxs-lookup"><span data-stu-id="cd232-276">Note</span></span>**  
   <span data-ttu-id="cd232-277">若要验证 MBAM 安装，必须使用在每台服务器上具有本地计算机管理凭据的域帐户。</span><span class="sxs-lookup"><span data-stu-id="cd232-277">To validate the MBAM installation, you must use a domain account that has local computer administrative credentials on each server.</span></span>



2. <span data-ttu-id="cd232-278">在安装了恢复数据库的服务器上，打开 SQL Server Management Studio 并验证是否已安装**MBAM 恢复和硬件**数据库。</span><span class="sxs-lookup"><span data-stu-id="cd232-278">On the server where the Recovery Database is installed, open SQL Server Management Studio and verify that the **MBAM Recovery and Hardware** database is installed.</span></span>

3. <span data-ttu-id="cd232-279">在安装合规性和审核数据库的服务器上，打开 SQL Server Management Studio 并验证是否已安装**MBAM 合规性状态数据库**。</span><span class="sxs-lookup"><span data-stu-id="cd232-279">On the server where the Compliance and Audit Database is installed, open SQL Server Management Studio and verify that the **MBAM Compliance Status Database** is installed.</span></span>

4. <span data-ttu-id="cd232-280">在安装合规性和审核报告的服务器上，使用管理凭据打开 web 浏览器，然后浏览到 SQL Server Reporting Services 网站的 "开始"。</span><span class="sxs-lookup"><span data-stu-id="cd232-280">On the server where the Compliance and Audit Reports are installed, open a web browser with administrative credentials and browse to the “Home” of the SQL Server Reporting Services site.</span></span>

   <span data-ttu-id="cd232-281">可以在 http:// <em> &lt; NameofMBAMReportsServer &gt; </em> /Reports.aspx. 上找到 SQL Server Reporting Services 网站实例的默认起始位置</span><span class="sxs-lookup"><span data-stu-id="cd232-281">The default Home location of a SQL Server Reporting Services site instance can be found is at http://<em>&lt;NameofMBAMReportsServer&gt;</em>/Reports.aspx.</span></span> <span data-ttu-id="cd232-282">若要查找实际 URL，请使用 Reporting Services 配置管理器工具，并选择在安装过程中指定的实例。</span><span class="sxs-lookup"><span data-stu-id="cd232-282">To find the actual URL, use the Reporting Services Configuration Manager tool and select the instances that were specified during setup.</span></span>

   <span data-ttu-id="cd232-283">确认名为**Microsoft BitLocker 管理和监视**的报告文件夹包含名为 " **MaltaDataSource** " 的数据源，并且 " **en-us** " 文件夹包含四个报表。</span><span class="sxs-lookup"><span data-stu-id="cd232-283">Confirm that a reports folder named **Microsoft BitLocker Administration and Monitoring** contains a data source called **MaltaDataSource** and that an **en-us** folder contains four reports.</span></span>

   **<span data-ttu-id="cd232-284">注意</span><span class="sxs-lookup"><span data-stu-id="cd232-284">Note</span></span>**  
   <span data-ttu-id="cd232-285">如果 SQL Server Reporting Services 配置为命名实例，则 URL 应类似于以下内容： http：//\* &lt; NameofMBAMReportsServer &gt; */Reports\_* &lt; SRSInstanceName &gt; \*</span><span class="sxs-lookup"><span data-stu-id="cd232-285">If SQL Server Reporting Services was configured as a named instance, the URL should resemble the following:http://*&lt;NameofMBAMReportsServer&gt;*/Reports\_*&lt;SRSInstanceName&gt;*</span></span>



~~~
**Note**  
If SSRS was not configured to use Secure Socket Layer (SSL), the URL for the reports will be set to HTTP instead of HTTPS when you install the MBAM Server. If you then go to the Administration and Monitoring website and select a report, the following message appears: “Only Secure Content is Displayed.” To show the report, click **Show All Content**.
~~~



5. <span data-ttu-id="cd232-286">在安装了 "管理和监视" 功能的服务器上，运行 "**服务器管理器**" 并浏览到 "**角色**"。</span><span class="sxs-lookup"><span data-stu-id="cd232-286">On the server where the Administration and Monitoring feature is installed, run **Server Manager** and browse to **Roles**.</span></span> <span data-ttu-id="cd232-287">选择 " **Web 服务器（iis）**"，然后单击 " **Internet 信息服务（Iis）管理器**"。</span><span class="sxs-lookup"><span data-stu-id="cd232-287">Select **Web Server (IIS)**, and then click **Internet Information Services (IIS) Manager**.</span></span>

6. <span data-ttu-id="cd232-288">在 "**连接**" 中，浏览到 " \* &lt; computername &gt; \*"，选择 "**网站**"，然后选择 " **Microsoft BitLocker 管理和监视**"。</span><span class="sxs-lookup"><span data-stu-id="cd232-288">In **Connections**, browse to *&lt;computername&gt;*, select **Sites**, and select **Microsoft BitLocker Administration and Monitoring**.</span></span> <span data-ttu-id="cd232-289">验证 " **MBAMAdministrationService**"、" **MBAMComplianceStatusService**" 和 " **MBAMRecoveryAndHardwareService** " 是否已列出。</span><span class="sxs-lookup"><span data-stu-id="cd232-289">Verify that **MBAMAdministrationService**, **MBAMComplianceStatusService**, and **MBAMRecoveryAndHardwareService** are listed.</span></span>

7. <span data-ttu-id="cd232-290">在安装了 "管理" 和 "监视" 功能和 "自助服务" 门户的服务器上，打开具有管理凭据的 web 浏览器，然后浏览到以下位置以验证它们是否成功加载。</span><span class="sxs-lookup"><span data-stu-id="cd232-290">On the server where the Administration and Monitoring features and Self-Service Portal are installed, open a web browser with administrative credentials and browse to the following locations to verify that they load successfully.</span></span>

   **<span data-ttu-id="cd232-291">注意</span><span class="sxs-lookup"><span data-stu-id="cd232-291">Note</span></span>**  
   <span data-ttu-id="cd232-292">以 ".svc" 结尾的 Url 不会显示网站。</span><span class="sxs-lookup"><span data-stu-id="cd232-292">The URLs ending in “.svc” do not display a website.</span></span> <span data-ttu-id="cd232-293">成功由消息 "此服务的元数据发布当前已禁用" 或类似代码的信息指示。</span><span class="sxs-lookup"><span data-stu-id="cd232-293">Success is indicated by the message “Metadata publishing for this service is currently disabled” or by information resembling code.</span></span> <span data-ttu-id="cd232-294">如果您看到其他错误消息，或者如果找不到页面，则页面未成功加载。</span><span class="sxs-lookup"><span data-stu-id="cd232-294">If you see some other error message or if the page cannot be found, the page has not loaded successfully.</span></span>



~~~
-   *http://&lt;hostname&gt;/HelpDesk/default.aspx* and confirm each of the links for navigation and reports

-   *http://&lt;hostname&gt;/SelfService&gt;/*

-   *http://&lt;computername&gt;/MBAMAdministrationService/AdministrationService.svc*

-   *http://&lt;hostname&gt;/MBAMUserSupportService/UserSupportService.svc*

-   *http://&lt;computername&gt;/MBAMComplianceStatusService/StatusReportingService.svc*

-   *http://&lt;computername&gt;/MBAMRecoveryAndHardwareService/CoreService.svc*

**Note**  
It is assumed that the server features were installed on the default port without network encryption. If you installed the server features on a different port or virtual directory, change the URLs to include the appropriate port, for example, *http://&lt;hostname&gt;:&lt;port&gt;/HelpDesk/default.aspx* or*http://&lt;hostname&gt;:&lt;port&gt;/&lt;virtualdirectory&gt;/default.aspx*

If the server features were installed with network encryption, change http:// to https://.
~~~



8. <span data-ttu-id="cd232-295">验证每个网页是否已成功加载。</span><span class="sxs-lookup"><span data-stu-id="cd232-295">Verify that each webpage loads successfully.</span></span>

## <span data-ttu-id="cd232-296">相关主题</span><span class="sxs-lookup"><span data-stu-id="cd232-296">Related topics</span></span>


[<span data-ttu-id="cd232-297">部署 MBAM 2.0 服务器基础结构</span><span class="sxs-lookup"><span data-stu-id="cd232-297">Deploying the MBAM 2.0 Server Infrastructure</span></span>](deploying-the-mbam-20-server-infrastructure-mbam-2.md)









