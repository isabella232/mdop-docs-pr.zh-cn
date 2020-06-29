---
title: 如何为特定计算机上的所有用户将 App-V 5.0 程序包中的扩展点还原到 App-V 4.6 程序包
description: 如何为特定计算机上的所有用户将 App-V 5.0 程序包中的扩展点还原到 App-V 4.6 程序包
ms.assetid: 2a43ca1b-6847-4dd1-ade2-336ac4ac6af0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/21/2016
ms.openlocfilehash: 62542e5cd0b9dcb55f6e8f3db4d4f43c011a2839
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798368"
---
# 如何为特定计算机上的所有用户将 App-V 5.0 程序包中的扩展点还原到 App-V 4.6 程序包

*注意：** App-V 4.6 已退出主流支持。 以下示例假设已安装了 App-v 4.6 SP3 客户端。

使用以下过程，使用部署配置文件将应用程序 V 5.0 程序包中的扩展点还原到 app-v 4.6 文件格式。

**还原程序包**

1.  确保将 app-v 4.6 程序包发布给用户，但 FTAs 和快捷方式已由 app-v 5.0 程序包（使用以下迁移方法）使用，[如何将应用程序 v 4.6 程序包中的扩展点迁移到特定计算机上所有用户的已转换的 app-v 5.0 程序包](how-to-migrate-extension-points-from-an-app-v-46-package-to-a-converted-app-v-50-package-for-all-users-on-a-specific-computer.md)。

    在已转换程序包的部署配置文件的 " **userConfiguration** " 部分中，若要设置策略，请对**userConfiguration**部分进行以下更新： **ManagingAuthority TakeoverExtensionPointsFrom46 = "FALSE" PackageName = &lt; 程序包 ID &gt; **

2.  从提升的命令提示符处，键入：

    PS &gt; **Set-AppvClientPackage $Pkg-DynamicDeploymentConfiguration** &lt; 到部署配置文件的路径&gt;

    PS &gt; **发布-AppVClientPackage $Pkg-DynamicUserConfigurationType useDeploymentConfiguration**

3.  执行发布刷新，或等待适用于 app-v 4.6 SP2 程序包的下一次计划发布刷新。

    使用 FTAs 或快捷方式打开应用程序。 应用程序现在应使用 App-v 4.6 打开。

    **注意**  
    如果您不再需要 app-v 5.0 程序包，则可以取消发布 app-v 5.0 程序包，扩展点将自动还原为 App-v 4.6。



~~~
**Got a suggestion for App-V**? Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization). **Got an App-V issue?** Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).
~~~

## 相关主题


[App-V 5.0 的操作](operations-for-app-v-50.md)









