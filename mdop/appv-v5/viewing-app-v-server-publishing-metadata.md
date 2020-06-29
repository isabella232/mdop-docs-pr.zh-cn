---
title: 查看 App-V 服务器发布元数据
description: 查看 App-V 服务器发布元数据
author: dansimp
ms.assetid: 048dd42a-24d4-4cc4-81f6-7a919aadd9b2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 304aa656de98a0c9d59f0a6166811ead911033ad
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798252"
---
# <span data-ttu-id="1cde4-103">查看 App-V 服务器发布元数据</span><span class="sxs-lookup"><span data-stu-id="1cde4-103">Viewing App-V Server Publishing Metadata</span></span>


<span data-ttu-id="1cde4-104">使用此过程可查看发布元数据，这有助于解决与发布相关的问题。</span><span class="sxs-lookup"><span data-stu-id="1cde4-104">Use this procedure to view publishing metadata, which can help you resolve publishing-related issues.</span></span> <span data-ttu-id="1cde4-105">必须使用 App-v 管理服务器才能使用此过程。</span><span class="sxs-lookup"><span data-stu-id="1cde4-105">You must be using the App-V Management server to use this procedure.</span></span>

<span data-ttu-id="1cde4-106">本文包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="1cde4-106">This article contains the following information:</span></span>

-   [<span data-ttu-id="1cde4-107">用于查看发布元数据的 app-v 5.0 SP3 要求</span><span class="sxs-lookup"><span data-stu-id="1cde4-107">App-V 5.0 SP3 requirements for viewing publishing metadata</span></span>](#bkmk-50sp3-reqs-pub-meta)

-   [<span data-ttu-id="1cde4-108">用于查看发布元数据的语法</span><span class="sxs-lookup"><span data-stu-id="1cde4-108">Syntax to use for viewing publishing metadata</span></span>](#bkmk-syntax-view-pub-meta)

-   [<span data-ttu-id="1cde4-109">客户端操作系统和版本的查询值</span><span class="sxs-lookup"><span data-stu-id="1cde4-109">Query values for client operating system and version</span></span>](#bkmk-values-query-pub-meta)

-   [<span data-ttu-id="1cde4-110">发布元数据的定义</span><span class="sxs-lookup"><span data-stu-id="1cde4-110">Definition of publishing metadata</span></span>](#bkmk-whatis-pub-metadata)

## <a href="" id="bkmk-50sp3-reqs-pub-meta"></a><span data-ttu-id="1cde4-111">用于查看发布元数据的 app-v 5.0 SP3 要求</span><span class="sxs-lookup"><span data-stu-id="1cde4-111">App-V 5.0 SP3 requirements for viewing publishing metadata</span></span>


<span data-ttu-id="1cde4-112">在 App-v 5.0 SP3 中，当你查询用于元数据的 app-v 发布服务器时，必须在地址中提供以下值：</span><span class="sxs-lookup"><span data-stu-id="1cde4-112">In App-V 5.0 SP3, you must provide the following values in the address when you query the App-V Publishing server for metadata:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="1cde4-113">值</span><span class="sxs-lookup"><span data-stu-id="1cde4-113">Value</span></span></th>
<th align="left"><span data-ttu-id="1cde4-114">其他详细信息</span><span class="sxs-lookup"><span data-stu-id="1cde4-114">Additional details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="1cde4-115">ClientVersion</span><span class="sxs-lookup"><span data-stu-id="1cde4-115">ClientVersion</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="1cde4-116">如果省略查询中的 <strong> ClientVersion </strong> 参数，则元数据将排除新的 APP-V 5.0 SP3 功能。</span><span class="sxs-lookup"><span data-stu-id="1cde4-116">If you omit the <strong>ClientVersion</strong> parameter from the query, the metadata excludes the new App-V 5.0 SP3 features.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="1cde4-117">ClientOS</span><span class="sxs-lookup"><span data-stu-id="1cde4-117">ClientOS</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="1cde4-118">只有在对程序包进行排序时选择特定客户端操作系统时，才必须提供此值。</span><span class="sxs-lookup"><span data-stu-id="1cde4-118">You have to provide this value only if you select specific client operating systems when you sequence the package.</span></span> <span data-ttu-id="1cde4-119">如果选择 "默认（所有操作系统）"，请不要在查询中指定此值。</span><span class="sxs-lookup"><span data-stu-id="1cde4-119">If you select the default (all operating systems), do not specify this value in the query.</span></span></p>
<p><span data-ttu-id="1cde4-120">如果省略查询中的 <strong> ClientOS </strong> 参数，则只有已排序支持任何操作系统的程序包才会显示在元数据中。</span><span class="sxs-lookup"><span data-stu-id="1cde4-120">If you omit the <strong>ClientOS</strong> parameter from the query, only the packages that were sequenced to support any operating system appear in the metadata.</span></span></p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-syntax-view-pub-meta"></a><span data-ttu-id="1cde4-121">用于查看发布元数据的查询语法</span><span class="sxs-lookup"><span data-stu-id="1cde4-121">Query syntax for viewing publishing metadata</span></span>


<span data-ttu-id="1cde4-122">下表提供了语法和查询示例。</span><span class="sxs-lookup"><span data-stu-id="1cde4-122">The following table provides the syntax and query examples.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="1cde4-123">App-v 版本</span><span class="sxs-lookup"><span data-stu-id="1cde4-123">Version of App-V</span></span></th>
<th align="left"><span data-ttu-id="1cde4-124">查询语法</span><span class="sxs-lookup"><span data-stu-id="1cde4-124">Query syntax</span></span></th>
<th align="left"><span data-ttu-id="1cde4-125">参数说明</span><span class="sxs-lookup"><span data-stu-id="1cde4-125">Parameter descriptions</span></span></th>
<th align="left"><span data-ttu-id="1cde4-126">示例</span><span class="sxs-lookup"><span data-stu-id="1cde4-126">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1cde4-127">App-v 5.0 SP3</span><span class="sxs-lookup"><span data-stu-id="1cde4-127">App-V 5.0 SP3</span></span></p></td>
<td align="left"><p><code>http://&lt;PubServer&gt;:&lt;Publishing Port#&gt;/?ClientVersion=&lt;AppvClientVersion&gt;&amp;ClientOS=&lt;OSStringValue&gt;</code></p></td>
<td align="left"><table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="1cde4-128">参数</span><span class="sxs-lookup"><span data-stu-id="1cde4-128">Parameter</span></span></th>
<th align="left"><span data-ttu-id="1cde4-129">描述</span><span class="sxs-lookup"><span data-stu-id="1cde4-129">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1cde4-130">&lt;PubServer&gt;</span><span class="sxs-lookup"><span data-stu-id="1cde4-130">&lt;PubServer&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="1cde4-131">App-v 发布服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="1cde4-131">Name of the App-V Publishing server.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="1cde4-132">&lt;发布端口#&gt;</span><span class="sxs-lookup"><span data-stu-id="1cde4-132">&lt;Publishing Port#&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="1cde4-133">指向在配置发布服务器时定义的 app-v 发布服务器的端口。</span><span class="sxs-lookup"><span data-stu-id="1cde4-133">Port to the App-V Publishing server, which you defined when you configured the Publishing server.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1cde4-134">ClientVersion = &lt; AppvClientVersion&gt;</span><span class="sxs-lookup"><span data-stu-id="1cde4-134">ClientVersion=&lt;AppvClientVersion&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="1cde4-135">App-v 客户端的版本。</span><span class="sxs-lookup"><span data-stu-id="1cde4-135">Version of the App-V client.</span></span> <span data-ttu-id="1cde4-136">请参考下表，以获取正确的值以供使用。</span><span class="sxs-lookup"><span data-stu-id="1cde4-136">Refer to the following table for the correct value to use.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="1cde4-137">ClientOS = &lt; OSStringValue&gt;</span><span class="sxs-lookup"><span data-stu-id="1cde4-137">ClientOS=&lt;OSStringValue&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="1cde4-138">运行 App-v 客户端的计算机的操作系统。</span><span class="sxs-lookup"><span data-stu-id="1cde4-138">Operating system of the computer that is running the App-V client.</span></span> <span data-ttu-id="1cde4-139">请参考下表，以获取正确的值以供使用。</span><span class="sxs-lookup"><span data-stu-id="1cde4-139">Refer to the following table for the correct value to use.</span></span></p></td>
</tr>
</tbody>
</table>
<p> </p>
<p><span data-ttu-id="1cde4-140">若要从 App-v 客户端获取发布服务器和端口号（http:// &lt; PubServer &gt; ： &lt; 发布端口 # &gt; ）的名称，请查看 <strong> AppvPublishingServer PowerShell cmdlet 的 URL 配置 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="1cde4-140">To get the name of the Publishing server and the port number (http://&lt;PubServer&gt;:&lt;Publishing Port#&gt;) from the App-V Client, look at the URL configuration of the <strong>Get-AppvPublishingServer</strong> PowerShell cmdlet.</span></span></p></td>
<td align="left"><p><code><a href="http://pubsvr01:2718/?clientversion=5.0.10066.0&amp;clientos=WindowsClient_6.2_x64" data-raw-source="http://pubsvr01:2718/?clientversion=5.0.10066.0&amp;amp;clientos=WindowsClient_6.2_x64">http://pubsvr01:2718/?clientversion=5.0.10066.0&amp;clientos=WindowsClient_6.2_x64</a></code></p>
<p><span data-ttu-id="1cde4-141">在示例中：</span><span class="sxs-lookup"><span data-stu-id="1cde4-141">In the example:</span></span></p>
<ul>
<li><p><span data-ttu-id="1cde4-142">名为 "pubsvr01" 的 Windows Server 2012 R2 托管发布服务。</span><span class="sxs-lookup"><span data-stu-id="1cde4-142">A Windows Server 2012 R2 named “pubsvr01” hosts the Publishing service.</span></span></p></li>
<li><p><span data-ttu-id="1cde4-143">Windows 客户端是 Windows 8.1 64 位。</span><span class="sxs-lookup"><span data-stu-id="1cde4-143">The Windows client is Windows 8.1 64-bit.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="1cde4-144">App-v 5.0 至 App-V 5.0 SP2</span><span class="sxs-lookup"><span data-stu-id="1cde4-144">App-V 5.0 through App-V 5.0 SP2</span></span></p></td>
<td align="left"><p><code>http://&lt;PubServer&gt;:&lt;Publishing Port#&gt;/ </code></p>
<div class="alert">
<strong><span data-ttu-id="1cde4-145">注意</span><span class="sxs-lookup"><span data-stu-id="1cde4-145">Note</span></span></strong><br/><p><strong><span data-ttu-id="1cde4-146">ClientVersion </strong> 和 <strong> ClientOS </strong> 仅在 app-v 5.0 SP3 中受支持。</span><span class="sxs-lookup"><span data-stu-id="1cde4-146">ClientVersion</strong> and <strong>ClientOS</strong> are supported only in App-V 5.0 SP3.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><span data-ttu-id="1cde4-147">请参阅 App-v 5.0 SP3 的信息。</span><span class="sxs-lookup"><span data-stu-id="1cde4-147">See the information for App-V 5.0 SP3.</span></span></p></td>
<td align="left"><p><code><a href="http://pubsvr01:2718" data-raw-source="http://pubsvr01:2718">http://pubsvr01:2718</a></code></p>
<p><span data-ttu-id="1cde4-148">在此示例中，名为 "pubsvr01" 的 Windows Server 2012 R2 托管了管理和发布服务。</span><span class="sxs-lookup"><span data-stu-id="1cde4-148">In the example, A Windows Server 2012 R2 named “pubsvr01” hosts the Management and Publishing services.</span></span></p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-values-query-pub-meta"></a><span data-ttu-id="1cde4-149">客户端操作系统和版本的查询值</span><span class="sxs-lookup"><span data-stu-id="1cde4-149">Query values for client operating system and version</span></span>


<span data-ttu-id="1cde4-150">在 "发布元数据" 查询中，输入与你正在使用的客户端操作系统和版本对应的字符串值。</span><span class="sxs-lookup"><span data-stu-id="1cde4-150">In your publishing metadata query, enter the string values that correspond to the client operating system and version that you’re using.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="1cde4-151">操作系统</span><span class="sxs-lookup"><span data-stu-id="1cde4-151">Operating system</span></span></th>
<th align="left"><span data-ttu-id="1cde4-152">体系结构</span><span class="sxs-lookup"><span data-stu-id="1cde4-152">Architecture</span></span></th>
<th align="left"><span data-ttu-id="1cde4-153">操作字符串字符串值</span><span class="sxs-lookup"><span data-stu-id="1cde4-153">Operating string string value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1cde4-154">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="1cde4-154">Windows 8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="1cde4-155">64 位</span><span class="sxs-lookup"><span data-stu-id="1cde4-155">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="1cde4-156">WindowsClient_6。2_x64</span><span class="sxs-lookup"><span data-stu-id="1cde4-156">WindowsClient_6.2_x64</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="1cde4-157">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="1cde4-157">Windows 8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="1cde4-158">32 位</span><span class="sxs-lookup"><span data-stu-id="1cde4-158">32-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="1cde4-159">WindowsClient_6。2_x86</span><span class="sxs-lookup"><span data-stu-id="1cde4-159">WindowsClient_6.2_x86</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1cde4-160">Windows 8</span><span class="sxs-lookup"><span data-stu-id="1cde4-160">Windows 8</span></span></p></td>
<td align="left"><p><span data-ttu-id="1cde4-161">64 位</span><span class="sxs-lookup"><span data-stu-id="1cde4-161">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="1cde4-162">WindowsClient_6。2_x64</span><span class="sxs-lookup"><span data-stu-id="1cde4-162">WindowsClient_6.2_x64</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="1cde4-163">Windows 8</span><span class="sxs-lookup"><span data-stu-id="1cde4-163">Windows 8</span></span></p></td>
<td align="left"><p><span data-ttu-id="1cde4-164">32 位</span><span class="sxs-lookup"><span data-stu-id="1cde4-164">32-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="1cde4-165">WindowsClient_6。2_x86</span><span class="sxs-lookup"><span data-stu-id="1cde4-165">WindowsClient_6.2_x86</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1cde4-166">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="1cde4-166">Windows Server 2012 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="1cde4-167">64 位</span><span class="sxs-lookup"><span data-stu-id="1cde4-167">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="1cde4-168">WindowsServer_6。2_x64</span><span class="sxs-lookup"><span data-stu-id="1cde4-168">WindowsServer_6.2_x64</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="1cde4-169">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="1cde4-169">Windows Server 2012 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="1cde4-170">32 位</span><span class="sxs-lookup"><span data-stu-id="1cde4-170">32-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="1cde4-171">WindowsServer_6。2_x86</span><span class="sxs-lookup"><span data-stu-id="1cde4-171">WindowsServer_6.2_x86</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1cde4-172">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="1cde4-172">Windows Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="1cde4-173">64 位</span><span class="sxs-lookup"><span data-stu-id="1cde4-173">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="1cde4-174">WindowsServer_6。2_x64</span><span class="sxs-lookup"><span data-stu-id="1cde4-174">WindowsServer_6.2_x64</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="1cde4-175">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="1cde4-175">Windows Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="1cde4-176">32 位</span><span class="sxs-lookup"><span data-stu-id="1cde4-176">32-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="1cde4-177">WindowsServer_6。2_x86</span><span class="sxs-lookup"><span data-stu-id="1cde4-177">WindowsServer_6.2_x86</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1cde4-178">Windows 7</span><span class="sxs-lookup"><span data-stu-id="1cde4-178">Windows 7</span></span></p></td>
<td align="left"><p><span data-ttu-id="1cde4-179">64 位</span><span class="sxs-lookup"><span data-stu-id="1cde4-179">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="1cde4-180">WindowsClient_6。1_x64</span><span class="sxs-lookup"><span data-stu-id="1cde4-180">WindowsClient_6.1_x64</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="1cde4-181">Windows 7</span><span class="sxs-lookup"><span data-stu-id="1cde4-181">Windows 7</span></span></p></td>
<td align="left"><p><span data-ttu-id="1cde4-182">32 位</span><span class="sxs-lookup"><span data-stu-id="1cde4-182">32-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="1cde4-183">WindowsClient_6。1_x86</span><span class="sxs-lookup"><span data-stu-id="1cde4-183">WindowsClient_6.1_x86</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1cde4-184">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="1cde4-184">Windows Server 2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="1cde4-185">64 位</span><span class="sxs-lookup"><span data-stu-id="1cde4-185">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="1cde4-186">WindowsServer_6。1_x64</span><span class="sxs-lookup"><span data-stu-id="1cde4-186">WindowsServer_6.1_x64</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="1cde4-187">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="1cde4-187">Windows Server 2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="1cde4-188">32 位</span><span class="sxs-lookup"><span data-stu-id="1cde4-188">32-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="1cde4-189">WindowsServer_6。1_x86</span><span class="sxs-lookup"><span data-stu-id="1cde4-189">WindowsServer_6.1_x86</span></span></p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-whatis-pub-metadata"></a><span data-ttu-id="1cde4-190">发布元数据的定义</span><span class="sxs-lookup"><span data-stu-id="1cde4-190">Definition of publishing metadata</span></span>


<span data-ttu-id="1cde4-191">将程序包发布到运行 App-v 客户端的计算机时，将向该计算机发送元数据，指示正在发布哪些程序包和连接组。</span><span class="sxs-lookup"><span data-stu-id="1cde4-191">When packages are published to a computer that is running the App-V client, metadata is sent to that computer indicating which packages and connection groups are being published.</span></span> <span data-ttu-id="1cde4-192">App-v 客户端对以下两个单独的请求进行请求：</span><span class="sxs-lookup"><span data-stu-id="1cde4-192">The App-V Client makes two separate requests for the following:</span></span>

-   <span data-ttu-id="1cde4-193">客户端计算机有权享有的程序包和连接组。</span><span class="sxs-lookup"><span data-stu-id="1cde4-193">Packages and connection groups that are entitled to the client computer.</span></span>

-   <span data-ttu-id="1cde4-194">当前用户有权使用的程序包和连接组。</span><span class="sxs-lookup"><span data-stu-id="1cde4-194">Packages and connection groups that are entitled to the current user.</span></span>

<span data-ttu-id="1cde4-195">发布服务器与管理服务器通信，以确定请求者可以使用哪些程序包和连接组。</span><span class="sxs-lookup"><span data-stu-id="1cde4-195">The Publishing server communicates with the Management server to determine which packages and connection groups are available to the requester.</span></span> <span data-ttu-id="1cde4-196">发布服务器必须注册到管理服务器才能生成元数据。</span><span class="sxs-lookup"><span data-stu-id="1cde4-196">The Publishing server must be registered with the Management server in order for the metadata to be generated.</span></span>

<span data-ttu-id="1cde4-197">你可以使用特定用户或计算机上下文中的查询，在 Internet 浏览器中查看每个请求的元数据。</span><span class="sxs-lookup"><span data-stu-id="1cde4-197">You can view the metadata for each request in an Internet browser by using a query that is in the context of the specific user or computer.</span></span>






## <span data-ttu-id="1cde4-198">相关主题</span><span class="sxs-lookup"><span data-stu-id="1cde4-198">Related topics</span></span>


[<span data-ttu-id="1cde4-199">App-V 5.0 技术参考</span><span class="sxs-lookup"><span data-stu-id="1cde4-199">Technical Reference for App-V 5.0</span></span>](technical-reference-for-app-v-50.md)









