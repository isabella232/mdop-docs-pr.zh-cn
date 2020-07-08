---
title: 如何配置 VM 计算机名称模式属性
description: 如何配置 VM 计算机名称模式属性
author: dansimp
ms.assetid: ddf79ace-8cc3-4ee6-be5a-5940b4df5c36
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: aa171712b6624b73fb5e0756aaf56277baa4c8cc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804096"
---
# 如何配置 VM 计算机名称模式属性


可以为 revertible 和持久的 MED-V 工作区分配虚拟机计算机名称模式。

-   Revertible-管理员可以为每个 Revertible MED-V 工作区实例分配一个唯一名称，以便使用同一 MED-V 工作区区分多台计算机。

-   持久性—在永久性的 MED-V 工作区中，管理员可以将计算机设置为在安装脚本期间重命名。

## 如何将虚拟机计算机名模式分配给 Revertible MED-V 工作区


**将虚拟机计算机名模式分配给 revertible MED-V 工作区**

1.  单击要配置的 revertible MED-V 工作区。

2.  在 " **REVERTIBLE VM 设置**" 部分中，选中 "**基于计算机名称模式重命名 VM** " 复选框。

3.  在 " **VM 计算机名称模式**" 部分中，输入用于命名虚拟机映像的模式，使用以下选项：

    -   **常量**-使用 med-v 工作区输入将在所有计算机上保持不变的自由文本。

    -   **变量**-输入变量，方法是单击 "**插入变量**"，然后选择下列操作之一：

        -   **用户名**

        -   **域名**

        -   **主机名**

        -   **工作区名称**

        -   **虚拟机名称**

        所选变量将使用 MED-V 工作区特定于计算机。 例如，如果选择了 "**域名**"，每台计算机的唯一名称将包含计算机的域名。

    -   **随机字符**-为要包括在模式中的每个随机字符输入 "\ #"。 使用 MED-V 工作区的每台计算机都将具有指定长度的后缀，该后缀是随机生成的。

    **注意**  
    计算机名的长度限制为15个字符。 如果模式超过限制，将被截尾取整。



4.  在 "**策略**" 菜单上，选择 "**提交**"。

    **注意**  
    仅当选中 "**基于计算机名称模式**（在**revertible VM 设置**" 部分）重命名 vm 时，才能分配 revertible vm 计算机名称模式。



~~~
**Note**  
A unique computer name can be assigned only if it is configured prior to MED-V workspace setup. Changing the name will not affect MED-V workspaces that were already set up.
~~~



## 如何将虚拟机计算机名模式分配给持久的 MED-V 工作区


**将虚拟机计算机名模式分配给持久的 MED-V 工作区**

1.  单击要配置的持久 MED-V 工作区。

2.  在 "**永久性 VM 设置**" 部分中，单击 "**脚本编辑器**"。

3.  在 "**脚本操作**" 对话框中，单击 "**添加**"，然后在子菜单上单击 "**重命名计算机**"。

4.  单击 **"确定"** 关闭 "**脚本操作**" 对话框。

5.  在 " **Vm 设置**" 选项卡上的 " **Vm 计算机名称模式**" 部分中，输入用于重命名计算机的模式，使用以下内容：

    -   **常量**-输入将包含在计算机名称中的任意文本。

    -   **变量**-输入变量，方法是单击 "**插入变量**"，然后选择下列操作之一：

        -   **用户名**

        -   **域名**

        -   **主机名**

        -   **工作区名称**

        -   **虚拟机名称**

        所选变量将特定于正在重命名的计算机。 例如，如果选择了 "**域名**"，计算机名称将包含计算机的域名。

    -   **随机字符**-为要包括在模式中的每个随机字符输入 "\ #"。 计算机将具有指定长度的后缀，该后缀是随机生成的。

    **注意**  
    计算机名的长度限制为15个字符。 如果模式超过限制，将被截尾取整。



6.  在 "**策略**" 菜单上，选择 "**提交**"。

    **注意**  
    只有将计算机设置为 "**脚本操作**" 对话框中的操作时，才会重命名计算机。 有关详细信息，请参阅[如何设置脚本操作](how-to-set-up-script-actions.md)。



## 相关主题


[使用 MED-V 管理控制台用户界面](using-the-med-v-management-console-user-interface.md)

[创建 MED-V 工作区](creating-a-med-v-workspacemedv-10-sp1.md)

[如何设置脚本操作](how-to-set-up-script-actions.md)

[虚拟机配置示例](examples-of-virtual-machine-configurationsv2.md)









