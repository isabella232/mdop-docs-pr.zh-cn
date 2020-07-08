---
title: App-V 5.0 SP1 中的新增功能
description: App-V 5.0 SP1 中的新增功能
author: dansimp
ms.assetid: e97c2dbb-7b40-46a0-8137-9ee4fc2bd071
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2542d0cc5a544d26b3279b24063cf3ef428b9f39
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798240"
---
# App-V 5.0 SP1 中的新增功能


本部分适用于已熟悉 app-v 的用户，想要了解 app-v 5.0 SP1 中的更改。 如果你还不熟悉 App-v，应首先阅读适用[于 app-v 5.0 的规划](planning-for-app-v-50-rc.md)。

## 标准功能的更改


以下各节包含有关 App-v 5.0 SP1 的标准功能更改的信息。

### 对受支持语言的更改

有关详细信息，请参阅[关于 App-V 5.0 SP1](about-app-v-50-sp1.md)。

以下列表包含有关新语言包的详细信息：

-   App-v 5.0 SP1 语言包已捆绑到所有 App-v 5.0 组件的**appv\_xxx\_setup.exe**安装程序中。

-   运行安装程序时，它将根据在目标计算机上运行的关联操作系统的区域设置自动安装最合适的语言包。

-   如果需要其他语言包，则必须通过运行以下命令从安装程序提取这些语言包： `appv_xxx_setup.exe /Layout /LayoutDir=”<path>”` 。 运行此操作后，安装程序的内容将解压缩到指定位置。

-   必须通过应用相应语言包的 Windows 安装文件来安装所需的语言包。 例如， **appv\_hib\_LP\_jmmb\_x86.msi**或**appv\_hib\_LP\_jmmb\_x64.msi**，其中**hib**指的是组件， **jmmb**指的是区域设置。

## Microsoft Office2010 增强版支持


**适用于应用程序虚拟化的 Microsoft Office 2010 排序包 5.0** -通过 microsoft Office2010 的虚拟化版本帮助用户提供一致的体验。 **应用程序虚拟化5.0 的 Microsoft office 2010 排序工具包**与适用于 App-v 的**Microsoft Office 2010 部署工具包**结合使用，并且还提供所需的 Microsoft Office2010 授权服务。






## 相关主题


[关于 App-V 5.0](about-app-v-50.md)

 

 





