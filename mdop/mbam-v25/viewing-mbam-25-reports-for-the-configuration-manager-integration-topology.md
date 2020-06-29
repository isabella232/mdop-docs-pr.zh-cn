---
title: 查看 Configuration Manager 集成拓扑的 MBAM 2.5 报告
description: 查看 Configuration Manager 集成拓扑的 MBAM 2.5 报告
author: dansimp
ms.assetid: 60d11b2f-3a76-4023-8da4-f89e9f35b790
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3384fee62d302ac47775fe106265456ef119ab47
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803489"
---
# <span data-ttu-id="89edd-103">查看 Configuration Manager 集成拓扑的 MBAM 2.5 报告</span><span class="sxs-lookup"><span data-stu-id="89edd-103">Viewing MBAM 2.5 Reports for the Configuration Manager Integration Topology</span></span>


<span data-ttu-id="89edd-104">本主题介绍使用 Configuration Manager 集成拓扑配置 Microsoft BitLocker 管理和监视（MBAM）时可用的报告。</span><span class="sxs-lookup"><span data-stu-id="89edd-104">This topic describes the reports that are available when you configure Microsoft BitLocker Administration and Monitoring (MBAM) with the Configuration Manager Integration topology.</span></span> <span data-ttu-id="89edd-105">这些报表显示企业和 MBAM 管理的单个计算机和设备的 BitLocker 合规性。</span><span class="sxs-lookup"><span data-stu-id="89edd-105">The reports show BitLocker compliance for the enterprise and for individual computers and devices that MBAM manages.</span></span> <span data-ttu-id="89edd-106">报表提供表格信息和图表，并且它们具有可用于从不同视角查看数据的筛选器。</span><span class="sxs-lookup"><span data-stu-id="89edd-106">The reports provide tabular information and charts, and they have filters that let you view data from different perspectives.</span></span>

<span data-ttu-id="89edd-107">在 Configuration Manager 集成拓扑中，你可以从 Configuration Manager 查看报告，而不是从管理和监视网站查看报告，除了**恢复审核报告**外，你还可以从 "管理和监控" 网站继续查看。</span><span class="sxs-lookup"><span data-stu-id="89edd-107">In the Configuration Manager Integration topology, you view reports from Configuration Manager rather than from the Administration and Monitoring Website, with the exception of the **Recovery Audit Report**, which you continue to view from the Administration and Monitoring Website.</span></span>

<span data-ttu-id="89edd-108">有关独立拓扑的 MBAM 报表的信息，请参阅[查看独立拓扑的 MBAM 2.5 报表](viewing-mbam-25-reports-for-the-stand-alone-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="89edd-108">For information about MBAM reports for the Stand-alone topology, see [Viewing MBAM 2.5 Reports for the Stand-alone Topology](viewing-mbam-25-reports-for-the-stand-alone-topology.md).</span></span>

## <span data-ttu-id="89edd-109">在配置管理器中访问报表</span><span class="sxs-lookup"><span data-stu-id="89edd-109">Accessing reports in Configuration Manager</span></span>


<span data-ttu-id="89edd-110">要访问配置管理器中的 "报表" 功能，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="89edd-110">To access the Reports feature in Configuration Manager:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="89edd-111">版本的 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="89edd-111">Version of Configuration Manager</span></span></th>
<th align="left"><span data-ttu-id="89edd-112">如何查看报表</span><span class="sxs-lookup"><span data-stu-id="89edd-112">How to view the reports</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="89edd-113">SystemCenter2012 ConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="89edd-113">SystemCenter2012 ConfigurationManager</span></span></p></td>
<td align="left"><ol>
<li><p><span data-ttu-id="89edd-114">在左窗格中，选择 " <strong> 监视" </strong> 工作区。</span><span class="sxs-lookup"><span data-stu-id="89edd-114">In the left pane, select the <strong>Monitoring</strong> workspace.</span></span></p></li>
<li><p><span data-ttu-id="89edd-115">在树中，展开 " <strong> 概述 </strong> &gt; <strong> 报告 </strong> &gt; <strong> 报告 </strong> &gt; <strong> MBAM" </strong> 。</span><span class="sxs-lookup"><span data-stu-id="89edd-115">In the tree, expand <strong>Overview</strong> &gt; <strong>Reporting</strong> &gt; <strong>Reports</strong> &gt; <strong>MBAM</strong>.</span></span></p></li>
<li><p><span data-ttu-id="89edd-116">选择表示要查看报表的语言的文件夹，然后从右窗格中选择报表。</span><span class="sxs-lookup"><span data-stu-id="89edd-116">Select the folder that represents the language in which you want to view reports, and then select the report from the right pane.</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="89edd-117">配置管理器 2007</span><span class="sxs-lookup"><span data-stu-id="89edd-117">Configuration Manager 2007</span></span></p></td>
<td align="left"><ol>
<li><p><span data-ttu-id="89edd-118">在左窗格中，展开 " <strong> 计算机管理报告 </strong> &gt; <strong> </strong> &gt; <strong> 服务 </strong> &gt; <strong> &lt; 服务器名称 &gt; </strong> &gt; <strong> 报告文件夹 </strong> &gt; <strong> MBAM" </strong> 。</span><span class="sxs-lookup"><span data-stu-id="89edd-118">In the left pane, expand <strong>Computer Management</strong> &gt; <strong>Reporting</strong> &gt; <strong>Reporting Services</strong> &gt; <strong>&lt;server name&gt;</strong> &gt; <strong>Report folders</strong> &gt; <strong>MBAM</strong>.</span></span></p></li>
<li><p><span data-ttu-id="89edd-119">选择表示要查看报表的语言的文件夹，然后从右窗格中选择报表。</span><span class="sxs-lookup"><span data-stu-id="89edd-119">Select the folder that represents the language in which you want to view reports, and then select the report from the right pane.</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="89edd-120">配置管理器中的报表说明</span><span class="sxs-lookup"><span data-stu-id="89edd-120">Description of reports in Configuration Manager</span></span>


<span data-ttu-id="89edd-121">Configuration Manager 集成拓扑和独立拓扑的报表有一些细微差别。</span><span class="sxs-lookup"><span data-stu-id="89edd-121">There are a few minor differences in the reports for the Configuration Manager Integration topology and the Stand-alone topology.</span></span> <span data-ttu-id="89edd-122">以下部分介绍了 Configuration Manager 集成拓扑的 MBAM 报告中的数据：</span><span class="sxs-lookup"><span data-stu-id="89edd-122">The following sections describe the data in the MBAM reports for the Configuration Manager Integration topology:</span></span>

-   [<span data-ttu-id="89edd-123">BitLocker 企业合规性仪表板</span><span class="sxs-lookup"><span data-stu-id="89edd-123">BitLocker Enterprise Compliance Dashboard</span></span>](#bkmk-dashboard)

-   [<span data-ttu-id="89edd-124">BitLocker 企业合规性详细信息</span><span class="sxs-lookup"><span data-stu-id="89edd-124">BitLocker Enterprise Compliance Details</span></span>](#bkmk-compliancedetails)

-   [<span data-ttu-id="89edd-125">BitLocker 企业合规性摘要</span><span class="sxs-lookup"><span data-stu-id="89edd-125">BitLocker Enterprise Compliance Summary</span></span>](#bkmk-compliancesummary)

-   [<span data-ttu-id="89edd-126">BitLocker 计算机合规性报告</span><span class="sxs-lookup"><span data-stu-id="89edd-126">BitLocker Computer Compliance Report</span></span>](#bkmk-compliancereport)

### <a href="" id="bkmk-dashboard"></a><span data-ttu-id="89edd-127">BitLocker 企业合规性仪表板</span><span class="sxs-lookup"><span data-stu-id="89edd-127">BitLocker Enterprise Compliance Dashboard</span></span>

<span data-ttu-id="89edd-128">BitLocker 企业合规性仪表板提供以下图形，其中显示了整个企业的 BitLocker 合规性状态：</span><span class="sxs-lookup"><span data-stu-id="89edd-128">The BitLocker Enterprise Compliance Dashboard provides the following graphs, which show BitLocker compliance status across the enterprise:</span></span>

-   <span data-ttu-id="89edd-129">合规性状态分发</span><span class="sxs-lookup"><span data-stu-id="89edd-129">Compliance Status Distribution</span></span>

-   <span data-ttu-id="89edd-130">不符合的错误分布</span><span class="sxs-lookup"><span data-stu-id="89edd-130">Non Compliant Errors Distribution</span></span>

-   <span data-ttu-id="89edd-131">按驱动器类型的合规性状态分发</span><span class="sxs-lookup"><span data-stu-id="89edd-131">Compliance Status Distribution by Drive Type</span></span>

**<span data-ttu-id="89edd-132">合规性状态分发</span><span class="sxs-lookup"><span data-stu-id="89edd-132">Compliance Status Distribution</span></span>**

<span data-ttu-id="89edd-133">此饼图显示企业内计算机的合规性状态。</span><span class="sxs-lookup"><span data-stu-id="89edd-133">This pie chart shows compliance status for computers within the enterprise.</span></span> <span data-ttu-id="89edd-134">它还显示计算机的百分比，与所选集合中的计算机总数相比较，这些计算机具有符合性状态。</span><span class="sxs-lookup"><span data-stu-id="89edd-134">It also shows the percentage of computers, compared to the total number of computers in the selected collection, that has that compliance status.</span></span> <span data-ttu-id="89edd-135">还将显示每个状态的实际计算机数。</span><span class="sxs-lookup"><span data-stu-id="89edd-135">The actual number of computers with each status is also shown.</span></span> <span data-ttu-id="89edd-136">饼图显示以下合规性状态：</span><span class="sxs-lookup"><span data-stu-id="89edd-136">The pie chart shows the following compliance statuses:</span></span>

-   <span data-ttu-id="89edd-137">性</span><span class="sxs-lookup"><span data-stu-id="89edd-137">Compliant</span></span>

-   <span data-ttu-id="89edd-138">不符合</span><span class="sxs-lookup"><span data-stu-id="89edd-138">Non Compliant</span></span>

-   <span data-ttu-id="89edd-139">用户豁免</span><span class="sxs-lookup"><span data-stu-id="89edd-139">User Exempt</span></span>

-   <span data-ttu-id="89edd-140">临时用户豁免</span><span class="sxs-lookup"><span data-stu-id="89edd-140">Temporary User Exempt</span></span>

-   <span data-ttu-id="89edd-141">未强制执行策略</span><span class="sxs-lookup"><span data-stu-id="89edd-141">Policy Not Enforced</span></span>

-   <span data-ttu-id="89edd-142">可知.</span><span class="sxs-lookup"><span data-stu-id="89edd-142">Unknown.</span></span> <span data-ttu-id="89edd-143">这些计算机报告了状态错误，或者它们是集合的一部分，但从未报告过合规性状态。</span><span class="sxs-lookup"><span data-stu-id="89edd-143">These computers reported a status error, or they are part of the collection, but have never reported their compliance status.</span></span> <span data-ttu-id="89edd-144">如果计算机与组织断开连接，则可能会出现合规性状态。</span><span class="sxs-lookup"><span data-stu-id="89edd-144">The lack of a compliance status could occur if the computer is disconnected from the organization.</span></span>

**<span data-ttu-id="89edd-145">不符合的错误分布</span><span class="sxs-lookup"><span data-stu-id="89edd-145">Non Compliant Errors Distribution</span></span>**

<span data-ttu-id="89edd-146">此饼图显示企业中与 BitLocker 驱动器加密策略不兼容的计算机类别，并显示每个类别中的计算机数。</span><span class="sxs-lookup"><span data-stu-id="89edd-146">This pie chart shows the categories of computers in the enterprise that are not compliant with the BitLocker Drive Encryption policy, and shows the number of computers in each category.</span></span> <span data-ttu-id="89edd-147">每个类别百分比均由集合中不兼容计算机的总数计算。</span><span class="sxs-lookup"><span data-stu-id="89edd-147">Each category percentage is calculated from the total number of non-compliant computers in the collection.</span></span>

-   <span data-ttu-id="89edd-148">用户延期的加密</span><span class="sxs-lookup"><span data-stu-id="89edd-148">User postponed encryption</span></span>

-   <span data-ttu-id="89edd-149">找不到兼容的 TPM</span><span class="sxs-lookup"><span data-stu-id="89edd-149">Unable to find compatible TPM</span></span>

-   <span data-ttu-id="89edd-150">系统分区不可用或足够大</span><span class="sxs-lookup"><span data-stu-id="89edd-150">System partition not available or large enough</span></span>

-   <span data-ttu-id="89edd-151">策略冲突</span><span class="sxs-lookup"><span data-stu-id="89edd-151">Policy conflict</span></span>

-   <span data-ttu-id="89edd-152">正在等待 TPM 自动预配</span><span class="sxs-lookup"><span data-stu-id="89edd-152">Waiting for TPM auto provisioning</span></span>

-   <span data-ttu-id="89edd-153">出现未知错误</span><span class="sxs-lookup"><span data-stu-id="89edd-153">An unknown error has occurred</span></span>

-   <span data-ttu-id="89edd-154">无信息。</span><span class="sxs-lookup"><span data-stu-id="89edd-154">No information.</span></span> <span data-ttu-id="89edd-155">这些计算机未安装 MBAM 客户端，或者安装了 MBAM 客户端但未激活（例如，服务不工作）。</span><span class="sxs-lookup"><span data-stu-id="89edd-155">These computers do not have the MBAM Client installed, or they have the MBAM Client installed but not activated (for example, the service is not working).</span></span>

**<span data-ttu-id="89edd-156">按驱动器类型的合规性状态分发</span><span class="sxs-lookup"><span data-stu-id="89edd-156">Compliance Status Distribution by Drive Type</span></span>**

<span data-ttu-id="89edd-157">此条形图按驱动器类型显示当前的 BitLocker 合规性状态。</span><span class="sxs-lookup"><span data-stu-id="89edd-157">This bar chart shows the current BitLocker compliance status by drive type.</span></span> <span data-ttu-id="89edd-158">状态**符合标准**且**不合规**。</span><span class="sxs-lookup"><span data-stu-id="89edd-158">The statuses are **Compliant** and **Non Compliant**.</span></span> <span data-ttu-id="89edd-159">显示固定数据驱动器和操作系统驱动器的栏。</span><span class="sxs-lookup"><span data-stu-id="89edd-159">Bars are shown for fixed data drives and operating system drives.</span></span> <span data-ttu-id="89edd-160">不包含固定数据驱动器的计算机将包含在**操作系统驱动器**栏中且仅显示一个值。</span><span class="sxs-lookup"><span data-stu-id="89edd-160">Computers that do not have a fixed data drive are included and show a value only in the **Operating System Drive** bar.</span></span> <span data-ttu-id="89edd-161">图表不包括已被授予 BitLocker 驱动器加密策略或 "无策略" 类别的豁免的用户。</span><span class="sxs-lookup"><span data-stu-id="89edd-161">The chart does not include users who have been granted an exemption from the BitLocker Drive Encryption policy or the No Policy category.</span></span>

### <a href="" id="bkmk-compliancedetails"></a><span data-ttu-id="89edd-162">BitLocker 企业合规性详细信息</span><span class="sxs-lookup"><span data-stu-id="89edd-162">BitLocker Enterprise Compliance Details</span></span>

<span data-ttu-id="89edd-163">此报表显示有关面向 BitLocker 使用的计算机集合的整个企业范围内的 BitLocker 合规性的信息。</span><span class="sxs-lookup"><span data-stu-id="89edd-163">This report shows information about the overall BitLocker compliance across your enterprise for the collection of computers that is targeted for BitLocker use.</span></span>

**<span data-ttu-id="89edd-164">BitLocker 企业合规性详细信息字段</span><span class="sxs-lookup"><span data-stu-id="89edd-164">BitLocker Enterprise Compliance Details Fields</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="89edd-165">列名称</span><span class="sxs-lookup"><span data-stu-id="89edd-165">Column Name</span></span></th>
<th align="left"><span data-ttu-id="89edd-166">描述</span><span class="sxs-lookup"><span data-stu-id="89edd-166">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="89edd-167">托管计算机</span><span class="sxs-lookup"><span data-stu-id="89edd-167">Managed Computers</span></span></p></td>
<td align="left"><p><span data-ttu-id="89edd-168">MBAM 管理的计算机数。</span><span class="sxs-lookup"><span data-stu-id="89edd-168">Number of computers that MBAM manages.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="89edd-169">符合百分比</span><span class="sxs-lookup"><span data-stu-id="89edd-169">% Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="89edd-170">企业中合规性计算机的百分比。</span><span class="sxs-lookup"><span data-stu-id="89edd-170">Percentage of compliant computers in the enterprise.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="89edd-171">不符合的%</span><span class="sxs-lookup"><span data-stu-id="89edd-171">% Non-Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="89edd-172">企业中不符合的计算机的百分比。</span><span class="sxs-lookup"><span data-stu-id="89edd-172">Percentage of non-compliant computers in the enterprise.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="89edd-173">% 的未知合规性</span><span class="sxs-lookup"><span data-stu-id="89edd-173">% Unknown Compliance</span></span></p></td>
<td align="left"><p><span data-ttu-id="89edd-174">符合性状态为未知的计算机的百分比。</span><span class="sxs-lookup"><span data-stu-id="89edd-174">Percentage of computers with a compliance state that is not known.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="89edd-175">% 豁免</span><span class="sxs-lookup"><span data-stu-id="89edd-175">% Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="89edd-176">免除 BitLocker 加密要求的计算机的百分比。</span><span class="sxs-lookup"><span data-stu-id="89edd-176">Percentage of computers exempt from the BitLocker encryption requirement.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="89edd-177">% 非豁免</span><span class="sxs-lookup"><span data-stu-id="89edd-177">% Non-Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="89edd-178">不受 BitLocker 加密要求免除的计算机的百分比。</span><span class="sxs-lookup"><span data-stu-id="89edd-178">Percentage of computers not exempt from the BitLocker encryption requirement.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="89edd-179">性</span><span class="sxs-lookup"><span data-stu-id="89edd-179">Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="89edd-180">企业中合规性计算机的百分比。</span><span class="sxs-lookup"><span data-stu-id="89edd-180">Percentage of compliant computers in the enterprise.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="89edd-181">不符合</span><span class="sxs-lookup"><span data-stu-id="89edd-181">Non-Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="89edd-182">企业中不符合的计算机的百分比。</span><span class="sxs-lookup"><span data-stu-id="89edd-182">Percentage of non-compliant computers in the enterprise.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="89edd-183">未知合规性</span><span class="sxs-lookup"><span data-stu-id="89edd-183">Unknown Compliance</span></span></p></td>
<td align="left"><p><span data-ttu-id="89edd-184">符合性状态为未知的计算机的百分比。</span><span class="sxs-lookup"><span data-stu-id="89edd-184">Percentage of computers with a compliance state that is not known.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="89edd-185">例外</span><span class="sxs-lookup"><span data-stu-id="89edd-185">Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="89edd-186">免除 BitLocker 加密要求的计算机的总数。</span><span class="sxs-lookup"><span data-stu-id="89edd-186">Total computers that are exempt from the BitLocker encryption requirement.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="89edd-187">非豁免</span><span class="sxs-lookup"><span data-stu-id="89edd-187">Non-Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="89edd-188">不免除 BitLocker 加密要求的计算机的总数。</span><span class="sxs-lookup"><span data-stu-id="89edd-188">Total computers that are not exempt from the BitLocker encryption requirement.</span></span></p></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="89edd-189">BitLocker 企业合规性详细信息状态</span><span class="sxs-lookup"><span data-stu-id="89edd-189">BitLocker Enterprise Compliance Details States</span></span>**

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="89edd-190">合规性状态</span><span class="sxs-lookup"><span data-stu-id="89edd-190">Compliance Status</span></span></th>
<th align="left"><span data-ttu-id="89edd-191">免除</span><span class="sxs-lookup"><span data-stu-id="89edd-191">Exemption</span></span></th>
<th align="left"><span data-ttu-id="89edd-192">描述</span><span class="sxs-lookup"><span data-stu-id="89edd-192">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="89edd-193">标准</span><span class="sxs-lookup"><span data-stu-id="89edd-193">Noncompliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="89edd-194">不豁免</span><span class="sxs-lookup"><span data-stu-id="89edd-194">Not exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="89edd-195">根据指定的策略，计算机不相容。</span><span class="sxs-lookup"><span data-stu-id="89edd-195">The computer is noncompliant, according to the specified policy.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="89edd-196">性</span><span class="sxs-lookup"><span data-stu-id="89edd-196">Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="89edd-197">不豁免</span><span class="sxs-lookup"><span data-stu-id="89edd-197">Not exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="89edd-198">计算机符合指定的策略。</span><span class="sxs-lookup"><span data-stu-id="89edd-198">The computer is compliant in accordance with the specified policy.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="bkmk-compliancesummary"></a><span data-ttu-id="89edd-199">BitLocker 企业合规性摘要</span><span class="sxs-lookup"><span data-stu-id="89edd-199">BitLocker Enterprise Compliance Summary</span></span>

<span data-ttu-id="89edd-200">使用此报告类型可显示整个企业中的所有 BitLocker 合规性的相关信息，并显示针对 BitLocker 使用的计算机集合中的各个计算机的合规性。</span><span class="sxs-lookup"><span data-stu-id="89edd-200">Use this report type to show information about the overall BitLocker compliance across your enterprise and to show the compliance for individual computers that are in the collection of computers that is targeted for BitLocker use.</span></span>

**<span data-ttu-id="89edd-201">BitLocker 企业合规性摘要字段</span><span class="sxs-lookup"><span data-stu-id="89edd-201">BitLocker Enterprise Compliance Summary Fields</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="89edd-202">列名称</span><span class="sxs-lookup"><span data-stu-id="89edd-202">Column Name</span></span></th>
<th align="left"><span data-ttu-id="89edd-203">描述</span><span class="sxs-lookup"><span data-stu-id="89edd-203">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="89edd-204">托管计算机</span><span class="sxs-lookup"><span data-stu-id="89edd-204">Managed Computers</span></span></p></td>
<td align="left"><p><span data-ttu-id="89edd-205">MBAM 管理的计算机数。</span><span class="sxs-lookup"><span data-stu-id="89edd-205">Number of computers that MBAM manages.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="89edd-206">符合百分比</span><span class="sxs-lookup"><span data-stu-id="89edd-206">% Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="89edd-207">企业中合规性计算机的百分比。</span><span class="sxs-lookup"><span data-stu-id="89edd-207">Percentage of compliant computers in the enterprise.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="89edd-208">不符合的%</span><span class="sxs-lookup"><span data-stu-id="89edd-208">% Non-Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="89edd-209">企业中不符合的计算机的百分比。</span><span class="sxs-lookup"><span data-stu-id="89edd-209">Percentage of non-compliant computers in the enterprise.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="89edd-210">% 的未知合规性</span><span class="sxs-lookup"><span data-stu-id="89edd-210">% Unknown Compliance</span></span></p></td>
<td align="left"><p><span data-ttu-id="89edd-211">符合性状态为未知的计算机的百分比。</span><span class="sxs-lookup"><span data-stu-id="89edd-211">Percentage of computers with a compliance state that is not known.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="89edd-212">% 豁免</span><span class="sxs-lookup"><span data-stu-id="89edd-212">% Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="89edd-213">免除 BitLocker 加密要求的计算机的百分比。</span><span class="sxs-lookup"><span data-stu-id="89edd-213">Percentage of computers exempt from the BitLocker encryption requirement.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="89edd-214">% 非豁免</span><span class="sxs-lookup"><span data-stu-id="89edd-214">% Non-Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="89edd-215">不受 BitLocker 加密要求免除的计算机的百分比。</span><span class="sxs-lookup"><span data-stu-id="89edd-215">Percentage of computers not exempt from the BitLocker encryption requirement.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="89edd-216">性</span><span class="sxs-lookup"><span data-stu-id="89edd-216">Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="89edd-217">企业中合规性计算机的百分比。</span><span class="sxs-lookup"><span data-stu-id="89edd-217">Percentage of compliant computers in the enterprise.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="89edd-218">不符合</span><span class="sxs-lookup"><span data-stu-id="89edd-218">Non-Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="89edd-219">企业中不符合的计算机的百分比。</span><span class="sxs-lookup"><span data-stu-id="89edd-219">Percentage of non-compliant computers in the enterprise.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="89edd-220">未知合规性</span><span class="sxs-lookup"><span data-stu-id="89edd-220">Unknown Compliance</span></span></p></td>
<td align="left"><p><span data-ttu-id="89edd-221">符合性状态为未知的计算机的百分比。</span><span class="sxs-lookup"><span data-stu-id="89edd-221">Percentage of computers with a compliance state that is not known.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="89edd-222">例外</span><span class="sxs-lookup"><span data-stu-id="89edd-222">Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="89edd-223">免除 BitLocker 加密要求的计算机的总数。</span><span class="sxs-lookup"><span data-stu-id="89edd-223">Total computers that are exempt from the BitLocker encryption requirement.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="89edd-224">非豁免</span><span class="sxs-lookup"><span data-stu-id="89edd-224">Non-Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="89edd-225">不免除 BitLocker 加密要求的计算机的总数。</span><span class="sxs-lookup"><span data-stu-id="89edd-225">Total computers that are not exempt from the BitLocker encryption requirement.</span></span></p></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="89edd-226">BitLocker 企业合规性摘要计算机详细信息</span><span class="sxs-lookup"><span data-stu-id="89edd-226">BitLocker Enterprise Compliance Summary Computer Details</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="89edd-227">列名称</span><span class="sxs-lookup"><span data-stu-id="89edd-227">Column Name</span></span></th>
<th align="left"><span data-ttu-id="89edd-228">描述</span><span class="sxs-lookup"><span data-stu-id="89edd-228">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="89edd-229">计算机名</span><span class="sxs-lookup"><span data-stu-id="89edd-229">Computer Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="89edd-230">由 MBAM 管理的用户指定的 DNS 计算机名。</span><span class="sxs-lookup"><span data-stu-id="89edd-230">User-specified DNS computer name that is being managed by MBAM.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="89edd-231">域名</span><span class="sxs-lookup"><span data-stu-id="89edd-231">Domain Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="89edd-232">客户端计算机所在的完全限定的域名，由 MBAM 管理。</span><span class="sxs-lookup"><span data-stu-id="89edd-232">Fully qualified domain name, where the client computer resides and is managed by MBAM.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="89edd-233">合规性状态</span><span class="sxs-lookup"><span data-stu-id="89edd-233">Compliance Status</span></span></p></td>
<td align="left"><p><span data-ttu-id="89edd-234">由 MBAM 管理的计算机的整体合规性状态。</span><span class="sxs-lookup"><span data-stu-id="89edd-234">Overall compliance status of the computer managed by MBAM.</span></span> <span data-ttu-id="89edd-235">有效状态符合和不相容。</span><span class="sxs-lookup"><span data-stu-id="89edd-235">Valid states are Compliant and Noncompliant.</span></span> <span data-ttu-id="89edd-236">请注意，每个驱动器的合规性状态（请参阅后面的表）可能指示不同的合规性状态。</span><span class="sxs-lookup"><span data-stu-id="89edd-236">Notice that the compliance status per drive (see the table that follows) may indicate different compliance states.</span></span> <span data-ttu-id="89edd-237">但是，此字段根据指定的策略表示符合性状态。</span><span class="sxs-lookup"><span data-stu-id="89edd-237">However, this field represents that compliance state, in accordance with the policy specified.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="89edd-238">免除</span><span class="sxs-lookup"><span data-stu-id="89edd-238">Exemption</span></span></p></td>
<td align="left"><p><span data-ttu-id="89edd-239">用于指示用户是否为 BitLocker 策略豁免或非豁免的状态。</span><span class="sxs-lookup"><span data-stu-id="89edd-239">Status that indicates whether the user is exempt or non-exempt from the BitLocker policy.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="89edd-240">设备用户</span><span class="sxs-lookup"><span data-stu-id="89edd-240">Device Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="89edd-241">设备的用户。</span><span class="sxs-lookup"><span data-stu-id="89edd-241">User of the device.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="89edd-242">合规性状态详细信息</span><span class="sxs-lookup"><span data-stu-id="89edd-242">Compliance Status Details</span></span></p></td>
<td align="left"><p><span data-ttu-id="89edd-243">根据指定的策略，有关计算机合规性状态的错误和状态消息。</span><span class="sxs-lookup"><span data-stu-id="89edd-243">Error and status messages about the compliance state of the computer in accordance with the policy specified.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="89edd-244">上次联系人</span><span class="sxs-lookup"><span data-stu-id="89edd-244">Last Contact</span></span></p></td>
<td align="left"><p><span data-ttu-id="89edd-245">计算机上次联系服务器以报告合规性状态的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="89edd-245">Date and time that the computer last contacted the server to report compliance status.</span></span> <span data-ttu-id="89edd-246">可通过组策略设置配置联系人频率。</span><span class="sxs-lookup"><span data-stu-id="89edd-246">The contact frequency is configurable through the Group Policy settings.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="bkmk-compliancereport"></a><span data-ttu-id="89edd-247">BitLocker 计算机合规性报告</span><span class="sxs-lookup"><span data-stu-id="89edd-247">BitLocker Computer Compliance Report</span></span>

<span data-ttu-id="89edd-248">使用此报告类型可收集特定于计算机的信息。</span><span class="sxs-lookup"><span data-stu-id="89edd-248">Use this report type to collect information that is specific to a computer.</span></span> <span data-ttu-id="89edd-249">BitLocker 计算机合规性报告提供有关计算机上的每个驱动器（操作系统和固定数据驱动器）的详细加密信息。</span><span class="sxs-lookup"><span data-stu-id="89edd-249">The BitLocker Computer Compliance Report provides detailed encryption information about each drive on a computer (operating system and fixed data drives).</span></span> <span data-ttu-id="89edd-250">它还提供了应用于计算机上每个驱动器类型的策略的指示。</span><span class="sxs-lookup"><span data-stu-id="89edd-250">It also provides an indication of the policy that is applied to each drive type on the computer.</span></span> <span data-ttu-id="89edd-251">若要查看每个驱动器的详细信息，请展开 "计算机名称" 条目。</span><span class="sxs-lookup"><span data-stu-id="89edd-251">To view the details of each drive, expand the Computer Name entry.</span></span>

<span data-ttu-id="89edd-252">**注意** 可移动数据卷加密状态不会显示在此报告中。</span><span class="sxs-lookup"><span data-stu-id="89edd-252">**Note** The Removable Data Volume encryption status is not shown in this report.</span></span>

 

**<span data-ttu-id="89edd-253">BitLocker 计算机合规性报告：计算机详细信息字段</span><span class="sxs-lookup"><span data-stu-id="89edd-253">BitLocker Computer Compliance Report: Computer Details Fields</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="89edd-254">列名称</span><span class="sxs-lookup"><span data-stu-id="89edd-254">Column Name</span></span></th>
<th align="left"><span data-ttu-id="89edd-255">描述</span><span class="sxs-lookup"><span data-stu-id="89edd-255">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="89edd-256">计算机名</span><span class="sxs-lookup"><span data-stu-id="89edd-256">Computer Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="89edd-257">由 MBAM 管理的用户指定的 DNS 计算机名。</span><span class="sxs-lookup"><span data-stu-id="89edd-257">User-specified DNS computer name that is being managed by MBAM.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="89edd-258">域名</span><span class="sxs-lookup"><span data-stu-id="89edd-258">Domain Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="89edd-259">客户端计算机所在的完全限定的域名，由 MBAM 管理。</span><span class="sxs-lookup"><span data-stu-id="89edd-259">Fully qualified domain name, where the client computer resides and is managed by MBAM.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="89edd-260">计算机类型</span><span class="sxs-lookup"><span data-stu-id="89edd-260">Computer Type</span></span></p></td>
<td align="left"><p><span data-ttu-id="89edd-261">计算机的类型。</span><span class="sxs-lookup"><span data-stu-id="89edd-261">Type of computer.</span></span> <span data-ttu-id="89edd-262">有效类型为非便携式和可移植。</span><span class="sxs-lookup"><span data-stu-id="89edd-262">Valid types are Non-Portable and Portable.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="89edd-263">操作系统</span><span class="sxs-lookup"><span data-stu-id="89edd-263">Operating System</span></span></p></td>
<td align="left"><p><span data-ttu-id="89edd-264">在 MBAM 托管客户端计算机上找到的操作系统类型。</span><span class="sxs-lookup"><span data-stu-id="89edd-264">Operating System type found on the MBAM managed client computer.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="89edd-265">整体合规性</span><span class="sxs-lookup"><span data-stu-id="89edd-265">Overall Compliance</span></span></p></td>
<td align="left"><p><span data-ttu-id="89edd-266">由 MBAM 管理的计算机的整体合规性状态。</span><span class="sxs-lookup"><span data-stu-id="89edd-266">Overall compliance status of the computer managed by MBAM.</span></span> <span data-ttu-id="89edd-267">有效状态符合和不相容。</span><span class="sxs-lookup"><span data-stu-id="89edd-267">Valid states are Compliant and Noncompliant.</span></span> <span data-ttu-id="89edd-268">请注意，每个驱动器的合规性状态（请参阅后面的表）可能指示不同的合规性状态。</span><span class="sxs-lookup"><span data-stu-id="89edd-268">Notice that the compliance status per drive (see the table that follows) may indicate different compliance states.</span></span> <span data-ttu-id="89edd-269">但是，此字段根据指定的策略表示符合性状态。</span><span class="sxs-lookup"><span data-stu-id="89edd-269">However, this field represents that compliance state in accordance with the policy specified.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="89edd-270">操作系统合规性</span><span class="sxs-lookup"><span data-stu-id="89edd-270">Operating System Compliance</span></span></p></td>
<td align="left"><p><span data-ttu-id="89edd-271">由 MBAM 托管的操作系统的合规性状态。</span><span class="sxs-lookup"><span data-stu-id="89edd-271">Compliance status of the operating system that is managed by MBAM.</span></span> <span data-ttu-id="89edd-272">有效状态符合和不相容。</span><span class="sxs-lookup"><span data-stu-id="89edd-272">Valid states are Compliant and Noncompliant.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="89edd-273">固定数据驱动器合规性</span><span class="sxs-lookup"><span data-stu-id="89edd-273">Fixed Data Drive Compliance</span></span></p></td>
<td align="left"><p><span data-ttu-id="89edd-274">由 MBAM 管理的固定数据驱动器的合规性状态。</span><span class="sxs-lookup"><span data-stu-id="89edd-274">Compliance status of the fixed data drive that is managed by MBAM.</span></span> <span data-ttu-id="89edd-275">有效状态符合和不相容。</span><span class="sxs-lookup"><span data-stu-id="89edd-275">Valid states are Compliant and Noncompliant.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="89edd-276">上次更新日期</span><span class="sxs-lookup"><span data-stu-id="89edd-276">Last Update Date</span></span></p></td>
<td align="left"><p><span data-ttu-id="89edd-277">计算机上次联系服务器以报告合规性状态的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="89edd-277">Date and time that the computer last contacted the server to report compliance status.</span></span> <span data-ttu-id="89edd-278">可通过组策略设置配置联系人频率。</span><span class="sxs-lookup"><span data-stu-id="89edd-278">The contact frequency is configurable through the Group Policy settings.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="89edd-279">免除</span><span class="sxs-lookup"><span data-stu-id="89edd-279">Exemption</span></span></p></td>
<td align="left"><p><span data-ttu-id="89edd-280">用于指示用户是否为 BitLocker 策略豁免或非豁免的状态。</span><span class="sxs-lookup"><span data-stu-id="89edd-280">Status that indicates whether the user is exempt or non-exempt from the BitLocker policy.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="89edd-281">已免除用户</span><span class="sxs-lookup"><span data-stu-id="89edd-281">Exempted User</span></span></p></td>
<td align="left"><p><span data-ttu-id="89edd-282">不受 BitLocker 策略阻止的用户。</span><span class="sxs-lookup"><span data-stu-id="89edd-282">User who is exempt from the BitLocker policy.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="89edd-283">豁免日期</span><span class="sxs-lookup"><span data-stu-id="89edd-283">Exemption Date</span></span></p></td>
<td align="left"><p><span data-ttu-id="89edd-284">已获豁免的日期。</span><span class="sxs-lookup"><span data-stu-id="89edd-284">Date on which the exemption was granted.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="89edd-285">合规性状态详细信息</span><span class="sxs-lookup"><span data-stu-id="89edd-285">Compliance Status Details</span></span></p></td>
<td align="left"><p><span data-ttu-id="89edd-286">根据指定的策略，有关计算机合规性状态的错误和状态消息。</span><span class="sxs-lookup"><span data-stu-id="89edd-286">Error and status messages about the compliance state of the computer in accordance with the policy specified.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="89edd-287">策略密码强度</span><span class="sxs-lookup"><span data-stu-id="89edd-287">Policy Cipher Strength</span></span></p></td>
<td align="left"><p><span data-ttu-id="89edd-288">MBAM 策略规范期间管理员选择的密码长度（例如，使用扩散器的128位）。</span><span class="sxs-lookup"><span data-stu-id="89edd-288">Cipher strength selected by the Administrator during the MBAM policy specification (for example, 128-bit with diffuser).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="89edd-289">策略：操作系统驱动器</span><span class="sxs-lookup"><span data-stu-id="89edd-289">Policy: Operating System Drive</span></span></p></td>
<td align="left"><p><span data-ttu-id="89edd-290">指示操作系统是否需要加密以及相应的保护器类型。</span><span class="sxs-lookup"><span data-stu-id="89edd-290">Indicates if encryption is required for the operating system and the appropriate protector type.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="89edd-291">策略：固定数据驱动器</span><span class="sxs-lookup"><span data-stu-id="89edd-291">Policy: Fixed Data Drive</span></span></p></td>
<td align="left"><p><span data-ttu-id="89edd-292">指示固定数据驱动器是否需要加密。</span><span class="sxs-lookup"><span data-stu-id="89edd-292">Indicates if encryption is required for the fixed data drive.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="89edd-293">制造商</span><span class="sxs-lookup"><span data-stu-id="89edd-293">Manufacturer</span></span></p></td>
<td align="left"><p><span data-ttu-id="89edd-294">计算机 BIOS 中显示的计算机制造商名称。</span><span class="sxs-lookup"><span data-stu-id="89edd-294">Computer manufacturer name as it appears in the computer BIOS.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="89edd-295">型号</span><span class="sxs-lookup"><span data-stu-id="89edd-295">Model</span></span></p></td>
<td align="left"><p><span data-ttu-id="89edd-296">计算机 BIOS 中显示的计算机制造商型号名称。</span><span class="sxs-lookup"><span data-stu-id="89edd-296">Computer manufacturer model name as it appears in the computer BIOS.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="89edd-297">设备用户</span><span class="sxs-lookup"><span data-stu-id="89edd-297">Device Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="89edd-298">由 MBAM 管理的计算机上的已知用户。</span><span class="sxs-lookup"><span data-stu-id="89edd-298">Known users on the computer that is being managed by MBAM.</span></span></p></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="89edd-299">BitLocker 计算机合规性报告：计算机卷字段</span><span class="sxs-lookup"><span data-stu-id="89edd-299">BitLocker Computer Compliance Report: Computer Volume Fields</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="89edd-300">列名称</span><span class="sxs-lookup"><span data-stu-id="89edd-300">Column Name</span></span></th>
<th align="left"><span data-ttu-id="89edd-301">描述</span><span class="sxs-lookup"><span data-stu-id="89edd-301">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="89edd-302">驱动器号</span><span class="sxs-lookup"><span data-stu-id="89edd-302">Drive Letter</span></span></p></td>
<td align="left"><p><span data-ttu-id="89edd-303">用户分配给特定驱动器的计算机驱动器号。</span><span class="sxs-lookup"><span data-stu-id="89edd-303">Computer drive letter that was assigned to the particular drive by the user.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="89edd-304">驱动器类型</span><span class="sxs-lookup"><span data-stu-id="89edd-304">Drive Type</span></span></p></td>
<td align="left"><p><span data-ttu-id="89edd-305">驱动器的类型。</span><span class="sxs-lookup"><span data-stu-id="89edd-305">Type of drive.</span></span> <span data-ttu-id="89edd-306">有效值为操作系统驱动器和固定数据驱动器。</span><span class="sxs-lookup"><span data-stu-id="89edd-306">Valid values are Operating System Drive and Fixed Data Drive.</span></span> <span data-ttu-id="89edd-307">这些驱动器是物理驱动器，而不是逻辑卷。</span><span class="sxs-lookup"><span data-stu-id="89edd-307">These are physical drives rather than logical volumes.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="89edd-308">密码强度</span><span class="sxs-lookup"><span data-stu-id="89edd-308">Cipher Strength</span></span></p></td>
<td align="left"><p><span data-ttu-id="89edd-309">MBAM 策略规范期间管理员选择的密码长度。</span><span class="sxs-lookup"><span data-stu-id="89edd-309">Cipher strength selected by the Administrator during MBAM policy specification.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="89edd-310">保护器类型</span><span class="sxs-lookup"><span data-stu-id="89edd-310">Protector Types</span></span></p></td>
<td align="left"><p><span data-ttu-id="89edd-311">通过用于加密操作系统或固定数据驱动器的策略选择的保护器类型。</span><span class="sxs-lookup"><span data-stu-id="89edd-311">Type of protector selected through the policy used to encrypt an operating system or fixed data drive.</span></span> <span data-ttu-id="89edd-312">操作系统的有效保护程序类型为 TPM 或 TPM + PIN。</span><span class="sxs-lookup"><span data-stu-id="89edd-312">The valid protector types for an operating system are TPM or TPM+PIN.</span></span> <span data-ttu-id="89edd-313">固定数据驱动器的有效保护器类型是密码。</span><span class="sxs-lookup"><span data-stu-id="89edd-313">The valid protector type for a fixed data drive is a password.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="89edd-314">保护程序状态</span><span class="sxs-lookup"><span data-stu-id="89edd-314">Protector State</span></span></p></td>
<td align="left"><p><span data-ttu-id="89edd-315">指示由 MBAM 托管的计算机已启用在策略中指定的保护者类型。</span><span class="sxs-lookup"><span data-stu-id="89edd-315">Indicates that the computer being managed by MBAM has enabled the protector type specified in the policy.</span></span> <span data-ttu-id="89edd-316">有效状态为 "开" 或 "关"。</span><span class="sxs-lookup"><span data-stu-id="89edd-316">The valid states are ON or OFF.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="89edd-317">加密状态</span><span class="sxs-lookup"><span data-stu-id="89edd-317">Encryption State</span></span></p></td>
<td align="left"><p><span data-ttu-id="89edd-318">驱动器的加密状态。</span><span class="sxs-lookup"><span data-stu-id="89edd-318">Encryption state of the drive.</span></span> <span data-ttu-id="89edd-319">有效状态为加密、未加密和加密。</span><span class="sxs-lookup"><span data-stu-id="89edd-319">Valid states are Encrypted, Not Encrypted, and Encrypting.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="89edd-320">相关主题</span><span class="sxs-lookup"><span data-stu-id="89edd-320">Related topics</span></span>


[<span data-ttu-id="89edd-321">监视和报告 BitLocker 与 MBAM 2.5 的相容性</span><span class="sxs-lookup"><span data-stu-id="89edd-321">Monitoring and Reporting BitLocker Compliance with MBAM 2.5</span></span>](monitoring-and-reporting-bitlocker-compliance-with-mbam-25.md)

 

## <span data-ttu-id="89edd-322">已获得 MBAM 的建议？</span><span class="sxs-lookup"><span data-stu-id="89edd-322">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="89edd-323">在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="89edd-323">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="89edd-324">对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="89edd-324">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





