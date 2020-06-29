---
title: PUBLISH APP
description: PUBLISH APP
author: dansimp
ms.assetid: f25f06a8-ca23-435b-a0c2-16a5f39b6b97
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b2ccb19255786ee47a8356feef14be1c4d9b4fb2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798847"
---
# <span data-ttu-id="d3dd3-103">PUBLISH APP</span><span class="sxs-lookup"><span data-stu-id="d3dd3-103">PUBLISH APP</span></span>


<span data-ttu-id="d3dd3-104">将应用程序快捷方式发布到用户的 "开始" 菜单、"桌面" 或其他指定位置。</span><span class="sxs-lookup"><span data-stu-id="d3dd3-104">Publishes an application shortcut to the user's Start menu, desktop, or other specified location.</span></span>

`SFTMIME PUBLISH APP:application                 {/DESKTOP | /START | /TARGET target-path} [/ICON icon-pathname]                 [/DISPLAY display-name] [/ARGS command-args...]                 [/LOG log-pathname | /CONSOLE | /GUI]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="d3dd3-105">参数</span><span class="sxs-lookup"><span data-stu-id="d3dd3-105">Parameter</span></span></th>
<th align="left"><span data-ttu-id="d3dd3-106">描述</span><span class="sxs-lookup"><span data-stu-id="d3dd3-106">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d3dd3-107">应用程序： &lt; 应用程序&gt;</span><span class="sxs-lookup"><span data-stu-id="d3dd3-107">APPLICATION:&lt;application&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="d3dd3-108">应用程序的名称和版本（可选）。</span><span class="sxs-lookup"><span data-stu-id="d3dd3-108">The name and version (optional) of the application.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d3dd3-109">/DESKTOP</span><span class="sxs-lookup"><span data-stu-id="d3dd3-109">/DESKTOP</span></span></p></td>
<td align="left"><p><span data-ttu-id="d3dd3-110">发布用户桌面的快捷方式。</span><span class="sxs-lookup"><span data-stu-id="d3dd3-110">Publishes a shortcut to the user's desktop.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d3dd3-111">/START</span><span class="sxs-lookup"><span data-stu-id="d3dd3-111">/START</span></span></p></td>
<td align="left"><p><span data-ttu-id="d3dd3-112">发布 "开始" 菜单的 "程序" 文件夹中的 "应用程序虚拟化应用程序" 文件夹的快捷方式。</span><span class="sxs-lookup"><span data-stu-id="d3dd3-112">Publishes a shortcut to the Application Virtualization Applications folder in the Programs folder of the Start menu.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d3dd3-113">/TARGET &lt; 目标路径&gt;</span><span class="sxs-lookup"><span data-stu-id="d3dd3-113">/TARGET &lt;target-path&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="d3dd3-114">应在其中发布快捷方式的绝对路径。</span><span class="sxs-lookup"><span data-stu-id="d3dd3-114">The absolute path where the shortcut should be published.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d3dd3-115">/ICON &lt; 图标-pathname&gt;</span><span class="sxs-lookup"><span data-stu-id="d3dd3-115">/ICON &lt;icon-pathname&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="d3dd3-116">图标文件的路径或 URL。</span><span class="sxs-lookup"><span data-stu-id="d3dd3-116">The path or URL for the icon file.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d3dd3-117">/DISPLAY &lt; 显示名称&gt;</span><span class="sxs-lookup"><span data-stu-id="d3dd3-117">/DISPLAY &lt;display-name&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="d3dd3-118">快捷方式的显示名称。</span><span class="sxs-lookup"><span data-stu-id="d3dd3-118">The display name for the shortcut.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d3dd3-119">/ARGS &lt; 命令-参数&gt;</span><span class="sxs-lookup"><span data-stu-id="d3dd3-119">/ARGS &lt;command-args&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="d3dd3-120">要传递到应用程序的参数。</span><span class="sxs-lookup"><span data-stu-id="d3dd3-120">Parameters to be passed to the application.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d3dd3-121">/LOG</span><span class="sxs-lookup"><span data-stu-id="d3dd3-121">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="d3dd3-122">如果指定，输出将记录到指定的路径名称。</span><span class="sxs-lookup"><span data-stu-id="d3dd3-122">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d3dd3-123">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="d3dd3-123">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="d3dd3-124">如果指定，将在活动控制台窗口中显示输出（默认）。</span><span class="sxs-lookup"><span data-stu-id="d3dd3-124">If specified, output is presented in the active console window (default).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d3dd3-125">/GUI</span><span class="sxs-lookup"><span data-stu-id="d3dd3-125">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="d3dd3-126">如果指定，将在 Windows 对话框中显示输出。</span><span class="sxs-lookup"><span data-stu-id="d3dd3-126">If specified, output is presented in a Windows dialog box.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="d3dd3-127">对于版本4.6，已添加以下选项。</span><span class="sxs-lookup"><span data-stu-id="d3dd3-127">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d3dd3-128">/LOGU</span><span class="sxs-lookup"><span data-stu-id="d3dd3-128">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="d3dd3-129">如果指定，将以 UNICODE 格式将输出记录到指定的路径名称。</span><span class="sxs-lookup"><span data-stu-id="d3dd3-129">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="d3dd3-130">相关主题</span><span class="sxs-lookup"><span data-stu-id="d3dd3-130">Related topics</span></span>


[<span data-ttu-id="d3dd3-131">SFTMIME 命令引用</span><span class="sxs-lookup"><span data-stu-id="d3dd3-131">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





