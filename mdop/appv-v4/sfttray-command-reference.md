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
# SFTTRAY 命令参考


Microsoft Application Virtualization （App-v）客户端任务栏应用程序 sfttray.exe 是用户在正常使用期间将与之交互的 App-v 客户端的主用户界面元素。 此程序控制所有虚拟应用程序的流处理和启动，并通过右键单击通知区域中显示的图标来显示客户端函数的菜单来访问。 该菜单使用户能够加载应用程序、启动发布刷新、取消请求或将客户端更改为脱机模式。 用户还可以通过单击 "**退出**" 关闭应用程序虚拟化客户端任务栏应用程序和所有活动的应用程序。

默认情况下，每当启动虚拟应用程序时，都会显示图标，尽管你可以使用 SFTTRAY 命令控制此行为。 应用程序虚拟化客户端任务栏应用程序还显示已启动的每个应用程序的进度条以及有关活动应用程序的状态消息。 单击进度栏将显示一条消息，允许您取消加载或启动应用程序。

## SFTTRAY 命令


通过从命令窗口运行以下命令，可以显示命令和命令行开关列表。

**注意**  
每个用户上下文只有一个应用程序虚拟化客户端托盘实例，因此，如果你启动新的 SFTTRAY 命令，该命令将传递到已在运行的程序。



`Sfttray.exe /?`

### 命令使用

`Sfttray.exe [/HIDE | /SHOW]`

`Sfttray.exe [/HIDE | /SHOW] [/QUIET] [/EXE alternate-exe] /LAUNCH app [args]`

`Sfttray.exe [/HIDE | /SHOW] [/QUIET] /LOAD app [/SFTFILE sft]`

`Sfttray.exe [/HIDE | /SHOW] [/QUIET] /LOADALL`

`Sfttray.exe [/HIDE | /SHOW] [/QUIET] /REFRESHALL`

`Sfttray.exe [/HIDE | /SHOW] [/QUIET] /LAUNCHRESULT <UNIQUE ID>  /LAUNCH app [args]`

`Sfttray.exe /EXIT`

### 命令行开关

下表介绍了 SFTTRAY 命令行开关。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">开关</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>/HIDE</p></td>
<td align="left"><p>隐藏 Windows 通知区域中的 SFTTRAY 图标。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/SHOW</p></td>
<td align="left"><p>显示 Windows 通知区域中的 "SFTTRAY" 图标。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/QUIET</p></td>
<td align="left"><p>通过防止错误显示需要用户确认的消息框来支持无人参与使用。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/EXE &lt; 备用 EXE&gt;</p></td>
<td align="left"><p>与/LAUNCH 一起使用，以指定在启动虚拟应用程序以替换 OSD 中指定的目标文件时，将在虚拟环境中启动一个可执行程序。</p>
<div class="alert">
<strong>注意</strong><br/><p>例如，使用 "SFTTRAY.EXE/EXE REGEDIT.EXE/LAUNCH &lt; app &gt; " 来使你能够检查运行应用程序的虚拟环境的注册表。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p>/LAUNCH &lt; 应用 &gt; [ &lt; args &gt; ]</p></td>
<td align="left"><p>启动虚拟应用程序。 指定应用程序的名称和版本或 OSD 文件的路径。 或者，可以将命令行参数传递到虚拟应用程序。</p>
<div class="alert">
<strong>注意</strong><br/><p>使用命令 "SFTMIME.EXE/QUERY OBJ： APP/SHORT" 获取可用虚拟应用程序的名称和版本的列表。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p>/LOAD</p></td>
<td align="left"><p>加载或导入虚拟应用程序。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/LOADALL</p></td>
<td align="left"><p>将所有应用程序加载到缓存中。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/REFRESHALL</p></td>
<td align="left"><p>为所有应用程序启动发布刷新。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/LAUNCHRESULT &lt; 唯一标识号&gt;</p></td>
<td align="left"><p>通过使用全局事件和基于唯一 ID 的指定根名称的内存映射文件，将启动结果代码返回到启动 sfttray.exe 的进程。¹</p></td>
</tr>
<tr class="even">
<td align="left"><p>/SFTFILE &lt; sft&gt;</p></td>
<td align="left"><p>与/LOAD 一起使用的可选开关，用于指定应用程序的 SFT 文件的路径。 如果指定，将导入应用程序，而不是加载应用程序。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/EXIT</p></td>
<td align="left"><p>关闭 SFTTRAY 程序和所有活动的虚拟应用程序，并从 Windows 通知区域中删除图标。</p></td>
</tr>
</tbody>
</table>



**注意**  
¹ */LAUNCHRESULT*命令行参数为启动 sfttray.exe 以指定全局事件的根名称和用于将启动结果代码返回到进程的内存映射文件提供了一种方法。 唯一标识符名称应以 "SFT-" 开头，以防止事件名称在虚拟环境中调用启动过程时获取虚拟化。 内存映射区域的大小为64位。

若要使用此参数，启动过程将创建一个名为 " &lt; UNIQUE id-result \ _event" 的事件，其中包含名称为 " &gt; &lt; unique id &gt; -result \ _value" 的内存映射文件，还可以选择使用名称 " &lt; 唯一 id &gt; -shutdown \ _event" 的事件，然后启动过程将启动 sfttray.exe 并等待事件发出信号。 事件 " &lt; 唯一 ID &gt; -result \ _event" 终止后，启动过程将从内存映射区域中检索64位返回代码。

如果 &lt; &gt; 当虚拟应用程序退出时，存在可选事件 "唯一 ID-shutdown \ _event"，则 sfttray.exe 打开并发出事件信号。 如果启动过程需要确定虚拟应用程序何时退出，则启动过程将等待此关闭事件。











