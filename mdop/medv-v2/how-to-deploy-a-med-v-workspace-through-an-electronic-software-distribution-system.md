---
title: 如何通过电子软件分发系统部署 MED-V 工作区
description: 如何通过电子软件分发系统部署 MED-V 工作区
author: dansimp
ms.assetid: b5134c35-e1de-470c-93f8-ead6218d9dce
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 56d21b0c2f010f63c04056d9fadd7763531bd9d5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798184"
---
# 如何通过电子软件分发系统部署 MED-V 工作区


电子软件分发系统旨在通过慢速或快速网络连接高效地将软件移动到许多不同的计算机。 以下部分提供了可帮助你使用软件分发系统在整个企业中部署 MED-V 工作区的信息和说明。

**注意**  
无论使用哪种软件分发解决方案，您都必须熟悉特定解决方案的要求。 如果您使用的是 System Center Configuration Manager 2007 R2 或更高版本，请参阅 Microsoft 技术库（）中的[Configuration Manager 文档库](https://go.microsoft.com/fwlink/?LinkId=66999) https://go.microsoft.com/fwlink/?LinkId=66999) 。



**重要提示**  
如果你使用的是 System Center Configuration Manager 2007 SP2，并且你的 MED-V 工作区配置为在**NAT**模式下运行，则虚拟机将归为基于 Internet 的客户端，并且无法找到要从中下载内容的最近分发点。

[用于改进由 med-v 管理的 vm 的功能的修复程序](https://go.microsoft.com/fwlink/?LinkId=201088)（ https://go.microsoft.com/fwlink/?LinkId=201088) 将新功能添加到由 med-v 托管的虚拟机并配置为在**NAT**模式下运行。 新功能允许虚拟机访问最近的分发点。 因此，管理员可以采用同样的方式管理虚拟机和主机。 此修补程序必须首先在网站服务器上安装，然后再安装在客户端上。

该更新已公开提供。 但是，系统可能会提示您接受 Microsoft 服务协议。 按照后续网页上的提示检索此修补程序。



你还可以使用批处理文件将 MED-V 组件一起部署，但这需要在安装 Windows 虚拟 PC 后重新启动。 若要跳过此要求，可以在安装所有组件后指定一个重启。 单次重启也会自动启动 MED-V-V，因为 MED-V 工作区安装会在 RUNKEY 中放置一个条目。

**使用软件分发系统部署 MED-V 工作区**

1.  将电子软件分发系统中的一组计算机和用户定义为计算机/用户的目标组。

2.  为每个需要分发的 Microsoft 安装文件创建程序包。 以下是所需的文件和必须安装它们的顺序：

    1.  **Windows 虚拟 PC** -如果尚未安装（需要重启计算机）。 有关详细信息，请参阅[配置安装先决条件](configure-installation-prerequisites.md)。

    2.  **Windows 虚拟 PC 的添加和更新**-如果尚未安装。 有关详细信息，请参阅[配置安装先决条件](configure-installation-prerequisites.md)。

    3.  **Med-v Host Agent 安装文件**-安装主机代理（med-v \ _HostAgent \ _Setup 安装文件）。 有关详细信息，请参阅[如何手动安装 Med-v 主机代理](how-to-manually-install-the-med-v-host-agent.md)。

        **警告**  
        在安装 MED-V 主机代理之前关闭 Internet Explorer，否则可能会在 URL 重定向中出现冲突。 您也可以通过在分发期间指定计算机重启来执行此操作。



    4.  **Med-v 工作区安装程序、VHD 和安装可执行文件**-在**Med-v 工作区包装**程序中创建。 有关详细信息，请参阅[创建 Med-v 工作区程序包](create-a-med-v-workspace-package.md)。

        **重要提示**  
        压缩的虚拟硬盘文件（medv）和设置可执行程序（setup.exe）必须与 MED-V 工作区安装程序位于同一个文件夹中。 然后，通过运行 setup.exe 安装 MED-V 工作区安装程序。



~~~
    **Tip**  
    Because problems can occur when you install MED-V from a network location, we recommend that you copy the MED-V workspace setup files locally and then run setup.exe.
~~~



3. 将程序包配置为在静默模式下运行（无需用户交互）。

   如果在缄默模式下运行，则不会提示关闭 Internet Explorer （如果正在运行）以及启动 MED-V Host Agent 的提示。 重新启动计算机时，将执行这两项操作。

   **注意**  
   安装 Windows 虚拟 PC 需要重新启动计算机。 如果禁止重启和忽略 MED-V 安装所需的先决条件，则可以创建单个安装过程并同时安装所有组件。 也可以通过使用命令行参数执行此操作。 有关这些参数的示例，请参阅[如何通过电子软件分发系统部署 Med-v 组件](how-to-deploy-the-med-v-components-through-an-electronic-software-distribution-system.md#bkmk-batch)。 当计算机重新启动时，MED-V 会自动启动。



4. 安装 Windows 虚拟电脑之前安装 MED-V 及其组件。 请参阅本主题后面的批处理文件示例。

   **重要提示**  
   选择 "**忽略 \ _PREREQUISITES** " 选项（如示例批处理文件中所示），以便可以在必需的 VPC 组件之前安装 med-v 组件。 按此顺序安装 MED-V 组件以允许单个重启。



5. 确定安装和软件分发系统所需的任何其他要求，例如目标平台和可用磁盘空间。

6. 将程序包分配给计算机/用户的目标组。

   当计算机运行时，软件分发系统客户端识别出新的程序包可用并开始按照定义和要求安装程序包。 安装应以静默顺序运行。 我们建议以单个进程的形式执行此操作，直到安装所有软件包才需要重启。

7. 安装完成后，重新启动已更新的计算机。

   根据软件分发系统，你可以计划重启计算机，或者最终用户可以在正常工作期间手动重新启动计算机。 重新启动计算机后，在最终用户登录后，MED-V 将自动启动。 当 MED-V 首次启动时，它将在首次设置时运行。

首次设置启动，可能需要几分钟才能完成，具体取决于你指定的虚拟硬盘的大小以及启动时应用到 MED-V 工作区的策略数。 最终用户可以通过在通知区域中观看 MED-V 图标来跟踪进度。 有关首次设置的详细信息，请参阅[med-v 2.0 部署概述](med-v-20-deployment-overview.md)。

**使用批处理文件安装 MED-V 工作区**

1.  使用管理凭据在命令提示符处运行安装。

2.  将每个组件部署到单个目录。 如果从网络共享运行，解压缩 medv 文件需要较长时间。

3.  最佳做法是指定在 MED-V 主机代理和 MED-V 工作区程序包文件之后安装 Windows 虚拟 PC 和 Windows 虚拟 PC 修补程序。 这意味着，Windows 更新不会通过需要重新启动来导致任何与安装过程的干扰。

4.  批处理文件完成后重新启动计算机。

重启后，系统会提示用户第一次运行安装并完成 MED-V 的配置。

以下使用指定参数的示例显示了如何在单个进程中安装64位 MED-V 组件：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">参数</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>/norestart</p></td>
<td align="left"><p>阻止 Windows 虚拟电脑和 Windows 虚拟 PC 更新的安装重新启动主机计算机。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/quiet</p></td>
<td align="left"><p>无需用户交互即可在安静模式下安装 MED-V 组件。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/qn</p></td>
<td align="left"><p>安装不带用户界面的 MED-V 组件。</p></td>
</tr>
<tr class="even">
<td align="left"><p>IGNORE_PREREQUISITES</p></td>
<td align="left"><p>安装而不检查 Windows 虚拟 PC。</p>
<div class="alert">
<strong>注意</strong><br/><p>仅当在此安装过程中安装 Windows 虚拟电脑时，才指定此参数。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p>OVERWRITEVHD</p></td>
<td align="left"><p>强制安装 MED-V 工作区并阻止它可能生成的任何提示。</p></td>
</tr>
</tbody>
</table>



## 示例


``` syntax
:: Install MED-V and the Pre-requisites

:: Install the MED-V Host Agent: install in quiet mode, ignore that Windows Virtual PC is not installed completely, and log results
start /WAIT .\MED-V_HostAgent_Setup.exe /qn IGNORE_PREREQUISITES=1 /l* %TEMP%\MEDVhost.log

:: Install the MED-V Workspace: install in quiet mode, Overwrite the VHD if it already exists, and log results
start /WAIT .\setup.exe /qn OVERWRITEVHD=1 /l* %TEMP%\MEDVworkspace.log

:: Install Windows Virtual PC: install in quiet mode and do not reboot
start /WAIT wusa.exe Windows6.1-KB958559-x64.msu /norestart /quiet

:: Install Windows Virtual PC patch to support non-HAV: install in quiet mode and do not reboot
wusa.exe Windows6.1-KB977206-x64.msu /norestart /quiet

:: After successful installation of the above components, a reboot of the host computer is required to complete installation.
```

## 相关主题


[MED-V 2.0 部署概述](med-v-20-deployment-overview.md)

[如何在 Windows 7 映像中部署 MED-V 工作区](how-to-deploy-a-med-v-workspace-in-a-windows-7-image.md)









