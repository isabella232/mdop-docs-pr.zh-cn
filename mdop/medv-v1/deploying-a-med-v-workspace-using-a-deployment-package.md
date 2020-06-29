---
title: 使用部署包部署 MED-V 工作区
description: 使用部署包部署 MED-V 工作区
author: dansimp
ms.assetid: e07fa70a-1a9f-486f-9a86-b33593b234da
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: dc16b32fd44e45606df5502fda2e580d404dbb19
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803407"
---
# 使用部署包部署 MED-V 工作区


部署程序包安装提供了一种方法，用于安装 MED-V 客户及其所有必需的先决条件以及由管理员预定义的任何设置。

使用部署程序包时，将通过共享网络或可移动媒体分发程序包。 图像可以包含在程序包中，也可以单独分发。

在创建部署程序包之前，请确保已创建准备好部署的 MED-V 映像。 有关创建 MED-V 图像的详细信息，请参阅[创建 Med-v 图像](creating-a-med-v-image.md)。

准备好 MED-V 映像后，请考虑在你的环境中分发映像的最佳方法。 可以通过以下方式之一分发图像：

-   通过 Web 下载上传到 Web 并进行分发，也可以选择使用 "剪裁传输技术"。

-   使用映像预分段进行分发。

-   包含在部署程序包中，并与所有其他 MED-V 组件一起分发。

如果该图像将包含在程序包中，则不需要任何其他配置。 如果部署程序包中不包含该映像，请执行下列操作之一：

-   如果要通过 Web 部署映像，请将 MED-V 图像上载到图像 Web 分发服务器。 有关配置图像 Web 分发服务器的信息，请参阅[如何配置图像 Web 分发服务器](how-to-configure-the-image-web-distribution-server.md)。 有关将图像上载到服务器的信息，请参阅[如何将 Med-v 图像上载到服务器](how-to-upload-a-med-v-image-to-the-server.md)。

-   如果你是通过预暂存的映像部署映像，请配置前暂存文件夹，并将 MED-V 图像推送到该文件夹。 有关配置映像预暂存的详细信息，请参阅[如何配置映像预暂存](how-to-configure-image-pre-staging.md)。

**注意** 如果你使用的是映像预暂存，则在创建部署包之前配置图像预调试文件夹非常重要。 文件夹路径需要包含在部署程序包中。

 

最后，创建部署程序包。 有关创建部署包的详细信息，请参阅[如何配置部署包](how-to-configure-a-deployment-package.md)。 程序包完成后，将其分配给部署。

分发部署包后，可以安装 MED-V 客户端并部署映像。 有关安装 MED-V 客户端的详细信息，请参阅[如何安装 Med-v 客户端](how-to-install-med-v-clientdeployment-package.md)。 有关部署映像的详细信息，请参阅[如何部署工作区映像](how-to-deploy-a-workspace-imagedeployment-package.md)。

 

 





