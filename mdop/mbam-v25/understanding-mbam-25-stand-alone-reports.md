---
title: 了解 MBAM 2.5 独立报告
description: 了解 MBAM 2.5 独立报告
author: dansimp
ms.assetid: 78b5aaf4-8257-4722-8eb9-e0de48db6a11
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 45e84c7c3b2bcb1602890c7c5a09592324da691e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798130"
---
# <span data-ttu-id="bc1d4-103">了解 MBAM 2.5 独立报告</span><span class="sxs-lookup"><span data-stu-id="bc1d4-103">Understanding MBAM 2.5 Stand-alone Reports</span></span>


<span data-ttu-id="bc1d4-104">本主题介绍了在独立拓扑中运行 Microsoft BitLocker 管理和监视（MBAM）时可用的报表。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-104">This topic describes the reports that are available when you are running Microsoft BitLocker Administration and Monitoring (MBAM) in the Stand-alone topology.</span></span>

**<span data-ttu-id="bc1d4-105">注意</span><span class="sxs-lookup"><span data-stu-id="bc1d4-105">Note</span></span>**  
<span data-ttu-id="bc1d4-106">如果你正在通过 Configuration Manager 集成拓扑运行 MBAM，则会从 Configuration Manager 生成报表，而不是从 MBAM 生成报表。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-106">If you are running MBAM with the Configuration Manager Integration topology, you generate reports from Configuration Manager rather than from MBAM.</span></span> <span data-ttu-id="bc1d4-107">有关这些报告的详细信息，请参阅[查看 Configuration Manager 集成拓扑的 MBAM 2.5 报告](viewing-mbam-25-reports-for-the-configuration-manager-integration-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-107">See [Viewing MBAM 2.5 Reports for the Configuration Manager Integration Topology](viewing-mbam-25-reports-for-the-configuration-manager-integration-topology.md) for more information about these reports.</span></span>



## <span data-ttu-id="bc1d4-108">了解 MBAM 独立拓扑报告</span><span class="sxs-lookup"><span data-stu-id="bc1d4-108">Understanding the MBAM Stand-alone topology reports</span></span>


<span data-ttu-id="bc1d4-109">MBAM 提供三种报告类型，可用于监控你的组织的 BitLocker 合规性：</span><span class="sxs-lookup"><span data-stu-id="bc1d4-109">MBAM provides three report types that you can use to monitor your organization for BitLocker compliance:</span></span>

-   [<span data-ttu-id="bc1d4-110">企业合规性报告</span><span class="sxs-lookup"><span data-stu-id="bc1d4-110">Enterprise Compliance Report</span></span>](#bkmk-enterprisecompliance)

-   [<span data-ttu-id="bc1d4-111">计算机合规性报告</span><span class="sxs-lookup"><span data-stu-id="bc1d4-111">Computer Compliance Report</span></span>](#bkmk-compliance)

-   [<span data-ttu-id="bc1d4-112">恢复审核报告</span><span class="sxs-lookup"><span data-stu-id="bc1d4-112">Recovery Audit Report</span></span>](#bkmk-recovery)

<span data-ttu-id="bc1d4-113">在独立拓扑中运行 MBAM 时，若要访问 MBAM 报表，请打开 web 浏览器，然后打开 "管理和监视" 网站。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-113">To access MBAM reports when you are running MBAM in the Stand-alone topology, open a web browser, and then open the Administration and Monitoring Website.</span></span> <span data-ttu-id="bc1d4-114">在左侧菜单栏中选择 "**报表**"。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-114">Select **Reports** in the left menu bar.</span></span> <span data-ttu-id="bc1d4-115">从顶部菜单栏中，选择要生成的报表类型。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-115">From the top menu bar, select the kind of report that you want to generate.</span></span> <span data-ttu-id="bc1d4-116">有关生成这些报表的详细信息，请参阅[生成 2.5 MBAM 独立报表](generating-mbam-25-stand-alone-reports.md)。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-116">For more information about generating these reports, see [Generating MBAM 2.5 Stand-alone Reports](generating-mbam-25-stand-alone-reports.md).</span></span>

### <a href="" id="bkmk-enterprisecompliance"></a><span data-ttu-id="bc1d4-117">企业合规性报告</span><span class="sxs-lookup"><span data-stu-id="bc1d4-117">Enterprise Compliance Report</span></span>

<span data-ttu-id="bc1d4-118">使用此报告类型可收集你的组织中的所有 BitLocker 合规性的相关信息。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-118">Use this report type to collect information about overall BitLocker compliance in your organization.</span></span> <span data-ttu-id="bc1d4-119">可以使用筛选器缩小搜索结果范围，以了解有关组织中计算机的合规性状态和错误状态的详细信息。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-119">You can use filters to narrow your search results to learn more about the compliance state and error status of computers in your organization.</span></span>

**<span data-ttu-id="bc1d4-120">企业合规性概述</span><span class="sxs-lookup"><span data-stu-id="bc1d4-120">Enterprise Compliance Overview</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="bc1d4-121">列名称</span><span class="sxs-lookup"><span data-stu-id="bc1d4-121">Column Name</span></span></th>
<th align="left"><span data-ttu-id="bc1d4-122">描述</span><span class="sxs-lookup"><span data-stu-id="bc1d4-122">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bc1d4-123">托管计算机</span><span class="sxs-lookup"><span data-stu-id="bc1d4-123">Managed Computers</span></span></p></td>
<td align="left"><p><span data-ttu-id="bc1d4-124">MBAM 管理的计算机数。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-124">Number of computers that MBAM manages.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bc1d4-125">符合百分比</span><span class="sxs-lookup"><span data-stu-id="bc1d4-125">% Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="bc1d4-126">企业中合规性计算机的百分比。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-126">Percentage of compliant computers in the enterprise.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bc1d4-127">不符合的%</span><span class="sxs-lookup"><span data-stu-id="bc1d4-127">% Non-Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="bc1d4-128">企业中不符合的计算机的百分比。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-128">Percentage of non-compliant computers in the enterprise.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bc1d4-129">% 豁免</span><span class="sxs-lookup"><span data-stu-id="bc1d4-129">% Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="bc1d4-130">免除 BitLocker 加密要求的计算机的百分比。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-130">Percentage of computers exempt from the BitLocker encryption requirement.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bc1d4-131">% 非豁免</span><span class="sxs-lookup"><span data-stu-id="bc1d4-131">% Non-Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="bc1d4-132">不受 BitLocker 加密要求免除的计算机的百分比。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-132">Percentage of computers not exempt from the BitLocker encryption requirement.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bc1d4-133">性</span><span class="sxs-lookup"><span data-stu-id="bc1d4-133">Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="bc1d4-134">企业中合规性计算机的百分比。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-134">Percentage of compliant computers in the enterprise.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bc1d4-135">不符合</span><span class="sxs-lookup"><span data-stu-id="bc1d4-135">Non-Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="bc1d4-136">企业中不符合的计算机的百分比。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-136">Percentage of non-compliant computers in the enterprise.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bc1d4-137">例外</span><span class="sxs-lookup"><span data-stu-id="bc1d4-137">Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="bc1d4-138">免除 BitLocker 加密要求的计算机的总数。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-138">Total computers that are exempt from the BitLocker encryption requirement.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bc1d4-139">非豁免</span><span class="sxs-lookup"><span data-stu-id="bc1d4-139">Non-Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="bc1d4-140">不免除 BitLocker 加密要求的计算机的总数。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-140">Total computers that are not exempt from the BitLocker encryption requirement.</span></span></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="bc1d4-141">企业合规性计算机详细信息</span><span class="sxs-lookup"><span data-stu-id="bc1d4-141">Enterprise Compliance Computer Details</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="bc1d4-142">列名称</span><span class="sxs-lookup"><span data-stu-id="bc1d4-142">Column Name</span></span></th>
<th align="left"><span data-ttu-id="bc1d4-143">描述</span><span class="sxs-lookup"><span data-stu-id="bc1d4-143">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bc1d4-144">计算机名</span><span class="sxs-lookup"><span data-stu-id="bc1d4-144">Computer Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="bc1d4-145">由 MBAM 托管的用户指定的 DNS 名称。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-145">User-specified DNS name that is managed by MBAM.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bc1d4-146">域名</span><span class="sxs-lookup"><span data-stu-id="bc1d4-146">Domain Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="bc1d4-147">客户端计算机所在的完全限定的域名，由 MBAM 管理。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-147">Fully qualified domain name where the client computer resides and is managed by MBAM.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bc1d4-148">合规性状态</span><span class="sxs-lookup"><span data-stu-id="bc1d4-148">Compliance Status</span></span></p></td>
<td align="left"><p><span data-ttu-id="bc1d4-149">根据为计算机指定的策略，对计算机合规的状态。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-149">State of compliance for the computer, according to the policy specified for the computer.</span></span> <span data-ttu-id="bc1d4-150">状态是不相容的和合规的。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-150">The states are Noncompliant and Compliant.</span></span> <span data-ttu-id="bc1d4-151">有关如何解释合规性状态的详细信息，请参阅以下企业合规性报告合规性状态表。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-151">See the following Enterprise Compliance Report Compliance States table for more information about how to interpret compliance states.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bc1d4-152">免除</span><span class="sxs-lookup"><span data-stu-id="bc1d4-152">Exemption</span></span></p></td>
<td align="left"><p><span data-ttu-id="bc1d4-153">指示此计算机是否不受 BitLocker 策略的状态。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-153">Status that indicates whether this computer is exempt from the BitLocker policy.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bc1d4-154">合规性状态详细信息</span><span class="sxs-lookup"><span data-stu-id="bc1d4-154">Compliance Status Details</span></span></p></td>
<td align="left"><p><span data-ttu-id="bc1d4-155">根据指定策略，有关计算机合规性状态的错误和状态消息。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-155">Error and status messages about the compliance state of the computer in accordance to the policy specified.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bc1d4-156">上次联系人</span><span class="sxs-lookup"><span data-stu-id="bc1d4-156">Last Contact</span></span></p></td>
<td align="left"><p><span data-ttu-id="bc1d4-157">计算机上次联系服务器以报告合规性状态的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-157">Date and time when the computer last contacted the server to report compliance status.</span></span> <span data-ttu-id="bc1d4-158">可配置联系人频率。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-158">The contact frequency is configurable.</span></span> <span data-ttu-id="bc1d4-159">有关详细信息，请参阅 MBAM 组策略设置。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-159">For more information, see the MBAM Group Policy settings.</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-compliance"></a><span data-ttu-id="bc1d4-160">计算机合规性报告</span><span class="sxs-lookup"><span data-stu-id="bc1d4-160">Computer Compliance Report</span></span>

<span data-ttu-id="bc1d4-161">使用此报告类型可收集特定于计算机或用户的信息。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-161">Use this report type to collect information that is specific to a computer or user.</span></span>

<span data-ttu-id="bc1d4-162">若要查看此报告，请单击企业合规性报告中的计算机名称，或在计算机合规性报告中键入计算机名称。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-162">View this report by clicking the computer name in the Enterprise Compliance Report, or by typing the computer name in the Computer Compliance Report.</span></span> <span data-ttu-id="bc1d4-163">此报告显示计算机上每个驱动器（操作系统和固定数据驱动器）的详细加密信息。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-163">This report shows detailed encryption information about each drive (operating system and fixed data drives) on a computer.</span></span> <span data-ttu-id="bc1d4-164">它还指示应用于计算机上的每个驱动器类型的策略。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-164">It also indicates the policy that is applied to each drive type on the computer.</span></span> <span data-ttu-id="bc1d4-165">若要查看每个驱动器的详细信息，请展开 "计算机名称" 条目。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-165">To view the details of each drive, expand the Computer Name entry.</span></span>

**<span data-ttu-id="bc1d4-166">注意</span><span class="sxs-lookup"><span data-stu-id="bc1d4-166">Note</span></span>**  
<span data-ttu-id="bc1d4-167">可移动数据卷加密状态不会显示在此报告中。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-167">Removable Data Volume encryption status is not shown in this report.</span></span>



**<span data-ttu-id="bc1d4-168">计算机合规性报告字段</span><span class="sxs-lookup"><span data-stu-id="bc1d4-168">Computer Compliance Report Fields</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="bc1d4-169">列名称</span><span class="sxs-lookup"><span data-stu-id="bc1d4-169">Column Name</span></span></th>
<th align="left"><span data-ttu-id="bc1d4-170">描述</span><span class="sxs-lookup"><span data-stu-id="bc1d4-170">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bc1d4-171">计算机名</span><span class="sxs-lookup"><span data-stu-id="bc1d4-171">Computer Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="bc1d4-172">由 MBAM 管理的用户指定的 DNS 计算机名。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-172">User-specified DNS computer name that is managed by MBAM.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bc1d4-173">域名</span><span class="sxs-lookup"><span data-stu-id="bc1d4-173">Domain Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="bc1d4-174">客户端计算机所在的完全限定的域名，由 MBAM 管理。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-174">Fully qualified domain name where the client computer resides and is managed by MBAM.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bc1d4-175">计算机类型</span><span class="sxs-lookup"><span data-stu-id="bc1d4-175">Computer Type</span></span></p></td>
<td align="left"><p><span data-ttu-id="bc1d4-176">计算机的类型。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-176">Type of computer.</span></span> <span data-ttu-id="bc1d4-177">有效类型为非便携式和可移植。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-177">Valid types are Non-Portable and Portable.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bc1d4-178">操作系统</span><span class="sxs-lookup"><span data-stu-id="bc1d4-178">Operating System</span></span></p></td>
<td align="left"><p><span data-ttu-id="bc1d4-179">在由 MBAM 托管的客户端计算机上找到的操作系统类型。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-179">Operating system type found on the client computer that is managed by MBAM.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bc1d4-180">合规性状态</span><span class="sxs-lookup"><span data-stu-id="bc1d4-180">Compliance Status</span></span></p></td>
<td align="left"><p><span data-ttu-id="bc1d4-181">由 MBAM 管理的计算机的整体合规性状态。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-181">Overall compliance status of the computer that is managed by MBAM.</span></span> <span data-ttu-id="bc1d4-182">有效状态符合和不相容。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-182">Valid states are Compliant and Noncompliant.</span></span></p>
<p><span data-ttu-id="bc1d4-183">请注意，每个驱动器的合规性状态（请参阅下表）可能指示不同的合规性状态。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-183">Notice that the compliance status per drive (see the following table) may indicate different compliance states.</span></span> <span data-ttu-id="bc1d4-184">但是，此字段根据指定的策略表示符合性状态。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-184">However, this field represents that compliance state, according to the specified policy.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bc1d4-185">策略密码强度</span><span class="sxs-lookup"><span data-stu-id="bc1d4-185">Policy Cipher Strength</span></span></p></td>
<td align="left"><p><span data-ttu-id="bc1d4-186">MBAM 策略规范期间管理员选择的密码长度（例如，使用扩散器的128位）。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-186">Cipher strength selected by the administrator during MBAM policy specification (for example, 128-bit with diffuser).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bc1d4-187">策略操作系统驱动器</span><span class="sxs-lookup"><span data-stu-id="bc1d4-187">Policy Operating System Drive</span></span></p></td>
<td align="left"><p><span data-ttu-id="bc1d4-188">指示操作系统是否需要加密，并显示相应的保护器类型。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-188">Indicates if encryption is required for the operating system and shows the appropriate protector type.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bc1d4-189">策略-固定数据驱动器</span><span class="sxs-lookup"><span data-stu-id="bc1d4-189">Policy-Fixed Data Drive</span></span></p></td>
<td align="left"><p><span data-ttu-id="bc1d4-190">指示固定数据驱动器是否需要加密。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-190">Indicates if encryption is required for the fixed data drive.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bc1d4-191">策略可移动数据驱动器</span><span class="sxs-lookup"><span data-stu-id="bc1d4-191">Policy Removable Data Drive</span></span></p></td>
<td align="left"><p><span data-ttu-id="bc1d4-192">指示可移动驱动器是否需要加密。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-192">Indicates if encryption is required for the removable drive.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bc1d4-193">设备用户</span><span class="sxs-lookup"><span data-stu-id="bc1d4-193">Device Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="bc1d4-194">由 MBAM 托管的计算机上的已知用户。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-194">Known users on the computer that is managed by MBAM.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bc1d4-195">免除</span><span class="sxs-lookup"><span data-stu-id="bc1d4-195">Exemption</span></span></p></td>
<td align="left"><p><span data-ttu-id="bc1d4-196">指示此计算机是否不受 BitLocker 策略的状态。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-196">Status that indicates whether this computer is exempt from the BitLocker policy.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bc1d4-197">制造商</span><span class="sxs-lookup"><span data-stu-id="bc1d4-197">Manufacturer</span></span></p></td>
<td align="left"><p><span data-ttu-id="bc1d4-198">计算机制造商名称，它显示在计算机 BIOS 中。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-198">Computer manufacturer name, as it appears in the computer BIOS.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bc1d4-199">型号</span><span class="sxs-lookup"><span data-stu-id="bc1d4-199">Model</span></span></p></td>
<td align="left"><p><span data-ttu-id="bc1d4-200">计算机制造商模型名称，它显示在计算机 BIOS 中。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-200">Computer manufacturer model name, as it appears in the computer BIOS.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bc1d4-201">合规性状态详细信息</span><span class="sxs-lookup"><span data-stu-id="bc1d4-201">Compliance Status Details</span></span></p></td>
<td align="left"><p><span data-ttu-id="bc1d4-202">根据指定的策略，有关计算机合规性状态的错误和状态消息。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-202">Error and status messages about the compliance state of the computer, in accordance with the specified policy.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bc1d4-203">上次联系人</span><span class="sxs-lookup"><span data-stu-id="bc1d4-203">Last Contact</span></span></p></td>
<td align="left"><p><span data-ttu-id="bc1d4-204">计算机上次联系服务器以报告合规性状态的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-204">Date and time that the computer last contacted the server to report compliance status.</span></span> <span data-ttu-id="bc1d4-205">可配置联系人频率。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-205">The contact frequency is configurable.</span></span> <span data-ttu-id="bc1d4-206">有关详细信息，请参阅 MBAM 组策略设置。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-206">For more information, see the MBAM Group Policy settings.</span></span></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="bc1d4-207">计算机合规性报告驱动器字段</span><span class="sxs-lookup"><span data-stu-id="bc1d4-207">Computer Compliance Report Drive Fields</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="bc1d4-208">列名称</span><span class="sxs-lookup"><span data-stu-id="bc1d4-208">Column Name</span></span></th>
<th align="left"><span data-ttu-id="bc1d4-209">描述</span><span class="sxs-lookup"><span data-stu-id="bc1d4-209">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bc1d4-210">驱动器号</span><span class="sxs-lookup"><span data-stu-id="bc1d4-210">Drive Letter</span></span></p></td>
<td align="left"><p><span data-ttu-id="bc1d4-211">用户分配给特定驱动器的计算机驱动器号。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-211">Computer drive letter that was assigned to the particular drive by the user.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bc1d4-212">驱动器类型</span><span class="sxs-lookup"><span data-stu-id="bc1d4-212">Drive Type</span></span></p></td>
<td align="left"><p><span data-ttu-id="bc1d4-213">驱动器的类型。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-213">Type of drive.</span></span> <span data-ttu-id="bc1d4-214">有效值为操作系统驱动器和固定数据驱动器。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-214">Valid values are Operating System Drive and Fixed Data Drive.</span></span> <span data-ttu-id="bc1d4-215">这些驱动器是物理驱动器，而不是逻辑卷。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-215">These are physical drives rather than logical volumes.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bc1d4-216">密码强度</span><span class="sxs-lookup"><span data-stu-id="bc1d4-216">Cipher Strength</span></span></p></td>
<td align="left"><p><span data-ttu-id="bc1d4-217">MBAM 策略规范期间管理员选择的密码长度。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-217">Cipher strength selected by the administrator during MBAM policy specification.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bc1d4-218">保护器类型</span><span class="sxs-lookup"><span data-stu-id="bc1d4-218">Protector Type</span></span></p></td>
<td align="left"><p><span data-ttu-id="bc1d4-219">通过用于加密操作系统或固定数据卷的组策略设置选择的保护器类型。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-219">Type of protector selected through the Group Policy setting used to encrypt an operating system or fixed data volume.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bc1d4-220">保护程序状态</span><span class="sxs-lookup"><span data-stu-id="bc1d4-220">Protector State</span></span></p></td>
<td align="left"><p><span data-ttu-id="bc1d4-221">指示由 MBAM 托管的计算机已启用在策略中指定的保护程序类型。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-221">Indicates that the computer being managed by MBAM has enabled the protector type that is specified in the policy.</span></span> <span data-ttu-id="bc1d4-222">有效状态为 "开" 或 "关"。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-222">The valid states are ON or OFF.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bc1d4-223">加密状态</span><span class="sxs-lookup"><span data-stu-id="bc1d4-223">Encryption State</span></span></p></td>
<td align="left"><p><span data-ttu-id="bc1d4-224">驱动器的加密状态。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-224">Encryption state of the drive.</span></span> <span data-ttu-id="bc1d4-225">有效状态为加密、未加密和加密。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-225">Valid states are Encrypted, Not Encrypted, and Encrypting.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bc1d4-226">合规性状态</span><span class="sxs-lookup"><span data-stu-id="bc1d4-226">Compliance Status</span></span></p></td>
<td align="left"><p><span data-ttu-id="bc1d4-227">指示驱动器是否符合策略的状态。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-227">State that indicates whether the drive is in accordance with the policy.</span></span> <span data-ttu-id="bc1d4-228">状态是不相容的和合规的。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-228">States are Noncompliant and Compliant.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bc1d4-229">合规性状态详细信息</span><span class="sxs-lookup"><span data-stu-id="bc1d4-229">Compliance Status Details</span></span></p></td>
<td align="left"><p><span data-ttu-id="bc1d4-230">根据指定的策略，对计算机合规性状态的错误和状态消息。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-230">Error and status messages of the compliance state of the computer, according to the specified policy.</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-recovery"></a><span data-ttu-id="bc1d4-231">恢复审核报告</span><span class="sxs-lookup"><span data-stu-id="bc1d4-231">Recovery Audit Report</span></span>

<span data-ttu-id="bc1d4-232">使用此报告类型审核请求访问 BitLocker 恢复密钥的用户。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-232">Use this report type to audit users who have requested access to BitLocker recovery keys.</span></span> <span data-ttu-id="bc1d4-233">该报表基于所需的筛选条件提供了多个筛选器。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-233">The report offers several filters based on the desired filtering criteria.</span></span> <span data-ttu-id="bc1d4-234">你可以筛选特定类型的用户（帮助台用户或最终用户），无论请求失败还是成功，所请求的密钥的具体类型以及发生检索的日期范围。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-234">You can filter on a specific type of user (a Help Desk user or an end user), whether the request failed or was successful, the specific type of key requested, and a date range during which the retrieval occurred.</span></span>

**<span data-ttu-id="bc1d4-235">恢复审核报告字段</span><span class="sxs-lookup"><span data-stu-id="bc1d4-235">Recovery Audit Report Fields</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="bc1d4-236">列名称</span><span class="sxs-lookup"><span data-stu-id="bc1d4-236">Column Name</span></span></th>
<th align="left"><span data-ttu-id="bc1d4-237">描述</span><span class="sxs-lookup"><span data-stu-id="bc1d4-237">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bc1d4-238">请求日期和时间</span><span class="sxs-lookup"><span data-stu-id="bc1d4-238">Request Date and Time</span></span></p></td>
<td align="left"><p><span data-ttu-id="bc1d4-239">最终用户或技术支持用户进行密钥检索请求的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-239">Date and time that a key retrieval request was made by an end user or Help Desk user.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bc1d4-240">审核请求源</span><span class="sxs-lookup"><span data-stu-id="bc1d4-240">Audit Request Source</span></span></p></td>
<td align="left"><p><span data-ttu-id="bc1d4-241">发起请求的网站。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-241">The site from which the request was initiated.</span></span> <span data-ttu-id="bc1d4-242">此条目将具有两个值之一： <strong> 自助服务门户 </strong> 或 <strong> 支持人员 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-242">This entry will have one of two values: <strong>Self-Service Portal</strong> or <strong>Helpdesk</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bc1d4-243">请求状态</span><span class="sxs-lookup"><span data-stu-id="bc1d4-243">Request Status</span></span></p></td>
<td align="left"><p><span data-ttu-id="bc1d4-244">请求的状态。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-244">Status of the request.</span></span> <span data-ttu-id="bc1d4-245">有效状态为 "成功" （已检索密钥）或 "失败" （未检索到密钥）。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-245">Valid statuses are Successful (the key was retrieved), or Failed (the key was not retrieved).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bc1d4-246">帮助台用户</span><span class="sxs-lookup"><span data-stu-id="bc1d4-246">Helpdesk User</span></span></p></td>
<td align="left"><p><span data-ttu-id="bc1d4-247">启动了密钥检索请求的技术支持用户。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-247">Help Desk user who initiated the request for key retrieval.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="bc1d4-248">注意</span><span class="sxs-lookup"><span data-stu-id="bc1d4-248">Note</span></span></strong><br/><p><span data-ttu-id="bc1d4-249">如果高级帮助台用户在未指定最终用户的情况下恢复密钥，则 " <strong> 最终用户" </strong> 字段将为空。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-249">If an Advanced Helpdesk User recovers the key without specifying the end user, the <strong>End User</strong> field will be blank.</span></span> <span data-ttu-id="bc1d4-250">标准帮助台用户必须指定最终用户，该用户将在此字段中显示。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-250">A standard Helpdesk User must specify the end user, and that user will appear in this field.</span></span></p>
<p><span data-ttu-id="bc1d4-251">通过自助服务门户的恢复将在此字段和 "最终用户" 字段中列出请求的最终用户 <strong> </strong> 。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-251">A recovery via the Self-Service Portal will list the requesting end user both in this field and in the <strong>End User</strong> field.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bc1d4-252">最终用户</span><span class="sxs-lookup"><span data-stu-id="bc1d4-252">End User</span></span></p></td>
<td align="left"><p><span data-ttu-id="bc1d4-253">启动密钥检索请求的最终用户。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-253">End user who initiated the request for key retrieval.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bc1d4-254">计算机</span><span class="sxs-lookup"><span data-stu-id="bc1d4-254">Computer</span></span></p></td>
<td align="left"><p><span data-ttu-id="bc1d4-255">已恢复的计算机的计算机名。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-255">Computer name of the computer that was recovered.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bc1d4-256">键类型</span><span class="sxs-lookup"><span data-stu-id="bc1d4-256">Key Type</span></span></p></td>
<td align="left"><p><span data-ttu-id="bc1d4-257">技术支持用户或最终用户请求的键类型。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-257">Type of key that was requested by the Help Desk user or the end user.</span></span> <span data-ttu-id="bc1d4-258">MBAM 收集的三种类型的键如下所示：</span><span class="sxs-lookup"><span data-stu-id="bc1d4-258">The three types of keys that MBAM collects are:</span></span></p>
<ul>
<li><p><span data-ttu-id="bc1d4-259">恢复密钥密码（用于在恢复模式下恢复计算机）</span><span class="sxs-lookup"><span data-stu-id="bc1d4-259">Recovery Key Password (used to recover a computer in recovery mode)</span></span></p></li>
<li><p><span data-ttu-id="bc1d4-260">恢复密钥 ID （用于以恢复模式代表另一个用户恢复计算机）</span><span class="sxs-lookup"><span data-stu-id="bc1d4-260">Recovery Key ID (used to recover a computer in recovery mode on behalf of another user)</span></span></p></li>
<li><p><span data-ttu-id="bc1d4-261">TPM 密码哈希（用于使用已锁定的 TPM 恢复计算机）</span><span class="sxs-lookup"><span data-stu-id="bc1d4-261">TPM Password Hash (used to recover a computer with a locked TPM)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bc1d4-262">原因描述</span><span class="sxs-lookup"><span data-stu-id="bc1d4-262">Reason Description</span></span></p></td>
<td align="left"><p><span data-ttu-id="bc1d4-263">由技术支持用户或最终用户请求指定的键类型的原因。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-263">Reason the specified key type was requested by the Help Desk user or the end user.</span></span> <span data-ttu-id="bc1d4-264">原因在 "驱动器恢复" 和 "管理管理和监视网站的 TPM" 功能中指定。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-264">The reasons are specified in the Drive Recovery and Manage TPM features of the Administration and Monitoring Website.</span></span> <span data-ttu-id="bc1d4-265">有效输入为用户输入的文本或以下原因代码之一：</span><span class="sxs-lookup"><span data-stu-id="bc1d4-265">The valid entries are user-entered text or one of the following reason codes:</span></span></p>
<ul>
<li><p><span data-ttu-id="bc1d4-266">操作系统启动顺序已更改</span><span class="sxs-lookup"><span data-stu-id="bc1d4-266">Operating System Boot Order changed</span></span></p></li>
<li><p><span data-ttu-id="bc1d4-267">BIOS 已更改</span><span class="sxs-lookup"><span data-stu-id="bc1d4-267">BIOS Changed</span></span></p></li>
<li><p><span data-ttu-id="bc1d4-268">操作系统文件已更改</span><span class="sxs-lookup"><span data-stu-id="bc1d4-268">Operating System files changed</span></span></p></li>
<li><p><span data-ttu-id="bc1d4-269">已丢失启动密钥</span><span class="sxs-lookup"><span data-stu-id="bc1d4-269">Lost Startup key</span></span></p></li>
<li><p><span data-ttu-id="bc1d4-270">丢失的 PIN</span><span class="sxs-lookup"><span data-stu-id="bc1d4-270">Lost PIN</span></span></p></li>
<li><p><span data-ttu-id="bc1d4-271">TPM 重置</span><span class="sxs-lookup"><span data-stu-id="bc1d4-271">TPM Reset</span></span></p></li>
<li><p><span data-ttu-id="bc1d4-272">丢失密码</span><span class="sxs-lookup"><span data-stu-id="bc1d4-272">Lost Passphrase</span></span></p></li>
<li><p><span data-ttu-id="bc1d4-273">失去智能卡</span><span class="sxs-lookup"><span data-stu-id="bc1d4-273">Lost Smartcard</span></span></p></li>
<li><p><span data-ttu-id="bc1d4-274">重置 PIN 锁定</span><span class="sxs-lookup"><span data-stu-id="bc1d4-274">Reset PIN lockout</span></span></p></li>
<li><p><span data-ttu-id="bc1d4-275">打开 TPM</span><span class="sxs-lookup"><span data-stu-id="bc1d4-275">Turn on TPM</span></span></p></li>
<li><p><span data-ttu-id="bc1d4-276">关闭 TPM</span><span class="sxs-lookup"><span data-stu-id="bc1d4-276">Turn off TPM</span></span></p></li>
<li><p><span data-ttu-id="bc1d4-277">更改 TPM 密码</span><span class="sxs-lookup"><span data-stu-id="bc1d4-277">Change TPM password</span></span></p></li>
<li><p><span data-ttu-id="bc1d4-278">清除 TPM</span><span class="sxs-lookup"><span data-stu-id="bc1d4-278">Clear TPM</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="bc1d4-279">注意</span><span class="sxs-lookup"><span data-stu-id="bc1d4-279">Note</span></span>**  
<span data-ttu-id="bc1d4-280">通过单击 "**报表**" 菜单栏上的 "**导出**" 按钮，可将报表结果保存到文件中。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-280">Report results can be saved to a file by clicking the **Export** button on the **Reports** menu bar.</span></span>




## <span data-ttu-id="bc1d4-281">相关主题</span><span class="sxs-lookup"><span data-stu-id="bc1d4-281">Related topics</span></span>


[<span data-ttu-id="bc1d4-282">监视和报告 BitLocker 与 MBAM 2.5 的相容性</span><span class="sxs-lookup"><span data-stu-id="bc1d4-282">Monitoring and Reporting BitLocker Compliance with MBAM 2.5</span></span>](monitoring-and-reporting-bitlocker-compliance-with-mbam-25.md)

[<span data-ttu-id="bc1d4-283">生成 MBAM 2.5 独立报告</span><span class="sxs-lookup"><span data-stu-id="bc1d4-283">Generating MBAM 2.5 Stand-alone Reports</span></span>](generating-mbam-25-stand-alone-reports.md)



## <span data-ttu-id="bc1d4-284">已获得 MBAM 的建议？</span><span class="sxs-lookup"><span data-stu-id="bc1d4-284">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="bc1d4-285">在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-285">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="bc1d4-286">对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-286">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





