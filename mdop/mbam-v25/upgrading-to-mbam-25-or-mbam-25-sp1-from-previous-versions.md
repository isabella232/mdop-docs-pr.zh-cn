---
title: 从先前版本升级到 MBAM 2.5 或 MBAM 2.5 SP1
description: 从先前版本升级到 MBAM 2.5 或 MBAM 2.5 SP1
author: dansimp
ms.assetid: a9edb4b8-5d5e-42ab-8db6-619db2878e50
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 07a03ebbbfce45f7f69a85000e18ddf1a58e53ad
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798124"
---
# <span data-ttu-id="6abae-103">从先前版本升级到 MBAM 2.5 或 MBAM 2.5 SP1</span><span class="sxs-lookup"><span data-stu-id="6abae-103">Upgrading to MBAM 2.5 or MBAM 2.5 SP1 from Previous Versions</span></span>


<span data-ttu-id="6abae-104">本主题介绍了从早期版本的 MBAM 升级 Microsoft BitLocker 管理和监视（MBAM）服务器和 MBAM 客户端的过程。</span><span class="sxs-lookup"><span data-stu-id="6abae-104">This topic describes the process for upgrading the Microsoft BitLocker Administration and Monitoring (MBAM) Server and the MBAM Client from earlier versions of MBAM.</span></span>

<span data-ttu-id="6abae-105">**注意** 你可以从任何以前版本的 MBAM 直接升级到 MBAM 2.5 或 MBAM 2.5 SP1。</span><span class="sxs-lookup"><span data-stu-id="6abae-105">**Note** You can upgrade directly to MBAM 2.5 or MBAM 2.5 SP1 from any previous version of MBAM.</span></span>

 

## <span data-ttu-id="6abae-106">开始升级之前</span><span class="sxs-lookup"><span data-stu-id="6abae-106">Before you start the upgrade</span></span>


<span data-ttu-id="6abae-107">在开始升级之前查看以下信息。</span><span class="sxs-lookup"><span data-stu-id="6abae-107">Review the following information before you start the upgrade.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="6abae-108">开始之前需要了解的内容</span><span class="sxs-lookup"><span data-stu-id="6abae-108">What to know before you start</span></span></th>
<th align="left"><span data-ttu-id="6abae-109">详细信息</span><span class="sxs-lookup"><span data-stu-id="6abae-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6abae-110">如果要在一台服务器上安装 MBAM 网站，并在另一台服务器上安装 web 服务，则必须使用 Windows PowerShell cmdlet 对其进行配置。</span><span class="sxs-lookup"><span data-stu-id="6abae-110">If you are installing the MBAM websites on one server and the web services on another server, you have to use Windows PowerShell cmdlets to configure them.</span></span></p></td>
<td align="left"><p><span data-ttu-id="6abae-111">MBAM Server 配置向导不支持在另一台服务器上配置网站，也不支持在其他服务器上配置 web 服务。</span><span class="sxs-lookup"><span data-stu-id="6abae-111">The MBAM Server Configuration wizard does not support configuring the websites on one server and the web services on a different server.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6abae-112">如果你要从 Windows Server2008 R2 中的 MBAM 2.0 或 2.0 SP1 升级到 MBAM 2.5 或 2.5 SP1：</span><span class="sxs-lookup"><span data-stu-id="6abae-112">If you are upgrading to MBAM2.5 or 2.5 SP1 from MBAM2.0 or 2.0 SP1 in Windows Server2008 R2:</span></span></p>
<p><span data-ttu-id="6abae-113">如果在已安装 Internet 信息服务（IIS）之后安装所需的 .NET Framework 4.5 软件，则管理和监视网站和自助服务门户将无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="6abae-113">The Administration and Monitoring Website and the Self-Service Portal will not work if you install the required .NET Framework4.5 software after Internet Information Services (IIS) is already installed.</span></span></p>
<p><span data-ttu-id="6abae-114">出现此问题的原因是，如果在安装 IIS 后安装了 .NET Framework，ASP.NET 无法正确注册 IIS。</span><span class="sxs-lookup"><span data-stu-id="6abae-114">This issue occurs because ASP.NET cannot be registered correctly with IIS if the .NET Framework is installed after IIS has already been installed.</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="6abae-115">要解决此问题，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6abae-115">To resolve this issue:</span></span></strong></p>
<p><span data-ttu-id="6abae-116"><strong>从以下位置运行 aspnet_regiis-i </strong> ：</span><span class="sxs-lookup"><span data-stu-id="6abae-116">Run <strong>aspnet_regiis –i</strong> from the following location:</span></span></p>
<p><span data-ttu-id="6abae-117">C:\windows\microsoft.net\Framework\v4.0.30319</span><span class="sxs-lookup"><span data-stu-id="6abae-117">C:\windows\microsoft.net\Framework\v4.0.30319</span></span></p>
<p><span data-ttu-id="6abae-118">有关详细信息，请参阅： <a href="https://go.microsoft.com/fwlink/?LinkId=393272" data-raw-source="[ASP.NET IIS Registration Tool](https://go.microsoft.com/fwlink/?LinkId=393272)"> ASP.NET IIS 注册工具 </a> 。</span><span class="sxs-lookup"><span data-stu-id="6abae-118">For more information, see: <a href="https://go.microsoft.com/fwlink/?LinkId=393272" data-raw-source="[ASP.NET IIS Registration Tool](https://go.microsoft.com/fwlink/?LinkId=393272)">ASP.NET IIS Registration Tool</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6abae-119">如果以下所有条件均为 true，则在应用程序池帐户上注册 SPN：</span><span class="sxs-lookup"><span data-stu-id="6abae-119">Register an SPN on the application pool account if all of the following are true:</span></span></p>
<ul>
<li><p><span data-ttu-id="6abae-120">您从 MBAM 的早期版本升级。</span><span class="sxs-lookup"><span data-stu-id="6abae-120">You are upgrading from a previous version of MBAM.</span></span></p></li>
<li><p><span data-ttu-id="6abae-121">目前，你没有在负载平衡或分布式配置下运行 MBAM 网站，但你希望在升级到 MBAM 2.5 或 2.5 SP1 时执行此操作。</span><span class="sxs-lookup"><span data-stu-id="6abae-121">Currently, you are not running the MBAM websites in a load-balanced or distributed configuration, but you would like to do so when you upgrade to MBAM2.5 or 2.5 SP1.</span></span></p></li>
</ul></td>
<td align="left"><p><span data-ttu-id="6abae-122">有关说明，请参阅 <a href="planning-how-to-secure-the-mbam-websites.md#bkmk-registerspn" data-raw-source="[Planning How to Secure the MBAM Websites](planning-how-to-secure-the-mbam-websites.md#bkmk-registerspn)"> 规划如何保护 MBAM 网站的安全 </a> 。</span><span class="sxs-lookup"><span data-stu-id="6abae-122">For instructions, see <a href="planning-how-to-secure-the-mbam-websites.md#bkmk-registerspn" data-raw-source="[Planning How to Secure the MBAM Websites](planning-how-to-secure-the-mbam-websites.md#bkmk-registerspn)">Planning How to Secure the MBAM Websites</a>.</span></span></p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="6abae-123">我们建议的操作</span><span class="sxs-lookup"><span data-stu-id="6abae-123">What we recommend</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="6abae-124">注册应用程序池帐户的服务主体名称（SPN），即使你可能已注册了计算机帐户的 Spn 也是如此。</span><span class="sxs-lookup"><span data-stu-id="6abae-124">Register a service principal name (SPN) for the application pool account, even though you may already have registered SPNs for the machine account.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="6abae-125">我们建议的原因</span><span class="sxs-lookup"><span data-stu-id="6abae-125">Why we recommend it</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="6abae-126">若要在负载平衡或分布式配置中配置网站，必须在应用程序池帐户上注册 SPN。</span><span class="sxs-lookup"><span data-stu-id="6abae-126">Registering an SPN on the application pool account is required to configure the websites in a load-balanced or distributed configuration.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="6abae-127">如果已在计算机帐户上配置 Spn，会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="6abae-127">What happens if SPNs are already configured on a machine account?</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="6abae-128">MBAM 将使用你已注册的 Spn，并且无需配置其他 Spn，但你无法在负载平衡或分布式配置中配置网站。</span><span class="sxs-lookup"><span data-stu-id="6abae-128">MBAM will use the SPNs that you have already registered, and you don’t need to configure additional SPNs, but you are not able to configure the websites in a load-balanced or distributed configuration.</span></span></p></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="6abae-129">升级 MBAM Server 基础结构的步骤</span><span class="sxs-lookup"><span data-stu-id="6abae-129">Steps to upgrade the MBAM Server infrastructure</span></span>


<span data-ttu-id="6abae-130">使用以下部分中的步骤升级 MBAM 以获取独立拓扑或 System Center Configuration Manager 集成拓扑。</span><span class="sxs-lookup"><span data-stu-id="6abae-130">Use the steps in the following sections to upgrade MBAM for the Stand-alone topology or the System Center Configuration Manager Integration topology.</span></span>

**<span data-ttu-id="6abae-131">升级 MBAM 服务器基础结构以获取独立拓扑</span><span class="sxs-lookup"><span data-stu-id="6abae-131">To upgrade the MBAM Server infrastructure for Stand-alone topology</span></span>**

1.  <span data-ttu-id="6abae-132">从 "**程序和功能**" 和 "web 服务器" 中卸载以前版本的 MBAM，以确保信息不会从 MBAM 客户端写入 MBAM 基础结构。</span><span class="sxs-lookup"><span data-stu-id="6abae-132">Uninstall previous versions of MBAM from **Programs and Features** and from web servers to make sure that information is not being written from MBAM clients to the MBAM infrastructure.</span></span> <span data-ttu-id="6abae-133">有关说明，请参阅[删除 MBAM 服务器功能或软件](removing-mbam-server-features-or-software.md#bkmk-removeserverfeatures)。</span><span class="sxs-lookup"><span data-stu-id="6abae-133">For instructions, see [Removing MBAM Server Features or Software](removing-mbam-server-features-or-software.md#bkmk-removeserverfeatures).</span></span>

2.  <span data-ttu-id="6abae-134">备份数据库。</span><span class="sxs-lookup"><span data-stu-id="6abae-134">Back up your databases.</span></span>

3.  <span data-ttu-id="6abae-135">通过使用 "**程序和功能**" （包括通过 Sql Server Reporting SERVICES 托管 MBAM 报表的 sql server），从 SQL Server 中卸载以前版本的 MBAM。</span><span class="sxs-lookup"><span data-stu-id="6abae-135">Uninstall previous versions of MBAM from SQL Server by using **Programs and Features**, including SQL Servers hosting the MBAM reports via SQL Server Reporting Services.</span></span> <span data-ttu-id="6abae-136">从数据库服务器和 reporting services 中删除任何剩余的 MBAM 服务器临时文件或文件夹。</span><span class="sxs-lookup"><span data-stu-id="6abae-136">Remove any remaining MBAM server temporary files or folders from the database server and reporting services.</span></span>

    <span data-ttu-id="6abae-137">**注意** 将不会删除数据库，并且在数据库中维护所有合规性和恢复数据。</span><span class="sxs-lookup"><span data-stu-id="6abae-137">**Note** The databases will not be removed, and all compliance and recovery data is maintained in the database.</span></span>

     

4.  <span data-ttu-id="6abae-138">按照该顺序安装和配置 MBAM 2.5 或 2.5 SP1 数据库、报表和 web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="6abae-138">Install and configure the MBAM2.5 or 2.5 SP1 databases, reports, and web applications, in that order.</span></span> <span data-ttu-id="6abae-139">数据库已就地升级。</span><span class="sxs-lookup"><span data-stu-id="6abae-139">The databases are upgraded in place.</span></span>

5.  <span data-ttu-id="6abae-140">使用 MBAM 2.5 模板更新组策略对象（Gpo），以利用 MBAM 中的新功能，如强制加密。</span><span class="sxs-lookup"><span data-stu-id="6abae-140">Update the Group Policy Objects (GPOs) using the MBAM 2.5 Templates to leverage the new features in MBAM, such as enforced encryption.</span></span> <span data-ttu-id="6abae-141">如果不将 Gpo 和 MBAM 客户端更新为 MBAM 2.5，则较早版本的 MBAM 客户端将继续向你的当前 Gpo 提供缩减功能的报告。</span><span class="sxs-lookup"><span data-stu-id="6abae-141">If you do not update the GPOs and the MBAM client to MBAM 2.5, earlier versions of MBAM clients will continue to report against your current GPOs with reduced functionality.</span></span> <span data-ttu-id="6abae-142">了解[如何获取 MDOP 组策略（admx）模板](https://www.microsoft.com/download/details.aspx?id=41183)以下载最新的 admx 模板。</span><span class="sxs-lookup"><span data-stu-id="6abae-142">See [How to Get MDOP Group Policy (.admx) Templates](https://www.microsoft.com/download/details.aspx?id=41183) to download the latest ADMX templates.</span></span>

    <span data-ttu-id="6abae-143">升级 MBAM 服务器基础结构后，现有客户端计算机会继续成功地向 MBAM 2.5 或 2.5 SP1 服务器报告，并继续存储恢复数据。</span><span class="sxs-lookup"><span data-stu-id="6abae-143">After you upgrade the MBAM Server infrastructure, the existing client computers continue to successfully report to the MBAM2.5 or 2.5 SP1 Server, and recovery data continues to be stored.</span></span>

6.  <span data-ttu-id="6abae-144">安装最新的 MBAM 2.5 或 2.5 SP1 客户端。</span><span class="sxs-lookup"><span data-stu-id="6abae-144">Install the latest MBAM2.5 or 2.5 SP1 Client.</span></span> <span data-ttu-id="6abae-145">部署后不需要重新启动客户端计算机。</span><span class="sxs-lookup"><span data-stu-id="6abae-145">Client computers do not need to be rebooted after the deployment.</span></span>

**<span data-ttu-id="6abae-146">升级 System Center Configuration Manager 集成拓扑的 MBAM 基础结构</span><span class="sxs-lookup"><span data-stu-id="6abae-146">To upgrade the MBAM infrastructure for System Center Configuration Manager Integration topology</span></span>**

1.  <span data-ttu-id="6abae-147">从 "**程序和功能**" 和 "web 服务器" 中卸载以前版本的 MBAM，以确保信息不会从 MBAM 客户端写入 MBAM 基础结构。</span><span class="sxs-lookup"><span data-stu-id="6abae-147">Uninstall previous versions of MBAM from **Programs and Features** and from web servers to make sure that information is not being written from MBAM clients to the MBAM infrastructure.</span></span> <span data-ttu-id="6abae-148">有关说明，请参阅[删除 MBAM 服务器功能或软件](removing-mbam-server-features-or-software.md#bkmk-removeserverfeatures)。</span><span class="sxs-lookup"><span data-stu-id="6abae-148">For instructions, see [Removing MBAM Server Features or Software](removing-mbam-server-features-or-software.md#bkmk-removeserverfeatures).</span></span>

2.  <span data-ttu-id="6abae-149">备份数据库。</span><span class="sxs-lookup"><span data-stu-id="6abae-149">Back up your databases.</span></span>

3.  <span data-ttu-id="6abae-150">通过使用 "**程序和功能**" （包括通过 Sql Server Reporting SERVICES 托管 MBAM 报表的 sql server），从 SQL Server 中卸载以前版本的 MBAM。</span><span class="sxs-lookup"><span data-stu-id="6abae-150">Uninstall previous versions of MBAM from SQL Server by using **Programs and Features**, including SQL Servers hosting the MBAM reports via SQL Server Reporting Services.</span></span> <span data-ttu-id="6abae-151">从数据库服务器和 reporting services 中删除任何剩余的 MBAM 服务器临时文件或文件夹。</span><span class="sxs-lookup"><span data-stu-id="6abae-151">Remove any remaining MBAM server temporary files or folders from the database server and reporting services.</span></span>

4.  <span data-ttu-id="6abae-152">从 Configuration Manager 服务器卸载 MBAM。</span><span class="sxs-lookup"><span data-stu-id="6abae-152">Uninstall MBAM from the Configuration Manager server.</span></span>

    <span data-ttu-id="6abae-153">**注意** 数据库和配置管理器对象（基准、MBAM 支持的计算机集合和报告）将不会被删除，并且所有合规性和恢复数据都将保留在数据库中。</span><span class="sxs-lookup"><span data-stu-id="6abae-153">**Note** The databases and the Configuration Manager objects (baseline, MBAM supported computers collection, and Reports) will not be removed, and all compliance and recovery data is maintained in the database.</span></span>

     

5.  <span data-ttu-id="6abae-154">更新 mof 文件。</span><span class="sxs-lookup"><span data-stu-id="6abae-154">Update the .mof files.</span></span>

6.  <span data-ttu-id="6abae-155">按照该顺序安装和配置 MBAM 2.5 或 2.5 SP1 数据库、报表、web 应用程序和 Configuration Manager 集成。</span><span class="sxs-lookup"><span data-stu-id="6abae-155">Install and configure the MBAM2.5 or 2.5 SP1 databases, reports, web applications, and Configuration Manager integration, in that order.</span></span> <span data-ttu-id="6abae-156">数据库和配置管理器对象已就地升级。</span><span class="sxs-lookup"><span data-stu-id="6abae-156">The databases and Configuration Manager objects are upgraded in place.</span></span>

7.  <span data-ttu-id="6abae-157">（可选）更新组策略对象（Gpo），如果要在 MBAM 中实现新功能（如强制加密），请编辑设置。</span><span class="sxs-lookup"><span data-stu-id="6abae-157">Optionally, update the Group Policy Objects (GPOs), and edit the settings if you want to implement new features in MBAM, such as enforced encryption.</span></span> <span data-ttu-id="6abae-158">如果不更新 Gpo，MBAM 将继续报告当前 Gpo。</span><span class="sxs-lookup"><span data-stu-id="6abae-158">If you do not update the GPOs, MBAM will continue to report against your current GPOs.</span></span> <span data-ttu-id="6abae-159">了解[如何获取 MDOP 组策略（admx）模板](https://docs.microsoft.com/microsoft-desktop-optimization-pack/solutions/how-to-download-and-deploy-mdop-group-policy--admx--templates)以下载最新的 admx 模板。</span><span class="sxs-lookup"><span data-stu-id="6abae-159">See [How to Get MDOP Group Policy (.admx) Templates](https://docs.microsoft.com/microsoft-desktop-optimization-pack/solutions/how-to-download-and-deploy-mdop-group-policy--admx--templates) to download the latest ADMX templates.</span></span>

    <span data-ttu-id="6abae-160">升级 MBAM 服务器基础结构后，现有客户端计算机会继续成功地向 MBAM 2.5 或 2.5 SP1 服务器报告，并继续存储恢复数据。</span><span class="sxs-lookup"><span data-stu-id="6abae-160">After you upgrade the MBAM Server infrastructure, the existing client computers continue to successfully report to the MBAM2.5 or 2.5 SP1 Server, and recovery data continues to be stored.</span></span>

8.  <span data-ttu-id="6abae-161">安装最新的 MBAM 2.5 或 2.5 SP1 客户端。</span><span class="sxs-lookup"><span data-stu-id="6abae-161">Install the latest MBAM2.5 or 2.5 SP1 Client.</span></span> <span data-ttu-id="6abae-162">部署后不需要重新启动客户端计算机。</span><span class="sxs-lookup"><span data-stu-id="6abae-162">Client computers do not need to be rebooted after the deployment.</span></span>

## <span data-ttu-id="6abae-163">MBAM 客户端的升级支持</span><span class="sxs-lookup"><span data-stu-id="6abae-163">Upgrade support for the MBAM Client</span></span>


<span data-ttu-id="6abae-164">MBAM 支持从任何早期版本的 MBAM 客户端升级到 MBAM 2.5 客户端。</span><span class="sxs-lookup"><span data-stu-id="6abae-164">MBAM supports upgrades to the MBAM2.5 Client from any earlier version of the MBAM Client.</span></span>

**<span data-ttu-id="6abae-165">安装 MBAM 客户端的方法：</span><span class="sxs-lookup"><span data-stu-id="6abae-165">Ways to install the MBAM Client:</span></span>**

-   <span data-ttu-id="6abae-166">在安装 MBAM 2.5 服务器基础结构之后，立即或逐步升级运行 MBAM 客户端的计算机。</span><span class="sxs-lookup"><span data-stu-id="6abae-166">Upgrade the computers running MBAM Client all at once or gradually after you install the MBAM2.5 Server infrastructure.</span></span>

-   <span data-ttu-id="6abae-167">通过电子软件分发系统或通过诸如 Active Directory 域服务或 System Center Configuration Manager 之类的工具安装 MBAM 客户端。</span><span class="sxs-lookup"><span data-stu-id="6abae-167">Install the MBAM Client through an electronic software distribution system or through tools such as Active Directory Domain Services or System Center Configuration Manager.</span></span>



## <span data-ttu-id="6abae-168">相关主题</span><span class="sxs-lookup"><span data-stu-id="6abae-168">Related topics</span></span>


[<span data-ttu-id="6abae-169">部署 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="6abae-169">Deploying MBAM 2.5</span></span>](deploying-mbam-25.md)

[<span data-ttu-id="6abae-170">部署 MBAM 2.5 客户端</span><span class="sxs-lookup"><span data-stu-id="6abae-170">Deploying the MBAM 2.5 Client</span></span>](deploying-the-mbam-25-client.md)

[<span data-ttu-id="6abae-171">配置 MBAM 2.5 服务器功能</span><span class="sxs-lookup"><span data-stu-id="6abae-171">Configuring the MBAM 2.5 Server Features</span></span>](configuring-the-mbam-25-server-features.md)

 

## <span data-ttu-id="6abae-172">已获得 MBAM 的建议？</span><span class="sxs-lookup"><span data-stu-id="6abae-172">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="6abae-173">在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="6abae-173">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span>
- <span data-ttu-id="6abae-174">对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="6abae-174">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





