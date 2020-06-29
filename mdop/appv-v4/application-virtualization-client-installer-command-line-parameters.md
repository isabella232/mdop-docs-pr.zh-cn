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
# Application Virtualization Client 安装程序命令行参数


下表列出了所有可用的 Microsoft Application Virtualization 客户端安装程序命令行参数、它们的值以及每个参数的简要说明。 参数区分大小写，并且必须以全大写字母形式输入。 所有参数值都必须用双引号引起来。

**注意**  
-   对于 App-v 版本4.6，在客户端升级期间无法使用命令行参数。

-   *SWICACHESIZE*和*MINFREESPACEMB*参数不能在命令行上组合。 如果同时使用这两个参数，则*SWICACHESIZE*参数将被忽略。



<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">参数</th>
<th align="left">值</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><em>ALLOWINDEPENDENTFILESTREAMING</em></p></td>
<td align="left"><p>TRUE</p>
<p>FALSE</p></td>
<td align="left"><p>指示是否将启用来自文件的流，无论客户端是否已配置了 <em> APPLICATIONSOURCEROOT </em> 参数。 如果设置为 FALSE，则传输将不会启用来自文件的流处理，即使 OSD HREF 或 <em> APPLICATIONSOURCEROOT </em> 参数包含文件路径也是如此。</p>
<p>可能值：</p>
<ul>
<li><p>TRUE —手动部署的应用程序可能从磁盘加载。</p></li>
<li><p>FALSE-所有应用程序都必须来自源流式服务器。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><em>APPLICATIONSOURCEROOT</em></p></td>
<td align="left"><p>RTSP:// <em> URL </em> （用于动态包传递）</p>
<p>File:// <em> URL </em> 或 <em> UNC </em> （用于从文件包传递进行加载）</p></td>
<td align="left"><p>若要启用管理员或电子软件分发系统以确保在符合拓扑管理方案的情况下执行应用程序加载，允许覆盖应用程序 HREF 元素（源位置）的 OSD 基本代码。 如果值为 "" （默认值），则使用现有的 OSD 文件设置。</p>
<p>URL 有多个部分：</p>
<p>&lt;协议 &gt; // &lt; 服务器 &gt; ： &lt; 端口 &gt; / &lt; 路径 &gt; / &lt; ？查询 &gt; &lt; #fragment&gt;</p>
<p>UNC 路径有三个部分：</p>
<p>&amp;lt; computername &gt; &amp; lt; 共享文件夹 &gt; &amp; lt; 资源&gt;</p>
<p>如果 <em> </em> 在客户端上指定了 APPLICATIONSOURCEROOT 参数，则客户端将从 OSD 文件将 URL 或 UNC 路径中断到其构成部分，并将 osd 分区替换为相应的 <em> APPLICATIONSOURCEROOT </em> 部分。</p>
<div class="alert">
<strong>重要提示</strong><br/><p>在将 file://与 UNC 路径配合使用时，请确保使用正确的格式。 正确的格式为 file:// &amp; lt; server &gt; &amp; lt; share &gt; 。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><em>ICONSOURCEROOT</em></p></td>
<td align="left"><p><em>UNC</em></p>
<p>HTTP:// <em> url </em> 或 HTTPS:// <em> url</em></p></td>
<td align="left"><p>允许管理员为发布期间的序列化应用程序包指定图标检索的源位置。 图标源根目录支持 UNC 路径和 Url （HTTP 或 HTTPS）。 如果值为 "" （默认值），则使用现有的 OSD 文件设置。</p>
<p>URL 有多个部分：</p>
<p>&lt;协议 &gt; // &lt; 服务器 &gt; ： &lt; 端口 &gt; / &lt; 路径 &gt; / &lt; ？查询 &gt; &lt; #fragment&gt;</p>
<p>UNC 路径有三个部分：</p>
<p>&amp;lt; computername &gt; &amp; lt; 共享文件夹 &gt; &amp; lt; 资源&gt;</p>
<div class="alert">
<strong>重要提示</strong><br/><p>请确保使用 UNC 路径时使用正确的格式。 可接受的格式为 &amp; lt; 服务器 &gt; &amp; lt; 共享 &gt; 或 &lt; 驱动器号 &gt; ： &amp; lt; 文件夹 &gt; 。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><em>OSDSOURCEROOT</em></p></td>
<td align="left"><p><em>UNC</em></p>
<p>HTTP:// <em> url </em> 或 HTTPS:// <em> url</em></p></td>
<td align="left"><p>允许管理员为发布期间的应用程序包指定 OSD 文件检索的源位置。 OSD 源根目录支持 UNC 路径和 Url （HTTP 或 HTTPS）。 如果值为 "" （默认值），则使用现有的 OSD 文件设置。</p>
<p>URL 有多个部分：</p>
<p>&lt;协议 &gt; // &lt; 服务器 &gt; ： &lt; 端口 &gt; / &lt; 路径 &gt; / &lt; ？查询 &gt; &lt; #fragment&gt;</p>
<p>UNC 路径有三个部分：</p>
<p>&amp;lt; computername &gt; &amp; lt; 共享文件夹 &gt; &amp; lt; 资源&gt;</p>
<div class="alert">
<strong>重要提示</strong><br/><p>请确保使用 UNC 路径时使用正确的格式。 可接受的格式为 &amp; lt; 服务器 &gt; &amp; lt; 共享 &gt; 或 &lt; 驱动器号 &gt; ： &amp; lt; 文件夹 &gt; 。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><em>AUTOLOADONLOGIN</em></p>
<p><em>AUTOLOADONLAUNCH</em></p>
<p><em>AUTOLOADONREFRESH</em></p></td>
<td align="left"><p>[0 | 1]</p></td>
<td align="left"><p>定义启动应用程序自动加载的事件的 AutoLoad 触发器。 AutoLoad 隐式使用后台流，使应用程序能够完全加载到缓存中。</p>
<p>主功能块将尽快加载。 将在后台加载剩余功能块以启用前台操作，例如用户与应用程序交互，以获得优先级并提供最佳性能。</p>
<div class="alert">
<strong>注意</strong><br/><p><em>AUTOLOADTARGET </em> 参数确定自动加载的应用程序。 默认情况下，已使用的程序包将自动加载，除非 <em> </em> 已设置 AUTOLOADTARGET。</p>
</div>
<div>

</div>
<p>每个参数都影响加载行为，如下所示：</p>
<ul>
<li><p><em>AUTOLOADONLOGIN </em> -用户登录时开始加载。</p></li>
<li><p><em>AUTOLOADONLAUNCH </em> -用户启动应用程序时开始加载。</p></li>
<li><p><em>AUTOLOADONREFRESH </em> -在进行发布刷新时开始加载。</p></li>
</ul>
<p>这三个值可以组合。 在以下示例中，在用户登录时和发布刷新发生时均启用 AutoLoad 触发器：</p>
<p><em>AUTOLOADONLOGIN AUTOLOADONREFRESH</em></p>
<div class="alert">
<strong>注意</strong><br/><p>如果在首次安装时使用这些值配置客户端，则在下次用户注销并重新登录之前，不会触发 Autoload。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><em>AUTOLOADTARGET</em></p></td>
<td align="left"><p>尚</p>
<p>所有</p>
<p>PREVUSED</p></td>
<td align="left"><p>指示在任何给定的 AutoLoad 触发器出现时将自动加载的内容。</p>
<p>可能值：</p>
<ul>
<li><p>无-不自动加载，无论可能设置哪些触发器。</p></li>
<li><p>所有-如果启用了任何 AutoLoad 触发器，则会自动加载所有程序包，无论它们是否已启动。</p>
<div class="alert">
<strong>注意</strong><br/><p>通过使用 SFTMIME <strong> 添加程序包 </strong> 和 <strong> 配置程序包命令，为单个程序包配置此设置 </strong> 。 有关这些命令的详细信息，请参阅 <a href="sftmime--command-reference.md" data-raw-source="[SFTMIME Command Reference](sftmime--command-reference.md)"> SFTMIME 命令参考 </a> 。</p>
</div>
<div>

</div></li>
<li><p>PREVUSED-如果启用了任何 AutoLoad 触发器，则仅加载以前使用过程序包中至少一个应用程序（即启动或 precached）的程序包。</p></li>
</ul>
<div class="alert">
<strong>注意</strong><br/><p>当安装 app-v 客户端以使用只读缓存（例如，作为 VDI 服务器实现）时，必须将 <em> AUTOLOADTARGET </em> 参数设置为 NONE，以防止客户端尝试更新只读缓存中的应用程序。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><em>DOTIMEOUTMINUTES</em></p></td>
<td align="left"><p>29600（默认值）</p>
<p>1–1439998560分钟数（范围）</p></td>
<td align="left"><p>指示在断开连接的操作中可以使用的应用程序的分钟数。</p></td>
</tr>
<tr class="even">
<td align="left"><p><em>INSTALLDIR</em></p></td>
<td align="left"><p>&lt;路径名&gt;</p></td>
<td align="left"><p>指定 App-v 客户端的安装目录。</p>
<p>示例： INSTALLDIR = &quot; C:\Program Files\Microsoft Application Virtualization 客户端&quot;</p></td>
</tr>
<tr class="odd">
<td align="left"><p><em>OPTIN</em></p></td>
<td align="left"><p>真实</p>
<p>“”</p></td>
<td align="left"><p>Microsoft Application Virtualization 客户端组件将可通过 Microsoft 更新进行升级，可供公众使用更新。 在 Windows 操作系统上安装的 Microsoft Update 代理要求用户明确选择使用该服务。 对于设备上的所有应用程序，此选择性加入只需一次。 如果你已选择加入 Microsoft 更新，则设备上的 Microsoft Application Virtualization 组件将自动利用该服务。</p>
<p>对于命令行安装，默认情况下使用 "Microsoft Update" 默认选择退出（除非以前的应用程序已启用要选择加入的设备），因为需要手动选择 "Microsoft Update"。 因此，在命令行安装中，选择 "加入" 必须是显式的。 将命令行参数 OPTIN 设置 <em> </em> 为 TRUE 会强制设置 Microsoft 更新选择加入。</p></td>
</tr>
<tr class="even">
<td align="left"><p><em>REQUIREAUTHORIZATIONIFCACHED</em></p></td>
<td align="left"><p>TRUE</p>
<p>FALSE</p></td>
<td align="left"><p>指示是否始终需要授权，无论是否需要授权应用程序是否已在缓存中。</p>
<p>可能值：</p>
<ul>
<li><p>TRUE-应用程序始终必须在启动时获得授权。 对于 RTSP 流处理应用程序，将向服务器发送用户授权令牌以进行授权。 对于基于文件的应用程序，文件 Acl 决定用户是否可以访问应用程序。</p></li>
<li><p>FALSE —始终尝试连接到服务器。 如果无法建立与服务器的连接，客户端仍允许用户启动以前加载到缓存中的应用程序。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><em>SWICACHESIZE</em></p></td>
<td align="left"><p>缓存大小（以 MB 为单位）</p></td>
<td align="left"><p>指定客户端缓存的大小（以 mb 为单位）。 默认大小为 4096 MB，最大大小为 1048576 MB （1 TB）。 系统会在安装时检查可用空间，但不保留空间。</p>
<p>示例： <strong> SWICACHESIZE = &quot; 1024&quot;</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><em>SWIPUBSVRDISPLAY</em></p></td>
<td align="left"><p>显示名称</p></td>
<td align="left"><p>指定发布服务器的显示名称;<em>使用 SWIPUBSVRHOST 时需要 </em> 。</p>
<p>示例： <strong> SWIPUBSVRDISPLAY = &quot; 生产环境&quot;</strong></p></td>
</tr>
<tr class="odd">
<td align="left"><p><em>SWIPUBSVRTYPE</em></p></td>
<td align="left"><p>[HTTP |RTSP</p></td>
<td align="left"><p>指定发布服务器类型。 默认服务器类型是 Application Virtualization 服务器。 <strong>/Secure </strong> 开关不区分大小写。</p>
<ul>
<li><p>HTTP-标准 HTTP 服务器</p></li>
<li><p>HTTP <strong> /secure </strong> -增强的安全 HTTP 服务器</p></li>
<li><p>RTSP-应用程序虚拟化服务器</p></li>
<li><p>RTSP <strong> /secure </strong> -增强的安全应用程序虚拟化服务器</p></li>
</ul>
<p>示例： <strong> SWIPUBSVRTYPE = &quot; HTTP/secure&quot;</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><em>SWIPUBSVRHOST</em></p></td>
<td align="left"><p>IP 地址 | 主机名</p></td>
<td align="left"><p>指定应用程序虚拟化服务器的 IP 地址或解析为服务器的服务器的主机名&#39;s IP 地址;<em>使用 SWIPUBSVRDISPLAY 时需要 </em> 。</p>
<p>示例： <strong> SWIPUBSVRHOST = &quot; SERVER01&quot;</strong></p></td>
</tr>
<tr class="odd">
<td align="left"><p><em>SWIPUBSVRPORT</em></p></td>
<td align="left"><p>端口号</p></td>
<td align="left"><p>指定此应用程序虚拟化服务器用于侦听来自客户端的请求的逻辑端口（default = 554）。</p>
<ul>
<li><p>标准 HTTP 服务器-默认 = 80。</p></li>
<li><p>增强的安全 HTTP 服务器-默认 = 443。</p></li>
<li><p>应用程序虚拟化服务器-默认 = 554。</p></li>
<li><p>增强的安全应用程序虚拟化服务器-默认 = 322。</p></li>
</ul>
<p>示例： <strong> SWIPUBSVRPORT = &quot; 443&quot;</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><em>SWIPUBSVRPATH</em></p></td>
<td align="left"><p>路径名称</p></td>
<td align="left"><p>指定文件的发布服务器上定义文件类型关联（default =/）的位置;当 <em> SWIPUBSVRTYPE </em> 参数值为 HTTP 时是必需的。</p>
<p>示例： <strong> SWIPUBSVRPATH = &quot; /AppVirt/appsntypes.xml&quot;</strong></p></td>
</tr>
<tr class="odd">
<td align="left"><p><em>SWIPUBSVRREFRESH</em></p></td>
<td align="left"><p>[打开 |之外</p></td>
<td align="left"><p>指定当用户登录到客户端时，客户端是否自动查询文件类型关联和应用程序的发布服务器（default = ON）。</p>
<p>示例： <strong> SWIPUBSVRREFRESH = &quot; off&quot;</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><em>SWIGLOBALDATA</em></p></td>
<td align="left"><p>全局数据目录</p></td>
<td align="left"><p>指定将存储不特定于特定用户的数据的目录（默认值 = C:\Documents 和 Settings\All Users\Documents）。</p>
<p>示例： <strong> SWIGLOBALDATA = &quot; D:\Microsoft Application Virtualization Client\Global&quot;</strong></p></td>
</tr>
<tr class="odd">
<td align="left"><p><em>SWIUSERDATA</em></p></td>
<td align="left"><p>用户数据目录</p></td>
<td align="left"><p>指定将存储特定于特定用户的数据的目录（默认值 =% APPDATA%）。</p>
<p>示例： <strong> SWIUSERDATA = &quot; H:\Windows\Microsoft Application Virtualization 客户端&quot;</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><em>SWIFSDRIVE</em></p></td>
<td align="left"><p>首选驱动器号</p></td>
<td align="left"><p>对应于为虚拟驱动器选择的驱动器号。</p>
<p>示例： <strong> SWIFSDRIVE = &quot; S&quot;</strong></p></td>
</tr>
<tr class="odd">
<td align="left"><p><em>SYSTEMEVENTLOGLEVEL</em></p></td>
<td align="left"><p>0–4</p></td>
<td align="left"><p>指示日志消息写入 NT 事件日志的日志记录级别。 该值指示所记录内容的阈值，即记录的所有内容都等于或小于该值。 例如，值0x3 （警告）表示记录警告（0x3）、错误（0x2）和严重错误（0x1）。</p>
<p>可能值：</p>
<ul>
<li><p>0 = = 无</p></li>
<li><p>1 = = 严重</p></li>
<li><p>2 = = 错误</p></li>
<li><p>3 = = 警告</p></li>
<li><p>4 = = 信息</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><em>MINFREESPACEMB</em></p></td>
<td align="left"><p>以 MB 为单位</p></td>
<td align="left"><p>指定主机上必须提供的可用空间量（以兆字节为单位），才能增加缓存大小。 以下示例将配置客户端以确保磁盘上至少有 5 GB 的可用空间，然后再允许缓存大小增加。 默认值为安装时磁盘上的 5000 MB 可用空间。</p>
<p>示例： <strong> MINFREESPACEMB = &quot; 5000 &quot; （5 GB）</strong></p></td>
</tr>
<tr class="odd">
<td align="left"><p><em>KEEPCURRENTSETTINGS</em></p></td>
<td align="left"><p>[0 | 1]</p></td>
<td align="left"><p>在部署客户端之前应用注册表设置（例如，通过使用组策略）时使用。 当部署客户端时，将此参数设置为值1，以便它不会覆盖注册表设置。</p>
<div class="alert">
<strong>重要提示</strong><br/><p>如果设置为值1，将忽略以下客户端安装程序命令行参数：</p>
<p><strong>SWICACHESIZE </strong> 、 <strong> MINFREESPACEMB </strong> 、 <strong> ALLOWINDEPENDENTFILESTREAMING </strong> 、 <strong> APPLICATIONSOURCEROOT、ICONSOURCEROOT、OSDSOURCEROOT、 </strong> <strong> SYSTEMEVENTLOGLEVEL、 </strong> <strong> </strong> <strong> </strong> <strong> </strong> <strong> </strong> <strong> </strong> <strong> </strong> <strong> </strong> <strong> </strong> SWIGLOBALDATA、DOTIMEOUTMINUTES、SWIFSDRIVE、AUTOLOADTARGET、AUTOLOADTRIGGERS 和 SWIUSERDATA。</p>
<p>有关在安装后设置这些值的进一步信息，请参阅如何使用 "应用程序虚拟化（app-v）操作指南" （）中的 "使用命令行配置 App-v Client 注册表设置" <a href="https://go.microsoft.com/fwlink/?LinkId=122939" data-raw-source="[https://go.microsoft.com/fwlink/?LinkId=122939](https://go.microsoft.com/fwlink/?LinkId=122939)"> https://go.microsoft.com/fwlink/?LinkId=122939 </a> 。</p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



## 相关主题


[如何手动安装 Application Virtualization Client](how-to-manually-install-the-application-virtualization-client.md)

[如何升级 Application Virtualization Client](how-to-upgrade-the-application-virtualization-client.md)

[SFTMIME 命令引用](sftmime--command-reference.md)









