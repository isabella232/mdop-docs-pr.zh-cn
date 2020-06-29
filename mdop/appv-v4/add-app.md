---
title: ADD APP
description: ADD APP
author: dansimp
ms.assetid: 329fd0c8-a795-49be-b0fd-1367c5b4a34b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ac83c0cf130e8de1d34d42d74e946716e4503246
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802400"
---
# <span data-ttu-id="b32ae-103">ADD APP</span><span class="sxs-lookup"><span data-stu-id="b32ae-103">ADD APP</span></span>


<span data-ttu-id="b32ae-104">添加应用程序记录。</span><span class="sxs-lookup"><span data-stu-id="b32ae-104">Adds an application record.</span></span>

`SFTMIME ADD APP:application /OSD osd-pathname [/ICON icon-pathname] [/LOG log-pathname | /CONSOLE | /GUI]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="b32ae-105">参数</span><span class="sxs-lookup"><span data-stu-id="b32ae-105">Parameter</span></span></th>
<th align="left"><span data-ttu-id="b32ae-106">描述</span><span class="sxs-lookup"><span data-stu-id="b32ae-106">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b32ae-107">应用： &lt; 应用程序&gt;</span><span class="sxs-lookup"><span data-stu-id="b32ae-107">APP:&lt;application&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="b32ae-108">应用程序的名称和版本（可选）。</span><span class="sxs-lookup"><span data-stu-id="b32ae-108">The name and version (optional) of the application.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b32ae-109">/OSD &lt; OSD-路径名&gt;</span><span class="sxs-lookup"><span data-stu-id="b32ae-109">/OSD &lt;osd-pathname&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="b32ae-110">OSD 文件的路径或 URL。</span><span class="sxs-lookup"><span data-stu-id="b32ae-110">The path or URL for the OSD file.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b32ae-111">/ICON &lt; 图标-pathname&gt;</span><span class="sxs-lookup"><span data-stu-id="b32ae-111">/ICON &lt;icon-pathname&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="b32ae-112">图标文件的路径或 URL。</span><span class="sxs-lookup"><span data-stu-id="b32ae-112">The path or URL for the icon file.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b32ae-113">/LOG</span><span class="sxs-lookup"><span data-stu-id="b32ae-113">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="b32ae-114">如果指定，输出将记录到指定的路径名称。</span><span class="sxs-lookup"><span data-stu-id="b32ae-114">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b32ae-115">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="b32ae-115">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="b32ae-116">如果指定，将在活动控制台窗口中显示输出（默认）。</span><span class="sxs-lookup"><span data-stu-id="b32ae-116">If specified, output is presented in the active console window (default).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b32ae-117">/GUI</span><span class="sxs-lookup"><span data-stu-id="b32ae-117">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="b32ae-118">如果指定，将在 Windows 对话框中显示输出。</span><span class="sxs-lookup"><span data-stu-id="b32ae-118">If specified, output is presented in a Windows dialog box.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="b32ae-119">对于版本4.6，已添加以下选项。</span><span class="sxs-lookup"><span data-stu-id="b32ae-119">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b32ae-120">/LOGU</span><span class="sxs-lookup"><span data-stu-id="b32ae-120">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="b32ae-121">如果指定，将以 UNICODE 格式将输出记录到指定的路径名称。</span><span class="sxs-lookup"><span data-stu-id="b32ae-121">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="b32ae-122">**注意** 应用程序的结果名称将从 OSD 文件中获取，而不是从应用：应用程序中提供的名称中获取 &lt; &gt; 。</span><span class="sxs-lookup"><span data-stu-id="b32ae-122">**Note** The resulting name of the application will be taken from the OSD file and not from the name provided in APP:&lt;application&gt;.</span></span>

 

## <span data-ttu-id="b32ae-123">相关主题</span><span class="sxs-lookup"><span data-stu-id="b32ae-123">Related topics</span></span>


[<span data-ttu-id="b32ae-124">SFTMIME 命令引用</span><span class="sxs-lookup"><span data-stu-id="b32ae-124">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





