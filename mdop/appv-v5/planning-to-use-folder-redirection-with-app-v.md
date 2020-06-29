---
title: 计划将文件夹重定向与 App-V 结合使用
description: 计划将文件夹重定向与 App-V 结合使用
author: dansimp
ms.assetid: 2a4deeed-fdc0-465c-b88a-3a2fbbf27436
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b25b3531faa495275bf4e478389f44790d8eed9a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798281"
---
# <span data-ttu-id="ad7ba-103">计划将文件夹重定向与 App-V 结合使用</span><span class="sxs-lookup"><span data-stu-id="ad7ba-103">Planning to Use Folder Redirection with App-V</span></span>


<span data-ttu-id="ad7ba-104">App-v 5.0 SP2 支持使用文件夹重定向，这种功能使用户和管理员能够将文件夹的路径重定向到新位置。</span><span class="sxs-lookup"><span data-stu-id="ad7ba-104">App-V 5.0 SP2 supports the use of folder redirection, a feature that enables users and administrators to redirect the path of a folder to a new location.</span></span>

<span data-ttu-id="ad7ba-105">本主题包含以下各节：</span><span class="sxs-lookup"><span data-stu-id="ad7ba-105">This topic contains the following sections:</span></span>

-   [<span data-ttu-id="ad7ba-106">使用文件夹重定向的要求</span><span class="sxs-lookup"><span data-stu-id="ad7ba-106">Requirements for using folder redirection</span></span>](#bkmk-folder-redir-reqs)

-   [<span data-ttu-id="ad7ba-107">如何配置用于 App-v 的文件夹重定向</span><span class="sxs-lookup"><span data-stu-id="ad7ba-107">How to configure folder redirection for use with App-V</span></span>](#bkmk-folder-redir-cfg)

-   [<span data-ttu-id="ad7ba-108">文件夹重定向如何与 app-v 配合使用</span><span class="sxs-lookup"><span data-stu-id="ad7ba-108">How folder redirection works with App-V</span></span>](#bkmk-folder-redir-works)

-   [<span data-ttu-id="ad7ba-109">文件夹重定向概述</span><span class="sxs-lookup"><span data-stu-id="ad7ba-109">Overview of folder redirection</span></span>](#bkmk-folder-redir-overview)

## <a href="" id="bkmk-folder-redir-reqs"></a><span data-ttu-id="ad7ba-110">使用文件夹重定向的要求和不受支持的方案</span><span class="sxs-lookup"><span data-stu-id="ad7ba-110">Requirements and unsupported scenarios for using folder redirection</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ad7ba-111">要求</span><span class="sxs-lookup"><span data-stu-id="ad7ba-111">Requirements</span></span></p></td>
<td align="left"><p><span data-ttu-id="ad7ba-112">若要使用% AppData% 文件夹重定向，必须：</span><span class="sxs-lookup"><span data-stu-id="ad7ba-112">To use %AppData% folder redirection, you must:</span></span></p>
<ul>
<li><p><span data-ttu-id="ad7ba-113">具有具有 AppData 虚拟文件系统（VFS）文件夹的 app-v 包。</span><span class="sxs-lookup"><span data-stu-id="ad7ba-113">Have an App-V package that has an AppData virtual file system (VFS) folder.</span></span></p></li>
<li><p><span data-ttu-id="ad7ba-114">启用文件夹重定向并将用户文件夹重定向到共享文件夹，通常是网络文件夹。</span><span class="sxs-lookup"><span data-stu-id="ad7ba-114">Enable folder redirection and redirect users’ folders to a shared folder, typically a network folder.</span></span></p></li>
<li><p><span data-ttu-id="ad7ba-115">既能漫游下列两项，也不漫游：</span><span class="sxs-lookup"><span data-stu-id="ad7ba-115">Roam both or neither of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="ad7ba-116">%Appdata%\Microsoft\AppV\Client\Catalog 下的文件</span><span class="sxs-lookup"><span data-stu-id="ad7ba-116">Files under %appdata%\Microsoft\AppV\Client\Catalog</span></span></p></li>
<li><p><span data-ttu-id="ad7ba-117">HKEY_CURRENT_USER \Software\Microsoft\AppV\Client\Packages 下的注册表设置</span><span class="sxs-lookup"><span data-stu-id="ad7ba-117">Registry settings under HKEY_CURRENT_USER\Software\Microsoft\AppV\Client\Packages</span></span></p>
<p><span data-ttu-id="ad7ba-118">有关更多详细信息，请参阅 <a href="application-publishing-and-client-interaction.md#bkmk-clt-inter-roam-reqs" data-raw-source="[Application Publishing and Client Interaction](application-publishing-and-client-interaction.md#bkmk-clt-inter-roam-reqs)"> 应用程序发布和客户端交互 </a> 。</span><span class="sxs-lookup"><span data-stu-id="ad7ba-118">For more detail, see <a href="application-publishing-and-client-interaction.md#bkmk-clt-inter-roam-reqs" data-raw-source="[Application Publishing and Client Interaction](application-publishing-and-client-interaction.md#bkmk-clt-inter-roam-reqs)">Application Publishing and Client Interaction</a>.</span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="ad7ba-119">确保登录到运行 App-v 5.0 SP2 或更高版本客户端的计算机的每个用户都可以使用以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="ad7ba-119">Ensure that the following folders are available to each user who logs into the computer that is running the App-V 5.0 SP2 or later client:</span></span></p>
<ul>
<li><p><span data-ttu-id="ad7ba-120">% AppData% 配置为所需的网络位置（有或不 <a href="https://technet.microsoft.com/library/cc780552.aspx" data-raw-source="[Offline Files](https://technet.microsoft.com/library/cc780552.aspx)"> 支持脱机文件 </a> ）。</span><span class="sxs-lookup"><span data-stu-id="ad7ba-120">%AppData% is configured to the desired network location (with or without <a href="https://technet.microsoft.com/library/cc780552.aspx" data-raw-source="[Offline Files](https://technet.microsoft.com/library/cc780552.aspx)">Offline Files</a> support).</span></span></p></li>
<li><p><span data-ttu-id="ad7ba-121">% LocalAppData% 配置为所需的本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="ad7ba-121">%LocalAppData% is configured to the desired local folder.</span></span></p></li>
</ul></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ad7ba-122">不受支持的情形</span><span class="sxs-lookup"><span data-stu-id="ad7ba-122">Unsupported scenarios</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="ad7ba-123">将% LocalAppData% 配置为网络驱动器。</span><span class="sxs-lookup"><span data-stu-id="ad7ba-123">Configuring %LocalAppData% as a network drive.</span></span></p></li>
<li><p><span data-ttu-id="ad7ba-124">为多个用户将 "开始" 菜单重定向到单个文件夹。</span><span class="sxs-lookup"><span data-stu-id="ad7ba-124">Redirecting the Start menu to a single folder for multiple users.</span></span></p></li>
<li><p><span data-ttu-id="ad7ba-125">如果漫游 AppData （% AppData%）被重定向到不可用的网络共享，则 App-v 应用程序将无法启动，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ad7ba-125">If roaming AppData (%AppData%) is redirected to a network share that is not available, App-V applications will fail to launch as follows:</span></span></p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ad7ba-126">App-v 版本</span><span class="sxs-lookup"><span data-stu-id="ad7ba-126">App-V version</span></span></th>
<th align="left"><span data-ttu-id="ad7ba-127">方案说明</span><span class="sxs-lookup"><span data-stu-id="ad7ba-127">Scenario description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ad7ba-128">在 app-v 5.0 中，通过 app-v 5.0 SP2 和修补程序</span><span class="sxs-lookup"><span data-stu-id="ad7ba-128">In App-V 5.0 through App-V 5.0 SP2 plus hotfixes</span></span></p></td>
<td align="left"><p><span data-ttu-id="ad7ba-129">无论是否启用 "脱机文件"，都将出现此错误。</span><span class="sxs-lookup"><span data-stu-id="ad7ba-129">This failure will occur regardless of whether Offline Files is enabled.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ad7ba-130">在 App-v 5.0 SP3 中</span><span class="sxs-lookup"><span data-stu-id="ad7ba-130">In App-V 5.0 SP3</span></span></p></td>
<td align="left"><p><span data-ttu-id="ad7ba-131">如果为脱机文件启用了不可用的网络共享，则 App-v 应用程序将成功启动。</span><span class="sxs-lookup"><span data-stu-id="ad7ba-131">If the unavailable network share has been enabled for Offline Files, the App-V application will start successfully.</span></span></p></td>
</tr>
</tbody>
</table>
<p> </p></li>
</ul></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-folder-redir-cfg"></a><span data-ttu-id="ad7ba-132">如何配置用于 App-v 的文件夹重定向</span><span class="sxs-lookup"><span data-stu-id="ad7ba-132">How to configure folder redirection for use with App-V</span></span>


<span data-ttu-id="ad7ba-133">文件夹重定向可应用于不同的文件夹，例如 "桌面"、"我的文档"、"我的图片" 等。但是，影响 App-v 应用程序的使用的唯一文件夹是用户的漫游 AppData 文件夹（% AppData%）。</span><span class="sxs-lookup"><span data-stu-id="ad7ba-133">Folder redirection can be applied to different folders, such as Desktop, My Documents, My Pictures, etc. However, the only folder that impacts the use of App-V applications is the user’s roaming AppData folder (%AppData%).</span></span> <span data-ttu-id="ad7ba-134">你可以将文件夹重定向应用到任何其他支持的文件夹，而不会影响 App-v。</span><span class="sxs-lookup"><span data-stu-id="ad7ba-134">You can apply folder redirection to any other supported folders without impacting App-V.</span></span>

## <a href="" id="bkmk-folder-redir-works"></a><span data-ttu-id="ad7ba-135">文件夹重定向如何与 app-v 配合使用</span><span class="sxs-lookup"><span data-stu-id="ad7ba-135">How folder redirection works with App-V</span></span>


<span data-ttu-id="ad7ba-136">下表介绍了当% AppData% 被重定向到网络时，以及当满足本文前面列出的要求时，文件夹重定向如何工作。</span><span class="sxs-lookup"><span data-stu-id="ad7ba-136">The following table describes how folder redirection works when %AppData% is redirected to a network and when you have met the requirements listed earlier in this article.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ad7ba-137">虚拟环境状态</span><span class="sxs-lookup"><span data-stu-id="ad7ba-137">Virtual environment state</span></span></th>
<th align="left"><span data-ttu-id="ad7ba-138">发生的操作</span><span class="sxs-lookup"><span data-stu-id="ad7ba-138">Action that occurs</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ad7ba-139">虚拟环境启动时</span><span class="sxs-lookup"><span data-stu-id="ad7ba-139">When the virtual environment starts</span></span></p></td>
<td align="left"><p><span data-ttu-id="ad7ba-140">虚拟文件系统（VFS） AppData 文件夹映射到本地 AppData 文件夹（% LocalAppData%）而不是用户的漫游 AppData 文件夹（% AppData%）。</span><span class="sxs-lookup"><span data-stu-id="ad7ba-140">The virtual file system (VFS) AppData folder is mapped to the local AppData folder (%LocalAppData%) instead of to the user’s roaming AppData folder (%AppData%).</span></span></p>
<ul>
<li><p><span data-ttu-id="ad7ba-141">LocalAppData 包含要使用的程序包的用户漫游 AppData 文件夹的本地缓存。</span><span class="sxs-lookup"><span data-stu-id="ad7ba-141">LocalAppData contains a local cache of the user’s roaming AppData folder for the package in use.</span></span> <span data-ttu-id="ad7ba-142">本地缓存位于以下位置：</span><span class="sxs-lookup"><span data-stu-id="ad7ba-142">The local cache is located under:</span></span></p>
<p><code>%LocalAppData%\Microsoft\AppV\Client\VFS\PackageGUID\AppData</code></p></li>
<li><p><span data-ttu-id="ad7ba-143">用户的漫游 AppData 文件夹中的最新数据将复制到并替换本地缓存中的当前数据。</span><span class="sxs-lookup"><span data-stu-id="ad7ba-143">The latest data from the user’s roaming AppData folder is copied to and replaces the data currently in the local cache.</span></span></p></li>
<li><p><span data-ttu-id="ad7ba-144">虚拟环境运行时，数据将继续保存到本地缓存。</span><span class="sxs-lookup"><span data-stu-id="ad7ba-144">While the virtual environment is running, data continues to be saved to the local cache.</span></span> <span data-ttu-id="ad7ba-145">仅提供% LocalAppData% 的数据，并且不会与% AppData% 一起移动或同步，直到最终用户关闭计算机。</span><span class="sxs-lookup"><span data-stu-id="ad7ba-145">Data is served only out of %LocalAppData% and is not moved or synchronized with %AppData% until the end user shuts down the computer.</span></span></p></li>
<li><p><span data-ttu-id="ad7ba-146">使用用户上下文（而非系统上下文）对 AppData 文件夹的条目进行输入。</span><span class="sxs-lookup"><span data-stu-id="ad7ba-146">Entries to the AppData folder are made using the user context, not the system context.</span></span></p></li>
</ul>
<div class="alert">
<strong><span data-ttu-id="ad7ba-147">注意</span><span class="sxs-lookup"><span data-stu-id="ad7ba-147">Note</span></span></strong><br/><p><span data-ttu-id="ad7ba-148">App-v 客户端文件夹重定向有时无法将文件从% AppData% 移动到% LocalAppData%。</span><span class="sxs-lookup"><span data-stu-id="ad7ba-148">The App-V client folder redirection sometimes fails to move files from %AppData% to %LocalAppData%.</span></span> <span data-ttu-id="ad7ba-149">请参阅 <a href="release-notes-for-app-v-50-sp2.md#bkmk-folderredirection" data-raw-source="[Release Notes for App-V 5.0 SP2](release-notes-for-app-v-50-sp2.md#bkmk-folderredirection)"> 应用-V 5.0 SP2 的发行说明 </a> 。</span><span class="sxs-lookup"><span data-stu-id="ad7ba-149">See <a href="release-notes-for-app-v-50-sp2.md#bkmk-folderredirection" data-raw-source="[Release Notes for App-V 5.0 SP2](release-notes-for-app-v-50-sp2.md#bkmk-folderredirection)">Release Notes for App-V 5.0 SP2</a>.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ad7ba-150">虚拟环境关闭时</span><span class="sxs-lookup"><span data-stu-id="ad7ba-150">When the virtual environment shuts down</span></span></p></td>
<td align="left"><p><span data-ttu-id="ad7ba-151">将 AppData （漫游）中的本地缓存数据压缩并复制到% AppData% 中的 "真正的" 漫游 AppData 文件夹。</span><span class="sxs-lookup"><span data-stu-id="ad7ba-151">The local cached data in AppData (roaming) is zipped up and copied to the “real” roaming AppData folder in %AppData%.</span></span> <span data-ttu-id="ad7ba-152">时间戳（指示上次已知上载）将同时另存为注册表项，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ad7ba-152">A time stamp, which indicates the last known upload, is simultaneously saved as a registry key under:</span></span></p>
<p><code>HKCU\Software\Microsoft\AppV\Client\Packages&amp;lt;PACKAGE_GUID&gt;\AppDataTime</code></p>
<p><span data-ttu-id="ad7ba-153">为了提供冗余，App-v 5.0 保留% AppData% 下的三个最新压缩数据副本。</span><span class="sxs-lookup"><span data-stu-id="ad7ba-153">To provide redundancy, App-V 5.0 keeps the three most recent copies of the compressed data under %AppData%.</span></span></p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-folder-redir-overview"></a><span data-ttu-id="ad7ba-154">文件夹重定向概述</span><span class="sxs-lookup"><span data-stu-id="ad7ba-154">Overview of folder redirection</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ad7ba-155">用途</span><span class="sxs-lookup"><span data-stu-id="ad7ba-155">Purpose</span></span></p></td>
<td align="left"><p><span data-ttu-id="ad7ba-156">使最终用户能够使用已重定向到另一个文件夹的文件，就像文件仍然存在于本地驱动器上一样。</span><span class="sxs-lookup"><span data-stu-id="ad7ba-156">Enables end users to work with files, which have been redirected to another folder, as if the files still existed on the local drive.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ad7ba-157">描述</span><span class="sxs-lookup"><span data-stu-id="ad7ba-157">Description</span></span></p></td>
<td align="left"><p><span data-ttu-id="ad7ba-158">文件夹重定向允许用户和管理员将文件夹的路径重定向到网络位置。</span><span class="sxs-lookup"><span data-stu-id="ad7ba-158">Folder redirection allows users and administrators to redirect the path of a folder to a network location.</span></span> <span data-ttu-id="ad7ba-159">用户可从网络上的任何计算机使用该文件夹中的文档。</span><span class="sxs-lookup"><span data-stu-id="ad7ba-159">The documents in the folder are available to the user from any computer on the network.</span></span></p>
<ul>
<li><p><span data-ttu-id="ad7ba-160">文件夹重定向允许用户和管理员将文件夹的路径重定向到网络位置。</span><span class="sxs-lookup"><span data-stu-id="ad7ba-160">Folder redirection allows users and administrators to redirect the path of a folder to a network location.</span></span> <span data-ttu-id="ad7ba-161">用户可从网络上的任何计算机使用该文件夹中的文档。</span><span class="sxs-lookup"><span data-stu-id="ad7ba-161">The documents in the folder are available to the user from any computer on the network.</span></span></p></li>
<li><p><span data-ttu-id="ad7ba-162">新位置可以是本地计算机上的文件夹，也可以是共享网络上的文件夹。</span><span class="sxs-lookup"><span data-stu-id="ad7ba-162">The new location can be a folder on the local computer or a folder on a shared network.</span></span></p></li>
<li><p><span data-ttu-id="ad7ba-163">"文件夹重定向" 将立即更新文件，而漫游数据通常在用户登录或注销时同步。</span><span class="sxs-lookup"><span data-stu-id="ad7ba-163">Folder redirection updates the files immediately, whereas roaming data is typically synchronized when the user logs in or logs off.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ad7ba-164">用法示例</span><span class="sxs-lookup"><span data-stu-id="ad7ba-164">Usage example</span></span></p></td>
<td align="left"><p><span data-ttu-id="ad7ba-165">你可以将 "文档" 文件夹（通常存储在计算机&#39;s 本地硬盘）重定向到网络位置。</span><span class="sxs-lookup"><span data-stu-id="ad7ba-165">You can redirect the Documents folder, which is usually stored on the computer&#39;s local hard disk, to a network location.</span></span> <span data-ttu-id="ad7ba-166">用户可以从网络上的任何计算机访问文件夹中的文档。</span><span class="sxs-lookup"><span data-stu-id="ad7ba-166">The user can access the documents in the folder from any computer on the network.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ad7ba-167">更多资源</span><span class="sxs-lookup"><span data-stu-id="ad7ba-167">More resources</span></span></p></td>
<td align="left"><p><a href="https://technet.microsoft.com/library/cc778976.aspx" data-raw-source="[Folder redirection overview](https://technet.microsoft.com/library/cc778976.aspx)"><span data-ttu-id="ad7ba-168">文件夹重定向概述</span><span class="sxs-lookup"><span data-stu-id="ad7ba-168">Folder redirection overview</span></span></a></p></td>
</tr>
</tbody>
</table>
















