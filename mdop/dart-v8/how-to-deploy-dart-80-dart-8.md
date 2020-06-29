---
title: 如何部署 DaRT 8.0
description: 如何部署 DaRT 8.0
author: dansimp
ms.assetid: ab772e7a-c02f-4847-acdf-8bd362769a77
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: e7d64297f7687ebc0a23add3aa749ee4719beee4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803540"
---
# 如何部署 DaRT 8.0


以下说明介绍了如何在你的环境中部署 Microsoft Diagnostics 和恢复工具集（DaRT）8.0。 若要获取 DaRT 软件，请参阅[如何获取 MDOP](https://go.microsoft.com/fwlink/?LinkId=322049)。 假定你在一台管理员计算机上安装所有功能。 如果需要在多台计算机上部署或卸载 DaRT 8.0，请使用电子软件分发系统，例如使用命令行安装选项可能更容易。 本部分提供了可用命令行选项的说明和示例。

**重要提示** 在安装 DaRT 之前，请参阅[DaRT 8.0 支持的配置](dart-80-supported-configurations-dart-8.md)，以确保已安装所有必备软件，并且计算机满足最低系统要求。 在其上安装 DaRT 的计算机必须运行 Windows 8 或 Windows Server 2012。

 

你可以使用以下两种不同的配置之一安装 DaRT：

-   在管理员计算机上安装 DaRT 和所有 DaRT 工具。

-   仅在管理员计算机上安装创建 DaRT 恢复映像所需的工具，然后在技术支持计算机上安装**远程连接查看器**和**故障分析器**（可选）。

DaRT 安装文件在32位和64位版本中均可用。 安装与运行 DaRT 恢复映像向导的计算机的体系结构相匹配的版本，而不是要创建的恢复映像的计算机体系结构。

你可以使用 DaRT 安装文件的任一版本创建32位或64位计算机的恢复映像，但不能为32位和64位计算机创建一个恢复映像。

**在管理员计算机上安装 DaRT 和所有 DaRT 工具**

1.  下载32位或64位版本的 DaRT 8.0 安装程序文件。 选择与要安装 DaRT 的计算机相匹配的体系结构，并运行 DaRT 恢复映像向导。

2.  在下载了 DaRT 8.0 的文件夹中，运行与你的系统要求对应的**MSDaRT80.msi**安装文件。

3.  在 "**欢迎使用 Microsoft DaRT 8.0 安装向导**" 页面上，单击 "**下一步**"。

4.  接受 Microsoft 软件许可条款，然后单击 "**下一步**"。

5.  在 " **Microsoft 更新**" 页面上，选择 "**当我检查更新时使用 Microsoft 更新**"，然后单击 "**下一步**"。

6.  在 "**选择安装文件夹**" 页面上，选择一个文件夹，或单击 "**下一步**" 以在默认安装位置安装 DaRT。

7.  在 "**安装选项**" 页面上，选择要安装的 dart 功能，或单击 "**下一步**" 以安装 dart 和所有功能。

8.  若要开始安装，请单击 "**安装**"。

9.  安装成功完成后，单击 "**完成**" 退出向导。

## 使用命令提示符在管理员计算机上安装 DaRT 和所有 DaRT 工具


安装或卸载 DaRT 时，可以选择在命令提示符处运行安装文件。 本部分介绍了在命令提示符处安装或卸载 DaRT 时可以指定的不同选项的一些示例。

以下示例显示了如何安装所有 DaRT 功能。

``` syntax
msiexec /i MSDaRT80.msi ADDLOCAL=CommonFiles, DaRTRecoveryImage,CrashAnalyzer,RemoteViewer 
```

以下示例显示了如何仅安装 DaRT 恢复映像向导。

``` syntax
msiexec /i MSDaRT80.msi ADDLOCAL=CommonFiles, ,DaRTRecoveryImage
```

以下示例显示了如何仅安装崩溃分析器和 DaRT 远程连接查看器。

``` syntax
msiexec /i MSDaRT80.msi ADDLOCAL=CommonFiles,CrashAnalyzer,RemoteViewer 
```

以下示例为 Windows Installer 创建安装日志。 这对于调试非常有用。

``` syntax
msiexec.exe /i MSDaRT80.msi /l*v log.txt 
```

**注意** 你可以添加/qn 或/qb 以执行静默式安装。

 

**验证 DaRT 安装**

1.  单击 "**开始**"，然后选择 "**诊断和恢复工具集**"。

    将打开 "**诊断和恢复工具集**" 窗口。

2.  检查您选择安装的所有 DaRT 工具是否已成功安装。

## 相关主题


[将 DaRT 8.0 部署到管理员计算机](deploying-dart-80-to-administrator-computers-dart-8.md)

 

 





