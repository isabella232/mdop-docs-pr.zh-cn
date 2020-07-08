---
title: 还原与 UE-V 1.0 同步的应用程序和 Windows 设置
description: 还原与 UE-V 1.0 同步的应用程序和 Windows 设置
author: dansimp
ms.assetid: 254a16b1-f186-44a4-8e22-49a4ee87c734
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 31ae83e0a44f98b66a9930f8c5db2231992a4700
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798030"
---
# 还原与 UE-V 1.0 同步的应用程序和 Windows 设置


Microsoft 用户体验虚拟化（UE-V）的 WMI 和 PowerShell 功能提供了还原设置程序包的功能。 WMI 和 PowerShell 命令允许你在安装 UE-V Agent 后首次启动应用程序时，将应用程序和 Windows 设置还原到计算机上的设置值。 将在每个应用程序或 Windows 设置基础上执行此还原操作。 下次运行应用程序时或当用户登录到操作系统时，将还原这些设置。

**通过 PowerShell 还原应用程序设置和 Windows 设置**

1.  打开 Windows PowerShell 窗口。 若要导入 Microsoft UE-V PowerShell 模块，请输入以下命令：

    ``` syntax
    Import-module UEV
    ```

2.  输入以下 PowerShell cmdlet 以还原应用程序设置和 Windows 设置。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><strong>PowerShell cmdlet</strong></th>
    <th align="left"><strong>描述</strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>Restore-UevUserSetting</p></td>
    <td align="left"><p>还原应用程序的用户设置或还原一组 Windows 设置</p></td>
    </tr>
    </tbody>
    </table>

     

**通过 WMI 还原应用程序设置和 Windows 设置**

1.  打开一个 PowerShell 窗口。

2.  输入以下 WMI 命令以还原应用程序设置和 Windows 设置。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><strong>WMI 命令</strong></th>
    <th align="left"><strong>描述</strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>WmiMethod-命名空间 root\Microsoft\UEV 类 UserSettings-Name RestoreByTemplateId-ArgumentList &lt; template_ID&gt;</p></td>
    <td align="left"><p>还原应用程序的用户设置或还原一组 Windows 设置</p></td>
    </tr>
    </tbody>
    </table>

     

## 相关主题


[管理 UE-V 1.0](administering-ue-v-10.md)

[UE-V 1.0 的操作](operations-for-ue-v-10.md)

 

 





