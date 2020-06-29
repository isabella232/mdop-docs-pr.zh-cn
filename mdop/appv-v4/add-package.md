---
title: ADD PACKAGE
description: ADD PACKAGE
author: dansimp
ms.assetid: aa83928d-a234-4395-831e-2a7ef786ff53
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 925349ce5bdf041b6a8768b5413692966e1cfc1e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803160"
---
# <span data-ttu-id="76a9b-103">ADD PACKAGE</span><span class="sxs-lookup"><span data-stu-id="76a9b-103">ADD PACKAGE</span></span>


<span data-ttu-id="76a9b-104">添加程序包记录。</span><span class="sxs-lookup"><span data-stu-id="76a9b-104">Adds a package record.</span></span> <span data-ttu-id="76a9b-105">如果程序包已存在，此命令将更新现有程序包的配置。</span><span class="sxs-lookup"><span data-stu-id="76a9b-105">If the package already exists, this command will update the configuration of the existing package.</span></span>

`SFTMIME ADD PACKAGE:package-name /MANIFEST manifest-path                 [/OVERRIDEURL url [/AUTOLOADONREFRESH] [/AUTOLOADONLOGIN]                 [/AUTOLOADONLAUNCH] [/AUTOLOADTARGET {NONE|ALL|PREVUSED}]                 [/GLOBAL] [/LOG log-pathname | /CONSOLE | /GUI]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="76a9b-106">参数</span><span class="sxs-lookup"><span data-stu-id="76a9b-106">Parameter</span></span></th>
<th align="left"><span data-ttu-id="76a9b-107">描述</span><span class="sxs-lookup"><span data-stu-id="76a9b-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="76a9b-108">程序包： &lt; 软件包-name&gt;</span><span class="sxs-lookup"><span data-stu-id="76a9b-108">PACKAGE:&lt;package-name&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="76a9b-109">程序包的用户可见名称和用户友好名称。</span><span class="sxs-lookup"><span data-stu-id="76a9b-109">User-visible and user-friendly name for the package.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="76a9b-110">/MANIFEST &lt; 清单-path&gt;</span><span class="sxs-lookup"><span data-stu-id="76a9b-110">/MANIFEST &lt;manifest-path&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="76a9b-111">列出程序包中包含的应用程序及其所有发布信息的清单文件的路径。</span><span class="sxs-lookup"><span data-stu-id="76a9b-111">The path of the manifest file that lists the applications included in the package and all of their publishing information.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="76a9b-112">/OVERRIDEURL &lt; URL&gt;</span><span class="sxs-lookup"><span data-stu-id="76a9b-112">/OVERRIDEURL &lt;URL&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="76a9b-113">程序包的 SFT 文件的位置。</span><span class="sxs-lookup"><span data-stu-id="76a9b-113">The location of the package's SFT file.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="76a9b-114">/AUTOLOADONREFRESH</span><span class="sxs-lookup"><span data-stu-id="76a9b-114">/AUTOLOADONREFRESH</span></span></p></td>
<td align="left"><p><span data-ttu-id="76a9b-115">在发布刷新后执行后台加载。</span><span class="sxs-lookup"><span data-stu-id="76a9b-115">Background loading is performed after a publishing refresh.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="76a9b-116">/AUTOLOADONLOGIN</span><span class="sxs-lookup"><span data-stu-id="76a9b-116">/AUTOLOADONLOGIN</span></span></p></td>
<td align="left"><p><span data-ttu-id="76a9b-117">在用户登录时执行后台加载。</span><span class="sxs-lookup"><span data-stu-id="76a9b-117">Background loading is performed when a user logs in.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="76a9b-118">/AUTOLOADONLAUNCH</span><span class="sxs-lookup"><span data-stu-id="76a9b-118">/AUTOLOADONLAUNCH</span></span></p></td>
<td align="left"><p><span data-ttu-id="76a9b-119">在用户从程序包启动应用程序后执行后台加载。</span><span class="sxs-lookup"><span data-stu-id="76a9b-119">Background loading is performed after a user starts an application from the package.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="76a9b-120">/AUTOLOADTARGET 目标</span><span class="sxs-lookup"><span data-stu-id="76a9b-120">/AUTOLOADTARGET target</span></span></p></td>
<td align="left"><p><span data-ttu-id="76a9b-121">指示程序包中将 autoloaded 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="76a9b-121">Indicates which applications from the package will be autoloaded.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="76a9b-122">尚</span><span class="sxs-lookup"><span data-stu-id="76a9b-122">NONE</span></span></p></td>
<td align="left"><p><span data-ttu-id="76a9b-123">尽管存在任何/AUTOLOADONxxx 标志，也不会执行任何 autoloading。</span><span class="sxs-lookup"><span data-stu-id="76a9b-123">No autoloading will be performed, despite the presence of any /AUTOLOADONxxx flags.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="76a9b-124">所有</span><span class="sxs-lookup"><span data-stu-id="76a9b-124">ALL</span></span></p></td>
<td align="left"><p><span data-ttu-id="76a9b-125">如果启用了 autoload 触发器，则程序包中的所有应用程序都将加载到缓存中，无论它们以前是否已启动。</span><span class="sxs-lookup"><span data-stu-id="76a9b-125">If an autoload trigger is enabled, all applications in the package will be loaded into cache whether or not they have been previously started.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="76a9b-126">PREVUSED</span><span class="sxs-lookup"><span data-stu-id="76a9b-126">PREVUSED</span></span></p></td>
<td align="left"><p><span data-ttu-id="76a9b-127">如果启用了 autoload 触发器，则在此程序包中的任何应用程序之前已由用户启动时，将加载该程序包。</span><span class="sxs-lookup"><span data-stu-id="76a9b-127">If an autoload trigger is enabled, the package will load if any applications in this package have previously been started by a user.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="76a9b-128">/GLOBAL</span><span class="sxs-lookup"><span data-stu-id="76a9b-128">/GLOBAL</span></span></p></td>
<td align="left"><p><span data-ttu-id="76a9b-129">如果存在，则此计算机上的所有用户都可以使用该程序包。</span><span class="sxs-lookup"><span data-stu-id="76a9b-129">If present, the package will be available for all users on this computer.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="76a9b-130">/LOG</span><span class="sxs-lookup"><span data-stu-id="76a9b-130">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="76a9b-131">如果指定，输出将记录到指定的路径名称。</span><span class="sxs-lookup"><span data-stu-id="76a9b-131">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="76a9b-132">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="76a9b-132">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="76a9b-133">如果指定，将在活动控制台窗口中显示输出（默认）。</span><span class="sxs-lookup"><span data-stu-id="76a9b-133">If specified, output is presented in the active console window (default).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="76a9b-134">/GUI</span><span class="sxs-lookup"><span data-stu-id="76a9b-134">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="76a9b-135">如果指定，将在 Windows 对话框中显示输出。</span><span class="sxs-lookup"><span data-stu-id="76a9b-135">If specified, output is presented in a Windows dialog box.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="76a9b-136">对于版本4.6，已添加以下选项。</span><span class="sxs-lookup"><span data-stu-id="76a9b-136">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="76a9b-137">/LOGU</span><span class="sxs-lookup"><span data-stu-id="76a9b-137">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="76a9b-138">如果指定，将以 UNICODE 格式将输出记录到指定的路径名称。</span><span class="sxs-lookup"><span data-stu-id="76a9b-138">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="76a9b-139">相关主题</span><span class="sxs-lookup"><span data-stu-id="76a9b-139">Related topics</span></span>


[<span data-ttu-id="76a9b-140">SFTMIME 命令引用</span><span class="sxs-lookup"><span data-stu-id="76a9b-140">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





