---
title: 如何确定是编辑还是升级虚拟应用程序包
description: 如何确定是编辑还是升级虚拟应用程序包
author: dansimp
ms.assetid: 33dd5332-6802-46e0-9748-43fcc8f80aa3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b256a4927231613b6f2e688b5951adf57c9cb89a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801443"
---
# <span data-ttu-id="0f3d1-103">如何确定是编辑还是升级虚拟应用程序包</span><span class="sxs-lookup"><span data-stu-id="0f3d1-103">How to Determine Whether to Edit or Upgrade a Virtual Application Package</span></span>


<span data-ttu-id="0f3d1-104">使用下表来帮助确定是否可以打开虚拟应用程序包进行编辑，无论是需要创建新版本的程序包，还是使用 App-v 排序器的任一选项可用。</span><span class="sxs-lookup"><span data-stu-id="0f3d1-104">Use the following table to help determine whether a virtual application package can be opened for edit, whether you need to create a new version of the package, or whether either option is available, using the App-V Sequencer.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="0f3d1-105">操作</span><span class="sxs-lookup"><span data-stu-id="0f3d1-105">Action</span></span></th>
<th align="left"><span data-ttu-id="0f3d1-106">打开进行编辑</span><span class="sxs-lookup"><span data-stu-id="0f3d1-106">Open for edit</span></span></th>
<th align="left"><span data-ttu-id="0f3d1-107">打开以升级</span><span class="sxs-lookup"><span data-stu-id="0f3d1-107">Open for upgrade</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0f3d1-108">查看程序包属性。</span><span class="sxs-lookup"><span data-stu-id="0f3d1-108">View package properties.</span></span></p></td>
<td align="left"><p><span data-ttu-id="0f3d1-109">是</span><span class="sxs-lookup"><span data-stu-id="0f3d1-109">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="0f3d1-110">是</span><span class="sxs-lookup"><span data-stu-id="0f3d1-110">Yes</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0f3d1-111">查看程序包更改历史记录。</span><span class="sxs-lookup"><span data-stu-id="0f3d1-111">View package change history.</span></span></p></td>
<td align="left"><p><span data-ttu-id="0f3d1-112">是</span><span class="sxs-lookup"><span data-stu-id="0f3d1-112">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="0f3d1-113">是</span><span class="sxs-lookup"><span data-stu-id="0f3d1-113">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0f3d1-114">查看关联的程序包文件。</span><span class="sxs-lookup"><span data-stu-id="0f3d1-114">View associated package files.</span></span></p></td>
<td align="left"><p><span data-ttu-id="0f3d1-115">是</span><span class="sxs-lookup"><span data-stu-id="0f3d1-115">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="0f3d1-116">是</span><span class="sxs-lookup"><span data-stu-id="0f3d1-116">Yes</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0f3d1-117">编辑注册表设置。</span><span class="sxs-lookup"><span data-stu-id="0f3d1-117">Edit registry settings.</span></span></p></td>
<td align="left"><p><span data-ttu-id="0f3d1-118">是</span><span class="sxs-lookup"><span data-stu-id="0f3d1-118">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="0f3d1-119">是</span><span class="sxs-lookup"><span data-stu-id="0f3d1-119">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0f3d1-120">查看其他程序包设置（操作系统文件属性除外）。</span><span class="sxs-lookup"><span data-stu-id="0f3d1-120">Review additional package settings (except operating system file properties).</span></span></p></td>
<td align="left"><p><span data-ttu-id="0f3d1-121">是</span><span class="sxs-lookup"><span data-stu-id="0f3d1-121">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="0f3d1-122">是</span><span class="sxs-lookup"><span data-stu-id="0f3d1-122">Yes</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0f3d1-123">创建关联的 Windows Installer （MSI）。</span><span class="sxs-lookup"><span data-stu-id="0f3d1-123">Create associated Windows Installer (MSI).</span></span></p></td>
<td align="left"><p><span data-ttu-id="0f3d1-124">是</span><span class="sxs-lookup"><span data-stu-id="0f3d1-124">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="0f3d1-125">是</span><span class="sxs-lookup"><span data-stu-id="0f3d1-125">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0f3d1-126">修改 OSD 文件。</span><span class="sxs-lookup"><span data-stu-id="0f3d1-126">Modify OSD file.</span></span></p></td>
<td align="left"><p><span data-ttu-id="0f3d1-127">是</span><span class="sxs-lookup"><span data-stu-id="0f3d1-127">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="0f3d1-128">是</span><span class="sxs-lookup"><span data-stu-id="0f3d1-128">Yes</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0f3d1-129">压缩和解压缩程序包。</span><span class="sxs-lookup"><span data-stu-id="0f3d1-129">Compress and uncompress package.</span></span></p></td>
<td align="left"><p><span data-ttu-id="0f3d1-130">是</span><span class="sxs-lookup"><span data-stu-id="0f3d1-130">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="0f3d1-131">是</span><span class="sxs-lookup"><span data-stu-id="0f3d1-131">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0f3d1-132">添加文件类型关联。</span><span class="sxs-lookup"><span data-stu-id="0f3d1-132">Add file type associations.</span></span></p></td>
<td align="left"><p><span data-ttu-id="0f3d1-133">是</span><span class="sxs-lookup"><span data-stu-id="0f3d1-133">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="0f3d1-134">是</span><span class="sxs-lookup"><span data-stu-id="0f3d1-134">Yes</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0f3d1-135">重命名快捷方式。</span><span class="sxs-lookup"><span data-stu-id="0f3d1-135">Rename shortcuts.</span></span></p></td>
<td align="left"><p><span data-ttu-id="0f3d1-136">是</span><span class="sxs-lookup"><span data-stu-id="0f3d1-136">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="0f3d1-137">是</span><span class="sxs-lookup"><span data-stu-id="0f3d1-137">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0f3d1-138">设置虚拟化注册表项状态（替代/合并）。</span><span class="sxs-lookup"><span data-stu-id="0f3d1-138">Set virtualized registry key state (override / merge).</span></span></p></td>
<td align="left"><p><span data-ttu-id="0f3d1-139">是</span><span class="sxs-lookup"><span data-stu-id="0f3d1-139">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="0f3d1-140">是</span><span class="sxs-lookup"><span data-stu-id="0f3d1-140">Yes</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0f3d1-141">设置虚拟化文件夹状态。</span><span class="sxs-lookup"><span data-stu-id="0f3d1-141">Set virtualized folder state.</span></span></p></td>
<td align="left"><p><span data-ttu-id="0f3d1-142">是</span><span class="sxs-lookup"><span data-stu-id="0f3d1-142">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="0f3d1-143">是</span><span class="sxs-lookup"><span data-stu-id="0f3d1-143">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0f3d1-144">编辑虚拟文件系统映射。</span><span class="sxs-lookup"><span data-stu-id="0f3d1-144">Edit virtual file system mappings.</span></span></p></td>
<td align="left"><p><span data-ttu-id="0f3d1-145">是</span><span class="sxs-lookup"><span data-stu-id="0f3d1-145">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="0f3d1-146">是</span><span class="sxs-lookup"><span data-stu-id="0f3d1-146">Yes</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0f3d1-147">查看程序包的所有关联操作系统文件属性。</span><span class="sxs-lookup"><span data-stu-id="0f3d1-147">Review all associated operating system file properties for a package.</span></span></p></td>
<td align="left"><p><span data-ttu-id="0f3d1-148">否</span><span class="sxs-lookup"><span data-stu-id="0f3d1-148">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="0f3d1-149">是</span><span class="sxs-lookup"><span data-stu-id="0f3d1-149">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0f3d1-150">添加其他服务。</span><span class="sxs-lookup"><span data-stu-id="0f3d1-150">Add additional services.</span></span></p></td>
<td align="left"><p><span data-ttu-id="0f3d1-151">否</span><span class="sxs-lookup"><span data-stu-id="0f3d1-151">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="0f3d1-152">是</span><span class="sxs-lookup"><span data-stu-id="0f3d1-152">Yes</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0f3d1-153">添加其他文件。</span><span class="sxs-lookup"><span data-stu-id="0f3d1-153">Add additional files.</span></span></p></td>
<td align="left"><p><span data-ttu-id="0f3d1-154">否</span><span class="sxs-lookup"><span data-stu-id="0f3d1-154">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="0f3d1-155">是</span><span class="sxs-lookup"><span data-stu-id="0f3d1-155">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0f3d1-156">收集和配置关联的安全描述符。</span><span class="sxs-lookup"><span data-stu-id="0f3d1-156">Collect and configure associated security descriptors.</span></span></p></td>
<td align="left"><p><span data-ttu-id="0f3d1-157">否</span><span class="sxs-lookup"><span data-stu-id="0f3d1-157">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="0f3d1-158">是</span><span class="sxs-lookup"><span data-stu-id="0f3d1-158">Yes</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0f3d1-159">应用安全更新或升级到新版本。</span><span class="sxs-lookup"><span data-stu-id="0f3d1-159">Apply security updates or upgrade to a new version.</span></span></p></td>
<td align="left"><p><span data-ttu-id="0f3d1-160">否</span><span class="sxs-lookup"><span data-stu-id="0f3d1-160">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="0f3d1-161">是</span><span class="sxs-lookup"><span data-stu-id="0f3d1-161">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0f3d1-162">添加其他应用程序。</span><span class="sxs-lookup"><span data-stu-id="0f3d1-162">Add an additional application.</span></span></p></td>
<td align="left"><p><span data-ttu-id="0f3d1-163">否</span><span class="sxs-lookup"><span data-stu-id="0f3d1-163">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="0f3d1-164">是</span><span class="sxs-lookup"><span data-stu-id="0f3d1-164">Yes</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0f3d1-165">应用需要打开应用程序的更新。</span><span class="sxs-lookup"><span data-stu-id="0f3d1-165">Apply updates that require the application to open.</span></span></p></td>
<td align="left"><p><span data-ttu-id="0f3d1-166">否</span><span class="sxs-lookup"><span data-stu-id="0f3d1-166">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="0f3d1-167">是</span><span class="sxs-lookup"><span data-stu-id="0f3d1-167">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0f3d1-168">应用需要重新启动计算机的更新。</span><span class="sxs-lookup"><span data-stu-id="0f3d1-168">Apply updates that require the computer to restart.</span></span></p></td>
<td align="left"><p><span data-ttu-id="0f3d1-169">否</span><span class="sxs-lookup"><span data-stu-id="0f3d1-169">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="0f3d1-170">是</span><span class="sxs-lookup"><span data-stu-id="0f3d1-170">Yes</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="0f3d1-171">相关主题</span><span class="sxs-lookup"><span data-stu-id="0f3d1-171">Related topics</span></span>


[<span data-ttu-id="0f3d1-172">如何编辑现有的虚拟应用程序</span><span class="sxs-lookup"><span data-stu-id="0f3d1-172">How to Edit an Existing Virtual Application</span></span>](how-to-edit-an-existing-virtual-application.md)

[<span data-ttu-id="0f3d1-173">如何升级现有的虚拟应用程序</span><span class="sxs-lookup"><span data-stu-id="0f3d1-173">How to Upgrade an Existing Virtual Application</span></span>](how-to-upgrade-an-existing-virtual-application.md)

 

 





