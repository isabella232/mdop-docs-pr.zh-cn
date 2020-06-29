---
title: 关于“部署”选项卡
description: 关于“部署”选项卡
author: dansimp
ms.assetid: 12891798-baa4-45a5-b845-b9505ab95633
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 147e8b1057c789d97087461a585fa3f365089784
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802427"
---
# 关于“部署”选项卡


使用应用程序虚拟化 Sequencer 控制台中的 "**部署**" 选项卡更改要序列化的应用程序的信息。 此选项卡包含以下元素。

## 服务器 URL


使用**服务器 URL**控件指定虚拟应用程序服务器配置设置。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">控件</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>协议</strong></p></td>
<td align="left"><p>使你能够选择将序列化应用程序包从虚拟应用程序服务器流式传输到应用程序虚拟化桌面客户端的协议。 可使用以下协议：</p>
<ul>
<li><p><strong>RTSP </strong> -默认情况下，它指定实时流协议控制支持虚拟化的应用程序的交换。</p></li>
<li><p><strong>RTSPS </strong> -指定具有传输层安全性的实时流协议控制序列化应用程序包的交换。</p></li>
<li><p><strong>文件 </strong> -指定序列化的应用程序将从文件共享流出。</p></li>
<li><p><strong>HTTPS </strong> —指定安全超文本传输协议控制程序包的交换。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><strong>主机</strong></p></td>
<td align="left"><p>使你能够选择虚拟应用程序服务器或虚拟应用程序服务器组前面的负载平衡器，这些服务器会将软件包传输到应用程序虚拟化桌面客户端。 必须完成此项才能创建顺序应用程序包，但你可以从默认的% SFT_SOFTGRIDSERVER% 环境变量更改为虚拟应用程序服务器的实际主机名或 IP 地址。</p>
<div class="alert">
<strong>注意</strong><br/><p>如果您选择不指定静态主机名或 IP 地址，请在每个应用程序虚拟化桌面客户端上设置一个名为 SFT_SOFTGRIDSERVER 的环境变量。 它的值必须是虚拟应用程序服务器或负载平衡器的主机名或 IP 地址，该客户端&#39;s 应用程序源。 你应该将此环境变量设置为系统变量，而不是用户变量。 在分配此变量期间，在此计算机上运行的任何应用程序虚拟化桌面客户端会话必须关闭，然后再打开，以便恢复的会话将知道它的新应用程序源。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>端口</strong></p></td>
<td align="left"><p>使你能够指定虚拟应用程序服务器或负载平衡器将在其上侦听应用程序虚拟化桌面客户端&#39;程序包请求的端口。 创建程序包需要此信息，但你可以对其进行更改。 默认端口为554。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>路径</strong></p></td>
<td align="left"><p>使你能够指定存储软件包的虚拟应用服务器上的相对路径，以及将从该程序包传送数据包的位置。 如果将 SFT 文件存储在内容子目录中，则创建程序包需要此信息;否则，不需要此信息。</p></td>
</tr>
</tbody>
</table>



## 操作系统


使用**操作系统**控件指定应用程序的操作系统要求。 如果应用程序虚拟化桌面客户端无法支持任何选定的操作系统，应用程序将无法启动。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">控件</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>可用操作系统</strong></p></td>
<td align="left"><p>显示可支持程序包中的应用程序的操作系统列表。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>所选操作系统</strong></p></td>
<td align="left"><p>显示支持程序包中的应用程序的选定操作系统的列表。</p></td>
</tr>
</tbody>
</table>



## 输出选项


使用 "**输出" 选项**控件指定要安装的应用程序的输出选项。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">控件</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>压缩算法</strong></p></td>
<td align="left"><p>用于选择压缩 SFT 文件以通过网络进行流式传输的方法。 选择下列压缩方法之一：</p>
<ul>
<li><p><strong>已压缩 </strong> —指定将 SFT 文件压缩为 <a href="https://go.microsoft.com/fwlink/?LinkId=111475" data-raw-source="[ZLIB](https://go.microsoft.com/fwlink/?LinkId=111475)"> ZLIB </a> 格式。</p></li>
<li><p><strong>未压缩 </strong> -默认情况下; 指定不压缩 SFT 文件。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><strong>强制实施安全描述符</strong></p></td>
<td align="left"><p>选择以在将程序包部署到客户端后，在其中执行应用程序的安全描述符。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>生成 Microsoft Windows Installer （MSI）程序包</strong></p></td>
<td align="left"><p>选择以使用 Windows Installer 安装或部署序列化的应用程序包。 如果你使用 sequencer 进行了任何更改，则 Windows Installer 文件中将不包含这些更改。 将始终使用保存在硬盘上的 sft 文件创建 Windows Installer 文件。</p></td>
</tr>
</tbody>
</table>



## 相关主题


[如何更改部署属性](how-to-change-deployment-properties.md)

[Sequencer 控制台](sequencer-console.md)









