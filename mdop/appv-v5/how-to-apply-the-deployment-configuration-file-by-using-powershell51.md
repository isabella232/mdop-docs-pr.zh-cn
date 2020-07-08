---
title: 如何使用 PowerShell 应用部署配置文件
description: 如何使用 PowerShell 应用部署配置文件
author: dansimp
ms.assetid: 78fe0f15-4a36-41e3-96d6-7d5aa77c1e06
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 49beb7ea4afe46c9b0f1640152c786d7c6ba8663
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798546"
---
# 如何使用 PowerShell 应用部署配置文件


在发布程序包之前，如果将程序包添加或设置为运行 app-v 5.1 客户端的计算机，则应用动态部署配置文件。 该文件为运行 App-v 5.1 客户端的计算机上的所有用户配置程序包的默认设置。 本节介绍用于使用部署配置文件的步骤。 该过程基于以下示例，并假定计算机上存在以下程序包和配置文件：

**c:\\Packages\\Contoso\\MyApp.appv**

**c:\\Packages\\Contoso\\DynamicConfigurations\\deploymentconfig.xml**

**使用 PowerShell 应用部署配置文件**

-   若要为将在特定计算机上运行程序包的所有用户指定新的默认配置集，请使用 PowerShell 控制台键入以下内容：

    **AppVClientPackage-Path c:\\Packages\\Contoso\\MyApp.appv-DynamicDeploymentConfiguration c:\\Packages\\Contoso\\DynamicConfigurations\\deploymentconfig.xml**

    **注意**  
    此命令将生成的对象捕获到 $pkg 中。 如果计算机上已存在该程序包，则可以使用**AppVclientPackage** cmdlet 应用部署配置文档：

    **设置-AppVClientPackage-Name Myapp-Path c:\\Packages\\Contoso\\MyApp.appv-DynamicDeploymentConfiguration c:\\Packages\\Contoso\\DynamicConfigurations\\deploymentconfig.xml**



~~~
**Got a suggestion for App-V**? Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization). **Got an App-V issue?** Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).
~~~

## 相关主题


[App-V 5.1 的操作](operations-for-app-v-51.md)









