---
title: AGPM 4.0 SP1 中的新增功能
description: AGPM 4.0 SP1 中的新增功能
author: dansimp
ms.assetid: c6a3d94a-13c3-44e6-a466-c3011879999e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: eca1ee4a1c2eb943a25246dc31b127eaf72ff5fc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801703"
---
# <span data-ttu-id="10f61-103">AGPM 4.0 SP1 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="10f61-103">What's New in AGPM 4.0 SP1</span></span>


<span data-ttu-id="10f61-104">此 "新增功能" 内容介绍 Microsoft 高级组策略管理（AGPM） 4.0 SP1 的增强功能和受支持的配置。</span><span class="sxs-lookup"><span data-stu-id="10f61-104">This “What’s New” content describes enhancements and supported configurations for Microsoft Advanced Group Policy Management (AGPM) 4.0 SP1.</span></span> <span data-ttu-id="10f61-105">如果此内容和其他 AGPM 文档之间存在差异，此内容应视为权威内容，并且应该取代本产品附带的内容。</span><span class="sxs-lookup"><span data-stu-id="10f61-105">If there is a difference between this content and other AGPM documentation, this content should be considered authoritative and should supersede the content included with this product.</span></span>

## <a href="" id="what-s-new"></a><span data-ttu-id="10f61-106">新增内容</span><span class="sxs-lookup"><span data-stu-id="10f61-106">What’s new</span></span>


<span data-ttu-id="10f61-107">AGPM 4.0 SP1 支持下列增强：</span><span class="sxs-lookup"><span data-stu-id="10f61-107">AGPM 4.0 SP1 supports the following enhancements:</span></span>

### <span data-ttu-id="10f61-108">新的和更改的客户端扩展</span><span class="sxs-lookup"><span data-stu-id="10f61-108">New and changed client-side extensions</span></span>

<span data-ttu-id="10f61-109">已为 AGPM 添加或更改了组策略客户端扩展（CSEs），以支持 Windows 8 和 Windows Server 2012 中的新组策略。</span><span class="sxs-lookup"><span data-stu-id="10f61-109">Group Policy client-side extensions (CSEs) have been added or changed for AGPM to support new Group Policies in Windows 8 and Windows Server 2012.</span></span> <span data-ttu-id="10f61-110">这些组策略使组策略管理员能够管理和跟踪在两个组策略对象（Gpo）或模板之间更改的 Windows 8 特定组策略设置。</span><span class="sxs-lookup"><span data-stu-id="10f61-110">These group policies enable Group Policy administrators to manage and track Windows 8-specific Group Policy settings that change between two Group Policy Objects (GPOs) or templates.</span></span> <span data-ttu-id="10f61-111">你还可以使用特定于 Windows 8 的设置创建自定义 Gpo，并将 Gpo 配置和保存为模板。</span><span class="sxs-lookup"><span data-stu-id="10f61-111">You can also create custom GPOs, with Windows 8-specific settings, and configure and save the GPOs as a template.</span></span> <span data-ttu-id="10f61-112">若要查看 CSEs，请使用 AGPM 4.0 SP1 客户端中提供的 "设置" 和 "差异" 报表。</span><span class="sxs-lookup"><span data-stu-id="10f61-112">To view your CSEs, use the settings and difference reports that are available in the AGPM 4.0 SP1 client.</span></span>

<span data-ttu-id="10f61-113">新的和已更改的组策略客户端扩展为：</span><span class="sxs-lookup"><span data-stu-id="10f61-113">The new and changed Group Policy client-side extensions are:</span></span>

-   <span data-ttu-id="10f61-114">**中心访问策略：** 允许组策略管理员指定组策略服务器（例如，文件服务器）上的中心访问策略。</span><span class="sxs-lookup"><span data-stu-id="10f61-114">**Central Access Policy:** Enables Group Policy administrators to specify Central Access Policies on Group Policy servers, for example, file servers.</span></span> <span data-ttu-id="10f61-115">中心访问策略是由 GPO 项目指定并应用于策略目标的授权策略，用于促进对资源的集中访问和控制。</span><span class="sxs-lookup"><span data-stu-id="10f61-115">Central Access Policy is an authorization policy that is specified by a GPO item and applied to policy targets to facilitate centralized access and control of resources.</span></span> <span data-ttu-id="10f61-116">必须在 Active Directory 中的组策略客户端计算机上配置这些中心访问策略。</span><span class="sxs-lookup"><span data-stu-id="10f61-116">These Central Access Policies must be configured on a Group Policy client computer from within Active Directory.</span></span> <span data-ttu-id="10f61-117">组策略将适用的中心访问策略的知识分配给必须强制使用的计算机。</span><span class="sxs-lookup"><span data-stu-id="10f61-117">A Group Policy distributes the knowledge of an applicable Central Access Policy to the computers that have to enforce it.</span></span>

-   <span data-ttu-id="10f61-118">**名称解析策略更改：** 允许组策略管理员为 DNS 客户端计算机上的 DNS 安全和 DirectAccess 配置设置。</span><span class="sxs-lookup"><span data-stu-id="10f61-118">**Name Resolution Policy changes:** Enables Group Policy administrators to configure settings for DNS security and DirectAccess on DNS client computers.</span></span> <span data-ttu-id="10f61-119">添加了用于配置常规 DNS 服务器设置和编码设置的新选项卡。</span><span class="sxs-lookup"><span data-stu-id="10f61-119">New tabs for configuring Generic DNS Server settings and Encoding settings have been added.</span></span>

-   <span data-ttu-id="10f61-120">**组策略首选项更改：** 添加对 Windows 8 中添加的 Internet Explorer 10 设置的配置和管理的支持。</span><span class="sxs-lookup"><span data-stu-id="10f61-120">**Group Policy Preference changes:** Adds support for the configuration and management of Internet Explorer 10 settings that were added for Windows 8.</span></span>

-   <span data-ttu-id="10f61-121">**远程应用程序和桌面连接：** 允许组策略管理员指定用于远程应用程序和桌面连接的默认连接 URL。</span><span class="sxs-lookup"><span data-stu-id="10f61-121">**Remote Application and Desktop Connections:** Lets Group Policy administrators specify the default connection URL that is used for Remote Application and Desktop Connections.</span></span>

-   <span data-ttu-id="10f61-122">**Windows To Go 启动选项：** 允许组策略管理员配置当包含 Windows To Go 工作区的 USB 设备已连接时，计算机是否将引导到 Windows To Go。</span><span class="sxs-lookup"><span data-stu-id="10f61-122">**Windows To Go Startup Options:** Lets Group Policy administrators configure whether the computer will boot to Windows To Go if a USB device that contains a Windows To Go workspace is connected.</span></span>

-   <span data-ttu-id="10f61-123">**Windows To Go 休眠选项：** 允许组策略管理员配置当计算机从 Windows To Go 工作区启动时，计算机是否可以使用休眠睡眠状态（S4）。</span><span class="sxs-lookup"><span data-stu-id="10f61-123">**Windows To Go Hibernate Options:** Lets Group Policy administrators configure whether a computer can use the hibernation sleep state (S4) when the computer is started from a Windows To Go workspace.</span></span>

### <span data-ttu-id="10f61-124">客户反馈和修补程序汇总</span><span class="sxs-lookup"><span data-stu-id="10f61-124">Customer feedback and hotfix rollup</span></span>

<span data-ttu-id="10f61-125">AGPM 4.0 SP1 包括自 AGPM 4.0 发布以来发现的解决问题的修补程序汇总。</span><span class="sxs-lookup"><span data-stu-id="10f61-125">AGPM 4.0 SP1 includes a rollup of fixes to address issues found since the AGPM 4.0 release.</span></span> <span data-ttu-id="10f61-126">AGPM 4.0 SP1 包含的最新修复程序，包括 Microsoft 高级组策略管理4.0 修复程序1。</span><span class="sxs-lookup"><span data-stu-id="10f61-126">AGPM 4.0 SP1 contains the latest fixes up to and including Microsoft Advanced Group Policy Management 4.0 Hotfix 1.</span></span>

### <span data-ttu-id="10f61-127">"设置和差异" 报表显示新的组策略扩展</span><span class="sxs-lookup"><span data-stu-id="10f61-127">Settings and difference reports show new Group Policy extensions</span></span>

<span data-ttu-id="10f61-128">新的组策略扩展已添加到 "设置" 和 "差异" 报告。</span><span class="sxs-lookup"><span data-stu-id="10f61-128">The new Group Policy extensions have been added to the settings and difference reports.</span></span>

### <span data-ttu-id="10f61-129">安装程序更改和支持</span><span class="sxs-lookup"><span data-stu-id="10f61-129">Installer changes and support</span></span>

<span data-ttu-id="10f61-130">AGPM 4.0 SP1 安装程序的更改和支持如下所示：</span><span class="sxs-lookup"><span data-stu-id="10f61-130">The changes and support for the AGPM 4.0 SP1 installer are:</span></span>

-   <span data-ttu-id="10f61-131">如果在 Windows 8 或 Windows Server 2012 上安装了 AGPM 4.0 SP1，AGPM 安装程序将验证是否已安装所需的必备软件（组策略管理控制台和 .NET 3.5 Framework）。</span><span class="sxs-lookup"><span data-stu-id="10f61-131">If you install AGPM 4.0 SP1 on Windows 8 or Windows Server 2012, the AGPM installer verifies that the required prerequisite software (Group Policy Management Console and the .NET 3.5 Framework) is installed.</span></span> <span data-ttu-id="10f61-132">如果未安装这些必备组件，则将阻止 AGPM 4.0 SP1 安装。</span><span class="sxs-lookup"><span data-stu-id="10f61-132">If these prerequisites are not installed, the AGPM 4.0 SP1 installation is blocked.</span></span>

-   <span data-ttu-id="10f61-133">安装 AGPM 4.0 SP1 时，将自动启用 WCF 激活、非 HTTP 激活和 Windows 进程激活服务。</span><span class="sxs-lookup"><span data-stu-id="10f61-133">When you install AGPM 4.0 SP1, WCF Activation, Non-HTTP Activation, and Windows Process Activation Service are automatically enabled.</span></span>

-   <span data-ttu-id="10f61-134">在 Windows Vista、Windows 7 和 Windows 8 客户端操作系统上，下载适用于你的操作系统的远程系统管理工具包版本，然后再安装 AGPM 4.0 SP1。</span><span class="sxs-lookup"><span data-stu-id="10f61-134">On Windows Vista, Windows 7, and Windows 8 client operating systems, download the appropriate version of the Remote System Administration Toolkit for your operating system before you install AGPM 4.0 SP1.</span></span>

-   <span data-ttu-id="10f61-135">支持与旧版支持的操作系统的向后兼容性。</span><span class="sxs-lookup"><span data-stu-id="10f61-135">Backward compatibility with older supported operating systems is supported.</span></span>

### <span data-ttu-id="10f61-136">无需重新输入配置参数即可升级或更新到 AGPM 4.0 SP1 的功能</span><span class="sxs-lookup"><span data-stu-id="10f61-136">Ability to upgrade or update to AGPM 4.0 SP1 without re-entering configuration parameters</span></span>

<span data-ttu-id="10f61-137">您只能从 AGPM 4.0 将 AGPM 客户端或服务器升级到 AGPM 4.0 SP1，而无需提示重新输入配置参数（称为 "智能升级"），如下表所示。</span><span class="sxs-lookup"><span data-stu-id="10f61-137">You can upgrade the AGPM client or server to AGPM 4.0 SP1 only from AGPM 4.0 without being prompted to re-enter configuration parameters (called “Smart Upgrade”), as shown in the following table.</span></span> <span data-ttu-id="10f61-138">如果要从其他版本的 AGPM 升级到 AGPM 4.0 SP1 （如表中所示），则必须使用 "经典升级"，这要求重新输入配置参数。</span><span class="sxs-lookup"><span data-stu-id="10f61-138">If you are upgrading to AGPM 4.0 SP1 from other versions of AGPM, as shown in the table, you must use the “Classic Upgrade,” which requires you to re-enter the configuration parameters.</span></span> <span data-ttu-id="10f61-139">由于你的每个版本的 AGPM 都与特定操作系统相关联，因此请参阅[选择要安装的 Agpm 版本](https://go.microsoft.com/fwlink/?LinkId=254350)，并确保在执行升级之前根据需要升级操作系统。</span><span class="sxs-lookup"><span data-stu-id="10f61-139">Since each version of AGPM is associated with a particular operating system, refer to [Choosing Which Version of AGPM to Install](https://go.microsoft.com/fwlink/?LinkId=254350), and be sure to upgrade your operating system as appropriate before performing an upgrade.</span></span>

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="10f61-140">可升级的 AGPM 版本</span><span class="sxs-lookup"><span data-stu-id="10f61-140">AGPM Version From Which You Can Upgrade</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="10f61-141">2.5</span><span class="sxs-lookup"><span data-stu-id="10f61-141">2.5</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="10f61-142">3.0</span><span class="sxs-lookup"><span data-stu-id="10f61-142">3.0</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="10f61-143">4.0</span><span class="sxs-lookup"><span data-stu-id="10f61-143">4.0</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="10f61-144">4.0 SP1</span><span class="sxs-lookup"><span data-stu-id="10f61-144">4.0 SP1</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="10f61-145">2.5</span><span class="sxs-lookup"><span data-stu-id="10f61-145">2.5</span></span></p></td>
<td align="left"><p><span data-ttu-id="10f61-146">不适用</span><span class="sxs-lookup"><span data-stu-id="10f61-146">Not Applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="10f61-147">经典升级</span><span class="sxs-lookup"><span data-stu-id="10f61-147">Classic Upgrade</span></span></p></td>
<td align="left"><p><span data-ttu-id="10f61-148">经典升级</span><span class="sxs-lookup"><span data-stu-id="10f61-148">Classic Upgrade</span></span></p></td>
<td align="left"><p><span data-ttu-id="10f61-149">安装被阻止</span><span class="sxs-lookup"><span data-stu-id="10f61-149">Installation is blocked</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="10f61-150">3.0</span><span class="sxs-lookup"><span data-stu-id="10f61-150">3.0</span></span></p></td>
<td align="left"><p><span data-ttu-id="10f61-151">不适用</span><span class="sxs-lookup"><span data-stu-id="10f61-151">Not Applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="10f61-152">不适用</span><span class="sxs-lookup"><span data-stu-id="10f61-152">Not Applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="10f61-153">经典升级</span><span class="sxs-lookup"><span data-stu-id="10f61-153">Classic Upgrade</span></span></p></td>
<td align="left"><p><span data-ttu-id="10f61-154">安装被阻止</span><span class="sxs-lookup"><span data-stu-id="10f61-154">Installation is blocked</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="10f61-155">4.0</span><span class="sxs-lookup"><span data-stu-id="10f61-155">4.0</span></span></p></td>
<td align="left"><p><span data-ttu-id="10f61-156">不适用</span><span class="sxs-lookup"><span data-stu-id="10f61-156">Not Applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="10f61-157">不适用</span><span class="sxs-lookup"><span data-stu-id="10f61-157">Not Applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="10f61-158">不适用</span><span class="sxs-lookup"><span data-stu-id="10f61-158">Not Applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="10f61-159">智能升级</span><span class="sxs-lookup"><span data-stu-id="10f61-159">Smart Upgrade</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="10f61-160">支持的配置</span><span class="sxs-lookup"><span data-stu-id="10f61-160">Supported configurations</span></span>


<span data-ttu-id="10f61-161">AGPM 支持下表中的配置。</span><span class="sxs-lookup"><span data-stu-id="10f61-161">AGPM supports the configurations in the following table.</span></span> <span data-ttu-id="10f61-162">尽管 AGPM 支持混合配置，但强烈建议你在相同操作系统系列上运行 AGPM 客户端和服务器，例如，使用 windows Server 2012、windows 7 和 Windows Server 2008 R2 运行 Windows 8。</span><span class="sxs-lookup"><span data-stu-id="10f61-162">Although AGPM supports mixed configurations, it is strongly recommended that you run the AGPM client and server on the same operating system family, for example, Windows 8 with Windows Server 2012, Windows 7 with Windows Server 2008 R2, and so on.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="10f61-163">AGPM 4.0 SP1 服务器支持的配置</span><span class="sxs-lookup"><span data-stu-id="10f61-163">Supported Configurations for AGPM 4.0 SP1 Server</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="10f61-164">AGPM 4.0 SP1 客户端支持的配置</span><span class="sxs-lookup"><span data-stu-id="10f61-164">Supported Configurations for AGPM 4.0 SP1 Client</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="10f61-165">AGPM 4.0 SP1 支持</span><span class="sxs-lookup"><span data-stu-id="10f61-165">AGPM 4.0 SP1 Support</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="10f61-166">Windows 8 或 Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="10f61-166">Windows 8 or Windows Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="10f61-167">Windows 8 或 Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="10f61-167">Windows 8 or Windows Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="10f61-168">支持</span><span class="sxs-lookup"><span data-stu-id="10f61-168">Supported</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="10f61-169">Windows Server 2008 R2 或 Windows 7</span><span class="sxs-lookup"><span data-stu-id="10f61-169">Windows Server 2008 R2 or Windows 7</span></span></p></td>
<td align="left"><p><span data-ttu-id="10f61-170">Windows Server 2008 R2 或 Windows 7</span><span class="sxs-lookup"><span data-stu-id="10f61-170">Windows Server 2008 R2 or Windows 7</span></span></p></td>
<td align="left"><p><span data-ttu-id="10f61-171">受支持，但不能编辑仅存在于 Windows 8 中的策略设置或首选项</span><span class="sxs-lookup"><span data-stu-id="10f61-171">Supported, but cannot edit policy settings or preference items that exist only in Windows 8</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="10f61-172">Windows Server 2008 R2 或 Windows 7 或 windows 8 或 windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="10f61-172">Windows Server 2008 R2 or Windows 7 or Windows 8 or Windows Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="10f61-173">Windows Server 2008 或 Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="10f61-173">Windows Server 2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="10f61-174">受支持，但不能编辑仅存在于 Windows Server 2008 R2 或 Windows 7 或 Windows 8 中的策略设置或首选项。</span><span class="sxs-lookup"><span data-stu-id="10f61-174">Supported, but cannot edit policy settings or preference items that exist only in Windows Server 2008 R2 or Windows 7 or Windows 8.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="10f61-175">Windows Server 2008 或 Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="10f61-175">Windows Server 2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="10f61-176">Windows Server 2008 R2 或 Windows 7 或 windows 8 或 windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="10f61-176">Windows Server 2008 R2 or Windows 7 or Windows 8 or Windows Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="10f61-177">支持</span><span class="sxs-lookup"><span data-stu-id="10f61-177">Supported</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="10f61-178">Windows Server 2008 或 Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="10f61-178">Windows Server 2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="10f61-179">Windows Server 2008 或 Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="10f61-179">Windows Server 2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="10f61-180">受支持，但无法报告或编辑仅存在于 Windows Server 2008 R2 或 Windows 7 或 Windows 8 中的策略设置或首选项</span><span class="sxs-lookup"><span data-stu-id="10f61-180">Supported, but cannot report or edit policy settings or preference items that exist only in Windows Server 2008 R2 or Windows 7 or Windows 8</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="10f61-181">安装 AGPM 4.0 SP1 的先决条件</span><span class="sxs-lookup"><span data-stu-id="10f61-181">Prerequisites for installing AGPM 4.0 SP1</span></span>


<span data-ttu-id="10f61-182">下表介绍了在缺少远程服务器管理工具（RSAT）中的 .NET 3.5 或组策略管理控制台时，AGPM 4.0 SP1 客户端和服务器安装程序的 Windows 8 上的行为。</span><span class="sxs-lookup"><span data-stu-id="10f61-182">The following table describes the behavior on Windows 8 of AGPM 4.0 SP1 client and server installers when .NET 3.5 or the Group Policy Management Console in the Remote Server Administration Tools (RSAT) is missing.</span></span>

**<span data-ttu-id="10f61-183">AGPM 客户端 4.0 SP1</span><span class="sxs-lookup"><span data-stu-id="10f61-183">AGPM Client 4.0 SP1</span></span>**

**<span data-ttu-id="10f61-184">AGPM 服务器 4.0 SP1</span><span class="sxs-lookup"><span data-stu-id="10f61-184">AGPM Server 4.0 SP1</span></span>**

**<span data-ttu-id="10f61-185">操作系统</span><span class="sxs-lookup"><span data-stu-id="10f61-185">Operating System</span></span>**

**<span data-ttu-id="10f61-186">.NET</span><span class="sxs-lookup"><span data-stu-id="10f61-186">.NET</span></span>**

**<span data-ttu-id="10f61-187">RSAT</span><span class="sxs-lookup"><span data-stu-id="10f61-187">RSAT</span></span>**

**<span data-ttu-id="10f61-188">.NET</span><span class="sxs-lookup"><span data-stu-id="10f61-188">.NET</span></span>**

**<span data-ttu-id="10f61-189">RSAT</span><span class="sxs-lookup"><span data-stu-id="10f61-189">RSAT</span></span>**

**<span data-ttu-id="10f61-190">Windows 8</span><span class="sxs-lookup"><span data-stu-id="10f61-190">Windows 8</span></span>**

<span data-ttu-id="10f61-191">如果未启用或安装 .NET 3.5，安装程序将阻止安装。</span><span class="sxs-lookup"><span data-stu-id="10f61-191">If .NET 3.5 is not enabled or installed, the installer blocks the installation.</span></span>

<span data-ttu-id="10f61-192">如果系统上未启用或安装 GPMC，安装程序将阻止安装。</span><span class="sxs-lookup"><span data-stu-id="10f61-192">If GPMC is not enabled or installed on the system, the installer blocks the installation.</span></span>

<span data-ttu-id="10f61-193">如果未启用或安装 .NET 3.5，安装程序将阻止安装。</span><span class="sxs-lookup"><span data-stu-id="10f61-193">If .NET 3.5 is not enabled or installed, the installer blocks the installation.</span></span>

<span data-ttu-id="10f61-194">如果系统上未启用或安装 GPMC，安装程序将阻止安装。</span><span class="sxs-lookup"><span data-stu-id="10f61-194">If GPMC is not enabled or installed on the system, the installer blocks the installation.</span></span>

**<span data-ttu-id="10f61-195">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="10f61-195">Windows Server 2012</span></span>**

<span data-ttu-id="10f61-196">如果未启用或安装 .NET 3.5，安装程序将阻止安装。</span><span class="sxs-lookup"><span data-stu-id="10f61-196">If .NET 3.5 is not enabled or installed, the installer blocks the installation.</span></span>

<span data-ttu-id="10f61-197">如果未启用 GPMC，安装程序将在安装期间启用它。</span><span class="sxs-lookup"><span data-stu-id="10f61-197">If GPMC is not enabled, the installer enables it during the installation.</span></span>

<span data-ttu-id="10f61-198">如果未启用或安装 .NET 3.5，安装程序将阻止安装。</span><span class="sxs-lookup"><span data-stu-id="10f61-198">If .NET 3.5 is not enabled or installed, the installer blocks the installation.</span></span>

<span data-ttu-id="10f61-199">如果未启用 GPMC，安装程序将在安装期间启用它。</span><span class="sxs-lookup"><span data-stu-id="10f61-199">If GPMC is not enabled, the installer enables it during the installation.</span></span>

 

## <span data-ttu-id="10f61-200">相关主题</span><span class="sxs-lookup"><span data-stu-id="10f61-200">Related topics</span></span>


[<span data-ttu-id="10f61-201">高级组策略管理</span><span class="sxs-lookup"><span data-stu-id="10f61-201">Advanced Group Policy Management</span></span>](index.md)

[<span data-ttu-id="10f61-202">Microsoft 高级组策略管理 4.0 SP1 发行说明</span><span class="sxs-lookup"><span data-stu-id="10f61-202">Release Notes for Microsoft Advanced Group Policy Management 4.0 SP1</span></span>](release-notes-for-microsoft-advanced-group-policy-management-40-sp1.md)

 

 





