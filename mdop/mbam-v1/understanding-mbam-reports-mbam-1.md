---
title: 了解 MBAM 报告
description: 了解 MBAM 报告
author: dansimp
ms.assetid: 34e4aaeb-7f89-41a1-b816-c6fe8397b060
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fa64a4724c87a42774e569b556013bfec2ed5514
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803254"
---
# <span data-ttu-id="55396-103">了解 MBAM 报告</span><span class="sxs-lookup"><span data-stu-id="55396-103">Understanding MBAM Reports</span></span>


<span data-ttu-id="55396-104">Microsoft BitLocker 管理和监视（MBAM）生成各种报告以监控 BitLocker 使用情况和合规性。</span><span class="sxs-lookup"><span data-stu-id="55396-104">Microsoft BitLocker Administration and Monitoring (MBAM) generates various reports to monitor BitLocker usage and compliance.</span></span> <span data-ttu-id="55396-105">本主题介绍针对企业合规性、单独计算机、硬件兼容性和密钥恢复活动的 MBAM 报告。</span><span class="sxs-lookup"><span data-stu-id="55396-105">This topic describes the MBAM reports for enterprise compliance, individual computers, hardware compatibility, and key recovery activity.</span></span>

## <span data-ttu-id="55396-106">了解报表</span><span class="sxs-lookup"><span data-stu-id="55396-106">Understanding Reports</span></span>


<span data-ttu-id="55396-107">若要访问 MBAM 的报表功能，请打开 MBAM 管理网站。</span><span class="sxs-lookup"><span data-stu-id="55396-107">To access the Reports feature of MBAM, open the MBAM administration website.</span></span> <span data-ttu-id="55396-108">在导航窗格中选择 "**报表**"。</span><span class="sxs-lookup"><span data-stu-id="55396-108">Select **Reports** in the navigation pane.</span></span> <span data-ttu-id="55396-109">然后，在 "主内容" 窗格中，单击报表类型的选项卡： "**企业合规性报告**"、"**计算机合规性报告**"、"**硬件审核报告**" 或 "**恢复审核报告**"。</span><span class="sxs-lookup"><span data-stu-id="55396-109">Then, in the main content pane, click the tab for your report type: **Enterprise Compliance Report**, **Computer Compliance Report**, **Hardware Audit Report**, or **Recovery Audit Report**.</span></span>

### <span data-ttu-id="55396-110">企业合规性报告</span><span class="sxs-lookup"><span data-stu-id="55396-110">Enterprise Compliance Report</span></span>

<span data-ttu-id="55396-111">企业合规性报告提供有关您的组织中的所有 BitLocker 合规性的信息。</span><span class="sxs-lookup"><span data-stu-id="55396-111">An Enterprise Compliance Report provides information on overall BitLocker compliance in your organization.</span></span> <span data-ttu-id="55396-112">此报告的可用筛选器允许你根据合规性状态和错误状态缩小搜索结果的范围。</span><span class="sxs-lookup"><span data-stu-id="55396-112">The available filters for this report allow you to narrow your search results according to Compliance state and Error status.</span></span> <span data-ttu-id="55396-113">此报告每6小时运行一次。</span><span class="sxs-lookup"><span data-stu-id="55396-113">This report runs every six hours.</span></span>

**<span data-ttu-id="55396-114">企业合规性报告字段</span><span class="sxs-lookup"><span data-stu-id="55396-114">Enterprise Compliance Report fields</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="55396-115">列名称</span><span class="sxs-lookup"><span data-stu-id="55396-115">Column Name</span></span></th>
<th align="left"><span data-ttu-id="55396-116">描述</span><span class="sxs-lookup"><span data-stu-id="55396-116">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="55396-117">计算机名</span><span class="sxs-lookup"><span data-stu-id="55396-117">Computer Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="55396-118">由 MBAM 管理的用户指定的 DNS 名称。</span><span class="sxs-lookup"><span data-stu-id="55396-118">The user-specified DNS name that is being managed by MBAM.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="55396-119">域名</span><span class="sxs-lookup"><span data-stu-id="55396-119">Domain Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="55396-120">客户端计算机所在的完全限定的域名，由 MBAM 管理。</span><span class="sxs-lookup"><span data-stu-id="55396-120">The fully qualified domain name where the client computer resides and is managed by MBAM.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="55396-121">合规性状态</span><span class="sxs-lookup"><span data-stu-id="55396-121">Compliance Status</span></span></p></td>
<td align="left"><p><span data-ttu-id="55396-122">根据为计算机指定的策略，对计算机合规性的状态。</span><span class="sxs-lookup"><span data-stu-id="55396-122">The state of compliance for the computer, according to the policy specified for the computer.</span></span> <span data-ttu-id="55396-123">可能的状态是不相容的和合规的。</span><span class="sxs-lookup"><span data-stu-id="55396-123">The possible states are Noncompliant and Compliant.</span></span> <span data-ttu-id="55396-124">有关详细信息，请参阅本主题中的企业合规性报告合规性状态。</span><span class="sxs-lookup"><span data-stu-id="55396-124">For more information, see Enterprise Compliance Report Compliance States in this topic.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="55396-125">免除</span><span class="sxs-lookup"><span data-stu-id="55396-125">Exemption</span></span></p></td>
<td align="left"><p><span data-ttu-id="55396-126">确定硬件类型的标识以及计算机是否受策略豁免的计算机硬件状态。</span><span class="sxs-lookup"><span data-stu-id="55396-126">The state of the computer hardware for determining the identification of the hardware type and whether the computer is exempt from policy.</span></span> <span data-ttu-id="55396-127">有三种可能的状态：硬件未知（MBAM 未识别硬件类型）、硬件免除（硬件类型已识别并被标记为不受 MBAM 策略的免除），并且不例外（硬件已确定，不会免于策略的例外）。</span><span class="sxs-lookup"><span data-stu-id="55396-127">There are three possible states: Hardware Unknown (the hardware type has not been identified by MBAM), Hardware Exempt (the hardware type was identified and was marked as exempt from MBAM policy), and Not Exempt (the hardware was identified and is not exempt from policy).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="55396-128">设备用户</span><span class="sxs-lookup"><span data-stu-id="55396-128">Device Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="55396-129">由 MBAM 管理的计算机上的已知用户。</span><span class="sxs-lookup"><span data-stu-id="55396-129">Known users on the computer that is being managed by MBAM.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="55396-130">合规性状态详细信息</span><span class="sxs-lookup"><span data-stu-id="55396-130">Compliance Status Details</span></span></p></td>
<td align="left"><p><span data-ttu-id="55396-131">根据指定策略，有关计算机合规性状态的错误和状态消息。</span><span class="sxs-lookup"><span data-stu-id="55396-131">Error and status messages about the compliance state of the computer in accordance to the specified policy.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="55396-132">上次联系人</span><span class="sxs-lookup"><span data-stu-id="55396-132">Last Contact</span></span></p></td>
<td align="left"><p><span data-ttu-id="55396-133">计算机上次联系服务器以报告合规性状态的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="55396-133">Date and time when the computer last contacted the server to report compliance status.</span></span> <span data-ttu-id="55396-134">此时间可配置。</span><span class="sxs-lookup"><span data-stu-id="55396-134">This time is configurable.</span></span> <span data-ttu-id="55396-135">请参阅 MBAM 策略设置。</span><span class="sxs-lookup"><span data-stu-id="55396-135">See MBAM policy settings.</span></span></p></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="55396-136">企业合规性报告合规性状态</span><span class="sxs-lookup"><span data-stu-id="55396-136">Enterprise Compliance Report Compliance states</span></span>**

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="55396-137">合规性状态</span><span class="sxs-lookup"><span data-stu-id="55396-137">Compliance Status</span></span></th>
<th align="left"><span data-ttu-id="55396-138">免除</span><span class="sxs-lookup"><span data-stu-id="55396-138">Exemption</span></span></th>
<th align="left"><span data-ttu-id="55396-139">描述</span><span class="sxs-lookup"><span data-stu-id="55396-139">Description</span></span></th>
<th align="left"><span data-ttu-id="55396-140">用户操作</span><span class="sxs-lookup"><span data-stu-id="55396-140">User Action</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="55396-141">标准</span><span class="sxs-lookup"><span data-stu-id="55396-141">Noncompliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="55396-142">不豁免</span><span class="sxs-lookup"><span data-stu-id="55396-142">Not Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="55396-143">根据指定的策略，计算机不符合规则，并且硬件类型未被指定为策略例外。</span><span class="sxs-lookup"><span data-stu-id="55396-143">The computer is noncompliant according to the specified policy, and the hardware type has not been indicated as exempt from policy.</span></span></p></td>
<td align="left"><p><span data-ttu-id="55396-144">单击 " <strong> 计算机名 </strong> " 以展开计算机合规性报告，并确定每个驱动器的状态是否符合指定的策略。</span><span class="sxs-lookup"><span data-stu-id="55396-144">Click <strong>Computer Name</strong> to expand the Computer Compliance Report and determine whether the state of each drive complies with the specified policy.</span></span> <span data-ttu-id="55396-145">如果加密状态指示计算机未加密，可能仍在处理加密，或者计算机上可能存在错误。</span><span class="sxs-lookup"><span data-stu-id="55396-145">If the encryption state indicates that the computer is not encrypted, encryption might still be in process, or there might be an error on the computer.</span></span> <span data-ttu-id="55396-146">如果没有错误，可能是因为计算机仍在连接或建立加密状态的过程中。</span><span class="sxs-lookup"><span data-stu-id="55396-146">If there is no error, the likely cause is that the computer is still in the process of connecting or establishing the encryption status.</span></span> <span data-ttu-id="55396-147">稍后再次查看以确定状态是否更改。</span><span class="sxs-lookup"><span data-stu-id="55396-147">Check back later to determine if the state changes.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="55396-148">性</span><span class="sxs-lookup"><span data-stu-id="55396-148">Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="55396-149">不豁免</span><span class="sxs-lookup"><span data-stu-id="55396-149">Not Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="55396-150">计算机符合指定的策略。</span><span class="sxs-lookup"><span data-stu-id="55396-150">The computer is compliant in accordance with the specified policy.</span></span></p></td>
<td align="left"><p><span data-ttu-id="55396-151">无需执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="55396-151">No Action needed.</span></span> <span data-ttu-id="55396-152">或者，您可以查看计算机合规性报告以确认计算机的状态。</span><span class="sxs-lookup"><span data-stu-id="55396-152">Optionally, you can view the Computer Compliance Report to confirm the state of the computer.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="55396-153">性</span><span class="sxs-lookup"><span data-stu-id="55396-153">Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="55396-154">硬件豁免</span><span class="sxs-lookup"><span data-stu-id="55396-154">Hardware Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="55396-155">如果硬件类型不受豁免。</span><span class="sxs-lookup"><span data-stu-id="55396-155">If the Hardware type is exempt.</span></span> <span data-ttu-id="55396-156">无论策略的设置方式或每个硬驱的单个状态如何，整体状态均视为合规。</span><span class="sxs-lookup"><span data-stu-id="55396-156">Regardless of how the policy is set or the individual status of each hard-drive, the overall state is considered to be compliant.</span></span></p></td>
<td align="left"><p><span data-ttu-id="55396-157">无需执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="55396-157">No action needed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="55396-158">性</span><span class="sxs-lookup"><span data-stu-id="55396-158">Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="55396-159">硬件未知</span><span class="sxs-lookup"><span data-stu-id="55396-159">Hardware Unknown</span></span></p></td>
<td align="left"><p><span data-ttu-id="55396-160">MBAM 识别硬件类型，但 MBAM 不知道它是否豁免。</span><span class="sxs-lookup"><span data-stu-id="55396-160">MBAM recognizes the hardware type, but MBAM does not know whether it is exempt or not exempt.</span></span> <span data-ttu-id="55396-161">如果管理员未设置硬件的兼容状态，则会出现此情况。</span><span class="sxs-lookup"><span data-stu-id="55396-161">This occurs if the administrator has not set the Compatible status for the hardware.</span></span> <span data-ttu-id="55396-162">因此，默认情况下，MBAM 将恢复为合规状态。</span><span class="sxs-lookup"><span data-stu-id="55396-162">Therefore, MBAM reverts to Compliant status by default.</span></span></p></td>
<td align="left"><p><span data-ttu-id="55396-163">这是新部署的 MBAM 客户端的初始状态。</span><span class="sxs-lookup"><span data-stu-id="55396-163">This is the initial state of a newly deployed MBAM client.</span></span> <span data-ttu-id="55396-164">它通常仅是瞬时状态。</span><span class="sxs-lookup"><span data-stu-id="55396-164">It is typically only a transient state.</span></span> <span data-ttu-id="55396-165">即使管理员已将硬件标记为兼容，在客户端计算机重新报告之前，可能会有很长的延迟或可配置的等待时间。</span><span class="sxs-lookup"><span data-stu-id="55396-165">Even if the administrator has marked the Hardware as Compatible, there can be a significant delay or configurable wait time before the client computer reports back in.</span></span> <span data-ttu-id="55396-166">记下上次联系人的时间，并在指定间隔后再次签入，以查看状态是否已更改。</span><span class="sxs-lookup"><span data-stu-id="55396-166">Make note of the time of Last Contact, and check in again after the specified interval to see if the state has changed.</span></span> <span data-ttu-id="55396-167">如果状态未更改，则此计算机或硬件类型可能存在错误。</span><span class="sxs-lookup"><span data-stu-id="55396-167">If the state has not changed, there may be an error for this computer or hardware type.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="55396-168">计算机合规性报告</span><span class="sxs-lookup"><span data-stu-id="55396-168">Computer Compliance Report</span></span>

<span data-ttu-id="55396-169">"计算机合规性" 报表显示特定于计算机或用户的信息。</span><span class="sxs-lookup"><span data-stu-id="55396-169">The Computer Compliance Report displays information that is specific to a computer or user.</span></span>

<span data-ttu-id="55396-170">计算机合规性报告为计算机上的每个驱动器提供详细的加密信息和适用的策略，包括操作系统驱动器和固定数据驱动器。</span><span class="sxs-lookup"><span data-stu-id="55396-170">The Computer Compliance Report provides detailed encryption information and applicable policies for each drive on a computer, including operating system drives and fixed data drives.</span></span> <span data-ttu-id="55396-171">若要查看此报告类型，请在企业合规性报告中单击计算机名称，或在 "计算机合规性报告" 中键入计算机名称。</span><span class="sxs-lookup"><span data-stu-id="55396-171">To view this report type, click the computer name in the Enterprise Compliance Report or type the computer name in the Computer Compliance Report.</span></span> <span data-ttu-id="55396-172">若要查看每个驱动器的详细信息，请展开 "计算机名称" 条目。</span><span class="sxs-lookup"><span data-stu-id="55396-172">To view the details of each drive, expand the Computer Name entry.</span></span>

<span data-ttu-id="55396-173">**注意** 此报告不提供可移动数据卷的加密状态。</span><span class="sxs-lookup"><span data-stu-id="55396-173">**Note** This report does not provide encryption status for Removable Data Volumes.</span></span>

 

**<span data-ttu-id="55396-174">计算机合规性报告字段</span><span class="sxs-lookup"><span data-stu-id="55396-174">Computer Compliance Report fields</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="55396-175">列名称</span><span class="sxs-lookup"><span data-stu-id="55396-175">Column Name</span></span></th>
<th align="left"><span data-ttu-id="55396-176">描述</span><span class="sxs-lookup"><span data-stu-id="55396-176">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="55396-177">计算机名</span><span class="sxs-lookup"><span data-stu-id="55396-177">Computer Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="55396-178">由 MBAM 管理的用户指定的 DNS 计算机名。</span><span class="sxs-lookup"><span data-stu-id="55396-178">The user-specified DNS computer name that is being managed by MBAM.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="55396-179">域名</span><span class="sxs-lookup"><span data-stu-id="55396-179">Domain Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="55396-180">客户端计算机所在的完全限定的域名，由 MBAM 管理。</span><span class="sxs-lookup"><span data-stu-id="55396-180">The fully qualified domain name where the client computer resides and is managed by MBAM.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="55396-181">计算机类型</span><span class="sxs-lookup"><span data-stu-id="55396-181">Computer Type</span></span></p></td>
<td align="left"><p><span data-ttu-id="55396-182">计算机的可移植性类型。</span><span class="sxs-lookup"><span data-stu-id="55396-182">The portability type of computer.</span></span> <span data-ttu-id="55396-183">有效类型为非便携式和可移植。</span><span class="sxs-lookup"><span data-stu-id="55396-183">Valid types are non-Portable and Portable.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="55396-184">操作系统</span><span class="sxs-lookup"><span data-stu-id="55396-184">Operating System</span></span></p></td>
<td align="left"><p><span data-ttu-id="55396-185">MBAM 托管客户端计算机上安装的操作系统类型。</span><span class="sxs-lookup"><span data-stu-id="55396-185">Operating System type installed on the MBAM managed client computer.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="55396-186">合规性状态</span><span class="sxs-lookup"><span data-stu-id="55396-186">Compliance Status</span></span></p></td>
<td align="left"><p><span data-ttu-id="55396-187">由 MBAM 管理的计算机的整体合规性状态。</span><span class="sxs-lookup"><span data-stu-id="55396-187">The overall Compliance Status of the computer managed by MBAM.</span></span> <span data-ttu-id="55396-188">有效状态符合和不相容。</span><span class="sxs-lookup"><span data-stu-id="55396-188">Valid states are Compliant and Noncompliant.</span></span> <span data-ttu-id="55396-189">尽管可以在同一台计算机中具有兼容和不兼容的驱动器，但此字段指示每个指定策略的计算机总体合规性。</span><span class="sxs-lookup"><span data-stu-id="55396-189">While it is possible to have Compliant and Noncompliant drives in the same computer, this field indicates the overall computer compliance per specified policy.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="55396-190">策略 Cypher 强度</span><span class="sxs-lookup"><span data-stu-id="55396-190">Policy Cypher Strength</span></span></p></td>
<td align="left"><p><span data-ttu-id="55396-191">MBAM 策略规范期间管理员选择的密码强度。</span><span class="sxs-lookup"><span data-stu-id="55396-191">The Cipher Strength selected by the Administrator during MBAM policy specification.</span></span> <span data-ttu-id="55396-192">例如，带扩散器的128位</span><span class="sxs-lookup"><span data-stu-id="55396-192">For example, 128-bit with Diffuser</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="55396-193">策略操作系统驱动器</span><span class="sxs-lookup"><span data-stu-id="55396-193">Policy Operating System Drive</span></span></p></td>
<td align="left"><p><span data-ttu-id="55396-194">指示是否需要对 O/S 和保护器类型进行加密（如果适用）。</span><span class="sxs-lookup"><span data-stu-id="55396-194">Indicates whether encryption is required for the O/S and the protector type as applicable.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="55396-195">策略固定数据驱动器</span><span class="sxs-lookup"><span data-stu-id="55396-195">Policy Fixed Data Drive</span></span></p></td>
<td align="left"><p><span data-ttu-id="55396-196">指示是否需要对固定驱动器进行加密。</span><span class="sxs-lookup"><span data-stu-id="55396-196">Indicates whether encryption is required for the Fixed Drive.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="55396-197">策略可移动数据驱动器</span><span class="sxs-lookup"><span data-stu-id="55396-197">Policy Removable Data Drive</span></span></p></td>
<td align="left"><p><span data-ttu-id="55396-198">指示可移动驱动器是否需要加密。</span><span class="sxs-lookup"><span data-stu-id="55396-198">Indicates whether encryption is required for the Removable Drive.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="55396-199">设备用户</span><span class="sxs-lookup"><span data-stu-id="55396-199">Device Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="55396-200">提供计算机上已知用户的标识。</span><span class="sxs-lookup"><span data-stu-id="55396-200">Provides the identity of known users on the computer.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="55396-201">免除</span><span class="sxs-lookup"><span data-stu-id="55396-201">Exemption</span></span></p></td>
<td align="left"><p><span data-ttu-id="55396-202">指示计算机硬件类型是否由 MBAM 识别，如果知道计算机是否已被指示为策略例外。</span><span class="sxs-lookup"><span data-stu-id="55396-202">Indicates whether the computer hardware type is recognized by MBAM and, if known, whether the computer has been indicated as exempt from policy.</span></span> <span data-ttu-id="55396-203">有三种状态：硬件未知（硬件类型尚未由 MBAM 标识）;硬件例外（识别硬件类型，并标记为不受 MBAM 策略的豁免）;不例外（硬件已确定，不会被策略豁免）。</span><span class="sxs-lookup"><span data-stu-id="55396-203">There are three states: Hardware Unknown (the hardware type has not been identified by MBAM); Hardware Exempt (the hardware type was identified and was marked as exempt from MBAM policy); and Not Exempt (the hardware was identified and is not exempt from policy).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="55396-204">制造商</span><span class="sxs-lookup"><span data-stu-id="55396-204">Manufacturer</span></span></p></td>
<td align="left"><p><span data-ttu-id="55396-205">计算机 BIOS 中显示的计算机制造商名称。</span><span class="sxs-lookup"><span data-stu-id="55396-205">The computer manufacturer name as it appears in the computer BIOS.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="55396-206">型号</span><span class="sxs-lookup"><span data-stu-id="55396-206">Model</span></span></p></td>
<td align="left"><p><span data-ttu-id="55396-207">计算机 BIOS 中显示的计算机制造商型号名称。</span><span class="sxs-lookup"><span data-stu-id="55396-207">The computer manufacturer model name as it appears in the computer BIOS.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="55396-208">合规性状态详细信息</span><span class="sxs-lookup"><span data-stu-id="55396-208">Compliance Status Details</span></span></p></td>
<td align="left"><p><span data-ttu-id="55396-209">根据指定策略，计算机合规性状态的错误和状态消息。</span><span class="sxs-lookup"><span data-stu-id="55396-209">Error and status messages of the compliance state of the computer in accordance with the specified policy.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="55396-210">上次联系人</span><span class="sxs-lookup"><span data-stu-id="55396-210">Last Contact</span></span></p></td>
<td align="left"><p><span data-ttu-id="55396-211">计算机上次联系服务器以报告合规性状态的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="55396-211">Date and time that the computer last contacted the server to report compliance status.</span></span> <span data-ttu-id="55396-212">T</span><span class="sxs-lookup"><span data-stu-id="55396-212">T</span></span></p></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="55396-213">计算机合规性报告驱动器字段</span><span class="sxs-lookup"><span data-stu-id="55396-213">Computer Compliance Report Drive fields</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="55396-214">列名称</span><span class="sxs-lookup"><span data-stu-id="55396-214">Column Name</span></span></th>
<th align="left"><span data-ttu-id="55396-215">描述</span><span class="sxs-lookup"><span data-stu-id="55396-215">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="55396-216">驱动器号</span><span class="sxs-lookup"><span data-stu-id="55396-216">Drive Letter</span></span></p></td>
<td align="left"><p><span data-ttu-id="55396-217">用户分配给此特定驱动器的计算机驱动器号。</span><span class="sxs-lookup"><span data-stu-id="55396-217">Computer drive letter that was assigned to this particular drive by the user.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="55396-218">驱动器类型</span><span class="sxs-lookup"><span data-stu-id="55396-218">Drive Type</span></span></p></td>
<td align="left"><p><span data-ttu-id="55396-219">驱动器的类型。</span><span class="sxs-lookup"><span data-stu-id="55396-219">Type of drive.</span></span> <span data-ttu-id="55396-220">有效值为操作系统驱动器和固定数据驱动器。</span><span class="sxs-lookup"><span data-stu-id="55396-220">Valid values are Operating System Drive and Fixed Data Drive.</span></span> <span data-ttu-id="55396-221">这些驱动器是物理驱动器，而不是逻辑卷。</span><span class="sxs-lookup"><span data-stu-id="55396-221">These are physical drives rather than logical volumes.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="55396-222">Cypher 强度</span><span class="sxs-lookup"><span data-stu-id="55396-222">Cypher Strength</span></span></p></td>
<td align="left"><p><span data-ttu-id="55396-223">MBAM 策略规范期间管理员选择的密码长度。</span><span class="sxs-lookup"><span data-stu-id="55396-223">Cipher Strength selected by the Administrator during MBAM policy specification.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="55396-224">保护器类型</span><span class="sxs-lookup"><span data-stu-id="55396-224">Protector Type</span></span></p></td>
<td align="left"><p><span data-ttu-id="55396-225">通过用于加密操作系统或固定卷的策略选择的保护器类型。</span><span class="sxs-lookup"><span data-stu-id="55396-225">Type of protector selected via policy used to encrypt an operating system or Fixed volume.</span></span> <span data-ttu-id="55396-226">操作系统驱动器上的有效保护器类型为 TPM 或 TPM + PIN。</span><span class="sxs-lookup"><span data-stu-id="55396-226">The valid protector types on an operating system drive are TPM or TPM+PIN.</span></span> <span data-ttu-id="55396-227">固定数据卷的唯一有效保护程序类型是密码。</span><span class="sxs-lookup"><span data-stu-id="55396-227">The only valid protector type for a Fixed Data Volume is Password.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="55396-228">保护程序状态</span><span class="sxs-lookup"><span data-stu-id="55396-228">Protector State</span></span></p></td>
<td align="left"><p><span data-ttu-id="55396-229">此字段指示计算机是否已启用在策略中指定的保护器类型。</span><span class="sxs-lookup"><span data-stu-id="55396-229">This field indicates whether the computer has enabled the protector type specified in the policy.</span></span> <span data-ttu-id="55396-230">有效状态为 "开" 或 "关"。</span><span class="sxs-lookup"><span data-stu-id="55396-230">The valid states are ON or OFF.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="55396-231">加密状态</span><span class="sxs-lookup"><span data-stu-id="55396-231">Encryption State</span></span></p></td>
<td align="left"><p><span data-ttu-id="55396-232">这是驱动器的当前加密状态。</span><span class="sxs-lookup"><span data-stu-id="55396-232">This is the current encryption state of the drive.</span></span> <span data-ttu-id="55396-233">有效状态为加密、未加密和加密。</span><span class="sxs-lookup"><span data-stu-id="55396-233">Valid states are Encrypted, Not Encrypted, and Encrypting.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="55396-234">合规性状态</span><span class="sxs-lookup"><span data-stu-id="55396-234">Compliance Status</span></span></p></td>
<td align="left"><p><span data-ttu-id="55396-235">指示驱动器是否符合策略。</span><span class="sxs-lookup"><span data-stu-id="55396-235">Indicates whether the drive is in accordance with the policy.</span></span> <span data-ttu-id="55396-236">状态是不相容的和合规的。</span><span class="sxs-lookup"><span data-stu-id="55396-236">States are Noncompliant and Compliant.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="55396-237">合规性状态详细信息</span><span class="sxs-lookup"><span data-stu-id="55396-237">Compliance Status Details</span></span></p></td>
<td align="left"><p><span data-ttu-id="55396-238">包含有关计算机合规性状态的错误和状态消息。</span><span class="sxs-lookup"><span data-stu-id="55396-238">Contains error and status messages regarding the compliance state of the computer.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="55396-239">硬件审核报告</span><span class="sxs-lookup"><span data-stu-id="55396-239">Hardware Audit Report</span></span>

<span data-ttu-id="55396-240">此报告可帮助你审核对特定计算机和模型的硬件兼容性状态所做的更改。</span><span class="sxs-lookup"><span data-stu-id="55396-240">This report can help you audit changes to the Hardware Compatibility status of specific computer makes and models.</span></span> <span data-ttu-id="55396-241">为了帮助您缩小搜索结果的范围，此报告包括筛选条件等条件，例如更改类型和发生时间。</span><span class="sxs-lookup"><span data-stu-id="55396-241">To help you narrow your search results, this report includes filtering on criteria such as type of change and time of occurrence.</span></span> <span data-ttu-id="55396-242">每个状态更改均按用户和日期和时间进行跟踪。</span><span class="sxs-lookup"><span data-stu-id="55396-242">Each state change is tracked by user and date and time.</span></span> <span data-ttu-id="55396-243">硬件类型由在客户端计算机上运行的 MBAM 代理自动填充。</span><span class="sxs-lookup"><span data-stu-id="55396-243">The Hardware Type is automatically populated by the MBAM agent that runs on the client computer.</span></span> <span data-ttu-id="55396-244">此报告跟踪用户对从 MBAM 托管计算机直接收集的信息所做的更改。</span><span class="sxs-lookup"><span data-stu-id="55396-244">This report tracks user changes to the information collected directly from the MBAM managed computer.</span></span> <span data-ttu-id="55396-245">典型的管理更改是从兼容性更改到不兼容。</span><span class="sxs-lookup"><span data-stu-id="55396-245">A typical administrative change is changing from Compatible to incompatible.</span></span> <span data-ttu-id="55396-246">但是，管理员还可以修改任何字段。</span><span class="sxs-lookup"><span data-stu-id="55396-246">However, the administrator can also revise any field.</span></span>

**<span data-ttu-id="55396-247">硬件审核报告字段</span><span class="sxs-lookup"><span data-stu-id="55396-247">Hardware Audit Report fields</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="55396-248">列名称</span><span class="sxs-lookup"><span data-stu-id="55396-248">Column Name</span></span></th>
<th align="left"><span data-ttu-id="55396-249">描述</span><span class="sxs-lookup"><span data-stu-id="55396-249">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="55396-250">日期和时间</span><span class="sxs-lookup"><span data-stu-id="55396-250">Date and Time</span></span></p></td>
<td align="left"><p><span data-ttu-id="55396-251">对硬件类型进行更改的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="55396-251">Date and time that a change was made to the Hardware Type.</span></span> <span data-ttu-id="55396-252">请注意，每个唯一硬件类型都分配给至少一个条目。</span><span class="sxs-lookup"><span data-stu-id="55396-252">Note that every unique hardware type is assigned to at least one entry.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="55396-253">用户</span><span class="sxs-lookup"><span data-stu-id="55396-253">User</span></span></p></td>
<td align="left"><p><span data-ttu-id="55396-254">对特定条目进行更改的管理用户。</span><span class="sxs-lookup"><span data-stu-id="55396-254">Administrative user that has made the change for the particular entry.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="55396-255">更改类型</span><span class="sxs-lookup"><span data-stu-id="55396-255">Change Type</span></span></p></td>
<td align="left"><p><span data-ttu-id="55396-256">对硬件类型信息所做的更改的类型。</span><span class="sxs-lookup"><span data-stu-id="55396-256">Type of change that was made to the hardware type information.</span></span> <span data-ttu-id="55396-257">有效值为加法（新条目）、更新（更改现有条目）或删除（删除现有条目）。</span><span class="sxs-lookup"><span data-stu-id="55396-257">Valid values are Addition (new entry), Update (change existing entry), or Deletion (remove existing entry).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="55396-258">原始值</span><span class="sxs-lookup"><span data-stu-id="55396-258">Original Value</span></span></p></td>
<td align="left"><p><span data-ttu-id="55396-259">在进行更改之前硬件类型规范的值。</span><span class="sxs-lookup"><span data-stu-id="55396-259">Value of the hardware type specification before the change was made.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="55396-260">当前值</span><span class="sxs-lookup"><span data-stu-id="55396-260">Current Value</span></span></p></td>
<td align="left"><p><span data-ttu-id="55396-261">在进行更改后硬件类型规范的值。</span><span class="sxs-lookup"><span data-stu-id="55396-261">Value of the hardware type specification after the change was made.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="55396-262">恢复审核报告</span><span class="sxs-lookup"><span data-stu-id="55396-262">Recovery Audit Report</span></span>

<span data-ttu-id="55396-263">恢复审核报告可帮助你审核已请求恢复密钥访问权限的用户。</span><span class="sxs-lookup"><span data-stu-id="55396-263">The Recovery Audit Report can help you audit users who have requested access to recovery keys.</span></span> <span data-ttu-id="55396-264">此报告的筛选条件包括发出请求的用户类型、请求的密钥类型、发生时间、成功或失败、发生时间和用户请求类型（帮助桌面、最终用户）。</span><span class="sxs-lookup"><span data-stu-id="55396-264">The filter criteria for this report includes type of user making the request, type of key requested, time of occurrence, success or fail, time of occurrence, and type of user requesting (help desk, end user).</span></span> <span data-ttu-id="55396-265">此报表使管理员能够根据需要生成上下文报告。</span><span class="sxs-lookup"><span data-stu-id="55396-265">This report enables administrators to produce contextual reports based on need.</span></span>

**<span data-ttu-id="55396-266">恢复审核报告字段</span><span class="sxs-lookup"><span data-stu-id="55396-266">Recovery Audit Report Fields</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="55396-267">列名称</span><span class="sxs-lookup"><span data-stu-id="55396-267">Column Name</span></span></th>
<th align="left"><span data-ttu-id="55396-268">描述</span><span class="sxs-lookup"><span data-stu-id="55396-268">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="55396-269">请求日期和时间</span><span class="sxs-lookup"><span data-stu-id="55396-269">Request Date and Time</span></span></p></td>
<td align="left"><p><span data-ttu-id="55396-270">最终用户或技术支持用户发出密钥检索请求的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="55396-270">The date and time that a key retrieval request was made by an end user or help desk user.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="55396-271">请求状态</span><span class="sxs-lookup"><span data-stu-id="55396-271">Request Status</span></span></p></td>
<td align="left"><p><span data-ttu-id="55396-272">请求的状态。</span><span class="sxs-lookup"><span data-stu-id="55396-272">Status of the request.</span></span> <span data-ttu-id="55396-273">有效状态为 "成功" （已检索密钥）或 "失败" （未检索到密钥）。</span><span class="sxs-lookup"><span data-stu-id="55396-273">Valid statuses are either Successful (the key was retrieved) or Failed (the key was not retrieved).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="55396-274">帮助台用户</span><span class="sxs-lookup"><span data-stu-id="55396-274">Helpdesk User</span></span></p></td>
<td align="left"><p><span data-ttu-id="55396-275">启动了密钥检索请求的技术支持用户。</span><span class="sxs-lookup"><span data-stu-id="55396-275">The help desk user who initiated the request for key retrieval.</span></span> <span data-ttu-id="55396-276">如果技术支持用户代表最终用户检索密钥，则 "最终用户" 字段将为空。</span><span class="sxs-lookup"><span data-stu-id="55396-276">If the help desk user retrieves the key on behalf of an end user, the End User field will be blank.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="55396-277">用户</span><span class="sxs-lookup"><span data-stu-id="55396-277">User</span></span></p></td>
<td align="left"><p><span data-ttu-id="55396-278">启动密钥检索请求的最终用户。</span><span class="sxs-lookup"><span data-stu-id="55396-278">The end user who initiated the request for key retrieval.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="55396-279">键类型</span><span class="sxs-lookup"><span data-stu-id="55396-279">Key Type</span></span></p></td>
<td align="left"><p><span data-ttu-id="55396-280">所请求的键的类型。</span><span class="sxs-lookup"><span data-stu-id="55396-280">The type of key that was requested.</span></span> <span data-ttu-id="55396-281">MBAM 收集三种密钥类型：恢复密钥密码（恢复模式下恢复计算机）;恢复密钥 ID （代表另一个用户在恢复模式下恢复计算机）;和受信任的平台模块（TPM）密码哈希（使用已锁定的 TPM 恢复计算机）。</span><span class="sxs-lookup"><span data-stu-id="55396-281">MBAM collects three key types: Recovery Key Password (to recovery a computer in recovery mode); Recovery Key ID (to recover a computer in recovery mode on behalf of another user); and Trusted Platform Module (TPM) Password Hash (to recover a computer with a locked TPM).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="55396-282">原因描述</span><span class="sxs-lookup"><span data-stu-id="55396-282">Reason Description</span></span></p></td>
<td align="left"><p><span data-ttu-id="55396-283">请求指定键类型的原因。</span><span class="sxs-lookup"><span data-stu-id="55396-283">The reason that the specified Key Type was requested.</span></span> <span data-ttu-id="55396-284">原因在管理网站的驱动器恢复和管理 TPM 功能中指定。</span><span class="sxs-lookup"><span data-stu-id="55396-284">The reasons are specified in the Drive Recovery and Manage TPM features of the Administrative web site.</span></span> <span data-ttu-id="55396-285">有效条目包括用户输入的文本或以下原因代码之一：</span><span class="sxs-lookup"><span data-stu-id="55396-285">Valid entries include user-entered text or one of the following reason codes:</span></span></p>
<ul>
<li><p><span data-ttu-id="55396-286">操作系统启动顺序已更改</span><span class="sxs-lookup"><span data-stu-id="55396-286">Operating System Boot Order changed</span></span></p></li>
<li><p><span data-ttu-id="55396-287">BIOS 已更改</span><span class="sxs-lookup"><span data-stu-id="55396-287">BIOS changed</span></span></p></li>
<li><p><span data-ttu-id="55396-288">操作系统文件已更改</span><span class="sxs-lookup"><span data-stu-id="55396-288">Operating System files changed</span></span></p></li>
<li><p><span data-ttu-id="55396-289">已丢失启动密钥</span><span class="sxs-lookup"><span data-stu-id="55396-289">Lost Startup key</span></span></p></li>
<li><p><span data-ttu-id="55396-290">丢失的 PIN</span><span class="sxs-lookup"><span data-stu-id="55396-290">Lost PIN</span></span></p></li>
<li><p><span data-ttu-id="55396-291">TPM 重置</span><span class="sxs-lookup"><span data-stu-id="55396-291">TPM Reset</span></span></p></li>
<li><p><span data-ttu-id="55396-292">丢失密码</span><span class="sxs-lookup"><span data-stu-id="55396-292">Lost Passphrase</span></span></p></li>
<li><p><span data-ttu-id="55396-293">失去智能卡</span><span class="sxs-lookup"><span data-stu-id="55396-293">Lost Smartcard</span></span></p></li>
<li><p><span data-ttu-id="55396-294">重置 PIN 锁定</span><span class="sxs-lookup"><span data-stu-id="55396-294">Reset PIN lockout</span></span></p></li>
<li><p><span data-ttu-id="55396-295">打开 TPM</span><span class="sxs-lookup"><span data-stu-id="55396-295">Turn on TPM</span></span></p></li>
<li><p><span data-ttu-id="55396-296">关闭 TPM</span><span class="sxs-lookup"><span data-stu-id="55396-296">Turn off TPM</span></span></p></li>
<li><p><span data-ttu-id="55396-297">更改 TPM 密码</span><span class="sxs-lookup"><span data-stu-id="55396-297">Change TPM password</span></span></p></li>
<li><p><span data-ttu-id="55396-298">清除 TPM</span><span class="sxs-lookup"><span data-stu-id="55396-298">Clear TPM</span></span></p></li>
</ul>
<p></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="55396-299">**注意** 若要将报告结果保存到文件中，请单击 "报告" 菜单栏上的 "**导出**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="55396-299">**Note** To save report results to a file, click the **Export** button on the reports menu bar.</span></span>

 

## <span data-ttu-id="55396-300">相关主题</span><span class="sxs-lookup"><span data-stu-id="55396-300">Related topics</span></span>


[<span data-ttu-id="55396-301">使用 MBAM 1.0 监视和报告 BitLocker 符合性</span><span class="sxs-lookup"><span data-stu-id="55396-301">Monitoring and Reporting BitLocker Compliance with MBAM 1.0</span></span>](monitoring-and-reporting-bitlocker-compliance-with-mbam-10.md)

 

 





