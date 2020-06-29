---
title: 如何使用电子软件分发部署 App-V 5.0 程序包
description: 如何使用电子软件分发部署 App-V 5.0 程序包
author: dansimp
ms.assetid: 08e5e05b-dbb8-4be7-b2d8-721ef627da81
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 33af02c5e9fad7408f9719ecd1a7fa90eacfeb29
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798483"
---
# 如何使用电子软件分发部署 App-V 5.0 程序包


你可以使用电子软件分发（ESD）系统将 app-v 5.0 虚拟应用程序部署到 App-v 客户端。 有关详细信息，请参阅您正在使用的 ESD 提供的文档。

有关使用 ESD 部署 app-v 程序包的组件要求和选项，请参阅[计划使用电子软件分发系统部署 app-v 5.0](planning-to-deploy-app-v-50-with-an-electronic-software-distribution-system.md)。

使用以下方法之一将程序包发布到带有 ESD 的 App-v 客户端计算机：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">方法</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>由第三方 ESD 提供的功能</p></td>
<td align="left"><p>使用第三方 ESD 中的功能。</p></td>
</tr>
<tr class="even">
<td align="left"><p>独立 Windows Installer</p></td>
<td align="left"><p>在目标客户端计算机上通过使用在最初对应用程序进行序列化时创建的关联的 Windows Installer （.msi）文件来安装应用程序。 Windows Installer 文件包含用于配置程序包的关联 App-v 5.0 包文件信息，并将所需的程序包文件复制到客户端。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>PowerShell</p></td>
<td align="left"><p>使用 PowerShell cmdlet 部署虚拟化应用程序。 有关使用 PowerShell 和 App-v 5.0 的详细信息，请参阅 <a href="administering-app-v-by-using-powershell.md" data-raw-source="[Administering App-V by Using PowerShell](administering-app-v-by-using-powershell.md)"> 使用 powershell 管理 app-v </a> 。</p></td>
</tr>
</tbody>
</table>

 

**使用 ESD 部署 app-v 5.0 程序包**

1.  在环境中的计算机上安装 App-v 5.0 Sequencer。 有关安装 sequencer 的详细信息，请参阅[如何安装 sequencer](how-to-install-the-sequencer-beta-gb18030.md)。

2.  使用 app-v 5.0 Sequencer 创建虚拟应用程序。 有关创建虚拟应用程序的信息，请参阅[创建和管理 app-v 5.0 虚拟化应用程序](creating-and-managing-app-v-50-virtualized-applications.md)。

3.  创建虚拟应用程序后，使用 ESD 解决方案部署程序包。

    如果您使用的是 System Center Configuration Manager，请首先查看[配置管理器中的应用程序管理简介](https://go.microsoft.com/fwlink/?LinkId=281816)，了解有关使用 app-v 5.0 和 System Center2012 Configuration Manager 的信息。

    已**获得有关 app-v 的建议**？ 在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。 **遇到了 app-v 问题？** 使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相关主题


[App-V 5.0 的操作](operations-for-app-v-50.md)

 

 





