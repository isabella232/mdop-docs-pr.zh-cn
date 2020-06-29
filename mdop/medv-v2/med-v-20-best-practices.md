---
title: MED-V 2.0 最佳做法
description: MED-V 2.0 最佳做法
author: dansimp
ms.assetid: 47ba2dd1-6c6e-4d6e-8e18-b42291f8e02a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 7b664d33b403b821ce6bc9c045d937380ab4f91b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803903"
---
# MED-V 2.0 最佳做法


在您的企业中规划、部署和管理 MED-V 时，您可能会发现最佳做法建议非常有用。

### 配置首次设置以无人参与运行

虽然你可以指定所需的任何设置，但 MED-V 最佳做法是创建 Sysprep.inf 文件，以便首次运行时可以在**无人参与**模式下运行。 这要求你在继续**安装管理器**向导时提供所有所需的设置信息。 有关如何配置 MED-V 映像的详细信息，请参阅[配置适用于 med-v 的 Windows 虚拟 PC 映像](configuring-a-windows-virtual-pc-image-for-med-v.md)。

### 在虚拟机上禁用还原点

在创建 MED-V 工作区程序包之前，我们建议你在虚拟机上禁用还原点，以防止差异磁盘无限增长。 有关详细信息，请参阅[如何在 WINDOWS XP 中关闭和打开系统还原](https://go.microsoft.com/fwlink/?LinkId=195927)（ https://go.microsoft.com/fwlink/?LinkId=195927) 。

### 将 MED-V 映像配置为使用本地配置文件

我们建议你仅应用在 Windows XP 的应用程序兼容性环境中有意义的策略。 例如，桌面自定义策略通常不需要应用，应禁用。 有关如何仅允许本地配置文件的详细信息，请参阅[漫游用户配置文件（.）的组策略设置](https://go.microsoft.com/fwlink/?LinkId=205072) https://go.microsoft.com/fwlink/?LinkId=205072) 。

### 配置组策略性能更新

默认情况下，组策略一次下载到计算机一个字节。 这将导致在 MED-V 加入到域时出现延迟。 若要提高组策略的性能，建议将以下注册表项值设置为注册表：

注册表子项： HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon

Entry： BufferPolicyReads

类型：DWORD

值：1

### 通过组策略（而不是在 MED-V 映像）分发法律公告

如果希望最终用户在访问 MED-V 之前看到服务级别协议（SLA），我们建议你稍后通过组策略强制实施 SLA，以便在首次完成设置后向最终用户显示 SLA。

**小心** 尽管最佳做法是在**无人参与**模式下首次运行设置，但如果你决定将本地策略或注册表项设置为在映像（虚拟硬盘）中包含 SLA，则还必须指定首次在**参与**模式下运行设置，或者首次安装失败。

 

### 压缩虚拟硬盘

我们建议你压缩虚拟硬盘以回收空磁盘空间并减小虚拟硬盘的大小。 有关如何压缩虚拟硬盘的详细信息，请参阅[压缩 Med-v 虚拟硬盘](compacting-the-med-v-virtual-hard-disk.md)。

### 将虚拟机配置为在蓝色屏幕崩溃时重启

我们建议你将 MED-V 工作区虚拟机配置为在遇到蓝色屏幕崩溃时自动重启。 若要在来宾中配置此设置，请将 HKEY \ _LOCAL \ _MACHINE \\SYSTEM\\CurrentControlSet\\Control\\CrashControl 项中的 AutoReboot 值设置为 "1"。

您也可以通过单击 "**开始**"，单击 **"控制面板**"，然后单击 "**系统**" 来配置此设置。 然后，在 "**高级**" 选项卡的 "**启动和恢复**" 区域中，单击 "**设置**"。 选中 "**自动重新启动**" 复选框，然后单击 **"确定"**。

### 在密封 MED-V 图像之前对其进行备份

我们建议你先创建 MED-V 映像的备份副本，然后再进行密封。 有关密封 MED-V 映像的详细信息，请参阅[配置适用于 med-v 的 Windows 虚拟 PC 映像](configuring-a-windows-virtual-pc-image-for-med-v.md)。

### 从批处理文件安装时最后安装 Windows Virtual 电脑

使用批处理文件安装 MED-V 组件时，请指定在 MED-V 主机代理和 MED-V 工作区程序包文件之后安装 Windows 虚拟 PC 和 Windows 虚拟 PC 修补程序。 这可确保 Windows 更新不会通过需要重新启动来导致任何与安装过程的干扰。

### 从本地文件夹安装 MED-V 工作区

由于从网络位置安装 MED-V 时可能出现的问题，我们建议你在本地复制 MED-V 工作区设置文件，然后运行 setup.exe。

### <a href="" id="manage-printer-redirection-in-one-manner-only-"></a>仅以一种方式管理打印机重定向

如果在 MED-V 来宾虚拟机上手动安装了打印机，并且在主机上安装了相同的打印机，则结果是在来宾中安装了两次。 为避免这种情况，我们建议采用一种仅以一种方式管理打印机重定向的 MED-V 最佳做法：禁用重定向并在来宾上手动安装打印机，或者启用重定向，不要在来宾上手动安装打印机。

### <a href="" id="configure-settings-for-med-v-guest-patching-"></a>为 MED-V 来宾修补程序配置设置

你可以通过在注册表中定义相关的配置值来控制 MED-V 虚拟机 awakens 接收自动更新的时间和时间。 MED-V 最佳做法是设置唤醒时间间隔，以匹配为 MED-V 虚拟机安排定期更新的时间。 此外，我们建议你将这些设置配置为类似于主机的行为。

有关如何配置 MED-V 来宾修补的设置的详细信息，请参阅[管理 Med-v 工作区的自动更新](managing-automatic-updates-for-med-v-workspaces.md)。

### 配置防病毒/备份软件

为了防止防病毒活动影响虚拟桌面的性能，我们建议你在可以时从运行于 MED-V 主机计算机上的任何防病毒软件或备份进程中排除以下虚拟机文件类型：

-   \*.VMC

-   \*.VUD

-   \*.VSV

-   \*..VHD

## 相关主题


[MED-V 的安全和保护](security-and-protection-for-med-v.md)

 

 





