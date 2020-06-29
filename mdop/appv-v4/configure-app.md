---
title: CONFIGURE APP
description: CONFIGURE APP
author: dansimp
ms.assetid: fcfb4f86-8b7c-4208-bca3-955fd067079f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 42ff17e180df262deed3fe79674ad6fda6f0be4e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802192"
---
# <span data-ttu-id="f702b-103">CONFIGURE APP</span><span class="sxs-lookup"><span data-stu-id="f702b-103">CONFIGURE APP</span></span>


<span data-ttu-id="f702b-104">使用户能够更改与应用程序关联的图标，但不会更新现有快捷方式或文件类型关联上的图标。</span><span class="sxs-lookup"><span data-stu-id="f702b-104">Enables the user to change the icon associated with an application but does not update the icon on existing shortcuts or file type associations.</span></span>

`SFTMIME CONFIGURE APP:application /ICON icon-pathname                 [/LOG log-pathname | /CONSOLE | /GUI]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="f702b-105">参数</span><span class="sxs-lookup"><span data-stu-id="f702b-105">Parameter</span></span></th>
<th align="left"><span data-ttu-id="f702b-106">描述</span><span class="sxs-lookup"><span data-stu-id="f702b-106">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f702b-107">应用： &lt; 应用程序&gt;</span><span class="sxs-lookup"><span data-stu-id="f702b-107">APP:&lt;application&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="f702b-108">应用程序的名称和版本（可选）。</span><span class="sxs-lookup"><span data-stu-id="f702b-108">The name and version (optional) of the application.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f702b-109">/ICON &lt; 图标-pathname&gt;</span><span class="sxs-lookup"><span data-stu-id="f702b-109">/ICON &lt;icon-pathname&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="f702b-110">图标文件的路径或 URL。</span><span class="sxs-lookup"><span data-stu-id="f702b-110">The path or URL for the icon file.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f702b-111">/LOG</span><span class="sxs-lookup"><span data-stu-id="f702b-111">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="f702b-112">如果指定，输出将记录到指定的路径名称。</span><span class="sxs-lookup"><span data-stu-id="f702b-112">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f702b-113">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="f702b-113">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="f702b-114">如果指定，将在活动控制台窗口中显示输出（默认）。</span><span class="sxs-lookup"><span data-stu-id="f702b-114">If specified, output is presented in the active console window (default).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f702b-115">/GUI</span><span class="sxs-lookup"><span data-stu-id="f702b-115">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="f702b-116">如果指定，将在 Windows 对话框中显示输出。</span><span class="sxs-lookup"><span data-stu-id="f702b-116">If specified, output is presented in a Windows dialog box.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="f702b-117">对于版本4.6，已添加以下选项。</span><span class="sxs-lookup"><span data-stu-id="f702b-117">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f702b-118">/LOGU</span><span class="sxs-lookup"><span data-stu-id="f702b-118">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="f702b-119">如果指定，将以 UNICODE 格式将输出记录到指定的路径名称。</span><span class="sxs-lookup"><span data-stu-id="f702b-119">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="f702b-120">相关主题</span><span class="sxs-lookup"><span data-stu-id="f702b-120">Related topics</span></span>


[<span data-ttu-id="f702b-121">SFTMIME 命令引用</span><span class="sxs-lookup"><span data-stu-id="f702b-121">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





