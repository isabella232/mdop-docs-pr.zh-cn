---
title: 了解 Configuration Manager 中的 MBAM 报告
description: 了解 Configuration Manager 中的 MBAM 报告
author: dansimp
ms.assetid: b2582190-c9de-4e64-bd5a-f31ac1916f53
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 995d628cafd03c8bdd209e467c9d22169b7e03c3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803445"
---
# <span data-ttu-id="4fa53-103">了解 Configuration Manager 中的 MBAM 报告</span><span class="sxs-lookup"><span data-stu-id="4fa53-103">Understanding MBAM Reports in Configuration Manager</span></span>


<span data-ttu-id="4fa53-104">当 Microsoft BitLocker 管理和监视（MBAM）与 Configuration Manager 集成拓扑一起安装时，硬件合规性和报告功能将被移动到 Configuration Manager 基础结构中，而不是 MBAM。</span><span class="sxs-lookup"><span data-stu-id="4fa53-104">When Microsoft BitLocker Administration and Monitoring (MBAM) is installed with the Configuration Manager Integrated topology, the hardware compliance and reporting features are moved into the Configuration Manager infrastructure and out of MBAM.</span></span> <span data-ttu-id="4fa53-105">使用 Configuration Manager 拓扑时，从 Configuration Manager （而不是从 MBAM）运行报表，但不是从 "恢复审核报告" （使用 "管理和监视" 网站继续访问）除外。</span><span class="sxs-lookup"><span data-stu-id="4fa53-105">When you use the Configuration Manager topology, you run reports from Configuration Manager rather than from MBAM, except for the Recovery Audit Report, which you continue to access by using the Administration and Monitoring Website.</span></span>

<span data-ttu-id="4fa53-106">Configuration Manager 集成拓扑的报告显示企业和 MBAM 管理的单个计算机和设备的 BitLocker 合规性。</span><span class="sxs-lookup"><span data-stu-id="4fa53-106">The reports for the Configuration Manager Integrated topology show BitLocker compliance for the enterprise and for individual computers and devices that MBAM manages.</span></span> <span data-ttu-id="4fa53-107">这些报表提供表格信息和图表，使你可以筛选报表以查看来自不同视角的数据。</span><span class="sxs-lookup"><span data-stu-id="4fa53-107">The reports provide both tabular information and charts, and enable you to filter reports to view data from different perspectives.</span></span>

<span data-ttu-id="4fa53-108">本主题中的信息介绍了您从配置管理器中运行的 MBAM 报表。</span><span class="sxs-lookup"><span data-stu-id="4fa53-108">The information in this topic describes the MBAM reports that you run from Configuration Manager.</span></span> <span data-ttu-id="4fa53-109">有关独立拓扑的 MBAM 报表的信息，请参阅[了解 MBAM 报表](understanding-mbam-reports-mbam-2.md)。</span><span class="sxs-lookup"><span data-stu-id="4fa53-109">For information about MBAM reports for the Stand-alone topology, see [Understanding MBAM Reports](understanding-mbam-reports-mbam-2.md).</span></span>

## <span data-ttu-id="4fa53-110">在配置管理器中访问报表</span><span class="sxs-lookup"><span data-stu-id="4fa53-110">Accessing Reports in Configuration Manager</span></span>


<span data-ttu-id="4fa53-111">若要访问配置管理器中的报表功能，请打开**Configuration manager 控制台**。</span><span class="sxs-lookup"><span data-stu-id="4fa53-111">To access the Reports feature in Configuration Manager, open the **Configuration Manager console**.</span></span> <span data-ttu-id="4fa53-112">要显示可用报表的列表，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="4fa53-112">To display the list of available reports:</span></span>

-   <span data-ttu-id="4fa53-113">在 Configuration Manager 2007 中，展开 "**计算机管理**" 节点，然后展开 "**报告**" 节点。</span><span class="sxs-lookup"><span data-stu-id="4fa53-113">In Configuration Manager 2007, expand the **Computer Management** node, and then expand the **Reporting** node.</span></span>

-   <span data-ttu-id="4fa53-114">在 SystemCenter2012 ConfigurationManager 中，在 "监视" 工作区的 "**概述**" 下，展开 "**报表**" 节点，然后单击 "**报表**"。</span><span class="sxs-lookup"><span data-stu-id="4fa53-114">In SystemCenter2012 ConfigurationManager, in the Monitoring workspace under **Overview**, expand the **Reporting** node and then click **Reports**.</span></span>

### <span data-ttu-id="4fa53-115">BitLocker 企业合规性仪表板</span><span class="sxs-lookup"><span data-stu-id="4fa53-115">BitLocker Enterprise Compliance Dashboard</span></span>

<span data-ttu-id="4fa53-116">BitLocker 企业合规性仪表板提供以下图形，其中显示了整个企业的 BitLocker 合规性状态：</span><span class="sxs-lookup"><span data-stu-id="4fa53-116">The BitLocker Enterprise Compliance Dashboard provides the following graphs, which show BitLocker compliance status across the enterprise:</span></span>

-   <span data-ttu-id="4fa53-117">合规性状态分发</span><span class="sxs-lookup"><span data-stu-id="4fa53-117">Compliance Status Distribution</span></span>

-   <span data-ttu-id="4fa53-118">不符合的错误分布</span><span class="sxs-lookup"><span data-stu-id="4fa53-118">Non Compliant Errors Distribution</span></span>

-   <span data-ttu-id="4fa53-119">按驱动器类型的合规性状态分发</span><span class="sxs-lookup"><span data-stu-id="4fa53-119">Compliance Status Distribution by Drive Type</span></span>

**<span data-ttu-id="4fa53-120">合规性状态分发</span><span class="sxs-lookup"><span data-stu-id="4fa53-120">Compliance Status Distribution</span></span>**

<span data-ttu-id="4fa53-121">此饼图显示企业内的计算机合规性状态，并显示计算机的百分比，与所选集合中的计算机总数相比较，其符合性状态。</span><span class="sxs-lookup"><span data-stu-id="4fa53-121">This pie chart shows computer compliance statuses within the enterprise, and shows the percentage of computers, compared to the total number of computers in the selected collection, that have that compliance status.</span></span> <span data-ttu-id="4fa53-122">还将显示每个状态的实际计算机数。</span><span class="sxs-lookup"><span data-stu-id="4fa53-122">The actual number of computers with each status is also shown.</span></span> <span data-ttu-id="4fa53-123">饼图显示以下合规性状态：</span><span class="sxs-lookup"><span data-stu-id="4fa53-123">The pie chart shows the following compliance statuses:</span></span>

-   <span data-ttu-id="4fa53-124">性</span><span class="sxs-lookup"><span data-stu-id="4fa53-124">Compliant</span></span>

-   <span data-ttu-id="4fa53-125">不符合</span><span class="sxs-lookup"><span data-stu-id="4fa53-125">Non Compliant</span></span>

-   <span data-ttu-id="4fa53-126">用户豁免</span><span class="sxs-lookup"><span data-stu-id="4fa53-126">User Exempt</span></span>

-   <span data-ttu-id="4fa53-127">临时用户豁免</span><span class="sxs-lookup"><span data-stu-id="4fa53-127">Temporary User Exempt</span></span>

-   <span data-ttu-id="4fa53-128">未强制执行策略</span><span class="sxs-lookup"><span data-stu-id="4fa53-128">Policy Not Enforced</span></span>

-   <span data-ttu-id="4fa53-129">未知-状态被报告为错误的计算机，或属于集合一部分但从未报告其合规性状态的设备（例如，在与组织断开连接时）</span><span class="sxs-lookup"><span data-stu-id="4fa53-129">Unknown -computers whose status was reported as an error, or devices that are part of the collection but have never reported their compliance status, for example, if they are disconnected from the organization</span></span>

**<span data-ttu-id="4fa53-130">不符合的错误分布</span><span class="sxs-lookup"><span data-stu-id="4fa53-130">Non Compliant Errors Distribution</span></span>**

<span data-ttu-id="4fa53-131">此饼图显示企业中与 BitLocker 驱动器加密策略不兼容的计算机类别，并显示每个类别中的计算机数。</span><span class="sxs-lookup"><span data-stu-id="4fa53-131">This pie chart shows the categories of computers in the enterprise that are not compliant with the BitLocker drive encryption policy, and shows the number of computers in each category.</span></span> <span data-ttu-id="4fa53-132">每个类别百分比均由集合中不兼容计算机的总数计算。</span><span class="sxs-lookup"><span data-stu-id="4fa53-132">Each category percentage is calculated from the total number of non-compliant computers in the collection.</span></span>

-   <span data-ttu-id="4fa53-133">用户延期的加密</span><span class="sxs-lookup"><span data-stu-id="4fa53-133">User postponed encryption</span></span>

-   <span data-ttu-id="4fa53-134">找不到兼容的 TPM</span><span class="sxs-lookup"><span data-stu-id="4fa53-134">Unable to find compatible TPM</span></span>

-   <span data-ttu-id="4fa53-135">系统分区不可用或足够大</span><span class="sxs-lookup"><span data-stu-id="4fa53-135">System Partition not available or large enough</span></span>

-   <span data-ttu-id="4fa53-136">策略冲突</span><span class="sxs-lookup"><span data-stu-id="4fa53-136">Policy conflict</span></span>

-   <span data-ttu-id="4fa53-137">正在等待 TPM 自动预配</span><span class="sxs-lookup"><span data-stu-id="4fa53-137">Waiting for TPM auto provisioning</span></span>

-   <span data-ttu-id="4fa53-138">出现未知错误</span><span class="sxs-lookup"><span data-stu-id="4fa53-138">An unknown error has occurred</span></span>

-   <span data-ttu-id="4fa53-139">无信息-未安装 MBAM 客户端的计算机，或者安装了 MBAM 客户端但未激活的计算机（例如，服务无法正常工作）</span><span class="sxs-lookup"><span data-stu-id="4fa53-139">No information – computers that do not have the MBAM Client installed, or that have the MBAM Client installed but not activated, for example, the service is not working</span></span>

**<span data-ttu-id="4fa53-140">按驱动器类型的合规性状态分发</span><span class="sxs-lookup"><span data-stu-id="4fa53-140">Compliance Status Distribution by Drive Type</span></span>**

<span data-ttu-id="4fa53-141">此条形图按驱动器类型显示当前的 BitLocker 合规性状态。</span><span class="sxs-lookup"><span data-stu-id="4fa53-141">This bar chart shows the current BitLocker compliance status by drive type.</span></span> <span data-ttu-id="4fa53-142">状态为 "合规" 和 "不合规"。</span><span class="sxs-lookup"><span data-stu-id="4fa53-142">The statuses are “Compliant” and “Non Compliant.”</span></span> <span data-ttu-id="4fa53-143">显示固定数据驱动器和操作系统驱动器的栏。</span><span class="sxs-lookup"><span data-stu-id="4fa53-143">Bars are shown for fixed data drives and operating system drives.</span></span> <span data-ttu-id="4fa53-144">不包含固定数据驱动器的计算机将包含在操作系统驱动器栏中且仅显示一个值。</span><span class="sxs-lookup"><span data-stu-id="4fa53-144">Computers that do not have a fixed data drive are included and show a value only in the Operating System Drive bar.</span></span> <span data-ttu-id="4fa53-145">图表不包括已通过 BitLocker 驱动器加密策略或 "无策略" 类别授予豁免的用户。</span><span class="sxs-lookup"><span data-stu-id="4fa53-145">The chart does not include users who have been granted an exemption from the BitLocker drive encryption policy or the “No Policy” category.</span></span>

### <span data-ttu-id="4fa53-146">BitLocker 企业合规性详细信息报告</span><span class="sxs-lookup"><span data-stu-id="4fa53-146">BitLocker Enterprise Compliance Details Report</span></span>

<span data-ttu-id="4fa53-147">此报表显示有关面向 BitLocker 使用的计算机集合的整个企业范围内的 BitLocker 合规性的信息。</span><span class="sxs-lookup"><span data-stu-id="4fa53-147">This report shows information about the overall BitLocker compliance across your enterprise for the collection of computers that is targeted for BitLocker use.</span></span>

**<span data-ttu-id="4fa53-148">BitLocker 企业合规性详细信息报表字段</span><span class="sxs-lookup"><span data-stu-id="4fa53-148">BitLocker Enterprise Compliance Details Report Fields</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4fa53-149">列名称</span><span class="sxs-lookup"><span data-stu-id="4fa53-149">Column Name</span></span></th>
<th align="left"><span data-ttu-id="4fa53-150">描述</span><span class="sxs-lookup"><span data-stu-id="4fa53-150">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4fa53-151">托管计算机</span><span class="sxs-lookup"><span data-stu-id="4fa53-151">Managed Computers</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fa53-152">MBAM 管理的计算机数。</span><span class="sxs-lookup"><span data-stu-id="4fa53-152">Number of computers that MBAM manages.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4fa53-153">符合百分比</span><span class="sxs-lookup"><span data-stu-id="4fa53-153">% Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fa53-154">企业中合规性计算机的百分比。</span><span class="sxs-lookup"><span data-stu-id="4fa53-154">Percentage of compliant computers in the enterprise.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4fa53-155">不符合的%</span><span class="sxs-lookup"><span data-stu-id="4fa53-155">% Non-Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fa53-156">企业中不符合的计算机的百分比。</span><span class="sxs-lookup"><span data-stu-id="4fa53-156">Percentage of non-compliant computers in the enterprise.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4fa53-157">% 的未知合规性</span><span class="sxs-lookup"><span data-stu-id="4fa53-157">% Unknown Compliance</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fa53-158">合规性状态未知的计算机的百分比。</span><span class="sxs-lookup"><span data-stu-id="4fa53-158">Percentage of computers whose compliance state is not known.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4fa53-159">% 豁免</span><span class="sxs-lookup"><span data-stu-id="4fa53-159">% Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fa53-160">免除 BitLocker 加密要求的计算机的百分比。</span><span class="sxs-lookup"><span data-stu-id="4fa53-160">Percentage of computers exempt from the BitLocker encryption requirement.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4fa53-161">% 非豁免</span><span class="sxs-lookup"><span data-stu-id="4fa53-161">% Non-Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fa53-162">免除 BitLocker 加密要求的计算机的百分比。</span><span class="sxs-lookup"><span data-stu-id="4fa53-162">Percentage of computers exempt from the BitLocker encryption requirement.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4fa53-163">性</span><span class="sxs-lookup"><span data-stu-id="4fa53-163">Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fa53-164">企业中合规性计算机的百分比。</span><span class="sxs-lookup"><span data-stu-id="4fa53-164">Percentage of compliant computers in the enterprise.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4fa53-165">不符合</span><span class="sxs-lookup"><span data-stu-id="4fa53-165">Non-Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fa53-166">企业中不符合的计算机的百分比。</span><span class="sxs-lookup"><span data-stu-id="4fa53-166">Percentage of non-compliant computers in the enterprise.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4fa53-167">未知合规性</span><span class="sxs-lookup"><span data-stu-id="4fa53-167">Unknown Compliance</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fa53-168">合规性状态未知的计算机的百分比。</span><span class="sxs-lookup"><span data-stu-id="4fa53-168">Percentage of computers whose compliance state is not known.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4fa53-169">例外</span><span class="sxs-lookup"><span data-stu-id="4fa53-169">Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fa53-170">免除 BitLocker 加密要求的计算机的总数。</span><span class="sxs-lookup"><span data-stu-id="4fa53-170">Total computers that are exempt from the BitLocker encryption requirement.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4fa53-171">非豁免</span><span class="sxs-lookup"><span data-stu-id="4fa53-171">Non-Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fa53-172">不免除 BitLocker 加密要求的计算机的总数。</span><span class="sxs-lookup"><span data-stu-id="4fa53-172">Total computers that are not exempt from the BitLocker encryption requirement.</span></span></p></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="4fa53-173">BitLocker 企业合规性详细信息报告合规性状态</span><span class="sxs-lookup"><span data-stu-id="4fa53-173">BitLocker Enterprise Compliance Details Report - Compliance States</span></span>**

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4fa53-174">合规性状态</span><span class="sxs-lookup"><span data-stu-id="4fa53-174">Compliance Status</span></span></th>
<th align="left"><span data-ttu-id="4fa53-175">免除</span><span class="sxs-lookup"><span data-stu-id="4fa53-175">Exemption</span></span></th>
<th align="left"><span data-ttu-id="4fa53-176">描述</span><span class="sxs-lookup"><span data-stu-id="4fa53-176">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4fa53-177">标准</span><span class="sxs-lookup"><span data-stu-id="4fa53-177">Noncompliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fa53-178">不豁免</span><span class="sxs-lookup"><span data-stu-id="4fa53-178">Not Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fa53-179">根据指定的策略，计算机不相容。</span><span class="sxs-lookup"><span data-stu-id="4fa53-179">The computer is noncompliant, according to the specified policy.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4fa53-180">性</span><span class="sxs-lookup"><span data-stu-id="4fa53-180">Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fa53-181">不豁免</span><span class="sxs-lookup"><span data-stu-id="4fa53-181">Not Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fa53-182">计算机符合指定的策略。</span><span class="sxs-lookup"><span data-stu-id="4fa53-182">The computer is compliant in accordance with the specified policy.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="4fa53-183">BitLocker 企业合规性摘要报告</span><span class="sxs-lookup"><span data-stu-id="4fa53-183">BitLocker Enterprise Compliance Summary Report</span></span>

<span data-ttu-id="4fa53-184">使用此报告类型可显示整个企业中的所有 BitLocker 合规性的相关信息，并显示针对 BitLocker 使用的计算机集合中的各个计算机的合规性。</span><span class="sxs-lookup"><span data-stu-id="4fa53-184">Use this report type to show information about the overall BitLocker compliance across your enterprise and to show the compliance for individual computers that are in the collection of computers that is targeted for BitLocker use.</span></span>

**<span data-ttu-id="4fa53-185">BitLocker 企业合规性摘要报告字段</span><span class="sxs-lookup"><span data-stu-id="4fa53-185">BitLocker Enterprise Compliance Summary Report Fields</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4fa53-186">列名称</span><span class="sxs-lookup"><span data-stu-id="4fa53-186">Column Name</span></span></th>
<th align="left"><span data-ttu-id="4fa53-187">描述</span><span class="sxs-lookup"><span data-stu-id="4fa53-187">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4fa53-188">托管计算机</span><span class="sxs-lookup"><span data-stu-id="4fa53-188">Managed Computers</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fa53-189">MBAM 管理的计算机数。</span><span class="sxs-lookup"><span data-stu-id="4fa53-189">Number of computers that MBAM manages.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4fa53-190">符合百分比</span><span class="sxs-lookup"><span data-stu-id="4fa53-190">% Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fa53-191">企业中合规性计算机的百分比。</span><span class="sxs-lookup"><span data-stu-id="4fa53-191">Percentage of compliant computers in the enterprise.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4fa53-192">不符合的%</span><span class="sxs-lookup"><span data-stu-id="4fa53-192">% Non-Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fa53-193">企业中不符合的计算机的百分比。</span><span class="sxs-lookup"><span data-stu-id="4fa53-193">Percentage of non-compliant computers in the enterprise.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4fa53-194">% 的未知合规性</span><span class="sxs-lookup"><span data-stu-id="4fa53-194">% Unknown Compliance</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fa53-195">合规性状态未知的计算机的百分比。</span><span class="sxs-lookup"><span data-stu-id="4fa53-195">Percentage of computers whose compliance state is not known.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4fa53-196">% 豁免</span><span class="sxs-lookup"><span data-stu-id="4fa53-196">% Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fa53-197">免除 BitLocker 加密要求的计算机的百分比。</span><span class="sxs-lookup"><span data-stu-id="4fa53-197">Percentage of computers exempt from the BitLocker encryption requirement.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4fa53-198">% 非豁免</span><span class="sxs-lookup"><span data-stu-id="4fa53-198">% Non-Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fa53-199">免除 BitLocker 加密要求的计算机的百分比。</span><span class="sxs-lookup"><span data-stu-id="4fa53-199">Percentage of computers exempt from the BitLocker encryption requirement.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4fa53-200">性</span><span class="sxs-lookup"><span data-stu-id="4fa53-200">Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fa53-201">企业中合规性计算机的百分比。</span><span class="sxs-lookup"><span data-stu-id="4fa53-201">Percentage of compliant computers in the enterprise.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4fa53-202">不符合</span><span class="sxs-lookup"><span data-stu-id="4fa53-202">Non-Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fa53-203">企业中不符合的计算机的百分比。</span><span class="sxs-lookup"><span data-stu-id="4fa53-203">Percentage of non-compliant computers in the enterprise.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4fa53-204">未知合规性</span><span class="sxs-lookup"><span data-stu-id="4fa53-204">Unknown Compliance</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fa53-205">合规性状态未知的计算机的百分比。</span><span class="sxs-lookup"><span data-stu-id="4fa53-205">Percentage of computers whose compliance state is not known.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4fa53-206">例外</span><span class="sxs-lookup"><span data-stu-id="4fa53-206">Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fa53-207">免除 BitLocker 加密要求的计算机的总数。</span><span class="sxs-lookup"><span data-stu-id="4fa53-207">Total computers that are exempt from the BitLocker encryption requirement.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4fa53-208">非豁免</span><span class="sxs-lookup"><span data-stu-id="4fa53-208">Non-Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fa53-209">不免除 BitLocker 加密要求的计算机的总数。</span><span class="sxs-lookup"><span data-stu-id="4fa53-209">Total computers that are not exempt from the BitLocker encryption requirement.</span></span></p></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="4fa53-210">BitLocker 企业合规性摘要报告-计算机详细信息</span><span class="sxs-lookup"><span data-stu-id="4fa53-210">BitLocker Enterprise Compliance Summary Report - Computer Details</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4fa53-211">列名称</span><span class="sxs-lookup"><span data-stu-id="4fa53-211">Column Name</span></span></th>
<th align="left"><span data-ttu-id="4fa53-212">描述</span><span class="sxs-lookup"><span data-stu-id="4fa53-212">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4fa53-213">计算机名</span><span class="sxs-lookup"><span data-stu-id="4fa53-213">Computer Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fa53-214">由 MBAM 管理的用户指定的 DNS 计算机名。</span><span class="sxs-lookup"><span data-stu-id="4fa53-214">User-specified DNS computer name that is being managed by MBAM.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4fa53-215">域名</span><span class="sxs-lookup"><span data-stu-id="4fa53-215">Domain Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fa53-216">客户端计算机所在的完全限定的域名，由 MBAM 管理。</span><span class="sxs-lookup"><span data-stu-id="4fa53-216">Fully qualified domain name, where the client computer resides and is managed by MBAM.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4fa53-217">合规性状态</span><span class="sxs-lookup"><span data-stu-id="4fa53-217">Compliance Status</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fa53-218">由 MBAM 管理的计算机的整体合规性状态。</span><span class="sxs-lookup"><span data-stu-id="4fa53-218">Overall Compliance Status of the computer managed by MBAM.</span></span> <span data-ttu-id="4fa53-219">有效状态符合和不相容。</span><span class="sxs-lookup"><span data-stu-id="4fa53-219">Valid states are Compliant and Noncompliant.</span></span> <span data-ttu-id="4fa53-220">请注意，每个驱动器的合规性状态（请参阅后面的表）可能指示不同的合规性状态。</span><span class="sxs-lookup"><span data-stu-id="4fa53-220">Notice that the compliance status per drive (see table that follows) may indicate different compliance states.</span></span> <span data-ttu-id="4fa53-221">但是，此字段根据指定的策略表示符合性状态。</span><span class="sxs-lookup"><span data-stu-id="4fa53-221">However, this field represents that compliance state, in accordance with the policy specified.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4fa53-222">免除</span><span class="sxs-lookup"><span data-stu-id="4fa53-222">Exemption</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fa53-223">用于指示用户是否为 BitLocker 策略豁免或非豁免的状态。</span><span class="sxs-lookup"><span data-stu-id="4fa53-223">Status that indicates whether the user is exempt or non-exemption from the BitLocker policy.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4fa53-224">设备用户</span><span class="sxs-lookup"><span data-stu-id="4fa53-224">Device Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fa53-225">设备的用户。</span><span class="sxs-lookup"><span data-stu-id="4fa53-225">User of the device.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4fa53-226">合规性状态详细信息</span><span class="sxs-lookup"><span data-stu-id="4fa53-226">Compliance Status Details</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fa53-227">根据指定策略，计算机符合性状态的错误和状态消息。</span><span class="sxs-lookup"><span data-stu-id="4fa53-227">Error and status messages of the compliance state of the computer in accordance to the policy specified.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4fa53-228">上次联系人</span><span class="sxs-lookup"><span data-stu-id="4fa53-228">Last Contact</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fa53-229">计算机上次联系服务器以报告合规性状态的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="4fa53-229">Date and time that the computer last contacted the server to report compliance status.</span></span> <span data-ttu-id="4fa53-230">可配置联系人频率（请参阅 MBAM 策略设置）。</span><span class="sxs-lookup"><span data-stu-id="4fa53-230">The contact frequency is configurable (see MBAM policy settings).</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="4fa53-231">BitLocker 计算机合规性报告</span><span class="sxs-lookup"><span data-stu-id="4fa53-231">BitLocker Computer Compliance Report</span></span>

<span data-ttu-id="4fa53-232">使用此报告类型可收集特定于计算机的信息。</span><span class="sxs-lookup"><span data-stu-id="4fa53-232">Use this report type to collect information that is specific to a computer.</span></span> <span data-ttu-id="4fa53-233">计算机合规性报告提供有关计算机上每个驱动器（操作系统和固定数据驱动器）的详细加密信息，以及应用于计算机上每个驱动器类型的策略的指示。</span><span class="sxs-lookup"><span data-stu-id="4fa53-233">The Computer Compliance Report provides detailed encryption information about each drive (Operating System and Fixed data drives) on a computer, and also an indication of the policy that is applied to each drive type on the computer.</span></span> <span data-ttu-id="4fa53-234">若要查看每个驱动器的详细信息，请展开 "计算机名称" 条目。</span><span class="sxs-lookup"><span data-stu-id="4fa53-234">To view the details of each drive, expand the Computer Name entry.</span></span>

<span data-ttu-id="4fa53-235">**注意** 可移动数据卷加密状态不会显示在报表中。</span><span class="sxs-lookup"><span data-stu-id="4fa53-235">**Note** Removable Data Volume encryption status is not shown in the report.</span></span>

 

**<span data-ttu-id="4fa53-236">BitLocker 计算机合规性报告-计算机详细信息字段</span><span class="sxs-lookup"><span data-stu-id="4fa53-236">BitLocker Computer Compliance Report – Computer Details Fields</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4fa53-237">列名称</span><span class="sxs-lookup"><span data-stu-id="4fa53-237">Column Name</span></span></th>
<th align="left"><span data-ttu-id="4fa53-238">描述</span><span class="sxs-lookup"><span data-stu-id="4fa53-238">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4fa53-239">计算机名</span><span class="sxs-lookup"><span data-stu-id="4fa53-239">Computer Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fa53-240">由 MBAM 管理的用户指定的 DNS 计算机名。</span><span class="sxs-lookup"><span data-stu-id="4fa53-240">User-specified DNS computer name that is being managed by MBAM.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4fa53-241">域名</span><span class="sxs-lookup"><span data-stu-id="4fa53-241">Domain Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fa53-242">客户端计算机所在的完全限定的域名，由 MBAM 管理。</span><span class="sxs-lookup"><span data-stu-id="4fa53-242">Fully qualified domain name, where the client computer resides and is managed by MBAM.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4fa53-243">计算机类型</span><span class="sxs-lookup"><span data-stu-id="4fa53-243">Computer Type</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fa53-244">计算机的类型。</span><span class="sxs-lookup"><span data-stu-id="4fa53-244">Type of computer.</span></span> <span data-ttu-id="4fa53-245">有效类型为非便携式和可移植。</span><span class="sxs-lookup"><span data-stu-id="4fa53-245">Valid types are non-Portable and Portable.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4fa53-246">操作系统</span><span class="sxs-lookup"><span data-stu-id="4fa53-246">Operating System</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fa53-247">在 MBAM 托管客户端计算机上找到的操作系统类型。</span><span class="sxs-lookup"><span data-stu-id="4fa53-247">Operating System type found on the MBAM managed client computer.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4fa53-248">整体合规性</span><span class="sxs-lookup"><span data-stu-id="4fa53-248">Overall Compliance</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fa53-249">由 MBAM 管理的计算机的整体合规性状态。</span><span class="sxs-lookup"><span data-stu-id="4fa53-249">Overall Compliance Status of the computer managed by MBAM.</span></span> <span data-ttu-id="4fa53-250">有效状态符合和不相容。</span><span class="sxs-lookup"><span data-stu-id="4fa53-250">Valid states are Compliant and Noncompliant.</span></span> <span data-ttu-id="4fa53-251">请注意，每个驱动器的合规性状态（请参阅后面的表）可能指示不同的合规性状态。</span><span class="sxs-lookup"><span data-stu-id="4fa53-251">Notice that the compliance status per drive (see table that follows) may indicate different compliance states.</span></span> <span data-ttu-id="4fa53-252">但是，此字段根据指定的策略表示符合性状态。</span><span class="sxs-lookup"><span data-stu-id="4fa53-252">However, this field represents that compliance state, in accordance with the policy specified.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4fa53-253">操作系统合规性</span><span class="sxs-lookup"><span data-stu-id="4fa53-253">Operating System Compliance</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fa53-254">由 MBAM 托管的操作系统的合规性状态。</span><span class="sxs-lookup"><span data-stu-id="4fa53-254">Compliance status of the operating system that is managed by MBAM.</span></span> <span data-ttu-id="4fa53-255">有效状态符合和不相容。</span><span class="sxs-lookup"><span data-stu-id="4fa53-255">Valid states are Compliant and Noncompliant.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4fa53-256">固定数据驱动器合规性</span><span class="sxs-lookup"><span data-stu-id="4fa53-256">Fixed Data Drive Compliance</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fa53-257">由 MBAM 管理的固定数据驱动器的合规性状态。</span><span class="sxs-lookup"><span data-stu-id="4fa53-257">Compliance status of the Fixed Data Drive that is managed by MBAM.</span></span> <span data-ttu-id="4fa53-258">有效状态符合和不相容。</span><span class="sxs-lookup"><span data-stu-id="4fa53-258">Valid states are Compliant and Noncompliant.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4fa53-259">上次更新日期</span><span class="sxs-lookup"><span data-stu-id="4fa53-259">Last Update Date</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fa53-260">计算机上次联系服务器以报告合规性状态的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="4fa53-260">Date and time that the computer last contacted the server to report compliance status.</span></span> <span data-ttu-id="4fa53-261">可配置联系人频率（请参阅 MBAM 策略设置）。</span><span class="sxs-lookup"><span data-stu-id="4fa53-261">The contact frequency is configurable (see MBAM policy settings).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4fa53-262">免除</span><span class="sxs-lookup"><span data-stu-id="4fa53-262">Exemption</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fa53-263">用于指示用户是否为 BitLocker 策略豁免或非豁免的状态。</span><span class="sxs-lookup"><span data-stu-id="4fa53-263">Status that indicates whether the user is exempt or non-exemption from the BitLocker policy.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4fa53-264">已免除用户</span><span class="sxs-lookup"><span data-stu-id="4fa53-264">Exempted User</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fa53-265">不受 BitLocker 策略阻止的用户。</span><span class="sxs-lookup"><span data-stu-id="4fa53-265">User who is exempt from the BitLocker policy.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4fa53-266">豁免日期</span><span class="sxs-lookup"><span data-stu-id="4fa53-266">Exemption Date</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fa53-267">已获豁免的日期。</span><span class="sxs-lookup"><span data-stu-id="4fa53-267">Date on which the exemption was granted.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4fa53-268">合规性状态详细信息</span><span class="sxs-lookup"><span data-stu-id="4fa53-268">Compliance Status Details</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fa53-269">根据指定策略，计算机符合性状态的错误和状态消息。</span><span class="sxs-lookup"><span data-stu-id="4fa53-269">Error and status messages of the compliance state of the computer in accordance to the policy specified.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4fa53-270">策略密码强度</span><span class="sxs-lookup"><span data-stu-id="4fa53-270">Policy Cipher Strength</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fa53-271">MBAM 策略规范期间管理员选择的密码长度。</span><span class="sxs-lookup"><span data-stu-id="4fa53-271">Cipher Strength selected by the Administrator during MBAM policy specification.</span></span> <span data-ttu-id="4fa53-272">（例如，有扩散器的128位）。</span><span class="sxs-lookup"><span data-stu-id="4fa53-272">(for example, 128-bit with Diffuser).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4fa53-273">策略：操作系统驱动器</span><span class="sxs-lookup"><span data-stu-id="4fa53-273">Policy: Operating System Drive</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fa53-274">指示 O/S 和相应的保护器类型是否需要加密。</span><span class="sxs-lookup"><span data-stu-id="4fa53-274">Indicates if encryption is required for the O/S and the appropriate protector type.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4fa53-275">策略：固定数据驱动器</span><span class="sxs-lookup"><span data-stu-id="4fa53-275">Policy:Fixed Data Drive</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fa53-276">指示是否需要对固定驱动器进行加密。</span><span class="sxs-lookup"><span data-stu-id="4fa53-276">Indicates if encryption is required for the Fixed Drive.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4fa53-277">制造商</span><span class="sxs-lookup"><span data-stu-id="4fa53-277">Manufacturer</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fa53-278">计算机 BIOS 中显示的计算机制造商名称。</span><span class="sxs-lookup"><span data-stu-id="4fa53-278">Computer manufacturer name as it appears in the computer BIOS.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4fa53-279">型号</span><span class="sxs-lookup"><span data-stu-id="4fa53-279">Model</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fa53-280">计算机 BIOS 中显示的计算机制造商型号名称。</span><span class="sxs-lookup"><span data-stu-id="4fa53-280">Computer manufacturer model name as it appears in the computer BIOS.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4fa53-281">设备用户</span><span class="sxs-lookup"><span data-stu-id="4fa53-281">Device Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fa53-282">由 MBAM 管理的计算机上的已知用户。</span><span class="sxs-lookup"><span data-stu-id="4fa53-282">Known users on the computer that is being managed by MBAM.</span></span></p></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="4fa53-283">BitLocker 计算机合规性报告-计算机卷字段</span><span class="sxs-lookup"><span data-stu-id="4fa53-283">BitLocker Computer Compliance Report – Computer Volume Fields</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4fa53-284">列名称</span><span class="sxs-lookup"><span data-stu-id="4fa53-284">Column Name</span></span></th>
<th align="left"><span data-ttu-id="4fa53-285">描述</span><span class="sxs-lookup"><span data-stu-id="4fa53-285">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4fa53-286">驱动器号</span><span class="sxs-lookup"><span data-stu-id="4fa53-286">Drive Letter</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fa53-287">用户分配给特定驱动器的计算机驱动器号。</span><span class="sxs-lookup"><span data-stu-id="4fa53-287">Computer drive letter that was assigned to the particular drive by the user.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4fa53-288">驱动器类型</span><span class="sxs-lookup"><span data-stu-id="4fa53-288">Drive Type</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fa53-289">驱动器的类型。</span><span class="sxs-lookup"><span data-stu-id="4fa53-289">Type of drive.</span></span> <span data-ttu-id="4fa53-290">有效值为操作系统驱动器和固定数据驱动器。</span><span class="sxs-lookup"><span data-stu-id="4fa53-290">Valid values are Operating System Drive and Fixed Data Drive.</span></span> <span data-ttu-id="4fa53-291">这些驱动器是物理驱动器，而不是逻辑卷。</span><span class="sxs-lookup"><span data-stu-id="4fa53-291">These are physical drives rather than logical volumes.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4fa53-292">密码强度</span><span class="sxs-lookup"><span data-stu-id="4fa53-292">Cipher Strength</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fa53-293">MBAM 策略规范期间管理员选择的密码长度。</span><span class="sxs-lookup"><span data-stu-id="4fa53-293">Cipher Strength selected by the Administrator during MBAM policy specification.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4fa53-294">保护器类型</span><span class="sxs-lookup"><span data-stu-id="4fa53-294">Protector Types</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fa53-295">通过用于加密操作系统或固定卷的策略选择的保护器类型。</span><span class="sxs-lookup"><span data-stu-id="4fa53-295">Type of protector selected via policy used to encrypt an operating system or Fixed volume.</span></span> <span data-ttu-id="4fa53-296">操作系统上的有效保护器类型为 TPM 或 TPM + PIN，并且固定数据卷的密码为密码。</span><span class="sxs-lookup"><span data-stu-id="4fa53-296">The valid protector types on an operating system are TPM or TPM+PIN and for a Fixed Data Volume is Password.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4fa53-297">保护程序状态</span><span class="sxs-lookup"><span data-stu-id="4fa53-297">Protector State</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fa53-298">指示由 MBAM 托管的计算机已启用在策略中指定的保护者类型。</span><span class="sxs-lookup"><span data-stu-id="4fa53-298">Indicates that the computer being managed by MBAM has enabled the protector type specified in the policy.</span></span> <span data-ttu-id="4fa53-299">有效状态为 "开" 或 "关"。</span><span class="sxs-lookup"><span data-stu-id="4fa53-299">The valid states are ON or OFF.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4fa53-300">加密状态</span><span class="sxs-lookup"><span data-stu-id="4fa53-300">Encryption State</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fa53-301">驱动器的加密状态。</span><span class="sxs-lookup"><span data-stu-id="4fa53-301">Encryption state of the drive.</span></span> <span data-ttu-id="4fa53-302">有效状态为加密、未加密和加密。</span><span class="sxs-lookup"><span data-stu-id="4fa53-302">Valid states are Encrypted, Not Encrypted, and Encrypting.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="4fa53-303">相关主题</span><span class="sxs-lookup"><span data-stu-id="4fa53-303">Related topics</span></span>


[<span data-ttu-id="4fa53-304">结合使用 MBAM 和 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="4fa53-304">Using MBAM with Configuration Manager</span></span>](using-mbam-with-configuration-manager.md)

 

 





