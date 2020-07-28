---
title: AGPM 4.0 SP3 中的新增功能
description: AGPM 4.0 SP3 中的新增功能
author: dansimp
ms.assetid: df495d55-9fbf-4f7e-a7af-3905f4f8790e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 09/27/2016
ms.openlocfilehash: 44e7dc6c5de75ae3a5e5def638974bae20ad2a1e
ms.sourcegitcommit: 594b6e431af98562e0b806e224d2c5c7e07d2c77
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/27/2020
ms.locfileid: "10895762"
---
# <span data-ttu-id="a6c6e-103">AGPM 4.0 SP3 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="a6c6e-103">What's New in AGPM 4.0 SP3</span></span>


<span data-ttu-id="a6c6e-104">此内容介绍 Microsoft 高级组策略管理（AGPM）4.0 服务 Pack3 （SP3）的增强功能和受支持的配置。</span><span class="sxs-lookup"><span data-stu-id="a6c6e-104">This content describes enhancements and supported configurations for Microsoft Advanced Group Policy Management (AGPM)4.0 Service Pack3 (SP3).</span></span> <span data-ttu-id="a6c6e-105">如果此内容和其他 AGPM 文档之间存在差异，请考虑此内容的权威，并假定它取代了其他文档。</span><span class="sxs-lookup"><span data-stu-id="a6c6e-105">If there is a difference between this content and other AGPM documentation, consider this content authoritative and assume that it supersedes the other documentation.</span></span>

## <a href="" id="what-s-new"></a><span data-ttu-id="a6c6e-106">新增内容</span><span class="sxs-lookup"><span data-stu-id="a6c6e-106">What’s new</span></span>


<span data-ttu-id="a6c6e-107">AGPM 4.0 SP3 支持以下功能和功能。</span><span class="sxs-lookup"><span data-stu-id="a6c6e-107">AGPM4.0 SP3 supports the following features and functionality.</span></span>

### <span data-ttu-id="a6c6e-108">对 Windows10 的支持</span><span class="sxs-lookup"><span data-stu-id="a6c6e-108">Support for Windows10</span></span>

<span data-ttu-id="a6c6e-109">AGPM 4.0 SP3 添加了对 Windows10 和 Windows Server 2016 操作系统的支持。</span><span class="sxs-lookup"><span data-stu-id="a6c6e-109">AGPM4.0 SP3 adds support for the Windows10 and Windows Server 2016 operating systems.</span></span>

### <span data-ttu-id="a6c6e-110">对 PowerShell 的支持</span><span class="sxs-lookup"><span data-stu-id="a6c6e-110">Support for PowerShell</span></span>

<span data-ttu-id="a6c6e-111">AGPM 4.0 SP3 添加了对 PowerShell cmdlet 的支持。</span><span class="sxs-lookup"><span data-stu-id="a6c6e-111">AGPM4.0 SP3 adds support for PowerShell cmdlets.</span></span> <span data-ttu-id="a6c6e-112">有关 AGPM 4.0 SP3 中可用的 cmdlet （包括说明和语法）的列表，请参阅[Microsoft 桌面优化包自动化与 Windows PowerShell](https://docs.microsoft.com/powershell/mdop/get-started?view=win-mdop2-ps)。</span><span class="sxs-lookup"><span data-stu-id="a6c6e-112">For a list of the cmdlets available in AGPM4.0 SP3, including descriptions and syntax, see [Microsoft Desktop Optimization Pack Automation with Windows PowerShell](https://docs.microsoft.com/powershell/mdop/get-started?view=win-mdop2-ps).</span></span>

### <span data-ttu-id="a6c6e-113">客户反馈和修补程序汇总</span><span class="sxs-lookup"><span data-stu-id="a6c6e-113">Customer feedback and hotfix rollup</span></span>

<span data-ttu-id="a6c6e-114">AGPM 4.0 SP3 包括所有修复的汇总，包括 Microsoft 高级组策略管理 4.0 SP2 以及有关自 AGPM 4.0 SP2 以来发现的问题的任何修补程序。</span><span class="sxs-lookup"><span data-stu-id="a6c6e-114">AGPM 4.0 SP3 includes a rollup of all fixes up to and including Microsoft Advanced Group Policy Management 4.0 SP2 and any fixes for issues found since AGPM 4.0 SP2.</span></span>

### <span data-ttu-id="a6c6e-115">无需重新输入配置参数即可升级到 AGPM 4.0 SP3 的功能</span><span class="sxs-lookup"><span data-stu-id="a6c6e-115">Ability to upgrade to AGPM4.0 SP3 without re-entering configuration parameters</span></span>

<span data-ttu-id="a6c6e-116">你可以将 AGPM 客户端或 AGPM 服务器升级到 AGPM 4.0 SP3，而不提示仅从 AGPM 4.0 和更高版本重新输入配置参数（称为 "智能升级"），如下表所示。</span><span class="sxs-lookup"><span data-stu-id="a6c6e-116">You can upgrade the AGPM Client or AGPM Server to AGPM4.0 SP3 without being prompted to re-enter configuration parameters (called the Smart Upgrade) only from AGPM4.0 and later, as shown in the following table.</span></span> <span data-ttu-id="a6c6e-117">如果要从其他版本的 AGPM 升级到 AGPM 4.0 SP3 （如表中所示），则必须使用 "经典升级"，这需要重新输入配置参数。</span><span class="sxs-lookup"><span data-stu-id="a6c6e-117">If you are upgrading to AGPM4.0 SP3 from other versions of AGPM, as shown in the table, you must use the Classic Upgrade, which requires you to re-enter the configuration parameters.</span></span> <span data-ttu-id="a6c6e-118">由于 AGPM 的每个版本都与特定操作系统相关联，请参阅[选择要安装的 Agpm 版本](https://go.microsoft.com/fwlink/?LinkId=254350)，并确保在升级 AGPM 之前升级操作系统。</span><span class="sxs-lookup"><span data-stu-id="a6c6e-118">Because each version of AGPM is associated with a particular operating system, see [Choosing Which Version of AGPM to Install](https://go.microsoft.com/fwlink/?LinkId=254350) and make sure that you upgrade your operating system as appropriate before you upgrade AGPM.</span></span>

**<span data-ttu-id="a6c6e-119">AGPM 4.0 SP3 支持的升级</span><span class="sxs-lookup"><span data-stu-id="a6c6e-119">AGPM 4.0 SP3 supported upgrades</span></span>**

<table style="width:100%;">
<colgroup>
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="a6c6e-120">可升级的 AGPM 版本</span><span class="sxs-lookup"><span data-stu-id="a6c6e-120">AGPM version from which you can upgrade</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="a6c6e-121">2.5</span><span class="sxs-lookup"><span data-stu-id="a6c6e-121">2.5</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="a6c6e-122">3.0</span><span class="sxs-lookup"><span data-stu-id="a6c6e-122">3.0</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="a6c6e-123">4.0</span><span class="sxs-lookup"><span data-stu-id="a6c6e-123">4.0</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="a6c6e-124">4.0 SP1</span><span class="sxs-lookup"><span data-stu-id="a6c6e-124">4.0 SP1</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="a6c6e-125">4.0 SP2</span><span class="sxs-lookup"><span data-stu-id="a6c6e-125">4.0 SP2</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="a6c6e-126">4.0 SP3</span><span class="sxs-lookup"><span data-stu-id="a6c6e-126">4.0 SP3</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a6c6e-127">2.5</span><span class="sxs-lookup"><span data-stu-id="a6c6e-127">2.5</span></span></p></td>
<td align="left"><p><span data-ttu-id="a6c6e-128">不适用</span><span class="sxs-lookup"><span data-stu-id="a6c6e-128">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="a6c6e-129">经典升级</span><span class="sxs-lookup"><span data-stu-id="a6c6e-129">Classic Upgrade</span></span></p></td>
<td align="left"><p><span data-ttu-id="a6c6e-130">经典升级</span><span class="sxs-lookup"><span data-stu-id="a6c6e-130">Classic Upgrade</span></span></p></td>
<td align="left"><p><span data-ttu-id="a6c6e-131">安装被阻止</span><span class="sxs-lookup"><span data-stu-id="a6c6e-131">Installation is blocked</span></span></p></td>
<td align="left"><p><span data-ttu-id="a6c6e-132">安装被阻止</span><span class="sxs-lookup"><span data-stu-id="a6c6e-132">Installation is blocked</span></span></p></td>
<td align="left"><p><span data-ttu-id="a6c6e-133">安装被阻止</span><span class="sxs-lookup"><span data-stu-id="a6c6e-133">Installation is blocked</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a6c6e-134">3.0</span><span class="sxs-lookup"><span data-stu-id="a6c6e-134">3.0</span></span></p></td>
<td align="left"><p><span data-ttu-id="a6c6e-135">不适用</span><span class="sxs-lookup"><span data-stu-id="a6c6e-135">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="a6c6e-136">不适用</span><span class="sxs-lookup"><span data-stu-id="a6c6e-136">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="a6c6e-137">经典升级</span><span class="sxs-lookup"><span data-stu-id="a6c6e-137">Classic Upgrade</span></span></p></td>
<td align="left"><p><span data-ttu-id="a6c6e-138">安装被阻止</span><span class="sxs-lookup"><span data-stu-id="a6c6e-138">Installation is blocked</span></span></p></td>
<td align="left"><p><span data-ttu-id="a6c6e-139">安装被阻止</span><span class="sxs-lookup"><span data-stu-id="a6c6e-139">Installation is blocked</span></span></p></td>
<td align="left"><p><span data-ttu-id="a6c6e-140">安装被阻止</span><span class="sxs-lookup"><span data-stu-id="a6c6e-140">Installation is blocked</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a6c6e-141">4.0</span><span class="sxs-lookup"><span data-stu-id="a6c6e-141">4.0</span></span></p></td>
<td align="left"><p><span data-ttu-id="a6c6e-142">不适用</span><span class="sxs-lookup"><span data-stu-id="a6c6e-142">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="a6c6e-143">不适用</span><span class="sxs-lookup"><span data-stu-id="a6c6e-143">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="a6c6e-144">不适用</span><span class="sxs-lookup"><span data-stu-id="a6c6e-144">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="a6c6e-145">智能升级</span><span class="sxs-lookup"><span data-stu-id="a6c6e-145">Smart Upgrade</span></span></p></td>
<td align="left"><p><span data-ttu-id="a6c6e-146">智能升级</span><span class="sxs-lookup"><span data-stu-id="a6c6e-146">Smart Upgrade</span></span></p></td>
<td align="left"><p><span data-ttu-id="a6c6e-147">智能升级</span><span class="sxs-lookup"><span data-stu-id="a6c6e-147">Smart Upgrade</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a6c6e-148">4.0 SP1</span><span class="sxs-lookup"><span data-stu-id="a6c6e-148">4.0 SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="a6c6e-149">不适用</span><span class="sxs-lookup"><span data-stu-id="a6c6e-149">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="a6c6e-150">不适用</span><span class="sxs-lookup"><span data-stu-id="a6c6e-150">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="a6c6e-151">不适用</span><span class="sxs-lookup"><span data-stu-id="a6c6e-151">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="a6c6e-152">不适用</span><span class="sxs-lookup"><span data-stu-id="a6c6e-152">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="a6c6e-153">智能升级</span><span class="sxs-lookup"><span data-stu-id="a6c6e-153">Smart Upgrade</span></span></p></td>
<td align="left"><p><span data-ttu-id="a6c6e-154">智能升级</span><span class="sxs-lookup"><span data-stu-id="a6c6e-154">Smart Upgrade</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a6c6e-155">4.0 SP2</span><span class="sxs-lookup"><span data-stu-id="a6c6e-155">4.0 SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="a6c6e-156">不适用</span><span class="sxs-lookup"><span data-stu-id="a6c6e-156">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="a6c6e-157">不适用</span><span class="sxs-lookup"><span data-stu-id="a6c6e-157">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="a6c6e-158">不适用</span><span class="sxs-lookup"><span data-stu-id="a6c6e-158">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="a6c6e-159">不适用</span><span class="sxs-lookup"><span data-stu-id="a6c6e-159">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="a6c6e-160">不适用</span><span class="sxs-lookup"><span data-stu-id="a6c6e-160">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="a6c6e-161">智能升级</span><span class="sxs-lookup"><span data-stu-id="a6c6e-161">Smart Upgrade</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="a6c6e-162">支持的配置</span><span class="sxs-lookup"><span data-stu-id="a6c6e-162">Supported configurations</span></span>


<span data-ttu-id="a6c6e-163">AGPM 4.0 SP3 支持下表中的配置。</span><span class="sxs-lookup"><span data-stu-id="a6c6e-163">AGPM4.0 SP3 supports the configurations in the following table.</span></span> <span data-ttu-id="a6c6e-164">尽管 AGPM 支持混合配置，但我们强烈建议你在相同的操作系统行上运行 AGPM 客户端和 AGPM 服务器，例如，Windows10 Windows Server 2016、windows 8.1 和 Windows Server 2012 R2 等。</span><span class="sxs-lookup"><span data-stu-id="a6c6e-164">Although AGPM supports mixed configurations, we strongly recommend that you run the AGPM Client and AGPM Server on the same operating system line—for example, Windows10 with Windows Server 2016, Windows 8.1 with Windows Server 2012 R2, and so on.</span></span>

**<span data-ttu-id="a6c6e-165">AGPM 4.0 SP3 支持的操作系统和策略设置</span><span class="sxs-lookup"><span data-stu-id="a6c6e-165">AGPM4.0 SP3 supported operating systems and policy settings</span></span>**

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong><span data-ttu-id="a6c6e-166">AGPM 服务器支持的配置</span><span class="sxs-lookup"><span data-stu-id="a6c6e-166">Supported configurations for the AGPM Server</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="a6c6e-167">AGPM 客户端支持的配置</span><span class="sxs-lookup"><span data-stu-id="a6c6e-167">Supported configurations for the AGPM Client</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="a6c6e-168">AGPM 支持</span><span class="sxs-lookup"><span data-stu-id="a6c6e-168">AGPM Support</span></span></strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a6c6e-169">Windows Server 2019 或 Windows 10</span><span class="sxs-lookup"><span data-stu-id="a6c6e-169">Windows Server 2019 or Windows 10</span></span></p></td>
<td align="left"><p><span data-ttu-id="a6c6e-170">Windows10</span><span class="sxs-lookup"><span data-stu-id="a6c6e-170">Windows 10</span></span></p></td>
<td align="left"><p><span data-ttu-id="a6c6e-171">支持</span><span class="sxs-lookup"><span data-stu-id="a6c6e-171">Supported</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a6c6e-172">Windows Server 2016 或 Windows 10</span><span class="sxs-lookup"><span data-stu-id="a6c6e-172">Windows Server 2016 or Windows 10</span></span></p></td>
<td align="left"><p><span data-ttu-id="a6c6e-173">Windows10</span><span class="sxs-lookup"><span data-stu-id="a6c6e-173">Windows 10</span></span></p></td>
<td align="left"><p><span data-ttu-id="a6c6e-174">支持</span><span class="sxs-lookup"><span data-stu-id="a6c6e-174">Supported</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a6c6e-175">Windows Server2012 R2 或 Windows 8。1</span><span class="sxs-lookup"><span data-stu-id="a6c6e-175">Windows Server2012 R2 or Windows8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="a6c6e-176">Windows Server2012 R2 或 Windows 8。1</span><span class="sxs-lookup"><span data-stu-id="a6c6e-176">Windows Server2012 R2 or Windows8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="a6c6e-177">支持</span><span class="sxs-lookup"><span data-stu-id="a6c6e-177">Supported</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a6c6e-178">Windows Server2012 R2、Windows Server 2012 或 Windows 8。1</span><span class="sxs-lookup"><span data-stu-id="a6c6e-178">Windows Server2012 R2, Windows Server 2012, or Windows8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="a6c6e-179">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="a6c6e-179">Windows Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="a6c6e-180">受支持，但不能编辑仅存在于 Windows 8.1 中的策略设置或首选项</span><span class="sxs-lookup"><span data-stu-id="a6c6e-180">Supported, but cannot edit policy settings or preference items that exist only in Windows8.1</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a6c6e-181">Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="a6c6e-181">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="a6c6e-182">Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="a6c6e-182">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="a6c6e-183">受支持，但不能编辑仅存在于 Windows 8.1 中的策略设置或首选项</span><span class="sxs-lookup"><span data-stu-id="a6c6e-183">Supported, but cannot edit policy settings or preference items that exist only in Windows8.1</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a6c6e-184">Windows Server 2012、Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="a6c6e-184">Windows Server 2012, Windows Server2008R2, or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="a6c6e-185">Windows Server2008 或 WindowsVista Service Pack 1 （SP1）</span><span class="sxs-lookup"><span data-stu-id="a6c6e-185">Windows Server2008 or WindowsVista with Service Pack 1 (SP1)</span></span></p></td>
<td align="left"><p><span data-ttu-id="a6c6e-186">受支持，但不能编辑仅存在于 Windows Server2012 R2、Windows Server 2012、Windows Server2008R2、Windows 8.1 或 Windows7 中的策略设置或首选项</span><span class="sxs-lookup"><span data-stu-id="a6c6e-186">Supported, but cannot edit policy settings or preference items that exist only in Windows Server2012 R2, Windows Server 2012, Windows Server2008R2, Windows8.1, or Windows7</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a6c6e-187">Windows Server2008 或 Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="a6c6e-187">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="a6c6e-188">Windows Server 2012、Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="a6c6e-188">Windows Server 2012, Windows Server2008R2, or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="a6c6e-189">不支持</span><span class="sxs-lookup"><span data-stu-id="a6c6e-189">Not supported</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a6c6e-190">Windows Server2008 或 Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="a6c6e-190">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="a6c6e-191">Windows Server2008 或 Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="a6c6e-191">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="a6c6e-192">受支持，但无法报告或编辑仅存在于 Windows Server2012 R2、Windows Server 2012、Windows Server2008R2、Windows 8.1 或 Windows7 中的策略设置或首选项</span><span class="sxs-lookup"><span data-stu-id="a6c6e-192">Supported, but cannot report or edit policy settings or preference items that exist only in Windows Server2012 R2, Windows Server 2012, Windows Server2008R2, Windows8.1, or Windows7</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="a6c6e-193">安装 AGPM 4.0 SP3 的先决条件</span><span class="sxs-lookup"><span data-stu-id="a6c6e-193">Prerequisites for installing AGPM4.0 SP3</span></span>

<span data-ttu-id="a6c6e-194">下表介绍了当缺少远程服务器管理工具中的 .NET Framework 4.5.1、PowerShell 3.0 或 GPMC 时，AGPM 4.0 SP3 客户端和服务器安装程序的行为。</span><span class="sxs-lookup"><span data-stu-id="a6c6e-194">The following table describes the behavior of AGPM4.0 SP3 Client and Server installers when the .NET Framework4.5.1, PowerShell 3.0, or the GPMC in the Remote Server Administration Tools is missing.</span></span>

| <span data-ttu-id="a6c6e-195">AGPM 客户端</span><span class="sxs-lookup"><span data-stu-id="a6c6e-195">AGPM Client</span></span>            |                                                                                                 |                                                                            | <span data-ttu-id="a6c6e-196">AGPM 服务器</span><span class="sxs-lookup"><span data-stu-id="a6c6e-196">AGPM Server</span></span>                                                                     |                                                                                                 |                                                                                 |
|------------------------|-------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------|---------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------|
| <span data-ttu-id="a6c6e-197">操作系统</span><span class="sxs-lookup"><span data-stu-id="a6c6e-197">Operating system</span></span>       | <span data-ttu-id="a6c6e-198">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="a6c6e-198">.NET Framework</span></span>                                                                                  | <span data-ttu-id="a6c6e-199">PowerShell</span><span class="sxs-lookup"><span data-stu-id="a6c6e-199">PowerShell</span></span>                                                                 | <span data-ttu-id="a6c6e-200">远程服务器管理工具</span><span class="sxs-lookup"><span data-stu-id="a6c6e-200">Remote Server Administration Tools</span></span>                                              | <span data-ttu-id="a6c6e-201">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="a6c6e-201">.NET Framework</span></span>                                                                                  | <span data-ttu-id="a6c6e-202">远程服务器管理工具</span><span class="sxs-lookup"><span data-stu-id="a6c6e-202">Remote Server Administration Tools</span></span>                                              |
| <span data-ttu-id="a6c6e-203">Windows 10</span><span class="sxs-lookup"><span data-stu-id="a6c6e-203">Windows 10</span></span>             | <span data-ttu-id="a6c6e-204">如果未启用或安装 .NET Framework 4.5.1，安装程序将阻止安装。</span><span class="sxs-lookup"><span data-stu-id="a6c6e-204">If the .NET Framework 4.5.1 is not enabled or installed, the installer blocks the installation.</span></span> | <span data-ttu-id="a6c6e-205">如果未安装 Powershell 3.0，安装程序将阻止安装。</span><span class="sxs-lookup"><span data-stu-id="a6c6e-205">If Powershell 3.0 is not installed, the installer blocks the installation.</span></span> | <span data-ttu-id="a6c6e-206">如果 GPMC 未启用或未安装，安装程序将阻止安装。</span><span class="sxs-lookup"><span data-stu-id="a6c6e-206">If the GPMC is not enabled or installed, the installer blocks the installation.</span></span> | <span data-ttu-id="a6c6e-207">如果未启用或安装 .NET Framework 4.5.1，安装程序将阻止安装。</span><span class="sxs-lookup"><span data-stu-id="a6c6e-207">If the .NET Framework 4.5.1 is not enabled or installed, the installer blocks the installation.</span></span> | <span data-ttu-id="a6c6e-208">如果 GPMC 未启用或未安装，安装程序将阻止安装。</span><span class="sxs-lookup"><span data-stu-id="a6c6e-208">If the GPMC is not enabled or installed, the installer blocks the installation.</span></span> |
| <span data-ttu-id="a6c6e-209">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="a6c6e-209">Windows 8.1</span></span>            | <span data-ttu-id="a6c6e-210">如果未启用或安装 .NET Framework 4.5.1，安装程序将阻止安装。</span><span class="sxs-lookup"><span data-stu-id="a6c6e-210">If the .NET Framework 4.5.1 is not enabled or installed, the installer blocks the installation.</span></span> | <span data-ttu-id="a6c6e-211">如果未安装 Powershell 3.0，安装程序将阻止安装。</span><span class="sxs-lookup"><span data-stu-id="a6c6e-211">If Powershell 3.0 is not installed, the installer blocks the installation.</span></span> | <span data-ttu-id="a6c6e-212">如果 GPMC 未启用或未安装，安装程序将阻止安装。</span><span class="sxs-lookup"><span data-stu-id="a6c6e-212">If the GPMC is not enabled or installed, the installer blocks the installation.</span></span> | <span data-ttu-id="a6c6e-213">如果未启用或安装 .NET Framework 4.5.1，安装程序将阻止安装。</span><span class="sxs-lookup"><span data-stu-id="a6c6e-213">If the .NET Framework 4.5.1 is not enabled or installed, the installer blocks the installation.</span></span> | <span data-ttu-id="a6c6e-214">如果 GPMC 未启用或未安装，安装程序将阻止安装。</span><span class="sxs-lookup"><span data-stu-id="a6c6e-214">If the GPMC is not enabled or installed, the installer blocks the installation.</span></span> |
| <span data-ttu-id="a6c6e-215">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="a6c6e-215">Windows Server 2012 R2</span></span> | <span data-ttu-id="a6c6e-216">如果未启用或安装 .NET Framework 4.5.1，安装程序将阻止安装。</span><span class="sxs-lookup"><span data-stu-id="a6c6e-216">If the .NET Framework 4.5.1 is not enabled or installed, the installer blocks the installation.</span></span> | <span data-ttu-id="a6c6e-217">如果未安装 Powershell 3.0，安装程序将阻止安装。</span><span class="sxs-lookup"><span data-stu-id="a6c6e-217">If Powershell 3.0 is not installed, the installer blocks the installation.</span></span> | <span data-ttu-id="a6c6e-218">如果未启用 GPMC，安装程序将在安装期间启用它。</span><span class="sxs-lookup"><span data-stu-id="a6c6e-218">If the GPMC is not enabled, the installer enables it during the installation.</span></span>   | <span data-ttu-id="a6c6e-219">如果未启用或安装 .NET Framework 4.5.1，安装程序将阻止安装。</span><span class="sxs-lookup"><span data-stu-id="a6c6e-219">If the .NET Framework 4.5.1 is not enabled or installed, the installer blocks the installation.</span></span> | <span data-ttu-id="a6c6e-220">如果未启用 GPMC，安装程序将在安装期间启用它。</span><span class="sxs-lookup"><span data-stu-id="a6c6e-220">If the GPMC is not enabled, the installer enables it during the installation.</span></span>   |

 

## <span data-ttu-id="a6c6e-221">如何获取 MDOP 技术</span><span class="sxs-lookup"><span data-stu-id="a6c6e-221">How to Get MDOP Technologies</span></span>


<span data-ttu-id="a6c6e-222">AGPM 4.0 SP3 是 Microsoft 桌面优化包（MDOP）的一部分，自 MDOP 2015 起。</span><span class="sxs-lookup"><span data-stu-id="a6c6e-222">AGPM 4.0 SP3 is a part of the Microsoft Desktop Optimization Pack (MDOP) since MDOP 2015.</span></span> <span data-ttu-id="a6c6e-223">MDOP 是 Microsoft 软件保障的一部分。</span><span class="sxs-lookup"><span data-stu-id="a6c6e-223">MDOP is part of Microsoft Software Assurance.</span></span> <span data-ttu-id="a6c6e-224">有关 Microsoft 软件保证和获取 MDOP 的详细信息，请参阅[如何获取 mdop](https://go.microsoft.com/fwlink/?LinkId=322049) （ https://go.microsoft.com/fwlink/?LinkId=322049) 。</span><span class="sxs-lookup"><span data-stu-id="a6c6e-224">For more information about Microsoft Software Assurance and acquiring MDOP, see [How Do I Get MDOP](https://go.microsoft.com/fwlink/?LinkId=322049) (https://go.microsoft.com/fwlink/?LinkId=322049).</span></span>

## <span data-ttu-id="a6c6e-225">相关主题</span><span class="sxs-lookup"><span data-stu-id="a6c6e-225">Related topics</span></span>


[<span data-ttu-id="a6c6e-226">高级组策略管理</span><span class="sxs-lookup"><span data-stu-id="a6c6e-226">Advanced Group Policy Management</span></span>](index.md)

[<span data-ttu-id="a6c6e-227">Microsoft 高级组策略管理 4.0 SP3 发行说明</span><span class="sxs-lookup"><span data-stu-id="a6c6e-227">Release Notes for Microsoft Advanced Group Policy Management 4.0 SP3</span></span>](release-notes-for-microsoft-advanced-group-policy-management-40-sp3.md)

[<span data-ttu-id="a6c6e-228">选择要安装的 AGPM 版本</span><span class="sxs-lookup"><span data-stu-id="a6c6e-228">Choosing Which Version of AGPM to Install</span></span>](choosing-which-version-of-agpm-to-install.md)

 

 





