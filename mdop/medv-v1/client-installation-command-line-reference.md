---
title: 客户端安装命令行参考
description: 客户端安装命令行参考
author: dansimp
ms.assetid: 122a593d-3314-4e9b-858a-08a25ed00c32
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 708daf82699c63dfaa1f99ae595911cf6bad3737
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804026"
---
# 客户端安装命令行参考


**从命令行安装 MED-V**

1.  从命令行运行 MED-V 程序包，后跟下表中所述的任何可选参数。

2.  MED-V 程序包称为 " *MED-V\_x.msi*"，其中*x*是版本号。

    例如， *MED-V\_1.0.65.msi*。

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
<td align="left"><p>/quiet</p></td>
<td align="left"><p></p></td>
<td align="left"><p>无提示安装</p></td>
</tr>
<tr class="even">
<td align="left"><p>/log &lt; 日志文件的完整路径&gt;</p></td>
<td align="left"><p>日志文件的完整路径。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>INSTALLDIR</p></td>
<td align="left"><p>安装目录的完整路径。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>VMSFOLDER</p></td>
<td align="left"><p>虚拟机文件夹的完整路径。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>INSTALL_ADMIN_TOOLS</p></td>
<td align="left"><p><strong>1,0</strong></p>
<p>默认值： <strong> 0</strong></p></td>
<td align="left"><p>安装 MED-V 管理工具。</p></td>
</tr>
<tr class="even">
<td align="left"><p>START_AUTOMATICALLY</p></td>
<td align="left"><p><strong>1,0</strong></p>
<p>默认值： <strong> 0</strong></p></td>
<td align="left"><p>每次用户登录到 Windows 时，都将自动启动 MED-V-V 客户端。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>SERVER_ADDRESS</p></td>
<td align="left"><p>主机名或 IP</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>SERVER_PORT</p></td>
<td align="left"><p>端口</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>SERVER_SSL</p></td>
<td align="left"><p><strong>1,0</strong></p>
<p>对于 <strong> https </strong> 或 <strong> http</strong></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>START_MEDV</p></td>
<td align="left"><p><strong>1,0</strong></p>
<p>默认值： <strong> 1</strong></p></td>
<td align="left"><p>在 MED-V 安装完成后启动 MED-V。</p>
<div class="alert">
<strong>注意</strong><br/><p>建议在系统安装 "MED-V" 时设置 START_MEDV = 0。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p>DESKTOP_SHORTCUT</p></td>
<td align="left"><p><strong>1,0</strong></p>
<p>默认值： <strong> 1</strong></p></td>
<td align="left"><p>在桌面上创建快捷方式，这将启动 MED-V 客户端。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MINIMAL_RAM_REQUIRED</p></td>
<td align="left"><p>RAM （MB）</p></td>
<td align="left"><p>安装 MED-V 时，检查计算机是否具有指定的最小 RAM 数量。 如果不是，则中止安装。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>SKIP_OS_CHECK</p></td>
<td align="left"><p><strong>1,0</strong></p></td>
<td align="left"><p>省略操作系统验证。</p></td>
</tr>
</tbody>
</table>











