---
ms.reviewer: ''
title: 如何为特定用户将 App-V 5.0 程序包中的扩展点还原到 App-V 4.6 程序包
description: 如何为特定用户将 App-V 5.0 程序包中的扩展点还原到 App-V 4.6 程序包
ms.assetid: f1d2ab1f-0831-4976-b49f-169511d3382a
author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/21/2016
ms.openlocfilehash: 2a0660024734806c508043cc2db030c96cfd16a2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798371"
---
# 如何为特定用户将 App-V 5.0 程序包中的扩展点还原到 App-V 4.6 程序包

*注意：** App-V 4.6 已退出主流支持。

使用以下过程，使用用户配置文件将 app-v 5.0 程序包还原到 App-v 文件格式。

**还原程序包**

1.  确保将 app-v 4.6 程序包发布到用户，但 FTAs 和快捷方式已由 app-v 5.0 程序包（使用以下迁移方法）使用，[如何将应用程序 v 4.6 程序包中的扩展点迁移到特定用户](how-to-migrate-extension-points-from-an-app-v-46-package-to-app-v-50-for-a-specific-user.md)的 app-v 5.0。

    在已转换程序包的部署配置文件的 " **userConfiguration** " 部分中，若要设置策略，请对**userConfiguration**部分进行以下更新： **ManagingAuthority TakeoverExtensionPointsFrom46 = "FALSE" PackageName = &lt; 程序包 ID &gt; **

2.  从提升的命令提示符处，键入：

    PS &gt; **发布-AppVClientPackage $Pkg-DynamicUserConfigurationPath** &lt; 用户配置文件的路径&gt;

3.  执行发布刷新，或等待应用的下一次计划发布刷新-V 4.6。 使用 FTAs 或快捷方式打开应用程序。 现在，应用程序应使用 App-v 4.6 SP2 打开。

    **注意**  
    如果您不再需要 app-v 5.0 程序包，则可以取消发布 app-v 5.0 程序包，扩展点将自动还原为 App-v 4.6。



~~~
**Got a suggestion for App-V**? Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization). **Got an App-V issue?** Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).
~~~

## 相关主题


[App-V 5.0 的操作](operations-for-app-v-50.md)












