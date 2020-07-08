---
title: Application Virtualization Client 硬件和软件要求
description: Application Virtualization Client 硬件和软件要求
author: dansimp
ms.assetid: 8b877a2c-5721-4b22-a47f-e2838d58ab12
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 5b828f59ba36099b4f6a545cd5bbcb3c72d24e3e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802335"
---
# Application Virtualization Client 硬件和软件要求


本主题介绍了为远程桌面服务（以前称为终端服务）安装应用程序虚拟化桌面客户端和应用程序虚拟化客户端时推荐的最低硬件和软件配置。

## 应用程序虚拟化桌面客户端


下表列出了应用程序虚拟化桌面客户端推荐的最低硬件和软件要求。 首先列出了 Microsoft Application Virtualization （app-v） 4.6 SP2 的要求，后跟前面的 App-v 4.6 SP2 版本的要求。

**注意** 应用程序虚拟化（app-v）桌面客户端不需要除主机操作系统要求之外的其他处理器或 RAM 资源。

 

### 硬件要求

硬件要求适用于所有版本。

-   处理器-请参阅所使用操作系统的推荐系统要求。

-   RAM —请参阅所使用操作系统的推荐系统要求。

-   磁盘-用于安装的30MB 和针对缓存的6GB。

### App-v 4.6 SP2 的软件要求

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
<th align="left">体系结构 SKU</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>WindowsXP</p></td>
<td align="left"><p>专业版</p></td>
<td align="left"><p>又</p></td>
<td align="left"><p>x86</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Vista</p></td>
<td align="left"><p>企业版、企业版或旗舰版</p></td>
<td align="left"><p>SP2</p></td>
<td align="left"><p>x86</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows7</p></td>
<td align="left"><p>专业版、企业版或旗舰版</p></td>
<td align="left"><p>无服务包或 SP1</p></td>
<td align="left"><p>x86 和 x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows 8</p></td>
<td align="left"><p>专业版或企业版</p></td>
<td align="left"><p></p></td>
<td align="left"><p>x86 和 x64</p></td>
</tr>
</tbody>
</table>

如果您使用的是 Setup.exe 方法，则会自动安装以下软件先决条件。 如果您使用的是 Setup.msi 安装程序，必须首先安装以下产品。
- **Microsoft Visual c + + 2005 sp1 可再发行程序包（x86）**-有关安装 Microsoft Visual c + + 2005 SP1 可再发行程序包（x86）的详细信息，请参阅[Microsoft Visual c + + 2005 Sp1 可再发行程序包（x86）](https://go.microsoft.com/fwlink/?LinkId=119961) （ https://go.microsoft.com/fwlink/?LinkId=119961) 。 对于 App-v 客户端的版本 4.5 SP2，从[Microsoft Visual c + + 2005 Service Pack 1 可再发行软件包1可再发行软件包 1](https://go.microsoft.com/fwlink/?LinkId=169360)下载 Vcredist\_x86.exe （ https://go.microsoft.com/fwlink/?LinkId=169360) 。
  -   **Microsoft CORE Xml services （MSXML） 6.0 sp1 （x86）**-有关安装 MICROSOFT Core xml SERVICES （msxml） 6.0 SP1 （x86）的详细信息，请参阅[Microsoft core XML services （msxml） 6.0 sp1 （x86） SP1 （x86）](https://go.microsoft.com/fwlink/?LinkId=63266) （ https://go.microsoft.com/fwlink/?LinkId=63266) 。

对于应用程序虚拟化（app-v）4.6 桌面客户端，如果使用的是 Setup.exe 方法，则会自动安装以下额外的软件必备项。 如果你使用的是 Setup.msi 安装程序，还必须使用列出的其他先决条件进行安装。

-   **Microsoft VisualC + + 2008SP1 可再发行程序包（x86）**-有关安装 microsoft VisualC + + 2008 Sp1 可再发行程序包（x86）的详细信息，请参阅[Microsoft VisualC + + 2008 Sp1 可再发行程序包（x86）（）](https://go.microsoft.com/fwlink/?LinkId=150700) https://go.microsoft.com/fwlink/?LinkId=150700) 。

### 在 App-v 4.6 SP2 之前的版本的软件要求

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
<th align="left">体系结构 SKU</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>WindowsXP</p></td>
<td align="left"><p>专业版</p></td>
<td align="left"><p>SP2 或 SP3</p></td>
<td align="left"><p>x86 和 x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Vista</p></td>
<td align="left"><p>企业版、企业版或旗舰版</p></td>
<td align="left"><p>无服务包、SP1 或 SP2</p></td>
<td align="left"><p>x86 和 x64</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows7 ¹</p></td>
<td align="left"><p>专业版、企业版或旗舰版</p></td>
<td align="left"><p>无服务包或 SP1</p></td>
<td align="left"><p>x86 和 x64</p></td>
</tr>
</tbody>
</table>
¹支持 app-v 4.5 SP1 和 SP2、app-v 4.6 和 4.6 SP1

应用程序虚拟化（app-v）4.6 桌面客户端支持这些操作系统的 x86 和 x64 Sku。

如果您使用的是 Setup.exe 方法，则会自动安装以下软件先决条件。 如果您使用的是 Setup.msi 安装程序，必须首先安装以下产品。

-   <strong>Microsoft Visual c + + 2005 SP1 可再发行程序包（x86） </strong> -有关安装 Microsoft Visual c + + 2005 SP1 可再发行程序包（x86）的详细信息，请参阅 <a href="https://go.microsoft.com/fwlink/?LinkId=119961" data-raw-source="[Microsoft Visual C++ 2005 SP1 Redistributable Package (x86)](https://go.microsoft.com/fwlink/?LinkId=119961)"> Microsoft Visual c + + 2005 Sp1 可再发行程序包（x86） </a> （ <a href="https://go.microsoft.com/fwlink/?LinkId=119961" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=119961"> https://go.microsoft.com/fwlink/?LinkId=119961 </a> ）。 对于 App-v 客户端的版本 4.5 SP2，从 <a href="https://go.microsoft.com/fwlink/?LinkId=169360" data-raw-source="[Microsoft Visual C++ 2005 Service Pack 1 Redistributable Package ATL Security Update](https://go.microsoft.com/fwlink/?LinkId=169360)"> Microsoft Visual c + + 2005 Service Pack 1 可再发行程序包 "ATL 安全更新 </a> （ <a href="https://go.microsoft.com/fwlink/?LinkId=169360" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=169360"> https://go.microsoft.com/fwlink/?LinkId=169360 </a> ）" 下载 Vcredist_x86.exe。

-   <strong>Microsoft Core XML Services （MSXML） 6.0 SP1 （x86） </strong> -有关安装 Microsoft CORE Xml services （msxml） 6.0 SP1 （x86）的详细信息，请参阅 <a href="https://go.microsoft.com/fwlink/?LinkId=63266" data-raw-source="[Microsoft Core XML Services (MSXML) 6.0 SP1 (x86)](https://go.microsoft.com/fwlink/?LinkId=63266)"> MICROSOFT Core xml SERVICES （msxml） 6.0 SP1 （x86） </a> （ <a href="https://go.microsoft.com/fwlink/?LinkId=63266" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=63266"> https://go.microsoft.com/fwlink/?LinkId=63266 </a> ）。

-   <strong>Microsoft 应用程序错误报告 </strong> -此软件的安装程序包含在 <strong> </strong> 自解压缩的存档文件的 Support\Watson 文件夹中。

对于应用程序虚拟化（app-v）4.6 桌面客户端，如果使用的是 Setup.exe 方法，则会自动安装以下额外的软件必备项。 如果你使用的是 Setup.msi 安装程序，还必须使用列出的其他先决条件进行安装。

-   <strong>Microsoft Visual c + + 2008 SP1 可再发行程序包（x86） </strong> -有关安装 Microsoft Visual c + + 2008 SP1 可再发行程序包（x86）的详细信息，请参阅 <a href="https://go.microsoft.com/fwlink/?LinkId=150700" data-raw-source="[Microsoft Visual C++ 2008 SP1 Redistributable Package (x86)](https://go.microsoft.com/fwlink/?LinkId=150700)"> Microsoft Visual c + + 2008 Sp1 可再发行程序包（x86） </a> （ <a href="https://go.microsoft.com/fwlink/?LinkId=150700" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=150700"> https://go.microsoft.com/fwlink/?LinkId=150700 </a> ）。

## 远程桌面服务的应用程序虚拟化客户端

以下是适用于远程桌面服务的应用程序虚拟化客户端的推荐硬件和软件要求。 首先列出 appv461_3 的要求，后跟前面的应用 V 4.6 SP2 的版本的要求。

远程桌面服务的应用程序虚拟化（app-v）客户端不需要任何额外的处理器或 RAM 资源，而不需要主机操作系统的要求。

### 硬件要求

硬件要求适用于所有版本。

-   处理器-请参阅所使用操作系统的推荐系统要求。

-   RAM —请参阅所使用操作系统的推荐系统要求。 这些要求还取决于用户和应用程序的数量。

-   磁盘-用于安装的30MB 和针对缓存的6GB。

### App-v 4.6 SP2 的软件要求

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
<th align="left">体系结构 SKU</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows Server2003 R2</p></td>
<td align="left"><p>标准版、企业版或数据中心版</p></td>
<td align="left"><p>SP2</p></td>
<td align="left"><p>x86 和 x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2008</p></td>
<td align="left"><p>标准版、企业版或数据中心版</p></td>
<td align="left"><p>SP2</p></td>
<td align="left"><p>x86 和 x64</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2008 R2</p></td>
<td align="left"><p>标准版、企业版或数据中心版</p></td>
<td align="left"><p>无服务包或 SP1</p></td>
<td align="left"><p>x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server 2012</p></td>
<td align="left"><p>标准版、企业版或数据中心版</p></td>
<td align="left"><p></p></td>
<td align="left"><p>x64</p></td>
</tr>
</tbody>
</table>

如果您使用的是 Setup.exe 方法，则会自动安装以下软件先决条件。 如果您使用的是 Setup.msi 安装程序，必须首先安装以下产品。

-   **Microsoft VisualC + + 2005SP1 可再发行程序包（x86）**-有关安装 microsoft VisualC + + 2005 Sp1 可再发行程序包（x86）的详细信息，请参阅[Microsoft VisualC + + 2005 Sp1 可再发行程序包（x86）（）](https://go.microsoft.com/fwlink/?LinkId=119961) https://go.microsoft.com/fwlink/?LinkId=119961) 。 对于 App-v 客户端的版本 4.5 SP2，从[Microsoft Visual c + + 2005 Service Pack 1 可再发行软件包1可再发行软件包 1](https://go.microsoft.com/fwlink/?LinkId=169360)下载 Vcredist\_x86.exe （ https://go.microsoft.com/fwlink/?LinkId=169360) 。

-   **Microsoft CORE Xml Services （MSXML） 6.0 sp1 （x86）**-有关安装 MICROSOFT Core xml SERVICES （msxml） 6.0 sp1 （x86）的详细信息，请参阅[Microsoft core XML services （MSXML） 6.0 sp1 （x86）](https://go.microsoft.com/fwlink/?LinkId=63266) （ https://go.microsoft.com/fwlink/?LinkId=63266) 。

-   **Microsoft 应用程序错误报告**-此软件的安装程序包含在自解压缩的存档文件的**Support\\Watson**文件夹中。

对于应用程序虚拟化（app-v）4.6 桌面客户端，如果使用的是 Setup.exe 方法，则会自动安装以下额外的软件必备项。 如果你使用的是 Setup.msi 安装程序，还必须使用列出的其他先决条件进行安装。

-   **Microsoft VisualC + + 2008SP1 可再发行程序包（x86）**-有关安装 microsoft VisualC + + 2008 Sp1 可再发行程序包（x86）的详细信息，请参阅[Microsoft VisualC + + 2008 Sp1 可再发行程序包（x86）（）](https://go.microsoft.com/fwlink/?LinkId=150700) https://go.microsoft.com/fwlink/?LinkId=150700) 。

### 在 App-v 4.6 SP2 之前的版本的软件要求

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
<th align="left">体系结构 SKU</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows Server2003</p></td>
<td align="left"><p>标准版、企业版或数据中心版</p></td>
<td align="left"><p>SP1 或 SP2</p></td>
<td align="left"><p>x86 和 x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2003 R2</p></td>
<td align="left"><p>标准版、企业版或数据中心版</p></td>
<td align="left"><p>无服务包或 SP2</p></td>
<td align="left"><p>x86 和 x64</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2008</p></td>
<td align="left"><p>标准版、企业版或数据中心版</p></td>
<td align="left"><p>SP1 或 SP2</p></td>
<td align="left"><p>x86 和 x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2008 R2</p></td>
<td align="left"><p>标准版、企业版或数据中心版</p></td>
<td align="left"><p>无服务包或 SP1</p></td>
<td align="left"><p>x64</p></td>
</tr>
</tbody>
</table>

适用于远程桌面服务的应用程序虚拟化（app-v）4.6 客户端支持这些操作系统的 x86 和 x64 Sku。

## 相关主题
- [Application Virtualization Sequencer 硬件和软件要求](application-virtualization-sequencer-hardware-and-software-requirements.md)
- [Application Virtualization System 要求](application-virtualization-system-requirements.md)
- [如何使用命令行安装客户端](how-to-install-the-client-by-using-the-command-line-new.md)
- [如何手动安装 Application Virtualization Client](how-to-manually-install-the-application-virtualization-client.md)
- [如何升级 Application Virtualization Client](how-to-upgrade-the-application-virtualization-client.md)
