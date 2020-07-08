---
title: 使用企业软件分发系统部署 MED-V 工作区
description: 使用企业软件分发系统部署 MED-V 工作区
author: dansimp
ms.assetid: 867faed6-74ce-4573-84be-8bf26e66c08c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fb9ebbc0fb605f84c5a8e67fc77fd9be51b29ff4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803406"
---
# 使用企业软件分发系统部署 MED-V 工作区


MED-V 客户端可以使用企业软件分发系统（如 Microsoft System Center Configuration Manager）进行分发。

**注意** 如果 MED-V 是使用 Microsoft System Center Configuration Manager 安装的，则在为 MED-V 创建程序包时，请将 "运行模式" 设置为 "管理权限"。

 

使用企业软件分发系统部署 MED-V 之前，请确保已创建一个 MED-V 映像供部署使用。 有关创建 MED-V 图像的详细信息，请参阅[创建 Med-v 图像](creating-a-med-v-image.md)。

准备好 MED-V 映像后，请考虑在你的环境中分发映像的最佳方法。 可以通过以下方式之一分发图像：

-   已上载到 Web 并通过 Web 下载分发，可选择利用修剪转移技术。

-   使用映像预分段进行分发。

## 通过 Web 部署图像


如果要通过 Web 部署映像，请将 MED-V 图像上载到图像 Web 分发服务器。 有关配置图像 Web 分发服务器的信息，请参阅[如何配置图像 Web 分发服务器](how-to-configure-the-image-web-distribution-server.md)。 有关将图像上载到服务器的信息，请参阅[如何将 Med-v 图像上载到服务器](how-to-upload-a-med-v-image-to-the-server.md)。

## 通过预暂存部署映像


如果你是通过预暂存的映像部署映像，请配置前暂存文件夹，并将 MED-V 图像推送到该文件夹。 有关配置映像预暂存的详细信息，请参阅[如何配置映像预暂存](how-to-configure-image-pre-staging.md)。

**注意** 如果你使用的是映像预暂存，在推送客户端 .msi 程序包之前，请务必先配置图像预调试文件夹。 需要将文件夹路径包含在客户端 .msi 程序包中。

 

最后，使用企业软件分发中心推送客户端 .msi 程序包。 然后，可以安装 MED-V 并部署映像。 有关安装 MED-V 客户端的详细信息，请参阅[如何安装 Med-v 客户端](how-to-install-med-v-clientesds.md)。 有关部署映像的详细信息，请参阅[如何部署工作区映像](how-to-deploy-a-workspace-imageesds.md)。

 

 





