---
title: MED-V 1.0 SP1 支持的配置
description: MED-V 1.0 SP1 支持的配置
author: dansimp
ms.assetid: 4dcf37c4-a061-43d2-878c-28efc87c3cdd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 5a707e8a3d59a423308f9f735ff38df9e235fbf5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803514"
---
# MED-V 1.0 SP1 支持的配置


本主题指定在你的环境中安装和运行 Microsoft 企业桌面虚拟化（MED-V） 1.0 Service Pack 1 （SP1）所需的要求。

## MED-V 1.0 SP1 客户端系统要求


### MED-V 客户端操作系统要求

下表列出了 MED-V 1.0 SP1 客户端安装支持的操作系统。

**注意**  
Microsoft 提供对当前服务包的支持，在某些情况下，还提供了之前的服务包。 若要查找产品的支持时间表，请参阅[生命周期支持的 Service pack](https://go.microsoft.com/fwlink/?LinkId=31975) （ https://go.microsoft.com/fwlink/?LinkId=31975) 。 有关 Microsoft 支持生命周期策略的其他信息，请参阅[Microsoft 支持生命周期支持策略常见问题](https://go.microsoft.com/fwlink/?LinkId=31976)（ https://go.microsoft.com/fwlink/?LinkId=31976) 。



<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">操作系统</th>
<th align="left">版本</th>
<th align="left">Service Pack</th>
<th align="left">系统体系结构</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows XP</p></td>
<td align="left"><p>专业版</p></td>
<td align="left"><p>SP2 或 SP3</p></td>
<td align="left"><p>x86</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Vista</p></td>
<td align="left"><p>企业版、企业版或旗舰版</p></td>
<td align="left"><p>SP1 或 SP2</p></td>
<td align="left"><p>x86</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows 7</p></td>
<td align="left"><p>专业版、企业版或旗舰版</p></td>
<td align="left"><p>无</p></td>
<td align="left"><p>x86 或 x64</p></td>
</tr>
</tbody>
</table>



**注意**  
MED-V 客户端不在本机 x64 模式下运行。 而 MED-V 在64位计算机上的 Windows 64 位（WOW64）模式下运行。



下表列出了 MED-V 1.0 SP1 中支持的每个操作系统所需的最低 RAM。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">操作系统</th>
<th align="left">最低要求的 RAM</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows XP 专业版</p></td>
<td align="left"><p>1 GB</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Vista</p></td>
<td align="left"><p>2 GB</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows 7 x86</p></td>
<td align="left"><p>2 GB</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows 7 x64</p></td>
<td align="left"><p>3 GB</p></td>
</tr>
</tbody>
</table>



### <a href="" id="med-v-1-0-sp1-client-configuration-"></a>MED-V 1.0 SP1 客户端配置

**.NET Framework 版本**

以下版本的 Microsoft .NET Framework 支持 MED-V 1.0 SP1 客户端安装：

-   .NET Framework 2.0 或 .NET Framework 2.0 SP1

-   .NET Framework 3.0 或 .NET Framework 3.0 SP1

-   .NET Framework 3.5 或 .NET Framework 3.5 SP1

**虚拟化引擎**

对于以下配置中的 MED-V 1.0 SP1 客户端安装，支持 microsoft office 知识库文章974918中所述修复程序的 microsoft Virtual PC 2007 SP1：

-   静态虚拟硬盘（VHD）文件

-   位于同一目录中的多个 VHD 文件

-   动态 VHD 文件

**Internet 浏览器**

Windows Internet Explorer 7 和 Windows Internet Explorer 8 支持 MED-V 1.0 SP1 客户端安装。

**Microsoft Hyper-V Server**

在 Microsoft Hyper-v Server 环境中不支持 MED-V 客户端。

## MED-V 1.0 SP1 工作区系统要求


MED-V 1.0 SP1 引入了适用于 MED-V 1.0 的系统要求的更改。

### MED-V 工作区操作系统要求

下表列出了 MED-V 1.0 SP1 工作区支持的操作系统。

**注意**  
Microsoft 提供对当前服务包的支持，在某些情况下，还提供了之前的服务包。 若要查找产品的支持时间表，请参阅[生命周期支持的 Service pack](https://go.microsoft.com/fwlink/?LinkId=31975) （ https://go.microsoft.com/fwlink/?LinkId=31975) 。 有关 Microsoft 支持生命周期策略的其他信息，请参阅[Microsoft 支持生命周期支持策略常见问题](https://go.microsoft.com/fwlink/?LinkId=31976)（ https://go.microsoft.com/fwlink/?LinkId=31976) 。



<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">操作系统</th>
<th align="left">版本</th>
<th align="left">Service Pack</th>
<th align="left">系统体系结构</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows 2000</p></td>
<td align="left"><p>专业版</p></td>
<td align="left"><p>以后</p></td>
<td align="left"><p>X86</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows XP</p></td>
<td align="left"><p>专业版</p></td>
<td align="left"><p>SP2 或 SP3</p>
<div class="alert">
<strong>注意</strong><br/><p>建议使用 SP3，以确保 MED-V 工作区与 MED-V 的未来版本兼容。</p>
</div>
<div>

</div></td>
<td align="left"><p>x86</p></td>
</tr>
</tbody>
</table>



### <a href="" id="med-v-1-0-sp1-workspace-configuration-"></a>MED-V 1.0 SP1 工作区配置

**.NET Framework 版本**

MED-V 需要以下支持版本的 Microsoft .NET Framework for MED-V 1.0 SP1 工作区安装：

-   .NET Framework 2.0 SP1

-   .NET Framework 3.0 SP1

-   .NET Framework 3.5 或 .NET Framework 3.5 SP1

**注意**  
我们建议 .NET Framework 3.5 SP1，以确保 MED-V 工作区与 MED-V 的未来版本兼容。



**Internet 浏览器**

对于 MED-V 1.0 SP1 工作区安装，windows Internet Explorer 6 SP2 和 Windows Internet Explorer 7 均受支持。

### <a href="" id="med-v-workspace-images-"></a>MED-V 工作区图像

MED-V 工作区映像必须使用虚拟 PC 2007 SP1 创建。

## MED-V 1.0 SP1 服务器系统要求


MED-V 1.0 SP1 引入了适用于 MED-V 1.0 的系统要求的更改。

### MED-V 1.0 服务器操作系统要求

下表列出了 MED-V 1.0 SP1 服务器安装支持的操作系统。

**注意**  
Microsoft 提供对当前服务包的支持，在某些情况下，还提供了之前的服务包。 若要查找产品的支持时间表，请参阅[生命周期支持的 Service pack](https://go.microsoft.com/fwlink/?LinkId=31975) （ https://go.microsoft.com/fwlink/?LinkId=31975) 。 有关 Microsoft 支持生命周期策略的其他信息，请参阅[Microsoft 支持生命周期支持策略常见问题](https://go.microsoft.com/fwlink/?LinkId=31976)（ https://go.microsoft.com/fwlink/?LinkId=31976) 。



<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">操作系统</th>
<th align="left">版本</th>
<th align="left">Service Pack</th>
<th align="left">系统体系结构</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows Server 2008</p></td>
<td align="left"><p>Standard 或 Enterprise</p></td>
<td align="left"><p>SP1 或 SP2</p></td>
<td align="left"><p>X86 或 x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server 2008 R2</p></td>
<td align="left"><p>Standard 或 Enterprise</p></td>
<td align="left"><p>无</p></td>
<td align="left"><p>x64</p></td>
</tr>
</tbody>
</table>



### <a href="" id="med-v-1-0-sp1-server-configuration-"></a>MED-V 1.0 SP1 服务器配置

**.NET Framework 版本**

MED-V 需要以下支持版本的 Microsoft .NET Framework for MED-V 1.0 SP1 工作区安装：

-   .NET Framework 2.0 或 .NET Framework 2.0 SP1

-   .NET Framework 3.0 或 .NET Framework 3.0 SP1

-   .NET Framework 3.5 或 .NET Framework 3.5 SP1

**Microsoft SQL Server 版本**

从 MED-V 1.0 SP1 服务器本地或远程安装 SQL Server 时，MED-V 1.0 SP1 支持以下版本的 Microsoft SQL Server：

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">SQL Server 版本</th>
<th align="left">版本</th>
<th align="left">Service Pack</th>
<th align="left">系统体系结构</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>SQL Server 2005</p></td>
<td align="left"><p>速成版、标准版或企业版</p></td>
<td align="left"><p>SP2</p></td>
<td align="left"><p>X86 或 x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>SQL Server 2008</p></td>
<td align="left"><p>速成版、标准版或企业版</p></td>
<td align="left"><p>无</p></td>
<td align="left"><p>X86 或 x64</p></td>
</tr>
</tbody>
</table>



**Microsoft Hyper-V Server**

在 Microsoft Hyper-v server 环境中支持 MED-V 服务器。

## MED-V 1.0 SP1 全球化信息


尽管 MED-V 不是用英语以外的语言发布的，但对于 MED-V 1.0 SP1 客户端、工作区和服务器安装，支持以下 Windows 操作系统语言版本：

-   英语

-   法语

-   德语

-   意大利语

-   西班牙语

-   葡萄牙语（巴西）

-   荷兰语（荷兰）

-   日语









