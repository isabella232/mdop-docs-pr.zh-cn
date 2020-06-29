---
title: 评估 MBAM 2.0
description: 评估 MBAM 2.0
author: dansimp
ms.assetid: bfc77eec-0fd7-4fec-9c78-6870afa87152
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b7be883f44f5f09a904f619972ae3e7c35261d26
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803628"
---
# <span data-ttu-id="dc50f-103">评估 MBAM 2.0</span><span class="sxs-lookup"><span data-stu-id="dc50f-103">Evaluating MBAM 2.0</span></span>


<span data-ttu-id="dc50f-104">在将 Microsoft BitLocker 管理和监视（MBAM）部署到生产环境之前，应在测试环境中对其进行评估。</span><span class="sxs-lookup"><span data-stu-id="dc50f-104">Before deploying Microsoft BitLocker Administration and Monitoring (MBAM) into a production environment, you should evaluate it in a test environment.</span></span> <span data-ttu-id="dc50f-105">本主题中的信息可用于在单服务器测试环境中使用独立拓扑设置 Microsoft BitLocker 管理和监视，仅供评估之用。</span><span class="sxs-lookup"><span data-stu-id="dc50f-105">The information in this topic can be used to set up Microsoft BitLocker Administration and Monitoring with a Stand-alone topology in a single-server test environment for evaluation purposes only.</span></span> <span data-ttu-id="dc50f-106">对于生产环境，不推荐使用单服务器拓扑。</span><span class="sxs-lookup"><span data-stu-id="dc50f-106">A single-server topology is not recommended for production environments.</span></span>

<span data-ttu-id="dc50f-107">有关在测试环境中部署 MBAM 的说明，请参阅[如何在单个服务器上安装和配置 MBAM](how-to-install-and-configure-mbam-on-a-single-server-mbam-2.md)。</span><span class="sxs-lookup"><span data-stu-id="dc50f-107">For instructions on deploying MBAM in a test environment, see [How to Install and Configure MBAM on a Single Server](how-to-install-and-configure-mbam-on-a-single-server-mbam-2.md).</span></span>

## <span data-ttu-id="dc50f-108">设置测试环境</span><span class="sxs-lookup"><span data-stu-id="dc50f-108">Setting up the Test Environment</span></span>


<span data-ttu-id="dc50f-109">即使你要在测试环境中设置要评估的 MBAM 的非生产实例，你仍应验证你是否满足先决条件和硬件和软件要求。</span><span class="sxs-lookup"><span data-stu-id="dc50f-109">Even though you are setting up a non-production instance of MBAM to evaluate in a test environment, you should still verify that you have met the prerequisites and hardware and software requirements.</span></span> <span data-ttu-id="dc50f-110">开始安装之前，请参阅[MBAM 2.0 部署先决条件](mbam-20-deployment-prerequisites-mbam-2.md)、 [MBAM 2.0 支持的配置](mbam-20-supported-configurations-mbam-2.md)和[为 MBAM 2.0 准备环境](preparing-your-environment-for-mbam-20-mbam-2.md)。</span><span class="sxs-lookup"><span data-stu-id="dc50f-110">Before you start the installation, see [MBAM 2.0 Deployment Prerequisites](mbam-20-deployment-prerequisites-mbam-2.md), [MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md), and [Preparing your Environment for MBAM 2.0](preparing-your-environment-for-mbam-20-mbam-2.md).</span></span>

### <span data-ttu-id="dc50f-111">规划 MBAM 评估部署</span><span class="sxs-lookup"><span data-stu-id="dc50f-111">Plan for an MBAM Evaluation Deployment</span></span>

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
<th align="left"><span data-ttu-id="dc50f-112">任务</span><span class="sxs-lookup"><span data-stu-id="dc50f-112">Task</span></span></th>
<th align="left"><span data-ttu-id="dc50f-113">引用</span><span class="sxs-lookup"><span data-stu-id="dc50f-113">References</span></span></th>
<th align="left"><span data-ttu-id="dc50f-114">注释</span><span class="sxs-lookup"><span data-stu-id="dc50f-114">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="dc50f-115">查看有关 MBAM 的入门信息，以在开始部署规划之前对产品进行基本的了解。</span><span class="sxs-lookup"><span data-stu-id="dc50f-115">Review the Getting Started information about MBAM to gain a basic understanding of the product before beginning deployment planning.</span></span></p></td>
<td align="left"><p><a href="getting-started-with-mbam-20-mbam-2.md" data-raw-source="[Getting Started with MBAM 2.0](getting-started-with-mbam-20-mbam-2.md)"><span data-ttu-id="dc50f-116">MBAM 2.0 入门</span><span class="sxs-lookup"><span data-stu-id="dc50f-116">Getting Started with MBAM 2.0</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="dc50f-117">规划 MBAM 2.0 部署先决条件并准备你的计算环境。</span><span class="sxs-lookup"><span data-stu-id="dc50f-117">Plan for MBAM 2.0 Deployment Prerequisites and prepare your computing environment.</span></span></p></td>
<td align="left"><p><a href="mbam-20-deployment-prerequisites-mbam-2.md" data-raw-source="[MBAM 2.0 Deployment Prerequisites](mbam-20-deployment-prerequisites-mbam-2.md)"><span data-ttu-id="dc50f-118">MBAM 2.0 部署先决条件</span><span class="sxs-lookup"><span data-stu-id="dc50f-118">MBAM 2.0 Deployment Prerequisites</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="dc50f-119">规划和配置 MBAM 组策略要求。</span><span class="sxs-lookup"><span data-stu-id="dc50f-119">Plan for and configure MBAM Group Policy requirements.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-20-group-policy-requirements-mbam-2.md" data-raw-source="[Planning for MBAM 2.0 Group Policy Requirements](planning-for-mbam-20-group-policy-requirements-mbam-2.md)"><span data-ttu-id="dc50f-120">计划 MBAM 2.0 组策略要求</span><span class="sxs-lookup"><span data-stu-id="dc50f-120">Planning for MBAM 2.0 Group Policy Requirements</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="dc50f-121">规划和创建必要的 ActiveDirectoryDomainServices 安全组，并针对 MBAM 本地安全组成员身份要求进行规划。</span><span class="sxs-lookup"><span data-stu-id="dc50f-121">Plan for and create necessary ActiveDirectoryDomainServices security groups, and plan for MBAM local security group membership requirements.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-20-administrator-roles-mbam-2.md" data-raw-source="[Planning for MBAM 2.0 Administrator Roles](planning-for-mbam-20-administrator-roles-mbam-2.md)"><span data-ttu-id="dc50f-122">计划 MBAM 2.0 管理员角色</span><span class="sxs-lookup"><span data-stu-id="dc50f-122">Planning for MBAM 2.0 Administrator Roles</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="dc50f-123">规划部署 MBAM Server 功能部署。</span><span class="sxs-lookup"><span data-stu-id="dc50f-123">Plan for deploying MBAM Server feature deployment.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-20-server-deployment-mbam-2.md" data-raw-source="[Planning for MBAM 2.0 Server Deployment](planning-for-mbam-20-server-deployment-mbam-2.md)"><span data-ttu-id="dc50f-124">计划 MBAM 2.0 服务器部署</span><span class="sxs-lookup"><span data-stu-id="dc50f-124">Planning for MBAM 2.0 Server Deployment</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="dc50f-125">规划部署 MBAM 客户端部署。</span><span class="sxs-lookup"><span data-stu-id="dc50f-125">Plan for deploying MBAM Client deployment.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-20-client-deployment-mbam-2.md" data-raw-source="[Planning for MBAM 2.0 Client Deployment](planning-for-mbam-20-client-deployment-mbam-2.md)"><span data-ttu-id="dc50f-126">计划 MBAM 2.0 客户端部署</span><span class="sxs-lookup"><span data-stu-id="dc50f-126">Planning for MBAM 2.0 Client Deployment</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="dc50f-127">执行 MBAM 评估部署</span><span class="sxs-lookup"><span data-stu-id="dc50f-127">Perform an MBAM Evaluation Deployment</span></span>

<span data-ttu-id="dc50f-128">完成必要的规划和软件必备安装以准备 MBAM 安装的计算环境后，您可以开始 MBAM 评估部署。</span><span class="sxs-lookup"><span data-stu-id="dc50f-128">After completing the necessary planning and software prerequisite installations to prepare your computing environment for the MBAM installation, you can begin the MBAM evaluation deployment.</span></span>

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
<td align="left"><p><span data-ttu-id="dc50f-129">查看 MBAM 支持的配置信息，确保所选客户端和服务器计算机支持 MBAM 功能安装。</span><span class="sxs-lookup"><span data-stu-id="dc50f-129">Review the MBAM supported configurations information to make sure that selected client and server computers are supported for MBAM feature installation.</span></span></p></td>
<td align="left"><p><a href="mbam-20-supported-configurations-mbam-2.md" data-raw-source="[MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md)"><span data-ttu-id="dc50f-130">MBAM 2.0 支持的配置</span><span class="sxs-lookup"><span data-stu-id="dc50f-130">MBAM 2.0 Supported Configurations</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="dc50f-131">运行 MBAM 安装程序以在单个服务器上部署 MBAM 服务器功能，以供评估之用。</span><span class="sxs-lookup"><span data-stu-id="dc50f-131">Run MBAM Setup to deploy MBAM Server features on a single server for evaluation purposes.</span></span></p></td>
<td align="left"><p><a href="how-to-install-and-configure-mbam-on-a-single-server-mbam-2.md" data-raw-source="[How to Install and Configure MBAM on a Single Server](how-to-install-and-configure-mbam-on-a-single-server-mbam-2.md)"><span data-ttu-id="dc50f-132">如何在单个服务器上安装和配置 MBAM</span><span class="sxs-lookup"><span data-stu-id="dc50f-132">How to Install and Configure MBAM on a Single Server</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="dc50f-133">将在计划阶段创建的 ActiveDirectoryDomainServices 安全组添加到新 MBAM 服务器上相应的本地 MBAM 服务器功能本地组。</span><span class="sxs-lookup"><span data-stu-id="dc50f-133">Add ActiveDirectoryDomainServices security groups, that you created during the planning phase, to the appropriate local MBAM Server feature local groups on the new MBAM Server.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-20-administrator-roles-mbam-2.md" data-raw-source="[Planning for MBAM 2.0 Administrator Roles](planning-for-mbam-20-administrator-roles-mbam-2.md)"><span data-ttu-id="dc50f-134">规划 MBAM 2.0 管理员角色 </a> 以及 <a href="how-to-manage-mbam-administrator-roles-mbam-2.md" data-raw-source="[How to Manage MBAM Administrator Roles](how-to-manage-mbam-administrator-roles-mbam-2.md)"> 如何管理 MBAM 管理员角色</span><span class="sxs-lookup"><span data-stu-id="dc50f-134">Planning for MBAM 2.0 Administrator Roles</a> and <a href="how-to-manage-mbam-administrator-roles-mbam-2.md" data-raw-source="[How to Manage MBAM Administrator Roles](how-to-manage-mbam-administrator-roles-mbam-2.md)">How to Manage MBAM Administrator Roles</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="dc50f-135">创建和部署所需的 MBAM 组策略对象。</span><span class="sxs-lookup"><span data-stu-id="dc50f-135">Create and deploy required MBAM Group Policy Objects.</span></span></p></td>
<td align="left"><p><a href="deploying-mbam-20-group-policy-objects-mbam-2.md" data-raw-source="[Deploying MBAM 2.0 Group Policy Objects](deploying-mbam-20-group-policy-objects-mbam-2.md)"><span data-ttu-id="dc50f-136">部署 MBAM 2.0 组策略对象</span><span class="sxs-lookup"><span data-stu-id="dc50f-136">Deploying MBAM 2.0 Group Policy Objects</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="dc50f-137">部署 MBAM 客户端软件。</span><span class="sxs-lookup"><span data-stu-id="dc50f-137">Deploy the MBAM Client software.</span></span></p></td>
<td align="left"><p><a href="deploying-the-mbam-20-client-mbam-2.md" data-raw-source="[Deploying the MBAM 2.0 Client](deploying-the-mbam-20-client-mbam-2.md)"><span data-ttu-id="dc50f-138">部署 MBAM 2.0 客户端</span><span class="sxs-lookup"><span data-stu-id="dc50f-138">Deploying the MBAM 2.0 Client</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="dc50f-139">为 MBAM 评估配置实验室计算机</span><span class="sxs-lookup"><span data-stu-id="dc50f-139">Configure Lab Computers for MBAM Evaluation</span></span>


<span data-ttu-id="dc50f-140">本部分包含可用于加速 MBAM 客户端状态报告的信息。</span><span class="sxs-lookup"><span data-stu-id="dc50f-140">This section contains information that can be used to speed up the MBAM Client status reporting.</span></span> <span data-ttu-id="dc50f-141">但是，这些修改只应用于测试目的。</span><span class="sxs-lookup"><span data-stu-id="dc50f-141">However, these modifications should be used for testing purposes only.</span></span>

<span data-ttu-id="dc50f-142">**注意** 下一节中的信息介绍了如何修改 Windows 注册表。</span><span class="sxs-lookup"><span data-stu-id="dc50f-142">**Note** The information in following section describes how to modify the Windows registry.</span></span> <span data-ttu-id="dc50f-143">注册表编辑器使用不当可能导致严重问题，可能需要重新安装 Windows。</span><span class="sxs-lookup"><span data-stu-id="dc50f-143">Using Registry Editor incorrectly can cause serious problems that may require you to reinstall Windows.</span></span> <span data-ttu-id="dc50f-144">Microsoft 无法保证无法通过错误地使用注册表编辑器来解决所产生的问题。</span><span class="sxs-lookup"><span data-stu-id="dc50f-144">Microsoft cannot guarantee that problems resulting from the incorrect use of Registry Editor can be solved.</span></span> <span data-ttu-id="dc50f-145">使用注册表编辑器的风险由您自己承担。</span><span class="sxs-lookup"><span data-stu-id="dc50f-145">Use Registry Editor at your own risk.</span></span>

 

### <span data-ttu-id="dc50f-146">修改 MBAM 客户端状态报告频率设置</span><span class="sxs-lookup"><span data-stu-id="dc50f-146">Modify MBAM Client Status Reporting Frequency Settings</span></span>

<span data-ttu-id="dc50f-147">MBAM 客户端唤醒和状态报告频率在使用组策略设置时的最小值为90分钟。</span><span class="sxs-lookup"><span data-stu-id="dc50f-147">The MBAM Client wakeup and status reporting frequencies have a minimum value of 90 minutes when they are set using Group Policy.</span></span> <span data-ttu-id="dc50f-148">你可以使用 Windows 注册表将这些频率更改为 MBAM 客户端计算机上的较低值，以帮助加速测试。</span><span class="sxs-lookup"><span data-stu-id="dc50f-148">You can use the Windows registry to change these frequencies to a lower value on MBAM client computers to help speed up testing.</span></span>

<span data-ttu-id="dc50f-149">要修改 MBAM 客户端状态报告频率设置，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="dc50f-149">To modify the MBAM Client status reporting frequency settings:</span></span>

1.  <span data-ttu-id="dc50f-150">使用注册表编辑器导航到**HKLM\\Software\\Policies\\Microsoft\\FVE\\MDOPBitLockerManagement**。</span><span class="sxs-lookup"><span data-stu-id="dc50f-150">Use a registry editor to navigate to **HKLM\\Software\\Policies\\Microsoft\\FVE\\MDOPBitLockerManagement**.</span></span>

2.  <span data-ttu-id="dc50f-151">将**ClientWakeupFrequency**和**StatusReportingFrequency**的值更改为**1** ，以支持最小客户端支持的值。</span><span class="sxs-lookup"><span data-stu-id="dc50f-151">Change the values for **ClientWakeupFrequency** and **StatusReportingFrequency** to **1** as the minimum client-supported value.</span></span> <span data-ttu-id="dc50f-152">此更改导致 MBAM 客户端每分钟报告一次。</span><span class="sxs-lookup"><span data-stu-id="dc50f-152">This change causes the MBAM Client to report every minute.</span></span>

3.  <span data-ttu-id="dc50f-153">重新启动**BitLocker 管理客户端服务**。</span><span class="sxs-lookup"><span data-stu-id="dc50f-153">Restart **BitLocker Management Client Service**.</span></span>

<span data-ttu-id="dc50f-154">**注意** 若要设置这种低的值，必须在注册表中手动设置它们。</span><span class="sxs-lookup"><span data-stu-id="dc50f-154">**Note** To set values that are this low, you must set them in the registry manually.</span></span>

 

### <span data-ttu-id="dc50f-155">修改 MBAM 客户端服务启动延迟</span><span class="sxs-lookup"><span data-stu-id="dc50f-155">Modify MBAM Client Service Startup Delay</span></span>

<span data-ttu-id="dc50f-156">除了 MBAM 客户端唤醒和状态报告频率之外，在客户端计算机上启动 MBAM 客户端代理服务时，随机延迟最多为90分钟。</span><span class="sxs-lookup"><span data-stu-id="dc50f-156">In addition to the MBAM Client wakeup and status reporting frequencies, there is a random delay of up to 90 minutes when the MBAM Client agent service starts on client computers.</span></span> <span data-ttu-id="dc50f-157">如果不希望随机延迟，请在 " **HKLM\\Software\\Microsoft\\MBAM**" 下创建**NoStartupDelay**的**DWORD**值，将其值设置为**1**，然后重新启动**BitLocker 管理客户端服务**。</span><span class="sxs-lookup"><span data-stu-id="dc50f-157">If you do not want the random delay, create a **DWORD** value of **NoStartupDelay** under **HKLM\\Software\\Microsoft\\MBAM**, set its value to **1**, and then restart **BitLocker Management Client Service**.</span></span>

## <span data-ttu-id="dc50f-158">相关主题</span><span class="sxs-lookup"><span data-stu-id="dc50f-158">Related topics</span></span>


[<span data-ttu-id="dc50f-159">MBAM 2.0 入门</span><span class="sxs-lookup"><span data-stu-id="dc50f-159">Getting Started with MBAM 2.0</span></span>](getting-started-with-mbam-20-mbam-2.md)

 

 





