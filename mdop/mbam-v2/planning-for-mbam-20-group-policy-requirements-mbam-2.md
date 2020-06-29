---
title: 计划 MBAM 2.0 组策略要求
description: 计划 MBAM 2.0 组策略要求
author: dansimp
ms.assetid: f5e19dcb-eb15-4722-bb71-0734b3799eb8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f6092507996fe6f0234178c8b1abae5cea7bf836
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798143"
---
# <span data-ttu-id="79cc0-103">计划 MBAM 2.0 组策略要求</span><span class="sxs-lookup"><span data-stu-id="79cc0-103">Planning for MBAM 2.0 Group Policy Requirements</span></span>


<span data-ttu-id="79cc0-104">若要管理 Microsoft BitLocker 管理和监视（MBAM）客户端计算机，你需要考虑你希望在你的组织中支持的 BitLocker 保护器的类型，然后配置要应用的相应组策略设置。</span><span class="sxs-lookup"><span data-stu-id="79cc0-104">To manage Microsoft BitLocker Administration and Monitoring (MBAM) client computers, you need to consider the types of BitLocker protectors that you want to support in your organization, and then configure the corresponding Group Policy settings that you want to apply.</span></span> <span data-ttu-id="79cc0-105">本主题介绍使用 Microsoft BitLocker 管理和监视管理企业中的 BitLocker 驱动器加密时可使用的组策略设置。</span><span class="sxs-lookup"><span data-stu-id="79cc0-105">This topic describes the Group Policy settings that are available for use when you are using Microsoft BitLocker Administration and Monitoring to manage BitLocker Drive Encryption in the enterprise.</span></span>

<span data-ttu-id="79cc0-106">MBAM 支持以下类型的适用于操作系统驱动器的 BitLocker 保护程序：受信任的平台模块（TPM）、TPM + PIN、TPM + USB 密钥以及 TPM + PIN + USB 密钥、密码、数字密码和数据恢复代理。</span><span class="sxs-lookup"><span data-stu-id="79cc0-106">MBAM supports the following types of BitLocker protectors for operating system drives: Trusted Platform Module (TPM), TPM + PIN, TPM + USB key, and TPM + PIN + USB key, password, numerical password, and Data Recovery Agent.</span></span> <span data-ttu-id="79cc0-107">只有 Windows To Go 设备和没有 TPM 的 Windows 8 设备支持密码保护程序。</span><span class="sxs-lookup"><span data-stu-id="79cc0-107">The password protector is supported only for Windows To Go devices and for Windows 8 devices that do not have a TPM.</span></span> <span data-ttu-id="79cc0-108">仅当操作系统卷在安装 MBAM 之前已加密时，MBAM 支持 TPM + USB 密钥和 TPM + 引脚 + USB 密钥保护器。</span><span class="sxs-lookup"><span data-stu-id="79cc0-108">MBAM supports the TPM + USB key and the TPM + PIN + USB key protectors only when the operating system volume is encrypted before MBAM is installed.</span></span>

<span data-ttu-id="79cc0-109">MBAM 支持固定数据驱动器的以下类型的 BitLocker 保护器：密码、自动解锁、数字密码和数据恢复代理。</span><span class="sxs-lookup"><span data-stu-id="79cc0-109">MBAM supports the following types of BitLocker protectors for fixed data drives: password, auto-unlock, numerical password, and Data Recovery Agent.</span></span>

<span data-ttu-id="79cc0-110">数字密码保护程序将自动应用为卷加密的一部分，并且不需要进行配置。</span><span class="sxs-lookup"><span data-stu-id="79cc0-110">The numeric password protector is applied automatically as part of volume encryption and does not need to be configured.</span></span>

**<span data-ttu-id="79cc0-111">重要提示</span><span class="sxs-lookup"><span data-stu-id="79cc0-111">Important</span></span>**  
<span data-ttu-id="79cc0-112">MBAM 未使用默认 Windows BitLocker 驱动器加密组策略对象（GPO）设置，如果启用，可能会导致冲突行为。</span><span class="sxs-lookup"><span data-stu-id="79cc0-112">The default Windows BitLocker drive encryption Group Policy Object (GPO) settings are not used by MBAM and can cause conflicting behavior if they are enabled.</span></span> <span data-ttu-id="79cc0-113">若要启用 MBAM 来管理 BitLocker，必须在安装 MBAM 组策略模板后定义 MBAM 组策略设置。</span><span class="sxs-lookup"><span data-stu-id="79cc0-113">To enable MBAM to manage BitLocker, you must define the MBAM Group Policy settings only after installing the MBAM Group Policy template.</span></span>



<span data-ttu-id="79cc0-114">增强的启动 Pin 可以包含字符，例如大写字母和小写字母以及数字。</span><span class="sxs-lookup"><span data-stu-id="79cc0-114">Enhanced startup PINs can contain characters, such as uppercase and lowercase letters, and numbers.</span></span> <span data-ttu-id="79cc0-115">与 BitLocker 不同，MBAM 不支持将符号和空格用于增强的引脚。</span><span class="sxs-lookup"><span data-stu-id="79cc0-115">Unlike BitLocker, MBAM does not support the use of symbols and spaces for enhanced PINs.</span></span>

<span data-ttu-id="79cc0-116">在能够运行组策略管理控制台（GPMC）或高级组策略管理（AGPM） MDOP 技术的计算机上安装 MBAM 组策略模板。</span><span class="sxs-lookup"><span data-stu-id="79cc0-116">Install the MBAM Group Policy template on a computer that is capable of running the Group Policy Management Console (GPMC) or the Advanced Group Policy Management (AGPM) MDOP technology.</span></span> <span data-ttu-id="79cc0-117">若要编辑启用 MBAM 功能的 GPO 设置，必须首先安装 MBAM 组策略模板，打开 GPMC 或 AGPM 以编辑适用的 gpo，然后导航到以下 GPO 节点：**计算机配置** \\ **策略** \\ **管理模板** \\ **Windows 组件** \\ **MDOP MBAM （BitLocker Management）。**</span><span class="sxs-lookup"><span data-stu-id="79cc0-117">To edit the GPO settings that enable MBAM functionality, you must first install the MBAM Group Policy template, open the GPMC or AGPM to edit the applicable GPO, and then navigate to the following GPO node: **Computer Configuration**\\**Policies**\\**Administrative Templates**\\**Windows Components**\\**MDOP MBAM (BitLocker Management).**</span></span>

<span data-ttu-id="79cc0-118">MDOP MBAM （BitLocker Management） GPO 节点包含四个全局策略设置和四个子 GPO 设置节点：客户端管理、固定驱动器、操作系统驱动器和可移动驱动器。</span><span class="sxs-lookup"><span data-stu-id="79cc0-118">The MDOP MBAM (BitLocker Management) GPO node contains four global policy settings and four child GPO settings nodes: Client Management, Fixed Drive, Operating System Drive, and Removable Drive.</span></span> <span data-ttu-id="79cc0-119">以下各节提供了策略定义和建议的策略设置，可帮助你规划 MBAM GPO 策略设置要求。</span><span class="sxs-lookup"><span data-stu-id="79cc0-119">The following sections provide policy definitions and suggested policy settings to assist you in planning for MBAM GPO policy setting requirements.</span></span>

**<span data-ttu-id="79cc0-120">注意</span><span class="sxs-lookup"><span data-stu-id="79cc0-120">Note</span></span>**  
<span data-ttu-id="79cc0-121">有关配置最小的推荐 GPO 设置以使 MBAM 管理 BitLocker 加密的详细信息，请参阅[如何编辑 MBAM 2.0 GPO 设置](how-to-edit-mbam-20-gpo-settings-mbam-2.md)。</span><span class="sxs-lookup"><span data-stu-id="79cc0-121">For more information about configuring the minimum, recommended GPO settings to enable MBAM to manage BitLocker encryption, see [How to Edit MBAM 2.0 GPO Settings](how-to-edit-mbam-20-gpo-settings-mbam-2.md).</span></span>



## <span data-ttu-id="79cc0-122">全局策略定义</span><span class="sxs-lookup"><span data-stu-id="79cc0-122">Global Policy Definitions</span></span>


<span data-ttu-id="79cc0-123">本部分介绍在以下 GPO 节点中找到的 MBAM 全局策略定义：**计算机配置** \\ **策略** \\ **管理模板** \\ **Windows 组件** \\ **MDOP MBAM （BitLocker Management）**。</span><span class="sxs-lookup"><span data-stu-id="79cc0-123">This section describes MBAM Global policy definitions found at the following GPO node: **Computer Configuration**\\**Policies**\\**Administrative Templates**\\**Windows Components**\\**MDOP MBAM (BitLocker Management)**.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="79cc0-124">策略名称</span><span class="sxs-lookup"><span data-stu-id="79cc0-124">Policy Name</span></span></th>
<th align="left"><span data-ttu-id="79cc0-125">概述和建议的策略设置</span><span class="sxs-lookup"><span data-stu-id="79cc0-125">Overview and Suggested Policy Setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="79cc0-126">选择驱动器加密方法和密码强度</span><span class="sxs-lookup"><span data-stu-id="79cc0-126">Choose drive encryption method and cipher strength</span></span></p></td>
<td align="left"><p><span data-ttu-id="79cc0-127">建议的配置： <strong> 未配置</span><span class="sxs-lookup"><span data-stu-id="79cc0-127">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="79cc0-128">将此策略配置为使用特定加密方法和密码强度。</span><span class="sxs-lookup"><span data-stu-id="79cc0-128">Configure this policy to use a specific encryption method and cipher strength.</span></span></p>
<p><span data-ttu-id="79cc0-129">如果未配置此策略，BitLocker 将使用具有扩散器的 AES 128 位的默认加密方法或由安装脚本指定的加密方法。</span><span class="sxs-lookup"><span data-stu-id="79cc0-129">When this policy is not configured, BitLocker uses the default encryption method of AES 128-bit with Diffuser or the encryption method specified by the setup script.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="79cc0-130">在重启时防止内存覆盖</span><span class="sxs-lookup"><span data-stu-id="79cc0-130">Prevent memory overwrite on restart</span></span></p></td>
<td align="left"><p><span data-ttu-id="79cc0-131">建议的配置： <strong> 未配置</span><span class="sxs-lookup"><span data-stu-id="79cc0-131">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="79cc0-132">配置此策略可提高重启性能，而无需在重新启动时覆盖内存中的 BitLocker 机密。</span><span class="sxs-lookup"><span data-stu-id="79cc0-132">Configure this policy to improve restart performance without overwriting BitLocker secrets in memory on restart.</span></span></p>
<p><span data-ttu-id="79cc0-133">如果未配置此策略，当计算机重新启动时，将从内存中删除 BitLocker 机密。</span><span class="sxs-lookup"><span data-stu-id="79cc0-133">When this policy is not configured, BitLocker secrets are removed from memory when the computer restarts.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="79cc0-134">验证智能卡证书使用规则</span><span class="sxs-lookup"><span data-stu-id="79cc0-134">Validate smart card certificate usage rule</span></span></p></td>
<td align="left"><p><span data-ttu-id="79cc0-135">建议的配置： <strong> 未配置</span><span class="sxs-lookup"><span data-stu-id="79cc0-135">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="79cc0-136">将此策略配置为使用基于智能卡证书的 BitLocker 保护。</span><span class="sxs-lookup"><span data-stu-id="79cc0-136">Configure this policy to use smartcard certificate-based BitLocker protection.</span></span></p>
<p><span data-ttu-id="79cc0-137">如果未配置此策略，则使用默认对象标识符1.3.6.1.4.1.311.67.1.1 指定证书。</span><span class="sxs-lookup"><span data-stu-id="79cc0-137">When this policy is not configured, a default object identifier 1.3.6.1.4.1.311.67.1.1 is used to specify a certificate.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="79cc0-138">为你的组织提供唯一标识符</span><span class="sxs-lookup"><span data-stu-id="79cc0-138">Provide the unique identifiers for your organization</span></span></p></td>
<td align="left"><p><span data-ttu-id="79cc0-139">建议的配置： <strong> 未配置</span><span class="sxs-lookup"><span data-stu-id="79cc0-139">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="79cc0-140">将此策略配置为使用基于证书的数据恢复代理或 BitLocker To Go 阅读器。</span><span class="sxs-lookup"><span data-stu-id="79cc0-140">Configure this policy to use a certificate-based data recovery agent or the BitLocker To Go reader.</span></span></p>
<p><span data-ttu-id="79cc0-141">如果未配置此策略，则 <strong> </strong> 不会使用 "标识" 字段。</span><span class="sxs-lookup"><span data-stu-id="79cc0-141">When this policy is not configured, the <strong>Identification</strong> field is not used.</span></span></p>
<p><span data-ttu-id="79cc0-142">如果您的公司需要更高的安全测量，您可能需要配置 <strong> 标识 </strong> 字段，以确保所有 USB 设备都具有此字段集，并且它们与此组策略设置对齐。</span><span class="sxs-lookup"><span data-stu-id="79cc0-142">If your company requires higher security measurements, you may want to configure the <strong>Identification</strong> field to make sure that all USB devices have this field set and that they are aligned with this Group Policy setting.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="79cc0-143">客户端管理策略定义</span><span class="sxs-lookup"><span data-stu-id="79cc0-143">Client Management Policy Definitions</span></span>


<span data-ttu-id="79cc0-144">本部分介绍在下列 GPO 节点处找到的 Microsoft BitLocker 管理和监视的客户端管理策略定义：**计算机配置** \\ **策略** \\ **管理模板** \\ **Windows 组件** \\ **MDOP MBAM （BitLocker Management）** \\ **客户端管理**。</span><span class="sxs-lookup"><span data-stu-id="79cc0-144">This section describes Client Management policy definitions for Microsoft BitLocker Administration and Monitoring found at the following GPO node: **Computer Configuration**\\**Policies**\\**Administrative Templates**\\**Windows Components**\\**MDOP MBAM (BitLocker Management)**\\**Client Management**.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="79cc0-145">策略名称</span><span class="sxs-lookup"><span data-stu-id="79cc0-145">Policy Name</span></span></th>
<th align="left"><span data-ttu-id="79cc0-146">概述和建议的策略设置</span><span class="sxs-lookup"><span data-stu-id="79cc0-146">Overview and Suggested Policy Settings</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="79cc0-147">配置 MBAM 服务</span><span class="sxs-lookup"><span data-stu-id="79cc0-147">Configure MBAM Services</span></span></p></td>
<td align="left"><p><span data-ttu-id="79cc0-148">建议的配置： <strong> 已启用</span><span class="sxs-lookup"><span data-stu-id="79cc0-148">Suggested Configuration: <strong>Enabled</span></span></strong></p>
<ul>
<li><p><strong><span data-ttu-id="79cc0-149">MBAM 恢复和硬件服务终结点 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="79cc0-149">MBAM Recovery and Hardware service endpoint</strong>.</span></span> <span data-ttu-id="79cc0-150">使用此设置启用 MBAM 客户端 BitLocker 加密管理。</span><span class="sxs-lookup"><span data-stu-id="79cc0-150">Use this setting to enable MBAM Client BitLocker encryption management.</span></span> <span data-ttu-id="79cc0-151">输入类似于以下示例的终结点位置： <strong> http:// </strong><em> &lt; MBAM 管理和监视服务器名称 &gt; </em><strong> ： </strong><em> &lt; 端口 web 服务绑定到 &gt; </em><strong> /MBAMRecoveryAndHardwareService/CoreService.svc </strong> 。</span><span class="sxs-lookup"><span data-stu-id="79cc0-151">Enter an endpoint location that is similar to the following example: <strong>http://</strong><em>&lt;MBAM Administration and Monitoring Server Name&gt;</em><strong>:</strong><em>&lt;port the web service is bound to&gt;</em><strong>/MBAMRecoveryAndHardwareService/CoreService.svc</strong>.</span></span></p></li>
<li><p><strong><span data-ttu-id="79cc0-152">选择要存储的 BitLocker 恢复信息 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="79cc0-152">Select BitLocker recovery information to store</strong>.</span></span> <span data-ttu-id="79cc0-153">此策略设置允许你配置密钥恢复服务以备份 BitLocker 恢复信息。</span><span class="sxs-lookup"><span data-stu-id="79cc0-153">This policy setting lets you configure the key recovery service to back up BitLocker recovery information.</span></span> <span data-ttu-id="79cc0-154">它还允许你配置用于收集合规性和审核报告的状态报告服务。</span><span class="sxs-lookup"><span data-stu-id="79cc0-154">It also lets you configure status reporting service for collecting compliance and audit reports.</span></span> <span data-ttu-id="79cc0-155">该策略提供一种管理方法来恢复由 BitLocker 加密的数据，以防止因缺少密钥信息而导致数据丢失。</span><span class="sxs-lookup"><span data-stu-id="79cc0-155">The policy provides an administrative method of recovering data encrypted by BitLocker to prevent data loss due to the lack of key information.</span></span> <span data-ttu-id="79cc0-156">状态报告和密钥恢复活动将自动并以静默方式发送到配置的报表服务器位置。</span><span class="sxs-lookup"><span data-stu-id="79cc0-156">Status report and key recovery activity will automatically and silently be sent to the configured report server location.</span></span></p>
<p><span data-ttu-id="79cc0-157">如果未配置或禁用此策略设置，将不会保存密钥恢复信息，并且不会向服务器报告状态报告和密钥恢复活动。</span><span class="sxs-lookup"><span data-stu-id="79cc0-157">If you do not configure or if you disable this policy setting, the Key recovery information will not be saved, and status report and key recovery activity will not be reported to server.</span></span> <span data-ttu-id="79cc0-158">当此设置设置为 <strong> 恢复密码和密钥包时 </strong> ，将自动将恢复密码和密钥数据包备份到配置的密钥恢复服务器位置。</span><span class="sxs-lookup"><span data-stu-id="79cc0-158">When this setting is set to <strong>Recovery Password and key package</strong>, the recovery password and key package will be automatically and silently backed up to the configured key recovery server location.</span></span></p></li>
<li><p><strong><span data-ttu-id="79cc0-159">以分钟为单位输入客户端检查状态频率 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="79cc0-159">Enter client checking status frequency in minutes</strong>.</span></span> <span data-ttu-id="79cc0-160">此策略设置管理客户端计算机上的客户端检查 BitLocker 保护策略和状态的频率。</span><span class="sxs-lookup"><span data-stu-id="79cc0-160">This policy setting manages how frequently the client checks the BitLocker protection policies and status on the client computer.</span></span> <span data-ttu-id="79cc0-161">此策略还管理将客户端合规性状态保存到服务器的频率。</span><span class="sxs-lookup"><span data-stu-id="79cc0-161">This policy also manages how frequently the client compliance status is saved to the server.</span></span> <span data-ttu-id="79cc0-162">客户端在客户端计算机上检查 BitLocker 保护策略和状态，还将按配置的频率备份客户端恢复密钥。</span><span class="sxs-lookup"><span data-stu-id="79cc0-162">The client checks the BitLocker protection policies and status on the client computer and also backs up the client recovery key at the configured frequency.</span></span></p>
<p><span data-ttu-id="79cc0-163">根据公司设置的要求检查计算机合规性状态的频率，以及备份客户端恢复密钥的频率，设置此频率。</span><span class="sxs-lookup"><span data-stu-id="79cc0-163">Set this frequency based on the requirement set by your company on how frequently to check the compliance status of the computer, and how frequently to back up the client recovery key.</span></span></p></li>
<li><p><strong><span data-ttu-id="79cc0-164">MBAM 状态报告服务终结点 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="79cc0-164">MBAM Status reporting service endpoint</strong>.</span></span> <span data-ttu-id="79cc0-165">必须将此设置配置为启用 MBAM 客户端 BitLocker 加密管理。</span><span class="sxs-lookup"><span data-stu-id="79cc0-165">You must configure this setting to enable MBAM Client BitLocker encryption management.</span></span> <span data-ttu-id="79cc0-166">输入类似于以下示例的终结点位置： <strong> http:// </strong><em> &lt; MBAM 管理和监视服务器名称 &gt; </em><strong> ： </strong><em> &lt; 端口 web 服务绑定到 &gt; </em><strong> /MBAMComplianceStatusService/StatusReportingService.svc </strong> 。</span><span class="sxs-lookup"><span data-stu-id="79cc0-166">Enter an endpoint location that is similar to the following example: <strong>http://</strong><em>&lt;MBAM Administration and Monitoring Server Name&gt;</em><strong>:</strong><em>&lt;port the web service is bound to&gt;</em><strong>/MBAMComplianceStatusService/StatusReportingService.svc</strong>.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="79cc0-167">配置用户豁免策略</span><span class="sxs-lookup"><span data-stu-id="79cc0-167">Configure user exemption policy</span></span></p></td>
<td align="left"><p><span data-ttu-id="79cc0-168">建议的配置： <strong> 未配置</span><span class="sxs-lookup"><span data-stu-id="79cc0-168">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="79cc0-169">此策略设置允许你配置网站地址、电子邮件地址或电话号码，以指示用户向 BitLocker 加密请求豁免。</span><span class="sxs-lookup"><span data-stu-id="79cc0-169">This policy setting lets you configure a web site address, email address, or phone number that will instruct a user to request an exemption from BitLocker encryption.</span></span></p>
<p><span data-ttu-id="79cc0-170">如果启用此策略设置并提供网站地址、电子邮件地址或电话号码，用户将看到一个对话框，该对话框向用户提供有关如何申请来自 BitLocker 保护的豁免的说明。</span><span class="sxs-lookup"><span data-stu-id="79cc0-170">If you enable this policy setting and provide a web site address, email address, or phone number, users will see a dialog that gives them instructions on how to apply for an exemption from BitLocker protection.</span></span> <span data-ttu-id="79cc0-171">有关为用户启用 BitLocker 加密免除的详细信息，请参阅 <a href="how-to-manage-user-bitlocker-encryption-exemptions-mbam-2.md" data-raw-source="[How to Manage User BitLocker Encryption Exemptions](how-to-manage-user-bitlocker-encryption-exemptions-mbam-2.md)"> 如何管理用户 Bitlocker 加密免除 </a> 。</span><span class="sxs-lookup"><span data-stu-id="79cc0-171">For more information about enabling BitLocker encryption exemptions for users, see <a href="how-to-manage-user-bitlocker-encryption-exemptions-mbam-2.md" data-raw-source="[How to Manage User BitLocker Encryption Exemptions](how-to-manage-user-bitlocker-encryption-exemptions-mbam-2.md)">How to Manage User BitLocker Encryption Exemptions</a>.</span></span></p>
<p><span data-ttu-id="79cc0-172">如果禁用或未配置此策略设置，将不向用户显示豁免请求说明。</span><span class="sxs-lookup"><span data-stu-id="79cc0-172">If you either disable or do not configure this policy setting, the exemption request instructions will not be presented to users.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="79cc0-173">注意</span><span class="sxs-lookup"><span data-stu-id="79cc0-173">Note</span></span></strong><br/><p><span data-ttu-id="79cc0-174">用户豁免按用户管理，而不是按计算机进行管理。</span><span class="sxs-lookup"><span data-stu-id="79cc0-174">User exemption is managed per user, not per computer.</span></span> <span data-ttu-id="79cc0-175">如果多个用户登录到同一台计算机，并且任何一个用户没有豁免，计算机将被加密。</span><span class="sxs-lookup"><span data-stu-id="79cc0-175">If multiple users log on to the same computer and any one user is not exempt, the computer will be encrypted.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="79cc0-176">配置客户体验改善计划</span><span class="sxs-lookup"><span data-stu-id="79cc0-176">Configure customer experience improvement program</span></span></p></td>
<td align="left"><p><span data-ttu-id="79cc0-177">此策略设置允许你配置 MBAM 用户如何加入客户体验改善计划。</span><span class="sxs-lookup"><span data-stu-id="79cc0-177">This policy setting lets you configure how MBAM users can join the Customer Experience Improvement Program.</span></span> <span data-ttu-id="79cc0-178">此程序将收集有关计算机硬件以及用户如何使用 MBAM 的信息，而无需中断其工作。</span><span class="sxs-lookup"><span data-stu-id="79cc0-178">This program collects information about computer hardware and how users use MBAM without interrupting their work.</span></span> <span data-ttu-id="79cc0-179">此信息可帮助 Microsoft 确定要改进的 MBAM 功能。</span><span class="sxs-lookup"><span data-stu-id="79cc0-179">The information helps Microsoft to identify which MBAM features to improve.</span></span> <span data-ttu-id="79cc0-180">Microsoft 不会使用此信息识别或联系 MBAM 用户。</span><span class="sxs-lookup"><span data-stu-id="79cc0-180">Microsoft will not use this information to identify or contact MBAM users.</span></span></p>
<p><span data-ttu-id="79cc0-181">如果启用此策略设置，用户将能够加入客户体验改善计划。</span><span class="sxs-lookup"><span data-stu-id="79cc0-181">If you enable this policy setting, users will be able to join the Customer Experience Improvement Program.</span></span></p>
<p><span data-ttu-id="79cc0-182">如果禁用此策略设置，用户将无法加入客户体验改善计划。</span><span class="sxs-lookup"><span data-stu-id="79cc0-182">If you disable this policy setting, users will not be able to join the Customer Experience Improvement Program.</span></span></p>
<p><span data-ttu-id="79cc0-183">如果未配置此策略设置，则用户可以选择加入客户体验改善计划。</span><span class="sxs-lookup"><span data-stu-id="79cc0-183">If you do not configure this policy setting, users will have the option to join the Customer Experience Improvement Program.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="79cc0-184">固定驱动器策略定义</span><span class="sxs-lookup"><span data-stu-id="79cc0-184">Fixed Drive Policy Definitions</span></span>


<span data-ttu-id="79cc0-185">本部分介绍在下列 GPO 节点处找到的 Microsoft BitLocker 管理和监视的固定驱动器策略定义：**计算机配置** \\ **策略** \\ **管理模板** \\ **Windows 组件** \\ **MDOP MBAM （BitLocker Management）** 已 \\ **修复的驱动器**。</span><span class="sxs-lookup"><span data-stu-id="79cc0-185">This section describes Fixed Drive policy definitions for Microsoft BitLocker Administration and Monitoring found at the following GPO node: **Computer Configuration**\\**Policies**\\**Administrative Templates**\\**Windows Components**\\**MDOP MBAM (BitLocker Management)**\\**Fixed Drive**.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="79cc0-186">策略名称</span><span class="sxs-lookup"><span data-stu-id="79cc0-186">Policy Name</span></span></th>
<th align="left"><span data-ttu-id="79cc0-187">概述和建议的策略设置</span><span class="sxs-lookup"><span data-stu-id="79cc0-187">Overview and Suggested Policy Setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="79cc0-188">固定数据驱动器加密设置</span><span class="sxs-lookup"><span data-stu-id="79cc0-188">Fixed data drive encryption settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="79cc0-189">建议的配置： <strong> 已启用</span><span class="sxs-lookup"><span data-stu-id="79cc0-189">Suggested Configuration: <strong>Enabled</span></span></strong></p>
<p><span data-ttu-id="79cc0-190">通过此策略设置，您可以管理固定驱动器是否必须加密。</span><span class="sxs-lookup"><span data-stu-id="79cc0-190">This policy setting let you manage whether fixed drives must be encrypted.</span></span></p>
<p><span data-ttu-id="79cc0-191">如果需要加密操作系统卷，请选择 " <strong> 启用自动解锁固定数据驱动器" </strong> 选项。</span><span class="sxs-lookup"><span data-stu-id="79cc0-191">If the operating system volume is required to be encrypted, select the <strong>Enable auto-unlock fixed data drive</strong> option.</span></span></p>
<p><span data-ttu-id="79cc0-192">启用此策略时，您不得禁用 " <strong> 配置固定数据驱动器的密码使用" </strong> 策略，除非允许或需要对固定数据驱动器使用自动解锁。</span><span class="sxs-lookup"><span data-stu-id="79cc0-192">When enabling this policy, you must not disable the <strong>Configure use of password for fixed data drives</strong> policy unless the use of Auto-Unlock for fixed data drives is allowed or required.</span></span></p>
<p><span data-ttu-id="79cc0-193">如果需要对固定数据驱动器使用自动解锁，必须配置要加密的操作系统卷。</span><span class="sxs-lookup"><span data-stu-id="79cc0-193">If you require the use of Auto-Unlock for fixed data drives, you must configure operating system volumes to be encrypted.</span></span></p>
<p><span data-ttu-id="79cc0-194">如果启用此策略设置，则用户需要将所有固定驱动器置于 BitLocker 保护下，并且驱动器将被加密。</span><span class="sxs-lookup"><span data-stu-id="79cc0-194">If you enable this policy setting, users are required to put all fixed drives under BitLocker protection, and the drives will be encrypted.</span></span></p>
<p><span data-ttu-id="79cc0-195">如果未配置此策略设置，则不需要用户在 BitLocker 保护下放置固定驱动器。</span><span class="sxs-lookup"><span data-stu-id="79cc0-195">If you do not configure this policy setting, users are not required to put fixed drives under BitLocker protection.</span></span> <span data-ttu-id="79cc0-196">如果在对固定数据驱动器进行加密之后应用此策略，MBAM 代理将对已加密的固定驱动器进行解密。</span><span class="sxs-lookup"><span data-stu-id="79cc0-196">If you apply this policy after fixed data drives are encrypted, the MBAM agent decrypts the encrypted fixed drives.</span></span></p>
<p><span data-ttu-id="79cc0-197">如果禁用此策略设置，用户将无法在 "BitLocker 保护" 下放置固定数据驱动器。</span><span class="sxs-lookup"><span data-stu-id="79cc0-197">If you disable this policy setting, users will not be able to put their fixed data drives under BitLocker protection.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="79cc0-198">拒绝对不受 BitLocker 保护的固定驱动器的写访问</span><span class="sxs-lookup"><span data-stu-id="79cc0-198">Deny write access to fixed drives not protected by BitLocker</span></span></p></td>
<td align="left"><p><span data-ttu-id="79cc0-199">建议的配置： <strong> 未配置</span><span class="sxs-lookup"><span data-stu-id="79cc0-199">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="79cc0-200">此策略设置确定固定驱动器是否需要 BitLocker 保护才能在计算机上写入。</span><span class="sxs-lookup"><span data-stu-id="79cc0-200">This policy setting determines whether BitLocker protection is required for fixed drives to be writable on a computer.</span></span> <span data-ttu-id="79cc0-201">启用 BitLocker 时，将应用此策略设置。</span><span class="sxs-lookup"><span data-stu-id="79cc0-201">This policy setting is applied when you turn on BitLocker.</span></span></p>
<p><span data-ttu-id="79cc0-202">当未配置策略时，计算机上的所有固定数据驱动器都将使用读写访问权限挂载。</span><span class="sxs-lookup"><span data-stu-id="79cc0-202">When the policy is not configured, all fixed data drives on the computer are mounted with read and write access.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="79cc0-203">允许从早期版本的 Windows 访问受 BitLocker 保护的固定驱动器</span><span class="sxs-lookup"><span data-stu-id="79cc0-203">Allow access to BitLocker-protected fixed drives from earlier versions of Windows</span></span></p></td>
<td align="left"><p><span data-ttu-id="79cc0-204">建议的配置： <strong> 未配置</span><span class="sxs-lookup"><span data-stu-id="79cc0-204">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="79cc0-205">启用此策略，让带有 FAT 文件系统的固定驱动器在运行 Windows Server 2008、Windows Vista、Windows XP SP3 或 Windows XP SP2 的计算机上被解锁和查看。</span><span class="sxs-lookup"><span data-stu-id="79cc0-205">Enable this policy to let fixed drives with the FAT file system be unlocked and viewed on computers that are running Windows Server 2008, Windows Vista, Windows XP with SP3, or Windows XP with SP2.</span></span></p>
<p><span data-ttu-id="79cc0-206">如果启用或未配置此策略，则可以解除对带有 FAT 文件系统格式的固定驱动器的锁定，并且可以在运行 Windows Server 2008、Windows Vista、Windows XP SP3 或 Windows XP SP2 的计算机上查看其内容。</span><span class="sxs-lookup"><span data-stu-id="79cc0-206">When the policy is enabled or not configured, fixed drives formatted with the FAT file system can be unlocked and their content can be viewed on computers that are running Windows Server 2008, Windows Vista, Windows XP with SP3, or Windows XP with SP2.</span></span> <span data-ttu-id="79cc0-207">这些操作系统具有对受 BitLocker 保护的驱动器的只读访问权限。</span><span class="sxs-lookup"><span data-stu-id="79cc0-207">These operating systems have read-only access to BitLocker-protected drives.</span></span></p>
<p><span data-ttu-id="79cc0-208">禁用策略时，无法解锁用 FAT 文件系统格式化的固定驱动器，并且无法在运行 Windows Server 2008、Windows Vista、Windows XP SP3 或 Windows XP SP2 的计算机上查看其内容。</span><span class="sxs-lookup"><span data-stu-id="79cc0-208">When the policy is disabled, fixed drives formatted with the FAT file system cannot be unlocked and their content cannot be viewed on computers that are running Windows Server 2008, Windows Vista, Windows XP with SP3, or Windows XP with SP2.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="79cc0-209">为固定驱动器配置密码的使用</span><span class="sxs-lookup"><span data-stu-id="79cc0-209">Configure use of password for fixed drives</span></span></p></td>
<td align="left"><p><span data-ttu-id="79cc0-210">建议的配置： <strong> 未配置</span><span class="sxs-lookup"><span data-stu-id="79cc0-210">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="79cc0-211">使用此策略指定是否需要密码来解锁受 BitLocker 保护的固定数据驱动器。</span><span class="sxs-lookup"><span data-stu-id="79cc0-211">Use this policy to specify whether a password is required to unlock BitLocker-protected fixed data drives.</span></span></p>
<p><span data-ttu-id="79cc0-212">如果启用此策略设置，则用户可以配置满足你定义的要求的密码。</span><span class="sxs-lookup"><span data-stu-id="79cc0-212">If you enable this policy setting, users can configure a password that meets the requirements you define.</span></span> <span data-ttu-id="79cc0-213">BitLocker 将允许用户使用驱动器上提供的任何保护程序解锁驱动器。</span><span class="sxs-lookup"><span data-stu-id="79cc0-213">BitLocker will allow users to unlock a drive with any of the protectors that are available on the drive.</span></span></p>
<p><span data-ttu-id="79cc0-214">启用 BitLocker 时强制执行这些设置，而不是在解锁卷时执行。</span><span class="sxs-lookup"><span data-stu-id="79cc0-214">These settings are enforced when turning on BitLocker, not when unlocking a volume.</span></span></p>
<p><span data-ttu-id="79cc0-215">如果禁用此策略设置，则不允许用户使用密码。</span><span class="sxs-lookup"><span data-stu-id="79cc0-215">If you disable this policy setting, users are not allowed to use a password.</span></span></p>
<p><span data-ttu-id="79cc0-216">如果未配置策略，则密码受默认设置支持，默认设置不包括密码复杂性要求，并且不需要八个字符。</span><span class="sxs-lookup"><span data-stu-id="79cc0-216">When the policy is not configured, passwords are supported with the default settings, which do not include password complexity requirements and which require only eight characters.</span></span></p>
<p><span data-ttu-id="79cc0-217">若要获得更高的安全性，请启用此策略并选择 <strong> "需要密码才能修复固定数据驱动器 </strong> "，选择 <strong> "需要密码复杂性 </strong> "，然后设置所需的 <strong> 最小密码长度 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="79cc0-217">For higher security, enable this policy and select <strong>Require password for fixed data drive</strong>, select <strong>Require password complexity</strong>, and set the desired <strong>minimum password length</strong>.</span></span></p>
<p><span data-ttu-id="79cc0-218">如果禁用此策略设置，则不允许用户使用密码。</span><span class="sxs-lookup"><span data-stu-id="79cc0-218">If you disable this policy setting, users are not allowed to use a password.</span></span></p>
<p><span data-ttu-id="79cc0-219">如果未配置此策略设置，则密码将受默认设置支持，这些设置不包括密码复杂性要求，并且不需要八个字符。</span><span class="sxs-lookup"><span data-stu-id="79cc0-219">If you do not configure this policy setting, passwords will be supported with the default settings, which do not include password complexity requirements and which require only eight characters.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="79cc0-220">选择如何恢复受 BitLocker 保护的固定驱动器</span><span class="sxs-lookup"><span data-stu-id="79cc0-220">Choose how BitLocker-protected fixed drives can be recovered</span></span></p></td>
<td align="left"><p><span data-ttu-id="79cc0-221">建议的配置： <strong> 未配置</span><span class="sxs-lookup"><span data-stu-id="79cc0-221">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="79cc0-222">将此策略配置为启用 BitLocker 数据恢复代理或将 BitLocker 恢复信息保存到 Active Directory 域服务（AD DS）。</span><span class="sxs-lookup"><span data-stu-id="79cc0-222">Configure this policy to enable the BitLocker data recovery agent or to save BitLocker recovery information to Active Directory Domain Services (AD DS).</span></span></p>
<p><span data-ttu-id="79cc0-223">如果未配置策略，则允许 BitLocker 数据恢复代理，并且不会将恢复信息备份到 AD DS。</span><span class="sxs-lookup"><span data-stu-id="79cc0-223">When the policy is not configured, the BitLocker data recovery agent is allowed, and recovery information is not backed up to AD DS.</span></span> <span data-ttu-id="79cc0-224">MBAM 不需要将恢复信息备份到 AD DS。</span><span class="sxs-lookup"><span data-stu-id="79cc0-224">MBAM does not require recovery information to be backed up to AD DS.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="79cc0-225">操作系统驱动器策略定义</span><span class="sxs-lookup"><span data-stu-id="79cc0-225">Operating System Drive Policy Definitions</span></span>


<span data-ttu-id="79cc0-226">本部分介绍在下列 GPO 节点处找到的 Microsoft BitLocker 管理和监视的操作系统驱动器策略定义：**计算机配置** \\ **策略** \\ **管理模板** \\ **Windows 组件** \\ **MDOP MBAM （BitLocker 管理）** \\ **操作系统驱动器**。</span><span class="sxs-lookup"><span data-stu-id="79cc0-226">This section describes Operating System Drive policy definitions for Microsoft BitLocker Administration and Monitoring found at the following GPO node: **Computer Configuration**\\**Policies**\\**Administrative Templates**\\**Windows Components**\\**MDOP MBAM (BitLocker Management)**\\**Operating System Drive**.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="79cc0-227">策略名称</span><span class="sxs-lookup"><span data-stu-id="79cc0-227">Policy Name</span></span></th>
<th align="left"><span data-ttu-id="79cc0-228">概述和建议的策略设置</span><span class="sxs-lookup"><span data-stu-id="79cc0-228">Overview and Suggested Policy Setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="79cc0-229">操作系统驱动器加密设置</span><span class="sxs-lookup"><span data-stu-id="79cc0-229">Operating system drive encryption settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="79cc0-230">建议的配置： <strong> 已启用</span><span class="sxs-lookup"><span data-stu-id="79cc0-230">Suggested configuration: <strong>Enabled</span></span></strong></p>
<p><span data-ttu-id="79cc0-231">通过此策略设置，你可以管理操作系统驱动器是否必须加密。</span><span class="sxs-lookup"><span data-stu-id="79cc0-231">This policy setting lets you manage whether the operating system drive must be encrypted.</span></span></p>
<p><span data-ttu-id="79cc0-232">若要获得更高的安全性，请考虑在 <strong> </strong> 使用 TPM + 引脚保护器启用 "系统/电源管理/睡眠设置" 中的以下策略设置：</span><span class="sxs-lookup"><span data-stu-id="79cc0-232">For higher security, consider disabling the following policy settings in <strong>System/Power Management/Sleep Settings</strong> when you enable them with TPM + PIN protector:</span></span></p>
<ul>
<li><p><span data-ttu-id="79cc0-233">睡眠（接通）时允许待机状态（S1-S3）</span><span class="sxs-lookup"><span data-stu-id="79cc0-233">Allow Standby States (S1-S3) When Sleeping (Plugged In)</span></span></p></li>
<li><p><span data-ttu-id="79cc0-234">睡眠时允许待机状态（S1-S3）（使用电池）</span><span class="sxs-lookup"><span data-stu-id="79cc0-234">Allow Standby States (S1-S3) When Sleeping (On Battery)</span></span></p></li>
</ul>
<p><span data-ttu-id="79cc0-235">如果你运行的是 Microsoft Windows 8 或更高版本，并且想要在没有 TPM 的计算机上使用 BitLocker，请选中 " <strong> 允许没有兼容的 TPM 的 bitlocker" </strong> 复选框。</span><span class="sxs-lookup"><span data-stu-id="79cc0-235">If you are running Microsoft Windows 8 or later, and you want to use BitLocker on a computer without a TPM, select the <strong>Allow BitLocker without a compatible TPM</strong> check box.</span></span> <span data-ttu-id="79cc0-236">在此模式下，启动时需要密码。</span><span class="sxs-lookup"><span data-stu-id="79cc0-236">In this mode, a password is required for startup.</span></span> <span data-ttu-id="79cc0-237">如果您忘记了密码，则必须使用其中一个 BitLocker 恢复选项来访问驱动器。</span><span class="sxs-lookup"><span data-stu-id="79cc0-237">If you forget the password, you have to use one of the BitLocker recovery options to access the drive.</span></span></p>
<p><span data-ttu-id="79cc0-238">在具有兼容的 TPM 的计算机上，启动时可以使用两种类型的身份验证方法为加密数据提供额外保护。</span><span class="sxs-lookup"><span data-stu-id="79cc0-238">On a computer with a compatible TPM, two types of authentication methods can be used at startup to provide added protection for encrypted data.</span></span> <span data-ttu-id="79cc0-239">当计算机启动时，它只能使用 TPM 进行身份验证，也可以要求输入个人识别码（PIN）。</span><span class="sxs-lookup"><span data-stu-id="79cc0-239">When the computer starts, it can use only the TPM for authentication, or it can also require the entry of a personal identification number (PIN).</span></span></p>
<p><span data-ttu-id="79cc0-240">如果启用此策略设置，则用户必须将操作系统驱动器置于 BitLocker 保护下，并且将加密驱动器。</span><span class="sxs-lookup"><span data-stu-id="79cc0-240">If you enable this policy setting, users have to put the operating system drive under BitLocker protection, and the drive will be encrypted.</span></span></p>
<p><span data-ttu-id="79cc0-241">如果禁用此策略，用户将无法在 BitLocker 保护下放置操作系统驱动器。</span><span class="sxs-lookup"><span data-stu-id="79cc0-241">If you disable this policy, users will not be able to put the operating system drive under BitLocker protection.</span></span> <span data-ttu-id="79cc0-242">如果在加密操作系统驱动器后应用此策略，则将解密驱动器。</span><span class="sxs-lookup"><span data-stu-id="79cc0-242">If you apply this policy after the operating system drive is encrypted, the drive will be decrypted.</span></span></p>
<p><span data-ttu-id="79cc0-243">如果未配置此策略，则不需要将操作系统驱动器置于 "BitLocker 保护" 下。</span><span class="sxs-lookup"><span data-stu-id="79cc0-243">If you do not configure this policy, the operating system drive is not required to be placed under BitLocker protection.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="79cc0-244">配置 TPM 平台验证配置文件</span><span class="sxs-lookup"><span data-stu-id="79cc0-244">Configure TPM platform validation profile</span></span></p></td>
<td align="left"><p><span data-ttu-id="79cc0-245">建议的配置： <strong> 未配置</span><span class="sxs-lookup"><span data-stu-id="79cc0-245">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="79cc0-246">此策略设置允许你配置计算机上的 TPM 安全硬件如何保护 BitLocker 加密密钥。</span><span class="sxs-lookup"><span data-stu-id="79cc0-246">This policy setting lets you configure how the TPM security hardware on a computer secures the BitLocker encryption key.</span></span> <span data-ttu-id="79cc0-247">如果计算机没有兼容的 TPM，或者如果 BitLocker 已使用 TPM 保护启用，则此策略设置不适用。</span><span class="sxs-lookup"><span data-stu-id="79cc0-247">This policy setting does not apply if the computer does not have a compatible TPM or if BitLocker has already been turned on with TPM protection.</span></span></p>
<p><span data-ttu-id="79cc0-248">如果未配置此策略设置，TPM 将使用由安装脚本指定的默认平台验证配置文件或平台验证配置文件。</span><span class="sxs-lookup"><span data-stu-id="79cc0-248">When this policy setting is not configured, the TPM uses the default platform validation profile or the platform validation profile that is specified by the setup script.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="79cc0-249">选择可以如何恢复受 BitLocker 保护的操作系统驱动器</span><span class="sxs-lookup"><span data-stu-id="79cc0-249">Choose how BitLocker-protected operating system drives can be recovered</span></span></p></td>
<td align="left"><p><span data-ttu-id="79cc0-250">建议的配置： <strong> 未配置</span><span class="sxs-lookup"><span data-stu-id="79cc0-250">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="79cc0-251">将此策略配置为启用 BitLocker 数据恢复代理或将 BitLocker 恢复信息保存到 Active Directory 域服务（AD DS）。</span><span class="sxs-lookup"><span data-stu-id="79cc0-251">Configure this policy to enable the BitLocker data recovery agent or to save BitLocker recovery information to Active Directory Domain Services (AD DS).</span></span></p>
<p><span data-ttu-id="79cc0-252">如果未配置此策略，则允许数据恢复代理，并且不会将恢复信息备份到 AD DS。</span><span class="sxs-lookup"><span data-stu-id="79cc0-252">When this policy is not configured, the data recovery agent is allowed, and recovery information is not backed up to AD DS.</span></span></p>
<p><span data-ttu-id="79cc0-253">MBAM 操作不需要将恢复信息备份到 AD DS。</span><span class="sxs-lookup"><span data-stu-id="79cc0-253">MBAM operation does not require recovery information to be backed up to AD DS.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="79cc0-254">可移动驱动器策略定义</span><span class="sxs-lookup"><span data-stu-id="79cc0-254">Removable Drive Policy Definitions</span></span>


<span data-ttu-id="79cc0-255">本部分介绍在下列 GPO 节点处找到的 Microsoft BitLocker 管理和监视的可移动驱动器策略定义：**计算机配置** \\ **策略** \\ **管理模板** \\ **Windows 组件** \\ **MDOP MBAM （BitLocker Management）**  \\  **可移动驱动器**。</span><span class="sxs-lookup"><span data-stu-id="79cc0-255">This section describes Removable Drive Policy definitions for Microsoft BitLocker Administration and Monitoring found at the following GPO node: **Computer Configuration**\\**Policies**\\**Administrative Templates**\\**Windows Components**\\**MDOP MBAM (BitLocker Management)** \\ **Removable Drive**.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="79cc0-256">策略名称</span><span class="sxs-lookup"><span data-stu-id="79cc0-256">Policy Name</span></span></th>
<th align="left"><span data-ttu-id="79cc0-257">概述和建议的策略设置</span><span class="sxs-lookup"><span data-stu-id="79cc0-257">Overview and Suggested Policy Setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="79cc0-258">控制可移动驱动器上的 BitLocker 的使用</span><span class="sxs-lookup"><span data-stu-id="79cc0-258">Control use of BitLocker on removable drives</span></span></p></td>
<td align="left"><p><span data-ttu-id="79cc0-259">建议的配置： <strong> 已启用</span><span class="sxs-lookup"><span data-stu-id="79cc0-259">Suggested configuration: <strong>Enabled</span></span></strong></p>
<p><span data-ttu-id="79cc0-260">此策略控制对可移动数据驱动器使用 BitLocker。</span><span class="sxs-lookup"><span data-stu-id="79cc0-260">This policy controls the use of BitLocker on removable data drives.</span></span></p>
<p><span data-ttu-id="79cc0-261">启用 " <strong> 允许用户对可移动数据驱动器应用 bitlocker 保护" </strong> 选项，以允许用户在可移动数据驱动器上运行 bitlocker 设置向导。</span><span class="sxs-lookup"><span data-stu-id="79cc0-261">Enable the <strong>Allow users to apply BitLocker protection on removable data drives</strong> option to allow users to run the BitLocker setup wizard on a removable data drive.</span></span></p>
<p><span data-ttu-id="79cc0-262">启用 " <strong> 允许用户暂停和解密可移动数据驱动器上的 bitlocker" </strong> 选项，允许用户从驱动器中删除 bitlocker 驱动器加密，或在执行维护时暂停加密。</span><span class="sxs-lookup"><span data-stu-id="79cc0-262">Enable the <strong>Allow users to suspend and decrypt BitLocker on removable data drives</strong> option to allow users to remove BitLocker drive encryption from the drive or to suspend the encryption while maintenance is performed.</span></span></p>
<p><span data-ttu-id="79cc0-263">如果启用此策略并选中 " <strong> 允许用户对可移动数据驱动器应用 BitLocker 保护" </strong> 选项，则 MBAM 客户端会将可移动驱动器的恢复信息保存到 MBAM 密钥恢复服务器，并允许用户在密码丢失时恢复驱动器。</span><span class="sxs-lookup"><span data-stu-id="79cc0-263">When this policy is enabled and the <strong>Allow users to apply BitLocker protection on removable data drives</strong> option is selected, the MBAM Client saves the recovery information about removable drives to the MBAM key recovery server and allows users to recover the drive if the password is lost.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="79cc0-264">拒绝对不受 BitLocker 保护的可移动驱动器的写访问</span><span class="sxs-lookup"><span data-stu-id="79cc0-264">Deny write access to removable drives not protected by BitLocker</span></span></p></td>
<td align="left"><p><span data-ttu-id="79cc0-265">建议的配置： <strong> 未配置</span><span class="sxs-lookup"><span data-stu-id="79cc0-265">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="79cc0-266">启用此策略以仅允许对受 BitLocker 保护的驱动器进行写入访问。</span><span class="sxs-lookup"><span data-stu-id="79cc0-266">Enable this policy to allow only write access to BitLocker protected drives.</span></span></p>
<p><span data-ttu-id="79cc0-267">如果启用此策略，则计算机上的所有可移动数据驱动器都需要加密才能允许写入访问。</span><span class="sxs-lookup"><span data-stu-id="79cc0-267">When this policy is enabled, all removable data drives on the computer require encryption before write access is allowed.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="79cc0-268">允许从早期版本的 Windows 访问受 BitLocker 保护的可移动驱动器</span><span class="sxs-lookup"><span data-stu-id="79cc0-268">Allow access to BitLocker-protected removable drives from earlier versions of Windows</span></span></p></td>
<td align="left"><p><span data-ttu-id="79cc0-269">建议的配置： <strong> 未配置</span><span class="sxs-lookup"><span data-stu-id="79cc0-269">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="79cc0-270">启用此策略以允许在运行 Windows Server 2008、Windows Vista、Windows XP SP3 或 Windows XP SP2 的计算机上解除锁定和查看具有 FAT 文件系统的固定驱动器。</span><span class="sxs-lookup"><span data-stu-id="79cc0-270">Enable this policy to allow fixed drives with the FAT file system to be unlocked and viewed on computers that are running Windows Server 2008, Windows Vista, Windows XP with SP3, or Windows XP with SP2.</span></span></p>
<p><span data-ttu-id="79cc0-271">如果未配置此策略，则可以在运行 Windows Server 2008、Windows Vista、windows XP SP3 或具有 SP2 的 Windows XP 的计算机上解锁带有 FAT 文件系统格式的可移动数据驱动器，并且可以查看其内容。</span><span class="sxs-lookup"><span data-stu-id="79cc0-271">When this policy is not configured, removable data drives formatted with the FAT file system can be unlocked on computers that are running Windows Server 2008, Windows Vista, Windows XP with SP3, or Windows XP with SP2, and their content can be viewed.</span></span> <span data-ttu-id="79cc0-272">这些操作系统具有对受 BitLocker 保护的驱动器的只读访问权限。</span><span class="sxs-lookup"><span data-stu-id="79cc0-272">These operating systems have read-only access to BitLocker-protected drives.</span></span></p>
<p><span data-ttu-id="79cc0-273">禁用策略时，无法解锁用 FAT 文件系统格式化的可移动驱动器，并且无法在运行 Windows Server 2008、Windows Vista、Windows XP SP3 或 Windows XP SP2 的计算机上查看其内容。</span><span class="sxs-lookup"><span data-stu-id="79cc0-273">When the policy is disabled, removable drives formatted with the FAT file system cannot be unlocked and their content cannot be viewed on computers that are running Windows Server 2008, Windows Vista, Windows XP with SP3, or Windows XP with SP2.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="79cc0-274">为可移动数据驱动器配置密码的使用</span><span class="sxs-lookup"><span data-stu-id="79cc0-274">Configure use of password for removable data drives</span></span></p></td>
<td align="left"><p><span data-ttu-id="79cc0-275">建议的配置： <strong> 未配置</span><span class="sxs-lookup"><span data-stu-id="79cc0-275">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="79cc0-276">启用此策略以在可移动数据驱动器上配置密码保护。</span><span class="sxs-lookup"><span data-stu-id="79cc0-276">Enable this policy to configure password protection on removable data drives.</span></span></p>
<p><span data-ttu-id="79cc0-277">如果未配置此策略，则密码支持的默认设置（不包括密码复杂性要求），并且不需要八个字符。</span><span class="sxs-lookup"><span data-stu-id="79cc0-277">When this policy is not configured, passwords are supported with the default settings, which do not include password complexity requirements and which require only eight characters.</span></span></p>
<p><span data-ttu-id="79cc0-278">为了提高安全性，你可以启用此策略并选中 <strong> "可移动数据驱动器需要密码 </strong> "，选择 <strong> "需要密码复杂性 </strong> "，然后设置首选的 <strong> 最小密码长度 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="79cc0-278">For increased security, you may enable this policy and check <strong>Require password for removable data drive</strong>, select <strong>Require password complexity</strong>, and set the preferred <strong>minimum password length</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="79cc0-279">选择可以如何恢复受 BitLocker 保护的可移动驱动器</span><span class="sxs-lookup"><span data-stu-id="79cc0-279">Choose how BitLocker-protected removable drives can be recovered</span></span></p></td>
<td align="left"><p><span data-ttu-id="79cc0-280">建议的配置： <strong> 未配置</span><span class="sxs-lookup"><span data-stu-id="79cc0-280">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="79cc0-281">将此策略配置为启用 BitLocker 数据恢复代理或将 BitLocker 恢复信息保存到 Active Directory 域服务（AD DS）。</span><span class="sxs-lookup"><span data-stu-id="79cc0-281">Configure this policy to enable the BitLocker data recovery agent or to save BitLocker recovery information to Active Directory Domain Services (AD DS).</span></span></p>
<p><span data-ttu-id="79cc0-282">如果设置为 <strong> "未配置" </strong> ，则允许数据恢复代理，并且不会将恢复信息备份到 AD DS。</span><span class="sxs-lookup"><span data-stu-id="79cc0-282">When set to <strong>Not Configured</strong>, the data recovery agent is allowed and recovery information is not backed up to AD DS.</span></span></p>
<p><span data-ttu-id="79cc0-283">MBAM 操作不需要将恢复信息备份到 AD DS。</span><span class="sxs-lookup"><span data-stu-id="79cc0-283">MBAM operation does not require recovery information to be backed up to AD DS.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="79cc0-284">相关主题</span><span class="sxs-lookup"><span data-stu-id="79cc0-284">Related topics</span></span>


[<span data-ttu-id="79cc0-285">MBAM 2.0 部署先决条件</span><span class="sxs-lookup"><span data-stu-id="79cc0-285">MBAM 2.0 Deployment Prerequisites</span></span>](mbam-20-deployment-prerequisites-mbam-2.md)









