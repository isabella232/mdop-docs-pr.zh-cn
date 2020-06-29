---
title: 评估 MBAM 1.0
description: 评估 MBAM 1.0
author: dansimp
ms.assetid: a1e2b674-eda9-4e1c-9b4c-e748470c71f2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: f09b06af52f5738fd50bfe727987b760d98552d9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803731"
---
# <span data-ttu-id="b3ccc-103">评估 MBAM 1.0</span><span class="sxs-lookup"><span data-stu-id="b3ccc-103">Evaluating MBAM 1.0</span></span>


<span data-ttu-id="b3ccc-104">在将 Microsoft BitLocker 管理和监视（MBAM）部署到生产环境之前，应在实验室环境中对其进行评估。</span><span class="sxs-lookup"><span data-stu-id="b3ccc-104">Before you deploy Microsoft BitLocker Administration and Monitoring (MBAM) into a production environment, you should evaluate it in a lab environment.</span></span> <span data-ttu-id="b3ccc-105">你可以使用本主题中的信息在单个服务器实验室环境中设置 MBAM，以便仅用于评估目的。</span><span class="sxs-lookup"><span data-stu-id="b3ccc-105">You can use the information in this topic to set up MBAM in a single server lab environment for evaluation purposes only.</span></span>

<span data-ttu-id="b3ccc-106">虽然实际部署步骤与在[单个服务器上安装和配置 MBAM](how-to-install-and-configure-mbam-on-a-single-server-mbam-1.md)的方案非常相似，但本主题包含可让你在最少的时间内设置 MBAM 评估环境的其他信息。</span><span class="sxs-lookup"><span data-stu-id="b3ccc-106">While the actual deployment steps are very similar to the scenario that is described in [How to Install and Configure MBAM on a Single Server](how-to-install-and-configure-mbam-on-a-single-server-mbam-1.md), this topic contains additional information to enable you to set up an MBAM evaluation environment in the least amount of time.</span></span>

## <span data-ttu-id="b3ccc-107">设置实验室环境</span><span class="sxs-lookup"><span data-stu-id="b3ccc-107">Set up the Lab Environment</span></span>


<span data-ttu-id="b3ccc-108">即使在实验室环境中设置要评估的 MBAM 的非生产实例，仍应验证是否满足部署先决条件以及硬件和软件要求。</span><span class="sxs-lookup"><span data-stu-id="b3ccc-108">Even when you set up a non-production instance of MBAM to evaluate in a lab environment, you should still verify that you have met the deployment prerequisites and the hardware and software requirements.</span></span> <span data-ttu-id="b3ccc-109">有关详细信息，请参阅[MBAM 1.0 部署先决条件](mbam-10-deployment-prerequisites.md)和[MBAM 1.0 支持的配置](mbam-10-supported-configurations.md)。</span><span class="sxs-lookup"><span data-stu-id="b3ccc-109">For more information, see [MBAM 1.0 Deployment Prerequisites](mbam-10-deployment-prerequisites.md) and [MBAM 1.0 Supported Configurations](mbam-10-supported-configurations.md).</span></span> <span data-ttu-id="b3ccc-110">在开始 MBAM 评估部署之前，还应查看[准备 MBAM 1.0 的环境](preparing-your-environment-for-mbam-10.md)。</span><span class="sxs-lookup"><span data-stu-id="b3ccc-110">You should also review [Preparing your Environment for MBAM 1.0](preparing-your-environment-for-mbam-10.md) before you begin the MBAM evaluation deployment.</span></span>

### <span data-ttu-id="b3ccc-111">规划 MBAM 评估部署</span><span class="sxs-lookup"><span data-stu-id="b3ccc-111">Plan for an MBAM Evaluation Deployment</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left"><span data-ttu-id="b3ccc-112">任务</span><span class="sxs-lookup"><span data-stu-id="b3ccc-112">Task</span></span></th>
<th align="left"><span data-ttu-id="b3ccc-113">引用</span><span class="sxs-lookup"><span data-stu-id="b3ccc-113">References</span></span></th>
<th align="left"><span data-ttu-id="b3ccc-114">注释</span><span class="sxs-lookup"><span data-stu-id="b3ccc-114">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="b3ccc-115">查看有关 MBAM 的入门信息，以在开始部署规划之前对产品进行基本的了解。</span><span class="sxs-lookup"><span data-stu-id="b3ccc-115">Review the Getting Started information about MBAM to gain a basic understanding of the product before you begin your deployment planning.</span></span></p></td>
<td align="left"><p><a href="getting-started-with-mbam-10.md" data-raw-source="[Getting Started with MBAM 1.0](getting-started-with-mbam-10.md)"><span data-ttu-id="b3ccc-116">MBAM 1.0 入门</span><span class="sxs-lookup"><span data-stu-id="b3ccc-116">Getting Started with MBAM 1.0</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p></p>
<p><span data-ttu-id="b3ccc-117">为 MBAM 安装准备你的计算环境。</span><span class="sxs-lookup"><span data-stu-id="b3ccc-117">Prepare your computing environment for the MBAM installation.</span></span> <span data-ttu-id="b3ccc-118">若要执行此操作，必须在将托管 MBAM 数据库的 SQL Server 实例上启用透明数据加密（TDE）。</span><span class="sxs-lookup"><span data-stu-id="b3ccc-118">To do so, you must enable the Transparent Data Encryption (TDE) on the SQL Server instances that will host MBAM databases.</span></span> <span data-ttu-id="b3ccc-119">若要在你的实验室环境中启用 TDE，你可以创建一个 .sql 文件，以便针对托管在 MBAM 将使用的 SQL Server 实例上的 master 数据库运行。</span><span class="sxs-lookup"><span data-stu-id="b3ccc-119">To enable TDE in your lab environment, you can create a .sql file to run against the master database that is hosted on the instance of the SQL Server that MBAM will use.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="b3ccc-120">注意</span><span class="sxs-lookup"><span data-stu-id="b3ccc-120">Note</span></span></strong><br/><p><span data-ttu-id="b3ccc-121">你可以使用以下示例为你的实验室环境创建 .sql 文件，以便在将托管 MBAM 数据库的 SQL Server 实例上快速启用 TDE。</span><span class="sxs-lookup"><span data-stu-id="b3ccc-121">You can use the following example to create a .sql file for your lab environment to quickly enable TDE on the SQL Server instance that will host the MBAM databases.</span></span> <span data-ttu-id="b3ccc-122">这些 SQL Server 命令将使用本地签名的 SQL Server 证书启用 TDE。</span><span class="sxs-lookup"><span data-stu-id="b3ccc-122">These SQL Server commands will enable TDE by using a locally signed SQL Server certificate.</span></span> <span data-ttu-id="b3ccc-123">确保将 TDE 证书及其关联的加密密钥备份到 C:\Backup 的示例本地备份路径 <em> </em> 。</span><span class="sxs-lookup"><span data-stu-id="b3ccc-123">Make sure to back up the TDE certificate and its associated encryption key to the example local backup path of <em>C:\Backup</em>.</span></span> <span data-ttu-id="b3ccc-124">恢复数据库或将证书和密钥移动到具有 TDE 加密的另一台服务器时，需要 TDE 证书和密钥。</span><span class="sxs-lookup"><span data-stu-id="b3ccc-124">The TDE certificate and key are required when recover the database or move the certificate and key to another server that has TDE encryption in place.</span></span></p>
</div>
<div>

</div>
<pre class="syntax" space="preserve"><code>USE master;
GO
CREATE MASTER KEY ENCRYPTION BY PASSWORD = &#39;P@55w0rd&#39;;
GO
CREATE CERTIFICATE tdeCert WITH SUBJECT = &#39;TDE Certificate&#39;;
GO
BACKUP CERTIFICATE tdeCert TO FILE = &#39;C:\Backup\TDECertificate.cer&#39;
   WITH PRIVATE KEY (
         FILE = &#39;C:\Backup\TDECertificateKey.pvk&#39;,
         ENCRYPTION BY PASSWORD = &#39;P@55w0rd&#39;);
GO</code></pre></td>
<td align="left"><p><a href="mbam-10-deployment-prerequisites.md" data-raw-source="[MBAM 1.0 Deployment Prerequisites](mbam-10-deployment-prerequisites.md)"><span data-ttu-id="b3ccc-125">MBAM 1.0 部署先决条件</span><span class="sxs-lookup"><span data-stu-id="b3ccc-125">MBAM 1.0 Deployment Prerequisites</span></span></a></p>
<p><a href="https://go.microsoft.com/fwlink/?LinkId=269703" data-raw-source="[Database Encryption in SQL Server 2008 Enterprise Edition](https://go.microsoft.com/fwlink/?LinkId=269703)"><span data-ttu-id="b3ccc-126">SQL Server 2008 企业版中的数据库加密</span><span class="sxs-lookup"><span data-stu-id="b3ccc-126">Database Encryption in SQL Server 2008 Enterprise Edition</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="b3ccc-127">规划和配置 MBAM 组策略要求。</span><span class="sxs-lookup"><span data-stu-id="b3ccc-127">Plan for and configure MBAM Group Policy requirements.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-10-group-policy-requirements.md" data-raw-source="[Planning for MBAM 1.0 Group Policy Requirements](planning-for-mbam-10-group-policy-requirements.md)"><span data-ttu-id="b3ccc-128">计划 MBAM 1.0 组策略要求</span><span class="sxs-lookup"><span data-stu-id="b3ccc-128">Planning for MBAM 1.0 Group Policy Requirements</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="b3ccc-129">规划和创建必要的 Active Directory 域服务安全组，并针对 MBAM 本地安全组成员身份要求进行规划。</span><span class="sxs-lookup"><span data-stu-id="b3ccc-129">Plan for and create the necessary Active Directory Domain Services security groups and plan for MBAM local security group membership requirements.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-10-administrator-roles.md" data-raw-source="[Planning for MBAM 1.0 Administrator Roles](planning-for-mbam-10-administrator-roles.md)"><span data-ttu-id="b3ccc-130">计划 MBAM 1.0 管理员角色</span><span class="sxs-lookup"><span data-stu-id="b3ccc-130">Planning for MBAM 1.0 Administrator Roles</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="b3ccc-131">规划 MBAM Server 功能部署。</span><span class="sxs-lookup"><span data-stu-id="b3ccc-131">Plan for MBAM Server feature deployment.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-10-server-deployment.md" data-raw-source="[Planning for MBAM 1.0 Server Deployment](planning-for-mbam-10-server-deployment.md)"><span data-ttu-id="b3ccc-132">计划 MBAM 1.0 服务器部署</span><span class="sxs-lookup"><span data-stu-id="b3ccc-132">Planning for MBAM 1.0 Server Deployment</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="b3ccc-133">规划 MBAM 客户端部署。</span><span class="sxs-lookup"><span data-stu-id="b3ccc-133">Plan for MBAM Client deployment.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-10-client-deployment.md" data-raw-source="[Planning for MBAM 1.0 Client Deployment](planning-for-mbam-10-client-deployment.md)"><span data-ttu-id="b3ccc-134">计划 MBAM 1.0 客户端部署</span><span class="sxs-lookup"><span data-stu-id="b3ccc-134">Planning for MBAM 1.0 Client Deployment</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="b3ccc-135">执行 MBAM 评估部署</span><span class="sxs-lookup"><span data-stu-id="b3ccc-135">Perform an MBAM Evaluation Deployment</span></span>

<span data-ttu-id="b3ccc-136">完成必要的规划和软件必备安装以准备 MBAM 安装的计算环境后，您可以开始 MBAM 评估部署。</span><span class="sxs-lookup"><span data-stu-id="b3ccc-136">After you complete the necessary planning and software prerequisite installations to prepare your computing environment for an MBAM installation, you can begin the MBAM evaluation deployment.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="b3ccc-137">查看 MBAM 支持的配置信息，确保所选客户端和服务器计算机支持 MBAM 功能安装。</span><span class="sxs-lookup"><span data-stu-id="b3ccc-137">Review the MBAM supported configurations information to make sure that the selected client and server computers are supported for the MBAM feature installation.</span></span></p></td>
<td align="left"><p><a href="mbam-10-supported-configurations.md" data-raw-source="[MBAM 1.0 Supported Configurations](mbam-10-supported-configurations.md)"><span data-ttu-id="b3ccc-138">MBAM 1.0 支持的配置</span><span class="sxs-lookup"><span data-stu-id="b3ccc-138">MBAM 1.0 Supported Configurations</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="b3ccc-139">运行 MBAM 安装程序以在单个服务器上部署 MBAM 服务器功能，以供评估之用。</span><span class="sxs-lookup"><span data-stu-id="b3ccc-139">Run MBAM Setup to deploy MBAM Server features on a single server for evaluation purposes.</span></span></p></td>
<td align="left"><p><a href="how-to-install-and-configure-mbam-on-a-single-server-mbam-1.md" data-raw-source="[How to Install and Configure MBAM on a Single Server](how-to-install-and-configure-mbam-on-a-single-server-mbam-1.md)"><span data-ttu-id="b3ccc-140">如何在单个服务器上安装和配置 MBAM</span><span class="sxs-lookup"><span data-stu-id="b3ccc-140">How to Install and Configure MBAM on a Single Server</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="b3ccc-141">将在计划阶段创建的 Active Directory 域服务安全组添加到新的 MBAM 服务器上的相应本地 MBAM 服务器功能本地组。</span><span class="sxs-lookup"><span data-stu-id="b3ccc-141">Add the Active Directory Domain Services security groups that you created during the planning phase to the appropriate local MBAM Server feature local groups on the new MBAM server.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-10-administrator-roles.md" data-raw-source="[Planning for MBAM 1.0 Administrator Roles](planning-for-mbam-10-administrator-roles.md)"><span data-ttu-id="b3ccc-142">规划 MBAM 1.0 管理员角色 </a> 以及 <a href="how-to-manage-mbam-administrator-roles-mbam-1.md" data-raw-source="[How to Manage MBAM Administrator Roles](how-to-manage-mbam-administrator-roles-mbam-1.md)"> 如何管理 MBAM 管理员角色</span><span class="sxs-lookup"><span data-stu-id="b3ccc-142">Planning for MBAM 1.0 Administrator Roles</a> and <a href="how-to-manage-mbam-administrator-roles-mbam-1.md" data-raw-source="[How to Manage MBAM Administrator Roles](how-to-manage-mbam-administrator-roles-mbam-1.md)">How to Manage MBAM Administrator Roles</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="b3ccc-143">创建和部署所需的 MBAM 组策略对象。</span><span class="sxs-lookup"><span data-stu-id="b3ccc-143">Create and deploy the required MBAM Group Policy Objects.</span></span></p></td>
<td align="left"><p><a href="deploying-mbam-10-group-policy-objects.md" data-raw-source="[Deploying MBAM 1.0 Group Policy Objects](deploying-mbam-10-group-policy-objects.md)"><span data-ttu-id="b3ccc-144">部署 MBAM 1.0 组策略对象</span><span class="sxs-lookup"><span data-stu-id="b3ccc-144">Deploying MBAM 1.0 Group Policy Objects</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="b3ccc-145">部署 MBAM 客户端软件。</span><span class="sxs-lookup"><span data-stu-id="b3ccc-145">Deploy the MBAM Client software.</span></span></p></td>
<td align="left"><p><a href="deploying-the-mbam-10-client.md" data-raw-source="[Deploying the MBAM 1.0 Client](deploying-the-mbam-10-client.md)"><span data-ttu-id="b3ccc-146">部署 MBAM 1.0 客户端</span><span class="sxs-lookup"><span data-stu-id="b3ccc-146">Deploying the MBAM 1.0 Client</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="b3ccc-147">为 MBAM 评估配置实验室计算机</span><span class="sxs-lookup"><span data-stu-id="b3ccc-147">Configure Lab Computers for MBAM Evaluation</span></span>


<span data-ttu-id="b3ccc-148">你可以使用注册表编辑器更改 MBAM 客户端状态报告上的频率设置。</span><span class="sxs-lookup"><span data-stu-id="b3ccc-148">You can change the frequency settings on the MBAM Client status reporting by using Registry Editor.</span></span> <span data-ttu-id="b3ccc-149">但是，这些修改只应用于测试目的。</span><span class="sxs-lookup"><span data-stu-id="b3ccc-149">However, these modifications should be used for testing purposes only.</span></span>

**<span data-ttu-id="b3ccc-150">警告</span><span class="sxs-lookup"><span data-stu-id="b3ccc-150">Warning</span></span>**  
<span data-ttu-id="b3ccc-151">本主题介绍如何使用注册表编辑器更改 Windows 注册表。</span><span class="sxs-lookup"><span data-stu-id="b3ccc-151">This topic describes how to change the Windows registry by using Registry Editor.</span></span> <span data-ttu-id="b3ccc-152">如果不正确地更改 Windows 注册表，则可能会导致严重问题，可能需要重新安装 Windows。</span><span class="sxs-lookup"><span data-stu-id="b3ccc-152">If you change the Windows registry incorrectly, you can cause serious problems that might require you to reinstall Windows.</span></span> <span data-ttu-id="b3ccc-153">在更改注册表之前，应创建注册表文件（.dat 和 .dat）的备份副本。</span><span class="sxs-lookup"><span data-stu-id="b3ccc-153">You should make a backup copy of the registry files (System.dat and User.dat) before you change the registry.</span></span> <span data-ttu-id="b3ccc-154">Microsoft 无法保证更改注册表时可能出现的问题可以解决。</span><span class="sxs-lookup"><span data-stu-id="b3ccc-154">Microsoft cannot guarantee that the problems that might occur when you change the registry can be resolved.</span></span> <span data-ttu-id="b3ccc-155">更改注册表的风险由您自己承担。</span><span class="sxs-lookup"><span data-stu-id="b3ccc-155">Change the registry at your own risk.</span></span>



### <a href="" id="modify-the-frequency-settings-on-mbam-client-status-reporting-"></a><span data-ttu-id="b3ccc-156">在 MBAM 客户端状态报告上修改频率设置</span><span class="sxs-lookup"><span data-stu-id="b3ccc-156">Modify the Frequency Settings on MBAM Client Status Reporting</span></span>

<span data-ttu-id="b3ccc-157">当设置为使用组策略时，MBAM 客户端唤醒和状态报告频率的最小值为90分钟。</span><span class="sxs-lookup"><span data-stu-id="b3ccc-157">The MBAM Client wakeup and status reporting frequencies have a minimum value of 90 minutes when they are set to use Group Policy.</span></span> <span data-ttu-id="b3ccc-158">你可以通过将 Windows 注册表编辑为更低的值来更改 MBAM 客户端计算机上的这些频率，这将有助于加速测试。</span><span class="sxs-lookup"><span data-stu-id="b3ccc-158">You can change these frequencies on MBAM client computers by editing the Windows registry to lower values, which will help speed up the testing.</span></span> <span data-ttu-id="b3ccc-159">若要修改 MBAM 客户端状态报告上的频率设置，请使用注册表编辑器导航到**HKLM\\Software\\Policies\\FVE\\MDOPBitLockerManagement**，将**ClientWakeupFrequency**和**StatusReportingFrequency**的值更改为**1** ，作为最小客户端支持的值，然后重新启动 BitLocker 管理客户端服务。</span><span class="sxs-lookup"><span data-stu-id="b3ccc-159">To modify the frequency settings on MBAM Client status reporting, use a registry editor to navigate to **HKLM\\Software\\Policies\\FVE\\MDOPBitLockerManagement**, change the values for **ClientWakeupFrequency** and **StatusReportingFrequency** to **1** as the minimum client supported value, and then restart BitLocker Management Client Service.</span></span> <span data-ttu-id="b3ccc-160">进行此更改时，MBAM 客户将每分钟报告一次。</span><span class="sxs-lookup"><span data-stu-id="b3ccc-160">When you make this change, the MBAM Client will report every minute.</span></span> <span data-ttu-id="b3ccc-161">只有在注册表中手动执行此操作时，才能将值设置为 "低"。</span><span class="sxs-lookup"><span data-stu-id="b3ccc-161">You can set values this low only when you do so manually in the registry.</span></span>

### <a href="" id="modify-the-startup-delay-on-mbam-client-service-"></a><span data-ttu-id="b3ccc-162">修改 MBAM 客户端服务上的启动延迟</span><span class="sxs-lookup"><span data-stu-id="b3ccc-162">Modify the Startup Delay on MBAM Client Service</span></span>

<span data-ttu-id="b3ccc-163">除了 MBAM 客户端唤醒和状态报告频率之外，在客户端计算机上启动 MBAM 客户端代理服务时，随机延迟最多为90分钟。</span><span class="sxs-lookup"><span data-stu-id="b3ccc-163">In addition to the MBAM Client wakeup and status reporting frequencies, there is a random delay of up to 90 minutes when the MBAM Client agent service starts on client computers.</span></span> <span data-ttu-id="b3ccc-164">如果不希望随机延迟，请在 " **HKLM\\Software\\Microsoft\\MBAM**" 下创建**NoStartupDelay**的**DWORD**值，将其值设置为**1**，然后重新启动 BitLocker 管理客户端服务。</span><span class="sxs-lookup"><span data-stu-id="b3ccc-164">If you do not want the random delay, create a **DWORD** value of **NoStartupDelay** under **HKLM\\Software\\Microsoft\\MBAM**, set its value to **1**, and then restart BitLocker Management Client Service.</span></span>

## <span data-ttu-id="b3ccc-165">相关主题</span><span class="sxs-lookup"><span data-stu-id="b3ccc-165">Related topics</span></span>


[<span data-ttu-id="b3ccc-166">MBAM 1.0 入门</span><span class="sxs-lookup"><span data-stu-id="b3ccc-166">Getting Started with MBAM 1.0</span></span>](getting-started-with-mbam-10.md)









