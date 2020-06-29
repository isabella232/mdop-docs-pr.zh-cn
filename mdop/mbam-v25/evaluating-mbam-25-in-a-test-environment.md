---
title: 在测试环境中评估 MBAM 2.5
description: 在测试环境中评估 MBAM 2.5
author: dansimp
ms.assetid: 72959b7a-e55f-4797-91b3-5be23c8c2844
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0d7ba8a62f5ddecf85fe56e04fc16a6bae374ba9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803311"
---
# <span data-ttu-id="13336-103">在测试环境中评估 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="13336-103">Evaluating MBAM 2.5 in a Test Environment</span></span>


<span data-ttu-id="13336-104">本主题介绍了如何设置测试环境以在独立或 System Center Configuration Manager 集成拓扑中评估 Microsoft BitLocker 管理和监视（MBAM）2.5。</span><span class="sxs-lookup"><span data-stu-id="13336-104">This topic describes how you can set up a test environment to evaluate Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 in the Stand-alone or System Center Configuration Manager Integration topology.</span></span>

## <span data-ttu-id="13336-105">使用独立拓扑评估 MBAM 2。5</span><span class="sxs-lookup"><span data-stu-id="13336-105">Evaluating MBAM 2.5 by using the Stand-alone topology</span></span>


<span data-ttu-id="13336-106">若要使用独立拓扑评估 MBAM，请使用下表中的信息安装 MBAM 服务器软件，然后在测试环境中配置 MBAM 服务器功能。</span><span class="sxs-lookup"><span data-stu-id="13336-106">To evaluate MBAM by using the Stand-alone topology, use the information in the following tables to install the MBAM Server software, and then configure the MBAM Server features in your test environment.</span></span>

**<span data-ttu-id="13336-107">使用独立拓扑评估 MBAM 2。5</span><span class="sxs-lookup"><span data-stu-id="13336-107">To evaluate MBAM 2.5 by using the Stand-alone topology</span></span>**

1. <span data-ttu-id="13336-108">在安装 MBAM 之前，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="13336-108">Before installing MBAM, do the following:</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="13336-109">任务</span><span class="sxs-lookup"><span data-stu-id="13336-109">Task</span></span></th>
   <th align="left"><span data-ttu-id="13336-110">获取说明的位置</span><span class="sxs-lookup"><span data-stu-id="13336-110">Where to get instructions</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="13336-111">确保已安装所有必备软件。</span><span class="sxs-lookup"><span data-stu-id="13336-111">Ensure that you have installed all of the prerequisite software.</span></span></p></td>
   <td align="left"><p><a href="mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md" data-raw-source="[MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)"><span data-ttu-id="13336-112">独立和 Configuration Manager 集成拓扑的 MBAM 2.5 服务器先决条件</span><span class="sxs-lookup"><span data-stu-id="13336-112">MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies</span></span></a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="13336-113">检查所需的硬件、RAM 和其他规范。</span><span class="sxs-lookup"><span data-stu-id="13336-113">Check the required hardware, RAM, and other specifications.</span></span></p></td>
   <td align="left"><p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)"><span data-ttu-id="13336-114">MBAM 2.5 支持的配置</span><span class="sxs-lookup"><span data-stu-id="13336-114">MBAM 2.5 Supported Configurations</span></span></a></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="13336-115">如果计划使用 cmdlet 配置 MBAM，请查看使用 Windows PowerShell 的先决条件。</span><span class="sxs-lookup"><span data-stu-id="13336-115">Review the prerequisites for using Windows PowerShell if you plan to use the cmdlets to configure MBAM.</span></span></p></td>
   <td align="left"><p><a href="configuring-mbam-25-server-features-by-using-windows-powershell.md" data-raw-source="[Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md)"><span data-ttu-id="13336-116">使用 Windows PowerShell 配置 MBAM 2.5 服务器功能</span><span class="sxs-lookup"><span data-stu-id="13336-116">Configuring MBAM 2.5 Server Features by Using Windows PowerShell</span></span></a></p></td>
   </tr>
   </tbody>
   </table>



2. <span data-ttu-id="13336-117">安装 MBAM Server 软件，然后配置所需的功能。</span><span class="sxs-lookup"><span data-stu-id="13336-117">Install the MBAM Server software, and then configure the features you want.</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="13336-118">任务</span><span class="sxs-lookup"><span data-stu-id="13336-118">Task</span></span></th>
   <th align="left"><span data-ttu-id="13336-119">获取说明的位置</span><span class="sxs-lookup"><span data-stu-id="13336-119">Where to get instructions</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="13336-120">在要配置 MBAM 服务器功能的每台服务器上安装 MBAM 服务器软件。</span><span class="sxs-lookup"><span data-stu-id="13336-120">Install the MBAM Server software on each server where you want to configure an MBAM Server feature.</span></span></p></td>
   <td align="left"><p><a href="installing-the-mbam-25-server-software.md" data-raw-source="[Installing the MBAM 2.5 Server Software](installing-the-mbam-25-server-software.md)"><span data-ttu-id="13336-121">安装 MBAM 2.5 服务器软件</span><span class="sxs-lookup"><span data-stu-id="13336-121">Installing the MBAM 2.5 Server Software</span></span></a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="13336-122">配置合规性和审核数据库以及恢复数据库。</span><span class="sxs-lookup"><span data-stu-id="13336-122">Configure the Compliance and Audit Database and the Recovery Database.</span></span></p></td>
   <td align="left"><p><a href="how-to-configure-the-mbam-25-databases.md" data-raw-source="[How to Configure the MBAM 2.5 Databases](how-to-configure-the-mbam-25-databases.md)"><span data-ttu-id="13336-123">如何配置 MBAM 2.5 数据库</span><span class="sxs-lookup"><span data-stu-id="13336-123">How to Configure the MBAM 2.5 Databases</span></span></a></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="13336-124">配置 "报表" 功能。</span><span class="sxs-lookup"><span data-stu-id="13336-124">Configure the Reports feature.</span></span></p></td>
   <td align="left"><p><a href="how-to-configure-the-mbam-25-reports.md" data-raw-source="[How to Configure the MBAM 2.5 Reports](how-to-configure-the-mbam-25-reports.md)"><span data-ttu-id="13336-125">如何配置 MBAM 2.5 报告</span><span class="sxs-lookup"><span data-stu-id="13336-125">How to Configure the MBAM 2.5 Reports</span></span></a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="13336-126">配置 web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="13336-126">Configure the web applications.</span></span></p></td>
   <td align="left"><p><a href="how-to-configure-the-mbam-25-web-applications.md" data-raw-source="[How to Configure the MBAM 2.5 Web Applications](how-to-configure-the-mbam-25-web-applications.md)"><span data-ttu-id="13336-127">如何配置 MBAM 2.5 Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="13336-127">How to Configure the MBAM 2.5 Web Applications</span></span></a></p></td>
   </tr>
   </tbody>
   </table>



3. <span data-ttu-id="13336-128">在客户端计算机上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="13336-128">On a client computer, do the following:</span></span>

   1.  <span data-ttu-id="13336-129">在客户端计算机上安装 MBAM 客户端。</span><span class="sxs-lookup"><span data-stu-id="13336-129">Install the MBAM Client on a client computer.</span></span>

   2.  <span data-ttu-id="13336-130">将 MBAM 组策略对象（Gpo）应用到计算机。</span><span class="sxs-lookup"><span data-stu-id="13336-130">Apply the MBAM Group Policy Objects (GPOs) to the computer.</span></span>

   3.  <span data-ttu-id="13336-131">设置以下注册表项，强制 MBAM 客户端以更快的速度唤醒，并且按固定时间间隔：</span><span class="sxs-lookup"><span data-stu-id="13336-131">Set the following registry keys to force the MBAM Client to wake up faster and at regular intervals:</span></span>

       ``` syntax
       [HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\FVE\MDOPBitLockerManagement
       "ClientWakeupFrequency"=dword:00000001
       "StatusReportingFrequency"=dword:00000001
       ```

       ``` syntax
       [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MBAM]
       "NoStartupDelay"=dword:00000001
       ```

       **<span data-ttu-id="13336-132">注意</span><span class="sxs-lookup"><span data-stu-id="13336-132">Note</span></span>**  
       <span data-ttu-id="13336-133">由于这些键每分钟唤醒 MBAM 客户端，因此我们建议你仅在测试环境中使用这些注册表项设置。</span><span class="sxs-lookup"><span data-stu-id="13336-133">Because these keys wake up the MBAM Client every minute, we recommend that you use these registry key settings only in a test environment.</span></span>



   4.  <span data-ttu-id="13336-134">重新启动**BitLocker 管理客户端服务**。</span><span class="sxs-lookup"><span data-stu-id="13336-134">Restart the **BitLocker Management Client Service**.</span></span>

## <span data-ttu-id="13336-135">使用 System Center 2012 Configuration Manager 集成拓扑评估 MBAM 2。5</span><span class="sxs-lookup"><span data-stu-id="13336-135">Evaluating MBAM 2.5 by using the System Center 2012 Configuration Manager Integration topology</span></span>


<span data-ttu-id="13336-136">若要使用 Configuration Manager 集成拓扑评估 MBAM，请使用下表中的信息安装 MBAM 服务器软件，然后在测试环境中配置 MBAM 服务器功能。</span><span class="sxs-lookup"><span data-stu-id="13336-136">To evaluate MBAM by using the Configuration Manager Integration topology, use the information in the following tables to install the MBAM Server software, and then configure the MBAM Server features in your test environment.</span></span> <span data-ttu-id="13336-137">在客户端计算机上安装 MBAM 客户端之后，你将完成额外的步骤，强制 MBAM 客户端更快地向 MBAM 报告计算机的状态。</span><span class="sxs-lookup"><span data-stu-id="13336-137">After installing the MBAM Client on a client computer, you will complete additional steps to force the MBAM Client to report the computer’s status to MBAM more quickly.</span></span>

**<span data-ttu-id="13336-138">使用 System Center 2012 Configuration Manager 集成拓扑评估 MBAM 2。5</span><span class="sxs-lookup"><span data-stu-id="13336-138">To evaluate MBAM 2.5 by using the System Center 2012 Configuration Manager Integration topology</span></span>**

1. <span data-ttu-id="13336-139">在安装 MBAM 之前，请查看必备软件和支持的配置。</span><span class="sxs-lookup"><span data-stu-id="13336-139">Before installing MBAM, review the prerequisite software and supported configuration.</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="13336-140">任务</span><span class="sxs-lookup"><span data-stu-id="13336-140">Task</span></span></th>
   <th align="left"><span data-ttu-id="13336-141">获取说明的位置</span><span class="sxs-lookup"><span data-stu-id="13336-141">Where to get instructions</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="13336-142">确保已安装所有必备软件。</span><span class="sxs-lookup"><span data-stu-id="13336-142">Ensure that you have installed all of the prerequisite software.</span></span></p></td>
   <td align="left"><p><a href="mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md" data-raw-source="[MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)"><span data-ttu-id="13336-143">独立和 Configuration Manager 集成拓扑的 MBAM 2.5 服务器先决条件</span><span class="sxs-lookup"><span data-stu-id="13336-143">MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies</span></span></a></p>
   <p><a href="mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md" data-raw-source="[MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology](mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md)"><span data-ttu-id="13336-144">仅适用于 Configuration Manager 集成拓扑的 MBAM 2.5 服务器先决条件</span><span class="sxs-lookup"><span data-stu-id="13336-144">MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology</span></span></a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="13336-145">检查所需的硬件、RAM 和其他规范。</span><span class="sxs-lookup"><span data-stu-id="13336-145">Check the required hardware, RAM, and other specifications.</span></span></p></td>
   <td align="left"><p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)"><span data-ttu-id="13336-146">MBAM 2.5 支持的配置</span><span class="sxs-lookup"><span data-stu-id="13336-146">MBAM 2.5 Supported Configurations</span></span></a></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="13336-147">如果计划使用 cmdlet 配置 MBAM，请查看使用 Windows PowerShell 的先决条件。</span><span class="sxs-lookup"><span data-stu-id="13336-147">Review the prerequisites for using Windows PowerShell if you plan to use the cmdlets to configure MBAM.</span></span></p></td>
   <td align="left"><p><a href="configuring-mbam-25-server-features-by-using-windows-powershell.md" data-raw-source="[Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md)"><span data-ttu-id="13336-148">使用 Windows PowerShell 配置 MBAM 2.5 服务器功能</span><span class="sxs-lookup"><span data-stu-id="13336-148">Configuring MBAM 2.5 Server Features by Using Windows PowerShell</span></span></a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="13336-149">创建或编辑该 mof 文件。</span><span class="sxs-lookup"><span data-stu-id="13336-149">Create or edit the .mof files.</span></span></p></td>
   <td align="left"><p><a href="edit-the-configurationmof-file-mbam-25.md" data-raw-source="[Edit the Configuration.mof File](edit-the-configurationmof-file-mbam-25.md)"><span data-ttu-id="13336-150">编辑 Configuration.mof 文件</span><span class="sxs-lookup"><span data-stu-id="13336-150">Edit the Configuration.mof File</span></span></a></p>
   <p><a href="create-or-edit-the-sms-defmof-file-mbam-25.md" data-raw-source="[Create or Edit the Sms_def.mof File](create-or-edit-the-sms-defmof-file-mbam-25.md)"><span data-ttu-id="13336-151">创建或编辑 Sms_def.mof 文件</span><span class="sxs-lookup"><span data-stu-id="13336-151">Create or Edit the Sms_def.mof File</span></span></a></p></td>
   </tr>
   </tbody>
   </table>



2. <span data-ttu-id="13336-152">安装 MBAM Server 软件，然后配置所需的功能。</span><span class="sxs-lookup"><span data-stu-id="13336-152">Install the MBAM Server software, and then configure the features you want.</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="13336-153">任务</span><span class="sxs-lookup"><span data-stu-id="13336-153">Task</span></span></th>
   <th align="left"><span data-ttu-id="13336-154">获取说明的位置</span><span class="sxs-lookup"><span data-stu-id="13336-154">Where to get instructions</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="13336-155">在要配置 MBAM 服务器功能的每台服务器上安装 MBAM 服务器软件。</span><span class="sxs-lookup"><span data-stu-id="13336-155">Install the MBAM Server software on each server where you want to configure an MBAM Server feature.</span></span></p>
   <div class="alert">
   <strong><span data-ttu-id="13336-156">注意</span><span class="sxs-lookup"><span data-stu-id="13336-156">Note</span></span></strong><br/><p><span data-ttu-id="13336-157">你可以使用 Windows PowerShell 或导出的数据层应用程序（DAC）程序包将数据库安装到远程 SQL Server 计算机。</span><span class="sxs-lookup"><span data-stu-id="13336-157">You can install the databases to a remote SQL Server computer by using Windows PowerShell or an exported data-tier application (DAC) package.</span></span> <span data-ttu-id="13336-158">有关 DAC 包的详细信息，请参阅 <a href="https://technet.microsoft.com/library/ee210546.aspx" data-raw-source="[Data-tier Applications](https://technet.microsoft.com/library/ee210546.aspx)"> 数据层应用程序 </a> 。</span><span class="sxs-lookup"><span data-stu-id="13336-158">For more information about DAC packages, see <a href="https://technet.microsoft.com/library/ee210546.aspx" data-raw-source="[Data-tier Applications](https://technet.microsoft.com/library/ee210546.aspx)">Data-tier Applications</a>.</span></span></p>
   </div>
   <div>

   </div></td>
   <td align="left"><p><a href="installing-the-mbam-25-server-software.md" data-raw-source="[Installing the MBAM 2.5 Server Software](installing-the-mbam-25-server-software.md)"><span data-ttu-id="13336-159">安装 MBAM 2.5 服务器软件</span><span class="sxs-lookup"><span data-stu-id="13336-159">Installing the MBAM 2.5 Server Software</span></span></a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="13336-160">配置合规性和审核数据库以及恢复数据库。</span><span class="sxs-lookup"><span data-stu-id="13336-160">Configure the Compliance and Audit Database and the Recovery Database.</span></span></p></td>
   <td align="left"><p><a href="how-to-configure-the-mbam-25-databases.md" data-raw-source="[How to Configure the MBAM 2.5 Databases](how-to-configure-the-mbam-25-databases.md)"><span data-ttu-id="13336-161">如何配置 MBAM 2.5 数据库</span><span class="sxs-lookup"><span data-stu-id="13336-161">How to Configure the MBAM 2.5 Databases</span></span></a></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="13336-162">配置 "报表" 功能。</span><span class="sxs-lookup"><span data-stu-id="13336-162">Configure the Reports feature.</span></span></p></td>
   <td align="left"><p><a href="how-to-configure-the-mbam-25-reports.md" data-raw-source="[How to Configure the MBAM 2.5 Reports](how-to-configure-the-mbam-25-reports.md)"><span data-ttu-id="13336-163">如何配置 MBAM 2.5 报告</span><span class="sxs-lookup"><span data-stu-id="13336-163">How to Configure the MBAM 2.5 Reports</span></span></a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="13336-164">配置 web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="13336-164">Configure the web applications.</span></span></p></td>
   <td align="left"><p><a href="how-to-configure-the-mbam-25-web-applications.md" data-raw-source="[How to Configure the MBAM 2.5 Web Applications](how-to-configure-the-mbam-25-web-applications.md)"><span data-ttu-id="13336-165">如何配置 MBAM 2.5 Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="13336-165">How to Configure the MBAM 2.5 Web Applications</span></span></a></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="13336-166">将 System Center Configuration Manager 配置为安装 Configuration Manager 对象。</span><span class="sxs-lookup"><span data-stu-id="13336-166">Configure the System Center Configuration Manager to install the Configuration Manager objects.</span></span></p></td>
   <td align="left"><p><a href="how-to-configure-the-mbam-25-system-center-configuration-manager-integration.md" data-raw-source="[How to Configure the MBAM 2.5 System Center Configuration Manager Integration](how-to-configure-the-mbam-25-system-center-configuration-manager-integration.md)"><span data-ttu-id="13336-167">如何配置 MBAM 2.5 System Center Configuration Manager 集成</span><span class="sxs-lookup"><span data-stu-id="13336-167">How to Configure the MBAM 2.5 System Center Configuration Manager Integration</span></span></a></p></td>
   </tr>
   </tbody>
   </table>



3. <span data-ttu-id="13336-168">在客户端计算机上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="13336-168">On a client computer, do the following:</span></span>

   1.  <span data-ttu-id="13336-169">在客户端计算机上安装 MBAM 客户端和 Configuration Manager 客户端。</span><span class="sxs-lookup"><span data-stu-id="13336-169">Install the MBAM Client and the Configuration Manager Client on a client computer.</span></span>

   2.  <span data-ttu-id="13336-170">将 MBAM 组策略对象应用到计算机。</span><span class="sxs-lookup"><span data-stu-id="13336-170">Apply the MBAM Group Policy Objects to the computer.</span></span>

   3.  <span data-ttu-id="13336-171">设置以下注册表项，强制 MBAM 客户端以更快的速度唤醒，并且按固定时间间隔：</span><span class="sxs-lookup"><span data-stu-id="13336-171">Set the following registry keys to force the MBAM Client to wake up faster and at regular intervals:</span></span>

       ``` syntax
       [HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\FVE\MDOPBitLockerManagement
       "ClientWakeupFrequency"=dword:00000001
       "StatusReportingFrequency"=dword:00000001
       ```

       ``` syntax
       [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MBAM]
       "NoStartupDelay"=dword:00000001
       ```

       **<span data-ttu-id="13336-172">注意</span><span class="sxs-lookup"><span data-stu-id="13336-172">Note</span></span>**  
       <span data-ttu-id="13336-173">由于这些键每分钟唤醒 MBAM 客户端，因此我们建议你仅在测试环境中使用这些注册表项设置。</span><span class="sxs-lookup"><span data-stu-id="13336-173">Because these keys wake up the MBAM Client every minute, we recommend that you use these registry key settings only in a test environment.</span></span>



   4.  <span data-ttu-id="13336-174">重新启动**BitLocker 管理客户端服务**。</span><span class="sxs-lookup"><span data-stu-id="13336-174">Restart the **BitLocker Management Client Service**.</span></span>

   5.  <span data-ttu-id="13336-175">在 "控制面板" 中，打开 "**配置管理器**"，然后单击 "**操作**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="13336-175">In Control Panel, open **Configuration Manager**, and then click the **Actions** tab.</span></span>

   6.  <span data-ttu-id="13336-176">选择 "**硬件清单周期**"，然后单击 "**立即运行**"。</span><span class="sxs-lookup"><span data-stu-id="13336-176">Select **Hardware Inventory Cycle**, and then click **Run Now**.</span></span> <span data-ttu-id="13336-177">此步骤通过使用您导入到的 mof 文件中的新类运行硬件清单，然后将数据发送到 Configuration Manager 服务器。</span><span class="sxs-lookup"><span data-stu-id="13336-177">This step runs the hardware inventory by using the new classes that you imported to your .mof files, and then sends the data to the Configuration Manager server.</span></span>

   7.  <span data-ttu-id="13336-178">选择 "**计算机策略检索" & 评估周期**，然后单击 "**立即运行**" 以应用与该客户端计算机相关的组策略对象。</span><span class="sxs-lookup"><span data-stu-id="13336-178">Select **Machine Policy Retrieval & Evaluation Cycle**, and then click **Run Now** to apply the Group Policy Objects that are relevant to that client computer.</span></span>



4. <span data-ttu-id="13336-179">在 Configuration Manager 控制台中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="13336-179">In the Configuration Manager console, do the following:</span></span>

   1.  <span data-ttu-id="13336-180">在导航窗格中，右键单击 " **MBAM 支持的计算机**"，单击 "**更新成员身份**"，然后单击 **"是"** 强制客户端计算机立即报告其成员身份。</span><span class="sxs-lookup"><span data-stu-id="13336-180">In the navigation pane, right-click **MBAM Supported Computers**, click **Update Membership**, and then click **Yes** to force the client computer to report its membership immediately.</span></span>

   2.  <span data-ttu-id="13336-181">在导航窗格中，单击 " **MBAM 支持的计算机**" 以验证客户端计算机是否显示在该集合中。</span><span class="sxs-lookup"><span data-stu-id="13336-181">In the navigation pane, click **MBAM Supported Computers** to verify that the client computer appears in the collection.</span></span>

5. <span data-ttu-id="13336-182">在客户端计算机上的 "控制面板" 中，再次重新打开**Configuration Manager** ，然后执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="13336-182">On the client computer, in Control Panel, reopen **Configuration Manager** again, and do the following:</span></span>

   1.  <span data-ttu-id="13336-183">单击 "**操作**" 选项卡，然后重新运行**计算机策略检索 & 评估周期**。</span><span class="sxs-lookup"><span data-stu-id="13336-183">Click the **Actions** tab, and then rerun **Machine Policy Retrieval & Evaluation Cycle**.</span></span>

   2.  <span data-ttu-id="13336-184">单击 "**配置**" 选项卡，选择 "BitLocker 基线"，然后单击 "**求值**"。</span><span class="sxs-lookup"><span data-stu-id="13336-184">Click the **Configurations** tab, select the BitLocker baseline, and then click **Evaluate**.</span></span>

6. <span data-ttu-id="13336-185">在配置管理器控制台中，验证客户端计算机是否显示在企业合规性报告上：如下所示：</span><span class="sxs-lookup"><span data-stu-id="13336-185">In the Configuration Manager console, verify that the client computer appears on the Enterprise Compliance Report: as follows:</span></span>

   1.  <span data-ttu-id="13336-186">在导航窗格中，选择 "**监视**" 工作区。</span><span class="sxs-lookup"><span data-stu-id="13336-186">In the navigation pane, select the **Monitoring** workspace.</span></span>

   2.  <span data-ttu-id="13336-187">在控制台树中，展开 "**概述** &gt; **报告** &gt; **报告** &gt; **MBAM**"。</span><span class="sxs-lookup"><span data-stu-id="13336-187">In the console tree, expand **Overview** &gt; **Reporting** &gt; **Reports** &gt; **MBAM**.</span></span>

   3.  <span data-ttu-id="13336-188">选择表示要查看报表的语言的文件夹，然后在 "结果" 窗格中选择报表。</span><span class="sxs-lookup"><span data-stu-id="13336-188">Select the folder that represents the language in which you want to view reports, and then select the report in the results pane.</span></span>

## <span data-ttu-id="13336-189">使用 System Center Configuration Manager 2007 集成拓扑评估 MBAM 2。5</span><span class="sxs-lookup"><span data-stu-id="13336-189">Evaluating MBAM 2.5 by using the System Center Configuration Manager 2007 Integration topology</span></span>


<span data-ttu-id="13336-190">若要使用 Configuration Manager 集成拓扑评估 MBAM，请按照与在生产环境中使用的相同步骤在测试环境中安装和配置 MBAM。</span><span class="sxs-lookup"><span data-stu-id="13336-190">To evaluate MBAM by using the Configuration Manager Integration topology, follow the same steps to install and configure MBAM in your test environment as you use in a production environment.</span></span> <span data-ttu-id="13336-191">在客户端计算机上安装 MBAM 客户端后，请完成本主题中的其他步骤，以使 MBAM 客户端能够更快地开始将计算机的状态报告到 MBAM。</span><span class="sxs-lookup"><span data-stu-id="13336-191">After installing the MBAM Client on a client computer, complete the additional steps in this topic to enable the MBAM Client to start reporting the computer’s status to MBAM more quickly.</span></span>

**<span data-ttu-id="13336-192">使用 Configuration Manager 2007 集成拓扑评估 MBAM</span><span class="sxs-lookup"><span data-stu-id="13336-192">To evaluate MBAM by using the Configuration Manager 2007 Integration topology</span></span>**

1. <span data-ttu-id="13336-193">在安装 MBAM 之前，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="13336-193">Before you install MBAM, do the following:</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="13336-194">任务</span><span class="sxs-lookup"><span data-stu-id="13336-194">Task</span></span></th>
   <th align="left"><span data-ttu-id="13336-195">获取说明的位置</span><span class="sxs-lookup"><span data-stu-id="13336-195">Where to get instructions</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="13336-196">确保已安装所有必备软件。</span><span class="sxs-lookup"><span data-stu-id="13336-196">Ensure that you have installed all of the prerequisite software.</span></span></p></td>
   <td align="left"><p><a href="mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md" data-raw-source="[MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)"><span data-ttu-id="13336-197">独立和 Configuration Manager 集成拓扑的 MBAM 2.5 服务器先决条件</span><span class="sxs-lookup"><span data-stu-id="13336-197">MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies</span></span></a></p>
   <p><a href="mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md" data-raw-source="[MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology](mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md)"><span data-ttu-id="13336-198">仅适用于 Configuration Manager 集成拓扑的 MBAM 2.5 服务器先决条件</span><span class="sxs-lookup"><span data-stu-id="13336-198">MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology</span></span></a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="13336-199">检查所需的硬件、RAM 和其他规范。</span><span class="sxs-lookup"><span data-stu-id="13336-199">Check the required hardware, RAM, and other specifications.</span></span></p></td>
   <td align="left"><p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)"><span data-ttu-id="13336-200">MBAM 2.5 支持的配置</span><span class="sxs-lookup"><span data-stu-id="13336-200">MBAM 2.5 Supported Configurations</span></span></a></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="13336-201">创建或编辑该 mof 文件。</span><span class="sxs-lookup"><span data-stu-id="13336-201">Create or edit the .mof files.</span></span></p></td>
   <td align="left"><p><a href="edit-the-configurationmof-file-mbam-25.md" data-raw-source="[Edit the Configuration.mof File](edit-the-configurationmof-file-mbam-25.md)"><span data-ttu-id="13336-202">编辑 Configuration.mof 文件</span><span class="sxs-lookup"><span data-stu-id="13336-202">Edit the Configuration.mof File</span></span></a></p>
   <p><a href="create-or-edit-the-sms-defmof-file-mbam-25.md" data-raw-source="[Create or Edit the Sms_def.mof File](create-or-edit-the-sms-defmof-file-mbam-25.md)"><span data-ttu-id="13336-203">创建或编辑 Sms_def.mof 文件</span><span class="sxs-lookup"><span data-stu-id="13336-203">Create or Edit the Sms_def.mof File</span></span></a></p></td>
   </tr>
   </tbody>
   </table>



2. <span data-ttu-id="13336-204">安装 MBAM Server 软件，然后配置所需的功能。</span><span class="sxs-lookup"><span data-stu-id="13336-204">Install the MBAM Server software, and then configure the features you want.</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="13336-205">任务</span><span class="sxs-lookup"><span data-stu-id="13336-205">Task</span></span></th>
   <th align="left"><span data-ttu-id="13336-206">获取说明的位置</span><span class="sxs-lookup"><span data-stu-id="13336-206">Where to get instructions</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="13336-207">在要配置 MBAM 服务器功能的每台服务器上安装 MBAM 服务器软件。</span><span class="sxs-lookup"><span data-stu-id="13336-207">Install the MBAM Server software on each server where you want to configure an MBAM Server feature.</span></span></p>
   <div class="alert">
   <strong><span data-ttu-id="13336-208">注意</span><span class="sxs-lookup"><span data-stu-id="13336-208">Note</span></span></strong><br/><p><span data-ttu-id="13336-209">你可以使用 Windows PowerShell 或导出的数据层应用程序（DAC）程序包将数据库安装到远程 SQL Server 计算机。</span><span class="sxs-lookup"><span data-stu-id="13336-209">You can install the databases to a remote SQL Server computer by using Windows PowerShell or an exported data-tier application (DAC) package.</span></span> <span data-ttu-id="13336-210">有关 DAC 包的详细信息，请参阅 <a href="https://technet.microsoft.com/library/ee210546.aspx" data-raw-source="[Data-tier Applications](https://technet.microsoft.com/library/ee210546.aspx)"> 数据层应用程序 </a> 。</span><span class="sxs-lookup"><span data-stu-id="13336-210">For more information about DAC packages, see <a href="https://technet.microsoft.com/library/ee210546.aspx" data-raw-source="[Data-tier Applications](https://technet.microsoft.com/library/ee210546.aspx)">Data-tier Applications</a>.</span></span></p>
   </div>
   <div>

   </div></td>
   <td align="left"><p><a href="installing-the-mbam-25-server-software.md" data-raw-source="[Installing the MBAM 2.5 Server Software](installing-the-mbam-25-server-software.md)"><span data-ttu-id="13336-211">安装 MBAM 2.5 服务器软件</span><span class="sxs-lookup"><span data-stu-id="13336-211">Installing the MBAM 2.5 Server Software</span></span></a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="13336-212">配置合规性和审核数据库以及恢复数据库。</span><span class="sxs-lookup"><span data-stu-id="13336-212">Configure the Compliance and Audit Database and the Recovery Database.</span></span></p></td>
   <td align="left"><p><a href="how-to-configure-the-mbam-25-databases.md" data-raw-source="[How to Configure the MBAM 2.5 Databases](how-to-configure-the-mbam-25-databases.md)"><span data-ttu-id="13336-213">如何配置 MBAM 2.5 数据库</span><span class="sxs-lookup"><span data-stu-id="13336-213">How to Configure the MBAM 2.5 Databases</span></span></a></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="13336-214">配置 "报表" 功能。</span><span class="sxs-lookup"><span data-stu-id="13336-214">Configure the Reports feature.</span></span></p></td>
   <td align="left"><p><a href="how-to-configure-the-mbam-25-reports.md" data-raw-source="[How to Configure the MBAM 2.5 Reports](how-to-configure-the-mbam-25-reports.md)"><span data-ttu-id="13336-215">如何配置 MBAM 2.5 报告</span><span class="sxs-lookup"><span data-stu-id="13336-215">How to Configure the MBAM 2.5 Reports</span></span></a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="13336-216">配置 web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="13336-216">Configure the web applications.</span></span></p></td>
   <td align="left"><p><a href="how-to-configure-the-mbam-25-web-applications.md" data-raw-source="[How to Configure the MBAM 2.5 Web Applications](how-to-configure-the-mbam-25-web-applications.md)"><span data-ttu-id="13336-217">如何配置 MBAM 2.5 Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="13336-217">How to Configure the MBAM 2.5 Web Applications</span></span></a></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="13336-218">将 System Center Configuration Manager 配置为安装 Configuration Manager 对象。</span><span class="sxs-lookup"><span data-stu-id="13336-218">Configure the System Center Configuration Manager to install the Configuration Manager objects.</span></span></p></td>
   <td align="left"><p><a href="how-to-configure-the-mbam-25-system-center-configuration-manager-integration.md" data-raw-source="[How to Configure the MBAM 2.5 System Center Configuration Manager Integration](how-to-configure-the-mbam-25-system-center-configuration-manager-integration.md)"><span data-ttu-id="13336-219">如何配置 MBAM 2.5 System Center Configuration Manager 集成</span><span class="sxs-lookup"><span data-stu-id="13336-219">How to Configure the MBAM 2.5 System Center Configuration Manager Integration</span></span></a></p></td>
   </tr>
   </tbody>
   </table>



3. <span data-ttu-id="13336-220">在客户端计算机上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="13336-220">On a client computer, do the following:</span></span>

   1.  <span data-ttu-id="13336-221">在客户端计算机上安装 MBAM 客户端。</span><span class="sxs-lookup"><span data-stu-id="13336-221">Install the MBAM Client on a client computer.</span></span>

   2.  <span data-ttu-id="13336-222">将 MBAM 组策略对象应用到计算机。</span><span class="sxs-lookup"><span data-stu-id="13336-222">Apply the MBAM Group Policy Objects to the computer.</span></span>

   3.  <span data-ttu-id="13336-223">设置以下注册表项以强制 MBAM 客户更快、更快地醒来：</span><span class="sxs-lookup"><span data-stu-id="13336-223">Set the following registry keys to force the MBAM Client to wake up more quickly and at faster intervals:</span></span>

       ``` syntax
       [HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\FVE\MDOPBitLockerManagement
       "ClientWakeupFrequency"=dword:00000001
       "StatusReportingFrequency"=dword:00000001
       ```

       ``` syntax
       [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MBAM]
       "NoStartupDelay"=dword:00000001
       ```

       **<span data-ttu-id="13336-224">注意</span><span class="sxs-lookup"><span data-stu-id="13336-224">Note</span></span>**  
       <span data-ttu-id="13336-225">由于这些键每分钟唤醒 MBAM 客户端，因此我们建议你仅在评估环境中使用这些注册表项设置。</span><span class="sxs-lookup"><span data-stu-id="13336-225">Because these keys wake up the MBAM Client every minute, we recommend that you use these registry key settings only in an evaluation environment.</span></span>



   4.  <span data-ttu-id="13336-226">重新启动**BitLocker 管理客户端服务**。</span><span class="sxs-lookup"><span data-stu-id="13336-226">Restart the **BitLocker Management Client Service**.</span></span>

   5.  <span data-ttu-id="13336-227">在 "控制面板" 中，打开 "**配置管理器**"，然后单击 "**操作**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="13336-227">In Control Panel, open **Configuration Manager**, and then click the **Actions** tab.</span></span>

   6.  <span data-ttu-id="13336-228">选择 "**计算机策略检索" & 评估周期**，然后单击 "**立即运行**" 以应用与该客户端计算机相关的组策略对象。</span><span class="sxs-lookup"><span data-stu-id="13336-228">Select **Machine Policy Retrieval & Evaluation Cycle**, and then click **Run Now** to apply the Group Policy Objects that are relevant to that client computer.</span></span>

   7.  <span data-ttu-id="13336-229">选择 "**硬件清单周期**"，然后单击 "**立即运行**"。</span><span class="sxs-lookup"><span data-stu-id="13336-229">Select **Hardware Inventory Cycle**, and then click **Run Now**.</span></span> <span data-ttu-id="13336-230">此步骤通过使用您导入到的 mof 文件中的新类运行硬件清单，然后将数据发送到 Configuration Manager 服务器。</span><span class="sxs-lookup"><span data-stu-id="13336-230">This step runs the hardware inventory by using the new classes that you imported to your .mof files and then sends the data to the Configuration Manager server.</span></span>

4. <span data-ttu-id="13336-231">在 Configuration Manager 控制台中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="13336-231">In the Configuration Manager console, do the following:</span></span>

   1.  <span data-ttu-id="13336-232">在导航窗格中，右键单击 " **MBAM 支持的计算机**"，单击 "**更新成员身份**"，然后单击 **"是"** 强制客户端计算机立即报告其成员身份。</span><span class="sxs-lookup"><span data-stu-id="13336-232">In the navigation pane, right-click **MBAM Supported Computers**, click **Update Membership**, and then click **Yes** to force the client computer to report its membership immediately.</span></span>

   2.  <span data-ttu-id="13336-233">在导航窗格中，单击 " **MBAM 支持的计算机**" 以验证客户端计算机是否显示在该集合中。</span><span class="sxs-lookup"><span data-stu-id="13336-233">In the navigation pane, click **MBAM Supported Computers** to verify that the client computer appears in the collection.</span></span>

5. <span data-ttu-id="13336-234">在客户端计算机上的 "控制面板" 中，再次重新打开**Configuration Manager** ，然后执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="13336-234">On the client computer, in Control Panel, reopen **Configuration Manager** again, and do the following:</span></span>

   1.  <span data-ttu-id="13336-235">单击 "**操作**" 选项卡，然后重新运行**计算机策略检索 & 评估周期**。</span><span class="sxs-lookup"><span data-stu-id="13336-235">Click the **Actions** tab, and then rerun **Machine Policy Retrieval & Evaluation Cycle**.</span></span>

   2.  <span data-ttu-id="13336-236">单击 "**配置**" 选项卡，选择 "BitLocker 基线"，然后单击 "**求值**"。</span><span class="sxs-lookup"><span data-stu-id="13336-236">Click the **Configurations** tab, select the BitLocker baseline, and click **Evaluate**.</span></span>

6. <span data-ttu-id="13336-237">在 Configuration Manager 控制台中，验证客户端计算机是否显示在 "企业合规性报告" 上，如下所示</span><span class="sxs-lookup"><span data-stu-id="13336-237">In the Configuration Manager console, verify that the client computer appears on the Enterprise Compliance Report, as follows</span></span>

   1.  <span data-ttu-id="13336-238">在导航窗格中，展开 "**计算机管理** &gt; **报告** &gt; **服务**" &gt; \*\* &lt; 服务器名称 &gt; MBAM\*\*。</span><span class="sxs-lookup"><span data-stu-id="13336-238">In the navigation pane, expand **Computer Management** &gt; **Reporting** &gt; **Reporting Services** &gt; **&lt;server name&gt;MBAM**.</span></span>

   2.  <span data-ttu-id="13336-239">在**MBAM**节点中，选择表示要查看报表的语言的文件夹，然后从 "结果" 窗格中选择报表。</span><span class="sxs-lookup"><span data-stu-id="13336-239">Within the **MBAM** node, select the folder that represents the language in which you want to view reports, and then select the report from the results pane.</span></span>


## <span data-ttu-id="13336-240">相关主题</span><span class="sxs-lookup"><span data-stu-id="13336-240">Related topics</span></span>


[<span data-ttu-id="13336-241">MBAM 2.5 入门</span><span class="sxs-lookup"><span data-stu-id="13336-241">Getting Started with MBAM 2.5</span></span>](getting-started-with-mbam-25.md)


## <span data-ttu-id="13336-242">已获得 MBAM 的建议？</span><span class="sxs-lookup"><span data-stu-id="13336-242">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="13336-243">在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="13336-243">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span>
- <span data-ttu-id="13336-244">对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="13336-244">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>





