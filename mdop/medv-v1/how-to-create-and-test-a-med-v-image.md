---
title: 如何创建和测试 MED-V 映像
description: 如何创建和测试 MED-V 映像
author: dansimp
ms.assetid: 40e4aba6-12cb-4794-967d-2c09dc20d808
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9f7989871a695b09c987124ab02c0143082148f3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804089"
---
# 如何创建和测试 MED-V 映像


MED-V 管理员创建了一个 MED-V 映像，以便它可以上载，与 MED-V 工作区相关联，然后通过 Web 分发给客户端，添加到 MED-V 程序包，或使用第三方系统下载到客户端。 建议在部署之前先创建一个测试图像并在 MED-V 客户端上对其进行测试。

创建 MED-V 图像时，它将经历以下阶段：

1.  **本地测试图像**-可在本地测试的基本图像。

2.  **本地打包的映像**-测试图像后，图像将打包为测试前的存在。 打包的映像中不包含测试期间所做的更改。

3.  **在服务器上打包的图像**-将打包的图像上载到服务器。

## 如何创建 MED-V 测试图像


**创建新的 MED-V 测试图像**

1.  单击 "**图像**管理" 按钮。

    将显示 "**图像**" 模块。

    -   "**图像**" 模块包含以下窗格：

        -   **本地测试图像**-本地解包的图像。

        -   **本地打包的图像**-本地计算机上的所有打包图像。

        -   **服务器上的压缩图像**-已打包并上载到服务器的所有图像。

    -   在 "**本地打包的图像**" 和 **"服务器" 窗格上的打包图像**中，每个图像的最新版本将显示为父节点。 单击父节点以查看该映像的所有其他现有版本。

2.  在 "**本地测试图像**" 窗格中，单击 "**新建**"。

3.  在 "**测试映像创建**" 对话框中，通过执行下列操作之一，选择要配置为 med-v 测试映像的虚拟机映像：

    -   在 "**基本图像**文件" 字段中，键入为 med-v 准备的 MICROSOFT 虚拟 PC 映像所在目录的完整路径。

    -   单击 "**浏览**" 浏览到准备用于 Med-v 的 MICROSOFT 虚拟 PC 映像所在的目录。

4.  在 "**图像名称**" 字段中，键入或选择所需的名称。

    **注意** 以下字符不能包含在 "图像名称：空间" &lt; &gt; |\\ / : \* ?

     

5.  单击“确定”****。

    将在你的主机上使用下表中定义的属性创建新的 MED-V 测试图像。

    有关配置 MED-V 工作区映像的详细信息，请参阅[配置 Med-v 工作区策略](configuring-med-v-workspace-policies.md)。

**本地测试图像属性**

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
<td align="left"><p>图像名称</p></td>
<td align="left"><p>在管理员创建图像时定义的测试映像的名称。</p></td>
</tr>
<tr class="even">
<td align="left"><p>图像路径</p></td>
<td align="left"><p>测试图像的本地路径。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>已创建</p></td>
<td align="left"><p>测试映像的创建日期。</p></td>
</tr>
</tbody>
</table>

 

## 如何从 MED-V 客户端测试 MED-V 映像


创建 MED-V 测试图像后，请使用以下过程在本地测试图像。

**测试 MED-V 映像**

1.  单击 "**策略**管理" 按钮。

2.  在**策略**模块中，通过执行下列操作将 med-v 测试映像分配给 med-v 工作区：

    1.  单击 "**虚拟机**" 选项卡。

    2.  在 "**分配的图像**" 字段中，选择您创建的 med-v 测试图像。 如果你的测试图像不在列表中，请单击 "**刷新**"。

    3.  在工具栏上，单击 "**保存更改**"。

3.  配置要测试的任何其他 MED-V 工作区设置。 有关详细信息，请参阅[配置 Med-v 工作区策略](configuring-med-v-workspace-policies.md)。

4.  启动 MED-V-V 客户端。

5.  在 "**确认正在运行的测试**确认" 框中，单击 "**使用测试图像**"。

6.  测试 MED-V 工作区测试图像。

    有关启动和运行 MED-V 客户端的信息，请参阅[Med-v 客户端操作](med-v-client-operations.md)。

**注意** 测试图像时，请勿打开 VPC 并对图像进行更改。

 

**注意** 测试图像时，不会在会话之间保存任何更改;而是保存在单独的临时文件中。 这是为了确保在生产环境中打包和运行图像时，它是原始的干净图像。

 

## 相关主题


[为 MED-V 创建虚拟 PC 映像](creating-a-virtual-pc-image-for-med-v.md)

[创建 MED-V 工作区](creating-a-med-v-workspacemedv-10-sp1.md)

[配置 MED-V 工作区策略](configuring-med-v-workspace-policies.md)

[MED-V 客户端操作](med-v-client-operations.md)

 

 





