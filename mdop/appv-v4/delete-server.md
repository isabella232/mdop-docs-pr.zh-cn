---
title: DELETE SERVER
description: DELETE SERVER
author: dansimp
ms.assetid: 4c929639-1c1d-47c3-9225-cc4d7a8736f0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 92af31a818174fb4b0e82a11c918af2484ac2bce
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803019"
---
# <span data-ttu-id="18cae-103">DELETE SERVER</span><span class="sxs-lookup"><span data-stu-id="18cae-103">DELETE SERVER</span></span>


<span data-ttu-id="18cae-104">删除发布服务器。</span><span class="sxs-lookup"><span data-stu-id="18cae-104">Removes a publishing server.</span></span>

<span data-ttu-id="18cae-105">**注意** 此命令不会删除服务器发布到客户端的任何应用程序或程序包。</span><span class="sxs-lookup"><span data-stu-id="18cae-105">**Note** This command does not remove any applications or packages published to the client by the server.</span></span> <span data-ttu-id="18cae-106">对于每个应用程序，使用 SFTMIME **CLEAR 应用**命令，后跟**DELETE 程序包**命令，从客户端完全删除这些应用程序和程序包。</span><span class="sxs-lookup"><span data-stu-id="18cae-106">For each application, use the SFTMIME **CLEAR APP** command followed by the **DELETE PACKAGE** command to completely remove those applications and packages from the client.</span></span>

 

`SFTMIME DELETE SERVER:server-name [/LOG log-pathname | /CONSOLE | /GUI]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="18cae-107">参数</span><span class="sxs-lookup"><span data-stu-id="18cae-107">Parameter</span></span></th>
<th align="left"><span data-ttu-id="18cae-108">描述</span><span class="sxs-lookup"><span data-stu-id="18cae-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="18cae-109">服务器： &lt; 服务器名称&gt;</span><span class="sxs-lookup"><span data-stu-id="18cae-109">SERVER:&lt;server-name&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="18cae-110">发布服务器的显示名称。</span><span class="sxs-lookup"><span data-stu-id="18cae-110">The display name of the publishing server.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="18cae-111">/LOG</span><span class="sxs-lookup"><span data-stu-id="18cae-111">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="18cae-112">如果指定，输出将记录到指定的路径名称。</span><span class="sxs-lookup"><span data-stu-id="18cae-112">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="18cae-113">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="18cae-113">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="18cae-114">如果指定，将在活动控制台窗口中显示输出（默认）。</span><span class="sxs-lookup"><span data-stu-id="18cae-114">If specified, output is presented in the active console window (default).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="18cae-115">/GUI</span><span class="sxs-lookup"><span data-stu-id="18cae-115">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="18cae-116">如果指定，将在 Windows 对话框中显示输出。</span><span class="sxs-lookup"><span data-stu-id="18cae-116">If specified, output is presented in a Windows dialog box.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="18cae-117">对于版本4.6，已添加以下选项。</span><span class="sxs-lookup"><span data-stu-id="18cae-117">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="18cae-118">/LOGU</span><span class="sxs-lookup"><span data-stu-id="18cae-118">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="18cae-119">如果指定，将以 UNICODE 格式将输出记录到指定的路径名称。</span><span class="sxs-lookup"><span data-stu-id="18cae-119">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="18cae-120">相关主题</span><span class="sxs-lookup"><span data-stu-id="18cae-120">Related topics</span></span>


[<span data-ttu-id="18cae-121">SFTMIME 命令引用</span><span class="sxs-lookup"><span data-stu-id="18cae-121">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





