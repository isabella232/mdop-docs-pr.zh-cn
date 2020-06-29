---
title: DELETE TYPE
description: DELETE TYPE
author: dansimp
ms.assetid: f2852723-c894-49f3-a3c5-56f9648bb9ca
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0df68c0a0efcd0e269410d1580f7b0a82301c46d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803018"
---
# <span data-ttu-id="7592d-103">DELETE TYPE</span><span class="sxs-lookup"><span data-stu-id="7592d-103">DELETE TYPE</span></span>


<span data-ttu-id="7592d-104">删除指定的文件类型关联。</span><span class="sxs-lookup"><span data-stu-id="7592d-104">Removes the specified file type association.</span></span>

`SFTMIME DELETE TYPE:file-extension [/GLOBAL]                 [/LOG log-pathname | /CONSOLE | /GUI]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="7592d-105">参数</span><span class="sxs-lookup"><span data-stu-id="7592d-105">Parameter</span></span></th>
<th align="left"><span data-ttu-id="7592d-106">描述</span><span class="sxs-lookup"><span data-stu-id="7592d-106">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="7592d-107">类型： &lt; 文件扩展名&gt;</span><span class="sxs-lookup"><span data-stu-id="7592d-107">TYPE:&lt;file-extension&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="7592d-108">要删除的文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="7592d-108">The file name extension to be removed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="7592d-109">/GLOBAL</span><span class="sxs-lookup"><span data-stu-id="7592d-109">/GLOBAL</span></span></p></td>
<td align="left"><p><span data-ttu-id="7592d-110">如果已指定，则表示应删除文件扩展名的全局关联。</span><span class="sxs-lookup"><span data-stu-id="7592d-110">If specified, indicates that the global association for the file name extension should be removed.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="7592d-111">/LOG</span><span class="sxs-lookup"><span data-stu-id="7592d-111">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="7592d-112">如果指定，输出将记录到指定的路径名称。</span><span class="sxs-lookup"><span data-stu-id="7592d-112">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="7592d-113">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="7592d-113">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="7592d-114">如果指定，将在活动控制台窗口中显示输出（默认）。</span><span class="sxs-lookup"><span data-stu-id="7592d-114">If specified, output is presented in the active console window (default).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="7592d-115">/GUI</span><span class="sxs-lookup"><span data-stu-id="7592d-115">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="7592d-116">如果指定，将在 Windows 对话框中显示输出。</span><span class="sxs-lookup"><span data-stu-id="7592d-116">If specified, output is presented in a Windows dialog box.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="7592d-117">对于版本4.6，已添加以下选项。</span><span class="sxs-lookup"><span data-stu-id="7592d-117">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="7592d-118">/LOGU</span><span class="sxs-lookup"><span data-stu-id="7592d-118">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="7592d-119">如果指定，将以 UNICODE 格式将输出记录到指定的路径名称。</span><span class="sxs-lookup"><span data-stu-id="7592d-119">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="7592d-120">相关主题</span><span class="sxs-lookup"><span data-stu-id="7592d-120">Related topics</span></span>


[<span data-ttu-id="7592d-121">SFTMIME 命令引用</span><span class="sxs-lookup"><span data-stu-id="7592d-121">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





