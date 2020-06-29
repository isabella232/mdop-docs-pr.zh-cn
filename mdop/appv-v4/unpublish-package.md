---
title: UNPUBLISH PACKAGE
description: UNPUBLISH PACKAGE
author: dansimp
ms.assetid: 1651427c-72a5-4701-bb57-71e14a7a3803
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7704fb3ed03be4864a837767d9e890d28b63f175
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798710"
---
# <span data-ttu-id="51181-103">UNPUBLISH PACKAGE</span><span class="sxs-lookup"><span data-stu-id="51181-103">UNPUBLISH PACKAGE</span></span>


<span data-ttu-id="51181-104">允许删除整个程序包的快捷方式和文件类型。</span><span class="sxs-lookup"><span data-stu-id="51181-104">Enables you to remove the shortcuts and file types for an entire package.</span></span>

`SFTMIME UNPUBLISH PACKAGE:package-name [/CLEAR] [/GLOBAL]                 [/LOG log-pathname | /CONSOLE | /GUI]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="51181-105">参数</span><span class="sxs-lookup"><span data-stu-id="51181-105">Parameter</span></span></th>
<th align="left"><span data-ttu-id="51181-106">描述</span><span class="sxs-lookup"><span data-stu-id="51181-106">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="51181-107">程序包： &lt; 软件包-name&gt;</span><span class="sxs-lookup"><span data-stu-id="51181-107">PACKAGE:&lt;package-name&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="51181-108">程序包的名称。</span><span class="sxs-lookup"><span data-stu-id="51181-108">The name of the package.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="51181-109">/CLEAR</span><span class="sxs-lookup"><span data-stu-id="51181-109">/CLEAR</span></span></p></td>
<td align="left"><p><span data-ttu-id="51181-110">如果存在，用户设置也将被删除。</span><span class="sxs-lookup"><span data-stu-id="51181-110">If present, user settings will also be removed.</span></span> <span data-ttu-id="51181-111">（有关详细信息，请参阅本主题后面的重要说明。）</span><span class="sxs-lookup"><span data-stu-id="51181-111">(For more information, see the Important note later in this topic.)</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="51181-112">/GLOBAL</span><span class="sxs-lookup"><span data-stu-id="51181-112">/GLOBAL</span></span></p></td>
<td align="left"><p><span data-ttu-id="51181-113">如果存在，将取消发布此计算机上所有用户的程序包。</span><span class="sxs-lookup"><span data-stu-id="51181-113">If present, the package will be unpublished for all users on this computer.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="51181-114">/LOG</span><span class="sxs-lookup"><span data-stu-id="51181-114">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="51181-115">如果指定，输出将记录到指定的路径名称。</span><span class="sxs-lookup"><span data-stu-id="51181-115">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="51181-116">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="51181-116">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="51181-117">如果指定，将在活动控制台窗口中显示输出（默认）。</span><span class="sxs-lookup"><span data-stu-id="51181-117">If specified, output is presented in the active console window (default).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="51181-118">/GUI</span><span class="sxs-lookup"><span data-stu-id="51181-118">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="51181-119">如果指定，将在 Windows 对话框中显示输出。</span><span class="sxs-lookup"><span data-stu-id="51181-119">If specified, output is presented in a Windows dialog box.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="51181-120">对于版本4.6，已添加以下选项。</span><span class="sxs-lookup"><span data-stu-id="51181-120">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="51181-121">/LOGU</span><span class="sxs-lookup"><span data-stu-id="51181-121">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="51181-122">如果指定，将以 UNICODE 格式将输出记录到指定的路径名称。</span><span class="sxs-lookup"><span data-stu-id="51181-122">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="51181-123">**重要提示** 必须已将程序包添加到应用程序虚拟化客户端，然后才能运行 "**取消发布程序包**" 命令。</span><span class="sxs-lookup"><span data-stu-id="51181-123">**Important** Before you can run the **UNPUBLISH PACKAGE** command, the package must already have been added to the Application Virtualization Client.</span></span>

<span data-ttu-id="51181-124">若要使用**全局**，**取消发布程序包**必须以本地管理员身份运行;否则，仅需要**ClearApp**权限。</span><span class="sxs-lookup"><span data-stu-id="51181-124">To use **GLOBAL**, **UNPUBLISH PACKAGE** must be run as local Administrator; otherwise, only **ClearApp** permission is needed.</span></span>

<span data-ttu-id="51181-125">将**取消发布程序包**与**全局**结合使用将删除程序包的所有全局文件类型和快捷方式。</span><span class="sxs-lookup"><span data-stu-id="51181-125">Using **UNPUBLISH PACKAGE** with **GLOBAL** removes any global file types and shortcuts for the package.</span></span> <span data-ttu-id="51181-126">"**清除**" 不适用。</span><span class="sxs-lookup"><span data-stu-id="51181-126">**CLEAR** is not applicable.</span></span>

<span data-ttu-id="51181-127">使用**取消发布程序包**（不带**全局**）将删除程序包的用户快捷方式和文件类型，如果已设置 "**清除**"，则还会删除用户设置并停止用户上下文中的后台加载。</span><span class="sxs-lookup"><span data-stu-id="51181-127">Using **UNPUBLISH PACKAGE** without **GLOBAL** removes the user shortcuts and file types for the package and, if **CLEAR** is set, also removes user settings and stops background loads under the user’s context.</span></span>

<span data-ttu-id="51181-128">**取消发布程序包**适用于使用与**添加**、**编辑**和**发布程序包**的源 ID 相同的程序包名称或 GUID 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="51181-128">**UNPUBLISH PACKAGE** works on applications from the same package name or GUID that was used as the source ID for **ADD**, **EDIT**, and **PUBLISH PACKAGE**.</span></span>

<span data-ttu-id="51181-129">**取消发布程序包**始终清除所有用户设置、快捷方式和文件类型，而不管/CLEAR 开关的使用。</span><span class="sxs-lookup"><span data-stu-id="51181-129">**UNPUBLISH PACKAGE** always clears all the user settings, shortcuts, and file types regardless of the use of the /CLEAR switch.</span></span>

 

## <span data-ttu-id="51181-130">相关主题</span><span class="sxs-lookup"><span data-stu-id="51181-130">Related topics</span></span>


[<span data-ttu-id="51181-131">SFTMIME 命令引用</span><span class="sxs-lookup"><span data-stu-id="51181-131">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





