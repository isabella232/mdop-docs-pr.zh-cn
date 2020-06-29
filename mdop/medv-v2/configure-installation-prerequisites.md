---
title: 配置安装先决条件
description: 配置安装先决条件
author: dansimp
ms.assetid: ff9cf28a-3eac-4b6c-8ce9-bfc202f57947
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 6cd9379804c45a2025064a6eecf363c010980369
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802164"
---
# 配置安装先决条件


以下说明是安装和使用 Microsoft 企业桌面虚拟化（MED-V）2.0 的先决条件：

[Windows 虚拟电脑](#bkmk-howtoinstallandconfiguremicrosoftvirtualpc7)

[Windows 虚拟电脑更新](#bkmk-howtoinstallandconfiguremicrosoftvirtualpc7update)

[防病毒/备份软件配置](#bkmk-antivirusbackupsoftwareconfiguration)

## <a href="" id="bkmk-howtoinstallandconfiguremicrosoftvirtualpc7"></a>如何安装和配置 Windows 虚拟 PC


**重要提示** 如果主机上已存在虚拟 PC for Windows 的一个版本，则必须在安装 Windows 虚拟 PC 之前将其卸载。

 

**安装 Windows 虚拟电脑**

1.  从 Microsoft 下载中心下载[Windows 虚拟电脑](https://go.microsoft.com/fwlink/?LinkId=195918)（ https://go.microsoft.com/fwlink/?LinkId=195918) 。

2.  在主机计算机上运行安装文件，然后按照向导中的步骤操作。

**重要提示** Windows 虚拟 PC 包含集成组件程序包，该程序包提供改进虚拟环境和物理计算机之间的交互的功能。 例如，它允许你在主机和来宾计算机之间移动鼠标。 MED-V 需要安装集成组件程序包。

 

## <a href="" id="bkmk-howtoinstallandconfiguremicrosoftvirtualpc7update"></a>如何安装和配置 Windows 虚拟 PC 更新


与文章 KB977206 相关联的 Microsoft 更新为没有硬件辅助虚拟化（HAV）技术的计算机启用 Windows XP 模式。 我们建议安装此更新，因为如果来宾操作系统中的集成组件程序包与主机上安装的 Windows Virtual 电脑版本不匹配，某些集成功能可能无法正常工作。

**重要提示** 在运行 Windows 7 Service Pack 1 的主机上安装 MED-V 时，无需安装此更新。

 

**提示** 除了此处列出的更新，建议你查看所有可用的 Windows 虚拟电脑更新，并针对你的环境应用相应的或必需的更新。

 

**安装 Windows 虚拟 PC 更新**

1.  从 Microsoft 下载中心下载所需的 Windows 虚拟 PC 更新。

    [32 位更新](https://go.microsoft.com/fwlink/?LinkId=195919)（ https://go.microsoft.com/fwlink/?LinkId=195919) 。

    [64 位更新](https://go.microsoft.com/fwlink/?LinkId=195920)（ https://go.microsoft.com/fwlink/?LinkId=195920) 。

2.  在提升模式下在主机计算机上运行安装文件，然后按照向导中的步骤操作。

    有关适用于 Windows 虚拟 PC 的修补程序包的详细信息，请参阅[文章 977206](https://go.microsoft.com/fwlink/?LinkId=195921) （ https://go.microsoft.com/fwlink/?LinkId=195921) 。

## <a href="" id="bkmk-antivirusbackupsoftwareconfiguration"></a>如何配置防病毒/备份软件


为了防止防病毒活动影响虚拟桌面的性能，我们建议你可以从在主机计算机上运行的任何防病毒软件或备份进程中排除以下虚拟机文件类型：

-   \*.VMC

-   \*.VUD

-   \*.VSV

-   \*..VHD

## 相关主题


[配置环境先决条件](configure-environment-prerequisites.md)

[高级别体系结构](high-level-architecturemedv2.md)

[MED-V 2.0 支持的配置](med-v-20-supported-configurations.md)

 

 





