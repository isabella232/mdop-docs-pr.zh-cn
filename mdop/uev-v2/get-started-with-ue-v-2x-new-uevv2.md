---
title: UE-V 2.x 入门
description: UE-V 2.x 入门
author: dansimp
ms.assetid: 526ecbf0-0dee-4f0b-b017-8f8d25357b14
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 02/13/2017
ms.openlocfilehash: d3f01dd67ea9e5f6cfcf5dc3425265deff3f7df1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803338"
---
# UE-V 2.x 入门


按照本指南中的步骤，在小型测试环境中快速部署 Microsoft 用户体验虚拟化（UE-V）2.0 或2.1。 这可帮助你确定 UE-V 是否是在企业内的多个设备上管理用户设置的合适解决方案。

**注意** 本部分中的信息将在整个文档的其余部分中更详细地重复。 因此，如果你已经知道 UE-V 2 是正确的解决方案，而你不需要对其进行评估，则可以直接转到[准备 ue-v 2. x 部署](prepare-a-ue-v-2x-deployment-new-uevv2.md)。

 

UE-V 的标准安装将同步默认的 Microsoft Windows 和 Office 设置以及许多 Windows 应用设置。 确保你的测试环境包含两个或多个共享网络访问的用户计算机，你将在短期内评估 UE-V。

-   [步骤1：确认系统必备](#step1)：确保你的环境能够运行 ue-v，包括有关受支持的配置的详细信息。

-   [步骤2：为 ue-v 2 部署设置存储位置](#step2)：所有 Ue-v 部署都需要一个包含同步设置值的设置程序包的位置。

-   [步骤3：部署 ue-v 2 代理](#step3)：若要使用 ue-v 同步设置，设备必须安装并运行 ue-v Agent。

-   [步骤4：测试 ue-v 2 评估部署](#step4)：在安装了 ue-v Agent 的两台计算机上运行一些测试，并查看 ue-v 如何工作。

就是这样！ 按照这些步骤操作后，你将能够评估 UE-V 如何在你的企业中工作。

**进一步评估：** 你还可以执行其他步骤来配置一些第三方应用程序和业务线应用程序，以便使用 UE-V 同步其设置，如[部署 ue-v 的自定义应用程序](deploy-ue-v-2x-for-custom-applications-new-uevv2.md)中所述。

## <a href="" id="step1"></a>步骤1：确认先决条件


在继续操作之前，请确保你的环境包括运行 UE-V 的这些要求。

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
<th align="left"><strong>操作系统</strong></th>
<th align="left"><strong>版本</strong></th>
<th align="left"><strong>Service pack</strong></th>
<th align="left"><strong>系统体系结构</strong></th>
<th align="left"><strong>Windows PowerShell</strong></th>
<th align="left"><strong>Microsoft .NET Framework</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows7</p></td>
<td align="left"><p>旗舰版、企业版或专业版</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>32 位或 64 位</p></td>
<td align="left"><p>Windows PowerShell 3.0 或更高版本</p></td>
<td align="left"><p>.NET Framework 4 或更高版本</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2008R2</p></td>
<td align="left"><p>标准版、企业版、数据中心版或 Web 服务器</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>64 位</p></td>
<td align="left"><p>Windows PowerShell 3.0 或更高版本</p></td>
<td align="left"><p>.NET Framework 4 或更高版本</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows 8.1</p></td>
<td align="left"><p>企业版或专业版</p></td>
<td align="left"><p>无</p></td>
<td align="left"><p>32 位或 64 位</p></td>
<td align="left"><p>Windows PowerShell 3.0 或更高版本</p></td>
<td align="left"><p>.NET Framework 4。5</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server 2012 或 Windows Server 2012 R2</p></td>
<td align="left"><p>标准版或数据中心</p></td>
<td align="left"><p>无</p></td>
<td align="left"><p>64 位</p></td>
<td align="left"><p>Windows PowerShell 3.0 或更高版本</p></td>
<td align="left"><p>.NET Framework 4。5</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows 10 预 1607 verison</p></td>
<td align="left"><p>企业版或专业版</p></td>
<td align="left"><p></p></td>
<td align="left"><p>32 位或 64 位</p></td>
<td align="left"><p>Windows PowerShell 3.0 或更高版本</p></td>
<td align="left"><p>.NET Framework 4。5</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server 2016</p></td>
<td align="left"><p>标准版或数据中心</p></td>
<td align="left"><p>无</p></td>
<td align="left"><p>64 位</p></td>
<td align="left"><p>Windows PowerShell 3.0 或更高版本</p></td>
<td align="left"><p>.NET Framework 4。5</p></td>
</tr>
</tbody>
</table>

**注意：** 从 Windows 10 版本1607开始，UE-V 已包含在[windows 10 For 企业](https://www.microsoft.com/WindowsForBusiness/windows-for-enterprise)中，不再属于 Microsoft 桌面优化包

同样 .。。

-   **MDOP 许可证：** 此技术是 Microsoft 桌面优化包（MDOP）的一部分。 企业客户可以通过 Microsoft 软件保障获得 MDOP。 有关 Microsoft 软件保证和获取 MDOP 的详细信息，请参阅如何获取 MDOP （ https://go.microsoft.com/fwlink/p/?LinkId=322049) 。

-   要安装的任何计算机的**管理凭据**

## <a href="" id="step2"></a>步骤2：为 UE-V 2 部署设置存储位置


你将需要部署设置存储位置（一个标准网络共享，用户设置存储在设置包文件中）。 创建设置存储共享时，应限制对需要它的用户的访问。 [部署设置存储位置](https://technet.microsoft.com/library/dn458891.aspx#ssl)可提供更详细的信息。

**创建网络共享**

1.  创建新的安全组并将 UE-V 用户添加到其中。

2.  在存储 UE-V settings 程序包的集中位置的计算机上创建一个新文件夹，然后向 UE-V 用户授予对该文件夹的组权限。 支持 UE-V 的管理员必须具有此共享文件夹的权限。

3.  在连接时，请分配 UE-V 用户创建目录的权限。 向该目录的所有子目录授予完全权限，但阻止对上述任何内容的访问。

    1.  为 "设置存储位置" 文件夹设置以下共享级服务器消息块（SMB）权限。

        <table>
        <colgroup>
        <col width="50%" />
        <col width="50%" />
        </colgroup>
        <thead>
        <tr class="header">
        <th align="left"><strong>用户帐户</strong></th>
        <th align="left"><strong>推荐的权限</strong></th>
        </tr>
        </thead>
        <tbody>
        <tr class="odd">
        <td align="left"><p>所有人</p></td>
        <td align="left"><p>无权限</p></td>
        </tr>
        <tr class="even">
        <td align="left"><p>UE-V 用户的安全组</p></td>
        <td align="left"><p>完全控制</p></td>
        </tr>
        </tbody>
        </table>

         

    2.  为 "设置存储位置" 文件夹设置以下 NTFS 文件系统权限。

        <table>
        <colgroup>
        <col width="33%" />
        <col width="33%" />
        <col width="33%" />
        </colgroup>
        <thead>
        <tr class="header">
        <th align="left"><strong>用户帐户</strong></th>
        <th align="left"><strong>推荐的权限</strong></th>
        <th align="left"><strong>文件夹</strong></th>
        </tr>
        </thead>
        <tbody>
        <tr class="odd">
        <td align="left"><p>创建者/所有者</p></td>
        <td align="left"><p>完全控制</p></td>
        <td align="left"><p>仅子文件夹和文件</p></td>
        </tr>
        <tr class="even">
        <td align="left"><p>UE-V 用户的安全组</p></td>
        <td align="left"><p>列出文件夹/读取数据、创建文件夹/附加数据</p></td>
        <td align="left"><p>仅此文件夹</p></td>
        </tr>
        </tbody>
        </table>

         

**安全说明：**

如果在运行 Windows Server 操作系统的计算机上创建设置存储共享，请配置 UE-V 以验证本地管理员组或当前用户是否为存储设置包的文件夹的所有者。 若要启用此附加安全性，请在 Windows Server 注册表编辑器中指定此设置：

1.  将名为 **"RepositoryOwnerCheckEnabled"** 的**REG \ _DWORD**注册表项添加到**HKEY \ _LOCAL \ _MACHINE \\software\\microsoft\\uev\\agent\\configuration**。

2.  将注册表项值设置为*1*。

## <a href="" id="step3"></a>步骤3：部署 UE-V 2 代理


UE-V Agent 会同步用户计算机和设备之间的应用程序和 Windows 设置。 对于评估目的，请在属于同一用户的测试环境中的至少两台计算机上安装代理。

从命令行运行 AgentSetup.exe 文件以安装 UE-V Agent。 它在32位和64位操作系统上安装。

``` syntax
AgentSetup.exe SettingsStoragePath=\\server\settingsshare\%username%
```

必须将 SettingsStoragePath 命令行参数指定为步骤2中的网络共享。 [部署 Ue-v Agent](https://technet.microsoft.com/library/dn458891.aspx#agent)提供更详细的信息。

## <a href="" id="step4"></a>步骤4：测试 UE-V 2 评估部署


现在，你可以在 UE-V 评估部署上运行一些测试，以了解 UE-V 的工作方式。

****

1.  在第一台计算机（计算机 A）上，执行以下一项或多项更改：

    1.  打开到 Windows 桌面并将任务栏移动到窗口中的其他位置。

    2.  更改默认字体。

    3.  打开 "计算器" 并设置为 "**科学记数**"。

    4.  更改任何 Windows 应用的行为，如[管理 ue-v 2. 使用 Windows PowerShell 和 WMI 的 Ue-v Settings 位置模板](managing-ue-v-2x-settings-location-templates-using-windows-powershell-and-wmi-both-uevv2.md)中所述。

    5.  禁用 Microsoft 帐户设置同步和漫游配置文件。

2.  注销计算机 A：当用户锁定、注销、退出应用程序或同步提供程序运行时（默认情况下，每隔30分钟），将在 UE-V 设置程序包中保存设置。

3.  以与计算机 A 相同的用户的身份登录到第二台计算机（计算机 B）。

4.  打开到 Windows 桌面并验证任务栏位置是否与计算机 A 的位置相匹配。验证默认字体是否匹配且计算器是否设置为**科学计数**。 同时验证你对任何 Windows 应用所做的更改。

你可以将计算机 B 中的设置更改回原始计算机的设置。 然后从计算机 B 注销并登录到计算机 A 以验证更改。

## 此产品的其他资源


-   [Microsoft 用户体验虚拟化（UE-V） 2. x](index.md)

-   [准备 UE-V 2. x 部署](prepare-a-ue-v-2x-deployment-new-uevv2.md)

-   [管理 UE-V 2. x](administering-ue-v-2x-new-uevv2.md)

-   [解决 UE-V 2. x](troubleshooting-ue-v-2x-both-uevv2.md)

-   [UE-V 2.x 的技术参考](technical-reference-for-ue-v-2x-both-uevv2.md)






 

 





