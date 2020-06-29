---
title: CONFIGURE PACKAGE
description: CONFIGURE PACKAGE
author: dansimp
ms.assetid: acc7eaa8-6ada-47b9-a655-2ca2537605b9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: dc8b315b68349cc9834316786b0bf15d4ac3c5cd
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802180"
---
# <span data-ttu-id="79372-103">CONFIGURE PACKAGE</span><span class="sxs-lookup"><span data-stu-id="79372-103">CONFIGURE PACKAGE</span></span>


<span data-ttu-id="79372-104">允许用户更改程序包的程序包清单文件、程序包源、加载触发器类型或加载目标。</span><span class="sxs-lookup"><span data-stu-id="79372-104">Enables the user to change a package manifest file, package source, load trigger types, or load target for a package.</span></span>

`SFTMIME CONFIGURE PACKAGE:package-name [/MANIFEST manifest-path]                 [/OVERRIDEURL url] [/AUTOLOADNEVER] [/AUTOLOADONREFRESH]                 [/AUTOLOADONLOGIN] [/AUTOLOADONLAUNCH]                 [/AUTOLOADTARGET {NONE|ALL|PREVUSED}]                 [/LOG log-pathname | /CONSOLE | /GUI]                 [/NO-UPDATE-FTA-SHORTCUT {TRUE|FALSE} {/GLOBAL}]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="79372-105">参数</span><span class="sxs-lookup"><span data-stu-id="79372-105">Parameter</span></span></th>
<th align="left"><span data-ttu-id="79372-106">描述</span><span class="sxs-lookup"><span data-stu-id="79372-106">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="79372-107">程序包： &lt; 软件包-name&gt;</span><span class="sxs-lookup"><span data-stu-id="79372-107">PACKAGE:&lt;package-name&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="79372-108">程序包的用户可见名称和用户友好名称。</span><span class="sxs-lookup"><span data-stu-id="79372-108">User-visible and user-friendly name for the package.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="79372-109">/MANIFEST &lt; 清单-path&gt;</span><span class="sxs-lookup"><span data-stu-id="79372-109">/MANIFEST &lt;manifest-path&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="79372-110">列出程序包中包含的应用程序及其所有发布信息的清单文件的路径或 URL。</span><span class="sxs-lookup"><span data-stu-id="79372-110">The path or URL of the manifest file that lists the applications included in the package and all of their publishing information.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="79372-111">/OVERRIDEURL &lt; URL&gt;</span><span class="sxs-lookup"><span data-stu-id="79372-111">/OVERRIDEURL &lt;URL&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="79372-112">程序包的 SFT 文件的位置。</span><span class="sxs-lookup"><span data-stu-id="79372-112">The location of the package's SFT file.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="79372-113">/AUTOLOADNEVER</span><span class="sxs-lookup"><span data-stu-id="79372-113">/AUTOLOADNEVER</span></span></p></td>
<td align="left"><p><span data-ttu-id="79372-114">程序包的后台加载已关闭。</span><span class="sxs-lookup"><span data-stu-id="79372-114">Background loading is turned off for the package.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="79372-115">/AUTOLOADONREFRESH</span><span class="sxs-lookup"><span data-stu-id="79372-115">/AUTOLOADONREFRESH</span></span></p></td>
<td align="left"><p><span data-ttu-id="79372-116">在发布刷新后执行后台加载。</span><span class="sxs-lookup"><span data-stu-id="79372-116">Background loading is performed after a publishing refresh.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="79372-117">/AUTOLOADONLOGIN</span><span class="sxs-lookup"><span data-stu-id="79372-117">/AUTOLOADONLOGIN</span></span></p></td>
<td align="left"><p><span data-ttu-id="79372-118">在用户登录时执行后台加载。</span><span class="sxs-lookup"><span data-stu-id="79372-118">Background loading is performed when a user logs in.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="79372-119">/AUTOLOADONLAUNCH</span><span class="sxs-lookup"><span data-stu-id="79372-119">/AUTOLOADONLAUNCH</span></span></p></td>
<td align="left"><p><span data-ttu-id="79372-120">在用户从程序包启动应用程序后执行后台加载。</span><span class="sxs-lookup"><span data-stu-id="79372-120">Background loading is performed after a user starts an application from the package.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="79372-121">/AUTOLOADTARGET &lt; 目标&gt;</span><span class="sxs-lookup"><span data-stu-id="79372-121">/AUTOLOADTARGET &lt;target&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="79372-122">指示程序包中将 autoloaded 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="79372-122">Indicates which applications from the package will be autoloaded.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="79372-123">尚</span><span class="sxs-lookup"><span data-stu-id="79372-123">NONE</span></span></p></td>
<td align="left"><p><span data-ttu-id="79372-124">尽管存在任何/AUTOLOADONxxx 标志，也不会执行任何 autoloading。</span><span class="sxs-lookup"><span data-stu-id="79372-124">No autoloading will be performed despite the presence of any /AUTOLOADONxxx flags.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="79372-125">所有</span><span class="sxs-lookup"><span data-stu-id="79372-125">ALL</span></span></p></td>
<td align="left"><p><span data-ttu-id="79372-126">如果启用了 autoload 触发器，则程序包中的所有应用程序都将加载到缓存中，无论它们是否曾被启动。</span><span class="sxs-lookup"><span data-stu-id="79372-126">If an autoload trigger is enabled, all applications in the package will be loaded into cache regardless of whether they have ever been launched.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="79372-127">PREVUSED</span><span class="sxs-lookup"><span data-stu-id="79372-127">PREVUSED</span></span></p></td>
<td align="left"><p><span data-ttu-id="79372-128">如果启用了 autoload 触发器，则在此程序包中的任何应用程序之前已由用户启动时，将加载该程序包。</span><span class="sxs-lookup"><span data-stu-id="79372-128">If an autoload trigger is enabled, the package will load if any applications in this package have previously been started by a user.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="79372-129">/LOG</span><span class="sxs-lookup"><span data-stu-id="79372-129">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="79372-130">如果指定，输出将记录到指定的路径名称。</span><span class="sxs-lookup"><span data-stu-id="79372-130">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="79372-131">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="79372-131">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="79372-132">如果指定，将在活动控制台窗口中显示输出（默认）。</span><span class="sxs-lookup"><span data-stu-id="79372-132">If specified, output is presented in the active console window (default).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="79372-133">/GUI</span><span class="sxs-lookup"><span data-stu-id="79372-133">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="79372-134">如果指定，将在 Windows 对话框中显示输出。</span><span class="sxs-lookup"><span data-stu-id="79372-134">If specified, output is presented in a Windows dialog box.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="79372-135">对于版本4.6，已添加以下选项。</span><span class="sxs-lookup"><span data-stu-id="79372-135">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="79372-136">/LOGU</span><span class="sxs-lookup"><span data-stu-id="79372-136">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="79372-137">如果指定，将以 UNICODE 格式将输出记录到指定的路径名称。</span><span class="sxs-lookup"><span data-stu-id="79372-137">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="79372-138">对于版本 4.6 SP2，已添加以下选项。</span><span class="sxs-lookup"><span data-stu-id="79372-138">For version4.6 SP2, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="79372-139">[/NO-UPDATE-FTA-SHORTCUT {TRUE |FALSE} {/GLOBAL}]</span><span class="sxs-lookup"><span data-stu-id="79372-139">[/NO-UPDATE-FTA-SHORTCUT {TRUE|FALSE} {/GLOBAL}]</span></span></p></td>
<td align="left"><p><span data-ttu-id="79372-140">如果设置为 TRUE，则为程序包（每用户）创建注册表值，如果指定了/GLOBAL 标志，则为全局。</span><span class="sxs-lookup"><span data-stu-id="79372-140">If set to TRUE, a registry value is created for the package, either per user, or globally if the /GLOBAL flag is specified.</span></span></p>
<p><span data-ttu-id="79372-141">如果设置为 FALSE，将删除注册表值并重新安装程序包的文件类型关联（FTA）。</span><span class="sxs-lookup"><span data-stu-id="79372-141">If set to FALSE, the registry value is removed and the file type associations (FTA) for the package are reinstalled.</span></span></p>
<p><span data-ttu-id="79372-142">如果未指定，则会发生正常的 FTA 和快捷方式发布行为。</span><span class="sxs-lookup"><span data-stu-id="79372-142">If not specified, normal FTA and shortcut publishing behavior occurs.</span></span> <span data-ttu-id="79372-143">如果在 App-V 4.6 SP2 客户端上执行任何后续的发布刷新操作，则不会更改具有此注册表值设置的程序包的快捷方式和 FTAs，并且不会在系统启动或用户登录时注册快捷方式和 FTAs，除非你重置该标记。</span><span class="sxs-lookup"><span data-stu-id="79372-143">If you perform any subsequent publishing refresh operations on the App-V 4.6 SP2 client, the shortcuts and FTAs for packages that have this registry value set will not be changed, and the shortcuts and FTAs will not be registered at system startup or user login unless you reset the flag.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="79372-144">/GLOBAL</span><span class="sxs-lookup"><span data-stu-id="79372-144">/GLOBAL</span></span></p></td>
<td align="left"><p><span data-ttu-id="79372-145">与/NO-UPDATE-FTA-SHORTCUT 标志配合使用。</span><span class="sxs-lookup"><span data-stu-id="79372-145">Works in conjunction with the /NO-UPDATE-FTA-SHORTCUT flag.</span></span> <span data-ttu-id="79372-146">如果/GLOBAL 标志存在，则表示将为所有用户创建该程序包的注册表值。</span><span class="sxs-lookup"><span data-stu-id="79372-146">If the /GLOBAL flag is present, it indicates that a registry value will be created for that package for all users.</span></span> <span data-ttu-id="79372-147">默认情况下，仅为此用户创建注册表值。</span><span class="sxs-lookup"><span data-stu-id="79372-147">By default, the registry value is created only for this user.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="79372-148">相关主题</span><span class="sxs-lookup"><span data-stu-id="79372-148">Related topics</span></span>


[<span data-ttu-id="79372-149">SFTMIME 命令引用</span><span class="sxs-lookup"><span data-stu-id="79372-149">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





