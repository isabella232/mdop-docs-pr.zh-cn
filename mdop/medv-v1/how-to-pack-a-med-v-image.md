---
title: 如何打包 MED-V 映像
description: 如何打包 MED-V 映像
author: dansimp
ms.assetid: e1ce2307-0f1b-4bf8-b146-e4012dc138d2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0a330b8feca922239691bed083767c3acc57105d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803616"
---
# 如何打包 MED-V 映像


必须先压缩 MED-V 映像，然后才能将其添加到部署包或上载到服务器。

**创建打包的 MED-V 映像**

1.  单击 "**图像**管理" 按钮。

2.  在 "**图像**" 模块的 "**本地打包的图像**" 窗格中，单击 "**新建**"。

3.  在 "**打包图像创建**" 对话框中，通过执行下列操作之一选择虚拟机映像：

    -   在 "**基本图像文件**" 字段中，键入为 med-v 准备的 MICROSOFT 虚拟 PC 映像所在目录的完整路径。

    -   单击 "**浏览**" 浏览到准备用于 Med-v 的 MICROSOFT 虚拟 PC 映像所在的目录。

4.  通过执行下列操作之一指定新图像的名称：

    -   在 "**图像名称**" 字段中，键入所需的名称。

        **注意**  
        以下字符不能包含在 "图像名称：空间" &lt; &gt; |\\ / : \* ?



~~~
    A new packed image will be created.

-   From the drop-down list, select an existing name.

    A new version of the existing image will be created.
~~~

5. 单击“确定”****。

   将在你的主机上使用下表中定义的属性创建新的 MED-V 包装图像。

**注意**  
在 "**本地打包的图像**" 和 **"服务器" 窗格上的打包图像**中，每个图像的最新版本将显示为父节点。 单击父节点以查看该映像的所有其他现有版本。



**本地打包的图像属性**

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
<td align="left"><p>在管理员创建图像时定义的压缩图像的名称。</p></td>
</tr>
<tr class="even">
<td align="left"><p>版本</p></td>
<td align="left"><p>所显示的图像的版本。</p>
<div class="alert">
<strong>注意</strong><br/><p>所有以前的版本都将保留，除非已删除。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p>文件大小（已压缩）</p></td>
<td align="left"><p>图像的物理压缩大小。</p></td>
</tr>
<tr class="even">
<td align="left"><p>图像大小（未压缩）</p></td>
<td align="left"><p>图像的物理未压缩大小。</p></td>
</tr>
</tbody>
</table>



## 相关主题


[如何安装 MED-V 客户端和 MED-V 管理控制台](how-to-install-med-v-client-and-med-v-management-console.md)

[使用 MED-V 管理控制台用户界面](using-the-med-v-management-console-user-interface.md)

[为 MED-V 创建虚拟 PC 映像](creating-a-virtual-pc-image-for-med-v.md)









