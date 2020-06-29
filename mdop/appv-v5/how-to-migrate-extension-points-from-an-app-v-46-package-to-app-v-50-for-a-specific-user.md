---
title: 如何为特定用户将 App-V 4.6 程序包中的扩展点迁移到 App-V 5.0
description: 如何为特定用户将 App-V 4.6 程序包中的扩展点迁移到 App-V 5.0
ms.assetid: dad25992-3c75-4b7d-b4c6-c2edf43baaea
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/21/2016
ms.openlocfilehash: a17d9dad11092a4c8356983b70bea3c18da1be04
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798405"
---
# 如何为特定用户将 App-V 4.6 程序包中的扩展点迁移到 App-V 5.0

*注意：** App-V 4.6 已退出主流支持。

使用以下过程迁移使用 "用户配置" 文件的 App-v 创建的程序包。

**转换程序包**

1. 找到要转换的程序包的用户配置文件。 若要设置策略，请在**userConfiguration**部分中执行以下更新： **ManagingAuthority TakeoverExtensionPointsFrom46 = "true" PACKAGENAME = &lt; 程序包 ID &gt; **。

   以下是用户配置文件的示例：

   &lt;？ xml 版本 = "1.0"？&gt;

   &lt;UserConfiguration PackageId = &lt; 程序包 ID &gt; DisplayName = &lt; 程序包的名称&gt;

   xmlns = " <https://schemas.microsoft.com/appv/2010/userconfiguration"&gt> ; &lt;ManagingAuthority TakeoverExtensionPointsFrom46 = "true"

   PackageName = &lt; 程序包 ID&gt;

   &lt;/UserConfiguration&gt;

2. 若要添加 App-v 5.0 程序包，请在提升的 PowerShell 命令提示符中键入以下内容：

   PS &gt; **$Pkg = AppvClientPackage-** &lt; 程序包位置路径路径&gt;

   PS &gt; **发布-AppVClientPackage $pkg DynamicUserConfiguration** &lt; 用户配置文件的路径&gt;

3. 现在使用 FTAs 或快捷方式打开应用程序。 应用程序应使用 App-v 5.0 打开。

   将向用户发布 app-v SP2 程序包和已转换的 App-v 5.0 程序包，但应用程序的 FTAs 和快捷方式已由 app-v 5.0 程序包承担。

   已**获得有关 app-v 的建议**？ 在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。 **遇到了 app-v 问题？** 使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相关主题


[App-V 5.0 的操作](operations-for-app-v-50.md)

 

 





