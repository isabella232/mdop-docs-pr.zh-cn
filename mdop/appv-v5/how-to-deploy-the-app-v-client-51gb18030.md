---
title: 如何部署 App-V Client
description: 如何部署 App-V Client
author: dansimp
ms.assetid: 981f57c9-56c3-45da-8261-0972bfad3e5b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/01/2016
ms.openlocfilehash: ea216f6b86820f752e0c0ac693470eac72cb847a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798467"
---
# 如何部署 App-V Client


使用以下过程安装 Microsoft Application Virtualization （App-v）5.1 客户端和远程桌面服务客户端。 必须安装与目标计算机的操作系统匹配的客户端版本。

<a href="" id="bkmk-clt-install-prereqs"></a>**开始之前应执行的操作**

1. 查看和安装软件必备条件：

   安装与要安装的 App-v 版本对应的必备软件：

   -   [关于 App-V 5.1](about-app-v-51.md)

   -   [App-V 5.1 先决条件](app-v-51-prerequisites.md)

2. 查看适用于你的安装的客户端共存和不受支持的方案：

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <tbody>
   <tr class="odd">
   <td align="left"><p>部署共存的应用程序-V 客户端</p></td>
   <td align="left"><p><a href="planning-for-the-app-v-51-sequencer-and-client-deployment.md" data-raw-source="[Planning for the App-V 5.1 Sequencer and Client Deployment](planning-for-the-app-v-51-sequencer-and-client-deployment.md)">计划 App-V 5.1 Sequencer 和 Client 部署</a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>不受支持或受限的安装方案</p></td>
   <td align="left"><p>请参阅 <a href="app-v-51-supported-configurations.md" data-raw-source="[App-V 5.1 Supported Configurations](app-v-51-supported-configurations.md)"> 应用 V 5.1 支持的配置中的客户端部分</a></p></td>
   </tr>
   </tbody>
   </table>



3. 查看客户端注册表、日志和疑难解答信息的位置：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p>客户端注册信息</p></td>
<td align="left"><ul>
<li><p>默认情况下，在安装 app-v 5.1 客户端之后，客户端信息将存储在注册表中的以下注册表项中：</p>
<p><strong>HKEY_LOCAL_MACHINE \ 软件 \ MICROSOFT \ APPV \ 客户端</strong></p></li>
<li><p>将虚拟化程序包部署到运行 App-v 客户端的计算机时，关联的程序包数据存储在以下位置：</p>
<p><strong>C： \ ProgramData \ App-V</strong></p>
<p>但是，你可以通过以下注册表项重新配置此位置：</p>
<p><strong>HKEY_LOCAL_MACHINE \ 软件 \ MICROSOFT \ 软件 \ MICROSOFT \ APPV \ 客户端 \ 流 \ PACKAGEINSTALLATIONROOT</strong></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>客户端日志文件</p></td>
<td align="left"><ul>
<li><p>对于与 App-v 5.1 客户端相关联的日志文件信息，请在以下日志中搜索：</p>
<p><strong>事件日志/应用程序和服务日志/Microsoft/AppV</strong></p></li>
<li><p>在 App-v 5.0 SP3 中，某些日志已合并并移动到以下位置：</p>
<p><strong>事件日志/应用程序和服务日志/Microsoft/AppV/ServiceLog</strong></p>
<p>有关已移动日志的列表，请参阅 <a href="about-app-v-50-sp3.md#bkmk-event-logs-moved" data-raw-source="[About App-V 5.0 SP3](about-app-v-50-sp3.md#bkmk-event-logs-moved)"> 关于 App-V 5.0 SP3 </a> 。</p></li>
<li><p>当前存储在运行 App-v 5.1 客户端的计算机上的程序包将保存到以下位置：</p>
<p><strong>C:\ProgramData\App-V &amp; lt; 程序包 id &gt; &amp; lt; 版本 id&gt;</strong></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>客户端安装疑难解答信息</p></td>
<td align="left"><p>请参阅 <strong> % temp% 文件夹中的错误日志 </strong> 。 若要查看日志文件，请单击 " <strong> 开始 </strong> "，键入 <strong> % temp% </strong> ，然后查找 " <strong> appv_ 日志" </strong> 。</p></td>
</tr>
</tbody>
</table>



**安装 app-v 5.1 客户端**

1.  将 app-v 5.1 客户端安装文件复制到将在其上安装的计算机。 从以下客户端类型中进行选择：

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">客户端类型</th>
    <th align="left">要使用的文件</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>客户端的标准版本</p></td>
    <td align="left"><p><strong>appv_client_setup.exe</strong></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>客户端的远程桌面服务版本</p></td>
    <td align="left"><p><strong>appv_client_setup_rds.exe</strong></p></td>
    </tr>
    </tbody>
    </table>



2.  双击安装文件，然后单击 "**安装**"。 安装开始之前，安装程序会检查计算机上是否缺少任何缺少[的 app-v 5.1 先决条件](app-v-51-prerequisites.md)。

3.  查看并接受软件许可条款，选择是否使用 Microsoft 更新以及是否参与 Microsoft 客户体验改善计划，并单击 "**安装**"。

4.  在 "**安装成功完成**" 页面上，单击 "**关闭**"。

    安装过程将在**程序**中为 app-v 客户端创建以下条目：

    -   **.exe**

    -   **.msi**

    -   **语言包**

        **注意**  
        安装后，仅可卸载 .exe 文件。



**使用脚本安装 app-v 5.1 客户端**

1. 在目标计算机上安装所有必需的必备软件。 [在开始之前，请查看要执行的操作](#bkmk-clt-install-prereqs)。 如果使用 .msi 文件安装客户端，则如果缺少任何先决条件，安装将失败。

2. 若要使用脚本安装 App-v 5.1 客户端，请将以下参数与**appv\_client\_setup.exe**结合使用。

   **注意**  
   除了 **/log**参数外，客户端 Windows Installer （.msi）支持相同的开关集。

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <tbody>
   <tr class="odd">
   <td align="left"><p>/INSTALLDIR</p></td>
   <td align="left"><p>指定安装目录。 示例用法： <strong> /INSTALLDIR = C:\Program Files\AppV 客户端</strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>/CEIPOPTIN</p></td>
   <td align="left"><p>允许参与客户体验改善计划。 示例用法： <strong> /CEIPOPTIN = [0 | 1]</strong></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>/MUOPTIN</p></td>
   <td align="left"><p>启用 Microsoft 更新。 示例用法： <strong> /MUOPTIN = [0 | 1]</strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>/PACKAGEINSTALLATIONROOT</p></td>
   <td align="left"><p>指定要在其中安装所有新应用程序和更新的目录。 示例用法： <strong> /PACKAGEINSTALLATIONROOT =&#39;C:\App-V 程序包&#39;</strong></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>/PACKAGESOURCEROOT</p></td>
   <td align="left"><p>替代用于下载软件包内容的源位置。 示例用法： <strong> /PACKAGESOURCEROOT =&#39;<a href="http://packageStore" data-raw-source="http://packageStore"> http://packageStore </a>&#39;</strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>/AUTOLOAD</p></td>
   <td align="left"><p>指定在特定计算机上由 app-v 5.1 加载新程序包的方式。 启用以下选项： [1];自动加载所有程序包 [2];或自动加载 "无程序包" [0]。 <strong>示例用法：/AUTOLOAD = [0 | 1 | 2]</strong></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>/SHAREDCONTENTSTOREMODE</p></td>
   <td align="left"><p>指定流式处理的程序包内容将不会保存到本地硬盘。 示例用法： <strong> /SHAREDCONTENTSTOREMODE = [0 | 1]</strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>/MIGRATIONMODE</p></td>
   <td align="left"><p>允许 App-v 5.1 客户端修改与使用早期版本创建的程序包相关联的快捷方式和 FTAs。 示例用法： <strong> /MIGRATIONMODE = [0 | 1]</strong></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>/ENABLEPACKAGESCRIPTS</p></td>
   <td align="left"><p>启用应运行的程序包清单文件或配置文件中定义的脚本。 示例用法： <strong> /ENABLEPACKAGESCRIPTS = [0 | 1]</strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>/ROAMINGREGISTRYEXCLUSIONS</p></td>
   <td align="left"><p>指定将不随用户配置文件漫游的注册表路径。 示例用法： <strong> /ROAMINGREGISTRYEXCLUSIONS = software\classes; software\clients</strong></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>/ROAMINGFILEEXCLUSIONS</p></td>
   <td align="left"><p>指定相对于% userprofile% 的文件路径，不要与用户&#39;s 配置文件一起漫游。 示例用法： <strong> /ROAMINGFILEEXCLUSIONS &#39;桌面; "我的图片"&#39;</strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>/S [1-5] PUBLISHINGSERVERNAME</p></td>
   <td align="left"><p>显示发布服务器的名称。 示例用法： <strong> /S2PUBLISHINGSERVERNAME = MyPublishingServer</strong></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>/S [1-5] PUBLISHINGSERVERURL</p></td>
   <td align="left"><p>显示发布服务器的 URL。 示例用法： <strong> /S2PUBLISHINGSERVERURL = \pubserver</strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>/S [1-5] GLOBALREFRESHENABLED-</p></td>
   <td align="left"><p>启用全局发布刷新。 示例用法： <strong> /S2GLOBALREFRESHENABLED = [0 | 1]</strong></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>/S [1-5] GLOBALREFRESHONLOGON</p></td>
   <td align="left"><p>当用户登录时启动全局发布刷新。 示例用法： <strong> /S2LOGONREFRESH = [0 | 1]</strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>/S [1-5] GLOBALREFRESHINTERVAL-</p></td>
   <td align="left"><p>指定发布刷新间隔，其中 <strong> 0 </strong> 表示不定期刷新。 示例用法： <strong> /S2PERIODICREFRESHINTERVAL = [0-744]</strong></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>/S [1-5] GLOBALREFRESHINTERVALUNIT</p></td>
   <td align="left"><p>指定间隔单位（小时 [0]，天 [1]）。 示例用法： <strong> /S2GLOBALREFRESHINTERVALUNIT = [0 | 1]</strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>/S [1-5] USERREFRESHENABLED</p></td>
   <td align="left"><p>启用用户发布刷新。 示例用法： <strong> /S2USERREFRESHENABLED = [0 | 1]</strong></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>/S [1-5] USERREFRESHONLOGON</p></td>
   <td align="left"><p>用户登录时启动用户发布刷新。 示例用法： <strong> /S2LOGONREFRESH = [0 | 1]</strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>/S [1-5] USERREFRESHINTERVAL-</p></td>
   <td align="left"><p>指定发布刷新间隔，其中 <strong> 0 </strong> 表示不定期刷新。 示例用法： <strong> /S2PERIODICREFRESHINTERVAL = [0-744]</strong></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>/S [1-5] USERREFRESHINTERVALUNIT</p></td>
   <td align="left"><p>指定间隔单位（小时 [0]，天 [1]）。 示例用法： <strong> /S2USERREFRESHINTERVALUNIT = [0 | 1]</strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>/Log</p></td>
   <td align="left"><p>指定保存日志信息的位置。 默认位置为% Temp%。 示例用法： <strong> /Log C:\logs\log.log</strong></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>/q</p></td>
   <td align="left"><p>指定无人参与安装。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>/REPAIR</p></td>
   <td align="left"><p>修复以前的客户端安装。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>/NORESTART</p></td>
   <td align="left"><p>阻止计算机在客户端安装后重新启动。</p>
   <p>该参数可防止最终用户计算机在安装每个更新后重新启动，并允许你在方便时计划重启。 例如，你可以安装 app-v 5.1，然后安装修补程序包 Y，而无需在安装 Service Pack 后重新启动。 安装完成后，必须重新启动才能开始使用 app-v。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>/UNINSTALL</p></td>
   <td align="left"><p>卸载客户端。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>/ACCEPTEULA</p></td>
   <td align="left"><p>接受许可协议。 这是无人参与安装所必需的。 示例用法： <strong> /ACCEPTEULA </strong> 或 <strong> /ACCEPTEULA = 1 </strong> 。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>/LAYOUT</p></td>
   <td align="left"><p>指定关联的布局操作。 它还将 Windows Installer （.msi）和脚本文件提取到文件夹中，但不安装 app-v 5.1。 不应为任何值。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>/LAYOUTDIR</p></td>
   <td align="left"><p>指定布局目录。 需要字符串值。 示例用法： <strong> /LAYOUTDIR = "C:\Application Virtualization 客户端" </strong> 。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>/？、/h、/help</p></td>
   <td align="left"><p>请求有关以前的安装参数的帮助。</p></td>
   </tr>
   </tbody>
   </table>



**使用 Windows Installer （.msi）文件安装 App-v 5.1 客户端**

1.  在目标计算机上安装所需的先决条件。 [在开始之前，请查看要执行的操作](#bkmk-clt-install-prereqs)。 如果未满足任何先决条件，安装将失败。

2.  在使用 App-v 5.1 Windows Installer （.msi）文件安装客户端之前，请确保目标计算机没有任何挂起的重启。 Windows Installer 文件不会标记待重启。

3.  将以下 Windows Installer 文件之一部署到目标计算机。 你指定的文件必须与目标计算机的配置相匹配。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">部署类型</th>
    <th align="left">部署此文件</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>计算机运行的是32位 Microsoft Windows 操作系统</p></td>
    <td align="left"><p>appv_client_MSI_x86.msi</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>计算机运行的是64位 Microsoft Windows 操作系统</p></td>
    <td align="left"><p>appv_client_MSI_x64.msi</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>你正在部署 app-v 5.1 远程桌面服务客户端</p></td>
    <td align="left"><p>appv_client_rds_MSI_x64.msi</p></td>
    </tr>
    </tbody>
    </table>



4.  使用下表中的信息，根据目标计算机所需的语言选择要安装的相应语言包 **。** 表中的**xxxx**指语言包的目标区域设置。

    **开始之前应了解的事项：**

    -   标准 App-v 5.1 客户端和 app-v 5.1 客户端的远程桌面服务版本均共有语言包。

    -   如果您使用 **.exe**安装 app-v 5.1 客户端，安装程序将仅部署与目标计算机上运行的操作系统匹配的语言包。

    -   若要在目标计算机上部署其他语言包，请使用**Windows Installer （.msi）文件中的步骤安装 app-v 5.1 客户端**。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">部署类型</th>
    <th align="left">部署此文件</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>计算机运行的是32位 Microsoft Windows 操作系统</p></td>
    <td align="left"><p>appv_client_LP_xxxx_ x86.msi</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>计算机运行的是64位 Microsoft Windows 操作系统</p></td>
    <td align="left"><p>appv_client_LP_xxxx_ x64.msi</p></td>
    </tr>
    </tbody>
    </table>



~~~
**Got a suggestion for App-V**? Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization). **Got an App-V issue?** Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).
~~~

## 相关主题


[部署 App-V 5.1](deploying-app-v-51.md)

[关于 Client 配置设置](about-client-configuration-settings51.md)

[如何卸载 App-V 5.1 Client](how-to-uninstall-the-app-v-51-client.md)









