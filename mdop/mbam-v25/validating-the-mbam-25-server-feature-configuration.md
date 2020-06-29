---
title: 验证 MBAM 2.5 服务器功能配置
description: 验证 MBAM 2.5 服务器功能配置
author: dansimp
ms.assetid: f4983a33-ce18-4186-a471-dd6415940504
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f955e0b9ccb7952995574e4aa981674f7c7667fe
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804097"
---
# <span data-ttu-id="3de7b-103">验证 MBAM 2.5 服务器功能配置</span><span class="sxs-lookup"><span data-stu-id="3de7b-103">Validating the MBAM 2.5 Server Feature Configuration</span></span>


<span data-ttu-id="3de7b-104">完成 Microsoft BitLocker 管理和监视（MBAM）2.5 服务器功能部署时，建议你验证部署，以确保已成功配置所有功能。</span><span class="sxs-lookup"><span data-stu-id="3de7b-104">When you finish the Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 Server feature deployment, we recommend that you validate the deployment to ensure that all features have been successfully configured.</span></span> <span data-ttu-id="3de7b-105">使用与你部署的拓扑（独立或 System Center Configuration Manager 集成）匹配的过程。</span><span class="sxs-lookup"><span data-stu-id="3de7b-105">Use the procedure that matches the topology (Stand-alone or System Center Configuration Manager Integration) that you deployed.</span></span>

## <span data-ttu-id="3de7b-106">使用独立拓扑验证 MBAM 服务器部署</span><span class="sxs-lookup"><span data-stu-id="3de7b-106">Validating the MBAM Server deployment with the Stand-alone topology</span></span>


<span data-ttu-id="3de7b-107">使用以下步骤验证具有独立拓扑的 MBAM 服务器部署。</span><span class="sxs-lookup"><span data-stu-id="3de7b-107">Use the following steps to validate your MBAM Server deployment with the Stand-alone topology.</span></span>

**<span data-ttu-id="3de7b-108">验证独立的 MBAM 服务器部署</span><span class="sxs-lookup"><span data-stu-id="3de7b-108">To validate a Stand-alone MBAM Server deployment</span></span>**

1.  <span data-ttu-id="3de7b-109">在部署 MBAM 功能的每台服务器上，单击 **"控制面板** &gt; **程序** &gt; **程序和功能**"。</span><span class="sxs-lookup"><span data-stu-id="3de7b-109">On each server where an MBAM feature is deployed, click **Control Panel** &gt; **Programs** &gt; **Programs and Features**.</span></span> <span data-ttu-id="3de7b-110">验证 "**程序和功能**" 列表中是否显示 " **Microsoft BitLocker 管理和监视**"。</span><span class="sxs-lookup"><span data-stu-id="3de7b-110">Verify that **Microsoft BitLocker Administration and Monitoring** appears in the **Programs and Features** list.</span></span>

    **<span data-ttu-id="3de7b-111">注意</span><span class="sxs-lookup"><span data-stu-id="3de7b-111">Note</span></span>**  
    <span data-ttu-id="3de7b-112">若要进行验证，你必须使用在每台服务器上具有本地计算机管理凭据的域帐户。</span><span class="sxs-lookup"><span data-stu-id="3de7b-112">To do the validation, you must use a domain account that has local computer administrative credentials on each server.</span></span>



2.  <span data-ttu-id="3de7b-113">在配置了恢复数据库的服务器上，打开 SQL Server Management Studio 并验证是否配置了**MBAM 恢复和硬件**数据库。</span><span class="sxs-lookup"><span data-stu-id="3de7b-113">On the server where the Recovery Database is configured, open SQL Server Management Studio and verify that the **MBAM Recovery and Hardware** database is configured.</span></span>

3.  <span data-ttu-id="3de7b-114">在配置合规性和审核数据库的服务器上，打开 SQL Server Management Studio 并验证是否配置了**MBAM 合规性状态数据库**。</span><span class="sxs-lookup"><span data-stu-id="3de7b-114">On the server where the Compliance and Audit Database is configured, open SQL Server Management Studio and verify that the **MBAM Compliance Status Database** is configured.</span></span>

4.  <span data-ttu-id="3de7b-115">在配置了 "报表" 功能的服务器上，打开具有管理凭据的 web 浏览器，然后浏览到 SQL Server Reporting Services 网站的 "开始"。</span><span class="sxs-lookup"><span data-stu-id="3de7b-115">On the server where the Reports feature is configured, open a web browser with administrative credentials and browse to the "Home" of the SQL Server Reporting Services site.</span></span>

    <span data-ttu-id="3de7b-116">SQL Server Reporting Services 网站实例的默认起始位置为：</span><span class="sxs-lookup"><span data-stu-id="3de7b-116">The default Home location of a SQL Server Reporting Services site instance is at:</span></span>

    <span data-ttu-id="3de7b-117">http （s）：// &lt; *MBAMReportsServerName* &gt; ： &lt; *port* &gt; /Reports.aspx</span><span class="sxs-lookup"><span data-stu-id="3de7b-117">http(s)://&lt; *MBAMReportsServerName*&gt;:&lt;*port*&gt;/Reports.aspx</span></span>

    <span data-ttu-id="3de7b-118">若要查找实际 URL，请使用 Reporting Services 配置管理器工具，并选择在安装过程中指定的实例。</span><span class="sxs-lookup"><span data-stu-id="3de7b-118">To find the actual URL, use the Reporting Services Configuration Manager tool and select the instances that you specified during setup.</span></span>

5.  <span data-ttu-id="3de7b-119">确认名为**Microsoft BitLocker 管理和监视**的报告文件夹包含名为**MaltaDataSource**的数据源和语言文件夹。</span><span class="sxs-lookup"><span data-stu-id="3de7b-119">Confirm that a reports folder named **Microsoft BitLocker Administration and Monitoring** contains a data source called **MaltaDataSource** as well as the language folders.</span></span> <span data-ttu-id="3de7b-120">数据源包含名称表示语言（例如，en-us）的文件夹。</span><span class="sxs-lookup"><span data-stu-id="3de7b-120">The data source contains folders with names that represent languages (for example, en-us).</span></span> <span data-ttu-id="3de7b-121">报表位于 "语言" 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="3de7b-121">The reports are in the language folders.</span></span>

    **<span data-ttu-id="3de7b-122">注意</span><span class="sxs-lookup"><span data-stu-id="3de7b-122">Note</span></span>**  
    <span data-ttu-id="3de7b-123">如果 SQL Server Reporting Services （SSRS）配置为命名实例，则 URL 应类似于以下内容： http （s）：// &lt; *MBAMReportsServerName* &gt; ： &lt; *port* &gt; /Reports\_ &lt; *SSRSInstanceName*&gt;</span><span class="sxs-lookup"><span data-stu-id="3de7b-123">If SQL Server Reporting Services (SSRS) was configured as a named instance, the URL should resemble the following: http(s)://&lt; *MBAMReportsServerName*&gt;:&lt;*port*&gt;/Reports\_&lt;*SSRSInstanceName*&gt;</span></span>



~~~
**Note**  
If SSRS was not configured to use Secure Socket Layer (SSL), the URL for the reports will be set to HTTP instead of HTTPS when you install the MBAM Server. If you then go to the Administration and Monitoring Website (also known as Help Desk) and select a report, the following message appears: "Only Secure Content is Displayed." To show the report, click **Show All Content**.
~~~



6. <span data-ttu-id="3de7b-124">在配置了 "管理和监视网站" 功能的服务器上，运行 "**服务器管理器**"，浏览到 "**角色**"，然后选择 " **Web 服务器（iis）** &gt; **Internet 信息服务（iis）管理器**"。</span><span class="sxs-lookup"><span data-stu-id="3de7b-124">On the server where the Administration and Monitoring Website feature is configured, run **Server Manager**, browse to **Roles**, and then select **Web Server (IIS)** &gt; **Internet Information Services (IIS) Manager**.</span></span>

7. <span data-ttu-id="3de7b-125">在 "**连接**" 中，浏览到 " \* &lt; 计算机名称 &gt; \* "，然后选择 " **Sites** &gt; **Microsoft BitLocker 管理和监视**" 站点。</span><span class="sxs-lookup"><span data-stu-id="3de7b-125">In **Connections**, browse to *&lt;computer name&gt;* and select **Sites** &gt; **Microsoft BitLocker Administration and Monitoring**.</span></span> <span data-ttu-id="3de7b-126">验证是否列出以下内容：</span><span class="sxs-lookup"><span data-stu-id="3de7b-126">Verify that the following are listed:</span></span>

   -   **<span data-ttu-id="3de7b-127">MBAMAdministrationService</span><span class="sxs-lookup"><span data-stu-id="3de7b-127">MBAMAdministrationService</span></span>**

   -   **<span data-ttu-id="3de7b-128">MBAMComplianceStatusService</span><span class="sxs-lookup"><span data-stu-id="3de7b-128">MBAMComplianceStatusService</span></span>**

   -   **<span data-ttu-id="3de7b-129">MBAMRecoveryAndHardwareService</span><span class="sxs-lookup"><span data-stu-id="3de7b-129">MBAMRecoveryAndHardwareService</span></span>**

8. <span data-ttu-id="3de7b-130">在配置了管理和监视网站和自助服务门户的服务器上，使用管理凭据打开 web 浏览器。</span><span class="sxs-lookup"><span data-stu-id="3de7b-130">On the server where the Administration and Monitoring Website and Self-Service Portal are configured, open a web browser with administrative credentials.</span></span>

9. <span data-ttu-id="3de7b-131">浏览到以下网站，验证它们是否成功加载：</span><span class="sxs-lookup"><span data-stu-id="3de7b-131">Browse to the following websites to verify that they load successfully:</span></span>

   -   <span data-ttu-id="3de7b-132">https （s）：// &lt; *MBAMAdministrationServerName* &gt; ： &lt; *port* &gt; /HelpDesk/-确认导航和报告的每个链接</span><span class="sxs-lookup"><span data-stu-id="3de7b-132">https(s)://&lt;*MBAMAdministrationServerName*&gt;:&lt;*port*&gt;/HelpDesk/ - confirm each of the links for navigation and reports</span></span>

   -   <span data-ttu-id="3de7b-133">http （s）：// &lt; *MBAMAdministrationServerName* &gt; ： &lt; *port* &gt; /SelfService/</span><span class="sxs-lookup"><span data-stu-id="3de7b-133">http(s)://&lt; *MBAMAdministrationServerName*&gt;:&lt;*port*&gt;/SelfService/</span></span>

   **<span data-ttu-id="3de7b-134">注意</span><span class="sxs-lookup"><span data-stu-id="3de7b-134">Note</span></span>**  
   <span data-ttu-id="3de7b-135">假设您在没有网络加密的情况下在默认端口上配置了服务器功能。</span><span class="sxs-lookup"><span data-stu-id="3de7b-135">It is assumed that you configured the server features on the default port without network encryption.</span></span> <span data-ttu-id="3de7b-136">如果你在其他端口或虚拟目录上配置了服务器功能，请将 Url 更改为包含相应的端口，例如：</span><span class="sxs-lookup"><span data-stu-id="3de7b-136">If you configured the server features on a different port or virtual directory, change the URLs to include the appropriate port, for example:</span></span>

   <span data-ttu-id="3de7b-137">http （s）：// &lt; *主机名* &gt; ： &lt; *port* &gt; /HelpDesk/</span><span class="sxs-lookup"><span data-stu-id="3de7b-137">http(s)://&lt; *host name*&gt;:&lt;*port*&gt;/HelpDesk/</span></span>

   <span data-ttu-id="3de7b-138">http （s）：// &lt; *主机名* &gt; ： &lt; *port* &gt; / &lt; *virtualdirectory*&gt;/</span><span class="sxs-lookup"><span data-stu-id="3de7b-138">http(s)://&lt; *host name*&gt;:&lt;*port*&gt;/&lt;*virtualdirectory*&gt;/</span></span>

   <span data-ttu-id="3de7b-139">如果服务器功能配置了网络加密，请将 http://更改为 https://。</span><span class="sxs-lookup"><span data-stu-id="3de7b-139">If the server features were configured with network encryption, change http:// to https://.</span></span>



10. <span data-ttu-id="3de7b-140">浏览到以下 web 服务以验证它们是否已成功加载。</span><span class="sxs-lookup"><span data-stu-id="3de7b-140">Browse to the following web services to verify that they load successfully.</span></span> <span data-ttu-id="3de7b-141">将打开一个页面，指示该服务正在运行，但页面不显示任何元数据。</span><span class="sxs-lookup"><span data-stu-id="3de7b-141">A page opens to indicate that the service is running, but the page does not display any metadata.</span></span>

    -   <span data-ttu-id="3de7b-142">http （s）：// &lt; *MBAMAdministrationServerName* &gt; ： &lt; *port* &gt; /MBAMAdministrationService/AdministrationService.svc</span><span class="sxs-lookup"><span data-stu-id="3de7b-142">http(s)://&lt; *MBAMAdministrationServerName*&gt;:&lt;*port*&gt;/MBAMAdministrationService/AdministrationService.svc</span></span>

    -   <span data-ttu-id="3de7b-143">http （s）：// &lt; *MBAMAdministrationServerName* &gt; ： &lt; *port* &gt; /MBAMUserSupportService/UserSupportService.svc</span><span class="sxs-lookup"><span data-stu-id="3de7b-143">http(s)://&lt; *MBAMAdministrationServerName*&gt;:&lt;*port*&gt;/MBAMUserSupportService/UserSupportService.svc</span></span>

    -   <span data-ttu-id="3de7b-144">http （s）：// &lt; *MBAMAdministrationServerName* &gt; ： &lt; *port* &gt; /MBAMComplianceStatusService/StatusReportingService.svc</span><span class="sxs-lookup"><span data-stu-id="3de7b-144">http(s)://&lt; *MBAMAdministrationServerName*&gt;:&lt;*port*&gt;/MBAMComplianceStatusService/StatusReportingService.svc</span></span>

    -   <span data-ttu-id="3de7b-145">http （s）：// &lt; *MBAMAdministrationServerName* &gt; ： &lt; *port* &gt; /MBAMRecoveryAndHardwareService/CoreService.svc</span><span class="sxs-lookup"><span data-stu-id="3de7b-145">http(s)://&lt; *MBAMAdministrationServerName*&gt;:&lt;*port*&gt;/MBAMRecoveryAndHardwareService/CoreService.svc</span></span>

## <span data-ttu-id="3de7b-146">通过 Configuration Manager 集成拓扑验证 MBAM 服务器部署</span><span class="sxs-lookup"><span data-stu-id="3de7b-146">Validating the MBAM Server deployment with the Configuration Manager Integration topology</span></span>


<span data-ttu-id="3de7b-147">使用以下步骤通过 Configuration Manager 集成拓扑验证 MBAM 部署。</span><span class="sxs-lookup"><span data-stu-id="3de7b-147">Use the following steps to validate your MBAM deployment with the Configuration Manager Integration topology.</span></span> <span data-ttu-id="3de7b-148">完成与你正在使用的 Configuration Manager 版本相匹配的验证步骤。</span><span class="sxs-lookup"><span data-stu-id="3de7b-148">Complete the validation steps that match the version of Configuration Manager that you are using.</span></span>

### <a href="" id="validating-the-mbam-server-deployment-with-system-center-2012-configuration-manager-"></a><span data-ttu-id="3de7b-149">通过 System Center 2012 配置管理器验证 MBAM 服务器部署</span><span class="sxs-lookup"><span data-stu-id="3de7b-149">Validating the MBAM Server deployment with System Center 2012 Configuration Manager</span></span>

<span data-ttu-id="3de7b-150">将 MBAM 与 System Center 2012 Configuration Manager 配合使用时，请使用以下步骤验证 MBAM 服务器部署。</span><span class="sxs-lookup"><span data-stu-id="3de7b-150">Use these steps to validate your MBAM Server deployment when you are using MBAM with System Center 2012 Configuration Manager.</span></span>

**<span data-ttu-id="3de7b-151">验证 Configuration Manager 集成 MBAM Server 部署-System Center 2012 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="3de7b-151">To validate a Configuration Manager Integration MBAM Server deployment – System Center 2012 Configuration Manager</span></span>**

1.  <span data-ttu-id="3de7b-152">在部署 System Center 2012 配置管理器的服务器上，打开 **"控制面板**" 中的 "**程序和功能**"，然后验证是否显示 " **Microsoft BitLocker 管理和监视**"。</span><span class="sxs-lookup"><span data-stu-id="3de7b-152">On the server where System Center 2012 Configuration Manager is deployed, open **Programs and Features** in **Control Panel**, and verify that **Microsoft BitLocker Administration and Monitoring** appears.</span></span>

    **<span data-ttu-id="3de7b-153">注意</span><span class="sxs-lookup"><span data-stu-id="3de7b-153">Note</span></span>**  
    <span data-ttu-id="3de7b-154">若要验证配置，必须使用在每台服务器上具有本地计算机管理凭据的域帐户。</span><span class="sxs-lookup"><span data-stu-id="3de7b-154">To validate the configuration, you must use a domain account that has local computer administrative credentials on each server.</span></span>



2.  <span data-ttu-id="3de7b-155">在 Configuration Manager 控制台中，单击 "**资源" 和 "合规性**" 工作区 &gt; **设备集合**，并确认是否显示名为 " **MBAM 支持的计算机**" 的新集合。</span><span class="sxs-lookup"><span data-stu-id="3de7b-155">In the Configuration Manager console, click the **Assets and Compliance** workspace &gt; **Device Collections**, and confirm that a new collection called **MBAM Supported Computers** is displayed.</span></span>

3.  <span data-ttu-id="3de7b-156">在 Configuration Manager 控制台中，单击 "**监视**工作区 &gt; **报告** &gt; **报告** &gt; **MBAM**"。</span><span class="sxs-lookup"><span data-stu-id="3de7b-156">In the Configuration Manager console, click the **Monitoring** workspace &gt; **Reporting** &gt; **Reports** &gt; **MBAM**.</span></span>

4.  <span data-ttu-id="3de7b-157">验证**MBAM**文件夹是否包含具有表示不同语言的名称的子文件夹，以及每个语言子文件夹中列出了下列报表：</span><span class="sxs-lookup"><span data-stu-id="3de7b-157">Verify that the **MBAM** folder contains subfolders, with names that represent different languages, and that the following reports are listed in each language subfolder:</span></span>

    -   <span data-ttu-id="3de7b-158">BitLocker 计算机合规性</span><span class="sxs-lookup"><span data-stu-id="3de7b-158">BitLocker Computer Compliance</span></span>

    -   <span data-ttu-id="3de7b-159">BitLocker 企业合规性仪表板</span><span class="sxs-lookup"><span data-stu-id="3de7b-159">BitLocker Enterprise Compliance Dashboard</span></span>

    -   <span data-ttu-id="3de7b-160">BitLocker 企业合规性详细信息</span><span class="sxs-lookup"><span data-stu-id="3de7b-160">BitLocker Enterprise Compliance Details</span></span>

    -   <span data-ttu-id="3de7b-161">BitLocker 企业合规性摘要</span><span class="sxs-lookup"><span data-stu-id="3de7b-161">BitLocker Enterprise Compliance Summary</span></span>

5.  <span data-ttu-id="3de7b-162">在 Configuration Manager 控制台中，单击 "**资源和合规性**工作区 &gt; **合规性设置**" &gt; **配置基线**，并确认 "配置基线**BitLocker 保护**" 已列出。</span><span class="sxs-lookup"><span data-stu-id="3de7b-162">In the Configuration Manager console, click the **Assets and Compliance** workspace &gt; **Compliance Settings** &gt; **Configuration Baselines**, and confirm that the configuration baseline **BitLocker Protection** is listed.</span></span>

6.  <span data-ttu-id="3de7b-163">在 Configuration Manager 控制台中，单击 "**资源和合规性**工作区 &gt; **合规性设置**" &gt; **配置项目**，并确认显示以下新配置项目：</span><span class="sxs-lookup"><span data-stu-id="3de7b-163">In the Configuration Manager console, click the **Assets and Compliance** workspace &gt; **Compliance Settings** &gt; **Configuration Items**, and confirm that the following new configuration items are displayed:</span></span>

    -   <span data-ttu-id="3de7b-164">BitLocker 固定数据驱动器保护</span><span class="sxs-lookup"><span data-stu-id="3de7b-164">BitLocker Fixed Data Drives Protection</span></span>

    -   <span data-ttu-id="3de7b-165">BitLocker 操作系统驱动器保护</span><span class="sxs-lookup"><span data-stu-id="3de7b-165">BitLocker Operating System Drive Protection</span></span>

### <span data-ttu-id="3de7b-166">通过 Configuration Manager 2007 验证 MBAM 服务器部署</span><span class="sxs-lookup"><span data-stu-id="3de7b-166">Validating the MBAM Server deployment with Configuration Manager 2007</span></span>

<span data-ttu-id="3de7b-167">将 MBAM 与 Configuration Manager 2007 配合使用时，请使用以下步骤验证 MBAM 服务器部署。</span><span class="sxs-lookup"><span data-stu-id="3de7b-167">Use these steps to validate your MBAM Server deployment when you are using MBAM with Configuration Manager 2007.</span></span>

**<span data-ttu-id="3de7b-168">验证 Configuration Manager 集成 MBAM Server 部署-Configuration Manager 2007</span><span class="sxs-lookup"><span data-stu-id="3de7b-168">To validate a Configuration Manager Integration MBAM Server deployment – Configuration Manager 2007</span></span>**

1.  <span data-ttu-id="3de7b-169">在部署 Configuration Manager 2007 的服务器上，打开 "**控制面板**" 上的 "**程序和功能**"，然后验证是否显示 " **Microsoft BitLocker 管理和监视**"。</span><span class="sxs-lookup"><span data-stu-id="3de7b-169">On the server where Configuration Manager 2007 is deployed, open **Programs and Features** on **Control Panel** , and verify that **Microsoft BitLocker Administration and Monitoring** appears.</span></span>

    **<span data-ttu-id="3de7b-170">注意</span><span class="sxs-lookup"><span data-stu-id="3de7b-170">Note</span></span>**  
    <span data-ttu-id="3de7b-171">若要验证配置，必须使用在每台服务器上具有本地计算机管理凭据的域帐户。</span><span class="sxs-lookup"><span data-stu-id="3de7b-171">To validate the configuration, you must use a domain account that has local computer administrative credentials on each server.</span></span>



2.  <span data-ttu-id="3de7b-172">在 Configuration Manager 控制台中，单击 "**网站数据库 &lt; SiteCode &gt;  -  &lt; 服务器名 &gt; ， &lt; SiteName" &gt; ，"计算机管理**"，确认显示名为 " **MBAM 支持的计算机**" 的新集合。</span><span class="sxs-lookup"><span data-stu-id="3de7b-172">In the Configuration Manager console, click **Site Database &lt;SiteCode&gt; - &lt;ServerName&gt;, &lt;SiteName&gt;), Computer Management**, and confirm that a new collection called **MBAM Supported Computers** is displayed.</span></span>

3.  <span data-ttu-id="3de7b-173">在 Configuration Manager 控制台中，单击 "**报告** &gt; **服务** &gt; \*\* \\\\ &lt; 服务器 &gt; 名\*\* &gt; **报告文件夹** &gt; **MBAM**"。</span><span class="sxs-lookup"><span data-stu-id="3de7b-173">In the Configuration Manager console, click **Reporting** &gt; **Reporting Services** &gt; **\\\\&lt;ServerName&gt;** &gt; **Report Folders** &gt; **MBAM**.</span></span>

    <span data-ttu-id="3de7b-174">验证**MBAM**文件夹是否包含具有表示不同语言的名称的子文件夹，以及每个语言子文件夹中列出了下列报表：</span><span class="sxs-lookup"><span data-stu-id="3de7b-174">Verify that the **MBAM** folder contains subfolders, with names that represent different languages, and that the following reports are listed in each language subfolder:</span></span>

    -   <span data-ttu-id="3de7b-175">BitLocker 计算机合规性</span><span class="sxs-lookup"><span data-stu-id="3de7b-175">BitLocker Computer Compliance</span></span>

    -   <span data-ttu-id="3de7b-176">BitLocker 企业合规性仪表板</span><span class="sxs-lookup"><span data-stu-id="3de7b-176">BitLocker Enterprise Compliance Dashboard</span></span>

    -   <span data-ttu-id="3de7b-177">BitLocker 企业合规性详细信息</span><span class="sxs-lookup"><span data-stu-id="3de7b-177">BitLocker Enterprise Compliance Details</span></span>

    -   <span data-ttu-id="3de7b-178">BitLocker 企业合规性摘要</span><span class="sxs-lookup"><span data-stu-id="3de7b-178">BitLocker Enterprise Compliance Summary</span></span>

4.  <span data-ttu-id="3de7b-179">在 Configuration Manager 控制台中，单击 "**所需配置管理** &gt; **配置基线**"，然后确认 "配置基线**BitLocker 保护**" 已列出。</span><span class="sxs-lookup"><span data-stu-id="3de7b-179">In the Configuration Manager console, click **Desired Configuration Management** &gt; **Configuration Baselines**, and confirm that the configuration baseline **BitLocker Protection** is listed.</span></span>

5.  <span data-ttu-id="3de7b-180">在 Configuration Manager 控制台中，单击**所需的配置管理** &gt; **配置项目**，并确认显示以下新配置项目：</span><span class="sxs-lookup"><span data-stu-id="3de7b-180">In the Configuration Manager console, click **Desired Configuration Management** &gt; **Configuration Items**, and confirm that the following new configuration items are displayed:</span></span>

    -   <span data-ttu-id="3de7b-181">BitLocker 固定数据驱动器保护</span><span class="sxs-lookup"><span data-stu-id="3de7b-181">BitLocker Fixed Data Drives Protection</span></span>

    -   <span data-ttu-id="3de7b-182">BitLocker 操作系统驱动器保护</span><span class="sxs-lookup"><span data-stu-id="3de7b-182">BitLocker Operating System Drive Protection</span></span>



## <span data-ttu-id="3de7b-183">相关主题</span><span class="sxs-lookup"><span data-stu-id="3de7b-183">Related topics</span></span>


[<span data-ttu-id="3de7b-184">配置 MBAM 2.5 服务器功能</span><span class="sxs-lookup"><span data-stu-id="3de7b-184">Configuring the MBAM 2.5 Server Features</span></span>](configuring-the-mbam-25-server-features.md)


## <span data-ttu-id="3de7b-185">已获得 MBAM 的建议？</span><span class="sxs-lookup"><span data-stu-id="3de7b-185">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="3de7b-186">在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="3de7b-186">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="3de7b-187">对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="3de7b-187">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>






