---
title: 如何将 MBAM 客户端部署到台式机或笔记本电脑
description: 如何将 MBAM 客户端部署到台式机或笔记本电脑
author: dansimp
ms.assetid: f32927a2-4c05-4da8-acca-1108d1dfdb7e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ce4f8597cc182c037983a89efd60c5ef935712ce
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803789"
---
# 如何将 MBAM 客户端部署到台式机或笔记本电脑


Microsoft BitLocker 管理和监视（MBAM）客户端使管理员能够在企业中的计算机上实施和监视 BitLocker 驱动器加密。 通过工具（如 Active Directory 域服务或企业软件部署工具，如 MicrosoftSystemCenter2012 ConfigurationManager）部署客户端，可以将 MBAM 客户端集成到组织中。

**注意** 若要查看 MBAM 客户端系统要求，请参阅[MBAM 1.0 支持的配置](mbam-10-supported-configurations.md)。

 

**将 MBAM 客户端部署到台式计算机或膝上型计算机**

1.  找到 MBAM 软件附带的 MBAM 客户端安装文件。

2.  使用 Active Directory 域服务或企业软件部署工具（如 MicrosoftSystemCenter2012 ConfigurationManager）将 Windows Installer 程序包部署到目标计算机。

    **注意** 不应使用组策略来部署 Windows Installer 程序包。

     

3.  配置分发设置或组策略以运行 MBAM 客户端安装文件。 成功安装后，MBAM 客户端将应用从域控制器收到的组策略设置以开始 BitLocker 加密和管理功能。 有关 MBAM 组策略设置的详细信息，请参阅[规划 MBAM 1.0 组策略要求](planning-for-mbam-10-group-policy-requirements.md)。

    **重要提示** 如果远程桌面协议连接处于活动状态，MBAM 客户端将不会启动 BitLocker 加密操作。 必须先关闭所有远程控制台连接，然后才可开始 BitLocker 加密。

     

## 相关主题


[部署 MBAM 1.0 客户端](deploying-the-mbam-10-client.md)

 

 





