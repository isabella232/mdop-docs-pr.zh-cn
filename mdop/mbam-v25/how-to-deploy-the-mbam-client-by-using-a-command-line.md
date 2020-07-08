---
title: 如何使用命令行部署 MBAM 客户端
description: 如何使用命令行部署 MBAM 客户端
author: dansimp
ms.assetid: ac1d4ffe-c26d-41c9-9737-a4f2b37fde24
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 416d76ad876c5114e3a8764111b6a15c879b13b5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803578"
---
# 如何使用命令行部署 MBAM 客户端


你可以使用命令行部署 Microsoft BitLocker 管理和监视（MBAM）客户端软件。

## 部署 MBAM 客户端软件的命令行


在命令提示符处键入以下命令，以在部署 MBAM 客户端软件时自动接受《最终用户许可协议》。

**MBAMClientSetup.exe/acceptEula = 是**

**注意** **/Ju**和 **/jm**命令行选项不受支持，并且不能用于安装 MBAM 客户端软件。

 

在命令提示符处键入以下命令，提取并安装 MSP：

**MBAMClientSetup.exe/extract &lt; path 提取 MSI &gt; /AcceptEula = Yes**

然后，通过运行以下命令以静默方式安装 MSI：

**msiexec/i &lt; 用于提取的 MSI &gt; /qb 的路径 = 1 重启 = ReallySuppress**

**注意** 从 MBAM 2.5 SP1 开始，MBAM 产品不再附带单独的 MSI。 但是，你可以在接受 EULA 后从产品附带的可执行文件（.exe）中提取 MSI。

 

## <a href="" id="optin-for-microsoft-updates-1-command-line-option"></a>OPTIN \ _FOR \ _MICROSOFT \ _UPDATES = 1 命令行选项


你可以选择在 `OPTIN_FOR_MICROSOFT_UPDATES=1` 客户端软件安装期间指定命令行选项，以便在客户端计算机上自动安装 Microsoft 更新。 指定此选项会使 Microsoft 更新在客户端软件安装完成后自动启动和搜索可用更新以进行安装。

你可以将此命令行选项与以下任一安装方法结合使用。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">使用安装 MBAM 客户端软件</th>
<th align="left">示例</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>MBAMClientSetup.exe</strong></p></td>
<td align="left"><p><strong>MbamClientSetup.exe OPTIN_FOR_MICROSOFT_UPDATES = 1</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>msiexec/i MBAMClient.msi</strong></p></td>
<td align="left"><p><strong>msiexec/i MBAMClient.msi OPTIN_FOR_MICROSOFT_UPDATES = 1</strong></p></td>
</tr>
</tbody>
</table>

 


## 相关主题


[部署 MBAM 2.5 客户端](deploying-the-mbam-25-client.md)

 

 
## 已获得 MBAM 的建议？
- 在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。 
- 对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。




