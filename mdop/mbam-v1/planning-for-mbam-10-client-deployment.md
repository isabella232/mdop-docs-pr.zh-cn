---
title: 计划 MBAM 1.0 客户端部署
description: 计划 MBAM 1.0 客户端部署
author: dansimp
ms.assetid: 3af2e7f3-134b-4ab9-9847-b07474ca6ac3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d58d6420febd2da9ee9cd4074fc8b5870285b0b4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803856"
---
# 计划 MBAM 1.0 客户端部署


根据你部署 Microsoft BitLocker 管理和监视（MBAM）客户端的时间，你可以在你的组织中的计算机上启用 BitLocker 加密，在最终用户收到计算机之前或之后。 若要在最终用户收到计算机后启用 BitLocker 加密，请配置组策略。 若要在最终用户接收计算机之前启用 BitLocker 加密，请使用企业软件部署系统部署 MBAM 客户端软件。

您可以在您的组织中使用一种或两种方法。 如果使用这两种方法，则可以改进合规性、报告和密钥恢复支持。

**注意** 若要查看 MBAM 客户端系统要求，请参阅[MBAM 1.0 支持的配置](mbam-10-supported-configurations.md)。

 

## 部署 MBAM 客户端以在将计算机分发给最终用户后启用 BitLocker 加密


配置组策略后，您可以使用企业软件部署系统产品（如 Microsoft System Center Configuration Manager 2012 或 Active Directory 域服务）将 MBAM 客户端安装 Windows 安装程序文件部署到目标计算机。 两个 MBAM 客户端安装 Windows Installer 文件 MBAMClient-64bit.msi 和 MBAMClient-32bit.msi，这些文件随 MBAM 软件一起提供。 有关如何部署 MBAM 组策略对象的详细信息，请参阅[部署 MBAM 1.0 组策略对象](deploying-mbam-10-group-policy-objects.md)。

部署 MBAM 客户端时，在将计算机分发给最终用户后，系统会提示最终用户加密其计算机。 这允许 MBAM 收集数据，以包括 PIN 和密码，然后开始加密过程。

**注意** 在此方法中，系统会提示用户激活并初始化受信任的平台模块（TPM）芯片（如果之前尚未激活）。

 

## 在将计算机分发给最终用户之前使用 MBAM 客户端启用 BitLocker 加密


在计算机被集中接收和配置的组织中，你可以安装 MBAM 客户端以在每台计算机上管理 BitLocker 加密，然后再向其写入任何用户数据。 此过程的好处是，每台计算机都将符合 BitLocker 加密的要求。 此方法不依赖于用户操作，因为管理员已加密计算机。 此方案的一个关键假设是，组织的策略在将计算机交付给用户之前安装企业的 Windows 映像。

如果你的组织希望使用（TPM）对计算机进行加密，管理员必须使用 TPM 保护程序加密计算机的操作系统卷。 如果你的组织想要使用 TPM 芯片和 PIN 保护器，管理员必须使用 TPM 保护程序加密系统卷，然后用户在首次登录时选择 PIN 码。 如果您的组织决定仅使用引脚保护器，则管理员不必先加密卷。 当用户在其计算机上登录时，MBAM 会提示他们提供 PIN 或 PIN 以及用户在稍后重新启动计算机时将使用的密码。

**注意** TPM 保护程序选项要求管理员在将计算机交付给用户之前接受激活和初始化 TPM 的 BIOS 提示。

 

## 相关主题


[计划部署 MBAM 1.0](planning-to-deploy-mbam-10.md)

[部署 MBAM 1.0 客户端](deploying-the-mbam-10-client.md)

 

 





