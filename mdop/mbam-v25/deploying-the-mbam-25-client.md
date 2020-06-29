---
title: 部署 MBAM 2.5 客户端
description: 部署 MBAM 2.5 客户端
author: dansimp
ms.assetid: 0a96a0ee-f280-49d9-a244-88f4147fe9fd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 375af8966c8e66a58baec5065d065891187899fc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803936"
---
# 部署 MBAM 2.5 客户端


Microsoft BitLocker 管理和监视（MBAM）客户端软件使管理员能够在企业中的计算机上实施和监视 BitLocker 驱动器加密。 通过电子软件分发系统（如 Active Directory 域服务）部署客户端，或者通过直接加密客户端计算机作为初始映像过程的一部分，可将 BitLocker 客户端集成到组织中。

根据部署 Microsoft BitLocker 管理和监视客户端软件的时间，你可以在最终用户接收计算机之前或通过配置组策略并使用企业软件部署系统部署 MBAM 客户端软件，在组织中的计算机上启用 BitLocker 驱动器加密。

## 将 MBAM 客户端部署到台式计算机或膝上型计算机


配置组策略设置后，你可以使用企业软件部署系统产品（如 MicrosoftSystemCenter2012 ConfigurationManager 或 Active Directory 域服务）将 MBAM 客户端安装 Windows Installer 文件部署到目标计算机。 你可以使用32位或64位 MbamClientSetup.exe 文件或32位或64位 MBAMClient.msi 文件，这些文件随 MBAM 客户端软件一起提供。 有关部署 MBAM 组策略设置的详细信息，请参阅[部署 MBAM 2.5 组策略对象](deploying-mbam-25-group-policy-objects.md)。

**注意** 从 MBAM 2.5 SP1 开始，MBAM 产品不再附带单独的 MSI。 但是，你可以从产品附带的可执行文件（.exe）中提取 MSI。

 

[如何将 MBAM 客户端部署到台式机或笔记本电脑](how-to-deploy-the-mbam-client-to-desktop-or-laptop-computers-mbam-25.md)

## 将 MBAM 客户端部署为 Windows 部署的一部分


在计算机被集中接收和配置的组织中，你可以安装 MBAM 客户端以在每台计算机上管理 BitLocker 驱动器加密，然后再向其写入任何用户数据。 此过程的好处是，每台计算机都与 BitLocker 驱动器加密兼容。 此方法不依赖于用户操作，因为管理员已加密计算机。 此方案的一个关键假设是，组织的策略在将计算机交付给用户之前安装企业的 Windows 映像。 如果已将组策略设置配置为需要 PIN 码，则会在用户收到策略后提示用户设置 PIN。

[如何通过使用 MBAM 将 BitLocker 作为 Windows 部署的一部分来启用](how-to-enable-bitlocker-by-using-mbam-as-part-of-a-windows-deploymentmbam-25.md)

## 如何使用命令行部署 MBAM 客户端


本部分介绍如何使用命令行安装 MBAM 客户端。

[如何使用命令行部署 MBAM 客户端](how-to-deploy-the-mbam-client-by-using-a-command-line.md)

## 用于部署 MBAM 客户端的其他资源


[部署 MBAM 2.5](deploying-mbam-25.md)



## 相关主题


[部署 MBAM 2.5](deploying-mbam-25.md)

[规划 MBAM 2.5](planning-for-mbam-25.md)

 
## 已获得 MBAM 的建议？
- 在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。 
- 对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。
 





