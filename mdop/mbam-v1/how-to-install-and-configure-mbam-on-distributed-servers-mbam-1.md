---
title: 如何在分布式服务器上安装和配置 MBAM
description: 如何在分布式服务器上安装和配置 MBAM
author: dansimp
ms.assetid: 9ee766aa-6339-422a-8d00-4f58e4646a5e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 51f56a12d4e59226f834c7e474af0f1e96c1e8e9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803812"
---
# <span data-ttu-id="67dc7-103">如何在分布式服务器上安装和配置 MBAM</span><span class="sxs-lookup"><span data-stu-id="67dc7-103">How to Install and Configure MBAM on Distributed Servers</span></span>


<span data-ttu-id="67dc7-104">本主题中的过程介绍了分布式服务器上的 Microsoft BitLocker 管理和监视（MBAM）功能的完整安装。</span><span class="sxs-lookup"><span data-stu-id="67dc7-104">The procedures in this topic describe the full installation of the Microsoft BitLocker Administration and Monitoring (MBAM) features on distributed servers.</span></span>

<span data-ttu-id="67dc7-105">每个服务器功能都具有特定的先决条件。</span><span class="sxs-lookup"><span data-stu-id="67dc7-105">Each server feature has certain prerequisites.</span></span> <span data-ttu-id="67dc7-106">若要验证你是否满足先决条件和硬件和软件要求，请参阅[MBAM 1.0 部署先决条件](mbam-10-deployment-prerequisites.md)和[MBAM 1.0 支持的配置](mbam-10-supported-configurations.md)。</span><span class="sxs-lookup"><span data-stu-id="67dc7-106">To verify that you have met the prerequisites and hardware and software requirements, see [MBAM 1.0 Deployment Prerequisites](mbam-10-deployment-prerequisites.md) and [MBAM 1.0 Supported Configurations](mbam-10-supported-configurations.md).</span></span> <span data-ttu-id="67dc7-107">此外，某些功能需要你在安装过程中提供特定信息才能成功部署该功能。</span><span class="sxs-lookup"><span data-stu-id="67dc7-107">In addition, some features require that you provide certain information during the installation process to successfully deploy the feature.</span></span>

**<span data-ttu-id="67dc7-108">注意</span><span class="sxs-lookup"><span data-stu-id="67dc7-108">Note</span></span>**  
<span data-ttu-id="67dc7-109">若要获取安装程序日志文件，必须通过使用**msiexec**程序包和 \*\*/l &lt; LOCATION &gt; \*\*选项来安装 MBAM。</span><span class="sxs-lookup"><span data-stu-id="67dc7-109">To obtain the setup log files, you have to install MBAM by using the **msiexec** package and the **/l &lt;location&gt;** option.</span></span> <span data-ttu-id="67dc7-110">将在您指定的位置创建日志文件。</span><span class="sxs-lookup"><span data-stu-id="67dc7-110">Log files are created in the location that you specify.</span></span>

<span data-ttu-id="67dc7-111">其他安装日志文件将在运行 MBAM 安装的用户的% temp% 文件夹中创建。</span><span class="sxs-lookup"><span data-stu-id="67dc7-111">Additional setup log files are created in the %temp% folder of the user that runs the MBAM installation.</span></span>



## <a href="" id="deploy-the-mbam-server-features-"></a><span data-ttu-id="67dc7-112">部署 MBAM 服务器功能</span><span class="sxs-lookup"><span data-stu-id="67dc7-112">Deploy the MBAM Server features</span></span>


<span data-ttu-id="67dc7-113">以下步骤介绍了如何安装常规 MBAM 功能。</span><span class="sxs-lookup"><span data-stu-id="67dc7-113">The following steps describe how to install the general MBAM features.</span></span>

**<span data-ttu-id="67dc7-114">注意</span><span class="sxs-lookup"><span data-stu-id="67dc7-114">Note</span></span>**  
<span data-ttu-id="67dc7-115">请确保在32位服务器上使用32位设置，并在64服务器上使用64位设置。</span><span class="sxs-lookup"><span data-stu-id="67dc7-115">Make sure that you use the 32-bit setup on 32-bit servers and the 64-bit setup on 64-bit servers.</span></span>



**<span data-ttu-id="67dc7-116">部署 MBAM 服务器功能</span><span class="sxs-lookup"><span data-stu-id="67dc7-116">To Deploy MBAM Server features</span></span>**

1.  <span data-ttu-id="67dc7-117">启动 MBAM 安装向导，然后单击 "欢迎" 页面上的 "**安装**"。</span><span class="sxs-lookup"><span data-stu-id="67dc7-117">Start the MBAM installation wizard, and click **Install** at the Welcome page.</span></span>

2.  <span data-ttu-id="67dc7-118">阅读并接受 Microsoft 软件许可条款，然后单击 "**下一步**" 继续安装。</span><span class="sxs-lookup"><span data-stu-id="67dc7-118">Read and accept the Microsoft Software License Terms, and then click **Next** to continue the installation.</span></span>

3.  <span data-ttu-id="67dc7-119">默认情况下，将选择所有 MBAM 功能进行安装。</span><span class="sxs-lookup"><span data-stu-id="67dc7-119">By default, all MBAM features are selected for installation.</span></span> <span data-ttu-id="67dc7-120">清除要在别处安装的功能。</span><span class="sxs-lookup"><span data-stu-id="67dc7-120">Clear the features that you want to install elsewhere.</span></span> <span data-ttu-id="67dc7-121">要在同一台计算机上安装的功能必须同时安装。</span><span class="sxs-lookup"><span data-stu-id="67dc7-121">Features that you want to install on the same computer must be installed all at the same time.</span></span> <span data-ttu-id="67dc7-122">MBAM 功能必须按以下顺序安装：</span><span class="sxs-lookup"><span data-stu-id="67dc7-122">MBAM features must be installed in the following order:</span></span>

    -   <span data-ttu-id="67dc7-123">恢复和硬件数据库</span><span class="sxs-lookup"><span data-stu-id="67dc7-123">Recovery and Hardware Database</span></span>

    -   <span data-ttu-id="67dc7-124">合规性和审核数据库</span><span class="sxs-lookup"><span data-stu-id="67dc7-124">Compliance and Audit Database</span></span>

    -   <span data-ttu-id="67dc7-125">合规性审核和报告</span><span class="sxs-lookup"><span data-stu-id="67dc7-125">Compliance Audit and Reports</span></span>

    -   <span data-ttu-id="67dc7-126">管理和监视服务器</span><span class="sxs-lookup"><span data-stu-id="67dc7-126">Administration and Monitoring Server</span></span>

    -   <span data-ttu-id="67dc7-127">MBAM 组策略模板</span><span class="sxs-lookup"><span data-stu-id="67dc7-127">MBAM Group Policy Template</span></span>

    **<span data-ttu-id="67dc7-128">注意</span><span class="sxs-lookup"><span data-stu-id="67dc7-128">Note</span></span>**  
    <span data-ttu-id="67dc7-129">安装向导将检查安装的先决条件，并显示缺少的必备条件。</span><span class="sxs-lookup"><span data-stu-id="67dc7-129">The installation wizard checks the prerequisites for your installation and displays the prerequisites that are missing.</span></span> <span data-ttu-id="67dc7-130">如果满足所有先决条件，安装将继续。</span><span class="sxs-lookup"><span data-stu-id="67dc7-130">If all the prerequisites are met, the installation continues.</span></span> <span data-ttu-id="67dc7-131">如果检测到缺少先决条件，则必须解决缺少的先决条件，然后再次单击 "**检查必备项**"。</span><span class="sxs-lookup"><span data-stu-id="67dc7-131">If a missing prerequisite is detected, you have to resolve the missing prerequisites, and then click **Check prerequisites again**.</span></span> <span data-ttu-id="67dc7-132">如果此时间满足所有先决条件，安装将继续。</span><span class="sxs-lookup"><span data-stu-id="67dc7-132">If all prerequisites are met this time, the installation will resume.</span></span>



4.  <span data-ttu-id="67dc7-133">MBAM 安装向导将显示所选功能的安装页面。</span><span class="sxs-lookup"><span data-stu-id="67dc7-133">The MBAM Setup wizard will display the installation pages for the selected features.</span></span> <span data-ttu-id="67dc7-134">以下部分介绍了每个功能的安装过程。</span><span class="sxs-lookup"><span data-stu-id="67dc7-134">The following sections describe the installation procedures for each feature.</span></span>

    **<span data-ttu-id="67dc7-135">注意</span><span class="sxs-lookup"><span data-stu-id="67dc7-135">Note</span></span>**  
    <span data-ttu-id="67dc7-136">通常情况下，每个功能都安装在单独的服务器上。</span><span class="sxs-lookup"><span data-stu-id="67dc7-136">Typically, each feature is installed on a separate server.</span></span> <span data-ttu-id="67dc7-137">如果要在一台服务器上安装多个功能，您可以更改或删除以下某些步骤。</span><span class="sxs-lookup"><span data-stu-id="67dc7-137">If you want to install multiple features on a single server, you may change or eliminate some of the following steps.</span></span>



~~~
**To install the Recovery and Hardware Database**

1.  Choose an option for MBAM communication encryption. MBAM can encrypt the communication between the Recovery and Hardware Database and the Administration and Monitoring servers. If you choose the option to encrypt communication, you are asked to select the authority-provisioned certificate that is used for encryption.

2.  Click **Next** to continue.

3.  Specify the names of the computers that will be running the Administration and Monitoring Server feature, to configure access to the Recovery and Hardware Database.. Once the Administration and Monitoring Server feature is deployed, it connects to the database by using its domain account.

4.  Click **Next** to continue.

5.  Specify the **Database Configuration** for the SQL Server instance that stores the recovery and hardware data. You must also specify where the database will be located and where the log information will be located.

6.  Click **Next** to continue with the MBAM Setup wizard.

**To install the Compliance and Audit Database**

1.  Choose an option for the MBAM communication encryption. MBAM can encrypt the communication between the Compliance and Audit Database and the Administration and Monitoring servers. If you choose the option to encrypt communication, you are asked to select the authority-provisioned certificate that will be used for encryption.

2.  Click **Next** to continue.

3.  Specify the user account that will be used to access the database for reports.

4.  Click **Next** to continue.

5.  Specify the computer names of the computers that you want to run the Administration and Monitoring Server and the Compliance and Audit Reports, to configure the access to the Compliance and Audit Database.. After the Administration and Monitoring and the Compliance and Audit Reports Server are deployed, they will connect to the databases by using their domain accounts.

6.  Specify the **Database Configuration** for the SQL Server instance that will store the compliance and audit data. You must also specify where the database will be located and where the log information will be located.

7.  Click **Next** to continue with the MBAM Setup wizard.

**To install the Compliance and Audit Reports**

1.  Specify the remote SQL Server instance. For example, *&lt;ServerName&gt;*,where the Compliance and Audit Database are installed.

2.  Specify the name of the Compliance and Audit Database. By default, the database name is “MBAM Compliance Status”, but you can change the name when you install the Compliance and Audit Database.

3.  Click **Next** to continue.

4.  Select the SQL Server Reporting Services instance where the Compliance and Audit Reports will be installed. Provide the username and password used to access the compliance database.

5.  Click **Next** to continue with the MBAM Setup wizard.

**To install the Administration and Monitoring Server feature**

1.  Choose an option for the MBAM communication encryption. MBAM can encrypt the communication between the Recovery and Hardware Database and the Administration and Monitoring servers. If you choose the option to encrypt communication, you are asked to select the authority-provisioned certificate that is used for encryption.

2.  Click **Next** to continue.

3.  Specify the remote SQL Server instance, For example, *&lt;ServerName&gt;*, where the Compliance and Audit Database are installed.

4.  Specify the name of the Compliance and Audit Database. By default, the database name is MBAM Compliance Status, but, you can change the name when you install the Compliance and Audit Database.

5.  Click **Next** to continue.

6.  Specify the remote SQL Server instance. For example, *&lt;ServerName&gt;*,where the Recovery and Hardware Database are installed.

7.  Specify the name of the Recovery and Hardware Database. By default, the database name is **MBAM Recovery and Hardware**, but you can change the name when you install the Recovery and Hardware Database feature.

8.  Click **Next** to continue.

9.  Specify the URL for the “Home” of the SQL Server Reporting Services (SRS) site. The default Home location of a SQL Server Reporting Services site instance is at:

    http://*&lt;NameofMBAMReportsServer&gt;/*ReportServer

    **Note**  
    If you configured the SQL Server Reporting Services as a named instance, the URL resembles the following:http://*&lt;NameofMBAMReportsServer&gt;*/ReportServer\_*&lt;SRSInstanceName&gt;*



10. Click **Next** to continue.

11. Enter the **Port Number**, the **Host Name** (optional), and the **Installation Path** for the MBAM Administration and Monitoring server

    **Warning**  
    The port number that you specify must be an unused port number on the Administration and Monitoring server, unless you specify a unique host header name.



12. Click **Next** to continue with the MBAM Setup wizard.
~~~

5. 

   <span data-ttu-id="67dc7-138">指定是否使用 Microsoft 更新来帮助保护您的计算机安全，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="67dc7-138">Specify whether to use Microsoft Updates to help keep your computer secure, and then click **Next**.</span></span>

6. <span data-ttu-id="67dc7-139">所选的 MBAM 功能信息完成后，即可使用设置向导启动 MBAM 安装。</span><span class="sxs-lookup"><span data-stu-id="67dc7-139">When the selected MBAM feature information is complete, you are ready to start the MBAM installation by using the Setup wizard.</span></span> <span data-ttu-id="67dc7-140">如果必须查看或更改安装设置，请单击 "**返回**" 以在向导中移动。</span><span class="sxs-lookup"><span data-stu-id="67dc7-140">Click **Back** to move through the wizard if you have to review or change your installation settings.</span></span> <span data-ttu-id="67dc7-141">单击 "**安装**" 以开始安装。</span><span class="sxs-lookup"><span data-stu-id="67dc7-141">Click **Install** to begin the installation.</span></span> <span data-ttu-id="67dc7-142">单击 "**取消**" 退出向导。</span><span class="sxs-lookup"><span data-stu-id="67dc7-142">Click **Cancel** to exit the Wizard.</span></span> <span data-ttu-id="67dc7-143">安装程序安装你选择的 MBAM 功能并通知你安装已完成。</span><span class="sxs-lookup"><span data-stu-id="67dc7-143">Setup installs the MBAM features that you selected and notifies you that the installation is finished.</span></span>

7. <span data-ttu-id="67dc7-144">单击 "**完成**" 退出向导。</span><span class="sxs-lookup"><span data-stu-id="67dc7-144">Click **Finish** to exit the wizard.</span></span>

8. <span data-ttu-id="67dc7-145">在安装 MBAM 服务器功能后，将用户添加到相应的 MBAM 角色。</span><span class="sxs-lookup"><span data-stu-id="67dc7-145">Add users to appropriate MBAM roles, after the MBAM server features are installed..</span></span> <span data-ttu-id="67dc7-146">有关详细信息，请参阅[规划 MBAM 1.0 管理员角色](planning-for-mbam-10-administrator-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="67dc7-146">For more information, see [Planning for MBAM 1.0 Administrator Roles](planning-for-mbam-10-administrator-roles.md).</span></span>

**<span data-ttu-id="67dc7-147">安装后配置</span><span class="sxs-lookup"><span data-stu-id="67dc7-147">Post-installation configuration</span></span>**

1.  <span data-ttu-id="67dc7-148">在 MBAM 设置完成后，你必须添加用户角色，然后用户才能访问 MBAM 管理网站中的功能。</span><span class="sxs-lookup"><span data-stu-id="67dc7-148">After MBAM Setup is finished, you must add user Roles before users can access to features in the MBAM administration website.</span></span> <span data-ttu-id="67dc7-149">在 "管理和监视" 服务器上，将用户添加到以下本地组。</span><span class="sxs-lookup"><span data-stu-id="67dc7-149">On the Administration and Monitoring Server, add users to the following local groups.</span></span>

    -   <span data-ttu-id="67dc7-150">**MBAM 硬件用户**：此本地组的成员可以访问 MBAM 管理网站中的硬件功能。</span><span class="sxs-lookup"><span data-stu-id="67dc7-150">**MBAM Hardware Users**: Members of this local group can access the Hardware feature in the MBAM administration website.</span></span>

    -   <span data-ttu-id="67dc7-151">**MBAM 支持人员用户**：此本地组的成员可以在 MBAM 管理网站中访问驱动器恢复和管理受信任的平台模块（TPM）功能。</span><span class="sxs-lookup"><span data-stu-id="67dc7-151">**MBAM Helpdesk Users**: Members of this local group can access the Drive Recovery and Manage Trusted Platform Modules (TPM) features in the MBAM administration website.</span></span> <span data-ttu-id="67dc7-152">驱动器恢复和管理 TPM 中的所有字段是支持人员用户的必填字段。</span><span class="sxs-lookup"><span data-stu-id="67dc7-152">All fields in Drive Recovery and Manage TPM are required fields for a Helpdesk User.</span></span>

    -   <span data-ttu-id="67dc7-153">**MBAM 高级帮助台用户**：此本地组的成员对驱动器恢复具有高级访问权限，并在 MBAM 管理网站中管理 TPM 功能。</span><span class="sxs-lookup"><span data-stu-id="67dc7-153">**MBAM Advanced Helpdesk Users**: Members of this local group have advanced access to the Drive Recovery and Manage TPM features in the MBAM administration website.</span></span> <span data-ttu-id="67dc7-154">对于高级帮助台用户，驱动器恢复中仅需要 "密钥 ID" 字段。</span><span class="sxs-lookup"><span data-stu-id="67dc7-154">For Advanced Helpdesk Users, only the Key ID field is required in Drive Recovery.</span></span> <span data-ttu-id="67dc7-155">在 "管理 TPM" 中，仅需要 "计算机域字段" 和 "计算机名称" 字段。</span><span class="sxs-lookup"><span data-stu-id="67dc7-155">In Manage TPM, only the Computer Domain field and Computer Name field are required.</span></span>

2.  <span data-ttu-id="67dc7-156">在管理和监视服务器、合规性和审核数据库以及托管合规性和审核报告的服务器上，将用户添加到以下本地组，以便他们可以访问 MBAM 管理网站中的 "报告" 功能。</span><span class="sxs-lookup"><span data-stu-id="67dc7-156">On the Administration and Monitoring Server, Compliance and Audit Database, and on the server that hosts the Compliance and Audit Reports, add users to the following local group to give them access to the Reports feature in the MBAM administration website.</span></span>

    -   <span data-ttu-id="67dc7-157">**MBAM 报表用户**：此本地组的成员可以访问 MBAM 管理网站中的报表。</span><span class="sxs-lookup"><span data-stu-id="67dc7-157">**MBAM Report Users**: Members of this local group can access the Reports in the MBAM administration website.</span></span>

    **<span data-ttu-id="67dc7-158">注意</span><span class="sxs-lookup"><span data-stu-id="67dc7-158">Note</span></span>**  
    <span data-ttu-id="67dc7-159">**MBAM 报表**的相同用户或组成员身份必须在所有计算机上维护，这些用户本地组 MBAM 管理和监视服务器功能、合规性和审核数据库以及合规性和审核报告已安装。</span><span class="sxs-lookup"><span data-stu-id="67dc7-159">Identical user or group membership of the **MBAM Report Users** local group must be maintained on all computers where the MBAM Administration and Monitoring Server features, Compliance and Audit Database, and the Compliance and Audit Reports are installed.</span></span>



## <span data-ttu-id="67dc7-160">验证 MBAM 服务器功能安装</span><span class="sxs-lookup"><span data-stu-id="67dc7-160">Validate the MBAM Server feature installation</span></span>


<span data-ttu-id="67dc7-161">MBAM 服务器功能安装完成后，应验证安装是否已成功设置 MBAM 的所有必要功能。</span><span class="sxs-lookup"><span data-stu-id="67dc7-161">When the MBAM Server feature installation is complete, you should validate that the installation has successfully set up all the necessary features for MBAM.</span></span> <span data-ttu-id="67dc7-162">使用以下过程确认 MBAM 服务是否正常工作。</span><span class="sxs-lookup"><span data-stu-id="67dc7-162">Use the following procedure to confirm that the MBAM service is functional.</span></span>

**<span data-ttu-id="67dc7-163">验证 MBAM 安装</span><span class="sxs-lookup"><span data-stu-id="67dc7-163">To validate an MBAM installation</span></span>**

1. <span data-ttu-id="67dc7-164">在每台已部署 MBAM 功能的服务器上，打开 "**控制面板**"，单击 "**程序**"，然后单击 "**程序和功能**"。</span><span class="sxs-lookup"><span data-stu-id="67dc7-164">On each server, where an MBAM feature is deployed, open **Control Panel**, click **Programs**, and then click **Programs and Features**.</span></span> <span data-ttu-id="67dc7-165">验证 "**程序和功能**" 列表中是否显示 " **Microsoft BitLocker 管理和监视**"。</span><span class="sxs-lookup"><span data-stu-id="67dc7-165">Verify that **Microsoft BitLocker Administration and Monitoring** appears in the **Programs and Features** list.</span></span>

   **<span data-ttu-id="67dc7-166">注意</span><span class="sxs-lookup"><span data-stu-id="67dc7-166">Note</span></span>**  
   <span data-ttu-id="67dc7-167">若要验证 MBAM 安装，必须使用在每台服务器上具有本地计算机管理凭据的域帐户。</span><span class="sxs-lookup"><span data-stu-id="67dc7-167">To validate the MBAM installation, you must use a Domain Account that has local computer administrative credentials on each server.</span></span>



2. <span data-ttu-id="67dc7-168">在安装了恢复和硬件数据库的服务器上，打开 SQL Server Management Studio 并验证是否已安装**MBAM 恢复和硬件**数据库。</span><span class="sxs-lookup"><span data-stu-id="67dc7-168">On the server where the Recovery and Hardware Database is installed, open SQL Server Management Studio and verify that the **MBAM Recovery and Hardware** database is installed.</span></span>

3. <span data-ttu-id="67dc7-169">在安装合规性和审核数据库的服务器上，打开 SQL Server Management Studio 并验证是否已安装**MBAM 合规性状态**数据库。</span><span class="sxs-lookup"><span data-stu-id="67dc7-169">On the server where the Compliance and Audit Database is installed, open SQL Server Management Studio and verify that the **MBAM Compliance Status** database is installed.</span></span>

4. <span data-ttu-id="67dc7-170">在安装合规性和审核报告的服务器上，打开具有管理权限的 web 浏览器，然后浏览到 SQL Server Reporting Services 网站的 "开始"。</span><span class="sxs-lookup"><span data-stu-id="67dc7-170">On the server where the Compliance and Audit Reports are installed, open a web browser with administrative privileges and browse to the “Home” of the SQL Server Reporting Services site.</span></span>

   <span data-ttu-id="67dc7-171">SQL Server Reporting Services 网站实例的默认起始位置可在 http:// <em> &lt; NameofMBAMReportsServer &gt; </em> /Reports.aspx. 中找到</span><span class="sxs-lookup"><span data-stu-id="67dc7-171">The default Home location of a SQL Server Reporting Services site instance can be found at http://<em>&lt;NameofMBAMReportsServer&gt;</em>/Reports.aspx.</span></span> <span data-ttu-id="67dc7-172">若要查找实际 URL，请使用 Reporting Services 配置管理器工具，并选择在安装过程中指定的实例。</span><span class="sxs-lookup"><span data-stu-id="67dc7-172">To find the actual URL, use the Reporting Services Configuration Manager tool and select the instances specified during setup.</span></span>

   <span data-ttu-id="67dc7-173">确认列出了名为 "**马耳他合规性报告**" 的文件夹，其中包含五个报表和一个数据源。</span><span class="sxs-lookup"><span data-stu-id="67dc7-173">Confirm that a folder named **Malta Compliance Reports** is listed and that it contains five reports and one data source.</span></span>

   **<span data-ttu-id="67dc7-174">注意</span><span class="sxs-lookup"><span data-stu-id="67dc7-174">Note</span></span>**  
   <span data-ttu-id="67dc7-175">如果 SQL Server Reporting Services 配置为命名实例，则 URL 应类似于以下内容： http：//\* &lt; NameofMBAMReportsServer &gt; */Reports\_* &lt; SRSInstanceName &gt; \*</span><span class="sxs-lookup"><span data-stu-id="67dc7-175">If SQL Server Reporting Services was configured as a named instance, the URL should resemble the following:http://*&lt;NameofMBAMReportsServer&gt;*/Reports\_*&lt;SRSInstanceName&gt;*</span></span>



5. <span data-ttu-id="67dc7-176">在安装了 "管理和监视" 功能的服务器上，运行 "**服务器管理器**" 并浏览到 "**角色**"，选择 " **Web 服务器（iis）**"，然后单击 " **Internet 信息服务（iis）管理器**"。</span><span class="sxs-lookup"><span data-stu-id="67dc7-176">On the server where the Administration and Monitoring feature is installed, run **Server Manager** and browse to **Roles**, select **Web Server (IIS)**, and then click **Internet Information Services (IIS) Manager**.</span></span> <span data-ttu-id="67dc7-177">在 "**连接**" 中，浏览到\* &lt; Computername &gt; \*，单击 "**网站**"，然后单击 " **Microsoft BitLocker 管理和监视**"。</span><span class="sxs-lookup"><span data-stu-id="67dc7-177">In **Connections** browse to *&lt;computername&gt;*, click **Sites**, and click **Microsoft BitLocker Administration and Monitoring**.</span></span> <span data-ttu-id="67dc7-178">验证 " **MBAMAdministrationService**"、" **MBAMComplianceStatusService**" 和 " **MBAMRecoveryAndHardwareService** " 是否已列出。</span><span class="sxs-lookup"><span data-stu-id="67dc7-178">Verify that **MBAMAdministrationService**, **MBAMComplianceStatusService**, and **MBAMRecoveryAndHardwareService** are listed.</span></span>

6. <span data-ttu-id="67dc7-179">在安装了 "管理和监视" 功能的服务器上，打开具有管理权限的 web 浏览器，然后浏览到 MBAM 网站中的以下位置，验证它们是否已成功加载：</span><span class="sxs-lookup"><span data-stu-id="67dc7-179">On the server where the Administration and Monitoring feature is installed, open a web browser with administrative privileges and browse to the following locations in the MBAM web site, to verify that they load successfully:</span></span>

   -   <span data-ttu-id="67dc7-180">*http:// &lt; computername &gt; /default.aspx*和确认导航和报表的每个链接</span><span class="sxs-lookup"><span data-stu-id="67dc7-180">*http://&lt;computername&gt;/default.aspx* and confirm each of the links for navigation and reports</span></span>

   -   *<span data-ttu-id="67dc7-181">http:// &lt; computername &gt; /MBAMAdministrationService/AdministrationService.svc</span><span class="sxs-lookup"><span data-stu-id="67dc7-181">http://&lt;computername&gt;/MBAMAdministrationService/AdministrationService.svc</span></span>*

   -   *<span data-ttu-id="67dc7-182">http:// &lt; computername &gt; /MBAMComplianceStatusService/StatusReportingService.svc</span><span class="sxs-lookup"><span data-stu-id="67dc7-182">http://&lt;computername&gt;/MBAMComplianceStatusService/StatusReportingService.svc</span></span>*

   -   *<span data-ttu-id="67dc7-183">http:// &lt; computername &gt; /MBAMRecoveryAndHardwareService/CoreService.svc</span><span class="sxs-lookup"><span data-stu-id="67dc7-183">http://&lt;computername&gt;/MBAMRecoveryAndHardwareService/CoreService.svc</span></span>*

   **<span data-ttu-id="67dc7-184">注意</span><span class="sxs-lookup"><span data-stu-id="67dc7-184">Note</span></span>**  
   <span data-ttu-id="67dc7-185">通常情况下，服务安装在默认端口80上，而不进行网络加密。</span><span class="sxs-lookup"><span data-stu-id="67dc7-185">Typically, services are installed on the default port 80 without network encryption.</span></span> <span data-ttu-id="67dc7-186">如果服务安装在其他端口上，请将 Url 更改为包含相应的端口。</span><span class="sxs-lookup"><span data-stu-id="67dc7-186">If the services are installed on a different port, change the URLs to include the appropriate port.</span></span> <span data-ttu-id="67dc7-187">例如，http://\* &lt; computername &gt; ： &lt; port &gt; \*/default.aspx 或 http:// <em> &lt; hostheadername &gt; / </em> 默认值 .aspx</span><span class="sxs-lookup"><span data-stu-id="67dc7-187">For example, http://*&lt;computername&gt;:&lt;port&gt;*/default.aspx or http://<em>&lt;hostheadername&gt;/</em>default.aspx</span></span>

   <span data-ttu-id="67dc7-188">如果服务是通过网络加密安装的，请将 http://更改为 https://。</span><span class="sxs-lookup"><span data-stu-id="67dc7-188">If the services were installed with network encryption, change http:// to https://.</span></span>



~~~
Verify that each web page loads successfully.
~~~

## <span data-ttu-id="67dc7-189">相关主题</span><span class="sxs-lookup"><span data-stu-id="67dc7-189">Related topics</span></span>


[<span data-ttu-id="67dc7-190">部署 MBAM 1.0 服务器基础结构</span><span class="sxs-lookup"><span data-stu-id="67dc7-190">Deploying the MBAM 1.0 Server Infrastructure</span></span>](deploying-the-mbam-10-server-infrastructure.md)









