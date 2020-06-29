---
title: MBAM 2.5 的发行说明
description: MBAM 2.5 的发行说明
author: dansimp
ms.assetid: fcaf03e6-5e39-4771-af3c-a3cd468f3961
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 4bcc17d6295b14a7f3276146d5630b869b94b7f0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803677"
---
# <span data-ttu-id="8a4ad-103">MBAM 2.5 的发行说明</span><span class="sxs-lookup"><span data-stu-id="8a4ad-103">Release Notes for MBAM 2.5</span></span>


<span data-ttu-id="8a4ad-104">若要搜索这些发行说明，请按 Ctrl + F。</span><span class="sxs-lookup"><span data-stu-id="8a4ad-104">To search these release notes, press Ctrl+F.</span></span>

<span data-ttu-id="8a4ad-105">安装 Microsoft BitLocker 管理和监视（MBAM）2.5 之前，请仔细阅读这些发行说明。</span><span class="sxs-lookup"><span data-stu-id="8a4ad-105">Read these release notes thoroughly before you install Microsoft BitLocker Administration and Monitoring (MBAM) 2.5.</span></span> <span data-ttu-id="8a4ad-106">这些发行说明包含成功安装 MBAM 所需的信息，并且可以包含产品文档中不可用的信息。</span><span class="sxs-lookup"><span data-stu-id="8a4ad-106">These release notes contain information that is required to successfully install MBAM and can contain information that is not available in the product documentation.</span></span> <span data-ttu-id="8a4ad-107">如果这些发行说明与其他 MBAM 2.5 文档不同，请考虑最新更改为权威。</span><span class="sxs-lookup"><span data-stu-id="8a4ad-107">If these release notes differ from other MBAM 2.5 documentation, consider the latest change to be authoritative.</span></span> <span data-ttu-id="8a4ad-108">这些发行说明取代了本产品附带的内容。</span><span class="sxs-lookup"><span data-stu-id="8a4ad-108">These release notes supersede the content that is included with this product.</span></span>

## <a href="" id="---------mbam-2-5-known-issues"></a> <span data-ttu-id="8a4ad-109">MBAM 2.5 已知问题</span><span class="sxs-lookup"><span data-stu-id="8a4ad-109">MBAM 2.5 known issues</span></span>


<span data-ttu-id="8a4ad-110">本部分包含 MBAM 2.5 的发行说明。</span><span class="sxs-lookup"><span data-stu-id="8a4ad-110">This section contains release notes for MBAM 2.5.</span></span>

### <span data-ttu-id="8a4ad-111">无意间以管理员身份运行 Web 浏览器</span><span class="sxs-lookup"><span data-stu-id="8a4ad-111">Web browser unintentionally run as administrator</span></span>

<span data-ttu-id="8a4ad-112">MBAM 服务器配置工具中的帮助链接可导致浏览器窗口以管理员权限打开。</span><span class="sxs-lookup"><span data-stu-id="8a4ad-112">Help links in the MBAM Server Configuration tool can cause browser windows to open with administrator rights.</span></span>

<span data-ttu-id="8a4ad-113">**解决方法：** 在导航到其他网站之前，启用 Internet Explorer 增强的安全配置（IESC）或关闭您的 web 浏览器。</span><span class="sxs-lookup"><span data-stu-id="8a4ad-113">**Workaround:** Enable Internet Explorer Enhanced Security Configuration (IESC) or close your web browser before navigating to other sites.</span></span>

<span data-ttu-id="8a4ad-114">**注意** 这在 MBAM 2.5 SP1 中已修复。</span><span class="sxs-lookup"><span data-stu-id="8a4ad-114">**Note** This is fixed in MBAM 2.5 SP1.</span></span>

 

### <a href="" id="-------------mbam-reports-as-noncompliant-a-client-encrypted-with-aes-256-bit-encryption-keys-and-diffuser"></a> <span data-ttu-id="8a4ad-115">将报表 MBAM 为不符合使用 AES 256 位加密密钥和扩散器加密的客户端</span><span class="sxs-lookup"><span data-stu-id="8a4ad-115">MBAM reports as noncompliant a client encrypted with AES 256-bit encryption keys and Diffuser</span></span>

<span data-ttu-id="8a4ad-116">如果计算机安装了 MBAM 2.5 客户端，并且它是通过将 AES 256 位与扩散器密码强度一起加密的，则 MBAM 客户端在 MBAM 合规性报告中报告为不相容。</span><span class="sxs-lookup"><span data-stu-id="8a4ad-116">If a computer has the MBAM 2.5 client installed and is encrypted by using the AES 256-bit with Diffuser cipher strength, the MBAM client is reported as noncompliant in the MBAM compliance reports.</span></span>

<span data-ttu-id="8a4ad-117">**解决方法：** 在[KB2975636](https://go.microsoft.com/fwlink/?LinkId=511972)处安装修补程序。</span><span class="sxs-lookup"><span data-stu-id="8a4ad-117">**Workaround:** Install the hotfix at [KB2975636](https://go.microsoft.com/fwlink/?LinkId=511972).</span></span>

### <a href="" id="-------------mbam-fails-to-encrypt-a-volume-and-reports-an-error-if-you-set-a-tpm---pin-protector-on-a-tablet-device"></a> <span data-ttu-id="8a4ad-118">如果在平板电脑上设置 TPM + 引脚保护器，MBAM 无法加密卷并报告错误</span><span class="sxs-lookup"><span data-stu-id="8a4ad-118">MBAM fails to encrypt a volume and reports an error if you set a TPM + PIN protector on a tablet device</span></span>

<span data-ttu-id="8a4ad-119">如果最终用户尝试在平板电脑上设置 TPM + PIN 保护程序，MBAM 无法加密，并且会报告错误。</span><span class="sxs-lookup"><span data-stu-id="8a4ad-119">If end users try to set a TPM + PIN protector on a tablet device, MBAM fails to encrypt, and it reports an error.</span></span> <span data-ttu-id="8a4ad-120">出现此问题的原因是平板电脑设备没有预引导环境键盘。</span><span class="sxs-lookup"><span data-stu-id="8a4ad-120">This issue occurs because tablet devices do not have a pre-boot environment keyboard.</span></span>

<span data-ttu-id="8a4ad-121">**解决方法：** 启用 "**启用 BitLocker 身份验证，需要在平板电脑组上预启动键盘输入"** 策略设置。</span><span class="sxs-lookup"><span data-stu-id="8a4ad-121">**Workaround:** Enable the **Enable use of BitLocker authentication requiring preboot keyboard input on tablets** Group Policy setting.</span></span> <span data-ttu-id="8a4ad-122">此设置是 BitLocker 组策略设置，在 MBAM 组策略模板中不可用。</span><span class="sxs-lookup"><span data-stu-id="8a4ad-122">This setting is a BitLocker Group Policy setting and is not available in the MBAM Group Policy Templates.</span></span>

### <span data-ttu-id="8a4ad-123">所有服务帐户都需要用户主体名称</span><span class="sxs-lookup"><span data-stu-id="8a4ad-123">User principal name is required for all service accounts</span></span>

<span data-ttu-id="8a4ad-124">必须为 MBAM 中的所有服务帐户设置用户主体名称（UPN）。</span><span class="sxs-lookup"><span data-stu-id="8a4ad-124">A user principal name (UPN) must be set for all service accounts in MBAM.</span></span> <span data-ttu-id="8a4ad-125">如果无法为帐户创建 UPN，则在配置过程中会出现一条错误消息，指示在 Active Directory 中找不到该用户或组。</span><span class="sxs-lookup"><span data-stu-id="8a4ad-125">If you fail to create a UPN for an account, an error message appears during the configuration process to indicate that the user or group could not be found in Active Directory.</span></span>

<span data-ttu-id="8a4ad-126">**解决方法：** 将 UPN 添加到服务帐户。</span><span class="sxs-lookup"><span data-stu-id="8a4ad-126">**Workaround:** Add the UPN to the service account.</span></span>

### <span data-ttu-id="8a4ad-127">如果客户端计算机无法访问 Microsoft Ajax 内容传递网络，则自助服务门户需要其他配置</span><span class="sxs-lookup"><span data-stu-id="8a4ad-127">Self-Service Portal requires additional configuration if client computers cannot access Microsoft Ajax Content Delivery Network</span></span>

<span data-ttu-id="8a4ad-128">如果你的客户端计算机无法访问 Microsoft Ajax 内容传递网络（CDN），从而为自助门户提供对某些 JavaScript 文件所需的访问权限，则必须将自助服务门户配置为从易于访问的源引用 JavaScript 文件。</span><span class="sxs-lookup"><span data-stu-id="8a4ad-128">If your client computers do not have access to the Microsoft Ajax Content Delivery Network (CDN), which gives the Self-Service Portal the access that it requires to certain JavaScript files, you must configure the Self-Service Portal to reference the JavaScript files from an accessible source.</span></span> <span data-ttu-id="8a4ad-129">如果客户端计算机无法访问 CDN 时未配置自助服务门户，则仅显示公司名称和登录帐户。</span><span class="sxs-lookup"><span data-stu-id="8a4ad-129">If you don’t configure the Self-Service Portal when client computers cannot access CDN, only the company name and the account under which you logged on is displayed.</span></span> <span data-ttu-id="8a4ad-130">不会显示任何错误消息。</span><span class="sxs-lookup"><span data-stu-id="8a4ad-130">No error message appears.</span></span>

<span data-ttu-id="8a4ad-131">**解决方法：** 安装 MBAM 2.5 SP1。</span><span class="sxs-lookup"><span data-stu-id="8a4ad-131">**Workaround:** Install MBAM 2.5 SP1.</span></span> <span data-ttu-id="8a4ad-132">或按照以下说明配置自助服务门户：[如何在客户端计算机无法访问 Microsoft 内容传递网络时配置自助服务门户](how-to-configure-the-self-service-portal-when-client-computers-cannot-access-the-microsoft-content-delivery-network.md)。</span><span class="sxs-lookup"><span data-stu-id="8a4ad-132">or configure the Self-Service Portal by following these instructions: [How to Configure the Self-Service Portal When Client Computers Cannot Access the Microsoft Content Delivery Network](how-to-configure-the-self-service-portal-when-client-computers-cannot-access-the-microsoft-content-delivery-network.md).</span></span>

### <span data-ttu-id="8a4ad-133">在将 IIS 升级到 .NET Framework 4.5 后，自助服务门户和管理和监视网站不会打开</span><span class="sxs-lookup"><span data-stu-id="8a4ad-133">Self-Service Portal and the Administration and Monitoring Website do not open after you upgrade IIS to .NET Framework 4.5</span></span>

<span data-ttu-id="8a4ad-134">将 Internet 信息服务（IIS）升级到 Microsoft .NET Framework 4.5 时，无法打开自助服务门户和管理和监视网站。</span><span class="sxs-lookup"><span data-stu-id="8a4ad-134">When you upgrade Internet Information Services (IIS) to the Microsoft .NET Framework 4.5, the Self-Service Portal and the Administration and Monitoring Website do not open.</span></span>

<span data-ttu-id="8a4ad-135">**解决方法：** 在[安装 .Net Framework 4.0 后，请参阅文章错误消息： "无法加载类型 ' system.servicemodel. HttpModule '](https://go.microsoft.com/fwlink/?LinkId=393568)。</span><span class="sxs-lookup"><span data-stu-id="8a4ad-135">**Workaround:** See the article [Error message after you install the .NET Framework 4.0: "Could not load type 'System.ServiceModel.Activation.HttpModule'](https://go.microsoft.com/fwlink/?LinkId=393568).</span></span>

### <span data-ttu-id="8a4ad-136">管理和监视网站在未配置报表时显示 "找不到报表" 错误消息</span><span class="sxs-lookup"><span data-stu-id="8a4ad-136">Administration and Monitoring Website displays a "Report cannot be found" error message when Reports are not configured</span></span>

<span data-ttu-id="8a4ad-137">如果您配置了管理和监控网站，然后尝试查看报表但没有配置报表功能，则会出现一条错误消息，指示无法找到报表。</span><span class="sxs-lookup"><span data-stu-id="8a4ad-137">If you configure the Administration and Monitoring Website and then try to view a report without configuring the Reports feature first, an error message indicates that the report cannot be found.</span></span>

<span data-ttu-id="8a4ad-138">**解决方法：** 配置 web 应用程序之前，请先配置报表功能。</span><span class="sxs-lookup"><span data-stu-id="8a4ad-138">**Workaround:** Configure the Reports feature before you configure the web applications.</span></span>

### <span data-ttu-id="8a4ad-139">如果未在 SSRS 中配置 SSL，管理和监视网站中的报表将显示警告</span><span class="sxs-lookup"><span data-stu-id="8a4ad-139">Reports in the Administration and Monitoring Website display a warning if SSL is not configured in SSRS</span></span>

<span data-ttu-id="8a4ad-140">如果 SQL Server Reporting Services （SSRS）未配置为使用安全套接字层（SSL），则当你配置 MBAM 服务器时，"报告" 功能的 URL 将设置为 HTTP 而不是 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="8a4ad-140">If SQL Server Reporting Services (SSRS) was not configured to use Secure Socket Layer (SSL), the URL for the Reports feature will be set to HTTP instead of to HTTPS when you configure the MBAM Server.</span></span> <span data-ttu-id="8a4ad-141">如果随后打开 "管理和监视" 网站并选择报表，则会显示以下错误消息： "仅显示安全内容"。</span><span class="sxs-lookup"><span data-stu-id="8a4ad-141">If you then open the Administration and Monitoring Website and select a report, the following error message appears: "Only Secure Content is Displayed."</span></span>

<span data-ttu-id="8a4ad-142">**解决方法：** 若要显示报表，请单击 "**显示所有内容**"。</span><span class="sxs-lookup"><span data-stu-id="8a4ad-142">**Workaround:** To show the report, click **Show All Content**.</span></span> <span data-ttu-id="8a4ad-143">若要解决此问题，请转到安装了 SQL Server Reporting Services 的 MBAM 计算机，运行**Reporting Services 配置管理器**，然后单击 " **Web 服务 URL**"。</span><span class="sxs-lookup"><span data-stu-id="8a4ad-143">To correct this issue, go to the MBAM computer where SQL Server Reporting Services is installed, run **Reporting Services Configuration Manager**, and then click **Web Service URL**.</span></span> <span data-ttu-id="8a4ad-144">为服务器选择相应的 SSL 证书，输入相应的 SSL 端口（默认端口为443），然后单击 "**应用**"。</span><span class="sxs-lookup"><span data-stu-id="8a4ad-144">Select the appropriate SSL certificate for the server, enter the appropriate SSL port (the default port is 443), and then click **Apply**.</span></span>

### <span data-ttu-id="8a4ad-145">单击 "BitLocker 合规性摘要" 报告中的 "后退" 可能会引发错误</span><span class="sxs-lookup"><span data-stu-id="8a4ad-145">Clicking "Back" in the BitLocker Compliance Summary report might throw an error</span></span>

<span data-ttu-id="8a4ad-146">如果向下钻取到 BitLocker 合规性摘要报告，然后单击 SSRS 报表中的**Back**链接，可能会引发错误。</span><span class="sxs-lookup"><span data-stu-id="8a4ad-146">If you drill down into a BitLocker Compliance Summary report, and then click the **Back** link in the SSRS report, an error might be thrown.</span></span>

<span data-ttu-id="8a4ad-147">**解决方法：** 尚.</span><span class="sxs-lookup"><span data-stu-id="8a4ad-147">**Workaround:** None.</span></span>

### <span data-ttu-id="8a4ad-148">"仅使用空间" 加密不会正常工作</span><span class="sxs-lookup"><span data-stu-id="8a4ad-148">Used Space Only Encryption does not work correctly</span></span>

<span data-ttu-id="8a4ad-149">如果在安装 MBAM 客户端后首次加密计算机，并且已将组策略设置配置为仅实现已使用的空间加密，则 MBAM 会错误地加密整个磁盘，而不是仅加密磁盘的已用空间。</span><span class="sxs-lookup"><span data-stu-id="8a4ad-149">If you encrypt a computer for the first time after you install the MBAM Client, and you have configured a Group Policy setting to implement Used Space Only encryption, MBAM erroneously encrypts the entire disk instead of encrypting only the disk’s used space.</span></span> <span data-ttu-id="8a4ad-150">如果已使用仅在安装 MBAM 客户端时已使用的空间对计算机进行了加密，并且配置了相同的组策略设置，MBAM 将报告该驱动器已正确加密，并且不会尝试重新加密该驱动器。</span><span class="sxs-lookup"><span data-stu-id="8a4ad-150">If a computer is already encrypted with Used Space Only when you install the MBAM Client, and you have configured the same Group Policy setting, MBAM reports that the drive is encrypted correctly, and does not try to re-encrypt the drive.</span></span>

<span data-ttu-id="8a4ad-151">**解决方法：** 尚.</span><span class="sxs-lookup"><span data-stu-id="8a4ad-151">**Workaround:** None.</span></span>

### <span data-ttu-id="8a4ad-152">密码强度在 BitLocker 计算机合规性报告上显示不正确</span><span class="sxs-lookup"><span data-stu-id="8a4ad-152">Cipher strength displays incorrectly on the BitLocker Computer Compliance report</span></span>

<span data-ttu-id="8a4ad-153">如果未在 "**选择驱动器加密方法" 和 "密码强度**" 组策略对象中设置特定的密码强度，则配置管理器集成拓扑中的 BitLocker 计算机合规性报告始终显示密码强度的 "unknown"，即使密码强度使用默认的128位加密也是如此。</span><span class="sxs-lookup"><span data-stu-id="8a4ad-153">If you do not set a specific cipher strength in the **Choose drive encryption method and cipher strength** Group Policy Object, the BitLocker Computer Compliance report in the Configuration Manager Integration topology always displays "unknown" for the cipher strength, even when the cipher strength uses the default of 128-bit encryption.</span></span> <span data-ttu-id="8a4ad-154">如果在组策略对象中设置了特定的密码强度，则报表将显示正确的密码强度。</span><span class="sxs-lookup"><span data-stu-id="8a4ad-154">The report displays the correct cipher strength if you set a specific cipher strength in the Group Policy Object.</span></span>

<span data-ttu-id="8a4ad-155">**解决方法：** 在 "**选择驱动器加密方法" 和 "密码强度**" 组策略对象中始终设置特定的密码强度。</span><span class="sxs-lookup"><span data-stu-id="8a4ad-155">**Workaround:** Always set a specific cipher strength in the **Choose drive encryption method and cipher strength** Group Policy Object.</span></span>

### <span data-ttu-id="8a4ad-156">合规性状态按驱动器类型分布在更新配置项目后显示旧数据</span><span class="sxs-lookup"><span data-stu-id="8a4ad-156">Compliance Status Distribution by Drive Type displays old data after you update configuration items</span></span>

<span data-ttu-id="8a4ad-157">在 SystemCenter2012 ConfigurationManager 中更新 MBAM 配置项目后，"BitLocker 企业合规性" 仪表板上的 "驱动器类型" 分布图中的合规性状态分布将显示基于来自旧版本的配置项目的信息的数据。</span><span class="sxs-lookup"><span data-stu-id="8a4ad-157">After you update MBAM configuration items in SystemCenter2012 ConfigurationManager, the Compliance Status Distribution By Drive Type bar chart on the BitLocker Enterprise Compliance Dashboard shows data that is based on information from old versions of the configuration items.</span></span>

<span data-ttu-id="8a4ad-158">**解决方法：** 尚.</span><span class="sxs-lookup"><span data-stu-id="8a4ad-158">**Workaround:** None.</span></span> <span data-ttu-id="8a4ad-159">不支持修改 MBAM 配置项目，并且报表可能不会按预期显示。</span><span class="sxs-lookup"><span data-stu-id="8a4ad-159">Modification of the MBAM configuration items is not supported, and the report might not appear as expected.</span></span>

### <span data-ttu-id="8a4ad-160">增强的安全配置可能会导致报表不能正确显示错误消息</span><span class="sxs-lookup"><span data-stu-id="8a4ad-160">Enhanced Security Configuration might cause reports to display an error message incorrectly</span></span>

<span data-ttu-id="8a4ad-161">如果 Internet Explorer 增强的安全配置（ESC）处于打开状态，则当你尝试在 MBAM 服务器上查看报告时可能会显示 "拒绝访问" 错误消息。</span><span class="sxs-lookup"><span data-stu-id="8a4ad-161">If Internet Explorer Enhanced Security Configuration (ESC) is turned on, an "Access Denied" error message might appear when you try to view reports on the MBAM Server.</span></span> <span data-ttu-id="8a4ad-162">默认情况下，按 ESC 可保护服务器，方法是降低服务器对通过 web 内容和应用程序脚本可能发生的潜在攻击的影响。</span><span class="sxs-lookup"><span data-stu-id="8a4ad-162">By default, ESC is turned on to protect the server by decreasing the server’s exposure to potential attacks that can occur through web content and application scripts.</span></span>

<span data-ttu-id="8a4ad-163">**解决方法：** 如果尝试在 MBAM 服务器上查看报告时出现 "拒绝访问" 错误消息，则可以在映像中设置组策略对象或手动更改默认设置，以禁用增强的安全配置。</span><span class="sxs-lookup"><span data-stu-id="8a4ad-163">**Workaround:** If the "Access Denied" error message appears when you try to view reports on the MBAM Server, you can set a Group Policy Object or change the default manually in your image to disable Enhanced Security Configuration.</span></span> <span data-ttu-id="8a4ad-164">您也可以从另一台计算机上查看未启用 ESC 的报告。</span><span class="sxs-lookup"><span data-stu-id="8a4ad-164">You can also alternatively view the reports from another computer on which ESC is not enabled.</span></span>

## <a href="" id="hotfixes-and-knowledge-base-articles-for-mbam-2-5-"></a><span data-ttu-id="8a4ad-165">MBAM 2.5 的修补程序和知识文库文章</span><span class="sxs-lookup"><span data-stu-id="8a4ad-165">Hotfixes and Knowledge Base articles for MBAM 2.5</span></span>


<span data-ttu-id="8a4ad-166">下表列出了 MBAM 2.5 的修补程序和知识库文章。</span><span class="sxs-lookup"><span data-stu-id="8a4ad-166">This table lists the hotfixes and KB articles for MBAM 2.5.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong><span data-ttu-id="8a4ad-167">知识库文章</span><span class="sxs-lookup"><span data-stu-id="8a4ad-167">KB Article</span></span></strong></th>
<th align="left"><span data-ttu-id="8a4ad-168">Title</span><span class="sxs-lookup"><span data-stu-id="8a4ad-168">Title</span></span></th>
<th align="left"><strong><span data-ttu-id="8a4ad-169">链接</span><span class="sxs-lookup"><span data-stu-id="8a4ad-169">Link</span></span></strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8a4ad-170">2975636</span><span class="sxs-lookup"><span data-stu-id="8a4ad-170">2975636</span></span></p></td>
<td align="left"><p><span data-ttu-id="8a4ad-171">Microsoft BitLocker 管理和监视2.5 的修补程序包1</span><span class="sxs-lookup"><span data-stu-id="8a4ad-171">Hotfix Package 1 for Microsoft BitLocker Administration and Monitoring 2.5</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2975636/EN-US" data-raw-source="[support.microsoft.com/kb/2975636/EN-US](https://support.microsoft.com/kb/2975636/EN-US)"><span data-ttu-id="8a4ad-172">support.microsoft.com/kb/2975636/EN-US</span><span class="sxs-lookup"><span data-stu-id="8a4ad-172">support.microsoft.com/kb/2975636/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8a4ad-173">3015477</span><span class="sxs-lookup"><span data-stu-id="8a4ad-173">3015477</span></span></p></td>
<td align="left"><p><span data-ttu-id="8a4ad-174">用于 BitLocker 管理和监视2.5 的修补程序包2</span><span class="sxs-lookup"><span data-stu-id="8a4ad-174">Hotfix Package 2 for BitLocker Administration and Monitoring 2.5</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/3015477" data-raw-source="[support.microsoft.com/kb/3015477](https://support.microsoft.com/kb/3015477)"><span data-ttu-id="8a4ad-175">support.microsoft.com/kb/3015477</span><span class="sxs-lookup"><span data-stu-id="8a4ad-175">support.microsoft.com/kb/3015477</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8a4ad-176">3011022</span><span class="sxs-lookup"><span data-stu-id="8a4ad-176">3011022</span></span></p></td>
<td align="left"><p><span data-ttu-id="8a4ad-177">如果 SSRS 实例的名称包含下划线，MBAM 2.5 安装或 Configuration Manager 报告将失败</span><span class="sxs-lookup"><span data-stu-id="8a4ad-177">MBAM 2.5 installation or Configuration Manager reporting fails if the name of SSRS instance contains an underscore</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/3011022/EN-US" data-raw-source="[support.microsoft.com/kb/3011022/EN-US](https://support.microsoft.com/kb/3011022/EN-US)"><span data-ttu-id="8a4ad-178">support.microsoft.com/kb/3011022/EN-US</span><span class="sxs-lookup"><span data-stu-id="8a4ad-178">support.microsoft.com/kb/3011022/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8a4ad-179">2756402</span><span class="sxs-lookup"><span data-stu-id="8a4ad-179">2756402</span></span></p></td>
<td align="left"><p><span data-ttu-id="8a4ad-180">MBAM 客户端将失败，并出现事件描述中的事件 ID 4 和错误代码0x8004100E</span><span class="sxs-lookup"><span data-stu-id="8a4ad-180">MBAM client would fail with Event ID 4 and error code 0x8004100E in the Event description</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2756402/EN-US" data-raw-source="[support.microsoft.com/kb/2756402/EN-US](https://support.microsoft.com/kb/2756402/EN-US)"><span data-ttu-id="8a4ad-181">support.microsoft.com/kb/2756402/EN-US</span><span class="sxs-lookup"><span data-stu-id="8a4ad-181">support.microsoft.com/kb/2756402/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8a4ad-182">2639518</span><span class="sxs-lookup"><span data-stu-id="8a4ad-182">2639518</span></span></p></td>
<td align="left"><p><span data-ttu-id="8a4ad-183">在 MBAM 中打开企业或计算机合规性报告时出错</span><span class="sxs-lookup"><span data-stu-id="8a4ad-183">Error opening Enterprise or Computer Compliance Reports in MBAM</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2639518/EN-US" data-raw-source="[support.microsoft.com/kb/2639518/EN-US](https://support.microsoft.com/kb/2639518/EN-US)"><span data-ttu-id="8a4ad-184">support.microsoft.com/kb/2639518/EN-US</span><span class="sxs-lookup"><span data-stu-id="8a4ad-184">support.microsoft.com/kb/2639518/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8a4ad-185">2870842</span><span class="sxs-lookup"><span data-stu-id="8a4ad-185">2870842</span></span></p></td>
<td align="left"><p><span data-ttu-id="8a4ad-186">MBAM 2.0 在 SQL Server 2008 的配置管理器集成方案期间安装失败</span><span class="sxs-lookup"><span data-stu-id="8a4ad-186">MBAM 2.0 Setup fails during Configuration Manager Integration Scenario with SQL Server 2008</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2870842/EN-US" data-raw-source="[support.microsoft.com/kb/2870842/EN-US](https://support.microsoft.com/kb/2870842/EN-US)"><span data-ttu-id="8a4ad-187">support.microsoft.com/kb/2870842/EN-US</span><span class="sxs-lookup"><span data-stu-id="8a4ad-187">support.microsoft.com/kb/2870842/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8a4ad-188">2975472</span><span class="sxs-lookup"><span data-stu-id="8a4ad-188">2975472</span></span></p></td>
<td align="left"><p><span data-ttu-id="8a4ad-189">许多 MBAM 客户端连接到 MBAM 恢复数据库时的 SQL 死锁</span><span class="sxs-lookup"><span data-stu-id="8a4ad-189">SQL deadlocks when many MBAM clients connect to the MBAM recovery database</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2975472/EN-US" data-raw-source="[support.microsoft.com/kb/2975472/EN-US](https://support.microsoft.com/kb/2975472/EN-US)"><span data-ttu-id="8a4ad-190">support.microsoft.com/kb/2975472/EN-US</span><span class="sxs-lookup"><span data-stu-id="8a4ad-190">support.microsoft.com/kb/2975472/EN-US</span></span></a></p></td>
</tr>
</tbody>
</table>

 


## <span data-ttu-id="8a4ad-191">相关主题</span><span class="sxs-lookup"><span data-stu-id="8a4ad-191">Related topics</span></span>


[<span data-ttu-id="8a4ad-192">关于 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="8a4ad-192">About MBAM 2.5</span></span>](about-mbam-25.md)

 

## <span data-ttu-id="8a4ad-193">已获得 MBAM 的建议？</span><span class="sxs-lookup"><span data-stu-id="8a4ad-193">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="8a4ad-194">在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="8a4ad-194">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span>
- <span data-ttu-id="8a4ad-195">对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="8a4ad-195">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





