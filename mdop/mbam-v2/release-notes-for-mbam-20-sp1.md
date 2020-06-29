---
title: MBAM 2.0 SP1 发行说明
description: MBAM 2.0 SP1 发行说明
author: dansimp
ms.assetid: b39002ba-33c6-45ec-9d1b-464327b60f5c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 54a77fc7a493b36217ae2cdc875226b25fdc6e7b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803797"
---
# <span data-ttu-id="c1066-103">MBAM 2.0 SP1 发行说明</span><span class="sxs-lookup"><span data-stu-id="c1066-103">Release Notes for MBAM 2.0 SP1</span></span>


<span data-ttu-id="c1066-104">若要搜索这些发行说明，请按 Ctrl + F。</span><span class="sxs-lookup"><span data-stu-id="c1066-104">To search these release notes, press Ctrl+F.</span></span>

<span data-ttu-id="c1066-105">安装 Microsoft BitLocker 管理和监视（MBAM） 2.0 Service Pack 1 （SP1）之前，请仔细阅读这些发行说明。</span><span class="sxs-lookup"><span data-stu-id="c1066-105">Read these release notes thoroughly before you install Microsoft BitLocker Administration and Monitoring (MBAM) 2.0 Service Pack 1 (SP1).</span></span> <span data-ttu-id="c1066-106">这些发行说明包含成功安装 BitLocker 管理和监视 2.0 SP1 所需的信息，其中包含产品文档中不可用的信息。</span><span class="sxs-lookup"><span data-stu-id="c1066-106">These release notes contain information that is required to successfully install BitLocker Administration and Monitoring 2.0 SP1, and they contain information that is not available in the product documentation.</span></span> <span data-ttu-id="c1066-107">如果这些发行说明和其他 MBAM 2.0 SP1 文档之间存在差异，则应将最新更改视为权威。</span><span class="sxs-lookup"><span data-stu-id="c1066-107">If there is a difference between these release notes and other MBAM 2.0 SP1 documentation, the latest change should be considered authoritative.</span></span> <span data-ttu-id="c1066-108">这些发行说明取代了本产品附带的内容。</span><span class="sxs-lookup"><span data-stu-id="c1066-108">These release notes supersede the content that is included with this product.</span></span>

## <a href="" id="---------mbam-2-0-sp1-known-issues"></a> <span data-ttu-id="c1066-109">MBAM 2.0 SP1 已知问题</span><span class="sxs-lookup"><span data-stu-id="c1066-109">MBAM 2.0 SP1 known issues</span></span>


<span data-ttu-id="c1066-110">本部分包含 MBAM 2.0 SP1 的已知问题。</span><span class="sxs-lookup"><span data-stu-id="c1066-110">This section contains known issues for MBAM 2.0 SP1.</span></span>

### <span data-ttu-id="c1066-111">将 Configuration Manager 集成拓扑的 MBAM 升级到 MBAM 2.0 SP1 需要手动删除 Configuration Manager 对象</span><span class="sxs-lookup"><span data-stu-id="c1066-111">Upgrade of MBAM with Configuration Manager Integrated topology to MBAM 2.0 SP1 requires manual removal of Configuration Manager objects</span></span>

<span data-ttu-id="c1066-112">如果你将 MBAM 与 Configuration Manager 配合使用，并且希望升级到 MBAM 2.0 SP1，则必须手动删除已安装到 Configuration Manager 的所有 Configuration Manager 对象，作为 MBAM 安装的一部分。</span><span class="sxs-lookup"><span data-stu-id="c1066-112">If you are using MBAM with Configuration Manager, and you want to upgrade to MBAM 2.0 SP1, you must manually remove all of the Configuration Manager objects that were installed into Configuration Manager as a part of the MBAM installation.</span></span> <span data-ttu-id="c1066-113">必须手动删除的对象包括 MBAM 报表、MBAM 支持的计算机集合以及 BitLocker 保护配置基线及其关联的配置项目。</span><span class="sxs-lookup"><span data-stu-id="c1066-113">The objects that you must manually remove are the MBAM reports, MBAM Supported Computers collection, and the BitLocker Protection Configuration Baseline and its associated configuration items.</span></span>

<span data-ttu-id="c1066-114">**解决方法**：通过完成以下步骤来升级 Configuration Manager 对象：</span><span class="sxs-lookup"><span data-stu-id="c1066-114">**Workaround**: Upgrade the Configuration Manager objects by completing the following steps:</span></span>

1.  <span data-ttu-id="c1066-115">将现有合规性数据备份到外部文件，如以下步骤中所述。</span><span class="sxs-lookup"><span data-stu-id="c1066-115">Back up existing compliance data to an external file, as described in the following steps.</span></span>

    <span data-ttu-id="c1066-116">**注意** 删除配置管理器中的现有基线后，所有现有的 BitLocker 合规性数据都将被删除。</span><span class="sxs-lookup"><span data-stu-id="c1066-116">**Note** All existing BitLocker compliance data will be deleted when you delete the existing baseline in Configuration Manager.</span></span> <span data-ttu-id="c1066-117">将随着时间的推移重新生成数据，但建议你保存数据的副本，以防需要特定计算机的合规性数据，然后再重新生成合规性数据。</span><span class="sxs-lookup"><span data-stu-id="c1066-117">The data will be regenerated over time, but it is recommended that you save a copy of the data in case you need the compliance data for a particular computer before the compliance data has been regenerated.</span></span>

     

    1.  <span data-ttu-id="c1066-118">若要保存已记录的 BitLocker 合规性数据，请打开 " **Bitlocker 企业合规性详细信息**" 报表。</span><span class="sxs-lookup"><span data-stu-id="c1066-118">To save historical BitLocker compliance data, open the **BitLocker Enterprise Compliance Details** Report.</span></span>

    2.  <span data-ttu-id="c1066-119">单击报表中的 "**保存**" 图标，然后选择 " **Excel**"。</span><span class="sxs-lookup"><span data-stu-id="c1066-119">Click the **Save** icon in the report and select **Excel**.</span></span>

        <span data-ttu-id="c1066-120">保存的报表将包含诸如计算机名、域名、合规性状态、豁免、设备用户、合规性状态详细信息和上次联系日期/时间等数据。</span><span class="sxs-lookup"><span data-stu-id="c1066-120">The saved report will contain data such as the computer name, domain name, compliance status, exemption, device users, compliance status details, and last contact date/time.</span></span> <span data-ttu-id="c1066-121">某些信息（如详细的卷信息和加密强度）将不会保存。</span><span class="sxs-lookup"><span data-stu-id="c1066-121">Some information, such as detailed volume information and encryption strength, are not saved.</span></span>

2.  <span data-ttu-id="c1066-122">通过使用**MBAM**安装程序从服务器卸载**MBAM** 。</span><span class="sxs-lookup"><span data-stu-id="c1066-122">Uninstall **MBAM** from the server by using the **MBAM** installer.</span></span>

3.  <span data-ttu-id="c1066-123">从配置管理器中手动删除以下对象：</span><span class="sxs-lookup"><span data-stu-id="c1066-123">Manually delete the following objects from Configuration Manager:</span></span>

    -   <span data-ttu-id="c1066-124">MBAM 支持的计算机集合</span><span class="sxs-lookup"><span data-stu-id="c1066-124">MBAM Supported Computers collection</span></span>

    -   <span data-ttu-id="c1066-125">BitLocker 保护基线</span><span class="sxs-lookup"><span data-stu-id="c1066-125">BitLocker Protection baseline</span></span>

    -   <span data-ttu-id="c1066-126">BitLocker 操作系统驱动器保护配置项目</span><span class="sxs-lookup"><span data-stu-id="c1066-126">BitLocker Operating System Drive Protection configuration item</span></span>

    -   <span data-ttu-id="c1066-127">BitLocker 固定数据驱动器保护配置项目</span><span class="sxs-lookup"><span data-stu-id="c1066-127">BitLocker Fixed Data Drives Protection configuration item</span></span>

4.  <span data-ttu-id="c1066-128">在 Configuration Manager SQL Server Reporting Services 网站中手动删除 MBAM 报表文件夹。</span><span class="sxs-lookup"><span data-stu-id="c1066-128">Manually delete the MBAM Reports folder in the Configuration Manager SQL Server Reporting Services site.</span></span> <span data-ttu-id="c1066-129">若要实现此目的，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c1066-129">To do this:</span></span>

    1.  <span data-ttu-id="c1066-130">使用 Internet Explorer 浏览到 reporting services 点，例如，http:// &lt; yourcmserver &gt; /reports。</span><span class="sxs-lookup"><span data-stu-id="c1066-130">Use Internet Explorer to browse to the reporting services point, for example, http://&lt;yourcmserver&gt;/reports.</span></span>

    2.  <span data-ttu-id="c1066-131">单击相应的 Configuration Manager "站点代码" 链接。</span><span class="sxs-lookup"><span data-stu-id="c1066-131">Click the appropriate Configuration Manager site code link.</span></span>

    3.  <span data-ttu-id="c1066-132">删除 MBAM 文件夹。</span><span class="sxs-lookup"><span data-stu-id="c1066-132">Delete the MBAM folder.</span></span>

5.  <span data-ttu-id="c1066-133">使用 MBAM 服务器安装程序重新安装 Configuration Manager 集成对象。</span><span class="sxs-lookup"><span data-stu-id="c1066-133">Use the MBAM Server installer to reinstall the Configuration Manager Integration objects.</span></span> <span data-ttu-id="c1066-134">客户端计算机将随着时间的推移再次开始上载 BitLocker 合规性数据。</span><span class="sxs-lookup"><span data-stu-id="c1066-134">The client computers will begin to upload BitLocker compliance data again over time.</span></span>

### <span data-ttu-id="c1066-135">自助服务门户上的 "提交" 按钮在 Internet Explorer10 中不起作用</span><span class="sxs-lookup"><span data-stu-id="c1066-135">Submit button on Self-Service Portal does not work in Internet Explorer10</span></span>

<span data-ttu-id="c1066-136">使用 Internet Explorer10 访问管理和监视网站时，网站上的 "**提交**" 按钮不起作用。</span><span class="sxs-lookup"><span data-stu-id="c1066-136">When you use Internet Explorer10 to access the Administration and Monitoring Website, the **Submit** button on the website does not work.</span></span>

<span data-ttu-id="c1066-137">**解决方法**：在安装了管理和监视网站的服务器上，安装[ASP.NET 浏览器定义文件的修复程序](https://go.microsoft.com/fwlink/?LinkId=317798)。</span><span class="sxs-lookup"><span data-stu-id="c1066-137">**Workaround**: On the server where you installed the Administration and Monitoring Website, install [Hotfix for ASP.NET browser definition files](https://go.microsoft.com/fwlink/?LinkId=317798).</span></span>

### <span data-ttu-id="c1066-138">不支持国际域名</span><span class="sxs-lookup"><span data-stu-id="c1066-138">International domain names are not supported</span></span>

<span data-ttu-id="c1066-139">MBAM 2.0 SP1 不支持国际域名。</span><span class="sxs-lookup"><span data-stu-id="c1066-139">MBAM 2.0 SP1 does not support international domain names.</span></span>

<span data-ttu-id="c1066-140">**解决方法**：无。</span><span class="sxs-lookup"><span data-stu-id="c1066-140">**Workaround**: None.</span></span>

### <span data-ttu-id="c1066-141">如果未在 SSRS 中配置 SSL，管理和监视网站中的报表将显示警告</span><span class="sxs-lookup"><span data-stu-id="c1066-141">Reports in the Administration and Monitoring website display a warning if SSL is not configured in SSRS</span></span>

<span data-ttu-id="c1066-142">如果未将 SQLServer Reporting Services （SSRS）配置为使用安全套接字层（SSL），则在安装 MBAM 服务器时，报表的 URL 将设置为 HTTP 而不是 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="c1066-142">If SQLServer Reporting Services (SSRS) was not configured to use Secure Socket Layer (SSL), the URL for the reports will be set to HTTP instead of HTTPS when you install the MBAM Server.</span></span> <span data-ttu-id="c1066-143">如果您随后浏览到 "管理和监视" 网站并选择一个报表，则会显示以下消息： "仅显示安全内容"。</span><span class="sxs-lookup"><span data-stu-id="c1066-143">If you then browse to the Administration and Monitoring website and select a report, the following message displays: “Only Secure Content is Displayed.”</span></span>

<span data-ttu-id="c1066-144">**解决方法**：若要解决此问题，请在安装了 SQLServer Reporting SERVICES 的 MBAM 服务器上的**Reporting Services 配置管理器**中配置 SSL。</span><span class="sxs-lookup"><span data-stu-id="c1066-144">**Workaround**: To correct this issue, configure SSL in **Reporting Services Configuration Manager** on the MBAM server where SQLServer Reporting Services is installed.</span></span> <span data-ttu-id="c1066-145">卸载并重新安装 "管理和监视服务器" 网站。</span><span class="sxs-lookup"><span data-stu-id="c1066-145">Uninstall and then reinstall the Administration and Monitoring Server website.</span></span>

### <span data-ttu-id="c1066-146">单击 "合规性摘要" 报表中的 "返回" 可能会产生错误</span><span class="sxs-lookup"><span data-stu-id="c1066-146">Clicking Back in the Compliance Summary report might create an error</span></span>

<span data-ttu-id="c1066-147">如果向下钻取到合规性摘要报表，然后单击 SSRS 报表中的**Back**链接，可能会出现错误。</span><span class="sxs-lookup"><span data-stu-id="c1066-147">If you drill down into a Compliance Summary report, and then click the **Back** link in the SSRS report, an error might occur.</span></span>

<span data-ttu-id="c1066-148">**解决方法**：无。</span><span class="sxs-lookup"><span data-stu-id="c1066-148">**Workaround**: None.</span></span>

### <span data-ttu-id="c1066-149">"仅使用空间" 加密不会正常工作</span><span class="sxs-lookup"><span data-stu-id="c1066-149">Used Space Only Encryption does not work correctly</span></span>

<span data-ttu-id="c1066-150">如果你在安装 MBAM 客户端后首次加密计算机，并且已将组策略对象设置为仅实现已使用的空间加密，则 MBAM 会错误地加密整个磁盘，而不是仅加密磁盘的已用空间。</span><span class="sxs-lookup"><span data-stu-id="c1066-150">If you encrypt a computer for the first time after you install the MBAM Client, and you have set a Group Policy Object to implement Used Space Only Encryption, MBAM erroneously encrypts the entire disk instead of encrypting only the disk’s used space.</span></span> <span data-ttu-id="c1066-151">如果在安装 MBAM 客户端之前已使用仅加密的计算机进行了加密，并且已设置了相同的已用空间 "仅加密组策略" 对象，则 MBAM 会识别该设置并在合规性报告中正确报告加密。</span><span class="sxs-lookup"><span data-stu-id="c1066-151">If a computer is already encrypted with Used Space Only Encryption before you install the MBAM Client, and you have set the same Used Space Only Encryption Group Policy Object, MBAM recognizes the setting and reports the encryption correctly in the compliance reports.</span></span>

<span data-ttu-id="c1066-152">**解决方法**：无。</span><span class="sxs-lookup"><span data-stu-id="c1066-152">**Workaround**: None.</span></span>

### <span data-ttu-id="c1066-153">密码强度在计算机合规性报告中显示不正确</span><span class="sxs-lookup"><span data-stu-id="c1066-153">Cipher strength displays incorrectly in the Computer Compliance report</span></span>

<span data-ttu-id="c1066-154">如果未在 "**选择驱动器加密方法" 和 "密码强度**" 组策略对象中设置特定的密码强度，则配置管理器集成拓扑中的 "计算机合规性报告" 将始终显示密码强度的 "**未知**"，即使密码强度使用默认值128位加密也是如此。</span><span class="sxs-lookup"><span data-stu-id="c1066-154">If you do not set a specific cipher strength in the **Choose drive encryption method and cipher strength** Group Policy Object, the Computer Compliance report in the Configuration Manager integrated topology always displays **Unknown** for the cipher strength, even when the cipher strength uses the default of 128-bit encryption.</span></span> <span data-ttu-id="c1066-155">如果在组策略对象中设置了特定的密码强度，则报表将显示正确的密码强度。</span><span class="sxs-lookup"><span data-stu-id="c1066-155">The report displays the correct cipher strength if you set a specific cipher strength in the Group Policy Object.</span></span>

<span data-ttu-id="c1066-156">**解决方法**：在 "**选择驱动器加密方法" 和 "密码强度**" 组策略对象中始终设置特定的密码强度。</span><span class="sxs-lookup"><span data-stu-id="c1066-156">**Workaround**: Always set a specific cipher strength in the **Choose drive encryption method and cipher strength** Group Policy Object.</span></span>

### <span data-ttu-id="c1066-157">合规性状态按驱动器类型分布在更新配置项目后显示旧数据</span><span class="sxs-lookup"><span data-stu-id="c1066-157">Compliance Status Distribution By Drive Type displays old data after you update configuration items</span></span>

<span data-ttu-id="c1066-158">在 SystemCenter2012 ConfigurationManager 中更新 MBAM 配置项目后，"BitLocker 企业合规性" 仪表板上的 "驱动器类型" 分布图中的合规性状态分布将显示基于来自旧版本的配置项目的信息的数据。</span><span class="sxs-lookup"><span data-stu-id="c1066-158">After you update MBAM configuration items in SystemCenter2012 ConfigurationManager, the Compliance Status Distribution By Drive Type bar chart on the BitLocker Enterprise Compliance Dashboard shows data that is based on information from old versions of the configuration items.</span></span>

<span data-ttu-id="c1066-159">**解决方法**：无。</span><span class="sxs-lookup"><span data-stu-id="c1066-159">**Workaround**: None.</span></span> <span data-ttu-id="c1066-160">不支持修改 MBAM 配置项目，并且报表可能不会按预期显示。</span><span class="sxs-lookup"><span data-stu-id="c1066-160">Modification of the MBAM configuration items is not supported, and the report might not appear as expected.</span></span>

### <span data-ttu-id="c1066-161">增强的安全配置可能导致报表显示不正确</span><span class="sxs-lookup"><span data-stu-id="c1066-161">Enhanced Security Configuration may cause reports to display incorrectly</span></span>

<span data-ttu-id="c1066-162">如果 Internet Explorer 增强的安全配置（ESC）处于打开状态，则当你尝试在 MBAM 服务器上查看报告时，可能会显示 "**拒绝访问**" 消息。</span><span class="sxs-lookup"><span data-stu-id="c1066-162">If Internet Explorer Enhanced Security Configuration (ESC) is turned on, an **Access Denied** message might appear when you try to view reports on the MBAM Server.</span></span> <span data-ttu-id="c1066-163">默认情况下，已启用增强的安全配置以保护服务器，方法是降低服务器对通过 web 内容和应用程序脚本可能发生的潜在攻击的影响。</span><span class="sxs-lookup"><span data-stu-id="c1066-163">By default, Enhanced Security Configuration is turned on to protect the server by decreasing the server’s exposure to potential attacks that can occur through web content and application scripts.</span></span>

<span data-ttu-id="c1066-164">**解决方法**：如果尝试在 MBAM 服务器上查看报告时出现**拒绝访问**消息，则可以在映像中设置组策略对象或手动更改默认设置，以禁用增强的安全配置。</span><span class="sxs-lookup"><span data-stu-id="c1066-164">**Workaround**: If the **Access Denied** message appears when you try to view reports on the MBAM Server, you can set a Group Policy Object or change the default manually in your image to disable Enhanced Security Configuration.</span></span> <span data-ttu-id="c1066-165">您也可以从其他计算机上查看未启用增强安全配置的报告。</span><span class="sxs-lookup"><span data-stu-id="c1066-165">You can also alternatively view the reports from another computer on which Enhanced Security Configuration is not enabled.</span></span>

### <a href="" id="-------------mbam-server-installation-fails-when-you-upgrade-from-sql-server-2008-to-sql-server-2012"></a> <span data-ttu-id="c1066-166">从 SQLServer2008 升级到 SQLServer2012 时，MBAM 服务器安装失败</span><span class="sxs-lookup"><span data-stu-id="c1066-166">MBAM Server installation fails when you upgrade from SQLServer2008 to SQLServer2012</span></span>

<span data-ttu-id="c1066-167">如果从 SQLServer2008 升级到 SQLServer2012，然后尝试安装合规性和审核数据库或恢复数据库，则安装将失败并回退。</span><span class="sxs-lookup"><span data-stu-id="c1066-167">If you upgrade from SQLServer2008 to SQLServer2012, and then try to install the Compliance and Audit Database or the Recovery Database, the installation fails and rolls back.</span></span> <span data-ttu-id="c1066-168">发生故障的原因是，在 SQLServer 升级期间删除了所需的 SQLCMD.exe 文件，但 MBAM 安装程序无法找到该文件。</span><span class="sxs-lookup"><span data-stu-id="c1066-168">The failure occurs because the required SQLCMD.exe file was removed during the SQLServer upgrade, and it cannot be found by the MBAM installer.</span></span> <span data-ttu-id="c1066-169">MSI 日志文件行可能看起来类似于以下内容：</span><span class="sxs-lookup"><span data-stu-id="c1066-169">The MSI log file lines may look similar to the following:</span></span>

<span data-ttu-id="c1066-170">RunDbInstallScript Recovery Db CA： BinDir-E:\\MSSQL\\100\\Tools\\Binn\\SqlCmd.exeRunDbInstallScript db ca： dbInstance-xxxxxx\\I01RunDbInstallScript sqlScript C:\\program files BitLocker 管理和 Files\\Microsoft\\Microsoft 恢复 Db CA： dbName-MONITORING\\SETUP\\KEYRECOVERY.SQLRUNDBINSTALLSCRIPT \ _Recovery \ _and \ _HardwareRunDbInstallScript 恢复 db ca： MBAM-defaultFileName \ _Recovery \ _and _HardwareRunDbInstallScript 恢复 Db CA： MBAM-defaultDataPathI01\\MSSQL\\DATA\\RunDbInstallScript Recovery Db CA： defaultLogPath-K:\\MSSQL\\MSSQL10。I01\\MSSQL\\Data\\RunDbInstallScript： scriptLogPath-C:\\Users\\xxxxxx\\AppData\\Local\\Temp\\InstallKeyComplianceDatabase.log-e-E S xxxxxxx\\I01-i "C:\\program files Files\\Microsoft\\Microsoft BitLocker 管理和 Monitoring\\Setup\\KeyRecovery.sql"-v DatabaseName = "MBAM \ _Recovery \ _and \ _Hardware" DefaultFileName = "MBAM _Recovery \ _and" DefaultDataPath = "F:\\MSSQL\\MSSQL10。I01\\MSSQL\\DATA\\ "DefaultLogPath =" K:\\MSSQL\\MSSQL10。I01\\MSSQL\\Data\\ "-o" C:\\Users\\xxxxxx\\AppData\\Local\\Temp\\InstallKeyComplianceDatabase.log "RunDbInstallScript 恢复数据库 CA：正在开始运行恢复数据库安装 scriptRunDbInstallScript 恢复数据库 CA： Sqlcmd 日志文件位于 C:\\Users\\xxxxxx\\AppData\\Local\\Temp\\\\InstallKeyRecoveryDatabase.logRunDbInstallScript 恢复数据库 CA 异常：安装恢复数据库自定义操作命令行输出异常：系统找不到指定的文件</span><span class="sxs-lookup"><span data-stu-id="c1066-170">RunDbInstallScript Recovery Db CA: BinDir - E:\\MSSQL\\100\\Tools\\Binn\\SqlCmd.exeRunDbInstallScript Recovery Db CA: dbInstance - xxxxxx\\I01RunDbInstallScript Recovery Db CA: sqlScript- C:\\Program Files\\Microsoft\\Microsoft BitLocker Administration and Monitoring\\Setup\\KeyRecovery.sqlRunDbInstallScript Recovery Db CA: dbName- MBAM\_Recovery\_and\_HardwareRunDbInstallScript Recovery Db CA: defaultFileName- MBAM\_Recovery\_and\_HardwareRunDbInstallScript Recovery Db CA: defaultDataPath- F:\\MSSQL\\MSSQL10.I01\\MSSQL\\DATA\\RunDbInstallScript Recovery Db CA: defaultLogPath- K:\\MSSQL\\MSSQL10.I01\\MSSQL\\Data\\RunDbInstallScript Recovery Db CA: scriptLogPath - C:\\Users\\xxxxxx\\AppData\\Local\\Temp\\InstallKeyComplianceDatabase.log-e -E -S xxxxxxx\\I01 -i "C:\\Program Files\\Microsoft\\Microsoft BitLocker Administration and Monitoring\\Setup\\KeyRecovery.sql" -v DatabaseName="MBAM\_Recovery\_and\_Hardware" DefaultFileName="MBAM\_Recovery\_and\_Hardware" DefaultDataPath="F:\\MSSQL\\MSSQL10.I01\\MSSQL\\DATA\\" DefaultLogPath="K:\\MSSQL\\MSSQL10.I01\\MSSQL\\Data\\" -o "C:\\Users\\xxxxxx\\AppData\\Local\\Temp\\InstallKeyComplianceDatabase.log"RunDbInstallScript Recovery Db CA:Starting to run the Recovery database install scriptRunDbInstallScript Recovery Db CA: Sqlcmd log file is located in C:\\Users\\xxxxxx\\AppData\\Local\\Temp\\\\InstallKeyRecoveryDatabase.logRunDbInstallScript Recovery Db CA Exception: Install Recovery database Custom Action command line output Exception: The system cannot find the file specified</span></span>

<span data-ttu-id="c1066-171">MBAM 服务器 Windows Installer 是硬编码的，可通过在 HKLM\\Software\\Microsoft\\Microsoft SQLServer\\100\\Tools\\ClientSetup. 下的注册表中查看 Path 字符串值来查找 SQLCMD.exe 路径。</span><span class="sxs-lookup"><span data-stu-id="c1066-171">The MBAM Server Windows Installer is hardcoded to find the SQLCMD.exe path by looking in the Path string value in the registry under HKLM\\Software\\Microsoft\\Microsoft SQLServer\\100\\Tools\\ClientSetup.</span></span> <span data-ttu-id="c1066-172">从 SQLServer2008 到 SQLServer2012 的迁移期间，该键仍然存在，但数据值引用的路径不包含 SQLCMD.exe 文件，因为 SQLupgrade 进程删除了该文件。</span><span class="sxs-lookup"><span data-stu-id="c1066-172">The key is still present during the migration from SQLServer2008 to SQLServer2012, but the path that is referenced by the data value does not contain the SQLCMD.exe file, because the SQLupgrade process removed the file.</span></span>

<span data-ttu-id="c1066-173">**解决方法**：将 HKLM\\Software\\Microsoft\\Microsoft SQLServer\\100\\Tools\\ClientSetup path 字符串值暂时重命名为**path \ _old**，然后再次在 MBAM 服务器上运行 Windows Installer。</span><span class="sxs-lookup"><span data-stu-id="c1066-173">**Workaround**: Temporarily rename the HKLM\\Software\\Microsoft\\Microsoft SQLServer\\100\\Tools\\ClientSetup path string value to **Path\_old**, and then run Windows Installer on the MBAM Server again.</span></span> <span data-ttu-id="c1066-174">当安装成功完成并在 SQLServer2012 中创建数据库时，请将**路径 \ _old**重命名为**path**。</span><span class="sxs-lookup"><span data-stu-id="c1066-174">When the installation completes successfully and creates the databases in SQLServer2012, rename **Path\_old** to **Path**.</span></span>

## <span data-ttu-id="c1066-175">适用于 MBAM 2.0 SP1 的修补程序和知识文库文章</span><span class="sxs-lookup"><span data-stu-id="c1066-175">Hotfixes and Knowledge Base articles for MBAM 2.0 SP1</span></span>


<span data-ttu-id="c1066-176">本部分包含适用于 MBAM 2.0 SP1 的修补程序和知识库文章。</span><span class="sxs-lookup"><span data-stu-id="c1066-176">This section contains hotfixes and KB articles for MBAM 2.0 SP1.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong><span data-ttu-id="c1066-177">知识库文章</span><span class="sxs-lookup"><span data-stu-id="c1066-177">KB Article</span></span></strong></th>
<th align="left"><span data-ttu-id="c1066-178">Title</span><span class="sxs-lookup"><span data-stu-id="c1066-178">Title</span></span></th>
<th align="left"><strong><span data-ttu-id="c1066-179">链接</span><span class="sxs-lookup"><span data-stu-id="c1066-179">Link</span></span></strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c1066-180">2831166</span><span class="sxs-lookup"><span data-stu-id="c1066-180">2831166</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1066-181">安装 Microsoft BitLocker 管理和监视（MBAM）2.0 失败， &quot; 已安装 System CENTER CM 对象&quot;</span><span class="sxs-lookup"><span data-stu-id="c1066-181">Installing Microsoft BitLocker Administration and Monitoring (MBAM) 2.0 fails with &quot;System Center CM Objects Already Installed&quot;</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2831166/EN-US" data-raw-source="[support.microsoft.com/kb/2831166/EN-US](https://support.microsoft.com/kb/2831166/EN-US)"><span data-ttu-id="c1066-182">support.microsoft.com/kb/2831166/EN-US</span><span class="sxs-lookup"><span data-stu-id="c1066-182">support.microsoft.com/kb/2831166/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c1066-183">2870849</span><span class="sxs-lookup"><span data-stu-id="c1066-183">2870849</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1066-184">用户无法使用 MBAM 2.0 自助服务门户检索 BitLocker 恢复密钥</span><span class="sxs-lookup"><span data-stu-id="c1066-184">Users cannot retrieve BitLocker Recovery key using MBAM2.0 Self Service Portal</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2870849/EN-US" data-raw-source="[support.microsoft.com/kb/2870849/EN-US](https://support.microsoft.com/kb/2870849/EN-US)"><span data-ttu-id="c1066-185">support.microsoft.com/kb/2870849/EN-US</span><span class="sxs-lookup"><span data-stu-id="c1066-185">support.microsoft.com/kb/2870849/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c1066-186">2756402</span><span class="sxs-lookup"><span data-stu-id="c1066-186">2756402</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1066-187">MBAM 客户端将失败，并出现事件描述中的事件 ID 4 和错误代码0x8004100E</span><span class="sxs-lookup"><span data-stu-id="c1066-187">MBAM client would fail with Event ID 4 and error code 0x8004100E in the Event description</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2756402/EN-US" data-raw-source="[support.microsoft.com/kb/2756402/EN-US](https://support.microsoft.com/kb/2756402/EN-US)"><span data-ttu-id="c1066-188">support.microsoft.com/kb/2756402/EN-US</span><span class="sxs-lookup"><span data-stu-id="c1066-188">support.microsoft.com/kb/2756402/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c1066-189">2620287</span><span class="sxs-lookup"><span data-stu-id="c1066-189">2620287</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1066-190">单击 MBAM 中的 "报表" 选项卡时，出现 "/Reports" 应用程序中的 "服务器错误" 错误消息</span><span class="sxs-lookup"><span data-stu-id="c1066-190">Error Message “Server Error in ‘/Reports’ Application” When You Click Reports Tab in MBAM</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2620287/EN-US" data-raw-source="[support.microsoft.com/kb/2620287/EN-US](https://support.microsoft.com/kb/2620287/EN-US)"><span data-ttu-id="c1066-191">support.microsoft.com/kb/2620287/EN-US</span><span class="sxs-lookup"><span data-stu-id="c1066-191">support.microsoft.com/kb/2620287/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c1066-192">2639518</span><span class="sxs-lookup"><span data-stu-id="c1066-192">2639518</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1066-193">在 MBAM 中打开企业或计算机合规性报告时出错</span><span class="sxs-lookup"><span data-stu-id="c1066-193">Error opening Enterprise or Computer Compliance Reports in MBAM</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2639518/EN-US" data-raw-source="[support.microsoft.com/kb/2639518/EN-US](https://support.microsoft.com/kb/2639518/EN-US)"><span data-ttu-id="c1066-194">support.microsoft.com/kb/2639518/EN-US</span><span class="sxs-lookup"><span data-stu-id="c1066-194">support.microsoft.com/kb/2639518/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c1066-195">2620269</span><span class="sxs-lookup"><span data-stu-id="c1066-195">2620269</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1066-196">MBAM 企业报告未获得更新</span><span class="sxs-lookup"><span data-stu-id="c1066-196">MBAM Enterprise Reporting Not Getting Updated</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2620269/EN-US" data-raw-source="[support.microsoft.com/kb/2620269/EN-US](https://support.microsoft.com/kb/2620269/EN-US)"><span data-ttu-id="c1066-197">support.microsoft.com/kb/2620269/EN-US</span><span class="sxs-lookup"><span data-stu-id="c1066-197">support.microsoft.com/kb/2620269/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c1066-198">2712461</span><span class="sxs-lookup"><span data-stu-id="c1066-198">2712461</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1066-199">不支持在域控制器上安装 MBAM</span><span class="sxs-lookup"><span data-stu-id="c1066-199">Installing MBAM on a Domain Controller is not supported</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2712461/EN-US" data-raw-source="[support.microsoft.com/kb/2712461/EN-US](https://support.microsoft.com/kb/2712461/EN-US)"><span data-ttu-id="c1066-200">support.microsoft.com/kb/2712461/EN-US</span><span class="sxs-lookup"><span data-stu-id="c1066-200">support.microsoft.com/kb/2712461/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c1066-201">2876732</span><span class="sxs-lookup"><span data-stu-id="c1066-201">2876732</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1066-202">在 MBAM 2.0 的独立或 Configuration Manager 集成设置期间收到错误代码0x80071a90</span><span class="sxs-lookup"><span data-stu-id="c1066-202">You receive error code 0x80071a90 during Standalone or Configuration Manager Integration setup of MBAM2.0</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2876732/EN-US" data-raw-source="[support.microsoft.com/kb/2876732/EN-US](https://support.microsoft.com/kb/2876732/EN-US)"><span data-ttu-id="c1066-203">support.microsoft.com/kb/2876732/EN-US</span><span class="sxs-lookup"><span data-stu-id="c1066-203">support.microsoft.com/kb/2876732/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c1066-204">2754259</span><span class="sxs-lookup"><span data-stu-id="c1066-204">2754259</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1066-205">MBAM 和安全网络通信</span><span class="sxs-lookup"><span data-stu-id="c1066-205">MBAM and Secure Network Communication</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2754259/EN-US" data-raw-source="[support.microsoft.com/kb/2754259/EN-US](https://support.microsoft.com/kb/2754259/EN-US)"><span data-ttu-id="c1066-206">support.microsoft.com/kb/2754259/EN-US</span><span class="sxs-lookup"><span data-stu-id="c1066-206">support.microsoft.com/kb/2754259/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c1066-207">2870842</span><span class="sxs-lookup"><span data-stu-id="c1066-207">2870842</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1066-208">MBAM 2.0 安装程序在 SQL Server 2008 的 Configuration Manager 集成方案期间失败</span><span class="sxs-lookup"><span data-stu-id="c1066-208">MBAM2.0 Setup fails during Configuration Manager Integration Scenario with SQL Server 2008</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2870842/EN-US" data-raw-source="[support.microsoft.com/kb/2870842/EN-US](https://support.microsoft.com/kb/2870842/EN-US)"><span data-ttu-id="c1066-209">support.microsoft.com/kb/2870842/EN-US</span><span class="sxs-lookup"><span data-stu-id="c1066-209">support.microsoft.com/kb/2870842/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c1066-210">2668533</span><span class="sxs-lookup"><span data-stu-id="c1066-210">2668533</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1066-211">如果 SQL SSRS 的配置不正确，MBAM 安装将失败</span><span class="sxs-lookup"><span data-stu-id="c1066-211">MBAM Setup fails if SQL SSRS is not configured properly</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2668533/EN-US" data-raw-source="[support.microsoft.com/kb/2668533/EN-US](https://support.microsoft.com/kb/2668533/EN-US)"><span data-ttu-id="c1066-212">support.microsoft.com/kb/2668533/EN-US</span><span class="sxs-lookup"><span data-stu-id="c1066-212">support.microsoft.com/kb/2668533/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c1066-213">2870847</span><span class="sxs-lookup"><span data-stu-id="c1066-213">2870847</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1066-214">MBAM 2.0 安装失败， &quot; 检索 &#39;Reporting Services 点&#39; 角色的 Configuration Manager 服务器角色设置时出错&quot;</span><span class="sxs-lookup"><span data-stu-id="c1066-214">MBAM 2.0 Setup fails with &quot;Error retrieving Configuration Manager Server role settings for &#39;Reporting Services Point&#39; role&quot;</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2870847/EN-US" data-raw-source="[support.microsoft.com/kb/2870847/EN-US](https://support.microsoft.com/kb/2870847/EN-US)"><span data-ttu-id="c1066-215">support.microsoft.com/kb/2870847/EN-US</span><span class="sxs-lookup"><span data-stu-id="c1066-215">support.microsoft.com/kb/2870847/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c1066-216">2870839</span><span class="sxs-lookup"><span data-stu-id="c1066-216">2870839</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1066-217">由于 SQL 作业 CreateCache 失败，MBAM 2.0 企业版报表不会在 MBAM 2.0 独立拓扑中刷新</span><span class="sxs-lookup"><span data-stu-id="c1066-217">MBAM2.0 Enterprise Reports are not refreshed in MBAM2.0 Standalone topology due to SQL job CreateCache failure</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2870839/EN-US" data-raw-source="[support.microsoft.com/kb/2870839/EN-US](https://support.microsoft.com/kb/2870839/EN-US)"><span data-ttu-id="c1066-218">support.microsoft.com/kb/2870839/EN-US</span><span class="sxs-lookup"><span data-stu-id="c1066-218">support.microsoft.com/kb/2870839/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c1066-219">2620269</span><span class="sxs-lookup"><span data-stu-id="c1066-219">2620269</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1066-220">MBAM 企业报告未获得更新</span><span class="sxs-lookup"><span data-stu-id="c1066-220">MBAM Enterprise Reporting Not Getting Updated</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2620269/EN-US" data-raw-source="[support.microsoft.com/kb/2620269/EN-US](https://support.microsoft.com/kb/2620269/EN-US)"><span data-ttu-id="c1066-221">support.microsoft.com/kb/2620269/EN-US</span><span class="sxs-lookup"><span data-stu-id="c1066-221">support.microsoft.com/kb/2620269/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c1066-222">2935997</span><span class="sxs-lookup"><span data-stu-id="c1066-222">2935997</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1066-223">MBAM 支持的计算机合规性报告不正确包括不支持的产品</span><span class="sxs-lookup"><span data-stu-id="c1066-223">MBAM Supported Computers compliance reporting incorrectly includes unsupported products</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2935997/EN-US" data-raw-source="[support.microsoft.com/kb/2935997/EN-US](https://support.microsoft.com/kb/2935997/EN-US)"><span data-ttu-id="c1066-224">support.microsoft.com/kb/2935997/EN-US</span><span class="sxs-lookup"><span data-stu-id="c1066-224">support.microsoft.com/kb/2935997/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c1066-225">2612822</span><span class="sxs-lookup"><span data-stu-id="c1066-225">2612822</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1066-226">MBAM 中的计算机记录被拒绝</span><span class="sxs-lookup"><span data-stu-id="c1066-226">Computer Record is Rejected in MBAM</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2612822/EN-US" data-raw-source="[support.microsoft.com/kb/2612822/EN-US](https://support.microsoft.com/kb/2612822/EN-US)"><span data-ttu-id="c1066-227">support.microsoft.com/kb/2612822/EN-US</span><span class="sxs-lookup"><span data-stu-id="c1066-227">support.microsoft.com/kb/2612822/EN-US</span></span></a></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="c1066-228">相关主题</span><span class="sxs-lookup"><span data-stu-id="c1066-228">Related topics</span></span>


[<span data-ttu-id="c1066-229">关于 MBAM 2.0 SP1</span><span class="sxs-lookup"><span data-stu-id="c1066-229">About MBAM 2.0 SP1</span></span>](about-mbam-20-sp1.md)

 

 





