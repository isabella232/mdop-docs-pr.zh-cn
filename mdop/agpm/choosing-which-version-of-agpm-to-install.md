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
ms.openlocfilehash: b09ea8161b6801c62552f1c0d0ef8455dc111e2f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802080"
---
# <span data-ttu-id="58caf-103">选择要安装的 AGPM 版本</span><span class="sxs-lookup"><span data-stu-id="58caf-103">Choosing Which Version of AGPM to Install</span></span>


<span data-ttu-id="58caf-104">MicrosoftAdvanced 组策略管理（AGPM）的每个版本都支持特定版本的 Windows 操作系统。</span><span class="sxs-lookup"><span data-stu-id="58caf-104">Each release of MicrosoftAdvanced Group Policy Management (AGPM) supports specific versions of the Windows operating system.</span></span> <span data-ttu-id="58caf-105">我们强烈建议你在同一操作系统行上运行 AGPM 客户端和 AGPM 服务器。</span><span class="sxs-lookup"><span data-stu-id="58caf-105">We strongly recommend that you run the AGPM Client and AGPM Server on the same line of operating systems.</span></span> <span data-ttu-id="58caf-106">例如，windows 10 适用于 windows Server 2016、windows 8.1 和 Windows Server2012 R2 等。</span><span class="sxs-lookup"><span data-stu-id="58caf-106">For example, Windows 10 with Windows Server 2016, Windows8.1 with Windows Server2012 R2, and so on.</span></span>

<span data-ttu-id="58caf-107">我们建议你在域中的最新版本的操作系统上安装 AGPM 服务器。</span><span class="sxs-lookup"><span data-stu-id="58caf-107">We recommend that you install the AGPM Server on the most recent version of the operating system in the domain.</span></span> <span data-ttu-id="58caf-108">AGPM 使用组策略管理控制台（GPMC）备份和还原组策略对象（Gpo）。</span><span class="sxs-lookup"><span data-stu-id="58caf-108">AGPM uses the Group Policy Management Console (GPMC) to back up and restore Group Policy Objects (GPOs).</span></span> <span data-ttu-id="58caf-109">由于较新版本的 GPMC 提供的其他策略设置在早期版本中不可用，因此你可以使用最新版本的操作系统管理更多策略设置。</span><span class="sxs-lookup"><span data-stu-id="58caf-109">Because newer versions of the GPMC provide additional policy settings that are not available in earlier versions, you can manage more policy settings by using the most recent version of the operating system.</span></span>

<span data-ttu-id="58caf-110">所有版本的 AGPM 都只能管理在同一版本或早期版本的运行 AGPM 的操作系统中引入的策略设置。</span><span class="sxs-lookup"><span data-stu-id="58caf-110">All versions of AGPM can manage only the policy settings that were introduced in the same version or an earlier version of the operating system on which AGPM is running.</span></span> <span data-ttu-id="58caf-111">例如，如果在 Windows Server 2012 上安装了 AGPM 4.0 SP2，则可以管理 Windows Server 2012 或更早版本中引入的策略设置，但不能管理稍后在 Windows 8.1 或 Windows Server2012 R2 中引入的策略设置。</span><span class="sxs-lookup"><span data-stu-id="58caf-111">For example, if you install AGPM4.0 SP2 on Windows Server 2012, you can manage policy settings that were introduced in Windows Server 2012 or earlier, but you cannot manage policy settings that were introduced later, in Windows8.1 or Windows Server2012 R2.</span></span>

<span data-ttu-id="58caf-112">如果你的 AGPM 服务器上的 GPMC 版本比管理员用于管理组策略的计算机上的版本旧，则 AGPM 服务器将无法存储在较早版本的 GPMC 中不可用的任何策略设置。</span><span class="sxs-lookup"><span data-stu-id="58caf-112">If the version of the GPMC on your AGPM Server is older than the version on the computers that administrators use to manage Group Policy, the AGPM Server will be unable to store any policy settings that are not available in the older version of the GPMC.</span></span> <span data-ttu-id="58caf-113">有关 Windows 中包含的组策略设置的电子表格，请参阅[适用于 Windows 和 Windows Server 的组策略设置参考](https://go.microsoft.com/fwlink/p/?LinkId=613627)。</span><span class="sxs-lookup"><span data-stu-id="58caf-113">For a spreadsheet of Group Policy settings included in Windows, see [Group Policy Settings Reference for Windows and Windows Server](https://go.microsoft.com/fwlink/p/?LinkId=613627).</span></span>

## <span data-ttu-id="58caf-114">AGPM 4.0 SP3</span><span class="sxs-lookup"><span data-stu-id="58caf-114">AGPM4.0 SP3</span></span>


<span data-ttu-id="58caf-115">如果使用运行 Windows 10 的计算机管理 Gpo，则必须使用 AGPM 4.0 SP3。</span><span class="sxs-lookup"><span data-stu-id="58caf-115">If you are using computers that are running Windows 10 to manage GPOs, you must use AGPM 4.0 SP3.</span></span> <span data-ttu-id="58caf-116">无法在运行 Windows 10 操作系统的计算机上安装早期版本的 AGPM。</span><span class="sxs-lookup"><span data-stu-id="58caf-116">You cannot install earlier versions of AGPM on computers that are running the Windows 10 operating system.</span></span>

<span data-ttu-id="58caf-117">表1列出了可在其上安装 AGPM 4.0 SP3 的操作系统，以及可使用 AGPM 4.0 SP3 管理的策略设置。</span><span class="sxs-lookup"><span data-stu-id="58caf-117">Table 1 lists the operating systems on which you can install AGPM4.0 SP3, and the policy settings that you can manage by using AGPM4.0 SP3.</span></span>

**<span data-ttu-id="58caf-118">表1： AGPM 4.0 SP3 支持的操作系统和策略设置</span><span class="sxs-lookup"><span data-stu-id="58caf-118">Table 1: AGPM 4.0 SP3 supported operating systems and policy settings</span></span>**

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong><span data-ttu-id="58caf-119">AGPM 服务器支持的配置</span><span class="sxs-lookup"><span data-stu-id="58caf-119">Supported configurations for the AGPM Server</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="58caf-120">AGPM 客户端支持的配置</span><span class="sxs-lookup"><span data-stu-id="58caf-120">Supported configurations for the AGPM Client</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="58caf-121">AGPM 支持</span><span class="sxs-lookup"><span data-stu-id="58caf-121">AGPM Support</span></span></strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="58caf-122">Windows Server 2016 或 Windows 10</span><span class="sxs-lookup"><span data-stu-id="58caf-122">Windows Server 2016 or Windows 10</span></span></p></td>
<td align="left"><p><span data-ttu-id="58caf-123">Windows Server 2016 或 Windows 10</span><span class="sxs-lookup"><span data-stu-id="58caf-123">Windows Server 2016 or Windows 10</span></span></p></td>
<td align="left"><p><span data-ttu-id="58caf-124">支持</span><span class="sxs-lookup"><span data-stu-id="58caf-124">Supported</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="58caf-125">Windows Server2012 R2</span><span class="sxs-lookup"><span data-stu-id="58caf-125">Windows Server2012 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="58caf-126">Windows 10</span><span class="sxs-lookup"><span data-stu-id="58caf-126">Windows 10</span></span></p></td>
<td align="left"><p><span data-ttu-id="58caf-127">通过在 KB 4015786 中概述的注意事项提供支持 <a href="https://support.microsoft.com/help/4015786/known-issues-managing-a-windows-10-group-policy-client-in-windows-serv" data-raw-source="[KB 4015786](https://support.microsoft.com/help/4015786/known-issues-managing-a-windows-10-group-policy-client-in-windows-serv)"></span><span class="sxs-lookup"><span data-stu-id="58caf-127">Supported with the caveats outlined in <a href="https://support.microsoft.com/help/4015786/known-issues-managing-a-windows-10-group-policy-client-in-windows-serv" data-raw-source="[KB 4015786](https://support.microsoft.com/help/4015786/known-issues-managing-a-windows-10-group-policy-client-in-windows-serv)">KB 4015786</span></span></a>
</p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="58caf-128">Windows Server2012 R2 或 Windows 8。1</span><span class="sxs-lookup"><span data-stu-id="58caf-128">Windows Server2012 R2 or Windows8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="58caf-129">Windows Server2012 R2 或 Windows 8。1</span><span class="sxs-lookup"><span data-stu-id="58caf-129">Windows Server2012 R2 or Windows8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="58caf-130">支持</span><span class="sxs-lookup"><span data-stu-id="58caf-130">Supported</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="58caf-131">Windows Server2012 R2、Windows Server 2012 或 Windows 8。1</span><span class="sxs-lookup"><span data-stu-id="58caf-131">Windows Server2012 R2, Windows Server 2012, or Windows8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="58caf-132">Windows Server 2012 或 Windows 8。1</span><span class="sxs-lookup"><span data-stu-id="58caf-132">Windows Server 2012 or Windows 8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="58caf-133">受支持，但不能编辑仅存在于 Windows 8.1 中的策略设置或首选项</span><span class="sxs-lookup"><span data-stu-id="58caf-133">Supported, but cannot edit policy settings or preference items that exist only in Windows8.1</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="58caf-134">Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="58caf-134">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="58caf-135">Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="58caf-135">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="58caf-136">受支持，但不能编辑仅存在于 Windows 8.1 中的策略设置或首选项</span><span class="sxs-lookup"><span data-stu-id="58caf-136">Supported, but cannot edit policy settings or preference items that exist only in Windows8.1</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="58caf-137">Windows Server 2012、Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="58caf-137">Windows Server 2012, Windows Server2008R2, or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="58caf-138">Windows Server2008 或 WindowsVista Service Pack 1 （SP1）</span><span class="sxs-lookup"><span data-stu-id="58caf-138">Windows Server2008 or WindowsVista with Service Pack 1 (SP1)</span></span></p></td>
<td align="left"><p><span data-ttu-id="58caf-139">受支持，但不能编辑仅存在于 Windows Server2012 R2、Windows Server 2012、Windows Server2008R2、Windows 8.1 或 Windows7 中的策略设置或首选项</span><span class="sxs-lookup"><span data-stu-id="58caf-139">Supported, but cannot edit policy settings or preference items that exist only in Windows Server2012 R2, Windows Server 2012, Windows Server2008R2, Windows8.1, or Windows7</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="58caf-140">Windows Server2008 或 Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="58caf-140">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="58caf-141">Windows Server 2012、Windows Server2008R2、Windows 8 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="58caf-141">Windows Server 2012, Windows Server2008R2, Windows 8, or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="58caf-142">不支持</span><span class="sxs-lookup"><span data-stu-id="58caf-142">Not supported</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="58caf-143">Windows Server2008 或 Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="58caf-143">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="58caf-144">Windows Server2008 或 Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="58caf-144">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="58caf-145">受支持，但无法报告或编辑仅存在于 Windows Server2012 R2、Windows Server 2012、Windows Server2008R2、Windows 8.1 或 Windows7 中的策略设置或首选项</span><span class="sxs-lookup"><span data-stu-id="58caf-145">Supported, but cannot report or edit policy settings or preference items that exist only in Windows Server2012 R2, Windows Server 2012, Windows Server2008R2, Windows8.1, or Windows7</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="58caf-146">AGPM 4.0 SP2</span><span class="sxs-lookup"><span data-stu-id="58caf-146">AGPM4.0 SP2</span></span>


<span data-ttu-id="58caf-147">如果你使用运行 Windows Server2012 R2 或 Windows 8.1 的计算机管理 Gpo，则必须使用 AGPM 4.0 SP2。</span><span class="sxs-lookup"><span data-stu-id="58caf-147">If you are using computers that are running Windows Server2012 R2 or Windows8.1 to manage GPOs, you must use AGPM4.0 SP2.</span></span> <span data-ttu-id="58caf-148">无法在运行这些操作系统的计算机上安装早期版本的 AGPM。</span><span class="sxs-lookup"><span data-stu-id="58caf-148">You cannot install earlier versions of AGPM on computers that are running those operating systems.</span></span>

<span data-ttu-id="58caf-149">表1列出了可在其上安装 AGPM 4.0 SP2 的操作系统，以及可使用 AGPM 4.0 SP2 管理的策略设置。</span><span class="sxs-lookup"><span data-stu-id="58caf-149">Table 1 lists the operating systems on which you can install AGPM4.0 SP2, and the policy settings that you can manage by using AGPM4.0 SP2.</span></span>

**<span data-ttu-id="58caf-150">表2： AGPM 4.0 SP2 支持的操作系统和策略设置</span><span class="sxs-lookup"><span data-stu-id="58caf-150">Table 2: AGPM4.0 SP2 supported operating systems and policy settings</span></span>**

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong><span data-ttu-id="58caf-151">AGPM 服务器支持的配置</span><span class="sxs-lookup"><span data-stu-id="58caf-151">Supported configurations for the AGPM Server</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="58caf-152">AGPM 客户端支持的配置</span><span class="sxs-lookup"><span data-stu-id="58caf-152">Supported configurations for the AGPM Client</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="58caf-153">AGPM 支持</span><span class="sxs-lookup"><span data-stu-id="58caf-153">AGPM Support</span></span></strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="58caf-154">Windows Server2012 R2 或 Windows 8。1</span><span class="sxs-lookup"><span data-stu-id="58caf-154">Windows Server2012 R2 or Windows8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="58caf-155">Windows Server2012 R2 或 Windows 8。1</span><span class="sxs-lookup"><span data-stu-id="58caf-155">Windows Server2012 R2 or Windows8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="58caf-156">支持</span><span class="sxs-lookup"><span data-stu-id="58caf-156">Supported</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="58caf-157">Windows Server2012 R2、Windows Server 2012 或 Windows 8。1</span><span class="sxs-lookup"><span data-stu-id="58caf-157">Windows Server2012 R2, Windows Server 2012, or Windows8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="58caf-158">Windows Server 2012 或 Windows 8。1</span><span class="sxs-lookup"><span data-stu-id="58caf-158">Windows Server 2012 or Windows 8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="58caf-159">受支持，但不能编辑仅存在于 Windows 8.1 中的策略设置或首选项</span><span class="sxs-lookup"><span data-stu-id="58caf-159">Supported, but cannot edit policy settings or preference items that exist only in Windows8.1</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="58caf-160">Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="58caf-160">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="58caf-161">Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="58caf-161">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="58caf-162">受支持，但不能编辑仅存在于 Windows 8.1 中的策略设置或首选项</span><span class="sxs-lookup"><span data-stu-id="58caf-162">Supported, but cannot edit policy settings or preference items that exist only in Windows8.1</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="58caf-163">Windows Server 2012、Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="58caf-163">Windows Server 2012, Windows Server2008R2, or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="58caf-164">Windows Server2008 或 WindowsVista Service Pack 1 （SP1）</span><span class="sxs-lookup"><span data-stu-id="58caf-164">Windows Server2008 or WindowsVista with Service Pack 1 (SP1)</span></span></p></td>
<td align="left"><p><span data-ttu-id="58caf-165">受支持，但不能编辑仅存在于 Windows Server2012 R2、Windows Server 2012、Windows Server2008R2、Windows 8.1 或 Windows7 中的策略设置或首选项</span><span class="sxs-lookup"><span data-stu-id="58caf-165">Supported, but cannot edit policy settings or preference items that exist only in Windows Server2012 R2, Windows Server 2012, Windows Server2008R2, Windows8.1, or Windows7</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="58caf-166">Windows Server2008 或 Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="58caf-166">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="58caf-167">Windows Server 2012、Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="58caf-167">Windows Server 2012, Windows Server2008R2, or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="58caf-168">不支持</span><span class="sxs-lookup"><span data-stu-id="58caf-168">Not supported</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="58caf-169">Windows Server2008 或 Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="58caf-169">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="58caf-170">Windows Server2008 或 Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="58caf-170">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="58caf-171">受支持，但无法报告或编辑仅存在于 Windows Server2012 R2、Windows Server 2012、Windows Server2008R2、Windows 8.1 或 Windows7 中的策略设置或首选项</span><span class="sxs-lookup"><span data-stu-id="58caf-171">Supported, but cannot report or edit policy settings or preference items that exist only in Windows Server2012 R2, Windows Server 2012, Windows Server2008R2, Windows8.1, or Windows7</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="58caf-172">AGPM 4.0 SP1</span><span class="sxs-lookup"><span data-stu-id="58caf-172">AGPM4.0 SP1</span></span>


<span data-ttu-id="58caf-173">表2列出了可安装 AGPM 4.0 SP1 的操作系统，以及可使用 AGPM 4.0 SP1 管理的策略设置。</span><span class="sxs-lookup"><span data-stu-id="58caf-173">Table 2 lists the operating systems on which you can install AGPM 4.0 SP1, and the policy settings that you can manage by using AGPM4.0 SP1.</span></span>

**<span data-ttu-id="58caf-174">表3： AGPM 4.0 SP1 支持的操作系统和策略设置</span><span class="sxs-lookup"><span data-stu-id="58caf-174">Table 3: AGPM4.0 SP1 supported operating systems and policy settings</span></span>**

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong><span data-ttu-id="58caf-175">AGPM 服务器支持的配置</span><span class="sxs-lookup"><span data-stu-id="58caf-175">Supported configurations for the AGPM Server</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="58caf-176">AGPM 客户端支持的配置</span><span class="sxs-lookup"><span data-stu-id="58caf-176">Supported configurations for the AGPM Client</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="58caf-177">AGPM 支持</span><span class="sxs-lookup"><span data-stu-id="58caf-177">AGPM Support</span></span></strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="58caf-178">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="58caf-178">Windows Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="58caf-179">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="58caf-179">Windows Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="58caf-180">支持</span><span class="sxs-lookup"><span data-stu-id="58caf-180">Supported</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="58caf-181">Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="58caf-181">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="58caf-182">Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="58caf-182">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="58caf-183">受支持，但不能编辑仅存在于 Windows 8.1 中的策略设置或首选项项目</span><span class="sxs-lookup"><span data-stu-id="58caf-183">Supported, but cannot edit policy settings or preference items that exist only in Windows 8.1</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="58caf-184">Windows Server 2012、Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="58caf-184">Windows Server 2012, Windows Server2008R2, or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="58caf-185">Windows Server2008 或 Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="58caf-185">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="58caf-186">受支持，但不能编辑仅存在于 Windows Server2008R2 或 Windows7 中的策略设置或首选项</span><span class="sxs-lookup"><span data-stu-id="58caf-186">Supported, but cannot edit policy settings or preference items that exist only in Windows Server2008R2, or Windows7</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="58caf-187">Windows Server2008 或 Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="58caf-187">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="58caf-188">Windows Server 2012、Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="58caf-188">Windows Server 2012, Windows Server2008R2, or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="58caf-189">支持</span><span class="sxs-lookup"><span data-stu-id="58caf-189">Supported</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="58caf-190">Windows Server2008 或 Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="58caf-190">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="58caf-191">Windows Server2008 或 Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="58caf-191">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="58caf-192">受支持，但无法报告或编辑仅存在于 Windows Server2008R2 或 Windows7 中的策略设置或首选项</span><span class="sxs-lookup"><span data-stu-id="58caf-192">Supported, but cannot report or edit policy settings or preference items that exist only in Windows Server2008R2, or Windows7</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="58caf-193">AGPM 4。0</span><span class="sxs-lookup"><span data-stu-id="58caf-193">AGPM4.0</span></span>


<span data-ttu-id="58caf-194">表3列出了可安装 AGPM 4.0 的操作系统，以及可使用 AGPM 4.0 管理的策略设置。</span><span class="sxs-lookup"><span data-stu-id="58caf-194">Table 3 lists the operating systems on which you can install AGPM 4.0, and the policy settings that you can manage by using AGPM4.0.</span></span>

**<span data-ttu-id="58caf-195">表4： AGPM 4.0 支持的操作系统和策略设置</span><span class="sxs-lookup"><span data-stu-id="58caf-195">Table 4: AGPM4.0 supported operating systems and policy settings</span></span>**

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="58caf-196">AGPM 服务器支持的操作系统</span><span class="sxs-lookup"><span data-stu-id="58caf-196">Supported operating systems for the AGPM Server</span></span></th>
<th align="left"><span data-ttu-id="58caf-197">AGPM 客户端支持的操作系统</span><span class="sxs-lookup"><span data-stu-id="58caf-197">Supported operating systems for the AGPM Client</span></span></th>
<th align="left"><span data-ttu-id="58caf-198">AGPM 支持</span><span class="sxs-lookup"><span data-stu-id="58caf-198">AGPM Support</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="58caf-199">Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="58caf-199">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="58caf-200">Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="58caf-200">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="58caf-201">支持</span><span class="sxs-lookup"><span data-stu-id="58caf-201">Supported</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="58caf-202">Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="58caf-202">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="58caf-203">Windows Server2008 或 Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="58caf-203">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="58caf-204">受支持，但不能编辑仅存在于 Windows Server2008R2 或 Windows7 中的策略设置或首选项</span><span class="sxs-lookup"><span data-stu-id="58caf-204">Supported, but cannot edit policy settings or preference items that exist only in Windows Server2008R2 or Windows7</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="58caf-205">Windows Server2008 或 Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="58caf-205">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="58caf-206">Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="58caf-206">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="58caf-207">不支持</span><span class="sxs-lookup"><span data-stu-id="58caf-207">Not supported</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="58caf-208">Windows Server2008 或 Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="58caf-208">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="58caf-209">Windows Server2008 或 Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="58caf-209">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="58caf-210">受支持，但无法报告或编辑仅存在于 Windows Server2008R2 或 Windows7 中的策略设置或首选项</span><span class="sxs-lookup"><span data-stu-id="58caf-210">Supported, but cannot report or edit policy settings or preference items that exist only in Windows Server2008R2 or Windows7</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="58caf-211">在 AGPM 4.0 之前的 AGPM 版本</span><span class="sxs-lookup"><span data-stu-id="58caf-211">Versions of AGPM that precede AGPM4.0</span></span>


<span data-ttu-id="58caf-212">表4列出了可在其上安装 agpm 4.0 之前的 AGPM 版本的操作系统。</span><span class="sxs-lookup"><span data-stu-id="58caf-212">Table 4 lists the operating systems on which you can install the versions of AGPM that precede AGPM4.0.</span></span> <span data-ttu-id="58caf-213">如果未列出操作系统，则无法在该操作系统上安装 AGPM。</span><span class="sxs-lookup"><span data-stu-id="58caf-213">If an operating system is not listed, you cannot install AGPM on that operating system.</span></span>

**<span data-ttu-id="58caf-214">表5：在 AGPM 4.0 之前的 AGPM 版本的受支持的操作系统</span><span class="sxs-lookup"><span data-stu-id="58caf-214">Table 5: Supported operating systems for versions of AGPM that precede AGPM4.0</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="58caf-215">操作系统</span><span class="sxs-lookup"><span data-stu-id="58caf-215">Operating system</span></span></th>
<th align="left"><span data-ttu-id="58caf-216">可安装的 AGPM 版本</span><span class="sxs-lookup"><span data-stu-id="58caf-216">Version of AGPM that can be installed</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="58caf-217">Windows Server2008</span><span class="sxs-lookup"><span data-stu-id="58caf-217">Windows Server2008</span></span></p></td>
<td align="left"><p><span data-ttu-id="58caf-218">3.0</span><span class="sxs-lookup"><span data-stu-id="58caf-218">3.0</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="58caf-219">Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="58caf-219">Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="58caf-220">3.0</span><span class="sxs-lookup"><span data-stu-id="58caf-220">3.0</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="58caf-221">WindowsVista 未安装 service pack （32位）</span><span class="sxs-lookup"><span data-stu-id="58caf-221">WindowsVista with no service pack installed (32-bit)</span></span></p></td>
<td align="left"><p><span data-ttu-id="58caf-222">2.5</span><span class="sxs-lookup"><span data-stu-id="58caf-222">2.5</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="58caf-223">Windows Server2003 （32位）</span><span class="sxs-lookup"><span data-stu-id="58caf-223">Windows Server2003 (32-bit)</span></span></p></td>
<td align="left"><p><span data-ttu-id="58caf-224">2.5</span><span class="sxs-lookup"><span data-stu-id="58caf-224">2.5</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="58caf-225">如何获取 MDOP 技术</span><span class="sxs-lookup"><span data-stu-id="58caf-225">How to Get MDOP Technologies</span></span>


<span data-ttu-id="58caf-226">AGPM 4.0 SP2 是 Microsoft 桌面优化包（MDOP）的一部分。</span><span class="sxs-lookup"><span data-stu-id="58caf-226">AGPM 4.0 SP2 is a part of the Microsoft Desktop Optimization Pack (MDOP).</span></span> <span data-ttu-id="58caf-227">MDOP 是 Microsoft 软件保障的一部分。</span><span class="sxs-lookup"><span data-stu-id="58caf-227">MDOP is part of Microsoft Software Assurance.</span></span> <span data-ttu-id="58caf-228">有关 Microsoft 软件保证和获取 MDOP 的详细信息，请参阅[如何获取 mdop](https://go.microsoft.com/fwlink/?LinkId=322049) （ https://go.microsoft.com/fwlink/?LinkId=322049) 。</span><span class="sxs-lookup"><span data-stu-id="58caf-228">For more information about Microsoft Software Assurance and acquiring MDOP, see [How Do I Get MDOP](https://go.microsoft.com/fwlink/?LinkId=322049) (https://go.microsoft.com/fwlink/?LinkId=322049).</span></span>

## <span data-ttu-id="58caf-229">相关主题</span><span class="sxs-lookup"><span data-stu-id="58caf-229">Related topics</span></span>


[<span data-ttu-id="58caf-230">高级组策略管理</span><span class="sxs-lookup"><span data-stu-id="58caf-230">Advanced Group Policy Management</span></span>](index.md)

 

 





