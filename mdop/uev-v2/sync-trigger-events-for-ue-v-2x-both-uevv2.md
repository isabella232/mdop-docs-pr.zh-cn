---
title: UE-V 2.x 的同步触发器事件
description: UE-V 2.x 的同步触发器事件
author: dansimp
ms.assetid: 4ed71a13-6a4f-4376-996f-74b126536bbc
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f3e89a0370790e7f462b2f469792128dba033460
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804040"
---
# UE-V 2.x 的同步触发器事件


Microsoft 用户体验虚拟化（UE-V）2.0、2.1 和 2.1 SP1 使你可以在所有加入域的设备上同步你的应用程序和 Windows 设置。 *同步触发器事件*定义了 ue-v Agent 何时将这些设置与设置存储位置同步。 UE-V 2 引入了一个名为*SyncProvider*的新*同步方法*。 有关同步方法配置的详细信息，请参阅[ue-v 2. x 的同步方法](sync-methods-for-ue-v-2x-both-uevv2.md)。

## UE-V 2 同步触发事件


下表介绍了经典应用程序和 Windows 设置的触发器事件。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>UE-V 2 触发器事件</strong></p></td>
<td align="left"><p><strong>Powerschool = SyncProvider</strong></p></td>
<td align="left"><p><strong>Powerschool = None</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>Windows 登录</strong></p></td>
<td align="left"><ul>
<li><p>将从设置存储位置将应用程序和 Windows 设置导入到本地缓存。</p></li>
<li><p><a href="https://technet.microsoft.com/library/dn458932.aspx#autosyncsettings2" data-raw-source="[Asynchronous Windows settings](https://technet.microsoft.com/library/dn458932.aspx#autosyncsettings2)">已应用异步 Windows 设置 </a> 。</p></li>
<li><p>将在下次 Windows 登录期间应用同步 Windows 设置。</p></li>
<li><p>应用程序设置将在应用程序启动时应用。</p></li>
</ul></td>
<td align="left"><ul>
<li><p>从 "设置" 存储位置直接读取 "应用程序" 和 "Windows 设置"。</p></li>
<li><p>应用了异步和同步 Windows 设置。</p></li>
<li><p>应用程序设置将在应用程序启动时应用。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Windows 注销</strong></p></td>
<td align="left"><p>将更改存储在本地，并将异步和同步 Windows 设置缓存和复制到设置存储位置服务器（如果可用）</p></td>
<td align="left"><p>将更改存储到异步和同步 Windows 设置存储位置</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>Windows Connect （RDP）/解锁</strong></p></td>
<td align="left"><p>将任何异步 Windows 设置从 "设置存储位置" 同步到 "本地缓存" （如果可用）。</p>
<p>应用缓存的 Windows 设置</p></td>
<td align="left"><p>从设置存储位置下载和应用异步 windows 设置</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Windows 断开连接（RDP）/锁</strong></p></td>
<td align="left"><p>将异步 Windows 设置更改存储到本地缓存。</p>
<p>将本地缓存中的任何异步 Windows 设置同步到设置存储位置（如果可用）</p></td>
<td align="left"><p>将异步 Windows 设置更改存储到设置存储位置</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>应用程序启动</strong></p></td>
<td align="left"><p>应用程序启动时从本地缓存应用应用程序设置</p></td>
<td align="left"><p>应用程序启动时从设置存储位置应用应用程序设置</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>应用程序关闭</strong></p></td>
<td align="left"><p>将任何应用程序设置更改存储到本地缓存并将设置复制到设置存储位置（如果可用）</p></td>
<td align="left"><p>将任何应用程序设置更改存储到设置存储位置</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>从公司设置中心运行同步控制器计划任务或 "立即同步"</strong></p>
<p></p></td>
<td align="left"><p>应用程序和 Windows 设置在设置存储位置和本地缓存之间同步。</p>
<div class="alert">
<strong>注意</strong><br/><p>在应用程序关闭之前，不会将设置更改缓存到本地。 此触发器将不会导出对当前运行的应用程序所做的更改。</p>
<p>对于 Windows 设置，这意味着不会在本地和导出任何更改，直到下一个锁定（异步）或注销（异步和同步）。</p>
</div>
<div>

</div>
<p>在以下情况下应用设置：</p>
<ul>
<li><p>将直接应用异步 Windows 设置。</p></li>
<li><p>应用程序设置在应用程序启动时应用。</p></li>
<li><p>在下次 Windows 登录期间，将应用异步和同步 Windows 设置。</p></li>
<li><p>Windows 应用（AppX）设置将在下一次刷新期间应用。 <a href="https://technet.microsoft.com/library/dn458944.aspx" data-raw-source="[Monitor Application Settings](https://technet.microsoft.com/library/dn458944.aspx)">有关详细信息，请参阅监视应用程序设置 </a> 。</p></li>
</ul></td>
<td align="left"><p>NA</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>在远程存储上更新的异步设置 *</strong></p></td>
<td align="left"><p>从缓存加载和应用新的异步设置。</p></td>
<td align="left"><p>从中央服务器加载和应用设置</p></td>
</tr>
</tbody>
</table>








## 相关主题


[UE-V 2.x 的技术参考](technical-reference-for-ue-v-2x-both-uevv2.md)

[更改 UE-V 2 x 计划任务的频率](changing-the-frequency-of-ue-v-2x-scheduled-tasks-both-uevv2.md)

[选择 UE-V 2 的配置方法。](https://technet.microsoft.com/library/dn458891.aspx#config)









