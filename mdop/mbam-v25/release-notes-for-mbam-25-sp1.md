---
title: MBAM 2.5 SP1 的发行说明
description: MBAM 2.5 SP1 的发行说明
author: dansimp
ms.assetid: 3ac424c8-c490-4d62-aba4-1b462c02e962
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 09/06/2017
ms.openlocfilehash: 837892897aeca341433de54aca1228c0faeee124
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803678"
---
# <span data-ttu-id="006f3-103">MBAM 2.5 SP1 的发行说明</span><span class="sxs-lookup"><span data-stu-id="006f3-103">Release Notes for MBAM 2.5 SP1</span></span>


<span data-ttu-id="006f3-104">若要搜索这些发行说明，请按 Ctrl + F。</span><span class="sxs-lookup"><span data-stu-id="006f3-104">To search these release notes, press Ctrl+F.</span></span>

<span data-ttu-id="006f3-105">在安装 Microsoft BitLocker 管理和监视（MBAM） 2.5 SP1 之前，请仔细阅读这些发行说明。</span><span class="sxs-lookup"><span data-stu-id="006f3-105">Read these release notes thoroughly before you install Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 SP1.</span></span> <span data-ttu-id="006f3-106">这些发行说明包含成功安装 MBAM 所需的信息，并且可以包含产品文档中不可用的信息。</span><span class="sxs-lookup"><span data-stu-id="006f3-106">These release notes contain information that is required to successfully install MBAM and can contain information that is not available in the product documentation.</span></span> <span data-ttu-id="006f3-107">如果这些发行说明与其他 MBAM 2.5 SP1 文档不同，请考虑最新的更改为权威。</span><span class="sxs-lookup"><span data-stu-id="006f3-107">If these release notes differ from other MBAM 2.5 SP1 documentation, consider the latest change to be authoritative.</span></span> <span data-ttu-id="006f3-108">这些发行说明取代了本产品附带的内容。</span><span class="sxs-lookup"><span data-stu-id="006f3-108">These release notes supersede the content that is included with this product.</span></span>

## <a href="" id="---------mbam-2-5-sp1-known-issues"></a> <span data-ttu-id="006f3-109">MBAM 2.5 SP1 已知问题</span><span class="sxs-lookup"><span data-stu-id="006f3-109">MBAM 2.5 SP1 known issues</span></span>


<span data-ttu-id="006f3-110">本部分包含适用于 MBAM 2.5 SP1 的发行说明。</span><span class="sxs-lookup"><span data-stu-id="006f3-110">This section contains release notes for MBAM 2.5 SP1.</span></span>

### <a href="" id="powershell-read-ad--cmdlets-do-not-provide-feedback-if-user-does-not-have-sufficient-rights"></a><span data-ttu-id="006f3-111">如果用户没有足够的权限，PowerShell Read-AD \ \* cmdlet 不提供反馈</span><span class="sxs-lookup"><span data-stu-id="006f3-111">PowerShell Read-AD\* cmdlets do not provide feedback if user does not have sufficient rights</span></span>

<span data-ttu-id="006f3-112">如果尝试对 MBAM 服务器使用 PowerShell Read-AD \ \* cmdlet 的用户没有读取 Active Directory 恢复信息或读取 TPM 信息的用户权限，则 cmdlet 将不会向用户提供任何错误或警告。</span><span class="sxs-lookup"><span data-stu-id="006f3-112">If a user trying to use the PowerShell Read-AD\* cmdlets for the MBAM Server does not have user rights to read the Active Directory recovery information or to read the TPM information, the cmdlets will not provide the user with any error or warning.</span></span>

<span data-ttu-id="006f3-113">**解决方法：** 如果你拥有所需的用户权限，请仅使用 PowerShell Read AD \* cmdlet。</span><span class="sxs-lookup"><span data-stu-id="006f3-113">**Workaround:** Only use the PowerShell Read-AD\* cmdlets if you have the required user rights.</span></span>

### <span data-ttu-id="006f3-114">MBAM Active Directory （AD）迁移 cmdlet 不检索卷恢复信息</span><span class="sxs-lookup"><span data-stu-id="006f3-114">MBAM Active Directory (AD) Migration cmdlets do not retrieve volume recovery information</span></span>

<span data-ttu-id="006f3-115">MBAM Active Directory （AD）迁移 cmdlet 无法检索组织单位（Ou）中的计算机的卷恢复信息，前提是 "正斜杠字符（/）" 是组织单位名称的一部分。</span><span class="sxs-lookup"><span data-stu-id="006f3-115">MBAM Active Directory (AD) Migration cmdlets fail to retrieve volume recovery information for computers in organizational units (OUs) if the forward slash character (/) is part of the OU name.</span></span> <span data-ttu-id="006f3-116">当遇到此错误时，重复的广告拉将失败，并出现管道终止错误。</span><span class="sxs-lookup"><span data-stu-id="006f3-116">Repeated AD pulls will fail with a pipeline terminating error when this error is encountered.</span></span>

<span data-ttu-id="006f3-117">**技术详细信息：** 运行命令时，您将看到此错误：</span><span class="sxs-lookup"><span data-stu-id="006f3-117">**Technical Details:** You will see this error when running the command:</span></span>

``` syntax
Read-ADRecoveryInformation : Unknown error (0x80005000)
At line:1 char:1
+ Read-ADRecoveryInformation -Server "…" -SearchBase " ...
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : NotSpecified: (:) [Read-ADRecoveryInformation], COMException
    + FullyQualifiedErrorId : System.Runtime.InteropServices.COMException,Microsoft.Mbam.Server.Commands.ADPullCommands.ReadADRecoveryInformationCommand
```

<span data-ttu-id="006f3-118">此外，异常堆栈跟踪 `Error[0].Exception.StackTrace` 将如下所示：</span><span class="sxs-lookup"><span data-stu-id="006f3-118">In addition, the Exception stack trace `Error[0].Exception.StackTrace` will look like this:</span></span>

``` syntax
   at System.DirectoryServices.DirectoryEntry.Bind(Boolean throwIfFail)
   at System.DirectoryServices.DirectoryEntry.Bind()
   at System.DirectoryServices.DirectoryEntry.get_AdsObject()
   at System.DirectoryServices.PropertyValueCollection.PopulateList()
   at System.DirectoryServices.PropertyValueCollection..ctor(DirectoryEntry entry, String propertyName)
   at System.DirectoryServices.PropertyCollection.get_Item(String propertyName)
   at Microsoft.Mbam.Server.Commands.ADPullCommands.ReadCore.VerifySettingsConnectivity()
   at Microsoft.Mbam.Server.Commands.ADPullCommands.ReadCore.ExecuteRead()
   at Microsoft.Mbam.Server.Commands.ADPullCommands.ReadADInformationBase.ProcessRecord()
   at System.Management.Automation.CommandProcessor.ProcessRecord()
```

<span data-ttu-id="006f3-119">**解决方法：** 若要解决此问题，请执行以下任务之一：</span><span class="sxs-lookup"><span data-stu-id="006f3-119">**Workaround:** Perform one of these tasks to resolve this situation:</span></span>

-   <span data-ttu-id="006f3-120">重命名 OU 以删除正斜杠字符，然后运行脚本。</span><span class="sxs-lookup"><span data-stu-id="006f3-120">Rename the OU to remove the forward slash character and then run the script.</span></span>

-   <span data-ttu-id="006f3-121">若要从备份过程中排除任何有问题的 OU，请查找名称不包含正斜杠字符的 Ou 的列表。</span><span class="sxs-lookup"><span data-stu-id="006f3-121">To exclude any problematic OU from the backup process, find a list of OUs whose names do not contain the forward slash character.</span></span> <span data-ttu-id="006f3-122">对这些 Ou 运行脚本，一次一个 OU。</span><span class="sxs-lookup"><span data-stu-id="006f3-122">Run the script on these OUs, one OU at a time.</span></span>

### <a href="" id="-------------mbam-fails-to-encrypt-a-volume-and-reports-an-error-if-you-set-a-tpm---pin-protector-on-a-tablet-device"></a> <span data-ttu-id="006f3-123">如果在平板电脑上设置 TPM + 引脚保护器，MBAM 无法加密卷并报告错误</span><span class="sxs-lookup"><span data-stu-id="006f3-123">MBAM fails to encrypt a volume and reports an error if you set a TPM + PIN protector on a tablet device</span></span>

<span data-ttu-id="006f3-124">如果最终用户尝试在平板电脑上设置 TPM + PIN 保护程序，MBAM 无法加密，并且会报告错误。</span><span class="sxs-lookup"><span data-stu-id="006f3-124">If end users try to set a TPM + PIN protector on a tablet device, MBAM fails to encrypt, and it reports an error.</span></span> <span data-ttu-id="006f3-125">出现此问题的原因是平板电脑设备没有预引导环境键盘。</span><span class="sxs-lookup"><span data-stu-id="006f3-125">This issue occurs because tablet devices do not have a pre-boot environment keyboard.</span></span>

<span data-ttu-id="006f3-126">**解决方法：** 启用 "**启用 BitLocker 身份验证，需要在平板电脑组上预启动键盘输入"** 策略设置。</span><span class="sxs-lookup"><span data-stu-id="006f3-126">**Workaround:** Enable the **Enable use of BitLocker authentication requiring preboot keyboard input on tablets** Group Policy setting.</span></span> <span data-ttu-id="006f3-127">此设置是 BitLocker 组策略设置，在 MBAM 组策略模板中不可用。</span><span class="sxs-lookup"><span data-stu-id="006f3-127">This setting is a BitLocker Group Policy setting and is not available in the MBAM Group Policy Templates.</span></span>

### <span data-ttu-id="006f3-128">所有服务帐户都需要用户主体名称</span><span class="sxs-lookup"><span data-stu-id="006f3-128">User principal name is required for all service accounts</span></span>

<span data-ttu-id="006f3-129">必须为 MBAM 中的所有服务帐户设置用户主体名称（UPN）。</span><span class="sxs-lookup"><span data-stu-id="006f3-129">A user principal name (UPN) must be set for all service accounts in MBAM.</span></span> <span data-ttu-id="006f3-130">如果无法为帐户创建 UPN，则在配置过程中会出现一条错误消息，指示在 Active Directory 中找不到该用户或组。</span><span class="sxs-lookup"><span data-stu-id="006f3-130">If you fail to create a UPN for an account, an error message appears during the configuration process to indicate that the user or group could not be found in Active Directory.</span></span>

<span data-ttu-id="006f3-131">**解决方法：** 将 UPN 添加到服务帐户。</span><span class="sxs-lookup"><span data-stu-id="006f3-131">**Workaround:** Add the UPN to the service account.</span></span>

### <span data-ttu-id="006f3-132">在将 IIS 升级到 .NET Framework 4.5 后，自助服务门户和管理和监视网站不会打开</span><span class="sxs-lookup"><span data-stu-id="006f3-132">Self-Service Portal and the Administration and Monitoring Website do not open after you upgrade IIS to .NET Framework 4.5</span></span>

<span data-ttu-id="006f3-133">将 Internet 信息服务（IIS）升级到 Microsoft .NET Framework 4.5 时，无法打开自助服务门户和管理和监视网站。</span><span class="sxs-lookup"><span data-stu-id="006f3-133">When you upgrade Internet Information Services (IIS) to the Microsoft .NET Framework 4.5, the Self-Service Portal and the Administration and Monitoring Website do not open.</span></span>

<span data-ttu-id="006f3-134">**解决方法：** 在[安装 .Net Framework 4.0 后，请参阅文章错误消息： "无法加载类型 ' system.servicemodel. HttpModule '](https://go.microsoft.com/fwlink/?LinkId=393568)。</span><span class="sxs-lookup"><span data-stu-id="006f3-134">**Workaround:** See the article [Error message after you install the .NET Framework 4.0: "Could not load type 'System.ServiceModel.Activation.HttpModule'](https://go.microsoft.com/fwlink/?LinkId=393568).</span></span>

### <span data-ttu-id="006f3-135">管理和监视网站在未配置报表时显示 "找不到报表" 错误消息</span><span class="sxs-lookup"><span data-stu-id="006f3-135">Administration and Monitoring Website displays a "Report cannot be found" error message when Reports are not configured</span></span>

<span data-ttu-id="006f3-136">如果您配置了管理和监控网站，然后尝试查看报表但没有配置报表功能，则会出现一条错误消息，指示无法找到报表。</span><span class="sxs-lookup"><span data-stu-id="006f3-136">If you configure the Administration and Monitoring Website and then try to view a report without configuring the Reports feature first, an error message indicates that the report cannot be found.</span></span>

<span data-ttu-id="006f3-137">**解决方法：** 配置 web 应用程序之前，请先配置报表功能。</span><span class="sxs-lookup"><span data-stu-id="006f3-137">**Workaround:** Configure the Reports feature before you configure the web applications.</span></span>

### <span data-ttu-id="006f3-138">如果未在 SSRS 中配置 SSL，管理和监视网站中的报表将显示警告</span><span class="sxs-lookup"><span data-stu-id="006f3-138">Reports in the Administration and Monitoring Website display a warning if SSL is not configured in SSRS</span></span>

<span data-ttu-id="006f3-139">如果 SQL Server Reporting Services （SSRS）未配置为使用安全套接字层（SSL），则当你配置 MBAM 服务器时，"报告" 功能的 URL 将设置为 HTTP 而不是 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="006f3-139">If SQL Server Reporting Services (SSRS) was not configured to use Secure Socket Layer (SSL), the URL for the Reports feature will be set to HTTP instead of to HTTPS when you configure the MBAM Server.</span></span> <span data-ttu-id="006f3-140">如果随后打开 "管理和监视" 网站并选择报表，则会显示以下错误消息： "仅显示安全内容"。</span><span class="sxs-lookup"><span data-stu-id="006f3-140">If you then open the Administration and Monitoring Website and select a report, the following error message appears: "Only Secure Content is Displayed."</span></span>

<span data-ttu-id="006f3-141">**解决方法：** 若要显示报表，请单击 "**显示所有内容**"。</span><span class="sxs-lookup"><span data-stu-id="006f3-141">**Workaround:** To show the report, click **Show All Content**.</span></span> <span data-ttu-id="006f3-142">若要解决此问题，请转到安装了 SQL Server Reporting Services 的 MBAM 计算机，运行**Reporting Services 配置管理器**，然后单击 " **Web 服务 URL**"。</span><span class="sxs-lookup"><span data-stu-id="006f3-142">To correct this issue, go to the MBAM computer where SQL Server Reporting Services is installed, run **Reporting Services Configuration Manager**, and then click **Web Service URL**.</span></span> <span data-ttu-id="006f3-143">为服务器选择相应的 SSL 证书，输入相应的 SSL 端口（默认端口为443），然后单击 "**应用**"。</span><span class="sxs-lookup"><span data-stu-id="006f3-143">Select the appropriate SSL certificate for the server, enter the appropriate SSL port (the default port is 443), and then click **Apply**.</span></span>

### <span data-ttu-id="006f3-144">单击 "BitLocker 合规性摘要" 报告中的 "后退" 可能会引发错误</span><span class="sxs-lookup"><span data-stu-id="006f3-144">Clicking "Back" in the BitLocker Compliance Summary report might throw an error</span></span>

<span data-ttu-id="006f3-145">如果向下钻取到 BitLocker 合规性摘要报告，然后单击 SSRS 报表中的**Back**链接，可能会引发错误。</span><span class="sxs-lookup"><span data-stu-id="006f3-145">If you drill down into a BitLocker Compliance Summary report, and then click the **Back** link in the SSRS report, an error might be thrown.</span></span>

<span data-ttu-id="006f3-146">**解决方法：** 尚.</span><span class="sxs-lookup"><span data-stu-id="006f3-146">**Workaround:** None.</span></span>

### <span data-ttu-id="006f3-147">密码强度在 BitLocker 计算机合规性报告上显示不正确</span><span class="sxs-lookup"><span data-stu-id="006f3-147">Cipher strength displays incorrectly on the BitLocker Computer Compliance report</span></span>

<span data-ttu-id="006f3-148">如果未在 "**选择驱动器加密方法" 和 "密码强度**" 组策略对象中设置特定的密码强度，则配置管理器集成拓扑中的 BitLocker 计算机合规性报告始终显示密码强度的 "unknown"，即使密码强度使用默认的128位加密也是如此。</span><span class="sxs-lookup"><span data-stu-id="006f3-148">If you do not set a specific cipher strength in the **Choose drive encryption method and cipher strength** Group Policy Object, the BitLocker Computer Compliance report in the Configuration Manager Integration topology always displays "unknown" for the cipher strength, even when the cipher strength uses the default of 128-bit encryption.</span></span> <span data-ttu-id="006f3-149">如果在组策略对象中设置了特定的密码强度，则报表将显示正确的密码强度。</span><span class="sxs-lookup"><span data-stu-id="006f3-149">The report displays the correct cipher strength if you set a specific cipher strength in the Group Policy Object.</span></span>

<span data-ttu-id="006f3-150">**解决方法：** 在 "**选择驱动器加密方法" 和 "密码强度**" 组策略对象中始终设置特定的密码强度。</span><span class="sxs-lookup"><span data-stu-id="006f3-150">**Workaround:** Always set a specific cipher strength in the **Choose drive encryption method and cipher strength** Group Policy Object.</span></span>

### <span data-ttu-id="006f3-151">合规性状态按驱动器类型分布在更新配置项目后显示旧数据</span><span class="sxs-lookup"><span data-stu-id="006f3-151">Compliance Status Distribution By Drive Type displays old data after you update configuration items</span></span>

<span data-ttu-id="006f3-152">在 SystemCenter2012 ConfigurationManager 中更新 MBAM 配置项目后，"BitLocker 企业合规性" 仪表板上的 "驱动器类型" 分布图中的合规性状态分布将显示基于来自旧版本的配置项目的信息的数据。</span><span class="sxs-lookup"><span data-stu-id="006f3-152">After you update MBAM configuration items in SystemCenter2012 ConfigurationManager, the Compliance Status Distribution By Drive Type bar chart on the BitLocker Enterprise Compliance Dashboard shows data that is based on information from old versions of the configuration items.</span></span>

<span data-ttu-id="006f3-153">**解决方法：** 尚.</span><span class="sxs-lookup"><span data-stu-id="006f3-153">**Workaround:** None.</span></span> <span data-ttu-id="006f3-154">不支持修改 MBAM 配置项目，并且报表可能不会按预期显示。</span><span class="sxs-lookup"><span data-stu-id="006f3-154">Modification of the MBAM configuration items is not supported, and the report might not appear as expected.</span></span>

### <span data-ttu-id="006f3-155">增强的安全配置可能会导致报表不能正确显示错误消息</span><span class="sxs-lookup"><span data-stu-id="006f3-155">Enhanced Security Configuration might cause reports to display an error message incorrectly</span></span>

<span data-ttu-id="006f3-156">如果 Internet Explorer 增强的安全配置（ESC）处于打开状态，则当你尝试在 MBAM 服务器上查看报告时可能会显示 "拒绝访问" 错误消息。</span><span class="sxs-lookup"><span data-stu-id="006f3-156">If Internet Explorer Enhanced Security Configuration (ESC) is turned on, an "Access Denied" error message might appear when you try to view reports on the MBAM Server.</span></span> <span data-ttu-id="006f3-157">默认情况下，按 ESC 可保护服务器，方法是降低服务器对通过 web 内容和应用程序脚本可能发生的潜在攻击的影响。</span><span class="sxs-lookup"><span data-stu-id="006f3-157">By default, ESC is turned on to protect the server by decreasing the server’s exposure to potential attacks that can occur through web content and application scripts.</span></span>

<span data-ttu-id="006f3-158">**解决方法：** 如果尝试在 MBAM 服务器上查看报告时出现 "拒绝访问" 错误消息，则可以在映像中设置组策略对象或手动更改默认设置，以禁用增强的安全配置。</span><span class="sxs-lookup"><span data-stu-id="006f3-158">**Workaround:** If the "Access Denied" error message appears when you try to view reports on the MBAM Server, you can set a Group Policy Object or change the default manually in your image to disable Enhanced Security Configuration.</span></span> <span data-ttu-id="006f3-159">您也可以从另一台计算机上查看未启用 ESC 的报告。</span><span class="sxs-lookup"><span data-stu-id="006f3-159">You can also alternatively view the reports from another computer on which ESC is not enabled.</span></span>

### <span data-ttu-id="006f3-160">支持 Bitlocker XTS-AES 加密算法</span><span class="sxs-lookup"><span data-stu-id="006f3-160">Support for Bitlocker XTS-AES encryption algorithm</span></span>
<span data-ttu-id="006f3-161">Bitlocker 添加了对 Windows 10 版本1511中的 XTS 加密算法的支持。</span><span class="sxs-lookup"><span data-stu-id="006f3-161">Bitlocker added support for the XTS-AES encryption algorithm in Windows 10, version 1511.</span></span> <span data-ttu-id="006f3-162">通过 HF02、MBAM 添加了适用于此 Bitlocker 选项和 HF04 中的客户端支持，添加了服务器端支持。</span><span class="sxs-lookup"><span data-stu-id="006f3-162">With HF02, MBAM added client support for this Bitlocker option and in HF04, the server-side support was added.</span></span> <span data-ttu-id="006f3-163">但是，有一个已知的限制：</span><span class="sxs-lookup"><span data-stu-id="006f3-163">However, there is one known limitation:</span></span>

* <span data-ttu-id="006f3-164">客户必须对同一台计算机上的操作系统和数据量使用相同的加密强度。</span><span class="sxs-lookup"><span data-stu-id="006f3-164">Customers must use the same encryption strength for OS and data volumes on the same machine.</span></span>
<span data-ttu-id="006f3-165">如果使用不同的加密强度，MBAM 会将计算机报告为**不合规**。</span><span class="sxs-lookup"><span data-stu-id="006f3-165">If different encryption strengths are used, MBAM will report the machine as **non-compliant**.</span></span>

### <span data-ttu-id="006f3-166">自助服务门户会自动在键 ID 条目上添加 "-"</span><span class="sxs-lookup"><span data-stu-id="006f3-166">Self-Service Portal automatically adds "-" on Key ID entry</span></span>
<span data-ttu-id="006f3-167">自 HF02 到 MBAM，Portal 会自动在键 ID 条目上添加 "-"。</span><span class="sxs-lookup"><span data-stu-id="006f3-167">As of HF02, the MBAM Self-Service Portal automatically adds the '-' on Key ID entry.</span></span>  
<span data-ttu-id="006f3-168">**注意：** 必须重新配置服务器才能使 Javascript 生效。</span><span class="sxs-lookup"><span data-stu-id="006f3-168">**Note:** The Server has to be reconfigured for the Javascript to take effect.</span></span>

### <span data-ttu-id="006f3-169">MBAM 2.5 Sp1 报告无法正常工作/呈现</span><span class="sxs-lookup"><span data-stu-id="006f3-169">MBAM 2.5 Sp1 Reports does not work / render properly</span></span>
<span data-ttu-id="006f3-170">当 SSRS 托管在 SQL Server 2016 edition 上时，"报表" 页面不会正确呈现。</span><span class="sxs-lookup"><span data-stu-id="006f3-170">Reports Page does not render properly when SSRS is hosted on SQL Server 2016 edition.</span></span> 
<span data-ttu-id="006f3-171">例如，浏览到 "帮助台"-单击 "报表"-（突出显示部分在其上有 "x"）使用 Fiddler 尽情这一功能-如果单击 "报表"，它看起来就像是使用 HTML 4.0 呈现格式调用 SSRS 页面。</span><span class="sxs-lookup"><span data-stu-id="006f3-171">For example – Browsing to Helpdesk – Clicking on Reports – ( Highlighted portion have “x” on it ) Digging this further with Fiddler – it does look like once we click on Reports – it calls the SSRS page with HTML 4.0 rendering format.</span></span>

<span data-ttu-id="006f3-172">**解决方法：** 查看网站。主代码并注意 X-UA 模式是 IE8。</span><span class="sxs-lookup"><span data-stu-id="006f3-172">**Workaround:** Looking at the site.master code and noticed the X-UA mode was dictated as IE8.</span></span> <span data-ttu-id="006f3-173">作为 IE8 在生命周期结束，客户使用 IE11。</span><span class="sxs-lookup"><span data-stu-id="006f3-173">As IE8 is WAY past the end of life, and customer is using IE11.</span></span> <span data-ttu-id="006f3-174">将设置更新为以下代码。</span><span class="sxs-lookup"><span data-stu-id="006f3-174">Update the setting to the below code.</span></span> <span data-ttu-id="006f3-175">这使网站能够利用 IE11 呈现技术</span><span class="sxs-lookup"><span data-stu-id="006f3-175">This allows the site to utilize IE11 rendering technologies</span></span>

    <meta http-equiv="X-UA-Compatible" content="IE=Edge" />

<span data-ttu-id="006f3-176">原始设置为：</span><span class="sxs-lookup"><span data-stu-id="006f3-176">Original setting is:</span></span> 

    <meta http-equiv="X-UA-Compatible" content="IE=8" />


<span data-ttu-id="006f3-177">这是与其他浏览器（如 Chrome、Firefox 等）看不到此问题的原因。</span><span class="sxs-lookup"><span data-stu-id="006f3-177">This is the reason why the issue was not seen with other browsers like Chrome, Firefox etc.</span></span>



## <span data-ttu-id="006f3-178">相关主题</span><span class="sxs-lookup"><span data-stu-id="006f3-178">Related topics</span></span>


[<span data-ttu-id="006f3-179">关于 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="006f3-179">About MBAM 2.5</span></span>](about-mbam-25.md)

 

## <span data-ttu-id="006f3-180">已获得 MBAM 的建议？</span><span class="sxs-lookup"><span data-stu-id="006f3-180">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="006f3-181">在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="006f3-181">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="006f3-182">对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="006f3-182">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





