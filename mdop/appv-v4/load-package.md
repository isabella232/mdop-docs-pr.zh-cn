---
title: LOAD PACKAGE
description: LOAD PACKAGE
author: dansimp
ms.assetid: eb19116d-e5d0-445c-b2f0-3116a09384d7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 938aa92696c8530c91d9a7acaac42408de534edc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798931"
---
# <span data-ttu-id="f01c5-103">LOAD PACKAGE</span><span class="sxs-lookup"><span data-stu-id="f01c5-103">LOAD PACKAGE</span></span>


<span data-ttu-id="f01c5-104">将指定的程序包加载到文件系统缓存中。</span><span class="sxs-lookup"><span data-stu-id="f01c5-104">Loads the specified package into the file system cache.</span></span>

`SFTMIME LOAD PACKAGE:package-name [/SFTPATH sft-pathname]                 [/LOG log-pathname | /CONSOLE | /GUI]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="f01c5-105">参数</span><span class="sxs-lookup"><span data-stu-id="f01c5-105">Parameter</span></span></th>
<th align="left"><span data-ttu-id="f01c5-106">描述</span><span class="sxs-lookup"><span data-stu-id="f01c5-106">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f01c5-107">程序包： &lt; 软件包-name&gt;</span><span class="sxs-lookup"><span data-stu-id="f01c5-107">PACKAGE:&lt;package-name&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="f01c5-108">要加载的程序包的名称。</span><span class="sxs-lookup"><span data-stu-id="f01c5-108">The name of the package to load.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f01c5-109">/SFTPATH &lt; sft-pathname&gt;</span><span class="sxs-lookup"><span data-stu-id="f01c5-109">/SFTPATH &lt;sft-pathname&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="f01c5-110">如果指定，则为要从中加载的 SFT 文件的路径。</span><span class="sxs-lookup"><span data-stu-id="f01c5-110">If specified, the path to an SFT file to load from.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f01c5-111">/LOG</span><span class="sxs-lookup"><span data-stu-id="f01c5-111">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="f01c5-112">如果指定，输出将记录到指定的路径名称。</span><span class="sxs-lookup"><span data-stu-id="f01c5-112">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f01c5-113">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="f01c5-113">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="f01c5-114">如果指定，将在活动控制台窗口中显示输出（默认）。</span><span class="sxs-lookup"><span data-stu-id="f01c5-114">If specified, output is presented in the active console window (default).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f01c5-115">/GUI</span><span class="sxs-lookup"><span data-stu-id="f01c5-115">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="f01c5-116">如果指定，将在 Windows 对话框中显示输出。</span><span class="sxs-lookup"><span data-stu-id="f01c5-116">If specified, output is presented in a Windows dialog box.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="f01c5-117">对于版本4.6，已添加以下选项。</span><span class="sxs-lookup"><span data-stu-id="f01c5-117">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f01c5-118">/LOGU</span><span class="sxs-lookup"><span data-stu-id="f01c5-118">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="f01c5-119">如果指定，将以 UNICODE 格式将输出记录到指定的路径名称。</span><span class="sxs-lookup"><span data-stu-id="f01c5-119">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="f01c5-120">**注意** 如果未指定 SFTPATH，客户端将通过使用已配置为使用的路径（基于 OSD 文件、ApplicationSourceRoot 注册表项值或 OverrideURL 设置）来加载程序包。</span><span class="sxs-lookup"><span data-stu-id="f01c5-120">**Note** If no SFTPATH is specified, the client will load the package by using the path it has been configured to use, based on the OSD file, the ApplicationSourceRoot registry key value, or the OverrideURL setting.</span></span>

<span data-ttu-id="f01c5-121">"**加载包**" 命令执行同步加载，并且在程序包完全加载或遇到错误情况之前将不会完成。</span><span class="sxs-lookup"><span data-stu-id="f01c5-121">The **LOAD PACKAGE** command performs a synchronous load and will not be complete until the package is fully loaded or until it encounters an error condition.</span></span>

 

## <span data-ttu-id="f01c5-122">相关主题</span><span class="sxs-lookup"><span data-stu-id="f01c5-122">Related topics</span></span>


[<span data-ttu-id="f01c5-123">SFTMIME 命令引用</span><span class="sxs-lookup"><span data-stu-id="f01c5-123">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





