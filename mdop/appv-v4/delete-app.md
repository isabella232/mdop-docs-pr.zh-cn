---
title: DELETE APP
description: DELETE APP
author: dansimp
ms.assetid: 2f89c0c0-373b-4389-a26d-67b3f9712957
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c27c70ef3227ebaf6b16bcb1fbb4b4e65b7cb7f4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803024"
---
# <span data-ttu-id="c44db-103">DELETE APP</span><span class="sxs-lookup"><span data-stu-id="c44db-103">DELETE APP</span></span>


<span data-ttu-id="c44db-104">从文件系统缓存中删除应用程序记录，以使其不再可见。</span><span class="sxs-lookup"><span data-stu-id="c44db-104">Removes an application record from the file system cache to make it no longer visible.</span></span> <span data-ttu-id="c44db-105">用户的快捷方式和文件类型关联已隐藏，但未被删除。</span><span class="sxs-lookup"><span data-stu-id="c44db-105">Users’ shortcuts and file type associations are hidden but not deleted.</span></span> <span data-ttu-id="c44db-106">不会删除任何用户设置。</span><span class="sxs-lookup"><span data-stu-id="c44db-106">No user settings are removed.</span></span>

`SFTMIME DELETE APP:application [/LOG log-pathname | /CONSOLE | /GUI]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="c44db-107">参数</span><span class="sxs-lookup"><span data-stu-id="c44db-107">Parameter</span></span></th>
<th align="left"><span data-ttu-id="c44db-108">描述</span><span class="sxs-lookup"><span data-stu-id="c44db-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c44db-109">应用： &lt; 应用程序&gt;</span><span class="sxs-lookup"><span data-stu-id="c44db-109">APP:&lt;application&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="c44db-110">要删除的应用程序的名称和版本（可选）。</span><span class="sxs-lookup"><span data-stu-id="c44db-110">The name and version (optional) of the application to be removed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c44db-111">/LOG</span><span class="sxs-lookup"><span data-stu-id="c44db-111">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="c44db-112">如果指定，输出将记录到指定的路径名称。</span><span class="sxs-lookup"><span data-stu-id="c44db-112">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c44db-113">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="c44db-113">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="c44db-114">如果指定，将在活动控制台窗口中显示输出（默认）。</span><span class="sxs-lookup"><span data-stu-id="c44db-114">If specified, output is presented in the active console window (default).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c44db-115">/GUI</span><span class="sxs-lookup"><span data-stu-id="c44db-115">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="c44db-116">如果指定，将在 Windows 对话框中显示输出。</span><span class="sxs-lookup"><span data-stu-id="c44db-116">If specified, output is presented in a Windows dialog box.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="c44db-117">对于版本4.6，已添加以下选项。</span><span class="sxs-lookup"><span data-stu-id="c44db-117">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c44db-118">/LOGU</span><span class="sxs-lookup"><span data-stu-id="c44db-118">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="c44db-119">如果指定，将以 UNICODE 格式将输出记录到指定的路径名称。</span><span class="sxs-lookup"><span data-stu-id="c44db-119">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="c44db-120">相关主题</span><span class="sxs-lookup"><span data-stu-id="c44db-120">Related topics</span></span>


[<span data-ttu-id="c44db-121">SFTMIME 命令引用</span><span class="sxs-lookup"><span data-stu-id="c44db-121">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





