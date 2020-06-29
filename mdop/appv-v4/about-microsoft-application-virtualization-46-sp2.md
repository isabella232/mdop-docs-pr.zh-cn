---
title: 关于 Microsoft Application Virtualization 4.6 SP2
description: 关于 Microsoft Application Virtualization 4.6 SP2
author: dansimp
ms.assetid: 1429e314-9c38-472b-8687-3bed6cf0015c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 16303380782a086cfd750c7a8b2f99bf4f4c8b5d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802448"
---
# 关于 Microsoft Application Virtualization 4.6 SP2


Microsoft Application Virtualization （App-v） 4.6 SP2 提供了一些增强功能和新功能，本主题中将介绍这些功能。

**小心** 本主题介绍如何使用注册表编辑器更改 Windows 注册表。 如果不正确地更改 Windows 注册表，则可能会导致严重问题，可能需要重新安装 Windows。 在更改注册表之前，应创建注册表文件（.dat 和 .dat）的备份副本。 Microsoft 无法保证更改注册表时可能出现的问题可以解决。 更改注册表的风险由您自己承担。

 

**Windows 8 和 Windows Server 2012 支持**

App-v 4.6 SP2 添加了对 Windows 8 和 Windows Server 2012 远程桌面服务的支持。

**支持与 App-v 5.0 客户端共存**

App-v 4.6 SP2 为与 Microsoft Application Virtualization 5.0 客户端的共存提供支持。 有关如何将 app-v 5.0 客户端配置为与 app-v 4.6 SP2 客户端共存的说明，请查看 app-v 5.0 文档。 有关 App-V 5.0 的详细信息，请参阅 TechNet 上的[应用程序虚拟化 5](https://go.microsoft.com/fwlink/?LinkId=267599) 。

**使 Adobe Reader X 与受保护模式的虚拟化的能力**

你可以通过使用以下过程来虚拟化 Adobe Reader X，其保护模式功能处于打开状态。 以前，您必须禁用保护模式才能虚拟化 Adobe Reader X。

在启动 App-v 排序器之前，在 HKEY \ _LOCAL \ _MACHINE \\SOFTWARE \\Microsoft\\SoftGrid\\4.5\\SystemGuard\\Overrides 下创建以下注册表值：

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p>名称</p></td>
<td align="left"><p>类型</p></td>
<td align="left"><p>数据</p></td>
<td align="left"><p>描述</p></td>
</tr>
<tr class="even">
<td align="left"><p>EnableVFSPassthrough</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>raid-1</p></td>
<td align="left"><p>将此值设置为 <strong> 1， </strong> 以便在启动阶段，在保护模式下启动 Adobe Reader X。</p></td>
</tr>
</tbody>
</table>

 

**注意** 在运行64位操作系统的计算机上，创建 HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid\\4.5\\SystemGuard\\Overrides. 的注册表值

 

对于 Adobe Reader X 程序包中的每个 OSD 文件，在 "策略" 元素下添加以下项目 &lt; &gt; ：

`<VIRTUAL_FILE_SYSTEM_PASS_THROUGH>TRUE</VIRTUAL_FILE_SYSTEM_PASS_THROUGH>`

`<VIRTUAL_REGISTRY_PASS_THROUGH>TRUE</VIRTUAL_REGISTRY_PASS_THROUGH>`

`<ENFORCE_ACLS_ON_VREG_MODIFY>TRUE</ENFORCE_ACLS_ON_VREG_MODIFY>`

**新的 Sequencer 命令行参数**

通过 Sequencer GUI 创建程序包加速器（PA）时，你可以选择为将应用包加速器的管理员提供打包和部署指南的 RTF 或 TXT 文件。 此功能现在可使用 Sequencer CLI 使用。

`/ACCELERATORDESCRIPTIONFILE:PathToDescriptionFile`

指定在创建包加速器时提供打包和部署指南的 RTF 或 TXT 文件的路径。

**不再需要安装 Microsoft 应用程序错误报告**

当你使用 setup.msi 安装 app-v 4.6 SP2 客户端时，不再需要安装 Microsoft 应用程序错误报告（dw20shared.msi）。 现在，app-v 4.6 SP2 使用 Microsoft 错误报告。 有关详细信息，请参阅[如何使用 Setup.msi安装 App-v 客户端](https://go.microsoft.com/fwlink/?LinkId=267237)。

**客户反馈和修补程序汇总**

App-v 4.6 SP2 包括自 app-v 4.6 SP1 发布以来发现的解决问题的修补程序汇总。 App-v 4.6 SP2 包含 Microsoft Application Virtualization 4.6 SP1 修补程序（包括 Microsoft Application Virtualization SP1）的最新修补程序。

## 本部分内容


<a href="" id="app-v-4-6-sp2-release-notes"></a>[App-V 4.6 SP2 发行说明](https://go.microsoft.com/fwlink/?LinkId=267600)  
提供有关 app-v 4.6 SP2 的已知问题的最新信息。

 

 





