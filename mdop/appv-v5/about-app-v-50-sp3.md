---
title: 关于 App-V 5.0 SP3
description: 关于 App-V 5.0 SP3
author: dansimp
ms.assetid: 67b5268b-edc1-4027-98b0-b3937dd70a6b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/02/2016
ms.openlocfilehash: bc72f3f72c2b06470287dfe4ba3ed22abcc6068b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798678"
---
# <span data-ttu-id="bbd82-103">关于 App-V 5.0 SP3</span><span class="sxs-lookup"><span data-stu-id="bbd82-103">About App-V 5.0 SP3</span></span>


<span data-ttu-id="bbd82-104">使用以下部分查看有关适用于 Microsoft Application Virtualization （App-v） 5.0 SP3 的重大更改的信息。</span><span class="sxs-lookup"><span data-stu-id="bbd82-104">Use the following sections to review information about significant changes that apply to Microsoft Application Virtualization (App-V) 5.0 SP3:</span></span>

-   [<span data-ttu-id="bbd82-105">App-v 5.0 SP3 软件先决条件和支持的配置</span><span class="sxs-lookup"><span data-stu-id="bbd82-105">App-V 5.0 SP3 software prerequisites and supported configurations</span></span>](#bkmk-sp3-prereq-configs)

-   [<span data-ttu-id="bbd82-106">迁移到 App-v 5.0 SP3</span><span class="sxs-lookup"><span data-stu-id="bbd82-106">Migrating to App-V 5.0 SP3</span></span>](#bkmk-migrate-to-50sp3)

-   [<span data-ttu-id="bbd82-107">手动创建的连接组 xml 文件需要更新到架构</span><span class="sxs-lookup"><span data-stu-id="bbd82-107">Manually created connection group xml file requires update to schema</span></span>](#bkmk-update-schema-cg)

-   [<span data-ttu-id="bbd82-108">对连接组的改进</span><span class="sxs-lookup"><span data-stu-id="bbd82-108">Improvements to connection groups</span></span>](#bkmk-cg-improvements)

-   [<span data-ttu-id="bbd82-109">管理员可以发布和取消发布特定用户的程序包</span><span class="sxs-lookup"><span data-stu-id="bbd82-109">Administrators can publish and unpublish packages for a specific user</span></span>](#bkmk-usersid-pub-pkgs-specf-user)

-   [<span data-ttu-id="bbd82-110">仅启用管理员发布和取消发布程序包</span><span class="sxs-lookup"><span data-stu-id="bbd82-110">Enable only administrators to publish and unpublish packages</span></span>](#bkmk-admins-only-pub-unpub-pkgs)

-   [<span data-ttu-id="bbd82-111">RunVirtual 注册表项支持发布到用户的程序包</span><span class="sxs-lookup"><span data-stu-id="bbd82-111">RunVirtual registry key supports packages that are published to the user</span></span>](#bkmk-runvirtual-reg-key)

-   [<span data-ttu-id="bbd82-112">新增 PowerShell cmdlet 和可更新 cmdlet 帮助</span><span class="sxs-lookup"><span data-stu-id="bbd82-112">New PowerShell cmdlets and updateable cmdlet help</span></span>](#bkmk-posh-cmdlets-help)

-   [<span data-ttu-id="bbd82-113">主虚拟应用程序目录（PVAD）已隐藏，但可以启用</span><span class="sxs-lookup"><span data-stu-id="bbd82-113">Primary virtual application directory (PVAD) is hidden but can be turned on</span></span>](#bkmk-pvad-hidden)

-   [<span data-ttu-id="bbd82-114">需要 ClientVersion，才能查看 App-v 发布元数据</span><span class="sxs-lookup"><span data-stu-id="bbd82-114">ClientVersion is required to view App-V publishing metadata</span></span>](#bkmk-pub-metadata-clientversion)

-   [<span data-ttu-id="bbd82-115">App-v 事件日志已合并</span><span class="sxs-lookup"><span data-stu-id="bbd82-115">App-V event logs have been consolidated</span></span>](#bkmk-event-logs-moved)

## <a href="" id="bkmk-sp3-prereq-configs"></a><span data-ttu-id="bbd82-116">App-v 5.0 SP3 软件先决条件和支持的配置</span><span class="sxs-lookup"><span data-stu-id="bbd82-116">App-V 5.0 SP3 software prerequisites and supported configurations</span></span>


<span data-ttu-id="bbd82-117">请参阅应用程序 V 的以下链接-V 5.0 SP3 软件先决条件和支持的配置。</span><span class="sxs-lookup"><span data-stu-id="bbd82-117">See the following links for the App-V 5.0 SP3 software prerequisites and supported configurations.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="bbd82-118">链接到先决条件和受支持的配置</span><span class="sxs-lookup"><span data-stu-id="bbd82-118">Links to prerequisites and supported configurations</span></span></th>
<th align="left"><span data-ttu-id="bbd82-119">描述</span><span class="sxs-lookup"><span data-stu-id="bbd82-119">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><a href="app-v-50-sp3-prerequisites.md" data-raw-source="[App-V 5.0 SP3 Prerequisites](app-v-50-sp3-prerequisites.md)"><span data-ttu-id="bbd82-120">App-V 5.0 SP3 先决条件</span><span class="sxs-lookup"><span data-stu-id="bbd82-120">App-V 5.0 SP3 Prerequisites</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="bbd82-121">在启动 app-v 5.0 SP3 安装之前必须安装的必备软件</span><span class="sxs-lookup"><span data-stu-id="bbd82-121">Prerequisite software that you must install before starting the App-V 5.0 SP3 installation</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="app-v-50-sp3-supported-configurations.md" data-raw-source="[App-V 5.0 SP3 Supported Configurations](app-v-50-sp3-supported-configurations.md)"><span data-ttu-id="bbd82-122">App-V 5.0 SP3 支持的配置</span><span class="sxs-lookup"><span data-stu-id="bbd82-122">App-V 5.0 SP3 Supported Configurations</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="bbd82-123">支持的操作系统和适用于 app-v Server、Sequencer 和客户端组件的硬件要求</span><span class="sxs-lookup"><span data-stu-id="bbd82-123">Supported operating systems and hardware requirements for the App-V Server, Sequencer, and Client components</span></span></p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-migrate-to-50sp3"></a><span data-ttu-id="bbd82-124">迁移到 App-v 5.0 SP3</span><span class="sxs-lookup"><span data-stu-id="bbd82-124">Migrating to App-V 5.0 SP3</span></span>


<span data-ttu-id="bbd82-125">使用以下信息从早期版本升级到 app-v 5.0 SP3。</span><span class="sxs-lookup"><span data-stu-id="bbd82-125">Use the following information to upgrade to App-V 5.0 SP3 from earlier versions.</span></span>

### <span data-ttu-id="bbd82-126">开始升级之前</span><span class="sxs-lookup"><span data-stu-id="bbd82-126">Before you start the upgrade</span></span>

<span data-ttu-id="bbd82-127">在开始升级之前查看以下信息：</span><span class="sxs-lookup"><span data-stu-id="bbd82-127">Review the following information before you start the upgrade:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="bbd82-128">升级前要查看的项目</span><span class="sxs-lookup"><span data-stu-id="bbd82-128">Items to review before upgrading</span></span></th>
<th align="left"><span data-ttu-id="bbd82-129">描述</span><span class="sxs-lookup"><span data-stu-id="bbd82-129">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bbd82-130">要升级的组件</span><span class="sxs-lookup"><span data-stu-id="bbd82-130">Components to upgrade</span></span></p></td>
<td align="left"><ol>
<li><p><span data-ttu-id="bbd82-131">App-v 服务器</span><span class="sxs-lookup"><span data-stu-id="bbd82-131">App-V Server</span></span></p></li>
<li><p><span data-ttu-id="bbd82-132">序列</span><span class="sxs-lookup"><span data-stu-id="bbd82-132">Sequencer</span></span></p></li>
<li><p><span data-ttu-id="bbd82-133">App-v 客户端或 App-v 远程桌面服务（RDS）客户端</span><span class="sxs-lookup"><span data-stu-id="bbd82-133">App-V client or App-V Remote Desktop Services (RDS) client</span></span></p></li>
<li><p><span data-ttu-id="bbd82-134">连接组</span><span class="sxs-lookup"><span data-stu-id="bbd82-134">Connection groups</span></span></p></li>
</ol>
<div class="alert">
<strong><span data-ttu-id="bbd82-135">注意</span><span class="sxs-lookup"><span data-stu-id="bbd82-135">Note</span></span></strong><br/><p><span data-ttu-id="bbd82-136">若要使用 App-v 客户端用户界面，请从 " <a href="https://www.microsoft.com/download/details.aspx?id=41186" data-raw-source="[Microsoft Application Virtualization 5.0 Client UI Application](https://www.microsoft.com/download/details.aspx?id=41186)"> Microsoft Application Virtualization 5.0 客户端 UI" 应用程序下载现有版本 </a> 。</span><span class="sxs-lookup"><span data-stu-id="bbd82-136">To use the App-V client user interface, download the existing version from <a href="https://www.microsoft.com/download/details.aspx?id=41186" data-raw-source="[Microsoft Application Virtualization 5.0 Client UI Application](https://www.microsoft.com/download/details.aspx?id=41186)">Microsoft Application Virtualization 5.0 Client UI Application</a>.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bbd82-137">从 App-v 4 升级</span><span class="sxs-lookup"><span data-stu-id="bbd82-137">Upgrading from App-V 4.x</span></span></p></td>
<td align="left"><p><span data-ttu-id="bbd82-138">必须首先升级到 app-v 5.0。</span><span class="sxs-lookup"><span data-stu-id="bbd82-138">You must first upgrade to App-V 5.0.</span></span> <span data-ttu-id="bbd82-139">您不能直接从 app-v 4. x 升级到 app-v 5.0 SP3。</span><span class="sxs-lookup"><span data-stu-id="bbd82-139">You cannot upgrade directly from App-V 4.x to App-V 5.0 SP3.</span></span></p>
<p><span data-ttu-id="bbd82-140">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="bbd82-140">For more information, see:</span></span></p>
<ul>
<li><p><a href="about-app-v-50.md" data-raw-source="[About App-V 5.0](about-app-v-50.md)"><span data-ttu-id="bbd82-141">关于 App-V 5.0</span><span class="sxs-lookup"><span data-stu-id="bbd82-141">About App-V 5.0</span></span></a> </p></li>
<li><p><a href="planning-for-migrating-from-a-previous-version-of-app-v.md" data-raw-source="[Planning for Migrating from a Previous Version of App-V](planning-for-migrating-from-a-previous-version-of-app-v.md)"><span data-ttu-id="bbd82-142">计划从以前版本的 App-V 迁移</span><span class="sxs-lookup"><span data-stu-id="bbd82-142">Planning for Migrating from a Previous Version of App-V</span></span></a></p></li>
</ul>
<p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bbd82-143">从 App-v 5.0 或更高版本升级</span><span class="sxs-lookup"><span data-stu-id="bbd82-143">Upgrading from App-V 5.0 or later</span></span></p></td>
<td align="left"><p><span data-ttu-id="bbd82-144">你可以直接从以下任何版本升级到 app-v 5.0 SP3：</span><span class="sxs-lookup"><span data-stu-id="bbd82-144">You can upgrade to App-V 5.0 SP3 directly from any of the following versions:</span></span></p>
<ul>
<li><p><span data-ttu-id="bbd82-145">App-v 5。0</span><span class="sxs-lookup"><span data-stu-id="bbd82-145">App-V 5.0</span></span></p></li>
<li><p><span data-ttu-id="bbd82-146">App-v 5.0 SP1</span><span class="sxs-lookup"><span data-stu-id="bbd82-146">App-V 5.0 SP1</span></span></p></li>
<li><p><span data-ttu-id="bbd82-147">App-v 5.0 SP2</span><span class="sxs-lookup"><span data-stu-id="bbd82-147">App-V 5.0 SP2</span></span></p></li>
</ul>
<p><span data-ttu-id="bbd82-148">若要升级到 app-v 5.0 SP3，请按照本文其余部分中的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="bbd82-148">To upgrade to App-V 5.0 SP3, follow the steps in the remaining sections of this article.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bbd82-149">升级后对程序包和连接组所做的更改</span><span class="sxs-lookup"><span data-stu-id="bbd82-149">Required changes to packages and connection groups after upgrade</span></span></p></td>
<td align="left"><p><span data-ttu-id="bbd82-150">无。</span><span class="sxs-lookup"><span data-stu-id="bbd82-150">None.</span></span> <span data-ttu-id="bbd82-151">程序包和连接组将继续按当前方式工作。</span><span class="sxs-lookup"><span data-stu-id="bbd82-151">Packages and connection groups will continue to work as they currently do.</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-steps-upgrd-infrastruc"></a><span data-ttu-id="bbd82-152">升级 app-v 基础结构的步骤</span><span class="sxs-lookup"><span data-stu-id="bbd82-152">Steps to upgrade the App-V infrastructure</span></span>

<span data-ttu-id="bbd82-153">完成以下步骤，将 app-v 基础结构的每个组件升级到 app-v 5.0 SP3。</span><span class="sxs-lookup"><span data-stu-id="bbd82-153">Complete the following steps to upgrade each component of the App-V infrastructure to App-V 5.0 SP3.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="bbd82-154">步骤</span><span class="sxs-lookup"><span data-stu-id="bbd82-154">Step</span></span></th>
<th align="left"><span data-ttu-id="bbd82-155">有关详细信息</span><span class="sxs-lookup"><span data-stu-id="bbd82-155">For more information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bbd82-156">步骤1：升级 app-v 服务器。</span><span class="sxs-lookup"><span data-stu-id="bbd82-156">Step 1: Upgrade the App-V Server.</span></span></p>
<p><span data-ttu-id="bbd82-157">如果未使用 App-v 服务器，请跳过此步骤，然后转到下一步。</span><span class="sxs-lookup"><span data-stu-id="bbd82-157">If you are not using the App-V Server, skip this step and go to the next step.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="bbd82-158">注意</span><span class="sxs-lookup"><span data-stu-id="bbd82-158">Note</span></span></strong><br/><p><span data-ttu-id="bbd82-159">App-v 5.0 SP3 客户端与 App-v 5.0 SP1 服务器兼容。</span><span class="sxs-lookup"><span data-stu-id="bbd82-159">The App-V 5.0 SP3 client is compatible with the App-V 5.0 SP1 Server.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><span data-ttu-id="bbd82-160">请按照下列步骤进行操作：</span><span class="sxs-lookup"><span data-stu-id="bbd82-160">Follow these steps:</span></span></p>
<ol>
<li><p><span data-ttu-id="bbd82-161">查看 app-v <a href="release-notes-for-app-v-50-sp3.md" data-raw-source="[Release Notes for App-V 5.0 SP3](release-notes-for-app-v-50-sp3.md)"> 5.0 SP3 的发行说明， </a> 了解可能会影响 app-v 服务器安装的问题。</span><span class="sxs-lookup"><span data-stu-id="bbd82-161">Review the <a href="release-notes-for-app-v-50-sp3.md" data-raw-source="[Release Notes for App-V 5.0 SP3](release-notes-for-app-v-50-sp3.md)">Release Notes for App-V 5.0 SP3</a> for issues that may affect the App-V Server installation.</span></span></p></li>
<li><p><span data-ttu-id="bbd82-162">根据用于升级管理数据库和/或报告数据库的方法，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="bbd82-162">Do one of the following, depending on the method you are using to upgrade the Management database and/or Reporting database:</span></span></p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="bbd82-163">数据库升级方法</span><span class="sxs-lookup"><span data-stu-id="bbd82-163">Database upgrade method</span></span></th>
<th align="left"><span data-ttu-id="bbd82-164">步骤</span><span class="sxs-lookup"><span data-stu-id="bbd82-164">Step</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bbd82-165">Windows Installer</span><span class="sxs-lookup"><span data-stu-id="bbd82-165">Windows Installer</span></span></p></td>
<td align="left"><p><span data-ttu-id="bbd82-166">跳过此步骤并转到步骤 3 "如果要升级 app-v 服务器 ..."</span><span class="sxs-lookup"><span data-stu-id="bbd82-166">Skip this step and go to step 3, “If you are upgrading the App-V Server...”</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bbd82-167">SQL 脚本</span><span class="sxs-lookup"><span data-stu-id="bbd82-167">SQL scripts</span></span></p></td>
<td align="left"><table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="bbd82-168">管理数据库</span><span class="sxs-lookup"><span data-stu-id="bbd82-168">Management database</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="bbd82-169">若要安装或升级，请参阅 <a href="https://support.microsoft.com/kb/3031340" data-raw-source="[SQL scripts to install or upgrade the App-V 5.0 SP3 Management Server database fail](https://support.microsoft.com/kb/3031340)"> 安装或升级 app-v 5.0 SP3 管理服务器数据库失败的 SQL 脚本 </a> 。</span><span class="sxs-lookup"><span data-stu-id="bbd82-169">To install or upgrade, see <a href="https://support.microsoft.com/kb/3031340" data-raw-source="[SQL scripts to install or upgrade the App-V 5.0 SP3 Management Server database fail](https://support.microsoft.com/kb/3031340)">SQL scripts to install or upgrade the App-V 5.0 SP3 Management Server database fail</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="bbd82-170">报告数据库</span><span class="sxs-lookup"><span data-stu-id="bbd82-170">Reporting database</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="bbd82-171">按照 <a href="how-to-deploy-the-app-v-databases-by-using-sql-scripts.md" data-raw-source="[How to Deploy the App-V Databases by Using SQL Scripts](how-to-deploy-the-app-v-databases-by-using-sql-scripts.md)"> 如何使用 SQL 脚本部署 App-v 数据库中的步骤操作 </a> 。</span><span class="sxs-lookup"><span data-stu-id="bbd82-171">Follow the steps in <a href="how-to-deploy-the-app-v-databases-by-using-sql-scripts.md" data-raw-source="[How to Deploy the App-V Databases by Using SQL Scripts](how-to-deploy-the-app-v-databases-by-using-sql-scripts.md)">How to Deploy the App-V Databases by Using SQL Scripts</a>.</span></span></p></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
</tbody>
</table>
<p> </p></li>
<li><p><span data-ttu-id="bbd82-172">如果你要从 App-v 5.0 SP1 修补程序包3或更高版本升级 app-v 服务器，请完成 <a href="#bkmk-check-reg-key-svr" data-raw-source="[Check registry keys after installing the App-V 5.0 SP3 Server](#bkmk-check-reg-key-svr)"> 安装 app-v 5.0 SP3 服务器后检查注册表项部分中的步骤 </a> 。</span><span class="sxs-lookup"><span data-stu-id="bbd82-172">If you are upgrading the App-V Server from App-V 5.0 SP1 Hotfix Package 3 or later, complete the steps in section <a href="#bkmk-check-reg-key-svr" data-raw-source="[Check registry keys after installing the App-V 5.0 SP3 Server](#bkmk-check-reg-key-svr)">Check registry keys after installing the App-V 5.0 SP3 Server</a>.</span></span></p></li>
<li><p><span data-ttu-id="bbd82-173">按照部署 app-v 5.0 服务器的步骤进行操作 <a href="how-to-deploy-the-app-v-50-server-50sp3.md" data-raw-source="[How to Deploy the App-V 5.0 Server](how-to-deploy-the-app-v-50-server-50sp3.md)"> </a> 。</span><span class="sxs-lookup"><span data-stu-id="bbd82-173">Follow the steps in <a href="how-to-deploy-the-app-v-50-server-50sp3.md" data-raw-source="[How to Deploy the App-V 5.0 Server](how-to-deploy-the-app-v-50-server-50sp3.md)">How to Deploy the App-V 5.0 Server</a>.</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bbd82-174">步骤2：升级 app-v Sequencer。</span><span class="sxs-lookup"><span data-stu-id="bbd82-174">Step 2: Upgrade the App-V Sequencer.</span></span></p></td>
<td align="left"><p><span data-ttu-id="bbd82-175">请参阅 <a href="how-to-install-the-sequencer-beta-gb18030.md" data-raw-source="[How to Install the Sequencer](how-to-install-the-sequencer-beta-gb18030.md)"> 如何安装 Sequencer </a> 。</span><span class="sxs-lookup"><span data-stu-id="bbd82-175">See <a href="how-to-install-the-sequencer-beta-gb18030.md" data-raw-source="[How to Install the Sequencer](how-to-install-the-sequencer-beta-gb18030.md)">How to Install the Sequencer</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bbd82-176">步骤3：升级 App-v 客户端或 App-v RDS 客户端。</span><span class="sxs-lookup"><span data-stu-id="bbd82-176">Step 3: Upgrade the App-V client or App-V RDS client.</span></span></p></td>
<td align="left"><p><span data-ttu-id="bbd82-177">请参阅 <a href="how-to-deploy-the-app-v-client-gb18030.md" data-raw-source="[How to Deploy the App-V Client](how-to-deploy-the-app-v-client-gb18030.md)"> 如何部署 App-v 客户端 </a> 。</span><span class="sxs-lookup"><span data-stu-id="bbd82-177">See <a href="how-to-deploy-the-app-v-client-gb18030.md" data-raw-source="[How to Deploy the App-V Client](how-to-deploy-the-app-v-client-gb18030.md)">How to Deploy the App-V Client</a>.</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-check-reg-key-svr"></a><span data-ttu-id="bbd82-178">在安装 app-v 5.0 SP3 服务器之前检查注册表项</span><span class="sxs-lookup"><span data-stu-id="bbd82-178">Check registry keys before installing the App-V 5.0 SP3 Server</span></span>

<span data-ttu-id="bbd82-179">这是上表中的步骤3。</span><span class="sxs-lookup"><span data-stu-id="bbd82-179">This is step 3 from the previous table.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="bbd82-180">需要执行此步骤时</span><span class="sxs-lookup"><span data-stu-id="bbd82-180">When this step is required</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="bbd82-181">从 App-v SP1 升级到使用 .msp 文件安装的任何后续修补程序包。</span><span class="sxs-lookup"><span data-stu-id="bbd82-181">You are upgrading from App-V SP1 with any subsequent Hotfix Packages that you installed by using an .msp file.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="bbd82-182">哪些组件需要执行此步骤</span><span class="sxs-lookup"><span data-stu-id="bbd82-182">Which components require that you do this step</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="bbd82-183">仅限你要升级的 app-v Server 组件。</span><span class="sxs-lookup"><span data-stu-id="bbd82-183">Only the App-V Server components that you are upgrading.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="bbd82-184">需要执行此步骤时</span><span class="sxs-lookup"><span data-stu-id="bbd82-184">When you need to do this step</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="bbd82-185">将 App-v Server 升级到 App-v 5.0 SP3 之前</span><span class="sxs-lookup"><span data-stu-id="bbd82-185">Before you upgrade the App-V Server to App-V 5.0 SP3</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="bbd82-186">需要执行的操作</span><span class="sxs-lookup"><span data-stu-id="bbd82-186">What you need to do</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="bbd82-187">使用下表中的信息，使用 <code>HKLM\Software\Microsoft\AppV\Server</code> 您在原始服务器安装中提供的值更新下的每个注册表项值。</span><span class="sxs-lookup"><span data-stu-id="bbd82-187">Using the information in the following tables, update each registry key value under <code>HKLM\Software\Microsoft\AppV\Server</code> with the value that you provided in your original server installation.</span></span> <span data-ttu-id="bbd82-188">完成此步骤将还原在安装 app-v SP1 修补程序包时可能已删除的注册表值。</span><span class="sxs-lookup"><span data-stu-id="bbd82-188">Completing this step restores registry values that may have been removed when App-V SP1 Hotfix Packages were installed.</span></span></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="bbd82-189">ManagementDatabase 键</span><span class="sxs-lookup"><span data-stu-id="bbd82-189">ManagementDatabase key</span></span>**

<span data-ttu-id="bbd82-190">如果要安装管理数据库，请在 "" 下设置这些注册表项 `HKLM\Software\Microsoft\AppV\Server\ManagementDatabase` 。</span><span class="sxs-lookup"><span data-stu-id="bbd82-190">If you are installing the Management database, set these registry keys under `HKLM\Software\Microsoft\AppV\Server\ManagementDatabase`.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="bbd82-191">键名</span><span class="sxs-lookup"><span data-stu-id="bbd82-191">Key name</span></span></th>
<th align="left"><span data-ttu-id="bbd82-192">描述</span><span class="sxs-lookup"><span data-stu-id="bbd82-192">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bbd82-193">IS_MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="bbd82-193">IS_MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</span></span></p></td>
<td align="left"><p><span data-ttu-id="bbd82-194">描述访问非本地管理数据库是否需要公共访问帐户。</span><span class="sxs-lookup"><span data-stu-id="bbd82-194">Describes whether a public access account is required to access non-local management databases.</span></span> <span data-ttu-id="bbd82-195">如果需要，值设置为 "1"。</span><span class="sxs-lookup"><span data-stu-id="bbd82-195">Value is set to “1” if it is required.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bbd82-196">MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="bbd82-196">MANAGEMENT_DB_NAME</span></span></p></td>
<td align="left"><p><span data-ttu-id="bbd82-197">管理数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="bbd82-197">Name of the Management database.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bbd82-198">MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="bbd82-198">MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT</span></span></p></td>
<td align="left"><p><span data-ttu-id="bbd82-199">用于读取（公共）访问管理数据库的帐户。</span><span class="sxs-lookup"><span data-stu-id="bbd82-199">Account used for read (public) access to the Management database.</span></span></p>
<p><span data-ttu-id="bbd82-200">在 <code>IS_MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</code> 设置为1时使用。</span><span class="sxs-lookup"><span data-stu-id="bbd82-200">Used when <code>IS_MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</code> is set to 1.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bbd82-201">MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT_SID</span><span class="sxs-lookup"><span data-stu-id="bbd82-201">MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT_SID</span></span></p></td>
<td align="left"><p><span data-ttu-id="bbd82-202">用于读取（公共）访问管理数据库的帐户的安全标识符（SID）。</span><span class="sxs-lookup"><span data-stu-id="bbd82-202">Secure identifier (SID) of the account used for read (public) access to the Management database.</span></span></p>
<p><span data-ttu-id="bbd82-203">在 <code>IS_MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</code> 设置为1时使用。</span><span class="sxs-lookup"><span data-stu-id="bbd82-203">Used when <code>IS_MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</code> is set to 1.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bbd82-204">MANAGEMENT_DB_SQL_INSTANCE</span><span class="sxs-lookup"><span data-stu-id="bbd82-204">MANAGEMENT_DB_SQL_INSTANCE</span></span></p></td>
<td align="left"><p><span data-ttu-id="bbd82-205">管理数据库的 SQL Server 实例。</span><span class="sxs-lookup"><span data-stu-id="bbd82-205">SQL Server instance for the Management database.</span></span></p>
<p><span data-ttu-id="bbd82-206">如果值为空，则使用默认数据库实例。</span><span class="sxs-lookup"><span data-stu-id="bbd82-206">If the value is blank, the default database instance is used.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bbd82-207">MANAGEMENT_DB_WRITE_ACCESS_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="bbd82-207">MANAGEMENT_DB_WRITE_ACCESS_ACCOUNT</span></span></p></td>
<td align="left"><p><span data-ttu-id="bbd82-208">用于写入（管理员）访问管理数据库的帐户。</span><span class="sxs-lookup"><span data-stu-id="bbd82-208">Account used for write (administrator) access to the Management database.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bbd82-209">MANAGEMENT_DB_WRITE_ACCESS_ACCOUNT_SID</span><span class="sxs-lookup"><span data-stu-id="bbd82-209">MANAGEMENT_DB_WRITE_ACCESS_ACCOUNT_SID</span></span></p></td>
<td align="left"><p><span data-ttu-id="bbd82-210">用于写入（管理员）访问管理数据库的帐户的安全标识符（SID）。</span><span class="sxs-lookup"><span data-stu-id="bbd82-210">Secure identifier (SID) of the account used for write (administrator) access to the Management database.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bbd82-211">MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="bbd82-211">MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT</span></span></p></td>
<td align="left"><p><span data-ttu-id="bbd82-212">管理服务器远程计算机帐户（域 \ 帐户）。</span><span class="sxs-lookup"><span data-stu-id="bbd82-212">Management server remote computer account (domain\account).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bbd82-213">MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="bbd82-213">MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span></span></p></td>
<td align="left"><p><span data-ttu-id="bbd82-214">管理服务器（域 \ 帐户）的安装管理员登录。</span><span class="sxs-lookup"><span data-stu-id="bbd82-214">Installation administrator login for the Management server (domain\account).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bbd82-215">MANAGEMENT_SERVER_MACHINE_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="bbd82-215">MANAGEMENT_SERVER_MACHINE_USE_LOCAL</span></span></p></td>
<td align="left"><p><span data-ttu-id="bbd82-216">有效值为：</span><span class="sxs-lookup"><span data-stu-id="bbd82-216">Valid values are:</span></span></p>
<ul>
<li><p><strong><span data-ttu-id="bbd82-217">1 </strong> -管理服务位于本地计算机上，即 MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT 为空。</span><span class="sxs-lookup"><span data-stu-id="bbd82-217">1</strong> – the Management service is on the local computer, that is, MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT is blank.</span></span></p></li>
<li><p><strong><span data-ttu-id="bbd82-218">0 </strong> - 管理服务位于本地计算机的不同计算机上。</span><span class="sxs-lookup"><span data-stu-id="bbd82-218">0</strong> - the Management service is on a different computer from the local computer.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="bbd82-219">ManagementService 键</span><span class="sxs-lookup"><span data-stu-id="bbd82-219">ManagementService key</span></span>**

<span data-ttu-id="bbd82-220">如果要安装管理服务器，请在 "" 下设置这些注册表项 `HKLM\Software\Microsoft\AppV\Server\ManagementService` 。</span><span class="sxs-lookup"><span data-stu-id="bbd82-220">If you are installing the Management server, set these registry keys under `HKLM\Software\Microsoft\AppV\Server\ManagementService`.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="bbd82-221">键名</span><span class="sxs-lookup"><span data-stu-id="bbd82-221">Key name</span></span></th>
<th align="left"><span data-ttu-id="bbd82-222">描述</span><span class="sxs-lookup"><span data-stu-id="bbd82-222">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bbd82-223">MANAGEMENT_ADMINACCOUNT</span><span class="sxs-lookup"><span data-stu-id="bbd82-223">MANAGEMENT_ADMINACCOUNT</span></span></p></td>
<td align="left"><p><span data-ttu-id="bbd82-224">已授权管理 App-v （域 \ 帐户）的 Active Directory 域服务（AD DS）组或帐户。</span><span class="sxs-lookup"><span data-stu-id="bbd82-224">Active Directory Domain Services (AD DS) group or account that is authorized to manage App-V (domain\account).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bbd82-225">MANAGEMENT_DB_SQL_INSTANCE</span><span class="sxs-lookup"><span data-stu-id="bbd82-225">MANAGEMENT_DB_SQL_INSTANCE</span></span></p></td>
<td align="left"><p><span data-ttu-id="bbd82-226">包含管理数据库的 SQL server 实例。</span><span class="sxs-lookup"><span data-stu-id="bbd82-226">SQL server instance that contains the Management database.</span></span></p>
<p><span data-ttu-id="bbd82-227">如果值为空，则使用默认数据库实例。</span><span class="sxs-lookup"><span data-stu-id="bbd82-227">If the value is blank, the default database instance is used.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bbd82-228">MANAGEMENT_DB_SQL_SERVER_NAME</span><span class="sxs-lookup"><span data-stu-id="bbd82-228">MANAGEMENT_DB_SQL_SERVER_NAME</span></span></p></td>
<td align="left"><p><span data-ttu-id="bbd82-229">带有管理数据库的远程 SQL server 的名称。</span><span class="sxs-lookup"><span data-stu-id="bbd82-229">Name of the remote SQL server with the Management database.</span></span></p>
<p><span data-ttu-id="bbd82-230">如果值为空，则使用本地计算机。</span><span class="sxs-lookup"><span data-stu-id="bbd82-230">If the value is blank, the local computer is used.</span></span></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="bbd82-231">ReportingDatabase 键</span><span class="sxs-lookup"><span data-stu-id="bbd82-231">ReportingDatabase key</span></span>**

<span data-ttu-id="bbd82-232">如果要安装报告数据库，请在 "" 下设置这些注册表项 `HKLM\Software\Microsoft\AppV\Server\ReportingDatabase` 。</span><span class="sxs-lookup"><span data-stu-id="bbd82-232">If you are installing the Reporting database, set these registry keys under `HKLM\Software\Microsoft\AppV\Server\ReportingDatabase`.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="bbd82-233">键名</span><span class="sxs-lookup"><span data-stu-id="bbd82-233">Key name</span></span></th>
<th align="left"><span data-ttu-id="bbd82-234">描述</span><span class="sxs-lookup"><span data-stu-id="bbd82-234">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bbd82-235">IS_REPORTING_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="bbd82-235">IS_REPORTING_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</span></span></p></td>
<td align="left"><p><span data-ttu-id="bbd82-236">描述访问非本地报告数据库是否需要公共访问帐户。</span><span class="sxs-lookup"><span data-stu-id="bbd82-236">Describes whether a public access account is required to access non-local reporting databases.</span></span> <span data-ttu-id="bbd82-237">如果需要，值设置为 "1"。</span><span class="sxs-lookup"><span data-stu-id="bbd82-237">Value is set to “1” if it is required.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bbd82-238">REPORTING_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="bbd82-238">REPORTING_DB_NAME</span></span></p></td>
<td align="left"><p><span data-ttu-id="bbd82-239">报告数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="bbd82-239">Name of the Reporting database.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bbd82-240">REPORTING_DB_PUBLIC_ACCESS_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="bbd82-240">REPORTING_DB_PUBLIC_ACCESS_ACCOUNT</span></span></p></td>
<td align="left"><p><span data-ttu-id="bbd82-241">用于对报告数据库进行读取（公共）访问的帐户。</span><span class="sxs-lookup"><span data-stu-id="bbd82-241">Account used for read (public) access to the Reporting database.</span></span></p>
<p><span data-ttu-id="bbd82-242">在 <code>IS_REPORTING_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</code> 设置为1时使用。</span><span class="sxs-lookup"><span data-stu-id="bbd82-242">Used when <code>IS_REPORTING_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</code> is set to 1.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bbd82-243">REPORTING_DB_PUBLIC_ACCESS_ACCOUNT_SID</span><span class="sxs-lookup"><span data-stu-id="bbd82-243">REPORTING_DB_PUBLIC_ACCESS_ACCOUNT_SID</span></span></p></td>
<td align="left"><p><span data-ttu-id="bbd82-244">用于对报告数据库进行读取（公共）访问的帐户的安全标识符（SID）。</span><span class="sxs-lookup"><span data-stu-id="bbd82-244">Secure identifier (SID) of the account used for read (public) access to the Reporting database.</span></span></p>
<p><span data-ttu-id="bbd82-245">在 <code>IS_REPORTING_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</code> 设置为1时使用。</span><span class="sxs-lookup"><span data-stu-id="bbd82-245">Used when <code>IS_REPORTING_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</code> is set to 1.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bbd82-246">REPORTING_DB_SQL_INSTANCE</span><span class="sxs-lookup"><span data-stu-id="bbd82-246">REPORTING_DB_SQL_INSTANCE</span></span></p></td>
<td align="left"><p><span data-ttu-id="bbd82-247">报告数据库的 SQL Server 实例。</span><span class="sxs-lookup"><span data-stu-id="bbd82-247">SQL Server instance for the Reporting database.</span></span></p>
<p><span data-ttu-id="bbd82-248">如果值为空，则使用默认数据库实例。</span><span class="sxs-lookup"><span data-stu-id="bbd82-248">If the value is blank, the default database instance is used.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bbd82-249">REPORTING_DB_WRITE_ACCESS_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="bbd82-249">REPORTING_DB_WRITE_ACCESS_ACCOUNT</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bbd82-250">REPORTING_DB_WRITE_ACCESS_ACCOUNT_SID</span><span class="sxs-lookup"><span data-stu-id="bbd82-250">REPORTING_DB_WRITE_ACCESS_ACCOUNT_SID</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bbd82-251">REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="bbd82-251">REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT</span></span></p></td>
<td align="left"><p><span data-ttu-id="bbd82-252">报表服务器远程计算机帐户（域 \ 帐户）。</span><span class="sxs-lookup"><span data-stu-id="bbd82-252">Reporting server remote computer account (domain\account).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bbd82-253">REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="bbd82-253">REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span></span></p></td>
<td align="left"><p><span data-ttu-id="bbd82-254">报告服务器（域 \ 帐户）的安装管理员登录。</span><span class="sxs-lookup"><span data-stu-id="bbd82-254">Installation administrator login for the Reporting server (domain\account).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bbd82-255">REPORTING_SERVER_MACHINE_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="bbd82-255">REPORTING_SERVER_MACHINE_USE_LOCAL</span></span></p></td>
<td align="left"><p><span data-ttu-id="bbd82-256">有效值为：</span><span class="sxs-lookup"><span data-stu-id="bbd82-256">Valid values are:</span></span></p>
<ul>
<li><p><strong><span data-ttu-id="bbd82-257">1 </strong> -报告服务在本地计算机上，即 REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT 为空。</span><span class="sxs-lookup"><span data-stu-id="bbd82-257">1</strong> – the Reporting service is on the local computer, that is, REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT is blank.</span></span></p></li>
<li><p><strong><span data-ttu-id="bbd82-258">0 </strong> - 报告服务位于本地计算机的不同计算机上。</span><span class="sxs-lookup"><span data-stu-id="bbd82-258">0</strong> - the Reporting service is on a different computer from the local computer.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="bbd82-259">ReportingService 键</span><span class="sxs-lookup"><span data-stu-id="bbd82-259">ReportingService key</span></span>**

<span data-ttu-id="bbd82-260">如果要安装报表服务器，请在 "" 下设置这些注册表项 `HKLM\Software\Microsoft\AppV\Server\ReportingService` 。</span><span class="sxs-lookup"><span data-stu-id="bbd82-260">If you are installing the Reporting server, set these registry keys under `HKLM\Software\Microsoft\AppV\Server\ReportingService`.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="bbd82-261">键名</span><span class="sxs-lookup"><span data-stu-id="bbd82-261">Key name</span></span></th>
<th align="left"><span data-ttu-id="bbd82-262">描述</span><span class="sxs-lookup"><span data-stu-id="bbd82-262">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bbd82-263">REPORTING_DB_SQL_INSTANCE</span><span class="sxs-lookup"><span data-stu-id="bbd82-263">REPORTING_DB_SQL_INSTANCE</span></span></p></td>
<td align="left"><p><span data-ttu-id="bbd82-264">报告数据库的 SQL Server 实例。</span><span class="sxs-lookup"><span data-stu-id="bbd82-264">SQL Server instance for the Reporting database.</span></span></p>
<p><span data-ttu-id="bbd82-265">如果值为空，则使用默认数据库实例。</span><span class="sxs-lookup"><span data-stu-id="bbd82-265">If the value is blank, the default database instance is used.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bbd82-266">REPORTING_DB_SQL_SERVER_NAME</span><span class="sxs-lookup"><span data-stu-id="bbd82-266">REPORTING_DB_SQL_SERVER_NAME</span></span></p></td>
<td align="left"><p><span data-ttu-id="bbd82-267">带有报告数据库的远程 SQL 服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="bbd82-267">Name of the remote SQL server with the Reporting database.</span></span></p>
<p><span data-ttu-id="bbd82-268">如果值为空，则使用本地计算机。</span><span class="sxs-lookup"><span data-stu-id="bbd82-268">If the value is blank, the local computer is used.</span></span></p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-update-schema-cg"></a><span data-ttu-id="bbd82-269">手动创建的连接组 xml 文件需要更新到架构</span><span class="sxs-lookup"><span data-stu-id="bbd82-269">Manually created connection group xml file requires update to schema</span></span>


<span data-ttu-id="bbd82-270">如果你要手动创建连接组 XML 文件，并且希望使用新的 "可选程序包" 和 "使用任何版本" 功能（将在 "[连接组](#bkmk-cg-improvements)" 的改进中介绍），必须在 XML 文件中指定以下架构：</span><span class="sxs-lookup"><span data-stu-id="bbd82-270">If you are manually creating the connection group XML file, and want to use the new “optional packages” and “use any version” features that are described in [Improvements to connection groups](#bkmk-cg-improvements), you must specify the following schema in the XML file:</span></span>

`xmlns="http://schemas.microsoft.com/appv/2014/virtualapplicationconnectiongroup"`

<span data-ttu-id="bbd82-271">有关示例和详细信息，请参阅[关于连接组文件](about-the-connection-group-file.md)。</span><span class="sxs-lookup"><span data-stu-id="bbd82-271">For examples and more information, see [About the Connection Group File](about-the-connection-group-file.md).</span></span>

## <a href="" id="bkmk-cg-improvements"></a><span data-ttu-id="bbd82-272">对连接组的改进</span><span class="sxs-lookup"><span data-stu-id="bbd82-272">Improvements to connection groups</span></span>


<span data-ttu-id="bbd82-273">通过使用 App-v 5.0 SP3 中添加的可选程序包和其他改进，可以更轻松地管理连接组。</span><span class="sxs-lookup"><span data-stu-id="bbd82-273">You can manage connection groups more easily by using optional packages and other improvements that have been added in App-V 5.0 SP3.</span></span> <span data-ttu-id="bbd82-274">下表总结了可使用新的连接组功能执行的任务，并提供了指向有关每个任务的更详细信息的链接。</span><span class="sxs-lookup"><span data-stu-id="bbd82-274">The following table summarizes the tasks that you can perform by using the new connection group features, and links to more detailed information about each task.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="bbd82-275">任务/功能</span><span class="sxs-lookup"><span data-stu-id="bbd82-275">Task/feature</span></span></th>
<th align="left"><span data-ttu-id="bbd82-276">描述</span><span class="sxs-lookup"><span data-stu-id="bbd82-276">Description</span></span></th>
<th align="left"><span data-ttu-id="bbd82-277">指向详细信息的链接</span><span class="sxs-lookup"><span data-stu-id="bbd82-277">Links to more information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bbd82-278">启用连接组以包含可选程序包</span><span class="sxs-lookup"><span data-stu-id="bbd82-278">Enable a connection group to include optional packages</span></span></p></td>
<td align="left"><p><span data-ttu-id="bbd82-279">在连接组中包含可选程序包后，你可以根据用户有权使用的应用程序，动态确定哪些应用程序将包含在连接组的虚拟环境中。</span><span class="sxs-lookup"><span data-stu-id="bbd82-279">Including optional packages in a connection group enables you to dynamically determine which applications will be included in the connection group’s virtual environment, based on the applications that users are entitled to.</span></span></p>
<p><span data-ttu-id="bbd82-280">你不需要管理任意多个连接组，因为你可以在同一连接组中混合使用可选和非可选的程序包。</span><span class="sxs-lookup"><span data-stu-id="bbd82-280">You don’t need to manage as many connection groups because you can mix optional and non-optional packages in the same connection group.</span></span> <span data-ttu-id="bbd82-281">混合程序包允许不同组的用户使用相同的连接组，即使用户可能只有一个程序包。</span><span class="sxs-lookup"><span data-stu-id="bbd82-281">Mixing packages allows different groups of users to use the same connection group, even though users might have only one package in common.</span></span></p>
<p><strong><span data-ttu-id="bbd82-282">示例 </strong> ：你可以为所有用户启用 Microsoft Office 的程序包，但将包含不同 Office 插件的不同可选程序包启用为不同的用户子集。</span><span class="sxs-lookup"><span data-stu-id="bbd82-282">Example</strong>: You can enable a package with Microsoft Office for all users, but enable different optional packages, which contain different Office plug-ins, to different subsets of users.</span></span></p></td>
<td align="left"><p><a href="how-to-use-optional-packages-in-connection-groups.md#bkmk-apps-plugs-optional" data-raw-source="[How to Use Optional Packages in Connection Groups](how-to-use-optional-packages-in-connection-groups.md#bkmk-apps-plugs-optional)"><span data-ttu-id="bbd82-283">如何使用连接组中的可选程序包</span><span class="sxs-lookup"><span data-stu-id="bbd82-283">How to Use Optional Packages in Connection Groups</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bbd82-284">取消发布或删除可选程序包，而不更改连接组</span><span class="sxs-lookup"><span data-stu-id="bbd82-284">Unpublish or delete an optional package without changing the connection group</span></span></p></td>
<td align="left"><p><span data-ttu-id="bbd82-285">取消发布或删除或取消发布和重新发布在连接组中的可选程序包，而无需在 App-v 客户端上禁用或重新启用连接组。</span><span class="sxs-lookup"><span data-stu-id="bbd82-285">Unpublish or delete, or unpublish and republish an optional package, which is in a connection group, without having to disable or re-enable the connection group on the App-V client.</span></span></p></td>
<td align="left"><p><a href="how-to-use-optional-packages-in-connection-groups.md#bkmk-apps-plugs-optional" data-raw-source="[How to Use Optional Packages in Connection Groups](how-to-use-optional-packages-in-connection-groups.md#bkmk-apps-plugs-optional)"><span data-ttu-id="bbd82-286">如何使用连接组中的可选程序包</span><span class="sxs-lookup"><span data-stu-id="bbd82-286">How to Use Optional Packages in Connection Groups</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bbd82-287">发布包含用户发布和全局发布的程序包的连接组</span><span class="sxs-lookup"><span data-stu-id="bbd82-287">Publish connection groups that contain user-published and globally published packages</span></span></p></td>
<td align="left"><p><span data-ttu-id="bbd82-288">创建一个用户发布的连接组，其中包含用户发布和全局发布的程序包。</span><span class="sxs-lookup"><span data-stu-id="bbd82-288">Create a user-published connection group that contains user-published and globally published packages.</span></span></p></td>
<td align="left"><p><a href="how-to-create-a-connection-group-with-user-published-and-globally-published-packages.md" data-raw-source="[How to Create a Connection Group with User-Published and Globally Published Packages](how-to-create-a-connection-group-with-user-published-and-globally-published-packages.md)"><span data-ttu-id="bbd82-289">如何创建与用户发布和全局发布的程序包的连接组</span><span class="sxs-lookup"><span data-stu-id="bbd82-289">How to Create a Connection Group with User-Published and Globally Published Packages</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bbd82-290">使连接组忽略程序包版本</span><span class="sxs-lookup"><span data-stu-id="bbd82-290">Make a connection group ignore the package version</span></span></p></td>
<td align="left"><p><span data-ttu-id="bbd82-291">将连接组配置为接受程序包的任何版本，这使你可以升级程序包，而无需禁用连接组。</span><span class="sxs-lookup"><span data-stu-id="bbd82-291">Configure a connection group to accept any version of a package, which enables you to upgrade a package without having to disable the connection group.</span></span> <span data-ttu-id="bbd82-292">此外，如果在连接组中有一个可选程序包，并且该程序包的版本不正确，则会忽略该程序包，并且不会阻止创建连接组的虚拟环境。</span><span class="sxs-lookup"><span data-stu-id="bbd82-292">In addition, if there is an optional package with an incorrect version in the connection group, the package is ignored and won’t block the connection group’s virtual environment from being created.</span></span></p></td>
<td align="left"><p><a href="how-to-make-a-connection-group-ignore-the-package-version.md" data-raw-source="[How to Make a Connection Group Ignore the Package Version](how-to-make-a-connection-group-ignore-the-package-version.md)"><span data-ttu-id="bbd82-293">如何使连接组忽略程序包版本</span><span class="sxs-lookup"><span data-stu-id="bbd82-293">How to Make a Connection Group Ignore the Package Version</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bbd82-294">限制最终用户的发布功能</span><span class="sxs-lookup"><span data-stu-id="bbd82-294">Limit end users’ publishing capabilities</span></span></p></td>
<td align="left"><p><span data-ttu-id="bbd82-295">仅允许管理员（而非最终用户）发布程序包和启用连接组。</span><span class="sxs-lookup"><span data-stu-id="bbd82-295">Enable only administrators (not end users) to publish packages and to enable connection groups.</span></span></p></td>
<td align="left"><p><span data-ttu-id="bbd82-296">有关连接组的信息，请参阅 <a href="how-to-allow-only-administrators-to-enable-connection-groups.md" data-raw-source="[How to Allow Only Administrators to Enable Connection Groups](how-to-allow-only-administrators-to-enable-connection-groups.md)"> 如何仅允许管理员启用连接组</span><span class="sxs-lookup"><span data-stu-id="bbd82-296">For information about connection groups, see <a href="how-to-allow-only-administrators-to-enable-connection-groups.md" data-raw-source="[How to Allow Only Administrators to Enable Connection Groups](how-to-allow-only-administrators-to-enable-connection-groups.md)">How to Allow Only Administrators to Enable Connection Groups</span></span></a></p>
<p><span data-ttu-id="bbd82-297">有关程序包的详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="bbd82-297">For information about packages, see the following articles:</span></span></p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="bbd82-298">方法</span><span class="sxs-lookup"><span data-stu-id="bbd82-298">Method</span></span></th>
<th align="left"><span data-ttu-id="bbd82-299">链接到详细信息</span><span class="sxs-lookup"><span data-stu-id="bbd82-299">Link to more information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bbd82-300">管理控制台</span><span class="sxs-lookup"><span data-stu-id="bbd82-300">Management console</span></span></p></td>
<td align="left"><p><a href="how-to-publish-a-package-by-using-the-management-console-50.md" data-raw-source="[How to Publish a Package by Using the Management Console](how-to-publish-a-package-by-using-the-management-console-50.md)"><span data-ttu-id="bbd82-301">如何使用管理控制台发布程序包</span><span class="sxs-lookup"><span data-stu-id="bbd82-301">How to Publish a Package by Using the Management Console</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bbd82-302">PowerShell</span><span class="sxs-lookup"><span data-stu-id="bbd82-302">PowerShell</span></span></p></td>
<td align="left"><p><a href="how-to-manage-connection-groups-on-a-stand-alone-computer-by-using-powershell.md#bkmk-admin-only-posh-topic-cg" data-raw-source="[How to Manage Connection Groups on a Stand-alone Computer by Using PowerShell](how-to-manage-connection-groups-on-a-stand-alone-computer-by-using-powershell.md#bkmk-admin-only-posh-topic-cg)"><span data-ttu-id="bbd82-303">如何使用 PowerShell 管理独立计算机上的连接组</span><span class="sxs-lookup"><span data-stu-id="bbd82-303">How to Manage Connection Groups on a Stand-alone Computer by Using PowerShell</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bbd82-304">第三方电子软件交付系统</span><span class="sxs-lookup"><span data-stu-id="bbd82-304">Third-party electronic software delivery system</span></span></p></td>
<td align="left"><p><a href="how-to-enable-only-administrators-to-publish-packages-by-using-an-esd.md" data-raw-source="[How to Enable Only Administrators to Publish Packages by Using an ESD](how-to-enable-only-administrators-to-publish-packages-by-using-an-esd.md)"><span data-ttu-id="bbd82-305">如何使用 ESD 来仅允许管理员发布程序包</span><span class="sxs-lookup"><span data-stu-id="bbd82-305">How to Enable Only Administrators to Publish Packages by Using an ESD</span></span></a></p></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bbd82-306">为特定用户启用或禁用连接组</span><span class="sxs-lookup"><span data-stu-id="bbd82-306">Enable or disable a connection group for a specific user</span></span></p></td>
<td align="left"><p><span data-ttu-id="bbd82-307">管理员可以通过将 optional <strong> -UserSID </strong> 参数与以下 cmdlet 结合使用来启用或禁用特定用户的连接组：</span><span class="sxs-lookup"><span data-stu-id="bbd82-307">Administrators can enable or disable a connection group for a specific user by using the optional <strong>–UserSID</strong> parameter with the following cmdlets:</span></span></p>
<ul>
<li><p><span data-ttu-id="bbd82-308">Enable-AppVClientConnectionGroup</span><span class="sxs-lookup"><span data-stu-id="bbd82-308">Enable-AppVClientConnectionGroup</span></span></p></li>
<li><p><span data-ttu-id="bbd82-309">Disable-AppVClientConnectionGroup</span><span class="sxs-lookup"><span data-stu-id="bbd82-309">Disable-AppVClientConnectionGroup</span></span></p></li>
</ul></td>
<td align="left"><p><a href="how-to-manage-connection-groups-on-a-stand-alone-computer-by-using-powershell.md#bkmk-enable-cg-for-user-poshtopic" data-raw-source="[How to Manage Connection Groups on a Stand-alone Computer by Using PowerShell](how-to-manage-connection-groups-on-a-stand-alone-computer-by-using-powershell.md#bkmk-enable-cg-for-user-poshtopic)"><span data-ttu-id="bbd82-310">如何使用 PowerShell 管理独立计算机上的连接组</span><span class="sxs-lookup"><span data-stu-id="bbd82-310">How to Manage Connection Groups on a Stand-alone Computer by Using PowerShell</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bbd82-311">将相同的包路径合并到连接组中的一个虚拟目录中</span><span class="sxs-lookup"><span data-stu-id="bbd82-311">Merging identical package paths into one virtual directory in connection groups</span></span></p></td>
<td align="left"><p><span data-ttu-id="bbd82-312">如果连接组中的两个或多个程序包包含相同的目录路径，则路径将合并到连接组虚拟环境内的单个虚拟目录中。</span><span class="sxs-lookup"><span data-stu-id="bbd82-312">If two or more packages in a connection group contain identical directory paths, the paths are merged into a single virtual directory inside the connection group virtual environment.</span></span></p>
<p><span data-ttu-id="bbd82-313">这种路径合并允许一个程序包中的应用程序访问不同程序包中的文件。</span><span class="sxs-lookup"><span data-stu-id="bbd82-313">This merging of paths allows an application in one package to access files that are in a different package.</span></span></p></td>
<td align="left"><p><a href="about-the-connection-group-virtual-environment.md#bkmk-merged-root-ve-exp" data-raw-source="[About the Connection Group Virtual Environment](about-the-connection-group-virtual-environment.md#bkmk-merged-root-ve-exp)"><span data-ttu-id="bbd82-314">关于连接组虚拟环境</span><span class="sxs-lookup"><span data-stu-id="bbd82-314">About the Connection Group Virtual Environment</span></span></a></p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-usersid-pub-pkgs-specf-user"></a><span data-ttu-id="bbd82-315">管理员可以发布和取消发布特定用户的程序包</span><span class="sxs-lookup"><span data-stu-id="bbd82-315">Administrators can publish and unpublish packages for a specific user</span></span>


<span data-ttu-id="bbd82-316">管理员可以使用以下 cmdlet 发布或取消发布特定用户的程序包。</span><span class="sxs-lookup"><span data-stu-id="bbd82-316">Administrators can use the following cmdlets to publish or unpublish packages for a specific user.</span></span> <span data-ttu-id="bbd82-317">若要使用 cmdlet，请输入 **-UserSID**参数，后跟用户的安全标识符（SID）。</span><span class="sxs-lookup"><span data-stu-id="bbd82-317">To use the cmdlets, enter the **–UserSID** parameter, followed by the user’s security identifier (SID).</span></span> <span data-ttu-id="bbd82-318">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="bbd82-318">For more information, see:</span></span>

-   [<span data-ttu-id="bbd82-319">如何使用 PowerShell 管理在独立计算机上运行的 App-V 5.0 程序包</span><span class="sxs-lookup"><span data-stu-id="bbd82-319">How to Manage App-V 5.0 Packages Running on a Stand-Alone Computer by Using PowerShell</span></span>](how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md#bkmk-pub-pkg-a-user-standalone-posh)

-   [<span data-ttu-id="bbd82-320">如何使用 PowerShell 管理在独立计算机上运行的 App-V 5.0 程序包</span><span class="sxs-lookup"><span data-stu-id="bbd82-320">How to Manage App-V 5.0 Packages Running on a Stand-Alone Computer by Using PowerShell</span></span>](how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md#bkmk-unpub-pkg-specfc-use)

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="bbd82-321">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="bbd82-321">Cmdlet</span></span></th>
<th align="left"><span data-ttu-id="bbd82-322">示例</span><span class="sxs-lookup"><span data-stu-id="bbd82-322">Examples</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bbd82-323">发布-AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="bbd82-323">Publish-AppvClientPackage</span></span></p></td>
<td align="left"><p><span data-ttu-id="bbd82-324">发布-AppvClientPackage "ContosoApplication"-UserSID S-1-2-34-56789012-3456789012-345678901-2345</span><span class="sxs-lookup"><span data-stu-id="bbd82-324">Publish-AppvClientPackage “ContosoApplication” -UserSID S-1-2-34-56789012-3456789012-345678901-2345</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bbd82-325">取消发布-AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="bbd82-325">Unpublish-AppvClientPackage</span></span></p></td>
<td align="left"><p><span data-ttu-id="bbd82-326">取消发布-AppvClientPackage "ContosoApplication"-UserSID S-1-2-34-56789012-3456789012-345678901-2345</span><span class="sxs-lookup"><span data-stu-id="bbd82-326">Unpublish-AppvClientPackage “ContosoApplication” -UserSID S-1-2-34-56789012-3456789012-345678901-2345</span></span></p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-admins-only-pub-unpub-pkgs"></a><span data-ttu-id="bbd82-327">仅启用管理员发布和取消发布程序包</span><span class="sxs-lookup"><span data-stu-id="bbd82-327">Enable only administrators to publish and unpublish packages</span></span>


<span data-ttu-id="bbd82-328">你可以使用以下方法之一，仅允许管理员（而非最终用户）发布和取消发布程序包：</span><span class="sxs-lookup"><span data-stu-id="bbd82-328">You can enable only administrators (not end users) to publish and unpublish packages by using one of the following methods:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="bbd82-329">方法</span><span class="sxs-lookup"><span data-stu-id="bbd82-329">Method</span></span></th>
<th align="left"><span data-ttu-id="bbd82-330">详细信息</span><span class="sxs-lookup"><span data-stu-id="bbd82-330">More information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bbd82-331">组策略设置</span><span class="sxs-lookup"><span data-stu-id="bbd82-331">Group Policy setting</span></span></p></td>
<td align="left"><p><span data-ttu-id="bbd82-332">导航到以下组策略对象节点：</span><span class="sxs-lookup"><span data-stu-id="bbd82-332">Navigate to the following Group Policy Object node:</span></span></p>
<p><strong><span data-ttu-id="bbd82-333">计算机配置 &gt; 策略 &gt; 管理模板 &gt; 系统 &gt; 应用程序-V &gt; 发布 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="bbd82-333">Computer Configuration &gt; Policies &gt; Administrative Templates &gt; System &gt; App-V &gt; Publishing</strong>.</span></span></p>
<p><span data-ttu-id="bbd82-334">启用 " <strong> 要求发布为管理员 </strong> 组" 策略设置。</span><span class="sxs-lookup"><span data-stu-id="bbd82-334">Enable the <strong>Require publish as administrator</strong> Group Policy setting.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bbd82-335">PowerShell</span><span class="sxs-lookup"><span data-stu-id="bbd82-335">PowerShell</span></span></p></td>
<td align="left"><p><a href="how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md#bkmk-admins-pub-pkgs" data-raw-source="[How to Manage App-V 5.0 Packages Running on a Stand-Alone Computer by Using PowerShell](how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md#bkmk-admins-pub-pkgs)"><span data-ttu-id="bbd82-336">如何使用 PowerShell 管理在独立计算机上运行的 App-V 5.0 程序包</span><span class="sxs-lookup"><span data-stu-id="bbd82-336">How to Manage App-V 5.0 Packages Running on a Stand-Alone Computer by Using PowerShell</span></span></a></p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-runvirtual-reg-key"></a><span data-ttu-id="bbd82-337">RunVirtual 注册表项支持发布到用户的程序包</span><span class="sxs-lookup"><span data-stu-id="bbd82-337">RunVirtual registry key supports packages that are published to the user</span></span>


<span data-ttu-id="bbd82-338">App-v 5.0 SP3 添加了对将**RunVirtual**注册表项与用户发布的程序包中的虚拟化应用程序配合使用的支持。</span><span class="sxs-lookup"><span data-stu-id="bbd82-338">App-V 5.0 SP3 adds support for using the **RunVirtual** registry key with virtualized applications that are in user-published packages.</span></span> <span data-ttu-id="bbd82-339">**RunVirtual**注册表项允许你在虚拟环境中运行本地安装的应用程序，以及已使用 app-v 虚拟化的应用程序。</span><span class="sxs-lookup"><span data-stu-id="bbd82-339">The **RunVirtual** registry key lets you run a locally installed application in a virtual environment, along with applications that have been virtualized by using App-V.</span></span>

<span data-ttu-id="bbd82-340">以前，app-v 程序包中的虚拟化应用程序必须全局发布。</span><span class="sxs-lookup"><span data-stu-id="bbd82-340">Previously, the virtualized applications in App-V packages had to be published globally.</span></span> <span data-ttu-id="bbd82-341">有关**RunVirtual**和其他使用虚拟化应用程序在虚拟环境中运行本地安装的应用程序的方法的详细信息，请参阅在[虚拟环境中使用虚拟化应用程序运行本地安装的应用程序](running-a-locally-installed-application-inside-a-virtual-environment-with-virtualized-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="bbd82-341">For more about **RunVirtual** and about other methods of running locally installed applications in a virtual environment with virtualized applications, see [Running a Locally Installed Application Inside a Virtual Environment with Virtualized Applications](running-a-locally-installed-application-inside-a-virtual-environment-with-virtualized-applications.md).</span></span>

## <a href="" id="bkmk-posh-cmdlets-help"></a><span data-ttu-id="bbd82-342">新增 PowerShell cmdlet 和可更新 cmdlet 帮助</span><span class="sxs-lookup"><span data-stu-id="bbd82-342">New PowerShell cmdlets and updateable cmdlet help</span></span>


<span data-ttu-id="bbd82-343">App-v 5.0 SP3 中包含新的 PowerShell cmdlet 和可更新的 cmdlet 帮助。</span><span class="sxs-lookup"><span data-stu-id="bbd82-343">New PowerShell cmdlets and updateable cmdlet help are included in App-V 5.0 SP3.</span></span> <span data-ttu-id="bbd82-344">若要下载 cmdlet 模块，请参阅[如何加载 PowerShell cmdlet 和获取 Cmdlet 帮助](how-to-load-the-powershell-cmdlets-and-get-cmdlet-help-50-sp3.md#bkmk-load-cmdlets)。</span><span class="sxs-lookup"><span data-stu-id="bbd82-344">To download the cmdlet modules, see [How to Load the PowerShell Cmdlets and Get Cmdlet Help](how-to-load-the-powershell-cmdlets-and-get-cmdlet-help-50-sp3.md#bkmk-load-cmdlets).</span></span>

### <span data-ttu-id="bbd82-345">新的 App-v 5.0 SP3 服务器 PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="bbd82-345">New App-V 5.0 SP3 Server PowerShell cmdlets</span></span>

<span data-ttu-id="bbd82-346">已添加用于 App-v 服务器的新 Windows PowerShell cmdlet，以帮助你管理连接组。</span><span class="sxs-lookup"><span data-stu-id="bbd82-346">New Windows PowerShell cmdlets for the App-V Server have been added to help you manage connection groups.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="bbd82-347">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="bbd82-347">Cmdlet</span></span></th>
<th align="left"><span data-ttu-id="bbd82-348">描述</span><span class="sxs-lookup"><span data-stu-id="bbd82-348">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bbd82-349">Add-AppvServerConnectionGroupPackage</span><span class="sxs-lookup"><span data-stu-id="bbd82-349">Add-AppvServerConnectionGroupPackage</span></span></p></td>
<td align="left"><p><span data-ttu-id="bbd82-350">将程序包追加到连接组的末尾&#39;s 程序包列表，使你能够将程序包配置为可选和/或在连接组中不使用任何版本。</span><span class="sxs-lookup"><span data-stu-id="bbd82-350">Appends a package to the end of a connection group&#39;s package list and enables you to configure the package as optional and/or with no version within the connection group.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bbd82-351">Set-AppvServerConnectionGroupPackage</span><span class="sxs-lookup"><span data-stu-id="bbd82-351">Set-AppvServerConnectionGroupPackage</span></span></p></td>
<td align="left"><p><span data-ttu-id="bbd82-352">使你能够编辑有关连接组程序包的详细信息，例如它是否是可选的。</span><span class="sxs-lookup"><span data-stu-id="bbd82-352">Enables you to edit details about the connection group package, such as whether it is optional.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bbd82-353">Remove-AppvServerConnectionGroupPackage</span><span class="sxs-lookup"><span data-stu-id="bbd82-353">Remove-AppvServerConnectionGroupPackage</span></span></p></td>
<td align="left"><p><span data-ttu-id="bbd82-354">从连接组中删除程序包。</span><span class="sxs-lookup"><span data-stu-id="bbd82-354">Removes a package from a connection group.</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-get-cmdlet-help"></a><span data-ttu-id="bbd82-355">获取有关 PowerShell cmdlet 的帮助</span><span class="sxs-lookup"><span data-stu-id="bbd82-355">Getting help for the PowerShell cmdlets</span></span>

<span data-ttu-id="bbd82-356">Cmdlet 帮助可采用以下格式：</span><span class="sxs-lookup"><span data-stu-id="bbd82-356">Cmdlet help is available in the following formats:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="bbd82-357">格式</span><span class="sxs-lookup"><span data-stu-id="bbd82-357">Format</span></span></th>
<th align="left"><span data-ttu-id="bbd82-358">描述</span><span class="sxs-lookup"><span data-stu-id="bbd82-358">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bbd82-359">作为可下载的模块</span><span class="sxs-lookup"><span data-stu-id="bbd82-359">As a downloadable module</span></span></p></td>
<td align="left"><p><span data-ttu-id="bbd82-360">下载 cmdlet 模块后获取最新帮助：</span><span class="sxs-lookup"><span data-stu-id="bbd82-360">To get the latest help after downloading the cmdlet module:</span></span></p>
<ol>
<li><p><span data-ttu-id="bbd82-361">打开 Windows PowerShell 或 Windows PowerShell 集成脚本环境（ISE）。</span><span class="sxs-lookup"><span data-stu-id="bbd82-361">Open Windows PowerShell or Windows PowerShell Integrated Scripting Environment (ISE).</span></span></p></li>
<li><p><span data-ttu-id="bbd82-362">键入以下命令之一，为所需的模块加载 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="bbd82-362">Type one of the following commands to load the cmdlets for the module you want:</span></span></p></li>
</ol>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="bbd82-363">App-v 组件</span><span class="sxs-lookup"><span data-stu-id="bbd82-363">App-V component</span></span></th>
<th align="left"><span data-ttu-id="bbd82-364">要键入的命令</span><span class="sxs-lookup"><span data-stu-id="bbd82-364">Command to type</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bbd82-365">App-v 服务器</span><span class="sxs-lookup"><span data-stu-id="bbd82-365">App-V Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="bbd82-366">Update-Help-Module AppvServer</span><span class="sxs-lookup"><span data-stu-id="bbd82-366">Update-Help-Module AppvServer</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bbd82-367">App-v 排序器</span><span class="sxs-lookup"><span data-stu-id="bbd82-367">App-V Sequencer</span></span></p></td>
<td align="left"><p><span data-ttu-id="bbd82-368">Update-Help-Module AppvSequencer</span><span class="sxs-lookup"><span data-stu-id="bbd82-368">Update-Help-Module AppvSequencer</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bbd82-369">App-v 客户端</span><span class="sxs-lookup"><span data-stu-id="bbd82-369">App-V client</span></span></p></td>
<td align="left"><p><span data-ttu-id="bbd82-370">Update-Help-Module AppvClient</span><span class="sxs-lookup"><span data-stu-id="bbd82-370">Update-Help-Module AppvClient</span></span></p></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bbd82-371">在 TechNet 上作为网页</span><span class="sxs-lookup"><span data-stu-id="bbd82-371">On TechNet as web pages</span></span></p></td>
<td align="left"><p><span data-ttu-id="bbd82-372">在 <a href="https://technet.microsoft.com/library/dn520245.aspx" data-raw-source="[Microsoft Desktop Optimization Pack Automation with Windows PowerShell](https://technet.microsoft.com/library/dn520245.aspx)"> Windows PowerShell 的 Microsoft 桌面优化包自动化下，查看 app-v 节点 </a> 。</span><span class="sxs-lookup"><span data-stu-id="bbd82-372">See the App-V node under <a href="https://technet.microsoft.com/library/dn520245.aspx" data-raw-source="[Microsoft Desktop Optimization Pack Automation with Windows PowerShell](https://technet.microsoft.com/library/dn520245.aspx)">Microsoft Desktop Optimization Pack Automation with Windows PowerShell</a>.</span></span></p></td>
</tr>
</tbody>
</table>



<span data-ttu-id="bbd82-373">有关详细信息，请参阅[如何加载 PowerShell cmdlet 和获取 Cmdlet 帮助](how-to-load-the-powershell-cmdlets-and-get-cmdlet-help-50-sp3.md)。</span><span class="sxs-lookup"><span data-stu-id="bbd82-373">For more information, see [How to Load the PowerShell Cmdlets and Get Cmdlet Help](how-to-load-the-powershell-cmdlets-and-get-cmdlet-help-50-sp3.md).</span></span>

## <a href="" id="bkmk-pvad-hidden"></a><span data-ttu-id="bbd82-374">主虚拟应用程序目录（PVAD）已隐藏，但可以启用</span><span class="sxs-lookup"><span data-stu-id="bbd82-374">Primary virtual application directory (PVAD) is hidden but can be turned on</span></span>


<span data-ttu-id="bbd82-375">主虚拟应用程序目录（PVAD）在 App-v 5.0 SP3 中处于隐藏状态，但你可以将其重新打开并使用以下方法之一使其可见：</span><span class="sxs-lookup"><span data-stu-id="bbd82-375">The primary virtual application directory (PVAD) is hidden in App-V 5.0 SP3, but you can turn it back on and make it visible by using one of the following methods:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="bbd82-376">方法</span><span class="sxs-lookup"><span data-stu-id="bbd82-376">Method</span></span></th>
<th align="left"><span data-ttu-id="bbd82-377">步骤</span><span class="sxs-lookup"><span data-stu-id="bbd82-377">Steps</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bbd82-378">使用命令行参数</span><span class="sxs-lookup"><span data-stu-id="bbd82-378">Use a command line parameter</span></span></p></td>
<td align="left"><p><span data-ttu-id="bbd82-379"><strong>将– EnablePVADControl </strong> 参数传递到 <strong>Sequencer.exe</strong> 。</span><span class="sxs-lookup"><span data-stu-id="bbd82-379">Pass the <strong>–EnablePVADControl</strong> parameter to the <strong>Sequencer.exe</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bbd82-380">创建注册表子项</span><span class="sxs-lookup"><span data-stu-id="bbd82-380">Create a registry subkey</span></span></p></td>
<td align="left"><ol>
<li><p><span data-ttu-id="bbd82-381">在注册表编辑器中，导航到：</span><span class="sxs-lookup"><span data-stu-id="bbd82-381">In the Registry Editor, navigate to:</span></span> <code>HKLM\SOFTWARE\Microsoft\AppV\Sequencer\Compatibility</code></p>
<div class="alert">
<strong><span data-ttu-id="bbd82-382">注意</span><span class="sxs-lookup"><span data-stu-id="bbd82-382">Note</span></span></strong><br/><p><span data-ttu-id="bbd82-383">如果该 <code>Compatibility</code> 子项不存在，则必须创建它。</span><span class="sxs-lookup"><span data-stu-id="bbd82-383">If the <code>Compatibility</code> subkey doesn’t exist, you must create it.</span></span></p>
</div>
<div>

</div></li>
<li><p><span data-ttu-id="bbd82-384">创建名为 EnablePVADControl 的 DWORD 值 <strong> </strong> ，并将该值设置为 <strong> 1 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="bbd82-384">Create a DWORD Value named <strong>EnablePVADControl</strong>, and set the value to <strong>1</strong>.</span></span></p>
<p><span data-ttu-id="bbd82-385">值为 <strong> 0 </strong> 意味着 PVAD 已隐藏。</span><span class="sxs-lookup"><span data-stu-id="bbd82-385">A value of <strong>0</strong> means that PVAD is hidden.</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>



<span data-ttu-id="bbd82-386">**有关 PVAD 的详细信息：** 使用排序器创建程序包时，可以为程序包输入任何安装路径。</span><span class="sxs-lookup"><span data-stu-id="bbd82-386">**More about PVAD:** When you use the Sequencer to create a package, you can enter any installation path for the package.</span></span> <span data-ttu-id="bbd82-387">在早期版本的 App-v 中，你需要将应用程序的主虚拟应用程序目录（PVAD）指定为 path。</span><span class="sxs-lookup"><span data-stu-id="bbd82-387">In past versions of App-V, you were required to specify the primary virtual application directory (PVAD) of the application as the path.</span></span> <span data-ttu-id="bbd82-388">PVAD 是你通常在本地计算机上安装应用程序（如果你未使用 App-v）的目录。</span><span class="sxs-lookup"><span data-stu-id="bbd82-388">PVAD is the directory to which you would typically install an application on your local computer if you weren’t using App-V.</span></span> <span data-ttu-id="bbd82-389">例如，如果在计算机上安装 Office，则 PVAD 通常会 C:\\program files Files\\Microsoft Office\\。</span><span class="sxs-lookup"><span data-stu-id="bbd82-389">For example, if you were installing Office on a computer, the PVAD typically would be C:\\Program Files\\Microsoft Office\\.</span></span>

## <a href="" id="bkmk-pub-metadata-clientversion"></a><span data-ttu-id="bbd82-390">需要 ClientVersion，才能查看 App-v 发布元数据</span><span class="sxs-lookup"><span data-stu-id="bbd82-390">ClientVersion is required to view App-V publishing metadata</span></span>


<span data-ttu-id="bbd82-391">在 App-v 5.0 SP3 中，当你查询用于元数据的 app-v 发布服务器时，必须在地址中提供以下值：</span><span class="sxs-lookup"><span data-stu-id="bbd82-391">In App-V 5.0 SP3, you must provide the following values in the address when you query the App-V Publishing server for metadata:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="bbd82-392">值</span><span class="sxs-lookup"><span data-stu-id="bbd82-392">Value</span></span></th>
<th align="left"><span data-ttu-id="bbd82-393">其他详细信息</span><span class="sxs-lookup"><span data-stu-id="bbd82-393">Additional details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="bbd82-394">ClientVersion</span><span class="sxs-lookup"><span data-stu-id="bbd82-394">ClientVersion</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="bbd82-395">如果省略查询中的 <strong> ClientVersion </strong> 参数，则元数据将排除新的 APP-V 5.0 SP3 功能。</span><span class="sxs-lookup"><span data-stu-id="bbd82-395">If you omit the <strong>ClientVersion</strong> parameter from the query, the metadata excludes the new App-V 5.0 SP3 features.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="bbd82-396">ClientOS</span><span class="sxs-lookup"><span data-stu-id="bbd82-396">ClientOS</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="bbd82-397">只有在对程序包进行排序时选择特定客户端操作系统时，才必须提供此值。</span><span class="sxs-lookup"><span data-stu-id="bbd82-397">You have to provide this value only if you select specific client operating systems when you sequence the package.</span></span> <span data-ttu-id="bbd82-398">如果选择 "默认（所有操作系统）"，请不要在查询中指定此值。</span><span class="sxs-lookup"><span data-stu-id="bbd82-398">If you select the default (all operating systems), do not specify this value in the query.</span></span></p>
<p><span data-ttu-id="bbd82-399">如果省略查询中的 <strong> ClientOS </strong> 参数，则只有已排序支持任何操作系统的程序包才会显示在元数据中。</span><span class="sxs-lookup"><span data-stu-id="bbd82-399">If you omit the <strong>ClientOS</strong> parameter from the query, only the packages that were sequenced to support any operating system appear in the metadata.</span></span></p></td>
</tr>
</tbody>
</table>



<span data-ttu-id="bbd82-400">有关此查询的语法和示例，请参阅[查看 App-v 服务器发布元数据](viewing-app-v-server-publishing-metadata.md)。</span><span class="sxs-lookup"><span data-stu-id="bbd82-400">For syntax and examples of this query, see [Viewing App-V Server Publishing Metadata](viewing-app-v-server-publishing-metadata.md).</span></span>

## <a href="" id="bkmk-event-logs-moved"></a><span data-ttu-id="bbd82-401">App-v 事件日志已合并</span><span class="sxs-lookup"><span data-stu-id="bbd82-401">App-V event logs have been consolidated</span></span>


<span data-ttu-id="bbd82-402">以下事件日志（以前位于**应用程序和服务日志/microsoft/appv/app-v &lt; 组件 &gt; **上）已被移动到**应用程序和服务日志/microsoft/appv/ServiceLog**。</span><span class="sxs-lookup"><span data-stu-id="bbd82-402">The following event logs, previously located at **Applications and Services Logs/Microsoft/AppV/&lt;App-V component&gt;**, have been moved to **Applications and Services Logs/Microsoft/AppV/ServiceLog**.</span></span>

<span data-ttu-id="bbd82-403">若要查看日志，请**View**选择 &gt; 事件查看器应用程序中的 "查看**显示分析日志和调试日志**"。</span><span class="sxs-lookup"><span data-stu-id="bbd82-403">To view the logs, select **View** &gt; **Show Analytic and Debug Logs** in the Event Viewer application.</span></span>

<span data-ttu-id="bbd82-404">客户端目录客户端-集成客户端-PackageConfig 客户端-脚本客户端-服务客户端-Vemgr 客户端-VFSC FilesystemMetadataLibrary ManifestLibrary PolicyLibrary 子系统--AppPath 子系统-fta</span><span class="sxs-lookup"><span data-stu-id="bbd82-404">Client-Catalog Client-Integration Client-Orchestration Client-PackageConfig Client-Scripting Client-Service Client-Vemgr Client-VFSC FilesystemMetadataLibrary ManifestLibrary PolicyLibrary Subsystems-ActiveX Subsystems-AppPath Subsystems-Com Subsystems-fta</span></span>

## <span data-ttu-id="bbd82-405">如何获取 MDOP 技术</span><span class="sxs-lookup"><span data-stu-id="bbd82-405">How to Get MDOP Technologies</span></span>


<span data-ttu-id="bbd82-406">App-v 是 Microsoft 桌面优化包（MDOP）的一部分。</span><span class="sxs-lookup"><span data-stu-id="bbd82-406">App-V is a part of the Microsoft Desktop Optimization Pack (MDOP).</span></span> <span data-ttu-id="bbd82-407">MDOP 是 Microsoft 软件保障的一部分。</span><span class="sxs-lookup"><span data-stu-id="bbd82-407">MDOP is part of Microsoft Software Assurance.</span></span> <span data-ttu-id="bbd82-408">有关 Microsoft 软件保证和获取 MDOP 的详细信息，请参阅[如何获取 mdop](https://go.microsoft.com/fwlink/?LinkId=322049)。</span><span class="sxs-lookup"><span data-stu-id="bbd82-408">For more information about Microsoft Software Assurance and acquiring MDOP, see [How Do I Get MDOP](https://go.microsoft.com/fwlink/?LinkId=322049).</span></span>






## <span data-ttu-id="bbd82-409">相关主题</span><span class="sxs-lookup"><span data-stu-id="bbd82-409">Related topics</span></span>


[<span data-ttu-id="bbd82-410">App-V 5.0 SP3 发行说明</span><span class="sxs-lookup"><span data-stu-id="bbd82-410">Release Notes for App-V 5.0 SP3</span></span>](release-notes-for-app-v-50-sp3.md)









