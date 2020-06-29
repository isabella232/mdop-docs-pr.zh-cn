---
title: 如何部署工作区映像
description: 如何部署工作区映像
author: dansimp
ms.assetid: b2c77e0d-101d-4956-a27c-8beb0e4f262e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d691514691286c92bd62d6fda6666345e17eb9f3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804083"
---
# 如何部署工作区映像


使用部署包时，可以通过以下方式之一将新映像部署到客户端计算机：

-   [Web 下载](#bkmk-howtodeployaworkspaceimageviatheweb)

-   [映像预暂存](#bkmk-howtodeployaworkspaceimageusingimageprestaging)

-   [在部署程序包内部署映像](#bkmk-howtodeployaworkspaceimageusingadeploymentapackage)

## <a href="" id="bkmk-howtodeployaworkspaceimageviatheweb"></a>如何通过 Web 部署工作区图像


**通过 Web 部署工作区图像**

1.  将 MED-V 图像上载到服务器。

    有关上载图像的信息，请参阅[如何将 Med-v 图像上载到服务器](how-to-upload-a-med-v-image-to-the-server.md)。

2.  创建一个部署程序包，并将服务器路径包含到该映像的位置。

    有关创建部署包的信息，请参阅[如何配置部署包](how-to-configure-a-deployment-package.md)。

3.  将程序包部署到最终用户。

    有关部署程序包的信息，请参阅[如何安装 Med-v 客户端](how-to-install-med-v-clientdeployment-package.md)。

    MED-V 客户端首次安装并启动。 在首次启动时，客户端从客户端安装中指定的服务器地址下载映像。

## <a href="" id="bkmk-howtodeployaworkspaceimageusingimageprestaging"></a>如何使用映像预转储部署工作区映像


**使用映像预暂存部署工作区映像**

1.  创建一个图像预调试文件夹，并将图像推送到该文件夹。

    有关配置映像预暂存的信息，请参阅[如何配置映像预暂存](how-to-configure-image-pre-staging.md)。

2.  创建部署程序包，并包含图像预调试文件夹的路径。

    有关创建部署包的信息，请参阅[如何配置部署包](how-to-configure-a-deployment-package.md)。

3.  将程序包部署到最终用户。

    有关部署程序包的信息，请参阅[如何安装 Med-v 客户端](how-to-install-med-v-clientdeployment-package.md)。

    MED-V 客户端首次安装并启动。 在首次启动时，客户端从客户端安装中指定的预安装文件夹中获取映像。

## <a href="" id="bkmk-howtodeployaworkspaceimageusingadeploymentapackage"></a>如何使用部署包部署工作区映像


**使用部署包部署工作区映像**

1.  创建一个部署程序包，并将该映像包含在程序包中。

    有关创建部署包的信息，请参阅[如何配置部署包](how-to-configure-a-deployment-package.md)。

2.  将程序包部署到最终用户。

    有关部署程序包的信息，请参阅[如何安装 Med-v 客户端](how-to-install-med-v-clientdeployment-package.md)。

    将图像作为软件包安装的一部分导入到主机。

## 相关主题


[如何配置映像 Web 分发服务器](how-to-configure-the-image-web-distribution-server.md)

[如何配置部署包](how-to-configure-a-deployment-package.md)

 

 





