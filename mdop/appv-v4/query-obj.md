---
title: QUERY OBJ
description: QUERY OBJ
author: dansimp
ms.assetid: 55abf0d1-c779-4172-8357-552ab010933b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 328e9feb96c70080531cbbc666d8ff1b86045ba5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798831"
---
# <span data-ttu-id="648ef-103">QUERY OBJ</span><span class="sxs-lookup"><span data-stu-id="648ef-103">QUERY OBJ</span></span>


<span data-ttu-id="648ef-104">返回由 tab 分隔的当前应用程序、程序包、文件类型关联或发布服务器的列表。</span><span class="sxs-lookup"><span data-stu-id="648ef-104">Returns a tab-delimited list of current applications, packages, file type associations, or publishing servers.</span></span>

`SFTMIME QUERY OBJ:{APP|PACKAGE|TYPE|SERVER} [/SHORT] [/GLOBAL]                 [/LOG log-pathname | /CONSOLE ]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="648ef-105">参数</span><span class="sxs-lookup"><span data-stu-id="648ef-105">Parameter</span></span></th>
<th align="left"><span data-ttu-id="648ef-106">描述</span><span class="sxs-lookup"><span data-stu-id="648ef-106">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="648ef-107">应用</span><span class="sxs-lookup"><span data-stu-id="648ef-107">APP</span></span></p></td>
<td align="left"><p><span data-ttu-id="648ef-108">返回应用程序的列表。</span><span class="sxs-lookup"><span data-stu-id="648ef-108">Returns a list of applications.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="648ef-109">程序包</span><span class="sxs-lookup"><span data-stu-id="648ef-109">PACKAGE</span></span></p></td>
<td align="left"><p><span data-ttu-id="648ef-110">返回程序包列表。</span><span class="sxs-lookup"><span data-stu-id="648ef-110">Returns a list of packages.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="648ef-111">类型</span><span class="sxs-lookup"><span data-stu-id="648ef-111">TYPE</span></span></p></td>
<td align="left"><p><span data-ttu-id="648ef-112">返回文件类型关联的列表。</span><span class="sxs-lookup"><span data-stu-id="648ef-112">Returns a list of file type associations.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="648ef-113">服务</span><span class="sxs-lookup"><span data-stu-id="648ef-113">SERVER</span></span></p></td>
<td align="left"><p><span data-ttu-id="648ef-114">返回发布服务器的列表。</span><span class="sxs-lookup"><span data-stu-id="648ef-114">Returns a list of publishing servers.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="648ef-115">/SHORT</span><span class="sxs-lookup"><span data-stu-id="648ef-115">/SHORT</span></span></p></td>
<td align="left"><p><span data-ttu-id="648ef-116">如果不显示每个属性的完整属性，则返回应用程序名称、程序包、关联或服务器名称的列表。</span><span class="sxs-lookup"><span data-stu-id="648ef-116">Without displaying the full properties of each, returns a list of application names, packages, associations, or server names.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="648ef-117">/GLOBAL</span><span class="sxs-lookup"><span data-stu-id="648ef-117">/GLOBAL</span></span></p></td>
<td align="left"><p><span data-ttu-id="648ef-118">对于应用程序，返回所有已知的应用程序，而不是当前用户有权访问的应用程序。</span><span class="sxs-lookup"><span data-stu-id="648ef-118">For applications, returns all known applications instead of only the ones the current user has access to.</span></span> <span data-ttu-id="648ef-119">对于程序包，返回所有已知程序包，而不是当前用户有权访问的程序包。</span><span class="sxs-lookup"><span data-stu-id="648ef-119">For packages, returns all known packages instead of only the ones the current user has access to.</span></span> <span data-ttu-id="648ef-120">对于关联，仅返回适用于所有用户（而不是特定于用户的用户）的关联。</span><span class="sxs-lookup"><span data-stu-id="648ef-120">For associations, returns only associations that apply to all users, not user-specific ones.</span></span> <span data-ttu-id="648ef-121">对服务器无效。</span><span class="sxs-lookup"><span data-stu-id="648ef-121">Not valid for servers.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="648ef-122">/LOG</span><span class="sxs-lookup"><span data-stu-id="648ef-122">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="648ef-123">如果指定，输出将记录到指定的路径名称。</span><span class="sxs-lookup"><span data-stu-id="648ef-123">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="648ef-124">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="648ef-124">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="648ef-125">如果指定，将在活动控制台窗口中显示输出（默认）。</span><span class="sxs-lookup"><span data-stu-id="648ef-125">If specified, output is presented in the active console window (default).</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="648ef-126">对于版本4.6，已添加以下选项。</span><span class="sxs-lookup"><span data-stu-id="648ef-126">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="648ef-127">/LOGU</span><span class="sxs-lookup"><span data-stu-id="648ef-127">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="648ef-128">如果指定，将以 UNICODE 格式将输出记录到指定的路径名称。</span><span class="sxs-lookup"><span data-stu-id="648ef-128">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="648ef-129">**注意** 在版本4.6 中，已将新列添加到 SFTMIME 查询 OBJ： APP \ [/GLOBAL\] 的输出。</span><span class="sxs-lookup"><span data-stu-id="648ef-129">**Note** In version 4.6, a new column has been added to the output of SFTMIME QUERY OBJ:APP \[/GLOBAL\].</span></span> <span data-ttu-id="648ef-130">输出的最后一列是指示是否发布应用程序的数字值。</span><span class="sxs-lookup"><span data-stu-id="648ef-130">The last column of the output is a numeric value that indicates whether an application is published or not.</span></span>

<span data-ttu-id="648ef-131">已发布 = 1 表示应用程序由发布服务器刷新所发布，通过使用 Windows Installer 文件（）安装应用程序。MSI），或者通过运行 SFTMIME 添加程序包，使用程序包清单配置程序包或发布程序包命令。</span><span class="sxs-lookup"><span data-stu-id="648ef-131">PUBLISHED=1 means the application was published by a Publishing Server refresh, by installing the application by using a Windows Installer file (.MSI), or by running an SFTMIME ADD PACKAGE, CONFIGURE PACKAGE or PUBLISH PACKAGE command by using a package manifest.</span></span>

<span data-ttu-id="648ef-132">已发布 = 0 表示应用程序尚未发布，或者由于执行清除操作或运行 SFTMIME 取消发布命令而不再发布该应用程序。</span><span class="sxs-lookup"><span data-stu-id="648ef-132">PUBLISHED=0 means the application has not been published or it is no longer published as a result of performing a Clear operation or running an SFTMIME UNPUBLISH command.</span></span>

<span data-ttu-id="648ef-133">如果你使用/GLOBAL 参数，则发布状态将为1，适用于全局发布的应用程序，而对于在用户上下文中发布的应用程序，则为0。</span><span class="sxs-lookup"><span data-stu-id="648ef-133">If you use the /GLOBAL parameter, the PUBLISHED state will be 1 for applications that were published globally and 0 for those applications that were published under user contexts.</span></span> <span data-ttu-id="648ef-134">如果没有/GLOBAL 参数，将为运行该命令的用户上下文中发布的应用程序返回1的已发布状态，并为全局发布的应用程序返回0的状态。</span><span class="sxs-lookup"><span data-stu-id="648ef-134">Without the /GLOBAL parameter, a PUBLISHED state of 1 is returned for applications published in the context of the user running the command, and a state of 0 is returned for those applications that are published globally.</span></span>

 

<span data-ttu-id="648ef-135">SFTMIME 查询 OBJ 命令可用于查询上面显示的所有对象（应用程序、程序包、文件类型关联和服务器）的相关信息。</span><span class="sxs-lookup"><span data-stu-id="648ef-135">The SFTMIME QUERY OBJ command can be used to query for information on all of the objects shown above—applications, packages, file type associations, and servers.</span></span><span data-ttu-id="648ef-136">若要显示如何在正常操作任务中使用 SFTMIME 查询 OBJ 命令，下面的示例演示了要为特定程序包设置 OVERRIDEURL 参数值时应遵循的过程，以指定程序包内容的新路径。</span><span class="sxs-lookup"><span data-stu-id="648ef-136">To show how you might use the SFTMIME QUERY OBJ command in your normal operations tasks, the following example demonstrates the process you would follow if you wanted to set the OVERRIDEURL parameter value for a specific package to specify a new path to the package content.</span></span> 

1.  <span data-ttu-id="648ef-137">若要查找要配置的程序包，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="648ef-137">To find the package that you want to configure, run the following command:</span></span>

    `SFTMIME QUERY OBJ:PACKAGE`

    <span data-ttu-id="648ef-138">此命令将在输出的第一列中以 GUID 的形式返回每个发现的程序包名称，例如 {AF78ABE1-57D4-4297-89DE-C308684AEDD6}。</span><span class="sxs-lookup"><span data-stu-id="648ef-138">This command returns each discovered package name as a GUID in the first column of output—for example, {AF78ABE1-57D4-4297-89DE-C308684AEDD6}.</span></span>

2.  <span data-ttu-id="648ef-139">若要设置 OVERRIDEURL 参数值，请使用 "SFTMIME[配置包](configure-package.md)" 命令。</span><span class="sxs-lookup"><span data-stu-id="648ef-139">To set the OVERRIDEURL parameter value, you use the SFTMIME [CONFIGURE PACKAGE](configure-package.md) command.</span></span> <span data-ttu-id="648ef-140">例如，若要将此程序包的 OVERRIDEURL 值设置为*\\\\server\\share\\mypackage.sft*值，请使用 SFTMIME 的 "配置程序包" 命令，并从步骤1中 SFTMIME 查询 OBJ 命令的输出中为它提供所选的程序包 GUID，后跟 OVERRIDEURL 参数及其新值，如下所示：</span><span class="sxs-lookup"><span data-stu-id="648ef-140">For example, to set the OVERRIDEURL value for this package to a value of *\\\\server\\share\\mypackage.sft*, use the SFTMIME CONFIGURE PACKAGE command and give it the selected package GUID from the output of the SFTMIME QUERY OBJ command in step 1, followed by the OVERRIDEURL parameter and its new value, as follows:</span></span>

    `SFTMIME CONFIGURE PACKAGE:"{AF78ABE1-57D4-4297-89DE-C308684AEDD6}" /OVERRIDEURL "\\\\server\\share\\mypackage.sft "`

<span data-ttu-id="648ef-141">对于版本 4.6 SP2，已添加以下选项。</span><span class="sxs-lookup"><span data-stu-id="648ef-141">For version4.6 SP2, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="648ef-142">/NO-UPDATE-FTA-SHORTCUT</span><span class="sxs-lookup"><span data-stu-id="648ef-142">/NO-UPDATE-FTA-SHORTCUT</span></span></p></td>
<td align="left"><p><span data-ttu-id="648ef-143">指示/NO-UPDATE-FTA-SHORTCUT 标志的当前状态。</span><span class="sxs-lookup"><span data-stu-id="648ef-143">Indicates the current state of the /NO-UPDATE-FTA-SHORTCUT flag.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="648ef-144">相关主题</span><span class="sxs-lookup"><span data-stu-id="648ef-144">Related topics</span></span>


[<span data-ttu-id="648ef-145">SFTMIME 命令引用</span><span class="sxs-lookup"><span data-stu-id="648ef-145">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





