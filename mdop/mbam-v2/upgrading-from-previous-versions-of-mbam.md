---
title: 从以前版本的 MBAM 升级
description: 从以前版本的 MBAM 升级
author: dansimp
ms.assetid: 73b425cf-9cd9-4ebc-a35e-1b3bf18596ce
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: af45d193a5e8001288e70389ff220cb5d8269918
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803442"
---
# <span data-ttu-id="c0a82-103">从以前版本的 MBAM 升级</span><span class="sxs-lookup"><span data-stu-id="c0a82-103">Upgrading from Previous Versions of MBAM</span></span>


<span data-ttu-id="c0a82-104">你可以通过执行以下操作，使用独立拓扑或配置管理器拓扑将 Microsoft BitLocker 管理和监视（MBAM）升级到 MBAM 2.0：</span><span class="sxs-lookup"><span data-stu-id="c0a82-104">You can upgrade Microsoft BitLocker Administration and Monitoring (MBAM) to MBAM2.0, with the Stand-alone topology or Configuration Manager topology, by doing the following:</span></span>

-   <span data-ttu-id="c0a82-105">**手动就地服务器更换**-若要升级 MBAM 服务器，请使用 "安装程序" 或 "控制面板" 手动卸载 MBAM，然后安装 MBAM 2.0 基础结构。</span><span class="sxs-lookup"><span data-stu-id="c0a82-105">**Manual in-place server replacement** – To upgrade the MBAM Server, manually uninstall MBAM by using either the installer or Control Panel, and then install the MBAM2.0 infrastructure.</span></span> <span data-ttu-id="c0a82-106">不必删除数据库。</span><span class="sxs-lookup"><span data-stu-id="c0a82-106">You do not have to remove the databases.</span></span> <span data-ttu-id="c0a82-107">卸载 MBAM 1.0 服务器会使 MBAM 数据库保持不变。</span><span class="sxs-lookup"><span data-stu-id="c0a82-107">Uninstalling the MBAM 1.0 Server leaves the MBAM databases intact.</span></span> <span data-ttu-id="c0a82-108">如果你指定的数据库与 MBAM 1.0 使用的数据库相同，则 MBAM 2.0 安装将在数据库中保留 MBAM 1.0 数据，并将数据库转换为与 MBAM 2.0 配合使用。</span><span class="sxs-lookup"><span data-stu-id="c0a82-108">If you specify the same databases that MBAM 1.0 was using, the MBAM2.0 installation retains MBAM 1.0 data in the databases and converts the databases to work with MBAM2.0.</span></span>

-   <span data-ttu-id="c0a82-109">**分布式客户端升级**-如果你使用的是独立的 MBAM 拓扑，则可以在安装 MBAM 2.0 服务器基础结构后逐步升级 MBAM 客户端。</span><span class="sxs-lookup"><span data-stu-id="c0a82-109">**Distributed Client Upgrade** - If you are using the Stand-alone MBAM topology, you can upgrade the MBAM Clients gradually after you install the MBAM 2.0 Server infrastructure.</span></span> <span data-ttu-id="c0a82-110">MBAM 2.0 服务器检测现有客户端的版本并执行升级到2.0 客户端所需的步骤。</span><span class="sxs-lookup"><span data-stu-id="c0a82-110">The MBAM 2.0 Server detects the version of the existing Client and performs the required steps to upgrade to the 2.0 Client.</span></span>

    <span data-ttu-id="c0a82-111">升级 MBAM 2.0 服务器基础结构后，MBAM 1.0 客户端会继续向 MBAM 2.0 服务器报告 escrowing 恢复数据，但合规性将基于 MBAM 1.0 中的策略。</span><span class="sxs-lookup"><span data-stu-id="c0a82-111">After you upgrade the MBAM 2.0 Server infrastructure, MBAM 1.0 Clients continue to report to the MBAM 2.0 Server successfully, escrowing recovery data, but compliance will be based on the policies in MBAM 1.0.</span></span> <span data-ttu-id="c0a82-112">必须将客户端升级到 MBAM 2.0 以使客户端计算机能够根据 MBAM 2.0 策略准确地报告合规性。</span><span class="sxs-lookup"><span data-stu-id="c0a82-112">You must upgrade clients to MBAM 2.0 to have client computers accurately report compliance against the MBAM 2.0 policies.</span></span> <span data-ttu-id="c0a82-113">你可以将客户端升级到 MBAM 2.0 客户端，而不卸载以前的客户端，并且客户端将开始应用和报告 MBAM 2.0 策略。</span><span class="sxs-lookup"><span data-stu-id="c0a82-113">You can upgrade the clients to the MBAM 2.0 Client without uninstalling the previous client, and the client will start to apply and report MBAM 2.0 policies.</span></span>

    <span data-ttu-id="c0a82-114">如果你将 MBAM 与 Configuration Manager 配合使用，则必须将 MBAM 1.0 客户端升级到 MBAM 2.0。</span><span class="sxs-lookup"><span data-stu-id="c0a82-114">If you are using MBAM with Configuration Manager, you must upgrade the MBAM 1.0 clients to MBAM 2.0.</span></span>

## <span data-ttu-id="c0a82-115">从两个服务器体系结构升级 MBAM</span><span class="sxs-lookup"><span data-stu-id="c0a82-115">Upgrading MBAM from a Two-Server Architecture</span></span>


<span data-ttu-id="c0a82-116">当你使用双服务器体系结构（其中一个服务器托管 Microsoft SQL Server 组件，而另一个服务器托管网站和服务）时，请使用以下说明从 MBAM 的早期版本进行升级。</span><span class="sxs-lookup"><span data-stu-id="c0a82-116">Use the following instructions to upgrade from a previous version of MBAM when you are using a two-server architecture, where one server is hosting the Microsoft SQL Server components, and the other server is hosting the websites and services.</span></span>

**<span data-ttu-id="c0a82-117">从两个服务器体系结构升级 MBAM</span><span class="sxs-lookup"><span data-stu-id="c0a82-117">To upgrade MBAM from a two-server architecture</span></span>**

1.  <span data-ttu-id="c0a82-118">在具有 SQL Server 功能的服务器上，在 "控制面板" 中选择 "**程序和功能**"，然后卸载 " **Microsoft BitLocker 管理和监视**"。</span><span class="sxs-lookup"><span data-stu-id="c0a82-118">On the server with the SQL Server features, in Control Panel, select **Programs and Features**, and then uninstall **Microsoft BitLocker Administration and Monitoring**.</span></span> <span data-ttu-id="c0a82-119">恢复数据库和合规性以及审核数据库保持不变。</span><span class="sxs-lookup"><span data-stu-id="c0a82-119">The Recovery Database and Compliance and Audit database remain unchanged.</span></span>

2.  <span data-ttu-id="c0a82-120">针对版本 MBAM 2.0 运行**MBAMSetup.exe** （可选）选择 "**客户体验改善计划**"，然后单击 "**开始**"。</span><span class="sxs-lookup"><span data-stu-id="c0a82-120">Run **MBAMSetup.exe** for version MBAM 2.0, optionally select the **Customer Experience Improvement Program**, and then click **Start**.</span></span>

3.  <span data-ttu-id="c0a82-121">阅读并接受 Microsoft 软件许可协议，然后单击 "**下一步**" 继续安装。</span><span class="sxs-lookup"><span data-stu-id="c0a82-121">Read and accept the Microsoft Software License Agreement, and then click **Next** to continue the installation.</span></span>

4.  <span data-ttu-id="c0a82-122">在 "**拓扑选择**" 页面上，选择 "**独立**" 或 " **System Center Configuration Manager 集成**拓扑"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="c0a82-122">On the **Topology Selection** page, select the **Stand-alone** or **System Center Configuration Manager Integration** topology, and then click **Next**.</span></span>

5.  <span data-ttu-id="c0a82-123">在 "**选择要安装的功能**" 页面上，清除 "**自助式服务器**" 和 "**管理和监视服务器**功能"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="c0a82-123">On the **Select features to install** page, clear the **Self-Service Server** and **Administration and Monitoring Server** features, and then click **Next**.</span></span>

6.  <span data-ttu-id="c0a82-124">等待先决条件检查完成，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="c0a82-124">Wait for the prerequisite checks to finish, and then click **Next**.</span></span> <span data-ttu-id="c0a82-125">如果检测到缺少先决条件，请解决缺少的先决条件，然后再次单击 "**检查必备项**"。</span><span class="sxs-lookup"><span data-stu-id="c0a82-125">If a missing prerequisite is detected, resolve the missing prerequisites, and then click **Check prerequisites again**.</span></span>

7.  <span data-ttu-id="c0a82-126">在 "**提供用于访问 MBAM 数据库的帐户**" 页面上，为将承载网站和服务的服务器提供计算机名称，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="c0a82-126">On the **Provide account used to access the MBAM databases** page, provide the computer name for the server that will host the sites and services, and then click **Next**.</span></span>

8.  <span data-ttu-id="c0a82-127">在 "**配置恢复数据库**" 页面上，指定要存储恢复数据的数据库的 SQL Server 实例名称和数据库名称。</span><span class="sxs-lookup"><span data-stu-id="c0a82-127">On the **Configure the Recovery database** page, specify the SQL Server instance name and the name of the database that will store the recovery data.</span></span> <span data-ttu-id="c0a82-128">还必须指定数据库文件和日志信息的存放位置。</span><span class="sxs-lookup"><span data-stu-id="c0a82-128">You must also specify where the database files and log information will be located.</span></span>

9.  <span data-ttu-id="c0a82-129">单击**下一步**以继续。</span><span class="sxs-lookup"><span data-stu-id="c0a82-129">Click **Next** to continue.</span></span>

10. <span data-ttu-id="c0a82-130">在 "**配置合规性和审核数据库**" 页面上，指定要存储合规性和审核数据的数据库的 SQL Server 实例名称和名称。</span><span class="sxs-lookup"><span data-stu-id="c0a82-130">On the **Configure the Compliance and Audit database** page, specify the SQL Server instance name and the name of the database that will store the compliance and audit data.</span></span>

11. <span data-ttu-id="c0a82-131">单击**下一步**以继续。</span><span class="sxs-lookup"><span data-stu-id="c0a82-131">Click **Next** to continue.</span></span>

12. <span data-ttu-id="c0a82-132">在 "**配置合规性和审核报告**" 页面上，指定将安装合规性和审核报告的 SQL Server Reporting Services 实例，并提供用于访问合规性和审核数据库的域用户帐户和密码。</span><span class="sxs-lookup"><span data-stu-id="c0a82-132">On the **Configure the Compliance and Audit Reports** page, specify the SQL Server Reporting Services instance where the Compliance and Audit reports will be installed, and provide a domain user account and password to access the Compliance and Audit database.</span></span> <span data-ttu-id="c0a82-133">将此帐户的密码配置为永不过期。</span><span class="sxs-lookup"><span data-stu-id="c0a82-133">Configure the password for this account to never expire.</span></span> <span data-ttu-id="c0a82-134">用户帐户可以访问 MBAM 报告用户组中可用的所有数据。</span><span class="sxs-lookup"><span data-stu-id="c0a82-134">The user account can access all data available to the MBAM Reports Users group.</span></span>

13. <span data-ttu-id="c0a82-135">单击**下一步**以继续。</span><span class="sxs-lookup"><span data-stu-id="c0a82-135">Click **Next** to continue.</span></span>

14. <span data-ttu-id="c0a82-136">指定是否使用 Microsoft 更新来帮助保护您的计算机安全，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="c0a82-136">Specify whether to use Microsoft Updates to help keep your computer secure, and then click **Next**.</span></span> <span data-ttu-id="c0a82-137">此操作不会在 Windows 中启用自动更新。</span><span class="sxs-lookup"><span data-stu-id="c0a82-137">This does not turn on Automatic Updates in Windows.</span></span> <span data-ttu-id="c0a82-138">如果以前选择将 Microsoft 更新用于此产品或其他产品，则不会显示 "Microsoft 更新" 页面。</span><span class="sxs-lookup"><span data-stu-id="c0a82-138">If you previously chose to use Microsoft Update for this product or another product, the Microsoft Update page does not appear.</span></span>

15. <span data-ttu-id="c0a82-139">在 "**安装摘要**" 页面上，查看将安装的功能，然后单击 "**安装**" 以开始安装。</span><span class="sxs-lookup"><span data-stu-id="c0a82-139">On the **Installation Summary** page, review the features that will be installed, and then click **Install** to start the installation.</span></span>

**<span data-ttu-id="c0a82-140">卸载管理和监视服务器功能并完成升级</span><span class="sxs-lookup"><span data-stu-id="c0a82-140">To uninstall the Administration and Monitoring Server features and to complete the upgrade</span></span>**

1.  <span data-ttu-id="c0a82-141">在托管管理和监视服务器功能的计算机上，在 "控制面板" 中选择 "**程序和功能**"，然后卸载 MBAM 以删除以前安装的网站和服务。</span><span class="sxs-lookup"><span data-stu-id="c0a82-141">On the computer that hosts the Administration and Monitoring Server features, in Control Panel, select **Programs and Features**, and then uninstall MBAM to remove the previously installed websites and services.</span></span>

2.  <span data-ttu-id="c0a82-142">运行版本2.0 的**MBAMSetup.exe** ，选择 "**客户体验改善计划**"，然后单击 "**开始**"。</span><span class="sxs-lookup"><span data-stu-id="c0a82-142">Run the **MBAMSetup.exe** for version 2.0, optionally select the **Customer Experience Improvement Program**, and then click **Start**.</span></span>

3.  <span data-ttu-id="c0a82-143">阅读并接受 Microsoft 软件许可协议，然后单击 "**下一步**" 继续安装。</span><span class="sxs-lookup"><span data-stu-id="c0a82-143">Read and accept the Microsoft Software License Agreement, and then click **Next** to continue the installation.</span></span>

4.  <span data-ttu-id="c0a82-144">在 "**拓扑选择**" 页面上，选择 "**独立**" 或 " **System Center Configuration Manager 集成**拓扑"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="c0a82-144">On the **Topology Selection** page, select the **Stand-alone** or **System Center Configuration Manager Integration** topology, and then click **Next**.</span></span>

5.  <span data-ttu-id="c0a82-145">在 "**选择要安装的功能**" 页面上，清除 "**恢复数据库**和**合规性" 和 "审核数据库**和**合规性和审核报告**功能"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="c0a82-145">On the **Select features to install** page, clear the **Recovery Database** and **Compliance and Audit Database** and **Compliance and Audit Reports** features, and then click **Next**.</span></span>

6.  <span data-ttu-id="c0a82-146">等待先决条件检查完成，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="c0a82-146">Wait for the prerequisite checks to finish, and then click **Next**.</span></span> <span data-ttu-id="c0a82-147">如果检测到缺少先决条件，请首先解决缺少的先决条件，然后再次单击 "**检查必备项**"。</span><span class="sxs-lookup"><span data-stu-id="c0a82-147">If a missing prerequisite is detected, resolve the missing prerequisites first, and then click **Check prerequisites again**.</span></span>

7.  <span data-ttu-id="c0a82-148">在 "**配置网络通信安全**" 页面上，选择是否对网站和服务使用安全套接字层（SSL）加密。</span><span class="sxs-lookup"><span data-stu-id="c0a82-148">On the **Configure network communication security** page, choose whether to use Secure Socket Layer (SSL) encryption for the websites and services.</span></span> <span data-ttu-id="c0a82-149">如果您决定加密通信，请选择要用于加密的证书颁发机构（CA）证书。</span><span class="sxs-lookup"><span data-stu-id="c0a82-149">If you decide to encrypt the communication, select the certification authority (CA) certificate to use for encryption.</span></span>

    <span data-ttu-id="c0a82-150">**注意** 必须先创建证书，然后才能在此页面上选择该证书。</span><span class="sxs-lookup"><span data-stu-id="c0a82-150">**Note** The certificate must be created before this step to enable you to select it on this page.</span></span>

     

8.  <span data-ttu-id="c0a82-151">在 "**配置合规性状态数据库的位置**" 页面上，指定 SQL Server 实例名称和存储合规性和审核数据的数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="c0a82-151">On the **Configure the location of the Compliance Status database** page, specify the SQL Server instance name and the name of the database that stores the compliance and audit data.</span></span> <span data-ttu-id="c0a82-152">还必须指定数据库文件和日志信息的存放位置。</span><span class="sxs-lookup"><span data-stu-id="c0a82-152">You must also specify where the database files and log information will be located.</span></span>

9.  <span data-ttu-id="c0a82-153">单击**下一步**以继续。</span><span class="sxs-lookup"><span data-stu-id="c0a82-153">Click **Next** to continue.</span></span>

10. <span data-ttu-id="c0a82-154">在 "**配置恢复数据库的位置**" 页面上，指定用于存储恢复数据的数据库的 SQL Server 实例名称和数据库名称。</span><span class="sxs-lookup"><span data-stu-id="c0a82-154">On the **Configure the location of the Recovery Database** page, specify the SQL Server instance name and the name of the database that stores the recovery data.</span></span>

11. <span data-ttu-id="c0a82-155">单击**下一步**以继续。</span><span class="sxs-lookup"><span data-stu-id="c0a82-155">Click **Next** to continue.</span></span>

12. <span data-ttu-id="c0a82-156">在 "**配置合规性和审核报告**" 页面上，输入您在其他服务器上配置的报告实例的 URL。</span><span class="sxs-lookup"><span data-stu-id="c0a82-156">On the **Configure the Compliance and Audit Reports** page, enter the URL for the reporting instance that you configured on the other server.</span></span> <span data-ttu-id="c0a82-157">使用 "**测试**" 按钮验证您是否可以访问该网站。</span><span class="sxs-lookup"><span data-stu-id="c0a82-157">Use the **Test** button to verify that you can reach the site.</span></span>

13. <span data-ttu-id="c0a82-158">单击**下一步**以继续。</span><span class="sxs-lookup"><span data-stu-id="c0a82-158">Click **Next** to continue.</span></span>

14. <span data-ttu-id="c0a82-159">在 "**配置自助服务门户**" 页面上，输入自助服务门户的端口号、主机名、虚拟目录名称和安装路径。</span><span class="sxs-lookup"><span data-stu-id="c0a82-159">On the **Configure the Self-Service Portal** page, enter the port number, host name, virtual directory name, and installation path for the Self-Service Portal.</span></span>

    <span data-ttu-id="c0a82-160">**注意** 你指定的端口号必须是管理和监视服务器上未使用的端口号，除非你指定唯一的主机标题名称。</span><span class="sxs-lookup"><span data-stu-id="c0a82-160">**Note** The port number that you specify must be an unused port number on the Administration and Monitoring Server unless you specify a unique host header name.</span></span>

     

15. <span data-ttu-id="c0a82-161">在 "**配置管理和监视服务器**" 页面上，为技术支持网站指定所需的虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="c0a82-161">On the **Configure the Administration and Monitoring Server** page, specify the desired virtual directory for the Help Desk website.</span></span>

16. <span data-ttu-id="c0a82-162">指定是否使用 Microsoft 更新来帮助保护您的计算机安全，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="c0a82-162">Specify whether to use Microsoft Updates to help keep your computer secure, and then click **Next**.</span></span> <span data-ttu-id="c0a82-163">此步骤不会在 Windows 中启用自动更新。</span><span class="sxs-lookup"><span data-stu-id="c0a82-163">This step does not turn on Automatic Updates in Windows.</span></span> <span data-ttu-id="c0a82-164">如果以前选择将 Microsoft 更新用于此产品或其他产品，则不会显示 "Microsoft 更新" 页面。</span><span class="sxs-lookup"><span data-stu-id="c0a82-164">If you previously chose to use Microsoft Update for this product or another product, the Microsoft Update page does not appear.</span></span>

17. <span data-ttu-id="c0a82-165">在 "**安装摘要**" 页面上，查看将安装的功能，然后单击 "**安装**" 以开始安装。</span><span class="sxs-lookup"><span data-stu-id="c0a82-165">On the **Installation Summary** page, review the features that will be installed, and then click **Install** to start the installation.</span></span>

18. <span data-ttu-id="c0a82-166">若要验证升级是否成功，请验证你是否可以从域中的另一台计算机访问每个网站。</span><span class="sxs-lookup"><span data-stu-id="c0a82-166">To validate that the upgrade was successful, verify that you can reach each site from another computer in the domain.</span></span>

## <span data-ttu-id="c0a82-167">在最终用户计算机上升级 MBAM 客户端</span><span class="sxs-lookup"><span data-stu-id="c0a82-167">Upgrading the MBAM Client on End-User Computers</span></span>


<span data-ttu-id="c0a82-168">若要将最终用户计算机升级到 MBAM 2.0 客户端，请在每台客户端计算机上运行**MbamClientSetup.exe** 。</span><span class="sxs-lookup"><span data-stu-id="c0a82-168">To upgrade end-user computers to the MBAM 2.0 Client, run **MbamClientSetup.exe** on each client computer.</span></span> <span data-ttu-id="c0a82-169">安装程序自动将客户端更新到 MBAM 2.0 客户端。</span><span class="sxs-lookup"><span data-stu-id="c0a82-169">The installer automatically updates the Client to the MBAM 2.0 Client.</span></span> <span data-ttu-id="c0a82-170">你可以通过电子软件分发系统（如 Active Directory 域服务或 System Center Configuration Manager 等工具）安装 MBAM 客户端。</span><span class="sxs-lookup"><span data-stu-id="c0a82-170">You can install the MBAM Client through an electronic software distribution system, tools such as Active Directory Domain Services or System Center Configuration Manager.</span></span>

<span data-ttu-id="c0a82-171">若要验证客户端升级，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="c0a82-171">To validate the Client upgrade, do the following:</span></span>

1.  <span data-ttu-id="c0a82-172">等待配置的报告周期完成，然后在 SQL Server 计算机上启动**Sql Server Management Studio** 。</span><span class="sxs-lookup"><span data-stu-id="c0a82-172">Wait until the configured reporting cycle is finished, and then start **SQL Server Management Studio** on the SQL Server computer.</span></span>

2.  <span data-ttu-id="c0a82-173">在 SQL Server 计算机上，启动**Sql Server Management Studio**。</span><span class="sxs-lookup"><span data-stu-id="c0a82-173">On the SQL Server computer, start **SQL Server Management Studio**.</span></span>

3.  <span data-ttu-id="c0a82-174">验证**RecoveryAndHardwareCore**表是否包含显示最终用户的计算机名的行。</span><span class="sxs-lookup"><span data-stu-id="c0a82-174">Verify that the **RecoveryAndHardwareCore.Machines** table contains a row that shows the end-user’s computer name.</span></span>

## <span data-ttu-id="c0a82-175">相关主题</span><span class="sxs-lookup"><span data-stu-id="c0a82-175">Related topics</span></span>


[<span data-ttu-id="c0a82-176">部署 MBAM 2.0</span><span class="sxs-lookup"><span data-stu-id="c0a82-176">Deploying MBAM 2.0</span></span>](deploying-mbam-20-mbam-2.md)

 

 





