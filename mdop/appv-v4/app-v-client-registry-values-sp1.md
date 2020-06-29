---
title: App-V Client 注册表值
description: App-V Client 注册表值
author: dansimp
ms.assetid: 46af5209-9762-47b9-afdb-9a2947e013f7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 05cd807ff9882bc478aca07abc4a28cdea83086a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802364"
---
# <span data-ttu-id="e31af-103">App-V Client 注册表值</span><span class="sxs-lookup"><span data-stu-id="e31af-103">App-V Client Registry Values</span></span>


<span data-ttu-id="e31af-104">Microsoft Application Virtualization （App-v）客户端将其配置存储在注册表中。</span><span class="sxs-lookup"><span data-stu-id="e31af-104">The Microsoft Application Virtualization (App-V) client stores its configuration in the registry.</span></span> <span data-ttu-id="e31af-105">如果你了解注册表中的数据的格式，则可以收集有关客户端的一些有用信息。</span><span class="sxs-lookup"><span data-stu-id="e31af-105">You can gather some useful information about the client if you understand the format of data in the registry.</span></span> <span data-ttu-id="e31af-106">您也可以通过更改注册表项来配置多个客户端操作。</span><span class="sxs-lookup"><span data-stu-id="e31af-106">You can also configure many client actions by changing registry entries.</span></span> <span data-ttu-id="e31af-107">本主题列出了所有应用程序虚拟化（app-v）客户端注册表项并解释其用法。</span><span class="sxs-lookup"><span data-stu-id="e31af-107">This topic lists all the Application Virtualization (App-V) client registry keys and explains their uses.</span></span>

**<span data-ttu-id="e31af-108">重要提示</span><span class="sxs-lookup"><span data-stu-id="e31af-108">Important</span></span>**  
<span data-ttu-id="e31af-109">在运行64位操作系统的计算机上，以下部分中所述的键和值将在 HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid\\4.5\\Client. 下。</span><span class="sxs-lookup"><span data-stu-id="e31af-109">On a computer running a 64-bit operating system, the keys and values described in the following sections will be under HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid\\4.5\\Client.</span></span>



## <span data-ttu-id="e31af-110">配置键</span><span class="sxs-lookup"><span data-stu-id="e31af-110">Configuration Key</span></span>


<span data-ttu-id="e31af-111">下表提供了与 HKEY _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration 键相关联的注册表值的相关信息。</span><span class="sxs-lookup"><span data-stu-id="e31af-111">The following table provides information about the registry values associated with the HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration key.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e31af-112">名称</span><span class="sxs-lookup"><span data-stu-id="e31af-112">Name</span></span></th>
<th align="left"><span data-ttu-id="e31af-113">类型</span><span class="sxs-lookup"><span data-stu-id="e31af-113">Type</span></span></th>
<th align="left"><span data-ttu-id="e31af-114">数据（示例）</span><span class="sxs-lookup"><span data-stu-id="e31af-114">Data (Examples)</span></span></th>
<th align="left"><span data-ttu-id="e31af-115">描述</span><span class="sxs-lookup"><span data-stu-id="e31af-115">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e31af-116">ProductName</span><span class="sxs-lookup"><span data-stu-id="e31af-116">ProductName</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-117">字符串</span><span class="sxs-lookup"><span data-stu-id="e31af-117">String</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-118">Microsoft Application Virtualization 桌面客户端</span><span class="sxs-lookup"><span data-stu-id="e31af-118">Microsoft Application Virtualization Desktop Client</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-119">请勿修改。</span><span class="sxs-lookup"><span data-stu-id="e31af-119">Do not modify.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e31af-120">版本</span><span class="sxs-lookup"><span data-stu-id="e31af-120">Version</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-121">字符串</span><span class="sxs-lookup"><span data-stu-id="e31af-121">String</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-122">4.5.0.xxx</span><span class="sxs-lookup"><span data-stu-id="e31af-122">4.5.0.xxx</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-123">请勿修改。</span><span class="sxs-lookup"><span data-stu-id="e31af-123">Do not modify.</span></span> </p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e31af-124">驱动程序</span><span class="sxs-lookup"><span data-stu-id="e31af-124">Drivers</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-125">字符串</span><span class="sxs-lookup"><span data-stu-id="e31af-125">String</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-126">Sftfs.sys</span><span class="sxs-lookup"><span data-stu-id="e31af-126">Sftfs.sys</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-127">如果此项值存在，则它包含上次启动内核时导致停止错误的驱动程序的名称。</span><span class="sxs-lookup"><span data-stu-id="e31af-127">If this key value is present, it contains the name of the driver that caused a stop error the last time the core was starting.</span></span> <span data-ttu-id="e31af-128">修复错误修复后，必须删除此项值，以便 sftlist 可以启动。</span><span class="sxs-lookup"><span data-stu-id="e31af-128">After you have fixed the stop error, you must delete this key value so that sftlist can start.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e31af-129">InstallPath</span><span class="sxs-lookup"><span data-stu-id="e31af-129">InstallPath</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-130">字符串</span><span class="sxs-lookup"><span data-stu-id="e31af-130">String</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-131">Default = C:\Program Files\Microsoft Application Virtualization 客户端</span><span class="sxs-lookup"><span data-stu-id="e31af-131">Default=C:\Program Files\Microsoft Application Virtualization Client</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-132">客户端的安装位置。</span><span class="sxs-lookup"><span data-stu-id="e31af-132">The location where the client is installed.</span></span> <span data-ttu-id="e31af-133">请勿修改。</span><span class="sxs-lookup"><span data-stu-id="e31af-133">Do not modify.</span></span> </p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e31af-134">LogFileName</span><span class="sxs-lookup"><span data-stu-id="e31af-134">LogFileName</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-135">字符串</span><span class="sxs-lookup"><span data-stu-id="e31af-135">String</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-136">默认值 = CSIDL_COMMON_APPDATA \Microsoft\Application 虚拟化 Client\sftlog.txt</span><span class="sxs-lookup"><span data-stu-id="e31af-136">Default=CSIDL_COMMON_APPDATA\Microsoft\Application Virtualization Client\sftlog.txt</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-137">客户端日志文件的路径和名称。</span><span class="sxs-lookup"><span data-stu-id="e31af-137">The path and name for the client log file.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="e31af-138">注意</span><span class="sxs-lookup"><span data-stu-id="e31af-138">Note</span></span></strong><br/><p><span data-ttu-id="e31af-139">如果你运行的版本比 App-v 4.6、SP1 更早，而你修改了日志文件的名称或位置，则必须重新启动 sftlist 服务才能使更改生效。</span><span class="sxs-lookup"><span data-stu-id="e31af-139">If you are running an earlier version than App-V 4.6, SP1 and you modify the log file name or location, you must restart the sftlist service for the change to take effect.</span></span></p>
</div>
<div>

</div>
<p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e31af-140">LogMinSeverity</span><span class="sxs-lookup"><span data-stu-id="e31af-140">LogMinSeverity</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-141">DWORD</span><span class="sxs-lookup"><span data-stu-id="e31af-141">DWORD</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-142">默认值 = 4，信息</span><span class="sxs-lookup"><span data-stu-id="e31af-142">Default=4, Informational</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-143">控制将哪些消息写入日志。</span><span class="sxs-lookup"><span data-stu-id="e31af-143">Controls which messages are written to the log.</span></span> <span data-ttu-id="e31af-144">该值指示所记录内容的阈值，即记录小于或等于该值的所有内容。</span><span class="sxs-lookup"><span data-stu-id="e31af-144">The value indicates a threshold of what is logged—everything less than or equal to that value is logged.</span></span> <span data-ttu-id="e31af-145">例如，值0x3 （警告）表示记录警告（0x3）、错误（0x2）和严重错误（0x1）。</span><span class="sxs-lookup"><span data-stu-id="e31af-145">For example, a value of 0x3 (Warning) indicates that Warnings (0x3), Errors (0x2), and Critical Errors (0x1) are logged.</span></span></p>
<p><span data-ttu-id="e31af-146">值范围： 0x0 = None，0x1 = 严重，0x2 = 错误，0x3 = Warning，0x4 = 信息（默认值），0x5 = Verbose。</span><span class="sxs-lookup"><span data-stu-id="e31af-146">Value Range: 0x0 = None, 0x1 = Critical, 0x2 = Error, 0x3 = Warning, 0x4 = Information (Default), 0x5 = Verbose.</span></span></p>
<p><span data-ttu-id="e31af-147">日志级别可通过应用程序虚拟化（app-v）客户端控制台和命令提示符进行配置。</span><span class="sxs-lookup"><span data-stu-id="e31af-147">The log level is configurable from the Application Virtualization (App-V) client console and from the command prompt.</span></span> <span data-ttu-id="e31af-148">在命令提示符处，命令 sftlist.exe/verboselog 会将日志级别增加到详细。</span><span class="sxs-lookup"><span data-stu-id="e31af-148">At a command prompt, the command sftlist.exe /verboselog will increase the log level to verbose.</span></span> <span data-ttu-id="e31af-149">有关命令行详细信息的详细信息，请参阅</span><span class="sxs-lookup"><span data-stu-id="e31af-149">For more information on command-line details see</span></span></p>
<p><a href="https://go.microsoft.com/fwlink/?LinkId=141467https://go.microsoft.com/fwlink/?LinkId=141467" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=141467https://go.microsoft.com/fwlink/?LinkId=141467">https://go.microsoft.com/fwlink/?LinkId=141467https://go.microsoft.com/fwlink/?LinkId=141467</a></p>
<p><span data-ttu-id="e31af-150">.</span><span class="sxs-lookup"><span data-stu-id="e31af-150">.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e31af-151">LogRolloverCount</span><span class="sxs-lookup"><span data-stu-id="e31af-151">LogRolloverCount</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-152">DWORD</span><span class="sxs-lookup"><span data-stu-id="e31af-152">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-153">默认值 = 4</span><span class="sxs-lookup"><span data-stu-id="e31af-153">Default=4</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-154">定义在重置时保留的日志文件的备份副本数。</span><span class="sxs-lookup"><span data-stu-id="e31af-154">Defines the number of backup copies of the log file that are kept when it is reset.</span></span> <span data-ttu-id="e31af-155">有效范围为0到9999。</span><span class="sxs-lookup"><span data-stu-id="e31af-155">The valid range is 0–9999.</span></span> <span data-ttu-id="e31af-156">默认值为4。</span><span class="sxs-lookup"><span data-stu-id="e31af-156">The default is 4.</span></span> <span data-ttu-id="e31af-157">值0表示将不保留任何副本。</span><span class="sxs-lookup"><span data-stu-id="e31af-157">A value of 0 means no copies will be kept.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e31af-158">LogMaxSize</span><span class="sxs-lookup"><span data-stu-id="e31af-158">LogMaxSize</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-159">DWORD</span><span class="sxs-lookup"><span data-stu-id="e31af-159">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-160">默认值 = 256</span><span class="sxs-lookup"><span data-stu-id="e31af-160">Default=256</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-161">定义在重置之前日志文件可以增长的最大大小（以兆字节（MB）为单位）。</span><span class="sxs-lookup"><span data-stu-id="e31af-161">Defines the maximum size in megabytes (MB) that the log file can grow before being reset.</span></span> <span data-ttu-id="e31af-162">默认大小为 256 MB。</span><span class="sxs-lookup"><span data-stu-id="e31af-162">The default size is 256 MB.</span></span> <span data-ttu-id="e31af-163">达到此大小时，将在下次写入尝试时强制重置日志。</span><span class="sxs-lookup"><span data-stu-id="e31af-163">When this size is reached, a log reset will be forced on the next write attempt.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e31af-164">SystemEventLogLevel</span><span class="sxs-lookup"><span data-stu-id="e31af-164">SystemEventLogLevel</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-165">DWORD</span><span class="sxs-lookup"><span data-stu-id="e31af-165">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-166">默认值 = 0x4 （App-v 4.5）</span><span class="sxs-lookup"><span data-stu-id="e31af-166">Default=0x4 (App-V 4.5)</span></span></p>
<p><span data-ttu-id="e31af-167">默认值 = 0x3 （App-v 4.6）</span><span class="sxs-lookup"><span data-stu-id="e31af-167">Default=0x3 (App-V 4.6)</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-168">指示日志消息写入 NT 事件日志的日志记录级别。</span><span class="sxs-lookup"><span data-stu-id="e31af-168">Indicates the logging level at which log messages are written to the NT event log.</span></span> <span data-ttu-id="e31af-169">该值指示所记录内容的阈值，即记录的所有内容都等于或小于该值。</span><span class="sxs-lookup"><span data-stu-id="e31af-169">The value indicates a threshold of what is logged—that is, everything equal to or less than that value is logged.</span></span> <span data-ttu-id="e31af-170">例如，值0x3 （警告）表示记录警告（0x3）、错误（0x2）和严重错误（0x1）。</span><span class="sxs-lookup"><span data-stu-id="e31af-170">For example, a value of 0x3 (Warning) indicates that Warnings (0x3), Errors (0x2), and Critical Errors (0x1) are logged.</span></span></p>
<p><span data-ttu-id="e31af-171">值范围</span><span class="sxs-lookup"><span data-stu-id="e31af-171">Value Range</span></span></p>
<p><span data-ttu-id="e31af-172">0x0 = None</span><span class="sxs-lookup"><span data-stu-id="e31af-172">0x0 = None</span></span></p>
<p><span data-ttu-id="e31af-173">0x1 = 严重</span><span class="sxs-lookup"><span data-stu-id="e31af-173">0x1 = Critical</span></span></p>
<p><span data-ttu-id="e31af-174">0x2 = 错误</span><span class="sxs-lookup"><span data-stu-id="e31af-174">0x2 = Error</span></span></p>
<p><span data-ttu-id="e31af-175">0x3 = 警告</span><span class="sxs-lookup"><span data-stu-id="e31af-175">0x3 = Warning</span></span></p>
<p><span data-ttu-id="e31af-176">0x4 = 信息（默认值）</span><span class="sxs-lookup"><span data-stu-id="e31af-176">0x4 = Information (Default)</span></span></p>
<p><span data-ttu-id="e31af-177">0x5 = 详细</span><span class="sxs-lookup"><span data-stu-id="e31af-177">0x5 = Verbose</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e31af-178">AllowIndependentFileStreaming</span><span class="sxs-lookup"><span data-stu-id="e31af-178">AllowIndependentFileStreaming</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-179">DWORD</span><span class="sxs-lookup"><span data-stu-id="e31af-179">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-180">默认值 = 0</span><span class="sxs-lookup"><span data-stu-id="e31af-180">Default=0</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-181">指示是否将启用来自文件的流，无论客户端是否已配置了 APPLICATIONSOURCEROOT 参数。</span><span class="sxs-lookup"><span data-stu-id="e31af-181">Indicates whether streaming from file will be enabled regardless of how the client has been configured with the APPLICATIONSOURCEROOT parameter.</span></span> <span data-ttu-id="e31af-182">如果设置为 FALSE，则传输将不会启用来自文件的流处理，即使 OSD HREF 或 APPLICATIONSOURCEROOT 参数包含文件路径也是如此。</span><span class="sxs-lookup"><span data-stu-id="e31af-182">If set to FALSE, the transport will not enable streaming from files even if the OSD HREF or the APPLICATIONSOURCEROOT parameter contains a file path.</span></span></p>
<p><span data-ttu-id="e31af-183">0x0 = False （默认值）</span><span class="sxs-lookup"><span data-stu-id="e31af-183">0x0=False (default)</span></span></p>
<p><span data-ttu-id="e31af-184">0x1 = True</span><span class="sxs-lookup"><span data-stu-id="e31af-184">0x1=True</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e31af-185">ApplicationSourceRoot</span><span class="sxs-lookup"><span data-stu-id="e31af-185">ApplicationSourceRoot</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-186">字符串</span><span class="sxs-lookup"><span data-stu-id="e31af-186">String</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-187">rtsps://mainserver:322/prodapps</span><span class="sxs-lookup"><span data-stu-id="e31af-187">rtsps://mainserver:322/prodapps</span></span></p>
<p><a href="https://mainserver:443/prodapps" data-raw-source="https://mainserver:443/prodapps">https://mainserver:443/prodapps</a></p>
<p><span data-ttu-id="e31af-188">文件：//\uncserver\share\prodapps</span><span class="sxs-lookup"><span data-stu-id="e31af-188">file://\uncserver\share\prodapps</span></span></p>
<p><span data-ttu-id="e31af-189">文件：//\uncserver\share</span><span class="sxs-lookup"><span data-stu-id="e31af-189">file://\uncserver\share</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-190">支持管理员或电子软件分发（ESD）系统，确保根据拓扑管理方案执行应用程序加载。</span><span class="sxs-lookup"><span data-stu-id="e31af-190">Enables an administrator or electronic software distribution (ESD) system to ensure application loading is performed according to the topology management scheme.</span></span> <span data-ttu-id="e31af-191">使用此关键字值替代应用程序的 HREF 元素（例如，源位置）的 OSD 基本代码。</span><span class="sxs-lookup"><span data-stu-id="e31af-191">Use this key value to override the OSD CODEBASE for the HREF element (for example, the source location) for an application.</span></span> <span data-ttu-id="e31af-192">应用程序源根目录支持 Url 和通用命名约定（UNC）路径格式。</span><span class="sxs-lookup"><span data-stu-id="e31af-192">Application Source Root supports URLs and Universal Naming Convention (UNC) path formats.</span></span></p>
<p><span data-ttu-id="e31af-193">URL 路径的正确格式为 protocol：/id： [port] [/path] [/]，其中 port 和 path 是可选的。</span><span class="sxs-lookup"><span data-stu-id="e31af-193">The correct format for the URL path is protocol://servername:[port][/path][/], where port and path are optional.</span></span> <span data-ttu-id="e31af-194">如果未指定端口，则使用协议的默认端口。</span><span class="sxs-lookup"><span data-stu-id="e31af-194">If a port is not specified, the default port for the protocol is used.</span></span> <span data-ttu-id="e31af-195">仅替换了 OSD URL 的协议：//server：端口部分。</span><span class="sxs-lookup"><span data-stu-id="e31af-195">Only the protocol://server:port portion of the OSD URL is replaced.</span></span> </p>
<p><span data-ttu-id="e31af-196">UNC 路径的正确格式为 \computername\sharefolder [folder] []，其中文件夹是可选的。</span><span class="sxs-lookup"><span data-stu-id="e31af-196">The correct format for the UNC path is \computername\sharefolder[folder][], where folder is optional.</span></span> <span data-ttu-id="e31af-197">计算机名可以是完全限定的域名（FQDN）或 IP 地址，sharefolder 可以是驱动器号。</span><span class="sxs-lookup"><span data-stu-id="e31af-197">The computer name can be a fully qualified domain name (FQDN) or an IP address, and sharefolder can be a drive letter.</span></span> <span data-ttu-id="e31af-198">仅替换 OSD 路径的 \computername\sharefolder 或驱动器号部分。</span><span class="sxs-lookup"><span data-stu-id="e31af-198">Only the \computername\sharefolder or drive letter portion of the OSD path is replaced.</span></span> </p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e31af-199">OSDSourceRoot</span><span class="sxs-lookup"><span data-stu-id="e31af-199">OSDSourceRoot</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-200">字符串</span><span class="sxs-lookup"><span data-stu-id="e31af-200">String</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-201">\computername\sharefolder\resource</span><span class="sxs-lookup"><span data-stu-id="e31af-201">\computername\sharefolder\resource</span></span></p>
<p><span data-ttu-id="e31af-202">\computername\content</span><span class="sxs-lookup"><span data-stu-id="e31af-202">\computername\content</span></span></p>
<p><span data-ttu-id="e31af-203">C:\foldername</span><span class="sxs-lookup"><span data-stu-id="e31af-203">C:\foldername</span></span></p>
<p><a href="http://computername/productivity/" data-raw-source="http://computername/productivity/">http://computername/productivity/</a></p>
<p><a href="https://computername/productivity/" data-raw-source="https://computername/productivity/">https://computername/productivity/</a></p></td>
<td align="left"><p><span data-ttu-id="e31af-204">允许管理员为发布期间的序列化应用程序包指定 OSD 文件检索的源位置。</span><span class="sxs-lookup"><span data-stu-id="e31af-204">Enables an administrator to specify a source location for OSD file retrieval for a sequenced application package during publication.</span></span> <span data-ttu-id="e31af-205">OSDSourceRoot 的可接受格式包括 UNC 路径和 Url （http 或 https）。</span><span class="sxs-lookup"><span data-stu-id="e31af-205">Acceptable formats for the OSDSourceRoot include UNC paths and URLs (http or https).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e31af-206">IconSourceRoot</span><span class="sxs-lookup"><span data-stu-id="e31af-206">IconSourceRoot</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-207">字符串</span><span class="sxs-lookup"><span data-stu-id="e31af-207">String</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-208">\computername\sharefolder\resource</span><span class="sxs-lookup"><span data-stu-id="e31af-208">\computername\sharefolder\resource</span></span></p>
<p><span data-ttu-id="e31af-209">\computername\content</span><span class="sxs-lookup"><span data-stu-id="e31af-209">\computername\content</span></span></p>
<p><span data-ttu-id="e31af-210">C:\foldername</span><span class="sxs-lookup"><span data-stu-id="e31af-210">C:\foldername</span></span></p>
<p><a href="http://computername/productivity/" data-raw-source="http://computername/productivity/">http://computername/productivity/</a></p>
<p><a href="https://computername/productivity/" data-raw-source="https://computername/productivity/">https://computername/productivity/</a></p></td>
<td align="left"><p><span data-ttu-id="e31af-211">允许管理员为发布期间的序列化应用程序包指定图标文件检索的源位置。</span><span class="sxs-lookup"><span data-stu-id="e31af-211">Enables an administrator to specify a source location for icon file retrieval for a sequenced application package during publication.</span></span> <span data-ttu-id="e31af-212">IconSourceRoot 的可接受格式包括 UNC 路径和 Url （http 或 https）。</span><span class="sxs-lookup"><span data-stu-id="e31af-212">Acceptable formats for the IconSourceRoot include UNC paths and URLs (http or https).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e31af-213">AutoLoadTriggers</span><span class="sxs-lookup"><span data-stu-id="e31af-213">AutoLoadTriggers</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-214">DWORD</span><span class="sxs-lookup"><span data-stu-id="e31af-214">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-215">默认值 = 5</span><span class="sxs-lookup"><span data-stu-id="e31af-215">Default=5</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-216">AutoLoad 是一种客户端运行时策略配置参数，可使虚拟化应用程序的辅助功能块在后台自动流式传输到客户端。</span><span class="sxs-lookup"><span data-stu-id="e31af-216">AutoLoad is a client runtime policy configuration parameter that enables the secondary feature block of a virtualized application to be streamed to the client automatically in the background.</span></span> <span data-ttu-id="e31af-217">AutoLoad 触发器是标志，用于指示启动应用程序自动加载的事件。</span><span class="sxs-lookup"><span data-stu-id="e31af-217">The AutoLoad triggers are flags to indicate events that initiate auto-loading of applications.</span></span> <span data-ttu-id="e31af-218">AutoLoad 隐式使用后台流，使应用程序能够完全加载到缓存中。</span><span class="sxs-lookup"><span data-stu-id="e31af-218">AutoLoad implicitly uses background streaming to enable the application to be fully loaded into cache.</span></span> <span data-ttu-id="e31af-219">将首先加载主功能块，并将在后台加载剩余的功能块以启用前台操作，例如用户与应用程序交互，并提供最佳的感知性能。</span><span class="sxs-lookup"><span data-stu-id="e31af-219">The primary feature block will be loaded first, and the remaining feature blocks will be loaded in the background to enable foreground operations, such as user interaction with applications, to take place and provide optimal perceived performance.</span></span></p>
<p><span data-ttu-id="e31af-220">位掩码值：</span><span class="sxs-lookup"><span data-stu-id="e31af-220">Bit mask values:</span></span></p>
<p><span data-ttu-id="e31af-221">（0）从不：未设置任何位（值为0），不会执行自动加载，因为没有设置触发器。</span><span class="sxs-lookup"><span data-stu-id="e31af-221">(0) Never: No bits are set (value is 0), no auto loading will be performed, because there are no triggers set.</span></span></p>
<p><span data-ttu-id="e31af-222">（1） OnLaunch：当用户启动应用程序时开始加载。</span><span class="sxs-lookup"><span data-stu-id="e31af-222">(1) OnLaunch: Loading starts when a user starts an application.</span></span></p>
<p><span data-ttu-id="e31af-223">（2） OnRefresh：发布应用程序时开始加载。</span><span class="sxs-lookup"><span data-stu-id="e31af-223">(2) OnRefresh: Loading starts when the application is published.</span></span> <span data-ttu-id="e31af-224">只要添加或更新软件包记录（例如，当发生发布刷新时），就会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="e31af-224">This occurs whenever the package record is added or updated—for example, when a publishing refresh occurs.</span></span></p>
<p><span data-ttu-id="e31af-225">（4） OnLogin：用户登录时开始加载。</span><span class="sxs-lookup"><span data-stu-id="e31af-225">(4) OnLogin: Loading starts when a user logs in.</span></span></p>
<p><span data-ttu-id="e31af-226">（5） OnLaunch 和 OnLogin： Default。</span><span class="sxs-lookup"><span data-stu-id="e31af-226">(5) OnLaunch and OnLogin: Default.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e31af-227">AutoLoadTarget</span><span class="sxs-lookup"><span data-stu-id="e31af-227">AutoLoadTarget</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-228">DWORD</span><span class="sxs-lookup"><span data-stu-id="e31af-228">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-229">默认值 = 1</span><span class="sxs-lookup"><span data-stu-id="e31af-229">Default=1</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-230">指示在任何给定的 AutoLoad 触发器出现时将自动加载的内容。</span><span class="sxs-lookup"><span data-stu-id="e31af-230">Indicates what will be auto-loaded when any given AutoLoad triggers occur.</span></span> <span data-ttu-id="e31af-231">位掩码值：</span><span class="sxs-lookup"><span data-stu-id="e31af-231">Bit mask values:</span></span></p>
<p><span data-ttu-id="e31af-232">（0）无：不自动加载，无论可设置哪些触发器。</span><span class="sxs-lookup"><span data-stu-id="e31af-232">(0) None: No auto-loading, regardless of what triggers may be set.</span></span></p>
<p><span data-ttu-id="e31af-233">（1） PreviouslyUsed （默认值）：如果启用了任何 AutoLoad 触发器，则仅加载程序包中之前已使用过一个应用程序的程序包（即，已启动或 precached）。</span><span class="sxs-lookup"><span data-stu-id="e31af-233">(1) PreviouslyUsed (default): If any AutoLoad trigger is enabled, load only the packages where at least one application in the package has been previously used—that is, started or precached.</span></span></p>
<p><span data-ttu-id="e31af-234">（2）所有：如果启用了任何 AutoLoad 触发器，程序包中的所有应用程序（每个程序包）或所有程序包（为客户端设置）将自动加载，无论它们是否已启动。</span><span class="sxs-lookup"><span data-stu-id="e31af-234">(2) All: If any AutoLoad trigger is enabled, all applications in the package (per package) or all packages (set for client) will be automatically loaded, whether or not they have ever been started.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e31af-235">RequireAuthorizationIfCached</span><span class="sxs-lookup"><span data-stu-id="e31af-235">RequireAuthorizationIfCached</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-236">DWORD</span><span class="sxs-lookup"><span data-stu-id="e31af-236">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-237">默认值 = 1</span><span class="sxs-lookup"><span data-stu-id="e31af-237">Default=1</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-238">指示始终需要授权，无论应用程序是否已在缓存中。</span><span class="sxs-lookup"><span data-stu-id="e31af-238">Indicates that authorization is always required, whether or not an application is already in cache.</span></span> <span data-ttu-id="e31af-239">可能值：</span><span class="sxs-lookup"><span data-stu-id="e31af-239">Possible values:</span></span></p>
<p><span data-ttu-id="e31af-240">0 = False：始终尝试连接到服务器。</span><span class="sxs-lookup"><span data-stu-id="e31af-240">0=False: Always try to connect to the server.</span></span> <span data-ttu-id="e31af-241">如果无法建立与服务器的连接，客户端仍允许用户启动以前加载到缓存中的应用程序。</span><span class="sxs-lookup"><span data-stu-id="e31af-241">If a connection to the server cannot be established, the client still allows the user to launch an application that has previously been loaded into cache.</span></span></p>
<p><span data-ttu-id="e31af-242">1 = True （默认值）：应用程序始终必须在启动时获得授权。</span><span class="sxs-lookup"><span data-stu-id="e31af-242">1=True (default): Application always must be authorized at startup.</span></span> <span data-ttu-id="e31af-243">对于 RTSP 流处理应用程序，将向服务器发送用户授权令牌以进行授权。</span><span class="sxs-lookup"><span data-stu-id="e31af-243">For RTSP streamed applications, the user authorization token is sent to the server for authorization.</span></span> <span data-ttu-id="e31af-244">对于基于文件的应用程序，文件 Acl 控制用户是否可以访问应用程序。</span><span class="sxs-lookup"><span data-stu-id="e31af-244">For file-based applications, file ACLs control whether a user may access the application.</span></span></p>
<p><span data-ttu-id="e31af-245">重新启动 sftlist 服务以使更改生效。</span><span class="sxs-lookup"><span data-stu-id="e31af-245">Restart the sftlist service for the change to take effect.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e31af-246">UserDataDirectory</span><span class="sxs-lookup"><span data-stu-id="e31af-246">UserDataDirectory</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-247">字符串</span><span class="sxs-lookup"><span data-stu-id="e31af-247">String</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-248">APPDATA</span><span class="sxs-lookup"><span data-stu-id="e31af-248">%APPDATA%</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-249">存储图标缓存和用户设置的位置。</span><span class="sxs-lookup"><span data-stu-id="e31af-249">Location where the icon cache and user settings are stored.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e31af-250">GlobalDataDirectory</span><span class="sxs-lookup"><span data-stu-id="e31af-250">GlobalDataDirectory</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-251">字符串</span><span class="sxs-lookup"><span data-stu-id="e31af-251">String</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-252">C:\Users\Public\Documents</span><span class="sxs-lookup"><span data-stu-id="e31af-252">C:\Users\Public\Documents</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-253">用于全局 App-v 数据的目录，包括用于 OSD 文件、图标文件、快捷方式信息和 SystemGuard 资源（如 .ini 文件）的缓存。</span><span class="sxs-lookup"><span data-stu-id="e31af-253">Directory to use for global App-V data, including caches for OSD files, icon files, shortcut information, and SystemGuard resources such as .ini files.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e31af-254">AllowCrashes</span><span class="sxs-lookup"><span data-stu-id="e31af-254">AllowCrashes</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-255">DWORD</span><span class="sxs-lookup"><span data-stu-id="e31af-255">DWORD</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-256">0 或 1</span><span class="sxs-lookup"><span data-stu-id="e31af-256">0 or 1</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-257">默认值 = 0：值0表示客户端尝试捕获内部程序异常，以便其他用户应用程序可以在发生崩溃时恢复和继续。</span><span class="sxs-lookup"><span data-stu-id="e31af-257">Default=0: A value of 0 means that the client tries to catch internal program exceptions so that other user applications can recover and continue when a crash happens.</span></span> <span data-ttu-id="e31af-258">值1表示客户端允许出现内部程序异常，以便可以在调试程序中捕获它们。</span><span class="sxs-lookup"><span data-stu-id="e31af-258">A value of 1 means that the client allows the internal program exceptions to occur so that they can be captured in a debugger.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e31af-259">CoreInternalTimeout</span><span class="sxs-lookup"><span data-stu-id="e31af-259">CoreInternalTimeout</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-260">DWORD</span><span class="sxs-lookup"><span data-stu-id="e31af-260">DWORD</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-261">60</span><span class="sxs-lookup"><span data-stu-id="e31af-261">60</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-262">内核和前端之间的内部 IPC 请求超时（以秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="e31af-262">Time-out in seconds for internal IPC requests between core and front-end.</span></span> <span data-ttu-id="e31af-263">请勿修改。</span><span class="sxs-lookup"><span data-stu-id="e31af-263">Do not modify.</span></span> </p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e31af-264">DefaultSuiteCombineTime</span><span class="sxs-lookup"><span data-stu-id="e31af-264">DefaultSuiteCombineTime</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-265">DWORD</span><span class="sxs-lookup"><span data-stu-id="e31af-265">DWORD</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-266">10</span><span class="sxs-lookup"><span data-stu-id="e31af-266">10</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-267">此值用于指示启动程序后不久，在同一套件中运行另一个应用程序时，不会生成任何错误消息。</span><span class="sxs-lookup"><span data-stu-id="e31af-267">This value is used to indicate how soon after being started that a program can shut down and not generate any error messages when another application in the same suite is running.</span></span> </p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e31af-268">SerializedSuiteLaunchTimeout</span><span class="sxs-lookup"><span data-stu-id="e31af-268">SerializedSuiteLaunchTimeout</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-269">DWORD</span><span class="sxs-lookup"><span data-stu-id="e31af-269">DWORD</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-270">默认 = 60000</span><span class="sxs-lookup"><span data-stu-id="e31af-270">Default=60000</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-271">定义当尝试序列化程序在同一套件中启动时，客户端将等待的时间（以毫秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="e31af-271">Defines how long in milliseconds the client will wait as it tries to serialize program starts in the same suite.</span></span> <span data-ttu-id="e31af-272">如果客户端超时，程序启动将继续，但不会序列化。</span><span class="sxs-lookup"><span data-stu-id="e31af-272">If the client times out, the program start will continue but it will not be serialized.</span></span> </p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e31af-273">ScriptTimeout</span><span class="sxs-lookup"><span data-stu-id="e31af-273">ScriptTimeout</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-274">DWORD</span><span class="sxs-lookup"><span data-stu-id="e31af-274">DWORD</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-275">300</span><span class="sxs-lookup"><span data-stu-id="e31af-275">300</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-276">如果 WAIT = TRUE，则 OSD 文件中脚本的默认超时值（以秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="e31af-276">Default time-out in seconds for scripts in OSD file if WAIT=TRUE.</span></span> <span data-ttu-id="e31af-277">你可以通过超时（而不是等待）指定每脚本超时。</span><span class="sxs-lookup"><span data-stu-id="e31af-277">You can specify per-script time-outs with TIMEOUT instead of WAIT.</span></span> <span data-ttu-id="e31af-278">值0表示无等待，0xFFFFFFFF 表示永久等待。</span><span class="sxs-lookup"><span data-stu-id="e31af-278">A value of 0 means no wait, and 0xFFFFFFFF means wait forever.</span></span> </p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e31af-279">LaunchRecordLogPath</span><span class="sxs-lookup"><span data-stu-id="e31af-279">LaunchRecordLogPath</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-280">字符串</span><span class="sxs-lookup"><span data-stu-id="e31af-280">String</span></span> </p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="e31af-281">如果在 HKLM 或 HKCU 下，此值包含日志文件的有效路径，SFTTray 将在程序启动、关闭、启动失败时写入此日志，进入或退出断开连接模式。</span><span class="sxs-lookup"><span data-stu-id="e31af-281">If, under either HKLM or HKCU, this value contains a valid path to a log file, SFTTray will write to this log when programs start, shut down, fail to launch, and enter or exit disconnected mode.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e31af-282">LaunchRecordMask</span><span class="sxs-lookup"><span data-stu-id="e31af-282">LaunchRecordMask</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-283">DWORD</span><span class="sxs-lookup"><span data-stu-id="e31af-283">DWORD</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-284">0x1A （26）日志启动错误和断开模式进入和退出活动。</span><span class="sxs-lookup"><span data-stu-id="e31af-284">0x1A (26) log launch errors and disconnected mode entry and exit activity.</span></span></p>
<p><span data-ttu-id="e31af-285">0x1F （31）记录所有内容。</span><span class="sxs-lookup"><span data-stu-id="e31af-285">0x1F (31) logs everything.</span></span></p>
<p><span data-ttu-id="e31af-286">0x0 （0）不记录任何内容。</span><span class="sxs-lookup"><span data-stu-id="e31af-286">0x0 (0) logs nothing.</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-287">指定要记录的五个事件中的哪一个（位掩码值）：</span><span class="sxs-lookup"><span data-stu-id="e31af-287">Specifies which of the five events are logged (bitmask values):</span></span></p>
<p><span data-ttu-id="e31af-288">1表示程序启动</span><span class="sxs-lookup"><span data-stu-id="e31af-288">1 for program starts</span></span></p>
<p><span data-ttu-id="e31af-289">2表示启动失败错误</span><span class="sxs-lookup"><span data-stu-id="e31af-289">2 for launch failure errors</span></span></p>
<p><span data-ttu-id="e31af-290">4个用于关机</span><span class="sxs-lookup"><span data-stu-id="e31af-290">4 for shutdowns</span></span></p>
<p><span data-ttu-id="e31af-291">8用于进入断开连接模式</span><span class="sxs-lookup"><span data-stu-id="e31af-291">8 for entering disconnected mode</span></span></p>
<p><span data-ttu-id="e31af-292">16用于退出断开连接模式以重新连接到服务器</span><span class="sxs-lookup"><span data-stu-id="e31af-292">16 for exiting disconnected mode to reconnect to a server</span></span></p>
<p><span data-ttu-id="e31af-293">添加这些号码的任意组合以打开各自的邮件。</span><span class="sxs-lookup"><span data-stu-id="e31af-293">Add any combination of those numbers to turn on the respective messages.</span></span> <span data-ttu-id="e31af-294">如果注册表中不0x1F，则默认为 ""。</span><span class="sxs-lookup"><span data-stu-id="e31af-294">Defaults to 0x1F if not in registry.</span></span> </p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e31af-295">LaunchRecordWriteTimeout</span><span class="sxs-lookup"><span data-stu-id="e31af-295">LaunchRecordWriteTimeout</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-296">DWORD</span><span class="sxs-lookup"><span data-stu-id="e31af-296">DWORD</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-297">默认 = 3000</span><span class="sxs-lookup"><span data-stu-id="e31af-297">Default=3000</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-298">指定在尝试写入启动记录日志时托盘将等待多长时间（如果另一个进程正在使用它）。</span><span class="sxs-lookup"><span data-stu-id="e31af-298">Specifies in milliseconds how long the tray will wait when trying to write to the launch record log if another process is using it.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e31af-299">ImportSearchPath</span><span class="sxs-lookup"><span data-stu-id="e31af-299">ImportSearchPath</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-300">字符串</span><span class="sxs-lookup"><span data-stu-id="e31af-300">String</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-301">d:\files;C:\documents 和 settings\user1\SFTs</span><span class="sxs-lookup"><span data-stu-id="e31af-301">d:\files;C:\documents and settings\user1\SFTs</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-302">一个分号分隔的列表，其中列出了最多五个目录，可在提示用户选择目录之前搜索便携式 SFT 文件。</span><span class="sxs-lookup"><span data-stu-id="e31af-302">A semicolon delimited list of up to five directories to search for portable SFT files before prompting the user to select a directory.</span></span> <span data-ttu-id="e31af-303">路径中的尾部反斜杠是可选的。</span><span class="sxs-lookup"><span data-stu-id="e31af-303">Trailing backslash in paths is optional.</span></span> <span data-ttu-id="e31af-304">默认情况下，此值不存在，必须手动设置。</span><span class="sxs-lookup"><span data-stu-id="e31af-304">This value is not present by default and must be set manually.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e31af-305">UserImportPath</span><span class="sxs-lookup"><span data-stu-id="e31af-305">UserImportPath</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-306">字符串</span><span class="sxs-lookup"><span data-stu-id="e31af-306">String</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-307">D:\SFTs</span><span class="sxs-lookup"><span data-stu-id="e31af-307">D:\SFTs</span></span>\ </p></td>
<td align="left"><p><span data-ttu-id="e31af-308">仅在 HKCU 下有效。</span><span class="sxs-lookup"><span data-stu-id="e31af-308">Valid only under HKCU.</span></span> <span data-ttu-id="e31af-309">查找程序包导入的 SFT 文件时用户浏览到的最后一个位置。</span><span class="sxs-lookup"><span data-stu-id="e31af-309">The last location the user browsed to while finding a SFT file for package import.</span></span> <span data-ttu-id="e31af-310">如果已成功找到 SFT，则自动设置。</span><span class="sxs-lookup"><span data-stu-id="e31af-310">Set automatically if the SFT is found successfully.</span></span> <span data-ttu-id="e31af-311">当尝试自动查找 SFT 文件时，将在连续的导入中使用此功能。</span><span class="sxs-lookup"><span data-stu-id="e31af-311">This is used on successive imports when trying to automatically locate SFT files.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="e31af-312">共享密钥</span><span class="sxs-lookup"><span data-stu-id="e31af-312">Shared Key</span></span>


<span data-ttu-id="e31af-313">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Shared 键控制跨 app-v 组件共享的值。</span><span class="sxs-lookup"><span data-stu-id="e31af-313">The HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Shared key controls values that are shared across App-V components.</span></span> <span data-ttu-id="e31af-314">下表提供了与共享密钥相关联的注册表值的相关信息。</span><span class="sxs-lookup"><span data-stu-id="e31af-314">The following table provides information about the registry values associated with the Shared key.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e31af-315">名称</span><span class="sxs-lookup"><span data-stu-id="e31af-315">Name</span></span> </th>
<th align="left"><span data-ttu-id="e31af-316">类型</span><span class="sxs-lookup"><span data-stu-id="e31af-316">Type</span></span> </th>
<th align="left"><span data-ttu-id="e31af-317">数据（示例）</span><span class="sxs-lookup"><span data-stu-id="e31af-317">Data (Examples)</span></span> </th>
<th align="left"><span data-ttu-id="e31af-318">描述</span><span class="sxs-lookup"><span data-stu-id="e31af-318">Description</span></span> </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e31af-319">DumpPath</span><span class="sxs-lookup"><span data-stu-id="e31af-319">DumpPath</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-320">字符串</span><span class="sxs-lookup"><span data-stu-id="e31af-320">String</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-321">默认值 = C：</span><span class="sxs-lookup"><span data-stu-id="e31af-321">Default=C:</span></span>\ </p></td>
<td align="left"><p><span data-ttu-id="e31af-322">在异常上生成小型转储时创建转储文件的默认路径。</span><span class="sxs-lookup"><span data-stu-id="e31af-322">Default path to create dump files when generating a minidump on an exception.</span></span> <span data-ttu-id="e31af-323">默认值为 C：\如果未指定，则为。</span><span class="sxs-lookup"><span data-stu-id="e31af-323">This defaults to C:\ if not specified.</span></span> <span data-ttu-id="e31af-324">客户端安装程序将此密钥设置为 &lt; 应用虚拟化全局数据目录 &gt; \Dumps。</span><span class="sxs-lookup"><span data-stu-id="e31af-324">The Client installer sets this key to the &lt;App Virtualization global data directory&gt;\Dumps.</span></span> <span data-ttu-id="e31af-325">Sequencer 安装程序将此密钥设置为安装目录。</span><span class="sxs-lookup"><span data-stu-id="e31af-325">The Sequencer installer sets this key to the installation directory.</span></span> </p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e31af-326">DumpPathSizeLimit</span><span class="sxs-lookup"><span data-stu-id="e31af-326">DumpPathSizeLimit</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-327">DWORD</span><span class="sxs-lookup"><span data-stu-id="e31af-327">DWORD</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-328">1000</span><span class="sxs-lookup"><span data-stu-id="e31af-328">1000</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-329">指定可用于存储 minidumps 的磁盘空间的最大总数量（以 mb 为单位）。</span><span class="sxs-lookup"><span data-stu-id="e31af-329">Specifies the maximum total amount of disk space in megabytes that can be used to store minidumps.</span></span> <span data-ttu-id="e31af-330">默认值 = 1000 MB。</span><span class="sxs-lookup"><span data-stu-id="e31af-330">Default = 1000 MB.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="e31af-331">网络密钥</span><span class="sxs-lookup"><span data-stu-id="e31af-331">Network Key</span></span>


<span data-ttu-id="e31af-332">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Network 键控制各种与网络相关的参数。</span><span class="sxs-lookup"><span data-stu-id="e31af-332">The HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Network key controls a variety of network-related parameters.</span></span> <span data-ttu-id="e31af-333">此密钥主要由网络传输代理使用。</span><span class="sxs-lookup"><span data-stu-id="e31af-333">This key is primarily used by the network transport agent.</span></span> <span data-ttu-id="e31af-334">下表提供了与网络密钥相关联的注册表值的相关信息。</span><span class="sxs-lookup"><span data-stu-id="e31af-334">The following table provides information about the registry values associated with the Network key.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e31af-335">名称</span><span class="sxs-lookup"><span data-stu-id="e31af-335">Name</span></span> </th>
<th align="left"><span data-ttu-id="e31af-336">类型</span><span class="sxs-lookup"><span data-stu-id="e31af-336">Type</span></span> </th>
<th align="left"><span data-ttu-id="e31af-337">数据（示例）</span><span class="sxs-lookup"><span data-stu-id="e31af-337">Data (Examples)</span></span> </th>
<th align="left"><span data-ttu-id="e31af-338">描述</span><span class="sxs-lookup"><span data-stu-id="e31af-338">Description</span></span> </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e31af-339">Online</span><span class="sxs-lookup"><span data-stu-id="e31af-339">Online</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-340">DWORD</span><span class="sxs-lookup"><span data-stu-id="e31af-340">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-341">默认值 = 1</span><span class="sxs-lookup"><span data-stu-id="e31af-341">Default=1</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-342">启用或禁用脱机模式。</span><span class="sxs-lookup"><span data-stu-id="e31af-342">Enables or disables offline mode.</span></span> <span data-ttu-id="e31af-343">如果设置为0，则客户端将不会与 App-v 管理服务器或发布服务器通信。</span><span class="sxs-lookup"><span data-stu-id="e31af-343">If set to 0, the client will not communicate with App-V Management Servers or publishing servers.</span></span> <span data-ttu-id="e31af-344">在断开连接的操作中，客户端可以启动加载的应用程序，即使它未连接到 app-v 管理服务器也是如此。</span><span class="sxs-lookup"><span data-stu-id="e31af-344">In disconnected operations, the client can start a loaded application even when it is not connected to an App-V Management Server.</span></span> <span data-ttu-id="e31af-345">在脱机模式下，客户端不会尝试连接到 app-v 管理服务器或发布服务器。</span><span class="sxs-lookup"><span data-stu-id="e31af-345">In offline mode, the client does not attempt to connect to an App-V Management Server or publishing server.</span></span> <span data-ttu-id="e31af-346">您必须允许断开连接的操作能够脱机工作。</span><span class="sxs-lookup"><span data-stu-id="e31af-346">You must allow disconnected operations to be able to work offline.</span></span> <span data-ttu-id="e31af-347">默认值为1（联机），并且0为 "已禁用" （脱机）。</span><span class="sxs-lookup"><span data-stu-id="e31af-347">Default value is 1 enabled (online), and 0 is disabled (offline).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e31af-348">AllowDisconnectedOperation</span><span class="sxs-lookup"><span data-stu-id="e31af-348">AllowDisconnectedOperation</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-349">DWORD</span><span class="sxs-lookup"><span data-stu-id="e31af-349">DWORD</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-350">默认值 = 1</span><span class="sxs-lookup"><span data-stu-id="e31af-350">Default=1</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-351">启用或禁用断开连接的操作。</span><span class="sxs-lookup"><span data-stu-id="e31af-351">Enables or disables disconnected operation.</span></span> <span data-ttu-id="e31af-352">默认值为1，并且禁用0。</span><span class="sxs-lookup"><span data-stu-id="e31af-352">Default value is 1 enabled, and 0 is disabled.</span></span> <span data-ttu-id="e31af-353">启用断开连接操作后，即使未连接到 App-v 管理服务器，App-v 客户端也可以启动加载的应用程序。</span><span class="sxs-lookup"><span data-stu-id="e31af-353">When disconnected operations are enabled, the App-V client can start a loaded application even when it is not connected to an App-V Management Server.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e31af-354">FastConnectTimeout</span><span class="sxs-lookup"><span data-stu-id="e31af-354">FastConnectTimeout</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-355">DWORD</span><span class="sxs-lookup"><span data-stu-id="e31af-355">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-356">默认值 = 1000</span><span class="sxs-lookup"><span data-stu-id="e31af-356">Default=1000</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-357">此值指定 TCP 连接超时值（以毫秒为单位），用于确定何时进入断开连接的操作模式。</span><span class="sxs-lookup"><span data-stu-id="e31af-357">This value specifies the TCP connect time-out in milliseconds to determine when to go into disconnected operations mode.</span></span> <span data-ttu-id="e31af-358">此值可用于替代20秒的默认 ConnectTimeout （用于网络事务的 App-v connect 超时）或系统的 TCP 超时约25秒。</span><span class="sxs-lookup"><span data-stu-id="e31af-358">This value can be used to override the default ConnectTimeout of 20 seconds (App-V connect time-out for network transactions) or the system’s TCP time-out of approximately 25 seconds.</span></span> <span data-ttu-id="e31af-359">这会将客户端快速带入断开连接的操作模式。</span><span class="sxs-lookup"><span data-stu-id="e31af-359">This brings the client into disconnected operations mode quickly.</span></span> <span data-ttu-id="e31af-360">在下一次连接时应用。</span><span class="sxs-lookup"><span data-stu-id="e31af-360">Applied on the next connect.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e31af-361">LimitDisconnectedOperation</span><span class="sxs-lookup"><span data-stu-id="e31af-361">LimitDisconnectedOperation</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-362">DWORD</span><span class="sxs-lookup"><span data-stu-id="e31af-362">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-363">默认值 = 1</span><span class="sxs-lookup"><span data-stu-id="e31af-363">Default=1</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-364">仅适用于 AllowDisconnectedOperation 为1的情况下，"已启用"。</span><span class="sxs-lookup"><span data-stu-id="e31af-364">Applicable only if AllowDisconnectedOperation is 1, enabled.</span></span> <span data-ttu-id="e31af-365">此值确定在断开连接的操作中允许客户端运行多长时间时是否会出现时间限制。</span><span class="sxs-lookup"><span data-stu-id="e31af-365">This value determines whether there will be a time limit for how long the client will be allowed to operate in disconnected operations.</span></span> <span data-ttu-id="e31af-366">1 = 受限。</span><span class="sxs-lookup"><span data-stu-id="e31af-366">1=limited.</span></span> <span data-ttu-id="e31af-367">0 = 无限制。</span><span class="sxs-lookup"><span data-stu-id="e31af-367">0=unlimited.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e31af-368">DOTimeoutMinutes</span><span class="sxs-lookup"><span data-stu-id="e31af-368">DOTimeoutMinutes</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-369">DWORD</span><span class="sxs-lookup"><span data-stu-id="e31af-369">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-370">默认值 = 129600</span><span class="sxs-lookup"><span data-stu-id="e31af-370">Default=129,600</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-371">指示在断开连接的操作模式下可以使用的应用程序的分钟数。</span><span class="sxs-lookup"><span data-stu-id="e31af-371">Indicates how many minutes an application may be used in disconnected operation mode.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="e31af-372">有效值为 1-以分钟为单位的999999（1-1439998560 分钟）。</span><span class="sxs-lookup"><span data-stu-id="e31af-372">The valid values are 1–999,999 in days expressed in minutes (1–1,439,998,560 minutes).</span></span> <span data-ttu-id="e31af-373">默认值为90天或129600分钟。</span><span class="sxs-lookup"><span data-stu-id="e31af-373">The default value is 90 days or 129,600 minutes.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e31af-374">协议</span><span class="sxs-lookup"><span data-stu-id="e31af-374">Protocol</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-375">DWORD</span><span class="sxs-lookup"><span data-stu-id="e31af-375">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-376">默认值 = 8</span><span class="sxs-lookup"><span data-stu-id="e31af-376">Default=8</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-377">要使用的默认协议（TCP 与 SSL）。</span><span class="sxs-lookup"><span data-stu-id="e31af-377">Default protocol to use (TCP vs SSL).</span></span> <span data-ttu-id="e31af-378">在 "选项" 对话框中配置。</span><span class="sxs-lookup"><span data-stu-id="e31af-378">Configure in Options Dialog.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e31af-379">ReadTimeout</span><span class="sxs-lookup"><span data-stu-id="e31af-379">ReadTimeout</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-380">DWORD</span><span class="sxs-lookup"><span data-stu-id="e31af-380">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-381">名</span><span class="sxs-lookup"><span data-stu-id="e31af-381">20</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-382">查看网络事务的超时时间（以秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="e31af-382">Read time-out for network transactions, in seconds.</span></span> <span data-ttu-id="e31af-383">请勿修改。</span><span class="sxs-lookup"><span data-stu-id="e31af-383">Do not modify.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e31af-384">WriteTimeout</span><span class="sxs-lookup"><span data-stu-id="e31af-384">WriteTimeout</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-385">DWORD</span><span class="sxs-lookup"><span data-stu-id="e31af-385">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-386">名</span><span class="sxs-lookup"><span data-stu-id="e31af-386">20</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-387">为网络事务写超时（以秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="e31af-387">Write time-out for network transactions, in seconds.</span></span> <span data-ttu-id="e31af-388">请勿修改。</span><span class="sxs-lookup"><span data-stu-id="e31af-388">Do not modify.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e31af-389">ConnectTimeout</span><span class="sxs-lookup"><span data-stu-id="e31af-389">ConnectTimeout</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-390">DWORD</span><span class="sxs-lookup"><span data-stu-id="e31af-390">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-391">名</span><span class="sxs-lookup"><span data-stu-id="e31af-391">20</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-392">为网络事务连接超时（以秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="e31af-392">Connect time-out for network transactions, in seconds.</span></span> <span data-ttu-id="e31af-393">请勿修改。</span><span class="sxs-lookup"><span data-stu-id="e31af-393">Do not modify.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e31af-394">ReestablishmentRetries</span><span class="sxs-lookup"><span data-stu-id="e31af-394">ReestablishmentRetries</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-395">DWORD</span><span class="sxs-lookup"><span data-stu-id="e31af-395">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-396">三维空间</span><span class="sxs-lookup"><span data-stu-id="e31af-396">3</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-397">尝试重新建立已删除会话的次数。</span><span class="sxs-lookup"><span data-stu-id="e31af-397">The number of times to try to reestablish a dropped session.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e31af-398">ReestablishmentInterval</span><span class="sxs-lookup"><span data-stu-id="e31af-398">ReestablishmentInterval</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-399">DWORD</span><span class="sxs-lookup"><span data-stu-id="e31af-399">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-400">岁</span><span class="sxs-lookup"><span data-stu-id="e31af-400">15</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-401">在尝试重新建立已删除的会话之间等待的秒数。</span><span class="sxs-lookup"><span data-stu-id="e31af-401">The number of seconds to wait between tries to reestablish a dropped session.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="e31af-402">Http 密钥</span><span class="sxs-lookup"><span data-stu-id="e31af-402">Http Key</span></span>


<span data-ttu-id="e31af-403">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Network\\Http 键控制与 Http 流相关的参数。</span><span class="sxs-lookup"><span data-stu-id="e31af-403">The HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Network\\Http key controls the parameters that are related to Http streaming.</span></span> <span data-ttu-id="e31af-404">此密钥主要由网络传输代理使用。</span><span class="sxs-lookup"><span data-stu-id="e31af-404">This key is used primarily by the network transport agent.</span></span> <span data-ttu-id="e31af-405">下表提供了与 Http 密钥相关联的注册表值的相关信息。</span><span class="sxs-lookup"><span data-stu-id="e31af-405">The following table provides information about the registry values that are associated with the Http key.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e31af-406">名称</span><span class="sxs-lookup"><span data-stu-id="e31af-406">Name</span></span> </th>
<th align="left"><span data-ttu-id="e31af-407">类型</span><span class="sxs-lookup"><span data-stu-id="e31af-407">Type</span></span> </th>
<th align="left"><span data-ttu-id="e31af-408">数据（示例）</span><span class="sxs-lookup"><span data-stu-id="e31af-408">Data (Examples)</span></span> </th>
<th align="left"><span data-ttu-id="e31af-409">描述</span><span class="sxs-lookup"><span data-stu-id="e31af-409">Description</span></span> </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e31af-410">LaunchIfNotFound</span><span class="sxs-lookup"><span data-stu-id="e31af-410">LaunchIfNotFound</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-411">DWORD</span><span class="sxs-lookup"><span data-stu-id="e31af-411">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-412">默认值 = 0</span><span class="sxs-lookup"><span data-stu-id="e31af-412">Default=0</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-413">控制当与 http 服务器建立连接且该程序包文件不再存在于 HTTP 服务器上时 HTTP 流的行为。</span><span class="sxs-lookup"><span data-stu-id="e31af-413">Controls the behavior of HTTP streaming when a connection to the HTTP server can be established and the package file no longer exists on the HTTP server.</span></span> <span data-ttu-id="e31af-414">如果值不存在或未设置为1，则 App-v 客户端不允许启动以前加载到缓存中的应用程序。</span><span class="sxs-lookup"><span data-stu-id="e31af-414">If the value does not exist or if it is not set to 1, the App-V client does not let you launch an application that has previously been loaded into cache.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="e31af-415">raid-1</span><span class="sxs-lookup"><span data-stu-id="e31af-415">1</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-416">如果此值设置为1，则 App-v 客户端允许你启动以前加载到缓存中的应用程序。</span><span class="sxs-lookup"><span data-stu-id="e31af-416">If this value is set to 1, the App-V client lets you launch an application that has previously been loaded into cache.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="e31af-417">文件系统密钥</span><span class="sxs-lookup"><span data-stu-id="e31af-417">File System Key</span></span>


<span data-ttu-id="e31af-418">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\AppFS 键下包含的值控制 App-v 的文件系统参数。</span><span class="sxs-lookup"><span data-stu-id="e31af-418">The values that are contained under the HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\AppFS key control the file system parameters for App-V.</span></span> <span data-ttu-id="e31af-419">下表提供了与 AppFS 键相关联的注册表值的相关信息。</span><span class="sxs-lookup"><span data-stu-id="e31af-419">The following table provides information about the registry values associated with the AppFS key.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e31af-420">名称</span><span class="sxs-lookup"><span data-stu-id="e31af-420">Name</span></span> </th>
<th align="left"><span data-ttu-id="e31af-421">类型</span><span class="sxs-lookup"><span data-stu-id="e31af-421">Type</span></span> </th>
<th align="left"><span data-ttu-id="e31af-422">数据（示例）</span><span class="sxs-lookup"><span data-stu-id="e31af-422">Data (Examples)</span></span> </th>
<th align="left"><span data-ttu-id="e31af-423">描述</span><span class="sxs-lookup"><span data-stu-id="e31af-423">Description</span></span> </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e31af-424">FileSize</span><span class="sxs-lookup"><span data-stu-id="e31af-424">FileSize</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-425">DWORD</span><span class="sxs-lookup"><span data-stu-id="e31af-425">DWORD</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-426">4096</span><span class="sxs-lookup"><span data-stu-id="e31af-426">4096</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-427">文件系统缓存文件的最大大小（以 mb 为单位）。</span><span class="sxs-lookup"><span data-stu-id="e31af-427">Maximum size in megabytes of file system cache file.</span></span> <span data-ttu-id="e31af-428">如果在注册表中更改此值，则必须将状态设置为0，然后重新启动。</span><span class="sxs-lookup"><span data-stu-id="e31af-428">If you change this value in the registry, you must set State to 0 and reboot.</span></span> </p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e31af-429">FileName</span><span class="sxs-lookup"><span data-stu-id="e31af-429">FileName</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-430">字符串</span><span class="sxs-lookup"><span data-stu-id="e31af-430">String</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-431">C:\Users\Public\Documents\SoftGrid Client\sftfs.fsd</span><span class="sxs-lookup"><span data-stu-id="e31af-431">C:\Users\Public\Documents\SoftGrid Client\sftfs.fsd</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-432">文件系统缓存文件的位置。</span><span class="sxs-lookup"><span data-stu-id="e31af-432">Location of file system cache file.</span></span> <span data-ttu-id="e31af-433">如果在注册表中更改此值，则必须将 FileSize 保留相同，然后重新启动或将状态设置为0，然后重新启动。</span><span class="sxs-lookup"><span data-stu-id="e31af-433">If you change this value in the registry, you must either leave FileSize the same and reboot or set State to 0 and reboot.</span></span> </p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e31af-434">DriveLetter</span><span class="sxs-lookup"><span data-stu-id="e31af-434">DriveLetter</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-435">字符串</span><span class="sxs-lookup"><span data-stu-id="e31af-435">String</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-436">问：</span><span class="sxs-lookup"><span data-stu-id="e31af-436">Q:</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-437">将挂载 app-v 文件系统的驱动器（如果可用）。</span><span class="sxs-lookup"><span data-stu-id="e31af-437">Drive where App-V file system will be mounted, if it is available.</span></span> <span data-ttu-id="e31af-438">此值由侦听器或安装程序设置，并且由文件系统读取。</span><span class="sxs-lookup"><span data-stu-id="e31af-438">This value is set either by the listener or the installer, and it is read by the file system.</span></span> </p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e31af-439">State</span><span class="sxs-lookup"><span data-stu-id="e31af-439">State</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-440">DWORD</span><span class="sxs-lookup"><span data-stu-id="e31af-440">DWORD</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-441">0x100</span><span class="sxs-lookup"><span data-stu-id="e31af-441">0x100</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-442">文件系统的状态。</span><span class="sxs-lookup"><span data-stu-id="e31af-442">State of file system.</span></span> <span data-ttu-id="e31af-443">设置为0，然后重新启动以完全清除文件系统缓存。</span><span class="sxs-lookup"><span data-stu-id="e31af-443">Set to 0 and reboot to completely clear the file system cache.</span></span> </p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e31af-444">FileSystemStorage</span><span class="sxs-lookup"><span data-stu-id="e31af-444">FileSystemStorage</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-445">字符串</span><span class="sxs-lookup"><span data-stu-id="e31af-445">String</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-446">C:\Profiles\Joe\SG</span><span class="sxs-lookup"><span data-stu-id="e31af-446">C:\Profiles\Joe\SG</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-447">Symlinks 的路径，在 HKCU 下设置。</span><span class="sxs-lookup"><span data-stu-id="e31af-447">Path for symlinks, set under HKCU.</span></span> <span data-ttu-id="e31af-448">请勿修改（使用 "配置" 下的 "数据目录" 更改）。</span><span class="sxs-lookup"><span data-stu-id="e31af-448">Do not modify (use data directory under Configuration to change).</span></span> </p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e31af-449">GlobalFileSystemStorage</span><span class="sxs-lookup"><span data-stu-id="e31af-449">GlobalFileSystemStorage</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-450">字符串</span><span class="sxs-lookup"><span data-stu-id="e31af-450">String</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-451">C:\Users\Public\Documents\SoftGrid Client\AppFS 存储</span><span class="sxs-lookup"><span data-stu-id="e31af-451">C:\Users\Public\Documents\SoftGrid Client\AppFS Storage</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-452">全局文件系统数据的路径。</span><span class="sxs-lookup"><span data-stu-id="e31af-452">Path for global file system data.</span></span> <span data-ttu-id="e31af-453">请勿修改。</span><span class="sxs-lookup"><span data-stu-id="e31af-453">Do not modify.</span></span> </p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e31af-454">MaxPercentToLockInCache</span><span class="sxs-lookup"><span data-stu-id="e31af-454">MaxPercentToLockInCache</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-455">DWORD</span><span class="sxs-lookup"><span data-stu-id="e31af-455">DWORD</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-456">默认值 = 90</span><span class="sxs-lookup"><span data-stu-id="e31af-456">Default=90</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-457">指定可锁定的文件系统缓存文件的最大百分比。</span><span class="sxs-lookup"><span data-stu-id="e31af-457">Specifies the maximum percentage of the file system cache file that can be locked.</span></span> <span data-ttu-id="e31af-458">请勿修改。</span><span class="sxs-lookup"><span data-stu-id="e31af-458">Do not modify.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e31af-459">UnloadLeastRecentlyUsed</span><span class="sxs-lookup"><span data-stu-id="e31af-459">UnloadLeastRecentlyUsed</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-460">DWORD</span><span class="sxs-lookup"><span data-stu-id="e31af-460">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-461">默认值 = 1</span><span class="sxs-lookup"><span data-stu-id="e31af-461">Default=1</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-462">文件系统缓存空间管理功能使用最近最少使用的（LRU）算法，并且默认情况下处于启用状态。</span><span class="sxs-lookup"><span data-stu-id="e31af-462">The file system cache space management feature uses a Least Recently Used (LRU) algorithm and is enabled by default.</span></span> <span data-ttu-id="e31af-463">如果新程序包所需的空间超过缓存中的可用空间，则 App-v 客户端使用此功能确定它可以从缓存中删除的现有程序包（如果有），以便为新程序包腾出空间。</span><span class="sxs-lookup"><span data-stu-id="e31af-463">If the space that is required for a new package would exceed the available free space in the cache, the App-V Client uses this feature to determine which, if any, existing packages it can delete from the cache to make room for the new package.</span></span> <span data-ttu-id="e31af-464">如果上次访问日期比在 MinPkgAge 注册表值中指定的值旧，客户端将删除该程序包。</span><span class="sxs-lookup"><span data-stu-id="e31af-464">The client deletes the package with the oldest last-accessed date if it is older than the value specified in the MinPkgAge registry value.</span></span> <span data-ttu-id="e31af-465">值为0（已禁用）和1（默认值，已启用）。</span><span class="sxs-lookup"><span data-stu-id="e31af-465">Values are 0 (disabled) and 1 (default, enabled).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e31af-466">MinPackageAge</span><span class="sxs-lookup"><span data-stu-id="e31af-466">MinPackageAge</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-467">DWORD</span><span class="sxs-lookup"><span data-stu-id="e31af-467">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-468">raid-1</span><span class="sxs-lookup"><span data-stu-id="e31af-468">1</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-469">若要确定何时可以选择要放弃的程序包，请将此注册表值设置为等于自上次访问程序包后所需的最小天数。</span><span class="sxs-lookup"><span data-stu-id="e31af-469">To determine when the package can be selected for discard, set this registry value to equal the minimum number of days you want to elapse since the package was last accessed.</span></span> <span data-ttu-id="e31af-470">不会放弃最近使用过的程序包。</span><span class="sxs-lookup"><span data-stu-id="e31af-470">Packages that have been used more recently are not discarded.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="e31af-471">权限密钥</span><span class="sxs-lookup"><span data-stu-id="e31af-471">Permissions Key</span></span>


<span data-ttu-id="e31af-472">为了帮助防止用户犯错误，管理员可以使用 HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Permissions 键来控制对非管理用户的某些操作的访问权限，例如，防止用户意外卸载程序。</span><span class="sxs-lookup"><span data-stu-id="e31af-472">To help to prevent users from making mistakes, administrators can use the HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Permissions key to control access to some actions for non-administrative users—for example, to prevent users from accidentally unloading programs.</span></span> <span data-ttu-id="e31af-473">具有管理权限的用户可以提供任何这些权限。</span><span class="sxs-lookup"><span data-stu-id="e31af-473">Users with administrative rights can give themselves any of these permissions.</span></span> <span data-ttu-id="e31af-474">在共享系统（如远程桌面会话主机（RD 会话主机）服务器（以前称为终端服务器）系统）上，在向用户授予额外权限时要小心，因为这些权限中的某些权限将允许用户控制系统上所有用户使用的应用程序。</span><span class="sxs-lookup"><span data-stu-id="e31af-474">On shared systems, such as a Remote Desktop Session Host (RD Session Host) server (formerly Terminal Server) system, be careful when granting additional permissions to users because some of these permissions would enable users to control the applications used by all users on the system.</span></span> <span data-ttu-id="e31af-475">这些设置的可能值为1（允许）和0（不允许）。</span><span class="sxs-lookup"><span data-stu-id="e31af-475">Possible values for these settings are 1 (allow) and 0 (disallow).</span></span>

<span data-ttu-id="e31af-476">权限密钥设置控制启用命名操作的所有接口。</span><span class="sxs-lookup"><span data-stu-id="e31af-476">The Permissions key settings control all interfaces that enable the named actions.</span></span> <span data-ttu-id="e31af-477">其中包括 "选项" 对话框、"SFTTray" 和 "SFTMime"。</span><span class="sxs-lookup"><span data-stu-id="e31af-477">This includes the Options Dialog, SFTTray, and SFTMime.</span></span> <span data-ttu-id="e31af-478">这些设置不会影响管理员。</span><span class="sxs-lookup"><span data-stu-id="e31af-478">These settings do not affect administrators.</span></span> <span data-ttu-id="e31af-479">下表提供了与权限密钥相关联的注册表值的相关信息。</span><span class="sxs-lookup"><span data-stu-id="e31af-479">The following table provides information about the registry values associated with the Permissions key.</span></span>

<span data-ttu-id="e31af-480">名称类型数据（示例）描述 ChangeFSDrive</span><span class="sxs-lookup"><span data-stu-id="e31af-480">Name Type Data (Examples) Description ChangeFSDrive</span></span>

<span data-ttu-id="e31af-481">DWORD</span><span class="sxs-lookup"><span data-stu-id="e31af-481">DWORD</span></span>

<span data-ttu-id="e31af-482">默认值 = 0</span><span class="sxs-lookup"><span data-stu-id="e31af-482">Default=0</span></span>

<span data-ttu-id="e31af-483">值1允许用户选择用作文件系统驱动器的其他驱动器号。</span><span class="sxs-lookup"><span data-stu-id="e31af-483">A value of 1 allows users to pick a different drive letter to be used as the file system drive.</span></span>

<span data-ttu-id="e31af-484">ChangeCacheSize</span><span class="sxs-lookup"><span data-stu-id="e31af-484">ChangeCacheSize</span></span>

<span data-ttu-id="e31af-485">DWORD</span><span class="sxs-lookup"><span data-stu-id="e31af-485">DWORD</span></span>

<span data-ttu-id="e31af-486">默认值 = 0</span><span class="sxs-lookup"><span data-stu-id="e31af-486">Default=0</span></span>

<span data-ttu-id="e31af-487">值1允许用户更改缓存大小。</span><span class="sxs-lookup"><span data-stu-id="e31af-487">A value of 1 allows users to change the cache size.</span></span>

<span data-ttu-id="e31af-488">ChangeLogSettings</span><span class="sxs-lookup"><span data-stu-id="e31af-488">ChangeLogSettings</span></span>

<span data-ttu-id="e31af-489">DWORD</span><span class="sxs-lookup"><span data-stu-id="e31af-489">DWORD</span></span>

<span data-ttu-id="e31af-490">默认值 = 0</span><span class="sxs-lookup"><span data-stu-id="e31af-490">Default=0</span></span>

<span data-ttu-id="e31af-491">值1允许用户修改日志级别、更改其位置，然后通过用户界面重置它。</span><span class="sxs-lookup"><span data-stu-id="e31af-491">A value of 1 allows users to modify the log level, change its location, and reset it through the user interface.</span></span>

<span data-ttu-id="e31af-492">AddApp</span><span class="sxs-lookup"><span data-stu-id="e31af-492">AddApp</span></span>

<span data-ttu-id="e31af-493">DWORD</span><span class="sxs-lookup"><span data-stu-id="e31af-493">DWORD</span></span>

<span data-ttu-id="e31af-494">默认值 = 0</span><span class="sxs-lookup"><span data-stu-id="e31af-494">Default=0</span></span>

<span data-ttu-id="e31af-495">值1允许用户显式添加应用程序。</span><span class="sxs-lookup"><span data-stu-id="e31af-495">A value of 1 allows users to add applications explicitly.</span></span> <span data-ttu-id="e31af-496">这不会影响通过发布刷新添加的应用程序，也不会阻止用户启动（并因此隐式添加）尚未添加的应用程序。</span><span class="sxs-lookup"><span data-stu-id="e31af-496">This does not affect applications that are added through publishing refresh nor does it prevent users from starting (and thereby implicitly adding) applications that have not already been added.</span></span> <span data-ttu-id="e31af-497">值为0或1。</span><span class="sxs-lookup"><span data-stu-id="e31af-497">Values are 0 or 1.</span></span>

<span data-ttu-id="e31af-498">LoadApp</span><span class="sxs-lookup"><span data-stu-id="e31af-498">LoadApp</span></span> 

<span data-ttu-id="e31af-499">DWORD</span><span class="sxs-lookup"><span data-stu-id="e31af-499">DWORD</span></span> 

<span data-ttu-id="e31af-500">0</span><span class="sxs-lookup"><span data-stu-id="e31af-500">0</span></span>

<span data-ttu-id="e31af-501">不允许用户加载应用程序。</span><span class="sxs-lookup"><span data-stu-id="e31af-501">Does not allow a user to load an application.</span></span> <span data-ttu-id="e31af-502">这是 RD 会话主机的默认值。</span><span class="sxs-lookup"><span data-stu-id="e31af-502">This is the default for RD Session Hosts.</span></span> <span data-ttu-id="e31af-503">如果你是移动用户，你可能希望将应用程序中的应用程序完全加载到缓存中，以便在断开连接操作或脱机模式下使用它们。</span><span class="sxs-lookup"><span data-stu-id="e31af-503">If you are a mobile user, you might want to fully load your applications in the cache to use them during disconnected operation or offline mode.</span></span> <span data-ttu-id="e31af-504">若要从 app-v 管理服务器或 App-v 流式处理服务器流处理应用程序，必须连接到服务器才能加载应用程序。</span><span class="sxs-lookup"><span data-stu-id="e31af-504">To stream applications from the App-V Management Server or the App-V Streaming Server, you must be connected to a server to load applications.</span></span>

<span data-ttu-id="e31af-505">raid-1</span><span class="sxs-lookup"><span data-stu-id="e31af-505">1</span></span>

<span data-ttu-id="e31af-506">允许用户加载应用程序。</span><span class="sxs-lookup"><span data-stu-id="e31af-506">Allows a user to load an application.</span></span> <span data-ttu-id="e31af-507">这是 Windows 桌面版的默认设置。</span><span class="sxs-lookup"><span data-stu-id="e31af-507">This is the default for Windows desktops.</span></span> 

<span data-ttu-id="e31af-508">UnloadApp</span><span class="sxs-lookup"><span data-stu-id="e31af-508">UnloadApp</span></span> 

<span data-ttu-id="e31af-509">DWORD</span><span class="sxs-lookup"><span data-stu-id="e31af-509">DWORD</span></span> 

<span data-ttu-id="e31af-510">0</span><span class="sxs-lookup"><span data-stu-id="e31af-510">0</span></span>

<span data-ttu-id="e31af-511">不允许用户卸载应用程序。</span><span class="sxs-lookup"><span data-stu-id="e31af-511">Does not allow a user to unload an application.</span></span> <span data-ttu-id="e31af-512">加载或卸载程序包时，程序包中的所有应用程序都将加载到或从缓存中删除。</span><span class="sxs-lookup"><span data-stu-id="e31af-512">When you load or unload a package, all the applications in the package are loaded into or removed from cache.</span></span>

<span data-ttu-id="e31af-513">raid-1</span><span class="sxs-lookup"><span data-stu-id="e31af-513">1</span></span>

<span data-ttu-id="e31af-514">允许用户卸载应用程序。</span><span class="sxs-lookup"><span data-stu-id="e31af-514">Allows a user to unload an application.</span></span> 

<span data-ttu-id="e31af-515">LockApp</span><span class="sxs-lookup"><span data-stu-id="e31af-515">LockApp</span></span> 

<span data-ttu-id="e31af-516">DWORD</span><span class="sxs-lookup"><span data-stu-id="e31af-516">DWORD</span></span> 

<span data-ttu-id="e31af-517">0</span><span class="sxs-lookup"><span data-stu-id="e31af-517">0</span></span>

<span data-ttu-id="e31af-518">不允许用户锁定和解除锁定应用程序。</span><span class="sxs-lookup"><span data-stu-id="e31af-518">Does not allow a user to lock and unlock an application.</span></span> <span data-ttu-id="e31af-519">这是 RD 会话主机的默认值。</span><span class="sxs-lookup"><span data-stu-id="e31af-519">This is the default for RD Session Hosts.</span></span> <span data-ttu-id="e31af-520">无法从缓存中删除已锁定的应用程序，以便为新应用程序腾出空间。</span><span class="sxs-lookup"><span data-stu-id="e31af-520">A locked application cannot be removed from the cache to make room for new applications.</span></span> <span data-ttu-id="e31af-521">若要从远程桌面服务（以前称为终端服务）缓存的 App-v 桌面或客户端删除已锁定的应用程序，必须解除锁定。</span><span class="sxs-lookup"><span data-stu-id="e31af-521">To remove a locked application from the App-V Desktop or Client for Remote Desktop Services (formerly Terminal Services) cache, you must unlock it.</span></span>

<span data-ttu-id="e31af-522">raid-1</span><span class="sxs-lookup"><span data-stu-id="e31af-522">1</span></span>

<span data-ttu-id="e31af-523">允许用户锁定和解除锁定应用程序。</span><span class="sxs-lookup"><span data-stu-id="e31af-523">Allows a user to lock and unlock an application.</span></span> <span data-ttu-id="e31af-524">这是 Windows 桌面版的默认设置。</span><span class="sxs-lookup"><span data-stu-id="e31af-524">This is the default for Windows Desktops.</span></span> 

<span data-ttu-id="e31af-525">ManageTypes</span><span class="sxs-lookup"><span data-stu-id="e31af-525">ManageTypes</span></span> 

<span data-ttu-id="e31af-526">DWORD</span><span class="sxs-lookup"><span data-stu-id="e31af-526">DWORD</span></span> 

<span data-ttu-id="e31af-527">0</span><span class="sxs-lookup"><span data-stu-id="e31af-527">0</span></span>

<span data-ttu-id="e31af-528">不允许用户单独为该用户添加、编辑或删除文件类型关联。</span><span class="sxs-lookup"><span data-stu-id="e31af-528">Does not allow a user to add, edit, or remove file type associations for that User alone.</span></span> <span data-ttu-id="e31af-529">这是 RD 会话主机的默认值。</span><span class="sxs-lookup"><span data-stu-id="e31af-529">This is the default for RD Session Hosts.</span></span> 

<span data-ttu-id="e31af-530">raid-1</span><span class="sxs-lookup"><span data-stu-id="e31af-530">1</span></span>

<span data-ttu-id="e31af-531">允许用户仅为该用户添加、编辑和删除文件类型关联，而不是全局。</span><span class="sxs-lookup"><span data-stu-id="e31af-531">Allows a user to add, edit, and remove file type associations for that user only and not globally.</span></span> <span data-ttu-id="e31af-532">这是 Windows 桌面版的默认设置。</span><span class="sxs-lookup"><span data-stu-id="e31af-532">This is the default for Windows Desktops.</span></span> 

<span data-ttu-id="e31af-533">RefreshServer</span><span class="sxs-lookup"><span data-stu-id="e31af-533">RefreshServer</span></span> 

<span data-ttu-id="e31af-534">DWORD</span><span class="sxs-lookup"><span data-stu-id="e31af-534">DWORD</span></span> 

<span data-ttu-id="e31af-535">0</span><span class="sxs-lookup"><span data-stu-id="e31af-535">0</span></span>

<span data-ttu-id="e31af-536">不允许用户触发 MIME 设置的刷新。</span><span class="sxs-lookup"><span data-stu-id="e31af-536">Does not allow a user to trigger a refresh of MIME settings.</span></span> <span data-ttu-id="e31af-537">这是 RD 会话主机的默认值。</span><span class="sxs-lookup"><span data-stu-id="e31af-537">This is the default for RD Session Hosts.</span></span> 

<span data-ttu-id="e31af-538">raid-1</span><span class="sxs-lookup"><span data-stu-id="e31af-538">1</span></span>

<span data-ttu-id="e31af-539">允许用户触发 MIME 设置的刷新。</span><span class="sxs-lookup"><span data-stu-id="e31af-539">Enables a user to trigger a refresh of MIME settings.</span></span> <span data-ttu-id="e31af-540">这是 Windows 桌面版的默认设置。</span><span class="sxs-lookup"><span data-stu-id="e31af-540">This is the default for Windows Desktops.</span></span> 

<span data-ttu-id="e31af-541">UpdateOSDFile</span><span class="sxs-lookup"><span data-stu-id="e31af-541">UpdateOSDFile</span></span>

<span data-ttu-id="e31af-542">DWORD</span><span class="sxs-lookup"><span data-stu-id="e31af-542">DWORD</span></span>

<span data-ttu-id="e31af-543">默认值 = 0</span><span class="sxs-lookup"><span data-stu-id="e31af-543">Default= 0</span></span>

<span data-ttu-id="e31af-544">如果值为1，则用户可以使用已修改的 OSD 文件。</span><span class="sxs-lookup"><span data-stu-id="e31af-544">A value of 1 enables a user to use a modified OSD file.</span></span>

<span data-ttu-id="e31af-545">ImportApp</span><span class="sxs-lookup"><span data-stu-id="e31af-545">ImportApp</span></span> 

<span data-ttu-id="e31af-546">DWORD</span><span class="sxs-lookup"><span data-stu-id="e31af-546">DWORD</span></span> 

<span data-ttu-id="e31af-547">0</span><span class="sxs-lookup"><span data-stu-id="e31af-547">0</span></span>

<span data-ttu-id="e31af-548">不允许用户将应用程序导入到缓存中。</span><span class="sxs-lookup"><span data-stu-id="e31af-548">Does not allow a user to import applications into cache.</span></span> <span data-ttu-id="e31af-549">负载和导入之间的区别在于，当触发加载时，客户端从在 OSD、ASR 或替代 URL 中包含的当前配置位置获取程序包。</span><span class="sxs-lookup"><span data-stu-id="e31af-549">The difference between Load and Import is that when a Load is triggered, the client gets the package from the currently configured location contained in the OSD, ASR, or Override URL.</span></span> <span data-ttu-id="e31af-550">使用导入时，必须指定从中获取程序包的位置。</span><span class="sxs-lookup"><span data-stu-id="e31af-550">When using Import, a location to get the package from must be specified.</span></span> 

<span data-ttu-id="e31af-551">raid-1</span><span class="sxs-lookup"><span data-stu-id="e31af-551">1</span></span>

<span data-ttu-id="e31af-552">允许用户将应用程序导入到缓存中。</span><span class="sxs-lookup"><span data-stu-id="e31af-552">Allows a user to import applications into cache.</span></span> 

<span data-ttu-id="e31af-553">ChangeRefreshSettings</span><span class="sxs-lookup"><span data-stu-id="e31af-553">ChangeRefreshSettings</span></span>

<span data-ttu-id="e31af-554">DWORD</span><span class="sxs-lookup"><span data-stu-id="e31af-554">DWORD</span></span>

<span data-ttu-id="e31af-555">默认值 = 0</span><span class="sxs-lookup"><span data-stu-id="e31af-555">Default=0</span></span>

<span data-ttu-id="e31af-556">值1允许用户修改服务器的刷新设置（登录时刷新和定期刷新）。</span><span class="sxs-lookup"><span data-stu-id="e31af-556">A value of 1 allows users to modify the refresh settings for servers (refresh on login and periodic refresh).</span></span> <span data-ttu-id="e31af-557">这并不意味着用户可以修改其他服务器设置（路径、主机等）。</span><span class="sxs-lookup"><span data-stu-id="e31af-557">This does not imply that the user can modify other server settings (path, host, and so on).</span></span>

<span data-ttu-id="e31af-558">ManageServers</span><span class="sxs-lookup"><span data-stu-id="e31af-558">ManageServers</span></span>

<span data-ttu-id="e31af-559">DWORD</span><span class="sxs-lookup"><span data-stu-id="e31af-559">DWORD</span></span>

<span data-ttu-id="e31af-560">默认值 = 0</span><span class="sxs-lookup"><span data-stu-id="e31af-560">Default=0</span></span>

<span data-ttu-id="e31af-561">如果值为1，则允许用户添加、编辑和删除服务器，除了编辑刷新设置（由 ChangeRefreshSettings 权限控制）之外。</span><span class="sxs-lookup"><span data-stu-id="e31af-561">A value of 1 allows the user to add, edit, and remove servers, except for editing the refresh settings, which is controlled by the ChangeRefreshSettings permission.</span></span>

<span data-ttu-id="e31af-562">PublishShortcut</span><span class="sxs-lookup"><span data-stu-id="e31af-562">PublishShortcut</span></span>

<span data-ttu-id="e31af-563">DWORD</span><span class="sxs-lookup"><span data-stu-id="e31af-563">DWORD</span></span>

<span data-ttu-id="e31af-564">默认值 = 0</span><span class="sxs-lookup"><span data-stu-id="e31af-564">Default=0</span></span>

<span data-ttu-id="e31af-565">值1允许用户通过用户界面发布快捷方式。</span><span class="sxs-lookup"><span data-stu-id="e31af-565">A value of 1 allows users to publish shortcuts through the user interface.</span></span> <span data-ttu-id="e31af-566">这不会影响在发布刷新期间发布的快捷方式。</span><span class="sxs-lookup"><span data-stu-id="e31af-566">This does not affect shortcuts that are published during a publishing refresh.</span></span>

<span data-ttu-id="e31af-567">ViewAllApplications</span><span class="sxs-lookup"><span data-stu-id="e31af-567">ViewAllApplications</span></span>

<span data-ttu-id="e31af-568">DWORD</span><span class="sxs-lookup"><span data-stu-id="e31af-568">DWORD</span></span>

<span data-ttu-id="e31af-569">默认值 = 0</span><span class="sxs-lookup"><span data-stu-id="e31af-569">Default=0</span></span>

<span data-ttu-id="e31af-570">值1通过用户界面显示所有应用程序;否则，仅显示用户的应用程序。</span><span class="sxs-lookup"><span data-stu-id="e31af-570">A value of 1 displays all applications through the user interface; otherwise, only the user’s applications are displayed.</span></span>

<span data-ttu-id="e31af-571">RepairApp</span><span class="sxs-lookup"><span data-stu-id="e31af-571">RepairApp</span></span>

<span data-ttu-id="e31af-572">DWORD</span><span class="sxs-lookup"><span data-stu-id="e31af-572">DWORD</span></span>

<span data-ttu-id="e31af-573">默认值 = 1</span><span class="sxs-lookup"><span data-stu-id="e31af-573">Default=1</span></span>

<span data-ttu-id="e31af-574">值1允许用户在 SFTMime 或客户端管理控制台中的应用程序上使用修复操作。</span><span class="sxs-lookup"><span data-stu-id="e31af-574">A value of 1 allows the user to use the Repair action on applications in SFTMime or the Client Management Console.</span></span> <span data-ttu-id="e31af-575">修复应用程序时，删除任何自定义用户设置并还原默认设置。</span><span class="sxs-lookup"><span data-stu-id="e31af-575">When you repair an application, you remove any custom user settings and restore the default settings.</span></span> <span data-ttu-id="e31af-576">此操作不会更改或删除快捷方式或文件类型关联，也不会从缓存中删除应用程序。</span><span class="sxs-lookup"><span data-stu-id="e31af-576">This action does not change or delete shortcuts or file type associations, and it does not remove the application from cache.</span></span>

<span data-ttu-id="e31af-577">ClearApp</span><span class="sxs-lookup"><span data-stu-id="e31af-577">ClearApp</span></span>

<span data-ttu-id="e31af-578">DWORD</span><span class="sxs-lookup"><span data-stu-id="e31af-578">DWORD</span></span>

<span data-ttu-id="e31af-579">默认值 = 1</span><span class="sxs-lookup"><span data-stu-id="e31af-579">Default=1</span></span>

<span data-ttu-id="e31af-580">值1允许用户对 SFTMime 或客户端管理控制台中的应用程序使用清除操作。</span><span class="sxs-lookup"><span data-stu-id="e31af-580">A value of 1 allows the user to use the Clear action on applications in SFTMime or the Client Management Console.</span></span> <span data-ttu-id="e31af-581">从控制台中清除应用程序后，您将无法再使用该应用程序。</span><span class="sxs-lookup"><span data-stu-id="e31af-581">When you clear an application from the console, you can no longer use that application.</span></span> <span data-ttu-id="e31af-582">但是，应用程序仍保留在缓存中，并且在同一系统上仍可供其他用户使用。</span><span class="sxs-lookup"><span data-stu-id="e31af-582">However, the application remains in cache and is still available to other users on the same system.</span></span> <span data-ttu-id="e31af-583">在发布刷新后，已清除的应用程序将再次变为可用。</span><span class="sxs-lookup"><span data-stu-id="e31af-583">After a publishing refresh, the cleared applications will again become available to you.</span></span>

<span data-ttu-id="e31af-584">DeleteApp</span><span class="sxs-lookup"><span data-stu-id="e31af-584">DeleteApp</span></span>

<span data-ttu-id="e31af-585">DWORD</span><span class="sxs-lookup"><span data-stu-id="e31af-585">DWORD</span></span>

<span data-ttu-id="e31af-586">默认值 = 0</span><span class="sxs-lookup"><span data-stu-id="e31af-586">Default=0</span></span>

<span data-ttu-id="e31af-587">值1允许用户对 SFTMime 或客户端管理控制台中的应用程序使用删除操作。</span><span class="sxs-lookup"><span data-stu-id="e31af-587">A value of 1 allows the user to use the Delete action on applications in SFTMime or the Client Management Console.</span></span> <span data-ttu-id="e31af-588">删除应用程序时，所选应用程序将不再可用于该客户端上的任何用户。</span><span class="sxs-lookup"><span data-stu-id="e31af-588">When you delete an application, the selected application will no longer be available to any users on that client.</span></span> <span data-ttu-id="e31af-589">将删除快捷方式和文件类型关联，并从缓存中删除应用程序。</span><span class="sxs-lookup"><span data-stu-id="e31af-589">Shortcuts and file type associations are deleted and the application is deleted from cache.</span></span> <span data-ttu-id="e31af-590">但是，如果另一个应用程序引用文件系统缓存或所选应用程序的设置数据中的数据，这些项目将不会被删除。</span><span class="sxs-lookup"><span data-stu-id="e31af-590">However, if another application refers to data in the file system cache or settings data for the selected application, these items will not be deleted.</span></span>

<span data-ttu-id="e31af-591">在发布刷新后，已删除的应用程序将再次可供你使用。</span><span class="sxs-lookup"><span data-stu-id="e31af-591">After a publishing refresh, the deleted applications will again become available to you.</span></span>

<span data-ttu-id="e31af-592">ToggleOfflineMode</span><span class="sxs-lookup"><span data-stu-id="e31af-592">ToggleOfflineMode</span></span>

<span data-ttu-id="e31af-593">DWORD</span><span class="sxs-lookup"><span data-stu-id="e31af-593">DWORD</span></span>

<span data-ttu-id="e31af-594">值1允许用户选择以脱机模式运行客户端。</span><span class="sxs-lookup"><span data-stu-id="e31af-594">A value of 1 allows the users to select to run the client in Offline Mode.</span></span> <span data-ttu-id="e31af-595">在脱机模式下，应用程序虚拟化客户端可以启动加载的应用程序，即使该应用程序未连接到应用程序虚拟化服务器。</span><span class="sxs-lookup"><span data-stu-id="e31af-595">In Offline Mode, the Application Virtualization client can start a loaded application even when it is not connected to an Application Virtualization Server.</span></span>



## <span data-ttu-id="e31af-596">自定义设置</span><span class="sxs-lookup"><span data-stu-id="e31af-596">Custom Settings</span></span>


<span data-ttu-id="e31af-597">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\CustomSettings 键包含特定于前端组件的值。</span><span class="sxs-lookup"><span data-stu-id="e31af-597">The HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\CustomSettings key contains values specific to front-end components.</span></span> <span data-ttu-id="e31af-598">所有自定义设置均存储为字符串。</span><span class="sxs-lookup"><span data-stu-id="e31af-598">All custom settings are stored as strings.</span></span> <span data-ttu-id="e31af-599">下表提供了与 CustomSettings 键相关联的注册表值的相关信息。</span><span class="sxs-lookup"><span data-stu-id="e31af-599">The following table provides information about the registry values associated with the CustomSettings key.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e31af-600">名称</span><span class="sxs-lookup"><span data-stu-id="e31af-600">Name</span></span> </th>
<th align="left"><span data-ttu-id="e31af-601">类型</span><span class="sxs-lookup"><span data-stu-id="e31af-601">Type</span></span> </th>
<th align="left"><span data-ttu-id="e31af-602">数据（示例）</span><span class="sxs-lookup"><span data-stu-id="e31af-602">Data (Examples)</span></span> </th>
<th align="left"><span data-ttu-id="e31af-603">描述</span><span class="sxs-lookup"><span data-stu-id="e31af-603">Description</span></span> </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e31af-604">TrayErrorDelay</span><span class="sxs-lookup"><span data-stu-id="e31af-604">TrayErrorDelay</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-605">DWORD</span><span class="sxs-lookup"><span data-stu-id="e31af-605">DWORD</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-606">默认值 = 30</span><span class="sxs-lookup"><span data-stu-id="e31af-606">Default=30</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-607">应用程序虚拟化通知区域将显示错误消息（如启动失败）的时间（以秒为单位） &quot; &quot; 。</span><span class="sxs-lookup"><span data-stu-id="e31af-607">Time in seconds that the Application Virtualization notification area will display error messages like &quot;Launch failed&quot;.</span></span> <span data-ttu-id="e31af-608">1的最小值。</span><span class="sxs-lookup"><span data-stu-id="e31af-608">Minimum value of 1.</span></span> </p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e31af-609">TraySuccessDelay</span><span class="sxs-lookup"><span data-stu-id="e31af-609">TraySuccessDelay</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-610">DWORD</span><span class="sxs-lookup"><span data-stu-id="e31af-610">DWORD</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-611">默认值 = 10</span><span class="sxs-lookup"><span data-stu-id="e31af-611">Default=10</span></span> </p></td>
<td align="left"><p><span data-ttu-id="e31af-612">Appvmed 通知区域将显示成功消息（如 &quot; Word 已启动 &quot; 或 &quot; Excel 关闭）的时间（以秒为单位） &quot; 。</span><span class="sxs-lookup"><span data-stu-id="e31af-612">Time in seconds that the appvmed notification area will display success messages like &quot;Word launched&quot; or &quot;Excel shut down&quot;.</span></span> <span data-ttu-id="e31af-613">如果为0，将禁止显示这些消息。</span><span class="sxs-lookup"><span data-stu-id="e31af-613">If 0, those messages will be suppressed.</span></span> </p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e31af-614">TrayVisibility</span><span class="sxs-lookup"><span data-stu-id="e31af-614">TrayVisibility</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-615">DWORD</span><span class="sxs-lookup"><span data-stu-id="e31af-615">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-616">默认值 = 0</span><span class="sxs-lookup"><span data-stu-id="e31af-616">Default=0</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-617">0 = 在使用虚拟化应用程序时显示托盘。</span><span class="sxs-lookup"><span data-stu-id="e31af-617">0=Show Tray when virtualized applications are in use.</span></span></p>
<p><span data-ttu-id="e31af-618">1 = 始终显示托盘。</span><span class="sxs-lookup"><span data-stu-id="e31af-618">1=Show Tray always.</span></span></p>
<p><span data-ttu-id="e31af-619">2 = 从不显示托盘。</span><span class="sxs-lookup"><span data-stu-id="e31af-619">2=Never show Tray.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e31af-620">TrayShowRefresh</span><span class="sxs-lookup"><span data-stu-id="e31af-620">TrayShowRefresh</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-621">DWORD</span><span class="sxs-lookup"><span data-stu-id="e31af-621">DWORD</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="e31af-622">当存在并设置为1值时，允许在任务栏菜单上显示菜单项刷新应用程序，并可供用户访问。</span><span class="sxs-lookup"><span data-stu-id="e31af-622">When present and set to a value of 1, allows menu item Refresh Applications to be displayed on the Tray menu and is accessible by the user.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e31af-623">TrayShowLoad</span><span class="sxs-lookup"><span data-stu-id="e31af-623">TrayShowLoad</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-624">DWORD</span><span class="sxs-lookup"><span data-stu-id="e31af-624">DWORD</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="e31af-625">当存在并设置为1值时，允许在任务栏菜单上显示菜单项加载应用程序，并可供用户访问。</span><span class="sxs-lookup"><span data-stu-id="e31af-625">When present and set to a value of 1, allows menu item Load Applications to be displayed on the Tray menu and is accessible by the user.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="e31af-626">报告设置</span><span class="sxs-lookup"><span data-stu-id="e31af-626">Reporting Settings</span></span>


<span data-ttu-id="e31af-627">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Reporting 键包含特定于 App-v 管理服务器的报告值。</span><span class="sxs-lookup"><span data-stu-id="e31af-627">The HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Reporting key contains values specific to reporting to an App-V Management Server.</span></span> <span data-ttu-id="e31af-628">下表提供了与报告密钥相关联的注册表值的相关信息。</span><span class="sxs-lookup"><span data-stu-id="e31af-628">The following table provides information about the registry values associated with the Reporting key.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e31af-629">名称</span><span class="sxs-lookup"><span data-stu-id="e31af-629">Name</span></span> </th>
<th align="left"><span data-ttu-id="e31af-630">类型</span><span class="sxs-lookup"><span data-stu-id="e31af-630">Type</span></span> </th>
<th align="left"><span data-ttu-id="e31af-631">数据（示例）</span><span class="sxs-lookup"><span data-stu-id="e31af-631">Data (Examples)</span></span> </th>
<th align="left"><span data-ttu-id="e31af-632">描述</span><span class="sxs-lookup"><span data-stu-id="e31af-632">Description</span></span> </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e31af-633">DataCacheLimit</span><span class="sxs-lookup"><span data-stu-id="e31af-633">DataCacheLimit</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-634">DWORD</span><span class="sxs-lookup"><span data-stu-id="e31af-634">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-635">默认值 = 20</span><span class="sxs-lookup"><span data-stu-id="e31af-635">Default=20</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-636">此值指定用于存储报告信息的 XML 缓存的最大大小（以兆字节（MB）为单位）。</span><span class="sxs-lookup"><span data-stu-id="e31af-636">This value specifies the maximum size in megabytes (MB) of the XML cache for storing reporting information.</span></span> <span data-ttu-id="e31af-637">大小应用于内存中的缓存。</span><span class="sxs-lookup"><span data-stu-id="e31af-637">The size applies to the cache in memory.</span></span> <span data-ttu-id="e31af-638">达到限制时，日志文件将翻转。</span><span class="sxs-lookup"><span data-stu-id="e31af-638">When the limit is reached, the log file will roll over.</span></span> <span data-ttu-id="e31af-639">添加新记录（列表的底部）时，将删除一个或多个最旧的记录（列表顶部），以腾出空间。</span><span class="sxs-lookup"><span data-stu-id="e31af-639">When a new record is added (bottom of the list), one or more of the oldest records (top of the list) will be deleted to make room.</span></span> <span data-ttu-id="e31af-640">第一次出现时，将向客户端日志和事件日志中记录一条警告，直到缓存成功地清除传输并再次填充日志后，才会再次记录该警告。</span><span class="sxs-lookup"><span data-stu-id="e31af-640">A warning will be logged to the Client log and the event log the first time this occurs, and it will not be logged again until after the cache has been successfully cleared on transmission and the log has filled up again.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e31af-641">DataBlockSize</span><span class="sxs-lookup"><span data-stu-id="e31af-641">DataBlockSize</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-642">DWORD</span><span class="sxs-lookup"><span data-stu-id="e31af-642">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-643">默认值 = 65536</span><span class="sxs-lookup"><span data-stu-id="e31af-643">Default=65536</span></span></p></td>
<td align="left"><p><span data-ttu-id="e31af-644">此值指定在发布刷新时同时传输到服务器的最大大小（以字节为单位），以避免日志达到较大大小时的永久传输失败。</span><span class="sxs-lookup"><span data-stu-id="e31af-644">This value specifies the maximum size in bytes to transmit to the server at once on publishing refresh, to avoid permanent transmission failures when the log has reached a significant size.</span></span> <span data-ttu-id="e31af-645">默认值为65536。</span><span class="sxs-lookup"><span data-stu-id="e31af-645">The default value is 65536.</span></span> <span data-ttu-id="e31af-646">将报表数据传输到服务器时，将从缓存中删除一个应用程序记录块（小于或等于 XML 数据的块大小），并将其发送到服务器。</span><span class="sxs-lookup"><span data-stu-id="e31af-646">When transmitting report data to the server, one block of application records—less than or equal to the block size in bytes of XML data—will be removed from the cache and sent to the server.</span></span> <span data-ttu-id="e31af-647">每个块都将具有常规客户端数据和全局包列表数据，这些数据将不会考虑到块大小计算;极大的程序包列表可能存在通过低带宽或不可靠的连接导致传输失败的可能性。</span><span class="sxs-lookup"><span data-stu-id="e31af-647">Each block will have the general Client data and global package list data prepended, and these will not factor into the block size calculations; the potential exists for an extremely large package list to result in transmission failures over low bandwidth or unreliable connections.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="e31af-648">相关主题</span><span class="sxs-lookup"><span data-stu-id="e31af-648">Related topics</span></span>


[<span data-ttu-id="e31af-649">Application Virtualization Client 参考</span><span class="sxs-lookup"><span data-stu-id="e31af-649">Application Virtualization Client Reference</span></span>](application-virtualization-client-reference.md)









