---
title: App-V Package WMI 类
description: App-V Package WMI 类
author: dansimp
ms.assetid: 0fc26c3b-9706-4804-be2d-645771dc33ae
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fa452afaaeb2f490c179a928b24de47207d6dc63
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802360"
---
# App-V Package WMI 类


在应用程序虚拟化（App-v）客户端中，**程序包**类是一个 Windows 管理规范（WMI）类，用于表示客户端上的所有虚拟程序包。 虚拟程序包可以包含许多虚拟应用程序。

## 语法


``` syntax
class Package
{
      string Name;
      string Version;
      string PackageGUID;
      string SftPath;
      uint64 TotalSize;
      uint64 CachedSize;
      uint64 LaunchSize;
      uint64 CachedLaunchSize;
      boolean InUse;
      boolean Locked;
      uint16 CachedPercentage;
      string VersionGUID;
 };
```

## 属性


<a href="" id="name"></a>**名称**  
数据类型：**字符串**

访问类型：只读

限定符：无

虚拟程序包的用户友好名称。

<a href="" id="version"></a>**版本**  
数据类型：**字符串**

访问类型：只读

限定符：无

虚拟包的版本。

<a href="" id="packageguid"></a>**PackageGUID**  
数据类型：**字符串**

访问类型：只读

限定符： Key

程序包配置和源文件的 GUID 标识符。

<a href="" id="sftpath"></a>**SftPath**  
数据类型：**字符串**

访问类型：只读

限定符：无

SFT 文件的文件路径。

<a href="" id="totalsize"></a>**TotalSize**  
数据类型： **UInt64**

访问类型：只读

限定符：无

虚拟包的总大小（以 kb 为单位）。

<a href="" id="cachedsize"></a>**CachedSize**  
数据类型： **UInt64**

访问类型：只读

限定符：无

虚拟包的缓存的总大小（以 kb 为单位）。

<a href="" id="launchsize"></a>**LaunchSize**  
数据类型： **UInt64**

访问类型：只读

限定符：无

虚拟包的主功能块的总大小（以 kb 为单位）。

<a href="" id="cachedlaunchsize"></a>**CachedLaunchSize**  
数据类型： **UInt64**

访问类型：只读

限定符：无

已缓存的虚拟程序包主功能块的总大小（以 kb 为单位）。

<a href="" id="inuse"></a>**InUse**  
数据类型：**布尔型**

访问类型：只读

限定符：无

如果虚拟程序包中的任何虚拟应用程序正在运行，**则为 true** ;否则**为 false**。

<a href="" id="locked"></a>**已锁定**  
数据类型：**布尔型**

访问类型：只读

限定符：无

如果虚拟包已锁定，**则为 true** ;否则**为 false**。

<a href="" id="cachedpercentage"></a>**CachedPercentage**  
数据类型： **UInt16**

访问类型：只读

限定符：无

缓存文件的百分比。 基于以下公式： CachedSize/TotalSize ×100。

<a href="" id="versionguid"></a>**VersionGUID**  
数据类型：**字符串**

访问类型：只读

限定符：无

程序包版本的 GUID 标识符。

 

 





