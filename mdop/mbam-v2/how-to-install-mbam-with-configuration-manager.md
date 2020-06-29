---
title: 如何使用 Configuration Manager 安装 MBAM
description: 如何使用 Configuration Manager 安装 MBAM
author: dansimp
ms.assetid: fd0832e4-3b79-4e56-9550-d2f396be6d09
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a556ce961e6a423caecdd0766cf8623383897b58
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803706"
---
# <span data-ttu-id="bafb3-103">如何使用 Configuration Manager 安装 MBAM</span><span class="sxs-lookup"><span data-stu-id="bafb3-103">How to Install MBAM with Configuration Manager</span></span>


<span data-ttu-id="bafb3-104">本节介绍使用配置管理器通过[配置管理器](getting-started---using-mbam-with-configuration-manager.md)将 MBAM 安装到配置管理器的步骤。</span><span class="sxs-lookup"><span data-stu-id="bafb3-104">This section describes the steps to install MBAM with Configuration Manager by using the recommended configuration, which is illustrated in [Getting Started - Using MBAM with Configuration Manager](getting-started---using-mbam-with-configuration-manager.md).</span></span> <span data-ttu-id="bafb3-105">步骤分为以下任务：</span><span class="sxs-lookup"><span data-stu-id="bafb3-105">The steps are divided into the following tasks:</span></span>

-   <span data-ttu-id="bafb3-106">在 Configuration Manager 服务器上安装和配置 MBAM</span><span class="sxs-lookup"><span data-stu-id="bafb3-106">Install and configure MBAM on the Configuration Manager Server</span></span>

-   <span data-ttu-id="bafb3-107">在数据库服务器上安装恢复和审核数据库</span><span class="sxs-lookup"><span data-stu-id="bafb3-107">Install the Recovery and Audit Databases on the Database Server</span></span>

-   <span data-ttu-id="bafb3-108">在 "管理和监视" 服务器上安装 "管理和监视服务器" 功能</span><span class="sxs-lookup"><span data-stu-id="bafb3-108">Install the Administration and Monitoring Server features on the Administration and Monitoring Server</span></span>

<span data-ttu-id="bafb3-109">开始安装之前，请确保您已编辑或创建了必要的 mof 文件。</span><span class="sxs-lookup"><span data-stu-id="bafb3-109">Before you begin the installation, ensure that you have edited or created the necessary mof files.</span></span> <span data-ttu-id="bafb3-110">有关说明，请参阅[如何创建或编辑 Mof 文件](how-to-create-or-edit-the-mof-files.md)。</span><span class="sxs-lookup"><span data-stu-id="bafb3-110">For instructions, see [How to Create or Edit the mof Files](how-to-create-or-edit-the-mof-files.md).</span></span>

<span data-ttu-id="bafb3-111">**重要提示** 如果你使用的是非默认 SQL Server Reporting Services （SSRS）实例，则必须使用以下命令行来启动 MBAM 设置以指定 SSRS 命名的实例：</span><span class="sxs-lookup"><span data-stu-id="bafb3-111">**Important** If you are using a non-default SQL Server Reporting Services (SSRS) instance, you must start the MBAM Setup by using the following command line to specify the SSRS named instance:</span></span>

`MbamSetup.exe CM_SSRS_INSTANCE_NAME=<NamedInstance>`

 

**<span data-ttu-id="bafb3-112">在 Configuration Manager 服务器上安装 MBAM</span><span class="sxs-lookup"><span data-stu-id="bafb3-112">To install MBAM on the Configuration Manager Server</span></span>**

1.  <span data-ttu-id="bafb3-113">在 Configuration Manager 服务器上，运行 " **MBAMSetup.exe** " 以启动 MBAM 安装向导。</span><span class="sxs-lookup"><span data-stu-id="bafb3-113">On the Configuration Manager Server, run **MBAMSetup.exe** to start the MBAM installation wizard.</span></span>

    <span data-ttu-id="bafb3-114">**注意** 若要获取安装程序日志文件，必须使用 Msiexec 程序包和 **/l** &lt; location &gt; 选项来安装 Configuration Manager。</span><span class="sxs-lookup"><span data-stu-id="bafb3-114">**Note** To obtain the setup log files, you have to use the Msiexec package and the **/L** &lt;location&gt; option to install Configuration Manager.</span></span> <span data-ttu-id="bafb3-115">将在您指定的位置创建日志文件。</span><span class="sxs-lookup"><span data-stu-id="bafb3-115">Log files are created in the location that you specify.</span></span>

    <span data-ttu-id="bafb3-116">在安装 Configuration Manager 的用户的计算机上的% temp% 文件夹中创建了其他安装日志文件。</span><span class="sxs-lookup"><span data-stu-id="bafb3-116">Additional setup log files are created in the %temp% folder on the computer of the user who is installing Configuration Manager.</span></span>

     

2.  <span data-ttu-id="bafb3-117">在 "**欢迎**" 页面上，选择 "**客户体验改善计划**"，然后单击 "**开始**"。</span><span class="sxs-lookup"><span data-stu-id="bafb3-117">On the **Welcome** page, optionally select the **Customer Experience Improvement Program**, and then click **Start**.</span></span>

3.  <span data-ttu-id="bafb3-118">阅读并接受 Microsoft 软件许可协议，然后单击 "**下一步**" 继续安装。</span><span class="sxs-lookup"><span data-stu-id="bafb3-118">Read and accept the Microsoft Software License Agreement, and then click **Next** to continue the installation.</span></span>

4.  <span data-ttu-id="bafb3-119">在 "**拓扑选择**" 页面上，选择 " **System Center Configuration Manager 集成**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="bafb3-119">On the **Topology Selection** page, select **System Center Configuration Manager Integration**, and then click **Next**.</span></span>

5.  <span data-ttu-id="bafb3-120">在 "**选择要安装的功能**" 页面上，选择 " **System Center Configuration Manager 集成**"。</span><span class="sxs-lookup"><span data-stu-id="bafb3-120">On the **Select features to install** page, select **System Center Configuration Manager Integration**.</span></span>

    <span data-ttu-id="bafb3-121">**注意** 在 "**检查先决条件**" 页面上，在安装向导检查安装的先决条件并确认没有缺失时，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="bafb3-121">**Note** On the **Checking Prerequisites** page, click **Next** after the installation wizard checks the prerequisites for your installation and confirms that none are missing.</span></span> <span data-ttu-id="bafb3-122">如果检测到缺少先决条件，则必须解决缺少的先决条件，然后再次单击 "**检查必备项"。**</span><span class="sxs-lookup"><span data-stu-id="bafb3-122">If a missing prerequisite is detected, you have to resolve the missing prerequisites, and then click **Check prerequisites again.**</span></span>

     

6.  <span data-ttu-id="bafb3-123">指定是否使用 Microsoft 更新来帮助保护您的计算机安全，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="bafb3-123">Specify whether to use Microsoft Updates to help keep your computer secure, and then click **Next**.</span></span> <span data-ttu-id="bafb3-124">使用 Microsoft 更新不会在 Windows 中启用自动更新。</span><span class="sxs-lookup"><span data-stu-id="bafb3-124">Using Microsoft Updates does not turn on Automatic Updates in Windows.</span></span>

7.  <span data-ttu-id="bafb3-125">单击**下一步**以继续。</span><span class="sxs-lookup"><span data-stu-id="bafb3-125">Click **Next** to continue.</span></span>

8.  <span data-ttu-id="bafb3-126">在 "**安装摘要**" 页面上，查看将安装的功能列表，然后单击 "**安装**" 以开始安装 MBAM 功能。</span><span class="sxs-lookup"><span data-stu-id="bafb3-126">On the **Installation Summary** page, review the list of features that will be installed, and click **Install** to start installing the MBAM features.</span></span> <span data-ttu-id="bafb3-127">如果必须查看或更改安装设置，请单击 "**返回**" 以在向导中向后移动，或者单击 "**取消**" 退出安装程序。</span><span class="sxs-lookup"><span data-stu-id="bafb3-127">Click **Back** to move back through the wizard if you have to review or change your installation settings, or click **Cancel** to exit Setup.</span></span> <span data-ttu-id="bafb3-128">安装程序安装 MBAM 功能并通知您安装已完成。</span><span class="sxs-lookup"><span data-stu-id="bafb3-128">Setup installs the MBAM features and notifies you that the installation is completed.</span></span>

9.  <span data-ttu-id="bafb3-129">单击 "**完成**" 退出向导。</span><span class="sxs-lookup"><span data-stu-id="bafb3-129">Click **Finish** to exit the wizard.</span></span>

**<span data-ttu-id="bafb3-130">在数据库服务器上安装恢复和审核数据库</span><span class="sxs-lookup"><span data-stu-id="bafb3-130">To install the Recovery and Audit Databases on the Database Server</span></span>**

1.  <span data-ttu-id="bafb3-131">在数据库服务器上，运行**MBAMSetup.exe**以启动 MBAM 安装向导。</span><span class="sxs-lookup"><span data-stu-id="bafb3-131">On the Database Server, run **MBAMSetup.exe** to start the MBAM installation wizard.</span></span>

2.  <span data-ttu-id="bafb3-132">在 "**欢迎**" 页面上，选择 "**客户体验改善计划**"，然后单击 "**开始**"。</span><span class="sxs-lookup"><span data-stu-id="bafb3-132">On the **Welcome** page, optionally select the **Customer Experience Improvement Program**, and then click **Start**.</span></span>

3.  <span data-ttu-id="bafb3-133">阅读并接受 Microsoft 软件许可协议，然后单击 "**下一步**" 继续安装。</span><span class="sxs-lookup"><span data-stu-id="bafb3-133">Read and accept the Microsoft Software License Agreement, and then click **Next** to continue the installation.</span></span>

4.  <span data-ttu-id="bafb3-134">在 "**拓扑选择**" 页面上，选择 " **System Center Configuration Manager 集成**拓扑"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="bafb3-134">On the **Topology Selection** page, select the **System Center Configuration Manager Integration** topology, and then click **Next**.</span></span>

5.  <span data-ttu-id="bafb3-135">从要安装的功能列表中，选择 "**恢复数据库**和**审核数据库**"，然后清除剩余的功能。</span><span class="sxs-lookup"><span data-stu-id="bafb3-135">From the list of features to install, select **Recovery Database** and **Audit Database**, and clear the remaining features.</span></span>

    <span data-ttu-id="bafb3-136">**注意** 安装向导将检查安装的先决条件，并显示缺少的必备条件。</span><span class="sxs-lookup"><span data-stu-id="bafb3-136">**Note** The installation wizard checks the prerequisites for your installation and displays the prerequisites that are missing.</span></span> <span data-ttu-id="bafb3-137">如果满足所有先决条件，安装将继续。</span><span class="sxs-lookup"><span data-stu-id="bafb3-137">If all of the prerequisites are met, the installation continues.</span></span> <span data-ttu-id="bafb3-138">如果检测到缺少先决条件，则必须解决缺少的先决条件，然后再次单击 "**检查必备项**"。</span><span class="sxs-lookup"><span data-stu-id="bafb3-138">If a missing prerequisite is detected, you have to resolve the missing prerequisites, and then click **Check prerequisites again**.</span></span> <span data-ttu-id="bafb3-139">如果此时间满足所有先决条件，安装将继续。</span><span class="sxs-lookup"><span data-stu-id="bafb3-139">If all prerequisites are met this time, the installation resumes.</span></span>

     

6.  <span data-ttu-id="bafb3-140">在 "**配置恢复数据库**" 页面上，指定将运行 "管理和监视服务器" 功能的计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="bafb3-140">On the **Configure the Recovery Database** page, specify the names of the computers that will be running the Administration and Monitoring Server feature.</span></span> <span data-ttu-id="bafb3-141">部署 "管理和监视服务器" 功能后，它将使用其域帐户连接到数据库。</span><span class="sxs-lookup"><span data-stu-id="bafb3-141">After the Administration and Monitoring Server feature is deployed, it uses its domain account to connect to the database.</span></span>

7.  <span data-ttu-id="bafb3-142">单击**下一步**以继续。</span><span class="sxs-lookup"><span data-stu-id="bafb3-142">Click **Next** to continue.</span></span>

8.  <span data-ttu-id="bafb3-143">指定要存储恢复数据的 SQL Server 实例名称和数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="bafb3-143">Specify the SQL Server instance name and the name of the database that will store the recovery data.</span></span> <span data-ttu-id="bafb3-144">还必须指定数据库将位于的位置以及日志信息所在的位置。</span><span class="sxs-lookup"><span data-stu-id="bafb3-144">You must also specify both where the database will be located and where the log information will be located.</span></span>

9.  <span data-ttu-id="bafb3-145">单击 "**下一步**" 以继续安装 MBAM 设置安装向导。</span><span class="sxs-lookup"><span data-stu-id="bafb3-145">Click **Next** to continue with the MBAM Setup installation wizard.</span></span>

10. <span data-ttu-id="bafb3-146">在 "**配置审核数据库**" 页面上，指定将用于访问报表的数据库的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="bafb3-146">On the **Configure the Audit Database** page, specify the user account that will be used to access the database for reports.</span></span>

11. <span data-ttu-id="bafb3-147">指定将运行管理和监视服务器以及审核报告的计算机的计算机名称。</span><span class="sxs-lookup"><span data-stu-id="bafb3-147">Specify the computer names of the computers that will be running the Administration and Monitoring Server and the Audit Reports.</span></span> <span data-ttu-id="bafb3-148">部署 "管理和监视" 和 "审核报告" 功能后，将使用其域帐户连接到数据库。</span><span class="sxs-lookup"><span data-stu-id="bafb3-148">After the Administration and Monitoring and the Audit Reports features are deployed, their domain accounts will be used to connect to the databases.</span></span>

    <span data-ttu-id="bafb3-149">**注意** 如果在未使用 "审核报告" 功能的情况下安装审核数据库，则必须在审核数据库计算机上添加一个例外，以便在 Microsoft SQL Server 端口上启用入站流量。</span><span class="sxs-lookup"><span data-stu-id="bafb3-149">**Note** If you are installing the Audit Database without the Audit Reports feature, you must add an exception on the Audit Database computer to enable inbound traffic on the Microsoft SQL Server port.</span></span> <span data-ttu-id="bafb3-150">默认端口号为1433。</span><span class="sxs-lookup"><span data-stu-id="bafb3-150">The default port number is 1433.</span></span>

     

12. <span data-ttu-id="bafb3-151">指定要存储审核数据的数据库的 SQL Server 实例名称和数据库名称。</span><span class="sxs-lookup"><span data-stu-id="bafb3-151">Specify the SQL Server instance name and the name of the database that will store the audit data.</span></span> <span data-ttu-id="bafb3-152">你还必须指定数据库和日志信息的位置。</span><span class="sxs-lookup"><span data-stu-id="bafb3-152">You must also specify where the database and log information will be located.</span></span>

13. <span data-ttu-id="bafb3-153">单击 "**安装**" 以开始安装，然后单击 "**完成**" 以完成安装。</span><span class="sxs-lookup"><span data-stu-id="bafb3-153">Click **Install** to start the installation, and then click **Finish** to complete the installation.</span></span>

**<span data-ttu-id="bafb3-154">在管理和监视服务器上安装管理和监视服务器功能</span><span class="sxs-lookup"><span data-stu-id="bafb3-154">To install the Administration and Monitoring Server features on the Administration and Monitoring Server</span></span>**

1.  <span data-ttu-id="bafb3-155">在 "管理和监视" 服务器上，运行 " **MBAMSetup.exe** " 以启动 MBAM 安装向导。</span><span class="sxs-lookup"><span data-stu-id="bafb3-155">On the Administration and Monitoring Server, run **MBAMSetup.exe** to start the MBAM installation wizard.</span></span>

2.  <span data-ttu-id="bafb3-156">在 "**欢迎**" 页面上，选择 "**客户体验改善计划**"，然后单击 "**开始**"。</span><span class="sxs-lookup"><span data-stu-id="bafb3-156">On the **Welcome** page, optionally select the **Customer Experience Improvement Program**, and then click **Start**.</span></span>

3.  <span data-ttu-id="bafb3-157">阅读并接受 Microsoft 软件许可协议，然后单击 "**下一步**" 继续安装。</span><span class="sxs-lookup"><span data-stu-id="bafb3-157">Read and accept the Microsoft Software License Agreement, and then click **Next** to continue the installation.</span></span>

4.  <span data-ttu-id="bafb3-158">在 "**拓扑选择**" 页面上，选择 " **System Center Configuration Manager 集成**拓扑"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="bafb3-158">On the **Topology Selection** page, select the **System Center Configuration Manager Integration** topology, and then click **Next**.</span></span>

5.  <span data-ttu-id="bafb3-159">从要安装的功能列表中，选择 "**管理和监视服务器**和**自助服务门户**"，然后清除 "剩余功能"。</span><span class="sxs-lookup"><span data-stu-id="bafb3-159">From the list of features to install, select **Administration and Monitoring Server** and **Self-Service Portal**, and clear the remaining features.</span></span>

    <span data-ttu-id="bafb3-160">**注意** 安装向导将检查安装的先决条件，并显示缺少的必备条件。</span><span class="sxs-lookup"><span data-stu-id="bafb3-160">**Note** The installation wizard checks the prerequisites for your installation and displays the prerequisites that are missing.</span></span> <span data-ttu-id="bafb3-161">如果满足所有先决条件，安装将继续。</span><span class="sxs-lookup"><span data-stu-id="bafb3-161">If all of the prerequisites are met, the installation continues.</span></span> <span data-ttu-id="bafb3-162">如果检测到缺少先决条件，则必须解决缺少的先决条件，然后再次单击 "**检查必备项**"。</span><span class="sxs-lookup"><span data-stu-id="bafb3-162">If a missing prerequisite is detected, you have to resolve the missing prerequisites, and then click **Check prerequisites again**.</span></span> <span data-ttu-id="bafb3-163">如果此时间满足所有先决条件，安装将继续。</span><span class="sxs-lookup"><span data-stu-id="bafb3-163">If all prerequisites are met this time, the installation resumes.</span></span>

     

6.  <span data-ttu-id="bafb3-164">按照[如何在分布式服务器上安装和配置 MBAM](how-to-install-and-configure-mbam-on-distributed-servers-mbam-2.md)的 "**安装自助服务门户**" 部分中的步骤安装自助服务门户。</span><span class="sxs-lookup"><span data-stu-id="bafb3-164">Install the Self-Service Portal by following the steps in the **To install the Self-Service Portal** section in [How to Install and Configure MBAM on Distributed Servers](how-to-install-and-configure-mbam-on-distributed-servers-mbam-2.md).</span></span>

    <span data-ttu-id="bafb3-165">**注意** 如果客户端计算机将无法访问 Microsoft 内容交付网络（CDN），这将为自助服务门户提供对某些 JavaScript 文件所需的访问权限，完成了在**最终用户无法访问 Microsoft Content 传递网络部分时配置自助服务门户**中的步骤，[如何在分布式服务器上安装和配置 MBAM](how-to-install-and-configure-mbam-on-distributed-servers-mbam-2.md) ，以将自助服务门户配置为从易于访问的源中引用 JavaScript 文件。</span><span class="sxs-lookup"><span data-stu-id="bafb3-165">**Note** If the client computers will not have access to the Microsoft Content Delivery Network (CDN), which gives the Self-Service Portal the required access to certain JavaScript files, complete the steps in the **To configure the Self-Service Portal when end users cannot access the Microsoft Content Delivery Network** section [How to Install and Configure MBAM on Distributed Servers](how-to-install-and-configure-mbam-on-distributed-servers-mbam-2.md) to configure the Self-Service Portal to reference the JavaScript files from an accessible source.</span></span>

     

7.  <span data-ttu-id="bafb3-166">按照[如何在分布式服务器上安装和配置 MBAM](how-to-install-and-configure-mbam-on-distributed-servers-mbam-2.md)的 "**安装管理和监视服务器功能**" 部分中的步骤安装管理和监视服务器功能。</span><span class="sxs-lookup"><span data-stu-id="bafb3-166">Install the Administration and Monitoring Server features by following the steps in the **To install the Administration and Monitoring Server feature** section in [How to Install and Configure MBAM on Distributed Servers](how-to-install-and-configure-mbam-on-distributed-servers-mbam-2.md).</span></span>

8.  <span data-ttu-id="bafb3-167">单击 "**完成**" 以完成安装。</span><span class="sxs-lookup"><span data-stu-id="bafb3-167">Click **Finish** to complete the installation.</span></span>

## <span data-ttu-id="bafb3-168">相关主题</span><span class="sxs-lookup"><span data-stu-id="bafb3-168">Related topics</span></span>


[<span data-ttu-id="bafb3-169">如何使用 Configuration Manager 验证 MBAM 安装</span><span class="sxs-lookup"><span data-stu-id="bafb3-169">How to Validate the MBAM Installation with Configuration Manager</span></span>](how-to-validate-the-mbam-installation-with-configuration-manager.md)

[<span data-ttu-id="bafb3-170">使用 Configuration Manager 部署 MBAM</span><span class="sxs-lookup"><span data-stu-id="bafb3-170">Deploying MBAM with Configuration Manager</span></span>](deploying-mbam-with-configuration-manager-mbam2.md)

 

 





