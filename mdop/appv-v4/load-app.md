---
title: LOAD APP
description: LOAD APP
author: dansimp
ms.assetid: 7b727d0c-5423-419d-92ef-7ebbc6343e79
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 02bd6e35da898f5b34f7efc21cbc01a72d555b8d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798933"
---
# <span data-ttu-id="f1f3a-103">LOAD APP</span><span class="sxs-lookup"><span data-stu-id="f1f3a-103">LOAD APP</span></span>


<span data-ttu-id="f1f3a-104">将程序包中的指定应用程序和所有其他应用程序加载到文件系统缓存中。</span><span class="sxs-lookup"><span data-stu-id="f1f3a-104">Loads the specified application and all other applications in the package into the file system cache.</span></span>

<span data-ttu-id="f1f3a-105">**注意** "**加载应用**" 命令将启动加载过程，并且进度栏将显示在桌面通知区域中。</span><span class="sxs-lookup"><span data-stu-id="f1f3a-105">**Note** The **LOAD APP** command starts the load process and a progress bar is displayed in the Desktop Notification Area.</span></span> <span data-ttu-id="f1f3a-106">此命令将在开始此过程后立即退出，因此任何加载错误都将显示在同一位置。</span><span class="sxs-lookup"><span data-stu-id="f1f3a-106">The command exits immediately after starting this process, so any load errors are displayed in the same location.</span></span> <span data-ttu-id="f1f3a-107">如果要从命令行开始加载过程而不使用桌面通知区域，请使用**加载包**命令。</span><span class="sxs-lookup"><span data-stu-id="f1f3a-107">Use the **LOAD PACKAGE** command if you want to start the load process from the command line without using the Desktop Notification Area.</span></span>

 

`SFTMIME LOAD APP:application [/LOG log-pathname | /GUI]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="f1f3a-108">参数</span><span class="sxs-lookup"><span data-stu-id="f1f3a-108">Parameter</span></span></th>
<th align="left"><span data-ttu-id="f1f3a-109">描述</span><span class="sxs-lookup"><span data-stu-id="f1f3a-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f1f3a-110">应用： &lt; 应用程序&gt;</span><span class="sxs-lookup"><span data-stu-id="f1f3a-110">APP:&lt;application&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="f1f3a-111">要加载的应用程序的名称和版本（可选）。</span><span class="sxs-lookup"><span data-stu-id="f1f3a-111">The name and version (optional) of the application to load.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f1f3a-112">/LOG</span><span class="sxs-lookup"><span data-stu-id="f1f3a-112">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="f1f3a-113">如果指定，输出将记录到指定的路径名称。</span><span class="sxs-lookup"><span data-stu-id="f1f3a-113">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f1f3a-114">/GUI</span><span class="sxs-lookup"><span data-stu-id="f1f3a-114">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="f1f3a-115">如果指定，将在 Windows 对话框中显示输出。</span><span class="sxs-lookup"><span data-stu-id="f1f3a-115">If specified, output is presented in a Windows dialog box.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="f1f3a-116">对于版本4.6，已添加以下选项。</span><span class="sxs-lookup"><span data-stu-id="f1f3a-116">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f1f3a-117">/LOGU</span><span class="sxs-lookup"><span data-stu-id="f1f3a-117">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="f1f3a-118">如果指定，将以 UNICODE 格式将输出记录到指定的路径名称。</span><span class="sxs-lookup"><span data-stu-id="f1f3a-118">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="f1f3a-119">相关主题</span><span class="sxs-lookup"><span data-stu-id="f1f3a-119">Related topics</span></span>


[<span data-ttu-id="f1f3a-120">SFTMIME 命令引用</span><span class="sxs-lookup"><span data-stu-id="f1f3a-120">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





