---
title: 虚拟机配置示例
description: 虚拟机配置示例
author: dansimp
ms.assetid: 5937601e-41ab-4ca2-8fa1-3c9154710cd6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6b9fc7b1f88b2b30ea149fe73a387826fdbb2a66
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803598"
---
# 虚拟机配置示例


下面是典型的虚拟机配置的示例：一个在永久性的 MED-V 工作区中，另一个位于 revertible MED-V 工作区中。

**注意** 这些示例不适合在所有环境中使用。 根据你的环境调整配置。

 

**在持久的 MED-V 工作区中配置典型域设置**

1.  在基本映像上配置 Sysprep 以创建唯一的 SID。 有关详细信息，请参阅[创建 med-v 的虚拟 PC 映像](creating-a-virtual-pc-image-for-med-v.md#bkmk-howtoconfiguresysprepformedvimages)。

2.  在 " **VM 设置**" 选项卡上，选中 "**运行 VM 设置**" 复选框。

3.  在 " **VM 计算机名称模式**" 部分中，配置计算机映像名称的模式。 有关详细信息，请参阅[如何配置 VM 计算机名称模式属性](how-to-configure-vm-computer-name-pattern-propertiesmedvv2.md)。

4.  单击 "**脚本编辑器**"，然后在 " **VM 设置脚本编辑器**" 对话框中，配置以下操作：

    1.  **重命名计算机**

    2.  **重启 Windows**

    3.  **检查连接性**

    4.  **加入域**

    5.  **禁用自动登录**

    有关详细信息，请参阅[如何设置脚本操作](how-to-set-up-script-actions.md)。

5.  在 "**策略**" 菜单上，单击 "**提交**"。

**在 revertible 工作区中配置典型设置**

1.  在 " **VM 设置**" 选项卡上，选中 "**基于计算机名称模式重命名 VM** " 复选框。

2.  在 " **VM 计算机名称模式**" 部分中，配置计算机映像名称的模式。 有关详细信息，请参阅[如何配置 VM 计算机名称模式属性](how-to-configure-vm-computer-name-pattern-propertiesmedvv2.md)。

3.  在 "**策略**" 菜单上，单击 "**提交**"。

## 相关主题


[如何为 MED-V 工作区配置虚拟机设置](how-to-configure-the-virtual-machine-setup-for-a-med-v-workspacemedvv2.md)

[如何配置 VM 计算机名称模式属性](how-to-configure-vm-computer-name-pattern-propertiesmedvv2.md)

[如何设置脚本操作](how-to-set-up-script-actions.md)

 

 





