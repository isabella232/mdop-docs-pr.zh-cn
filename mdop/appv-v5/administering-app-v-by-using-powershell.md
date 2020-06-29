---
title: 使用 PowerShell 管理 App-V
description: 使用 PowerShell 管理 App-V
author: dansimp
ms.assetid: 1ff4686a-1e19-4eff-b648-ada091281094
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0e7f9171e0ac5589d8f1935e715dfdb9c349192d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798651"
---
# <span data-ttu-id="bc76d-103">使用 PowerShell 管理 App-V</span><span class="sxs-lookup"><span data-stu-id="bc76d-103">Administering App-V by Using PowerShell</span></span>


<span data-ttu-id="bc76d-104">Microsoft Application Virtualization （App-v）5.0 提供 Windows PowerShell cmdlet，此 cmdlet 可帮助管理员执行各种应用 V 5.0 任务。</span><span class="sxs-lookup"><span data-stu-id="bc76d-104">Microsoft Application Virtualization (App-V) 5.0 provides Windows PowerShell cmdlets, which can help administrators perform various App-V 5.0 tasks.</span></span> <span data-ttu-id="bc76d-105">以下部分提供了有关将 PowerShell 与 App-v 5.0 结合使用的详细信息。</span><span class="sxs-lookup"><span data-stu-id="bc76d-105">The following sections provide more information about using PowerShell with App-V 5.0.</span></span>

## <span data-ttu-id="bc76d-106">如何使用 PowerShell 管理 app-v 5。0</span><span class="sxs-lookup"><span data-stu-id="bc76d-106">How to administer App-V 5.0 by using PowerShell</span></span>


<span data-ttu-id="bc76d-107">使用以下 PowerShell 过程执行各种应用程序 V 5.0 任务。</span><span class="sxs-lookup"><span data-stu-id="bc76d-107">Use the following PowerShell procedures to perform various App-V 5.0 tasks.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="bc76d-108">名称</span><span class="sxs-lookup"><span data-stu-id="bc76d-108">Name</span></span></th>
<th align="left"><span data-ttu-id="bc76d-109">描述</span><span class="sxs-lookup"><span data-stu-id="bc76d-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><a href="how-to-load-the-powershell-cmdlets-and-get-cmdlet-help-50-sp3.md" data-raw-source="[How to Load the PowerShell Cmdlets and Get Cmdlet Help](how-to-load-the-powershell-cmdlets-and-get-cmdlet-help-50-sp3.md)"><span data-ttu-id="bc76d-110">如何加载 PowerShell Cmdlet 和获取 Cmdlet 帮助</span><span class="sxs-lookup"><span data-stu-id="bc76d-110">How to Load the PowerShell Cmdlets and Get Cmdlet Help</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="bc76d-111">介绍如何安装 PowerShell cmdlet 和查找 cmdlet 帮助和示例。</span><span class="sxs-lookup"><span data-stu-id="bc76d-111">Describes how to install the PowerShell cmdlets and find cmdlet help and examples.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md" data-raw-source="[How to Manage App-V 5.0 Packages Running on a Stand-Alone Computer by Using PowerShell](how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md)"><span data-ttu-id="bc76d-112">如何使用 PowerShell 管理在独立计算机上运行的 App-V 5.0 程序包</span><span class="sxs-lookup"><span data-stu-id="bc76d-112">How to Manage App-V 5.0 Packages Running on a Stand-Alone Computer by Using PowerShell</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="bc76d-113">介绍如何使用 PowerShell 管理独立计算机上的客户端程序包生命周期。</span><span class="sxs-lookup"><span data-stu-id="bc76d-113">Describes how to manage the client package lifecycle on a stand-alone computer using PowerShell.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="how-to-manage-connection-groups-on-a-stand-alone-computer-by-using-powershell.md" data-raw-source="[How to Manage Connection Groups on a Stand-alone Computer by Using PowerShell](how-to-manage-connection-groups-on-a-stand-alone-computer-by-using-powershell.md)"><span data-ttu-id="bc76d-114">如何使用 PowerShell 管理独立计算机上的连接组</span><span class="sxs-lookup"><span data-stu-id="bc76d-114">How to Manage Connection Groups on a Stand-alone Computer by Using PowerShell</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="bc76d-115">介绍如何使用 PowerShell 管理连接组。</span><span class="sxs-lookup"><span data-stu-id="bc76d-115">Describes how to manage connection groups using PowerShell.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="how-to-modify-client-configuration-by-using-powershell.md" data-raw-source="[How to Modify Client Configuration by Using PowerShell](how-to-modify-client-configuration-by-using-powershell.md)"><span data-ttu-id="bc76d-116">如何使用 PowerShell 修改客户端配置</span><span class="sxs-lookup"><span data-stu-id="bc76d-116">How to Modify Client Configuration by Using PowerShell</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="bc76d-117">介绍如何使用 PowerShell 修改客户端。</span><span class="sxs-lookup"><span data-stu-id="bc76d-117">Describes how to modify the client using PowerShell.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="how-to-apply-the-user-configuration-file-by-using-powershell.md" data-raw-source="[How to Apply the User Configuration File by Using PowerShell](how-to-apply-the-user-configuration-file-by-using-powershell.md)"><span data-ttu-id="bc76d-118">如何使用 PowerShell 应用用户配置文件</span><span class="sxs-lookup"><span data-stu-id="bc76d-118">How to Apply the User Configuration File by Using PowerShell</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="bc76d-119">介绍如何使用 PowerShell 应用用户配置文件。</span><span class="sxs-lookup"><span data-stu-id="bc76d-119">Describes how to apply a user configuration file using PowerShell.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="how-to-apply-the-deployment-configuration-file-by-using-powershell.md" data-raw-source="[How to Apply the Deployment Configuration File by Using PowerShell](how-to-apply-the-deployment-configuration-file-by-using-powershell.md)"><span data-ttu-id="bc76d-120">如何使用 PowerShell 应用部署配置文件</span><span class="sxs-lookup"><span data-stu-id="bc76d-120">How to Apply the Deployment Configuration File by Using PowerShell</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="bc76d-121">介绍如何使用 PowerShell 应用部署配置文件。</span><span class="sxs-lookup"><span data-stu-id="bc76d-121">Describes how to apply a deployment configuration file using PowerShell.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="how-to-sequence-a-package--by-using-powershell-50.md" data-raw-source="[How to Sequence a Package by Using PowerShell](how-to-sequence-a-package--by-using-powershell-50.md)"><span data-ttu-id="bc76d-122">如何使用 PowerShell 对程序包进行排序</span><span class="sxs-lookup"><span data-stu-id="bc76d-122">How to Sequence a Package by Using PowerShell</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="bc76d-123">介绍如何使用 PowerShell 创建新的程序包。</span><span class="sxs-lookup"><span data-stu-id="bc76d-123">Describes how to create a new package using PowerShell.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="how-to-create-a-package-accelerator-by-using-powershell.md" data-raw-source="[How to Create a Package Accelerator by Using PowerShell](how-to-create-a-package-accelerator-by-using-powershell.md)"><span data-ttu-id="bc76d-124">如何使用 PowerShell 创建包加速器</span><span class="sxs-lookup"><span data-stu-id="bc76d-124">How to Create a Package Accelerator by Using PowerShell</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="bc76d-125">介绍如何使用 PowerShell 创建程序包加速器。</span><span class="sxs-lookup"><span data-stu-id="bc76d-125">Describes how to create a package accelerator using PowerShell.</span></span> <span data-ttu-id="bc76d-126">可以使用程序包加速器自动序列大型、复杂的应用程序。</span><span class="sxs-lookup"><span data-stu-id="bc76d-126">You can use package accelerators automatically sequence large, complex applications.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="how-to-enable-reporting-on-the-app-v-50-client-by-using-powershell.md" data-raw-source="[How to Enable Reporting on the App-V 5.0 Client by Using PowerShell](how-to-enable-reporting-on-the-app-v-50-client-by-using-powershell.md)"><span data-ttu-id="bc76d-127">如何使用 PowerShell 在 App-V 5.0 Client 上启用报告</span><span class="sxs-lookup"><span data-stu-id="bc76d-127">How to Enable Reporting on the App-V 5.0 Client by Using PowerShell</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="bc76d-128">介绍如何启用运行 App-v 5.0 的计算机发送报告信息。</span><span class="sxs-lookup"><span data-stu-id="bc76d-128">Describes how to enable the computer running the App-V 5.0 to send reporting information.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="how-to-install-the-app-v-databases-and-convert-the-associated-security-identifiers--by-using-powershell.md" data-raw-source="[How to Install the App-V Databases and Convert the Associated Security Identifiers by Using PowerShell](how-to-install-the-app-v-databases-and-convert-the-associated-security-identifiers--by-using-powershell.md)"><span data-ttu-id="bc76d-129">如何使用 PowerShell 安装 app-v 数据库并转换关联的安全标识符</span><span class="sxs-lookup"><span data-stu-id="bc76d-129">How to Install the App-V Databases and Convert the Associated Security Identifiers by Using PowerShell</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="bc76d-130">介绍如何获取帐户名称数组并将每个帐户名称转换为标准和十六进制格式的相应 SID。</span><span class="sxs-lookup"><span data-stu-id="bc76d-130">Describes how to take an array of account names and to convert each of them to the corresponding SID in standard and hexadecimal formats.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="bc76d-131">PowerShell 错误处理</span><span class="sxs-lookup"><span data-stu-id="bc76d-131">PowerShell Error Handling</span></span>


<span data-ttu-id="bc76d-132">有关 App-v 5.0 PowerShell 错误处理的信息，请使用下表。</span><span class="sxs-lookup"><span data-stu-id="bc76d-132">Use the following table for information about App-V 5.0 PowerShell error handling.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="bc76d-133">事件</span><span class="sxs-lookup"><span data-stu-id="bc76d-133">Event</span></span></th>
<th align="left"><span data-ttu-id="bc76d-134">操作</span><span class="sxs-lookup"><span data-stu-id="bc76d-134">Action</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bc76d-135">将 RollbackOnError 属性与嵌入式脚本结合使用</span><span class="sxs-lookup"><span data-stu-id="bc76d-135">Using the RollbackOnError attribute with embedded scripts</span></span></p></td>
<td align="left"><p><span data-ttu-id="bc76d-136">将 <strong> RollbackOnError </strong> 属性与嵌入式脚本配合使用时，将忽略以下事件的属性：</span><span class="sxs-lookup"><span data-stu-id="bc76d-136">When you use the <strong>RollbackOnError</strong> attribute with embedded scripts, the attribute is ignored for the following events:</span></span></p>
<ul>
<li><p><span data-ttu-id="bc76d-137">删除程序包</span><span class="sxs-lookup"><span data-stu-id="bc76d-137">Removing a package</span></span></p></li>
<li><p><span data-ttu-id="bc76d-138">取消发布程序包</span><span class="sxs-lookup"><span data-stu-id="bc76d-138">Unpublishing a package</span></span></p></li>
<li><p><span data-ttu-id="bc76d-139">终止虚拟环境</span><span class="sxs-lookup"><span data-stu-id="bc76d-139">Terminating a virtual environment</span></span></p></li>
<li><p><span data-ttu-id="bc76d-140">终止进程</span><span class="sxs-lookup"><span data-stu-id="bc76d-140">Terminating a process</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bc76d-141">程序包名称包含<strong>$</span><span class="sxs-lookup"><span data-stu-id="bc76d-141">Package name contains <strong>$</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="bc76d-142">如果程序包名称包含字符（ <strong> $ </strong> ），则必须使用单引号（ <strong> ' </strong> ），例如</span><span class="sxs-lookup"><span data-stu-id="bc76d-142">If a package name contains the character ( <strong>$</strong> ), you must use a single-quote ( <strong>‘</strong> ), for example,</span></span></p>
<p><strong><span data-ttu-id="bc76d-143">AppvClientPackage "Contoso $ 应用 appv"</span><span class="sxs-lookup"><span data-stu-id="bc76d-143">Add-AppvClientPackage ‘Contoso$App.appv’</span></span></strong></p></td>
</tr>
</tbody>
</table>

 






## <span data-ttu-id="bc76d-144">相关主题</span><span class="sxs-lookup"><span data-stu-id="bc76d-144">Related topics</span></span>


[<span data-ttu-id="bc76d-145">App-V 5.0 的操作</span><span class="sxs-lookup"><span data-stu-id="bc76d-145">Operations for App-V 5.0</span></span>](operations-for-app-v-50.md)

 

 





