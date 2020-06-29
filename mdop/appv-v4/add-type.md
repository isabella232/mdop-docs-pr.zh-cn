---
title: ADD TYPE
description: ADD TYPE
author: dansimp
ms.assetid: 8f1d3978-9977-4851-9f46-fee6aefa3535
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4d2dcfb24a32dc733aa91b5534e0011090ef12b9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803157"
---
# <span data-ttu-id="82d13-103">ADD TYPE</span><span class="sxs-lookup"><span data-stu-id="82d13-103">ADD TYPE</span></span>


<span data-ttu-id="82d13-104">添加指定的文件类型关联。</span><span class="sxs-lookup"><span data-stu-id="82d13-104">Adds the specified file type association.</span></span>

`SFTMIME ADD TYPE:file-extension /APP application [/ICON icon-pathname]                 [/DESCRIPTION type-desc] [/CONTENT-TYPE content-type] [/GLOBAL]                 [/PERCEIVED-TYPE perceived-type] [/PROGID progid]                 [/CONFIRMOPEN {YES|NO}] [/SHOWEXT {YES|NO}]                 [/NEWMENU {YES|NO}]  [/LOG log-pathname | /CONSOLE | /GUI]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="82d13-105">参数</span><span class="sxs-lookup"><span data-stu-id="82d13-105">Parameter</span></span></th>
<th align="left"><span data-ttu-id="82d13-106">描述</span><span class="sxs-lookup"><span data-stu-id="82d13-106">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="82d13-107">类型： &lt; 文件扩展名&gt;</span><span class="sxs-lookup"><span data-stu-id="82d13-107">TYPE:&lt;file-extension&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="82d13-108">将与指定的应用程序相关联的文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="82d13-108">The file name extension that will be associated with the application specified.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="82d13-109">/APP &lt; 应用程序&gt;</span><span class="sxs-lookup"><span data-stu-id="82d13-109">/APP &lt;application&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="82d13-110">应用程序的名称和版本（可选）。</span><span class="sxs-lookup"><span data-stu-id="82d13-110">The name and version (optional) of the application.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="82d13-111">/ICON &lt; 图标-pathname&gt;</span><span class="sxs-lookup"><span data-stu-id="82d13-111">/ICON &lt;icon-pathname&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="82d13-112">图标文件的路径或 URL。</span><span class="sxs-lookup"><span data-stu-id="82d13-112">The path or URL for the icon file.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="82d13-113">/DESCRIPTION &lt; 类型-desc&gt;</span><span class="sxs-lookup"><span data-stu-id="82d13-113">/DESCRIPTION &lt;type-desc&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="82d13-114">文件类型的用户友好名称。</span><span class="sxs-lookup"><span data-stu-id="82d13-114">The user-friendly name for the file type.</span></span> <span data-ttu-id="82d13-115">默认为 &quot; 扩展文件。&quot;</span><span class="sxs-lookup"><span data-stu-id="82d13-115">Defaults to &quot;EXTENSION File.&quot;</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="82d13-116">/CONTENT-TYPE &lt; 内容类型&gt;</span><span class="sxs-lookup"><span data-stu-id="82d13-116">/CONTENT-TYPE &lt;content-type&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="82d13-117">文件的内容类型。</span><span class="sxs-lookup"><span data-stu-id="82d13-117">The content type of the file.</span></span> <span data-ttu-id="82d13-118">默认为 &quot; application/softricity-extension。&quot;</span><span class="sxs-lookup"><span data-stu-id="82d13-118">Defaults to &quot;application/softricity-extension.&quot;</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="82d13-119">/GLOBAL</span><span class="sxs-lookup"><span data-stu-id="82d13-119">/GLOBAL</span></span></p></td>
<td align="left"><p><span data-ttu-id="82d13-120">如果存在，则此计算机上的所有用户都可以使用该程序包。</span><span class="sxs-lookup"><span data-stu-id="82d13-120">If present, the package will be available for all users on this computer.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="82d13-121">/PERCEIVED-TYPE &lt; 感知-类型&gt;</span><span class="sxs-lookup"><span data-stu-id="82d13-121">/PERCEIVED-TYPE &lt;perceived-type&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="82d13-122">文件的假设类型。</span><span class="sxs-lookup"><span data-stu-id="82d13-122">The perceived type of the file.</span></span> <span data-ttu-id="82d13-123">默认值为 nothing。</span><span class="sxs-lookup"><span data-stu-id="82d13-123">Defaults to nothing.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="82d13-124">/PROGID &lt; PROGID&gt;</span><span class="sxs-lookup"><span data-stu-id="82d13-124">/PROGID &lt;progid&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="82d13-125">文件类型的编程标识符。</span><span class="sxs-lookup"><span data-stu-id="82d13-125">The programmatic identifier for the file type.</span></span> <span data-ttu-id="82d13-126">默认值为 App Virt 文件。</span><span class="sxs-lookup"><span data-stu-id="82d13-126">Defaults to App Virt.extension.File.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="82d13-127">/CONFIRMOPEN</span><span class="sxs-lookup"><span data-stu-id="82d13-127">/CONFIRMOPEN</span></span></p></td>
<td align="left"><p><span data-ttu-id="82d13-128">指示是否应询问用户是否要打开或保存此类文件。</span><span class="sxs-lookup"><span data-stu-id="82d13-128">Indicates whether users downloading a file of this type should be asked whether to open or save the file.</span></span> <span data-ttu-id="82d13-129">默认值为 "是"。</span><span class="sxs-lookup"><span data-stu-id="82d13-129">Defaults to YES.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="82d13-130">/SHOWEXT</span><span class="sxs-lookup"><span data-stu-id="82d13-130">/SHOWEXT</span></span></p></td>
<td align="left"><p><span data-ttu-id="82d13-131">指示是否应始终显示文件的扩展名，即使用户已请求隐藏所有扩展名也是如此。</span><span class="sxs-lookup"><span data-stu-id="82d13-131">Indicates whether the file's extension should always be shown, even if the user has requested that all extensions be hidden.</span></span> <span data-ttu-id="82d13-132">默认值为 "否"。</span><span class="sxs-lookup"><span data-stu-id="82d13-132">Defaults to NO.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="82d13-133">/NEWMENU</span><span class="sxs-lookup"><span data-stu-id="82d13-133">/NEWMENU</span></span></p></td>
<td align="left"><p><span data-ttu-id="82d13-134">指示是否应将某个条目添加到外壳的 " <strong> 新建" </strong> 菜单。</span><span class="sxs-lookup"><span data-stu-id="82d13-134">Indicates whether an entry should be added to the shell's <strong>New</strong> menu.</span></span> <span data-ttu-id="82d13-135">默认值为 "否"。</span><span class="sxs-lookup"><span data-stu-id="82d13-135">Defaults to NO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="82d13-136">/LOG</span><span class="sxs-lookup"><span data-stu-id="82d13-136">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="82d13-137">如果指定，输出将记录到指定的路径名称。</span><span class="sxs-lookup"><span data-stu-id="82d13-137">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="82d13-138">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="82d13-138">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="82d13-139">如果指定，将在活动控制台窗口中显示输出（默认）。</span><span class="sxs-lookup"><span data-stu-id="82d13-139">If specified, output is presented in the active console window (default).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="82d13-140">/GUI</span><span class="sxs-lookup"><span data-stu-id="82d13-140">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="82d13-141">如果指定，将在 Windows 对话框中显示输出。</span><span class="sxs-lookup"><span data-stu-id="82d13-141">If specified, output is presented in a Windows dialog box.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="82d13-142">对于版本4.6，已添加以下选项。</span><span class="sxs-lookup"><span data-stu-id="82d13-142">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="82d13-143">/LOGU</span><span class="sxs-lookup"><span data-stu-id="82d13-143">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="82d13-144">如果指定，将以 UNICODE 格式将输出记录到指定的路径名称。</span><span class="sxs-lookup"><span data-stu-id="82d13-144">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="82d13-145">相关主题</span><span class="sxs-lookup"><span data-stu-id="82d13-145">Related topics</span></span>


[<span data-ttu-id="82d13-146">SFTMIME 命令引用</span><span class="sxs-lookup"><span data-stu-id="82d13-146">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





