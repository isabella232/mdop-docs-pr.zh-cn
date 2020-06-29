---
title: SFTTRAY 命令参考
description: SFTTRAY 命令参考
author: dansimp
ms.assetid: 6fa3a939-b047-4d6c-bd1d-dfb93e065eb2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 45a664b91ff7edd5f8536f035417cc3b0f52d7ca
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798754"
---
# <span data-ttu-id="0f08c-103">SFTTRAY 命令参考</span><span class="sxs-lookup"><span data-stu-id="0f08c-103">SFTTRAY Command Reference</span></span>


<span data-ttu-id="0f08c-104">Microsoft Application Virtualization （App-v）客户端任务栏应用程序 sfttray.exe 是用户在正常使用期间将与之交互的 App-v 客户端的主用户界面元素。</span><span class="sxs-lookup"><span data-stu-id="0f08c-104">The Microsoft Application Virtualization (App-V) Client Tray application, sfttray.exe, is the main user interface element of the App-V Client that users will interact with during normal use.</span></span> <span data-ttu-id="0f08c-105">此程序控制所有虚拟应用程序的流处理和启动，并通过右键单击通知区域中显示的图标来显示客户端函数的菜单来访问。</span><span class="sxs-lookup"><span data-stu-id="0f08c-105">This program controls the streaming and starting of all virtual applications and is accessed by right-clicking the icon displayed in the notification area to display the menu of client functions.</span></span> <span data-ttu-id="0f08c-106">该菜单使用户能够加载应用程序、启动发布刷新、取消请求或将客户端更改为脱机模式。</span><span class="sxs-lookup"><span data-stu-id="0f08c-106">The menu enables the user to load applications, start a publishing refresh, cancel a request, or change the client to offline mode.</span></span> <span data-ttu-id="0f08c-107">用户还可以通过单击 "**退出**" 关闭应用程序虚拟化客户端任务栏应用程序和所有活动的应用程序。</span><span class="sxs-lookup"><span data-stu-id="0f08c-107">The user can also close the Application Virtualization Client Tray application and all active applications by clicking **Exit**.</span></span>

<span data-ttu-id="0f08c-108">默认情况下，每当启动虚拟应用程序时，都会显示图标，尽管你可以使用 SFTTRAY 命令控制此行为。</span><span class="sxs-lookup"><span data-stu-id="0f08c-108">By default, the icon is displayed whenever a virtual application is started, although you can control this behavior by using SFTTRAY commands.</span></span> <span data-ttu-id="0f08c-109">应用程序虚拟化客户端任务栏应用程序还显示已启动的每个应用程序的进度条以及有关活动应用程序的状态消息。</span><span class="sxs-lookup"><span data-stu-id="0f08c-109">The Application Virtualization Client Tray application also displays a progress bar for each application that is started, as well as status messages about active applications.</span></span> <span data-ttu-id="0f08c-110">单击进度栏将显示一条消息，允许您取消加载或启动应用程序。</span><span class="sxs-lookup"><span data-stu-id="0f08c-110">Clicking the progress bar displays a message that allows you to cancel the loading or starting of an application.</span></span>

## <span data-ttu-id="0f08c-111">SFTTRAY 命令</span><span class="sxs-lookup"><span data-stu-id="0f08c-111">SFTTRAY Commands</span></span>


<span data-ttu-id="0f08c-112">通过从命令窗口运行以下命令，可以显示命令和命令行开关列表。</span><span class="sxs-lookup"><span data-stu-id="0f08c-112">The list of commands and command-line switches can be displayed by running the following command from a command window.</span></span>

**<span data-ttu-id="0f08c-113">注意</span><span class="sxs-lookup"><span data-stu-id="0f08c-113">Note</span></span>**  
<span data-ttu-id="0f08c-114">每个用户上下文只有一个应用程序虚拟化客户端托盘实例，因此，如果你启动新的 SFTTRAY 命令，该命令将传递到已在运行的程序。</span><span class="sxs-lookup"><span data-stu-id="0f08c-114">There is only one Application Virtualization Client Tray instance for each user context, so if you start a new SFTTRAY command, it will be passed to the program that is already running.</span></span>



`Sfttray.exe /?`

### <span data-ttu-id="0f08c-115">命令使用</span><span class="sxs-lookup"><span data-stu-id="0f08c-115">Command Usage</span></span>

`Sfttray.exe [/HIDE | /SHOW]`

`Sfttray.exe [/HIDE | /SHOW] [/QUIET] [/EXE alternate-exe] /LAUNCH app [args]`

`Sfttray.exe [/HIDE | /SHOW] [/QUIET] /LOAD app [/SFTFILE sft]`

`Sfttray.exe [/HIDE | /SHOW] [/QUIET] /LOADALL`

`Sfttray.exe [/HIDE | /SHOW] [/QUIET] /REFRESHALL`

`Sfttray.exe [/HIDE | /SHOW] [/QUIET] /LAUNCHRESULT <UNIQUE ID>  /LAUNCH app [args]`

`Sfttray.exe /EXIT`

### <span data-ttu-id="0f08c-116">命令行开关</span><span class="sxs-lookup"><span data-stu-id="0f08c-116">Command-Line Switches</span></span>

<span data-ttu-id="0f08c-117">下表介绍了 SFTTRAY 命令行开关。</span><span class="sxs-lookup"><span data-stu-id="0f08c-117">The SFTTRAY command-line switches are described in the following table.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="0f08c-118">开关</span><span class="sxs-lookup"><span data-stu-id="0f08c-118">Switch</span></span></th>
<th align="left"><span data-ttu-id="0f08c-119">描述</span><span class="sxs-lookup"><span data-stu-id="0f08c-119">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0f08c-120">/HIDE</span><span class="sxs-lookup"><span data-stu-id="0f08c-120">/HIDE</span></span></p></td>
<td align="left"><p><span data-ttu-id="0f08c-121">隐藏 Windows 通知区域中的 SFTTRAY 图标。</span><span class="sxs-lookup"><span data-stu-id="0f08c-121">Hides the SFTTRAY icon in the Windows notification area.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0f08c-122">/SHOW</span><span class="sxs-lookup"><span data-stu-id="0f08c-122">/SHOW</span></span></p></td>
<td align="left"><p><span data-ttu-id="0f08c-123">显示 Windows 通知区域中的 "SFTTRAY" 图标。</span><span class="sxs-lookup"><span data-stu-id="0f08c-123">Displays the SFTTRAY icon in the Windows notification area.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0f08c-124">/QUIET</span><span class="sxs-lookup"><span data-stu-id="0f08c-124">/QUIET</span></span></p></td>
<td align="left"><p><span data-ttu-id="0f08c-125">通过防止错误显示需要用户确认的消息框来支持无人参与使用。</span><span class="sxs-lookup"><span data-stu-id="0f08c-125">Supports unattended usage by preventing errors from displaying message boxes that require user acknowledgement.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0f08c-126">/EXE &lt; 备用 EXE&gt;</span><span class="sxs-lookup"><span data-stu-id="0f08c-126">/EXE &lt;alternate-exe&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="0f08c-127">与/LAUNCH 一起使用，以指定在启动虚拟应用程序以替换 OSD 中指定的目标文件时，将在虚拟环境中启动一个可执行程序。</span><span class="sxs-lookup"><span data-stu-id="0f08c-127">Used with /LAUNCH to specify that an executable program is to be started in the virtual environment when a virtual application is started in place of the target file specified in the OSD.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="0f08c-128">注意</span><span class="sxs-lookup"><span data-stu-id="0f08c-128">Note</span></span></strong><br/><p><span data-ttu-id="0f08c-129">例如，使用 "SFTTRAY.EXE/EXE REGEDIT.EXE/LAUNCH &lt; app &gt; " 来使你能够检查运行应用程序的虚拟环境的注册表。</span><span class="sxs-lookup"><span data-stu-id="0f08c-129">For example, use “SFTTRAY.EXE /EXE REGEDIT.EXE /LAUNCH &lt;app&gt;” to enable you to examine the registry of the virtual environment in which the application is running.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0f08c-130">/LAUNCH &lt; 应用 &gt; [ &lt; args &gt; ]</span><span class="sxs-lookup"><span data-stu-id="0f08c-130">/LAUNCH &lt;app&gt; [&lt;args&gt;]</span></span></p></td>
<td align="left"><p><span data-ttu-id="0f08c-131">启动虚拟应用程序。</span><span class="sxs-lookup"><span data-stu-id="0f08c-131">Starts a virtual application.</span></span> <span data-ttu-id="0f08c-132">指定应用程序的名称和版本或 OSD 文件的路径。</span><span class="sxs-lookup"><span data-stu-id="0f08c-132">Specify the name and version of an application or the path to an OSD file.</span></span> <span data-ttu-id="0f08c-133">或者，可以将命令行参数传递到虚拟应用程序。</span><span class="sxs-lookup"><span data-stu-id="0f08c-133">Optionally, command-line arguments can be passed to the virtual application.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="0f08c-134">注意</span><span class="sxs-lookup"><span data-stu-id="0f08c-134">Note</span></span></strong><br/><p><span data-ttu-id="0f08c-135">使用命令 "SFTMIME.EXE/QUERY OBJ： APP/SHORT" 获取可用虚拟应用程序的名称和版本的列表。</span><span class="sxs-lookup"><span data-stu-id="0f08c-135">Use the command “SFTMIME.EXE /QUERY OBJ:APP /SHORT” to obtain a list of the names and versions of available virtual applications.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0f08c-136">/LOAD</span><span class="sxs-lookup"><span data-stu-id="0f08c-136">/LOAD</span></span></p></td>
<td align="left"><p><span data-ttu-id="0f08c-137">加载或导入虚拟应用程序。</span><span class="sxs-lookup"><span data-stu-id="0f08c-137">Loads or imports a virtual application.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0f08c-138">/LOADALL</span><span class="sxs-lookup"><span data-stu-id="0f08c-138">/LOADALL</span></span></p></td>
<td align="left"><p><span data-ttu-id="0f08c-139">将所有应用程序加载到缓存中。</span><span class="sxs-lookup"><span data-stu-id="0f08c-139">Loads all applications into cache.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0f08c-140">/REFRESHALL</span><span class="sxs-lookup"><span data-stu-id="0f08c-140">/REFRESHALL</span></span></p></td>
<td align="left"><p><span data-ttu-id="0f08c-141">为所有应用程序启动发布刷新。</span><span class="sxs-lookup"><span data-stu-id="0f08c-141">Starts a publishing refresh for all applications.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0f08c-142">/LAUNCHRESULT &lt; 唯一标识号&gt;</span><span class="sxs-lookup"><span data-stu-id="0f08c-142">/LAUNCHRESULT &lt;UNIQUE ID&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="0f08c-143">通过使用全局事件和基于唯一 ID 的指定根名称的内存映射文件，将启动结果代码返回到启动 sfttray.exe 的进程。¹</span><span class="sxs-lookup"><span data-stu-id="0f08c-143">Returns the launch result code to the process that launches sfttray.exe by using a global event and a memory mapped file that are based on the specified root name for the UNIQUE ID.¹</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0f08c-144">/SFTFILE &lt; sft&gt;</span><span class="sxs-lookup"><span data-stu-id="0f08c-144">/SFTFILE &lt;sft&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="0f08c-145">与/LOAD 一起使用的可选开关，用于指定应用程序的 SFT 文件的路径。</span><span class="sxs-lookup"><span data-stu-id="0f08c-145">Optional switch used with /LOAD to specify the path to the application’s SFT file.</span></span> <span data-ttu-id="0f08c-146">如果指定，将导入应用程序，而不是加载应用程序。</span><span class="sxs-lookup"><span data-stu-id="0f08c-146">If specified, the application is imported rather than loaded.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0f08c-147">/EXIT</span><span class="sxs-lookup"><span data-stu-id="0f08c-147">/EXIT</span></span></p></td>
<td align="left"><p><span data-ttu-id="0f08c-148">关闭 SFTTRAY 程序和所有活动的虚拟应用程序，并从 Windows 通知区域中删除图标。</span><span class="sxs-lookup"><span data-stu-id="0f08c-148">Closes the SFTTRAY program and all active virtual applications and removes the icon from the Windows notification area.</span></span></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="0f08c-149">注意</span><span class="sxs-lookup"><span data-stu-id="0f08c-149">Note</span></span>**  
<span data-ttu-id="0f08c-150">¹ */LAUNCHRESULT*命令行参数为启动 sfttray.exe 以指定全局事件的根名称和用于将启动结果代码返回到进程的内存映射文件提供了一种方法。</span><span class="sxs-lookup"><span data-stu-id="0f08c-150">¹ The */LAUNCHRESULT* command line parameter provides a means for the process that launches sfttray.exe to specify the root name for a global event and a memory mapped file that are used to return the launch result code to the process.</span></span> <span data-ttu-id="0f08c-151">唯一标识符名称应以 "SFT-" 开头，以防止事件名称在虚拟环境中调用启动过程时获取虚拟化。</span><span class="sxs-lookup"><span data-stu-id="0f08c-151">The unique identifier name should start with “SFT-” to prevent the event name from getting virtualized when the launching process is invoked within a virtual environment.</span></span> <span data-ttu-id="0f08c-152">内存映射区域的大小为64位。</span><span class="sxs-lookup"><span data-stu-id="0f08c-152">The memory mapped region will be 64 bits in size.</span></span>

<span data-ttu-id="0f08c-153">若要使用此参数，启动过程将创建一个名为 " &lt; UNIQUE id-result \ _event" 的事件，其中包含名称为 " &gt; &lt; unique id &gt; -result \ _value" 的内存映射文件，还可以选择使用名称 " &lt; 唯一 id &gt; -shutdown \ _event" 的事件，然后启动过程将启动 sfttray.exe 并等待事件发出信号。</span><span class="sxs-lookup"><span data-stu-id="0f08c-153">To use this parameter, the launching process creates an event with the name “&lt;UNIQUE ID&gt;-result\_event”, a memory mapped file with the name “&lt;UNIQUE ID&gt;-result\_value”, and optionally an event with the name “&lt;UNIQUE ID&gt;-shutdown\_event”, and then the launching process launches sfttray.exe and waits on the event to be signaled.</span></span> <span data-ttu-id="0f08c-154">事件 " &lt; 唯一 ID &gt; -result \ _event" 终止后，启动过程将从内存映射区域中检索64位返回代码。</span><span class="sxs-lookup"><span data-stu-id="0f08c-154">After the event “&lt;UNIQUE ID&gt;-result\_event” is signaled, the launching process retrieves the 64-bit return code from the memory mapped region.</span></span>

<span data-ttu-id="0f08c-155">如果 &lt; &gt; 当虚拟应用程序退出时，存在可选事件 "唯一 ID-shutdown \ _event"，则 sfttray.exe 打开并发出事件信号。</span><span class="sxs-lookup"><span data-stu-id="0f08c-155">If the optional event “&lt;UNIQUE ID&gt;-shutdown\_event” exists when the virtual application exits, sfttray.exe opens and signals the event.</span></span> <span data-ttu-id="0f08c-156">如果启动过程需要确定虚拟应用程序何时退出，则启动过程将等待此关闭事件。</span><span class="sxs-lookup"><span data-stu-id="0f08c-156">The launching process waits on this shutdown event if it needs to determine when the virtual application exits.</span></span>











