---
title: MED-V 安装文件的命令行选项
description: MED-V 安装文件的命令行选项
author: dansimp
ms.assetid: 7b8cd3e4-1d09-44a0-b690-f85b0d0a6b02
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 39582a592a59a4d0e81ef406edc6a984497275c7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803974"
---
# MED-V 安装文件的命令行选项


在安装或卸载 Microsoft 企业桌面虚拟化（MED-V）2.0 时，可以选择在命令提示符处运行安装文件。 本部分介绍了在命令提示符处安装或卸载 MED-V 时可以指定的不同选项。

### 命令行参数

你可以将以下命令行参数与它们各自的 MED-V 安装文件结合使用。

<table style="width:100%;">
<colgroup>
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">安装文件</th>
<th align="left">参数</th>
<th align="left">接受的值</th>
<th align="left">类型</th>
<th align="left">描述</th>
<th align="left">默认值</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Host Agent</p></td>
<td align="left"><p>MEDVDIR</p></td>
<td align="left"><p>&lt;安装路径&gt;</p></td>
<td align="left"><p>安装</p></td>
<td align="left"><p>更改已安装目录</p></td>
<td align="left"><p>安装转到程序 Files\Microsoft 企业版桌面虚拟化。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MED-V 工作区包装程序</p></td>
<td align="left"><p>MEDVDIR</p></td>
<td align="left"><p>&lt;安装路径&gt;</p></td>
<td align="left"><p>安装</p></td>
<td align="left"><p>更改已安装目录</p></td>
<td align="left"><p>安装转到程序 Files\Microsoft 企业版桌面虚拟化。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MED-V 工作区</p></td>
<td align="left"><p>INSTALLDIR</p></td>
<td align="left"><p>&lt;安装路径&gt;</p></td>
<td align="left"><p>安装</p></td>
<td align="left"><p>更改已安装目录</p></td>
<td align="left"><p>安装转到 ProgramData\Microsoft\Medv\Workspace。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MED-V 工作区</p></td>
<td align="left"><p>覆盖 VHD</p></td>
<td align="left"><p>0 或 1</p></td>
<td align="left"><p>安装</p></td>
<td align="left"><p>如果 VHD 存在（0）或覆盖现有 VHD （1），则安装失败。</p></td>
<td align="left"><p>不会发生覆盖，如果虚拟硬盘（VHD）已存在，则安装将失败。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MED-V 工作区</p></td>
<td align="left"><p>SUPPRESSMEDVLAUNCH</p></td>
<td align="left"><p>0 或 1</p></td>
<td align="left"><p>安装</p></td>
<td align="left"><p>开始（0）或不启动（1）安装 MED-V 工作区后的 MED-V。</p></td>
<td align="left"><p>如果 MED-V 工作区是使用用户界面（UI）安装的，则 "完成" 页面上的复选框 <strong> </strong> 控制是否启动 med-v。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MED-V 工作区</p></td>
<td align="left"><p>DELETEDIFFDISKS</p></td>
<td align="left"><p>0 或 1</p></td>
<td align="left"><p>卸载</p></td>
<td align="left"><p>保留（0）或删除（1）由 MED-V 创建的 Vhd</p></td>
<td align="left"><p>不会删除任何 Vhd。</p></td>
</tr>
</tbody>
</table>

 

### 命令行参数的示例

以下示例安装由 MED-V 工作区包装程序创建的 MED-V 工作区。 安装文件将在 Temp 目录中创建一个日志文件，并以安静模式运行安装文件，但不会在完成时启动 MED-V 主机代理。 安装文件将覆盖以前具有相同名称的安装所留下的任何 VHD。

``` syntax
setup.exe /l* %temp%\medv-workspace-install.log /qn SUPPRESSMEDVLAUNCH=1 OVERWRITEVHD=1
```

以下示例卸载以前安装的 MED-V 工作区。 安装文件将在 Temp 目录中创建一个日志文件，并以安静模式运行安装文件。 安装文件从文件系统中删除所有剩余的虚拟硬盘文件。

``` syntax
%ProgramData%\Microsoft\Medv\Workspace\uninstall.exe /l* %temp%\medv-workspace-uninstall.log /qn DELETEDIFFDISKS=1
```

## 相关主题


[部署 MED-V 组件](deploy-the-med-v-components.md)

[MED-V 的技术参考](technical-reference-for-med-v.md)

 

 





