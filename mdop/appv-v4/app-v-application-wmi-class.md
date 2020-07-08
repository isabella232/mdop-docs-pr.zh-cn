---
title: App-V Application WMI 类
description: App-V Application WMI 类
author: dansimp
ms.assetid: b79b0d5a-ba57-442f-8bb4-d7154fc056f9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a4e1e49e35b231ddb2a480a06c46e364121ac2d2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803145"
---
# App-V Application WMI 类


在应用程序虚拟化（App-v）客户端中，**应用程序**类是一个 Windows 管理规范（WMI）类，用于表示客户端上的所有虚拟应用程序。

从托管对象格式（MOF）代码简化了以下语法。 该代码包含所有继承的属性。

## 语法


``` syntax
class Application
{
      string Name;
      string Version;
      string PackageGUID;
      datetime LastLaunchOnSystem;
      uint32 GlobalRunningCount;
      boolean Loading;
      string OriginalOsdPath;
      string CachedOsdPath;
};
```

## 要求


## 属性


<a href="" id="name"></a>**名称**  
数据类型：**字符串**

访问类型：只读

限定符： Key

虚拟应用程序的显示名称。

<a href="" id="version"></a>**版本**  
数据类型：**字符串**

访问类型：只读

限定符： Key

虚拟应用程序的版本。

<a href="" id="packageguid"></a>**PackageGUID**  
数据类型：**字符串**

访问类型：只读

限定符：无

与虚拟应用程序关联的程序包的 GUID。

<a href="" id="lastlaunchonsystem"></a>**LastLaunchOnSystem**  
数据类型： **DateTime**

访问类型：只读

限定符：无

虚拟应用程序启动的最后日期和时间。

<a href="" id="globalrunningcount"></a>**GlobalRunningCount**  
数据类型： **UInt32**

访问类型：只读

限定符：无

直接启动的虚拟应用程序的运行实例的计数。

<a href="" id="loading"></a>**正在加载**  
数据类型：**布尔型**

访问类型：只读

限定符：无

如果正在启动虚拟应用程序，**则为 true** ;否则**为 false**。

<a href="" id="originalosdpath"></a>**OriginalOsdPath**  
数据类型：**字符串**

访问类型：只读

限定符：无

在 App-v 客户端注册的 OSD 文件的原始文件路径。

<a href="" id="cachedosdpath"></a>**CachedOsdPath**  
数据类型：**字符串**

访问类型：只读

限定符：无

如果 App-v 客户端已在本地缓存 OSD 文件，则该 OSD 文件的文件路径。

 

 





