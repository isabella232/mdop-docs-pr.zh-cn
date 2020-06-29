---
title: 确定 MED-V 工作区的数量和类型
description: 确定 MED-V 工作区的数量和类型
author: dansimp
ms.assetid: 11642253-6b1f-4c4a-a11e-48d8a360e1ea
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e0c9ed4b0ce92d0ca752525b847405bbce90a270
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804133"
---
# <span data-ttu-id="f2175-103">确定 MED-V 工作区的数量和类型</span><span class="sxs-lookup"><span data-stu-id="f2175-103">Identifying the Number and Types of MED-V Workspaces</span></span>


<span data-ttu-id="f2175-104">MED-V 创建一个虚拟环境，用于运行需要 Windows XP 的应用程序，或者需要与主机上的版本不同的 Internet Explorer 版本。</span><span class="sxs-lookup"><span data-stu-id="f2175-104">MED-V creates a virtual environment for running applications that require Windows XP or that require a version of Internet Explorer that differs from the version on the host computer.</span></span> <span data-ttu-id="f2175-105">此虚拟环境称为 MED-V 工作区。</span><span class="sxs-lookup"><span data-stu-id="f2175-105">This virtual environment is known as a MED-V workspace.</span></span>

<span data-ttu-id="f2175-106">根据你的组织在迁移到 Windows 7 时所面临的应用程序兼容性要求，只有特定用户或部门可能需要 MED-V 工作区。</span><span class="sxs-lookup"><span data-stu-id="f2175-106">Depending on the application compatibility requirements faced by your organization as you migrate to Windows 7, only certain users or departments might require MED-V workspaces.</span></span> <span data-ttu-id="f2175-107">在规划部署时，必须确定企业中所需的 MED-V 工作区的数量。</span><span class="sxs-lookup"><span data-stu-id="f2175-107">As you plan your deployment, you have to determine the number of MED-V workspaces required in your enterprise.</span></span> <span data-ttu-id="f2175-108">你还必须定义每个 MED-V 工作区的要求。</span><span class="sxs-lookup"><span data-stu-id="f2175-108">You also have to define the requirements of each MED-V workspace.</span></span>

## <span data-ttu-id="f2175-109">标识 MED-V 工作区的数量和类型</span><span class="sxs-lookup"><span data-stu-id="f2175-109">Identify the Number and Types of MED-V Workspaces</span></span>


<span data-ttu-id="f2175-110">确定你的企业中将为其创建 MED-V 工作区的计算机和组。</span><span class="sxs-lookup"><span data-stu-id="f2175-110">Identify the computers and groups in your enterprise for which you will be creating MED-V workspaces.</span></span> <span data-ttu-id="f2175-111">通常情况下，这些用户需要访问无法迁移到 Windows 7 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="f2175-111">Typically, these are the users who require access to those applications that cannot be migrated to Windows 7.</span></span> <span data-ttu-id="f2175-112">标识无法迁移的应用程序和需要 MED-V 工作区才能运行这些应用程序的用户。</span><span class="sxs-lookup"><span data-stu-id="f2175-112">Identify those applications that cannot be migrated and the users who require a MED-V workspace to run these applications.</span></span>

<span data-ttu-id="f2175-113">你可能还具有尚未针对 Windows 7 进行优化的 intranet 地址。</span><span class="sxs-lookup"><span data-stu-id="f2175-113">You might also have intranet addresses that have not yet been optimized for Windows 7.</span></span> <span data-ttu-id="f2175-114">MED-V 工作区提供了 Internet Explorer 浏览器，最终用户可以通过该浏览器更好地访问尚未准备好用于迁移到 Windows 7 的这些 web 地址。</span><span class="sxs-lookup"><span data-stu-id="f2175-114">The MED-V workspace provides an Internet Explorer browser through which end users can better access those web addresses that are not yet ready for the migration to Windows 7.</span></span> <span data-ttu-id="f2175-115">当你准备和规划 MED-V 部署时，你将必须标识和编译 URL 地址列表，以便从主机上的 Internet Explorer 重定向到 MED-V 工作区中的 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="f2175-115">As you are preparing and planning your MED-V deployment, you will have to identify and compile a list of the URL addresses to redirect from Internet Explorer on the host computer to Internet Explorer in the MED-V workspace.</span></span>

<span data-ttu-id="f2175-116">最后，你必须评估磁盘空间需求。</span><span class="sxs-lookup"><span data-stu-id="f2175-116">Finally, you have to evaluate your disk space requirements.</span></span> <span data-ttu-id="f2175-117">大多数 MED-V 工作区都是2千兆字节（GB）或更大。</span><span class="sxs-lookup"><span data-stu-id="f2175-117">Most MED-V workspaces are 2 gigabytes (GB) or larger.</span></span> <span data-ttu-id="f2175-118">系统上的可用磁盘空间可以快速使用，具体取决于用户数和 MED-V 的配置。</span><span class="sxs-lookup"><span data-stu-id="f2175-118">The available disk space on a system can be consumed quickly, depending on the number of users and the configuration of MED-V.</span></span> <span data-ttu-id="f2175-119">此外，贵公司的首选分发方式可能需要额外的空间。</span><span class="sxs-lookup"><span data-stu-id="f2175-119">Also, your company’s preferred method of distribution can require additional space.</span></span> <span data-ttu-id="f2175-120">通常，你应该为 MED-V 工作区释放至少 10 GB 的磁盘空间，但这种情况会有所不同，具体取决于图像的大小。</span><span class="sxs-lookup"><span data-stu-id="f2175-120">Generally, you should free a minimum of 10 GB of disk space for a MED-V workspace, but this varies greatly, depending on the size of the image.</span></span>

### <span data-ttu-id="f2175-121">计算 MED-V 工作区的磁盘空间要求</span><span class="sxs-lookup"><span data-stu-id="f2175-121">Calculate the Disk Space Requirements for MED-V Workspaces</span></span>

<span data-ttu-id="f2175-122">MED-V 工作区需要内存和磁盘空间来自安装它的主机。</span><span class="sxs-lookup"><span data-stu-id="f2175-122">A MED-V workspace requires memory and disk space from the host computer on which it is installed.</span></span> <span data-ttu-id="f2175-123">主机上至少需要 2 GB 的磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="f2175-123">At a minimum, 2 GB of disk space are required on the host.</span></span> <span data-ttu-id="f2175-124">磁盘空间是可变的，取决于用户的 MED-V 工作区中的应用程序和数据的数量。</span><span class="sxs-lookup"><span data-stu-id="f2175-124">Disk space is variable and depends on the number of applications and the data in a user’s MED-V workspace.</span></span>

<span data-ttu-id="f2175-125">我们建议最少 10 GB 的磁盘空间用于 MED-V。</span><span class="sxs-lookup"><span data-stu-id="f2175-125">We recommend a minimum of 10 GB of disk space for MED-V.</span></span> <span data-ttu-id="f2175-126">此金额允许基本 Windows XP 工作区和某些基本安装的应用程序和 web 重定向。</span><span class="sxs-lookup"><span data-stu-id="f2175-126">This amount allows for a basic Windows XP workspace and some basic installed applications and web redirection.</span></span> <span data-ttu-id="f2175-127">它还提供主机交换驱动器的可用空间。</span><span class="sxs-lookup"><span data-stu-id="f2175-127">It also provides available space for the host swap drive.</span></span> <span data-ttu-id="f2175-128">在基本配置中，MED-V 和单个部署的 MED-V 工作区最多可使用6到 8 GB。</span><span class="sxs-lookup"><span data-stu-id="f2175-128">In a basic configuration, MED-V and a single deployed MED-V workspace consume as much as 6 to 8 GB.</span></span> <span data-ttu-id="f2175-129">如果在 MED-V 工作区上包含许多应用程序，或者每台计算机有多个用户，则可以使用以下计算更准确地确定 MED-V 工作区所需的磁盘空间：</span><span class="sxs-lookup"><span data-stu-id="f2175-129">If you include lots of applications on the MED-V workspace or have more than one user per computer, then you can use the following calculation to more accurately determine the disk space your MED-V workspace requires:</span></span>

*<span data-ttu-id="f2175-130">基本 VHD + （每台计算机 x 的用户数（磁盘差异 + 已保存状态））</span><span class="sxs-lookup"><span data-stu-id="f2175-130">Base VHD + (User per computer x (Difference Disk + Saved State))</span></span>*

<span data-ttu-id="f2175-131">若要计算所需的磁盘空间，请确定以下各项：</span><span class="sxs-lookup"><span data-stu-id="f2175-131">To calculate the required disk space, determine the following:</span></span>

-   <span data-ttu-id="f2175-132">**基本 VHD 的大小**-用于创建 med-v 工作区的虚拟硬盘。</span><span class="sxs-lookup"><span data-stu-id="f2175-132">**Size of the base VHD** – the virtual hard disk that was used to create the MED-V workspace.</span></span>

    <span data-ttu-id="f2175-133">**重要提示** 不要对计算使用 medv 文件大小，因为 medv 文件已压缩。</span><span class="sxs-lookup"><span data-stu-id="f2175-133">**Important** Do not use the .medv file size for your calculation because the .medv file is compressed.</span></span>

     

-   <span data-ttu-id="f2175-134">**每台计算机的用户数**-med-v 为计算机上的每个用户创建了一个 med-v 工作区;在每个用户登录和创建 MED-V 工作区时，MED-V 工作区会占用磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="f2175-134">**Users per computer** – MED-V creates a MED-V workspace for each user on a computer; the MED-V workspace consumes disk space as each user logs on and the MED-V workspace is created.</span></span>

-   <span data-ttu-id="f2175-135">**差异磁盘的大小**-用于跟踪与基本 VHD 之间的差异。</span><span class="sxs-lookup"><span data-stu-id="f2175-135">**Size of the differencing disk** – used to track the difference from the base VHD.</span></span> <span data-ttu-id="f2175-136">此大小因你将应用程序和软件更新添加到虚拟硬盘而不同。</span><span class="sxs-lookup"><span data-stu-id="f2175-136">This size varies as you add applications and software updates to the virtual hard disk.</span></span> <span data-ttu-id="f2175-137">第一次启动 MED-V 时，将为每个 MED-V 用户创建差异磁盘。</span><span class="sxs-lookup"><span data-stu-id="f2175-137">A differencing disk is created for each MED-V user when they start MED-V for the first time.</span></span>

-   <span data-ttu-id="f2175-138">**已保存状态文件的大小**-用于维护虚拟机中的状态。</span><span class="sxs-lookup"><span data-stu-id="f2175-138">**Size of the Saved State file** – used to maintain state in the virtual machine.</span></span> <span data-ttu-id="f2175-139">通常，这比分配给虚拟机的 RAM 稍大一些。</span><span class="sxs-lookup"><span data-stu-id="f2175-139">Typically, this is just a bit larger than the allocated RAM for the virtual machine.</span></span> <span data-ttu-id="f2175-140">例如，分配的 1 GB RAM 将创建一个大约 1081000 KB 的文件。</span><span class="sxs-lookup"><span data-stu-id="f2175-140">For example, 1 GB of RAM allocated creates a file about 1,081,000 KB.</span></span>

<span data-ttu-id="f2175-141">以下示例显示基于具有 2.6 GB 虚拟硬盘的 MED-V 工作区的三个用户的计算：</span><span class="sxs-lookup"><span data-stu-id="f2175-141">The following example shows a calculation based on three users of a MED-V workspace that has a 2.6 GB virtual hard disk:</span></span>

*<span data-ttu-id="f2175-142">2.6 gb + （3 x （1.5 gb + 1gb）） = 10.1 gb</span><span class="sxs-lookup"><span data-stu-id="f2175-142">2.6gb + (3 x (1.5gb + 1gb)) = 10.1gb</span></span>*

<span data-ttu-id="f2175-143">**注意** MED-V 最佳做法是使用实验室部署来验证要求，从而计算所需的空间。</span><span class="sxs-lookup"><span data-stu-id="f2175-143">**Note** A MED-V best practice is to calculate the required space by using a lab deployment to validate the requirements.</span></span>

 

### <span data-ttu-id="f2175-144">找到文件以确定文件大小</span><span class="sxs-lookup"><span data-stu-id="f2175-144">Locate the Files to Determine File Size</span></span>

<span data-ttu-id="f2175-145">以下位置包含计算机和用户设置的文件：</span><span class="sxs-lookup"><span data-stu-id="f2175-145">The following locations contain the files for the computer and user settings:</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="f2175-146">类型</span><span class="sxs-lookup"><span data-stu-id="f2175-146">Type</span></span></th>
<th align="left"><span data-ttu-id="f2175-147">位置</span><span class="sxs-lookup"><span data-stu-id="f2175-147">Location</span></span></th>
<th align="left"><span data-ttu-id="f2175-148">文件</span><span class="sxs-lookup"><span data-stu-id="f2175-148">Files</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f2175-149">基本 VHD</span><span class="sxs-lookup"><span data-stu-id="f2175-149">Base VHD</span></span></p></td>
<td align="left"><p><span data-ttu-id="f2175-150">%ProgramData%\Microsoft\Medv\Workspace</span><span class="sxs-lookup"><span data-stu-id="f2175-150">%ProgramData%\Microsoft\Medv\Workspace</span></span></p></td>
<td align="left"><p><em><span data-ttu-id="f2175-151">InternalName </em> -其中 <em> InternalName </em> 是你在 Med-v 工作区包装程序中选择的虚拟硬盘的名称。</span><span class="sxs-lookup"><span data-stu-id="f2175-151">InternalName</em>.vhd - Where <em>InternalName</em> is the name of the virtual hard disk that you selected in the MED-V Workspace Packager.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f2175-152">差异磁盘</span><span class="sxs-lookup"><span data-stu-id="f2175-152">Differencing Disk</span></span></p></td>
<td align="left"><p><span data-ttu-id="f2175-153">%LocalAppData%\Microsoft\MEDV\v2\Virtual 计算机</span><span class="sxs-lookup"><span data-stu-id="f2175-153">%LocalAppData%\Microsoft\MEDV\v2\Virtual Machines</span></span></p></td>
<td align="left"><p><em><span data-ttu-id="f2175-154">WorkspaceName </em></span><span class="sxs-lookup"><span data-stu-id="f2175-154">WorkspaceName</em>.vhd</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f2175-155">已保存状态文件</span><span class="sxs-lookup"><span data-stu-id="f2175-155">Saved State File</span></span></p></td>
<td align="left"><p><span data-ttu-id="f2175-156">%LocalAppData%\Microsoft\MEDV\v2\Virtual 计算机</span><span class="sxs-lookup"><span data-stu-id="f2175-156">%LocalAppData%\Microsoft\MEDV\v2\Virtual Machines</span></span></p></td>
<td align="left"><p><em><span data-ttu-id="f2175-157">WorkspaceName </em> vsv</span><span class="sxs-lookup"><span data-stu-id="f2175-157">WorkspaceName</em>.vsv</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="f2175-158">计算共享的 MED-V 工作区的磁盘空间要求</span><span class="sxs-lookup"><span data-stu-id="f2175-158">Calculate the Disk Space Requirements for Shared MED-V Workspaces</span></span>

<span data-ttu-id="f2175-159">如果你在一台计算机上计算共享的 MED-V 工作区部署，则你的计算中的每台计算机的用户数始终为 "1"，因为 MED-V 仅为所有用户配置单个差异磁盘。</span><span class="sxs-lookup"><span data-stu-id="f2175-159">If you are calculating for a shared MED-V workspace deployment on a single computer, then the number of users per computer in your calculation is always “1” because MED-V only configures a single differencing disk for all users.</span></span>

<span data-ttu-id="f2175-160">你可以在%ProgramData%\\Microsoft\\Medv\\AllUsers. 中找到共享的 MED-V 工作区的差异磁盘和已保存状态文件</span><span class="sxs-lookup"><span data-stu-id="f2175-160">You can find the differencing disk and the saved state file for shared MED-V workspaces in %ProgramData%\\Microsoft\\Medv\\AllUsers.</span></span>

## <span data-ttu-id="f2175-161">相关主题</span><span class="sxs-lookup"><span data-stu-id="f2175-161">Related topics</span></span>


[<span data-ttu-id="f2175-162">定义和规划 MED-V 部署</span><span class="sxs-lookup"><span data-stu-id="f2175-162">Define and Plan your MED-V Deployment</span></span>](define-and-plan-your-med-v-deployment.md)

[<span data-ttu-id="f2175-163">规划 MED-V</span><span class="sxs-lookup"><span data-stu-id="f2175-163">Planning for MED-V</span></span>](planning-for-med-v.md)

 

 





