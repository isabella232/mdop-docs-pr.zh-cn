---
title: 更新 MED-V 工作区映像
description: 更新 MED-V 工作区映像
author: dansimp
ms.assetid: 1b9c4a73-3487-43d2-98e3-43dbc79e10e3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 60a5d12622e0cb7012c6d0a22124d63c085f6d0a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803851"
---
# 更新 MED-V 工作区映像


可通过以下方式之一更新图像：

-   可以使用企业软件分发系统将更新推送到来宾操作系统。

-   更新可以上载到图像 Web 分发服务器，然后由客户端下载并应用于 MED-V 映像。

-   可以更新和重新部署 MED-V 基本图像。

## <a href="" id="bkmk-howtoupdateamedvimageusinganesd"></a>如何使用企业软件分发系统更新 MED-V 映像


**使用企业软件分发系统更新 MED-V 映像**

-   请参阅您正在使用的系统的文档。

## <a href="" id="bkmk-howtoupdateamedvimageusingwebdownload"></a>如何使用 Web 下载更新 MED-V 图像


**使用 Web 下载更新 MED-V 图像**

1.  在 MED-V 管理的 "**虚拟机**" 选项卡上，确保将以下设置应用到与正在更新的 med-v 映像相关联的 med-v 工作区策略：

    -   选中 "**新版本可用时的建议更新**" 复选框。

    -   （可选）**在 "下载此工作区的图像**" 复选框处于选中状态时，客户端应使用 "剪裁传输"。

    有关详细信息，请参阅[如何将虚拟机设置应用到 Med-v 工作区](how-to-apply-virtual-machine-settings-to-a-med-v-workspace.md)。

2.  将图像更新上载到图像 Web 分发服务器。

    具有需要更新的图像的所有客户端都将自动下载更新，并将其应用到映像。

## <a href="" id="bkmk-howtoupdateamedvbaseimage"></a>如何更新 MED-V 基本图像


**更新 MED-V 基本图像**

1.  在虚拟 PC2007 中打开现有图像。

2.  对图像进行所需的更改（如安装新软件）。

3.  关闭虚拟 PC2007。

4.  测试图像。

5.  在测试图像后，将其打包到本地存储库，使用与现有图像相同的名称。

    **注意** 如果将该图像命名为与现有版本不同的名称，将创建新的图像，而不是现有图像的新版本。

     

6.  将新版本上载到服务器，将其推送到 "图像预调试" 文件夹，或通过部署包分发。

## 相关主题


[创建 MED-V 映像](creating-a-med-v-image.md)

[如何更新 MED-V 映像](how-to-update-a-med-v-image.md)

[配置 MED-V 工作区策略](configuring-med-v-workspace-policies.md)

[如何配置映像 Web 分发服务器](how-to-configure-the-image-web-distribution-server.md)

 

 





