---
title: 如何将 MED-V 映像上传到服务器
description: 如何将 MED-V 映像上传到服务器
author: dansimp
ms.assetid: 0e70dfdf-3e3a-4860-970c-535806caa907
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6703eb24bc3542c280af41988a257a2f14643645
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803821"
---
# 如何将 MED-V 映像上传到服务器


测试了 MED-V 图像后，可以将其打包，然后上载到服务器。 有关配置图像 Web 分发服务器的信息，请参阅[如何配置图像 Web 分发服务器](how-to-configure-the-image-web-distribution-server.md)。

将 MED-V 映像打包并上传到服务器后，可以使用企业软件分发中心将其分发给用户，也可以使用部署包由用户下载。 有关使用企业软件分发中心进行部署的信息，请参阅[使用企业软件分发系统部署 Med-v 工作区](deploying-a-med-v-workspace-using-an-enterprise-software-distribution-system.md)。 有关使用程序包进行部署的信息，请参阅[使用部署包部署 Med-v 工作区](deploying-a-med-v-workspace-using-a-deployment-package.md)。

**注意**  
在上载图像之前，验证未在浏览器设置中定义 Web 代理，并且 Windows 更新当前未运行。



**将 MED-V 图像上载到服务器**

1.  在 "**本地打包的图像**" 窗格中，选择您创建的图像。

2.  单击 "**上载**"。

    将图像上载到服务器。 这可能需要花费大量时间。

    服务器上的图像是用下表中列出的属性定义的。

**服务器属性上的压缩图像**

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

[如何打包 MED-V 映像](how-to-pack-a-med-v-image.md)









