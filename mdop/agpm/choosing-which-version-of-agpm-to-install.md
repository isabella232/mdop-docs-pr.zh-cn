---
title: 选择要安装的 AGPM 版本
description: 选择要安装的 AGPM 版本
author: dansimp
ms.assetid: 31357d2a-bc23-4e15-93f4-0beda8ab7a7b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 04/05/2017
ms.openlocfilehash: f8a69fb323d9f47c5b906ac3abc6ec59376ee6f7
ms.sourcegitcommit: 0a7dee11289780336d9c24ebbf27c5c1ffee441c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/04/2020
ms.locfileid: "10905599"
---
# <span data-ttu-id="04281-103">选择要安装的 AGPM 版本</span><span class="sxs-lookup"><span data-stu-id="04281-103">Choosing Which Version of AGPM to Install</span></span>


<span data-ttu-id="04281-104">MicrosoftAdvanced 组策略管理的每个版本 (AGPM) 支持特定版本的 Windows 操作系统。</span><span class="sxs-lookup"><span data-stu-id="04281-104">Each release of MicrosoftAdvanced Group Policy Management (AGPM) supports specific versions of the Windows operating system.</span></span> <span data-ttu-id="04281-105">我们强烈建议你在同一操作系统行上运行 AGPM 客户端和 AGPM 服务器。</span><span class="sxs-lookup"><span data-stu-id="04281-105">We strongly recommend that you run the AGPM Client and AGPM Server on the same line of operating systems.</span></span> <span data-ttu-id="04281-106">例如，windows 10 适用于 windows Server 2016、windows 8.1 和 Windows Server2012 R2 等。</span><span class="sxs-lookup"><span data-stu-id="04281-106">For example, Windows 10 with Windows Server 2016, Windows8.1 with Windows Server2012 R2, and so on.</span></span>

<span data-ttu-id="04281-107">我们建议你在域中的最新版本的操作系统上安装 AGPM 服务器。</span><span class="sxs-lookup"><span data-stu-id="04281-107">We recommend that you install the AGPM Server on the most recent version of the operating system in the domain.</span></span> <span data-ttu-id="04281-108">AGPM 使用组策略管理控制台 (GPMC) 备份和还原 Gpo)  (的组策略对象。</span><span class="sxs-lookup"><span data-stu-id="04281-108">AGPM uses the Group Policy Management Console (GPMC) to back up and restore Group Policy Objects (GPOs).</span></span> <span data-ttu-id="04281-109">由于较新版本的 GPMC 提供的其他策略设置在早期版本中不可用，因此你可以使用最新版本的操作系统管理更多策略设置。</span><span class="sxs-lookup"><span data-stu-id="04281-109">Because newer versions of the GPMC provide additional policy settings that are not available in earlier versions, you can manage more policy settings by using the most recent version of the operating system.</span></span>

<span data-ttu-id="04281-110">所有版本的 AGPM 都只能管理在同一版本或早期版本的运行 AGPM 的操作系统中引入的策略设置。</span><span class="sxs-lookup"><span data-stu-id="04281-110">All versions of AGPM can manage only the policy settings that were introduced in the same version or an earlier version of the operating system on which AGPM is running.</span></span> <span data-ttu-id="04281-111">例如，如果在 Windows Server 2012 上安装了 AGPM 4.0 SP2，则可以管理 Windows Server 2012 或更早版本中引入的策略设置，但不能管理稍后在 Windows 8.1 或 Windows Server2012 R2 中引入的策略设置。</span><span class="sxs-lookup"><span data-stu-id="04281-111">For example, if you install AGPM4.0 SP2 on Windows Server 2012, you can manage policy settings that were introduced in Windows Server 2012 or earlier, but you cannot manage policy settings that were introduced later, in Windows8.1 or Windows Server2012 R2.</span></span>

<span data-ttu-id="04281-112">如果你的 AGPM 服务器上的 GPMC 版本比管理员用于管理组策略的计算机上的版本旧，则 AGPM 服务器将无法存储在较早版本的 GPMC 中不可用的任何策略设置。</span><span class="sxs-lookup"><span data-stu-id="04281-112">If the version of the GPMC on your AGPM Server is older than the version on the computers that administrators use to manage Group Policy, the AGPM Server will be unable to store any policy settings that are not available in the older version of the GPMC.</span></span> <span data-ttu-id="04281-113">有关 Windows 中包含的组策略设置的电子表格，请参阅[适用于 Windows 和 Windows Server 的组策略设置参考](https://go.microsoft.com/fwlink/p/?LinkId=613627)。</span><span class="sxs-lookup"><span data-stu-id="04281-113">For a spreadsheet of Group Policy settings included in Windows, see [Group Policy Settings Reference for Windows and Windows Server](https://go.microsoft.com/fwlink/p/?LinkId=613627).</span></span>

## <span data-ttu-id="04281-114">AGPM 4.0 SP3</span><span class="sxs-lookup"><span data-stu-id="04281-114">AGPM4.0 SP3</span></span>


<span data-ttu-id="04281-115">如果使用运行 Windows 10 的计算机管理 Gpo，则必须使用 AGPM 4.0 SP3。</span><span class="sxs-lookup"><span data-stu-id="04281-115">If you are using computers that are running Windows 10 to manage GPOs, you must use AGPM 4.0 SP3.</span></span> <span data-ttu-id="04281-116">无法在运行 Windows 10 操作系统的计算机上安装早期版本的 AGPM。</span><span class="sxs-lookup"><span data-stu-id="04281-116">You cannot install earlier versions of AGPM on computers that are running the Windows 10 operating system.</span></span>

<span data-ttu-id="04281-117">表1列出了可在其上安装 AGPM 4.0 SP3 的操作系统，以及可使用 AGPM 4.0 SP3 管理的策略设置。</span><span class="sxs-lookup"><span data-stu-id="04281-117">Table 1 lists the operating systems on which you can install AGPM4.0 SP3, and the policy settings that you can manage by using AGPM4.0 SP3.</span></span>

**<span data-ttu-id="04281-118">表1： AGPM 4.0 SP3 支持的操作系统和策略设置</span><span class="sxs-lookup"><span data-stu-id="04281-118">Table 1: AGPM 4.0 SP3 supported operating systems and policy settings</span></span>**

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong><span data-ttu-id="04281-119">AGPM 服务器支持的配置</span><span class="sxs-lookup"><span data-stu-id="04281-119">Supported configurations for the AGPM Server</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="04281-120">AGPM 客户端支持的配置</span><span class="sxs-lookup"><span data-stu-id="04281-120">Supported configurations for the AGPM Client</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="04281-121">AGPM 支持</span><span class="sxs-lookup"><span data-stu-id="04281-121">AGPM Support</span></span></strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="04281-122">Windows Server 2019 或 Windows 10</span><span class="sxs-lookup"><span data-stu-id="04281-122">Windows Server 2019 or Windows 10</span></span></p></td>
<td align="left"><p><span data-ttu-id="04281-123">Windows Server 2019 或 Windows 10</span><span class="sxs-lookup"><span data-stu-id="04281-123">Windows Server 2019 or Windows 10</span></span></p></td>
<td align="left"><p><span data-ttu-id="04281-124">支持</span><span class="sxs-lookup"><span data-stu-id="04281-124">Supported</span></span></p></td>
</tr>
 <tr class="even">
<td align="left"><p><span data-ttu-id="04281-125">Windows Server 2019 或 Windows 10</span><span class="sxs-lookup"><span data-stu-id="04281-125">Windows Server 2019 or Windows 10</span></span></p></td>
<td align="left"><p><span data-ttu-id="04281-126">Windows Server 2019 或 Windows 10</span><span class="sxs-lookup"><span data-stu-id="04281-126">Windows Server 2019 or Windows 10</span></span></p></td>
<td align="left"><p><span data-ttu-id="04281-127">支持</span><span class="sxs-lookup"><span data-stu-id="04281-127">Supported</span></span></p></td>
</tr>
<tr class="edd">
<td align="left"><p><span data-ttu-id="04281-128">Windows Server2012 R2</span><span class="sxs-lookup"><span data-stu-id="04281-128">Windows Server2012 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="04281-129">Windows 10</span><span class="sxs-lookup"><span data-stu-id="04281-129">Windows 10</span></span></p></td>
<td align="left"><p><span data-ttu-id="04281-130">通过在 KB 4015786 中概述的注意事项提供支持 <a href="https://support.microsoft.com/help/4015786/known-issues-managing-a-windows-10-group-policy-client-in-windows-serv" data-raw-source="[KB 4015786](https://support.microsoft.com/help/4015786/known-issues-managing-a-windows-10-group-policy-client-in-windows-serv)"></span><span class="sxs-lookup"><span data-stu-id="04281-130">Supported with the caveats outlined in <a href="https://support.microsoft.com/help/4015786/known-issues-managing-a-windows-10-group-policy-client-in-windows-serv" data-raw-source="[KB 4015786](https://support.microsoft.com/help/4015786/known-issues-managing-a-windows-10-group-policy-client-in-windows-serv)">KB 4015786</span></span></a>
</p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="04281-131">Windows Server2012 R2 或 Windows 8。1</span><span class="sxs-lookup"><span data-stu-id="04281-131">Windows Server2012 R2 or Windows8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="04281-132">Windows Server2012 R2 或 Windows 8。1</span><span class="sxs-lookup"><span data-stu-id="04281-132">Windows Server2012 R2 or Windows8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="04281-133">支持</span><span class="sxs-lookup"><span data-stu-id="04281-133">Supported</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="04281-134">Windows Server2012 R2、Windows Server 2012 或 Windows 8。1</span><span class="sxs-lookup"><span data-stu-id="04281-134">Windows Server2012 R2, Windows Server 2012, or Windows8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="04281-135">Windows Server 2012 或 Windows 8。1</span><span class="sxs-lookup"><span data-stu-id="04281-135">Windows Server 2012 or Windows 8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="04281-136">受支持，但不能编辑仅存在于 Windows 8.1 中的策略设置或首选项</span><span class="sxs-lookup"><span data-stu-id="04281-136">Supported, but cannot edit policy settings or preference items that exist only in Windows8.1</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="04281-137">Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="04281-137">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="04281-138">Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="04281-138">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="04281-139">受支持，但不能编辑仅存在于 Windows 8.1 中的策略设置或首选项</span><span class="sxs-lookup"><span data-stu-id="04281-139">Supported, but cannot edit policy settings or preference items that exist only in Windows8.1</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="04281-140">Windows Server 2012、Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="04281-140">Windows Server 2012, Windows Server2008R2, or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="04281-141">Windows Server2008 或 WindowsVista Service Pack 1 (SP1) </span><span class="sxs-lookup"><span data-stu-id="04281-141">Windows Server2008 or WindowsVista with Service Pack 1 (SP1)</span></span></p></td>
<td align="left"><p><span data-ttu-id="04281-142">受支持，但不能编辑仅存在于 Windows Server2012 R2、Windows Server 2012、Windows Server2008R2、Windows 8.1 或 Windows7 中的策略设置或首选项</span><span class="sxs-lookup"><span data-stu-id="04281-142">Supported, but cannot edit policy settings or preference items that exist only in Windows Server2012 R2, Windows Server 2012, Windows Server2008R2, Windows8.1, or Windows7</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="04281-143">Windows Server2008 或 Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="04281-143">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="04281-144">Windows Server 2012、Windows Server2008R2、Windows 8 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="04281-144">Windows Server 2012, Windows Server2008R2, Windows 8, or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="04281-145">不支持</span><span class="sxs-lookup"><span data-stu-id="04281-145">Not supported</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="04281-146">Windows Server2008 或 Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="04281-146">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="04281-147">Windows Server2008 或 Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="04281-147">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="04281-148">受支持，但无法报告或编辑仅存在于 Windows Server2012 R2、Windows Server 2012、Windows Server2008R2、Windows 8.1 或 Windows7 中的策略设置或首选项</span><span class="sxs-lookup"><span data-stu-id="04281-148">Supported, but cannot report or edit policy settings or preference items that exist only in Windows Server2012 R2, Windows Server 2012, Windows Server2008R2, Windows8.1, or Windows7</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="04281-149">AGPM 4.0 SP2</span><span class="sxs-lookup"><span data-stu-id="04281-149">AGPM4.0 SP2</span></span>


<span data-ttu-id="04281-150">如果你使用运行 Windows Server2012 R2 或 Windows 8.1 的计算机管理 Gpo，则必须使用 AGPM 4.0 SP2。</span><span class="sxs-lookup"><span data-stu-id="04281-150">If you are using computers that are running Windows Server2012 R2 or Windows8.1 to manage GPOs, you must use AGPM4.0 SP2.</span></span> <span data-ttu-id="04281-151">无法在运行这些操作系统的计算机上安装早期版本的 AGPM。</span><span class="sxs-lookup"><span data-stu-id="04281-151">You cannot install earlier versions of AGPM on computers that are running those operating systems.</span></span>

<span data-ttu-id="04281-152">表1列出了可在其上安装 AGPM 4.0 SP2 的操作系统，以及可使用 AGPM 4.0 SP2 管理的策略设置。</span><span class="sxs-lookup"><span data-stu-id="04281-152">Table 1 lists the operating systems on which you can install AGPM4.0 SP2, and the policy settings that you can manage by using AGPM4.0 SP2.</span></span>

**<span data-ttu-id="04281-153">表2： AGPM 4.0 SP2 支持的操作系统和策略设置</span><span class="sxs-lookup"><span data-stu-id="04281-153">Table 2: AGPM4.0 SP2 supported operating systems and policy settings</span></span>**

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong><span data-ttu-id="04281-154">AGPM 服务器支持的配置</span><span class="sxs-lookup"><span data-stu-id="04281-154">Supported configurations for the AGPM Server</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="04281-155">AGPM 客户端支持的配置</span><span class="sxs-lookup"><span data-stu-id="04281-155">Supported configurations for the AGPM Client</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="04281-156">AGPM 支持</span><span class="sxs-lookup"><span data-stu-id="04281-156">AGPM Support</span></span></strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="04281-157">Windows Server2012 R2 或 Windows 8。1</span><span class="sxs-lookup"><span data-stu-id="04281-157">Windows Server2012 R2 or Windows8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="04281-158">Windows Server2012 R2 或 Windows 8。1</span><span class="sxs-lookup"><span data-stu-id="04281-158">Windows Server2012 R2 or Windows8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="04281-159">支持</span><span class="sxs-lookup"><span data-stu-id="04281-159">Supported</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="04281-160">Windows Server2012 R2、Windows Server 2012 或 Windows 8。1</span><span class="sxs-lookup"><span data-stu-id="04281-160">Windows Server2012 R2, Windows Server 2012, or Windows8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="04281-161">Windows Server 2012 或 Windows 8。1</span><span class="sxs-lookup"><span data-stu-id="04281-161">Windows Server 2012 or Windows 8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="04281-162">受支持，但不能编辑仅存在于 Windows 8.1 中的策略设置或首选项</span><span class="sxs-lookup"><span data-stu-id="04281-162">Supported, but cannot edit policy settings or preference items that exist only in Windows8.1</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="04281-163">Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="04281-163">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="04281-164">Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="04281-164">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="04281-165">受支持，但不能编辑仅存在于 Windows 8.1 中的策略设置或首选项</span><span class="sxs-lookup"><span data-stu-id="04281-165">Supported, but cannot edit policy settings or preference items that exist only in Windows8.1</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="04281-166">Windows Server 2012、Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="04281-166">Windows Server 2012, Windows Server2008R2, or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="04281-167">Windows Server2008 或 WindowsVista Service Pack 1 (SP1) </span><span class="sxs-lookup"><span data-stu-id="04281-167">Windows Server2008 or WindowsVista with Service Pack 1 (SP1)</span></span></p></td>
<td align="left"><p><span data-ttu-id="04281-168">受支持，但不能编辑仅存在于 Windows Server2012 R2、Windows Server 2012、Windows Server2008R2、Windows 8.1 或 Windows7 中的策略设置或首选项</span><span class="sxs-lookup"><span data-stu-id="04281-168">Supported, but cannot edit policy settings or preference items that exist only in Windows Server2012 R2, Windows Server 2012, Windows Server2008R2, Windows8.1, or Windows7</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="04281-169">Windows Server2008 或 Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="04281-169">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="04281-170">Windows Server 2012、Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="04281-170">Windows Server 2012, Windows Server2008R2, or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="04281-171">不支持</span><span class="sxs-lookup"><span data-stu-id="04281-171">Not supported</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="04281-172">Windows Server2008 或 Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="04281-172">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="04281-173">Windows Server2008 或 Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="04281-173">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="04281-174">受支持，但无法报告或编辑仅存在于 Windows Server2012 R2、Windows Server 2012、Windows Server2008R2、Windows 8.1 或 Windows7 中的策略设置或首选项</span><span class="sxs-lookup"><span data-stu-id="04281-174">Supported, but cannot report or edit policy settings or preference items that exist only in Windows Server2012 R2, Windows Server 2012, Windows Server2008R2, Windows8.1, or Windows7</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="04281-175">AGPM 4.0 SP1</span><span class="sxs-lookup"><span data-stu-id="04281-175">AGPM4.0 SP1</span></span>


<span data-ttu-id="04281-176">表2列出了可安装 AGPM 4.0 SP1 的操作系统，以及可使用 AGPM 4.0 SP1 管理的策略设置。</span><span class="sxs-lookup"><span data-stu-id="04281-176">Table 2 lists the operating systems on which you can install AGPM 4.0 SP1, and the policy settings that you can manage by using AGPM4.0 SP1.</span></span>

**<span data-ttu-id="04281-177">表3： AGPM 4.0 SP1 支持的操作系统和策略设置</span><span class="sxs-lookup"><span data-stu-id="04281-177">Table 3: AGPM4.0 SP1 supported operating systems and policy settings</span></span>**

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong><span data-ttu-id="04281-178">AGPM 服务器支持的配置</span><span class="sxs-lookup"><span data-stu-id="04281-178">Supported configurations for the AGPM Server</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="04281-179">AGPM 客户端支持的配置</span><span class="sxs-lookup"><span data-stu-id="04281-179">Supported configurations for the AGPM Client</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="04281-180">AGPM 支持</span><span class="sxs-lookup"><span data-stu-id="04281-180">AGPM Support</span></span></strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="04281-181">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="04281-181">Windows Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="04281-182">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="04281-182">Windows Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="04281-183">支持</span><span class="sxs-lookup"><span data-stu-id="04281-183">Supported</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="04281-184">Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="04281-184">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="04281-185">Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="04281-185">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="04281-186">受支持，但不能编辑仅存在于 Windows 8.1 中的策略设置或首选项项目</span><span class="sxs-lookup"><span data-stu-id="04281-186">Supported, but cannot edit policy settings or preference items that exist only in Windows 8.1</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="04281-187">Windows Server 2012、Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="04281-187">Windows Server 2012, Windows Server2008R2, or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="04281-188">Windows Server2008 或 Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="04281-188">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="04281-189">受支持，但不能编辑仅存在于 Windows Server2008R2 或 Windows7 中的策略设置或首选项</span><span class="sxs-lookup"><span data-stu-id="04281-189">Supported, but cannot edit policy settings or preference items that exist only in Windows Server2008R2, or Windows7</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="04281-190">Windows Server2008 或 Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="04281-190">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="04281-191">Windows Server 2012、Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="04281-191">Windows Server 2012, Windows Server2008R2, or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="04281-192">支持</span><span class="sxs-lookup"><span data-stu-id="04281-192">Supported</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="04281-193">Windows Server2008 或 Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="04281-193">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="04281-194">Windows Server2008 或 Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="04281-194">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="04281-195">受支持，但无法报告或编辑仅存在于 Windows Server2008R2 或 Windows7 中的策略设置或首选项</span><span class="sxs-lookup"><span data-stu-id="04281-195">Supported, but cannot report or edit policy settings or preference items that exist only in Windows Server2008R2, or Windows7</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="04281-196">AGPM 4。0</span><span class="sxs-lookup"><span data-stu-id="04281-196">AGPM4.0</span></span>


<span data-ttu-id="04281-197">表3列出了可安装 AGPM 4.0 的操作系统，以及可使用 AGPM 4.0 管理的策略设置。</span><span class="sxs-lookup"><span data-stu-id="04281-197">Table 3 lists the operating systems on which you can install AGPM 4.0, and the policy settings that you can manage by using AGPM4.0.</span></span>

**<span data-ttu-id="04281-198">表4： AGPM 4.0 支持的操作系统和策略设置</span><span class="sxs-lookup"><span data-stu-id="04281-198">Table 4: AGPM4.0 supported operating systems and policy settings</span></span>**

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="04281-199">AGPM 服务器支持的操作系统</span><span class="sxs-lookup"><span data-stu-id="04281-199">Supported operating systems for the AGPM Server</span></span></th>
<th align="left"><span data-ttu-id="04281-200">AGPM 客户端支持的操作系统</span><span class="sxs-lookup"><span data-stu-id="04281-200">Supported operating systems for the AGPM Client</span></span></th>
<th align="left"><span data-ttu-id="04281-201">AGPM 支持</span><span class="sxs-lookup"><span data-stu-id="04281-201">AGPM Support</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="04281-202">Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="04281-202">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="04281-203">Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="04281-203">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="04281-204">支持</span><span class="sxs-lookup"><span data-stu-id="04281-204">Supported</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="04281-205">Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="04281-205">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="04281-206">Windows Server2008 或 Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="04281-206">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="04281-207">受支持，但不能编辑仅存在于 Windows Server2008R2 或 Windows7 中的策略设置或首选项</span><span class="sxs-lookup"><span data-stu-id="04281-207">Supported, but cannot edit policy settings or preference items that exist only in Windows Server2008R2 or Windows7</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="04281-208">Windows Server2008 或 Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="04281-208">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="04281-209">Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="04281-209">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="04281-210">不支持</span><span class="sxs-lookup"><span data-stu-id="04281-210">Not supported</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="04281-211">Windows Server2008 或 Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="04281-211">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="04281-212">Windows Server2008 或 Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="04281-212">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="04281-213">受支持，但无法报告或编辑仅存在于 Windows Server2008R2 或 Windows7 中的策略设置或首选项</span><span class="sxs-lookup"><span data-stu-id="04281-213">Supported, but cannot report or edit policy settings or preference items that exist only in Windows Server2008R2 or Windows7</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="04281-214">在 AGPM 4.0 之前的 AGPM 版本</span><span class="sxs-lookup"><span data-stu-id="04281-214">Versions of AGPM that precede AGPM4.0</span></span>


<span data-ttu-id="04281-215">表4列出了可在其上安装 agpm 4.0 之前的 AGPM 版本的操作系统。</span><span class="sxs-lookup"><span data-stu-id="04281-215">Table 4 lists the operating systems on which you can install the versions of AGPM that precede AGPM4.0.</span></span> <span data-ttu-id="04281-216">如果未列出操作系统，则无法在该操作系统上安装 AGPM。</span><span class="sxs-lookup"><span data-stu-id="04281-216">If an operating system is not listed, you cannot install AGPM on that operating system.</span></span>

**<span data-ttu-id="04281-217">表5：在 AGPM 4.0 之前的 AGPM 版本的受支持的操作系统</span><span class="sxs-lookup"><span data-stu-id="04281-217">Table 5: Supported operating systems for versions of AGPM that precede AGPM4.0</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="04281-218">操作系统</span><span class="sxs-lookup"><span data-stu-id="04281-218">Operating system</span></span></th>
<th align="left"><span data-ttu-id="04281-219">可安装的 AGPM 版本</span><span class="sxs-lookup"><span data-stu-id="04281-219">Version of AGPM that can be installed</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="04281-220">Windows Server2008</span><span class="sxs-lookup"><span data-stu-id="04281-220">Windows Server2008</span></span></p></td>
<td align="left"><p><span data-ttu-id="04281-221">3.0</span><span class="sxs-lookup"><span data-stu-id="04281-221">3.0</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="04281-222">Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="04281-222">Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="04281-223">3.0</span><span class="sxs-lookup"><span data-stu-id="04281-223">3.0</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="04281-224">WindowsVista 未安装 service pack (32 位) </span><span class="sxs-lookup"><span data-stu-id="04281-224">WindowsVista with no service pack installed (32-bit)</span></span></p></td>
<td align="left"><p><span data-ttu-id="04281-225">2.5</span><span class="sxs-lookup"><span data-stu-id="04281-225">2.5</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="04281-226">Windows Server2003 (32 位) </span><span class="sxs-lookup"><span data-stu-id="04281-226">Windows Server2003 (32-bit)</span></span></p></td>
<td align="left"><p><span data-ttu-id="04281-227">2.5</span><span class="sxs-lookup"><span data-stu-id="04281-227">2.5</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="04281-228">如何获取 MDOP 技术</span><span class="sxs-lookup"><span data-stu-id="04281-228">How to Get MDOP Technologies</span></span>


<span data-ttu-id="04281-229">AGPM 4.0 SP2 是 Microsoft 桌面优化包 (MDOP) 的一部分。</span><span class="sxs-lookup"><span data-stu-id="04281-229">AGPM 4.0 SP2 is a part of the Microsoft Desktop Optimization Pack (MDOP).</span></span> <span data-ttu-id="04281-230">MDOP 是 Microsoft 软件保障的一部分。</span><span class="sxs-lookup"><span data-stu-id="04281-230">MDOP is part of Microsoft Software Assurance.</span></span> <span data-ttu-id="04281-231">有关 Microsoft 软件保证和获取 MDOP 的详细信息，请参阅[如何获取 mdop](https://go.microsoft.com/fwlink/?LinkId=322049) (https://go.microsoft.com/fwlink/?LinkId=322049) 。</span><span class="sxs-lookup"><span data-stu-id="04281-231">For more information about Microsoft Software Assurance and acquiring MDOP, see [How Do I Get MDOP](https://go.microsoft.com/fwlink/?LinkId=322049) (https://go.microsoft.com/fwlink/?LinkId=322049).</span></span>

## <span data-ttu-id="04281-232">相关主题</span><span class="sxs-lookup"><span data-stu-id="04281-232">Related topics</span></span>


[<span data-ttu-id="04281-233">高级组策略管理</span><span class="sxs-lookup"><span data-stu-id="04281-233">Advanced Group Policy Management</span></span>](index.md)

 

 





