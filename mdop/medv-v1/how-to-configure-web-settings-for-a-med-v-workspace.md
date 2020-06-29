---
title: 如何为 MED-V 工作区配置 Web 设置
description: 如何为 MED-V 工作区配置 Web 设置
author: dansimp
ms.assetid: 9a6cd28f-7e4f-468f-830a-7b1d9abd3af3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 770d3fa9a03c9754db86ca348390d0b916de6d5d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804094"
---
# 如何为 MED-V 工作区配置 Web 设置


仅可在较早版本的 Internet Explorer 中显示且不存在于主机操作系统中的网站可以在早期版本的 Internet Explorer 中在 MED-V 工作区中查看。 用户无需在 MED-V 工作区中打开浏览器即可查看指定的网站。 用户可以打开主机上的浏览器，并自动重定向到 MED-V 工作区，反之亦然。

以下过程介绍了如何为 MED-V 工作区设置 Web 浏览规则列表。 这些规则中包含的所有网站均可在 MED-V 工作区或主机上浏览，如管理员定义。 在规则中未定义的所有网站从请求它们的环境中进行浏览。 但是，你也可以将它们配置为组，以便在 MED-V 工作区或主机中进行浏览。

**注意**  
Web 设置仅应用于 Internet Explorer 和其他任何浏览器。



所有 Web 设置均在 " **web** " 选项卡上的 "**策略**" 模块中配置。

## 如何配置 MED-V 工作区的 Web 设置


**配置 MED-V 工作区的 Web 设置**

1.  单击要配置的 MED-V 工作区。

2.  选中 "**浏览下表中定义的 url 列表**" 复选框，以便在用户浏览到符合指定 Web 规则的 URL 时，将用户重定向到 med-v 工作区或主机中的浏览器。

3.  单击下列操作之一：

    -   **在工作区中**-重定向到 med-v 工作区中的浏览器。

    -   **在主机中**-重定向到主机上的浏览器。

4.  选中 "**浏览所有其他 url** " 复选框以将所有从 Web 规则中排除的 url 重定向到主机或 med-v 工作区。

5.  单击下列操作之一：

    -   **在工作区中**-将所有其他 url 重定向到 med-v 工作区中的浏览器。

    -   **在主机中**，将所有其他 url 重定向到主机上的浏览器。

6.  在 "**策略**" 菜单上，选择 "**提交**"。

## 如何添加 Web 规则


**添加 Web 规则**

1.  选中 "**浏览下表中定义的 url 列表**" 复选框以启用 Web 浏览规则。

2.  单击**添加**。

    添加了新的 Web 规则。

3.  按下表所述配置 Web 规则属性。

4.  在 "**策略**" 菜单上，选择 "**提交**"。

**MED-V 工作区 Web 属性**

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
<td align="left"><p>类型</p></td>
<td align="left"><ul>
<li><p><strong>域后缀 </strong> -访问以 "Value" 属性中指定的后缀结尾的任何主机地址 <strong> </strong> ，并根据 Web 浏览中的选项设置 <strong> </strong> 。</p></li>
<li><p><strong>IP 前缀 </strong> ——在 Value 属性中指定的前缀范围内访问任何完整或部分 IP 地址 <strong> </strong> ，并根据 Web 浏览中的选项设置 <strong> </strong> 。</p></li>
<li><p><strong>所有本地地址 </strong> —访问所有不带 &#39; 的地址。 &#39; 并根据 Web 浏览中设置的选项进行设置。 <strong> </strong></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>值</p></td>
<td align="left"><ul>
<li><p>如果在 <strong> </strong> "类型" 属性中选择了 "域后缀" <strong> </strong> ，请输入域后缀。</p>
<div class="alert">
<strong>注意</strong><br/><ul>
<li><p>不要 &quot; * &quot; 在后缀前输入。</p></li>
<li><p>域后缀也支持别名。</p></li>
</ul>
</div>
<div>

</div></li>
<li><p>如果在 "类型" 属性中选择了 "IP 前缀 <strong> </strong> "，请输入完整或部分 ip 地址。</p></li>
</ul></td>
</tr>
</tbody>
</table>



## 如何删除 Web 规则


**删除 Web 规则**

1.  在 " **web** " 窗格中，选择要删除的 Web 规则。

2.  单击 "**删除**"。

    Web 规则已删除。

## 相关主题


[使用 MED-V 管理控制台用户界面](using-the-med-v-management-console-user-interface.md)

[创建 MED-V 工作区](creating-a-med-v-workspacemedv-10-sp1.md)









