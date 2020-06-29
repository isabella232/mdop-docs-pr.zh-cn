---
title: 使用 Windows PowerShell 配置 MBAM 2.5 服务器功能
description: 使用 Windows PowerShell 配置 MBAM 2.5 服务器功能
author: dansimp
ms.assetid: 826429fd-29bb-44be-b47e-5f5c7d20dd1d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: f350a9eb96a20f50644cfdc1965b7f72741a2c29
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803248"
---
# <span data-ttu-id="e1a3f-103">使用 Windows PowerShell 配置 MBAM 2.5 服务器功能</span><span class="sxs-lookup"><span data-stu-id="e1a3f-103">Configuring MBAM 2.5 Server Features by Using Windows PowerShell</span></span>


<span data-ttu-id="e1a3f-104">在安装 MBAM 2.5 服务器软件后，您可以使用 Windows PowerShell cmdlet 或 "MBAM 服务器配置向导" 配置 MBAM 2.5 服务器功能。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-104">After you install the MBAM 2.5 Server software, you can use configure MBAM 2.5 Server features by using Windows PowerShell cmdlets or the MBAM Server Configuration wizard.</span></span> <span data-ttu-id="e1a3f-105">本主题介绍如何使用 Windows PowerShell cmdlet 配置 MBAM 2.5。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-105">This topic describes how to configure MBAM 2.5 by using the Windows PowerShell cmdlets.</span></span> <span data-ttu-id="e1a3f-106">若要改为使用该向导，请参阅[配置 MBAM 2.5 服务器功能](configuring-the-mbam-25-server-features.md)。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-106">To use the wizard instead, see [Configuring the MBAM 2.5 Server Features](configuring-the-mbam-25-server-features.md).</span></span>

## <span data-ttu-id="e1a3f-107">本主题内容</span><span class="sxs-lookup"><span data-stu-id="e1a3f-107">In this topic</span></span>


<span data-ttu-id="e1a3f-108">本主题包括有关使用 Windows PowerShell 配置 MBAM 的以下信息：</span><span class="sxs-lookup"><span data-stu-id="e1a3f-108">This topic includes the following information about using Windows PowerShell to configure MBAM:</span></span>

-   [<span data-ttu-id="e1a3f-109">如何加载 MBAM 2.5 的 Windows PowerShell 帮助</span><span class="sxs-lookup"><span data-stu-id="e1a3f-109">How to load Windows PowerShell Help for MBAM 2.5</span></span>](#bkmk-load-posh-help)

-   [<span data-ttu-id="e1a3f-110">如何获取有关 MBAM Windows PowerShell cmdlet 的帮助</span><span class="sxs-lookup"><span data-stu-id="e1a3f-110">How to get Help about an MBAM Windows PowerShell cmdlet</span></span>](#bkmk-help-specific-cmdlet)

-   [<span data-ttu-id="e1a3f-111">只能在 Windows PowerShell 中执行但不能通过 MBAM Server 配置向导执行的配置</span><span class="sxs-lookup"><span data-stu-id="e1a3f-111">Configurations that you can do only with Windows PowerShell but not with the MBAM Server Configuration wizard</span></span>](#bkmk-config-only-posh)

-   [<span data-ttu-id="e1a3f-112">使用 Windows PowerShell 配置 MBAM Server 功能的先决条件和要求</span><span class="sxs-lookup"><span data-stu-id="e1a3f-112">Prerequisites and requirements for using Windows PowerShell to configure MBAM Server features</span></span>](#bkmk-prereqs-posh-mbamsvr)

-   [<span data-ttu-id="e1a3f-113">在远程计算机上使用 Windows PowerShell 配置 MBAM</span><span class="sxs-lookup"><span data-stu-id="e1a3f-113">Using Windows PowerShell to configure MBAM on a remote computer</span></span>](#bkmk-remote-config)

-   [<span data-ttu-id="e1a3f-114">必需帐户和相应的 Windows PowerShell cmdlet 参数</span><span class="sxs-lookup"><span data-stu-id="e1a3f-114">Required accounts and corresponding Windows PowerShell cmdlet parameters</span></span>](#bkmk-reqd-posh-accts)

<span data-ttu-id="e1a3f-115">有关用于管理 MBAM 的**MbamBitLockerRecoveryKey**和**MbamTPMOwnerPassword** Windows PowerShell cmdlet 的信息，请参阅[使用 Windows PowerShell 管理 MBAM 2.5](using-windows-powershell-to-administer-mbam-25.md)。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-115">For information about the **Get-MbamBitLockerRecoveryKey** and **Get-MbamTPMOwnerPassword** Windows PowerShell cmdlets, which are used to administer MBAM, see [Using Windows PowerShell to Administer MBAM 2.5](using-windows-powershell-to-administer-mbam-25.md).</span></span>

## <a href="" id="bkmk-load-posh-help"></a><span data-ttu-id="e1a3f-116">如何加载 MBAM 2.5 的 Windows PowerShell 帮助</span><span class="sxs-lookup"><span data-stu-id="e1a3f-116">How to load Windows PowerShell Help for MBAM 2.5</span></span>


<span data-ttu-id="e1a3f-117">有关 TechNet 上的 Windows PowerShell cmdlet 的列表，请参阅[使用 Windows PowerShell 的 Microsoft 桌面优化包自动化](https://go.microsoft.com/fwlink/?LinkId=392816)。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-117">For a list of the Windows PowerShell cmdlets on TechNet, see [Microsoft Desktop Optimization Pack Automation with Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=392816).</span></span>

**<span data-ttu-id="e1a3f-118">在安装 MBAM 服务器软件后加载适用于 Windows PowerShell cmdlet 的 MBAM 2.5 帮助</span><span class="sxs-lookup"><span data-stu-id="e1a3f-118">To load the MBAM 2.5 Help for Windows PowerShell cmdlets after installing the MBAM Server software</span></span>**

1.  <span data-ttu-id="e1a3f-119">打开 Windows PowerShell 或 Windows PowerShell 集成脚本环境（ISE）。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-119">Open Windows PowerShell or Windows PowerShell Integrated Scripting Environment (ISE).</span></span>

2.  <span data-ttu-id="e1a3f-120">类型**更新-帮助-MBAM**。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-120">Type **Update-Help –Module Microsoft.MBAM**.</span></span>

## <a href="" id="bkmk-help-specific-cmdlet"></a><span data-ttu-id="e1a3f-121">如何获取有关 MBAM Windows PowerShell cmdlet 的帮助</span><span class="sxs-lookup"><span data-stu-id="e1a3f-121">How to get Help about an MBAM Windows PowerShell cmdlet</span></span>


<span data-ttu-id="e1a3f-122">适用于 MBAM 的 Windows PowerShell 帮助有以下格式：</span><span class="sxs-lookup"><span data-stu-id="e1a3f-122">Windows PowerShell Help for MBAM is available in the following formats:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e1a3f-123">Windows PowerShell 帮助格式</span><span class="sxs-lookup"><span data-stu-id="e1a3f-123">Windows PowerShell Help format</span></span></th>
<th align="left"><span data-ttu-id="e1a3f-124">详细信息</span><span class="sxs-lookup"><span data-stu-id="e1a3f-124">More information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e1a3f-125">在 Windows PowerShell 命令提示符处，键入 <strong> get-help </strong> &lt; <em> cmdlet</em>&gt;</span><span class="sxs-lookup"><span data-stu-id="e1a3f-125">At a Windows PowerShell command prompt, type <strong>Get-Help</strong> &lt;<em>cmdlet</em>&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="e1a3f-126">若要上载最新的 Windows PowerShell cmdlet，请按照上一节中关于如何加载 MBAM 的 Windows PowerShell 帮助中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-126">To upload the latest Windows PowerShell cmdlets, follow the instructions in the previous section on how to load Windows PowerShell Help for MBAM.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e1a3f-127">在 TechNet 上作为网页</span><span class="sxs-lookup"><span data-stu-id="e1a3f-127">On TechNet as webpages</span></span></p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=393498" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=393498">https://go.microsoft.com/fwlink/?LinkId=393498</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e1a3f-128">在下载中心中作为单词表文件</span><span class="sxs-lookup"><span data-stu-id="e1a3f-128">On the Download Center as a Word .docx file</span></span></p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=393497" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=393497">https://go.microsoft.com/fwlink/?LinkId=393497</a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e1a3f-129">在下载中心中作为 .pdf 文件</span><span class="sxs-lookup"><span data-stu-id="e1a3f-129">On the Download Center as a .pdf file</span></span></p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=393499" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=393499">https://go.microsoft.com/fwlink/?LinkId=393499</a></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-config-only-posh"></a><span data-ttu-id="e1a3f-130">只能在 Windows PowerShell 中执行但不能通过 MBAM Server 配置向导执行的配置</span><span class="sxs-lookup"><span data-stu-id="e1a3f-130">Configurations that you can do only with Windows PowerShell but not with the MBAM Server Configuration wizard</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e1a3f-131">只能使用 Windows PowerShell 执行的配置</span><span class="sxs-lookup"><span data-stu-id="e1a3f-131">Configurations that you can do only by using Windows PowerShell</span></span></th>
<th align="left"><span data-ttu-id="e1a3f-132">详细信息</span><span class="sxs-lookup"><span data-stu-id="e1a3f-132">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e1a3f-133">从 web 应用程序在单独的计算机上安装 web 服务。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-133">Install the web services on a separate computer from the web applications.</span></span></p></td>
<td align="left"><p><span data-ttu-id="e1a3f-134">使用该向导，必须在同一台计算机上安装 web 服务和 web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-134">Using the wizard, you must install the web services and web applications on the same computer.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e1a3f-135">在单独的报告服务点上启用报告，而不安装所有配置管理器对象。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-135">Enable reports on a separate reporting services point without installing all of the Configuration Manager objects.</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e1a3f-136">从 Configuration Manager 中删除所有对象。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-136">Delete all of the objects from Configuration Manager.</span></span></p></td>
<td align="left"><p><span data-ttu-id="e1a3f-137">删除对象依次删除配置管理器中的所有合规性数据。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-137">Deleting the objects in turn deletes all of the compliance data from Configuration Manager.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e1a3f-138">为数据库输入自定义连接字符串。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-138">Enter a custom connection string for the databases.</span></span></p></td>
<td align="left"><p><span data-ttu-id="e1a3f-139">示例：若要将 web 应用程序配置为使用镜像，必须使用 <strong> Enable-MbamWebApplication </strong> cmdlet 指定连接字符串中的相应故障转移合作伙伴语法。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-139">Example: To configure the web applications to work with mirroring, you must use the <strong>Enable-MbamWebApplication</strong> cmdlet to specify the appropriate failover partner syntax in the connection string.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e1a3f-140">即使先决条件检查失败，也跳过验证和配置功能。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-140">Skip validation and configure a feature even though the prerequisite check failed.</span></span></p></td>
<td align="left"></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="e1a3f-141">**注意** 不能使用 Windows PowerShell cmdlet 或 MBAM 服务器配置向导禁用 MBAM 数据库。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-141">**Note** You cannot disable the MBAM databases with a Windows PowerShell cmdlet or the MBAM Server Configuration wizard.</span></span> <span data-ttu-id="e1a3f-142">为了防止意外删除合规性和审核数据，数据库管理员必须手动删除数据库。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-142">To prevent the accidental removal of your compliance and audit data, database administrators must remove databases manually.</span></span>

 

## <a href="" id="bkmk-prereqs-posh-mbamsvr"></a><span data-ttu-id="e1a3f-143">使用 Windows PowerShell 配置 MBAM Server 功能的先决条件和要求</span><span class="sxs-lookup"><span data-stu-id="e1a3f-143">Prerequisites and requirements for using Windows PowerShell to configure MBAM Server features</span></span>


<span data-ttu-id="e1a3f-144">开始配置之前，请完成以下先决条件。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-144">Before starting the configuration, complete the following prerequisites.</span></span>

**<span data-ttu-id="e1a3f-145">与客户相关的先决条件</span><span class="sxs-lookup"><span data-stu-id="e1a3f-145">Account-related prerequisites</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e1a3f-146">必备</span><span class="sxs-lookup"><span data-stu-id="e1a3f-146">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="e1a3f-147">详细信息或其他信息</span><span class="sxs-lookup"><span data-stu-id="e1a3f-147">Details or additional information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e1a3f-148">创建所需帐户。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-148">Create the required accounts.</span></span></p></td>
<td align="left"><p><span data-ttu-id="e1a3f-149">请参阅 <strong> 本主题后面部分的所需帐户和相应的 Windows PowerShell cmdlet 参数 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-149">See section <strong>Required accounts and corresponding Windows PowerShell cmdlet parameters</strong> later in this topic.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e1a3f-150">作为参数传递到 Windows PowerShell cmdlet 的用户帐户和组必须是域中的有效帐户。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-150">User accounts and groups that you pass as parameters to the Windows PowerShell cmdlets must be valid accounts in the domain.</span></span></p></td>
<td align="left"><p><span data-ttu-id="e1a3f-151">您不能使用本地帐户。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-151">You cannot use local accounts.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e1a3f-152">以低级格式指定帐户。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-152">Specify accounts in the down-level format.</span></span></p></td>
<td align="left"><p><span data-ttu-id="e1a3f-153">示例：</span><span class="sxs-lookup"><span data-stu-id="e1a3f-153">Examples:</span></span></p>
<p><span data-ttu-id="e1a3f-154">domainNetBiosName\userdomainNetBiosName\group</span><span class="sxs-lookup"><span data-stu-id="e1a3f-154">domainNetBiosName\userdomainNetBiosName\group</span></span></p></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="e1a3f-155">权限相关的先决条件</span><span class="sxs-lookup"><span data-stu-id="e1a3f-155">Permission-related prerequisites</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e1a3f-156">必备</span><span class="sxs-lookup"><span data-stu-id="e1a3f-156">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="e1a3f-157">详细信息或其他信息</span><span class="sxs-lookup"><span data-stu-id="e1a3f-157">Details or additional information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e1a3f-158">您必须是要在其中配置 MBAM 功能的本地计算机上的管理员。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-158">You must be an administrator on the local computer where you are configuring the MBAM feature.</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e1a3f-159">使用提升的 Windows PowerShell 命令提示符运行所有 Windows PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-159">Use an elevated Windows PowerShell command prompt to run all Windows PowerShell cmdlets.</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e1a3f-160"><strong>仅限 Enable-MbamDatabase </strong> cmdlet：</span><span class="sxs-lookup"><span data-stu-id="e1a3f-160">For the <strong>Enable-MbamDatabase</strong> cmdlet only:</span></span></p>
<p><span data-ttu-id="e1a3f-161">您必须对 &quot; &quot; 目标 Microsoft SQL Server 数据库的实例具有 "创建任何数据库权限"。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-161">You must have &quot;create any database&quot; permissions on the instance of the target Microsoft SQL Server database.</span></span></p>
<p><span data-ttu-id="e1a3f-162">此用户帐户必须是本地管理员组或备份操作员组的一部分，才能注册 MBAM 卷影复制服务（VSS）编写器。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-162">This user account must be a part of the local administrators group or the Backup Operators group to register the MBAM Volume Shadow Copy Service (VSS) Writer.</span></span></p></td>
<td align="left"><p><span data-ttu-id="e1a3f-163">默认情况下，数据库管理员或系统管理员具有所需的 &quot; 创建任何数据库 &quot; 权限。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-163">By default, the database administrator or system administrator has the required &quot;create any database&quot; permissions.</span></span></p>
<p></p>
<p><span data-ttu-id="e1a3f-164">有关 VSS 书写器的详细信息，请参阅 <a href="https://go.microsoft.com/fwlink/?LinkId=392814" data-raw-source="[Volume Shadow Copy Service](https://go.microsoft.com/fwlink/?LinkId=392814)"> 卷影复制服务 </a> 。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-164">For more information about VSS Writer, see <a href="https://go.microsoft.com/fwlink/?LinkId=392814" data-raw-source="[Volume Shadow Copy Service](https://go.microsoft.com/fwlink/?LinkId=392814)">Volume Shadow Copy Service</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e1a3f-165">仅适用于 <strong> System Center Configuration Manager 集成 </strong> 功能：</span><span class="sxs-lookup"><span data-stu-id="e1a3f-165">For the <strong>System Center Configuration Manager Integration</strong> feature only:</span></span></p>
<p><span data-ttu-id="e1a3f-166">启用此功能的用户必须在 Configuration Manager 中具有以下权限：</span><span class="sxs-lookup"><span data-stu-id="e1a3f-166">The user who enables this feature must have these rights in Configuration Manager:</span></span></p></td>
<td align="left"><table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e1a3f-167">Configuration Manager 中的权限类型</span><span class="sxs-lookup"><span data-stu-id="e1a3f-167">Type of rights in Configuration Manager</span></span></th>
<th align="left"><span data-ttu-id="e1a3f-168">所需权限</span><span class="sxs-lookup"><span data-stu-id="e1a3f-168">Required rights</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e1a3f-169">Configuration Manager 网站权限：</span><span class="sxs-lookup"><span data-stu-id="e1a3f-169">Configuration Manager Site rights:</span></span></p></td>
<td align="left"><p>- <span data-ttu-id="e1a3f-170">已阅读</span><span class="sxs-lookup"><span data-stu-id="e1a3f-170">Read</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e1a3f-171">Configuration Manager 收集权限：</span><span class="sxs-lookup"><span data-stu-id="e1a3f-171">Configuration Manager Collection rights:</span></span></p></td>
<td align="left"><p>- <span data-ttu-id="e1a3f-172">创建-删除-已读-修改-部署配置项目</span><span class="sxs-lookup"><span data-stu-id="e1a3f-172">Create- Delete- Read- Modify- Deploy Configuration Items</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e1a3f-173">Configuration Manager 配置项目权限：</span><span class="sxs-lookup"><span data-stu-id="e1a3f-173">Configuration Manager Configuration item rights:</span></span></p></td>
<td align="left"><p>- <span data-ttu-id="e1a3f-174">创建-删除-已读</span><span class="sxs-lookup"><span data-stu-id="e1a3f-174">Create- Delete- Read</span></span></p></td>
</tr>
</tbody>
</table>
<p> </p>
<p></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-remote-config"></a><span data-ttu-id="e1a3f-175">在远程计算机上使用 Windows PowerShell 配置 MBAM</span><span class="sxs-lookup"><span data-stu-id="e1a3f-175">Using Windows PowerShell to configure MBAM on a remote computer</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="e1a3f-176">何时使用此功能</span><span class="sxs-lookup"><span data-stu-id="e1a3f-176">When to use this capability</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e1a3f-177">当您想要在远程计算机上配置 MBAM 2.5 服务器功能时。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-177">When you want to configure the MBAM 2.5 Server features on a remote computer.</span></span> <span data-ttu-id="e1a3f-178">Windows PowerShell cmdlet 在一台计算机上运行，并且你正在配置不同的远程计算机上的功能。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-178">The Windows PowerShell cmdlets are running on one computer, and you are configuring the features on a different, remote computer.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="e1a3f-179">必须执行的操作</span><span class="sxs-lookup"><span data-stu-id="e1a3f-179">What you have to do</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e1a3f-180">若要使用 Windows PowerShell 在远程计算机上配置 MBAM 2.5 服务器功能，您必须：</span><span class="sxs-lookup"><span data-stu-id="e1a3f-180">To use Windows PowerShell to configure MBAM 2.5 Server features on a remote computer, you must:</span></span></p>
<ul>
<li><p><span data-ttu-id="e1a3f-181">确保已在远程计算机上安装了 MBAM 2.5 服务器软件。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-181">Ensure that the MBAM 2.5 Server software has been installed on the remote computer.</span></span></p></li>
<li><p><span data-ttu-id="e1a3f-182">使用凭据安全支持提供程序（CredSSP）协议打开 Windows PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-182">Use the Credential Security Support Provider (CredSSP) Protocol to open the Windows PowerShell session.</span></span></p></li>
<li><p><span data-ttu-id="e1a3f-183">启用 Windows 远程管理（WinRM）。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-183">Enable Windows Remote Management (WinRM).</span></span> <span data-ttu-id="e1a3f-184">如果你无法启用 WinRM 并正确配置它， <strong> </strong> 此表中所述的新 PSSession cmdlet 将显示错误并介绍如何解决该问题。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-184">If you fail to enable WinRM and to configure it correctly, the <strong>New-PSSession</strong> cmdlet that is described in this table displays an error and describes how to fix the issue.</span></span> <span data-ttu-id="e1a3f-185">有关 WinRM 的详细信息，请参阅 <a href="https://go.microsoft.com/fwlink/?LinkId=393064" data-raw-source="[Using Windows Remote Management](https://go.microsoft.com/fwlink/?LinkId=393064)"> 使用 Windows 远程管理 </a> 。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-185">For more information about WinRM, see <a href="https://go.microsoft.com/fwlink/?LinkId=393064" data-raw-source="[Using Windows Remote Management](https://go.microsoft.com/fwlink/?LinkId=393064)">Using Windows Remote Management</a>.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="e1a3f-186">为什么必须执行此操作</span><span class="sxs-lookup"><span data-stu-id="e1a3f-186">Why you have to do it</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e1a3f-187">此协议支持使用用户的管理凭据连接到 Active Directory 域服务的 Windows PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-187">This protocol enables the Windows PowerShell cmdlets to connect to Active Directory Domain Services by using the user’s administrative credentials.</span></span> <span data-ttu-id="e1a3f-188">如果在不使用此协议的情况下启动 Windows PowerShell 会话，则可能会收到验证错误。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-188">You might get a validation error if you start the Windows PowerShell session without this protocol.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="e1a3f-189">如何使用 CredSSP 协议启动 Windows PowerShell 会话</span><span class="sxs-lookup"><span data-stu-id="e1a3f-189">How to start a Windows PowerShell session with the CredSSP protocol</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e1a3f-190">在 Windows PowerShell 提示符处键入以下代码：</span><span class="sxs-lookup"><span data-stu-id="e1a3f-190">Type the following code at the Windows PowerShell prompt:</span></span></p>
<p><code>$s = New-PSSession -ComputerName xxx -Authentication Credssp -Credential xxx</code></p>
<p><span data-ttu-id="e1a3f-191">下面的代码显示了一个示例。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-191">The following code shows an example.</span></span></p>
<p><code>$session = New-PSSession -ComputerName &lt;MBAM_server_name&gt; -Authentication Credssp -Credential (Get-Credential)</code></p>
<p><code>Enter-PSSession $session</code></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-reqd-posh-accts"></a><span data-ttu-id="e1a3f-192">必需帐户和相应的 Windows PowerShell cmdlet 参数</span><span class="sxs-lookup"><span data-stu-id="e1a3f-192">Required accounts and corresponding Windows PowerShell cmdlet parameters</span></span>


<span data-ttu-id="e1a3f-193">下表介绍了配置 MBAM 2.5 服务器功能所需的帐户。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-193">The following table describes the accounts that are required to configure MBAM 2.5 Server features.</span></span> <span data-ttu-id="e1a3f-194">它还会列出你必须在配置期间为其指定帐户的相应 Windows PowerShell cmdlet 和参数。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-194">It also lists the corresponding Windows PowerShell cmdlet and parameter for which you have to specify the account during configuration.</span></span>

<span data-ttu-id="e1a3f-195">Cmdlet 参数类型（用户或组）描述 Enable-MBAMDatabase</span><span class="sxs-lookup"><span data-stu-id="e1a3f-195">Cmdlet Parameter Type (User or Group) Description Enable-MBAMDatabase</span></span>

<span data-ttu-id="e1a3f-196">AccessAccount</span><span class="sxs-lookup"><span data-stu-id="e1a3f-196">AccessAccount</span></span>

<span data-ttu-id="e1a3f-197">用户或组</span><span class="sxs-lookup"><span data-stu-id="e1a3f-197">User or Group</span></span>

<span data-ttu-id="e1a3f-198">指定对此数据库具有读/写权限的域用户或组，以使 web 应用程序能够访问此数据库中的数据和报表。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-198">Specify a domain user or group that has read/write permission to this database to give the web applications access to data and reports in this database.</span></span> <span data-ttu-id="e1a3f-199">如果值为域用户，则运行**Enable MbamWebApplication** cmdlet 时使用的**WebServiceApplicationPoolCredential**参数必须使用相同的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-199">If the value is a domain user, then the **WebServiceApplicationPoolCredential** parameter that is used when running the **Enable-MbamWebApplication** cmdlet must use the same user account.</span></span> <span data-ttu-id="e1a3f-200">如果值为 "域用户" 组，则**WebServiceApplicationPoolCredential**参数使用的域帐户必须是该组的成员。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-200">If the value is a domain Users group, then the domain account that is used by the **WebServiceApplicationPoolCredential** parameter must be a member of this group.</span></span>

<span data-ttu-id="e1a3f-201">ReportAccount</span><span class="sxs-lookup"><span data-stu-id="e1a3f-201">ReportAccount</span></span>

<span data-ttu-id="e1a3f-202">用户或组</span><span class="sxs-lookup"><span data-stu-id="e1a3f-202">User or Group</span></span>

<span data-ttu-id="e1a3f-203">指定对此数据库具有只读权限的域用户组，以便提供 MBAM 报表对合规性和审核数据的访问。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-203">Specify a domain user or Users group that has read-only permission to this database to provide the MBAM reports access to the compliance and audit data.</span></span> <span data-ttu-id="e1a3f-204">如果值为域用户，则**Enable-MbamReport** Cmdlet 的**ComplianceAndAuditDBCredential**参数必须使用相同的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-204">If the value is a domain user, then the **ComplianceAndAuditDBCredential** parameter of the **Enable-MbamReport** cmdlet must use the same user account.</span></span> <span data-ttu-id="e1a3f-205">如果值为 "域用户" 组，则**ComplianceAndAuditDBCredential**参数使用的域帐户必须是该组的成员。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-205">If the value is a domain Users group, then the domain account that is used by the **ComplianceAndAuditDBCredential** parameter must be a member of this group.</span></span>

<span data-ttu-id="e1a3f-206">Enable-MbamReport</span><span class="sxs-lookup"><span data-stu-id="e1a3f-206">Enable-MbamReport</span></span>

<span data-ttu-id="e1a3f-207">ComplianceAndAuditDBCredential</span><span class="sxs-lookup"><span data-stu-id="e1a3f-207">ComplianceAndAuditDBCredential</span></span>

<span data-ttu-id="e1a3f-208">用户</span><span class="sxs-lookup"><span data-stu-id="e1a3f-208">User</span></span>

<span data-ttu-id="e1a3f-209">指定本地 SSRS 实例用于连接到 MBAM 合规性和审核数据库的管理凭据。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-209">Specifies the administrative credential that the local SSRS instance uses to connect to the MBAM Compliance and Audit Database.</span></span> <span data-ttu-id="e1a3f-210">管理凭据中的域用户必须与用于**ReportAccount**参数的用户帐户相同，该帐户在运行**Enable-MbamDatabase** cmdlet 时使用。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-210">The domain user in the administrative credential must be the same as the user account that is used for the **ReportAccount** parameter, which is used while running the **Enable-MbamDatabase** cmdlet.</span></span> <span data-ttu-id="e1a3f-211">如果域用户组与**ReportAccount**参数一起使用，则此帐户应为该组的成员。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-211">If a domain Users group was used with the **ReportAccount** parameter, this account should be a member of that group.</span></span>

<span data-ttu-id="e1a3f-212">**重要提示** 管理凭据中指定的帐户应具有受限的用户权限，以提高安全性。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-212">**Important** The account specified in the administrative credentials should have limited user rights for improved security.</span></span> <span data-ttu-id="e1a3f-213">此外，帐户的密码应设置为 "未过期"。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-213">Also, the password of the account should be set to not expire.</span></span>

 

<span data-ttu-id="e1a3f-214">ReportsReadOnlyAccessGroup</span><span class="sxs-lookup"><span data-stu-id="e1a3f-214">ReportsReadOnlyAccessGroup</span></span>

<span data-ttu-id="e1a3f-215">组</span><span class="sxs-lookup"><span data-stu-id="e1a3f-215">Group</span></span>

<span data-ttu-id="e1a3f-216">指定对报告具有读取权限的域用户组。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-216">Specifies the domain user group that has read permissions to the reports.</span></span> <span data-ttu-id="e1a3f-217">指定的组必须与**Enable-MbamWebApplication** cmdlet 中的**ReportsReadOnlyAccessGroup**参数一起使用的组相同。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-217">The specified group must be the same group that is used for the **ReportsReadOnlyAccessGroup** parameter in the **Enable-MbamWebApplication** cmdlet.</span></span>

<span data-ttu-id="e1a3f-218">Enable-MBAMWebApplication</span><span class="sxs-lookup"><span data-stu-id="e1a3f-218">Enable-MBAMWebApplication</span></span>

<span data-ttu-id="e1a3f-219">AdvancedHelpdeskAccessGroup</span><span class="sxs-lookup"><span data-stu-id="e1a3f-219">AdvancedHelpdeskAccessGroup</span></span>

<span data-ttu-id="e1a3f-220">组</span><span class="sxs-lookup"><span data-stu-id="e1a3f-220">Group</span></span>

<span data-ttu-id="e1a3f-221">指定有权访问除 "报告" 区域之外的 "管理和监视" 网站的所有区域的 "域用户" 组。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-221">Specifies the domain Users group that has access to all areas of the Administration and Monitoring Website except the Reports area.</span></span>

<span data-ttu-id="e1a3f-222">HelpdeskAccessGroup</span><span class="sxs-lookup"><span data-stu-id="e1a3f-222">HelpdeskAccessGroup</span></span>

<span data-ttu-id="e1a3f-223">组</span><span class="sxs-lookup"><span data-stu-id="e1a3f-223">Group</span></span>

<span data-ttu-id="e1a3f-224">指定有权访问管理和监视网站的 "**管理 TPM** " 和 "**驱动器恢复**" 区域的 "域用户" 组。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-224">Specifies the domain Users group that has access to the **Manage TPM** and **Drive Recovery** areas of the Administration and Monitoring Website.</span></span>

<span data-ttu-id="e1a3f-225">ReportsReadOnlyAccessGroup</span><span class="sxs-lookup"><span data-stu-id="e1a3f-225">ReportsReadOnlyAccessGroup</span></span>

<span data-ttu-id="e1a3f-226">组</span><span class="sxs-lookup"><span data-stu-id="e1a3f-226">Group</span></span>

<span data-ttu-id="e1a3f-227">指定对管理和监视网站的 "**报告**" 区域具有读取权限的 "域用户" 组。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-227">Specifies the domain Users group that has read permission to the **Reports** area of the Administration and Monitoring Website.</span></span> <span data-ttu-id="e1a3f-228">指定的组必须与**Enable-MbamReport** cmdlet 中的**ReportsReadOnlyAccessGroup**参数一起使用的组相同。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-228">The specified group must be the same group that is used for the **ReportsReadOnlyAccessGroup** parameter in the **Enable-MbamReport** cmdlet.</span></span>

<span data-ttu-id="e1a3f-229">WebServiceApplicationPoolCredential</span><span class="sxs-lookup"><span data-stu-id="e1a3f-229">WebServiceApplicationPoolCredential</span></span>

<span data-ttu-id="e1a3f-230">用户</span><span class="sxs-lookup"><span data-stu-id="e1a3f-230">User</span></span>

<span data-ttu-id="e1a3f-231">指定要由 MBAM web 应用程序的应用程序池使用的域用户。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-231">Specifies the domain user to be used by the application pool for the MBAM web applications.</span></span> <span data-ttu-id="e1a3f-232">它必须是在**Enable-MbamDatabase** Cmdlet 的**AccessAccount**参数中指定的相同域用户帐户。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-232">It must be the same domain user account that is specified in the **AccessAccount** parameter of the **Enable-MbamDatabase** cmdlet.</span></span> <span data-ttu-id="e1a3f-233">如果在运行**Enable MbamDatabase** Cmdlet 时**AccessAccount**参数使用域用户组，则此处指定的域用户必须是该组的成员。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-233">If a domain Users group was used by the **AccessAccount** parameter when running the **Enable-MbamDatabase** cmdlet, the domain user that is specified here must be a member of that group.</span></span> <span data-ttu-id="e1a3f-234">如果不指定管理凭据，将使用由以前启用的任何 web 应用程序指定的管理凭据。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-234">If you do not specify the administrative credentials, the administrative credentials that were specified by any previously enabled web application are used.</span></span> <span data-ttu-id="e1a3f-235">所有 web 应用程序都使用相同的应用程序池标识。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-235">All of the web applications use the same application pool identity.</span></span> <span data-ttu-id="e1a3f-236">如果多次指定，则使用最新指定的值。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-236">If it is specified multiple times, the most recently specified value is used.</span></span>

<span data-ttu-id="e1a3f-237">**重要提示** 为了提高安全性，请将管理凭据中指定的帐户设置为受限的用户权限。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-237">**Important** For improved security, set the account that is specified in the administrative credentials to limited user rights.</span></span> <span data-ttu-id="e1a3f-238">此外，将帐户的密码设置为永不过期。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-238">Also, set the password of the account to never expire.</span></span> <span data-ttu-id="e1a3f-239">确保已将内置 IIS \ _IUSRS 帐户或用于**WebServiceApplicationPoolCredential**参数的帐户添加到 "身份验证本地安全设置**后模拟客户端**" 设置。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-239">Ensure that either the built-in IIS\_IUSRS account or the account that is used for the **WebServiceApplicationPoolCredential** parameter has been added to the **Impersonate a client after authentication** local security setting.</span></span>

<span data-ttu-id="e1a3f-240">若要查看本地安全设置，请打开 "**本地安全策略编辑器**"，展开 "**本地策略**" 节点，选择 "**用户权限分配**" 节点，然后双击 "**身份验证后模拟客户端**"，然后双击 "详细信息" 窗格中的 "**批处理作业**组策略设置"。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-240">To view the local security setting, open the **Local Security Policy editor**, expand the **Local Policies** node, select the **User Rights Assignment** node, and then double-click the **Impersonate a client after authentication** and **Log on as a batch job** Group Policy settings in the details pane.</span></span>

 

 




## <span data-ttu-id="e1a3f-241">相关主题</span><span class="sxs-lookup"><span data-stu-id="e1a3f-241">Related topics</span></span>


[<span data-ttu-id="e1a3f-242">配置 MBAM 2.5 服务器功能</span><span class="sxs-lookup"><span data-stu-id="e1a3f-242">Configuring the MBAM 2.5 Server Features</span></span>](configuring-the-mbam-25-server-features.md)

[<span data-ttu-id="e1a3f-243">验证 MBAM 2.5 服务器功能配置</span><span class="sxs-lookup"><span data-stu-id="e1a3f-243">Validating the MBAM 2.5 Server Feature Configuration</span></span>](validating-the-mbam-25-server-feature-configuration.md)

[<span data-ttu-id="e1a3f-244">使用 Windows PowerShell 管理 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="e1a3f-244">Using Windows PowerShell to Administer MBAM 2.5</span></span>](using-windows-powershell-to-administer-mbam-25.md)

 
## <span data-ttu-id="e1a3f-245">已获得 MBAM 的建议？</span><span class="sxs-lookup"><span data-stu-id="e1a3f-245">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="e1a3f-246">在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-246">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="e1a3f-247">对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="e1a3f-247">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>
 





