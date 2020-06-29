---
title: 确定发布方法
description: 确定发布方法
author: dansimp
ms.assetid: 1f2d0d39-5d65-457a-b826-4f45b00c8c85
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9a6b19b12c28ab67e3250909cb32ddb8419f399a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803016"
---
# 确定发布方法


使用应用程序虚拟化 Sequencer 对应用程序进行排序之后，你需要将该应用程序*发布*给你的用户。 发布应用程序包括将图标、程序包定义信息和内容源位置提供给安装了应用程序虚拟化客户端的每台计算机。 下表介绍了使用电子软件分发（ESD）系统部署应用程序虚拟化时支持的发布方法。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">方法</th>
<th align="left">优点</th>
<th align="left">缺点</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>在排序期间生成 Windows Installer 文件，作为独立的解决方案。</p></td>
<td align="left"><ul>
<li><p>使用非常简单。</p></li>
<li><p>程序包在每台计算机上本地加载到缓存中。</p></li>
<li><p>向用户显示的图标。</p></li>
<li><p>与传统软件部署类似。</p></li>
<li><p>无需流式服务器。</p></li>
</ul></td>
<td align="left"><ul>
<li><p>在计算机上的程序包内容的位置没有灵活性——在所有计算机上都有相同的位置。</p></li>
<li><p>必须仅使用 "添加/删除程序" 或 msiexec 删除应用程序。</p></li>
<li><p>删除和替换更新软件包更新所需的新版本。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>在排序期间生成 Windows Installer 文件，使用模式、加载和 OVERRIDEURL 命令行属性和程序包清单。</p></td>
<td align="left"><ul>
<li><p>使用方便，但灵活性更高。</p></li>
<li><p>向用户显示的图标。</p></li>
<li><p>可将包含应用程序的 SFT 文件置于流源位置，并且客户端配置为使用该位置。</p></li>
</ul></td>
<td align="left"><ul>
<li><p>灵活性有限-仅可在运行时控制软件包内容的位置。</p></li>
<li><p>必须仅使用 "添加/删除程序" 或 msiexec 删除应用程序。</p></li>
<li><p>删除和替换更新软件包更新所需的新版本，除非使用流式服务器。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>运行 SFTMIME 命令。</p></td>
<td align="left"><ul>
<li><p>全面的灵活性-完全控制所有软件包管理功能。</p></li>
</ul></td>
<td align="left"><ul>
<li><p>命令必须经过脚本才能与 ESD 系统配合使用。</p></li>
<li><p>必须按正确顺序在每台计算机上运行命令。</p></li>
<li><p>详细了解命令语言并仔细规划所需。</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

有关使用这些发布方法的详细信息，请参阅[如何在客户端发布虚拟应用程序](how-to-publish-a-virtual-application-on-the-client.md)。

## 相关主题


[确定流式处理方法](determine-your-streaming-method.md)

[基于电子软件分发的方案](electronic-software-distribution-based-scenario.md)

[基于电子软件分发的方案概述](electronic-software-distribution-based-scenario-overview.md)

[如何在客户端上发布虚拟应用程序](how-to-publish-a-virtual-application-on-the-client.md)

[SFTMIME 命令引用](sftmime--command-reference.md)

 

 





