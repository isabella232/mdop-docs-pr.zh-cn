---
title: 安装 MBAM 2.5 服务器软件
description: 安装 MBAM 2.5 服务器软件
author: dansimp
ms.assetid: b9dbe697-5400-4bac-acfb-ee6dc6586c30
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6612bf52aa53ae693694d7ac02c5cab212d4e24f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803359"
---
# 安装 MBAM 2.5 服务器软件


本主题介绍了如何使用 Microsoft BitLocker 管理和监视设置向导或使用命令行参数安装 Microsoft BitLocker 管理和监视（MBAM）2.5 服务器软件。 对配置 MBAM 2.5 服务器功能的每台服务器重复服务器安装过程。 安装完成后，有关配置服务器功能的步骤，请参阅[配置 MBAM 2.5 服务器功能](configuring-the-mbam-25-server-features.md)。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">准备工作</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>查看 MBAM 2.5 规划信息</p></td>
<td align="left"><ul>
<li><p><a href="mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md" data-raw-source="[MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)">独立和 Configuration Manager 集成拓扑的 MBAM 2.5 服务器先决条件</a></p></li>
<li><p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)">MBAM 2.5 支持的配置</a></p></li>
<li><p><a href="high-level-architecture-for-mbam-25.md" data-raw-source="[High-Level Architecture for MBAM 2.5](high-level-architecture-for-mbam-25.md)">MBAM 2.5 的高级别体系结构</a></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>阅读如何获取日志文件</p></td>
<td align="left"><p>默认情况下，将在本地计算机的% temp% 文件夹中创建日志文件。 若要将日志文件写入特定位置而不是 <strong> % temp </strong> % 文件夹，请使用 <strong> /log </strong> &lt; <em> 位置 </em> &gt; 参数。</p>
<p>在 " <strong> </strong> <strong> </strong> <strong> 应用程序和服务日志" 下 &gt; &gt; </strong> 的 "MBAM-设置" 或 "MBAM" 子节点下，可能会在事件查看器中记录其他事件。 例如，如果卸载 MBAM，卸载程序还将卸载 EventViewer 中的 MBAM 和 MBAM Web 日志。</p></td>
</tr>
</tbody>
</table>

 

## 使用 Microsoft BitLocker 管理和监视设置向导安装 MBAM 2.5 服务器软件


使用以下步骤，通过使用 Microsoft BitLocker 管理和监视设置向导安装 MBAM 服务器软件。

**使用向导安装 MBAM 2.5 服务器软件**

1.  在要安装 MBAM 的服务器上，运行**MBAMserversetup.exe**以启动 Microsoft BitLocker 管理和监视设置向导。

2.  在 "**欢迎**" 页面上，单击 "**下一步**"。

3.  阅读并接受 Microsoft 软件许可协议，然后单击 "**下一步**" 继续安装。

4.  选择在检查更新时是否使用 Microsoft Update，然后单击 "**下一步**"。

5.  选择是否参与 "客户体验改善计划"，然后单击 "**下一步**"。

6.  若要开始安装，请单击 "**安装**"。

7.  若要在 MBAM 服务器软件完成安装后配置服务器功能，请选择 "在**向导关闭后运行 MBAM 服务器配置**" 复选框。 或者，你可以稍后通过使用服务器安装在 "**开始**" 菜单上创建的**MBAM 服务器配置**快捷方式来配置 MBAM。

8.  单击**完成**。

## 使用命令提示符窗口安装 MBAM 2.5 服务器软件


在命令提示符处，键入类似于以下命令的命令来安装 MBAM Server 软件。

``` syntax
MbamServerSetup.exe MBAMServerInstall.log
CEIPENABLED=True OPTIN_FOR_MICROFOST_UPDATES=True INSTALLDIR=c:\mbaminstall
```

下表介绍了用于安装 MBAM 2.5 服务器软件的命令行参数。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">参数</th>
<th align="left">参数值</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>CEIPENABLED</p></td>
<td align="left"><p>真假</p></td>
<td align="left"><p>True-参与 "客户改善体验计划"，该计划可帮助 Microsoft 识别要改进的 MBAM 功能。</p>
<p>False-不参与 "客户改善体验计划"。</p></td>
</tr>
<tr class="even">
<td align="left"><p>OPTIN_FOR_MICROSOFT_UPDATES</p></td>
<td align="left"><p>真假</p></td>
<td align="left"><p>True-使用 Microsoft Update 保持计算机的安全和最新的 Windows 和其他 Microsoft 产品，包括 MBAM。</p>
<p>False-不使用 Microsoft Update</p></td>
</tr>
<tr class="odd">
<td align="left"><p>INSTALLDIR</p></td>
<td align="left"><p>&lt;路径&gt;</p></td>
<td align="left"><p>要在其中安装 MBAM 的位置。</p>
<p>示例：</p>
<p>INSTALLDIR = c:\mbaminstall</p></td>
</tr>
<tr class="even">
<td align="left"><p>FORCE_UNINSTALL</p></td>
<td align="left"><p>真假</p></td>
<td align="left"><p>True-继续卸载 MBAM 的过程，即使无法删除任何功能也是如此。</p>
<p>False （默认值）如果卸载自定义操作无法删除添加的 MBAM 服务器功能，则卸载将失败，并且 MBAM 将保持安装状态。</p>
<p>在这两种情况下，在尝试卸载 MBAM 期间成功删除的所有功能将保持删除。</p></td>
</tr>
</tbody>
</table>

 



## 相关主题


[部署 MBAM 2.5](deploying-mbam-25.md)

[配置 MBAM 2.5 服务器功能](configuring-the-mbam-25-server-features.md)

 

## 已获得 MBAM 的建议？
- 在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。 
- 对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。 





