---
title: Application Virtualization Sequencer 的日志文件
description: Application Virtualization Sequencer 的日志文件
author: dansimp
ms.assetid: 1a296544-eab4-46f9-82ce-3136f8b578af
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d8cdf9dbc78ccdd03df5903ef4d42990099a2c53
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798927"
---
# <span data-ttu-id="6ff68-103">Application Virtualization Sequencer 的日志文件</span><span class="sxs-lookup"><span data-stu-id="6ff68-103">Log Files for the Application Virtualization Sequencer</span></span>


<span data-ttu-id="6ff68-104">应用程序虚拟化（app-v） Sequencer 的日志文件提供有关顺序应用程序的详细信息，当你验证功能或解决问题时，这些文件可能很有帮助。</span><span class="sxs-lookup"><span data-stu-id="6ff68-104">The log files for the Application Virtualization (App-V) Sequencer provide detailed information about sequencing applications, and they can be helpful when you are verifying functionality or when you are troubleshooting issues.</span></span>

<span data-ttu-id="6ff68-105">下表提供了有关日志文件及其默认位置的信息，这些信息在使用 Sequencer 时创建。</span><span class="sxs-lookup"><span data-stu-id="6ff68-105">The following table provides information about the log files and their default locations, which are created when using the Sequencer.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="6ff68-106">日志文件名</span><span class="sxs-lookup"><span data-stu-id="6ff68-106">Log File Name</span></span></th>
<th align="left"><span data-ttu-id="6ff68-107">描述</span><span class="sxs-lookup"><span data-stu-id="6ff68-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="6ff68-108">sft-seq-log.txt</span><span class="sxs-lookup"><span data-stu-id="6ff68-108">sft-seq-log.txt</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="6ff68-109">提供有关如何对应用程序进行序列化的常规信息。</span><span class="sxs-lookup"><span data-stu-id="6ff68-109">Provides general information about sequencing an application.</span></span> <span data-ttu-id="6ff68-110">将此日志用作对 Sequencer 错误进行故障排除的起始点。</span><span class="sxs-lookup"><span data-stu-id="6ff68-110">Use this log as a starting point for troubleshooting Sequencer errors.</span></span></p>
<p><span data-ttu-id="6ff68-111">日志文件位置： <em> %Windir%\Microsoft Application Virtualization Sequencer\Logs</span><span class="sxs-lookup"><span data-stu-id="6ff68-111">Log file location: <em>%windir%\Microsoft Application Virtualization Sequencer\Logs</span></span></em></p>
<p><span data-ttu-id="6ff68-112">[模板令牌值]App-v 4.6 日志文件位置： <em> %Windir%\Program Files\Microsoft Application Virtualization Sequencer\Logs </em> [Template Token Value]</span><span class="sxs-lookup"><span data-stu-id="6ff68-112">[Template Token Value] App-V4.6 log file location: <em>%windir%\Program Files\Microsoft Application Virtualization Sequencer\Logs</em>[Template Token Value]</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="6ff68-113">sftbt.txt</span><span class="sxs-lookup"><span data-stu-id="6ff68-113">sftbt.txt</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="6ff68-114">提供有关在 Sequencer 的模拟重启期间执行的计算机重启任务的信息。</span><span class="sxs-lookup"><span data-stu-id="6ff68-114">Provides information about computer restart tasks that occur during the Sequencer’s simulated restart.</span></span></p>
<p><span data-ttu-id="6ff68-115">日志文件位置： <em> %Windir%\Microsoft Application Virtualization Sequencer\Logs</span><span class="sxs-lookup"><span data-stu-id="6ff68-115">Log file location: <em>%windir%\Microsoft Application Virtualization Sequencer\Logs</span></span></em></p>
<p><span data-ttu-id="6ff68-116">[模板令牌值]App-v 4.6 日志文件位置： <em> %Windir%\Program Files\Microsoft Application Virtualization Sequencer\Logs </em> [Template Token Value]</span><span class="sxs-lookup"><span data-stu-id="6ff68-116">[Template Token Value] App-V4.6 log file location: <em>%windir%\Program Files\Microsoft Application Virtualization Sequencer\Logs</em>[Template Token Value]</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="6ff68-117">SftCallBack.txt</span><span class="sxs-lookup"><span data-stu-id="6ff68-117">SftCallBack.txt</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="6ff68-118">提供有关在排序期间使用的进程的一般信息。</span><span class="sxs-lookup"><span data-stu-id="6ff68-118">Provides general information about processes used during sequencing.</span></span></p>
<p><span data-ttu-id="6ff68-119">日志文件位置： <em> %Windir%\Microsoft Application Virtualization Sequencer\Logs</span><span class="sxs-lookup"><span data-stu-id="6ff68-119">Log file location: <em>%windir%\Microsoft Application Virtualization Sequencer\Logs</span></span></em></p>
<p><span data-ttu-id="6ff68-120">[模板令牌值]App-v 4.6 日志文件位置： <em> %Windir%\Program Files\Microsoft Application Virtualization Sequencer\Logs </em> [Template Token Value]</span><span class="sxs-lookup"><span data-stu-id="6ff68-120">[Template Token Value] App-V4.6 log file location: <em>%windir%\Program Files\Microsoft Application Virtualization Sequencer\Logs</em>[Template Token Value]</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="6ff68-121">相关主题</span><span class="sxs-lookup"><span data-stu-id="6ff68-121">Related topics</span></span>


[<span data-ttu-id="6ff68-122">Application Virtualization Sequencer 参考</span><span class="sxs-lookup"><span data-stu-id="6ff68-122">Application Virtualization Sequencer Reference</span></span>](application-virtualization-sequencer-reference.md)

 

 





