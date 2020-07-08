---
title: 如何为特定计算机上的所有用户将 App-V 4.6 程序包中的扩展点迁移到转换后的 App-V 5.1 程序包
description: 如何为特定计算机上的所有用户将 App-V 4.6 程序包中的扩展点迁移到转换后的 App-V 5.1 程序包
author: dansimp
ms.assetid: 4ef823a5-3106-44c5-aecc-29edf69c2fbb
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/21/2016
ms.openlocfilehash: 7bac244804b46309a0e0a75cb3742dfe22e92e8f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798406"
---
# 如何为特定计算机上的所有用户将 App-V 4.6 程序包中的扩展点迁移到转换后的 App-V 5.1 程序包


使用以下过程将扩展点从 App-v 4.6 程序包迁移到使用部署配置文件的 App-v 5.1 程序包。

**注意** 此过程假定你运行的是最新版本的 App-v 4.6。  
以下过程不需要 app-v 5.1 管理服务器。

 

**将程序包中的扩展点从 App-v 4.6 包迁移到使用部署配置文件的已转换的 App-v 5.1 程序包**

1. 找到包含要迁移的程序包的部署配置文件的目录。 若要设置策略，请对**userConfiguration**部分进行以下更新：

   **ManagingAuthority TakeoverExtensionPointsFrom46 = "true" PackageName = &lt; 程序包 ID&gt;**

   下面是部署配置文件中内容的示例：

   &lt;？ xml 版本 = "1.0"？&gt;

   &lt;DeploymentConfiguration

   xmlns = " <https://schemas.microsoft.com/appv/2010/deploymentconfiguration> " PackageId = &lt; Package ID &gt; DisplayName = &lt; 显示名称&gt;

   &lt;MachineConfiguration/&gt;

   &lt;UserConfiguration&gt;

   &lt;ManagingAuthority TakeoverExtensionPointsFrom46 = "true"

   PackageName = &lt; 程序包 ID&gt;

   &lt;/UserConfiguration&gt;

   &lt;/DeploymentConfiguration&gt;

2. 要添加 App-v 5.1 程序包，请在提升的 PowerShell 命令提示符中键入：

   PS &gt; **$pkg = Add-AppvClientPackage** **-** &lt; 程序包位置的路径路径指向 &gt;  - **DynamicDeploymentConfiguration** &lt; 部署配置文件的路径 DynamicDeploymentConfiguration 路径&gt;

   PS &gt; **发布-AppVClientPackage $pkg**

3. 若要测试迁移，请使用关联的 FTAs 或快捷方式打开虚拟应用程序。 应用程序随即打开，其中包含 App-v 5.1。 同时，app-v 4.6 程序包和转换后的 App-v 5.1 程序包将发布给用户，但应用程序的 FTAs 和快捷方式已由 app-v 5.1 程序包承担。

   已**获得有关 app-v 的建议**？ 在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。 **遇到了 app-v 问题？** 使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相关主题


[如何为特定计算机上的所有用户将 App-V 5.1 程序包中的扩展点还原到 App-V 4.6 程序包](how-to-revert-extension-points-from-an-app-v-51-package-to-an-app-v-46-package-for-all-users-on-a-specific-computer.md)

[App-V 5.1 的操作](operations-for-app-v-51.md)

 

 





