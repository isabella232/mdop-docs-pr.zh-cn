---
title: 部署 MBAM 2.0 客户端
description: 部署 MBAM 2.0 客户端
author: dansimp
ms.assetid: 3dd584fe-2a54-40f0-9bab-13ea74040b01
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fa42c8ab3adc273f0e00ba56a59f487deba89c6f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803370"
---
# 部署 MBAM 2.0 客户端


Microsoft BitLocker 管理和监视（MBAM）客户端使管理员能够在企业中的计算机上实施和监视 BitLocker 驱动器加密。 通过电子软件分发系统（如 Active Directory 域服务）部署客户端，或者通过直接加密客户端计算机作为初始映像过程的一部分，可将 BitLocker 客户端集成到组织中。

根据你部署 Microsoft BitLocker 管理和监视客户端的时间，你可以在最终用户接收计算机之前或通过配置组策略并使用企业软件部署系统部署 MBAM 客户端软件，在组织中的计算机上启用 BitLocker 加密。

## 将 MBAM 客户端部署到台式计算机或膝上型计算机


配置组策略后，您可以使用企业软件部署系统产品（如 Microsoft System Center Configuration Manager 2012 或 Active Directory 域服务）将 MBAM 客户端安装 Windows Installer 文件部署到目标计算机。 你可以使用32位或64位 MbamClientSetup.exe 文件，或者使用 MBAM 软件附带的32位或64位 MBAMClient.msi 文件来部署客户端。 有关部署 MBAM 组策略对象的详细信息，请参阅[部署 MBAM 2.0 组策略对象](deploying-mbam-20-group-policy-objects-mbam-2.md)。

[如何将 MBAM 客户端部署到台式机或笔记本电脑](how-to-deploy-the-mbam-client-to-desktop-or-laptop-computers-mbam-2.md)

## 将 MBAM 客户端部署为 Windows 部署的一部分


在计算机被集中接收和配置的组织中，你可以安装 MBAM 客户端以在每台计算机上管理 BitLocker 加密，然后再向其写入任何用户数据。 此过程的优点是，每台计算机都符合 BitLocker 加密标准。 此方法不依赖于用户操作，因为管理员已加密计算机。 此方案的一个关键假设是，组织的策略在将计算机交付给用户之前安装企业的 Windows 映像。 如果已将组策略配置为需要 PIN 码，则会在用户收到组策略后提示用户设置 PIN。

[如何在 Windows 部署过程中部署 MBAM 客户端](how-to-deploy-the-mbam-client-as-part-of-a-windows-deployment-mbam-2.md)

## 如何使用命令行安装 MBAM 客户端


本部分介绍如何使用命令行安装 MBAM 客户端。

[如何使用命令行安装 MBAM 客户端](how-to-use-a-command-line-to-install-the-mbam-client.md)

## 用于部署 MBAM 客户端的其他资源


[部署 MBAM 2.0](deploying-mbam-20-mbam-2.md)[MBAM 2.0 客户端部署计划](planning-for-mbam-20-client-deployment-mbam-2.md)

 

 





