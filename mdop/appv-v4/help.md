---
title: HELP
description: HELP
author: dansimp
ms.assetid: 0ddb5f18-0c0a-45ea-b7c7-2d4749e3d35d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 395e6199529ccbe708aa7d1ac6673ea6f9494ae4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802973"
---
# <span data-ttu-id="6835c-103">HELP</span><span class="sxs-lookup"><span data-stu-id="6835c-103">HELP</span></span>


<span data-ttu-id="6835c-104">显示有关可在应用程序虚拟化（app-v）中使用的各种 SFTMIME 命令的信息。</span><span class="sxs-lookup"><span data-stu-id="6835c-104">Displays information about the various SFTMIME commands that can be used in Application Virtualization (App-V).</span></span>

## <span data-ttu-id="6835c-105">HELP</span><span class="sxs-lookup"><span data-stu-id="6835c-105">HELP</span></span>


`SFTMIME [/? | /HELP [VERB:<verb>]]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="6835c-106">参数</span><span class="sxs-lookup"><span data-stu-id="6835c-106">Parameter</span></span></th>
<th align="left"><span data-ttu-id="6835c-107">描述</span><span class="sxs-lookup"><span data-stu-id="6835c-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6835c-108">/？、/HELP</span><span class="sxs-lookup"><span data-stu-id="6835c-108">/?, /HELP</span></span></p></td>
<td align="left"><p><span data-ttu-id="6835c-109">显示使用信息。</span><span class="sxs-lookup"><span data-stu-id="6835c-109">Displays usage information.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6835c-110">谓词</span><span class="sxs-lookup"><span data-stu-id="6835c-110">verb</span></span></p></td>
<td align="left"><p><span data-ttu-id="6835c-111">要运行的命令，如 "添加"、"刷新"、"帮助" 或 "删除"。</span><span class="sxs-lookup"><span data-stu-id="6835c-111">The command to run, such as ADD, REFRESH, HELP or REMOVE.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6835c-112">object</span><span class="sxs-lookup"><span data-stu-id="6835c-112">object</span></span></p></td>
<td align="left"><p><span data-ttu-id="6835c-113">该命令的应用方式，如应用： &quot; 默认应用程序。&quot;</span><span class="sxs-lookup"><span data-stu-id="6835c-113">What the command applies to, such as APP:&quot;Default Application.&quot;</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6835c-114">实参</span><span class="sxs-lookup"><span data-stu-id="6835c-114">parameters</span></span></p></td>
<td align="left"><p><span data-ttu-id="6835c-115">指定动词和对象的可选参数。</span><span class="sxs-lookup"><span data-stu-id="6835c-115">Optional parameters for the specified verb and object.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6835c-116">/LOG</span><span class="sxs-lookup"><span data-stu-id="6835c-116">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="6835c-117">将输出记录到指定的路径名称。</span><span class="sxs-lookup"><span data-stu-id="6835c-117">Log output to the specified path name.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6835c-118">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="6835c-118">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="6835c-119">在活动控制台窗口中显示输出（默认）。</span><span class="sxs-lookup"><span data-stu-id="6835c-119">Displays output in the active console window (default).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6835c-120">/GUI</span><span class="sxs-lookup"><span data-stu-id="6835c-120">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="6835c-121">显示对话框中的错误（对于查询无效）。</span><span class="sxs-lookup"><span data-stu-id="6835c-121">Displays errors in a dialog box (not valid for queries).</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="6835c-122">对于版本4.6，已添加以下选项。</span><span class="sxs-lookup"><span data-stu-id="6835c-122">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6835c-123">/LOGU</span><span class="sxs-lookup"><span data-stu-id="6835c-123">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="6835c-124">如果指定，将以 UNICODE 格式将输出记录到指定的路径名称。</span><span class="sxs-lookup"><span data-stu-id="6835c-124">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="6835c-125">下表中所述的谓词受支持。</span><span class="sxs-lookup"><span data-stu-id="6835c-125">The verbs described in the following table are supported.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6835c-126">ADD</span><span class="sxs-lookup"><span data-stu-id="6835c-126">ADD</span></span></p></td>
<td align="left"><p><span data-ttu-id="6835c-127">将新的应用程序、程序包、文件类型关联或发布服务器添加到 App-v 客户端。</span><span class="sxs-lookup"><span data-stu-id="6835c-127">Adds a new application, package, file type association, or publishing server to the App-V Client.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6835c-128">对</span><span class="sxs-lookup"><span data-stu-id="6835c-128">CONFIGURE</span></span></p></td>
<td align="left"><p><span data-ttu-id="6835c-129">更改应用程序、程序包、文件类型关联或发布服务器的配置。</span><span class="sxs-lookup"><span data-stu-id="6835c-129">Changes the configuration of an application, a package, a file type association, or a publishing server.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6835c-130">DELETE</span><span class="sxs-lookup"><span data-stu-id="6835c-130">DELETE</span></span></p></td>
<td align="left"><p><span data-ttu-id="6835c-131">删除应用程序、程序包、文件类型关联或服务器。</span><span class="sxs-lookup"><span data-stu-id="6835c-131">Removes applications, packages, file type associations, or servers.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6835c-132">载量</span><span class="sxs-lookup"><span data-stu-id="6835c-132">LOAD</span></span></p></td>
<td align="left"><p><span data-ttu-id="6835c-133">将程序包加载到文件系统缓存中。</span><span class="sxs-lookup"><span data-stu-id="6835c-133">Loads a package into the file system cache.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6835c-134">修复</span><span class="sxs-lookup"><span data-stu-id="6835c-134">REPAIR</span></span></p></td>
<td align="left"><p><span data-ttu-id="6835c-135">重置应用程序的个人设置。</span><span class="sxs-lookup"><span data-stu-id="6835c-135">Resets your personal settings for an application.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6835c-136">恢复</span><span class="sxs-lookup"><span data-stu-id="6835c-136">REFRESH</span></span></p></td>
<td align="left"><p><span data-ttu-id="6835c-137">触发发布服务器刷新。</span><span class="sxs-lookup"><span data-stu-id="6835c-137">Triggers a publishing server refresh.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6835c-138">发布</span><span class="sxs-lookup"><span data-stu-id="6835c-138">PUBLISH</span></span></p></td>
<td align="left"><p><span data-ttu-id="6835c-139">将应用程序快捷方式发布到用户的 "开始" 菜单、"桌面" 或其他指定位置，或者可用于发布整个程序包的内容。</span><span class="sxs-lookup"><span data-stu-id="6835c-139">Publishes an application shortcut to the user's Start menu, desktop, or other specified location, or can be used to publish the contents of an entire package.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6835c-140">发布</span><span class="sxs-lookup"><span data-stu-id="6835c-140">UNPUBLISH</span></span></p></td>
<td align="left"><p><span data-ttu-id="6835c-141">删除整个程序包的快捷方式和文件类型。</span><span class="sxs-lookup"><span data-stu-id="6835c-141">Removes the shortcuts and file types for an entire package.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6835c-142">查询</span><span class="sxs-lookup"><span data-stu-id="6835c-142">QUERY</span></span></p></td>
<td align="left"><p><span data-ttu-id="6835c-143">获取应用程序、程序包、文件类型关联或发布服务器的当前列表。</span><span class="sxs-lookup"><span data-stu-id="6835c-143">Gets a current list of applications, packages, file type associations, or publishing servers.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6835c-144">消除</span><span class="sxs-lookup"><span data-stu-id="6835c-144">CLEAR</span></span></p></td>
<td align="left"><p><span data-ttu-id="6835c-145">删除一个或多个应用程序的个人设置和桌面配置。</span><span class="sxs-lookup"><span data-stu-id="6835c-145">Removes your personal settings and desktop configurations for one or more applications.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6835c-146">卸载</span><span class="sxs-lookup"><span data-stu-id="6835c-146">UNLOAD</span></span></p></td>
<td align="left"><p><span data-ttu-id="6835c-147">从文件系统缓存中卸载程序包。</span><span class="sxs-lookup"><span data-stu-id="6835c-147">Unloads a package from the file system cache.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6835c-148">形</span><span class="sxs-lookup"><span data-stu-id="6835c-148">LOCK</span></span></p></td>
<td align="left"><p><span data-ttu-id="6835c-149">锁定在文件系统缓存中指定的应用程序。</span><span class="sxs-lookup"><span data-stu-id="6835c-149">Locks the application specified in the file system cache.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6835c-150">钥匙</span><span class="sxs-lookup"><span data-stu-id="6835c-150">UNLOCK</span></span></p></td>
<td align="left"><p><span data-ttu-id="6835c-151">解除锁定文件系统缓存中指定的应用程序。</span><span class="sxs-lookup"><span data-stu-id="6835c-151">Unlocks the application specified in the file system cache.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="6835c-152">有关上述操作的详细信息，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="6835c-152">For more information about the preceding actions, use the following command:</span></span>

`SFTMIME /HELP VERB:verb`

<span data-ttu-id="6835c-153">例如，以下命令将显示 ADD 谓词的信息：</span><span class="sxs-lookup"><span data-stu-id="6835c-153">For example, the following command will display information for the ADD verb:</span></span>

`SFTMIME /HELP VERB:ADD`

## <span data-ttu-id="6835c-154">相关主题</span><span class="sxs-lookup"><span data-stu-id="6835c-154">Related topics</span></span>


[<span data-ttu-id="6835c-155">SFTMIME 命令引用</span><span class="sxs-lookup"><span data-stu-id="6835c-155">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





