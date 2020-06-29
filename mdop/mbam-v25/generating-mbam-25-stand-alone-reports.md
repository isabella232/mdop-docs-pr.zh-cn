---
title: 生成 MBAM 2.5 独立报告
description: 生成 MBAM 2.5 独立报告
author: dansimp
ms.assetid: 0ec623ff-5155-4906-aef2-20cdc0f84667
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 11/01/2016
ms.openlocfilehash: e1c6b33de26cce5d9ad8d20461dbe0ea0f138c78
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803305"
---
# <span data-ttu-id="6fc62-103">生成 MBAM 2.5 独立报告</span><span class="sxs-lookup"><span data-stu-id="6fc62-103">Generating MBAM 2.5 Stand-alone Reports</span></span>


<span data-ttu-id="6fc62-104">使用独立拓扑配置 Microsoft BitLocker 管理和监视（MBAM）时，你可以生成报告以监视 BitLocker 驱动器加密使用情况和合规性。</span><span class="sxs-lookup"><span data-stu-id="6fc62-104">When you configure Microsoft BitLocker Administration and Monitoring (MBAM) with the Stand-alone topology, you can generate reports to monitor BitLocker drive encryption usage and compliance.</span></span> <span data-ttu-id="6fc62-105">本主题包含以下过程：</span><span class="sxs-lookup"><span data-stu-id="6fc62-105">This topic contains the following procedures:</span></span>

-   [<span data-ttu-id="6fc62-106">打开 "管理和监视" 网站</span><span class="sxs-lookup"><span data-stu-id="6fc62-106">To open the Administration and Monitoring Website</span></span>](#bkmk-openadmin)

-   [<span data-ttu-id="6fc62-107">生成企业合规性报告</span><span class="sxs-lookup"><span data-stu-id="6fc62-107">To generate an Enterprise Compliance Report</span></span>](#bkmk-enterprise)

-   [<span data-ttu-id="6fc62-108">生成计算机合规性报告</span><span class="sxs-lookup"><span data-stu-id="6fc62-108">To generate a Computer Compliance Report</span></span>](#bkmk-computercomp)

-   [<span data-ttu-id="6fc62-109">生成恢复密钥审核报告</span><span class="sxs-lookup"><span data-stu-id="6fc62-109">To generate a Recovery Key Audit Report</span></span>](#bkmk-recoverykey)

<span data-ttu-id="6fc62-110">有关独立报表的说明，请参阅[了解 MBAM 2.5 独立的报表](understanding-mbam-25-stand-alone-reports.md)。</span><span class="sxs-lookup"><span data-stu-id="6fc62-110">For descriptions of the Stand-alone reports, see [Understanding MBAM 2.5 Stand-alone Reports](understanding-mbam-25-stand-alone-reports.md).</span></span>

<span data-ttu-id="6fc62-111">**注意** 若要运行报表，您必须是在 Active Directory 域服务中配置的**MBAM Report Users**组的成员。</span><span class="sxs-lookup"><span data-stu-id="6fc62-111">**Note** To run the reports, you must be a member of the **MBAM Report Users** group, which you configure in Active Directory Domain Services.</span></span> <span data-ttu-id="6fc62-112">有关详细信息，请参阅[规划 MBAM 2.5 组和帐户](planning-for-mbam-25-groups-and-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="6fc62-112">For more information, see [Planning for MBAM 2.5 Groups and Accounts](planning-for-mbam-25-groups-and-accounts.md).</span></span>

 

<a href="" id="bkmk-openadmin"></a>**<span data-ttu-id="6fc62-113">打开 "管理和监视" 网站</span><span class="sxs-lookup"><span data-stu-id="6fc62-113">To open the Administration and Monitoring Website</span></span>**

1.  <span data-ttu-id="6fc62-114">打开 web 浏览器并导航到 "管理和监视" 网站。</span><span class="sxs-lookup"><span data-stu-id="6fc62-114">Open a web browser and navigate to the Administration and Monitoring Website.</span></span> <span data-ttu-id="6fc62-115">管理和监视网站的默认 URL 为：</span><span class="sxs-lookup"><span data-stu-id="6fc62-115">The default URL for the Administration and Monitoring Website is:</span></span>

    *<span data-ttu-id="6fc62-116">http （s）：// &lt; MBAMAdministrationServerName &gt; ： &lt; port &gt; /Helpdesk</span><span class="sxs-lookup"><span data-stu-id="6fc62-116">http(s)://&lt;MBAMAdministrationServerName&gt;:&lt;port&gt;/Helpdesk</span></span>*

2.  <span data-ttu-id="6fc62-117">在左窗格中，单击 "**报表**"。</span><span class="sxs-lookup"><span data-stu-id="6fc62-117">In the left pane, click **Reports**.</span></span> <span data-ttu-id="6fc62-118">从顶部的菜单栏中，选择要运行的报表。</span><span class="sxs-lookup"><span data-stu-id="6fc62-118">From the top menu bar, select the report you want to run.</span></span>

    <span data-ttu-id="6fc62-119">在计算机丢失或被盗时，MBAM 客户端数据将保留在合规性和审核数据库中以供历史参考。</span><span class="sxs-lookup"><span data-stu-id="6fc62-119">MBAM client data is retained in the Compliance and Audit Database for historical reference in case a computer is lost or stolen.</span></span> <span data-ttu-id="6fc62-120">运行企业报告时，我们建议你使用相应的开始日期和结束日期将报表的时间范围从一到两周范围内的范围增加到报表数据准确性。</span><span class="sxs-lookup"><span data-stu-id="6fc62-120">When running enterprise reports, we recommend that you use appropriate start and end dates to scope the time frames for the reports from one to two weeks to increase reporting data accuracy.</span></span>

    <span data-ttu-id="6fc62-121">生成报表后，可将结果保存为不同格式，如 HTML、Microsoft Word 和 Microsoft Excel。</span><span class="sxs-lookup"><span data-stu-id="6fc62-121">After you generate a report, you can save the results in different formats, such as HTML, Microsoft Word, and Microsoft Excel.</span></span>

    <span data-ttu-id="6fc62-122">**注意** 配置 SQL Server Reporting Services （SSRS）以使用安全套接字层（SSL），然后再配置管理和监视网站。</span><span class="sxs-lookup"><span data-stu-id="6fc62-122">**Note** Configure SQL Server Reporting Services (SSRS) to use Secure Sockets Layer (SSL) before configuring the Administration and Monitoring Website.</span></span> <span data-ttu-id="6fc62-123">如果出于任何原因，未将 SSRS 配置为使用 SSL，则在配置管理和监视网站时，报表的 URL 将设置为 HTTP，而不是 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="6fc62-123">If, for any reason, SSRS is not configured to use SSL, the URL for the Reports will be set to HTTP instead of to HTTPS when you configure the Administration and Monitoring Website.</span></span> <span data-ttu-id="6fc62-124">如果随后转到 "管理和监视" 网站并选择报表，则会显示以下消息： "仅显示安全内容"。</span><span class="sxs-lookup"><span data-stu-id="6fc62-124">If you then go to the Administration and Monitoring Website and select a report, the following message displays: “Only Secure Content is Displayed.”</span></span> <span data-ttu-id="6fc62-125">若要显示报表，请单击 "**显示所有内容**"。</span><span class="sxs-lookup"><span data-stu-id="6fc62-125">To show the report, click **Show All Content**.</span></span>

     

<a href="" id="bkmk-enterprise"></a>**<span data-ttu-id="6fc62-126">生成企业合规性报告</span><span class="sxs-lookup"><span data-stu-id="6fc62-126">To generate an Enterprise Compliance Report</span></span>**

1.  <span data-ttu-id="6fc62-127">从 "管理和监视" 网站，从左侧导航窗格中选择 "**报表**" 节点，选择 "**企业合规性报表**"，然后选择要使用的筛选器。</span><span class="sxs-lookup"><span data-stu-id="6fc62-127">From the Administration and Monitoring Website, select the **Reports** node from the left navigation pane, select **Enterprise Compliance Report**, and select the filters that you want to use.</span></span> <span data-ttu-id="6fc62-128">企业合规性报告的可用筛选器包括：</span><span class="sxs-lookup"><span data-stu-id="6fc62-128">The available filters for the Enterprise Compliance Report are:</span></span>

    -   <span data-ttu-id="6fc62-129">**合规性状态**。</span><span class="sxs-lookup"><span data-stu-id="6fc62-129">**Compliance Status**.</span></span> <span data-ttu-id="6fc62-130">使用此筛选器指定报表的符合性状态类型（例如，合规或不符合）。</span><span class="sxs-lookup"><span data-stu-id="6fc62-130">Use this filter to specify the compliance status types of the report (for example, Compliant or Noncompliant).</span></span>

    -   <span data-ttu-id="6fc62-131">**错误状态**。</span><span class="sxs-lookup"><span data-stu-id="6fc62-131">**Error State**.</span></span> <span data-ttu-id="6fc62-132">使用此筛选器指定报表的错误状态类型（例如，无错误或错误）。</span><span class="sxs-lookup"><span data-stu-id="6fc62-132">Use this filter to specify the error state types of the report (for example, No Error or Error).</span></span>

2.  <span data-ttu-id="6fc62-133">单击 "**查看报表**" 以显示所选报表。</span><span class="sxs-lookup"><span data-stu-id="6fc62-133">Click **View Report** to display the selected report.</span></span>

3.  <span data-ttu-id="6fc62-134">选择计算机名称以查看计算机合规性报告中有关计算机的信息。</span><span class="sxs-lookup"><span data-stu-id="6fc62-134">Select a computer name to view information about the computer in the Computer Compliance Report.</span></span>

4.  <span data-ttu-id="6fc62-135">选择计算机名称旁边的加号（+）以查看有关计算机上的卷的信息。</span><span class="sxs-lookup"><span data-stu-id="6fc62-135">Select the plus sign (+) next to the computer name to view information about the volumes on the computer.</span></span>

<a href="" id="bkmk-computercomp"></a>**<span data-ttu-id="6fc62-136">生成计算机合规性报告</span><span class="sxs-lookup"><span data-stu-id="6fc62-136">To generate a Computer Compliance Report</span></span>**

1.  <span data-ttu-id="6fc62-137">从 "管理和监视" 网站中，从左侧导航窗格中选择 "**报表**" 节点，然后选择 "**计算机合规性报告**"。</span><span class="sxs-lookup"><span data-stu-id="6fc62-137">From the Administration and Monitoring Website, select the **Report** node from the left navigation pane, and then select **Computer Compliance Report**.</span></span> <span data-ttu-id="6fc62-138">使用 "计算机合规性报告" 搜索**用户名**或**计算机名称**。</span><span class="sxs-lookup"><span data-stu-id="6fc62-138">Use the Computer Compliance Report to search for **User name** or **Computer name**.</span></span>

2.  <span data-ttu-id="6fc62-139">单击 "**查看报表**" 以查看计算机合规性报告。</span><span class="sxs-lookup"><span data-stu-id="6fc62-139">Click **View Report** to view the Computer Compliance Report.</span></span>

3.  <span data-ttu-id="6fc62-140">选择计算机名称以在计算机合规性报告中显示有关计算机的详细信息。</span><span class="sxs-lookup"><span data-stu-id="6fc62-140">Select a computer name to display more information about the computer in the Computer Compliance Report.</span></span>

4.  <span data-ttu-id="6fc62-141">选择计算机名称旁边的加号（+）以查看有关计算机上的卷的信息。</span><span class="sxs-lookup"><span data-stu-id="6fc62-141">Select the plus sign (+) next to the computer name to view information about the volumes on the computer.</span></span>

    <span data-ttu-id="6fc62-142">**注意** 如果计算机匹配或超过 MBAM 组策略设置的要求，则认为 MBAM 客户端计算机合规。</span><span class="sxs-lookup"><span data-stu-id="6fc62-142">**Note** An MBAM client computer is considered compliant if the computer matches or exceeds the requirements of the MBAM Group Policy settings.</span></span>

<a href="" id="bkmk-recoverykey"></a>**<span data-ttu-id="6fc62-143">生成恢复密钥审核报告</span><span class="sxs-lookup"><span data-stu-id="6fc62-143">To generate a Recovery Key Audit Report</span></span>**

1.  <span data-ttu-id="6fc62-144">从 "管理和监视" 网站中，选择左侧导航窗格中的 "**报表**" 节点，然后选择 "**恢复审核报告**"。</span><span class="sxs-lookup"><span data-stu-id="6fc62-144">From the Administration and Monitoring Website, select the **Report** node in the left navigation pane, and then select **Recovery Audit Report**.</span></span> <span data-ttu-id="6fc62-145">为恢复密钥审核报告选择筛选器。</span><span class="sxs-lookup"><span data-stu-id="6fc62-145">Select the filters for your Recovery Key Audit Report.</span></span> <span data-ttu-id="6fc62-146">用于恢复密钥审核的可用筛选器如下所示：</span><span class="sxs-lookup"><span data-stu-id="6fc62-146">The available filters for recovery key audits are as follows:</span></span>

    -   <span data-ttu-id="6fc62-147">**帮助台用户**。</span><span class="sxs-lookup"><span data-stu-id="6fc62-147">**Helpdesk User**.</span></span> <span data-ttu-id="6fc62-148">此筛选器使用户能够指定申请者的用户名。</span><span class="sxs-lookup"><span data-stu-id="6fc62-148">This filter enables users to specify the user name of the requester.</span></span> <span data-ttu-id="6fc62-149">申请者是帮助台中代表最终用户访问密钥的人员。</span><span class="sxs-lookup"><span data-stu-id="6fc62-149">The requester is the person in the Help Desk who accessed the key on behalf of an end user.</span></span>

    -   <span data-ttu-id="6fc62-150">**最终用户**。</span><span class="sxs-lookup"><span data-stu-id="6fc62-150">**End User**.</span></span> <span data-ttu-id="6fc62-151">此筛选器使用户能够指定 requestee 的用户名。</span><span class="sxs-lookup"><span data-stu-id="6fc62-151">This filter enables users to specify the user name of the requestee.</span></span> <span data-ttu-id="6fc62-152">Requestee 是呼叫帮助台以获取恢复密钥的最终用户。</span><span class="sxs-lookup"><span data-stu-id="6fc62-152">The requestee is the end user who called the Help Desk to obtain a recovery key.</span></span>

    -   <span data-ttu-id="6fc62-153">**请求结果**。</span><span class="sxs-lookup"><span data-stu-id="6fc62-153">**Request Result**.</span></span> <span data-ttu-id="6fc62-154">此筛选器使用户能够指定报表要基于的请求结果类型（如成功或失败）。</span><span class="sxs-lookup"><span data-stu-id="6fc62-154">This filter enables users to specify the request result types (for example, Success or Failed) that they want to base the report on.</span></span> <span data-ttu-id="6fc62-155">例如，用户可能希望查看失败的键访问尝试。</span><span class="sxs-lookup"><span data-stu-id="6fc62-155">For example, users may want to view failed key access attempts.</span></span>

    -   <span data-ttu-id="6fc62-156">**键类型**。</span><span class="sxs-lookup"><span data-stu-id="6fc62-156">**Key Type**.</span></span> <span data-ttu-id="6fc62-157">此筛选器使用户能够指定报表要基于的密钥类型（例如，恢复密钥密码或 TPM 密码哈希）。</span><span class="sxs-lookup"><span data-stu-id="6fc62-157">This filter enables users to specify the key type (for example, Recovery Key Password or TPM Password Hash) that they want to base the report on.</span></span>

    -   <span data-ttu-id="6fc62-158">**开始日期**。</span><span class="sxs-lookup"><span data-stu-id="6fc62-158">**Start Date**.</span></span> <span data-ttu-id="6fc62-159">此筛选器用于定义用户要报告的日期范围的开始日期部分。</span><span class="sxs-lookup"><span data-stu-id="6fc62-159">This filter is used to define the Start Date part of the date range that the user wants to report on.</span></span>

    -   <span data-ttu-id="6fc62-160">**结束日期**。</span><span class="sxs-lookup"><span data-stu-id="6fc62-160">**End Date**.</span></span> <span data-ttu-id="6fc62-161">此筛选器用于定义用户要报告的日期范围的结束日期部分。</span><span class="sxs-lookup"><span data-stu-id="6fc62-161">This filter is used to define the End Date part of the date range that the users want to report on.</span></span>

2.  <span data-ttu-id="6fc62-162">单击 "**查看报表**" 以查看报表。</span><span class="sxs-lookup"><span data-stu-id="6fc62-162">Click **View Report** to view the report.</span></span>



## <span data-ttu-id="6fc62-163">相关主题</span><span class="sxs-lookup"><span data-stu-id="6fc62-163">Related topics</span></span>


[<span data-ttu-id="6fc62-164">监视和报告 BitLocker 与 MBAM 2.5 的相容性</span><span class="sxs-lookup"><span data-stu-id="6fc62-164">Monitoring and Reporting BitLocker Compliance with MBAM 2.5</span></span>](monitoring-and-reporting-bitlocker-compliance-with-mbam-25.md)

[<span data-ttu-id="6fc62-165">了解 MBAM 2.5 独立报告</span><span class="sxs-lookup"><span data-stu-id="6fc62-165">Understanding MBAM 2.5 Stand-alone Reports</span></span>](understanding-mbam-25-stand-alone-reports.md)

 

## <span data-ttu-id="6fc62-166">已获得 MBAM 的建议？</span><span class="sxs-lookup"><span data-stu-id="6fc62-166">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="6fc62-167">在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="6fc62-167">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="6fc62-168">对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="6fc62-168">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





