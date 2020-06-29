---
title: AGPM 4.0 SP2 中的新增功能
description: AGPM 4.0 SP2 中的新增功能
author: dansimp
ms.assetid: 5c0dcab4-f27d-4153-8b8e-b280b080be51
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 56369207780cf0795f16eda91f249a26270c4b47
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801700"
---
# <span data-ttu-id="da9d9-103">AGPM 4.0 SP2 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="da9d9-103">What's New in AGPM 4.0 SP2</span></span>


<span data-ttu-id="da9d9-104">此内容介绍 Microsoft 高级组策略管理（AGPM）4.0 服务 Pack2 （SP2）的增强功能和受支持的配置。</span><span class="sxs-lookup"><span data-stu-id="da9d9-104">This content describes enhancements and supported configurations for Microsoft Advanced Group Policy Management (AGPM)4.0 Service Pack2 (SP2).</span></span> <span data-ttu-id="da9d9-105">如果此内容和其他 AGPM 文档之间存在差异，请考虑此内容的权威，并假定它取代了其他文档。</span><span class="sxs-lookup"><span data-stu-id="da9d9-105">If there is a difference between this content and other AGPM documentation, consider this content authoritative and assume that it supersedes the other documentation.</span></span>

## <a href="" id="what-s-new"></a><span data-ttu-id="da9d9-106">新增内容</span><span class="sxs-lookup"><span data-stu-id="da9d9-106">What’s new</span></span>


<span data-ttu-id="da9d9-107">AGPM 4.0 SP2 支持以下特性和功能。</span><span class="sxs-lookup"><span data-stu-id="da9d9-107">AGPM4.0 SP2 supports the following features and functionality.</span></span>

### <span data-ttu-id="da9d9-108">Windows 8.1 和 Windows Server2012 R2 支持</span><span class="sxs-lookup"><span data-stu-id="da9d9-108">Support for Windows8.1 and Windows Server2012 R2</span></span>

<span data-ttu-id="da9d9-109">AGPM 4.0 SP2 添加了对 Windows 8.1 和 Windows Server2012 R2 操作系统的支持。</span><span class="sxs-lookup"><span data-stu-id="da9d9-109">AGPM4.0 SP2 adds support for the Windows8.1 and Windows Server2012 R2 operating systems.</span></span>

### <span data-ttu-id="da9d9-110">新的和更改的客户端扩展</span><span class="sxs-lookup"><span data-stu-id="da9d9-110">New and changed client-side extensions</span></span>

<span data-ttu-id="da9d9-111">已为 AGPM 添加或更改了组策略客户端扩展，以支持 Windows 8.1 中的新策略设置。</span><span class="sxs-lookup"><span data-stu-id="da9d9-111">Group Policy client-side extensions have been added or changed for AGPM to support new policy settings in Windows8.1.</span></span> <span data-ttu-id="da9d9-112">这些策略设置使组策略管理员能够管理和跟踪 Windows 8.1-在两个组策略对象（Gpo）或模板之间更改的特定策略设置。</span><span class="sxs-lookup"><span data-stu-id="da9d9-112">These policy settings enable Group Policy administrators to manage and track Windows8.1–specific policy settings that change between two Group Policy Objects (GPOs) or templates.</span></span> <span data-ttu-id="da9d9-113">若要查看客户端扩展，请使用在 AGPM 客户端中可用的 "设置" 和 "差异" 报表。</span><span class="sxs-lookup"><span data-stu-id="da9d9-113">To view your client-side extensions, use the settings and difference reports that are available in the AGPM Client.</span></span>

<span data-ttu-id="da9d9-114">新的和已更改的组策略客户端扩展为：</span><span class="sxs-lookup"><span data-stu-id="da9d9-114">The new and changed Group Policy client-side extensions are:</span></span>

-   <span data-ttu-id="da9d9-115">**指定工作文件夹设置**。</span><span class="sxs-lookup"><span data-stu-id="da9d9-115">**Specify Work Folders settings**.</span></span> <span data-ttu-id="da9d9-116">如果启用此策略设置，IT 管理员可以配置要自动创建的工作文件夹。</span><span class="sxs-lookup"><span data-stu-id="da9d9-116">If you enable this policy setting, IT administrators can configure Work Folders to be created automatically.</span></span> <span data-ttu-id="da9d9-117">"工作文件夹" 功能使最终用户能够将文件从其 Windows 桌面设备同步到其其他设备。</span><span class="sxs-lookup"><span data-stu-id="da9d9-117">The Work Folders feature enables end users to synchronize files from their Windows desktop devices to their other devices.</span></span> <span data-ttu-id="da9d9-118">使用此策略设置可在最终用户的设备上创建同步关系，并配置如何识别存储用户工作文件夹的文件服务器。</span><span class="sxs-lookup"><span data-stu-id="da9d9-118">Use this policy setting to create the synchronization relationship on an end user’s devices and to configure how to identify the file server that stores the user’s Work Folders.</span></span> <span data-ttu-id="da9d9-119">如果选中 "**自动设置同步**" 复选框，则将在不使用用户输入的情况下创建同步合作关系，并且数据将自动开始与用户的设备同步。</span><span class="sxs-lookup"><span data-stu-id="da9d9-119">If you select the **Auto provision synchronization** check box, the synchronization partnership will be created without user input, and data will automatically start synchronizing to the user’s device.</span></span> <span data-ttu-id="da9d9-120">如果未选中 "**自动设置同步**" 复选框，则用户必须提供输入才能启动同步。</span><span class="sxs-lookup"><span data-stu-id="da9d9-120">If you do not select the **Auto provision synchronization** check box, users must provide input to start the synchronization.</span></span>

-   <span data-ttu-id="da9d9-121">**为所有用户强制自动设置**。</span><span class="sxs-lookup"><span data-stu-id="da9d9-121">**Force automatic setup for all users**.</span></span> <span data-ttu-id="da9d9-122">如果启用此策略设置，IT 管理员可以确定是否在最终用户的设备上自动创建工作文件夹，而无需最终用户输入。</span><span class="sxs-lookup"><span data-stu-id="da9d9-122">If you enable this policy setting, IT administrators can determine whether to create the Work Folders partnership automatically on end-user devices without input from end users.</span></span> <span data-ttu-id="da9d9-123">如果启用此策略设置，将根据你配置 "**指定工作文件夹设置**" 策略设置的方式设置同步。</span><span class="sxs-lookup"><span data-stu-id="da9d9-123">If you enable this policy setting, the synchronization will be set up according to how you configure the **Specify Work Folders settings** policy setting.</span></span> <span data-ttu-id="da9d9-124">如果将 "**强制自动设置为所有用户**" 策略设置设置为 "**已禁用**" 或 "**未配置**"，则将根据你在 "**指定工作文件夹设置**" 策略设置中设置**自动提供**选项来配置工作文件夹合作关系。</span><span class="sxs-lookup"><span data-stu-id="da9d9-124">If you set the **Force automatic setup for all users** policy setting to **Disabled** or **Not configured**, the Work Folders partnership will be configured according to how you set the **Automatic Provisioning** option in the **Specify Work Folders settings** policy setting.</span></span>

<span data-ttu-id="da9d9-125">有关工作文件夹功能的详细信息，请参阅[工作文件夹概述](https://go.microsoft.com/fwlink/?LinkId=330444)。</span><span class="sxs-lookup"><span data-stu-id="da9d9-125">For more information about the Work Folders feature, see [Work Folders Overview](https://go.microsoft.com/fwlink/?LinkId=330444).</span></span>

### <span data-ttu-id="da9d9-126">客户反馈和修补程序汇总</span><span class="sxs-lookup"><span data-stu-id="da9d9-126">Customer feedback and hotfix rollup</span></span>

<span data-ttu-id="da9d9-127">AGPM 4.0 SP2 包括修复程序的汇总，用于解决自 AGPM 4.0 服务 Pack1 （SP1）发布以来发现的问题。</span><span class="sxs-lookup"><span data-stu-id="da9d9-127">AGPM4.0 SP2 includes a rollup of hotfixes to address issues found since the AGPM4.0 Service Pack1 (SP1) release.</span></span> <span data-ttu-id="da9d9-128">AGPM 4.0 SP2 包含 Microsoft 高级组策略管理 4.0 SP1 Hotfix1 的最新修补程序，包括 Microsoft 高级组策略管理 4.0 SP1。</span><span class="sxs-lookup"><span data-stu-id="da9d9-128">AGPM4.0 SP2 contains the latest fixes up to and including Microsoft Advanced Group Policy Management4.0 SP1 Hotfix1.</span></span> <span data-ttu-id="da9d9-129">有关详细信息，请参阅知识文库文章[2873472](https://go.microsoft.com/fwlink/?LinkId=325400)。</span><span class="sxs-lookup"><span data-stu-id="da9d9-129">For more information, see Knowledge Base article [2873472](https://go.microsoft.com/fwlink/?LinkId=325400)).</span></span>

### <span data-ttu-id="da9d9-130">"设置" 和 "差异" 报告中的新组策略扩展</span><span class="sxs-lookup"><span data-stu-id="da9d9-130">New Group Policy extensions in settings and difference reports</span></span>

<span data-ttu-id="da9d9-131">新的组策略扩展已添加到 "设置" 和 "差异" 报告。</span><span class="sxs-lookup"><span data-stu-id="da9d9-131">The new Group Policy extensions have been added to the settings and difference reports.</span></span>

### <span data-ttu-id="da9d9-132">安装程序更改和支持</span><span class="sxs-lookup"><span data-stu-id="da9d9-132">Installer changes and support</span></span>

<span data-ttu-id="da9d9-133">AGPM 4.0 SP2 安装程序的更改和支持包括：</span><span class="sxs-lookup"><span data-stu-id="da9d9-133">The changes and support for the AGPM4.0 SP2 installer are:</span></span>

-   <span data-ttu-id="da9d9-134">如果在 Windows 8 或 Windows Server 2012 操作系统或更高版本的操作系统上安装了 AGPM 4.0 SP2，AGPM 安装程序将验证是否已安装所需的必备软件（组策略管理控制台（GPMC）和 Microsoft .NET Framework 3.5）。</span><span class="sxs-lookup"><span data-stu-id="da9d9-134">If you install AGPM4.0 SP2 on the Windows 8 or Windows Server 2012 operating system or later operating systems, the AGPM installer verifies that the required prerequisite software (the Group Policy Management Console (GPMC) and the Microsoft .NET Framework3.5) is installed.</span></span> <span data-ttu-id="da9d9-135">如果未安装此必备软件，则将阻止 AGPM 4.0 SP2 安装。</span><span class="sxs-lookup"><span data-stu-id="da9d9-135">If this prerequisite software is not installed, the AGPM4.0 SP2 installation is blocked.</span></span>

-   <span data-ttu-id="da9d9-136">安装 AGPM 服务器时，将自动启用 WCF 激活、非 HTTP 激活和 Windows 进程激活服务。</span><span class="sxs-lookup"><span data-stu-id="da9d9-136">When you install the AGPM Server, WCF Activation, Non-HTTP Activation, and Windows Process Activation Service are automatically enabled.</span></span>

-   <span data-ttu-id="da9d9-137">在 WindowsVista 客户端操作系统和更高版本的操作系统上，在安装 AGPM 4.0 SP2 之前，下载适用于您的操作系统的远程系统管理工具的相应版本。</span><span class="sxs-lookup"><span data-stu-id="da9d9-137">On the WindowsVista client operating system and later operating systems, download the appropriate version of the Remote System Administration Tools for your operating system before you install AGPM4.0 SP2.</span></span>

-   <span data-ttu-id="da9d9-138">AGPM 4.0 SP2 支持与早期支持的操作系统的向后兼容性。</span><span class="sxs-lookup"><span data-stu-id="da9d9-138">AGPM4.0 SP2 supports backward compatibility with older supported operating systems.</span></span>

### <span data-ttu-id="da9d9-139">无需重新设置配置参数即可升级到 AGPM 4.0 SP2 的功能</span><span class="sxs-lookup"><span data-stu-id="da9d9-139">Ability to upgrade to AGPM4.0 SP2 without reentering configuration parameters</span></span>

<span data-ttu-id="da9d9-140">你可以将 AGPM 客户端或 AGPM 服务器升级到 AGPM 4.0 SP2，而不提示仅从 AGPM 4.0 开始重新输入配置参数（称为 "智能升级"），如下表所示。</span><span class="sxs-lookup"><span data-stu-id="da9d9-140">You can upgrade the AGPM Client or AGPM Server to AGPM4.0 SP2 without being prompted to reenter configuration parameters (called the Smart Upgrade) only from AGPM4.0 onward, as shown in the following table.</span></span> <span data-ttu-id="da9d9-141">如果要从其他版本的 AGPM 升级到 AGPM 4.0 SP2 （如表中所示），则必须使用 "经典" 升级，这需要重新输入配置参数。</span><span class="sxs-lookup"><span data-stu-id="da9d9-141">If you are upgrading to AGPM4.0 SP2 from other versions of AGPM, as shown in the table, you must use the Classic Upgrade, which requires you to reenter the configuration parameters.</span></span> <span data-ttu-id="da9d9-142">由于 AGPM 的每个版本都与特定操作系统相关联，请参阅[选择要安装的 Agpm 版本](https://go.microsoft.com/fwlink/?LinkId=254350)，并确保在升级 AGPM 之前升级操作系统。</span><span class="sxs-lookup"><span data-stu-id="da9d9-142">Because each version of AGPM is associated with a particular operating system, see [Choosing Which Version of AGPM to Install](https://go.microsoft.com/fwlink/?LinkId=254350) and make sure that you upgrade your operating system as appropriate before you upgrade AGPM.</span></span>

**<span data-ttu-id="da9d9-143">AGPM 4.0 SP2 支持的升级</span><span class="sxs-lookup"><span data-stu-id="da9d9-143">AGPM 4.0 SP2 supported upgrades</span></span>**

<table style="width:100%;">
<colgroup>
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="da9d9-144">可升级的 AGPM 版本</span><span class="sxs-lookup"><span data-stu-id="da9d9-144">AGPM version from which you can upgrade</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="da9d9-145">2.5</span><span class="sxs-lookup"><span data-stu-id="da9d9-145">2.5</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="da9d9-146">3.0</span><span class="sxs-lookup"><span data-stu-id="da9d9-146">3.0</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="da9d9-147">4.0</span><span class="sxs-lookup"><span data-stu-id="da9d9-147">4.0</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="da9d9-148">4.0 SP1</span><span class="sxs-lookup"><span data-stu-id="da9d9-148">4.0 SP1</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="da9d9-149">4.0 SP2</span><span class="sxs-lookup"><span data-stu-id="da9d9-149">4.0 SP2</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="da9d9-150">2.5</span><span class="sxs-lookup"><span data-stu-id="da9d9-150">2.5</span></span></p></td>
<td align="left"><p><span data-ttu-id="da9d9-151">不适用</span><span class="sxs-lookup"><span data-stu-id="da9d9-151">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="da9d9-152">经典升级</span><span class="sxs-lookup"><span data-stu-id="da9d9-152">Classic Upgrade</span></span></p></td>
<td align="left"><p><span data-ttu-id="da9d9-153">经典升级</span><span class="sxs-lookup"><span data-stu-id="da9d9-153">Classic Upgrade</span></span></p></td>
<td align="left"><p><span data-ttu-id="da9d9-154">安装被阻止</span><span class="sxs-lookup"><span data-stu-id="da9d9-154">Installation is blocked</span></span></p></td>
<td align="left"><p><span data-ttu-id="da9d9-155">安装被阻止</span><span class="sxs-lookup"><span data-stu-id="da9d9-155">Installation is blocked</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="da9d9-156">3.0</span><span class="sxs-lookup"><span data-stu-id="da9d9-156">3.0</span></span></p></td>
<td align="left"><p><span data-ttu-id="da9d9-157">不适用</span><span class="sxs-lookup"><span data-stu-id="da9d9-157">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="da9d9-158">不适用</span><span class="sxs-lookup"><span data-stu-id="da9d9-158">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="da9d9-159">经典升级</span><span class="sxs-lookup"><span data-stu-id="da9d9-159">Classic Upgrade</span></span></p></td>
<td align="left"><p><span data-ttu-id="da9d9-160">安装被阻止</span><span class="sxs-lookup"><span data-stu-id="da9d9-160">Installation is blocked</span></span></p></td>
<td align="left"><p><span data-ttu-id="da9d9-161">安装被阻止</span><span class="sxs-lookup"><span data-stu-id="da9d9-161">Installation is blocked</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="da9d9-162">4.0</span><span class="sxs-lookup"><span data-stu-id="da9d9-162">4.0</span></span></p></td>
<td align="left"><p><span data-ttu-id="da9d9-163">不适用</span><span class="sxs-lookup"><span data-stu-id="da9d9-163">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="da9d9-164">不适用</span><span class="sxs-lookup"><span data-stu-id="da9d9-164">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="da9d9-165">不适用</span><span class="sxs-lookup"><span data-stu-id="da9d9-165">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="da9d9-166">智能升级</span><span class="sxs-lookup"><span data-stu-id="da9d9-166">Smart Upgrade</span></span></p></td>
<td align="left"><p><span data-ttu-id="da9d9-167">智能升级</span><span class="sxs-lookup"><span data-stu-id="da9d9-167">Smart Upgrade</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="da9d9-168">4.0 SP1</span><span class="sxs-lookup"><span data-stu-id="da9d9-168">4.0 SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="da9d9-169">不适用</span><span class="sxs-lookup"><span data-stu-id="da9d9-169">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="da9d9-170">不适用</span><span class="sxs-lookup"><span data-stu-id="da9d9-170">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="da9d9-171">不适用</span><span class="sxs-lookup"><span data-stu-id="da9d9-171">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="da9d9-172">不适用</span><span class="sxs-lookup"><span data-stu-id="da9d9-172">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="da9d9-173">智能升级</span><span class="sxs-lookup"><span data-stu-id="da9d9-173">Smart Upgrade</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="da9d9-174">支持的配置</span><span class="sxs-lookup"><span data-stu-id="da9d9-174">Supported configurations</span></span>


<span data-ttu-id="da9d9-175">AGPM 4.0 SP2 支持下表中的配置。</span><span class="sxs-lookup"><span data-stu-id="da9d9-175">AGPM4.0 SP2 supports the configurations in the following table.</span></span> <span data-ttu-id="da9d9-176">尽管 AGPM 支持混合配置，但我们强烈建议你在相同的操作系统行上运行 AGPM 客户端和 AGPM 服务器，例如，具有 windows Server2012 R2 的 windows 8.1 和 windows Server 2012 的 windows 8 等。</span><span class="sxs-lookup"><span data-stu-id="da9d9-176">Although AGPM supports mixed configurations, we strongly recommend that you run the AGPM Client and AGPM Server on the same operating system line—for example, Windows8.1 with Windows Server2012 R2, Windows 8 with Windows Server 2012, and so on.</span></span>

**<span data-ttu-id="da9d9-177">AGPM 4.0 SP2 支持的操作系统和策略设置</span><span class="sxs-lookup"><span data-stu-id="da9d9-177">AGPM4.0 SP2 supported operating systems and policy settings</span></span>**

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong><span data-ttu-id="da9d9-178">AGPM 服务器支持的配置</span><span class="sxs-lookup"><span data-stu-id="da9d9-178">Supported configurations for the AGPM Server</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="da9d9-179">AGPM 客户端支持的配置</span><span class="sxs-lookup"><span data-stu-id="da9d9-179">Supported configurations for the AGPM Client</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="da9d9-180">AGPM 支持</span><span class="sxs-lookup"><span data-stu-id="da9d9-180">AGPM Support</span></span></strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="da9d9-181">Windows Server2012 R2 或 Windows 8。1</span><span class="sxs-lookup"><span data-stu-id="da9d9-181">Windows Server2012 R2 or Windows8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="da9d9-182">Windows Server2012 R2 或 Windows 8。1</span><span class="sxs-lookup"><span data-stu-id="da9d9-182">Windows Server2012 R2 or Windows8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="da9d9-183">支持</span><span class="sxs-lookup"><span data-stu-id="da9d9-183">Supported</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="da9d9-184">Windows Server2012 R2、Windows Server 2012、Windows 8.1 或 Windows 8</span><span class="sxs-lookup"><span data-stu-id="da9d9-184">Windows Server2012 R2, Windows Server 2012, Windows8.1, or Windows 8</span></span></p></td>
<td align="left"><p><span data-ttu-id="da9d9-185">Windows Server 2012 或 Windows 8</span><span class="sxs-lookup"><span data-stu-id="da9d9-185">Windows Server 2012 or Windows 8</span></span></p></td>
<td align="left"><p><span data-ttu-id="da9d9-186">受支持，但不能编辑仅存在于 Windows 8.1 中的策略设置或首选项</span><span class="sxs-lookup"><span data-stu-id="da9d9-186">Supported, but cannot edit policy settings or preference items that exist only in Windows8.1</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="da9d9-187">Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="da9d9-187">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="da9d9-188">Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="da9d9-188">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="da9d9-189">受支持，但不能编辑仅存在于 Windows 8.1 或 Windows 8 中的策略设置或首选项</span><span class="sxs-lookup"><span data-stu-id="da9d9-189">Supported, but cannot edit policy settings or preference items that exist only in Windows8.1 or Windows 8</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="da9d9-190">Windows Server 2012、Windows Server2008R2、Windows 8 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="da9d9-190">Windows Server 2012, Windows Server2008R2, Windows 8, or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="da9d9-191">Windows Server2008 或 WindowsVista Service Pack 1 （SP1）</span><span class="sxs-lookup"><span data-stu-id="da9d9-191">Windows Server2008 or WindowsVista with Service Pack 1 (SP1)</span></span></p></td>
<td align="left"><p><span data-ttu-id="da9d9-192">受支持，但不能编辑仅存在于 Windows Server2012 R2、Windows Server 2012、Windows Server2008R2、Windows 8.1、windows 8 或 Windows7 中的策略设置或首选项</span><span class="sxs-lookup"><span data-stu-id="da9d9-192">Supported, but cannot edit policy settings or preference items that exist only in Windows Server2012 R2, Windows Server 2012, Windows Server2008R2, Windows8.1, Windows 8, or Windows7</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="da9d9-193">Windows Server2008 或 Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="da9d9-193">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="da9d9-194">Windows Server 2012、Windows Server2008R2、Windows 8 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="da9d9-194">Windows Server 2012, Windows Server2008R2, Windows 8, or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="da9d9-195">不支持</span><span class="sxs-lookup"><span data-stu-id="da9d9-195">Not supported</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="da9d9-196">Windows Server2008 或 Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="da9d9-196">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="da9d9-197">Windows Server2008 或 Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="da9d9-197">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="da9d9-198">受支持，但不能报告或编辑仅存在于 Windows Server2012 R2、Windows Server 2012、Windows Server2008R2、Windows 8.1、windows 8 或 Windows7 中的策略设置或首选项</span><span class="sxs-lookup"><span data-stu-id="da9d9-198">Supported, but cannot report or edit policy settings or preference items that exist only in Windows Server2012 R2, Windows Server 2012, Windows Server2008R2, Windows8.1, Windows 8, or Windows7</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="da9d9-199">安装 AGPM 4.0 SP2 的先决条件</span><span class="sxs-lookup"><span data-stu-id="da9d9-199">Prerequisites for installing AGPM4.0 SP2</span></span>


<span data-ttu-id="da9d9-200">下表介绍了当 .NET Framework 3.5 或远程服务器管理工具中的 GPMC 缺失时 Windows 8.1 上的 AGPM 4.0 SP2 客户端和服务器安装程序的行为。</span><span class="sxs-lookup"><span data-stu-id="da9d9-200">The following table describes the behavior of AGPM4.0 SP2 Client and Server installers on Windows8.1 when the .NET Framework3.5 or the GPMC in the Remote Server Administration Tools is missing.</span></span>

**<span data-ttu-id="da9d9-201">AGPM 客户端</span><span class="sxs-lookup"><span data-stu-id="da9d9-201">AGPM Client</span></span>**

**<span data-ttu-id="da9d9-202">AGPM 服务器</span><span class="sxs-lookup"><span data-stu-id="da9d9-202">AGPM Server</span></span>**

**<span data-ttu-id="da9d9-203">操作系统</span><span class="sxs-lookup"><span data-stu-id="da9d9-203">Operating system</span></span>**

**<span data-ttu-id="da9d9-204">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="da9d9-204">.NET Framework</span></span>**

**<span data-ttu-id="da9d9-205">远程服务器管理工具</span><span class="sxs-lookup"><span data-stu-id="da9d9-205">Remote Server Administration Tools</span></span>**

**<span data-ttu-id="da9d9-206">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="da9d9-206">.NET Framework</span></span>**

**<span data-ttu-id="da9d9-207">远程服务器管理工具</span><span class="sxs-lookup"><span data-stu-id="da9d9-207">Remote Server Administration Tools</span></span>**

**<span data-ttu-id="da9d9-208">Windows 8。1</span><span class="sxs-lookup"><span data-stu-id="da9d9-208">Windows8.1</span></span>**

<span data-ttu-id="da9d9-209">如果未启用或安装 .NET Framework 3.5，安装程序将阻止安装。</span><span class="sxs-lookup"><span data-stu-id="da9d9-209">If the .NET Framework3.5 is not enabled or installed, the installer blocks the installation.</span></span>

<span data-ttu-id="da9d9-210">如果 GPMC 未启用或未安装，安装程序将阻止安装。</span><span class="sxs-lookup"><span data-stu-id="da9d9-210">If the GPMC is not enabled or installed, the installer blocks the installation.</span></span>

<span data-ttu-id="da9d9-211">如果未启用或安装 .NET Framework 3.5，安装程序将阻止安装。</span><span class="sxs-lookup"><span data-stu-id="da9d9-211">If the .NET Framework3.5 is not enabled or installed, the installer blocks the installation.</span></span>

<span data-ttu-id="da9d9-212">如果 GPMC 未启用或未安装，安装程序将阻止安装。</span><span class="sxs-lookup"><span data-stu-id="da9d9-212">If the GPMC is not enabled or installed, the installer blocks the installation.</span></span>

**<span data-ttu-id="da9d9-213">Windows Server2012 R2</span><span class="sxs-lookup"><span data-stu-id="da9d9-213">Windows Server2012 R2</span></span>**

<span data-ttu-id="da9d9-214">如果未启用或安装 .NET Framework 3.5，安装程序将阻止安装。</span><span class="sxs-lookup"><span data-stu-id="da9d9-214">If the .NET Framework3.5 is not enabled or installed, the installer blocks the installation.</span></span>

<span data-ttu-id="da9d9-215">如果未启用 GPMC，安装程序将在安装期间启用它。</span><span class="sxs-lookup"><span data-stu-id="da9d9-215">If the GPMC is not enabled, the installer enables it during the installation.</span></span>

<span data-ttu-id="da9d9-216">如果未启用或安装 .NET Framework 3.5，安装程序将阻止安装。</span><span class="sxs-lookup"><span data-stu-id="da9d9-216">If the .NET Framework3.5 is not enabled or installed, the installer blocks the installation.</span></span>

<span data-ttu-id="da9d9-217">如果未启用 GPMC，安装程序将在安装期间启用它。</span><span class="sxs-lookup"><span data-stu-id="da9d9-217">If the GPMC is not enabled, the installer enables it during the installation.</span></span>

 

## <span data-ttu-id="da9d9-218">如何获取 MDOP 技术</span><span class="sxs-lookup"><span data-stu-id="da9d9-218">How to Get MDOP Technologies</span></span>


<span data-ttu-id="da9d9-219">AGPM 4.0 SP2 是 Microsoft 桌面优化包（MDOP）的一部分。</span><span class="sxs-lookup"><span data-stu-id="da9d9-219">AGPM 4.0 SP2 is a part of the Microsoft Desktop Optimization Pack (MDOP).</span></span> <span data-ttu-id="da9d9-220">MDOP 是 Microsoft 软件保障的一部分。</span><span class="sxs-lookup"><span data-stu-id="da9d9-220">MDOP is part of Microsoft Software Assurance.</span></span> <span data-ttu-id="da9d9-221">有关 Microsoft 软件保证和获取 MDOP 的详细信息，请参阅[如何获取 mdop](https://go.microsoft.com/fwlink/?LinkId=322049) （ https://go.microsoft.com/fwlink/?LinkId=322049) 。</span><span class="sxs-lookup"><span data-stu-id="da9d9-221">For more information about Microsoft Software Assurance and acquiring MDOP, see [How Do I Get MDOP](https://go.microsoft.com/fwlink/?LinkId=322049) (https://go.microsoft.com/fwlink/?LinkId=322049).</span></span>

## <span data-ttu-id="da9d9-222">相关主题</span><span class="sxs-lookup"><span data-stu-id="da9d9-222">Related topics</span></span>


[<span data-ttu-id="da9d9-223">高级组策略管理</span><span class="sxs-lookup"><span data-stu-id="da9d9-223">Advanced Group Policy Management</span></span>](index.md)

[<span data-ttu-id="da9d9-224">Microsoft 高级组策略管理 4.0 SP2 发行说明</span><span class="sxs-lookup"><span data-stu-id="da9d9-224">Release Notes for Microsoft Advanced Group Policy Management 4.0 SP2</span></span>](release-notes-for-microsoft-advanced-group-policy-management-40-sp2.md)

[<span data-ttu-id="da9d9-225">选择要安装的 AGPM 版本</span><span class="sxs-lookup"><span data-stu-id="da9d9-225">Choosing Which Version of AGPM to Install</span></span>](choosing-which-version-of-agpm-to-install.md)

 

 





