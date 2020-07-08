---
title: 配置 MED-V 以启用远程网络
description: 配置 MED-V 以启用远程网络
author: dansimp
ms.assetid: 4d2f0081-622f-4a6f-8d73-f8c2108036e0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 328376046ee5213f3d5bb09be7adf8c81f8508b1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804025"
---
# 配置 MED-V 以启用远程网络


你可以将 MED-V 配置为在网络内部、远程或远程从网络内部进行工作。

## <a href="" id="bkmk-howtoconfiguremedvtoworkfrominsideanetworkorremotely"></a>


**将 MED-V 配置为从网络内部工作**

-   在网络内配置 MED-V 服务器和映像分布。

**将 MED-V 配置为远程工作**

1.  配置从 Internet 访问的 MED-V 服务器和图像分发服务器。

2.  如果需要，请配置外围网络（也称为 DMZ）反向代理。

3.  在 " *ClientSettings.xml* " 文件中设置身份验证方法，该方法可在**Servers\\Configuration Server\\**文件夹中找到。

**将 MED-V 配置为从网络内部和远程处理**

1.  在网络内配置 MED-V 服务器和图像分发服务器。

2.  确保可以从 Internet 访问服务器。

3.  配置 DNS 解析，以便当客户端尝试连接到服务器时，它会根据客户端位置自动连接到正确的服务器（位于网络或 Internet 内）。

4.  如果需要，请配置外围网络反向代理。

5.  在 " *ClientSettings.xml* " 文件中设置身份验证方法，该方法可在**Servers\\Configuration Server\\**文件夹中找到。

**注意** 应用新设置时，必须重新启动服务。

 

-   你可以将 IIS 身份验证方案更改为下列之一：基本、摘要式、NTLM 或 NEGOTIATE。 默认为 "协商"，并使用以下条目：

    ```xml
    <ImageDistribution>
    <!-- The authentication used for image download. Basic and digest authentication should be used only under SSL.-->
       <!-- The line below can be one of the following: -->
       <!--BG_AUTH_SCHEME>BG_AUTH_SCHEME_BASIC</BG_AUTH_SCHEME-->
       <!--BG_AUTH_SCHEME>BG_AUTH_SCHEME_DIGEST</BG_AUTH_SCHEME-->
       <!--BG_AUTH_SCHEME>BG_AUTH_SCHEME_NTLM</BG_AUTH_SCHEME-->
       <!--BG_AUTH_SCHEME>BG_AUTH_SCHEME_NEGOTIATE</BG_AUTH_SCHEME-->
       <Authentication type="Kidaro.Foundation.Bits.BG_AUTH_SCHEME">
          <BG_AUTH_SCHEME>BG_AUTH_SCHEME_NEGOTIATE</BG_AUTH_SCHEME>
       </Authentication>
    </ImageDistribution>
    ```

## 相关主题


[MED-V 基础结构规划和设计](med-v-infrastructure-planning-and-design.md)

 

 





