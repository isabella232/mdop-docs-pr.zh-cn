---
title: 使用 Windows PowerShell 配置高级设置
description: 使用 Windows PowerShell 配置高级设置
author: dansimp
ms.assetid: 437a31cc-2a11-456f-b448-b0b869fb53f7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 45a3ece3f76f6e982913aad2b25cfe0084542f32
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804159"
---
# 使用 Windows PowerShell 配置高级设置


你创建的 MED-V 工作区程序包包括可在测试和部署 MED-V 工作区程序包之前进行编辑的 Windows PowerShell 脚本（ps1）文件。 本部分提供的信息和指南可帮助你在部署 MED-V 工作区之前使用 Windows PowerShell 管理 MED-V 配置设置。

## 在 MED-V 中使用 Windows PowerShell Cmdlet


Microsoft 企业版虚拟化（MED-V）2.0 中提供了以下 Windows PowerShell cmdlet：

**新-MedvConfiguration**

**Export-MedvConfiguration**

**新-MedvWorkspace**

**Export-MedvWorkspace**

若要访问 MED-V 的 Windows PowerShell cmdlet，请打开 Windows PowerShell 并键入以下命令以导入 MED-V 模块。

``` syntax
Import-Module microsoft.medv
```

导入模块后，您可以通过使用标准的 Windows PowerShell 帮助命令、 **man**或**get-help**来访问 cmdlet 的内联帮助。 例如，若要访问**MedvConfiguration** cmdlet 的描述，包括可用参数的完整列表，请键入以下命令。

``` syntax
get-help New-MedvConfiguration
```

您还可以查看特定参数的帮助。 例如，若要查看参数 VmMemory 的帮助，请键入以下内容：

``` syntax
get-help New-MedvConfiguration -parameter VmMemory
```

若要查看所有 MED-V 配置设置及其默认设置的列表，请键入以下命令。

``` syntax
New-MedvConfiguration -ForceDefaults
```

若要查看所有 MED-V 配置设置及其当前值的列表，请键入以下命令。

``` syntax
gwmi -Class "Setting” -Namespace "root/microsoft/medv”
```

## 使用自定义设置创建 MED-V 工作区


使用 MED-V 工作区包装程序成功创建 MED-V 工作区程序包后，在指定用于保存包装程序文件的文件夹中生成 Windows PowerShell 脚本。 此脚本的内容显示一些可以编辑的可用 MED-V 配置设置。

执行这些步骤后，你可以自定义脚本，然后在 Windows PowerShell 中运行它，以使用新设置创建 MED-V 工作区。

**重要提示** 通过管理凭据运行 Windows PowerShell，并确保 Windows PowerShell 执行策略允许运行脚本。

1.  编辑由 MED-V 工作区包装程序生成的 Windows PowerShell 脚本，或使用所需的配置设置创作新脚本。

2.  通过管理凭据运行 Windows PowerShell，然后在命令提示符处键入以下命令。

    ``` syntax
    & “.\<workspacename>.ps1”
    ```

    此命令运行 Windows PowerShell 脚本并运行 MedvWorkspace cmdlet 以生成新**的**med-v 工作区程序包。 新的包装程序文件将保存在最初指定用于存储 MED-V 工作区包装程序文件的文件夹中。 有关此 cmdlet 的其他帮助，请参阅 Windows PowerShell 帮助。

 

## 将 MED-V 配置导出到注册表文件


在安装 MED-V 工作区后，您可以更新 MED-V 配置设置。 使用**MedvConfiguration** cmdlet 指定要更改的参数。 例如，若要创建可更改虚拟机内存设置的注册表文件，请键入以下命令。

``` syntax
New-MedvConfiguration  -VmMemory 1024 | Export-MedvConfiguration -Path c:\medvConfiguration\myConfig.reg
```

你可以将最终的注册表文件从主机计算机导入到 MED-V 工作区，以应用新的配置设置。

## 相关主题


[管理 MED-V 工作区配置设置](managing-med-v-workspace-configuration-settings.md)

[测试和部署 MED-V 工作区程序包](test-and-deploy-the-med-v-workspace-package.md)

 

 





