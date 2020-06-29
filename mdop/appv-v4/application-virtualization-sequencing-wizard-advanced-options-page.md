---
title: 应用程序虚拟化顺序向导高级选项页面
description: 应用程序虚拟化顺序向导高级选项页面
author: dansimp
ms.assetid: 2c4c5d95-d55e-463d-a851-8486f6a724f2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 716fa27852f1cadfebec31a267ce1b9b581b8ff7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802280"
---
# 应用程序虚拟化顺序向导高级选项页面


使用应用程序虚拟化（app-v）顺序向导的 "**高级选项**" 页面指定要安装的应用程序的高级选项。 页面包含下表中所述的元素。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">名称</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>块大小</strong></p></td>
<td align="left"><p>用于指定在通过网络传输时，SFT 文件将被分成的块的大小。 所有块都等于指定的大小;但是，最后一个块可能小于指定的大小。 选择以下值之一：</p>
<ul>
<li><p><strong>4 KB</strong></p></li>
<li><p><strong>16 KB</strong></p></li>
<li><p><strong>32 KB</strong></p></li>
<li><p><strong>64 KB</strong></p></li>
</ul>
<div class="alert">
<strong>注意</strong><br/><p>选择块大小时，请考虑 SFT 文件的大小和你的网络带宽。 块大小较小的文件需要花费较长时间才能通过网络传输，但占用带宽较少。 块大小较大的文件可能会更快地传输，但它们会占用更多的网络带宽。 通过实验，你可以发现网络上的流式处理应用程序的最佳块大小。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><strong>在监视期间启用 Microsoft 更新</strong></p></td>
<td align="left"><p>允许在排序向导&#39;s 监视阶段安装 Microsoft 更新。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>变基 Dll</strong></p></td>
<td align="left"><p>允许将支持的动态链接库重新映射到 RAM 中的连续空间，从而节省内存并提高性能。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>后退</strong></p></td>
<td align="left"><p>访问排序向导&#39;s 上一页。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>下一个</strong></p></td>
<td align="left"><p>访问顺序向导&#39;s 下一页。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>取消</strong></p></td>
<td align="left"><p>序列向导的终止操作。</p></td>
</tr>
</tbody>
</table>



\ [模板令牌值 \]

使用 App-v 顺序向导的 "**高级选项**" 页，为要排序的应用程序指定高级选项。 此页面包含下表中所述的元素。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">名称</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>允许 Microsoft 更新在监视期间运行</strong></p></td>
<td align="left"><p>指定在应用程序排序期间监视阶段是否将软件更新应用于应用程序。 如果需要更新才能成功完成应用程序安装，此选项将很有帮助。 默认情况下，此选项处于未选中状态。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>变基 Dll</strong></p></td>
<td align="left"><p>允许将支持的动态链接库重新映射到 RAM 中的连续空间。 选择此选项可帮助管理内存和提高应用程序性能。 默认情况下，此选项处于未选中状态。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>后退</strong></p></td>
<td align="left"><p>转到向导的上一页。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>下一个</strong></p></td>
<td align="left"><p>转到向导的下一页。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>取消</strong></p></td>
<td align="left"><p>放弃设置并退出向导。</p></td>
</tr>
</tbody>
</table>



\ [模板令牌值 \]

## 相关主题


[序列化向导](sequencing-wizard.md)









