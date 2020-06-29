---
title: 如何在单个服务器上安装和配置 MBAM
description: 如何在单个服务器上安装和配置 MBAM
author: dansimp
ms.assetid: 55841c63-bad9-44e7-b7fd-ea7037febbd7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 225f66493ceafce5461df3fcc6f701e9a2922a5f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803500"
---
# <span data-ttu-id="353b9-103">如何在单个服务器上安装和配置 MBAM</span><span class="sxs-lookup"><span data-stu-id="353b9-103">How to Install and Configure MBAM on a Single Server</span></span>


<span data-ttu-id="353b9-104">本主题中的过程介绍了单个服务器上的 Microsoft BitLocker 管理和监视（MBAM）功能的完整安装。</span><span class="sxs-lookup"><span data-stu-id="353b9-104">The procedures in this topic describe the full installation of the Microsoft BitLocker Administration and Monitoring (MBAM) features on a single server.</span></span>

<span data-ttu-id="353b9-105">每个服务器功能都具有特定的先决条件。</span><span class="sxs-lookup"><span data-stu-id="353b9-105">Each server feature has certain prerequisites.</span></span> <span data-ttu-id="353b9-106">若要验证你是否满足先决条件以及硬件和软件要求，请参阅[MBAM 1.0 部署先决条件](mbam-10-deployment-prerequisites.md)和[MBAM 1.0 支持的配置](mbam-10-supported-configurations.md)。</span><span class="sxs-lookup"><span data-stu-id="353b9-106">To verify that you have met the prerequisites and the hardware and software requirements, see [MBAM 1.0 Deployment Prerequisites](mbam-10-deployment-prerequisites.md) and [MBAM 1.0 Supported Configurations](mbam-10-supported-configurations.md).</span></span> <span data-ttu-id="353b9-107">此外，某些功能还包含安装过程中必须提供的信息才能成功部署该功能。</span><span class="sxs-lookup"><span data-stu-id="353b9-107">In addition, some features also have information that must be provided during the installation process to successfully deploy the feature.</span></span> <span data-ttu-id="353b9-108">在开始 MBAM 部署之前，还应查看[准备 MBAM 1.0 的环境](preparing-your-environment-for-mbam-10.md)。</span><span class="sxs-lookup"><span data-stu-id="353b9-108">You should also review [Preparing your Environment for MBAM 1.0](preparing-your-environment-for-mbam-10.md) before you begin the MBAM deployment.</span></span>

<span data-ttu-id="353b9-109">**注意** 若要获取安装程序日志文件，必须通过使用**msiexec**程序包和 **/l** &lt; location 选项来安装 MBAM &gt; 。</span><span class="sxs-lookup"><span data-stu-id="353b9-109">**Note** To obtain the setup log files, you must install MBAM by using the **msiexec** package and the **/l** &lt;location&gt; option.</span></span> <span data-ttu-id="353b9-110">将在您指定的位置创建日志文件。</span><span class="sxs-lookup"><span data-stu-id="353b9-110">Log files are created in the location that you specify.</span></span>

<span data-ttu-id="353b9-111">在安装 MBAM 的用户的% temp% 文件夹中创建了其他安装日志文件。</span><span class="sxs-lookup"><span data-stu-id="353b9-111">Additional setup log files are created in the %temp% folder of the user who is installing MBAM.</span></span>

 

## <span data-ttu-id="353b9-112">在单个服务器上安装 MBAM 服务器功能</span><span class="sxs-lookup"><span data-stu-id="353b9-112">To install MBAM Server features on a single server</span></span>


<span data-ttu-id="353b9-113">以下步骤介绍了如何安装常规 MBAM 功能。</span><span class="sxs-lookup"><span data-stu-id="353b9-113">The following steps describe how to install general MBAM features.</span></span>

<span data-ttu-id="353b9-114">**注意** 请确保在32位服务器上使用32位设置，并在64服务器上使用64位设置。</span><span class="sxs-lookup"><span data-stu-id="353b9-114">**Note** Make sure that you use the 32-bit setup on 32-bit servers and the 64-bit setup on 64-bit servers.</span></span>

 

**<span data-ttu-id="353b9-115">启动 MBAM Server 功能安装</span><span class="sxs-lookup"><span data-stu-id="353b9-115">To start MBAM Server features installation</span></span>**

1.  <span data-ttu-id="353b9-116">启动 MBAM 安装向导。</span><span class="sxs-lookup"><span data-stu-id="353b9-116">Start the MBAM installation wizard.</span></span> <span data-ttu-id="353b9-117">单击欢迎页面上的 "**安装**"。</span><span class="sxs-lookup"><span data-stu-id="353b9-117">Click **Install** at the Welcome page.</span></span>

2.  <span data-ttu-id="353b9-118">阅读并接受 Microsoft 软件许可条款，然后单击 "**下一步**" 继续安装。</span><span class="sxs-lookup"><span data-stu-id="353b9-118">Read and accept the Microsoft Software License Terms, and then click **Next** to continue the installation.</span></span>

3.  <span data-ttu-id="353b9-119">默认情况下，将选择所有 MBAM 功能进行安装。</span><span class="sxs-lookup"><span data-stu-id="353b9-119">By default, all MBAM features are selected for installation.</span></span> <span data-ttu-id="353b9-120">将在同一台计算机上安装的功能必须同时安装。</span><span class="sxs-lookup"><span data-stu-id="353b9-120">Features that will be installed on the same computer must be installed together at the same time.</span></span> <span data-ttu-id="353b9-121">清除要在别处安装的功能。</span><span class="sxs-lookup"><span data-stu-id="353b9-121">Clear the features that you want to install elsewhere.</span></span> <span data-ttu-id="353b9-122">必须按以下顺序安装 MBAM 功能：</span><span class="sxs-lookup"><span data-stu-id="353b9-122">You must install the MBAM features in the following order:</span></span>

    -   <span data-ttu-id="353b9-123">恢复和硬件数据库</span><span class="sxs-lookup"><span data-stu-id="353b9-123">Recovery and Hardware Database</span></span>

    -   <span data-ttu-id="353b9-124">合规性和审核数据库</span><span class="sxs-lookup"><span data-stu-id="353b9-124">Compliance and Audit Database</span></span>

    -   <span data-ttu-id="353b9-125">合规性审核和报告</span><span class="sxs-lookup"><span data-stu-id="353b9-125">Compliance Audit and Reports</span></span>

    -   <span data-ttu-id="353b9-126">管理和监视服务器</span><span class="sxs-lookup"><span data-stu-id="353b9-126">Administration and Monitoring Server</span></span>

    -   <span data-ttu-id="353b9-127">MBAM 组策略模板</span><span class="sxs-lookup"><span data-stu-id="353b9-127">MBAM Group Policy Template</span></span>

    <span data-ttu-id="353b9-128">**注意** 安装向导将检查安装的先决条件，并显示缺少的必备条件。</span><span class="sxs-lookup"><span data-stu-id="353b9-128">**Note** The installation wizard checks the prerequisites for your installation and displays the prerequisites that are missing.</span></span> <span data-ttu-id="353b9-129">如果满足所有先决条件，安装将继续。</span><span class="sxs-lookup"><span data-stu-id="353b9-129">If all the prerequisites are met, the installation continues.</span></span> <span data-ttu-id="353b9-130">如果检测到缺少先决条件，则必须解决缺少的先决条件，然后再次单击 "**检查必备项**"。</span><span class="sxs-lookup"><span data-stu-id="353b9-130">If a missing prerequisite is detected, you must resolve the missing prerequisites, and then click **Check prerequisites again**.</span></span> <span data-ttu-id="353b9-131">满足所有先决条件后，安装将继续。</span><span class="sxs-lookup"><span data-stu-id="353b9-131">After all prerequisites are met, the installation resumes.</span></span>

     

4.  <span data-ttu-id="353b9-132">系统将提示您配置网络通信安全。</span><span class="sxs-lookup"><span data-stu-id="353b9-132">You are prompted to configure the network communication security.</span></span> <span data-ttu-id="353b9-133">MBAM 可以加密恢复和硬件数据库、管理和监视服务器以及客户端之间的通信。</span><span class="sxs-lookup"><span data-stu-id="353b9-133">MBAM can encrypt the communication between the Recovery and Hardware Database, the Administration and Monitoring Server, and the clients.</span></span> <span data-ttu-id="353b9-134">如果你决定加密通信，系统将要求你选择要用于加密的授权机构预配的证书。</span><span class="sxs-lookup"><span data-stu-id="353b9-134">If you decide to encrypt the communication, you are asked to select the authority-provisioned certificate that will be used for encryption.</span></span>

5.  <span data-ttu-id="353b9-135">单击**下一步**以继续。</span><span class="sxs-lookup"><span data-stu-id="353b9-135">Click **Next** to continue.</span></span>

6.  <span data-ttu-id="353b9-136">MBAM 安装向导将显示所选功能的安装页面。</span><span class="sxs-lookup"><span data-stu-id="353b9-136">The MBAM Setup wizard will display the installation pages for the selected features.</span></span>

**<span data-ttu-id="353b9-137">部署 MBAM 服务器功能</span><span class="sxs-lookup"><span data-stu-id="353b9-137">To deploy MBAM Server features</span></span>**

1.  <span data-ttu-id="353b9-138">在 "**配置恢复和硬件数据库**" 窗口中，指定 SQL Server 实例以及将存储恢复和硬件数据的数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="353b9-138">In the **Configure the Recovery and Hardware database** window, specify the instance of SQL Server and the name of the database that will store the recovery and hardware data.</span></span> <span data-ttu-id="353b9-139">你还必须同时指定数据库文件位置和日志信息位置。</span><span class="sxs-lookup"><span data-stu-id="353b9-139">You must also specify both the database files location and the log information location.</span></span>

2.  <span data-ttu-id="353b9-140">单击**下一步**以继续。</span><span class="sxs-lookup"><span data-stu-id="353b9-140">Click **Next** to continue.</span></span>

3.  <span data-ttu-id="353b9-141">在 "**配置合规性和审核数据库**" 窗口中，指定 SQL Server 实例以及将存储合规性和审核数据的数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="353b9-141">In the **Configure the Compliance and Audit database** window, specify the instance of the SQL Server and the name of the database that will store the compliance and audit data.</span></span> <span data-ttu-id="353b9-142">然后，指定数据库文件位置和日志信息位置。</span><span class="sxs-lookup"><span data-stu-id="353b9-142">Then, specify the database files location and the log information location.</span></span>

4.  <span data-ttu-id="353b9-143">单击**下一步**以继续。</span><span class="sxs-lookup"><span data-stu-id="353b9-143">Click **Next** to continue.</span></span>

5.  <span data-ttu-id="353b9-144">在 "**合规性和审核报告**" 窗口中，指定将使用的报表服务实例，并提供用于访问数据库的域用户帐户。</span><span class="sxs-lookup"><span data-stu-id="353b9-144">In the **Compliance and Audit Reports** window, specify the report service instance that will be used and provide a domain user account for accessing the database.</span></span> <span data-ttu-id="353b9-145">这应该是专为此用途预配的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="353b9-145">This should be a user account that is provisioned specifically for this use.</span></span> <span data-ttu-id="353b9-146">用户帐户应该能够访问 MBAM Reports Users 组中所有可用的数据。</span><span class="sxs-lookup"><span data-stu-id="353b9-146">The user account should be able to access all data available to the MBAM Reports Users group.</span></span>

6.  <span data-ttu-id="353b9-147">单击**下一步**以继续。</span><span class="sxs-lookup"><span data-stu-id="353b9-147">Click **Next** to continue.</span></span>

7.  <span data-ttu-id="353b9-148">在 "**配置管理和监视服务器**" 窗口中，输入**端口绑定**、**主机名**（可选）和 MBAM 管理和监视服务器的**安装路径**。</span><span class="sxs-lookup"><span data-stu-id="353b9-148">In the **Configure the Administration and Monitoring Server** window, enter the **Port Binding**, the **Host Name** (optional), and the **Installation Path** for the MBAM Administration and Monitoring server.</span></span>

    <span data-ttu-id="353b9-149">**警告** 你指定的端口号必须是管理和监视服务器上未使用的端口号，除非指定了唯一的主机标题名称。</span><span class="sxs-lookup"><span data-stu-id="353b9-149">**Warning** The port number that you specify must be an unused port number on the Administration and Monitoring server, unless a unique host header name is specified.</span></span>

     

8.  <span data-ttu-id="353b9-150">单击**下一步**以继续。</span><span class="sxs-lookup"><span data-stu-id="353b9-150">Click **Next** to continue.</span></span>

9.  <span data-ttu-id="353b9-151">指定是否使用 Microsoft 更新来帮助保护您的计算机安全，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="353b9-151">Specify whether to use Microsoft Updates to help keep your computer secure, and then click **Next**.</span></span> <span data-ttu-id="353b9-152">Microsoft Update 选项不会打开 Windows 中的自动更新。</span><span class="sxs-lookup"><span data-stu-id="353b9-152">The Microsoft Updates option does not turn on the Automatic Updates in Windows.</span></span>

10. <span data-ttu-id="353b9-153">当安装向导收集了必要的功能信息时，MBAM 安装已准备好开始。</span><span class="sxs-lookup"><span data-stu-id="353b9-153">When the Setup wizard has collected the necessary feature information, the MBAM installation is ready to start.</span></span> <span data-ttu-id="353b9-154">如果要查看或更改安装设置，请单击 "**返回**" 以在向导中向后移动。</span><span class="sxs-lookup"><span data-stu-id="353b9-154">Click **Back** to move back through the wizard if you want to review or change your installation settings.</span></span> <span data-ttu-id="353b9-155">单击 "**安装**" 以开始安装。</span><span class="sxs-lookup"><span data-stu-id="353b9-155">Click **Install** to begin the installation.</span></span> <span data-ttu-id="353b9-156">单击 "**取消**" 退出安装程序。</span><span class="sxs-lookup"><span data-stu-id="353b9-156">Click **Cancel** to exit Setup.</span></span> <span data-ttu-id="353b9-157">安装程序安装 MBAM 功能并通知您安装已完成。</span><span class="sxs-lookup"><span data-stu-id="353b9-157">Setup installs the MBAM features and notifies you that the installation is completed.</span></span>

11. <span data-ttu-id="353b9-158">单击 "**完成**" 退出向导。</span><span class="sxs-lookup"><span data-stu-id="353b9-158">Click **Finish** to exit the wizard.</span></span>

12. <span data-ttu-id="353b9-159">安装 MBAM server 功能后，必须将用户添加到 MBAM 角色。</span><span class="sxs-lookup"><span data-stu-id="353b9-159">After you install MBAM server features, you must add users to the MBAM roles.</span></span> <span data-ttu-id="353b9-160">有关详细信息，请参阅[规划 MBAM 1.0 管理员角色](planning-for-mbam-10-administrator-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="353b9-160">For more information, see [Planning for MBAM 1.0 Administrator Roles](planning-for-mbam-10-administrator-roles.md).</span></span>

**<span data-ttu-id="353b9-161">执行安装后配置</span><span class="sxs-lookup"><span data-stu-id="353b9-161">To perform post installation configuration</span></span>**

1.  <span data-ttu-id="353b9-162">安装完成后，你必须添加用户角色，以便你可以授予用户访问 MBAM 管理网站中的功能的权限。</span><span class="sxs-lookup"><span data-stu-id="353b9-162">After Setup is finished, you must add user roles so that you can give users access to features in the MBAM administration website.</span></span> <span data-ttu-id="353b9-163">在 "管理和监视" 服务器上，将用户添加到以下本地组：</span><span class="sxs-lookup"><span data-stu-id="353b9-163">On the Administration and Monitoring Server, add users to the following local groups:</span></span>

    -   <span data-ttu-id="353b9-164">**MBAM 硬件用户**：此本地组的成员可以访问 MBAM 管理网站中的硬件功能。</span><span class="sxs-lookup"><span data-stu-id="353b9-164">**MBAM Hardware Users**: Members of this local group can access the Hardware feature in the MBAM administration website.</span></span>

    -   <span data-ttu-id="353b9-165">**MBAM 帮助台用户**：此本地组的成员可以访问 MBAM 管理网站中的驱动器恢复和管理 TPM 功能。</span><span class="sxs-lookup"><span data-stu-id="353b9-165">**MBAM Helpdesk Users**: Members of this local group can access the Drive Recovery and Manage TPM features in the MBAM administration website.</span></span> <span data-ttu-id="353b9-166">驱动器恢复和管理 TPM 中的所有字段是支持人员用户的必填字段。</span><span class="sxs-lookup"><span data-stu-id="353b9-166">All fields in Drive Recovery and Manage TPM are required fields for a Helpdesk User.</span></span>

    -   <span data-ttu-id="353b9-167">**MBAM 高级帮助台用户**：此本地组的成员对驱动器恢复具有高级访问权限，并在 MBAM 管理网站中管理 TPM 功能。</span><span class="sxs-lookup"><span data-stu-id="353b9-167">**MBAM Advanced Helpdesk Users**: Members of this local group have advanced access to the Drive Recovery and Manage TPM features in the MBAM administration website.</span></span> <span data-ttu-id="353b9-168">对于高级帮助台用户，驱动器恢复中仅需要 "密钥 ID" 字段。</span><span class="sxs-lookup"><span data-stu-id="353b9-168">For Advanced Helpdesk Users, only the Key ID field is required in Drive Recovery.</span></span> <span data-ttu-id="353b9-169">对于 "管理 TPM 用户"，仅需要 "计算机域字段" 和 "计算机名称" 字段。</span><span class="sxs-lookup"><span data-stu-id="353b9-169">For Manage TPM users, only the Computer Domain field and Computer Name field are required.</span></span>

2.  <span data-ttu-id="353b9-170">在管理和监视服务器、合规性和审核数据库以及托管合规性和审核报告的计算机上，将用户添加到以下本地组以使其能够访问 MBAM 管理网站中的 "报告" 功能：</span><span class="sxs-lookup"><span data-stu-id="353b9-170">On the Administration and Monitoring Server, Compliance and Audit Database, and on the computer that hosts the Compliance and Audit Reports, add users to the following local group to enable them to access the Reports feature in the MBAM administration website:</span></span>

    -   <span data-ttu-id="353b9-171">**MBAM 报表用户**：此本地组的成员可以访问 MBAM 管理网站中的报表功能。</span><span class="sxs-lookup"><span data-stu-id="353b9-171">**MBAM Report Users**: Members of this local group can access the Reports features in the MBAM administration website.</span></span>

    <span data-ttu-id="353b9-172">**注意** **MBAM 报表**的相同用户成员身份或组成员身份必须在已安装管理和监视服务器功能、合规性和审核数据库以及合规性和审核报告的所有计算机上维护。</span><span class="sxs-lookup"><span data-stu-id="353b9-172">**Note** Identical user membership or group membership of the **MBAM Report Users** local group must be maintained on all computers where the Administration and Monitoring Server features, Compliance and Audit Database, and Compliance and Audit Reports are installed.</span></span>

    <span data-ttu-id="353b9-173">若要在所有计算机上保持相同的成员身份，你应该创建一个域安全组，并将该域组添加到每个本地 MBAM Report Users 组。</span><span class="sxs-lookup"><span data-stu-id="353b9-173">To maintain identical memberships on all computers, you should create a domain security group and add that domain group to each local MBAM Report Users group.</span></span> <span data-ttu-id="353b9-174">执行此操作时，可以使用 "域" 组管理组成员身份。</span><span class="sxs-lookup"><span data-stu-id="353b9-174">When you do this, you can manage the group memberships by using the domain group.</span></span>

     

## <span data-ttu-id="353b9-175">验证 MBAM 服务器功能安装</span><span class="sxs-lookup"><span data-stu-id="353b9-175">Validating the MBAM Server feature installation</span></span>


<span data-ttu-id="353b9-176">MBAM 安装完成后，验证安装是否已成功设置 BitLocker 管理所需的所有必需 MBAM 功能。</span><span class="sxs-lookup"><span data-stu-id="353b9-176">When the MBAM installation is complete, validate that the installation has successfully set up all the necessary MBAM features that are required for BitLocker management.</span></span> <span data-ttu-id="353b9-177">使用以下过程确认 MBAM 服务是否正常运行：</span><span class="sxs-lookup"><span data-stu-id="353b9-177">Use the following procedure to confirm that the MBAM service is functional:</span></span>

**<span data-ttu-id="353b9-178">验证 MBAM 服务器功能安装</span><span class="sxs-lookup"><span data-stu-id="353b9-178">To validate MBAM Server feature installation</span></span>**

1. <span data-ttu-id="353b9-179">在部署 MBAM 功能的每台服务器上，打开 **"控制面板"**。</span><span class="sxs-lookup"><span data-stu-id="353b9-179">On each server where an MBAM feature is deployed, open **Control Panel**.</span></span> <span data-ttu-id="353b9-180">单击 "**程序**"，然后单击 "**程序和功能**"。</span><span class="sxs-lookup"><span data-stu-id="353b9-180">Click **Programs**, and then click **Programs and Features**.</span></span> <span data-ttu-id="353b9-181">验证 "**程序和功能**" 列表中是否显示 " **Microsoft BitLocker 管理和监视**"。</span><span class="sxs-lookup"><span data-stu-id="353b9-181">Verify that **Microsoft BitLocker Administration and Monitoring** appears in the **Programs and Features** list.</span></span>

   **<span data-ttu-id="353b9-182">注意</span><span class="sxs-lookup"><span data-stu-id="353b9-182">Note</span></span>**  
   <span data-ttu-id="353b9-183">若要验证安装，必须使用在每台服务器上具有本地计算机管理凭据的域帐户。</span><span class="sxs-lookup"><span data-stu-id="353b9-183">To validate the installation, you must use a Domain Account that has local computer administrative credentials on each server.</span></span>

     

2. <span data-ttu-id="353b9-184">在安装了恢复和硬件数据库的服务器上，打开 SQL Server Management Studio 并验证是否已安装**MBAM 恢复和硬件**数据库。</span><span class="sxs-lookup"><span data-stu-id="353b9-184">On the server where the Recovery and Hardware Database is installed, open SQL Server Management Studio and verify that the **MBAM Recovery and Hardware** database is installed.</span></span>

3. <span data-ttu-id="353b9-185">在安装合规性和审核数据库的服务器上，打开 SQL Server Management Studio 并验证是否已安装**MBAM 合规性和审核数据库**。</span><span class="sxs-lookup"><span data-stu-id="353b9-185">On the server where the Compliance and Audit Database is installed, open SQL Server Management Studio and verify that the **MBAM Compliance and Audit Database** is installed.</span></span>

4. <span data-ttu-id="353b9-186">在安装合规性和审核报告的服务器上，打开具有管理权限的 web 浏览器，然后浏览到 SQL Server Reporting Services 网站的 "开始"。</span><span class="sxs-lookup"><span data-stu-id="353b9-186">On the server where the Compliance and Audit Reports are installed, open a web browser with administrative privileges and browse to the “Home” of the SQL Server Reporting Services site.</span></span>

   <span data-ttu-id="353b9-187">SQL Server Reporting Services 网站实例的默认主位置位于 http:// <em> &lt; NameofMBAMReportsServer &gt; </em> /Reports。</span><span class="sxs-lookup"><span data-stu-id="353b9-187">The default Home location of a SQL Server Reporting Services site instance is at http://<em>&lt;NameofMBAMReportsServer&gt;</em>/Reports.</span></span> <span data-ttu-id="353b9-188">若要查找实际 URL，请使用 Reporting Services 配置管理器工具，并选择在安装过程中指定的实例。</span><span class="sxs-lookup"><span data-stu-id="353b9-188">To find the actual URL, use the Reporting Services Configuration Manager tool and select the instances specified during setup.</span></span>

   <span data-ttu-id="353b9-189">确认列出了名为 "**马耳他合规性报告**" 的文件夹，其中包含五个报表和一个数据源。</span><span class="sxs-lookup"><span data-stu-id="353b9-189">Confirm that a folder named **Malta Compliance Reports** is listed and that it contains five reports and one data source.</span></span>

   **<span data-ttu-id="353b9-190">注意</span><span class="sxs-lookup"><span data-stu-id="353b9-190">Note</span></span>**  
   <span data-ttu-id="353b9-191">如果 SQL Server Reporting Services 配置为命名实例，则 URL 应类似于以下内容： http：//\* &lt; NameofMBAMReportsServer &gt; */Reports\_* &lt; SRSInstanceName &gt; \*</span><span class="sxs-lookup"><span data-stu-id="353b9-191">If SQL Server Reporting Services was configured as a named instance, the URL should resemble the following:http://*&lt;NameofMBAMReportsServer&gt;*/Reports\_*&lt;SRSInstanceName&gt;*</span></span>

     

5. <span data-ttu-id="353b9-192">在安装了 "管理和监视" 功能的服务器上，运行 "**服务器管理器**" 并浏览到 "**角色**"，选择 " **Web 服务器（iis）**"，然后单击 " **Internet 信息服务（iis）管理器**"</span><span class="sxs-lookup"><span data-stu-id="353b9-192">On the server where the Administration and Monitoring feature is installed, run **Server Manager** and browse to **Roles**, select **Web Server (IIS)**, and click **Internet Information Services (IIS) Manager**</span></span>

6. <span data-ttu-id="353b9-193">在 "**连接**" 中，浏览到 " \* &lt; computername &gt; \*"，选择 "**网站**"，然后选择 " **Microsoft BitLocker 管理和监视**"。</span><span class="sxs-lookup"><span data-stu-id="353b9-193">In **Connections**, browse to *&lt;computername&gt;*, select **Sites**, and select **Microsoft BitLocker Administration and Monitoring**.</span></span> <span data-ttu-id="353b9-194">验证 " **MBAMAdministrationService**"、" **MBAMComplianceStatusService**" 和 " **MBAMRecoveryAndHardwareService** " 是否已列出。</span><span class="sxs-lookup"><span data-stu-id="353b9-194">Verify that **MBAMAdministrationService**, **MBAMComplianceStatusService**, and **MBAMRecoveryAndHardwareService** are listed.</span></span>

7. <span data-ttu-id="353b9-195">在安装了 "管理和监视" 功能的服务器上，打开具有管理权限的 web 浏览器，然后浏览到 MBAM 网站中的以下位置以验证它们是否已成功加载：</span><span class="sxs-lookup"><span data-stu-id="353b9-195">On the server where the Administration and Monitoring feature is installed, open a web browser with administrative privileges, and then browse to the following locations in the MBAM website to verify that they load successfully:</span></span>

   -   <span data-ttu-id="353b9-196">*http:// &lt; computername &gt; /default.aspx*和确认导航和报表的每个链接</span><span class="sxs-lookup"><span data-stu-id="353b9-196">*http://&lt;computername&gt;/default.aspx* and confirm each of the links for navigation and reports</span></span>

   -   *<span data-ttu-id="353b9-197">http:// &lt; computername &gt; /MBAMAdministrationService/AdministrationService.svc</span><span class="sxs-lookup"><span data-stu-id="353b9-197">http://&lt;computername&gt;/MBAMAdministrationService/AdministrationService.svc</span></span>*

   -   *<span data-ttu-id="353b9-198">http:// &lt; computername &gt; /MBAMComplianceStatusService/StatusReportingService.svc</span><span class="sxs-lookup"><span data-stu-id="353b9-198">http://&lt;computername&gt;/MBAMComplianceStatusService/StatusReportingService.svc</span></span>*

   -   *<span data-ttu-id="353b9-199">http:// &lt; computername &gt; /MBAMRecoveryAndHardwareService/CoreService.svc</span><span class="sxs-lookup"><span data-stu-id="353b9-199">http://&lt;computername&gt;/MBAMRecoveryAndHardwareService/CoreService.svc</span></span>*

   **<span data-ttu-id="353b9-200">注意</span><span class="sxs-lookup"><span data-stu-id="353b9-200">Note</span></span>**  
   <span data-ttu-id="353b9-201">通常，服务安装在默认端口80上，而不进行网络加密。</span><span class="sxs-lookup"><span data-stu-id="353b9-201">Typically, the services are installed on the default port 80 without network encryption.</span></span> <span data-ttu-id="353b9-202">如果服务安装在其他端口上，请将 Url 更改为包含相应的端口。</span><span class="sxs-lookup"><span data-stu-id="353b9-202">If the services are installed on a different port, change the URLs to include the appropriate port.</span></span> <span data-ttu-id="353b9-203">例如，http://\* &lt; computername &gt; ： &lt; port &gt; \*/default.aspx 或 http:// <em> &lt; hostheadername &gt; / </em> 默认值 .aspx。</span><span class="sxs-lookup"><span data-stu-id="353b9-203">For example, http://*&lt;computername&gt;:&lt;port&gt;*/default.aspx or http://<em>&lt;hostheadername&gt;/</em>default.aspx.</span></span>

   <span data-ttu-id="353b9-204">如果服务是通过网络加密安装的，请将 http://更改为 https://。</span><span class="sxs-lookup"><span data-stu-id="353b9-204">If the services are installed with network encryption, change http:// to https://.</span></span>

     

## <span data-ttu-id="353b9-205">相关主题</span><span class="sxs-lookup"><span data-stu-id="353b9-205">Related topics</span></span>


[<span data-ttu-id="353b9-206">部署 MBAM 1.0 服务器基础结构</span><span class="sxs-lookup"><span data-stu-id="353b9-206">Deploying the MBAM 1.0 Server Infrastructure</span></span>](deploying-the-mbam-10-server-infrastructure.md)

 

 





