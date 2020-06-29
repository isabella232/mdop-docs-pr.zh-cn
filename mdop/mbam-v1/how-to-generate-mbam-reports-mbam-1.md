---
title: 如何生成 MBAM 报告
description: 如何生成 MBAM 报告
author: dansimp
ms.assetid: cdf4ae76-040c-447c-8736-c9e57068d221
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7f0b5a4e984d7a609eab7204e67f46042992f586
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803586"
---
# <span data-ttu-id="65c81-103">如何生成 MBAM 报告</span><span class="sxs-lookup"><span data-stu-id="65c81-103">How to Generate MBAM Reports</span></span>


<span data-ttu-id="65c81-104">Microsoft BitLocker 管理和监视（MBAM）生成各种报告以监控 BitLocker 加密的使用情况和合规性。</span><span class="sxs-lookup"><span data-stu-id="65c81-104">Microsoft BitLocker Administration and Monitoring (MBAM) generates various reports to monitor BitLocker encryption usage and compliance.</span></span> <span data-ttu-id="65c81-105">本主题介绍了如何打开 MBAM 管理网站以及如何生成有关企业合规性、单独计算机、硬件兼容性和密钥恢复活动的 MBAM 报告。</span><span class="sxs-lookup"><span data-stu-id="65c81-105">This topic describes how to open the MBAM administration website and how to generate MBAM reports on enterprise compliance, individual computers, hardware compatibility, and key recovery activity.</span></span> <span data-ttu-id="65c81-106">有关 MBAM 报表的详细信息，请参阅[了解 MBAM 报表](understanding-mbam-reports-mbam-1.md)。</span><span class="sxs-lookup"><span data-stu-id="65c81-106">For more information about MBAM reports, see [Understanding MBAM Reports](understanding-mbam-reports-mbam-1.md).</span></span>

<span data-ttu-id="65c81-107">**注意** 若要运行报表，您必须是已安装管理和监视服务器功能、合规性和审核数据库以及合规性和审核报告的计算机上的**报表用户**角色的成员。</span><span class="sxs-lookup"><span data-stu-id="65c81-107">**Note** To run the reports, you must be a member of the **Report Users** role on the computers where you have installed the Administration and Monitoring Server features, Compliance and Audit Database, and Compliance and Audit Reports.</span></span>

 

**<span data-ttu-id="65c81-108">打开 MBAM 管理网站</span><span class="sxs-lookup"><span data-stu-id="65c81-108">To open the MBAM Administration website</span></span>**

1.  <span data-ttu-id="65c81-109">打开 web 浏览器并导航到 MBAM 网站。</span><span class="sxs-lookup"><span data-stu-id="65c81-109">Open a web browser and navigate to the MBAM website.</span></span> <span data-ttu-id="65c81-110">网站的默认 URL 是 Microsoft BitLocker 管理和监视服务器的\*http:// &lt; computername &gt; \* 。</span><span class="sxs-lookup"><span data-stu-id="65c81-110">The default URL for the website is *http://&lt;computername&gt;* of the Microsoft BitLocker Administration and Monitoring server.</span></span>

    <span data-ttu-id="65c81-111">**注意** 如果 MBAMadministration 网站安装在除端口80之外的其他端口上，则必须在 URL 中指定该端口号。</span><span class="sxs-lookup"><span data-stu-id="65c81-111">**Note** If the MBAMadministration website was installed on a port other than port 80, you must specify that port number in the URL.</span></span> <span data-ttu-id="65c81-112">例如， \*http:// &lt; computername &gt; ： &lt; port &gt; \*。</span><span class="sxs-lookup"><span data-stu-id="65c81-112">For example, *http://&lt;computername&gt;:&lt;port&gt;*.</span></span> <span data-ttu-id="65c81-113">如果在安装期间为 MBAMadministration 网站指定了一个主机名，URL 将为\*http:// &lt; 主机 &gt; \*名。</span><span class="sxs-lookup"><span data-stu-id="65c81-113">If you specified a Host Name for the MBAMadministration website during the installation, the URL would be *http://&lt;hostname&gt;*.</span></span>

     

2.  <span data-ttu-id="65c81-114">在导航窗格中，单击 "**报表**"。</span><span class="sxs-lookup"><span data-stu-id="65c81-114">In the navigation pane, click **Reports**.</span></span> <span data-ttu-id="65c81-115">在主窗格中，单击报表类型的选项卡：**企业合规性报告**、**计算机合规性报告**、**硬件审核报告**或**恢复审核报告**。</span><span class="sxs-lookup"><span data-stu-id="65c81-115">In the main pane, click the tab for your report type: **Enterprise Compliance Report**, **Computer Compliance Report**, **Hardware Audit Report**, or **Recovery Audit Report**.</span></span>

    <span data-ttu-id="65c81-116">**注意** 历史 MBAM 客户端数据保留在合规性数据库中。</span><span class="sxs-lookup"><span data-stu-id="65c81-116">**Note** Historical MBAM Client data is retained in the compliance database.</span></span> <span data-ttu-id="65c81-117">如果计算机丢失或被盗，可能需要这些保留的数据。</span><span class="sxs-lookup"><span data-stu-id="65c81-117">This retained data may be needed in case a computer is lost or stolen.</span></span> <span data-ttu-id="65c81-118">运行企业报表时，应使用相应的开始和结束日期将报表的时间范围从一到两周范围范围内，以增加报告数据的准确性。</span><span class="sxs-lookup"><span data-stu-id="65c81-118">When running enterprise reports, you should use appropriate start and end dates to scope the time frames for the reports from one to two weeks to increase the reporting data accuracy.</span></span>

     

**<span data-ttu-id="65c81-119">生成企业合规性报告</span><span class="sxs-lookup"><span data-stu-id="65c81-119">To generate an enterprise Compliance Report</span></span>**

1.  <span data-ttu-id="65c81-120">在 MBAMadministration 网站上，单击导航窗格中的 "**报表**"，然后单击 "**企业合规性报告**" 选项卡，为报表选择相应的筛选器。</span><span class="sxs-lookup"><span data-stu-id="65c81-120">On the MBAMadministration website, click **Reports** in the navigation pane, then click the **Enterprise Compliance Report** tab and select the appropriate filters for your report.</span></span> <span data-ttu-id="65c81-121">对于企业合规性报告，你可以设置以下筛选器。</span><span class="sxs-lookup"><span data-stu-id="65c81-121">For the Enterprise Compliance Report, you can set the following filters.</span></span>

    -   <span data-ttu-id="65c81-122">**合规性状态**。</span><span class="sxs-lookup"><span data-stu-id="65c81-122">**Compliance Status**.</span></span> <span data-ttu-id="65c81-123">使用此筛选器指定要包括在报表中的合规性状态类型（例如，合规性或不符合）。</span><span class="sxs-lookup"><span data-stu-id="65c81-123">Use this filter to specify the compliance status types (for example, Compliant or Noncompliant) to include in the report.</span></span>

    -   <span data-ttu-id="65c81-124">**错误状态**。</span><span class="sxs-lookup"><span data-stu-id="65c81-124">**Error State**.</span></span> <span data-ttu-id="65c81-125">使用此筛选器指定要包含在报表中的错误状态类型，如 "无错误" 或 "错误"。</span><span class="sxs-lookup"><span data-stu-id="65c81-125">Use this filter to specify the Error State types, such as No Error or Error, to include in the report.</span></span>

2.  <span data-ttu-id="65c81-126">单击 "**查看报表**" 以显示指定的报表。</span><span class="sxs-lookup"><span data-stu-id="65c81-126">Click **View Report** to display the specified report.</span></span>

    <span data-ttu-id="65c81-127">可以使用多种可用文件格式（如 HTML、Microsoft Word 和 Microsoft Excel）保存报表结果。</span><span class="sxs-lookup"><span data-stu-id="65c81-127">The report results can be saved in any of several available file formats such as HTML, Microsoft Word, and Microsoft Excel.</span></span>

    <span data-ttu-id="65c81-128">**注意** 企业合规性报告由每6个小时运行的 SQL 作业生成。</span><span class="sxs-lookup"><span data-stu-id="65c81-128">**Note** The Enterprise Compliance report is generated by a SQL job that runs every six hours.</span></span> <span data-ttu-id="65c81-129">因此，第一次尝试查看报表时，您可能会发现某些数据丢失。</span><span class="sxs-lookup"><span data-stu-id="65c81-129">Therefore, the first time you try to view the report you may find that some data is missing.</span></span>

     

3.  <span data-ttu-id="65c81-130">若要查看计算机合规性报告中有关计算机的信息，请选择计算机名称。</span><span class="sxs-lookup"><span data-stu-id="65c81-130">To view information about a computer in the Computer Compliance Report, select the computer name.</span></span>

4.  <span data-ttu-id="65c81-131">选择计算机名称旁边的加号（+）以查看有关计算机上的卷的信息。</span><span class="sxs-lookup"><span data-stu-id="65c81-131">Select the plus sign (+) next to the computer name to view information about the volumes on the computer.</span></span>

**<span data-ttu-id="65c81-132">生成计算机合规性报告</span><span class="sxs-lookup"><span data-stu-id="65c81-132">To generate the Computer Compliance Report</span></span>**

1.  <span data-ttu-id="65c81-133">在 MBAMadministration 网站中，在导航窗格中选择 "**报表**" 节点，然后选择 "**计算机合规性报告**"。</span><span class="sxs-lookup"><span data-stu-id="65c81-133">In the MBAMadministration website, select the **Report** node in the navigation pane, and then select the **Computer Compliance Report**.</span></span> <span data-ttu-id="65c81-134">使用 "计算机合规性报告" 搜索**用户名**或**计算机名称**。</span><span class="sxs-lookup"><span data-stu-id="65c81-134">Use the Computer Compliance report to search for **user name** or **computer name**.</span></span>

2.  <span data-ttu-id="65c81-135">单击 "**查看报表**" 以查看计算机报告。</span><span class="sxs-lookup"><span data-stu-id="65c81-135">Click **View Report** to view the computer report.</span></span>

    <span data-ttu-id="65c81-136">可使用多种可用文件格式（如 HTML、Microsoft Word 和 Microsoft Excel）保存结果。</span><span class="sxs-lookup"><span data-stu-id="65c81-136">Results can be saved in any of several available file formats such as HTML, Microsoft Word, and Microsoft Excel.</span></span>

3.  <span data-ttu-id="65c81-137">若要在计算机合规性报告中显示有关计算机的详细信息，请选择计算机名称。</span><span class="sxs-lookup"><span data-stu-id="65c81-137">To display more information about a computer in the Computer Compliance Report, select the computer name.</span></span>

4.  <span data-ttu-id="65c81-138">选择计算机名称旁边的加号（+）以查看有关计算机上的卷的信息。</span><span class="sxs-lookup"><span data-stu-id="65c81-138">Select the plus sign (+) next to the computer name to view information about the volumes on the computer.</span></span>

    <span data-ttu-id="65c81-139">**注意** 如果计算机满足 MBAM 策略设置的要求，或者计算机的硬件模型设置为不兼容，MBAM 客户端计算机将视为合规性。</span><span class="sxs-lookup"><span data-stu-id="65c81-139">**Note** An MBAM Client computer is considered compliant if the computer matches the requirements of the MBAM policy settings or the computer’s hardware model is set to incompatible.</span></span> <span data-ttu-id="65c81-140">因此，当你查看与计算机相关联的磁盘卷的详细信息时，由于设备的驱动器卷加密状态显示为不符合规则，因此不受硬件兼容性阻止 BitLocker 加密的计算机也会显示为合规。</span><span class="sxs-lookup"><span data-stu-id="65c81-140">Therefore, when you are viewing detailed information about the disk volumes associated with the computer, computers that are exempt from BitLocker encryption due to hardware compatibility can be displayed as compliant even though their drive volume encryption status is displayed as noncompliant.</span></span>

     

**<span data-ttu-id="65c81-141">生成硬件兼容性审核报告</span><span class="sxs-lookup"><span data-stu-id="65c81-141">To generate the Hardware Compatibility Audit Report</span></span>**

1.  <span data-ttu-id="65c81-142">从 MBAMadministration 网站上，从导航窗格中选择 "**报表**" 节点，然后选择 "**硬件审核报表**"。</span><span class="sxs-lookup"><span data-stu-id="65c81-142">From the MBAMadministration website, select the **Report** node from the navigation pane, and then select the **Hardware Audit Report**.</span></span> <span data-ttu-id="65c81-143">为你的硬件审核报告选择相应的筛选器。</span><span class="sxs-lookup"><span data-stu-id="65c81-143">Select the appropriate filters for your Hardware Audit report.</span></span> <span data-ttu-id="65c81-144">硬件审核报告提供以下可用筛选器：</span><span class="sxs-lookup"><span data-stu-id="65c81-144">The Hardware Audit report offers the following available filters:</span></span>

    -   <span data-ttu-id="65c81-145">**User （Domain\\User）**。</span><span class="sxs-lookup"><span data-stu-id="65c81-145">**User (Domain\\User)**.</span></span> <span data-ttu-id="65c81-146">指定进行更改的用户的姓名。</span><span class="sxs-lookup"><span data-stu-id="65c81-146">Specifies the name of the user who made a change.</span></span>

    -   <span data-ttu-id="65c81-147">**更改类型**。</span><span class="sxs-lookup"><span data-stu-id="65c81-147">**Change Type**.</span></span> <span data-ttu-id="65c81-148">指定要查找的更改类型。</span><span class="sxs-lookup"><span data-stu-id="65c81-148">Specifies the type of changes you are looking for.</span></span>

    -   <span data-ttu-id="65c81-149">**开始日期**。</span><span class="sxs-lookup"><span data-stu-id="65c81-149">**Start Date**.</span></span> <span data-ttu-id="65c81-150">指定要报告的日期范围的开始日期部分。</span><span class="sxs-lookup"><span data-stu-id="65c81-150">Specifies the Start Date part of the date range that you want to report on.</span></span>

    -   <span data-ttu-id="65c81-151">**结束日期**。</span><span class="sxs-lookup"><span data-stu-id="65c81-151">**End Date**.</span></span> <span data-ttu-id="65c81-152">指定要报告的日期范围的结束日期部分。</span><span class="sxs-lookup"><span data-stu-id="65c81-152">Specifies the End Date part of the date range that you want to report on.</span></span>

2.  <span data-ttu-id="65c81-153">单击 "**查看报表**" 以查看报表。</span><span class="sxs-lookup"><span data-stu-id="65c81-153">Click **View Report** to view the report.</span></span>

    <span data-ttu-id="65c81-154">可通过多种可用的文件格式（如 HTML、Microsoft Word 和 Microsoft Excel）保存结果。</span><span class="sxs-lookup"><span data-stu-id="65c81-154">Results can be saved in several available file formats such as HTML, Microsoft Word, and Microsoft Excel.</span></span>

**<span data-ttu-id="65c81-155">生成恢复密钥审核报告</span><span class="sxs-lookup"><span data-stu-id="65c81-155">To generate the Recovery Key Audit Report</span></span>**

1.  <span data-ttu-id="65c81-156">从 MBAMadministration 网站上，选择 "导航" 窗格中的 "**报表**" 节点，然后选择 "**恢复审核报告**"。</span><span class="sxs-lookup"><span data-stu-id="65c81-156">From the MBAMadministration website, select the **Report** node in the navigation pane, and then select the **Recovery Audit Report**.</span></span> <span data-ttu-id="65c81-157">为恢复密钥审核报告选择筛选器。</span><span class="sxs-lookup"><span data-stu-id="65c81-157">Select the filters for your Recovery Key Audit report.</span></span> <span data-ttu-id="65c81-158">用于恢复密钥审核的可用筛选器如下所示：</span><span class="sxs-lookup"><span data-stu-id="65c81-158">The available filters for Recovery Key audits are as follows:</span></span>

    -   <span data-ttu-id="65c81-159">**请求**程序。</span><span class="sxs-lookup"><span data-stu-id="65c81-159">**Requestor**.</span></span> <span data-ttu-id="65c81-160">指定请求者的用户名。</span><span class="sxs-lookup"><span data-stu-id="65c81-160">Specifies the user name of the requestor.</span></span> <span data-ttu-id="65c81-161">请求者是帮助台中代表用户访问密钥的人员。</span><span class="sxs-lookup"><span data-stu-id="65c81-161">The requestor is the person in the help desk who accessed the key on behalf of a user.</span></span>

    -   <span data-ttu-id="65c81-162">**Requestee**。</span><span class="sxs-lookup"><span data-stu-id="65c81-162">**Requestee**.</span></span> <span data-ttu-id="65c81-163">指定 requestee 的用户名。</span><span class="sxs-lookup"><span data-stu-id="65c81-163">Specifies the user name of the requestee.</span></span> <span data-ttu-id="65c81-164">Requestee 是呼叫支持人员以获取恢复密钥的人员。</span><span class="sxs-lookup"><span data-stu-id="65c81-164">The requestee is the person who called the help desk to obtain a recovery key.</span></span>

    -   <span data-ttu-id="65c81-165">**请求结果**指定请求结果类型，如：成功或失败。</span><span class="sxs-lookup"><span data-stu-id="65c81-165">**Request Result** Specifies the request result types, such as: Success or Failed.</span></span> <span data-ttu-id="65c81-166">例如，你可能希望查看失败的键访问尝试。</span><span class="sxs-lookup"><span data-stu-id="65c81-166">For example, you may want to view failed key access attempts.</span></span>

    -   <span data-ttu-id="65c81-167">**键类型**。</span><span class="sxs-lookup"><span data-stu-id="65c81-167">**Key Type**.</span></span> <span data-ttu-id="65c81-168">指定密钥类型，如：恢复密钥密码或 TPM 密码哈希。</span><span class="sxs-lookup"><span data-stu-id="65c81-168">Specifies the Key Type, such as: Recovery Key Password or TPM Password Hash.</span></span>

    -   <span data-ttu-id="65c81-169">**开始日期**。</span><span class="sxs-lookup"><span data-stu-id="65c81-169">**Start Date**.</span></span> <span data-ttu-id="65c81-170">指定日期范围的开始日期部分。</span><span class="sxs-lookup"><span data-stu-id="65c81-170">Specifies the Start Date part of the date range.</span></span>

    -   <span data-ttu-id="65c81-171">**结束日期**。</span><span class="sxs-lookup"><span data-stu-id="65c81-171">**End Date**.</span></span> <span data-ttu-id="65c81-172">指定日期范围的结束日期部分。</span><span class="sxs-lookup"><span data-stu-id="65c81-172">Specifies the End Date part of the date range.</span></span>

2.  <span data-ttu-id="65c81-173">单击 "**查看报表**" 以显示报表。</span><span class="sxs-lookup"><span data-stu-id="65c81-173">Click **View Report** to display the report.</span></span>

    <span data-ttu-id="65c81-174">可通过多种可用的文件格式（如 HTML、Microsoft Word 和 Microsoft Excel）保存结果。</span><span class="sxs-lookup"><span data-stu-id="65c81-174">Results can be saved in several available file formats such as HTML, Microsoft Word, and Microsoft Excel.</span></span>

## <span data-ttu-id="65c81-175">相关主题</span><span class="sxs-lookup"><span data-stu-id="65c81-175">Related topics</span></span>


[<span data-ttu-id="65c81-176">使用 MBAM 1.0 监视和报告 BitLocker 符合性</span><span class="sxs-lookup"><span data-stu-id="65c81-176">Monitoring and Reporting BitLocker Compliance with MBAM 1.0</span></span>](monitoring-and-reporting-bitlocker-compliance-with-mbam-10.md)

 

 





