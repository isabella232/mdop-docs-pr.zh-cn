---
title: 如何配置 MBAM 2.5 System Center Configuration Manager 集成
description: 如何配置 MBAM 2.5 System Center Configuration Manager 集成
author: dansimp
ms.assetid: 2b8a4c13-1dad-41e8-89ac-6889c5f7e051
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7c6fb0a0b06399baf1dc6493a40d17e76a51741f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798047"
---
# <span data-ttu-id="b74f0-103">如何配置 MBAM 2.5 System Center Configuration Manager 集成</span><span class="sxs-lookup"><span data-stu-id="b74f0-103">How to Configure the MBAM 2.5 System Center Configuration Manager Integration</span></span>


<span data-ttu-id="b74f0-104">本主题介绍如何配置 Microsoft BitLocker 管理和监视（MBAM）以使用 System Center Configuration Manager 集成拓扑，该拓扑将 MBAM 与 Configuration Manager 集成。</span><span class="sxs-lookup"><span data-stu-id="b74f0-104">This topic explains how to configure Microsoft BitLocker Administration and Monitoring (MBAM) to use the System Center Configuration Manager Integration topology, which integrates MBAM with Configuration Manager.</span></span>

<span data-ttu-id="b74f0-105">这些说明介绍了如何使用以下内容配置 Configuration Manager 集成：</span><span class="sxs-lookup"><span data-stu-id="b74f0-105">The instructions explain how to configure Configuration Manager Integration by using:</span></span>

-   <span data-ttu-id="b74f0-106">Windows PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="b74f0-106">A Windows PowerShell cmdlet</span></span>

-   <span data-ttu-id="b74f0-107">MBAM Server 配置向导</span><span class="sxs-lookup"><span data-stu-id="b74f0-107">The MBAM Server Configuration wizard</span></span>

<span data-ttu-id="b74f0-108">说明基于[MBAM 2.5 的高级别体系结构](high-level-architecture-for-mbam-25.md)中的推荐体系结构。</span><span class="sxs-lookup"><span data-stu-id="b74f0-108">The instructions are based on the recommended architecture in [High-Level Architecture for MBAM 2.5](high-level-architecture-for-mbam-25.md).</span></span>

**<span data-ttu-id="b74f0-109">开始配置之前：</span><span class="sxs-lookup"><span data-stu-id="b74f0-109">Before you start the configuration:</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="b74f0-110">步骤</span><span class="sxs-lookup"><span data-stu-id="b74f0-110">Step</span></span></th>
<th align="left"><span data-ttu-id="b74f0-111">获取说明的位置</span><span class="sxs-lookup"><span data-stu-id="b74f0-111">Where to get instructions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b74f0-112">查看建议的 MBAM 体系结构。</span><span class="sxs-lookup"><span data-stu-id="b74f0-112">Review the recommended architecture for MBAM.</span></span></p></td>
<td align="left"><p><a href="high-level-architecture-of-mbam-25-with-configuration-manager-integration-topology.md" data-raw-source="[High-Level Architecture of MBAM 2.5 with Configuration Manager Integration Topology](high-level-architecture-of-mbam-25-with-configuration-manager-integration-topology.md)"><span data-ttu-id="b74f0-113">采用 Configuration Manager 集成拓扑的 MBAM 2.5 的高级别体系结构</span><span class="sxs-lookup"><span data-stu-id="b74f0-113">High-Level Architecture of MBAM 2.5 with Configuration Manager Integration Topology</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b74f0-114">查看 MBAM 支持的配置。</span><span class="sxs-lookup"><span data-stu-id="b74f0-114">Review the supported configurations for MBAM.</span></span></p></td>
<td align="left"><p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)"><span data-ttu-id="b74f0-115">MBAM 2.5 支持的配置</span><span class="sxs-lookup"><span data-stu-id="b74f0-115">MBAM 2.5 Supported Configurations</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b74f0-116">在每台服务器上完成所需的先决条件。</span><span class="sxs-lookup"><span data-stu-id="b74f0-116">Complete the required prerequisites on each server.</span></span></p></td>
<td align="left"><ul>
<li><p><a href="mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md" data-raw-source="[MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)"><span data-ttu-id="b74f0-117">独立和 Configuration Manager 集成拓扑的 MBAM 2.5 服务器先决条件</span><span class="sxs-lookup"><span data-stu-id="b74f0-117">MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies</span></span></a></p></li>
<li><p><a href="mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md" data-raw-source="[MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology](mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md)"><span data-ttu-id="b74f0-118">仅适用于 Configuration Manager 集成拓扑的 MBAM 2.5 服务器先决条件</span><span class="sxs-lookup"><span data-stu-id="b74f0-118">MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology</span></span></a></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b74f0-119">在将在其中配置 MBAM 服务器功能的每台服务器上安装 MBAM 服务器软件。</span><span class="sxs-lookup"><span data-stu-id="b74f0-119">Install the MBAM Server software on each server where you will configure an MBAM Server feature.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="b74f0-120">注意</span><span class="sxs-lookup"><span data-stu-id="b74f0-120">Note</span></span></strong><br/><p><span data-ttu-id="b74f0-121">对于此拓扑，你必须在要安装 MBAM Server 软件的计算机上安装 Configuration Manager 控制台。</span><span class="sxs-lookup"><span data-stu-id="b74f0-121">For this topology, you must install the Configuration Manager console on the computer where you are installing the MBAM Server software.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><a href="installing-the-mbam-25-server-software.md" data-raw-source="[Installing the MBAM 2.5 Server Software](installing-the-mbam-25-server-software.md)"><span data-ttu-id="b74f0-122">安装 MBAM 2.5 服务器软件</span><span class="sxs-lookup"><span data-stu-id="b74f0-122">Installing the MBAM 2.5 Server Software</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b74f0-123">查看 Windows PowerShell 先决条件（仅适用于使用 Windows PowerShell cmdlet 配置 MBAM 的情况）。</span><span class="sxs-lookup"><span data-stu-id="b74f0-123">Review Windows PowerShell prerequisites (applicable only if you are going to use Windows PowerShell cmdlets to configure MBAM).</span></span></p></td>
<td align="left"><p><a href="configuring-mbam-25-server-features-by-using-windows-powershell.md" data-raw-source="[Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md)"><span data-ttu-id="b74f0-124">使用 Windows PowerShell 配置 MBAM 2.5 服务器功能</span><span class="sxs-lookup"><span data-stu-id="b74f0-124">Configuring MBAM 2.5 Server Features by Using Windows PowerShell</span></span></a></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="b74f0-125">使用 Windows PowerShell 配置 Configuration Manager 集成</span><span class="sxs-lookup"><span data-stu-id="b74f0-125">To configure Configuration Manager Integration by using Windows PowerShell</span></span>**

1.  <span data-ttu-id="b74f0-126">在开始配置之前，请参阅[使用 Windows Powershell 配置 MBAM 2.5 服务器功能](configuring-mbam-25-server-features-by-using-windows-powershell.md)，以查看使用 windows powershell 的先决条件。</span><span class="sxs-lookup"><span data-stu-id="b74f0-126">Before you start the configuration, see [Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md) to review the prerequisites for using Windows PowerShell.</span></span>

2.  <span data-ttu-id="b74f0-127">使用**Enable-MbamCMIntegration** Windows PowerShell Cmdlet 配置报告。</span><span class="sxs-lookup"><span data-stu-id="b74f0-127">Use the **Enable-MbamCMIntegration** Windows PowerShell cmdlet to configure the Reports.</span></span> <span data-ttu-id="b74f0-128">若要获取有关此 cmdlet 的信息，请键入**Get-help Enable-MbamCMIntegration**。</span><span class="sxs-lookup"><span data-stu-id="b74f0-128">To get information about this cmdlet, type **Get-Help Enable-MbamCMIntegration**.</span></span>

**<span data-ttu-id="b74f0-129">使用向导配置 System Center Configuration Manager 集成</span><span class="sxs-lookup"><span data-stu-id="b74f0-129">To configure the System Center Configuration Manager Integration by using the wizard</span></span>**

1.  <span data-ttu-id="b74f0-130">在要配置 System Center Configuration Manager 集成功能的服务器上，启动 "MBAM Server 配置向导"。</span><span class="sxs-lookup"><span data-stu-id="b74f0-130">On the server where you want to configure the System Center Configuration Manager Integration feature, start the MBAM Server Configuration wizard.</span></span> <span data-ttu-id="b74f0-131">可以从 "**开始**" 菜单中选择 " **MBAM 服务器配置**" 以打开该向导。</span><span class="sxs-lookup"><span data-stu-id="b74f0-131">You can select **MBAM Server Configuration** from the **Start** menu to open the wizard.</span></span>

2.  <span data-ttu-id="b74f0-132">单击 "**添加新功能**"，选择 " **System Center Configuration Manager 集成**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="b74f0-132">Click **Add New Features**, select **System Center Configuration Manager Integration**, and then click **Next**.</span></span>

    <span data-ttu-id="b74f0-133">向导检查是否满足 Configuration Manager 集成的所有先决条件。</span><span class="sxs-lookup"><span data-stu-id="b74f0-133">The wizard checks that all prerequisites for the Configuration Manager Integration have been met.</span></span>

3.  <span data-ttu-id="b74f0-134">如果先决条件检查成功，请单击 "**下一步**" 以继续。</span><span class="sxs-lookup"><span data-stu-id="b74f0-134">If the prerequisite check is successful, click **Next** to continue.</span></span> <span data-ttu-id="b74f0-135">否则，请解决任何缺少的先决条件，然后**再次单击 "检查必备项**"。</span><span class="sxs-lookup"><span data-stu-id="b74f0-135">Otherwise, resolve any missing prerequisites, and then click **Check prerequisites again**.</span></span>

4.  <span data-ttu-id="b74f0-136">使用以下说明在向导中输入字段值：</span><span class="sxs-lookup"><span data-stu-id="b74f0-136">Use the following descriptions to enter the field values in the wizard:</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="b74f0-137">字段</span><span class="sxs-lookup"><span data-stu-id="b74f0-137">Field</span></span></th>
    <th align="left"><span data-ttu-id="b74f0-138">描述</span><span class="sxs-lookup"><span data-stu-id="b74f0-138">Description</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><strong><span data-ttu-id="b74f0-139">SQL Server Reporting Services 服务器</span><span class="sxs-lookup"><span data-stu-id="b74f0-139">SQL Server Reporting Services server</span></span></strong></p></td>
    <td align="left"><p><span data-ttu-id="b74f0-140">具有报告服务点角色的服务器的完全限定的域名（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="b74f0-140">Fully qualified domain name (FQDN) of the server with the Reporting Service point role.</span></span> <span data-ttu-id="b74f0-141">这是要将 MBAM Configuration Manager 报表部署到的服务器。</span><span class="sxs-lookup"><span data-stu-id="b74f0-141">This is the server to which the MBAM Configuration Manager Reports are deployed.</span></span></p>
    <p><span data-ttu-id="b74f0-142">如果不指定服务器，配置管理器报告将部署到本地服务器。</span><span class="sxs-lookup"><span data-stu-id="b74f0-142">If you don’t specify a server, the Configuration Manager Reports will be deployed to the local server.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><strong><span data-ttu-id="b74f0-143">SQL Server Reporting Services 实例</span><span class="sxs-lookup"><span data-stu-id="b74f0-143">SQL Server Reporting Services instance</span></span></strong></p></td>
    <td align="left"><p><span data-ttu-id="b74f0-144">部署配置管理器报告的 SQL Server Reporting Services （SSRS）实例的名称。</span><span class="sxs-lookup"><span data-stu-id="b74f0-144">Name of the SQL Server Reporting Services (SSRS) instance where the Configuration Manager Reports are deployed.</span></span></p>
    <p><span data-ttu-id="b74f0-145">如果不指定实例，配置管理器报告将部署到默认的 SSRS 实例名称。</span><span class="sxs-lookup"><span data-stu-id="b74f0-145">If you don’t specify an instance, the Configuration Manager Reports will be deployed to the default SSRS instance name.</span></span> <span data-ttu-id="b74f0-146">如果服务器安装了 System Center 2012 配置管理器，则输入的值将被忽略。</span><span class="sxs-lookup"><span data-stu-id="b74f0-146">The value you enter is ignored if the server has System Center 2012 Configuration Manager installed.</span></span></p></td>
    </tr>
    </tbody>
    </table>



5.  <span data-ttu-id="b74f0-147">在 "**摘要**" 页面上，查看将添加的功能。</span><span class="sxs-lookup"><span data-stu-id="b74f0-147">On the **Summary** page, review the features that will be added.</span></span>

    **<span data-ttu-id="b74f0-148">注意</span><span class="sxs-lookup"><span data-stu-id="b74f0-148">Note</span></span>**  
    <span data-ttu-id="b74f0-149">若要创建刚刚创建的条目的 Windows PowerShell 脚本，请单击 "**导出 PowerShell 脚本**" 并保存脚本。</span><span class="sxs-lookup"><span data-stu-id="b74f0-149">To create a Windows PowerShell script of the entries you just made, click **Export PowerShell Script** and save the script.</span></span>



6.  <span data-ttu-id="b74f0-150">单击 "**添加**" 将 Configuration Manager 集成功能添加到服务器，然后单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="b74f0-150">Click **Add** to add the Configuration Manager Integration feature to the server, and then click **Close**.</span></span>



## <span data-ttu-id="b74f0-151">相关主题</span><span class="sxs-lookup"><span data-stu-id="b74f0-151">Related topics</span></span>


[<span data-ttu-id="b74f0-152">配置 MBAM 2.5 服务器功能</span><span class="sxs-lookup"><span data-stu-id="b74f0-152">Configuring the MBAM 2.5 Server Features</span></span>](configuring-the-mbam-25-server-features.md)

[<span data-ttu-id="b74f0-153">验证 MBAM 2.5 服务器功能配置</span><span class="sxs-lookup"><span data-stu-id="b74f0-153">Validating the MBAM 2.5 Server Feature Configuration</span></span>](validating-the-mbam-25-server-feature-configuration.md)


## <span data-ttu-id="b74f0-154">已获得 MBAM 的建议？</span><span class="sxs-lookup"><span data-stu-id="b74f0-154">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="b74f0-155">在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="b74f0-155">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="b74f0-156">对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="b74f0-156">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>






