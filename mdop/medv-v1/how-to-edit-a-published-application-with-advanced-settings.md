---
title: 如何使用高级设置编辑已发布的应用程序
description: 如何使用高级设置编辑已发布的应用程序
author: dansimp
ms.assetid: 06a79049-9ce9-490f-aad7-fd4fdf185590
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 843aebb38f54959f209e742b398e3979acac3334
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804080"
---
# 如何使用高级设置编辑已发布的应用程序


添加并配置已发布的应用程序后，可以编辑已发布的应用程序，并可配置其他高级设置。

**使用高级设置编辑已发布的应用程序**

1.  在 "**应用程序**" 窗格中，添加和配置已发布的应用程序。

2.  选择要编辑的已发布应用程序。

3.  单击**编辑**。

4.  在 "**已发布的应用程序**" 对话框中，按下表中所述配置参数。

5.  单击“确定”****。

6.  在 "**策略**" 菜单上，选择 "**提交**"。

**编辑已发布的应用程序属性**

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
<td align="left"><p>显示名称</p></td>
<td align="left"><p>用户&#39;s Windows "开始" 菜单中的快捷方式的名称。</p>
<div class="alert">
<strong>注意</strong><br/><p>显示名称 <strong> 不 </strong> 区分大小写。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p>描述</p></td>
<td align="left"><p>已发布菜单的说明。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>开始于</p></td>
<td align="left"><p>从其启动应用程序的目录。</p>
<div class="alert">
<strong>注意</strong><br/><p>路径不需要包含引号。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p>命令行</p></td>
<td align="left"><p>用于从 MED-V 工作区中运行应用程序的命令。</p>
<p>完整路径是必需的，并且参数可以与任何其他 Windows 命令中类似的方式传递到应用程序。</p>
<p>在域配置中，共享驱动器通常位于所有域计算机映射到的服务器上。 应在此处映射目录，如果它是需要用户身份验证的文件夹，则 <strong> 必须选中 "使用 med-v 凭据运行此应用程序" </strong> 复选框。</p>
<p>在 revertible med-v 工作区中，你可以使用 MapNetworkDrive 语法： &quot; <em> MapNetworkDrive &lt; 驱动器 &gt; &lt; 路径 &gt; </em> &quot; （例如 &quot; <em> MapNetworkDrive t： \tux\data） </em> &quot; 映射网络驱动器。</p>
<p>例如，若要发布 Windows 资源管理器，请使用以下语法： &quot; <em> c： &amp; q; 或 &quot; c：\windows </em> &quot; 。</p>
<div class="alert">
<strong>注意</strong><br/><p>若要进行名称解析，您需要执行下列操作之一：</p>
</div>
<div>

</div>
<ul>
<li><p>在 "基本 MED-V-V" 工作区映像中配置 DNS。</p></li>
<li><p>验证主机中是否定义了 DNS 解析，并将其配置为使用主机 DNS。</p></li>
<li><p>使用 IP 定义网络驱动器。</p></li>
</ul>
<div class="alert">
<strong>注意</strong><br/><p>如果路径中包含空格，则整个路径必须位于引号内。</p>
</div>
<div>

</div>
<div class="alert">
<strong>注意</strong><br/><p>路径不应以反斜杠（）结尾。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p>在主机 Windows "开始" 菜单中添加快捷方式</p></td>
<td align="left"><p>选中此复选框可在用户&#39;s Windows "开始" 菜单中创建应用程序的快捷方式。</p></td>
</tr>
<tr class="even">
<td align="left"><p>启动工作区时启动此应用程序</p></td>
<td align="left"><p>选中此复选框以在 MED-V 工作区启动时自动运行应用程序。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>使用 MED-V 凭据运行此应用程序</p></td>
<td align="left"><p>选中此复选框以使用 MED-V 凭据（而不是为应用程序设置的凭据）对请求用户名和密码的应用程序进行身份验证。</p>
<div class="alert">
<strong>注意</strong><br/><p>使用 SSO 时，应将命令行 <strong>C:\Windows\Explorer.exe &quot; 文件夹路径 &quot; </strong> 。 如果不使用 SSO，则命令行应为 &quot; <strong> 文件夹路径 </strong> &quot; 。</p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



## 相关主题


[如何配置已发布的应用程序](how-to-configure-published-applicationsmedvv2.md)









