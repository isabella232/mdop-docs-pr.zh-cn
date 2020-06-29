---
title: ADD SERVER
description: ADD SERVER
author: dansimp
ms.assetid: 4be2ac2e-a410-4711-9f84-f305393c8fa7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e15a5943b40e14b2f9031bf8b3ddffa693e32dea
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802396"
---
# <span data-ttu-id="fca6e-103">ADD SERVER</span><span class="sxs-lookup"><span data-stu-id="fca6e-103">ADD SERVER</span></span>


<span data-ttu-id="fca6e-104">添加发布服务器。</span><span class="sxs-lookup"><span data-stu-id="fca6e-104">Adds a publishing server.</span></span>

`SFTMIME ADD SERVER:server-name /HOST hostname /TYPE {HTTP|RTSP}                 /PATH path [/PORT port] [/REFRESH {ON|OFF}] [/SECURE]                 [/LOG log-pathname | /CONSOLE | /GUI]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="fca6e-105">参数</span><span class="sxs-lookup"><span data-stu-id="fca6e-105">Parameter</span></span></th>
<th align="left"><span data-ttu-id="fca6e-106">描述</span><span class="sxs-lookup"><span data-stu-id="fca6e-106">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="fca6e-107">服务器： &lt; 服务器名称&gt;</span><span class="sxs-lookup"><span data-stu-id="fca6e-107">SERVER:&lt;server-name&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="fca6e-108">发布服务器的显示名称。</span><span class="sxs-lookup"><span data-stu-id="fca6e-108">The display name for the publishing server.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="fca6e-109">/HOST &lt; 主机名&gt;</span><span class="sxs-lookup"><span data-stu-id="fca6e-109">/HOST &lt;hostname&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="fca6e-110">发布服务器的主机名或 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="fca6e-110">The host name or IP address for the publishing server.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="fca6e-111">/TYPE {HTTP |RTSP</span><span class="sxs-lookup"><span data-stu-id="fca6e-111">/TYPE {HTTP|RTSP}</span></span></p></td>
<td align="left"><p><span data-ttu-id="fca6e-112">指示发布服务器是 Web 服务器（ &quot; HTTP &quot; ）还是应用程序虚拟化服务器（ &quot; RTSP &quot; ）。</span><span class="sxs-lookup"><span data-stu-id="fca6e-112">Indicates whether the publishing server is a Web server (&quot;HTTP&quot;) or an Application Virtualization Server (&quot;RTSP&quot;).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="fca6e-113">/PORT &lt; 端口&gt;</span><span class="sxs-lookup"><span data-stu-id="fca6e-113">/PORT &lt;port&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="fca6e-114">发布服务器侦听的端口。</span><span class="sxs-lookup"><span data-stu-id="fca6e-114">The port on which the publishing server listens.</span></span> <span data-ttu-id="fca6e-115">对于使用增强安全性的 HTTP 服务器443，对于使用554增强安全性的 HTTP 服务器，80的默认值为; 对于使用增强安全性的服务器，则默认为322。</span><span class="sxs-lookup"><span data-stu-id="fca6e-115">Defaults to 80 for normal HTTP servers, 443 for HTTP servers using enhanced security, 554 for normal Application Virtualization Servers, and 322 for servers using enhanced security.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="fca6e-116">/PATH &lt; 路径&gt;</span><span class="sxs-lookup"><span data-stu-id="fca6e-116">/PATH &lt;path&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="fca6e-117">发布请求中使用的 URL 的路径部分。</span><span class="sxs-lookup"><span data-stu-id="fca6e-117">The path portion of the URL used in a publishing request.</span></span> <span data-ttu-id="fca6e-118">如果 TYPE 参数设置为 RTSP，则路径是可选的，并且默认为 &quot; / &quot; 。</span><span class="sxs-lookup"><span data-stu-id="fca6e-118">If the TYPE parameter is set to RTSP, the path is optional and defaults to &quot;/&quot;.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="fca6e-119">/REFRESH</span><span class="sxs-lookup"><span data-stu-id="fca6e-119">/REFRESH</span></span></p></td>
<td align="left"><p><span data-ttu-id="fca6e-120">如果设置为 "开"，则在用户登录时将刷新发布信息。</span><span class="sxs-lookup"><span data-stu-id="fca6e-120">If set to ON, publishing information will be refreshed when the user logs in.</span></span> <span data-ttu-id="fca6e-121">默认值为 "开"。</span><span class="sxs-lookup"><span data-stu-id="fca6e-121">Defaults to ON.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="fca6e-122">/SECURE</span><span class="sxs-lookup"><span data-stu-id="fca6e-122">/SECURE</span></span></p></td>
<td align="left"><p><span data-ttu-id="fca6e-123">如果存在，则表示应建立与发布服务器的增强安全性的连接。</span><span class="sxs-lookup"><span data-stu-id="fca6e-123">If present, indicates that a connection with enhanced security should be established to the publishing server.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="fca6e-124">/LOG</span><span class="sxs-lookup"><span data-stu-id="fca6e-124">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="fca6e-125">如果指定，输出将记录到指定的路径名称。</span><span class="sxs-lookup"><span data-stu-id="fca6e-125">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="fca6e-126">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="fca6e-126">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="fca6e-127">如果指定，将在活动控制台窗口中显示输出（默认）。</span><span class="sxs-lookup"><span data-stu-id="fca6e-127">If specified, output is presented in the active console window (default).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="fca6e-128">/GUI</span><span class="sxs-lookup"><span data-stu-id="fca6e-128">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="fca6e-129">如果指定，将在 Windows 对话框中显示输出。</span><span class="sxs-lookup"><span data-stu-id="fca6e-129">If specified, output is presented in a Windows dialog box.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="fca6e-130">对于版本4.6，已添加以下选项。</span><span class="sxs-lookup"><span data-stu-id="fca6e-130">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="fca6e-131">/LOGU</span><span class="sxs-lookup"><span data-stu-id="fca6e-131">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="fca6e-132">如果指定，将以 UNICODE 格式将输出记录到指定的路径名称。</span><span class="sxs-lookup"><span data-stu-id="fca6e-132">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="fca6e-133">相关主题</span><span class="sxs-lookup"><span data-stu-id="fca6e-133">Related topics</span></span>


[<span data-ttu-id="fca6e-134">SFTMIME 命令引用</span><span class="sxs-lookup"><span data-stu-id="fca6e-134">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





