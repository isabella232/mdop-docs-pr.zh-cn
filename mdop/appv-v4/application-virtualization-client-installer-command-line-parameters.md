---
title: Application Virtualization Client 安装程序命令行参数
description: Application Virtualization Client 安装程序命令行参数
author: dansimp
ms.assetid: 508fa404-52a5-4919-8788-2a3dfb00639b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 911d333c80060c1881c96430c1d2d0516b6a4855
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802328"
---
# <span data-ttu-id="d3176-103">Application Virtualization Client 安装程序命令行参数</span><span class="sxs-lookup"><span data-stu-id="d3176-103">Application Virtualization Client Installer Command-Line Parameters</span></span>


<span data-ttu-id="d3176-104">下表列出了所有可用的 Microsoft Application Virtualization 客户端安装程序命令行参数、它们的值以及每个参数的简要说明。</span><span class="sxs-lookup"><span data-stu-id="d3176-104">The following table lists all available Microsoft Application Virtualization Client installer command-line parameters, their values, and a brief description of each parameter.</span></span> <span data-ttu-id="d3176-105">参数区分大小写，并且必须以全大写字母形式输入。</span><span class="sxs-lookup"><span data-stu-id="d3176-105">Parameters are case-sensitive and must be entered as all-uppercase letters.</span></span> <span data-ttu-id="d3176-106">所有参数值都必须用双引号引起来。</span><span class="sxs-lookup"><span data-stu-id="d3176-106">All parameter values must be enclosed in double quotes.</span></span>

**<span data-ttu-id="d3176-107">注意</span><span class="sxs-lookup"><span data-stu-id="d3176-107">Note</span></span>**  
-   <span data-ttu-id="d3176-108">对于 App-v 版本4.6，在客户端升级期间无法使用命令行参数。</span><span class="sxs-lookup"><span data-stu-id="d3176-108">For App-V version 4.6, command-line parameters cannot be used during a client upgrade.</span></span>

-   <span data-ttu-id="d3176-109">*SWICACHESIZE*和*MINFREESPACEMB*参数不能在命令行上组合。</span><span class="sxs-lookup"><span data-stu-id="d3176-109">The *SWICACHESIZE* and *MINFREESPACEMB* parameters cannot be combined on the command line.</span></span> <span data-ttu-id="d3176-110">如果同时使用这两个参数，则*SWICACHESIZE*参数将被忽略。</span><span class="sxs-lookup"><span data-stu-id="d3176-110">If both are used, the *SWICACHESIZE* parameter will be ignored.</span></span>



<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="d3176-111">参数</span><span class="sxs-lookup"><span data-stu-id="d3176-111">Parameter</span></span></th>
<th align="left"><span data-ttu-id="d3176-112">值</span><span class="sxs-lookup"><span data-stu-id="d3176-112">Values</span></span></th>
<th align="left"><span data-ttu-id="d3176-113">描述</span><span class="sxs-lookup"><span data-stu-id="d3176-113">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><em><span data-ttu-id="d3176-114">ALLOWINDEPENDENTFILESTREAMING</span><span class="sxs-lookup"><span data-stu-id="d3176-114">ALLOWINDEPENDENTFILESTREAMING</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="d3176-115">TRUE</span><span class="sxs-lookup"><span data-stu-id="d3176-115">TRUE</span></span></p>
<p><span data-ttu-id="d3176-116">FALSE</span><span class="sxs-lookup"><span data-stu-id="d3176-116">FALSE</span></span></p></td>
<td align="left"><p><span data-ttu-id="d3176-117">指示是否将启用来自文件的流，无论客户端是否已配置了 <em> APPLICATIONSOURCEROOT </em> 参数。</span><span class="sxs-lookup"><span data-stu-id="d3176-117">Indicates whether streaming from file will be enabled regardless of how the client has been configured with the <em>APPLICATIONSOURCEROOT</em> parameter.</span></span> <span data-ttu-id="d3176-118">如果设置为 FALSE，则传输将不会启用来自文件的流处理，即使 OSD HREF 或 <em> APPLICATIONSOURCEROOT </em> 参数包含文件路径也是如此。</span><span class="sxs-lookup"><span data-stu-id="d3176-118">If set to FALSE, the transport will not enable streaming from files even if the OSD HREF or the <em>APPLICATIONSOURCEROOT</em> parameter contains a file path.</span></span></p>
<p><span data-ttu-id="d3176-119">可能值：</span><span class="sxs-lookup"><span data-stu-id="d3176-119">Possible values:</span></span></p>
<ul>
<li><p><span data-ttu-id="d3176-120">TRUE —手动部署的应用程序可能从磁盘加载。</span><span class="sxs-lookup"><span data-stu-id="d3176-120">TRUE—Manually deployed application may be loaded from disk.</span></span></p></li>
<li><p><span data-ttu-id="d3176-121">FALSE-所有应用程序都必须来自源流式服务器。</span><span class="sxs-lookup"><span data-stu-id="d3176-121">FALSE—All applications must come from source streaming server.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><em><span data-ttu-id="d3176-122">APPLICATIONSOURCEROOT</span><span class="sxs-lookup"><span data-stu-id="d3176-122">APPLICATIONSOURCEROOT</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="d3176-123">RTSP:// <em> URL </em> （用于动态包传递）</span><span class="sxs-lookup"><span data-stu-id="d3176-123">RTSP:// <em>URL</em> (for dynamic package delivery)</span></span></p>
<p><span data-ttu-id="d3176-124">File:// <em> URL </em> 或 <em> UNC </em> （用于从文件包传递进行加载）</span><span class="sxs-lookup"><span data-stu-id="d3176-124">File:// <em>URL</em> or <em>UNC</em> (for load from file package delivery)</span></span></p></td>
<td align="left"><p><span data-ttu-id="d3176-125">若要启用管理员或电子软件分发系统以确保在符合拓扑管理方案的情况下执行应用程序加载，允许覆盖应用程序 HREF 元素（源位置）的 OSD 基本代码。</span><span class="sxs-lookup"><span data-stu-id="d3176-125">To enable an administrator or an electronic software distribution system to ensure that application loading is performed in compliance with the topology management scheme, allows an override of the OSD CODEBASE for the application HREF element (the source location).</span></span> <span data-ttu-id="d3176-126">如果值为 "" （默认值），则使用现有的 OSD 文件设置。</span><span class="sxs-lookup"><span data-stu-id="d3176-126">If the value is “”, which is the default value, the existing OSD file settings are used.</span></span></p>
<p><span data-ttu-id="d3176-127">URL 有多个部分：</span><span class="sxs-lookup"><span data-stu-id="d3176-127">A URL has several parts:</span></span></p>
<p><span data-ttu-id="d3176-128">&lt;协议 &gt; // &lt; 服务器 &gt; ： &lt; 端口 &gt; / &lt; 路径 &gt; / &lt; ？查询 &gt; &lt; #fragment&gt;</span><span class="sxs-lookup"><span data-stu-id="d3176-128">&lt;protocol&gt;://&lt;server&gt;:&lt;port&gt;/&lt;path&gt;/&lt;?query&gt;&lt;#fragment&gt;</span></span></p>
<p><span data-ttu-id="d3176-129">UNC 路径有三个部分：</span><span class="sxs-lookup"><span data-stu-id="d3176-129">A UNC path has three parts:</span></span></p>
<p><span data-ttu-id="d3176-130">&amp;lt; computername &gt; &amp; lt; 共享文件夹 &gt; &amp; lt; 资源&gt;</span><span class="sxs-lookup"><span data-stu-id="d3176-130">&amp;lt;computername&gt;&amp;lt;share folder&gt;&amp;lt;resource&gt;</span></span></p>
<p><span data-ttu-id="d3176-131">如果 <em> </em> 在客户端上指定了 APPLICATIONSOURCEROOT 参数，则客户端将从 OSD 文件将 URL 或 UNC 路径中断到其构成部分，并将 osd 分区替换为相应的 <em> APPLICATIONSOURCEROOT </em> 部分。</span><span class="sxs-lookup"><span data-stu-id="d3176-131">If the <em>APPLICATIONSOURCEROOT</em> parameter is specified on a client, the client will break the URL or UNC path from an OSD file into its constituent parts and replace the OSD sections with the corresponding <em>APPLICATIONSOURCEROOT</em> sections.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="d3176-132">重要提示</span><span class="sxs-lookup"><span data-stu-id="d3176-132">Important</span></span></strong><br/><p><span data-ttu-id="d3176-133">在将 file://与 UNC 路径配合使用时，请确保使用正确的格式。</span><span class="sxs-lookup"><span data-stu-id="d3176-133">Be sure to use the correct format when using file:// with a UNC path.</span></span> <span data-ttu-id="d3176-134">正确的格式为 file:// &amp; lt; server &gt; &amp; lt; share &gt; 。</span><span class="sxs-lookup"><span data-stu-id="d3176-134">The correct format is file://&amp;lt;server&gt;&amp;lt;share&gt;.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><em><span data-ttu-id="d3176-135">ICONSOURCEROOT</span><span class="sxs-lookup"><span data-stu-id="d3176-135">ICONSOURCEROOT</span></span></em></p></td>
<td align="left"><p><em><span data-ttu-id="d3176-136">UNC</span><span class="sxs-lookup"><span data-stu-id="d3176-136">UNC</span></span></em></p>
<p><span data-ttu-id="d3176-137">HTTP:// <em> url </em> 或 HTTPS:// <em> url</span><span class="sxs-lookup"><span data-stu-id="d3176-137">HTTP://<em>URL</em> or HTTPS://<em>URL</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="d3176-138">允许管理员为发布期间的序列化应用程序包指定图标检索的源位置。</span><span class="sxs-lookup"><span data-stu-id="d3176-138">Enables an administrator to specify a source location for icon retrieval for a sequenced application package during publication.</span></span> <span data-ttu-id="d3176-139">图标源根目录支持 UNC 路径和 Url （HTTP 或 HTTPS）。</span><span class="sxs-lookup"><span data-stu-id="d3176-139">Icon source roots support UNC paths and URLs (HTTP or HTTPS).</span></span> <span data-ttu-id="d3176-140">如果值为 "" （默认值），则使用现有的 OSD 文件设置。</span><span class="sxs-lookup"><span data-stu-id="d3176-140">If the value is “”, which is the default value, the existing OSD file settings are used.</span></span></p>
<p><span data-ttu-id="d3176-141">URL 有多个部分：</span><span class="sxs-lookup"><span data-stu-id="d3176-141">A URL has several parts:</span></span></p>
<p><span data-ttu-id="d3176-142">&lt;协议 &gt; // &lt; 服务器 &gt; ： &lt; 端口 &gt; / &lt; 路径 &gt; / &lt; ？查询 &gt; &lt; #fragment&gt;</span><span class="sxs-lookup"><span data-stu-id="d3176-142">&lt;protocol&gt;://&lt;server&gt;:&lt;port&gt;/&lt;path&gt;/&lt;?query&gt;&lt;#fragment&gt;</span></span></p>
<p><span data-ttu-id="d3176-143">UNC 路径有三个部分：</span><span class="sxs-lookup"><span data-stu-id="d3176-143">A UNC path has three parts:</span></span></p>
<p><span data-ttu-id="d3176-144">&amp;lt; computername &gt; &amp; lt; 共享文件夹 &gt; &amp; lt; 资源&gt;</span><span class="sxs-lookup"><span data-stu-id="d3176-144">&amp;lt;computername&gt;&amp;lt;share folder&gt;&amp;lt;resource&gt;</span></span></p>
<div class="alert">
<strong><span data-ttu-id="d3176-145">重要提示</span><span class="sxs-lookup"><span data-stu-id="d3176-145">Important</span></span></strong><br/><p><span data-ttu-id="d3176-146">请确保使用 UNC 路径时使用正确的格式。</span><span class="sxs-lookup"><span data-stu-id="d3176-146">Be sure to use the correct format when using a UNC path.</span></span> <span data-ttu-id="d3176-147">可接受的格式为 &amp; lt; 服务器 &gt; &amp; lt; 共享 &gt; 或 &lt; 驱动器号 &gt; ： &amp; lt; 文件夹 &gt; 。</span><span class="sxs-lookup"><span data-stu-id="d3176-147">Acceptable formats are &amp;lt;server&gt;&amp;lt;share&gt; or &lt;drive letter&gt;:&amp;lt;folder&gt;.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><em><span data-ttu-id="d3176-148">OSDSOURCEROOT</span><span class="sxs-lookup"><span data-stu-id="d3176-148">OSDSOURCEROOT</span></span></em></p></td>
<td align="left"><p><em><span data-ttu-id="d3176-149">UNC</span><span class="sxs-lookup"><span data-stu-id="d3176-149">UNC</span></span></em></p>
<p><span data-ttu-id="d3176-150">HTTP:// <em> url </em> 或 HTTPS:// <em> url</span><span class="sxs-lookup"><span data-stu-id="d3176-150">HTTP://<em>URL</em> or HTTPS://<em>URL</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="d3176-151">允许管理员为发布期间的应用程序包指定 OSD 文件检索的源位置。</span><span class="sxs-lookup"><span data-stu-id="d3176-151">Enables an administrator to specify a source location for OSD file retrieval for an application package during publication.</span></span> <span data-ttu-id="d3176-152">OSD 源根目录支持 UNC 路径和 Url （HTTP 或 HTTPS）。</span><span class="sxs-lookup"><span data-stu-id="d3176-152">OSD source roots support UNC paths and URLs (HTTP or HTTPS).</span></span> <span data-ttu-id="d3176-153">如果值为 "" （默认值），则使用现有的 OSD 文件设置。</span><span class="sxs-lookup"><span data-stu-id="d3176-153">If the value is “”, which is the default value, the existing OSD file settings are used.</span></span></p>
<p><span data-ttu-id="d3176-154">URL 有多个部分：</span><span class="sxs-lookup"><span data-stu-id="d3176-154">A URL has several parts:</span></span></p>
<p><span data-ttu-id="d3176-155">&lt;协议 &gt; // &lt; 服务器 &gt; ： &lt; 端口 &gt; / &lt; 路径 &gt; / &lt; ？查询 &gt; &lt; #fragment&gt;</span><span class="sxs-lookup"><span data-stu-id="d3176-155">&lt;protocol&gt;://&lt;server&gt;:&lt;port&gt;/&lt;path&gt;/&lt;?query&gt;&lt;#fragment&gt;</span></span></p>
<p><span data-ttu-id="d3176-156">UNC 路径有三个部分：</span><span class="sxs-lookup"><span data-stu-id="d3176-156">A UNC path has three parts:</span></span></p>
<p><span data-ttu-id="d3176-157">&amp;lt; computername &gt; &amp; lt; 共享文件夹 &gt; &amp; lt; 资源&gt;</span><span class="sxs-lookup"><span data-stu-id="d3176-157">&amp;lt;computername&gt;&amp;lt;share folder&gt;&amp;lt;resource&gt;</span></span></p>
<div class="alert">
<strong><span data-ttu-id="d3176-158">重要提示</span><span class="sxs-lookup"><span data-stu-id="d3176-158">Important</span></span></strong><br/><p><span data-ttu-id="d3176-159">请确保使用 UNC 路径时使用正确的格式。</span><span class="sxs-lookup"><span data-stu-id="d3176-159">Be sure to use the correct format when using a UNC path.</span></span> <span data-ttu-id="d3176-160">可接受的格式为 &amp; lt; 服务器 &gt; &amp; lt; 共享 &gt; 或 &lt; 驱动器号 &gt; ： &amp; lt; 文件夹 &gt; 。</span><span class="sxs-lookup"><span data-stu-id="d3176-160">Acceptable formats are &amp;lt;server&gt;&amp;lt;share&gt; or &lt;drive letter&gt;:&amp;lt;folder&gt;.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><em><span data-ttu-id="d3176-161">AUTOLOADONLOGIN</span><span class="sxs-lookup"><span data-stu-id="d3176-161">AUTOLOADONLOGIN</span></span></em></p>
<p><em><span data-ttu-id="d3176-162">AUTOLOADONLAUNCH</span><span class="sxs-lookup"><span data-stu-id="d3176-162">AUTOLOADONLAUNCH</span></span></em></p>
<p><em><span data-ttu-id="d3176-163">AUTOLOADONREFRESH</span><span class="sxs-lookup"><span data-stu-id="d3176-163">AUTOLOADONREFRESH</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="d3176-164">[0 | 1]</span><span class="sxs-lookup"><span data-stu-id="d3176-164">[0|1]</span></span></p></td>
<td align="left"><p><span data-ttu-id="d3176-165">定义启动应用程序自动加载的事件的 AutoLoad 触发器。</span><span class="sxs-lookup"><span data-stu-id="d3176-165">The AutoLoad triggers that define the events that initiate auto-loading of applications.</span></span> <span data-ttu-id="d3176-166">AutoLoad 隐式使用后台流，使应用程序能够完全加载到缓存中。</span><span class="sxs-lookup"><span data-stu-id="d3176-166">AutoLoad implicitly uses background streaming to enable the application to be fully loaded into cache.</span></span></p>
<p><span data-ttu-id="d3176-167">主功能块将尽快加载。</span><span class="sxs-lookup"><span data-stu-id="d3176-167">The primary feature block will be loaded as quickly as possible.</span></span> <span data-ttu-id="d3176-168">将在后台加载剩余功能块以启用前台操作，例如用户与应用程序交互，以获得优先级并提供最佳性能。</span><span class="sxs-lookup"><span data-stu-id="d3176-168">Remaining feature blocks will be loaded in the background to enable foreground operations, such as user interaction with applications, to take priority and provide optimal performance.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="d3176-169">注意</span><span class="sxs-lookup"><span data-stu-id="d3176-169">Note</span></span></strong><br/><p><span data-ttu-id="d3176-170"><em>AUTOLOADTARGET </em> 参数确定自动加载的应用程序。</span><span class="sxs-lookup"><span data-stu-id="d3176-170">The <em>AUTOLOADTARGET</em> parameter determines which applications are auto-loaded.</span></span> <span data-ttu-id="d3176-171">默认情况下，已使用的程序包将自动加载，除非 <em> </em> 已设置 AUTOLOADTARGET。</span><span class="sxs-lookup"><span data-stu-id="d3176-171">By default, packages that have been used are auto-loaded unless <em>AUTOLOADTARGET</em> is set.</span></span></p>
</div>
<div>

</div>
<p><span data-ttu-id="d3176-172">每个参数都影响加载行为，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d3176-172">Each parameter affects loading behavior as follows:</span></span></p>
<ul>
<li><p><em><span data-ttu-id="d3176-173">AUTOLOADONLOGIN </em> -用户登录时开始加载。</span><span class="sxs-lookup"><span data-stu-id="d3176-173">AUTOLOADONLOGIN</em>—Loading starts when the user logs in.</span></span></p></li>
<li><p><em><span data-ttu-id="d3176-174">AUTOLOADONLAUNCH </em> -用户启动应用程序时开始加载。</span><span class="sxs-lookup"><span data-stu-id="d3176-174">AUTOLOADONLAUNCH</em>—Loading starts when the user starts an application.</span></span></p></li>
<li><p><em><span data-ttu-id="d3176-175">AUTOLOADONREFRESH </em> -在进行发布刷新时开始加载。</span><span class="sxs-lookup"><span data-stu-id="d3176-175">AUTOLOADONREFRESH</em>—Loading starts when a publishing refresh occurs.</span></span></p></li>
</ul>
<p><span data-ttu-id="d3176-176">这三个值可以组合。</span><span class="sxs-lookup"><span data-stu-id="d3176-176">The three values can be combined.</span></span> <span data-ttu-id="d3176-177">在以下示例中，在用户登录时和发布刷新发生时均启用 AutoLoad 触发器：</span><span class="sxs-lookup"><span data-stu-id="d3176-177">In the following example, AutoLoad triggers are enabled both at user login and when publishing refresh occurs:</span></span></p>
<p><em><span data-ttu-id="d3176-178">AUTOLOADONLOGIN AUTOLOADONREFRESH</span><span class="sxs-lookup"><span data-stu-id="d3176-178">AUTOLOADONLOGIN AUTOLOADONREFRESH</span></span></em></p>
<div class="alert">
<strong><span data-ttu-id="d3176-179">注意</span><span class="sxs-lookup"><span data-stu-id="d3176-179">Note</span></span></strong><br/><p><span data-ttu-id="d3176-180">如果在首次安装时使用这些值配置客户端，则在下次用户注销并重新登录之前，不会触发 Autoload。</span><span class="sxs-lookup"><span data-stu-id="d3176-180">If the client is configured with these values at first install, Autoload will not be triggered until the next time the user logs off and logs back on.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><em><span data-ttu-id="d3176-181">AUTOLOADTARGET</span><span class="sxs-lookup"><span data-stu-id="d3176-181">AUTOLOADTARGET</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="d3176-182">尚</span><span class="sxs-lookup"><span data-stu-id="d3176-182">NONE</span></span></p>
<p><span data-ttu-id="d3176-183">所有</span><span class="sxs-lookup"><span data-stu-id="d3176-183">ALL</span></span></p>
<p><span data-ttu-id="d3176-184">PREVUSED</span><span class="sxs-lookup"><span data-stu-id="d3176-184">PREVUSED</span></span></p></td>
<td align="left"><p><span data-ttu-id="d3176-185">指示在任何给定的 AutoLoad 触发器出现时将自动加载的内容。</span><span class="sxs-lookup"><span data-stu-id="d3176-185">Indicates what will be auto-loaded when any given AutoLoad triggers occur.</span></span></p>
<p><span data-ttu-id="d3176-186">可能值：</span><span class="sxs-lookup"><span data-stu-id="d3176-186">Possible values:</span></span></p>
<ul>
<li><p><span data-ttu-id="d3176-187">无-不自动加载，无论可能设置哪些触发器。</span><span class="sxs-lookup"><span data-stu-id="d3176-187">NONE—No auto-loading, regardless of what triggers might be set.</span></span></p></li>
<li><p><span data-ttu-id="d3176-188">所有-如果启用了任何 AutoLoad 触发器，则会自动加载所有程序包，无论它们是否已启动。</span><span class="sxs-lookup"><span data-stu-id="d3176-188">ALL—If any AutoLoad trigger is enabled, all packages are automatically loaded, whether or not they have ever been launched.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="d3176-189">注意</span><span class="sxs-lookup"><span data-stu-id="d3176-189">Note</span></span></strong><br/><p><span data-ttu-id="d3176-190">通过使用 SFTMIME <strong> 添加程序包 </strong> 和 <strong> 配置程序包命令，为单个程序包配置此设置 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="d3176-190">This setting is configured for individual packages by using the SFTMIME <strong>ADD PACKAGE</strong> and <strong>CONFIGURE PACKAGE</strong> commands.</span></span> <span data-ttu-id="d3176-191">有关这些命令的详细信息，请参阅 <a href="sftmime--command-reference.md" data-raw-source="[SFTMIME Command Reference](sftmime--command-reference.md)"> SFTMIME 命令参考 </a> 。</span><span class="sxs-lookup"><span data-stu-id="d3176-191">For more information about these commands, see <a href="sftmime--command-reference.md" data-raw-source="[SFTMIME Command Reference](sftmime--command-reference.md)">SFTMIME Command Reference</a>.</span></span></p>
</div>
<div>

</div></li>
<li><p><span data-ttu-id="d3176-192">PREVUSED-如果启用了任何 AutoLoad 触发器，则仅加载以前使用过程序包中至少一个应用程序（即启动或 precached）的程序包。</span><span class="sxs-lookup"><span data-stu-id="d3176-192">PREVUSED—If any AutoLoad trigger is enabled, load only the packages where at least one application in the package has been previously used (that is, launched or precached).</span></span></p></li>
</ul>
<div class="alert">
<strong><span data-ttu-id="d3176-193">注意</span><span class="sxs-lookup"><span data-stu-id="d3176-193">Note</span></span></strong><br/><p><span data-ttu-id="d3176-194">当安装 app-v 客户端以使用只读缓存（例如，作为 VDI 服务器实现）时，必须将 <em> AUTOLOADTARGET </em> 参数设置为 NONE，以防止客户端尝试更新只读缓存中的应用程序。</span><span class="sxs-lookup"><span data-stu-id="d3176-194">When you install the App-V client to use a read-only cache, (for example, as a VDI server implementation), you must set the <em>AUTOLOADTARGET</em> parameter to NONE to prevent the client from trying to update applications in the read-only cache.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><em><span data-ttu-id="d3176-195">DOTIMEOUTMINUTES</span><span class="sxs-lookup"><span data-stu-id="d3176-195">DOTIMEOUTMINUTES</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="d3176-196">29600（默认值）</span><span class="sxs-lookup"><span data-stu-id="d3176-196">29600 (default)</span></span></p>
<p><span data-ttu-id="d3176-197">1–1439998560分钟数（范围）</span><span class="sxs-lookup"><span data-stu-id="d3176-197">1–1439998560 minutes (range)</span></span></p></td>
<td align="left"><p><span data-ttu-id="d3176-198">指示在断开连接的操作中可以使用的应用程序的分钟数。</span><span class="sxs-lookup"><span data-stu-id="d3176-198">Indicates how many minutes an application may be used in disconnected operation.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><em><span data-ttu-id="d3176-199">INSTALLDIR</span><span class="sxs-lookup"><span data-stu-id="d3176-199">INSTALLDIR</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="d3176-200">&lt;路径名&gt;</span><span class="sxs-lookup"><span data-stu-id="d3176-200">&lt;pathname&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="d3176-201">指定 App-v 客户端的安装目录。</span><span class="sxs-lookup"><span data-stu-id="d3176-201">Specifies the installation directory of the App-V Client.</span></span></p>
<p><span data-ttu-id="d3176-202">示例： INSTALLDIR = &quot; C:\Program Files\Microsoft Application Virtualization 客户端&quot;</span><span class="sxs-lookup"><span data-stu-id="d3176-202">Example: INSTALLDIR=&quot;C:\Program Files\Microsoft Application Virtualization Client&quot;</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><em><span data-ttu-id="d3176-203">OPTIN</span><span class="sxs-lookup"><span data-stu-id="d3176-203">OPTIN</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="d3176-204">真实</span><span class="sxs-lookup"><span data-stu-id="d3176-204">“TRUE”</span></span></p>
<p><span data-ttu-id="d3176-205">“”</span><span class="sxs-lookup"><span data-stu-id="d3176-205">“”</span></span></p></td>
<td align="left"><p><span data-ttu-id="d3176-206">Microsoft Application Virtualization 客户端组件将可通过 Microsoft 更新进行升级，可供公众使用更新。</span><span class="sxs-lookup"><span data-stu-id="d3176-206">Microsoft Application Virtualization Client components will be upgradable through Microsoft Update when updates are made available to the general public.</span></span> <span data-ttu-id="d3176-207">在 Windows 操作系统上安装的 Microsoft Update 代理要求用户明确选择使用该服务。</span><span class="sxs-lookup"><span data-stu-id="d3176-207">The Microsoft Update Agent installed on Windows operating systems requires a user to explicitly opt-in to use the service.</span></span> <span data-ttu-id="d3176-208">对于设备上的所有应用程序，此选择性加入只需一次。</span><span class="sxs-lookup"><span data-stu-id="d3176-208">This opt-in is required only one time for all applications on the device.</span></span> <span data-ttu-id="d3176-209">如果你已选择加入 Microsoft 更新，则设备上的 Microsoft Application Virtualization 组件将自动利用该服务。</span><span class="sxs-lookup"><span data-stu-id="d3176-209">If you have already opted into Microsoft Update, the Microsoft Application Virtualization components on the device will automatically take advantage of the service.</span></span></p>
<p><span data-ttu-id="d3176-210">对于命令行安装，默认情况下使用 "Microsoft Update" 默认选择退出（除非以前的应用程序已启用要选择加入的设备），因为需要手动选择 "Microsoft Update"。</span><span class="sxs-lookup"><span data-stu-id="d3176-210">For command-line installation, use of Microsoft Update is by default opt-out (unless a previous application already enabled the device to be opted in) due to the requirement for manually opting into Microsoft Update.</span></span> <span data-ttu-id="d3176-211">因此，在命令行安装中，选择 "加入" 必须是显式的。</span><span class="sxs-lookup"><span data-stu-id="d3176-211">Therefore, opting in must be explicit for command-line installations.</span></span> <span data-ttu-id="d3176-212">将命令行参数 OPTIN 设置 <em> </em> 为 TRUE 会强制设置 Microsoft 更新选择加入。</span><span class="sxs-lookup"><span data-stu-id="d3176-212">Setting the command-line parameter <em>OPTIN</em> to TRUE forces the Microsoft Update opt-in to be set.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><em><span data-ttu-id="d3176-213">REQUIREAUTHORIZATIONIFCACHED</span><span class="sxs-lookup"><span data-stu-id="d3176-213">REQUIREAUTHORIZATIONIFCACHED</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="d3176-214">TRUE</span><span class="sxs-lookup"><span data-stu-id="d3176-214">TRUE</span></span></p>
<p><span data-ttu-id="d3176-215">FALSE</span><span class="sxs-lookup"><span data-stu-id="d3176-215">FALSE</span></span></p></td>
<td align="left"><p><span data-ttu-id="d3176-216">指示是否始终需要授权，无论是否需要授权应用程序是否已在缓存中。</span><span class="sxs-lookup"><span data-stu-id="d3176-216">Indicates whether authorization is always required, whether or not an application is already in cache.</span></span></p>
<p><span data-ttu-id="d3176-217">可能值：</span><span class="sxs-lookup"><span data-stu-id="d3176-217">Possible values:</span></span></p>
<ul>
<li><p><span data-ttu-id="d3176-218">TRUE-应用程序始终必须在启动时获得授权。</span><span class="sxs-lookup"><span data-stu-id="d3176-218">TRUE—Application always must be authorized at startup.</span></span> <span data-ttu-id="d3176-219">对于 RTSP 流处理应用程序，将向服务器发送用户授权令牌以进行授权。</span><span class="sxs-lookup"><span data-stu-id="d3176-219">For RTSP streamed applications, the user authorization token is sent to the server for authorization.</span></span> <span data-ttu-id="d3176-220">对于基于文件的应用程序，文件 Acl 决定用户是否可以访问应用程序。</span><span class="sxs-lookup"><span data-stu-id="d3176-220">For file-based applications, file ACLs dictate whether a user may access the application.</span></span></p></li>
<li><p><span data-ttu-id="d3176-221">FALSE —始终尝试连接到服务器。</span><span class="sxs-lookup"><span data-stu-id="d3176-221">FALSE—Always try to connect to the server.</span></span> <span data-ttu-id="d3176-222">如果无法建立与服务器的连接，客户端仍允许用户启动以前加载到缓存中的应用程序。</span><span class="sxs-lookup"><span data-stu-id="d3176-222">If a connection to the server cannot be established, the client still allows the user to launch an application that has previously been loaded into cache.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><em><span data-ttu-id="d3176-223">SWICACHESIZE</span><span class="sxs-lookup"><span data-stu-id="d3176-223">SWICACHESIZE</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="d3176-224">缓存大小（以 MB 为单位）</span><span class="sxs-lookup"><span data-stu-id="d3176-224">Cache size in MB</span></span></p></td>
<td align="left"><p><span data-ttu-id="d3176-225">指定客户端缓存的大小（以 mb 为单位）。</span><span class="sxs-lookup"><span data-stu-id="d3176-225">Specifies the size in megabytes of the client cache.</span></span> <span data-ttu-id="d3176-226">默认大小为 4096 MB，最大大小为 1048576 MB （1 TB）。</span><span class="sxs-lookup"><span data-stu-id="d3176-226">The default size is 4096 MB, and the maximum size is 1,048,576 MB (1 TB).</span></span> <span data-ttu-id="d3176-227">系统会在安装时检查可用空间，但不保留空间。</span><span class="sxs-lookup"><span data-stu-id="d3176-227">The system checks for the available space at installation time, but the space is not reserved.</span></span></p>
<p><span data-ttu-id="d3176-228">示例： <strong> SWICACHESIZE = &quot; 1024&quot;</span><span class="sxs-lookup"><span data-stu-id="d3176-228">Example: <strong>SWICACHESIZE=&quot;1024&quot;</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><em><span data-ttu-id="d3176-229">SWIPUBSVRDISPLAY</span><span class="sxs-lookup"><span data-stu-id="d3176-229">SWIPUBSVRDISPLAY</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="d3176-230">显示名称</span><span class="sxs-lookup"><span data-stu-id="d3176-230">Display name</span></span></p></td>
<td align="left"><p><span data-ttu-id="d3176-231">指定发布服务器的显示名称;<em>使用 SWIPUBSVRHOST 时需要 </em> 。</span><span class="sxs-lookup"><span data-stu-id="d3176-231">Specifies the displayed name of the publishing server; required when <em>SWIPUBSVRHOST</em> is used.</span></span></p>
<p><span data-ttu-id="d3176-232">示例： <strong> SWIPUBSVRDISPLAY = &quot; 生产环境&quot;</span><span class="sxs-lookup"><span data-stu-id="d3176-232">Example: <strong>SWIPUBSVRDISPLAY=&quot;PRODUCTION ENVIRONMENT&quot;</span></span></strong></p></td>
</tr>
<tr class="odd">
<td align="left"><p><em><span data-ttu-id="d3176-233">SWIPUBSVRTYPE</span><span class="sxs-lookup"><span data-stu-id="d3176-233">SWIPUBSVRTYPE</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="d3176-234">[HTTP |RTSP</span><span class="sxs-lookup"><span data-stu-id="d3176-234">[HTTP|RTSP]</span></span></p></td>
<td align="left"><p><span data-ttu-id="d3176-235">指定发布服务器类型。</span><span class="sxs-lookup"><span data-stu-id="d3176-235">Specifies the publishing server type.</span></span> <span data-ttu-id="d3176-236">默认服务器类型是 Application Virtualization 服务器。</span><span class="sxs-lookup"><span data-stu-id="d3176-236">The default server type is Application Virtualization Server.</span></span> <span data-ttu-id="d3176-237"><strong>/Secure </strong> 开关不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="d3176-237">The <strong>/secure</strong> switch is not case sensitive.</span></span></p>
<ul>
<li><p><span data-ttu-id="d3176-238">HTTP-标准 HTTP 服务器</span><span class="sxs-lookup"><span data-stu-id="d3176-238">HTTP—Standard HTTP Server</span></span></p></li>
<li><p><span data-ttu-id="d3176-239">HTTP <strong> /secure </strong> -增强的安全 HTTP 服务器</span><span class="sxs-lookup"><span data-stu-id="d3176-239">HTTP <strong>/secure</strong>—Enhanced Security HTTP Server</span></span></p></li>
<li><p><span data-ttu-id="d3176-240">RTSP-应用程序虚拟化服务器</span><span class="sxs-lookup"><span data-stu-id="d3176-240">RTSP—Application Virtualization Server</span></span></p></li>
<li><p><span data-ttu-id="d3176-241">RTSP <strong> /secure </strong> -增强的安全应用程序虚拟化服务器</span><span class="sxs-lookup"><span data-stu-id="d3176-241">RTSP <strong>/secure</strong>—Enhanced Security Application Virtualization Server</span></span></p></li>
</ul>
<p><span data-ttu-id="d3176-242">示例： <strong> SWIPUBSVRTYPE = &quot; HTTP/secure&quot;</span><span class="sxs-lookup"><span data-stu-id="d3176-242">Example: <strong>SWIPUBSVRTYPE=&quot;HTTP /secure&quot;</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><em><span data-ttu-id="d3176-243">SWIPUBSVRHOST</span><span class="sxs-lookup"><span data-stu-id="d3176-243">SWIPUBSVRHOST</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="d3176-244">IP 地址 | 主机名</span><span class="sxs-lookup"><span data-stu-id="d3176-244">IP address|host name</span></span></p></td>
<td align="left"><p><span data-ttu-id="d3176-245">指定应用程序虚拟化服务器的 IP 地址或解析为服务器的服务器的主机名&#39;s IP 地址;<em>使用 SWIPUBSVRDISPLAY 时需要 </em> 。</span><span class="sxs-lookup"><span data-stu-id="d3176-245">Specifies either the IP address of the Application Virtualization Server or a host name of the server that resolves into the server&#39;s IP address; required when <em>SWIPUBSVRDISPLAY</em> is used.</span></span></p>
<p><span data-ttu-id="d3176-246">示例： <strong> SWIPUBSVRHOST = &quot; SERVER01&quot;</span><span class="sxs-lookup"><span data-stu-id="d3176-246">Example: <strong>SWIPUBSVRHOST=&quot;SERVER01&quot;</span></span></strong></p></td>
</tr>
<tr class="odd">
<td align="left"><p><em><span data-ttu-id="d3176-247">SWIPUBSVRPORT</span><span class="sxs-lookup"><span data-stu-id="d3176-247">SWIPUBSVRPORT</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="d3176-248">端口号</span><span class="sxs-lookup"><span data-stu-id="d3176-248">Port number</span></span></p></td>
<td align="left"><p><span data-ttu-id="d3176-249">指定此应用程序虚拟化服务器用于侦听来自客户端的请求的逻辑端口（default = 554）。</span><span class="sxs-lookup"><span data-stu-id="d3176-249">Specifies the logical port that is used by this Application Virtualization Server to listen for requests from the client (default = 554).</span></span></p>
<ul>
<li><p><span data-ttu-id="d3176-250">标准 HTTP 服务器-默认 = 80。</span><span class="sxs-lookup"><span data-stu-id="d3176-250">Standard HTTP server—Default = 80.</span></span></p></li>
<li><p><span data-ttu-id="d3176-251">增强的安全 HTTP 服务器-默认 = 443。</span><span class="sxs-lookup"><span data-stu-id="d3176-251">Enhanced Security HTTP Server—Default = 443.</span></span></p></li>
<li><p><span data-ttu-id="d3176-252">应用程序虚拟化服务器-默认 = 554。</span><span class="sxs-lookup"><span data-stu-id="d3176-252">Application Virtualization Server—Default = 554.</span></span></p></li>
<li><p><span data-ttu-id="d3176-253">增强的安全应用程序虚拟化服务器-默认 = 322。</span><span class="sxs-lookup"><span data-stu-id="d3176-253">Enhanced Security Application Virtualization Server—Default = 322.</span></span></p></li>
</ul>
<p><span data-ttu-id="d3176-254">示例： <strong> SWIPUBSVRPORT = &quot; 443&quot;</span><span class="sxs-lookup"><span data-stu-id="d3176-254">Example: <strong>SWIPUBSVRPORT=&quot;443&quot;</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><em><span data-ttu-id="d3176-255">SWIPUBSVRPATH</span><span class="sxs-lookup"><span data-stu-id="d3176-255">SWIPUBSVRPATH</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="d3176-256">路径名称</span><span class="sxs-lookup"><span data-stu-id="d3176-256">Path name</span></span></p></td>
<td align="left"><p><span data-ttu-id="d3176-257">指定文件的发布服务器上定义文件类型关联（default =/）的位置;当 <em> SWIPUBSVRTYPE </em> 参数值为 HTTP 时是必需的。</span><span class="sxs-lookup"><span data-stu-id="d3176-257">Specifies the location on the publishing server of the file that defines file type associations (default = /); required when the <em>SWIPUBSVRTYPE</em> parameter value is HTTP.</span></span></p>
<p><span data-ttu-id="d3176-258">示例： <strong> SWIPUBSVRPATH = &quot; /AppVirt/appsntypes.xml&quot;</span><span class="sxs-lookup"><span data-stu-id="d3176-258">Example: <strong>SWIPUBSVRPATH=&quot;/AppVirt/appsntypes.xml&quot;</span></span></strong></p></td>
</tr>
<tr class="odd">
<td align="left"><p><em><span data-ttu-id="d3176-259">SWIPUBSVRREFRESH</span><span class="sxs-lookup"><span data-stu-id="d3176-259">SWIPUBSVRREFRESH</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="d3176-260">[打开 |之外</span><span class="sxs-lookup"><span data-stu-id="d3176-260">[ON|OFF]</span></span></p></td>
<td align="left"><p><span data-ttu-id="d3176-261">指定当用户登录到客户端时，客户端是否自动查询文件类型关联和应用程序的发布服务器（default = ON）。</span><span class="sxs-lookup"><span data-stu-id="d3176-261">Specifies whether the client automatically queries the publishing server for file type associations and applications when a user logs in to the client (default = ON).</span></span></p>
<p><span data-ttu-id="d3176-262">示例： <strong> SWIPUBSVRREFRESH = &quot; off&quot;</span><span class="sxs-lookup"><span data-stu-id="d3176-262">Example: <strong>SWIPUBSVRREFRESH=&quot;off&quot;</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><em><span data-ttu-id="d3176-263">SWIGLOBALDATA</span><span class="sxs-lookup"><span data-stu-id="d3176-263">SWIGLOBALDATA</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="d3176-264">全局数据目录</span><span class="sxs-lookup"><span data-stu-id="d3176-264">Global data directory</span></span></p></td>
<td align="left"><p><span data-ttu-id="d3176-265">指定将存储不特定于特定用户的数据的目录（默认值 = C:\Documents 和 Settings\All Users\Documents）。</span><span class="sxs-lookup"><span data-stu-id="d3176-265">Specifies the directory where data will be stored that is not specific to particular users (default = C:\Documents and Settings\All Users\Documents).</span></span></p>
<p><span data-ttu-id="d3176-266">示例： <strong> SWIGLOBALDATA = &quot; D:\Microsoft Application Virtualization Client\Global&quot;</span><span class="sxs-lookup"><span data-stu-id="d3176-266">Example: <strong>SWIGLOBALDATA=&quot;D:\Microsoft Application Virtualization Client\Global&quot;</span></span></strong></p></td>
</tr>
<tr class="odd">
<td align="left"><p><em><span data-ttu-id="d3176-267">SWIUSERDATA</span><span class="sxs-lookup"><span data-stu-id="d3176-267">SWIUSERDATA</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="d3176-268">用户数据目录</span><span class="sxs-lookup"><span data-stu-id="d3176-268">User data directory</span></span></p></td>
<td align="left"><p><span data-ttu-id="d3176-269">指定将存储特定于特定用户的数据的目录（默认值 =% APPDATA%）。</span><span class="sxs-lookup"><span data-stu-id="d3176-269">Specifies the directory where data will be stored that is specific to particular users (default = %APPDATA%).</span></span></p>
<p><span data-ttu-id="d3176-270">示例： <strong> SWIUSERDATA = &quot; H:\Windows\Microsoft Application Virtualization 客户端&quot;</span><span class="sxs-lookup"><span data-stu-id="d3176-270">Example: <strong>SWIUSERDATA=&quot;H:\Windows\Microsoft Application Virtualization Client&quot;</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><em><span data-ttu-id="d3176-271">SWIFSDRIVE</span><span class="sxs-lookup"><span data-stu-id="d3176-271">SWIFSDRIVE</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="d3176-272">首选驱动器号</span><span class="sxs-lookup"><span data-stu-id="d3176-272">Preferred drive letter</span></span></p></td>
<td align="left"><p><span data-ttu-id="d3176-273">对应于为虚拟驱动器选择的驱动器号。</span><span class="sxs-lookup"><span data-stu-id="d3176-273">Corresponds to the drive letter that you selected for the virtual drive.</span></span></p>
<p><span data-ttu-id="d3176-274">示例： <strong> SWIFSDRIVE = &quot; S&quot;</span><span class="sxs-lookup"><span data-stu-id="d3176-274">Example: <strong>SWIFSDRIVE=&quot;S&quot;</span></span></strong></p></td>
</tr>
<tr class="odd">
<td align="left"><p><em><span data-ttu-id="d3176-275">SYSTEMEVENTLOGLEVEL</span><span class="sxs-lookup"><span data-stu-id="d3176-275">SYSTEMEVENTLOGLEVEL</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="d3176-276">0–4</span><span class="sxs-lookup"><span data-stu-id="d3176-276">0–4</span></span></p></td>
<td align="left"><p><span data-ttu-id="d3176-277">指示日志消息写入 NT 事件日志的日志记录级别。</span><span class="sxs-lookup"><span data-stu-id="d3176-277">Indicates the logging level at which log messages are written to the NT event Log.</span></span> <span data-ttu-id="d3176-278">该值指示所记录内容的阈值，即记录的所有内容都等于或小于该值。</span><span class="sxs-lookup"><span data-stu-id="d3176-278">The value indicates a threshold of what is logged—that is, everything equal to or less than that value is logged.</span></span> <span data-ttu-id="d3176-279">例如，值0x3 （警告）表示记录警告（0x3）、错误（0x2）和严重错误（0x1）。</span><span class="sxs-lookup"><span data-stu-id="d3176-279">For example, a value of 0x3 (Warning) indicates that Warnings (0x3), Errors (0x2), and Critical Errors (0x1) are logged.</span></span></p>
<p><span data-ttu-id="d3176-280">可能值：</span><span class="sxs-lookup"><span data-stu-id="d3176-280">Possible values:</span></span></p>
<ul>
<li><p><span data-ttu-id="d3176-281">0 = = 无</span><span class="sxs-lookup"><span data-stu-id="d3176-281">0 == None</span></span></p></li>
<li><p><span data-ttu-id="d3176-282">1 = = 严重</span><span class="sxs-lookup"><span data-stu-id="d3176-282">1 == Critical</span></span></p></li>
<li><p><span data-ttu-id="d3176-283">2 = = 错误</span><span class="sxs-lookup"><span data-stu-id="d3176-283">2 == Error</span></span></p></li>
<li><p><span data-ttu-id="d3176-284">3 = = 警告</span><span class="sxs-lookup"><span data-stu-id="d3176-284">3 == Warning</span></span></p></li>
<li><p><span data-ttu-id="d3176-285">4 = = 信息</span><span class="sxs-lookup"><span data-stu-id="d3176-285">4 == Information</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><em><span data-ttu-id="d3176-286">MINFREESPACEMB</span><span class="sxs-lookup"><span data-stu-id="d3176-286">MINFREESPACEMB</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="d3176-287">以 MB 为单位</span><span class="sxs-lookup"><span data-stu-id="d3176-287">In MB</span></span></p></td>
<td align="left"><p><span data-ttu-id="d3176-288">指定主机上必须提供的可用空间量（以兆字节为单位），才能增加缓存大小。</span><span class="sxs-lookup"><span data-stu-id="d3176-288">Specifies the amount of free space (in megabytes) that must be available on the host before the cache size can increase.</span></span> <span data-ttu-id="d3176-289">以下示例将配置客户端以确保磁盘上至少有 5 GB 的可用空间，然后再允许缓存大小增加。</span><span class="sxs-lookup"><span data-stu-id="d3176-289">The following example would configure the client to ensure at least 5 GB of free space on the disk before allowing the size of the cache to increase.</span></span> <span data-ttu-id="d3176-290">默认值为安装时磁盘上的 5000 MB 可用空间。</span><span class="sxs-lookup"><span data-stu-id="d3176-290">The default is 5000 MB of free space available on disk at installation time.</span></span></p>
<p><span data-ttu-id="d3176-291">示例： <strong> MINFREESPACEMB = &quot; 5000 &quot; （5 GB）</span><span class="sxs-lookup"><span data-stu-id="d3176-291">Example: <strong>MINFREESPACEMB =&quot;5000&quot; (5 GB)</span></span></strong></p></td>
</tr>
<tr class="odd">
<td align="left"><p><em><span data-ttu-id="d3176-292">KEEPCURRENTSETTINGS</span><span class="sxs-lookup"><span data-stu-id="d3176-292">KEEPCURRENTSETTINGS</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="d3176-293">[0 | 1]</span><span class="sxs-lookup"><span data-stu-id="d3176-293">[0|1]</span></span></p></td>
<td align="left"><p><span data-ttu-id="d3176-294">在部署客户端之前应用注册表设置（例如，通过使用组策略）时使用。</span><span class="sxs-lookup"><span data-stu-id="d3176-294">Used when you have applied registry settings prior to deploying a client—for example, by using Group Policy.</span></span> <span data-ttu-id="d3176-295">当部署客户端时，将此参数设置为值1，以便它不会覆盖注册表设置。</span><span class="sxs-lookup"><span data-stu-id="d3176-295">When a client is deployed, set this parameter to a value of 1 so that it will not overwrite the registry settings.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="d3176-296">重要提示</span><span class="sxs-lookup"><span data-stu-id="d3176-296">Important</span></span></strong><br/><p><span data-ttu-id="d3176-297">如果设置为值1，将忽略以下客户端安装程序命令行参数：</span><span class="sxs-lookup"><span data-stu-id="d3176-297">If set to a value of 1, the following client installer command-line parameters are ignored:</span></span></p>
<p><strong><span data-ttu-id="d3176-298">SWICACHESIZE </strong> 、 <strong> MINFREESPACEMB </strong> 、 <strong> ALLOWINDEPENDENTFILESTREAMING </strong> 、 <strong> APPLICATIONSOURCEROOT、ICONSOURCEROOT、OSDSOURCEROOT、 </strong> <strong> SYSTEMEVENTLOGLEVEL、 </strong> <strong> </strong> <strong> </strong> <strong> </strong> <strong> </strong> <strong> </strong> <strong> </strong> <strong> </strong> <strong> </strong> SWIGLOBALDATA、DOTIMEOUTMINUTES、SWIFSDRIVE、AUTOLOADTARGET、AUTOLOADTRIGGERS 和 SWIUSERDATA。</span><span class="sxs-lookup"><span data-stu-id="d3176-298">SWICACHESIZE</strong>, <strong>MINFREESPACEMB</strong>, <strong>ALLOWINDEPENDENTFILESTREAMING</strong>, <strong>APPLICATIONSOURCEROOT</strong>, <strong>ICONSOURCEROOT</strong>, <strong>OSDSOURCEROOT</strong>, <strong>SYSTEMEVENTLOGLEVEL</strong>, <strong>SWIGLOBALDATA</strong>, <strong>DOTIMEOUTMINUTES</strong>, <strong>SWIFSDRIVE</strong>, <strong>AUTOLOADTARGET</strong>, <strong>AUTOLOADTRIGGERS</strong>, and <strong>SWIUSERDATA</strong>.</span></span></p>
<p><span data-ttu-id="d3176-299">有关在安装后设置这些值的进一步信息，请参阅如何使用 "应用程序虚拟化（app-v）操作指南" （）中的 "使用命令行配置 App-v Client 注册表设置" <a href="https://go.microsoft.com/fwlink/?LinkId=122939" data-raw-source="[https://go.microsoft.com/fwlink/?LinkId=122939](https://go.microsoft.com/fwlink/?LinkId=122939)"> https://go.microsoft.com/fwlink/?LinkId=122939 </a> 。</span><span class="sxs-lookup"><span data-stu-id="d3176-299">For further information about setting these values after installation, see “How to Configure the App-V Client Registry Settings by Using the Command Line” in the Application Virtualization (App-V) Operations Guide (<a href="https://go.microsoft.com/fwlink/?LinkId=122939" data-raw-source="[https://go.microsoft.com/fwlink/?LinkId=122939](https://go.microsoft.com/fwlink/?LinkId=122939)">https://go.microsoft.com/fwlink/?LinkId=122939</a>).</span></span></p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="d3176-300">相关主题</span><span class="sxs-lookup"><span data-stu-id="d3176-300">Related topics</span></span>


[<span data-ttu-id="d3176-301">如何手动安装 Application Virtualization Client</span><span class="sxs-lookup"><span data-stu-id="d3176-301">How to Manually Install the Application Virtualization Client</span></span>](how-to-manually-install-the-application-virtualization-client.md)

[<span data-ttu-id="d3176-302">如何升级 Application Virtualization Client</span><span class="sxs-lookup"><span data-stu-id="d3176-302">How to Upgrade the Application Virtualization Client</span></span>](how-to-upgrade-the-application-virtualization-client.md)

[<span data-ttu-id="d3176-303">SFTMIME 命令引用</span><span class="sxs-lookup"><span data-stu-id="d3176-303">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)









