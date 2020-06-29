---
title: UNLOAD APP
description: UNLOAD APP
author: dansimp
ms.assetid: f0d729ae-8772-498b-be11-1a4b35499c53
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f1ae30f5b8c788f8763c2c2b9d1c1956182750d3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798714"
---
# <span data-ttu-id="0d11b-103">UNLOAD APP</span><span class="sxs-lookup"><span data-stu-id="0d11b-103">UNLOAD APP</span></span>


<span data-ttu-id="0d11b-104">从文件系统缓存卸载程序包中的应用程序和所有其他应用程序。</span><span class="sxs-lookup"><span data-stu-id="0d11b-104">Unloads the application and all other applications in the package from the file system cache.</span></span>

`SFTMIME UNLOAD APP:application [/LOG log-pathname | /CONSOLE | /GUI]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="0d11b-105">参数</span><span class="sxs-lookup"><span data-stu-id="0d11b-105">Parameter</span></span></th>
<th align="left"><span data-ttu-id="0d11b-106">描述</span><span class="sxs-lookup"><span data-stu-id="0d11b-106">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0d11b-107">应用： &lt; 应用程序&gt;</span><span class="sxs-lookup"><span data-stu-id="0d11b-107">APP:&lt;application&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="0d11b-108">要卸载的应用程序的名称和版本（可选）。</span><span class="sxs-lookup"><span data-stu-id="0d11b-108">The name and version (optional) of the application to unload.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0d11b-109">/LOG</span><span class="sxs-lookup"><span data-stu-id="0d11b-109">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="0d11b-110">如果指定，输出将记录到指定的路径名称。</span><span class="sxs-lookup"><span data-stu-id="0d11b-110">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0d11b-111">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="0d11b-111">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="0d11b-112">如果指定，将在活动控制台窗口中显示输出（默认）。</span><span class="sxs-lookup"><span data-stu-id="0d11b-112">If specified, output is presented in the active console window (default).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0d11b-113">/GUI</span><span class="sxs-lookup"><span data-stu-id="0d11b-113">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="0d11b-114">如果指定，将在 Windows 对话框中显示输出。</span><span class="sxs-lookup"><span data-stu-id="0d11b-114">If specified, output is presented in a Windows dialog box.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="0d11b-115">对于版本4.6，已添加以下选项。</span><span class="sxs-lookup"><span data-stu-id="0d11b-115">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0d11b-116">/LOGU</span><span class="sxs-lookup"><span data-stu-id="0d11b-116">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="0d11b-117">如果指定，将以 UNICODE 格式将输出记录到指定的路径名称。</span><span class="sxs-lookup"><span data-stu-id="0d11b-117">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="0d11b-118">相关主题</span><span class="sxs-lookup"><span data-stu-id="0d11b-118">Related topics</span></span>


[<span data-ttu-id="0d11b-119">SFTMIME 命令引用</span><span class="sxs-lookup"><span data-stu-id="0d11b-119">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





