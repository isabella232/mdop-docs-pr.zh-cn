---
title: MED-V 故障排除
description: MED-V 故障排除
author: dansimp
ms.assetid: f43dae36-6485-4e06-9c66-0a646e27079d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 38d13be699a92368ff258026acd8e0d5f0e28cd6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803853"
---
# MED-V 故障排除


本部分提供的信息可帮助解决 Microsoft 企业桌面虚拟化（MED-V）中的常见问题。

## 更改主机分辨率，然后最大化 MED-V 工作区使桌面显示为黑色


在完整桌面模式下工作时，如果更改主机分辨率，然后最大化 MED-V 工作区窗口，则桌面会显示为黑色，并且 MED-V 工作区可能不会响应。

### 解决方案

停止并启动 MED-V 工作区。

## 在禁用网络适配器后启动 MED-V 工作区，随后启用适配器不会还原网络连接


如果在桥模式下配置 MED-V 工作区，然后在禁用网络适配器时启动 MED-V 工作区，则如果该适配器已启用，则不会还原通过该适配器的网络连接。

### 解决方案

停止并启动 MED-V 工作区。

## 每台计算机只能由一个 Windows 用户使用图像


MED-V 工作区映像只能由下载或导入该映像的 Windows 用户使用。 除了对下载的图像所在的文件夹拥有权限的管理员而言，此用户是唯一的用户。

### 解决方案

在映像存储上手动更改访问控制列表（ACL）。

## 使用启用了用户权限的配置管理器安装 MED-V 时，卸载失败


如果 MED-V 是使用 Microsoft System Center Configuration Manager 安装的，并且程序包的运行模式设置为 "用户权限"，则卸载失败并显示一条错误消息，指出只有管理员用户可以卸载 MED-V。

### 解决方案

创建 MED-V 的 Configuration Manager 程序包时，请将 "运行模式" 设置为 "管理权限"。

## 使用企业部署系统安装 MED-V 时（安装过程配置为在安装后运行客户端）时，无法运行客户端


如果 MED-V 是使用企业部署系统安装的，并且安装程序包配置为在安装后运行 MED-V 客户端，则在客户端在系统帐户下运行后，你将看不到客户端正在运行（在通知区域中除外），你无法与之进行交互。

### 解决方案

使用企业部署系统安装 MED-V 时，请使用*START \ _MEDV = 0* .msi 参数。

## MED-V 测试图像无法启动


如果不能启动 MED-V 测试映像，它将不会恢复，并且所有未来启动将失败，并出现 "GINA 无法加载" 错误消息。

### 解决方案

删除现有测试映像，然后重新创建它。

## 在尝试使用错误的凭据加入域之后，该映像在加入域时永远不会成功


如果加入域构建基块中存在配置错误（这是虚拟机首次设置脚本的一部分），则它会在尝试加入域时导致 MED-V 工作区失败。 修复配置错误后，MED-V 工作区中包含的图像无法加入域。

### 解决方案

如果已部署映像，请重新发布该映像。 如果图像是测试图像，请重新创建图像。

## MED-V 不支持多台监视器


MED-V 不支持在多台监视器上显示已发布的应用程序。 已发布的应用程序和其他客户端窗口可能显示在错误的屏幕上，有时在屏幕断开连接后，MED-V 会尝试将屏幕发送到监视器，以便连接的监视器显示为空白。

### 解决方案

断开其他屏幕，然后重新启动客户端。

## 如果在 MED-V 工作区启动期间主机崩溃，则 MED-V 工作区可能无法启动


如果主机在 MED-V 工作区启动过程中崩溃，并且出现一条错误消息，显示 "根元素缺失"，则 MED-V 工作区可能会将数据添加到空虚拟机配置（VMC）文件，这将导致启动过程失败。

### 解决方案

将空的 VMC 文件替换为基本图像中的 VMC 文件。

## 键盘在已发布的应用程序窗口中不响应


在 MED-V 工作区中，如果在已发布的应用程序处于焦点时按 Windows 徽标键，键盘将不再在已发布的应用程序窗口中响应。

### 解决方案

当已发布的应用程序处于焦点时，按 Windows 徽标键。

## 域 MED-V 工作区不会更新域凭据


在域环境中使用持久的 MED-V 工作区时，如果您更改域密码，则 MED-V 客户端不会更新 MED-V 工作区域凭据。 当已发布的应用程序尝试访问网络资源时，将收到一条错误消息，通知您凭据已过期。

### 解决方案

重启 MED-V 工作区操作系统。

## 最大化的已发布应用程序窗口覆盖主机任务栏


如果将已发布的应用程序窗口最大化到全屏，它可能会覆盖主机任务栏。

### 解决方案

执行下列操作之一：

最小化已发布的应用程序窗口以获取对通知区域的访问权限，然后重启 MED-V 工作区。

最小化已发布的应用程序窗口，然后将窗口还原为最大化状态。

## 在 MED-V 服务器配置管理器中添加用户或组不起作用


在 "**选择用户或组**" 对话框中添加用户或组时，所选用户或组不会添加到 Med-v 服务器配置管理器中的访问控制列表。

### 解决方案

使用 "**输入用户或组名称**" 对话框添加用户或组。 有关详细信息，请参阅[如何安装和配置 Med-v 服务器组件](how-to-install-and-configure-the-med-v-server-component.md#bkmk-configuringpermissions)。

## 在安装了 windows 7 的 Windows 虚拟 PC 的计算机上，MED-V 不起作用


MED-V 需要 Windows 虚拟 PC2007。 Windows 虚拟电脑 for Windows7 和 Virtual PC2007 SP1 无法安装在同一台计算机上。

### 解决方案

在安装 Virtual PC2007 SP1 和 MED-V 之前卸载 Windows7 的虚拟电脑。

## <a href="" id="med-v-does-not-support-virtual-pc-and-windows-xp-mode-images-"></a>MED-V 不支持虚拟 PC 和 WindowsXP 模式图像


MED-V 1.0 SP1 不支持 Windows 虚拟电脑 for Windows7 创建的图像。 如果使用 Windows7 映像的虚拟 PC，则客户端在启动期间将失败。

### 解决方案

使用 Virtual PC2007 SP1 创建 MED-V 图像。

## Windows 防火墙阻止虚拟 PC2007 SP1 网络活动


默认情况下，Windows 防火墙阻止虚拟 PC2007 SP1 网络活动，并且当 Virtual PC2007 SP1 在客户端计算机上启动时，将阻止其启动顺序和所有网络访问。

### 解决方案

在由最终用户使用 MED-V 之前使用组策略更新防火墙例外。

## 升级客户端时会出现一条错误消息


将客户端从 MED-V 1.0 升级到 MED-V 1.0 SP1 时，可能会显示一条消息，通知您未定义任何 MED-V 工作区。

### 解决方案

关闭客户端，然后重新启动它。

## 相关主题


[MED-V 1.0 发行说明](med-v-10-release-notesmedv-10.md)

[MED-V 1.0 SP1 和 SP2 发行说明](med-v-10-sp1-and-sp2-release-notesmedv-10-sp1.md)

 

 





