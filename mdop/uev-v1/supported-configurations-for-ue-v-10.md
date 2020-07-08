---
title: UE-V 1.0 支持的配置
description: UE-V 1.0 支持的配置
author: dansimp
ms.assetid: d90ab83e-741f-48eb-b1d8-a64cb9259f7a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: a84514317de8a4cfd9df9c94a9a130933b00874a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803791"
---
# UE-V 1.0 支持的配置


Microsoft 用户体验虚拟化（UE-V）支持以下所述的配置。

**注意** Microsoft 提供对当前服务包的支持，在某些情况下，还提供上述服务包。 若要查找产品的支持时间表，请参阅[支持生命周期的服务包](https://go.microsoft.com/fwlink/p/?LinkId=31975)。 有关 Microsoft 支持生命周期策略的详细信息，请参阅[Microsoft 支持生命周期支持策略常见问题解答](https://go.microsoft.com/fwlink/p/?LinkId=31976)。

 

## UE-V Agent 和 UE-V 发生器支持的配置


下表列出了支持用户体验虚拟化生成器和用户体验虚拟化代理的操作系统。

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong>操作系统</strong></th>
<th align="left"><strong>版本</strong></th>
<th align="left"><strong>Service pack</strong></th>
<th align="left"><strong>系统体系结构</strong></th>
<th align="left"><strong>Microsoft .NET Framework</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows7</p></td>
<td align="left"><p>旗舰版、企业版或专业版</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>32 位或 64 位</p></td>
<td align="left"><p>.NET Framework 3.5 SP1</p>
<p>.NET Framework 4 （生成器）</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2008R2</p></td>
<td align="left"><p>标准、企业版、数据中心或 Web 服务器</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>64 位</p></td>
<td align="left"><p>.NET Framework 3.5 SP1</p>
<p>.NET Framework 4 （生成器）</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows 8</p></td>
<td align="left"><p>企业版或专业版</p></td>
<td align="left"><p>无</p></td>
<td align="left"><p>32 位或 64 位</p></td>
<td align="left"><p>.NET Framework 4 或 .NET Framework 3.5 SP1 （代理）</p>
<p>.NET Framework 4 （生成器）</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server 2012</p></td>
<td align="left"><p>标准版或数据中心</p></td>
<td align="left"><p>无</p></td>
<td align="left"><p>64 位</p></td>
<td align="left"><p>.NET Framework 4 或 .NET Framework 3.5 SP1 （代理）</p>
<p>.NET Framework 4 （生成器）</p></td>
</tr>
</tbody>
</table>

 

没有特定于 UE-V 的特殊 RAM 要求。

UE-V agent 的安装需要管理员权限，并且需要重新启动计算机才能运行 UE-V agent。

**重要提示** 必须禁用 Windows 8 中的 "同步你的设置" 功能，才能使 UE-V 能够正常运行。 同时与 Windows 8 和 UE-V 的设置同步将导致不可预测的同步行为。

 

### <a href="" id="requirements-for-the-offline-files-feature-"></a>脱机文件功能的要求

UE-V agent 可以同步并非始终连接到企业网络的计算机的用户设置，例如膝上型计算机或位于远程办公室的计算机，以及始终连接到企业网络的计算机，例如托管虚拟桌面接口（VDI）会话的 Windows 服务器。

UE-V 默认配置使用 Windows 脱机文件功能同步设置。 "脱机文件" 可确保即使计算机离开企业网络，用户的设置仍可用。 当重新建立与企业网络的连接时，对设置所做的任何更改都会自动与设置存储位置同步。 脱机文件还可确保用户的设置对位于具有低速或受限连接的远程办公室中的计算机可用。

若要同步偶尔离开企业网络的计算机的设置，必须在 UE-V agent 部署开始之前启用并启动 "脱机文件" 功能。 默认情况下，在 Windows7 上启用 "脱机文件" 功能。 默认情况下，在 Windows Server2008R2、Windows Server 2012 和 Windows 8 上禁用该功能。 如果未启用 "脱机文件" 功能，则 UE-V 设置同步将失败。

-   **Windows 7**

    默认情况下，Windows 7 上已启用 "脱机文件" 功能。 如有必要，可在提升的命令提示符下使用以下命令启用脱机文件：

    ``` syntax
    sc config CscService start=auto
    ```

-   **Windows 8**

    默认情况下，Windows 8 版本上禁用 "脱机文件" 功能。 通过在提升的命令提示符下使用以下命令，可以在 Windows 8 上启用脱机文件：

    ``` syntax
    sc config CscService start=auto
    ```

-   **Windows Server 2008 R2 和 Windows Server 2012**

    默认情况下，Windows Server 2008 R2 或 Windows Server 2012 上不安装 "脱机文件" 功能。 为了启用 "脱机文件" 功能，必须安装桌面体验包。 这是一个包含 "脱机文件" 功能的可选服务器组件。 安装后，在提升的命令提示符下使用以下命令启动 "脱机文件" 功能：

    ``` syntax
    sc config csc start= system
    ```

    ``` syntax
    sc config cscservice start= auto
    ```

必须重新启动计算机，设置才会开始同步。

### 对始终可用的连接的计算机进行同步

当您在始终连接到企业网络的计算机（如托管 VDI 会话的 Windows Server 计算机）上使用 UE-V 时，应禁用 "脱机文件"。

当 UE-V agent 配置为同步设置而不使用脱机文件时，设置存储服务器将被视为标准网络共享。 当网络可用时，设置将保持同步。 在此配置中，UE-V agent 可以配置为在应用程序设置导入延迟时发出通知。

如果不使用 "脱机文件" 功能，则必须在 UE-V agent 部署之前或期间禁用 UE-V 默认行为。 若要禁用 UE-V 的脱机文件，请执行下列操作之一：

-   在部署 UE-V agent 之前，请标记 UE-V 组策略设置中的 "不要使用脱机文件" 复选框。

-   在 UE-V 安装期间，在 `SyncMethod = None` 命令提示符处或批处理文件中设置 AgentSetup.exe 参数。 有关如何部署代理的详细信息，请参阅[部署 Ue-v agent](deploying-the-ue-v-agent.md)。

如果禁用 UE-V 的脱机文件设置，并且在安装时没有指定**powerschool**参数，则 ue-v agent 安装将失败。 您也可以通过 PowerShell 或 WMI 禁用脱机文件。 有关 WMI 和 PowerShell 命令的详细信息，请参阅[通过 PowerShell 和 WMI 管理 ue-v 1.0 代理和程序包](managing-the-ue-v-10-agent-and-packages-with-powershell-and-wmi.md)。

必须重新启动计算机，设置才会开始同步。

### UE-V PowerShell 功能的先决条件

代理的 UE-V PowerShell 功能需要启用 .NET Framework 版本 3.5 SP1 和 PowerShell 版本2.0 或更高版本。

### UE-V 发电机支持的先决条件

在用于创建自定义设置位置模板的计算机上安装 UE-V 发生器。 此计算机应安装其设置将漫游的应用程序。 您必须是运行 UE-V 发生器软件的计算机上 "管理员" 组的成员。 此外，UE-V 生成器必须安装在使用 NTFS 文件系统的计算机上。 UE-V 发生器软件需要 .NET Framework 版本4。 有关详细信息，请参阅[规划用于 ue-v 1.0 的自定义模板部署](planning-for-custom-template-deployment-for-ue-v-10.md)。

## 相关主题


[规划 UE-V 1.0](planning-for-ue-v-10.md)

[为 UE-V 准备你的环境](preparing-your-environment-for-ue-v.md)

[部署 UE-V 1.0](deploying-ue-v-10.md)

为[ue-v 1.0 部署设置存储位置](deploying-the-settings-storage-location-for-ue-v-10.md)的用户体验虚拟化支持的配置

[安装 UE-V 生成器](installing-the-ue-v-generator.md)

[部署 UE-V 代理](deploying-the-ue-v-agent.md)

 

 





