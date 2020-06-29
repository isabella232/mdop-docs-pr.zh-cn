---
title: 规划 MBAM 2.5 组策略要求
description: 规划 MBAM 2.5 组策略要求
author: dansimp
ms.assetid: 82d545dc-3fbf-4b46-b62f-47fe178a7c44
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 4beeb9f88f16e7d48d145861c398a90fa29f3491
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803434"
---
# <span data-ttu-id="1ba40-103">规划 MBAM 2.5 组策略要求</span><span class="sxs-lookup"><span data-stu-id="1ba40-103">Planning for MBAM 2.5 Group Policy Requirements</span></span>


<span data-ttu-id="1ba40-104">使用以下信息确定可用于管理企业中的 Microsoft BitLocker 管理和监视（MBAM）客户端计算机的 BitLocker 保护器的类型。</span><span class="sxs-lookup"><span data-stu-id="1ba40-104">Use the following information to determine the types of BitLocker protectors that you can use to manage the Microsoft BitLocker Administration and Monitoring (MBAM) client computers in your enterprise.</span></span>

## <span data-ttu-id="1ba40-105">MBAM 支持的 BitLocker 保护器的类型</span><span class="sxs-lookup"><span data-stu-id="1ba40-105">Types of BitLocker protectors that MBAM supports</span></span>


<span data-ttu-id="1ba40-106">MBAM 支持以下类型的 BitLocker 保护器。</span><span class="sxs-lookup"><span data-stu-id="1ba40-106">MBAM supports the following types of BitLocker protectors.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="1ba40-107">驱动器或卷的类型</span><span class="sxs-lookup"><span data-stu-id="1ba40-107">Type of drive or volume</span></span></th>
<th align="left"><span data-ttu-id="1ba40-108">支持的 BitLocker 保护器</span><span class="sxs-lookup"><span data-stu-id="1ba40-108">Supported BitLocker protectors</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1ba40-109">操作系统卷</span><span class="sxs-lookup"><span data-stu-id="1ba40-109">Operating system volumes</span></span></p></td>
<td align="left"><ul>
<li><p><strong><span data-ttu-id="1ba40-110">受信任的平台模块 (TPM)</span><span class="sxs-lookup"><span data-stu-id="1ba40-110">Trusted Platform Module (TPM)</span></span></strong></p></li>
<li><p><strong><span data-ttu-id="1ba40-111">TPM + PIN</span><span class="sxs-lookup"><span data-stu-id="1ba40-111">TPM + PIN</span></span></strong></p></li>
<li><p><strong><span data-ttu-id="1ba40-112">TPM + USB 密钥 </strong> -仅当操作系统卷在安装 MBAM 之前已加密时才受支持</span><span class="sxs-lookup"><span data-stu-id="1ba40-112">TPM + USB key</strong> – supported only when the operating system volume is encrypted before MBAM is installed</span></span></p></li>
<li><p><strong><span data-ttu-id="1ba40-113"></strong> - 仅在安装 MBAM 之前加密操作系统卷时支持 TPM + 引脚 + USB 密钥</span><span class="sxs-lookup"><span data-stu-id="1ba40-113">TPM + PIN + USB key</strong> - supported only when the operating system volume is encrypted before MBAM is installed</span></span></p></li>
<li><p><strong><span data-ttu-id="1ba40-114"></strong> - 仅适用于 Windows To Go 设备、固定数据驱动器、windows 8、windows 8.1 和没有 TPM 的 windows 10 设备支持的密码</span><span class="sxs-lookup"><span data-stu-id="1ba40-114">Password</strong> - supported only for Windows To Go devices, fixed data drives, and Windows 8, Windows 8.1, and Windows 10 devices that do not have a TPM</span></span></p></li>
<li><p><strong><span data-ttu-id="1ba40-115"></strong> - 在卷加密过程中自动应用的数字密码，不需要在 Windows 7 上的 FIPS 模式下进行配置</span><span class="sxs-lookup"><span data-stu-id="1ba40-115">Numerical password</strong> - applied automatically as part of volume encryption and does not need to be configured except in FIPS mode on Windows 7</span></span></p></li>
<li><p><strong><span data-ttu-id="1ba40-116">数据恢复代理（DRA）</span><span class="sxs-lookup"><span data-stu-id="1ba40-116">Data recovery agent (DRA)</span></span></strong></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="1ba40-117">固定数据驱动器</span><span class="sxs-lookup"><span data-stu-id="1ba40-117">Fixed data drives</span></span></p></td>
<td align="left"><ul>
<li><p><strong><span data-ttu-id="1ba40-118">密码</span><span class="sxs-lookup"><span data-stu-id="1ba40-118">Password</span></span></strong></p></li>
<li><p><strong><span data-ttu-id="1ba40-119">自动解锁</span><span class="sxs-lookup"><span data-stu-id="1ba40-119">Auto-unlock</span></span></strong></p></li>
<li><p><strong><span data-ttu-id="1ba40-120"></strong> - 在卷加密过程中自动应用的数字密码，不需要在 Windows 7 上的 FIPS 模式下进行配置</span><span class="sxs-lookup"><span data-stu-id="1ba40-120">Numerical password</strong> - applied automatically as part of volume encryption and does not need to be configured except in FIPS mode on Windows 7</span></span></p></li>
<li><p><strong><span data-ttu-id="1ba40-121">数据恢复代理（DRA）</span><span class="sxs-lookup"><span data-stu-id="1ba40-121">Data recovery agent (DRA)</span></span></strong></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1ba40-122">可移动驱动器</span><span class="sxs-lookup"><span data-stu-id="1ba40-122">Removable drives</span></span></p></td>
<td align="left"><ul>
<li><p><strong><span data-ttu-id="1ba40-123">密码</span><span class="sxs-lookup"><span data-stu-id="1ba40-123">Password</span></span></strong></p></li>
<li><p><strong><span data-ttu-id="1ba40-124">自动解锁</span><span class="sxs-lookup"><span data-stu-id="1ba40-124">Auto-unlock</span></span></strong></p></li>
<li><p><strong><span data-ttu-id="1ba40-125"></strong> - 作为卷加密的一部分自动应用的数字密码，不需要进行配置</span><span class="sxs-lookup"><span data-stu-id="1ba40-125">Numerical password</strong> - applied automatically as part of volume encryption and does not need to be configured</span></span></p></li>
<li><p><strong><span data-ttu-id="1ba40-126">数据恢复代理（DRA）</span><span class="sxs-lookup"><span data-stu-id="1ba40-126">Data recovery agent (DRA)</span></span></strong></p></li>
</ul></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="1ba40-127">支持已使用的空间加密 BitLocker 策略</span><span class="sxs-lookup"><span data-stu-id="1ba40-127">Support for the Used Space Encryption BitLocker policy</span></span>

<span data-ttu-id="1ba40-128">在 MBAM 2.5 SP1 中，如果通过 BitLocker 组策略启用已使用的空间加密，MBAM 客户端将接受它。</span><span class="sxs-lookup"><span data-stu-id="1ba40-128">In MBAM 2.5 SP1, if you enable Used Space Encryption via BitLocker Group policy, the MBAM Client honors it.</span></span>

<span data-ttu-id="1ba40-129">此组策略设置称为 **"在操作系统驱动器上强制执行驱动器加密类型"** ，位于以下 GPO 节点中： "**计算机配置** &gt; **管理模板**" &gt; **Windows 组件**" &gt; **BitLocker 驱动器加密** &gt; **操作系统驱动器**"。</span><span class="sxs-lookup"><span data-stu-id="1ba40-129">This Group Policy setting is called **Enforce drive encryption type on operating system drives** and is located in the following GPO node: **Computer Configuration** &gt; **Administrative Templates** &gt; **Windows Components** &gt; **BitLocker Drive Encryption** &gt; **Operating System Drives**.</span></span> <span data-ttu-id="1ba40-130">如果启用此策略并选择 "**仅限已用空间" 加密**的加密类型，则 MBAM 将接受该策略，并且 BitLocker 将仅加密卷上使用的磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="1ba40-130">If you enable this policy and select the encryption type as **Used Space Only encryption**, MBAM will honor the policy and BitLocker will only encrypt disk space that is used on the volume.</span></span>

## <span data-ttu-id="1ba40-131">如何获取 MBAM 组策略模板并编辑设置</span><span class="sxs-lookup"><span data-stu-id="1ba40-131">How to get the MBAM Group Policy Templates and edit the settings</span></span>


<span data-ttu-id="1ba40-132">准备好配置所需的 MBAM 组策略设置时，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="1ba40-132">When you are ready to configure the MBAM Group Policy settings you want, do the following:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="1ba40-133">后续步骤</span><span class="sxs-lookup"><span data-stu-id="1ba40-133">Steps to follow</span></span></th>
<th align="left"><span data-ttu-id="1ba40-134">获取说明的位置</span><span class="sxs-lookup"><span data-stu-id="1ba40-134">Where to get instructions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1ba40-135">将 MBAM 组策略模板从 <a href="https://go.microsoft.com/fwlink/p/?LinkId=393941" data-raw-source="[How to Get MDOP Group Policy (.admx) Templates](https://go.microsoft.com/fwlink/p/?LinkId=393941)"> 如何获取 MDOP 组策略（admx）模板中 </a> ，并将其安装在能够运行组策略管理控制台（GPMC）或高级组策略管理（AGPM）的计算机上。</span><span class="sxs-lookup"><span data-stu-id="1ba40-135">Copy the MBAM Group Policy Templates from <a href="https://go.microsoft.com/fwlink/p/?LinkId=393941" data-raw-source="[How to Get MDOP Group Policy (.admx) Templates](https://go.microsoft.com/fwlink/p/?LinkId=393941)">How to Get MDOP Group Policy (.admx) Templates</a> and install them on a computer that is capable of running the Group Policy Management Console (GPMC) or Advanced Group Policy Management (AGPM).</span></span></p></td>
<td align="left"><p><a href="copying-the-mbam-25-group-policy-templates.md" data-raw-source="[Copying the MBAM 2.5 Group Policy Templates](copying-the-mbam-25-group-policy-templates.md)"><span data-ttu-id="1ba40-136">复制 MBAM 2.5 组策略模板</span><span class="sxs-lookup"><span data-stu-id="1ba40-136">Copying the MBAM 2.5 Group Policy Templates</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="1ba40-137">配置要在企业中使用的组策略设置。</span><span class="sxs-lookup"><span data-stu-id="1ba40-137">Configure the Group Policy settings that you want to use in your enterprise.</span></span></p></td>
<td align="left"><p><a href="editing-the-mbam-25-group-policy-settings.md" data-raw-source="[Editing the MBAM 2.5 Group Policy Settings](editing-the-mbam-25-group-policy-settings.md)"><span data-ttu-id="1ba40-138">编辑 MBAM 2.5 组策略设置</span><span class="sxs-lookup"><span data-stu-id="1ba40-138">Editing the MBAM 2.5 Group Policy Settings</span></span></a></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="1ba40-139">MBAM 组策略设置的说明</span><span class="sxs-lookup"><span data-stu-id="1ba40-139">Descriptions of the MBAM Group Policy settings</span></span>


<span data-ttu-id="1ba40-140">**MDOP MBAM （BitLocker Management）** GPO 节点包含四个全局策略设置和四个子 GPO 节点：**客户端管理**、**固定驱动器**、**操作系统驱动器**和**可移动驱动器**。</span><span class="sxs-lookup"><span data-stu-id="1ba40-140">The **MDOP MBAM (BitLocker Management)** GPO node contains four global policy settings and four child GPO nodes: **Client Management**, **Fixed Drive**, **Operating System Drive**, and **Removable Drive**.</span></span> <span data-ttu-id="1ba40-141">以下部分介绍和建议 MBAM 组策略设置的设置。</span><span class="sxs-lookup"><span data-stu-id="1ba40-141">The following sections describe and suggest settings for the MBAM Group Policy settings.</span></span>

**<span data-ttu-id="1ba40-142">重要提示</span><span class="sxs-lookup"><span data-stu-id="1ba40-142">Important</span></span>**  
<span data-ttu-id="1ba40-143">请勿更改**BitLocker 驱动器加密**节点中的组策略设置，否则 MBAM 将无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="1ba40-143">Do not change the Group Policy settings in the **BitLocker Drive Encryption** node, or MBAM will not work correctly.</span></span> <span data-ttu-id="1ba40-144">当配置**MDOP MBAM （BitLocker Management）** 节点中的设置时，MBAM 会自动配置此节点中的设置。</span><span class="sxs-lookup"><span data-stu-id="1ba40-144">MBAM automatically configures the settings in this node for you when you configure the settings in the **MDOP MBAM (BitLocker Management)** node.</span></span>



### <span data-ttu-id="1ba40-145">全局组策略定义</span><span class="sxs-lookup"><span data-stu-id="1ba40-145">Global Group Policy definitions</span></span>

<span data-ttu-id="1ba40-146">本部分介绍了以下 GPO 节点 MBAM 全局组策略定义：**计算机配置** &gt; **策略** &gt; **管理模板** &gt; **Windows 组件** &gt; **MDOP MBAM （BitLocker Management）**。</span><span class="sxs-lookup"><span data-stu-id="1ba40-146">This section describes MBAM Global Group Policy definitions at the following GPO node: **Computer Configuration** &gt; **Policies** &gt; **Administrative Templates** &gt; **Windows Components** &gt; **MDOP MBAM (BitLocker Management)**.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="1ba40-147">策略名称</span><span class="sxs-lookup"><span data-stu-id="1ba40-147">Policy name</span></span></th>
<th align="left"><span data-ttu-id="1ba40-148">概述和建议的组策略设置</span><span class="sxs-lookup"><span data-stu-id="1ba40-148">Overview and suggested Group Policy settings</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1ba40-149">选择驱动器加密方法和密码强度</span><span class="sxs-lookup"><span data-stu-id="1ba40-149">Choose drive encryption method and cipher strength</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ba40-150">建议的配置： <strong> 已启用</span><span class="sxs-lookup"><span data-stu-id="1ba40-150">Suggested configuration: <strong>Enabled</span></span></strong></p>
<p><span data-ttu-id="1ba40-151">将此策略配置为使用特定加密方法和密码强度。</span><span class="sxs-lookup"><span data-stu-id="1ba40-151">Configure this policy to use a specific encryption method and cipher strength.</span></span></p>
<p><span data-ttu-id="1ba40-152">如果未配置此策略，BitLocker 将使用默认加密方法：使用扩散器的 AES 128 位。</span><span class="sxs-lookup"><span data-stu-id="1ba40-152">When this policy is not configured, BitLocker uses the default encryption method: AES 128-bit with Diffuser.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="1ba40-153">注意</span><span class="sxs-lookup"><span data-stu-id="1ba40-153">Note</span></span></strong><br/><p><span data-ttu-id="1ba40-154">BitLocker 计算机合规性报告的问题使其显示 &quot; &quot; 密码强度的 "未知"，即使你使用的是默认值也是如此。</span><span class="sxs-lookup"><span data-stu-id="1ba40-154">An issue with the BitLocker Computer Compliance report causes it to display &quot;unknown&quot; for the cipher strength, even if you are using the default value.</span></span> <span data-ttu-id="1ba40-155">若要解决此问题，请确保启用此设置并为密码强度设置一个值。</span><span class="sxs-lookup"><span data-stu-id="1ba40-155">To work around this issue, make sure you enable this setting and set a value for cipher strength.</span></span></p>
</div>
<div>

</div>
<ul>
<li><p><span data-ttu-id="1ba40-156">带有扩散器的 AES 128 位-仅适用于 Windows 7</span><span class="sxs-lookup"><span data-stu-id="1ba40-156">AES 128-bit with Diffuser – for Windows 7 only</span></span></p></li>
<li><p><span data-ttu-id="1ba40-157">适用于 Windows 8、Windows 8.1 和 Windows 10 的 AES 128</span><span class="sxs-lookup"><span data-stu-id="1ba40-157">AES 128 for Windows 8, Windows 8.1, and Windows 10</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="1ba40-158">在重启时防止内存覆盖</span><span class="sxs-lookup"><span data-stu-id="1ba40-158">Prevent memory overwrite on restart</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ba40-159">建议的配置： <strong> 未配置</span><span class="sxs-lookup"><span data-stu-id="1ba40-159">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="1ba40-160">配置此策略可提高重启性能，而无需在重新启动时覆盖内存中的 BitLocker 机密。</span><span class="sxs-lookup"><span data-stu-id="1ba40-160">Configure this policy to improve restart performance without overwriting BitLocker secrets in memory on restart.</span></span></p>
<p><span data-ttu-id="1ba40-161">如果未配置此策略，当计算机重新启动时，将从内存中删除 BitLocker 机密。</span><span class="sxs-lookup"><span data-stu-id="1ba40-161">When this policy is not configured, BitLocker secrets are removed from memory when the computer restarts.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1ba40-162">验证智能卡证书使用规则</span><span class="sxs-lookup"><span data-stu-id="1ba40-162">Validate smart card certificate usage rule</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ba40-163">建议的配置： <strong> 未配置</span><span class="sxs-lookup"><span data-stu-id="1ba40-163">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="1ba40-164">将此策略配置为使用基于智能卡证书的 BitLocker 保护。</span><span class="sxs-lookup"><span data-stu-id="1ba40-164">Configure this policy to use smartcard certificate-based BitLocker protection.</span></span></p>
<p><span data-ttu-id="1ba40-165">如果未配置此策略，则使用默认对象标识符1.3.6.1.4.1.311.67.1.1 指定证书。</span><span class="sxs-lookup"><span data-stu-id="1ba40-165">When this policy is not configured, the default object identifier 1.3.6.1.4.1.311.67.1.1 is used to specify a certificate.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="1ba40-166">为你的组织提供唯一标识符</span><span class="sxs-lookup"><span data-stu-id="1ba40-166">Provide the unique identifiers for your organization</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ba40-167">建议的配置： <strong> 未配置</span><span class="sxs-lookup"><span data-stu-id="1ba40-167">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="1ba40-168">将此策略配置为使用基于证书的数据恢复代理或 BitLocker To Go 阅读器。</span><span class="sxs-lookup"><span data-stu-id="1ba40-168">Configure this policy to use a certificate-based data recovery agent or the BitLocker To Go reader.</span></span></p>
<p><span data-ttu-id="1ba40-169">如果未配置此策略，则 <strong> </strong> 不会使用 "标识" 字段。</span><span class="sxs-lookup"><span data-stu-id="1ba40-169">When this policy is not configured, the <strong>Identification</strong> field is not used.</span></span></p>
<p><span data-ttu-id="1ba40-170">如果您的公司需要更高的安全测量，则可以配置 <strong> 标识 </strong> 字段以确保所有 USB 设备都具有此字段集，并且它们与此组策略设置对齐。</span><span class="sxs-lookup"><span data-stu-id="1ba40-170">If your company requires higher security measurements, you can configure the <strong>Identification</strong> field to make sure that all USB devices have this field set and that they are aligned with this Group Policy setting.</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="1ba40-171">客户端管理组策略定义</span><span class="sxs-lookup"><span data-stu-id="1ba40-171">Client Management Group Policy definitions</span></span>

<span data-ttu-id="1ba40-172">本部分介绍下列 GPO 节点的 MBAM 的客户端管理策略定义：**计算机配置** &gt; **策略** &gt; **管理模板** &gt; **Windows 组件** &gt; **MDOP MBAM （BitLocker Management）** &gt; **客户端管理**。</span><span class="sxs-lookup"><span data-stu-id="1ba40-172">This section describes Client Management policy definitions for MBAM at the following GPO node: **Computer Configuration** &gt; **Policies** &gt;**Administrative Templates** &gt; **Windows Components** &gt; **MDOP MBAM (BitLocker Management)** &gt; **Client Management**.</span></span>

<span data-ttu-id="1ba40-173">你可以为独立和 System Center Configuration Manager 集成拓扑设置相同的组策略设置，但有一种例外：禁用配置**MBAM 服务 &gt; MBAM Status reporting service 终结点**设置，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="1ba40-173">You can set the same Group Policy settings for the Stand-alone and System Center Configuration Manager Integration topologies, with one exception: Disable the **Configure MBAM Services &gt; MBAM Status reporting service endpoint** setting if you are using the Configuration Manager Integration topology, as indicated in the following table.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="1ba40-174">策略名称</span><span class="sxs-lookup"><span data-stu-id="1ba40-174">Policy name</span></span></th>
<th align="left"><span data-ttu-id="1ba40-175">概述和建议的组策略设置</span><span class="sxs-lookup"><span data-stu-id="1ba40-175">Overview and suggested Group Policy settings</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1ba40-176">配置 MBAM 服务</span><span class="sxs-lookup"><span data-stu-id="1ba40-176">Configure MBAM Services</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ba40-177">建议的配置： <strong> 已启用</span><span class="sxs-lookup"><span data-stu-id="1ba40-177">Suggested configuration: <strong>Enabled</span></span></strong></p>
<ul>
<li><p><strong><span data-ttu-id="1ba40-178">MBAM 恢复和硬件服务终结点 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="1ba40-178">MBAM Recovery and Hardware service endpoint</strong>.</span></span> <span data-ttu-id="1ba40-179">使用此设置启用 MBAM 客户端 BitLocker 加密管理。</span><span class="sxs-lookup"><span data-stu-id="1ba40-179">Use this setting to enable MBAM Client BitLocker encryption management.</span></span> <span data-ttu-id="1ba40-180">输入类似于以下示例的终结点位置： <strong> http （s）：// </strong><em> &lt; MBAM 管理和监视服务器名称 &gt; </em><strong> ： </strong><em> &lt; web 服务绑定到/MBAMRecoveryAndHardwareService/CoreService.svc 的端口 &gt; </em><strong> </strong> 。</span><span class="sxs-lookup"><span data-stu-id="1ba40-180">Enter an endpoint location that is similar to the following example: <strong>http(s)://</strong><em>&lt;MBAM Administration and Monitoring Server Name&gt;</em><strong>:</strong><em>&lt;the port the web service is bound to&gt;</em><strong>/MBAMRecoveryAndHardwareService/CoreService.svc</strong>.</span></span></p></li>
<li><p><strong><span data-ttu-id="1ba40-181">选择要存储的 BitLocker 恢复信息 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="1ba40-181">Select BitLocker recovery information to store</strong>.</span></span> <span data-ttu-id="1ba40-182">此策略设置允许你配置密钥恢复服务以备份 BitLocker 恢复信息。</span><span class="sxs-lookup"><span data-stu-id="1ba40-182">This policy setting lets you configure the key recovery service to back up BitLocker recovery information.</span></span> <span data-ttu-id="1ba40-183">它还允许你配置用于收集报表的状态报告服务。</span><span class="sxs-lookup"><span data-stu-id="1ba40-183">It also lets you configure a status reporting service for collecting reports.</span></span> <span data-ttu-id="1ba40-184">该策略提供一种管理方法来恢复由 BitLocker 加密的数据，以防止因缺少密钥信息而导致数据丢失。</span><span class="sxs-lookup"><span data-stu-id="1ba40-184">The policy provides an administrative method of recovering data encrypted by BitLocker to prevent data loss due to the lack of key information.</span></span> <span data-ttu-id="1ba40-185">"状态报告" 和 "密钥恢复" 活动将自动并以静默方式发送到配置的报表服务器位置。</span><span class="sxs-lookup"><span data-stu-id="1ba40-185">The status report and key recovery activity are automatically and silently sent to the configured report server location.</span></span></p>
<p><span data-ttu-id="1ba40-186">如果未配置或禁用此策略设置，则不会保存密钥恢复信息，并且不会向服务器报告状态报告和密钥恢复活动。</span><span class="sxs-lookup"><span data-stu-id="1ba40-186">If you do not configure this policy setting or if you disable it, the key recovery information is not saved, and the status report and key recovery activity are not reported to the server.</span></span> <span data-ttu-id="1ba40-187">当此设置设置为 <strong> 恢复密码和密钥包时 </strong> ，将自动将恢复密码和密钥数据包备份到配置的密钥恢复服务器位置。</span><span class="sxs-lookup"><span data-stu-id="1ba40-187">When this setting is set to <strong>Recovery Password and key package</strong>, the recovery password and key package are automatically and silently backed up to the configured key recovery server location.</span></span></p></li>
<li><p><strong><span data-ttu-id="1ba40-188">以分钟为单位输入客户端检查状态频率 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="1ba40-188">Enter client checking status frequency in minutes</strong>.</span></span> <span data-ttu-id="1ba40-189">此策略设置管理客户端计算机上的客户端检查 BitLocker 保护策略和状态的频率。</span><span class="sxs-lookup"><span data-stu-id="1ba40-189">This policy setting manages how frequently the client checks the BitLocker protection policies and status on the client computer.</span></span> <span data-ttu-id="1ba40-190">此策略还管理将客户端合规性状态保存到服务器的频率。</span><span class="sxs-lookup"><span data-stu-id="1ba40-190">This policy also manages how frequently the client compliance status is saved to the server.</span></span> <span data-ttu-id="1ba40-191">客户端在客户端计算机上检查 BitLocker 保护策略和状态，还将按配置的频率备份客户端恢复密钥。</span><span class="sxs-lookup"><span data-stu-id="1ba40-191">The client checks the BitLocker protection policies and status on the client computer and also backs up the client recovery key at the configured frequency.</span></span></p>
<p><span data-ttu-id="1ba40-192">根据你的公司针对检查计算机合规性状态和备份客户端恢复密钥的频率设置的要求，设置此频率。</span><span class="sxs-lookup"><span data-stu-id="1ba40-192">Set this frequency based on the requirement set by your company on how frequently to check the compliance status of the computer and how frequently to back up the client recovery key.</span></span></p></li>
<li><p><strong><span data-ttu-id="1ba40-193">MBAM 状态报告服务终结点：</span><span class="sxs-lookup"><span data-stu-id="1ba40-193">MBAM Status reporting service endpoint:</span></span></strong></p>
<p><strong><span data-ttu-id="1ba40-194">对于独立拓扑中的 MBAM </strong> ：必须配置此设置以启用 MBAM 客户端 BitLocker 加密管理。</span><span class="sxs-lookup"><span data-stu-id="1ba40-194">For MBAM in a Stand-alone topology</strong>: You must configure this setting to enable MBAM Client BitLocker encryption management.</span></span></p>
<p><span data-ttu-id="1ba40-195">输入类似于以下示例的终结点位置：</span><span class="sxs-lookup"><span data-stu-id="1ba40-195">Enter an endpoint location that is similar to the following example:</span></span></p>
<p><strong><span data-ttu-id="1ba40-196">http （s）：// </strong><em> &lt; MBAM 管理和监视服务器名称 &gt; </em><strong> ： </strong><em> &lt; web 服务绑定到的端口 &gt; </em><strong> /MBAMComplianceStatusService/StatusReportingService.svc</span><span class="sxs-lookup"><span data-stu-id="1ba40-196">http(s)://</strong><em>&lt;MBAM Administration and Monitoring Server Name&gt;</em><strong>:</strong><em>&lt;the port the web service is bound to&gt;</em><strong>/MBAMComplianceStatusService/StatusReportingService.svc</span></span></strong></p>
<p><strong><span data-ttu-id="1ba40-197">对于 Configuration Manager 集成拓扑中的 MBAM </strong> ：禁用此设置。</span><span class="sxs-lookup"><span data-stu-id="1ba40-197">For MBAM in the Configuration Manager Integration topology</strong>: Disable this setting.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="1ba40-198">配置用户豁免策略</span><span class="sxs-lookup"><span data-stu-id="1ba40-198">Configure user exemption policy</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ba40-199">建议的配置： <strong> 未配置</span><span class="sxs-lookup"><span data-stu-id="1ba40-199">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="1ba40-200">通过此策略设置，你可以配置网站地址、电子邮件地址或电话号码，以指示用户向 BitLocker 加密请求豁免。</span><span class="sxs-lookup"><span data-stu-id="1ba40-200">This policy setting lets you configure a website address, email address, or phone number that instructs a user to request an exemption from BitLocker encryption.</span></span></p>
<p><span data-ttu-id="1ba40-201">如果启用此策略设置并提供网站地址、电子邮件地址或电话号码，用户将看到一个对话框，其中提供了有关如何申请来自 BitLocker 保护的豁免的说明。</span><span class="sxs-lookup"><span data-stu-id="1ba40-201">If you enable this policy setting and provide a website address, email address, or phone number, users see a dialog box with instructions on how to apply for an exemption from BitLocker protection.</span></span> <span data-ttu-id="1ba40-202">有关为用户启用 BitLocker 加密免除的详细信息，请参阅 <a href="how-to-manage-user-bitlocker-encryption-exemptions-mbam-25.md" data-raw-source="[How to Manage User BitLocker Encryption Exemptions](how-to-manage-user-bitlocker-encryption-exemptions-mbam-25.md)"> 如何管理用户 Bitlocker 加密免除 </a> 。</span><span class="sxs-lookup"><span data-stu-id="1ba40-202">For more information about enabling BitLocker encryption exemptions for users, see <a href="how-to-manage-user-bitlocker-encryption-exemptions-mbam-25.md" data-raw-source="[How to Manage User BitLocker Encryption Exemptions](how-to-manage-user-bitlocker-encryption-exemptions-mbam-25.md)">How to Manage User BitLocker Encryption Exemptions</a>.</span></span></p>
<p><span data-ttu-id="1ba40-203">如果禁用或未配置此策略设置，将不向用户显示豁免请求说明。</span><span class="sxs-lookup"><span data-stu-id="1ba40-203">If you either disable or do not configure this policy setting, the exemption request instructions are not displayed to users.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="1ba40-204">注意</span><span class="sxs-lookup"><span data-stu-id="1ba40-204">Note</span></span></strong><br/><p><span data-ttu-id="1ba40-205">用户豁免按用户管理，而不是按计算机进行管理。</span><span class="sxs-lookup"><span data-stu-id="1ba40-205">User exemption is managed per user, not per computer.</span></span> <span data-ttu-id="1ba40-206">如果多个用户登录到同一台计算机，而任何一个用户没有豁免，则该计算机已加密。</span><span class="sxs-lookup"><span data-stu-id="1ba40-206">If multiple users log on to the same computer and any one user is not exempt, the computer is encrypted.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1ba40-207">配置客户体验改善计划</span><span class="sxs-lookup"><span data-stu-id="1ba40-207">Configure customer experience improvement program</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ba40-208">建议的配置： <strong> 已启用</span><span class="sxs-lookup"><span data-stu-id="1ba40-208">Suggested configuration: <strong>Enabled</span></span></strong></p>
<p><span data-ttu-id="1ba40-209">此策略设置允许你配置 MBAM 用户如何加入客户体验改善计划。</span><span class="sxs-lookup"><span data-stu-id="1ba40-209">This policy setting lets you configure how MBAM users can join the Customer Experience Improvement Program.</span></span> <span data-ttu-id="1ba40-210">此程序将收集有关计算机硬件以及用户如何使用 MBAM 的信息，而无需中断其工作。</span><span class="sxs-lookup"><span data-stu-id="1ba40-210">This program collects information about computer hardware and how users use MBAM without interrupting their work.</span></span> <span data-ttu-id="1ba40-211">此信息可帮助 Microsoft 确定要改进的 MBAM 功能。</span><span class="sxs-lookup"><span data-stu-id="1ba40-211">The information helps Microsoft to identify which MBAM features to improve.</span></span> <span data-ttu-id="1ba40-212">Microsoft 不会使用此信息识别或联系 MBAM 用户。</span><span class="sxs-lookup"><span data-stu-id="1ba40-212">Microsoft does not use this information to identify or contact MBAM users.</span></span></p>
<p><span data-ttu-id="1ba40-213">如果启用此策略设置，则用户可以加入客户体验改善计划。</span><span class="sxs-lookup"><span data-stu-id="1ba40-213">If you enable this policy setting, users can join the Customer Experience Improvement Program.</span></span></p>
<p><span data-ttu-id="1ba40-214">如果禁用此策略设置，则用户无法加入客户体验改善计划。</span><span class="sxs-lookup"><span data-stu-id="1ba40-214">If you disable this policy setting, users cannot join the Customer Experience Improvement Program.</span></span></p>
<p><span data-ttu-id="1ba40-215">如果未配置此策略设置，则用户可以选择加入客户体验改善计划。</span><span class="sxs-lookup"><span data-stu-id="1ba40-215">If you do not configure this policy setting, users have the option to join the Customer Experience Improvement Program.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="1ba40-216">提供安全策略链接的 URL</span><span class="sxs-lookup"><span data-stu-id="1ba40-216">Provide the URL for the Security Policy link</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ba40-217">建议的配置： <strong> 已启用</span><span class="sxs-lookup"><span data-stu-id="1ba40-217">Suggested configuration: <strong>Enabled</span></span></strong></p>
<p><span data-ttu-id="1ba40-218">使用此策略设置指定显示给最终用户的 URL，作为名为 " &quot; 公司安全策略" 的链接。 &quot;该链接指向公司的内部安全策略，并向最终用户提供有关加密要求的信息。</span><span class="sxs-lookup"><span data-stu-id="1ba40-218">Use this policy setting to specify a URL that is displayed to end users as a link named &quot;Company Security Policy.&quot; The link points to your company’s internal security policy and provides end users with information about encryption requirements.</span></span> <span data-ttu-id="1ba40-219">当 MBAM 提示用户加密驱动器时，将显示该链接。</span><span class="sxs-lookup"><span data-stu-id="1ba40-219">The link appears when users are prompted by MBAM to encrypt a drive.</span></span></p>
<p><span data-ttu-id="1ba40-220">如果启用此策略设置，则可以配置安全策略链接的 URL。</span><span class="sxs-lookup"><span data-stu-id="1ba40-220">If you enable this policy setting, you can configure the URL for the Security Policy link.</span></span></p>
<p><span data-ttu-id="1ba40-221">如果禁用或未配置此策略设置，则不会向用户显示 "安全策略" 链接。</span><span class="sxs-lookup"><span data-stu-id="1ba40-221">If you disable or do not configure this policy setting, the Security Policy link is not displayed to users.</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="1ba40-222">已修复的驱动器组策略定义</span><span class="sxs-lookup"><span data-stu-id="1ba40-222">Fixed Drive Group Policy definitions</span></span>

<span data-ttu-id="1ba40-223">本部分介绍了在下列 GPO 节点处进行 Microsoft BitLocker 管理和监视的固定驱动器策略定义：**计算机配置** &gt; **策略** &gt; **管理模板** &gt; **Windows 组件** &gt; **MDOP MBAM （BitLocker Management）** 已 &gt; **修复的驱动器**。</span><span class="sxs-lookup"><span data-stu-id="1ba40-223">This section describes Fixed Drive policy definitions for Microsoft BitLocker Administration and Monitoring at the following GPO node: **Computer Configuration** &gt; **Policies** &gt; **Administrative Templates** &gt; **Windows Components** &gt; **MDOP MBAM (BitLocker Management)** &gt; **Fixed Drive**.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="1ba40-224">策略名称</span><span class="sxs-lookup"><span data-stu-id="1ba40-224">Policy name</span></span></th>
<th align="left"><span data-ttu-id="1ba40-225">概述和建议的组策略设置</span><span class="sxs-lookup"><span data-stu-id="1ba40-225">Overview and suggested Group Policy settings</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1ba40-226">固定数据驱动器加密设置</span><span class="sxs-lookup"><span data-stu-id="1ba40-226">Fixed data drive encryption settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ba40-227">建议的配置： <strong> 已启用</span><span class="sxs-lookup"><span data-stu-id="1ba40-227">Suggested configuration: <strong>Enabled</span></span></strong></p>
<p><span data-ttu-id="1ba40-228">通过此策略设置，你可以管理固定数据驱动器是否必须加密。</span><span class="sxs-lookup"><span data-stu-id="1ba40-228">This policy setting lets you manage whether fixed data drives must be encrypted.</span></span></p>
<p><span data-ttu-id="1ba40-229">如果需要加密操作系统卷，请单击 " <strong> 启用自动解锁固定数据驱动器" </strong> 。</span><span class="sxs-lookup"><span data-stu-id="1ba40-229">If the operating system volume is required to be encrypted, click <strong>Enable auto-unlock fixed data drive</strong>.</span></span></p>
<p><span data-ttu-id="1ba40-230">如果启用此策略，则不能禁用 " <strong> 配置固定数据驱动器的密码使用" </strong> 策略，除非你要启用或要求对固定数据驱动器使用自动解锁。</span><span class="sxs-lookup"><span data-stu-id="1ba40-230">When you enable this policy, you must not disable the <strong>Configure use of password for fixed data drives</strong> policy unless you are enabling or requiring the use of auto-unlock for fixed data drives.</span></span></p>
<p><span data-ttu-id="1ba40-231">如果必须对固定数据驱动器使用自动解锁，必须配置要加密的操作系统卷。</span><span class="sxs-lookup"><span data-stu-id="1ba40-231">If you have to use auto-unlock for fixed data drives, you must configure operating system volumes to be encrypted.</span></span></p>
<p><span data-ttu-id="1ba40-232">如果启用此策略设置，则用户需要将所有固定的数据驱动器置于 BitLocker 保护下，然后再加密数据驱动器。</span><span class="sxs-lookup"><span data-stu-id="1ba40-232">If you enable this policy setting, users are required to put all fixed data drives under BitLocker protection, and the data drives are then encrypted.</span></span></p>
<p><span data-ttu-id="1ba40-233">如果未配置此策略设置，则不需要用户在 BitLocker 保护下放置固定的数据驱动器。</span><span class="sxs-lookup"><span data-stu-id="1ba40-233">If you do not configure this policy setting, users are not required to put fixed data drives under BitLocker protection.</span></span> <span data-ttu-id="1ba40-234">如果在对固定数据驱动器进行加密之后应用此策略，MBAM 代理将对加密的固定数据驱动器进行解密。</span><span class="sxs-lookup"><span data-stu-id="1ba40-234">If you apply this policy after fixed data drives are encrypted, the MBAM agent decrypts the encrypted fixed data drives.</span></span></p>
<p><span data-ttu-id="1ba40-235">如果禁用此策略设置，则用户无法在 "BitLocker 保护" 下放置固定数据驱动器。</span><span class="sxs-lookup"><span data-stu-id="1ba40-235">If you disable this policy setting, users cannot put their fixed data drives under BitLocker protection.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="1ba40-236">拒绝对不受 BitLocker 保护的固定驱动器的写访问</span><span class="sxs-lookup"><span data-stu-id="1ba40-236">Deny write access to fixed drives not protected by BitLocker</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ba40-237">建议的配置： <strong> 未配置</span><span class="sxs-lookup"><span data-stu-id="1ba40-237">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="1ba40-238">此策略设置确定固定数据驱动器是否需要 BitLocker 保护才能在计算机上写入。</span><span class="sxs-lookup"><span data-stu-id="1ba40-238">This policy setting determines whether BitLocker protection is required for fixed data drives to be writable on a computer.</span></span> <span data-ttu-id="1ba40-239">启用 BitLocker 时，将应用此策略设置。</span><span class="sxs-lookup"><span data-stu-id="1ba40-239">This policy setting is applied when you turn on BitLocker.</span></span></p>
<p><span data-ttu-id="1ba40-240">当未配置策略时，计算机上的所有固定数据驱动器都将以读/写权限挂载。</span><span class="sxs-lookup"><span data-stu-id="1ba40-240">When the policy is not configured, all fixed data drives on the computer are mounted with read/write permission.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1ba40-241">允许从早期版本的 Windows 访问受 BitLocker 保护的固定驱动器</span><span class="sxs-lookup"><span data-stu-id="1ba40-241">Allow access to BitLocker-protected fixed drives from earlier versions of Windows</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ba40-242">建议的配置： <strong> 未配置</span><span class="sxs-lookup"><span data-stu-id="1ba40-242">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="1ba40-243">启用此策略，以便可以在运行 Windows Server 2008、Windows Vista、Windows XP SP3 或具有 SP2 的 Windows XP 的计算机上解锁和查看具有 FAT 文件系统的固定驱动器。</span><span class="sxs-lookup"><span data-stu-id="1ba40-243">Enable this policy so that fixed drives with the FAT file system can be unlocked and viewed on computers that are running Windows Server 2008, Windows Vista, Windows XP with SP3, or Windows XP with SP2.</span></span></p>
<p><span data-ttu-id="1ba40-244">如果启用或未配置此策略，则可以解锁通过 FAT 文件系统格式化的固定驱动器，并且可以在运行 Windows Server 2008、Windows Vista、Windows XP SP3 的计算机或具有 SP2 的 Windows XP 的计算机上查看其内容。</span><span class="sxs-lookup"><span data-stu-id="1ba40-244">When the policy is enabled or not configured, fixed drives that are formatted with the FAT file system can be unlocked and their content can be viewed on computers that are running Windows Server 2008, Windows Vista, Windows XP with SP3, or Windows XP with SP2.</span></span> <span data-ttu-id="1ba40-245">这些操作系统对受 BitLocker 保护的驱动器具有只读权限。</span><span class="sxs-lookup"><span data-stu-id="1ba40-245">These operating systems have read-only permission to BitLocker-protected drives.</span></span></p>
<p><span data-ttu-id="1ba40-246">禁用该策略时，无法解锁通过 FAT 文件系统格式化的固定驱动器，并且无法在运行 Windows Server 2008、Windows Vista、Windows XP SP3 或 Windows XP SP2 的计算机上查看其内容。</span><span class="sxs-lookup"><span data-stu-id="1ba40-246">When the policy is disabled, fixed drives that are formatted with the FAT file system cannot be unlocked and their content cannot be viewed on computers that are running Windows Server 2008, Windows Vista, Windows XP with SP3, or Windows XP with SP2.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="1ba40-247">为固定驱动器配置密码的使用</span><span class="sxs-lookup"><span data-stu-id="1ba40-247">Configure use of password for fixed drives</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ba40-248">建议的配置： <strong> 未配置</span><span class="sxs-lookup"><span data-stu-id="1ba40-248">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="1ba40-249">使用此策略指定是否需要密码来解锁受 BitLocker 保护的固定数据驱动器。</span><span class="sxs-lookup"><span data-stu-id="1ba40-249">Use this policy to specify whether a password is required to unlock BitLocker-protected fixed data drives.</span></span></p>
<p><span data-ttu-id="1ba40-250">如果启用此策略设置，则用户可以配置满足你定义的要求的密码。</span><span class="sxs-lookup"><span data-stu-id="1ba40-250">If you enable this policy setting, users can configure a password that meets the requirements that you define.</span></span> <span data-ttu-id="1ba40-251">BitLocker 使用户能够使用驱动器上提供的任何保护程序解锁驱动器。</span><span class="sxs-lookup"><span data-stu-id="1ba40-251">BitLocker enables users to unlock a drive with any of the protectors that are available on the drive.</span></span></p>
<p><span data-ttu-id="1ba40-252">启用 BitLocker 时，将强制执行这些设置，而不是在解锁卷时执行。</span><span class="sxs-lookup"><span data-stu-id="1ba40-252">These settings are enforced when you turn on BitLocker, not when you unlock a volume.</span></span></p>
<p><span data-ttu-id="1ba40-253">如果禁用此策略设置，则不允许用户使用密码。</span><span class="sxs-lookup"><span data-stu-id="1ba40-253">If you disable this policy setting, users are not allowed to use a password.</span></span></p>
<p><span data-ttu-id="1ba40-254">如果未配置策略，则密码受默认设置支持，默认设置不包括密码复杂性要求，并且不需要八个字符。</span><span class="sxs-lookup"><span data-stu-id="1ba40-254">When the policy is not configured, passwords are supported with the default settings, which do not include password complexity requirements and which require only eight characters.</span></span></p>
<p><span data-ttu-id="1ba40-255">若要获得更高的安全性，请启用此策略，然后选择 <strong> "需要密码才能使用固定数据驱动器" </strong> ，单击 " <strong> 需要密码复杂性 </strong> "，然后设置所 <strong> 需的最小密码长度 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="1ba40-255">For higher security, enable this policy, and then select <strong>Require password for fixed data drive</strong>, click <strong>Require password complexity</strong>, and set the <strong>minimum password length</strong> that you want.</span></span></p>
<p><span data-ttu-id="1ba40-256">如果禁用此策略设置，则不允许用户使用密码。</span><span class="sxs-lookup"><span data-stu-id="1ba40-256">If you disable this policy setting, users are not allowed to use a password.</span></span></p>
<p><span data-ttu-id="1ba40-257">如果未配置此策略设置，则密码支持的默认设置（不包括密码复杂性要求），并且不需要八个字符。</span><span class="sxs-lookup"><span data-stu-id="1ba40-257">If you do not configure this policy setting, passwords are supported with the default settings, which do not include password complexity requirements and which require only eight characters.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1ba40-258">选择如何恢复受 BitLocker 保护的固定驱动器</span><span class="sxs-lookup"><span data-stu-id="1ba40-258">Choose how BitLocker-protected fixed drives can be recovered</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ba40-259">建议的配置： <strong> 未配置</span><span class="sxs-lookup"><span data-stu-id="1ba40-259">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="1ba40-260">将此策略配置为启用 BitLocker 数据恢复代理或将 BitLocker 恢复信息保存到 Active Directory 域服务（AD DS）。</span><span class="sxs-lookup"><span data-stu-id="1ba40-260">Configure this policy to enable the BitLocker data recovery agent or to save BitLocker recovery information to Active Directory Domain Services (AD DS).</span></span></p>
<p><span data-ttu-id="1ba40-261">如果未配置策略，则允许 BitLocker 数据恢复代理，并且不会将恢复信息备份到 AD DS。</span><span class="sxs-lookup"><span data-stu-id="1ba40-261">When the policy is not configured, the BitLocker data recovery agent is allowed, and recovery information is not backed up to AD DS.</span></span> <span data-ttu-id="1ba40-262">MBAM 不需要将恢复信息备份到 AD DS。</span><span class="sxs-lookup"><span data-stu-id="1ba40-262">MBAM does not require recovery information to be backed up to AD DS.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="1ba40-263">加密策略强制设置</span><span class="sxs-lookup"><span data-stu-id="1ba40-263">Encryption Policy Enforcement Settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ba40-264">建议的配置： <strong> 已启用</span><span class="sxs-lookup"><span data-stu-id="1ba40-264">Suggested configuration: <strong>Enabled</span></span></strong></p>
<p><span data-ttu-id="1ba40-265">使用此策略设置配置固定数据驱动器可以保持不兼容的天数，直到它们强制遵从 MBAM 策略。</span><span class="sxs-lookup"><span data-stu-id="1ba40-265">Use this policy setting to configure the number of days that fixed data drives can remain noncompliant until they are forced to comply with MBAM policies.</span></span> <span data-ttu-id="1ba40-266">用户不能推迟所需操作或在宽限期后向其请求豁免。</span><span class="sxs-lookup"><span data-stu-id="1ba40-266">Users cannot postpone the required action or request an exemption from it after the grace period.</span></span> <span data-ttu-id="1ba40-267">宽限期在固定数据驱动器被确定为不相容时开始。</span><span class="sxs-lookup"><span data-stu-id="1ba40-267">The grace period starts when the fixed data drive is determined to be noncompliant.</span></span> <span data-ttu-id="1ba40-268">但是，固定数据驱动器策略不会强制实施，直到操作系统驱动器符合要求。</span><span class="sxs-lookup"><span data-stu-id="1ba40-268">However, the fixed data drive policy is not enforced until the operating system drive is compliant.</span></span></p>
<p><span data-ttu-id="1ba40-269">如果宽限期已过，并且固定数据驱动器仍不合规，则用户无法选择延期或请求豁免。</span><span class="sxs-lookup"><span data-stu-id="1ba40-269">If the grace period expires and the fixed data drive is still not compliant, users do not have the option to postpone or to request an exemption.</span></span> <span data-ttu-id="1ba40-270">如果加密过程需要用户输入，则会显示一个对话框，用户在提供所需的信息之前无法关闭该对话框。</span><span class="sxs-lookup"><span data-stu-id="1ba40-270">If the encryption process requires user input, a dialog box appears that users cannot close until they provide the required information.</span></span></p>
<p><span data-ttu-id="1ba40-271"><strong> </strong> 在 " <strong> 配置固定驱动器的不符合性宽限期天数" 中输入 0 </strong> ，以强制在操作系统驱动器的宽限期到期后立即开始加密过程。</span><span class="sxs-lookup"><span data-stu-id="1ba40-271">Enter <strong>0</strong> in the <strong>Configure the number of noncompliance grace period days for fixed drives</strong> to force the encryption process to begin immediately after the grace period expires for the operating system drive.</span></span></p>
<p><span data-ttu-id="1ba40-272">如果禁用或未配置此设置，则不强制用户遵守 MBAM 策略。</span><span class="sxs-lookup"><span data-stu-id="1ba40-272">If you disable or do not configure this setting, users are not forced to comply with MBAM policies.</span></span></p>
<p><span data-ttu-id="1ba40-273">如果无需用户交互即可添加保护程序，则在宽限期到期后，加密将在后台开始。</span><span class="sxs-lookup"><span data-stu-id="1ba40-273">If no user interaction is required to add a protector, encryption begins in the background after the grace period expires.</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="1ba40-274">操作系统驱动器组策略定义</span><span class="sxs-lookup"><span data-stu-id="1ba40-274">Operating System Drive Group Policy definitions</span></span>

<span data-ttu-id="1ba40-275">本部分介绍了以下 GPO 节点上的 Microsoft BitLocker 管理和监视的操作系统驱动器策略定义：**计算机配置** &gt; **策略** &gt; **管理模板** &gt; **Windows 组件** &gt; **MDOP MBAM （BitLocker 管理）** &gt; **操作系统驱动器**。</span><span class="sxs-lookup"><span data-stu-id="1ba40-275">This section describes Operating System Drive policy definitions for Microsoft BitLocker Administration and Monitoring at the following GPO node: **Computer Configuration** &gt; **Policies** &gt; **Administrative Templates** &gt; **Windows Components** &gt; **MDOP MBAM (BitLocker Management)** &gt; **Operating System Drive**.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="1ba40-276">策略名称</span><span class="sxs-lookup"><span data-stu-id="1ba40-276">Policy name</span></span></th>
<th align="left"><span data-ttu-id="1ba40-277">概述和建议的组策略设置</span><span class="sxs-lookup"><span data-stu-id="1ba40-277">Overview and suggested Group Policy settings</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1ba40-278">操作系统驱动器加密设置</span><span class="sxs-lookup"><span data-stu-id="1ba40-278">Operating system drive encryption settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ba40-279">建议的配置： <strong> 已启用</span><span class="sxs-lookup"><span data-stu-id="1ba40-279">Suggested configuration: <strong>Enabled</span></span></strong></p>
<p><span data-ttu-id="1ba40-280">通过此策略设置，你可以管理操作系统驱动器是否必须加密。</span><span class="sxs-lookup"><span data-stu-id="1ba40-280">This policy setting lets you manage whether the operating system drive must be encrypted.</span></span></p>
<p><span data-ttu-id="1ba40-281">若要获得更高的安全性，请考虑在 <strong> </strong> &gt; <strong> </strong> &gt; <strong> </strong> 使用 TPM + 引脚保护器启用时在系统电源管理睡眠设置中禁用以下策略设置：</span><span class="sxs-lookup"><span data-stu-id="1ba40-281">For higher security, consider disabling the following policy settings in <strong>System</strong> &gt; <strong>Power Management</strong> &gt; <strong>Sleep Settings</strong> when you enable them with TPM + PIN protector:</span></span></p>
<ul>
<li><p><span data-ttu-id="1ba40-282">睡眠（接通）时允许待机状态（S1-S3）</span><span class="sxs-lookup"><span data-stu-id="1ba40-282">Allow Standby States (S1-S3) When Sleeping (Plugged In)</span></span></p></li>
<li><p><span data-ttu-id="1ba40-283">睡眠时允许待机状态（S1-S3）（使用电池）</span><span class="sxs-lookup"><span data-stu-id="1ba40-283">Allow Standby States (S1-S3) When Sleeping (On Battery)</span></span></p></li>
</ul>
<p><span data-ttu-id="1ba40-284">如果你运行的是 Microsoft Windows 8 或更高版本，并且想要在没有 TPM 的计算机上使用 BitLocker，请选中 " <strong> 允许没有兼容的 TPM 的 bitlocker" </strong> 复选框。</span><span class="sxs-lookup"><span data-stu-id="1ba40-284">If you are running Microsoft Windows 8 or later, and you want to use BitLocker on a computer without a TPM, select the <strong>Allow BitLocker without a compatible TPM</strong> check box.</span></span> <span data-ttu-id="1ba40-285">在此模式下，启动时需要密码。</span><span class="sxs-lookup"><span data-stu-id="1ba40-285">In this mode, a password is required for startup.</span></span> <span data-ttu-id="1ba40-286">如果您忘记了密码，则必须使用其中一个 BitLocker 恢复选项来访问驱动器。</span><span class="sxs-lookup"><span data-stu-id="1ba40-286">If you forget the password, you have to use one of the BitLocker recovery options to access the drive.</span></span></p>
<p><span data-ttu-id="1ba40-287">在具有兼容的 TPM 的计算机上，启动时可以使用两种类型的身份验证方法为加密数据提供额外保护。</span><span class="sxs-lookup"><span data-stu-id="1ba40-287">On a computer with a compatible TPM, two types of authentication methods can be used at startup to provide added protection for encrypted data.</span></span> <span data-ttu-id="1ba40-288">当计算机启动时，它只能使用 TPM 进行身份验证，也可以要求输入个人识别码（PIN）。</span><span class="sxs-lookup"><span data-stu-id="1ba40-288">When the computer starts, it can use only the TPM for authentication, or it can also require the entry of a personal identification number (PIN).</span></span></p>
<p><span data-ttu-id="1ba40-289">如果启用此策略设置，则用户必须将操作系统驱动器置于 BitLocker 保护下，然后再加密驱动器。</span><span class="sxs-lookup"><span data-stu-id="1ba40-289">If you enable this policy setting, users have to put the operating system drive under BitLocker protection, and the drive is then encrypted.</span></span></p>
<p><span data-ttu-id="1ba40-290">如果禁用此策略，则用户无法将操作系统驱动器置于 BitLocker 保护下。</span><span class="sxs-lookup"><span data-stu-id="1ba40-290">If you disable this policy, users cannot put the operating system drive under BitLocker protection.</span></span> <span data-ttu-id="1ba40-291">如果在加密操作系统驱动器后应用此策略，则会解密驱动器。</span><span class="sxs-lookup"><span data-stu-id="1ba40-291">If you apply this policy after the operating system drive is encrypted, the drive is then decrypted.</span></span></p>
<p><span data-ttu-id="1ba40-292">如果未配置此策略，则不需要将操作系统驱动器置于 "BitLocker 保护" 下。</span><span class="sxs-lookup"><span data-stu-id="1ba40-292">If you do not configure this policy, the operating system drive is not required to be placed under BitLocker protection.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="1ba40-293">允许增强的 Pin 启动</span><span class="sxs-lookup"><span data-stu-id="1ba40-293">Allow enhanced PINs for startup</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ba40-294">建议的配置： <strong> 未配置</span><span class="sxs-lookup"><span data-stu-id="1ba40-294">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="1ba40-295">使用此策略设置配置是否将增强的启动 Pin 用于 BitLocker。</span><span class="sxs-lookup"><span data-stu-id="1ba40-295">Use this policy setting to configure whether enhanced startup PINs are used with BitLocker.</span></span> <span data-ttu-id="1ba40-296">增强的启动 Pin 允许使用包括大写字母和小写字母、符号、数字和空格的字符。</span><span class="sxs-lookup"><span data-stu-id="1ba40-296">Enhanced startup PINs permit the use of characters including uppercase and lowercase letters, symbols, numbers, and spaces.</span></span> <span data-ttu-id="1ba40-297">启用 BitLocker 时，将应用此策略设置。</span><span class="sxs-lookup"><span data-stu-id="1ba40-297">This policy setting is applied when you turn on BitLocker.</span></span></p>
<p><span data-ttu-id="1ba40-298">如果启用此策略设置，则设置的所有新 BitLocker 启动引脚将使最终用户能够创建增强的 Pin。</span><span class="sxs-lookup"><span data-stu-id="1ba40-298">If you enable this policy setting, all new BitLocker startup PINs set will enable end user to create enhanced PINs.</span></span> <span data-ttu-id="1ba40-299">但是，并非所有计算机都可以支持预引导环境中的增强引脚。</span><span class="sxs-lookup"><span data-stu-id="1ba40-299">However, not all computers can support enhanced PINs in the pre-boot environment.</span></span> <span data-ttu-id="1ba40-300">我们强烈建议管理员先评估其系统是否与此功能兼容，然后再启用其使用。</span><span class="sxs-lookup"><span data-stu-id="1ba40-300">We strongly recommend that administrators evaluate whether their systems are compatible with this feature before enabling its use.</span></span></p>
<p><span data-ttu-id="1ba40-301">选中 " <strong> 需要 ASCII 专用引脚" </strong> 复选框，以使增强引脚更好地与限制可在预引导环境中输入的字符类型或字符数的计算机兼容。</span><span class="sxs-lookup"><span data-stu-id="1ba40-301">Select the <strong>Require ASCII-only PINs</strong> check box to help make enhanced PINs more compatible with computers that limit the type or number of characters that can be entered in the pre-boot environment.</span></span></p>
<p><span data-ttu-id="1ba40-302">如果禁用或未配置此策略设置，则不使用增强型 Pin。</span><span class="sxs-lookup"><span data-stu-id="1ba40-302">If you disable or do not configure this policy setting, enhanced PINs are not used.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1ba40-303">选择可以如何恢复受 BitLocker 保护的操作系统驱动器</span><span class="sxs-lookup"><span data-stu-id="1ba40-303">Choose how BitLocker-protected operating system drives can be recovered</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ba40-304">建议的配置： <strong> 未配置</span><span class="sxs-lookup"><span data-stu-id="1ba40-304">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="1ba40-305">将此策略配置为启用 BitLocker 数据恢复代理或将 BitLocker 恢复信息保存到 Active Directory 域服务（AD DS）。</span><span class="sxs-lookup"><span data-stu-id="1ba40-305">Configure this policy to enable the BitLocker data recovery agent or to save BitLocker recovery information to Active Directory Domain Services (AD DS).</span></span></p>
<p><span data-ttu-id="1ba40-306">如果未配置此策略，则允许数据恢复代理，并且不会将恢复信息备份到 AD DS。</span><span class="sxs-lookup"><span data-stu-id="1ba40-306">When this policy is not configured, the data recovery agent is allowed, and recovery information is not backed up to AD DS.</span></span></p>
<p><span data-ttu-id="1ba40-307">MBAM 操作不需要将恢复信息备份到 AD DS。</span><span class="sxs-lookup"><span data-stu-id="1ba40-307">MBAM operation does not require recovery information to be backed up to AD DS.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="1ba40-308">为操作系统驱动器配置密码的使用</span><span class="sxs-lookup"><span data-stu-id="1ba40-308">Configure use of passwords for operating system drives</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ba40-309">建议的配置： <strong> 未配置</span><span class="sxs-lookup"><span data-stu-id="1ba40-309">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="1ba40-310">使用此策略设置可设置用于解锁受 BitLocker 保护的操作系统驱动器的密码的约束。</span><span class="sxs-lookup"><span data-stu-id="1ba40-310">Use this policy setting to set the constraints for passwords that are used to unlock BitLocker-protected operating system drives.</span></span> <span data-ttu-id="1ba40-311">如果在操作系统驱动器上允许非 TPM 保护器，则可以设置密码、强制密码的复杂性要求，并配置密码的最小长度。</span><span class="sxs-lookup"><span data-stu-id="1ba40-311">If non-TPM protectors are allowed on operating system drives, you can provision a password, enforce complexity requirements on the password, and configure a minimum length for the password.</span></span> <span data-ttu-id="1ba40-312">为了使复杂性要求设置生效，你还必须启用组策略设置 &quot; 密码必须满足 &quot; 位于 "计算机配置 &gt; Windows 设置 &gt; 安全设置" &gt; 帐户策略 &gt; 密码策略中的复杂性要求。</span><span class="sxs-lookup"><span data-stu-id="1ba40-312">For the complexity requirement setting to be effective, you must also enable the Group Policy setting &quot;Password must meet complexity requirements&quot; located in Computer Configuration &gt; Windows Settings &gt; Security Settings &gt; Account Policies &gt; Password Policy.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="1ba40-313">注意</span><span class="sxs-lookup"><span data-stu-id="1ba40-313">Note</span></span></strong><br/><p><span data-ttu-id="1ba40-314">启用 BitLocker 时，将强制执行这些设置，而不是在解锁卷时执行。</span><span class="sxs-lookup"><span data-stu-id="1ba40-314">These settings are enforced when you turn on BitLocker, not when you unlock a volume.</span></span> <span data-ttu-id="1ba40-315">BitLocker 允许您使用驱动器上提供的任何保护程序解锁驱动器。</span><span class="sxs-lookup"><span data-stu-id="1ba40-315">BitLocker lets you unlock a drive with any of the protectors that are available on the drive.</span></span></p>
</div>
<div>

</div>
<p><span data-ttu-id="1ba40-316">如果启用此策略设置，则用户可以配置满足你定义的要求的密码。</span><span class="sxs-lookup"><span data-stu-id="1ba40-316">If you enable this policy setting, users can configure a password that meets the requirements that you define.</span></span> <span data-ttu-id="1ba40-317">若要对密码强制执行复杂性要求，请单击 " <strong> 需要密码复杂性" </strong> 。</span><span class="sxs-lookup"><span data-stu-id="1ba40-317">To enforce complexity requirements on the password, click <strong>Require password complexity</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1ba40-318">为基于 BIOS 的固件配置配置 TPM 平台验证配置文件</span><span class="sxs-lookup"><span data-stu-id="1ba40-318">Configure TPM platform validation profile for BIOS-based firmware configurations</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ba40-319">建议的配置： <strong> 未配置</span><span class="sxs-lookup"><span data-stu-id="1ba40-319">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="1ba40-320">通过此策略设置，你可以配置计算机&#39;s 受信任的平台模块（TPM）安全硬件如何保护 BitLocker 加密密钥。</span><span class="sxs-lookup"><span data-stu-id="1ba40-320">This policy setting allows you to configure how the computer&#39;s Trusted Platform Module (TPM) security hardware secures the BitLocker encryption key.</span></span> <span data-ttu-id="1ba40-321">如果计算机没有兼容的 TPM，或者如果 BitLocker 已使用 TPM 保护启用，则此策略设置不适用。</span><span class="sxs-lookup"><span data-stu-id="1ba40-321">This policy setting does not apply if the computer does not have a compatible TPM or if BitLocker has already been turned on with TPM protection.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="1ba40-322">重要提示</span><span class="sxs-lookup"><span data-stu-id="1ba40-322">Important</span></span></strong><br/><p><span data-ttu-id="1ba40-323">此组策略设置仅适用于使用启用了兼容性服务模块（CSM）的具有 BIOS 配置的计算机或具有 UEFI 固件的计算机。</span><span class="sxs-lookup"><span data-stu-id="1ba40-323">This Group Policy setting applies only to computers with BIOS configurations or to computers with UEFI firmware with a Compatibility Service Module (CSM) enabled.</span></span> <span data-ttu-id="1ba40-324">使用本机 UEFI 固件配置的计算机将不同的值存储到平台配置寄存器（PCRs）中。</span><span class="sxs-lookup"><span data-stu-id="1ba40-324">Computers that use a native UEFI firmware configuration store different values into the Platform Configuration Registers (PCRs).</span></span> <span data-ttu-id="1ba40-325">使用 " &quot; 配置本机 uefi 固件配置" 组策略设置的 tpm 平台验证配置文件 &quot; ，为使用本机 uefi 固件的计算机配置 tpm PCR 配置文件。</span><span class="sxs-lookup"><span data-stu-id="1ba40-325">Use the &quot;Configure TPM platform validation profile for native UEFI firmware configurations&quot; Group Policy setting to configure the TPM PCR profile for computers that use native UEFI firmware.</span></span></p>
</div>
<div>

</div>
<p><span data-ttu-id="1ba40-326">如果启用 BitLocker 之前启用此策略设置，则可以在取消对 BitLocker 加密的操作系统驱动器的访问之前配置 TPM 验证的启动组件。</span><span class="sxs-lookup"><span data-stu-id="1ba40-326">If you enable this policy setting before you turn on BitLocker, you can configure the boot components that the TPM validates before you unlock access to the BitLocker-encrypted operating system drive.</span></span> <span data-ttu-id="1ba40-327">如果这些组件中的任何一个在 BitLocker 保护生效时更改，则 TPM 不会释放加密密钥以解锁驱动器，而是显示 BitLocker 恢复控制台，并且要求你提供恢复密码或恢复密钥以解锁驱动器。</span><span class="sxs-lookup"><span data-stu-id="1ba40-327">If any of these components change while BitLocker protection is in effect, the TPM does not release the encryption key to unlock the drive and the computer instead displays the BitLocker Recovery console and requires that you provide either the recovery password or recovery key to unlock the drive.</span></span></p>
<p><span data-ttu-id="1ba40-328">如果禁用或未配置此策略设置，则 BitLocker 使用由安装脚本指定的默认平台验证配置文件或平台验证配置文件。</span><span class="sxs-lookup"><span data-stu-id="1ba40-328">If you disable or do not configure this policy setting, BitLocker uses the default platform validation profile or the platform validation profile that is specified by the Setup script.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="1ba40-329">配置 TPM 平台验证配置文件</span><span class="sxs-lookup"><span data-stu-id="1ba40-329">Configure TPM platform validation profile</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ba40-330">建议的配置： <strong> 未配置</span><span class="sxs-lookup"><span data-stu-id="1ba40-330">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="1ba40-331">通过此策略设置，你可以配置计算机&#39;s 受信任的平台模块（TPM）安全硬件如何保护 BitLocker 加密密钥。</span><span class="sxs-lookup"><span data-stu-id="1ba40-331">This policy setting enables you to configure how the computer&#39;s Trusted Platform Module (TPM) security hardware secures the BitLocker encryption key.</span></span> <span data-ttu-id="1ba40-332">如果计算机没有兼容的 TPM，或者如果 BitLocker 已使用 TPM 保护启用，则此策略设置不适用。</span><span class="sxs-lookup"><span data-stu-id="1ba40-332">This policy setting does not apply if the computer does not have a compatible TPM or if BitLocker has already been turned on with TPM protection.</span></span></p>
<p><span data-ttu-id="1ba40-333">如果启用 BitLocker 之前启用此策略设置，则可以在取消对 BitLocker 加密的操作系统驱动器的访问之前配置 TPM 验证的启动组件。</span><span class="sxs-lookup"><span data-stu-id="1ba40-333">If you enable this policy setting before you turn on BitLocker, you can configure the boot components that the TPM validates before you unlock access to the BitLocker-encrypted operating system drive.</span></span> <span data-ttu-id="1ba40-334">如果这些组件中的任何一个在 BitLocker 保护生效时更改，则 TPM 不会释放加密密钥以解锁驱动器，而是显示 BitLocker 恢复控制台，并且要求你提供恢复密码或恢复密钥以解锁驱动器。</span><span class="sxs-lookup"><span data-stu-id="1ba40-334">If any of these components change while BitLocker protection is in effect, the TPM does not release the encryption key to unlock the drive and the computer instead displays the BitLocker Recovery console and requires that you provide either the recovery password or recovery key to unlock the drive.</span></span></p>
<p><span data-ttu-id="1ba40-335">如果禁用或未配置此策略设置，则 BitLocker 使用由安装脚本指定的默认平台验证配置文件或平台验证配置文件。</span><span class="sxs-lookup"><span data-stu-id="1ba40-335">If you disable or do not configure this policy setting, BitLocker uses the default platform validation profile or the platform validation profile that is specified by the setup script.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1ba40-336">为本机 UEFI 固件配置配置 TPM 平台验证配置文件</span><span class="sxs-lookup"><span data-stu-id="1ba40-336">Configure TPM platform validation profile for native UEFI firmware configurations</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ba40-337">建议的配置： <strong> 未配置</span><span class="sxs-lookup"><span data-stu-id="1ba40-337">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="1ba40-338">通过此策略设置，你可以配置计算机&#39;s 受信任的平台模块（TPM）安全硬件如何保护 BitLocker 加密密钥。</span><span class="sxs-lookup"><span data-stu-id="1ba40-338">This policy setting allows you to configure how the computer&#39;s Trusted Platform Module (TPM) security hardware secures the BitLocker encryption key.</span></span> <span data-ttu-id="1ba40-339">如果计算机没有兼容的 TPM，或者如果 BitLocker 已使用 TPM 保护启用，则此策略设置不适用。</span><span class="sxs-lookup"><span data-stu-id="1ba40-339">This policy setting does not apply if the computer does not have a compatible TPM or if BitLocker has already been turned on with TPM protection.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="1ba40-340">重要提示</span><span class="sxs-lookup"><span data-stu-id="1ba40-340">Important</span></span></strong><br/><p><span data-ttu-id="1ba40-341">此组策略设置仅适用于具有本机 UEFI 固件配置的计算机。</span><span class="sxs-lookup"><span data-stu-id="1ba40-341">This Group Policy setting applies only to computers with a native UEFI firmware configuration.</span></span></p>
</div>
<div>

</div>
<p><span data-ttu-id="1ba40-342">如果启用 BitLocker 之前启用此策略设置，则可以先配置 TPM 验证的启动组件，然后再解除对 BitLocker 加密操作系统驱动器的访问。</span><span class="sxs-lookup"><span data-stu-id="1ba40-342">If you enable this policy setting before you turn on BitLocker, you can configure the boot components that the TPM validates before unlocking access to the BitLocker-encrypted operating system drive.</span></span> <span data-ttu-id="1ba40-343">如果这些组件中的任何一个在 BitLocker 保护生效时更改，则 TPM 不会释放加密密钥以解锁驱动器，而是显示 BitLocker 恢复控制台，并且要求你提供恢复密码或恢复密钥以解锁驱动器。</span><span class="sxs-lookup"><span data-stu-id="1ba40-343">If any of these components change while BitLocker protection is in effect, the TPM does not release the encryption key to unlock the drive and the computer instead displays the BitLocker Recovery console and requires that you provide either the recovery password or recovery key to unlock the drive.</span></span></p>
<p><span data-ttu-id="1ba40-344">如果禁用或未配置此策略设置，则 BitLocker 使用由安装脚本指定的默认平台验证配置文件或平台验证配置文件。</span><span class="sxs-lookup"><span data-stu-id="1ba40-344">If you disable or do not configure this policy setting, BitLocker uses the default platform validation profile or the platform validation profile that is specified by the setup script.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="1ba40-345">在 BitLocker 恢复后重置平台验证数据</span><span class="sxs-lookup"><span data-stu-id="1ba40-345">Reset platform validation data after BitLocker recovery</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ba40-346">建议的配置： <strong> 未配置</span><span class="sxs-lookup"><span data-stu-id="1ba40-346">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="1ba40-347">使用此策略设置控制在 BitLocker 恢复后启动 Windows 时是否刷新平台验证数据。</span><span class="sxs-lookup"><span data-stu-id="1ba40-347">Use this policy setting to control whether platform validation data is refreshed when Windows is started after BitLocker recovery.</span></span></p>
<p><span data-ttu-id="1ba40-348">如果启用此策略设置，则在 BitLocker 恢复后启动 Windows 时，将刷新平台验证数据。</span><span class="sxs-lookup"><span data-stu-id="1ba40-348">If you enable this policy setting, platform validation data are refreshed when Windows is started after BitLocker recovery.</span></span> <span data-ttu-id="1ba40-349">如果禁用此策略设置，则在 BitLocker 恢复后启动 Windows 时，不会刷新平台验证数据。</span><span class="sxs-lookup"><span data-stu-id="1ba40-349">If you disable this policy setting, platform validation data are not refreshed when Windows is started after BitLocker recovery.</span></span> <span data-ttu-id="1ba40-350">如果未配置此策略设置，则在 BitLocker 恢复后启动 Windows 时，将刷新平台验证数据。</span><span class="sxs-lookup"><span data-stu-id="1ba40-350">If you do not configure this policy setting, platform validation data are refreshed when Windows is started after BitLocker recovery.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1ba40-351">使用增强的引导配置数据验证配置文件</span><span class="sxs-lookup"><span data-stu-id="1ba40-351">Use enhanced Boot Configuration Data validation profile</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ba40-352">建议的配置： <strong> 未配置</span><span class="sxs-lookup"><span data-stu-id="1ba40-352">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="1ba40-353">通过此策略设置，你可以选择要在平台验证期间验证的特定引导配置数据（BCD）设置。</span><span class="sxs-lookup"><span data-stu-id="1ba40-353">This policy setting allows you to choose specific Boot Configuration Data (BCD) settings to verify during platform validation.</span></span></p>
<p><span data-ttu-id="1ba40-354">如果启用此策略设置，你可以添加其他设置，删除默认设置，或两者都删除。</span><span class="sxs-lookup"><span data-stu-id="1ba40-354">If you enable this policy setting, you can add additional settings, remove the default settings, or both.</span></span> <span data-ttu-id="1ba40-355">如果禁用此策略设置，计算机将还原到类似于 Windows 7 使用的默认 BCD 配置文件的 BCD 配置文件。</span><span class="sxs-lookup"><span data-stu-id="1ba40-355">If you disable this policy setting, the computer reverts to a BCD profile similar to the default BCD profile that is used by Windows 7.</span></span> <span data-ttu-id="1ba40-356">如果未配置此策略设置，计算机将验证默认 Windows BCD 设置。</span><span class="sxs-lookup"><span data-stu-id="1ba40-356">If you do not configure this policy setting, the computer verifies the default Windows BCD settings.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="1ba40-357">注意</span><span class="sxs-lookup"><span data-stu-id="1ba40-357">Note</span></span></strong><br/><p><span data-ttu-id="1ba40-358">当 BitLocker 使用针对平台和引导配置数据（BCD）完整性验证（由 " &quot; 允许安全启动以实现完整性验证" 策略定义）进行安全启动时 &quot; ，将 &quot; 忽略 "使用增强的引导配置数据验证配置文件 &quot; 策略"。</span><span class="sxs-lookup"><span data-stu-id="1ba40-358">When BitLocker uses Secure Boot for platform and Boot Configuration Data (BCD) integrity validation, as defined by the &quot;Allow Secure Boot for integrity validation&quot; policy, the &quot;Use enhanced Boot Configuration Data validation profile&quot; policy is ignored.</span></span></p>
</div>
<div>

</div>
<p><span data-ttu-id="1ba40-359">控制启动调试（0x16000010）的设置将始终经过验证，并且在提供的字段中包含时不起作用。</span><span class="sxs-lookup"><span data-stu-id="1ba40-359">The setting that controls boot debugging (0x16000010) is always validated and has no effect if it is included in the provided fields.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="1ba40-360">加密策略强制设置</span><span class="sxs-lookup"><span data-stu-id="1ba40-360">Encryption Policy Enforcement Settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ba40-361">建议的配置： <strong> 已启用</span><span class="sxs-lookup"><span data-stu-id="1ba40-361">Suggested configuration: <strong>Enabled</span></span></strong></p>
<p><span data-ttu-id="1ba40-362">使用此策略设置，可配置用户使用其操作系统驱动器的 MBAM 策略推迟的天数。</span><span class="sxs-lookup"><span data-stu-id="1ba40-362">Use this policy setting to configure the number of days that users can postpone complying with MBAM policies for their operating system drive.</span></span> <span data-ttu-id="1ba40-363">如果首次检测到操作系统不符合要求，则开始宽限期。</span><span class="sxs-lookup"><span data-stu-id="1ba40-363">The grace period begins when the operating system is first detected as noncompliant.</span></span> <span data-ttu-id="1ba40-364">此宽限期到期后，用户无法推迟所需操作或向其请求豁免。</span><span class="sxs-lookup"><span data-stu-id="1ba40-364">After this grace period expires, users cannot postpone the required action or request an exemption from it.</span></span></p>
<p><span data-ttu-id="1ba40-365">如果加密过程需要用户输入，则会显示一个对话框，用户在提供所需的信息之前无法关闭该对话框。</span><span class="sxs-lookup"><span data-stu-id="1ba40-365">If the encryption process requires user input, a dialog box appears that users cannot close until they provide the required information.</span></span></p>
<p><span data-ttu-id="1ba40-366">如果禁用或未配置此设置，则不强制用户遵守 MBAM 策略。</span><span class="sxs-lookup"><span data-stu-id="1ba40-366">If you disable or do not configure this setting, users are not forced to comply with MBAM policies.</span></span></p>
<p><span data-ttu-id="1ba40-367">如果无需用户交互即可添加保护程序，则在宽限期到期后，加密将在后台开始。</span><span class="sxs-lookup"><span data-stu-id="1ba40-367">If no user interaction is required to add a protector, encryption begins in the background after the grace period expires.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1ba40-368">配置预启动恢复消息和 URL</span><span class="sxs-lookup"><span data-stu-id="1ba40-368">Configure pre-boot recovery message and URL</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ba40-369">建议的配置： <strong> 未配置</span><span class="sxs-lookup"><span data-stu-id="1ba40-369">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="1ba40-370">启用此策略设置可配置自定义恢复消息，或指定在操作系统驱动器锁定时在预启动 BitLocker 恢复屏幕上显示的 URL。</span><span class="sxs-lookup"><span data-stu-id="1ba40-370">Enable this policy setting to configure a custom recovery message or to specify a URL that is then displayed on the pre-boot BitLocker recovery screen when the OS drive is locked.</span></span> <span data-ttu-id="1ba40-371">此设置仅在运行 Windows 10 的客户端计算机上可用。</span><span class="sxs-lookup"><span data-stu-id="1ba40-371">This setting is only available on client computers running Windows 10.</span></span></p>
<p><span data-ttu-id="1ba40-372">如果启用此策略，你可以为预启动恢复消息选择以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="1ba40-372">When this policy is enabled, you can select one of these options for the pre-boot recovery message:</span></span></p>
<ul>
<li><p><strong><span data-ttu-id="1ba40-373">使用自定义恢复消息 </strong> ：选择此选项可在预启动 BitLocker 恢复屏幕中包含自定义消息。</span><span class="sxs-lookup"><span data-stu-id="1ba40-373">Use custom recovery message</strong>: Select this option to include a custom message in the pre-boot BitLocker recovery screen.</span></span> <span data-ttu-id="1ba40-374">在 " <strong> 自定义恢复消息" 选项 </strong> 框中，键入要显示的消息。</span><span class="sxs-lookup"><span data-stu-id="1ba40-374">In the <strong>Custom recovery message option</strong> box, type the message that you want displayed.</span></span> <span data-ttu-id="1ba40-375">如果你还希望指定恢复 URL，请将其包含在你的自定义恢复消息中。</span><span class="sxs-lookup"><span data-stu-id="1ba40-375">If you also want to specify a recovery URL, include it as part of your custom recovery message.</span></span></p></li>
<li><p><strong><span data-ttu-id="1ba40-376">使用自定义恢复 URL </strong> ：选择此选项可替换 "预启动 BitLocker 恢复" 屏幕中显示的默认 URL。</span><span class="sxs-lookup"><span data-stu-id="1ba40-376">Use custom recovery URL</strong>: Select this option to replace the default URL that is displayed in the pre-boot BitLocker recovery screen.</span></span> <span data-ttu-id="1ba40-377">在 " <strong> 自定义恢复 URL" 选项 </strong> 框中，键入要显示的 URL。</span><span class="sxs-lookup"><span data-stu-id="1ba40-377">In the <strong>Custom recovery URL option</strong> box, type the URL that you want displayed.</span></span></p></li>
<li><p><strong><span data-ttu-id="1ba40-378">使用默认的恢复消息和 URL </strong> ：选择此选项可在预启动 bitlocker 恢复屏幕中显示默认的 BitLocker 恢复消息和 url。</span><span class="sxs-lookup"><span data-stu-id="1ba40-378">Use default recovery message and URL</strong>: Select this option to display the default BitLocker recovery message and URL in the pre-boot BitLocker recovery screen.</span></span> <span data-ttu-id="1ba40-379">如果你以前配置了自定义恢复消息或 URL 并希望还原到默认消息，则必须启用此策略，然后选择 " <strong> 使用默认恢复消息和 URL" </strong> 选项。</span><span class="sxs-lookup"><span data-stu-id="1ba40-379">If you previously configured a custom recovery message or URL and want to revert to the default message, you must enable this policy and select the <strong>Use default recovery message and URL</strong> option.</span></span></p></li>
</ul>
<div class="alert">
<strong><span data-ttu-id="1ba40-380">注意</span><span class="sxs-lookup"><span data-stu-id="1ba40-380">Note</span></span></strong><br/><p><span data-ttu-id="1ba40-381">并非所有字符和语言都在预启动中受支持。</span><span class="sxs-lookup"><span data-stu-id="1ba40-381">Not all characters and languages are supported in pre-boot.</span></span> <span data-ttu-id="1ba40-382">我们建议你测试用于自定义消息或 URL 的字符是否正确显示在预启动 BitLocker 恢复屏幕上。</span><span class="sxs-lookup"><span data-stu-id="1ba40-382">We recommend that you test that the characters you use for the custom message or URL appear correctly on the pre-boot BitLocker recovery screen.</span></span></p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="1ba40-383">可移动驱动器组策略定义</span><span class="sxs-lookup"><span data-stu-id="1ba40-383">Removable Drive Group Policy definitions</span></span>

<span data-ttu-id="1ba40-384">本部分介绍了用于 Microsoft BitLocker 管理和监视以下 GPO 节点的可移动驱动器组策略定义：**计算机配置** &gt; **策略** &gt; **管理模板** &gt; **Windows 组件** &gt; **MDOP MBAM （BitLocker 管理）** &gt; **可移动驱动器**。</span><span class="sxs-lookup"><span data-stu-id="1ba40-384">This section describes Removable Drive Group Policy definitions for Microsoft BitLocker Administration and Monitoring at the following GPO node: **Computer Configuration** &gt; **Policies** &gt; **Administrative Templates** &gt; **Windows Components** &gt; **MDOP MBAM (BitLocker Management)** &gt; **Removable Drive**.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="1ba40-385">策略名称</span><span class="sxs-lookup"><span data-stu-id="1ba40-385">Policy name</span></span></th>
<th align="left"><span data-ttu-id="1ba40-386">概述和建议的组策略设置</span><span class="sxs-lookup"><span data-stu-id="1ba40-386">Overview and suggested Group Policy settings</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1ba40-387">控制可移动驱动器上的 BitLocker 的使用</span><span class="sxs-lookup"><span data-stu-id="1ba40-387">Control use of BitLocker on removable drives</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ba40-388">建议的配置： <strong> 已启用</span><span class="sxs-lookup"><span data-stu-id="1ba40-388">Suggested configuration: <strong>Enabled</span></span></strong></p>
<p><span data-ttu-id="1ba40-389">此策略控制对可移动数据驱动器使用 BitLocker。</span><span class="sxs-lookup"><span data-stu-id="1ba40-389">This policy controls the use of BitLocker on removable data drives.</span></span></p>
<p><span data-ttu-id="1ba40-390">单击 " <strong> 允许用户对可移动数据驱动器应用 bitlocker 保护" </strong> ，以允许用户在可移动数据驱动器上运行 bitlocker 设置向导。</span><span class="sxs-lookup"><span data-stu-id="1ba40-390">Click <strong>Allow users to apply BitLocker protection on removable data drives</strong> to allow users to run the BitLocker setup wizard on a removable data drive.</span></span></p>
<p><span data-ttu-id="1ba40-391">单击 " <strong> 允许用户暂停和解密可移动数据驱动器上的 bitlocker"， </strong> 以使用户能够从驱动器中删除 bitlocker 驱动器加密，或者在执行维护时暂停加密。</span><span class="sxs-lookup"><span data-stu-id="1ba40-391">Click <strong>Allow users to suspend and decrypt BitLocker on removable data drives</strong> to enable users to remove BitLocker drive encryption from the drive or to suspend the encryption while maintenance is performed.</span></span></p>
<p><span data-ttu-id="1ba40-392">如果启用此策略，并且单击 " <strong> 允许用户对可移动数据驱动器应用 BitLocker 保护" </strong> ，MBAM 客户端会将可移动驱动器的恢复信息保存到 MBAM 密钥恢复服务器，并允许用户在密码丢失时恢复驱动器。</span><span class="sxs-lookup"><span data-stu-id="1ba40-392">When this policy is enabled, and you click <strong>Allow users to apply BitLocker protection on removable data drives</strong>, the MBAM Client saves the recovery information about removable drives to the MBAM key recovery server and allows users to recover the drive if the password is lost.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="1ba40-393">拒绝对不受 BitLocker 保护的可移动驱动器的写访问</span><span class="sxs-lookup"><span data-stu-id="1ba40-393">Deny write access to removable drives not protected by BitLocker</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ba40-394">建议的配置： <strong> 未配置</span><span class="sxs-lookup"><span data-stu-id="1ba40-394">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="1ba40-395">启用此策略以仅允许受 BitLocker 保护的驱动器的写入权限。</span><span class="sxs-lookup"><span data-stu-id="1ba40-395">Enable this policy to allow only write permission to BitLocker-protected drives.</span></span></p>
<p><span data-ttu-id="1ba40-396">如果启用此策略，则在允许写入权限之前，计算机上的所有可移动数据驱动器都需要加密。</span><span class="sxs-lookup"><span data-stu-id="1ba40-396">When this policy is enabled, all removable data drives on the computer require encryption before write permission is allowed.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1ba40-397">允许从早期版本的 Windows 访问受 BitLocker 保护的可移动驱动器</span><span class="sxs-lookup"><span data-stu-id="1ba40-397">Allow access to BitLocker-protected removable drives from earlier versions of Windows</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ba40-398">建议的配置： <strong> 未配置</span><span class="sxs-lookup"><span data-stu-id="1ba40-398">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="1ba40-399">启用此策略以允许在运行 Windows Server 2008、Windows Vista、Windows XP SP3 或 Windows XP SP2 的计算机上解除锁定和查看具有 FAT 文件系统的固定驱动器。</span><span class="sxs-lookup"><span data-stu-id="1ba40-399">Enable this policy to allow fixed drives with the FAT file system to be unlocked and viewed on computers that are running Windows Server 2008, Windows Vista, Windows XP with SP3, or Windows XP with SP2.</span></span></p>
<p><span data-ttu-id="1ba40-400">如果未配置此策略，则可以在运行 Windows Server 2008、Windows Vista、windows XP SP3 或具有 SP2 的 Windows XP 的计算机上解锁具有 FAT 文件系统格式的可移动驱动器，并且可以查看其内容。</span><span class="sxs-lookup"><span data-stu-id="1ba40-400">When this policy is not configured, removable drives that are formatted with the FAT file system can be unlocked on computers that are running Windows Server 2008, Windows Vista, Windows XP with SP3, or Windows XP with SP2, and their content can be viewed.</span></span> <span data-ttu-id="1ba40-401">这些操作系统对受 BitLocker 保护的驱动器具有只读权限。</span><span class="sxs-lookup"><span data-stu-id="1ba40-401">These operating systems have read-only permission to BitLocker-protected drives.</span></span></p>
<p><span data-ttu-id="1ba40-402">禁用策略时，无法解锁用 FAT 文件系统格式化的可移动驱动器，并且无法在运行 Windows Server 2008、Windows Vista、Windows XP SP3 或 Windows XP SP2 的计算机上查看其内容。</span><span class="sxs-lookup"><span data-stu-id="1ba40-402">When the policy is disabled, removable drives formatted with the FAT file system cannot be unlocked and their content cannot be viewed on computers that are running Windows Server 2008, Windows Vista, Windows XP with SP3, or Windows XP with SP2.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="1ba40-403">为可移动数据驱动器配置密码的使用</span><span class="sxs-lookup"><span data-stu-id="1ba40-403">Configure use of password for removable data drives</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ba40-404">建议的配置： <strong> 未配置</span><span class="sxs-lookup"><span data-stu-id="1ba40-404">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="1ba40-405">启用此策略以在可移动数据驱动器上配置密码保护。</span><span class="sxs-lookup"><span data-stu-id="1ba40-405">Enable this policy to configure password protection on removable data drives.</span></span></p>
<p><span data-ttu-id="1ba40-406">如果未配置此策略，则密码支持的默认设置（不包括密码复杂性要求），并且不需要八个字符。</span><span class="sxs-lookup"><span data-stu-id="1ba40-406">When this policy is not configured, passwords are supported with the default settings, which do not include password complexity requirements and which require only eight characters.</span></span></p>
<p><span data-ttu-id="1ba40-407">为了提高安全性，你可以启用此策略，并选择 <strong> "需要密码以使用可移动数据驱动器 </strong> "，单击 " <strong> 需要密码复杂性 </strong> "，然后设置首选的 <strong> 最小密码长度 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="1ba40-407">For increased security, you can enable this policy and select <strong>Require password for removable data drive</strong>, click <strong>Require password complexity</strong>, and set the preferred <strong>minimum password length</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1ba40-408">选择可以如何恢复受 BitLocker 保护的可移动驱动器</span><span class="sxs-lookup"><span data-stu-id="1ba40-408">Choose how BitLocker-protected removable drives can be recovered</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ba40-409">建议的配置： <strong> 未配置</span><span class="sxs-lookup"><span data-stu-id="1ba40-409">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="1ba40-410">将此策略配置为启用 BitLocker 数据恢复代理或将 BitLocker 恢复信息保存到 Active Directory 域服务（AD DS）。</span><span class="sxs-lookup"><span data-stu-id="1ba40-410">Configure this policy to enable the BitLocker data recovery agent or to save BitLocker recovery information to Active Directory Domain Services (AD DS).</span></span></p>
<p><span data-ttu-id="1ba40-411">如果设置为 <strong> "未配置" </strong> ，则允许数据恢复代理，并且不会将恢复信息备份到 AD DS。</span><span class="sxs-lookup"><span data-stu-id="1ba40-411">When set to <strong>Not Configured</strong>, the data recovery agent is allowed, and recovery information is not backed up to AD DS.</span></span></p>
<p><span data-ttu-id="1ba40-412">MBAM 操作不需要将恢复信息备份到 AD DS。</span><span class="sxs-lookup"><span data-stu-id="1ba40-412">MBAM operation does not require recovery information to be backed up to AD DS.</span></span></p></td>
</tr>
</tbody>
</table>




## <span data-ttu-id="1ba40-413">相关主题</span><span class="sxs-lookup"><span data-stu-id="1ba40-413">Related topics</span></span>


[<span data-ttu-id="1ba40-414">为 MBAM 2.5 准备你的环境</span><span class="sxs-lookup"><span data-stu-id="1ba40-414">Preparing your Environment for MBAM 2.5</span></span>](preparing-your-environment-for-mbam-25.md)

[<span data-ttu-id="1ba40-415">MBAM 2.5 部署先决条件</span><span class="sxs-lookup"><span data-stu-id="1ba40-415">MBAM 2.5 Deployment Prerequisites</span></span>](mbam-25-deployment-prerequisites.md)


## <span data-ttu-id="1ba40-416">已获得 MBAM 的建议？</span><span class="sxs-lookup"><span data-stu-id="1ba40-416">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="1ba40-417">在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="1ba40-417">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="1ba40-418">对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="1ba40-418">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>






