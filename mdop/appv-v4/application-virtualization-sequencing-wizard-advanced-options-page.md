---
title: 应用程序虚拟化顺序向导高级选项页面
description: 应用程序虚拟化顺序向导高级选项页面
author: dansimp
ms.assetid: 2c4c5d95-d55e-463d-a851-8486f6a724f2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 716fa27852f1cadfebec31a267ce1b9b581b8ff7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802280"
---
# <span data-ttu-id="baff3-103">应用程序虚拟化顺序向导高级选项页面</span><span class="sxs-lookup"><span data-stu-id="baff3-103">Application Virtualization Sequencing Wizard Advanced Options Page</span></span>


<span data-ttu-id="baff3-104">使用应用程序虚拟化（app-v）顺序向导的 "**高级选项**" 页面指定要安装的应用程序的高级选项。</span><span class="sxs-lookup"><span data-stu-id="baff3-104">Use the **Advanced Options** page of the Application Virtualization (App-V) Sequencing Wizard to specify advanced options for the application to be installed.</span></span> <span data-ttu-id="baff3-105">页面包含下表中所述的元素。</span><span class="sxs-lookup"><span data-stu-id="baff3-105">The page contains the elements described in the following table.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="baff3-106">名称</span><span class="sxs-lookup"><span data-stu-id="baff3-106">Name</span></span></th>
<th align="left"><span data-ttu-id="baff3-107">描述</span><span class="sxs-lookup"><span data-stu-id="baff3-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="baff3-108">块大小</span><span class="sxs-lookup"><span data-stu-id="baff3-108">Block Size</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="baff3-109">用于指定在通过网络传输时，SFT 文件将被分成的块的大小。</span><span class="sxs-lookup"><span data-stu-id="baff3-109">Use to specify the size of blocks that the SFT file will be divided into when streamed across a network.</span></span> <span data-ttu-id="baff3-110">所有块都等于指定的大小;但是，最后一个块可能小于指定的大小。</span><span class="sxs-lookup"><span data-stu-id="baff3-110">All blocks equal the specified size; however, the last block might be smaller than specified.</span></span> <span data-ttu-id="baff3-111">选择以下值之一：</span><span class="sxs-lookup"><span data-stu-id="baff3-111">Select one of the following values:</span></span></p>
<ul>
<li><p><strong><span data-ttu-id="baff3-112">4 KB</span><span class="sxs-lookup"><span data-stu-id="baff3-112">4 KB</span></span></strong></p></li>
<li><p><strong><span data-ttu-id="baff3-113">16 KB</span><span class="sxs-lookup"><span data-stu-id="baff3-113">16 KB</span></span></strong></p></li>
<li><p><strong><span data-ttu-id="baff3-114">32 KB</span><span class="sxs-lookup"><span data-stu-id="baff3-114">32 KB</span></span></strong></p></li>
<li><p><strong><span data-ttu-id="baff3-115">64 KB</span><span class="sxs-lookup"><span data-stu-id="baff3-115">64 KB</span></span></strong></p></li>
</ul>
<div class="alert">
<strong><span data-ttu-id="baff3-116">注意</span><span class="sxs-lookup"><span data-stu-id="baff3-116">Note</span></span></strong><br/><p><span data-ttu-id="baff3-117">选择块大小时，请考虑 SFT 文件的大小和你的网络带宽。</span><span class="sxs-lookup"><span data-stu-id="baff3-117">When you select a block size, consider the size of the SFT file and your network bandwidth.</span></span> <span data-ttu-id="baff3-118">块大小较小的文件需要花费较长时间才能通过网络传输，但占用带宽较少。</span><span class="sxs-lookup"><span data-stu-id="baff3-118">A file with a smaller block size takes longer to stream over the network but is less bandwidth-intensive.</span></span> <span data-ttu-id="baff3-119">块大小较大的文件可能会更快地传输，但它们会占用更多的网络带宽。</span><span class="sxs-lookup"><span data-stu-id="baff3-119">Files with larger block sizes might stream faster, but they use more network bandwidth.</span></span> <span data-ttu-id="baff3-120">通过实验，你可以发现网络上的流式处理应用程序的最佳块大小。</span><span class="sxs-lookup"><span data-stu-id="baff3-120">Through experimentation, you can discover the optimum block size for streaming applications on your network.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="baff3-121">在监视期间启用 Microsoft 更新</span><span class="sxs-lookup"><span data-stu-id="baff3-121">Enable Microsoft Update During Monitoring</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="baff3-122">允许在排序向导&#39;s 监视阶段安装 Microsoft 更新。</span><span class="sxs-lookup"><span data-stu-id="baff3-122">Enables installation of Microsoft Updates during the Sequencing Wizard&#39;s monitoring phase.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="baff3-123">变基 Dll</span><span class="sxs-lookup"><span data-stu-id="baff3-123">Rebase DLLs</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="baff3-124">允许将支持的动态链接库重新映射到 RAM 中的连续空间，从而节省内存并提高性能。</span><span class="sxs-lookup"><span data-stu-id="baff3-124">Enables remapping of supported dynamic-link libraries to a contiguous space in RAM, saving memory and improving performance.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="baff3-125">后退</span><span class="sxs-lookup"><span data-stu-id="baff3-125">Back</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="baff3-126">访问排序向导&#39;s 上一页。</span><span class="sxs-lookup"><span data-stu-id="baff3-126">Accesses the Sequencing Wizard&#39;s previous page.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="baff3-127">下一个</span><span class="sxs-lookup"><span data-stu-id="baff3-127">Next</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="baff3-128">访问顺序向导&#39;s 下一页。</span><span class="sxs-lookup"><span data-stu-id="baff3-128">Accesses the Sequencing Wizard&#39;s next page.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="baff3-129">取消</span><span class="sxs-lookup"><span data-stu-id="baff3-129">Cancel</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="baff3-130">序列向导的终止操作。</span><span class="sxs-lookup"><span data-stu-id="baff3-130">Terminates operation of the Sequencing Wizard.</span></span></p></td>
</tr>
</tbody>
</table>



<span data-ttu-id="baff3-131">\ [模板令牌值 \]</span><span class="sxs-lookup"><span data-stu-id="baff3-131">\[Template Token Value\]</span></span>

<span data-ttu-id="baff3-132">使用 App-v 顺序向导的 "**高级选项**" 页，为要排序的应用程序指定高级选项。</span><span class="sxs-lookup"><span data-stu-id="baff3-132">Use the **Advanced Options** page of the App-V Sequencing Wizard to specify advanced options for the application you are sequencing.</span></span> <span data-ttu-id="baff3-133">此页面包含下表中所述的元素。</span><span class="sxs-lookup"><span data-stu-id="baff3-133">This page contains the elements described in the following table.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="baff3-134">名称</span><span class="sxs-lookup"><span data-stu-id="baff3-134">Name</span></span></th>
<th align="left"><span data-ttu-id="baff3-135">描述</span><span class="sxs-lookup"><span data-stu-id="baff3-135">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="baff3-136">允许 Microsoft 更新在监视期间运行</span><span class="sxs-lookup"><span data-stu-id="baff3-136">Allow Microsoft Update to run during monitoring</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="baff3-137">指定在应用程序排序期间监视阶段是否将软件更新应用于应用程序。</span><span class="sxs-lookup"><span data-stu-id="baff3-137">Specifies whether software updates will be applied to the application during the monitoring phase of application sequencing.</span></span> <span data-ttu-id="baff3-138">如果需要更新才能成功完成应用程序安装，此选项将很有帮助。</span><span class="sxs-lookup"><span data-stu-id="baff3-138">This option is helpful if updates are required to successfully complete the application installation.</span></span> <span data-ttu-id="baff3-139">默认情况下，此选项处于未选中状态。</span><span class="sxs-lookup"><span data-stu-id="baff3-139">This option is not selected by default.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="baff3-140">变基 Dll</span><span class="sxs-lookup"><span data-stu-id="baff3-140">Rebase Dlls</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="baff3-141">允许将支持的动态链接库重新映射到 RAM 中的连续空间。</span><span class="sxs-lookup"><span data-stu-id="baff3-141">Enables remapping of supported dynamic-link libraries to a contiguous space in RAM.</span></span> <span data-ttu-id="baff3-142">选择此选项可帮助管理内存和提高应用程序性能。</span><span class="sxs-lookup"><span data-stu-id="baff3-142">Selecting this option can help manage memory and improve application performance.</span></span> <span data-ttu-id="baff3-143">默认情况下，此选项处于未选中状态。</span><span class="sxs-lookup"><span data-stu-id="baff3-143">This option is not selected by default.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="baff3-144">后退</span><span class="sxs-lookup"><span data-stu-id="baff3-144">Back</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="baff3-145">转到向导的上一页。</span><span class="sxs-lookup"><span data-stu-id="baff3-145">Goes to the previous page of the wizard.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="baff3-146">下一个</span><span class="sxs-lookup"><span data-stu-id="baff3-146">Next</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="baff3-147">转到向导的下一页。</span><span class="sxs-lookup"><span data-stu-id="baff3-147">Goes to the next page of the wizard.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="baff3-148">取消</span><span class="sxs-lookup"><span data-stu-id="baff3-148">Cancel</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="baff3-149">放弃设置并退出向导。</span><span class="sxs-lookup"><span data-stu-id="baff3-149">Discards the settings and exits the wizard.</span></span></p></td>
</tr>
</tbody>
</table>



<span data-ttu-id="baff3-150">\ [模板令牌值 \]</span><span class="sxs-lookup"><span data-stu-id="baff3-150">\[Template Token Value\]</span></span>

## <span data-ttu-id="baff3-151">相关主题</span><span class="sxs-lookup"><span data-stu-id="baff3-151">Related topics</span></span>


[<span data-ttu-id="baff3-152">序列化向导</span><span class="sxs-lookup"><span data-stu-id="baff3-152">Sequencing Wizard</span></span>](sequencing-wizard.md)









