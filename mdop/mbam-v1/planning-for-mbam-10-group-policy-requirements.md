---
title: 计划 MBAM 1.0 组策略要求
description: 计划 MBAM 1.0 组策略要求
author: dansimp
ms.assetid: 0fc9c509-7850-4a8e-bb82-b949025bcb02
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f5061748107dc1d00baa41188b8cf240ec187317
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798045"
---
# <span data-ttu-id="130e9-103">计划 MBAM 1.0 组策略要求</span><span class="sxs-lookup"><span data-stu-id="130e9-103">Planning for MBAM 1.0 Group Policy Requirements</span></span>


<span data-ttu-id="130e9-104">Microsoft BitLocker 管理和监视（MBAM）客户端管理需要应用自定义组策略设置。</span><span class="sxs-lookup"><span data-stu-id="130e9-104">Microsoft BitLocker Administration and Monitoring (MBAM) Client management requires custom Group Policy settings to be applied.</span></span> <span data-ttu-id="130e9-105">本主题介绍了使用 MBAM 管理企业中的 BitLocker 驱动器加密时，组策略对象（GPO）可用的策略选项。</span><span class="sxs-lookup"><span data-stu-id="130e9-105">This topic describes the available policy options for Group Policy Object (GPO) when you use MBAM to manage BitLocker Drive Encryption in the enterprise.</span></span>

**<span data-ttu-id="130e9-106">重要提示</span><span class="sxs-lookup"><span data-stu-id="130e9-106">Important</span></span>**  
<span data-ttu-id="130e9-107">MBAM 不使用 Windows BitLocker 驱动器加密的默认 GPO 设置。</span><span class="sxs-lookup"><span data-stu-id="130e9-107">MBAM does not use the default GPO settings for Windows BitLocker drive encryption.</span></span> <span data-ttu-id="130e9-108">如果启用了默认设置，它们可能会导致冲突行为。</span><span class="sxs-lookup"><span data-stu-id="130e9-108">If the default settings are enabled, they can cause conflicting behavior.</span></span> <span data-ttu-id="130e9-109">若要启用 MBAM 来管理 BitLocker，必须在安装 MBAM 组策略模板之后定义 GPO 策略设置。</span><span class="sxs-lookup"><span data-stu-id="130e9-109">To enable MBAM to manage BitLocker, you must define the GPO policy settings after you install the MBAM Group Policy Template.</span></span>



<span data-ttu-id="130e9-110">在安装 MBAM 组策略模板之后，你可以查看和修改可启用 MBAM 管理企业 BitLocker 加密的可用自定义 MBAM GPO 策略设置。</span><span class="sxs-lookup"><span data-stu-id="130e9-110">After you install the MBAM Group Policy template, you can view and modify the available custom MBAM GPO policy settings that enable MBAM to manage the enterprise BitLocker encryption.</span></span> <span data-ttu-id="130e9-111">MBAM 组策略模板必须安装在能够运行组策略管理控制台（GPMC）或高级组策略管理（AGPM） MDOP 技术的计算机上。</span><span class="sxs-lookup"><span data-stu-id="130e9-111">The MBAM Group Policy template must be installed on a computer that is capable of running the Group Policy Management Console (GPMC) or the Advanced Group Policy Management (AGPM) MDOP technology.</span></span> <span data-ttu-id="130e9-112">接下来，要编辑适用的 gpo，请打开 GPMC 或 AGPM，然后导航到以下 GPO 节点：**计算机配置** \\ **管理模板** \\ **Windows 组件** \\ **MDOP MBAM （BitLocker 管理）**。</span><span class="sxs-lookup"><span data-stu-id="130e9-112">Next, to edit the applicable GPO, open the GPMC or AGPM, and then navigate to the following GPO node: **Computer Configuration**\\**Administrative Templates**\\**Windows Components**\\**MDOP MBAM (BitLocker Management)**.</span></span>

<span data-ttu-id="130e9-113">MDOP MBAM （BitLocker Management） GPO 节点分别包含四个全局策略设置和四个子 GPO 设置节点。</span><span class="sxs-lookup"><span data-stu-id="130e9-113">The MDOP MBAM (BitLocker Management) GPO node contains four global policy settings and four child GPO setting nodes, respectively.</span></span> <span data-ttu-id="130e9-114">四个 GPO 全局策略设置为：客户端管理、固定驱动器、操作系统驱动器和可移动驱动器。</span><span class="sxs-lookup"><span data-stu-id="130e9-114">The four GPO global policy settings are: Client Management, Fixed Drive, Operating System Drive, and Removable Drive.</span></span> <span data-ttu-id="130e9-115">以下各节提供了策略定义和建议的策略设置，可帮助你规划 MBAM GPO 策略设置要求。</span><span class="sxs-lookup"><span data-stu-id="130e9-115">The following sections provide policy definitions and suggested policy settings to help you plan for the MBAM GPO policy setting requirements.</span></span>

**<span data-ttu-id="130e9-116">注意</span><span class="sxs-lookup"><span data-stu-id="130e9-116">Note</span></span>**  
<span data-ttu-id="130e9-117">有关配置建议的最低 GPO 设置以使 MBAM 管理 BitLocker 加密的详细信息，请参阅[如何编辑 MBAM 1.0 GPO 设置](how-to-edit-mbam-10-gpo-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="130e9-117">For more information about configuring the minimum suggested GPO settings to enable MBAM to manage BitLocker encryption, see [How to Edit MBAM 1.0 GPO Settings](how-to-edit-mbam-10-gpo-settings.md).</span></span>



## <span data-ttu-id="130e9-118">全局策略定义</span><span class="sxs-lookup"><span data-stu-id="130e9-118">Global policy definitions</span></span>


<span data-ttu-id="130e9-119">本部分介绍 MBAM 全局策略定义，可在以下 GPO 节点找到：**计算机配置** \\ **管理模板** \\ **Windows 组件** \\ **MDOP MBAM （BitLocker Management）**。</span><span class="sxs-lookup"><span data-stu-id="130e9-119">This section describes the MBAM Global policy definitions, which can be found at the following GPO node: **Computer Configuration**\\**Administrative Templates**\\**Windows Components**\\**MDOP MBAM (BitLocker Management)**.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="130e9-120">策略名称</span><span class="sxs-lookup"><span data-stu-id="130e9-120">Policy Name</span></span></th>
<th align="left"><span data-ttu-id="130e9-121">概述和建议的策略设置</span><span class="sxs-lookup"><span data-stu-id="130e9-121">Overview and Suggested Policy Setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="130e9-122">选择驱动器加密方法和密码强度</span><span class="sxs-lookup"><span data-stu-id="130e9-122">Choose drive encryption method and cipher strength</span></span></p></td>
<td align="left"><p><span data-ttu-id="130e9-123">建议的配置： <strong> 未配置</span><span class="sxs-lookup"><span data-stu-id="130e9-123">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="130e9-124">将此策略配置为使用特定加密方法和密码强度。</span><span class="sxs-lookup"><span data-stu-id="130e9-124">Configure this policy to use a specific encryption method and cipher strength.</span></span></p>
<p><span data-ttu-id="130e9-125">如果未配置此策略，BitLocker 将使用具有扩散器的 AES 128 位的默认加密方法或由安装脚本指定的加密方法。</span><span class="sxs-lookup"><span data-stu-id="130e9-125">When this policy is not configured, BitLocker uses the default encryption method of AES 128-bit with Diffuser or the encryption method specified by the setup script.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="130e9-126">在重启时防止内存覆盖</span><span class="sxs-lookup"><span data-stu-id="130e9-126">Prevent memory overwrite on restart</span></span></p></td>
<td align="left"><p><span data-ttu-id="130e9-127">建议的配置： <strong> 未配置</span><span class="sxs-lookup"><span data-stu-id="130e9-127">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="130e9-128">配置此策略可提高重启性能，而无需在重新启动时覆盖内存中的 BitLocker 机密。</span><span class="sxs-lookup"><span data-stu-id="130e9-128">Configure this policy to improve restart performance without overwriting BitLocker secrets in memory on restart.</span></span></p>
<p><span data-ttu-id="130e9-129">如果未配置此策略，当计算机重新启动时，将从内存中删除 BitLocker 机密。</span><span class="sxs-lookup"><span data-stu-id="130e9-129">When this policy is not configured, BitLocker secrets are removed from memory when the computer restarts.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="130e9-130">验证智能卡证书使用规则</span><span class="sxs-lookup"><span data-stu-id="130e9-130">Validate smart card certificate usage rule</span></span></p></td>
<td align="left"><p><span data-ttu-id="130e9-131">建议的配置： <strong> 未配置</span><span class="sxs-lookup"><span data-stu-id="130e9-131">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="130e9-132">将此策略配置为使用基于智能卡证书的 BitLocker 保护。</span><span class="sxs-lookup"><span data-stu-id="130e9-132">Configure this policy to use smartcard certificate-based BitLocker protection.</span></span></p>
<p><span data-ttu-id="130e9-133">如果未配置此策略，则使用默认对象标识符1.3.6.1.4.1.311.67.1.1 指定证书。</span><span class="sxs-lookup"><span data-stu-id="130e9-133">When this policy is not configured, a default object identifier 1.3.6.1.4.1.311.67.1.1 is used to specify a certificate.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="130e9-134">为你的组织提供唯一标识符</span><span class="sxs-lookup"><span data-stu-id="130e9-134">Provide the unique identifiers for your organization</span></span></p></td>
<td align="left"><p><span data-ttu-id="130e9-135">建议的配置： <strong> 未配置</span><span class="sxs-lookup"><span data-stu-id="130e9-135">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="130e9-136">将此策略配置为使用基于证书的数据恢复代理或 BitLocker To Go 阅读器。</span><span class="sxs-lookup"><span data-stu-id="130e9-136">Configure this policy to use a certificate-based data recovery agent or the BitLocker To Go reader.</span></span></p>
<p><span data-ttu-id="130e9-137">如果未配置此策略，则 <strong> </strong> 不会使用 "标识" 字段。</span><span class="sxs-lookup"><span data-stu-id="130e9-137">When this policy is not configured, the <strong>Identification</strong> field is not used.</span></span></p>
<p><span data-ttu-id="130e9-138">如果您的公司需要更高的安全测量，您可能需要配置 <strong> 标识 </strong> 字段，以确保所有 USB 设备都具有此字段集，并且它们与此组策略设置对齐。</span><span class="sxs-lookup"><span data-stu-id="130e9-138">If your company requires higher security measurements, you may want to configure the <strong>Identification</strong> field to make sure that all USB devices have this field set and that they are aligned with this Group Policy setting.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="130e9-139">客户端管理策略定义</span><span class="sxs-lookup"><span data-stu-id="130e9-139">Client Management policy definitions</span></span>


<span data-ttu-id="130e9-140">本部分介绍 MBAM 的客户端管理策略定义，可在以下 GPO 节点找到：**计算机配置** \\ **管理模板** \\ **Windows 组件** \\ **MDOP MBAM （BitLocker Management）**  \\  **客户端管理**。</span><span class="sxs-lookup"><span data-stu-id="130e9-140">This section describes the Client Management policy definitions for MBAM, found at the following GPO node: **Computer Configuration**\\**Administrative Templates**\\**Windows Components**\\**MDOP MBAM (BitLocker Management)** \\ **Client Management**.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="130e9-141">策略名称</span><span class="sxs-lookup"><span data-stu-id="130e9-141">Policy Name</span></span></th>
<th align="left"><span data-ttu-id="130e9-142">概述和建议的策略设置</span><span class="sxs-lookup"><span data-stu-id="130e9-142">Overview and Suggested Policy Settings</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="130e9-143">配置 MBAM 服务</span><span class="sxs-lookup"><span data-stu-id="130e9-143">Configure MBAM Services</span></span></p></td>
<td align="left"><p><span data-ttu-id="130e9-144">建议的配置： <strong> 已启用</span><span class="sxs-lookup"><span data-stu-id="130e9-144">Suggested Configuration: <strong>Enabled</span></span></strong></p>
<ul>
<li><p><strong><span data-ttu-id="130e9-145">MBAM 恢复和硬件服务终结点 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="130e9-145">MBAM Recovery and Hardware service endpoint</strong>.</span></span> <span data-ttu-id="130e9-146">这是你必须配置以启用 MBAM 客户端 BitLocker 加密管理的第一个策略设置。</span><span class="sxs-lookup"><span data-stu-id="130e9-146">This is the first policy setting that you must configure to enable the MBAM Client BitLocker encryption management.</span></span> <span data-ttu-id="130e9-147">对于此设置，请输入类似于以下示例的终结点位置： <strong> http:// </strong><em> &lt; MBAM 管理和监视服务器名称 &gt; </em><strong> ： </strong><em> &lt; 端口将 web 服务绑定到 &gt; </em><strong> /MBAMRecoveryAndHardwareService/CoreService.svc </strong> 。</span><span class="sxs-lookup"><span data-stu-id="130e9-147">For this setting, enter the endpoint location similar to the following example: <strong>http://</strong><em>&lt;MBAM Administration and Monitoring Server Name&gt;</em><strong>:</strong><em>&lt;port the web service is bound to&gt;</em><strong>/MBAMRecoveryAndHardwareService/CoreService.svc</strong>.</span></span></p></li>
<li><p><strong><span data-ttu-id="130e9-148">选择要存储的 BitLocker 恢复信息 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="130e9-148">Select BitLocker recovery information to store</strong>.</span></span> <span data-ttu-id="130e9-149">此策略设置允许你配置密钥恢复服务以备份 BitLocker 恢复信息。</span><span class="sxs-lookup"><span data-stu-id="130e9-149">This policy setting lets you configure the key recovery service to back up the BitLocker recovery information.</span></span> <span data-ttu-id="130e9-150">它还允许你配置状态报告服务以收集合规性和审核报告。</span><span class="sxs-lookup"><span data-stu-id="130e9-150">It also lets you configure the status reporting service for collecting compliance and audit reports.</span></span> <span data-ttu-id="130e9-151">该策略提供一种管理方法来恢复 BitLocker 加密的数据，以帮助防止因缺少密钥信息而导致数据丢失。</span><span class="sxs-lookup"><span data-stu-id="130e9-151">The policy provides an administrative method of recovering data encrypted by BitLocker to help prevent data loss due to the lack of key information.</span></span> <span data-ttu-id="130e9-152">状态报告和密钥恢复活动将自动并以静默方式发送到配置的报表服务器位置。</span><span class="sxs-lookup"><span data-stu-id="130e9-152">Status report and key recovery activity will automatically and silently be sent to the configured report server location.</span></span></p>
<p><span data-ttu-id="130e9-153">如果未配置或禁用此策略设置，将不会保存密钥恢复信息，并且不会向服务器报告状态报告和密钥恢复活动。</span><span class="sxs-lookup"><span data-stu-id="130e9-153">If you do not configure or if you disable this policy setting, the key recovery information will not be saved, and status report and key recovery activity will not be reported to server.</span></span> <span data-ttu-id="130e9-154">当此设置设置为 <strong> 恢复密码和密钥包时 </strong> ，将自动将恢复密码和密钥数据包备份到配置的密钥恢复服务器位置。</span><span class="sxs-lookup"><span data-stu-id="130e9-154">When this setting is set to <strong>Recovery Password and key package</strong>, the recovery password and key package will be automatically and silently backed up to the configured key recovery server location.</span></span></p></li>
<li><p><strong><span data-ttu-id="130e9-155">以分钟为单位输入客户端检查状态频率 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="130e9-155">Enter the client checking status frequency in minutes</strong>.</span></span> <span data-ttu-id="130e9-156">此策略设置管理客户端在客户端计算机上检查 BitLocker 保护策略和状态的频率。</span><span class="sxs-lookup"><span data-stu-id="130e9-156">This policy setting manages how frequently the client checks the BitLocker protection policies and the status on the client computer.</span></span> <span data-ttu-id="130e9-157">此策略还管理将客户端合规性状态保存到服务器的频率。</span><span class="sxs-lookup"><span data-stu-id="130e9-157">This policy also manages how frequently the client compliance status is saved to the server.</span></span> <span data-ttu-id="130e9-158">客户端在客户端计算机上检查 BitLocker 保护策略和状态，并且它还将按配置的频率备份客户端恢复密钥。</span><span class="sxs-lookup"><span data-stu-id="130e9-158">The client checks the BitLocker protection policies and status on the client computer, and it also backs up the client recovery key at the configured frequency.</span></span></p>
<p><span data-ttu-id="130e9-159">根据公司建立的要求检查计算机合规性状态的频率以及备份客户端恢复密钥的频率，设置此频率。</span><span class="sxs-lookup"><span data-stu-id="130e9-159">Set this frequency based on the requirement established by your company on how frequently to check the compliance status of the computer, and how frequently to back up the client recovery key.</span></span></p></li>
<li><p><strong><span data-ttu-id="130e9-160">MBAM 状态报告服务终结点 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="130e9-160">MBAM Status reporting service endpoint</strong>.</span></span> <span data-ttu-id="130e9-161">这是你必须配置以启用 MBAM 客户端 BitLocker 加密管理的第二个策略设置。</span><span class="sxs-lookup"><span data-stu-id="130e9-161">This is the second policy setting that you must configure to enable MBAM Client BitLocker encryption management.</span></span> <span data-ttu-id="130e9-162">对于此设置，请使用以下示例输入终结点位置： <strong> http:// </strong><em> &lt; MBAM 管理和监视服务器名称 &gt; </em><strong> ： </strong><em> &lt; 端口将 web 服务绑定到 &gt; </em><strong> /MBAMComplianceStatusService/StatusReportingService。</span><span class="sxs-lookup"><span data-stu-id="130e9-162">For this setting, enter the endpoint location by using the following example: <strong>http://</strong><em>&lt;MBAM Administration and Monitoring Server Name&gt;</em><strong>:</strong><em>&lt;port the web service is bound to&gt;</em><strong>/MBAMComplianceStatusService/StatusReportingService.</span></span> <span data-ttu-id="130e9-163">svc </strong> 。</span><span class="sxs-lookup"><span data-stu-id="130e9-163">svc</strong>.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="130e9-164">允许硬件兼容性检查</span><span class="sxs-lookup"><span data-stu-id="130e9-164">Allow hardware compatibility checking</span></span></p></td>
<td align="left"><p><span data-ttu-id="130e9-165">建议的配置： <strong> 已启用</span><span class="sxs-lookup"><span data-stu-id="130e9-165">Suggested Configuration: <strong>Enabled</span></span></strong></p>
<p><span data-ttu-id="130e9-166">此策略设置允许你在 MBAM 客户端计算机的驱动器上启用 BitLocker 保护之前，管理硬件兼容性验证。</span><span class="sxs-lookup"><span data-stu-id="130e9-166">This policy setting lets you manage the verification of hardware compatibility before you enable BitLocker protection on drives of MBAM client computers.</span></span></p>
<p><span data-ttu-id="130e9-167">如果您的企业有较旧的计算机硬件或不支持受信任的平台模块（TPM）的计算机，则应启用此策略选项。</span><span class="sxs-lookup"><span data-stu-id="130e9-167">You should enable this policy option if your enterprise has older computer hardware or computers that do not support Trusted Platform Module (TPM).</span></span> <span data-ttu-id="130e9-168">如果满足上述任一条件，请启用硬件兼容性验证，以确保 MBAM 仅应用于支持 BitLocker 的计算机模型。</span><span class="sxs-lookup"><span data-stu-id="130e9-168">If either of these criteria is true, enable the hardware compatibility verification to make sure that MBAM is applied only to computer models that support BitLocker.</span></span> <span data-ttu-id="130e9-169">如果你的组织中的所有计算机都支持 BitLocker，则无需部署硬件兼容性，你可以将此策略设置为 " <strong> 未配置" </strong> 。</span><span class="sxs-lookup"><span data-stu-id="130e9-169">If all computers in your organization support BitLocker, you do not have to deploy the Hardware Compatibility, and you can set this policy to <strong>Not Configured</strong>.</span></span></p>
<p><span data-ttu-id="130e9-170">如果启用此策略设置，则在该策略在计算机驱动器上启用 BitLocker 保护之前，每隔24小时验证一次硬件兼容性列表的计算机型号。</span><span class="sxs-lookup"><span data-stu-id="130e9-170">If you enable this policy setting, the model of the computer is validated against the hardware compatibility list once every 24 hours, before the policy enables BitLocker protection on a computer drive.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="130e9-171">注意</span><span class="sxs-lookup"><span data-stu-id="130e9-171">Note</span></span></strong><br/><p><span data-ttu-id="130e9-172">在启用此策略设置之前，请确保你已 <strong> </strong> 在 <strong> 配置 MBAM 服务策略选项中配置了 MBAM 恢复和硬件服务终结点设置 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="130e9-172">Before enabling this policy setting, make sure that you have configured the <strong>MBAM Recovery and Hardware service endpoint</strong> setting in the <strong>Configure MBAM Services</strong> policy options.</span></span></p>
</div>
<div>

</div>
<p><span data-ttu-id="130e9-173">如果禁用或未配置此策略设置，则不会根据硬件兼容性列表验证计算机模型。</span><span class="sxs-lookup"><span data-stu-id="130e9-173">If you either disable or do not configure this policy setting, the computer model is not validated against the hardware compatibility list.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="130e9-174">配置用户豁免策略</span><span class="sxs-lookup"><span data-stu-id="130e9-174">Configure user exemption policy</span></span></p></td>
<td align="left"><p><span data-ttu-id="130e9-175">建议的配置： <strong> 未配置</span><span class="sxs-lookup"><span data-stu-id="130e9-175">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="130e9-176">此策略设置允许你配置网站地址、电子邮件地址或电话号码，以指示用户向 BitLocker 加密请求豁免。</span><span class="sxs-lookup"><span data-stu-id="130e9-176">This policy setting lets you configure a web site address, email address, or phone number that will instruct a user to request an exemption from BitLocker encryption.</span></span></p>
<p><span data-ttu-id="130e9-177">如果启用此策略设置并提供网站地址、电子邮件地址或电话号码，用户将看到一个对话框，其中提供了有关如何申请来自 BitLocker 保护的豁免的说明。</span><span class="sxs-lookup"><span data-stu-id="130e9-177">If you enable this policy setting and provide a web site address, email address, or phone number, users will see a dialog with instructions on how to apply for an exemption from BitLocker protection.</span></span> <span data-ttu-id="130e9-178">有关如何为用户启用 BitLocker 加密免除的详细信息，请参阅 <a href="how-to-manage-user-bitlocker-encryption-exemptions-mbam-1.md" data-raw-source="[How to Manage User BitLocker Encryption Exemptions](how-to-manage-user-bitlocker-encryption-exemptions-mbam-1.md)"> 如何管理用户 Bitlocker 加密免除 </a> 。</span><span class="sxs-lookup"><span data-stu-id="130e9-178">For more information about how to enable BitLocker encryption exemptions for users, see <a href="how-to-manage-user-bitlocker-encryption-exemptions-mbam-1.md" data-raw-source="[How to Manage User BitLocker Encryption Exemptions](how-to-manage-user-bitlocker-encryption-exemptions-mbam-1.md)">How to Manage User BitLocker Encryption Exemptions</a>.</span></span></p>
<p><span data-ttu-id="130e9-179">如果禁用或未配置此策略设置，则不会向用户显示有关如何申请豁免请求的说明。</span><span class="sxs-lookup"><span data-stu-id="130e9-179">If you either disable or do not configure this policy setting, the instructions about how to apply for an exemption request will not be presented to users.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="130e9-180">注意</span><span class="sxs-lookup"><span data-stu-id="130e9-180">Note</span></span></strong><br/><p><span data-ttu-id="130e9-181">用户豁免按用户管理，而不是按计算机进行管理。</span><span class="sxs-lookup"><span data-stu-id="130e9-181">User exemption is managed per user, not per computer.</span></span> <span data-ttu-id="130e9-182">如果多个用户登录到同一台计算机，并且一位用户没有豁免，计算机将被加密。</span><span class="sxs-lookup"><span data-stu-id="130e9-182">If multiple users log on to the same computer and one user is not exempt, the computer will be encrypted.</span></span></p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="130e9-183">固定驱动器策略定义</span><span class="sxs-lookup"><span data-stu-id="130e9-183">Fixed Drive policy definitions</span></span>


<span data-ttu-id="130e9-184">本部分介绍 MBAM 的固定驱动器策略定义，可在以下 GPO 节点找到：**计算机配置** \\ **管理模板** \\ **Windows 组件** \\ **MDOP MBAM （BitLocker Management）** 已  \\  **修复的驱动器**。</span><span class="sxs-lookup"><span data-stu-id="130e9-184">This section describes the Fixed Drive policy definitions for MBAM, which can be found at the following GPO node: **Computer Configuration**\\**Administrative Templates**\\**Windows Components**\\**MDOP MBAM (BitLocker Management)** \\ **Fixed Drive**.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="130e9-185">策略名称</span><span class="sxs-lookup"><span data-stu-id="130e9-185">Policy Name</span></span></th>
<th align="left"><span data-ttu-id="130e9-186">概述和建议的策略设置</span><span class="sxs-lookup"><span data-stu-id="130e9-186">Overview and Suggested Policy Setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="130e9-187">固定数据驱动器加密设置</span><span class="sxs-lookup"><span data-stu-id="130e9-187">Fixed data drive encryption settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="130e9-188">建议的配置： <strong> 启用 </strong> ， <strong> </strong> 如果需要加密操作系统卷，请选中 "启用自动解锁固定数据驱动器" 复选框。</span><span class="sxs-lookup"><span data-stu-id="130e9-188">Suggested Configuration: <strong>Enabled</strong>, and select the <strong>Enable auto-unlock fixed data drive</strong> check box if the operating system volume is required to be encrypted.</span></span></p>
<p><span data-ttu-id="130e9-189">通过此策略设置，你可以管理是否加密固定的驱动器。</span><span class="sxs-lookup"><span data-stu-id="130e9-189">This policy setting lets you manage whether or not to encrypt the fixed drives.</span></span></p>
<p><span data-ttu-id="130e9-190">如果启用此策略，请不要禁用 " <strong> 为固定数据驱动器配置密码使用密码" </strong> 策略。</span><span class="sxs-lookup"><span data-stu-id="130e9-190">When you enable this policy, do not disable the <strong>Configure use of password for fixed data drives</strong> policy.</span></span></p>
<p><span data-ttu-id="130e9-191">如果 <strong> 选中 "启用自动解锁固定数据驱动器" </strong> 复选框，则操作系统卷必须加密。</span><span class="sxs-lookup"><span data-stu-id="130e9-191">If the <strong>Enable auto-unlock fixed data drive</strong> check box is selected, the operating system volume must be encrypted.</span></span></p>
<p><span data-ttu-id="130e9-192">如果启用此策略设置，则用户需要将所有固定驱动器置于 BitLocker 保护下，这将加密驱动器。</span><span class="sxs-lookup"><span data-stu-id="130e9-192">If you enable this policy setting, users are required to put all fixed drives under BitLocker protection, which will encrypt the drives.</span></span></p>
<p><span data-ttu-id="130e9-193">如果不配置此策略，或者禁用此策略，则不需要用户在 BitLocker 保护下放置固定的驱动器。</span><span class="sxs-lookup"><span data-stu-id="130e9-193">If you do not configure this policy or if you disable this policy, users are not required to put fixed drives under BitLocker protection.</span></span></p>
<p><span data-ttu-id="130e9-194">如果禁用此策略，MBAM 代理将对任何已加密的固定驱动器进行解密。</span><span class="sxs-lookup"><span data-stu-id="130e9-194">If you disable this policy, the MBAM agent decrypts any encrypted fixed drives.</span></span></p>
<p><span data-ttu-id="130e9-195">如果不需要加密操作系统卷，请清除 " <strong> 启用自动解锁固定数据驱动器" </strong> 复选框。</span><span class="sxs-lookup"><span data-stu-id="130e9-195">If encrypting the operating system volume is not required, clear the <strong>Enable auto-unlock fixed data drive</strong> check box.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="130e9-196">拒绝不受 BitLocker 保护的固定驱动器的 "写入" 权限</span><span class="sxs-lookup"><span data-stu-id="130e9-196">Deny “write” permission to fixed drives that are not protected by BitLocker</span></span></p></td>
<td align="left"><p><span data-ttu-id="130e9-197">建议的配置： <strong> 未配置</span><span class="sxs-lookup"><span data-stu-id="130e9-197">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="130e9-198">此策略设置确定计算机上的固定驱动器是否需要 BitLocker 保护，以便它们可写。</span><span class="sxs-lookup"><span data-stu-id="130e9-198">This policy setting determines if BitLocker protection is required for fixed drives on a computer so that they are writable.</span></span> <span data-ttu-id="130e9-199">启用 BitLocker 时，将应用此策略设置。</span><span class="sxs-lookup"><span data-stu-id="130e9-199">This policy setting is applied when you turn on BitLocker.</span></span></p>
<p><span data-ttu-id="130e9-200">当未配置策略时，计算机上的所有固定驱动器都将以读/写权限挂载。</span><span class="sxs-lookup"><span data-stu-id="130e9-200">When the policy is not configured, all fixed drives on the computer are mounted with read/write permissions.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="130e9-201">允许从早期版本的 Windows 访问受 BitLocker 保护的固定驱动器</span><span class="sxs-lookup"><span data-stu-id="130e9-201">Allow access to BitLocker-protected fixed drives from earlier versions of Windows</span></span></p></td>
<td align="left"><p><span data-ttu-id="130e9-202">建议的配置： <strong> 未配置</span><span class="sxs-lookup"><span data-stu-id="130e9-202">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="130e9-203">启用此策略可解锁和查看在运行 Windows Server 2008、Windows Vista、Windows XP SP3 或 Windows XP SP2 的计算机上使用文件分配表（FAT）文件系统格式化的固定驱动器。</span><span class="sxs-lookup"><span data-stu-id="130e9-203">Enable this policy to unlock and view the fixed drives that are formatted with the file allocation table (FAT) file system on computers that are running Windows Server 2008, Windows Vista, Windows XP with SP3, or Windows XP with SP2.</span></span></p>
<p><span data-ttu-id="130e9-204">这些操作系统对受 BitLocker 保护的驱动器具有只读权限。</span><span class="sxs-lookup"><span data-stu-id="130e9-204">These operating systems have read-only permissions to BitLocker-protected drives.</span></span></p>
<p><span data-ttu-id="130e9-205">禁用策略时，无法解锁用 FAT 文件系统格式化的固定驱动器，并且无法在运行 Windows Server 2008、Windows Vista、Windows XP SP3 或 Windows XP SP2 的计算机上查看其内容。</span><span class="sxs-lookup"><span data-stu-id="130e9-205">When the policy is disabled, fixed drives formatted with the FAT file system cannot be unlocked and their content cannot be viewed on computers that are running Windows Server 2008, Windows Vista, Windows XP with SP3, or Windows XP with SP2.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="130e9-206">为固定驱动器配置密码的使用</span><span class="sxs-lookup"><span data-stu-id="130e9-206">Configure use of password for fixed drives</span></span></p></td>
<td align="left"><p><span data-ttu-id="130e9-207">建议的配置： <strong> 未配置</span><span class="sxs-lookup"><span data-stu-id="130e9-207">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="130e9-208">启用此策略以在固定驱动器上配置密码保护。</span><span class="sxs-lookup"><span data-stu-id="130e9-208">Enable this policy to configure password protection on fixed drives.</span></span></p>
<p><span data-ttu-id="130e9-209">当未配置策略时，将支持密码，默认设置不包括密码复杂性要求，并且只需要八个字符。</span><span class="sxs-lookup"><span data-stu-id="130e9-209">When the policy is not configured, passwords will be supported with the default settings, which do not include password complexity requirements and require only eight characters.</span></span></p>
<p><span data-ttu-id="130e9-210">若要获得更高的安全性，请启用此策略并选择 <strong> "需要密码才能修复固定数据驱动器 </strong> "，选择 <strong> "需要密码复杂性 </strong> "，然后设置所需的 <strong> 最小密码长度 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="130e9-210">For higher security, enable this policy and select <strong>Require password for fixed data drive</strong>, select <strong>Require password complexity</strong>, and set the desired <strong>minimum password length</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="130e9-211">选择如何恢复受 BitLocker 保护的固定驱动器</span><span class="sxs-lookup"><span data-stu-id="130e9-211">Choose how BitLocker-protected fixed drives can be recovered</span></span></p></td>
<td align="left"><p><span data-ttu-id="130e9-212">建议的配置： <strong> 未配置</span><span class="sxs-lookup"><span data-stu-id="130e9-212">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="130e9-213">将此策略配置为启用 BitLocker 数据恢复代理或将 BitLocker 恢复信息保存到 Active Directory 域服务（AD DS）。</span><span class="sxs-lookup"><span data-stu-id="130e9-213">Configure this policy to enable the BitLocker data recovery agent or to save BitLocker recovery information to Active Directory Domain Services (AD DS).</span></span></p>
<p><span data-ttu-id="130e9-214">如果未配置此策略，则允许 BitLocker 数据恢复代理，并且不会将恢复信息备份到 AD DS。</span><span class="sxs-lookup"><span data-stu-id="130e9-214">When this policy is not configured, the BitLocker data recovery agent is allowed, and recovery information is not backed up to AD DS.</span></span> <span data-ttu-id="130e9-215">MBAM 不需要将恢复信息备份到 AD DS。</span><span class="sxs-lookup"><span data-stu-id="130e9-215">MBAM does not require the recovery information to be backed up to AD DS.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="130e9-216">操作系统驱动器策略定义</span><span class="sxs-lookup"><span data-stu-id="130e9-216">Operating System Drive policy definitions</span></span>


<span data-ttu-id="130e9-217">本部分介绍 MBAM 的操作系统驱动器策略定义，可在以下 GPO 节点找到：**计算机配置** \\ **管理模板** \\ **Windows 组件** \\ **MDOP MBAM （BitLocker Management）**  \\  **操作系统驱动器**。</span><span class="sxs-lookup"><span data-stu-id="130e9-217">This section describes the Operating System Drive policy definitions for MBAM, found at the following GPO node: **Computer Configuration**\\**Administrative Templates**\\**Windows Components**\\**MDOP MBAM (BitLocker Management)** \\ **Operating System Drive**.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="130e9-218">策略名称</span><span class="sxs-lookup"><span data-stu-id="130e9-218">Policy Name</span></span></th>
<th align="left"><span data-ttu-id="130e9-219">概述和建议的策略设置</span><span class="sxs-lookup"><span data-stu-id="130e9-219">Overview and Suggested Policy Setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="130e9-220">操作系统驱动器加密设置</span><span class="sxs-lookup"><span data-stu-id="130e9-220">Operating system drive encryption settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="130e9-221">建议的配置： <strong> 已启用</span><span class="sxs-lookup"><span data-stu-id="130e9-221">Suggested configuration: <strong>Enabled</span></span></strong></p>
<p><span data-ttu-id="130e9-222">此策略设置确定操作系统驱动器是否将加密。</span><span class="sxs-lookup"><span data-stu-id="130e9-222">This policy setting determines if the operating system drive will be encrypted.</span></span></p>
<p><span data-ttu-id="130e9-223">配置此策略以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="130e9-223">Configure this policy to do the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="130e9-224">为操作系统驱动器强制执行 BitLocker 保护。</span><span class="sxs-lookup"><span data-stu-id="130e9-224">Enforce BitLocker protection for the operating system drive.</span></span></p></li>
<li><p><span data-ttu-id="130e9-225">将 "PIN 使用情况" 配置为使用受信任的平台模块（TPM） PIN 以实现操作系统保护。</span><span class="sxs-lookup"><span data-stu-id="130e9-225">Configure PIN usage to use a Trusted Platform Module (TPM) PIN for operating system protection.</span></span></p></li>
<li><p><span data-ttu-id="130e9-226">配置增强的启动 Pin 以允许字符（如大写字母和小写字母）和数字。</span><span class="sxs-lookup"><span data-stu-id="130e9-226">Configure enhanced startup PINs to permit characters such as uppercase and lowercase letters, and numbers.</span></span> <span data-ttu-id="130e9-227">MBAM 不支持将符号和空格用于增强的 Pin，即使 BitLocker 支持符号和空格也是如此。</span><span class="sxs-lookup"><span data-stu-id="130e9-227">MBAM does not support the use of symbols and spaces for enhanced PINs, even though BitLocker supports symbols and spaces.</span></span></p></li>
</ul>
<p><span data-ttu-id="130e9-228">如果启用此策略设置，则用户需要使用 BitLocker 保护操作系统驱动器。</span><span class="sxs-lookup"><span data-stu-id="130e9-228">If you enable this policy setting, users are required to secure the operating system drive by using BitLocker.</span></span></p>
<p><span data-ttu-id="130e9-229">如果未配置或禁用此设置，则不需要用户使用 BitLocker 保护操作系统驱动器。</span><span class="sxs-lookup"><span data-stu-id="130e9-229">If you do not configure or if you disable the setting, users are not required to secure the operating system drive by using BitLocker.</span></span></p>
<p><span data-ttu-id="130e9-230">如果禁用此策略，MBAM 代理将对操作系统卷进行解密（如果已加密）。</span><span class="sxs-lookup"><span data-stu-id="130e9-230">If you disable this policy, the MBAM agent decrypts the operating system volume if it is encrypted.</span></span></p>
<p><span data-ttu-id="130e9-231">如果启用此策略设置，则要求用户使用 BitLocker 保护保护操作系统，并且驱动器已加密。</span><span class="sxs-lookup"><span data-stu-id="130e9-231">When it is enabled, this policy setting requires users to secure the operating system by using BitLocker protection, and the drive is encrypted.</span></span> <span data-ttu-id="130e9-232">根据您的加密要求，您可以选择操作系统驱动器的保护方法。</span><span class="sxs-lookup"><span data-stu-id="130e9-232">Based on your encryption requirements, you may select the method of protection for the operating system drive.</span></span></p>
<p><span data-ttu-id="130e9-233">对于更高的安全要求，请使用 TPM + PIN，允许增强的 pin，并将最小 PIN 长度设置为八个字符。</span><span class="sxs-lookup"><span data-stu-id="130e9-233">For higher security requirements, use TPM + PIN, allow enhanced PINs, and set the minimum PIN length to eight characters.</span></span></p>
<p><span data-ttu-id="130e9-234">当启用 TPM + 引脚保护器的此策略时，可以考虑禁用 " <strong> 系统 </strong>  /  <strong> 电源管理 </strong>  /  <strong> 睡眠设置 </strong> " 下的以下策略：</span><span class="sxs-lookup"><span data-stu-id="130e9-234">When this policy is enabled with the TPM + PIN protector, you can consider disabling the following policies under <strong>System</strong> / <strong>Power Management</strong> / <strong>Sleep Settings</strong>:</span></span></p>
<ul>
<li><p><span data-ttu-id="130e9-235">睡眠（接通）时允许待机状态（S1-S3）</span><span class="sxs-lookup"><span data-stu-id="130e9-235">Allow Standby States (S1-S3) When Sleeping (Plugged In)</span></span></p></li>
<li><p><span data-ttu-id="130e9-236">睡眠时允许待机状态（S1-S3）（使用电池）</span><span class="sxs-lookup"><span data-stu-id="130e9-236">Allow Standby States (S1-S3) When Sleeping (On Battery)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="130e9-237">配置 TPM 平台验证配置文件</span><span class="sxs-lookup"><span data-stu-id="130e9-237">Configure TPM platform validation profile</span></span></p></td>
<td align="left"><p><span data-ttu-id="130e9-238">建议的配置： <strong> 未配置</span><span class="sxs-lookup"><span data-stu-id="130e9-238">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="130e9-239">此策略设置允许你配置计算机上的 TPM 安全硬件如何保护 BitLocker 加密密钥。</span><span class="sxs-lookup"><span data-stu-id="130e9-239">This policy setting lets you configure how the TPM security hardware on a computer secures the BitLocker encryption key.</span></span> <span data-ttu-id="130e9-240">如果计算机没有兼容的 TPM 或 BitLocker 已启用 TPM 保护，则此策略设置不适用。</span><span class="sxs-lookup"><span data-stu-id="130e9-240">This policy setting does not apply if the computer does not have a compatible TPM or if BitLocker already has TPM protection enabled.</span></span></p>
<p><span data-ttu-id="130e9-241">如果未配置此策略，TPM 将使用默认平台验证配置文件或由安装脚本指定的平台验证配置文件。</span><span class="sxs-lookup"><span data-stu-id="130e9-241">When this policy is not configured, the TPM uses the default platform validation profile or the platform validation profile specified by the setup script.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="130e9-242">选择如何恢复受 BitLocker 保护的操作系统驱动器</span><span class="sxs-lookup"><span data-stu-id="130e9-242">Choose how to recover BitLocker-protected operating system drives</span></span></p></td>
<td align="left"><p><span data-ttu-id="130e9-243">建议的配置： <strong> 未配置</span><span class="sxs-lookup"><span data-stu-id="130e9-243">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="130e9-244">将此策略配置为启用 BitLocker 数据恢复代理或将 BitLocker 恢复信息保存到 Active Directory 域服务（AD DS）。</span><span class="sxs-lookup"><span data-stu-id="130e9-244">Configure this policy to enable the BitLocker data recovery agent or to save BitLocker recovery information to Active Directory Domain Services (AD DS).</span></span></p>
<p><span data-ttu-id="130e9-245">如果未配置此策略，则允许数据恢复代理，并且不会将恢复信息备份到 AD DS。</span><span class="sxs-lookup"><span data-stu-id="130e9-245">When this policy is not configured, the data recovery agent is allowed, and the recovery information is not backed up to AD DS.</span></span></p>
<p><span data-ttu-id="130e9-246">MBAM 操作不需要将恢复信息备份到 AD DS。</span><span class="sxs-lookup"><span data-stu-id="130e9-246">MBAM operation does not require the recovery information to be backed up to AD DS.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="130e9-247">可移动驱动器策略定义</span><span class="sxs-lookup"><span data-stu-id="130e9-247">Removable Drive policy definitions</span></span>


<span data-ttu-id="130e9-248">本部分介绍了 MBAM 的可移动驱动器策略定义，可在以下 GPO 节点找到：**计算机配置** \\ **管理模板** \\ **Windows 组件** \\ **MDOP MBAM （BitLocker Management）**  \\  **可移动驱动器**。</span><span class="sxs-lookup"><span data-stu-id="130e9-248">This section describes the Removable Drive Policy definitions for MBAM, found at the following GPO node: **Computer Configuration**\\**Administrative Templates**\\**Windows Components**\\**MDOP MBAM (BitLocker Management)** \\ **Removable Drive**.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="130e9-249">策略名称</span><span class="sxs-lookup"><span data-stu-id="130e9-249">Policy Name</span></span></th>
<th align="left"><span data-ttu-id="130e9-250">概述和建议的策略设置</span><span class="sxs-lookup"><span data-stu-id="130e9-250">Overview and Suggested Policy Setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="130e9-251">控制在可移动驱动器上使用 BitLocker</span><span class="sxs-lookup"><span data-stu-id="130e9-251">Control the use of BitLocker on removable drives</span></span></p></td>
<td align="left"><p><span data-ttu-id="130e9-252">建议的配置： <strong> 已启用</span><span class="sxs-lookup"><span data-stu-id="130e9-252">Suggested configuration: <strong>Enabled</span></span></strong></p>
<p><span data-ttu-id="130e9-253">此策略控制对可移动数据驱动器使用 BitLocker。</span><span class="sxs-lookup"><span data-stu-id="130e9-253">This policy controls the use of BitLocker on removable data drives.</span></span></p>
<p><span data-ttu-id="130e9-254">启用 " <strong> 允许用户对可移动数据驱动器应用 bitlocker 保护" </strong> 选项，以允许用户在可移动数据驱动器上运行 bitlocker 设置向导。</span><span class="sxs-lookup"><span data-stu-id="130e9-254">Enable the <strong>Allow users to apply BitLocker protection on removable data drives</strong> option, to allow users to run the BitLocker setup wizard on a removable data drive.</span></span></p>
<p><span data-ttu-id="130e9-255">启用 " <strong> 允许用户暂停和解密可移动数据驱动器上的 bitlocker" </strong> 选项，允许用户从驱动器中删除 bitlocker 驱动器加密，或在执行维护时暂停加密。</span><span class="sxs-lookup"><span data-stu-id="130e9-255">Enable the <strong>Allow users to suspend and decrypt BitLocker on removable data drives</strong> option to allow users to remove BitLocker drive encryption from the drive or to suspend the encryption while maintenance is performed.</span></span></p>
<p><span data-ttu-id="130e9-256">如果已选中此策略并 <strong> 选中 "允许用户对可移动数据驱动器应用 BitLocker 保护" </strong> 选项，则 MBAM 客户端会将可移动驱动器的恢复信息保存到 MBAM 密钥恢复服务器，并允许用户在密码丢失时恢复驱动器。</span><span class="sxs-lookup"><span data-stu-id="130e9-256">When this policy is enabled and the <strong>Allow users to apply BitLocker protection on removable data drives</strong> option is selected, the MBAM Client saves the recovery information about removable drives to the MBAM key recovery server, and it allows users to recover the drive if the password is lost.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="130e9-257">拒绝不受 BitLocker 保护的可移动驱动器的 "写入" 权限</span><span class="sxs-lookup"><span data-stu-id="130e9-257">Deny the “write” permissions to removable drives that are not protected by BitLocker</span></span></p></td>
<td align="left"><p><span data-ttu-id="130e9-258">建议的配置： <strong> 未配置</span><span class="sxs-lookup"><span data-stu-id="130e9-258">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="130e9-259">启用此策略以允许对 BitLocker 受保护的驱动器的仅写权限。</span><span class="sxs-lookup"><span data-stu-id="130e9-259">Enable this policy to allow write-only permissions to BitLocker protected drives.</span></span></p>
<p><span data-ttu-id="130e9-260">如果启用此策略，则计算机上的所有可移动数据驱动器都需要加密才能允许写入权限。</span><span class="sxs-lookup"><span data-stu-id="130e9-260">When this policy is enabled, all removable data drives on the computer require encryption before write permissions are allowed.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="130e9-261">允许从早期版本的 Windows 访问受 BitLocker 保护的可移动驱动器</span><span class="sxs-lookup"><span data-stu-id="130e9-261">Allow access to BitLocker-protected removable drives from earlier versions of Windows</span></span></p></td>
<td align="left"><p><span data-ttu-id="130e9-262">建议的配置： <strong> 未配置</span><span class="sxs-lookup"><span data-stu-id="130e9-262">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="130e9-263">启用此策略可解锁和查看在运行 Windows Server 2008、Windows Vista、Windows XP SP3 或 Windows XP SP2 的计算机上使用（FAT）文件系统格式化的固定驱动器。</span><span class="sxs-lookup"><span data-stu-id="130e9-263">Enable this policy to unlock and view the fixed drives that are formatted with the (FAT) file system on computers that are running Windows Server 2008, Windows Vista, Windows XP with SP3, or Windows XP with SP2.</span></span></p>
<p><span data-ttu-id="130e9-264">这些操作系统对受 BitLocker 保护的驱动器具有只读权限。</span><span class="sxs-lookup"><span data-stu-id="130e9-264">These operating systems have read-only permissions to BitLocker-protected drives.</span></span></p>
<p><span data-ttu-id="130e9-265">禁用策略时，无法解锁用 FAT 文件系统格式化的可移动驱动器，并且无法在运行 Windows Server 2008、Windows Vista、Windows XP SP3 或 Windows XP SP2 的计算机上查看其内容。</span><span class="sxs-lookup"><span data-stu-id="130e9-265">When the policy is disabled, removable drives formatted with the FAT file system cannot be unlocked and their content cannot be viewed on computers that are running Windows Server 2008, Windows Vista, Windows XP with SP3, or Windows XP with SP2.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="130e9-266">为可移动数据驱动器配置密码的使用</span><span class="sxs-lookup"><span data-stu-id="130e9-266">Configure the use of password for removable data drives</span></span></p></td>
<td align="left"><p><span data-ttu-id="130e9-267">建议的配置： <strong> 未配置</span><span class="sxs-lookup"><span data-stu-id="130e9-267">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="130e9-268">启用此策略以在可移动数据驱动器上配置密码保护。</span><span class="sxs-lookup"><span data-stu-id="130e9-268">Enable this policy to configure password protection on removable data drives.</span></span></p>
<p><span data-ttu-id="130e9-269">如果未配置此策略，则密码支持的默认设置包括密码复杂性要求，并且只需要八个字符。</span><span class="sxs-lookup"><span data-stu-id="130e9-269">When this policy is not configured, passwords are supported with the default settings, which do not include password complexity requirements and require only eight characters.</span></span></p>
<p><span data-ttu-id="130e9-270">为了提高安全性，你可以启用此策略，并选择 <strong> "需要密码以使用可移动数据驱动器 </strong> "，选择 <strong> "需要密码复杂性 </strong> "，然后设置首选的 <strong> 最小密码长度 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="130e9-270">For increased security, you can enable this policy and select <strong>Require password for removable data drive</strong>, select <strong>Require password complexity</strong>, and then set the preferred <strong>minimum password length</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="130e9-271">选择可以如何恢复受 BitLocker 保护的可移动驱动器</span><span class="sxs-lookup"><span data-stu-id="130e9-271">Choose how BitLocker-protected removable drives can be recovered</span></span></p></td>
<td align="left"><p><span data-ttu-id="130e9-272">建议的配置： <strong> 未配置</span><span class="sxs-lookup"><span data-stu-id="130e9-272">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="130e9-273">你可以将此策略配置为启用 BitLocker 数据恢复代理或将 BitLocker 恢复信息保存到 Active Directory 域服务（AD DS）。</span><span class="sxs-lookup"><span data-stu-id="130e9-273">You can configure this policy to enable the BitLocker data recovery agent or to save BitLocker recovery information to Active Directory Domain Services (AD DS).</span></span></p>
<p><span data-ttu-id="130e9-274">如果策略设置为 <strong> "未配置" </strong> ，则允许数据恢复代理，并且不会将恢复信息备份到 AD DS。</span><span class="sxs-lookup"><span data-stu-id="130e9-274">When the policy is set to <strong>Not Configured</strong>, the data recovery agent is allowed and recovery information is not backed up to AD DS.</span></span></p>
<p><span data-ttu-id="130e9-275">MBAM 操作不需要将恢复信息备份到 AD DS。</span><span class="sxs-lookup"><span data-stu-id="130e9-275">MBAM operation does not require the recovery information to be backed up to AD DS.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="130e9-276">相关主题</span><span class="sxs-lookup"><span data-stu-id="130e9-276">Related topics</span></span>


[<span data-ttu-id="130e9-277">针对 MBAM 1.0 准备环境</span><span class="sxs-lookup"><span data-stu-id="130e9-277">Preparing your Environment for MBAM 1.0</span></span>](preparing-your-environment-for-mbam-10.md)









