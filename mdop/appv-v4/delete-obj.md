---
title: DELETE OBJ
description: DELETE OBJ
author: dansimp
ms.assetid: fb17a261-f378-4ce6-a538-ab2f0ada0f2d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4d74fc1ac098d7dc4dd2f28633e9ca58d4211d74
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803021"
---
# <span data-ttu-id="b20ba-103">DELETE OBJ</span><span class="sxs-lookup"><span data-stu-id="b20ba-103">DELETE OBJ</span></span>


<span data-ttu-id="b20ba-104">删除所有应用程序记录。</span><span class="sxs-lookup"><span data-stu-id="b20ba-104">Removes all of your application records.</span></span>

`SFTMIME DELETE OBJ:APP [/GLOBAL] [/LOG log-pathname | /CONSOLE | /GUI]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="b20ba-105">参数</span><span class="sxs-lookup"><span data-stu-id="b20ba-105">Parameter</span></span></th>
<th align="left"><span data-ttu-id="b20ba-106">描述</span><span class="sxs-lookup"><span data-stu-id="b20ba-106">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b20ba-107">/GLOBAL</span><span class="sxs-lookup"><span data-stu-id="b20ba-107">/GLOBAL</span></span></p></td>
<td align="left"><p><span data-ttu-id="b20ba-108">如果指定，将删除所有应用程序。</span><span class="sxs-lookup"><span data-stu-id="b20ba-108">If specified, all applications are removed.</span></span> <span data-ttu-id="b20ba-109">默认情况下，仅删除当前用户有权访问的应用程序。</span><span class="sxs-lookup"><span data-stu-id="b20ba-109">By default, only applications the current user has access to are removed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b20ba-110">/LOG</span><span class="sxs-lookup"><span data-stu-id="b20ba-110">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="b20ba-111">如果指定，输出将记录到指定的路径名称。</span><span class="sxs-lookup"><span data-stu-id="b20ba-111">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b20ba-112">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="b20ba-112">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="b20ba-113">如果指定，将在活动控制台窗口中显示输出（默认）。</span><span class="sxs-lookup"><span data-stu-id="b20ba-113">If specified, output is presented in the active console window (default).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b20ba-114">/GUI</span><span class="sxs-lookup"><span data-stu-id="b20ba-114">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="b20ba-115">如果指定，将在 Windows 对话框中显示输出。</span><span class="sxs-lookup"><span data-stu-id="b20ba-115">If specified, output is presented in a Windows dialog box.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="b20ba-116">对于版本4.6，已添加以下选项。</span><span class="sxs-lookup"><span data-stu-id="b20ba-116">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b20ba-117">/LOGU</span><span class="sxs-lookup"><span data-stu-id="b20ba-117">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="b20ba-118">如果指定，将以 UNICODE 格式将输出记录到指定的路径名称。</span><span class="sxs-lookup"><span data-stu-id="b20ba-118">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="b20ba-119">相关主题</span><span class="sxs-lookup"><span data-stu-id="b20ba-119">Related topics</span></span>


[<span data-ttu-id="b20ba-120">SFTMIME 命令引用</span><span class="sxs-lookup"><span data-stu-id="b20ba-120">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





