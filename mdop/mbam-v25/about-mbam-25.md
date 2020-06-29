---
title: 关于 MBAM 2.5
description: 关于 MBAM 2.5
author: dansimp
ms.assetid: 1ce218ec-4d2e-4a75-8d1a-68d737a8f3c9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: d4c9ff0bc5ee3f7dc51a56cc428081a7c3783694
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803523"
---
# <span data-ttu-id="eaec9-103">关于 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="eaec9-103">About MBAM 2.5</span></span>


<span data-ttu-id="eaec9-104">Microsoft BitLocker 管理和监视（MBAM）2.5 为 BitLocker 驱动器加密提供简化的管理接口。</span><span class="sxs-lookup"><span data-stu-id="eaec9-104">Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 provides a simplified administrative interface for BitLocker Drive Encryption.</span></span> <span data-ttu-id="eaec9-105">对于丢失或被盗的计算机，BitLocker 提供增强的防护功能，防止数据失窃或数据暴露。</span><span class="sxs-lookup"><span data-stu-id="eaec9-105">BitLocker offers enhanced protection against data theft or data exposure for computers that are lost or stolen.</span></span> <span data-ttu-id="eaec9-106">BitLocker 将加密存储在 Windows 操作系统卷、驱动器和已配置数据驱动器上的所有数据。</span><span class="sxs-lookup"><span data-stu-id="eaec9-106">BitLocker encrypts all data that is stored on the Windows operating system volumes and drives and configured data drives.</span></span>

## <span data-ttu-id="eaec9-107">MBAM 概述</span><span class="sxs-lookup"><span data-stu-id="eaec9-107">Overview of MBAM</span></span>


<span data-ttu-id="eaec9-108">MBAM 2.5 具有以下功能：</span><span class="sxs-lookup"><span data-stu-id="eaec9-108">MBAM 2.5 has the following features:</span></span>

-   <span data-ttu-id="eaec9-109">使管理员能够自动对企业内的客户端计算机上的卷进行加密的过程。</span><span class="sxs-lookup"><span data-stu-id="eaec9-109">Enables administrators to automate the process of encrypting volumes on client computers across the enterprise.</span></span>

-   <span data-ttu-id="eaec9-110">使安全监察官能够快速确定单个计算机或甚至企业本身的合规性状态。</span><span class="sxs-lookup"><span data-stu-id="eaec9-110">Enables security officers to quickly determine the compliance state of individual computers or even of the enterprise itself.</span></span>

-   <span data-ttu-id="eaec9-111">通过 Microsoft System Center Configuration Manager 提供集中报告和硬件管理。</span><span class="sxs-lookup"><span data-stu-id="eaec9-111">Provides centralized reporting and hardware management with Microsoft System Center Configuration Manager.</span></span>

-   <span data-ttu-id="eaec9-112">减少了帮助台上的工作负荷，帮助最终用户提供 BitLocker PIN 和恢复密钥请求。</span><span class="sxs-lookup"><span data-stu-id="eaec9-112">Reduces the workload on the Help Desk to assist end users with BitLocker PIN and recovery key requests.</span></span>

-   <span data-ttu-id="eaec9-113">使最终用户能够使用自助服务门户单独恢复加密的设备。</span><span class="sxs-lookup"><span data-stu-id="eaec9-113">Enables end users to recover encrypted devices independently by using the Self-Service Portal.</span></span>

-   <span data-ttu-id="eaec9-114">使安全专员能够轻松审核 access 以恢复密钥信息。</span><span class="sxs-lookup"><span data-stu-id="eaec9-114">Enables security officers to easily audit access to recover key information.</span></span>

-   <span data-ttu-id="eaec9-115">使 Windows 企业用户能够在任何位置继续工作，确保其企业数据受到保护。</span><span class="sxs-lookup"><span data-stu-id="eaec9-115">Empowers Windows Enterprise users to continue working anywhere with the assurance that their corporate data is protected.</span></span>

<span data-ttu-id="eaec9-116">MBAM 强制执行你为你的企业设置的 BitLocker 加密策略选项，监视客户端计算机与这些策略的合规性，并报告企业和个人计算机的加密状态。</span><span class="sxs-lookup"><span data-stu-id="eaec9-116">MBAM enforces the BitLocker encryption policy options that you set for your enterprise, monitors the compliance of client computers with those policies, and reports on the encryption status of the enterprise’s and individual’s computers.</span></span> <span data-ttu-id="eaec9-117">此外，MBAM 允许你在用户忘记其 PIN 或密码时，或者在其 BIOS 或启动记录发生更改时访问恢复密钥信息。</span><span class="sxs-lookup"><span data-stu-id="eaec9-117">In addition, MBAM lets you access the recovery key information when users forget their PIN or password, or when their BIOS or boot records change.</span></span>

<span data-ttu-id="eaec9-118">以下组可能对使用 MBAM 管理 BitLocker 感兴趣：</span><span class="sxs-lookup"><span data-stu-id="eaec9-118">The following groups might be interested in using MBAM to manage BitLocker:</span></span>

-   <span data-ttu-id="eaec9-119">管理员、IT 安全专家和合规性监察官负责确保机密数据在未经授权的情况下不公开</span><span class="sxs-lookup"><span data-stu-id="eaec9-119">Administrators, IT security professionals, and compliance officers who are responsible for ensuring that confidential data is not disclosed without authorization</span></span>

-   <span data-ttu-id="eaec9-120">负责远程或分支办公室中的计算机安全的管理员</span><span class="sxs-lookup"><span data-stu-id="eaec9-120">Administrators who are responsible for computer security in remote or branch offices</span></span>

-   <span data-ttu-id="eaec9-121">负责运行 Windows 的客户端计算机的管理员</span><span class="sxs-lookup"><span data-stu-id="eaec9-121">Administrators who are responsible for client computers that are running Windows</span></span>

<span data-ttu-id="eaec9-122">**注意** 在本 MBAM 文档中不详细介绍 BitLocker。</span><span class="sxs-lookup"><span data-stu-id="eaec9-122">**Note** BitLocker is not explained in detail in this MBAM documentation.</span></span> <span data-ttu-id="eaec9-123">有关详细信息，请参阅[BitLocker 驱动器加密概述](https://go.microsoft.com/fwlink/p/?LinkId=225013)。</span><span class="sxs-lookup"><span data-stu-id="eaec9-123">For more information, see [BitLocker Drive Encryption Overview](https://go.microsoft.com/fwlink/p/?LinkId=225013).</span></span>

 

## <a href="" id="what-s-new-in-mbam-2-5"></a><span data-ttu-id="eaec9-124">MBAM 2.5 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="eaec9-124">What’s new in MBAM 2.5</span></span>


<span data-ttu-id="eaec9-125">本部分介绍 MBAM 2.5 中的新增功能。</span><span class="sxs-lookup"><span data-stu-id="eaec9-125">This section describes the new features in MBAM 2.5.</span></span>

### <span data-ttu-id="eaec9-126">Microsoft SQL Server 2014 支持</span><span class="sxs-lookup"><span data-stu-id="eaec9-126">Support for Microsoft SQL Server 2014</span></span>

<span data-ttu-id="eaec9-127">MBAM 还将添加对 Microsoft SQL Server 2014 的支持，以及早期版本的 MBAM 中支持的相同软件。</span><span class="sxs-lookup"><span data-stu-id="eaec9-127">MBAM adds support for Microsoft SQL Server 2014, in addition to the same software that is supported in earlier versions of MBAM.</span></span>

### <a href="" id="-------------mbam-group-policy-templates-downloaded-separately"></a> <span data-ttu-id="eaec9-128">MBAM 单独下载的组策略模板</span><span class="sxs-lookup"><span data-stu-id="eaec9-128">MBAM Group Policy Templates downloaded separately</span></span>

<span data-ttu-id="eaec9-129">MBAM 组策略模板必须从 MBAM 安装中单独下载。</span><span class="sxs-lookup"><span data-stu-id="eaec9-129">The MBAM Group Policy Templates must be downloaded separately from the MBAM installation.</span></span> <span data-ttu-id="eaec9-130">在早期版本的 MBAM 中，MBAM 安装程序包括一个 MBAM 策略模板，该模板包含用于定义 BitLocker 驱动器加密 MBAM 实现设置的所需的特定 MBAM 组策略对象（Gpo）。</span><span class="sxs-lookup"><span data-stu-id="eaec9-130">In previous versions of MBAM, the MBAM installer included an MBAM Policy Template, which contained the required MBAM-specific Group Policy Objects (GPOs) that define MBAM implementation settings for BitLocker Drive Encryption.</span></span> <span data-ttu-id="eaec9-131">这些 Gpo 已从 MBAM 安装程序中删除。</span><span class="sxs-lookup"><span data-stu-id="eaec9-131">These GPOs have been removed from the MBAM installer.</span></span> <span data-ttu-id="eaec9-132">现在，你可以在开始 MBAM 客户端安装之前，从[如何获取受 MDOP 组策略（admx）的模板](https://go.microsoft.com/fwlink/p/?LinkId=393941)并将其复制到服务器或工作站。</span><span class="sxs-lookup"><span data-stu-id="eaec9-132">You now download the GPOs from [How to Get MDOP Group Policy (.admx) Templates](https://go.microsoft.com/fwlink/p/?LinkId=393941) and copy them to a server or workstation before you begin the MBAM Client installation.</span></span> <span data-ttu-id="eaec9-133">你可以将组策略模板复制到运行受支持的 Windows Server 或 Windows 操作系统版本的任何服务器或工作站。</span><span class="sxs-lookup"><span data-stu-id="eaec9-133">You can copy the Group Policy Templates to any server or workstation that is running a supported version of the Windows Server or Windows operating system.</span></span>

<span data-ttu-id="eaec9-134">**重要提示** 请勿更改**BitLocker 驱动器加密**节点中的组策略设置，否则 MBAM 将无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="eaec9-134">**Important** Do not change the Group Policy settings in the **BitLocker Drive Encryption** node, or MBAM will not work correctly.</span></span> <span data-ttu-id="eaec9-135">在**MDOP MBAM （BitLocker Management）** 节点中配置组策略设置时，MBAM 会自动为你配置 BitLocker 驱动器加密设置。</span><span class="sxs-lookup"><span data-stu-id="eaec9-135">When you configure the Group Policy settings in the **MDOP MBAM (BitLocker Management)** node, MBAM automatically configures the BitLocker Drive Encryption settings for you.</span></span>

 

<span data-ttu-id="eaec9-136">需要复制到服务器或工作站的模板文件如下所示：</span><span class="sxs-lookup"><span data-stu-id="eaec9-136">The template files that you need to copy to a server or workstation are:</span></span>

-   <span data-ttu-id="eaec9-137">BitLockerManagement adml</span><span class="sxs-lookup"><span data-stu-id="eaec9-137">BitLockerManagement.adml</span></span>

-   <span data-ttu-id="eaec9-138">BitLockerManagement</span><span class="sxs-lookup"><span data-stu-id="eaec9-138">BitLockerManagement.admx</span></span>

-   <span data-ttu-id="eaec9-139">BitLockerUserManagement adml</span><span class="sxs-lookup"><span data-stu-id="eaec9-139">BitLockerUserManagement.adml</span></span>

-   <span data-ttu-id="eaec9-140">BitLockerUserManagement</span><span class="sxs-lookup"><span data-stu-id="eaec9-140">BitLockerUserManagement.admx</span></span>

<span data-ttu-id="eaec9-141">将模板文件复制到最适合你的需求的位置。</span><span class="sxs-lookup"><span data-stu-id="eaec9-141">Copy the template files to the location that best meets your needs.</span></span> <span data-ttu-id="eaec9-142">对于必须复制到特定于语言的文件夹的语言特定文件，需要使用组策略管理控制台查看文件。</span><span class="sxs-lookup"><span data-stu-id="eaec9-142">For the language-specific files, which must be copied to a language-specific folder, the Group Policy Management Console is required to view the files.</span></span>

- <span data-ttu-id="eaec9-143">若要在服务器或工作站本地安装模板文件，请将文件复制到以下位置之一。</span><span class="sxs-lookup"><span data-stu-id="eaec9-143">To install the template files locally on a server or workstation, copy the files to one of the following locations.</span></span>

  <table>
  <colgroup>
  <col width="50%" />
  <col width="50%" />
  </colgroup>
  <thead>
  <tr class="header">
  <th align="left"><span data-ttu-id="eaec9-144">文件类型</span><span class="sxs-lookup"><span data-stu-id="eaec9-144">File type</span></span></th>
  <th align="left"><span data-ttu-id="eaec9-145">文件位置</span><span class="sxs-lookup"><span data-stu-id="eaec9-145">File location</span></span></th>
  </tr>
  </thead>
  <tbody>
  <tr class="odd">
  <td align="left"><p><span data-ttu-id="eaec9-146">非特定语言（admx）</span><span class="sxs-lookup"><span data-stu-id="eaec9-146">language neutral (.admx)</span></span></p></td>
  <td align="left"><p><em><span data-ttu-id="eaec9-147">% systemroot% </em> \policyDefinitions</span><span class="sxs-lookup"><span data-stu-id="eaec9-147">%systemroot%</em>\policyDefinitions</span></span></p></td>
  </tr>
  <tr class="even">
  <td align="left"><p><span data-ttu-id="eaec9-148">特定语言（adml）</span><span class="sxs-lookup"><span data-stu-id="eaec9-148">language specific (.adml)</span></span></p></td>
  <td align="left"><p><em><span data-ttu-id="eaec9-149">% systemroot% </em> \policyDefinitions [ <em> MUIculture </em> ] （例如，美国英语语言特定的文件将存储在 <em> % systemroot% &lt; /em &gt; policyDefinitions\en-us）中</span><span class="sxs-lookup"><span data-stu-id="eaec9-149">%systemroot%</em>\policyDefinitions[<em>MUIculture</em>] (for example, the U.S. English language specific file will be stored in <em>%systemroot%&lt;/em&gt;policyDefinitions\en-us)</span></span></p></td>
  </tr>
  </tbody>
  </table>

     

- <span data-ttu-id="eaec9-150">若要使模板对域中的所有组策略管理员可用，请将文件复制到域控制器上的以下位置之一。</span><span class="sxs-lookup"><span data-stu-id="eaec9-150">To make the templates available to all Group Policy administrators in a domain, copy the files to one of the following locations on a domain controller.</span></span>

  <table>
  <colgroup>
  <col width="50%" />
  <col width="50%" />
  </colgroup>
  <thead>
  <tr class="header">
  <th align="left"><span data-ttu-id="eaec9-151">文件类型</span><span class="sxs-lookup"><span data-stu-id="eaec9-151">File type</span></span></th>
  <th align="left"><span data-ttu-id="eaec9-152">域控制器文件位置</span><span class="sxs-lookup"><span data-stu-id="eaec9-152">Domain controller file location</span></span></th>
  </tr>
  </thead>
  <tbody>
  <tr class="odd">
  <td align="left"><p><span data-ttu-id="eaec9-153">非特定语言（admx）</span><span class="sxs-lookup"><span data-stu-id="eaec9-153">Language neutral (.admx)</span></span></p></td>
  <td align="left"><p><em><span data-ttu-id="eaec9-154">% systemroot% </em> sysvol\domain\policies\PolicyDefinitions</span><span class="sxs-lookup"><span data-stu-id="eaec9-154">%systemroot%</em>sysvol\domain\policies\PolicyDefinitions</span></span></p></td>
  </tr>
  <tr class="even">
  <td align="left"><p><span data-ttu-id="eaec9-155">特定语言（adml）</span><span class="sxs-lookup"><span data-stu-id="eaec9-155">Language specific (.adml)</span></span></p></td>
  <td align="left"><p><em><span data-ttu-id="eaec9-156">% systemroot% </em> \sysvol\domain\policies\PolicyDefinitions [ <em> MUIculture </em> ] （例如，美国英语语言特定的文件将存储在 <em> % systemroot% </em> \sysvol\domain\policies\PolicyDefinitions\en-us）中</span><span class="sxs-lookup"><span data-stu-id="eaec9-156">%systemroot%</em>\sysvol\domain\policies\PolicyDefinitions[<em>MUIculture</em>] (for example, the U.S. English language-specific file will be stored in <em>%systemroot%</em>\sysvol\domain\policies\PolicyDefinitions\en-us)</span></span></p></td>
  </tr>
  </tbody>
  </table>

     

<span data-ttu-id="eaec9-157">有关模板文件的详细信息，请参阅[管理组策略 ADMX 文件分步指南](https://go.microsoft.com/fwlink/?LinkId=392818)。</span><span class="sxs-lookup"><span data-stu-id="eaec9-157">For more information about template files, see [Managing Group Policy ADMX Files Step-by-Step Guide](https://go.microsoft.com/fwlink/?LinkId=392818).</span></span>

### <span data-ttu-id="eaec9-158">对操作系统和固定数据驱动器实施加密策略的能力</span><span class="sxs-lookup"><span data-stu-id="eaec9-158">Ability to enforce encryption policies on operating system and fixed data drives</span></span>

<span data-ttu-id="eaec9-159">MBAM 2.5 使你能够在你的组织中对计算机的操作系统和固定数据驱动器强制执行加密策略，并限制最终用户可以请求达到符合 MBAM 加密策略要求的延迟的天数。</span><span class="sxs-lookup"><span data-stu-id="eaec9-159">MBAM2.5 enables you to enforce encryption policies on operating system and fixed data drives for computers in your organization and limit the number of days that end users can request a postponement of the requirement to comply with MBAM encryption policies.</span></span>

<span data-ttu-id="eaec9-160">为使你能够配置加密策略强制，已为操作系统驱动器和固定数据驱动器添加了新的组策略设置，称为加密策略强制设置。</span><span class="sxs-lookup"><span data-stu-id="eaec9-160">To enable you to configure encryption policy enforcement, a new Group Policy setting, called Encryption Policy Enforcement Settings, has been added for operating system drives and fixed data drives.</span></span> <span data-ttu-id="eaec9-161">下表中介绍了此策略。</span><span class="sxs-lookup"><span data-stu-id="eaec9-161">This policy is described in the following table.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="eaec9-162">组策略设置</span><span class="sxs-lookup"><span data-stu-id="eaec9-162">Group Policy setting</span></span></th>
<th align="left"><span data-ttu-id="eaec9-163">描述</span><span class="sxs-lookup"><span data-stu-id="eaec9-163">Description</span></span></th>
<th align="left"><span data-ttu-id="eaec9-164">用于配置此设置的组策略节点</span><span class="sxs-lookup"><span data-stu-id="eaec9-164">Group Policy node used to configure this setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="eaec9-165">加密策略强制设置（操作系统驱动器）</span><span class="sxs-lookup"><span data-stu-id="eaec9-165">Encryption Policy Enforcement Settings (Operating System Drive)</span></span></p></td>
<td align="left"><p><span data-ttu-id="eaec9-166">对于此设置，使用选项 <strong> 配置操作系统驱动器配置宽限期的不符合的宽限期间天数 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="eaec9-166">For this setting, use the option <strong>Configure the number of noncompliance grace period days for operating system drives</strong> to configure a grace period.</span></span></p>
<p><span data-ttu-id="eaec9-167">宽限期指定最终用户在第一次检测到驱动器为不符合的情况后，可为其操作系统驱动器推迟遵守 MBAM 策略的天数。</span><span class="sxs-lookup"><span data-stu-id="eaec9-167">The grace period specifies the number of days that end users can postpone compliance with MBAM policies for their operating system drive after the drive is first detected as noncompliant.</span></span></p>
<p><span data-ttu-id="eaec9-168">在配置的宽限期到期后，用户无法推迟所需操作或向其请求豁免。</span><span class="sxs-lookup"><span data-stu-id="eaec9-168">After the configured grace period expires, users cannot postpone the required action or request an exemption from it.</span></span></p>
<p><span data-ttu-id="eaec9-169">如果需要用户交互（例如，如果你使用的是受信任的平台模块（TPM） + PIN 或使用密码保护程序），则会显示一个对话框，并且用户在提供所需的信息之前无法关闭它。</span><span class="sxs-lookup"><span data-stu-id="eaec9-169">If user interaction is required (for example, if you are using the Trusted Platform Module (TPM) + PIN or using a password protector), a dialog box appears, and users cannot close it until they provide the required information.</span></span> <span data-ttu-id="eaec9-170">如果保护程序仅 TPM，则在后台立即开始加密，无需用户输入。</span><span class="sxs-lookup"><span data-stu-id="eaec9-170">If the protector is TPM only, encryption begins immediately in the background without user input.</span></span></p>
<p><span data-ttu-id="eaec9-171">用户无法通过 BitLocker 加密向导请求豁免。</span><span class="sxs-lookup"><span data-stu-id="eaec9-171">Users cannot request exemptions through the BitLocker encryption wizard.</span></span> <span data-ttu-id="eaec9-172">他们必须联系技术支持人员或使用其组织为豁免请求所使用的任何流程。</span><span class="sxs-lookup"><span data-stu-id="eaec9-172">Instead, they must contact their Help Desk or use whatever process their organization uses for exemption requests.</span></span></p></td>
<td align="left"><p><span data-ttu-id="eaec9-173">计算机配置 &gt; 策略 &gt; 管理模板 &gt; WINDOWS 组件 &gt; MDOP MBAM （BitLocker 管理） &gt; 操作系统驱动器</span><span class="sxs-lookup"><span data-stu-id="eaec9-173">Computer Configuration &gt; Policies &gt; Administrative Templates &gt; Windows Components &gt; MDOP MBAM (BitLocker Management) &gt; Operating System Drive</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="eaec9-174">加密策略强制设置（固定数据驱动器）</span><span class="sxs-lookup"><span data-stu-id="eaec9-174">Encryption Policy Enforcement Settings (Fixed Data Drives)</span></span></p></td>
<td align="left"><p><span data-ttu-id="eaec9-175">对于此设置，请使用选项 <strong> 配置固定驱动器的不符合的宽限期间天数 </strong> 以配置宽限期。</span><span class="sxs-lookup"><span data-stu-id="eaec9-175">For this setting, use the option <strong>Configure the number of noncompliance grace period days for fixed drives</strong> to configure a grace period.</span></span></p>
<p><span data-ttu-id="eaec9-176">宽限期指定在第一次检测到驱动器为不兼容后，最终用户可以为其固定驱动器推迟遵守 MBAM 策略的天数。</span><span class="sxs-lookup"><span data-stu-id="eaec9-176">The grace period specifies the number of days that end users can postpone compliance with MBAM policies for their fixed drive after the drive is first detected as noncompliant.</span></span></p>
<p><span data-ttu-id="eaec9-177">当固定驱动器被确定为不相容时，宽限期开始。</span><span class="sxs-lookup"><span data-stu-id="eaec9-177">The grace period begins when the fixed drive is determined to be noncompliant.</span></span> <span data-ttu-id="eaec9-178">如果您使用的是自动解锁，则在操作系统驱动器符合要求之前，不会强制执行该策略。</span><span class="sxs-lookup"><span data-stu-id="eaec9-178">If you are using auto-unlock, the policy will not be enforced until the operating system drive is compliant.</span></span> <span data-ttu-id="eaec9-179">但是，如果未使用自动解锁，则可以在操作系统驱动器完全加密之前开始对固定数据驱动器加密。</span><span class="sxs-lookup"><span data-stu-id="eaec9-179">However, if you are not using auto-unlock, encryption of the fixed data drive can begin before the operating system drive is fully encrypted.</span></span></p>
<p><span data-ttu-id="eaec9-180">在配置的宽限期到期后，用户无法推迟所需操作或向其请求豁免。</span><span class="sxs-lookup"><span data-stu-id="eaec9-180">After the configured grace period expires, users cannot postpone the required action or request an exemption from it.</span></span> <span data-ttu-id="eaec9-181">如果需要用户交互，则会出现一个对话框，用户在提供所需的信息之前无法将其关闭。</span><span class="sxs-lookup"><span data-stu-id="eaec9-181">If user interaction is required, a dialog box appears and users cannot close it until they provide the required information.</span></span></p></td>
<td align="left"><p><span data-ttu-id="eaec9-182">计算机配置 &gt; 策略 &gt; 管理模板 &gt; WINDOWS 组件 &gt; MDOP MBAM （BitLocker Management）已 &gt; 修复的驱动器</span><span class="sxs-lookup"><span data-stu-id="eaec9-182">Computer Configuration &gt; Policies &gt; Administrative Templates &gt; Windows Components &gt; MDOP MBAM (BitLocker Management) &gt; Fixed Drive</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="eaec9-183">能够在 BitLocker 驱动器加密向导中提供 URL 以指向你的安全策略</span><span class="sxs-lookup"><span data-stu-id="eaec9-183">Ability to provide a URL in the BitLocker Drive Encryption wizard to point to your security policy</span></span>

<span data-ttu-id="eaec9-184">新的组策略设置，**提供 "安全策略" 链接的 url**，使你能够将呈现给最终用户的 url 配置为名为 "**公司安全策略**" 的链接。</span><span class="sxs-lookup"><span data-stu-id="eaec9-184">A new Group Policy setting, **Provide the URL for the Security Policy link**, enables you to configure a URL that will be presented to end users as a link called **Company Security Policy**.</span></span> <span data-ttu-id="eaec9-185">当 MBAM 提示用户加密卷时，将出现此链接。</span><span class="sxs-lookup"><span data-stu-id="eaec9-185">This link will appear when MBAM prompts users to encrypt a volume.</span></span>

<span data-ttu-id="eaec9-186">如果启用此策略设置，则可以配置 "**公司安全策略**" 链接的 URL。</span><span class="sxs-lookup"><span data-stu-id="eaec9-186">If you enable this policy setting, you can configure the URL for the **Company Security Policy** link.</span></span> <span data-ttu-id="eaec9-187">如果禁用或未配置此策略设置，则不会向用户显示**公司安全策略**链接。</span><span class="sxs-lookup"><span data-stu-id="eaec9-187">If you disable or do not configure this policy setting, the **Company Security Policy** link is not displayed to users.</span></span>

<span data-ttu-id="eaec9-188">新组策略设置位于以下 GPO 节点中：**计算机配置** &gt; **策略** &gt; **管理模板** &gt; **Windows 组件** &gt; **MDOP MBAM （BitLocker Management） &gt; 客户端管理**。</span><span class="sxs-lookup"><span data-stu-id="eaec9-188">The new Group Policy setting is located in the following GPO node: **Computer Configuration** &gt; **Policies** &gt; **Administrative Templates** &gt; **Windows Components** &gt; **MDOP MBAM (BitLocker Management) &gt; Client Management**.</span></span>

### <span data-ttu-id="eaec9-189">支持 FIPS 兼容的恢复密钥</span><span class="sxs-lookup"><span data-stu-id="eaec9-189">Support for FIPS-compliant recovery keys</span></span>

<span data-ttu-id="eaec9-190">MBAM 2.5 支持运行 Windows 8.1 操作系统的设备上的符合联邦信息处理标准（FIPS）的 BitLocker 恢复密钥。</span><span class="sxs-lookup"><span data-stu-id="eaec9-190">MBAM2.5 supports Federal Information Processing Standard (FIPS)-compliant BitLocker recovery keys on devices that are running the Windows8.1 operating system.</span></span> <span data-ttu-id="eaec9-191">在早期版本的 Windows 中，恢复密钥不兼容 FIPS。</span><span class="sxs-lookup"><span data-stu-id="eaec9-191">The recovery key was not FIPS compliant in earlier versions of Windows.</span></span> <span data-ttu-id="eaec9-192">此增强功能改进了需要 FIPS 合规的组织中的驱动器恢复过程，因为它使最终用户能够使用自助服务门户或管理和监视网站（帮助桌面）在忘记其 PIN 或密码或将其从计算机中锁定的情况下恢复其驱动器。</span><span class="sxs-lookup"><span data-stu-id="eaec9-192">This enhancement improves the drive recovery process in organizations that require FIPS compliance because it enables end users to use the Self-Service Portal or Administration and Monitoring Website (Help Desk) to recover their drives if they forget their PIN or password or get locked out of their computers.</span></span> <span data-ttu-id="eaec9-193">新的 FIPS 合规性功能不会扩展到密码保护器。</span><span class="sxs-lookup"><span data-stu-id="eaec9-193">The new FIPS compliance feature does not extend to password protectors.</span></span>

<span data-ttu-id="eaec9-194">若要在你的组织中启用 FIPS 合规性，必须配置联邦信息处理标准（FIPS）组策略设置。</span><span class="sxs-lookup"><span data-stu-id="eaec9-194">To enable FIPS compliance in your organization, you must configure the Federal Information Processing Standard (FIPS) Group Policy settings.</span></span> <span data-ttu-id="eaec9-195">有关配置说明，请参阅[BitLocker 组策略设置](https://go.microsoft.com/fwlink/?LinkId=393560)。</span><span class="sxs-lookup"><span data-stu-id="eaec9-195">For configuration instructions, see [BitLocker Group Policy Settings](https://go.microsoft.com/fwlink/?LinkId=393560).</span></span>

<span data-ttu-id="eaec9-196">对于运行 Windows8 或 Windows7 操作系统但未[安装 BitLocker 修补程序](https://support.microsoft.com/kb/3015477)的客户端计算机，IT 管理员将继续使用 FIPS 兼容的环境中的数据恢复代理（DRA）保护程序。</span><span class="sxs-lookup"><span data-stu-id="eaec9-196">For client computers that are running the Windows8 or Windows7 operating systems without the [installed BitLocker hotfix](https://support.microsoft.com/kb/3015477), IT administrators will continue to use the Data Recovery Agents (DRA) protector in FIPS-compliant environments.</span></span> <span data-ttu-id="eaec9-197">有关 DRA 的信息，请参阅将[数据恢复代理与 BitLocker 配合使用](https://go.microsoft.com/fwlink/?LinkId=393557)。</span><span class="sxs-lookup"><span data-stu-id="eaec9-197">For information about DRA, see [Using Data Recovery Agents with BitLocker](https://go.microsoft.com/fwlink/?LinkId=393557).</span></span>

<span data-ttu-id="eaec9-198">请参阅[Bitlocker 管理和监视2.5 的修补程序包 2](https://support.microsoft.com/kb/3015477) ，下载并安装适用于 windows 7 和 windows 8 计算机的 bitlocker 修补程序。</span><span class="sxs-lookup"><span data-stu-id="eaec9-198">See [Hotfix Package 2 for BitLocker Administration and Monitoring 2.5](https://support.microsoft.com/kb/3015477) to download and install the BitLocker hotfix for Windows 7 and Windows 8 computers.</span></span>

### <span data-ttu-id="eaec9-199">支持高可用性部署</span><span class="sxs-lookup"><span data-stu-id="eaec9-199">Support for high availability deployments</span></span>

<span data-ttu-id="eaec9-200">除了标准的两服务器和配置管理器集成拓扑之外，MBAM 还支持下列高可用性方案：</span><span class="sxs-lookup"><span data-stu-id="eaec9-200">MBAM supports the following high-availability scenarios in addition to the standard two-server and Configuration Manager Integration topologies:</span></span>

-   <span data-ttu-id="eaec9-201">SQL Server AlwaysOn 可用性组</span><span class="sxs-lookup"><span data-stu-id="eaec9-201">SQL Server AlwaysOn availability groups</span></span>

-   <span data-ttu-id="eaec9-202">SQL Server 群集</span><span class="sxs-lookup"><span data-stu-id="eaec9-202">SQL Server clustering</span></span>

-   <span data-ttu-id="eaec9-203">网络负载平衡（NLB）</span><span class="sxs-lookup"><span data-stu-id="eaec9-203">Network load balancing (NLB)</span></span>

-   <span data-ttu-id="eaec9-204">SQL Server 镜像</span><span class="sxs-lookup"><span data-stu-id="eaec9-204">SQL Server mirroring</span></span>

-   <span data-ttu-id="eaec9-205">卷影复制服务（VSS）备份</span><span class="sxs-lookup"><span data-stu-id="eaec9-205">Volume Shadow Copy Service (VSS) Backup</span></span>

<span data-ttu-id="eaec9-206">有关这些功能的详细信息，请参阅[规划 MBAM 2.5 高可用性](planning-for-mbam-25-high-availability.md)。</span><span class="sxs-lookup"><span data-stu-id="eaec9-206">For more information about these features, see [Planning for MBAM 2.5 High Availability](planning-for-mbam-25-high-availability.md).</span></span>

### <a href="" id="management-of-roles-for-administration-and-monitoring-website-changed-"></a><span data-ttu-id="eaec9-207">管理和监视网站的角色管理已更改</span><span class="sxs-lookup"><span data-stu-id="eaec9-207">Management of roles for Administration and Monitoring Website changed</span></span>

<span data-ttu-id="eaec9-208">在 MBAM 2.5 中，必须在 Active Directory 域服务（添加）中创建安全组，以管理提供对管理和监视网站的访问权限的角色。</span><span class="sxs-lookup"><span data-stu-id="eaec9-208">In MBAM2.5, you must create security groups in Active Directory Domain Services (ADDS) to manage the roles that provide access rights to the Administration and Monitoring Website.</span></span> <span data-ttu-id="eaec9-209">角色使特定安全组中的用户可以在网站中执行不同的任务，例如查看报表或帮助最终用户恢复加密的驱动器。</span><span class="sxs-lookup"><span data-stu-id="eaec9-209">Roles enable users who are in specific security groups to perform different tasks in the website such as viewing reports or helping end users recover encrypted drives.</span></span> <span data-ttu-id="eaec9-210">在早期版本的 MBAM 中，角色是使用本地组进行管理的。</span><span class="sxs-lookup"><span data-stu-id="eaec9-210">In previous versions of MBAM, roles were managed by using local groups.</span></span>

<span data-ttu-id="eaec9-211">在 MBAM 2.5 中，术语 "roles" 替换了早期版本的 MBAM 中使用的术语 "管理员角色"。</span><span class="sxs-lookup"><span data-stu-id="eaec9-211">In MBAM2.5, the term “roles” replaces the term “administrator roles,” which was used in earlier versions of MBAM.</span></span> <span data-ttu-id="eaec9-212">此外，在 MBAM 2.5 中，"MBAM 系统管理员" 角色已被删除。</span><span class="sxs-lookup"><span data-stu-id="eaec9-212">In addition, in MBAM2.5 the “MBAM System Administrators” role has been removed.</span></span>

<span data-ttu-id="eaec9-213">下表列出了必须在 AD DS 中创建的安全组。</span><span class="sxs-lookup"><span data-stu-id="eaec9-213">The following table lists the security groups that you must create in AD DS.</span></span> <span data-ttu-id="eaec9-214">你可以为安全组使用任何名称。</span><span class="sxs-lookup"><span data-stu-id="eaec9-214">You can use any name for the security groups.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="eaec9-215">角色</span><span class="sxs-lookup"><span data-stu-id="eaec9-215">Role</span></span></th>
<th align="left"><span data-ttu-id="eaec9-216">此角色在 "管理和监视" 网站上的访问权限</span><span class="sxs-lookup"><span data-stu-id="eaec9-216">Access rights for this role on the Administration and Monitoring Website</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="eaec9-217">MBAM 帮助台用户</span><span class="sxs-lookup"><span data-stu-id="eaec9-217">MBAM Helpdesk Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="eaec9-218">提供对 MBAM 管理和监视网站的 "管理 TPM 和驱动器恢复" 区域的访问权限。</span><span class="sxs-lookup"><span data-stu-id="eaec9-218">Provides access to the Manage TPM and Drive Recovery areas of the MBAM Administration and Monitoring Website.</span></span> <span data-ttu-id="eaec9-219">有权访问这些区域的用户在使用任一区域时都必须填写所有字段。</span><span class="sxs-lookup"><span data-stu-id="eaec9-219">Users who have access to these areas must fill in all fields when they use either area.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="eaec9-220">MBAM 报表用户</span><span class="sxs-lookup"><span data-stu-id="eaec9-220">MBAM Report Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="eaec9-221">提供对 "管理和监视" 网站中的报表的访问。</span><span class="sxs-lookup"><span data-stu-id="eaec9-221">Provides access to the Reports in the Administration and Monitoring Website.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="eaec9-222">MBAM 高级帮助台用户</span><span class="sxs-lookup"><span data-stu-id="eaec9-222">MBAM Advanced Helpdesk Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="eaec9-223">提供对管理和监控网站中的所有区域的访问权限。</span><span class="sxs-lookup"><span data-stu-id="eaec9-223">Provides access to all areas in the Administration and Monitoring Website.</span></span> <span data-ttu-id="eaec9-224">在帮助最终用户恢复其驱动器时，此组中的用户只需输入恢复密钥，而不是最终用户的域和用户名。</span><span class="sxs-lookup"><span data-stu-id="eaec9-224">Users in this group have to enter only the recovery key, not the end user’s domain and user name, when helping end users recover their drives.</span></span> <span data-ttu-id="eaec9-225">如果用户是 MBAM "支持人员" 组和 "MBAM 高级帮助台用户" 组的成员，则 MBAM "高级帮助台用户" 组权限将替代 "MBAM 帮助台用户" 组权限。</span><span class="sxs-lookup"><span data-stu-id="eaec9-225">If a user is a member of the MBAM Helpdesk Users group and the MBAM Advanced Helpdesk Users group, the MBAM Advanced Helpdesk Users group permissions override the MBAM Helpdesk Users group permissions.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="eaec9-226">在添加安全组后，将用户和/或组分配给相应的安全组，以启用对管理和监视网站的相应级别的访问权限。</span><span class="sxs-lookup"><span data-stu-id="eaec9-226">After you create the security groups in ADDS, assign users and/or groups to the appropriate security group to enable the corresponding level of access to the Administration and Monitoring Website.</span></span> <span data-ttu-id="eaec9-227">若要使具有每个角色的人员能够访问管理和监视网站，你还必须在配置管理和监视网站时指定每个安全组。</span><span class="sxs-lookup"><span data-stu-id="eaec9-227">To enable individuals with each role to access the Administration and Monitoring Website, you must also specify each security group when you are configuring the Administration and Monitoring Website.</span></span>

### <span data-ttu-id="eaec9-228">用于配置 MBAM Server 功能的 Windows PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="eaec9-228">Windows PowerShell cmdlets for configuring MBAM Server features</span></span>

<span data-ttu-id="eaec9-229">MBAM 2.5 的 Windows PowerShell cmdlet 使你能够配置和管理 MBAM 服务器功能。</span><span class="sxs-lookup"><span data-stu-id="eaec9-229">Windows PowerShell cmdlets for MBAM2.5 enable you to configure and manage the MBAM Server features.</span></span> <span data-ttu-id="eaec9-230">每个功能都有一个对应的 Windows PowerShell cmdlet，可用于启用或禁用功能，或获取有关该功能的信息。</span><span class="sxs-lookup"><span data-stu-id="eaec9-230">Each feature has a corresponding Windows PowerShell cmdlet that you can use to enable or disable features, or to get information about the feature.</span></span>

<span data-ttu-id="eaec9-231">有关使用 Windows PowerShell 的先决条件和先决条件，请参阅[使用 Windows Powershell 配置 MBAM 2.5 服务器功能](configuring-mbam-25-server-features-by-using-windows-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="eaec9-231">For prerequisites and prerequisites for using Windows PowerShell, see [Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md).</span></span>

**<span data-ttu-id="eaec9-232">在安装 MBAM 服务器软件后加载适用于 Windows PowerShell cmdlet 的 MBAM 2.5 帮助</span><span class="sxs-lookup"><span data-stu-id="eaec9-232">To load the MBAM 2.5 Help for Windows PowerShell cmdlets after installing the MBAM Server software</span></span>**

1.  <span data-ttu-id="eaec9-233">打开 Windows PowerShell 或 Windows PowerShell 集成脚本环境（ISE）。</span><span class="sxs-lookup"><span data-stu-id="eaec9-233">Open Windows PowerShell or Windows PowerShell Integrated Scripting Environment (ISE).</span></span>

2.  <span data-ttu-id="eaec9-234">类型**更新-帮助-MBAM**。</span><span class="sxs-lookup"><span data-stu-id="eaec9-234">Type **Update-Help –Module Microsoft.MBAM**.</span></span>

<span data-ttu-id="eaec9-235">适用于 MBAM 的 Windows PowerShell 帮助有以下格式：</span><span class="sxs-lookup"><span data-stu-id="eaec9-235">Windows PowerShell Help for MBAM is available in the following formats:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="eaec9-236">Windows PowerShell 帮助格式</span><span class="sxs-lookup"><span data-stu-id="eaec9-236">Windows PowerShell Help format</span></span></th>
<th align="left"><span data-ttu-id="eaec9-237">详细信息</span><span class="sxs-lookup"><span data-stu-id="eaec9-237">More information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="eaec9-238">在 Windows PowerShell 命令提示符处，键入 <strong> get-help </strong> &lt; <em> cmdlet</em>&gt;</span><span class="sxs-lookup"><span data-stu-id="eaec9-238">At a Windows PowerShell command prompt, type <strong>Get-Help</strong> &lt;<em>cmdlet</em>&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="eaec9-239">若要上载最新的 Windows PowerShell cmdlet，请按照上一节中关于如何加载 MBAM 的 Windows PowerShell 帮助中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="eaec9-239">To upload the latest Windows PowerShell cmdlets, follow the instructions in the previous section on how to load Windows PowerShell Help for MBAM.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="eaec9-240">在 TechNet 上作为网页</span><span class="sxs-lookup"><span data-stu-id="eaec9-240">On TechNet as webpages</span></span></p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=393498" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=393498">https://go.microsoft.com/fwlink/?LinkId=393498</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="eaec9-241">在下载中心中作为单词表文件</span><span class="sxs-lookup"><span data-stu-id="eaec9-241">On the Download Center as a Word .docx file</span></span></p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=393497" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=393497">https://go.microsoft.com/fwlink/?LinkId=393497</a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="eaec9-242">在下载中心中作为 .pdf 文件</span><span class="sxs-lookup"><span data-stu-id="eaec9-242">On the Download Center as a .pdf file</span></span></p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=393499" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=393499">https://go.microsoft.com/fwlink/?LinkId=393499</a></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="eaec9-243">支持仅限 ASCII 的和增强的 Pin，以及阻止顺序和重复字符的功能</span><span class="sxs-lookup"><span data-stu-id="eaec9-243">Support for ASCII-only and enhanced PINs and ability to prevent sequential and repeating characters</span></span>

**<span data-ttu-id="eaec9-244">允许启用 "启动" 组策略设置的增强引脚</span><span class="sxs-lookup"><span data-stu-id="eaec9-244">Allow enhanced PINs for startup Group Policy setting</span></span>**

<span data-ttu-id="eaec9-245">组策略设置，**允许使用增强的 pin 启动**，你可以配置是否将增强的启动 Pin 用于 BitLocker。</span><span class="sxs-lookup"><span data-stu-id="eaec9-245">The Group Policy setting, **Allow enhanced PINs for startup**, enables you to configure whether enhanced startup PINs are used with BitLocker.</span></span> <span data-ttu-id="eaec9-246">增强的启动 Pin 允许用户输入全键盘上的任何键，包括大写和小写字母、符号、数字和空格。</span><span class="sxs-lookup"><span data-stu-id="eaec9-246">Enhanced startup PINs permit users to enter any keys on a full keyboard, including uppercase and lowercase letters, symbols, numbers, and spaces.</span></span> <span data-ttu-id="eaec9-247">如果启用此策略设置，则设置的所有新 BitLocker 启动 Pin 将为增强引脚。</span><span class="sxs-lookup"><span data-stu-id="eaec9-247">If you enable this policy setting, all new BitLocker startup PINs that are set will be enhanced PINs.</span></span> <span data-ttu-id="eaec9-248">如果禁用或未配置此策略设置，则无法使用增强的 Pin 码。</span><span class="sxs-lookup"><span data-stu-id="eaec9-248">If you disable or do not configure this policy setting, enhanced PINs cannot be used.</span></span>

<span data-ttu-id="eaec9-249">并非所有计算机都支持预启动执行环境（PXE）中的增强型 Pin 输入。</span><span class="sxs-lookup"><span data-stu-id="eaec9-249">Not all computers support the entry of enhanced PINs in the Pre-Boot Execution Environment (PXE).</span></span> <span data-ttu-id="eaec9-250">在为你的组织启用此组策略设置之前，请在 BitLocker 安装过程中运行系统检查，以确保计算机的 BIOS 支持在 PXE 中使用完整的键盘。</span><span class="sxs-lookup"><span data-stu-id="eaec9-250">Before you enable this Group Policy setting for your organization, run a system check during the BitLocker setup process to ensure that the computer’s BIOS supports the use of the full keyboard in PXE.</span></span> <span data-ttu-id="eaec9-251">有关详细信息，请参阅[规划 MBAM 2.5 组策略要求](planning-for-mbam-25-group-policy-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="eaec9-251">For more information, see [Planning for MBAM 2.5 Group Policy Requirements](planning-for-mbam-25-group-policy-requirements.md).</span></span>

**<span data-ttu-id="eaec9-252">"要求仅限 ASCII 的 Pin" 复选框</span><span class="sxs-lookup"><span data-stu-id="eaec9-252">Require ASCII-only PINs check box</span></span>**

<span data-ttu-id="eaec9-253">"**允许启动组的增强引脚**" 策略设置还包含 "**需要 ASCII 专用 pin** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="eaec9-253">The **Allow enhanced PINs for startup** Group Policy setting also contains a **Require ASCII-only PINs** check box.</span></span> <span data-ttu-id="eaec9-254">如果组织中的计算机不支持在 PXE 中使用完整键盘，则可以启用 "允许启动组的**增强引脚**" 策略设置，然后选中 "**需要 ASCII 专用引脚**" 复选框以要求增强引脚仅使用可打印的 ascii 字符。</span><span class="sxs-lookup"><span data-stu-id="eaec9-254">If the computers in your organization do not support the use of the full keyboard in PXE, you can enable the **Allow enhanced PINs for startup** Group Policy setting, and then select the **Require ASCII-only PINs** check box to require that enhanced PINs use only printable ASCII characters.</span></span>

**<span data-ttu-id="eaec9-255">强制使用非顺序和非重复字符</span><span class="sxs-lookup"><span data-stu-id="eaec9-255">Enforced use of nonsequential and nonrepeating characters</span></span>**

<span data-ttu-id="eaec9-256">MBAM 2.5 阻止最终用户创建由重复号码（如1111）或序列号（如1234）组成的引脚。</span><span class="sxs-lookup"><span data-stu-id="eaec9-256">MBAM2.5 prevents end users from creating PINs that consist of repeating numbers (such as 1111) or sequential numbers (such as 1234).</span></span> <span data-ttu-id="eaec9-257">如果最终用户尝试输入包含三个或更多重复或连续数字的密码，则 Bitlocker 驱动器加密向导将显示一条错误消息，并防止用户输入包含禁止使用的字符的 PIN 码。</span><span class="sxs-lookup"><span data-stu-id="eaec9-257">If end users try to enter a password that contains three or more repeating or sequential numbers, the Bitlocker Drive Encryption wizard displays an error message and prevents users from entering a PIN with the prohibited characters.</span></span>

### <span data-ttu-id="eaec9-258">将 DRA 证书添加到 BitLocker 计算机合规性报告</span><span class="sxs-lookup"><span data-stu-id="eaec9-258">Addition of DRA Certificate to BitLocker Computer Compliance report</span></span>

<span data-ttu-id="eaec9-259">已在 Configuration Manager 的 BitLocker 计算机合规性报告中添加了新的保护程序类型（数据恢复代理（DRA）证书）。</span><span class="sxs-lookup"><span data-stu-id="eaec9-259">A new protector type, the Data Recovery Agent (DRA) Certificate, has been added to the BitLocker Computer Compliance Report in Configuration Manager.</span></span> <span data-ttu-id="eaec9-260">此保护器类型适用于操作系统驱动器，并且显示在 "**保护类型**" 列中的 "**计算机卷**" 部分。</span><span class="sxs-lookup"><span data-stu-id="eaec9-260">This protector type applies to operating system drives, and it appears in the **Computer Volume(s)** section in the **Protector Types** column.</span></span>

### <span data-ttu-id="eaec9-261">支持多林支持部署</span><span class="sxs-lookup"><span data-stu-id="eaec9-261">Support for multi-forest support deployments</span></span>

<span data-ttu-id="eaec9-262">MBAM 2.5 支持以下类型的多林部署：</span><span class="sxs-lookup"><span data-stu-id="eaec9-262">MBAM 2.5 supports the following types of multi-forest deployments:</span></span>

-   <span data-ttu-id="eaec9-263">具有单个域的单林</span><span class="sxs-lookup"><span data-stu-id="eaec9-263">Single forest with single domain</span></span>

-   <span data-ttu-id="eaec9-264">具有单个树和多个域的单林</span><span class="sxs-lookup"><span data-stu-id="eaec9-264">Single forest with a single tree and multiple domains</span></span>

-   <span data-ttu-id="eaec9-265">具有多个树和不连续命名空间的单林</span><span class="sxs-lookup"><span data-stu-id="eaec9-265">Single forest with multiple trees and disjoint namespaces</span></span>

-   <span data-ttu-id="eaec9-266">中央林拓扑中的多个林</span><span class="sxs-lookup"><span data-stu-id="eaec9-266">Multiple forests in a central forest topology</span></span>

-   <span data-ttu-id="eaec9-267">资源林拓扑中的多个林</span><span class="sxs-lookup"><span data-stu-id="eaec9-267">Multiple forests in a resource forest topology</span></span>

<span data-ttu-id="eaec9-268">不支持林迁移（从单一到多、多到单、资源到整个林，等等），或者升级或降级。</span><span class="sxs-lookup"><span data-stu-id="eaec9-268">There is no support for forest migration (going from single to multiple, multiple to single, resource to across the forest, etc.), or upgrade or downgrade.</span></span>

<span data-ttu-id="eaec9-269">在多林部署中部署 MBAM 的先决条件包括：</span><span class="sxs-lookup"><span data-stu-id="eaec9-269">The prerequisites for deploying MBAM in multi-forest deployments are:</span></span>

-   <span data-ttu-id="eaec9-270">林必须在支持的 Windows Server 版本上运行。</span><span class="sxs-lookup"><span data-stu-id="eaec9-270">Forest must be running on supported versions of Windows Server.</span></span>

-   <span data-ttu-id="eaec9-271">需要双向或单向信任。</span><span class="sxs-lookup"><span data-stu-id="eaec9-271">A two-way or one-way trust is required.</span></span> <span data-ttu-id="eaec9-272">单向信任要求服务器的域信任客户端的域。</span><span class="sxs-lookup"><span data-stu-id="eaec9-272">One-way trusts require that the server’s domain trusts the client’s domain.</span></span> <span data-ttu-id="eaec9-273">换句话说，服务器的域指向客户的域。</span><span class="sxs-lookup"><span data-stu-id="eaec9-273">In other words, the server’s domain is pointed at the client’s domain.</span></span>

### <span data-ttu-id="eaec9-274">MBAM 客户端对加密硬驱的支持</span><span class="sxs-lookup"><span data-stu-id="eaec9-274">MBAM Client support for Encrypted Hard Drives</span></span>

<span data-ttu-id="eaec9-275">MBAM 支持在满足 Opal 的 TCG 规范要求和 IEEE 1667 标准的加密硬盘上支持 BitLocker。</span><span class="sxs-lookup"><span data-stu-id="eaec9-275">MBAM supports BitLocker on Encrypted Hard Drives that meet TCG specification requirements for Opal as well as IEEE 1667 standards.</span></span> <span data-ttu-id="eaec9-276">在这些设备上启用 BitLocker 时，它将在已加密的驱动器上生成密钥并执行管理功能。</span><span class="sxs-lookup"><span data-stu-id="eaec9-276">When BitLocker is enabled on these devices, it will generate keys and perform management functions on the encrypted drive.</span></span> <span data-ttu-id="eaec9-277">有关详细信息，请参阅[加密的硬驱](https://technet.microsoft.com/library/hh831627.aspx)。</span><span class="sxs-lookup"><span data-stu-id="eaec9-277">See [Encrypted Hard Drive](https://technet.microsoft.com/library/hh831627.aspx) for more information.</span></span>

## <span data-ttu-id="eaec9-278">如何获取 MDOP 技术</span><span class="sxs-lookup"><span data-stu-id="eaec9-278">How to Get MDOP Technologies</span></span>


<span data-ttu-id="eaec9-279">MBAM 是 Microsoft 桌面优化包（MDOP）的一部分。</span><span class="sxs-lookup"><span data-stu-id="eaec9-279">MBAM is a part of the Microsoft Desktop Optimization Pack (MDOP).</span></span> <span data-ttu-id="eaec9-280">MDOP 是 Microsoft 软件保障计划的一部分。</span><span class="sxs-lookup"><span data-stu-id="eaec9-280">MDOP is part of the Microsoft Software Assurance program.</span></span> <span data-ttu-id="eaec9-281">有关 Microsoft 软件保证计划以及如何获取 MDOP 的详细信息，请参阅[如何获取 mdop？](https://go.microsoft.com/fwlink/?LinkId=322049)。</span><span class="sxs-lookup"><span data-stu-id="eaec9-281">For more information about the Microsoft Software Assurance program and how to acquire the MDOP, see [How Do I Get MDOP?](https://go.microsoft.com/fwlink/?LinkId=322049).</span></span>

## <a href="" id="---------mbam-2-5-release-notes"></a> <span data-ttu-id="eaec9-282">MBAM 2.5 发行说明</span><span class="sxs-lookup"><span data-stu-id="eaec9-282">MBAM 2.5 Release Notes</span></span>


<span data-ttu-id="eaec9-283">有关此文档中未包括的详细信息和最新新闻，请参阅[MBAM 2.5 的发行说明](release-notes-for-mbam-25.md)。</span><span class="sxs-lookup"><span data-stu-id="eaec9-283">For more information and late-breaking news that is not included in this documentation, see [Release Notes for MBAM 2.5](release-notes-for-mbam-25.md).</span></span>

## <span data-ttu-id="eaec9-284">已获得 MBAM 的建议？</span><span class="sxs-lookup"><span data-stu-id="eaec9-284">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="eaec9-285">[在此处](https://support.microsoft.com/help/4021566/windows-10-send-feedback-to-microsoft-with-feedback-hub)发送反馈。</span><span class="sxs-lookup"><span data-stu-id="eaec9-285">Send your feedback [here](https://support.microsoft.com/help/4021566/windows-10-send-feedback-to-microsoft-with-feedback-hub).</span></span> 
- <span data-ttu-id="eaec9-286">对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="eaec9-286">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>

## <span data-ttu-id="eaec9-287">相关主题</span><span class="sxs-lookup"><span data-stu-id="eaec9-287">Related topics</span></span>


[<span data-ttu-id="eaec9-288">Microsoft BitLocker 管理和监控 2.5</span><span class="sxs-lookup"><span data-stu-id="eaec9-288">Microsoft BitLocker Administration and Monitoring 2.5</span></span>](index.md)

[<span data-ttu-id="eaec9-289">MBAM 2.5 入门</span><span class="sxs-lookup"><span data-stu-id="eaec9-289">Getting Started with MBAM 2.5</span></span>](getting-started-with-mbam-25.md)

 

 





