---
title: 如何生成 MBAM 报告
description: 如何生成 MBAM 报告
author: dansimp
ms.assetid: 083550cb-8c3f-49b3-a30e-97d85374d2f4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ccdc1a2cd69d8cc2e2c2823827f5ea43ad867a78
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803499"
---
# <span data-ttu-id="6f0be-103">如何生成 MBAM 报告</span><span class="sxs-lookup"><span data-stu-id="6f0be-103">How to Generate MBAM Reports</span></span>


<span data-ttu-id="6f0be-104">使用独立拓扑安装 Microsoft BitLocker 管理和监视（MBAM）时，你可以生成不同的报表来监视 BitLocker 加密使用情况和合规性。</span><span class="sxs-lookup"><span data-stu-id="6f0be-104">When you install Microsoft BitLocker Administration and Monitoring (MBAM) with the Stand-alone topology, you can generate different reports to monitor BitLocker encryption usage and compliance.</span></span> <span data-ttu-id="6f0be-105">本主题中的过程介绍了如何打开管理和监视网站以及针对企业合规性、单独计算机和密钥恢复活动生成 Microsoft BitLocker 管理和监视报告所需的步骤。</span><span class="sxs-lookup"><span data-stu-id="6f0be-105">The procedures in this topic describe how to open the Administration and Monitoring website and the steps that are needed to generate Microsoft BitLocker Administration and Monitoring reports on enterprise compliance, individual computers, and key recovery activity.</span></span> <span data-ttu-id="6f0be-106">有关帮助了解 MBAM 报表的详细信息，请参阅[了解 MBAM 报表](understanding-mbam-reports-mbam-2.md)。</span><span class="sxs-lookup"><span data-stu-id="6f0be-106">For detailed information to help understand MBAM reports, see [Understanding MBAM Reports](understanding-mbam-reports-mbam-2.md).</span></span>

<span data-ttu-id="6f0be-107">**注意** 若要运行报表，您必须是已安装管理和监视服务器功能、合规性和审核数据库以及合规性和审核报告的计算机上的**报表用户角色**的成员。</span><span class="sxs-lookup"><span data-stu-id="6f0be-107">**Note** To run the reports, you must be a member of the **Report Users Role** on the computers where the Administration and Monitoring Server features, Compliance and Audit Database, and Compliance and Audit Reports are installed.</span></span>

 

**<span data-ttu-id="6f0be-108">打开 "管理和监视" 网站</span><span class="sxs-lookup"><span data-stu-id="6f0be-108">To open the Administration and Monitoring website</span></span>**

1.  <span data-ttu-id="6f0be-109">打开 web 浏览器并导航到 "管理和监视" 网站。</span><span class="sxs-lookup"><span data-stu-id="6f0be-109">Open a web browser and navigate to the Administration and Monitoring website.</span></span> <span data-ttu-id="6f0be-110">管理和监视网站的默认 URL 是\*http:// &lt; computername &gt; \*。</span><span class="sxs-lookup"><span data-stu-id="6f0be-110">The default URL for the Administration and Monitoring website is *http://&lt;computername&gt;*.</span></span>

    <span data-ttu-id="6f0be-111">**注意** 如果 theAdministration 和监视网站安装在80以外的端口上，则必须在 URL 中指定该端口（例如， \*http:// &lt; computername &gt; ： &lt; port &gt; \*。</span><span class="sxs-lookup"><span data-stu-id="6f0be-111">**Note** If theAdministration and Monitoring website was installed on a port other than 80, you have to specify the port in the URL (for example, *http://&lt;computername&gt;:&lt;port&gt;*.</span></span> <span data-ttu-id="6f0be-112">如果在安装期间为 theAdministration 和监视网站指定了一个主机名，则 URL 为\*http:// &lt; 主机 &gt; \*名。</span><span class="sxs-lookup"><span data-stu-id="6f0be-112">If you specified a host name for theAdministration and Monitoring website during the installation, the URL is *http://&lt;hostname&gt;*.</span></span>

     

2.  <span data-ttu-id="6f0be-113">在左窗格中，单击 "**报表**"，然后从顶部菜单栏中选择要运行的报表。</span><span class="sxs-lookup"><span data-stu-id="6f0be-113">In the left pane, click **Reports** and then select the report you want to run from the top menu bar.</span></span>

    <span data-ttu-id="6f0be-114">当计算机丢失或被盗时，历史 MBAM 客户端数据将保留在合规性数据库中以供历史参考。</span><span class="sxs-lookup"><span data-stu-id="6f0be-114">Historical MBAM client data is retained in the compliance database for historical reference in case a computer is lost or stolen.</span></span> <span data-ttu-id="6f0be-115">运行企业报告时，我们建议你使用相应的开始日期和结束日期将报表的时间范围从一到两周范围内的范围增加到报表数据准确性。</span><span class="sxs-lookup"><span data-stu-id="6f0be-115">When running enterprise reports, we recommend that you use appropriate start and end dates to scope the time frames for the reports from one to two weeks to increase reporting data accuracy.</span></span>

    <span data-ttu-id="6f0be-116">**注意** 如果未将 SSRS 配置为使用安全套接字层，则在安装 MBAM 服务器时，报表的 URL 将设置为 HTTP，而不是 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="6f0be-116">**Note** If SSRS was not configured to use Secure Socket Layer, the URL for the reports will be set to HTTP instead of to HTTPS when you install the MBAM Server.</span></span> <span data-ttu-id="6f0be-117">如果您转到技术支持门户并选择报表，则会显示以下消息： "仅显示安全内容"。</span><span class="sxs-lookup"><span data-stu-id="6f0be-117">If you then go to the Help Desk portal and select a report, the following message displays: “Only Secure Content is Displayed.”</span></span> <span data-ttu-id="6f0be-118">若要显示报表，请单击 "**显示所有内容**"。</span><span class="sxs-lookup"><span data-stu-id="6f0be-118">To show the report, click **Show All Content**.</span></span>

     

**<span data-ttu-id="6f0be-119">生成企业合规性报告</span><span class="sxs-lookup"><span data-stu-id="6f0be-119">To generate an Enterprise Compliance Report</span></span>**

1.  <span data-ttu-id="6f0be-120">从 "管理和监视" 网站，从左侧导航窗格中选择 "**报表**" 节点，选择 "**企业合规性报表**"，然后选择要使用的筛选器。</span><span class="sxs-lookup"><span data-stu-id="6f0be-120">From the Administration and Monitoring website, select the **Reports** node from the left navigation pane, select **Enterprise Compliance Report**, and select the filters that you want to use.</span></span> <span data-ttu-id="6f0be-121">企业合规性报告的可用筛选器如下所示：</span><span class="sxs-lookup"><span data-stu-id="6f0be-121">The available filters for the Enterprise Compliance Report are the following:</span></span>

    -   <span data-ttu-id="6f0be-122">**合规性状态**。</span><span class="sxs-lookup"><span data-stu-id="6f0be-122">**Compliance Status**.</span></span> <span data-ttu-id="6f0be-123">使用此筛选器指定报表的符合性状态类型（例如，合规性或不符合）。</span><span class="sxs-lookup"><span data-stu-id="6f0be-123">Use this filter to specify the compliance status types (for example, Compliant, or Noncompliant) of the report.</span></span>

    -   <span data-ttu-id="6f0be-124">**错误状态**。</span><span class="sxs-lookup"><span data-stu-id="6f0be-124">**Error State**.</span></span> <span data-ttu-id="6f0be-125">使用此筛选器指定报表的错误状态类型（如无错误或错误）。</span><span class="sxs-lookup"><span data-stu-id="6f0be-125">Use this filter to specify the error state types (for example, No Error, or Error) of the report.</span></span>

2.  <span data-ttu-id="6f0be-126">单击 "**查看报表**" 以显示所选报表。</span><span class="sxs-lookup"><span data-stu-id="6f0be-126">Click **View Report** to display the selected report.</span></span>

    <span data-ttu-id="6f0be-127">可将结果保存为不同格式，如 HTML、Microsoft Word 和 Microsoft Excel。</span><span class="sxs-lookup"><span data-stu-id="6f0be-127">Results can be saved in different formats, such as HTML, Microsoft Word, and Microsoft Excel.</span></span>

    <span data-ttu-id="6f0be-128">**注意** 企业合规性报告由每6个小时运行的 SQL 作业生成。</span><span class="sxs-lookup"><span data-stu-id="6f0be-128">**Note** The Enterprise Compliance report is generated by a SQL job that runs every six hours.</span></span> <span data-ttu-id="6f0be-129">因此，第一次查看报表时，您可能会发现某些数据丢失。</span><span class="sxs-lookup"><span data-stu-id="6f0be-129">Therefore, the first time you view the report, you may find that some data is missing.</span></span> <span data-ttu-id="6f0be-130">你可以使用 SQL Management Studio 手动生成更新的报表数据。</span><span class="sxs-lookup"><span data-stu-id="6f0be-130">You can generate updated report data manually by using SQL Management Studio.</span></span> <span data-ttu-id="6f0be-131">在 "**对象资源管理器**" 窗口中，展开 " **SQL Server 代理**"，展开 "**作业**"，右键单击**CreateCache**作业，然后选择 "**在步骤中启动作业**..."。</span><span class="sxs-lookup"><span data-stu-id="6f0be-131">From the **Object Explorer** window, expand **SQL Server Agent**, expand **Jobs**, right-click the **CreateCache** job, and select **Start Job at Step….**</span></span>

     

3.  <span data-ttu-id="6f0be-132">选择计算机名称以查看计算机合规性报告中有关计算机的信息。</span><span class="sxs-lookup"><span data-stu-id="6f0be-132">Select a computer name to view information about the computer in the Computer Compliance Report.</span></span>

4.  <span data-ttu-id="6f0be-133">选择计算机名称旁边的加号（+）以查看有关计算机上的卷的信息。</span><span class="sxs-lookup"><span data-stu-id="6f0be-133">Select the plus sign (+) next to the computer name to view information about the volumes on the computer.</span></span>

**<span data-ttu-id="6f0be-134">生成计算机合规性报告</span><span class="sxs-lookup"><span data-stu-id="6f0be-134">To generate the Computer Compliance Report</span></span>**

1.  <span data-ttu-id="6f0be-135">在 "管理和监视" 网站中，从左侧导航窗格中选择 "**报表**" 节点，然后选择 "**计算机合规性报告**"。</span><span class="sxs-lookup"><span data-stu-id="6f0be-135">In the Administration and Monitoring website, select the **Report** node from the left navigation pane, and then select the **Computer Compliance Report**.</span></span> <span data-ttu-id="6f0be-136">使用 "计算机合规性报告" 搜索**用户名**或**计算机名称**。</span><span class="sxs-lookup"><span data-stu-id="6f0be-136">Use the Computer Compliance report to search for **user name** or **computer name**.</span></span>

2.  <span data-ttu-id="6f0be-137">单击 "**查看报表**" 以查看计算机报告。</span><span class="sxs-lookup"><span data-stu-id="6f0be-137">Click **View Report** to view the computer report.</span></span>

    <span data-ttu-id="6f0be-138">可将结果保存为不同格式，如 HTML、Microsoft Word 和 Microsoft Excel。</span><span class="sxs-lookup"><span data-stu-id="6f0be-138">Results can be saved in different formats, such as HTML, Microsoft Word, and Microsoft Excel.</span></span>

3.  <span data-ttu-id="6f0be-139">选择计算机名称以在计算机合规性报告中显示有关计算机的详细信息。</span><span class="sxs-lookup"><span data-stu-id="6f0be-139">Select a computer name to display more information about the computer in the Computer Compliance Report.</span></span>

4.  <span data-ttu-id="6f0be-140">选择计算机名称旁边的加号（+）以查看有关计算机上的卷的信息。</span><span class="sxs-lookup"><span data-stu-id="6f0be-140">Select the plus sign (+) next to the computer name to view information about the volumes on the computer.</span></span>

    <span data-ttu-id="6f0be-141">**注意** 如果计算机符合 MBAM 策略设置的要求，则认为 MBAM 客户端计算机合规。</span><span class="sxs-lookup"><span data-stu-id="6f0be-141">**Note** An MBAM client computer is considered compliant if the computer matches the requirements of the MBAM policy settings.</span></span>

     

**<span data-ttu-id="6f0be-142">生成恢复密钥审核报告</span><span class="sxs-lookup"><span data-stu-id="6f0be-142">To generate the Recovery Key Audit Report</span></span>**

1.  <span data-ttu-id="6f0be-143">从 "管理和监视" 网站中，选择左侧导航窗格中的 "**报表**" 节点，然后选择 "**恢复审核报告**"。</span><span class="sxs-lookup"><span data-stu-id="6f0be-143">From the Administration and Monitoring website, select the **Report** node in the left navigation pane, and then select the **Recovery Audit Report**.</span></span> <span data-ttu-id="6f0be-144">为恢复密钥审核报告选择筛选器。</span><span class="sxs-lookup"><span data-stu-id="6f0be-144">Select the filters for your Recovery Key Audit report.</span></span> <span data-ttu-id="6f0be-145">用于恢复密钥审核的可用筛选器如下所示：</span><span class="sxs-lookup"><span data-stu-id="6f0be-145">The available filters for Recovery Key audits are as follows:</span></span>

    -   <span data-ttu-id="6f0be-146">**请求**程序。</span><span class="sxs-lookup"><span data-stu-id="6f0be-146">**Requestor**.</span></span> <span data-ttu-id="6f0be-147">此筛选器使用户能够指定申请者的用户名。</span><span class="sxs-lookup"><span data-stu-id="6f0be-147">This filter enables users to specify the user name of the requester.</span></span> <span data-ttu-id="6f0be-148">申请者是帮助台中代表用户访问密钥的人员。</span><span class="sxs-lookup"><span data-stu-id="6f0be-148">The requester is the person in the Help Desk who accessed the key on behalf of a user.</span></span>

    -   <span data-ttu-id="6f0be-149">**Requestee**。</span><span class="sxs-lookup"><span data-stu-id="6f0be-149">**Requestee**.</span></span> <span data-ttu-id="6f0be-150">此筛选器使用户能够指定 requestee 的用户名。</span><span class="sxs-lookup"><span data-stu-id="6f0be-150">This filter enables users to specify the user name of the requestee.</span></span> <span data-ttu-id="6f0be-151">Requestee 是呼叫支持人员以获取恢复密钥的人员。</span><span class="sxs-lookup"><span data-stu-id="6f0be-151">The requestee is the person who called the Help Desk to obtain a recovery key.</span></span>

    -   <span data-ttu-id="6f0be-152">**请求结果**。</span><span class="sxs-lookup"><span data-stu-id="6f0be-152">**Request Result**.</span></span> <span data-ttu-id="6f0be-153">此筛选器使用户能够指定报表要基于的请求结果类型（如成功或失败）。</span><span class="sxs-lookup"><span data-stu-id="6f0be-153">This filter enables users to specify the request result types (for example, Success or Failed) that they want to base the report on.</span></span> <span data-ttu-id="6f0be-154">例如，用户可能希望查看失败的键访问尝试。</span><span class="sxs-lookup"><span data-stu-id="6f0be-154">For example, users may want to view failed key access attempts.</span></span>

    -   <span data-ttu-id="6f0be-155">**键类型**。</span><span class="sxs-lookup"><span data-stu-id="6f0be-155">**Key Type**.</span></span> <span data-ttu-id="6f0be-156">此筛选器使用户能够指定要基于其创建报表的密钥类型（例如，恢复密钥密码或 TPM 密码哈希）。</span><span class="sxs-lookup"><span data-stu-id="6f0be-156">This filter enables users to specify the Key Type (for example: Recovery Key Password or TPM Password Hash) that they want to base the report on.</span></span>

    -   <span data-ttu-id="6f0be-157">**开始日期**。</span><span class="sxs-lookup"><span data-stu-id="6f0be-157">**Start Date**.</span></span> <span data-ttu-id="6f0be-158">此筛选器用于定义用户要报告的日期范围的开始日期部分。</span><span class="sxs-lookup"><span data-stu-id="6f0be-158">This filter is used to define the Start Date part of the date range that the user wants to report on.</span></span>

    -   <span data-ttu-id="6f0be-159">**结束日期**。</span><span class="sxs-lookup"><span data-stu-id="6f0be-159">**End Date**.</span></span> <span data-ttu-id="6f0be-160">此筛选器用于定义用户要报告的日期范围的结束日期部分。</span><span class="sxs-lookup"><span data-stu-id="6f0be-160">This filter is used to define the End Date part of the date range that the users want to report on.</span></span>

2.  <span data-ttu-id="6f0be-161">单击 "**查看报表**" 以查看报表。</span><span class="sxs-lookup"><span data-stu-id="6f0be-161">Click **View Report** to view the report.</span></span>

    <span data-ttu-id="6f0be-162">可将结果保存为不同格式，如 HTML、Microsoft Word 和 Microsoft Excel。</span><span class="sxs-lookup"><span data-stu-id="6f0be-162">Results can be saved in different formats, such as HTML, Microsoft Word, and Microsoft Excel.</span></span>

## <span data-ttu-id="6f0be-163">相关主题</span><span class="sxs-lookup"><span data-stu-id="6f0be-163">Related topics</span></span>


[<span data-ttu-id="6f0be-164">使用 MBAM 2.0 监视和报告 BitLocker 符合性</span><span class="sxs-lookup"><span data-stu-id="6f0be-164">Monitoring and Reporting BitLocker Compliance with MBAM 2.0</span></span>](monitoring-and-reporting-bitlocker-compliance-with-mbam-20-mbam-2.md)

 

 





