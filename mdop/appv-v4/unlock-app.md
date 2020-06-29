---
title: UNLOCK APP
description: UNLOCK APP
author: dansimp
ms.assetid: 91fc8ceb-b4f5-4a06-8193-05189f830943
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2ea47191450014856b4a9823728e3e275c7fb4cf
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798712"
---
# <span data-ttu-id="9574a-103">UNLOCK APP</span><span class="sxs-lookup"><span data-stu-id="9574a-103">UNLOCK APP</span></span>


<span data-ttu-id="9574a-104">解除锁定文件系统缓存中指定的应用程序。</span><span class="sxs-lookup"><span data-stu-id="9574a-104">Unlocks the application specified in the file system cache.</span></span>

`SFTMIME UNLOCK APP:application [/LOG log-pathname | /CONSOLE | /GUI]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="9574a-105">参数</span><span class="sxs-lookup"><span data-stu-id="9574a-105">Parameter</span></span></th>
<th align="left"><span data-ttu-id="9574a-106">描述</span><span class="sxs-lookup"><span data-stu-id="9574a-106">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9574a-107">应用： &lt; 应用程序&gt;</span><span class="sxs-lookup"><span data-stu-id="9574a-107">APP:&lt;application&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="9574a-108">要解锁的应用程序的名称和版本（可选）。</span><span class="sxs-lookup"><span data-stu-id="9574a-108">The name and version (optional) of the application to unlock.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9574a-109">/LOG</span><span class="sxs-lookup"><span data-stu-id="9574a-109">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="9574a-110">如果指定，输出将记录到指定的路径名称。</span><span class="sxs-lookup"><span data-stu-id="9574a-110">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9574a-111">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="9574a-111">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="9574a-112">如果指定，将在活动控制台窗口中显示输出（默认）。</span><span class="sxs-lookup"><span data-stu-id="9574a-112">If specified, output is presented in the active console window (default).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9574a-113">/GUI</span><span class="sxs-lookup"><span data-stu-id="9574a-113">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="9574a-114">如果指定，将在 Windows 对话框中显示输出。</span><span class="sxs-lookup"><span data-stu-id="9574a-114">If specified, output is presented in a Windows dialog box.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="9574a-115">对于版本4.6，已添加以下选项。</span><span class="sxs-lookup"><span data-stu-id="9574a-115">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9574a-116">/LOGU</span><span class="sxs-lookup"><span data-stu-id="9574a-116">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="9574a-117">如果指定，将以 UNICODE 格式将输出记录到指定的路径名称。</span><span class="sxs-lookup"><span data-stu-id="9574a-117">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="9574a-118">相关主题</span><span class="sxs-lookup"><span data-stu-id="9574a-118">Related topics</span></span>


[<span data-ttu-id="9574a-119">SFTMIME 命令引用</span><span class="sxs-lookup"><span data-stu-id="9574a-119">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





