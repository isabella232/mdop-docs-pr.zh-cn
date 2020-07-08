---
title: 增强 App-V 排序期间的安全性
description: 增强 App-V 排序期间的安全性
author: dansimp
ms.assetid: f30206dd-5749-4a27-bbaf-61fc21b9c663
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ba97c334c4ac9a928fee3d69c265c12e82e43619
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798955"
---
# 增强 App-V 排序期间的安全性


打包应用程序进行排序是 App-v 基础结构中最大的持续任务。 由于此任务正在进行，因此应仔细考虑创建顺序应用程序时要遵循的策略和过程。 在 App-v 4.5 中，排序期间，你可以捕获虚拟化应用程序的文件资源上的访问控制列表（Acl）。

## 排序器上的病毒扫描


最佳做法是在排序计算机上安装扫描软件，然后扫描计算机以查找病毒和恶意软件。 在对顺序计算机进行扫描且没有任何病毒或恶意软件后，在对任何应用程序进行排序之前，在排序计算机上禁用扫描软件（包括所有防病毒和恶意软件检测软件）。 这将加快排序过程，并防止扫描软件组件在序列化期间被检测并包含在虚拟应用程序包中。

## 捕获文件上的 Acl （NTFS）


Sequencer 将捕获在排序安装阶段中监视的文件的 NTFS 权限（Acl）。 （在发布 app-v 4.5 之前，不会作为排序过程的一部分捕获 Acl。）此新功能允许某些应用程序针对权限级别较低的用户运行，这些用户通常需要管理权限。

此功能还使排序工程师能够捕获由供应商标识的安全设置。 无法应用供应商推荐的设置可能会使应用程序开放于用户的攻击或滥用。 有关是否应使用开放 Acl 部署应用程序的信息，请参阅你的应用程序支持组或软件供应商。

**重要提示** 虽然排序器在监视排序的安装阶段时捕获了 NTFS Acl，但它不会捕获注册表的 Acl。 用户对虚拟应用程序（服务除外）的所有注册表项具有完全访问权限。 但是，如果用户修改了虚拟应用程序的注册表，该更改将存储在特定位置（）中， `uservol_sftfs_v1.pkg` 并且不会影响其他用户。

 

在安装阶段中，如果需要，排序工程师可以修改文件的默认权限。 排序过程完成后，在保存程序包之前，先后顺序工程师可以选择强制实施在安装阶段捕获的安全描述符。 最佳做法是，如果任何其他解决方案都不允许应用程序在虚拟化后正常运行，则强制实施安全描述符。

 

 





