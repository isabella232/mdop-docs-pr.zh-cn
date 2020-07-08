---
title: 如何配置映像 Web 分发服务器
description: 如何配置映像 Web 分发服务器
author: dansimp
ms.assetid: 2d32ae79-dff5-4c05-a412-dd15452b6007
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 8a21b14fbaca6bbc09d4c35b4d8fb86365c42e3b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803712"
---
# 如何配置映像 Web 分发服务器


图像存储库是用于映像分发的可选服务器（在此情况下，管理员上载新图像和客户端计算机每15分钟检查一次服务器，并在有新的映像时更新其映像）。

## <a href="" id="bkmk-configuringanimagereporitoryusingiis"></a>


映像分发服务器需要以下内容：

-   Internet information Services （IIS）-有关信息，请参阅[Internet 信息服务](https://go.microsoft.com/fwlink/?LinkId=142995)。

    在 IIS 安装期间，在添加角色服务时，请选择以下受支持的身份验证方法：

    -   **基本身份验证**

    -   **Windows 身份验证**

    -   **客户端证书映射身份验证**

    配置 IIS 时，请包括以下内容：

    -   使用名为**MEDVImages**的别名添加虚拟目录。 物理路径应指向图像的位置。

    -   启用 BITS。

    -   添加以下 MIME 类型：

        -   **。 ckm （应用程序/八进制流）**

        -   **。索引（应用程序/八进制流**）

    -   在 MED-V 网站上，向**所有人**添加 "读取" 权限。

    -   重新启动 IIS。

-   适用于 IIS 的 BITS 服务器扩展-有关信息，请参阅[安装 BITS 服务器扩展](https://go.microsoft.com/fwlink/?LinkId=142996)。

## 相关主题


[支持的配置](supported-configurationsmedv-orientation.md)

[设计 MED-V 映像存储库](design-the-med-v-image-repositories.md)

 

 





