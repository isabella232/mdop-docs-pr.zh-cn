---
title: LOCK APP
description: LOCK APP
author: dansimp
ms.assetid: 30673433-4364-499f-8116-cb135fe2716f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 319271640c2550fc94479e876a59b30d3b2bf7ae
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798932"
---
# <span data-ttu-id="88777-103">LOCK APP</span><span class="sxs-lookup"><span data-stu-id="88777-103">LOCK APP</span></span>


<span data-ttu-id="88777-104">锁定在文件系统缓存中指定的应用程序。</span><span class="sxs-lookup"><span data-stu-id="88777-104">Locks the application specified in the file system cache.</span></span>

`SFTMIME LOCK APP:application [/LOG log-pathname | /CONSOLE | /GUI]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="88777-105">参数</span><span class="sxs-lookup"><span data-stu-id="88777-105">Parameter</span></span></th>
<th align="left"><span data-ttu-id="88777-106">描述</span><span class="sxs-lookup"><span data-stu-id="88777-106">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="88777-107">应用： &lt; 应用程序&gt;</span><span class="sxs-lookup"><span data-stu-id="88777-107">APP:&lt;application&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="88777-108">要锁定的应用程序的名称和版本（可选）。</span><span class="sxs-lookup"><span data-stu-id="88777-108">The name and version (optional) of the application to lock.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="88777-109">/LOG</span><span class="sxs-lookup"><span data-stu-id="88777-109">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="88777-110">如果指定，输出将记录到指定的路径名称。</span><span class="sxs-lookup"><span data-stu-id="88777-110">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="88777-111">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="88777-111">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="88777-112">如果指定，将在活动控制台窗口中显示输出（默认）。</span><span class="sxs-lookup"><span data-stu-id="88777-112">If specified, output is presented in the active console window (default).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="88777-113">/GUI</span><span class="sxs-lookup"><span data-stu-id="88777-113">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="88777-114">如果指定，将在 Windows 对话框中显示输出。</span><span class="sxs-lookup"><span data-stu-id="88777-114">If specified, output is presented in a Windows dialog box.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="88777-115">对于版本4.6，已添加以下选项。</span><span class="sxs-lookup"><span data-stu-id="88777-115">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="88777-116">/LOGU</span><span class="sxs-lookup"><span data-stu-id="88777-116">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="88777-117">如果指定，将以 UNICODE 格式将输出记录到指定的路径名称。</span><span class="sxs-lookup"><span data-stu-id="88777-117">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="88777-118">相关主题</span><span class="sxs-lookup"><span data-stu-id="88777-118">Related topics</span></span>


[<span data-ttu-id="88777-119">SFTMIME 命令引用</span><span class="sxs-lookup"><span data-stu-id="88777-119">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





