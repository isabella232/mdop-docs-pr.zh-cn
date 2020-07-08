---
title: 维护 App-V 5.1
description: 维护 App-V 5.1
author: dansimp
ms.assetid: 5abd17d3-e8af-4261-b914-741ae116b0e7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 431ad65507a5699358159c73eaf9f3cf0dee33b7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798339"
---
# 维护 App-V 5.1


完成所有必要的计划，然后部署 app-v 5.1 之后，你可以使用以下信息维护 App-v 5.1 基础结构。

## <a href="" id="move-the-app-v-5-1-server-"></a>移动 app-v 5.1 服务器


App-v 5.1 服务器连接到 app-v 5.1 数据库。 因此，你可以将管理组件安装到网络上的任何计算机，然后将其连接到 app-v 5.1 数据库。

[如何将 App-V Server 移动到另一台计算机](how-to-move-the-app-v-server-to-another-computer51.md)

## <a href="" id="determine-if-an-app-v-5-1-application-is-running-virtualized-"></a>确定 App-v 5.1 应用程序是否运行虚拟化


希望确定应用程序是否使用 App-v 5.1 或更高版本运行的独立软件供应商（ISV）应在默认命名空间中打开名为**AppVVirtual 的 &lt; &gt; **命名对象。 例如，Windows API **GetCurrentProcessId （）** 可用于获取当前进程的 ID （例如4052），然后，如果可以使用**OpenEvent （）** 在默认命名空间中成功打开名为**AppVVirtual-4052**的命名事件对象，则应用程序是虚拟的。 如果**OpenEvent （）** 调用失败，则应用程序不是虚拟的。

此外，要使用 app-v 5.1 和更高版本在特定 API 上显式虚拟化或不虚拟化调用的 ISV 用户可以使用在 AppEntSubsystems32.dll 模块中实现的**VirtualizeCurrentThread （）** 和**CurrentThreadIsVirtualized （）** 函数。 这些方法提供了一种在下游组件上进行提示的方法，即不应虚拟化调用。






## 用于维护 App-v 5.1 的其他资源


[App-V 5.1 的操作](operations-for-app-v-51.md)

 

 





