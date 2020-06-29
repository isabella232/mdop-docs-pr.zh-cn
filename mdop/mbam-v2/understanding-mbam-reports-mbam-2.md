---
title: 了解 MBAM 报告
description: 了解 MBAM 报告
author: dansimp
ms.assetid: 8778f333-760e-4f26-acb4-4e73b6fbb536
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3c3ca5e4da4cbcea80c87520f0ecd05e1e7d6be0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803443"
---
# <span data-ttu-id="e5351-103">了解 MBAM 报告</span><span class="sxs-lookup"><span data-stu-id="e5351-103">Understanding MBAM Reports</span></span>


<span data-ttu-id="e5351-104">如果你在安装 Microsoft BitLocker 管理和监视（MBAM）时选择了独立拓扑，则可以在 MBAM 中运行不同的报告，以监视 BitLocker 使用情况和合规性。</span><span class="sxs-lookup"><span data-stu-id="e5351-104">If you chose the Stand-alone topology when you installed Microsoft BitLocker Administration and Monitoring (MBAM), you can run different reports in MBAM to monitor BitLocker usage and compliance.</span></span> <span data-ttu-id="e5351-105">MBAM 报告合规性以及它所管理的所有计算机和设备的其他信息。</span><span class="sxs-lookup"><span data-stu-id="e5351-105">MBAM reports compliance and other information about all of the computers and devices it manages.</span></span> <span data-ttu-id="e5351-106">本主题中的信息可用于帮助你了解适用于企业和个人计算机合规性以及密钥恢复活动的 Microsoft BitLocker 管理和监视报告。</span><span class="sxs-lookup"><span data-stu-id="e5351-106">The information in this topic can be used to help you understand the Microsoft BitLocker Administration and Monitoring reports for enterprise and individual computer compliance and for key recovery activity.</span></span>

<span data-ttu-id="e5351-107">**注意** 如果你在安装 Microsoft BitLocker 管理和监视（MBAM）时选择了 Configuration Manager 拓扑，则报告将从 Configuration Manager 生成，而不是从 MBAM。</span><span class="sxs-lookup"><span data-stu-id="e5351-107">**Note** If you chose the Configuration Manager topology when you installed Microsoft BitLocker Administration and Monitoring (MBAM), reports are generated from Configuration Manager rather than from MBAM.</span></span> <span data-ttu-id="e5351-108">有关从配置管理器运行的报表的详细信息，请参阅[了解配置管理器中的 MBAM 报表](understanding-mbam-reports-in-configuration-manager.md)。</span><span class="sxs-lookup"><span data-stu-id="e5351-108">For more information about reports that are run from Configuration Manager, see [Understanding MBAM Reports in Configuration Manager](understanding-mbam-reports-in-configuration-manager.md).</span></span>

 

## <span data-ttu-id="e5351-109">了解报表</span><span class="sxs-lookup"><span data-stu-id="e5351-109">Understanding Reports</span></span>


<span data-ttu-id="e5351-110">若要访问 Microsoft BitLocker 管理和监视的 "报表" 功能，请打开 web 浏览器并打开 "管理和监视" 网站。</span><span class="sxs-lookup"><span data-stu-id="e5351-110">To access the Reports feature of Microsoft BitLocker Administration and Monitoring, open a web browser and open the Administration and Monitoring website.</span></span> <span data-ttu-id="e5351-111">在左侧菜单栏中选择 "**报表**"，然后从顶部菜单栏中选择要生成的报表类型。</span><span class="sxs-lookup"><span data-stu-id="e5351-111">Select **Reports** in the left menu bar and then select from the top menu bar the kind of report that you want to generate.</span></span>

### <span data-ttu-id="e5351-112">企业合规性报告</span><span class="sxs-lookup"><span data-stu-id="e5351-112">Enterprise Compliance Report</span></span>

<span data-ttu-id="e5351-113">使用此报告类型可收集组织中的所有 BitLocker 合规性的信息。</span><span class="sxs-lookup"><span data-stu-id="e5351-113">Use this report type to collect information on overall BitLocker compliance in your organization.</span></span> <span data-ttu-id="e5351-114">你可以使用不同的筛选器将搜索结果缩小到合规性状态和错误状态。</span><span class="sxs-lookup"><span data-stu-id="e5351-114">You can use different filters to narrow your search results to Compliance state and Error status.</span></span> <span data-ttu-id="e5351-115">报表信息每6小时更新一次。</span><span class="sxs-lookup"><span data-stu-id="e5351-115">The report information is updated every six hours.</span></span>

**<span data-ttu-id="e5351-116">企业合规性报告字段</span><span class="sxs-lookup"><span data-stu-id="e5351-116">Enterprise Compliance Report Fields</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e5351-117">列名称</span><span class="sxs-lookup"><span data-stu-id="e5351-117">Column Name</span></span></th>
<th align="left"><span data-ttu-id="e5351-118">描述</span><span class="sxs-lookup"><span data-stu-id="e5351-118">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e5351-119">计算机名</span><span class="sxs-lookup"><span data-stu-id="e5351-119">Computer Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="e5351-120">由 MBAM 管理的用户指定的 DNS 名称。</span><span class="sxs-lookup"><span data-stu-id="e5351-120">User-specified DNS name that is being managed by MBAM.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e5351-121">域名</span><span class="sxs-lookup"><span data-stu-id="e5351-121">Domain Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="e5351-122">客户端计算机所在的完全限定的域名，由 MBAM 管理。</span><span class="sxs-lookup"><span data-stu-id="e5351-122">Fully qualified domain name where the client computer resides and is managed by MBAM.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e5351-123">合规性状态</span><span class="sxs-lookup"><span data-stu-id="e5351-123">Compliance Status</span></span></p></td>
<td align="left"><p><span data-ttu-id="e5351-124">根据为计算机指定的策略，对计算机合规的状态。</span><span class="sxs-lookup"><span data-stu-id="e5351-124">State of compliance for the computer, according to the policy specified for the computer.</span></span> <span data-ttu-id="e5351-125">状态是不相容的和合规的。</span><span class="sxs-lookup"><span data-stu-id="e5351-125">The states are Noncompliant and Compliant.</span></span> <span data-ttu-id="e5351-126">有关如何解释合规性状态的详细信息，请参阅企业合规性报告合规性状态表。</span><span class="sxs-lookup"><span data-stu-id="e5351-126">See the Enterprise Compliance Report Compliance States table for more information about how to interpret compliance states.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e5351-127">合规性状态详细信息</span><span class="sxs-lookup"><span data-stu-id="e5351-127">Compliance Status Details</span></span></p></td>
<td align="left"><p><span data-ttu-id="e5351-128">根据指定策略，计算机符合性状态的错误和状态消息。</span><span class="sxs-lookup"><span data-stu-id="e5351-128">Error and status messages of the compliance state of the computer in accordance to the policy specified.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e5351-129">上次联系人</span><span class="sxs-lookup"><span data-stu-id="e5351-129">Last Contact</span></span></p></td>
<td align="left"><p><span data-ttu-id="e5351-130">计算机上次联系服务器以报告合规性状态的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="e5351-130">Date and time when the computer last contacted the server to report compliance status.</span></span> <span data-ttu-id="e5351-131">可配置联系人频率（请参阅 MBAM 策略设置）。</span><span class="sxs-lookup"><span data-stu-id="e5351-131">The contact frequency is configurable (see MBAM policy settings).</span></span></p></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="e5351-132">企业合规性报告合规性状态</span><span class="sxs-lookup"><span data-stu-id="e5351-132">Enterprise Compliance Report Compliance States</span></span>**

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e5351-133">合规性状态</span><span class="sxs-lookup"><span data-stu-id="e5351-133">Compliance Status</span></span></th>
<th align="left"><span data-ttu-id="e5351-134">免除</span><span class="sxs-lookup"><span data-stu-id="e5351-134">Exemption</span></span></th>
<th align="left"><span data-ttu-id="e5351-135">描述</span><span class="sxs-lookup"><span data-stu-id="e5351-135">Description</span></span></th>
<th align="left"><span data-ttu-id="e5351-136">用户操作</span><span class="sxs-lookup"><span data-stu-id="e5351-136">User Action</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e5351-137">标准</span><span class="sxs-lookup"><span data-stu-id="e5351-137">Noncompliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="e5351-138">不豁免</span><span class="sxs-lookup"><span data-stu-id="e5351-138">Not Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="e5351-139">根据指定的策略，计算机不相容。</span><span class="sxs-lookup"><span data-stu-id="e5351-139">The computer is noncompliant, according to the specified policy.</span></span></p></td>
<td align="left"><p><span data-ttu-id="e5351-140">通过单击 "计算机名称" 展开 "计算机合规性报告详细信息" <strong> </strong> ，确定每个驱动器的状态是否符合指定的策略。</span><span class="sxs-lookup"><span data-stu-id="e5351-140">Expand the Computer Compliance Report details by clicking <strong>Computer Name</strong>, and determine whether the state of each drive complies with the specified policy.</span></span> <span data-ttu-id="e5351-141">如果加密状态指示计算机未加密，则可能正在进行加密，或者计算机上出现错误。</span><span class="sxs-lookup"><span data-stu-id="e5351-141">If the encryption state indicates that the computer is not encrypted, encryption may be in process, or there is an error on the computer.</span></span> <span data-ttu-id="e5351-142">如果没有错误，可能是因为计算机仍在连接或建立加密状态的过程中。</span><span class="sxs-lookup"><span data-stu-id="e5351-142">If there is no error, the likely cause is that the computer is still in the process of connecting or establishing the encryption status.</span></span> <span data-ttu-id="e5351-143">稍后再次查看以确定状态是否更改。</span><span class="sxs-lookup"><span data-stu-id="e5351-143">Check back later to determine if the state changes.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e5351-144">性</span><span class="sxs-lookup"><span data-stu-id="e5351-144">Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="e5351-145">不豁免</span><span class="sxs-lookup"><span data-stu-id="e5351-145">Not Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="e5351-146">根据指定的策略，计算机合规。</span><span class="sxs-lookup"><span data-stu-id="e5351-146">The computer is compliant, according to the specified policy.</span></span></p></td>
<td align="left"><p><span data-ttu-id="e5351-147">无需执行任何操作;可通过查看计算机合规性报告来确认计算机的状态。</span><span class="sxs-lookup"><span data-stu-id="e5351-147">No action needed; the state of the computer can be confirmed by viewing the Computer Compliance Report.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="e5351-148">计算机合规性报告</span><span class="sxs-lookup"><span data-stu-id="e5351-148">Computer Compliance Report</span></span>

<span data-ttu-id="e5351-149">使用此报告类型可收集特定于计算机或用户的信息。</span><span class="sxs-lookup"><span data-stu-id="e5351-149">Use this report type to collect information that is specific to a computer or user.</span></span>

<span data-ttu-id="e5351-150">通过在企业合规性报告中单击计算机名称，或在计算机合规性报告中键入计算机名称，可查看此报告。</span><span class="sxs-lookup"><span data-stu-id="e5351-150">This report can be viewed by clicking the computer name in the Enterprise Compliance Report, or by typing the computer name in the Computer Compliance Report.</span></span> <span data-ttu-id="e5351-151">计算机合规性报告提供有关计算机上每个驱动器（操作系统和固定数据驱动器）的详细加密信息，以及应用于计算机上每个驱动器类型的策略的指示。</span><span class="sxs-lookup"><span data-stu-id="e5351-151">The Computer Compliance Report provides detailed encryption information about each drive (operating system and fixed data drives) on a computer, and also an indication of the policy that is applied to each drive type on the computer.</span></span> <span data-ttu-id="e5351-152">若要查看每个驱动器的详细信息，请展开 "计算机名称" 条目。</span><span class="sxs-lookup"><span data-stu-id="e5351-152">To view the details of each drive, expand the Computer Name entry.</span></span>

<span data-ttu-id="e5351-153">**注意** 可移动数据卷加密状态将不会显示在报告中。</span><span class="sxs-lookup"><span data-stu-id="e5351-153">**Note** Removable Data Volume encryption status will not be shown in the report.</span></span>

 

**<span data-ttu-id="e5351-154">计算机合规性报告字段</span><span class="sxs-lookup"><span data-stu-id="e5351-154">Computer Compliance Report Fields</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e5351-155">列名称</span><span class="sxs-lookup"><span data-stu-id="e5351-155">Column Name</span></span></th>
<th align="left"><span data-ttu-id="e5351-156">描述</span><span class="sxs-lookup"><span data-stu-id="e5351-156">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e5351-157">计算机名</span><span class="sxs-lookup"><span data-stu-id="e5351-157">Computer Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="e5351-158">由 MBAM 管理的用户指定的 DNS 计算机名。</span><span class="sxs-lookup"><span data-stu-id="e5351-158">User-specified DNS computer name that is being managed by MBAM.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e5351-159">域名</span><span class="sxs-lookup"><span data-stu-id="e5351-159">Domain Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="e5351-160">客户端计算机所在的完全限定的域名，由 MBAM 管理。</span><span class="sxs-lookup"><span data-stu-id="e5351-160">Fully qualified domain name, where the client computer resides and is managed by MBAM.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e5351-161">计算机类型</span><span class="sxs-lookup"><span data-stu-id="e5351-161">Computer Type</span></span></p></td>
<td align="left"><p><span data-ttu-id="e5351-162">计算机的类型。</span><span class="sxs-lookup"><span data-stu-id="e5351-162">Type of computer.</span></span> <span data-ttu-id="e5351-163">有效类型为非便携式和可移植。</span><span class="sxs-lookup"><span data-stu-id="e5351-163">Valid types are non-Portable and Portable.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e5351-164">操作系统</span><span class="sxs-lookup"><span data-stu-id="e5351-164">Operating System</span></span></p></td>
<td align="left"><p><span data-ttu-id="e5351-165">在 MBAM 管理的客户端计算机上找到的操作系统类型。</span><span class="sxs-lookup"><span data-stu-id="e5351-165">Operating system type found on the MBAM-managed client computer.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e5351-166">合规性状态</span><span class="sxs-lookup"><span data-stu-id="e5351-166">Compliance Status</span></span></p></td>
<td align="left"><p><span data-ttu-id="e5351-167">由 MBAM 管理的计算机的整体合规性状态。</span><span class="sxs-lookup"><span data-stu-id="e5351-167">Overall compliance status of the computer managed by MBAM.</span></span> <span data-ttu-id="e5351-168">有效状态符合和不相容。</span><span class="sxs-lookup"><span data-stu-id="e5351-168">Valid states are Compliant and Noncompliant.</span></span> <span data-ttu-id="e5351-169">请注意，每个驱动器的合规性状态（请参阅下表）可能指示不同的合规性状态。</span><span class="sxs-lookup"><span data-stu-id="e5351-169">Notice that the compliance status per drive (see the following table) may indicate different compliance states.</span></span> <span data-ttu-id="e5351-170">但是，此字段根据指定的策略表示符合性状态。</span><span class="sxs-lookup"><span data-stu-id="e5351-170">However, this field represents that compliance state, according to the specified policy.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e5351-171">策略密码强度</span><span class="sxs-lookup"><span data-stu-id="e5351-171">Policy Cipher Strength</span></span></p></td>
<td align="left"><p><span data-ttu-id="e5351-172">MBAM 策略规范期间管理员选择的密码长度（例如，使用扩散器的128位）。</span><span class="sxs-lookup"><span data-stu-id="e5351-172">Cipher strength selected by the administrator during MBAM policy specification (for example, 128-bit with Diffuser).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e5351-173">策略操作系统驱动器</span><span class="sxs-lookup"><span data-stu-id="e5351-173">Policy Operating System Drive</span></span></p></td>
<td align="left"><p><span data-ttu-id="e5351-174">指示操作系统是否需要加密，并显示相应的保护器类型。</span><span class="sxs-lookup"><span data-stu-id="e5351-174">Indicates if encryption is required for the operating system and shows the appropriate protector type.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e5351-175">策略-固定数据驱动器</span><span class="sxs-lookup"><span data-stu-id="e5351-175">Policy-Fixed Data Drive</span></span></p></td>
<td align="left"><p><span data-ttu-id="e5351-176">指示固定数据驱动器是否需要加密。</span><span class="sxs-lookup"><span data-stu-id="e5351-176">Indicates if encryption is required for the fixed data drive.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e5351-177">策略可移动数据驱动器</span><span class="sxs-lookup"><span data-stu-id="e5351-177">Policy Removable Data Drive</span></span></p></td>
<td align="left"><p><span data-ttu-id="e5351-178">指示可移动驱动器是否需要加密。</span><span class="sxs-lookup"><span data-stu-id="e5351-178">Indicates if encryption is required for the removable drive.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e5351-179">设备用户</span><span class="sxs-lookup"><span data-stu-id="e5351-179">Device Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="e5351-180">由 MBAM 管理的计算机上的已知用户。</span><span class="sxs-lookup"><span data-stu-id="e5351-180">Known users on the computer that is being managed by MBAM.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e5351-181">制造商</span><span class="sxs-lookup"><span data-stu-id="e5351-181">Manufacturer</span></span></p></td>
<td align="left"><p><span data-ttu-id="e5351-182">计算机制造商名称，它显示在计算机 BIOS 中。</span><span class="sxs-lookup"><span data-stu-id="e5351-182">Computer manufacturer name, as it appears in the computer BIOS.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e5351-183">型号</span><span class="sxs-lookup"><span data-stu-id="e5351-183">Model</span></span></p></td>
<td align="left"><p><span data-ttu-id="e5351-184">计算机制造商模型名称，它显示在计算机 BIOS 中。</span><span class="sxs-lookup"><span data-stu-id="e5351-184">Computer manufacturer model name, as it appears in the computer BIOS.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e5351-185">合规性状态详细信息</span><span class="sxs-lookup"><span data-stu-id="e5351-185">Compliance Status Details</span></span></p></td>
<td align="left"><p><span data-ttu-id="e5351-186">根据指定的策略，对计算机合规性状态的错误和状态消息。</span><span class="sxs-lookup"><span data-stu-id="e5351-186">Error and status messages of the compliance state of the computer, in accordance with the specified policy.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e5351-187">上次联系人</span><span class="sxs-lookup"><span data-stu-id="e5351-187">Last Contact</span></span></p></td>
<td align="left"><p><span data-ttu-id="e5351-188">计算机上次联系服务器以报告合规性状态的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="e5351-188">Date and time that the computer last contacted the server to report compliance status.</span></span> <span data-ttu-id="e5351-189">可配置联系人频率（请参阅 MBAM 策略设置）。</span><span class="sxs-lookup"><span data-stu-id="e5351-189">The contact frequency is configurable (see MBAM policy settings).</span></span></p></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="e5351-190">计算机合规性报告驱动器字段</span><span class="sxs-lookup"><span data-stu-id="e5351-190">Computer Compliance Report Drive Fields</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e5351-191">列名称</span><span class="sxs-lookup"><span data-stu-id="e5351-191">Column Name</span></span></th>
<th align="left"><span data-ttu-id="e5351-192">描述</span><span class="sxs-lookup"><span data-stu-id="e5351-192">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e5351-193">驱动器号</span><span class="sxs-lookup"><span data-stu-id="e5351-193">Drive Letter</span></span></p></td>
<td align="left"><p><span data-ttu-id="e5351-194">用户分配给特定驱动器的计算机驱动器号。</span><span class="sxs-lookup"><span data-stu-id="e5351-194">Computer drive letter that was assigned to the particular drive by the user.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e5351-195">驱动器类型</span><span class="sxs-lookup"><span data-stu-id="e5351-195">Drive Type</span></span></p></td>
<td align="left"><p><span data-ttu-id="e5351-196">驱动器的类型。</span><span class="sxs-lookup"><span data-stu-id="e5351-196">Type of drive.</span></span> <span data-ttu-id="e5351-197">有效值为操作系统驱动器和固定数据驱动器。</span><span class="sxs-lookup"><span data-stu-id="e5351-197">Valid values are Operating System Drive and Fixed Data Drive.</span></span> <span data-ttu-id="e5351-198">这些驱动器是物理驱动器，而不是逻辑卷。</span><span class="sxs-lookup"><span data-stu-id="e5351-198">These are physical drives rather than logical volumes.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e5351-199">密码强度</span><span class="sxs-lookup"><span data-stu-id="e5351-199">Cipher Strength</span></span></p></td>
<td align="left"><p><span data-ttu-id="e5351-200">MBAM 策略规范期间管理员选择的密码长度。</span><span class="sxs-lookup"><span data-stu-id="e5351-200">Cipher strength selected by the administrator during MBAM policy specification.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e5351-201">保护器类型</span><span class="sxs-lookup"><span data-stu-id="e5351-201">Protector Type</span></span></p></td>
<td align="left"><p><span data-ttu-id="e5351-202">通过用于加密操作系统或固定数据卷的策略选择的保护程序类型。</span><span class="sxs-lookup"><span data-stu-id="e5351-202">Type of protector selected via the policy used to encrypt an operating system or fixed data volume.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e5351-203">保护程序状态</span><span class="sxs-lookup"><span data-stu-id="e5351-203">Protector State</span></span></p></td>
<td align="left"><p><span data-ttu-id="e5351-204">指示由 MBAM 托管的计算机已启用在策略中指定的保护程序类型。</span><span class="sxs-lookup"><span data-stu-id="e5351-204">Indicates that the computer being managed by MBAM has enabled the protector type that is specified in the policy.</span></span> <span data-ttu-id="e5351-205">有效状态为 "开" 或 "关"。</span><span class="sxs-lookup"><span data-stu-id="e5351-205">The valid states are ON or OFF.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e5351-206">加密状态</span><span class="sxs-lookup"><span data-stu-id="e5351-206">Encryption State</span></span></p></td>
<td align="left"><p><span data-ttu-id="e5351-207">驱动器的加密状态。</span><span class="sxs-lookup"><span data-stu-id="e5351-207">Encryption state of the drive.</span></span> <span data-ttu-id="e5351-208">有效状态为加密、未加密和加密。</span><span class="sxs-lookup"><span data-stu-id="e5351-208">Valid states are Encrypted, Not Encrypted, and Encrypting.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e5351-209">合规性状态</span><span class="sxs-lookup"><span data-stu-id="e5351-209">Compliance Status</span></span></p></td>
<td align="left"><p><span data-ttu-id="e5351-210">指示驱动器是否符合策略的状态。</span><span class="sxs-lookup"><span data-stu-id="e5351-210">State that indicates whether the drive is in accordance with the policy.</span></span> <span data-ttu-id="e5351-211">状态是不相容的和合规的。</span><span class="sxs-lookup"><span data-stu-id="e5351-211">States are Noncompliant and Compliant.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e5351-212">合规性状态详细信息</span><span class="sxs-lookup"><span data-stu-id="e5351-212">Compliance Status Details</span></span></p></td>
<td align="left"><p><span data-ttu-id="e5351-213">根据指定的策略，对计算机合规性状态的错误和状态消息。</span><span class="sxs-lookup"><span data-stu-id="e5351-213">Error and status messages of the compliance state of the computer, according to the specified policy.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="e5351-214">恢复审核报告</span><span class="sxs-lookup"><span data-stu-id="e5351-214">Recovery Audit Report</span></span>

<span data-ttu-id="e5351-215">使用此报告类型审核请求了恢复密钥访问权限的用户。</span><span class="sxs-lookup"><span data-stu-id="e5351-215">Use this report type to audit users who have requested access to recovery keys.</span></span> <span data-ttu-id="e5351-216">该报表基于所需的筛选条件提供了多个筛选器。</span><span class="sxs-lookup"><span data-stu-id="e5351-216">The report offers several filters based on the desired filtering criteria.</span></span> <span data-ttu-id="e5351-217">用户可以筛选特定类型的用户，无论是帮助台用户还是最终用户、请求失败还是成功、所请求的特定类型的密钥以及发生检索的日期范围。</span><span class="sxs-lookup"><span data-stu-id="e5351-217">Users can filter on a specific type of user, either a Help Desk user or an end user, whether the request failed or was successful, the specific type of key requested, and a date range during which the retrieval occurred.</span></span> <span data-ttu-id="e5351-218">管理员可以根据需要生成上下文报告。</span><span class="sxs-lookup"><span data-stu-id="e5351-218">The administrator can produce contextual reports based on need.</span></span>

**<span data-ttu-id="e5351-219">恢复审核报告字段</span><span class="sxs-lookup"><span data-stu-id="e5351-219">Recovery Audit Report Fields</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e5351-220">列名称</span><span class="sxs-lookup"><span data-stu-id="e5351-220">Column Name</span></span></th>
<th align="left"><span data-ttu-id="e5351-221">描述</span><span class="sxs-lookup"><span data-stu-id="e5351-221">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e5351-222">请求日期和时间</span><span class="sxs-lookup"><span data-stu-id="e5351-222">Request Date and Time</span></span></p></td>
<td align="left"><p><span data-ttu-id="e5351-223">最终用户或技术支持用户进行密钥检索请求的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="e5351-223">Date and time that a key retrieval request was made by an end user or Help Desk user.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e5351-224">请求状态</span><span class="sxs-lookup"><span data-stu-id="e5351-224">Request Status</span></span></p></td>
<td align="left"><p><span data-ttu-id="e5351-225">请求的状态。</span><span class="sxs-lookup"><span data-stu-id="e5351-225">Status of the request.</span></span> <span data-ttu-id="e5351-226">有效状态为 "成功" （已检索密钥）或 "失败" （未检索到密钥）。</span><span class="sxs-lookup"><span data-stu-id="e5351-226">Valid statuses are either Successful (the key was retrieved), or Failed (the key was not retrieved).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e5351-227">帮助台用户</span><span class="sxs-lookup"><span data-stu-id="e5351-227">Helpdesk User</span></span></p></td>
<td align="left"><p><span data-ttu-id="e5351-228">启动了密钥检索请求的技术支持用户。</span><span class="sxs-lookup"><span data-stu-id="e5351-228">Help Desk user that initiated the request for key retrieval.</span></span> <span data-ttu-id="e5351-229">注意：如果技术支持用户代表最终用户检索密钥，则 "最终用户" 字段将为空。</span><span class="sxs-lookup"><span data-stu-id="e5351-229">Note: If the Help Desk user retrieves the key on behalf on an end-user, the End User field will be blank.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e5351-230">用户</span><span class="sxs-lookup"><span data-stu-id="e5351-230">User</span></span></p></td>
<td align="left"><p><span data-ttu-id="e5351-231">启动密钥检索请求的最终用户。</span><span class="sxs-lookup"><span data-stu-id="e5351-231">End user who initiated the request for key retrieval.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e5351-232">键类型</span><span class="sxs-lookup"><span data-stu-id="e5351-232">Key Type</span></span></p></td>
<td align="left"><p><span data-ttu-id="e5351-233">技术支持用户或最终用户请求的键类型。</span><span class="sxs-lookup"><span data-stu-id="e5351-233">Type of key that was requested by either the Help Desk user or the end user.</span></span> <span data-ttu-id="e5351-234">MBAM 收集的三种密钥类型为：恢复密钥密码（用于在恢复模式下恢复计算机）、恢复密钥 ID （用于在恢复模式中代表另一个用户恢复计算机）和 TPM 密码哈希（用于使用已锁定的 TPM 恢复计算机）。</span><span class="sxs-lookup"><span data-stu-id="e5351-234">The three types of keys that MBAM collects are: Recovery Key Password (used to recovery a computer in recovery mode), Recovery Key ID (used to recover a computer in recovery mode on behalf of another user), and TPM Password Hash (used to recover a computer with a locked TPM).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e5351-235">原因描述</span><span class="sxs-lookup"><span data-stu-id="e5351-235">Reason Description</span></span></p></td>
<td align="left"><p><span data-ttu-id="e5351-236">由技术支持用户或最终用户请求指定的键类型的原因。</span><span class="sxs-lookup"><span data-stu-id="e5351-236">Reason the specified Key Type was requested by the Help Desk user or the end user.</span></span> <span data-ttu-id="e5351-237">原因在 "驱动器恢复" 和 "管理管理和监视网站的 TPM" 功能中指定。</span><span class="sxs-lookup"><span data-stu-id="e5351-237">The reasons are specified in the Drive Recovery and Manage TPM features of the Administration and Monitoring website.</span></span> <span data-ttu-id="e5351-238">有效的条目是用户输入的文本，或者是以下原因代码之一：</span><span class="sxs-lookup"><span data-stu-id="e5351-238">The valid entries are either user-entered text, or one of the following reason codes:</span></span></p>
<ul>
<li><p><span data-ttu-id="e5351-239">操作系统启动顺序已更改</span><span class="sxs-lookup"><span data-stu-id="e5351-239">Operating System Boot Order changed</span></span></p></li>
<li><p><span data-ttu-id="e5351-240">BIOS 已更改</span><span class="sxs-lookup"><span data-stu-id="e5351-240">BIOS Changed</span></span></p></li>
<li><p><span data-ttu-id="e5351-241">操作系统文件已更改</span><span class="sxs-lookup"><span data-stu-id="e5351-241">Operating System files changed</span></span></p></li>
<li><p><span data-ttu-id="e5351-242">已丢失启动密钥</span><span class="sxs-lookup"><span data-stu-id="e5351-242">Lost Startup key</span></span></p></li>
<li><p><span data-ttu-id="e5351-243">丢失的 PIN</span><span class="sxs-lookup"><span data-stu-id="e5351-243">Lost PIN</span></span></p></li>
<li><p><span data-ttu-id="e5351-244">TPM 重置</span><span class="sxs-lookup"><span data-stu-id="e5351-244">TPM Reset</span></span></p></li>
<li><p><span data-ttu-id="e5351-245">丢失密码</span><span class="sxs-lookup"><span data-stu-id="e5351-245">Lost Passphrase</span></span></p></li>
<li><p><span data-ttu-id="e5351-246">失去智能卡</span><span class="sxs-lookup"><span data-stu-id="e5351-246">Lost Smartcard</span></span></p></li>
<li><p><span data-ttu-id="e5351-247">重置 PIN 锁定</span><span class="sxs-lookup"><span data-stu-id="e5351-247">Reset PIN lockout</span></span></p></li>
<li><p><span data-ttu-id="e5351-248">打开 TPM</span><span class="sxs-lookup"><span data-stu-id="e5351-248">Turn on TPM</span></span></p></li>
<li><p><span data-ttu-id="e5351-249">关闭 TPM</span><span class="sxs-lookup"><span data-stu-id="e5351-249">Turn off TPM</span></span></p></li>
<li><p><span data-ttu-id="e5351-250">更改 TPM 密码</span><span class="sxs-lookup"><span data-stu-id="e5351-250">Change TPM password</span></span></p></li>
<li><p><span data-ttu-id="e5351-251">清除 TPM</span><span class="sxs-lookup"><span data-stu-id="e5351-251">Clear TPM</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="e5351-252">**注意** 通过单击 "报表" 菜单栏上的 "**导出**" 按钮，可将报表结果保存到文件中。</span><span class="sxs-lookup"><span data-stu-id="e5351-252">**Note** Report results can be saved to a file by clicking the **Export** button on the reports menu bar.</span></span> <span data-ttu-id="e5351-253">有关如何运行 MBAM 报表的详细信息，请参阅[如何生成 MBAM 报表](how-to-generate-mbam-reports-mbam-2.md)。</span><span class="sxs-lookup"><span data-stu-id="e5351-253">For more information about how to run MBAM reports, see [How to Generate MBAM Reports](how-to-generate-mbam-reports-mbam-2.md).</span></span>

 

## <span data-ttu-id="e5351-254">相关主题</span><span class="sxs-lookup"><span data-stu-id="e5351-254">Related topics</span></span>


[<span data-ttu-id="e5351-255">使用 MBAM 2.0 监视和报告 BitLocker 符合性</span><span class="sxs-lookup"><span data-stu-id="e5351-255">Monitoring and Reporting BitLocker Compliance with MBAM 2.0</span></span>](monitoring-and-reporting-bitlocker-compliance-with-mbam-20-mbam-2.md)

 

 





