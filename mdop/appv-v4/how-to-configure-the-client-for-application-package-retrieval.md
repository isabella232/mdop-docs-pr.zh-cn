---
title: 如何配置客户端以进行应用程序包检索
description: 如何配置客户端以进行应用程序包检索
author: dansimp
ms.assetid: 891f2739-da7a-46da-b452-b8c0af075525
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f5eeb0b977c6ecd44947d5d1c42d25d47b9e2530
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801572"
---
# <span data-ttu-id="64e4c-103">如何配置客户端以进行应用程序包检索</span><span class="sxs-lookup"><span data-stu-id="64e4c-103">How to Configure the Client for Application Package Retrieval</span></span>


<span data-ttu-id="64e4c-104">将客户端配置为将应用程序虚拟化（app-v）管理服务器配置为发布服务器时，默认情况下，在下一个发布刷新周期中，客户端从服务器检索用户有权使用的每个程序包的开放软件描述符（OSD）和程序包清单文件。</span><span class="sxs-lookup"><span data-stu-id="64e4c-104">When the client is configured with an Application Virtualization (App-V) Management Server as its publishing server, by default at the next publishing refresh cycle, the client retrieves from the server the Open Software Descriptor (OSD) and package manifest files for each package that the user is authorized to use.</span></span> <span data-ttu-id="64e4c-105">客户端使用在这些文件中定义的程序包源信息来确定要在何处查找程序包内容、图标和文件类型关联。</span><span class="sxs-lookup"><span data-stu-id="64e4c-105">The client uses the package source information that is defined in these files to determine where to find the package content, icons, and file type associations.</span></span>

<span data-ttu-id="64e4c-106">如果你希望客户从本地 App-v 流式处理服务器或其他备用源（如 Web 服务器或文件服务器）获取程序包内容（SFT 文件），可以将计算机上的 ApplicationSourceRoot 注册表项值配置为指向另一台服务器上的本地内容共享。</span><span class="sxs-lookup"><span data-stu-id="64e4c-106">If you want the client to obtain the package content (SFT file) from a local App-V Streaming Server or other alternate source such as a Web server or file server, instead of from the App-V Management Server, you can configure the ApplicationSourceRoot registry key value on the computer to point to the local content share on the other server.</span></span> <span data-ttu-id="64e4c-107">OSD 文件仍定义程序包内容的原始源路径。</span><span class="sxs-lookup"><span data-stu-id="64e4c-107">The OSD file still defines the original source path for the package content.</span></span> <span data-ttu-id="64e4c-108">但是，客户端使用 ApplicationSourceRoot 设置的值代替在 OSD 文件的内容路径中指定的服务器和共享。</span><span class="sxs-lookup"><span data-stu-id="64e4c-108">However the client uses the value of the ApplicationSourceRoot setting in place of the server and share that are specified in the content path in the OSD file.</span></span> <span data-ttu-id="64e4c-109">这将重定向客户端以从另一台服务器检索内容。</span><span class="sxs-lookup"><span data-stu-id="64e4c-109">This redirects the client to retrieve the content from the other server.</span></span>

<span data-ttu-id="64e4c-110">如果你想要在程序包清单文件或发布服务器发送的路径中替代这些设置，也可以配置 OSDSourceRoot 和 IconSourceRoot 注册表项值。</span><span class="sxs-lookup"><span data-stu-id="64e4c-110">You can also configure the OSDSourceRoot and IconSourceRoot registry key values if you want to override those settings in the package manifest file or in the paths sent by a publishing server.</span></span> <span data-ttu-id="64e4c-111">OSDSourceRoot 指定发布期间应用程序包的 OSD 文件检索的源位置。</span><span class="sxs-lookup"><span data-stu-id="64e4c-111">The OSDSourceRoot specifies a source location for OSD file retrieval for an application package during publication.</span></span> <span data-ttu-id="64e4c-112">IconSourceRoot 指定发布期间应用程序包的图标检索的源位置。</span><span class="sxs-lookup"><span data-stu-id="64e4c-112">The IconSourceRoot specifies a source location for icon retrieval for an application package during publication.</span></span>

**<span data-ttu-id="64e4c-113">注意</span><span class="sxs-lookup"><span data-stu-id="64e4c-113">Note</span></span>**  
-   <span data-ttu-id="64e4c-114">IconSourceRoot 和 OSDSourceRoot 设置替代程序包清单文件中的值，因此，如果你尝试使用 Windows Installer （.msi）文件方法部署程序包，则它还将替代该 .msi 文件中包含的程序包清单文件中的值。</span><span class="sxs-lookup"><span data-stu-id="64e4c-114">The IconSourceRoot and OSDSourceRoot settings override the values in the package manifest file, so if you try to deploy a package by using the Windows Installer (.msi) file method, it will also override the values in the package manifest file that is contained within that .msi file.</span></span>

-   <span data-ttu-id="64e4c-115">在发布和 HTTP （S）流操作过程中，App-v 4.5 SP1 客户端使用在用户计算机上的 Internet Explorer 中配置的代理服务器设置。</span><span class="sxs-lookup"><span data-stu-id="64e4c-115">During both the publishing and HTTP(S) streaming operations,App-V 4.5 SP1 clients use the proxy server settings that are configured in Internet Explorer on the user’s computer.</span></span>



**<span data-ttu-id="64e4c-116">配置 ApplicationSourceRoot 注册表项值</span><span class="sxs-lookup"><span data-stu-id="64e4c-116">To configure the ApplicationSourceRoot registry key value</span></span>**

-   <span data-ttu-id="64e4c-117">使用 UNC 路径或 URL 配置以下注册表项值中的 ApplicationSourceRoot：</span><span class="sxs-lookup"><span data-stu-id="64e4c-117">Configure the ApplicationSourceRoot in the following registry key value with either a UNC path or a URL:</span></span>

    <span data-ttu-id="64e4c-118">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\\ApplicationSourceRoot</span><span class="sxs-lookup"><span data-stu-id="64e4c-118">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\\ApplicationSourceRoot</span></span>

    <span data-ttu-id="64e4c-119">通用命名约定（UNC）路径的正确格式为**\\\\computername\\sharefolder\\\ [folder \] \ [\\]**，其中**文件夹**是可选的。</span><span class="sxs-lookup"><span data-stu-id="64e4c-119">The correct format for the Universal Naming Convention (UNC) path is **\\\\computername\\sharefolder\\\[folder\]\[\\\]**, where **folder** is optional.</span></span> <span data-ttu-id="64e4c-120">**Computername**可以是完全限定的域名（FQDN）或 IP 地址， **sharefolder**可以是驱动器号。</span><span class="sxs-lookup"><span data-stu-id="64e4c-120">The **computername** can be a Fully Qualified Domain Name (FQDN) or an IP address, and **sharefolder** can be a drive letter.</span></span> <span data-ttu-id="64e4c-121">仅替换 OSD 路径的**\\\\computername\\sharedfolder**或驱动器号部分。</span><span class="sxs-lookup"><span data-stu-id="64e4c-121">Only the **\\\\computername\\sharedfolder** or drive letter portion of the OSD path is replaced.</span></span>

    <span data-ttu-id="64e4c-122">URL 路径的正确格式为**protocol：/path\： \ [port \] \ [] \ [/\]**，其中**port**和**path**是可选的。</span><span class="sxs-lookup"><span data-stu-id="64e4c-122">The correct format for the URL path is **protocol://servername:\[port\]\[/path\]\[/\]**, where **port** and **path** are optional.</span></span> <span data-ttu-id="64e4c-123">如果未指定**port** ，则使用协议的默认端口。</span><span class="sxs-lookup"><span data-stu-id="64e4c-123">If **port** is not specified, the default port for the protocol is used.</span></span> <span data-ttu-id="64e4c-124">仅替换了 OSD URL 的**协议：//server：端口**部分。</span><span class="sxs-lookup"><span data-stu-id="64e4c-124">Only the **protocol://server:port** portion of the OSD URL is replaced.</span></span>

    **<span data-ttu-id="64e4c-125">重要提示</span><span class="sxs-lookup"><span data-stu-id="64e4c-125">Important</span></span>**  
    <span data-ttu-id="64e4c-126">ApplicationSourceRoot 定义中不支持环境变量。</span><span class="sxs-lookup"><span data-stu-id="64e4c-126">Environment variables are not supported in the ApplicationSourceRoot definition.</span></span>



~~~
The following table lists examples of acceptable URL and UNC path formats.

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">ApplicationSourceRoot</th>
<th align="left">OSD File HREF Path</th>
<th align="left">Result</th>
<th align="left">Comments</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>rtsps://mainserver:322</p></td>
<td align="left"><p>rtsp://appserver/productivity/office2k3.sft?customer=seq</p></td>
<td align="left"><p>rtsps://mainserver:322/productivity/office2k3.sft?customer=seq</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>rtsps://mainserver:322/prodapps</p></td>
<td align="left"><p>rtsp://appserver/productivity/office2k3.sft?customer=seq</p></td>
<td align="left"><p>rtsps://mainserver:322/prodapps/productivity/office2k3.sft?customer=seq</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>https://mainserver:443/prodapps</p></td>
<td align="left"><p>rtsp://appserver/productivity/office2k3.sft?customer=seq</p></td>
<td align="left"><p>https://mainserver:443/prodapps/productivity/office2k3.sft?customer=seq</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>rtsps://mainserver:322/prodapps</p></td>
<td align="left"><p>rtsp://%SFT_APPVSERVER%:554/productivity/office2k3.sft?customer=seq</p></td>
<td align="left"><p>rtsps://mainserver:322/prodapps/productivity/office2k3.sft?customer=seq</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>rtsps://mainserver:322</p></td>
<td align="left"><p>\\uncserver\share\productivity\office2k3.sft</p></td>
<td align="left"><p>rtsps://mainserver:322/productivity/office2k3.sft</p></td>
<td align="left"><p>‘\’ converted to ‘/’</p></td>
</tr>
<tr class="even">
<td align="left"><p>rtsps://mainserver:322</p></td>
<td align="left"><p>file://\\uncserver\share\productivity\office2k3.sft</p></td>
<td align="left"><p>rtsps://mainserver:322/productivity/office2k3.sft</p></td>
<td align="left"><p>‘\’ converted to ‘/’</p></td>
</tr>
<tr class="odd">
<td align="left"><p>\\uncserver\share</p></td>
<td align="left"><p>rtsp://appserver/productivity/office2k3.sft?customer=seq</p></td>
<td align="left"><p>\\uncserver\share\productivity\office2k3.sft</p></td>
<td align="left"><p>‘/’ converted to ‘\’ and parameter dropped when converting to UNC path</p></td>
</tr>
<tr class="even">
<td align="left"><p>\\uncserver\share\prodapps</p></td>
<td align="left"><p>rtsp://appserver/productivity/office2k3.sft?customer=seq</p></td>
<td align="left"><p>\\uncserver\share\prodapps\productivity\office2k3.sft</p></td>
<td align="left"><p>‘/’ converted to ‘\’ and parameter dropped when converting to UNC path</p></td>
</tr>
<tr class="odd">
<td align="left"><p>M:</p></td>
<td align="left"><p>\\uncserver\share\productivity\office2k3.sft</p></td>
<td align="left"><p>M:\productivity\office2k3.sft</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>M:\prodapps</p></td>
<td align="left"><p>\\uncserver\share\productivity\office2k3.sft</p></td>
<td align="left"><p>M:\prodapps\productivity\office2k3.sft</p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>
~~~



**<span data-ttu-id="64e4c-127">配置 OSDSourceRoot 值</span><span class="sxs-lookup"><span data-stu-id="64e4c-127">To configure the OSDSourceRoot value</span></span>**

-   <span data-ttu-id="64e4c-128">使用 UNC 路径或 URL 配置以下注册表项值中的 OSDSourceRoot：</span><span class="sxs-lookup"><span data-stu-id="64e4c-128">Configure the OSDSourceRoot in the following registry key value with either a UNC path or a URL:</span></span>

    <span data-ttu-id="64e4c-129">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\\OSDSourceRoot</span><span class="sxs-lookup"><span data-stu-id="64e4c-129">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\\OSDSourceRoot</span></span>

    <span data-ttu-id="64e4c-130">OSDSourceRoot 的可接受格式包括 UNC 路径和 Url，如以下示例中所示：</span><span class="sxs-lookup"><span data-stu-id="64e4c-130">Acceptable formats for the OSDSourceRoot include UNC paths and URLs, as in the following example:</span></span>

    <span data-ttu-id="64e4c-131">**\\\\computername\\sharefolder\\resource**或**\\\\computername\\content**或\*\* &lt; drive &gt; ： \\foldername\*\*</span><span class="sxs-lookup"><span data-stu-id="64e4c-131">**\\\\computername\\sharefolder\\resource** or **\\\\computername\\content** or **&lt;drive&gt;:\\foldername**</span></span>

    <span data-ttu-id="64e4c-132">**http://computername/productivity/** 或**https://computername/productivity/**</span><span class="sxs-lookup"><span data-stu-id="64e4c-132">**http://computername/productivity/** or **https://computername/productivity/**</span></span>

**<span data-ttu-id="64e4c-133">配置 IconSourceRoot 值</span><span class="sxs-lookup"><span data-stu-id="64e4c-133">To configure the IconSourceRoot value</span></span>**

-   <span data-ttu-id="64e4c-134">使用 UNC 路径或 URL 配置以下注册表项值中的 IconSourceRoot：</span><span class="sxs-lookup"><span data-stu-id="64e4c-134">Configure the IconSourceRoot in the following registry key value with either a UNC path or a URL:</span></span>

    <span data-ttu-id="64e4c-135">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\\IconSourceRoot</span><span class="sxs-lookup"><span data-stu-id="64e4c-135">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\\IconSourceRoot</span></span>

    <span data-ttu-id="64e4c-136">IconSourceRoot 的可接受格式包括 UNC 路径和 Url，如以下示例中所示：</span><span class="sxs-lookup"><span data-stu-id="64e4c-136">Acceptable formats for the IconSourceRoot include UNC paths and URLs, as in the following example:</span></span>

    <span data-ttu-id="64e4c-137">**\\\\computername\\sharefolder\\resource**或**\\\\computername\\content**或\*\* &lt; drive &gt; ： \\foldername\*\*</span><span class="sxs-lookup"><span data-stu-id="64e4c-137">**\\\\computername\\sharefolder\\resource** or **\\\\computername\\content** or **&lt;drive&gt;:\\foldername**</span></span>

    <span data-ttu-id="64e4c-138">**http://computername/productivity/** 或**https://computername/productivity/**</span><span class="sxs-lookup"><span data-stu-id="64e4c-138">**http://computername/productivity/** or **https://computername/productivity/**</span></span>

## <span data-ttu-id="64e4c-139">相关主题</span><span class="sxs-lookup"><span data-stu-id="64e4c-139">Related topics</span></span>


[<span data-ttu-id="64e4c-140">如何使用命令行配置 App-V Client 注册表设置</span><span class="sxs-lookup"><span data-stu-id="64e4c-140">How to Configure the App-V Client Registry Settings by Using the Command Line</span></span>](how-to-configure-the-app-v-client-registry-settings-by-using-the-command-line.md)









