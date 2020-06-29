---
title: 将 MED-V 服务器配置为群集模式
description: 将 MED-V 服务器配置为群集模式
author: dansimp
ms.assetid: 41f0b2a3-4ce9-48e1-a6fb-4c13c4228515
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ddb7dd5af65d8a465c5c1884bb27a3027621bac1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804024"
---
# 将 MED-V 服务器配置为群集模式


你可以在群集模式下配置 MED-V 服务器。 在群集模式中，将使用两个服务器，并将两个服务器标识为相互的所有文件都放置在文件系统上。 服务器从文件系统访问文件，而不是本地存储文件。

## <a href="" id="bkmk-howtoconfigurethemedvserverinclustermode"></a>


**在群集模式下配置 MED-V 服务器**

1.  在其中一个服务器上安装和配置 MED-V。

2.  在所有服务器都可以访问的中心位置创建共享网络。

3.  将* &lt; InstallDir &gt; /Servers/ConfigurationServer*文件夹的内容复制到共享网络。

4.  在所有指定的服务器上安装 MED-V 服务器。

5.  在共享网络上，分配对所有 MED-V 服务器系统帐户的完全访问权限。

6.  在每台服务器上，执行下列操作：

    1.  在* &lt; InstallDir &gt; /Servers/ServerConfiguration.xml*文件中，将* &lt; StorePath &gt; *的值设置为共享网络路径。

    2.  将* &lt; InstsallDir &gt; /Servers/KeyPair.xml*文件从原始服务器复制到所有 med-v 服务器。

    3.  重新启动 MED-V 服务。

**注意** 如果所有服务器都具有相同的本地设置（如侦听端口、IIS 服务器、管理权限、报表数据库等），则* &lt; InstallDir &gt; /Servers/ServerSettings.xml*也可以由所有服务器共享。

 

## 相关主题


[MED-V 基础结构规划和设计](med-v-infrastructure-planning-and-design.md)

 

 





