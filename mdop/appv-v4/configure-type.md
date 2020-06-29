---
title: CONFIGURE TYPE
description: CONFIGURE TYPE
author: dansimp
ms.assetid: 2caf9433-5449-486f-ab94-83ee8e44d7f1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9b70cdd1b27eba0109183f1eb9cfb42f08b3f341
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803068"
---
# <span data-ttu-id="4396c-103">CONFIGURE TYPE</span><span class="sxs-lookup"><span data-stu-id="4396c-103">CONFIGURE TYPE</span></span>


<span data-ttu-id="4396c-104">允许用户更改文件类型关联的设置。</span><span class="sxs-lookup"><span data-stu-id="4396c-104">Enables the user to change settings for a file type association.</span></span>

`SFTMIME CONFIGURE TYPE:file-extension [/GLOBAL] [/APP application]                 [/ICON icon-pathname] [/DESCRIPTION type-desc]                 [/CONTENT-TYPE content-type] [/PERCEIVED-TYPE perceived-type]                 [/PROGID progid] [/CONFIRMOPEN {YES|NO}]                 [/SHOWEXT {YES|NO}] [/NEWMENU {YES|NO}]                 [/LOG log-pathname | /CONSOLE | /GUI]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4396c-105">参数</span><span class="sxs-lookup"><span data-stu-id="4396c-105">Parameter</span></span></th>
<th align="left"><span data-ttu-id="4396c-106">描述</span><span class="sxs-lookup"><span data-stu-id="4396c-106">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4396c-107">类型： &lt; 文件扩展名&gt;</span><span class="sxs-lookup"><span data-stu-id="4396c-107">TYPE:&lt;file-extension&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="4396c-108">要配置的文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="4396c-108">The file name extension to be configured.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4396c-109">/APP &lt; 应用程序&gt;</span><span class="sxs-lookup"><span data-stu-id="4396c-109">/APP &lt;application&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="4396c-110">将此文件类型与关联的应用程序的名称和版本（可选）。</span><span class="sxs-lookup"><span data-stu-id="4396c-110">The name and version (optional) of the application to associate this file type with.</span></span> <span data-ttu-id="4396c-111">不能指定 PROGID。</span><span class="sxs-lookup"><span data-stu-id="4396c-111">Cannot be specified with PROGID.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4396c-112">/ICON &lt; 图标-pathname&gt;</span><span class="sxs-lookup"><span data-stu-id="4396c-112">/ICON &lt;icon-pathname&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="4396c-113">图标文件的路径或 URL。</span><span class="sxs-lookup"><span data-stu-id="4396c-113">The path or URL for the icon file.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4396c-114">/DESCRIPTION &lt; 类型-desc&gt;</span><span class="sxs-lookup"><span data-stu-id="4396c-114">/DESCRIPTION &lt;type-desc&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="4396c-115">文件类型的用户友好名称。</span><span class="sxs-lookup"><span data-stu-id="4396c-115">The user-friendly name for the file type.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4396c-116">/CONTENT-TYPE &lt; 内容类型&gt;</span><span class="sxs-lookup"><span data-stu-id="4396c-116">/CONTENT-TYPE &lt;content-type&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="4396c-117">文件的内容类型。</span><span class="sxs-lookup"><span data-stu-id="4396c-117">The content type of the file.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4396c-118">/GLOBAL</span><span class="sxs-lookup"><span data-stu-id="4396c-118">/GLOBAL</span></span></p></td>
<td align="left"><p><span data-ttu-id="4396c-119">如果存在，则指示应编辑适用于所有用户的关联，而不是特定于用户的关联。</span><span class="sxs-lookup"><span data-stu-id="4396c-119">If present, indicates that the association that applies to all users should be edited, not the user-specific one.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4396c-120">/PERCEIVED-TYPE &lt; 感知-类型&gt;</span><span class="sxs-lookup"><span data-stu-id="4396c-120">/PERCEIVED-TYPE &lt;perceived-type&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="4396c-121">文件的假设类型。</span><span class="sxs-lookup"><span data-stu-id="4396c-121">The perceived type of the file.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4396c-122">/PROGID &lt; PROGID&gt;</span><span class="sxs-lookup"><span data-stu-id="4396c-122">/PROGID &lt;progid&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="4396c-123">指示扩展应与不同的文件类型相关联。</span><span class="sxs-lookup"><span data-stu-id="4396c-123">Indicates that the extension should be associated with a different file type.</span></span> <span data-ttu-id="4396c-124">以前的文件类型不会被删除。</span><span class="sxs-lookup"><span data-stu-id="4396c-124">The previous file type is not deleted.</span></span> <span data-ttu-id="4396c-125">不能指定应用、ICON、DESCRIPTION、CONFIRMOPEN 或 SHOWEXT。</span><span class="sxs-lookup"><span data-stu-id="4396c-125">Cannot be specified with APP, ICON, DESCRIPTION, CONFIRMOPEN, or SHOWEXT.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4396c-126">/CONFIRMOPEN</span><span class="sxs-lookup"><span data-stu-id="4396c-126">/CONFIRMOPEN</span></span></p></td>
<td align="left"><p><span data-ttu-id="4396c-127">指示是否应询问用户是否要打开或保存此类文件。</span><span class="sxs-lookup"><span data-stu-id="4396c-127">Indicates whether users downloading a file of this type should be asked whether to open or save the file.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4396c-128">/SHOWEXT</span><span class="sxs-lookup"><span data-stu-id="4396c-128">/SHOWEXT</span></span></p></td>
<td align="left"><p><span data-ttu-id="4396c-129">指示是否应始终显示文件的扩展名，即使用户已请求隐藏所有扩展名也是如此。</span><span class="sxs-lookup"><span data-stu-id="4396c-129">Indicates whether the file's extension should always be shown, even if the user has requested that all extensions be hidden.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4396c-130">/NEWMENU</span><span class="sxs-lookup"><span data-stu-id="4396c-130">/NEWMENU</span></span></p></td>
<td align="left"><p><span data-ttu-id="4396c-131">指示是否应将某个条目添加到外壳的 " <strong> 新建" </strong> 菜单。</span><span class="sxs-lookup"><span data-stu-id="4396c-131">Indicates whether an entry should be added to the shell's <strong>New</strong> menu.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4396c-132">/LOG</span><span class="sxs-lookup"><span data-stu-id="4396c-132">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="4396c-133">如果指定，输出将记录到指定的路径名称。</span><span class="sxs-lookup"><span data-stu-id="4396c-133">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4396c-134">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="4396c-134">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="4396c-135">如果指定，将在活动控制台窗口中显示输出（默认）。</span><span class="sxs-lookup"><span data-stu-id="4396c-135">If specified, output is presented in the active console window (default).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4396c-136">/GUI</span><span class="sxs-lookup"><span data-stu-id="4396c-136">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="4396c-137">如果指定，将在 Windows 对话框中显示输出。</span><span class="sxs-lookup"><span data-stu-id="4396c-137">If specified, output is presented in a Windows dialog box.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="4396c-138">对于版本4.6，已添加以下选项。</span><span class="sxs-lookup"><span data-stu-id="4396c-138">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4396c-139">/LOGU</span><span class="sxs-lookup"><span data-stu-id="4396c-139">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="4396c-140">如果指定，将以 UNICODE 格式将输出记录到指定的路径名称。</span><span class="sxs-lookup"><span data-stu-id="4396c-140">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="4396c-141">相关主题</span><span class="sxs-lookup"><span data-stu-id="4396c-141">Related topics</span></span>


[<span data-ttu-id="4396c-142">SFTMIME 命令引用</span><span class="sxs-lookup"><span data-stu-id="4396c-142">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





