---
title: 为 MED-V 创建 Windows Virtual PC 映像
description: 为 MED-V 创建 Windows Virtual PC 映像
author: dansimp
ms.assetid: fd7c0b1a-0769-4e7b-ad1a-dad19cca081f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: f947479776e84a4c54edb10d583dd21d7ccf6f43
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798107"
---
# 为 MED-V 创建 Windows Virtual PC 映像


在你可以向用户提供 MED-V 工作区之前，你必须先准备一个虚拟硬盘，用于为 Microsoft 企业版虚拟化（MED-V）2.0 构建 MED-V 工作区安装程序包。 若要准备必要的虚拟硬盘，必须创建包含所需操作系统、更新和软件的 Windows 虚拟 PC 映像，以便你可以在以后将应用程序和 URL 重定向信息部署到用户。 本部分提供了有关如何创建虚拟硬盘的指南。

若要创建 MED-V 的虚拟映像，必须执行以下步骤。

1.  [创建 Windows 虚拟 PC 映像](#bkmk-creatingavirtualmachinebyusingmicrosoftvirtualpc)

2.  [在映像上安装 Windows XP](#bkmk-installingwindowsxpontovpc)

3.  [在映像上安装 .NET Framework](#bkmk-installingnet)

4.  [将更新应用到映像](#bkmk-applypatchestovpc)

5.  [安装集成组件](#bkmk-installintegration)

## <a href="" id="bkmk-creatingavirtualmachinebyusingmicrosoftvirtualpc"></a>创建 Windows 虚拟 PC 映像


若要创建 Windows 虚拟 PC 映像，请参阅 Windows 虚拟电脑文档：

-   [Windows 虚拟 PC 主页](https://go.microsoft.com/fwlink/?LinkId=148103)（ https://go.microsoft.com/fwlink/?LinkId=148103) 。

-   [Windows 虚拟电脑帮助](https://go.microsoft.com/fwlink/?LinkId=182378)（ https://go.microsoft.com/fwlink/?LinkId=182378) 。

或者，如果你已有要用作虚拟映像基础的 Windows 映像（WIM）文件，你可以将其转换为用于构建 MED-V 工作区的 VHD。 有关如何将 WIM 转换为虚拟硬盘的详细信息，请参阅[Windows 7 中的本机 VHD 支持](https://go.microsoft.com/fwlink/?LinkId=195922)（ https://go.microsoft.com/fwlink/?LinkId=195922) 。

**重要提示** MED-V 在每个虚拟磁盘上仅支持一个虚拟硬盘，每个虚拟磁盘上仅支持一个分区。

 

创建虚拟硬盘后，在映像上安装 Windows XP。

## <a href="" id="bkmk-installingwindowsxpontovpc"></a>在 Windows 虚拟 PC 映像上安装 Windows XP


在构建 MED-V 工作区之前，MED-V 要求在 Windows 虚拟 PC 映像上安装 Windows XP SP3。

有关如何安装 Windows XP 的详细信息，请参阅[创建虚拟机和安装来宾操作系统](https://go.microsoft.com/fwlink/?LinkId=182379)（ https://go.microsoft.com/fwlink/?LinkId=182379) 。

## <a href="" id="bkmk-installingnet"></a>在 Windows 虚拟 PC 映像上安装 .NET Framework 3.5 SP1


你必须手动将 .NET Framework 3.5 SP1 和更新 KB959209 安装到你准备用于 MED-V 的 Windows 虚拟 PC 映像中。 更新[KB959209](https://go.microsoft.com/fwlink/?LinkId=204950) （ https://go.microsoft.com/fwlink/?LinkId=204950) 解决几个已知的应用程序兼容性问题。

## <a href="" id="bkmk-applypatchestovpc"></a>将更新应用到 Windows 虚拟 PC 映像


在虚拟机上安装 Windows XP 后，在映像上安装任何所需的 Windows XP 更新（如 SP3）。 你还可以安装某些可选更新，以获得更佳性能。

**重要提示** MED-V 要求在来宾操作系统上运行 Windows XP SP3。

 

**警告** 在安装 Windows XP 更新时，请确保你在要在 MED-V 工作区中使用的来宾中保留了 Internet Explorer 的版本。 例如，如果你打算在 MED-V 工作区中运行 Internet Explorer 6，请确保现在安装的任何更新不包括 Internet Explorer 7 或 Internet Explorer 8。 此外，建议配置注册表以防止自动更新升级 Internet Explorer。

 

### 安装可选的性能更新

尽管这是可选的，但我们建议你安装以下[修补程序 KB972435](https://go.microsoft.com/fwlink/?LinkId=201077)更新（ https://go.microsoft.com/fwlink/?LinkId=201077) 。 此更新提高了终端服务会话中共享文件夹的性能：

**注意** 该更新已公开提供。 但是，系统可能会提示您接受 Microsoft 服务协议。 按照后续网页上的提示检索此修补程序。

 

### 配置组策略性能更新

默认情况下，组策略一次下载到计算机一个字节。 这将导致在 MED-V 加入到域时出现延迟。 若要提高组策略的性能，请将以下注册表项值设置为注册表：

注册表子项： HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon

Entry： BufferPolicyReads

类型：DWORD

值：1

## <a href="" id="bkmk-installintegration"></a>安装集成组件


Windows 虚拟 PC 包括集成组件程序包。 这提供了改进虚拟环境和物理计算机之间的交互的功能。 例如，"集成组件" 程序包允许你在主机和来宾计算机之间移动鼠标。

**重要提示** MED-V 需要安装集成组件程序包。

 

将虚拟映像配置为与 MED-V 配合使用时，必须在来宾操作系统上手动安装集成组件程序包，以使集成功能可用。

有关如何安装和使用集成组件程序包的详细信息，请参阅以下内容：

-   [安装或升级集成组件程序包](https://go.microsoft.com/fwlink/?LinkId=195923)（ https://go.microsoft.com/fwlink/?LinkId=195923) 。

-   [关于集成功能](https://go.microsoft.com/fwlink/?LinkId=195924)（ https://go.microsoft.com/fwlink/?LinkId=195924) 。

### 安装 RemoteApp 更新

安装集成组件程序包后，系统将提示你安装以下更新： "适用于 Windows XP SP3 的更新以启用 RemoteApp"。 这是 MED-V 的必需组件。

**重要提示** 如果系统未提示您安装 RemoteApp 更新，则必须手动下载并安装。 有关如何下载此更新的详细信息和说明，请参阅[WINDOWS XP SP3 更新以启用 RemoteApp](https://go.microsoft.com/fwlink/?LinkId=195925) （ https://go.microsoft.com/fwlink/?LinkId=195925) 。

 

### 启用远程桌面

默认情况下，安装集成组件程序包后，将启用远程桌面。 要使 MED-V 能够正常运行，请确保已启用远程桌面，并且不分发任何禁用它的组策略。

有关如何启用远程桌面的信息，请参阅[启用或禁用远程桌面](https://go.microsoft.com/fwlink/?LinkId=201162)（ https://go.microsoft.com/fwlink/?LinkId=201162) 。

## 使用 Internet Explorer 管理工具包自定义 Internet Explorer


如果需要，您可以使用 Internet Explorer 管理工具包自定义来宾操作系统上的 Internet Explorer。 有关详细信息，请参阅[Internet Explorer 6 管理工具包和部署指南](https://go.microsoft.com/fwlink/?LinkId=200007)（http://go.microsoft.com/fwlink/?LinkId=200007）。

**警告** 应考虑与在 MED-V 工作区中自定义 Internet Explorer 相关的安全问题。 有关详细信息，请参阅[Med-v 操作的安全最佳做法](security-best-practices-for-med-v-operations.md)。

 

使用最新的来宾操作系统安装虚拟硬盘后，您可以在映像上安装应用程序。

## 相关主题


[在 Windows Virtual PC 映像上安装应用程序](installing-applications-on-a-windows-virtual-pc-image.md)

[为 MED-V 配置 Windows Virtual PC 映像](configuring-a-windows-virtual-pc-image-for-med-v.md)

 

 





