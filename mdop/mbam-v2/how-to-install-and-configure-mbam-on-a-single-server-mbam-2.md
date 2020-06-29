---
title: 如何在单个服务器上安装和配置 MBAM
description: 如何在单个服务器上安装和配置 MBAM
author: dansimp
ms.assetid: 45e6a012-6c8c-4d90-902c-d09de9a0cbea
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 53e170f421bdce8dd6f771af3902af627a15a085
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803494"
---
# <span data-ttu-id="d8488-103">如何在单个服务器上安装和配置 MBAM</span><span class="sxs-lookup"><span data-stu-id="d8488-103">How to Install and Configure MBAM on a Single Server</span></span>


<span data-ttu-id="d8488-104">本主题中的过程介绍了如何在单个服务器上的独立拓扑中安装 Microsoft BitLocker 管理和监视（MBAM）。</span><span class="sxs-lookup"><span data-stu-id="d8488-104">The procedures in this topic describe how to install Microsoft BitLocker Administration and Monitoring (MBAM) in the Stand-alone topology on a single server.</span></span> <span data-ttu-id="d8488-105">仅在测试环境中使用单服务器配置。</span><span class="sxs-lookup"><span data-stu-id="d8488-105">Use the single-server configuration only in a test environment.</span></span> <span data-ttu-id="d8488-106">对于生产环境，使用两个或多个服务器。</span><span class="sxs-lookup"><span data-stu-id="d8488-106">For production environments, use two or more servers.</span></span> <span data-ttu-id="d8488-107">如果你正在使用 Configuration Manager 拓扑安装 Microsoft BitLocker 管理和监视，请参阅使用[Configuration Manager 部署 MBAM](deploying-mbam-with-configuration-manager-mbam2.md)。</span><span class="sxs-lookup"><span data-stu-id="d8488-107">If you are installing Microsoft BitLocker Administration and Monitoring by using the Configuration Manager topology, see [Deploying MBAM with Configuration Manager](deploying-mbam-with-configuration-manager-mbam2.md).</span></span>

<span data-ttu-id="d8488-108">下图显示了单服务器体系结构的示例。</span><span class="sxs-lookup"><span data-stu-id="d8488-108">The following diagram shows an example of a single-server architecture.</span></span> <span data-ttu-id="d8488-109">有关数据库和功能的说明，请参阅[MBAM 2.0 的高级别体系结构](high-level-architecture-for-mbam-20-mbam-2.md)。</span><span class="sxs-lookup"><span data-stu-id="d8488-109">For a description of the databases and features, see [High-Level Architecture for MBAM 2.0](high-level-architecture-for-mbam-20-mbam-2.md).</span></span>

![mbam 2 单服务器部署拓扑](images/mbam2-1-server.gif)

<span data-ttu-id="d8488-111">每个服务器功能都具有特定的先决条件。</span><span class="sxs-lookup"><span data-stu-id="d8488-111">Each server feature has certain prerequisites.</span></span> <span data-ttu-id="d8488-112">若要验证你是否满足先决条件和硬件和软件要求，请参阅[MBAM 2.0 部署先决条件](mbam-20-deployment-prerequisites-mbam-2.md)和[MBAM 2.0 支持的配置](mbam-20-supported-configurations-mbam-2.md)。</span><span class="sxs-lookup"><span data-stu-id="d8488-112">To verify that you have met the prerequisites and hardware and software requirements, see [MBAM 2.0 Deployment Prerequisites](mbam-20-deployment-prerequisites-mbam-2.md) and [MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md).</span></span> <span data-ttu-id="d8488-113">此外，某些功能还包含安装过程中必须提供的信息才能成功部署该功能。</span><span class="sxs-lookup"><span data-stu-id="d8488-113">In addition, some features also have information that must be provided during the installation process to successfully deploy the feature.</span></span> <span data-ttu-id="d8488-114">在开始 MBAM 部署之前，还应查看[准备 MBAM 2.0 的环境](preparing-your-environment-for-mbam-20-mbam-2.md)。</span><span class="sxs-lookup"><span data-stu-id="d8488-114">You should also review [Preparing your Environment for MBAM 2.0](preparing-your-environment-for-mbam-20-mbam-2.md) before you start MBAM deployment.</span></span>

**<span data-ttu-id="d8488-115">注意</span><span class="sxs-lookup"><span data-stu-id="d8488-115">Note</span></span>**  
<span data-ttu-id="d8488-116">若要获取安装程序日志文件，你可以使用 Msiexec 程序包和 **/l** &lt; location &gt; 选项来安装 MBAM。</span><span class="sxs-lookup"><span data-stu-id="d8488-116">To obtain the setup log files, you have use the Msiexec package and the **/L** &lt;location&gt; option to install MBAM.</span></span> <span data-ttu-id="d8488-117">将在您指定的位置创建日志文件。</span><span class="sxs-lookup"><span data-stu-id="d8488-117">Log files are created in the location that you specify.</span></span>

<span data-ttu-id="d8488-118">其他安装日志文件在安装 MBAM 的用户服务器上的% temp% 文件夹中创建。</span><span class="sxs-lookup"><span data-stu-id="d8488-118">Additional setup log files are created in the %temp% folder on the server of the user who is installing MBAM.</span></span>



## <span data-ttu-id="d8488-119">在单个服务器上安装 MBAM 服务器功能</span><span class="sxs-lookup"><span data-stu-id="d8488-119">To install MBAM Server features on a single server</span></span>


<span data-ttu-id="d8488-120">以下步骤介绍了如何安装常规 MBAM 功能。</span><span class="sxs-lookup"><span data-stu-id="d8488-120">The following steps describe how to install general MBAM features.</span></span>

**<span data-ttu-id="d8488-121">启动 MBAM Server 功能安装</span><span class="sxs-lookup"><span data-stu-id="d8488-121">To start the MBAM Server features installation</span></span>**

1.  <span data-ttu-id="d8488-122">在要安装 MBAM 的服务器上，运行**MBAMSetup.exe**以启动 MBAM 安装向导。</span><span class="sxs-lookup"><span data-stu-id="d8488-122">On the server where you want to install MBAM, run **MBAMSetup.exe** to start the MBAM installation wizard.</span></span>

2.  <span data-ttu-id="d8488-123">在 "**欢迎**" 页面上，选择 "**客户体验改善计划**"，然后单击 "**开始**"。</span><span class="sxs-lookup"><span data-stu-id="d8488-123">On the **Welcome** page, optionally select the **Customer Experience Improvement Program**, and then click **Start**.</span></span>

3.  <span data-ttu-id="d8488-124">阅读并接受 Microsoft 软件许可协议，然后单击 "**下一步**" 继续安装。</span><span class="sxs-lookup"><span data-stu-id="d8488-124">Read and accept the Microsoft Software License Agreement, and then click **Next** to continue the installation.</span></span>

4.  <span data-ttu-id="d8488-125">在 "**拓扑选择**" 页面上，选择**独立**拓扑，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="d8488-125">On the **Topology Selection** page, select the **Stand-alone** topology, and then click **Next**.</span></span>

5.  <span data-ttu-id="d8488-126">在 "**选择要安装的功能**" 页面上，选择要安装的功能。</span><span class="sxs-lookup"><span data-stu-id="d8488-126">On the **Select features to install** page, select the features that you want to install.</span></span> <span data-ttu-id="d8488-127">默认情况下，将选择所有 MBAM 功能进行安装。</span><span class="sxs-lookup"><span data-stu-id="d8488-127">By default, all MBAM features are selected for installation.</span></span> <span data-ttu-id="d8488-128">要在同一台计算机上安装的功能必须同时安装在一起。</span><span class="sxs-lookup"><span data-stu-id="d8488-128">Features that are to be installed on the same computer must be installed together at the same time.</span></span> <span data-ttu-id="d8488-129">清除要在其他位置安装的任何功能的复选框。</span><span class="sxs-lookup"><span data-stu-id="d8488-129">Clear the check boxes for any features that you want to install elsewhere.</span></span> <span data-ttu-id="d8488-130">必须按以下顺序安装 MBAM 功能：</span><span class="sxs-lookup"><span data-stu-id="d8488-130">You must install MBAM features in the following order:</span></span>

    -   <span data-ttu-id="d8488-131">恢复数据库</span><span class="sxs-lookup"><span data-stu-id="d8488-131">Recovery Database</span></span>

    -   <span data-ttu-id="d8488-132">合规性和审核数据库</span><span class="sxs-lookup"><span data-stu-id="d8488-132">Compliance and Audit Database</span></span>

    -   <span data-ttu-id="d8488-133">合规性和审核报告</span><span class="sxs-lookup"><span data-stu-id="d8488-133">Compliance and Audit Reports</span></span>

    -   <span data-ttu-id="d8488-134">自助服务服务器</span><span class="sxs-lookup"><span data-stu-id="d8488-134">Self-Service Server</span></span>

    -   <span data-ttu-id="d8488-135">管理和监视服务器</span><span class="sxs-lookup"><span data-stu-id="d8488-135">Administration and Monitoring Server</span></span>

    -   <span data-ttu-id="d8488-136">MBAM 组策略模板</span><span class="sxs-lookup"><span data-stu-id="d8488-136">MBAM Group Policy template</span></span>

    **<span data-ttu-id="d8488-137">注意</span><span class="sxs-lookup"><span data-stu-id="d8488-137">Note</span></span>**  
    <span data-ttu-id="d8488-138">安装向导将检查安装的先决条件，并显示缺少的必备条件。</span><span class="sxs-lookup"><span data-stu-id="d8488-138">The installation wizard checks the prerequisites for your installation and displays the prerequisites that are missing.</span></span> <span data-ttu-id="d8488-139">如果满足所有先决条件，安装将继续。</span><span class="sxs-lookup"><span data-stu-id="d8488-139">If all of the prerequisites are met, the installation continues.</span></span> <span data-ttu-id="d8488-140">如果检测到缺少先决条件，则必须解决缺少的先决条件，然后再次单击 "**检查必备项**"。</span><span class="sxs-lookup"><span data-stu-id="d8488-140">If a missing prerequisite is detected, you have to resolve the missing prerequisites, and then click **Check prerequisites again**.</span></span> <span data-ttu-id="d8488-141">如果此时间满足所有先决条件，安装将继续。</span><span class="sxs-lookup"><span data-stu-id="d8488-141">If all prerequisites are met this time, the installation resumes.</span></span>



6.  <span data-ttu-id="d8488-142">在 "**配置网络通信安全**" 页面上，选择是否加密管理和监视服务器和客户端上的 Web 服务之间的通信。</span><span class="sxs-lookup"><span data-stu-id="d8488-142">On the **Configure network communication security** page, choose whether to encrypt the communication between the Web Services on the Administration and Monitoring Server and the clients.</span></span> <span data-ttu-id="d8488-143">如果您决定加密通信，请选择用于加密的证书颁发机构预配的证书。</span><span class="sxs-lookup"><span data-stu-id="d8488-143">If you decide to encrypt the communication, select the certification authority-provisioned certificate to use for encryption.</span></span> <span data-ttu-id="d8488-144">在此步骤之前，必须创建证书，以使你能够在此页面上选择它。</span><span class="sxs-lookup"><span data-stu-id="d8488-144">The certificate must be created prior to this step to enable you to select it on this page.</span></span>

    **<span data-ttu-id="d8488-145">注意</span><span class="sxs-lookup"><span data-stu-id="d8488-145">Note</span></span>**  
    <span data-ttu-id="d8488-146">仅当在 "**选择要安装的功能**" 页面上选择了 "自助式门户" 或 "管理和监视服务器" 功能时，才会显示此页面。</span><span class="sxs-lookup"><span data-stu-id="d8488-146">This page appears only if you selected the Self-Service Portal or the Administration and Monitoring Server feature on the **Select features to install** page.</span></span>



7.  <span data-ttu-id="d8488-147">单击 "**下一步**"，然后继续执行下一组步骤来配置 MBAM 服务器功能。</span><span class="sxs-lookup"><span data-stu-id="d8488-147">Click **Next**, and then continue to the next set of steps to configure the MBAM Server features.</span></span>

**<span data-ttu-id="d8488-148">配置 MBAM 服务器功能</span><span class="sxs-lookup"><span data-stu-id="d8488-148">To configure the MBAM Server features</span></span>**

1.  <span data-ttu-id="d8488-149">在 "**配置恢复数据库**" 页面上，指定要存储恢复数据的数据库的 SQL Server 实例名称和数据库名称。</span><span class="sxs-lookup"><span data-stu-id="d8488-149">On the **Configure the Recovery database** page, specify the SQL Server instance name and the name of the database that will store the recovery data.</span></span> <span data-ttu-id="d8488-150">你还必须指定数据库文件所在的位置以及日志信息将位于何处。</span><span class="sxs-lookup"><span data-stu-id="d8488-150">You must also specify both where the database files will be located and where the log information will be located.</span></span>

2.  <span data-ttu-id="d8488-151">单击**下一步**以继续。</span><span class="sxs-lookup"><span data-stu-id="d8488-151">Click **Next** to continue.</span></span>

3.  <span data-ttu-id="d8488-152">在 "**配置合规性和审核数据库**" 页面上，指定要存储合规性和审核数据的数据库的 SQL Server 实例名称和名称。</span><span class="sxs-lookup"><span data-stu-id="d8488-152">On the **Configure the Compliance and Audit database** page, specify the SQL Server instance name and the name of the database that will store the compliance and audit data.</span></span> <span data-ttu-id="d8488-153">你还必须指定数据库文件的位置和日志信息将位于何处。</span><span class="sxs-lookup"><span data-stu-id="d8488-153">You must also specify where the database files will be located and where the log information will be located.</span></span>

4.  <span data-ttu-id="d8488-154">单击**下一步**以继续。</span><span class="sxs-lookup"><span data-stu-id="d8488-154">Click **Next** to continue.</span></span>

5.  <span data-ttu-id="d8488-155">在 "**配置合规性和审核报告**" 页面上，指定将安装合规性和审核报告的 SQL Server Reporting Services 实例，并提供用于访问合规性和审核数据库的域用户帐户和密码。</span><span class="sxs-lookup"><span data-stu-id="d8488-155">On the **Configure the Compliance and Audit Reports** page, specify the SQL Server Reporting Services instance where the Compliance and Audit reports will be installed, and provide a domain user account and password for accessing the Compliance and Audit database.</span></span> <span data-ttu-id="d8488-156">将此帐户的密码配置为永不过期。</span><span class="sxs-lookup"><span data-stu-id="d8488-156">Configure the password for this account to never expire.</span></span> <span data-ttu-id="d8488-157">用户帐户应该能够访问 MBAM Reports Users 组中所有可用的数据。</span><span class="sxs-lookup"><span data-stu-id="d8488-157">The user account should be able to access all data available to the MBAM Reports Users group.</span></span>

6.  <span data-ttu-id="d8488-158">单击**下一步**以继续。</span><span class="sxs-lookup"><span data-stu-id="d8488-158">Click **Next** to continue.</span></span>

7.  <span data-ttu-id="d8488-159">在 "**配置自助服务门户**" 页面上，输入自助服务门户的端口号、主机名、虚拟目录名称和安装路径。</span><span class="sxs-lookup"><span data-stu-id="d8488-159">On the **Configure the Self-Service Portal** page, enter the port number, host name, virtual directory name, and installation path for the Self-Service Portal.</span></span>

    **<span data-ttu-id="d8488-160">注意</span><span class="sxs-lookup"><span data-stu-id="d8488-160">Note</span></span>**  
    <span data-ttu-id="d8488-161">你指定的端口号必须是管理和监视服务器上未使用的端口号，除非你指定唯一的主机标题名称。</span><span class="sxs-lookup"><span data-stu-id="d8488-161">The port number that you specify must be an unused port number on the Administration and Monitoring Server unless you specify a unique host header name.</span></span> <span data-ttu-id="d8488-162">如果您使用的是 Windows 防火墙，则该端口将自动打开。</span><span class="sxs-lookup"><span data-stu-id="d8488-162">If you are using Windows Firewall, the port will be opened automatically.</span></span>



8.  <span data-ttu-id="d8488-163">单击**下一步**以继续。</span><span class="sxs-lookup"><span data-stu-id="d8488-163">Click **Next** to continue.</span></span>

9.  <span data-ttu-id="d8488-164">指定是否使用 Microsoft 更新来帮助保护您的计算机安全，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="d8488-164">Specify whether to use Microsoft Updates to help keep your computer secure, and then click **Next**.</span></span> <span data-ttu-id="d8488-165">此操作不会在 Windows 中启用自动更新。</span><span class="sxs-lookup"><span data-stu-id="d8488-165">This does not turn on Automatic Updates in Windows.</span></span>

10. <span data-ttu-id="d8488-166">在 "**配置管理和监视服务器**" 页面上，输入技术支持网站的端口号、主机名、虚拟目录名称和安装路径。</span><span class="sxs-lookup"><span data-stu-id="d8488-166">On the **Configure the Administration and Monitoring Server** page, enter the port number, host name, virtual directory name, and installation path for the Help Desk website.</span></span>

    **<span data-ttu-id="d8488-167">注意</span><span class="sxs-lookup"><span data-stu-id="d8488-167">Note</span></span>**  
    <span data-ttu-id="d8488-168">你指定的端口号必须是管理和监视服务器上未使用的端口号，除非你指定唯一的主机标题名称。</span><span class="sxs-lookup"><span data-stu-id="d8488-168">The port number that you specify must be an unused port number on the Administration and Monitoring Server unless you specify a unique host header name.</span></span> <span data-ttu-id="d8488-169">如果您使用的是 Windows 防火墙，则该端口将自动打开。</span><span class="sxs-lookup"><span data-stu-id="d8488-169">If you are using Windows Firewall, the port will be opened automatically.</span></span>



11. <span data-ttu-id="d8488-170">在 "**安装摘要**" 页面上，查看将安装的功能列表，然后单击 "**安装**" 以开始安装 MBAM 功能。</span><span class="sxs-lookup"><span data-stu-id="d8488-170">On the **Installation Summary** page, review the list of features that will be installed, and click **Install** to start installing the MBAM features.</span></span> <span data-ttu-id="d8488-171">如果必须查看或更改安装设置，请单击 "**返回**" 以在向导中向后移动，或者单击 "**取消**" 退出安装程序。</span><span class="sxs-lookup"><span data-stu-id="d8488-171">Click **Back** to move back through the wizard if you have to review or change your installation settings, or click **Cancel** to exit Setup.</span></span> <span data-ttu-id="d8488-172">安装程序安装 MBAM 功能并通知您安装已完成。</span><span class="sxs-lookup"><span data-stu-id="d8488-172">Setup installs the MBAM features and notifies you that the installation is complete.</span></span>

12. <span data-ttu-id="d8488-173">单击 "**完成**" 退出向导。</span><span class="sxs-lookup"><span data-stu-id="d8488-173">Click **Finish** to exit the wizard.</span></span> <span data-ttu-id="d8488-174">安装 Microsoft BitLocker 管理和监视服务器功能后，继续下一节，完成步骤必须将用户添加到 Microsoft BitLocker 管理和监视角色。</span><span class="sxs-lookup"><span data-stu-id="d8488-174">After the Microsoft BitLocker Administration and Monitoring Server features have been installed, continue to the next section and complete the steps have to add users to the Microsoft BitLocker Administration and Monitoring roles.</span></span> <span data-ttu-id="d8488-175">有关角色的详细信息，请参阅[规划 MBAM 2.0 管理员角色](planning-for-mbam-20-administrator-roles-mbam-2.md)。</span><span class="sxs-lookup"><span data-stu-id="d8488-175">For more information about roles, see [Planning for MBAM 2.0 Administrator Roles](planning-for-mbam-20-administrator-roles-mbam-2.md).</span></span>

**<span data-ttu-id="d8488-176">执行安装后配置</span><span class="sxs-lookup"><span data-stu-id="d8488-176">To perform post-installation configuration</span></span>**

1.  <span data-ttu-id="d8488-177">在 "管理和监视" 服务器上，将用户添加到以下本地组，让他们可以访问 MBAM 技术支持网站功能：</span><span class="sxs-lookup"><span data-stu-id="d8488-177">On the Administration and Monitoring Server, add users to the following local groups to give them access to the MBAM Help Desk website features:</span></span>

    -   <span data-ttu-id="d8488-178">**MBAM 帮助台用户**：此本地组的成员可以访问 MBAM 管理和监视网站上的驱动器恢复和管理 TPM 功能。</span><span class="sxs-lookup"><span data-stu-id="d8488-178">**MBAM Helpdesk Users**: Members of this local group can access the Drive Recovery and Manage TPM features on the MBAM Administration and Monitoring website.</span></span> <span data-ttu-id="d8488-179">驱动器恢复和管理 TPM 中的所有字段是支持人员用户的必填字段。</span><span class="sxs-lookup"><span data-stu-id="d8488-179">All fields in Drive Recovery and Manage TPM are required fields for a Helpdesk User.</span></span>

    -   <span data-ttu-id="d8488-180">**MBAM 高级帮助台用户**：此本地组的成员对驱动器恢复具有高级访问权限，并在 MBAM 管理和监视网站上管理 TPM 功能。</span><span class="sxs-lookup"><span data-stu-id="d8488-180">**MBAM Advanced Helpdesk Users**: Members of this local group have advanced access to the Drive Recovery and Manage TPM features on the MBAM Administration and Monitoring website.</span></span> <span data-ttu-id="d8488-181">对于高级帮助台用户，驱动器恢复中仅需要 "**密钥 ID** " 字段。</span><span class="sxs-lookup"><span data-stu-id="d8488-181">For Advanced Helpdesk Users, only the **Key ID** field is required in Drive Recovery.</span></span> <span data-ttu-id="d8488-182">在 "管理 TPM" 中，仅需要 "**计算机域**字段" 和 "**计算机名称**" 字段。</span><span class="sxs-lookup"><span data-stu-id="d8488-182">In Manage TPM, only the **Computer Domain** field and **Computer Name** field are required.</span></span>

2.  <span data-ttu-id="d8488-183">在 "管理和监视" 服务器上，将用户添加到以下本地组，以使其能够访问 MBAM 管理和监视网站上的 "报告" 功能：</span><span class="sxs-lookup"><span data-stu-id="d8488-183">On the Administration and Monitoring Server, add users to the following local group to enable them to access the Reports feature on the MBAM Administration and Monitoring website:</span></span>

    -   <span data-ttu-id="d8488-184">**MBAM 报表用户**：此本地组的成员可以访问 MBAM 管理和监视网站上的报表功能。</span><span class="sxs-lookup"><span data-stu-id="d8488-184">**MBAM Report Users**: Members of this local group can access the Reports features on the MBAM Administration and Monitoring website.</span></span>

    -   <span data-ttu-id="d8488-185">通过您的公司名称、通知文本和其他特定于公司的信息，为自助服务门户提供品牌。</span><span class="sxs-lookup"><span data-stu-id="d8488-185">Brand the Self-Service Portal with your company name, notice text, and other company-specific information.</span></span> <span data-ttu-id="d8488-186">有关说明，请参阅[如何为自助服务门户提供品牌](how-to-brand-the-self-service-portal.md)。</span><span class="sxs-lookup"><span data-stu-id="d8488-186">For instructions, see [How to Brand the Self-Service Portal](how-to-brand-the-self-service-portal.md).</span></span>

    **<span data-ttu-id="d8488-187">注意</span><span class="sxs-lookup"><span data-stu-id="d8488-187">Note</span></span>**  
    <span data-ttu-id="d8488-188">**MBAM 报表**的相同用户或组成员身份必须在已安装 MBAM 管理和监视服务器功能、合规性和审核数据库以及合规性和审核报告的所有计算机上维护。</span><span class="sxs-lookup"><span data-stu-id="d8488-188">Identical user or group membership of the **MBAM Report Users** local group must be maintained on all computers where the MBAM Administration and Monitoring Server features, Compliance and Audit Database, and Compliance and Audit Reports are installed.</span></span> <span data-ttu-id="d8488-189">执行此操作的推荐方法是创建域安全组，并将该域组添加到每个本地 MBAM Report Users 组。</span><span class="sxs-lookup"><span data-stu-id="d8488-189">The recommended way to do this is to create a domain security group and add that domain group to each local MBAM Report Users group.</span></span> <span data-ttu-id="d8488-190">使用此过程时，按域组的方式管理组成员身份。</span><span class="sxs-lookup"><span data-stu-id="d8488-190">When you use this process, manage the group memberships by way of the domain group.</span></span>



## <span data-ttu-id="d8488-191">验证 MBAM 服务器功能安装</span><span class="sxs-lookup"><span data-stu-id="d8488-191">Validating the MBAM Server feature installation</span></span>


<span data-ttu-id="d8488-192">当 Microsoft BitLocker 管理和监视安装完成后，请验证安装是否已成功设置 BitLocker 管理所需的所有必需的 MBAM 功能。</span><span class="sxs-lookup"><span data-stu-id="d8488-192">When the Microsoft BitLocker Administration and Monitoring installation is completed, validate that the installation has successfully set up all the necessary MBAM features that are required for BitLocker management.</span></span> <span data-ttu-id="d8488-193">使用以下过程确认 MBAM 服务是否正常工作。</span><span class="sxs-lookup"><span data-stu-id="d8488-193">Use the following procedure to confirm that the MBAM service is functional.</span></span>

**<span data-ttu-id="d8488-194">验证 MBAM 服务器功能安装</span><span class="sxs-lookup"><span data-stu-id="d8488-194">To validate the MBAM Server feature installation</span></span>**

1. <span data-ttu-id="d8488-195">在部署 MBAM 功能的每台服务器上，打开 **"控制面板"**。</span><span class="sxs-lookup"><span data-stu-id="d8488-195">On each server where a MBAM feature is deployed, open **Control Panel**.</span></span> <span data-ttu-id="d8488-196">选择 "**程序**"，然后选择 "**程序和功能**"。</span><span class="sxs-lookup"><span data-stu-id="d8488-196">Select **Programs**, and then select **Programs and Features**.</span></span> <span data-ttu-id="d8488-197">验证 "**程序和功能**" 列表中是否显示 " **Microsoft BitLocker 管理和监视**"。</span><span class="sxs-lookup"><span data-stu-id="d8488-197">Verify that **Microsoft BitLocker Administration and Monitoring** appears in the **Programs and Features** list.</span></span>

   **<span data-ttu-id="d8488-198">注意</span><span class="sxs-lookup"><span data-stu-id="d8488-198">Note</span></span>**  
   <span data-ttu-id="d8488-199">若要验证安装，必须使用在每台服务器上具有本地计算机管理凭据的域帐户。</span><span class="sxs-lookup"><span data-stu-id="d8488-199">To validate the installation, you must use a domain account that has local computer administrative credentials on each server.</span></span>



2. <span data-ttu-id="d8488-200">在安装了恢复数据库的服务器上，打开 SQL Server Management Studio，并验证是否已安装**MBAM 恢复和硬件**数据库。</span><span class="sxs-lookup"><span data-stu-id="d8488-200">On the server where the Recovery Database is installed, open SQL Server Management Studio, and verify that the **MBAM Recovery and Hardware** database is installed.</span></span>

3. <span data-ttu-id="d8488-201">在安装合规性和审核数据库的服务器上，打开 SQL Server Management Studio，并验证是否安装了**MBAM 合规性状态数据库**。</span><span class="sxs-lookup"><span data-stu-id="d8488-201">On the server where the Compliance and Audit Database is installed, open SQL Server Management Studio, and verify that the **MBAM Compliance Status Database** is installed.</span></span>

4. <span data-ttu-id="d8488-202">在安装合规性和审核报告的服务器上，使用管理凭据打开 web 浏览器，然后浏览到 SQL Server Reporting Services 网站的 "开始"。</span><span class="sxs-lookup"><span data-stu-id="d8488-202">On the server where the Compliance and Audit Reports are installed, open a web browser with administrative credentials and browse to the “Home” of the SQL Server Reporting Services site.</span></span>

   <span data-ttu-id="d8488-203">SQL Server Reporting Services 网站实例的默认主位置位于 http:// <em> &lt; NameofMBAMReportsServer &gt; </em> /Reports。</span><span class="sxs-lookup"><span data-stu-id="d8488-203">The default Home location of a SQL Server Reporting Services site instance is at http://<em>&lt;NameofMBAMReportsServer&gt;</em>/Reports.</span></span> <span data-ttu-id="d8488-204">若要查找实际 URL，请使用 Reporting Services 配置管理器工具，并选择在安装过程中指定的实例。</span><span class="sxs-lookup"><span data-stu-id="d8488-204">To find the actual URL, use the Reporting Services Configuration Manager tool and select the instances that are specified during setup.</span></span>

   <span data-ttu-id="d8488-205">确认名为 Microsoft BitLocker 管理和监视的报告文件夹包含名为 " **MaltaDataSource** " 的数据源，并且 " **en-us** " 文件夹包含四个报表。</span><span class="sxs-lookup"><span data-stu-id="d8488-205">Confirm that a Reports folder named Microsoft BitLocker Administration and Monitoring contains a data source called **MaltaDataSource** and that an **en-us** folder contains four reports.</span></span>

   **<span data-ttu-id="d8488-206">注意</span><span class="sxs-lookup"><span data-stu-id="d8488-206">Note</span></span>**  
   <span data-ttu-id="d8488-207">如果 SQL Server Reporting Services 配置为命名实例，则 URL 应类似于以下内容： http://\* &lt; NameofMBAMReportsServer &gt; */Reports\_* &lt; SRSInstanceName &gt; \*</span><span class="sxs-lookup"><span data-stu-id="d8488-207">If SQL Server Reporting Services was configured as a named instance, the URL should resemble the following: http://*&lt;NameofMBAMReportsServer&gt;*/Reports\_*&lt;SRSInstanceName&gt;*</span></span>



~~~
**Note**  
If SSRS was not configured to use Secure Socket Layer (SSL), the URL for the reports will be set to HTTP instead of HTTPS when you install the MBAM Server. If you then go to the Administration and Monitoring website and select a report, the following message appears: “Only Secure Content is Displayed.” To show the report, click **Show All Content**.
~~~



5. <span data-ttu-id="d8488-208">在安装了 "管理和监视" 功能的服务器上，运行 "**服务器管理器**" 并浏览到 "**角色**"。</span><span class="sxs-lookup"><span data-stu-id="d8488-208">On the server where the Administration and Monitoring feature is installed, run **Server Manager** and browse to **Roles**.</span></span> <span data-ttu-id="d8488-209">选择 " **Web 服务器（iis）**"，然后单击 " **Internet 信息服务（Iis）管理器"。**</span><span class="sxs-lookup"><span data-stu-id="d8488-209">Select **Web Server (IIS)**, and then click **Internet Information Services (IIS) Manager.**</span></span>

6. <span data-ttu-id="d8488-210">在 **"连接" 中，** 浏览到 " \* &lt; computername &gt; \*"，选择 "**网站**"，然后选择 " **Microsoft BitLocker 管理和监视**"。</span><span class="sxs-lookup"><span data-stu-id="d8488-210">In **Connections,** browse to *&lt;computername&gt;*, select **Sites**, and then select **Microsoft BitLocker Administration and Monitoring**.</span></span> <span data-ttu-id="d8488-211">验证 " **MBAMAdministrationService**"、" **MBAMUserSupportService**"、" **MBAMComplianceStatusService**" 和 " **MBAMRecoveryAndHardwareService** " 是否已列出。</span><span class="sxs-lookup"><span data-stu-id="d8488-211">Verify that **MBAMAdministrationService**, **MBAMUserSupportService**, **MBAMComplianceStatusService**, and **MBAMRecoveryAndHardwareService** are listed.</span></span>

7. <span data-ttu-id="d8488-212">在安装了 "管理" 和 "监视" 功能和 "自助服务" 门户的服务器上，打开具有管理凭据的 web 浏览器，然后浏览到以下位置以验证它们是否成功加载：</span><span class="sxs-lookup"><span data-stu-id="d8488-212">On the server where the Administration and Monitoring features and Self-Service Portal are installed, open a web browser with administrative credentials and browse to the following locations to verify that they load successfully:</span></span>

   -   <span data-ttu-id="d8488-213">*http:// &lt; 主机名 &gt; /HelpDesk/default.aspx*并确认导航和报表的每个链接</span><span class="sxs-lookup"><span data-stu-id="d8488-213">*http://&lt;hostname&gt;/HelpDesk/default.aspx* and confirm each of the links for navigation and reports</span></span>

   -   *<span data-ttu-id="d8488-214">http:// &lt; hostname &gt; /SelfService&gt;/</span><span class="sxs-lookup"><span data-stu-id="d8488-214">http://&lt;hostname&gt;/SelfService&gt;/</span></span>*

   -   *<span data-ttu-id="d8488-215">http:// &lt; computername &gt; /MBAMAdministrationService/AdministrationService.svc</span><span class="sxs-lookup"><span data-stu-id="d8488-215">http://&lt;computername&gt;/MBAMAdministrationService/AdministrationService.svc</span></span>*

   -   *<span data-ttu-id="d8488-216">http:// &lt; hostname &gt; /MBAMUserSupportService/UserSupportService.svc</span><span class="sxs-lookup"><span data-stu-id="d8488-216">http://&lt;hostname&gt;/MBAMUserSupportService/UserSupportService.svc</span></span>*

   -   *<span data-ttu-id="d8488-217">http:// &lt; computername &gt; /MBAMComplianceStatusService/StatusReportingService.svc</span><span class="sxs-lookup"><span data-stu-id="d8488-217">http://&lt;computername&gt;/MBAMComplianceStatusService/StatusReportingService.svc</span></span>*

   -   *<span data-ttu-id="d8488-218">http:// &lt; computername &gt; /MBAMRecoveryAndHardwareService/CoreService.svc</span><span class="sxs-lookup"><span data-stu-id="d8488-218">http://&lt;computername&gt;/MBAMRecoveryAndHardwareService/CoreService.svc</span></span>*

   **<span data-ttu-id="d8488-219">注意</span><span class="sxs-lookup"><span data-stu-id="d8488-219">Note</span></span>**  
   <span data-ttu-id="d8488-220">假设服务器功能安装在默认端口上，而不进行网络加密。</span><span class="sxs-lookup"><span data-stu-id="d8488-220">It is assumed that the server features were installed on the default port without network encryption.</span></span> <span data-ttu-id="d8488-221">如果你在其他端口或虚拟目录上安装了服务器功能，请将 url 更改为包含相应的端口，例如*http:// &lt; 主机名 &gt; ： &lt; port &gt; /HelpDesk/default.asp*x 或*http:// &lt; 主机名 &gt; ： &lt; port &gt; / &lt; virtualdirectory &gt; /default.aspx*</span><span class="sxs-lookup"><span data-stu-id="d8488-221">If you installed the server features on a different port or virtual directory, change the URLs to include the appropriate port, for example, *http://&lt;hostname&gt;:&lt;port&gt;/HelpDesk/default.asp*x or*http://&lt;hostname&gt;:&lt;port&gt;/&lt;virtualdirectory&gt;/default.aspx*</span></span>

   <span data-ttu-id="d8488-222">如果服务器功能是通过网络加密安装的，请将 http://更改为 https://。</span><span class="sxs-lookup"><span data-stu-id="d8488-222">If the server features were installed with network encryption, change http:// to https://.</span></span>



## <span data-ttu-id="d8488-223">相关主题</span><span class="sxs-lookup"><span data-stu-id="d8488-223">Related topics</span></span>


[<span data-ttu-id="d8488-224">部署 MBAM 2.0 服务器基础结构</span><span class="sxs-lookup"><span data-stu-id="d8488-224">Deploying the MBAM 2.0 Server Infrastructure</span></span>](deploying-the-mbam-20-server-infrastructure-mbam-2.md)









