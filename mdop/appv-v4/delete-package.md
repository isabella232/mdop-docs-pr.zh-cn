---
title: DELETE PACKAGE
description: DELETE PACKAGE
author: dansimp
ms.assetid: 8f7a4598-610d-490e-a224-426acce01a9f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a0051967ca308e88d143b8116330f5d770d6086d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803020"
---
# <span data-ttu-id="7c9cf-103">DELETE PACKAGE</span><span class="sxs-lookup"><span data-stu-id="7c9cf-103">DELETE PACKAGE</span></span>


<span data-ttu-id="7c9cf-104">删除软件包记录和与其关联的应用程序。</span><span class="sxs-lookup"><span data-stu-id="7c9cf-104">Removes a package record and the applications associated with it.</span></span>

`SFTMIME DELETE PACKAGE:package-name                 [/LOG log-pathname | /CONSOLE | /GUI]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="7c9cf-105">参数</span><span class="sxs-lookup"><span data-stu-id="7c9cf-105">Parameter</span></span></th>
<th align="left"><span data-ttu-id="7c9cf-106">描述</span><span class="sxs-lookup"><span data-stu-id="7c9cf-106">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="7c9cf-107">程序包： &lt; 软件包-name&gt;</span><span class="sxs-lookup"><span data-stu-id="7c9cf-107">PACKAGE:&lt;package-name&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="7c9cf-108">要删除的程序包的名称。</span><span class="sxs-lookup"><span data-stu-id="7c9cf-108">The name of the package to be removed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="7c9cf-109">/LOG</span><span class="sxs-lookup"><span data-stu-id="7c9cf-109">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="7c9cf-110">如果指定，输出将记录到指定的路径名称。</span><span class="sxs-lookup"><span data-stu-id="7c9cf-110">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="7c9cf-111">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="7c9cf-111">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="7c9cf-112">如果指定，将在活动控制台窗口中显示输出（默认）。</span><span class="sxs-lookup"><span data-stu-id="7c9cf-112">If specified, output is presented in the active console window (default).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="7c9cf-113">/GUI</span><span class="sxs-lookup"><span data-stu-id="7c9cf-113">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="7c9cf-114">如果指定，将在 Windows 对话框中显示输出。</span><span class="sxs-lookup"><span data-stu-id="7c9cf-114">If specified, output is presented in a Windows dialog box.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="7c9cf-115">对于版本4.6，已添加以下选项。</span><span class="sxs-lookup"><span data-stu-id="7c9cf-115">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="7c9cf-116">/LOGU</span><span class="sxs-lookup"><span data-stu-id="7c9cf-116">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="7c9cf-117">如果指定，将以 UNICODE 格式将输出记录到指定的路径名称。</span><span class="sxs-lookup"><span data-stu-id="7c9cf-117">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="7c9cf-118">**重要提示** "删除程序包" 命令始终执行程序包的全局删除，并仅删除全局文件类型和快捷方式。</span><span class="sxs-lookup"><span data-stu-id="7c9cf-118">**Important** The DELETE PACKAGE command always performs a global delete of the package and deletes only global file types and shortcuts.</span></span>

<span data-ttu-id="7c9cf-119">如果程序包是全局的，则必须以本地管理员身份运行此命令;否则，仅需要**DeleteApp**权限。</span><span class="sxs-lookup"><span data-stu-id="7c9cf-119">If the package is global, this command must be run as local Administrator; otherwise, only **DeleteApp** permission is needed.</span></span>

 

## <span data-ttu-id="7c9cf-120">相关主题</span><span class="sxs-lookup"><span data-stu-id="7c9cf-120">Related topics</span></span>


[<span data-ttu-id="7c9cf-121">SFTMIME 命令引用</span><span class="sxs-lookup"><span data-stu-id="7c9cf-121">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





