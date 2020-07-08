---
title: 如何将网络设置应用于 MED-V 工作区
description: 如何将网络设置应用于 MED-V 工作区
author: dansimp
ms.assetid: 641f46b3-a56f-478a-823b-1d90aa1716b3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 5a13227518945e74be9e4b3772af97eadbce3fc4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803984"
---
# 如何将网络设置应用于 MED-V 工作区


管理员可以定义每个 MED-V 工作区的网络设置。

所有网络设置均在 "**网络**" 选项卡上的 "**策略**" 模块中配置。

**将网络设置应用到 MED-V 工作区**

1.  单击要配置的 MED-V 工作区。

2.  在 "**网络**" 窗格中，按下表中所述配置设置。

3.  在 "**策略**" 菜单上，选择 "**提交**"。

**MED-V 工作区网络属性**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">属性</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>TCP/IP 属性</p></td>
<td align="left"><ul>
<li><p><strong>使用主机的 IP 地址（NAT） </strong> ，工作区将使用 NAT 来共享托管通信的主机 IP。</p></li>
<li><p><strong>使用不同于主机的 IP 地址（网桥） </strong> -med-v 工作区将拥有自己的网络地址，通常通过 DHCP 获得。</p></li>
</ul>
<p><strong> </strong> 当主机具有多个适配器时，选中 "将多个适配器映射到工作区" 复选框。 当主机在使用不同适配器的不同网络之间移动时，建议使用此配置。</p></td>
</tr>
<tr class="even">
<td align="left"><p>DNS 服务器</p></td>
<td align="left"><ul>
<li><p><strong>不更改 </strong> -不会更改在 med-v 工作区虚拟机中设置的 DNS 设置。</p></li>
<li><p><strong>使用主机的 DNS 地址 </strong> -将同步 "med-v" 工作区 dns 设置以匹配主机的设置。 DNS 同步是动态的。 它将定期与主机进行同步，以便在主机上更改它时，它将在 MED-V 工作区中动态更改。</p></li>
<li><p><strong>使用特定的 DNS 地址 </strong> -med-v 工作区将根据指定使用特定的 dns。</p>
<p>在 <strong> 主要 </strong> 和 <strong> 辅助字段中 </strong> ，输入主要和辅助 DNS 地址。</p>
<p>选中 " <strong> 追加主机的 DNS 地址" </strong> 复选框以将主机追加到已配置的 DNS 地址。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>分配 DNS 后缀</p></td>
<td align="left"><ul>
<li><p><strong>分配下列后缀 </strong> -选中此复选框以分配特定的 DNS 后缀; 在 "" 框中，输入用逗号分隔的后缀或多个后缀。</p></li>
<li><p><strong>"附加主机后缀" </strong> -选中此复选框以将主机后缀追加到 DNS 地址。</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

## 相关主题


[创建 MED-V 工作区](creating-a-med-v-workspacemedv-10-sp1.md)

[使用 MED-V 管理控制台用户界面](using-the-med-v-management-console-user-interface.md)

 

 





