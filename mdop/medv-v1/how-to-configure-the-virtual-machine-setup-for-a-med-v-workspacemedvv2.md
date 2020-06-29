---
title: 如何为 MED-V 工作区配置虚拟机设置
description: 如何为 MED-V 工作区配置虚拟机设置
author: dansimp
ms.assetid: 50bbf58b-842c-4b63-bb93-3783903f6c7d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d0ba24f0e9aa5befeaf385acf06273a53feaae29
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804095"
---
# 如何为 MED-V 工作区配置虚拟机设置


所有虚拟机设置配置设置均在 " **VM 设置**" 选项卡上的 "**策略**" 模块中配置。

## 如何为持久的 MED-V 工作区配置虚拟机设置


**为持久的 MED-V 工作区配置虚拟机设置**

1.  单击要配置的持久 MED-V 工作区。

2.  在 "**永久性 VM 设置**" 部分中，按下表中所述配置属性。

    **注意**  
    仅对持久的 MED-V 工作区启用永久性 VM 设置属性。



3.  在 "**策略**" 菜单上，选择 "**提交**"。

**持久性 VM 设置属性**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">属性</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>运行 VM 设置</p></td>
<td align="left"><p>选中此复选框以在 MED-V 工作区首次运行时运行安装脚本。</p></td>
</tr>
<tr class="even">
<td align="left"><p>脚本编辑器</p></td>
<td align="left"><p>单击以配置安装脚本。 有关详细信息，请参阅 <a href="how-to-set-up-script-actions.md" data-raw-source="[How to Set Up Script Actions](how-to-set-up-script-actions.md)"> 如何设置脚本操作 </a> 。</p>
<div class="alert">
<strong>注意</strong><br/><p>仅当选择了 " <strong> 运行 VM 安装脚本" 时，此按钮才会启用 </strong> 。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p>脚本运行时显示的消息</p></td>
<td align="left"><p>在脚本运行时要显示的消息。 如果保留为空，则显示默认消息。</p>
<div class="alert">
<strong>注意</strong><br/><p>仅当 <strong> 选中 "运行 VM 安装脚本" 时，才会启用此字段 </strong> 。</p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



## 如何配置 Revertible MED-V 工作区的虚拟机设置


**为 revertible MED-V 工作区配置虚拟机设置**

1.  单击要配置的 revertible MED-V 工作区。

2.  在**REVERTIBLE VM 设置**部分中，按下表中所述配置属性。

    **注意**  
    仅对 revertible MED-V 工作区启用 revertible VM 设置属性。



3.  在 "**策略**" 菜单上，选择 "**提交**"。

**Revertible VM 设置属性**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">属性</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>基于计算机名称模式重命名 VM</p></td>
<td align="left"><p>选中此复选框可使用 MED-V 工作区为每台计算机分配唯一名称，以便你可以使用相同的 MED-V 工作区区分多台计算机。</p>
<p>有关配置计算机映像名称的详细信息，请参阅 <a href="how-to-configure-vm-computer-name-pattern-propertiesmedvv2.md" data-raw-source="[How to Configure VM Computer Name Pattern Properties](how-to-configure-vm-computer-name-pattern-propertiesmedvv2.md)"> 如何配置 VM 计算机名称模式属性 </a> 。</p></td>
</tr>
</tbody>
</table>



## 相关主题


[使用 MED-V 管理控制台用户界面](using-the-med-v-management-console-user-interface.md)

[创建 MED-V 工作区](creating-a-med-v-workspacemedv-10-sp1.md)

[虚拟机配置示例](examples-of-virtual-machine-configurationsv2.md)









