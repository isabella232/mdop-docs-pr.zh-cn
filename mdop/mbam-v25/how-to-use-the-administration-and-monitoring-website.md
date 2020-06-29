---
title: 如何使用管理和监控网站
description: 如何使用管理和监控网站
author: dansimp
ms.assetid: bb96a4e8-d4f4-4e6f-b7db-82d96998bfa6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9b9597e29a5a7a6236cb351d8d6d1f682edce3cf
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798197"
---
# <span data-ttu-id="1b51f-103">如何使用管理和监控网站</span><span class="sxs-lookup"><span data-stu-id="1b51f-103">How to Use the Administration and Monitoring Website</span></span>


<span data-ttu-id="1b51f-104">管理和监视网站（也称为帮助桌面）是用于 BitLocker 驱动器加密的管理界面。</span><span class="sxs-lookup"><span data-stu-id="1b51f-104">The Administration and Monitoring Website, also referred to as the Help Desk, is an administrative interface for BitLocker Drive Encryption.</span></span> <span data-ttu-id="1b51f-105">使用该网站查看报告、恢复最终用户的驱动器和管理最终用户的 TPMs，如下部分所述。</span><span class="sxs-lookup"><span data-stu-id="1b51f-105">Use the website to review reports, recover end users’ drives, and manage end users’ TPMs, as described in the following sections.</span></span>

<span data-ttu-id="1b51f-106">**注意** 如果在独立拓扑中使用 MBAM，则可以从 "管理和监视" 网站查看所有报表。</span><span class="sxs-lookup"><span data-stu-id="1b51f-106">**Note** If you are using MBAM in the Stand-alone topology, you view all reports from the Administration and Monitoring Website.</span></span> <span data-ttu-id="1b51f-107">如果您使用的是 Configuration Manager 集成拓扑，则可以在 "配置管理器" 中查看所有报表，但恢复审核报表除外，您可以从 "管理和监视" 网站继续查看。</span><span class="sxs-lookup"><span data-stu-id="1b51f-107">If you are using the Configuration Manager Integration topology, you view all reports in Configuration Manager, except the Recovery Audit report, which you continue to view from the Administration and Monitoring Website.</span></span> <span data-ttu-id="1b51f-108">有关报表的详细信息，请参阅[通过 MBAM 2.5 监视和报告 BitLocker 合规性](monitoring-and-reporting-bitlocker-compliance-with-mbam-25.md)。</span><span class="sxs-lookup"><span data-stu-id="1b51f-108">For more information about reports, see [Monitoring and Reporting BitLocker Compliance with MBAM 2.5](monitoring-and-reporting-bitlocker-compliance-with-mbam-25.md).</span></span>

 

## <span data-ttu-id="1b51f-109">使用管理和监视网站所需的角色</span><span class="sxs-lookup"><span data-stu-id="1b51f-109">Required roles for using the Administration and Monitoring Website</span></span>


<span data-ttu-id="1b51f-110">若要访问管理和监视网站的特定区域，你必须具有下列角色之一，这些角色是你在 Active Directory 中创建的组。</span><span class="sxs-lookup"><span data-stu-id="1b51f-110">To access specific areas of the Administration and Monitoring Website, you must have one of the following roles, which are groups that you create in Active Directory.</span></span> <span data-ttu-id="1b51f-111">你可以为这些组使用任何名称。</span><span class="sxs-lookup"><span data-stu-id="1b51f-111">You can use any name for these groups.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="1b51f-112">帐户</span><span class="sxs-lookup"><span data-stu-id="1b51f-112">Account</span></span></th>
<th align="left"><span data-ttu-id="1b51f-113">描述</span><span class="sxs-lookup"><span data-stu-id="1b51f-113">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1b51f-114">MBAM 高级帮助台用户</span><span class="sxs-lookup"><span data-stu-id="1b51f-114">MBAM Advanced Helpdesk Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="1b51f-115">提供对管理和监视网站的所有区域的访问权限。</span><span class="sxs-lookup"><span data-stu-id="1b51f-115">Provides access to all areas of the Administration and Monitoring Website.</span></span> <span data-ttu-id="1b51f-116">具有此角色的用户在帮助最终用户恢复其驱动器时，只需输入恢复密钥，而不是最终用户的域和用户名。</span><span class="sxs-lookup"><span data-stu-id="1b51f-116">Users who have this role enter only the recovery key, and not the end user’s domain and user name, when helping end users recover their drives.</span></span> <span data-ttu-id="1b51f-117">如果用户是 MBAM "支持人员" 组和 MBAM "高级帮助台用户" 组的成员，则 MBAM "高级帮助台用户" 组权限将替代 "MBAM 帮助台用户" 组权限。</span><span class="sxs-lookup"><span data-stu-id="1b51f-117">If a user is a member of both the MBAM Helpdesk Users group and the MBAM Advanced Helpdesk Users group, the MBAM Advanced Helpdesk Users group permissions override the MBAM Helpdesk Users Group permissions.</span></span></p>
<p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="1b51f-118">MBAM 帮助台用户</span><span class="sxs-lookup"><span data-stu-id="1b51f-118">MBAM Helpdesk Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="1b51f-119">提供对管理和监视网站的 "管理 TPM" 和 "驱动器恢复" 区域的访问权限。</span><span class="sxs-lookup"><span data-stu-id="1b51f-119">Provides access to the Manage TPM and Drive Recovery areas of the Administration and Monitoring Website.</span></span> <span data-ttu-id="1b51f-120">具有此角色的人员必须在使用任一区域时填写所有字段，包括最终用户的域和帐户名称。</span><span class="sxs-lookup"><span data-stu-id="1b51f-120">Individuals who have this role must fill in all fields, including the end-user’s domain and account name, when they use either area.</span></span></p>
<p><span data-ttu-id="1b51f-121">如果用户是 MBAM "支持人员" 组和 MBAM "高级帮助台用户" 组的成员，则 MBAM "高级帮助台用户" 组权限将替代 "MBAM 帮助台用户" 组权限。</span><span class="sxs-lookup"><span data-stu-id="1b51f-121">If a user is a member of both the MBAM Helpdesk Users group and the MBAM Advanced Helpdesk Users group, the MBAM Advanced Helpdesk Users group permissions override the MBAM Helpdesk Users Group permissions.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1b51f-122">MBAM 报表用户</span><span class="sxs-lookup"><span data-stu-id="1b51f-122">MBAM Report Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="1b51f-123">提供对 <strong> </strong> 管理和监控网站的 "报告" 区域中的报告的访问权限。</span><span class="sxs-lookup"><span data-stu-id="1b51f-123">Provides access to the reports in the <strong>Reports</strong> area of the Administration and Monitoring Website.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="1b51f-124">可在 "管理和监视" 网站上执行的任务</span><span class="sxs-lookup"><span data-stu-id="1b51f-124">Tasks you can perform on the Administration and Monitoring Website</span></span>


<span data-ttu-id="1b51f-125">下表总结了可在 "管理" 和 "监视" 网站上执行的任务，并提供了指向有关每个任务的详细信息的链接。</span><span class="sxs-lookup"><span data-stu-id="1b51f-125">The following table summarizes the tasks you can perform on the Administration and Monitoring Website and provides links to more information about each task.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="1b51f-126">任务</span><span class="sxs-lookup"><span data-stu-id="1b51f-126">Task</span></span></th>
<th align="left"><span data-ttu-id="1b51f-127">您可在其中访问任务的网站区域</span><span class="sxs-lookup"><span data-stu-id="1b51f-127">Area of the Website where you access the task</span></span></th>
<th align="left"><span data-ttu-id="1b51f-128">描述</span><span class="sxs-lookup"><span data-stu-id="1b51f-128">Description</span></span></th>
<th align="left"><span data-ttu-id="1b51f-129">有关详细信息</span><span class="sxs-lookup"><span data-stu-id="1b51f-129">For more information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1b51f-130">查看报告</span><span class="sxs-lookup"><span data-stu-id="1b51f-130">View reports</span></span></p></td>
<td align="left"><p><span data-ttu-id="1b51f-131">报告</span><span class="sxs-lookup"><span data-stu-id="1b51f-131">Reports</span></span></p></td>
<td align="left"><p><span data-ttu-id="1b51f-132">使你能够运行报告，以监视 BitLocker 使用情况、合规性和密钥恢复活动。</span><span class="sxs-lookup"><span data-stu-id="1b51f-132">Enables you to run reports to monitor BitLocker usage, compliance, and key recovery activity.</span></span> <span data-ttu-id="1b51f-133">报表提供有关企业合规性、单个计算机以及为特定计算机请求恢复密钥或 TPM OwnerAuth 程序包的数据。</span><span class="sxs-lookup"><span data-stu-id="1b51f-133">Reports provide data about enterprise compliance, individual computers, and who requested recovery keys or the TPM OwnerAuth package for a specific computer.</span></span></p></td>
<td align="left"><p><a href="viewing-mbam-25-reports-for-the-stand-alone-topology.md" data-raw-source="[Viewing MBAM 2.5 Reports for the Stand-alone Topology](viewing-mbam-25-reports-for-the-stand-alone-topology.md)"><span data-ttu-id="1b51f-134">查看独立拓扑的 MBAM 2.5 报告</span><span class="sxs-lookup"><span data-stu-id="1b51f-134">Viewing MBAM 2.5 Reports for the Stand-alone Topology</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="1b51f-135">确定丢失或被盗计算机的 BitLocker 加密状态</span><span class="sxs-lookup"><span data-stu-id="1b51f-135">Determine the BitLocker encryption status of lost or stolen computers</span></span></p></td>
<td align="left"><p><span data-ttu-id="1b51f-136">报告</span><span class="sxs-lookup"><span data-stu-id="1b51f-136">Reports</span></span></p></td>
<td align="left"><p><span data-ttu-id="1b51f-137">确定当计算机丢失或被盗时，卷是否已加密。</span><span class="sxs-lookup"><span data-stu-id="1b51f-137">Determine if a volume was encrypted if the computer is lost or stolen.</span></span></p></td>
<td align="left"><p><a href="how-to-determine-bitlocker-encryption-state-of-lost-computers-mbam-25.md" data-raw-source="[How to Determine BitLocker Encryption State of Lost Computers](how-to-determine-bitlocker-encryption-state-of-lost-computers-mbam-25.md)"><span data-ttu-id="1b51f-138">如何确定丢失计算机的 BitLocker 加密状态</span><span class="sxs-lookup"><span data-stu-id="1b51f-138">How to Determine BitLocker Encryption State of Lost Computers</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1b51f-139">恢复丢失的驱动器</span><span class="sxs-lookup"><span data-stu-id="1b51f-139">Recover lost drives</span></span></p></td>
<td align="left"><p><span data-ttu-id="1b51f-140">驱动器恢复</span><span class="sxs-lookup"><span data-stu-id="1b51f-140">Drive Recovery</span></span></p></td>
<td align="left"><p><span data-ttu-id="1b51f-141">恢复驱动器：</span><span class="sxs-lookup"><span data-stu-id="1b51f-141">Recover drives that are:</span></span></p>
<ul>
<li><p><span data-ttu-id="1b51f-142">在恢复模式下</span><span class="sxs-lookup"><span data-stu-id="1b51f-142">In recovery mode</span></span></p></li>
<li><p><span data-ttu-id="1b51f-143">已被移动</span><span class="sxs-lookup"><span data-stu-id="1b51f-143">Have been moved</span></span></p></li>
<li><p><span data-ttu-id="1b51f-144">已损坏</span><span class="sxs-lookup"><span data-stu-id="1b51f-144">Are corrupted</span></span></p></li>
</ul></td>
<td align="left"><ul>
<li><p><a href="how-to-recover-a-drive-in-recovery-mode-mbam-25.md" data-raw-source="[How to Recover a Drive in Recovery Mode](how-to-recover-a-drive-in-recovery-mode-mbam-25.md)"><span data-ttu-id="1b51f-145">如何在恢复模式下恢复驱动器</span><span class="sxs-lookup"><span data-stu-id="1b51f-145">How to Recover a Drive in Recovery Mode</span></span></a></p></li>
<li><p><a href="how-to-recover-a-moved-drive-mbam-25.md" data-raw-source="[How to Recover a Moved Drive](how-to-recover-a-moved-drive-mbam-25.md)"><span data-ttu-id="1b51f-146">如何恢复已移动的驱动器</span><span class="sxs-lookup"><span data-stu-id="1b51f-146">How to Recover a Moved Drive</span></span></a></p></li>
<li><p><a href="how-to-recover-a-corrupted-drive-mbam-25.md" data-raw-source="[How to Recover a Corrupted Drive](how-to-recover-a-corrupted-drive-mbam-25.md)"><span data-ttu-id="1b51f-147">如何恢复已损坏的驱动器</span><span class="sxs-lookup"><span data-stu-id="1b51f-147">How to Recover a Corrupted Drive</span></span></a></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="1b51f-148">重置 TPM 锁定</span><span class="sxs-lookup"><span data-stu-id="1b51f-148">Reset a TPM lockout</span></span></p></td>
<td align="left"><p><span data-ttu-id="1b51f-149">管理 TPM</span><span class="sxs-lookup"><span data-stu-id="1b51f-149">Manage TPM</span></span></p></td>
<td align="left"><p><span data-ttu-id="1b51f-150">提供对 MBAM 客户端收集的 TPM 数据的访问权限。</span><span class="sxs-lookup"><span data-stu-id="1b51f-150">Provides access to TPM data that has been collected by the MBAM Client.</span></span> <span data-ttu-id="1b51f-151">在 TPM 锁定中，使用 "管理和监视" 网站检索用于解锁 TPM 的必需密码文件。</span><span class="sxs-lookup"><span data-stu-id="1b51f-151">In a TPM lockout, use the Administration and Monitoring Website to retrieve the necessary password file to unlock the TPM.</span></span></p></td>
<td align="left"><p><a href="how-to-reset-a-tpm-lockout-mbam-25.md" data-raw-source="[How to Reset a TPM Lockout](how-to-reset-a-tpm-lockout-mbam-25.md)"><span data-ttu-id="1b51f-152">如何重置 TPM 锁定</span><span class="sxs-lookup"><span data-stu-id="1b51f-152">How to Reset a TPM Lockout</span></span></a></p></td>
</tr>
</tbody>
</table>

 


## <span data-ttu-id="1b51f-153">相关主题</span><span class="sxs-lookup"><span data-stu-id="1b51f-153">Related topics</span></span>


[<span data-ttu-id="1b51f-154">使用 MBAM 2.5 执行 BitLocker 管理</span><span class="sxs-lookup"><span data-stu-id="1b51f-154">Performing BitLocker Management with MBAM 2.5</span></span>](performing-bitlocker-management-with-mbam-25.md)

 

## <span data-ttu-id="1b51f-155">已获得 MBAM 的建议？</span><span class="sxs-lookup"><span data-stu-id="1b51f-155">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="1b51f-156">在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="1b51f-156">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="1b51f-157">对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="1b51f-157">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





