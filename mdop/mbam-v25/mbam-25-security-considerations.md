---
title: MBAM 2.5 安全注意事项
description: MBAM 2.5 安全注意事项
author: dansimp
ms.assetid: f6613c63-b32b-45fb-a6e8-673d6dae7d16
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 04/23/2017
ms.openlocfilehash: 86a756ab6f983fa1f22de6835b5993e1215d1dbe
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804048"
---
# <span data-ttu-id="f518e-103">MBAM 2.5 安全注意事项</span><span class="sxs-lookup"><span data-stu-id="f518e-103">MBAM 2.5 Security Considerations</span></span>


<span data-ttu-id="f518e-104">本主题包含有关如何保护 Microsoft BitLocker 管理和监视（MBAM）的以下信息：</span><span class="sxs-lookup"><span data-stu-id="f518e-104">This topic contains the following information about how to secure Microsoft BitLocker Administration and Monitoring (MBAM):</span></span>

-   [<span data-ttu-id="f518e-105">配置 MBAM 以托管 TPM 和存储 OwnerAuth 密码</span><span class="sxs-lookup"><span data-stu-id="f518e-105">Configure MBAM to escrow the TPM and store OwnerAuth passwords</span></span>](#bkmk-tpm)

-   [<span data-ttu-id="f518e-106">将 MBAM 配置为在锁定后自动解锁 TPM</span><span class="sxs-lookup"><span data-stu-id="f518e-106">Configure MBAM to automatically unlock the TPM after a lockout</span></span>](#bkmk-autounlock)

-   [<span data-ttu-id="f518e-107">连接到 SQL Server 的安全连接</span><span class="sxs-lookup"><span data-stu-id="f518e-107">Secure connections to SQL Server</span></span>](#bkmk-secure-databases)

-   [<span data-ttu-id="f518e-108">创建帐户和组</span><span class="sxs-lookup"><span data-stu-id="f518e-108">Create accounts and groups</span></span>](#bkmk-accts-groups)

-   [<span data-ttu-id="f518e-109">使用 MBAM 日志文件</span><span class="sxs-lookup"><span data-stu-id="f518e-109">Use MBAM log files</span></span>](#bkmk-logfiles)

-   [<span data-ttu-id="f518e-110">查看 MBAM 数据库 TDE 注意事项</span><span class="sxs-lookup"><span data-stu-id="f518e-110">Review MBAM database TDE considerations</span></span>](#bkmk-tde)

-   [<span data-ttu-id="f518e-111">了解常规安全注意事项</span><span class="sxs-lookup"><span data-stu-id="f518e-111">Understand general security considerations</span></span>](#bkmk-general-security)

## <a href="" id="bkmk-tpm"></a><span data-ttu-id="f518e-112">配置 MBAM 以托管 TPM 和存储 OwnerAuth 密码</span><span class="sxs-lookup"><span data-stu-id="f518e-112">Configure MBAM to escrow the TPM and store OwnerAuth passwords</span></span>

<span data-ttu-id="f518e-113">**注意**对于 Windows 10 版本1607或更高版本，只有 Windows 可以获得 TPM 的所有权。</span><span class="sxs-lookup"><span data-stu-id="f518e-113">**Note** For Windows 10, version 1607 or later, only Windows can take ownership of the TPM.</span></span> <span data-ttu-id="f518e-114">此外，预配 TPM 时，Windows 不会保留 TPM 所有者密码。</span><span class="sxs-lookup"><span data-stu-id="f518e-114">In addition, Windows will not retain the TPM owner password when provisioning the TPM.</span></span> <span data-ttu-id="f518e-115">有关进一步的详细信息，请参阅[TPM 所有者密码](https://docs.microsoft.com/windows/security/information-protection/tpm/change-the-tpm-owner-password)。</span><span class="sxs-lookup"><span data-stu-id="f518e-115">See [TPM owner password](https://docs.microsoft.com/windows/security/information-protection/tpm/change-the-tpm-owner-password) for further details.</span></span>

<span data-ttu-id="f518e-116">根据其配置，受信任的平台模块（TPM）将在某些情况下锁定自身，例如在输入了太多不正确的密码时，可以在一段时间内保持锁定。</span><span class="sxs-lookup"><span data-stu-id="f518e-116">Depending on its configuration, the Trusted Platform Module (TPM) will lock itself in certain situations ─ such as when too many incorrect passwords are entered ─ and can remain locked for a period of time.</span></span> <span data-ttu-id="f518e-117">在 TPM 锁定期间，BitLocker 无法访问加密密钥以执行解锁或解密操作，要求用户输入其 BitLocker 恢复密钥才能访问操作系统驱动器。</span><span class="sxs-lookup"><span data-stu-id="f518e-117">During TPM lockout, BitLocker cannot access the encryption keys to perform unlock or decryption operations, requiring the user to enter their BitLocker recovery key to access the operating system drive.</span></span> <span data-ttu-id="f518e-118">若要重置 TPM 锁定，必须提供 TPM OwnerAuth 密码。</span><span class="sxs-lookup"><span data-stu-id="f518e-118">To reset TPM lockout, you must provide the TPM OwnerAuth password.</span></span>

<span data-ttu-id="f518e-119">MBAM 可以在 MBAM 数据库中存储 TPM OwnerAuth 密码（如果它拥有 TPM 或 escrows 该密码）。</span><span class="sxs-lookup"><span data-stu-id="f518e-119">MBAM can store the TPM OwnerAuth password in the MBAM database if it owns the TPM or if it escrows the password.</span></span> <span data-ttu-id="f518e-120">当必须从 TPM 锁定恢复时，可以在管理和监视网站上轻松访问 OwnerAuth 密码，这样就不必等到锁定自行解决。</span><span class="sxs-lookup"><span data-stu-id="f518e-120">OwnerAuth passwords are then easily accessible on the Administration and Monitoring Website when you must recover from a TPM lockout, eliminating the need to wait for the lockout to resolve on its own.</span></span>

### <span data-ttu-id="f518e-121">Windows 8 及更高版本中的 Escrowing TPM OwnerAuth</span><span class="sxs-lookup"><span data-stu-id="f518e-121">Escrowing TPM OwnerAuth in Windows 8 and higher</span></span>

<span data-ttu-id="f518e-122">**注意**对于 Windows 10 版本1607或更高版本，只有 Windows 可以获得 TPM 的所有权。</span><span class="sxs-lookup"><span data-stu-id="f518e-122">**Note** For Windows 10, version 1607 or later, only Windows can take ownership of the TPM.</span></span> <span data-ttu-id="f518e-123">在 addiiton 中，Windows 将不会在预配 TPM 时保留 TPM 所有者密码。</span><span class="sxs-lookup"><span data-stu-id="f518e-123">In addiiton, Windows will not retain the TPM owner password when provisioning the TPM.</span></span> <span data-ttu-id="f518e-124">有关进一步的详细信息，请参阅[TPM 所有者密码](https://docs.microsoft.com/windows/security/information-protection/tpm/change-the-tpm-owner-password)。</span><span class="sxs-lookup"><span data-stu-id="f518e-124">See [TPM owner password](https://docs.microsoft.com/windows/security/information-protection/tpm/change-the-tpm-owner-password) for further details.</span></span>

<span data-ttu-id="f518e-125">在 Windows 8 或更高版本中，只要 OwnerAuth 在本地计算机上可用，MBAM 就不能再拥有 TPM 来存储 OwnerAuth 密码。</span><span class="sxs-lookup"><span data-stu-id="f518e-125">In Windows 8 or higher, MBAM no longer must own the TPM to store the OwnerAuth password, as long as the OwnerAuth is available on the local machine.</span></span>

<span data-ttu-id="f518e-126">若要使 MBAM 能够进行托管，然后存储 TPM OwnerAuth 密码，必须配置这些组策略设置。</span><span class="sxs-lookup"><span data-stu-id="f518e-126">To enable MBAM to escrow and then store TPM OwnerAuth passwords, you must configure these Group Policy settings.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="f518e-127">组策略设置</span><span class="sxs-lookup"><span data-stu-id="f518e-127">Group Policy Setting</span></span></th>
<th align="left"><span data-ttu-id="f518e-128">配置</span><span class="sxs-lookup"><span data-stu-id="f518e-128">Configuration</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f518e-129">将 TPM 备份启用到 Active Directory 域服务</span><span class="sxs-lookup"><span data-stu-id="f518e-129">Turn on TPM backup to Active Directory Domain Services</span></span></p></td>
<td align="left"><p><span data-ttu-id="f518e-130">已禁用或未配置</span><span class="sxs-lookup"><span data-stu-id="f518e-130">Disabled or Not Configured</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f518e-131">配置操作系统可用的 TPM 所有者授权信息级别</span><span class="sxs-lookup"><span data-stu-id="f518e-131">Configure the level of TPM owner authorization information available to the operating system</span></span></p></td>
<td align="left"><p><span data-ttu-id="f518e-132">已委派/无或未配置</span><span class="sxs-lookup"><span data-stu-id="f518e-132">Delegated/None or Not Configured</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="f518e-133">这些组策略设置的位置是 "**计算机配置**" &gt; **管理模板** &gt; **系统** &gt; **受信任的平台模块服务**。</span><span class="sxs-lookup"><span data-stu-id="f518e-133">The location of these Group Policy settings is **Computer Configuration** &gt; **Administrative Templates** &gt; **System** &gt; **Trusted Platform Module Services**.</span></span>

<span data-ttu-id="f518e-134">**注意** 在 MBAM 成功 escrows 所有设置后，Windows 将 OwnerAuth 在本地删除。</span><span class="sxs-lookup"><span data-stu-id="f518e-134">**Note** Windows removes the OwnerAuth locally after MBAM successfully escrows it with these settings.</span></span>

 

### <span data-ttu-id="f518e-135">Windows 7 中的 Escrowing TPM OwnerAuth</span><span class="sxs-lookup"><span data-stu-id="f518e-135">Escrowing TPM OwnerAuth in Windows 7</span></span>

<span data-ttu-id="f518e-136">在 Windows 7 中，MBAM 必须拥有 TPM 才能在 MBAM 数据库中自动托管 TPM OwnerAuth 信息。</span><span class="sxs-lookup"><span data-stu-id="f518e-136">In Windows 7, MBAM must own the TPM to automatically escrow TPM OwnerAuth information in the MBAM database.</span></span> <span data-ttu-id="f518e-137">如果 MBAM 不拥有 TPM，则必须使用 MBAM Active Directory （AD）数据导入 cmdlet 将 TPM OwnerAuth 从 Active Directory 复制到 MBAM 数据库中。</span><span class="sxs-lookup"><span data-stu-id="f518e-137">If MBAM does not own the TPM, you must use the MBAM Active Directory (AD) Data Import cmdlets to copy TPM OwnerAuth from Active Directory into the MBAM database.</span></span>

### <span data-ttu-id="f518e-138">MBAM Active Directory 数据导入 cmdlet</span><span class="sxs-lookup"><span data-stu-id="f518e-138">MBAM Active Directory Data Import cmdlets</span></span>

<span data-ttu-id="f518e-139">MBAM Active Directory 数据导入 cmdlet 可用于检索存储在 Active Directory 中的恢复密钥包和 OwnerAuth 密码。</span><span class="sxs-lookup"><span data-stu-id="f518e-139">The MBAM Active Directory Data Import cmdlets let you retrieve recovery key packages and OwnerAuth passwords that are stored in Active Directory.</span></span>

<span data-ttu-id="f518e-140">MBAM 2.5 SP1 服务器随附有四个 PowerShell cmdlet，这些 cmdlet 通过存储在 Active Directory 中的卷恢复和 TPM 所有者信息预填充 MBAM 数据库。</span><span class="sxs-lookup"><span data-stu-id="f518e-140">The MBAM 2.5 SP1 server ships with four PowerShell cmdlets that pre-populate MBAM databases with the Volume recovery and TPM owner information stored in Active Directory.</span></span>

<span data-ttu-id="f518e-141">对于卷恢复密钥和程序包：</span><span class="sxs-lookup"><span data-stu-id="f518e-141">For Volume Recovery keys and packages:</span></span>

-   <span data-ttu-id="f518e-142">Read ADRecoveryInformation</span><span class="sxs-lookup"><span data-stu-id="f518e-142">Read-ADRecoveryInformation</span></span>

-   <span data-ttu-id="f518e-143">Write-MbamRecoveryInformation</span><span class="sxs-lookup"><span data-stu-id="f518e-143">Write-MbamRecoveryInformation</span></span>

<span data-ttu-id="f518e-144">对于 TPM 所有者信息：</span><span class="sxs-lookup"><span data-stu-id="f518e-144">For TPM Owner Information:</span></span>

-   <span data-ttu-id="f518e-145">Read ADTpmInformation</span><span class="sxs-lookup"><span data-stu-id="f518e-145">Read-ADTpmInformation</span></span>

-   <span data-ttu-id="f518e-146">Write-MbamTpmInformation</span><span class="sxs-lookup"><span data-stu-id="f518e-146">Write-MbamTpmInformation</span></span>

<span data-ttu-id="f518e-147">将用户与计算机相关联：</span><span class="sxs-lookup"><span data-stu-id="f518e-147">For Associating Users to Computers:</span></span>

-   <span data-ttu-id="f518e-148">Write-MbamComputerUser</span><span class="sxs-lookup"><span data-stu-id="f518e-148">Write-MbamComputerUser</span></span>

<span data-ttu-id="f518e-149">Read 广告 \ \* cmdlet 读取 Active Directory 中的信息。</span><span class="sxs-lookup"><span data-stu-id="f518e-149">The Read-AD\* cmdlets read information from Active Directory.</span></span> <span data-ttu-id="f518e-150">Write Mbam \ \* cmdlet 将数据推送到 MBAM 数据库中。</span><span class="sxs-lookup"><span data-stu-id="f518e-150">The Write-Mbam\* cmdlets push the data into the MBAM databases.</span></span> <span data-ttu-id="f518e-151">有关这些 cmdlet 的详细信息，请参阅[Microsoft Bitlocker 管理和监视 2.5 Cmdlet 参考](https://technet.microsoft.com/library/dn459018.aspx)，包括语法、参数和示例。</span><span class="sxs-lookup"><span data-stu-id="f518e-151">See [Cmdlet Reference for Microsoft Bitlocker Administration and Monitoring 2.5](https://technet.microsoft.com/library/dn459018.aspx) for detailed information about these cmdlets, including syntax, parameters, and examples.</span></span>

<span data-ttu-id="f518e-152">**创建用户到计算机的关联：** MBAM Active Directory 数据导入 cmdlet 从 Active Directory 中收集信息，并将数据插入 MBAM 数据库中。</span><span class="sxs-lookup"><span data-stu-id="f518e-152">**Create user-to-computer associations:** The MBAM Active Directory Data Import cmdlets gather information from Active Directory and insert the data into MBAM database.</span></span> <span data-ttu-id="f518e-153">但是，它们不会将用户与卷相关联。</span><span class="sxs-lookup"><span data-stu-id="f518e-153">However, they do not associate users to volumes.</span></span> <span data-ttu-id="f518e-154">你可以下载 Add-ComputerUser.ps1 PowerShell 脚本以创建用户到计算机关联，从而使用户可以通过管理和监视网站或通过使用自助服务门户进行恢复来重新访问计算机。</span><span class="sxs-lookup"><span data-stu-id="f518e-154">You can download the Add-ComputerUser.ps1 PowerShell script to create user-to-machine associations, which let users regain access to a computer through the Administration and Monitoring Website or by using the Self-Service Portal for recovery.</span></span> <span data-ttu-id="f518e-155">Add-ComputerUser.ps1 脚本从 Active Directory （AD）、AD 中的对象所有者或自定义 CSV 文件中的 "**托管者**" 属性收集数据。</span><span class="sxs-lookup"><span data-stu-id="f518e-155">The Add-ComputerUser.ps1 script gathers data from the **Managed By** attribute in Active Directory (AD), the object owner in AD, or from a custom CSV file.</span></span> <span data-ttu-id="f518e-156">然后，该脚本将发现的用户添加到恢复信息管道对象，该对象必须传递到 MbamRecoveryInformation 以将数据插入到恢复数据库中。</span><span class="sxs-lookup"><span data-stu-id="f518e-156">The script then adds the discovered users to the recovery information pipeline object, which must be passed to Write-MbamRecoveryInformation to insert the data into the recovery database.</span></span>

<span data-ttu-id="f518e-157">从[Microsoft 下载中心](https://go.microsoft.com/fwlink/?LinkId=613122)下载 Add-ComputerUser.ps1 PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="f518e-157">Download the Add-ComputerUser.ps1 PowerShell script from the [Microsoft Download Center](https://go.microsoft.com/fwlink/?LinkId=613122).</span></span>

<span data-ttu-id="f518e-158">你可以指定**帮助 Add-ComputerUser.ps1**获取有关脚本的帮助，包括如何使用 cmdlet 和脚本的示例。</span><span class="sxs-lookup"><span data-stu-id="f518e-158">You can specify **help Add-ComputerUser.ps1** to get help for the script, including examples of how to use the cmdlets and the script.</span></span>

<span data-ttu-id="f518e-159">若要在安装 MBAM 服务器之后创建用户到计算机的关联，请使用 MbamComputerUser PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f518e-159">To create user-to-computer associations after you have installed the MBAM server, use the Write-MbamComputerUser PowerShell cmdlet.</span></span> <span data-ttu-id="f518e-160">与 Add-ComputerUser.ps1 PowerShell 脚本类似，此 cmdlet 允许你指定可使用自助服务门户获取指定计算机的 TPM OwnerAuth 信息或卷恢复密码的用户。</span><span class="sxs-lookup"><span data-stu-id="f518e-160">Similar to the Add-ComputerUser.ps1 PowerShell script, this cmdlet lets you specify users that can use the Self-Service Portal to get TPM OwnerAuth information or volume recovery passwords for the specified computer.</span></span>

<span data-ttu-id="f518e-161">**注意** 当该计算机开始向服务器报告时，MBAM 代理将替代用户到计算机的关联。</span><span class="sxs-lookup"><span data-stu-id="f518e-161">**Note** The MBAM agent will override user-to-computer associations when that computer begins reporting up to the server.</span></span>

 

<span data-ttu-id="f518e-162">**先决条件：** 只有当用户以高度特权的用户帐户（如域管理员）身份运行，或以帐户的形式作为帐户在被授予对该信息的读取访问权限的自定义安全组中运行时，"已读广告 \ \*" cmdlet 才能检索来自该信息的信息（推荐）。</span><span class="sxs-lookup"><span data-stu-id="f518e-162">**Prerequisites:** The Read-AD\* cmdlets can retrieve information from AD only if they are either run as a highly privileged user account, such as a Domain Administrator, or run as an account in a custom security group granted read access to the information (recommended).</span></span>

<span data-ttu-id="f518e-163">[BitLocker 驱动器加密操作指南：使用 AD DS 恢复加密的卷](https://technet.microsoft.com/library/cc771778(WS.10).aspx)提供有关创建自定义安全组（或多个组）以及对广告信息的读取访问权限的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f518e-163">[BitLocker Drive Encryption Operations Guide: Recovering Encrypted Volumes with AD DS](https://technet.microsoft.com/library/cc771778(WS.10).aspx) provides details about creating a custom security group (or multiple groups) with read access to the AD information.</span></span>

<span data-ttu-id="f518e-164">**MBAM 恢复和硬件 Web 服务写入权限：** Write Mbam \ \* cmdlet 接受用于发布恢复或 TPM 信息的 MBAM 恢复和硬件服务的 URL。</span><span class="sxs-lookup"><span data-stu-id="f518e-164">**MBAM Recovery and Hardware Web Service Write Permissions:** The Write-Mbam\* cmdlets accept the URL of the MBAM Recovery and Hardware Service, used to publish the recovery or TPM information.</span></span> <span data-ttu-id="f518e-165">通常，只有域计算机服务帐户可以与 MBAM 恢复和硬件服务进行通信。</span><span class="sxs-lookup"><span data-stu-id="f518e-165">Typically, only a domain computer service account can communicate with the MBAM Recovery and Hardware Service.</span></span> <span data-ttu-id="f518e-166">在 MBAM 2.5 SP1 中，你可以使用名为 DataMigrationAccessGroup 的安全组将 MBAM 恢复和硬件服务配置为允许其成员绕过域计算机服务帐户检查。</span><span class="sxs-lookup"><span data-stu-id="f518e-166">In MBAM 2.5 SP1, you can configure the MBAM Recovery and Hardware Service with a security group called DataMigrationAccessGroup whose members are allowed to bypass the domain computer service account check.</span></span> <span data-ttu-id="f518e-167">Write-Mbam \ \* cmdlet 必须作为属于此配置组的用户运行。</span><span class="sxs-lookup"><span data-stu-id="f518e-167">The Write-Mbam\* cmdlets must be run as a user belonging to this configured group.</span></span> <span data-ttu-id="f518e-168">（或者，可以使用 Write-Mbam \ \* cmdlet 中的– Credential 参数指定已配置组中单个用户的凭据。）</span><span class="sxs-lookup"><span data-stu-id="f518e-168">(Alternatively, the credentials of an individual user in the configured group can be specified by using the –Credential parameter in the Write-Mbam\* cmdlets.)</span></span>

<span data-ttu-id="f518e-169">你可以通过以下方式之一将 MBAM 恢复和硬件服务与此安全组的名称进行配置：</span><span class="sxs-lookup"><span data-stu-id="f518e-169">You can configure the MBAM Recovery and Hardware Service with the name of this security group in one of these ways:</span></span>

-   <span data-ttu-id="f518e-170">在 Enable-MbamWebApplication-AgentService Powershell cmdlet 的-DataMigrationAccessGroup 参数中提供安全组（或个人）的名称。</span><span class="sxs-lookup"><span data-stu-id="f518e-170">Provide the name of the security group (or individual) in the -DataMigrationAccessGroup parameter of the Enable-MbamWebApplication –AgentService Powershell cmdlet.</span></span>

-   <span data-ttu-id="f518e-171">通过在 &lt; inetpub &gt; \\Microsoft Bitlocker 管理 Solution\\Recovery 和硬件 Service\\ 文件夹中编辑 web.config 文件，在安装 MBAM 恢复和硬件服务之后配置组。</span><span class="sxs-lookup"><span data-stu-id="f518e-171">Configure the group after the MBAM Recovery and Hardware Service has been installed by editing the web.config file in the &lt;inetpub&gt;\\Microsoft Bitlocker Management Solution\\Recovery and Hardware Service\\ folder.</span></span>

    ```xml
    <add key="DataMigrationUsersGroupName" value="<groupName>|<empty>" />
    ```

    <span data-ttu-id="f518e-172">&lt; &gt; 将用于允许从 Active Directory 进行数据迁移的域和组名（或单个用户）替换了组名。</span><span class="sxs-lookup"><span data-stu-id="f518e-172">where &lt;groupName&gt; is replaced with the domain and the group name (or the individual user) that will be used to allow data migration from Active Directory.</span></span>

-   <span data-ttu-id="f518e-173">在 IIS 管理器中使用配置编辑器编辑此 appSetting。</span><span class="sxs-lookup"><span data-stu-id="f518e-173">Use the Configuration Editor in IIS Manager to edit this appSetting.</span></span>

<span data-ttu-id="f518e-174">在以下示例中，当作为 ADRecoveryInformation 组和数据迁移用户组的成员运行时，该命令将从 contoso.com 域中的工作站组织单位（OU）内的计算机提取卷恢复信息，并使用 mbam.contoso.com 服务器上运行的 MBAM 恢复和硬件服务将这些信息写入 MBAM。</span><span class="sxs-lookup"><span data-stu-id="f518e-174">In the following example, the command, when run as a member of both the ADRecoveryInformation group and the Data Migration Users group, will pull the volume recovery information from computers in the WORKSTATIONS organizational unit (OU) in the contoso.com domain and write them to MBAM by using the MBAM Recovery and Hardware Service running on the mbam.contoso.com server.</span></span>

``` syntax
PS C:\> Read-ADRecoveryInformation -Server contoso.com -SearchBase "OU=WORKSTATIONS,DC=CONTOSO,DC=COM" | Write-MbamRecoveryInformation -RecoveryServiceEndPoint "https://mbam.contoso.com/MBAMRecoveryAndHardwareService/CoreService.svc"
```

<span data-ttu-id="f518e-175">**Read-广告 \ \* cmdlet**接受托管服务器计算机的 Active Directory 的名称或 IP 地址，以查询恢复或 TPM 信息。</span><span class="sxs-lookup"><span data-stu-id="f518e-175">**Read-AD\* cmdlets** accept the name or IP address of an Active Directory hosting server machine to query for recovery or TPM information.</span></span> <span data-ttu-id="f518e-176">我们建议你提供将计算机对象作为 SearchBase 参数的值驻留的广告容器的可分辨名称。</span><span class="sxs-lookup"><span data-stu-id="f518e-176">We recommend providing the distinguished names of the AD containers in which the computer object resides as the value of the SearchBase parameter.</span></span> <span data-ttu-id="f518e-177">如果计算机存储在多个 Ou 中，则 cmdlet 可以接受针对每个容器运行一次的管道输入。</span><span class="sxs-lookup"><span data-stu-id="f518e-177">If computers are stored across several OUs, the cmdlets can accept pipeline input to run once for each container.</span></span> <span data-ttu-id="f518e-178">广告容器的可分辨名称看起来将类似于 OU = 计算机，DC = contoso，DC = com。</span><span class="sxs-lookup"><span data-stu-id="f518e-178">The distinguished name of an AD container will look similar to OU=Machines,DC=contoso,DC=com.</span></span> <span data-ttu-id="f518e-179">执行针对特定容器的搜索可提供以下好处：</span><span class="sxs-lookup"><span data-stu-id="f518e-179">Performing a search targeted to specific containers provides the following benefits:</span></span>

-   <span data-ttu-id="f518e-180">在查询大型 AD 数据集以查找计算机对象时，降低超时风险。</span><span class="sxs-lookup"><span data-stu-id="f518e-180">Reduces the risk of timeout while querying a large AD dataset for computer objects.</span></span>

-   <span data-ttu-id="f518e-181">可以忽略包含数据中心服务器或可能不需要备份的其他计算机类的 Ou。</span><span class="sxs-lookup"><span data-stu-id="f518e-181">Can omit OUs containing datacenter servers or other classes of computers for which the backup might not be desired or necessary.</span></span>

<span data-ttu-id="f518e-182">另一个选择是提供带有或不带可选 SearchBase 的-递归标志，以在指定的 SearchBase 或整个域下的所有容器中搜索计算机对象。</span><span class="sxs-lookup"><span data-stu-id="f518e-182">Another option is to provide the –Recurse flag with or without the optional SearchBase to search for computer objects across all containers under the specified SearchBase or the entire domain respectively.</span></span> <span data-ttu-id="f518e-183">使用-递归标志时，还可以使用-MaxPageSize 参数来控制服务查询所需的本地和远程内存量。</span><span class="sxs-lookup"><span data-stu-id="f518e-183">When you use the -Recurse flag, you can also use the -MaxPageSize parameter to control the amount of local and remote memory required to service the query.</span></span>

<span data-ttu-id="f518e-184">这些 cmdlet 将写入类型为 PsObject 的管道对象。</span><span class="sxs-lookup"><span data-stu-id="f518e-184">These cmdlets write to the pipeline objects of type PsObject.</span></span> <span data-ttu-id="f518e-185">每个 PsObject 实例都包含一个卷恢复密钥或 TPM 所有者字符串以及将其与其关联的计算机名称、时间戳和其他信息发布到 MBAM 数据存储中所需的其他信息。</span><span class="sxs-lookup"><span data-stu-id="f518e-185">Each PsObject instance contains a single volume recovery key or TPM owner string with its associated computer name, timestamp, and other information required to publish it to the MBAM data store.</span></span>

<span data-ttu-id="f518e-186">**Write-Mbam \ \* cmdlet**按属性名称从管道中接受恢复信息参数值。</span><span class="sxs-lookup"><span data-stu-id="f518e-186">**Write-Mbam\* cmdlets** accept recovery information parameter values from the pipeline by property name.</span></span> <span data-ttu-id="f518e-187">这允许 Write-Mbam \ \* cmdlet 接受 Read 广告 \ \* cmdlet 的管道输出（例如，Read ADRecoveryInformation-Server contoso.com-递归 |Write-MbamRecoveryInformation-RecoveryServiceEndpoint mbam.contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="f518e-187">This allows the Write-Mbam\* cmdlets to accept the pipeline output of the Read-AD\* cmdlets (for example, Read-ADRecoveryInformation –Server contoso.com –Recurse | Write-MbamRecoveryInformation –RecoveryServiceEndpoint mbam.contoso.com).</span></span>

<span data-ttu-id="f518e-188">**Write-Mbam \ \* cmdlet**包括可选参数，这些参数提供容错、详细日志记录和 WhatIf 和确认首选项的选项。</span><span class="sxs-lookup"><span data-stu-id="f518e-188">The **Write-Mbam\* cmdlets** include optional parameters that provide options for fault tolerance, verbose logging, and preferences for WhatIf and Confirm.</span></span>

<span data-ttu-id="f518e-189">**Write Mbam \ \* cmdlet**还包括值为**DateTime**对象的可选*Time*参数。</span><span class="sxs-lookup"><span data-stu-id="f518e-189">The **Write-Mbam\* cmdlets** also include an optional *Time* parameter whose value is a **DateTime** object.</span></span> <span data-ttu-id="f518e-190">此对象包括可设置为、或的*Kind*属性 `Local` `UTC` `Unspecified` 。</span><span class="sxs-lookup"><span data-stu-id="f518e-190">This object includes a *Kind* attribute that can be set to `Local`, `UTC`, or `Unspecified`.</span></span> <span data-ttu-id="f518e-191">当使用从 Active Directory 中获取的数据填充*时间*参数时，时间将转换为 UTC，并且此*Kind*属性将自动设置为 `UTC` 。</span><span class="sxs-lookup"><span data-stu-id="f518e-191">When the *Time* parameter is populated from data taken from the Active Directory, the time is converted to UTC and this *Kind* attribute is set automatically to `UTC`.</span></span> <span data-ttu-id="f518e-192">但是，当使用另一个源（如文本文件）填充*时间*参数时，必须将*Kind*属性显式设置为相应值。</span><span class="sxs-lookup"><span data-stu-id="f518e-192">However, when populating the *Time* parameter using another source, such as a text file, you must explicitly set the *Kind* attribute to its appropriate value.</span></span>

<span data-ttu-id="f518e-193">**注意** 已读广告 \ \* cmdlet 不能发现代表计算机用户的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="f518e-193">**Note** The Read-AD\* cmdlets do not have the ability to discover the user accounts that represent the computer users.</span></span> <span data-ttu-id="f518e-194">以下情况需要用户帐户关联：</span><span class="sxs-lookup"><span data-stu-id="f518e-194">User account associations are needed for the following:</span></span>

-   <span data-ttu-id="f518e-195">用户使用自助服务门户恢复卷密码/程序包</span><span class="sxs-lookup"><span data-stu-id="f518e-195">Users to recover volume passwords/packages by using the Self-Service portal</span></span>

-   <span data-ttu-id="f518e-196">在安装期间未在 MBAM 高级支持人员用户安全组中定义的用户，代表其他用户进行恢复</span><span class="sxs-lookup"><span data-stu-id="f518e-196">Users who are not in the MBAM Advanced Helpdesk Users security group as defined during installation, recovering on behalf of other users</span></span>

 

## <a href="" id="bkmk-autounlock"></a><span data-ttu-id="f518e-197">将 MBAM 配置为在锁定后自动解锁 TPM</span><span class="sxs-lookup"><span data-stu-id="f518e-197">Configure MBAM to automatically unlock the TPM after a lockout</span></span>


<span data-ttu-id="f518e-198">你可以将 MBAM 2.5 SP1 配置为在锁定时自动解锁 TPM。</span><span class="sxs-lookup"><span data-stu-id="f518e-198">You can configure MBAM 2.5 SP1 to automatically unlock the TPM in case of a lockout.</span></span> <span data-ttu-id="f518e-199">如果启用了 TPM 锁定自动重置，MBAM 可以检测到用户已被锁定，然后获取 MBAM 数据库中的 OwnerAuth 密码，以自动解锁用户的 TPM。</span><span class="sxs-lookup"><span data-stu-id="f518e-199">If TPM lockout auto reset is enabled, MBAM can detect that a user is locked out and then get the OwnerAuth password from the MBAM database to automatically unlock the TPM for the user.</span></span> <span data-ttu-id="f518e-200">仅当使用自助服务门户或管理和监视网站检索该计算机的操作系统恢复密钥时，TPM 锁定自动重置才可用。</span><span class="sxs-lookup"><span data-stu-id="f518e-200">TPM lockout auto reset is only available if the OS recovery key for that computer was retrieved by using the Self Service Portal or the Administration and Monitoring Website.</span></span>

<span data-ttu-id="f518e-201">**重要提示** 若要启用 TPM 锁定自动重置，必须在服务器端和客户端上的组策略中配置此功能。</span><span class="sxs-lookup"><span data-stu-id="f518e-201">**Important** To enable TPM lockout auto reset, you must configure this feature on both the server side and in Group Policy on the client side.</span></span>

 

-   <span data-ttu-id="f518e-202">若要在客户端启用 TPM 锁定自动重置，请在 "**计算机配置**" &gt; **管理模板** &gt; **Windows 组件** &gt; **MDOP MBAM** &gt; **客户端管理**中配置组策略设置 "配置 TPM 锁定自动重置"。</span><span class="sxs-lookup"><span data-stu-id="f518e-202">To enable TPM lockout auto reset on the client side, configure the Group Policy setting "Configure TPM lockout auto reset" located at **Computer Configuration** &gt; **Administrative Templates** &gt; **Windows Components** &gt; **MDOP MBAM** &gt; **Client Management**.</span></span>

-   <span data-ttu-id="f518e-203">若要在服务器端启用 TPM 锁定自动重置，可以在安装期间在 MBAM Server 配置向导中选中 "启用 TPM 锁定自动重置"。</span><span class="sxs-lookup"><span data-stu-id="f518e-203">To enable TPM lockout auto reset on the server side, you can check "Enable TPM lockout auto reset" in the MBAM Server Configuration wizard during setup.</span></span>

    <span data-ttu-id="f518e-204">你还可以通过在启用代理服务 web 组件时指定 "-TPM 锁定自动重置" 切换器，在 PowerShell 中启用 TPM 锁定自动重置。</span><span class="sxs-lookup"><span data-stu-id="f518e-204">You can also enable TPM lockout auto reset in PowerShell by specifying the "-TPM lockout auto reset" switch while enabling the agent service web component.</span></span>

<span data-ttu-id="f518e-205">用户输入从自助服务门户或管理和监视网站获取的 BitLocker 恢复密钥后，MBAM 代理将确定 TPM 是否已锁定。如果它已被锁定，它将尝试从 MBAM 数据库检索计算机的 TPM OwnerAuth。</span><span class="sxs-lookup"><span data-stu-id="f518e-205">After a user enters the BitLocker recovery key they obtained from the Self Service Portal or the Administration and Monitoring Website, the MBAM agent will determine if the TPM is locked out. If it is locked out, it will attempt to retrieve the TPM OwnerAuth for the computer from the MBAM database.</span></span> <span data-ttu-id="f518e-206">如果 TPM OwnerAuth 已成功检索，它将用于解锁 TPM。</span><span class="sxs-lookup"><span data-stu-id="f518e-206">If the TPM OwnerAuth is successfully retrieved, it will be used to unlock the TPM.</span></span> <span data-ttu-id="f518e-207">解锁 TPM 将使 TPM 完全正常工作，并且不会强制用户在从 TPM 锁定的后续重启过程中输入恢复密码。</span><span class="sxs-lookup"><span data-stu-id="f518e-207">Unlocking the TPM makes the TPM fully functional and the user will not be forced to enter the recovery password during subsequent reboots from a TPM lockout.</span></span>

<span data-ttu-id="f518e-208">默认情况下，将禁用 TPM 锁定自动重置。</span><span class="sxs-lookup"><span data-stu-id="f518e-208">TPM lockout auto reset is disabled by default.</span></span>

<span data-ttu-id="f518e-209">**注意** 仅在运行 TPM 版本1.2 的计算机上支持 TPM 锁定自动重置。</span><span class="sxs-lookup"><span data-stu-id="f518e-209">**Note** TPM lockout auto reset is only supported on computers running TPM version 1.2.</span></span> <span data-ttu-id="f518e-210">TPM 2.0 提供了内置的锁定自动重置功能。</span><span class="sxs-lookup"><span data-stu-id="f518e-210">TPM 2.0 provides built-in lockout auto reset functionality.</span></span>

 

<span data-ttu-id="f518e-211">**恢复审核报告**包括与 TPM 锁定自动重置相关的事件。</span><span class="sxs-lookup"><span data-stu-id="f518e-211">**The Recovery Audit Report** includes events related to TPM lockout auto reset.</span></span> <span data-ttu-id="f518e-212">如果从 MBAM 客户端发出请求以检索 TPM OwnerAuth 密码，则会记录一个事件以指示恢复。</span><span class="sxs-lookup"><span data-stu-id="f518e-212">If a request is made from the MBAM client to retrieve a TPM OwnerAuth password, an event is logged to indicate recovery.</span></span> <span data-ttu-id="f518e-213">审核条目将包括以下事件：</span><span class="sxs-lookup"><span data-stu-id="f518e-213">Audit entries will include the following events:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="f518e-214">Entry</span><span class="sxs-lookup"><span data-stu-id="f518e-214">Entry</span></span></th>
<th align="left"><span data-ttu-id="f518e-215">值</span><span class="sxs-lookup"><span data-stu-id="f518e-215">Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f518e-216">审核请求源</span><span class="sxs-lookup"><span data-stu-id="f518e-216">Audit Request Source</span></span></p></td>
<td align="left"><p><span data-ttu-id="f518e-217">代理 TPM 解锁</span><span class="sxs-lookup"><span data-stu-id="f518e-217">Agent TPM unlock</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f518e-218">键类型</span><span class="sxs-lookup"><span data-stu-id="f518e-218">Key Type</span></span></p></td>
<td align="left"><p><span data-ttu-id="f518e-219">TPM 密码哈希</span><span class="sxs-lookup"><span data-stu-id="f518e-219">TPM Password Hash</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f518e-220">原因描述</span><span class="sxs-lookup"><span data-stu-id="f518e-220">Reason Description</span></span></p></td>
<td align="left"><p><span data-ttu-id="f518e-221">TPM 重置</span><span class="sxs-lookup"><span data-stu-id="f518e-221">TPM Reset</span></span></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-secure-databases"></a><span data-ttu-id="f518e-222">连接到 SQL Server 的安全连接</span><span class="sxs-lookup"><span data-stu-id="f518e-222">Secure connections to SQL Server</span></span>


<span data-ttu-id="f518e-223">在 MBAM 中，SQL Server 与 SQL Server Reporting Services 以及用于管理和监视网站和自助服务门户的 web 服务进行通信。</span><span class="sxs-lookup"><span data-stu-id="f518e-223">In MBAM, SQL Server communicates with SQL Server Reporting Services and with the web services for the Administration and Monitoring Website and Self-Service Portal.</span></span> <span data-ttu-id="f518e-224">我们建议您确保与 SQL Server 的通信安全。</span><span class="sxs-lookup"><span data-stu-id="f518e-224">We recommend that you secure the communication with SQL Server.</span></span> <span data-ttu-id="f518e-225">有关详细信息，请参阅[加密到 SQL Server 的连接](https://technet.microsoft.com/library/ms189067.aspx)。</span><span class="sxs-lookup"><span data-stu-id="f518e-225">For more information, see [Encrypting Connections to SQL Server](https://technet.microsoft.com/library/ms189067.aspx).</span></span>

<span data-ttu-id="f518e-226">有关保护 MBAM 网站安全的详细信息，请参阅[规划如何保护 MBAM 网站的安全](planning-how-to-secure-the-mbam-websites.md)。</span><span class="sxs-lookup"><span data-stu-id="f518e-226">For more information about securing the MBAM websites, see [Planning How to Secure the MBAM Websites](planning-how-to-secure-the-mbam-websites.md).</span></span>

## <a href="" id="bkmk-accts-groups"></a><span data-ttu-id="f518e-227">创建帐户和组</span><span class="sxs-lookup"><span data-stu-id="f518e-227">Create accounts and groups</span></span>


<span data-ttu-id="f518e-228">管理用户帐户的最佳做法是创建域全局组并向其添加用户帐户。</span><span class="sxs-lookup"><span data-stu-id="f518e-228">The best practice for managing user accounts is to create domain global groups and add user accounts to them.</span></span> <span data-ttu-id="f518e-229">有关推荐的帐户和组的说明，请参阅[规划 MBAM 2.5 组和帐户](planning-for-mbam-25-groups-and-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="f518e-229">For a description of the recommended accounts and groups, see [Planning for MBAM 2.5 Groups and Accounts](planning-for-mbam-25-groups-and-accounts.md).</span></span>

## <a href="" id="bkmk-logfiles"></a><span data-ttu-id="f518e-230">使用 MBAM 日志文件</span><span class="sxs-lookup"><span data-stu-id="f518e-230">Use MBAM log files</span></span>


<span data-ttu-id="f518e-231">本部分介绍 MBAM 服务器和 MBAM 客户端日志文件。</span><span class="sxs-lookup"><span data-stu-id="f518e-231">This section describes the MBAM Server and MBAM Client log files.</span></span>

**<span data-ttu-id="f518e-232">MBAM Server 安装程序日志文件</span><span class="sxs-lookup"><span data-stu-id="f518e-232">MBAM Server Setup log files</span></span>**

<span data-ttu-id="f518e-233">在 MBAM 安装期间， **MBAMServerSetup.exe**文件将在用户的 **% temp%** 文件夹中生成以下日志文件：</span><span class="sxs-lookup"><span data-stu-id="f518e-233">The **MBAMServerSetup.exe** file generates the following log files in the user’s **%temp%** folder during the MBAM installation:</span></span>

-   **<span data-ttu-id="f518e-234">Microsoft \ _BitLocker \ _Administration \ _and \ _Monitoring \ \ &lt; 14 号码 &gt; 。日志</span><span class="sxs-lookup"><span data-stu-id="f518e-234">Microsoft\_BitLocker\_Administration\_and\_Monitoring\_&lt;14 numbers&gt;.log</span></span>**

    <span data-ttu-id="f518e-235">记录在 MBAM 设置和 MBAM 服务器功能配置期间执行的操作。</span><span class="sxs-lookup"><span data-stu-id="f518e-235">Logs the actions taken during the MBAM setup and the MBAM Server feature configuration.</span></span>

-   **<span data-ttu-id="f518e-236">Microsoft \ _BitLocker \ _Administration \ _and \ _Monitoring \ _ &lt; 14 \ _numbers &gt;\_0\_MBAMServer.msi</span><span class="sxs-lookup"><span data-stu-id="f518e-236">Microsoft\_BitLocker\_Administration\_and\_Monitoring\_&lt;14\_numbers&gt;\_0\_MBAMServer.msi.log</span></span>**

    <span data-ttu-id="f518e-237">记录安装期间执行的其他操作。</span><span class="sxs-lookup"><span data-stu-id="f518e-237">Logs additional action taken during installation.</span></span>

**<span data-ttu-id="f518e-238">MBAM 服务器配置日志文件</span><span class="sxs-lookup"><span data-stu-id="f518e-238">MBAM Server Configuration log files</span></span>**

-   **<span data-ttu-id="f518e-239">应用程序和服务日志/Microsoft Windows/MBAM-设置</span><span class="sxs-lookup"><span data-stu-id="f518e-239">Applications and Services Logs/Microsoft Windows/MBAM-Setup</span></span>**

    <span data-ttu-id="f518e-240">记录使用 Windows Powershell cmdlet 或 MBAM Server 配置向导配置 MBAM 服务器功能时出现的错误。</span><span class="sxs-lookup"><span data-stu-id="f518e-240">Logs the errors that occur when you are using Windows Powershell cmdlets or the MBAM Server Configuration wizard to configure the MBAM Server features.</span></span>

**<span data-ttu-id="f518e-241">MBAM 客户端安装程序日志文件</span><span class="sxs-lookup"><span data-stu-id="f518e-241">MBAM Client setup log files</span></span>**

-   **<span data-ttu-id="f518e-242">MSI &lt; 5 个随机字符 &gt; 。日志</span><span class="sxs-lookup"><span data-stu-id="f518e-242">MSI&lt;five random characters&gt;.log</span></span>**

    <span data-ttu-id="f518e-243">记录在 MBAM 客户端安装期间执行的操作。</span><span class="sxs-lookup"><span data-stu-id="f518e-243">Logs the actions taken during the MBAM Client installation.</span></span>

**<span data-ttu-id="f518e-244">MBAM-Web 日志文件</span><span class="sxs-lookup"><span data-stu-id="f518e-244">MBAM-Web log files</span></span>**

-   <span data-ttu-id="f518e-245">显示来自 web 门户和服务的活动。</span><span class="sxs-lookup"><span data-stu-id="f518e-245">Shows activity from the web portals and services.</span></span>

## <a href="" id="bkmk-tde"></a><span data-ttu-id="f518e-246">查看 MBAM 数据库 TDE 注意事项</span><span class="sxs-lookup"><span data-stu-id="f518e-246">Review MBAM database TDE considerations</span></span>


<span data-ttu-id="f518e-247">SQL Server 中可用的透明数据加密（TDE）功能是用于承载 MBAM 数据库功能的数据库实例的可选安装。</span><span class="sxs-lookup"><span data-stu-id="f518e-247">The transparent data encryption (TDE) feature that is available in SQL Server is an optional installation for the database instances that will host the MBAM database features.</span></span>

<span data-ttu-id="f518e-248">通过 TDE，你可以执行实时、完整数据库级别的加密。</span><span class="sxs-lookup"><span data-stu-id="f518e-248">With TDE, you can perform real-time, full database-level encryption.</span></span> <span data-ttu-id="f518e-249">TDE 是批量加密的最佳选择，可满足法规遵从性或公司数据安全标准。</span><span class="sxs-lookup"><span data-stu-id="f518e-249">TDE is the optimal choice for bulk encryption to meet regulatory compliance or corporate data security standards.</span></span> <span data-ttu-id="f518e-250">TDE 适用于文件级别，它类似于两个 Windows 功能：加密文件系统（EFS）和 BitLocker 驱动器加密。</span><span class="sxs-lookup"><span data-stu-id="f518e-250">TDE works at the file level, which is similar to two Windows features: the Encrypting File System (EFS) and BitLocker Drive Encryption.</span></span> <span data-ttu-id="f518e-251">这两种功能还会加密硬盘上的数据。</span><span class="sxs-lookup"><span data-stu-id="f518e-251">Both features also encrypt data on the hard drive.</span></span> <span data-ttu-id="f518e-252">TDE 不会替换单元级加密、EFS 或 BitLocker。</span><span class="sxs-lookup"><span data-stu-id="f518e-252">TDE does not replace cell-level encryption, EFS, or BitLocker.</span></span>

<span data-ttu-id="f518e-253">在数据库上启用 TDE 时，将加密所有备份。</span><span class="sxs-lookup"><span data-stu-id="f518e-253">When TDE is enabled on a database, all backups are encrypted.</span></span> <span data-ttu-id="f518e-254">因此，必须特别注意才能确保使用数据库备份对用于保护数据库加密密钥的证书进行备份和维护。</span><span class="sxs-lookup"><span data-stu-id="f518e-254">Thus, special care must be taken to ensure that the certificate that was used to protect the database encryption key is backed up and maintained with the database backup.</span></span> <span data-ttu-id="f518e-255">如果此证书（或证书）丢失，则数据将不可读。</span><span class="sxs-lookup"><span data-stu-id="f518e-255">If this certificate (or certificates) is lost, the data will be unreadable.</span></span>

<span data-ttu-id="f518e-256">备份数据库中的证书。</span><span class="sxs-lookup"><span data-stu-id="f518e-256">Back up the certificate with the database.</span></span> <span data-ttu-id="f518e-257">每个证书备份都应具有两个文件。</span><span class="sxs-lookup"><span data-stu-id="f518e-257">Each certificate backup should have two files.</span></span> <span data-ttu-id="f518e-258">这两个文件都应存档。</span><span class="sxs-lookup"><span data-stu-id="f518e-258">Both of these files should be archived.</span></span> <span data-ttu-id="f518e-259">理想情况下，应将其与数据库备份文件分开备份。</span><span class="sxs-lookup"><span data-stu-id="f518e-259">Ideally for security, they should be backed up separately from the database backup file.</span></span> <span data-ttu-id="f518e-260">您也可以考虑使用可扩展密钥管理（EKM）功能（请参阅可扩展密钥管理）存储和维护用于 TDE 的密钥。</span><span class="sxs-lookup"><span data-stu-id="f518e-260">You can alternatively consider using the extensible key management (EKM) feature (see Extensible Key Management) for storage and maintenance of keys that are used for TDE.</span></span>

<span data-ttu-id="f518e-261">有关如何为 MBAM 数据库实例启用 TDE 的示例，请参阅[了解透明数据加密（TDE）](https://technet.microsoft.com/library/bb934049.aspx)。</span><span class="sxs-lookup"><span data-stu-id="f518e-261">For an example of how to enable TDE for MBAM database instances, see [Understanding Transparent Data Encryption (TDE)](https://technet.microsoft.com/library/bb934049.aspx).</span></span>

## <a href="" id="bkmk-general-security"></a><span data-ttu-id="f518e-262">了解常规安全注意事项</span><span class="sxs-lookup"><span data-stu-id="f518e-262">Understand general security considerations</span></span>


**<span data-ttu-id="f518e-263">了解安全风险。</span><span class="sxs-lookup"><span data-stu-id="f518e-263">Understand the security risks.</span></span>** <span data-ttu-id="f518e-264">使用 Microsoft BitLocker 管理和监视时，最严重的风险是，未经授权的用户可能会泄漏其功能，这样就可以在 MBAM 客户端上重新配置 BitLocker 驱动器加密和获取 BitLocker 加密密钥数据。</span><span class="sxs-lookup"><span data-stu-id="f518e-264">The most serious risk when you use Microsoft BitLocker Administration and Monitoring is that its functionality could be compromised by an unauthorized user who could then reconfigure BitLocker Drive Encryption and gain BitLocker encryption key data on MBAM Clients.</span></span> <span data-ttu-id="f518e-265">但是，由于拒绝服务攻击而导致的 MBAM 功能的损失通常不会产生灾难性影响，例如，丢失电子邮件或网络通信，或使用电源。</span><span class="sxs-lookup"><span data-stu-id="f518e-265">However, the loss of MBAM functionality for a short period of time, due to a denial-of-service attack, does not generally have a catastrophic impact, unlike, for example, losing e-mail or network communications, or power.</span></span>

<span data-ttu-id="f518e-266">**确保计算机的物理安全**。</span><span class="sxs-lookup"><span data-stu-id="f518e-266">**Physically secure your computers**.</span></span> <span data-ttu-id="f518e-267">没有物理安全的安全性。</span><span class="sxs-lookup"><span data-stu-id="f518e-267">There is no security without physical security.</span></span> <span data-ttu-id="f518e-268">获得 MBAM 服务器物理访问权限的攻击者可能会使用它来攻击整个客户端。</span><span class="sxs-lookup"><span data-stu-id="f518e-268">An attacker who gets physical access to an MBAM Server could potentially use it to attack the entire client base.</span></span> <span data-ttu-id="f518e-269">所有潜在的物理攻击都必须被视为高风险并相应地缓解。</span><span class="sxs-lookup"><span data-stu-id="f518e-269">All potential physical attacks must be considered high risk and mitigated appropriately.</span></span> <span data-ttu-id="f518e-270">MBAM 服务器应存储在具有受控访问权限的安全服务器机房中。</span><span class="sxs-lookup"><span data-stu-id="f518e-270">MBAM Servers should be stored in a secure server room with controlled access.</span></span> <span data-ttu-id="f518e-271">通过让操作系统锁定计算机，或使用安全的屏幕保护程序，确保管理员不在物理上显示这些计算机。</span><span class="sxs-lookup"><span data-stu-id="f518e-271">Secure these computers when administrators are not physically present by having the operating system lock the computer, or by using a secured screen saver.</span></span>

<span data-ttu-id="f518e-272">**对所有计算机应用最新的安全更新**。</span><span class="sxs-lookup"><span data-stu-id="f518e-272">**Apply the most recent security updates to all computers**.</span></span> <span data-ttu-id="f518e-273">通过在[安全技术中心](https://go.microsoft.com/fwlink/?LinkId=28819)订阅安全通知服务，随时了解 Windows 操作系统、SQL SERVER 和 MBAM 的新更新。</span><span class="sxs-lookup"><span data-stu-id="f518e-273">Stay informed about new updates for Windows operating systems, SQL Server, and MBAM by subscribing to the Security Notification service at the [Security TechCenter](https://go.microsoft.com/fwlink/?LinkId=28819).</span></span>

<span data-ttu-id="f518e-274">**使用强密码或密码短语**。</span><span class="sxs-lookup"><span data-stu-id="f518e-274">**Use strong passwords or pass phrases**.</span></span> <span data-ttu-id="f518e-275">始终对所有 MBAM 管理员帐户使用具有15个或更多字符的强密码。</span><span class="sxs-lookup"><span data-stu-id="f518e-275">Always use strong passwords with 15 or more characters for all MBAM administrator accounts.</span></span> <span data-ttu-id="f518e-276">千万不要使用空白密码。</span><span class="sxs-lookup"><span data-stu-id="f518e-276">Never use blank passwords.</span></span> <span data-ttu-id="f518e-277">有关密码概念的详细信息，请参阅[密码策略](https://technet.microsoft.com/library/hh994572.aspx)。</span><span class="sxs-lookup"><span data-stu-id="f518e-277">For more information about password concepts, see [Password Policy](https://technet.microsoft.com/library/hh994572.aspx).</span></span>



## <span data-ttu-id="f518e-278">相关主题</span><span class="sxs-lookup"><span data-stu-id="f518e-278">Related topics</span></span>


[<span data-ttu-id="f518e-279">规划部署 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="f518e-279">Planning to Deploy MBAM 2.5</span></span>](planning-to-deploy-mbam-25.md)

 
## <span data-ttu-id="f518e-280">已获得 MBAM 的建议？</span><span class="sxs-lookup"><span data-stu-id="f518e-280">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="f518e-281">在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="f518e-281">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span>
- <span data-ttu-id="f518e-282">对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="f518e-282">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>
 





