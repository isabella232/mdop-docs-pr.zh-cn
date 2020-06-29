---
title: UNLOAD PACKAGE
description: UNLOAD PACKAGE
author: dansimp
ms.assetid: a076eb5a-ce3d-49e4-ac7a-4d4df10e3477
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fbee040f97bf5675ace7e873741a4270a993a911
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798713"
---
# <span data-ttu-id="c50ed-103">UNLOAD PACKAGE</span><span class="sxs-lookup"><span data-stu-id="c50ed-103">UNLOAD PACKAGE</span></span>


<span data-ttu-id="c50ed-104">从文件系统缓存卸载程序包。</span><span class="sxs-lookup"><span data-stu-id="c50ed-104">Unloads the package from the file system cache.</span></span>

`SFTMIME UNLOAD PACKAGE:package-name [/LOG log-pathname | /CONSOLE | /GUI]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="c50ed-105">参数</span><span class="sxs-lookup"><span data-stu-id="c50ed-105">Parameter</span></span></th>
<th align="left"><span data-ttu-id="c50ed-106">描述</span><span class="sxs-lookup"><span data-stu-id="c50ed-106">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c50ed-107">程序包： &lt; 软件包-name&gt;</span><span class="sxs-lookup"><span data-stu-id="c50ed-107">PACKAGE:&lt;package-name&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="c50ed-108">要卸载的程序包的名称。</span><span class="sxs-lookup"><span data-stu-id="c50ed-108">The name of the package to unload.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c50ed-109">/LOG</span><span class="sxs-lookup"><span data-stu-id="c50ed-109">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="c50ed-110">如果指定，输出将记录到指定的路径名称。</span><span class="sxs-lookup"><span data-stu-id="c50ed-110">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c50ed-111">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="c50ed-111">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="c50ed-112">如果指定，将在活动控制台窗口中显示输出（默认）。</span><span class="sxs-lookup"><span data-stu-id="c50ed-112">If specified, output is presented in the active console window (default).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c50ed-113">/GUI</span><span class="sxs-lookup"><span data-stu-id="c50ed-113">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="c50ed-114">如果指定，将在 Windows 对话框中显示输出。</span><span class="sxs-lookup"><span data-stu-id="c50ed-114">If specified, output is presented in a Windows dialog box.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="c50ed-115">对于版本4.6，已添加以下选项。</span><span class="sxs-lookup"><span data-stu-id="c50ed-115">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c50ed-116">/LOGU</span><span class="sxs-lookup"><span data-stu-id="c50ed-116">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="c50ed-117">如果指定，将以 UNICODE 格式将输出记录到指定的路径名称。</span><span class="sxs-lookup"><span data-stu-id="c50ed-117">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="c50ed-118">相关主题</span><span class="sxs-lookup"><span data-stu-id="c50ed-118">Related topics</span></span>


[<span data-ttu-id="c50ed-119">SFTMIME 命令引用</span><span class="sxs-lookup"><span data-stu-id="c50ed-119">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





