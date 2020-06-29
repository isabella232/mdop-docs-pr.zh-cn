---
title: 部署 MBAM 1.0 客户端
description: 部署 MBAM 1.0 客户端
author: dansimp
ms.assetid: f7ca233f-5035-4ff9-ab3a-f2453b4929d1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: dee8c2f4a9b398c9f0797ada35e4c36610c755b1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803261"
---
# 部署 MBAM 1.0 客户端


Microsoft BitLocker 管理和监视（MBAM）客户端使管理员能够在企业中的计算机上实施和监视 BitLocker 驱动器加密。 通过诸如 Active Directory 域服务之类的工具部署客户端，或者在初始映像过程中直接加密客户端计算机，可将 BitLocker 客户端集成到组织中。

根据部署 MBAM 客户端的时间，你可以在你组织中的计算机上或最终用户接收计算机之前或之后启用 BitLocker 加密。 若要控制此计时，请配置组策略并使用企业软件部署系统部署 MBAM 客户端软件。

您可以在您的组织中使用其中一个或两个方法。 如果使用这两种方法，则可以改进合规性、报告和密钥恢复支持。

## 将 MBAM 客户端部署到台式计算机或膝上型计算机


配置组策略后，你可以将 MBAM 客户端安装 Windows Installer 文件部署到目标计算机。 你可以使用企业软件部署系统产品（如 Microsoft System Center 2012 配置管理器或 Active Directory 域服务）执行此操作。 两个可用的 MBAM 客户端安装 Windows 安装程序文件 MBAMClient-64bit.msi 和 MBAMClient-32bit.msi。 这些文件随 MBAM 软件一起提供。 有关如何部署 MBAM 组策略对象的详细信息，请参阅[部署 MBAM 1.0 组策略对象](deploying-mbam-10-group-policy-objects.md)。

[如何将 MBAM 客户端部署到台式机或笔记本电脑](how-to-deploy-the-mbam-client-to-desktop-or-laptop-computers-mbam-1.md)

## 将 MBAM 客户端部署为 Windows 部署的一部分


在某些组织中，新计算机的接收和配置是集中的。 这种情况使管理员能够在任何用户数据写入计算机之前安装 MBAM 客户端来管理每台计算机上的 BitLocker 加密。 此方法有助于确保计算机被正确加密，因为管理员执行操作时不依赖最终用户操作。 此方案的一个关键假设是，组织的策略在将计算机交付给用户之前安装企业的 Windows 映像。

[如何在 Windows 部署过程中部署 MBAM 客户端](how-to-deploy-the-mbam-client-as-part-of-a-windows-deployment-mbam-1.md)

## 用于部署 MBAM 客户端的其他资源


[部署 MBAM 1.0](deploying-mbam-10.md)

[计划 MBAM 1.0 客户端部署](planning-for-mbam-10-client-deployment.md)

 

 





