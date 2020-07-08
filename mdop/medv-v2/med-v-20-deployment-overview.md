---
title: MED-V 2.0 部署概述
description: MED-V 2.0 部署概述
author: dansimp
ms.assetid: 0b8998ea-c46f-4c81-a304-f380b2ed7cf8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: ec2a5f86ac7d63295bd7c550bcb0a90004987e42
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803902"
---
# MED-V 2.0 部署概述


本部分提供有关如何安装和部署 Microsoft 企业版桌面虚拟化（MED-V）2.0 的一般信息和说明。

## 概述


MED-V 2.0 基于应用程序模型，您用于部署应用程序的相同方法可用于部署和管理 MED-V。 已部署的 MED-V 解决方案包括两个组件： MED-V 主机代理和来宾代理。 MED-V 主机代理安装在 Windows 7 桌面版上，而 MED-V 来宾代理安装在 MED-V 工作区内部的 Windows XP 中。 MED-V 还包括一个 MED-V 工作区包装程序，该包装程序提供创建和配置 MED-V 工作区所需的信息和工具。

**重要提示**  
MED-V 仅支持安装用于所有用户的 MED-V 工作区包装程序、MED-V 主机代理和 MED-V 工作区。 仅通过选择**ALLUSERS = ""** 来为当前用户安装 med-v 会导致在组件安装和 med-v 工作区的设置中出现故障。



### MED-V 安装文件

MED-V 包括运行 MED-V 所需的以下安装文件：

**MED-V 主机代理安装文件**

Host Agent 安装文件命名为 "MED-V\_HostAgent\_Setup.exe"。 此文件作为 MED-V 的企业内部部署的一部分，在每个相关的最终用户计算机上分发和安装。

**MED-V 工作区包装程序安装文件**

MED-V 工作区包装程序安装文件命名为 "MED-V\_WorkspacePackager\_Setup.exe"。 使用此文件在具有管理员权限的计算机上安装 MED-V 工作区包装程序。 桌面管理员使用 MED-V 工作区包装程序来创建和管理 MED-V 工作区。

**注意**  
MED-V 来宾代理将在首次设置时自动安装。



### MED-V 部署过程

以下是 MED-V 安装和部署过程的高级概述：

1.  在具有管理凭据且将用于构建 MED-V 工作区程序包的计算机上安装 MED-V 工作区包装程序。 有关详细信息，请参阅[如何安装 Med-v 工作区包装程序](how-to-install-the-med-v-workspace-packager.md)。

2.  使用 MED-V 工作区包装器准备 MED-V 映像并创建 MED-V 工作区程序包。 有关详细信息，请参阅[med-v 的操作](operations-for-med-v.md)。

3.  在整个企业中部署所需的 MED-V 组件。 MED-V 的必需组件是 Windows Virtual PC、MED-V 主机代理和 MED-V 工作区。

**重要提示**  
安装 MED-V 组件需要管理凭据。 如果最终用户正在安装 MED-V，系统将提示他们输入管理凭据。 或者，如果你使用电子软件分发（ESD）系统进行安装，则可以在上下文中提供管理凭据。



### MED-V 组件

在整个企业中部署的 MED-V 组件由以下部分组成：

**Windows 虚拟电脑**

Windows 虚拟 PC 映像内用于兼容性解决方案的 MED-V 函数。 需要 windows 虚拟 PC 和适用于 Windows 7 的更新（KB977206）。 有关详细信息，请参阅[配置安装先决条件](configure-installation-prerequisites.md)。

**MED-V 主机代理安装文件**

MED-V\_HostAgent\_Setup.exe。

**MED-V 工作区安装文件**

在构建由以下内容组成的 MED-V 工作区程序包时，将创建 MED-V 工作区安装文件：

执行 MED-V 工作区安装的 setup.exe 可执行程序

&lt;Med-v \ _workspace \ _name &gt; .msi 安装程序

&lt;VHD \ _filename &gt; medv 文件，它是压缩的虚拟硬盘

用于配置设置的文件（ &lt; 工作区 \ _name &gt; .reg 和 &lt; 工作区 \ _name &gt; ps1）

若要部署 MED-V，请将所有所需的安装文件复制到主计算机或主机可访问的共享。 运行 Windows Virtual PC、MED-V 主机代理和 MED-V 工作区的组件安装文件。 然后启动 MED-V 主机代理以在第一次安装 MED-V 时完成。

你可以手动执行安装。 但是，我们建议你使用电子软件分发方法自动部署组件。 有关详细信息，请参阅[如何通过电子软件分发系统部署 Med-v 工作区](how-to-deploy-a-med-v-workspace-through-an-electronic-software-distribution-system.md)。

**注意**  
有关控制安装选项的可用命令行参数的信息，请参阅[Med-v 安装文件的命令行选项](command-line-options-for-med-v-installation-files.md)。



## 部署步骤


在整个企业中部署 MED-V 时，有两个主要注意事项： "安装" 和 "首次设置"。

### 安装

1.  **Windows 虚拟电脑**-在安装期间，WINDOWS 虚拟 PC 的 med-v 检查及其所需的 windows 7 更新（KB977206）。 有关详细信息，请参阅[配置安装先决条件](configure-installation-prerequisites.md)。

    你可以在安装 MED-V 之前将它们安装为 Windows 7 安装的一部分，也可以将其安装为 MED-V 分发的一部分。 但是，MED-V 不包括其部署的机制;必须使用电子软件分发（ESD）系统或作为 Windows 7 映像的一部分来部署它们。

    **重要提示**  
    在使用批处理文件安装 MED-V 组件时，最佳做法是指定在 MED-V 主机代理和 MED-V 工作区程序包文件之后安装 Windows 虚拟 PC 和 Windows 虚拟 PC 修补程序。 这意味着，Windows 更新不会通过需要重新启动来导致任何与安装过程的干扰。



~~~
**Note**  
After you install Windows Virtual PC, the computer must be restarted.
~~~



2. **Med-v 主机代理**-在将运行 Med-v 的 Windows 7 计算机上安装 Med-v 主机代理。 必须先安装此功能，然后才能安装 MED-V 工作区并进行检查以确保已安装 Windows 虚拟 PC。

3. **Med-v 工作区**-通过使用 Med-v 工作区包装器创建在此安装中所需的文件： setup.exe、medv 和 .msi 文件。 若要安装 MED-V 工作区，请运行 setup.exe;这会根据需要触发其他文件。 安装会将注册表中的一个条目放入本地计算机运行键，以启动 MED-V 主机代理，该代理在 Windows 启动时始终运行 MED-V。

   **重要提示**  
   MED-V 工作区的安装可由最终用户以交互方式运行或通过电子软件分发系统进行自动运行。 安装 MED-V 工作区需要管理凭据，因此最终用户必须是其计算机的管理员才能安装 MED-V 工作区。 或者，电子软件分发系统通常在系统上下文中运行，并且具有足够的权限。



~~~
**Tip**  
Because of problems that can occur when you install MED-V from a network location, we recommend that you copy the MED-V workspace setup files locally and then run setup.exe.
~~~



### 首次设置

安装 MED-V 并安装其所需组件后，必须配置 MED-V。 MED-V 的配置称为 "首次设置"。 通过使用**Med-v 工作区包装**程序，你可以将首次设置配置为以静默方式或交互方式运行。 第一次设置 MED-V 需要最终用户输入其密码才能对 MED-V 工作区进行身份验证，但在其他情况下，用户几乎看不到它们。 通知区域中显示通知，如首次设置完成且应用程序已准备就绪。 以下是第一次安装 MED-V 时发生的操作：

1.  必须配置虚拟硬盘。 "最小化安装" 运行并扩展 Windows XP 映像。 通常，这发生在隐藏窗口中，但 MED-V 可以配置为在此配置期间显示。

2.  在 "最小化安装" 完成后，你可以运行你必须具有的命令以进行其他配置（如安装 ESD 软件或其他应用程序）或配置映像。 这些可在 Sysprep.inf 文件中调用，但不是必需的。 有关详细信息，请参阅[配置适用于 med-v 的 Windows 虚拟 PC 映像](configuring-a-windows-virtual-pc-image-for-med-v.md)。

3.  Ftscompletion.exe 作为配置中的最后一个步骤运行。 此过程完成 MED-V 配置，将用户添加到 RDP 组，使其可以访问 MED-V 工作区、复制日志、向 MED-V 工作区准备就绪，然后重新启动 MED-V 工作区。 如果在创建 MED-V 工作区时配置此过程，此过程还可以将用户添加为 MED-V 工作区的管理员。 Ftscompletion.exe 通常通过 Sysprep、inf 文件进行调用，但也可以通过另一种方法（如脚本）运行。 但是，Ftscompletion.exe 必须是在配置工作站时执行的最后一步操作。 有关详细信息，请参阅[配置适用于 med-v 的 Windows 虚拟 PC 映像](configuring-a-windows-virtual-pc-image-for-med-v.md)。

4.  Ftscompletion.exe 重新启动 MED-V 工作区后，最终用户登录。 如果他们在首次设置时没有保存密码，系统将再次提示他们。 然后为用户启动并配置 MED-V 工作区。 配置包括应用组策略。

    我们建议你仅应用在 Windows XP 的应用程序兼容性环境中有意义的策略。 例如，桌面个性化策略通常不需要应用，并且应被禁用。 有关如何仅允许本地配置文件的详细信息，请参阅[漫游用户配置文件（.）的组策略设置](https://go.microsoft.com/fwlink/?LinkId=205072) https://go.microsoft.com/fwlink/?LinkId=205072) 。

第一次设置完成后，系统会通知最终用户已发布的应用程序已准备就绪。 然后，他们可以从其 "**开始**" 菜单访问 med-v 工作区中安装的应用程序。

## 相关主题


[为 MED-V 准备部署环境](prepare-the-deployment-environment-for-med-v.md)

[MED-V 的部署](deployment-of-med-v.md)









