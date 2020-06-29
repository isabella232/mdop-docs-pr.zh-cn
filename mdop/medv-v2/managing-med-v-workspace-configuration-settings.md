---
title: 管理 MED-V 工作区配置设置
description: 管理 MED-V 工作区配置设置
author: dansimp
ms.assetid: 517d04de-c31f-4b50-b2b3-5f8c312ed37b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 97add695f605b71547b564789cce07a1d58763f2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803912"
---
# <span data-ttu-id="85f5a-103">管理 MED-V 工作区配置设置</span><span class="sxs-lookup"><span data-stu-id="85f5a-103">Managing MED-V Workspace Configuration Settings</span></span>


<span data-ttu-id="85f5a-104">Microsoft 企业版桌面虚拟化（MED-V）2.0 将其配置设置存储在注册表中。</span><span class="sxs-lookup"><span data-stu-id="85f5a-104">Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 stores its configuration settings in the registry.</span></span> <span data-ttu-id="85f5a-105">我们在此处介绍的有关注册表的信息可以帮助你更好地管理 MED-V 服务。</span><span class="sxs-lookup"><span data-stu-id="85f5a-105">The information we include here about the registry may help you better manage your MED-V services.</span></span>

<span data-ttu-id="85f5a-106">在查找结果设置值时，MED-V 使用以下搜索路径：</span><span class="sxs-lookup"><span data-stu-id="85f5a-106">MED-V uses the following search path when looking for the resultant settings values:</span></span>

<span data-ttu-id="85f5a-107">MED-V 首先在计算机策略中查找。</span><span class="sxs-lookup"><span data-stu-id="85f5a-107">MED-V first looks in the machine policy.</span></span>

<span data-ttu-id="85f5a-108">如果找不到该值，则 MED-V 将在用户策略中查找。</span><span class="sxs-lookup"><span data-stu-id="85f5a-108">If the value is not found, MED-V looks in the user policy.</span></span>

<span data-ttu-id="85f5a-109">如果找不到该值，则 MED-V 将在 HKEY _LOCAL \ _MACHINE \\System 配置单元中查找。</span><span class="sxs-lookup"><span data-stu-id="85f5a-109">If the value is not found, MED-V looks in the HKEY\_LOCAL\_MACHINE\\System hive.</span></span>

<span data-ttu-id="85f5a-110">如果找不到该值，则 MED-V 将在 HKEY \ _CURRENT 用户注册表配置单元中查找。</span><span class="sxs-lookup"><span data-stu-id="85f5a-110">If the value is not found, MED-V looks in the HKEY\_CURRENT USER registry hive.</span></span>

<span data-ttu-id="85f5a-111">如果仍然找不到值，则 MED-V 使用默认值。</span><span class="sxs-lookup"><span data-stu-id="85f5a-111">If the value is still not found, MED-V uses the default.</span></span>

<span data-ttu-id="85f5a-112">通常，最佳做法是在 HKEY _LOCAL \ _MACHINE \\System 配置单元或计算机策略中设置值。</span><span class="sxs-lookup"><span data-stu-id="85f5a-112">A general best practice is to set the value in the HKEY\_LOCAL\_MACHINE\\System hive or in the machine policy.</span></span> <span data-ttu-id="85f5a-113">但是，如果希望最终用户能够配置特定设置，则应将其保留。</span><span class="sxs-lookup"><span data-stu-id="85f5a-113">But if you want the end user to be able to configure a particular setting, then you should leave it out.</span></span>

**<span data-ttu-id="85f5a-114">注意</span><span class="sxs-lookup"><span data-stu-id="85f5a-114">Note</span></span>**  
<span data-ttu-id="85f5a-115">在部署 MED-V 工作区之前，可以使用脚本编辑器更改 MED-V 工作区包装程序创建的 Windows PowerShell 脚本（ps1 文件）。</span><span class="sxs-lookup"><span data-stu-id="85f5a-115">Before you deploy your MED-V workspaces, you can use a script editor to change the Windows PowerShell script (.ps1 file) that the MED-V workspace packager created.</span></span> <span data-ttu-id="85f5a-116">有关详细信息，请参阅[使用 Windows PowerShell 配置高级设置](configuring-advanced-settings-by-using-windows-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="85f5a-116">For more information, see [Configuring Advanced Settings by Using Windows PowerShell](configuring-advanced-settings-by-using-windows-powershell.md).</span></span>

<span data-ttu-id="85f5a-117">部署 MED-V 工作区后，您可以通过编辑注册表项来更改某些 MED-V 配置设置。</span><span class="sxs-lookup"><span data-stu-id="85f5a-117">After you have deployed your MED-V workspaces, you can change certain MED-V configuration settings by editing the registry entries.</span></span>



<span data-ttu-id="85f5a-118">本部分列出了所有可配置的 MED-V 注册表项并解释其用法。</span><span class="sxs-lookup"><span data-stu-id="85f5a-118">This section lists all the configurable MED-V registry keys and explains their uses.</span></span>

## <span data-ttu-id="85f5a-119">诊断密钥</span><span class="sxs-lookup"><span data-stu-id="85f5a-119">Diagnostics Key</span></span>


<span data-ttu-id="85f5a-120">下表提供了与 HKEY _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\Medv\\v2\\Diagnostics 键相关联的注册表值的相关信息。</span><span class="sxs-lookup"><span data-stu-id="85f5a-120">The following table provides information about the registry values associated with the HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Medv\\v2\\Diagnostics key.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="85f5a-121">名称</span><span class="sxs-lookup"><span data-stu-id="85f5a-121">Name</span></span> </th>
<th align="left"><span data-ttu-id="85f5a-122">类型</span><span class="sxs-lookup"><span data-stu-id="85f5a-122">Type</span></span> </th>
<th align="left"><span data-ttu-id="85f5a-123">Data/Default</span><span class="sxs-lookup"><span data-stu-id="85f5a-123">Data/Default</span></span> </th>
<th align="left"><span data-ttu-id="85f5a-124">描述</span><span class="sxs-lookup"><span data-stu-id="85f5a-124">Description</span></span> </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="85f5a-125">EventLogLevel</span><span class="sxs-lookup"><span data-stu-id="85f5a-125">EventLogLevel</span></span> </p></td>
<td align="left"><p><span data-ttu-id="85f5a-126">DWORD</span><span class="sxs-lookup"><span data-stu-id="85f5a-126">DWORD</span></span> </p></td>
<td align="left"><p><span data-ttu-id="85f5a-127">默认值 = 3</span><span class="sxs-lookup"><span data-stu-id="85f5a-127">Default=3</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-128">事件日志中记录的信息类型。</span><span class="sxs-lookup"><span data-stu-id="85f5a-128">The type of information that is logged in the event log.</span></span> <span data-ttu-id="85f5a-129">级别包括以下内容：0（无）、1（错误）、2（警告）、3（信息）、4（调试）。</span><span class="sxs-lookup"><span data-stu-id="85f5a-129">Levels include the following: 0 (None), 1 (Error), 2 (Warning), 3 (Information), 4 (Debug).</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="85f5a-130">Fts 键</span><span class="sxs-lookup"><span data-stu-id="85f5a-130">Fts Key</span></span>


<span data-ttu-id="85f5a-131">下表提供了与 HKEY _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\Medv\\v2\\Fts 键相关联的注册表值的相关信息。</span><span class="sxs-lookup"><span data-stu-id="85f5a-131">The following table provides information about the registry values associated with the HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Medv\\v2\\Fts key.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="85f5a-132">名称</span><span class="sxs-lookup"><span data-stu-id="85f5a-132">Name</span></span></th>
<th align="left"><span data-ttu-id="85f5a-133">类型</span><span class="sxs-lookup"><span data-stu-id="85f5a-133">Type</span></span></th>
<th align="left"><span data-ttu-id="85f5a-134">Data/Default</span><span class="sxs-lookup"><span data-stu-id="85f5a-134">Data/Default</span></span></th>
<th align="left"><span data-ttu-id="85f5a-135">描述</span><span class="sxs-lookup"><span data-stu-id="85f5a-135">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="85f5a-136">AddUserToAdminGroupEnabled</span><span class="sxs-lookup"><span data-stu-id="85f5a-136">AddUserToAdminGroupEnabled</span></span> </p></td>
<td align="left"><p><span data-ttu-id="85f5a-137">DWORD</span><span class="sxs-lookup"><span data-stu-id="85f5a-137">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-138">默认值 = 0</span><span class="sxs-lookup"><span data-stu-id="85f5a-138">Default=0</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-139">配置首次设置是否自动将最终用户添加到管理员&#39;s 组。</span><span class="sxs-lookup"><span data-stu-id="85f5a-139">Configures whether first time setup automatically adds the end user to the administrator&#39;s group.</span></span> <span data-ttu-id="85f5a-140">0 = false;1 = true。</span><span class="sxs-lookup"><span data-stu-id="85f5a-140">0 = false; 1 = true.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="85f5a-141">0 = false：首次设置不会自动将最终用户添加到管理员&#39;s 组。</span><span class="sxs-lookup"><span data-stu-id="85f5a-141">0 = false: First time setup does not automatically add the end user to the administrator&#39;s group.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="85f5a-142">1 = true：首次设置会自动将最终用户添加到管理员&#39;s 组。</span><span class="sxs-lookup"><span data-stu-id="85f5a-142">1 = true: First time setup automatically adds the end user to the administrator&#39;s group.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="85f5a-143">ComputerNameMask</span><span class="sxs-lookup"><span data-stu-id="85f5a-143">ComputerNameMask</span></span> </p></td>
<td align="left"><p><span data-ttu-id="85f5a-144">SZ</span><span class="sxs-lookup"><span data-stu-id="85f5a-144">SZ</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-145">MEDV\*</span><span class="sxs-lookup"><span data-stu-id="85f5a-145">MEDV\*</span></span> </p></td>
<td align="left"><p><span data-ttu-id="85f5a-146">用于创建来宾虚拟机&#39;计算机名的计算机名称掩码。</span><span class="sxs-lookup"><span data-stu-id="85f5a-146">The computer name mask that is used to create the guest virtual machine&#39;s computer name.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="85f5a-147">掩码可以包含% username% 标签以插入用户名作为计算机名称的一部分。</span><span class="sxs-lookup"><span data-stu-id="85f5a-147">The mask can contain a %username% tag to insert the username as part of the computer name.</span></span> <span data-ttu-id="85f5a-148">同样，% hostname% 标签插入主计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="85f5a-148">Likewise, the %hostname% tag inserts the name of the host computer.</span></span></p>
<p><span data-ttu-id="85f5a-149">&quot; # &quot; 掩码中的每个字符替换为随机数字。</span><span class="sxs-lookup"><span data-stu-id="85f5a-149">Every &quot;#&quot; character in the mask is replaced by a random digit.</span></span> <span data-ttu-id="85f5a-150">掩码结尾处的星号（\*）字符将替换为随机字母数字字符。</span><span class="sxs-lookup"><span data-stu-id="85f5a-150">An asterisk (\*) character at the end of the mask is replaced by random alphanumeric characters.</span></span></p>
<p><span data-ttu-id="85f5a-151">可以使用方括号捕获% hostname% 和% 用户名% 中的特定数量的字符。</span><span class="sxs-lookup"><span data-stu-id="85f5a-151">A specific number of characters from %hostname% and %username% can be captured by using square brackets.</span></span> <span data-ttu-id="85f5a-152">例如， &quot; % 用户名% [3] &quot; 将使用用户名的前三个字符。</span><span class="sxs-lookup"><span data-stu-id="85f5a-152">For example, &quot;%username%[3]&quot; would use the first three characters of the username.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="85f5a-153">DeleteVMStateTimeout</span><span class="sxs-lookup"><span data-stu-id="85f5a-153">DeleteVMStateTimeout</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-154">DWORD</span><span class="sxs-lookup"><span data-stu-id="85f5a-154">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-155">默认值 = 90</span><span class="sxs-lookup"><span data-stu-id="85f5a-155">Default=90</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-156">首次设置尝试删除虚拟机时的超时值（以秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="85f5a-156">The time-out value, in seconds, when first time setup tries to delete the virtual machine.</span></span> <span data-ttu-id="85f5a-157">范围 = 0 到2147483647。</span><span class="sxs-lookup"><span data-stu-id="85f5a-157">Range = 0 to 2147483647.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="85f5a-158">DetachVfdTimeout</span><span class="sxs-lookup"><span data-stu-id="85f5a-158">DetachVfdTimeout</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-159">DWORD</span><span class="sxs-lookup"><span data-stu-id="85f5a-159">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-160">默认值 = 120</span><span class="sxs-lookup"><span data-stu-id="85f5a-160">Default=120</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-161">第一次设置尝试从虚拟机分离虚拟软盘的超时值（以秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="85f5a-161">The time-out value, in seconds, when first time setup tries to detach the virtual floppy disk from the virtual machine.</span></span> <span data-ttu-id="85f5a-162">范围 = 0 到2147483647。</span><span class="sxs-lookup"><span data-stu-id="85f5a-162">Range = 0 to 2147483647.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="85f5a-163">DialogUrl</span><span class="sxs-lookup"><span data-stu-id="85f5a-163">DialogUrl</span></span> </p></td>
<td align="left"><p><span data-ttu-id="85f5a-164">SZ</span><span class="sxs-lookup"><span data-stu-id="85f5a-164">SZ</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="85f5a-165">链接到内部网页且由首次设置对话框消息显示的可自定义 URL。</span><span class="sxs-lookup"><span data-stu-id="85f5a-165">Customizable URL that links to internal webpage and is displayed by first time setup dialog messages.</span></span> </p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="85f5a-166">ExplorerTimeout</span><span class="sxs-lookup"><span data-stu-id="85f5a-166">ExplorerTimeout</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-167">DWORD</span><span class="sxs-lookup"><span data-stu-id="85f5a-167">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-168">默认值 = 900</span><span class="sxs-lookup"><span data-stu-id="85f5a-168">Default=900</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-169">首次设置等待 Windows 资源管理器时的超时值（以秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="85f5a-169">The time-out value, in seconds, that first time setup waits for Windows Explorer.</span></span> <span data-ttu-id="85f5a-170">范围 = 0 到2147483647。</span><span class="sxs-lookup"><span data-stu-id="85f5a-170">Range = 0 to 2147483647.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="85f5a-171">FailureDialogMsg</span><span class="sxs-lookup"><span data-stu-id="85f5a-171">FailureDialogMsg</span></span> </p></td>
<td align="left"><p><span data-ttu-id="85f5a-172">MULTI_SZ</span><span class="sxs-lookup"><span data-stu-id="85f5a-172">MULTI_SZ</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-173">在资源文件中找到邮件</span><span class="sxs-lookup"><span data-stu-id="85f5a-173">Message is found in resource file</span></span> </p></td>
<td align="left"><p><span data-ttu-id="85f5a-174">首次设置无法完成时显示给最终用户的可自定义消息。</span><span class="sxs-lookup"><span data-stu-id="85f5a-174">Customizable message that is displayed to the end user when first time setup cannot be completed.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="85f5a-175">GiveUserGroupRightsMaxRetryCount</span><span class="sxs-lookup"><span data-stu-id="85f5a-175">GiveUserGroupRightsMaxRetryCount</span></span> </p></td>
<td align="left"><p><span data-ttu-id="85f5a-176">DWORD</span><span class="sxs-lookup"><span data-stu-id="85f5a-176">DWORD</span></span> </p></td>
<td align="left"><p><span data-ttu-id="85f5a-177">默认值 = 3</span><span class="sxs-lookup"><span data-stu-id="85f5a-177">Default=3</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-178">MED-V 尝试授予最终用户组权限的最大次数。</span><span class="sxs-lookup"><span data-stu-id="85f5a-178">The maximum number of times that MED-V tries to give an end user group rights.</span></span> <span data-ttu-id="85f5a-179">超过指定的重试值，并且不能成功授予最终用户组权限后，最有可能会导致虚拟机的预准备失败，然后受 MaxRetryCount 值的制约。</span><span class="sxs-lookup"><span data-stu-id="85f5a-179">Exceeding the specified retry value without being able to successfully give an end user group rights most likely causes a virtual machine preparation failure that is then subject to the MaxRetryCount value.</span></span> <span data-ttu-id="85f5a-180">范围 = 0 到2147483647。</span><span class="sxs-lookup"><span data-stu-id="85f5a-180">Range = 0 to 2147483647.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="85f5a-181">GiveUserGroupRightsTimeout</span><span class="sxs-lookup"><span data-stu-id="85f5a-181">GiveUserGroupRightsTimeout</span></span> </p></td>
<td align="left"><p><span data-ttu-id="85f5a-182">DWORD</span><span class="sxs-lookup"><span data-stu-id="85f5a-182">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-183">默认值 = 300</span><span class="sxs-lookup"><span data-stu-id="85f5a-183">Default=300</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-184">授予用户组权限的超时值（以秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="85f5a-184">The time-out value, in seconds, when giving a user group rights.</span></span> <span data-ttu-id="85f5a-185">范围 = 0 到2147483647。</span><span class="sxs-lookup"><span data-stu-id="85f5a-185">Range = 0 to 2147483647.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="85f5a-186">LogFilePaths</span><span class="sxs-lookup"><span data-stu-id="85f5a-186">LogFilePaths</span></span> </p></td>
<td align="left"><p><span data-ttu-id="85f5a-187">MULTI_SZ</span><span class="sxs-lookup"><span data-stu-id="85f5a-187">MULTI_SZ</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="85f5a-188">第一次设置期间的 MED-V 收集的日志文件路径的列表。</span><span class="sxs-lookup"><span data-stu-id="85f5a-188">A list of the log file paths that MED-V collects during first time setup.</span></span> </p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="85f5a-189">MaxPostponeTime</span><span class="sxs-lookup"><span data-stu-id="85f5a-189">MaxPostponeTime</span></span> </p></td>
<td align="left"><p><span data-ttu-id="85f5a-190">DWORD</span><span class="sxs-lookup"><span data-stu-id="85f5a-190">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-191">默认值 = 120</span><span class="sxs-lookup"><span data-stu-id="85f5a-191">Default=120</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-192">最终用户第一次可以延迟的最大小时数。</span><span class="sxs-lookup"><span data-stu-id="85f5a-192">The maximum number of hours that first time setup can be postponed by the end user.</span></span> <span data-ttu-id="85f5a-193">范围 = 0 到2147483647。</span><span class="sxs-lookup"><span data-stu-id="85f5a-193">Range = 0 to 2147483647.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="85f5a-194">MaxRetryCount</span><span class="sxs-lookup"><span data-stu-id="85f5a-194">MaxRetryCount</span></span> </p></td>
<td align="left"><p><span data-ttu-id="85f5a-195">DWORD</span><span class="sxs-lookup"><span data-stu-id="85f5a-195">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-196">默认值 = 3</span><span class="sxs-lookup"><span data-stu-id="85f5a-196">Default=3</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-197">如果每次尝试在软件错误之外的故障中停止，则 MED-V 尝试准备虚拟机的最大次数。</span><span class="sxs-lookup"><span data-stu-id="85f5a-197">The maximum number of times that MED-V tries to prepare a virtual machine if each attempt ends in a failure other than a software error.</span></span> <span data-ttu-id="85f5a-198">当虚拟机准备失败并且超过了首次设置重试的次数时，MED-V 将通知最终用户该故障，并且不会提供重试选项。</span><span class="sxs-lookup"><span data-stu-id="85f5a-198">When virtual machine preparation fails and the number of first time setup retries is exceeded, then MED-V informs the end user about the failure and does not give the option to retry.</span></span> <span data-ttu-id="85f5a-199">每次启动 MED-V 时，都会重新设置计数。</span><span class="sxs-lookup"><span data-stu-id="85f5a-199">The count is re-set every time that MED-V is started.</span></span> <span data-ttu-id="85f5a-200">范围 = 0 到2147483647。</span><span class="sxs-lookup"><span data-stu-id="85f5a-200">Range = 0 to 2147483647.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="85f5a-201">模式</span><span class="sxs-lookup"><span data-stu-id="85f5a-201">Mode</span></span> </p></td>
<td align="left"><p><span data-ttu-id="85f5a-202">SZ</span><span class="sxs-lookup"><span data-stu-id="85f5a-202">SZ</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-203">默认值 = 无人参与</span><span class="sxs-lookup"><span data-stu-id="85f5a-203">Default=Unattended</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-204">配置首次设置与用户交互的方式。</span><span class="sxs-lookup"><span data-stu-id="85f5a-204">Configures how first time setup interacts with the user.</span></span> <span data-ttu-id="85f5a-205">可能的值如下所示：</span><span class="sxs-lookup"><span data-stu-id="85f5a-205">Possible values are as follows:</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><strong><span data-ttu-id="85f5a-206">参加了.</span><span class="sxs-lookup"><span data-stu-id="85f5a-206">Attended.</span></span></strong> <span data-ttu-id="85f5a-207">最终用户在首次设置时必须输入信息。</span><span class="sxs-lookup"><span data-stu-id="85f5a-207">The end user must enter information during first time setup.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="85f5a-208">注意</span><span class="sxs-lookup"><span data-stu-id="85f5a-208">Note</span></span></strong><br/><p><span data-ttu-id="85f5a-209">如果你创建了 Sysprep.inf 文件，以便最小化安装需要用户输入才能完成，则你必须选择 " <strong> 有人参与 </strong> 模式" 或 "首次设置时可能出现问题"。</span><span class="sxs-lookup"><span data-stu-id="85f5a-209">If you created the Sysprep.inf file so that Mini-Setup requires user input to complete, then you must select <strong>Attended</strong> mode or problems might occur during first time setup.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><strong><span data-ttu-id="85f5a-210">无人参与 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="85f5a-210">Unattended</strong>.</span></span> <span data-ttu-id="85f5a-211">第一次设置期间，虚拟机不会向最终用户显示，但最终用户在首次启动设置之前会收到提示。</span><span class="sxs-lookup"><span data-stu-id="85f5a-211">The virtual machine is not shown to the end user during first time setup, but the end user is prompted before first time setup starts.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><strong><span data-ttu-id="85f5a-212">无声 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="85f5a-212">Silent</strong>.</span></span> <span data-ttu-id="85f5a-213">首次设置时，虚拟机不会显示给最终用户。</span><span class="sxs-lookup"><span data-stu-id="85f5a-213">The virtual machine is not shown to the end user at all during first time setup.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="85f5a-214">NonInteractiveRetryTimeoutInc</span><span class="sxs-lookup"><span data-stu-id="85f5a-214">NonInteractiveRetryTimeoutInc</span></span> </p></td>
<td align="left"><p><span data-ttu-id="85f5a-215">DWORD</span><span class="sxs-lookup"><span data-stu-id="85f5a-215">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-216">默认值 = 15</span><span class="sxs-lookup"><span data-stu-id="85f5a-216">Default=15</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-217">第一次必须在重新尝试安装程序时首次完成设置的超时值（以分钟为单位）。</span><span class="sxs-lookup"><span data-stu-id="85f5a-217">The time-out value, in minutes, that first time setup must be completed in first time setup interactive mode when re-attempting setup.</span></span> <span data-ttu-id="85f5a-218">范围 = 0 到2147483647。</span><span class="sxs-lookup"><span data-stu-id="85f5a-218">Range = 0 to 2147483647.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="85f5a-219">NonInteractiveTimeout</span><span class="sxs-lookup"><span data-stu-id="85f5a-219">NonInteractiveTimeout</span></span> </p></td>
<td align="left"><p><span data-ttu-id="85f5a-220">DWORD</span><span class="sxs-lookup"><span data-stu-id="85f5a-220">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-221">默认值 = 45</span><span class="sxs-lookup"><span data-stu-id="85f5a-221">Default=45</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-222">第一次必须在第一次设置交互模式时首次完成设置的超时值（以分钟为单位）。</span><span class="sxs-lookup"><span data-stu-id="85f5a-222">The time-out value, in minutes, that first time setup must be completed in first time setup interactive mode.</span></span> <span data-ttu-id="85f5a-223">范围 = 0 到2147483647。</span><span class="sxs-lookup"><span data-stu-id="85f5a-223">Range = 0 to 2147483647.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="85f5a-224">PostponeUtcDateTimeLimit</span><span class="sxs-lookup"><span data-stu-id="85f5a-224">PostponeUtcDateTimeLimit</span></span> </p></td>
<td align="left"><p><span data-ttu-id="85f5a-225">SZ</span><span class="sxs-lookup"><span data-stu-id="85f5a-225">SZ</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="85f5a-226">第一次可以延迟设置的日期和时间（采用 UTC 日期时间格式）。</span><span class="sxs-lookup"><span data-stu-id="85f5a-226">The date and time, in UTC DateTime format, that first time setup can be postponed.</span></span> <span data-ttu-id="85f5a-227">以 " &quot; 24 小时制" 标准的格式输入 yyyy hh： MM &quot; 和小时数。</span><span class="sxs-lookup"><span data-stu-id="85f5a-227">Enter in the format &quot;yyyy-MM-dd hh:mm&quot; with hours specified by using the 24-hour clock standard.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="85f5a-228">RetryDialogMsg</span><span class="sxs-lookup"><span data-stu-id="85f5a-228">RetryDialogMsg</span></span> </p></td>
<td align="left"><p><span data-ttu-id="85f5a-229">MULTI_SZ</span><span class="sxs-lookup"><span data-stu-id="85f5a-229">MULTI_SZ</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-230">在资源文件中找到邮件</span><span class="sxs-lookup"><span data-stu-id="85f5a-230">Message is found in resource file</span></span> </p></td>
<td align="left"><p><span data-ttu-id="85f5a-231">首次设置必须重新尝试设置时显示给最终用户的可自定义消息。</span><span class="sxs-lookup"><span data-stu-id="85f5a-231">Customizable message that is displayed to the end user when first time setup must re-attempt setup.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="85f5a-232">SetComputerNameEnabled</span><span class="sxs-lookup"><span data-stu-id="85f5a-232">SetComputerNameEnabled</span></span> </p></td>
<td align="left"><p><span data-ttu-id="85f5a-233">DWORD</span><span class="sxs-lookup"><span data-stu-id="85f5a-233">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-234">默认值 = 0</span><span class="sxs-lookup"><span data-stu-id="85f5a-234">Default=0</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-235">配置来宾中的 Sysprep.inf 文件的 [UserData] 部分下的 ComputerName 条目是否应根据指定的 ComputerNameMask 进行更新。</span><span class="sxs-lookup"><span data-stu-id="85f5a-235">Configures whether the ComputerName entry under the [UserData] section of the Sysprep.inf file in the guest should be updated according to the specified ComputerNameMask.</span></span>   <span data-ttu-id="85f5a-236">0 = false;1 = true。</span><span class="sxs-lookup"><span data-stu-id="85f5a-236">0 = false; 1 = true.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="85f5a-237">0 = false：不会根据 ComputerNameMask 更新 Sysprep.inf 文件中的 ComputerName 条目。</span><span class="sxs-lookup"><span data-stu-id="85f5a-237">0 = false: The ComputerName entry in the Sysprep.inf file is not updated according to the ComputerNameMask.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="85f5a-238">1 = true：将根据 ComputerNameMask 更新 Sysprep.inf 文件中的 ComputerName 条目。</span><span class="sxs-lookup"><span data-stu-id="85f5a-238">1 = true: The ComputerName entry in the Sysprep.inf file is updated according to the ComputerNameMask.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="85f5a-239">SetJoinDomainEnabled</span><span class="sxs-lookup"><span data-stu-id="85f5a-239">SetJoinDomainEnabled</span></span> </p></td>
<td align="left"><p><span data-ttu-id="85f5a-240">DWORD</span><span class="sxs-lookup"><span data-stu-id="85f5a-240">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-241">默认值 = 0</span><span class="sxs-lookup"><span data-stu-id="85f5a-241">Default=0</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-242">配置是否应更新来宾中 Sysprep.inf 文件的 [标识] 部分中的 JoinDomain 设置以匹配主机上的设置。</span><span class="sxs-lookup"><span data-stu-id="85f5a-242">Configures whether the JoinDomain setting under the [Identification] section of the Sysprep.inf file in the guest should be updated to match the settings on the host.</span></span>  <span data-ttu-id="85f5a-243">0 = false;1 = true。</span><span class="sxs-lookup"><span data-stu-id="85f5a-243">0 = false; 1 = true.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="85f5a-244">0 = false：不会更新 Sysprep.inf 文件中的 JoinDomain 设置以匹配主机上的设置。</span><span class="sxs-lookup"><span data-stu-id="85f5a-244">0 = false: The JoinDomain setting in the Sysprep.inf file is not updated to match the settings on the host.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="85f5a-245">1 = true： Sysprep.inf 文件中的 JoinDomain 设置会更新，以匹配主机上的设置。</span><span class="sxs-lookup"><span data-stu-id="85f5a-245">1 = true: The JoinDomain setting in the Sysprep.inf file is updated to match the settings on the host.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="85f5a-246">SetMachineObjectOUEnabled</span><span class="sxs-lookup"><span data-stu-id="85f5a-246">SetMachineObjectOUEnabled</span></span> </p></td>
<td align="left"><p><span data-ttu-id="85f5a-247">DWORD</span><span class="sxs-lookup"><span data-stu-id="85f5a-247">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-248">默认值 = 0</span><span class="sxs-lookup"><span data-stu-id="85f5a-248">Default=0</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-249">配置来宾中的 Sysprep.inf 文件的 [标识] 部分下的 MachineObjectOU 设置是否会更新，以匹配主机。</span><span class="sxs-lookup"><span data-stu-id="85f5a-249">Configures whether the MachineObjectOU setting under the [Identification] section of the Sysprep.inf file in the guest is updated to match the host.</span></span>  <span data-ttu-id="85f5a-250">0 = false;1 = true。</span><span class="sxs-lookup"><span data-stu-id="85f5a-250">0 = false; 1 = true.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="85f5a-251">0 = false：不会更新 Sysprep.inf 文件中的 MachineObjectOU 设置以匹配主机上的设置。</span><span class="sxs-lookup"><span data-stu-id="85f5a-251">0 = false: The MachineObjectOU setting in the Sysprep.inf file is not updated to match the settings on the host.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="85f5a-252">1 = true： Sysprep.inf 文件中的 MachineObjectOU 设置会更新，以匹配主机上的设置。</span><span class="sxs-lookup"><span data-stu-id="85f5a-252">1 = true: The MachineObjectOU setting in the Sysprep.inf file is updated to match the settings on the host.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="85f5a-253">SetRegionalSettingsEnabled</span><span class="sxs-lookup"><span data-stu-id="85f5a-253">SetRegionalSettingsEnabled</span></span> </p></td>
<td align="left"><p><span data-ttu-id="85f5a-254">DWORD</span><span class="sxs-lookup"><span data-stu-id="85f5a-254">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-255">默认值 = 0</span><span class="sxs-lookup"><span data-stu-id="85f5a-255">Default=0</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-256">配置来宾中的 Sysprep.inf 文件的 [RegionalSettings] 部分下的设置是否会更新，以匹配主机。</span><span class="sxs-lookup"><span data-stu-id="85f5a-256">Configures whether the settings under the [RegionalSettings] section of the Sysprep.inf file in the guest are updated to match the host.</span></span>  <span data-ttu-id="85f5a-257">0 = false;1 = true。</span><span class="sxs-lookup"><span data-stu-id="85f5a-257">0 = false; 1 = true.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="85f5a-258">注意</span><span class="sxs-lookup"><span data-stu-id="85f5a-258">Note</span></span></strong><br/><p><span data-ttu-id="85f5a-259">默认情况下，来宾中的时区设置始终与主机中的时区设置同步。</span><span class="sxs-lookup"><span data-stu-id="85f5a-259">By default, the setting for TimeZone in the guest is always synchronized with the TimeZone setting in the host.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="85f5a-260">0 = false：来宾中 Sysprep.inf 文件的 [RegionalSettings] 部分下的设置不会更新以匹配主机。</span><span class="sxs-lookup"><span data-stu-id="85f5a-260">0 = false: The settings under the [RegionalSettings] section of the Sysprep.inf file in the guest are not updated to match the host.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="85f5a-261">1 = true：来宾中 Sysprep.inf 文件的 [RegionalSettings] 部分下的设置已更新，以匹配主机。</span><span class="sxs-lookup"><span data-stu-id="85f5a-261">1 = true: The settings under the [RegionalSettings] section of the Sysprep.inf file in the guest are updated to match the host.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="85f5a-262">SetUserDataEnabled</span><span class="sxs-lookup"><span data-stu-id="85f5a-262">SetUserDataEnabled</span></span> </p></td>
<td align="left"><p><span data-ttu-id="85f5a-263">DWORD</span><span class="sxs-lookup"><span data-stu-id="85f5a-263">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-264">默认值 = 0</span><span class="sxs-lookup"><span data-stu-id="85f5a-264">Default=0</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-265">配置来宾中的 Sysprep.inf 文件的 [UserData] 部分下的 FullName 和 OrgName 设置是否会更新，以匹配主机上的设置。</span><span class="sxs-lookup"><span data-stu-id="85f5a-265">Configures whether the FullName and the OrgName settings under the [UserData] section of the Sysprep.inf file in the guest are updated to match the settings on the host.</span></span>  <span data-ttu-id="85f5a-266">0 = false;1 = true。</span><span class="sxs-lookup"><span data-stu-id="85f5a-266">0 = false; 1 = true.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="85f5a-267">0 = false：不会更新 Sysprep.inf 文件中的 FullName 和 OrgName 设置以匹配主机上的设置。</span><span class="sxs-lookup"><span data-stu-id="85f5a-267">0 = false: The FullName and OrgName settings in the Sysprep.inf file are not updated to match the settings on the host.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="85f5a-268">1 = true：将更新 Sysprep.inf 文件中的 FullName 和 OrgName 设置以匹配主机上的设置。</span><span class="sxs-lookup"><span data-stu-id="85f5a-268">1 = true: The FullName and OrgName settings in the Sysprep.inf file are updated to match the settings on the host.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="85f5a-269">StartDialogMsg</span><span class="sxs-lookup"><span data-stu-id="85f5a-269">StartDialogMsg</span></span> </p></td>
<td align="left"><p><span data-ttu-id="85f5a-270">MULTI_SZ</span><span class="sxs-lookup"><span data-stu-id="85f5a-270">MULTI_SZ</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-271">在资源文件中找到邮件</span><span class="sxs-lookup"><span data-stu-id="85f5a-271">Message is found in resource file</span></span> </p></td>
<td align="left"><p><span data-ttu-id="85f5a-272">可自定义的消息，在首次设置准备好开始时显示给最终用户。</span><span class="sxs-lookup"><span data-stu-id="85f5a-272">Customizable message that is displayed to the end user when first time setup is ready to start.</span></span> </p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="85f5a-273">TaskCancelTimeout</span><span class="sxs-lookup"><span data-stu-id="85f5a-273">TaskCancelTimeout</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-274">DWORD</span><span class="sxs-lookup"><span data-stu-id="85f5a-274">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-275">默认值 = 30</span><span class="sxs-lookup"><span data-stu-id="85f5a-275">Default=30</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-276">超时值（以秒为单位），在设置为取消操作的第一次等待来自虚拟机的响应时。</span><span class="sxs-lookup"><span data-stu-id="85f5a-276">The time-out value, in seconds, that first time setup waits for a response from the virtual machine for a Cancel operation.</span></span> <span data-ttu-id="85f5a-277">范围 = 0 到2147483647。</span><span class="sxs-lookup"><span data-stu-id="85f5a-277">Range = 0 to 2147483647.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="85f5a-278">TaskVMTurnOffTimeout</span><span class="sxs-lookup"><span data-stu-id="85f5a-278">TaskVMTurnOffTimeout</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-279">DWORD</span><span class="sxs-lookup"><span data-stu-id="85f5a-279">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-280">默认值 = 60</span><span class="sxs-lookup"><span data-stu-id="85f5a-280">Default=60</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-281">第一次设置等待虚拟机关闭的超时值（以秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="85f5a-281">The time-out value, in seconds, that first time setup waits for the virtual machine to shut down.</span></span> <span data-ttu-id="85f5a-282">范围 = 0 到2147483647。</span><span class="sxs-lookup"><span data-stu-id="85f5a-282">Range = 0 to 2147483647.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="85f5a-283">UpgradeTimeout</span><span class="sxs-lookup"><span data-stu-id="85f5a-283">UpgradeTimeout</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-284">DWORD</span><span class="sxs-lookup"><span data-stu-id="85f5a-284">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-285">默认值 = 600</span><span class="sxs-lookup"><span data-stu-id="85f5a-285">Default=600</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-286">尝试升级 MED-V 来宾代理软件超时前的时间（以秒为单位）。范围 = 0 到2147483647。</span><span class="sxs-lookup"><span data-stu-id="85f5a-286">The time, in seconds, before an attempted upgrade of the MED-V Guest Agent software times out. Range = 0 to 2147483647.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="85f5a-287">UserExperience 键</span><span class="sxs-lookup"><span data-stu-id="85f5a-287">UserExperience Key</span></span>


<span data-ttu-id="85f5a-288">下表提供了与 HKEY _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\Medv\\v2\\UserExperience 键和 HKEY \ _CURRENT \ _USER \\Software\\Microsoft\\Medv\\v2\\UserExperience 键相关联的注册表值的相关信息。</span><span class="sxs-lookup"><span data-stu-id="85f5a-288">The following table provides information about the registry values associated with the HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Medv\\v2\\UserExperience key and the HKEY\_CURRENT\_USER\\Software\\Microsoft\\Medv\\v2\\UserExperience key.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="85f5a-289">名称</span><span class="sxs-lookup"><span data-stu-id="85f5a-289">Name</span></span></th>
<th align="left"><span data-ttu-id="85f5a-290">类型</span><span class="sxs-lookup"><span data-stu-id="85f5a-290">Type</span></span></th>
<th align="left"><span data-ttu-id="85f5a-291">Data/Default</span><span class="sxs-lookup"><span data-stu-id="85f5a-291">Data/Default</span></span></th>
<th align="left"><span data-ttu-id="85f5a-292">描述</span><span class="sxs-lookup"><span data-stu-id="85f5a-292">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="85f5a-293">AppPublishingEnabled</span><span class="sxs-lookup"><span data-stu-id="85f5a-293">AppPublishingEnabled</span></span> </p></td>
<td align="left"><p><span data-ttu-id="85f5a-294">DWORD</span><span class="sxs-lookup"><span data-stu-id="85f5a-294">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-295">默认值 = 1</span><span class="sxs-lookup"><span data-stu-id="85f5a-295">Default=1</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-296">配置是否启用从来宾到主机的应用程序发布。</span><span class="sxs-lookup"><span data-stu-id="85f5a-296">Configures whether application publication from the guest to the host is enabled.</span></span>  <span data-ttu-id="85f5a-297">0 = false;1 = true。</span><span class="sxs-lookup"><span data-stu-id="85f5a-297">0 = false; 1 = true.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="85f5a-298">0 = false：禁用从来宾到主机的应用程序发布。</span><span class="sxs-lookup"><span data-stu-id="85f5a-298">0 = false: Disables application publishing from the guest to the host.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="85f5a-299">1 = true：支持从来宾到主机的应用程序发布。</span><span class="sxs-lookup"><span data-stu-id="85f5a-299">1 = true: Enables application publishing from the guest to the host.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="85f5a-300">AudioSharingEnabled</span><span class="sxs-lookup"><span data-stu-id="85f5a-300">AudioSharingEnabled</span></span> </p></td>
<td align="left"><p><span data-ttu-id="85f5a-301">DWORD</span><span class="sxs-lookup"><span data-stu-id="85f5a-301">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-302">默认值 = 1</span><span class="sxs-lookup"><span data-stu-id="85f5a-302">Default=1</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-303">配置在来宾和主机之间共享音频 i/o 设备是否已启用。</span><span class="sxs-lookup"><span data-stu-id="85f5a-303">Configures whether the sharing of the audio I/O device between the guest and the host is enabled.</span></span>  <span data-ttu-id="85f5a-304">0 = false;1 = true。</span><span class="sxs-lookup"><span data-stu-id="85f5a-304">0 = false; 1 = true.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="85f5a-305">0 = false：在来宾和主机之间禁用音频 i/o 设备的共享。</span><span class="sxs-lookup"><span data-stu-id="85f5a-305">0 = false: Disables the sharing of the audio I/O device between the guest and the host.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="85f5a-306">1 = true：支持在来宾和主机之间共享音频输入/输出设备。</span><span class="sxs-lookup"><span data-stu-id="85f5a-306">1 = true: Enables the sharing of the audio I/O device between the guest and the host.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="85f5a-307">ClipboardSharingEnabled</span><span class="sxs-lookup"><span data-stu-id="85f5a-307">ClipboardSharingEnabled</span></span> </p></td>
<td align="left"><p><span data-ttu-id="85f5a-308">DWORD</span><span class="sxs-lookup"><span data-stu-id="85f5a-308">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-309">默认值 = 1</span><span class="sxs-lookup"><span data-stu-id="85f5a-309">Default=1</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-310">配置是否启用了来宾和主机之间的剪贴板共享。</span><span class="sxs-lookup"><span data-stu-id="85f5a-310">Configures whether the sharing of the Clipboard between the guest and the host is enabled.</span></span>  <span data-ttu-id="85f5a-311">0 = false;1 = true。</span><span class="sxs-lookup"><span data-stu-id="85f5a-311">0 = false; 1 = true.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="85f5a-312">0 = false：禁用来宾和主机之间的剪贴板共享。</span><span class="sxs-lookup"><span data-stu-id="85f5a-312">0 = false: Disables the sharing of the Clipboard between the guest and the host.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="85f5a-313">1 = true：支持在来宾和主机之间共享剪贴板。</span><span class="sxs-lookup"><span data-stu-id="85f5a-313">1 = true: Enables the sharing of the Clipboard between the guest and the host.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="85f5a-314">DialogTimeout</span><span class="sxs-lookup"><span data-stu-id="85f5a-314">DialogTimeout</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-315">DWORD</span><span class="sxs-lookup"><span data-stu-id="85f5a-315">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-316">默认值 = 300</span><span class="sxs-lookup"><span data-stu-id="85f5a-316">Default=300</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-317">首次设置 "开始" 对话框超时之前的时间（以秒为单位）。范围 = 0 到2147483647。</span><span class="sxs-lookup"><span data-stu-id="85f5a-317">The time, in seconds, before the first time setup Start Dialog times out. Range = 0 to 2147483647.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="85f5a-318">HideVmTimeout</span><span class="sxs-lookup"><span data-stu-id="85f5a-318">HideVmTimeout</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-319">DWORD</span><span class="sxs-lookup"><span data-stu-id="85f5a-319">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-320">默认值 = 30</span><span class="sxs-lookup"><span data-stu-id="85f5a-320">Default=30</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-321">长时间登录尝试期间从最终用户隐藏全屏虚拟机窗口的超时值（以分钟为单位）。</span><span class="sxs-lookup"><span data-stu-id="85f5a-321">The time-out value, in minutes, that the full-screen virtual machine window is hidden from the end user during a long logon attempt.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="85f5a-322">LogonStartEnabled</span><span class="sxs-lookup"><span data-stu-id="85f5a-322">LogonStartEnabled</span></span> </p></td>
<td align="left"><p><span data-ttu-id="85f5a-323">DWORD</span><span class="sxs-lookup"><span data-stu-id="85f5a-323">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-324">默认值 = 1</span><span class="sxs-lookup"><span data-stu-id="85f5a-324">Default=1</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-325">配置当最终用户登录到桌面或启动第一个来宾应用程序时是否应启动来宾。</span><span class="sxs-lookup"><span data-stu-id="85f5a-325">Configures whether the guest should be started when the end user logs on to the desktop or when the first guest application is started.</span></span>  <span data-ttu-id="85f5a-326">0 = false;1 = true。</span><span class="sxs-lookup"><span data-stu-id="85f5a-326">0 = false; 1 = true.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="85f5a-327">0 = false：启动第一个来宾应用程序时，将启动来宾。</span><span class="sxs-lookup"><span data-stu-id="85f5a-327">0 = false: The guest is started when the first guest application is started.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="85f5a-328">1 = true：当最终用户登录到桌面时，将启动来宾。</span><span class="sxs-lookup"><span data-stu-id="85f5a-328">1 = true: The guest is started when the end user logs on to the desktop.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="85f5a-329">PrinterSharingEnabled</span><span class="sxs-lookup"><span data-stu-id="85f5a-329">PrinterSharingEnabled</span></span> </p></td>
<td align="left"><p><span data-ttu-id="85f5a-330">DWORD</span><span class="sxs-lookup"><span data-stu-id="85f5a-330">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-331">默认值 = 1</span><span class="sxs-lookup"><span data-stu-id="85f5a-331">Default=1</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-332">配置是否启用来宾和主机之间的打印机共享。</span><span class="sxs-lookup"><span data-stu-id="85f5a-332">Configures whether the sharing of printers between the guest and the host is enabled.</span></span>  <span data-ttu-id="85f5a-333">0 = false;1 = true。</span><span class="sxs-lookup"><span data-stu-id="85f5a-333">0 = false; 1 = true.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="85f5a-334">0 = false：禁用来宾和主机之间的打印机共享。</span><span class="sxs-lookup"><span data-stu-id="85f5a-334">0 = false: Disables the sharing of printers between the guest and the host.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="85f5a-335">1 = true：启用来宾和主机之间的打印机共享。</span><span class="sxs-lookup"><span data-stu-id="85f5a-335">1 = true: Enables the sharing of printers between the guest and the host.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="85f5a-336">RebootAbsoluteDelayTimeout</span><span class="sxs-lookup"><span data-stu-id="85f5a-336">RebootAbsoluteDelayTimeout</span></span> </p></td>
<td align="left"><p><span data-ttu-id="85f5a-337">DWORD</span><span class="sxs-lookup"><span data-stu-id="85f5a-337">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-338">默认 = 1440</span><span class="sxs-lookup"><span data-stu-id="85f5a-338">Default=1440</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-339">第一次设置等待重启的超时值（以分钟为单位）。</span><span class="sxs-lookup"><span data-stu-id="85f5a-339">The time-out value, in minutes, that first time setup waits for a restart.</span></span> <span data-ttu-id="85f5a-340">范围 = 0 到2147483647。</span><span class="sxs-lookup"><span data-stu-id="85f5a-340">Range = 0 to 2147483647.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="85f5a-341">RedirectUrls</span><span class="sxs-lookup"><span data-stu-id="85f5a-341">RedirectUrls</span></span> </p></td>
<td align="left"><p><span data-ttu-id="85f5a-342">MULTI_SZ</span><span class="sxs-lookup"><span data-stu-id="85f5a-342">MULTI_SZ</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-343">指定的 URL 列表</span><span class="sxs-lookup"><span data-stu-id="85f5a-343">Specified URL list</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-344">指定要从主机重定向到来宾的 Url 的列表。</span><span class="sxs-lookup"><span data-stu-id="85f5a-344">Specifies a list of URLs to be redirected from the host to the guest.</span></span> </p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="85f5a-345">SmartCardLogonEnabled</span><span class="sxs-lookup"><span data-stu-id="85f5a-345">SmartCardLogonEnabled</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-346">DWORD</span><span class="sxs-lookup"><span data-stu-id="85f5a-346">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-347">默认值 = 0</span><span class="sxs-lookup"><span data-stu-id="85f5a-347">Default=0</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-348">配置智能卡是否可用于对用户进行身份验证以使用 MED-V。</span><span class="sxs-lookup"><span data-stu-id="85f5a-348">Configures whether smart cards can be used to authenticate users to MED-V.</span></span> <span data-ttu-id="85f5a-349">0 = false;1 = true。</span><span class="sxs-lookup"><span data-stu-id="85f5a-349">0 = false; 1 = true.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="85f5a-350">0 = false：不允许智能卡向 MED-V 用户验证最终用户。</span><span class="sxs-lookup"><span data-stu-id="85f5a-350">0 = false: Does not let Smart Cards authenticate end users to MED-V.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="85f5a-351">1 = true：让智能卡向 MED-V 用户验证最终用户。</span><span class="sxs-lookup"><span data-stu-id="85f5a-351">1 = true: Lets Smart Cards authenticate end users to MED-V.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="85f5a-352">重要提示</span><span class="sxs-lookup"><span data-stu-id="85f5a-352">Important</span></span></strong><br/><p><span data-ttu-id="85f5a-353">如果 SmartCardLogonEnabled 和 CredentialCacheEnabled 都已启用，SmartCardLogonEnabled 将忽略 CredentialCacheEnabled。</span><span class="sxs-lookup"><span data-stu-id="85f5a-353">If SmartCardLogonEnabled and CredentialCacheEnabled are both enabled, SmartCardLogonEnabled overrides CredentialCacheEnabled.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="85f5a-354">SmartCardSharingEnabled</span><span class="sxs-lookup"><span data-stu-id="85f5a-354">SmartCardSharingEnabled</span></span> </p></td>
<td align="left"><p><span data-ttu-id="85f5a-355">DWORD</span><span class="sxs-lookup"><span data-stu-id="85f5a-355">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-356">默认值 = 1</span><span class="sxs-lookup"><span data-stu-id="85f5a-356">Default=1</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-357">配置是否启用来宾与主机之间的智能卡共享。</span><span class="sxs-lookup"><span data-stu-id="85f5a-357">Configures whether the sharing of Smart Cards between the guest and the host is enabled.</span></span>  <span data-ttu-id="85f5a-358">0 = false;1 = true。</span><span class="sxs-lookup"><span data-stu-id="85f5a-358">0 = false; 1 = true.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="85f5a-359">0 = false：禁用来宾和主机之间的智能卡共享。</span><span class="sxs-lookup"><span data-stu-id="85f5a-359">0 = false: Disables the sharing of Smart Cards between the guest and the host.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="85f5a-360">1 = true：启用来宾和主机之间的智能卡共享。</span><span class="sxs-lookup"><span data-stu-id="85f5a-360">1 = true: Enables the sharing of Smart Cards between the guest and the host.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="85f5a-361">USBDeviceSharingEnabled</span><span class="sxs-lookup"><span data-stu-id="85f5a-361">USBDeviceSharingEnabled</span></span> </p></td>
<td align="left"><p><span data-ttu-id="85f5a-362">DWORD</span><span class="sxs-lookup"><span data-stu-id="85f5a-362">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-363">默认值 = 1</span><span class="sxs-lookup"><span data-stu-id="85f5a-363">Default=1</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-364">配置是否启用来宾与主机之间的 USB 设备共享。</span><span class="sxs-lookup"><span data-stu-id="85f5a-364">Configures whether the sharing of USB devices between the guest and the host is enabled.</span></span>  <span data-ttu-id="85f5a-365">0 = false;1 = true。</span><span class="sxs-lookup"><span data-stu-id="85f5a-365">0 = false; 1 = true.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="85f5a-366">0 = false：禁用来宾和主机之间的 USB 设备共享。</span><span class="sxs-lookup"><span data-stu-id="85f5a-366">0 = false: Disables the sharing of USB devices between the guest and the host.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="85f5a-367">1 = true：启用来宾和主机之间的 USB 设备共享。</span><span class="sxs-lookup"><span data-stu-id="85f5a-367">1 = true: Enables the sharing of USB devices between the guest and the host.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="85f5a-368">VM 密钥</span><span class="sxs-lookup"><span data-stu-id="85f5a-368">VM Key</span></span>


<span data-ttu-id="85f5a-369">下表提供了与 HKEY _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\Medv\\v2\\VM 键和 HKEY \ _CURRENT \ _USER \\Software\\Microsoft\\Medv\\v2\\VM 键相关联的注册表值的相关信息。</span><span class="sxs-lookup"><span data-stu-id="85f5a-369">The following table provides information about the registry values associated with the HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Medv\\v2\\VM key and the HKEY\_CURRENT\_USER\\Software\\Microsoft\\Medv\\v2\\VM key.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="85f5a-370">名称</span><span class="sxs-lookup"><span data-stu-id="85f5a-370">Name</span></span></th>
<th align="left"><span data-ttu-id="85f5a-371">类型</span><span class="sxs-lookup"><span data-stu-id="85f5a-371">Type</span></span></th>
<th align="left"><span data-ttu-id="85f5a-372">Data/Default</span><span class="sxs-lookup"><span data-stu-id="85f5a-372">Data/Default</span></span></th>
<th align="left"><span data-ttu-id="85f5a-373">描述</span><span class="sxs-lookup"><span data-stu-id="85f5a-373">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="85f5a-374">CloseAction</span><span class="sxs-lookup"><span data-stu-id="85f5a-374">CloseAction</span></span> </p></td>
<td align="left"><p><span data-ttu-id="85f5a-375">SZ</span><span class="sxs-lookup"><span data-stu-id="85f5a-375">SZ</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-376">默认 = 休眠</span><span class="sxs-lookup"><span data-stu-id="85f5a-376">Default=HIBERNATE</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-377">虚拟机在运行的最后一个应用程序关闭后执行的操作。</span><span class="sxs-lookup"><span data-stu-id="85f5a-377">The action that the virtual machine performs after the last application that is running is closed.</span></span> <span data-ttu-id="85f5a-378">如果启用了 LogonStartEnabled 值，此设置将被忽略。</span><span class="sxs-lookup"><span data-stu-id="85f5a-378">This setting is ignored if the LogonStartEnabled value is enabled.</span></span> <span data-ttu-id="85f5a-379">可能的选项如下所示：</span><span class="sxs-lookup"><span data-stu-id="85f5a-379">Possible options are as follows:</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><strong><span data-ttu-id="85f5a-380">休眠 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="85f5a-380">HIBERNATE</strong> .</span></span> <span data-ttu-id="85f5a-381">此选项将释放虚拟机正在使用的所有物理资源（如内存和 CPU），并保存所有运行的应用程序和操作的状态。</span><span class="sxs-lookup"><span data-stu-id="85f5a-381">This option releases all physical resources that the virtual machine is using, such as memory and CPU, and saves the state of all running applications and operations.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><strong><span data-ttu-id="85f5a-382">关闭 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="85f5a-382">SHUTDOWN</strong> .</span></span> <span data-ttu-id="85f5a-383">此选项将安全地关闭来宾操作系统，然后释放虚拟机使用的所有物理资源，例如内存和 CPU。</span><span class="sxs-lookup"><span data-stu-id="85f5a-383">This option shuts down the guest operating system safely and then releases all physical resources that the virtual machine is using, such as memory and CPU.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><strong><span data-ttu-id="85f5a-384">关闭 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="85f5a-384">TURN-OFF</strong>.</span></span> <span data-ttu-id="85f5a-385">此选项可能会导致数据丢失，因为它与关闭电源按钮或在物理计算机上拉出电源线的方式相同。</span><span class="sxs-lookup"><span data-stu-id="85f5a-385">This option can cause data loss because it is the same as turning off the power button or pulling out the power cord on a physical computer.</span></span> <span data-ttu-id="85f5a-386">只有在不能使用其他两个选项时，才可使用此选项。</span><span class="sxs-lookup"><span data-stu-id="85f5a-386">Use this option only if you cannot use one of the other two options.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="85f5a-387">GuestMemFromHostMem</span><span class="sxs-lookup"><span data-stu-id="85f5a-387">GuestMemFromHostMem</span></span> </p></td>
<td align="left"><p><span data-ttu-id="85f5a-388">MULTI_SZ</span><span class="sxs-lookup"><span data-stu-id="85f5a-388">MULTI_SZ</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-389">378、512、1024、1536、2048</span><span class="sxs-lookup"><span data-stu-id="85f5a-389">378, 512, 1024, 1536, 2048</span></span> </p></td>
<td align="left"><p><span data-ttu-id="85f5a-390">来宾的内存（MB）值的列表。</span><span class="sxs-lookup"><span data-stu-id="85f5a-390">A list of memory (MB) values for the guest.</span></span> <span data-ttu-id="85f5a-391">此值用于确定来宾可使用的 RAM 量。</span><span class="sxs-lookup"><span data-stu-id="85f5a-391">This value is used to determine how much RAM is available to the guest.</span></span> <span data-ttu-id="85f5a-392">与 HostMemToGuestMem 结合使用时，将创建一个查找表，以确定要在来宾虚拟机上分配的 RAM 量。</span><span class="sxs-lookup"><span data-stu-id="85f5a-392">Combined with HostMemToGuestMem, a lookup table is created to determine how much RAM to allocate on the guest virtual machine.</span></span> <span data-ttu-id="85f5a-393">可能的值可以从128到3712。</span><span class="sxs-lookup"><span data-stu-id="85f5a-393">Possible values can be from 128 to 3712.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="85f5a-394">GuestUpdateDuration</span><span class="sxs-lookup"><span data-stu-id="85f5a-394">GuestUpdateDuration</span></span> </p></td>
<td align="left"><p><span data-ttu-id="85f5a-395">DWORD</span><span class="sxs-lookup"><span data-stu-id="85f5a-395">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-396">默认值 = 240</span><span class="sxs-lookup"><span data-stu-id="85f5a-396">Default=240</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-397">从 GuestUpdateTime 值中指定的时间开始，MED-V 应将来宾保持唤醒状态以进行自动更新。</span><span class="sxs-lookup"><span data-stu-id="85f5a-397">The number of minutes that MED-V should keep the guest awake for automatic updating, starting at the time specified in the GuestUpdateTime value.</span></span> <span data-ttu-id="85f5a-398">范围 = 0 到1440。</span><span class="sxs-lookup"><span data-stu-id="85f5a-398">Range = 0 to 1440.</span></span> <span data-ttu-id="85f5a-399">将此值设置为零（0）可禁用来宾修补功能。</span><span class="sxs-lookup"><span data-stu-id="85f5a-399">Setting this value to zero (0) disables the guest patching functionality.</span></span></p>
<p><span data-ttu-id="85f5a-400">有关自动更新的来宾修补的详细信息，请参阅 <a href="managing-automatic-updates-for-med-v-workspaces.md" data-raw-source="[Managing Automatic Updates for MED-V Workspaces](managing-automatic-updates-for-med-v-workspaces.md)"> 管理 Med-v 工作区的自动更新 </a> 。</span><span class="sxs-lookup"><span data-stu-id="85f5a-400">For more information about guest patching for automatic updating, see <a href="managing-automatic-updates-for-med-v-workspaces.md" data-raw-source="[Managing Automatic Updates for MED-V Workspaces](managing-automatic-updates-for-med-v-workspaces.md)">Managing Automatic Updates for MED-V Workspaces</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="85f5a-401">GuestUpdateTime</span><span class="sxs-lookup"><span data-stu-id="85f5a-401">GuestUpdateTime</span></span> </p></td>
<td align="left"><p><span data-ttu-id="85f5a-402">SZ</span><span class="sxs-lookup"><span data-stu-id="85f5a-402">SZ</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-403">默认值 = 00：00</span><span class="sxs-lookup"><span data-stu-id="85f5a-403">Default=00:00</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-404">当 MED-V 应使用24小时制时钟标准唤醒客户进行自动更新时，每个工作日的小时数和分钟数。</span><span class="sxs-lookup"><span data-stu-id="85f5a-404">The hour and minute each day when MED-V should wake up the guest for automatic updating, by using the 24-hour clock standard.</span></span> <span data-ttu-id="85f5a-405">以 HH： MM 的格式指定时间</span><span class="sxs-lookup"><span data-stu-id="85f5a-405">Specify the time in the format HH:MM</span></span>  </p>
<p><span data-ttu-id="85f5a-406">有关自动更新的来宾修补的详细信息，请参阅 <a href="managing-automatic-updates-for-med-v-workspaces.md" data-raw-source="[Managing Automatic Updates for MED-V Workspaces](managing-automatic-updates-for-med-v-workspaces.md)"> 管理 Med-v 工作区的自动更新 </a> 。</span><span class="sxs-lookup"><span data-stu-id="85f5a-406">For more information about guest patching for automatic updating, see <a href="managing-automatic-updates-for-med-v-workspaces.md" data-raw-source="[Managing Automatic Updates for MED-V Workspaces](managing-automatic-updates-for-med-v-workspaces.md)">Managing Automatic Updates for MED-V Workspaces</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="85f5a-407">HostMemToGuestMem</span><span class="sxs-lookup"><span data-stu-id="85f5a-407">HostMemToGuestMem</span></span> </p></td>
<td align="left"><p><span data-ttu-id="85f5a-408">MULTI_SZ</span><span class="sxs-lookup"><span data-stu-id="85f5a-408">MULTI_SZ</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-409">1024、2048、4096、8192、16384</span><span class="sxs-lookup"><span data-stu-id="85f5a-409">1024, 2048, 4096, 8192, 16384</span></span> </p></td>
<td align="left"><p><span data-ttu-id="85f5a-410">来宾的内存（MB）值列表，由主机上可用的 RAM 确定。</span><span class="sxs-lookup"><span data-stu-id="85f5a-410">A list of memory (MB) values for the guest, determined by the RAM available on the host.</span></span> <span data-ttu-id="85f5a-411">与 GuestMemFromHostMem 结合使用时，将创建一个查找表，以确定要在来宾虚拟机上分配的 RAM 量。</span><span class="sxs-lookup"><span data-stu-id="85f5a-411">Combined with GuestMemFromHostMem, a lookup table is created to determine how much RAM to allocate on the guest virtual machine.</span></span> <span data-ttu-id="85f5a-412">可能的值可以从1024到16384。</span><span class="sxs-lookup"><span data-stu-id="85f5a-412">Possible values can be from 1024 to 16384.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="85f5a-413">HostMemToGuestMemCalcEnabled</span><span class="sxs-lookup"><span data-stu-id="85f5a-413">HostMemToGuestMemCalcEnabled</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-414">DWORD</span><span class="sxs-lookup"><span data-stu-id="85f5a-414">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-415">默认值 = 1</span><span class="sxs-lookup"><span data-stu-id="85f5a-415">Default=1</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-416">配置是否从主机上存在的内存计算为来宾分配的内存。</span><span class="sxs-lookup"><span data-stu-id="85f5a-416">Configures whether the memory allocated for the guest is calculated from the memory present on the host.</span></span>  <span data-ttu-id="85f5a-417">0 = false;1 = true。</span><span class="sxs-lookup"><span data-stu-id="85f5a-417">0 = false; 1 = true.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="85f5a-418">0 = false：分配给来宾的内存不是通过主机上存在的内存计算的。</span><span class="sxs-lookup"><span data-stu-id="85f5a-418">0 = false: The memory allocated for the guest is not calculated from the memory present on the host.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="85f5a-419">1 = true：为来宾分配的内存是根据主机上存在的内存计算的。</span><span class="sxs-lookup"><span data-stu-id="85f5a-419">1 = true: The memory allocated for the guest is calculated from the memory present on the host.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="85f5a-420">内存</span><span class="sxs-lookup"><span data-stu-id="85f5a-420">Memory</span></span> </p></td>
<td align="left"><p><span data-ttu-id="85f5a-421">DWORD</span><span class="sxs-lookup"><span data-stu-id="85f5a-421">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-422">默认值 = 512</span><span class="sxs-lookup"><span data-stu-id="85f5a-422">Default=512</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-423">应为来宾虚拟机分配的 RAM （MB）。</span><span class="sxs-lookup"><span data-stu-id="85f5a-423">The RAM (MB) that should be allocated for the guest virtual machine.</span></span> <span data-ttu-id="85f5a-424">如果启用了 HostMemToGuestMemEnabled 设置，此设置将被忽略。</span><span class="sxs-lookup"><span data-stu-id="85f5a-424">This setting is ignored if the HostMemToGuestMemEnabled setting is enabled.</span></span> <span data-ttu-id="85f5a-425">范围 = 128 到2048。</span><span class="sxs-lookup"><span data-stu-id="85f5a-425">Range=128 to 2048.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="85f5a-426">MultiUserEnabled</span><span class="sxs-lookup"><span data-stu-id="85f5a-426">MultiUserEnabled</span></span> </p></td>
<td align="left"><p><span data-ttu-id="85f5a-427">DWORD</span><span class="sxs-lookup"><span data-stu-id="85f5a-427">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-428">默认值 = 0</span><span class="sxs-lookup"><span data-stu-id="85f5a-428">Default=0</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-429">配置多个用户是否共享同一个 MED-V 工作区。</span><span class="sxs-lookup"><span data-stu-id="85f5a-429">Configures whether multiple users share the same MED-V workspace.</span></span>  <span data-ttu-id="85f5a-430">0 = false;1 = true。</span><span class="sxs-lookup"><span data-stu-id="85f5a-430">0 = false; 1 = true.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="85f5a-431">0 = false：多个用户不共享同一个 MED-V 工作区。</span><span class="sxs-lookup"><span data-stu-id="85f5a-431">0 = false: Multiple users do not share the same MED-V workspace.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="85f5a-432">1 = true：多个用户共享同一个 MED-V 工作区。</span><span class="sxs-lookup"><span data-stu-id="85f5a-432">1 = true: Multiple users share the same MED-V workspace.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="85f5a-433">NetworkingMode</span><span class="sxs-lookup"><span data-stu-id="85f5a-433">NetworkingMode</span></span> </p></td>
<td align="left"><p><span data-ttu-id="85f5a-434">SZ</span><span class="sxs-lookup"><span data-stu-id="85f5a-434">SZ</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-435">默认值 = NAT</span><span class="sxs-lookup"><span data-stu-id="85f5a-435">Default=NAT</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-436">来宾上使用的网络连接类型。</span><span class="sxs-lookup"><span data-stu-id="85f5a-436">The kind of network connection used on the guest.</span></span> <span data-ttu-id="85f5a-437">可能的值如下所示：</span><span class="sxs-lookup"><span data-stu-id="85f5a-437">Possible values are as follows:</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><strong><span data-ttu-id="85f5a-438">已桥接 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="85f5a-438">Bridged</strong>.</span></span> <span data-ttu-id="85f5a-439">MED-V 有自己的网络地址，通常通过 DHCP 获得。</span><span class="sxs-lookup"><span data-stu-id="85f5a-439">MED-V has its own network address, typically obtained through DHCP.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><strong><span data-ttu-id="85f5a-440">NAT </strong> 。</span><span class="sxs-lookup"><span data-stu-id="85f5a-440">NAT</strong>.</span></span> <span data-ttu-id="85f5a-441">MED-V 使用网络地址转换（NAT）共享主机&#39;s IP 用于传出通信。</span><span class="sxs-lookup"><span data-stu-id="85f5a-441">MED-V uses Network Address Translation (NAT) to share the host&#39;s IP for outgoing traffic.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="85f5a-442">TaskTimeout</span><span class="sxs-lookup"><span data-stu-id="85f5a-442">TaskTimeout</span></span> </p></td>
<td align="left"><p><span data-ttu-id="85f5a-443">DWORD</span><span class="sxs-lookup"><span data-stu-id="85f5a-443">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-444">默认值 = 600</span><span class="sxs-lookup"><span data-stu-id="85f5a-444">Default=600</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-445">常规超时值（以秒为单位），MED-V 将等待任务完成，例如重启和关闭。</span><span class="sxs-lookup"><span data-stu-id="85f5a-445">A general time-out value, in seconds, that MED-V waits for a task to be completed, such as restarting and shutting down.</span></span> <span data-ttu-id="85f5a-446">范围 = 0 到2147483647。</span><span class="sxs-lookup"><span data-stu-id="85f5a-446">Range = 0 to 2147483647.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="85f5a-447">来宾注册表设置</span><span class="sxs-lookup"><span data-stu-id="85f5a-447">Guest Registry Settings</span></span>


<span data-ttu-id="85f5a-448">本部分列出了可配置的 MED-V 来宾注册表项并解释其用法。</span><span class="sxs-lookup"><span data-stu-id="85f5a-448">This section lists the configurable MED-V guest registry keys and explains their uses.</span></span>

### <span data-ttu-id="85f5a-449">2</span><span class="sxs-lookup"><span data-stu-id="85f5a-449">v2</span></span>

<span data-ttu-id="85f5a-450">下表提供了与 HKEY _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\Medv\\v2\\ 键相关联的来宾注册表值的相关信息。</span><span class="sxs-lookup"><span data-stu-id="85f5a-450">The following table provides information about the guest registry value associated with the HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Medv\\v2\\ key.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="85f5a-451">名称</span><span class="sxs-lookup"><span data-stu-id="85f5a-451">Name</span></span> </th>
<th align="left"><span data-ttu-id="85f5a-452">类型</span><span class="sxs-lookup"><span data-stu-id="85f5a-452">Type</span></span> </th>
<th align="left"><span data-ttu-id="85f5a-453">Data/Default</span><span class="sxs-lookup"><span data-stu-id="85f5a-453">Data/Default</span></span> </th>
<th align="left"><span data-ttu-id="85f5a-454">描述</span><span class="sxs-lookup"><span data-stu-id="85f5a-454">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="85f5a-455">EnableGPWorkarounds</span><span class="sxs-lookup"><span data-stu-id="85f5a-455">EnableGPWorkarounds</span></span></p></td>
<td align="left"><p><span data-ttu-id="85f5a-456">DWORD</span><span class="sxs-lookup"><span data-stu-id="85f5a-456">DWORD</span></span> </p></td>
<td align="left"><p><span data-ttu-id="85f5a-457">默认值 = 1</span><span class="sxs-lookup"><span data-stu-id="85f5a-457">Default=1</span></span> </p></td>
<td align="left"><p><span data-ttu-id="85f5a-458">配置 MED-V 处理密钥 BufferPolicyReads 和 GroupPolicyMinTransferRate 的方式。</span><span class="sxs-lookup"><span data-stu-id="85f5a-458">Configures how MED-V handles the keys BufferPolicyReads and GroupPolicyMinTransferRate.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="85f5a-459">默认情况下，MED-V 按如下方式设置这些键：</span><span class="sxs-lookup"><span data-stu-id="85f5a-459">By default, MED-V sets these keys as follows:</span></span></p>
<p><span data-ttu-id="85f5a-460">BufferPolicyReads = 1 和 GroupPolicyMinTransferRate = 0。</span><span class="sxs-lookup"><span data-stu-id="85f5a-460">BufferPolicyReads=1 and GroupPolicyMinTransferRate=0.</span></span></p>
<p><span data-ttu-id="85f5a-461">创建 EnableGPWorkarounds 键（如有必要），如果不希望 MED-V 更改 BufferPolicyReads 和 GroupPolicyMinTransferRate 的默认设置，则将键设置为零。</span><span class="sxs-lookup"><span data-stu-id="85f5a-461">Create the EnableGPWorkarounds  key, if it is necessary, and set the key to zero if you do not want MED-V to change the default settings of BufferPolicyReads and GroupPolicyMinTransferRate.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="85f5a-462">注意</span><span class="sxs-lookup"><span data-stu-id="85f5a-462">Note</span></span></strong><br/><p><span data-ttu-id="85f5a-463">如果你的 MED-V 工作区在 NAT 模式下运行，EnableGPWorkarounds 将影响注册表项 BufferPolicyReads 和 GroupPolicyMinTransferRate。</span><span class="sxs-lookup"><span data-stu-id="85f5a-463">If your MED-V workspace is running in NAT mode, EnableGPWorkarounds affects the registry keys BufferPolicyReads and GroupPolicyMinTransferRate.</span></span> <span data-ttu-id="85f5a-464">如果你的 MED-V 工作区在桥接模式下运行，EnableGPWorkarounds 仅影响注册表项 BufferPolicyReads。</span><span class="sxs-lookup"><span data-stu-id="85f5a-464">If your MED-V workspace is running in BRIDGED mode, EnableGPWorkarounds only affects the registry key BufferPolicyReads.</span></span></p>
</div>
<div>

</div>
<p><span data-ttu-id="85f5a-465">1 = true： MED-V 设置键 BufferPolicyReads = 1 和 GroupPolicyMinTransferRate = 0 （如果在 NAT 模式下运行）或仅 BufferPolicyReads = 1 （如果在桥接模式下运行）。</span><span class="sxs-lookup"><span data-stu-id="85f5a-465">1=true: MED-V sets the keys BufferPolicyReads=1 and GroupPolicyMinTransferRate=0 (if running in NAT mode) or just BufferPolicyReads=1 (if running in BRIDGED mode).</span></span></p>
<p><span data-ttu-id="85f5a-466">0 = false： MED-V 不会对键 BufferPolicyReads 和 GroupPolicyMinTransferRate 进行任何更改。</span><span class="sxs-lookup"><span data-stu-id="85f5a-466">0=false: MED-V does not make any changes to the keys BufferPolicyReads and GroupPolicyMinTransferRate.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="85f5a-467">相关主题</span><span class="sxs-lookup"><span data-stu-id="85f5a-467">Related topics</span></span>


[<span data-ttu-id="85f5a-468">管理 MED-V 工作区应用程序</span><span class="sxs-lookup"><span data-stu-id="85f5a-468">Manage MED-V Workspace Applications</span></span>](manage-med-v-workspace-applications.md)

[<span data-ttu-id="85f5a-469">管理 MED-V URL 重定向</span><span class="sxs-lookup"><span data-stu-id="85f5a-469">Manage MED-V URL Redirection</span></span>](manage-med-v-url-redirection.md)

[<span data-ttu-id="85f5a-470">管理 MED-V 工作区设置</span><span class="sxs-lookup"><span data-stu-id="85f5a-470">Manage MED-V Workspace Settings</span></span>](manage-med-v-workspace-settings.md)









