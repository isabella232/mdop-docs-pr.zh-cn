---
title: 如何部署 DaRT 7.0
description: 如何部署 DaRT 7.0
author: dansimp
ms.assetid: 30522441-40cb-4eca-99b4-dff758f5c647
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c2059b64e5f3ae7af8926bc00e5965598ede4288
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798198"
---
# 如何部署 DaRT 7.0


本主题提供了在你的环境中部署 Microsoft 诊断和恢复工具集（DaRT）7的说明。 本主题中的第一个过程假定你在一台管理员计算机上安装所有功能。 如果需要在多台计算机上部署或卸载 DaRT （例如，使用电子软件分发系统），则使用命令行安装选项可能更容易。 本主题的第二个过程中定义了这些选项，其中提供了可用命令行选项的示例用法。

**重要提示** 在安装 DaRT 之前，请确保计算机满足[DaRT 7.0 支持的配置](dart-70-supported-configurations-dart-7.md)中列出的最低系统要求。

 

**在管理员计算机上安装 DaRT**

1.  找到您在软件下载中收到的 DaRT 安装文件。

2.  双击与你的系统要求相对应的 DaRT 安装文件，无论是32位还是64位。 DaRT 安装文件命名为 " **MSDaRT70.msi**"。

3.  接受 Microsoft 软件许可条款，然后单击 "**下一步**"。

4.  选择用于安装 DaRT 的目标文件夹，选择是应为所有用户安装 DaRT 还是仅为当前用户安装 DaRT，然后单击 "**下一步**"。

5.  选择是**典型**、**自定义**还是**完成**安装，然后单击 "**下一步**"。

    -   **典型**安装最常用的工具。 对于大多数用户，建议使用此方法。

    -   "**自定义**" 让你可以选择已安装的工具以及它们的安装位置。 建议高级用户使用此功能，尤其是在不同的支持台计算机上安装不同的 DaRT 工具时。

    -   **完整**安装所有 DaRT 工具，并且需要最大磁盘空间。

    选择了安装方法后，单击 "**下一步**"。

6.  若要开始安装，请单击 "**安装**"。

7.  安装成功完成后，单击 "**完成**" 退出向导。

**在命令提示符处安装 DaRT**

1.  以下示例显示了如何安装所有 DaRT 功能。

    ``` syntax
    msiexec /i MSDaRT70.msi ADDLOCAL=CommonFiles,MSDaRTHelp,DaRTRecoveryImage,CrashAnalyzer,RemoteViewer 
    ```

2.  以下示例显示了如何仅安装**DaRT 恢复映像向导**。

    ``` syntax
    msiexec /i MSDaRT70.msi ADDLOCAL=CommonFiles,MSDaRTHelp,DaRTRecoveryImage
    ```

3.  以下示例显示了如何仅安装崩溃分析器和 DaRT 远程连接查看器。

    ``` syntax
    msiexec /i MSDaRT70.msi ADDLOCAL=CommonFiles,MSDaRTHelp,CrashAnalyzer,RemoteViewer 
    ```

4.  以下示例为 Windows Installer 创建安装日志。 这对于调试非常有用。

    ``` syntax
    msiexec.exe /i MSDaRT70.msi /l*v log.txt 
    ```

**注意** 您可以将/qn 或/qb 添加到任何 DaRT 安装命令提示符选项以执行静默式安装。

 

## 相关主题


[将 DaRT 7.0 部署到管理员计算机](deploying-dart-70-to-administrator-computers-dart-7.md)

 

 





